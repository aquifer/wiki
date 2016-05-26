# Quick-start guide

Get started using Aquifer with the following commands.

## 1. Install Aquifer

Aquifer is an npm module. Install the latest stable version by running:

```bash
npm install -g aquifer
```

## 2. Create an Aquifer project

To create a Aquifer-based, Drush Make, Drupal 7 project, run:

```bash
aquifer create my_project_name
```

This command creates scaffolding that holds all the project's files and folders. It also creates an `aquifer.json` file, which contains settings and configuration for Aquifer.

The following options are available to you:

- `-d, --drupal_version <major_version_number>`  Optional Major Drupal version. Accepts 7 or 8, defaults to 7.
- `-c, --config_file <path>`                     Optional path to an aquifer.json config file.

## 3. Building a Drupal site

Aquifer has a system that constructs a Drupal site root from a Drush make file, settings files, and custom code. This can be invoked by running: 

```bash
aquifer build
```

The directory that Aquifer builds into can be configured by editing the `"build"` property in the `aquifer.json` file. The value of that property should be a path, and can be relative to the project directory, or an absolute path (for example, `build`, or `/var/www`).

### Overriding `aquifer.json` locally

Any property in `aquifer.json` can be overridden locally without modifying `aquifer.json`. For instance, the build directory is highly relative to the environment in which Aquifer is building.

To override properties, create an `aquifer.local.json` file in the root of your Aquifer project, and set any properties with the values you want. They will automatically take presidence over the values specified in `aquifer.json`. Note that only properties you want to override should be added to `aquifer.local.json`, as this file does not replace the main `aquifer.json` file entirely, but only overrides the values assigned to properties it contains.

## 4. Adding contrib code

To add contrib modules to your project, edit the `drupal.make.yml` file and add your contrib modules there. To learn more about Drush make, see the [these docs](http://www.drush.org/en/master/make).

## 5. Adding custom code.

Add custom themes to the `themes` folder within the Aquifer root. Likewise, add custom modules  to the `modules/custom` folder, or `modules/features` folder if the custom module is a feature. When you build the site, Aquifer will symlink those files into your site root.

## 6. Installing, removing, and loading extensions.

Installing extensions is simple. You can add extensions from local directories, git repositories, or from the npm repository.

### Installing from npm

```bash
aquifer extension-add extension-name
```

### Installing from git

Installing from sources that are _not_ npm require you to use the `-s` source flag.

```bash
aquifer extension-add extension-name -s git+ssh://git@github.com/username/reponame
```

### Installing from local file system

You could even write an Aquifer extension and store it in your project if you wanted to.

```bash
aquifer extension-add extension-name -s /path/to/extension-name
```

### Loading extensions

Aquifer will load all the extensions specified in the `aquifer.json` file when this command runs:

```bash
aquifer extensions-load
```

Extensions are not checked into repositories. This is useful when you have multiple people working on a project. If one adds an extension, the others can load the extensions in. Aquifer will notify you when you have extensions that are installed but not downloaded locally.
