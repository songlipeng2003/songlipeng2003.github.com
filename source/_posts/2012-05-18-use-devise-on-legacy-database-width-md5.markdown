---
layout: post
title: "use devise on legacy database width md5"
date: 2012-05-18 17:01
comments: true
categories: ruby rails devise
---
建议使用deivse 2.1,并且添加devise-encryptable

``` ruby
# Gemfile
gem 'devise', '~> 2.1'
gem 'devise-encryptable'
```

实现自己的加密方式,我是使用的是md5：

``` ruby
# lib/devise/encryptable/encryptors/md5.rb
require 'digest/md5'

module Devise
  module Encryptable
    module Encryptors
      class Md5 < Base
        def self.digest(password, stretches, salt, pepper)
          str = [password, salt].flatten.compact.join
          Digest::MD5.hexdigest(str)
        end
      end
    end
  end
end
```

如果Devise版本低于2.1

``` ruby
# lib/devise/encryptors/md5.rb
require 'digest/md5'

module Devise
  module Encryptors
    class Md5 < Base
      def self.digest(password, stretches, salt, pepper)
        str = [password, salt].flatten.compact.join
        Digest::MD5.hexdigest(str)
      end
    end
  end
end
```

在config/initializers/devise.rb中加载md5加密

``` ruby
require Rails.root.join('lib', 'devise', 'encryptable', 'encryptors', 'md5')
```

在config/initializers/devise.rb中修改加密方式为md5

``` ruby
config.encryptor = :md5
```

添加 :encryptable 到User model.

如果password_salt为空的话，要在model中加入如下代码

``` ruby
# for devise
class User < ActiveRecord::Base
  # Include default devise modules. Others available are:
  # :token_authenticatable, :encryptable, :confirmable, :lockable, :timeoutable and :omniauthable
  devise :database_authenticatable, :registerable, :confirmable,
         :recoverable, :rememberable, :trackable, :validatable
  devise :encryptable

  # Setup accessible (or protected) attributes for your model
  attr_accessible :email, :username, :password, :password_confirmation, :remember_me
  
  # for devise
  def password_salt=(password_salt)
  end

  def password_salt
  end
  
  protected

    def password_digest(password)
        Devise::Encryptable::Encryptors::Md5::digest(password, self.class.stretches, authenticatable_salt, self.class.pepper)
    end
end
```

这里必须覆盖password_digest方法，因为password_digest中监测了password_salt是否为空

在https://github.com/plataformatec/devise-encryptable/blob/master/lib/devise/encryptable/model.rb中56行

```ruby
# Digests the password using the configured encryptor.
      def password_digest(password)
        if password_salt.present?
          encryptor_class.digest(password, self.class.stretches, authenticatable_salt, self.class.pepper)
        end
      end
```

### 参考信息:
[How-To:-Create-a-custom-encryptor](https://github.com/plataformatec/devise/wiki/How-To:-Create-a-custom-encryptor)

