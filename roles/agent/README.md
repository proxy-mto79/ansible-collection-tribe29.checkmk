# tribe29.checkmk.agent

<!-- A brief description of the role goes here. -->
This role installs Checkmk agents.

## Requirements

<!-- Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required. -->
None.

## Role Variables

<!-- A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well. -->

    checkmk_agent_version: "2.1.0p1"

The Checkmk version of your site.

    checkmk_agent_edition: cre

The edition you are using. Valid values are `cre` and `cee`.
Note, that `cee` is not implemented yet.

    checkmk_agent_protocol: http

The protocol used to connect to your Checkmk site.

    checkmk_agent_server: localhost

The FQDN or IP address of your Checkmk server.

    checkmk_agent_site: my_site

The name of your Checkmk site.

    checkmk_agent_user: automation

The user used to authenticate against your Checkmk site.

    checkmk_agent_pass: SECRET

The password for the user used to authenticate against your Checkmk site.

    checkmk_agent_add_host: 'false'

Automatically add the host where the agent was installed to Checkmk.

    checkmk_agent_discover: 'false'

Automatically discover services on the host where the agent was installed.

    checkmk_agent_update: 'false'

Register host for automatic updates. Make sure to have the server side prepared
for automatic updates. Otherwise this will fail.

    checkmk_agent_tls: 'false'

Register for TLS encryption. Make sure to have the server side prepared
for automatic updates. Otherwise this will fail.

    checkmk_agent_configure_firewall: 'true'

Automatically configure the firewall to allow access to the Checkmk agent.

    checkmk_agent_prep_legacy: 'false'

Enable this to automatically install `xinetd` on hosts with systemd prior to version 220.

    checkmk_agent_delegate_api_calls: localhost

Configure the host to which Checkmk API calls are delegated to.

    checkmk_agent_host_name: "{{ inventory_hostname }}"

Define the hostname which will be used to add the host to Checkmk.

    checkmk_agent_host_ip: "{{ hostvars[inventory_hostname]['ansible_default_ipv4']['address'] }}"

Define an IP address which will be added to the host in Checkmk. This is optional, as long as the hostname is DNS-resolvable.

## Dependencies

<!-- A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles. -->
None.

## Example Playbook

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - tribe29.checkmk.agent

## Contributing

See [CONTRIBUTING](../../CONTRIBUTING).

## Disclaimer

This role is provided AS IS and we can and will not guarantee that the role works
as intended, nor can we be accountable for any damage or misconfiguration done
by this role. Study the role thoroughly before using it.

## License

See [LICENSE](../../LICENSE).

## Author Information

<!-- An optional section for the role authors to include contact information, or a website (HTML is not allowed). -->
Robin Gierse (@robin-tribe29)
