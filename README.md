Make DMP Tools Actionable
=========================

-   **194.045 Data Stewardship 2019S**
-   Gerald Weber, 0125536
-   Helmuth Breitenfellner, 08725866

Set Up Instance of RDMO
=======================

We have been setting up an instance of RDMO on a virtualized
environment, using Docker. The installation can be used at
[rdmo.helmuth.at/](https://rdmo.helmuth.at).

For this part of the exercise we have been using the docker-compose
version of RDMO as available on
[GitHub](https://github.com/rdmorganiser/rdmo-docker-compose).

Re-created DMP in RDMO
----------------------

RDA DMP Export for RDMO
=======================

Approach to Connect with RDMO
-----------------------------

We were investigating the following possible ways of connecting with an
RDMO instance:

-   Database connection
-   RDMO API
-   XML export from RDMO

Using the database access was considered the last resort, as this would
be dependend on internal data structures of the tool.

The RDMO API did originally sound very promising. However, we found that
existing installations often disabled the API (e.g.
[rdmo-demo.uibk.ac.at/](http://rdmo-demo.uibk.ac.at/)), or the API is
not accessible for regular users.

We settled on the third option, which is using the XML which can be
exported from a project in the RDMO user interface. This allows using
the export tool for regular users, even if the API has been disabled in
the installation.

Using the Tool
--------------

The tool is now a simple command line tool. As a precondition, the user
has to export the project as XML from RDMO. Then the tool can be started
with

    python3 xml2madmp.py <rdmo-export.xml> <ma-dmp.json>

Mapping existing DMP templates to RDA DMP Common Standard
=========================================================

For this part of the exercise we have used a two-part mapping.

First, we created a questionaire based on the Horizon 2020 template and
FWF template, which maps the questions to the corresponding fields and
attributes of the RDMO model.

Then, we were applying our mapping from RDMO attributes to the [RDA DMP
Common
Standard](https://github.com/RDA-DMP-Common/RDA-DMP-Common-Standard).

Map Horizon 2020 template to RDA DMP Common Standard
----------------------------------------------------

Some of the questions from Horizon 2020 do not clearly map to attributes
in the RDMO data model. We were using guidelines from the existing
Horizon 2020 view which performs the mapping into the other direction.

Map FWF template to RDA DMP Common Standard
-------------------------------------------

Similar issues as in the case of Horizon 2020 were encountered. In
addition, we did not cater for the last case when no data is processed,
as a DMP is then not needed at all.
