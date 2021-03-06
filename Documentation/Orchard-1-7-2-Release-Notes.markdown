Build: 1.7.2

Published: 11/19/2013

How to Install Orchard
----------------------

To install Orchard using Web PI, follow these instructions:
<http://docs.orchardproject.net/Documentation/Installing-Orchard>.
Web PI will detect your hardware environment and install the application.

Alternatively, to install the release manually, download the Orchard.Web.1.7.2.zip file.

<http://docs.orchardproject.net/Documentation/Manually-installing-Orchard-zip-file>

The zip contents are pre-built and ready-to-run. Simply extract the contents of the Orchard
folder from the zip contents to an IIS virtual directory (or site root) and then point your
browser to the site. You can also just extract to a local folder and open the Orchard
folder in Visual Studio or WebMatrix as a web site (but not as a web application).
Please make sure you have a machine key
<http://docs.orchardproject.net/Documentation/Setting-up-a-machine-key>
or you may experience frequent disconnections.

What file to download?
----------------------

If you just want to use Orchard and don't care about the source code, Orchard.Web.1.7.2.zip
is what you want to use, preferably through the WebPI instructions.
Do not attempt to build the WebPI version in VS. Use the full source if you want to use VS.

If you want to take a look at the source code or want to be able to build the application in Visual Studio,
Orchard.Source.1.7.2.zip is fine.

If you want to setup a development environment for patch or module development,
you should clone the repository by following the instructions here:
<http://docs.orchardproject.net/Documentation/Setting-up-a-source-enlistment>

Branches are described here: <http://docs.orchardproject.net/Documentation/Developer-FAQ#Whatarethedefaultanddevbranches?WhichoneshouldIbeusing?>

Who should use this software?
-----------------------------

This software is in version 1.7.2. The code is in a stable state and constitutes
a solid foundation for building applications, themes and modules.
Suggestions are welcome in the discussion forums.

You are allowed to use this software in any way that is compatible with the new BSD license.
This includes commercial derivative work.

What's new?
-----------

Orchard 1.7.2 fixes bugs and introduces the following features:

* *Orchard.SSL*: New SSL module replacing Contrib.SSL, providing convention enhanced security, convention based
* Azure SDK 2.2 support
* *Orchard.MediaLibrary*: 
  - Search engine integration feature
  - Creation of custom media types
* Consistent css class names for text boxes  
* Performance
  - Removed BlogConstraintPathUpdator background task
  - Optimized AliasUpdator
  - Removed deep recursive data migration calls
  - Created default indexes on content item tables
  - Added Eager Fetching filter for projection
* *Orchard.Search*: 
  - Improved API to define range queries

The full list of fixed bugs for this release can be found here:

