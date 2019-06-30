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

We were focusing on the functionality. The UI of the tool is a prototype
using Jupyter Notebook.

The export tool is connecting via the API to an RDMO instance. For this
the user has to provide username and password.

*Note: Some RDMO instances have apparently disabled the API, e.g.
[rdmo-demo.uibk.ac.at/](http://rdmo-demo.uibk.ac.at/).*

Then the tool is asking the user to select the project they want to
export. It will then be transformed into a maDMP according to [RDA DMP
Common
Standard](https://github.com/RDA-DMP-Common/RDA-DMP-Common-Standard).

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
