

.. _Tagging Amazon Elasticsearch Service Domains for more information.: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-awsresorcetagging
.. _Creating Elasticsearch Domains: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomains
.. _Configuring Advanced Options: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-advanced-options
.. _Configuring Access Policies: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-access-policies
.. _Configuration Advanced Options: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-advanced-options
.. _Configuring EBS-based Storage: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-ebs
.. _Identifiers for IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/index.html?Using_Identifiers.html
.. _About Zone Awareness: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-zoneawareness
.. _About Dedicated Master Nodes: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-dedicatedmasternodes


********************
ElasticsearchService
********************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: ElasticsearchService.Client

  A low-level client representing Amazon Elasticsearch Service::

    
    import boto3
    
    client = boto3.client('es')

  
  These are the available methods:
  
  *   :py:meth:`add_tags`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_elasticsearch_domain`

  
  *   :py:meth:`delete_elasticsearch_domain`

  
  *   :py:meth:`describe_elasticsearch_domain`

  
  *   :py:meth:`describe_elasticsearch_domain_config`

  
  *   :py:meth:`describe_elasticsearch_domains`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_domain_names`

  
  *   :py:meth:`list_tags`

  
  *   :py:meth:`remove_tags`

  
  *   :py:meth:`update_elasticsearch_domain_config`

  

  .. py:method:: add_tags(**kwargs)

    

    Attaches tags to an existing Elasticsearch domain. Tags are a set of case-sensitive key value pairs. An Elasticsearch domain may have up to 10 tags. See `Tagging Amazon Elasticsearch Service Domains for more information.`_ 

    

    **Request Syntax** 
    ::

      response = client.add_tags(
          ARN='string',
          TagList=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type ARN: string
    :param ARN: **[REQUIRED]** 

      Specify the ``ARN`` for which you want to add the tags.

      

    
    :type TagList: list
    :param TagList: **[REQUIRED]** 

      List of ``Tag`` that need to be added for the Elasticsearch domain. 

      

    
      - *(dict) --* 

        Specifies a key value pair for a resource tag.

        

      
        - **Key** *(string) --* **[REQUIRED]** 

          Specifies the ``TagKey`` , the name of the tag. Tag keys must be unique for the Elasticsearch domain to which they are attached.

          

        
        - **Value** *(string) --* **[REQUIRED]** 

          Specifies the ``TagValue`` , the value assigned to the corresponding tag key. Tag values can be null and do not have to be unique in a tag set. For example, you can have a key value pair in a tag set of ``project : Trinity`` and ``cost-center : Trinity`` 

          

        
      
  
    
    :returns: None

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


  .. py:method:: create_elasticsearch_domain(**kwargs)

    

    Creates a new Elasticsearch domain. For more information, see `Creating Elasticsearch Domains`_ in the *Amazon Elasticsearch Service Developer Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_elasticsearch_domain(
          DomainName='string',
          ElasticsearchVersion='string',
          ElasticsearchClusterConfig={
              'InstanceType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
              'InstanceCount': 123,
              'DedicatedMasterEnabled': True|False,
              'ZoneAwarenessEnabled': True|False,
              'DedicatedMasterType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
              'DedicatedMasterCount': 123
          },
          EBSOptions={
              'EBSEnabled': True|False,
              'VolumeType': 'standard'|'gp2'|'io1',
              'VolumeSize': 123,
              'Iops': 123
          },
          AccessPolicies='string',
          SnapshotOptions={
              'AutomatedSnapshotStartHour': 123
          },
          AdvancedOptions={
              'string': 'string'
          }
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of the Elasticsearch domain that you are creating. Domain names are unique across the domains owned by an account within an AWS region. Domain names must start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

      

    
    :type ElasticsearchVersion: string
    :param ElasticsearchVersion: 

      String of format X.Y to specify version for the Elasticsearch domain eg. "1.5" or "2.3". For more information, see `Creating Elasticsearch Domains`_ in the *Amazon Elasticsearch Service Developer Guide* .

      

    
    :type ElasticsearchClusterConfig: dict
    :param ElasticsearchClusterConfig: 

      Configuration options for an Elasticsearch domain. Specifies the instance type and number of instances in the domain cluster. 

      

    
      - **InstanceType** *(string) --* 

        The instance type for an Elasticsearch cluster.

        

      
      - **InstanceCount** *(integer) --* 

        The number of instances in the specified domain cluster.

        

      
      - **DedicatedMasterEnabled** *(boolean) --* 

        A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes`_ for more information.

        

      
      - **ZoneAwarenessEnabled** *(boolean) --* 

        A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness`_ for more information.

        

      
      - **DedicatedMasterType** *(string) --* 

        The instance type for a dedicated master node.

        

      
      - **DedicatedMasterCount** *(integer) --* 

        Total number of dedicated master nodes, active and on standby, for the cluster.

        

      
    
    :type EBSOptions: dict
    :param EBSOptions: 

      Options to enable, disable and specify the type and size of EBS storage volumes. 

      

    
      - **EBSEnabled** *(boolean) --* 

        Specifies whether EBS-based storage is enabled.

        

      
      - **VolumeType** *(string) --* 

        Specifies the volume type for EBS-based storage.

        

      
      - **VolumeSize** *(integer) --* 

        Integer to specify the size of an EBS volume.

        

      
      - **Iops** *(integer) --* 

        Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

        

      
    
    :type AccessPolicies: string
    :param AccessPolicies: 

      IAM access policy as a JSON-formatted string.

      

    
    :type SnapshotOptions: dict
    :param SnapshotOptions: 

      Option to set time, in UTC format, of the daily automated snapshot. Default value is 0 hours. 

      

    
      - **AutomatedSnapshotStartHour** *(integer) --* 

        Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

        

      
    
    :type AdvancedOptions: dict
    :param AdvancedOptions: 

      Option to allow references to indices in an HTTP request body. Must be ``false`` when configuring access to individual sub-resources. By default, the value is ``true`` . See `Configuration Advanced Options`_ for more information.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DomainStatus': {
                'DomainId': 'string',
                'DomainName': 'string',
                'ARN': 'string',
                'Created': True|False,
                'Deleted': True|False,
                'Endpoint': 'string',
                'Processing': True|False,
                'ElasticsearchVersion': 'string',
                'ElasticsearchClusterConfig': {
                    'InstanceType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                    'InstanceCount': 123,
                    'DedicatedMasterEnabled': True|False,
                    'ZoneAwarenessEnabled': True|False,
                    'DedicatedMasterType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                    'DedicatedMasterCount': 123
                },
                'EBSOptions': {
                    'EBSEnabled': True|False,
                    'VolumeType': 'standard'|'gp2'|'io1',
                    'VolumeSize': 123,
                    'Iops': 123
                },
                'AccessPolicies': 'string',
                'SnapshotOptions': {
                    'AutomatedSnapshotStartHour': 123
                },
                'AdvancedOptions': {
                    'string': 'string'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of a ``CreateElasticsearchDomain`` operation. Contains the status of the newly created Elasticsearch domain.

        
        

        - **DomainStatus** *(dict) --* 

          The status of the newly created Elasticsearch domain. 

          
          

          - **DomainId** *(string) --* 

            The unique identifier for the specified Elasticsearch domain.

            
          

          - **DomainName** *(string) --* 

            The name of an Elasticsearch domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

            
          

          - **ARN** *(string) --* 

            The Amazon resource name (ARN) of an Elasticsearch domain. See `Identifiers for IAM Entities`_ in *Using AWS Identity and Access Management* for more information.

            
          

          - **Created** *(boolean) --* 

            The domain creation status. ``True`` if the creation of an Elasticsearch domain is complete. ``False`` if domain creation is still in progress.

            
          

          - **Deleted** *(boolean) --* 

            The domain deletion status. ``True`` if a delete request has been received for the domain but resource cleanup is still in progress. ``False`` if the domain has not been deleted. Once domain deletion is complete, the status of the domain is no longer returned.

            
          

          - **Endpoint** *(string) --* 

            The Elasticsearch domain endpoint that you use to submit index and search requests.

            
          

          - **Processing** *(boolean) --* 

            The status of the Elasticsearch domain configuration. ``True`` if Amazon Elasticsearch Service is processing configuration changes. ``False`` if the configuration is active.

            
          

          - **ElasticsearchVersion** *(string) --* 
          

          - **ElasticsearchClusterConfig** *(dict) --* 

            The type and number of instances in the domain cluster.

            
            

            - **InstanceType** *(string) --* 

              The instance type for an Elasticsearch cluster.

              
            

            - **InstanceCount** *(integer) --* 

              The number of instances in the specified domain cluster.

              
            

            - **DedicatedMasterEnabled** *(boolean) --* 

              A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes`_ for more information.

              
            

            - **ZoneAwarenessEnabled** *(boolean) --* 

              A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness`_ for more information.

              
            

            - **DedicatedMasterType** *(string) --* 

              The instance type for a dedicated master node.

              
            

            - **DedicatedMasterCount** *(integer) --* 

              Total number of dedicated master nodes, active and on standby, for the cluster.

              
        
          

          - **EBSOptions** *(dict) --* 

            The ``EBSOptions`` for the specified domain. See `Configuring EBS-based Storage`_ for more information.

            
            

            - **EBSEnabled** *(boolean) --* 

              Specifies whether EBS-based storage is enabled.

              
            

            - **VolumeType** *(string) --* 

              Specifies the volume type for EBS-based storage.

              
            

            - **VolumeSize** *(integer) --* 

              Integer to specify the size of an EBS volume.

              
            

            - **Iops** *(integer) --* 

              Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

              
        
          

          - **AccessPolicies** *(string) --* 

            IAM access policy as a JSON-formatted string.

            
          

          - **SnapshotOptions** *(dict) --* 

            Specifies the status of the ``SnapshotOptions`` 

            
            

            - **AutomatedSnapshotStartHour** *(integer) --* 

              Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

              
        
          

          - **AdvancedOptions** *(dict) --* 

            Specifies the status of the ``AdvancedOptions`` 

            
            

            - *(string) --* 
              

              - *(string) --* 
        
      
      
    

  .. py:method:: delete_elasticsearch_domain(**kwargs)

    

    Permanently deletes the specified Elasticsearch domain and all of its data. Once a domain is deleted, it cannot be recovered.

    

    **Request Syntax** 
    ::

      response = client.delete_elasticsearch_domain(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of the Elasticsearch domain that you want to permanently delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DomainStatus': {
                'DomainId': 'string',
                'DomainName': 'string',
                'ARN': 'string',
                'Created': True|False,
                'Deleted': True|False,
                'Endpoint': 'string',
                'Processing': True|False,
                'ElasticsearchVersion': 'string',
                'ElasticsearchClusterConfig': {
                    'InstanceType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                    'InstanceCount': 123,
                    'DedicatedMasterEnabled': True|False,
                    'ZoneAwarenessEnabled': True|False,
                    'DedicatedMasterType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                    'DedicatedMasterCount': 123
                },
                'EBSOptions': {
                    'EBSEnabled': True|False,
                    'VolumeType': 'standard'|'gp2'|'io1',
                    'VolumeSize': 123,
                    'Iops': 123
                },
                'AccessPolicies': 'string',
                'SnapshotOptions': {
                    'AutomatedSnapshotStartHour': 123
                },
                'AdvancedOptions': {
                    'string': 'string'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of a ``DeleteElasticsearchDomain`` request. Contains the status of the pending deletion, or no status if the domain and all of its resources have been deleted.

        
        

        - **DomainStatus** *(dict) --* 

          The status of the Elasticsearch domain being deleted.

          
          

          - **DomainId** *(string) --* 

            The unique identifier for the specified Elasticsearch domain.

            
          

          - **DomainName** *(string) --* 

            The name of an Elasticsearch domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

            
          

          - **ARN** *(string) --* 

            The Amazon resource name (ARN) of an Elasticsearch domain. See `Identifiers for IAM Entities`_ in *Using AWS Identity and Access Management* for more information.

            
          

          - **Created** *(boolean) --* 

            The domain creation status. ``True`` if the creation of an Elasticsearch domain is complete. ``False`` if domain creation is still in progress.

            
          

          - **Deleted** *(boolean) --* 

            The domain deletion status. ``True`` if a delete request has been received for the domain but resource cleanup is still in progress. ``False`` if the domain has not been deleted. Once domain deletion is complete, the status of the domain is no longer returned.

            
          

          - **Endpoint** *(string) --* 

            The Elasticsearch domain endpoint that you use to submit index and search requests.

            
          

          - **Processing** *(boolean) --* 

            The status of the Elasticsearch domain configuration. ``True`` if Amazon Elasticsearch Service is processing configuration changes. ``False`` if the configuration is active.

            
          

          - **ElasticsearchVersion** *(string) --* 
          

          - **ElasticsearchClusterConfig** *(dict) --* 

            The type and number of instances in the domain cluster.

            
            

            - **InstanceType** *(string) --* 

              The instance type for an Elasticsearch cluster.

              
            

            - **InstanceCount** *(integer) --* 

              The number of instances in the specified domain cluster.

              
            

            - **DedicatedMasterEnabled** *(boolean) --* 

              A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes`_ for more information.

              
            

            - **ZoneAwarenessEnabled** *(boolean) --* 

              A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness`_ for more information.

              
            

            - **DedicatedMasterType** *(string) --* 

              The instance type for a dedicated master node.

              
            

            - **DedicatedMasterCount** *(integer) --* 

              Total number of dedicated master nodes, active and on standby, for the cluster.

              
        
          

          - **EBSOptions** *(dict) --* 

            The ``EBSOptions`` for the specified domain. See `Configuring EBS-based Storage`_ for more information.

            
            

            - **EBSEnabled** *(boolean) --* 

              Specifies whether EBS-based storage is enabled.

              
            

            - **VolumeType** *(string) --* 

              Specifies the volume type for EBS-based storage.

              
            

            - **VolumeSize** *(integer) --* 

              Integer to specify the size of an EBS volume.

              
            

            - **Iops** *(integer) --* 

              Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

              
        
          

          - **AccessPolicies** *(string) --* 

            IAM access policy as a JSON-formatted string.

            
          

          - **SnapshotOptions** *(dict) --* 

            Specifies the status of the ``SnapshotOptions`` 

            
            

            - **AutomatedSnapshotStartHour** *(integer) --* 

              Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

              
        
          

          - **AdvancedOptions** *(dict) --* 

            Specifies the status of the ``AdvancedOptions`` 

            
            

            - *(string) --* 
              

              - *(string) --* 
        
      
      
    

  .. py:method:: describe_elasticsearch_domain(**kwargs)

    

    Returns domain configuration information about the specified Elasticsearch domain, including the domain ID, domain endpoint, and domain ARN.

    

    **Request Syntax** 
    ::

      response = client.describe_elasticsearch_domain(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of the Elasticsearch domain for which you want information.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DomainStatus': {
                'DomainId': 'string',
                'DomainName': 'string',
                'ARN': 'string',
                'Created': True|False,
                'Deleted': True|False,
                'Endpoint': 'string',
                'Processing': True|False,
                'ElasticsearchVersion': 'string',
                'ElasticsearchClusterConfig': {
                    'InstanceType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                    'InstanceCount': 123,
                    'DedicatedMasterEnabled': True|False,
                    'ZoneAwarenessEnabled': True|False,
                    'DedicatedMasterType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                    'DedicatedMasterCount': 123
                },
                'EBSOptions': {
                    'EBSEnabled': True|False,
                    'VolumeType': 'standard'|'gp2'|'io1',
                    'VolumeSize': 123,
                    'Iops': 123
                },
                'AccessPolicies': 'string',
                'SnapshotOptions': {
                    'AutomatedSnapshotStartHour': 123
                },
                'AdvancedOptions': {
                    'string': 'string'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of a ``DescribeElasticsearchDomain`` request. Contains the status of the domain specified in the request.

        
        

        - **DomainStatus** *(dict) --* 

          The current status of the Elasticsearch domain.

          
          

          - **DomainId** *(string) --* 

            The unique identifier for the specified Elasticsearch domain.

            
          

          - **DomainName** *(string) --* 

            The name of an Elasticsearch domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

            
          

          - **ARN** *(string) --* 

            The Amazon resource name (ARN) of an Elasticsearch domain. See `Identifiers for IAM Entities`_ in *Using AWS Identity and Access Management* for more information.

            
          

          - **Created** *(boolean) --* 

            The domain creation status. ``True`` if the creation of an Elasticsearch domain is complete. ``False`` if domain creation is still in progress.

            
          

          - **Deleted** *(boolean) --* 

            The domain deletion status. ``True`` if a delete request has been received for the domain but resource cleanup is still in progress. ``False`` if the domain has not been deleted. Once domain deletion is complete, the status of the domain is no longer returned.

            
          

          - **Endpoint** *(string) --* 

            The Elasticsearch domain endpoint that you use to submit index and search requests.

            
          

          - **Processing** *(boolean) --* 

            The status of the Elasticsearch domain configuration. ``True`` if Amazon Elasticsearch Service is processing configuration changes. ``False`` if the configuration is active.

            
          

          - **ElasticsearchVersion** *(string) --* 
          

          - **ElasticsearchClusterConfig** *(dict) --* 

            The type and number of instances in the domain cluster.

            
            

            - **InstanceType** *(string) --* 

              The instance type for an Elasticsearch cluster.

              
            

            - **InstanceCount** *(integer) --* 

              The number of instances in the specified domain cluster.

              
            

            - **DedicatedMasterEnabled** *(boolean) --* 

              A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes`_ for more information.

              
            

            - **ZoneAwarenessEnabled** *(boolean) --* 

              A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness`_ for more information.

              
            

            - **DedicatedMasterType** *(string) --* 

              The instance type for a dedicated master node.

              
            

            - **DedicatedMasterCount** *(integer) --* 

              Total number of dedicated master nodes, active and on standby, for the cluster.

              
        
          

          - **EBSOptions** *(dict) --* 

            The ``EBSOptions`` for the specified domain. See `Configuring EBS-based Storage`_ for more information.

            
            

            - **EBSEnabled** *(boolean) --* 

              Specifies whether EBS-based storage is enabled.

              
            

            - **VolumeType** *(string) --* 

              Specifies the volume type for EBS-based storage.

              
            

            - **VolumeSize** *(integer) --* 

              Integer to specify the size of an EBS volume.

              
            

            - **Iops** *(integer) --* 

              Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

              
        
          

          - **AccessPolicies** *(string) --* 

            IAM access policy as a JSON-formatted string.

            
          

          - **SnapshotOptions** *(dict) --* 

            Specifies the status of the ``SnapshotOptions`` 

            
            

            - **AutomatedSnapshotStartHour** *(integer) --* 

              Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

              
        
          

          - **AdvancedOptions** *(dict) --* 

            Specifies the status of the ``AdvancedOptions`` 

            
            

            - *(string) --* 
              

              - *(string) --* 
        
      
      
    

  .. py:method:: describe_elasticsearch_domain_config(**kwargs)

    

    Provides cluster configuration information about the specified Elasticsearch domain, such as the state, creation date, update version, and update date for cluster options.

    

    **Request Syntax** 
    ::

      response = client.describe_elasticsearch_domain_config(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The Elasticsearch domain that you want to get information about.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DomainConfig': {
                'ElasticsearchVersion': {
                    'Options': 'string',
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'ElasticsearchClusterConfig': {
                    'Options': {
                        'InstanceType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                        'InstanceCount': 123,
                        'DedicatedMasterEnabled': True|False,
                        'ZoneAwarenessEnabled': True|False,
                        'DedicatedMasterType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                        'DedicatedMasterCount': 123
                    },
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'EBSOptions': {
                    'Options': {
                        'EBSEnabled': True|False,
                        'VolumeType': 'standard'|'gp2'|'io1',
                        'VolumeSize': 123,
                        'Iops': 123
                    },
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'AccessPolicies': {
                    'Options': 'string',
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'SnapshotOptions': {
                    'Options': {
                        'AutomatedSnapshotStartHour': 123
                    },
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'AdvancedOptions': {
                    'Options': {
                        'string': 'string'
                    },
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of a ``DescribeElasticsearchDomainConfig`` request. Contains the configuration information of the requested domain.

        
        

        - **DomainConfig** *(dict) --* 

          The configuration information of the domain requested in the ``DescribeElasticsearchDomainConfig`` request.

          
          

          - **ElasticsearchVersion** *(dict) --* 

            String of format X.Y to specify version for the Elasticsearch domain.

            
            

            - **Options** *(string) --* 

              Specifies the Elasticsearch version for the specified Elasticsearch domain.

              
            

            - **Status** *(dict) --* 

              Specifies the status of the Elasticsearch version options for the specified Elasticsearch domain.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **ElasticsearchClusterConfig** *(dict) --* 

            Specifies the ``ElasticsearchClusterConfig`` for the Elasticsearch domain.

            
            

            - **Options** *(dict) --* 

              Specifies the cluster configuration for the specified Elasticsearch domain.

              
              

              - **InstanceType** *(string) --* 

                The instance type for an Elasticsearch cluster.

                
              

              - **InstanceCount** *(integer) --* 

                The number of instances in the specified domain cluster.

                
              

              - **DedicatedMasterEnabled** *(boolean) --* 

                A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes`_ for more information.

                
              

              - **ZoneAwarenessEnabled** *(boolean) --* 

                A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness`_ for more information.

                
              

              - **DedicatedMasterType** *(string) --* 

                The instance type for a dedicated master node.

                
              

              - **DedicatedMasterCount** *(integer) --* 

                Total number of dedicated master nodes, active and on standby, for the cluster.

                
          
            

            - **Status** *(dict) --* 

              Specifies the status of the configuration for the specified Elasticsearch domain.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **EBSOptions** *(dict) --* 

            Specifies the ``EBSOptions`` for the Elasticsearch domain.

            
            

            - **Options** *(dict) --* 

              Specifies the EBS options for the specified Elasticsearch domain.

              
              

              - **EBSEnabled** *(boolean) --* 

                Specifies whether EBS-based storage is enabled.

                
              

              - **VolumeType** *(string) --* 

                Specifies the volume type for EBS-based storage.

                
              

              - **VolumeSize** *(integer) --* 

                Integer to specify the size of an EBS volume.

                
              

              - **Iops** *(integer) --* 

                Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

                
          
            

            - **Status** *(dict) --* 

              Specifies the status of the EBS options for the specified Elasticsearch domain.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **AccessPolicies** *(dict) --* 

            IAM access policy as a JSON-formatted string.

            
            

            - **Options** *(string) --* 

              The access policy configured for the Elasticsearch domain. Access policies may be resource-based, IP-based, or IAM-based. See `Configuring Access Policies`_ for more information.

              
            

            - **Status** *(dict) --* 

              The status of the access policy for the Elasticsearch domain. See ``OptionStatus`` for the status information that's included. 

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **SnapshotOptions** *(dict) --* 

            Specifies the ``SnapshotOptions`` for the Elasticsearch domain.

            
            

            - **Options** *(dict) --* 

              Specifies the daily snapshot options specified for the Elasticsearch domain.

              
              

              - **AutomatedSnapshotStartHour** *(integer) --* 

                Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

                
          
            

            - **Status** *(dict) --* 

              Specifies the status of a daily automated snapshot.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **AdvancedOptions** *(dict) --* 

            Specifies the ``AdvancedOptions`` for the domain. See `Configuring Advanced Options`_ for more information.

            
            

            - **Options** *(dict) --* 

              Specifies the status of advanced options for the specified Elasticsearch domain.

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
            

            - **Status** *(dict) --* 

              Specifies the status of ``OptionStatus`` for advanced options for the specified Elasticsearch domain.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
      
    

  .. py:method:: describe_elasticsearch_domains(**kwargs)

    

    Returns domain configuration information about the specified Elasticsearch domains, including the domain ID, domain endpoint, and domain ARN.

    

    **Request Syntax** 
    ::

      response = client.describe_elasticsearch_domains(
          DomainNames=[
              'string',
          ]
      )
    :type DomainNames: list
    :param DomainNames: **[REQUIRED]** 

      The Elasticsearch domains for which you want information.

      

    
      - *(string) --* 

        The name of an Elasticsearch domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

        

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DomainStatusList': [
                {
                    'DomainId': 'string',
                    'DomainName': 'string',
                    'ARN': 'string',
                    'Created': True|False,
                    'Deleted': True|False,
                    'Endpoint': 'string',
                    'Processing': True|False,
                    'ElasticsearchVersion': 'string',
                    'ElasticsearchClusterConfig': {
                        'InstanceType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                        'InstanceCount': 123,
                        'DedicatedMasterEnabled': True|False,
                        'ZoneAwarenessEnabled': True|False,
                        'DedicatedMasterType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                        'DedicatedMasterCount': 123
                    },
                    'EBSOptions': {
                        'EBSEnabled': True|False,
                        'VolumeType': 'standard'|'gp2'|'io1',
                        'VolumeSize': 123,
                        'Iops': 123
                    },
                    'AccessPolicies': 'string',
                    'SnapshotOptions': {
                        'AutomatedSnapshotStartHour': 123
                    },
                    'AdvancedOptions': {
                        'string': 'string'
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of a ``DescribeElasticsearchDomains`` request. Contains the status of the specified domains or all domains owned by the account.

        
        

        - **DomainStatusList** *(list) --* 

          The status of the domains requested in the ``DescribeElasticsearchDomains`` request.

          
          

          - *(dict) --* 

            The current status of an Elasticsearch domain.

            
            

            - **DomainId** *(string) --* 

              The unique identifier for the specified Elasticsearch domain.

              
            

            - **DomainName** *(string) --* 

              The name of an Elasticsearch domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

              
            

            - **ARN** *(string) --* 

              The Amazon resource name (ARN) of an Elasticsearch domain. See `Identifiers for IAM Entities`_ in *Using AWS Identity and Access Management* for more information.

              
            

            - **Created** *(boolean) --* 

              The domain creation status. ``True`` if the creation of an Elasticsearch domain is complete. ``False`` if domain creation is still in progress.

              
            

            - **Deleted** *(boolean) --* 

              The domain deletion status. ``True`` if a delete request has been received for the domain but resource cleanup is still in progress. ``False`` if the domain has not been deleted. Once domain deletion is complete, the status of the domain is no longer returned.

              
            

            - **Endpoint** *(string) --* 

              The Elasticsearch domain endpoint that you use to submit index and search requests.

              
            

            - **Processing** *(boolean) --* 

              The status of the Elasticsearch domain configuration. ``True`` if Amazon Elasticsearch Service is processing configuration changes. ``False`` if the configuration is active.

              
            

            - **ElasticsearchVersion** *(string) --* 
            

            - **ElasticsearchClusterConfig** *(dict) --* 

              The type and number of instances in the domain cluster.

              
              

              - **InstanceType** *(string) --* 

                The instance type for an Elasticsearch cluster.

                
              

              - **InstanceCount** *(integer) --* 

                The number of instances in the specified domain cluster.

                
              

              - **DedicatedMasterEnabled** *(boolean) --* 

                A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes`_ for more information.

                
              

              - **ZoneAwarenessEnabled** *(boolean) --* 

                A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness`_ for more information.

                
              

              - **DedicatedMasterType** *(string) --* 

                The instance type for a dedicated master node.

                
              

              - **DedicatedMasterCount** *(integer) --* 

                Total number of dedicated master nodes, active and on standby, for the cluster.

                
          
            

            - **EBSOptions** *(dict) --* 

              The ``EBSOptions`` for the specified domain. See `Configuring EBS-based Storage`_ for more information.

              
              

              - **EBSEnabled** *(boolean) --* 

                Specifies whether EBS-based storage is enabled.

                
              

              - **VolumeType** *(string) --* 

                Specifies the volume type for EBS-based storage.

                
              

              - **VolumeSize** *(integer) --* 

                Integer to specify the size of an EBS volume.

                
              

              - **Iops** *(integer) --* 

                Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

                
          
            

            - **AccessPolicies** *(string) --* 

              IAM access policy as a JSON-formatted string.

              
            

            - **SnapshotOptions** *(dict) --* 

              Specifies the status of the ``SnapshotOptions`` 

              
              

              - **AutomatedSnapshotStartHour** *(integer) --* 

                Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

                
          
            

            - **AdvancedOptions** *(dict) --* 

              Specifies the status of the ``AdvancedOptions`` 

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
        
      
    

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

        


  .. py:method:: list_domain_names()

    

    Returns the name of all Elasticsearch domains owned by the current user's account. 

    

    **Request Syntax** 

    ::

      response = client.list_domain_names()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DomainNames': [
                {
                    'DomainName': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of a ``ListDomainNames`` operation. Contains the names of all Elasticsearch domains owned by this account.

        
        

        - **DomainNames** *(list) --* 

          List of Elasticsearch domain names.

          
          

          - *(dict) --* 
            

            - **DomainName** *(string) --* 

              Specifies the ``DomainName`` .

              
        
      
    

  .. py:method:: list_tags(**kwargs)

    

    Returns all tags for the given Elasticsearch domain.

    

    **Request Syntax** 
    ::

      response = client.list_tags(
          ARN='string'
      )
    :type ARN: string
    :param ARN: **[REQUIRED]** 

      Specify the ``ARN`` for the Elasticsearch domain to which the tags are attached that you want to view.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TagList': [
                {
                    'Key': 'string',
                    'Value': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of a ``ListTags`` operation. Contains tags for all requested Elasticsearch domains.

        
        

        - **TagList** *(list) --* 

          List of ``Tag`` for the requested Elasticsearch domain.

          
          

          - *(dict) --* 

            Specifies a key value pair for a resource tag.

            
            

            - **Key** *(string) --* 

              Specifies the ``TagKey`` , the name of the tag. Tag keys must be unique for the Elasticsearch domain to which they are attached.

              
            

            - **Value** *(string) --* 

              Specifies the ``TagValue`` , the value assigned to the corresponding tag key. Tag values can be null and do not have to be unique in a tag set. For example, you can have a key value pair in a tag set of ``project : Trinity`` and ``cost-center : Trinity`` 

              
        
      
    

  .. py:method:: remove_tags(**kwargs)

    

    Removes the specified set of tags from the specified Elasticsearch domain.

    

    **Request Syntax** 
    ::

      response = client.remove_tags(
          ARN='string',
          TagKeys=[
              'string',
          ]
      )
    :type ARN: string
    :param ARN: **[REQUIRED]** 

      Specifies the ``ARN`` for the Elasticsearch domain from which you want to delete the specified tags.

      

    
    :type TagKeys: list
    :param TagKeys: **[REQUIRED]** 

      Specifies the ``TagKey`` list which you want to remove from the Elasticsearch domain.

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: update_elasticsearch_domain_config(**kwargs)

    

    Modifies the cluster configuration of the specified Elasticsearch domain, setting as setting the instance type and the number of instances. 

    

    **Request Syntax** 
    ::

      response = client.update_elasticsearch_domain_config(
          DomainName='string',
          ElasticsearchClusterConfig={
              'InstanceType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
              'InstanceCount': 123,
              'DedicatedMasterEnabled': True|False,
              'ZoneAwarenessEnabled': True|False,
              'DedicatedMasterType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
              'DedicatedMasterCount': 123
          },
          EBSOptions={
              'EBSEnabled': True|False,
              'VolumeType': 'standard'|'gp2'|'io1',
              'VolumeSize': 123,
              'Iops': 123
          },
          SnapshotOptions={
              'AutomatedSnapshotStartHour': 123
          },
          AdvancedOptions={
              'string': 'string'
          },
          AccessPolicies='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of the Elasticsearch domain that you are updating. 

      

    
    :type ElasticsearchClusterConfig: dict
    :param ElasticsearchClusterConfig: 

      The type and number of instances to instantiate for the domain cluster.

      

    
      - **InstanceType** *(string) --* 

        The instance type for an Elasticsearch cluster.

        

      
      - **InstanceCount** *(integer) --* 

        The number of instances in the specified domain cluster.

        

      
      - **DedicatedMasterEnabled** *(boolean) --* 

        A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes`_ for more information.

        

      
      - **ZoneAwarenessEnabled** *(boolean) --* 

        A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness`_ for more information.

        

      
      - **DedicatedMasterType** *(string) --* 

        The instance type for a dedicated master node.

        

      
      - **DedicatedMasterCount** *(integer) --* 

        Total number of dedicated master nodes, active and on standby, for the cluster.

        

      
    
    :type EBSOptions: dict
    :param EBSOptions: 

      Specify the type and size of the EBS volume that you want to use. 

      

    
      - **EBSEnabled** *(boolean) --* 

        Specifies whether EBS-based storage is enabled.

        

      
      - **VolumeType** *(string) --* 

        Specifies the volume type for EBS-based storage.

        

      
      - **VolumeSize** *(integer) --* 

        Integer to specify the size of an EBS volume.

        

      
      - **Iops** *(integer) --* 

        Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

        

      
    
    :type SnapshotOptions: dict
    :param SnapshotOptions: 

      Option to set the time, in UTC format, for the daily automated snapshot. Default value is ``0`` hours. 

      

    
      - **AutomatedSnapshotStartHour** *(integer) --* 

        Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

        

      
    
    :type AdvancedOptions: dict
    :param AdvancedOptions: 

      Modifies the advanced option to allow references to indices in an HTTP request body. Must be ``false`` when configuring access to individual sub-resources. By default, the value is ``true`` . See `Configuration Advanced Options`_ for more information.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type AccessPolicies: string
    :param AccessPolicies: 

      IAM access policy as a JSON-formatted string.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DomainConfig': {
                'ElasticsearchVersion': {
                    'Options': 'string',
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'ElasticsearchClusterConfig': {
                    'Options': {
                        'InstanceType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                        'InstanceCount': 123,
                        'DedicatedMasterEnabled': True|False,
                        'ZoneAwarenessEnabled': True|False,
                        'DedicatedMasterType': 'm3.medium.elasticsearch'|'m3.large.elasticsearch'|'m3.xlarge.elasticsearch'|'m3.2xlarge.elasticsearch'|'m4.large.elasticsearch'|'m4.xlarge.elasticsearch'|'m4.2xlarge.elasticsearch'|'m4.4xlarge.elasticsearch'|'m4.10xlarge.elasticsearch'|'t2.micro.elasticsearch'|'t2.small.elasticsearch'|'t2.medium.elasticsearch'|'r3.large.elasticsearch'|'r3.xlarge.elasticsearch'|'r3.2xlarge.elasticsearch'|'r3.4xlarge.elasticsearch'|'r3.8xlarge.elasticsearch'|'i2.xlarge.elasticsearch'|'i2.2xlarge.elasticsearch',
                        'DedicatedMasterCount': 123
                    },
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'EBSOptions': {
                    'Options': {
                        'EBSEnabled': True|False,
                        'VolumeType': 'standard'|'gp2'|'io1',
                        'VolumeSize': 123,
                        'Iops': 123
                    },
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'AccessPolicies': {
                    'Options': 'string',
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'SnapshotOptions': {
                    'Options': {
                        'AutomatedSnapshotStartHour': 123
                    },
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                },
                'AdvancedOptions': {
                    'Options': {
                        'string': 'string'
                    },
                    'Status': {
                        'CreationDate': datetime(2015, 1, 1),
                        'UpdateDate': datetime(2015, 1, 1),
                        'UpdateVersion': 123,
                        'State': 'RequiresIndexDocuments'|'Processing'|'Active',
                        'PendingDeletion': True|False
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of an ``UpdateElasticsearchDomain`` request. Contains the status of the Elasticsearch domain being updated.

        
        

        - **DomainConfig** *(dict) --* 

          The status of the updated Elasticsearch domain. 

          
          

          - **ElasticsearchVersion** *(dict) --* 

            String of format X.Y to specify version for the Elasticsearch domain.

            
            

            - **Options** *(string) --* 

              Specifies the Elasticsearch version for the specified Elasticsearch domain.

              
            

            - **Status** *(dict) --* 

              Specifies the status of the Elasticsearch version options for the specified Elasticsearch domain.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **ElasticsearchClusterConfig** *(dict) --* 

            Specifies the ``ElasticsearchClusterConfig`` for the Elasticsearch domain.

            
            

            - **Options** *(dict) --* 

              Specifies the cluster configuration for the specified Elasticsearch domain.

              
              

              - **InstanceType** *(string) --* 

                The instance type for an Elasticsearch cluster.

                
              

              - **InstanceCount** *(integer) --* 

                The number of instances in the specified domain cluster.

                
              

              - **DedicatedMasterEnabled** *(boolean) --* 

                A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes`_ for more information.

                
              

              - **ZoneAwarenessEnabled** *(boolean) --* 

                A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness`_ for more information.

                
              

              - **DedicatedMasterType** *(string) --* 

                The instance type for a dedicated master node.

                
              

              - **DedicatedMasterCount** *(integer) --* 

                Total number of dedicated master nodes, active and on standby, for the cluster.

                
          
            

            - **Status** *(dict) --* 

              Specifies the status of the configuration for the specified Elasticsearch domain.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **EBSOptions** *(dict) --* 

            Specifies the ``EBSOptions`` for the Elasticsearch domain.

            
            

            - **Options** *(dict) --* 

              Specifies the EBS options for the specified Elasticsearch domain.

              
              

              - **EBSEnabled** *(boolean) --* 

                Specifies whether EBS-based storage is enabled.

                
              

              - **VolumeType** *(string) --* 

                Specifies the volume type for EBS-based storage.

                
              

              - **VolumeSize** *(integer) --* 

                Integer to specify the size of an EBS volume.

                
              

              - **Iops** *(integer) --* 

                Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

                
          
            

            - **Status** *(dict) --* 

              Specifies the status of the EBS options for the specified Elasticsearch domain.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **AccessPolicies** *(dict) --* 

            IAM access policy as a JSON-formatted string.

            
            

            - **Options** *(string) --* 

              The access policy configured for the Elasticsearch domain. Access policies may be resource-based, IP-based, or IAM-based. See `Configuring Access Policies`_ for more information.

              
            

            - **Status** *(dict) --* 

              The status of the access policy for the Elasticsearch domain. See ``OptionStatus`` for the status information that's included. 

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **SnapshotOptions** *(dict) --* 

            Specifies the ``SnapshotOptions`` for the Elasticsearch domain.

            
            

            - **Options** *(dict) --* 

              Specifies the daily snapshot options specified for the Elasticsearch domain.

              
              

              - **AutomatedSnapshotStartHour** *(integer) --* 

                Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

                
          
            

            - **Status** *(dict) --* 

              Specifies the status of a daily automated snapshot.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
          

          - **AdvancedOptions** *(dict) --* 

            Specifies the ``AdvancedOptions`` for the domain. See `Configuring Advanced Options`_ for more information.

            
            

            - **Options** *(dict) --* 

              Specifies the status of advanced options for the specified Elasticsearch domain.

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
            

            - **Status** *(dict) --* 

              Specifies the status of ``OptionStatus`` for advanced options for the specified Elasticsearch domain.

              
              

              - **CreationDate** *(datetime) --* 

                Timestamp which tells the creation date for the entity.

                
              

              - **UpdateDate** *(datetime) --* 

                Timestamp which tells the last updated time for the entity.

                
              

              - **UpdateVersion** *(integer) --* 

                Specifies the latest version for the entity.

                
              

              - **State** *(string) --* 

                Provides the ``OptionState`` for the Elasticsearch domain.

                
              

              - **PendingDeletion** *(boolean) --* 

                Indicates whether the Elasticsearch domain is being deleted.

                
          
        
      
    