

.. _Tagging Your Amazon EC2 Resources: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html
.. _Setting Up Managed Instances (Linux): http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/managed-instances.html
.. _Setting Up Managed Instances (Windows): http://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/managed-instances.html
.. _Monitoring Commands: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitor-commands.html


***
SSM
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: SSM.Client

  A low-level client representing Amazon Simple Systems Management Service (SSM)::

    
    import boto3
    
    client = boto3.client('ssm')

  
  These are the available methods:
  
  *   :py:meth:`add_tags_to_resource`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`cancel_command`

  
  *   :py:meth:`create_activation`

  
  *   :py:meth:`create_association`

  
  *   :py:meth:`create_association_batch`

  
  *   :py:meth:`create_document`

  
  *   :py:meth:`delete_activation`

  
  *   :py:meth:`delete_association`

  
  *   :py:meth:`delete_document`

  
  *   :py:meth:`deregister_managed_instance`

  
  *   :py:meth:`describe_activations`

  
  *   :py:meth:`describe_association`

  
  *   :py:meth:`describe_document`

  
  *   :py:meth:`describe_document_permission`

  
  *   :py:meth:`describe_instance_information`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_document`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_associations`

  
  *   :py:meth:`list_command_invocations`

  
  *   :py:meth:`list_commands`

  
  *   :py:meth:`list_documents`

  
  *   :py:meth:`list_tags_for_resource`

  
  *   :py:meth:`modify_document_permission`

  
  *   :py:meth:`remove_tags_from_resource`

  
  *   :py:meth:`send_command`

  
  *   :py:meth:`update_association_status`

  
  *   :py:meth:`update_managed_instance_role`

  

  .. py:method:: add_tags_to_resource(**kwargs)

    

    Adds or overwrites one or more tags for the specified resource. Tags are metadata that you assign to your managed instances. Tags enable you to categorize your managed instances in different ways, for example, by purpose, owner, or environment. Each tag consists of a key and an optional value, both of which you define. For example, you could define a set of tags for your account's managed instances that helps you track each instance's owner and stack level. For example: Key=Owner and Value=DbAdmin, SysAdmin, or Dev. Or Key=Stack and Value=Production, Pre-Production, or Test. Each resource can have a maximum of 10 tags. 

     

    We recommend that you devise a set of tag keys that meets your needs for each resource type. Using a consistent set of tag keys makes it easier for you to manage your resources. You can search and filter the resources based on the tags you add. Tags don't have any semantic meaning to Amazon EC2 and are interpreted strictly as a string of characters. 

     

    For more information about tags, see `Tagging Your Amazon EC2 Resources`_ in the Amazon EC2 User Guide. 

    

    **Request Syntax** 
    ::

      response = client.add_tags_to_resource(
          ResourceType='ManagedInstance',
          ResourceId='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type ResourceType: string
    :param ResourceType: **[REQUIRED]** 

      Specifies the type of resource you are tagging.

      

    
    :type ResourceId: string
    :param ResourceId: **[REQUIRED]** 

      The resource ID you want to tag.

      

    
    :type Tags: list
    :param Tags: **[REQUIRED]** 

      One or more tags. The value parameter is required, but if you don't want the tag to have a value, specify the parameter with no value, and we set the value to an empty string. 

      

    
      - *(dict) --* 

        Metadata that you assign to your managed instances. Tags enable you to categorize your managed instances in different ways, for example, by purpose, owner, or environment.

        

      
        - **Key** *(string) --* **[REQUIRED]** 

          The name of the tag.

          

        
        - **Value** *(string) --* **[REQUIRED]** 

          The value of the tag.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

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


  .. py:method:: cancel_command(**kwargs)

    

    Attempts to cancel the command specified by the Command ID. There is no guarantee that the command will be terminated and the underlying process stopped.

    

    **Request Syntax** 
    ::

      response = client.cancel_command(
          CommandId='string',
          InstanceIds=[
              'string',
          ]
      )
    :type CommandId: string
    :param CommandId: **[REQUIRED]** 

      The ID of the command you want to cancel.

      

    
    :type InstanceIds: list
    :param InstanceIds: 

      (Optional) A list of instance IDs on which you want to cancel the command. If not provided, the command is canceled on every instance on which it was requested.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Whether or not the command was successfully canceled. There is no guarantee that a request can be canceled.

        
    

  .. py:method:: create_activation(**kwargs)

    

    Registers your on-premises server or virtual machine with Amazon EC2 so that you can manage these resources using Run Command. An on-premises server or virtual machine that has been registered with EC2 is called a managed instance. For more information about activations, see `Setting Up Managed Instances (Linux)`_ or `Setting Up Managed Instances (Windows)`_ in the Amazon EC2 User Guide. 

    

    **Request Syntax** 
    ::

      response = client.create_activation(
          Description='string',
          DefaultInstanceName='string',
          IamRole='string',
          RegistrationLimit=123,
          ExpirationDate=datetime(2015, 1, 1)
      )
    :type Description: string
    :param Description: 

      A user-defined description of the resource that you want to register with Amazon EC2. 

      

    
    :type DefaultInstanceName: string
    :param DefaultInstanceName: 

      The name of the registered, managed instance as it will appear in the Amazon EC2 console or when you use the AWS command line tools to list EC2 resources.

      

    
    :type IamRole: string
    :param IamRole: **[REQUIRED]** 

      The Amazon Identity and Access Management (IAM) role that you want to assign to the managed instance. 

      

    
    :type RegistrationLimit: integer
    :param RegistrationLimit: 

      Specify the maximum number of managed instances you want to register. The default value is 1 instance.

      

    
    :type ExpirationDate: datetime
    :param ExpirationDate: 

      The date by which this activation request should expire. The default value is 24 hours.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ActivationId': 'string',
            'ActivationCode': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ActivationId** *(string) --* 

          The ID number generated by the system when it processed the activation. The activation ID functions like a user name.

          
        

        - **ActivationCode** *(string) --* 

          The code the system generates when it processes the activation. The activation code functions like a password to validate the activation ID. 

          
    

  .. py:method:: create_association(**kwargs)

    

    Associates the specified SSM document with the specified instance.

     

    When you associate an SSM document with an instance, the configuration agent on the instance (SSM agent for Linux and EC2Config service for Windows) processes the document and configures the instance as specified.

     

    If you associate a document with an instance that already has an associated document, the system throws the AssociationAlreadyExists exception.

    

    **Request Syntax** 
    ::

      response = client.create_association(
          Name='string',
          InstanceId='string',
          Parameters={
              'string': [
                  'string',
              ]
          }
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the SSM document.

      

    
    :type InstanceId: string
    :param InstanceId: **[REQUIRED]** 

      The instance ID.

      

    
    :type Parameters: dict
    :param Parameters: 

      The parameters for the documents runtime configuration. 

      

    
      - *(string) --* 

      
        - *(list) --* 

        
          - *(string) --* 

          
      
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AssociationDescription': {
                'Name': 'string',
                'InstanceId': 'string',
                'Date': datetime(2015, 1, 1),
                'Status': {
                    'Date': datetime(2015, 1, 1),
                    'Name': 'Pending'|'Success'|'Failed',
                    'Message': 'string',
                    'AdditionalInfo': 'string'
                },
                'Parameters': {
                    'string': [
                        'string',
                    ]
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **AssociationDescription** *(dict) --* 

          Information about the association.

          
          

          - **Name** *(string) --* 

            The name of the SSM document.

            
          

          - **InstanceId** *(string) --* 

            The ID of the instance.

            
          

          - **Date** *(datetime) --* 

            The date when the association was made.

            
          

          - **Status** *(dict) --* 

            The association status.

            
            

            - **Date** *(datetime) --* 

              The date when the status changed.

              
            

            - **Name** *(string) --* 

              The status.

              
            

            - **Message** *(string) --* 

              The reason for the status.

              
            

            - **AdditionalInfo** *(string) --* 

              A user-defined string.

              
        
          

          - **Parameters** *(dict) --* 

            A description of the parameters for a document. 

            
            

            - *(string) --* 
              

              - *(list) --* 
                

                - *(string) --* 
            
        
      
      
    

  .. py:method:: create_association_batch(**kwargs)

    

    Associates the specified SSM document with the specified instances.

     

    When you associate an SSM document with an instance, the configuration agent on the instance (SSM agent for Linux and EC2Config service for Windows) processes the document and configures the instance as specified.

     

    If you associate a document with an instance that already has an associated document, the system throws the AssociationAlreadyExists exception.

    

    **Request Syntax** 
    ::

      response = client.create_association_batch(
          Entries=[
              {
                  'Name': 'string',
                  'InstanceId': 'string',
                  'Parameters': {
                      'string': [
                          'string',
                      ]
                  }
              },
          ]
      )
    :type Entries: list
    :param Entries: **[REQUIRED]** 

      One or more associations.

      

    
      - *(dict) --* 

        Describes the association of an SSM document and an instance. 

        

      
        - **Name** *(string) --* 

          The name of the configuration document. 

          

        
        - **InstanceId** *(string) --* 

          The ID of the instance. 

          

        
        - **Parameters** *(dict) --* 

          A description of the parameters for a document. 

          

        
          - *(string) --* 

          
            - *(list) --* 

            
              - *(string) --* 

              
          
      
    
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Successful': [
                {
                    'Name': 'string',
                    'InstanceId': 'string',
                    'Date': datetime(2015, 1, 1),
                    'Status': {
                        'Date': datetime(2015, 1, 1),
                        'Name': 'Pending'|'Success'|'Failed',
                        'Message': 'string',
                        'AdditionalInfo': 'string'
                    },
                    'Parameters': {
                        'string': [
                            'string',
                        ]
                    }
                },
            ],
            'Failed': [
                {
                    'Entry': {
                        'Name': 'string',
                        'InstanceId': 'string',
                        'Parameters': {
                            'string': [
                                'string',
                            ]
                        }
                    },
                    'Message': 'string',
                    'Fault': 'Client'|'Server'|'Unknown'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Successful** *(list) --* 

          Information about the associations that succeeded.

          
          

          - *(dict) --* 

            Describes the parameters for a document.

            
            

            - **Name** *(string) --* 

              The name of the SSM document.

              
            

            - **InstanceId** *(string) --* 

              The ID of the instance.

              
            

            - **Date** *(datetime) --* 

              The date when the association was made.

              
            

            - **Status** *(dict) --* 

              The association status.

              
              

              - **Date** *(datetime) --* 

                The date when the status changed.

                
              

              - **Name** *(string) --* 

                The status.

                
              

              - **Message** *(string) --* 

                The reason for the status.

                
              

              - **AdditionalInfo** *(string) --* 

                A user-defined string.

                
          
            

            - **Parameters** *(dict) --* 

              A description of the parameters for a document. 

              
              

              - *(string) --* 
                

                - *(list) --* 
                  

                  - *(string) --* 
              
          
        
        
      
        

        - **Failed** *(list) --* 

          Information about the associations that failed.

          
          

          - *(dict) --* 

            Describes a failed association.

            
            

            - **Entry** *(dict) --* 

              The association.

              
              

              - **Name** *(string) --* 

                The name of the configuration document. 

                
              

              - **InstanceId** *(string) --* 

                The ID of the instance. 

                
              

              - **Parameters** *(dict) --* 

                A description of the parameters for a document. 

                
                

                - *(string) --* 
                  

                  - *(list) --* 
                    

                    - *(string) --* 
                
            
          
          
            

            - **Message** *(string) --* 

              A description of the failure.

              
            

            - **Fault** *(string) --* 

              The source of the failure.

              
        
      
    

  .. py:method:: create_document(**kwargs)

    

    Creates an SSM document.

     

    After you create an SSM document, you can use CreateAssociation to associate it with one or more running instances.

    

    **Request Syntax** 
    ::

      response = client.create_document(
          Content='string',
          Name='string'
      )
    :type Content: string
    :param Content: **[REQUIRED]** 

      A valid JSON string.

      

    
    :type Name: string
    :param Name: **[REQUIRED]** 

      A name for the SSM document.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DocumentDescription': {
                'Sha1': 'string',
                'Hash': 'string',
                'HashType': 'Sha256'|'Sha1',
                'Name': 'string',
                'Owner': 'string',
                'CreatedDate': datetime(2015, 1, 1),
                'Status': 'Creating'|'Active'|'Deleting',
                'Description': 'string',
                'Parameters': [
                    {
                        'Name': 'string',
                        'Type': 'String'|'StringList',
                        'Description': 'string',
                        'DefaultValue': 'string'
                    },
                ],
                'PlatformTypes': [
                    'Windows'|'Linux',
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DocumentDescription** *(dict) --* 

          Information about the SSM document.

          
          

          - **Sha1** *(string) --* 

            The SHA1 hash of the document, which you can use for verification purposes.

            
          

          - **Hash** *(string) --* 

            The Sha256 or Sha1 hash created by the system when the document was created. 

             

            .. note::

               

              Sha1 hashes have been deprecated.

               

            
          

          - **HashType** *(string) --* 

            Sha256 or Sha1.

             

            .. note::

               

              Sha1 hashes have been deprecated.

               

            
          

          - **Name** *(string) --* 

            The name of the SSM document.

            
          

          - **Owner** *(string) --* 

            The AWS user account of the person who created the document.

            
          

          - **CreatedDate** *(datetime) --* 

            The date when the SSM document was created. 

            
          

          - **Status** *(string) --* 

            The status of the SSM document.

            
          

          - **Description** *(string) --* 

            A description of the document. 

            
          

          - **Parameters** *(list) --* 

            A description of the parameters for a document.

            
            

            - *(dict) --* 

              Parameters specified in the SSM document that execute on the server when the command is run. 

              
              

              - **Name** *(string) --* 

                The name of the parameter.

                
              

              - **Type** *(string) --* 

                The type of parameter. The type can be either “String” or “StringList”.

                
              

              - **Description** *(string) --* 

                A description of what the parameter does, how to use it, the default value, and whether or not the parameter is optional.

                
              

              - **DefaultValue** *(string) --* 

                If specified, the default values for the parameters. Parameters without a default value are required. Parameters with a default value are optional.

                
          
        
          

          - **PlatformTypes** *(list) --* 

            The list of OS platforms compatible with this SSM document. 

            
            

            - *(string) --* 
        
      
    

  .. py:method:: delete_activation(**kwargs)

    

    Deletes an activation. You are not required to delete an activation. If you delete an activation, you can no longer use it to register additional managed instances. Deleting an activation does not de-register managed instances. You must manually de-register managed instances.

    

    **Request Syntax** 
    ::

      response = client.delete_activation(
          ActivationId='string'
      )
    :type ActivationId: string
    :param ActivationId: **[REQUIRED]** 

      The ID of the activation that you want to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: delete_association(**kwargs)

    

    Disassociates the specified SSM document from the specified instance.

     

    When you disassociate an SSM document from an instance, it does not change the configuration of the instance. To change the configuration state of an instance after you disassociate a document, you must create a new document with the desired configuration and associate it with the instance.

    

    **Request Syntax** 
    ::

      response = client.delete_association(
          Name='string',
          InstanceId='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the SSM document.

      

    
    :type InstanceId: string
    :param InstanceId: **[REQUIRED]** 

      The ID of the instance.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: delete_document(**kwargs)

    

    Deletes the SSM document and all instance associations to the document.

     

    Before you delete the SSM document, we recommend that you use DeleteAssociation to disassociate all instances that are associated with the document.

    

    **Request Syntax** 
    ::

      response = client.delete_document(
          Name='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the SSM document.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: deregister_managed_instance(**kwargs)

    

    Removes the server or virtual machine from the list of registered servers. You can reregister the instance again at any time. If you don’t plan to use Run Command on the server, we suggest uninstalling the SSM agent first.

    

    **Request Syntax** 
    ::

      response = client.deregister_managed_instance(
          InstanceId='string'
      )
    :type InstanceId: string
    :param InstanceId: **[REQUIRED]** 

      The ID assigned to the managed instance when you registered it using the activation process. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: describe_activations(**kwargs)

    

    Details about the activation, including: the date and time the activation was created, the expiration date, the IAM role assigned to the instances in the activation, and the number of instances activated by this registration.

    

    **Request Syntax** 
    ::

      response = client.describe_activations(
          Filters=[
              {
                  'FilterKey': 'ActivationIds'|'DefaultInstanceName'|'IamRole',
                  'FilterValues': [
                      'string',
                  ]
              },
          ],
          MaxResults=123,
          NextToken='string'
      )
    :type Filters: list
    :param Filters: 

      A filter to view information about your activations.

      

    
      - *(dict) --* 

        Filter for the DescribeActivation API.

        

      
        - **FilterKey** *(string) --* 

          The name of the filter.

          

        
        - **FilterValues** *(list) --* 

          The filter values.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxResults: integer
    :param MaxResults: 

      The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

      

    
    :type NextToken: string
    :param NextToken: 

      A token to start the list. Use this token to get the next set of results. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ActivationList': [
                {
                    'ActivationId': 'string',
                    'Description': 'string',
                    'DefaultInstanceName': 'string',
                    'IamRole': 'string',
                    'RegistrationLimit': 123,
                    'RegistrationsCount': 123,
                    'ExpirationDate': datetime(2015, 1, 1),
                    'Expired': True|False,
                    'CreatedDate': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ActivationList** *(list) --* 

          A list of activations for your AWS account.

          
          

          - *(dict) --* 

            An activation registers one or more on-premises servers or virtual machines (VMs) with AWS so that you can configure those servers or VMs using Run Command. A server or VM that has been registered with AWS is called a managed instance.

            
            

            - **ActivationId** *(string) --* 

              The ID created by SSM when you submitted the activation.

              
            

            - **Description** *(string) --* 

              A user defined description of the activation.

              
            

            - **DefaultInstanceName** *(string) --* 

              A name for the managed instance when it is created.

              
            

            - **IamRole** *(string) --* 

              The Amazon Identity and Access Management (IAM) role to assign to the managed instance.

              
            

            - **RegistrationLimit** *(integer) --* 

              The maximum number of managed instances that can be registered using this activation.

              
            

            - **RegistrationsCount** *(integer) --* 

              The number of managed instances already registered with this activation.

              
            

            - **ExpirationDate** *(datetime) --* 

              The date when this activation can no longer be used to register managed instances.

              
            

            - **Expired** *(boolean) --* 

              Whether or not the activation is expired.

              
            

            - **CreatedDate** *(datetime) --* 

              The date the activation was created.

              
        
      
        

        - **NextToken** *(string) --* 

          The token for the next set of items to return. Use this token to get the next set of results. 

          
    

  .. py:method:: describe_association(**kwargs)

    

    Describes the associations for the specified SSM document or instance.

    

    **Request Syntax** 
    ::

      response = client.describe_association(
          Name='string',
          InstanceId='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the SSM document.

      

    
    :type InstanceId: string
    :param InstanceId: **[REQUIRED]** 

      The instance ID.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AssociationDescription': {
                'Name': 'string',
                'InstanceId': 'string',
                'Date': datetime(2015, 1, 1),
                'Status': {
                    'Date': datetime(2015, 1, 1),
                    'Name': 'Pending'|'Success'|'Failed',
                    'Message': 'string',
                    'AdditionalInfo': 'string'
                },
                'Parameters': {
                    'string': [
                        'string',
                    ]
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **AssociationDescription** *(dict) --* 

          Information about the association.

          
          

          - **Name** *(string) --* 

            The name of the SSM document.

            
          

          - **InstanceId** *(string) --* 

            The ID of the instance.

            
          

          - **Date** *(datetime) --* 

            The date when the association was made.

            
          

          - **Status** *(dict) --* 

            The association status.

            
            

            - **Date** *(datetime) --* 

              The date when the status changed.

              
            

            - **Name** *(string) --* 

              The status.

              
            

            - **Message** *(string) --* 

              The reason for the status.

              
            

            - **AdditionalInfo** *(string) --* 

              A user-defined string.

              
        
          

          - **Parameters** *(dict) --* 

            A description of the parameters for a document. 

            
            

            - *(string) --* 
              

              - *(list) --* 
                

                - *(string) --* 
            
        
      
      
    

  .. py:method:: describe_document(**kwargs)

    

    Describes the specified SSM document.

    

    **Request Syntax** 
    ::

      response = client.describe_document(
          Name='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the SSM document.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Document': {
                'Sha1': 'string',
                'Hash': 'string',
                'HashType': 'Sha256'|'Sha1',
                'Name': 'string',
                'Owner': 'string',
                'CreatedDate': datetime(2015, 1, 1),
                'Status': 'Creating'|'Active'|'Deleting',
                'Description': 'string',
                'Parameters': [
                    {
                        'Name': 'string',
                        'Type': 'String'|'StringList',
                        'Description': 'string',
                        'DefaultValue': 'string'
                    },
                ],
                'PlatformTypes': [
                    'Windows'|'Linux',
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Document** *(dict) --* 

          Information about the SSM document.

          
          

          - **Sha1** *(string) --* 

            The SHA1 hash of the document, which you can use for verification purposes.

            
          

          - **Hash** *(string) --* 

            The Sha256 or Sha1 hash created by the system when the document was created. 

             

            .. note::

               

              Sha1 hashes have been deprecated.

               

            
          

          - **HashType** *(string) --* 

            Sha256 or Sha1.

             

            .. note::

               

              Sha1 hashes have been deprecated.

               

            
          

          - **Name** *(string) --* 

            The name of the SSM document.

            
          

          - **Owner** *(string) --* 

            The AWS user account of the person who created the document.

            
          

          - **CreatedDate** *(datetime) --* 

            The date when the SSM document was created. 

            
          

          - **Status** *(string) --* 

            The status of the SSM document.

            
          

          - **Description** *(string) --* 

            A description of the document. 

            
          

          - **Parameters** *(list) --* 

            A description of the parameters for a document.

            
            

            - *(dict) --* 

              Parameters specified in the SSM document that execute on the server when the command is run. 

              
              

              - **Name** *(string) --* 

                The name of the parameter.

                
              

              - **Type** *(string) --* 

                The type of parameter. The type can be either “String” or “StringList”.

                
              

              - **Description** *(string) --* 

                A description of what the parameter does, how to use it, the default value, and whether or not the parameter is optional.

                
              

              - **DefaultValue** *(string) --* 

                If specified, the default values for the parameters. Parameters without a default value are required. Parameters with a default value are optional.

                
          
        
          

          - **PlatformTypes** *(list) --* 

            The list of OS platforms compatible with this SSM document. 

            
            

            - *(string) --* 
        
      
    

  .. py:method:: describe_document_permission(**kwargs)

    

    Describes the permissions for an SSM document. If you created the document, you are the owner. If a document is shared, it can either be shared privately (by specifying a user’s AWS account ID) or publicly (*All* ). 

    

    **Request Syntax** 
    ::

      response = client.describe_document_permission(
          Name='string',
          PermissionType='Share'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the document for which you are the owner.

      

    
    :type PermissionType: string
    :param PermissionType: **[REQUIRED]** 

      The permission type for the document. The permission type can be *Share* .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AccountIds': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **AccountIds** *(list) --* 

          The account IDs that have permission to use this document. The ID can be either an AWS account or *All* .

          
          

          - *(string) --* 
      
    

  .. py:method:: describe_instance_information(**kwargs)

    

    Describes one or more of your instances. You can use this to get information about instances like the operating system platform, the SSM agent version (Linux), status etc. If you specify one or more instance IDs, it returns information for those instances. If you do not specify instance IDs, it returns information for all your instances. If you specify an instance ID that is not valid or an instance that you do not own, you receive an error. 

    

    **Request Syntax** 
    ::

      response = client.describe_instance_information(
          InstanceInformationFilterList=[
              {
                  'key': 'InstanceIds'|'AgentVersion'|'PingStatus'|'PlatformTypes'|'ActivationIds'|'IamRole'|'ResourceType',
                  'valueSet': [
                      'string',
                  ]
              },
          ],
          MaxResults=123,
          NextToken='string'
      )
    :type InstanceInformationFilterList: list
    :param InstanceInformationFilterList: 

      One or more filters. Use a filter to return a more specific list of instances.

      

    
      - *(dict) --* 

        Describes a filter for a specific list of instances. 

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The name of the filter. 

          

        
        - **valueSet** *(list) --* **[REQUIRED]** 

          The filter values. 

          

        
          - *(string) --* 

          
      
      
  
    :type MaxResults: integer
    :param MaxResults: 

      The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results. 

      

    
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'InstanceInformationList': [
                {
                    'InstanceId': 'string',
                    'PingStatus': 'Online'|'ConnectionLost'|'Inactive',
                    'LastPingDateTime': datetime(2015, 1, 1),
                    'AgentVersion': 'string',
                    'IsLatestVersion': True|False,
                    'PlatformType': 'Windows'|'Linux',
                    'PlatformName': 'string',
                    'PlatformVersion': 'string',
                    'ActivationId': 'string',
                    'IamRole': 'string',
                    'RegistrationDate': datetime(2015, 1, 1),
                    'ResourceType': 'ManagedInstance'|'Document'|'EC2Instance',
                    'Name': 'string',
                    'IPAddress': 'string',
                    'ComputerName': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **InstanceInformationList** *(list) --* 

          The instance information list.

          
          

          - *(dict) --* 

            Describes a filter for a specific list of instances. 

            
            

            - **InstanceId** *(string) --* 

              The instance ID. 

              
            

            - **PingStatus** *(string) --* 

              Connection status of the SSM agent. 

              
            

            - **LastPingDateTime** *(datetime) --* 

              The date and time when agent last pinged SSM service. 

              
            

            - **AgentVersion** *(string) --* 

              The version of the SSM agent running on your Linux instance. 

              
            

            - **IsLatestVersion** *(boolean) --* 

              Indicates whether latest version of the SSM agent is running on your instance. 

              
            

            - **PlatformType** *(string) --* 

              The operating system platform type. 

              
            

            - **PlatformName** *(string) --* 

              The name of the operating system platform running on your instance. 

              
            

            - **PlatformVersion** *(string) --* 

              The version of the OS platform running on your instance. 

              
            

            - **ActivationId** *(string) --* 

              The activation ID created by SSM when the server or VM was registered.

              
            

            - **IamRole** *(string) --* 

              The Amazon Identity and Access Management (IAM) role assigned to EC2 instances or managed instances. 

              
            

            - **RegistrationDate** *(datetime) --* 

              The date the server or VM was registered with AWS as a managed instance.

              
            

            - **ResourceType** *(string) --* 

              The type of instance. Instances are either EC2 instances or managed instances. 

              
            

            - **Name** *(string) --* 

              The name of the managed instance.

              
            

            - **IPAddress** *(string) --* 

              The IP address of the managed instance.

              
            

            - **ComputerName** *(string) --* 

              The fully qualified host name of the managed instance.

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty. 

          
    

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


  .. py:method:: get_document(**kwargs)

    

    Gets the contents of the specified SSM document.

    

    **Request Syntax** 
    ::

      response = client.get_document(
          Name='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the SSM document.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Name': 'string',
            'Content': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Name** *(string) --* 

          The name of the SSM document.

          
        

        - **Content** *(string) --* 

          The contents of the SSM document.

          
    

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

        


  .. py:method:: list_associations(**kwargs)

    

    Lists the associations for the specified SSM document or instance.

    

    **Request Syntax** 
    ::

      response = client.list_associations(
          AssociationFilterList=[
              {
                  'key': 'InstanceId'|'Name',
                  'value': 'string'
              },
          ],
          MaxResults=123,
          NextToken='string'
      )
    :type AssociationFilterList: list
    :param AssociationFilterList: **[REQUIRED]** 

      One or more filters. Use a filter to return a more specific list of results.

      

    
      - *(dict) --* 

        Describes a filter.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The name of the filter.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          The filter value.

          

        
      
  
    :type MaxResults: integer
    :param MaxResults: 

      The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

      

    
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Associations': [
                {
                    'Name': 'string',
                    'InstanceId': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Associations** *(list) --* 

          The associations.

          
          

          - *(dict) --* 

            Describes an association of an SSM document and an instance.

            
            

            - **Name** *(string) --* 

              The name of the SSM document.

              
            

            - **InstanceId** *(string) --* 

              The ID of the instance.

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: list_command_invocations(**kwargs)

    

    An invocation is copy of a command sent to a specific instance. A command can apply to one or more instances. A command invocation applies to one instance. For example, if a user executes SendCommand against three instances, then a command invocation is created for each requested instance ID. ListCommandInvocations provide status about command execution.

    

    **Request Syntax** 
    ::

      response = client.list_command_invocations(
          CommandId='string',
          InstanceId='string',
          MaxResults=123,
          NextToken='string',
          Filters=[
              {
                  'key': 'InvokedAfter'|'InvokedBefore'|'Status',
                  'value': 'string'
              },
          ],
          Details=True|False
      )
    :type CommandId: string
    :param CommandId: 

      (Optional) The invocations for a specific command ID.

      

    
    :type InstanceId: string
    :param InstanceId: 

      (Optional) The command execution details for a specific instance ID.

      

    
    :type MaxResults: integer
    :param MaxResults: 

      (Optional) The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

      

    
    :type NextToken: string
    :param NextToken: 

      (Optional) The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type Filters: list
    :param Filters: 

      (Optional) One or more filters. Use a filter to return a more specific list of results.

      

    
      - *(dict) --* 

        Describes a command filter.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The name of the filter. For example, requested date and time.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          The filter value. For example: June 30, 2015.

          

        
      
  
    :type Details: boolean
    :param Details: 

      (Optional) If set this returns the response of the command executions and any command output. By default this is set to False. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CommandInvocations': [
                {
                    'CommandId': 'string',
                    'InstanceId': 'string',
                    'Comment': 'string',
                    'DocumentName': 'string',
                    'RequestedDateTime': datetime(2015, 1, 1),
                    'Status': 'Pending'|'InProgress'|'Cancelling'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                    'TraceOutput': 'string',
                    'CommandPlugins': [
                        {
                            'Name': 'string',
                            'Status': 'Pending'|'InProgress'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                            'ResponseCode': 123,
                            'ResponseStartDateTime': datetime(2015, 1, 1),
                            'ResponseFinishDateTime': datetime(2015, 1, 1),
                            'Output': 'string',
                            'OutputS3BucketName': 'string',
                            'OutputS3KeyPrefix': 'string'
                        },
                    ],
                    'ServiceRole': 'string',
                    'NotificationConfig': {
                        'NotificationArn': 'string',
                        'NotificationEvents': [
                            'All'|'InProgress'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                        ],
                        'NotificationType': 'Command'|'Invocation'
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **CommandInvocations** *(list) --* 

          (Optional) A list of all invocations. 

          
          

          - *(dict) --* 

            An invocation is copy of a command sent to a specific instance. A command can apply to one or more instances. A command invocation applies to one instance. For example, if a user executes SendCommand against three instances, then a command invocation is created for each requested instance ID. A command invocation returns status and detail information about a command you executed. 

            
            

            - **CommandId** *(string) --* 

              The command against which this invocation was requested.

              
            

            - **InstanceId** *(string) --* 

              The instance ID in which this invocation was requested.

              
            

            - **Comment** *(string) --* 

              User-specified information about the command, such as a brief description of what the command should do.

              
            

            - **DocumentName** *(string) --* 

              The document name that was requested for execution.

              
            

            - **RequestedDateTime** *(datetime) --* 

              The time and date the request was sent to this instance.

              
            

            - **Status** *(string) --* 

              Whether or not the invocation succeeded, failed, or is pending.

              
            

            - **TraceOutput** *(string) --* 

              Gets the trace output sent by the agent. 

              
            

            - **CommandPlugins** *(list) --* 
              

              - *(dict) --* 

                Describes plugin details.

                
                

                - **Name** *(string) --* 

                  The name of the plugin. Must be one of the following: aws:updateAgent, aws:domainjoin, aws:applications, aws:runPowerShellScript, aws:psmodule, aws:cloudWatch, aws:runShellScript, or aws:updateSSMAgent. 

                  
                

                - **Status** *(string) --* 

                  The status of this plugin. You can execute a document with multiple plugins.

                  
                

                - **ResponseCode** *(integer) --* 

                  A numeric response code generated after executing the plugin. 

                  
                

                - **ResponseStartDateTime** *(datetime) --* 

                  The time the plugin started executing. 

                  
                

                - **ResponseFinishDateTime** *(datetime) --* 

                  The time the plugin stopped executing. Could stop prematurely if, for example, a cancel command was sent. 

                  
                

                - **Output** *(string) --* 

                  Output of the plugin execution.

                  
                

                - **OutputS3BucketName** *(string) --* 

                  The S3 bucket where the responses to the command executions should be stored. This was requested when issuing the command.

                  
                

                - **OutputS3KeyPrefix** *(string) --* 

                  The S3 directory path inside the bucket where the responses to the command executions should be stored. This was requested when issuing the command. 

                  
            
          
            

            - **ServiceRole** *(string) --* 

              The IAM service role that SSM uses to act on your behalf when sending notifications about command status changes on a per instance basis.

              
            

            - **NotificationConfig** *(dict) --* 

              Configurations for sending notifications about command status changes on a per instance basis.

              
              

              - **NotificationArn** *(string) --* 

                An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. SSM pushes notifications about command status changes to this topic.

                
              

              - **NotificationEvents** *(list) --* 

                The different events for which you can receive notifications. These events include the following: All (events), InProgress, Success, TimedOut, Cancelled, Failed. To learn more about these events, see `Monitoring Commands`_ in the *Amazon Elastic Compute Cloud User Guide* .

                
                

                - *(string) --* 
            
              

              - **NotificationType** *(string) --* 

                Command: Receive notification when the status of a command changes. Invocation: For commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. 

                
          
        
      
        

        - **NextToken** *(string) --* 

          (Optional) The token for the next set of items to return. (You received this token from a previous call.)

          
    

  .. py:method:: list_commands(**kwargs)

    

    Lists the commands requested by users of the AWS account.

    

    **Request Syntax** 
    ::

      response = client.list_commands(
          CommandId='string',
          InstanceId='string',
          MaxResults=123,
          NextToken='string',
          Filters=[
              {
                  'key': 'InvokedAfter'|'InvokedBefore'|'Status',
                  'value': 'string'
              },
          ]
      )
    :type CommandId: string
    :param CommandId: 

      (Optional) If provided, lists only the specified command.

      

    
    :type InstanceId: string
    :param InstanceId: 

      (Optional) Lists commands issued against this instance ID.

      

    
    :type MaxResults: integer
    :param MaxResults: 

      (Optional) The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

      

    
    :type NextToken: string
    :param NextToken: 

      (Optional) The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type Filters: list
    :param Filters: 

      (Optional) One or more filters. Use a filter to return a more specific list of results. 

      

    
      - *(dict) --* 

        Describes a command filter.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The name of the filter. For example, requested date and time.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          The filter value. For example: June 30, 2015.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Commands': [
                {
                    'CommandId': 'string',
                    'DocumentName': 'string',
                    'Comment': 'string',
                    'ExpiresAfter': datetime(2015, 1, 1),
                    'Parameters': {
                        'string': [
                            'string',
                        ]
                    },
                    'InstanceIds': [
                        'string',
                    ],
                    'RequestedDateTime': datetime(2015, 1, 1),
                    'Status': 'Pending'|'InProgress'|'Cancelling'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                    'OutputS3BucketName': 'string',
                    'OutputS3KeyPrefix': 'string',
                    'ServiceRole': 'string',
                    'NotificationConfig': {
                        'NotificationArn': 'string',
                        'NotificationEvents': [
                            'All'|'InProgress'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                        ],
                        'NotificationType': 'Command'|'Invocation'
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Commands** *(list) --* 

          (Optional) The list of commands requested by the user. 

          
          

          - *(dict) --* 

            Describes a command request.

            
            

            - **CommandId** *(string) --* 

              A unique identifier for this command.

              
            

            - **DocumentName** *(string) --* 

              The name of the SSM document requested for execution.

              
            

            - **Comment** *(string) --* 

              User-specified information about the command, such as a brief description of what the command should do.

              
            

            - **ExpiresAfter** *(datetime) --* 

              If this time is reached and the command has not already started executing, it will not execute. Calculated based on the ExpiresAfter user input provided as part of the SendCommand API.

              
            

            - **Parameters** *(dict) --* 

              The parameter values to be inserted in the SSM document when executing the command.

              
              

              - *(string) --* 
                

                - *(list) --* 
                  

                  - *(string) --* 
              
          
        
            

            - **InstanceIds** *(list) --* 

              The instance IDs against which this command was requested.

              
              

              - *(string) --* 
          
            

            - **RequestedDateTime** *(datetime) --* 

              The date and time the command was requested.

              
            

            - **Status** *(string) --* 

              The status of the command.

              
            

            - **OutputS3BucketName** *(string) --* 

              The S3 bucket where the responses to the command executions should be stored. This was requested when issuing the command.

              
            

            - **OutputS3KeyPrefix** *(string) --* 

              The S3 directory path inside the bucket where the responses to the command executions should be stored. This was requested when issuing the command.

              
            

            - **ServiceRole** *(string) --* 

              The IAM service role that SSM uses to act on your behalf when sending notifications about command status changes. 

              
            

            - **NotificationConfig** *(dict) --* 

              Configurations for sending notifications about command status changes. 

              
              

              - **NotificationArn** *(string) --* 

                An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. SSM pushes notifications about command status changes to this topic.

                
              

              - **NotificationEvents** *(list) --* 

                The different events for which you can receive notifications. These events include the following: All (events), InProgress, Success, TimedOut, Cancelled, Failed. To learn more about these events, see `Monitoring Commands`_ in the *Amazon Elastic Compute Cloud User Guide* .

                
                

                - *(string) --* 
            
              

              - **NotificationType** *(string) --* 

                Command: Receive notification when the status of a command changes. Invocation: For commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. 

                
          
        
      
        

        - **NextToken** *(string) --* 

          (Optional) The token for the next set of items to return. (You received this token from a previous call.)

          
    

  .. py:method:: list_documents(**kwargs)

    

    Describes one or more of your SSM documents.

    

    **Request Syntax** 
    ::

      response = client.list_documents(
          DocumentFilterList=[
              {
                  'key': 'Name'|'Owner'|'PlatformTypes',
                  'value': 'string'
              },
          ],
          MaxResults=123,
          NextToken='string'
      )
    :type DocumentFilterList: list
    :param DocumentFilterList: 

      One or more filters. Use a filter to return a more specific list of results.

      

    
      - *(dict) --* 

        Describes a filter.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The name of the filter.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          The value of the filter.

          

        
      
  
    :type MaxResults: integer
    :param MaxResults: 

      The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

      

    
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DocumentIdentifiers': [
                {
                    'Name': 'string',
                    'Owner': 'string',
                    'PlatformTypes': [
                        'Windows'|'Linux',
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DocumentIdentifiers** *(list) --* 

          The names of the SSM documents.

          
          

          - *(dict) --* 

            Describes the name of an SSM document.

            
            

            - **Name** *(string) --* 

              The name of the SSM document.

              
            

            - **Owner** *(string) --* 

              The AWS user account of the person who created the document.

              
            

            - **PlatformTypes** *(list) --* 

              The operating system platform. 

              
              

              - *(string) --* 
          
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: list_tags_for_resource(**kwargs)

    

    Returns a list of the tags assigned to the specified resource.

    

    **Request Syntax** 
    ::

      response = client.list_tags_for_resource(
          ResourceType='ManagedInstance',
          ResourceId='string'
      )
    :type ResourceType: string
    :param ResourceType: **[REQUIRED]** 

      Returns a list of tags for a specific resource type.

      

    
    :type ResourceId: string
    :param ResourceId: **[REQUIRED]** 

      The resource ID for which you want to see a list of tags.

      

    
    
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
        

        - **TagList** *(list) --* 

          A list of tags.

          
          

          - *(dict) --* 

            Metadata that you assign to your managed instances. Tags enable you to categorize your managed instances in different ways, for example, by purpose, owner, or environment.

            
            

            - **Key** *(string) --* 

              The name of the tag.

              
            

            - **Value** *(string) --* 

              The value of the tag.

              
        
      
    

  .. py:method:: modify_document_permission(**kwargs)

    

    Share a document publicly or privately. If you share a document privately, you must specify the AWS user account IDs for those people who can use the document. If you share a document publicly, you must specify *All* as the account ID.

    

    **Request Syntax** 
    ::

      response = client.modify_document_permission(
          Name='string',
          PermissionType='Share',
          AccountIdsToAdd=[
              'string',
          ],
          AccountIdsToRemove=[
              'string',
          ]
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the document that you want to share.

      

    
    :type PermissionType: string
    :param PermissionType: **[REQUIRED]** 

      The permission type for the document. The permission type can be *Share* .

      

    
    :type AccountIdsToAdd: list
    :param AccountIdsToAdd: 

      The AWS user accounts that should have access to the document. The account IDs can either be a group of account IDs or *All* .

      

    
      - *(string) --* 

      
  
    :type AccountIdsToRemove: list
    :param AccountIdsToRemove: 

      The AWS user accounts that should no longer have access to the document. The AWS user account can either be a group of account IDs or *All* . This action has a higher priority than *AccountIdsToAdd* . If you specify an account ID to add and the same ID to remove, the system removes access to the document.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: remove_tags_from_resource(**kwargs)

    

    Removes all tags from the specified resource.

    

    **Request Syntax** 
    ::

      response = client.remove_tags_from_resource(
          ResourceType='ManagedInstance',
          ResourceId='string',
          TagKeys=[
              'string',
          ]
      )
    :type ResourceType: string
    :param ResourceType: **[REQUIRED]** 

      The type of resource of which you want to remove a tag.

      

    
    :type ResourceId: string
    :param ResourceId: **[REQUIRED]** 

      The resource ID for which you want to remove tags.

      

    
    :type TagKeys: list
    :param TagKeys: **[REQUIRED]** 

      Tag keys that you want to remove from the specified resource.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: send_command(**kwargs)

    

    Executes commands on one or more remote instances.

    

    **Request Syntax** 
    ::

      response = client.send_command(
          InstanceIds=[
              'string',
          ],
          DocumentName='string',
          DocumentHash='string',
          DocumentHashType='Sha256'|'Sha1',
          TimeoutSeconds=123,
          Comment='string',
          Parameters={
              'string': [
                  'string',
              ]
          },
          OutputS3BucketName='string',
          OutputS3KeyPrefix='string',
          ServiceRoleArn='string',
          NotificationConfig={
              'NotificationArn': 'string',
              'NotificationEvents': [
                  'All'|'InProgress'|'Success'|'TimedOut'|'Cancelled'|'Failed',
              ],
              'NotificationType': 'Command'|'Invocation'
          }
      )
    :type InstanceIds: list
    :param InstanceIds: **[REQUIRED]** 

      Required. The instance IDs where the command should execute. You can specify a maximum of 50 IDs.

      

    
      - *(string) --* 

      
  
    :type DocumentName: string
    :param DocumentName: **[REQUIRED]** 

      Required. The name of the SSM document to execute. This can be an SSM public document or a custom document.

      

    
    :type DocumentHash: string
    :param DocumentHash: 

      The Sha256 or Sha1 hash created by the system when the document was created. 

       

      .. note::

         

        Sha1 hashes have been deprecated.

         

      

    
    :type DocumentHashType: string
    :param DocumentHashType: 

      Sha256 or Sha1.

       

      .. note::

         

        Sha1 hashes have been deprecated.

         

      

    
    :type TimeoutSeconds: integer
    :param TimeoutSeconds: 

      If this time is reached and the command has not already started executing, it will not execute.

      

    
    :type Comment: string
    :param Comment: 

      User-specified information about the command, such as a brief description of what the command should do.

      

    
    :type Parameters: dict
    :param Parameters: 

      The required and optional parameters specified in the SSM document being executed.

      

    
      - *(string) --* 

      
        - *(list) --* 

        
          - *(string) --* 

          
      
  

    :type OutputS3BucketName: string
    :param OutputS3BucketName: 

      The name of the S3 bucket where command execution responses should be stored.

      

    
    :type OutputS3KeyPrefix: string
    :param OutputS3KeyPrefix: 

      The directory structure within the S3 bucket where the responses should be stored.

      

    
    :type ServiceRoleArn: string
    :param ServiceRoleArn: 

      The IAM role that SSM uses to send notifications. 

      

    
    :type NotificationConfig: dict
    :param NotificationConfig: 

      Configurations for sending notifications.

      

    
      - **NotificationArn** *(string) --* 

        An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. SSM pushes notifications about command status changes to this topic.

        

      
      - **NotificationEvents** *(list) --* 

        The different events for which you can receive notifications. These events include the following: All (events), InProgress, Success, TimedOut, Cancelled, Failed. To learn more about these events, see `Monitoring Commands`_ in the *Amazon Elastic Compute Cloud User Guide* .

        

      
        - *(string) --* 

        
    
      - **NotificationType** *(string) --* 

        Command: Receive notification when the status of a command changes. Invocation: For commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. 

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Command': {
                'CommandId': 'string',
                'DocumentName': 'string',
                'Comment': 'string',
                'ExpiresAfter': datetime(2015, 1, 1),
                'Parameters': {
                    'string': [
                        'string',
                    ]
                },
                'InstanceIds': [
                    'string',
                ],
                'RequestedDateTime': datetime(2015, 1, 1),
                'Status': 'Pending'|'InProgress'|'Cancelling'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                'OutputS3BucketName': 'string',
                'OutputS3KeyPrefix': 'string',
                'ServiceRole': 'string',
                'NotificationConfig': {
                    'NotificationArn': 'string',
                    'NotificationEvents': [
                        'All'|'InProgress'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                    ],
                    'NotificationType': 'Command'|'Invocation'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Command** *(dict) --* 

          The request as it was received by SSM. Also provides the command ID which can be used future references to this request.

          
          

          - **CommandId** *(string) --* 

            A unique identifier for this command.

            
          

          - **DocumentName** *(string) --* 

            The name of the SSM document requested for execution.

            
          

          - **Comment** *(string) --* 

            User-specified information about the command, such as a brief description of what the command should do.

            
          

          - **ExpiresAfter** *(datetime) --* 

            If this time is reached and the command has not already started executing, it will not execute. Calculated based on the ExpiresAfter user input provided as part of the SendCommand API.

            
          

          - **Parameters** *(dict) --* 

            The parameter values to be inserted in the SSM document when executing the command.

            
            

            - *(string) --* 
              

              - *(list) --* 
                

                - *(string) --* 
            
        
      
          

          - **InstanceIds** *(list) --* 

            The instance IDs against which this command was requested.

            
            

            - *(string) --* 
        
          

          - **RequestedDateTime** *(datetime) --* 

            The date and time the command was requested.

            
          

          - **Status** *(string) --* 

            The status of the command.

            
          

          - **OutputS3BucketName** *(string) --* 

            The S3 bucket where the responses to the command executions should be stored. This was requested when issuing the command.

            
          

          - **OutputS3KeyPrefix** *(string) --* 

            The S3 directory path inside the bucket where the responses to the command executions should be stored. This was requested when issuing the command.

            
          

          - **ServiceRole** *(string) --* 

            The IAM service role that SSM uses to act on your behalf when sending notifications about command status changes. 

            
          

          - **NotificationConfig** *(dict) --* 

            Configurations for sending notifications about command status changes. 

            
            

            - **NotificationArn** *(string) --* 

              An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. SSM pushes notifications about command status changes to this topic.

              
            

            - **NotificationEvents** *(list) --* 

              The different events for which you can receive notifications. These events include the following: All (events), InProgress, Success, TimedOut, Cancelled, Failed. To learn more about these events, see `Monitoring Commands`_ in the *Amazon Elastic Compute Cloud User Guide* .

              
              

              - *(string) --* 
          
            

            - **NotificationType** *(string) --* 

              Command: Receive notification when the status of a command changes. Invocation: For commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. 

              
        
      
    

  .. py:method:: update_association_status(**kwargs)

    

    Updates the status of the SSM document associated with the specified instance.

    

    **Request Syntax** 
    ::

      response = client.update_association_status(
          Name='string',
          InstanceId='string',
          AssociationStatus={
              'Date': datetime(2015, 1, 1),
              'Name': 'Pending'|'Success'|'Failed',
              'Message': 'string',
              'AdditionalInfo': 'string'
          }
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the SSM document.

      

    
    :type InstanceId: string
    :param InstanceId: **[REQUIRED]** 

      The ID of the instance.

      

    
    :type AssociationStatus: dict
    :param AssociationStatus: **[REQUIRED]** 

      The association status.

      

    
      - **Date** *(datetime) --* **[REQUIRED]** 

        The date when the status changed.

        

      
      - **Name** *(string) --* **[REQUIRED]** 

        The status.

        

      
      - **Message** *(string) --* **[REQUIRED]** 

        The reason for the status.

        

      
      - **AdditionalInfo** *(string) --* 

        A user-defined string.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AssociationDescription': {
                'Name': 'string',
                'InstanceId': 'string',
                'Date': datetime(2015, 1, 1),
                'Status': {
                    'Date': datetime(2015, 1, 1),
                    'Name': 'Pending'|'Success'|'Failed',
                    'Message': 'string',
                    'AdditionalInfo': 'string'
                },
                'Parameters': {
                    'string': [
                        'string',
                    ]
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **AssociationDescription** *(dict) --* 

          Information about the association.

          
          

          - **Name** *(string) --* 

            The name of the SSM document.

            
          

          - **InstanceId** *(string) --* 

            The ID of the instance.

            
          

          - **Date** *(datetime) --* 

            The date when the association was made.

            
          

          - **Status** *(dict) --* 

            The association status.

            
            

            - **Date** *(datetime) --* 

              The date when the status changed.

              
            

            - **Name** *(string) --* 

              The status.

              
            

            - **Message** *(string) --* 

              The reason for the status.

              
            

            - **AdditionalInfo** *(string) --* 

              A user-defined string.

              
        
          

          - **Parameters** *(dict) --* 

            A description of the parameters for a document. 

            
            

            - *(string) --* 
              

              - *(list) --* 
                

                - *(string) --* 
            
        
      
      
    

  .. py:method:: update_managed_instance_role(**kwargs)

    

    Assigns or changes an Amazon Identity and Access Management (IAM) role to the managed instance.

    

    **Request Syntax** 
    ::

      response = client.update_managed_instance_role(
          InstanceId='string',
          IamRole='string'
      )
    :type InstanceId: string
    :param InstanceId: **[REQUIRED]** 

      The ID of the managed instance where you want to update the role.

      

    
    :type IamRole: string
    :param IamRole: **[REQUIRED]** 

      The IAM role you want to assign or change.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

==========
Paginators
==========


The available paginators are:

* :py:class:`SSM.Paginator.ListAssociations`


* :py:class:`SSM.Paginator.ListCommandInvocations`


* :py:class:`SSM.Paginator.ListCommands`


* :py:class:`SSM.Paginator.ListDocuments`



.. py:class:: SSM.Paginator.ListAssociations

  ::

    
    paginator = client.get_paginator('list_associations')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`SSM.Client.list_associations`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          AssociationFilterList=[
              {
                  'key': 'InstanceId'|'Name',
                  'value': 'string'
              },
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type AssociationFilterList: list
    :param AssociationFilterList: **[REQUIRED]** 

      One or more filters. Use a filter to return a more specific list of results.

      

    
      - *(dict) --* 

        Describes a filter.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The name of the filter.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          The filter value.

          

        
      
  
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
            'Associations': [
                {
                    'Name': 'string',
                    'InstanceId': 'string'
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Associations** *(list) --* 

          The associations.

          
          

          - *(dict) --* 

            Describes an association of an SSM document and an instance.

            
            

            - **Name** *(string) --* 

              The name of the SSM document.

              
            

            - **InstanceId** *(string) --* 

              The ID of the instance.

              
        
      
    

.. py:class:: SSM.Paginator.ListCommandInvocations

  ::

    
    paginator = client.get_paginator('list_command_invocations')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`SSM.Client.list_command_invocations`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          CommandId='string',
          InstanceId='string',
          Filters=[
              {
                  'key': 'InvokedAfter'|'InvokedBefore'|'Status',
                  'value': 'string'
              },
          ],
          Details=True|False,
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type CommandId: string
    :param CommandId: 

      (Optional) The invocations for a specific command ID.

      

    
    :type InstanceId: string
    :param InstanceId: 

      (Optional) The command execution details for a specific instance ID.

      

    
    :type Filters: list
    :param Filters: 

      (Optional) One or more filters. Use a filter to return a more specific list of results.

      

    
      - *(dict) --* 

        Describes a command filter.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The name of the filter. For example, requested date and time.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          The filter value. For example: June 30, 2015.

          

        
      
  
    :type Details: boolean
    :param Details: 

      (Optional) If set this returns the response of the command executions and any command output. By default this is set to False. 

      

    
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
            'CommandInvocations': [
                {
                    'CommandId': 'string',
                    'InstanceId': 'string',
                    'Comment': 'string',
                    'DocumentName': 'string',
                    'RequestedDateTime': datetime(2015, 1, 1),
                    'Status': 'Pending'|'InProgress'|'Cancelling'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                    'TraceOutput': 'string',
                    'CommandPlugins': [
                        {
                            'Name': 'string',
                            'Status': 'Pending'|'InProgress'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                            'ResponseCode': 123,
                            'ResponseStartDateTime': datetime(2015, 1, 1),
                            'ResponseFinishDateTime': datetime(2015, 1, 1),
                            'Output': 'string',
                            'OutputS3BucketName': 'string',
                            'OutputS3KeyPrefix': 'string'
                        },
                    ],
                    'ServiceRole': 'string',
                    'NotificationConfig': {
                        'NotificationArn': 'string',
                        'NotificationEvents': [
                            'All'|'InProgress'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                        ],
                        'NotificationType': 'Command'|'Invocation'
                    }
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **CommandInvocations** *(list) --* 

          (Optional) A list of all invocations. 

          
          

          - *(dict) --* 

            An invocation is copy of a command sent to a specific instance. A command can apply to one or more instances. A command invocation applies to one instance. For example, if a user executes SendCommand against three instances, then a command invocation is created for each requested instance ID. A command invocation returns status and detail information about a command you executed. 

            
            

            - **CommandId** *(string) --* 

              The command against which this invocation was requested.

              
            

            - **InstanceId** *(string) --* 

              The instance ID in which this invocation was requested.

              
            

            - **Comment** *(string) --* 

              User-specified information about the command, such as a brief description of what the command should do.

              
            

            - **DocumentName** *(string) --* 

              The document name that was requested for execution.

              
            

            - **RequestedDateTime** *(datetime) --* 

              The time and date the request was sent to this instance.

              
            

            - **Status** *(string) --* 

              Whether or not the invocation succeeded, failed, or is pending.

              
            

            - **TraceOutput** *(string) --* 

              Gets the trace output sent by the agent. 

              
            

            - **CommandPlugins** *(list) --* 
              

              - *(dict) --* 

                Describes plugin details.

                
                

                - **Name** *(string) --* 

                  The name of the plugin. Must be one of the following: aws:updateAgent, aws:domainjoin, aws:applications, aws:runPowerShellScript, aws:psmodule, aws:cloudWatch, aws:runShellScript, or aws:updateSSMAgent. 

                  
                

                - **Status** *(string) --* 

                  The status of this plugin. You can execute a document with multiple plugins.

                  
                

                - **ResponseCode** *(integer) --* 

                  A numeric response code generated after executing the plugin. 

                  
                

                - **ResponseStartDateTime** *(datetime) --* 

                  The time the plugin started executing. 

                  
                

                - **ResponseFinishDateTime** *(datetime) --* 

                  The time the plugin stopped executing. Could stop prematurely if, for example, a cancel command was sent. 

                  
                

                - **Output** *(string) --* 

                  Output of the plugin execution.

                  
                

                - **OutputS3BucketName** *(string) --* 

                  The S3 bucket where the responses to the command executions should be stored. This was requested when issuing the command.

                  
                

                - **OutputS3KeyPrefix** *(string) --* 

                  The S3 directory path inside the bucket where the responses to the command executions should be stored. This was requested when issuing the command. 

                  
            
          
            

            - **ServiceRole** *(string) --* 

              The IAM service role that SSM uses to act on your behalf when sending notifications about command status changes on a per instance basis.

              
            

            - **NotificationConfig** *(dict) --* 

              Configurations for sending notifications about command status changes on a per instance basis.

              
              

              - **NotificationArn** *(string) --* 

                An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. SSM pushes notifications about command status changes to this topic.

                
              

              - **NotificationEvents** *(list) --* 

                The different events for which you can receive notifications. These events include the following: All (events), InProgress, Success, TimedOut, Cancelled, Failed. To learn more about these events, see `Monitoring Commands`_ in the *Amazon Elastic Compute Cloud User Guide* .

                
                

                - *(string) --* 
            
              

              - **NotificationType** *(string) --* 

                Command: Receive notification when the status of a command changes. Invocation: For commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. 

                
          
        
      
    

.. py:class:: SSM.Paginator.ListCommands

  ::

    
    paginator = client.get_paginator('list_commands')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`SSM.Client.list_commands`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          CommandId='string',
          InstanceId='string',
          Filters=[
              {
                  'key': 'InvokedAfter'|'InvokedBefore'|'Status',
                  'value': 'string'
              },
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type CommandId: string
    :param CommandId: 

      (Optional) If provided, lists only the specified command.

      

    
    :type InstanceId: string
    :param InstanceId: 

      (Optional) Lists commands issued against this instance ID.

      

    
    :type Filters: list
    :param Filters: 

      (Optional) One or more filters. Use a filter to return a more specific list of results. 

      

    
      - *(dict) --* 

        Describes a command filter.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The name of the filter. For example, requested date and time.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          The filter value. For example: June 30, 2015.

          

        
      
  
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
            'Commands': [
                {
                    'CommandId': 'string',
                    'DocumentName': 'string',
                    'Comment': 'string',
                    'ExpiresAfter': datetime(2015, 1, 1),
                    'Parameters': {
                        'string': [
                            'string',
                        ]
                    },
                    'InstanceIds': [
                        'string',
                    ],
                    'RequestedDateTime': datetime(2015, 1, 1),
                    'Status': 'Pending'|'InProgress'|'Cancelling'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                    'OutputS3BucketName': 'string',
                    'OutputS3KeyPrefix': 'string',
                    'ServiceRole': 'string',
                    'NotificationConfig': {
                        'NotificationArn': 'string',
                        'NotificationEvents': [
                            'All'|'InProgress'|'Success'|'TimedOut'|'Cancelled'|'Failed',
                        ],
                        'NotificationType': 'Command'|'Invocation'
                    }
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Commands** *(list) --* 

          (Optional) The list of commands requested by the user. 

          
          

          - *(dict) --* 

            Describes a command request.

            
            

            - **CommandId** *(string) --* 

              A unique identifier for this command.

              
            

            - **DocumentName** *(string) --* 

              The name of the SSM document requested for execution.

              
            

            - **Comment** *(string) --* 

              User-specified information about the command, such as a brief description of what the command should do.

              
            

            - **ExpiresAfter** *(datetime) --* 

              If this time is reached and the command has not already started executing, it will not execute. Calculated based on the ExpiresAfter user input provided as part of the SendCommand API.

              
            

            - **Parameters** *(dict) --* 

              The parameter values to be inserted in the SSM document when executing the command.

              
              

              - *(string) --* 
                

                - *(list) --* 
                  

                  - *(string) --* 
              
          
        
            

            - **InstanceIds** *(list) --* 

              The instance IDs against which this command was requested.

              
              

              - *(string) --* 
          
            

            - **RequestedDateTime** *(datetime) --* 

              The date and time the command was requested.

              
            

            - **Status** *(string) --* 

              The status of the command.

              
            

            - **OutputS3BucketName** *(string) --* 

              The S3 bucket where the responses to the command executions should be stored. This was requested when issuing the command.

              
            

            - **OutputS3KeyPrefix** *(string) --* 

              The S3 directory path inside the bucket where the responses to the command executions should be stored. This was requested when issuing the command.

              
            

            - **ServiceRole** *(string) --* 

              The IAM service role that SSM uses to act on your behalf when sending notifications about command status changes. 

              
            

            - **NotificationConfig** *(dict) --* 

              Configurations for sending notifications about command status changes. 

              
              

              - **NotificationArn** *(string) --* 

                An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. SSM pushes notifications about command status changes to this topic.

                
              

              - **NotificationEvents** *(list) --* 

                The different events for which you can receive notifications. These events include the following: All (events), InProgress, Success, TimedOut, Cancelled, Failed. To learn more about these events, see `Monitoring Commands`_ in the *Amazon Elastic Compute Cloud User Guide* .

                
                

                - *(string) --* 
            
              

              - **NotificationType** *(string) --* 

                Command: Receive notification when the status of a command changes. Invocation: For commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. 

                
          
        
      
    

.. py:class:: SSM.Paginator.ListDocuments

  ::

    
    paginator = client.get_paginator('list_documents')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`SSM.Client.list_documents`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DocumentFilterList=[
              {
                  'key': 'Name'|'Owner'|'PlatformTypes',
                  'value': 'string'
              },
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type DocumentFilterList: list
    :param DocumentFilterList: 

      One or more filters. Use a filter to return a more specific list of results.

      

    
      - *(dict) --* 

        Describes a filter.

        

      
        - **key** *(string) --* **[REQUIRED]** 

          The name of the filter.

          

        
        - **value** *(string) --* **[REQUIRED]** 

          The value of the filter.

          

        
      
  
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
            'DocumentIdentifiers': [
                {
                    'Name': 'string',
                    'Owner': 'string',
                    'PlatformTypes': [
                        'Windows'|'Linux',
                    ]
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DocumentIdentifiers** *(list) --* 

          The names of the SSM documents.

          
          

          - *(dict) --* 

            Describes the name of an SSM document.

            
            

            - **Name** *(string) --* 

              The name of the SSM document.

              
            

            - **Owner** *(string) --* 

              The AWS user account of the person who created the document.

              
            

            - **PlatformTypes** *(list) --* 

              The operating system platform. 

              
              

              - *(string) --* 
          
        
      
    