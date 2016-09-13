

.. _Instance Protection: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingBehavior.InstanceTermination.html#instance-protection
.. _Amazon EBS Volume Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html
.. _Health Checks: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/healthcheck.html
.. _Amazon EBS-Optimized Instances: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html
.. _Launch Configurations: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/LaunchConfiguration.html
.. _Suspending and Resuming Auto Scaling Processes: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/US_SuspendResume.html
.. _Amazon EBS Encryption: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html
.. _Launch Auto Scaling Instances with an IAM Role: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/us-iam-role.html
.. _Auto Scaling Lifecycle: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingGroupLifecycle.html
.. _Tagging Auto Scaling Groups and Instances: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASTagging.html
.. _Using a Load Balancer With an Auto Scaling Group: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/US_SetUpASLBApp.html
.. _Block Device Mapping: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html
.. _ClassicLink: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/vpc-classiclink.html
.. _Detach EC2 Instances from Your Auto Scaling Group: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/detach-instance-asg.html
.. _Scheduled Scaling: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/schedule_time.html
.. _Launching Auto Scaling Instances in a VPC: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/asg-in-vpc.html
.. _Auto Scaling Processes: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/US_SuspendResume.html#process-types
.. _Create an Auto Scaling Group Using an EC2 Instance: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/create-asg-from-instance.html
.. _Controlling Which Instances Auto Scaling Terminates During Scale In: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingBehavior.InstanceTermination.html
.. _Launching Spot Instances in Your Auto Scaling Group: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/US-SpotInstances.html
.. _Attach EC2 Instances to Your Auto Scaling Group: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/attach-instance-asg.html
.. _Security Groups for Your VPC: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_SecurityGroups.html
.. _What Is Auto Scaling?: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/WhatIsAutoScaling.html
.. _Supported Platforms: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-supported-platforms.html
.. _Placement Groups: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html
.. _Available Instance Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html#AvailableInstanceTypes
.. _Monitoring Your Auto Scaling Groups and Instances: http://docs.aws.amazon.com/AutoScaling/latest/userguide/as-instance-monitoring.html
.. _Finding an AMI: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/finding-an-ami.html
.. _Create a Launch Configuration Using an EC2 Instance: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/create-lc-with-instanceID.html
.. _AWS Service Limits: http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html
.. _Instance Metadata and User Data: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html
.. _Attach a Load Balancer to Your Auto Scaling Group: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/attach-load-balancer-asg.html
.. _Auto Scaling Cooldowns: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/Cooldown.html
.. _Dynamic Scaling: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html
.. _Amazon EC2 Key Pairs: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html
.. _Amazon EC2 Security Groups: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html
.. _Cron: http://en.wikipedia.org/wiki/Cron
.. _Auto Scaling Groups: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingGroup.html
.. _Getting SNS Notifications When Your Auto Scaling Group Scales: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASGettingNotifications.html


