# Scaffolding system

Aquifer ships with a highly-configurable scaffolding system that can create an Drush make Drupal workflow in a directory.

## Using `aquifer create`

The Aquifer CLI has a create command. When this command is run, it will create a directory, and scaffold a Drush make Drupal workflow in the folder. It takes one parameter, which should represent the machine name of your project. This command also allows you to pass in a configuration file that specifies how the project is scaffolded.

* `aquifer create --help` - Returns helpful documentation for this command.
* `aquifer create my_project_name` - Creates a folder called `my_project_name` in the current working directory, and scaffolds a drush make, Drupal 7 site root.
* `aquifer create my_project_name -d 8` - Creates a folder called `my_project_name` in the current working directory, and scaffolds a drush make, Drupal 8 site root.
* `aquifer create my_project_name --config_file /path/to/config.json` - Creates a folder called `my_project_name` in the current working directory, and uses the `config.json` to determine the file structure that should be scaffolded.

### Using a config file

As mentioned previously, `aquifer create` accepts a `--config_file` or `-c` flag that takes a path to a config JSON file.

When supplied, this JSON file is used to scaffold the project. File and folder names will are created based on what is specified in the passed-in file. This allows one to have complete control over the source tree structure of the entire project. Here's an example `config.json` file:

```javascript
{
  "name": false,
  "core": 7,
  "build": {
    "method": "drush make",
    "directory": "build",
    "makeFile": "drupal.make.yml"
  },
  "sync": {
    "directories": {
      "root": {
        "destination": "",
        "method": "symlink",
        "conflict": "overwrite"
      },
      "modules/custom": {
        "destination": "sites/all/modules/custom",
        "method": "symlink",
        "conflict": "overwrite"
      },
      "modules/features": {
        "destination": "sites/all/modules/features",
        "method": "symlink",
        "conflict": "overwrite"
      },
      "themes/custom": {
        "destination": "sites/all/themes/custom",
        "method": "symlink",
        "conflict": "overwrite"
      },
      "files": {
        "destination": "sites/default/files",
        "method": "symlink",
        "conflict": "overwrite"
      }
    },
    "files": {
      "settings/settings.php": {
        "destination": "sites/default/settings.php",
        "method": "symlink",
        "conflict": "overwrite"
      },
      "settings/secret.settings.php": {
        "destination": "sites/default/secret.settings.php",
        "method": "symlink",
        "conflict": "overwrite"
      },
      "settings/local.settings.php": {
        "destination": "sites/default/local.settings.php",
        "method": "symlink",
        "conflict": "overwrite"
      }
    }
  },
  "run": {
    "scripts": {
      "refresh": [
        "drush rr",
        "drush cc drush",
        "drush en -y master",
        "drush master-execute -y --scope=local",
        "drush updb -y",
        "drush fra -y",
        "drush cc drush"
      ]
    },
    "postBuild": []
  },
  "extensions": {},
  "environments": {
  }
}
```
