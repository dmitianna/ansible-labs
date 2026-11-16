 ansible all -i hosts.txt -m setup -a 'filter=ansible_all_ipv4_addresses,ansible_board_name,ansible_board_vendor,ansible_fqdn,ansible_os_family,ansible_uptime_seconds,ansible_user_id' > facts_hosts.txt<b>

Не создавая playbook, используя только ansible и модуль setup, из командной строки получите информацию представленную ниже, по основной машине, на которой установлен ansible (localhost) и с удаленных тестовых машин.
