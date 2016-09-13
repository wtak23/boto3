

.. _RFC3339: https://www.rfc-editor.org/rfc/rfc3339.txt
.. _JSONPath: http://goessner.net/articles/JsonPath/
.. _The JavaScript Object Notation (JSON) Data Interchange Format: http://www.rfc-editor.org/rfc/rfc7159.txt
.. _Permissions for Sending Events to Targets: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/EventsTargetPermissions.html


****************
CloudWatchEvents
****************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: CloudWatchEvents.Client

  A low-level client representing Amazon CloudWatch Events::

    
    import boto3
    
    client = boto3.client('events')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`delete_rule`

  
  *   :py:meth:`describe_rule`

  
  *   :py:meth:`disable_rule`

  
  *   :py:meth:`enable_rule`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_rule_names_by_target`

  
  *   :py:meth:`list_rules`

  
  *   :py:meth:`list_targets_by_rule`

  
  *   :py:meth:`put_events`

  
  *   :py:meth:`put_rule`

  
  *   :py:meth:`put_targets`

  
  *   :py:meth:`remove_targets`

  
  *   :py:meth:`test_event_pattern`

  

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


  .. py:method:: delete_rule(**kwargs)

    

    Deletes a rule. You must remove all targets from a rule using  RemoveTargets before you can delete the rule.

     

     **Note:** When you delete a rule, incoming events might still continue to match to the deleted rule. Please allow a short period of time for changes to take effect. 

    

    **Request Syntax** 
    ::

      response = client.delete_rule(
          Name='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the rule to be deleted.

      

    
    
    :returns: None

  .. py:method:: describe_rule(**kwargs)

    

    Describes the details of the specified rule.

    

    **Request Syntax** 
    ::

      response = client.describe_rule(
          Name='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the rule you want to describe details for.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Name': 'string',
            'Arn': 'string',
            'EventPattern': 'string',
            'ScheduleExpression': 'string',
            'State': 'ENABLED'|'DISABLED',
            'Description': 'string',
            'RoleArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  DescribeRule operation.

        
        

        - **Name** *(string) --* 

          The rule's name.

          
        

        - **Arn** *(string) --* 

          The Amazon Resource Name (ARN) associated with the rule.

          
        

        - **EventPattern** *(string) --* 

          The event pattern.

          
        

        - **ScheduleExpression** *(string) --* 

          The scheduling expression. For example, "cron(0 20 * * ? *)", "rate(5 minutes)".

          
        

        - **State** *(string) --* 

          Specifies whether the rule is enabled or disabled.

          
        

        - **Description** *(string) --* 

          The rule's description.

          
        

        - **RoleArn** *(string) --* 

          The Amazon Resource Name (ARN) of the IAM role associated with the rule.

          
    

  .. py:method:: disable_rule(**kwargs)

    

    Disables a rule. A disabled rule won't match any events, and won't self-trigger if it has a schedule expression.

     

     **Note:** When you disable a rule, incoming events might still continue to match to the disabled rule. Please allow a short period of time for changes to take effect. 

    

    **Request Syntax** 
    ::

      response = client.disable_rule(
          Name='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the rule you want to disable.

      

    
    
    :returns: None

  .. py:method:: enable_rule(**kwargs)

    

    Enables a rule. If the rule does not exist, the operation fails.

     

     **Note:** When you enable a rule, incoming events might not immediately start matching to a newly enabled rule. Please allow a short period of time for changes to take effect. 

    

    **Request Syntax** 
    ::

      response = client.enable_rule(
          Name='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the rule that you want to enable.

      

    
    
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

        


  .. py:method:: list_rule_names_by_target(**kwargs)

    

    Lists the names of the rules that the given target is put to. You can see which of the rules in Amazon CloudWatch Events can invoke a specific target in your account. If you have more rules in your account than the given limit, the results will be paginated. In that case, use the next token returned in the response and repeat ListRulesByTarget until the NextToken in the response is returned as null.

    

    **Request Syntax** 
    ::

      response = client.list_rule_names_by_target(
          TargetArn='string',
          NextToken='string',
          Limit=123
      )
    :type TargetArn: string
    :param TargetArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the target resource that you want to list the rules for.

      

    
    :type NextToken: string
    :param NextToken: 

      The token returned by a previous call to indicate that there is more data available.

      

    
    :type Limit: integer
    :param Limit: 

      The maximum number of results to return.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RuleNames': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  ListRuleNamesByTarget operation.

        
        

        - **RuleNames** *(list) --* 

          List of rules names that can invoke the given target.

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          Indicates that there are additional results to retrieve.

          
    

  .. py:method:: list_rules(**kwargs)

    

    Lists the Amazon CloudWatch Events rules in your account. You can either list all the rules or you can provide a prefix to match to the rule names. If you have more rules in your account than the given limit, the results will be paginated. In that case, use the next token returned in the response and repeat ListRules until the NextToken in the response is returned as null.

    

    **Request Syntax** 
    ::

      response = client.list_rules(
          NamePrefix='string',
          NextToken='string',
          Limit=123
      )
    :type NamePrefix: string
    :param NamePrefix: 

      The prefix matching the rule name.

      

    
    :type NextToken: string
    :param NextToken: 

      The token returned by a previous call to indicate that there is more data available.

      

    
    :type Limit: integer
    :param Limit: 

      The maximum number of results to return.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Rules': [
                {
                    'Name': 'string',
                    'Arn': 'string',
                    'EventPattern': 'string',
                    'State': 'ENABLED'|'DISABLED',
                    'Description': 'string',
                    'ScheduleExpression': 'string',
                    'RoleArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  ListRules operation.

        
        

        - **Rules** *(list) --* 

          List of rules matching the specified criteria.

          
          

          - *(dict) --* 

            Contains information about a rule in Amazon CloudWatch Events. A ListRulesResult contains a list of Rules.

            
            

            - **Name** *(string) --* 

              The rule's name.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) of the rule.

              
            

            - **EventPattern** *(string) --* 

              The event pattern of the rule.

              
            

            - **State** *(string) --* 

              The rule's state.

              
            

            - **Description** *(string) --* 

              The description of the rule.

              
            

            - **ScheduleExpression** *(string) --* 

              The scheduling expression. For example, "cron(0 20 * * ? *)", "rate(5 minutes)".

              
            

            - **RoleArn** *(string) --* 

              The Amazon Resource Name (ARN) associated with the role that is used for target invocation.

              
        
      
        

        - **NextToken** *(string) --* 

          Indicates that there are additional results to retrieve.

          
    

  .. py:method:: list_targets_by_rule(**kwargs)

    

    Lists of targets assigned to the rule.

    

    **Request Syntax** 
    ::

      response = client.list_targets_by_rule(
          Rule='string',
          NextToken='string',
          Limit=123
      )
    :type Rule: string
    :param Rule: **[REQUIRED]** 

      The name of the rule whose targets you want to list.

      

    
    :type NextToken: string
    :param NextToken: 

      The token returned by a previous call to indicate that there is more data available.

      

    
    :type Limit: integer
    :param Limit: 

      The maximum number of results to return.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Targets': [
                {
                    'Id': 'string',
                    'Arn': 'string',
                    'Input': 'string',
                    'InputPath': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  ListTargetsByRule operation.

        
        

        - **Targets** *(list) --* 

          Lists the targets assigned to the rule.

          
          

          - *(dict) --* 

            Targets are the resources that can be invoked when a rule is triggered. For example, AWS Lambda functions, Amazon Kinesis streams, and built-in targets.

             

            **Input** and **InputPath** are mutually-exclusive and optional parameters of a target. When a rule is triggered due to a matched event, if for a target:

             

             
            * Neither **Input** nor **InputPath** is specified, then the entire event is passed to the target in JSON form.
             
            * **InputPath** is specified in the form of JSONPath (e.g. **$.detail** ), then only the part of the event specified in the path is passed to the target (e.g. only the detail part of the event is passed). 
             
            * **Input** is specified in the form of a valid JSON, then the matched event is overridden with this constant.
             

            
            

            - **Id** *(string) --* 

              The unique target assignment ID.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) associated of the target.

              
            

            - **Input** *(string) --* 

              Valid JSON text passed to the target. For more information about JSON text, see `The JavaScript Object Notation (JSON) Data Interchange Format`_ .

              
            

            - **InputPath** *(string) --* 

              The value of the JSONPath that is used for extracting part of the matched event when passing it to the target. For more information about JSON paths, see `JSONPath`_ .

              
        
      
        

        - **NextToken** *(string) --* 

          Indicates that there are additional results to retrieve.

          
    

  .. py:method:: put_events(**kwargs)

    

    Sends custom events to Amazon CloudWatch Events so that they can be matched to rules.

    

    **Request Syntax** 
    ::

      response = client.put_events(
          Entries=[
              {
                  'Time': datetime(2015, 1, 1),
                  'Source': 'string',
                  'Resources': [
                      'string',
                  ],
                  'DetailType': 'string',
                  'Detail': 'string'
              },
          ]
      )
    :type Entries: list
    :param Entries: **[REQUIRED]** 

      The entry that defines an event in your system. You can specify several parameters for the entry such as the source and type of the event, resources associated with the event, and so on.

      

    
      - *(dict) --* 

        Contains information about the event to be used in PutEvents.

        

      
        - **Time** *(datetime) --* 

          Timestamp of event, per `RFC3339`_ . If no timestamp is provided, the timestamp of the  PutEvents call will be used.

          

        
        - **Source** *(string) --* 

          The source of the event.

          

        
        - **Resources** *(list) --* 

          AWS resources, identified by Amazon Resource Name (ARN), which the event primarily concerns. Any number, including zero, may be present.

          

        
          - *(string) --* 

          
      
        - **DetailType** *(string) --* 

          Free-form string used to decide what fields to expect in the event detail.

          

        
        - **Detail** *(string) --* 

          In the JSON sense, an object containing fields, which may also contain nested sub-objects. No constraints are imposed on its contents.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FailedEntryCount': 123,
            'Entries': [
                {
                    'EventId': 'string',
                    'ErrorCode': 'string',
                    'ErrorMessage': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  PutEvents operation.

        
        

        - **FailedEntryCount** *(integer) --* 

          The number of failed entries.

          
        

        - **Entries** *(list) --* 

          A list of successfully and unsuccessfully ingested events results. If the ingestion was successful, the entry will have the event ID in it. If not, then the ErrorCode and ErrorMessage can be used to identify the problem with the entry.

          
          

          - *(dict) --* 

            A PutEventsResult contains a list of PutEventsResultEntry.

            
            

            - **EventId** *(string) --* 

              The ID of the event submitted to Amazon CloudWatch Events.

              
            

            - **ErrorCode** *(string) --* 

              The error code representing why the event submission failed on this entry.

              
            

            - **ErrorMessage** *(string) --* 

              The error message explaining why the event submission failed on this entry.

              
        
      
    

  .. py:method:: put_rule(**kwargs)

    

    Creates or updates a rule. Rules are enabled by default, or based on value of the State parameter. You can disable a rule using  DisableRule .

     

     **Note:** When you create or update a rule, incoming events might not immediately start matching to new or updated rules. Please allow a short period of time for changes to take effect.

     

    A rule must contain at least an EventPattern or ScheduleExpression. Rules with EventPatterns are triggered when a matching event is observed. Rules with ScheduleExpressions self-trigger based on the given schedule. A rule can have both an EventPattern and a ScheduleExpression, in which case the rule will trigger on matching events as well as on a schedule.

     

     **Note:** Most services in AWS treat : or / as the same character in Amazon Resource Names (ARNs). However, CloudWatch Events uses an exact match in event patterns and rules. Be sure to use the correct ARN characters when creating event patterns so that they match the ARN syntax in the event you want to match. 

    

    **Request Syntax** 
    ::

      response = client.put_rule(
          Name='string',
          ScheduleExpression='string',
          EventPattern='string',
          State='ENABLED'|'DISABLED',
          Description='string',
          RoleArn='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the rule that you are creating or updating.

      

    
    :type ScheduleExpression: string
    :param ScheduleExpression: 

      The scheduling expression. For example, "cron(0 20 * * ? *)", "rate(5 minutes)".

      

    
    :type EventPattern: string
    :param EventPattern: 

      The event pattern.

      

    
    :type State: string
    :param State: 

      Indicates whether the rule is enabled or disabled.

      

    
    :type Description: string
    :param Description: 

      A description of the rule.

      

    
    :type RoleArn: string
    :param RoleArn: 

      The Amazon Resource Name (ARN) of the IAM role associated with the rule.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RuleArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  PutRule operation.

        
        

        - **RuleArn** *(string) --* 

          The Amazon Resource Name (ARN) that identifies the rule.

          
    

  .. py:method:: put_targets(**kwargs)

    

    Adds target(s) to a rule. Targets are the resources that can be invoked when a rule is triggered. For example, AWS Lambda functions, Amazon Kinesis streams, and built-in targets. Updates the target(s) if they are already associated with the role. In other words, if there is already a target with the given target ID, then the target associated with that ID is updated.

     

    In order to be able to make API calls against the resources you own, Amazon CloudWatch Events needs the appropriate permissions. For AWS Lambda and Amazon SNS resources, CloudWatch Events relies on resource-based policies. For Amazon Kinesis streams, CloudWatch Events relies on IAM roles. For more information, see `Permissions for Sending Events to Targets`_ in the ***Amazon CloudWatch Developer Guide*** .

     

    **Input** and **InputPath** are mutually-exclusive and optional parameters of a target. When a rule is triggered due to a matched event, if for a target:

     

     
    * Neither **Input** nor **InputPath** is specified, then the entire event is passed to the target in JSON form.
     
    * **InputPath** is specified in the form of JSONPath (e.g. **$.detail** ), then only the part of the event specified in the path is passed to the target (e.g. only the detail part of the event is passed). 
     
    * **Input** is specified in the form of a valid JSON, then the matched event is overridden with this constant.
     

     

     **Note:** When you add targets to a rule, when the associated rule triggers, new or updated targets might not be immediately invoked. Please allow a short period of time for changes to take effect. 

    

    **Request Syntax** 
    ::

      response = client.put_targets(
          Rule='string',
          Targets=[
              {
                  'Id': 'string',
                  'Arn': 'string',
                  'Input': 'string',
                  'InputPath': 'string'
              },
          ]
      )
    :type Rule: string
    :param Rule: **[REQUIRED]** 

      The name of the rule you want to add targets to.

      

    
    :type Targets: list
    :param Targets: **[REQUIRED]** 

      List of targets you want to update or add to the rule.

      

    
      - *(dict) --* 

        Targets are the resources that can be invoked when a rule is triggered. For example, AWS Lambda functions, Amazon Kinesis streams, and built-in targets.

         

        **Input** and **InputPath** are mutually-exclusive and optional parameters of a target. When a rule is triggered due to a matched event, if for a target:

         

         
        * Neither **Input** nor **InputPath** is specified, then the entire event is passed to the target in JSON form.
         
        * **InputPath** is specified in the form of JSONPath (e.g. **$.detail** ), then only the part of the event specified in the path is passed to the target (e.g. only the detail part of the event is passed). 
         
        * **Input** is specified in the form of a valid JSON, then the matched event is overridden with this constant.
         

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          The unique target assignment ID.

          

        
        - **Arn** *(string) --* **[REQUIRED]** 

          The Amazon Resource Name (ARN) associated of the target.

          

        
        - **Input** *(string) --* 

          Valid JSON text passed to the target. For more information about JSON text, see `The JavaScript Object Notation (JSON) Data Interchange Format`_ .

          

        
        - **InputPath** *(string) --* 

          The value of the JSONPath that is used for extracting part of the matched event when passing it to the target. For more information about JSON paths, see `JSONPath`_ .

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FailedEntryCount': 123,
            'FailedEntries': [
                {
                    'TargetId': 'string',
                    'ErrorCode': 'string',
                    'ErrorMessage': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  PutTargets operation.

        
        

        - **FailedEntryCount** *(integer) --* 

          The number of failed entries.

          
        

        - **FailedEntries** *(list) --* 

          An array of failed target entries.

          
          

          - *(dict) --* 

            A PutTargetsResult contains a list of PutTargetsResultEntry.

            
            

            - **TargetId** *(string) --* 

              The ID of the target submitted to Amazon CloudWatch Events.

              
            

            - **ErrorCode** *(string) --* 

              The error code representing why the target submission failed on this entry.

              
            

            - **ErrorMessage** *(string) --* 

              The error message explaining why the target submission failed on this entry.

              
        
      
    

  .. py:method:: remove_targets(**kwargs)

    

    Removes target(s) from a rule so that when the rule is triggered, those targets will no longer be invoked.

     

     **Note:** When you remove a target, when the associated rule triggers, removed targets might still continue to be invoked. Please allow a short period of time for changes to take effect. 

    

    **Request Syntax** 
    ::

      response = client.remove_targets(
          Rule='string',
          Ids=[
              'string',
          ]
      )
    :type Rule: string
    :param Rule: **[REQUIRED]** 

      The name of the rule you want to remove targets from.

      

    
    :type Ids: list
    :param Ids: **[REQUIRED]** 

      The list of target IDs to remove from the rule.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FailedEntryCount': 123,
            'FailedEntries': [
                {
                    'TargetId': 'string',
                    'ErrorCode': 'string',
                    'ErrorMessage': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  RemoveTargets operation.

        
        

        - **FailedEntryCount** *(integer) --* 

          The number of failed entries.

          
        

        - **FailedEntries** *(list) --* 

          An array of failed target entries.

          
          

          - *(dict) --* 

            The ID of the target requested to be removed from the rule by Amazon CloudWatch Events.

            
            

            - **TargetId** *(string) --* 

              The ID of the target requested to be removed by Amazon CloudWatch Events.

              
            

            - **ErrorCode** *(string) --* 

              The error code representing why the target removal failed on this entry.

              
            

            - **ErrorMessage** *(string) --* 

              The error message explaining why the target removal failed on this entry.

              
        
      
    

  .. py:method:: test_event_pattern(**kwargs)

    

    Tests whether an event pattern matches the provided event.

     

     **Note:** Most services in AWS treat : or / as the same character in Amazon Resource Names (ARNs). However, CloudWatch Events uses an exact match in event patterns and rules. Be sure to use the correct ARN characters when creating event patterns so that they match the ARN syntax in the event you want to match. 

    

    **Request Syntax** 
    ::

      response = client.test_event_pattern(
          EventPattern='string',
          Event='string'
      )
    :type EventPattern: string
    :param EventPattern: **[REQUIRED]** 

      The event pattern you want to test.

      

    
    :type Event: string
    :param Event: **[REQUIRED]** 

      The event in the JSON format to test against the event pattern.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Result': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  TestEventPattern operation.

        
        

        - **Result** *(boolean) --* 

          Indicates whether the event matches the event pattern.

          
    