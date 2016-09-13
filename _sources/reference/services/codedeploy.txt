

**********
CodeDeploy
**********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: CodeDeploy.Client

  A low-level client representing AWS CodeDeploy::

    
    import boto3
    
    client = boto3.client('codedeploy')

  
  These are the available methods:
  
  *   :py:meth:`add_tags_to_on_premises_instances`

  
  *   :py:meth:`batch_get_application_revisions`

  
  *   :py:meth:`batch_get_applications`

  
  *   :py:meth:`batch_get_deployment_groups`

  
  *   :py:meth:`batch_get_deployment_instances`

  
  *   :py:meth:`batch_get_deployments`

  
  *   :py:meth:`batch_get_on_premises_instances`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_application`

  
  *   :py:meth:`create_deployment`

  
  *   :py:meth:`create_deployment_config`

  
  *   :py:meth:`create_deployment_group`

  
  *   :py:meth:`delete_application`

  
  *   :py:meth:`delete_deployment_config`

  
  *   :py:meth:`delete_deployment_group`

  
  *   :py:meth:`deregister_on_premises_instance`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_application`

  
  *   :py:meth:`get_application_revision`

  
  *   :py:meth:`get_deployment`

  
  *   :py:meth:`get_deployment_config`

  
  *   :py:meth:`get_deployment_group`

  
  *   :py:meth:`get_deployment_instance`

  
  *   :py:meth:`get_on_premises_instance`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_application_revisions`

  
  *   :py:meth:`list_applications`

  
  *   :py:meth:`list_deployment_configs`

  
  *   :py:meth:`list_deployment_groups`

  
  *   :py:meth:`list_deployment_instances`

  
  *   :py:meth:`list_deployments`

  
  *   :py:meth:`list_on_premises_instances`

  
  *   :py:meth:`register_application_revision`

  
  *   :py:meth:`register_on_premises_instance`

  
  *   :py:meth:`remove_tags_from_on_premises_instances`

  
  *   :py:meth:`stop_deployment`

  
  *   :py:meth:`update_application`

  
  *   :py:meth:`update_deployment_group`

  

  .. py:method:: add_tags_to_on_premises_instances(**kwargs)

    

    Adds tags to on-premises instances.

    

    **Request Syntax** 
    ::

      response = client.add_tags_to_on_premises_instances(
          tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          instanceNames=[
              'string',
          ]
      )
    :type tags: list
    :param tags: **[REQUIRED]** 

      The tag key-value pairs to add to the on-premises instances.

       

      Keys and values are both required. Keys cannot be null or empty strings. Value-only tags are not allowed.

      

    
      - *(dict) --* 

        Information about a tag.

        

      
        - **Key** *(string) --* 

          The tag's key.

          

        
        - **Value** *(string) --* 

          The tag's value.

          

        
      
  
    :type instanceNames: list
    :param instanceNames: **[REQUIRED]** 

      The names of the on-premises instances to which to add tags.

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: batch_get_application_revisions(**kwargs)

    

    Gets information about one or more application revisions.

    

    **Request Syntax** 
    ::

      response = client.batch_get_application_revisions(
          applicationName='string',
          revisions=[
              {
                  'revisionType': 'S3'|'GitHub',
                  's3Location': {
                      'bucket': 'string',
                      'key': 'string',
                      'bundleType': 'tar'|'tgz'|'zip',
                      'version': 'string',
                      'eTag': 'string'
                  },
                  'gitHubLocation': {
                      'repository': 'string',
                      'commitId': 'string'
                  }
              },
          ]
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application about which to get revision information.

      

    
    :type revisions: list
    :param revisions: **[REQUIRED]** 

      Information to get about the application revisions, including type and location.

      

    
      - *(dict) --* 

        Information about the location of an application revision.

        

      
        - **revisionType** *(string) --* 

          The type of application revision:

           

           
          * S3: An application revision stored in Amazon S3.
           
          * GitHub: An application revision stored in GitHub.
           

          

        
        - **s3Location** *(dict) --* 

          Information about the location of application artifacts stored in Amazon S3.

          

        
          - **bucket** *(string) --* 

            The name of the Amazon S3 bucket where the application revision is stored.

            

          
          - **key** *(string) --* 

            The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

            

          
          - **bundleType** *(string) --* 

            The file type of the application revision. Must be one of the following:

             

             
            * tar: A tar archive file.
             
            * tgz: A compressed tar archive file.
             
            * zip: A zip archive file.
             

            

          
          - **version** *(string) --* 

            A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

             

            If the version is not specified, the system will use the most recent version by default.

            

          
          - **eTag** *(string) --* 

            The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

             

            If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

            

          
        
        - **gitHubLocation** *(dict) --* 

          Information about the location of application artifacts stored in GitHub.

          

        
          - **repository** *(string) --* 

            The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

             

            Specified as account/repository.

            

          
          - **commitId** *(string) --* 

            The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

            

          
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'applicationName': 'string',
            'errorMessage': 'string',
            'revisions': [
                {
                    'revisionLocation': {
                        'revisionType': 'S3'|'GitHub',
                        's3Location': {
                            'bucket': 'string',
                            'key': 'string',
                            'bundleType': 'tar'|'tgz'|'zip',
                            'version': 'string',
                            'eTag': 'string'
                        },
                        'gitHubLocation': {
                            'repository': 'string',
                            'commitId': 'string'
                        }
                    },
                    'genericRevisionInfo': {
                        'description': 'string',
                        'deploymentGroups': [
                            'string',
                        ],
                        'firstUsedTime': datetime(2015, 1, 1),
                        'lastUsedTime': datetime(2015, 1, 1),
                        'registerTime': datetime(2015, 1, 1)
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a batch get application revisions operation.

        
        

        - **applicationName** *(string) --* 

          The name of the application that corresponds to the revisions.

          
        

        - **errorMessage** *(string) --* 

          Information about errors that may have occurred during the API call.

          
        

        - **revisions** *(list) --* 

          Additional information about the revisions, including the type and location.

          
          

          - *(dict) --* 

            Information about an application revision.

            
            

            - **revisionLocation** *(dict) --* 

              Information about the location of an application revision.

              
              

              - **revisionType** *(string) --* 

                The type of application revision:

                 

                 
                * S3: An application revision stored in Amazon S3.
                 
                * GitHub: An application revision stored in GitHub.
                 

                
              

              - **s3Location** *(dict) --* 

                Information about the location of application artifacts stored in Amazon S3.

                
                

                - **bucket** *(string) --* 

                  The name of the Amazon S3 bucket where the application revision is stored.

                  
                

                - **key** *(string) --* 

                  The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

                  
                

                - **bundleType** *(string) --* 

                  The file type of the application revision. Must be one of the following:

                   

                   
                  * tar: A tar archive file.
                   
                  * tgz: A compressed tar archive file.
                   
                  * zip: A zip archive file.
                   

                  
                

                - **version** *(string) --* 

                  A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

                   

                  If the version is not specified, the system will use the most recent version by default.

                  
                

                - **eTag** *(string) --* 

                  The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

                   

                  If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

                  
            
              

              - **gitHubLocation** *(dict) --* 

                Information about the location of application artifacts stored in GitHub.

                
                

                - **repository** *(string) --* 

                  The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

                   

                  Specified as account/repository.

                  
                

                - **commitId** *(string) --* 

                  The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

                  
            
          
            

            - **genericRevisionInfo** *(dict) --* 

              Information about an application revision.

              
              

              - **description** *(string) --* 

                A comment about the revision.

                
              

              - **deploymentGroups** *(list) --* 

                The deployment groups for which this is the current target revision.

                
                

                - *(string) --* 
            
              

              - **firstUsedTime** *(datetime) --* 

                When the revision was first used by AWS CodeDeploy.

                
              

              - **lastUsedTime** *(datetime) --* 

                When the revision was last used by AWS CodeDeploy.

                
              

              - **registerTime** *(datetime) --* 

                When the revision was registered with AWS CodeDeploy.

                
          
        
      
    

  .. py:method:: batch_get_applications(**kwargs)

    

    Gets information about one or more applications.

    

    **Request Syntax** 
    ::

      response = client.batch_get_applications(
          applicationNames=[
              'string',
          ]
      )
    :type applicationNames: list
    :param applicationNames: 

      A list of application names separated by spaces.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'applicationsInfo': [
                {
                    'applicationId': 'string',
                    'applicationName': 'string',
                    'createTime': datetime(2015, 1, 1),
                    'linkedToGitHub': True|False
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a batch get applications operation.

        
        

        - **applicationsInfo** *(list) --* 

          Information about the applications.

          
          

          - *(dict) --* 

            Information about an application.

            
            

            - **applicationId** *(string) --* 

              The application ID.

              
            

            - **applicationName** *(string) --* 

              The application name.

              
            

            - **createTime** *(datetime) --* 

              The time at which the application was created.

              
            

            - **linkedToGitHub** *(boolean) --* 

              True if the user has authenticated with GitHub for the specified application; otherwise, false.

              
        
      
    

  .. py:method:: batch_get_deployment_groups(**kwargs)

    

    Get information about one or more deployment groups.

    

    **Request Syntax** 
    ::

      response = client.batch_get_deployment_groups(
          applicationName='string',
          deploymentGroupNames=[
              'string',
          ]
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    :type deploymentGroupNames: list
    :param deploymentGroupNames: **[REQUIRED]** 

      The deployment groups' names.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentGroupsInfo': [
                {
                    'applicationName': 'string',
                    'deploymentGroupId': 'string',
                    'deploymentGroupName': 'string',
                    'deploymentConfigName': 'string',
                    'ec2TagFilters': [
                        {
                            'Key': 'string',
                            'Value': 'string',
                            'Type': 'KEY_ONLY'|'VALUE_ONLY'|'KEY_AND_VALUE'
                        },
                    ],
                    'onPremisesInstanceTagFilters': [
                        {
                            'Key': 'string',
                            'Value': 'string',
                            'Type': 'KEY_ONLY'|'VALUE_ONLY'|'KEY_AND_VALUE'
                        },
                    ],
                    'autoScalingGroups': [
                        {
                            'name': 'string',
                            'hook': 'string'
                        },
                    ],
                    'serviceRoleArn': 'string',
                    'targetRevision': {
                        'revisionType': 'S3'|'GitHub',
                        's3Location': {
                            'bucket': 'string',
                            'key': 'string',
                            'bundleType': 'tar'|'tgz'|'zip',
                            'version': 'string',
                            'eTag': 'string'
                        },
                        'gitHubLocation': {
                            'repository': 'string',
                            'commitId': 'string'
                        }
                    },
                    'triggerConfigurations': [
                        {
                            'triggerName': 'string',
                            'triggerTargetArn': 'string',
                            'triggerEvents': [
                                'DeploymentStart'|'DeploymentSuccess'|'DeploymentFailure'|'DeploymentStop'|'InstanceStart'|'InstanceSuccess'|'InstanceFailure',
                            ]
                        },
                    ]
                },
            ],
            'errorMessage': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a batch get deployment groups operation.

        
        

        - **deploymentGroupsInfo** *(list) --* 

          Information about the deployment groups.

          
          

          - *(dict) --* 

            Information about a deployment group.

            
            

            - **applicationName** *(string) --* 

              The application name.

              
            

            - **deploymentGroupId** *(string) --* 

              The deployment group ID.

              
            

            - **deploymentGroupName** *(string) --* 

              The deployment group name.

              
            

            - **deploymentConfigName** *(string) --* 

              The deployment configuration name.

              
            

            - **ec2TagFilters** *(list) --* 

              The Amazon EC2 tags on which to filter.

              
              

              - *(dict) --* 

                Information about a tag filter.

                
                

                - **Key** *(string) --* 

                  The tag filter key.

                  
                

                - **Value** *(string) --* 

                  The tag filter value.

                  
                

                - **Type** *(string) --* 

                  The tag filter type:

                   

                   
                  * KEY_ONLY: Key only.
                   
                  * VALUE_ONLY: Value only.
                   
                  * KEY_AND_VALUE: Key and value.
                   

                  
            
          
            

            - **onPremisesInstanceTagFilters** *(list) --* 

              The on-premises instance tags on which to filter.

              
              

              - *(dict) --* 

                Information about an on-premises instance tag filter.

                
                

                - **Key** *(string) --* 

                  The on-premises instance tag filter key.

                  
                

                - **Value** *(string) --* 

                  The on-premises instance tag filter value.

                  
                

                - **Type** *(string) --* 

                  The on-premises instance tag filter type:

                   

                   
                  * KEY_ONLY: Key only.
                   
                  * VALUE_ONLY: Value only.
                   
                  * KEY_AND_VALUE: Key and value.
                   

                  
            
          
            

            - **autoScalingGroups** *(list) --* 

              A list of associated Auto Scaling groups.

              
              

              - *(dict) --* 

                Information about an Auto Scaling group.

                
                

                - **name** *(string) --* 

                  The Auto Scaling group name.

                  
                

                - **hook** *(string) --* 

                  An Auto Scaling lifecycle event hook name.

                  
            
          
            

            - **serviceRoleArn** *(string) --* 

              A service role ARN.

              
            

            - **targetRevision** *(dict) --* 

              Information about the deployment group's target revision, including type and location.

              
              

              - **revisionType** *(string) --* 

                The type of application revision:

                 

                 
                * S3: An application revision stored in Amazon S3.
                 
                * GitHub: An application revision stored in GitHub.
                 

                
              

              - **s3Location** *(dict) --* 

                Information about the location of application artifacts stored in Amazon S3.

                
                

                - **bucket** *(string) --* 

                  The name of the Amazon S3 bucket where the application revision is stored.

                  
                

                - **key** *(string) --* 

                  The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

                  
                

                - **bundleType** *(string) --* 

                  The file type of the application revision. Must be one of the following:

                   

                   
                  * tar: A tar archive file.
                   
                  * tgz: A compressed tar archive file.
                   
                  * zip: A zip archive file.
                   

                  
                

                - **version** *(string) --* 

                  A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

                   

                  If the version is not specified, the system will use the most recent version by default.

                  
                

                - **eTag** *(string) --* 

                  The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

                   

                  If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

                  
            
              

              - **gitHubLocation** *(dict) --* 

                Information about the location of application artifacts stored in GitHub.

                
                

                - **repository** *(string) --* 

                  The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

                   

                  Specified as account/repository.

                  
                

                - **commitId** *(string) --* 

                  The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

                  
            
          
            

            - **triggerConfigurations** *(list) --* 

              A list of associated triggers. 

              
              

              - *(dict) --* 

                Information about notification triggers for the deployment group.

                
                

                - **triggerName** *(string) --* 

                  The name of the notification trigger.

                  
                

                - **triggerTargetArn** *(string) --* 

                  The ARN of the Amazon Simple Notification Service topic through which notifications about deployment or instance events are sent.

                  
                

                - **triggerEvents** *(list) --* 

                  The event type or types for which notifications are triggered.

                   

                  The following event type values are supported:

                   

                   
                  * DEPLOYMENT_START
                   
                  * DEPLOYMENT_SUCCESS
                   
                  * DEPLOYMENT_FAILURE
                   
                  * DEPLOYMENT_STOP
                   
                  * INSTANCE_START
                   
                  * INSTANCE_SUCCESS
                   
                  * INSTANCE_FAILURE
                   

                  
                  

                  - *(string) --* 
              
            
          
        
      
        

        - **errorMessage** *(string) --* 

          Information about errors that may have occurred during the API call.

          
    

  .. py:method:: batch_get_deployment_instances(**kwargs)

    

    Gets information about one or more instance that are part of a deployment group.

    

    **Request Syntax** 
    ::

      response = client.batch_get_deployment_instances(
          deploymentId='string',
          instanceIds=[
              'string',
          ]
      )
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      The unique ID of a deployment.

      

    
    :type instanceIds: list
    :param instanceIds: **[REQUIRED]** 

      The unique IDs of instances in the deployment group.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'instancesSummary': [
                {
                    'deploymentId': 'string',
                    'instanceId': 'string',
                    'status': 'Pending'|'InProgress'|'Succeeded'|'Failed'|'Skipped'|'Unknown',
                    'lastUpdatedAt': datetime(2015, 1, 1),
                    'lifecycleEvents': [
                        {
                            'lifecycleEventName': 'string',
                            'diagnostics': {
                                'errorCode': 'Success'|'ScriptMissing'|'ScriptNotExecutable'|'ScriptTimedOut'|'ScriptFailed'|'UnknownError',
                                'scriptName': 'string',
                                'message': 'string',
                                'logTail': 'string'
                            },
                            'startTime': datetime(2015, 1, 1),
                            'endTime': datetime(2015, 1, 1),
                            'status': 'Pending'|'InProgress'|'Succeeded'|'Failed'|'Skipped'|'Unknown'
                        },
                    ]
                },
            ],
            'errorMessage': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a batch get deployment instance operation.

        
        

        - **instancesSummary** *(list) --* 

          Information about the instance.

          
          

          - *(dict) --* 

            Information about an instance in a deployment.

            
            

            - **deploymentId** *(string) --* 

              The deployment ID.

              
            

            - **instanceId** *(string) --* 

              The instance ID.

              
            

            - **status** *(string) --* 

              The deployment status for this instance:

               

               
              * Pending: The deployment is pending for this instance.
               
              * In Progress: The deployment is in progress for this instance.
               
              * Succeeded: The deployment has succeeded for this instance.
               
              * Failed: The deployment has failed for this instance.
               
              * Skipped: The deployment has been skipped for this instance.
               
              * Unknown: The deployment status is unknown for this instance.
               

              
            

            - **lastUpdatedAt** *(datetime) --* 

              A timestamp indicating when the instance information was last updated.

              
            

            - **lifecycleEvents** *(list) --* 

              A list of lifecycle events for this instance.

              
              

              - *(dict) --* 

                Information about a deployment lifecycle event.

                
                

                - **lifecycleEventName** *(string) --* 

                  The deployment lifecycle event name, such as ApplicationStop, BeforeInstall, AfterInstall, ApplicationStart, or ValidateService.

                  
                

                - **diagnostics** *(dict) --* 

                  Diagnostic information about the deployment lifecycle event.

                  
                  

                  - **errorCode** *(string) --* 

                    The associated error code:

                     

                     
                    * Success: The specified script ran.
                     
                    * ScriptMissing: The specified script was not found in the specified location.
                     
                    * ScriptNotExecutable: The specified script is not a recognized executable file type.
                     
                    * ScriptTimedOut: The specified script did not finish running in the specified time period.
                     
                    * ScriptFailed: The specified script failed to run as expected.
                     
                    * UnknownError: The specified script did not run for an unknown reason.
                     

                    
                  

                  - **scriptName** *(string) --* 

                    The name of the script.

                    
                  

                  - **message** *(string) --* 

                    The message associated with the error.

                    
                  

                  - **logTail** *(string) --* 

                    The last portion of the diagnostic log.

                     

                    If available, AWS CodeDeploy returns up to the last 4 KB of the diagnostic log.

                    
              
                

                - **startTime** *(datetime) --* 

                  A timestamp indicating when the deployment lifecycle event started.

                  
                

                - **endTime** *(datetime) --* 

                  A timestamp indicating when the deployment lifecycle event ended.

                  
                

                - **status** *(string) --* 

                  The deployment lifecycle event status:

                   

                   
                  * Pending: The deployment lifecycle event is pending.
                   
                  * InProgress: The deployment lifecycle event is in progress.
                   
                  * Succeeded: The deployment lifecycle event ran successfully.
                   
                  * Failed: The deployment lifecycle event has failed.
                   
                  * Skipped: The deployment lifecycle event has been skipped.
                   
                  * Unknown: The deployment lifecycle event is unknown.
                   

                  
            
          
        
      
        

        - **errorMessage** *(string) --* 

          Information about errors that may have occurred during the API call.

          
    

  .. py:method:: batch_get_deployments(**kwargs)

    

    Gets information about one or more deployments.

    

    **Request Syntax** 
    ::

      response = client.batch_get_deployments(
          deploymentIds=[
              'string',
          ]
      )
    :type deploymentIds: list
    :param deploymentIds: 

      A list of deployment IDs, separated by spaces.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentsInfo': [
                {
                    'applicationName': 'string',
                    'deploymentGroupName': 'string',
                    'deploymentConfigName': 'string',
                    'deploymentId': 'string',
                    'revision': {
                        'revisionType': 'S3'|'GitHub',
                        's3Location': {
                            'bucket': 'string',
                            'key': 'string',
                            'bundleType': 'tar'|'tgz'|'zip',
                            'version': 'string',
                            'eTag': 'string'
                        },
                        'gitHubLocation': {
                            'repository': 'string',
                            'commitId': 'string'
                        }
                    },
                    'status': 'Created'|'Queued'|'InProgress'|'Succeeded'|'Failed'|'Stopped',
                    'errorInformation': {
                        'code': 'DEPLOYMENT_GROUP_MISSING'|'APPLICATION_MISSING'|'REVISION_MISSING'|'IAM_ROLE_MISSING'|'IAM_ROLE_PERMISSIONS'|'NO_EC2_SUBSCRIPTION'|'OVER_MAX_INSTANCES'|'NO_INSTANCES'|'TIMEOUT'|'HEALTH_CONSTRAINTS_INVALID'|'HEALTH_CONSTRAINTS'|'INTERNAL_ERROR'|'THROTTLED',
                        'message': 'string'
                    },
                    'createTime': datetime(2015, 1, 1),
                    'startTime': datetime(2015, 1, 1),
                    'completeTime': datetime(2015, 1, 1),
                    'deploymentOverview': {
                        'Pending': 123,
                        'InProgress': 123,
                        'Succeeded': 123,
                        'Failed': 123,
                        'Skipped': 123
                    },
                    'description': 'string',
                    'creator': 'user'|'autoscaling',
                    'ignoreApplicationStopFailures': True|False
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a batch get deployments operation.

        
        

        - **deploymentsInfo** *(list) --* 

          Information about the deployments.

          
          

          - *(dict) --* 

            Information about a deployment.

            
            

            - **applicationName** *(string) --* 

              The application name.

              
            

            - **deploymentGroupName** *(string) --* 

              The deployment group name.

              
            

            - **deploymentConfigName** *(string) --* 

              The deployment configuration name.

              
            

            - **deploymentId** *(string) --* 

              The deployment ID.

              
            

            - **revision** *(dict) --* 

              Information about the location of stored application artifacts and the service from which to retrieve them.

              
              

              - **revisionType** *(string) --* 

                The type of application revision:

                 

                 
                * S3: An application revision stored in Amazon S3.
                 
                * GitHub: An application revision stored in GitHub.
                 

                
              

              - **s3Location** *(dict) --* 

                Information about the location of application artifacts stored in Amazon S3.

                
                

                - **bucket** *(string) --* 

                  The name of the Amazon S3 bucket where the application revision is stored.

                  
                

                - **key** *(string) --* 

                  The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

                  
                

                - **bundleType** *(string) --* 

                  The file type of the application revision. Must be one of the following:

                   

                   
                  * tar: A tar archive file.
                   
                  * tgz: A compressed tar archive file.
                   
                  * zip: A zip archive file.
                   

                  
                

                - **version** *(string) --* 

                  A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

                   

                  If the version is not specified, the system will use the most recent version by default.

                  
                

                - **eTag** *(string) --* 

                  The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

                   

                  If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

                  
            
              

              - **gitHubLocation** *(dict) --* 

                Information about the location of application artifacts stored in GitHub.

                
                

                - **repository** *(string) --* 

                  The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

                   

                  Specified as account/repository.

                  
                

                - **commitId** *(string) --* 

                  The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

                  
            
          
            

            - **status** *(string) --* 

              The current state of the deployment as a whole.

              
            

            - **errorInformation** *(dict) --* 

              Information about any error associated with this deployment.

              
              

              - **code** *(string) --* 

                The error code:

                 

                 
                * APPLICATION_MISSING: The application was missing. This error code will most likely be raised if the application is deleted after the deployment is created but before it is started.
                 
                * DEPLOYMENT_GROUP_MISSING: The deployment group was missing. This error code will most likely be raised if the deployment group is deleted after the deployment is created but before it is started.
                 
                * HEALTH_CONSTRAINTS: The deployment failed on too many instances to be successfully deployed within the instance health constraints specified.
                 
                * HEALTH_CONSTRAINTS_INVALID: The revision cannot be successfully deployed within the instance health constraints specified.
                 
                * IAM_ROLE_MISSING: The service role cannot be accessed.
                 
                * IAM_ROLE_PERMISSIONS: The service role does not have the correct permissions.
                 
                * INTERNAL_ERROR: There was an internal error.
                 
                * NO_EC2_SUBSCRIPTION: The calling account is not subscribed to the Amazon EC2 service.
                 
                * NO_INSTANCES: No instance were specified, or no instance can be found.
                 
                * OVER_MAX_INSTANCES: The maximum number of instance was exceeded.
                 
                * THROTTLED: The operation was throttled because the calling account exceeded the throttling limits of one or more AWS services.
                 
                * TIMEOUT: The deployment has timed out.
                 
                * REVISION_MISSING: The revision ID was missing. This error code will most likely be raised if the revision is deleted after the deployment is created but before it is started.
                 

                
              

              - **message** *(string) --* 

                An accompanying error message.

                
          
            

            - **createTime** *(datetime) --* 

              A timestamp indicating when the deployment was created.

              
            

            - **startTime** *(datetime) --* 

              A timestamp indicating when the deployment was deployed to the deployment group.

               

              In some cases, the reported value of the start time may be later than the complete time. This is due to differences in the clock settings of back-end servers that participate in the deployment process.

              
            

            - **completeTime** *(datetime) --* 

              A timestamp indicating when the deployment was complete.

              
            

            - **deploymentOverview** *(dict) --* 

              A summary of the deployment status of the instances in the deployment.

              
              

              - **Pending** *(integer) --* 

                The number of instances in the deployment in a pending state.

                
              

              - **InProgress** *(integer) --* 

                The number of instances in which the deployment is in progress.

                
              

              - **Succeeded** *(integer) --* 

                The number of instances in the deployment to which revisions have been successfully deployed.

                
              

              - **Failed** *(integer) --* 

                The number of instances in the deployment in a failed state.

                
              

              - **Skipped** *(integer) --* 

                The number of instances in the deployment in a skipped state.

                
          
            

            - **description** *(string) --* 

              A comment about the deployment.

              
            

            - **creator** *(string) --* 

              The means by which the deployment was created:

               

               
              * user: A user created the deployment.
               
              * autoscaling: Auto Scaling created the deployment.
               

              
            

            - **ignoreApplicationStopFailures** *(boolean) --* 

              If true, then if the deployment causes the ApplicationStop deployment lifecycle event to an instance to fail, the deployment to that instance will not be considered to have failed at that point and will continue on to the BeforeInstall deployment lifecycle event.

               

              If false or not specified, then if the deployment causes the ApplicationStop deployment lifecycle event to an instance to fail, the deployment to that instance will stop, and the deployment to that instance will be considered to have failed.

              
        
      
    

  .. py:method:: batch_get_on_premises_instances(**kwargs)

    

    Gets information about one or more on-premises instances.

    

    **Request Syntax** 
    ::

      response = client.batch_get_on_premises_instances(
          instanceNames=[
              'string',
          ]
      )
    :type instanceNames: list
    :param instanceNames: 

      The names of the on-premises instances about which to get information.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'instanceInfos': [
                {
                    'instanceName': 'string',
                    'iamUserArn': 'string',
                    'instanceArn': 'string',
                    'registerTime': datetime(2015, 1, 1),
                    'deregisterTime': datetime(2015, 1, 1),
                    'tags': [
                        {
                            'Key': 'string',
                            'Value': 'string'
                        },
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a batch get on-premises instances operation.

        
        

        - **instanceInfos** *(list) --* 

          Information about the on-premises instances.

          
          

          - *(dict) --* 

            Information about an on-premises instance.

            
            

            - **instanceName** *(string) --* 

              The name of the on-premises instance.

              
            

            - **iamUserArn** *(string) --* 

              The IAM user ARN associated with the on-premises instance.

              
            

            - **instanceArn** *(string) --* 

              The ARN of the on-premises instance.

              
            

            - **registerTime** *(datetime) --* 

              The time at which the on-premises instance was registered.

              
            

            - **deregisterTime** *(datetime) --* 

              If the on-premises instance was deregistered, the time at which the on-premises instance was deregistered.

              
            

            - **tags** *(list) --* 

              The tags currently associated with the on-premises instance.

              
              

              - *(dict) --* 

                Information about a tag.

                
                

                - **Key** *(string) --* 

                  The tag's key.

                  
                

                - **Value** *(string) --* 

                  The tag's value.

                  
            
          
        
      
    

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


  .. py:method:: create_application(**kwargs)

    

    Creates an application.

    

    **Request Syntax** 
    ::

      response = client.create_application(
          applicationName='string'
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of the application. This name must be unique with the applicable IAM user or AWS account.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'applicationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a create application operation.

        
        

        - **applicationId** *(string) --* 

          A unique application ID.

          
    

  .. py:method:: create_deployment(**kwargs)

    

    Deploys an application revision through the specified deployment group.

    

    **Request Syntax** 
    ::

      response = client.create_deployment(
          applicationName='string',
          deploymentGroupName='string',
          revision={
              'revisionType': 'S3'|'GitHub',
              's3Location': {
                  'bucket': 'string',
                  'key': 'string',
                  'bundleType': 'tar'|'tgz'|'zip',
                  'version': 'string',
                  'eTag': 'string'
              },
              'gitHubLocation': {
                  'repository': 'string',
                  'commitId': 'string'
              }
          },
          deploymentConfigName='string',
          description='string',
          ignoreApplicationStopFailures=True|False
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    :type deploymentGroupName: string
    :param deploymentGroupName: 

      The name of the deployment group.

      

    
    :type revision: dict
    :param revision: 

      The type and location of the revision to deploy.

      

    
      - **revisionType** *(string) --* 

        The type of application revision:

         

         
        * S3: An application revision stored in Amazon S3.
         
        * GitHub: An application revision stored in GitHub.
         

        

      
      - **s3Location** *(dict) --* 

        Information about the location of application artifacts stored in Amazon S3.

        

      
        - **bucket** *(string) --* 

          The name of the Amazon S3 bucket where the application revision is stored.

          

        
        - **key** *(string) --* 

          The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

          

        
        - **bundleType** *(string) --* 

          The file type of the application revision. Must be one of the following:

           

           
          * tar: A tar archive file.
           
          * tgz: A compressed tar archive file.
           
          * zip: A zip archive file.
           

          

        
        - **version** *(string) --* 

          A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the version is not specified, the system will use the most recent version by default.

          

        
        - **eTag** *(string) --* 

          The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

          

        
      
      - **gitHubLocation** *(dict) --* 

        Information about the location of application artifacts stored in GitHub.

        

      
        - **repository** *(string) --* 

          The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

           

          Specified as account/repository.

          

        
        - **commitId** *(string) --* 

          The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

          

        
      
    
    :type deploymentConfigName: string
    :param deploymentConfigName: 

      The name of a deployment configuration associated with the applicable IAM user or AWS account.

       

      If not specified, the value configured in the deployment group will be used as the default. If the deployment group does not have a deployment configuration associated with it, then CodeDeployDefault.OneAtATime will be used by default.

      

    
    :type description: string
    :param description: 

      A comment about the deployment.

      

    
    :type ignoreApplicationStopFailures: boolean
    :param ignoreApplicationStopFailures: 

      If set to true, then if the deployment causes the ApplicationStop deployment lifecycle event to an instance to fail, the deployment to that instance will not be considered to have failed at that point and will continue on to the BeforeInstall deployment lifecycle event.

       

      If set to false or not specified, then if the deployment causes the ApplicationStop deployment lifecycle event to fail to an instance, the deployment to that instance will stop, and the deployment to that instance will be considered to have failed.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a create deployment operation.

        
        

        - **deploymentId** *(string) --* 

          A unique deployment ID.

          
    

  .. py:method:: create_deployment_config(**kwargs)

    

    Creates a deployment configuration.

    

    **Request Syntax** 
    ::

      response = client.create_deployment_config(
          deploymentConfigName='string',
          minimumHealthyHosts={
              'value': 123,
              'type': 'HOST_COUNT'|'FLEET_PERCENT'
          }
      )
    :type deploymentConfigName: string
    :param deploymentConfigName: **[REQUIRED]** 

      The name of the deployment configuration to create.

      

    
    :type minimumHealthyHosts: dict
    :param minimumHealthyHosts: 

      The minimum number of healthy instances that should be available at any time during the deployment. There are two parameters expected in the input: type and value.

       

      The type parameter takes either of the following values:

       

       
      * HOST_COUNT: The value parameter represents the minimum number of healthy instances as an absolute value.
       
      * FLEET_PERCENT: The value parameter represents the minimum number of healthy instances as a percentage of the total number of instances in the deployment. If you specify FLEET_PERCENT, at the start of the deployment, AWS CodeDeploy converts the percentage to the equivalent number of instance and rounds up fractional instances.
       

       

      The value parameter takes an integer.

       

      For example, to set a minimum of 95% healthy instance, specify a type of FLEET_PERCENT and a value of 95.

      

    
      - **value** *(integer) --* 

        The minimum healthy instance value.

        

      
      - **type** *(string) --* 

        The minimum healthy instance type:

         

         
        * HOST_COUNT: The minimum number of healthy instance as an absolute value.
         
        * FLEET_PERCENT: The minimum number of healthy instance as a percentage of the total number of instance in the deployment.
         

         

        In an example of nine instance, if a HOST_COUNT of six is specified, deploy to up to three instances at a time. The deployment will be successful if six or more instances are deployed to successfully; otherwise, the deployment fails. If a FLEET_PERCENT of 40 is specified, deploy to up to five instance at a time. The deployment will be successful if four or more instance are deployed to successfully; otherwise, the deployment fails.

         

        .. note::

          In a call to the get deployment configuration operation, CodeDeployDefault.OneAtATime will return a minimum healthy instance type of MOST_CONCURRENCY and a value of 1. This means a deployment to only one instance at a time. (You cannot set the type to MOST_CONCURRENCY, only to HOST_COUNT or FLEET_PERCENT.) In addition, with CodeDeployDefault.OneAtATime, AWS CodeDeploy will try to ensure that all instances but one are kept in a healthy state during the deployment. Although this allows one instance at a time to be taken offline for a new deployment, it also means that if the deployment to the last instance fails, the overall deployment still succeeds.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentConfigId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a create deployment configuration operation.

        
        

        - **deploymentConfigId** *(string) --* 

          A unique deployment configuration ID.

          
    

  .. py:method:: create_deployment_group(**kwargs)

    

    Creates a deployment group to which application revisions will be deployed.

    

    **Request Syntax** 
    ::

      response = client.create_deployment_group(
          applicationName='string',
          deploymentGroupName='string',
          deploymentConfigName='string',
          ec2TagFilters=[
              {
                  'Key': 'string',
                  'Value': 'string',
                  'Type': 'KEY_ONLY'|'VALUE_ONLY'|'KEY_AND_VALUE'
              },
          ],
          onPremisesInstanceTagFilters=[
              {
                  'Key': 'string',
                  'Value': 'string',
                  'Type': 'KEY_ONLY'|'VALUE_ONLY'|'KEY_AND_VALUE'
              },
          ],
          autoScalingGroups=[
              'string',
          ],
          serviceRoleArn='string',
          triggerConfigurations=[
              {
                  'triggerName': 'string',
                  'triggerTargetArn': 'string',
                  'triggerEvents': [
                      'DeploymentStart'|'DeploymentSuccess'|'DeploymentFailure'|'DeploymentStop'|'InstanceStart'|'InstanceSuccess'|'InstanceFailure',
                  ]
              },
          ]
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    :type deploymentGroupName: string
    :param deploymentGroupName: **[REQUIRED]** 

      The name of a new deployment group for the specified application.

      

    
    :type deploymentConfigName: string
    :param deploymentConfigName: 

      If specified, the deployment configuration name can be either one of the predefined configurations provided with AWS CodeDeploy or a custom deployment configuration that you create by calling the create deployment configuration operation.

       

      .. note::

         

        CodeDeployDefault.OneAtATime is the default deployment configuration. It is used if a configuration isn't specified for the deployment or the deployment group.

         

       

      The predefined deployment configurations include the following:

       

       
      * **CodeDeployDefault.AllAtOnce** attempts to deploy an application revision to as many instance as possible at once. The status of the overall deployment will be displayed as **Succeeded** if the application revision is deployed to one or more of the instances. The status of the overall deployment will be displayed as **Failed** if the application revision is not deployed to any of the instances. Using an example of nine instance, CodeDeployDefault.AllAtOnce will attempt to deploy to all nine instance at once. The overall deployment will succeed if deployment to even a single instance is successful; it will fail only if deployments to all nine instance fail.  
       
      * **CodeDeployDefault.HalfAtATime** deploys to up to half of the instances at a time (with fractions rounded down). The overall deployment succeeds if the application revision is deployed to at least half of the instances (with fractions rounded up); otherwise, the deployment fails. In the example of nine instances, it will deploy to up to four instance at a time. The overall deployment succeeds if deployment to five or more instances succeed; otherwise, the deployment fails. The deployment may be successfully deployed to some instances even if the overall deployment fails. 
       
      * **CodeDeployDefault.OneAtATime** deploys the application revision to only one instance at a time. For deployment groups that contain more than one instance: 

         
        * The overall deployment succeeds if the application revision is deployed to all of the instances. The exception to this rule is if deployment to the last instance fails, the overall deployment still succeeds. This is because AWS CodeDeploy allows only one instance at a time to be taken offline with the CodeDeployDefault.OneAtATime configuration. 
         
        * The overall deployment fails as soon as the application revision fails to be deployed to any but the last instance. The deployment may be successfully deployed to some instances even if the overall deployment fails. 
         
        * In an example using nine instance, it will deploy to one instance at a time. The overall deployment succeeds if deployment to the first eight instance is successful; the overall deployment fails if deployment to any of the first eight instance fails. 
         

       

      For deployment groups that contain only one instance, the overall deployment is successful only if deployment to the single instance is successful

       
       

      

    
    :type ec2TagFilters: list
    :param ec2TagFilters: 

      The Amazon EC2 tags on which to filter.

      

    
      - *(dict) --* 

        Information about a tag filter.

        

      
        - **Key** *(string) --* 

          The tag filter key.

          

        
        - **Value** *(string) --* 

          The tag filter value.

          

        
        - **Type** *(string) --* 

          The tag filter type:

           

           
          * KEY_ONLY: Key only.
           
          * VALUE_ONLY: Value only.
           
          * KEY_AND_VALUE: Key and value.
           

          

        
      
  
    :type onPremisesInstanceTagFilters: list
    :param onPremisesInstanceTagFilters: 

      The on-premises instance tags on which to filter.

      

    
      - *(dict) --* 

        Information about an on-premises instance tag filter.

        

      
        - **Key** *(string) --* 

          The on-premises instance tag filter key.

          

        
        - **Value** *(string) --* 

          The on-premises instance tag filter value.

          

        
        - **Type** *(string) --* 

          The on-premises instance tag filter type:

           

           
          * KEY_ONLY: Key only.
           
          * VALUE_ONLY: Value only.
           
          * KEY_AND_VALUE: Key and value.
           

          

        
      
  
    :type autoScalingGroups: list
    :param autoScalingGroups: 

      A list of associated Auto Scaling groups.

      

    
      - *(string) --* 

      
  
    :type serviceRoleArn: string
    :param serviceRoleArn: **[REQUIRED]** 

      A service role ARN that allows AWS CodeDeploy to act on the user's behalf when interacting with AWS services.

      

    
    :type triggerConfigurations: list
    :param triggerConfigurations: 

      Information about triggers to create when the deployment group is created.

      

    
      - *(dict) --* 

        Information about notification triggers for the deployment group.

        

      
        - **triggerName** *(string) --* 

          The name of the notification trigger.

          

        
        - **triggerTargetArn** *(string) --* 

          The ARN of the Amazon Simple Notification Service topic through which notifications about deployment or instance events are sent.

          

        
        - **triggerEvents** *(list) --* 

          The event type or types for which notifications are triggered.

           

          The following event type values are supported:

           

           
          * DEPLOYMENT_START
           
          * DEPLOYMENT_SUCCESS
           
          * DEPLOYMENT_FAILURE
           
          * DEPLOYMENT_STOP
           
          * INSTANCE_START
           
          * INSTANCE_SUCCESS
           
          * INSTANCE_FAILURE
           

          

        
          - *(string) --* 

          
      
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentGroupId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a create deployment group operation.

        
        

        - **deploymentGroupId** *(string) --* 

          A unique deployment group ID.

          
    

  .. py:method:: delete_application(**kwargs)

    

    Deletes an application.

    

    **Request Syntax** 
    ::

      response = client.delete_application(
          applicationName='string'
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    
    :returns: None

  .. py:method:: delete_deployment_config(**kwargs)

    

    Deletes a deployment configuration.

     

    .. note::

      A deployment configuration cannot be deleted if it is currently in use. Predefined configurations cannot be deleted.

    

    **Request Syntax** 
    ::

      response = client.delete_deployment_config(
          deploymentConfigName='string'
      )
    :type deploymentConfigName: string
    :param deploymentConfigName: **[REQUIRED]** 

      The name of a deployment configuration associated with the applicable IAM user or AWS account.

      

    
    
    :returns: None

  .. py:method:: delete_deployment_group(**kwargs)

    

    Deletes a deployment group.

    

    **Request Syntax** 
    ::

      response = client.delete_deployment_group(
          applicationName='string',
          deploymentGroupName='string'
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    :type deploymentGroupName: string
    :param deploymentGroupName: **[REQUIRED]** 

      The name of an existing deployment group for the specified application.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'hooksNotCleanedUp': [
                {
                    'name': 'string',
                    'hook': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a delete deployment group operation.

        
        

        - **hooksNotCleanedUp** *(list) --* 

          If the output contains no data, and the corresponding deployment group contained at least one Auto Scaling group, AWS CodeDeploy successfully removed all corresponding Auto Scaling lifecycle event hooks from the Amazon EC2 instances in the Auto Scaling group. If the output contains data, AWS CodeDeploy could not remove some Auto Scaling lifecycle event hooks from the Amazon EC2 instances in the Auto Scaling group.

          
          

          - *(dict) --* 

            Information about an Auto Scaling group.

            
            

            - **name** *(string) --* 

              The Auto Scaling group name.

              
            

            - **hook** *(string) --* 

              An Auto Scaling lifecycle event hook name.

              
        
      
    

  .. py:method:: deregister_on_premises_instance(**kwargs)

    

    Deregisters an on-premises instance.

    

    **Request Syntax** 
    ::

      response = client.deregister_on_premises_instance(
          instanceName='string'
      )
    :type instanceName: string
    :param instanceName: **[REQUIRED]** 

      The name of the on-premises instance to deregister.

      

    
    
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


  .. py:method:: get_application(**kwargs)

    

    Gets information about an application.

    

    **Request Syntax** 
    ::

      response = client.get_application(
          applicationName='string'
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'application': {
                'applicationId': 'string',
                'applicationName': 'string',
                'createTime': datetime(2015, 1, 1),
                'linkedToGitHub': True|False
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get application operation.

        
        

        - **application** *(dict) --* 

          Information about the application.

          
          

          - **applicationId** *(string) --* 

            The application ID.

            
          

          - **applicationName** *(string) --* 

            The application name.

            
          

          - **createTime** *(datetime) --* 

            The time at which the application was created.

            
          

          - **linkedToGitHub** *(boolean) --* 

            True if the user has authenticated with GitHub for the specified application; otherwise, false.

            
      
    

  .. py:method:: get_application_revision(**kwargs)

    

    Gets information about an application revision.

    

    **Request Syntax** 
    ::

      response = client.get_application_revision(
          applicationName='string',
          revision={
              'revisionType': 'S3'|'GitHub',
              's3Location': {
                  'bucket': 'string',
                  'key': 'string',
                  'bundleType': 'tar'|'tgz'|'zip',
                  'version': 'string',
                  'eTag': 'string'
              },
              'gitHubLocation': {
                  'repository': 'string',
                  'commitId': 'string'
              }
          }
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of the application that corresponds to the revision.

      

    
    :type revision: dict
    :param revision: **[REQUIRED]** 

      Information about the application revision to get, including type and location.

      

    
      - **revisionType** *(string) --* 

        The type of application revision:

         

         
        * S3: An application revision stored in Amazon S3.
         
        * GitHub: An application revision stored in GitHub.
         

        

      
      - **s3Location** *(dict) --* 

        Information about the location of application artifacts stored in Amazon S3.

        

      
        - **bucket** *(string) --* 

          The name of the Amazon S3 bucket where the application revision is stored.

          

        
        - **key** *(string) --* 

          The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

          

        
        - **bundleType** *(string) --* 

          The file type of the application revision. Must be one of the following:

           

           
          * tar: A tar archive file.
           
          * tgz: A compressed tar archive file.
           
          * zip: A zip archive file.
           

          

        
        - **version** *(string) --* 

          A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the version is not specified, the system will use the most recent version by default.

          

        
        - **eTag** *(string) --* 

          The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

          

        
      
      - **gitHubLocation** *(dict) --* 

        Information about the location of application artifacts stored in GitHub.

        

      
        - **repository** *(string) --* 

          The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

           

          Specified as account/repository.

          

        
        - **commitId** *(string) --* 

          The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

          

        
      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'applicationName': 'string',
            'revision': {
                'revisionType': 'S3'|'GitHub',
                's3Location': {
                    'bucket': 'string',
                    'key': 'string',
                    'bundleType': 'tar'|'tgz'|'zip',
                    'version': 'string',
                    'eTag': 'string'
                },
                'gitHubLocation': {
                    'repository': 'string',
                    'commitId': 'string'
                }
            },
            'revisionInfo': {
                'description': 'string',
                'deploymentGroups': [
                    'string',
                ],
                'firstUsedTime': datetime(2015, 1, 1),
                'lastUsedTime': datetime(2015, 1, 1),
                'registerTime': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get application revision operation.

        
        

        - **applicationName** *(string) --* 

          The name of the application that corresponds to the revision.

          
        

        - **revision** *(dict) --* 

          Additional information about the revision, including type and location.

          
          

          - **revisionType** *(string) --* 

            The type of application revision:

             

             
            * S3: An application revision stored in Amazon S3.
             
            * GitHub: An application revision stored in GitHub.
             

            
          

          - **s3Location** *(dict) --* 

            Information about the location of application artifacts stored in Amazon S3.

            
            

            - **bucket** *(string) --* 

              The name of the Amazon S3 bucket where the application revision is stored.

              
            

            - **key** *(string) --* 

              The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

              
            

            - **bundleType** *(string) --* 

              The file type of the application revision. Must be one of the following:

               

               
              * tar: A tar archive file.
               
              * tgz: A compressed tar archive file.
               
              * zip: A zip archive file.
               

              
            

            - **version** *(string) --* 

              A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

               

              If the version is not specified, the system will use the most recent version by default.

              
            

            - **eTag** *(string) --* 

              The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

               

              If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

              
        
          

          - **gitHubLocation** *(dict) --* 

            Information about the location of application artifacts stored in GitHub.

            
            

            - **repository** *(string) --* 

              The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

               

              Specified as account/repository.

              
            

            - **commitId** *(string) --* 

              The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

              
        
      
        

        - **revisionInfo** *(dict) --* 

          General information about the revision.

          
          

          - **description** *(string) --* 

            A comment about the revision.

            
          

          - **deploymentGroups** *(list) --* 

            The deployment groups for which this is the current target revision.

            
            

            - *(string) --* 
        
          

          - **firstUsedTime** *(datetime) --* 

            When the revision was first used by AWS CodeDeploy.

            
          

          - **lastUsedTime** *(datetime) --* 

            When the revision was last used by AWS CodeDeploy.

            
          

          - **registerTime** *(datetime) --* 

            When the revision was registered with AWS CodeDeploy.

            
      
    

  .. py:method:: get_deployment(**kwargs)

    

    Gets information about a deployment.

    

    **Request Syntax** 
    ::

      response = client.get_deployment(
          deploymentId='string'
      )
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      A deployment ID associated with the applicable IAM user or AWS account.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentInfo': {
                'applicationName': 'string',
                'deploymentGroupName': 'string',
                'deploymentConfigName': 'string',
                'deploymentId': 'string',
                'revision': {
                    'revisionType': 'S3'|'GitHub',
                    's3Location': {
                        'bucket': 'string',
                        'key': 'string',
                        'bundleType': 'tar'|'tgz'|'zip',
                        'version': 'string',
                        'eTag': 'string'
                    },
                    'gitHubLocation': {
                        'repository': 'string',
                        'commitId': 'string'
                    }
                },
                'status': 'Created'|'Queued'|'InProgress'|'Succeeded'|'Failed'|'Stopped',
                'errorInformation': {
                    'code': 'DEPLOYMENT_GROUP_MISSING'|'APPLICATION_MISSING'|'REVISION_MISSING'|'IAM_ROLE_MISSING'|'IAM_ROLE_PERMISSIONS'|'NO_EC2_SUBSCRIPTION'|'OVER_MAX_INSTANCES'|'NO_INSTANCES'|'TIMEOUT'|'HEALTH_CONSTRAINTS_INVALID'|'HEALTH_CONSTRAINTS'|'INTERNAL_ERROR'|'THROTTLED',
                    'message': 'string'
                },
                'createTime': datetime(2015, 1, 1),
                'startTime': datetime(2015, 1, 1),
                'completeTime': datetime(2015, 1, 1),
                'deploymentOverview': {
                    'Pending': 123,
                    'InProgress': 123,
                    'Succeeded': 123,
                    'Failed': 123,
                    'Skipped': 123
                },
                'description': 'string',
                'creator': 'user'|'autoscaling',
                'ignoreApplicationStopFailures': True|False
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get deployment operation.

        
        

        - **deploymentInfo** *(dict) --* 

          Information about the deployment.

          
          

          - **applicationName** *(string) --* 

            The application name.

            
          

          - **deploymentGroupName** *(string) --* 

            The deployment group name.

            
          

          - **deploymentConfigName** *(string) --* 

            The deployment configuration name.

            
          

          - **deploymentId** *(string) --* 

            The deployment ID.

            
          

          - **revision** *(dict) --* 

            Information about the location of stored application artifacts and the service from which to retrieve them.

            
            

            - **revisionType** *(string) --* 

              The type of application revision:

               

               
              * S3: An application revision stored in Amazon S3.
               
              * GitHub: An application revision stored in GitHub.
               

              
            

            - **s3Location** *(dict) --* 

              Information about the location of application artifacts stored in Amazon S3.

              
              

              - **bucket** *(string) --* 

                The name of the Amazon S3 bucket where the application revision is stored.

                
              

              - **key** *(string) --* 

                The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

                
              

              - **bundleType** *(string) --* 

                The file type of the application revision. Must be one of the following:

                 

                 
                * tar: A tar archive file.
                 
                * tgz: A compressed tar archive file.
                 
                * zip: A zip archive file.
                 

                
              

              - **version** *(string) --* 

                A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

                 

                If the version is not specified, the system will use the most recent version by default.

                
              

              - **eTag** *(string) --* 

                The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

                 

                If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

                
          
            

            - **gitHubLocation** *(dict) --* 

              Information about the location of application artifacts stored in GitHub.

              
              

              - **repository** *(string) --* 

                The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

                 

                Specified as account/repository.

                
              

              - **commitId** *(string) --* 

                The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

                
          
        
          

          - **status** *(string) --* 

            The current state of the deployment as a whole.

            
          

          - **errorInformation** *(dict) --* 

            Information about any error associated with this deployment.

            
            

            - **code** *(string) --* 

              The error code:

               

               
              * APPLICATION_MISSING: The application was missing. This error code will most likely be raised if the application is deleted after the deployment is created but before it is started.
               
              * DEPLOYMENT_GROUP_MISSING: The deployment group was missing. This error code will most likely be raised if the deployment group is deleted after the deployment is created but before it is started.
               
              * HEALTH_CONSTRAINTS: The deployment failed on too many instances to be successfully deployed within the instance health constraints specified.
               
              * HEALTH_CONSTRAINTS_INVALID: The revision cannot be successfully deployed within the instance health constraints specified.
               
              * IAM_ROLE_MISSING: The service role cannot be accessed.
               
              * IAM_ROLE_PERMISSIONS: The service role does not have the correct permissions.
               
              * INTERNAL_ERROR: There was an internal error.
               
              * NO_EC2_SUBSCRIPTION: The calling account is not subscribed to the Amazon EC2 service.
               
              * NO_INSTANCES: No instance were specified, or no instance can be found.
               
              * OVER_MAX_INSTANCES: The maximum number of instance was exceeded.
               
              * THROTTLED: The operation was throttled because the calling account exceeded the throttling limits of one or more AWS services.
               
              * TIMEOUT: The deployment has timed out.
               
              * REVISION_MISSING: The revision ID was missing. This error code will most likely be raised if the revision is deleted after the deployment is created but before it is started.
               

              
            

            - **message** *(string) --* 

              An accompanying error message.

              
        
          

          - **createTime** *(datetime) --* 

            A timestamp indicating when the deployment was created.

            
          

          - **startTime** *(datetime) --* 

            A timestamp indicating when the deployment was deployed to the deployment group.

             

            In some cases, the reported value of the start time may be later than the complete time. This is due to differences in the clock settings of back-end servers that participate in the deployment process.

            
          

          - **completeTime** *(datetime) --* 

            A timestamp indicating when the deployment was complete.

            
          

          - **deploymentOverview** *(dict) --* 

            A summary of the deployment status of the instances in the deployment.

            
            

            - **Pending** *(integer) --* 

              The number of instances in the deployment in a pending state.

              
            

            - **InProgress** *(integer) --* 

              The number of instances in which the deployment is in progress.

              
            

            - **Succeeded** *(integer) --* 

              The number of instances in the deployment to which revisions have been successfully deployed.

              
            

            - **Failed** *(integer) --* 

              The number of instances in the deployment in a failed state.

              
            

            - **Skipped** *(integer) --* 

              The number of instances in the deployment in a skipped state.

              
        
          

          - **description** *(string) --* 

            A comment about the deployment.

            
          

          - **creator** *(string) --* 

            The means by which the deployment was created:

             

             
            * user: A user created the deployment.
             
            * autoscaling: Auto Scaling created the deployment.
             

            
          

          - **ignoreApplicationStopFailures** *(boolean) --* 

            If true, then if the deployment causes the ApplicationStop deployment lifecycle event to an instance to fail, the deployment to that instance will not be considered to have failed at that point and will continue on to the BeforeInstall deployment lifecycle event.

             

            If false or not specified, then if the deployment causes the ApplicationStop deployment lifecycle event to an instance to fail, the deployment to that instance will stop, and the deployment to that instance will be considered to have failed.

            
      
    

  .. py:method:: get_deployment_config(**kwargs)

    

    Gets information about a deployment configuration.

    

    **Request Syntax** 
    ::

      response = client.get_deployment_config(
          deploymentConfigName='string'
      )
    :type deploymentConfigName: string
    :param deploymentConfigName: **[REQUIRED]** 

      The name of a deployment configuration associated with the applicable IAM user or AWS account.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentConfigInfo': {
                'deploymentConfigId': 'string',
                'deploymentConfigName': 'string',
                'minimumHealthyHosts': {
                    'value': 123,
                    'type': 'HOST_COUNT'|'FLEET_PERCENT'
                },
                'createTime': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get deployment configuration operation.

        
        

        - **deploymentConfigInfo** *(dict) --* 

          Information about the deployment configuration.

          
          

          - **deploymentConfigId** *(string) --* 

            The deployment configuration ID.

            
          

          - **deploymentConfigName** *(string) --* 

            The deployment configuration name.

            
          

          - **minimumHealthyHosts** *(dict) --* 

            Information about the number or percentage of minimum healthy instance.

            
            

            - **value** *(integer) --* 

              The minimum healthy instance value.

              
            

            - **type** *(string) --* 

              The minimum healthy instance type:

               

               
              * HOST_COUNT: The minimum number of healthy instance as an absolute value.
               
              * FLEET_PERCENT: The minimum number of healthy instance as a percentage of the total number of instance in the deployment.
               

               

              In an example of nine instance, if a HOST_COUNT of six is specified, deploy to up to three instances at a time. The deployment will be successful if six or more instances are deployed to successfully; otherwise, the deployment fails. If a FLEET_PERCENT of 40 is specified, deploy to up to five instance at a time. The deployment will be successful if four or more instance are deployed to successfully; otherwise, the deployment fails.

               

              .. note::

                In a call to the get deployment configuration operation, CodeDeployDefault.OneAtATime will return a minimum healthy instance type of MOST_CONCURRENCY and a value of 1. This means a deployment to only one instance at a time. (You cannot set the type to MOST_CONCURRENCY, only to HOST_COUNT or FLEET_PERCENT.) In addition, with CodeDeployDefault.OneAtATime, AWS CodeDeploy will try to ensure that all instances but one are kept in a healthy state during the deployment. Although this allows one instance at a time to be taken offline for a new deployment, it also means that if the deployment to the last instance fails, the overall deployment still succeeds.

              
        
          

          - **createTime** *(datetime) --* 

            The time at which the deployment configuration was created.

            
      
    

  .. py:method:: get_deployment_group(**kwargs)

    

    Gets information about a deployment group.

    

    **Request Syntax** 
    ::

      response = client.get_deployment_group(
          applicationName='string',
          deploymentGroupName='string'
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    :type deploymentGroupName: string
    :param deploymentGroupName: **[REQUIRED]** 

      The name of an existing deployment group for the specified application.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentGroupInfo': {
                'applicationName': 'string',
                'deploymentGroupId': 'string',
                'deploymentGroupName': 'string',
                'deploymentConfigName': 'string',
                'ec2TagFilters': [
                    {
                        'Key': 'string',
                        'Value': 'string',
                        'Type': 'KEY_ONLY'|'VALUE_ONLY'|'KEY_AND_VALUE'
                    },
                ],
                'onPremisesInstanceTagFilters': [
                    {
                        'Key': 'string',
                        'Value': 'string',
                        'Type': 'KEY_ONLY'|'VALUE_ONLY'|'KEY_AND_VALUE'
                    },
                ],
                'autoScalingGroups': [
                    {
                        'name': 'string',
                        'hook': 'string'
                    },
                ],
                'serviceRoleArn': 'string',
                'targetRevision': {
                    'revisionType': 'S3'|'GitHub',
                    's3Location': {
                        'bucket': 'string',
                        'key': 'string',
                        'bundleType': 'tar'|'tgz'|'zip',
                        'version': 'string',
                        'eTag': 'string'
                    },
                    'gitHubLocation': {
                        'repository': 'string',
                        'commitId': 'string'
                    }
                },
                'triggerConfigurations': [
                    {
                        'triggerName': 'string',
                        'triggerTargetArn': 'string',
                        'triggerEvents': [
                            'DeploymentStart'|'DeploymentSuccess'|'DeploymentFailure'|'DeploymentStop'|'InstanceStart'|'InstanceSuccess'|'InstanceFailure',
                        ]
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get deployment group operation.

        
        

        - **deploymentGroupInfo** *(dict) --* 

          Information about the deployment group.

          
          

          - **applicationName** *(string) --* 

            The application name.

            
          

          - **deploymentGroupId** *(string) --* 

            The deployment group ID.

            
          

          - **deploymentGroupName** *(string) --* 

            The deployment group name.

            
          

          - **deploymentConfigName** *(string) --* 

            The deployment configuration name.

            
          

          - **ec2TagFilters** *(list) --* 

            The Amazon EC2 tags on which to filter.

            
            

            - *(dict) --* 

              Information about a tag filter.

              
              

              - **Key** *(string) --* 

                The tag filter key.

                
              

              - **Value** *(string) --* 

                The tag filter value.

                
              

              - **Type** *(string) --* 

                The tag filter type:

                 

                 
                * KEY_ONLY: Key only.
                 
                * VALUE_ONLY: Value only.
                 
                * KEY_AND_VALUE: Key and value.
                 

                
          
        
          

          - **onPremisesInstanceTagFilters** *(list) --* 

            The on-premises instance tags on which to filter.

            
            

            - *(dict) --* 

              Information about an on-premises instance tag filter.

              
              

              - **Key** *(string) --* 

                The on-premises instance tag filter key.

                
              

              - **Value** *(string) --* 

                The on-premises instance tag filter value.

                
              

              - **Type** *(string) --* 

                The on-premises instance tag filter type:

                 

                 
                * KEY_ONLY: Key only.
                 
                * VALUE_ONLY: Value only.
                 
                * KEY_AND_VALUE: Key and value.
                 

                
          
        
          

          - **autoScalingGroups** *(list) --* 

            A list of associated Auto Scaling groups.

            
            

            - *(dict) --* 

              Information about an Auto Scaling group.

              
              

              - **name** *(string) --* 

                The Auto Scaling group name.

                
              

              - **hook** *(string) --* 

                An Auto Scaling lifecycle event hook name.

                
          
        
          

          - **serviceRoleArn** *(string) --* 

            A service role ARN.

            
          

          - **targetRevision** *(dict) --* 

            Information about the deployment group's target revision, including type and location.

            
            

            - **revisionType** *(string) --* 

              The type of application revision:

               

               
              * S3: An application revision stored in Amazon S3.
               
              * GitHub: An application revision stored in GitHub.
               

              
            

            - **s3Location** *(dict) --* 

              Information about the location of application artifacts stored in Amazon S3.

              
              

              - **bucket** *(string) --* 

                The name of the Amazon S3 bucket where the application revision is stored.

                
              

              - **key** *(string) --* 

                The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

                
              

              - **bundleType** *(string) --* 

                The file type of the application revision. Must be one of the following:

                 

                 
                * tar: A tar archive file.
                 
                * tgz: A compressed tar archive file.
                 
                * zip: A zip archive file.
                 

                
              

              - **version** *(string) --* 

                A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

                 

                If the version is not specified, the system will use the most recent version by default.

                
              

              - **eTag** *(string) --* 

                The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

                 

                If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

                
          
            

            - **gitHubLocation** *(dict) --* 

              Information about the location of application artifacts stored in GitHub.

              
              

              - **repository** *(string) --* 

                The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

                 

                Specified as account/repository.

                
              

              - **commitId** *(string) --* 

                The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

                
          
        
          

          - **triggerConfigurations** *(list) --* 

            A list of associated triggers. 

            
            

            - *(dict) --* 

              Information about notification triggers for the deployment group.

              
              

              - **triggerName** *(string) --* 

                The name of the notification trigger.

                
              

              - **triggerTargetArn** *(string) --* 

                The ARN of the Amazon Simple Notification Service topic through which notifications about deployment or instance events are sent.

                
              

              - **triggerEvents** *(list) --* 

                The event type or types for which notifications are triggered.

                 

                The following event type values are supported:

                 

                 
                * DEPLOYMENT_START
                 
                * DEPLOYMENT_SUCCESS
                 
                * DEPLOYMENT_FAILURE
                 
                * DEPLOYMENT_STOP
                 
                * INSTANCE_START
                 
                * INSTANCE_SUCCESS
                 
                * INSTANCE_FAILURE
                 

                
                

                - *(string) --* 
            
          
        
      
    

  .. py:method:: get_deployment_instance(**kwargs)

    

    Gets information about an instance as part of a deployment.

    

    **Request Syntax** 
    ::

      response = client.get_deployment_instance(
          deploymentId='string',
          instanceId='string'
      )
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      The unique ID of a deployment.

      

    
    :type instanceId: string
    :param instanceId: **[REQUIRED]** 

      The unique ID of an instance in the deployment group.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'instanceSummary': {
                'deploymentId': 'string',
                'instanceId': 'string',
                'status': 'Pending'|'InProgress'|'Succeeded'|'Failed'|'Skipped'|'Unknown',
                'lastUpdatedAt': datetime(2015, 1, 1),
                'lifecycleEvents': [
                    {
                        'lifecycleEventName': 'string',
                        'diagnostics': {
                            'errorCode': 'Success'|'ScriptMissing'|'ScriptNotExecutable'|'ScriptTimedOut'|'ScriptFailed'|'UnknownError',
                            'scriptName': 'string',
                            'message': 'string',
                            'logTail': 'string'
                        },
                        'startTime': datetime(2015, 1, 1),
                        'endTime': datetime(2015, 1, 1),
                        'status': 'Pending'|'InProgress'|'Succeeded'|'Failed'|'Skipped'|'Unknown'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get deployment instance operation.

        
        

        - **instanceSummary** *(dict) --* 

          Information about the instance.

          
          

          - **deploymentId** *(string) --* 

            The deployment ID.

            
          

          - **instanceId** *(string) --* 

            The instance ID.

            
          

          - **status** *(string) --* 

            The deployment status for this instance:

             

             
            * Pending: The deployment is pending for this instance.
             
            * In Progress: The deployment is in progress for this instance.
             
            * Succeeded: The deployment has succeeded for this instance.
             
            * Failed: The deployment has failed for this instance.
             
            * Skipped: The deployment has been skipped for this instance.
             
            * Unknown: The deployment status is unknown for this instance.
             

            
          

          - **lastUpdatedAt** *(datetime) --* 

            A timestamp indicating when the instance information was last updated.

            
          

          - **lifecycleEvents** *(list) --* 

            A list of lifecycle events for this instance.

            
            

            - *(dict) --* 

              Information about a deployment lifecycle event.

              
              

              - **lifecycleEventName** *(string) --* 

                The deployment lifecycle event name, such as ApplicationStop, BeforeInstall, AfterInstall, ApplicationStart, or ValidateService.

                
              

              - **diagnostics** *(dict) --* 

                Diagnostic information about the deployment lifecycle event.

                
                

                - **errorCode** *(string) --* 

                  The associated error code:

                   

                   
                  * Success: The specified script ran.
                   
                  * ScriptMissing: The specified script was not found in the specified location.
                   
                  * ScriptNotExecutable: The specified script is not a recognized executable file type.
                   
                  * ScriptTimedOut: The specified script did not finish running in the specified time period.
                   
                  * ScriptFailed: The specified script failed to run as expected.
                   
                  * UnknownError: The specified script did not run for an unknown reason.
                   

                  
                

                - **scriptName** *(string) --* 

                  The name of the script.

                  
                

                - **message** *(string) --* 

                  The message associated with the error.

                  
                

                - **logTail** *(string) --* 

                  The last portion of the diagnostic log.

                   

                  If available, AWS CodeDeploy returns up to the last 4 KB of the diagnostic log.

                  
            
              

              - **startTime** *(datetime) --* 

                A timestamp indicating when the deployment lifecycle event started.

                
              

              - **endTime** *(datetime) --* 

                A timestamp indicating when the deployment lifecycle event ended.

                
              

              - **status** *(string) --* 

                The deployment lifecycle event status:

                 

                 
                * Pending: The deployment lifecycle event is pending.
                 
                * InProgress: The deployment lifecycle event is in progress.
                 
                * Succeeded: The deployment lifecycle event ran successfully.
                 
                * Failed: The deployment lifecycle event has failed.
                 
                * Skipped: The deployment lifecycle event has been skipped.
                 
                * Unknown: The deployment lifecycle event is unknown.
                 

                
          
        
      
    

  .. py:method:: get_on_premises_instance(**kwargs)

    

    Gets information about an on-premises instance.

    

    **Request Syntax** 
    ::

      response = client.get_on_premises_instance(
          instanceName='string'
      )
    :type instanceName: string
    :param instanceName: **[REQUIRED]** 

      The name of the on-premises instance about which to get information.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'instanceInfo': {
                'instanceName': 'string',
                'iamUserArn': 'string',
                'instanceArn': 'string',
                'registerTime': datetime(2015, 1, 1),
                'deregisterTime': datetime(2015, 1, 1),
                'tags': [
                    {
                        'Key': 'string',
                        'Value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get on-premises instance operation.

        
        

        - **instanceInfo** *(dict) --* 

          Information about the on-premises instance.

          
          

          - **instanceName** *(string) --* 

            The name of the on-premises instance.

            
          

          - **iamUserArn** *(string) --* 

            The IAM user ARN associated with the on-premises instance.

            
          

          - **instanceArn** *(string) --* 

            The ARN of the on-premises instance.

            
          

          - **registerTime** *(datetime) --* 

            The time at which the on-premises instance was registered.

            
          

          - **deregisterTime** *(datetime) --* 

            If the on-premises instance was deregistered, the time at which the on-premises instance was deregistered.

            
          

          - **tags** *(list) --* 

            The tags currently associated with the on-premises instance.

            
            

            - *(dict) --* 

              Information about a tag.

              
              

              - **Key** *(string) --* 

                The tag's key.

                
              

              - **Value** *(string) --* 

                The tag's value.

                
          
        
      
    

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

        


  .. py:method:: list_application_revisions(**kwargs)

    

    Lists information about revisions for an application.

    

    **Request Syntax** 
    ::

      response = client.list_application_revisions(
          applicationName='string',
          sortBy='registerTime'|'firstUsedTime'|'lastUsedTime',
          sortOrder='ascending'|'descending',
          s3Bucket='string',
          s3KeyPrefix='string',
          deployed='include'|'exclude'|'ignore',
          nextToken='string'
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    :type sortBy: string
    :param sortBy: 

      The column name to use to sort the list results:

       

       
      * registerTime: Sort by the time the revisions were registered with AWS CodeDeploy.
       
      * firstUsedTime: Sort by the time the revisions were first used in a deployment.
       
      * lastUsedTime: Sort by the time the revisions were last used in a deployment.
       

       

      If not specified or set to null, the results will be returned in an arbitrary order.

      

    
    :type sortOrder: string
    :param sortOrder: 

      The order in which to sort the list results:

       

       
      * ascending: ascending order.
       
      * descending: descending order.
       

       

      If not specified, the results will be sorted in ascending order.

       

      If set to null, the results will be sorted in an arbitrary order.

      

    
    :type s3Bucket: string
    :param s3Bucket: 

      An Amazon S3 bucket name to limit the search for revisions.

       

      If set to null, all of the user's buckets will be searched.

      

    
    :type s3KeyPrefix: string
    :param s3KeyPrefix: 

      A key prefix for the set of Amazon S3 objects to limit the search for revisions.

      

    
    :type deployed: string
    :param deployed: 

      Whether to list revisions based on whether the revision is the target revision of an deployment group:

       

       
      * include: List revisions that are target revisions of a deployment group.
       
      * exclude: Do not list revisions that are target revisions of a deployment group.
       
      * ignore: List all revisions.
       

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier returned from the previous list application revisions call. It can be used to return the next set of applications in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'revisions': [
                {
                    'revisionType': 'S3'|'GitHub',
                    's3Location': {
                        'bucket': 'string',
                        'key': 'string',
                        'bundleType': 'tar'|'tgz'|'zip',
                        'version': 'string',
                        'eTag': 'string'
                    },
                    'gitHubLocation': {
                        'repository': 'string',
                        'commitId': 'string'
                    }
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list application revisions operation.

        
        

        - **revisions** *(list) --* 

          A list of locations that contain the matching revisions.

          
          

          - *(dict) --* 

            Information about the location of an application revision.

            
            

            - **revisionType** *(string) --* 

              The type of application revision:

               

               
              * S3: An application revision stored in Amazon S3.
               
              * GitHub: An application revision stored in GitHub.
               

              
            

            - **s3Location** *(dict) --* 

              Information about the location of application artifacts stored in Amazon S3.

              
              

              - **bucket** *(string) --* 

                The name of the Amazon S3 bucket where the application revision is stored.

                
              

              - **key** *(string) --* 

                The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

                
              

              - **bundleType** *(string) --* 

                The file type of the application revision. Must be one of the following:

                 

                 
                * tar: A tar archive file.
                 
                * tgz: A compressed tar archive file.
                 
                * zip: A zip archive file.
                 

                
              

              - **version** *(string) --* 

                A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

                 

                If the version is not specified, the system will use the most recent version by default.

                
              

              - **eTag** *(string) --* 

                The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

                 

                If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

                
          
            

            - **gitHubLocation** *(dict) --* 

              Information about the location of application artifacts stored in GitHub.

              
              

              - **repository** *(string) --* 

                The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

                 

                Specified as account/repository.

                
              

              - **commitId** *(string) --* 

                The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

                
          
        
      
        

        - **nextToken** *(string) --* 

          If a large amount of information is returned, an identifier will also be returned. It can be used in a subsequent list application revisions call to return the next set of application revisions in the list.

          
    

  .. py:method:: list_applications(**kwargs)

    

    Lists the applications registered with the applicable IAM user or AWS account.

    

    **Request Syntax** 
    ::

      response = client.list_applications(
          nextToken='string'
      )
    :type nextToken: string
    :param nextToken: 

      An identifier returned from the previous list applications call. It can be used to return the next set of applications in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'applications': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list applications operation.

        
        

        - **applications** *(list) --* 

          A list of application names.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list applications call to return the next set of applications, will also be returned. in the list.

          
    

  .. py:method:: list_deployment_configs(**kwargs)

    

    Lists the deployment configurations with the applicable IAM user or AWS account.

    

    **Request Syntax** 
    ::

      response = client.list_deployment_configs(
          nextToken='string'
      )
    :type nextToken: string
    :param nextToken: 

      An identifier returned from the previous list deployment configurations call. It can be used to return the next set of deployment configurations in the list. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentConfigsList': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list deployment configurations operation.

        
        

        - **deploymentConfigsList** *(list) --* 

          A list of deployment configurations, including built-in configurations such as CodeDeployDefault.OneAtATime.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list deployment configurations call to return the next set of deployment configurations in the list.

          
    

  .. py:method:: list_deployment_groups(**kwargs)

    

    Lists the deployment groups for an application registered with the applicable IAM user or AWS account.

    

    **Request Syntax** 
    ::

      response = client.list_deployment_groups(
          applicationName='string',
          nextToken='string'
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier returned from the previous list deployment groups call. It can be used to return the next set of deployment groups in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'applicationName': 'string',
            'deploymentGroups': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list deployment groups operation.

        
        

        - **applicationName** *(string) --* 

          The application name.

          
        

        - **deploymentGroups** *(list) --* 

          A list of corresponding deployment group names.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list deployment groups call to return the next set of deployment groups in the list.

          
    

  .. py:method:: list_deployment_instances(**kwargs)

    

    Lists the instance for a deployment associated with the applicable IAM user or AWS account.

    

    **Request Syntax** 
    ::

      response = client.list_deployment_instances(
          deploymentId='string',
          nextToken='string',
          instanceStatusFilter=[
              'Pending'|'InProgress'|'Succeeded'|'Failed'|'Skipped'|'Unknown',
          ]
      )
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      The unique ID of a deployment.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier returned from the previous list deployment instances call. It can be used to return the next set of deployment instances in the list.

      

    
    :type instanceStatusFilter: list
    :param instanceStatusFilter: 

      A subset of instances to list by status:

       

       
      * Pending: Include those instance with pending deployments.
       
      * InProgress: Include those instance where deployments are still in progress.
       
      * Succeeded: Include those instances with successful deployments.
       
      * Failed: Include those instance with failed deployments.
       
      * Skipped: Include those instance with skipped deployments.
       
      * Unknown: Include those instance with deployments in an unknown state.
       

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'instancesList': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list deployment instances operation.

        
        

        - **instancesList** *(list) --* 

          A list of instance IDs.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list deployment instances call to return the next set of deployment instances in the list.

          
    

  .. py:method:: list_deployments(**kwargs)

    

    Lists the deployments in a deployment group for an application registered with the applicable IAM user or AWS account.

    

    **Request Syntax** 
    ::

      response = client.list_deployments(
          applicationName='string',
          deploymentGroupName='string',
          includeOnlyStatuses=[
              'Created'|'Queued'|'InProgress'|'Succeeded'|'Failed'|'Stopped',
          ],
          createTimeRange={
              'start': datetime(2015, 1, 1),
              'end': datetime(2015, 1, 1)
          },
          nextToken='string'
      )
    :type applicationName: string
    :param applicationName: 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    :type deploymentGroupName: string
    :param deploymentGroupName: 

      The name of an existing deployment group for the specified application.

      

    
    :type includeOnlyStatuses: list
    :param includeOnlyStatuses: 

      A subset of deployments to list by status:

       

       
      * Created: Include created deployments in the resulting list.
       
      * Queued: Include queued deployments in the resulting list.
       
      * In Progress: Include in-progress deployments in the resulting list.
       
      * Succeeded: Include successful deployments in the resulting list.
       
      * Failed: Include failed deployments in the resulting list.
       
      * Stopped: Include stopped deployments in the resulting list.
       

      

    
      - *(string) --* 

      
  
    :type createTimeRange: dict
    :param createTimeRange: 

      A time range (start and end) for returning a subset of the list of deployments.

      

    
      - **start** *(datetime) --* 

        The start time of the time range.

         

        .. note::

          Specify null to leave the start time open-ended.

        

      
      - **end** *(datetime) --* 

        The end time of the time range.

         

        .. note::

          Specify null to leave the end time open-ended.

        

      
    
    :type nextToken: string
    :param nextToken: 

      An identifier returned from the previous list deployments call. It can be used to return the next set of deployments in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deployments': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list deployments operation.

        
        

        - **deployments** *(list) --* 

          A list of deployment IDs.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list deployments call to return the next set of deployments in the list.

          
    

  .. py:method:: list_on_premises_instances(**kwargs)

    

    Gets a list of names for one or more on-premises instances.

     

    Unless otherwise specified, both registered and deregistered on-premises instance names will be listed. To list only registered or deregistered on-premises instance names, use the registration status parameter.

    

    **Request Syntax** 
    ::

      response = client.list_on_premises_instances(
          registrationStatus='Registered'|'Deregistered',
          tagFilters=[
              {
                  'Key': 'string',
                  'Value': 'string',
                  'Type': 'KEY_ONLY'|'VALUE_ONLY'|'KEY_AND_VALUE'
              },
          ],
          nextToken='string'
      )
    :type registrationStatus: string
    :param registrationStatus: 

      The registration status of the on-premises instances:

       

       
      * Deregistered: Include deregistered on-premises instances in the resulting list.
       
      * Registered: Include registered on-premises instances in the resulting list.
       

      

    
    :type tagFilters: list
    :param tagFilters: 

      The on-premises instance tags that will be used to restrict the corresponding on-premises instance names returned.

      

    
      - *(dict) --* 

        Information about an on-premises instance tag filter.

        

      
        - **Key** *(string) --* 

          The on-premises instance tag filter key.

          

        
        - **Value** *(string) --* 

          The on-premises instance tag filter value.

          

        
        - **Type** *(string) --* 

          The on-premises instance tag filter type:

           

           
          * KEY_ONLY: Key only.
           
          * VALUE_ONLY: Value only.
           
          * KEY_AND_VALUE: Key and value.
           

          

        
      
  
    :type nextToken: string
    :param nextToken: 

      An identifier returned from the previous list on-premises instances call. It can be used to return the next set of on-premises instances in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'instanceNames': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of list on-premises instances operation.

        
        

        - **instanceNames** *(list) --* 

          The list of matching on-premises instance names.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list on-premises instances call to return the next set of on-premises instances in the list.

          
    

  .. py:method:: register_application_revision(**kwargs)

    

    Registers with AWS CodeDeploy a revision for the specified application.

    

    **Request Syntax** 
    ::

      response = client.register_application_revision(
          applicationName='string',
          description='string',
          revision={
              'revisionType': 'S3'|'GitHub',
              's3Location': {
                  'bucket': 'string',
                  'key': 'string',
                  'bundleType': 'tar'|'tgz'|'zip',
                  'version': 'string',
                  'eTag': 'string'
              },
              'gitHubLocation': {
                  'repository': 'string',
                  'commitId': 'string'
              }
          }
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

      

    
    :type description: string
    :param description: 

      A comment about the revision.

      

    
    :type revision: dict
    :param revision: **[REQUIRED]** 

      Information about the application revision to register, including type and location.

      

    
      - **revisionType** *(string) --* 

        The type of application revision:

         

         
        * S3: An application revision stored in Amazon S3.
         
        * GitHub: An application revision stored in GitHub.
         

        

      
      - **s3Location** *(dict) --* 

        Information about the location of application artifacts stored in Amazon S3.

        

      
        - **bucket** *(string) --* 

          The name of the Amazon S3 bucket where the application revision is stored.

          

        
        - **key** *(string) --* 

          The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

          

        
        - **bundleType** *(string) --* 

          The file type of the application revision. Must be one of the following:

           

           
          * tar: A tar archive file.
           
          * tgz: A compressed tar archive file.
           
          * zip: A zip archive file.
           

          

        
        - **version** *(string) --* 

          A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the version is not specified, the system will use the most recent version by default.

          

        
        - **eTag** *(string) --* 

          The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

          

        
      
      - **gitHubLocation** *(dict) --* 

        Information about the location of application artifacts stored in GitHub.

        

      
        - **repository** *(string) --* 

          The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

           

          Specified as account/repository.

          

        
        - **commitId** *(string) --* 

          The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

          

        
      
    
    
    :returns: None

  .. py:method:: register_on_premises_instance(**kwargs)

    

    Registers an on-premises instance.

    

    **Request Syntax** 
    ::

      response = client.register_on_premises_instance(
          instanceName='string',
          iamUserArn='string'
      )
    :type instanceName: string
    :param instanceName: **[REQUIRED]** 

      The name of the on-premises instance to register.

      

    
    :type iamUserArn: string
    :param iamUserArn: **[REQUIRED]** 

      The ARN of the IAM user to associate with the on-premises instance.

      

    
    
    :returns: None

  .. py:method:: remove_tags_from_on_premises_instances(**kwargs)

    

    Removes one or more tags from one or more on-premises instances.

    

    **Request Syntax** 
    ::

      response = client.remove_tags_from_on_premises_instances(
          tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          instanceNames=[
              'string',
          ]
      )
    :type tags: list
    :param tags: **[REQUIRED]** 

      The tag key-value pairs to remove from the on-premises instances.

      

    
      - *(dict) --* 

        Information about a tag.

        

      
        - **Key** *(string) --* 

          The tag's key.

          

        
        - **Value** *(string) --* 

          The tag's value.

          

        
      
  
    :type instanceNames: list
    :param instanceNames: **[REQUIRED]** 

      The names of the on-premises instances from which to remove tags.

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: stop_deployment(**kwargs)

    

    Attempts to stop an ongoing deployment.

    

    **Request Syntax** 
    ::

      response = client.stop_deployment(
          deploymentId='string'
      )
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      The unique ID of a deployment.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'status': 'Pending'|'Succeeded',
            'statusMessage': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a stop deployment operation.

        
        

        - **status** *(string) --* 

          The status of the stop deployment operation:

           

           
          * Pending: The stop operation is pending.
           
          * Succeeded: The stop operation was successful.
           

          
        

        - **statusMessage** *(string) --* 

          An accompanying status message.

          
    

  .. py:method:: update_application(**kwargs)

    

    Changes the name of an application.

    

    **Request Syntax** 
    ::

      response = client.update_application(
          applicationName='string',
          newApplicationName='string'
      )
    :type applicationName: string
    :param applicationName: 

      The current name of the application you want to change.

      

    
    :type newApplicationName: string
    :param newApplicationName: 

      The new name to give the application.

      

    
    
    :returns: None

  .. py:method:: update_deployment_group(**kwargs)

    

    Changes information about a deployment group.

    

    **Request Syntax** 
    ::

      response = client.update_deployment_group(
          applicationName='string',
          currentDeploymentGroupName='string',
          newDeploymentGroupName='string',
          deploymentConfigName='string',
          ec2TagFilters=[
              {
                  'Key': 'string',
                  'Value': 'string',
                  'Type': 'KEY_ONLY'|'VALUE_ONLY'|'KEY_AND_VALUE'
              },
          ],
          onPremisesInstanceTagFilters=[
              {
                  'Key': 'string',
                  'Value': 'string',
                  'Type': 'KEY_ONLY'|'VALUE_ONLY'|'KEY_AND_VALUE'
              },
          ],
          autoScalingGroups=[
              'string',
          ],
          serviceRoleArn='string',
          triggerConfigurations=[
              {
                  'triggerName': 'string',
                  'triggerTargetArn': 'string',
                  'triggerEvents': [
                      'DeploymentStart'|'DeploymentSuccess'|'DeploymentFailure'|'DeploymentStop'|'InstanceStart'|'InstanceSuccess'|'InstanceFailure',
                  ]
              },
          ]
      )
    :type applicationName: string
    :param applicationName: **[REQUIRED]** 

      The application name corresponding to the deployment group to update.

      

    
    :type currentDeploymentGroupName: string
    :param currentDeploymentGroupName: **[REQUIRED]** 

      The current name of the deployment group.

      

    
    :type newDeploymentGroupName: string
    :param newDeploymentGroupName: 

      The new name of the deployment group, if you want to change it.

      

    
    :type deploymentConfigName: string
    :param deploymentConfigName: 

      The replacement deployment configuration name to use, if you want to change it.

      

    
    :type ec2TagFilters: list
    :param ec2TagFilters: 

      The replacement set of Amazon EC2 tags on which to filter, if you want to change them. To keep the existing tags, enter their names. To remove tags, do not enter any tag names.

      

    
      - *(dict) --* 

        Information about a tag filter.

        

      
        - **Key** *(string) --* 

          The tag filter key.

          

        
        - **Value** *(string) --* 

          The tag filter value.

          

        
        - **Type** *(string) --* 

          The tag filter type:

           

           
          * KEY_ONLY: Key only.
           
          * VALUE_ONLY: Value only.
           
          * KEY_AND_VALUE: Key and value.
           

          

        
      
  
    :type onPremisesInstanceTagFilters: list
    :param onPremisesInstanceTagFilters: 

      The replacement set of on-premises instance tags on which to filter, if you want to change them. To keep the existing tags, enter their names. To remove tags, do not enter any tag names.

      

    
      - *(dict) --* 

        Information about an on-premises instance tag filter.

        

      
        - **Key** *(string) --* 

          The on-premises instance tag filter key.

          

        
        - **Value** *(string) --* 

          The on-premises instance tag filter value.

          

        
        - **Type** *(string) --* 

          The on-premises instance tag filter type:

           

           
          * KEY_ONLY: Key only.
           
          * VALUE_ONLY: Value only.
           
          * KEY_AND_VALUE: Key and value.
           

          

        
      
  
    :type autoScalingGroups: list
    :param autoScalingGroups: 

      The replacement list of Auto Scaling groups to be included in the deployment group, if you want to change them. To keep the Auto Scaling groups, enter their names. To remove Auto Scaling groups, do not enter any Auto Scaling group names.

      

    
      - *(string) --* 

      
  
    :type serviceRoleArn: string
    :param serviceRoleArn: 

      A replacement ARN for the service role, if you want to change it.

      

    
    :type triggerConfigurations: list
    :param triggerConfigurations: 

      Information about triggers to change when the deployment group is updated.

      

    
      - *(dict) --* 

        Information about notification triggers for the deployment group.

        

      
        - **triggerName** *(string) --* 

          The name of the notification trigger.

          

        
        - **triggerTargetArn** *(string) --* 

          The ARN of the Amazon Simple Notification Service topic through which notifications about deployment or instance events are sent.

          

        
        - **triggerEvents** *(list) --* 

          The event type or types for which notifications are triggered.

           

          The following event type values are supported:

           

           
          * DEPLOYMENT_START
           
          * DEPLOYMENT_SUCCESS
           
          * DEPLOYMENT_FAILURE
           
          * DEPLOYMENT_STOP
           
          * INSTANCE_START
           
          * INSTANCE_SUCCESS
           
          * INSTANCE_FAILURE
           

          

        
          - *(string) --* 

          
      
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'hooksNotCleanedUp': [
                {
                    'name': 'string',
                    'hook': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of an update deployment group operation.

        
        

        - **hooksNotCleanedUp** *(list) --* 

          If the output contains no data, and the corresponding deployment group contained at least one Auto Scaling group, AWS CodeDeploy successfully removed all corresponding Auto Scaling lifecycle event hooks from the AWS account. If the output contains data, AWS CodeDeploy could not remove some Auto Scaling lifecycle event hooks from the AWS account.

          
          

          - *(dict) --* 

            Information about an Auto Scaling group.

            
            

            - **name** *(string) --* 

              The Auto Scaling group name.

              
            

            - **hook** *(string) --* 

              An Auto Scaling lifecycle event hook name.

              
        
      
    

=======
Waiters
=======


The available waiters are:

* :py:class:`CodeDeploy.Waiter.DeploymentSuccessful`



.. py:class:: CodeDeploy.Waiter.DeploymentSuccessful

  ::

    
    waiter = client.get_waiter('deployment_successful')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`CodeDeploy.Client.get_deployment` every 15 seconds until a successful state is reached. An error is returned after 120 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          deploymentId='string'
      )
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      A deployment ID associated with the applicable IAM user or AWS account.

      

    
    
    :returns: None