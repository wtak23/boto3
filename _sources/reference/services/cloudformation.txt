

.. _AWS\:\:IAM\:\:Group: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-group.html
.. _Template Anatomy: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html
.. _AWS CloudFormation User Guide: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/
.. _AWS Resource Types Reference: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html
.. _AWS\:\:IAM\:\:Role: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-role.html
.. _Parameter: http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Parameter.html
.. _Controlling Access with AWS Identity and Access Management: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html
.. _AWS\:\:IAM\:\:InstanceProfile: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-instanceprofile.html
.. _AWS\:\:IAM\:\:UserToGroupAddition: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-addusertogroup.html
.. _Acknowledging IAM Resources in AWS CloudFormation Templates: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html#capabilities
.. _SNS console: https://console.aws.amazon.com/sns
.. _fix the error: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/troubleshooting.html#troubleshooting-errors-update-rollback-failed
.. _AWS\:\:IAM\:\:User: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-user.html
.. _AWS\:\:IAM\:\:AccessKey: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-accesskey.html
.. _Updating a Stack: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks.html
.. _Metadata Attribute: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-attribute-metadata.html
.. _Updating Stacks Using Change Sets: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-changesets.html
.. _property: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html
.. _AWS\:\:IAM\:\:Policy: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-policy.html
.. _Stacks: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/concept-stack.html
.. _Prevent Updates to Stack Resources: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/protect-stack-resources.html