* [Bugs fixed in 1.7.2](https://orchard.codeplex.com/workitem/list/advanced?keyword=&status=Resolved|Closed&type=All&priority=All&release=Orchard%201.7.2&assignedTo=All&component=All&sortField=LastUpdatedDate&sortDirection=Descending&page=0&reasonClosed=All).

How to upgrade from a previous version
--------------------------------------

You can find migration instructions here: <http://docs.orchardproject.net/Documentation/Upgrading-a-site-to-a-new-version-of-Orchard>.

No matter what migration path you take, please take the precaution of making a backup of your
site and database first.

### Upgrading from Orchard 1.3 and earlier

Orchard 1.4 introduced breaking changes in the way content URLs are managed. Because of that,
and if you're migrating from version 1.3 or earlier, the Upgrade module can be used to migrate
data. If you upgrade a site to 1.7 from 1.3 or earlier and can't
see your contents, you probably need to run this module. In order to do that, go to the admin
section of the site (by appending /admin to the URL where the home page should be), then go
to Modules and enable the feature.

The feature, once enabled, adds a new entry to the admin menu: "Upgrade to 1.7", that can
migrate the Route data of your content items as well as field data from older field modules, and menu items.

### Upgrading from Orchard 1.6 and earlier

* Enable the Upgrade module

#### Migrating Content Item Picker Field contents

In Orchard 1.7 this field has been moved to a more appropriate module, and thus needs it definitions to be migrated
in order to reflect this change.

* Click on Upgrade To 1.7 from the menu
* Select the Content Picker tab and click **Migrate**

#### Migrating Contrib.Taxonomies module

In Orchard 1.7 the Contrib.Taxonomies module has been integrated into the core modules as the Orchard.Taxonomies module.
If you want to use the new module then you need to follow these steps. It will convert all your content and metadata
which were associated with Contrib.Taxonomies.

* Disable the module Contrib.Taxonomies
* Enable the module Orchard.Taxonomies
* Click on Upgrade To 1.7 from the menu
* Select the Taxonomies tab and click **Migrate**
* Finally, update any template which was previously using the Contrib.Taxonomies templates

#### Importing Media files into the Media Library

In Orchard 1.7 a new media management module is provided. In order to use it you will have to import all your media files
to this new module. It will create a dedicated content item for each of your files. Ultimately it will also convert
all the current usage of Media Picker Fields to the new Media Library Picker Field.

* Disable the module Media
* Enable the module Media Library
* Click on Upgrade To 1.7 from the menu
* Select the Media Library tab and click **Migrate**
* In the Media Picker Field section click **Migrate**
* Finally, update any template which was previously using the Media Picker Field directly

### Upgrading from Orchard 1.7.1 

If you were using the Roles or Comments Workflow Activities you will need to enable the corresponding features:

* Comments Workflows Activities
* Roles Workflows Activities
* 

If you were using Multi-Tenancy then you might need to change the settings of the tenants. Multi-tenant host name are
not more matching sub-domains automatically. You will need to replace `foo.com` by `*.foo.com` if you want the tenant 
to match any sub-domain. You can also specifically set which sub-domains to accept like this: `foo.com, www.foo.com`

Contributors
------------

This software would not exist without the community. In particular, for this release,
we should all be grateful to the following people who contributed patches and features:

- Antoine Griffard ([agriffard](http://www.codeplex.com/site/users/view/agriffard))
- Benedek Farkas ([nightwolf226](https://www.codeplex.com/site/users/view/nightwolf226))
- Bertrand Le Roy ([bertrandleroy](http://www.codeplex.com/site/users/view/bertrandleroy))
- Christian Surieux ([csadnt](http://www.codeplex.com/site/users/view/csadnt))
- Daniel Stolt ([Decorum](https://www.codeplex.com/site/users/view/Decorum))
- Eric McGrath ([EricMcGrath](https://www.codeplex.com/site/users/view/EricMcGrath))
- Jay Harris ([jayharris](https://www.codeplex.com/site/users/view/jayharris))
- Jeff Bullock ([j3ffb](http://www.codeplex.com/site/users/view/j3ffb))
- Jeff Olmstead ([jao28](https://www.codeplex.com/site/users/view/jao28))
- Jim Macdonald ([Jimasp](http://www.codeplex.com/site/users/view/Jimasp))
- Piotr Szmyd ([pszmyd](https://www.codeplex.com/site/users/view/pszmyd))
- Sebastien Ros ([sebastienros](http://www.codeplex.com/site/users/view/sebastienros))
- Sipke Schoorstra ([sfmskywalker](http://www.codeplex.com/site/users/view/sfmskywalker))
- Stanley Goldman ([StanleyGoldman](http://www.codeplex.com/site/users/view/StanleyGoldman))
- Vladimir Makaev ([VMakaev](https://www.codeplex.com/site/users/view/VMakaev))
- Volodymyr Usarskyy ([usarskyy](https://www.codeplex.com/site/users/view/usarskyy))
- Zoltán Lehóczky ([Piedone](http://www.codeplex.com/site/users/view/Piedone))
