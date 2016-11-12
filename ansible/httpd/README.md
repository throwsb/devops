# Ansible basic httpd playbook

This is a simple ansible playbook to manage a singe virtual website for ports 80 abd 443.  The webserver is apache pulled from centos repo.  The OS is centos 7.2.  If I were to create a playbook to manage multiple virtual sites, I would create templates using Jinja2, varibles with in the playbooks, and perhaps roles. 

### The playbook completes the following.

* Install the latest version of httpd.
* Install mod_ssl package.
* Start the httpd service enable the service to start on server boot.
* The following files are pushed to the webserver.  If there is a change to any of the files while running the playbook, httpd servers will restart.

```
    httpd.conf
    ssl.conf
    index.html
    example.key
    example.crt
```

* Install the latest version of firewalld.
* Start the firewalld package and enable the service to start at server boot.
* The following ports are opened.  If there is a change to the ports while pushing the playbook, the firewalld service will restart.

Service|Port
-------|----
ssh | 22
http | 80
https | 443
