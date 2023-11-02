# Grafana-template-to-monitor-Azure-MySQL-Flexible

Monitoring Azure Database for MySQL - Flexible Server in a PaaS environment can be a challenging task. As a fully managed database service, MySQL - Flexible Server provides many benefits, including automatic backups, patching, and scaling. However, it also limits access to the underlying infrastructure, which can make it difficult to monitor the database's performance and health status. This lack of visibility can lead to operational challenges, such as slow query performance tuning or database downtime estimation.

Fortunately, there’s Azure Monitor, a service that you can use to monitor MySQL - Flexible Server. Azure Monitor provides a variety of metrics, including CPU utilization, memory usage, and storage space, native MySQL telemetry, such as InnoDB buffer pool usage, query counters, etc., collected from the built-in system views.

Additionally, native MySQL performance_schema and information_schema views also provide detailed insights, such as code space memory used or locking/wait events, into MySQL performance and how the service is running. You can access these views using simple MySQL SQL statements, though you would need a complex JOIN statement to get read-friendly details.

While Azure Monitor and native MySQL views provide valuable insights into the performance and health of a MySQL flexible server, these assets often are scattered across different interfaces, making it challenging to get a complete picture of the health status of the database. This is where Grafana, an open-source data visualization and monitoring platform, really helps. With Grafana, users can create a custom dashboard that consolidates all the available views, including Azure Monitor and native MySQL views, to gain a better understanding of the database's health status.

To make it easier for users to get started with Grafana, we’ve created a JSON file that you can use as a template for creating a dashboard to monitor Azure Database for MySQL - Flexible Server. This JSON file includes pre-configured panels that display important metrics integrated with Azure Monitor supported metrics, such as CPU utilization and memory usage, as well as native MySQL views that provide insights into MySQL performance and running status. Users can then customize the dashboard to meet their specific needs.

# Benefits of using this template
Using this template provides you with several benefits. For example, the template integrates with Azure Monitor to display all built-in metrics in one dashboard. As a result, you can easily monitor server health status including resource usage, HA status, workload including DML and DDL, InnoDB buffer pool, as well as status such as data page usage and physical/logical read. For more information, see the article Monitoring - Azure Database for MySQL - Flexible Server.

This template also leverages the views to display:
- Lock wait events
- Memory details
- Index statistics
- Query cost
 

# Using this Grafana template
To take advantage of using this template, be sure that you have the proper prerequisites in place, and then follow a few, straightforward steps.

## Prerequisites
Before you start, ensure that you an instance of Azure Database for MySQL – Flexible Server with:
- Grafana with the Azure Monitor plugin installed.
- MySQL with memory instrumentation enabled.
 
## Steps
Now, to use the template, perform the following steps:

1. Create an Azure Grafana instance via the Portal by using the information in the article Quickstart: create an Azure Managed Grafana instance using the Azure portal. You can also use self-managed instances or Grafana instances running on other clouds works.
1. Create connectors in Grafana to ensure that the Azure Monitor plugin is ready and that your Azure Database for MySQL instance is connected.
  - For Azure Grafana, Azure Monitor is built in. You will need to configure it to connect to your preferred Azure subscription.
  - For self-hosted instances or for Grafana instances running on other platforms, you can install the plugin by following the information in the article Azure Monitor plugin for Grafana.
1. Import the template JSON file.
1. Check that the correct Azure Database for MySQL flexible server displays in the breadcrumb trail at the top, and then verify that each widget/panel works properly.
 
