

.. _Amazon CloudWatch Metrics, Namespaces, and Dimensions Reference: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html
.. _Statistics: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#Statistic
.. _Permissions and Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/PermissionsAndPolicies.html


**********
CloudWatch
**********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: CloudWatch.Client

  A low-level client representing Amazon CloudWatch::

    
    import boto3
    
    client = boto3.client('cloudwatch')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`delete_alarms`

  
  *   :py:meth:`describe_alarm_history`

  
  *   :py:meth:`describe_alarms`

  
  *   :py:meth:`describe_alarms_for_metric`

  
  *   :py:meth:`disable_alarm_actions`

  
  *   :py:meth:`enable_alarm_actions`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_metric_statistics`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_metrics`

  
  *   :py:meth:`put_metric_alarm`

  
  *   :py:meth:`put_metric_data`

  
  *   :py:meth:`set_alarm_state`

  

  .. py:method:: can_paginate(operation_name)

        
    Check if an operation can be paginated.
    
    :type operation_name: string
    :param operation_name: The operation name.  This is the same name
        as the method name on the client.  For example, if the
        method name is ``create_foo``, and you'd normally invoke the
        operation as ``client.create_foo(**kwargs)``, if the
        ``create_foo`` operation can be paginated, you can use the
        call ``client.get_paginator("create_foo")``.
    
    :return: ``True`` if the operation can be paginated,
        ``False`` otherwise.


  .. py:method:: delete_alarms(**kwargs)

    

    Deletes all specified alarms. In the event of an error, no alarms are deleted.

    

    **Request Syntax** 
    ::

      response = client.delete_alarms(
          AlarmNames=[
              'string',
          ]
      )
    :type AlarmNames: list
    :param AlarmNames: **[REQUIRED]** 

      A list of alarms to be deleted.

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: describe_alarm_history(**kwargs)

    

    Retrieves history for the specified alarm. Filter alarms by date range or item type. If an alarm name is not specified, Amazon CloudWatch returns histories for all of the owner's alarms.

     

    .. note::

       

      Amazon CloudWatch retains the history of an alarm for two weeks, whether or not you delete the alarm.

       

    

    **Request Syntax** 
    ::

      response = client.describe_alarm_history(
          AlarmName='string',
          HistoryItemType='ConfigurationUpdate'|'StateUpdate'|'Action',
          StartDate=datetime(2015, 1, 1),
          EndDate=datetime(2015, 1, 1),
          MaxRecords=123,
          NextToken='string'
      )
    :type AlarmName: string
    :param AlarmName: 

      The name of the alarm.

      

    
    :type HistoryItemType: string
    :param HistoryItemType: 

      The type of alarm histories to retrieve.

      

    
    :type StartDate: datetime
    :param StartDate: 

      The starting date to retrieve alarm history.

      

    
    :type EndDate: datetime
    :param EndDate: 

      The ending date to retrieve alarm history.

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of alarm history records to retrieve.

      

    
    :type NextToken: string
    :param NextToken: 

      The token returned by a previous call to indicate that there is more data available.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AlarmHistoryItems': [
                {
                    'AlarmName': 'string',
                    'Timestamp': datetime(2015, 1, 1),
                    'HistoryItemType': 'ConfigurationUpdate'|'StateUpdate'|'Action',
                    'HistorySummary': 'string',
                    'HistoryData': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  DescribeAlarmHistory . 

        
        

        - **AlarmHistoryItems** *(list) --* 

          A list of alarm histories in JSON format.

          
          

          - *(dict) --* 

            The ``AlarmHistoryItem`` data type contains descriptive information about the history of a specific alarm. If you call  DescribeAlarmHistory , Amazon CloudWatch returns this data type as part of the DescribeAlarmHistoryResult data type. 

            
            

            - **AlarmName** *(string) --* 

              The descriptive name for the alarm.

              
            

            - **Timestamp** *(datetime) --* 

              The time stamp for the alarm history item.

              
            

            - **HistoryItemType** *(string) --* 

              The type of alarm history item.

              
            

            - **HistorySummary** *(string) --* 

              A human-readable summary of the alarm history.

              
            

            - **HistoryData** *(string) --* 

              Machine-readable data about the alarm in JSON format.

              
        
      
        

        - **NextToken** *(string) --* 

          A string that marks the start of the next batch of returned results.

          
    

  .. py:method:: describe_alarms(**kwargs)

    

    Retrieves alarms with the specified names. If no name is specified, all alarms for the user are returned. Alarms can be retrieved by using only a prefix for the alarm name, the alarm state, or a prefix for any action.

    

    **Request Syntax** 
    ::

      response = client.describe_alarms(
          AlarmNames=[
              'string',
          ],
          AlarmNamePrefix='string',
          StateValue='OK'|'ALARM'|'INSUFFICIENT_DATA',
          ActionPrefix='string',
          MaxRecords=123,
          NextToken='string'
      )
    :type AlarmNames: list
    :param AlarmNames: 

      A list of alarm names to retrieve information for.

      

    
      - *(string) --* 

      
  
    :type AlarmNamePrefix: string
    :param AlarmNamePrefix: 

      The alarm name prefix. ``AlarmNames`` cannot be specified if this parameter is specified.

      

    
    :type StateValue: string
    :param StateValue: 

      The state value to be used in matching alarms.

      

    
    :type ActionPrefix: string
    :param ActionPrefix: 

      The action name prefix.

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of alarm descriptions to retrieve.

      

    
    :type NextToken: string
    :param NextToken: 

      The token returned by a previous call to indicate that there is more data available.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MetricAlarms': [
                {
                    'AlarmName': 'string',
                    'AlarmArn': 'string',
                    'AlarmDescription': 'string',
                    'AlarmConfigurationUpdatedTimestamp': datetime(2015, 1, 1),
                    'ActionsEnabled': True|False,
                    'OKActions': [
                        'string',
                    ],
                    'AlarmActions': [
                        'string',
                    ],
                    'InsufficientDataActions': [
                        'string',
                    ],
                    'StateValue': 'OK'|'ALARM'|'INSUFFICIENT_DATA',
                    'StateReason': 'string',
                    'StateReasonData': 'string',
                    'StateUpdatedTimestamp': datetime(2015, 1, 1),
                    'MetricName': 'string',
                    'Namespace': 'string',
                    'Statistic': 'SampleCount'|'Average'|'Sum'|'Minimum'|'Maximum',
                    'Dimensions': [
                        {
                            'Name': 'string',
                            'Value': 'string'
                        },
                    ],
                    'Period': 123,
                    'Unit': 'Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None',
                    'EvaluationPeriods': 123,
                    'Threshold': 123.0,
                    'ComparisonOperator': 'GreaterThanOrEqualToThreshold'|'GreaterThanThreshold'|'LessThanThreshold'|'LessThanOrEqualToThreshold'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  DescribeAlarms .

        
        

        - **MetricAlarms** *(list) --* 

          A list of information for the specified alarms.

          
          

          - *(dict) --* 

            The  MetricAlarm data type represents an alarm. You can use  PutMetricAlarm to create or update an alarm. 

            
            

            - **AlarmName** *(string) --* 

              The name of the alarm.

              
            

            - **AlarmArn** *(string) --* 

              The Amazon Resource Name (ARN) of the alarm.

              
            

            - **AlarmDescription** *(string) --* 

              The description for the alarm.

              
            

            - **AlarmConfigurationUpdatedTimestamp** *(datetime) --* 

              The time stamp of the last update to the alarm configuration.

              
            

            - **ActionsEnabled** *(boolean) --* 

              Indicates whether actions should be executed during any changes to the alarm's state.

              
            

            - **OKActions** *(list) --* 

              The list of actions to execute when this alarm transitions into an ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

              
              

              - *(string) --* 
          
            

            - **AlarmActions** *(list) --* 

              The list of actions to execute when this alarm transitions into an ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

              
              

              - *(string) --* 
          
            

            - **InsufficientDataActions** *(list) --* 

              The list of actions to execute when this alarm transitions into an ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

               

              .. warning::

                 

                The current WSDL lists this attribute as ``UnknownActions`` .

                 

              
              

              - *(string) --* 
          
            

            - **StateValue** *(string) --* 

              The state value for the alarm.

              
            

            - **StateReason** *(string) --* 

              A human-readable explanation for the alarm's state.

              
            

            - **StateReasonData** *(string) --* 

              An explanation for the alarm's state in machine-readable JSON format

              
            

            - **StateUpdatedTimestamp** *(datetime) --* 

              The time stamp of the last update to the alarm's state.

              
            

            - **MetricName** *(string) --* 

              The name of the alarm's metric.

              
            

            - **Namespace** *(string) --* 

              The namespace of alarm's associated metric.

              
            

            - **Statistic** *(string) --* 

              The statistic to apply to the alarm's associated metric.

              
            

            - **Dimensions** *(list) --* 

              The list of dimensions associated with the alarm's associated metric.

              
              

              - *(dict) --* 

                The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

                 

                For examples that use one or more dimensions, see  PutMetricData .

                
                

                - **Name** *(string) --* 

                  The name of the dimension.

                  
                

                - **Value** *(string) --* 

                  The value representing the dimension measurement

                  
            
          
            

            - **Period** *(integer) --* 

              The period in seconds over which the statistic is applied.

              
            

            - **Unit** *(string) --* 

              The unit of the alarm's associated metric.

              
            

            - **EvaluationPeriods** *(integer) --* 

              The number of periods over which data is compared to the specified threshold.

              
            

            - **Threshold** *(float) --* 

              The value against which the specified statistic is compared.

              
            

            - **ComparisonOperator** *(string) --* 

              The arithmetic operation to use when comparing the specified ``Statistic`` and ``Threshold`` . The specified ``Statistic`` value is used as the first operand. 

              
        
      
        

        - **NextToken** *(string) --* 

          A string that marks the start of the next batch of returned results.

          
    

  .. py:method:: describe_alarms_for_metric(**kwargs)

    

    Retrieves all alarms for a single metric. Specify a statistic, period, or unit to filter the set of alarms further.

    

    **Request Syntax** 
    ::

      response = client.describe_alarms_for_metric(
          MetricName='string',
          Namespace='string',
          Statistic='SampleCount'|'Average'|'Sum'|'Minimum'|'Maximum',
          Dimensions=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ],
          Period=123,
          Unit='Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None'
      )
    :type MetricName: string
    :param MetricName: **[REQUIRED]** 

      The name of the metric.

      

    
    :type Namespace: string
    :param Namespace: **[REQUIRED]** 

      The namespace of the metric.

      

    
    :type Statistic: string
    :param Statistic: 

      The statistic for the metric.

      

    
    :type Dimensions: list
    :param Dimensions: 

      The list of dimensions associated with the metric. If the metric has any associated dimensions, you must specify them in order for the DescribeAlarmsForMetric to succeed.

      

    
      - *(dict) --* 

        The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

         

        For examples that use one or more dimensions, see  PutMetricData .

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the dimension.

          

        
        - **Value** *(string) --* **[REQUIRED]** 

          The value representing the dimension measurement

          

        
      
  
    :type Period: integer
    :param Period: 

      The period in seconds over which the statistic is applied.

      

    
    :type Unit: string
    :param Unit: 

      The unit for the metric.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MetricAlarms': [
                {
                    'AlarmName': 'string',
                    'AlarmArn': 'string',
                    'AlarmDescription': 'string',
                    'AlarmConfigurationUpdatedTimestamp': datetime(2015, 1, 1),
                    'ActionsEnabled': True|False,
                    'OKActions': [
                        'string',
                    ],
                    'AlarmActions': [
                        'string',
                    ],
                    'InsufficientDataActions': [
                        'string',
                    ],
                    'StateValue': 'OK'|'ALARM'|'INSUFFICIENT_DATA',
                    'StateReason': 'string',
                    'StateReasonData': 'string',
                    'StateUpdatedTimestamp': datetime(2015, 1, 1),
                    'MetricName': 'string',
                    'Namespace': 'string',
                    'Statistic': 'SampleCount'|'Average'|'Sum'|'Minimum'|'Maximum',
                    'Dimensions': [
                        {
                            'Name': 'string',
                            'Value': 'string'
                        },
                    ],
                    'Period': 123,
                    'Unit': 'Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None',
                    'EvaluationPeriods': 123,
                    'Threshold': 123.0,
                    'ComparisonOperator': 'GreaterThanOrEqualToThreshold'|'GreaterThanThreshold'|'LessThanThreshold'|'LessThanOrEqualToThreshold'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  DescribeAlarmsForMetric . 

        
        

        - **MetricAlarms** *(list) --* 

          A list of information for each alarm with the specified metric.

          
          

          - *(dict) --* 

            The  MetricAlarm data type represents an alarm. You can use  PutMetricAlarm to create or update an alarm. 

            
            

            - **AlarmName** *(string) --* 

              The name of the alarm.

              
            

            - **AlarmArn** *(string) --* 

              The Amazon Resource Name (ARN) of the alarm.

              
            

            - **AlarmDescription** *(string) --* 

              The description for the alarm.

              
            

            - **AlarmConfigurationUpdatedTimestamp** *(datetime) --* 

              The time stamp of the last update to the alarm configuration.

              
            

            - **ActionsEnabled** *(boolean) --* 

              Indicates whether actions should be executed during any changes to the alarm's state.

              
            

            - **OKActions** *(list) --* 

              The list of actions to execute when this alarm transitions into an ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

              
              

              - *(string) --* 
          
            

            - **AlarmActions** *(list) --* 

              The list of actions to execute when this alarm transitions into an ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

              
              

              - *(string) --* 
          
            

            - **InsufficientDataActions** *(list) --* 

              The list of actions to execute when this alarm transitions into an ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

               

              .. warning::

                 

                The current WSDL lists this attribute as ``UnknownActions`` .

                 

              
              

              - *(string) --* 
          
            

            - **StateValue** *(string) --* 

              The state value for the alarm.

              
            

            - **StateReason** *(string) --* 

              A human-readable explanation for the alarm's state.

              
            

            - **StateReasonData** *(string) --* 

              An explanation for the alarm's state in machine-readable JSON format

              
            

            - **StateUpdatedTimestamp** *(datetime) --* 

              The time stamp of the last update to the alarm's state.

              
            

            - **MetricName** *(string) --* 

              The name of the alarm's metric.

              
            

            - **Namespace** *(string) --* 

              The namespace of alarm's associated metric.

              
            

            - **Statistic** *(string) --* 

              The statistic to apply to the alarm's associated metric.

              
            

            - **Dimensions** *(list) --* 

              The list of dimensions associated with the alarm's associated metric.

              
              

              - *(dict) --* 

                The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

                 

                For examples that use one or more dimensions, see  PutMetricData .

                
                

                - **Name** *(string) --* 

                  The name of the dimension.

                  
                

                - **Value** *(string) --* 

                  The value representing the dimension measurement

                  
            
          
            

            - **Period** *(integer) --* 

              The period in seconds over which the statistic is applied.

              
            

            - **Unit** *(string) --* 

              The unit of the alarm's associated metric.

              
            

            - **EvaluationPeriods** *(integer) --* 

              The number of periods over which data is compared to the specified threshold.

              
            

            - **Threshold** *(float) --* 

              The value against which the specified statistic is compared.

              
            

            - **ComparisonOperator** *(string) --* 

              The arithmetic operation to use when comparing the specified ``Statistic`` and ``Threshold`` . The specified ``Statistic`` value is used as the first operand. 

              
        
      
    

  .. py:method:: disable_alarm_actions(**kwargs)

    

    Disables actions for the specified alarms. When an alarm's actions are disabled the alarm's state may change, but none of the alarm's actions will execute.

    

    **Request Syntax** 
    ::

      response = client.disable_alarm_actions(
          AlarmNames=[
              'string',
          ]
      )
    :type AlarmNames: list
    :param AlarmNames: **[REQUIRED]** 

      The names of the alarms to disable actions for.

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: enable_alarm_actions(**kwargs)

    

    Enables actions for the specified alarms.

    

    **Request Syntax** 
    ::

      response = client.enable_alarm_actions(
          AlarmNames=[
              'string',
          ]
      )
    :type AlarmNames: list
    :param AlarmNames: **[REQUIRED]** 

      The names of the alarms to enable actions for.

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: generate_presigned_url(ClientMethod, Params=None, ExpiresIn=3600, HttpMethod=None)

        
    Generate a presigned url given a client, its method, and arguments
    
    :type ClientMethod: string
    :param ClientMethod: The client method to presign for
    
    :type Params: dict
    :param Params: The parameters normally passed to
        ``ClientMethod``.
    
    :type ExpiresIn: int
    :param ExpiresIn: The number of seconds the presigned url is valid
        for. By default it expires in an hour (3600 seconds)
    
    :type HttpMethod: string
    :param HttpMethod: The http method to use on the generated url. By
        default, the http method is whatever is used in the method's model.
    
    :returns: The presigned url


  .. py:method:: get_metric_statistics(**kwargs)

    

    Gets statistics for the specified metric.

     

    The maximum number of data points that can be queried is 50,850, whereas the maximum number of data points returned from a single ``GetMetricStatistics`` request is 1,440. If you make a request that generates more than 1,440 data points, Amazon CloudWatch returns an error. In such a case, you can alter the request by narrowing the specified time range or increasing the specified period. A period can be as short as one minute (60 seconds) or as long as one day (86,400 seconds). Alternatively, you can make multiple requests across adjacent time ranges. ``GetMetricStatistics`` does not return the data in chronological order. 

     

    Amazon CloudWatch aggregates data points based on the length of the ``period`` that you specify. For example, if you request statistics with a one-minute granularity, Amazon CloudWatch aggregates data points with time stamps that fall within the same one-minute period. In such a case, the data points queried can greatly outnumber the data points returned. 

     

    The following examples show various statistics allowed by the data point query maximum of 50,850 when you call ``GetMetricStatistics`` on Amazon EC2 instances with detailed (one-minute) monitoring enabled: 

     

     
    * Statistics for up to 400 instances for a span of one hour 
     
    * Statistics for up to 35 instances over a span of 24 hours 
     
    * Statistics for up to 2 instances over a span of 2 weeks 
     

     

    For information about the namespace, metric names, and dimensions that other Amazon Web Services products use to send metrics to CloudWatch, go to `Amazon CloudWatch Metrics, Namespaces, and Dimensions Reference`_ in the *Amazon CloudWatch Developer Guide* . 

    

    **Request Syntax** 
    ::

      response = client.get_metric_statistics(
          Namespace='string',
          MetricName='string',
          Dimensions=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ],
          StartTime=datetime(2015, 1, 1),
          EndTime=datetime(2015, 1, 1),
          Period=123,
          Statistics=[
              'SampleCount'|'Average'|'Sum'|'Minimum'|'Maximum',
          ],
          Unit='Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None'
      )
    :type Namespace: string
    :param Namespace: **[REQUIRED]** 

      The namespace of the metric, with or without spaces.

      

    
    :type MetricName: string
    :param MetricName: **[REQUIRED]** 

      The name of the metric, with or without spaces.

      

    
    :type Dimensions: list
    :param Dimensions: 

      A list of dimensions describing qualities of the metric.

      

    
      - *(dict) --* 

        The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

         

        For examples that use one or more dimensions, see  PutMetricData .

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the dimension.

          

        
        - **Value** *(string) --* **[REQUIRED]** 

          The value representing the dimension measurement

          

        
      
  
    :type StartTime: datetime
    :param StartTime: **[REQUIRED]** 

      The time stamp to use for determining the first datapoint to return. The value specified is inclusive; results include datapoints with the time stamp specified. The time stamp must be in ISO 8601 UTC format (e.g., 2014-09-03T23:00:00Z).

       

      .. note::

         

        The specified start time is rounded down to the nearest value. Datapoints are returned for start times up to two weeks in the past. Specified start times that are more than two weeks in the past will not return datapoints for metrics that are older than two weeks.

         

        Data that is timestamped 24 hours or more in the past may take in excess of 48 hours to become available from submission time using ``GetMetricStatistics`` .

         

      

    
    :type EndTime: datetime
    :param EndTime: **[REQUIRED]** 

      The time stamp to use for determining the last datapoint to return. The value specified is exclusive; results will include datapoints up to the time stamp specified. The time stamp must be in ISO 8601 UTC format (e.g., 2014-09-03T23:00:00Z).

      

    
    :type Period: integer
    :param Period: **[REQUIRED]** 

      The granularity, in seconds, of the returned datapoints. A ``Period`` can be as short as one minute (60 seconds) or as long as one day (86,400 seconds), and must be a multiple of 60. The default value is 60. 

      

    
    :type Statistics: list
    :param Statistics: **[REQUIRED]** 

      The metric statistics to return. For information about specific statistics returned by GetMetricStatistics, see `Statistics`_ in the *Amazon CloudWatch Developer Guide* . 

      

    
      - *(string) --* 

      
  
    :type Unit: string
    :param Unit: 

      The specific unit for a given metric. Metrics may be reported in multiple units. Not supplying a unit results in all units being returned. If the metric only ever reports one unit, specifying a unit will have no effect.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Label': 'string',
            'Datapoints': [
                {
                    'Timestamp': datetime(2015, 1, 1),
                    'SampleCount': 123.0,
                    'Average': 123.0,
                    'Sum': 123.0,
                    'Minimum': 123.0,
                    'Maximum': 123.0,
                    'Unit': 'Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  GetMetricStatistics . 

        
        

        - **Label** *(string) --* 

          A label describing the specified metric.

          
        

        - **Datapoints** *(list) --* 

          The datapoints for the specified metric.

          
          

          - *(dict) --* 

            The ``Datapoint`` data type encapsulates the statistical data that Amazon CloudWatch computes from metric data. 

            
            

            - **Timestamp** *(datetime) --* 

              The time stamp used for the datapoint.

              
            

            - **SampleCount** *(float) --* 

              The number of metric values that contributed to the aggregate value of this datapoint.

              
            

            - **Average** *(float) --* 

              The average of metric values that correspond to the datapoint.

              
            

            - **Sum** *(float) --* 

              The sum of metric values used for the datapoint.

              
            

            - **Minimum** *(float) --* 

              The minimum metric value used for the datapoint.

              
            

            - **Maximum** *(float) --* 

              The maximum of the metric value used for the datapoint.

              
            

            - **Unit** *(string) --* 

              The standard unit used for the datapoint.

              
        
      
    

  .. py:method:: get_paginator(operation_name)

        
    Create a paginator for an operation.
    
    :type operation_name: string
    :param operation_name: The operation name.  This is the same name
        as the method name on the client.  For example, if the
        method name is ``create_foo``, and you'd normally invoke the
        operation as ``client.create_foo(**kwargs)``, if the
        ``create_foo`` operation can be paginated, you can use the
        call ``client.get_paginator("create_foo")``.
    
    :raise OperationNotPageableError: Raised if the operation is not
        pageable.  You can use the ``client.can_paginate`` method to
        check if an operation is pageable.
    
    :rtype: L{botocore.paginate.Paginator}
    :return: A paginator object.


  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: list_metrics(**kwargs)

    

    Returns a list of valid metrics stored for the AWS account owner. Returned metrics can be used with  GetMetricStatistics to obtain statistical data for a given metric. 

     

    .. note::

       

      Up to 500 results are returned for any one call. To retrieve further results, use returned ``NextToken`` values with subsequent ``ListMetrics`` operations.

       

     

    .. note::

       

      If you create a metric with  PutMetricData , allow up to fifteen minutes for the metric to appear in calls to ``ListMetrics`` . Statistics about the metric, however, are available sooner using  GetMetricStatistics .

       

    

    **Request Syntax** 
    ::

      response = client.list_metrics(
          Namespace='string',
          MetricName='string',
          Dimensions=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ],
          NextToken='string'
      )
    :type Namespace: string
    :param Namespace: 

      The namespace to filter against.

      

    
    :type MetricName: string
    :param MetricName: 

      The name of the metric to filter against.

      

    
    :type Dimensions: list
    :param Dimensions: 

      A list of dimensions to filter against.

      

    
      - *(dict) --* 

        The ``DimensionFilter`` data type is used to filter  ListMetrics results. 

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The dimension name to be matched.

          

        
        - **Value** *(string) --* 

          The value of the dimension to be matched.

           

          .. note::

             

            Specifying a ``Name`` without specifying a ``Value`` returns all values associated with that ``Name`` .

             

          

        
      
  
    :type NextToken: string
    :param NextToken: 

      The token returned by a previous call to indicate that there is more data available.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Metrics': [
                {
                    'Namespace': 'string',
                    'MetricName': 'string',
                    'Dimensions': [
                        {
                            'Name': 'string',
                            'Value': 'string'
                        },
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  ListMetrics . 

        
        

        - **Metrics** *(list) --* 

          A list of metrics used to generate statistics for an AWS account.

          
          

          - *(dict) --* 

            The ``Metric`` data type contains information about a specific metric. If you call  ListMetrics , Amazon CloudWatch returns information contained by this data type. 

             

            The example in the Examples section publishes two metrics named buffers and latency. Both metrics are in the examples namespace. Both metrics have two dimensions, InstanceID and InstanceType.

            
            

            - **Namespace** *(string) --* 

              The namespace of the metric.

              
            

            - **MetricName** *(string) --* 

              The name of the metric.

              
            

            - **Dimensions** *(list) --* 

              A list of dimensions associated with the metric.

              
              

              - *(dict) --* 

                The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

                 

                For examples that use one or more dimensions, see  PutMetricData .

                
                

                - **Name** *(string) --* 

                  The name of the dimension.

                  
                

                - **Value** *(string) --* 

                  The value representing the dimension measurement

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          A string that marks the start of the next batch of returned results.

          
    

  .. py:method:: put_metric_alarm(**kwargs)

    

    Creates or updates an alarm and associates it with the specified Amazon CloudWatch metric. Optionally, this operation can associate one or more Amazon SNS resources with the alarm.

     

    When this operation creates an alarm, the alarm state is immediately set to ``INSUFFICIENT_DATA`` . The alarm is evaluated and its ``StateValue`` is set appropriately. Any actions associated with the ``StateValue`` are then executed. 

     

    .. note::

       

      When updating an existing alarm, its ``StateValue`` is left unchanged, but it completely overwrites the alarm's previous configuration.

       

     

    .. note::

       

      If you are using an AWS Identity and Access Management (IAM) account to create or modify an alarm, you must have the following Amazon EC2 permissions:

       

       
      * ``ec2:DescribeInstanceStatus`` and ``ec2:DescribeInstances`` for all alarms on Amazon EC2 instance status metrics. 
       
      * ``ec2:StopInstances`` for alarms with stop actions. 
       
      * ``ec2:TerminateInstances`` for alarms with terminate actions. 
       
      * ``ec2:DescribeInstanceRecoveryAttribute`` , and ``ec2:RecoverInstances`` for alarms with recover actions. 
       

       

      If you have read/write permissions for Amazon CloudWatch but not for Amazon EC2, you can still create an alarm but the stop or terminate actions won't be performed on the Amazon EC2 instance. However, if you are later granted permission to use the associated Amazon EC2 APIs, the alarm actions you created earlier will be performed. For more information about IAM permissions, see `Permissions and Policies`_ in *Using IAM* .

       

      If you are using an IAM role (e.g., an Amazon EC2 instance profile), you cannot stop or terminate the instance using alarm actions. However, you can still see the alarm state and perform any other actions such as Amazon SNS notifications or Auto Scaling policies.

       

      If you are using temporary security credentials granted using the AWS Security Token Service (AWS STS), you cannot stop or terminate an Amazon EC2 instance using alarm actions.

       

    

    **Request Syntax** 
    ::

      response = client.put_metric_alarm(
          AlarmName='string',
          AlarmDescription='string',
          ActionsEnabled=True|False,
          OKActions=[
              'string',
          ],
          AlarmActions=[
              'string',
          ],
          InsufficientDataActions=[
              'string',
          ],
          MetricName='string',
          Namespace='string',
          Statistic='SampleCount'|'Average'|'Sum'|'Minimum'|'Maximum',
          Dimensions=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ],
          Period=123,
          Unit='Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None',
          EvaluationPeriods=123,
          Threshold=123.0,
          ComparisonOperator='GreaterThanOrEqualToThreshold'|'GreaterThanThreshold'|'LessThanThreshold'|'LessThanOrEqualToThreshold'
      )
    :type AlarmName: string
    :param AlarmName: **[REQUIRED]** 

      The descriptive name for the alarm. This name must be unique within the user's AWS account

      

    
    :type AlarmDescription: string
    :param AlarmDescription: 

      The description for the alarm.

      

    
    :type ActionsEnabled: boolean
    :param ActionsEnabled: 

      Indicates whether or not actions should be executed during any changes to the alarm's state.

      

    
    :type OKActions: list
    :param OKActions: 

      The list of actions to execute when this alarm transitions into an ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

       

      Valid Values: arn:aws:automate:*region (e.g., us-east-1)* :ec2:stop | arn:aws:automate:*region (e.g., us-east-1)* :ec2:terminate | arn:aws:automate:*region (e.g., us-east-1)* :ec2:recover

       

      Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

       

       **Note:** You must create at least one stop, terminate, or reboot alarm using the Amazon EC2 or CloudWatch console to create the **EC2ActionsAccess** IAM role for the first time. After this IAM role is created, you can create stop, terminate, or reboot alarms using the CLI.

      

    
      - *(string) --* 

      
  
    :type AlarmActions: list
    :param AlarmActions: 

      The list of actions to execute when this alarm transitions into an ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

       

      Valid Values: arn:aws:automate:*region (e.g., us-east-1)* :ec2:stop | arn:aws:automate:*region (e.g., us-east-1)* :ec2:terminate | arn:aws:automate:*region (e.g., us-east-1)* :ec2:recover

       

      Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

       

       **Note:** You must create at least one stop, terminate, or reboot alarm using the Amazon EC2 or CloudWatch console to create the **EC2ActionsAccess** IAM role for the first time. After this IAM role is created, you can create stop, terminate, or reboot alarms using the CLI.

      

    
      - *(string) --* 

      
  
    :type InsufficientDataActions: list
    :param InsufficientDataActions: 

      The list of actions to execute when this alarm transitions into an ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

       

      Valid Values: arn:aws:automate:*region (e.g., us-east-1)* :ec2:stop | arn:aws:automate:*region (e.g., us-east-1)* :ec2:terminate | arn:aws:automate:*region (e.g., us-east-1)* :ec2:recover

       

      Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

       

       **Note:** You must create at least one stop, terminate, or reboot alarm using the Amazon EC2 or CloudWatch console to create the **EC2ActionsAccess** IAM role for the first time. After this IAM role is created, you can create stop, terminate, or reboot alarms using the CLI.

      

    
      - *(string) --* 

      
  
    :type MetricName: string
    :param MetricName: **[REQUIRED]** 

      The name for the alarm's associated metric.

      

    
    :type Namespace: string
    :param Namespace: **[REQUIRED]** 

      The namespace for the alarm's associated metric.

      

    
    :type Statistic: string
    :param Statistic: **[REQUIRED]** 

      The statistic to apply to the alarm's associated metric.

      

    
    :type Dimensions: list
    :param Dimensions: 

      The dimensions for the alarm's associated metric.

      

    
      - *(dict) --* 

        The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

         

        For examples that use one or more dimensions, see  PutMetricData .

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the dimension.

          

        
        - **Value** *(string) --* **[REQUIRED]** 

          The value representing the dimension measurement

          

        
      
  
    :type Period: integer
    :param Period: **[REQUIRED]** 

      The period in seconds over which the specified statistic is applied.

      

    
    :type Unit: string
    :param Unit: 

      The statistic's unit of measure. For example, the units for the Amazon EC2 NetworkIn metric are Bytes because NetworkIn tracks the number of bytes that an instance receives on all network interfaces. You can also specify a unit when you create a custom metric. Units help provide conceptual meaning to your data. Metric data points that specify a unit of measure, such as Percent, are aggregated separately.

       

       **Note:** If you specify a unit, you must use a unit that is appropriate for the metric. Otherwise, this can cause an Amazon CloudWatch alarm to get stuck in the INSUFFICIENT DATA state. 

      

    
    :type EvaluationPeriods: integer
    :param EvaluationPeriods: **[REQUIRED]** 

      The number of periods over which data is compared to the specified threshold.

      

    
    :type Threshold: float
    :param Threshold: **[REQUIRED]** 

      The value against which the specified statistic is compared.

      

    
    :type ComparisonOperator: string
    :param ComparisonOperator: **[REQUIRED]** 

      The arithmetic operation to use when comparing the specified ``Statistic`` and ``Threshold`` . The specified ``Statistic`` value is used as the first operand. 

      

    
    
    :returns: None

  .. py:method:: put_metric_data(**kwargs)

    

    Publishes metric data points to Amazon CloudWatch. Amazon CloudWatch associates the data points with the specified metric. If the specified metric does not exist, Amazon CloudWatch creates the metric. When Amazon CloudWatch creates a metric, it can take up to fifteen minutes for the metric to appear in calls to  ListMetrics . 

     

    Each ``PutMetricData`` request is limited to 8 KB in size for HTTP GET requests and is limited to 40 KB in size for HTTP POST requests. 

     

    .. warning::

       

      Although the ``Value`` parameter accepts numbers of type ``Double`` , Amazon CloudWatch rejects values that are either too small or too large. Values must be in the range of 8.515920e-109 to 1.174271e+108 (Base 10) or 2e-360 to 2e360 (Base 2). In addition, special values (e.g., NaN, +Infinity, -Infinity) are not supported.

       

     

    Data that is timestamped 24 hours or more in the past may take in excess of 48 hours to become available from submission time using ``GetMetricStatistics`` .

    

    **Request Syntax** 
    ::

      response = client.put_metric_data(
          Namespace='string',
          MetricData=[
              {
                  'MetricName': 'string',
                  'Dimensions': [
                      {
                          'Name': 'string',
                          'Value': 'string'
                      },
                  ],
                  'Timestamp': datetime(2015, 1, 1),
                  'Value': 123.0,
                  'StatisticValues': {
                      'SampleCount': 123.0,
                      'Sum': 123.0,
                      'Minimum': 123.0,
                      'Maximum': 123.0
                  },
                  'Unit': 'Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None'
              },
          ]
      )
    :type Namespace: string
    :param Namespace: **[REQUIRED]** 

      The namespace for the metric data.

       

      .. note::

         

        You cannot specify a namespace that begins with "AWS/". Namespaces that begin with "AWS/" are reserved for other Amazon Web Services products that send metrics to Amazon CloudWatch.

         

      

    
    :type MetricData: list
    :param MetricData: **[REQUIRED]** 

      A list of data describing the metric.

      

    
      - *(dict) --* 

        The ``MetricDatum`` data type encapsulates the information sent with  PutMetricData to either create a new metric or add new values to be aggregated into an existing metric. 

        

      
        - **MetricName** *(string) --* **[REQUIRED]** 

          The name of the metric.

          

        
        - **Dimensions** *(list) --* 

          A list of dimensions associated with the metric. Note, when using the Dimensions value in a query, you need to append .member.N to it (e.g., Dimensions.member.N).

          

        
          - *(dict) --* 

            The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

             

            For examples that use one or more dimensions, see  PutMetricData .

            

          
            - **Name** *(string) --* **[REQUIRED]** 

              The name of the dimension.

              

            
            - **Value** *(string) --* **[REQUIRED]** 

              The value representing the dimension measurement

              

            
          
      
        - **Timestamp** *(datetime) --* 

          The time stamp used for the metric in ISO 8601 Universal Coordinated Time (UTC) format. If not specified, the default value is set to the time the metric data was received.

          

        
        - **Value** *(float) --* 

          The value for the metric.

           

          .. warning::

             

            Although the ``Value`` parameter accepts numbers of type ``Double`` , Amazon CloudWatch rejects values that are either too small or too large. Values must be in the range of 8.515920e-109 to 1.174271e+108 (Base 10) or 2e-360 to 2e360 (Base 2). In addition, special values (e.g., NaN, +Infinity, -Infinity) are not supported.

             

          

        
        - **StatisticValues** *(dict) --* 

          A set of statistical values describing the metric.

          

        
          - **SampleCount** *(float) --* **[REQUIRED]** 

            The number of samples used for the statistic set.

            

          
          - **Sum** *(float) --* **[REQUIRED]** 

            The sum of values for the sample set.

            

          
          - **Minimum** *(float) --* **[REQUIRED]** 

            The minimum value of the sample set.

            

          
          - **Maximum** *(float) --* **[REQUIRED]** 

            The maximum value of the sample set.

            

          
        
        - **Unit** *(string) --* 

          The unit of the metric.

          

        
      
  
    
    :returns: None

  .. py:method:: set_alarm_state(**kwargs)

    

    Temporarily sets the state of an alarm for testing purposes. When the updated ``StateValue`` differs from the previous value, the action configured for the appropriate state is invoked. For example, if your alarm is configured to send an Amazon SNS message when an alarm is triggered, temporarily changing the alarm's state to **ALARM** sends an Amazon SNS message. The alarm returns to its actual state (often within seconds). Because the alarm state change happens very quickly, it is typically only visible in the alarm's **History** tab in the Amazon CloudWatch console or through ``DescribeAlarmHistory`` . 

    

    **Request Syntax** 
    ::

      response = client.set_alarm_state(
          AlarmName='string',
          StateValue='OK'|'ALARM'|'INSUFFICIENT_DATA',
          StateReason='string',
          StateReasonData='string'
      )
    :type AlarmName: string
    :param AlarmName: **[REQUIRED]** 

      The descriptive name for the alarm. This name must be unique within the user's AWS account. The maximum length is 255 characters.

      

    
    :type StateValue: string
    :param StateValue: **[REQUIRED]** 

      The value of the state.

      

    
    :type StateReason: string
    :param StateReason: **[REQUIRED]** 

      The reason that this alarm is set to this specific state (in human-readable text format)

      

    
    :type StateReasonData: string
    :param StateReasonData: 

      The reason that this alarm is set to this specific state (in machine-readable JSON format)

      

    
    
    :returns: None

==========
Paginators
==========


The available paginators are:

* :py:class:`CloudWatch.Paginator.DescribeAlarmHistory`


* :py:class:`CloudWatch.Paginator.DescribeAlarms`


* :py:class:`CloudWatch.Paginator.ListMetrics`



.. py:class:: CloudWatch.Paginator.DescribeAlarmHistory

  ::

    
    paginator = client.get_paginator('describe_alarm_history')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudWatch.Client.describe_alarm_history`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          AlarmName='string',
          HistoryItemType='ConfigurationUpdate'|'StateUpdate'|'Action',
          StartDate=datetime(2015, 1, 1),
          EndDate=datetime(2015, 1, 1),
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type AlarmName: string
    :param AlarmName: 

      The name of the alarm.

      

    
    :type HistoryItemType: string
    :param HistoryItemType: 

      The type of alarm histories to retrieve.

      

    
    :type StartDate: datetime
    :param StartDate: 

      The starting date to retrieve alarm history.

      

    
    :type EndDate: datetime
    :param EndDate: 

      The ending date to retrieve alarm history.

      

    
    :type PaginationConfig: dict
    :param PaginationConfig: 

      A dictionary that provides parameters to control pagination.

      

    
      - **MaxItems** *(integer) --* 

        The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination.

        

      
      - **PageSize** *(integer) --* 

        The size of each page.

        

        

        

      
      - **StartingToken** *(string) --* 

        A token to specify where to start paginating. This is the ``NextToken`` from a previous response.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AlarmHistoryItems': [
                {
                    'AlarmName': 'string',
                    'Timestamp': datetime(2015, 1, 1),
                    'HistoryItemType': 'ConfigurationUpdate'|'StateUpdate'|'Action',
                    'HistorySummary': 'string',
                    'HistoryData': 'string'
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  DescribeAlarmHistory . 

        
        

        - **AlarmHistoryItems** *(list) --* 

          A list of alarm histories in JSON format.

          
          

          - *(dict) --* 

            The ``AlarmHistoryItem`` data type contains descriptive information about the history of a specific alarm. If you call  DescribeAlarmHistory , Amazon CloudWatch returns this data type as part of the DescribeAlarmHistoryResult data type. 

            
            

            - **AlarmName** *(string) --* 

              The descriptive name for the alarm.

              
            

            - **Timestamp** *(datetime) --* 

              The time stamp for the alarm history item.

              
            

            - **HistoryItemType** *(string) --* 

              The type of alarm history item.

              
            

            - **HistorySummary** *(string) --* 

              A human-readable summary of the alarm history.

              
            

            - **HistoryData** *(string) --* 

              Machine-readable data about the alarm in JSON format.

              
        
      
    

.. py:class:: CloudWatch.Paginator.DescribeAlarms

  ::

    
    paginator = client.get_paginator('describe_alarms')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudWatch.Client.describe_alarms`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          AlarmNames=[
              'string',
          ],
          AlarmNamePrefix='string',
          StateValue='OK'|'ALARM'|'INSUFFICIENT_DATA',
          ActionPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type AlarmNames: list
    :param AlarmNames: 

      A list of alarm names to retrieve information for.

      

    
      - *(string) --* 

      
  
    :type AlarmNamePrefix: string
    :param AlarmNamePrefix: 

      The alarm name prefix. ``AlarmNames`` cannot be specified if this parameter is specified.

      

    
    :type StateValue: string
    :param StateValue: 

      The state value to be used in matching alarms.

      

    
    :type ActionPrefix: string
    :param ActionPrefix: 

      The action name prefix.

      

    
    :type PaginationConfig: dict
    :param PaginationConfig: 

      A dictionary that provides parameters to control pagination.

      

    
      - **MaxItems** *(integer) --* 

        The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination.

        

      
      - **PageSize** *(integer) --* 

        The size of each page.

        

        

        

      
      - **StartingToken** *(string) --* 

        A token to specify where to start paginating. This is the ``NextToken`` from a previous response.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MetricAlarms': [
                {
                    'AlarmName': 'string',
                    'AlarmArn': 'string',
                    'AlarmDescription': 'string',
                    'AlarmConfigurationUpdatedTimestamp': datetime(2015, 1, 1),
                    'ActionsEnabled': True|False,
                    'OKActions': [
                        'string',
                    ],
                    'AlarmActions': [
                        'string',
                    ],
                    'InsufficientDataActions': [
                        'string',
                    ],
                    'StateValue': 'OK'|'ALARM'|'INSUFFICIENT_DATA',
                    'StateReason': 'string',
                    'StateReasonData': 'string',
                    'StateUpdatedTimestamp': datetime(2015, 1, 1),
                    'MetricName': 'string',
                    'Namespace': 'string',
                    'Statistic': 'SampleCount'|'Average'|'Sum'|'Minimum'|'Maximum',
                    'Dimensions': [
                        {
                            'Name': 'string',
                            'Value': 'string'
                        },
                    ],
                    'Period': 123,
                    'Unit': 'Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None',
                    'EvaluationPeriods': 123,
                    'Threshold': 123.0,
                    'ComparisonOperator': 'GreaterThanOrEqualToThreshold'|'GreaterThanThreshold'|'LessThanThreshold'|'LessThanOrEqualToThreshold'
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  DescribeAlarms .

        
        

        - **MetricAlarms** *(list) --* 

          A list of information for the specified alarms.

          
          

          - *(dict) --* 

            The  MetricAlarm data type represents an alarm. You can use  PutMetricAlarm to create or update an alarm. 

            
            

            - **AlarmName** *(string) --* 

              The name of the alarm.

              
            

            - **AlarmArn** *(string) --* 

              The Amazon Resource Name (ARN) of the alarm.

              
            

            - **AlarmDescription** *(string) --* 

              The description for the alarm.

              
            

            - **AlarmConfigurationUpdatedTimestamp** *(datetime) --* 

              The time stamp of the last update to the alarm configuration.

              
            

            - **ActionsEnabled** *(boolean) --* 

              Indicates whether actions should be executed during any changes to the alarm's state.

              
            

            - **OKActions** *(list) --* 

              The list of actions to execute when this alarm transitions into an ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

              
              

              - *(string) --* 
          
            

            - **AlarmActions** *(list) --* 

              The list of actions to execute when this alarm transitions into an ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

              
              

              - *(string) --* 
          
            

            - **InsufficientDataActions** *(list) --* 

              The list of actions to execute when this alarm transitions into an ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

               

              .. warning::

                 

                The current WSDL lists this attribute as ``UnknownActions`` .

                 

              
              

              - *(string) --* 
          
            

            - **StateValue** *(string) --* 

              The state value for the alarm.

              
            

            - **StateReason** *(string) --* 

              A human-readable explanation for the alarm's state.

              
            

            - **StateReasonData** *(string) --* 

              An explanation for the alarm's state in machine-readable JSON format

              
            

            - **StateUpdatedTimestamp** *(datetime) --* 

              The time stamp of the last update to the alarm's state.

              
            

            - **MetricName** *(string) --* 

              The name of the alarm's metric.

              
            

            - **Namespace** *(string) --* 

              The namespace of alarm's associated metric.

              
            

            - **Statistic** *(string) --* 

              The statistic to apply to the alarm's associated metric.

              
            

            - **Dimensions** *(list) --* 

              The list of dimensions associated with the alarm's associated metric.

              
              

              - *(dict) --* 

                The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

                 

                For examples that use one or more dimensions, see  PutMetricData .

                
                

                - **Name** *(string) --* 

                  The name of the dimension.

                  
                

                - **Value** *(string) --* 

                  The value representing the dimension measurement

                  
            
          
            

            - **Period** *(integer) --* 

              The period in seconds over which the statistic is applied.

              
            

            - **Unit** *(string) --* 

              The unit of the alarm's associated metric.

              
            

            - **EvaluationPeriods** *(integer) --* 

              The number of periods over which data is compared to the specified threshold.

              
            

            - **Threshold** *(float) --* 

              The value against which the specified statistic is compared.

              
            

            - **ComparisonOperator** *(string) --* 

              The arithmetic operation to use when comparing the specified ``Statistic`` and ``Threshold`` . The specified ``Statistic`` value is used as the first operand. 

              
        
      
    

.. py:class:: CloudWatch.Paginator.ListMetrics

  ::

    
    paginator = client.get_paginator('list_metrics')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudWatch.Client.list_metrics`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          Namespace='string',
          MetricName='string',
          Dimensions=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type Namespace: string
    :param Namespace: 

      The namespace to filter against.

      

    
    :type MetricName: string
    :param MetricName: 

      The name of the metric to filter against.

      

    
    :type Dimensions: list
    :param Dimensions: 

      A list of dimensions to filter against.

      

    
      - *(dict) --* 

        The ``DimensionFilter`` data type is used to filter  ListMetrics results. 

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The dimension name to be matched.

          

        
        - **Value** *(string) --* 

          The value of the dimension to be matched.

           

          .. note::

             

            Specifying a ``Name`` without specifying a ``Value`` returns all values associated with that ``Name`` .

             

          

        
      
  
    :type PaginationConfig: dict
    :param PaginationConfig: 

      A dictionary that provides parameters to control pagination.

      

    
      - **MaxItems** *(integer) --* 

        The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination.

        

      
      - **PageSize** *(integer) --* 

        The size of each page.

        

        

        

      
      - **StartingToken** *(string) --* 

        A token to specify where to start paginating. This is the ``NextToken`` from a previous response.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Metrics': [
                {
                    'Namespace': 'string',
                    'MetricName': 'string',
                    'Dimensions': [
                        {
                            'Name': 'string',
                            'Value': 'string'
                        },
                    ]
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  ListMetrics . 

        
        

        - **Metrics** *(list) --* 

          A list of metrics used to generate statistics for an AWS account.

          
          

          - *(dict) --* 

            The ``Metric`` data type contains information about a specific metric. If you call  ListMetrics , Amazon CloudWatch returns information contained by this data type. 

             

            The example in the Examples section publishes two metrics named buffers and latency. Both metrics are in the examples namespace. Both metrics have two dimensions, InstanceID and InstanceType.

            
            

            - **Namespace** *(string) --* 

              The namespace of the metric.

              
            

            - **MetricName** *(string) --* 

              The name of the metric.

              
            

            - **Dimensions** *(list) --* 

              A list of dimensions associated with the metric.

              
              

              - *(dict) --* 

                The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

                 

                For examples that use one or more dimensions, see  PutMetricData .

                
                

                - **Name** *(string) --* 

                  The name of the dimension.

                  
                

                - **Value** *(string) --* 

                  The value representing the dimension measurement

                  
            
          
        
      
    

================
Service Resource
================



.. py:class:: CloudWatch.ServiceResource()

  A resource representing Amazon CloudWatch::

    
    import boto3
    
    cloudwatch = boto3.resource('cloudwatch')

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Alarm()`

  
  *   :py:meth:`Metric()`

  
  These are the resource's available collections:
  
  *   :py:attr:`alarms`

  
  *   :py:attr:`metrics`

  
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Alarm(name)

    Creates a Alarm resource.::

      alarm = cloudwatch.Alarm('name')

    :type name: string
    :param name: The Alarm's name identifier. This **must** be set.
    
    :rtype: :py:class:`CloudWatch.Alarm`
    :returns: A Alarm resource
    

  .. py:method:: Metric(namespace,name)

    Creates a Metric resource.::

      metric = cloudwatch.Metric('namespace','name')

    :type namespace: string
    :param namespace: The Metric's namespace identifier. This **must** be set.
    :type name: string
    :param name: The Metric's name identifier. This **must** be set.
    
    :rtype: :py:class:`CloudWatch.Metric`
    :returns: A Metric resource
    
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: alarms

    A collection of Alarm resources

    .. py:method:: all()

      Creates an iterable of all Alarm resources in the collection.

      **Request Syntax** 
      ::

        alarm_iterator = cloudwatch.alarms.all()
        
      
      :rtype: list(:py:class:`cloudwatch.Alarm`)
      :returns: A list of Alarm resources
      

    .. py:method:: delete()

      

      Deletes all specified alarms. In the event of an error, no alarms are deleted.

      

      **Request Syntax** 
      ::

        response = cloudwatch.alarms.delete()
        
      
      :returns: None

    .. py:method:: disable_actions()

      

      Disables actions for the specified alarms. When an alarm's actions are disabled the alarm's state may change, but none of the alarm's actions will execute.

      

      **Request Syntax** 
      ::

        response = cloudwatch.alarms.disable_actions()
        
      
      :returns: None

    .. py:method:: enable_actions()

      

      Enables actions for the specified alarms.

      

      **Request Syntax** 
      ::

        response = cloudwatch.alarms.enable_actions()
        
      
      :returns: None

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Alarm resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        alarm_iterator = cloudwatch.alarms.filter(
            AlarmNames=[
                'string',
            ],
            AlarmNamePrefix='string',
            StateValue='OK'|'ALARM'|'INSUFFICIENT_DATA',
            ActionPrefix='string',
            MaxRecords=123,
            NextToken='string'
        )
      :type AlarmNames: list
      :param AlarmNames: 

        A list of alarm names to retrieve information for.

        

      
        - *(string) --* 

        
    
      :type AlarmNamePrefix: string
      :param AlarmNamePrefix: 

        The alarm name prefix. ``AlarmNames`` cannot be specified if this parameter is specified.

        

      
      :type StateValue: string
      :param StateValue: 

        The state value to be used in matching alarms.

        

      
      :type ActionPrefix: string
      :param ActionPrefix: 

        The action name prefix.

        

      
      :type MaxRecords: integer
      :param MaxRecords: 

        The maximum number of alarm descriptions to retrieve.

        

      
      :type NextToken: string
      :param NextToken: 

        The token returned by a previous call to indicate that there is more data available.

        

      
      
      :rtype: list(:py:class:`cloudwatch.Alarm`)
      :returns: A list of Alarm resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Alarm resources in the collection.

      **Request Syntax** 
      ::

        alarm_iterator = cloudwatch.alarms.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`cloudwatch.Alarm`)
      :returns: A list of Alarm resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Alarm resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        alarm_iterator = cloudwatch.alarms.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`cloudwatch.Alarm`)
      :returns: A list of Alarm resources
      

  .. py:attribute:: metrics

    A collection of Metric resources

    .. py:method:: all()

      Creates an iterable of all Metric resources in the collection.

      **Request Syntax** 
      ::

        metric_iterator = cloudwatch.metrics.all()
        
      
      :rtype: list(:py:class:`cloudwatch.Metric`)
      :returns: A list of Metric resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Metric resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        metric_iterator = cloudwatch.metrics.filter(
            Namespace='string',
            MetricName='string',
            Dimensions=[
                {
                    'Name': 'string',
                    'Value': 'string'
                },
            ],
            NextToken='string'
        )
      :type Namespace: string
      :param Namespace: 

        The namespace to filter against.

        

      
      :type MetricName: string
      :param MetricName: 

        The name of the metric to filter against.

        

      
      :type Dimensions: list
      :param Dimensions: 

        A list of dimensions to filter against.

        

      
        - *(dict) --* 

          The ``DimensionFilter`` data type is used to filter  ListMetrics results. 

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            The dimension name to be matched.

            

          
          - **Value** *(string) --* 

            The value of the dimension to be matched.

             

            .. note::

               

              Specifying a ``Name`` without specifying a ``Value`` returns all values associated with that ``Name`` .

               

            

          
        
    
      :type NextToken: string
      :param NextToken: 

        The token returned by a previous call to indicate that there is more data available.

        

      
      
      :rtype: list(:py:class:`cloudwatch.Metric`)
      :returns: A list of Metric resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Metric resources in the collection.

      **Request Syntax** 
      ::

        metric_iterator = cloudwatch.metrics.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`cloudwatch.Metric`)
      :returns: A list of Metric resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Metric resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        metric_iterator = cloudwatch.metrics.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`cloudwatch.Metric`)
      :returns: A list of Metric resources
      

