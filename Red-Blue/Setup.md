9/10/25
    - Attached all VMs to a host-only adapter and NAT adapter
    - Configured Ubuntu VM to be victim server and wazuh manager
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
                Manager IP: 192.168.56.101

9/11/25
    - Configured Wazuh agent profile on Ubuntu VM
        - sudo /var/ossec/bin/manage_agents
            - agent name: W10VM
            - agent ip: any
            - agent key: MDAxIFcxMFZNIGFueSAwNmu0OTgzMzRhNzM2ZjA3NGNlMWFlMWY0YTJkY2FhMmY1Mjc0ODc1NWUxYWYxNjFkODNkYmYwM2RmYTNj
        - sudo /var/ossec/bin/agent_control -l
            Check agent status
    - Configured Windows 10 VM to be victim server
        - Installed Wazuh agent
        - Application is called Manage Agent
        - Connected Wazuh Agent on Windows VM to Wazuh Manager on Ubuntu VM

9/14/25
    - Configured Kali VM to be attack box
        - Setup static IP for Kali VM
            - sudo nmcli connection modify "Wired connection 1" ipv4.method manual ipv4.addresses 192.168.56.110/24 ipv4.gateway 192.168.56.1
            - sudo nmcli connection up "Wired connection 1"
        - Updated Kali VM
            -s udo apt update && sudo apt full-upgrade -y
        - Installed tools
            - sudo apt install nmap nikto sqlmap hydra gobuster wfuzz proxychains4 dirbuster -y     
           

