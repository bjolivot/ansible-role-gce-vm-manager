gce_vm_manager
===============

This role is used to deploy VM on Google Cloud


Role Variables
--------------

Mandatory vars :

gce_vm_list:                
  vm1:    #vm name
    group: "db"    #for dynamic inventory group
    hdd: 50        # hdd boot size
    type: "n1-standard-2"   # VM type 
    image: "ubuntu-1404-trusty-v20160516"   #Boot image
    tags: "www,public,linux"
  vm2: 
    group: "www"
    hdd: 10
    type: "f1-micro"
    image: "ubuntu-1404-trusty-v20160516"
    tags: "vm,bdd"

gce_service_account_email: # gce service account email 
gce_pem_file:  #pem filename associated with service account, need to be saved at playbook root dir
gce_project_id: #project ID, found in google cloud console
gce_region: # where to deploy (ex: europe-west1)
gce_zone:  #VM zone (ex: "europe-west1-d")


How to use 
----------

You need to :
 - define mandatory vars
 - put pem file at playbook's root directory
 - start on localhost : 




- name: Create VM
  become: true
  hosts: localhost
  roles: 
    - gce_vm_manager


License
-------

Licensed under the MIT License. See the [LICENSE](LICENSE) file for details.


Author Information
------------------

See my other "work on my computer" ansible things on https://www.github.com/bjolivot