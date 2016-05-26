# Scaffolding system

Aquifer ships with a highly-configurable scaffolding system that can create an Drush make Drupal workflow in a directory.

## Using `aquifer create`

The Aquifer CLI has a create command. When this command is run, it will create a directory, and scaffold a Drush make Drupal workflow in the folder. It takes one parameter, which should represent the machine name of your project. This command also allows you to pass in a config file that specifies how the project should be scaffolded.

* `aquifer create --help` - Returns helpful documentation for this command.
* `aquifer create my_project_name` - Creates a folder called `my_project_name` in the current working directory, and scaffolds a drush make Drupal site root.
* `aquifer create my_project_name --config_file /path/to/config.json` - Creates a folder called `my_project_name` in the current working directory, and uses the `config.json` to determine the file structure that should be scaffolded.

### Using a config file

As mentioned previously, `aquifer create` accepts a `--config_file` or `-c` flag that takes a path to a config JSON file.

When supplied, this JSON file will be used to scaffold the project. File and folder names will be created based on what is specified in the passed-in file, allowing one to have complete control over the source tree structure of the entire project. Here's an example `config.json` file:

```javascript
{
  "name": false,
  "paths": {
    "make": "drupal.make.yml",
    "lock": false,
    "settings": "settings",
    "build": "build",
    "root": "root",
    "themes": {
      "root": "themes",
      "contrib": "themes/contrib",
      "custom": "themes/custom"
    },
    "modules": {
      "root": "modules",
      "contrib": "modules/contrib",
      "custom": "modules/custom",
      "features": "modules/features"
    },
    "files": {
      "root": "files"
    }
  }
}
```

Any file paths or settings not provided in the passed-in config file will be created using Aquifer's defaults.
