This code will install matrix-synapse on your server & get an certificates from `letsencrypt.org` for your domain, and set a cron job to renew the certificates.

**Tested:**  
 - Ubuntu Xenial (16.04)

**Minimum Requirements:**
 - Ubuntu >= 16.04
 - Vagrant >= 1.7.0 (If your staging server is vagrant, if not, this is not applicable)
 - ansible >=2.0

**Be mindful you need to set the variables before running the script; the variables are to be set in the defaults/main.yml file**
 - Send anonymus stats report to help improve matrix code, VISIT: matrix.org
     - reportStats: true/false
 - The domain of server where you plan to set homeserver. (Eg: www.MY_AWESOME_WEBSITE.com)
     - hostname: vagrant.box
 - Email is required if you plan to use letsencrypt for https (secure) connection.
     - email: YOUR_AWESOME@EMAIL.ID
 - This is the matrix.conf file that would be send to the server
     - matrixConfFileToSend: PATH/TO/MATRIX_CONF_FILE
 - Amount of RAM matrix-synapse is allowed to use, Read more at https://github.com/matrix-org/synapse#help-synapse-eats-all-my-ram
     - SynapseCacheFactor: INTEGER
 - Set to `true` if you plan to allow users to register themselves using riot.im like clients, Set `false` otherwise.
     - enableRegistration: true/false

**How to run:**
  1. Install Ansible
  2. Add your server group in the inventory.
  3. Change the `hosts` from `all` to the server group in which you want to install jitsi. (In file ansible-matrix-synapse/main.yaml) [optional; as per your Requirements]
  4. Make sure you have set the variables you desire for installation. (In file ansible-matrix-synapse/defaults/main.yaml)
  5. Run the following command (from inside the ansible-matrix-synapse folder): `ansible-playbook main.yaml --ask-become`

- Ansible: https://www.ansible.com
- Matrix: https://matrix.org/
- letsencrypt: https://letsencrypt.org/

**Feel free to contribute in this Repository or open an issue.**
