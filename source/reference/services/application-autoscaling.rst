

.. _AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#genref-aws-service-namespaces


**********************
ApplicationAutoScaling
**********************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: ApplicationAutoScaling.Client

  A low-level client representing Application Auto Scaling::

    
    import boto3
    
    client = boto3.client('application-autoscaling')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`delete_scaling_policy`

  
  *   :py:meth:`deregister_scalable_target`

  
  *   :py:meth:`describe_scalable_targets`

  
  *   :py:meth:`describe_scaling_activities`

  
  *   :py:meth:`describe_scaling_policies`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`put_scaling_policy`

  
  *   :py:meth:`register_scalable_target`

  

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


  .. py:method:: delete_scaling_policy(**kwargs)

    

    Deletes an Application Auto Scaling scaling policy that was previously created. If you are no longer using a scaling policy, you can delete it with this operation.

     

    Deleting a policy deletes the underlying alarm action, but does not delete the CloudWatch alarm associated with the scaling policy, even if it no longer has an associated action.

     

    To create a new scaling policy or update an existing one, see  PutScalingPolicy .

    

    **Request Syntax** 
    ::

      response = client.delete_scaling_policy(
          PolicyName='string',
          ServiceNamespace='ecs'|'ec2',
          ResourceId='string',
          ScalableDimension='ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity'
      )
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the scaling policy to delete.

      

    
    :type ServiceNamespace: string
    :param ServiceNamespace: **[REQUIRED]** 

      The namespace for the AWS service that the scaling policy is associated with. For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

      

    
    :type ResourceId: string
    :param ResourceId: **[REQUIRED]** 

      The resource type and unique identifier string for the resource associated with the scaling policy. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` .

      

    
    :type ScalableDimension: string
    :param ScalableDimension: **[REQUIRED]** 

      The scalable dimension associated with the scaling policy. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: deregister_scalable_target(**kwargs)

    

    Deregisters a scalable target that was previously registered. If you are no longer using a scalable target, you can delete it with this operation. When you deregister a scalable target, all of the scaling policies that are associated with that scalable target are deleted.

     

    To create a new scalable target or update an existing one, see  RegisterScalableTarget .

    

    **Request Syntax** 
    ::

      response = client.deregister_scalable_target(
          ServiceNamespace='ecs'|'ec2',
          ResourceId='string',
          ScalableDimension='ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity'
      )
    :type ServiceNamespace: string
    :param ServiceNamespace: **[REQUIRED]** 

      The namespace for the AWS service that the scalable target is associated with. For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

      

    
    :type ResourceId: string
    :param ResourceId: **[REQUIRED]** 

      The resource type and unique identifier string for the resource associated with the scalable target. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` .

      

    
    :type ScalableDimension: string
    :param ScalableDimension: **[REQUIRED]** 

      The scalable dimension associated with the scalable target. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: describe_scalable_targets(**kwargs)

    

    Provides descriptive information for scalable targets with a specified service namespace.

     

    You can filter the results in a service namespace with the ``ResourceIds`` and ``ScalableDimension`` parameters.

     

    To create a new scalable target or update an existing one, see  RegisterScalableTarget . If you are no longer using a scalable target, you can deregister it with  DeregisterScalableTarget .

    

    **Request Syntax** 
    ::

      response = client.describe_scalable_targets(
          ServiceNamespace='ecs'|'ec2',
          ResourceIds=[
              'string',
          ],
          ScalableDimension='ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity',
          MaxResults=123,
          NextToken='string'
      )
    :type ServiceNamespace: string
    :param ServiceNamespace: **[REQUIRED]** 

      The namespace for the AWS service that the scalable target is associated with. For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

      

    
    :type ResourceIds: list
    :param ResourceIds: 

      The resource type and unique identifier string for the resource associated with the scalable target. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` . If you specify a scalable dimension, you must also specify a resource ID.

      

    
      - *(string) --* 

      
  
    :type ScalableDimension: string
    :param ScalableDimension: 

      The scalable dimension associated with the scalable target. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request. If you specify a scalable dimension, you must also specify a resource ID.

      

    
    :type MaxResults: integer
    :param MaxResults: 

      The maximum number of scalable target results returned by ``DescribeScalableTargets`` in paginated output. When this parameter is used, ``DescribeScalableTargets`` returns up to ``MaxResults`` results in a single page along with a ``NextToken`` response element. The remaining results of the initial request can be seen by sending another ``DescribeScalableTargets`` request with the returned ``NextToken`` value. This value can be between 1 and 50. If this parameter is not used, then ``DescribeScalableTargets`` returns up to 50 results and a ``NextToken`` value, if applicable.

      

    
    :type NextToken: string
    :param NextToken: 

      The ``NextToken`` value returned from a previous paginated ``DescribeScalableTargets`` request. Pagination continues from the end of the previous results that returned the ``NextToken`` value. This value is ``null`` when there are no more results to return.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ScalableTargets': [
                {
                    'ServiceNamespace': 'ecs'|'ec2',
                    'ResourceId': 'string',
                    'ScalableDimension': 'ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity',
                    'MinCapacity': 123,
                    'MaxCapacity': 123,
                    'RoleARN': 'string',
                    'CreationTime': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ScalableTargets** *(list) --* 

          The list of scalable targets that matches the request parameters.

          
          

          - *(dict) --* 

            An object representing a scalable target.

            
            

            - **ServiceNamespace** *(string) --* 

              The namespace for the AWS service that the scalable target is associated with. For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

              
            

            - **ResourceId** *(string) --* 

              The resource type and unique identifier string for the resource associated with the scalable target. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` .

              
            

            - **ScalableDimension** *(string) --* 

              The scalable dimension associated with the scalable target. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request.

              
            

            - **MinCapacity** *(integer) --* 

              The minimum value for this scalable target to scale in to in response to scaling activities.

              
            

            - **MaxCapacity** *(integer) --* 

              The maximum value for this scalable target to scale out to in response to scaling activities.

              
            

            - **RoleARN** *(string) --* 

              The ARN of the IAM role that allows Application Auto Scaling to modify your scalable target on your behalf.

              
            

            - **CreationTime** *(datetime) --* 

              The Unix timestamp for when the scalable target was created.

              
        
      
        

        - **NextToken** *(string) --* 

          The ``NextToken`` value to include in a future ``DescribeScalableTargets`` request. When the results of a ``DescribeScalableTargets`` request exceed ``MaxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

  .. py:method:: describe_scaling_activities(**kwargs)

    

    Provides descriptive information for scaling activities with a specified service namespace for the previous six weeks.

     

    You can filter the results in a service namespace with the ``ResourceId`` and ``ScalableDimension`` parameters.

     

    Scaling activities are triggered by CloudWatch alarms that are associated with scaling policies. To view the existing scaling policies for a service namespace, see  DescribeScalingPolicies . To create a new scaling policy or update an existing one, see  PutScalingPolicy .

    

    **Request Syntax** 
    ::

      response = client.describe_scaling_activities(
          ServiceNamespace='ecs'|'ec2',
          ResourceId='string',
          ScalableDimension='ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity',
          MaxResults=123,
          NextToken='string'
      )
    :type ServiceNamespace: string
    :param ServiceNamespace: **[REQUIRED]** 

      The namespace for the AWS service that the scaling activity is associated with. For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

      

    
    :type ResourceId: string
    :param ResourceId: 

      The resource type and unique identifier string for the resource associated with the scaling activity. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` . If you specify a scalable dimension, you must also specify a resource ID.

      

    
    :type ScalableDimension: string
    :param ScalableDimension: 

      The scalable dimension associated with the scaling activity. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request. If you specify a scalable dimension, you must also specify a resource ID.

      

    
    :type MaxResults: integer
    :param MaxResults: 

      The maximum number of scaling activity results returned by ``DescribeScalingActivities`` in paginated output. When this parameter is used, ``DescribeScalingActivities`` returns up to ``MaxResults`` results in a single page along with a ``NextToken`` response element. The remaining results of the initial request can be seen by sending another ``DescribeScalingActivities`` request with the returned ``NextToken`` value. This value can be between 1 and 50. If this parameter is not used, then ``DescribeScalingActivities`` returns up to 50 results and a ``NextToken`` value, if applicable.

      

    
    :type NextToken: string
    :param NextToken: 

      The ``NextToken`` value returned from a previous paginated ``DescribeScalingActivities`` request. Pagination continues from the end of the previous results that returned the ``NextToken`` value. This value is ``null`` when there are no more results to return.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ScalingActivities': [
                {
                    'ActivityId': 'string',
                    'ServiceNamespace': 'ecs'|'ec2',
                    'ResourceId': 'string',
                    'ScalableDimension': 'ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity',
                    'Description': 'string',
                    'Cause': 'string',
                    'StartTime': datetime(2015, 1, 1),
                    'EndTime': datetime(2015, 1, 1),
                    'StatusCode': 'Pending'|'InProgress'|'Successful'|'Overridden'|'Unfulfilled'|'Failed',
                    'StatusMessage': 'string',
                    'Details': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ScalingActivities** *(list) --* 

          A list of scaling activity objects.

          
          

          - *(dict) --* 

            An object representing a scaling activity.

            
            

            - **ActivityId** *(string) --* 

              The unique identifier string for the scaling activity.

              
            

            - **ServiceNamespace** *(string) --* 

              The namespace for the AWS service that the scaling activity is associated with. For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

              
            

            - **ResourceId** *(string) --* 

              The resource type and unique identifier string for the resource associated with the scaling activity. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` .

              
            

            - **ScalableDimension** *(string) --* 

              The scalable dimension associated with the scaling activity. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request.

              
            

            - **Description** *(string) --* 

              A simple description of what action the scaling activity intends to accomplish.

              
            

            - **Cause** *(string) --* 

              A simple description of what caused the scaling activity to happen.

              
            

            - **StartTime** *(datetime) --* 

              The Unix timestamp for when the scaling activity began.

              
            

            - **EndTime** *(datetime) --* 

              The Unix timestamp for when the scaling activity ended.

              
            

            - **StatusCode** *(string) --* 

              Indicates the status of the scaling activity.

              
            

            - **StatusMessage** *(string) --* 

              A simple message about the current status of the scaling activity.

              
            

            - **Details** *(string) --* 

              The details about the scaling activity.

              
        
      
        

        - **NextToken** *(string) --* 

          The ``NextToken`` value to include in a future ``DescribeScalingActivities`` request. When the results of a ``DescribeScalingActivities`` request exceed ``MaxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

  .. py:method:: describe_scaling_policies(**kwargs)

    

    Provides descriptive information for scaling policies with a specified service namespace.

     

    You can filter the results in a service namespace with the ``ResourceId`` , ``ScalableDimension`` , and ``PolicyNames`` parameters.

     

    To create a new scaling policy or update an existing one, see  PutScalingPolicy . If you are no longer using a scaling policy, you can delete it with  DeleteScalingPolicy .

    

    **Request Syntax** 
    ::

      response = client.describe_scaling_policies(
          PolicyNames=[
              'string',
          ],
          ServiceNamespace='ecs'|'ec2',
          ResourceId='string',
          ScalableDimension='ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity',
          MaxResults=123,
          NextToken='string'
      )
    :type PolicyNames: list
    :param PolicyNames: 

      The names of the scaling policies to describe.

      

    
      - *(string) --* 

      
  
    :type ServiceNamespace: string
    :param ServiceNamespace: **[REQUIRED]** 

      The AWS service namespace of the scalable target that the scaling policy is associated with. For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

      

    
    :type ResourceId: string
    :param ResourceId: 

      The unique resource identifier string of the scalable target that the scaling policy is associated with. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` . If you specify a scalable dimension, you must also specify a resource ID.

      

    
    :type ScalableDimension: string
    :param ScalableDimension: 

      The scalable dimension of the scalable target that the scaling policy is associated with. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request. If you specify a scalable dimension, you must also specify a resource ID.

      

    
    :type MaxResults: integer
    :param MaxResults: 

      The maximum number of scaling policy results returned by ``DescribeScalingPolicies`` in paginated output. When this parameter is used, ``DescribeScalingPolicies`` returns up to ``MaxResults`` results in a single page along with a ``NextToken`` response element. The remaining results of the initial request can be seen by sending another ``DescribeScalingPolicies`` request with the returned ``NextToken`` value. This value can be between 1 and 50. If this parameter is not used, then ``DescribeScalingPolicies`` returns up to 50 results and a ``NextToken`` value, if applicable.

      

    
    :type NextToken: string
    :param NextToken: 

      The ``NextToken`` value returned from a previous paginated ``DescribeScalingPolicies`` request. Pagination continues from the end of the previous results that returned the ``NextToken`` value. This value is ``null`` when there are no more results to return.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ScalingPolicies': [
                {
                    'PolicyARN': 'string',
                    'PolicyName': 'string',
                    'ServiceNamespace': 'ecs'|'ec2',
                    'ResourceId': 'string',
                    'ScalableDimension': 'ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity',
                    'PolicyType': 'StepScaling',
                    'StepScalingPolicyConfiguration': {
                        'AdjustmentType': 'ChangeInCapacity'|'PercentChangeInCapacity'|'ExactCapacity',
                        'StepAdjustments': [
                            {
                                'MetricIntervalLowerBound': 123.0,
                                'MetricIntervalUpperBound': 123.0,
                                'ScalingAdjustment': 123
                            },
                        ],
                        'MinAdjustmentMagnitude': 123,
                        'Cooldown': 123,
                        'MetricAggregationType': 'Average'|'Minimum'|'Maximum'
                    },
                    'Alarms': [
                        {
                            'AlarmName': 'string',
                            'AlarmARN': 'string'
                        },
                    ],
                    'CreationTime': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ScalingPolicies** *(list) --* 

          A list of scaling policy objects.

          
          

          - *(dict) --* 

            An object representing a scaling policy.

            
            

            - **PolicyARN** *(string) --* 

              The Amazon Resource Name (ARN) of the scaling policy.

              
            

            - **PolicyName** *(string) --* 

              The name of the scaling policy.

              
            

            - **ServiceNamespace** *(string) --* 

              The namespace for the AWS service that the scaling policy is associated with. For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

              
            

            - **ResourceId** *(string) --* 

              The resource type and unique identifier string for the resource associated with the scaling policy. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` .

              
            

            - **ScalableDimension** *(string) --* 

              The scalable dimension associated with the scaling policy. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request.

              
            

            - **PolicyType** *(string) --* 

              The scaling policy type.

              
            

            - **StepScalingPolicyConfiguration** *(dict) --* 

              The configuration for the step scaling policy.

              
              

              - **AdjustmentType** *(string) --* 

                The adjustment type, which specifies how the ``ScalingAdjustment`` parameter in a  StepAdjustment is interpreted.

                
              

              - **StepAdjustments** *(list) --* 

                A set of adjustments that enable you to scale based on the size of the alarm breach.

                
                

                - *(dict) --* 

                  An object representing a step adjustment for a  StepScalingPolicyConfiguration . Describes an adjustment based on the difference between the value of the aggregated CloudWatch metric and the breach threshold that you've defined for the alarm. 

                   

                  For the following examples, suppose that you have an alarm with a breach threshold of 50:

                   

                   
                  * If you want the adjustment to be triggered when the metric is greater than or equal to 50 and less than 60, specify a lower bound of 0 and an upper bound of 10. 
                   
                  * If you want the adjustment to be triggered when the metric is greater than 40 and less than or equal to 50, specify a lower bound of -10 and an upper bound of 0. 
                   

                   

                  There are a few rules for the step adjustments for your step policy:

                   

                   
                  * The ranges of your step adjustments can't overlap or have a gap. 
                   
                  * At most one step adjustment can have a null lower bound. If one step adjustment has a negative lower bound, then there must be a step adjustment with a null lower bound. 
                   
                  * At most one step adjustment can have a null upper bound. If one step adjustment has a positive upper bound, then there must be a step adjustment with a null upper bound. 
                   
                  * The upper and lower bound can't be null in the same step adjustment. 
                   

                  
                  

                  - **MetricIntervalLowerBound** *(float) --* 

                    The lower bound for the difference between the alarm threshold and the CloudWatch metric. If the metric value is above the breach threshold, the lower bound is inclusive (the metric must be greater than or equal to the threshold plus the lower bound). Otherwise, it is exclusive (the metric must be greater than the threshold plus the lower bound). A null value indicates negative infinity.

                    
                  

                  - **MetricIntervalUpperBound** *(float) --* 

                    The upper bound for the difference between the alarm threshold and the CloudWatch metric. If the metric value is above the breach threshold, the upper bound is exclusive (the metric must be less than the threshold plus the upper bound). Otherwise, it is inclusive (the metric must be less than or equal to the threshold plus the upper bound). A null value indicates positive infinity.

                     

                    The upper bound must be greater than the lower bound.

                    
                  

                  - **ScalingAdjustment** *(integer) --* 

                    The amount by which to scale, based on the specified adjustment type. A positive value adds to the current scalable dimension while a negative number removes from the current scalable dimension.

                    
              
            
              

              - **MinAdjustmentMagnitude** *(integer) --* 

                The minimum number to adjust your scalable dimension as a result of a scaling activity. If the adjustment type is ``PercentChangeInCapacity`` , the scaling policy changes the scalable dimension of the scalable target by this amount.

                
              

              - **Cooldown** *(integer) --* 

                The amount of time, in seconds, after a scaling activity completes where previous trigger-related scaling activities can influence future scaling events.

                 

                For scale out policies, while ``Cooldown`` is in effect, the capacity that has been added by the previous scale out event that initiated the ``Cooldown`` is calculated as part of the desired capacity for the next scale out. The intention is to continuously (but not excessively) scale out. For example, an alarm triggers a step scaling policy to scale out an Amazon ECS service by 2 tasks, the scaling activity completes successfully, and a ``Cooldown`` period of 5 minutes starts. During the ``Cooldown`` period, if the alarm triggers the same policy again but at a more aggressive step adjustment to scale out the service by 3 tasks, the 2 tasks that were added in the previous scale out event are considered part of that capacity and only 1 additional task is added to the desired count.

                 

                For scale in policies, the ``Cooldown`` period is used to block subsequent scale in requests until it has expired. The intention is to scale in conservatively to protect your application's availability. However, if another alarm triggers a scale out policy during the ``Cooldown`` period after a scale-in, Application Auto Scaling scales out your scalable target immediately.

                
              

              - **MetricAggregationType** *(string) --* 

                The aggregation type for the CloudWatch metrics. Valid values are ``Minimum`` , ``Maximum`` , and ``Average`` .

                
          
            

            - **Alarms** *(list) --* 

              The CloudWatch alarms that are associated with the scaling policy.

              
              

              - *(dict) --* 

                An object representing a CloudWatch alarm associated with a scaling policy.

                
                

                - **AlarmName** *(string) --* 

                  The name of the alarm.

                  
                

                - **AlarmARN** *(string) --* 

                  The Amazon Resource Name (ARN) of the alarm.

                  
            
          
            

            - **CreationTime** *(datetime) --* 

              The Unix timestamp for when the scaling policy was created.

              
        
      
        

        - **NextToken** *(string) --* 

          The ``NextToken`` value to include in a future ``DescribeScalingPolicies`` request. When the results of a ``DescribeScalingPolicies`` request exceed ``MaxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

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

        


  .. py:method:: put_scaling_policy(**kwargs)

    

    Creates or updates a policy for an existing Application Auto Scaling scalable target. Each scalable target is identified by service namespace, a resource ID, and a scalable dimension, and a scaling policy applies to a scalable target that is identified by those three attributes. You cannot create a scaling policy without first registering a scalable target with  RegisterScalableTarget .

     

    To update an existing policy, use the existing policy name and set the parameters you want to change. Any existing parameter not changed in an update to an existing policy is not changed in this update request.

     

    You can view the existing scaling policies for a service namespace with  DescribeScalingPolicies . If you are no longer using a scaling policy, you can delete it with  DeleteScalingPolicy .

    

    **Request Syntax** 
    ::

      response = client.put_scaling_policy(
          PolicyName='string',
          ServiceNamespace='ecs'|'ec2',
          ResourceId='string',
          ScalableDimension='ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity',
          PolicyType='StepScaling',
          StepScalingPolicyConfiguration={
              'AdjustmentType': 'ChangeInCapacity'|'PercentChangeInCapacity'|'ExactCapacity',
              'StepAdjustments': [
                  {
                      'MetricIntervalLowerBound': 123.0,
                      'MetricIntervalUpperBound': 123.0,
                      'ScalingAdjustment': 123
                  },
              ],
              'MinAdjustmentMagnitude': 123,
              'Cooldown': 123,
              'MetricAggregationType': 'Average'|'Minimum'|'Maximum'
          }
      )
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the scaling policy.

      

    
    :type ServiceNamespace: string
    :param ServiceNamespace: **[REQUIRED]** 

      The AWS service namespace of the scalable target that this scaling policy applies to. For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

      

    
    :type ResourceId: string
    :param ResourceId: **[REQUIRED]** 

      The unique resource identifier string for the scalable target that this scaling policy applies to. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` .

      

    
    :type ScalableDimension: string
    :param ScalableDimension: **[REQUIRED]** 

      The scalable dimension of the scalable target that this scaling policy applies to. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request.

      

    
    :type PolicyType: string
    :param PolicyType: 

      The policy type. If you are creating a new policy, this parameter is required. If you are updating an existing policy, this parameter is not required.

      

    
    :type StepScalingPolicyConfiguration: dict
    :param StepScalingPolicyConfiguration: 

      The configuration for the step scaling policy. If you are creating a new policy, this parameter is required. If you are updating an existing policy, this parameter is not required. For more information, see  StepScalingPolicyConfiguration and  StepAdjustment .

      

    
      - **AdjustmentType** *(string) --* 

        The adjustment type, which specifies how the ``ScalingAdjustment`` parameter in a  StepAdjustment is interpreted.

        

      
      - **StepAdjustments** *(list) --* 

        A set of adjustments that enable you to scale based on the size of the alarm breach.

        

      
        - *(dict) --* 

          An object representing a step adjustment for a  StepScalingPolicyConfiguration . Describes an adjustment based on the difference between the value of the aggregated CloudWatch metric and the breach threshold that you've defined for the alarm. 

           

          For the following examples, suppose that you have an alarm with a breach threshold of 50:

           

           
          * If you want the adjustment to be triggered when the metric is greater than or equal to 50 and less than 60, specify a lower bound of 0 and an upper bound of 10. 
           
          * If you want the adjustment to be triggered when the metric is greater than 40 and less than or equal to 50, specify a lower bound of -10 and an upper bound of 0. 
           

           

          There are a few rules for the step adjustments for your step policy:

           

           
          * The ranges of your step adjustments can't overlap or have a gap. 
           
          * At most one step adjustment can have a null lower bound. If one step adjustment has a negative lower bound, then there must be a step adjustment with a null lower bound. 
           
          * At most one step adjustment can have a null upper bound. If one step adjustment has a positive upper bound, then there must be a step adjustment with a null upper bound. 
           
          * The upper and lower bound can't be null in the same step adjustment. 
           

          

        
          - **MetricIntervalLowerBound** *(float) --* 

            The lower bound for the difference between the alarm threshold and the CloudWatch metric. If the metric value is above the breach threshold, the lower bound is inclusive (the metric must be greater than or equal to the threshold plus the lower bound). Otherwise, it is exclusive (the metric must be greater than the threshold plus the lower bound). A null value indicates negative infinity.

            

          
          - **MetricIntervalUpperBound** *(float) --* 

            The upper bound for the difference between the alarm threshold and the CloudWatch metric. If the metric value is above the breach threshold, the upper bound is exclusive (the metric must be less than the threshold plus the upper bound). Otherwise, it is inclusive (the metric must be less than or equal to the threshold plus the upper bound). A null value indicates positive infinity.

             

            The upper bound must be greater than the lower bound.

            

          
          - **ScalingAdjustment** *(integer) --* **[REQUIRED]** 

            The amount by which to scale, based on the specified adjustment type. A positive value adds to the current scalable dimension while a negative number removes from the current scalable dimension.

            

          
        
    
      - **MinAdjustmentMagnitude** *(integer) --* 

        The minimum number to adjust your scalable dimension as a result of a scaling activity. If the adjustment type is ``PercentChangeInCapacity`` , the scaling policy changes the scalable dimension of the scalable target by this amount.

        

      
      - **Cooldown** *(integer) --* 

        The amount of time, in seconds, after a scaling activity completes where previous trigger-related scaling activities can influence future scaling events.

         

        For scale out policies, while ``Cooldown`` is in effect, the capacity that has been added by the previous scale out event that initiated the ``Cooldown`` is calculated as part of the desired capacity for the next scale out. The intention is to continuously (but not excessively) scale out. For example, an alarm triggers a step scaling policy to scale out an Amazon ECS service by 2 tasks, the scaling activity completes successfully, and a ``Cooldown`` period of 5 minutes starts. During the ``Cooldown`` period, if the alarm triggers the same policy again but at a more aggressive step adjustment to scale out the service by 3 tasks, the 2 tasks that were added in the previous scale out event are considered part of that capacity and only 1 additional task is added to the desired count.

         

        For scale in policies, the ``Cooldown`` period is used to block subsequent scale in requests until it has expired. The intention is to scale in conservatively to protect your application's availability. However, if another alarm triggers a scale out policy during the ``Cooldown`` period after a scale-in, Application Auto Scaling scales out your scalable target immediately.

        

      
      - **MetricAggregationType** *(string) --* 

        The aggregation type for the CloudWatch metrics. Valid values are ``Minimum`` , ``Maximum`` , and ``Average`` .

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **PolicyARN** *(string) --* 

          The Amazon Resource Name (ARN) of the resulting scaling policy.

          
    

  .. py:method:: register_scalable_target(**kwargs)

    

    Registers or updates a scalable target. A scalable target is a resource that can be scaled out or in with Application Auto Scaling. After you have registered a scalable target, you can use this operation to update the minimum and maximum values for your scalable dimension.

     

    After you register a scalable target with Application Auto Scaling, you can create and apply scaling policies to it with  PutScalingPolicy . You can view the existing scaling policies for a service namespace with  DescribeScalableTargets . If you are no longer using a scalable target, you can deregister it with  DeregisterScalableTarget .

    

    **Request Syntax** 
    ::

      response = client.register_scalable_target(
          ServiceNamespace='ecs'|'ec2',
          ResourceId='string',
          ScalableDimension='ecs:service:DesiredCount'|'ec2:spot-fleet-request:TargetCapacity',
          MinCapacity=123,
          MaxCapacity=123,
          RoleARN='string'
      )
    :type ServiceNamespace: string
    :param ServiceNamespace: **[REQUIRED]** 

      The namespace for the AWS service that the scalable target is associated with. For Amazon ECS services, the namespace value is ``ecs`` . For more information, see `AWS Service Namespaces`_ in the Amazon Web Services General Reference.

      

    
    :type ResourceId: string
    :param ResourceId: **[REQUIRED]** 

      The resource type and unique identifier string for the resource to associate with the scalable target. For Amazon ECS services, the resource type is ``services`` , and the identifier is the cluster name and service name; for example, ``service/default/sample-webapp`` . For Amazon EC2 Spot fleet requests, the resource type is ``spot-fleet-request`` , and the identifier is the Spot fleet request ID; for example, ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` .

      

    
    :type ScalableDimension: string
    :param ScalableDimension: **[REQUIRED]** 

      The scalable dimension associated with the scalable target. The scalable dimension contains the service namespace, resource type, and scaling property, such as ``ecs:service:DesiredCount`` for the desired task count of an Amazon ECS service, or ``ec2:spot-fleet-request:TargetCapacity`` for the target capacity of an Amazon EC2 Spot fleet request.

      

    
    :type MinCapacity: integer
    :param MinCapacity: 

      The minimum value for this scalable target to scale in to in response to scaling activities. This parameter is required if you are registering a new scalable target, and it is optional if you are updating an existing one.

      

    
    :type MaxCapacity: integer
    :param MaxCapacity: 

      The maximum value for this scalable target to scale out to in response to scaling activities. This parameter is required if you are registering a new scalable target, and it is optional if you are updating an existing one.

      

    
    :type RoleARN: string
    :param RoleARN: 

      The ARN of the IAM role that allows Application Auto Scaling to modify your scalable target on your behalf. This parameter is required if you are registering a new scalable target, and it is optional if you are updating an existing one.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    