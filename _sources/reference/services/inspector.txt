

.. _Amazon Inspector Assessment Targets: http://docs.aws.amazon.com/inspector/latest/userguide/inspector_applications.html


*********
Inspector
*********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: Inspector.Client

  A low-level client representing Amazon Inspector::

    
    import boto3
    
    client = boto3.client('inspector')

  
  These are the available methods:
  
  *   :py:meth:`add_attributes_to_findings`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_assessment_target`

  
  *   :py:meth:`create_assessment_template`

  
  *   :py:meth:`create_resource_group`

  
  *   :py:meth:`delete_assessment_run`

  
  *   :py:meth:`delete_assessment_target`

  
  *   :py:meth:`delete_assessment_template`

  
  *   :py:meth:`describe_assessment_runs`

  
  *   :py:meth:`describe_assessment_targets`

  
  *   :py:meth:`describe_assessment_templates`

  
  *   :py:meth:`describe_cross_account_access_role`

  
  *   :py:meth:`describe_findings`

  
  *   :py:meth:`describe_resource_groups`

  
  *   :py:meth:`describe_rules_packages`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_telemetry_metadata`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_assessment_run_agents`

  
  *   :py:meth:`list_assessment_runs`

  
  *   :py:meth:`list_assessment_targets`

  
  *   :py:meth:`list_assessment_templates`

  
  *   :py:meth:`list_event_subscriptions`

  
  *   :py:meth:`list_findings`

  
  *   :py:meth:`list_rules_packages`

  
  *   :py:meth:`list_tags_for_resource`

  
  *   :py:meth:`preview_agents`

  
  *   :py:meth:`register_cross_account_access_role`

  
  *   :py:meth:`remove_attributes_from_findings`

  
  *   :py:meth:`set_tags_for_resource`

  
  *   :py:meth:`start_assessment_run`

  
  *   :py:meth:`stop_assessment_run`

  
  *   :py:meth:`subscribe_to_event`

  
  *   :py:meth:`unsubscribe_from_event`

  
  *   :py:meth:`update_assessment_target`

  

  .. py:method:: add_attributes_to_findings(**kwargs)

    

    Assigns attributes (key and value pairs) to the findings that are specified by the ARNs of the findings.

    

    **Request Syntax** 
    ::

      response = client.add_attributes_to_findings(
          findingArns=[
              'string',
          ],
          attributes=[
              {
                  'key': 'string',
                  'value': 'string'
              },
          ]
      )
    :type findingArns: list
    :param findingArns: **[REQUIRED]** 

      The ARNs that specify the findings that you want to assign attributes to.

      

    
      - *(string) --* 

      
  
    :type attributes: list
    :param attributes: **[REQUIRED]** 

      The array of attributes that you want to assign to specified findings.

      

    
      - *(dict) --* 

        This data type is used as a request parameter in the  AddAttributesToFindings and  CreateAssessmentTemplate actions.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The attribute key.

          

        
        - **value** *(string) --* 

          The value assigned to the attribute key.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'failedItems': {
                'string': {
                    'failureCode': 'INVALID_ARN'|'DUPLICATE_ARN'|'ITEM_DOES_NOT_EXIST'|'ACCESS_DENIED'|'LIMIT_EXCEEDED'|'INTERNAL_ERROR',
                    'retryable': True|False
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **failedItems** *(dict) --* 

          Attribute details that cannot be described. An error code is provided for each failed item.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Includes details about the failed items.

              
              

              - **failureCode** *(string) --* 

                The status code of a failed item.

                
              

              - **retryable** *(boolean) --* 

                Indicates whether you can immediately retry a request for this item for a specified resource.

                
          
      
    
    

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


  .. py:method:: create_assessment_target(**kwargs)

    

    Creates a new assessment target using the ARN of the resource group that is generated by  CreateResourceGroup . You can create up to 50 assessment targets per AWS account. You can run up to 500 concurrent agents per AWS account. For more information, see `Amazon Inspector Assessment Targets`_ .

    

    **Request Syntax** 
    ::

      response = client.create_assessment_target(
          assessmentTargetName='string',
          resourceGroupArn='string'
      )
    :type assessmentTargetName: string
    :param assessmentTargetName: **[REQUIRED]** 

      The user-defined name that identifies the assessment target that you want to create. The name must be unique within the AWS account.

      

    
    :type resourceGroupArn: string
    :param resourceGroupArn: **[REQUIRED]** 

      The ARN that specifies the resource group that is used to create the assessment target.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentTargetArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentTargetArn** *(string) --* 

          The ARN that specifies the assessment target that is created.

          
    

  .. py:method:: create_assessment_template(**kwargs)

    

    Creates an assessment template for the assessment target that is specified by the ARN of the assessment target.

    

    **Request Syntax** 
    ::

      response = client.create_assessment_template(
          assessmentTargetArn='string',
          assessmentTemplateName='string',
          durationInSeconds=123,
          rulesPackageArns=[
              'string',
          ],
          userAttributesForFindings=[
              {
                  'key': 'string',
                  'value': 'string'
              },
          ]
      )
    :type assessmentTargetArn: string
    :param assessmentTargetArn: **[REQUIRED]** 

      The ARN that specifies the assessment target for which you want to create the assessment template.

      

    
    :type assessmentTemplateName: string
    :param assessmentTemplateName: **[REQUIRED]** 

      The user-defined name that identifies the assessment template that you want to create. You can create several assessment templates for an assessment target. The names of the assessment templates that correspond to a particular assessment target must be unique.

      

    
    :type durationInSeconds: integer
    :param durationInSeconds: **[REQUIRED]** 

      The duration of the assessment run in seconds. The default value is 3600 seconds (one hour).

      

    
    :type rulesPackageArns: list
    :param rulesPackageArns: **[REQUIRED]** 

      The ARNs that specify the rules packages that you want to attach to the assessment template.

      

    
      - *(string) --* 

      
  
    :type userAttributesForFindings: list
    :param userAttributesForFindings: 

      The user-defined attributes that are assigned to every finding that is generated by the assessment run that uses this assessment template.

      

    
      - *(dict) --* 

        This data type is used as a request parameter in the  AddAttributesToFindings and  CreateAssessmentTemplate actions.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The attribute key.

          

        
        - **value** *(string) --* 

          The value assigned to the attribute key.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentTemplateArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentTemplateArn** *(string) --* 

          The ARN that specifies the assessment template that is created.

          
    

  .. py:method:: create_resource_group(**kwargs)

    

    Creates a resource group using the specified set of tags (key and value pairs) that are used to select the EC2 instances to be included in an Amazon Inspector assessment target. The created resource group is then used to create an Amazon Inspector assessment target. For more information, see  CreateAssessmentTarget .

    

    **Request Syntax** 
    ::

      response = client.create_resource_group(
          resourceGroupTags=[
              {
                  'key': 'string',
                  'value': 'string'
              },
          ]
      )
    :type resourceGroupTags: list
    :param resourceGroupTags: **[REQUIRED]** 

      A collection of keys and an array of possible values, '[{"key":"key1","values":["Value1","Value2"]},{"key":"Key2","values":["Value3"]}]'.

       

      For example,'[{"key":"Name","values":["TestEC2Instance"]}]'.

      

    
      - *(dict) --* 

        This data type is used as one of the elements of the  ResourceGroup data type.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          A tag key.

          

        
        - **value** *(string) --* 

          The value assigned to a tag key.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'resourceGroupArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **resourceGroupArn** *(string) --* 

          The ARN that specifies the resource group that is created.

          
    

  .. py:method:: delete_assessment_run(**kwargs)

    

    Deletes the assessment run that is specified by the ARN of the assessment run.

    

    **Request Syntax** 
    ::

      response = client.delete_assessment_run(
          assessmentRunArn='string'
      )
    :type assessmentRunArn: string
    :param assessmentRunArn: **[REQUIRED]** 

      The ARN that specifies the assessment run that you want to delete.

      

    
    
    :returns: None

  .. py:method:: delete_assessment_target(**kwargs)

    

    Deletes the assessment target that is specified by the ARN of the assessment target.

    

    **Request Syntax** 
    ::

      response = client.delete_assessment_target(
          assessmentTargetArn='string'
      )
    :type assessmentTargetArn: string
    :param assessmentTargetArn: **[REQUIRED]** 

      The ARN that specifies the assessment target that you want to delete.

      

    
    
    :returns: None

  .. py:method:: delete_assessment_template(**kwargs)

    

    Deletes the assessment template that is specified by the ARN of the assessment template.

    

    **Request Syntax** 
    ::

      response = client.delete_assessment_template(
          assessmentTemplateArn='string'
      )
    :type assessmentTemplateArn: string
    :param assessmentTemplateArn: **[REQUIRED]** 

      The ARN that specifies the assessment template that you want to delete.

      

    
    
    :returns: None

  .. py:method:: describe_assessment_runs(**kwargs)

    

    Describes the assessment runs that are specified by the ARNs of the assessment runs.

    

    **Request Syntax** 
    ::

      response = client.describe_assessment_runs(
          assessmentRunArns=[
              'string',
          ]
      )
    :type assessmentRunArns: list
    :param assessmentRunArns: **[REQUIRED]** 

      The ARN that specifies the assessment run that you want to describe.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentRuns': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'assessmentTemplateArn': 'string',
                    'state': 'CREATED'|'START_DATA_COLLECTION_PENDING'|'START_DATA_COLLECTION_IN_PROGRESS'|'COLLECTING_DATA'|'STOP_DATA_COLLECTION_PENDING'|'DATA_COLLECTED'|'EVALUATING_RULES'|'FAILED'|'COMPLETED'|'COMPLETED_WITH_ERRORS',
                    'durationInSeconds': 123,
                    'rulesPackageArns': [
                        'string',
                    ],
                    'userAttributesForFindings': [
                        {
                            'key': 'string',
                            'value': 'string'
                        },
                    ],
                    'createdAt': datetime(2015, 1, 1),
                    'startedAt': datetime(2015, 1, 1),
                    'completedAt': datetime(2015, 1, 1),
                    'stateChangedAt': datetime(2015, 1, 1),
                    'dataCollected': True|False,
                    'stateChanges': [
                        {
                            'stateChangedAt': datetime(2015, 1, 1),
                            'state': 'CREATED'|'START_DATA_COLLECTION_PENDING'|'START_DATA_COLLECTION_IN_PROGRESS'|'COLLECTING_DATA'|'STOP_DATA_COLLECTION_PENDING'|'DATA_COLLECTED'|'EVALUATING_RULES'|'FAILED'|'COMPLETED'|'COMPLETED_WITH_ERRORS'
                        },
                    ],
                    'notifications': [
                        {
                            'date': datetime(2015, 1, 1),
                            'event': 'ASSESSMENT_RUN_STARTED'|'ASSESSMENT_RUN_COMPLETED'|'ASSESSMENT_RUN_STATE_CHANGED'|'FINDING_REPORTED'|'OTHER',
                            'message': 'string',
                            'error': True|False,
                            'snsTopicArn': 'string',
                            'snsPublishStatusCode': 'SUCCESS'|'TOPIC_DOES_NOT_EXIST'|'ACCESS_DENIED'|'INTERNAL_ERROR'
                        },
                    ]
                },
            ],
            'failedItems': {
                'string': {
                    'failureCode': 'INVALID_ARN'|'DUPLICATE_ARN'|'ITEM_DOES_NOT_EXIST'|'ACCESS_DENIED'|'LIMIT_EXCEEDED'|'INTERNAL_ERROR',
                    'retryable': True|False
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentRuns** *(list) --* 

          Information about the assessment run.

          
          

          - *(dict) --* 

            A snapshot of an Amazon Inspector assessment run that contains the findings of the assessment run .

             

            Used as the response element in the  DescribeAssessmentRuns action.

            
            

            - **arn** *(string) --* 

              The ARN of the assessment run.

              
            

            - **name** *(string) --* 

              The auto-generated name for the assessment run.

              
            

            - **assessmentTemplateArn** *(string) --* 

              The ARN of the assessment template that is associated with the assessment run.

              
            

            - **state** *(string) --* 

              The state of the assessment run.

              
            

            - **durationInSeconds** *(integer) --* 

              The duration of the assessment run.

              
            

            - **rulesPackageArns** *(list) --* 

              The rules packages selected for the assessment run.

              
              

              - *(string) --* 
          
            

            - **userAttributesForFindings** *(list) --* 

              The user-defined attributes that are assigned to every generated finding.

              
              

              - *(dict) --* 

                This data type is used as a request parameter in the  AddAttributesToFindings and  CreateAssessmentTemplate actions.

                
                

                - **key** *(string) --* 

                  The attribute key.

                  
                

                - **value** *(string) --* 

                  The value assigned to the attribute key.

                  
            
          
            

            - **createdAt** *(datetime) --* 

              The time when  StartAssessmentRun was called.

              
            

            - **startedAt** *(datetime) --* 

              The time when  StartAssessmentRun was called.

              
            

            - **completedAt** *(datetime) --* 

              The assessment run completion time that corresponds to the rules packages evaluation completion time or failure.

              
            

            - **stateChangedAt** *(datetime) --* 

              The last time when the assessment run's state changed.

              
            

            - **dataCollected** *(boolean) --* 

              A Boolean value (true or false) that specifies whether the process of collecting data from the agents is completed.

              
            

            - **stateChanges** *(list) --* 

              A list of the assessment run state changes.

              
              

              - *(dict) --* 

                Used as one of the elements of the  AssessmentRun data type.

                
                

                - **stateChangedAt** *(datetime) --* 

                  The last time the assessment run state changed.

                  
                

                - **state** *(string) --* 

                  The assessment run state.

                  
            
          
            

            - **notifications** *(list) --* 

              A list of notifications for the event subscriptions. A notification about a particular generated finding is added to this list only once.

              
              

              - *(dict) --* 

                Used as one of the elements of the  AssessmentRun data type.

                
                

                - **date** *(datetime) --* 

                  The date of the notification.

                  
                

                - **event** *(string) --* 

                  The event for which a notification is sent.

                  
                

                - **message** *(string) --* 
                

                - **error** *(boolean) --* 

                  The Boolean value that specifies whether the notification represents an error.

                  
                

                - **snsTopicArn** *(string) --* 

                  The SNS topic to which the SNS notification is sent.

                  
                

                - **snsPublishStatusCode** *(string) --* 

                  The status code of the SNS notification.

                  
            
          
        
      
        

        - **failedItems** *(dict) --* 

          Assessment run details that cannot be described. An error code is provided for each failed item.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Includes details about the failed items.

              
              

              - **failureCode** *(string) --* 

                The status code of a failed item.

                
              

              - **retryable** *(boolean) --* 

                Indicates whether you can immediately retry a request for this item for a specified resource.

                
          
      
    
    

  .. py:method:: describe_assessment_targets(**kwargs)

    

    Describes the assessment targets that are specified by the ARNs of the assessment targets.

    

    **Request Syntax** 
    ::

      response = client.describe_assessment_targets(
          assessmentTargetArns=[
              'string',
          ]
      )
    :type assessmentTargetArns: list
    :param assessmentTargetArns: **[REQUIRED]** 

      The ARNs that specifies the assessment targets that you want to describe.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentTargets': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'resourceGroupArn': 'string',
                    'createdAt': datetime(2015, 1, 1),
                    'updatedAt': datetime(2015, 1, 1)
                },
            ],
            'failedItems': {
                'string': {
                    'failureCode': 'INVALID_ARN'|'DUPLICATE_ARN'|'ITEM_DOES_NOT_EXIST'|'ACCESS_DENIED'|'LIMIT_EXCEEDED'|'INTERNAL_ERROR',
                    'retryable': True|False
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentTargets** *(list) --* 

          Information about the assessment targets.

          
          

          - *(dict) --* 

            Contains information about an Amazon Inspector application. This data type is used as the response element in the  DescribeAssessmentTargets action.

            
            

            - **arn** *(string) --* 

              The ARN that specifies the Amazon Inspector assessment target.

              
            

            - **name** *(string) --* 

              The name of the Amazon Inspector assessment target.

              
            

            - **resourceGroupArn** *(string) --* 

              The ARN that specifies the resource group that is associated with the assessment target.

              
            

            - **createdAt** *(datetime) --* 

              The time at which the assessment target is created.

              
            

            - **updatedAt** *(datetime) --* 

              The time at which  UpdateAssessmentTarget is called.

              
        
      
        

        - **failedItems** *(dict) --* 

          Assessment target details that cannot be described. An error code is provided for each failed item.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Includes details about the failed items.

              
              

              - **failureCode** *(string) --* 

                The status code of a failed item.

                
              

              - **retryable** *(boolean) --* 

                Indicates whether you can immediately retry a request for this item for a specified resource.

                
          
      
    
    

  .. py:method:: describe_assessment_templates(**kwargs)

    

    Describes the assessment templates that are specified by the ARNs of the assessment templates.

    

    **Request Syntax** 
    ::

      response = client.describe_assessment_templates(
          assessmentTemplateArns=[
              'string',
          ]
      )
    :type assessmentTemplateArns: list
    :param assessmentTemplateArns: **[REQUIRED]** 

      The ARN that specifiesthe assessment templates that you want to describe.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentTemplates': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'assessmentTargetArn': 'string',
                    'durationInSeconds': 123,
                    'rulesPackageArns': [
                        'string',
                    ],
                    'userAttributesForFindings': [
                        {
                            'key': 'string',
                            'value': 'string'
                        },
                    ],
                    'createdAt': datetime(2015, 1, 1)
                },
            ],
            'failedItems': {
                'string': {
                    'failureCode': 'INVALID_ARN'|'DUPLICATE_ARN'|'ITEM_DOES_NOT_EXIST'|'ACCESS_DENIED'|'LIMIT_EXCEEDED'|'INTERNAL_ERROR',
                    'retryable': True|False
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentTemplates** *(list) --* 

          Information about the assessment templates.

          
          

          - *(dict) --* 

            Contains information about an Amazon Inspector assessment template. This data type is used as the response element in the  DescribeAssessmentTemplates action.

            
            

            - **arn** *(string) --* 

              The ARN of the assessment template.

              
            

            - **name** *(string) --* 

              The name of the assessment template.

              
            

            - **assessmentTargetArn** *(string) --* 

              The ARN of the assessment target that corresponds to this assessment template.

              
            

            - **durationInSeconds** *(integer) --* 

              The duration in seconds specified for this assessment tempate. The default value is 3600 seconds (one hour). The maximum value is 86400 seconds (one day).

              
            

            - **rulesPackageArns** *(list) --* 

              The rules packages that are specified for this assessment template.

              
              

              - *(string) --* 
          
            

            - **userAttributesForFindings** *(list) --* 

              The user-defined attributes that are assigned to every generated finding from the assessment run that uses this assessment template.

              
              

              - *(dict) --* 

                This data type is used as a request parameter in the  AddAttributesToFindings and  CreateAssessmentTemplate actions.

                
                

                - **key** *(string) --* 

                  The attribute key.

                  
                

                - **value** *(string) --* 

                  The value assigned to the attribute key.

                  
            
          
            

            - **createdAt** *(datetime) --* 

              The time at which the assessment template is created.

              
        
      
        

        - **failedItems** *(dict) --* 

          Assessment template details that cannot be described. An error code is provided for each failed item.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Includes details about the failed items.

              
              

              - **failureCode** *(string) --* 

                The status code of a failed item.

                
              

              - **retryable** *(boolean) --* 

                Indicates whether you can immediately retry a request for this item for a specified resource.

                
          
      
    
    

  .. py:method:: describe_cross_account_access_role()

    

    Describes the IAM role that enables Amazon Inspector to access your AWS account.

    

    **Request Syntax** 

    ::

      response = client.describe_cross_account_access_role()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'roleArn': 'string',
            'valid': True|False,
            'registeredAt': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **roleArn** *(string) --* 

          The ARN that specifies the IAM role that Amazon Inspector uses to access your AWS account.

          
        

        - **valid** *(boolean) --* 

          A Boolean value that specifies whether the IAM role has the necessary policies attached to enable Amazon Inspector to access your AWS account.

          
        

        - **registeredAt** *(datetime) --* 

          The date when the cross-account access role was registered.

          
    

  .. py:method:: describe_findings(**kwargs)

    

    Describes the findings that are specified by the ARNs of the findings.

    

    **Request Syntax** 
    ::

      response = client.describe_findings(
          findingArns=[
              'string',
          ],
          locale='EN_US'
      )
    :type findingArns: list
    :param findingArns: **[REQUIRED]** 

      The ARN that specifies the finding that you want to describe.

      

    
      - *(string) --* 

      
  
    :type locale: string
    :param locale: 

      The locale into which you want to translate a finding description, recommendation, and the short description that identifies the finding.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'findings': [
                {
                    'arn': 'string',
                    'schemaVersion': 123,
                    'service': 'string',
                    'serviceAttributes': {
                        'schemaVersion': 123,
                        'assessmentRunArn': 'string',
                        'rulesPackageArn': 'string'
                    },
                    'assetType': 'ec2-instance',
                    'assetAttributes': {
                        'schemaVersion': 123,
                        'agentId': 'string',
                        'autoScalingGroup': 'string',
                        'amiId': 'string',
                        'hostname': 'string',
                        'ipv4Addresses': [
                            'string',
                        ]
                    },
                    'id': 'string',
                    'title': 'string',
                    'description': 'string',
                    'recommendation': 'string',
                    'severity': 'Low'|'Medium'|'High'|'Informational'|'Undefined',
                    'numericSeverity': 123.0,
                    'confidence': 123,
                    'indicatorOfCompromise': True|False,
                    'attributes': [
                        {
                            'key': 'string',
                            'value': 'string'
                        },
                    ],
                    'userAttributes': [
                        {
                            'key': 'string',
                            'value': 'string'
                        },
                    ],
                    'createdAt': datetime(2015, 1, 1),
                    'updatedAt': datetime(2015, 1, 1)
                },
            ],
            'failedItems': {
                'string': {
                    'failureCode': 'INVALID_ARN'|'DUPLICATE_ARN'|'ITEM_DOES_NOT_EXIST'|'ACCESS_DENIED'|'LIMIT_EXCEEDED'|'INTERNAL_ERROR',
                    'retryable': True|False
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **findings** *(list) --* 

          Information about the finding.

          
          

          - *(dict) --* 

            Contains information about an Amazon Inspector finding. This data type is used as the response element in the  DescribeFindings action.

            
            

            - **arn** *(string) --* 

              The ARN that specifies the finding.

              
            

            - **schemaVersion** *(integer) --* 

              The schema version of this data type.

              
            

            - **service** *(string) --* 

              The data element is set to "Inspector".

              
            

            - **serviceAttributes** *(dict) --* 

              This data type is used in the  Finding data type.

              
              

              - **schemaVersion** *(integer) --* 

                The schema version of this data type.

                
              

              - **assessmentRunArn** *(string) --* 

                The ARN of the assessment run during which the finding is generated.

                
              

              - **rulesPackageArn** *(string) --* 

                The ARN of the rules package that is used to generate the finding.

                
          
            

            - **assetType** *(string) --* 

              The type of the host from which the finding is generated.

              
            

            - **assetAttributes** *(dict) --* 

              A collection of attributes of the host from which the finding is generated.

              
              

              - **schemaVersion** *(integer) --* 

                The schema version of this data type.

                
              

              - **agentId** *(string) --* 

                The ID of the agent that is installed on the EC2 instance where the finding is generated.

                
              

              - **autoScalingGroup** *(string) --* 

                The Auto Scaling group of the EC2 instance where the finding is generated.

                
              

              - **amiId** *(string) --* 

                The ID of the Amazon Machine Image (AMI) that is installed on the EC2 instance where the finding is generated.

                
              

              - **hostname** *(string) --* 

                The hostname of the EC2 instance where the finding is generated.

                
              

              - **ipv4Addresses** *(list) --* 

                The list of IP v4 addresses of the EC2 instance where the finding is generated.

                
                

                - *(string) --* 
            
          
            

            - **id** *(string) --* 

              The ID of the finding.

              
            

            - **title** *(string) --* 

              The name of the finding.

              
            

            - **description** *(string) --* 

              The description of the finding.

              
            

            - **recommendation** *(string) --* 

              The recommendation for the finding.

              
            

            - **severity** *(string) --* 

              The finding severity. Values can be set to High, Medium, Low, and Informational.

              
            

            - **numericSeverity** *(float) --* 

              The numeric value of the finding severity.

              
            

            - **confidence** *(integer) --* 

              This data element is currently not used.

              
            

            - **indicatorOfCompromise** *(boolean) --* 

              This data element is currently not used.

              
            

            - **attributes** *(list) --* 

              The system-defined attributes for the finding.

              
              

              - *(dict) --* 

                This data type is used as a request parameter in the  AddAttributesToFindings and  CreateAssessmentTemplate actions.

                
                

                - **key** *(string) --* 

                  The attribute key.

                  
                

                - **value** *(string) --* 

                  The value assigned to the attribute key.

                  
            
          
            

            - **userAttributes** *(list) --* 

              The user-defined attributes that are assigned to the finding.

              
              

              - *(dict) --* 

                This data type is used as a request parameter in the  AddAttributesToFindings and  CreateAssessmentTemplate actions.

                
                

                - **key** *(string) --* 

                  The attribute key.

                  
                

                - **value** *(string) --* 

                  The value assigned to the attribute key.

                  
            
          
            

            - **createdAt** *(datetime) --* 

              The time when the finding was generated.

              
            

            - **updatedAt** *(datetime) --* 

              The time when  AddAttributesToFindings is called.

              
        
      
        

        - **failedItems** *(dict) --* 

          Finding details that cannot be described. An error code is provided for each failed item.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Includes details about the failed items.

              
              

              - **failureCode** *(string) --* 

                The status code of a failed item.

                
              

              - **retryable** *(boolean) --* 

                Indicates whether you can immediately retry a request for this item for a specified resource.

                
          
      
    
    

  .. py:method:: describe_resource_groups(**kwargs)

    

    Describes the resource groups that are specified by the ARNs of the resource groups.

    

    **Request Syntax** 
    ::

      response = client.describe_resource_groups(
          resourceGroupArns=[
              'string',
          ]
      )
    :type resourceGroupArns: list
    :param resourceGroupArns: **[REQUIRED]** 

      The ARN that specifies the resource group that you want to describe.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'resourceGroups': [
                {
                    'arn': 'string',
                    'tags': [
                        {
                            'key': 'string',
                            'value': 'string'
                        },
                    ],
                    'createdAt': datetime(2015, 1, 1)
                },
            ],
            'failedItems': {
                'string': {
                    'failureCode': 'INVALID_ARN'|'DUPLICATE_ARN'|'ITEM_DOES_NOT_EXIST'|'ACCESS_DENIED'|'LIMIT_EXCEEDED'|'INTERNAL_ERROR',
                    'retryable': True|False
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **resourceGroups** *(list) --* 

          Information about a resource group.

          
          

          - *(dict) --* 

            Contains information about a resource group. The resource group defines a set of tags that, when queried, identify the AWS resources that make up the assessment target. This data type is used as the response element in the  DescribeResourceGroups action.

            
            

            - **arn** *(string) --* 

              The ARN of the resource group.

              
            

            - **tags** *(list) --* 

              The tags (key and value pairs) of the resource group. This data type property is used in the  CreateResourceGroup action.

              
              

              - *(dict) --* 

                This data type is used as one of the elements of the  ResourceGroup data type.

                
                

                - **key** *(string) --* 

                  A tag key.

                  
                

                - **value** *(string) --* 

                  The value assigned to a tag key.

                  
            
          
            

            - **createdAt** *(datetime) --* 

              The time at which resource group is created.

              
        
      
        

        - **failedItems** *(dict) --* 

          Resource group details that cannot be described. An error code is provided for each failed item.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Includes details about the failed items.

              
              

              - **failureCode** *(string) --* 

                The status code of a failed item.

                
              

              - **retryable** *(boolean) --* 

                Indicates whether you can immediately retry a request for this item for a specified resource.

                
          
      
    
    

  .. py:method:: describe_rules_packages(**kwargs)

    

    Describes the rules packages that are specified by the ARNs of the rules packages.

    

    **Request Syntax** 
    ::

      response = client.describe_rules_packages(
          rulesPackageArns=[
              'string',
          ],
          locale='EN_US'
      )
    :type rulesPackageArns: list
    :param rulesPackageArns: **[REQUIRED]** 

      The ARN that specifies the rules package that you want to describe.

      

    
      - *(string) --* 

      
  
    :type locale: string
    :param locale: 

      The locale that you want to translate a rules package description into.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'rulesPackages': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'version': 'string',
                    'provider': 'string',
                    'description': 'string'
                },
            ],
            'failedItems': {
                'string': {
                    'failureCode': 'INVALID_ARN'|'DUPLICATE_ARN'|'ITEM_DOES_NOT_EXIST'|'ACCESS_DENIED'|'LIMIT_EXCEEDED'|'INTERNAL_ERROR',
                    'retryable': True|False
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **rulesPackages** *(list) --* 

          Information about the rules package.

          
          

          - *(dict) --* 

            Contains information about an Amazon Inspector rules package. This data type is used as the response element in the  DescribeRulesPackages action.

            
            

            - **arn** *(string) --* 

              The ARN of the rules package.

              
            

            - **name** *(string) --* 

              The name of the rules package.

              
            

            - **version** *(string) --* 

              The version ID of the rules package.

              
            

            - **provider** *(string) --* 

              The provider of the rules package.

              
            

            - **description** *(string) --* 

              The description of the rules package.

              
        
      
        

        - **failedItems** *(dict) --* 

          Rules package details that cannot be described. An error code is provided for each failed item.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Includes details about the failed items.

              
              

              - **failureCode** *(string) --* 

                The status code of a failed item.

                
              

              - **retryable** *(boolean) --* 

                Indicates whether you can immediately retry a request for this item for a specified resource.

                
          
      
    
    

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


  .. py:method:: get_telemetry_metadata(**kwargs)

    

    Information about the data that is collected for the specified assessment run.

    

    **Request Syntax** 
    ::

      response = client.get_telemetry_metadata(
          assessmentRunArn='string'
      )
    :type assessmentRunArn: string
    :param assessmentRunArn: **[REQUIRED]** 

      The ARN that specifies the assessment run that has the telemetry data that you want to obtain.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'telemetryMetadata': [
                {
                    'messageType': 'string',
                    'count': 123,
                    'dataSize': 123
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **telemetryMetadata** *(list) --* 

          Telemetry details.

          
          

          - *(dict) --* 

            The metadata about the Amazon Inspector application data metrics collected by the agent. This data type is used as the response element in the  GetTelemetryMetadata action.

            
            

            - **messageType** *(string) --* 

              A specific type of behavioral data that is collected by the agent.

              
            

            - **count** *(integer) --* 

              The count of messages that the agent sends to the Amazon Inspector service.

              
            

            - **dataSize** *(integer) --* 

              The data size of messages that the agent sends to the Amazon Inspector service.

              
        
      
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: list_assessment_run_agents(**kwargs)

    

    Lists the agents of the assessment runs that are specified by the ARNs of the assessment runs.

    

    **Request Syntax** 
    ::

      response = client.list_assessment_run_agents(
          assessmentRunArn='string',
          filter={
              'agentHealths': [
                  'HEALTHY'|'UNHEALTHY',
              ],
              'agentHealthCodes': [
                  'IDLE'|'RUNNING'|'SHUTDOWN'|'UNHEALTHY'|'THROTTLED'|'UNKNOWN',
              ]
          },
          nextToken='string',
          maxResults=123
      )
    :type assessmentRunArn: string
    :param assessmentRunArn: **[REQUIRED]** 

      The ARN that specifies the assessment run whose agents you want to list.

      

    
    :type filter: dict
    :param filter: 

      You can use this parameter to specify a subset of data to be included in the action's response.

       

      For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

      

    
      - **agentHealths** *(list) --* **[REQUIRED]** 

        The current health state of the agent. Values can be set to **HEALTHY** or **UNHEALTHY** .

        

      
        - *(string) --* 

        
    
      - **agentHealthCodes** *(list) --* **[REQUIRED]** 

        The detailed health state of the agent. Values can be set to **IDLE** , **RUNNING** , **SHUTDOWN** , **UNHEALTHY** , **THROTTLED** , and **UNKNOWN** . 

        

      
        - *(string) --* 

        
    
    
    :type nextToken: string
    :param nextToken: 

      You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **ListAssessmentRunAgents** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

      

    
    :type maxResults: integer
    :param maxResults: 

      You can use this parameter to indicate the maximum number of items that you want in the response. The default value is 10. The maximum value is 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentRunAgents': [
                {
                    'agentId': 'string',
                    'assessmentRunArn': 'string',
                    'agentHealth': 'HEALTHY'|'UNHEALTHY',
                    'agentHealthCode': 'IDLE'|'RUNNING'|'SHUTDOWN'|'UNHEALTHY'|'THROTTLED'|'UNKNOWN',
                    'agentHealthDetails': 'string',
                    'autoScalingGroup': 'string',
                    'telemetryMetadata': [
                        {
                            'messageType': 'string',
                            'count': 123,
                            'dataSize': 123
                        },
                    ]
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentRunAgents** *(list) --* 

          A list of ARNs that specifies the agents returned by the action.

          
          

          - *(dict) --* 

            Contains information about an Amazon Inspector agent. This data type is used as a response element in the  ListAssessmentRunAgents action.

            
            

            - **agentId** *(string) --* 

              The AWS account of the EC2 instance where the agent is installed.

              
            

            - **assessmentRunArn** *(string) --* 

              The ARN of the assessment run that is associated with the agent.

              
            

            - **agentHealth** *(string) --* 

              The current health state of the agent.

              
            

            - **agentHealthCode** *(string) --* 

              The detailed health state of the agent.

              
            

            - **agentHealthDetails** *(string) --* 

              The description for the agent health code.

              
            

            - **autoScalingGroup** *(string) --* 

              The Auto Scaling group of the EC2 instance that is specified by the agent ID.

              
            

            - **telemetryMetadata** *(list) --* 

              The Amazon Inspector application data metrics that are collected by the agent.

              
              

              - *(dict) --* 

                The metadata about the Amazon Inspector application data metrics collected by the agent. This data type is used as the response element in the  GetTelemetryMetadata action.

                
                

                - **messageType** *(string) --* 

                  A specific type of behavioral data that is collected by the agent.

                  
                

                - **count** *(integer) --* 

                  The count of messages that the agent sends to the Amazon Inspector service.

                  
                

                - **dataSize** *(integer) --* 

                  The data size of messages that the agent sends to the Amazon Inspector service.

                  
            
          
        
      
        

        - **nextToken** *(string) --* 

          When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

          
    

  .. py:method:: list_assessment_runs(**kwargs)

    

    Lists the assessment runs that correspond to the assessment templates that are specified by the ARNs of the assessment templates.

    

    **Request Syntax** 
    ::

      response = client.list_assessment_runs(
          assessmentTemplateArns=[
              'string',
          ],
          filter={
              'namePattern': 'string',
              'states': [
                  'CREATED'|'START_DATA_COLLECTION_PENDING'|'START_DATA_COLLECTION_IN_PROGRESS'|'COLLECTING_DATA'|'STOP_DATA_COLLECTION_PENDING'|'DATA_COLLECTED'|'EVALUATING_RULES'|'FAILED'|'COMPLETED'|'COMPLETED_WITH_ERRORS',
              ],
              'durationRange': {
                  'minSeconds': 123,
                  'maxSeconds': 123
              },
              'rulesPackageArns': [
                  'string',
              ],
              'startTimeRange': {
                  'beginDate': datetime(2015, 1, 1),
                  'endDate': datetime(2015, 1, 1)
              },
              'completionTimeRange': {
                  'beginDate': datetime(2015, 1, 1),
                  'endDate': datetime(2015, 1, 1)
              },
              'stateChangeTimeRange': {
                  'beginDate': datetime(2015, 1, 1),
                  'endDate': datetime(2015, 1, 1)
              }
          },
          nextToken='string',
          maxResults=123
      )
    :type assessmentTemplateArns: list
    :param assessmentTemplateArns: 

      The ARNs that specify the assessment templates whose assessment runs you want to list.

      

    
      - *(string) --* 

      
  
    :type filter: dict
    :param filter: 

      You can use this parameter to specify a subset of data to be included in the action's response.

       

      For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

      

    
      - **namePattern** *(string) --* 

        For a record to match a filter, an explicit value or a string containing a wildcard that is specified for this data type property must match the value of the **assessmentRunName** property of the  AssessmentRun data type.

        

      
      - **states** *(list) --* 

        For a record to match a filter, one of the values specified for this data type property must be the exact match of the value of the **assessmentRunState** property of the  AssessmentRun data type.

        

      
        - *(string) --* 

        
    
      - **durationRange** *(dict) --* 

        For a record to match a filter, the value that is specified for this data type property must inclusively match any value between the specified minimum and maximum values of the **durationInSeconds** property of the  AssessmentRun data type.

        

      
        - **minSeconds** *(integer) --* 

          The minimum value of the duration range. Must be greater than zero.

          

        
        - **maxSeconds** *(integer) --* 

          The maximum value of the duration range. Must be less than or equal to 604800 seconds (1 week).

          

        
      
      - **rulesPackageArns** *(list) --* 

        For a record to match a filter, the value that is specified for this data type property must be contained in the list of values of the **rulesPackages** property of the  AssessmentRun data type.

        

      
        - *(string) --* 

        
    
      - **startTimeRange** *(dict) --* 

        For a record to match a filter, the value that is specified for this data type property must inclusively match any value between the specified minimum and maximum values of the **startTime** property of the  AssessmentRun data type.

        

      
        - **beginDate** *(datetime) --* 

          The minimum value of the timestamp range.

          

        
        - **endDate** *(datetime) --* 

          The maximum value of the timestamp range.

          

        
      
      - **completionTimeRange** *(dict) --* 

        For a record to match a filter, the value that is specified for this data type property must inclusively match any value between the specified minimum and maximum values of the **completedAt** property of the  AssessmentRun data type.

        

      
        - **beginDate** *(datetime) --* 

          The minimum value of the timestamp range.

          

        
        - **endDate** *(datetime) --* 

          The maximum value of the timestamp range.

          

        
      
      - **stateChangeTimeRange** *(dict) --* 

        For a record to match a filter, the value that is specified for this data type property must match the **stateChangedAt** property of the  AssessmentRun data type.

        

      
        - **beginDate** *(datetime) --* 

          The minimum value of the timestamp range.

          

        
        - **endDate** *(datetime) --* 

          The maximum value of the timestamp range.

          

        
      
    
    :type nextToken: string
    :param nextToken: 

      You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **ListAssessmentRuns** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

      

    
    :type maxResults: integer
    :param maxResults: 

      You can use this parameter to indicate the maximum number of items that you want in the response. The default value is 10. The maximum value is 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentRunArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentRunArns** *(list) --* 

          A list of ARNs that specifies the assessment runs that are returned by the action.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

          
    

  .. py:method:: list_assessment_targets(**kwargs)

    

    Lists the ARNs of the assessment targets within this AWS account. For more information about assessment targets, see `Amazon Inspector Assessment Targets`_ .

    

    **Request Syntax** 
    ::

      response = client.list_assessment_targets(
          filter={
              'assessmentTargetNamePattern': 'string'
          },
          nextToken='string',
          maxResults=123
      )
    :type filter: dict
    :param filter: 

      You can use this parameter to specify a subset of data to be included in the action's response.

       

      For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

      

    
      - **assessmentTargetNamePattern** *(string) --* 

        For a record to match a filter, an explicit value or a string that contains a wildcard that is specified for this data type property must match the value of the **assessmentTargetName** property of the  AssessmentTarget data type.

        

      
    
    :type nextToken: string
    :param nextToken: 

      You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **ListAssessmentTargets** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

      

    
    :type maxResults: integer
    :param maxResults: 

      You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentTargetArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentTargetArns** *(list) --* 

          A list of ARNs that specifies the assessment targets that are returned by the action.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

          
    

  .. py:method:: list_assessment_templates(**kwargs)

    

    Lists the assessment templates that correspond to the assessment targets that are specified by the ARNs of the assessment targets.

    

    **Request Syntax** 
    ::

      response = client.list_assessment_templates(
          assessmentTargetArns=[
              'string',
          ],
          filter={
              'namePattern': 'string',
              'durationRange': {
                  'minSeconds': 123,
                  'maxSeconds': 123
              },
              'rulesPackageArns': [
                  'string',
              ]
          },
          nextToken='string',
          maxResults=123
      )
    :type assessmentTargetArns: list
    :param assessmentTargetArns: 

      A list of ARNs that specifies the assessment targets whose assessment templates you want to list.

      

    
      - *(string) --* 

      
  
    :type filter: dict
    :param filter: 

      You can use this parameter to specify a subset of data to be included in the action's response.

       

      For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

      

    
      - **namePattern** *(string) --* 

        For a record to match a filter, an explicit value or a string that contains a wildcard that is specified for this data type property must match the value of the **assessmentTemplateName** property of the  AssessmentTemplate data type.

        

      
      - **durationRange** *(dict) --* 

        For a record to match a filter, the value specified for this data type property must inclusively match any value between the specified minimum and maximum values of the **durationInSeconds** property of the  AssessmentTemplate data type.

        

      
        - **minSeconds** *(integer) --* 

          The minimum value of the duration range. Must be greater than zero.

          

        
        - **maxSeconds** *(integer) --* 

          The maximum value of the duration range. Must be less than or equal to 604800 seconds (1 week).

          

        
      
      - **rulesPackageArns** *(list) --* 

        For a record to match a filter, the values that are specified for this data type property must be contained in the list of values of the **rulesPackageArns** property of the  AssessmentTemplate data type.

        

      
        - *(string) --* 

        
    
    
    :type nextToken: string
    :param nextToken: 

      You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **ListAssessmentTemplates** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

      

    
    :type maxResults: integer
    :param maxResults: 

      You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentTemplateArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentTemplateArns** *(list) --* 

          A list of ARNs that specifies the assessment templates returned by the action.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

          
    

  .. py:method:: list_event_subscriptions(**kwargs)

    

    Lists all the event subscriptions for the assessment template that is specified by the ARN of the assessment template. For more information, see  SubscribeToEvent and  UnsubscribeFromEvent .

    

    **Request Syntax** 
    ::

      response = client.list_event_subscriptions(
          resourceArn='string',
          nextToken='string',
          maxResults=123
      )
    :type resourceArn: string
    :param resourceArn: 

      The ARN of the assessment template for which you want to list the existing event subscriptions.

      

    
    :type nextToken: string
    :param nextToken: 

      You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **ListEventSubscriptions** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

      

    
    :type maxResults: integer
    :param maxResults: 

      You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'subscriptions': [
                {
                    'resourceArn': 'string',
                    'topicArn': 'string',
                    'eventSubscriptions': [
                        {
                            'event': 'ASSESSMENT_RUN_STARTED'|'ASSESSMENT_RUN_COMPLETED'|'ASSESSMENT_RUN_STATE_CHANGED'|'FINDING_REPORTED'|'OTHER',
                            'subscribedAt': datetime(2015, 1, 1)
                        },
                    ]
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **subscriptions** *(list) --* 

          Details of the returned event subscriptions.

          
          

          - *(dict) --* 

            This data type is used as a response element in the  ListEventSubscriptions action.

            
            

            - **resourceArn** *(string) --* 

              The ARN of the assessment template that is used during the event for which the SNS notification is sent.

              
            

            - **topicArn** *(string) --* 

              The ARN of the Amazon Simple Notification Service (SNS) topic to which the SNS notifications are sent.

              
            

            - **eventSubscriptions** *(list) --* 

              The list of existing event subscriptions.

              
              

              - *(dict) --* 

                This data type is used in the  Subscription data type.

                
                

                - **event** *(string) --* 

                  The event for which Amazon Simple Notification Service (SNS) notifications are sent.

                  
                

                - **subscribedAt** *(datetime) --* 

                  The time at which  SubscribeToEvent is called.

                  
            
          
        
      
        

        - **nextToken** *(string) --* 

          When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

          
    

  .. py:method:: list_findings(**kwargs)

    

    Lists findings that are generated by the assessment runs that are specified by the ARNs of the assessment runs.

    

    **Request Syntax** 
    ::

      response = client.list_findings(
          assessmentRunArns=[
              'string',
          ],
          filter={
              'agentIds': [
                  'string',
              ],
              'autoScalingGroups': [
                  'string',
              ],
              'ruleNames': [
                  'string',
              ],
              'severities': [
                  'Low'|'Medium'|'High'|'Informational'|'Undefined',
              ],
              'rulesPackageArns': [
                  'string',
              ],
              'attributes': [
                  {
                      'key': 'string',
                      'value': 'string'
                  },
              ],
              'userAttributes': [
                  {
                      'key': 'string',
                      'value': 'string'
                  },
              ],
              'creationTimeRange': {
                  'beginDate': datetime(2015, 1, 1),
                  'endDate': datetime(2015, 1, 1)
              }
          },
          nextToken='string',
          maxResults=123
      )
    :type assessmentRunArns: list
    :param assessmentRunArns: 

      The ARNs of the assessment runs that generate the findings that you want to list.

      

    
      - *(string) --* 

      
  
    :type filter: dict
    :param filter: 

      You can use this parameter to specify a subset of data to be included in the action's response.

       

      For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

      

    
      - **agentIds** *(list) --* 

        For a record to match a filter, one of the values that is specified for this data type property must be the exact match of the value of the **agentId** property of the  Finding data type.

        

      
        - *(string) --* 

        
    
      - **autoScalingGroups** *(list) --* 

        For a record to match a filter, one of the values that is specified for this data type property must be the exact match of the value of the **autoScalingGroup** property of the  Finding data type.

        

      
        - *(string) --* 

        
    
      - **ruleNames** *(list) --* 

        For a record to match a filter, one of the values that is specified for this data type property must be the exact match of the value of the **ruleName** property of the  Finding data type.

        

      
        - *(string) --* 

        
    
      - **severities** *(list) --* 

        For a record to match a filter, one of the values that is specified for this data type property must be the exact match of the value of the **severity** property of the  Finding data type.

        

      
        - *(string) --* 

        
    
      - **rulesPackageArns** *(list) --* 

        For a record to match a filter, one of the values that is specified for this data type property must be the exact match of the value of the **rulesPackageArn** property of the  Finding data type.

        

      
        - *(string) --* 

        
    
      - **attributes** *(list) --* 

        For a record to match a filter, the list of values that are specified for this data type property must be contained in the list of values of the **attributes** property of the  Finding data type.

        

      
        - *(dict) --* 

          This data type is used as a request parameter in the  AddAttributesToFindings and  CreateAssessmentTemplate actions.

          

        
          - **key** *(string) --* **[REQUIRED]** 

            The attribute key.

            

          
          - **value** *(string) --* 

            The value assigned to the attribute key.

            

          
        
    
      - **userAttributes** *(list) --* 

        For a record to match a filter, the value that is specified for this data type property must be contained in the list of values of the **userAttributes** property of the  Finding data type.

        

      
        - *(dict) --* 

          This data type is used as a request parameter in the  AddAttributesToFindings and  CreateAssessmentTemplate actions.

          

        
          - **key** *(string) --* **[REQUIRED]** 

            The attribute key.

            

          
          - **value** *(string) --* 

            The value assigned to the attribute key.

            

          
        
    
      - **creationTimeRange** *(dict) --* 

        The time range during which the finding is generated.

        

      
        - **beginDate** *(datetime) --* 

          The minimum value of the timestamp range.

          

        
        - **endDate** *(datetime) --* 

          The maximum value of the timestamp range.

          

        
      
    
    :type nextToken: string
    :param nextToken: 

      You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **ListFindings** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

      

    
    :type maxResults: integer
    :param maxResults: 

      You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'findingArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **findingArns** *(list) --* 

          A list of ARNs that specifies the findings returned by the action.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

          
    

  .. py:method:: list_rules_packages(**kwargs)

    

    Lists all available Amazon Inspector rules packages.

    

    **Request Syntax** 
    ::

      response = client.list_rules_packages(
          nextToken='string',
          maxResults=123
      )
    :type nextToken: string
    :param nextToken: 

      You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **ListRulesPackages** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

      

    
    :type maxResults: integer
    :param maxResults: 

      You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'rulesPackageArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **rulesPackageArns** *(list) --* 

          The list of ARNs that specifies the rules packages returned by the action.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

          
    

  .. py:method:: list_tags_for_resource(**kwargs)

    

    Lists all tags associated with an assessment template.

    

    **Request Syntax** 
    ::

      response = client.list_tags_for_resource(
          resourceArn='string'
      )
    :type resourceArn: string
    :param resourceArn: **[REQUIRED]** 

      The ARN that specifies the assessment template whose tags you want to list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'tags': [
                {
                    'key': 'string',
                    'value': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **tags** *(list) --* 

          A collection of key and value pairs.

          
          

          - *(dict) --* 

            A key and value pair. This data type is used as a request parameter in the  SetTagsForResource action and a response element in the  ListTagsForResource action.

            
            

            - **key** *(string) --* 

              A tag key.

              
            

            - **value** *(string) --* 

              A value assigned to a tag key.

              
        
      
    

  .. py:method:: preview_agents(**kwargs)

    

    Previews the agents installed on the EC2 instances that are part of the specified assessment target.

    

    **Request Syntax** 
    ::

      response = client.preview_agents(
          previewAgentsArn='string',
          nextToken='string',
          maxResults=123
      )
    :type previewAgentsArn: string
    :param previewAgentsArn: **[REQUIRED]** 

      The ARN of the assessment target whose agents you want to preview.

      

    
    :type nextToken: string
    :param nextToken: 

      You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **PreviewAgents** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

      

    
    :type maxResults: integer
    :param maxResults: 

      You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'agentPreviews': [
                {
                    'agentId': 'string',
                    'autoScalingGroup': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **agentPreviews** *(list) --* 

          The resulting list of agents.

          
          

          - *(dict) --* 

            Used as a response element in the  PreviewAgents action.

            
            

            - **agentId** *(string) --* 

              The ID of the EC2 instance where the agent is installed.

              
            

            - **autoScalingGroup** *(string) --* 

              The Auto Scaling group for the EC2 instance where the agent is installed.

              
        
      
        

        - **nextToken** *(string) --* 

          When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

          
    

  .. py:method:: register_cross_account_access_role(**kwargs)

    

    Registers the IAM role that Amazon Inspector uses to list your EC2 instances at the start of the assessment run or when you call the  PreviewAgents action.

    

    **Request Syntax** 
    ::

      response = client.register_cross_account_access_role(
          roleArn='string'
      )
    :type roleArn: string
    :param roleArn: **[REQUIRED]** 

      The ARN of the IAM role that Amazon Inspector uses to list your EC2 instances during the assessment run or when you call the  PreviewAgents action. 

      

    
    
    :returns: None

  .. py:method:: remove_attributes_from_findings(**kwargs)

    

    Removes entire attributes (key and value pairs) from the findings that are specified by the ARNs of the findings where an attribute with the specified key exists.

    

    **Request Syntax** 
    ::

      response = client.remove_attributes_from_findings(
          findingArns=[
              'string',
          ],
          attributeKeys=[
              'string',
          ]
      )
    :type findingArns: list
    :param findingArns: **[REQUIRED]** 

      The ARNs that specify the findings that you want to remove attributes from.

      

    
      - *(string) --* 

      
  
    :type attributeKeys: list
    :param attributeKeys: **[REQUIRED]** 

      The array of attribute keys that you want to remove from specified findings.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'failedItems': {
                'string': {
                    'failureCode': 'INVALID_ARN'|'DUPLICATE_ARN'|'ITEM_DOES_NOT_EXIST'|'ACCESS_DENIED'|'LIMIT_EXCEEDED'|'INTERNAL_ERROR',
                    'retryable': True|False
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **failedItems** *(dict) --* 

          Attributes details that cannot be described. An error code is provided for each failed item.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Includes details about the failed items.

              
              

              - **failureCode** *(string) --* 

                The status code of a failed item.

                
              

              - **retryable** *(boolean) --* 

                Indicates whether you can immediately retry a request for this item for a specified resource.

                
          
      
    
    

  .. py:method:: set_tags_for_resource(**kwargs)

    

    Sets tags (key and value pairs) to the assessment template that is specified by the ARN of the assessment template.

    

    **Request Syntax** 
    ::

      response = client.set_tags_for_resource(
          resourceArn='string',
          tags=[
              {
                  'key': 'string',
                  'value': 'string'
              },
          ]
      )
    :type resourceArn: string
    :param resourceArn: **[REQUIRED]** 

      The ARN of the assessment template that you want to set tags to.

      

    
    :type tags: list
    :param tags: 

      A collection of key and value pairs that you want to set to the assessment template.

      

    
      - *(dict) --* 

        A key and value pair. This data type is used as a request parameter in the  SetTagsForResource action and a response element in the  ListTagsForResource action.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          A tag key.

          

        
        - **value** *(string) --* 

          A value assigned to a tag key.

          

        
      
  
    
    :returns: None

  .. py:method:: start_assessment_run(**kwargs)

    

    Starts the assessment run specified by the ARN of the assessment template. For this API to function properly, you must not exceed the limit of running up to 500 concurrent agents per AWS account.

    

    **Request Syntax** 
    ::

      response = client.start_assessment_run(
          assessmentTemplateArn='string',
          assessmentRunName='string'
      )
    :type assessmentTemplateArn: string
    :param assessmentTemplateArn: **[REQUIRED]** 

      The ARN of the assessment template of the assessment run that you want to start.

      

    
    :type assessmentRunName: string
    :param assessmentRunName: 

      You can specify the name for the assessment run, or you can use the auto-generated name that is based on the assessment template name. The name must be unique for the assessment template.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'assessmentRunArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **assessmentRunArn** *(string) --* 

          The ARN of the assessment run that has been started.

          
    

  .. py:method:: stop_assessment_run(**kwargs)

    

    Stops the assessment run that is specified by the ARN of the assessment run.

    

    **Request Syntax** 
    ::

      response = client.stop_assessment_run(
          assessmentRunArn='string'
      )
    :type assessmentRunArn: string
    :param assessmentRunArn: **[REQUIRED]** 

      The ARN of the assessment run that you want to stop.

      

    
    
    :returns: None

  .. py:method:: subscribe_to_event(**kwargs)

    

    Enables the process of sending Amazon Simple Notification Service (SNS) notifications about a specified event to a specified SNS topic.

    

    **Request Syntax** 
    ::

      response = client.subscribe_to_event(
          resourceArn='string',
          event='ASSESSMENT_RUN_STARTED'|'ASSESSMENT_RUN_COMPLETED'|'ASSESSMENT_RUN_STATE_CHANGED'|'FINDING_REPORTED'|'OTHER',
          topicArn='string'
      )
    :type resourceArn: string
    :param resourceArn: **[REQUIRED]** 

      The ARN of the assessment template that is used during the event for which you want to receive SNS notifications.

      

    
    :type event: string
    :param event: **[REQUIRED]** 

      The event for which you want to receive SNS notifications.

      

    
    :type topicArn: string
    :param topicArn: **[REQUIRED]** 

      The ARN of the SNS topic to which the SNS notifications are sent.

      

    
    
    :returns: None

  .. py:method:: unsubscribe_from_event(**kwargs)

    

    Disables the process of sending Amazon Simple Notification Service (SNS) notifications about a specified event to a specified SNS topic.

    

    **Request Syntax** 
    ::

      response = client.unsubscribe_from_event(
          resourceArn='string',
          event='ASSESSMENT_RUN_STARTED'|'ASSESSMENT_RUN_COMPLETED'|'ASSESSMENT_RUN_STATE_CHANGED'|'FINDING_REPORTED'|'OTHER',
          topicArn='string'
      )
    :type resourceArn: string
    :param resourceArn: **[REQUIRED]** 

      The ARN of the assessment template that is used during the event for which you want to stop receiving SNS notifications.

      

    
    :type event: string
    :param event: **[REQUIRED]** 

      The event for which you want to stop receiving SNS notifications.

      

    
    :type topicArn: string
    :param topicArn: **[REQUIRED]** 

      The ARN of the SNS topic to which SNS notifications are sent.

      

    
    
    :returns: None

  .. py:method:: update_assessment_target(**kwargs)

    

    Updates the assessment target that is specified by the ARN of the assessment target.

    

    **Request Syntax** 
    ::

      response = client.update_assessment_target(
          assessmentTargetArn='string',
          assessmentTargetName='string',
          resourceGroupArn='string'
      )
    :type assessmentTargetArn: string
    :param assessmentTargetArn: **[REQUIRED]** 

      The ARN of the assessment target that you want to update.

      

    
    :type assessmentTargetName: string
    :param assessmentTargetName: **[REQUIRED]** 

      The name of the assessment target that you want to update.

      

    
    :type resourceGroupArn: string
    :param resourceGroupArn: **[REQUIRED]** 

      The ARN of the resource group that is used to specify the new resource group to associate with the assessment target.

      

    
    
    :returns: None