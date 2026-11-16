# Контроль безопасности Linux-узлов с помощью Ansible

Курсовой проект по автоматизации проверки и исправления выбранных настроек безопасности Linux.

## Проверки

- `first_playbook` — параметры `UMASK` и `DIR_MODE`;
- `second_playbook` — права доступа к системным журналам;
- `third_playbook` — служба `auditd` и правила аудита;
- `fourth_playbook` — параметры защиты ядра (`sysctl`).

В `playbooks/` находятся проверяющие (`check_*.yml`) и исправляющие (`fix_*.yml`) сценарии. В `reports/` сохранены результаты их выполнения.

## Запуск

Из каталога `coursework/` настройте `inventory/hosts.ini` по примеру `inventory/hosts.ini.example`, SSH-доступ и Ansible Vault. Для настройки ядра нужна коллекция `ansible.posix`.

```bash
ansible-playbook playbooks/first_playbook/check_user_defaults.yml --ask-vault-pass
ansible-playbook playbooks/first_playbook/fix_user_defaults.yml --ask-vault-pass
```

Другие сценарии запускаются аналогично из соответствующих каталогов.

**Внимание:** исправляющие сценарии изменяют конфигурацию узлов.

