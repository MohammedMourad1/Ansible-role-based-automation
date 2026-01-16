# Server Baseline Role

## Role Purpose

This role provides a **standardized Linux server baseline** by automating common system configuration tasks using Ansible.

It is intended to be used as a reusable foundation for newly provisioned servers, ensuring consistency, security, and reduced manual setup.

The role is designed to be simple, extensible, and suitable for real-world environments.

---

## What This Role Does

This role performs essential baseline operations commonly required on Linux servers, including:

- Applying basic system configuration
- Installing commonly required utility packages
- Ensuring required services are enabled and running
- Restarting or reloading services when configuration changes occur using handlers
- Enforcing consistent configuration through variable-driven design

---

## Supported Platforms

This role is designed for Linux systems and has been tested on:

- Ubuntu
- Debian-based distributions

Other Linux distributions may work but are not officially tested.

---

## Role Structure

The role follows Ansible best practices and is structured as follows:

- `tasks`  
  Contains the main execution logic of the role

- `handlers`  
  Contains reactive tasks triggered only when changes occur

- `defaults`  
  Contains safe default values intended for customization

- `vars`  
  Contains internal variables used by the role logic

- `meta`  
  Defines role metadata and dependencies

- `tests`  
  Provides simple test playbooks for validation

---

## Variables

### Default Variables

The following variables can be safely overridden:

| Variable Name      | Default Value   | Description                    |
|--------------------|-----------------|--------------------------------|
| example_variable   | default_value   | Example configurable variable  |

All configurable values are defined in `defaults` to allow customization without modifying role logic.

---

### Vars Variables

Variables defined in `vars` are intended for internal use and should not be overridden unless the role logic is fully understood.

---

## Handlers

Handlers are used to perform reactive operations such as:

- Restarting services
- Reloading service configurations

They are executed only when notified by a task, ensuring efficient and idempotent execution.

---

## Example Usage

This role can be included in a playbook as follows:

- Define an inventory file
- Include the role in your playbook
- Override variables if required
- Run the playbook using Ansible

Example workflow:

- `ansible-playbook site.yml -i inventory`

---

## Testing

Basic testing files are provided under the `tests` directory to validate role behavior in an isolated environment.

---

## Future Improvements

Planned enhancements may include:

- Support for additional Linux distributions
- Extended system hardening options
- Additional configurable components

---

## Author

Maintained by Mohammed Ahmed Mourad.

---

## License

MIT
