# Configuring Spark and Databricks

## Local Configuration
### Overview

This section provides guidance on configuring your local environment to use Spark with the GeoAnalytics Engine. The settings are based on [recommendations](https://developers.arcgis.com/geoanalytics/install/local_mode/) by the GeoAnalytics Engine team.

### Setup Commands

Launch `pyspark` and `geoanalytics` with specific configurations:

```bash
pyspark --jars C:\engine\geoanalytics.jar ^
        --py-files C:\engine\geoanalytics.zip ^
        --conf spark.plugins=com.esri.geoanalytics.Plugin ^
        --conf spark.serializer=org.apache.spark.serializer.KryoSerializer ^
        --conf spark.kryo.registrator=com.esri.geoanalytics.KryoRegistrator ^
        --conf spark.driver.memory=6g ^
        --conf spark.executor.memory=10g
```

### Configuration Details
- **JAR and ZIP Files**: Include necessary files for GeoANalytics functionality.
- **Plugin Configuration**: Directs Spark to use the GeoAnalytics plugin.
- **Serialization**: Utilizes Kryo serialization for performance optimization.
- **Driver Memory**: Increased from 5G to 6G to prevent out-of-memory errors during complex operations involving extensive data aggregation, ensuring smooth application performance without overusing memory.
- **Executor Memory**: Set to 10G. In local mode, this setting does not really influence performance because the executor runs within the same JVM as the driver. However, specifying this setting ensures that, when deployed in a distributed environment, each executor has sufficient memory to handle large datasets efficiently without frequent spilling to disk. This inclusion helps maintain consistency across different deployment scenarios.


## Databricks Configuration
### Overview
The Databricks environment is configured to optimize resource allocation dynamically according to the workload. Minimal adjustments were needed in the Databricks environment. Here are the essential settings used:
- **Memory**: 14 GB
- **Cores**: 4
- **Workers**: Dynamically adjusts between 2 to 8 based on the workload.

Databricks is set to dynamically adjust the number of workers, scaling between 2 and 8 as needed. This feature allows the cluster to efficiently manage resources by scaling up during high demand periods and scaling down during low activity times. This configuration summary provides guidelines based on the general setup described. For detailed instructions on implementing these settings, refer to the [Databricks documentation](https://docs.databricks.com/) or consult with your IT team to align these settings with your specific operational requirements.
