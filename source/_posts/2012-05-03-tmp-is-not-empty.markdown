---
layout: post
title: "/tmp/目录没有空间"
date: 2012-05-03 21:36
comments: true
categories: 
---
这是错误信息，查了很多都没有查到问题所在

{% codeblock %}
[ pid=14193 thr=71528440 file=utils.rb:176 time=2012-05-03 21:15:35.137 ]: *** Exception Errno::ENOENT in application (No such file or directory - /tmp/RackRewindableInput20120503-14193-1w1x37q.lock) (process 14193, thread #<Thread:0x0000000886dff0>):
  from /usr/local/rvm/rubies/ruby-1.9.3-p194/lib/ruby/1.9.1/tempfile.rb:346:in `rmdir'
  from /usr/local/rvm/rubies/ruby-1.9.3-p194/lib/ruby/1.9.1/tempfile.rb:346:in `rmdir'
  from /usr/local/rvm/rubies/ruby-1.9.3-p194/lib/ruby/1.9.1/tempfile.rb:338:in `ensure in locking'
  from /usr/local/rvm/rubies/ruby-1.9.3-p194/lib/ruby/1.9.1/tempfile.rb:338:in `locking'
  from /usr/local/rvm/rubies/ruby-1.9.3-p194/lib/ruby/1.9.1/tempfile.rb:144:in `block in initialize'
  from /usr/local/rvm/rubies/ruby-1.9.3-p194/lib/ruby/1.9.1/tmpdir.rb:133:in `create'
  from /usr/local/rvm/rubies/ruby-1.9.3-p194/lib/ruby/1.9.1/tempfile.rb:134:in `initialize'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/utils/rewindable_input.rb:86:in `new'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/utils/rewindable_input.rb:86:in `make_rewindable'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/utils/rewindable_input.rb:30:in `read'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-1.4.1/lib/rack/request.rb:202:in `POST'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-1.4.1/lib/rack/methodoverride.rb:26:in `method_override'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-1.4.1/lib/rack/methodoverride.rb:14:in `call'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-1.4.1/lib/rack/runtime.rb:17:in `call'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/activesupport-3.2.2/lib/active_support/cache/strategy/local_cache.rb:72:in `call'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-1.4.1/lib/rack/lock.rb:15:in `call'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-cache-1.2/lib/rack/cache/context.rb:136:in `forward'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-cache-1.2/lib/rack/cache/context.rb:143:in `pass'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-cache-1.2/lib/rack/cache/context.rb:155:in `invalidate'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-cache-1.2/lib/rack/cache/context.rb:71:in `call!'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/rack-cache-1.2/lib/rack/cache/context.rb:51:in `call'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/railties-3.2.2/lib/rails/engine.rb:479:in `call'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/railties-3.2.2/lib/rails/application.rb:220:in `call'
  from /opt/www/memebox/shared/bundle/ruby/1.9.1/gems/railties-3.2.2/lib/rails/railtie/configurable.rb:30:in `method_missing'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/rack/request_handler.rb:96:in `process_request'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_request_handler.rb:513:in `accept_and_process_next_request'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_request_handler.rb:274:in `main_loop'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/rack/application_spawner.rb:206:in `start_request_handler'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/rack/application_spawner.rb:171:in `block in handle_spawn_application'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/utils.rb:479:in `safe_fork'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/rack/application_spawner.rb:166:in `handle_spawn_application'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_server.rb:357:in `server_main_loop'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_server.rb:206:in `start_synchronously'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_server.rb:180:in `start'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/rack/application_spawner.rb:129:in `start'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/spawn_manager.rb:253:in `block (2 levels) in spawn_rack_application'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_server_collection.rb:132:in `lookup_or_add'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/spawn_manager.rb:246:in `block in spawn_rack_application'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_server_collection.rb:82:in `block in synchronize'
  from <internal:prelude>:10:in `synchronize'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_server_collection.rb:79:in `synchronize'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/spawn_manager.rb:244:in `spawn_rack_application'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/spawn_manager.rb:137:in `spawn_application'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/spawn_manager.rb:275:in `handle_spawn_application'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_server.rb:357:in `server_main_loop'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/lib/phusion_passenger/abstract_server.rb:206:in `start_synchronously'
  from /usr/local/rvm/gems/ruby-1.9.3-p194/gems/passenger-3.0.12/helper-scripts/passenger-spawn-server:99:in `<main>'
{% endcodeblock %}

运行下面命令，查看磁盘空间是否够用

{% codeblock %}
dh -h
{% endcodeblock %}

我们的服务器系统只有16G，其他都挂载了/opt,前两天转移数据放了一个大文件7个G的文件，把16G占满了，当然写不进去了。终于解决了。呜呜，吸取教训了。

