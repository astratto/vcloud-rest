# Changes

### 2019-09-09 (1.5.0)

* Added an optional parameter to the Connection#initliaze for the SSL:
    *  {ssl_ciphers: 'ciphers_list'} in order to connect to servers with old versions of SSL 


### 2015-06-28 (1.4.0)

Note that I don't have enough time anymore to actively maintain this gem and I'm
looking for a co-maintainer.

**Fixes**

* Fix add network with manually specified IP
* Fix css selector in get_vapp
* Fix nil when deleting vapp

**Features**

* Add extensibility capabilities
* Handle *nat_type* in `compose_vapp_from_vm`

### 2014-06-03 (1.3.0)

Note that starting from this release Ruby 1.8.7+ and 1.9.2 are not explicitly tested against anymore.

**Features**

* Add "media" item type management to `get_catalog_item`
* Add `discard_suspend_state_[vapp|vm]` to discard suspended state of a vApp or VM
* Add independent disk capabilities
* `get_vapp` returns also network IDs
* Add `discard_[vm|vapp]_snapshot` to discard snapshots
* Add `acquire_ticket_vm` that retrieves a screen ticket (VMRC) for a given VM

**Fixes**

* Fix add network to VM for API v.5.5
* Fix VM IP address retrieval with different interfaces on same network
* Don't use hardcoded rasd:Parent in `add_disk`

Note that now `get_vm` appends NetworkConnectionIndex to network name to generate a unique hash key.

### 2014-02-06 (1.2.0)

**Features**

* vm
    * actions to control vm snapshots just as vApp snapshots
        * create_vm_snapshot
        * revert_vm_snapshot
    * network add/edit handle PrimaryNetworkConnectionIndex

**Deprecations**

* `create_snapshot` is deprecated in favour of create_vapp_snapshot
* `revert_snapshot` is deprecated in favour of revert_vapp_snapshot
* remove `set_vm_network_config` deprecated in 1.1.0

**Fixes**

* OVF: fix upload link retrieval (issue #23)
* Remove network placeholder when adding a network to a VM

### 2013-12-31 (1.1.1)

**Fixes**

* Unify IP address retrieval (issue #20)

### 2013-12-13 (1.1.0)

**Features**

* Add commands `[add|edit|delete]_vm_network` to manage multiple networks

**Deprecations**

* `set_vm_network_config` is now deprecated

### 2013-11-29 (1.0.0)

This is the first release that leaves beta status.
It's actively used in production by at least one company and thus it's important
to offer a more stable interface.

**Features**

* General
    * Add proper logging
        (set env vars *VCLOUD_REST_DEBUG_LEVEL* and *VCLOUD_REST_LOG_FILE*)
    * Various entities can be searched by name
* vApp
    * Add methods to create/revert snapshots
    * Add method to clone a vApp
    * Add support to force vApp's Guest Customization
    * get_vapp: retrieve network information
    * get_vapp: retrieve vApp snapshot info
    * Add method to remove a network from a vApp
    * Add method to add an external (from vDC) network to a vApp
    * retrieve vApp's RetainNetInfoAcrossDeployments setting
* VM
    * Add external ip address to ```get_vm```
    * Add method to retrieve VM info (cpu & RAM)
    * Add method to set VM's CPUs info
    * Add method to set VM's RAM info
    * Add method to retrieve VM's disks info
    * Add method to manage VM's disks (add, delete, resize)
    * Add support to upload a customization script
    * Add support to force VM's Guest Customization
    * Add support to manage VM's status (start/stop...)
    * retrieve VM's status in get_vm
    * Add method to rename VMs
* OVF
    * Add a :send_manifest option to ```upload_ovf```
* Network
    * Add method to show network details
* Tasks
    * Add methods to list/cancel Tasks

**Changes**

* vApp clone returns an hash to provide also the new vApp's ID
* retrieve VM's name directly instead of using the GuestCustomization section
* Do not track Gemfile.lock anymore
* Relax nokogiri version to >= 1.5.10
* set_vapp_network_config requires different parameters

**Fixes**

* Reset auth token when a session is destroyed
* Fix wait_task_completion
* Uniform output for get_catalog_item and get_catalog_item_by_name
* ParentNetwork is optional
* Fix ID retrievals using regexps
* set_vapp_network_config to ensure existing configs are not lost
* Better error handling for upload OVF

### 2013-07-25 (0.3.0)

**Features**

* Add ```compose_vapp_from_vm``` to compose a vapp using VMs in a catalog
* Add ```get_vapp_template``` to get information on VMs inside a vapp template
* Add ```set_vapp_port_forwarding_rules``` to set NAT port forwarding rules in an existing vapp
* ```set_vapp_network_config```: add parent network specification
* ```get_vapp```: ```vms_hash``` now contains also ```vapp_scoped_local_id```
* Add ```get_vapp_edge_public_ip``` to fetch the public IP of a vApp (vShield Edge)
* Add ```get_vapp_port_forwarding_rules``` to return vApp portforwarding rules
* Add ``reboot_vapp/suspend_vapp/reset_vapp``
* Add ```upload_ovf``` to upload an OVF Package

**Changes**

* ```RetainNetInfoAcrossDeployments``` now defaults to false (fenced deployments)

**Fixes**

* Better handling of 500 errors

*Remarks:* A big thanks to Fabio Rapposelli and Timo Sugliani for the great work done!

### 2013-05-13 (0.2.2)

**Fixes**

* Fix retrieving of 'ipAddress' attribute of VMs inside VAPP

**Various**

* Add license field to gemspec
* Bump nokogiri dependency to 1.5.9

### 2012-12-27 (0.2.1)

**Fixes**

* Fix VM's admin password retrieval

### 2012-12-21 (0.2.0)

**Features**

* Allow Task tracking for vApp startup & shutdown
* Improve error message for operations on vApp not running
* Improve error message for access forbidden
* Extend vApp status codes handling
* Add method to show VM's details
* Basic vApp network configuration
* Basic VM network configuration
* Basic Guest Customization configuration

**Fixes**

* Show catalog item: fix ID parsing

### 2012-12-19 (0.1.1)

**Fixes**

* Fix gemspec URL

### 2012-12-19 (0.1.0)

**Features**

* Add support for main operations:
 * login/logout
 * organization _list/show_
 * vdc _show_
 * catalog _show_
 * catalog item _show_
 * vapp _create/delete/startup/shutdown_

### 2012-12-14 (0.0.1)

* Initial release
