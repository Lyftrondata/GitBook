# Settings and Security

**Network Security: Opening Ports**

***

Ensuring network security while allowing access to specific services requires careful consideration of port openings. Below are the details for opening ports for various services within your network environment:

***

| Component | Port | Purpose                                                     | Security Considerations                                                                                                                                                             | Configuration                                                                                                                                          |
| --------- | ---- | ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| UI        | 3000 | Allows access to the Lyftrondata user interface.            | Opening port 3000 exposes the UI to potential attackers. Ensure proper authentication mechanisms are in place to prevent unauthorized access.                                       | Configure your network firewall to allow inbound traffic on port 3000 to the server hosting the Lyftrondata UI component.                              |
| API       | 8000 | Facilitates communication with Lyftrondata's API endpoints. | Open port 8000 grants access to Lyftrondata's API. Implement secure authentication and authorization mechanisms to control access to sensitive data and operations.                 | Configure your network firewall to allow inbound traffic on port 8000 to the server hosting the Lyftrondata API component.                             |
| DB        | 8001 | Enables database connections within Lyftrondata.            | Opening port 8001 allows communication with the Lyftrondata database. Implement network segmentation and access controls to restrict access to authorized clients and applications. | Configure your network firewall to allow inbound traffic on port 8001 to the server hosting the Lyftrondata database component.                        |
| Airflow   | 8080 | Provides access to the Airflow web interface.               | Opening port 8080 exposes Airflow to potential attacks. Implement HTTPS and strong authentication mechanisms to secure access to the Airflow interface.                             | Configure your network firewall to allow inbound traffic on port 8080 to the server hosting the Lyftrondata Airflow component.                         |
| Airflow   | 5009 | Provides access to the Airflow web interface.               | Opening port 5009 exposes Airflow to potential attacks. Implement HTTPS and strong authentication mechanisms to secure access to the Airflow interface.                             | Configure your network firewall to allow inbound traffic on port 5009 to the server hosting the Lyftrondata Airflow component.                         |
| Postgres  | 5432 | Facilitates communication with the PostgreSQL database.     | Opening port 5432 grants access to the PostgreSQL database. Implement encryption, strong authentication, and role-based access control (RBAC) to secure database connections.       | <p>Configure your network firewall to allow inbound traffic on port 5432 to the server hosting the PostgreSQL database used </p><p>by Lyftrondata.</p> |

**Description:-** In AWS Security Group inbound rules, you can specify the IP address of your office to open a particular port, allowing access to your project within your office environment.

For unrestricted traffic, you must specify the public IP address of specific AWS EC2 instances or the public IP address of the Airflow AWS EC2 instance.

**Application-Ec2-Security Inbound Rules**

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

**Airflow-Ec2-Security Inbound Rules**

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**After opening the require ports on server**

* Follow the lyftrondata installation [document](../lyftrondata-installation/) for installation.
