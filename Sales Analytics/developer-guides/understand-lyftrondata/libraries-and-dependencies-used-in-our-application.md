# Libraries and Dependencies Used in Our Application

Libraries and dependencies details regarding purpose and version are as follow



<table><thead><tr><th width="259">Library Name</th><th>Purpose</th><th>Version</th></tr></thead><tbody><tr><td>Python3-pip</td><td>Python package installer for Python 3.x.</td><td>21.3.1</td></tr><tr><td>Python3-dev</td><td>Development files for building Python modules in Python 3.x.</td><td>21.3.1</td></tr><tr><td>Python3-tk</td><td>Tkinter module for Python 3.x, used for GUI applications.</td><td>-21.3.1</td></tr><tr><td>Python3-venv</td><td>Python virtual environment support for Python 3.x.</td><td>21.3.1</td></tr><tr><td>Redis-server</td><td>The <code>image: redis:7.2.4</code> line in the Dockerfile specifies the Redis image version 7.2.4 to be used. Redis serves as a fast, in-memory data store for caching and messaging within the application's Docker environment, enhancing performance and scalability while ensuring compatibility and consistency across deployments.</td><td>7.2.4</td></tr><tr><td>Pymssql</td><td>MSSQL database adapter for Python version</td><td> 2.2.5.</td></tr><tr><td>Pyyaml</td><td>YAML parser and emitter for Python version </td><td>5.4.1</td></tr><tr><td>Apache-airflow</td><td><p></p><ul><li>This command installs Apache Airflow version 2.2.0, a platform for orchestrating workflows.</li><li>Ensure that pip is installed on your system before running this command.</li></ul></td><td>2.2.0</td></tr><tr><td>Java</td><td><p></p><ul><li>OpenJDK is a free and open-source implementation of the Java Platform.</li><li>This command installs OpenJDK version 11, which is required by Apache Airflow for execution.</li></ul></td><td>11 </td></tr><tr><td>Node.js v </td><td>JavaScript runtime environment for executing JavaScript code server-side.</td><td>16.15.1</td></tr><tr><td>Yarn</td><td>Dependency management tool for JavaScript projects.</td><td>1.22.21</td></tr><tr><td>Spark &#x26; Hadoop</td><td>Spark 3.2.2 with Hadoop 3.2 support is a distributed computing system for large-scale data processing. It offers high performance, fault tolerance, and diverse data processing capabilities like batch processing and real-time streaming. Spark simplifies complex data workflows, making it suitable for big data analytics and computation tasks.</td><td>spark-3.2.2-bin-hadoop3.2</td></tr><tr><td>Python 3.9 </td><td>Python 3.9 is a major release with enhanced features and performance improvements. It offers new syntax, built-in types, and additional library modules. Python 3.9 improves developer productivity, code readability, and application efficiency</td><td>Python 3.9 </td></tr><tr><td>PostgreSQL</td><td>Relational database management system</td><td>14</td></tr><tr><td>Docker</td><td>Used to run and manage containers </td><td>26.0.0</td></tr><tr><td>Docker Compose</td><td>Used to run and manage the multiple containers compose files</td><td>v2.25.0</td></tr></tbody></table>

## Libraries&#x20;

Below are the libraries which is used by our UI.

| Library                    | Version |
| -------------------------- | ------- |
| django                     | 3.1.7   |
| django-filter              | 2.4.0   |
| djangorestframework        | 3.12.4  |
| django-cors-headers        | 3.7.0   |
| python-dateutil            | 2.8.1   |
| python-dotenv              | 1.0.1   |
| pandas                     | 1.4.1   |
| SQLAlchemy                 | 1.4.17  |
| django-countries           | 7.2.1   |
| boto3                      | 1.17.79 |
| schedule                   | 1.1.0   |
| requests                   | 2.25.1  |
| psycopg2-binary            | 2.9.1   |
| getmac                     | 0.8.2   |
| sendgrid                   | 6.7.1   |
| redis                      | 3.5.3   |
| xlrd                       | 2.0.1   |
| openpyxl                   | 3.0.7   |
| selenium                   | 3.141.0 |
| apscheduler                | 3.7.0   |
| jaydebeapi                 | 1.2.3   |
| Jinja2                     | 3.0.1   |
| django-q                   | 1.0.2   |
| sentry-sdk                 | 1.3.1   |
| pyspark                    | 3.1.2   |
| google-cloud-bigquery      | 2.34.0  |
| google-auth                | 1.35.0  |
| django-allauth             | 0.45.0  |
| drf-yasg                   | 1.20.0  |
| rncryptor                  | 3.3.0   |
| gunicorn                   | 20.1.0  |
| simplejson                 | 3.17.6  |
| psutil                     | 5.9.1   |
| flower                     | 1.2.0   |
| stripe                     | 5.0.0   |
| pdfkit                     | -       |
| django\_otp                | 1.0.2   |
| dj\_rest\_auth             | 2.2.4   |
| dropbox                    | 11.36.2 |
| celery                     | 5.2.7   |
| snowflake-connector-python | 3.6.0   |
| django-guardian            | 2.4.0   |



{% hint style="info" %}
Info: For lyftrondata installation on the environment follow the [document](../../managing-lyftrondata/lyftrondata-installation/)
{% endhint %}