***********
AutoScaling
***********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: AutoScaling.Client

  A low-level client representing Auto Scaling::

    
    import boto3
    
    client = boto3.client('autoscaling')

  
  These are the available methods:
  
  *   :py:meth:`attach_instances`

  
  *   :py:meth:`attach_load_balancer_target_groups`

  
  *   :py:meth:`attach_load_balancers`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`complete_lifecycle_action`

  
  *   :py:meth:`create_auto_scaling_group`

  
  *   :py:meth:`create_launch_configuration`

  
  *   :py:meth:`create_or_update_tags`

  
  *   :py:meth:`delete_auto_scaling_group`

  
  *   :py:meth:`delete_launch_configuration`

  
  *   :py:meth:`delete_lifecycle_hook`

  
  *   :py:meth:`delete_notification_configuration`

  
  *   :py:meth:`delete_policy`

  
  *   :py:meth:`delete_scheduled_action`

  
  *   :py:meth:`delete_tags`

  
  *   :py:meth:`describe_account_limits`

  
  *   :py:meth:`describe_adjustment_types`

  
  *   :py:meth:`describe_auto_scaling_groups`

  
  *   :py:meth:`describe_auto_scaling_instances`

  
  *   :py:meth:`describe_auto_scaling_notification_types`

  
  *   :py:meth:`describe_launch_configurations`

  
  *   :py:meth:`describe_lifecycle_hook_types`

  
  *   :py:meth:`describe_lifecycle_hooks`

  
  *   :py:meth:`describe_load_balancer_target_groups`

  
  *   :py:meth:`describe_load_balancers`

  
  *   :py:meth:`describe_metric_collection_types`

  
  *   :py:meth:`describe_notification_configurations`

  
  *   :py:meth:`describe_policies`

  
  *   :py:meth:`describe_scaling_activities`

  
  *   :py:meth:`describe_scaling_process_types`

  
  *   :py:meth:`describe_scheduled_actions`

  
  *   :py:meth:`describe_tags`

  
  *   :py:meth:`describe_termination_policy_types`

  
  *   :py:meth:`detach_instances`

  
  *   :py:meth:`detach_load_balancer_target_groups`

  
  *   :py:meth:`detach_load_balancers`

  
  *   :py:meth:`disable_metrics_collection`

  
  *   :py:meth:`enable_metrics_collection`

  
  *   :py:meth:`enter_standby`

  
  *   :py:meth:`execute_policy`

  
  *   :py:meth:`exit_standby`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`put_lifecycle_hook`

  
  *   :py:meth:`put_notification_configuration`

  
  *   :py:meth:`put_scaling_policy`

  
  *   :py:meth:`put_scheduled_update_group_action`

  
  *   :py:meth:`record_lifecycle_action_heartbeat`

  
  *   :py:meth:`resume_processes`

  
  *   :py:meth:`set_desired_capacity`

  
  *   :py:meth:`set_instance_health`

  
  *   :py:meth:`set_instance_protection`

  
  *   :py:meth:`suspend_processes`

  
  *   :py:meth:`terminate_instance_in_auto_scaling_group`

  
  *   :py:meth:`update_auto_scaling_group`

  

  .. py:method:: attach_instances(**kwargs)

    

    Attaches one or more EC2 instances to the specified Auto Scaling group.

     

    When you attach instances, Auto Scaling increases the desired capacity of the group by the number of instances being attached. If the number of instances being attached plus the desired capacity of the group exceeds the maximum size of the group, the operation fails.

     

    If there is a Classic load balancer attached to your Auto Scaling group, the instances are also registered with the load balancer. If there are target groups attached to your Auto Scaling group, the instances are also registered with the target groups.

     

    For more information, see `Attach EC2 Instances to Your Auto Scaling Group`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.attach_instances(
          InstanceIds=[
              'string',
          ],
          AutoScalingGroupName='string'
      )
    :type InstanceIds: list
    :param InstanceIds: 

      One or more instance IDs.

      

    
      - *(string) --* 

      
  
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the group.

      

    
    
    :returns: None

  .. py:method:: attach_load_balancer_target_groups(**kwargs)

    

    Attaches one or more target groups to the specified Auto Scaling group.

     

    To describe the target groups for an Auto Scaling group, use  DescribeLoadBalancerTargetGroups . To detach the target group from the Auto Scaling group, use  DetachLoadBalancerTargetGroups .

     

    For more information, see `Attach a Load Balancer to Your Auto Scaling Group`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.attach_load_balancer_target_groups(
          AutoScalingGroupName='string',
          TargetGroupARNs=[
              'string',
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type TargetGroupARNs: list
    :param TargetGroupARNs: **[REQUIRED]** 

      The Amazon Resource Names (ARN) of the target groups.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: attach_load_balancers(**kwargs)

    

    Attaches one or more Classic load balancers to the specified Auto Scaling group.

     

    To attach an Application load balancer instead, see  AttachLoadBalancerTargetGroups .

     

    To describe the load balancers for an Auto Scaling group, use  DescribeLoadBalancers . To detach the load balancer from the Auto Scaling group, use  DetachLoadBalancers .

     

    For more information, see `Attach a Load Balancer to Your Auto Scaling Group`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.attach_load_balancers(
          AutoScalingGroupName='string',
          LoadBalancerNames=[
              'string',
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the group.

      

    
    :type LoadBalancerNames: list
    :param LoadBalancerNames: **[REQUIRED]** 

      One or more load balancer names.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of AttachLoadBalancers.

        
    

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


  .. py:method:: complete_lifecycle_action(**kwargs)

    

    Completes the lifecycle action for the specified token or instance with the specified result.

     

    This step is a part of the procedure for adding a lifecycle hook to an Auto Scaling group:

     

     
    * (Optional) Create a Lambda function and a rule that allows CloudWatch Events to invoke your Lambda function when Auto Scaling launches or terminates instances. 
     
    * (Optional) Create a notification target and an IAM role. The target can be either an Amazon SQS queue or an Amazon SNS topic. The role allows Auto Scaling to publish lifecycle notifications to the target. 
     
    * Create the lifecycle hook. Specify whether the hook is used when the instances launch or terminate. 
     
    * If you need more time, record the lifecycle action heartbeat to keep the instance in a pending state. 
     
    * **If you finish before the timeout period ends, complete the lifecycle action.**   
     

     

    For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.complete_lifecycle_action(
          LifecycleHookName='string',
          AutoScalingGroupName='string',
          LifecycleActionToken='string',
          LifecycleActionResult='string',
          InstanceId='string'
      )
    :type LifecycleHookName: string
    :param LifecycleHookName: **[REQUIRED]** 

      The name of the lifecycle hook.

      

    
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the group for the lifecycle hook.

      

    
    :type LifecycleActionToken: string
    :param LifecycleActionToken: 

      A universally unique identifier (UUID) that identifies a specific lifecycle action associated with an instance. Auto Scaling sends this token to the notification target you specified when you created the lifecycle hook.

      

    
    :type LifecycleActionResult: string
    :param LifecycleActionResult: **[REQUIRED]** 

      The action for the group to take. This parameter can be either ``CONTINUE`` or ``ABANDON`` .

      

    
    :type InstanceId: string
    :param InstanceId: 

      The ID of the instance.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of CompleteLifecycleAction.

        
    

  .. py:method:: create_auto_scaling_group(**kwargs)

    

    Creates an Auto Scaling group with the specified name and attributes.

     

    If you exceed your maximum limit of Auto Scaling groups, which by default is 20 per region, the call fails. For information about viewing and updating this limit, see  DescribeAccountLimits .

     

    For more information, see `Auto Scaling Groups`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_auto_scaling_group(
          AutoScalingGroupName='string',
          LaunchConfigurationName='string',
          InstanceId='string',
          MinSize=123,
          MaxSize=123,
          DesiredCapacity=123,
          DefaultCooldown=123,
          AvailabilityZones=[
              'string',
          ],
          LoadBalancerNames=[
              'string',
          ],
          TargetGroupARNs=[
              'string',
          ],
          HealthCheckType='string',
          HealthCheckGracePeriod=123,
          PlacementGroup='string',
          VPCZoneIdentifier='string',
          TerminationPolicies=[
              'string',
          ],
          NewInstancesProtectedFromScaleIn=True|False,
          Tags=[
              {
                  'ResourceId': 'string',
                  'ResourceType': 'string',
                  'Key': 'string',
                  'Value': 'string',
                  'PropagateAtLaunch': True|False
              },
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the group. This name must be unique within the scope of your AWS account.

      

    
    :type LaunchConfigurationName: string
    :param LaunchConfigurationName: 

      The name of the launch configuration. Alternatively, specify an EC2 instance instead of a launch configuration.

      

    
    :type InstanceId: string
    :param InstanceId: 

      The ID of the instance used to create a launch configuration for the group. Alternatively, specify a launch configuration instead of an EC2 instance.

       

      When you specify an ID of an instance, Auto Scaling creates a new launch configuration and associates it with the group. This launch configuration derives its attributes from the specified instance, with the exception of the block device mapping.

       

      For more information, see `Create an Auto Scaling Group Using an EC2 Instance`_ in the *Auto Scaling User Guide* .

      

    
    :type MinSize: integer
    :param MinSize: **[REQUIRED]** 

      The minimum size of the group.

      

    
    :type MaxSize: integer
    :param MaxSize: **[REQUIRED]** 

      The maximum size of the group.

      

    
    :type DesiredCapacity: integer
    :param DesiredCapacity: 

      The number of EC2 instances that should be running in the group. This number must be greater than or equal to the minimum size of the group and less than or equal to the maximum size of the group.

      

    
    :type DefaultCooldown: integer
    :param DefaultCooldown: 

      The amount of time, in seconds, after a scaling activity completes before another scaling activity can start. The default is 300.

       

      For more information, see `Auto Scaling Cooldowns`_ in the *Auto Scaling User Guide* .

      

    
    :type AvailabilityZones: list
    :param AvailabilityZones: 

      One or more Availability Zones for the group. This parameter is optional if you specify one or more subnets.

      

    
      - *(string) --* 

      
  
    :type LoadBalancerNames: list
    :param LoadBalancerNames: 

      One or more Classic load balancers. To specify an Application load balancer, use ``TargetGroupARNs`` instead.

       

      For more information, see `Using a Load Balancer With an Auto Scaling Group`_ in the *Auto Scaling User Guide* .

      

    
      - *(string) --* 

      
  
    :type TargetGroupARNs: list
    :param TargetGroupARNs: 

      The Amazon Resource Names (ARN) of the target groups.

      

    
      - *(string) --* 

      
  
    :type HealthCheckType: string
    :param HealthCheckType: 

      The service to use for the health checks. The valid values are ``EC2`` and ``ELB`` .

       

      By default, health checks use Amazon EC2 instance status checks to determine the health of an instance. For more information, see `Health Checks`_ in the *Auto Scaling User Guide* .

      

    
    :type HealthCheckGracePeriod: integer
    :param HealthCheckGracePeriod: 

      The amount of time, in seconds, that Auto Scaling waits before checking the health status of an EC2 instance that has come into service. During this time, any health check failures for the instance are ignored. The default is 0.

       

      This parameter is required if you are adding an ``ELB`` health check.

       

      For more information, see `Health Checks`_ in the *Auto Scaling User Guide* .

      

    
    :type PlacementGroup: string
    :param PlacementGroup: 

      The name of the placement group into which you'll launch your instances, if any. For more information, see `Placement Groups`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

    
    :type VPCZoneIdentifier: string
    :param VPCZoneIdentifier: 

      A comma-separated list of subnet identifiers for your virtual private cloud (VPC).

       

      If you specify subnets and Availability Zones with this call, ensure that the subnets' Availability Zones match the Availability Zones specified.

       

      For more information, see `Launching Auto Scaling Instances in a VPC`_ in the *Auto Scaling User Guide* .

      

    
    :type TerminationPolicies: list
    :param TerminationPolicies: 

      One or more termination policies used to select the instance to terminate. These policies are executed in the order that they are listed.

       

      For more information, see `Controlling Which Instances Auto Scaling Terminates During Scale In`_ in the *Auto Scaling User Guide* .

      

    
      - *(string) --* 

      
  
    :type NewInstancesProtectedFromScaleIn: boolean
    :param NewInstancesProtectedFromScaleIn: 

      Indicates whether newly launched instances are protected from termination by Auto Scaling when scaling in.

      

    
    :type Tags: list
    :param Tags: 

      One or more tags.

       

      For more information, see `Tagging Auto Scaling Groups and Instances`_ in the *Auto Scaling User Guide* .

      

    
      - *(dict) --* 

        Describes a tag for an Auto Scaling group.

        

      
        - **ResourceId** *(string) --* 

          The name of the group.

          

        
        - **ResourceType** *(string) --* 

          The type of resource. The only supported value is ``auto-scaling-group`` .

          

        
        - **Key** *(string) --* **[REQUIRED]** 

          The tag key.

          

        
        - **Value** *(string) --* 

          The tag value.

          

        
        - **PropagateAtLaunch** *(boolean) --* 

          Determines whether the tag is added to new instances as they are launched in the group.

          

        
      
  
    
    :returns: None

  .. py:method:: create_launch_configuration(**kwargs)

    

    Creates a launch configuration.

     

    If you exceed your maximum limit of launch configurations, which by default is 100 per region, the call fails. For information about viewing and updating this limit, see  DescribeAccountLimits .

     

    For more information, see `Launch Configurations`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_launch_configuration(
          LaunchConfigurationName='string',
          ImageId='string',
          KeyName='string',
          SecurityGroups=[
              'string',
          ],
          ClassicLinkVPCId='string',
          ClassicLinkVPCSecurityGroups=[
              'string',
          ],
          UserData='string',
          InstanceId='string',
          InstanceType='string',
          KernelId='string',
          RamdiskId='string',
          BlockDeviceMappings=[
              {
                  'VirtualName': 'string',
                  'DeviceName': 'string',
                  'Ebs': {
                      'SnapshotId': 'string',
                      'VolumeSize': 123,
                      'VolumeType': 'string',
                      'DeleteOnTermination': True|False,
                      'Iops': 123,
                      'Encrypted': True|False
                  },
                  'NoDevice': True|False
              },
          ],
          InstanceMonitoring={
              'Enabled': True|False
          },
          SpotPrice='string',
          IamInstanceProfile='string',
          EbsOptimized=True|False,
          AssociatePublicIpAddress=True|False,
          PlacementTenancy='string'
      )
    :type LaunchConfigurationName: string
    :param LaunchConfigurationName: **[REQUIRED]** 

      The name of the launch configuration. This name must be unique within the scope of your AWS account.

      

    
    :type ImageId: string
    :param ImageId: 

      The ID of the Amazon Machine Image (AMI) to use to launch your EC2 instances. For more information, see `Finding an AMI`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

    
    :type KeyName: string
    :param KeyName: 

      The name of the key pair. For more information, see `Amazon EC2 Key Pairs`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

    
    :type SecurityGroups: list
    :param SecurityGroups: 

      One or more security groups with which to associate the instances.

       

      If your instances are launched in EC2-Classic, you can either specify security group names or the security group IDs. For more information about security groups for EC2-Classic, see `Amazon EC2 Security Groups`_ in the *Amazon Elastic Compute Cloud User Guide* .

       

      If your instances are launched into a VPC, specify security group IDs. For more information, see `Security Groups for Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .

      

    
      - *(string) --* 

      
  
    :type ClassicLinkVPCId: string
    :param ClassicLinkVPCId: 

      The ID of a ClassicLink-enabled VPC to link your EC2-Classic instances to. This parameter is supported only if you are launching EC2-Classic instances. For more information, see `ClassicLink`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

    
    :type ClassicLinkVPCSecurityGroups: list
    :param ClassicLinkVPCSecurityGroups: 

      The IDs of one or more security groups for the specified ClassicLink-enabled VPC. This parameter is required if you specify a ClassicLink-enabled VPC, and is not supported otherwise. For more information, see `ClassicLink`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

    
      - *(string) --* 

      
  
    :type UserData: string
    :param UserData: 

      The user data to make available to the launched EC2 instances. For more information, see `Instance Metadata and User Data`_ in the *Amazon Elastic Compute Cloud User Guide* .

            **This value will be base64 encoded automatically. Do not base64 encode this value prior to performing the operation.**


    
    :type InstanceId: string
    :param InstanceId: 

      The ID of the instance to use to create the launch configuration.

       

      The new launch configuration derives attributes from the instance, with the exception of the block device mapping.

       

      To create a launch configuration with a block device mapping or override any other instance attributes, specify them as part of the same request.

       

      For more information, see `Create a Launch Configuration Using an EC2 Instance`_ in the *Auto Scaling User Guide* .

      

    
    :type InstanceType: string
    :param InstanceType: 

      The instance type of the EC2 instance. For information about available instance types, see `Available Instance Types`_ in the *Amazon Elastic Compute Cloud User Guide.*  

      

    
    :type KernelId: string
    :param KernelId: 

      The ID of the kernel associated with the AMI.

      

    
    :type RamdiskId: string
    :param RamdiskId: 

      The ID of the RAM disk associated with the AMI.

      

    
    :type BlockDeviceMappings: list
    :param BlockDeviceMappings: 

      One or more mappings that specify how block devices are exposed to the instance. For more information, see `Block Device Mapping`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

    
      - *(dict) --* 

        Describes a block device mapping.

        

      
        - **VirtualName** *(string) --* 

          The name of the virtual device (for example, ``ephemeral0`` ).

          

        
        - **DeviceName** *(string) --* **[REQUIRED]** 

          The device name exposed to the EC2 instance (for example, ``/dev/sdh`` or ``xvdh`` ).

          

        
        - **Ebs** *(dict) --* 

          The information about the Amazon EBS volume.

          

        
          - **SnapshotId** *(string) --* 

            The ID of the snapshot.

            

          
          - **VolumeSize** *(integer) --* 

            The volume size, in GiB. For ``standard`` volumes, specify a value from 1 to 1,024. For ``io1`` volumes, specify a value from 4 to 16,384. For ``gp2`` volumes, specify a value from 1 to 16,384. If you specify a snapshot, the volume size must be equal to or larger than the snapshot size.

             

            Default: If you create a volume from a snapshot and you don't specify a volume size, the default is the snapshot size.

            

          
          - **VolumeType** *(string) --* 

            The volume type. For more information, see `Amazon EBS Volume Types`_ in the *Amazon Elastic Compute Cloud User Guide* .

             

            Valid values: ``standard`` | ``io1`` | ``gp2``  

             

            Default: ``standard``  

            

          
          - **DeleteOnTermination** *(boolean) --* 

            Indicates whether the volume is deleted on instance termination.

             

            Default: ``true``  

            

          
          - **Iops** *(integer) --* 

            The number of I/O operations per second (IOPS) to provision for the volume.

             

            Constraint: Required when the volume type is ``io1`` .

            

          
          - **Encrypted** *(boolean) --* 

            Indicates whether the volume should be encrypted. Encrypted EBS volumes must be attached to instances that support Amazon EBS encryption. Volumes that are created from encrypted snapshots are automatically encrypted. There is no way to create an encrypted volume from an unencrypted snapshot or an unencrypted volume from an encrypted snapshot. For more information, see `Amazon EBS Encryption`_ in the *Amazon Elastic Compute Cloud User Guide* .

            

          
        
        - **NoDevice** *(boolean) --* 

          Suppresses a device mapping.

           

          If this parameter is true for the root device, the instance might fail the EC2 health check. Auto Scaling launches a replacement instance if the instance fails the health check.

          

        
      
  
    :type InstanceMonitoring: dict
    :param InstanceMonitoring: 

      Enables detailed monitoring (``true`` ) or basic monitoring (``false`` ) for the Auto Scaling instances.

      

    
      - **Enabled** *(boolean) --* 

        If ``True`` , instance monitoring is enabled.

        

      
    
    :type SpotPrice: string
    :param SpotPrice: 

      The maximum hourly price to be paid for any Spot Instance launched to fulfill the request. Spot Instances are launched when the price you specify exceeds the current Spot market price. For more information, see `Launching Spot Instances in Your Auto Scaling Group`_ in the *Auto Scaling User Guide* .

      

    
    :type IamInstanceProfile: string
    :param IamInstanceProfile: 

      The name or the Amazon Resource Name (ARN) of the instance profile associated with the IAM role for the instance.

       

      EC2 instances launched with an IAM role will automatically have AWS security credentials available. You can use IAM roles with Auto Scaling to automatically enable applications running on your EC2 instances to securely access other AWS resources. For more information, see `Launch Auto Scaling Instances with an IAM Role`_ in the *Auto Scaling User Guide* .

      

    
    :type EbsOptimized: boolean
    :param EbsOptimized: 

      Indicates whether the instance is optimized for Amazon EBS I/O. By default, the instance is not optimized for EBS I/O. The optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal I/O performance. This optimization is not available with all instance types. Additional usage charges apply. For more information, see `Amazon EBS-Optimized Instances`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

    
    :type AssociatePublicIpAddress: boolean
    :param AssociatePublicIpAddress: 

      Used for groups that launch instances into a virtual private cloud (VPC). Specifies whether to assign a public IP address to each instance. For more information, see `Launching Auto Scaling Instances in a VPC`_ in the *Auto Scaling User Guide* .

       

      If you specify this parameter, be sure to specify at least one subnet when you create your group.

       

      Default: If the instance is launched into a default subnet, the default is ``true`` . If the instance is launched into a nondefault subnet, the default is ``false`` . For more information, see `Supported Platforms`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

    
    :type PlacementTenancy: string
    :param PlacementTenancy: 

      The tenancy of the instance. An instance with a tenancy of ``dedicated`` runs on single-tenant hardware and can only be launched into a VPC.

       

      You must set the value of this parameter to ``dedicated`` if want to launch Dedicated Instances into a shared tenancy VPC (VPC with instance placement tenancy attribute set to ``default`` ).

       

      If you specify this parameter, be sure to specify at least one subnet when you create your group.

       

      For more information, see `Launching Auto Scaling Instances in a VPC`_ in the *Auto Scaling User Guide* .

       

      Valid values: ``default`` | ``dedicated``  

      

    
    
    :returns: None

  .. py:method:: create_or_update_tags(**kwargs)

    

    Creates or updates tags for the specified Auto Scaling group.

     

    When you specify a tag with a key that already exists, the operation overwrites the previous tag definition, and you do not get an error message.

     

    For more information, see `Tagging Auto Scaling Groups and Instances`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_or_update_tags(
          Tags=[
              {
                  'ResourceId': 'string',
                  'ResourceType': 'string',
                  'Key': 'string',
                  'Value': 'string',
                  'PropagateAtLaunch': True|False
              },
          ]
      )
    :type Tags: list
    :param Tags: **[REQUIRED]** 

      One or more tags.

      

    
      - *(dict) --* 

        Describes a tag for an Auto Scaling group.

        

      
        - **ResourceId** *(string) --* 

          The name of the group.

          

        
        - **ResourceType** *(string) --* 

          The type of resource. The only supported value is ``auto-scaling-group`` .

          

        
        - **Key** *(string) --* **[REQUIRED]** 

          The tag key.

          

        
        - **Value** *(string) --* 

          The tag value.

          

        
        - **PropagateAtLaunch** *(boolean) --* 

          Determines whether the tag is added to new instances as they are launched in the group.

          

        
      
  
    
    :returns: None

  .. py:method:: delete_auto_scaling_group(**kwargs)

    

    Deletes the specified Auto Scaling group.

     

    If the group has instances or scaling activities in progress, you must specify the option to force the deletion in order for it to succeed.

     

    If the group has policies, deleting the group deletes the policies, the underlying alarm actions, and any alarm that no longer has an associated action.

     

    To remove instances from the Auto Scaling group before deleting it, call  DetachInstances with the list of instances and the option to decrement the desired capacity so that Auto Scaling does not launch replacement instances.

     

    To terminate all instances before deleting the Auto Scaling group, call  UpdateAutoScalingGroup and set the minimum size and desired capacity of the Auto Scaling group to zero.

    

    **Request Syntax** 
    ::

      response = client.delete_auto_scaling_group(
          AutoScalingGroupName='string',
          ForceDelete=True|False
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the group to delete.

      

    
    :type ForceDelete: boolean
    :param ForceDelete: 

      Specifies that the group will be deleted along with all instances associated with the group, without waiting for all instances to be terminated. This parameter also deletes any lifecycle actions associated with the group.

      

    
    
    :returns: None

  .. py:method:: delete_launch_configuration(**kwargs)

    

    Deletes the specified launch configuration.

     

    The launch configuration must not be attached to an Auto Scaling group. When this call completes, the launch configuration is no longer available for use.

    

    **Request Syntax** 
    ::

      response = client.delete_launch_configuration(
          LaunchConfigurationName='string'
      )
    :type LaunchConfigurationName: string
    :param LaunchConfigurationName: **[REQUIRED]** 

      The name of the launch configuration.

      

    
    
    :returns: None

  .. py:method:: delete_lifecycle_hook(**kwargs)

    

    Deletes the specified lifecycle hook.

     

    If there are any outstanding lifecycle actions, they are completed first (``ABANDON`` for launching instances, ``CONTINUE`` for terminating instances).

    

    **Request Syntax** 
    ::

      response = client.delete_lifecycle_hook(
          LifecycleHookName='string',
          AutoScalingGroupName='string'
      )
    :type LifecycleHookName: string
    :param LifecycleHookName: **[REQUIRED]** 

      The name of the lifecycle hook.

      

    
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group for the lifecycle hook.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DeleteLifecycleHook.

        
    

  .. py:method:: delete_notification_configuration(**kwargs)

    

    Deletes the specified notification.

    

    **Request Syntax** 
    ::

      response = client.delete_notification_configuration(
          AutoScalingGroupName='string',
          TopicARN='string'
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type TopicARN: string
    :param TopicARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) topic.

      

    
    
    :returns: None

  .. py:method:: delete_policy(**kwargs)

    

    Deletes the specified Auto Scaling policy.

     

    Deleting a policy deletes the underlying alarm action, but does not delete the alarm, even if it no longer has an associated action.

    

    **Request Syntax** 
    ::

      response = client.delete_policy(
          AutoScalingGroupName='string',
          PolicyName='string'
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: 

      The name of the Auto Scaling group.

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name or Amazon Resource Name (ARN) of the policy.

      

    
    
    :returns: None

  .. py:method:: delete_scheduled_action(**kwargs)

    

    Deletes the specified scheduled action.

    

    **Request Syntax** 
    ::

      response = client.delete_scheduled_action(
          AutoScalingGroupName='string',
          ScheduledActionName='string'
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type ScheduledActionName: string
    :param ScheduledActionName: **[REQUIRED]** 

      The name of the action to delete.

      

    
    
    :returns: None

  .. py:method:: delete_tags(**kwargs)

    

    Deletes the specified tags.

    

    **Request Syntax** 
    ::

      response = client.delete_tags(
          Tags=[
              {
                  'ResourceId': 'string',
                  'ResourceType': 'string',
                  'Key': 'string',
                  'Value': 'string',
                  'PropagateAtLaunch': True|False
              },
          ]
      )
    :type Tags: list
    :param Tags: **[REQUIRED]** 

      One or more tags.

      

    
      - *(dict) --* 

        Describes a tag for an Auto Scaling group.

        

      
        - **ResourceId** *(string) --* 

          The name of the group.

          

        
        - **ResourceType** *(string) --* 

          The type of resource. The only supported value is ``auto-scaling-group`` .

          

        
        - **Key** *(string) --* **[REQUIRED]** 

          The tag key.

          

        
        - **Value** *(string) --* 

          The tag value.

          

        
        - **PropagateAtLaunch** *(boolean) --* 

          Determines whether the tag is added to new instances as they are launched in the group.

          

        
      
  
    
    :returns: None

  .. py:method:: describe_account_limits()

    

    Describes the current Auto Scaling resource limits for your AWS account.

     

    For information about requesting an increase in these limits, see `AWS Service Limits`_ in the *Amazon Web Services General Reference* .

    

    **Request Syntax** 

    ::

      response = client.describe_account_limits()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MaxNumberOfAutoScalingGroups': 123,
            'MaxNumberOfLaunchConfigurations': 123,
            'NumberOfAutoScalingGroups': 123,
            'NumberOfLaunchConfigurations': 123
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the parameters for DescribeAccountLimits.

        
        

        - **MaxNumberOfAutoScalingGroups** *(integer) --* 

          The maximum number of groups allowed for your AWS account. The default limit is 20 per region.

          
        

        - **MaxNumberOfLaunchConfigurations** *(integer) --* 

          The maximum number of launch configurations allowed for your AWS account. The default limit is 100 per region.

          
        

        - **NumberOfAutoScalingGroups** *(integer) --* 

          The current number of groups for your AWS account.

          
        

        - **NumberOfLaunchConfigurations** *(integer) --* 

          The current number of launch configurations for your AWS account.

          
    

  .. py:method:: describe_adjustment_types()

    

    Describes the policy adjustment types for use with  PutScalingPolicy .

    

    **Request Syntax** 

    ::

      response = client.describe_adjustment_types()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AdjustmentTypes': [
                {
                    'AdjustmentType': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the parameters for DescribeAdjustmentTypes.

        
        

        - **AdjustmentTypes** *(list) --* 

          The policy adjustment types.

          
          

          - *(dict) --* 

            Describes a policy adjustment type.

             

            For more information, see `Dynamic Scaling`_ in the *Auto Scaling User Guide* .

            
            

            - **AdjustmentType** *(string) --* 

              The policy adjustment type. The valid values are ``ChangeInCapacity`` , ``ExactCapacity`` , and ``PercentChangeInCapacity`` .

              
        
      
    

  .. py:method:: describe_auto_scaling_groups(**kwargs)

    

    Describes one or more Auto Scaling groups.

    

    **Request Syntax** 
    ::

      response = client.describe_auto_scaling_groups(
          AutoScalingGroupNames=[
              'string',
          ],
          NextToken='string',
          MaxRecords=123
      )
    :type AutoScalingGroupNames: list
    :param AutoScalingGroupNames: 

      The group names. If you omit this parameter, all Auto Scaling groups are described.

      

    
      - *(string) --* 

      
  
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AutoScalingGroups': [
                {
                    'AutoScalingGroupName': 'string',
                    'AutoScalingGroupARN': 'string',
                    'LaunchConfigurationName': 'string',
                    'MinSize': 123,
                    'MaxSize': 123,
                    'DesiredCapacity': 123,
                    'DefaultCooldown': 123,
                    'AvailabilityZones': [
                        'string',
                    ],
                    'LoadBalancerNames': [
                        'string',
                    ],
                    'TargetGroupARNs': [
                        'string',
                    ],
                    'HealthCheckType': 'string',
                    'HealthCheckGracePeriod': 123,
                    'Instances': [
                        {
                            'InstanceId': 'string',
                            'AvailabilityZone': 'string',
                            'LifecycleState': 'Pending'|'Pending:Wait'|'Pending:Proceed'|'Quarantined'|'InService'|'Terminating'|'Terminating:Wait'|'Terminating:Proceed'|'Terminated'|'Detaching'|'Detached'|'EnteringStandby'|'Standby',
                            'HealthStatus': 'string',
                            'LaunchConfigurationName': 'string',
                            'ProtectedFromScaleIn': True|False
                        },
                    ],
                    'CreatedTime': datetime(2015, 1, 1),
                    'SuspendedProcesses': [
                        {
                            'ProcessName': 'string',
                            'SuspensionReason': 'string'
                        },
                    ],
                    'PlacementGroup': 'string',
                    'VPCZoneIdentifier': 'string',
                    'EnabledMetrics': [
                        {
                            'Metric': 'string',
                            'Granularity': 'string'
                        },
                    ],
                    'Status': 'string',
                    'Tags': [
                        {
                            'ResourceId': 'string',
                            'ResourceType': 'string',
                            'Key': 'string',
                            'Value': 'string',
                            'PropagateAtLaunch': True|False
                        },
                    ],
                    'TerminationPolicies': [
                        'string',
                    ],
                    'NewInstancesProtectedFromScaleIn': True|False
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output for DescribeAutoScalingGroups.

        
        

        - **AutoScalingGroups** *(list) --* 

          The groups.

          
          

          - *(dict) --* 

            Describes an Auto Scaling group.

            
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the group.

              
            

            - **AutoScalingGroupARN** *(string) --* 

              The Amazon Resource Name (ARN) of the group.

              
            

            - **LaunchConfigurationName** *(string) --* 

              The name of the associated launch configuration.

              
            

            - **MinSize** *(integer) --* 

              The minimum size of the group.

              
            

            - **MaxSize** *(integer) --* 

              The maximum size of the group.

              
            

            - **DesiredCapacity** *(integer) --* 

              The desired size of the group.

              
            

            - **DefaultCooldown** *(integer) --* 

              The amount of time, in seconds, after a scaling activity completes before another scaling activity can start.

              
            

            - **AvailabilityZones** *(list) --* 

              One or more Availability Zones for the group.

              
              

              - *(string) --* 
          
            

            - **LoadBalancerNames** *(list) --* 

              One or more load balancers associated with the group.

              
              

              - *(string) --* 
          
            

            - **TargetGroupARNs** *(list) --* 

              The Amazon Resource Names (ARN) of the target groups for your load balancer.

              
              

              - *(string) --* 
          
            

            - **HealthCheckType** *(string) --* 

              The service to use for the health checks. The valid values are ``EC2`` and ``ELB`` .

              
            

            - **HealthCheckGracePeriod** *(integer) --* 

              The amount of time, in seconds, that Auto Scaling waits before checking the health status of an EC2 instance that has come into service.

              
            

            - **Instances** *(list) --* 

              The EC2 instances associated with the group.

              
              

              - *(dict) --* 

                Describes an EC2 instance.

                
                

                - **InstanceId** *(string) --* 

                  The ID of the instance.

                  
                

                - **AvailabilityZone** *(string) --* 

                  The Availability Zone in which the instance is running.

                  
                

                - **LifecycleState** *(string) --* 

                  A description of the current lifecycle state. Note that the ``Quarantined`` state is not used.

                  
                

                - **HealthStatus** *(string) --* 

                  The last reported health status of the instance. "Healthy" means that the instance is healthy and should remain in service. "Unhealthy" means that the instance is unhealthy and Auto Scaling should terminate and replace it.

                  
                

                - **LaunchConfigurationName** *(string) --* 

                  The launch configuration associated with the instance.

                  
                

                - **ProtectedFromScaleIn** *(boolean) --* 

                  Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

                  
            
          
            

            - **CreatedTime** *(datetime) --* 

              The date and time the group was created.

              
            

            - **SuspendedProcesses** *(list) --* 

              The suspended processes associated with the group.

              
              

              - *(dict) --* 

                Describes an Auto Scaling process that has been suspended. For more information, see  ProcessType .

                
                

                - **ProcessName** *(string) --* 

                  The name of the suspended process.

                  
                

                - **SuspensionReason** *(string) --* 

                  The reason that the process was suspended.

                  
            
          
            

            - **PlacementGroup** *(string) --* 

              The name of the placement group into which you'll launch your instances, if any. For more information, see `Placement Groups`_ in the *Amazon Elastic Compute Cloud User Guide* .

              
            

            - **VPCZoneIdentifier** *(string) --* 

              One or more subnet IDs, if applicable, separated by commas.

               

              If you specify ``VPCZoneIdentifier`` and ``AvailabilityZones`` , ensure that the Availability Zones of the subnets match the values for ``AvailabilityZones`` .

              
            

            - **EnabledMetrics** *(list) --* 

              The metrics enabled for the group.

              
              

              - *(dict) --* 

                Describes an enabled metric.

                
                

                - **Metric** *(string) --* 

                  One of the following metrics:

                   

                   
                  * ``GroupMinSize``   
                   
                  * ``GroupMaxSize``   
                   
                  * ``GroupDesiredCapacity``   
                   
                  * ``GroupInServiceInstances``   
                   
                  * ``GroupPendingInstances``   
                   
                  * ``GroupStandbyInstances``   
                   
                  * ``GroupTerminatingInstances``   
                   
                  * ``GroupTotalInstances``   
                   

                  
                

                - **Granularity** *(string) --* 

                  The granularity of the metric. The only valid value is ``1Minute`` .

                  
            
          
            

            - **Status** *(string) --* 

              The current state of the group when  DeleteAutoScalingGroup is in progress.

              
            

            - **Tags** *(list) --* 

              The tags for the group.

              
              

              - *(dict) --* 

                Describes a tag for an Auto Scaling group.

                
                

                - **ResourceId** *(string) --* 

                  The name of the group.

                  
                

                - **ResourceType** *(string) --* 

                  The type of resource. The only supported value is ``auto-scaling-group`` .

                  
                

                - **Key** *(string) --* 

                  The tag key.

                  
                

                - **Value** *(string) --* 

                  The tag value.

                  
                

                - **PropagateAtLaunch** *(boolean) --* 

                  Determines whether the tag is added to new instances as they are launched in the group.

                  
            
          
            

            - **TerminationPolicies** *(list) --* 

              The termination policies for the group.

              
              

              - *(string) --* 
          
            

            - **NewInstancesProtectedFromScaleIn** *(boolean) --* 

              Indicates whether newly launched instances are protected from termination by Auto Scaling when scaling in.

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_auto_scaling_instances(**kwargs)

    

    Describes one or more Auto Scaling instances.

    

    **Request Syntax** 
    ::

      response = client.describe_auto_scaling_instances(
          InstanceIds=[
              'string',
          ],
          MaxRecords=123,
          NextToken='string'
      )
    :type InstanceIds: list
    :param InstanceIds: 

      The instances to describe; up to 50 instance IDs. If you omit this parameter, all Auto Scaling instances are described. If you specify an ID that does not exist, it is ignored with no error.

      

    
      - *(string) --* 

      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to return with this call.

      

    
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AutoScalingInstances': [
                {
                    'InstanceId': 'string',
                    'AutoScalingGroupName': 'string',
                    'AvailabilityZone': 'string',
                    'LifecycleState': 'string',
                    'HealthStatus': 'string',
                    'LaunchConfigurationName': 'string',
                    'ProtectedFromScaleIn': True|False
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeAutoScalingInstances.

        
        

        - **AutoScalingInstances** *(list) --* 

          The instances.

          
          

          - *(dict) --* 

            Describes an EC2 instance associated with an Auto Scaling group.

            
            

            - **InstanceId** *(string) --* 

              The ID of the instance.

              
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group associated with the instance.

              
            

            - **AvailabilityZone** *(string) --* 

              The Availability Zone for the instance.

              
            

            - **LifecycleState** *(string) --* 

              The lifecycle state for the instance. For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling User Guide* .

              
            

            - **HealthStatus** *(string) --* 

              The last reported health status of this instance. "Healthy" means that the instance is healthy and should remain in service. "Unhealthy" means that the instance is unhealthy and Auto Scaling should terminate and replace it.

              
            

            - **LaunchConfigurationName** *(string) --* 

              The launch configuration associated with the instance.

              
            

            - **ProtectedFromScaleIn** *(boolean) --* 

              Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_auto_scaling_notification_types()

    

    Describes the notification types that are supported by Auto Scaling.

    

    **Request Syntax** 

    ::

      response = client.describe_auto_scaling_notification_types()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AutoScalingNotificationTypes': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeAutoScalingNotificationTypes.

        
        

        - **AutoScalingNotificationTypes** *(list) --* 

          The notification types.

          
          

          - *(string) --* 
      
    

  .. py:method:: describe_launch_configurations(**kwargs)

    

    Describes one or more launch configurations.

    

    **Request Syntax** 
    ::

      response = client.describe_launch_configurations(
          LaunchConfigurationNames=[
              'string',
          ],
          NextToken='string',
          MaxRecords=123
      )
    :type LaunchConfigurationNames: list
    :param LaunchConfigurationNames: 

      The launch configuration names. If you omit this parameter, all launch configurations are described.

      

    
      - *(string) --* 

      
  
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to return with this call. The default is 100.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LaunchConfigurations': [
                {
                    'LaunchConfigurationName': 'string',
                    'LaunchConfigurationARN': 'string',
                    'ImageId': 'string',
                    'KeyName': 'string',
                    'SecurityGroups': [
                        'string',
                    ],
                    'ClassicLinkVPCId': 'string',
                    'ClassicLinkVPCSecurityGroups': [
                        'string',
                    ],
                    'UserData': 'string',
                    'InstanceType': 'string',
                    'KernelId': 'string',
                    'RamdiskId': 'string',
                    'BlockDeviceMappings': [
                        {
                            'VirtualName': 'string',
                            'DeviceName': 'string',
                            'Ebs': {
                                'SnapshotId': 'string',
                                'VolumeSize': 123,
                                'VolumeType': 'string',
                                'DeleteOnTermination': True|False,
                                'Iops': 123,
                                'Encrypted': True|False
                            },
                            'NoDevice': True|False
                        },
                    ],
                    'InstanceMonitoring': {
                        'Enabled': True|False
                    },
                    'SpotPrice': 'string',
                    'IamInstanceProfile': 'string',
                    'CreatedTime': datetime(2015, 1, 1),
                    'EbsOptimized': True|False,
                    'AssociatePublicIpAddress': True|False,
                    'PlacementTenancy': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeLaunchConfigurations.

        
        

        - **LaunchConfigurations** *(list) --* 

          The launch configurations.

          
          

          - *(dict) --* 

            Describes a launch configuration.

            
            

            - **LaunchConfigurationName** *(string) --* 

              The name of the launch configuration.

              
            

            - **LaunchConfigurationARN** *(string) --* 

              The Amazon Resource Name (ARN) of the launch configuration.

              
            

            - **ImageId** *(string) --* 

              The ID of the Amazon Machine Image (AMI).

              
            

            - **KeyName** *(string) --* 

              The name of the key pair.

              
            

            - **SecurityGroups** *(list) --* 

              The security groups to associate with the instances.

              
              

              - *(string) --* 
          
            

            - **ClassicLinkVPCId** *(string) --* 

              The ID of a ClassicLink-enabled VPC to link your EC2-Classic instances to. This parameter can only be used if you are launching EC2-Classic instances. For more information, see `ClassicLink`_ in the *Amazon Elastic Compute Cloud User Guide* .

              
            

            - **ClassicLinkVPCSecurityGroups** *(list) --* 

              The IDs of one or more security groups for the VPC specified in ``ClassicLinkVPCId`` . This parameter is required if you specify a ClassicLink-enabled VPC, and cannot be used otherwise. For more information, see `ClassicLink`_ in the *Amazon Elastic Compute Cloud User Guide* .

              
              

              - *(string) --* 
          
            

            - **UserData** *(string) --* 

              The user data available to the instances.

              
            

            - **InstanceType** *(string) --* 

              The instance type for the instances.

              
            

            - **KernelId** *(string) --* 

              The ID of the kernel associated with the AMI.

              
            

            - **RamdiskId** *(string) --* 

              The ID of the RAM disk associated with the AMI.

              
            

            - **BlockDeviceMappings** *(list) --* 

              A block device mapping, which specifies the block devices for the instance.

              
              

              - *(dict) --* 

                Describes a block device mapping.

                
                

                - **VirtualName** *(string) --* 

                  The name of the virtual device (for example, ``ephemeral0`` ).

                  
                

                - **DeviceName** *(string) --* 

                  The device name exposed to the EC2 instance (for example, ``/dev/sdh`` or ``xvdh`` ).

                  
                

                - **Ebs** *(dict) --* 

                  The information about the Amazon EBS volume.

                  
                  

                  - **SnapshotId** *(string) --* 

                    The ID of the snapshot.

                    
                  

                  - **VolumeSize** *(integer) --* 

                    The volume size, in GiB. For ``standard`` volumes, specify a value from 1 to 1,024. For ``io1`` volumes, specify a value from 4 to 16,384. For ``gp2`` volumes, specify a value from 1 to 16,384. If you specify a snapshot, the volume size must be equal to or larger than the snapshot size.

                     

                    Default: If you create a volume from a snapshot and you don't specify a volume size, the default is the snapshot size.

                    
                  

                  - **VolumeType** *(string) --* 

                    The volume type. For more information, see `Amazon EBS Volume Types`_ in the *Amazon Elastic Compute Cloud User Guide* .

                     

                    Valid values: ``standard`` | ``io1`` | ``gp2``  

                     

                    Default: ``standard``  

                    
                  

                  - **DeleteOnTermination** *(boolean) --* 

                    Indicates whether the volume is deleted on instance termination.

                     

                    Default: ``true``  

                    
                  

                  - **Iops** *(integer) --* 

                    The number of I/O operations per second (IOPS) to provision for the volume.

                     

                    Constraint: Required when the volume type is ``io1`` .

                    
                  

                  - **Encrypted** *(boolean) --* 

                    Indicates whether the volume should be encrypted. Encrypted EBS volumes must be attached to instances that support Amazon EBS encryption. Volumes that are created from encrypted snapshots are automatically encrypted. There is no way to create an encrypted volume from an unencrypted snapshot or an unencrypted volume from an encrypted snapshot. For more information, see `Amazon EBS Encryption`_ in the *Amazon Elastic Compute Cloud User Guide* .

                    
              
                

                - **NoDevice** *(boolean) --* 

                  Suppresses a device mapping.

                   

                  If this parameter is true for the root device, the instance might fail the EC2 health check. Auto Scaling launches a replacement instance if the instance fails the health check.

                  
            
          
            

            - **InstanceMonitoring** *(dict) --* 

              Controls whether instances in this group are launched with detailed (``true`` ) or basic (``false`` ) monitoring.

              
              

              - **Enabled** *(boolean) --* 

                If ``True`` , instance monitoring is enabled.

                
          
            

            - **SpotPrice** *(string) --* 

              The price to bid when launching Spot Instances.

              
            

            - **IamInstanceProfile** *(string) --* 

              The name or Amazon Resource Name (ARN) of the instance profile associated with the IAM role for the instance.

              
            

            - **CreatedTime** *(datetime) --* 

              The creation date and time for the launch configuration.

              
            

            - **EbsOptimized** *(boolean) --* 

              Controls whether the instance is optimized for EBS I/O (``true`` ) or not (``false`` ).

              
            

            - **AssociatePublicIpAddress** *(boolean) --* 

              [EC2-VPC] Indicates whether to assign a public IP address to each instance.

              
            

            - **PlacementTenancy** *(string) --* 

              The tenancy of the instance, either ``default`` or ``dedicated`` . An instance with ``dedicated`` tenancy runs in an isolated, single-tenant hardware and can only be launched into a VPC.

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_lifecycle_hook_types()

    

    Describes the available types of lifecycle hooks.

    

    **Request Syntax** 

    ::

      response = client.describe_lifecycle_hook_types()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LifecycleHookTypes': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeLifecycleHookTypes.

        
        

        - **LifecycleHookTypes** *(list) --* 

          The lifecycle hook types.

          
          

          - *(string) --* 
      
    

  .. py:method:: describe_lifecycle_hooks(**kwargs)

    

    Describes the lifecycle hooks for the specified Auto Scaling group.

    

    **Request Syntax** 
    ::

      response = client.describe_lifecycle_hooks(
          AutoScalingGroupName='string',
          LifecycleHookNames=[
              'string',
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the group.

      

    
    :type LifecycleHookNames: list
    :param LifecycleHookNames: 

      The names of one or more lifecycle hooks. If you omit this parameter, all lifecycle hooks are described.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LifecycleHooks': [
                {
                    'LifecycleHookName': 'string',
                    'AutoScalingGroupName': 'string',
                    'LifecycleTransition': 'string',
                    'NotificationTargetARN': 'string',
                    'RoleARN': 'string',
                    'NotificationMetadata': 'string',
                    'HeartbeatTimeout': 123,
                    'GlobalTimeout': 123,
                    'DefaultResult': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeLifecycleHooks.

        
        

        - **LifecycleHooks** *(list) --* 

          The lifecycle hooks for the specified group.

          
          

          - *(dict) --* 

            Describes a lifecycle hook, which tells Auto Scaling that you want to perform an action when an instance launches or terminates. When you have a lifecycle hook in place, the Auto Scaling group will either:

             

             
            * Pause the instance after it launches, but before it is put into service 
             
            * Pause the instance as it terminates, but before it is fully terminated 
             

             

            For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling User Guide* .

            
            

            - **LifecycleHookName** *(string) --* 

              The name of the lifecycle hook.

              
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group for the lifecycle hook.

              
            

            - **LifecycleTransition** *(string) --* 

              The state of the EC2 instance to which you want to attach the lifecycle hook. For a list of lifecycle hook types, see  DescribeLifecycleHookTypes .

              
            

            - **NotificationTargetARN** *(string) --* 

              The ARN of the notification target that Auto Scaling uses to notify you when an instance is in the transition state for the lifecycle hook. This ARN target can be either an SQS queue or an SNS topic. The notification message sent to the target includes the following:

               

               
              * Lifecycle action token 
               
              * User account ID 
               
              * Name of the Auto Scaling group 
               
              * Lifecycle hook name 
               
              * EC2 instance ID 
               
              * Lifecycle transition 
               
              * Notification metadata 
               

              
            

            - **RoleARN** *(string) --* 

              The ARN of the IAM role that allows the Auto Scaling group to publish to the specified notification target.

              
            

            - **NotificationMetadata** *(string) --* 

              Additional information that you want to include any time Auto Scaling sends a message to the notification target.

              
            

            - **HeartbeatTimeout** *(integer) --* 

              The maximum time, in seconds, that can elapse before the lifecycle hook times out. The default is 3600 seconds (1 hour). When the lifecycle hook times out, Auto Scaling performs the default action. You can prevent the lifecycle hook from timing out by calling  RecordLifecycleActionHeartbeat .

              
            

            - **GlobalTimeout** *(integer) --* 

              The maximum time, in seconds, that an instance can remain in a ``Pending:Wait`` or ``Terminating:Wait`` state. The default is 172800 seconds (48 hours).

              
            

            - **DefaultResult** *(string) --* 

              Defines the action the Auto Scaling group should take when the lifecycle hook timeout elapses or if an unexpected failure occurs. The valid values are ``CONTINUE`` and ``ABANDON`` . The default value is ``CONTINUE`` .

              
        
      
    

  .. py:method:: describe_load_balancer_target_groups(**kwargs)

    

    Describes the target groups for the specified Auto Scaling group.

    

    **Request Syntax** 
    ::

      response = client.describe_load_balancer_target_groups(
          AutoScalingGroupName='string',
          NextToken='string',
          MaxRecords=123
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LoadBalancerTargetGroups': [
                {
                    'LoadBalancerTargetGroupARN': 'string',
                    'State': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeLoadBalancerTargetGroups.

        
        

        - **LoadBalancerTargetGroups** *(list) --* 

          Information about the target groups.

          
          

          - *(dict) --* 

            Describes the state of a target group.

             

            If you attach a target group to an existing Auto Scaling group, the initial state is ``Adding`` . The state transitions to ``Added`` after all Auto Scaling instances are registered with the target group. If ELB health checks are enabled, the state transitions to ``InService`` after at least one Auto Scaling instance passes the health check. If EC2 health checks are enabled instead, the target group remains in the ``Added`` state.

            
            

            - **LoadBalancerTargetGroupARN** *(string) --* 

              The Amazon Resource Name (ARN) of the target group.

              
            

            - **State** *(string) --* 

              The state of the target group.

               

               
              * ``Adding`` - The Auto Scaling instances are being registered with the target group. 
               
              * ``Added`` - All Auto Scaling instances are registered with the target group. 
               
              * ``InService`` - At least one Auto Scaling instance passed an ELB health check. 
               
              * ``Removing`` - The Auto Scaling instances are being deregistered from the target group. If connection draining is enabled, Elastic Load Balancing waits for in-flight requests to complete before deregistering the instances. 
               
              * ``Removed`` - All Auto Scaling instances are deregistered from the target group. 
               

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_load_balancers(**kwargs)

    

    Describes the load balancers for the specified Auto Scaling group.

     

    Note that this operation describes only Classic load balancers. If you have Application load balancers, use  DescribeLoadBalancerTargetGroups instead.

    

    **Request Syntax** 
    ::

      response = client.describe_load_balancers(
          AutoScalingGroupName='string',
          NextToken='string',
          MaxRecords=123
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the group.

      

    
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LoadBalancers': [
                {
                    'LoadBalancerName': 'string',
                    'State': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeLoadBalancers.

        
        

        - **LoadBalancers** *(list) --* 

          The load balancers.

          
          

          - *(dict) --* 

            Describes the state of a Classic load balancer.

             

            If you specify a load balancer when creating the Auto Scaling group, the state of the load balancer is ``InService`` .

             

            If you attach a load balancer to an existing Auto Scaling group, the initial state is ``Adding`` . The state transitions to ``Added`` after all instances in the group are registered with the load balancer. If ELB health checks are enabled for the load balancer, the state transitions to ``InService`` after at least one instance in the group passes the health check. If EC2 health checks are enabled instead, the load balancer remains in the ``Added`` state.

            
            

            - **LoadBalancerName** *(string) --* 

              The name of the load balancer.

              
            

            - **State** *(string) --* 

              One of the following load balancer states:

               

               
              * ``Adding`` - The instances in the group are being registered with the load balancer. 
               
              * ``Added`` - All instances in the group are registered with the load balancer. 
               
              * ``InService`` - At least one instance in the group passed an ELB health check. 
               
              * ``Removing`` - The instances in the group are being deregistered from the load balancer. If connection draining is enabled, Elastic Load Balancing waits for in-flight requests to complete before deregistering the instances. 
               
              * ``Removed`` - All instances in the group are deregistered from the load balancer. 
               

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_metric_collection_types()

    

    Describes the available CloudWatch metrics for Auto Scaling.

     

    Note that the ``GroupStandbyInstances`` metric is not returned by default. You must explicitly request this metric when calling  EnableMetricsCollection .

    

    **Request Syntax** 

    ::

      response = client.describe_metric_collection_types()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Metrics': [
                {
                    'Metric': 'string'
                },
            ],
            'Granularities': [
                {
                    'Granularity': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeMetricsCollectionTypes.

        
        

        - **Metrics** *(list) --* 

          One or more metrics.

          
          

          - *(dict) --* 

            Describes a metric.

            
            

            - **Metric** *(string) --* 

              One of the following metrics:

               

               
              * ``GroupMinSize``   
               
              * ``GroupMaxSize``   
               
              * ``GroupDesiredCapacity``   
               
              * ``GroupInServiceInstances``   
               
              * ``GroupPendingInstances``   
               
              * ``GroupStandbyInstances``   
               
              * ``GroupTerminatingInstances``   
               
              * ``GroupTotalInstances``   
               

              
        
      
        

        - **Granularities** *(list) --* 

          The granularities for the metrics.

          
          

          - *(dict) --* 

            Describes a granularity of a metric.

            
            

            - **Granularity** *(string) --* 

              The granularity. The only valid value is ``1Minute`` .

              
        
      
    

  .. py:method:: describe_notification_configurations(**kwargs)

    

    Describes the notification actions associated with the specified Auto Scaling group.

    

    **Request Syntax** 
    ::

      response = client.describe_notification_configurations(
          AutoScalingGroupNames=[
              'string',
          ],
          NextToken='string',
          MaxRecords=123
      )
    :type AutoScalingGroupNames: list
    :param AutoScalingGroupNames: 

      The name of the group.

      

    
      - *(string) --* 

      
  
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NotificationConfigurations': [
                {
                    'AutoScalingGroupName': 'string',
                    'TopicARN': 'string',
                    'NotificationType': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output from DescribeNotificationConfigurations.

        
        

        - **NotificationConfigurations** *(list) --* 

          The notification configurations.

          
          

          - *(dict) --* 

            Describes a notification.

            
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the group.

              
            

            - **TopicARN** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) topic.

              
            

            - **NotificationType** *(string) --* 

              One of the following event notification types:

               

               
              * ``autoscaling:EC2_INSTANCE_LAUNCH``   
               
              * ``autoscaling:EC2_INSTANCE_LAUNCH_ERROR``   
               
              * ``autoscaling:EC2_INSTANCE_TERMINATE``   
               
              * ``autoscaling:EC2_INSTANCE_TERMINATE_ERROR``   
               
              * ``autoscaling:TEST_NOTIFICATION``   
               

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_policies(**kwargs)

    

    Describes the policies for the specified Auto Scaling group.

    

    **Request Syntax** 
    ::

      response = client.describe_policies(
          AutoScalingGroupName='string',
          PolicyNames=[
              'string',
          ],
          PolicyTypes=[
              'string',
          ],
          NextToken='string',
          MaxRecords=123
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: 

      The name of the group.

      

    
    :type PolicyNames: list
    :param PolicyNames: 

      One or more policy names or policy ARNs to be described. If you omit this parameter, all policy names are described. If an group name is provided, the results are limited to that group. This list is limited to 50 items. If you specify an unknown policy name, it is ignored with no error.

      

    
      - *(string) --* 

      
  
    :type PolicyTypes: list
    :param PolicyTypes: 

      One or more policy types. Valid values are ``SimpleScaling`` and ``StepScaling`` .

      

    
      - *(string) --* 

      
  
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to be returned with each call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ScalingPolicies': [
                {
                    'AutoScalingGroupName': 'string',
                    'PolicyName': 'string',
                    'PolicyARN': 'string',
                    'PolicyType': 'string',
                    'AdjustmentType': 'string',
                    'MinAdjustmentStep': 123,
                    'MinAdjustmentMagnitude': 123,
                    'ScalingAdjustment': 123,
                    'Cooldown': 123,
                    'StepAdjustments': [
                        {
                            'MetricIntervalLowerBound': 123.0,
                            'MetricIntervalUpperBound': 123.0,
                            'ScalingAdjustment': 123
                        },
                    ],
                    'MetricAggregationType': 'string',
                    'EstimatedInstanceWarmup': 123,
                    'Alarms': [
                        {
                            'AlarmName': 'string',
                            'AlarmARN': 'string'
                        },
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribePolicies.

        
        

        - **ScalingPolicies** *(list) --* 

          The scaling policies.

          
          

          - *(dict) --* 

            Describes a scaling policy.

            
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group associated with this scaling policy.

              
            

            - **PolicyName** *(string) --* 

              The name of the scaling policy.

              
            

            - **PolicyARN** *(string) --* 

              The Amazon Resource Name (ARN) of the policy.

              
            

            - **PolicyType** *(string) --* 

              The policy type. Valid values are ``SimpleScaling`` and ``StepScaling`` .

              
            

            - **AdjustmentType** *(string) --* 

              The adjustment type, which specifies how ``ScalingAdjustment`` is interpreted. Valid values are ``ChangeInCapacity`` , ``ExactCapacity`` , and ``PercentChangeInCapacity`` .

              
            

            - **MinAdjustmentStep** *(integer) --* 

              Available for backward compatibility. Use ``MinAdjustmentMagnitude`` instead.

              
            

            - **MinAdjustmentMagnitude** *(integer) --* 

              The minimum number of instances to scale. If the value of ``AdjustmentType`` is ``PercentChangeInCapacity`` , the scaling policy changes the ``DesiredCapacity`` of the Auto Scaling group by at least this many instances. Otherwise, the error is ``ValidationError`` .

              
            

            - **ScalingAdjustment** *(integer) --* 

              The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

              
            

            - **Cooldown** *(integer) --* 

              The amount of time, in seconds, after a scaling activity completes before any further trigger-related scaling activities can start.

              
            

            - **StepAdjustments** *(list) --* 

              A set of adjustments that enable you to scale based on the size of the alarm breach.

              
              

              - *(dict) --* 

                Describes an adjustment based on the difference between the value of the aggregated CloudWatch metric and the breach threshold that you've defined for the alarm.

                 

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

                  The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

                  
            
          
            

            - **MetricAggregationType** *(string) --* 

              The aggregation type for the CloudWatch metrics. Valid values are ``Minimum`` , ``Maximum`` , and ``Average`` .

              
            

            - **EstimatedInstanceWarmup** *(integer) --* 

              The estimated time, in seconds, until a newly launched instance can contribute to the CloudWatch metrics.

              
            

            - **Alarms** *(list) --* 

              The CloudWatch alarms related to the policy.

              
              

              - *(dict) --* 

                Describes an alarm.

                
                

                - **AlarmName** *(string) --* 

                  The name of the alarm.

                  
                

                - **AlarmARN** *(string) --* 

                  The Amazon Resource Name (ARN) of the alarm.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_scaling_activities(**kwargs)

    

    Describes one or more scaling activities for the specified Auto Scaling group.

    

    **Request Syntax** 
    ::

      response = client.describe_scaling_activities(
          ActivityIds=[
              'string',
          ],
          AutoScalingGroupName='string',
          MaxRecords=123,
          NextToken='string'
      )
    :type ActivityIds: list
    :param ActivityIds: 

      The activity IDs of the desired scaling activities. If you omit this parameter, all activities for the past six weeks are described. If you specify an Auto Scaling group, the results are limited to that group. The list of requested activities cannot contain more than 50 items. If unknown activities are requested, they are ignored with no error.

      

    
      - *(string) --* 

      
  
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: 

      The name of the group.

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to return with this call.

      

    
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Activities': [
                {
                    'ActivityId': 'string',
                    'AutoScalingGroupName': 'string',
                    'Description': 'string',
                    'Cause': 'string',
                    'StartTime': datetime(2015, 1, 1),
                    'EndTime': datetime(2015, 1, 1),
                    'StatusCode': 'PendingSpotBidPlacement'|'WaitingForSpotInstanceRequestId'|'WaitingForSpotInstanceId'|'WaitingForInstanceId'|'PreInService'|'InProgress'|'WaitingForELBConnectionDraining'|'MidLifecycleAction'|'WaitingForInstanceWarmup'|'Successful'|'Failed'|'Cancelled',
                    'StatusMessage': 'string',
                    'Progress': 123,
                    'Details': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeScalingActivities.

        
        

        - **Activities** *(list) --* 

          The scaling activities. Activities are sorted by start time. Activities still in progress are described first.

          
          

          - *(dict) --* 

            Describes scaling activity, which is a long-running process that represents a change to your Auto Scaling group, such as changing its size or replacing an instance.

            
            

            - **ActivityId** *(string) --* 

              The ID of the activity.

              
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group.

              
            

            - **Description** *(string) --* 

              A friendly, more verbose description of the activity.

              
            

            - **Cause** *(string) --* 

              The reason the activity began.

              
            

            - **StartTime** *(datetime) --* 

              The start time of the activity.

              
            

            - **EndTime** *(datetime) --* 

              The end time of the activity.

              
            

            - **StatusCode** *(string) --* 

              The current status of the activity.

              
            

            - **StatusMessage** *(string) --* 

              A friendly, more verbose description of the activity status.

              
            

            - **Progress** *(integer) --* 

              A value between 0 and 100 that indicates the progress of the activity.

              
            

            - **Details** *(string) --* 

              The details about the activity.

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_scaling_process_types()

    

    Describes the scaling process types for use with  ResumeProcesses and  SuspendProcesses .

    

    **Request Syntax** 

    ::

      response = client.describe_scaling_process_types()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Processes': [
                {
                    'ProcessName': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeScalingProcessTypes.

        
        

        - **Processes** *(list) --* 

          The names of the process types.

          
          

          - *(dict) --* 

            Describes a process type.

             

            For more information, see `Auto Scaling Processes`_ in the *Auto Scaling User Guide* .

            
            

            - **ProcessName** *(string) --* 

              One of the following processes:

               

               
              * ``Launch``   
               
              * ``Terminate``   
               
              * ``AddToLoadBalancer``   
               
              * ``AlarmNotification``   
               
              * ``AZRebalance``   
               
              * ``HealthCheck``   
               
              * ``ReplaceUnhealthy``   
               
              * ``ScheduledActions``   
               

              
        
      
    

  .. py:method:: describe_scheduled_actions(**kwargs)

    

    Describes the actions scheduled for your Auto Scaling group that haven't run. To describe the actions that have already run, use  DescribeScalingActivities .

    

    **Request Syntax** 
    ::

      response = client.describe_scheduled_actions(
          AutoScalingGroupName='string',
          ScheduledActionNames=[
              'string',
          ],
          StartTime=datetime(2015, 1, 1),
          EndTime=datetime(2015, 1, 1),
          NextToken='string',
          MaxRecords=123
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: 

      The name of the group.

      

    
    :type ScheduledActionNames: list
    :param ScheduledActionNames: 

      Describes one or more scheduled actions. If you omit this parameter, all scheduled actions are described. If you specify an unknown scheduled action, it is ignored with no error.

       

      You can describe up to a maximum of 50 instances with a single call. If there are more items to return, the call returns a token. To get the next set of items, repeat the call with the returned token.

      

    
      - *(string) --* 

      
  
    :type StartTime: datetime
    :param StartTime: 

      The earliest scheduled start time to return. If scheduled action names are provided, this parameter is ignored.

      

    
    :type EndTime: datetime
    :param EndTime: 

      The latest scheduled start time to return. If scheduled action names are provided, this parameter is ignored.

      

    
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ScheduledUpdateGroupActions': [
                {
                    'AutoScalingGroupName': 'string',
                    'ScheduledActionName': 'string',
                    'ScheduledActionARN': 'string',
                    'Time': datetime(2015, 1, 1),
                    'StartTime': datetime(2015, 1, 1),
                    'EndTime': datetime(2015, 1, 1),
                    'Recurrence': 'string',
                    'MinSize': 123,
                    'MaxSize': 123,
                    'DesiredCapacity': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeScheduledActions.

        
        

        - **ScheduledUpdateGroupActions** *(list) --* 

          The scheduled actions.

          
          

          - *(dict) --* 

            Describes a scheduled update to an Auto Scaling group.

            
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the group.

              
            

            - **ScheduledActionName** *(string) --* 

              The name of the scheduled action.

              
            

            - **ScheduledActionARN** *(string) --* 

              The Amazon Resource Name (ARN) of the scheduled action.

              
            

            - **Time** *(datetime) --* 

              This parameter is deprecated.

              
            

            - **StartTime** *(datetime) --* 

              The date and time that the action is scheduled to begin. This date and time can be up to one month in the future.

               

              When ``StartTime`` and ``EndTime`` are specified with ``Recurrence`` , they form the boundaries of when the recurring action will start and stop.

              
            

            - **EndTime** *(datetime) --* 

              The date and time that the action is scheduled to end. This date and time can be up to one month in the future.

              
            

            - **Recurrence** *(string) --* 

              The recurring schedule for the action.

              
            

            - **MinSize** *(integer) --* 

              The minimum size of the group.

              
            

            - **MaxSize** *(integer) --* 

              The maximum size of the group.

              
            

            - **DesiredCapacity** *(integer) --* 

              The number of instances you prefer to maintain in the group.

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_tags(**kwargs)

    

    Describes the specified tags.

     

    You can use filters to limit the results. For example, you can query for the tags for a specific Auto Scaling group. You can specify multiple values for a filter. A tag must match at least one of the specified values for it to be included in the results.

     

    You can also specify multiple filters. The result includes information for a particular tag only if it matches all the filters. If there's no match, no special message is returned.

    

    **Request Syntax** 
    ::

      response = client.describe_tags(
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          NextToken='string',
          MaxRecords=123
      )
    :type Filters: list
    :param Filters: 

      A filter used to scope the tags to return.

      

    
      - *(dict) --* 

        Describes a filter.

        

      
        - **Name** *(string) --* 

          The name of the filter. The valid values are: ``"auto-scaling-group"`` , ``"key"`` , ``"value"`` , and ``"propagate-at-launch"`` .

          

        
        - **Values** *(list) --* 

          The value of the filter.

          

        
          - *(string) --* 

          
      
      
  
    :type NextToken: string
    :param NextToken: 

      The token for the next set of items to return. (You received this token from a previous call.)

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of items to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Tags': [
                {
                    'ResourceId': 'string',
                    'ResourceType': 'string',
                    'Key': 'string',
                    'Value': 'string',
                    'PropagateAtLaunch': True|False
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeTags.

        
        

        - **Tags** *(list) --* 

          One or more tags.

          
          

          - *(dict) --* 

            Describes a tag for an Auto Scaling group.

            
            

            - **ResourceId** *(string) --* 

              The name of the group.

              
            

            - **ResourceType** *(string) --* 

              The type of resource. The only supported value is ``auto-scaling-group`` .

              
            

            - **Key** *(string) --* 

              The tag key.

              
            

            - **Value** *(string) --* 

              The tag value.

              
            

            - **PropagateAtLaunch** *(boolean) --* 

              Determines whether the tag is added to new instances as they are launched in the group.

              
        
      
        

        - **NextToken** *(string) --* 

          The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

          
    

  .. py:method:: describe_termination_policy_types()

    

    Describes the termination policies supported by Auto Scaling.

    

    **Request Syntax** 

    ::

      response = client.describe_termination_policy_types()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TerminationPolicyTypes': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeTerminationPolicyTypes.

        
        

        - **TerminationPolicyTypes** *(list) --* 

          The termination policies supported by Auto Scaling (``OldestInstance`` , ``OldestLaunchConfiguration`` , ``NewestInstance`` , ``ClosestToNextInstanceHour`` , and ``Default`` ).

          
          

          - *(string) --* 
      
    

  .. py:method:: detach_instances(**kwargs)

    

    Removes one or more instances from the specified Auto Scaling group.

     

    After the instances are detached, you can manage them independently from the rest of the Auto Scaling group.

     

    If you do not specify the option to decrement the desired capacity, Auto Scaling launches instances to replace the ones that are detached.

     

    If there is a Classic load balancer attached to the Auto Scaling group, the instances are deregistered from the load balancer. If there are target groups attached to the Auto Scaling group, the instances are deregistered from the target groups.

     

    For more information, see `Detach EC2 Instances from Your Auto Scaling Group`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.detach_instances(
          InstanceIds=[
              'string',
          ],
          AutoScalingGroupName='string',
          ShouldDecrementDesiredCapacity=True|False
      )
    :type InstanceIds: list
    :param InstanceIds: 

      One or more instance IDs.

      

    
      - *(string) --* 

      
  
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the group.

      

    
    :type ShouldDecrementDesiredCapacity: boolean
    :param ShouldDecrementDesiredCapacity: **[REQUIRED]** 

      If ``True`` , the Auto Scaling group decrements the desired capacity value by the number of instances detached.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Activities': [
                {
                    'ActivityId': 'string',
                    'AutoScalingGroupName': 'string',
                    'Description': 'string',
                    'Cause': 'string',
                    'StartTime': datetime(2015, 1, 1),
                    'EndTime': datetime(2015, 1, 1),
                    'StatusCode': 'PendingSpotBidPlacement'|'WaitingForSpotInstanceRequestId'|'WaitingForSpotInstanceId'|'WaitingForInstanceId'|'PreInService'|'InProgress'|'WaitingForELBConnectionDraining'|'MidLifecycleAction'|'WaitingForInstanceWarmup'|'Successful'|'Failed'|'Cancelled',
                    'StatusMessage': 'string',
                    'Progress': 123,
                    'Details': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DetachInstances.

        
        

        - **Activities** *(list) --* 

          The activities related to detaching the instances from the Auto Scaling group.

          
          

          - *(dict) --* 

            Describes scaling activity, which is a long-running process that represents a change to your Auto Scaling group, such as changing its size or replacing an instance.

            
            

            - **ActivityId** *(string) --* 

              The ID of the activity.

              
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group.

              
            

            - **Description** *(string) --* 

              A friendly, more verbose description of the activity.

              
            

            - **Cause** *(string) --* 

              The reason the activity began.

              
            

            - **StartTime** *(datetime) --* 

              The start time of the activity.

              
            

            - **EndTime** *(datetime) --* 

              The end time of the activity.

              
            

            - **StatusCode** *(string) --* 

              The current status of the activity.

              
            

            - **StatusMessage** *(string) --* 

              A friendly, more verbose description of the activity status.

              
            

            - **Progress** *(integer) --* 

              A value between 0 and 100 that indicates the progress of the activity.

              
            

            - **Details** *(string) --* 

              The details about the activity.

              
        
      
    

  .. py:method:: detach_load_balancer_target_groups(**kwargs)

    

    Detaches one or more target groups from the specified Auto Scaling group.

    

    **Request Syntax** 
    ::

      response = client.detach_load_balancer_target_groups(
          AutoScalingGroupName='string',
          TargetGroupARNs=[
              'string',
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type TargetGroupARNs: list
    :param TargetGroupARNs: **[REQUIRED]** 

      The Amazon Resource Names (ARN) of the target groups.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: detach_load_balancers(**kwargs)

    

    Detaches one or more Classic load balancers from the specified Auto Scaling group.

     

    Note that this operation detaches only Classic load balancers. If you have Application load balancers, use  DetachLoadBalancerTargetGroups instead.

     

    When you detach a load balancer, it enters the ``Removing`` state while deregistering the instances in the group. When all instances are deregistered, then you can no longer describe the load balancer using  DescribeLoadBalancers . Note that the instances remain running.

    

    **Request Syntax** 
    ::

      response = client.detach_load_balancers(
          AutoScalingGroupName='string',
          LoadBalancerNames=[
              'string',
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type LoadBalancerNames: list
    :param LoadBalancerNames: **[REQUIRED]** 

      One or more load balancer names.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output for DetachLoadBalancers.

        
    

  .. py:method:: disable_metrics_collection(**kwargs)

    

    Disables group metrics for the specified Auto Scaling group.

    

    **Request Syntax** 
    ::

      response = client.disable_metrics_collection(
          AutoScalingGroupName='string',
          Metrics=[
              'string',
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name or Amazon Resource Name (ARN) of the group.

      

    
    :type Metrics: list
    :param Metrics: 

      One or more of the following metrics. If you omit this parameter, all metrics are disabled.

       

       
      * ``GroupMinSize``   
       
      * ``GroupMaxSize``   
       
      * ``GroupDesiredCapacity``   
       
      * ``GroupInServiceInstances``   
       
      * ``GroupPendingInstances``   
       
      * ``GroupStandbyInstances``   
       
      * ``GroupTerminatingInstances``   
       
      * ``GroupTotalInstances``   
       

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: enable_metrics_collection(**kwargs)

    

    Enables group metrics for the specified Auto Scaling group. For more information, see `Monitoring Your Auto Scaling Groups and Instances`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.enable_metrics_collection(
          AutoScalingGroupName='string',
          Metrics=[
              'string',
          ],
          Granularity='string'
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name or ARN of the Auto Scaling group.

      

    
    :type Metrics: list
    :param Metrics: 

      One or more of the following metrics. If you omit this parameter, all metrics are enabled.

       

       
      * ``GroupMinSize``   
       
      * ``GroupMaxSize``   
       
      * ``GroupDesiredCapacity``   
       
      * ``GroupInServiceInstances``   
       
      * ``GroupPendingInstances``   
       
      * ``GroupStandbyInstances``   
       
      * ``GroupTerminatingInstances``   
       
      * ``GroupTotalInstances``   
       

      

    
      - *(string) --* 

      
  
    :type Granularity: string
    :param Granularity: **[REQUIRED]** 

      The granularity to associate with the metrics to collect. The only valid value is ``1Minute`` .

      

    
    
    :returns: None

  .. py:method:: enter_standby(**kwargs)

    

    Moves the specified instances into ``Standby`` mode.

     

    For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.enter_standby(
          InstanceIds=[
              'string',
          ],
          AutoScalingGroupName='string',
          ShouldDecrementDesiredCapacity=True|False
      )
    :type InstanceIds: list
    :param InstanceIds: 

      One or more instances to move into ``Standby`` mode. You must specify at least one instance ID.

      

    
      - *(string) --* 

      
  
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type ShouldDecrementDesiredCapacity: boolean
    :param ShouldDecrementDesiredCapacity: **[REQUIRED]** 

      Specifies whether the instances moved to ``Standby`` mode count as part of the Auto Scaling group's desired capacity. If set, the desired capacity for the Auto Scaling group decrements by the number of instances moved to ``Standby`` mode.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Activities': [
                {
                    'ActivityId': 'string',
                    'AutoScalingGroupName': 'string',
                    'Description': 'string',
                    'Cause': 'string',
                    'StartTime': datetime(2015, 1, 1),
                    'EndTime': datetime(2015, 1, 1),
                    'StatusCode': 'PendingSpotBidPlacement'|'WaitingForSpotInstanceRequestId'|'WaitingForSpotInstanceId'|'WaitingForInstanceId'|'PreInService'|'InProgress'|'WaitingForELBConnectionDraining'|'MidLifecycleAction'|'WaitingForInstanceWarmup'|'Successful'|'Failed'|'Cancelled',
                    'StatusMessage': 'string',
                    'Progress': 123,
                    'Details': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of EnterStandby.

        
        

        - **Activities** *(list) --* 

          The activities related to moving instances into ``Standby`` mode.

          
          

          - *(dict) --* 

            Describes scaling activity, which is a long-running process that represents a change to your Auto Scaling group, such as changing its size or replacing an instance.

            
            

            - **ActivityId** *(string) --* 

              The ID of the activity.

              
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group.

              
            

            - **Description** *(string) --* 

              A friendly, more verbose description of the activity.

              
            

            - **Cause** *(string) --* 

              The reason the activity began.

              
            

            - **StartTime** *(datetime) --* 

              The start time of the activity.

              
            

            - **EndTime** *(datetime) --* 

              The end time of the activity.

              
            

            - **StatusCode** *(string) --* 

              The current status of the activity.

              
            

            - **StatusMessage** *(string) --* 

              A friendly, more verbose description of the activity status.

              
            

            - **Progress** *(integer) --* 

              A value between 0 and 100 that indicates the progress of the activity.

              
            

            - **Details** *(string) --* 

              The details about the activity.

              
        
      
    

  .. py:method:: execute_policy(**kwargs)

    

    Executes the specified policy.

    

    **Request Syntax** 
    ::

      response = client.execute_policy(
          AutoScalingGroupName='string',
          PolicyName='string',
          HonorCooldown=True|False,
          MetricValue=123.0,
          BreachThreshold=123.0
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: 

      The name or Amazon Resource Name (ARN) of the Auto Scaling group.

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name or ARN of the policy.

      

    
    :type HonorCooldown: boolean
    :param HonorCooldown: 

      If this parameter is true, Auto Scaling waits for the cooldown period to complete before executing the policy. Otherwise, Auto Scaling executes the policy without waiting for the cooldown period to complete.

       

      This parameter is not supported if the policy type is ``StepScaling`` .

       

      For more information, see `Auto Scaling Cooldowns`_ in the *Auto Scaling User Guide* .

      

    
    :type MetricValue: float
    :param MetricValue: 

      The metric value to compare to ``BreachThreshold`` . This enables you to execute a policy of type ``StepScaling`` and determine which step adjustment to use. For example, if the breach threshold is 50 and you want to use a step adjustment with a lower bound of 0 and an upper bound of 10, you can set the metric value to 59.

       

      If you specify a metric value that doesn't correspond to a step adjustment for the policy, the call returns an error.

       

      This parameter is required if the policy type is ``StepScaling`` and not supported otherwise.

      

    
    :type BreachThreshold: float
    :param BreachThreshold: 

      The breach threshold for the alarm.

       

      This parameter is required if the policy type is ``StepScaling`` and not supported otherwise.

      

    
    
    :returns: None

  .. py:method:: exit_standby(**kwargs)

    

    Moves the specified instances out of ``Standby`` mode.

     

    For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.exit_standby(
          InstanceIds=[
              'string',
          ],
          AutoScalingGroupName='string'
      )
    :type InstanceIds: list
    :param InstanceIds: 

      One or more instance IDs. You must specify at least one instance ID.

      

    
      - *(string) --* 

      
  
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Activities': [
                {
                    'ActivityId': 'string',
                    'AutoScalingGroupName': 'string',
                    'Description': 'string',
                    'Cause': 'string',
                    'StartTime': datetime(2015, 1, 1),
                    'EndTime': datetime(2015, 1, 1),
                    'StatusCode': 'PendingSpotBidPlacement'|'WaitingForSpotInstanceRequestId'|'WaitingForSpotInstanceId'|'WaitingForInstanceId'|'PreInService'|'InProgress'|'WaitingForELBConnectionDraining'|'MidLifecycleAction'|'WaitingForInstanceWarmup'|'Successful'|'Failed'|'Cancelled',
                    'StatusMessage': 'string',
                    'Progress': 123,
                    'Details': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the parameters for ExitStandby.

        
        

        - **Activities** *(list) --* 

          The activities related to moving instances out of ``Standby`` mode.

          
          

          - *(dict) --* 

            Describes scaling activity, which is a long-running process that represents a change to your Auto Scaling group, such as changing its size or replacing an instance.

            
            

            - **ActivityId** *(string) --* 

              The ID of the activity.

              
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group.

              
            

            - **Description** *(string) --* 

              A friendly, more verbose description of the activity.

              
            

            - **Cause** *(string) --* 

              The reason the activity began.

              
            

            - **StartTime** *(datetime) --* 

              The start time of the activity.

              
            

            - **EndTime** *(datetime) --* 

              The end time of the activity.

              
            

            - **StatusCode** *(string) --* 

              The current status of the activity.

              
            

            - **StatusMessage** *(string) --* 

              A friendly, more verbose description of the activity status.

              
            

            - **Progress** *(integer) --* 

              A value between 0 and 100 that indicates the progress of the activity.

              
            

            - **Details** *(string) --* 

              The details about the activity.

              
        
      
    

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

        


  .. py:method:: put_lifecycle_hook(**kwargs)

    

    Creates or updates a lifecycle hook for the specified Auto Scaling Group.

     

    A lifecycle hook tells Auto Scaling that you want to perform an action on an instance that is not actively in service; for example, either when the instance launches or before the instance terminates.

     

    This step is a part of the procedure for adding a lifecycle hook to an Auto Scaling group:

     

     
    * (Optional) Create a Lambda function and a rule that allows CloudWatch Events to invoke your Lambda function when Auto Scaling launches or terminates instances. 
     
    * (Optional) Create a notification target and an IAM role. The target can be either an Amazon SQS queue or an Amazon SNS topic. The role allows Auto Scaling to publish lifecycle notifications to the target. 
     
    * **Create the lifecycle hook. Specify whether the hook is used when the instances launch or terminate.**   
     
    * If you need more time, record the lifecycle action heartbeat to keep the instance in a pending state. 
     
    * If you finish before the timeout period ends, complete the lifecycle action. 
     

     

    For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling User Guide* .

     

    If you exceed your maximum limit of lifecycle hooks, which by default is 50 per Auto Scaling group, the call fails. For information about updating this limit, see `AWS Service Limits`_ in the *Amazon Web Services General Reference* .

    

    **Request Syntax** 
    ::

      response = client.put_lifecycle_hook(
          LifecycleHookName='string',
          AutoScalingGroupName='string',
          LifecycleTransition='string',
          RoleARN='string',
          NotificationTargetARN='string',
          NotificationMetadata='string',
          HeartbeatTimeout=123,
          DefaultResult='string'
      )
    :type LifecycleHookName: string
    :param LifecycleHookName: **[REQUIRED]** 

      The name of the lifecycle hook.

      

    
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group to which you want to assign the lifecycle hook.

      

    
    :type LifecycleTransition: string
    :param LifecycleTransition: 

      The instance state to which you want to attach the lifecycle hook. For a list of lifecycle hook types, see  DescribeLifecycleHookTypes .

       

      This parameter is required for new lifecycle hooks, but optional when updating existing hooks.

      

    
    :type RoleARN: string
    :param RoleARN: 

      The ARN of the IAM role that allows the Auto Scaling group to publish to the specified notification target.

       

      This parameter is required for new lifecycle hooks, but optional when updating existing hooks.

      

    
    :type NotificationTargetARN: string
    :param NotificationTargetARN: 

      The ARN of the notification target that Auto Scaling will use to notify you when an instance is in the transition state for the lifecycle hook. This target can be either an SQS queue or an SNS topic. If you specify an empty string, this overrides the current ARN.

       

      The notification messages sent to the target include the following information:

       

       
      * **AutoScalingGroupName** . The name of the Auto Scaling group. 
       
      * **AccountId** . The AWS account ID. 
       
      * **LifecycleTransition** . The lifecycle hook type. 
       
      * **LifecycleActionToken** . The lifecycle action token. 
       
      * **EC2InstanceId** . The EC2 instance ID. 
       
      * **LifecycleHookName** . The name of the lifecycle hook. 
       
      * **NotificationMetadata** . User-defined information. 
       

       

      This operation uses the JSON format when sending notifications to an Amazon SQS queue, and an email key/value pair format when sending notifications to an Amazon SNS topic.

       

      When you specify a notification target, Auto Scaling sends it a test message. Test messages contains the following additional key/value pair: ``"Event": "autoscaling:TEST_NOTIFICATION"`` .

      

    
    :type NotificationMetadata: string
    :param NotificationMetadata: 

      Contains additional information that you want to include any time Auto Scaling sends a message to the notification target.

      

    
    :type HeartbeatTimeout: integer
    :param HeartbeatTimeout: 

      The amount of time, in seconds, that can elapse before the lifecycle hook times out. When the lifecycle hook times out, Auto Scaling performs the default action. You can prevent the lifecycle hook from timing out by calling  RecordLifecycleActionHeartbeat . The default is 3600 seconds (1 hour).

      

    
    :type DefaultResult: string
    :param DefaultResult: 

      Defines the action the Auto Scaling group should take when the lifecycle hook timeout elapses or if an unexpected failure occurs. This parameter can be either ``CONTINUE`` or ``ABANDON`` . The default value is ``ABANDON`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of PutLifecycleHook.

        
    

  .. py:method:: put_notification_configuration(**kwargs)

    

    Configures an Auto Scaling group to send notifications when specified events take place. Subscribers to the specified topic can have messages delivered to an endpoint such as a web server or an email address.

     

    This configuration overwrites any existing configuration.

     

    For more information see `Getting SNS Notifications When Your Auto Scaling Group Scales`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.put_notification_configuration(
          AutoScalingGroupName='string',
          TopicARN='string',
          NotificationTypes=[
              'string',
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type TopicARN: string
    :param TopicARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) topic.

      

    
    :type NotificationTypes: list
    :param NotificationTypes: **[REQUIRED]** 

      The type of event that will cause the notification to be sent. For details about notification types supported by Auto Scaling, see  DescribeAutoScalingNotificationTypes .

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: put_scaling_policy(**kwargs)

    

    Creates or updates a policy for an Auto Scaling group. To update an existing policy, use the existing policy name and set the parameters you want to change. Any existing parameter not changed in an update to an existing policy is not changed in this update request.

     

    If you exceed your maximum limit of step adjustments, which by default is 20 per region, the call fails. For information about updating this limit, see `AWS Service Limits`_ in the *Amazon Web Services General Reference* .

    

    **Request Syntax** 
    ::

      response = client.put_scaling_policy(
          AutoScalingGroupName='string',
          PolicyName='string',
          PolicyType='string',
          AdjustmentType='string',
          MinAdjustmentStep=123,
          MinAdjustmentMagnitude=123,
          ScalingAdjustment=123,
          Cooldown=123,
          MetricAggregationType='string',
          StepAdjustments=[
              {
                  'MetricIntervalLowerBound': 123.0,
                  'MetricIntervalUpperBound': 123.0,
                  'ScalingAdjustment': 123
              },
          ],
          EstimatedInstanceWarmup=123
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name or ARN of the group.

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy.

      

    
    :type PolicyType: string
    :param PolicyType: 

      The policy type. Valid values are ``SimpleScaling`` and ``StepScaling`` . If the policy type is null, the value is treated as ``SimpleScaling`` .

      

    
    :type AdjustmentType: string
    :param AdjustmentType: **[REQUIRED]** 

      The adjustment type. Valid values are ``ChangeInCapacity`` , ``ExactCapacity`` , and ``PercentChangeInCapacity`` .

       

      For more information, see `Dynamic Scaling`_ in the *Auto Scaling User Guide* .

      

    
    :type MinAdjustmentStep: integer
    :param MinAdjustmentStep: 

      Available for backward compatibility. Use ``MinAdjustmentMagnitude`` instead.

      

    
    :type MinAdjustmentMagnitude: integer
    :param MinAdjustmentMagnitude: 

      The minimum number of instances to scale. If the value of ``AdjustmentType`` is ``PercentChangeInCapacity`` , the scaling policy changes the ``DesiredCapacity`` of the Auto Scaling group by at least this many instances. Otherwise, the error is ``ValidationError`` .

      

    
    :type ScalingAdjustment: integer
    :param ScalingAdjustment: 

      The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

       

      This parameter is required if the policy type is ``SimpleScaling`` and not supported otherwise.

      

    
    :type Cooldown: integer
    :param Cooldown: 

      The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start. If this parameter is not specified, the default cooldown period for the group applies.

       

      This parameter is not supported unless the policy type is ``SimpleScaling`` .

       

      For more information, see `Auto Scaling Cooldowns`_ in the *Auto Scaling User Guide* .

      

    
    :type MetricAggregationType: string
    :param MetricAggregationType: 

      The aggregation type for the CloudWatch metrics. Valid values are ``Minimum`` , ``Maximum`` , and ``Average`` . If the aggregation type is null, the value is treated as ``Average`` .

       

      This parameter is not supported if the policy type is ``SimpleScaling`` .

      

    
    :type StepAdjustments: list
    :param StepAdjustments: 

      A set of adjustments that enable you to scale based on the size of the alarm breach.

       

      This parameter is required if the policy type is ``StepScaling`` and not supported otherwise.

      

    
      - *(dict) --* 

        Describes an adjustment based on the difference between the value of the aggregated CloudWatch metric and the breach threshold that you've defined for the alarm.

         

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

          The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

          

        
      
  
    :type EstimatedInstanceWarmup: integer
    :param EstimatedInstanceWarmup: 

      The estimated time, in seconds, until a newly launched instance can contribute to the CloudWatch metrics. The default is to use the value specified for the default cooldown period for the group.

       

      This parameter is not supported if the policy type is ``SimpleScaling`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of PutScalingPolicy.

        
        

        - **PolicyARN** *(string) --* 

          The Amazon Resource Name (ARN) of the policy.

          
    

  .. py:method:: put_scheduled_update_group_action(**kwargs)

    

    Creates or updates a scheduled scaling action for an Auto Scaling group. When updating a scheduled scaling action, if you leave a parameter unspecified, the corresponding value remains unchanged in the affected Auto Scaling group.

     

    For more information, see `Scheduled Scaling`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.put_scheduled_update_group_action(
          AutoScalingGroupName='string',
          ScheduledActionName='string',
          Time=datetime(2015, 1, 1),
          StartTime=datetime(2015, 1, 1),
          EndTime=datetime(2015, 1, 1),
          Recurrence='string',
          MinSize=123,
          MaxSize=123,
          DesiredCapacity=123
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name or Amazon Resource Name (ARN) of the Auto Scaling group.

      

    
    :type ScheduledActionName: string
    :param ScheduledActionName: **[REQUIRED]** 

      The name of this scaling action.

      

    
    :type Time: datetime
    :param Time: 

      This parameter is deprecated.

      

    
    :type StartTime: datetime
    :param StartTime: 

      The time for this action to start, in "YYYY-MM-DDThh:mm:ssZ" format in UTC/GMT only (for example, ``2014-06-01T00:00:00Z`` ).

       

      If you try to schedule your action in the past, Auto Scaling returns an error message.

       

      When ``StartTime`` and ``EndTime`` are specified with ``Recurrence`` , they form the boundaries of when the recurring action starts and stops.

      

    
    :type EndTime: datetime
    :param EndTime: 

      The time for this action to end.

      

    
    :type Recurrence: string
    :param Recurrence: 

      The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format. For more information, see `Cron`_ in Wikipedia.

       

      When ``StartTime`` and ``EndTime`` are specified with ``Recurrence`` , they form the boundaries of when the recurring action will start and stop.

      

    
    :type MinSize: integer
    :param MinSize: 

      The minimum size for the Auto Scaling group.

      

    
    :type MaxSize: integer
    :param MaxSize: 

      The maximum size for the Auto Scaling group.

      

    
    :type DesiredCapacity: integer
    :param DesiredCapacity: 

      The number of EC2 instances that should be running in the group.

      

    
    
    :returns: None

  .. py:method:: record_lifecycle_action_heartbeat(**kwargs)

    

    Records a heartbeat for the lifecycle action associated with the specified token or instance. This extends the timeout by the length of time defined using  PutLifecycleHook .

     

    This step is a part of the procedure for adding a lifecycle hook to an Auto Scaling group:

     

     
    * (Optional) Create a Lambda function and a rule that allows CloudWatch Events to invoke your Lambda function when Auto Scaling launches or terminates instances. 
     
    * (Optional) Create a notification target and an IAM role. The target can be either an Amazon SQS queue or an Amazon SNS topic. The role allows Auto Scaling to publish lifecycle notifications to the target. 
     
    * Create the lifecycle hook. Specify whether the hook is used when the instances launch or terminate. 
     
    * **If you need more time, record the lifecycle action heartbeat to keep the instance in a pending state.**   
     
    * If you finish before the timeout period ends, complete the lifecycle action. 
     

     

    For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.record_lifecycle_action_heartbeat(
          LifecycleHookName='string',
          AutoScalingGroupName='string',
          LifecycleActionToken='string',
          InstanceId='string'
      )
    :type LifecycleHookName: string
    :param LifecycleHookName: **[REQUIRED]** 

      The name of the lifecycle hook.

      

    
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group for the hook.

      

    
    :type LifecycleActionToken: string
    :param LifecycleActionToken: 

      A token that uniquely identifies a specific lifecycle action associated with an instance. Auto Scaling sends this token to the notification target you specified when you created the lifecycle hook.

      

    
    :type InstanceId: string
    :param InstanceId: 

      The ID of the instance.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of RecordLifecycleActionHeartBeat.

        
    

  .. py:method:: resume_processes(**kwargs)

    

    Resumes the specified suspended Auto Scaling processes, or all suspended process, for the specified Auto Scaling group.

     

    For more information, see `Suspending and Resuming Auto Scaling Processes`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.resume_processes(
          AutoScalingGroupName='string',
          ScalingProcesses=[
              'string',
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name or Amazon Resource Name (ARN) of the Auto Scaling group.

      

    
    :type ScalingProcesses: list
    :param ScalingProcesses: 

      One or more of the following processes. If you omit this parameter, all processes are specified.

       

       
      * ``Launch``   
       
      * ``Terminate``   
       
      * ``HealthCheck``   
       
      * ``ReplaceUnhealthy``   
       
      * ``AZRebalance``   
       
      * ``AlarmNotification``   
       
      * ``ScheduledActions``   
       
      * ``AddToLoadBalancer``   
       

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: set_desired_capacity(**kwargs)

    

    Sets the size of the specified Auto Scaling group.

     

    For more information about desired capacity, see `What Is Auto Scaling?`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.set_desired_capacity(
          AutoScalingGroupName='string',
          DesiredCapacity=123,
          HonorCooldown=True|False
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type DesiredCapacity: integer
    :param DesiredCapacity: **[REQUIRED]** 

      The number of EC2 instances that should be running in the Auto Scaling group.

      

    
    :type HonorCooldown: boolean
    :param HonorCooldown: 

      By default, ``SetDesiredCapacity`` overrides any cooldown period associated with the Auto Scaling group. Specify ``True`` to make Auto Scaling to wait for the cool-down period associated with the Auto Scaling group to complete before initiating a scaling activity to set your Auto Scaling group to its new capacity.

      

    
    
    :returns: None

  .. py:method:: set_instance_health(**kwargs)

    

    Sets the health status of the specified instance.

     

    For more information, see `Health Checks`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.set_instance_health(
          InstanceId='string',
          HealthStatus='string',
          ShouldRespectGracePeriod=True|False
      )
    :type InstanceId: string
    :param InstanceId: **[REQUIRED]** 

      The ID of the instance.

      

    
    :type HealthStatus: string
    :param HealthStatus: **[REQUIRED]** 

      The health status of the instance. Set to ``Healthy`` if you want the instance to remain in service. Set to ``Unhealthy`` if you want the instance to be out of service. Auto Scaling will terminate and replace the unhealthy instance.

      

    
    :type ShouldRespectGracePeriod: boolean
    :param ShouldRespectGracePeriod: 

      If the Auto Scaling group of the specified instance has a ``HealthCheckGracePeriod`` specified for the group, by default, this call will respect the grace period. Set this to ``False`` , if you do not want the call to respect the grace period associated with the group.

       

      For more information, see the description of the health check grace period for  CreateAutoScalingGroup .

      

    
    
    :returns: None

  .. py:method:: set_instance_protection(**kwargs)

    

    Updates the instance protection settings of the specified instances.

     

    For more information, see `Instance Protection`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.set_instance_protection(
          InstanceIds=[
              'string',
          ],
          AutoScalingGroupName='string',
          ProtectedFromScaleIn=True|False
      )
    :type InstanceIds: list
    :param InstanceIds: **[REQUIRED]** 

      One or more instance IDs.

      

    
      - *(string) --* 

      
  
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the group.

      

    
    :type ProtectedFromScaleIn: boolean
    :param ProtectedFromScaleIn: **[REQUIRED]** 

      Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of SetInstanceProtection.

        
    

  .. py:method:: suspend_processes(**kwargs)

    

    Suspends the specified Auto Scaling processes, or all processes, for the specified Auto Scaling group.

     

    Note that if you suspend either the ``Launch`` or ``Terminate`` process types, it can prevent other process types from functioning properly.

     

    To resume processes that have been suspended, use  ResumeProcesses .

     

    For more information, see `Suspending and Resuming Auto Scaling Processes`_ in the *Auto Scaling User Guide* .

    

    **Request Syntax** 
    ::

      response = client.suspend_processes(
          AutoScalingGroupName='string',
          ScalingProcesses=[
              'string',
          ]
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name or Amazon Resource Name (ARN) of the Auto Scaling group.

      

    
    :type ScalingProcesses: list
    :param ScalingProcesses: 

      One or more of the following processes. If you omit this parameter, all processes are specified.

       

       
      * ``Launch``   
       
      * ``Terminate``   
       
      * ``HealthCheck``   
       
      * ``ReplaceUnhealthy``   
       
      * ``AZRebalance``   
       
      * ``AlarmNotification``   
       
      * ``ScheduledActions``   
       
      * ``AddToLoadBalancer``   
       

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: terminate_instance_in_auto_scaling_group(**kwargs)

    

    Terminates the specified instance and optionally adjusts the desired group size.

     

    This call simply makes a termination request. The instance is not terminated immediately.

    

    **Request Syntax** 
    ::

      response = client.terminate_instance_in_auto_scaling_group(
          InstanceId='string',
          ShouldDecrementDesiredCapacity=True|False
      )
    :type InstanceId: string
    :param InstanceId: **[REQUIRED]** 

      The ID of the instance.

      

    
    :type ShouldDecrementDesiredCapacity: boolean
    :param ShouldDecrementDesiredCapacity: **[REQUIRED]** 

      If ``true`` , terminating the instance also decrements the size of the Auto Scaling group.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Activity': {
                'ActivityId': 'string',
                'AutoScalingGroupName': 'string',
                'Description': 'string',
                'Cause': 'string',
                'StartTime': datetime(2015, 1, 1),
                'EndTime': datetime(2015, 1, 1),
                'StatusCode': 'PendingSpotBidPlacement'|'WaitingForSpotInstanceRequestId'|'WaitingForSpotInstanceId'|'WaitingForInstanceId'|'PreInService'|'InProgress'|'WaitingForELBConnectionDraining'|'MidLifecycleAction'|'WaitingForInstanceWarmup'|'Successful'|'Failed'|'Cancelled',
                'StatusMessage': 'string',
                'Progress': 123,
                'Details': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of TerminateInstancesInAutoScalingGroup.

        
        

        - **Activity** *(dict) --* 

          A scaling activity.

          
          

          - **ActivityId** *(string) --* 

            The ID of the activity.

            
          

          - **AutoScalingGroupName** *(string) --* 

            The name of the Auto Scaling group.

            
          

          - **Description** *(string) --* 

            A friendly, more verbose description of the activity.

            
          

          - **Cause** *(string) --* 

            The reason the activity began.

            
          

          - **StartTime** *(datetime) --* 

            The start time of the activity.

            
          

          - **EndTime** *(datetime) --* 

            The end time of the activity.

            
          

          - **StatusCode** *(string) --* 

            The current status of the activity.

            
          

          - **StatusMessage** *(string) --* 

            A friendly, more verbose description of the activity status.

            
          

          - **Progress** *(integer) --* 

            A value between 0 and 100 that indicates the progress of the activity.

            
          

          - **Details** *(string) --* 

            The details about the activity.

            
      
    

  .. py:method:: update_auto_scaling_group(**kwargs)

    

    Updates the configuration for the specified Auto Scaling group.

     

    To update an Auto Scaling group with a launch configuration with ``InstanceMonitoring`` set to ``False`` , you must first disable the collection of group metrics. Otherwise, you will get an error. If you have previously enabled the collection of group metrics, you can disable it using  DisableMetricsCollection .

     

    The new settings are registered upon the completion of this call. Any launch configuration settings take effect on any triggers after this call returns. Scaling activities that are currently in progress aren't affected.

     

    Note the following:

     

     
    * If you specify a new value for ``MinSize`` without specifying a value for ``DesiredCapacity`` , and the new ``MinSize`` is larger than the current size of the group, we implicitly call  SetDesiredCapacity to set the size of the group to the new value of ``MinSize`` . 
     
    * If you specify a new value for ``MaxSize`` without specifying a value for ``DesiredCapacity`` , and the new ``MaxSize`` is smaller than the current size of the group, we implicitly call  SetDesiredCapacity to set the size of the group to the new value of ``MaxSize`` . 
     
    * All other optional parameters are left unchanged if not specified. 
     

    

    **Request Syntax** 
    ::

      response = client.update_auto_scaling_group(
          AutoScalingGroupName='string',
          LaunchConfigurationName='string',
          MinSize=123,
          MaxSize=123,
          DesiredCapacity=123,
          DefaultCooldown=123,
          AvailabilityZones=[
              'string',
          ],
          HealthCheckType='string',
          HealthCheckGracePeriod=123,
          PlacementGroup='string',
          VPCZoneIdentifier='string',
          TerminationPolicies=[
              'string',
          ],
          NewInstancesProtectedFromScaleIn=True|False
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: **[REQUIRED]** 

      The name of the Auto Scaling group.

      

    
    :type LaunchConfigurationName: string
    :param LaunchConfigurationName: 

      The name of the launch configuration.

      

    
    :type MinSize: integer
    :param MinSize: 

      The minimum size of the Auto Scaling group.

      

    
    :type MaxSize: integer
    :param MaxSize: 

      The maximum size of the Auto Scaling group.

      

    
    :type DesiredCapacity: integer
    :param DesiredCapacity: 

      The number of EC2 instances that should be running in the Auto Scaling group. This number must be greater than or equal to the minimum size of the group and less than or equal to the maximum size of the group.

      

    
    :type DefaultCooldown: integer
    :param DefaultCooldown: 

      The amount of time, in seconds, after a scaling activity completes before another scaling activity can start. The default is 300.

       

      For more information, see `Auto Scaling Cooldowns`_ in the *Auto Scaling User Guide* .

      

    
    :type AvailabilityZones: list
    :param AvailabilityZones: 

      One or more Availability Zones for the group.

      

    
      - *(string) --* 

      
  
    :type HealthCheckType: string
    :param HealthCheckType: 

      The service to use for the health checks. The valid values are ``EC2`` and ``ELB`` .

      

    
    :type HealthCheckGracePeriod: integer
    :param HealthCheckGracePeriod: 

      The amount of time, in seconds, that Auto Scaling waits before checking the health status of an EC2 instance that has come into service. The default is 0.

       

      For more information, see `Health Checks`_ in the *Auto Scaling User Guide* .

      

    
    :type PlacementGroup: string
    :param PlacementGroup: 

      The name of the placement group into which you'll launch your instances, if any. For more information, see `Placement Groups`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

    
    :type VPCZoneIdentifier: string
    :param VPCZoneIdentifier: 

      The ID of the subnet, if you are launching into a VPC. You can specify several subnets in a comma-separated list.

       

      When you specify ``VPCZoneIdentifier`` with ``AvailabilityZones`` , ensure that the subnets' Availability Zones match the values you specify for ``AvailabilityZones`` .

       

      For more information, see `Launching Auto Scaling Instances in a VPC`_ in the *Auto Scaling User Guide* .

      

    
    :type TerminationPolicies: list
    :param TerminationPolicies: 

      A standalone termination policy or a list of termination policies used to select the instance to terminate. The policies are executed in the order that they are listed.

       

      For more information, see `Controlling Which Instances Auto Scaling Terminates During Scale In`_ in the *Auto Scaling User Guide* .

      

    
      - *(string) --* 

      
  
    :type NewInstancesProtectedFromScaleIn: boolean
    :param NewInstancesProtectedFromScaleIn: 

      Indicates whether newly launched instances are protected from termination by Auto Scaling when scaling in.

      

    
    
    :returns: None

==========
Paginators
==========


The available paginators are:

* :py:class:`AutoScaling.Paginator.DescribeAutoScalingGroups`


* :py:class:`AutoScaling.Paginator.DescribeAutoScalingInstances`


* :py:class:`AutoScaling.Paginator.DescribeLaunchConfigurations`


* :py:class:`AutoScaling.Paginator.DescribeNotificationConfigurations`


* :py:class:`AutoScaling.Paginator.DescribePolicies`


* :py:class:`AutoScaling.Paginator.DescribeScalingActivities`


* :py:class:`AutoScaling.Paginator.DescribeScheduledActions`


* :py:class:`AutoScaling.Paginator.DescribeTags`



.. py:class:: AutoScaling.Paginator.DescribeAutoScalingGroups

  ::

    
    paginator = client.get_paginator('describe_auto_scaling_groups')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`AutoScaling.Client.describe_auto_scaling_groups`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          AutoScalingGroupNames=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type AutoScalingGroupNames: list
    :param AutoScalingGroupNames: 

      The group names. If you omit this parameter, all Auto Scaling groups are described.

      

    
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
            'AutoScalingGroups': [
                {
                    'AutoScalingGroupName': 'string',
                    'AutoScalingGroupARN': 'string',
                    'LaunchConfigurationName': 'string',
                    'MinSize': 123,
                    'MaxSize': 123,
                    'DesiredCapacity': 123,
                    'DefaultCooldown': 123,
                    'AvailabilityZones': [
                        'string',
                    ],
                    'LoadBalancerNames': [
                        'string',
                    ],
                    'TargetGroupARNs': [
                        'string',
                    ],
                    'HealthCheckType': 'string',
                    'HealthCheckGracePeriod': 123,
                    'Instances': [
                        {
                            'InstanceId': 'string',
                            'AvailabilityZone': 'string',
                            'LifecycleState': 'Pending'|'Pending:Wait'|'Pending:Proceed'|'Quarantined'|'InService'|'Terminating'|'Terminating:Wait'|'Terminating:Proceed'|'Terminated'|'Detaching'|'Detached'|'EnteringStandby'|'Standby',
                            'HealthStatus': 'string',
                            'LaunchConfigurationName': 'string',
                            'ProtectedFromScaleIn': True|False
                        },
                    ],
                    'CreatedTime': datetime(2015, 1, 1),
                    'SuspendedProcesses': [
                        {
                            'ProcessName': 'string',
                            'SuspensionReason': 'string'
                        },
                    ],
                    'PlacementGroup': 'string',
                    'VPCZoneIdentifier': 'string',
                    'EnabledMetrics': [
                        {
                            'Metric': 'string',
                            'Granularity': 'string'
                        },
                    ],
                    'Status': 'string',
                    'Tags': [
                        {
                            'ResourceId': 'string',
                            'ResourceType': 'string',
                            'Key': 'string',
                            'Value': 'string',
                            'PropagateAtLaunch': True|False
                        },
                    ],
                    'TerminationPolicies': [
                        'string',
                    ],
                    'NewInstancesProtectedFromScaleIn': True|False
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output for DescribeAutoScalingGroups.

        
        

        - **AutoScalingGroups** *(list) --* 

          The groups.

          
          

          - *(dict) --* 

            Describes an Auto Scaling group.

            
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the group.

              
            

            - **AutoScalingGroupARN** *(string) --* 

              The Amazon Resource Name (ARN) of the group.

              
            

            - **LaunchConfigurationName** *(string) --* 

              The name of the associated launch configuration.

              
            

            - **MinSize** *(integer) --* 

              The minimum size of the group.

              
            

            - **MaxSize** *(integer) --* 

              The maximum size of the group.

              
            

            - **DesiredCapacity** *(integer) --* 

              The desired size of the group.

              
            

            - **DefaultCooldown** *(integer) --* 

              The amount of time, in seconds, after a scaling activity completes before another scaling activity can start.

              
            

            - **AvailabilityZones** *(list) --* 

              One or more Availability Zones for the group.

              
              

              - *(string) --* 
          
            

            - **LoadBalancerNames** *(list) --* 

              One or more load balancers associated with the group.

              
              

              - *(string) --* 
          
            

            - **TargetGroupARNs** *(list) --* 

              The Amazon Resource Names (ARN) of the target groups for your load balancer.

              
              

              - *(string) --* 
          
            

            - **HealthCheckType** *(string) --* 

              The service to use for the health checks. The valid values are ``EC2`` and ``ELB`` .

              
            

            - **HealthCheckGracePeriod** *(integer) --* 

              The amount of time, in seconds, that Auto Scaling waits before checking the health status of an EC2 instance that has come into service.

              
            

            - **Instances** *(list) --* 

              The EC2 instances associated with the group.

              
              

              - *(dict) --* 

                Describes an EC2 instance.

                
                

                - **InstanceId** *(string) --* 

                  The ID of the instance.

                  
                

                - **AvailabilityZone** *(string) --* 

                  The Availability Zone in which the instance is running.

                  
                

                - **LifecycleState** *(string) --* 

                  A description of the current lifecycle state. Note that the ``Quarantined`` state is not used.

                  
                

                - **HealthStatus** *(string) --* 

                  The last reported health status of the instance. "Healthy" means that the instance is healthy and should remain in service. "Unhealthy" means that the instance is unhealthy and Auto Scaling should terminate and replace it.

                  
                

                - **LaunchConfigurationName** *(string) --* 

                  The launch configuration associated with the instance.

                  
                

                - **ProtectedFromScaleIn** *(boolean) --* 

                  Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

                  
            
          
            

            - **CreatedTime** *(datetime) --* 

              The date and time the group was created.

              
            

            - **SuspendedProcesses** *(list) --* 

              The suspended processes associated with the group.

              
              

              - *(dict) --* 

                Describes an Auto Scaling process that has been suspended. For more information, see  ProcessType .

                
                

                - **ProcessName** *(string) --* 

                  The name of the suspended process.

                  
                

                - **SuspensionReason** *(string) --* 

                  The reason that the process was suspended.

                  
            
          
            

            - **PlacementGroup** *(string) --* 

              The name of the placement group into which you'll launch your instances, if any. For more information, see `Placement Groups`_ in the *Amazon Elastic Compute Cloud User Guide* .

              
            

            - **VPCZoneIdentifier** *(string) --* 

              One or more subnet IDs, if applicable, separated by commas.

               

              If you specify ``VPCZoneIdentifier`` and ``AvailabilityZones`` , ensure that the Availability Zones of the subnets match the values for ``AvailabilityZones`` .

              
            

            - **EnabledMetrics** *(list) --* 

              The metrics enabled for the group.

              
              

              - *(dict) --* 

                Describes an enabled metric.

                
                

                - **Metric** *(string) --* 

                  One of the following metrics:

                   

                   
                  * ``GroupMinSize``   
                   
                  * ``GroupMaxSize``   
                   
                  * ``GroupDesiredCapacity``   
                   
                  * ``GroupInServiceInstances``   
                   
                  * ``GroupPendingInstances``   
                   
                  * ``GroupStandbyInstances``   
                   
                  * ``GroupTerminatingInstances``   
                   
                  * ``GroupTotalInstances``   
                   

                  
                

                - **Granularity** *(string) --* 

                  The granularity of the metric. The only valid value is ``1Minute`` .

                  
            
          
            

            - **Status** *(string) --* 

              The current state of the group when  DeleteAutoScalingGroup is in progress.

              
            

            - **Tags** *(list) --* 

              The tags for the group.

              
              

              - *(dict) --* 

                Describes a tag for an Auto Scaling group.

                
                

                - **ResourceId** *(string) --* 

                  The name of the group.

                  
                

                - **ResourceType** *(string) --* 

                  The type of resource. The only supported value is ``auto-scaling-group`` .

                  
                

                - **Key** *(string) --* 

                  The tag key.

                  
                

                - **Value** *(string) --* 

                  The tag value.

                  
                

                - **PropagateAtLaunch** *(boolean) --* 

                  Determines whether the tag is added to new instances as they are launched in the group.

                  
            
          
            

            - **TerminationPolicies** *(list) --* 

              The termination policies for the group.

              
              

              - *(string) --* 
          
            

            - **NewInstancesProtectedFromScaleIn** *(boolean) --* 

              Indicates whether newly launched instances are protected from termination by Auto Scaling when scaling in.

              
        
      
    

.. py:class:: AutoScaling.Paginator.DescribeAutoScalingInstances

  ::

    
    paginator = client.get_paginator('describe_auto_scaling_instances')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`AutoScaling.Client.describe_auto_scaling_instances`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          InstanceIds=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type InstanceIds: list
    :param InstanceIds: 

      The instances to describe; up to 50 instance IDs. If you omit this parameter, all Auto Scaling instances are described. If you specify an ID that does not exist, it is ignored with no error.

      

    
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
            'AutoScalingInstances': [
                {
                    'InstanceId': 'string',
                    'AutoScalingGroupName': 'string',
                    'AvailabilityZone': 'string',
                    'LifecycleState': 'string',
                    'HealthStatus': 'string',
                    'LaunchConfigurationName': 'string',
                    'ProtectedFromScaleIn': True|False
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeAutoScalingInstances.

        
        

        - **AutoScalingInstances** *(list) --* 

          The instances.

          
          

          - *(dict) --* 

            Describes an EC2 instance associated with an Auto Scaling group.

            
            

            - **InstanceId** *(string) --* 

              The ID of the instance.

              
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group associated with the instance.

              
            

            - **AvailabilityZone** *(string) --* 

              The Availability Zone for the instance.

              
            

            - **LifecycleState** *(string) --* 

              The lifecycle state for the instance. For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling User Guide* .

              
            

            - **HealthStatus** *(string) --* 

              The last reported health status of this instance. "Healthy" means that the instance is healthy and should remain in service. "Unhealthy" means that the instance is unhealthy and Auto Scaling should terminate and replace it.

              
            

            - **LaunchConfigurationName** *(string) --* 

              The launch configuration associated with the instance.

              
            

            - **ProtectedFromScaleIn** *(boolean) --* 

              Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

              
        
      
    

.. py:class:: AutoScaling.Paginator.DescribeLaunchConfigurations

  ::

    
    paginator = client.get_paginator('describe_launch_configurations')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`AutoScaling.Client.describe_launch_configurations`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          LaunchConfigurationNames=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type LaunchConfigurationNames: list
    :param LaunchConfigurationNames: 

      The launch configuration names. If you omit this parameter, all launch configurations are described.

      

    
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
            'LaunchConfigurations': [
                {
                    'LaunchConfigurationName': 'string',
                    'LaunchConfigurationARN': 'string',
                    'ImageId': 'string',
                    'KeyName': 'string',
                    'SecurityGroups': [
                        'string',
                    ],
                    'ClassicLinkVPCId': 'string',
                    'ClassicLinkVPCSecurityGroups': [
                        'string',
                    ],
                    'UserData': 'string',
                    'InstanceType': 'string',
                    'KernelId': 'string',
                    'RamdiskId': 'string',
                    'BlockDeviceMappings': [
                        {
                            'VirtualName': 'string',
                            'DeviceName': 'string',
                            'Ebs': {
                                'SnapshotId': 'string',
                                'VolumeSize': 123,
                                'VolumeType': 'string',
                                'DeleteOnTermination': True|False,
                                'Iops': 123,
                                'Encrypted': True|False
                            },
                            'NoDevice': True|False
                        },
                    ],
                    'InstanceMonitoring': {
                        'Enabled': True|False
                    },
                    'SpotPrice': 'string',
                    'IamInstanceProfile': 'string',
                    'CreatedTime': datetime(2015, 1, 1),
                    'EbsOptimized': True|False,
                    'AssociatePublicIpAddress': True|False,
                    'PlacementTenancy': 'string'
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeLaunchConfigurations.

        
        

        - **LaunchConfigurations** *(list) --* 

          The launch configurations.

          
          

          - *(dict) --* 

            Describes a launch configuration.

            
            

            - **LaunchConfigurationName** *(string) --* 

              The name of the launch configuration.

              
            

            - **LaunchConfigurationARN** *(string) --* 

              The Amazon Resource Name (ARN) of the launch configuration.

              
            

            - **ImageId** *(string) --* 

              The ID of the Amazon Machine Image (AMI).

              
            

            - **KeyName** *(string) --* 

              The name of the key pair.

              
            

            - **SecurityGroups** *(list) --* 

              The security groups to associate with the instances.

              
              

              - *(string) --* 
          
            

            - **ClassicLinkVPCId** *(string) --* 

              The ID of a ClassicLink-enabled VPC to link your EC2-Classic instances to. This parameter can only be used if you are launching EC2-Classic instances. For more information, see `ClassicLink`_ in the *Amazon Elastic Compute Cloud User Guide* .

              
            

            - **ClassicLinkVPCSecurityGroups** *(list) --* 

              The IDs of one or more security groups for the VPC specified in ``ClassicLinkVPCId`` . This parameter is required if you specify a ClassicLink-enabled VPC, and cannot be used otherwise. For more information, see `ClassicLink`_ in the *Amazon Elastic Compute Cloud User Guide* .

              
              

              - *(string) --* 
          
            

            - **UserData** *(string) --* 

              The user data available to the instances.

              
            

            - **InstanceType** *(string) --* 

              The instance type for the instances.

              
            

            - **KernelId** *(string) --* 

              The ID of the kernel associated with the AMI.

              
            

            - **RamdiskId** *(string) --* 

              The ID of the RAM disk associated with the AMI.

              
            

            - **BlockDeviceMappings** *(list) --* 

              A block device mapping, which specifies the block devices for the instance.

              
              

              - *(dict) --* 

                Describes a block device mapping.

                
                

                - **VirtualName** *(string) --* 

                  The name of the virtual device (for example, ``ephemeral0`` ).

                  
                

                - **DeviceName** *(string) --* 

                  The device name exposed to the EC2 instance (for example, ``/dev/sdh`` or ``xvdh`` ).

                  
                

                - **Ebs** *(dict) --* 

                  The information about the Amazon EBS volume.

                  
                  

                  - **SnapshotId** *(string) --* 

                    The ID of the snapshot.

                    
                  

                  - **VolumeSize** *(integer) --* 

                    The volume size, in GiB. For ``standard`` volumes, specify a value from 1 to 1,024. For ``io1`` volumes, specify a value from 4 to 16,384. For ``gp2`` volumes, specify a value from 1 to 16,384. If you specify a snapshot, the volume size must be equal to or larger than the snapshot size.

                     

                    Default: If you create a volume from a snapshot and you don't specify a volume size, the default is the snapshot size.

                    
                  

                  - **VolumeType** *(string) --* 

                    The volume type. For more information, see `Amazon EBS Volume Types`_ in the *Amazon Elastic Compute Cloud User Guide* .

                     

                    Valid values: ``standard`` | ``io1`` | ``gp2``  

                     

                    Default: ``standard``  

                    
                  

                  - **DeleteOnTermination** *(boolean) --* 

                    Indicates whether the volume is deleted on instance termination.

                     

                    Default: ``true``  

                    
                  

                  - **Iops** *(integer) --* 

                    The number of I/O operations per second (IOPS) to provision for the volume.

                     

                    Constraint: Required when the volume type is ``io1`` .

                    
                  

                  - **Encrypted** *(boolean) --* 

                    Indicates whether the volume should be encrypted. Encrypted EBS volumes must be attached to instances that support Amazon EBS encryption. Volumes that are created from encrypted snapshots are automatically encrypted. There is no way to create an encrypted volume from an unencrypted snapshot or an unencrypted volume from an encrypted snapshot. For more information, see `Amazon EBS Encryption`_ in the *Amazon Elastic Compute Cloud User Guide* .

                    
              
                

                - **NoDevice** *(boolean) --* 

                  Suppresses a device mapping.

                   

                  If this parameter is true for the root device, the instance might fail the EC2 health check. Auto Scaling launches a replacement instance if the instance fails the health check.

                  
            
          
            

            - **InstanceMonitoring** *(dict) --* 

              Controls whether instances in this group are launched with detailed (``true`` ) or basic (``false`` ) monitoring.

              
              

              - **Enabled** *(boolean) --* 

                If ``True`` , instance monitoring is enabled.

                
          
            

            - **SpotPrice** *(string) --* 

              The price to bid when launching Spot Instances.

              
            

            - **IamInstanceProfile** *(string) --* 

              The name or Amazon Resource Name (ARN) of the instance profile associated with the IAM role for the instance.

              
            

            - **CreatedTime** *(datetime) --* 

              The creation date and time for the launch configuration.

              
            

            - **EbsOptimized** *(boolean) --* 

              Controls whether the instance is optimized for EBS I/O (``true`` ) or not (``false`` ).

              
            

            - **AssociatePublicIpAddress** *(boolean) --* 

              [EC2-VPC] Indicates whether to assign a public IP address to each instance.

              
            

            - **PlacementTenancy** *(string) --* 

              The tenancy of the instance, either ``default`` or ``dedicated`` . An instance with ``dedicated`` tenancy runs in an isolated, single-tenant hardware and can only be launched into a VPC.

              
        
      
    

.. py:class:: AutoScaling.Paginator.DescribeNotificationConfigurations

  ::

    
    paginator = client.get_paginator('describe_notification_configurations')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`AutoScaling.Client.describe_notification_configurations`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          AutoScalingGroupNames=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type AutoScalingGroupNames: list
    :param AutoScalingGroupNames: 

      The name of the group.

      

    
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
            'NotificationConfigurations': [
                {
                    'AutoScalingGroupName': 'string',
                    'TopicARN': 'string',
                    'NotificationType': 'string'
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output from DescribeNotificationConfigurations.

        
        

        - **NotificationConfigurations** *(list) --* 

          The notification configurations.

          
          

          - *(dict) --* 

            Describes a notification.

            
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the group.

              
            

            - **TopicARN** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) topic.

              
            

            - **NotificationType** *(string) --* 

              One of the following event notification types:

               

               
              * ``autoscaling:EC2_INSTANCE_LAUNCH``   
               
              * ``autoscaling:EC2_INSTANCE_LAUNCH_ERROR``   
               
              * ``autoscaling:EC2_INSTANCE_TERMINATE``   
               
              * ``autoscaling:EC2_INSTANCE_TERMINATE_ERROR``   
               
              * ``autoscaling:TEST_NOTIFICATION``   
               

              
        
      
    

.. py:class:: AutoScaling.Paginator.DescribePolicies

  ::

    
    paginator = client.get_paginator('describe_policies')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`AutoScaling.Client.describe_policies`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          AutoScalingGroupName='string',
          PolicyNames=[
              'string',
          ],
          PolicyTypes=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: 

      The name of the group.

      

    
    :type PolicyNames: list
    :param PolicyNames: 

      One or more policy names or policy ARNs to be described. If you omit this parameter, all policy names are described. If an group name is provided, the results are limited to that group. This list is limited to 50 items. If you specify an unknown policy name, it is ignored with no error.

      

    
      - *(string) --* 

      
  
    :type PolicyTypes: list
    :param PolicyTypes: 

      One or more policy types. Valid values are ``SimpleScaling`` and ``StepScaling`` .

      

    
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
            'ScalingPolicies': [
                {
                    'AutoScalingGroupName': 'string',
                    'PolicyName': 'string',
                    'PolicyARN': 'string',
                    'PolicyType': 'string',
                    'AdjustmentType': 'string',
                    'MinAdjustmentStep': 123,
                    'MinAdjustmentMagnitude': 123,
                    'ScalingAdjustment': 123,
                    'Cooldown': 123,
                    'StepAdjustments': [
                        {
                            'MetricIntervalLowerBound': 123.0,
                            'MetricIntervalUpperBound': 123.0,
                            'ScalingAdjustment': 123
                        },
                    ],
                    'MetricAggregationType': 'string',
                    'EstimatedInstanceWarmup': 123,
                    'Alarms': [
                        {
                            'AlarmName': 'string',
                            'AlarmARN': 'string'
                        },
                    ]
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribePolicies.

        
        

        - **ScalingPolicies** *(list) --* 

          The scaling policies.

          
          

          - *(dict) --* 

            Describes a scaling policy.

            
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group associated with this scaling policy.

              
            

            - **PolicyName** *(string) --* 

              The name of the scaling policy.

              
            

            - **PolicyARN** *(string) --* 

              The Amazon Resource Name (ARN) of the policy.

              
            

            - **PolicyType** *(string) --* 

              The policy type. Valid values are ``SimpleScaling`` and ``StepScaling`` .

              
            

            - **AdjustmentType** *(string) --* 

              The adjustment type, which specifies how ``ScalingAdjustment`` is interpreted. Valid values are ``ChangeInCapacity`` , ``ExactCapacity`` , and ``PercentChangeInCapacity`` .

              
            

            - **MinAdjustmentStep** *(integer) --* 

              Available for backward compatibility. Use ``MinAdjustmentMagnitude`` instead.

              
            

            - **MinAdjustmentMagnitude** *(integer) --* 

              The minimum number of instances to scale. If the value of ``AdjustmentType`` is ``PercentChangeInCapacity`` , the scaling policy changes the ``DesiredCapacity`` of the Auto Scaling group by at least this many instances. Otherwise, the error is ``ValidationError`` .

              
            

            - **ScalingAdjustment** *(integer) --* 

              The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

              
            

            - **Cooldown** *(integer) --* 

              The amount of time, in seconds, after a scaling activity completes before any further trigger-related scaling activities can start.

              
            

            - **StepAdjustments** *(list) --* 

              A set of adjustments that enable you to scale based on the size of the alarm breach.

              
              

              - *(dict) --* 

                Describes an adjustment based on the difference between the value of the aggregated CloudWatch metric and the breach threshold that you've defined for the alarm.

                 

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

                  The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

                  
            
          
            

            - **MetricAggregationType** *(string) --* 

              The aggregation type for the CloudWatch metrics. Valid values are ``Minimum`` , ``Maximum`` , and ``Average`` .

              
            

            - **EstimatedInstanceWarmup** *(integer) --* 

              The estimated time, in seconds, until a newly launched instance can contribute to the CloudWatch metrics.

              
            

            - **Alarms** *(list) --* 

              The CloudWatch alarms related to the policy.

              
              

              - *(dict) --* 

                Describes an alarm.

                
                

                - **AlarmName** *(string) --* 

                  The name of the alarm.

                  
                

                - **AlarmARN** *(string) --* 

                  The Amazon Resource Name (ARN) of the alarm.

                  
            
          
        
      
    

.. py:class:: AutoScaling.Paginator.DescribeScalingActivities

  ::

    
    paginator = client.get_paginator('describe_scaling_activities')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`AutoScaling.Client.describe_scaling_activities`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          ActivityIds=[
              'string',
          ],
          AutoScalingGroupName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type ActivityIds: list
    :param ActivityIds: 

      The activity IDs of the desired scaling activities. If you omit this parameter, all activities for the past six weeks are described. If you specify an Auto Scaling group, the results are limited to that group. The list of requested activities cannot contain more than 50 items. If unknown activities are requested, they are ignored with no error.

      

    
      - *(string) --* 

      
  
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: 

      The name of the group.

      

    
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
            'Activities': [
                {
                    'ActivityId': 'string',
                    'AutoScalingGroupName': 'string',
                    'Description': 'string',
                    'Cause': 'string',
                    'StartTime': datetime(2015, 1, 1),
                    'EndTime': datetime(2015, 1, 1),
                    'StatusCode': 'PendingSpotBidPlacement'|'WaitingForSpotInstanceRequestId'|'WaitingForSpotInstanceId'|'WaitingForInstanceId'|'PreInService'|'InProgress'|'WaitingForELBConnectionDraining'|'MidLifecycleAction'|'WaitingForInstanceWarmup'|'Successful'|'Failed'|'Cancelled',
                    'StatusMessage': 'string',
                    'Progress': 123,
                    'Details': 'string'
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeScalingActivities.

        
        

        - **Activities** *(list) --* 

          The scaling activities. Activities are sorted by start time. Activities still in progress are described first.

          
          

          - *(dict) --* 

            Describes scaling activity, which is a long-running process that represents a change to your Auto Scaling group, such as changing its size or replacing an instance.

            
            

            - **ActivityId** *(string) --* 

              The ID of the activity.

              
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the Auto Scaling group.

              
            

            - **Description** *(string) --* 

              A friendly, more verbose description of the activity.

              
            

            - **Cause** *(string) --* 

              The reason the activity began.

              
            

            - **StartTime** *(datetime) --* 

              The start time of the activity.

              
            

            - **EndTime** *(datetime) --* 

              The end time of the activity.

              
            

            - **StatusCode** *(string) --* 

              The current status of the activity.

              
            

            - **StatusMessage** *(string) --* 

              A friendly, more verbose description of the activity status.

              
            

            - **Progress** *(integer) --* 

              A value between 0 and 100 that indicates the progress of the activity.

              
            

            - **Details** *(string) --* 

              The details about the activity.

              
        
      
    

.. py:class:: AutoScaling.Paginator.DescribeScheduledActions

  ::

    
    paginator = client.get_paginator('describe_scheduled_actions')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`AutoScaling.Client.describe_scheduled_actions`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          AutoScalingGroupName='string',
          ScheduledActionNames=[
              'string',
          ],
          StartTime=datetime(2015, 1, 1),
          EndTime=datetime(2015, 1, 1),
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type AutoScalingGroupName: string
    :param AutoScalingGroupName: 

      The name of the group.

      

    
    :type ScheduledActionNames: list
    :param ScheduledActionNames: 

      Describes one or more scheduled actions. If you omit this parameter, all scheduled actions are described. If you specify an unknown scheduled action, it is ignored with no error.

       

      You can describe up to a maximum of 50 instances with a single call. If there are more items to return, the call returns a token. To get the next set of items, repeat the call with the returned token.

      

    
      - *(string) --* 

      
  
    :type StartTime: datetime
    :param StartTime: 

      The earliest scheduled start time to return. If scheduled action names are provided, this parameter is ignored.

      

    
    :type EndTime: datetime
    :param EndTime: 

      The latest scheduled start time to return. If scheduled action names are provided, this parameter is ignored.

      

    
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
            'ScheduledUpdateGroupActions': [
                {
                    'AutoScalingGroupName': 'string',
                    'ScheduledActionName': 'string',
                    'ScheduledActionARN': 'string',
                    'Time': datetime(2015, 1, 1),
                    'StartTime': datetime(2015, 1, 1),
                    'EndTime': datetime(2015, 1, 1),
                    'Recurrence': 'string',
                    'MinSize': 123,
                    'MaxSize': 123,
                    'DesiredCapacity': 123
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeScheduledActions.

        
        

        - **ScheduledUpdateGroupActions** *(list) --* 

          The scheduled actions.

          
          

          - *(dict) --* 

            Describes a scheduled update to an Auto Scaling group.

            
            

            - **AutoScalingGroupName** *(string) --* 

              The name of the group.

              
            

            - **ScheduledActionName** *(string) --* 

              The name of the scheduled action.

              
            

            - **ScheduledActionARN** *(string) --* 

              The Amazon Resource Name (ARN) of the scheduled action.

              
            

            - **Time** *(datetime) --* 

              This parameter is deprecated.

              
            

            - **StartTime** *(datetime) --* 

              The date and time that the action is scheduled to begin. This date and time can be up to one month in the future.

               

              When ``StartTime`` and ``EndTime`` are specified with ``Recurrence`` , they form the boundaries of when the recurring action will start and stop.

              
            

            - **EndTime** *(datetime) --* 

              The date and time that the action is scheduled to end. This date and time can be up to one month in the future.

              
            

            - **Recurrence** *(string) --* 

              The recurring schedule for the action.

              
            

            - **MinSize** *(integer) --* 

              The minimum size of the group.

              
            

            - **MaxSize** *(integer) --* 

              The maximum size of the group.

              
            

            - **DesiredCapacity** *(integer) --* 

              The number of instances you prefer to maintain in the group.

              
        
      
    

.. py:class:: AutoScaling.Paginator.DescribeTags

  ::

    
    paginator = client.get_paginator('describe_tags')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`AutoScaling.Client.describe_tags`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type Filters: list
    :param Filters: 

      A filter used to scope the tags to return.

      

    
      - *(dict) --* 

        Describes a filter.

        

      
        - **Name** *(string) --* 

          The name of the filter. The valid values are: ``"auto-scaling-group"`` , ``"key"`` , ``"value"`` , and ``"propagate-at-launch"`` .

          

        
        - **Values** *(list) --* 

          The value of the filter.

          

        
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
            'Tags': [
                {
                    'ResourceId': 'string',
                    'ResourceType': 'string',
                    'Key': 'string',
                    'Value': 'string',
                    'PropagateAtLaunch': True|False
                },
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeTags.

        
        

        - **Tags** *(list) --* 

          One or more tags.

          
          

          - *(dict) --* 

            Describes a tag for an Auto Scaling group.

            
            

            - **ResourceId** *(string) --* 

              The name of the group.

              
            

            - **ResourceType** *(string) --* 

              The type of resource. The only supported value is ``auto-scaling-group`` .

              
            

            - **Key** *(string) --* 

              The tag key.

              
            

            - **Value** *(string) --* 

              The tag value.

              
            

            - **PropagateAtLaunch** *(boolean) --* 

              Determines whether the tag is added to new instances as they are launched in the group.

              
        
      
    