

.. _Amazon S3 Object Name Format: http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html
.. _Amazon S3 Backup for Amazon Elasticsearch Service Destination: http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html#es-s3-backup
.. _Amazon Kinesis Firehose Limits: http://docs.aws.amazon.com/firehose/latest/dev/limits.html
.. _Amazon Kinesis Firehose Developer Guide: http://docs.aws.amazon.com/firehose/latest/dev/
.. _Amazon S3 Bucket Access: http://docs.aws.amazon.com/firehose/latest/dev/controlling-access.html#using-iam-s3
.. _Amazon Redshift COPY command: http://docs.aws.amazon.com/redshift/latest/dg/r_COPY.html
.. _Index Rotation for Amazon Elasticsearch Service Destination: http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html#es-index-rotation
.. _Amazon Redshift COPY command examples: http://docs.aws.amazon.com/redshift/latest/dg/r_COPY_command_examples.html


********
Firehose
********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: Firehose.Client

  A low-level client representing Amazon Kinesis Firehose::

    
    import boto3
    
    client = boto3.client('firehose')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_delivery_stream`

  
  *   :py:meth:`delete_delivery_stream`

  
  *   :py:meth:`describe_delivery_stream`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_delivery_streams`

  
  *   :py:meth:`put_record`

  
  *   :py:meth:`put_record_batch`

  
  *   :py:meth:`update_destination`

  

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


  .. py:method:: create_delivery_stream(**kwargs)

    

    Creates a delivery stream.

     

      CreateDeliveryStream is an asynchronous operation that immediately returns. The initial status of the delivery stream is ``CREATING`` . After the delivery stream is created, its status is ``ACTIVE`` and it now accepts data. Attempts to send data to a delivery stream that is not in the ``ACTIVE`` state cause an exception. To check the state of a delivery stream, use  DescribeDeliveryStream .

     

    The name of a delivery stream identifies it. You can't have two delivery streams with the same name in the same region. Two delivery streams in different AWS accounts or different regions in the same AWS account can have the same name.

     

    By default, you can create up to 20 delivery streams per region.

     

    A delivery stream can only be configured with a single destination, Amazon S3, Amazon Elasticsearch Service, or Amazon Redshift. For correct  CreateDeliveryStream request syntax, specify only one destination configuration parameter: either **S3DestinationConfiguration** , **ElasticsearchDestinationConfiguration** , or **RedshiftDestinationConfiguration** . 

     

    As part of **S3DestinationConfiguration** , optional values **BufferingHints** , **EncryptionConfiguration** , and **CompressionFormat** can be provided. By default, if no **BufferingHints** value is provided, Firehose buffers data up to 5 MB or for 5 minutes, whichever condition is satisfied first. Note that **BufferingHints** is a hint, so there are some cases where the service cannot adhere to these conditions strictly; for example, record boundaries are such that the size is a little over or under the configured buffering size. By default, no encryption is performed. We strongly recommend that you enable encryption to ensure secure data storage in Amazon S3.

     

    A few notes about **RedshiftDestinationConfiguration** :

     

     
    * An Amazon Redshift destination requires an S3 bucket as intermediate location, as Firehose first delivers data to S3 and then uses ``COPY`` syntax to load data into an Amazon Redshift table. This is specified in the **RedshiftDestinationConfiguration.S3Configuration** parameter element. 
     
    * The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified in **RedshiftDestinationConfiguration.S3Configuration** because the Amazon Redshift ``COPY`` operation that reads from the S3 bucket doesn't support these compression formats. 
     
    * We strongly recommend that the username and password provided is used exclusively for Firehose purposes, and that the permissions for the account are restricted for Amazon Redshift ``INSERT`` permissions. 
     

     

    Firehose assumes the IAM role that is configured as part of destinations. The IAM role should allow the Firehose principal to assume the role, and the role should have permissions that allows the service to deliver the data. For more information, see `Amazon S3 Bucket Access`_ in the *Amazon Kinesis Firehose Developer Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_delivery_stream(
          DeliveryStreamName='string',
          S3DestinationConfiguration={
              'RoleARN': 'string',
              'BucketARN': 'string',
              'Prefix': 'string',
              'BufferingHints': {
                  'SizeInMBs': 123,
                  'IntervalInSeconds': 123
              },
              'CompressionFormat': 'UNCOMPRESSED'|'GZIP'|'ZIP'|'Snappy',
              'EncryptionConfiguration': {
                  'NoEncryptionConfig': 'NoEncryption',
                  'KMSEncryptionConfig': {
                      'AWSKMSKeyARN': 'string'
                  }
              },
              'CloudWatchLoggingOptions': {
                  'Enabled': True|False,
                  'LogGroupName': 'string',
                  'LogStreamName': 'string'
              }
          },
          RedshiftDestinationConfiguration={
              'RoleARN': 'string',
              'ClusterJDBCURL': 'string',
              'CopyCommand': {
                  'DataTableName': 'string',
                  'DataTableColumns': 'string',
                  'CopyOptions': 'string'
              },
              'Username': 'string',
              'Password': 'string',
              'RetryOptions': {
                  'DurationInSeconds': 123
              },
              'S3Configuration': {
                  'RoleARN': 'string',
                  'BucketARN': 'string',
                  'Prefix': 'string',
                  'BufferingHints': {
                      'SizeInMBs': 123,
                      'IntervalInSeconds': 123
                  },
                  'CompressionFormat': 'UNCOMPRESSED'|'GZIP'|'ZIP'|'Snappy',
                  'EncryptionConfiguration': {
                      'NoEncryptionConfig': 'NoEncryption',
                      'KMSEncryptionConfig': {
                          'AWSKMSKeyARN': 'string'
                      }
                  },
                  'CloudWatchLoggingOptions': {
                      'Enabled': True|False,
                      'LogGroupName': 'string',
                      'LogStreamName': 'string'
                  }
              },
              'CloudWatchLoggingOptions': {
                  'Enabled': True|False,
                  'LogGroupName': 'string',
                  'LogStreamName': 'string'
              }
          },
          ElasticsearchDestinationConfiguration={
              'RoleARN': 'string',
              'DomainARN': 'string',
              'IndexName': 'string',
              'TypeName': 'string',
              'IndexRotationPeriod': 'NoRotation'|'OneHour'|'OneDay'|'OneWeek'|'OneMonth',
              'BufferingHints': {
                  'IntervalInSeconds': 123,
                  'SizeInMBs': 123
              },
              'RetryOptions': {
                  'DurationInSeconds': 123
              },
              'S3BackupMode': 'FailedDocumentsOnly'|'AllDocuments',
              'S3Configuration': {
                  'RoleARN': 'string',
                  'BucketARN': 'string',
                  'Prefix': 'string',
                  'BufferingHints': {
                      'SizeInMBs': 123,
                      'IntervalInSeconds': 123
                  },
                  'CompressionFormat': 'UNCOMPRESSED'|'GZIP'|'ZIP'|'Snappy',
                  'EncryptionConfiguration': {
                      'NoEncryptionConfig': 'NoEncryption',
                      'KMSEncryptionConfig': {
                          'AWSKMSKeyARN': 'string'
                      }
                  },
                  'CloudWatchLoggingOptions': {
                      'Enabled': True|False,
                      'LogGroupName': 'string',
                      'LogStreamName': 'string'
                  }
              },
              'CloudWatchLoggingOptions': {
                  'Enabled': True|False,
                  'LogGroupName': 'string',
                  'LogStreamName': 'string'
              }
          }
      )
    :type DeliveryStreamName: string
    :param DeliveryStreamName: **[REQUIRED]** 

      The name of the delivery stream.

      

    
    :type S3DestinationConfiguration: dict
    :param S3DestinationConfiguration: 

      The destination in Amazon S3. This value must be specified if **ElasticsearchDestinationConfiguration** or **RedshiftDestinationConfiguration** is specified (see restrictions listed above).

      

    
      - **RoleARN** *(string) --* **[REQUIRED]** 

        The ARN of the AWS credentials.

        

      
      - **BucketARN** *(string) --* **[REQUIRED]** 

        The ARN of the S3 bucket.

        

      
      - **Prefix** *(string) --* 

        The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `Amazon Kinesis Firehose Developer Guide`_ .

        

      
      - **BufferingHints** *(dict) --* 

        The buffering option. If no value is specified, **BufferingHints** object default values are used.

        

      
        - **SizeInMBs** *(integer) --* 

          Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

           

          We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

          

        
        - **IntervalInSeconds** *(integer) --* 

          Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

          

        
      
      - **CompressionFormat** *(string) --* 

        The compression format. If no value is specified, the default is ``UNCOMPRESSED`` .

         

        The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified for Amazon Redshift destinations because they are not supported by the Amazon Redshift ``COPY`` operation that reads from the S3 bucket.

        

      
      - **EncryptionConfiguration** *(dict) --* 

        The encryption configuration. If no value is specified, the default is no encryption.

        

      
        - **NoEncryptionConfig** *(string) --* 

          Specifically override existing encryption information to ensure no encryption is used.

          

        
        - **KMSEncryptionConfig** *(dict) --* 

          The encryption key.

          

        
          - **AWSKMSKeyARN** *(string) --* **[REQUIRED]** 

            The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

            

          
        
      
      - **CloudWatchLoggingOptions** *(dict) --* 

        Describes CloudWatch logging options for your delivery stream.

        

      
        - **Enabled** *(boolean) --* 

          Enables or disables CloudWatch logging.

          

        
        - **LogGroupName** *(string) --* 

          The CloudWatch group name for logging. This value is required if Enabled is true.

          

        
        - **LogStreamName** *(string) --* 

          The CloudWatch log stream name for logging. This value is required if Enabled is true.

          

        
      
    
    :type RedshiftDestinationConfiguration: dict
    :param RedshiftDestinationConfiguration: 

      The destination in Amazon Redshift. This value cannot be specified if Amazon S3 or Amazon Elasticsearch is the desired destination (see restrictions listed above).

      

    
      - **RoleARN** *(string) --* **[REQUIRED]** 

        The ARN of the AWS credentials.

        

      
      - **ClusterJDBCURL** *(string) --* **[REQUIRED]** 

        The database connection string.

        

      
      - **CopyCommand** *(dict) --* **[REQUIRED]** 

        The ``COPY`` command.

        

      
        - **DataTableName** *(string) --* **[REQUIRED]** 

          The name of the target table. The table must already exist in the database.

          

        
        - **DataTableColumns** *(string) --* 

          A comma-separated list of column names.

          

        
        - **CopyOptions** *(string) --* 

          Optional parameters to use with the Amazon Redshift ``COPY`` command. For more information, see the "Optional Parameters" section of `Amazon Redshift COPY command`_ . Some possible examples that would apply to Firehose are as follows.

           

           ``delimiter '\t' lzop;`` - fields are delimited with "\t" (TAB character) and compressed using lzop.

           

           ``delimiter '|`` - fields are delimited with "|" (this is the default delimiter).

           

           ``delimiter '|' escape`` - the delimiter should be escaped.

           

           ``fixedwidth 'venueid:3,venuename:25,venuecity:12,venuestate:2,venueseats:6'`` - fields are fixed width in the source, with each width specified after every column in the table.

           

           ``JSON 's3://mybucket/jsonpaths.txt'`` - data is in JSON format, and the path specified is the format of the data.

           

          For more examples, see `Amazon Redshift COPY command examples`_ .

          

        
      
      - **Username** *(string) --* **[REQUIRED]** 

        The name of the user.

        

      
      - **Password** *(string) --* **[REQUIRED]** 

        The user password.

        

      
      - **RetryOptions** *(dict) --* 

        Configures retry behavior in the event that Firehose is unable to deliver documents to Amazon Redshift. Default value is 3600 (60 minutes).

        

      
        - **DurationInSeconds** *(integer) --* 

          The length of time during which Firehose retries delivery after a failure, starting from the initial request and including the first attempt. The default value is 3600 seconds (60 minutes). Firehose does not retry if the value of ``DurationInSeconds`` is 0 (zero) or if the first delivery attempt takes longer than the current value.

          

        
      
      - **S3Configuration** *(dict) --* **[REQUIRED]** 

        The S3 configuration for the intermediate location from which Amazon Redshift obtains data. Restrictions are described in the topic for  CreateDeliveryStream .

         

        The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified in **RedshiftDestinationConfiguration.S3Configuration** because the Amazon Redshift ``COPY`` operation that reads from the S3 bucket doesn't support these compression formats.

        

      
        - **RoleARN** *(string) --* **[REQUIRED]** 

          The ARN of the AWS credentials.

          

        
        - **BucketARN** *(string) --* **[REQUIRED]** 

          The ARN of the S3 bucket.

          

        
        - **Prefix** *(string) --* 

          The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `Amazon Kinesis Firehose Developer Guide`_ .

          

        
        - **BufferingHints** *(dict) --* 

          The buffering option. If no value is specified, **BufferingHints** object default values are used.

          

        
          - **SizeInMBs** *(integer) --* 

            Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

             

            We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

            

          
          - **IntervalInSeconds** *(integer) --* 

            Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

            

          
        
        - **CompressionFormat** *(string) --* 

          The compression format. If no value is specified, the default is ``UNCOMPRESSED`` .

           

          The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified for Amazon Redshift destinations because they are not supported by the Amazon Redshift ``COPY`` operation that reads from the S3 bucket.

          

        
        - **EncryptionConfiguration** *(dict) --* 

          The encryption configuration. If no value is specified, the default is no encryption.

          

        
          - **NoEncryptionConfig** *(string) --* 

            Specifically override existing encryption information to ensure no encryption is used.

            

          
          - **KMSEncryptionConfig** *(dict) --* 

            The encryption key.

            

          
            - **AWSKMSKeyARN** *(string) --* **[REQUIRED]** 

              The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

              

            
          
        
        - **CloudWatchLoggingOptions** *(dict) --* 

          Describes CloudWatch logging options for your delivery stream.

          

        
          - **Enabled** *(boolean) --* 

            Enables or disables CloudWatch logging.

            

          
          - **LogGroupName** *(string) --* 

            The CloudWatch group name for logging. This value is required if Enabled is true.

            

          
          - **LogStreamName** *(string) --* 

            The CloudWatch log stream name for logging. This value is required if Enabled is true.

            

          
        
      
      - **CloudWatchLoggingOptions** *(dict) --* 

        Describes CloudWatch logging options for your delivery stream.

        

      
        - **Enabled** *(boolean) --* 

          Enables or disables CloudWatch logging.

          

        
        - **LogGroupName** *(string) --* 

          The CloudWatch group name for logging. This value is required if Enabled is true.

          

        
        - **LogStreamName** *(string) --* 

          The CloudWatch log stream name for logging. This value is required if Enabled is true.

          

        
      
    
    :type ElasticsearchDestinationConfiguration: dict
    :param ElasticsearchDestinationConfiguration: 

      The destination in Amazon ES. This value cannot be specified if Amazon S3 or Amazon Redshift is the desired destination (see restrictions listed above).

      

    
      - **RoleARN** *(string) --* **[REQUIRED]** 

        The ARN of the IAM role to be assumed by Firehose for calling the Amazon ES Configuration API and for indexing documents. For more information, see `Amazon S3 Bucket Access`_ .

        

      
      - **DomainARN** *(string) --* **[REQUIRED]** 

        The ARN of the Amazon ES domain. The IAM role must have permission for ``DescribeElasticsearchDomain`` , ``DescribeElasticsearchDomains`` , and ``DescribeElasticsearchDomainConfig`` after assuming **RoleARN** .

        

      
      - **IndexName** *(string) --* **[REQUIRED]** 

        The Elasticsearch index name.

        

      
      - **TypeName** *(string) --* **[REQUIRED]** 

        The Elasticsearch type name.

        

      
      - **IndexRotationPeriod** *(string) --* 

        The Elasticsearch index rotation period. Index rotation appends a timestamp to the IndexName to facilitate expiration of old data. For more information, see `Index Rotation for Amazon Elasticsearch Service Destination`_ . Default value is ``OneDay`` .

        

      
      - **BufferingHints** *(dict) --* 

        Buffering options. If no value is specified, **ElasticsearchBufferingHints** object default values are used. 

        

      
        - **IntervalInSeconds** *(integer) --* 

          Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300 (5 minutes).

          

        
        - **SizeInMBs** *(integer) --* 

          Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

           

          We recommend setting **SizeInMBs** to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, set **SizeInMBs** to be 10 MB or higher.

          

        
      
      - **RetryOptions** *(dict) --* 

        Configures retry behavior in the event that Firehose is unable to deliver documents to Amazon ES. Default value is 300 (5 minutes).

        

      
        - **DurationInSeconds** *(integer) --* 

          After an initial failure to deliver to Amazon ES, the total amount of time during which Firehose re-attempts delivery (including the first attempt). After this time has elapsed, the failed documents are written to Amazon S3. Default value is 300 seconds (5 minutes). A value of 0 (zero) results in no retries.

          

        
      
      - **S3BackupMode** *(string) --* 

        Defines how documents should be delivered to Amazon S3. When set to FailedDocumentsOnly, Firehose writes any documents that could not be indexed to the configured Amazon S3 destination, with elasticsearch-failed/ appended to the key prefix. When set to AllDocuments, Firehose delivers all incoming records to Amazon S3, and also writes failed documents with elasticsearch-failed/ appended to the prefix. For more information, see `Amazon S3 Backup for Amazon Elasticsearch Service Destination`_ . Default value is FailedDocumentsOnly.

        

      
      - **S3Configuration** *(dict) --* **[REQUIRED]** 

        Describes the configuration of a destination in Amazon S3.

        

      
        - **RoleARN** *(string) --* **[REQUIRED]** 

          The ARN of the AWS credentials.

          

        
        - **BucketARN** *(string) --* **[REQUIRED]** 

          The ARN of the S3 bucket.

          

        
        - **Prefix** *(string) --* 

          The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `Amazon Kinesis Firehose Developer Guide`_ .

          

        
        - **BufferingHints** *(dict) --* 

          The buffering option. If no value is specified, **BufferingHints** object default values are used.

          

        
          - **SizeInMBs** *(integer) --* 

            Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

             

            We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

            

          
          - **IntervalInSeconds** *(integer) --* 

            Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

            

          
        
        - **CompressionFormat** *(string) --* 

          The compression format. If no value is specified, the default is ``UNCOMPRESSED`` .

           

          The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified for Amazon Redshift destinations because they are not supported by the Amazon Redshift ``COPY`` operation that reads from the S3 bucket.

          

        
        - **EncryptionConfiguration** *(dict) --* 

          The encryption configuration. If no value is specified, the default is no encryption.

          

        
          - **NoEncryptionConfig** *(string) --* 

            Specifically override existing encryption information to ensure no encryption is used.

            

          
          - **KMSEncryptionConfig** *(dict) --* 

            The encryption key.

            

          
            - **AWSKMSKeyARN** *(string) --* **[REQUIRED]** 

              The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

              

            
          
        
        - **CloudWatchLoggingOptions** *(dict) --* 

          Describes CloudWatch logging options for your delivery stream.

          

        
          - **Enabled** *(boolean) --* 

            Enables or disables CloudWatch logging.

            

          
          - **LogGroupName** *(string) --* 

            The CloudWatch group name for logging. This value is required if Enabled is true.

            

          
          - **LogStreamName** *(string) --* 

            The CloudWatch log stream name for logging. This value is required if Enabled is true.

            

          
        
      
      - **CloudWatchLoggingOptions** *(dict) --* 

        Describes CloudWatch logging options for your delivery stream.

        

      
        - **Enabled** *(boolean) --* 

          Enables or disables CloudWatch logging.

          

        
        - **LogGroupName** *(string) --* 

          The CloudWatch group name for logging. This value is required if Enabled is true.

          

        
        - **LogStreamName** *(string) --* 

          The CloudWatch log stream name for logging. This value is required if Enabled is true.

          

        
      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DeliveryStreamARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of  CreateDeliveryStream .

        
        

        - **DeliveryStreamARN** *(string) --* 

          The ARN of the delivery stream.

          
    

  .. py:method:: delete_delivery_stream(**kwargs)

    

    Deletes a delivery stream and its data.

     

    You can delete a delivery stream only if it is in ``ACTIVE`` or ``DELETING`` state, and not in the ``CREATING`` state. While the deletion request is in process, the delivery stream is in the ``DELETING`` state.

     

    To check the state of a delivery stream, use  DescribeDeliveryStream .

     

    While the delivery stream is ``DELETING`` state, the service may continue to accept the records, but the service doesn't make any guarantees with respect to delivering the data. Therefore, as a best practice, you should first stop any applications that are sending records before deleting a delivery stream.

    

    **Request Syntax** 
    ::

      response = client.delete_delivery_stream(
          DeliveryStreamName='string'
      )
    :type DeliveryStreamName: string
    :param DeliveryStreamName: **[REQUIRED]** 

      The name of the delivery stream.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of  DeleteDeliveryStream .

        
    

  .. py:method:: describe_delivery_stream(**kwargs)

    

    Describes the specified delivery stream and gets the status. For example, after your delivery stream is created, call  DescribeDeliveryStream to see if the delivery stream is ``ACTIVE`` and therefore ready for data to be sent to it.

    

    **Request Syntax** 
    ::

      response = client.describe_delivery_stream(
          DeliveryStreamName='string',
          Limit=123,
          ExclusiveStartDestinationId='string'
      )
    :type DeliveryStreamName: string
    :param DeliveryStreamName: **[REQUIRED]** 

      The name of the delivery stream.

      

    
    :type Limit: integer
    :param Limit: 

      The limit on the number of destinations to return. Currently, you can have one destination per delivery stream.

      

    
    :type ExclusiveStartDestinationId: string
    :param ExclusiveStartDestinationId: 

      Specifies the destination ID to start returning the destination information. Currently Firehose supports one destination per delivery stream.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DeliveryStreamDescription': {
                'DeliveryStreamName': 'string',
                'DeliveryStreamARN': 'string',
                'DeliveryStreamStatus': 'CREATING'|'DELETING'|'ACTIVE',
                'VersionId': 'string',
                'CreateTimestamp': datetime(2015, 1, 1),
                'LastUpdateTimestamp': datetime(2015, 1, 1),
                'Destinations': [
                    {
                        'DestinationId': 'string',
                        'S3DestinationDescription': {
                            'RoleARN': 'string',
                            'BucketARN': 'string',
                            'Prefix': 'string',
                            'BufferingHints': {
                                'SizeInMBs': 123,
                                'IntervalInSeconds': 123
                            },
                            'CompressionFormat': 'UNCOMPRESSED'|'GZIP'|'ZIP'|'Snappy',
                            'EncryptionConfiguration': {
                                'NoEncryptionConfig': 'NoEncryption',
                                'KMSEncryptionConfig': {
                                    'AWSKMSKeyARN': 'string'
                                }
                            },
                            'CloudWatchLoggingOptions': {
                                'Enabled': True|False,
                                'LogGroupName': 'string',
                                'LogStreamName': 'string'
                            }
                        },
                        'RedshiftDestinationDescription': {
                            'RoleARN': 'string',
                            'ClusterJDBCURL': 'string',
                            'CopyCommand': {
                                'DataTableName': 'string',
                                'DataTableColumns': 'string',
                                'CopyOptions': 'string'
                            },
                            'Username': 'string',
                            'RetryOptions': {
                                'DurationInSeconds': 123
                            },
                            'S3DestinationDescription': {
                                'RoleARN': 'string',
                                'BucketARN': 'string',
                                'Prefix': 'string',
                                'BufferingHints': {
                                    'SizeInMBs': 123,
                                    'IntervalInSeconds': 123
                                },
                                'CompressionFormat': 'UNCOMPRESSED'|'GZIP'|'ZIP'|'Snappy',
                                'EncryptionConfiguration': {
                                    'NoEncryptionConfig': 'NoEncryption',
                                    'KMSEncryptionConfig': {
                                        'AWSKMSKeyARN': 'string'
                                    }
                                },
                                'CloudWatchLoggingOptions': {
                                    'Enabled': True|False,
                                    'LogGroupName': 'string',
                                    'LogStreamName': 'string'
                                }
                            },
                            'CloudWatchLoggingOptions': {
                                'Enabled': True|False,
                                'LogGroupName': 'string',
                                'LogStreamName': 'string'
                            }
                        },
                        'ElasticsearchDestinationDescription': {
                            'RoleARN': 'string',
                            'DomainARN': 'string',
                            'IndexName': 'string',
                            'TypeName': 'string',
                            'IndexRotationPeriod': 'NoRotation'|'OneHour'|'OneDay'|'OneWeek'|'OneMonth',
                            'BufferingHints': {
                                'IntervalInSeconds': 123,
                                'SizeInMBs': 123
                            },
                            'RetryOptions': {
                                'DurationInSeconds': 123
                            },
                            'S3BackupMode': 'FailedDocumentsOnly'|'AllDocuments',
                            'S3DestinationDescription': {
                                'RoleARN': 'string',
                                'BucketARN': 'string',
                                'Prefix': 'string',
                                'BufferingHints': {
                                    'SizeInMBs': 123,
                                    'IntervalInSeconds': 123
                                },
                                'CompressionFormat': 'UNCOMPRESSED'|'GZIP'|'ZIP'|'Snappy',
                                'EncryptionConfiguration': {
                                    'NoEncryptionConfig': 'NoEncryption',
                                    'KMSEncryptionConfig': {
                                        'AWSKMSKeyARN': 'string'
                                    }
                                },
                                'CloudWatchLoggingOptions': {
                                    'Enabled': True|False,
                                    'LogGroupName': 'string',
                                    'LogStreamName': 'string'
                                }
                            },
                            'CloudWatchLoggingOptions': {
                                'Enabled': True|False,
                                'LogGroupName': 'string',
                                'LogStreamName': 'string'
                            }
                        }
                    },
                ],
                'HasMoreDestinations': True|False
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of  DescribeDeliveryStream .

        
        

        - **DeliveryStreamDescription** *(dict) --* 

          Information about the delivery stream.

          
          

          - **DeliveryStreamName** *(string) --* 

            The name of the delivery stream.

            
          

          - **DeliveryStreamARN** *(string) --* 

            The Amazon Resource Name (ARN) of the delivery stream.

            
          

          - **DeliveryStreamStatus** *(string) --* 

            The status of the delivery stream.

            
          

          - **VersionId** *(string) --* 

            Used when calling the  UpdateDestination operation. Each time the destination is updated for the delivery stream, the VersionId is changed, and the current VersionId is required when updating the destination. This is so that the service knows it is applying the changes to the correct version of the delivery stream.

            
          

          - **CreateTimestamp** *(datetime) --* 

            The date and time that the delivery stream was created.

            
          

          - **LastUpdateTimestamp** *(datetime) --* 

            The date and time that the delivery stream was last updated.

            
          

          - **Destinations** *(list) --* 

            The destinations.

            
            

            - *(dict) --* 

              Describes the destination for a delivery stream.

              
              

              - **DestinationId** *(string) --* 

                The ID of the destination.

                
              

              - **S3DestinationDescription** *(dict) --* 

                The Amazon S3 destination.

                
                

                - **RoleARN** *(string) --* 

                  The ARN of the AWS credentials.

                  
                

                - **BucketARN** *(string) --* 

                  The ARN of the S3 bucket.

                  
                

                - **Prefix** *(string) --* 

                  The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `Amazon Kinesis Firehose Developer Guide`_ .

                  
                

                - **BufferingHints** *(dict) --* 

                  The buffering option. If no value is specified, **BufferingHints** object default values are used.

                  
                  

                  - **SizeInMBs** *(integer) --* 

                    Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

                     

                    We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

                    
                  

                  - **IntervalInSeconds** *(integer) --* 

                    Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

                    
              
                

                - **CompressionFormat** *(string) --* 

                  The compression format. If no value is specified, the default is ``NOCOMPRESSION`` .

                  
                

                - **EncryptionConfiguration** *(dict) --* 

                  The encryption configuration. If no value is specified, the default is no encryption.

                  
                  

                  - **NoEncryptionConfig** *(string) --* 

                    Specifically override existing encryption information to ensure no encryption is used.

                    
                  

                  - **KMSEncryptionConfig** *(dict) --* 

                    The encryption key.

                    
                    

                    - **AWSKMSKeyARN** *(string) --* 

                      The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

                      
                
              
                

                - **CloudWatchLoggingOptions** *(dict) --* 

                  Describes CloudWatch logging options for your delivery stream.

                  
                  

                  - **Enabled** *(boolean) --* 

                    Enables or disables CloudWatch logging.

                    
                  

                  - **LogGroupName** *(string) --* 

                    The CloudWatch group name for logging. This value is required if Enabled is true.

                    
                  

                  - **LogStreamName** *(string) --* 

                    The CloudWatch log stream name for logging. This value is required if Enabled is true.

                    
              
            
              

              - **RedshiftDestinationDescription** *(dict) --* 

                The destination in Amazon Redshift.

                
                

                - **RoleARN** *(string) --* 

                  The ARN of the AWS credentials.

                  
                

                - **ClusterJDBCURL** *(string) --* 

                  The database connection string.

                  
                

                - **CopyCommand** *(dict) --* 

                  The ``COPY`` command.

                  
                  

                  - **DataTableName** *(string) --* 

                    The name of the target table. The table must already exist in the database.

                    
                  

                  - **DataTableColumns** *(string) --* 

                    A comma-separated list of column names.

                    
                  

                  - **CopyOptions** *(string) --* 

                    Optional parameters to use with the Amazon Redshift ``COPY`` command. For more information, see the "Optional Parameters" section of `Amazon Redshift COPY command`_ . Some possible examples that would apply to Firehose are as follows.

                     

                     ``delimiter '\t' lzop;`` - fields are delimited with "\t" (TAB character) and compressed using lzop.

                     

                     ``delimiter '|`` - fields are delimited with "|" (this is the default delimiter).

                     

                     ``delimiter '|' escape`` - the delimiter should be escaped.

                     

                     ``fixedwidth 'venueid:3,venuename:25,venuecity:12,venuestate:2,venueseats:6'`` - fields are fixed width in the source, with each width specified after every column in the table.

                     

                     ``JSON 's3://mybucket/jsonpaths.txt'`` - data is in JSON format, and the path specified is the format of the data.

                     

                    For more examples, see `Amazon Redshift COPY command examples`_ .

                    
              
                

                - **Username** *(string) --* 

                  The name of the user.

                  
                

                - **RetryOptions** *(dict) --* 

                  Configures retry behavior in the event that Firehose is unable to deliver documents to Amazon Redshift. Default value is 3600 (60 minutes).

                  
                  

                  - **DurationInSeconds** *(integer) --* 

                    The length of time during which Firehose retries delivery after a failure, starting from the initial request and including the first attempt. The default value is 3600 seconds (60 minutes). Firehose does not retry if the value of ``DurationInSeconds`` is 0 (zero) or if the first delivery attempt takes longer than the current value.

                    
              
                

                - **S3DestinationDescription** *(dict) --* 

                  The Amazon S3 destination.

                  
                  

                  - **RoleARN** *(string) --* 

                    The ARN of the AWS credentials.

                    
                  

                  - **BucketARN** *(string) --* 

                    The ARN of the S3 bucket.

                    
                  

                  - **Prefix** *(string) --* 

                    The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `Amazon Kinesis Firehose Developer Guide`_ .

                    
                  

                  - **BufferingHints** *(dict) --* 

                    The buffering option. If no value is specified, **BufferingHints** object default values are used.

                    
                    

                    - **SizeInMBs** *(integer) --* 

                      Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

                       

                      We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

                      
                    

                    - **IntervalInSeconds** *(integer) --* 

                      Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

                      
                
                  

                  - **CompressionFormat** *(string) --* 

                    The compression format. If no value is specified, the default is ``NOCOMPRESSION`` .

                    
                  

                  - **EncryptionConfiguration** *(dict) --* 

                    The encryption configuration. If no value is specified, the default is no encryption.

                    
                    

                    - **NoEncryptionConfig** *(string) --* 

                      Specifically override existing encryption information to ensure no encryption is used.

                      
                    

                    - **KMSEncryptionConfig** *(dict) --* 

                      The encryption key.

                      
                      

                      - **AWSKMSKeyARN** *(string) --* 

                        The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

                        
                  
                
                  

                  - **CloudWatchLoggingOptions** *(dict) --* 

                    Describes CloudWatch logging options for your delivery stream.

                    
                    

                    - **Enabled** *(boolean) --* 

                      Enables or disables CloudWatch logging.

                      
                    

                    - **LogGroupName** *(string) --* 

                      The CloudWatch group name for logging. This value is required if Enabled is true.

                      
                    

                    - **LogStreamName** *(string) --* 

                      The CloudWatch log stream name for logging. This value is required if Enabled is true.

                      
                
              
                

                - **CloudWatchLoggingOptions** *(dict) --* 

                  Describes CloudWatch logging options for your delivery stream.

                  
                  

                  - **Enabled** *(boolean) --* 

                    Enables or disables CloudWatch logging.

                    
                  

                  - **LogGroupName** *(string) --* 

                    The CloudWatch group name for logging. This value is required if Enabled is true.

                    
                  

                  - **LogStreamName** *(string) --* 

                    The CloudWatch log stream name for logging. This value is required if Enabled is true.

                    
              
            
              

              - **ElasticsearchDestinationDescription** *(dict) --* 

                The destination in Amazon ES.

                
                

                - **RoleARN** *(string) --* 

                  The ARN of the AWS credentials.

                  
                

                - **DomainARN** *(string) --* 

                  The ARN of the Amazon ES domain.

                  
                

                - **IndexName** *(string) --* 

                  The Elasticsearch index name.

                  
                

                - **TypeName** *(string) --* 

                  The Elasticsearch type name.

                  
                

                - **IndexRotationPeriod** *(string) --* 

                  The Elasticsearch index rotation period

                  
                

                - **BufferingHints** *(dict) --* 

                  Buffering options.

                  
                  

                  - **IntervalInSeconds** *(integer) --* 

                    Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300 (5 minutes).

                    
                  

                  - **SizeInMBs** *(integer) --* 

                    Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

                     

                    We recommend setting **SizeInMBs** to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, set **SizeInMBs** to be 10 MB or higher.

                    
              
                

                - **RetryOptions** *(dict) --* 

                  Elasticsearch retry options.

                  
                  

                  - **DurationInSeconds** *(integer) --* 

                    After an initial failure to deliver to Amazon ES, the total amount of time during which Firehose re-attempts delivery (including the first attempt). After this time has elapsed, the failed documents are written to Amazon S3. Default value is 300 seconds (5 minutes). A value of 0 (zero) results in no retries.

                    
              
                

                - **S3BackupMode** *(string) --* 

                  Amazon S3 backup mode.

                  
                

                - **S3DestinationDescription** *(dict) --* 

                  Describes a destination in Amazon S3.

                  
                  

                  - **RoleARN** *(string) --* 

                    The ARN of the AWS credentials.

                    
                  

                  - **BucketARN** *(string) --* 

                    The ARN of the S3 bucket.

                    
                  

                  - **Prefix** *(string) --* 

                    The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `Amazon Kinesis Firehose Developer Guide`_ .

                    
                  

                  - **BufferingHints** *(dict) --* 

                    The buffering option. If no value is specified, **BufferingHints** object default values are used.

                    
                    

                    - **SizeInMBs** *(integer) --* 

                      Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

                       

                      We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

                      
                    

                    - **IntervalInSeconds** *(integer) --* 

                      Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

                      
                
                  

                  - **CompressionFormat** *(string) --* 

                    The compression format. If no value is specified, the default is ``NOCOMPRESSION`` .

                    
                  

                  - **EncryptionConfiguration** *(dict) --* 

                    The encryption configuration. If no value is specified, the default is no encryption.

                    
                    

                    - **NoEncryptionConfig** *(string) --* 

                      Specifically override existing encryption information to ensure no encryption is used.

                      
                    

                    - **KMSEncryptionConfig** *(dict) --* 

                      The encryption key.

                      
                      

                      - **AWSKMSKeyARN** *(string) --* 

                        The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

                        
                  
                
                  

                  - **CloudWatchLoggingOptions** *(dict) --* 

                    Describes CloudWatch logging options for your delivery stream.

                    
                    

                    - **Enabled** *(boolean) --* 

                      Enables or disables CloudWatch logging.

                      
                    

                    - **LogGroupName** *(string) --* 

                      The CloudWatch group name for logging. This value is required if Enabled is true.

                      
                    

                    - **LogStreamName** *(string) --* 

                      The CloudWatch log stream name for logging. This value is required if Enabled is true.

                      
                
              
                

                - **CloudWatchLoggingOptions** *(dict) --* 

                  CloudWatch logging options.

                  
                  

                  - **Enabled** *(boolean) --* 

                    Enables or disables CloudWatch logging.

                    
                  

                  - **LogGroupName** *(string) --* 

                    The CloudWatch group name for logging. This value is required if Enabled is true.

                    
                  

                  - **LogStreamName** *(string) --* 

                    The CloudWatch log stream name for logging. This value is required if Enabled is true.

                    
              
            
          
        
          

          - **HasMoreDestinations** *(boolean) --* 

            Indicates whether there are more destinations available to list.

            
      
    

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

        


  .. py:method:: list_delivery_streams(**kwargs)

    

    Lists your delivery streams.

     

    The number of delivery streams might be too large to return using a single call to  ListDeliveryStreams . You can limit the number of delivery streams returned, using the **Limit** parameter. To determine whether there are more delivery streams to list, check the value of **HasMoreDeliveryStreams** in the output. If there are more delivery streams to list, you can request them by specifying the name of the last delivery stream returned in the call in the **ExclusiveStartDeliveryStreamName** parameter of a subsequent call.

    

    **Request Syntax** 
    ::

      response = client.list_delivery_streams(
          Limit=123,
          ExclusiveStartDeliveryStreamName='string'
      )
    :type Limit: integer
    :param Limit: 

      The maximum number of delivery streams to list.

      

    
    :type ExclusiveStartDeliveryStreamName: string
    :param ExclusiveStartDeliveryStreamName: 

      The name of the delivery stream to start the list with.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DeliveryStreamNames': [
                'string',
            ],
            'HasMoreDeliveryStreams': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of  ListDeliveryStreams .

        
        

        - **DeliveryStreamNames** *(list) --* 

          The names of the delivery streams.

          
          

          - *(string) --* 
      
        

        - **HasMoreDeliveryStreams** *(boolean) --* 

          Indicates whether there are more delivery streams available to list.

          
    

  .. py:method:: put_record(**kwargs)

    

    Writes a single data record into an Amazon Kinesis Firehose delivery stream. To write multiple data records into a delivery stream, use  PutRecordBatch . Applications using these operations are referred to as producers.

     

    By default, each delivery stream can take in up to 2,000 transactions per second, 5,000 records per second, or 5 MB per second. Note that if you use  PutRecord and  PutRecordBatch , the limits are an aggregate across these two operations for each delivery stream. For more information about limits and how to request an increase, see `Amazon Kinesis Firehose Limits`_ . 

     

    You must specify the name of the delivery stream and the data record when using  PutRecord . The data record consists of a data blob that can be up to 1,000 KB in size, and any kind of data, for example, a segment from a log file, geographic location data, web site clickstream data, etc.

     

    Firehose buffers records before delivering them to the destination. To disambiguate the data blobs at the destination, a common solution is to use delimiters in the data, such as a newline (``\n`` ) or some other character unique within the data. This allows the consumer application(s) to parse individual data items when reading the data from the destination.

     

    The  PutRecord operation returns a **RecordId** , which is a unique string assigned to each record. Producer applications can use this ID for purposes such as auditability and investigation.

     

    If the  PutRecord operation throws a **ServiceUnavailableException** , back off and retry. If the exception persists, it is possible that the throughput limits have been exceeded for the delivery stream. 

     

    Data records sent to Firehose are stored for 24 hours from the time they are added to a delivery stream as it attempts to send the records to the destination. If the destination is unreachable for more than 24 hours, the data is no longer available.

    

    **Request Syntax** 
    ::

      response = client.put_record(
          DeliveryStreamName='string',
          Record={
              'Data': b'bytes'
          }
      )
    :type DeliveryStreamName: string
    :param DeliveryStreamName: **[REQUIRED]** 

      The name of the delivery stream.

      

    
    :type Record: dict
    :param Record: **[REQUIRED]** 

      The record.

      

    
      - **Data** *(bytes) --* **[REQUIRED]** 

        The data blob, which is base64-encoded when the blob is serialized. The maximum size of the data blob, before base64-encoding, is 1,000 KB.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RecordId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of  PutRecord .

        
        

        - **RecordId** *(string) --* 

          The ID of the record.

          
    

  .. py:method:: put_record_batch(**kwargs)

    

    Writes multiple data records into a delivery stream in a single call, which can achieve higher throughput per producer than when writing single records. To write single data records into a delivery stream, use  PutRecord . Applications using these operations are referred to as producers.

     

    Each  PutRecordBatch request supports up to 500 records. Each record in the request can be as large as 1,000 KB (before 64-bit encoding), up to a limit of 4 MB for the entire request. By default, each delivery stream can take in up to 2,000 transactions per second, 5,000 records per second, or 5 MB per second. Note that if you use  PutRecord and  PutRecordBatch , the limits are an aggregate across these two operations for each delivery stream. For more information about limits and how to request an increase, see `Amazon Kinesis Firehose Limits`_ . 

     

    You must specify the name of the delivery stream and the data record when using  PutRecord . The data record consists of a data blob that can be up to 1,000 KB in size, and any kind of data, for example, a segment from a log file, geographic location data, web site clickstream data, and so on.

     

    Firehose buffers records before delivering them to the destination. To disambiguate the data blobs at the destination, a common solution is to use delimiters in the data, such as a newline (``\n`` ) or some other character unique within the data. This allows the consumer application(s) to parse individual data items when reading the data from the destination.

     

    The  PutRecordBatch response includes a count of any failed records, **FailedPutCount** , and an array of responses, **RequestResponses** . The **FailedPutCount** value is a count of records that failed. Each entry in the **RequestResponses** array gives additional information of the processed record. Each entry in **RequestResponses** directly correlates with a record in the request array using the same ordering, from the top to the bottom of the request and response. **RequestResponses** always includes the same number of records as the request array. **RequestResponses** both successfully and unsuccessfully processed records. Firehose attempts to process all records in each  PutRecordBatch request. A single record failure does not stop the processing of subsequent records.

     

    A successfully processed record includes a **RecordId** value, which is a unique value identified for the record. An unsuccessfully processed record includes **ErrorCode** and **ErrorMessage** values. **ErrorCode** reflects the type of error and is one of the following values: ``ServiceUnavailable`` or ``InternalFailure`` . ``ErrorMessage`` provides more detailed information about the error.

     

    If **FailedPutCount** is greater than 0 (zero), retry the request. A retry of the entire batch of records is possible; however, we strongly recommend that you inspect the entire response and resend only those records that failed processing. This minimizes duplicate records and also reduces the total bytes sent (and corresponding charges).

     

    If the  PutRecordBatch operation throws a **ServiceUnavailableException** , back off and retry. If the exception persists, it is possible that the throughput limits have been exceeded for the delivery stream.

     

    Data records sent to Firehose are stored for 24 hours from the time they are added to a delivery stream as it attempts to send the records to the destination. If the destination is unreachable for more than 24 hours, the data is no longer available.

    

    **Request Syntax** 
    ::

      response = client.put_record_batch(
          DeliveryStreamName='string',
          Records=[
              {
                  'Data': b'bytes'
              },
          ]
      )
    :type DeliveryStreamName: string
    :param DeliveryStreamName: **[REQUIRED]** 

      The name of the delivery stream.

      

    
    :type Records: list
    :param Records: **[REQUIRED]** 

      One or more records.

      

    
      - *(dict) --* 

        The unit of data in a delivery stream.

        

      
        - **Data** *(bytes) --* **[REQUIRED]** 

          The data blob, which is base64-encoded when the blob is serialized. The maximum size of the data blob, before base64-encoding, is 1,000 KB.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FailedPutCount': 123,
            'RequestResponses': [
                {
                    'RecordId': 'string',
                    'ErrorCode': 'string',
                    'ErrorMessage': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of  PutRecordBatch .

        
        

        - **FailedPutCount** *(integer) --* 

          The number of unsuccessfully written records.

          
        

        - **RequestResponses** *(list) --* 

          The results for the individual records. The index of each element matches the same index in which records were sent.

          
          

          - *(dict) --* 

            Contains the result for an individual record from a  PutRecordBatch request. If the record is successfully added to your delivery stream, it receives a record ID. If the record fails to be added to your delivery stream, the result includes an error code and an error message.

            
            

            - **RecordId** *(string) --* 

              The ID of the record.

              
            

            - **ErrorCode** *(string) --* 

              The error code for an individual record result.

              
            

            - **ErrorMessage** *(string) --* 

              The error message for an individual record result.

              
        
      
    

  .. py:method:: update_destination(**kwargs)

    

    Updates the specified destination of the specified delivery stream. Note: Switching between Elasticsearch and other services is not supported. For Elasticsearch destination, you can only update an existing Elasticsearch destination with this operation.

     

    This operation can be used to change the destination type (for example, to replace the Amazon S3 destination with Amazon Redshift) or change the parameters associated with a given destination (for example, to change the bucket name of the Amazon S3 destination). The update may not occur immediately. The target delivery stream remains active while the configurations are updated, so data writes to the delivery stream can continue during this process. The updated configurations are normally effective within a few minutes.

     

    If the destination type is the same, Firehose merges the configuration parameters specified in the  UpdateDestination request with the destination configuration that already exists on the delivery stream. If any of the parameters are not specified in the update request, then the existing configuration parameters are retained. For example, in the Amazon S3 destination, if  EncryptionConfiguration is not specified then the existing  EncryptionConfiguration is maintained on the destination.

     

    If the destination type is not the same, for example, changing the destination from Amazon S3 to Amazon Redshift, Firehose does not merge any parameters. In this case, all parameters must be specified.

     

    Firehose uses the **CurrentDeliveryStreamVersionId** to avoid race conditions and conflicting merges. This is a required field in every request and the service only updates the configuration if the existing configuration matches the **VersionId** . After the update is applied successfully, the **VersionId** is updated, which can be retrieved with the  DescribeDeliveryStream operation. The new **VersionId** should be uses to set **CurrentDeliveryStreamVersionId** in the next  UpdateDestination operation.

    

    **Request Syntax** 
    ::

      response = client.update_destination(
          DeliveryStreamName='string',
          CurrentDeliveryStreamVersionId='string',
          DestinationId='string',
          S3DestinationUpdate={
              'RoleARN': 'string',
              'BucketARN': 'string',
              'Prefix': 'string',
              'BufferingHints': {
                  'SizeInMBs': 123,
                  'IntervalInSeconds': 123
              },
              'CompressionFormat': 'UNCOMPRESSED'|'GZIP'|'ZIP'|'Snappy',
              'EncryptionConfiguration': {
                  'NoEncryptionConfig': 'NoEncryption',
                  'KMSEncryptionConfig': {
                      'AWSKMSKeyARN': 'string'
                  }
              },
              'CloudWatchLoggingOptions': {
                  'Enabled': True|False,
                  'LogGroupName': 'string',
                  'LogStreamName': 'string'
              }
          },
          RedshiftDestinationUpdate={
              'RoleARN': 'string',
              'ClusterJDBCURL': 'string',
              'CopyCommand': {
                  'DataTableName': 'string',
                  'DataTableColumns': 'string',
                  'CopyOptions': 'string'
              },
              'Username': 'string',
              'Password': 'string',
              'RetryOptions': {
                  'DurationInSeconds': 123
              },
              'S3Update': {
                  'RoleARN': 'string',
                  'BucketARN': 'string',
                  'Prefix': 'string',
                  'BufferingHints': {
                      'SizeInMBs': 123,
                      'IntervalInSeconds': 123
                  },
                  'CompressionFormat': 'UNCOMPRESSED'|'GZIP'|'ZIP'|'Snappy',
                  'EncryptionConfiguration': {
                      'NoEncryptionConfig': 'NoEncryption',
                      'KMSEncryptionConfig': {
                          'AWSKMSKeyARN': 'string'
                      }
                  },
                  'CloudWatchLoggingOptions': {
                      'Enabled': True|False,
                      'LogGroupName': 'string',
                      'LogStreamName': 'string'
                  }
              },
              'CloudWatchLoggingOptions': {
                  'Enabled': True|False,
                  'LogGroupName': 'string',
                  'LogStreamName': 'string'
              }
          },
          ElasticsearchDestinationUpdate={
              'RoleARN': 'string',
              'DomainARN': 'string',
              'IndexName': 'string',
              'TypeName': 'string',
              'IndexRotationPeriod': 'NoRotation'|'OneHour'|'OneDay'|'OneWeek'|'OneMonth',
              'BufferingHints': {
                  'IntervalInSeconds': 123,
                  'SizeInMBs': 123
              },
              'RetryOptions': {
                  'DurationInSeconds': 123
              },
              'S3Update': {
                  'RoleARN': 'string',
                  'BucketARN': 'string',
                  'Prefix': 'string',
                  'BufferingHints': {
                      'SizeInMBs': 123,
                      'IntervalInSeconds': 123
                  },
                  'CompressionFormat': 'UNCOMPRESSED'|'GZIP'|'ZIP'|'Snappy',
                  'EncryptionConfiguration': {
                      'NoEncryptionConfig': 'NoEncryption',
                      'KMSEncryptionConfig': {
                          'AWSKMSKeyARN': 'string'
                      }
                  },
                  'CloudWatchLoggingOptions': {
                      'Enabled': True|False,
                      'LogGroupName': 'string',
                      'LogStreamName': 'string'
                  }
              },
              'CloudWatchLoggingOptions': {
                  'Enabled': True|False,
                  'LogGroupName': 'string',
                  'LogStreamName': 'string'
              }
          }
      )
    :type DeliveryStreamName: string
    :param DeliveryStreamName: **[REQUIRED]** 

      The name of the delivery stream.

      

    
    :type CurrentDeliveryStreamVersionId: string
    :param CurrentDeliveryStreamVersionId: **[REQUIRED]** 

      Obtain this value from the **VersionId** result of the  DeliveryStreamDescription operation. This value is required, and helps the service to perform conditional operations. For example, if there is a interleaving update and this value is null, then the update destination fails. After the update is successful, the **VersionId** value is updated. The service then performs a merge of the old configuration with the new configuration.

      

    
    :type DestinationId: string
    :param DestinationId: **[REQUIRED]** 

      The ID of the destination.

      

    
    :type S3DestinationUpdate: dict
    :param S3DestinationUpdate: 

      Describes an update for a destination in Amazon S3.

      

    
      - **RoleARN** *(string) --* 

        The ARN of the AWS credentials.

        

      
      - **BucketARN** *(string) --* 

        The ARN of the S3 bucket.

        

      
      - **Prefix** *(string) --* 

        The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `Amazon Kinesis Firehose Developer Guide`_ .

        

      
      - **BufferingHints** *(dict) --* 

        The buffering option. If no value is specified, **BufferingHints** object default values are used.

        

      
        - **SizeInMBs** *(integer) --* 

          Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

           

          We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

          

        
        - **IntervalInSeconds** *(integer) --* 

          Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

          

        
      
      - **CompressionFormat** *(string) --* 

        The compression format. If no value is specified, the default is ``NOCOMPRESSION`` .

         

        The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified for Amazon Redshift destinations because they are not supported by the Amazon Redshift ``COPY`` operation that reads from the S3 bucket.

        

      
      - **EncryptionConfiguration** *(dict) --* 

        The encryption configuration. If no value is specified, the default is no encryption.

        

      
        - **NoEncryptionConfig** *(string) --* 

          Specifically override existing encryption information to ensure no encryption is used.

          

        
        - **KMSEncryptionConfig** *(dict) --* 

          The encryption key.

          

        
          - **AWSKMSKeyARN** *(string) --* **[REQUIRED]** 

            The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

            

          
        
      
      - **CloudWatchLoggingOptions** *(dict) --* 

        Describes CloudWatch logging options for your delivery stream.

        

      
        - **Enabled** *(boolean) --* 

          Enables or disables CloudWatch logging.

          

        
        - **LogGroupName** *(string) --* 

          The CloudWatch group name for logging. This value is required if Enabled is true.

          

        
        - **LogStreamName** *(string) --* 

          The CloudWatch log stream name for logging. This value is required if Enabled is true.

          

        
      
    
    :type RedshiftDestinationUpdate: dict
    :param RedshiftDestinationUpdate: 

      Describes an update for a destination in Amazon Redshift.

      

    
      - **RoleARN** *(string) --* 

        The ARN of the AWS credentials.

        

      
      - **ClusterJDBCURL** *(string) --* 

        The database connection string.

        

      
      - **CopyCommand** *(dict) --* 

        The ``COPY`` command.

        

      
        - **DataTableName** *(string) --* **[REQUIRED]** 

          The name of the target table. The table must already exist in the database.

          

        
        - **DataTableColumns** *(string) --* 

          A comma-separated list of column names.

          

        
        - **CopyOptions** *(string) --* 

          Optional parameters to use with the Amazon Redshift ``COPY`` command. For more information, see the "Optional Parameters" section of `Amazon Redshift COPY command`_ . Some possible examples that would apply to Firehose are as follows.

           

           ``delimiter '\t' lzop;`` - fields are delimited with "\t" (TAB character) and compressed using lzop.

           

           ``delimiter '|`` - fields are delimited with "|" (this is the default delimiter).

           

           ``delimiter '|' escape`` - the delimiter should be escaped.

           

           ``fixedwidth 'venueid:3,venuename:25,venuecity:12,venuestate:2,venueseats:6'`` - fields are fixed width in the source, with each width specified after every column in the table.

           

           ``JSON 's3://mybucket/jsonpaths.txt'`` - data is in JSON format, and the path specified is the format of the data.

           

          For more examples, see `Amazon Redshift COPY command examples`_ .

          

        
      
      - **Username** *(string) --* 

        The name of the user.

        

      
      - **Password** *(string) --* 

        The user password.

        

      
      - **RetryOptions** *(dict) --* 

        Configures retry behavior in the event that Firehose is unable to deliver documents to Amazon Redshift. Default value is 3600 (60 minutes).

        

      
        - **DurationInSeconds** *(integer) --* 

          The length of time during which Firehose retries delivery after a failure, starting from the initial request and including the first attempt. The default value is 3600 seconds (60 minutes). Firehose does not retry if the value of ``DurationInSeconds`` is 0 (zero) or if the first delivery attempt takes longer than the current value.

          

        
      
      - **S3Update** *(dict) --* 

        The Amazon S3 destination.

         

        The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified in **RedshiftDestinationUpdate.S3Update** because the Amazon Redshift ``COPY`` operation that reads from the S3 bucket doesn't support these compression formats.

        

      
        - **RoleARN** *(string) --* 

          The ARN of the AWS credentials.

          

        
        - **BucketARN** *(string) --* 

          The ARN of the S3 bucket.

          

        
        - **Prefix** *(string) --* 

          The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `Amazon Kinesis Firehose Developer Guide`_ .

          

        
        - **BufferingHints** *(dict) --* 

          The buffering option. If no value is specified, **BufferingHints** object default values are used.

          

        
          - **SizeInMBs** *(integer) --* 

            Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

             

            We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

            

          
          - **IntervalInSeconds** *(integer) --* 

            Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

            

          
        
        - **CompressionFormat** *(string) --* 

          The compression format. If no value is specified, the default is ``NOCOMPRESSION`` .

           

          The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified for Amazon Redshift destinations because they are not supported by the Amazon Redshift ``COPY`` operation that reads from the S3 bucket.

          

        
        - **EncryptionConfiguration** *(dict) --* 

          The encryption configuration. If no value is specified, the default is no encryption.

          

        
          - **NoEncryptionConfig** *(string) --* 

            Specifically override existing encryption information to ensure no encryption is used.

            

          
          - **KMSEncryptionConfig** *(dict) --* 

            The encryption key.

            

          
            - **AWSKMSKeyARN** *(string) --* **[REQUIRED]** 

              The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

              

            
          
        
        - **CloudWatchLoggingOptions** *(dict) --* 

          Describes CloudWatch logging options for your delivery stream.

          

        
          - **Enabled** *(boolean) --* 

            Enables or disables CloudWatch logging.

            

          
          - **LogGroupName** *(string) --* 

            The CloudWatch group name for logging. This value is required if Enabled is true.

            

          
          - **LogStreamName** *(string) --* 

            The CloudWatch log stream name for logging. This value is required if Enabled is true.

            

          
        
      
      - **CloudWatchLoggingOptions** *(dict) --* 

        Describes CloudWatch logging options for your delivery stream.

        

      
        - **Enabled** *(boolean) --* 

          Enables or disables CloudWatch logging.

          

        
        - **LogGroupName** *(string) --* 

          The CloudWatch group name for logging. This value is required if Enabled is true.

          

        
        - **LogStreamName** *(string) --* 

          The CloudWatch log stream name for logging. This value is required if Enabled is true.

          

        
      
    
    :type ElasticsearchDestinationUpdate: dict
    :param ElasticsearchDestinationUpdate: 

      Describes an update for a destination in Amazon ES.

      

    
      - **RoleARN** *(string) --* 

        The ARN of the IAM role to be assumed by Firehose for calling the Amazon ES Configuration API and for indexing documents. For more information, see `Amazon S3 Bucket Access`_ .

        

      
      - **DomainARN** *(string) --* 

        The ARN of the Amazon ES domain. The IAM role must have permission for DescribeElasticsearchDomain, DescribeElasticsearchDomains , and DescribeElasticsearchDomainConfig after assuming **RoleARN** .

        

      
      - **IndexName** *(string) --* 

        The Elasticsearch index name.

        

      
      - **TypeName** *(string) --* 

        The Elasticsearch type name.

        

      
      - **IndexRotationPeriod** *(string) --* 

        The Elasticsearch index rotation period. Index rotation appends a timestamp to the IndexName to facilitate the expiration of old data. For more information, see `Index Rotation for Amazon Elasticsearch Service Destination`_ . Default value is ``OneDay`` .

        

      
      - **BufferingHints** *(dict) --* 

        Buffering options. If no value is specified, **ElasticsearchBufferingHints** object default values are used. 

        

      
        - **IntervalInSeconds** *(integer) --* 

          Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300 (5 minutes).

          

        
        - **SizeInMBs** *(integer) --* 

          Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

           

          We recommend setting **SizeInMBs** to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, set **SizeInMBs** to be 10 MB or higher.

          

        
      
      - **RetryOptions** *(dict) --* 

        Configures retry behavior in the event that Firehose is unable to deliver documents to Amazon ES. Default value is 300 (5 minutes).

        

      
        - **DurationInSeconds** *(integer) --* 

          After an initial failure to deliver to Amazon ES, the total amount of time during which Firehose re-attempts delivery (including the first attempt). After this time has elapsed, the failed documents are written to Amazon S3. Default value is 300 seconds (5 minutes). A value of 0 (zero) results in no retries.

          

        
      
      - **S3Update** *(dict) --* 

        Describes an update for a destination in Amazon S3.

        

      
        - **RoleARN** *(string) --* 

          The ARN of the AWS credentials.

          

        
        - **BucketARN** *(string) --* 

          The ARN of the S3 bucket.

          

        
        - **Prefix** *(string) --* 

          The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `Amazon Kinesis Firehose Developer Guide`_ .

          

        
        - **BufferingHints** *(dict) --* 

          The buffering option. If no value is specified, **BufferingHints** object default values are used.

          

        
          - **SizeInMBs** *(integer) --* 

            Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

             

            We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

            

          
          - **IntervalInSeconds** *(integer) --* 

            Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

            

          
        
        - **CompressionFormat** *(string) --* 

          The compression format. If no value is specified, the default is ``NOCOMPRESSION`` .

           

          The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified for Amazon Redshift destinations because they are not supported by the Amazon Redshift ``COPY`` operation that reads from the S3 bucket.

          

        
        - **EncryptionConfiguration** *(dict) --* 

          The encryption configuration. If no value is specified, the default is no encryption.

          

        
          - **NoEncryptionConfig** *(string) --* 

            Specifically override existing encryption information to ensure no encryption is used.

            

          
          - **KMSEncryptionConfig** *(dict) --* 

            The encryption key.

            

          
            - **AWSKMSKeyARN** *(string) --* **[REQUIRED]** 

              The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

              

            
          
        
        - **CloudWatchLoggingOptions** *(dict) --* 

          Describes CloudWatch logging options for your delivery stream.

          

        
          - **Enabled** *(boolean) --* 

            Enables or disables CloudWatch logging.

            

          
          - **LogGroupName** *(string) --* 

            The CloudWatch group name for logging. This value is required if Enabled is true.

            

          
          - **LogStreamName** *(string) --* 

            The CloudWatch log stream name for logging. This value is required if Enabled is true.

            

          
        
      
      - **CloudWatchLoggingOptions** *(dict) --* 

        Describes CloudWatch logging options for your delivery stream.

        

      
        - **Enabled** *(boolean) --* 

          Enables or disables CloudWatch logging.

          

        
        - **LogGroupName** *(string) --* 

          The CloudWatch group name for logging. This value is required if Enabled is true.

          

        
        - **LogStreamName** *(string) --* 

          The CloudWatch log stream name for logging. This value is required if Enabled is true.

          

        
      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of  UpdateDestination .

        
    