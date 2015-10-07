# What is a 'Drush make workflow'?
It's common practice when developing Drupal websites to simply add the Drupal core codebase to a repository, and then start building from there. Contrib modules, libraries, patches, and custom code files are then added into the Drupal file system, and committed directly into the repository.

The Drush make workflow takes a different approach. Instead of working with Drupal core's codebase directly, one would define the site's dependencies, and a Drupal core version in a make file. Then, when instructed, Drush make would scaffold out a Drupal site root, and add the contrib projects specified in the make file.  Then custom code is added to the freshly scaffolded Drupal file system, and then finally Drupal can be installed in a LAMP stack that has access to the codebase. The process for adding or changing contrib projects involves changing your make file, and re-running Drush make.

# Why use a Drush make workflow?
Although working with Drush make initially sounds complex, there are a number of benefits to using the Drush make workflow to construct Drupal sites.

## Clean source repositories
As opposed to committing core, contrib, library, and patch code files into a repository, Drush make manages dependencies with a make file. Non-custom dependencies are never added to the codebase, only specified as a dependency at a version.

## Clear dependency versioning
In the Drush make workflow, all dependencies are defined in a make file. This makes it easy to see what dependencies are being added to your site, and what version of the dependencies you're requiring.

## Easier updates and patches
Updating dependencies, applying patches, installing and updating libraries, and adding new dependencies is much easier and more directly manageable when using a Drush make workflow. Instead if manually performing those tasks, you simply need to tell Drush make where to get the dependencies, and what version you want. It handles the rest. Updating dependency versions is also a simple task. Simply increment or decrement the dependency version, and rebuild the site root.

## Ensured long-term stability
When using a Drush make workflow, every time you update a dependency version, or add a patch, or remove something from the codebase, the site is reconstructed with the new dependency settings. This means that if a dependency introduces problem, or a patch no longer applies with an update, the build will fail before critical problems are introduced into the site.
