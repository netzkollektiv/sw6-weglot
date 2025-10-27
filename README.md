# Weglot Integration for Shopware 6

A very basic Weglot integration for Shopware 6. This plugin provides a minimal but functional setup to integrate Weglot Translation Service with configurable API key, enable/disable toggle, and custom JSON configuration options.

## Description

This plugin adds Weglot translation capabilities to your Shopware 6 storefront. It's designed to be simple and straightforward, providing the essential configuration options needed to get Weglot working.

## Features

- **Configurable API Key**: Set your Weglot API key directly from the Shopware admin panel
- **Enable/Disable Toggle**: Easily turn Weglot on or off without conditions
- **Custom JSON Configuration**: Add advanced Weglot configuration options via a JSON textarea field
- **German & English Support**: Interface available in both languages

## Installation

1. Install the plugin via composer:
```bash
composer require netzkollektiv/weglot
```

2. Install the plugin via the command line:
```bash
./bin/console plugin:install --activate NetzkollektivWeglot
```

Or install it through the Shopware 6 Administration:
1. Go to Settings → System → Plugins
2. Search for "Weglot Integration (Basic)"
3. Click "Install" and then "Activate"

## Configuration

1. Go to Settings → System → Plugins
2. Find "Weglot Integration (Basic)" and click on it
3. Navigate to the "Plugin settings" tab

You'll find three configuration options:

### Enable Weglot
A toggle switch to enable or disable the Weglot integration.

### API Key
Enter your Weglot API key here. You can find your API key in your Weglot dashboard.

### JSON Configuration
(Optional) Add any additional Weglot configuration as JSON. This configuration will be merged with the API key configuration when initializing Weglot.

Example JSON configuration:
```json
{
  "switchers": [
    {
      "button_style": {
        "full_name": true,
        "with_name": true,
        "is_dropdown": true,
        "with_flags": true,
        "flag_type": "circle"
      },
      "location": {
        "target": ".header-weglot",
        "sibling": null
      }
    }
  ]
}
```

## How It Works

The plugin extends the storefront meta template (`layout/meta.html.twig`) and conditionally loads the Weglot JavaScript SDK when:
1. The plugin is enabled
2. An API key is configured

The Weglot script is loaded from the official Weglot CDN and initialized with your configuration.

## Requirements

- Shopware 6.5 or higher
- A valid Weglot API key

## License

MIT

## Support

This is a basic integration plugin. For advanced features or issues, please refer to the [Weglot documentation](https://doc.weglot.com/).
