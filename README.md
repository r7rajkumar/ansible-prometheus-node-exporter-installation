# Prometheus Node Exporter Installation

This Ansible playbook installs Prometheus Node Exporter on multiple Ubuntu Virtual Machines.

## Prerequisites

- Ansible installed on the control machine.
- SSH access to the target virtual machines.
- Ubuntu Virtual Machines with appropriate credentials (username/password) set.

## Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/r7rajkumar/ansible-prometheus-node-exporter-installation.git

   Navigate to your repo directory

2. Update the inventory.ini file:

Open the inventory.ini file and replace the placeholders with the IP addresses or hostnames of your target virtual machines. Also, update the ansible_user and ansible_ssh_pass values with the appropriate credentials.

3. Customize the playbook (optional):

If you want to use a specific version of Node Exporter, update the node_exporter_version variable in the playbook.yml file.
Modify any other settings or tasks in the playbook according to your requirements.
4. Execute the playbook:

Run the following command to execute the playbook and install Prometheus Node Exporter on the virtual machines:

ansible-playbook -i inventory.ini playbook.yml

The playbook will connect to the target virtual machines, install the required packages, download and extract Node Exporter, configure the service, and start it.

5. Verify installation:

Access the virtual machines and verify that Node Exporter is running by accessing the Node Exporter metrics endpoint. Open a web browser and enter the following URL, replacing vm-ip with the IP address or hostname of each virtual machine:

http://ipaddress:9100/metrics

you should see the Node Exporter metrics in the browser if the installation was successful.

Notes
In my case, I deployed this module on an Amazon EC2 instance using a PEM file for SSH authentication. However, in your case, since you are using a username and password for authentication, the steps or commands may vary slightly.
Make sure you have the necessary permissions and access rights to the target virtual machines.