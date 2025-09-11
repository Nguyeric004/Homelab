9/10/25
    - Attached all VMs to a host-only adapter and NAT adapter
    - Configured Ubuntu VM to be victim server
        - Install DVWA
            sudo systemctl start apache2
            sudo systemctl status apache2
            http://192.168.56.101/dvwa/
            Username: admin
            Password: password
        - Configure DVWA DB with MySQL credentials
            sudo systemctl start mysql
            sudo systemctl status mysql
        - Install Wazuh Manager
            sudo systemctl start wazuh-agent
            sudo systemctl status wazuh-agent     

