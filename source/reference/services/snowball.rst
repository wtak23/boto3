

.. _CreateKey: http://docs.aws.amazon.com/kms/latest/APIReference/API_CreateKey.html
.. _Subscribe: http://docs.aws.amazon.com/sns/latest/api/API_Subscribe.html
.. _CreateTopic: http://docs.aws.amazon.com/sns/latest/api/API_CreateTopic.html
.. _CreateRole: http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateRole.html


********
Snowball
********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: Snowball.Client

  A low-level client representing Amazon Import/Export Snowball::

    
    import boto3
    
    client = boto3.client('snowball')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`cancel_job`

  
  *   :py:meth:`create_address`

  
  *   :py:meth:`create_job`

  
  *   :py:meth:`describe_address`

  
  *   :py:meth:`describe_addresses`

  
  *   :py:meth:`describe_job`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_job_manifest`

  
  *   :py:meth:`get_job_unlock_code`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_snowball_usage`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_jobs`

  
  *   :py:meth:`update_job`

  

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


  .. py:method:: cancel_job(**kwargs)

    

    Cancels the specified job. Note that you can only cancel a job before its ``JobState`` value changes to ``PreparingAppliance`` . Requesting the ``ListJobs`` or ``DescribeJob`` action will return a job's ``JobState`` as part of the response element data returned.

    

    **Request Syntax** 
    ::

      response = client.cancel_job(
          JobId='string'
      )
    :type JobId: string
    :param JobId: **[REQUIRED]** 

      The 39 character job ID for the job that you want to cancel, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: create_address(**kwargs)

    

    Creates an address for a Snowball to be shipped to. 

     

    Addresses are validated at the time of creation. The address you provide must be located within the serviceable area of your region. If the address is invalid or unsupported, then an exception is thrown.

    

    **Request Syntax** 
    ::

      response = client.create_address(
          Address={
              'AddressId': 'string',
              'Name': 'string',
              'Company': 'string',
              'Street1': 'string',
              'Street2': 'string',
              'Street3': 'string',
              'City': 'string',
              'StateOrProvince': 'string',
              'PrefectureOrDistrict': 'string',
              'Landmark': 'string',
              'Country': 'string',
              'PostalCode': 'string',
              'PhoneNumber': 'string'
          }
      )
    :type Address: dict
    :param Address: **[REQUIRED]** 

      The address that you want the Snowball shipped to.

      

    
      - **AddressId** *(string) --* 

        The unique ID for an address.

        

      
      - **Name** *(string) --* 

        The name of a person to receive a Snowball at an address.

        

      
      - **Company** *(string) --* 

        The name of the company to receive a Snowball at an address.

        

      
      - **Street1** *(string) --* 

        The first line in a street address that a Snowball is to be delivered to.

        

      
      - **Street2** *(string) --* 

        The second line in a street address that a Snowball is to be delivered to.

        

      
      - **Street3** *(string) --* 

        The third line in a street address that a Snowball is to be delivered to.

        

      
      - **City** *(string) --* 

        The city in an address that a Snowball is to be delivered to.

        

      
      - **StateOrProvince** *(string) --* 

        The state or province in an address that a Snowball is to be delivered to.

        

      
      - **PrefectureOrDistrict** *(string) --* 

        The prefecture or district in an address that a Snowball is to be delivered to.

        

      
      - **Landmark** *(string) --* 

        A landmark listed in an address that a Snowball is to be delivered to.

        

      
      - **Country** *(string) --* 

        The country in an address that a Snowball is to be delivered to.

        

      
      - **PostalCode** *(string) --* 

        The postal code in an address that a Snowball is to be delivered to.

        

      
      - **PhoneNumber** *(string) --* 

        The phone number associated with an address that a Snowball is to be delivered to.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AddressId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **AddressId** *(string) --* 

          The automatically generated ID for a specific address. You'll use this ID when you create a job to specify which address you want the Snowball for that job shipped to.

          
    

  .. py:method:: create_job(**kwargs)

    

    Creates a job to import or export data between Amazon S3 and your on-premises data center. Note that your AWS account must have the right trust policies and permissions in place to create a job for Snowball. For more information, see  api-reference-policies .

    

    **Request Syntax** 
    ::

      response = client.create_job(
          JobType='IMPORT'|'EXPORT',
          Resources={
              'S3Resources': [
                  {
                      'BucketArn': 'string',
                      'KeyRange': {
                          'BeginMarker': 'string',
                          'EndMarker': 'string'
                      }
                  },
              ]
          },
          Description='string',
          AddressId='string',
          KmsKeyARN='string',
          RoleARN='string',
          SnowballCapacityPreference='T50'|'T80'|'NoPreference',
          ShippingOption='SECOND_DAY'|'NEXT_DAY'|'EXPRESS'|'STANDARD',
          Notification={
              'SnsTopicARN': 'string',
              'JobStatesToNotify': [
                  'New'|'PreparingAppliance'|'PreparingShipment'|'InTransitToCustomer'|'WithCustomer'|'InTransitToAWS'|'WithAWS'|'InProgress'|'Complete'|'Cancelled'|'Listing'|'Pending',
              ],
              'NotifyAll': True|False
          }
      )
    :type JobType: string
    :param JobType: **[REQUIRED]** 

      Defines the type of job that you're creating. 

      

    
    :type Resources: dict
    :param Resources: **[REQUIRED]** 

      Defines the Amazon S3 buckets associated with this job.

       

      With ``IMPORT`` jobs, you specify the bucket or buckets that your transferred data will be imported into.

       

      With ``EXPORT`` jobs, you specify the bucket or buckets that your transferred data will be exported from. Optionally, you can also specify a ``KeyRange`` value. If you choose to export a range, you define the length of the range by providing either an inclusive ``BeginMarker`` value, an inclusive ``EndMarker`` value, or both. Ranges are UTF-8 binary sorted.

      

    
      - **S3Resources** *(list) --* 

        An array of ``S3Resource`` objects.

        

      
        - *(dict) --* 

          Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into. For export jobs, this object can have an optional ``KeyRange`` value. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

          

        
          - **BucketArn** *(string) --* 

            The Amazon Resource Name (ARN) of an Amazon S3 bucket.

            

          
          - **KeyRange** *(dict) --* 

            For export jobs, you can provide an optional ``KeyRange`` within a specific Amazon S3 bucket. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

            

          
            - **BeginMarker** *(string) --* 

              The key that starts an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

              

            
            - **EndMarker** *(string) --* 

              The key that ends an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

              

            
          
        
    
    
    :type Description: string
    :param Description: 

      Defines an optional description of this specific job, for example ``Important Photos 2016-08-11`` .

      

    
    :type AddressId: string
    :param AddressId: **[REQUIRED]** 

      The ID for the address that you want the Snowball shipped to.

      

    
    :type KmsKeyARN: string
    :param KmsKeyARN: 

      The ``KmsKeyARN`` that you want to associate with this job. ``KmsKeyARN`` s are created using the `CreateKey`_ AWS Key Management Service (KMS) API action.

      

    
    :type RoleARN: string
    :param RoleARN: **[REQUIRED]** 

      The ``RoleARN`` that you want to associate with this job. ``RoleArn`` s are created using the `CreateRole`_ AWS Identity and Access Management (IAM) API action.

      

    
    :type SnowballCapacityPreference: string
    :param SnowballCapacityPreference: 

      If your job is being created in one of the US regions, you have the option of specifying what size Snowball you'd like for this job. In all other regions, Snowballs come with 80 TB in storage capacity.

      

    
    :type ShippingOption: string
    :param ShippingOption: **[REQUIRED]** 

      The shipping speed for this job. Note that this speed does not dictate how soon you'll get the Snowball, rather it represents how quickly the Snowball moves to its destination while in transit. Regional shipping speeds are as follows:

       

       
      * In Australia, you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. 
       
      * In the European Union (EU), you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. In addition, most countries in the EU have access to standard shipping, which typically takes less than a week, one way. 
       
      * In India, Snowballs are delivered in one to seven days. 
       
      * In the US, you have access to one-day shipping and two-day shipping. 
       

      

    
    :type Notification: dict
    :param Notification: 

      Defines the Amazon Simple Notification Service (Amazon SNS) notification settings for this job.

      

    
      - **SnsTopicARN** *(string) --* 

        The new SNS ``TopicArn`` that you want to associate with this job. You can create Amazon Resource Names (ARNs) for topics by using the `CreateTopic`_ Amazon SNS API action.

         

        Note that you can subscribe email addresses to an Amazon SNS topic through the AWS Management Console, or by using the `Subscribe`_ AWS Simple Notification Service (SNS) API action.

        

      
      - **JobStatesToNotify** *(list) --* 

        The list of job states that will trigger a notification for this job.

        

      
        - *(string) --* 

        
    
      - **NotifyAll** *(boolean) --* 

        Any change in job state will trigger a notification for this job.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'JobId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **JobId** *(string) --* 

          The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

          
    

  .. py:method:: describe_address(**kwargs)

    

    Takes an ``AddressId`` and returns specific details about that address in the form of an ``Address`` object.

    

    **Request Syntax** 
    ::

      response = client.describe_address(
          AddressId='string'
      )
    :type AddressId: string
    :param AddressId: **[REQUIRED]** 

      The automatically generated ID for a specific address.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Address': {
                'AddressId': 'string',
                'Name': 'string',
                'Company': 'string',
                'Street1': 'string',
                'Street2': 'string',
                'Street3': 'string',
                'City': 'string',
                'StateOrProvince': 'string',
                'PrefectureOrDistrict': 'string',
                'Landmark': 'string',
                'Country': 'string',
                'PostalCode': 'string',
                'PhoneNumber': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Address** *(dict) --* 

          The address that you want the Snowball or Snowballs associated with a specific job to be shipped to.

          
          

          - **AddressId** *(string) --* 

            The unique ID for an address.

            
          

          - **Name** *(string) --* 

            The name of a person to receive a Snowball at an address.

            
          

          - **Company** *(string) --* 

            The name of the company to receive a Snowball at an address.

            
          

          - **Street1** *(string) --* 

            The first line in a street address that a Snowball is to be delivered to.

            
          

          - **Street2** *(string) --* 

            The second line in a street address that a Snowball is to be delivered to.

            
          

          - **Street3** *(string) --* 

            The third line in a street address that a Snowball is to be delivered to.

            
          

          - **City** *(string) --* 

            The city in an address that a Snowball is to be delivered to.

            
          

          - **StateOrProvince** *(string) --* 

            The state or province in an address that a Snowball is to be delivered to.

            
          

          - **PrefectureOrDistrict** *(string) --* 

            The prefecture or district in an address that a Snowball is to be delivered to.

            
          

          - **Landmark** *(string) --* 

            A landmark listed in an address that a Snowball is to be delivered to.

            
          

          - **Country** *(string) --* 

            The country in an address that a Snowball is to be delivered to.

            
          

          - **PostalCode** *(string) --* 

            The postal code in an address that a Snowball is to be delivered to.

            
          

          - **PhoneNumber** *(string) --* 

            The phone number associated with an address that a Snowball is to be delivered to.

            
      
    

  .. py:method:: describe_addresses(**kwargs)

    

    Returns a specified number of ``ADDRESS`` objects. Calling this API in one of the US regions will return addresses from the list of all addresses associated with this account in all US regions.

    

    **Request Syntax** 
    ::

      response = client.describe_addresses(
          MaxResults=123,
          NextToken='string'
      )
    :type MaxResults: integer
    :param MaxResults: 

      The number of ``ADDRESS`` objects to return.

      

    
    :type NextToken: string
    :param NextToken: 

      HTTP requests are stateless. To identify what object comes "next" in the list of ``ADDRESS`` objects, you have the option of specifying a value for ``NextToken`` as the starting point for your list of returned addresses.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Addresses': [
                {
                    'AddressId': 'string',
                    'Name': 'string',
                    'Company': 'string',
                    'Street1': 'string',
                    'Street2': 'string',
                    'Street3': 'string',
                    'City': 'string',
                    'StateOrProvince': 'string',
                    'PrefectureOrDistrict': 'string',
                    'Landmark': 'string',
                    'Country': 'string',
                    'PostalCode': 'string',
                    'PhoneNumber': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Addresses** *(list) --* 

          The Snowball shipping addresses that were created for this account.

          
          

          - *(dict) --* 

            The address that you want the Snowball or Snowballs associated with a specific job to be shipped to. Addresses are validated at the time of creation. The address you provide must be located within the serviceable area of your region. Although no individual elements of the ``Address`` are required, if the address is invalid or unsupported, then an exception is thrown.

            
            

            - **AddressId** *(string) --* 

              The unique ID for an address.

              
            

            - **Name** *(string) --* 

              The name of a person to receive a Snowball at an address.

              
            

            - **Company** *(string) --* 

              The name of the company to receive a Snowball at an address.

              
            

            - **Street1** *(string) --* 

              The first line in a street address that a Snowball is to be delivered to.

              
            

            - **Street2** *(string) --* 

              The second line in a street address that a Snowball is to be delivered to.

              
            

            - **Street3** *(string) --* 

              The third line in a street address that a Snowball is to be delivered to.

              
            

            - **City** *(string) --* 

              The city in an address that a Snowball is to be delivered to.

              
            

            - **StateOrProvince** *(string) --* 

              The state or province in an address that a Snowball is to be delivered to.

              
            

            - **PrefectureOrDistrict** *(string) --* 

              The prefecture or district in an address that a Snowball is to be delivered to.

              
            

            - **Landmark** *(string) --* 

              A landmark listed in an address that a Snowball is to be delivered to.

              
            

            - **Country** *(string) --* 

              The country in an address that a Snowball is to be delivered to.

              
            

            - **PostalCode** *(string) --* 

              The postal code in an address that a Snowball is to be delivered to.

              
            

            - **PhoneNumber** *(string) --* 

              The phone number associated with an address that a Snowball is to be delivered to.

              
        
      
        

        - **NextToken** *(string) --* 

          HTTP requests are stateless. If you use the automatically generated ``NextToken`` value in your next ``DescribeAddresses`` call, your list of returned addresses will start from this point in the array.

          
    

  .. py:method:: describe_job(**kwargs)

    

    Returns information about a specific job including shipping information, job status, and other important metadata.

    

    **Request Syntax** 
    ::

      response = client.describe_job(
          JobId='string'
      )
    :type JobId: string
    :param JobId: **[REQUIRED]** 

      The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'JobMetadata': {
                'JobId': 'string',
                'JobState': 'New'|'PreparingAppliance'|'PreparingShipment'|'InTransitToCustomer'|'WithCustomer'|'InTransitToAWS'|'WithAWS'|'InProgress'|'Complete'|'Cancelled'|'Listing'|'Pending',
                'JobType': 'IMPORT'|'EXPORT',
                'CreationDate': datetime(2015, 1, 1),
                'Resources': {
                    'S3Resources': [
                        {
                            'BucketArn': 'string',
                            'KeyRange': {
                                'BeginMarker': 'string',
                                'EndMarker': 'string'
                            }
                        },
                    ]
                },
                'Description': 'string',
                'KmsKeyARN': 'string',
                'RoleARN': 'string',
                'AddressId': 'string',
                'ShippingDetails': {
                    'ShippingOption': 'SECOND_DAY'|'NEXT_DAY'|'EXPRESS'|'STANDARD',
                    'InboundShipment': {
                        'Status': 'string',
                        'TrackingNumber': 'string'
                    },
                    'OutboundShipment': {
                        'Status': 'string',
                        'TrackingNumber': 'string'
                    }
                },
                'SnowballCapacityPreference': 'T50'|'T80'|'NoPreference',
                'Notification': {
                    'SnsTopicARN': 'string',
                    'JobStatesToNotify': [
                        'New'|'PreparingAppliance'|'PreparingShipment'|'InTransitToCustomer'|'WithCustomer'|'InTransitToAWS'|'WithAWS'|'InProgress'|'Complete'|'Cancelled'|'Listing'|'Pending',
                    ],
                    'NotifyAll': True|False
                },
                'DataTransferProgress': {
                    'BytesTransferred': 123,
                    'ObjectsTransferred': 123,
                    'TotalBytes': 123,
                    'TotalObjects': 123
                },
                'JobLogInfo': {
                    'JobCompletionReportURI': 'string',
                    'JobSuccessLogURI': 'string',
                    'JobFailureLogURI': 'string'
                }
            },
            'SubJobMetadata': [
                {
                    'JobId': 'string',
                    'JobState': 'New'|'PreparingAppliance'|'PreparingShipment'|'InTransitToCustomer'|'WithCustomer'|'InTransitToAWS'|'WithAWS'|'InProgress'|'Complete'|'Cancelled'|'Listing'|'Pending',
                    'JobType': 'IMPORT'|'EXPORT',
                    'CreationDate': datetime(2015, 1, 1),
                    'Resources': {
                        'S3Resources': [
                            {
                                'BucketArn': 'string',
                                'KeyRange': {
                                    'BeginMarker': 'string',
                                    'EndMarker': 'string'
                                }
                            },
                        ]
                    },
                    'Description': 'string',
                    'KmsKeyARN': 'string',
                    'RoleARN': 'string',
                    'AddressId': 'string',
                    'ShippingDetails': {
                        'ShippingOption': 'SECOND_DAY'|'NEXT_DAY'|'EXPRESS'|'STANDARD',
                        'InboundShipment': {
                            'Status': 'string',
                            'TrackingNumber': 'string'
                        },
                        'OutboundShipment': {
                            'Status': 'string',
                            'TrackingNumber': 'string'
                        }
                    },
                    'SnowballCapacityPreference': 'T50'|'T80'|'NoPreference',
                    'Notification': {
                        'SnsTopicARN': 'string',
                        'JobStatesToNotify': [
                            'New'|'PreparingAppliance'|'PreparingShipment'|'InTransitToCustomer'|'WithCustomer'|'InTransitToAWS'|'WithAWS'|'InProgress'|'Complete'|'Cancelled'|'Listing'|'Pending',
                        ],
                        'NotifyAll': True|False
                    },
                    'DataTransferProgress': {
                        'BytesTransferred': 123,
                        'ObjectsTransferred': 123,
                        'TotalBytes': 123,
                        'TotalObjects': 123
                    },
                    'JobLogInfo': {
                        'JobCompletionReportURI': 'string',
                        'JobSuccessLogURI': 'string',
                        'JobFailureLogURI': 'string'
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **JobMetadata** *(dict) --* 

          Information about a specific job, including shipping information, job status, and other important metadata. 

          
          

          - **JobId** *(string) --* 

            The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

            
          

          - **JobState** *(string) --* 

            The current state of the jobs.

            
          

          - **JobType** *(string) --* 

            The type of job.

            
          

          - **CreationDate** *(datetime) --* 

            The creation date for this job.

            
          

          - **Resources** *(dict) --* 

            An array of ``S3Resource`` objects. Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into.

            
            

            - **S3Resources** *(list) --* 

              An array of ``S3Resource`` objects.

              
              

              - *(dict) --* 

                Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into. For export jobs, this object can have an optional ``KeyRange`` value. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

                
                

                - **BucketArn** *(string) --* 

                  The Amazon Resource Name (ARN) of an Amazon S3 bucket.

                  
                

                - **KeyRange** *(dict) --* 

                  For export jobs, you can provide an optional ``KeyRange`` within a specific Amazon S3 bucket. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

                  
                  

                  - **BeginMarker** *(string) --* 

                    The key that starts an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

                    
                  

                  - **EndMarker** *(string) --* 

                    The key that ends an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

                    
              
            
          
        
          

          - **Description** *(string) --* 

            The description of the job, provided at job creation.

            
          

          - **KmsKeyARN** *(string) --* 

            The Amazon Resource Name (ARN) for the AWS Key Management Service (AWS KMS) key associated with this job. This ARN was created using the ``CreateKey`` API action in AWS KMS.

            
          

          - **RoleARN** *(string) --* 

            The role ARN associated with this job. This ARN was created using the ``CreateRole`` API action in AWS Identity and Access Management (IAM).

            
          

          - **AddressId** *(string) --* 

            The ID for the address that you want the Snowball shipped to.

            
          

          - **ShippingDetails** *(dict) --* 

            A job's shipping information, including inbound and outbound tracking numbers and shipping speed options.

            
            

            - **ShippingOption** *(string) --* 

              The shipping speed for a particular job. Note that this speed does not dictate how soon you'll get the Snowball from the job's creation date. This speed represents how quickly it moves to its destination while in transit. Regional shipping speeds are as follows:

               

               
              * In Australia, you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. 
               
              * In the European Union (EU), you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. In addition, most countries in the EU have access to standard shipping, which typically takes less than a week, one way. 
               
              * In India, Snowballs are delivered in one to seven days. 
               
              * In the United States of America (US), you have access to one-day shipping and two-day shipping. 
               

              
            

            - **InboundShipment** *(dict) --* 

              The ``Status`` and ``TrackingNumber`` values for a Snowball being delivered to the address that you specified for a particular job.

              
              

              - **Status** *(string) --* 

                Status information for a shipment. Valid statuses include ``NEW`` , ``IN_TRANSIT`` , and ``DELIVERED`` .

                
              

              - **TrackingNumber** *(string) --* 

                The tracking number for this job. Using this tracking number with your region's carrier's website, you can track a Snowball as the carrier transports it.

                 

                For India, the carrier is Amazon Logistics. For all other regions, UPS is the carrier.

                
          
            

            - **OutboundShipment** *(dict) --* 

              The ``Status`` and ``TrackingNumber`` values for a Snowball being returned to AWS for a particular job.

              
              

              - **Status** *(string) --* 

                Status information for a shipment. Valid statuses include ``NEW`` , ``IN_TRANSIT`` , and ``DELIVERED`` .

                
              

              - **TrackingNumber** *(string) --* 

                The tracking number for this job. Using this tracking number with your region's carrier's website, you can track a Snowball as the carrier transports it.

                 

                For India, the carrier is Amazon Logistics. For all other regions, UPS is the carrier.

                
          
        
          

          - **SnowballCapacityPreference** *(string) --* 

            The Snowball capacity preference for this job, specified at job creation. In US regions, you can choose between 50 TB and 80 TB Snowballs. All other regions use 80 TB capacity Snowballs.

            
          

          - **Notification** *(dict) --* 

            The Amazon Simple Notification Service (Amazon SNS) notification settings associated with a specific job. The ``Notification`` object is returned as a part of the response syntax of the ``DescribeJob`` action in the ``JobMetadata`` data type.

            
            

            - **SnsTopicARN** *(string) --* 

              The new SNS ``TopicArn`` that you want to associate with this job. You can create Amazon Resource Names (ARNs) for topics by using the `CreateTopic`_ Amazon SNS API action.

               

              Note that you can subscribe email addresses to an Amazon SNS topic through the AWS Management Console, or by using the `Subscribe`_ AWS Simple Notification Service (SNS) API action.

              
            

            - **JobStatesToNotify** *(list) --* 

              The list of job states that will trigger a notification for this job.

              
              

              - *(string) --* 
          
            

            - **NotifyAll** *(boolean) --* 

              Any change in job state will trigger a notification for this job.

              
        
          

          - **DataTransferProgress** *(dict) --* 

            A value that defines the real-time status of a Snowball's data transfer while the appliance is at AWS. Note that this data is only available while a job has a ``JobState`` value of ``InProgress`` , for both import and export jobs.

            
            

            - **BytesTransferred** *(integer) --* 

              The number of bytes transferred between a Snowball and Amazon S3.

              
            

            - **ObjectsTransferred** *(integer) --* 

              The number of objects transferred between a Snowball and Amazon S3.

              
            

            - **TotalBytes** *(integer) --* 

              The total bytes of data for a transfer between a Snowball and Amazon S3. This value is set to 0 (zero) until all the keys that will be transferred have been listed.

              
            

            - **TotalObjects** *(integer) --* 

              The total number of objects for a transfer between a Snowball and Amazon S3. This value is set to 0 (zero) until all the keys that will be transferred have been listed.

              
        
          

          - **JobLogInfo** *(dict) --* 

            Links to Amazon S3 presigned URLs for the job report and logs. For import jobs, the PDF job report becomes available at the end of the import process. For export jobs, your job report typically becomes available while the Snowball for your job part is being delivered to you.

            
            

            - **JobCompletionReportURI** *(string) --* 

              A link to an Amazon S3 presigned URL where the job completion report is located.

              
            

            - **JobSuccessLogURI** *(string) --* 

              A link to an Amazon S3 presigned URL where the job success log is located.

              
            

            - **JobFailureLogURI** *(string) --* 

              A link to an Amazon S3 presigned URL where the job failure log is located.

              
        
      
        

        - **SubJobMetadata** *(list) --* 

          Information about a specific job part (in the case of an export job), including shipping information, job status, and other important metadata. 

          
          

          - *(dict) --* 

            Contains information about a specific job including shipping information, job status, and other important metadata. This information is returned as a part of the response syntax of the ``DescribeJob`` action.

            
            

            - **JobId** *(string) --* 

              The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

              
            

            - **JobState** *(string) --* 

              The current state of the jobs.

              
            

            - **JobType** *(string) --* 

              The type of job.

              
            

            - **CreationDate** *(datetime) --* 

              The creation date for this job.

              
            

            - **Resources** *(dict) --* 

              An array of ``S3Resource`` objects. Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into.

              
              

              - **S3Resources** *(list) --* 

                An array of ``S3Resource`` objects.

                
                

                - *(dict) --* 

                  Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into. For export jobs, this object can have an optional ``KeyRange`` value. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

                  
                  

                  - **BucketArn** *(string) --* 

                    The Amazon Resource Name (ARN) of an Amazon S3 bucket.

                    
                  

                  - **KeyRange** *(dict) --* 

                    For export jobs, you can provide an optional ``KeyRange`` within a specific Amazon S3 bucket. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

                    
                    

                    - **BeginMarker** *(string) --* 

                      The key that starts an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

                      
                    

                    - **EndMarker** *(string) --* 

                      The key that ends an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

                      
                
              
            
          
            

            - **Description** *(string) --* 

              The description of the job, provided at job creation.

              
            

            - **KmsKeyARN** *(string) --* 

              The Amazon Resource Name (ARN) for the AWS Key Management Service (AWS KMS) key associated with this job. This ARN was created using the ``CreateKey`` API action in AWS KMS.

              
            

            - **RoleARN** *(string) --* 

              The role ARN associated with this job. This ARN was created using the ``CreateRole`` API action in AWS Identity and Access Management (IAM).

              
            

            - **AddressId** *(string) --* 

              The ID for the address that you want the Snowball shipped to.

              
            

            - **ShippingDetails** *(dict) --* 

              A job's shipping information, including inbound and outbound tracking numbers and shipping speed options.

              
              

              - **ShippingOption** *(string) --* 

                The shipping speed for a particular job. Note that this speed does not dictate how soon you'll get the Snowball from the job's creation date. This speed represents how quickly it moves to its destination while in transit. Regional shipping speeds are as follows:

                 

                 
                * In Australia, you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. 
                 
                * In the European Union (EU), you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. In addition, most countries in the EU have access to standard shipping, which typically takes less than a week, one way. 
                 
                * In India, Snowballs are delivered in one to seven days. 
                 
                * In the United States of America (US), you have access to one-day shipping and two-day shipping. 
                 

                
              

              - **InboundShipment** *(dict) --* 

                The ``Status`` and ``TrackingNumber`` values for a Snowball being delivered to the address that you specified for a particular job.

                
                

                - **Status** *(string) --* 

                  Status information for a shipment. Valid statuses include ``NEW`` , ``IN_TRANSIT`` , and ``DELIVERED`` .

                  
                

                - **TrackingNumber** *(string) --* 

                  The tracking number for this job. Using this tracking number with your region's carrier's website, you can track a Snowball as the carrier transports it.

                   

                  For India, the carrier is Amazon Logistics. For all other regions, UPS is the carrier.

                  
            
              

              - **OutboundShipment** *(dict) --* 

                The ``Status`` and ``TrackingNumber`` values for a Snowball being returned to AWS for a particular job.

                
                

                - **Status** *(string) --* 

                  Status information for a shipment. Valid statuses include ``NEW`` , ``IN_TRANSIT`` , and ``DELIVERED`` .

                  
                

                - **TrackingNumber** *(string) --* 

                  The tracking number for this job. Using this tracking number with your region's carrier's website, you can track a Snowball as the carrier transports it.

                   

                  For India, the carrier is Amazon Logistics. For all other regions, UPS is the carrier.

                  
            
          
            

            - **SnowballCapacityPreference** *(string) --* 

              The Snowball capacity preference for this job, specified at job creation. In US regions, you can choose between 50 TB and 80 TB Snowballs. All other regions use 80 TB capacity Snowballs.

              
            

            - **Notification** *(dict) --* 

              The Amazon Simple Notification Service (Amazon SNS) notification settings associated with a specific job. The ``Notification`` object is returned as a part of the response syntax of the ``DescribeJob`` action in the ``JobMetadata`` data type.

              
              

              - **SnsTopicARN** *(string) --* 

                The new SNS ``TopicArn`` that you want to associate with this job. You can create Amazon Resource Names (ARNs) for topics by using the `CreateTopic`_ Amazon SNS API action.

                 

                Note that you can subscribe email addresses to an Amazon SNS topic through the AWS Management Console, or by using the `Subscribe`_ AWS Simple Notification Service (SNS) API action.

                
              

              - **JobStatesToNotify** *(list) --* 

                The list of job states that will trigger a notification for this job.

                
                

                - *(string) --* 
            
              

              - **NotifyAll** *(boolean) --* 

                Any change in job state will trigger a notification for this job.

                
          
            

            - **DataTransferProgress** *(dict) --* 

              A value that defines the real-time status of a Snowball's data transfer while the appliance is at AWS. Note that this data is only available while a job has a ``JobState`` value of ``InProgress`` , for both import and export jobs.

              
              

              - **BytesTransferred** *(integer) --* 

                The number of bytes transferred between a Snowball and Amazon S3.

                
              

              - **ObjectsTransferred** *(integer) --* 

                The number of objects transferred between a Snowball and Amazon S3.

                
              

              - **TotalBytes** *(integer) --* 

                The total bytes of data for a transfer between a Snowball and Amazon S3. This value is set to 0 (zero) until all the keys that will be transferred have been listed.

                
              

              - **TotalObjects** *(integer) --* 

                The total number of objects for a transfer between a Snowball and Amazon S3. This value is set to 0 (zero) until all the keys that will be transferred have been listed.

                
          
            

            - **JobLogInfo** *(dict) --* 

              Links to Amazon S3 presigned URLs for the job report and logs. For import jobs, the PDF job report becomes available at the end of the import process. For export jobs, your job report typically becomes available while the Snowball for your job part is being delivered to you.

              
              

              - **JobCompletionReportURI** *(string) --* 

                A link to an Amazon S3 presigned URL where the job completion report is located.

                
              

              - **JobSuccessLogURI** *(string) --* 

                A link to an Amazon S3 presigned URL where the job success log is located.

                
              

              - **JobFailureLogURI** *(string) --* 

                A link to an Amazon S3 presigned URL where the job failure log is located.

                
          
        
      
    

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


  .. py:method:: get_job_manifest(**kwargs)

    

    Returns a link to an Amazon S3 presigned URL for the manifest file associated with the specified ``JobId`` value. You can access the manifest file for up to 60 minutes after this request has been made. To access the manifest file after 60 minutes have passed, you'll have to make another call to the ``GetJobManifest`` action.

     

    The manifest is an encrypted file that you can download after your job enters the ``WithCustomer`` status. The manifest is decrypted by using the ``UnlockCode`` code value, when you pass both values to the Snowball through the Snowball client when the client is started for the first time.

     

    As a best practice, we recommend that you don't save a copy of an ``UnlockCode`` value in the same location as the manifest file for that job. Saving these separately helps prevent unauthorized parties from gaining access to the Snowball associated with that job.

     

    Note that the credentials of a given job, including its manifest file and unlock code, expire 90 days after the job is created.

    

    **Request Syntax** 
    ::

      response = client.get_job_manifest(
          JobId='string'
      )
    :type JobId: string
    :param JobId: **[REQUIRED]** 

      The ID for a job that you want to get the manifest file for, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ManifestURI': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ManifestURI** *(string) --* 

          The Amazon S3 presigned URL for the manifest file associated with the specified ``JobId`` value.

          
    

  .. py:method:: get_job_unlock_code(**kwargs)

    

    Returns the ``UnlockCode`` code value for the specified job. A particular ``UnlockCode`` value can be accessed for up to 90 days after the associated job has been created.

     

    The ``UnlockCode`` value is a 29-character code with 25 alphanumeric characters and 4 hyphens. This code is used to decrypt the manifest file when it is passed along with the manifest to the Snowball through the Snowball client when the client is started for the first time.

     

    As a best practice, we recommend that you don't save a copy of the ``UnlockCode`` in the same location as the manifest file for that job. Saving these separately helps prevent unauthorized parties from gaining access to the Snowball associated with that job.

    

    **Request Syntax** 
    ::

      response = client.get_job_unlock_code(
          JobId='string'
      )
    :type JobId: string
    :param JobId: **[REQUIRED]** 

      The ID for the job that you want to get the ``UnlockCode`` value for, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UnlockCode': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **UnlockCode** *(string) --* 

          The ``UnlockCode`` value for the specified job. The ``UnlockCode`` value can be accessed for up to 90 days after the job has been created.

          
    

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


  .. py:method:: get_snowball_usage()

    

    Returns information about the Snowball service limit for your account, and also the number of Snowballs your account has in use.

     

    Note that the default service limit for the number of Snowballs that you can have at one time is 1. If you want to increase your service limit, contact AWS Support.

    

    **Request Syntax** 
    ::

      response = client.get_snowball_usage()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SnowballLimit': 123,
            'SnowballsInUse': 123
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **SnowballLimit** *(integer) --* 

          The service limit for number of Snowballs this account can have at once. The default service limit is 1 (one).

          
        

        - **SnowballsInUse** *(integer) --* 

          The number of Snowballs that this account is currently using.

          
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: list_jobs(**kwargs)

    

    Returns an array of ``JobListEntry`` objects of the specified length. Each ``JobListEntry`` object contains a job's state, a job's ID, and a value that indicates whether the job is a job part, in the case of export jobs. Calling this API action in one of the US regions will return jobs from the list of all jobs associated with this account in all US regions.

    

    **Request Syntax** 
    ::

      response = client.list_jobs(
          MaxResults=123,
          NextToken='string'
      )
    :type MaxResults: integer
    :param MaxResults: 

      The number of ``JobListEntry`` objects to return.

      

    
    :type NextToken: string
    :param NextToken: 

      HTTP requests are stateless. To identify what object comes "next" in the list of ``JobListEntry`` objects, you have the option of specifying ``NextToken`` as the starting point for your returned list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'JobListEntries': [
                {
                    'JobId': 'string',
                    'JobState': 'New'|'PreparingAppliance'|'PreparingShipment'|'InTransitToCustomer'|'WithCustomer'|'InTransitToAWS'|'WithAWS'|'InProgress'|'Complete'|'Cancelled'|'Listing'|'Pending',
                    'IsMaster': True|False
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **JobListEntries** *(list) --* 

          Each ``JobListEntry`` object contains a job's state, a job's ID, and a value that indicates whether the job is a job part, in the case of export jobs. 

          
          

          - *(dict) --* 

            Each ``JobListEntry`` object contains a job's state, a job's ID, and a value that indicates whether the job is a job part, in the case of an export job.

            
            

            - **JobId** *(string) --* 

              The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

              
            

            - **JobState** *(string) --* 

              The current state of this job.

              
            

            - **IsMaster** *(boolean) --* 

              A value that indicates that this job is a master job. A master job represents a successful request to create an export job. Master jobs aren't associated with any Snowballs. Instead, each master job will have at least one job part, and each job part is associated with a Snowball. It might take some time before the job parts associated with a particular master job are listed, because they are created after the master job is created.

              
        
      
        

        - **NextToken** *(string) --* 

          HTTP requests are stateless. If you use this automatically generated ``NextToken`` value in your next ``ListJobs`` call, your returned ``JobListEntry`` objects will start from this point in the array.

          
    

  .. py:method:: update_job(**kwargs)

    

    While a job's ``JobState`` value is ``New`` , you can update some of the information associated with a job. Once the job changes to a different job state, usually within 60 minutes of the job being created, this action is no longer available.

    

    **Request Syntax** 
    ::

      response = client.update_job(
          JobId='string',
          RoleARN='string',
          Notification={
              'SnsTopicARN': 'string',
              'JobStatesToNotify': [
                  'New'|'PreparingAppliance'|'PreparingShipment'|'InTransitToCustomer'|'WithCustomer'|'InTransitToAWS'|'WithAWS'|'InProgress'|'Complete'|'Cancelled'|'Listing'|'Pending',
              ],
              'NotifyAll': True|False
          },
          Resources={
              'S3Resources': [
                  {
                      'BucketArn': 'string',
                      'KeyRange': {
                          'BeginMarker': 'string',
                          'EndMarker': 'string'
                      }
                  },
              ]
          },
          AddressId='string',
          ShippingOption='SECOND_DAY'|'NEXT_DAY'|'EXPRESS'|'STANDARD',
          Description='string',
          SnowballCapacityPreference='T50'|'T80'|'NoPreference'
      )
    :type JobId: string
    :param JobId: **[REQUIRED]** 

      The job ID of the job that you want to update, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

      

    
    :type RoleARN: string
    :param RoleARN: 

      The new role Amazon Resource Name (ARN) that you want to associate with this job. To create a role ARN, use the `CreateRole`_ AWS Identity and Access Management (IAM) API action.

      

    
    :type Notification: dict
    :param Notification: 

      The new or updated  Notification object.

      

    
      - **SnsTopicARN** *(string) --* 

        The new SNS ``TopicArn`` that you want to associate with this job. You can create Amazon Resource Names (ARNs) for topics by using the `CreateTopic`_ Amazon SNS API action.

         

        Note that you can subscribe email addresses to an Amazon SNS topic through the AWS Management Console, or by using the `Subscribe`_ AWS Simple Notification Service (SNS) API action.

        

      
      - **JobStatesToNotify** *(list) --* 

        The list of job states that will trigger a notification for this job.

        

      
        - *(string) --* 

        
    
      - **NotifyAll** *(boolean) --* 

        Any change in job state will trigger a notification for this job.

        

      
    
    :type Resources: dict
    :param Resources: 

      The updated  S3Resource object (for a single Amazon S3 bucket or key range), or the updated  JobResource object (for multiple buckets or key ranges). 

      

    
      - **S3Resources** *(list) --* 

        An array of ``S3Resource`` objects.

        

      
        - *(dict) --* 

          Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into. For export jobs, this object can have an optional ``KeyRange`` value. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

          

        
          - **BucketArn** *(string) --* 

            The Amazon Resource Name (ARN) of an Amazon S3 bucket.

            

          
          - **KeyRange** *(dict) --* 

            For export jobs, you can provide an optional ``KeyRange`` within a specific Amazon S3 bucket. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

            

          
            - **BeginMarker** *(string) --* 

              The key that starts an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

              

            
            - **EndMarker** *(string) --* 

              The key that ends an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

              

            
          
        
    
    
    :type AddressId: string
    :param AddressId: 

      The ID of the updated  Address object.

      

    
    :type ShippingOption: string
    :param ShippingOption: 

      The updated shipping option value of this job's  ShippingDetails object.

      

    
    :type Description: string
    :param Description: 

      The updated description of this job's  JobMetadata object.

      

    
    :type SnowballCapacityPreference: string
    :param SnowballCapacityPreference: 

      The updated ``SnowballCapacityPreference`` of this job's  JobMetadata object. Note that the 50 TB Snowballs are only available in the US regions.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    