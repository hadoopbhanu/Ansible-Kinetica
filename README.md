# Ansible Collection - hadoopbhanu.kinetica_cluster
Contributed to Ansible_Galaxy Collection: https://galaxy.ansible.com/ui/repo/published/hadoopbhanu/kinetica_cluster
![image](https://github.com/user-attachments/assets/87868e89-31d9-425a-a421-983182473165)


# Kinetica Cluster Management Role

This Ansible role manages Kinetica cluster worker nodes by ensuring configuration file consistency, checking for version drift in dependencies (Java, Python, Kinetica), and verifying that necessary dependencies (CUDA and NVIDIA drivers) are installed.

## Features

- **Configuration Management**: Synchronizes configuration files across nodes.
- **Version Drift Detection**: Checks for and reports version drift in dependencies.
- **Dependency Verification**: Installs and verifies required packages like NVIDIA drivers and CUDA.

## Requirements

- Ansible 2.9 or higher
- Supported OS:
  - Ubuntu
  - Red Hat-based systems

## Role Variables

- `kinetica_config_path`: Path to the Kinetica configuration file.
- `expected_java_version`: Expected Java version.
- `expected_python_version`: Expected Python version.
- `expected_kinetica_version`: Expected Kinetica version.

## Example Playbook

```yaml
- hosts: agents
  roles:
    - role: your_namespace.kinetica_cluster.kinetica_cluster
      vars:
        expected_java_version: "11"
        expected_python_version: "3.12.3"
        expected_kinetica_version: "7.1"
