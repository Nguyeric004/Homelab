9/10/25
    - Attached all VMs to a host-only adapter and NAT adapter
    - Configured Ubuntu VM to be victim server
        - Install DVWA
            - Startup
                sudo systemctl start apache2
                sudo systemctl status apache2
            - Web interface
                http://192.168.56.101/dvwa/
                Username: admin
                Password: password
            - Config location
                /var/www/html/dvwa/config/conifig.inc.php.dist
                'nano' for editing file
        - Configure DVWA DB with MySQL credentials
            - Startup
                sudo systemctl start mysql
                sudo systemctl status mysql
            - acess mysql commands
                sudo mysql -u root -p
        - Install Wazuh Manager
            - Startup            
                sudo systemctl start wazuh-manager
                sudo systemctl status wazuh-manager
                

