# Considerations When Using Zeppelin on Amazon EMR<a name="zeppelin-considerations"></a>

+ Connect to Zeppelin using the same [SSH tunneling method](http://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-ssh-tunnel.html) to connect to other web servers on the master node\. Zeppelin server is found at port 8890\.

+ Zeppelin on Amazon EMR release versions 5\.0\.0 and later supports [Shiro authentication](https://zeppelin.apache.org/docs/latest/security/shiroauthentication.html)\.

+ Zeppelin on Amazon EMR release versions 5\.8\.0 and later supports using AWS Glue Data Catalog as the metastore for Spark SQL\. For more information, see [Using AWS Glue Data Catalog as the Metastore for Spark SQL\.](http://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-glue.html)

+ Zeppelin does not use some of the settings defined in your cluster’s `spark-defaults.conf` configuration file, even though it instructs YARN to allocate executors dynamically if you have set `spark.dynamicAllocation.enabled` to `true`\. You must set executor settings, such as memory and cores, using the Zeppelin **Interpreter** tab, and then restart the interpreter for them to be used\.

+ Zeppelin on Amazon EMR does not support the SparkR interpreter\.