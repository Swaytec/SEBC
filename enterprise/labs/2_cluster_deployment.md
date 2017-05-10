## [root@ip-172-31-42-246 java]# curl -u swaytec:cloudera 'http://localhost:7180/api/v2/cm/deployment'
```
{
  "timestamp" : "2017-05-10T04:33:55.258Z",
  "clusters" : [ {
    "name" : "Swaytec",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "784334848"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-03bab261f0797ca9d5dae383246b5b14",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "451hpi71lu2fa7ysikmm0h4tj"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-92b8d7b04cfd48821dfab0c31d6488c1",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "d682b03f-01ed-440e-9177-cb48434126ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "24vmmq4a4enzo53fqvgdhugwq"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-ec0fbeea55140f6bdcc473d8ae7b3acb",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "a3540c00-9047-45d7-a503-896cfc0354b2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9psyv9wufif3g0uze92uizst6"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "784334848"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "845511884"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "784334848"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "784334848"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "nIwbwSCJ03fnPpTQVZHGSZtCdq5k9l"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "f6QO4AEwOKmbiE0OBhIoPNWIDClhtz"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "hJO6dpQ3GbHsDknWA5hdX9mvot2twr"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-03bab261f0797ca9d5dae383246b5b14",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-267538da47e2c3a8ddba7804803a8de8",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "5872409a-ba54-4afa-a0cb-d3ce89264f09"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aj4hsstm6yxz7z23t1s798veo"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-92b8d7b04cfd48821dfab0c31d6488c1",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "d682b03f-01ed-440e-9177-cb48434126ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cr3563ivjl3n3dslkmq95u3vt"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-ec0fbeea55140f6bdcc473d8ae7b3acb",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "a3540c00-9047-45d7-a503-896cfc0354b2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "achne2j0lshb9wnb4oqrotyh8"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-f92a2cc6bf3450ab5123770902cd0671",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "ff135aec-f9a8-4b9f-9425-bad5dd16a8b5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8lv8ywx9c7ho0qkra1qd8oxpp"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-03bab261f0797ca9d5dae383246b5b14",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ausspvff49q7pfxeirycpq0of"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-ec0fbeea55140f6bdcc473d8ae7b3acb",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "a3540c00-9047-45d7-a503-896cfc0354b2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5kairffjlqjxhuz3xcbytxp57"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-03bab261f0797ca9d5dae383246b5b14",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8ef9u2qsc7r52mva2pxcsmlco"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-92b8d7b04cfd48821dfab0c31d6488c1",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "d682b03f-01ed-440e-9177-cb48434126ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8n1bg7r4jop4qa1gjhenldvdu"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-ec0fbeea55140f6bdcc473d8ae7b3acb",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "a3540c00-9047-45d7-a503-896cfc0354b2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cxwbi96xyod03uenn8yjt1fjl"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-03bab261f0797ca9d5dae383246b5b14",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "77"
          }, {
            "name" : "role_jceks_password",
            "value" : "87a3czihgsg4if199cjt2ztjo"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-ec0fbeea55140f6bdcc473d8ae7b3acb",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "a3540c00-9047-45d7-a503-896cfc0354b2"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "85"
          }, {
            "name" : "role_jceks_password",
            "value" : "dn4yqjkjo54dxjuqcxfzrfva1"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "784334848"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1600"
          }, {
            "name" : "rm_io_weight",
            "value" : "800"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "2307"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "784334848"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5250"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "84AYDfmoeSr3rgiUqxK3Tr6JpG5u6f"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-03bab261f0797ca9d5dae383246b5b14",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4znj5wacjqd6bmylm1jn9z98a"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-267538da47e2c3a8ddba7804803a8de8",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "5872409a-ba54-4afa-a0cb-d3ce89264f09"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3gih2978x6wjgkrn4hxcqvu6l"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-92b8d7b04cfd48821dfab0c31d6488c1",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "d682b03f-01ed-440e-9177-cb48434126ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6dlca19bkz092kl9gls101sf3"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-ec0fbeea55140f6bdcc473d8ae7b3acb",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "a3540c00-9047-45d7-a503-896cfc0354b2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9e97svoh7epkm59osk4d0b8bj"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-f92a2cc6bf3450ab5123770902cd0671",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "ff135aec-f9a8-4b9f-9425-bad5dd16a8b5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cu1nq7t3ez5q3k06dlut87hr0"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-03bab261f0797ca9d5dae383246b5b14",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "84"
          }, {
            "name" : "role_jceks_password",
            "value" : "bv39uyeqqakghjs8r91jo9xio"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "52428800"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "52428800"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "3"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "2056205107"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "346"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-42-246.us-west-2.compute.internal"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "password00"
        }, {
          "name" : "hive_metastore_database_user",
          "value" : "root"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-03bab261f0797ca9d5dae383246b5b14",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-267538da47e2c3a8ddba7804803a8de8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5872409a-ba54-4afa-a0cb-d3ce89264f09"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-92b8d7b04cfd48821dfab0c31d6488c1",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "d682b03f-01ed-440e-9177-cb48434126ca"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-ec0fbeea55140f6bdcc473d8ae7b3acb",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "a3540c00-9047-45d7-a503-896cfc0354b2"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-f92a2cc6bf3450ab5123770902cd0671",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "ff135aec-f9a8-4b9f-9425-bad5dd16a8b5"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-03bab261f0797ca9d5dae383246b5b14",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7h13emr9jajoa4we7q03qkgz8"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-03bab261f0797ca9d5dae383246b5b14",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "kom8hpmfi5ve3yvhek9zdmkp"
          } ]
        }
      } ],
      "displayName" : "Hive"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "a3540c00-9047-45d7-a503-896cfc0354b2",
    "ipAddress" : "172.31.32.150",
    "hostname" : "ip-172-31-32-150.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "d682b03f-01ed-440e-9177-cb48434126ca",
    "ipAddress" : "172.31.34.219",
    "hostname" : "ip-172-31-34-219.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "5872409a-ba54-4afa-a0cb-d3ce89264f09",
    "ipAddress" : "172.31.40.86",
    "hostname" : "ip-172-31-40-86.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "ff135aec-f9a8-4b9f-9425-bad5dd16a8b5",
    "ipAddress" : "172.31.41.39",
    "hostname" : "ip-172-31-41-39.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab",
    "ipAddress" : "172.31.42.246",
    "hostname" : "ip-172-31-42-246.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-03bab261f0797ca9d5dae383246b5b14",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "65cab1e616feac12b2c28278cd6d4467d38a85dc0bb8e3bd8c931b362432deff",
    "pwSalt" : 1722439537316209639,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-03bab261f0797ca9d5dae383246b5b14",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "af12cac4c46e2ed7329fb79e9eb5ff382c5e4848855bb83289ef65edf2eeb4ee",
    "pwSalt" : -561596178156036143,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-03bab261f0797ca9d5dae383246b5b14",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "a0599428aa20040ae75ea107ed9ec67ae5830d4282dd1e4ca30992d00dcc9e4c",
    "pwSalt" : -5212579121692261479,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-03bab261f0797ca9d5dae383246b5b14",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "de0e382c8312261c0bd5ee8a438eb979d578cd21e2fcabfc7019a0fbb51c001a",
    "pwSalt" : 410222310310389880,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "dc80d300a2cf638ef67d7692efc92d514ae19497d3a4b27f1a216333909a424d",
    "pwSalt" : 7433790090900787453,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "ab3ccce870187bf4c8d161da002c1b9659888be3b62a610fb95c6d557275b0b1",
    "pwSalt" : 1599492549746781854,
    "pwLogin" : true
  }, {
    "name" : "swaytec",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "9e1666b662fba3c60c5bed5dddc02fc6ab5b689575dc60d9bd145b21ce1b7d94",
    "pwSalt" : -2769109316232420116,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.9.0",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161006-1801",
    "gitHash" : "898a5e032c080e18833dfc58180761f6ef2ea351",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "784334848"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "784334848"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1020264448"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-42-246.us-west-2.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "reports"
        }, {
          "name" : "headlamp_database_password",
          "value" : "password00"
        }, {
          "name" : "headlamp_database_user",
          "value" : "root"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "784334848"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "784334848"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1020264448"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-03bab261f0797ca9d5dae383246b5b14",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6yzsc1t9x1ynv1g17ab90no1t"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-03bab261f0797ca9d5dae383246b5b14",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "b3d84p03g3eyvdnygxuu6jhvu"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-03bab261f0797ca9d5dae383246b5b14",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5up9yej8h9mgnxbevleh53qiv"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-03bab261f0797ca9d5dae383246b5b14",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2zmmd7qkcd177266xkca3cqtd"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-03bab261f0797ca9d5dae383246b5b14",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "0034a299-d3db-4461-93cb-e39c1930eeab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "divf6qsghsml65m866c2wfhkq"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/26/2012 19:20"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }

```