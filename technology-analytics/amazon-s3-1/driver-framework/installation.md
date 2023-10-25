---
description: >-
  This sections covers the step-step instruction about the Lyftrondata connector
  installation. It's must to have Python 3.9 as the default version for our
  drivers to work efficiently.
---

# Installation

### Prerequisite

The [Lyftrondata](https://www.lyftrondata.com) driver for [S3Excel](https://lyftron.com/source/data-migration-from-amazon-s3-to-snowflake-google-bigquery-amazon-redshift-and-azure-sql-database/) requires the below versions

* [ ] <mark style="color:blue;">Python 3.9</mark>
* [ ] <mark style="color:blue;">Python 3 pip</mark>
* [ ] <mark style="color:blue;">Connector Wheel file</mark>
* [ ] <mark style="color:blue;">Valid license</mark>
* [ ] <mark style="color:blue;">Knowledge of Python programming</mark>
* [ ] <mark style="color:blue;">Knowledge of SQL</mark>

### Installation Steps

To start your installation, you need to download the [wheel](https://pypi.org/project/wheel/) file. The downloaded archive contains several whl files, each of which corresponds to a specific combination of environmental factors. These factors include:

* The operating system that the python connector is used in, whether it is Windows, Mac, or Linux.
* The Architecture of the operating system, whether it is 32-bit or 64-bit. For Windows systems, this will correspond to the win32 or win\_amd64 wheels. For Linux, this will correspond to the linux\_i686 and linux\_x86\_64 wheels.
* The version of Python is in use. The connectors are supported in Python 3.9 for Windows and Linux, and for Mac.
* Once the appropriate whl file is identified, install the connector to your Python distribution with the "pip install" command via the command line. This will usually take the form of running the following commands in sequence. The wheel for Python 3.9 is used for the below example:

#### Linux

{% code title="Lyftrondata_Linux_Sdk" lineNumbers="true" %}
```shell
sudo apt-get install python3.9
sudo apt-get install python3-pip
python3 -m venv myvenv
source venv/bin/activate
pip install Lyftrondata_Mylibrary.whl
```
{% endcode %}

#### Windows

{% code title="Lyftrondata_Win_Sdk" lineNumbers="true" %}
```shell
winget install -e --id Python.Python -v 3.9.0
python3 -m venv myvenv
source venv/bin/activate
pip install Lyftrondata_Mylibrary.whl
```
{% endcode %}

**Mac**

```shell
brew install python@3.9
python3 -m venv myvenv
source venv/bin/activate
pip install Lyftrondata_Mylibrary.whl
```

### Validation

You can confirm whether the connector is successfully installed by running the pip list command. If "Lyftrondata\_Mylibrary.whl" is present in the list output by the command, then the installation was successful.

```shell
pip list 
```

### Uninstallation

Should the connector need to be uninstalled for any reason, you can do so by running the pip uninstall command, as in the example below:

```shell
pip uninstall Lyftrondata_Mylibrary.whl
```

### License Key

The license key will be provided by the Lyftrondata team which will be used for driver connectivity validation.

```shell
import Lyftrondata.MyConnector.lib.Lyftrondata_MyConnector_Connector as con
lyft = con.Connect("My Lyftrondata license key")
```

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](https://app.gitbook.com/o/wtkDnJM7XX3whUqN09p1/s/lTEE4RQvO3RwZSpc3Y6M/\~/changes/14/technology-analytics/amazon-s3-1).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to answer any additional questions you may have! [Set up a meeting with our data experts.](https://www.lyftrondata.com/book-a-meeting/)