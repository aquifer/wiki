# Build system
The Aquifer CLI includes a `build` tool, which uses the `drupal.make` file to construct a Drupal site root in a working directory.

## Using `aquifer build`

* `aquifer build --help` - Returns documentation for this command.
* `aquifer build` - Constructs a Drupal site root in the build directory specified in the value of the `"build"` property in `aquifer.json`.
* `aquifer build --make|-m` - Builds off of the Drush make file, ignores any Drush make lock files.
* `aquifer build --refresh-lock|-r` - Builds and generates an updated lock file.

## Customizing the build directory
The directory that Aquifer builds into can be configured by editing the `"build"` property in the `aquifer.json` file. The value of that property should be a path, and can be relative to the project directory, or an absolute path (for example, `build`, or `/var/www/drupal`).

## Locking dependencies
Aquifer is able to utilize Drush make lock files to ensure that everyone on your team is building with the same dependencies and versions. By default, this is turned off in Aquifer because of various bugs and issues that exist in Drush's locking utilities between Drush versions. 

To opt into locking, simple change the `"lock"` property in `aquifer.json` from `false` to the name of the lock file you would like to use, like `drush.make.lock`.

After enabling locking, when you run `aquifer build` for the first time, you will notice that a lock file is generated in your project root. This file will contain fully resolved versions of the contrib projects defined in your make file and will be used to determine dependency versions for subsequent builds.

Note: You must be using drush version 7 for lock file support to work. If you are using a lesser version and are unable to update drush for some reason or just plain don't like any of this lock file business, you can turn off this behavior by setting `"lock"` to `false` in the `aquifer.json` file.
