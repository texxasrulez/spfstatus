# Roundcube SPF Status Plugin

This Roundcube plugin displays the **SPF (Sender Policy Framework) status** of incoming messages.  
It checks for the `Received-SPF` header in emails and shows a small status icon next to the message headers:

- ✅ Pass (valid sender)  
- ❌ Fail / Softfail (invalid sender)  
- ❓ Unknown (missing or neutral header)  

---

## Features
- Automatically inspects `Received-SPF` headers.
- Displays clear visual indicators (`pass.png`, `fail.png`, `unknown.png`).
- Integrates seamlessly with the Roundcube mail view (`show` and `preview` actions).

---

## Installation

### 1. Install via Composer (recommended)

In your Roundcube installation directory, run:

```bash
composer require texxasrulez/spfstatus
```

Thanks to [`composer/installers`](https://github.com/composer/installers) and the `"type": "roundcube-plugin"` declaration, the plugin will be installed into:

```
plugins/spfstatus/
```

### 2. Manual installation (fallback)

1. Download the plugin archive.  
2. Extract into your Roundcube `plugins/` directory so it looks like:

```
roundcubemail/
└── plugins/
    └── spfstatus/
        ├── spfstatus.php
        └── images/
            ├── pass.png
            ├── fail.png
            └── unknown.png
```

---

## Enabling the Plugin

Edit `config/config.inc.php` and add `spfstatus` to the plugins array:

```php
$config['plugins'][] = 'spfstatus';
```

Clear Roundcube cache if necessary:

```bash
bin/cleancache.sh
```

---

## Requirements
- PHP >= 7.4
- Roundcube Mail >= 1.4 (tested)
- Composer (if installing via Composer)

---

## Uninstallation

If installed via Composer:

```bash
composer remove texxasrulez/spfstatus
```

If installed manually, just remove the `plugins/spfstatus` directory.

---

## License
MIT License

---

## Credits
- **Author:** Gene Hawkins  
- **Original Plugin URL:** [GitHub Repository](https://github.com/texxasrulez/spfstatus)
- **Original Author:** Nathan Osman  
- **Original Plugin URL:** [GitHub Repository](https://github.com/texxasrulez/spfstatus)

---

## Troubleshooting

- Make sure `plugins/spfstatus/spfstatus.php` is present and readable.  
- Ensure the plugin directory name is exactly `spfstatus` (case-sensitive).  
- Check Roundcube logs (`logs/errors.log`) for plugin loading errors.  