**************
CloudFormation
**************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: CloudFormation.Client

  A low-level client representing AWS CloudFormation::

    
    import boto3
    
    client = boto3.client('cloudformation')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`cancel_update_stack`

  
  *   :py:meth:`continue_update_rollback`

  
  *   :py:meth:`create_change_set`

  
  *   :py:meth:`create_stack`

  
  *   :py:meth:`delete_change_set`

  
  *   :py:meth:`delete_stack`

  
  *   :py:meth:`describe_account_limits`

  
  *   :py:meth:`describe_change_set`

  
  *   :py:meth:`describe_stack_events`

  
  *   :py:meth:`describe_stack_resource`

  
  *   :py:meth:`describe_stack_resources`

  
  *   :py:meth:`describe_stacks`

  
  *   :py:meth:`estimate_template_cost`

  
  *   :py:meth:`execute_change_set`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_stack_policy`

  
  *   :py:meth:`get_template`

  
  *   :py:meth:`get_template_summary`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_change_sets`

  
  *   :py:meth:`list_stack_resources`

  
  *   :py:meth:`list_stacks`

  
  *   :py:meth:`set_stack_policy`

  
  *   :py:meth:`signal_resource`

  
  *   :py:meth:`update_stack`

  
  *   :py:meth:`validate_template`

  

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


  .. py:method:: cancel_update_stack(**kwargs)

    

    Cancels an update on the specified stack. If the call completes successfully, the stack rolls back the update and reverts to the previous stack configuration.

     

    .. note::

       

      You can cancel only stacks that are in the UPDATE_IN_PROGRESS state.

       

    

    **Request Syntax** 
    ::

      response = client.cancel_update_stack(
          StackName='string'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or the unique stack ID that is associated with the stack.

      

    
    
    :returns: None

  .. py:method:: continue_update_rollback(**kwargs)

    

    For a specified stack that is in the ``UPDATE_ROLLBACK_FAILED`` state, continues rolling it back to the ``UPDATE_ROLLBACK_COMPLETE`` state. Depending on the cause of the failure, you can manually `fix the error`_ and continue the rollback. By continuing the rollback, you can return your stack to a working state (the ``UPDATE_ROLLBACK_COMPLETE`` state), and then try to update the stack again.

     

    A stack goes into the ``UPDATE_ROLLBACK_FAILED`` state when AWS CloudFormation cannot roll back all changes after a failed stack update. For example, you might have a stack that is rolling back to an old database instance that was deleted outside of AWS CloudFormation. Because AWS CloudFormation doesn't know the database was deleted, it assumes that the database instance still exists and attempts to roll back to it, causing the update rollback to fail.

    

    **Request Syntax** 
    ::

      response = client.continue_update_rollback(
          StackName='string'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or the unique ID of the stack that you want to continue rolling back.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  ContinueUpdateRollback action.

        
    

  .. py:method:: create_change_set(**kwargs)

    

    Creates a list of changes for a stack. AWS CloudFormation generates the change set by comparing the stack's information with the information that you submit. A change set can help you understand which resources AWS CloudFormation will change and how it will change them before you update your stack. Change sets allow you to check before you make a change so that you don't delete or replace critical resources.

     

    AWS CloudFormation doesn't make any changes to the stack when you create a change set. To make the specified changes, you must execute the change set by using the  ExecuteChangeSet action.

     

    After the call successfully completes, AWS CloudFormation starts creating the change set. To check the status of the change set, use the  DescribeChangeSet action.

    

    **Request Syntax** 
    ::

      response = client.create_change_set(
          StackName='string',
          TemplateBody='string',
          TemplateURL='string',
          UsePreviousTemplate=True|False,
          Parameters=[
              {
                  'ParameterKey': 'string',
                  'ParameterValue': 'string',
                  'UsePreviousValue': True|False
              },
          ],
          Capabilities=[
              'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
          ],
          ResourceTypes=[
              'string',
          ],
          NotificationARNs=[
              'string',
          ],
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          ChangeSetName='string',
          ClientToken='string',
          Description='string'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or the unique ID of the stack for which you are creating a change set. AWS CloudFormation generates the change set by comparing this stack's information with the information that you submit, such as a modified template or different parameter input values.

      

    
    :type TemplateBody: string
    :param TemplateBody: 

      A structure that contains the body of the revised template, with a minimum length of 1 byte and a maximum length of 51,200 bytes. AWS CloudFormation generates the change set by comparing this template with the template of the stack that you specified.

       

      Conditional: You must specify only ``TemplateBody`` or ``TemplateURL`` .

      

    
    :type TemplateURL: string
    :param TemplateURL: 

      The location of the file that contains the revised template. The URL must point to a template (max size: 460,800 bytes) that is located in an S3 bucket. AWS CloudFormation generates the change set by comparing this template with the stack that you specified.

       

      Conditional: You must specify only ``TemplateBody`` or ``TemplateURL`` .

      

    
    :type UsePreviousTemplate: boolean
    :param UsePreviousTemplate: 

      Whether to reuse the template that is associated with the stack to create the change set.

      

    
    :type Parameters: list
    :param Parameters: 

      A list of ``Parameter`` structures that specify input parameters for the change set. For more information, see the `Parameter`_ data type.

      

    
      - *(dict) --* 

        The Parameter data type.

        

      
        - **ParameterKey** *(string) --* 

          The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

          

        
        - **ParameterValue** *(string) --* 

          The value associated with the parameter.

          

        
        - **UsePreviousValue** *(boolean) --* 

          During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

          

        
      
  
    :type Capabilities: list
    :param Capabilities: 

      A list of values that you must specify before AWS CloudFormation can update certain stacks. Some stack templates might include resources that can affect permissions in your AWS account, for example, by creating new AWS Identity and Access Management (IAM) users. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter.

       

      The only valid values are ``CAPABILITY_IAM`` and ``CAPABILITY_NAMED_IAM`` . The following resources require you to specify this parameter: `AWS\:\:IAM\:\:AccessKey`_ , `AWS\:\:IAM\:\:Group`_ , `AWS\:\:IAM\:\:InstanceProfile`_ , `AWS\:\:IAM\:\:Policy`_ , `AWS\:\:IAM\:\:Role`_ , `AWS\:\:IAM\:\:User`_ , and `AWS\:\:IAM\:\:UserToGroupAddition`_ . If your stack template contains these resources, we recommend that you review all permissions associated with them and edit their permissions if necessary.

       

      If you have IAM resources, you can specify either capability. If you have IAM resources with custom names, you must specify ``CAPABILITY_NAMED_IAM`` . If you don't specify this parameter, this action returns an ``InsufficientCapabilities`` error.

       

      For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates`_ .

      

    
      - *(string) --* 

      
  
    :type ResourceTypes: list
    :param ResourceTypes: 

      The template resource types that you have permissions to work with if you execute this change set, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` .

       

      If the list of resource types doesn't include a resource type that you're updating, the stack update fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for condition keys in IAM policies for AWS CloudFormation. For more information, see `Controlling Access with AWS Identity and Access Management`_ in the AWS CloudFormation User Guide.

      

    
      - *(string) --* 

      
  
    :type NotificationARNs: list
    :param NotificationARNs: 

      The Amazon Resource Names (ARNs) of Amazon Simple Notification Service (Amazon SNS) topics that AWS CloudFormation associates with the stack. To remove all associated notification topics, specify an empty list.

      

    
      - *(string) --* 

      
  
    :type Tags: list
    :param Tags: 

      Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to resources in the stack. You can specify a maximum of 10 tags.

      

    
      - *(dict) --* 

        The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

        

      
        - **Key** *(string) --* 

           *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

          

        
        - **Value** *(string) --* 

           *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

          

        
      
  
    :type ChangeSetName: string
    :param ChangeSetName: **[REQUIRED]** 

      The name of the change set. The name must be unique among all change sets that are associated with the specified stack.

       

      A change set name can contain only alphanumeric, case sensitive characters and hyphens. It must start with an alphabetic character and cannot exceed 128 characters.

      

    
    :type ClientToken: string
    :param ClientToken: 

      A unique identifier for this ``CreateChangeSet`` request. Specify this token if you plan to retry requests so that AWS CloudFormation knows that you're not attempting to create another change set with the same name. You might retry ``CreateChangeSet`` requests to ensure that AWS CloudFormation successfully received them.

      

    
    :type Description: string
    :param Description: 

      A description to help you identify this change set.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Id': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  CreateChangeSet action.

        
        

        - **Id** *(string) --* 

          The Amazon Resource Name (ARN) of the change set.

          
    

  .. py:method:: create_stack(**kwargs)

    

    Creates a stack as specified in the template. After the call completes successfully, the stack creation starts. You can check the status of the stack via the  DescribeStacks API.

    

    **Request Syntax** 
    ::

      response = client.create_stack(
          StackName='string',
          TemplateBody='string',
          TemplateURL='string',
          Parameters=[
              {
                  'ParameterKey': 'string',
                  'ParameterValue': 'string',
                  'UsePreviousValue': True|False
              },
          ],
          DisableRollback=True|False,
          TimeoutInMinutes=123,
          NotificationARNs=[
              'string',
          ],
          Capabilities=[
              'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
          ],
          ResourceTypes=[
              'string',
          ],
          OnFailure='DO_NOTHING'|'ROLLBACK'|'DELETE',
          StackPolicyBody='string',
          StackPolicyURL='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name that is associated with the stack. The name must be unique in the region in which you are creating the stack.

       

      .. note::

         

        A stack name can contain only alphanumeric characters (case sensitive) and hyphens. It must start with an alphabetic character and cannot be longer than 128 characters.

         

      

    
    :type TemplateBody: string
    :param TemplateBody: 

      Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must specify either the ``TemplateBody`` or the ``TemplateURL`` parameter, but not both.

      

    
    :type TemplateURL: string
    :param TemplateURL: 

      Location of file containing the template body. The URL must point to a template (max size: 460,800 bytes) that is located in an Amazon S3 bucket. For more information, go to the `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must specify either the ``TemplateBody`` or the ``TemplateURL`` parameter, but not both.

      

    
    :type Parameters: list
    :param Parameters: 

      A list of ``Parameter`` structures that specify input parameters for the stack. For more information, see the `Parameter`_ data type.

      

    
      - *(dict) --* 

        The Parameter data type.

        

      
        - **ParameterKey** *(string) --* 

          The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

          

        
        - **ParameterValue** *(string) --* 

          The value associated with the parameter.

          

        
        - **UsePreviousValue** *(boolean) --* 

          During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

          

        
      
  
    :type DisableRollback: boolean
    :param DisableRollback: 

      Set to ``true`` to disable rollback of the stack if stack creation failed. You can specify either ``DisableRollback`` or ``OnFailure`` , but not both.

       

      Default: ``false``  

      

    
    :type TimeoutInMinutes: integer
    :param TimeoutInMinutes: 

      The amount of time that can pass before the stack status becomes CREATE_FAILED; if ``DisableRollback`` is not set or is set to ``false`` , the stack will be rolled back.

      

    
    :type NotificationARNs: list
    :param NotificationARNs: 

      The Simple Notification Service (SNS) topic ARNs to publish stack related events. You can find your SNS topic ARNs using the `SNS console`_ or your Command Line Interface (CLI).

      

    
      - *(string) --* 

      
  
    :type Capabilities: list
    :param Capabilities: 

      A list of values that you must specify before AWS CloudFormation can create certain stacks. Some stack templates might include resources that can affect permissions in your AWS account, for example, by creating new AWS Identity and Access Management (IAM) users. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter.

       

      The only valid values are ``CAPABILITY_IAM`` and ``CAPABILITY_NAMED_IAM`` . The following resources require you to specify this parameter: `AWS\:\:IAM\:\:AccessKey`_ , `AWS\:\:IAM\:\:Group`_ , `AWS\:\:IAM\:\:InstanceProfile`_ , `AWS\:\:IAM\:\:Policy`_ , `AWS\:\:IAM\:\:Role`_ , `AWS\:\:IAM\:\:User`_ , and `AWS\:\:IAM\:\:UserToGroupAddition`_ . If your stack template contains these resources, we recommend that you review all permissions associated with them and edit their permissions if necessary.

       

      If you have IAM resources, you can specify either capability. If you have IAM resources with custom names, you must specify ``CAPABILITY_NAMED_IAM`` . If you don't specify this parameter, this action returns an ``InsufficientCapabilities`` error.

       

      For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates`_ .

      

    
      - *(string) --* 

      
  
    :type ResourceTypes: list
    :param ResourceTypes: 

      The template resource types that you have permissions to work with for this create stack action, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` . Use the following syntax to describe template resource types: ``AWS::*`` (for all AWS resource), ``Custom::*`` (for all custom resources), ``Custom::*logical_ID* `` (for a specific custom resource), ``AWS::*service_name* ::*`` (for all resources of a particular AWS service), and ``AWS::*service_name* ::*resource_logical_ID* `` (for a specific AWS resource).

       

      If the list of resource types doesn't include a resource that you're creating, the stack creation fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for AWS CloudFormation-specific condition keys in IAM policies. For more information, see `Controlling Access with AWS Identity and Access Management`_ .

      

    
      - *(string) --* 

      
  
    :type OnFailure: string
    :param OnFailure: 

      Determines what action will be taken if stack creation fails. This must be one of: DO_NOTHING, ROLLBACK, or DELETE. You can specify either ``OnFailure`` or ``DisableRollback`` , but not both.

       

      Default: ``ROLLBACK``  

      

    
    :type StackPolicyBody: string
    :param StackPolicyBody: 

      Structure containing the stack policy body. For more information, go to `Prevent Updates to Stack Resources`_ in the AWS CloudFormation User Guide. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

      

    
    :type StackPolicyURL: string
    :param StackPolicyURL: 

      Location of a file containing the stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

      

    
    :type Tags: list
    :param Tags: 

      Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to the resources created in the stack. A maximum number of 10 tags can be specified.

      

    
      - *(dict) --* 

        The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

        

      
        - **Key** *(string) --* 

           *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

          

        
        - **Value** *(string) --* 

           *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StackId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  CreateStack action.

        
        

        - **StackId** *(string) --* 

          Unique identifier of the stack.

          
    

  .. py:method:: delete_change_set(**kwargs)

    

    Deletes the specified change set. Deleting change sets ensures that no one executes the wrong change set.

     

    If the call successfully completes, AWS CloudFormation successfully deleted the change set.

    

    **Request Syntax** 
    ::

      response = client.delete_change_set(
          ChangeSetName='string',
          StackName='string'
      )
    :type ChangeSetName: string
    :param ChangeSetName: **[REQUIRED]** 

      The name or Amazon Resource Name (ARN) of the change set that you want to delete.

      

    
    :type StackName: string
    :param StackName: 

      If you specified the name of a change set to delete, specify the stack name or ID (ARN) that is associated with it.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  DeleteChangeSet action.

        
    

  .. py:method:: delete_stack(**kwargs)

    

    Deletes a specified stack. Once the call completes successfully, stack deletion starts. Deleted stacks do not show up in the  DescribeStacks API if the deletion has been completed successfully.

    

    **Request Syntax** 
    ::

      response = client.delete_stack(
          StackName='string',
          RetainResources=[
              'string',
          ]
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or the unique stack ID that is associated with the stack.

      

    
    :type RetainResources: list
    :param RetainResources: 

      For stacks in the ``DELETE_FAILED`` state, a list of resource logical IDs that are associated with the resources you want to retain. During deletion, AWS CloudFormation deletes the stack but does not delete the retained resources.

       

      Retaining resources is useful when you cannot delete a resource, such as a non-empty S3 bucket, but you want to delete the stack.

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: describe_account_limits(**kwargs)

    

    Retrieves your account's AWS CloudFormation limits, such as the maximum number of stacks that you can create in your account.

    

    **Request Syntax** 
    ::

      response = client.describe_account_limits(
          NextToken='string'
      )
    :type NextToken: string
    :param NextToken: 

      A string that identifies the next page of limits that you want to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AccountLimits': [
                {
                    'Name': 'string',
                    'Value': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  DescribeAccountLimits action.

        
        

        - **AccountLimits** *(list) --* 

          An account limit structure that contain a list of AWS CloudFormation account limits and their values.

          
          

          - *(dict) --* 

            The AccountLimit data type.

            
            

            - **Name** *(string) --* 

              The name of the account limit. Currently, the only account limit is ``StackLimit`` .

              
            

            - **Value** *(integer) --* 

              The value that is associated with the account limit name.

              
        
      
        

        - **NextToken** *(string) --* 

          If the output exceeds 1 MB in size, a string that identifies the next page of limits. If no additional page exists, this value is null.

          
    

  .. py:method:: describe_change_set(**kwargs)

    

    Returns the inputs for the change set and a list of changes that AWS CloudFormation will make if you execute the change set. For more information, see `Updating Stacks Using Change Sets`_ in the AWS CloudFormation User Guide.

    

    **Request Syntax** 
    ::

      response = client.describe_change_set(
          ChangeSetName='string',
          StackName='string',
          NextToken='string'
      )
    :type ChangeSetName: string
    :param ChangeSetName: **[REQUIRED]** 

      The name or Amazon Resource Name (ARN) of the change set that you want to describe.

      

    
    :type StackName: string
    :param StackName: 

      If you specified the name of a change set, specify the stack name or ID (ARN) of the change set you want to describe.

      

    
    :type NextToken: string
    :param NextToken: 

      A string (provided by the  DescribeChangeSet response output) that identifies the next page of information that you want to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeSetName': 'string',
            'ChangeSetId': 'string',
            'StackId': 'string',
            'StackName': 'string',
            'Description': 'string',
            'Parameters': [
                {
                    'ParameterKey': 'string',
                    'ParameterValue': 'string',
                    'UsePreviousValue': True|False
                },
            ],
            'CreationTime': datetime(2015, 1, 1),
            'ExecutionStatus': 'UNAVAILABLE'|'AVAILABLE'|'EXECUTE_IN_PROGRESS'|'EXECUTE_COMPLETE'|'EXECUTE_FAILED'|'OBSOLETE',
            'Status': 'CREATE_PENDING'|'CREATE_IN_PROGRESS'|'CREATE_COMPLETE'|'DELETE_COMPLETE'|'FAILED',
            'StatusReason': 'string',
            'NotificationARNs': [
                'string',
            ],
            'Capabilities': [
                'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
            ],
            'Tags': [
                {
                    'Key': 'string',
                    'Value': 'string'
                },
            ],
            'Changes': [
                {
                    'Type': 'Resource',
                    'ResourceChange': {
                        'Action': 'Add'|'Modify'|'Remove',
                        'LogicalResourceId': 'string',
                        'PhysicalResourceId': 'string',
                        'ResourceType': 'string',
                        'Replacement': 'True'|'False'|'Conditional',
                        'Scope': [
                            'Properties'|'Metadata'|'CreationPolicy'|'UpdatePolicy'|'DeletionPolicy'|'Tags',
                        ],
                        'Details': [
                            {
                                'Target': {
                                    'Attribute': 'Properties'|'Metadata'|'CreationPolicy'|'UpdatePolicy'|'DeletionPolicy'|'Tags',
                                    'Name': 'string',
                                    'RequiresRecreation': 'Never'|'Conditionally'|'Always'
                                },
                                'Evaluation': 'Static'|'Dynamic',
                                'ChangeSource': 'ResourceReference'|'ParameterReference'|'ResourceAttribute'|'DirectModification'|'Automatic',
                                'CausingEntity': 'string'
                            },
                        ]
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  DescribeChangeSet action.

        
        

        - **ChangeSetName** *(string) --* 

          The name of the change set.

          
        

        - **ChangeSetId** *(string) --* 

          The ARN of the change set.

          
        

        - **StackId** *(string) --* 

          The ARN of the stack that is associated with the change set.

          
        

        - **StackName** *(string) --* 

          The name of the stack that is associated with the change set.

          
        

        - **Description** *(string) --* 

          Information about the change set.

          
        

        - **Parameters** *(list) --* 

          A list of ``Parameter`` structures that describes the input parameters and their values used to create the change set. For more information, see the `Parameter`_ data type.

          
          

          - *(dict) --* 

            The Parameter data type.

            
            

            - **ParameterKey** *(string) --* 

              The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

              
            

            - **ParameterValue** *(string) --* 

              The value associated with the parameter.

              
            

            - **UsePreviousValue** *(boolean) --* 

              During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

              
        
      
        

        - **CreationTime** *(datetime) --* 

          The start time when the change set was created, in UTC.

          
        

        - **ExecutionStatus** *(string) --* 

          If the change set execution status is ``AVAILABLE`` , you can execute the change set. If you can’t execute the change set, the status indicates why. For example, a change set might be in an ``UNAVAILABLE`` state because AWS CloudFormation is still creating it or in an ``OBSOLETE`` state because the stack was already updated.

          
        

        - **Status** *(string) --* 

          The current status of the change set, such as ``CREATE_IN_PROGRESS`` , ``CREATE_COMPLETE`` , or ``FAILED`` .

          
        

        - **StatusReason** *(string) --* 

          A description of the change set's status. For example, if your attempt to create a change set failed, AWS CloudFormation shows the error message.

          
        

        - **NotificationARNs** *(list) --* 

          The ARNs of the Amazon Simple Notification Service (Amazon SNS) topics that will be associated with the stack if you execute the change set.

          
          

          - *(string) --* 
      
        

        - **Capabilities** *(list) --* 

          If you execute the change set, the list of capabilities that were explicitly acknowledged when the change set was created.

          
          

          - *(string) --* 
      
        

        - **Tags** *(list) --* 

          If you execute the change set, the tags that will be associated with the stack.

          
          

          - *(dict) --* 

            The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

            
            

            - **Key** *(string) --* 

               *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

              
            

            - **Value** *(string) --* 

               *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

              
        
      
        

        - **Changes** *(list) --* 

          A list of ``Change`` structures that describes the resources AWS CloudFormation changes if you execute the change set.

          
          

          - *(dict) --* 

            The ``Change`` structure describes the changes AWS CloudFormation will perform if you execute the change set.

            
            

            - **Type** *(string) --* 

              The type of entity that AWS CloudFormation changes. Currently, the only entity type is ``Resource`` .

              
            

            - **ResourceChange** *(dict) --* 

              A ``ResourceChange`` structure that describes the resource and action that AWS CloudFormation will perform.

              
              

              - **Action** *(string) --* 

                The action that AWS CloudFormation takes on the resource, such as ``Add`` (adds a new resource), ``Modify`` (changes a resource), or ``Remove`` (deletes a resource).

                
              

              - **LogicalResourceId** *(string) --* 

                The resource's logical ID, which is defined in the stack's template.

                
              

              - **PhysicalResourceId** *(string) --* 

                The resource's physical ID (resource name). Resources that you are adding don't have physical IDs because they haven't been created.

                
              

              - **ResourceType** *(string) --* 

                The type of AWS CloudFormation resource, such as ``AWS::S3::Bucket`` .

                
              

              - **Replacement** *(string) --* 

                For the ``Modify`` action, indicates whether AWS CloudFormation will replace the resource by creating a new one and deleting the old one. This value depends on the value of the ``RequiresRecreation`` property in the ``ResourceTargetDefinition`` structure. For example, if the ``RequiresRecreation`` field is ``Always`` and the ``Evaluation`` field is ``Static`` , ``Replacement`` is ``True`` . If the ``RequiresRecreation`` field is ``Always`` and the ``Evaluation`` field is ``Dynamic`` , ``Replacement`` is ``Conditionally`` .

                 

                If you have multiple changes with different ``RequiresRecreation`` values, the ``Replacement`` value depends on the change with the most impact. A ``RequiresRecreation`` value of ``Always`` has the most impact, followed by ``Conditionally`` , and then ``Never`` .

                
              

              - **Scope** *(list) --* 

                For the ``Modify`` action, indicates which resource attribute is triggering this update, such as a change in the resource attribute's ``Metadata`` , ``Properties`` , or ``Tags`` .

                
                

                - *(string) --* 
            
              

              - **Details** *(list) --* 

                For the ``Modify`` action, a list of ``ResourceChangeDetail`` structures that describes the changes that AWS CloudFormation will make to the resource. 

                
                

                - *(dict) --* 

                  For a resource with ``Modify`` as the action, the ``ResourceChange`` structure describes the changes AWS CloudFormation will make to that resource.

                  
                  

                  - **Target** *(dict) --* 

                    A ``ResourceTargetDefinition`` structure that describes the field that AWS CloudFormation will change and whether the resource will be recreated.

                    
                    

                    - **Attribute** *(string) --* 

                      Indicates which resource attribute is triggering this update, such as a change in the resource attribute's ``Metadata`` , ``Properties`` , or ``Tags`` .

                      
                    

                    - **Name** *(string) --* 

                      If the ``Attribute`` value is ``Properties`` , the name of the property. For all other attributes, the value is null.

                      
                    

                    - **RequiresRecreation** *(string) --* 

                      If the ``Attribute`` value is ``Properties`` , indicates whether a change to this property causes the resource to be recreated. The value can be ``Never`` , ``Always`` , or ``Conditionally`` . To determine the conditions for a ``Conditionally`` recreation, see the update behavior for that `property`_ in the AWS CloudFormation User Guide.

                      
                
                  

                  - **Evaluation** *(string) --* 

                    Indicates whether AWS CloudFormation can determine the target value, and whether the target value will change before you execute a change set.

                     

                    For ``Static`` evaluations, AWS CloudFormation can determine that the target value will change, and its value. For example, if you directly modify the ``InstanceType`` property of an EC2 instance, AWS CloudFormation knows that this property value will change, and its value, so this is a ``Static`` evaluation.

                     

                    For ``Dynamic`` evaluations, cannot determine the target value because it depends on the result of an intrinsic function, such as a ``Ref`` or ``Fn::GetAtt`` intrinsic function, when the stack is updated. For example, if your template includes a reference to a resource that is conditionally recreated, the value of the reference (the physical ID of the resource) might change, depending on if the resource is recreated. If the resource is recreated, it will have a new physical ID, so all references to that resource will also be updated.

                    
                  

                  - **ChangeSource** *(string) --* 

                    The group to which the ``CausingEntity`` value belongs. There are five entity groups:

                     

                     
                    * ``ResourceReference`` entities are ``Ref`` intrinsic functions that refer to resources in the template, such as ``{ "Ref" : "MyEC2InstanceResource" }`` . 
                     
                    * ``ParameterReference`` entities are ``Ref`` intrinsic functions that get template parameter values, such as ``{ "Ref" : "MyPasswordParameter" }`` . 
                     
                    * ``ResourceAttribute`` entities are ``Fn::GetAtt`` intrinsic functions that get resource attribute values, such as ``{ "Fn::GetAtt" : [ "MyEC2InstanceResource", "PublicDnsName" ] }`` . 
                     
                    * ``DirectModification`` entities are changes that are made directly to the template. 
                     
                    * ``Automatic`` entities are ``AWS::CloudFormation::Stack`` resource types, which are also known as nested stacks. If you made no changes to the ``AWS::CloudFormation::Stack`` resource, AWS CloudFormation sets the ``ChangeSource`` to ``Automatic`` because the nested stack's template might have changed. Changes to a nested stack's template aren't visible to AWS CloudFormation until you run an update on the parent stack. 
                     

                    
                  

                  - **CausingEntity** *(string) --* 

                    The identity of the entity that triggered this change. This entity is a member of the group that is specified by the ``ChangeSource`` field. For example, if you modified the value of the ``KeyPairName`` parameter, the ``CausingEntity`` is the name of the parameter (``KeyPairName`` ).

                     

                    If the ``ChangeSource`` value is ``DirectModification`` , no value is given for ``CausingEntity`` .

                    
              
            
          
        
      
        

        - **NextToken** *(string) --* 

          If the output exceeds 1 MB, a string that identifies the next page of changes. If there is no additional page, this value is null.

          
    

  .. py:method:: describe_stack_events(**kwargs)

    

    Returns all stack related events for a specified stack in reverse chronological order. For more information about a stack's event history, go to `Stacks`_ in the AWS CloudFormation User Guide.

     

    .. note::

       

      You can list events for stacks that have failed to create or have been deleted by specifying the unique stack identifier (stack ID).

       

    

    **Request Syntax** 
    ::

      response = client.describe_stack_events(
          StackName='string',
          NextToken='string'
      )
    :type StackName: string
    :param StackName: 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
    :type NextToken: string
    :param NextToken: 

      A string that identifies the next page of events that you want to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StackEvents': [
                {
                    'StackId': 'string',
                    'EventId': 'string',
                    'StackName': 'string',
                    'LogicalResourceId': 'string',
                    'PhysicalResourceId': 'string',
                    'ResourceType': 'string',
                    'Timestamp': datetime(2015, 1, 1),
                    'ResourceStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'DELETE_SKIPPED'|'UPDATE_IN_PROGRESS'|'UPDATE_FAILED'|'UPDATE_COMPLETE',
                    'ResourceStatusReason': 'string',
                    'ResourceProperties': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  DescribeStackEvents action.

        
        

        - **StackEvents** *(list) --* 

          A list of ``StackEvents`` structures.

          
          

          - *(dict) --* 

            The StackEvent data type.

            
            

            - **StackId** *(string) --* 

              The unique ID name of the instance of the stack.

              
            

            - **EventId** *(string) --* 

              The unique ID of this event.

              
            

            - **StackName** *(string) --* 

              The name associated with a stack.

              
            

            - **LogicalResourceId** *(string) --* 

              The logical name of the resource specified in the template.

              
            

            - **PhysicalResourceId** *(string) --* 

              The name or unique identifier associated with the physical instance of the resource.

              
            

            - **ResourceType** *(string) --* 

              Type of resource. (For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

              
            

            - **Timestamp** *(datetime) --* 

              Time the status was updated.

              
            

            - **ResourceStatus** *(string) --* 

              Current status of the resource.

              
            

            - **ResourceStatusReason** *(string) --* 

              Success/failure message associated with the resource.

              
            

            - **ResourceProperties** *(string) --* 

              BLOB of the properties used to create the resource.

              
        
      
        

        - **NextToken** *(string) --* 

          If the output exceeds 1 MB in size, a string that identifies the next page of events. If no additional page exists, this value is null.

          
    

  .. py:method:: describe_stack_resource(**kwargs)

    

    Returns a description of the specified resource in the specified stack.

     

    For deleted stacks, DescribeStackResource returns resource information for up to 90 days after the stack has been deleted.

    

    **Request Syntax** 
    ::

      response = client.describe_stack_resource(
          StackName='string',
          LogicalResourceId='string'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
    :type LogicalResourceId: string
    :param LogicalResourceId: **[REQUIRED]** 

      The logical name of the resource as specified in the template.

       

      Default: There is no default value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StackResourceDetail': {
                'StackName': 'string',
                'StackId': 'string',
                'LogicalResourceId': 'string',
                'PhysicalResourceId': 'string',
                'ResourceType': 'string',
                'LastUpdatedTimestamp': datetime(2015, 1, 1),
                'ResourceStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'DELETE_SKIPPED'|'UPDATE_IN_PROGRESS'|'UPDATE_FAILED'|'UPDATE_COMPLETE',
                'ResourceStatusReason': 'string',
                'Description': 'string',
                'Metadata': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  DescribeStackResource action.

        
        

        - **StackResourceDetail** *(dict) --* 

          A ``StackResourceDetail`` structure containing the description of the specified resource in the specified stack.

          
          

          - **StackName** *(string) --* 

            The name associated with the stack.

            
          

          - **StackId** *(string) --* 

            Unique identifier of the stack.

            
          

          - **LogicalResourceId** *(string) --* 

            The logical name of the resource specified in the template.

            
          

          - **PhysicalResourceId** *(string) --* 

            The name or unique identifier that corresponds to a physical instance ID of a resource supported by AWS CloudFormation.

            
          

          - **ResourceType** *(string) --* 

            Type of resource. ((For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

            
          

          - **LastUpdatedTimestamp** *(datetime) --* 

            Time the status was updated.

            
          

          - **ResourceStatus** *(string) --* 

            Current status of the resource.

            
          

          - **ResourceStatusReason** *(string) --* 

            Success/failure message associated with the resource.

            
          

          - **Description** *(string) --* 

            User defined description associated with the resource.

            
          

          - **Metadata** *(string) --* 

            The JSON format content of the ``Metadata`` attribute declared for the resource. For more information, see `Metadata Attribute`_ in the AWS CloudFormation User Guide.

            
      
    

  .. py:method:: describe_stack_resources(**kwargs)

    

    Returns AWS resource descriptions for running and deleted stacks. If ``StackName`` is specified, all the associated resources that are part of the stack are returned. If ``PhysicalResourceId`` is specified, the associated resources of the stack that the resource belongs to are returned.

     

    .. note::

       

      Only the first 100 resources will be returned. If your stack has more resources than this, you should use ``ListStackResources`` instead.

       

     

    For deleted stacks, ``DescribeStackResources`` returns resource information for up to 90 days after the stack has been deleted.

     

    You must specify either ``StackName`` or ``PhysicalResourceId`` , but not both. In addition, you can specify ``LogicalResourceId`` to filter the returned result. For more information about resources, the ``LogicalResourceId`` and ``PhysicalResourceId`` , go to the `AWS CloudFormation User Guide`_ .

     

    .. note::

       

      A ``ValidationError`` is returned if you specify both ``StackName`` and ``PhysicalResourceId`` in the same request.

       

    

    **Request Syntax** 
    ::

      response = client.describe_stack_resources(
          StackName='string',
          LogicalResourceId='string',
          PhysicalResourceId='string'
      )
    :type StackName: string
    :param StackName: 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

       

      Required: Conditional. If you do not specify ``StackName`` , you must specify ``PhysicalResourceId`` .

      

    
    :type LogicalResourceId: string
    :param LogicalResourceId: 

      The logical name of the resource as specified in the template.

       

      Default: There is no default value.

      

    
    :type PhysicalResourceId: string
    :param PhysicalResourceId: 

      The name or unique identifier that corresponds to a physical instance ID of a resource supported by AWS CloudFormation.

       

      For example, for an Amazon Elastic Compute Cloud (EC2) instance, ``PhysicalResourceId`` corresponds to the ``InstanceId`` . You can pass the EC2 ``InstanceId`` to ``DescribeStackResources`` to find which stack the instance belongs to and what other resources are part of the stack.

       

      Required: Conditional. If you do not specify ``PhysicalResourceId`` , you must specify ``StackName`` .

       

      Default: There is no default value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StackResources': [
                {
                    'StackName': 'string',
                    'StackId': 'string',
                    'LogicalResourceId': 'string',
                    'PhysicalResourceId': 'string',
                    'ResourceType': 'string',
                    'Timestamp': datetime(2015, 1, 1),
                    'ResourceStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'DELETE_SKIPPED'|'UPDATE_IN_PROGRESS'|'UPDATE_FAILED'|'UPDATE_COMPLETE',
                    'ResourceStatusReason': 'string',
                    'Description': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  DescribeStackResources action.

        
        

        - **StackResources** *(list) --* 

          A list of ``StackResource`` structures.

          
          

          - *(dict) --* 

            The StackResource data type.

            
            

            - **StackName** *(string) --* 

              The name associated with the stack.

              
            

            - **StackId** *(string) --* 

              Unique identifier of the stack.

              
            

            - **LogicalResourceId** *(string) --* 

              The logical name of the resource specified in the template.

              
            

            - **PhysicalResourceId** *(string) --* 

              The name or unique identifier that corresponds to a physical instance ID of a resource supported by AWS CloudFormation.

              
            

            - **ResourceType** *(string) --* 

              Type of resource. (For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

              
            

            - **Timestamp** *(datetime) --* 

              Time the status was updated.

              
            

            - **ResourceStatus** *(string) --* 

              Current status of the resource.

              
            

            - **ResourceStatusReason** *(string) --* 

              Success/failure message associated with the resource.

              
            

            - **Description** *(string) --* 

              User defined description associated with the resource.

              
        
      
    

  .. py:method:: describe_stacks(**kwargs)

    

    Returns the description for the specified stack; if no stack name was specified, then it returns the description for all the stacks created.

    

    **Request Syntax** 
    ::

      response = client.describe_stacks(
          StackName='string',
          NextToken='string'
      )
    :type StackName: string
    :param StackName: 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
    :type NextToken: string
    :param NextToken: 

      A string that identifies the next page of stacks that you want to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Stacks': [
                {
                    'StackId': 'string',
                    'StackName': 'string',
                    'Description': 'string',
                    'Parameters': [
                        {
                            'ParameterKey': 'string',
                            'ParameterValue': 'string',
                            'UsePreviousValue': True|False
                        },
                    ],
                    'CreationTime': datetime(2015, 1, 1),
                    'LastUpdatedTime': datetime(2015, 1, 1),
                    'StackStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'ROLLBACK_IN_PROGRESS'|'ROLLBACK_FAILED'|'ROLLBACK_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'UPDATE_IN_PROGRESS'|'UPDATE_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_COMPLETE'|'UPDATE_ROLLBACK_IN_PROGRESS'|'UPDATE_ROLLBACK_FAILED'|'UPDATE_ROLLBACK_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_ROLLBACK_COMPLETE',
                    'StackStatusReason': 'string',
                    'DisableRollback': True|False,
                    'NotificationARNs': [
                        'string',
                    ],
                    'TimeoutInMinutes': 123,
                    'Capabilities': [
                        'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
                    ],
                    'Outputs': [
                        {
                            'OutputKey': 'string',
                            'OutputValue': 'string',
                            'Description': 'string'
                        },
                    ],
                    'Tags': [
                        {
                            'Key': 'string',
                            'Value': 'string'
                        },
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  DescribeStacks action.

        
        

        - **Stacks** *(list) --* 

          A list of stack structures.

          
          

          - *(dict) --* 

            The Stack data type.

            
            

            - **StackId** *(string) --* 

              Unique identifier of the stack.

              
            

            - **StackName** *(string) --* 

              The name associated with the stack.

              
            

            - **Description** *(string) --* 

              A user-defined description associated with the stack.

              
            

            - **Parameters** *(list) --* 

              A list of ``Parameter`` structures.

              
              

              - *(dict) --* 

                The Parameter data type.

                
                

                - **ParameterKey** *(string) --* 

                  The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

                  
                

                - **ParameterValue** *(string) --* 

                  The value associated with the parameter.

                  
                

                - **UsePreviousValue** *(boolean) --* 

                  During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

                  
            
          
            

            - **CreationTime** *(datetime) --* 

              The time at which the stack was created.

              
            

            - **LastUpdatedTime** *(datetime) --* 

              The time the stack was last updated. This field will only be returned if the stack has been updated at least once.

              
            

            - **StackStatus** *(string) --* 

              Current status of the stack.

              
            

            - **StackStatusReason** *(string) --* 

              Success/failure message associated with the stack status.

              
            

            - **DisableRollback** *(boolean) --* 

              Boolean to enable or disable rollback on stack creation failures:

               

               
              * ``true`` : disable rollback 
               
              * ``false`` : enable rollback 
               

              
            

            - **NotificationARNs** *(list) --* 

              SNS topic ARNs to which stack related events are published.

              
              

              - *(string) --* 
          
            

            - **TimeoutInMinutes** *(integer) --* 

              The amount of time within which stack creation should complete.

              
            

            - **Capabilities** *(list) --* 

              The capabilities allowed in the stack.

              
              

              - *(string) --* 
          
            

            - **Outputs** *(list) --* 

              A list of output structures.

              
              

              - *(dict) --* 

                The Output data type.

                
                

                - **OutputKey** *(string) --* 

                  The key associated with the output.

                  
                

                - **OutputValue** *(string) --* 

                  The value associated with the output.

                  
                

                - **Description** *(string) --* 

                  User defined description associated with the output.

                  
            
          
            

            - **Tags** *(list) --* 

              A list of ``Tag`` s that specify information about the stack.

              
              

              - *(dict) --* 

                The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

                
                

                - **Key** *(string) --* 

                   *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

                  
                

                - **Value** *(string) --* 

                   *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          If the output exceeds 1 MB in size, a string that identifies the next page of stacks. If no additional page exists, this value is null.

          
    

  .. py:method:: estimate_template_cost(**kwargs)

    

    Returns the estimated monthly cost of a template. The return value is an AWS Simple Monthly Calculator URL with a query string that describes the resources required to run the template.

    

    **Request Syntax** 
    ::

      response = client.estimate_template_cost(
          TemplateBody='string',
          TemplateURL='string',
          Parameters=[
              {
                  'ParameterKey': 'string',
                  'ParameterValue': 'string',
                  'UsePreviousValue': True|False
              },
          ]
      )
    :type TemplateBody: string
    :param TemplateBody: 

      Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. (For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.)

       

      Conditional: You must pass ``TemplateBody`` or ``TemplateURL`` . If both are passed, only ``TemplateBody`` is used.

      

    
    :type TemplateURL: string
    :param TemplateURL: 

      Location of file containing the template body. The URL must point to a template that is located in an Amazon S3 bucket. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must pass ``TemplateURL`` or ``TemplateBody`` . If both are passed, only ``TemplateBody`` is used.

      

    
    :type Parameters: list
    :param Parameters: 

      A list of ``Parameter`` structures that specify input parameters.

      

    
      - *(dict) --* 

        The Parameter data type.

        

      
        - **ParameterKey** *(string) --* 

          The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

          

        
        - **ParameterValue** *(string) --* 

          The value associated with the parameter.

          

        
        - **UsePreviousValue** *(boolean) --* 

          During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Url': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  EstimateTemplateCost action.

        
        

        - **Url** *(string) --* 

          An AWS Simple Monthly Calculator URL with a query string that describes the resources required to run the template.

          
    

  .. py:method:: execute_change_set(**kwargs)

    

    Updates a stack using the input information that was provided when the specified change set was created. After the call successfully completes, AWS CloudFormation starts updating the stack. Use the  DescribeStacks action to view the status of the update.

     

    When you execute a change set, AWS CloudFormation deletes all other change sets associated with the stack because they aren't valid for the updated stack.

     

    If a stack policy is associated with the stack, AWS CloudFormation enforces the policy during the update. You can't specify a temporary stack policy that overrides the current policy.

    

    **Request Syntax** 
    ::

      response = client.execute_change_set(
          ChangeSetName='string',
          StackName='string'
      )
    :type ChangeSetName: string
    :param ChangeSetName: **[REQUIRED]** 

      The name or ARN of the change set that you want use to update the specified stack.

      

    
    :type StackName: string
    :param StackName: 

      If you specified the name of a change set, specify the stack name or ID (ARN) that is associated with the change set you want to execute.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  ExecuteChangeSet action.

        
    

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


  .. py:method:: get_stack_policy(**kwargs)

    

    Returns the stack policy for a specified stack. If a stack doesn't have a policy, a null value is returned.

    

    **Request Syntax** 
    ::

      response = client.get_stack_policy(
          StackName='string'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or unique stack ID that is associated with the stack whose policy you want to get.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StackPolicyBody': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  GetStackPolicy action.

        
        

        - **StackPolicyBody** *(string) --* 

          Structure containing the stack policy body. (For more information, go to `Prevent Updates to Stack Resources`_ in the AWS CloudFormation User Guide.)

          
    

  .. py:method:: get_template(**kwargs)

    

    Returns the template body for a specified stack. You can get the template for running or deleted stacks.

     

    For deleted stacks, GetTemplate returns the template for up to 90 days after the stack has been deleted.

     

    .. note::

       

      If the template does not exist, a ``ValidationError`` is returned. 

       

    

    **Request Syntax** 
    ::

      response = client.get_template(
          StackName='string'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TemplateBody': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  GetTemplate action.

        
        

        - **TemplateBody** *(string) --* 

          Structure containing the template body. (For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.)

          
    

  .. py:method:: get_template_summary(**kwargs)

    

    Returns information about a new or existing template. The ``GetTemplateSummary`` action is useful for viewing parameter information, such as default parameter values and parameter types, before you create or update a stack.

     

    You can use the ``GetTemplateSummary`` action when you submit a template, or you can get template information for a running or deleted stack.

     

    For deleted stacks, ``GetTemplateSummary`` returns the template information for up to 90 days after the stack has been deleted. If the template does not exist, a ``ValidationError`` is returned.

    

    **Request Syntax** 
    ::

      response = client.get_template_summary(
          TemplateBody='string',
          TemplateURL='string',
          StackName='string'
      )
    :type TemplateBody: string
    :param TemplateBody: 

      Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information about templates, see `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must specify only one of the following parameters: ``StackName`` , ``TemplateBody`` , or ``TemplateURL`` .

      

    
    :type TemplateURL: string
    :param TemplateURL: 

      Location of file containing the template body. The URL must point to a template (max size: 460,800 bytes) that is located in an Amazon S3 bucket. For more information about templates, see `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must specify only one of the following parameters: ``StackName`` , ``TemplateBody`` , or ``TemplateURL`` .

      

    
    :type StackName: string
    :param StackName: 

      The name or the stack ID that is associated with the stack, which are not always interchangeable. For running stacks, you can specify either the stack's name or its unique stack ID. For deleted stack, you must specify the unique stack ID.

       

      Conditional: You must specify only one of the following parameters: ``StackName`` , ``TemplateBody`` , or ``TemplateURL`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Parameters': [
                {
                    'ParameterKey': 'string',
                    'DefaultValue': 'string',
                    'ParameterType': 'string',
                    'NoEcho': True|False,
                    'Description': 'string',
                    'ParameterConstraints': {
                        'AllowedValues': [
                            'string',
                        ]
                    }
                },
            ],
            'Description': 'string',
            'Capabilities': [
                'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
            ],
            'CapabilitiesReason': 'string',
            'ResourceTypes': [
                'string',
            ],
            'Version': 'string',
            'Metadata': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  GetTemplateSummary action.

        
        

        - **Parameters** *(list) --* 

          A list of parameter declarations that describe various properties for each parameter.

          
          

          - *(dict) --* 

            The ParameterDeclaration data type.

            
            

            - **ParameterKey** *(string) --* 

              The name that is associated with the parameter.

              
            

            - **DefaultValue** *(string) --* 

              The default value of the parameter.

              
            

            - **ParameterType** *(string) --* 

              The type of parameter.

              
            

            - **NoEcho** *(boolean) --* 

              Flag that indicates whether the parameter value is shown as plain text in logs and in the AWS Management Console.

              
            

            - **Description** *(string) --* 

              The description that is associate with the parameter.

              
            

            - **ParameterConstraints** *(dict) --* 

              The criteria that AWS CloudFormation uses to validate parameter values.

              
              

              - **AllowedValues** *(list) --* 

                A list of values that are permitted for a parameter.

                
                

                - *(string) --* 
            
          
        
      
        

        - **Description** *(string) --* 

          The value that is defined in the ``Description`` property of the template.

          
        

        - **Capabilities** *(list) --* 

          The capabilities found within the template. If your template contains IAM resources, you must specify the CAPABILITY_IAM or CAPABILITY_NAMED_IAM value for this parameter when you use the  CreateStack or  UpdateStack actions with your template; otherwise, those actions return an InsufficientCapabilities error.

           

          For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates`_ .

          
          

          - *(string) --* 
      
        

        - **CapabilitiesReason** *(string) --* 

          The list of resources that generated the values in the ``Capabilities`` response element.

          
        

        - **ResourceTypes** *(list) --* 

          A list of all the template resource types that are defined in the template, such as ``AWS::EC2::Instance`` , ``AWS::Dynamo::Table`` , and ``Custom::MyCustomInstance`` .

          
          

          - *(string) --* 
      
        

        - **Version** *(string) --* 

          The AWS template format version, which identifies the capabilities of the template.

          
        

        - **Metadata** *(string) --* 

          The value that is defined for the ``Metadata`` property of the template.

          
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: list_change_sets(**kwargs)

    

    Returns the ID and status of each active change set for a stack. For example, AWS CloudFormation lists change sets that are in the ``CREATE_IN_PROGRESS`` or ``CREATE_PENDING`` state.

    

    **Request Syntax** 
    ::

      response = client.list_change_sets(
          StackName='string',
          NextToken='string'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or the Amazon Resource Name (ARN) of the stack for which you want to list change sets.

      

    
    :type NextToken: string
    :param NextToken: 

      A string (provided by the  ListChangeSets response output) that identifies the next page of change sets that you want to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Summaries': [
                {
                    'StackId': 'string',
                    'StackName': 'string',
                    'ChangeSetId': 'string',
                    'ChangeSetName': 'string',
                    'ExecutionStatus': 'UNAVAILABLE'|'AVAILABLE'|'EXECUTE_IN_PROGRESS'|'EXECUTE_COMPLETE'|'EXECUTE_FAILED'|'OBSOLETE',
                    'Status': 'CREATE_PENDING'|'CREATE_IN_PROGRESS'|'CREATE_COMPLETE'|'DELETE_COMPLETE'|'FAILED',
                    'StatusReason': 'string',
                    'CreationTime': datetime(2015, 1, 1),
                    'Description': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  ListChangeSets action.

        
        

        - **Summaries** *(list) --* 

          A list of ``ChangeSetSummary`` structures that provides the ID and status of each change set for the specified stack.

          
          

          - *(dict) --* 

            The ``ChangeSetSummary`` structure describes a change set, its status, and the stack with which it's associated.

            
            

            - **StackId** *(string) --* 

              The ID of the stack with which the change set is associated.

              
            

            - **StackName** *(string) --* 

              The name of the stack with which the change set is associated.

              
            

            - **ChangeSetId** *(string) --* 

              The ID of the change set.

              
            

            - **ChangeSetName** *(string) --* 

              The name of the change set.

              
            

            - **ExecutionStatus** *(string) --* 

              If the change set execution status is ``AVAILABLE`` , you can execute the change set. If you can’t execute the change set, the status indicates why. For example, a change set might be in an ``UNAVAILABLE`` state because AWS CloudFormation is still creating it or in an ``OBSOLETE`` state because the stack was already updated.

              
            

            - **Status** *(string) --* 

              The state of the change set, such as ``CREATE_IN_PROGRESS`` , ``CREATE_COMPLETE`` , or ``FAILED`` .

              
            

            - **StatusReason** *(string) --* 

              A description of the change set's status. For example, if your change set is in the ``FAILED`` state, AWS CloudFormation shows the error message.

              
            

            - **CreationTime** *(datetime) --* 

              The start time when the change set was created, in UTC.

              
            

            - **Description** *(string) --* 

              Descriptive information about the change set.

              
        
      
        

        - **NextToken** *(string) --* 

          If the output exceeds 1 MB, a string that identifies the next page of change sets. If there is no additional page, this value is null.

          
    

  .. py:method:: list_stack_resources(**kwargs)

    

    Returns descriptions of all resources of the specified stack.

     

    For deleted stacks, ListStackResources returns resource information for up to 90 days after the stack has been deleted.

    

    **Request Syntax** 
    ::

      response = client.list_stack_resources(
          StackName='string',
          NextToken='string'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
    :type NextToken: string
    :param NextToken: 

      A string that identifies the next page of stack resources that you want to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StackResourceSummaries': [
                {
                    'LogicalResourceId': 'string',
                    'PhysicalResourceId': 'string',
                    'ResourceType': 'string',
                    'LastUpdatedTimestamp': datetime(2015, 1, 1),
                    'ResourceStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'DELETE_SKIPPED'|'UPDATE_IN_PROGRESS'|'UPDATE_FAILED'|'UPDATE_COMPLETE',
                    'ResourceStatusReason': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  ListStackResources action.

        
        

        - **StackResourceSummaries** *(list) --* 

          A list of ``StackResourceSummary`` structures.

          
          

          - *(dict) --* 

            Contains high-level information about the specified stack resource.

            
            

            - **LogicalResourceId** *(string) --* 

              The logical name of the resource specified in the template.

              
            

            - **PhysicalResourceId** *(string) --* 

              The name or unique identifier that corresponds to a physical instance ID of the resource.

              
            

            - **ResourceType** *(string) --* 

              Type of resource. (For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

              
            

            - **LastUpdatedTimestamp** *(datetime) --* 

              Time the status was updated.

              
            

            - **ResourceStatus** *(string) --* 

              Current status of the resource.

              
            

            - **ResourceStatusReason** *(string) --* 

              Success/failure message associated with the resource.

              
        
      
        

        - **NextToken** *(string) --* 

          If the output exceeds 1 MB, a string that identifies the next page of stack resources. If no additional page exists, this value is null.

          
    

  .. py:method:: list_stacks(**kwargs)

    

    Returns the summary information for stacks whose status matches the specified StackStatusFilter. Summary information for stacks that have been deleted is kept for 90 days after the stack is deleted. If no StackStatusFilter is specified, summary information for all stacks is returned (including existing stacks and stacks that have been deleted).

    

    **Request Syntax** 
    ::

      response = client.list_stacks(
          NextToken='string',
          StackStatusFilter=[
              'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'ROLLBACK_IN_PROGRESS'|'ROLLBACK_FAILED'|'ROLLBACK_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'UPDATE_IN_PROGRESS'|'UPDATE_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_COMPLETE'|'UPDATE_ROLLBACK_IN_PROGRESS'|'UPDATE_ROLLBACK_FAILED'|'UPDATE_ROLLBACK_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_ROLLBACK_COMPLETE',
          ]
      )
    :type NextToken: string
    :param NextToken: 

      A string that identifies the next page of stacks that you want to retrieve.

      

    
    :type StackStatusFilter: list
    :param StackStatusFilter: 

      Stack status to use as a filter. Specify one or more stack status codes to list only stacks with the specified status codes. For a complete list of stack status codes, see the ``StackStatus`` parameter of the  Stack data type.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StackSummaries': [
                {
                    'StackId': 'string',
                    'StackName': 'string',
                    'TemplateDescription': 'string',
                    'CreationTime': datetime(2015, 1, 1),
                    'LastUpdatedTime': datetime(2015, 1, 1),
                    'DeletionTime': datetime(2015, 1, 1),
                    'StackStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'ROLLBACK_IN_PROGRESS'|'ROLLBACK_FAILED'|'ROLLBACK_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'UPDATE_IN_PROGRESS'|'UPDATE_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_COMPLETE'|'UPDATE_ROLLBACK_IN_PROGRESS'|'UPDATE_ROLLBACK_FAILED'|'UPDATE_ROLLBACK_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_ROLLBACK_COMPLETE',
                    'StackStatusReason': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  ListStacks action.

        
        

        - **StackSummaries** *(list) --* 

          A list of ``StackSummary`` structures containing information about the specified stacks.

          
          

          - *(dict) --* 

            The StackSummary Data Type

            
            

            - **StackId** *(string) --* 

              Unique stack identifier.

              
            

            - **StackName** *(string) --* 

              The name associated with the stack.

              
            

            - **TemplateDescription** *(string) --* 

              The template description of the template used to create the stack.

              
            

            - **CreationTime** *(datetime) --* 

              The time the stack was created.

              
            

            - **LastUpdatedTime** *(datetime) --* 

              The time the stack was last updated. This field will only be returned if the stack has been updated at least once.

              
            

            - **DeletionTime** *(datetime) --* 

              The time the stack was deleted.

              
            

            - **StackStatus** *(string) --* 

              The current status of the stack.

              
            

            - **StackStatusReason** *(string) --* 

              Success/Failure message associated with the stack status.

              
        
      
        

        - **NextToken** *(string) --* 

          If the output exceeds 1 MB in size, a string that identifies the next page of stacks. If no additional page exists, this value is null.

          
    

  .. py:method:: set_stack_policy(**kwargs)

    

    Sets a stack policy for a specified stack.

    

    **Request Syntax** 
    ::

      response = client.set_stack_policy(
          StackName='string',
          StackPolicyBody='string',
          StackPolicyURL='string'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or unique stack ID that you want to associate a policy with.

      

    
    :type StackPolicyBody: string
    :param StackPolicyBody: 

      Structure containing the stack policy body. For more information, go to `Prevent Updates to Stack Resources`_ in the AWS CloudFormation User Guide. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

      

    
    :type StackPolicyURL: string
    :param StackPolicyURL: 

      Location of a file containing the stack policy. The URL must point to a policy (maximum size: 16 KB) located in an S3 bucket in the same region as the stack. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

      

    
    
    :returns: None

  .. py:method:: signal_resource(**kwargs)

    

    Sends a signal to the specified resource with a success or failure status. You can use the SignalResource API in conjunction with a creation policy or update policy. AWS CloudFormation doesn't proceed with a stack creation or update until resources receive the required number of signals or the timeout period is exceeded. The SignalResource API is useful in cases where you want to send signals from anywhere other than an Amazon EC2 instance.

    

    **Request Syntax** 
    ::

      response = client.signal_resource(
          StackName='string',
          LogicalResourceId='string',
          UniqueId='string',
          Status='SUCCESS'|'FAILURE'
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The stack name or unique stack ID that includes the resource that you want to signal.

      

    
    :type LogicalResourceId: string
    :param LogicalResourceId: **[REQUIRED]** 

      The logical ID of the resource that you want to signal. The logical ID is the name of the resource that given in the template.

      

    
    :type UniqueId: string
    :param UniqueId: **[REQUIRED]** 

      A unique ID of the signal. When you signal Amazon EC2 instances or Auto Scaling groups, specify the instance ID that you are signaling as the unique ID. If you send multiple signals to a single resource (such as signaling a wait condition), each signal requires a different unique ID.

      

    
    :type Status: string
    :param Status: **[REQUIRED]** 

      The status of the signal, which is either success or failure. A failure signal causes AWS CloudFormation to immediately fail the stack creation or update.

      

    
    
    :returns: None

  .. py:method:: update_stack(**kwargs)

    

    Updates a stack as specified in the template. After the call completes successfully, the stack update starts. You can check the status of the stack via the  DescribeStacks action.

     

    To get a copy of the template for an existing stack, you can use the  GetTemplate action.

     

    For more information about creating an update template, updating a stack, and monitoring the progress of the update, see `Updating a Stack`_ .

    

    **Request Syntax** 
    ::

      response = client.update_stack(
          StackName='string',
          TemplateBody='string',
          TemplateURL='string',
          UsePreviousTemplate=True|False,
          StackPolicyDuringUpdateBody='string',
          StackPolicyDuringUpdateURL='string',
          Parameters=[
              {
                  'ParameterKey': 'string',
                  'ParameterValue': 'string',
                  'UsePreviousValue': True|False
              },
          ],
          Capabilities=[
              'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
          ],
          ResourceTypes=[
              'string',
          ],
          StackPolicyBody='string',
          StackPolicyURL='string',
          NotificationARNs=[
              'string',
          ],
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or unique stack ID of the stack to update.

      

    
    :type TemplateBody: string
    :param TemplateBody: 

      Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. (For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.)

       

      Conditional: You must specify either the ``TemplateBody`` or the ``TemplateURL`` parameter, but not both.

      

    
    :type TemplateURL: string
    :param TemplateURL: 

      Location of file containing the template body. The URL must point to a template that is located in an Amazon S3 bucket. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must specify either the ``TemplateBody`` or the ``TemplateURL`` parameter, but not both.

      

    
    :type UsePreviousTemplate: boolean
    :param UsePreviousTemplate: 

      Reuse the existing template that is associated with the stack that you are updating.

      

    
    :type StackPolicyDuringUpdateBody: string
    :param StackPolicyDuringUpdateBody: 

      Structure containing the temporary overriding stack policy body. You can specify either the ``StackPolicyDuringUpdateBody`` or the ``StackPolicyDuringUpdateURL`` parameter, but not both.

       

      If you want to update protected resources, specify a temporary overriding stack policy during this update. If you do not specify a stack policy, the current policy that is associated with the stack will be used.

      

    
    :type StackPolicyDuringUpdateURL: string
    :param StackPolicyDuringUpdateURL: 

      Location of a file containing the temporary overriding stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``StackPolicyDuringUpdateBody`` or the ``StackPolicyDuringUpdateURL`` parameter, but not both.

       

      If you want to update protected resources, specify a temporary overriding stack policy during this update. If you do not specify a stack policy, the current policy that is associated with the stack will be used.

      

    
    :type Parameters: list
    :param Parameters: 

      A list of ``Parameter`` structures that specify input parameters for the stack. For more information, see the `Parameter`_ data type.

      

    
      - *(dict) --* 

        The Parameter data type.

        

      
        - **ParameterKey** *(string) --* 

          The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

          

        
        - **ParameterValue** *(string) --* 

          The value associated with the parameter.

          

        
        - **UsePreviousValue** *(boolean) --* 

          During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

          

        
      
  
    :type Capabilities: list
    :param Capabilities: 

      A list of values that you must specify before AWS CloudFormation can update certain stacks. Some stack templates might include resources that can affect permissions in your AWS account, for example, by creating new AWS Identity and Access Management (IAM) users. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter.

       

      The only valid values are ``CAPABILITY_IAM`` and ``CAPABILITY_NAMED_IAM`` . The following resources require you to specify this parameter: `AWS\:\:IAM\:\:AccessKey`_ , `AWS\:\:IAM\:\:Group`_ , `AWS\:\:IAM\:\:InstanceProfile`_ , `AWS\:\:IAM\:\:Policy`_ , `AWS\:\:IAM\:\:Role`_ , `AWS\:\:IAM\:\:User`_ , and `AWS\:\:IAM\:\:UserToGroupAddition`_ . If your stack template contains these resources, we recommend that you review all permissions associated with them and edit their permissions if necessary.

       

      If you have IAM resources, you can specify either capability. If you have IAM resources with custom names, you must specify ``CAPABILITY_NAMED_IAM`` . If you don't specify this parameter, this action returns an ``InsufficientCapabilities`` error.

       

      For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates`_ .

      

    
      - *(string) --* 

      
  
    :type ResourceTypes: list
    :param ResourceTypes: 

      The template resource types that you have permissions to work with for this update stack action, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` .

       

      If the list of resource types doesn't include a resource that you're updating, the stack update fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for AWS CloudFormation-specific condition keys in IAM policies. For more information, see `Controlling Access with AWS Identity and Access Management`_ .

      

    
      - *(string) --* 

      
  
    :type StackPolicyBody: string
    :param StackPolicyBody: 

      Structure containing a new stack policy body. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

       

      You might update the stack policy, for example, in order to protect a new resource that you created during a stack update. If you do not specify a stack policy, the current policy that is associated with the stack is unchanged.

      

    
    :type StackPolicyURL: string
    :param StackPolicyURL: 

      Location of a file containing the updated stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

       

      You might update the stack policy, for example, in order to protect a new resource that you created during a stack update. If you do not specify a stack policy, the current policy that is associated with the stack is unchanged.

      

    
    :type NotificationARNs: list
    :param NotificationARNs: 

      Amazon Simple Notification Service topic Amazon Resource Names (ARNs) that AWS CloudFormation associates with the stack. Specify an empty list to remove all notification topics.

      

    
      - *(string) --* 

      
  
    :type Tags: list
    :param Tags: 

      Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to supported resources in the stack. You can specify a maximum number of 10 tags.

       

      If you don't specify this parameter, AWS CloudFormation doesn't modify the stack's tags. If you specify an empty value, AWS CloudFormation removes all associated tags.

      

    
      - *(dict) --* 

        The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

        

      
        - **Key** *(string) --* 

           *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

          

        
        - **Value** *(string) --* 

           *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StackId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for an  UpdateStack action.

        
        

        - **StackId** *(string) --* 

          Unique identifier of the stack.

          
    

  .. py:method:: validate_template(**kwargs)

    

    Validates a specified template.

    

    **Request Syntax** 
    ::

      response = client.validate_template(
          TemplateBody='string',
          TemplateURL='string'
      )
    :type TemplateBody: string
    :param TemplateBody: 

      Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must pass ``TemplateURL`` or ``TemplateBody`` . If both are passed, only ``TemplateBody`` is used.

      

    
    :type TemplateURL: string
    :param TemplateURL: 

      Location of file containing the template body. The URL must point to a template (max size: 460,800 bytes) that is located in an Amazon S3 bucket. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must pass ``TemplateURL`` or ``TemplateBody`` . If both are passed, only ``TemplateBody`` is used.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Parameters': [
                {
                    'ParameterKey': 'string',
                    'DefaultValue': 'string',
                    'NoEcho': True|False,
                    'Description': 'string'
                },
            ],
            'Description': 'string',
            'Capabilities': [
                'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
            ],
            'CapabilitiesReason': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  ValidateTemplate action.

        
        

        - **Parameters** *(list) --* 

          A list of ``TemplateParameter`` structures.

          
          

          - *(dict) --* 

            The TemplateParameter data type.

            
            

            - **ParameterKey** *(string) --* 

              The name associated with the parameter.

              
            

            - **DefaultValue** *(string) --* 

              The default value associated with the parameter.

              
            

            - **NoEcho** *(boolean) --* 

              Flag indicating whether the parameter should be displayed as plain text in logs and UIs.

              
            

            - **Description** *(string) --* 

              User defined description associated with the parameter.

              
        
      
        

        - **Description** *(string) --* 

          The description found within the template.

          
        

        - **Capabilities** *(list) --* 

          The capabilities found within the template. If your template contains IAM resources, you must specify the CAPABILITY_IAM or CAPABILITY_NAMED_IAM value for this parameter when you use the  CreateStack or  UpdateStack actions with your template; otherwise, those actions return an InsufficientCapabilities error.

           

          For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates`_ .

          
          

          - *(string) --* 
      
        

        - **CapabilitiesReason** *(string) --* 

          The list of resources that generated the values in the ``Capabilities`` response element.

          
    

==========
Paginators
==========


The available paginators are:

* :py:class:`CloudFormation.Paginator.DescribeStackEvents`


* :py:class:`CloudFormation.Paginator.DescribeStacks`


* :py:class:`CloudFormation.Paginator.ListStackResources`


* :py:class:`CloudFormation.Paginator.ListStacks`



.. py:class:: CloudFormation.Paginator.DescribeStackEvents

  ::

    
    paginator = client.get_paginator('describe_stack_events')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudFormation.Client.describe_stack_events`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          StackName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type StackName: string
    :param StackName: 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
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
            'StackEvents': [
                {
                    'StackId': 'string',
                    'EventId': 'string',
                    'StackName': 'string',
                    'LogicalResourceId': 'string',
                    'PhysicalResourceId': 'string',
                    'ResourceType': 'string',
                    'Timestamp': datetime(2015, 1, 1),
                    'ResourceStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'DELETE_SKIPPED'|'UPDATE_IN_PROGRESS'|'UPDATE_FAILED'|'UPDATE_COMPLETE',
                    'ResourceStatusReason': 'string',
                    'ResourceProperties': 'string'
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  DescribeStackEvents action.

        
        

        - **StackEvents** *(list) --* 

          A list of ``StackEvents`` structures.

          
          

          - *(dict) --* 

            The StackEvent data type.

            
            

            - **StackId** *(string) --* 

              The unique ID name of the instance of the stack.

              
            

            - **EventId** *(string) --* 

              The unique ID of this event.

              
            

            - **StackName** *(string) --* 

              The name associated with a stack.

              
            

            - **LogicalResourceId** *(string) --* 

              The logical name of the resource specified in the template.

              
            

            - **PhysicalResourceId** *(string) --* 

              The name or unique identifier associated with the physical instance of the resource.

              
            

            - **ResourceType** *(string) --* 

              Type of resource. (For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

              
            

            - **Timestamp** *(datetime) --* 

              Time the status was updated.

              
            

            - **ResourceStatus** *(string) --* 

              Current status of the resource.

              
            

            - **ResourceStatusReason** *(string) --* 

              Success/failure message associated with the resource.

              
            

            - **ResourceProperties** *(string) --* 

              BLOB of the properties used to create the resource.

              
        
      
    

.. py:class:: CloudFormation.Paginator.DescribeStacks

  ::

    
    paginator = client.get_paginator('describe_stacks')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudFormation.Client.describe_stacks`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          StackName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type StackName: string
    :param StackName: 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
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
            'Stacks': [
                {
                    'StackId': 'string',
                    'StackName': 'string',
                    'Description': 'string',
                    'Parameters': [
                        {
                            'ParameterKey': 'string',
                            'ParameterValue': 'string',
                            'UsePreviousValue': True|False
                        },
                    ],
                    'CreationTime': datetime(2015, 1, 1),
                    'LastUpdatedTime': datetime(2015, 1, 1),
                    'StackStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'ROLLBACK_IN_PROGRESS'|'ROLLBACK_FAILED'|'ROLLBACK_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'UPDATE_IN_PROGRESS'|'UPDATE_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_COMPLETE'|'UPDATE_ROLLBACK_IN_PROGRESS'|'UPDATE_ROLLBACK_FAILED'|'UPDATE_ROLLBACK_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_ROLLBACK_COMPLETE',
                    'StackStatusReason': 'string',
                    'DisableRollback': True|False,
                    'NotificationARNs': [
                        'string',
                    ],
                    'TimeoutInMinutes': 123,
                    'Capabilities': [
                        'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
                    ],
                    'Outputs': [
                        {
                            'OutputKey': 'string',
                            'OutputValue': 'string',
                            'Description': 'string'
                        },
                    ],
                    'Tags': [
                        {
                            'Key': 'string',
                            'Value': 'string'
                        },
                    ]
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  DescribeStacks action.

        
        

        - **Stacks** *(list) --* 

          A list of stack structures.

          
          

          - *(dict) --* 

            The Stack data type.

            
            

            - **StackId** *(string) --* 

              Unique identifier of the stack.

              
            

            - **StackName** *(string) --* 

              The name associated with the stack.

              
            

            - **Description** *(string) --* 

              A user-defined description associated with the stack.

              
            

            - **Parameters** *(list) --* 

              A list of ``Parameter`` structures.

              
              

              - *(dict) --* 

                The Parameter data type.

                
                

                - **ParameterKey** *(string) --* 

                  The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

                  
                

                - **ParameterValue** *(string) --* 

                  The value associated with the parameter.

                  
                

                - **UsePreviousValue** *(boolean) --* 

                  During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

                  
            
          
            

            - **CreationTime** *(datetime) --* 

              The time at which the stack was created.

              
            

            - **LastUpdatedTime** *(datetime) --* 

              The time the stack was last updated. This field will only be returned if the stack has been updated at least once.

              
            

            - **StackStatus** *(string) --* 

              Current status of the stack.

              
            

            - **StackStatusReason** *(string) --* 

              Success/failure message associated with the stack status.

              
            

            - **DisableRollback** *(boolean) --* 

              Boolean to enable or disable rollback on stack creation failures:

               

               
              * ``true`` : disable rollback 
               
              * ``false`` : enable rollback 
               

              
            

            - **NotificationARNs** *(list) --* 

              SNS topic ARNs to which stack related events are published.

              
              

              - *(string) --* 
          
            

            - **TimeoutInMinutes** *(integer) --* 

              The amount of time within which stack creation should complete.

              
            

            - **Capabilities** *(list) --* 

              The capabilities allowed in the stack.

              
              

              - *(string) --* 
          
            

            - **Outputs** *(list) --* 

              A list of output structures.

              
              

              - *(dict) --* 

                The Output data type.

                
                

                - **OutputKey** *(string) --* 

                  The key associated with the output.

                  
                

                - **OutputValue** *(string) --* 

                  The value associated with the output.

                  
                

                - **Description** *(string) --* 

                  User defined description associated with the output.

                  
            
          
            

            - **Tags** *(list) --* 

              A list of ``Tag`` s that specify information about the stack.

              
              

              - *(dict) --* 

                The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

                
                

                - **Key** *(string) --* 

                   *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

                  
                

                - **Value** *(string) --* 

                   *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

                  
            
          
        
      
    

.. py:class:: CloudFormation.Paginator.ListStackResources

  ::

    
    paginator = client.get_paginator('list_stack_resources')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudFormation.Client.list_stack_resources`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          StackName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
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
            'StackResourceSummaries': [
                {
                    'LogicalResourceId': 'string',
                    'PhysicalResourceId': 'string',
                    'ResourceType': 'string',
                    'LastUpdatedTimestamp': datetime(2015, 1, 1),
                    'ResourceStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'DELETE_SKIPPED'|'UPDATE_IN_PROGRESS'|'UPDATE_FAILED'|'UPDATE_COMPLETE',
                    'ResourceStatusReason': 'string'
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for a  ListStackResources action.

        
        

        - **StackResourceSummaries** *(list) --* 

          A list of ``StackResourceSummary`` structures.

          
          

          - *(dict) --* 

            Contains high-level information about the specified stack resource.

            
            

            - **LogicalResourceId** *(string) --* 

              The logical name of the resource specified in the template.

              
            

            - **PhysicalResourceId** *(string) --* 

              The name or unique identifier that corresponds to a physical instance ID of the resource.

              
            

            - **ResourceType** *(string) --* 

              Type of resource. (For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

              
            

            - **LastUpdatedTimestamp** *(datetime) --* 

              Time the status was updated.

              
            

            - **ResourceStatus** *(string) --* 

              Current status of the resource.

              
            

            - **ResourceStatusReason** *(string) --* 

              Success/failure message associated with the resource.

              
        
      
    

.. py:class:: CloudFormation.Paginator.ListStacks

  ::

    
    paginator = client.get_paginator('list_stacks')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CloudFormation.Client.list_stacks`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          StackStatusFilter=[
              'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'ROLLBACK_IN_PROGRESS'|'ROLLBACK_FAILED'|'ROLLBACK_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'UPDATE_IN_PROGRESS'|'UPDATE_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_COMPLETE'|'UPDATE_ROLLBACK_IN_PROGRESS'|'UPDATE_ROLLBACK_FAILED'|'UPDATE_ROLLBACK_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_ROLLBACK_COMPLETE',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type StackStatusFilter: list
    :param StackStatusFilter: 

      Stack status to use as a filter. Specify one or more stack status codes to list only stacks with the specified status codes. For a complete list of stack status codes, see the ``StackStatus`` parameter of the  Stack data type.

      

    
      - *(string) --* 

      
  
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
            'StackSummaries': [
                {
                    'StackId': 'string',
                    'StackName': 'string',
                    'TemplateDescription': 'string',
                    'CreationTime': datetime(2015, 1, 1),
                    'LastUpdatedTime': datetime(2015, 1, 1),
                    'DeletionTime': datetime(2015, 1, 1),
                    'StackStatus': 'CREATE_IN_PROGRESS'|'CREATE_FAILED'|'CREATE_COMPLETE'|'ROLLBACK_IN_PROGRESS'|'ROLLBACK_FAILED'|'ROLLBACK_COMPLETE'|'DELETE_IN_PROGRESS'|'DELETE_FAILED'|'DELETE_COMPLETE'|'UPDATE_IN_PROGRESS'|'UPDATE_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_COMPLETE'|'UPDATE_ROLLBACK_IN_PROGRESS'|'UPDATE_ROLLBACK_FAILED'|'UPDATE_ROLLBACK_COMPLETE_CLEANUP_IN_PROGRESS'|'UPDATE_ROLLBACK_COMPLETE',
                    'StackStatusReason': 'string'
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for  ListStacks action.

        
        

        - **StackSummaries** *(list) --* 

          A list of ``StackSummary`` structures containing information about the specified stacks.

          
          

          - *(dict) --* 

            The StackSummary Data Type

            
            

            - **StackId** *(string) --* 

              Unique stack identifier.

              
            

            - **StackName** *(string) --* 

              The name associated with the stack.

              
            

            - **TemplateDescription** *(string) --* 

              The template description of the template used to create the stack.

              
            

            - **CreationTime** *(datetime) --* 

              The time the stack was created.

              
            

            - **LastUpdatedTime** *(datetime) --* 

              The time the stack was last updated. This field will only be returned if the stack has been updated at least once.

              
            

            - **DeletionTime** *(datetime) --* 

              The time the stack was deleted.

              
            

            - **StackStatus** *(string) --* 

              The current status of the stack.

              
            

            - **StackStatusReason** *(string) --* 

              Success/Failure message associated with the stack status.

              
        
      
    

=======
Waiters
=======


The available waiters are:

* :py:class:`CloudFormation.Waiter.StackCreateComplete`


* :py:class:`CloudFormation.Waiter.StackDeleteComplete`


* :py:class:`CloudFormation.Waiter.StackExists`


* :py:class:`CloudFormation.Waiter.StackUpdateComplete`



.. py:class:: CloudFormation.Waiter.StackCreateComplete

  ::

    
    waiter = client.get_waiter('stack_create_complete')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`CloudFormation.Client.describe_stacks` every 30 seconds until a successful state is reached. An error is returned after 120 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          StackName='string',
          NextToken='string'
      )
    :type StackName: string
    :param StackName: 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
    :type NextToken: string
    :param NextToken: 

      A string that identifies the next page of stacks that you want to retrieve.

      

    
    
    :returns: None

.. py:class:: CloudFormation.Waiter.StackDeleteComplete

  ::

    
    waiter = client.get_waiter('stack_delete_complete')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`CloudFormation.Client.describe_stacks` every 30 seconds until a successful state is reached. An error is returned after 120 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          StackName='string',
          NextToken='string'
      )
    :type StackName: string
    :param StackName: 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
    :type NextToken: string
    :param NextToken: 

      A string that identifies the next page of stacks that you want to retrieve.

      

    
    
    :returns: None

.. py:class:: CloudFormation.Waiter.StackExists

  ::

    
    waiter = client.get_waiter('stack_exists')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`CloudFormation.Client.describe_stacks` every 5 seconds until a successful state is reached. An error is returned after 20 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          StackName='string',
          NextToken='string'
      )
    :type StackName: string
    :param StackName: 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
    :type NextToken: string
    :param NextToken: 

      A string that identifies the next page of stacks that you want to retrieve.

      

    
    
    :returns: None

.. py:class:: CloudFormation.Waiter.StackUpdateComplete

  ::

    
    waiter = client.get_waiter('stack_update_complete')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`CloudFormation.Client.describe_stacks` every 30 seconds until a successful state is reached. An error is returned after 120 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          StackName='string',
          NextToken='string'
      )
    :type StackName: string
    :param StackName: 

      The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

       

       
      * Running stacks: You can specify either the stack's name or its unique stack ID. 
       
      * Deleted stacks: You must specify the unique stack ID. 
       

       

      Default: There is no default value.

      

    
    :type NextToken: string
    :param NextToken: 

      A string that identifies the next page of stacks that you want to retrieve.

      

    
    
    :returns: None

================
Service Resource
================



.. py:class:: CloudFormation.ServiceResource()

  A resource representing AWS CloudFormation::

    
    import boto3
    
    cloudformation = boto3.resource('cloudformation')

  
  These are the resource's available actions:
  
  *   :py:meth:`create_stack()`

  
  *   :py:meth:`get_available_subresources()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Event()`

  
  *   :py:meth:`Stack()`

  
  *   :py:meth:`StackResource()`

  
  *   :py:meth:`StackResourceSummary()`

  
  These are the resource's available collections:
  
  *   :py:attr:`stacks`

  
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: create_stack(**kwargs)

    

    Creates a stack as specified in the template. After the call completes successfully, the stack creation starts. You can check the status of the stack via the  DescribeStacks API.

    

    **Request Syntax** 
    ::

      stack = cloudformation.create_stack(
          StackName='string',
          TemplateBody='string',
          TemplateURL='string',
          Parameters=[
              {
                  'ParameterKey': 'string',
                  'ParameterValue': 'string',
                  'UsePreviousValue': True|False
              },
          ],
          DisableRollback=True|False,
          TimeoutInMinutes=123,
          NotificationARNs=[
              'string',
          ],
          Capabilities=[
              'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
          ],
          ResourceTypes=[
              'string',
          ],
          OnFailure='DO_NOTHING'|'ROLLBACK'|'DELETE',
          StackPolicyBody='string',
          StackPolicyURL='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type StackName: string
    :param StackName: **[REQUIRED]** 

      The name that is associated with the stack. The name must be unique in the region in which you are creating the stack.

       

      .. note::

         

        A stack name can contain only alphanumeric characters (case sensitive) and hyphens. It must start with an alphabetic character and cannot be longer than 128 characters.

         

      

    
    :type TemplateBody: string
    :param TemplateBody: 

      Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must specify either the ``TemplateBody`` or the ``TemplateURL`` parameter, but not both.

      

    
    :type TemplateURL: string
    :param TemplateURL: 

      Location of file containing the template body. The URL must point to a template (max size: 460,800 bytes) that is located in an Amazon S3 bucket. For more information, go to the `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must specify either the ``TemplateBody`` or the ``TemplateURL`` parameter, but not both.

      

    
    :type Parameters: list
    :param Parameters: 

      A list of ``Parameter`` structures that specify input parameters for the stack. For more information, see the `Parameter`_ data type.

      

    
      - *(dict) --* 

        The Parameter data type.

        

      
        - **ParameterKey** *(string) --* 

          The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

          

        
        - **ParameterValue** *(string) --* 

          The value associated with the parameter.

          

        
        - **UsePreviousValue** *(boolean) --* 

          During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

          

        
      
  
    :type DisableRollback: boolean
    :param DisableRollback: 

      Set to ``true`` to disable rollback of the stack if stack creation failed. You can specify either ``DisableRollback`` or ``OnFailure`` , but not both.

       

      Default: ``false``  

      

    
    :type TimeoutInMinutes: integer
    :param TimeoutInMinutes: 

      The amount of time that can pass before the stack status becomes CREATE_FAILED; if ``DisableRollback`` is not set or is set to ``false`` , the stack will be rolled back.

      

    
    :type NotificationARNs: list
    :param NotificationARNs: 

      The Simple Notification Service (SNS) topic ARNs to publish stack related events. You can find your SNS topic ARNs using the `SNS console`_ or your Command Line Interface (CLI).

      

    
      - *(string) --* 

      
  
    :type Capabilities: list
    :param Capabilities: 

      A list of values that you must specify before AWS CloudFormation can create certain stacks. Some stack templates might include resources that can affect permissions in your AWS account, for example, by creating new AWS Identity and Access Management (IAM) users. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter.

       

      The only valid values are ``CAPABILITY_IAM`` and ``CAPABILITY_NAMED_IAM`` . The following resources require you to specify this parameter: `AWS\:\:IAM\:\:AccessKey`_ , `AWS\:\:IAM\:\:Group`_ , `AWS\:\:IAM\:\:InstanceProfile`_ , `AWS\:\:IAM\:\:Policy`_ , `AWS\:\:IAM\:\:Role`_ , `AWS\:\:IAM\:\:User`_ , and `AWS\:\:IAM\:\:UserToGroupAddition`_ . If your stack template contains these resources, we recommend that you review all permissions associated with them and edit their permissions if necessary.

       

      If you have IAM resources, you can specify either capability. If you have IAM resources with custom names, you must specify ``CAPABILITY_NAMED_IAM`` . If you don't specify this parameter, this action returns an ``InsufficientCapabilities`` error.

       

      For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates`_ .

      

    
      - *(string) --* 

      
  
    :type ResourceTypes: list
    :param ResourceTypes: 

      The template resource types that you have permissions to work with for this create stack action, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` . Use the following syntax to describe template resource types: ``AWS::*`` (for all AWS resource), ``Custom::*`` (for all custom resources), ``Custom::*logical_ID* `` (for a specific custom resource), ``AWS::*service_name* ::*`` (for all resources of a particular AWS service), and ``AWS::*service_name* ::*resource_logical_ID* `` (for a specific AWS resource).

       

      If the list of resource types doesn't include a resource that you're creating, the stack creation fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for AWS CloudFormation-specific condition keys in IAM policies. For more information, see `Controlling Access with AWS Identity and Access Management`_ .

      

    
      - *(string) --* 

      
  
    :type OnFailure: string
    :param OnFailure: 

      Determines what action will be taken if stack creation fails. This must be one of: DO_NOTHING, ROLLBACK, or DELETE. You can specify either ``OnFailure`` or ``DisableRollback`` , but not both.

       

      Default: ``ROLLBACK``  

      

    
    :type StackPolicyBody: string
    :param StackPolicyBody: 

      Structure containing the stack policy body. For more information, go to `Prevent Updates to Stack Resources`_ in the AWS CloudFormation User Guide. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

      

    
    :type StackPolicyURL: string
    :param StackPolicyURL: 

      Location of a file containing the stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

      

    
    :type Tags: list
    :param Tags: 

      Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to the resources created in the stack. A maximum number of 10 tags can be specified.

      

    
      - *(dict) --* 

        The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

        

      
        - **Key** *(string) --* 

           *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

          

        
        - **Value** *(string) --* 

           *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

          

        
      
  
    
    :rtype: :py:class:`cloudformation.Stack`
    :returns: Stack resource
    

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str

  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Event(id)

    Creates a Event resource.::

      event = cloudformation.Event('id')

    :type id: string
    :param id: The Event's id identifier. This **must** be set.
    
    :rtype: :py:class:`CloudFormation.Event`
    :returns: A Event resource
    

  .. py:method:: Stack(name)

    Creates a Stack resource.::

      stack = cloudformation.Stack('name')

    :type name: string
    :param name: The Stack's name identifier. This **must** be set.
    
    :rtype: :py:class:`CloudFormation.Stack`
    :returns: A Stack resource
    

  .. py:method:: StackResource(stack_name,logical_id)

    Creates a StackResource resource.::

      stack_resource = cloudformation.StackResource('stack_name','logical_id')

    :type stack_name: string
    :param stack_name: The StackResource's stack_name identifier. This **must** be set.
    :type logical_id: string
    :param logical_id: The StackResource's logical_id identifier. This **must** be set.
    
    :rtype: :py:class:`CloudFormation.StackResource`
    :returns: A StackResource resource
    

  .. py:method:: StackResourceSummary(stack_name,logical_id)

    Creates a StackResourceSummary resource.::

      stack_resource_summary = cloudformation.StackResourceSummary('stack_name','logical_id')

    :type stack_name: string
    :param stack_name: The StackResourceSummary's stack_name identifier. This **must** be set.
    :type logical_id: string
    :param logical_id: The StackResourceSummary's logical_id identifier. This **must** be set.
    
    :rtype: :py:class:`CloudFormation.StackResourceSummary`
    :returns: A StackResourceSummary resource
    
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: stacks

    A collection of Stack resources

    .. py:method:: all()

      Creates an iterable of all Stack resources in the collection.

      **Request Syntax** 
      ::

        stack_iterator = cloudformation.stacks.all()
        
      
      :rtype: list(:py:class:`cloudformation.Stack`)
      :returns: A list of Stack resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Stack resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        stack_iterator = cloudformation.stacks.filter(
            StackName='string',
            NextToken='string'
        )
      :type StackName: string
      :param StackName: 

        The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

         

         
        * Running stacks: You can specify either the stack's name or its unique stack ID. 
         
        * Deleted stacks: You must specify the unique stack ID. 
         

         

        Default: There is no default value.

        

      
      :type NextToken: string
      :param NextToken: 

        A string that identifies the next page of stacks that you want to retrieve.

        

      
      
      :rtype: list(:py:class:`cloudformation.Stack`)
      :returns: A list of Stack resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Stack resources in the collection.

      **Request Syntax** 
      ::

        stack_iterator = cloudformation.stacks.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`cloudformation.Stack`)
      :returns: A list of Stack resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Stack resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        stack_iterator = cloudformation.stacks.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`cloudformation.Stack`)
      :returns: A list of Stack resources
      

=====
Event
=====



.. py:class:: CloudFormation.Event(id)

  A resource representing an AWS CloudFormation Event::

    
    import boto3
    
    cloudformation = boto3.resource('cloudformation')
    event = cloudformation.Event('id')

  :type id: string
  :param id: The Event's id identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`id`

  
  These are the resource's available attributes:
  
  *   :py:attr:`event_id`

  
  *   :py:attr:`logical_resource_id`

  
  *   :py:attr:`physical_resource_id`

  
  *   :py:attr:`resource_properties`

  
  *   :py:attr:`resource_status`

  
  *   :py:attr:`resource_status_reason`

  
  *   :py:attr:`resource_type`

  
  *   :py:attr:`stack_id`

  
  *   :py:attr:`stack_name`

  
  *   :py:attr:`timestamp`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: id

    *(string)* The Event's id identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: event_id

    

    - *(string) --* 

      The unique ID of this event.

      

  .. py:attribute:: logical_resource_id

    

    - *(string) --* 

      The logical name of the resource specified in the template.

      

  .. py:attribute:: physical_resource_id

    

    - *(string) --* 

      The name or unique identifier associated with the physical instance of the resource.

      

  .. py:attribute:: resource_properties

    

    - *(string) --* 

      BLOB of the properties used to create the resource.

      

  .. py:attribute:: resource_status

    

    - *(string) --* 

      Current status of the resource.

      

  .. py:attribute:: resource_status_reason

    

    - *(string) --* 

      Success/failure message associated with the resource.

      

  .. py:attribute:: resource_type

    

    - *(string) --* 

      Type of resource. (For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

      

  .. py:attribute:: stack_id

    

    - *(string) --* 

      The unique ID name of the instance of the stack.

      

  .. py:attribute:: stack_name

    

    - *(string) --* 

      The name associated with a stack.

      

  .. py:attribute:: timestamp

    

    - *(datetime) --* 

      Time the status was updated.

      

=====
Stack
=====



.. py:class:: CloudFormation.Stack(name)

  A resource representing an AWS CloudFormation Stack::

    
    import boto3
    
    cloudformation = boto3.resource('cloudformation')
    stack = cloudformation.Stack('name')

  :type name: string
  :param name: The Stack's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`capabilities`

  
  *   :py:attr:`creation_time`

  
  *   :py:attr:`description`

  
  *   :py:attr:`disable_rollback`

  
  *   :py:attr:`last_updated_time`

  
  *   :py:attr:`notification_arns`

  
  *   :py:attr:`outputs`

  
  *   :py:attr:`parameters`

  
  *   :py:attr:`stack_id`

  
  *   :py:attr:`stack_name`

  
  *   :py:attr:`stack_status`

  
  *   :py:attr:`stack_status_reason`

  
  *   :py:attr:`tags`

  
  *   :py:attr:`timeout_in_minutes`

  
  These are the resource's available actions:
  
  *   :py:meth:`cancel_update()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`update()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Resource()`

  
  These are the resource's available collections:
  
  *   :py:attr:`events`

  
  *   :py:attr:`resource_summaries`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: name

    *(string)* The Stack's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: capabilities

    

    - *(list) --* 

      The capabilities allowed in the stack.

      
      

      - *(string) --* 
  

  .. py:attribute:: creation_time

    

    - *(datetime) --* 

      The time at which the stack was created.

      

  .. py:attribute:: description

    

    - *(string) --* 

      A user-defined description associated with the stack.

      

  .. py:attribute:: disable_rollback

    

    - *(boolean) --* 

      Boolean to enable or disable rollback on stack creation failures:

       

       
      * ``true`` : disable rollback 
       
      * ``false`` : enable rollback 
       

      

  .. py:attribute:: last_updated_time

    

    - *(datetime) --* 

      The time the stack was last updated. This field will only be returned if the stack has been updated at least once.

      

  .. py:attribute:: notification_arns

    

    - *(list) --* 

      SNS topic ARNs to which stack related events are published.

      
      

      - *(string) --* 
  

  .. py:attribute:: outputs

    

    - *(list) --* 

      A list of output structures.

      
      

      - *(dict) --* 

        The Output data type.

        
        

        - **OutputKey** *(string) --* 

          The key associated with the output.

          
        

        - **OutputValue** *(string) --* 

          The value associated with the output.

          
        

        - **Description** *(string) --* 

          User defined description associated with the output.

          
    
  

  .. py:attribute:: parameters

    

    - *(list) --* 

      A list of ``Parameter`` structures.

      
      

      - *(dict) --* 

        The Parameter data type.

        
        

        - **ParameterKey** *(string) --* 

          The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

          
        

        - **ParameterValue** *(string) --* 

          The value associated with the parameter.

          
        

        - **UsePreviousValue** *(boolean) --* 

          During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

          
    
  

  .. py:attribute:: stack_id

    

    - *(string) --* 

      Unique identifier of the stack.

      

  .. py:attribute:: stack_name

    

    - *(string) --* 

      The name associated with the stack.

      

  .. py:attribute:: stack_status

    

    - *(string) --* 

      Current status of the stack.

      

  .. py:attribute:: stack_status_reason

    

    - *(string) --* 

      Success/failure message associated with the stack status.

      

  .. py:attribute:: tags

    

    - *(list) --* 

      A list of ``Tag`` s that specify information about the stack.

      
      

      - *(dict) --* 

        The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

        
        

        - **Key** *(string) --* 

           *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

          
        

        - **Value** *(string) --* 

           *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

          
    
  

  .. py:attribute:: timeout_in_minutes

    

    - *(integer) --* 

      The amount of time within which stack creation should complete.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: cancel_update()

    

    Cancels an update on the specified stack. If the call completes successfully, the stack rolls back the update and reverts to the previous stack configuration.

     

    .. note::

       

      You can cancel only stacks that are in the UPDATE_IN_PROGRESS state.

       

    

    **Request Syntax** 
    ::

      response = stack.cancel_update()
      
    
    :returns: None

  .. py:method:: delete(**kwargs)

    

    Deletes a specified stack. Once the call completes successfully, stack deletion starts. Deleted stacks do not show up in the  DescribeStacks API if the deletion has been completed successfully.

    

    **Request Syntax** 
    ::

      response = stack.delete(
          RetainResources=[
              'string',
          ]
      )
    :type RetainResources: list
    :param RetainResources: 

      For stacks in the ``DELETE_FAILED`` state, a list of resource logical IDs that are associated with the resources you want to retain. During deletion, AWS CloudFormation deletes the stack but does not delete the retained resources.

       

      Retaining resources is useful when you cannot delete a resource, such as a non-empty S3 bucket, but you want to delete the stack.

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`CloudFormation.Client.describe_stacks` to update the attributes of the Stack resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      stack.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`CloudFormation.Client.describe_stacks` to update the attributes of the Stack resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      stack.reload()
    :returns: None

  .. py:method:: update(**kwargs)

    

    Updates a stack as specified in the template. After the call completes successfully, the stack update starts. You can check the status of the stack via the  DescribeStacks action.

     

    To get a copy of the template for an existing stack, you can use the  GetTemplate action.

     

    For more information about creating an update template, updating a stack, and monitoring the progress of the update, see `Updating a Stack`_ .

    

    **Request Syntax** 
    ::

      response = stack.update(
          TemplateBody='string',
          TemplateURL='string',
          UsePreviousTemplate=True|False,
          StackPolicyDuringUpdateBody='string',
          StackPolicyDuringUpdateURL='string',
          Parameters=[
              {
                  'ParameterKey': 'string',
                  'ParameterValue': 'string',
                  'UsePreviousValue': True|False
              },
          ],
          Capabilities=[
              'CAPABILITY_IAM'|'CAPABILITY_NAMED_IAM',
          ],
          ResourceTypes=[
              'string',
          ],
          StackPolicyBody='string',
          StackPolicyURL='string',
          NotificationARNs=[
              'string',
          ],
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type TemplateBody: string
    :param TemplateBody: 

      Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. (For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.)

       

      Conditional: You must specify either the ``TemplateBody`` or the ``TemplateURL`` parameter, but not both.

      

    
    :type TemplateURL: string
    :param TemplateURL: 

      Location of file containing the template body. The URL must point to a template that is located in an Amazon S3 bucket. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

       

      Conditional: You must specify either the ``TemplateBody`` or the ``TemplateURL`` parameter, but not both.

      

    
    :type UsePreviousTemplate: boolean
    :param UsePreviousTemplate: 

      Reuse the existing template that is associated with the stack that you are updating.

      

    
    :type StackPolicyDuringUpdateBody: string
    :param StackPolicyDuringUpdateBody: 

      Structure containing the temporary overriding stack policy body. You can specify either the ``StackPolicyDuringUpdateBody`` or the ``StackPolicyDuringUpdateURL`` parameter, but not both.

       

      If you want to update protected resources, specify a temporary overriding stack policy during this update. If you do not specify a stack policy, the current policy that is associated with the stack will be used.

      

    
    :type StackPolicyDuringUpdateURL: string
    :param StackPolicyDuringUpdateURL: 

      Location of a file containing the temporary overriding stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``StackPolicyDuringUpdateBody`` or the ``StackPolicyDuringUpdateURL`` parameter, but not both.

       

      If you want to update protected resources, specify a temporary overriding stack policy during this update. If you do not specify a stack policy, the current policy that is associated with the stack will be used.

      

    
    :type Parameters: list
    :param Parameters: 

      A list of ``Parameter`` structures that specify input parameters for the stack. For more information, see the `Parameter`_ data type.

      

    
      - *(dict) --* 

        The Parameter data type.

        

      
        - **ParameterKey** *(string) --* 

          The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

          

        
        - **ParameterValue** *(string) --* 

          The value associated with the parameter.

          

        
        - **UsePreviousValue** *(boolean) --* 

          During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

          

        
      
  
    :type Capabilities: list
    :param Capabilities: 

      A list of values that you must specify before AWS CloudFormation can update certain stacks. Some stack templates might include resources that can affect permissions in your AWS account, for example, by creating new AWS Identity and Access Management (IAM) users. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter.

       

      The only valid values are ``CAPABILITY_IAM`` and ``CAPABILITY_NAMED_IAM`` . The following resources require you to specify this parameter: `AWS\:\:IAM\:\:AccessKey`_ , `AWS\:\:IAM\:\:Group`_ , `AWS\:\:IAM\:\:InstanceProfile`_ , `AWS\:\:IAM\:\:Policy`_ , `AWS\:\:IAM\:\:Role`_ , `AWS\:\:IAM\:\:User`_ , and `AWS\:\:IAM\:\:UserToGroupAddition`_ . If your stack template contains these resources, we recommend that you review all permissions associated with them and edit their permissions if necessary.

       

      If you have IAM resources, you can specify either capability. If you have IAM resources with custom names, you must specify ``CAPABILITY_NAMED_IAM`` . If you don't specify this parameter, this action returns an ``InsufficientCapabilities`` error.

       

      For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates`_ .

      

    
      - *(string) --* 

      
  
    :type ResourceTypes: list
    :param ResourceTypes: 

      The template resource types that you have permissions to work with for this update stack action, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` .

       

      If the list of resource types doesn't include a resource that you're updating, the stack update fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for AWS CloudFormation-specific condition keys in IAM policies. For more information, see `Controlling Access with AWS Identity and Access Management`_ .

      

    
      - *(string) --* 

      
  
    :type StackPolicyBody: string
    :param StackPolicyBody: 

      Structure containing a new stack policy body. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

       

      You might update the stack policy, for example, in order to protect a new resource that you created during a stack update. If you do not specify a stack policy, the current policy that is associated with the stack is unchanged.

      

    
    :type StackPolicyURL: string
    :param StackPolicyURL: 

      Location of a file containing the updated stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``StackPolicyBody`` or the ``StackPolicyURL`` parameter, but not both.

       

      You might update the stack policy, for example, in order to protect a new resource that you created during a stack update. If you do not specify a stack policy, the current policy that is associated with the stack is unchanged.

      

    
    :type NotificationARNs: list
    :param NotificationARNs: 

      Amazon Simple Notification Service topic Amazon Resource Names (ARNs) that AWS CloudFormation associates with the stack. Specify an empty list to remove all notification topics.

      

    
      - *(string) --* 

      
  
    :type Tags: list
    :param Tags: 

      Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to supported resources in the stack. You can specify a maximum number of 10 tags.

       

      If you don't specify this parameter, AWS CloudFormation doesn't modify the stack's tags. If you specify an empty value, AWS CloudFormation removes all associated tags.

      

    
      - *(dict) --* 

        The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

        

      
        - **Key** *(string) --* 

           *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

          

        
        - **Value** *(string) --* 

           *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StackId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for an  UpdateStack action.

        
        

        - **StackId** *(string) --* 

          Unique identifier of the stack.

          
    
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Resource(logical_id)

    Creates a StackResource resource.::

      stack_resource = stack.Resource('logical_id')

    :type logical_id: string
    :param logical_id: The Resource's logical_id identifier. This **must** be set.
    
    :rtype: :py:class:`CloudFormation.StackResource`
    :returns: A StackResource resource
    
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: events

    A collection of Event resources

    .. py:method:: all()

      Creates an iterable of all Event resources in the collection.

      **Request Syntax** 
      ::

        event_iterator = stack.events.all()
        
      
      :rtype: list(:py:class:`cloudformation.Event`)
      :returns: A list of Event resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Event resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        event_iterator = stack.events.filter(
            NextToken='string'
        )
      :type NextToken: string
      :param NextToken: 

        A string that identifies the next page of events that you want to retrieve.

        

      
      
      :rtype: list(:py:class:`cloudformation.Event`)
      :returns: A list of Event resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Event resources in the collection.

      **Request Syntax** 
      ::

        event_iterator = stack.events.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`cloudformation.Event`)
      :returns: A list of Event resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Event resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        event_iterator = stack.events.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`cloudformation.Event`)
      :returns: A list of Event resources
      

  .. py:attribute:: resource_summaries

    A collection of StackResourceSummary resources

    .. py:method:: all()

      Creates an iterable of all StackResourceSummary resources in the collection.

      **Request Syntax** 
      ::

        stack_resource_summary_iterator = stack.resource_summaries.all()
        
      
      :rtype: list(:py:class:`cloudformation.StackResourceSummary`)
      :returns: A list of StackResourceSummary resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all StackResourceSummary resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        stack_resource_summary_iterator = stack.resource_summaries.filter(
            NextToken='string'
        )
      :type NextToken: string
      :param NextToken: 

        A string that identifies the next page of stack resources that you want to retrieve.

        

      
      
      :rtype: list(:py:class:`cloudformation.StackResourceSummary`)
      :returns: A list of StackResourceSummary resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of StackResourceSummary resources in the collection.

      **Request Syntax** 
      ::

        stack_resource_summary_iterator = stack.resource_summaries.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`cloudformation.StackResourceSummary`)
      :returns: A list of StackResourceSummary resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all StackResourceSummary resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        stack_resource_summary_iterator = stack.resource_summaries.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`cloudformation.StackResourceSummary`)
      :returns: A list of StackResourceSummary resources
      

=============
StackResource
=============



.. py:class:: CloudFormation.StackResource(stack_name,logical_id)

  A resource representing an AWS CloudFormation StackResource::

    
    import boto3
    
    cloudformation = boto3.resource('cloudformation')
    stack_resource = cloudformation.StackResource('stack_name','logical_id')

  :type stack_name: string
  :param stack_name: The StackResource's stack_name identifier. This **must** be set.
  :type logical_id: string
  :param logical_id: The StackResource's logical_id identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`stack_name`

  
  *   :py:attr:`logical_id`

  
  These are the resource's available attributes:
  
  *   :py:attr:`description`

  
  *   :py:attr:`last_updated_timestamp`

  
  *   :py:attr:`logical_resource_id`

  
  *   :py:attr:`metadata`

  
  *   :py:attr:`physical_resource_id`

  
  *   :py:attr:`resource_status`

  
  *   :py:attr:`resource_status_reason`

  
  *   :py:attr:`resource_type`

  
  *   :py:attr:`stack_id`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Stack()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: stack_name

    *(string)* The StackResource's stack_name identifier. This **must** be set.

  .. py:attribute:: logical_id

    *(string)* The StackResource's logical_id identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: description

    

    - *(string) --* 

      User defined description associated with the resource.

      

  .. py:attribute:: last_updated_timestamp

    

    - *(datetime) --* 

      Time the status was updated.

      

  .. py:attribute:: logical_resource_id

    

    - *(string) --* 

      The logical name of the resource specified in the template.

      

  .. py:attribute:: metadata

    

    - *(string) --* 

      The JSON format content of the ``Metadata`` attribute declared for the resource. For more information, see `Metadata Attribute`_ in the AWS CloudFormation User Guide.

      

  .. py:attribute:: physical_resource_id

    

    - *(string) --* 

      The name or unique identifier that corresponds to a physical instance ID of a resource supported by AWS CloudFormation.

      

  .. py:attribute:: resource_status

    

    - *(string) --* 

      Current status of the resource.

      

  .. py:attribute:: resource_status_reason

    

    - *(string) --* 

      Success/failure message associated with the resource.

      

  .. py:attribute:: resource_type

    

    - *(string) --* 

      Type of resource. ((For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

      

  .. py:attribute:: stack_id

    

    - *(string) --* 

      Unique identifier of the stack.

      
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Stack()

    Creates a Stack resource.::

      stack = stack_resource.Stack()

    
    :rtype: :py:class:`CloudFormation.Stack`
    :returns: A Stack resource
    

====================
StackResourceSummary
====================



.. py:class:: CloudFormation.StackResourceSummary(stack_name,logical_id)

  A resource representing an AWS CloudFormation StackResourceSummary::

    
    import boto3
    
    cloudformation = boto3.resource('cloudformation')
    stack_resource_summary = cloudformation.StackResourceSummary('stack_name','logical_id')

  :type stack_name: string
  :param stack_name: The StackResourceSummary's stack_name identifier. This **must** be set.
  :type logical_id: string
  :param logical_id: The StackResourceSummary's logical_id identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`stack_name`

  
  *   :py:attr:`logical_id`

  
  These are the resource's available attributes:
  
  *   :py:attr:`last_updated_timestamp`

  
  *   :py:attr:`logical_resource_id`

  
  *   :py:attr:`physical_resource_id`

  
  *   :py:attr:`resource_status`

  
  *   :py:attr:`resource_status_reason`

  
  *   :py:attr:`resource_type`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Resource()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: stack_name

    *(string)* The StackResourceSummary's stack_name identifier. This **must** be set.

  .. py:attribute:: logical_id

    *(string)* The StackResourceSummary's logical_id identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: last_updated_timestamp

    

    - *(datetime) --* 

      Time the status was updated.

      

  .. py:attribute:: logical_resource_id

    

    - *(string) --* 

      The logical name of the resource specified in the template.

      

  .. py:attribute:: physical_resource_id

    

    - *(string) --* 

      The name or unique identifier that corresponds to a physical instance ID of the resource.

      

  .. py:attribute:: resource_status

    

    - *(string) --* 

      Current status of the resource.

      

  .. py:attribute:: resource_status_reason

    

    - *(string) --* 

      Success/failure message associated with the resource.

      

  .. py:attribute:: resource_type

    

    - *(string) --* 

      Type of resource. (For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

      
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Resource()

    Creates a StackResource resource.::

      stack_resource = stack_resource_summary.Resource()

    
    :rtype: :py:class:`CloudFormation.StackResource`
    :returns: A StackResource resource
    