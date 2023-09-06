# Logging and monitoring

Code Engine integrates seamlessly with IBM Cloud Log Analysis and Monitoring services.

## View the logs for your application

When you work with Code Engine apps, jobs, or builds in the console with logging enabled, logs are forwarded to an IBM Log Analysis service where they are indexed, enabling full-text search through all generated messages and convenient querying based on specific fields.

1. Go to the list of projects at https://cloud.ibm.com/codeengine/projects.
1. Select the project you created previously.
1. Click **Applications** in the Summary and then select the application that you created previously.
1. From the **Overview** page for your application, click **Launch logging**.
   ![](images/50-launch-logging.png ':size=400')
1. When you launch logging, a new view opens for log data. Code Engine automatically sets log filters in Log Analysis that are scoped to the context of your application.
   ![](images/50-logging.png ':size=400')
1. Access your application by using its  application URL to generate more logging statements.

?> You can play with filters to scope the logs to a specific revision or a specific project. Refer to [this documentation](https://cloud.ibm.com/docs/codeengine?topic=codeengine-view-logs#view-logs-filters).

## View monitoring data for your application

You can use the IBM Cloud Monitoring service to monitor your Code Engine workloads. Code Engine forwards selected information about your workloads to Monitoring so that you can monitor specific metrics such as requests, revisions, and duration.

1. From the **Overview** page for the application, click **Launch monitoring**.
   ![](images/50-launch-monitoring.png ':size=400')
1. When you launch monitoring, the Code Engine monitoring dashboard opens. This dashboard is pre-configured with your Code Engine project.
   ![](images/50-monitoring.png ':size=400')
1. See the metrics on the Code Engine monitoring dashboard for your application. This dashboard includes a variety of metrics such as:
   * Number of concurrent requests per application
   * Total number of HTTP requests per application and revision
   * Number of job runs and their status

?> In addition to the pre-configured Code Engine monitoring dashboard, you can also [create your own custom dashboards](https://cloud.ibm.com/docs/codeengine?topic=codeengine-monitor-custom) to match your needs.

⇨ [Build from source](55-build-from-source.md)