lets-chat
=========

Install lets-chat developed by side-project at Security Compass (https://github.com/sdelements/lets-chat).


Remarks
------------

With this role, you can access via ``http://<ip address>:5000`` at default.

This installation script aims at a single-VM structure for the sake of simplicity. Let's Chat requires ``MongoDB`` and ``Node.js`` and therefore I implements those installation scripts * without additional configurations*. I may modify this scripts with other role dependencies.

Requirements
------------

* OS: CentOS

I've checked on CentOS 6.5. I haven't implement code for lamp or kerberos authentification.


Role Variables
--------------
I recommend to change variable ``lc_user_group`` and  ``lc_user``. Default value is ``vagrant``.


It's recommended to change variable ``lc_cookie_secrets_salt`` and ``lc_auth_secrets_salt`` because default setting is likely insecure.

You can change defaluts variavie as follows:

* lc_repos
  * dir
  * config
  * app
* temp_lc_location:


* lc_http_enable
* lc_http_host
* lc_http_port
* lc_https_enable
* lc_https_port
* lc_files_enable
  * Now there is only local upload. The implementation for ``S3``/``Azure`` authentifications is not finished.
* lc_files_maxFile
* lc_files_restrictTypes
* lc_auth_providers
  * Now there is only local authentification. The implementation for Kerberos/LDAP authentifications is not finished.
* lc_local_self_registration
* lc_auth_throttling_enable
* lc_auth_throttling_threshold


* lc_cookie_secrets_salt
  * default: secretsauce
* lc_auth_secrets_salt
  * default: secretsauce


Dependencies
------------

None, but I may add other roles such as ``MongoDB``.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: lets-chat
      roles:
         - { role: ken24.let-chat, sudo: yes }

License
-------

MIT

Author Information
------------------

Kenta Nishimura, data-science infrastructure engineers at a telecommunications company.
