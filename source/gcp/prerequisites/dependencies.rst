.. Copyright (C) 2021 Wazuh, Inc.

.. _gcp_dependencies:

Installing dependencies
=======================

.. note::
  The GCP module can be configured in both Wazuh manager and agent. The choice merely depends on where do you want to reach the GCP services from.

.. warning::
  The Wazuh manager includes all dependencies installed, the following steps are only necessary when configuring the integration in a Wazuh agent.


Python
------

The GCP module requires python 3. It is compatible with python versions from `3.6.0` to `3.9.5`. Future python releases should maintain compatibility although it cannot be guaranteed.

a) For CentOS/RHEL/Fedora operating systems:

.. code-block:: console

  # yum update && yum install python3

b) For Debian/Ubuntu operating systems:

.. code-block:: console

  # apt-get update && apt-get install python3


Pip
---

The required modules can be installed with Pip, the Python package manager. Most of UNIX distributions have this tool available in their software repositories:

a) For CentOS/RHEL/Fedora operating systems:

.. code-block:: console

  # yum update && yum install python3-pip


b) For Debian/Ubuntu operating systems:

.. code-block:: console

  # apt-get update && apt-get install python3-pip


Google cloud pip dependencies
-----------------------------

`google-cloud-pubsub <https://pypi.org/project/google-cloud-pubsub//>`_ is the official python library supported by Google to manage Google Cloud Pub/Sub resources. It will be used to pull the log messages from the Pub/Sub queue. Wazuh supports google-cloud-pubsub up to 1.4.3.

To install this package along with its dependencies, execute the following command:

.. code-block:: console

  # pip3 install google-cloud-pubsub==1.4.3 google-cloud-storage==1.39.0 google-api-core==1.16.0 google-auth==1.30.1 grpc-google-iam-v1==0.12.3 grpcio==1.38.0
