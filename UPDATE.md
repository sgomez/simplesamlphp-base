# UPDATE

## Version 1.1.1

The install

- Change the script section in composer.json to:
```json
{
    "scripts": {
        "post-package-install": [
            "Sgomez\\SimpleSamlPhp\\Composer\\ScriptHandler::installModuleHook"
        ],
        "post-package-update": [
            "Sgomez\\SimpleSamlPhp\\Composer\\ScriptHandler::installModuleHook"
        ],
        "pre-package-uninstall": [
            "Sgomez\\SimpleSamlPhp\\Composer\\ScriptHandler::uninstallModuleHook"
        ]
    }
}
```

## Version 1.0.0

- First version.