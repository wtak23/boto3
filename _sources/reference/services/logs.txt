

.. _IAM policy document: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html


**************
CloudWatchLogs
**************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: CloudWatchLogs.Client

  A low-level client representing Amazon CloudWatch Logs::

    
    import boto3
    
    client = boto3.client('logs')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`cancel_export_task`

  
  *   :py:meth:`create_export_task`

  
  *   :py:meth:`create_log_group`

  
  *   :py:meth:`create_log_stream`

  
  *   :py:meth:`delete_destination`

  
  *   :py:meth:`delete_log_group`

  
  *   :py:meth:`delete_log_stream`

  
  *   :py:meth:`delete_metric_filter`

  
  *   :py:meth:`delete_retention_policy`

  
  *   :py:meth:`delete_subscription_filter`

  
  *   :py:meth:`describe_destinations`

  
  *   :py:meth:`describe_export_tasks`

  
  *   :py:meth:`describe_log_groups`

  
  *   :py:meth:`describe_log_streams`

  
  *   :py:meth:`describe_metric_filters`

  
  *   :py:meth:`describe_subscription_filters`

  
  *   :py:meth:`filter_log_events`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_log_events`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`put_destination`

  
  *   :py:meth:`put_destination_policy`

  
  *   :py:meth:`put_log_events`

  
  *   :py:meth:`put_metric_filter`

  
  *   :py:meth:`put_retention_policy`

  
  *   :py:meth:`put_subscription_filter`

  
  *   :py:meth:`test_metric_filter`

  

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


  .. py:method:: cancel_export_task(**kwargs)

    

    Cancels an export task if it is in ``PENDING`` or ``RUNNING`` state.

    

    **Request Syntax** 
    ::

      response = client.cancel_export_task(
          taskId='string'
      )
    :type taskId: string
    :param taskId: **[REQUIRED]** 

      Id of the export task to cancel.

      

    
    
    :returns: None

  .. py:method:: create_export_task(**kwargs)

    

    Creates an ``ExportTask`` which allows you to efficiently export data from a Log Group to your Amazon S3 bucket.

     

    This is an asynchronous call. If all the required information is provided, this API will initiate an export task and respond with the task Id. Once started, ``DescribeExportTasks`` can be used to get the status of an export task. You can only have one active (``RUNNING`` or ``PENDING`` ) export task at a time, per account.

     

    You can export logs from multiple log groups or multiple time ranges to the same Amazon S3 bucket. To separate out log data for each export task, you can specify a prefix that will be used as the Amazon S3 key prefix for all exported objects.

    

    **Request Syntax** 
    ::

      response = client.create_export_task(
          taskName='string',
          logGroupName='string',
          logStreamNamePrefix='string',
          fromTime=123,
          to=123,
          destination='string',
          destinationPrefix='string'
      )
    :type taskName: string
    :param taskName: 

      The name of the export task.

      

    
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to export.

      

    
    :type logStreamNamePrefix: string
    :param logStreamNamePrefix: 

      Will only export log streams that match the provided logStreamNamePrefix. If you don't specify a value, no prefix filter is applied.

      

    
    :type fromTime: integer
    :param fromTime: **[REQUIRED]** 

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. It indicates the start time of the range for the request. Events with a timestamp prior to this time will not be exported.

      

    
    :type to: integer
    :param to: **[REQUIRED]** 

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. It indicates the end time of the range for the request. Events with a timestamp later than this time will not be exported.

      

    
    :type destination: string
    :param destination: **[REQUIRED]** 

      Name of Amazon S3 bucket to which the log data will be exported.

       

       **Note:** Only buckets in the same AWS region are supported.

      

    
    :type destinationPrefix: string
    :param destinationPrefix: 

      Prefix that will be used as the start of Amazon S3 key for every object exported. If not specified, this defaults to 'exportedlogs'.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'taskId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **taskId** *(string) --* 

          Id of the export task that got created.

          
    

  .. py:method:: create_log_group(**kwargs)

    

    Creates a new log group with the specified name. The name of the log group must be unique within a region for an AWS account. You can create up to 500 log groups per account.

     

    You must use the following guidelines when naming a log group:

     

     
    * Log group names can be between 1 and 512 characters long. 
     
    * Allowed characters are a-z, A-Z, 0-9, '_' (underscore), '-' (hyphen), '/' (forward slash), and '.' (period). 
     

    

    **Request Syntax** 
    ::

      response = client.create_log_group(
          logGroupName='string'
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to create.

      

    
    
    :returns: None

  .. py:method:: create_log_stream(**kwargs)

    

    Creates a new log stream in the specified log group. The name of the log stream must be unique within the log group. There is no limit on the number of log streams that can exist in a log group.

     

    You must use the following guidelines when naming a log stream:

     

     
    * Log stream names can be between 1 and 512 characters long. 
     
    * The ':' colon character is not allowed. 
     

    

    **Request Syntax** 
    ::

      response = client.create_log_stream(
          logGroupName='string',
          logStreamName='string'
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group under which the log stream is to be created.

      

    
    :type logStreamName: string
    :param logStreamName: **[REQUIRED]** 

      The name of the log stream to create.

      

    
    
    :returns: None

  .. py:method:: delete_destination(**kwargs)

    

    Deletes the destination with the specified name and eventually disables all the subscription filters that publish to it. This will not delete the physical resource encapsulated by the destination.

    

    **Request Syntax** 
    ::

      response = client.delete_destination(
          destinationName='string'
      )
    :type destinationName: string
    :param destinationName: **[REQUIRED]** 

      The name of destination to delete.

      

    
    
    :returns: None

  .. py:method:: delete_log_group(**kwargs)

    

    Deletes the log group with the specified name and permanently deletes all the archived log events associated with it.

    

    **Request Syntax** 
    ::

      response = client.delete_log_group(
          logGroupName='string'
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to delete.

      

    
    
    :returns: None

  .. py:method:: delete_log_stream(**kwargs)

    

    Deletes a log stream and permanently deletes all the archived log events associated with it.

    

    **Request Syntax** 
    ::

      response = client.delete_log_stream(
          logGroupName='string',
          logStreamName='string'
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group under which the log stream to delete belongs.

      

    
    :type logStreamName: string
    :param logStreamName: **[REQUIRED]** 

      The name of the log stream to delete.

      

    
    
    :returns: None

  .. py:method:: delete_metric_filter(**kwargs)

    

    Deletes a metric filter associated with the specified log group.

    

    **Request Syntax** 
    ::

      response = client.delete_metric_filter(
          logGroupName='string',
          filterName='string'
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group that is associated with the metric filter to delete.

      

    
    :type filterName: string
    :param filterName: **[REQUIRED]** 

      The name of the metric filter to delete.

      

    
    
    :returns: None

  .. py:method:: delete_retention_policy(**kwargs)

    

    Deletes the retention policy of the specified log group. Log events would not expire if they belong to log groups without a retention policy.

    

    **Request Syntax** 
    ::

      response = client.delete_retention_policy(
          logGroupName='string'
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group that is associated with the retention policy to delete.

      

    
    
    :returns: None

  .. py:method:: delete_subscription_filter(**kwargs)

    

    Deletes a subscription filter associated with the specified log group.

    

    **Request Syntax** 
    ::

      response = client.delete_subscription_filter(
          logGroupName='string',
          filterName='string'
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group that is associated with the subscription filter to delete.

      

    
    :type filterName: string
    :param filterName: **[REQUIRED]** 

      The name of the subscription filter to delete.

      

    
    
    :returns: None

  .. py:method:: describe_destinations(**kwargs)

    

    Returns all the destinations that are associated with the AWS account making the request. The list returned in the response is ASCII-sorted by destination name.

     

    By default, this operation returns up to 50 destinations. If there are more destinations to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of destinations returned in the response by specifying the ``limit`` parameter in the request.

    

    **Request Syntax** 
    ::

      response = client.describe_destinations(
          DestinationNamePrefix='string',
          nextToken='string',
          limit=123
      )
    :type DestinationNamePrefix: string
    :param DestinationNamePrefix: 

      Will only return destinations that match the provided destinationNamePrefix. If you don't specify a value, no prefix is applied.

      

    
    :type nextToken: string
    :param nextToken: 

      A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of results to return.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'destinations': [
                {
                    'destinationName': 'string',
                    'targetArn': 'string',
                    'roleArn': 'string',
                    'accessPolicy': 'string',
                    'arn': 'string',
                    'creationTime': 123
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **destinations** *(list) --* 
          

          - *(dict) --* 

            A cross account destination that is the recipient of subscription log events.

            
            

            - **destinationName** *(string) --* 

              Name of the destination.

              
            

            - **targetArn** *(string) --* 

              ARN of the physical target where the log events will be delivered (eg. ARN of a Kinesis stream).

              
            

            - **roleArn** *(string) --* 

              A role for impersonation for delivering log events to the target.

              
            

            - **accessPolicy** *(string) --* 

              An IAM policy document that governs which AWS accounts can create subscription filters against this destination.

              
            

            - **arn** *(string) --* 

              ARN of this destination.

              
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC specifying when this destination was created.

              
        
      
        

        - **nextToken** *(string) --* 

          A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

          
    

  .. py:method:: describe_export_tasks(**kwargs)

    

    Returns all the export tasks that are associated with the AWS account making the request. The export tasks can be filtered based on ``TaskId`` or ``TaskStatus`` .

     

    By default, this operation returns up to 50 export tasks that satisfy the specified filters. If there are more export tasks to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of export tasks returned in the response by specifying the ``limit`` parameter in the request.

    

    **Request Syntax** 
    ::

      response = client.describe_export_tasks(
          taskId='string',
          statusCode='CANCELLED'|'COMPLETED'|'FAILED'|'PENDING'|'PENDING_CANCEL'|'RUNNING',
          nextToken='string',
          limit=123
      )
    :type taskId: string
    :param taskId: 

      Export task that matches the specified task Id will be returned. This can result in zero or one export task.

      

    
    :type statusCode: string
    :param statusCode: 

      All export tasks that matches the specified status code will be returned. This can return zero or more export tasks.

      

    
    :type nextToken: string
    :param nextToken: 

      A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous ``DescribeExportTasks`` request.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of items returned in the response. If you don't specify a value, the request would return up to 50 items.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'exportTasks': [
                {
                    'taskId': 'string',
                    'taskName': 'string',
                    'logGroupName': 'string',
                    'from': 123,
                    'to': 123,
                    'destination': 'string',
                    'destinationPrefix': 'string',
                    'status': {
                        'code': 'CANCELLED'|'COMPLETED'|'FAILED'|'PENDING'|'PENDING_CANCEL'|'RUNNING',
                        'message': 'string'
                    },
                    'executionInfo': {
                        'creationTime': 123,
                        'completionTime': 123
                    }
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **exportTasks** *(list) --* 

          A list of export tasks.

          
          

          - *(dict) --* 

            Represents an export task.

            
            

            - **taskId** *(string) --* 

              Id of the export task.

              
            

            - **taskName** *(string) --* 

              The name of the export task.

              
            

            - **logGroupName** *(string) --* 

              The name of the log group from which logs data was exported.

              
            

            - **from** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp prior to this time are not exported.

              
            

            - **to** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp later than this time are not exported.

              
            

            - **destination** *(string) --* 

              Name of Amazon S3 bucket to which the log data was exported.

              
            

            - **destinationPrefix** *(string) --* 

              Prefix that was used as the start of Amazon S3 key for every object exported.

              
            

            - **status** *(dict) --* 

              Status of the export task.

              
              

              - **code** *(string) --* 

                Status code of the export task.

                
              

              - **message** *(string) --* 

                Status message related to the ``code`` .

                
          
            

            - **executionInfo** *(dict) --* 

              Execution info about the export task.

              
              

              - **creationTime** *(integer) --* 

                A point in time when the export task got created.

                
              

              - **completionTime** *(integer) --* 

                A point in time when the export task got completed.

                
          
        
      
        

        - **nextToken** *(string) --* 

          A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

          
    

  .. py:method:: describe_log_groups(**kwargs)

    

    Returns all the log groups that are associated with the AWS account making the request. The list returned in the response is ASCII-sorted by log group name.

     

    By default, this operation returns up to 50 log groups. If there are more log groups to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of log groups returned in the response by specifying the ``limit`` parameter in the request.

    

    **Request Syntax** 
    ::

      response = client.describe_log_groups(
          logGroupNamePrefix='string',
          nextToken='string',
          limit=123
      )
    :type logGroupNamePrefix: string
    :param logGroupNamePrefix: 

      Will only return log groups that match the provided logGroupNamePrefix. If you don't specify a value, no prefix filter is applied.

      

    
    :type nextToken: string
    :param nextToken: 

      A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous ``DescribeLogGroups`` request.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of items returned in the response. If you don't specify a value, the request would return up to 50 items.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'logGroups': [
                {
                    'logGroupName': 'string',
                    'creationTime': 123,
                    'retentionInDays': 123,
                    'metricFilterCount': 123,
                    'arn': 'string',
                    'storedBytes': 123
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **logGroups** *(list) --* 

          A list of log groups.

          
          

          - *(dict) --* 
            

            - **logGroupName** *(string) --* 
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **retentionInDays** *(integer) --* 

              Specifies the number of days you want to retain log events in the specified log group. Possible values are: 1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, 3653.

              
            

            - **metricFilterCount** *(integer) --* 

              The number of metric filters associated with the log group.

              
            

            - **arn** *(string) --* 
            

            - **storedBytes** *(integer) --* 
        
      
        

        - **nextToken** *(string) --* 

          A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

          
    

  .. py:method:: describe_log_streams(**kwargs)

    

    Returns all the log streams that are associated with the specified log group. The list returned in the response is ASCII-sorted by log stream name.

     

    By default, this operation returns up to 50 log streams. If there are more log streams to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of log streams returned in the response by specifying the ``limit`` parameter in the request. This operation has a limit of five transactions per second, after which transactions are throttled.

    

    **Request Syntax** 
    ::

      response = client.describe_log_streams(
          logGroupName='string',
          logStreamNamePrefix='string',
          orderBy='LogStreamName'|'LastEventTime',
          descending=True|False,
          nextToken='string',
          limit=123
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The log group name for which log streams are to be listed.

      

    
    :type logStreamNamePrefix: string
    :param logStreamNamePrefix: 

      Will only return log streams that match the provided logStreamNamePrefix. If you don't specify a value, no prefix filter is applied.

      

    
    :type orderBy: string
    :param orderBy: 

      Specifies what to order the returned log streams by. Valid arguments are 'LogStreamName' or 'LastEventTime'. If you don't specify a value, results are ordered by LogStreamName. If 'LastEventTime' is chosen, the request cannot also contain a logStreamNamePrefix.

      

    
    :type descending: boolean
    :param descending: 

      If set to true, results are returned in descending order. If you don't specify a value or set it to false, results are returned in ascending order.

      

    
    :type nextToken: string
    :param nextToken: 

      A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous ``DescribeLogStreams`` request.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of items returned in the response. If you don't specify a value, the request would return up to 50 items.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'logStreams': [
                {
                    'logStreamName': 'string',
                    'creationTime': 123,
                    'firstEventTimestamp': 123,
                    'lastEventTimestamp': 123,
                    'lastIngestionTime': 123,
                    'uploadSequenceToken': 'string',
                    'arn': 'string',
                    'storedBytes': 123
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **logStreams** *(list) --* 

          A list of log streams.

          
          

          - *(dict) --* 

            A log stream is sequence of log events from a single emitter of logs.

            
            

            - **logStreamName** *(string) --* 
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **firstEventTimestamp** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **lastEventTimestamp** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **lastIngestionTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **uploadSequenceToken** *(string) --* 

              A string token used for making PutLogEvents requests. A ``sequenceToken`` can only be used once, and PutLogEvents requests must include the ``sequenceToken`` obtained from the response of the previous request.

              
            

            - **arn** *(string) --* 
            

            - **storedBytes** *(integer) --* 
        
      
        

        - **nextToken** *(string) --* 

          A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

          
    

  .. py:method:: describe_metric_filters(**kwargs)

    

    Returns all the metrics filters associated with the specified log group. The list returned in the response is ASCII-sorted by filter name.

     

    By default, this operation returns up to 50 metric filters. If there are more metric filters to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of metric filters returned in the response by specifying the ``limit`` parameter in the request.

    

    **Request Syntax** 
    ::

      response = client.describe_metric_filters(
          logGroupName='string',
          filterNamePrefix='string',
          nextToken='string',
          limit=123
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The log group name for which metric filters are to be listed.

      

    
    :type filterNamePrefix: string
    :param filterNamePrefix: 

      Will only return metric filters that match the provided filterNamePrefix. If you don't specify a value, no prefix filter is applied.

      

    
    :type nextToken: string
    :param nextToken: 

      A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous ``DescribeMetricFilters`` request.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of items returned in the response. If you don't specify a value, the request would return up to 50 items.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'metricFilters': [
                {
                    'filterName': 'string',
                    'filterPattern': 'string',
                    'metricTransformations': [
                        {
                            'metricName': 'string',
                            'metricNamespace': 'string',
                            'metricValue': 'string',
                            'defaultValue': 123.0
                        },
                    ],
                    'creationTime': 123
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **metricFilters** *(list) --* 
          

          - *(dict) --* 

            Metric filters can be used to express how CloudWatch Logs would extract metric observations from ingested log events and transform them to metric data in a CloudWatch metric.

            
            

            - **filterName** *(string) --* 

              A name for a metric or subscription filter.

              
            

            - **filterPattern** *(string) --* 

              A symbolic description of how CloudWatch Logs should interpret the data in each log event. For example, a log event may contain timestamps, IP addresses, strings, and so on. You use the filter pattern to specify what to look for in the log event message.

              
            

            - **metricTransformations** *(list) --* 
              

              - *(dict) --* 
                

                - **metricName** *(string) --* 

                  Name of the metric.

                  
                

                - **metricNamespace** *(string) --* 

                  Namespace to which the metric belongs.

                  
                

                - **metricValue** *(string) --* 

                  A string representing a value to publish to this metric when a filter pattern matches a log event. 

                  
                

                - **defaultValue** *(float) --* 

                  (Optional) A default value to emit when a filter pattern does not match a log event. Can be null.

                  
            
          
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
        
      
        

        - **nextToken** *(string) --* 

          A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

          
    

  .. py:method:: describe_subscription_filters(**kwargs)

    

    Returns all the subscription filters associated with the specified log group. The list returned in the response is ASCII-sorted by filter name.

     

    By default, this operation returns up to 50 subscription filters. If there are more subscription filters to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of subscription filters returned in the response by specifying the ``limit`` parameter in the request.

    

    **Request Syntax** 
    ::

      response = client.describe_subscription_filters(
          logGroupName='string',
          filterNamePrefix='string',
          nextToken='string',
          limit=123
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The log group name for which subscription filters are to be listed.

      

    
    :type filterNamePrefix: string
    :param filterNamePrefix: 

      Will only return subscription filters that match the provided filterNamePrefix. If you don't specify a value, no prefix filter is applied.

      

    
    :type nextToken: string
    :param nextToken: 

      A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of results to return.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'subscriptionFilters': [
                {
                    'filterName': 'string',
                    'logGroupName': 'string',
                    'filterPattern': 'string',
                    'destinationArn': 'string',
                    'roleArn': 'string',
                    'creationTime': 123
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **subscriptionFilters** *(list) --* 
          

          - *(dict) --* 
            

            - **filterName** *(string) --* 

              A name for a metric or subscription filter.

              
            

            - **logGroupName** *(string) --* 
            

            - **filterPattern** *(string) --* 

              A symbolic description of how CloudWatch Logs should interpret the data in each log event. For example, a log event may contain timestamps, IP addresses, strings, and so on. You use the filter pattern to specify what to look for in the log event message.

              
            

            - **destinationArn** *(string) --* 
            

            - **roleArn** *(string) --* 
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
        
      
        

        - **nextToken** *(string) --* 

          A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

          
    

  .. py:method:: filter_log_events(**kwargs)

    

    Retrieves log events, optionally filtered by a filter pattern from the specified log group. You can provide an optional time range to filter the results on the event ``timestamp`` . You can limit the streams searched to an explicit list of ``logStreamNames`` .

     

    By default, this operation returns as much matching log events as can fit in a response size of 1MB, up to 10,000 log events, or all the events found within a time-bounded scan window. If the response includes a ``nextToken`` , then there is more data to search, and the search can be resumed with a new request providing the nextToken. The response will contain a list of ``searchedLogStreams`` that contains information about which streams were searched in the request and whether they have been searched completely or require further pagination. The ``limit`` parameter in the request can be used to specify the maximum number of events to return in a page.

    

    **Request Syntax** 
    ::

      response = client.filter_log_events(
          logGroupName='string',
          logStreamNames=[
              'string',
          ],
          startTime=123,
          endTime=123,
          filterPattern='string',
          nextToken='string',
          limit=123,
          interleaved=True|False
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to query.

      

    
    :type logStreamNames: list
    :param logStreamNames: 

      Optional list of log stream names within the specified log group to search. Defaults to all the log streams in the log group.

      

    
      - *(string) --* 

      
  
    :type startTime: integer
    :param startTime: 

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. If provided, events with a timestamp prior to this time are not returned.

      

    
    :type endTime: integer
    :param endTime: 

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. If provided, events with a timestamp later than this time are not returned.

      

    
    :type filterPattern: string
    :param filterPattern: 

      A valid CloudWatch Logs filter pattern to use for filtering the response. If not provided, all the events are matched.

      

    
    :type nextToken: string
    :param nextToken: 

      A pagination token obtained from a ``FilterLogEvents`` response to continue paginating the FilterLogEvents results. This token is omitted from the response when there are no other events to display.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of events to return in a page of results. Default is 10,000 events.

      

    
    :type interleaved: boolean
    :param interleaved: 

      If provided, the API will make a best effort to provide responses that contain events from multiple log streams within the log group interleaved in a single response. If not provided, all the matched log events in the first log stream will be searched first, then those in the next log stream, etc.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'events': [
                {
                    'logStreamName': 'string',
                    'timestamp': 123,
                    'message': 'string',
                    'ingestionTime': 123,
                    'eventId': 'string'
                },
            ],
            'searchedLogStreams': [
                {
                    'logStreamName': 'string',
                    'searchedCompletely': True|False
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **events** *(list) --* 

          A list of ``FilteredLogEvent`` objects representing the matched events from the request.

          
          

          - *(dict) --* 

            Represents a matched event from a ``FilterLogEvents`` request.

            
            

            - **logStreamName** *(string) --* 

              The name of the log stream this event belongs to.

              
            

            - **timestamp** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **message** *(string) --* 

              The data contained in the log event.

              
            

            - **ingestionTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **eventId** *(string) --* 

              A unique identifier for this event.

              
        
      
        

        - **searchedLogStreams** *(list) --* 

          A list of ``SearchedLogStream`` objects indicating which log streams have been searched in this request and whether each has been searched completely or still has more to be paginated.

          
          

          - *(dict) --* 

            An object indicating the search status of a log stream in a ``FilterLogEvents`` request.

            
            

            - **logStreamName** *(string) --* 

              The name of the log stream.

              
            

            - **searchedCompletely** *(boolean) --* 

              Indicates whether all the events in this log stream were searched or more data exists to search by paginating further.

              
        
      
        

        - **nextToken** *(string) --* 

          A pagination token obtained from a ``FilterLogEvents`` response to continue paginating the FilterLogEvents results. This token is omitted from the response when there are no other events to display.

          
    

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


  .. py:method:: get_log_events(**kwargs)

    

    Retrieves log events from the specified log stream. You can provide an optional time range to filter the results on the event ``timestamp`` .

     

    By default, this operation returns as much log events as can fit in a response size of 1MB, up to 10,000 log events. The response will always include a ``nextForwardToken`` and a ``nextBackwardToken`` in the response body. You can use any of these tokens in subsequent ``GetLogEvents`` requests to paginate through events in either forward or backward direction. You can also limit the number of log events returned in the response by specifying the ``limit`` parameter in the request.

    

    **Request Syntax** 
    ::

      response = client.get_log_events(
          logGroupName='string',
          logStreamName='string',
          startTime=123,
          endTime=123,
          nextToken='string',
          limit=123,
          startFromHead=True|False
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to query.

      

    
    :type logStreamName: string
    :param logStreamName: **[REQUIRED]** 

      The name of the log stream to query.

      

    
    :type startTime: integer
    :param startTime: 

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

    
    :type endTime: integer
    :param endTime: 

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

    
    :type nextToken: string
    :param nextToken: 

      A string token used for pagination that points to the next page of results. It must be a value obtained from the ``nextForwardToken`` or ``nextBackwardToken`` fields in the response of the previous ``GetLogEvents`` request.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of log events returned in the response. If you don't specify a value, the request would return as many log events as can fit in a response size of 1MB, up to 10,000 log events.

      

    
    :type startFromHead: boolean
    :param startFromHead: 

      If set to true, the earliest log events would be returned first. The default is false (the latest log events are returned first).

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'events': [
                {
                    'timestamp': 123,
                    'message': 'string',
                    'ingestionTime': 123
                },
            ],
            'nextForwardToken': 'string',
            'nextBackwardToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **events** *(list) --* 
          

          - *(dict) --* 
            

            - **timestamp** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **message** *(string) --* 
            

            - **ingestionTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
        
      
        

        - **nextForwardToken** *(string) --* 

          A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

          
        

        - **nextBackwardToken** *(string) --* 

          A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

          
    

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

        


  .. py:method:: put_destination(**kwargs)

    

    Creates or updates a ``Destination`` . A destination encapsulates a physical resource (such as a Kinesis stream) and allows you to subscribe to a real-time stream of log events of a different account, ingested through ``PutLogEvents`` requests. Currently, the only supported physical resource is a Amazon Kinesis stream belonging to the same account as the destination.

     

    A destination controls what is written to its Amazon Kinesis stream through an access policy. By default, PutDestination does not set any access policy with the destination, which means a cross-account user will not be able to call ``PutSubscriptionFilter`` against this destination. To enable that, the destination owner must call ``PutDestinationPolicy`` after PutDestination.

    

    **Request Syntax** 
    ::

      response = client.put_destination(
          destinationName='string',
          targetArn='string',
          roleArn='string'
      )
    :type destinationName: string
    :param destinationName: **[REQUIRED]** 

      A name for the destination.

      

    
    :type targetArn: string
    :param targetArn: **[REQUIRED]** 

      The ARN of an Amazon Kinesis stream to deliver matching log events to.

      

    
    :type roleArn: string
    :param roleArn: **[REQUIRED]** 

      The ARN of an IAM role that grants CloudWatch Logs permissions to do Amazon Kinesis PutRecord requests on the destination stream.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'destination': {
                'destinationName': 'string',
                'targetArn': 'string',
                'roleArn': 'string',
                'accessPolicy': 'string',
                'arn': 'string',
                'creationTime': 123
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **destination** *(dict) --* 

          A cross account destination that is the recipient of subscription log events.

          
          

          - **destinationName** *(string) --* 

            Name of the destination.

            
          

          - **targetArn** *(string) --* 

            ARN of the physical target where the log events will be delivered (eg. ARN of a Kinesis stream).

            
          

          - **roleArn** *(string) --* 

            A role for impersonation for delivering log events to the target.

            
          

          - **accessPolicy** *(string) --* 

            An IAM policy document that governs which AWS accounts can create subscription filters against this destination.

            
          

          - **arn** *(string) --* 

            ARN of this destination.

            
          

          - **creationTime** *(integer) --* 

            A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC specifying when this destination was created.

            
      
    

  .. py:method:: put_destination_policy(**kwargs)

    

    Creates or updates an access policy associated with an existing ``Destination`` . An access policy is an `IAM policy document`_ that is used to authorize claims to register a subscription filter against a given destination.

    

    **Request Syntax** 
    ::

      response = client.put_destination_policy(
          destinationName='string',
          accessPolicy='string'
      )
    :type destinationName: string
    :param destinationName: **[REQUIRED]** 

      A name for an existing destination.

      

    
    :type accessPolicy: string
    :param accessPolicy: **[REQUIRED]** 

      An IAM policy document that authorizes cross-account users to deliver their log events to associated destination.

      

    
    
    :returns: None

  .. py:method:: put_log_events(**kwargs)

    

    Uploads a batch of log events to the specified log stream.

     

    Every PutLogEvents request must include the ``sequenceToken`` obtained from the response of the previous request. An upload in a newly created log stream does not require a ``sequenceToken`` . You can also get the ``sequenceToken`` using  DescribeLogStreams .

     

    The batch of events must satisfy the following constraints:

     

     
    * The maximum batch size is 1,048,576 bytes, and this size is calculated as the sum of all event messages in UTF-8, plus 26 bytes for each log event. 
     
    * None of the log events in the batch can be more than 2 hours in the future. 
     
    * None of the log events in the batch can be older than 14 days or the retention period of the log group. 
     
    * The log events in the batch must be in chronological ordered by their ``timestamp`` . 
     
    * The maximum number of log events in a batch is 10,000. 
     
    * A batch of log events in a single PutLogEvents request cannot span more than 24 hours. Otherwise, the PutLogEvents operation will fail. 
     

    

    **Request Syntax** 
    ::

      response = client.put_log_events(
          logGroupName='string',
          logStreamName='string',
          logEvents=[
              {
                  'timestamp': 123,
                  'message': 'string'
              },
          ],
          sequenceToken='string'
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to put log events to.

      

    
    :type logStreamName: string
    :param logStreamName: **[REQUIRED]** 

      The name of the log stream to put log events to.

      

    
    :type logEvents: list
    :param logEvents: **[REQUIRED]** 

      A list of log events belonging to a log stream.

      

    
      - *(dict) --* 

        A log event is a record of some activity that was recorded by the application or resource being monitored. The log event record that CloudWatch Logs understands contains two properties: the timestamp of when the event occurred, and the raw event message.

        

      
        - **timestamp** *(integer) --* **[REQUIRED]** 

          A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

          

        
        - **message** *(string) --* **[REQUIRED]** 

        
      
  
    :type sequenceToken: string
    :param sequenceToken: 

      A string token that must be obtained from the response of the previous ``PutLogEvents`` request.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'nextSequenceToken': 'string',
            'rejectedLogEventsInfo': {
                'tooNewLogEventStartIndex': 123,
                'tooOldLogEventEndIndex': 123,
                'expiredLogEventEndIndex': 123
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **nextSequenceToken** *(string) --* 

          A string token used for making PutLogEvents requests. A ``sequenceToken`` can only be used once, and PutLogEvents requests must include the ``sequenceToken`` obtained from the response of the previous request.

          
        

        - **rejectedLogEventsInfo** *(dict) --* 
          

          - **tooNewLogEventStartIndex** *(integer) --* 
          

          - **tooOldLogEventEndIndex** *(integer) --* 
          

          - **expiredLogEventEndIndex** *(integer) --* 
      
    

  .. py:method:: put_metric_filter(**kwargs)

    

    Creates or updates a metric filter and associates it with the specified log group. Metric filters allow you to configure rules to extract metric data from log events ingested through ``PutLogEvents`` requests.

     

    The maximum number of metric filters that can be associated with a log group is 100.

    

    **Request Syntax** 
    ::

      response = client.put_metric_filter(
          logGroupName='string',
          filterName='string',
          filterPattern='string',
          metricTransformations=[
              {
                  'metricName': 'string',
                  'metricNamespace': 'string',
                  'metricValue': 'string',
                  'defaultValue': 123.0
              },
          ]
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to associate the metric filter with.

      

    
    :type filterName: string
    :param filterName: **[REQUIRED]** 

      A name for the metric filter.

      

    
    :type filterPattern: string
    :param filterPattern: **[REQUIRED]** 

      A valid CloudWatch Logs filter pattern for extracting metric data out of ingested log events.

      

    
    :type metricTransformations: list
    :param metricTransformations: **[REQUIRED]** 

      A collection of information needed to define how metric data gets emitted.

      

    
      - *(dict) --* 

      
        - **metricName** *(string) --* **[REQUIRED]** 

          Name of the metric.

          

        
        - **metricNamespace** *(string) --* **[REQUIRED]** 

          Namespace to which the metric belongs.

          

        
        - **metricValue** *(string) --* **[REQUIRED]** 

          A string representing a value to publish to this metric when a filter pattern matches a log event. 

          

        
        - **defaultValue** *(float) --* 

          (Optional) A default value to emit when a filter pattern does not match a log event. Can be null.

          

        
      
  
    
    :returns: None

  .. py:method:: put_retention_policy(**kwargs)

    

    Sets the retention of the specified log group. A retention policy allows you to configure the number of days you want to retain log events in the specified log group.

    

    **Request Syntax** 
    ::

      response = client.put_retention_policy(
          logGroupName='string',
          retentionInDays=123
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to associate the retention policy with.

      

    
    :type retentionInDays: integer
    :param retentionInDays: **[REQUIRED]** 

      Specifies the number of days you want to retain log events in the specified log group. Possible values are: 1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, 3653.

      

    
    
    :returns: None

  .. py:method:: put_subscription_filter(**kwargs)

    

    Creates or updates a subscription filter and associates it with the specified log group. Subscription filters allow you to subscribe to a real-time stream of log events ingested through ``PutLogEvents`` requests and have them delivered to a specific destination. Currently, the supported destinations are:

     

     
    * An Amazon Kinesis stream belonging to the same account as the subscription filter, for same-account delivery. 
     
    * A logical destination (used via an ARN of ``Destination`` ) belonging to a different account, for cross-account delivery. 
     
    * An Amazon Kinesis Firehose stream belonging to the same account as the subscription filter, for same-account delivery. 
     
    * An AWS Lambda function belonging to the same account as the subscription filter, for same-account delivery. 
     

     

    Currently there can only be one subscription filter associated with a log group.

    

    **Request Syntax** 
    ::

      response = client.put_subscription_filter(
          logGroupName='string',
          filterName='string',
          filterPattern='string',
          destinationArn='string',
          roleArn='string'
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to associate the subscription filter with.

      

    
    :type filterName: string
    :param filterName: **[REQUIRED]** 

      A name for the subscription filter.

      

    
    :type filterPattern: string
    :param filterPattern: **[REQUIRED]** 

      A valid CloudWatch Logs filter pattern for subscribing to a filtered stream of log events.

      

    
    :type destinationArn: string
    :param destinationArn: **[REQUIRED]** 

      The ARN of the destination to deliver matching log events to. Currently, the supported destinations are:

       

       
      * An Amazon Kinesis stream belonging to the same account as the subscription filter, for same-account delivery. 
       
      * A logical destination (used via an ARN of ``Destination`` ) belonging to a different account, for cross-account delivery. 
       
      * An Amazon Kinesis Firehose stream belonging to the same account as the subscription filter, for same-account delivery. 
       
      * An AWS Lambda function belonging to the same account as the subscription filter, for same-account delivery. 
       

      

    
    :type roleArn: string
    :param roleArn: 

      The ARN of an IAM role that grants CloudWatch Logs permissions to deliver ingested log events to the destination stream. You don't need to provide the ARN when you are working with a logical destination (used via an ARN of ``Destination`` ) for cross-account delivery.

      

    
    
    :returns: None

  .. py:method:: test_metric_filter(**kwargs)

    

    Tests the filter pattern of a metric filter against a sample of log event messages. You can use this operation to validate the correctness of a metric filter pattern.

    

    **Request Syntax** 
    ::

      response = client.test_metric_filter(
          filterPattern='string',
          logEventMessages=[
              'string',
          ]
      )
    :type filterPattern: string
    :param filterPattern: **[REQUIRED]** 

      A symbolic description of how CloudWatch Logs should interpret the data in each log event. For example, a log event may contain timestamps, IP addresses, strings, and so on. You use the filter pattern to specify what to look for in the log event message.

      

    
    :type logEventMessages: list
    :param logEventMessages: **[REQUIRED]** 

      A list of log event messages to test.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'matches': [
                {
                    'eventNumber': 123,
                    'eventMessage': 'string',
                    'extractedValues': {
                        'string': 'string'
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **matches** *(list) --* 
          

          - *(dict) --* 
            

            - **eventNumber** *(integer) --* 
            

            - **eventMessage** *(string) --* 
            

            - **extractedValues** *(dict) --* 
              

              - *(string) --* 
                

                - *(string) --* 
          
        
        
      
    

==========
Paginators
==========


The available paginators are:

* :py:class:`CloudWatchLogs.Paginator.DescribeDestinations`


* :py:class:`CloudWatchLogs.Paginator.DescribeLogGroups`


* :py:class:`CloudWatchLogs.Paginator.DescribeLogStreams`


* :py:class:`CloudWatchLogs.Paginator.DescribeMetricFilters`


* :py:class:`CloudWatchLogs.Paginator.DescribeSubscriptionFilters`


* :py:class:`CloudWatchLogs.Paginator.FilterLogEvents`



.. py:class:: CloudWatchLogs.Paginator.DescribeDestinations

  ::

    
    paginator = client.get_paginator('describe_destinations')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudWatchLogs.Client.describe_destinations`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DestinationNamePrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type DestinationNamePrefix: string
    :param DestinationNamePrefix: 

      Will only return destinations that match the provided destinationNamePrefix. If you don't specify a value, no prefix is applied.

      

    
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
            'destinations': [
                {
                    'destinationName': 'string',
                    'targetArn': 'string',
                    'roleArn': 'string',
                    'accessPolicy': 'string',
                    'arn': 'string',
                    'creationTime': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **destinations** *(list) --* 
          

          - *(dict) --* 

            A cross account destination that is the recipient of subscription log events.

            
            

            - **destinationName** *(string) --* 

              Name of the destination.

              
            

            - **targetArn** *(string) --* 

              ARN of the physical target where the log events will be delivered (eg. ARN of a Kinesis stream).

              
            

            - **roleArn** *(string) --* 

              A role for impersonation for delivering log events to the target.

              
            

            - **accessPolicy** *(string) --* 

              An IAM policy document that governs which AWS accounts can create subscription filters against this destination.

              
            

            - **arn** *(string) --* 

              ARN of this destination.

              
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC specifying when this destination was created.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: CloudWatchLogs.Paginator.DescribeLogGroups

  ::

    
    paginator = client.get_paginator('describe_log_groups')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudWatchLogs.Client.describe_log_groups`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          logGroupNamePrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type logGroupNamePrefix: string
    :param logGroupNamePrefix: 

      Will only return log groups that match the provided logGroupNamePrefix. If you don't specify a value, no prefix filter is applied.

      

    
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
            'logGroups': [
                {
                    'logGroupName': 'string',
                    'creationTime': 123,
                    'retentionInDays': 123,
                    'metricFilterCount': 123,
                    'arn': 'string',
                    'storedBytes': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **logGroups** *(list) --* 

          A list of log groups.

          
          

          - *(dict) --* 
            

            - **logGroupName** *(string) --* 
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **retentionInDays** *(integer) --* 

              Specifies the number of days you want to retain log events in the specified log group. Possible values are: 1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, 3653.

              
            

            - **metricFilterCount** *(integer) --* 

              The number of metric filters associated with the log group.

              
            

            - **arn** *(string) --* 
            

            - **storedBytes** *(integer) --* 
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: CloudWatchLogs.Paginator.DescribeLogStreams

  ::

    
    paginator = client.get_paginator('describe_log_streams')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudWatchLogs.Client.describe_log_streams`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          logGroupName='string',
          logStreamNamePrefix='string',
          orderBy='LogStreamName'|'LastEventTime',
          descending=True|False,
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The log group name for which log streams are to be listed.

      

    
    :type logStreamNamePrefix: string
    :param logStreamNamePrefix: 

      Will only return log streams that match the provided logStreamNamePrefix. If you don't specify a value, no prefix filter is applied.

      

    
    :type orderBy: string
    :param orderBy: 

      Specifies what to order the returned log streams by. Valid arguments are 'LogStreamName' or 'LastEventTime'. If you don't specify a value, results are ordered by LogStreamName. If 'LastEventTime' is chosen, the request cannot also contain a logStreamNamePrefix.

      

    
    :type descending: boolean
    :param descending: 

      If set to true, results are returned in descending order. If you don't specify a value or set it to false, results are returned in ascending order.

      

    
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
            'logStreams': [
                {
                    'logStreamName': 'string',
                    'creationTime': 123,
                    'firstEventTimestamp': 123,
                    'lastEventTimestamp': 123,
                    'lastIngestionTime': 123,
                    'uploadSequenceToken': 'string',
                    'arn': 'string',
                    'storedBytes': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **logStreams** *(list) --* 

          A list of log streams.

          
          

          - *(dict) --* 

            A log stream is sequence of log events from a single emitter of logs.

            
            

            - **logStreamName** *(string) --* 
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **firstEventTimestamp** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **lastEventTimestamp** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **lastIngestionTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **uploadSequenceToken** *(string) --* 

              A string token used for making PutLogEvents requests. A ``sequenceToken`` can only be used once, and PutLogEvents requests must include the ``sequenceToken`` obtained from the response of the previous request.

              
            

            - **arn** *(string) --* 
            

            - **storedBytes** *(integer) --* 
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: CloudWatchLogs.Paginator.DescribeMetricFilters

  ::

    
    paginator = client.get_paginator('describe_metric_filters')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudWatchLogs.Client.describe_metric_filters`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          logGroupName='string',
          filterNamePrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The log group name for which metric filters are to be listed.

      

    
    :type filterNamePrefix: string
    :param filterNamePrefix: 

      Will only return metric filters that match the provided filterNamePrefix. If you don't specify a value, no prefix filter is applied.

      

    
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
            'metricFilters': [
                {
                    'filterName': 'string',
                    'filterPattern': 'string',
                    'metricTransformations': [
                        {
                            'metricName': 'string',
                            'metricNamespace': 'string',
                            'metricValue': 'string',
                            'defaultValue': 123.0
                        },
                    ],
                    'creationTime': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **metricFilters** *(list) --* 
          

          - *(dict) --* 

            Metric filters can be used to express how CloudWatch Logs would extract metric observations from ingested log events and transform them to metric data in a CloudWatch metric.

            
            

            - **filterName** *(string) --* 

              A name for a metric or subscription filter.

              
            

            - **filterPattern** *(string) --* 

              A symbolic description of how CloudWatch Logs should interpret the data in each log event. For example, a log event may contain timestamps, IP addresses, strings, and so on. You use the filter pattern to specify what to look for in the log event message.

              
            

            - **metricTransformations** *(list) --* 
              

              - *(dict) --* 
                

                - **metricName** *(string) --* 

                  Name of the metric.

                  
                

                - **metricNamespace** *(string) --* 

                  Namespace to which the metric belongs.

                  
                

                - **metricValue** *(string) --* 

                  A string representing a value to publish to this metric when a filter pattern matches a log event. 

                  
                

                - **defaultValue** *(float) --* 

                  (Optional) A default value to emit when a filter pattern does not match a log event. Can be null.

                  
            
          
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: CloudWatchLogs.Paginator.DescribeSubscriptionFilters

  ::

    
    paginator = client.get_paginator('describe_subscription_filters')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudWatchLogs.Client.describe_subscription_filters`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          logGroupName='string',
          filterNamePrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The log group name for which subscription filters are to be listed.

      

    
    :type filterNamePrefix: string
    :param filterNamePrefix: 

      Will only return subscription filters that match the provided filterNamePrefix. If you don't specify a value, no prefix filter is applied.

      

    
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
            'subscriptionFilters': [
                {
                    'filterName': 'string',
                    'logGroupName': 'string',
                    'filterPattern': 'string',
                    'destinationArn': 'string',
                    'roleArn': 'string',
                    'creationTime': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **subscriptionFilters** *(list) --* 
          

          - *(dict) --* 
            

            - **filterName** *(string) --* 

              A name for a metric or subscription filter.

              
            

            - **logGroupName** *(string) --* 
            

            - **filterPattern** *(string) --* 

              A symbolic description of how CloudWatch Logs should interpret the data in each log event. For example, a log event may contain timestamps, IP addresses, strings, and so on. You use the filter pattern to specify what to look for in the log event message.

              
            

            - **destinationArn** *(string) --* 
            

            - **roleArn** *(string) --* 
            

            - **creationTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: CloudWatchLogs.Paginator.FilterLogEvents

  ::

    
    paginator = client.get_paginator('filter_log_events')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudWatchLogs.Client.filter_log_events`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          logGroupName='string',
          logStreamNames=[
              'string',
          ],
          startTime=123,
          endTime=123,
          filterPattern='string',
          interleaved=True|False,
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type logGroupName: string
    :param logGroupName: **[REQUIRED]** 

      The name of the log group to query.

      

    
    :type logStreamNames: list
    :param logStreamNames: 

      Optional list of log stream names within the specified log group to search. Defaults to all the log streams in the log group.

      

    
      - *(string) --* 

      
  
    :type startTime: integer
    :param startTime: 

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. If provided, events with a timestamp prior to this time are not returned.

      

    
    :type endTime: integer
    :param endTime: 

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. If provided, events with a timestamp later than this time are not returned.

      

    
    :type filterPattern: string
    :param filterPattern: 

      A valid CloudWatch Logs filter pattern to use for filtering the response. If not provided, all the events are matched.

      

    
    :type interleaved: boolean
    :param interleaved: 

      If provided, the API will make a best effort to provide responses that contain events from multiple log streams within the log group interleaved in a single response. If not provided, all the matched log events in the first log stream will be searched first, then those in the next log stream, etc.

      

    
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
            'events': [
                {
                    'logStreamName': 'string',
                    'timestamp': 123,
                    'message': 'string',
                    'ingestionTime': 123,
                    'eventId': 'string'
                },
            ],
            'searchedLogStreams': [
                {
                    'logStreamName': 'string',
                    'searchedCompletely': True|False
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **events** *(list) --* 

          A list of ``FilteredLogEvent`` objects representing the matched events from the request.

          
          

          - *(dict) --* 

            Represents a matched event from a ``FilterLogEvents`` request.

            
            

            - **logStreamName** *(string) --* 

              The name of the log stream this event belongs to.

              
            

            - **timestamp** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **message** *(string) --* 

              The data contained in the log event.

              
            

            - **ingestionTime** *(integer) --* 

              A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

              
            

            - **eventId** *(string) --* 

              A unique identifier for this event.

              
        
      
        

        - **searchedLogStreams** *(list) --* 

          A list of ``SearchedLogStream`` objects indicating which log streams have been searched in this request and whether each has been searched completely or still has more to be paginated.

          
          

          - *(dict) --* 

            An object indicating the search status of a log stream in a ``FilterLogEvents`` request.

            
            

            - **logStreamName** *(string) --* 

              The name of the log stream.

              
            

            - **searchedCompletely** *(boolean) --* 

              Indicates whether all the events in this log stream were searched or more data exists to search by paginating further.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    