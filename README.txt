Domain
========
<!--
|<- - - - - - - This line is exactly 80 characters for reference - - - - - - ->|
-->
WORK IN PROGRESS - this module is very buggy, please do not use on production
sites. However, please DO test this module, report bugs, and submit PRs. 


Taken from Drupal README
========================

This module is a PORT-IN-PROGRESS. We are using it for a specific site, but
it has not yet been properly tested and the port is not yet complete.

1) Overview

This module provide a solution to add Domain Access on entity.

You can use this module to restrict access for entity as you do with node.

You can choose for each bundle the assignation behavior you want to use :

    - Affiliate automatically created entity to a value 
	(no widget on entity creation form, auto-assignation)
    - User choose affiliate, with a default value 
	(form widget on the entity creation form)

The access rule is basic for front end user (without specific permission):

    entity data is only accessible on the domain(s) it's assigned to.
    This is the default behavior for user in administration and front office.

For administration / administrator:

    Site contributors, with specific permission can access and/or edit content
	of multiple domain.
    The user need to be assigned to the domain he can edit (in user/*/edit)
    And need the permission "access entities affiliate on assigned domains"
    With domain views, You can create list of entities and expose the domain
	field, to filter entities by domain.

To use this module with views, you need to disable sql rewriting on some views.
(open your views -> go in advanced settings pane -> query settings), 
if you don't want to disable sql rewriting, you can add manually a view filter
on the field that hold the domain(s) entity.

For administration views you can expose to Editors 
the filter of the domain field of your entity

2) Features

- Enable Domain Access on entities
- UI for enabling domain access on entity type, 
  and batch update of existing entities
- views integration

3) Requirements

- Domain Access http://drupal.org/project/domain
- Entity API http://drupal.org/project/entity

  Extra requirements:
- To expose domain filter in views: domain views

5) Setup

- Enable domain_entity
- setup at least one domain..
- Access to admin/structure/domain/entities
- Use the forms to enable domain on entity types, you can choose 
  the behavior widget used for each bundle 
  (existing content of your website will be assigned 
   to the default bundle domain value)
- After you activate domain access, all entity will be filtered 
  by domain, if you migrate entities without assign it 
  to at least one domain, these entities became inaccessible.
- For site administrator roles that you want to allow to see 
  multiple domain entities on one domain (only in administration path):

    - Create a user
    - Add a role to the user with the permission 
	  "access entities affiliate on assigned domains"
    - Assign the user to the domain(s) he can access 
	  ("Affiliate editor options" in admin/people)

Installation
------------
- Install this module using the official Backdrop CMS instructions at
  https://docs.backdropcms.org/documentation/extend-with-modules.
- TBC

Issues
------
Bugs and Feature Requests should be reported in the Issue Queue:
https://github.com/backdrop-contrib/domain/issues.

Documentation
-------------------
Please, do help us create documentation for this module. 
https://github.com/backdrop-contrib/domain/wiki

Current Maintainers
-------------------

- [Tim Erickson](https://github.com/stpaultim) - [Simplo by Triplo](https://simplo.site/)
- Collaboration and co-maintainers welcome! REALLY, REALLY WELCOME!!

Credits
-------

Port to Backdrop CMS by:
- [Tim Erickson](https://github.com/stpaultim) - [Simplo by Triplo](https://simplo.site/)
- Could you help? Help is needed to document issues, work on fixes and to test fixes.

Drupal maintainers:
- [Ken Rickard (agentrickard)](https://www.drupal.org/u/agentrickard)
- [Katrin Valdre (nonsie)](https://www.drupal.org/u/nonsie)

Drupal development sponsored by [Palantir.net](https://palantir.net/)

Created for Drupal by [Gurpartap Singh](https://www.drupal.org/u/gurpartap-singh)

License
-------

This project is GPL v2 software.
See the LICENSE.txt file in this directory for complete text.

