Windows Kerberos Setup
======================

Example settings for using kerberos to connect using an Active Directory user:

In ``group_vars/windows.yml``, define the following inventory variables::

    # it is suggested that these be encrypted with ansible-vault:
    # ansible-vault edit group_vars/windows.yml

    ansible_user: domainuser@name_of_your_domain
    ansible_password: SecretPasswordGoesHere
    ansible_port: 5986
    ansible_connection: winrm
    # The following is necessary for Python 2.7.9+ (or any older Python that has backported SSLContext, eg, Python 2.7.5 on RHEL7) when using default WinRM self-signed certificates:
    ansible_winrm_server_cert_validation: ignore


See :doc:`win_connection_options` for other connection options.
