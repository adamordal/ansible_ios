
# Ansible IOS

This repository provides Ansible playbooks and roles designed to automate the configuration and management of Cisco IOS-based network devices. It leverages Ansible's capabilities to streamline network operations, ensuring consistency and efficiency across device configurations.

## Features

- **Automated Configuration**: Deploy and manage configurations on Cisco IOS devices using Ansible playbooks.
- **Modular Roles**: Utilize the `cisco_switch` role for organized and reusable configuration tasks.
- **Inventory Management**: Define and manage device groups and variables through structured inventory files.
- **Customizable Variables**: Override default settings using group variables for flexible deployments.

## Repository Structure


```bash
ansible_ios/
├── ansible.cfg           # Ansible configuration file
├── inventory/            # Inventory directory containing host definitions
│   └── hosts             # Inventory file listing managed devices
├── group_vars/           # Directory for group variable files
│   └── all.yml           # Variables applicable to all hosts
├── playbooks/            # Directory containing Ansible playbooks
│   └── switch_apply.yml  # Playbook to apply configurations to switches
├── roles/                # Directory for Ansible roles
│   └── cisco_switch/     # Role for configuring Cisco switches
│       ├── tasks/        # Task definitions
│       │   └── main.yml  # Main task file
│       └── templates/    # Jinja2 templates for configurations
└── README.md             # Project documentation
```

## Getting Started

### Prerequisites

- Ansible installed on your control node.
- Access credentials for the target Cisco IOS devices.
- Python packages: `paramiko`, `netmiko`, or other relevant networking libraries if required.

### Setup

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/adamordal/ansible_ios.git
   cd ansible_ios
   ```

2. **Configure Inventory**:

   Edit the `inventory/hosts` file to include your Cisco IOS devices. Group them as needed.

3. **Define Variables**:

   Update `group_vars/all.yml` with variables applicable to all devices or create group-specific variable files as needed.

4. **Review and Customize Roles**:

   Inspect the `roles/cisco_switch/` directory to understand and modify the tasks and templates according to your network requirements.

### Execution

Run the playbook to apply configurations:


```bash
ansible-playbook -i inventory/hosts playbooks/switch_apply.yml
```


Ensure that the `ansible.cfg` file is correctly configured to suit your environment, specifying parameters like `inventory`, `remote_user`, and connection settings.

## Customization

- **Templates**: Modify Jinja2 templates in `roles/cisco_switch/templates/` to match your desired configurations.
- **Tasks**: Adjust tasks in `roles/cisco_switch/tasks/main.yml` to include additional configuration steps or logic.
- **Variables**: Define host or group-specific variables to tailor configurations per device or group.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your enhancements or bug fixes.

## License

This project is open-source and available under the [MIT License](https://github.com/rvm/rvm1-ansible/blob/master/LICENSE).

---

For more information and best practices on using Ansible for network automation, refer to the [Ansible Network Automation Guide](https://docs.ansible.com/ansible/latest/network/index.html).

--- 