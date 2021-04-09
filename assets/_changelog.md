
1.0 - Apr 8, 2021
=================

* Added this file
* Added feature-grid styling
* Added special-row styling
* Added stories-grid styling
* Added intro-smaller styling




About this file
===============

Use this changelog to indicate what was changed and added; it'll be a lot easier than trying to piece that together via reviewing commits in GitHub.



Versioning
----------

I'm using the [SemVer](https://semver.org/) versioning system. The format for this is major.minor.patch.

Basically:

- If you make major changes that are likely to break something, like changing classnames or radically restructuring something, increase the major version number (1.X to 2.0)

- If you make a minor change, like adding a feature or pattern, increase the minor version number (1.1 to 1.2)

- If you make a patch change, like a bugfix, increase the patch version number (1.0 to 1.0.1).

In my experience, most changes are minor or patches.



Deprecating old classes
-----------------------

Also: if changing a classname, leave the old name in place, but deprecated. Example: if the old naming scheme for themes was .theme-red, and the new scheme is .theme:red, add the new class but keep the old one. Nothing will break, but we'll use the new one and change examples of the old one as we run across them.

