## Ansible Wordpress Nginx

Ansible Playbook for automating wordpress website setup in NGINX server.

**Server Stack**

- Nginx
- Php-fpm
- Mysql
- WP-Cli

#### Step 1: Update Playbook Hosts

Change the IP Address with your custom IP address or localhost

```
[webhost]
142.93.214.145 ansible_python_interpreter=/usr/bin/python3
```

#### Step 2: Update Playbook Variables

Update variables with custom data from **./group_vars/all.yml**

```yaml
# ansible setup
ansible_ssh_pub_key: "{{ lookup('file', '~/.ssh/id_rsa.pub') }}"
ansible_ssh_private_key_file: ~/.ssh/id_rsa

# sudo user
ssh_user: ansible
ssh_groups: "sudo"

# Wordpress Database setup
host_name: "142.93.214.145"
wp_db_name: wordpress1
wp_db_user: wordpress
wp_db_password: w0rdpr355
wp_db_prefix: wp_

# Wp website setup
wp_title: Demo Beta Website
wp_admin_user: admin
wp_admin_password: admin450
wp_admin_email: admin@example.com
```

#### Step 3: Run the playbook

```bash
ansible-playbook play.yml
```

#### Tested Linux Distribution

- Ubuntu 18.04 x64
- Ubuntu 16.04 x64
