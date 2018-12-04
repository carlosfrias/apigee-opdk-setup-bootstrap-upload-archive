# Apigee OPDK Mirror Archive Uploader

This role will upload an Apigee Mirror to be used to install Apigee in an offline environments.

Requirements
------------

The Apigee Bootstrap must be installed so that the Apigee Service component is available prior to 
running this role. The  Apigee Mirror exists and has been packaged into a downloadable archive.

Role Variables
--------------

These are the variables that can be updated for this role:

| Name | Description |
| --- | --- |
| opdk_version | The version of OPDK to use. Default: 4.18.05 |


Dependencies
------------

Dependencies with the Ansible Galaxy requirements file. Role dependencies are:

* apigee-opdk-default-settings
* apigee-opdk-modules 
* apigee-opdk-setup-bootstrap-upload-archive

Example Playbook
----------------

    - name: Upload apigee mirror archive
      hosts: "{{ target_hosts }}"
      tags: ['upload']
      vars:
        ansible_workspace: "~/.ansible"
        apigee_workspace: "~/apigee-workspace"
        ansible_workspace: "~/.ansible"
        apigee_workspace: "~/apigee-workspace"
        opdk_version: 4.18.05
        apigeereleasever: 4.18.05
        property_folders:
        - "~/.apigee-secure"
      roles:
      - { role: apigee-opdk-setup-default-settings, tags: ['cache'] }
      - { role: apigee-opdk-modules }
      - { role: apigee-opdk-setup-bootstrap-upload-archive, tags: ['upload'] }


License
-------

Apache 2.0

Author Information
------------------

Carlos Frias


<!-- BEGIN Google Required Disclaimer -->

# Not Google Product Clause

This is not an officially supported Google product.
<!-- END Google Required Disclaimer -->
<!-- BEGIN Google How To Contribute -->
# How to Contribute

We'd love to accept your patches and contributions to this project. Please review our [guidelines](CONTRIBUTING.md).
<!-- END Google How To Contribute -->
