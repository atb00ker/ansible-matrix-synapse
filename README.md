#### This code will install matrix-synapse on your server & get an certificates from `letsencrypt.org` for your domain, and set a cron job to renew the certificates.

**Be mindful you need to set the variables before running the script; the variables are to be set in the `defaults/main.yml` file**
## Must Change
| Variable  | Valid Values | Example | Note |
| ------------- | ------------- | ------------- | ------------- |
| hostname | string | hostname: www.MY_AWESOME_WEBSITE.com | The domain of server where you plan to set homeserver |
| email | string | email: YOUR_AWESOME@EMAIL.ID | Email is required if you plan to use letsencrypt for https (secure) connection |
## Advanced Changes
| Variable  | Valid Values | Example | Note |
| ------------- | ------------- | ------------- | ------------- |
| enableRegistration |  true/false | enableRegistration: true | Set to `true` if you plan to allow users to register themselves using riot.im like clients, Set `false` otherwise |
| reportStats  | true/false | reportStats: false | Send anonymous stats report to help improve matrix code, for more information visit: `matrix.org` |
| matrixConfFileToSend | PATH/TO/NGINX_CONF_FILE | matrixConfFileToSend: files/nginx.conf  | This is the nginx configuration file that would be send to the server |
| synapseCacheFactor |  NUMBER | synapseCacheFactor: 0.2 | Amount of RAM matrix-synapse is allowed to use, Read more at https://github.com/matrix-org/synapse#help-synapse-eats-all-my-ram |
| portForRiot |  NUMBER [Valid port number] | portForRiot: 443 | You'll use this port on your domain for your homeserver |

**How to run:**
  1. Install Ansible
  2. Add your server group in the inventory.
  3. Change the `hosts` from `all` to the server group in which you want to install matrix-synapse. (In file ansible-matrix-synapse/main.yaml) [optional; as per your Requirements]
  4. Change the `remote_user` from `root` to a user which is a sudoer. (In file `ansible-matrix-synapse/main.yaml`) [optional; as per your Requirements]
  5. Make sure you have set the variables you desire for installation. (In file `ansible-matrix-synapse/defaults/main.yml`)
  6. Run the following command (from inside the ansible-matrix-synapse folder): `ansible-playbook main.yaml --ask-become`

**Tested:**  
- Ubuntu Xenial (16.04)

**Minimum Requirements:**
- ansible >=2.0  

**References:**
- Ansible: https://www.ansible.com
- Matrix: https://matrix.org/
- letsencrypt: https://letsencrypt.org/

**Feel free to contribute in this Repository or open an issue.**
