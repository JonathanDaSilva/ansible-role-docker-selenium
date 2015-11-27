Ansible Role: docker-selenium
=========

An Ansible Role that runs selenium docker images built by [SeleniumHQ](https://github.com/SeleniumHQ/docker-selenium).

Requirements
------------

None.

Role Variables
--------------

- __docker_selenium_version__: the selenium release version, default is 2.45.0. See the SeleniumHQ link above for more recent releases.
- __docker_selenium_hub_name__: logical name for the hub, default is selenium-hub.
- __docker_selenium_hub_port__: the hub port mapping between host and container, default 4444:4444.
- __docker_selenium_hub_image__: selenium hub image name in DockerHub.
- __docker_selenium_firefox_image__: selenium node image for firefox in DockerHub.
- __docker_selenium_chrome_image__: selenium node image for chrome in DockerHub.
- __docker_selenium_hub_link__: the hub link for nodes to link with.
- __docker_selenium_firefox_nodes__: the number of firefox container nodes to run.
- __docker_selenium_chrome_nodes__: the number of chrome container nodes to run.
- __docker_selenium_pull_image__: check docker registry for image, default is to pull if missing.
- __docker_selenium_state__: default is to reload for any changes made to the container configuration.

Dependencies
------------

None.

Example Playbook
----------------

Run a specific version of selenium specifying the number of nodes and using debug containers:

    - hosts: servers
      roles:
         - { role: ansible-role-docker-selenium, docker_selenium_version: 2.46.0, 
                   docker_selenium_chrome_nodes: 5, docker_selenium_firefox_image: "selenium/node-firefox-debug",
                   docker_selenium_firefox_nodes: 5,  docker_selenium_chrome_image: "selenium/node-chrome-debug"  }

License
-------

GPLv2

Author Information
------------------

John Parsons

Feedback, bug-reports, requests, ...
------------------
Are [welcome](https://github.com/jpparsons/ansible-role-docker-selenium/issues)!
