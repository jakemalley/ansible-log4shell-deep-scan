# ansible-log4shell-deep-scan

Ansible playbook wrapper for Arctic Wolf's Log4Shell detection script ([Found here](https://github.com/rtkwlf/wolf-tools/tree/main/log4shell)). More information in their blog post [here](https://arcticwolf.com/resources/blog/arctic-wolf-releases-open-source-log4shell-detection-script).

## usage

Running locally (using sudo, and prompting for password):
```
ansible-playbook -i 'localhost,' -c local log4shell_deep_scan.yml -K
```

Running with an inventory
```
ansible-playbook -i inventory.ini log4shell_deep_scan.yml
```

## disconnected environments:

Download the Log4Shell detection script manually from [GitHub](https://raw.githubusercontent.com/rtkwlf/wolf-tools/main/log4shell/log4shell_deep_scan.sh) manually or using:
```
curl -Lo log4shell_deep_scan.sh https://raw.githubusercontent.com/rtkwlf/wolf-tools/main/log4shell/log4shell_deep_scan.sh
```

The playbook will detect this file exists, and copy this to the remote host rather than downloading the script directly.
