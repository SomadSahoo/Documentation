Github repositories
===================

All software for this project is hosted on `Github <https://github.com/MultiModelling/>`_.

This page lists the available repositories, at the moment of writing of this documentation.

Generic repositories
--------------------
- `Model-Orchestrator <https://github.com/MultiModelling/Model-Orchestrator>`_: For setting up Apache Airflow as the orchectrator
- `Database-MinIO <https://github.com/MultiModelling/Database-MinIO>`_: For setting up Minio as the intermediate model storage
- `Model-Registry <https://github.com/MultiModelling/Model-Registry>`_: a simple model registry implementation
- `Model-Deployment <https://github.com/MultiModelling/Model-Deployment>`_: Some scripts to automatically deploy multi-model stacks

- `Model-Repository <https://github.com/MultiModelling/Model-Repository>`_: contains example workflow configurations for the three use cases considered in the MMvIB project
- `Documentation <https://github.com/MultiModelling/Documentation>`_: the source of this documentation page

Model adapter repositories
--------------------------
- `Adapter-CTM <https://github.com/MultiModelling/Adapter-CTM>`_: The CTM adapter for the MMvIB project
- `Adapter-ESSIM <https://github.com/MultiModelling/Adapter-ESSIM>`_: The ESSIM adapter for the MMvIB project
- `Adapter-ETM-KPIs <https://github.com/MultiModelling/Adapter-ETM-KPIs>`_: The ETM adapter for the MMvIB project
- `Adapter-Regionalization <https://github.com/MultiModelling/Adapter-Regionalization>`_: Adapter for the regionalization module
- `moter-adapter <https://github.com/MultiModelling/moter-adapter>`_: The MOTER adapter for the MMvIB project
- `teacos-adapter <https://github.com/MultiModelling/teacos-adapter>`_: The TEACOS adapter for the MMvIB project

AIMMS based model adapter template repository
---------------------------------------------
- `aimms-adapter <https://github.com/MultiModelling/aimms-adapter>`_: ...

Repositories for simple adapters used for initial testing
---------------------------------------------------------
- `Adapter-ESDL-Add-Price-Profile  <https://github.com/MultiModelling/Adapter-ESDL-Add-Price-Profile>`_: Demo adapter that adds a price profile to an ESDL energy system. This is a 'special' adapter as it doesn't call any external model, all logic is implemented by the adapter itself.
- `Adapter-ETM-Price-Profile <https://github.com/MultiModelling/Adapter-ETM-Price-Profile>`_: Demo adapter that retrieves and stores an electricity price profile from the ETM.

- `AIMMS-ESDL <https://github.com/MultiModelling/AIMMS-ESDL>`_: Generic repository with code to create a SQL database out of an ESDL file that can be used by an AIMMS based model. This code is used by the MOTER, Opera and TEACOS adapter
