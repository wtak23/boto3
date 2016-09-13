

***************************
ApplicationDiscoveryService
***************************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: ApplicationDiscoveryService.Client

  A low-level client representing AWS Application Discovery Service::

    
    import boto3
    
    client = boto3.client('discovery')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_tags`

  
  *   :py:meth:`delete_tags`

  
  *   :py:meth:`describe_agents`

  
  *   :py:meth:`describe_configurations`

  
  *   :py:meth:`describe_export_configurations`

  
  *   :py:meth:`describe_tags`

  
  *   :py:meth:`export_configurations`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_configurations`

  
  *   :py:meth:`start_data_collection_by_agent_ids`

  
  *   :py:meth:`stop_data_collection_by_agent_ids`

  

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


  .. py:method:: create_tags(**kwargs)

    

    Creates one or more tags for configuration items. Tags are metadata that help you categorize IT assets. This API accepts a list of multiple configuration items.

    

    **Request Syntax** 
    ::

      response = client.create_tags(
          configurationIds=[
              'string',
          ],
          tags=[
              {
                  'key': 'string',
                  'value': 'string'
              },
          ]
      )
    :type configurationIds: list
    :param configurationIds: **[REQUIRED]** 

      A list of configuration items that you want to tag.

      

    
      - *(string) --* 

      
  
    :type tags: list
    :param tags: **[REQUIRED]** 

      Tags that you want to associate with one or more configuration items. Specify the tags that you want to create in a *key* -*value* format. For example:

       

       ``{"key": "serverType", "value": "webServer"}``  

      

    
      - *(dict) --* 

        Metadata that help you categorize IT assets.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          A type of tag to filter on.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          A value for a tag key to filter on.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: delete_tags(**kwargs)

    

    Deletes the association between configuration items and one or more tags. This API accepts a list of multiple configuration items.

    

    **Request Syntax** 
    ::

      response = client.delete_tags(
          configurationIds=[
              'string',
          ],
          tags=[
              {
                  'key': 'string',
                  'value': 'string'
              },
          ]
      )
    :type configurationIds: list
    :param configurationIds: **[REQUIRED]** 

      A list of configuration items with tags that you want to delete.

      

    
      - *(string) --* 

      
  
    :type tags: list
    :param tags: 

      Tags that you want to delete from one or more configuration items. Specify the tags that you want to delete in a *key* -*value* format. For example:

       

       ``{"key": "serverType", "value": "webServer"}``  

      

    
      - *(dict) --* 

        Metadata that help you categorize IT assets.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          A type of tag to filter on.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          A value for a tag key to filter on.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: describe_agents(**kwargs)

    

    Lists AWS agents by ID or lists all agents associated with your user account if you did not specify an agent ID.

    

    **Request Syntax** 
    ::

      response = client.describe_agents(
          agentIds=[
              'string',
          ],
          maxResults=123,
          nextToken='string'
      )
    :type agentIds: list
    :param agentIds: 

      The agent IDs for which you want information. If you specify no IDs, the system returns information about all agents associated with your AWS user account.

      

    
      - *(string) --* 

      
  
    :type maxResults: integer
    :param maxResults: 

      The total number of agents to return. The maximum value is 100.

      

    
    :type nextToken: string
    :param nextToken: 

      A token to start the list. Use this token to get the next set of results.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'agentsInfo': [
                {
                    'agentId': 'string',
                    'hostName': 'string',
                    'agentNetworkInfoList': [
                        {
                            'ipAddress': 'string',
                            'macAddress': 'string'
                        },
                    ],
                    'connectorId': 'string',
                    'version': 'string',
                    'health': 'HEALTHY'|'UNHEALTHY'|'RUNNING'|'UNKNOWN'|'BLACKLISTED'|'SHUTDOWN'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **agentsInfo** *(list) --* 

          Lists AWS agents by ID or lists all agents associated with your user account if you did not specify an agent ID. The output includes agent IDs, IP addresses, media access control (MAC) addresses, agent health, host name where the agent resides, and the version number of each agent.

          
          

          - *(dict) --* 

            Information about agents associated with the user’s AWS account. Information includes agent IDs, IP addresses, media access control (MAC) addresses, agent health, hostname where the agent resides, and agent version for each agent.

            
            

            - **agentId** *(string) --* 

              The agent ID.

              
            

            - **hostName** *(string) --* 

              The name of the host where the agent resides. The host can be a server or virtual machine.

              
            

            - **agentNetworkInfoList** *(list) --* 

              Network details about the host where the agent resides.

              
              

              - *(dict) --* 

                Network details about the host where the agent resides.

                
                

                - **ipAddress** *(string) --* 

                  The IP address for the host where the agent resides.

                  
                

                - **macAddress** *(string) --* 

                  The MAC address for the host where the agent resides.

                  
            
          
            

            - **connectorId** *(string) --* 

              This data type is currently not valid.

              
            

            - **version** *(string) --* 

              The agent version.

              
            

            - **health** *(string) --* 

              The health of the agent.

              
        
      
        

        - **nextToken** *(string) --* 

          The call returns a token. Use this token to get the next set of results.

          
    

  .. py:method:: describe_configurations(**kwargs)

    

    Retrieves a list of attributes for a specific configuration ID. For example, the output for a *server* configuration item includes a list of attributes about the server, including host name, operating system, number of network cards, etc.

    

    **Request Syntax** 
    ::

      response = client.describe_configurations(
          configurationIds=[
              'string',
          ]
      )
    :type configurationIds: list
    :param configurationIds: **[REQUIRED]** 

      One or more configuration IDs.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'configurations': [
                {
                    'string': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **configurations** *(list) --* 

          A key in the response map. The value is an array of data.

          
          

          - *(dict) --* 
            

            - *(string) --* 
              

              - *(string) --* 
        
      
      
    

  .. py:method:: describe_export_configurations(**kwargs)

    

    Retrieves the status of a given export process. You can retrieve status from a maximum of 100 processes.

    

    **Request Syntax** 
    ::

      response = client.describe_export_configurations(
          exportIds=[
              'string',
          ],
          maxResults=123,
          nextToken='string'
      )
    :type exportIds: list
    :param exportIds: 

      A unique identifier that you can use to query the export status.

      

    
      - *(string) --* 

      
  
    :type maxResults: integer
    :param maxResults: 

      The maximum number of results that you want to display as a part of the query.

      

    
    :type nextToken: string
    :param nextToken: 

      A token to get the next set of results. For example, if you specified 100 IDs for ``DescribeConfigurationsRequest$configurationIds`` but set ``DescribeExportConfigurationsRequest$maxResults`` to 10, you will get results in a set of 10. Use the token in the query to get the next set of 10.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'exportsInfo': [
                {
                    'exportId': 'string',
                    'exportStatus': 'FAILED'|'SUCCEEDED'|'IN_PROGRESS',
                    'statusMessage': 'string',
                    'configurationsDownloadUrl': 'string',
                    'exportRequestTime': datetime(2015, 1, 1)
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **exportsInfo** *(list) --* 

          Returns export details. When the status is complete, the response includes a URL for an Amazon S3 bucket where you can view the data in a CSV file.

          
          

          - *(dict) --* 

            Information regarding the export status of the discovered data. The value is an array of objects.

            
            

            - **exportId** *(string) --* 

              A unique identifier that you can use to query the export.

              
            

            - **exportStatus** *(string) --* 

              The status of the configuration data export. The status can succeed, fail, or be in-progress.

              
            

            - **statusMessage** *(string) --* 

              Helpful status messages for API callers. For example: Too many exports in the last 6 hours. Export in progress. Export was successful.

              
            

            - **configurationsDownloadUrl** *(string) --* 

              A URL for an Amazon S3 bucket where you can review the configuration data. The URL is displayed only if the export succeeded.

              
            

            - **exportRequestTime** *(datetime) --* 

              The time the configuration data export was initiated.

              
        
      
        

        - **nextToken** *(string) --* 

          A token to get the next set of results. For example, if you specified 100 IDs for ``DescribeConfigurationsRequest$configurationIds`` but set ``DescribeExportConfigurationsRequest$maxResults`` to 10, you will get results in a set of 10. Use the token in the query to get the next set of 10.

          
    

  .. py:method:: describe_tags(**kwargs)

    

    Retrieves a list of configuration items that are tagged with a specific tag. Or retrieves a list of all tags assigned to a specific configuration item.

    

    **Request Syntax** 
    ::

      response = client.describe_tags(
          filters=[
              {
                  'name': 'string',
                  'values': [
                      'string',
                  ]
              },
          ],
          maxResults=123,
          nextToken='string'
      )
    :type filters: list
    :param filters: 

      You can filter the list using a *key* -*value* format. You can separate these items by using logical operators. Allowed filters include ``tagKey`` , ``tagValue`` , and ``configurationId`` . 

      

    
      - *(dict) --* 

        The name of a tag filter. Valid names are: ``tagKey`` , ``tagValue`` , ``configurationId`` .

        

      
        - **name** *(string) --* **[REQUIRED]** 

          A name of a tag filter.

          

        
        - **values** *(list) --* **[REQUIRED]** 

          Values of a tag filter.

          

        
          - *(string) --* 

          
      
      
  
    :type maxResults: integer
    :param maxResults: 

      The total number of items to return. The maximum value is 100.

      

    
    :type nextToken: string
    :param nextToken: 

      A token to start the list. Use this token to get the next set of results.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'tags': [
                {
                    'configurationType': 'SERVER'|'PROCESS'|'CONNECTION',
                    'configurationId': 'string',
                    'key': 'string',
                    'value': 'string',
                    'timeOfCreation': datetime(2015, 1, 1)
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **tags** *(list) --* 

          Depending on the input, this is a list of configuration items tagged with a specific tag, or a list of tags for a specific configuration item.

          
          

          - *(dict) --* 

            Tags for a configuration item. Tags are metadata that help you categorize IT assets.

            
            

            - **configurationType** *(string) --* 

              A type of IT asset that you want to tag.

              
            

            - **configurationId** *(string) --* 

              The configuration ID for the item you want to tag. You can specify a list of keys and values.

              
            

            - **key** *(string) --* 

              A type of tag to filter on. For example, *serverType* .

              
            

            - **value** *(string) --* 

              A value to filter on. For example *key = serverType* and *value = web server* .

              
            

            - **timeOfCreation** *(datetime) --* 

              The time the configuration tag was created in Coordinated Universal Time (UTC).

              
        
      
        

        - **nextToken** *(string) --* 

          The call returns a token. Use this token to get the next set of results.

          
    

  .. py:method:: export_configurations()

    

    Exports all discovered configuration data to an Amazon S3 bucket or an application that enables you to view and evaluate the data. Data includes tags and tag associations, processes, connections, servers, and system performance. This API returns an export ID which you can query using the *GetExportStatus* API. The system imposes a limit of two configuration exports in six hours.

    

    **Request Syntax** 

    ::

      response = client.export_configurations()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'exportId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **exportId** *(string) --* 

          A unique identifier that you can use to query the export status.

          
    

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

        


  .. py:method:: list_configurations(**kwargs)

    

    Retrieves a list of configurations items according to the criteria you specify in a filter. The filter criteria identify relationship requirements.

    

    **Request Syntax** 
    ::

      response = client.list_configurations(
          configurationType='SERVER'|'PROCESS'|'CONNECTION',
          filters=[
              {
                  'name': 'string',
                  'values': [
                      'string',
                  ],
                  'condition': 'string'
              },
          ],
          maxResults=123,
          nextToken='string'
      )
    :type configurationType: string
    :param configurationType: **[REQUIRED]** 

      A valid configuration identified by the Discovery Service. 

      

    
    :type filters: list
    :param filters: 

      You can filter the list using a *key* -*value* format. For example: 

       

       ``{"key": "serverType", "value": "webServer"}``  

       

      You can separate these items by using logical operators. 

      

    
      - *(dict) --* 

        A filter that can use conditional operators.

        

      
        - **name** *(string) --* **[REQUIRED]** 

          The name of the filter. The following filter names are allowed for ``SERVER`` configuration items.

           

           **Server**  

           

           
          * ``server.hostName``   
           
          * ``server.osName``   
           
          * ``server.osVersion``   
           
          * ``server.configurationid``   
           
          * ``server.agentid``   
           

           

          The name of the filter. The following filter names are allowed for ``PROCESS`` configuration items.

           

           **Process**  

           

           
          * ``process.configurationid``   
           
          * ``process.name``   
           
          * ``process.commandLine``   
           
          * ``server.configurationid``   
           
          * ``server.hostName``   
           
          * ``server.osName``   
           
          * ``server.osVersion``   
           
          * ``server.agentId``   
           

           

          The name of the filter. The following filter names are allowed for ``CONNECTION`` configuration items.

           

           **Connection**  

           

           
          * ``connection.sourceIp``   
           
          * ``connection.destinationIp``   
           
          * ``connection.destinationPort``   
           
          * ``sourceProcess.configurationId``   
           
          * ``sourceProcess.name``   
           
          * ``sourceProcess.commandLine``   
           
          * ``destinationProcess.configurationId``   
           
          * ``destinationProcess.name``   
           
          * ``destinationProcess.commandLine``   
           
          * ``sourceServer.configurationId``   
           
          * ``sourceServer.hostName``   
           
          * ``sourceServer.osName``   
           
          * ``sourceServer.osVersion``   
           
          * ``sourceServer.agentId``   
           
          * ``destinationServer.configurationId``   
           
          * ``destinationServer.hostName``   
           
          * ``destinationServer.osName``   
           
          * ``destinationServer.osVersion``   
           
          * ``destinationServer.agentId``   
           

          

        
        - **values** *(list) --* **[REQUIRED]** 

          A string value that you want to filter on. For example, if you choose the ``destinationServer.osVersion`` filter name, you could specify ``Ubuntu`` for the value.

          

        
          - *(string) --* 

          
      
        - **condition** *(string) --* **[REQUIRED]** 

          A conditional operator. The following operators are valid: EQUALS, NOT_EQUALS, CONTAINS, NOT_CONTAINS. If you specify multiple filters, the system utilizes all filters as though concatenated by *AND* . If you specify multiple values for a particular filter, the system differentiates the values using *OR* . Calling either *DescribeConfigurations* or *ListConfigurations* returns attributes of matching configuration items.

          

        
      
  
    :type maxResults: integer
    :param maxResults: 

      The total number of items to return. The maximum value is 100.

      

    
    :type nextToken: string
    :param nextToken: 

      A token to start the list. Use this token to get the next set of results.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'configurations': [
                {
                    'string': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **configurations** *(list) --* 

          Returns configuration details, including the configuration ID, attribute names, and attribute values.

          
          

          - *(dict) --* 
            

            - *(string) --* 
              

              - *(string) --* 
        
      
      
        

        - **nextToken** *(string) --* 

          The call returns a token. Use this token to get the next set of results.

          
    

  .. py:method:: start_data_collection_by_agent_ids(**kwargs)

    

    Instructs the specified agents to start collecting data. Agents can reside on host servers or virtual machines in your data center.

    

    **Request Syntax** 
    ::

      response = client.start_data_collection_by_agent_ids(
          agentIds=[
              'string',
          ]
      )
    :type agentIds: list
    :param agentIds: **[REQUIRED]** 

      The IDs of the agents that you want to start collecting data. If you send a request to an AWS agent ID that you do not have permission to contact, according to your AWS account, the service does not throw an exception. Instead, it returns the error in the *Description* field. If you send a request to multiple agents and you do not have permission to contact some of those agents, the system does not throw an exception. Instead, the system shows ``Failed`` in the *Description* field.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'agentsConfigurationStatus': [
                {
                    'agentId': 'string',
                    'operationSucceeded': True|False,
                    'description': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **agentsConfigurationStatus** *(list) --* 

          Information about agents that were instructed to start collecting data. Information includes the agent ID, a description of the operation performed, and whether or not the agent configuration was updated.

          
          

          - *(dict) --* 

            Information about agents that were instructed to start collecting data. Information includes the agent ID, a description of the operation, and whether or not the agent configuration was updated.

            
            

            - **agentId** *(string) --* 

              The agent ID.

              
            

            - **operationSucceeded** *(boolean) --* 

              Information about the status of the ``StartDataCollection`` and ``StopDataCollection`` operations. The system has recorded the data collection operation. The agent receives this command the next time it polls for a new command. 

              
            

            - **description** *(string) --* 

              A description of the operation performed.

              
        
      
    

  .. py:method:: stop_data_collection_by_agent_ids(**kwargs)

    

    Instructs the specified agents to stop collecting data.

    

    **Request Syntax** 
    ::

      response = client.stop_data_collection_by_agent_ids(
          agentIds=[
              'string',
          ]
      )
    :type agentIds: list
    :param agentIds: **[REQUIRED]** 

      The IDs of the agents that you want to stop collecting data.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'agentsConfigurationStatus': [
                {
                    'agentId': 'string',
                    'operationSucceeded': True|False,
                    'description': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **agentsConfigurationStatus** *(list) --* 

          Information about agents that were instructed to stop collecting data. Information includes the agent ID, a description of the operation performed, and whether or not the agent configuration was updated.

          
          

          - *(dict) --* 

            Information about agents that were instructed to start collecting data. Information includes the agent ID, a description of the operation, and whether or not the agent configuration was updated.

            
            

            - **agentId** *(string) --* 

              The agent ID.

              
            

            - **operationSucceeded** *(boolean) --* 

              Information about the status of the ``StartDataCollection`` and ``StopDataCollection`` operations. The system has recorded the data collection operation. The agent receives this command the next time it polls for a new command. 

              
            

            - **description** *(string) --* 

              A description of the operation performed.

              
        
      
    