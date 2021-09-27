# Using Teamstudio Adviser

Teamstudio Adviser collects information that allows you to explore all of the applications in your HCL Notes/Domino environment. It has four modules: Catalog, Usage, Complexity and Guidance.

## Catalog
The Catalog module reads information from your Domino server catalogs and address books to provide core lists of databases, templates, users and groups. You can use the catalog to browse your databases by name, server, template or how recently they have been modified. You can use the Effective Access feature to determine which users have access to which databases even when the ACL contains complex group structures. In addition to information pulled from the server catalog, this module also allows you to set a Business Value, from 1-5, for each database trapping its importance to your organization. Lastly, the catalog module allows you to configure filters to exclude certain databases and users from the other modules.

More details are available in the [catalog](catalog.md) documentation.

## Usage
The Usage module imports usage information from your Domino server logs and displays detailed usage statistics for both users and databases. For a database, you can see how many times it was accessed and by whom, along with historical trends showing whether the usage is increasing or decreasing. For a user, you can see which databases and servers they accessed.

More details are available in the [usage](usage.md) documentation.

## Complexity
The Complexity module scans the complete designs of the databases on your servers and generates a complexity score from 1-5 measuring the approximate difficulty of migrating this application to another platform. The score is based on a number of factors including the size of the design and the numbers of different types of design elements, along with counts of specific Domino features that are hard to migrate. You can also specify keywords whose presence suggest that migration may be hard. These include, for example, references to other proprietary internal systems or external code in DLLs.

More details are available in the [complexity](complexity.md) documentation.

## Guidance
The Guidance module brings together information from all of the other modules to make a recommendation on a future plan for each database. Its recommendation takes into account the business value, usage and complexity of each database. You may also override the recommendation in cases where you already have a plan for a given database.

More details are available in the [guidance](guidance.md) documentation.
