# What is a Aquifer?
Aquifer is a command line interface that makes it easy to create and build Drupal websites using the Drush make workflow.

At it's core, Aquifer is a set of highly-configurable tools that automate the process of scaffolding, building, and installing Drupal in a Drush make workflow. Then, Aquifer provides an intuitive extensions API that make it possible to painlessly add other pieces of functionality to your workflow, like coding standards sniffing, and running your project in drupalvm.

# Why use Aquifer?
There are a number of reasons that you may find Aquifer particularly useful.

## Minimalistic
Aquifer, at it's core, is only intended to automate laborious, repetitive tasks that have to be done initially when setting up a Drupal site, and continuously as a site is being built. It doesn't try to solve every imaginable problem, or provide every tool that any project might need. Instead, it focuses on being modular and extendable, so that tools can be added as needed.

## Configurable
Aquifer provides a very high level of configurability, of course with opinionated, sensible defaults. For example, Aquifer can scaffold a Drupal project that uses Drush make. However, it doesn't demand any specific file structure. It has a default sensible file structure, but any component of that structure can be overridden.

## Extendable
Instead of trying to provide every tool any project might need, Aquifer has an npm-based extension API that is easy to use and develop against. So, components such as a Behat testing tools or coding standards sniffers are really easy to install, and extremely configureable, but not forced upon projects. Aquifer extensions are intended to be easy-to-implement, portable, configurable tool sets.
