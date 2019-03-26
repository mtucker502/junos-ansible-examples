# Junos Space

These are a collection of playbooks for Junos Space using the URI module.

## Examples

```
$ ansible-playbook -i hosts space-add-device.yml -e "@devices.yml"
```

```
$ ansible-playbook -i hosts space-get-active-sessions.yml 

PLAY [Space API Example] ************************************************************************************************************************************************************

TASK [Login to Junos Space] *********************************************************************************************************************************************************
ok: [space01]

TASK [Print login results] **********************************************************************************************************************************************************
skipping: [space01]

TASK [Get Active User Sessions] *****************************************************************************************************************************************************
ok: [space01]

TASK [print results] ****************************************************************************************************************************************************************
ok: [space01] => {
    "result.json": {
        "users": {
            "@total": "2", 
            "@uri": "/api/space/user-management/users", 
            "user": [
                {
                    "@href": "/api/space/user-management/users/2", 
                    "@uri": "/api/space/user-management/users/2", 
                    "auth-mode": "Local", 
                    "domains": {
                        "domain": {
                            "@href": "/api/space/domain-management/domains/2", 
                            "id": 2, 
                            "name": "Global"
                        }
                    }, 
                    "first-name": "Lab", 
                    "id": 2, 
                    "last-name": "User", 
                    "lock-out-status": "No", 
                    "name": "lab", 
                    "password-status": "ACTIVE", 
                    "read-only": false, 
                    "role-type": "ALL_ACCESS", 
                    "status": "Enabled"
                }, 
                {
                    "@href": "/api/space/user-management/users/1", 
                    "@uri": "/api/space/user-management/users/1", 
                    "auth-mode": "Local", 
                    "domains": {
                        "domain": {
                            "@href": "/api/space/domain-management/domains/2", 
                            "id": 2, 
                            "name": "Global"
                        }
                    }, 
                    "first-name": "Open", 
                    "id": 1, 
                    "last-name": "Space", 
                    "lock-out-status": "No", 
                    "name": "super", 
                    "password-status": "ACTIVE", 
                    "primary-email": "super@juniper.net", 
                    "read-only": false, 
                    "role-type": "ALL_ACCESS", 
                    "status": "Enabled"
                }
            ]
        }
    }
}

PLAY RECAP **************************************************************************************************************************************************************************
space01                    : ok=3    changed=0    unreachable=0    failed=0   

```