=====
Alarm
=====



.. py:class:: CloudWatch.Alarm(name)

  A resource representing an Amazon CloudWatch Alarm::

    
    import boto3
    
    cloudwatch = boto3.resource('cloudwatch')
    alarm = cloudwatch.Alarm('name')

  :type name: string
  :param name: The Alarm's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`actions_enabled`

  
  *   :py:attr:`alarm_actions`

  
  *   :py:attr:`alarm_arn`

  
  *   :py:attr:`alarm_configuration_updated_timestamp`

  
  *   :py:attr:`alarm_description`

  
  *   :py:attr:`alarm_name`

  
  *   :py:attr:`comparison_operator`

  
  *   :py:attr:`dimensions`

  
  *   :py:attr:`evaluation_periods`

  
  *   :py:attr:`insufficient_data_actions`

  
  *   :py:attr:`metric_name`

  
  *   :py:attr:`namespace`

  
  *   :py:attr:`ok_actions`

  
  *   :py:attr:`period`

  
  *   :py:attr:`state_reason`

  
  *   :py:attr:`state_reason_data`

  
  *   :py:attr:`state_updated_timestamp`

  
  *   :py:attr:`state_value`

  
  *   :py:attr:`statistic`

  
  *   :py:attr:`threshold`

  
  *   :py:attr:`unit`

  
  These are the resource's available references:
  
  *   :py:attr:`metric`

  
  These are the resource's available actions:
  
  *   :py:meth:`delete()`

  
  *   :py:meth:`describe_history()`

  
  *   :py:meth:`disable_actions()`

  
  *   :py:meth:`enable_actions()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`set_state()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: name

    *(string)* The Alarm's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: actions_enabled

    

    - *(boolean) --* 

      Indicates whether actions should be executed during any changes to the alarm's state.

      

  .. py:attribute:: alarm_actions

    

    - *(list) --* 

      The list of actions to execute when this alarm transitions into an ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

      
      

      - *(string) --* 
  

  .. py:attribute:: alarm_arn

    

    - *(string) --* 

      The Amazon Resource Name (ARN) of the alarm.

      

  .. py:attribute:: alarm_configuration_updated_timestamp

    

    - *(datetime) --* 

      The time stamp of the last update to the alarm configuration.

      

  .. py:attribute:: alarm_description

    

    - *(string) --* 

      The description for the alarm.

      

  .. py:attribute:: alarm_name

    

    - *(string) --* 

      The name of the alarm.

      

  .. py:attribute:: comparison_operator

    

    - *(string) --* 

      The arithmetic operation to use when comparing the specified ``Statistic`` and ``Threshold`` . The specified ``Statistic`` value is used as the first operand. 

      

  .. py:attribute:: dimensions

    

    - *(list) --* 

      The list of dimensions associated with the alarm's associated metric.

      
      

      - *(dict) --* 

        The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

         

        For examples that use one or more dimensions, see  PutMetricData .

        
        

        - **Name** *(string) --* 

          The name of the dimension.

          
        

        - **Value** *(string) --* 

          The value representing the dimension measurement

          
    
  

  .. py:attribute:: evaluation_periods

    

    - *(integer) --* 

      The number of periods over which data is compared to the specified threshold.

      

  .. py:attribute:: insufficient_data_actions

    

    - *(list) --* 

      The list of actions to execute when this alarm transitions into an ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

       

      .. warning::

         

        The current WSDL lists this attribute as ``UnknownActions`` .

         

      
      

      - *(string) --* 
  

  .. py:attribute:: metric_name

    

    - *(string) --* 

      The name of the alarm's metric.

      

  .. py:attribute:: namespace

    

    - *(string) --* 

      The namespace of alarm's associated metric.

      

  .. py:attribute:: ok_actions

    

    - *(list) --* 

      The list of actions to execute when this alarm transitions into an ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

      
      

      - *(string) --* 
  

  .. py:attribute:: period

    

    - *(integer) --* 

      The period in seconds over which the statistic is applied.

      

  .. py:attribute:: state_reason

    

    - *(string) --* 

      A human-readable explanation for the alarm's state.

      

  .. py:attribute:: state_reason_data

    

    - *(string) --* 

      An explanation for the alarm's state in machine-readable JSON format

      

  .. py:attribute:: state_updated_timestamp

    

    - *(datetime) --* 

      The time stamp of the last update to the alarm's state.

      

  .. py:attribute:: state_value

    

    - *(string) --* 

      The state value for the alarm.

      

  .. py:attribute:: statistic

    

    - *(string) --* 

      The statistic to apply to the alarm's associated metric.

      

  .. py:attribute:: threshold

    

    - *(float) --* 

      The value against which the specified statistic is compared.

      

  .. py:attribute:: unit

    

    - *(string) --* 

      The unit of the alarm's associated metric.

      
  .. rst-class:: admonition-title
  
  References
  
  References are related resource instances that have a belongs-to relationship.
  For more information about references refer to the :ref:`Resources Introduction Guide<references_intro>`.
  

  .. py:attribute:: metric

    (:py:class:`Metric`) The related metric if set, otherwise ``None``.
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: delete()

    

    Deletes all specified alarms. In the event of an error, no alarms are deleted.

    

    **Request Syntax** 
    ::

      response = alarm.delete()
      
    
    :returns: None

  .. py:method:: describe_history(**kwargs)

    

    Retrieves history for the specified alarm. Filter alarms by date range or item type. If an alarm name is not specified, Amazon CloudWatch returns histories for all of the owner's alarms.

     

    .. note::

       

      Amazon CloudWatch retains the history of an alarm for two weeks, whether or not you delete the alarm.

       

    

    **Request Syntax** 
    ::

      response = alarm.describe_history(
          HistoryItemType='ConfigurationUpdate'|'StateUpdate'|'Action',
          StartDate=datetime(2015, 1, 1),
          EndDate=datetime(2015, 1, 1),
          MaxRecords=123,
          NextToken='string'
      )
    :type HistoryItemType: string
    :param HistoryItemType: 

      The type of alarm histories to retrieve.

      

    
    :type StartDate: datetime
    :param StartDate: 

      The starting date to retrieve alarm history.

      

    
    :type EndDate: datetime
    :param EndDate: 

      The ending date to retrieve alarm history.

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of alarm history records to retrieve.

      

    
    :type NextToken: string
    :param NextToken: 

      The token returned by a previous call to indicate that there is more data available.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AlarmHistoryItems': [
                {
                    'AlarmName': 'string',
                    'Timestamp': datetime(2015, 1, 1),
                    'HistoryItemType': 'ConfigurationUpdate'|'StateUpdate'|'Action',
                    'HistorySummary': 'string',
                    'HistoryData': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  DescribeAlarmHistory . 

        
        

        - **AlarmHistoryItems** *(list) --* 

          A list of alarm histories in JSON format.

          
          

          - *(dict) --* 

            The ``AlarmHistoryItem`` data type contains descriptive information about the history of a specific alarm. If you call  DescribeAlarmHistory , Amazon CloudWatch returns this data type as part of the DescribeAlarmHistoryResult data type. 

            
            

            - **AlarmName** *(string) --* 

              The descriptive name for the alarm.

              
            

            - **Timestamp** *(datetime) --* 

              The time stamp for the alarm history item.

              
            

            - **HistoryItemType** *(string) --* 

              The type of alarm history item.

              
            

            - **HistorySummary** *(string) --* 

              A human-readable summary of the alarm history.

              
            

            - **HistoryData** *(string) --* 

              Machine-readable data about the alarm in JSON format.

              
        
      
        

        - **NextToken** *(string) --* 

          A string that marks the start of the next batch of returned results.

          
    

  .. py:method:: disable_actions()

    

    Disables actions for the specified alarms. When an alarm's actions are disabled the alarm's state may change, but none of the alarm's actions will execute.

    

    **Request Syntax** 
    ::

      response = alarm.disable_actions()
      
    
    :returns: None

  .. py:method:: enable_actions()

    

    Enables actions for the specified alarms.

    

    **Request Syntax** 
    ::

      response = alarm.enable_actions()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`CloudWatch.Client.describe_alarms` to update the attributes of the Alarm resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      alarm.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`CloudWatch.Client.describe_alarms` to update the attributes of the Alarm resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      alarm.reload()
    :returns: None

  .. py:method:: set_state(**kwargs)

    

    Temporarily sets the state of an alarm for testing purposes. When the updated ``StateValue`` differs from the previous value, the action configured for the appropriate state is invoked. For example, if your alarm is configured to send an Amazon SNS message when an alarm is triggered, temporarily changing the alarm's state to **ALARM** sends an Amazon SNS message. The alarm returns to its actual state (often within seconds). Because the alarm state change happens very quickly, it is typically only visible in the alarm's **History** tab in the Amazon CloudWatch console or through ``DescribeAlarmHistory`` . 

    

    **Request Syntax** 
    ::

      response = alarm.set_state(
          StateValue='OK'|'ALARM'|'INSUFFICIENT_DATA',
          StateReason='string',
          StateReasonData='string'
      )
    :type StateValue: string
    :param StateValue: **[REQUIRED]** 

      The value of the state.

      

    
    :type StateReason: string
    :param StateReason: **[REQUIRED]** 

      The reason that this alarm is set to this specific state (in human-readable text format)

      

    
    :type StateReasonData: string
    :param StateReasonData: 

      The reason that this alarm is set to this specific state (in machine-readable JSON format)

      

    
    
    :returns: None

======
Metric
======



.. py:class:: CloudWatch.Metric(namespace,name)

  A resource representing an Amazon CloudWatch Metric::

    
    import boto3
    
    cloudwatch = boto3.resource('cloudwatch')
    metric = cloudwatch.Metric('namespace','name')

  :type namespace: string
  :param namespace: The Metric's namespace identifier. This **must** be set.
  :type name: string
  :param name: The Metric's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`namespace`

  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`dimensions`

  
  *   :py:attr:`metric_name`

  
  These are the resource's available actions:
  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`get_statistics()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`put_alarm()`

  
  *   :py:meth:`put_data()`

  
  *   :py:meth:`reload()`

  
  These are the resource's available collections:
  
  *   :py:attr:`alarms`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: namespace

    *(string)* The Metric's namespace identifier. This **must** be set.

  .. py:attribute:: name

    *(string)* The Metric's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: dimensions

    

    - *(list) --* 

      A list of dimensions associated with the metric.

      
      

      - *(dict) --* 

        The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

         

        For examples that use one or more dimensions, see  PutMetricData .

        
        

        - **Name** *(string) --* 

          The name of the dimension.

          
        

        - **Value** *(string) --* 

          The value representing the dimension measurement

          
    
  

  .. py:attribute:: metric_name

    

    - *(string) --* 

      The name of the metric.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: get_statistics(**kwargs)

    

    Gets statistics for the specified metric.

     

    The maximum number of data points that can be queried is 50,850, whereas the maximum number of data points returned from a single ``GetMetricStatistics`` request is 1,440. If you make a request that generates more than 1,440 data points, Amazon CloudWatch returns an error. In such a case, you can alter the request by narrowing the specified time range or increasing the specified period. A period can be as short as one minute (60 seconds) or as long as one day (86,400 seconds). Alternatively, you can make multiple requests across adjacent time ranges. ``GetMetricStatistics`` does not return the data in chronological order. 

     

    Amazon CloudWatch aggregates data points based on the length of the ``period`` that you specify. For example, if you request statistics with a one-minute granularity, Amazon CloudWatch aggregates data points with time stamps that fall within the same one-minute period. In such a case, the data points queried can greatly outnumber the data points returned. 

     

    The following examples show various statistics allowed by the data point query maximum of 50,850 when you call ``GetMetricStatistics`` on Amazon EC2 instances with detailed (one-minute) monitoring enabled: 

     

     
    * Statistics for up to 400 instances for a span of one hour 
     
    * Statistics for up to 35 instances over a span of 24 hours 
     
    * Statistics for up to 2 instances over a span of 2 weeks 
     

     

    For information about the namespace, metric names, and dimensions that other Amazon Web Services products use to send metrics to CloudWatch, go to `Amazon CloudWatch Metrics, Namespaces, and Dimensions Reference`_ in the *Amazon CloudWatch Developer Guide* . 

    

    **Request Syntax** 
    ::

      response = metric.get_statistics(
          Dimensions=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ],
          StartTime=datetime(2015, 1, 1),
          EndTime=datetime(2015, 1, 1),
          Period=123,
          Statistics=[
              'SampleCount'|'Average'|'Sum'|'Minimum'|'Maximum',
          ],
          Unit='Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None'
      )
    :type Dimensions: list
    :param Dimensions: 

      A list of dimensions describing qualities of the metric.

      

    
      - *(dict) --* 

        The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

         

        For examples that use one or more dimensions, see  PutMetricData .

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the dimension.

          

        
        - **Value** *(string) --* **[REQUIRED]** 

          The value representing the dimension measurement

          

        
      
  
    :type StartTime: datetime
    :param StartTime: **[REQUIRED]** 

      The time stamp to use for determining the first datapoint to return. The value specified is inclusive; results include datapoints with the time stamp specified. The time stamp must be in ISO 8601 UTC format (e.g., 2014-09-03T23:00:00Z).

       

      .. note::

         

        The specified start time is rounded down to the nearest value. Datapoints are returned for start times up to two weeks in the past. Specified start times that are more than two weeks in the past will not return datapoints for metrics that are older than two weeks.

         

        Data that is timestamped 24 hours or more in the past may take in excess of 48 hours to become available from submission time using ``GetMetricStatistics`` .

         

      

    
    :type EndTime: datetime
    :param EndTime: **[REQUIRED]** 

      The time stamp to use for determining the last datapoint to return. The value specified is exclusive; results will include datapoints up to the time stamp specified. The time stamp must be in ISO 8601 UTC format (e.g., 2014-09-03T23:00:00Z).

      

    
    :type Period: integer
    :param Period: **[REQUIRED]** 

      The granularity, in seconds, of the returned datapoints. A ``Period`` can be as short as one minute (60 seconds) or as long as one day (86,400 seconds), and must be a multiple of 60. The default value is 60. 

      

    
    :type Statistics: list
    :param Statistics: **[REQUIRED]** 

      The metric statistics to return. For information about specific statistics returned by GetMetricStatistics, see `Statistics`_ in the *Amazon CloudWatch Developer Guide* . 

      

    
      - *(string) --* 

      
  
    :type Unit: string
    :param Unit: 

      The specific unit for a given metric. Metrics may be reported in multiple units. Not supplying a unit results in all units being returned. If the metric only ever reports one unit, specifying a unit will have no effect.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Label': 'string',
            'Datapoints': [
                {
                    'Timestamp': datetime(2015, 1, 1),
                    'SampleCount': 123.0,
                    'Average': 123.0,
                    'Sum': 123.0,
                    'Minimum': 123.0,
                    'Maximum': 123.0,
                    'Unit': 'Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  GetMetricStatistics . 

        
        

        - **Label** *(string) --* 

          A label describing the specified metric.

          
        

        - **Datapoints** *(list) --* 

          The datapoints for the specified metric.

          
          

          - *(dict) --* 

            The ``Datapoint`` data type encapsulates the statistical data that Amazon CloudWatch computes from metric data. 

            
            

            - **Timestamp** *(datetime) --* 

              The time stamp used for the datapoint.

              
            

            - **SampleCount** *(float) --* 

              The number of metric values that contributed to the aggregate value of this datapoint.

              
            

            - **Average** *(float) --* 

              The average of metric values that correspond to the datapoint.

              
            

            - **Sum** *(float) --* 

              The sum of metric values used for the datapoint.

              
            

            - **Minimum** *(float) --* 

              The minimum metric value used for the datapoint.

              
            

            - **Maximum** *(float) --* 

              The maximum of the metric value used for the datapoint.

              
            

            - **Unit** *(string) --* 

              The standard unit used for the datapoint.

              
        
      
    

  .. py:method:: load()

    Calls :py:meth:`CloudWatch.Client.list_metrics` to update the attributes of the Metric resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      metric.load()
    :returns: None

  .. py:method:: put_alarm(**kwargs)

    

    Creates or updates an alarm and associates it with the specified Amazon CloudWatch metric. Optionally, this operation can associate one or more Amazon SNS resources with the alarm.

     

    When this operation creates an alarm, the alarm state is immediately set to ``INSUFFICIENT_DATA`` . The alarm is evaluated and its ``StateValue`` is set appropriately. Any actions associated with the ``StateValue`` are then executed. 

     

    .. note::

       

      When updating an existing alarm, its ``StateValue`` is left unchanged, but it completely overwrites the alarm's previous configuration.

       

     

    .. note::

       

      If you are using an AWS Identity and Access Management (IAM) account to create or modify an alarm, you must have the following Amazon EC2 permissions:

       

       
      * ``ec2:DescribeInstanceStatus`` and ``ec2:DescribeInstances`` for all alarms on Amazon EC2 instance status metrics. 
       
      * ``ec2:StopInstances`` for alarms with stop actions. 
       
      * ``ec2:TerminateInstances`` for alarms with terminate actions. 
       
      * ``ec2:DescribeInstanceRecoveryAttribute`` , and ``ec2:RecoverInstances`` for alarms with recover actions. 
       

       

      If you have read/write permissions for Amazon CloudWatch but not for Amazon EC2, you can still create an alarm but the stop or terminate actions won't be performed on the Amazon EC2 instance. However, if you are later granted permission to use the associated Amazon EC2 APIs, the alarm actions you created earlier will be performed. For more information about IAM permissions, see `Permissions and Policies`_ in *Using IAM* .

       

      If you are using an IAM role (e.g., an Amazon EC2 instance profile), you cannot stop or terminate the instance using alarm actions. However, you can still see the alarm state and perform any other actions such as Amazon SNS notifications or Auto Scaling policies.

       

      If you are using temporary security credentials granted using the AWS Security Token Service (AWS STS), you cannot stop or terminate an Amazon EC2 instance using alarm actions.

       

    

    **Request Syntax** 
    ::

      alarm = metric.put_alarm(
          AlarmName='string',
          AlarmDescription='string',
          ActionsEnabled=True|False,
          OKActions=[
              'string',
          ],
          AlarmActions=[
              'string',
          ],
          InsufficientDataActions=[
              'string',
          ],
          Statistic='SampleCount'|'Average'|'Sum'|'Minimum'|'Maximum',
          Dimensions=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ],
          Period=123,
          Unit='Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None',
          EvaluationPeriods=123,
          Threshold=123.0,
          ComparisonOperator='GreaterThanOrEqualToThreshold'|'GreaterThanThreshold'|'LessThanThreshold'|'LessThanOrEqualToThreshold'
      )
    :type AlarmName: string
    :param AlarmName: **[REQUIRED]** 

      The descriptive name for the alarm. This name must be unique within the user's AWS account

      

    
    :type AlarmDescription: string
    :param AlarmDescription: 

      The description for the alarm.

      

    
    :type ActionsEnabled: boolean
    :param ActionsEnabled: 

      Indicates whether or not actions should be executed during any changes to the alarm's state.

      

    
    :type OKActions: list
    :param OKActions: 

      The list of actions to execute when this alarm transitions into an ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

       

      Valid Values: arn:aws:automate:*region (e.g., us-east-1)* :ec2:stop | arn:aws:automate:*region (e.g., us-east-1)* :ec2:terminate | arn:aws:automate:*region (e.g., us-east-1)* :ec2:recover

       

      Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

       

       **Note:** You must create at least one stop, terminate, or reboot alarm using the Amazon EC2 or CloudWatch console to create the **EC2ActionsAccess** IAM role for the first time. After this IAM role is created, you can create stop, terminate, or reboot alarms using the CLI.

      

    
      - *(string) --* 

      
  
    :type AlarmActions: list
    :param AlarmActions: 

      The list of actions to execute when this alarm transitions into an ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

       

      Valid Values: arn:aws:automate:*region (e.g., us-east-1)* :ec2:stop | arn:aws:automate:*region (e.g., us-east-1)* :ec2:terminate | arn:aws:automate:*region (e.g., us-east-1)* :ec2:recover

       

      Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

       

       **Note:** You must create at least one stop, terminate, or reboot alarm using the Amazon EC2 or CloudWatch console to create the **EC2ActionsAccess** IAM role for the first time. After this IAM role is created, you can create stop, terminate, or reboot alarms using the CLI.

      

    
      - *(string) --* 

      
  
    :type InsufficientDataActions: list
    :param InsufficientDataActions: 

      The list of actions to execute when this alarm transitions into an ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

       

      Valid Values: arn:aws:automate:*region (e.g., us-east-1)* :ec2:stop | arn:aws:automate:*region (e.g., us-east-1)* :ec2:terminate | arn:aws:automate:*region (e.g., us-east-1)* :ec2:recover

       

      Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

       

       **Note:** You must create at least one stop, terminate, or reboot alarm using the Amazon EC2 or CloudWatch console to create the **EC2ActionsAccess** IAM role for the first time. After this IAM role is created, you can create stop, terminate, or reboot alarms using the CLI.

      

    
      - *(string) --* 

      
  
    :type Statistic: string
    :param Statistic: **[REQUIRED]** 

      The statistic to apply to the alarm's associated metric.

      

    
    :type Dimensions: list
    :param Dimensions: 

      The dimensions for the alarm's associated metric.

      

    
      - *(dict) --* 

        The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

         

        For examples that use one or more dimensions, see  PutMetricData .

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the dimension.

          

        
        - **Value** *(string) --* **[REQUIRED]** 

          The value representing the dimension measurement

          

        
      
  
    :type Period: integer
    :param Period: **[REQUIRED]** 

      The period in seconds over which the specified statistic is applied.

      

    
    :type Unit: string
    :param Unit: 

      The statistic's unit of measure. For example, the units for the Amazon EC2 NetworkIn metric are Bytes because NetworkIn tracks the number of bytes that an instance receives on all network interfaces. You can also specify a unit when you create a custom metric. Units help provide conceptual meaning to your data. Metric data points that specify a unit of measure, such as Percent, are aggregated separately.

       

       **Note:** If you specify a unit, you must use a unit that is appropriate for the metric. Otherwise, this can cause an Amazon CloudWatch alarm to get stuck in the INSUFFICIENT DATA state. 

      

    
    :type EvaluationPeriods: integer
    :param EvaluationPeriods: **[REQUIRED]** 

      The number of periods over which data is compared to the specified threshold.

      

    
    :type Threshold: float
    :param Threshold: **[REQUIRED]** 

      The value against which the specified statistic is compared.

      

    
    :type ComparisonOperator: string
    :param ComparisonOperator: **[REQUIRED]** 

      The arithmetic operation to use when comparing the specified ``Statistic`` and ``Threshold`` . The specified ``Statistic`` value is used as the first operand. 

      

    
    
    :rtype: :py:class:`cloudwatch.Alarm`
    :returns: Alarm resource
    

  .. py:method:: put_data()

    

    Publishes metric data points to Amazon CloudWatch. Amazon CloudWatch associates the data points with the specified metric. If the specified metric does not exist, Amazon CloudWatch creates the metric. When Amazon CloudWatch creates a metric, it can take up to fifteen minutes for the metric to appear in calls to  ListMetrics . 

     

    Each ``PutMetricData`` request is limited to 8 KB in size for HTTP GET requests and is limited to 40 KB in size for HTTP POST requests. 

     

    .. warning::

       

      Although the ``Value`` parameter accepts numbers of type ``Double`` , Amazon CloudWatch rejects values that are either too small or too large. Values must be in the range of 8.515920e-109 to 1.174271e+108 (Base 10) or 2e-360 to 2e360 (Base 2). In addition, special values (e.g., NaN, +Infinity, -Infinity) are not supported.

       

     

    Data that is timestamped 24 hours or more in the past may take in excess of 48 hours to become available from submission time using ``GetMetricStatistics`` .

    

    **Request Syntax** 
    ::

      response = metric.put_data()
      
    
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`CloudWatch.Client.list_metrics` to update the attributes of the Metric resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      metric.reload()
    :returns: None
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: alarms

    A collection of Alarm resources

    .. py:method:: all()

      Creates an iterable of all Alarm resources in the collection.

      **Request Syntax** 
      ::

        alarm_iterator = metric.alarms.all()
        
      
      :rtype: list(:py:class:`cloudwatch.Alarm`)
      :returns: A list of Alarm resources
      

    .. py:method:: delete()

      

      Deletes all specified alarms. In the event of an error, no alarms are deleted.

      

      **Request Syntax** 
      ::

        response = metric.alarms.delete()
        
      
      :returns: None

    .. py:method:: disable_actions()

      

      Disables actions for the specified alarms. When an alarm's actions are disabled the alarm's state may change, but none of the alarm's actions will execute.

      

      **Request Syntax** 
      ::

        response = metric.alarms.disable_actions()
        
      
      :returns: None

    .. py:method:: enable_actions()

      

      Enables actions for the specified alarms.

      

      **Request Syntax** 
      ::

        response = metric.alarms.enable_actions()
        
      
      :returns: None

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Alarm resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        alarm_iterator = metric.alarms.filter(
            Statistic='SampleCount'|'Average'|'Sum'|'Minimum'|'Maximum',
            Dimensions=[
                {
                    'Name': 'string',
                    'Value': 'string'
                },
            ],
            Period=123,
            Unit='Seconds'|'Microseconds'|'Milliseconds'|'Bytes'|'Kilobytes'|'Megabytes'|'Gigabytes'|'Terabytes'|'Bits'|'Kilobits'|'Megabits'|'Gigabits'|'Terabits'|'Percent'|'Count'|'Bytes/Second'|'Kilobytes/Second'|'Megabytes/Second'|'Gigabytes/Second'|'Terabytes/Second'|'Bits/Second'|'Kilobits/Second'|'Megabits/Second'|'Gigabits/Second'|'Terabits/Second'|'Count/Second'|'None'
        )
      :type Statistic: string
      :param Statistic: 

        The statistic for the metric.

        

      
      :type Dimensions: list
      :param Dimensions: 

        The list of dimensions associated with the metric. If the metric has any associated dimensions, you must specify them in order for the DescribeAlarmsForMetric to succeed.

        

      
        - *(dict) --* 

          The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

           

          For examples that use one or more dimensions, see  PutMetricData .

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            The name of the dimension.

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            The value representing the dimension measurement

            

          
        
    
      :type Period: integer
      :param Period: 

        The period in seconds over which the statistic is applied.

        

      
      :type Unit: string
      :param Unit: 

        The unit for the metric.

        

      
      
      :rtype: list(:py:class:`cloudwatch.Alarm`)
      :returns: A list of Alarm resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Alarm resources in the collection.

      **Request Syntax** 
      ::

        alarm_iterator = metric.alarms.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`cloudwatch.Alarm`)
      :returns: A list of Alarm resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Alarm resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        alarm_iterator = metric.alarms.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`cloudwatch.Alarm`)
      :returns: A list of Alarm resources
      