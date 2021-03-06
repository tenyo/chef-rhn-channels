rhn-channels Cookbook
=================

This cookbook contains a LWRP to manage RHN channel subscriptions.  This cookbook does not manage RHN node registration, for which you should use https://github.com/bflad/chef-rhn

Github repo: https://github.com/andrewfraley/chef-rhn-channels


Usage
-----
#### LWRP
Add depends "rhn-channels" to your metadata.rb, then use the rhn_channel resource to add a channel to your system.  Also see the included optional_repo.rb recipe for another example.

```ruby
rhn_channel "rhel-x86_64-server-optional-6" do
 	channel_name "rhel-x86_64-server-optional-6"
 	username "RHNUSERNAME"
 	password "RHNPASSWORD"
  action :add
 end
```
Alternatively, you can set **node['rhn-channels']['rhn_user']** and **node['rhn-channels']['rhn_pass']** and simply do:
```ruby
rhn_channel "rhel-x86_64-server-optional-6"
```
To remove a channel:
```ruby
rhn_channel "rhel-x86_64-server-optional-6" do
  action :remove
end
```
Note that you do not need to set your username and password for RHEL 7

TODO
----
* Provide a list of available RHEL channels

License and Authors
-------------------
* License: MIT
* Author: https://github.com/andrewfraley
* Author: Tenyo Grozev (tenyo.grozev@yale.edu)
