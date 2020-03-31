# ansible-role-firewall
firewall management via nftables

The role installs the nftables package and added permissive rules such as:
ip saddr X.X.X.X/X tcp dport XXXX ct state established,new counter accept

Variables are set in inventory file (hosts.yaml) in the dst_ports and src_hosts lists

port can be a number or range (for example: 443 or 8300-8335)
ip can be just address or address/mask (for example: 10.10.1.1 or 172.16.23.0/24)

play role:
ansible-playbook -i hosts.yaml playbooks/firewall.yml -DbkK

NOTE: add the address of your ansible deploy node in allowed before you get started https://github.com/timureh/ansible-role-firewall/blob/3ab6e939f58c011425aa96240fde28028389e084/roles/common/templates/nftables.j2#L20
