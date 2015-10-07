# What is a 'Drush make workflow'?
It's common practice when developing Drupal websites to simply add the Drupal core codebase to a repository, and then start building from there. Contrib modules, libraries, patches, and custom code files are then added into the Drupal file system, and committed directly into the repository.

The Drush make workflow takes a different approach. Instead of working with Drupal core's codebase directly, one would define the site's dependencies, and a Drupal core version in a make file. Then, when instructed, Drush make would scaffold out a Drupal site root, and add the contrib projects specified in the make file.  Then custom code is added to the freshly scaffolded Drupal file system, and then finally Drupal can be installed in a LAMP stack that has access to the codebase. The process for adding or changing contrib projects involves changing your make file, and re-running Drush make.

# Why use a Drush make workflow?
Although working with Drush make initially sounds complex, there are a number of benefits to using the Drush make workflow to construct Drupal sites.

## Clean source repositories

## Clear dependency versioning

## Easier updates

## Better patch management

## Ensured long-term stability

# Why use Aquifer?
