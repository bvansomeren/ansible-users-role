bvansomeren.users
=========

This role sets up users for Linux / FreeBSD systems. While Ansible has support for doing this we include some of the extra steps like:
  * setup public keys
  * forward emails
  * restore files based on backup folder / tar
  * setup ZFS dataset
  * setup quota

Ideas are welcome
Definitely still a work in progress

Requirements
------------

Role needs to run as privileged user that can setup accounts and chown files

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      become: yes
      become_user: root
      roles:
      - bvansomeren.users
      vars:
        users_role_groups:
        - name: test
        - name: test2
          gid: 10002
        users_role_users:
        - name: test
          comment: "test user"
          group: "test"
          archive_file: "files/test.tar.gz"
        - name: test2
          group: "test2"
          copy_folder: "files/test2/"
   
License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
