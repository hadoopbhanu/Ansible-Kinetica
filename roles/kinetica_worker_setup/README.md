# Kinetica Role

This role manages Kinetica cluster worker nodes, ensuring configuration consistency, dependency installation, and version checking.

## Requirements

- Ansible 2.9 or higher
- Supported OS:
  - Ubuntu
  - Red Hat-based systems

## Role Variables

- `kinetica_config_path`: Path to the Kinetica configuration file (default: `/opt/gpudb/core/etc/gpudb.conf`)
- `expected_java_version`: Expected Java version (default: `11`)
- `expected_python_version`: Expected Python version (default: `3.8`)
- `expected_kinetica_version`: Expected Kinetica version (default: `7.1`)

## Dependencies

This role installs and verifies required packages like NVIDIA drivers and CUDA.

## Example Playbook

```yaml
- hosts: agents
  roles:
    - role: hadoopbhanu.kinetica_cluster.kinetica_role
      vars:
        expected_java_version: "11"
        expected_python_version: "3.12.3"
        expected_kinetica_version: "7.1"
