

.. _Aurora on Amazon RDS: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html
.. _Tagging Amazon RDS Resources: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Tagging.html
.. _To create an IAM role for Amazon RDS Enhanced Monitoring: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Monitoring.html#USER_Monitoring.OS.IAMRole
.. _Constructing a Amazon RDS Amazon Resource Name (ARN): http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.ARN.html#USER_Tagging.ARN.Constructing
.. _Amazon RDS console: https://console.aws.amazon.com/rds/
.. _DB Instance Backups: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.BackingUpAndRestoringAmazonRDSInstances.html
.. _Adjusting the Preferred Maintenance Window: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/AdjustingTheMaintenanceWindow.html
.. _Copying a DB Snapshot: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CopySnapshot.html
.. _Wikipedia Tutorial: http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing
.. _DB Instance Maintenance: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.DBMaintenance.html
.. _Updating the VPC for a DB Instance: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.WorkingWithRDSInstanceinaVPC.html#USER_VPC.Non-VPC2VPC
.. _Constructing an RDS Amazon Resource Name (ARN): http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.ARN.html#USER_Tagging.ARN.Constructing
.. _Regions and Availability Zones: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RegionsAndAvailabilityZones.html
.. _Modifying a DB Instance and Using the Apply Immediately Parameter: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.DBInstance.Modifying.html
.. _Fault Tolerance for an Aurora DB Cluster: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Aurora.Managing.html#Aurora.Managing.FaultTolerance
.. _Migrating Data from an External MySQL Database to an Amazon Aurora DB Cluster: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Aurora.Migrate.html
.. _Events: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Events.html
.. _ISO8601 Wikipedia page.: http://en.wikipedia.org/wiki/ISO_8601


***
RDS
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: RDS.Client

  A low-level client representing Amazon Relational Database Service (RDS)::

    
    import boto3
    
    client = boto3.client('rds')

  
  These are the available methods:
  
  *   :py:meth:`add_source_identifier_to_subscription`

  
  *   :py:meth:`add_tags_to_resource`

  
  *   :py:meth:`apply_pending_maintenance_action`

  
  *   :py:meth:`authorize_db_security_group_ingress`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`copy_db_cluster_parameter_group`

  
  *   :py:meth:`copy_db_cluster_snapshot`

  
  *   :py:meth:`copy_db_parameter_group`

  
  *   :py:meth:`copy_db_snapshot`

  
  *   :py:meth:`copy_option_group`

  
  *   :py:meth:`create_db_cluster`

  
  *   :py:meth:`create_db_cluster_parameter_group`

  
  *   :py:meth:`create_db_cluster_snapshot`

  
  *   :py:meth:`create_db_instance`

  
  *   :py:meth:`create_db_instance_read_replica`

  
  *   :py:meth:`create_db_parameter_group`

  
  *   :py:meth:`create_db_security_group`

  
  *   :py:meth:`create_db_snapshot`

  
  *   :py:meth:`create_db_subnet_group`

  
  *   :py:meth:`create_event_subscription`

  
  *   :py:meth:`create_option_group`

  
  *   :py:meth:`delete_db_cluster`

  
  *   :py:meth:`delete_db_cluster_parameter_group`

  
  *   :py:meth:`delete_db_cluster_snapshot`

  
  *   :py:meth:`delete_db_instance`

  
  *   :py:meth:`delete_db_parameter_group`

  
  *   :py:meth:`delete_db_security_group`

  
  *   :py:meth:`delete_db_snapshot`

  
  *   :py:meth:`delete_db_subnet_group`

  
  *   :py:meth:`delete_event_subscription`

  
  *   :py:meth:`delete_option_group`

  
  *   :py:meth:`describe_account_attributes`

  
  *   :py:meth:`describe_certificates`

  
  *   :py:meth:`describe_db_cluster_parameter_groups`

  
  *   :py:meth:`describe_db_cluster_parameters`

  
  *   :py:meth:`describe_db_cluster_snapshot_attributes`

  
  *   :py:meth:`describe_db_cluster_snapshots`

  
  *   :py:meth:`describe_db_clusters`

  
  *   :py:meth:`describe_db_engine_versions`

  
  *   :py:meth:`describe_db_instances`

  
  *   :py:meth:`describe_db_log_files`

  
  *   :py:meth:`describe_db_parameter_groups`

  
  *   :py:meth:`describe_db_parameters`

  
  *   :py:meth:`describe_db_security_groups`

  
  *   :py:meth:`describe_db_snapshot_attributes`

  
  *   :py:meth:`describe_db_snapshots`

  
  *   :py:meth:`describe_db_subnet_groups`

  
  *   :py:meth:`describe_engine_default_cluster_parameters`

  
  *   :py:meth:`describe_engine_default_parameters`

  
  *   :py:meth:`describe_event_categories`

  
  *   :py:meth:`describe_event_subscriptions`

  
  *   :py:meth:`describe_events`

  
  *   :py:meth:`describe_option_group_options`

  
  *   :py:meth:`describe_option_groups`

  
  *   :py:meth:`describe_orderable_db_instance_options`

  
  *   :py:meth:`describe_pending_maintenance_actions`

  
  *   :py:meth:`describe_reserved_db_instances`

  
  *   :py:meth:`describe_reserved_db_instances_offerings`

  
  *   :py:meth:`describe_source_regions`

  
  *   :py:meth:`download_db_log_file_portion`

  
  *   :py:meth:`failover_db_cluster`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_tags_for_resource`

  
  *   :py:meth:`modify_db_cluster`

  
  *   :py:meth:`modify_db_cluster_parameter_group`

  
  *   :py:meth:`modify_db_cluster_snapshot_attribute`

  
  *   :py:meth:`modify_db_instance`

  
  *   :py:meth:`modify_db_parameter_group`

  
  *   :py:meth:`modify_db_snapshot_attribute`

  
  *   :py:meth:`modify_db_subnet_group`

  
  *   :py:meth:`modify_event_subscription`

  
  *   :py:meth:`modify_option_group`

  
  *   :py:meth:`promote_read_replica`

  
  *   :py:meth:`promote_read_replica_db_cluster`

  
  *   :py:meth:`purchase_reserved_db_instances_offering`

  
  *   :py:meth:`reboot_db_instance`

  
  *   :py:meth:`remove_source_identifier_from_subscription`

  
  *   :py:meth:`remove_tags_from_resource`

  
  *   :py:meth:`reset_db_cluster_parameter_group`

  
  *   :py:meth:`reset_db_parameter_group`

  
  *   :py:meth:`restore_db_cluster_from_s3`

  
  *   :py:meth:`restore_db_cluster_from_snapshot`

  
  *   :py:meth:`restore_db_cluster_to_point_in_time`

  
  *   :py:meth:`restore_db_instance_from_db_snapshot`

  
  *   :py:meth:`restore_db_instance_to_point_in_time`

  
  *   :py:meth:`revoke_db_security_group_ingress`

  

  .. py:method:: add_source_identifier_to_subscription(**kwargs)

    

    Adds a source identifier to an existing RDS event notification subscription.

    

    **Request Syntax** 
    ::

      response = client.add_source_identifier_to_subscription(
          SubscriptionName='string',
          SourceIdentifier='string'
      )
    :type SubscriptionName: string
    :param SubscriptionName: **[REQUIRED]** 

      The name of the RDS event notification subscription you want to add a source identifier to.

      

    
    :type SourceIdentifier: string
    :param SourceIdentifier: **[REQUIRED]** 

      The identifier of the event source to be added. An identifier must begin with a letter and must contain only ASCII letters, digits, and hyphens; it cannot end with a hyphen or contain two consecutive hyphens.

       

      Constraints:

       

       
      * If the source type is a DB instance, then a ``DBInstanceIdentifier`` must be supplied. 
       
      * If the source type is a DB security group, a ``DBSecurityGroupName`` must be supplied. 
       
      * If the source type is a DB parameter group, a ``DBParameterGroupName`` must be supplied. 
       
      * If the source type is a DB snapshot, a ``DBSnapshotIdentifier`` must be supplied. 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EventSubscription': {
                'CustomerAwsId': 'string',
                'CustSubscriptionId': 'string',
                'SnsTopicArn': 'string',
                'Status': 'string',
                'SubscriptionCreationTime': 'string',
                'SourceType': 'string',
                'SourceIdsList': [
                    'string',
                ],
                'EventCategoriesList': [
                    'string',
                ],
                'Enabled': True|False,
                'EventSubscriptionArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **EventSubscription** *(dict) --* 

          Contains the results of a successful invocation of the  DescribeEventSubscriptions action.

          
          

          - **CustomerAwsId** *(string) --* 

            The AWS customer account associated with the RDS event notification subscription.

            
          

          - **CustSubscriptionId** *(string) --* 

            The RDS event notification subscription Id.

            
          

          - **SnsTopicArn** *(string) --* 

            The topic ARN of the RDS event notification subscription.

            
          

          - **Status** *(string) --* 

            The status of the RDS event notification subscription.

             

            Constraints:

             

            Can be one of the following: creating | modifying | deleting | active | no-permission | topic-not-exist

             

            The status "no-permission" indicates that RDS no longer has permission to post to the SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created.

            
          

          - **SubscriptionCreationTime** *(string) --* 

            The time the RDS event notification subscription was created.

            
          

          - **SourceType** *(string) --* 

            The source type for the RDS event notification subscription.

            
          

          - **SourceIdsList** *(list) --* 

            A list of source IDs for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **EventCategoriesList** *(list) --* 

            A list of event categories for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **Enabled** *(boolean) --* 

            A Boolean value indicating if the subscription is enabled. True indicates the subscription is enabled.

            
          

          - **EventSubscriptionArn** *(string) --* 

            The Amazon Resource Name (ARN) for the event subscription.

            
      
    

  .. py:method:: add_tags_to_resource(**kwargs)

    

    Adds metadata tags to an Amazon RDS resource. These tags can also be used with cost allocation reporting to track cost associated with Amazon RDS resources, or used in a Condition statement in an IAM policy for Amazon RDS.

     

    For an overview on tagging Amazon RDS resources, see `Tagging Amazon RDS Resources`_ .

    

    **Request Syntax** 
    ::

      response = client.add_tags_to_resource(
          ResourceName='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type ResourceName: string
    :param ResourceName: **[REQUIRED]** 

      The Amazon RDS resource the tags will be added to. This value is an Amazon Resource Name (ARN). For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN)`_ .

      

    
    :type Tags: list
    :param Tags: **[REQUIRED]** 

      The tags to be assigned to the Amazon RDS resource.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :returns: None

  .. py:method:: apply_pending_maintenance_action(**kwargs)

    

    Applies a pending maintenance action to a resource (for example, to a DB instance).

    

    **Request Syntax** 
    ::

      response = client.apply_pending_maintenance_action(
          ResourceIdentifier='string',
          ApplyAction='string',
          OptInType='string'
      )
    :type ResourceIdentifier: string
    :param ResourceIdentifier: **[REQUIRED]** 

      The RDS Amazon Resource Name (ARN) of the resource that the pending maintenance action applies to. For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN)`_ .

      

    
    :type ApplyAction: string
    :param ApplyAction: **[REQUIRED]** 

      The pending maintenance action to apply to this resource.

       

      Valid values: ``system-update`` , ``db-upgrade``  

      

    
    :type OptInType: string
    :param OptInType: **[REQUIRED]** 

      A value that specifies the type of opt-in request, or undoes an opt-in request. An opt-in request of type ``immediate`` cannot be undone.

       

      Valid values:

       

       
      * ``immediate`` - Apply the maintenance action immediately. 
       
      * ``next-maintenance`` - Apply the maintenance action during the next maintenance window for the resource. 
       
      * ``undo-opt-in`` - Cancel any existing ``next-maintenance`` opt-in requests. 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ResourcePendingMaintenanceActions': {
                'ResourceIdentifier': 'string',
                'PendingMaintenanceActionDetails': [
                    {
                        'Action': 'string',
                        'AutoAppliedAfterDate': datetime(2015, 1, 1),
                        'ForcedApplyDate': datetime(2015, 1, 1),
                        'OptInStatus': 'string',
                        'CurrentApplyDate': datetime(2015, 1, 1),
                        'Description': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ResourcePendingMaintenanceActions** *(dict) --* 

          Describes the pending maintenance actions for a resource.

          
          

          - **ResourceIdentifier** *(string) --* 

            The ARN of the resource that has pending maintenance actions.

            
          

          - **PendingMaintenanceActionDetails** *(list) --* 

            A list that provides details about the pending maintenance actions for the resource.

            
            

            - *(dict) --* 

              Provides information about a pending maintenance action for a resource.

              
              

              - **Action** *(string) --* 

                The type of pending maintenance action that is available for the resource.

                
              

              - **AutoAppliedAfterDate** *(datetime) --* 

                The date of the maintenance window when the action will be applied. The maintenance action will be applied to the resource during its first maintenance window after this date. If this date is specified, any ``next-maintenance`` opt-in requests are ignored.

                
              

              - **ForcedApplyDate** *(datetime) --* 

                The date when the maintenance action will be automatically applied. The maintenance action will be applied to the resource on this date regardless of the maintenance window for the resource. If this date is specified, any ``immediate`` opt-in requests are ignored.

                
              

              - **OptInStatus** *(string) --* 

                Indicates the type of opt-in request that has been received for the resource.

                
              

              - **CurrentApplyDate** *(datetime) --* 

                The effective date when the pending maintenance action will be applied to the resource. This date takes into account opt-in requests received from the  ApplyPendingMaintenanceAction API, the ``AutoAppliedAfterDate`` , and the ``ForcedApplyDate`` . This value is blank if an opt-in request has not been received and nothing has been specified as ``AutoAppliedAfterDate`` or ``ForcedApplyDate`` .

                
              

              - **Description** *(string) --* 

                A description providing more detail about the maintenance action.

                
          
        
      
    

  .. py:method:: authorize_db_security_group_ingress(**kwargs)

    

    Enables ingress to a DBSecurityGroup using one of two forms of authorization. First, EC2 or VPC security groups can be added to the DBSecurityGroup if the application using the database is running on EC2 or VPC instances. Second, IP ranges are available if the application accessing your database is running on the Internet. Required parameters for this API are one of CIDR range, EC2SecurityGroupId for VPC, or (EC2SecurityGroupOwnerId and either EC2SecurityGroupName or EC2SecurityGroupId for non-VPC).

     

    .. note::

       

      You cannot authorize ingress from an EC2 security group in one region to an Amazon RDS DB instance in another. You cannot authorize ingress from a VPC security group in one VPC to an Amazon RDS DB instance in another.

       

     

    For an overview of CIDR ranges, go to the `Wikipedia Tutorial`_ . 

    

    **Request Syntax** 
    ::

      response = client.authorize_db_security_group_ingress(
          DBSecurityGroupName='string',
          CIDRIP='string',
          EC2SecurityGroupName='string',
          EC2SecurityGroupId='string',
          EC2SecurityGroupOwnerId='string'
      )
    :type DBSecurityGroupName: string
    :param DBSecurityGroupName: **[REQUIRED]** 

      The name of the DB security group to add authorization to.

      

    
    :type CIDRIP: string
    :param CIDRIP: 

      The IP range to authorize.

      

    
    :type EC2SecurityGroupName: string
    :param EC2SecurityGroupName: 

      Name of the EC2 security group to authorize. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, ``EC2SecurityGroupOwnerId`` and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

      

    
    :type EC2SecurityGroupId: string
    :param EC2SecurityGroupId: 

      Id of the EC2 security group to authorize. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, ``EC2SecurityGroupOwnerId`` and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

      

    
    :type EC2SecurityGroupOwnerId: string
    :param EC2SecurityGroupOwnerId: 

      AWS account number of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` parameter. The AWS Access Key ID is not an acceptable value. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, ``EC2SecurityGroupOwnerId`` and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSecurityGroup': {
                'OwnerId': 'string',
                'DBSecurityGroupName': 'string',
                'DBSecurityGroupDescription': 'string',
                'VpcId': 'string',
                'EC2SecurityGroups': [
                    {
                        'Status': 'string',
                        'EC2SecurityGroupName': 'string',
                        'EC2SecurityGroupId': 'string',
                        'EC2SecurityGroupOwnerId': 'string'
                    },
                ],
                'IPRanges': [
                    {
                        'Status': 'string',
                        'CIDRIP': 'string'
                    },
                ],
                'DBSecurityGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSecurityGroup** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  DescribeDBSecurityGroups   
           
          *  AuthorizeDBSecurityGroupIngress   
           
          *  CreateDBSecurityGroup   
           
          *  RevokeDBSecurityGroupIngress   
           

           

          This data type is used as a response element in the  DescribeDBSecurityGroups action.

          
          

          - **OwnerId** *(string) --* 

            Provides the AWS ID of the owner of a specific DB security group.

            
          

          - **DBSecurityGroupName** *(string) --* 

            Specifies the name of the DB security group.

            
          

          - **DBSecurityGroupDescription** *(string) --* 

            Provides the description of the DB security group.

            
          

          - **VpcId** *(string) --* 

            Provides the VpcId of the DB security group.

            
          

          - **EC2SecurityGroups** *(list) --* 

            Contains a list of  EC2SecurityGroup elements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  AuthorizeDBSecurityGroupIngress   
               
              *  DescribeDBSecurityGroups   
               
              *  RevokeDBSecurityGroupIngress   
               

              
              

              - **Status** *(string) --* 

                Provides the status of the EC2 security group. Status can be "authorizing", "authorized", "revoking", and "revoked".

                
              

              - **EC2SecurityGroupName** *(string) --* 

                Specifies the name of the EC2 security group.

                
              

              - **EC2SecurityGroupId** *(string) --* 

                Specifies the id of the EC2 security group.

                
              

              - **EC2SecurityGroupOwnerId** *(string) --* 

                Specifies the AWS ID of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` field. 

                
          
        
          

          - **IPRanges** *(list) --* 

            Contains a list of  IPRange elements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the  DescribeDBSecurityGroups action. 

              
              

              - **Status** *(string) --* 

                Specifies the status of the IP range. Status can be "authorizing", "authorized", "revoking", and "revoked".

                
              

              - **CIDRIP** *(string) --* 

                Specifies the IP range.

                
          
        
          

          - **DBSecurityGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB security group.

            
      
    

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


  .. py:method:: copy_db_cluster_parameter_group(**kwargs)

    

    Copies the specified DB cluster parameter group.

    

    **Request Syntax** 
    ::

      response = client.copy_db_cluster_parameter_group(
          SourceDBClusterParameterGroupIdentifier='string',
          TargetDBClusterParameterGroupIdentifier='string',
          TargetDBClusterParameterGroupDescription='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type SourceDBClusterParameterGroupIdentifier: string
    :param SourceDBClusterParameterGroupIdentifier: **[REQUIRED]** 

      The identifier or Amazon Resource Name (ARN) for the source DB cluster parameter group. For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN)`_ . 

       

      Constraints:

       

       
      * Must specify a valid DB cluster parameter group. 
       
      * If the source DB cluster parameter group is in the same region as the copy, specify a valid DB parameter group identifier, for example ``my-db-cluster-param-group`` , or a valid ARN. 
       
      * If the source DB parameter group is in a different region than the copy, specify a valid DB cluster parameter group ARN, for example ``arn:aws:rds:us-east-1:123456789012:cluster-pg:custom-cluster-group1`` . 
       

      

    
    :type TargetDBClusterParameterGroupIdentifier: string
    :param TargetDBClusterParameterGroupIdentifier: **[REQUIRED]** 

      The identifier for the copied DB cluster parameter group.

       

      Constraints:

       

       
      * Cannot be null, empty, or blank 
       
      * Must contain from 1 to 255 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``my-cluster-param-group1``  

      

    
    :type TargetDBClusterParameterGroupDescription: string
    :param TargetDBClusterParameterGroupDescription: **[REQUIRED]** 

      A description for the copied DB cluster parameter group.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBClusterParameterGroup': {
                'DBClusterParameterGroupName': 'string',
                'DBParameterGroupFamily': 'string',
                'Description': 'string',
                'DBClusterParameterGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBClusterParameterGroup** *(dict) --* 

          Contains the result of a successful invocation of the  CreateDBClusterParameterGroup or  CopyDBClusterParameterGroup action. 

           

          This data type is used as a request parameter in the  DeleteDBClusterParameterGroup action, and as a response element in the  DescribeDBClusterParameterGroups action. 

          
          

          - **DBClusterParameterGroupName** *(string) --* 

            Provides the name of the DB cluster parameter group.

            
          

          - **DBParameterGroupFamily** *(string) --* 

            Provides the name of the DB parameter group family that this DB cluster parameter group is compatible with.

            
          

          - **Description** *(string) --* 

            Provides the customer-specified description for this DB cluster parameter group.

            
          

          - **DBClusterParameterGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster parameter group.

            
      
    

  .. py:method:: copy_db_cluster_snapshot(**kwargs)

    

    Creates a snapshot of a DB cluster. For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.copy_db_cluster_snapshot(
          SourceDBClusterSnapshotIdentifier='string',
          TargetDBClusterSnapshotIdentifier='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type SourceDBClusterSnapshotIdentifier: string
    :param SourceDBClusterSnapshotIdentifier: **[REQUIRED]** 

      The identifier of the DB cluster snapshot to copy. This parameter is not case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

       

      Example: ``my-cluster-snapshot1``  

      

    
    :type TargetDBClusterSnapshotIdentifier: string
    :param TargetDBClusterSnapshotIdentifier: **[REQUIRED]** 

      The identifier of the new DB cluster snapshot to create from the source DB cluster snapshot. This parameter is not case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

       

      Example: ``my-cluster-snapshot2``  

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBClusterSnapshot': {
                'AvailabilityZones': [
                    'string',
                ],
                'DBClusterSnapshotIdentifier': 'string',
                'DBClusterIdentifier': 'string',
                'SnapshotCreateTime': datetime(2015, 1, 1),
                'Engine': 'string',
                'AllocatedStorage': 123,
                'Status': 'string',
                'Port': 123,
                'VpcId': 'string',
                'ClusterCreateTime': datetime(2015, 1, 1),
                'MasterUsername': 'string',
                'EngineVersion': 'string',
                'LicenseModel': 'string',
                'SnapshotType': 'string',
                'PercentProgress': 123,
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DBClusterSnapshotArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBClusterSnapshot** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBClusterSnapshot   
           
          *  DeleteDBClusterSnapshot   
           

           

          This data type is used as a response element in the  DescribeDBClusterSnapshots action.

          
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster snapshot can be restored in.

            
            

            - *(string) --* 
        
          

          - **DBClusterSnapshotIdentifier** *(string) --* 

            Specifies the identifier for the DB cluster snapshot.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Specifies the DB cluster identifier of the DB cluster that this DB cluster snapshot was created from.

            
          

          - **SnapshotCreateTime** *(datetime) --* 

            Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

            
          

          - **Engine** *(string) --* 

            Specifies the name of the database engine.

            
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **Status** *(string) --* 

            Specifies the status of this DB cluster snapshot.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the DB cluster was listening on at the time of the snapshot.

            
          

          - **VpcId** *(string) --* 

            Provides the VPC ID associated with the DB cluster snapshot.

            
          

          - **ClusterCreateTime** *(datetime) --* 

            Specifies the time when the DB cluster was created, in Universal Coordinated Time (UTC).

            
          

          - **MasterUsername** *(string) --* 

            Provides the master username for the DB cluster snapshot.

            
          

          - **EngineVersion** *(string) --* 

            Provides the version of the database engine for this DB cluster snapshot.

            
          

          - **LicenseModel** *(string) --* 

            Provides the license model information for this DB cluster snapshot.

            
          

          - **SnapshotType** *(string) --* 

            Provides the type of the DB cluster snapshot.

            
          

          - **PercentProgress** *(integer) --* 

            Specifies the percentage of the estimated data that has been transferred.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster snapshot is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster snapshot.

            
          

          - **DBClusterSnapshotArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster snapshot.

            
      
    

  .. py:method:: copy_db_parameter_group(**kwargs)

    

    Copies the specified DB parameter group.

    

    **Request Syntax** 
    ::

      response = client.copy_db_parameter_group(
          SourceDBParameterGroupIdentifier='string',
          TargetDBParameterGroupIdentifier='string',
          TargetDBParameterGroupDescription='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type SourceDBParameterGroupIdentifier: string
    :param SourceDBParameterGroupIdentifier: **[REQUIRED]** 

      The identifier or ARN for the source DB parameter group. For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN)`_ . 

       

      Constraints:

       

       
      * Must specify a valid DB parameter group. 
       
      * Must specify a valid DB parameter group identifier, for example ``my-db-param-group`` , or a valid ARN. 
       

      

    
    :type TargetDBParameterGroupIdentifier: string
    :param TargetDBParameterGroupIdentifier: **[REQUIRED]** 

      The identifier for the copied DB parameter group.

       

      Constraints:

       

       
      * Cannot be null, empty, or blank 
       
      * Must contain from 1 to 255 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``my-db-parameter-group``  

      

    
    :type TargetDBParameterGroupDescription: string
    :param TargetDBParameterGroupDescription: **[REQUIRED]** 

      A description for the copied DB parameter group.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBParameterGroup': {
                'DBParameterGroupName': 'string',
                'DBParameterGroupFamily': 'string',
                'Description': 'string',
                'DBParameterGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBParameterGroup** *(dict) --* 

          Contains the result of a successful invocation of the  CreateDBParameterGroup action. 

           

          This data type is used as a request parameter in the  DeleteDBParameterGroup action, and as a response element in the  DescribeDBParameterGroups action. 

          
          

          - **DBParameterGroupName** *(string) --* 

            Provides the name of the DB parameter group.

            
          

          - **DBParameterGroupFamily** *(string) --* 

            Provides the name of the DB parameter group family that this DB parameter group is compatible with.

            
          

          - **Description** *(string) --* 

            Provides the customer-specified description for this DB parameter group.

            
          

          - **DBParameterGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB parameter group.

            
      
    

  .. py:method:: copy_db_snapshot(**kwargs)

    

    Copies the specified DB snapshot. The source DB snapshot must be in the "available" state.

     

    If you are copying from a shared manual DB snapshot, the ``SourceDBSnapshotIdentifier`` must be the ARN of the shared DB snapshot.

    

    **Request Syntax** 
    ::

      response = client.copy_db_snapshot(
          SourceDBSnapshotIdentifier='string',
          TargetDBSnapshotIdentifier='string',
          KmsKeyId='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          CopyTags=True|False
      )
    :type SourceDBSnapshotIdentifier: string
    :param SourceDBSnapshotIdentifier: **[REQUIRED]** 

      The identifier for the source DB snapshot.

       

      If you are copying from a shared manual DB snapshot, this must be the ARN of the shared DB snapshot.

       

      Constraints:

       

       
      * Must specify a valid system snapshot in the "available" state. 
       
      * If the source snapshot is in the same region as the copy, specify a valid DB snapshot identifier. 
       
      * If the source snapshot is in a different region than the copy, specify a valid DB snapshot ARN. For more information, go to `Copying a DB Snapshot`_ . 
       

       

      Example: ``rds:mydb-2012-04-02-00-01``  

       

      Example: ``arn:aws:rds:rr-regn-1:123456789012:snapshot:mysql-instance1-snapshot-20130805``  

      

    
    :type TargetDBSnapshotIdentifier: string
    :param TargetDBSnapshotIdentifier: **[REQUIRED]** 

      The identifier for the copied snapshot.

       

      Constraints:

       

       
      * Cannot be null, empty, or blank 
       
      * Must contain from 1 to 255 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``my-db-snapshot``  

      

    
    :type KmsKeyId: string
    :param KmsKeyId: 

      The AWS Key Management Service (AWS KMS) key identifier for an encrypted DB snapshot. The KMS key identifier is the Amazon Resource Name (ARN) or the KMS key alias for the KMS encryption key.

       

      If you copy an unencrypted DB snapshot and specify a value for the ``KmsKeyId`` parameter, Amazon RDS encrypts the target DB snapshot using the specified KMS encryption key.

       

      If you copy an encrypted DB snapshot from your AWS account, you can specify a value for ``KmsKeyId`` to encrypt the copy with a new KMS encryption key. If you don't specify a value for ``KmsKeyId`` then the copy of the DB snapshot is encrypted with the same KMS key as the source DB snapshot. 

       

      If you copy an encrypted DB snapshot that is shared from another AWS account, then you must specify a value for ``KmsKeyId`` .

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    :type CopyTags: boolean
    :param CopyTags: 

      True to copy all tags from the source DB snapshot to the target DB snapshot; otherwise false. The default is false.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSnapshot': {
                'DBSnapshotIdentifier': 'string',
                'DBInstanceIdentifier': 'string',
                'SnapshotCreateTime': datetime(2015, 1, 1),
                'Engine': 'string',
                'AllocatedStorage': 123,
                'Status': 'string',
                'Port': 123,
                'AvailabilityZone': 'string',
                'VpcId': 'string',
                'InstanceCreateTime': datetime(2015, 1, 1),
                'MasterUsername': 'string',
                'EngineVersion': 'string',
                'LicenseModel': 'string',
                'SnapshotType': 'string',
                'Iops': 123,
                'OptionGroupName': 'string',
                'PercentProgress': 123,
                'SourceRegion': 'string',
                'SourceDBSnapshotIdentifier': 'string',
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'Encrypted': True|False,
                'KmsKeyId': 'string',
                'DBSnapshotArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSnapshot** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBSnapshot   
           
          *  DeleteDBSnapshot   
           

           

          This data type is used as a response element in the  DescribeDBSnapshots action.

          
          

          - **DBSnapshotIdentifier** *(string) --* 

            Specifies the identifier for the DB snapshot.

            
          

          - **DBInstanceIdentifier** *(string) --* 

            Specifies the DB instance identifier of the DB instance this DB snapshot was created from.

            
          

          - **SnapshotCreateTime** *(datetime) --* 

            Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

            
          

          - **Engine** *(string) --* 

            Specifies the name of the database engine.

            
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **Status** *(string) --* 

            Specifies the status of this DB snapshot.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine was listening on at the time of the snapshot.

            
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance was located in at the time of the DB snapshot.

            
          

          - **VpcId** *(string) --* 

            Provides the VPC ID associated with the DB snapshot.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Specifies the time when the snapshot was taken, in Universal Coordinated Time (UTC).

            
          

          - **MasterUsername** *(string) --* 

            Provides the master username for the DB snapshot.

            
          

          - **EngineVersion** *(string) --* 

            Specifies the version of the database engine.

            
          

          - **LicenseModel** *(string) --* 

            License model information for the restored DB instance.

            
          

          - **SnapshotType** *(string) --* 

            Provides the type of the DB snapshot.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value of the DB instance at the time of the snapshot.

            
          

          - **OptionGroupName** *(string) --* 

            Provides the option group name for the DB snapshot.

            
          

          - **PercentProgress** *(integer) --* 

            The percentage of the estimated data that has been transferred.

            
          

          - **SourceRegion** *(string) --* 

            The region that the DB snapshot was created in or copied from.

            
          

          - **SourceDBSnapshotIdentifier** *(string) --* 

            The DB snapshot Arn that the DB snapshot was copied from. It only has value in case of cross customer or cross region copy.

            
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB Snapshot.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which to associate the instance for TDE encryption.

            
          

          - **Encrypted** *(boolean) --* 

            Specifies whether the DB snapshot is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``Encrypted`` is true, the KMS key identifier for the encrypted DB snapshot. 

            
          

          - **DBSnapshotArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB snapshot.

            
      
    

  .. py:method:: copy_option_group(**kwargs)

    

    Copies the specified option group.

    

    **Request Syntax** 
    ::

      response = client.copy_option_group(
          SourceOptionGroupIdentifier='string',
          TargetOptionGroupIdentifier='string',
          TargetOptionGroupDescription='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type SourceOptionGroupIdentifier: string
    :param SourceOptionGroupIdentifier: **[REQUIRED]** 

      The identifier or ARN for the source option group. For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN)`_ . 

       

      Constraints:

       

       
      * Must specify a valid option group. 
       
      * If the source option group is in the same region as the copy, specify a valid option group identifier, for example ``my-option-group`` , or a valid ARN. 
       
      * If the source option group is in a different region than the copy, specify a valid option group ARN, for example ``arn:aws:rds:us-west-2:123456789012:og:special-options`` . 
       

      

    
    :type TargetOptionGroupIdentifier: string
    :param TargetOptionGroupIdentifier: **[REQUIRED]** 

      The identifier for the copied option group.

       

      Constraints:

       

       
      * Cannot be null, empty, or blank 
       
      * Must contain from 1 to 255 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``my-option-group``  

      

    
    :type TargetOptionGroupDescription: string
    :param TargetOptionGroupDescription: **[REQUIRED]** 

      The description for the copied option group.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OptionGroup': {
                'OptionGroupName': 'string',
                'OptionGroupDescription': 'string',
                'EngineName': 'string',
                'MajorEngineVersion': 'string',
                'Options': [
                    {
                        'OptionName': 'string',
                        'OptionDescription': 'string',
                        'Persistent': True|False,
                        'Permanent': True|False,
                        'Port': 123,
                        'OptionVersion': 'string',
                        'OptionSettings': [
                            {
                                'Name': 'string',
                                'Value': 'string',
                                'DefaultValue': 'string',
                                'Description': 'string',
                                'ApplyType': 'string',
                                'DataType': 'string',
                                'AllowedValues': 'string',
                                'IsModifiable': True|False,
                                'IsCollection': True|False
                            },
                        ],
                        'DBSecurityGroupMemberships': [
                            {
                                'DBSecurityGroupName': 'string',
                                'Status': 'string'
                            },
                        ],
                        'VpcSecurityGroupMemberships': [
                            {
                                'VpcSecurityGroupId': 'string',
                                'Status': 'string'
                            },
                        ]
                    },
                ],
                'AllowsVpcAndNonVpcInstanceMemberships': True|False,
                'VpcId': 'string',
                'OptionGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **OptionGroup** *(dict) --* 

          

          
          

          - **OptionGroupName** *(string) --* 

            Specifies the name of the option group.

            
          

          - **OptionGroupDescription** *(string) --* 

            Provides a description of the option group.

            
          

          - **EngineName** *(string) --* 

            Indicates the name of the engine that this option group can be applied to.

            
          

          - **MajorEngineVersion** *(string) --* 

            Indicates the major engine version associated with this option group.

            
          

          - **Options** *(list) --* 

            Indicates what options are available in the option group.

            
            

            - *(dict) --* 

              Option details.

              
              

              - **OptionName** *(string) --* 

                The name of the option.

                
              

              - **OptionDescription** *(string) --* 

                The description of the option.

                
              

              - **Persistent** *(boolean) --* 

                Indicate if this option is persistent.

                
              

              - **Permanent** *(boolean) --* 

                Indicate if this option is permanent.

                
              

              - **Port** *(integer) --* 

                If required, the port configured for this option to use.

                
              

              - **OptionVersion** *(string) --* 

                The version of the option.

                
              

              - **OptionSettings** *(list) --* 

                The option settings for this option.

                
                

                - *(dict) --* 

                  Option settings are the actual settings being applied or configured for that option. It is used when you modify an option group or describe option groups. For example, the NATIVE_NETWORK_ENCRYPTION option has a setting called SQLNET.ENCRYPTION_SERVER that can have several different values.

                  
                  

                  - **Name** *(string) --* 

                    The name of the option that has settings that you can set.

                    
                  

                  - **Value** *(string) --* 

                    The current value of the option setting.

                    
                  

                  - **DefaultValue** *(string) --* 

                    The default value of the option setting.

                    
                  

                  - **Description** *(string) --* 

                    The description of the option setting.

                    
                  

                  - **ApplyType** *(string) --* 

                    The DB engine specific parameter type.

                    
                  

                  - **DataType** *(string) --* 

                    The data type of the option setting.

                    
                  

                  - **AllowedValues** *(string) --* 

                    The allowed values of the option setting.

                    
                  

                  - **IsModifiable** *(boolean) --* 

                    A Boolean value that, when true, indicates the option setting can be modified from the default.

                    
                  

                  - **IsCollection** *(boolean) --* 

                    Indicates if the option setting is part of a collection.

                    
              
            
              

              - **DBSecurityGroupMemberships** *(list) --* 

                If the option requires access to a port, then this DB security group allows access to the port.

                
                

                - *(dict) --* 

                  This data type is used as a response element in the following actions:

                   

                   
                  *  ModifyDBInstance   
                   
                  *  RebootDBInstance   
                   
                  *  RestoreDBInstanceFromDBSnapshot   
                   
                  *  RestoreDBInstanceToPointInTime   
                   

                  
                  

                  - **DBSecurityGroupName** *(string) --* 

                    The name of the DB security group.

                    
                  

                  - **Status** *(string) --* 

                    The status of the DB security group.

                    
              
            
              

              - **VpcSecurityGroupMemberships** *(list) --* 

                If the option requires access to a port, then this VPC security group allows access to the port.

                
                

                - *(dict) --* 

                  This data type is used as a response element for queries on VPC security group membership.

                  
                  

                  - **VpcSecurityGroupId** *(string) --* 

                    The name of the VPC security group.

                    
                  

                  - **Status** *(string) --* 

                    The status of the VPC security group.

                    
              
            
          
        
          

          - **AllowsVpcAndNonVpcInstanceMemberships** *(boolean) --* 

            Indicates whether this option group can be applied to both VPC and non-VPC instances. The value ``true`` indicates the option group can be applied to both VPC and non-VPC instances. 

            
          

          - **VpcId** *(string) --* 

            If **AllowsVpcAndNonVpcInstanceMemberships** is ``false`` , this field is blank. If **AllowsVpcAndNonVpcInstanceMemberships** is ``true`` and this field is blank, then this option group can be applied to both VPC and non-VPC instances. If this field contains a value, then this option group can only be applied to instances that are in the VPC indicated by this field. 

            
          

          - **OptionGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the option group.

            
      
    

  .. py:method:: create_db_cluster(**kwargs)

    

    Creates a new Amazon Aurora DB cluster.

     

    You can use the ``ReplicationSourceIdentifier`` parameter to create the DB cluster as a Read Replica of another DB cluster.

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.create_db_cluster(
          AvailabilityZones=[
              'string',
          ],
          BackupRetentionPeriod=123,
          CharacterSetName='string',
          DatabaseName='string',
          DBClusterIdentifier='string',
          DBClusterParameterGroupName='string',
          VpcSecurityGroupIds=[
              'string',
          ],
          DBSubnetGroupName='string',
          Engine='string',
          EngineVersion='string',
          Port=123,
          MasterUsername='string',
          MasterUserPassword='string',
          OptionGroupName='string',
          PreferredBackupWindow='string',
          PreferredMaintenanceWindow='string',
          ReplicationSourceIdentifier='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          StorageEncrypted=True|False,
          KmsKeyId='string'
      )
    :type AvailabilityZones: list
    :param AvailabilityZones: 

      A list of EC2 Availability Zones that instances in the DB cluster can be created in. For information on regions and Availability Zones, see `Regions and Availability Zones`_ . 

      

    
      - *(string) --* 

      
  
    :type BackupRetentionPeriod: integer
    :param BackupRetentionPeriod: 

      The number of days for which automated backups are retained. You must specify a minimum value of 1.

       

      Default: 1

       

      Constraints:

       

       
      * Must be a value from 1 to 35 
       

      

    
    :type CharacterSetName: string
    :param CharacterSetName: 

      A value that indicates that the DB cluster should be associated with the specified CharacterSet.

      

    
    :type DatabaseName: string
    :param DatabaseName: 

      The name for your database of up to 8 alpha-numeric characters. If you do not provide a name, Amazon RDS will not create a database in the DB cluster you are creating.

      

    
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: **[REQUIRED]** 

      The DB cluster identifier. This parameter is stored as a lowercase string.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

       

      Example: ``my-cluster1``  

      

    
    :type DBClusterParameterGroupName: string
    :param DBClusterParameterGroupName: 

      The name of the DB cluster parameter group to associate with this DB cluster. If this argument is omitted, ``default.aurora5.6`` will be used. 

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type VpcSecurityGroupIds: list
    :param VpcSecurityGroupIds: 

      A list of EC2 VPC security groups to associate with this DB cluster.

      

    
      - *(string) --* 

      
  
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      A DB subnet group to associate with this DB cluster.

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    :type Engine: string
    :param Engine: **[REQUIRED]** 

      The name of the database engine to be used for this DB cluster.

       

      Valid Values: ``aurora``  

      

    
    :type EngineVersion: string
    :param EngineVersion: 

      The version number of the database engine to use.

       

       **Aurora**  

       

      Example: ``5.6.10a``  

      

    
    :type Port: integer
    :param Port: 

      The port number on which the instances in the DB cluster accept connections.

       

      Default: ``3306``  

      

    
    :type MasterUsername: string
    :param MasterUsername: 

      The name of the master user for the DB cluster.

       

      Constraints:

       

       
      * Must be 1 to 16 alphanumeric characters. 
       
      * First character must be a letter. 
       
      * Cannot be a reserved word for the chosen database engine. 
       

      

    
    :type MasterUserPassword: string
    :param MasterUserPassword: 

      The password for the master database user. This password can contain any printable ASCII character except "/", """, or "@".

       

      Constraints: Must contain from 8 to 41 characters.

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      A value that indicates that the DB cluster should be associated with the specified option group.

       

      Permanent options cannot be removed from an option group. The option group cannot be removed from a DB cluster once it is associated with a DB cluster.

      

    
    :type PreferredBackupWindow: string
    :param PreferredBackupWindow: 

      The daily time range during which automated backups are created if automated backups are enabled using the ``BackupRetentionPeriod`` parameter. 

       

      Default: A 30-minute window selected at random from an 8-hour block of time per region. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

       

      Constraints:

       

       
      * Must be in the format ``hh24:mi-hh24:mi`` . 
       
      * Times should be in Universal Coordinated Time (UTC). 
       
      * Must not conflict with the preferred maintenance window. 
       
      * Must be at least 30 minutes. 
       

      

    
    :type PreferredMaintenanceWindow: string
    :param PreferredMaintenanceWindow: 

      The weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

       

      Format: ``ddd:hh24:mi-ddd:hh24:mi``  

       

      Default: A 30-minute window selected at random from an 8-hour block of time per region, occurring on a random day of the week. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

       

      Valid Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun

       

      Constraints: Minimum 30-minute window.

      

    
    :type ReplicationSourceIdentifier: string
    :param ReplicationSourceIdentifier: 

      The Amazon Resource Name (ARN) of the source DB cluster if this DB cluster is created as a Read Replica.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    :type StorageEncrypted: boolean
    :param StorageEncrypted: 

      Specifies whether the DB cluster is encrypted.

      

    
    :type KmsKeyId: string
    :param KmsKeyId: 

      The KMS key identifier for an encrypted DB cluster.

       

      The KMS key identifier is the Amazon Resource Name (ARN) for the KMS encryption key. If you are creating a DB cluster with the same AWS account that owns the KMS encryption key used to encrypt the new DB cluster, then you can use the KMS key alias instead of the ARN for the KM encryption key.

       

      If the ``StorageEncrypted`` parameter is true, and you do not specify a value for the ``KmsKeyId`` parameter, then Amazon RDS will use your default encryption key. AWS KMS creates the default encryption key for your AWS account. Your AWS account has a different default encryption key for each AWS region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBCluster': {
                'AllocatedStorage': 123,
                'AvailabilityZones': [
                    'string',
                ],
                'BackupRetentionPeriod': 123,
                'CharacterSetName': 'string',
                'DatabaseName': 'string',
                'DBClusterIdentifier': 'string',
                'DBClusterParameterGroup': 'string',
                'DBSubnetGroup': 'string',
                'Status': 'string',
                'PercentProgress': 'string',
                'EarliestRestorableTime': datetime(2015, 1, 1),
                'Endpoint': 'string',
                'Engine': 'string',
                'EngineVersion': 'string',
                'LatestRestorableTime': datetime(2015, 1, 1),
                'Port': 123,
                'MasterUsername': 'string',
                'DBClusterOptionGroupMemberships': [
                    {
                        'DBClusterOptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'PreferredBackupWindow': 'string',
                'PreferredMaintenanceWindow': 'string',
                'ReplicationSourceIdentifier': 'string',
                'ReadReplicaIdentifiers': [
                    'string',
                ],
                'DBClusterMembers': [
                    {
                        'DBInstanceIdentifier': 'string',
                        'IsClusterWriter': True|False,
                        'DBClusterParameterGroupStatus': 'string',
                        'PromotionTier': 123
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'HostedZoneId': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbClusterResourceId': 'string',
                'DBClusterArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBCluster** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBCluster   
           
          *  DeleteDBCluster   
           
          *  FailoverDBCluster   
           
          *  ModifyDBCluster   
           
          *  RestoreDBClusterFromSnapshot   
           
          *  RestoreDBClusterToPointInTime   
           

           

          This data type is used as a response element in the  DescribeDBClusters action.

          
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

            
            

            - *(string) --* 
        
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this cluster is associated with.

            
          

          - **DatabaseName** *(string) --* 

            Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster.

            
          

          - **DBClusterParameterGroup** *(string) --* 

            Specifies the name of the DB cluster parameter group for the DB cluster.

            
          

          - **DBSubnetGroup** *(string) --* 

            Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group.

            
          

          - **Status** *(string) --* 

            Specifies the current state of this DB cluster.

            
          

          - **PercentProgress** *(string) --* 

            Specifies the progress of the operation as a percentage.

            
          

          - **EarliestRestorableTime** *(datetime) --* 

            Specifies the earliest time to which a database can be restored with point-in-time restore.

            
          

          - **Endpoint** *(string) --* 

            Specifies the connection endpoint for the primary instance of the DB cluster.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB cluster.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine is listening on.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB cluster.

            
          

          - **DBClusterOptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB cluster.

            
            

            - *(dict) --* 

              Contains status information for a DB cluster option group.

              
              

              - **DBClusterOptionGroupName** *(string) --* 

                Specifies the name of the DB cluster option group.

                
              

              - **Status** *(string) --* 

                Specifies the status of the DB cluster option group.

                
          
        
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **ReplicationSourceIdentifier** *(string) --* 

            Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

            
          

          - **ReadReplicaIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB cluster.

            
            

            - *(string) --* 
        
          

          - **DBClusterMembers** *(list) --* 

            Provides the list of instances that make up the DB cluster.

            
            

            - *(dict) --* 

              Contains information about an instance that is part of a DB cluster.

              
              

              - **DBInstanceIdentifier** *(string) --* 

                Specifies the instance identifier for this member of the DB cluster.

                
              

              - **IsClusterWriter** *(boolean) --* 

                Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

                
              

              - **DBClusterParameterGroupStatus** *(string) --* 

                Specifies the status of the DB cluster parameter group for this member of the DB cluster.

                
              

              - **PromotionTier** *(integer) --* 

                A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides a list of VPC security groups that the DB cluster belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **HostedZoneId** *(string) --* 

            Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

            
          

          - **DbClusterResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed.

            
          

          - **DBClusterArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster.

            
      
    

  .. py:method:: create_db_cluster_parameter_group(**kwargs)

    

    Creates a new DB cluster parameter group.

     

    Parameters in a DB cluster parameter group apply to all of the instances in a DB cluster.

     

    A DB cluster parameter group is initially created with the default parameters for the database engine used by instances in the DB cluster. To provide custom values for any of the parameters, you must modify the group after creating it using  ModifyDBClusterParameterGroup . Once you've created a DB cluster parameter group, you need to associate it with your DB cluster using  ModifyDBCluster . When you associate a new DB cluster parameter group with a running DB cluster, you need to reboot the DB instances in the DB cluster without failover for the new DB cluster parameter group and associated settings to take effect. 

     

    .. warning::

       

      After you create a DB cluster parameter group, you should wait at least 5 minutes before creating your first DB cluster that uses that DB cluster parameter group as the default parameter group. This allows Amazon RDS to fully complete the create action before the DB cluster parameter group is used as the default for a new DB cluster. This is especially important for parameters that are critical when creating the default database for a DB cluster, such as the character set for the default database defined by the ``character_set_database`` parameter. You can use the *Parameter Groups* option of the `Amazon RDS console`_ or the  DescribeDBClusterParameters command to verify that your DB cluster parameter group has been created or modified.

       

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.create_db_cluster_parameter_group(
          DBClusterParameterGroupName='string',
          DBParameterGroupFamily='string',
          Description='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type DBClusterParameterGroupName: string
    :param DBClusterParameterGroupName: **[REQUIRED]** 

      The name of the DB cluster parameter group.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      .. note::

         

        This value is stored as a lowercase string.

         

      

    
    :type DBParameterGroupFamily: string
    :param DBParameterGroupFamily: **[REQUIRED]** 

      The DB cluster parameter group family name. A DB cluster parameter group can be associated with one and only one DB cluster parameter group family, and can be applied only to a DB cluster running a database engine and engine version compatible with that DB cluster parameter group family.

      

    
    :type Description: string
    :param Description: **[REQUIRED]** 

      The description for the DB cluster parameter group.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBClusterParameterGroup': {
                'DBClusterParameterGroupName': 'string',
                'DBParameterGroupFamily': 'string',
                'Description': 'string',
                'DBClusterParameterGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBClusterParameterGroup** *(dict) --* 

          Contains the result of a successful invocation of the  CreateDBClusterParameterGroup or  CopyDBClusterParameterGroup action. 

           

          This data type is used as a request parameter in the  DeleteDBClusterParameterGroup action, and as a response element in the  DescribeDBClusterParameterGroups action. 

          
          

          - **DBClusterParameterGroupName** *(string) --* 

            Provides the name of the DB cluster parameter group.

            
          

          - **DBParameterGroupFamily** *(string) --* 

            Provides the name of the DB parameter group family that this DB cluster parameter group is compatible with.

            
          

          - **Description** *(string) --* 

            Provides the customer-specified description for this DB cluster parameter group.

            
          

          - **DBClusterParameterGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster parameter group.

            
      
    

  .. py:method:: create_db_cluster_snapshot(**kwargs)

    

    Creates a snapshot of a DB cluster. For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.create_db_cluster_snapshot(
          DBClusterSnapshotIdentifier='string',
          DBClusterIdentifier='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type DBClusterSnapshotIdentifier: string
    :param DBClusterSnapshotIdentifier: **[REQUIRED]** 

      The identifier of the DB cluster snapshot. This parameter is stored as a lowercase string.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

       

      Example: ``my-cluster1-snapshot1``  

      

    
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: **[REQUIRED]** 

      The identifier of the DB cluster to create a snapshot for. This parameter is not case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

       

      Example: ``my-cluster1``  

      

    
    :type Tags: list
    :param Tags: 

      The tags to be assigned to the DB cluster snapshot.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBClusterSnapshot': {
                'AvailabilityZones': [
                    'string',
                ],
                'DBClusterSnapshotIdentifier': 'string',
                'DBClusterIdentifier': 'string',
                'SnapshotCreateTime': datetime(2015, 1, 1),
                'Engine': 'string',
                'AllocatedStorage': 123,
                'Status': 'string',
                'Port': 123,
                'VpcId': 'string',
                'ClusterCreateTime': datetime(2015, 1, 1),
                'MasterUsername': 'string',
                'EngineVersion': 'string',
                'LicenseModel': 'string',
                'SnapshotType': 'string',
                'PercentProgress': 123,
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DBClusterSnapshotArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBClusterSnapshot** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBClusterSnapshot   
           
          *  DeleteDBClusterSnapshot   
           

           

          This data type is used as a response element in the  DescribeDBClusterSnapshots action.

          
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster snapshot can be restored in.

            
            

            - *(string) --* 
        
          

          - **DBClusterSnapshotIdentifier** *(string) --* 

            Specifies the identifier for the DB cluster snapshot.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Specifies the DB cluster identifier of the DB cluster that this DB cluster snapshot was created from.

            
          

          - **SnapshotCreateTime** *(datetime) --* 

            Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

            
          

          - **Engine** *(string) --* 

            Specifies the name of the database engine.

            
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **Status** *(string) --* 

            Specifies the status of this DB cluster snapshot.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the DB cluster was listening on at the time of the snapshot.

            
          

          - **VpcId** *(string) --* 

            Provides the VPC ID associated with the DB cluster snapshot.

            
          

          - **ClusterCreateTime** *(datetime) --* 

            Specifies the time when the DB cluster was created, in Universal Coordinated Time (UTC).

            
          

          - **MasterUsername** *(string) --* 

            Provides the master username for the DB cluster snapshot.

            
          

          - **EngineVersion** *(string) --* 

            Provides the version of the database engine for this DB cluster snapshot.

            
          

          - **LicenseModel** *(string) --* 

            Provides the license model information for this DB cluster snapshot.

            
          

          - **SnapshotType** *(string) --* 

            Provides the type of the DB cluster snapshot.

            
          

          - **PercentProgress** *(integer) --* 

            Specifies the percentage of the estimated data that has been transferred.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster snapshot is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster snapshot.

            
          

          - **DBClusterSnapshotArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster snapshot.

            
      
    

  .. py:method:: create_db_instance(**kwargs)

    

    Creates a new DB instance.

    

    **Request Syntax** 
    ::

      response = client.create_db_instance(
          DBName='string',
          DBInstanceIdentifier='string',
          AllocatedStorage=123,
          DBInstanceClass='string',
          Engine='string',
          MasterUsername='string',
          MasterUserPassword='string',
          DBSecurityGroups=[
              'string',
          ],
          VpcSecurityGroupIds=[
              'string',
          ],
          AvailabilityZone='string',
          DBSubnetGroupName='string',
          PreferredMaintenanceWindow='string',
          DBParameterGroupName='string',
          BackupRetentionPeriod=123,
          PreferredBackupWindow='string',
          Port=123,
          MultiAZ=True|False,
          EngineVersion='string',
          AutoMinorVersionUpgrade=True|False,
          LicenseModel='string',
          Iops=123,
          OptionGroupName='string',
          CharacterSetName='string',
          PubliclyAccessible=True|False,
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          DBClusterIdentifier='string',
          StorageType='string',
          TdeCredentialArn='string',
          TdeCredentialPassword='string',
          StorageEncrypted=True|False,
          KmsKeyId='string',
          Domain='string',
          CopyTagsToSnapshot=True|False,
          MonitoringInterval=123,
          MonitoringRoleArn='string',
          DomainIAMRoleName='string',
          PromotionTier=123
      )
    :type DBName: string
    :param DBName: 

      The meaning of this parameter differs according to the database engine you use.

       

      Type: String

       

       **MySQL**  

       

      The name of the database to create when the DB instance is created. If this parameter is not specified, no database is created in the DB instance.

       

      Constraints:

       

       
      * Must contain 1 to 64 alphanumeric characters 
       
      * Cannot be a word reserved by the specified database engine 
       

       

       **MariaDB**  

       

      The name of the database to create when the DB instance is created. If this parameter is not specified, no database is created in the DB instance.

       

      Constraints:

       

       
      * Must contain 1 to 64 alphanumeric characters 
       
      * Cannot be a word reserved by the specified database engine 
       

       

       **PostgreSQL**  

       

      The name of the database to create when the DB instance is created. If this parameter is not specified, the default "postgres" database is created in the DB instance.

       

      Constraints:

       

       
      * Must contain 1 to 63 alphanumeric characters 
       
      * Must begin with a letter or an underscore. Subsequent characters can be letters, underscores, or digits (0-9). 
       
      * Cannot be a word reserved by the specified database engine 
       

       

       **Oracle**  

       

      The Oracle System ID (SID) of the created DB instance.

       

      Default: ``ORCL``  

       

      Constraints:

       

       
      * Cannot be longer than 8 characters 
       

       

       **SQL Server**  

       

      Not applicable. Must be null.

       

       **Amazon Aurora**  

       

      The name of the database to create when the primary instance of the DB cluster is created. If this parameter is not specified, no database is created in the DB instance.

       

      Constraints:

       

       
      * Must contain 1 to 64 alphanumeric characters 
       
      * Cannot be a word reserved by the specified database engine 
       

      

    
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The DB instance identifier. This parameter is stored as a lowercase string.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens (1 to 15 for SQL Server). 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

       

      Example: ``mydbinstance``  

      

    
    :type AllocatedStorage: integer
    :param AllocatedStorage: 

      The amount of storage (in gigabytes) to be initially allocated for the database instance.

       

      Type: Integer

       

       **MySQL**  

       

      Constraints: Must be an integer from 5 to 6144.

       

       **MariaDB**  

       

      Constraints: Must be an integer from 5 to 6144.

       

       **PostgreSQL**  

       

      Constraints: Must be an integer from 5 to 6144.

       

       **Oracle**  

       

      Constraints: Must be an integer from 10 to 6144.

       

       **SQL Server**  

       

      Constraints: Must be an integer from 200 to 4096 (Standard Edition and Enterprise Edition) or from 20 to 4096 (Express Edition and Web Edition)

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: **[REQUIRED]** 

      The compute and memory capacity of the DB instance.

       

      Valid Values: ``db.t1.micro | db.m1.small | db.m1.medium | db.m1.large | db.m1.xlarge | db.m2.xlarge |db.m2.2xlarge | db.m2.4xlarge | db.m3.medium | db.m3.large | db.m3.xlarge | db.m3.2xlarge | db.m4.large | db.m4.xlarge | db.m4.2xlarge | db.m4.4xlarge | db.m4.10xlarge | db.r3.large | db.r3.xlarge | db.r3.2xlarge | db.r3.4xlarge | db.r3.8xlarge | db.t2.micro | db.t2.small | db.t2.medium | db.t2.large``  

      

    
    :type Engine: string
    :param Engine: **[REQUIRED]** 

      The name of the database engine to be used for this instance.

       

      Valid Values: ``MySQL`` | ``mariadb`` | ``oracle-se1`` | ``oracle-se`` | ``oracle-ee`` | ``sqlserver-ee`` | ``sqlserver-se`` | ``sqlserver-ex`` | ``sqlserver-web`` | ``postgres`` | ``aurora``  

       

      Not every database engine is available for every AWS region.

      

    
    :type MasterUsername: string
    :param MasterUsername: 

      The name of master user for the client DB instance.

       

       **MySQL**  

       

      Constraints:

       

       
      * Must be 1 to 16 alphanumeric characters. 
       
      * First character must be a letter. 
       
      * Cannot be a reserved word for the chosen database engine. 
       

       

       **MariaDB**  

       

      Constraints:

       

       
      * Must be 1 to 16 alphanumeric characters. 
       
      * Cannot be a reserved word for the chosen database engine. 
       

       

      Type: String

       

       **Oracle**  

       

      Constraints:

       

       
      * Must be 1 to 30 alphanumeric characters. 
       
      * First character must be a letter. 
       
      * Cannot be a reserved word for the chosen database engine. 
       

       

       **SQL Server**  

       

      Constraints:

       

       
      * Must be 1 to 128 alphanumeric characters. 
       
      * First character must be a letter. 
       
      * Cannot be a reserved word for the chosen database engine. 
       

       

       **PostgreSQL**  

       

      Constraints:

       

       
      * Must be 1 to 63 alphanumeric characters. 
       
      * First character must be a letter. 
       
      * Cannot be a reserved word for the chosen database engine. 
       

      

    
    :type MasterUserPassword: string
    :param MasterUserPassword: 

      The password for the master database user. Can be any printable ASCII character except "/", """, or "@".

       

      Type: String

       

       **MySQL**  

       

      Constraints: Must contain from 8 to 41 characters.

       

       **MariaDB**  

       

      Constraints: Must contain from 8 to 41 characters.

       

       **Oracle**  

       

      Constraints: Must contain from 8 to 30 characters.

       

       **SQL Server**  

       

      Constraints: Must contain from 8 to 128 characters.

       

       **PostgreSQL**  

       

      Constraints: Must contain from 8 to 128 characters.

       

       **Amazon Aurora**  

       

      Constraints: Must contain from 8 to 41 characters.

      

    
    :type DBSecurityGroups: list
    :param DBSecurityGroups: 

      A list of DB security groups to associate with this DB instance.

       

      Default: The default DB security group for the database engine.

      

    
      - *(string) --* 

      
  
    :type VpcSecurityGroupIds: list
    :param VpcSecurityGroupIds: 

      A list of EC2 VPC security groups to associate with this DB instance.

       

      Default: The default EC2 VPC security group for the DB subnet group's VPC.

      

    
      - *(string) --* 

      
  
    :type AvailabilityZone: string
    :param AvailabilityZone: 

      The EC2 Availability Zone that the database instance will be created in. For information on regions and Availability Zones, see `Regions and Availability Zones`_ . 

       

      Default: A random, system-chosen Availability Zone in the endpoint's region.

       

      Example: ``us-east-1d``  

       

      Constraint: The AvailabilityZone parameter cannot be specified if the MultiAZ parameter is set to ``true`` . The specified Availability Zone must be in the same region as the current endpoint. 

      

    
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      A DB subnet group to associate with this DB instance.

       

      If there is no DB subnet group, then it is a non-VPC DB instance.

      

    
    :type PreferredMaintenanceWindow: string
    :param PreferredMaintenanceWindow: 

      The weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC). For more information, see `DB Instance Maintenance`_ . 

       

      Format: ``ddd:hh24:mi-ddd:hh24:mi``  

       

      Default: A 30-minute window selected at random from an 8-hour block of time per region, occurring on a random day of the week. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

       

      Valid Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun

       

      Constraints: Minimum 30-minute window.

      

    
    :type DBParameterGroupName: string
    :param DBParameterGroupName: 

      The name of the DB parameter group to associate with this DB instance. If this argument is omitted, the default DBParameterGroup for the specified engine will be used.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type BackupRetentionPeriod: integer
    :param BackupRetentionPeriod: 

      The number of days for which automated backups are retained. Setting this parameter to a positive number enables backups. Setting this parameter to 0 disables automated backups.

       

      Default: 1

       

      Constraints:

       

       
      * Must be a value from 0 to 35 
       
      * Cannot be set to 0 if the DB instance is a source to Read Replicas 
       

      

    
    :type PreferredBackupWindow: string
    :param PreferredBackupWindow: 

      The daily time range during which automated backups are created if automated backups are enabled, using the ``BackupRetentionPeriod`` parameter. For more information, see `DB Instance Backups`_ . 

       

      Default: A 30-minute window selected at random from an 8-hour block of time per region. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

       

      Constraints:

       

       
      * Must be in the format ``hh24:mi-hh24:mi`` . 
       
      * Times should be in Universal Coordinated Time (UTC). 
       
      * Must not conflict with the preferred maintenance window. 
       
      * Must be at least 30 minutes. 
       

      

    
    :type Port: integer
    :param Port: 

      The port number on which the database accepts connections.

       

       **MySQL**  

       

      Default: ``3306``  

       

      Valid Values: ``1150-65535``  

       

      Type: Integer

       

       **MariaDB**  

       

      Default: ``3306``  

       

      Valid Values: ``1150-65535``  

       

      Type: Integer

       

       **PostgreSQL**  

       

      Default: ``5432``  

       

      Valid Values: ``1150-65535``  

       

      Type: Integer

       

       **Oracle**  

       

      Default: ``1521``  

       

      Valid Values: ``1150-65535``  

       

       **SQL Server**  

       

      Default: ``1433``  

       

      Valid Values: ``1150-65535`` except for ``1434`` , ``3389`` , ``47001`` , ``49152`` , and ``49152`` through ``49156`` . 

       

       **Amazon Aurora**  

       

      Default: ``3306``  

       

      Valid Values: ``1150-65535``  

       

      Type: Integer

      

    
    :type MultiAZ: boolean
    :param MultiAZ: 

      Specifies if the DB instance is a Multi-AZ deployment. You cannot set the AvailabilityZone parameter if the MultiAZ parameter is set to true.

      

    
    :type EngineVersion: string
    :param EngineVersion: 

      The version number of the database engine to use.

       

      The following are the database engines and major and minor versions that are available with Amazon RDS. Not every database engine is available for every AWS region.

       

       **Amazon Aurora**  

       

       
      * **Version 5.6 (only available in AWS regions ap-northeast-1, ap-northeast-2, ap-south-1, ap-southeast-2, eu-west-1, us-east-1, us-west-2):**  ``5.6.10a``   
       

       

       **MariaDB**  

       

       
      * **Version 10.1 (available in all AWS regions except us-gov-west-1):**  ``10.1.14``   
       
      * **Version 10.0 (available in all AWS regions):**  ``10.0.17 | 10.0.24``   
       

       

       **Microsoft SQL Server Enterprise Edition (sqlserver-ee)**  

       

       
      * **Version 11.00 (available in all AWS regions):**  ``11.00.2100.60.v1 | 11.00.5058.0.v1 | 11.00.6020.0.v1``   
       
      * **Version 10.50 (available in all AWS regions):**  ``10.50.2789.0.v1 | 10.50.6000.34.v1 | 10.50.6529.0.v1``   
       

       

       **Microsoft SQL Server Express Edition (sqlserver-ex)**  

       

       
      * **Version 12.00 (available in all AWS regions):**  ``12.00.4422.0.v1``   
       
      * **Version 11.00 (available in all AWS regions):**  ``11.00.2100.60.v1 | 11.00.5058.0.v1 | 11.00.6020.0.v1``   
       
      * **Version 10.50 (available in all AWS regions):**  ``10.50.2789.0.v1 | 10.50.6000.34.v1 | 10.50.6529.0.v1``   
       

       

       **Microsoft SQL Server Standard Edition (sqlserver-se)**  

       

       
      * **Version 12.00 (available in all AWS regions):**  ``12.00.4422.0.v1``   
       
      * **Version 11.00 (available in all AWS regions):**  ``11.00.2100.60.v1 | 11.00.5058.0.v1 | 11.00.6020.0.v1``   
       
      * **Version 10.50 (available in all AWS regions):**  ``10.50.2789.0.v1 | 10.50.6000.34.v1 | 10.50.6529.0.v1``   
       

       

       **Microsoft SQL Server Web Edition (sqlserver-web)**  

       

       
      * **Version 12.00 (available in all AWS regions):**  ``12.00.4422.0.v1``   
       
      * **Version 11.00 (available in all AWS regions):**  ``11.00.2100.60.v1 | 11.00.5058.0.v1 | 11.00.6020.0.v1``   
       
      * **Version 10.50 (available in all AWS regions):**  ``10.50.2789.0.v1 | 10.50.6000.34.v1 | 10.50.6529.0.v1``   
       

       

       **MySQL**  

       

       
      * **Version 5.7 (available in all AWS regions):**  ``5.7.10 | 5.7.11``   
       
      * **Version 5.6 (available in all AWS regions except ap-south-1, ap-northeast-2):**  ``5.6.19a | 5.6.19b | 5.6.21 | 5.6.21b | 5.6.22``   
       
      * **Version 5.6 (available in all AWS regions except ap-south-1):**  ``5.6.23``   
       
      * **Version 5.6 (available in all AWS regions):**  ``5.6.27 | 5.6.29``   
       
      * **Version 5.5 (only available in AWS regions ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-west-1, sa-east-1, us-east-1, us-gov-west-1, us-west-1, us-west-2):**  ``5.5.40 | 5.5.40a``   
       
      * **Version 5.5 (available in all AWS regions except ap-south-1, ap-northeast-2):**  ``5.5.40b | 5.5.41``   
       
      * **Version 5.5 (available in all AWS regions except ap-south-1):**  ``5.5.42``   
       
      * **Version 5.5 (available in all AWS regions):**  ``5.5.46``   
       

       

       **Oracle Database Enterprise Edition (oracle-ee)**  

       

       
      * **Version 12.1 (available in all AWS regions except ap-south-1, ap-northeast-2):**  ``12.1.0.1.v1 | 12.1.0.1.v2``   
       
      * **Version 12.1 (only available in AWS regions ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-central-1, eu-west-1, sa-east-1, us-east-1, us-west-1, us-west-2):**  ``12.1.0.1.v3 | 12.1.0.1.v4 | 12.1.0.1.v5``   
       
      * **Version 12.1 (available in all AWS regions):**  ``12.1.0.2.v1``   
       
      * **Version 12.1 (available in all AWS regions except us-gov-west-1):**  ``12.1.0.2.v2 | 12.1.0.2.v3 | 12.1.0.2.v4``   
       
      * **Version 11.2 (available in all AWS regions):**  ``11.2.0.4.v1 | 11.2.0.4.v3 | 11.2.0.4.v4``   
       
      * **Version 11.2 (available in all AWS regions except us-gov-west-1):**  ``11.2.0.4.v5 | 11.2.0.4.v6 | 11.2.0.4.v7 | 11.2.0.4.v8``   
       

       

       **Oracle Database Standard Edition (oracle-se)**  

       

       
      * **Version 12.1 (available in all AWS regions except ap-south-1, ap-northeast-2):**  ``12.1.0.1.v1 | 12.1.0.1.v2``   
       
      * **Version 12.1 (only available in AWS regions ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-central-1, eu-west-1, sa-east-1, us-east-1, us-west-1, us-west-2):**  ``12.1.0.1.v3 | 12.1.0.1.v4 | 12.1.0.1.v5``   
       
      * **Version 11.2 (available in all AWS regions):**  ``11.2.0.4.v1 | 11.2.0.4.v3 | 11.2.0.4.v4``   
       
      * **Version 11.2 (available in all AWS regions except us-gov-west-1):**  ``11.2.0.4.v5 | 11.2.0.4.v6 | 11.2.0.4.v7 | 11.2.0.4.v8``   
       

       

       **Oracle Database Standard Edition One (oracle-se1)**  

       

       
      * **Version 12.1 (available in all AWS regions except ap-south-1, ap-northeast-2):**  ``12.1.0.1.v1 | 12.1.0.1.v2``   
       
      * **Version 12.1 (only available in AWS regions ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-central-1, eu-west-1, sa-east-1, us-east-1, us-west-1, us-west-2):**  ``12.1.0.1.v3 | 12.1.0.1.v4 | 12.1.0.1.v5``   
       
      * **Version 11.2 (available in all AWS regions):**  ``11.2.0.4.v1 | 11.2.0.4.v3 | 11.2.0.4.v4``   
       
      * **Version 11.2 (available in all AWS regions except us-gov-west-1):**  ``11.2.0.4.v5 | 11.2.0.4.v6 | 11.2.0.4.v7 | 11.2.0.4.v8``   
       

       

       **Oracle Database Standard Edition Two (oracle-se2)**  

       

       
      * **Version 12.1 (available in all AWS regions except us-gov-west-1):**  ``12.1.0.2.v2 | 12.1.0.2.v3 | 12.1.0.2.v4``   
       

       

       **PostgreSQL**  

       

       
      * **Version 9.5 (available in all AWS regions except us-gov-west-1):**  ``9.5.2``   
       
      * **Version 9.4 (available in all AWS regions except ap-south-1):**  ``9.4.1 | 9.4.4``   
       
      * **Version 9.4 (available in all AWS regions):**  ``9.4.5``   
       
      * **Version 9.4 (available in all AWS regions except us-gov-west-1):**  ``9.4.7``   
       
      * **Version 9.3 (only available in AWS regions ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-west-1, sa-east-1, us-east-1, us-gov-west-1, us-west-1, us-west-2):**  ``9.3.1 | 9.3.2``   
       
      * **Version 9.3 (available in all AWS regions except ap-south-1, ap-northeast-2):**  ``9.3.10 | 9.3.3 | 9.3.5 | 9.3.6 | 9.3.9``   
       
      * **Version 9.3 (only available in AWS regions ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-central-1, eu-west-1, sa-east-1, us-east-1, us-west-1, us-west-2):**  ``9.3.12``   
       

      

    
    :type AutoMinorVersionUpgrade: boolean
    :param AutoMinorVersionUpgrade: 

      Indicates that minor engine upgrades will be applied automatically to the DB instance during the maintenance window.

       

      Default: ``true``  

      

    
    :type LicenseModel: string
    :param LicenseModel: 

      License model information for this DB instance.

       

      Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

      

    
    :type Iops: integer
    :param Iops: 

      The amount of Provisioned IOPS (input/output operations per second) to be initially allocated for the DB instance.

       

      Constraints: Must be a multiple between 3 and 10 of the storage amount for the DB instance. Must also be an integer multiple of 1000. For example, if the size of your DB instance is 500 GB, then your ``Iops`` value can be 2000, 3000, 4000, or 5000. 

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      Indicates that the DB instance should be associated with the specified option group.

       

      Permanent options, such as the TDE option for Oracle Advanced Security TDE, cannot be removed from an option group, and that option group cannot be removed from a DB instance once it is associated with a DB instance

      

    
    :type CharacterSetName: string
    :param CharacterSetName: 

      For supported engines, indicates that the DB instance should be associated with the specified CharacterSet.

      

    
    :type PubliclyAccessible: boolean
    :param PubliclyAccessible: 

      Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

       

      Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

       

       
      * **Default VPC:** true 
       
      * **VPC:** false 
       

       

      If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: 

      The identifier of the DB cluster that the instance will belong to.

       

      For information on creating a DB cluster, see  CreateDBCluster .

       

      Type: String

      

    
    :type StorageType: string
    :param StorageType: 

      Specifies the storage type to be associated with the DB instance.

       

      Valid values: ``standard | gp2 | io1``  

       

      If you specify ``io1`` , you must also include a value for the ``Iops`` parameter. 

       

      Default: ``io1`` if the ``Iops`` parameter is specified; otherwise ``standard``  

      

    
    :type TdeCredentialArn: string
    :param TdeCredentialArn: 

      The ARN from the Key Store with which to associate the instance for TDE encryption.

      

    
    :type TdeCredentialPassword: string
    :param TdeCredentialPassword: 

      The password for the given ARN from the Key Store in order to access the device.

      

    
    :type StorageEncrypted: boolean
    :param StorageEncrypted: 

      Specifies whether the DB instance is encrypted.

       

      Default: false

      

    
    :type KmsKeyId: string
    :param KmsKeyId: 

      The KMS key identifier for an encrypted DB instance.

       

      The KMS key identifier is the Amazon Resource Name (ARN) for the KMS encryption key. If you are creating a DB instance with the same AWS account that owns the KMS encryption key used to encrypt the new DB instance, then you can use the KMS key alias instead of the ARN for the KM encryption key.

       

      If the ``StorageEncrypted`` parameter is true, and you do not specify a value for the ``KmsKeyId`` parameter, then Amazon RDS will use your default encryption key. AWS KMS creates the default encryption key for your AWS account. Your AWS account has a different default encryption key for each AWS region.

      

    
    :type Domain: string
    :param Domain: 

      Specify the Active Directory Domain to create the instance in.

      

    
    :type CopyTagsToSnapshot: boolean
    :param CopyTagsToSnapshot: 

      True to copy all tags from the DB instance to snapshots of the DB instance; otherwise false. The default is false.

      

    
    :type MonitoringInterval: integer
    :param MonitoringInterval: 

      The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance. To disable collecting Enhanced Monitoring metrics, specify 0. The default is 0.

       

      If ``MonitoringRoleArn`` is specified, then you must also set ``MonitoringInterval`` to a value other than 0.

       

      Valid Values: ``0, 1, 5, 10, 15, 30, 60``  

      

    
    :type MonitoringRoleArn: string
    :param MonitoringRoleArn: 

      The ARN for the IAM role that permits RDS to send enhanced monitoring metrics to CloudWatch Logs. For example, ``arn:aws:iam:123456789012:role/emaccess`` . For information on creating a monitoring role, go to `To create an IAM role for Amazon RDS Enhanced Monitoring`_ .

       

      If ``MonitoringInterval`` is set to a value other than 0, then you must supply a ``MonitoringRoleArn`` value.

      

    
    :type DomainIAMRoleName: string
    :param DomainIAMRoleName: 

      Specify the name of the IAM role to be used when making API calls to the Directory Service.

      

    
    :type PromotionTier: integer
    :param PromotionTier: 

      A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

       

      Default: 1

       

      Valid Values: 0 - 15

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBInstance': {
                'DBInstanceIdentifier': 'string',
                'DBInstanceClass': 'string',
                'Engine': 'string',
                'DBInstanceStatus': 'string',
                'MasterUsername': 'string',
                'DBName': 'string',
                'Endpoint': {
                    'Address': 'string',
                    'Port': 123,
                    'HostedZoneId': 'string'
                },
                'AllocatedStorage': 123,
                'InstanceCreateTime': datetime(2015, 1, 1),
                'PreferredBackupWindow': 'string',
                'BackupRetentionPeriod': 123,
                'DBSecurityGroups': [
                    {
                        'DBSecurityGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'DBParameterGroups': [
                    {
                        'DBParameterGroupName': 'string',
                        'ParameterApplyStatus': 'string'
                    },
                ],
                'AvailabilityZone': 'string',
                'DBSubnetGroup': {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
                'PreferredMaintenanceWindow': 'string',
                'PendingModifiedValues': {
                    'DBInstanceClass': 'string',
                    'AllocatedStorage': 123,
                    'MasterUserPassword': 'string',
                    'Port': 123,
                    'BackupRetentionPeriod': 123,
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'DBInstanceIdentifier': 'string',
                    'StorageType': 'string',
                    'CACertificateIdentifier': 'string',
                    'DBSubnetGroupName': 'string'
                },
                'LatestRestorableTime': datetime(2015, 1, 1),
                'MultiAZ': True|False,
                'EngineVersion': 'string',
                'AutoMinorVersionUpgrade': True|False,
                'ReadReplicaSourceDBInstanceIdentifier': 'string',
                'ReadReplicaDBInstanceIdentifiers': [
                    'string',
                ],
                'LicenseModel': 'string',
                'Iops': 123,
                'OptionGroupMemberships': [
                    {
                        'OptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'CharacterSetName': 'string',
                'SecondaryAvailabilityZone': 'string',
                'PubliclyAccessible': True|False,
                'StatusInfos': [
                    {
                        'StatusType': 'string',
                        'Normal': True|False,
                        'Status': 'string',
                        'Message': 'string'
                    },
                ],
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'DbInstancePort': 123,
                'DBClusterIdentifier': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbiResourceId': 'string',
                'CACertificateIdentifier': 'string',
                'DomainMemberships': [
                    {
                        'Domain': 'string',
                        'Status': 'string',
                        'FQDN': 'string',
                        'IAMRoleName': 'string'
                    },
                ],
                'CopyTagsToSnapshot': True|False,
                'MonitoringInterval': 123,
                'EnhancedMonitoringResourceArn': 'string',
                'MonitoringRoleArn': 'string',
                'PromotionTier': 123,
                'DBInstanceArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBInstance** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBInstance   
           
          *  DeleteDBInstance   
           
          *  ModifyDBInstance   
           

           

          This data type is used as a response element in the  DescribeDBInstances action.

          
          

          - **DBInstanceIdentifier** *(string) --* 

            Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

            
          

          - **DBInstanceClass** *(string) --* 

            Contains the name of the compute and memory capacity class of the DB instance.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB instance.

            
          

          - **DBInstanceStatus** *(string) --* 

            Specifies the current state of this database.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB instance.

            
          

          - **DBName** *(string) --* 

            The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

             

             **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

             

            Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

             

            Type: String

             

             **Oracle**  

             

            Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

            
          

          - **Endpoint** *(dict) --* 

            Specifies the connection endpoint.

            
            

            - **Address** *(string) --* 

              Specifies the DNS address of the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine is listening on.

              
            

            - **HostedZoneId** *(string) --* 

              Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

              
        
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size specified in gigabytes.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Provides the date and time the DB instance was created.

            
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **DBSecurityGroups** *(list) --* 

            Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               
              *  RestoreDBInstanceToPointInTime   
               

              
              

              - **DBSecurityGroupName** *(string) --* 

                The name of the DB security group.

                
              

              - **Status** *(string) --* 

                The status of the DB security group.

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides List of VPC security group elements that the DB instance belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **DBParameterGroups** *(list) --* 

            Provides the list of DB parameter groups applied to this DB instance.

            
            

            - *(dict) --* 

              The status of the DB parameter group.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateDBInstance   
               
              *  CreateDBInstanceReadReplica   
               
              *  DeleteDBInstance   
               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               

              
              

              - **DBParameterGroupName** *(string) --* 

                The name of the DP parameter group.

                
              

              - **ParameterApplyStatus** *(string) --* 

                The status of parameter updates.

                
          
        
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance is located in.

            
          

          - **DBSubnetGroup** *(dict) --* 

            Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **PendingModifiedValues** *(dict) --* 

            Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

            
            

            - **DBInstanceClass** *(string) --* 

              Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

              
            

            - **AllocatedStorage** *(integer) --* 

              Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

              
            

            - **MasterUserPassword** *(string) --* 

              Contains the pending or in-progress change of the master credentials for the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the pending port for the DB instance.

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the pending number of days for which automated backups are retained.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the DB instance.

               

              Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

              
            

            - **Iops** *(integer) --* 

              Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type to be associated with the DB instance.

              
            

            - **CACertificateIdentifier** *(string) --* 

              Specifies the identifier of the CA certificate for the DB instance.

              
            

            - **DBSubnetGroupName** *(string) --* 

              The new DB subnet group for the DB instance. 

              
        
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **MultiAZ** *(boolean) --* 

            Specifies if the DB instance is a Multi-AZ deployment.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **AutoMinorVersionUpgrade** *(boolean) --* 

            Indicates that minor version patches are applied automatically.

            
          

          - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

            Contains the identifier of the source DB instance if this DB instance is a Read Replica.

            
          

          - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB instance.

            
            

            - *(string) --* 
        
          

          - **LicenseModel** *(string) --* 

            License model information for this DB instance.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value.

            
          

          - **OptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB instance.

            
            

            - *(dict) --* 

              Provides information on the option groups the DB instance is a member of.

              
              

              - **OptionGroupName** *(string) --* 

                The name of the option group that the instance belongs to.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                
          
        
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this instance is associated with.

            
          

          - **SecondaryAvailabilityZone** *(string) --* 

            If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

            
          

          - **PubliclyAccessible** *(boolean) --* 

            Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

             

            Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

             

             
            * **Default VPC:** true 
             
            * **VPC:** false 
             

             

            If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

            
          

          - **StatusInfos** *(list) --* 

            The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

            
            

            - *(dict) --* 

              Provides a list of status information for a DB instance.

              
              

              - **StatusType** *(string) --* 

                This value is currently "read replication."

                
              

              - **Normal** *(boolean) --* 

                Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                
              

              - **Status** *(string) --* 

                Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                
              

              - **Message** *(string) --* 

                Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                
          
        
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB instance.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which the instance is associated for TDE encryption.

            
          

          - **DbInstancePort** *(integer) --* 

            Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

            
          

          - **DBClusterIdentifier** *(string) --* 

            If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB instance is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

            
          

          - **DbiResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

            
          

          - **CACertificateIdentifier** *(string) --* 

            The identifier of the CA certificate for this DB instance.

            
          

          - **DomainMemberships** *(list) --* 

            The Active Directory Domain membership records associated with the DB instance.

            
            

            - *(dict) --* 

              An Active Directory Domain membership record associated with the DB instance.

              
              

              - **Domain** *(string) --* 

                The identifier of the Active Directory Domain.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                
              

              - **FQDN** *(string) --* 

                The fully qualified domain name of the Active Directory Domain.

                
              

              - **IAMRoleName** *(string) --* 

                The name of the IAM role to be used when making API calls to the Directory Service.

                
          
        
          

          - **CopyTagsToSnapshot** *(boolean) --* 

            Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

            
          

          - **MonitoringInterval** *(integer) --* 

            The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

            
          

          - **EnhancedMonitoringResourceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

            
          

          - **MonitoringRoleArn** *(string) --* 

            The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

            
          

          - **PromotionTier** *(integer) --* 

            A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

            
          

          - **DBInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB instance.

            
      
    

  .. py:method:: create_db_instance_read_replica(**kwargs)

    

    Creates a DB instance for a DB instance running MySQL, MariaDB, or PostgreSQL that acts as a Read Replica of a source DB instance.

     

    All Read Replica DB instances are created as Single-AZ deployments with backups disabled. All other DB instance attributes (including DB security groups and DB parameter groups) are inherited from the source DB instance, except as specified below.

     

    .. warning::

       

      The source DB instance must have backup retention enabled.

       

    

    **Request Syntax** 
    ::

      response = client.create_db_instance_read_replica(
          DBInstanceIdentifier='string',
          SourceDBInstanceIdentifier='string',
          DBInstanceClass='string',
          AvailabilityZone='string',
          Port=123,
          AutoMinorVersionUpgrade=True|False,
          Iops=123,
          OptionGroupName='string',
          PubliclyAccessible=True|False,
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          DBSubnetGroupName='string',
          StorageType='string',
          CopyTagsToSnapshot=True|False,
          MonitoringInterval=123,
          MonitoringRoleArn='string'
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The DB instance identifier of the Read Replica. This identifier is the unique key that identifies a DB instance. This parameter is stored as a lowercase string.

      

    
    :type SourceDBInstanceIdentifier: string
    :param SourceDBInstanceIdentifier: **[REQUIRED]** 

      The identifier of the DB instance that will act as the source for the Read Replica. Each DB instance can have up to five Read Replicas.

       

      Constraints:

       

       
      * Must be the identifier of an existing MySQL, MariaDB, or PostgreSQL DB instance. 
       
      * Can specify a DB instance that is a MySQL Read Replica only if the source is running MySQL 5.6. 
       
      * Can specify a DB instance that is a PostgreSQL Read Replica only if the source is running PostgreSQL 9.3.5. 
       
      * The specified DB instance must have automatic backups enabled, its backup retention period must be greater than 0. 
       
      * If the source DB instance is in the same region as the Read Replica, specify a valid DB instance identifier. 
       
      * If the source DB instance is in a different region than the Read Replica, specify a valid DB instance ARN. For more information, go to `Constructing a Amazon RDS Amazon Resource Name (ARN)`_ . 
       

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The compute and memory capacity of the Read Replica.

       

      Valid Values: ``db.m1.small | db.m1.medium | db.m1.large | db.m1.xlarge | db.m2.xlarge |db.m2.2xlarge | db.m2.4xlarge | db.m3.medium | db.m3.large | db.m3.xlarge | db.m3.2xlarge | db.m4.large | db.m4.xlarge | db.m4.2xlarge | db.m4.4xlarge | db.m4.10xlarge | db.r3.large | db.r3.xlarge | db.r3.2xlarge | db.r3.4xlarge | db.r3.8xlarge | db.t2.micro | db.t2.small | db.t2.medium | db.t2.large``  

       

      Default: Inherits from the source DB instance.

      

    
    :type AvailabilityZone: string
    :param AvailabilityZone: 

      The Amazon EC2 Availability Zone that the Read Replica will be created in.

       

      Default: A random, system-chosen Availability Zone in the endpoint's region.

       

      Example: ``us-east-1d``  

      

    
    :type Port: integer
    :param Port: 

      The port number that the DB instance uses for connections.

       

      Default: Inherits from the source DB instance

       

      Valid Values: ``1150-65535``  

      

    
    :type AutoMinorVersionUpgrade: boolean
    :param AutoMinorVersionUpgrade: 

      Indicates that minor engine upgrades will be applied automatically to the Read Replica during the maintenance window.

       

      Default: Inherits from the source DB instance

      

    
    :type Iops: integer
    :param Iops: 

      The amount of Provisioned IOPS (input/output operations per second) to be initially allocated for the DB instance.

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      The option group the DB instance will be associated with. If omitted, the default option group for the engine specified will be used.

      

    
    :type PubliclyAccessible: boolean
    :param PubliclyAccessible: 

      Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

       

      Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

       

       
      * **Default VPC:** true 
       
      * **VPC:** false 
       

       

      If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      Specifies a DB subnet group for the DB instance. The new DB instance will be created in the VPC associated with the DB subnet group. If no DB subnet group is specified, then the new DB instance is not created in a VPC.

       

      Constraints:

       

       
      * Can only be specified if the source DB instance identifier specifies a DB instance in another region. 
       
      * The specified DB subnet group must be in the same region in which the operation is running. 
       
      * All Read Replicas in one region that are created from the same source DB instance must either: 

         
        * Specify DB subnet groups from the same VPC. All these Read Replicas will be created in the same VPC. 
         
        * Not specify a DB subnet group. All these Read Replicas will be created outside of any VPC. 
         

       
       

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    :type StorageType: string
    :param StorageType: 

      Specifies the storage type to be associated with the Read Replica.

       

      Valid values: ``standard | gp2 | io1``  

       

      If you specify ``io1`` , you must also include a value for the ``Iops`` parameter. 

       

      Default: ``io1`` if the ``Iops`` parameter is specified; otherwise ``standard``  

      

    
    :type CopyTagsToSnapshot: boolean
    :param CopyTagsToSnapshot: 

      True to copy all tags from the Read Replica to snapshots of the Read Replica; otherwise false. The default is false.

      

    
    :type MonitoringInterval: integer
    :param MonitoringInterval: 

      The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the Read Replica. To disable collecting Enhanced Monitoring metrics, specify 0. The default is 0.

       

      If ``MonitoringRoleArn`` is specified, then you must also set ``MonitoringInterval`` to a value other than 0.

       

      Valid Values: ``0, 1, 5, 10, 15, 30, 60``  

      

    
    :type MonitoringRoleArn: string
    :param MonitoringRoleArn: 

      The ARN for the IAM role that permits RDS to send enhanced monitoring metrics to CloudWatch Logs. For example, ``arn:aws:iam:123456789012:role/emaccess`` . For information on creating a monitoring role, go to `To create an IAM role for Amazon RDS Enhanced Monitoring`_ .

       

      If ``MonitoringInterval`` is set to a value other than 0, then you must supply a ``MonitoringRoleArn`` value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBInstance': {
                'DBInstanceIdentifier': 'string',
                'DBInstanceClass': 'string',
                'Engine': 'string',
                'DBInstanceStatus': 'string',
                'MasterUsername': 'string',
                'DBName': 'string',
                'Endpoint': {
                    'Address': 'string',
                    'Port': 123,
                    'HostedZoneId': 'string'
                },
                'AllocatedStorage': 123,
                'InstanceCreateTime': datetime(2015, 1, 1),
                'PreferredBackupWindow': 'string',
                'BackupRetentionPeriod': 123,
                'DBSecurityGroups': [
                    {
                        'DBSecurityGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'DBParameterGroups': [
                    {
                        'DBParameterGroupName': 'string',
                        'ParameterApplyStatus': 'string'
                    },
                ],
                'AvailabilityZone': 'string',
                'DBSubnetGroup': {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
                'PreferredMaintenanceWindow': 'string',
                'PendingModifiedValues': {
                    'DBInstanceClass': 'string',
                    'AllocatedStorage': 123,
                    'MasterUserPassword': 'string',
                    'Port': 123,
                    'BackupRetentionPeriod': 123,
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'DBInstanceIdentifier': 'string',
                    'StorageType': 'string',
                    'CACertificateIdentifier': 'string',
                    'DBSubnetGroupName': 'string'
                },
                'LatestRestorableTime': datetime(2015, 1, 1),
                'MultiAZ': True|False,
                'EngineVersion': 'string',
                'AutoMinorVersionUpgrade': True|False,
                'ReadReplicaSourceDBInstanceIdentifier': 'string',
                'ReadReplicaDBInstanceIdentifiers': [
                    'string',
                ],
                'LicenseModel': 'string',
                'Iops': 123,
                'OptionGroupMemberships': [
                    {
                        'OptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'CharacterSetName': 'string',
                'SecondaryAvailabilityZone': 'string',
                'PubliclyAccessible': True|False,
                'StatusInfos': [
                    {
                        'StatusType': 'string',
                        'Normal': True|False,
                        'Status': 'string',
                        'Message': 'string'
                    },
                ],
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'DbInstancePort': 123,
                'DBClusterIdentifier': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbiResourceId': 'string',
                'CACertificateIdentifier': 'string',
                'DomainMemberships': [
                    {
                        'Domain': 'string',
                        'Status': 'string',
                        'FQDN': 'string',
                        'IAMRoleName': 'string'
                    },
                ],
                'CopyTagsToSnapshot': True|False,
                'MonitoringInterval': 123,
                'EnhancedMonitoringResourceArn': 'string',
                'MonitoringRoleArn': 'string',
                'PromotionTier': 123,
                'DBInstanceArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBInstance** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBInstance   
           
          *  DeleteDBInstance   
           
          *  ModifyDBInstance   
           

           

          This data type is used as a response element in the  DescribeDBInstances action.

          
          

          - **DBInstanceIdentifier** *(string) --* 

            Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

            
          

          - **DBInstanceClass** *(string) --* 

            Contains the name of the compute and memory capacity class of the DB instance.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB instance.

            
          

          - **DBInstanceStatus** *(string) --* 

            Specifies the current state of this database.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB instance.

            
          

          - **DBName** *(string) --* 

            The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

             

             **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

             

            Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

             

            Type: String

             

             **Oracle**  

             

            Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

            
          

          - **Endpoint** *(dict) --* 

            Specifies the connection endpoint.

            
            

            - **Address** *(string) --* 

              Specifies the DNS address of the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine is listening on.

              
            

            - **HostedZoneId** *(string) --* 

              Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

              
        
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size specified in gigabytes.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Provides the date and time the DB instance was created.

            
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **DBSecurityGroups** *(list) --* 

            Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               
              *  RestoreDBInstanceToPointInTime   
               

              
              

              - **DBSecurityGroupName** *(string) --* 

                The name of the DB security group.

                
              

              - **Status** *(string) --* 

                The status of the DB security group.

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides List of VPC security group elements that the DB instance belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **DBParameterGroups** *(list) --* 

            Provides the list of DB parameter groups applied to this DB instance.

            
            

            - *(dict) --* 

              The status of the DB parameter group.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateDBInstance   
               
              *  CreateDBInstanceReadReplica   
               
              *  DeleteDBInstance   
               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               

              
              

              - **DBParameterGroupName** *(string) --* 

                The name of the DP parameter group.

                
              

              - **ParameterApplyStatus** *(string) --* 

                The status of parameter updates.

                
          
        
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance is located in.

            
          

          - **DBSubnetGroup** *(dict) --* 

            Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **PendingModifiedValues** *(dict) --* 

            Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

            
            

            - **DBInstanceClass** *(string) --* 

              Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

              
            

            - **AllocatedStorage** *(integer) --* 

              Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

              
            

            - **MasterUserPassword** *(string) --* 

              Contains the pending or in-progress change of the master credentials for the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the pending port for the DB instance.

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the pending number of days for which automated backups are retained.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the DB instance.

               

              Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

              
            

            - **Iops** *(integer) --* 

              Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type to be associated with the DB instance.

              
            

            - **CACertificateIdentifier** *(string) --* 

              Specifies the identifier of the CA certificate for the DB instance.

              
            

            - **DBSubnetGroupName** *(string) --* 

              The new DB subnet group for the DB instance. 

              
        
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **MultiAZ** *(boolean) --* 

            Specifies if the DB instance is a Multi-AZ deployment.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **AutoMinorVersionUpgrade** *(boolean) --* 

            Indicates that minor version patches are applied automatically.

            
          

          - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

            Contains the identifier of the source DB instance if this DB instance is a Read Replica.

            
          

          - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB instance.

            
            

            - *(string) --* 
        
          

          - **LicenseModel** *(string) --* 

            License model information for this DB instance.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value.

            
          

          - **OptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB instance.

            
            

            - *(dict) --* 

              Provides information on the option groups the DB instance is a member of.

              
              

              - **OptionGroupName** *(string) --* 

                The name of the option group that the instance belongs to.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                
          
        
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this instance is associated with.

            
          

          - **SecondaryAvailabilityZone** *(string) --* 

            If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

            
          

          - **PubliclyAccessible** *(boolean) --* 

            Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

             

            Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

             

             
            * **Default VPC:** true 
             
            * **VPC:** false 
             

             

            If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

            
          

          - **StatusInfos** *(list) --* 

            The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

            
            

            - *(dict) --* 

              Provides a list of status information for a DB instance.

              
              

              - **StatusType** *(string) --* 

                This value is currently "read replication."

                
              

              - **Normal** *(boolean) --* 

                Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                
              

              - **Status** *(string) --* 

                Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                
              

              - **Message** *(string) --* 

                Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                
          
        
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB instance.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which the instance is associated for TDE encryption.

            
          

          - **DbInstancePort** *(integer) --* 

            Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

            
          

          - **DBClusterIdentifier** *(string) --* 

            If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB instance is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

            
          

          - **DbiResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

            
          

          - **CACertificateIdentifier** *(string) --* 

            The identifier of the CA certificate for this DB instance.

            
          

          - **DomainMemberships** *(list) --* 

            The Active Directory Domain membership records associated with the DB instance.

            
            

            - *(dict) --* 

              An Active Directory Domain membership record associated with the DB instance.

              
              

              - **Domain** *(string) --* 

                The identifier of the Active Directory Domain.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                
              

              - **FQDN** *(string) --* 

                The fully qualified domain name of the Active Directory Domain.

                
              

              - **IAMRoleName** *(string) --* 

                The name of the IAM role to be used when making API calls to the Directory Service.

                
          
        
          

          - **CopyTagsToSnapshot** *(boolean) --* 

            Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

            
          

          - **MonitoringInterval** *(integer) --* 

            The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

            
          

          - **EnhancedMonitoringResourceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

            
          

          - **MonitoringRoleArn** *(string) --* 

            The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

            
          

          - **PromotionTier** *(integer) --* 

            A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

            
          

          - **DBInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB instance.

            
      
    

  .. py:method:: create_db_parameter_group(**kwargs)

    

    Creates a new DB parameter group.

     

    A DB parameter group is initially created with the default parameters for the database engine used by the DB instance. To provide custom values for any of the parameters, you must modify the group after creating it using *ModifyDBParameterGroup* . Once you've created a DB parameter group, you need to associate it with your DB instance using *ModifyDBInstance* . When you associate a new DB parameter group with a running DB instance, you need to reboot the DB instance without failover for the new DB parameter group and associated settings to take effect. 

     

    .. warning::

       

      After you create a DB parameter group, you should wait at least 5 minutes before creating your first DB instance that uses that DB parameter group as the default parameter group. This allows Amazon RDS to fully complete the create action before the parameter group is used as the default for a new DB instance. This is especially important for parameters that are critical when creating the default database for a DB instance, such as the character set for the default database defined by the ``character_set_database`` parameter. You can use the *Parameter Groups* option of the `Amazon RDS console`_ or the *DescribeDBParameters* command to verify that your DB parameter group has been created or modified.

       

    

    **Request Syntax** 
    ::

      response = client.create_db_parameter_group(
          DBParameterGroupName='string',
          DBParameterGroupFamily='string',
          Description='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type DBParameterGroupName: string
    :param DBParameterGroupName: **[REQUIRED]** 

      The name of the DB parameter group.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      .. note::

         

        This value is stored as a lowercase string.

         

      

    
    :type DBParameterGroupFamily: string
    :param DBParameterGroupFamily: **[REQUIRED]** 

      The DB parameter group family name. A DB parameter group can be associated with one and only one DB parameter group family, and can be applied only to a DB instance running a database engine and engine version compatible with that DB parameter group family.

      

    
    :type Description: string
    :param Description: **[REQUIRED]** 

      The description for the DB parameter group.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBParameterGroup': {
                'DBParameterGroupName': 'string',
                'DBParameterGroupFamily': 'string',
                'Description': 'string',
                'DBParameterGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBParameterGroup** *(dict) --* 

          Contains the result of a successful invocation of the  CreateDBParameterGroup action. 

           

          This data type is used as a request parameter in the  DeleteDBParameterGroup action, and as a response element in the  DescribeDBParameterGroups action. 

          
          

          - **DBParameterGroupName** *(string) --* 

            Provides the name of the DB parameter group.

            
          

          - **DBParameterGroupFamily** *(string) --* 

            Provides the name of the DB parameter group family that this DB parameter group is compatible with.

            
          

          - **Description** *(string) --* 

            Provides the customer-specified description for this DB parameter group.

            
          

          - **DBParameterGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB parameter group.

            
      
    

  .. py:method:: create_db_security_group(**kwargs)

    

    Creates a new DB security group. DB security groups control access to a DB instance.

    

    **Request Syntax** 
    ::

      response = client.create_db_security_group(
          DBSecurityGroupName='string',
          DBSecurityGroupDescription='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type DBSecurityGroupName: string
    :param DBSecurityGroupName: **[REQUIRED]** 

      The name for the DB security group. This value is stored as a lowercase string.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       
      * Must not be "Default" 
       

       

      Example: ``mysecuritygroup``  

      

    
    :type DBSecurityGroupDescription: string
    :param DBSecurityGroupDescription: **[REQUIRED]** 

      The description for the DB security group.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSecurityGroup': {
                'OwnerId': 'string',
                'DBSecurityGroupName': 'string',
                'DBSecurityGroupDescription': 'string',
                'VpcId': 'string',
                'EC2SecurityGroups': [
                    {
                        'Status': 'string',
                        'EC2SecurityGroupName': 'string',
                        'EC2SecurityGroupId': 'string',
                        'EC2SecurityGroupOwnerId': 'string'
                    },
                ],
                'IPRanges': [
                    {
                        'Status': 'string',
                        'CIDRIP': 'string'
                    },
                ],
                'DBSecurityGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSecurityGroup** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  DescribeDBSecurityGroups   
           
          *  AuthorizeDBSecurityGroupIngress   
           
          *  CreateDBSecurityGroup   
           
          *  RevokeDBSecurityGroupIngress   
           

           

          This data type is used as a response element in the  DescribeDBSecurityGroups action.

          
          

          - **OwnerId** *(string) --* 

            Provides the AWS ID of the owner of a specific DB security group.

            
          

          - **DBSecurityGroupName** *(string) --* 

            Specifies the name of the DB security group.

            
          

          - **DBSecurityGroupDescription** *(string) --* 

            Provides the description of the DB security group.

            
          

          - **VpcId** *(string) --* 

            Provides the VpcId of the DB security group.

            
          

          - **EC2SecurityGroups** *(list) --* 

            Contains a list of  EC2SecurityGroup elements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  AuthorizeDBSecurityGroupIngress   
               
              *  DescribeDBSecurityGroups   
               
              *  RevokeDBSecurityGroupIngress   
               

              
              

              - **Status** *(string) --* 

                Provides the status of the EC2 security group. Status can be "authorizing", "authorized", "revoking", and "revoked".

                
              

              - **EC2SecurityGroupName** *(string) --* 

                Specifies the name of the EC2 security group.

                
              

              - **EC2SecurityGroupId** *(string) --* 

                Specifies the id of the EC2 security group.

                
              

              - **EC2SecurityGroupOwnerId** *(string) --* 

                Specifies the AWS ID of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` field. 

                
          
        
          

          - **IPRanges** *(list) --* 

            Contains a list of  IPRange elements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the  DescribeDBSecurityGroups action. 

              
              

              - **Status** *(string) --* 

                Specifies the status of the IP range. Status can be "authorizing", "authorized", "revoking", and "revoked".

                
              

              - **CIDRIP** *(string) --* 

                Specifies the IP range.

                
          
        
          

          - **DBSecurityGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB security group.

            
      
    

  .. py:method:: create_db_snapshot(**kwargs)

    

    Creates a DBSnapshot. The source DBInstance must be in "available" state.

    

    **Request Syntax** 
    ::

      response = client.create_db_snapshot(
          DBSnapshotIdentifier='string',
          DBInstanceIdentifier='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type DBSnapshotIdentifier: string
    :param DBSnapshotIdentifier: **[REQUIRED]** 

      The identifier for the DB snapshot.

       

      Constraints:

       

       
      * Cannot be null, empty, or blank 
       
      * Must contain from 1 to 255 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``my-snapshot-id``  

      

    
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The DB instance identifier. This is the unique key that identifies a DB instance.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSnapshot': {
                'DBSnapshotIdentifier': 'string',
                'DBInstanceIdentifier': 'string',
                'SnapshotCreateTime': datetime(2015, 1, 1),
                'Engine': 'string',
                'AllocatedStorage': 123,
                'Status': 'string',
                'Port': 123,
                'AvailabilityZone': 'string',
                'VpcId': 'string',
                'InstanceCreateTime': datetime(2015, 1, 1),
                'MasterUsername': 'string',
                'EngineVersion': 'string',
                'LicenseModel': 'string',
                'SnapshotType': 'string',
                'Iops': 123,
                'OptionGroupName': 'string',
                'PercentProgress': 123,
                'SourceRegion': 'string',
                'SourceDBSnapshotIdentifier': 'string',
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'Encrypted': True|False,
                'KmsKeyId': 'string',
                'DBSnapshotArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSnapshot** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBSnapshot   
           
          *  DeleteDBSnapshot   
           

           

          This data type is used as a response element in the  DescribeDBSnapshots action.

          
          

          - **DBSnapshotIdentifier** *(string) --* 

            Specifies the identifier for the DB snapshot.

            
          

          - **DBInstanceIdentifier** *(string) --* 

            Specifies the DB instance identifier of the DB instance this DB snapshot was created from.

            
          

          - **SnapshotCreateTime** *(datetime) --* 

            Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

            
          

          - **Engine** *(string) --* 

            Specifies the name of the database engine.

            
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **Status** *(string) --* 

            Specifies the status of this DB snapshot.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine was listening on at the time of the snapshot.

            
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance was located in at the time of the DB snapshot.

            
          

          - **VpcId** *(string) --* 

            Provides the VPC ID associated with the DB snapshot.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Specifies the time when the snapshot was taken, in Universal Coordinated Time (UTC).

            
          

          - **MasterUsername** *(string) --* 

            Provides the master username for the DB snapshot.

            
          

          - **EngineVersion** *(string) --* 

            Specifies the version of the database engine.

            
          

          - **LicenseModel** *(string) --* 

            License model information for the restored DB instance.

            
          

          - **SnapshotType** *(string) --* 

            Provides the type of the DB snapshot.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value of the DB instance at the time of the snapshot.

            
          

          - **OptionGroupName** *(string) --* 

            Provides the option group name for the DB snapshot.

            
          

          - **PercentProgress** *(integer) --* 

            The percentage of the estimated data that has been transferred.

            
          

          - **SourceRegion** *(string) --* 

            The region that the DB snapshot was created in or copied from.

            
          

          - **SourceDBSnapshotIdentifier** *(string) --* 

            The DB snapshot Arn that the DB snapshot was copied from. It only has value in case of cross customer or cross region copy.

            
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB Snapshot.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which to associate the instance for TDE encryption.

            
          

          - **Encrypted** *(boolean) --* 

            Specifies whether the DB snapshot is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``Encrypted`` is true, the KMS key identifier for the encrypted DB snapshot. 

            
          

          - **DBSnapshotArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB snapshot.

            
      
    

  .. py:method:: create_db_subnet_group(**kwargs)

    

    Creates a new DB subnet group. DB subnet groups must contain at least one subnet in at least two AZs in the region.

    

    **Request Syntax** 
    ::

      response = client.create_db_subnet_group(
          DBSubnetGroupName='string',
          DBSubnetGroupDescription='string',
          SubnetIds=[
              'string',
          ],
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: **[REQUIRED]** 

      The name for the DB subnet group. This value is stored as a lowercase string.

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    :type DBSubnetGroupDescription: string
    :param DBSubnetGroupDescription: **[REQUIRED]** 

      The description for the DB subnet group.

      

    
    :type SubnetIds: list
    :param SubnetIds: **[REQUIRED]** 

      The EC2 Subnet IDs for the DB subnet group.

      

    
      - *(string) --* 

      
  
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSubnetGroup': {
                'DBSubnetGroupName': 'string',
                'DBSubnetGroupDescription': 'string',
                'VpcId': 'string',
                'SubnetGroupStatus': 'string',
                'Subnets': [
                    {
                        'SubnetIdentifier': 'string',
                        'SubnetAvailabilityZone': {
                            'Name': 'string'
                        },
                        'SubnetStatus': 'string'
                    },
                ],
                'DBSubnetGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSubnetGroup** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBSubnetGroup   
           
          *  ModifyDBSubnetGroup   
           
          *  DescribeDBSubnetGroups   
           
          *  DeleteDBSubnetGroup   
           

           

          This data type is used as a response element in the  DescribeDBSubnetGroups action.

          
          

          - **DBSubnetGroupName** *(string) --* 

            The name of the DB subnet group.

            
          

          - **DBSubnetGroupDescription** *(string) --* 

            Provides the description of the DB subnet group.

            
          

          - **VpcId** *(string) --* 

            Provides the VpcId of the DB subnet group.

            
          

          - **SubnetGroupStatus** *(string) --* 

            Provides the status of the DB subnet group.

            
          

          - **Subnets** *(list) --* 

            Contains a list of  Subnet elements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the  DescribeDBSubnetGroups action. 

              
              

              - **SubnetIdentifier** *(string) --* 

                Specifies the identifier of the subnet.

                
              

              - **SubnetAvailabilityZone** *(dict) --* 

                Contains Availability Zone information.

                 

                This data type is used as an element in the following data type:

                 

                 
                *  OrderableDBInstanceOption   
                 

                
                

                - **Name** *(string) --* 

                  The name of the availability zone.

                  
            
              

              - **SubnetStatus** *(string) --* 

                Specifies the status of the subnet.

                
          
        
          

          - **DBSubnetGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB subnet group.

            
      
    

  .. py:method:: create_event_subscription(**kwargs)

    

    Creates an RDS event notification subscription. This action requires a topic ARN (Amazon Resource Name) created by either the RDS console, the SNS console, or the SNS API. To obtain an ARN with SNS, you must create a topic in Amazon SNS and subscribe to the topic. The ARN is displayed in the SNS console.

     

    You can specify the type of source (SourceType) you want to be notified of, provide a list of RDS sources (SourceIds) that triggers the events, and provide a list of event categories (EventCategories) for events you want to be notified of. For example, you can specify SourceType = db-instance, SourceIds = mydbinstance1, mydbinstance2 and EventCategories = Availability, Backup.

     

    If you specify both the SourceType and SourceIds, such as SourceType = db-instance and SourceIdentifier = myDBInstance1, you will be notified of all the db-instance events for the specified source. If you specify a SourceType but do not specify a SourceIdentifier, you will receive notice of the events for that source type for all your RDS sources. If you do not specify either the SourceType nor the SourceIdentifier, you will be notified of events generated from all RDS sources belonging to your customer account.

    

    **Request Syntax** 
    ::

      response = client.create_event_subscription(
          SubscriptionName='string',
          SnsTopicArn='string',
          SourceType='string',
          EventCategories=[
              'string',
          ],
          SourceIds=[
              'string',
          ],
          Enabled=True|False,
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type SubscriptionName: string
    :param SubscriptionName: **[REQUIRED]** 

      The name of the subscription.

       

      Constraints: The name must be less than 255 characters.

      

    
    :type SnsTopicArn: string
    :param SnsTopicArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the SNS topic created for event notification. The ARN is created by Amazon SNS when you create a topic and subscribe to it.

      

    
    :type SourceType: string
    :param SourceType: 

      The type of source that will be generating the events. For example, if you want to be notified of events generated by a DB instance, you would set this parameter to db-instance. if this value is not specified, all events are returned.

       

      Valid values: ``db-instance`` | ``db-cluster`` | ``db-parameter-group`` | ``db-security-group`` | ``db-snapshot`` | ``db-cluster-snapshot``  

      

    
    :type EventCategories: list
    :param EventCategories: 

      A list of event categories for a SourceType that you want to subscribe to. You can see a list of the categories for a given SourceType in the `Events`_ topic in the Amazon RDS User Guide or by using the **DescribeEventCategories** action. 

      

    
      - *(string) --* 

      
  
    :type SourceIds: list
    :param SourceIds: 

      The list of identifiers of the event sources for which events will be returned. If not specified, then all sources are included in the response. An identifier must begin with a letter and must contain only ASCII letters, digits, and hyphens; it cannot end with a hyphen or contain two consecutive hyphens.

       

      Constraints:

       

       
      * If SourceIds are supplied, SourceType must also be provided. 
       
      * If the source type is a DB instance, then a ``DBInstanceIdentifier`` must be supplied. 
       
      * If the source type is a DB security group, a ``DBSecurityGroupName`` must be supplied. 
       
      * If the source type is a DB parameter group, a ``DBParameterGroupName`` must be supplied. 
       
      * If the source type is a DB snapshot, a ``DBSnapshotIdentifier`` must be supplied. 
       

      

    
      - *(string) --* 

      
  
    :type Enabled: boolean
    :param Enabled: 

      A Boolean value; set to **true** to activate the subscription, set to **false** to create the subscription but not active it. 

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EventSubscription': {
                'CustomerAwsId': 'string',
                'CustSubscriptionId': 'string',
                'SnsTopicArn': 'string',
                'Status': 'string',
                'SubscriptionCreationTime': 'string',
                'SourceType': 'string',
                'SourceIdsList': [
                    'string',
                ],
                'EventCategoriesList': [
                    'string',
                ],
                'Enabled': True|False,
                'EventSubscriptionArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **EventSubscription** *(dict) --* 

          Contains the results of a successful invocation of the  DescribeEventSubscriptions action.

          
          

          - **CustomerAwsId** *(string) --* 

            The AWS customer account associated with the RDS event notification subscription.

            
          

          - **CustSubscriptionId** *(string) --* 

            The RDS event notification subscription Id.

            
          

          - **SnsTopicArn** *(string) --* 

            The topic ARN of the RDS event notification subscription.

            
          

          - **Status** *(string) --* 

            The status of the RDS event notification subscription.

             

            Constraints:

             

            Can be one of the following: creating | modifying | deleting | active | no-permission | topic-not-exist

             

            The status "no-permission" indicates that RDS no longer has permission to post to the SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created.

            
          

          - **SubscriptionCreationTime** *(string) --* 

            The time the RDS event notification subscription was created.

            
          

          - **SourceType** *(string) --* 

            The source type for the RDS event notification subscription.

            
          

          - **SourceIdsList** *(list) --* 

            A list of source IDs for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **EventCategoriesList** *(list) --* 

            A list of event categories for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **Enabled** *(boolean) --* 

            A Boolean value indicating if the subscription is enabled. True indicates the subscription is enabled.

            
          

          - **EventSubscriptionArn** *(string) --* 

            The Amazon Resource Name (ARN) for the event subscription.

            
      
    

  .. py:method:: create_option_group(**kwargs)

    

    Creates a new option group. You can create up to 20 option groups.

    

    **Request Syntax** 
    ::

      response = client.create_option_group(
          OptionGroupName='string',
          EngineName='string',
          MajorEngineVersion='string',
          OptionGroupDescription='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type OptionGroupName: string
    :param OptionGroupName: **[REQUIRED]** 

      Specifies the name of the option group to be created.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``myoptiongroup``  

      

    
    :type EngineName: string
    :param EngineName: **[REQUIRED]** 

      Specifies the name of the engine that this option group should be associated with.

      

    
    :type MajorEngineVersion: string
    :param MajorEngineVersion: **[REQUIRED]** 

      Specifies the major version of the engine that this option group should be associated with.

      

    
    :type OptionGroupDescription: string
    :param OptionGroupDescription: **[REQUIRED]** 

      The description of the option group.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OptionGroup': {
                'OptionGroupName': 'string',
                'OptionGroupDescription': 'string',
                'EngineName': 'string',
                'MajorEngineVersion': 'string',
                'Options': [
                    {
                        'OptionName': 'string',
                        'OptionDescription': 'string',
                        'Persistent': True|False,
                        'Permanent': True|False,
                        'Port': 123,
                        'OptionVersion': 'string',
                        'OptionSettings': [
                            {
                                'Name': 'string',
                                'Value': 'string',
                                'DefaultValue': 'string',
                                'Description': 'string',
                                'ApplyType': 'string',
                                'DataType': 'string',
                                'AllowedValues': 'string',
                                'IsModifiable': True|False,
                                'IsCollection': True|False
                            },
                        ],
                        'DBSecurityGroupMemberships': [
                            {
                                'DBSecurityGroupName': 'string',
                                'Status': 'string'
                            },
                        ],
                        'VpcSecurityGroupMemberships': [
                            {
                                'VpcSecurityGroupId': 'string',
                                'Status': 'string'
                            },
                        ]
                    },
                ],
                'AllowsVpcAndNonVpcInstanceMemberships': True|False,
                'VpcId': 'string',
                'OptionGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **OptionGroup** *(dict) --* 

          

          
          

          - **OptionGroupName** *(string) --* 

            Specifies the name of the option group.

            
          

          - **OptionGroupDescription** *(string) --* 

            Provides a description of the option group.

            
          

          - **EngineName** *(string) --* 

            Indicates the name of the engine that this option group can be applied to.

            
          

          - **MajorEngineVersion** *(string) --* 

            Indicates the major engine version associated with this option group.

            
          

          - **Options** *(list) --* 

            Indicates what options are available in the option group.

            
            

            - *(dict) --* 

              Option details.

              
              

              - **OptionName** *(string) --* 

                The name of the option.

                
              

              - **OptionDescription** *(string) --* 

                The description of the option.

                
              

              - **Persistent** *(boolean) --* 

                Indicate if this option is persistent.

                
              

              - **Permanent** *(boolean) --* 

                Indicate if this option is permanent.

                
              

              - **Port** *(integer) --* 

                If required, the port configured for this option to use.

                
              

              - **OptionVersion** *(string) --* 

                The version of the option.

                
              

              - **OptionSettings** *(list) --* 

                The option settings for this option.

                
                

                - *(dict) --* 

                  Option settings are the actual settings being applied or configured for that option. It is used when you modify an option group or describe option groups. For example, the NATIVE_NETWORK_ENCRYPTION option has a setting called SQLNET.ENCRYPTION_SERVER that can have several different values.

                  
                  

                  - **Name** *(string) --* 

                    The name of the option that has settings that you can set.

                    
                  

                  - **Value** *(string) --* 

                    The current value of the option setting.

                    
                  

                  - **DefaultValue** *(string) --* 

                    The default value of the option setting.

                    
                  

                  - **Description** *(string) --* 

                    The description of the option setting.

                    
                  

                  - **ApplyType** *(string) --* 

                    The DB engine specific parameter type.

                    
                  

                  - **DataType** *(string) --* 

                    The data type of the option setting.

                    
                  

                  - **AllowedValues** *(string) --* 

                    The allowed values of the option setting.

                    
                  

                  - **IsModifiable** *(boolean) --* 

                    A Boolean value that, when true, indicates the option setting can be modified from the default.

                    
                  

                  - **IsCollection** *(boolean) --* 

                    Indicates if the option setting is part of a collection.

                    
              
            
              

              - **DBSecurityGroupMemberships** *(list) --* 

                If the option requires access to a port, then this DB security group allows access to the port.

                
                

                - *(dict) --* 

                  This data type is used as a response element in the following actions:

                   

                   
                  *  ModifyDBInstance   
                   
                  *  RebootDBInstance   
                   
                  *  RestoreDBInstanceFromDBSnapshot   
                   
                  *  RestoreDBInstanceToPointInTime   
                   

                  
                  

                  - **DBSecurityGroupName** *(string) --* 

                    The name of the DB security group.

                    
                  

                  - **Status** *(string) --* 

                    The status of the DB security group.

                    
              
            
              

              - **VpcSecurityGroupMemberships** *(list) --* 

                If the option requires access to a port, then this VPC security group allows access to the port.

                
                

                - *(dict) --* 

                  This data type is used as a response element for queries on VPC security group membership.

                  
                  

                  - **VpcSecurityGroupId** *(string) --* 

                    The name of the VPC security group.

                    
                  

                  - **Status** *(string) --* 

                    The status of the VPC security group.

                    
              
            
          
        
          

          - **AllowsVpcAndNonVpcInstanceMemberships** *(boolean) --* 

            Indicates whether this option group can be applied to both VPC and non-VPC instances. The value ``true`` indicates the option group can be applied to both VPC and non-VPC instances. 

            
          

          - **VpcId** *(string) --* 

            If **AllowsVpcAndNonVpcInstanceMemberships** is ``false`` , this field is blank. If **AllowsVpcAndNonVpcInstanceMemberships** is ``true`` and this field is blank, then this option group can be applied to both VPC and non-VPC instances. If this field contains a value, then this option group can only be applied to instances that are in the VPC indicated by this field. 

            
          

          - **OptionGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the option group.

            
      
    

  .. py:method:: delete_db_cluster(**kwargs)

    

    The DeleteDBCluster action deletes a previously provisioned DB cluster. When you delete a DB cluster, all automated backups for that DB cluster are deleted and cannot be recovered. Manual DB cluster snapshots of the specified DB cluster are not deleted.

     

    

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.delete_db_cluster(
          DBClusterIdentifier='string',
          SkipFinalSnapshot=True|False,
          FinalDBSnapshotIdentifier='string'
      )
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: **[REQUIRED]** 

      The DB cluster identifier for the DB cluster to be deleted. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type SkipFinalSnapshot: boolean
    :param SkipFinalSnapshot: 

      Determines whether a final DB cluster snapshot is created before the DB cluster is deleted. If ``true`` is specified, no DB cluster snapshot is created. If ``false`` is specified, a DB cluster snapshot is created before the DB cluster is deleted. 

       

      .. note::

         

        You must specify a ``FinalDBSnapshotIdentifier`` parameter if ``SkipFinalSnapshot`` is ``false`` .

         

       

      Default: ``false``  

      

    
    :type FinalDBSnapshotIdentifier: string
    :param FinalDBSnapshotIdentifier: 

      The DB cluster snapshot identifier of the new DB cluster snapshot created when ``SkipFinalSnapshot`` is set to ``false`` . 

       

      .. note::

         

        Specifying this parameter and also setting the ``SkipFinalShapshot`` parameter to true results in an error. 

         

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBCluster': {
                'AllocatedStorage': 123,
                'AvailabilityZones': [
                    'string',
                ],
                'BackupRetentionPeriod': 123,
                'CharacterSetName': 'string',
                'DatabaseName': 'string',
                'DBClusterIdentifier': 'string',
                'DBClusterParameterGroup': 'string',
                'DBSubnetGroup': 'string',
                'Status': 'string',
                'PercentProgress': 'string',
                'EarliestRestorableTime': datetime(2015, 1, 1),
                'Endpoint': 'string',
                'Engine': 'string',
                'EngineVersion': 'string',
                'LatestRestorableTime': datetime(2015, 1, 1),
                'Port': 123,
                'MasterUsername': 'string',
                'DBClusterOptionGroupMemberships': [
                    {
                        'DBClusterOptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'PreferredBackupWindow': 'string',
                'PreferredMaintenanceWindow': 'string',
                'ReplicationSourceIdentifier': 'string',
                'ReadReplicaIdentifiers': [
                    'string',
                ],
                'DBClusterMembers': [
                    {
                        'DBInstanceIdentifier': 'string',
                        'IsClusterWriter': True|False,
                        'DBClusterParameterGroupStatus': 'string',
                        'PromotionTier': 123
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'HostedZoneId': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbClusterResourceId': 'string',
                'DBClusterArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBCluster** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBCluster   
           
          *  DeleteDBCluster   
           
          *  FailoverDBCluster   
           
          *  ModifyDBCluster   
           
          *  RestoreDBClusterFromSnapshot   
           
          *  RestoreDBClusterToPointInTime   
           

           

          This data type is used as a response element in the  DescribeDBClusters action.

          
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

            
            

            - *(string) --* 
        
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this cluster is associated with.

            
          

          - **DatabaseName** *(string) --* 

            Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster.

            
          

          - **DBClusterParameterGroup** *(string) --* 

            Specifies the name of the DB cluster parameter group for the DB cluster.

            
          

          - **DBSubnetGroup** *(string) --* 

            Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group.

            
          

          - **Status** *(string) --* 

            Specifies the current state of this DB cluster.

            
          

          - **PercentProgress** *(string) --* 

            Specifies the progress of the operation as a percentage.

            
          

          - **EarliestRestorableTime** *(datetime) --* 

            Specifies the earliest time to which a database can be restored with point-in-time restore.

            
          

          - **Endpoint** *(string) --* 

            Specifies the connection endpoint for the primary instance of the DB cluster.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB cluster.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine is listening on.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB cluster.

            
          

          - **DBClusterOptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB cluster.

            
            

            - *(dict) --* 

              Contains status information for a DB cluster option group.

              
              

              - **DBClusterOptionGroupName** *(string) --* 

                Specifies the name of the DB cluster option group.

                
              

              - **Status** *(string) --* 

                Specifies the status of the DB cluster option group.

                
          
        
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **ReplicationSourceIdentifier** *(string) --* 

            Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

            
          

          - **ReadReplicaIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB cluster.

            
            

            - *(string) --* 
        
          

          - **DBClusterMembers** *(list) --* 

            Provides the list of instances that make up the DB cluster.

            
            

            - *(dict) --* 

              Contains information about an instance that is part of a DB cluster.

              
              

              - **DBInstanceIdentifier** *(string) --* 

                Specifies the instance identifier for this member of the DB cluster.

                
              

              - **IsClusterWriter** *(boolean) --* 

                Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

                
              

              - **DBClusterParameterGroupStatus** *(string) --* 

                Specifies the status of the DB cluster parameter group for this member of the DB cluster.

                
              

              - **PromotionTier** *(integer) --* 

                A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides a list of VPC security groups that the DB cluster belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **HostedZoneId** *(string) --* 

            Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

            
          

          - **DbClusterResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed.

            
          

          - **DBClusterArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster.

            
      
    

  .. py:method:: delete_db_cluster_parameter_group(**kwargs)

    

    Deletes a specified DB cluster parameter group. The DB cluster parameter group to be deleted cannot be associated with any DB clusters.

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.delete_db_cluster_parameter_group(
          DBClusterParameterGroupName='string'
      )
    :type DBClusterParameterGroupName: string
    :param DBClusterParameterGroupName: **[REQUIRED]** 

      The name of the DB cluster parameter group.

       

      Constraints:

       

       
      * Must be the name of an existing DB cluster parameter group. 
       
      * You cannot delete a default DB cluster parameter group. 
       
      * Cannot be associated with any DB clusters. 
       

      

    
    
    :returns: None

  .. py:method:: delete_db_cluster_snapshot(**kwargs)

    

    Deletes a DB cluster snapshot. If the snapshot is being copied, the copy operation is terminated.

     

    .. note::

       

      The DB cluster snapshot must be in the ``available`` state to be deleted.

       

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.delete_db_cluster_snapshot(
          DBClusterSnapshotIdentifier='string'
      )
    :type DBClusterSnapshotIdentifier: string
    :param DBClusterSnapshotIdentifier: **[REQUIRED]** 

      The identifier of the DB cluster snapshot to delete.

       

      Constraints: Must be the name of an existing DB cluster snapshot in the ``available`` state.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBClusterSnapshot': {
                'AvailabilityZones': [
                    'string',
                ],
                'DBClusterSnapshotIdentifier': 'string',
                'DBClusterIdentifier': 'string',
                'SnapshotCreateTime': datetime(2015, 1, 1),
                'Engine': 'string',
                'AllocatedStorage': 123,
                'Status': 'string',
                'Port': 123,
                'VpcId': 'string',
                'ClusterCreateTime': datetime(2015, 1, 1),
                'MasterUsername': 'string',
                'EngineVersion': 'string',
                'LicenseModel': 'string',
                'SnapshotType': 'string',
                'PercentProgress': 123,
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DBClusterSnapshotArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBClusterSnapshot** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBClusterSnapshot   
           
          *  DeleteDBClusterSnapshot   
           

           

          This data type is used as a response element in the  DescribeDBClusterSnapshots action.

          
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster snapshot can be restored in.

            
            

            - *(string) --* 
        
          

          - **DBClusterSnapshotIdentifier** *(string) --* 

            Specifies the identifier for the DB cluster snapshot.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Specifies the DB cluster identifier of the DB cluster that this DB cluster snapshot was created from.

            
          

          - **SnapshotCreateTime** *(datetime) --* 

            Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

            
          

          - **Engine** *(string) --* 

            Specifies the name of the database engine.

            
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **Status** *(string) --* 

            Specifies the status of this DB cluster snapshot.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the DB cluster was listening on at the time of the snapshot.

            
          

          - **VpcId** *(string) --* 

            Provides the VPC ID associated with the DB cluster snapshot.

            
          

          - **ClusterCreateTime** *(datetime) --* 

            Specifies the time when the DB cluster was created, in Universal Coordinated Time (UTC).

            
          

          - **MasterUsername** *(string) --* 

            Provides the master username for the DB cluster snapshot.

            
          

          - **EngineVersion** *(string) --* 

            Provides the version of the database engine for this DB cluster snapshot.

            
          

          - **LicenseModel** *(string) --* 

            Provides the license model information for this DB cluster snapshot.

            
          

          - **SnapshotType** *(string) --* 

            Provides the type of the DB cluster snapshot.

            
          

          - **PercentProgress** *(integer) --* 

            Specifies the percentage of the estimated data that has been transferred.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster snapshot is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster snapshot.

            
          

          - **DBClusterSnapshotArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster snapshot.

            
      
    

  .. py:method:: delete_db_instance(**kwargs)

    

    The DeleteDBInstance action deletes a previously provisioned DB instance. When you delete a DB instance, all automated backups for that instance are deleted and cannot be recovered. Manual DB snapshots of the DB instance to be deleted by ``DeleteDBInstance`` are not deleted.

     

    If you request a final DB snapshot the status of the Amazon RDS DB instance is ``deleting`` until the DB snapshot is created. The API action ``DescribeDBInstance`` is used to monitor the status of this operation. The action cannot be canceled or reverted once submitted. 

     

    Note that when a DB instance is in a failure state and has a status of ``failed`` , ``incompatible-restore`` , or ``incompatible-network`` , you can only delete it when the ``SkipFinalSnapshot`` parameter is set to ``true`` .

     

    If the specified DB instance is part of an Amazon Aurora DB cluster, you cannot delete the DB instance if the following are true:

     

     
    * The DB cluster is a Read Replica of another Amazon Aurora DB cluster. 
     
    * The DB instance is the only instance in the DB cluster. 
     

     

    To delete a DB instance in this case, first call the  PromoteReadReplicaDBCluster API action to promote the DB cluster so it's no longer a Read Replica. After the promotion completes, then call the ``DeleteDBInstance`` API action to delete the final instance in the DB cluster.

    

    **Request Syntax** 
    ::

      response = client.delete_db_instance(
          DBInstanceIdentifier='string',
          SkipFinalSnapshot=True|False,
          FinalDBSnapshotIdentifier='string'
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The DB instance identifier for the DB instance to be deleted. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type SkipFinalSnapshot: boolean
    :param SkipFinalSnapshot: 

      Determines whether a final DB snapshot is created before the DB instance is deleted. If ``true`` is specified, no DBSnapshot is created. If ``false`` is specified, a DB snapshot is created before the DB instance is deleted. 

       

      Note that when a DB instance is in a failure state and has a status of 'failed', 'incompatible-restore', or 'incompatible-network', it can only be deleted when the SkipFinalSnapshot parameter is set to "true".

       

      Specify ``true`` when deleting a Read Replica.

       

      .. note::

         

        The FinalDBSnapshotIdentifier parameter must be specified if SkipFinalSnapshot is ``false`` .

         

       

      Default: ``false``  

      

    
    :type FinalDBSnapshotIdentifier: string
    :param FinalDBSnapshotIdentifier: 

      The DBSnapshotIdentifier of the new DBSnapshot created when SkipFinalSnapshot is set to ``false`` . 

       

      .. note::

         

        Specifying this parameter and also setting the SkipFinalShapshot parameter to true results in an error.

         

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       
      * Cannot be specified when deleting a Read Replica. 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBInstance': {
                'DBInstanceIdentifier': 'string',
                'DBInstanceClass': 'string',
                'Engine': 'string',
                'DBInstanceStatus': 'string',
                'MasterUsername': 'string',
                'DBName': 'string',
                'Endpoint': {
                    'Address': 'string',
                    'Port': 123,
                    'HostedZoneId': 'string'
                },
                'AllocatedStorage': 123,
                'InstanceCreateTime': datetime(2015, 1, 1),
                'PreferredBackupWindow': 'string',
                'BackupRetentionPeriod': 123,
                'DBSecurityGroups': [
                    {
                        'DBSecurityGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'DBParameterGroups': [
                    {
                        'DBParameterGroupName': 'string',
                        'ParameterApplyStatus': 'string'
                    },
                ],
                'AvailabilityZone': 'string',
                'DBSubnetGroup': {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
                'PreferredMaintenanceWindow': 'string',
                'PendingModifiedValues': {
                    'DBInstanceClass': 'string',
                    'AllocatedStorage': 123,
                    'MasterUserPassword': 'string',
                    'Port': 123,
                    'BackupRetentionPeriod': 123,
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'DBInstanceIdentifier': 'string',
                    'StorageType': 'string',
                    'CACertificateIdentifier': 'string',
                    'DBSubnetGroupName': 'string'
                },
                'LatestRestorableTime': datetime(2015, 1, 1),
                'MultiAZ': True|False,
                'EngineVersion': 'string',
                'AutoMinorVersionUpgrade': True|False,
                'ReadReplicaSourceDBInstanceIdentifier': 'string',
                'ReadReplicaDBInstanceIdentifiers': [
                    'string',
                ],
                'LicenseModel': 'string',
                'Iops': 123,
                'OptionGroupMemberships': [
                    {
                        'OptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'CharacterSetName': 'string',
                'SecondaryAvailabilityZone': 'string',
                'PubliclyAccessible': True|False,
                'StatusInfos': [
                    {
                        'StatusType': 'string',
                        'Normal': True|False,
                        'Status': 'string',
                        'Message': 'string'
                    },
                ],
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'DbInstancePort': 123,
                'DBClusterIdentifier': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbiResourceId': 'string',
                'CACertificateIdentifier': 'string',
                'DomainMemberships': [
                    {
                        'Domain': 'string',
                        'Status': 'string',
                        'FQDN': 'string',
                        'IAMRoleName': 'string'
                    },
                ],
                'CopyTagsToSnapshot': True|False,
                'MonitoringInterval': 123,
                'EnhancedMonitoringResourceArn': 'string',
                'MonitoringRoleArn': 'string',
                'PromotionTier': 123,
                'DBInstanceArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBInstance** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBInstance   
           
          *  DeleteDBInstance   
           
          *  ModifyDBInstance   
           

           

          This data type is used as a response element in the  DescribeDBInstances action.

          
          

          - **DBInstanceIdentifier** *(string) --* 

            Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

            
          

          - **DBInstanceClass** *(string) --* 

            Contains the name of the compute and memory capacity class of the DB instance.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB instance.

            
          

          - **DBInstanceStatus** *(string) --* 

            Specifies the current state of this database.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB instance.

            
          

          - **DBName** *(string) --* 

            The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

             

             **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

             

            Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

             

            Type: String

             

             **Oracle**  

             

            Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

            
          

          - **Endpoint** *(dict) --* 

            Specifies the connection endpoint.

            
            

            - **Address** *(string) --* 

              Specifies the DNS address of the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine is listening on.

              
            

            - **HostedZoneId** *(string) --* 

              Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

              
        
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size specified in gigabytes.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Provides the date and time the DB instance was created.

            
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **DBSecurityGroups** *(list) --* 

            Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               
              *  RestoreDBInstanceToPointInTime   
               

              
              

              - **DBSecurityGroupName** *(string) --* 

                The name of the DB security group.

                
              

              - **Status** *(string) --* 

                The status of the DB security group.

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides List of VPC security group elements that the DB instance belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **DBParameterGroups** *(list) --* 

            Provides the list of DB parameter groups applied to this DB instance.

            
            

            - *(dict) --* 

              The status of the DB parameter group.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateDBInstance   
               
              *  CreateDBInstanceReadReplica   
               
              *  DeleteDBInstance   
               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               

              
              

              - **DBParameterGroupName** *(string) --* 

                The name of the DP parameter group.

                
              

              - **ParameterApplyStatus** *(string) --* 

                The status of parameter updates.

                
          
        
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance is located in.

            
          

          - **DBSubnetGroup** *(dict) --* 

            Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **PendingModifiedValues** *(dict) --* 

            Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

            
            

            - **DBInstanceClass** *(string) --* 

              Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

              
            

            - **AllocatedStorage** *(integer) --* 

              Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

              
            

            - **MasterUserPassword** *(string) --* 

              Contains the pending or in-progress change of the master credentials for the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the pending port for the DB instance.

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the pending number of days for which automated backups are retained.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the DB instance.

               

              Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

              
            

            - **Iops** *(integer) --* 

              Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type to be associated with the DB instance.

              
            

            - **CACertificateIdentifier** *(string) --* 

              Specifies the identifier of the CA certificate for the DB instance.

              
            

            - **DBSubnetGroupName** *(string) --* 

              The new DB subnet group for the DB instance. 

              
        
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **MultiAZ** *(boolean) --* 

            Specifies if the DB instance is a Multi-AZ deployment.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **AutoMinorVersionUpgrade** *(boolean) --* 

            Indicates that minor version patches are applied automatically.

            
          

          - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

            Contains the identifier of the source DB instance if this DB instance is a Read Replica.

            
          

          - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB instance.

            
            

            - *(string) --* 
        
          

          - **LicenseModel** *(string) --* 

            License model information for this DB instance.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value.

            
          

          - **OptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB instance.

            
            

            - *(dict) --* 

              Provides information on the option groups the DB instance is a member of.

              
              

              - **OptionGroupName** *(string) --* 

                The name of the option group that the instance belongs to.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                
          
        
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this instance is associated with.

            
          

          - **SecondaryAvailabilityZone** *(string) --* 

            If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

            
          

          - **PubliclyAccessible** *(boolean) --* 

            Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

             

            Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

             

             
            * **Default VPC:** true 
             
            * **VPC:** false 
             

             

            If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

            
          

          - **StatusInfos** *(list) --* 

            The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

            
            

            - *(dict) --* 

              Provides a list of status information for a DB instance.

              
              

              - **StatusType** *(string) --* 

                This value is currently "read replication."

                
              

              - **Normal** *(boolean) --* 

                Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                
              

              - **Status** *(string) --* 

                Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                
              

              - **Message** *(string) --* 

                Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                
          
        
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB instance.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which the instance is associated for TDE encryption.

            
          

          - **DbInstancePort** *(integer) --* 

            Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

            
          

          - **DBClusterIdentifier** *(string) --* 

            If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB instance is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

            
          

          - **DbiResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

            
          

          - **CACertificateIdentifier** *(string) --* 

            The identifier of the CA certificate for this DB instance.

            
          

          - **DomainMemberships** *(list) --* 

            The Active Directory Domain membership records associated with the DB instance.

            
            

            - *(dict) --* 

              An Active Directory Domain membership record associated with the DB instance.

              
              

              - **Domain** *(string) --* 

                The identifier of the Active Directory Domain.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                
              

              - **FQDN** *(string) --* 

                The fully qualified domain name of the Active Directory Domain.

                
              

              - **IAMRoleName** *(string) --* 

                The name of the IAM role to be used when making API calls to the Directory Service.

                
          
        
          

          - **CopyTagsToSnapshot** *(boolean) --* 

            Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

            
          

          - **MonitoringInterval** *(integer) --* 

            The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

            
          

          - **EnhancedMonitoringResourceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

            
          

          - **MonitoringRoleArn** *(string) --* 

            The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

            
          

          - **PromotionTier** *(integer) --* 

            A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

            
          

          - **DBInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB instance.

            
      
    

  .. py:method:: delete_db_parameter_group(**kwargs)

    

    Deletes a specified DBParameterGroup. The DBParameterGroup to be deleted cannot be associated with any DB instances.

    

    **Request Syntax** 
    ::

      response = client.delete_db_parameter_group(
          DBParameterGroupName='string'
      )
    :type DBParameterGroupName: string
    :param DBParameterGroupName: **[REQUIRED]** 

      The name of the DB parameter group.

       

      Constraints:

       

       
      * Must be the name of an existing DB parameter group 
       
      * You cannot delete a default DB parameter group 
       
      * Cannot be associated with any DB instances 
       

      

    
    
    :returns: None

  .. py:method:: delete_db_security_group(**kwargs)

    

    Deletes a DB security group.

     

    .. note::

       

      The specified DB security group must not be associated with any DB instances.

       

    

    **Request Syntax** 
    ::

      response = client.delete_db_security_group(
          DBSecurityGroupName='string'
      )
    :type DBSecurityGroupName: string
    :param DBSecurityGroupName: **[REQUIRED]** 

      The name of the DB security group to delete.

       

      .. note::

         

        You cannot delete the default DB security group.

         

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       
      * Must not be "Default" 
       

      

    
    
    :returns: None

  .. py:method:: delete_db_snapshot(**kwargs)

    

    Deletes a DBSnapshot. If the snapshot is being copied, the copy operation is terminated.

     

    .. note::

       

      The DBSnapshot must be in the ``available`` state to be deleted.

       

    

    **Request Syntax** 
    ::

      response = client.delete_db_snapshot(
          DBSnapshotIdentifier='string'
      )
    :type DBSnapshotIdentifier: string
    :param DBSnapshotIdentifier: **[REQUIRED]** 

      The DBSnapshot identifier.

       

      Constraints: Must be the name of an existing DB snapshot in the ``available`` state.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSnapshot': {
                'DBSnapshotIdentifier': 'string',
                'DBInstanceIdentifier': 'string',
                'SnapshotCreateTime': datetime(2015, 1, 1),
                'Engine': 'string',
                'AllocatedStorage': 123,
                'Status': 'string',
                'Port': 123,
                'AvailabilityZone': 'string',
                'VpcId': 'string',
                'InstanceCreateTime': datetime(2015, 1, 1),
                'MasterUsername': 'string',
                'EngineVersion': 'string',
                'LicenseModel': 'string',
                'SnapshotType': 'string',
                'Iops': 123,
                'OptionGroupName': 'string',
                'PercentProgress': 123,
                'SourceRegion': 'string',
                'SourceDBSnapshotIdentifier': 'string',
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'Encrypted': True|False,
                'KmsKeyId': 'string',
                'DBSnapshotArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSnapshot** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBSnapshot   
           
          *  DeleteDBSnapshot   
           

           

          This data type is used as a response element in the  DescribeDBSnapshots action.

          
          

          - **DBSnapshotIdentifier** *(string) --* 

            Specifies the identifier for the DB snapshot.

            
          

          - **DBInstanceIdentifier** *(string) --* 

            Specifies the DB instance identifier of the DB instance this DB snapshot was created from.

            
          

          - **SnapshotCreateTime** *(datetime) --* 

            Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

            
          

          - **Engine** *(string) --* 

            Specifies the name of the database engine.

            
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **Status** *(string) --* 

            Specifies the status of this DB snapshot.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine was listening on at the time of the snapshot.

            
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance was located in at the time of the DB snapshot.

            
          

          - **VpcId** *(string) --* 

            Provides the VPC ID associated with the DB snapshot.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Specifies the time when the snapshot was taken, in Universal Coordinated Time (UTC).

            
          

          - **MasterUsername** *(string) --* 

            Provides the master username for the DB snapshot.

            
          

          - **EngineVersion** *(string) --* 

            Specifies the version of the database engine.

            
          

          - **LicenseModel** *(string) --* 

            License model information for the restored DB instance.

            
          

          - **SnapshotType** *(string) --* 

            Provides the type of the DB snapshot.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value of the DB instance at the time of the snapshot.

            
          

          - **OptionGroupName** *(string) --* 

            Provides the option group name for the DB snapshot.

            
          

          - **PercentProgress** *(integer) --* 

            The percentage of the estimated data that has been transferred.

            
          

          - **SourceRegion** *(string) --* 

            The region that the DB snapshot was created in or copied from.

            
          

          - **SourceDBSnapshotIdentifier** *(string) --* 

            The DB snapshot Arn that the DB snapshot was copied from. It only has value in case of cross customer or cross region copy.

            
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB Snapshot.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which to associate the instance for TDE encryption.

            
          

          - **Encrypted** *(boolean) --* 

            Specifies whether the DB snapshot is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``Encrypted`` is true, the KMS key identifier for the encrypted DB snapshot. 

            
          

          - **DBSnapshotArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB snapshot.

            
      
    

  .. py:method:: delete_db_subnet_group(**kwargs)

    

    Deletes a DB subnet group.

     

    .. note::

       

      The specified database subnet group must not be associated with any DB instances.

       

    

    **Request Syntax** 
    ::

      response = client.delete_db_subnet_group(
          DBSubnetGroupName='string'
      )
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: **[REQUIRED]** 

      The name of the database subnet group to delete.

       

      .. note::

         

        You cannot delete the default subnet group.

         

       

      Constraints:

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    
    :returns: None

  .. py:method:: delete_event_subscription(**kwargs)

    

    Deletes an RDS event notification subscription.

    

    **Request Syntax** 
    ::

      response = client.delete_event_subscription(
          SubscriptionName='string'
      )
    :type SubscriptionName: string
    :param SubscriptionName: **[REQUIRED]** 

      The name of the RDS event notification subscription you want to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EventSubscription': {
                'CustomerAwsId': 'string',
                'CustSubscriptionId': 'string',
                'SnsTopicArn': 'string',
                'Status': 'string',
                'SubscriptionCreationTime': 'string',
                'SourceType': 'string',
                'SourceIdsList': [
                    'string',
                ],
                'EventCategoriesList': [
                    'string',
                ],
                'Enabled': True|False,
                'EventSubscriptionArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **EventSubscription** *(dict) --* 

          Contains the results of a successful invocation of the  DescribeEventSubscriptions action.

          
          

          - **CustomerAwsId** *(string) --* 

            The AWS customer account associated with the RDS event notification subscription.

            
          

          - **CustSubscriptionId** *(string) --* 

            The RDS event notification subscription Id.

            
          

          - **SnsTopicArn** *(string) --* 

            The topic ARN of the RDS event notification subscription.

            
          

          - **Status** *(string) --* 

            The status of the RDS event notification subscription.

             

            Constraints:

             

            Can be one of the following: creating | modifying | deleting | active | no-permission | topic-not-exist

             

            The status "no-permission" indicates that RDS no longer has permission to post to the SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created.

            
          

          - **SubscriptionCreationTime** *(string) --* 

            The time the RDS event notification subscription was created.

            
          

          - **SourceType** *(string) --* 

            The source type for the RDS event notification subscription.

            
          

          - **SourceIdsList** *(list) --* 

            A list of source IDs for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **EventCategoriesList** *(list) --* 

            A list of event categories for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **Enabled** *(boolean) --* 

            A Boolean value indicating if the subscription is enabled. True indicates the subscription is enabled.

            
          

          - **EventSubscriptionArn** *(string) --* 

            The Amazon Resource Name (ARN) for the event subscription.

            
      
    

  .. py:method:: delete_option_group(**kwargs)

    

    Deletes an existing option group.

    

    **Request Syntax** 
    ::

      response = client.delete_option_group(
          OptionGroupName='string'
      )
    :type OptionGroupName: string
    :param OptionGroupName: **[REQUIRED]** 

      The name of the option group to be deleted.

       

      .. note::

         

        You cannot delete default option groups.

         

      

    
    
    :returns: None

  .. py:method:: describe_account_attributes()

    

    Lists all of the attributes for a customer account. The attributes include Amazon RDS quotas for the account, such as the number of DB instances allowed. The description for a quota includes the quota name, current usage toward that quota, and the quota's maximum value.

     

    This command does not take any parameters.

    

    **Request Syntax** 
    ::

      response = client.describe_account_attributes()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AccountQuotas': [
                {
                    'AccountQuotaName': 'string',
                    'Used': 123,
                    'Max': 123
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Data returned by the **DescribeAccountAttributes** action.

        
        

        - **AccountQuotas** *(list) --* 

          A list of  AccountQuota objects. Within this list, each quota has a name, a count of usage toward the quota maximum, and a maximum value for the quota.

          
          

          - *(dict) --* 

            Describes a quota for an AWS account, for example, the number of DB instances allowed.

            
            

            - **AccountQuotaName** *(string) --* 

              The name of the Amazon RDS quota for this AWS account.

              
            

            - **Used** *(integer) --* 

              The amount currently used toward the quota maximum.

              
            

            - **Max** *(integer) --* 

              The maximum allowed value for the quota.

              
        
      
    

  .. py:method:: describe_certificates(**kwargs)

    

    Lists the set of CA certificates provided by Amazon RDS for this AWS account.

    

    **Request Syntax** 
    ::

      response = client.describe_certificates(
          CertificateIdentifier='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type CertificateIdentifier: string
    :param CertificateIdentifier: 

      The user-supplied certificate identifier. If this parameter is specified, information for only the identified certificate is returned. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous  DescribeCertificates request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Certificates': [
                {
                    'CertificateIdentifier': 'string',
                    'CertificateType': 'string',
                    'Thumbprint': 'string',
                    'ValidFrom': datetime(2015, 1, 1),
                    'ValidTill': datetime(2015, 1, 1),
                    'CertificateArn': 'string'
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Data returned by the **DescribeCertificates** action.

        
        

        - **Certificates** *(list) --* 

          The list of  Certificate objects for the AWS account.

          
          

          - *(dict) --* 

            A CA certificate for an AWS account.

            
            

            - **CertificateIdentifier** *(string) --* 

              The unique key that identifies a certificate.

              
            

            - **CertificateType** *(string) --* 

              The type of the certificate.

              
            

            - **Thumbprint** *(string) --* 

              The thumbprint of the certificate.

              
            

            - **ValidFrom** *(datetime) --* 

              The starting date from which the certificate is valid.

              
            

            - **ValidTill** *(datetime) --* 

              The final date that the certificate continues to be valid.

              
            

            - **CertificateArn** *(string) --* 

              The Amazon Resource Name (ARN) for the certificate.

              
        
      
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous  DescribeCertificates request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
    

  .. py:method:: describe_db_cluster_parameter_groups(**kwargs)

    

    Returns a list of ``DBClusterParameterGroup`` descriptions. If a ``DBClusterParameterGroupName`` parameter is specified, the list will contain only the description of the specified DB cluster parameter group. 

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.describe_db_cluster_parameter_groups(
          DBClusterParameterGroupName='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBClusterParameterGroupName: string
    :param DBClusterParameterGroupName: 

      The name of a specific DB cluster parameter group to return details for.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBClusterParameterGroups`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'DBClusterParameterGroups': [
                {
                    'DBClusterParameterGroupName': 'string',
                    'DBParameterGroupFamily': 'string',
                    'Description': 'string',
                    'DBClusterParameterGroupArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous ``DescribeDBClusterParameterGroups`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **DBClusterParameterGroups** *(list) --* 

          A list of DB cluster parameter groups.

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the  CreateDBClusterParameterGroup or  CopyDBClusterParameterGroup action. 

             

            This data type is used as a request parameter in the  DeleteDBClusterParameterGroup action, and as a response element in the  DescribeDBClusterParameterGroups action. 

            
            

            - **DBClusterParameterGroupName** *(string) --* 

              Provides the name of the DB cluster parameter group.

              
            

            - **DBParameterGroupFamily** *(string) --* 

              Provides the name of the DB parameter group family that this DB cluster parameter group is compatible with.

              
            

            - **Description** *(string) --* 

              Provides the customer-specified description for this DB cluster parameter group.

              
            

            - **DBClusterParameterGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB cluster parameter group.

              
        
      
    

  .. py:method:: describe_db_cluster_parameters(**kwargs)

    

    Returns the detailed parameter list for a particular DB cluster parameter group.

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.describe_db_cluster_parameters(
          DBClusterParameterGroupName='string',
          Source='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBClusterParameterGroupName: string
    :param DBClusterParameterGroupName: **[REQUIRED]** 

      The name of a specific DB cluster parameter group to return parameter details for.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Source: string
    :param Source: 

      A value that indicates to return only parameters for a specific source. Parameter sources can be ``engine`` , ``service`` , or ``customer`` . 

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBClusterParameters`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Parameters': [
                {
                    'ParameterName': 'string',
                    'ParameterValue': 'string',
                    'Description': 'string',
                    'Source': 'string',
                    'ApplyType': 'string',
                    'DataType': 'string',
                    'AllowedValues': 'string',
                    'IsModifiable': True|False,
                    'MinimumEngineVersion': 'string',
                    'ApplyMethod': 'immediate'|'pending-reboot'
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Provides details about a DB cluster parameter group including the parameters in the DB cluster parameter group.

        
        

        - **Parameters** *(list) --* 

          Provides a list of parameters for the DB cluster parameter group.

          
          

          - *(dict) --* 

            This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

             

            This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

            
            

            - **ParameterName** *(string) --* 

              Specifies the name of the parameter.

              
            

            - **ParameterValue** *(string) --* 

              Specifies the value of the parameter.

              
            

            - **Description** *(string) --* 

              Provides a description of the parameter.

              
            

            - **Source** *(string) --* 

              Indicates the source of the parameter value.

              
            

            - **ApplyType** *(string) --* 

              Specifies the engine specific parameters type.

              
            

            - **DataType** *(string) --* 

              Specifies the valid data type for the parameter.

              
            

            - **AllowedValues** *(string) --* 

              Specifies the valid range of values for the parameter.

              
            

            - **IsModifiable** *(boolean) --* 

              Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

              
            

            - **MinimumEngineVersion** *(string) --* 

              The earliest engine version to which the parameter can apply.

              
            

            - **ApplyMethod** *(string) --* 

              Indicates when to apply parameter updates.

              
        
      
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous DescribeDBClusterParameters request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
    

  .. py:method:: describe_db_cluster_snapshot_attributes(**kwargs)

    

    Returns a list of DB cluster snapshot attribute names and values for a manual DB cluster snapshot.

     

    When sharing snapshots with other AWS accounts, ``DescribeDBClusterSnapshotAttributes`` returns the ``restore`` attribute and a list of IDs for the AWS accounts that are authorized to copy or restore the manual DB cluster snapshot. If ``all`` is included in the list of values for the ``restore`` attribute, then the manual DB cluster snapshot is public and can be copied or restored by all AWS accounts.

     

    To add or remove access for an AWS account to copy or restore a manual DB cluster snapshot, or to make the manual DB cluster snapshot public or private, use the  ModifyDBClusterSnapshotAttribute API action.

    

    **Request Syntax** 
    ::

      response = client.describe_db_cluster_snapshot_attributes(
          DBClusterSnapshotIdentifier='string'
      )
    :type DBClusterSnapshotIdentifier: string
    :param DBClusterSnapshotIdentifier: **[REQUIRED]** 

      The identifier for the DB cluster snapshot to describe the attributes for.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBClusterSnapshotAttributesResult': {
                'DBClusterSnapshotIdentifier': 'string',
                'DBClusterSnapshotAttributes': [
                    {
                        'AttributeName': 'string',
                        'AttributeValues': [
                            'string',
                        ]
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBClusterSnapshotAttributesResult** *(dict) --* 

          Contains the results of a successful call to the  DescribeDBClusterSnapshotAttributes API action.

           

          Manual DB cluster snapshot attributes are used to authorize other AWS accounts to copy or restore a manual DB cluster snapshot. For more information, see the  ModifyDBClusterSnapshotAttribute API action.

          
          

          - **DBClusterSnapshotIdentifier** *(string) --* 

            The identifier of the manual DB cluster snapshot that the attributes apply to.

            
          

          - **DBClusterSnapshotAttributes** *(list) --* 

            The list of attributes and values for the manual DB cluster snapshot.

            
            

            - *(dict) --* 

              Contains the name and values of a manual DB cluster snapshot attribute.

               

              Manual DB cluster snapshot attributes are used to authorize other AWS accounts to restore a manual DB cluster snapshot. For more information, see the  ModifyDBClusterSnapshotAttribute API action.

              
              

              - **AttributeName** *(string) --* 

                The name of the manual DB cluster snapshot attribute.

                 

                The attribute named ``restore`` refers to the list of AWS accounts that have permission to copy or restore the manual DB cluster snapshot. For more information, see the  ModifyDBClusterSnapshotAttribute API action.

                
              

              - **AttributeValues** *(list) --* 

                The value(s) for the manual DB cluster snapshot attribute.

                 

                If the ``AttributeName`` field is set to ``restore`` , then this element returns a list of IDs of the AWS accounts that are authorized to copy or restore the manual DB cluster snapshot. If a value of ``all`` is in the list, then the manual DB cluster snapshot is public and available for any AWS account to copy or restore.

                
                

                - *(string) --* 
            
          
        
      
    

  .. py:method:: describe_db_cluster_snapshots(**kwargs)

    

    Returns information about DB cluster snapshots. This API action supports pagination.

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.describe_db_cluster_snapshots(
          DBClusterIdentifier='string',
          DBClusterSnapshotIdentifier='string',
          SnapshotType='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string',
          IncludeShared=True|False,
          IncludePublic=True|False
      )
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: 

      The ID of the DB cluster to retrieve the list of DB cluster snapshots for. This parameter cannot be used in conjunction with the ``DBClusterSnapshotIdentifier`` parameter. This parameter is not case-sensitive. 

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type DBClusterSnapshotIdentifier: string
    :param DBClusterSnapshotIdentifier: 

      A specific DB cluster snapshot identifier to describe. This parameter cannot be used in conjunction with the ``DBClusterIdentifier`` parameter. This value is stored as a lowercase string. 

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       
      * If this identifier is for an automated snapshot, the ``SnapshotType`` parameter must also be specified. 
       

      

    
    :type SnapshotType: string
    :param SnapshotType: 

      The type of DB cluster snapshots to be returned. You can specify one of the following values:

       

       
      * ``automated`` - Return all DB cluster snapshots that have been automatically taken by Amazon RDS for my AWS account. 
       
      * ``manual`` - Return all DB cluster snapshots that have been taken by my AWS account. 
       
      * ``shared`` - Return all manual DB cluster snapshots that have been shared to my AWS account. 
       
      * ``public`` - Return all DB cluster snapshots that have been marked as public. 
       

       

      If you don't specify a ``SnapshotType`` value, then both automated and manual DB cluster snapshots are returned. You can include shared DB cluster snapshots with these results by setting the ``IncludeShared`` parameter to ``true`` . You can include public DB cluster snapshots with these results by setting the ``IncludePublic`` parameter to ``true`` .

       

      The ``IncludeShared`` and ``IncludePublic`` parameters don't apply for ``SnapshotType`` values of ``manual`` or ``automated`` . The ``IncludePublic`` parameter doesn't apply when ``SnapshotType`` is set to ``shared`` . The ``IncludeShared`` parameter doesn't apply when ``SnapshotType`` is set to ``public`` .

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBClusterSnapshots`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    :type IncludeShared: boolean
    :param IncludeShared: 

      Set this value to ``true`` to include shared manual DB cluster snapshots from other AWS accounts that this AWS account has been given permission to copy or restore, otherwise set this value to ``false`` . The default is ``false`` .

       

      You can give an AWS account permission to restore a manual DB cluster snapshot from another AWS account by the  ModifyDBClusterSnapshotAttribute API action.

      

    
    :type IncludePublic: boolean
    :param IncludePublic: 

      Set this value to ``true`` to include manual DB cluster snapshots that are public and can be copied or restored by any AWS account, otherwise set this value to ``false`` . The default is ``false`` . The default is false.

       

      You can share a manual DB cluster snapshot as public by using the  ModifyDBClusterSnapshotAttribute API action.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'DBClusterSnapshots': [
                {
                    'AvailabilityZones': [
                        'string',
                    ],
                    'DBClusterSnapshotIdentifier': 'string',
                    'DBClusterIdentifier': 'string',
                    'SnapshotCreateTime': datetime(2015, 1, 1),
                    'Engine': 'string',
                    'AllocatedStorage': 123,
                    'Status': 'string',
                    'Port': 123,
                    'VpcId': 'string',
                    'ClusterCreateTime': datetime(2015, 1, 1),
                    'MasterUsername': 'string',
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'SnapshotType': 'string',
                    'PercentProgress': 123,
                    'StorageEncrypted': True|False,
                    'KmsKeyId': 'string',
                    'DBClusterSnapshotArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Provides a list of DB cluster snapshots for the user as the result of a call to the  DescribeDBClusterSnapshots action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous  DescribeDBClusterSnapshots request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **DBClusterSnapshots** *(list) --* 

          Provides a list of DB cluster snapshots for the user.

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  CreateDBClusterSnapshot   
             
            *  DeleteDBClusterSnapshot   
             

             

            This data type is used as a response element in the  DescribeDBClusterSnapshots action.

            
            

            - **AvailabilityZones** *(list) --* 

              Provides the list of EC2 Availability Zones that instances in the DB cluster snapshot can be restored in.

              
              

              - *(string) --* 
          
            

            - **DBClusterSnapshotIdentifier** *(string) --* 

              Specifies the identifier for the DB cluster snapshot.

              
            

            - **DBClusterIdentifier** *(string) --* 

              Specifies the DB cluster identifier of the DB cluster that this DB cluster snapshot was created from.

              
            

            - **SnapshotCreateTime** *(datetime) --* 

              Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

              
            

            - **Engine** *(string) --* 

              Specifies the name of the database engine.

              
            

            - **AllocatedStorage** *(integer) --* 

              Specifies the allocated storage size in gigabytes (GB).

              
            

            - **Status** *(string) --* 

              Specifies the status of this DB cluster snapshot.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the DB cluster was listening on at the time of the snapshot.

              
            

            - **VpcId** *(string) --* 

              Provides the VPC ID associated with the DB cluster snapshot.

              
            

            - **ClusterCreateTime** *(datetime) --* 

              Specifies the time when the DB cluster was created, in Universal Coordinated Time (UTC).

              
            

            - **MasterUsername** *(string) --* 

              Provides the master username for the DB cluster snapshot.

              
            

            - **EngineVersion** *(string) --* 

              Provides the version of the database engine for this DB cluster snapshot.

              
            

            - **LicenseModel** *(string) --* 

              Provides the license model information for this DB cluster snapshot.

              
            

            - **SnapshotType** *(string) --* 

              Provides the type of the DB cluster snapshot.

              
            

            - **PercentProgress** *(integer) --* 

              Specifies the percentage of the estimated data that has been transferred.

              
            

            - **StorageEncrypted** *(boolean) --* 

              Specifies whether the DB cluster snapshot is encrypted.

              
            

            - **KmsKeyId** *(string) --* 

              If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster snapshot.

              
            

            - **DBClusterSnapshotArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB cluster snapshot.

              
        
      
    

  .. py:method:: describe_db_clusters(**kwargs)

    

    Returns information about provisioned Aurora DB clusters. This API supports pagination.

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.describe_db_clusters(
          DBClusterIdentifier='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: 

      The user-supplied DB cluster identifier. If this parameter is specified, information from only the specific DB cluster is returned. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous  DescribeDBClusters request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'DBClusters': [
                {
                    'AllocatedStorage': 123,
                    'AvailabilityZones': [
                        'string',
                    ],
                    'BackupRetentionPeriod': 123,
                    'CharacterSetName': 'string',
                    'DatabaseName': 'string',
                    'DBClusterIdentifier': 'string',
                    'DBClusterParameterGroup': 'string',
                    'DBSubnetGroup': 'string',
                    'Status': 'string',
                    'PercentProgress': 'string',
                    'EarliestRestorableTime': datetime(2015, 1, 1),
                    'Endpoint': 'string',
                    'Engine': 'string',
                    'EngineVersion': 'string',
                    'LatestRestorableTime': datetime(2015, 1, 1),
                    'Port': 123,
                    'MasterUsername': 'string',
                    'DBClusterOptionGroupMemberships': [
                        {
                            'DBClusterOptionGroupName': 'string',
                            'Status': 'string'
                        },
                    ],
                    'PreferredBackupWindow': 'string',
                    'PreferredMaintenanceWindow': 'string',
                    'ReplicationSourceIdentifier': 'string',
                    'ReadReplicaIdentifiers': [
                        'string',
                    ],
                    'DBClusterMembers': [
                        {
                            'DBInstanceIdentifier': 'string',
                            'IsClusterWriter': True|False,
                            'DBClusterParameterGroupStatus': 'string',
                            'PromotionTier': 123
                        },
                    ],
                    'VpcSecurityGroups': [
                        {
                            'VpcSecurityGroupId': 'string',
                            'Status': 'string'
                        },
                    ],
                    'HostedZoneId': 'string',
                    'StorageEncrypted': True|False,
                    'KmsKeyId': 'string',
                    'DbClusterResourceId': 'string',
                    'DBClusterArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBClusters action.

        
        

        - **Marker** *(string) --* 

          A pagination token that can be used in a subsequent DescribeDBClusters request.

          
        

        - **DBClusters** *(list) --* 

          Contains a list of DB clusters for the user.

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  CreateDBCluster   
             
            *  DeleteDBCluster   
             
            *  FailoverDBCluster   
             
            *  ModifyDBCluster   
             
            *  RestoreDBClusterFromSnapshot   
             
            *  RestoreDBClusterToPointInTime   
             

             

            This data type is used as a response element in the  DescribeDBClusters action.

            
            

            - **AllocatedStorage** *(integer) --* 

              Specifies the allocated storage size in gigabytes (GB).

              
            

            - **AvailabilityZones** *(list) --* 

              Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

              
              

              - *(string) --* 
          
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the number of days for which automatic DB snapshots are retained.

              
            

            - **CharacterSetName** *(string) --* 

              If present, specifies the name of the character set that this cluster is associated with.

              
            

            - **DatabaseName** *(string) --* 

              Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster.

              
            

            - **DBClusterIdentifier** *(string) --* 

              Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster.

              
            

            - **DBClusterParameterGroup** *(string) --* 

              Specifies the name of the DB cluster parameter group for the DB cluster.

              
            

            - **DBSubnetGroup** *(string) --* 

              Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group.

              
            

            - **Status** *(string) --* 

              Specifies the current state of this DB cluster.

              
            

            - **PercentProgress** *(string) --* 

              Specifies the progress of the operation as a percentage.

              
            

            - **EarliestRestorableTime** *(datetime) --* 

              Specifies the earliest time to which a database can be restored with point-in-time restore.

              
            

            - **Endpoint** *(string) --* 

              Specifies the connection endpoint for the primary instance of the DB cluster.

              
            

            - **Engine** *(string) --* 

              Provides the name of the database engine to be used for this DB cluster.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **LatestRestorableTime** *(datetime) --* 

              Specifies the latest time to which a database can be restored with point-in-time restore.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine is listening on.

              
            

            - **MasterUsername** *(string) --* 

              Contains the master username for the DB cluster.

              
            

            - **DBClusterOptionGroupMemberships** *(list) --* 

              Provides the list of option group memberships for this DB cluster.

              
              

              - *(dict) --* 

                Contains status information for a DB cluster option group.

                
                

                - **DBClusterOptionGroupName** *(string) --* 

                  Specifies the name of the DB cluster option group.

                  
                

                - **Status** *(string) --* 

                  Specifies the status of the DB cluster option group.

                  
            
          
            

            - **PreferredBackupWindow** *(string) --* 

              Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

              
            

            - **PreferredMaintenanceWindow** *(string) --* 

              Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

              
            

            - **ReplicationSourceIdentifier** *(string) --* 

              Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

              
            

            - **ReadReplicaIdentifiers** *(list) --* 

              Contains one or more identifiers of the Read Replicas associated with this DB cluster.

              
              

              - *(string) --* 
          
            

            - **DBClusterMembers** *(list) --* 

              Provides the list of instances that make up the DB cluster.

              
              

              - *(dict) --* 

                Contains information about an instance that is part of a DB cluster.

                
                

                - **DBInstanceIdentifier** *(string) --* 

                  Specifies the instance identifier for this member of the DB cluster.

                  
                

                - **IsClusterWriter** *(boolean) --* 

                  Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

                  
                

                - **DBClusterParameterGroupStatus** *(string) --* 

                  Specifies the status of the DB cluster parameter group for this member of the DB cluster.

                  
                

                - **PromotionTier** *(integer) --* 

                  A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

                  
            
          
            

            - **VpcSecurityGroups** *(list) --* 

              Provides a list of VPC security groups that the DB cluster belongs to.

              
              

              - *(dict) --* 

                This data type is used as a response element for queries on VPC security group membership.

                
                

                - **VpcSecurityGroupId** *(string) --* 

                  The name of the VPC security group.

                  
                

                - **Status** *(string) --* 

                  The status of the VPC security group.

                  
            
          
            

            - **HostedZoneId** *(string) --* 

              Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

              
            

            - **StorageEncrypted** *(boolean) --* 

              Specifies whether the DB cluster is encrypted.

              
            

            - **KmsKeyId** *(string) --* 

              If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

              
            

            - **DbClusterResourceId** *(string) --* 

              The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed.

              
            

            - **DBClusterArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB cluster.

              
        
      
    

  .. py:method:: describe_db_engine_versions(**kwargs)

    

    Returns a list of the available DB engines.

    

    **Request Syntax** 
    ::

      response = client.describe_db_engine_versions(
          Engine='string',
          EngineVersion='string',
          DBParameterGroupFamily='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string',
          DefaultOnly=True|False,
          ListSupportedCharacterSets=True|False
      )
    :type Engine: string
    :param Engine: 

      The database engine to return.

      

    
    :type EngineVersion: string
    :param EngineVersion: 

      The database engine version to return.

       

      Example: ``5.1.49``  

      

    
    :type DBParameterGroupFamily: string
    :param DBParameterGroupFamily: 

      The name of a specific DB parameter group family to return details for.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      Not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more than the ``MaxRecords`` value is available, a pagination token called a marker is included in the response so that the following results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    :type DefaultOnly: boolean
    :param DefaultOnly: 

      Indicates that only the default version of the specified engine or engine and major version combination is returned.

      

    
    :type ListSupportedCharacterSets: boolean
    :param ListSupportedCharacterSets: 

      If this parameter is specified, and if the requested engine supports the CharacterSetName parameter for CreateDBInstance, the response includes a list of supported character sets for each engine version.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'DBEngineVersions': [
                {
                    'Engine': 'string',
                    'EngineVersion': 'string',
                    'DBParameterGroupFamily': 'string',
                    'DBEngineDescription': 'string',
                    'DBEngineVersionDescription': 'string',
                    'DefaultCharacterSet': {
                        'CharacterSetName': 'string',
                        'CharacterSetDescription': 'string'
                    },
                    'SupportedCharacterSets': [
                        {
                            'CharacterSetName': 'string',
                            'CharacterSetDescription': 'string'
                        },
                    ],
                    'ValidUpgradeTarget': [
                        {
                            'Engine': 'string',
                            'EngineVersion': 'string',
                            'Description': 'string',
                            'AutoUpgrade': True|False,
                            'IsMajorVersionUpgrade': True|False
                        },
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBEngineVersions action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **DBEngineVersions** *(list) --* 

          A list of ``DBEngineVersion`` elements. 

          
          

          - *(dict) --* 

            This data type is used as a response element in the action  DescribeDBEngineVersions . 

            
            

            - **Engine** *(string) --* 

              The name of the database engine.

              
            

            - **EngineVersion** *(string) --* 

              The version number of the database engine.

              
            

            - **DBParameterGroupFamily** *(string) --* 

              The name of the DB parameter group family for the database engine.

              
            

            - **DBEngineDescription** *(string) --* 

              The description of the database engine.

              
            

            - **DBEngineVersionDescription** *(string) --* 

              The description of the database engine version.

              
            

            - **DefaultCharacterSet** *(dict) --* 

              The default character set for new instances of this engine version, if the ``CharacterSetName`` parameter of the CreateDBInstance API is not specified. 

              
              

              - **CharacterSetName** *(string) --* 

                The name of the character set.

                
              

              - **CharacterSetDescription** *(string) --* 

                The description of the character set.

                
          
            

            - **SupportedCharacterSets** *(list) --* 

              A list of the character sets supported by this engine for the ``CharacterSetName`` parameter of the CreateDBInstance API. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the action  DescribeDBEngineVersions . 

                
                

                - **CharacterSetName** *(string) --* 

                  The name of the character set.

                  
                

                - **CharacterSetDescription** *(string) --* 

                  The description of the character set.

                  
            
          
            

            - **ValidUpgradeTarget** *(list) --* 

              A list of engine versions that this database engine version can be upgraded to.

              
              

              - *(dict) --* 

                The version of the database engine that a DB instance can be upgraded to.

                
                

                - **Engine** *(string) --* 

                  The name of the upgrade target database engine.

                  
                

                - **EngineVersion** *(string) --* 

                  The version number of the upgrade target database engine.

                  
                

                - **Description** *(string) --* 

                  The version of the database engine that a DB instance can be upgraded to.

                  
                

                - **AutoUpgrade** *(boolean) --* 

                  A value that indicates whether the target version will be applied to any source DB instances that have AutoMinorVersionUpgrade set to true.

                  
                

                - **IsMajorVersionUpgrade** *(boolean) --* 

                  A value that indicates whether a database engine will be upgraded to a major version.

                  
            
          
        
      
    

  .. py:method:: describe_db_instances(**kwargs)

    

    Returns information about provisioned RDS instances. This API supports pagination.

    

    **Request Syntax** 
    ::

      response = client.describe_db_instances(
          DBInstanceIdentifier='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: 

      The user-supplied instance identifier. If this parameter is specified, information from only the specific DB instance is returned. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBInstances`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'DBInstances': [
                {
                    'DBInstanceIdentifier': 'string',
                    'DBInstanceClass': 'string',
                    'Engine': 'string',
                    'DBInstanceStatus': 'string',
                    'MasterUsername': 'string',
                    'DBName': 'string',
                    'Endpoint': {
                        'Address': 'string',
                        'Port': 123,
                        'HostedZoneId': 'string'
                    },
                    'AllocatedStorage': 123,
                    'InstanceCreateTime': datetime(2015, 1, 1),
                    'PreferredBackupWindow': 'string',
                    'BackupRetentionPeriod': 123,
                    'DBSecurityGroups': [
                        {
                            'DBSecurityGroupName': 'string',
                            'Status': 'string'
                        },
                    ],
                    'VpcSecurityGroups': [
                        {
                            'VpcSecurityGroupId': 'string',
                            'Status': 'string'
                        },
                    ],
                    'DBParameterGroups': [
                        {
                            'DBParameterGroupName': 'string',
                            'ParameterApplyStatus': 'string'
                        },
                    ],
                    'AvailabilityZone': 'string',
                    'DBSubnetGroup': {
                        'DBSubnetGroupName': 'string',
                        'DBSubnetGroupDescription': 'string',
                        'VpcId': 'string',
                        'SubnetGroupStatus': 'string',
                        'Subnets': [
                            {
                                'SubnetIdentifier': 'string',
                                'SubnetAvailabilityZone': {
                                    'Name': 'string'
                                },
                                'SubnetStatus': 'string'
                            },
                        ],
                        'DBSubnetGroupArn': 'string'
                    },
                    'PreferredMaintenanceWindow': 'string',
                    'PendingModifiedValues': {
                        'DBInstanceClass': 'string',
                        'AllocatedStorage': 123,
                        'MasterUserPassword': 'string',
                        'Port': 123,
                        'BackupRetentionPeriod': 123,
                        'MultiAZ': True|False,
                        'EngineVersion': 'string',
                        'LicenseModel': 'string',
                        'Iops': 123,
                        'DBInstanceIdentifier': 'string',
                        'StorageType': 'string',
                        'CACertificateIdentifier': 'string',
                        'DBSubnetGroupName': 'string'
                    },
                    'LatestRestorableTime': datetime(2015, 1, 1),
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'AutoMinorVersionUpgrade': True|False,
                    'ReadReplicaSourceDBInstanceIdentifier': 'string',
                    'ReadReplicaDBInstanceIdentifiers': [
                        'string',
                    ],
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'OptionGroupMemberships': [
                        {
                            'OptionGroupName': 'string',
                            'Status': 'string'
                        },
                    ],
                    'CharacterSetName': 'string',
                    'SecondaryAvailabilityZone': 'string',
                    'PubliclyAccessible': True|False,
                    'StatusInfos': [
                        {
                            'StatusType': 'string',
                            'Normal': True|False,
                            'Status': 'string',
                            'Message': 'string'
                        },
                    ],
                    'StorageType': 'string',
                    'TdeCredentialArn': 'string',
                    'DbInstancePort': 123,
                    'DBClusterIdentifier': 'string',
                    'StorageEncrypted': True|False,
                    'KmsKeyId': 'string',
                    'DbiResourceId': 'string',
                    'CACertificateIdentifier': 'string',
                    'DomainMemberships': [
                        {
                            'Domain': 'string',
                            'Status': 'string',
                            'FQDN': 'string',
                            'IAMRoleName': 'string'
                        },
                    ],
                    'CopyTagsToSnapshot': True|False,
                    'MonitoringInterval': 123,
                    'EnhancedMonitoringResourceArn': 'string',
                    'MonitoringRoleArn': 'string',
                    'PromotionTier': 123,
                    'DBInstanceArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBInstances action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **DBInstances** *(list) --* 

          A list of  DBInstance instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  CreateDBInstance   
             
            *  DeleteDBInstance   
             
            *  ModifyDBInstance   
             

             

            This data type is used as a response element in the  DescribeDBInstances action.

            
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

              
            

            - **DBInstanceClass** *(string) --* 

              Contains the name of the compute and memory capacity class of the DB instance.

              
            

            - **Engine** *(string) --* 

              Provides the name of the database engine to be used for this DB instance.

              
            

            - **DBInstanceStatus** *(string) --* 

              Specifies the current state of this database.

              
            

            - **MasterUsername** *(string) --* 

              Contains the master username for the DB instance.

              
            

            - **DBName** *(string) --* 

              The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

               

               **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

               

              Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

               

              Type: String

               

               **Oracle**  

               

              Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

              
            

            - **Endpoint** *(dict) --* 

              Specifies the connection endpoint.

              
              

              - **Address** *(string) --* 

                Specifies the DNS address of the DB instance.

                
              

              - **Port** *(integer) --* 

                Specifies the port that the database engine is listening on.

                
              

              - **HostedZoneId** *(string) --* 

                Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

                
          
            

            - **AllocatedStorage** *(integer) --* 

              Specifies the allocated storage size specified in gigabytes.

              
            

            - **InstanceCreateTime** *(datetime) --* 

              Provides the date and time the DB instance was created.

              
            

            - **PreferredBackupWindow** *(string) --* 

              Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the number of days for which automatic DB snapshots are retained.

              
            

            - **DBSecurityGroups** *(list) --* 

              Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the following actions:

                 

                 
                *  ModifyDBInstance   
                 
                *  RebootDBInstance   
                 
                *  RestoreDBInstanceFromDBSnapshot   
                 
                *  RestoreDBInstanceToPointInTime   
                 

                
                

                - **DBSecurityGroupName** *(string) --* 

                  The name of the DB security group.

                  
                

                - **Status** *(string) --* 

                  The status of the DB security group.

                  
            
          
            

            - **VpcSecurityGroups** *(list) --* 

              Provides List of VPC security group elements that the DB instance belongs to.

              
              

              - *(dict) --* 

                This data type is used as a response element for queries on VPC security group membership.

                
                

                - **VpcSecurityGroupId** *(string) --* 

                  The name of the VPC security group.

                  
                

                - **Status** *(string) --* 

                  The status of the VPC security group.

                  
            
          
            

            - **DBParameterGroups** *(list) --* 

              Provides the list of DB parameter groups applied to this DB instance.

              
              

              - *(dict) --* 

                The status of the DB parameter group.

                 

                This data type is used as a response element in the following actions:

                 

                 
                *  CreateDBInstance   
                 
                *  CreateDBInstanceReadReplica   
                 
                *  DeleteDBInstance   
                 
                *  ModifyDBInstance   
                 
                *  RebootDBInstance   
                 
                *  RestoreDBInstanceFromDBSnapshot   
                 

                
                

                - **DBParameterGroupName** *(string) --* 

                  The name of the DP parameter group.

                  
                

                - **ParameterApplyStatus** *(string) --* 

                  The status of parameter updates.

                  
            
          
            

            - **AvailabilityZone** *(string) --* 

              Specifies the name of the Availability Zone the DB instance is located in.

              
            

            - **DBSubnetGroup** *(dict) --* 

              Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

              
              

              - **DBSubnetGroupName** *(string) --* 

                The name of the DB subnet group.

                
              

              - **DBSubnetGroupDescription** *(string) --* 

                Provides the description of the DB subnet group.

                
              

              - **VpcId** *(string) --* 

                Provides the VpcId of the DB subnet group.

                
              

              - **SubnetGroupStatus** *(string) --* 

                Provides the status of the DB subnet group.

                
              

              - **Subnets** *(list) --* 

                Contains a list of  Subnet elements. 

                
                

                - *(dict) --* 

                  This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                  
                  

                  - **SubnetIdentifier** *(string) --* 

                    Specifies the identifier of the subnet.

                    
                  

                  - **SubnetAvailabilityZone** *(dict) --* 

                    Contains Availability Zone information.

                     

                    This data type is used as an element in the following data type:

                     

                     
                    *  OrderableDBInstanceOption   
                     

                    
                    

                    - **Name** *(string) --* 

                      The name of the availability zone.

                      
                
                  

                  - **SubnetStatus** *(string) --* 

                    Specifies the status of the subnet.

                    
              
            
              

              - **DBSubnetGroupArn** *(string) --* 

                The Amazon Resource Name (ARN) for the DB subnet group.

                
          
            

            - **PreferredMaintenanceWindow** *(string) --* 

              Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

              
            

            - **PendingModifiedValues** *(dict) --* 

              Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

              
              

              - **DBInstanceClass** *(string) --* 

                Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

                
              

              - **AllocatedStorage** *(integer) --* 

                Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

                
              

              - **MasterUserPassword** *(string) --* 

                Contains the pending or in-progress change of the master credentials for the DB instance.

                
              

              - **Port** *(integer) --* 

                Specifies the pending port for the DB instance.

                
              

              - **BackupRetentionPeriod** *(integer) --* 

                Specifies the pending number of days for which automated backups are retained.

                
              

              - **MultiAZ** *(boolean) --* 

                Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

                
              

              - **EngineVersion** *(string) --* 

                Indicates the database engine version.

                
              

              - **LicenseModel** *(string) --* 

                The license model for the DB instance.

                 

                Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

                
              

              - **Iops** *(integer) --* 

                Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

                
              

              - **DBInstanceIdentifier** *(string) --* 

                Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

                
              

              - **StorageType** *(string) --* 

                Specifies the storage type to be associated with the DB instance.

                
              

              - **CACertificateIdentifier** *(string) --* 

                Specifies the identifier of the CA certificate for the DB instance.

                
              

              - **DBSubnetGroupName** *(string) --* 

                The new DB subnet group for the DB instance. 

                
          
            

            - **LatestRestorableTime** *(datetime) --* 

              Specifies the latest time to which a database can be restored with point-in-time restore.

              
            

            - **MultiAZ** *(boolean) --* 

              Specifies if the DB instance is a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **AutoMinorVersionUpgrade** *(boolean) --* 

              Indicates that minor version patches are applied automatically.

              
            

            - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

              Contains the identifier of the source DB instance if this DB instance is a Read Replica.

              
            

            - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

              Contains one or more identifiers of the Read Replicas associated with this DB instance.

              
              

              - *(string) --* 
          
            

            - **LicenseModel** *(string) --* 

              License model information for this DB instance.

              
            

            - **Iops** *(integer) --* 

              Specifies the Provisioned IOPS (I/O operations per second) value.

              
            

            - **OptionGroupMemberships** *(list) --* 

              Provides the list of option group memberships for this DB instance.

              
              

              - *(dict) --* 

                Provides information on the option groups the DB instance is a member of.

                
                

                - **OptionGroupName** *(string) --* 

                  The name of the option group that the instance belongs to.

                  
                

                - **Status** *(string) --* 

                  The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                  
            
          
            

            - **CharacterSetName** *(string) --* 

              If present, specifies the name of the character set that this instance is associated with.

              
            

            - **SecondaryAvailabilityZone** *(string) --* 

              If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

              
            

            - **PubliclyAccessible** *(boolean) --* 

              Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

               

              Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

               

               
              * **Default VPC:** true 
               
              * **VPC:** false 
               

               

              If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

              
            

            - **StatusInfos** *(list) --* 

              The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

              
              

              - *(dict) --* 

                Provides a list of status information for a DB instance.

                
                

                - **StatusType** *(string) --* 

                  This value is currently "read replication."

                  
                

                - **Normal** *(boolean) --* 

                  Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                  
                

                - **Status** *(string) --* 

                  Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                  
                

                - **Message** *(string) --* 

                  Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                  
            
          
            

            - **StorageType** *(string) --* 

              Specifies the storage type associated with DB instance.

              
            

            - **TdeCredentialArn** *(string) --* 

              The ARN from the Key Store with which the instance is associated for TDE encryption.

              
            

            - **DbInstancePort** *(integer) --* 

              Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

              
            

            - **DBClusterIdentifier** *(string) --* 

              If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

              
            

            - **StorageEncrypted** *(boolean) --* 

              Specifies whether the DB instance is encrypted.

              
            

            - **KmsKeyId** *(string) --* 

              If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

              
            

            - **DbiResourceId** *(string) --* 

              The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

              
            

            - **CACertificateIdentifier** *(string) --* 

              The identifier of the CA certificate for this DB instance.

              
            

            - **DomainMemberships** *(list) --* 

              The Active Directory Domain membership records associated with the DB instance.

              
              

              - *(dict) --* 

                An Active Directory Domain membership record associated with the DB instance.

                
                

                - **Domain** *(string) --* 

                  The identifier of the Active Directory Domain.

                  
                

                - **Status** *(string) --* 

                  The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                  
                

                - **FQDN** *(string) --* 

                  The fully qualified domain name of the Active Directory Domain.

                  
                

                - **IAMRoleName** *(string) --* 

                  The name of the IAM role to be used when making API calls to the Directory Service.

                  
            
          
            

            - **CopyTagsToSnapshot** *(boolean) --* 

              Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

              
            

            - **MonitoringInterval** *(integer) --* 

              The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

              
            

            - **EnhancedMonitoringResourceArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

              
            

            - **MonitoringRoleArn** *(string) --* 

              The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

              
            

            - **PromotionTier** *(integer) --* 

              A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

              
            

            - **DBInstanceArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB instance.

              
        
      
    

  .. py:method:: describe_db_log_files(**kwargs)

    

    Returns a list of DB log files for the DB instance.

    

    **Request Syntax** 
    ::

      response = client.describe_db_log_files(
          DBInstanceIdentifier='string',
          FilenameContains='string',
          FileLastWritten=123,
          FileSize=123,
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The customer-assigned name of the DB instance that contains the log files you want to list.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type FilenameContains: string
    :param FilenameContains: 

      Filters the available log files for log file names that contain the specified string.

      

    
    :type FileLastWritten: integer
    :param FileLastWritten: 

      Filters the available log files for files written since the specified date, in POSIX timestamp format with milliseconds.

      

    
    :type FileSize: integer
    :param FileSize: 

      Filters the available log files for files larger than the specified size.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified MaxRecords value, a pagination token called a marker is included in the response so that the remaining results can be retrieved.

      

    
    :type Marker: string
    :param Marker: 

      The pagination token provided in the previous request. If this parameter is specified the response includes only records beyond the marker, up to MaxRecords.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DescribeDBLogFiles': [
                {
                    'LogFileName': 'string',
                    'LastWritten': 123,
                    'Size': 123
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response from a call to  DescribeDBLogFiles . 

        
        

        - **DescribeDBLogFiles** *(list) --* 

          The DB log files returned.

          
          

          - *(dict) --* 

            This data type is used as a response element to  DescribeDBLogFiles .

            
            

            - **LogFileName** *(string) --* 

              The name of the log file for the specified DB instance.

              
            

            - **LastWritten** *(integer) --* 

              A POSIX timestamp when the last log entry was written.

              
            

            - **Size** *(integer) --* 

              The size, in bytes, of the log file for the specified DB instance.

              
        
      
        

        - **Marker** *(string) --* 

          A pagination token that can be used in a subsequent DescribeDBLogFiles request.

          
    

  .. py:method:: describe_db_parameter_groups(**kwargs)

    

    Returns a list of ``DBParameterGroup`` descriptions. If a ``DBParameterGroupName`` is specified, the list will contain only the description of the specified DB parameter group. 

    

    **Request Syntax** 
    ::

      response = client.describe_db_parameter_groups(
          DBParameterGroupName='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBParameterGroupName: string
    :param DBParameterGroupName: 

      The name of a specific DB parameter group to return details for.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBParameterGroups`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'DBParameterGroups': [
                {
                    'DBParameterGroupName': 'string',
                    'DBParameterGroupFamily': 'string',
                    'Description': 'string',
                    'DBParameterGroupArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBParameterGroups action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **DBParameterGroups** *(list) --* 

          A list of  DBParameterGroup instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the  CreateDBParameterGroup action. 

             

            This data type is used as a request parameter in the  DeleteDBParameterGroup action, and as a response element in the  DescribeDBParameterGroups action. 

            
            

            - **DBParameterGroupName** *(string) --* 

              Provides the name of the DB parameter group.

              
            

            - **DBParameterGroupFamily** *(string) --* 

              Provides the name of the DB parameter group family that this DB parameter group is compatible with.

              
            

            - **Description** *(string) --* 

              Provides the customer-specified description for this DB parameter group.

              
            

            - **DBParameterGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB parameter group.

              
        
      
    

  .. py:method:: describe_db_parameters(**kwargs)

    

    Returns the detailed parameter list for a particular DB parameter group.

    

    **Request Syntax** 
    ::

      response = client.describe_db_parameters(
          DBParameterGroupName='string',
          Source='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBParameterGroupName: string
    :param DBParameterGroupName: **[REQUIRED]** 

      The name of a specific DB parameter group to return details for.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Source: string
    :param Source: 

      The parameter types to return.

       

      Default: All parameter types returned

       

      Valid Values: ``user | system | engine-default``  

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBParameters`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Parameters': [
                {
                    'ParameterName': 'string',
                    'ParameterValue': 'string',
                    'Description': 'string',
                    'Source': 'string',
                    'ApplyType': 'string',
                    'DataType': 'string',
                    'AllowedValues': 'string',
                    'IsModifiable': True|False,
                    'MinimumEngineVersion': 'string',
                    'ApplyMethod': 'immediate'|'pending-reboot'
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBParameters action. 

        
        

        - **Parameters** *(list) --* 

          A list of  Parameter values. 

          
          

          - *(dict) --* 

            This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

             

            This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

            
            

            - **ParameterName** *(string) --* 

              Specifies the name of the parameter.

              
            

            - **ParameterValue** *(string) --* 

              Specifies the value of the parameter.

              
            

            - **Description** *(string) --* 

              Provides a description of the parameter.

              
            

            - **Source** *(string) --* 

              Indicates the source of the parameter value.

              
            

            - **ApplyType** *(string) --* 

              Specifies the engine specific parameters type.

              
            

            - **DataType** *(string) --* 

              Specifies the valid data type for the parameter.

              
            

            - **AllowedValues** *(string) --* 

              Specifies the valid range of values for the parameter.

              
            

            - **IsModifiable** *(boolean) --* 

              Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

              
            

            - **MinimumEngineVersion** *(string) --* 

              The earliest engine version to which the parameter can apply.

              
            

            - **ApplyMethod** *(string) --* 

              Indicates when to apply parameter updates.

              
        
      
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
    

  .. py:method:: describe_db_security_groups(**kwargs)

    

    Returns a list of ``DBSecurityGroup`` descriptions. If a ``DBSecurityGroupName`` is specified, the list will contain only the descriptions of the specified DB security group. 

    

    **Request Syntax** 
    ::

      response = client.describe_db_security_groups(
          DBSecurityGroupName='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBSecurityGroupName: string
    :param DBSecurityGroupName: 

      The name of the DB security group to return details for.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBSecurityGroups`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'DBSecurityGroups': [
                {
                    'OwnerId': 'string',
                    'DBSecurityGroupName': 'string',
                    'DBSecurityGroupDescription': 'string',
                    'VpcId': 'string',
                    'EC2SecurityGroups': [
                        {
                            'Status': 'string',
                            'EC2SecurityGroupName': 'string',
                            'EC2SecurityGroupId': 'string',
                            'EC2SecurityGroupOwnerId': 'string'
                        },
                    ],
                    'IPRanges': [
                        {
                            'Status': 'string',
                            'CIDRIP': 'string'
                        },
                    ],
                    'DBSecurityGroupArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBSecurityGroups action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **DBSecurityGroups** *(list) --* 

          A list of  DBSecurityGroup instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  DescribeDBSecurityGroups   
             
            *  AuthorizeDBSecurityGroupIngress   
             
            *  CreateDBSecurityGroup   
             
            *  RevokeDBSecurityGroupIngress   
             

             

            This data type is used as a response element in the  DescribeDBSecurityGroups action.

            
            

            - **OwnerId** *(string) --* 

              Provides the AWS ID of the owner of a specific DB security group.

              
            

            - **DBSecurityGroupName** *(string) --* 

              Specifies the name of the DB security group.

              
            

            - **DBSecurityGroupDescription** *(string) --* 

              Provides the description of the DB security group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB security group.

              
            

            - **EC2SecurityGroups** *(list) --* 

              Contains a list of  EC2SecurityGroup elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the following actions:

                 

                 
                *  AuthorizeDBSecurityGroupIngress   
                 
                *  DescribeDBSecurityGroups   
                 
                *  RevokeDBSecurityGroupIngress   
                 

                
                

                - **Status** *(string) --* 

                  Provides the status of the EC2 security group. Status can be "authorizing", "authorized", "revoking", and "revoked".

                  
                

                - **EC2SecurityGroupName** *(string) --* 

                  Specifies the name of the EC2 security group.

                  
                

                - **EC2SecurityGroupId** *(string) --* 

                  Specifies the id of the EC2 security group.

                  
                

                - **EC2SecurityGroupOwnerId** *(string) --* 

                  Specifies the AWS ID of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` field. 

                  
            
          
            

            - **IPRanges** *(list) --* 

              Contains a list of  IPRange elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSecurityGroups action. 

                
                

                - **Status** *(string) --* 

                  Specifies the status of the IP range. Status can be "authorizing", "authorized", "revoking", and "revoked".

                  
                

                - **CIDRIP** *(string) --* 

                  Specifies the IP range.

                  
            
          
            

            - **DBSecurityGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB security group.

              
        
      
    

  .. py:method:: describe_db_snapshot_attributes(**kwargs)

    

    Returns a list of DB snapshot attribute names and values for a manual DB snapshot.

     

    When sharing snapshots with other AWS accounts, ``DescribeDBSnapshotAttributes`` returns the ``restore`` attribute and a list of IDs for the AWS accounts that are authorized to copy or restore the manual DB snapshot. If ``all`` is included in the list of values for the ``restore`` attribute, then the manual DB snapshot is public and can be copied or restored by all AWS accounts.

     

    To add or remove access for an AWS account to copy or restore a manual DB snapshot, or to make the manual DB snapshot public or private, use the  ModifyDBSnapshotAttribute API action.

    

    **Request Syntax** 
    ::

      response = client.describe_db_snapshot_attributes(
          DBSnapshotIdentifier='string'
      )
    :type DBSnapshotIdentifier: string
    :param DBSnapshotIdentifier: **[REQUIRED]** 

      The identifier for the DB snapshot to describe the attributes for.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSnapshotAttributesResult': {
                'DBSnapshotIdentifier': 'string',
                'DBSnapshotAttributes': [
                    {
                        'AttributeName': 'string',
                        'AttributeValues': [
                            'string',
                        ]
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSnapshotAttributesResult** *(dict) --* 

          Contains the results of a successful call to the  DescribeDBSnapshotAttributes API action.

           

          Manual DB snapshot attributes are used to authorize other AWS accounts to copy or restore a manual DB snapshot. For more information, see the  ModifyDBSnapshotAttribute API action.

          
          

          - **DBSnapshotIdentifier** *(string) --* 

            The identifier of the manual DB snapshot that the attributes apply to.

            
          

          - **DBSnapshotAttributes** *(list) --* 

            The list of attributes and values for the manual DB snapshot.

            
            

            - *(dict) --* 

              Contains the name and values of a manual DB snapshot attribute

               

              Manual DB snapshot attributes are used to authorize other AWS accounts to restore a manual DB snapshot. For more information, see the  ModifyDBSnapshotAttribute API.

              
              

              - **AttributeName** *(string) --* 

                The name of the manual DB snapshot attribute.

                 

                The attribute named ``restore`` refers to the list of AWS accounts that have permission to copy or restore the manual DB cluster snapshot. For more information, see the  ModifyDBSnapshotAttribute API action.

                
              

              - **AttributeValues** *(list) --* 

                The value or values for the manual DB snapshot attribute.

                 

                If the ``AttributeName`` field is set to ``restore`` , then this element returns a list of IDs of the AWS accounts that are authorized to copy or restore the manual DB snapshot. If a value of ``all`` is in the list, then the manual DB snapshot is public and available for any AWS account to copy or restore.

                
                

                - *(string) --* 
            
          
        
      
    

  .. py:method:: describe_db_snapshots(**kwargs)

    

    Returns information about DB snapshots. This API action supports pagination.

    

    **Request Syntax** 
    ::

      response = client.describe_db_snapshots(
          DBInstanceIdentifier='string',
          DBSnapshotIdentifier='string',
          SnapshotType='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string',
          IncludeShared=True|False,
          IncludePublic=True|False
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: 

      The ID of the DB instance to retrieve the list of DB snapshots for. This parameter cannot be used in conjunction with ``DBSnapshotIdentifier`` . This parameter is not case-sensitive. 

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type DBSnapshotIdentifier: string
    :param DBSnapshotIdentifier: 

      A specific DB snapshot identifier to describe. This parameter cannot be used in conjunction with ``DBInstanceIdentifier`` . This value is stored as a lowercase string. 

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       
      * If this identifier is for an automated snapshot, the ``SnapshotType`` parameter must also be specified. 
       

      

    
    :type SnapshotType: string
    :param SnapshotType: 

      The type of snapshots to be returned. You can specify one of the following values:

       

       
      * ``automated`` - Return all DB snapshots that have been automatically taken by Amazon RDS for my AWS account. 
       
      * ``manual`` - Return all DB snapshots that have been taken by my AWS account. 
       
      * ``shared`` - Return all manual DB snapshots that have been shared to my AWS account. 
       
      * ``public`` - Return all DB snapshots that have been marked as public. 
       

       

      If you don't specify a ``SnapshotType`` value, then both automated and manual snapshots are returned. Shared and public DB snapshots are not included in the returned results by default. You can include shared snapshots with these results by setting the ``IncludeShared`` parameter to ``true`` . You can include public snapshots with these results by setting the ``IncludePublic`` parameter to ``true`` .

       

      The ``IncludeShared`` and ``IncludePublic`` parameters don't apply for ``SnapshotType`` values of ``manual`` or ``automated`` . The ``IncludePublic`` parameter doesn't apply when ``SnapshotType`` is set to ``shared`` . The ``IncludeShared`` parameter doesn't apply when ``SnapshotType`` is set to ``public`` .

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBSnapshots`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    :type IncludeShared: boolean
    :param IncludeShared: 

      Set this value to ``true`` to include shared manual DB snapshots from other AWS accounts that this AWS account has been given permission to copy or restore, otherwise set this value to ``false`` . The default is ``false`` .

       

      You can give an AWS account permission to restore a manual DB snapshot from another AWS account by using the  ModifyDBSnapshotAttribute API action.

      

    
    :type IncludePublic: boolean
    :param IncludePublic: 

      Set this value to ``true`` to include manual DB snapshots that are public and can be copied or restored by any AWS account, otherwise set this value to ``false`` . The default is ``false`` .

       

      You can share a manual DB snapshot as public by using the  ModifyDBSnapshotAttribute API.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'DBSnapshots': [
                {
                    'DBSnapshotIdentifier': 'string',
                    'DBInstanceIdentifier': 'string',
                    'SnapshotCreateTime': datetime(2015, 1, 1),
                    'Engine': 'string',
                    'AllocatedStorage': 123,
                    'Status': 'string',
                    'Port': 123,
                    'AvailabilityZone': 'string',
                    'VpcId': 'string',
                    'InstanceCreateTime': datetime(2015, 1, 1),
                    'MasterUsername': 'string',
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'SnapshotType': 'string',
                    'Iops': 123,
                    'OptionGroupName': 'string',
                    'PercentProgress': 123,
                    'SourceRegion': 'string',
                    'SourceDBSnapshotIdentifier': 'string',
                    'StorageType': 'string',
                    'TdeCredentialArn': 'string',
                    'Encrypted': True|False,
                    'KmsKeyId': 'string',
                    'DBSnapshotArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBSnapshots action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **DBSnapshots** *(list) --* 

          A list of  DBSnapshot instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  CreateDBSnapshot   
             
            *  DeleteDBSnapshot   
             

             

            This data type is used as a response element in the  DescribeDBSnapshots action.

            
            

            - **DBSnapshotIdentifier** *(string) --* 

              Specifies the identifier for the DB snapshot.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Specifies the DB instance identifier of the DB instance this DB snapshot was created from.

              
            

            - **SnapshotCreateTime** *(datetime) --* 

              Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

              
            

            - **Engine** *(string) --* 

              Specifies the name of the database engine.

              
            

            - **AllocatedStorage** *(integer) --* 

              Specifies the allocated storage size in gigabytes (GB).

              
            

            - **Status** *(string) --* 

              Specifies the status of this DB snapshot.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine was listening on at the time of the snapshot.

              
            

            - **AvailabilityZone** *(string) --* 

              Specifies the name of the Availability Zone the DB instance was located in at the time of the DB snapshot.

              
            

            - **VpcId** *(string) --* 

              Provides the VPC ID associated with the DB snapshot.

              
            

            - **InstanceCreateTime** *(datetime) --* 

              Specifies the time when the snapshot was taken, in Universal Coordinated Time (UTC).

              
            

            - **MasterUsername** *(string) --* 

              Provides the master username for the DB snapshot.

              
            

            - **EngineVersion** *(string) --* 

              Specifies the version of the database engine.

              
            

            - **LicenseModel** *(string) --* 

              License model information for the restored DB instance.

              
            

            - **SnapshotType** *(string) --* 

              Provides the type of the DB snapshot.

              
            

            - **Iops** *(integer) --* 

              Specifies the Provisioned IOPS (I/O operations per second) value of the DB instance at the time of the snapshot.

              
            

            - **OptionGroupName** *(string) --* 

              Provides the option group name for the DB snapshot.

              
            

            - **PercentProgress** *(integer) --* 

              The percentage of the estimated data that has been transferred.

              
            

            - **SourceRegion** *(string) --* 

              The region that the DB snapshot was created in or copied from.

              
            

            - **SourceDBSnapshotIdentifier** *(string) --* 

              The DB snapshot Arn that the DB snapshot was copied from. It only has value in case of cross customer or cross region copy.

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type associated with DB Snapshot.

              
            

            - **TdeCredentialArn** *(string) --* 

              The ARN from the Key Store with which to associate the instance for TDE encryption.

              
            

            - **Encrypted** *(boolean) --* 

              Specifies whether the DB snapshot is encrypted.

              
            

            - **KmsKeyId** *(string) --* 

              If ``Encrypted`` is true, the KMS key identifier for the encrypted DB snapshot. 

              
            

            - **DBSnapshotArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB snapshot.

              
        
      
    

  .. py:method:: describe_db_subnet_groups(**kwargs)

    

    Returns a list of DBSubnetGroup descriptions. If a DBSubnetGroupName is specified, the list will contain only the descriptions of the specified DBSubnetGroup.

     

    For an overview of CIDR ranges, go to the `Wikipedia Tutorial`_ . 

    

    **Request Syntax** 
    ::

      response = client.describe_db_subnet_groups(
          DBSubnetGroupName='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      The name of the DB subnet group to return details for.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous DescribeDBSubnetGroups request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'DBSubnetGroups': [
                {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBSubnetGroups action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **DBSubnetGroups** *(list) --* 

          A list of  DBSubnetGroup instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  CreateDBSubnetGroup   
             
            *  ModifyDBSubnetGroup   
             
            *  DescribeDBSubnetGroups   
             
            *  DeleteDBSubnetGroup   
             

             

            This data type is used as a response element in the  DescribeDBSubnetGroups action.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
      
    

  .. py:method:: describe_engine_default_cluster_parameters(**kwargs)

    

    Returns the default engine and system parameter information for the cluster database engine.

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.describe_engine_default_cluster_parameters(
          DBParameterGroupFamily='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBParameterGroupFamily: string
    :param DBParameterGroupFamily: **[REQUIRED]** 

      The name of the DB cluster parameter group family to return engine parameter information for.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeEngineDefaultClusterParameters`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EngineDefaults': {
                'DBParameterGroupFamily': 'string',
                'Marker': 'string',
                'Parameters': [
                    {
                        'ParameterName': 'string',
                        'ParameterValue': 'string',
                        'Description': 'string',
                        'Source': 'string',
                        'ApplyType': 'string',
                        'DataType': 'string',
                        'AllowedValues': 'string',
                        'IsModifiable': True|False,
                        'MinimumEngineVersion': 'string',
                        'ApplyMethod': 'immediate'|'pending-reboot'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **EngineDefaults** *(dict) --* 

          Contains the result of a successful invocation of the  DescribeEngineDefaultParameters action. 

          
          

          - **DBParameterGroupFamily** *(string) --* 

            Specifies the name of the DB parameter group family that the engine default parameters apply to.

            
          

          - **Marker** *(string) --* 

            An optional pagination token provided by a previous EngineDefaults request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

            
          

          - **Parameters** *(list) --* 

            Contains a list of engine default parameters.

            
            

            - *(dict) --* 

              This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

               

              This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

              
              

              - **ParameterName** *(string) --* 

                Specifies the name of the parameter.

                
              

              - **ParameterValue** *(string) --* 

                Specifies the value of the parameter.

                
              

              - **Description** *(string) --* 

                Provides a description of the parameter.

                
              

              - **Source** *(string) --* 

                Indicates the source of the parameter value.

                
              

              - **ApplyType** *(string) --* 

                Specifies the engine specific parameters type.

                
              

              - **DataType** *(string) --* 

                Specifies the valid data type for the parameter.

                
              

              - **AllowedValues** *(string) --* 

                Specifies the valid range of values for the parameter.

                
              

              - **IsModifiable** *(boolean) --* 

                Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

                
              

              - **MinimumEngineVersion** *(string) --* 

                The earliest engine version to which the parameter can apply.

                
              

              - **ApplyMethod** *(string) --* 

                Indicates when to apply parameter updates.

                
          
        
      
    

  .. py:method:: describe_engine_default_parameters(**kwargs)

    

    Returns the default engine and system parameter information for the specified database engine.

    

    **Request Syntax** 
    ::

      response = client.describe_engine_default_parameters(
          DBParameterGroupFamily='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBParameterGroupFamily: string
    :param DBParameterGroupFamily: **[REQUIRED]** 

      The name of the DB parameter group family.

      

    
    :type Filters: list
    :param Filters: 

      Not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeEngineDefaultParameters`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EngineDefaults': {
                'DBParameterGroupFamily': 'string',
                'Marker': 'string',
                'Parameters': [
                    {
                        'ParameterName': 'string',
                        'ParameterValue': 'string',
                        'Description': 'string',
                        'Source': 'string',
                        'ApplyType': 'string',
                        'DataType': 'string',
                        'AllowedValues': 'string',
                        'IsModifiable': True|False,
                        'MinimumEngineVersion': 'string',
                        'ApplyMethod': 'immediate'|'pending-reboot'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **EngineDefaults** *(dict) --* 

          Contains the result of a successful invocation of the  DescribeEngineDefaultParameters action. 

          
          

          - **DBParameterGroupFamily** *(string) --* 

            Specifies the name of the DB parameter group family that the engine default parameters apply to.

            
          

          - **Marker** *(string) --* 

            An optional pagination token provided by a previous EngineDefaults request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

            
          

          - **Parameters** *(list) --* 

            Contains a list of engine default parameters.

            
            

            - *(dict) --* 

              This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

               

              This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

              
              

              - **ParameterName** *(string) --* 

                Specifies the name of the parameter.

                
              

              - **ParameterValue** *(string) --* 

                Specifies the value of the parameter.

                
              

              - **Description** *(string) --* 

                Provides a description of the parameter.

                
              

              - **Source** *(string) --* 

                Indicates the source of the parameter value.

                
              

              - **ApplyType** *(string) --* 

                Specifies the engine specific parameters type.

                
              

              - **DataType** *(string) --* 

                Specifies the valid data type for the parameter.

                
              

              - **AllowedValues** *(string) --* 

                Specifies the valid range of values for the parameter.

                
              

              - **IsModifiable** *(boolean) --* 

                Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

                
              

              - **MinimumEngineVersion** *(string) --* 

                The earliest engine version to which the parameter can apply.

                
              

              - **ApplyMethod** *(string) --* 

                Indicates when to apply parameter updates.

                
          
        
      
    

  .. py:method:: describe_event_categories(**kwargs)

    

    Displays a list of categories for all event source types, or, if specified, for a specified source type. You can see a list of the event categories and source types in the `Events`_ topic in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.describe_event_categories(
          SourceType='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ]
      )
    :type SourceType: string
    :param SourceType: 

      The type of source that will be generating the events.

       

      Valid values: db-instance | db-parameter-group | db-security-group | db-snapshot

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EventCategoriesMapList': [
                {
                    'SourceType': 'string',
                    'EventCategories': [
                        'string',
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Data returned from the **DescribeEventCategories** action.

        
        

        - **EventCategoriesMapList** *(list) --* 

          A list of EventCategoriesMap data types.

          
          

          - *(dict) --* 

            Contains the results of a successful invocation of the  DescribeEventCategories action.

            
            

            - **SourceType** *(string) --* 

              The source type that the returned categories belong to

              
            

            - **EventCategories** *(list) --* 

              The event categories for the specified source type

              
              

              - *(string) --* 
          
        
      
    

  .. py:method:: describe_event_subscriptions(**kwargs)

    

    Lists all the subscription descriptions for a customer account. The description for a subscription includes SubscriptionName, SNSTopicARN, CustomerID, SourceType, SourceID, CreationTime, and Status.

     

    If you specify a SubscriptionName, lists the description for that subscription.

    

    **Request Syntax** 
    ::

      response = client.describe_event_subscriptions(
          SubscriptionName='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type SubscriptionName: string
    :param SubscriptionName: 

      The name of the RDS event notification subscription you want to describe.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous DescribeOrderableDBInstanceOptions request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'EventSubscriptionsList': [
                {
                    'CustomerAwsId': 'string',
                    'CustSubscriptionId': 'string',
                    'SnsTopicArn': 'string',
                    'Status': 'string',
                    'SubscriptionCreationTime': 'string',
                    'SourceType': 'string',
                    'SourceIdsList': [
                        'string',
                    ],
                    'EventCategoriesList': [
                        'string',
                    ],
                    'Enabled': True|False,
                    'EventSubscriptionArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Data returned by the **DescribeEventSubscriptions** action.

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous DescribeOrderableDBInstanceOptions request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **EventSubscriptionsList** *(list) --* 

          A list of EventSubscriptions data types.

          
          

          - *(dict) --* 

            Contains the results of a successful invocation of the  DescribeEventSubscriptions action.

            
            

            - **CustomerAwsId** *(string) --* 

              The AWS customer account associated with the RDS event notification subscription.

              
            

            - **CustSubscriptionId** *(string) --* 

              The RDS event notification subscription Id.

              
            

            - **SnsTopicArn** *(string) --* 

              The topic ARN of the RDS event notification subscription.

              
            

            - **Status** *(string) --* 

              The status of the RDS event notification subscription.

               

              Constraints:

               

              Can be one of the following: creating | modifying | deleting | active | no-permission | topic-not-exist

               

              The status "no-permission" indicates that RDS no longer has permission to post to the SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created.

              
            

            - **SubscriptionCreationTime** *(string) --* 

              The time the RDS event notification subscription was created.

              
            

            - **SourceType** *(string) --* 

              The source type for the RDS event notification subscription.

              
            

            - **SourceIdsList** *(list) --* 

              A list of source IDs for the RDS event notification subscription.

              
              

              - *(string) --* 
          
            

            - **EventCategoriesList** *(list) --* 

              A list of event categories for the RDS event notification subscription.

              
              

              - *(string) --* 
          
            

            - **Enabled** *(boolean) --* 

              A Boolean value indicating if the subscription is enabled. True indicates the subscription is enabled.

              
            

            - **EventSubscriptionArn** *(string) --* 

              The Amazon Resource Name (ARN) for the event subscription.

              
        
      
    

  .. py:method:: describe_events(**kwargs)

    

    Returns events related to DB instances, DB security groups, DB snapshots, and DB parameter groups for the past 14 days. Events specific to a particular DB instance, DB security group, database snapshot, or DB parameter group can be obtained by providing the name as a parameter. By default, the past hour of events are returned.

    

    **Request Syntax** 
    ::

      response = client.describe_events(
          SourceIdentifier='string',
          SourceType='db-instance'|'db-parameter-group'|'db-security-group'|'db-snapshot'|'db-cluster'|'db-cluster-snapshot',
          StartTime=datetime(2015, 1, 1),
          EndTime=datetime(2015, 1, 1),
          Duration=123,
          EventCategories=[
              'string',
          ],
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type SourceIdentifier: string
    :param SourceIdentifier: 

      The identifier of the event source for which events will be returned. If not specified, then all sources are included in the response.

       

      Constraints:

       

       
      * If SourceIdentifier is supplied, SourceType must also be provided. 
       
      * If the source type is ``DBInstance`` , then a ``DBInstanceIdentifier`` must be supplied. 
       
      * If the source type is ``DBSecurityGroup`` , a ``DBSecurityGroupName`` must be supplied. 
       
      * If the source type is ``DBParameterGroup`` , a ``DBParameterGroupName`` must be supplied. 
       
      * If the source type is ``DBSnapshot`` , a ``DBSnapshotIdentifier`` must be supplied. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

      

    
    :type SourceType: string
    :param SourceType: 

      The event source to retrieve events for. If no value is specified, all events are returned.

      

    
    :type StartTime: datetime
    :param StartTime: 

      The beginning of the time interval to retrieve events for, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page.`_  

       

      Example: 2009-07-08T18:00Z

      

    
    :type EndTime: datetime
    :param EndTime: 

      The end of the time interval for which to retrieve events, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page.`_  

       

      Example: 2009-07-08T18:00Z

      

    
    :type Duration: integer
    :param Duration: 

      The number of minutes to retrieve events for.

       

      Default: 60

      

    
    :type EventCategories: list
    :param EventCategories: 

      A list of event categories that trigger notifications for a event notification subscription.

      

    
      - *(string) --* 

      
  
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous DescribeEvents request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'Events': [
                {
                    'SourceIdentifier': 'string',
                    'SourceType': 'db-instance'|'db-parameter-group'|'db-security-group'|'db-snapshot'|'db-cluster'|'db-cluster-snapshot',
                    'Message': 'string',
                    'EventCategories': [
                        'string',
                    ],
                    'Date': datetime(2015, 1, 1),
                    'SourceArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeEvents action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous Events request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **Events** *(list) --* 

          A list of  Event instances. 

          
          

          - *(dict) --* 

            This data type is used as a response element in the  DescribeEvents action. 

            
            

            - **SourceIdentifier** *(string) --* 

              Provides the identifier for the source of the event.

              
            

            - **SourceType** *(string) --* 

              Specifies the source type for this event.

              
            

            - **Message** *(string) --* 

              Provides the text of this event.

              
            

            - **EventCategories** *(list) --* 

              Specifies the category for the event.

              
              

              - *(string) --* 
          
            

            - **Date** *(datetime) --* 

              Specifies the date and time of the event.

              
            

            - **SourceArn** *(string) --* 

              The Amazon Resource Name (ARN) for the event.

              
        
      
    

  .. py:method:: describe_option_group_options(**kwargs)

    

    Describes all available options.

    

    **Request Syntax** 
    ::

      response = client.describe_option_group_options(
          EngineName='string',
          MajorEngineVersion='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type EngineName: string
    :param EngineName: **[REQUIRED]** 

      A required parameter. Options available for the given engine name will be described.

      

    
    :type MajorEngineVersion: string
    :param MajorEngineVersion: 

      If specified, filters the results to include only options for the specified major engine version.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OptionGroupOptions': [
                {
                    'Name': 'string',
                    'Description': 'string',
                    'EngineName': 'string',
                    'MajorEngineVersion': 'string',
                    'MinimumRequiredMinorEngineVersion': 'string',
                    'PortRequired': True|False,
                    'DefaultPort': 123,
                    'OptionsDependedOn': [
                        'string',
                    ],
                    'OptionsConflictsWith': [
                        'string',
                    ],
                    'Persistent': True|False,
                    'Permanent': True|False,
                    'OptionGroupOptionSettings': [
                        {
                            'SettingName': 'string',
                            'SettingDescription': 'string',
                            'DefaultValue': 'string',
                            'ApplyType': 'string',
                            'AllowedValues': 'string',
                            'IsModifiable': True|False
                        },
                    ],
                    'OptionGroupOptionVersions': [
                        {
                            'Version': 'string',
                            'IsDefault': True|False
                        },
                    ]
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        

        
        

        - **OptionGroupOptions** *(list) --* 

          List of available option group options.

          
          

          - *(dict) --* 

            Available option.

            
            

            - **Name** *(string) --* 

              The name of the option.

              
            

            - **Description** *(string) --* 

              The description of the option.

              
            

            - **EngineName** *(string) --* 

              The name of the engine that this option can be applied to.

              
            

            - **MajorEngineVersion** *(string) --* 

              Indicates the major engine version that the option is available for.

              
            

            - **MinimumRequiredMinorEngineVersion** *(string) --* 

              The minimum required engine version for the option to be applied.

              
            

            - **PortRequired** *(boolean) --* 

              Specifies whether the option requires a port.

              
            

            - **DefaultPort** *(integer) --* 

              If the option requires a port, specifies the default port for the option.

              
            

            - **OptionsDependedOn** *(list) --* 

              The options that are prerequisites for this option.

              
              

              - *(string) --* 
          
            

            - **OptionsConflictsWith** *(list) --* 

              The options that conflict with this option.

              
              

              - *(string) --* 
          
            

            - **Persistent** *(boolean) --* 

              Persistent options can't be removed from an option group while DB instances are associated with the option group. If you disassociate all DB instances from the option group, your can remove the persistent option from the option group.

              
            

            - **Permanent** *(boolean) --* 

              Permanent options can never be removed from an option group. An option group containing a permanent option can't be removed from a DB instance.

              
            

            - **OptionGroupOptionSettings** *(list) --* 

              The option settings that are available (and the default value) for each option in an option group.

              
              

              - *(dict) --* 

                Option group option settings are used to display settings available for each option with their default values and other information. These values are used with the DescribeOptionGroupOptions action.

                
                

                - **SettingName** *(string) --* 

                  The name of the option group option.

                  
                

                - **SettingDescription** *(string) --* 

                  The description of the option group option.

                  
                

                - **DefaultValue** *(string) --* 

                  The default value for the option group option.

                  
                

                - **ApplyType** *(string) --* 

                  The DB engine specific parameter type for the option group option.

                  
                

                - **AllowedValues** *(string) --* 

                  Indicates the acceptable values for the option group option.

                  
                

                - **IsModifiable** *(boolean) --* 

                  Boolean value where true indicates that this option group option can be changed from the default value.

                  
            
          
            

            - **OptionGroupOptionVersions** *(list) --* 

              The versions that are available for the option.

              
              

              - *(dict) --* 

                The version for an option. Option group option versions are returned by the  DescribeOptionGroupOptions action.

                
                

                - **Version** *(string) --* 

                  The version of the option.

                  
                

                - **IsDefault** *(boolean) --* 

                  True if the version is the default version of the option; otherwise, false.

                  
            
          
        
      
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` .

          
    

  .. py:method:: describe_option_groups(**kwargs)

    

    Describes the available option groups.

    

    **Request Syntax** 
    ::

      response = client.describe_option_groups(
          OptionGroupName='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          Marker='string',
          MaxRecords=123,
          EngineName='string',
          MajorEngineVersion='string'
      )
    :type OptionGroupName: string
    :param OptionGroupName: 

      The name of the option group to describe. Cannot be supplied together with EngineName or MajorEngineVersion.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous DescribeOptionGroups request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type EngineName: string
    :param EngineName: 

      Filters the list of option groups to only include groups associated with a specific database engine.

      

    
    :type MajorEngineVersion: string
    :param MajorEngineVersion: 

      Filters the list of option groups to only include groups associated with a specific database engine version. If specified, then EngineName must also be specified.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OptionGroupsList': [
                {
                    'OptionGroupName': 'string',
                    'OptionGroupDescription': 'string',
                    'EngineName': 'string',
                    'MajorEngineVersion': 'string',
                    'Options': [
                        {
                            'OptionName': 'string',
                            'OptionDescription': 'string',
                            'Persistent': True|False,
                            'Permanent': True|False,
                            'Port': 123,
                            'OptionVersion': 'string',
                            'OptionSettings': [
                                {
                                    'Name': 'string',
                                    'Value': 'string',
                                    'DefaultValue': 'string',
                                    'Description': 'string',
                                    'ApplyType': 'string',
                                    'DataType': 'string',
                                    'AllowedValues': 'string',
                                    'IsModifiable': True|False,
                                    'IsCollection': True|False
                                },
                            ],
                            'DBSecurityGroupMemberships': [
                                {
                                    'DBSecurityGroupName': 'string',
                                    'Status': 'string'
                                },
                            ],
                            'VpcSecurityGroupMemberships': [
                                {
                                    'VpcSecurityGroupId': 'string',
                                    'Status': 'string'
                                },
                            ]
                        },
                    ],
                    'AllowsVpcAndNonVpcInstanceMemberships': True|False,
                    'VpcId': 'string',
                    'OptionGroupArn': 'string'
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        List of option groups.

        
        

        - **OptionGroupsList** *(list) --* 

          List of option groups.

          
          

          - *(dict) --* 

            

            
            

            - **OptionGroupName** *(string) --* 

              Specifies the name of the option group.

              
            

            - **OptionGroupDescription** *(string) --* 

              Provides a description of the option group.

              
            

            - **EngineName** *(string) --* 

              Indicates the name of the engine that this option group can be applied to.

              
            

            - **MajorEngineVersion** *(string) --* 

              Indicates the major engine version associated with this option group.

              
            

            - **Options** *(list) --* 

              Indicates what options are available in the option group.

              
              

              - *(dict) --* 

                Option details.

                
                

                - **OptionName** *(string) --* 

                  The name of the option.

                  
                

                - **OptionDescription** *(string) --* 

                  The description of the option.

                  
                

                - **Persistent** *(boolean) --* 

                  Indicate if this option is persistent.

                  
                

                - **Permanent** *(boolean) --* 

                  Indicate if this option is permanent.

                  
                

                - **Port** *(integer) --* 

                  If required, the port configured for this option to use.

                  
                

                - **OptionVersion** *(string) --* 

                  The version of the option.

                  
                

                - **OptionSettings** *(list) --* 

                  The option settings for this option.

                  
                  

                  - *(dict) --* 

                    Option settings are the actual settings being applied or configured for that option. It is used when you modify an option group or describe option groups. For example, the NATIVE_NETWORK_ENCRYPTION option has a setting called SQLNET.ENCRYPTION_SERVER that can have several different values.

                    
                    

                    - **Name** *(string) --* 

                      The name of the option that has settings that you can set.

                      
                    

                    - **Value** *(string) --* 

                      The current value of the option setting.

                      
                    

                    - **DefaultValue** *(string) --* 

                      The default value of the option setting.

                      
                    

                    - **Description** *(string) --* 

                      The description of the option setting.

                      
                    

                    - **ApplyType** *(string) --* 

                      The DB engine specific parameter type.

                      
                    

                    - **DataType** *(string) --* 

                      The data type of the option setting.

                      
                    

                    - **AllowedValues** *(string) --* 

                      The allowed values of the option setting.

                      
                    

                    - **IsModifiable** *(boolean) --* 

                      A Boolean value that, when true, indicates the option setting can be modified from the default.

                      
                    

                    - **IsCollection** *(boolean) --* 

                      Indicates if the option setting is part of a collection.

                      
                
              
                

                - **DBSecurityGroupMemberships** *(list) --* 

                  If the option requires access to a port, then this DB security group allows access to the port.

                  
                  

                  - *(dict) --* 

                    This data type is used as a response element in the following actions:

                     

                     
                    *  ModifyDBInstance   
                     
                    *  RebootDBInstance   
                     
                    *  RestoreDBInstanceFromDBSnapshot   
                     
                    *  RestoreDBInstanceToPointInTime   
                     

                    
                    

                    - **DBSecurityGroupName** *(string) --* 

                      The name of the DB security group.

                      
                    

                    - **Status** *(string) --* 

                      The status of the DB security group.

                      
                
              
                

                - **VpcSecurityGroupMemberships** *(list) --* 

                  If the option requires access to a port, then this VPC security group allows access to the port.

                  
                  

                  - *(dict) --* 

                    This data type is used as a response element for queries on VPC security group membership.

                    
                    

                    - **VpcSecurityGroupId** *(string) --* 

                      The name of the VPC security group.

                      
                    

                    - **Status** *(string) --* 

                      The status of the VPC security group.

                      
                
              
            
          
            

            - **AllowsVpcAndNonVpcInstanceMemberships** *(boolean) --* 

              Indicates whether this option group can be applied to both VPC and non-VPC instances. The value ``true`` indicates the option group can be applied to both VPC and non-VPC instances. 

              
            

            - **VpcId** *(string) --* 

              If **AllowsVpcAndNonVpcInstanceMemberships** is ``false`` , this field is blank. If **AllowsVpcAndNonVpcInstanceMemberships** is ``true`` and this field is blank, then this option group can be applied to both VPC and non-VPC instances. If this field contains a value, then this option group can only be applied to instances that are in the VPC indicated by this field. 

              
            

            - **OptionGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the option group.

              
        
      
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
    

  .. py:method:: describe_orderable_db_instance_options(**kwargs)

    

    Returns a list of orderable DB instance options for the specified engine.

    

    **Request Syntax** 
    ::

      response = client.describe_orderable_db_instance_options(
          Engine='string',
          EngineVersion='string',
          DBInstanceClass='string',
          LicenseModel='string',
          Vpc=True|False,
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type Engine: string
    :param Engine: **[REQUIRED]** 

      The name of the engine to retrieve DB instance options for.

      

    
    :type EngineVersion: string
    :param EngineVersion: 

      The engine version filter value. Specify this parameter to show only the available offerings matching the specified engine version.

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The DB instance class filter value. Specify this parameter to show only the available offerings matching the specified DB instance class.

      

    
    :type LicenseModel: string
    :param LicenseModel: 

      The license model filter value. Specify this parameter to show only the available offerings matching the specified license model.

      

    
    :type Vpc: boolean
    :param Vpc: 

      The VPC filter value. Specify this parameter to show only the available VPC or non-VPC offerings.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous DescribeOrderableDBInstanceOptions request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OrderableDBInstanceOptions': [
                {
                    'Engine': 'string',
                    'EngineVersion': 'string',
                    'DBInstanceClass': 'string',
                    'LicenseModel': 'string',
                    'AvailabilityZones': [
                        {
                            'Name': 'string'
                        },
                    ],
                    'MultiAZCapable': True|False,
                    'ReadReplicaCapable': True|False,
                    'Vpc': True|False,
                    'SupportsStorageEncryption': True|False,
                    'StorageType': 'string',
                    'SupportsIops': True|False,
                    'SupportsEnhancedMonitoring': True|False
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeOrderableDBInstanceOptions action. 

        
        

        - **OrderableDBInstanceOptions** *(list) --* 

          An  OrderableDBInstanceOption structure containing information about orderable options for the DB instance.

          
          

          - *(dict) --* 

            Contains a list of available options for a DB instance

             

            This data type is used as a response element in the  DescribeOrderableDBInstanceOptions action. 

            
            

            - **Engine** *(string) --* 

              The engine type of the orderable DB instance.

              
            

            - **EngineVersion** *(string) --* 

              The engine version of the orderable DB instance.

              
            

            - **DBInstanceClass** *(string) --* 

              The DB instance class for the orderable DB instance.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the orderable DB instance.

              
            

            - **AvailabilityZones** *(list) --* 

              A list of Availability Zones for the orderable DB instance.

              
              

              - *(dict) --* 

                Contains Availability Zone information.

                 

                This data type is used as an element in the following data type:

                 

                 
                *  OrderableDBInstanceOption   
                 

                
                

                - **Name** *(string) --* 

                  The name of the availability zone.

                  
            
          
            

            - **MultiAZCapable** *(boolean) --* 

              Indicates whether this orderable DB instance is multi-AZ capable.

              
            

            - **ReadReplicaCapable** *(boolean) --* 

              Indicates whether this orderable DB instance can have a Read Replica.

              
            

            - **Vpc** *(boolean) --* 

              Indicates whether this is a VPC orderable DB instance.

              
            

            - **SupportsStorageEncryption** *(boolean) --* 

              Indicates whether this orderable DB instance supports encrypted storage.

              
            

            - **StorageType** *(string) --* 

              Indicates the storage type for this orderable DB instance.

              
            

            - **SupportsIops** *(boolean) --* 

              Indicates whether this orderable DB instance supports provisioned IOPS.

              
            

            - **SupportsEnhancedMonitoring** *(boolean) --* 

              Indicates whether the DB instance supports enhanced monitoring at intervals from 1 to 60 seconds.

              
        
      
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous OrderableDBInstanceOptions request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
    

  .. py:method:: describe_pending_maintenance_actions(**kwargs)

    

    Returns a list of resources (for example, DB instances) that have at least one pending maintenance action.

    

    **Request Syntax** 
    ::

      response = client.describe_pending_maintenance_actions(
          ResourceIdentifier='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          Marker='string',
          MaxRecords=123
      )
    :type ResourceIdentifier: string
    :param ResourceIdentifier: 

      The ARN of a resource to return pending maintenance actions for.

      

    
    :type Filters: list
    :param Filters: 

      A filter that specifies one or more resources to return pending maintenance actions for.

       

      Supported filters:

       

       
      * ``db-instance-id`` - Accepts DB instance identifiers and DB instance Amazon Resource Names (ARNs). The results list will only include pending maintenance actions for the DB instances identified by these ARNs. 
       

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribePendingMaintenanceActions`` request. If this parameter is specified, the response includes only records beyond the marker, up to a number of records specified by ``MaxRecords`` . 

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PendingMaintenanceActions': [
                {
                    'ResourceIdentifier': 'string',
                    'PendingMaintenanceActionDetails': [
                        {
                            'Action': 'string',
                            'AutoAppliedAfterDate': datetime(2015, 1, 1),
                            'ForcedApplyDate': datetime(2015, 1, 1),
                            'OptInStatus': 'string',
                            'CurrentApplyDate': datetime(2015, 1, 1),
                            'Description': 'string'
                        },
                    ]
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Data returned from the **DescribePendingMaintenanceActions** action.

        
        

        - **PendingMaintenanceActions** *(list) --* 

          A list of the pending maintenance actions for the resource.

          
          

          - *(dict) --* 

            Describes the pending maintenance actions for a resource.

            
            

            - **ResourceIdentifier** *(string) --* 

              The ARN of the resource that has pending maintenance actions.

              
            

            - **PendingMaintenanceActionDetails** *(list) --* 

              A list that provides details about the pending maintenance actions for the resource.

              
              

              - *(dict) --* 

                Provides information about a pending maintenance action for a resource.

                
                

                - **Action** *(string) --* 

                  The type of pending maintenance action that is available for the resource.

                  
                

                - **AutoAppliedAfterDate** *(datetime) --* 

                  The date of the maintenance window when the action will be applied. The maintenance action will be applied to the resource during its first maintenance window after this date. If this date is specified, any ``next-maintenance`` opt-in requests are ignored.

                  
                

                - **ForcedApplyDate** *(datetime) --* 

                  The date when the maintenance action will be automatically applied. The maintenance action will be applied to the resource on this date regardless of the maintenance window for the resource. If this date is specified, any ``immediate`` opt-in requests are ignored.

                  
                

                - **OptInStatus** *(string) --* 

                  Indicates the type of opt-in request that has been received for the resource.

                  
                

                - **CurrentApplyDate** *(datetime) --* 

                  The effective date when the pending maintenance action will be applied to the resource. This date takes into account opt-in requests received from the  ApplyPendingMaintenanceAction API, the ``AutoAppliedAfterDate`` , and the ``ForcedApplyDate`` . This value is blank if an opt-in request has not been received and nothing has been specified as ``AutoAppliedAfterDate`` or ``ForcedApplyDate`` .

                  
                

                - **Description** *(string) --* 

                  A description providing more detail about the maintenance action.

                  
            
          
        
      
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous ``DescribePendingMaintenanceActions`` request. If this parameter is specified, the response includes only records beyond the marker, up to a number of records specified by ``MaxRecords`` . 

          
    

  .. py:method:: describe_reserved_db_instances(**kwargs)

    

    Returns information about reserved DB instances for this account, or about a specified reserved DB instance.

    

    **Request Syntax** 
    ::

      response = client.describe_reserved_db_instances(
          ReservedDBInstanceId='string',
          ReservedDBInstancesOfferingId='string',
          DBInstanceClass='string',
          Duration='string',
          ProductDescription='string',
          OfferingType='string',
          MultiAZ=True|False,
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type ReservedDBInstanceId: string
    :param ReservedDBInstanceId: 

      The reserved DB instance identifier filter value. Specify this parameter to show only the reservation that matches the specified reservation ID.

      

    
    :type ReservedDBInstancesOfferingId: string
    :param ReservedDBInstancesOfferingId: 

      The offering identifier filter value. Specify this parameter to show only purchased reservations matching the specified offering identifier.

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The DB instance class filter value. Specify this parameter to show only those reservations matching the specified DB instances class.

      

    
    :type Duration: string
    :param Duration: 

      The duration filter value, specified in years or seconds. Specify this parameter to show only reservations for this duration.

       

      Valid Values: ``1 | 3 | 31536000 | 94608000``  

      

    
    :type ProductDescription: string
    :param ProductDescription: 

      The product description filter value. Specify this parameter to show only those reservations matching the specified product description.

      

    
    :type OfferingType: string
    :param OfferingType: 

      The offering type filter value. Specify this parameter to show only the available offerings matching the specified offering type.

       

      Valid Values: ``"Partial Upfront" | "All Upfront" | "No Upfront"``  

      

    
    :type MultiAZ: boolean
    :param MultiAZ: 

      The Multi-AZ filter value. Specify this parameter to show only those reservations matching the specified Multi-AZ parameter.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more than the ``MaxRecords`` value is available, a pagination token called a marker is included in the response so that the following results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'ReservedDBInstances': [
                {
                    'ReservedDBInstanceId': 'string',
                    'ReservedDBInstancesOfferingId': 'string',
                    'DBInstanceClass': 'string',
                    'StartTime': datetime(2015, 1, 1),
                    'Duration': 123,
                    'FixedPrice': 123.0,
                    'UsagePrice': 123.0,
                    'CurrencyCode': 'string',
                    'DBInstanceCount': 123,
                    'ProductDescription': 'string',
                    'OfferingType': 'string',
                    'MultiAZ': True|False,
                    'State': 'string',
                    'RecurringCharges': [
                        {
                            'RecurringChargeAmount': 123.0,
                            'RecurringChargeFrequency': 'string'
                        },
                    ],
                    'ReservedDBInstanceArn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeReservedDBInstances action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **ReservedDBInstances** *(list) --* 

          A list of reserved DB instances.

          
          

          - *(dict) --* 

            This data type is used as a response element in the  DescribeReservedDBInstances and  PurchaseReservedDBInstancesOffering actions. 

            
            

            - **ReservedDBInstanceId** *(string) --* 

              The unique identifier for the reservation.

              
            

            - **ReservedDBInstancesOfferingId** *(string) --* 

              The offering identifier.

              
            

            - **DBInstanceClass** *(string) --* 

              The DB instance class for the reserved DB instance.

              
            

            - **StartTime** *(datetime) --* 

              The time the reservation started.

              
            

            - **Duration** *(integer) --* 

              The duration of the reservation in seconds.

              
            

            - **FixedPrice** *(float) --* 

              The fixed price charged for this reserved DB instance.

              
            

            - **UsagePrice** *(float) --* 

              The hourly price charged for this reserved DB instance.

              
            

            - **CurrencyCode** *(string) --* 

              The currency code for the reserved DB instance.

              
            

            - **DBInstanceCount** *(integer) --* 

              The number of reserved DB instances.

              
            

            - **ProductDescription** *(string) --* 

              The description of the reserved DB instance.

              
            

            - **OfferingType** *(string) --* 

              The offering type of this reserved DB instance.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates if the reservation applies to Multi-AZ deployments.

              
            

            - **State** *(string) --* 

              The state of the reserved DB instance.

              
            

            - **RecurringCharges** *(list) --* 

              The recurring price charged to run this reserved DB instance.

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeReservedDBInstances and  DescribeReservedDBInstancesOfferings actions. 

                
                

                - **RecurringChargeAmount** *(float) --* 

                  The amount of the recurring charge.

                  
                

                - **RecurringChargeFrequency** *(string) --* 

                  The frequency of the recurring charge.

                  
            
          
            

            - **ReservedDBInstanceArn** *(string) --* 

              The Amazon Resource Name (ARN) for the reserved DB instance.

              
        
      
    

  .. py:method:: describe_reserved_db_instances_offerings(**kwargs)

    

    Lists available reserved DB instance offerings.

    

    **Request Syntax** 
    ::

      response = client.describe_reserved_db_instances_offerings(
          ReservedDBInstancesOfferingId='string',
          DBInstanceClass='string',
          Duration='string',
          ProductDescription='string',
          OfferingType='string',
          MultiAZ=True|False,
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type ReservedDBInstancesOfferingId: string
    :param ReservedDBInstancesOfferingId: 

      The offering identifier filter value. Specify this parameter to show only the available offering that matches the specified reservation identifier.

       

      Example: ``438012d3-4052-4cc7-b2e3-8d3372e0e706``  

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The DB instance class filter value. Specify this parameter to show only the available offerings matching the specified DB instance class.

      

    
    :type Duration: string
    :param Duration: 

      Duration filter value, specified in years or seconds. Specify this parameter to show only reservations for this duration.

       

      Valid Values: ``1 | 3 | 31536000 | 94608000``  

      

    
    :type ProductDescription: string
    :param ProductDescription: 

      Product description filter value. Specify this parameter to show only the available offerings matching the specified product description.

      

    
    :type OfferingType: string
    :param OfferingType: 

      The offering type filter value. Specify this parameter to show only the available offerings matching the specified offering type.

       

      Valid Values: ``"Partial Upfront" | "All Upfront" | "No Upfront"``  

      

    
    :type MultiAZ: boolean
    :param MultiAZ: 

      The Multi-AZ filter value. Specify this parameter to show only the available offerings matching the specified Multi-AZ parameter.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more than the ``MaxRecords`` value is available, a pagination token called a marker is included in the response so that the following results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'ReservedDBInstancesOfferings': [
                {
                    'ReservedDBInstancesOfferingId': 'string',
                    'DBInstanceClass': 'string',
                    'Duration': 123,
                    'FixedPrice': 123.0,
                    'UsagePrice': 123.0,
                    'CurrencyCode': 'string',
                    'ProductDescription': 'string',
                    'OfferingType': 'string',
                    'MultiAZ': True|False,
                    'RecurringCharges': [
                        {
                            'RecurringChargeAmount': 123.0,
                            'RecurringChargeFrequency': 'string'
                        },
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeReservedDBInstancesOfferings action. 

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **ReservedDBInstancesOfferings** *(list) --* 

          A list of reserved DB instance offerings.

          
          

          - *(dict) --* 

            This data type is used as a response element in the  DescribeReservedDBInstancesOfferings action. 

            
            

            - **ReservedDBInstancesOfferingId** *(string) --* 

              The offering identifier.

              
            

            - **DBInstanceClass** *(string) --* 

              The DB instance class for the reserved DB instance.

              
            

            - **Duration** *(integer) --* 

              The duration of the offering in seconds.

              
            

            - **FixedPrice** *(float) --* 

              The fixed price charged for this offering.

              
            

            - **UsagePrice** *(float) --* 

              The hourly price charged for this offering.

              
            

            - **CurrencyCode** *(string) --* 

              The currency code for the reserved DB instance offering.

              
            

            - **ProductDescription** *(string) --* 

              The database engine used by the offering.

              
            

            - **OfferingType** *(string) --* 

              The offering type.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates if the offering applies to Multi-AZ deployments.

              
            

            - **RecurringCharges** *(list) --* 

              The recurring price charged to run this reserved DB instance.

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeReservedDBInstances and  DescribeReservedDBInstancesOfferings actions. 

                
                

                - **RecurringChargeAmount** *(float) --* 

                  The amount of the recurring charge.

                  
                

                - **RecurringChargeFrequency** *(string) --* 

                  The frequency of the recurring charge.

                  
            
          
        
      
    

  .. py:method:: describe_source_regions(**kwargs)

    

    Returns a list that includes the status of each source AWS Region that the current region can get a Read Replica or a DB snapshot from. This API action supports pagination.

    

    **Request Syntax** 
    ::

      response = client.describe_source_regions(
          RegionName='string',
          MaxRecords=123,
          Marker='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ]
      )
    :type RegionName: string
    :param RegionName: 

      The source region name, for example US West (Oregon).

       

      Constraints:

       

       
      * Must specify a valid AWS Region name, for example US West (Oregon). 
       

      

    
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous  DescribeSourceRegions request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` .

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Marker': 'string',
            'SourceRegions': [
                {
                    'RegionName': 'string',
                    'Endpoint': 'string',
                    'Status': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeSourceRegions action.

        
        

        - **Marker** *(string) --* 

          An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

          
        

        - **SourceRegions** *(list) --* 

          A list of SourceRegion instances that contains each source AWS Region that the current region can get a Read Replica or a DB snapshot from.

          
          

          - *(dict) --* 

            Contains an AWS Region name as the result of a successful call to the  DescribeSourceRegions action.

            
            

            - **RegionName** *(string) --* 

              The source region name.

              
            

            - **Endpoint** *(string) --* 

              The source region endpoint.

              
            

            - **Status** *(string) --* 

              The status of the source region.

              
        
      
    

  .. py:method:: download_db_log_file_portion(**kwargs)

    

    Downloads all or a portion of the specified log file, up to 1 MB in size.

    

    **Request Syntax** 
    ::

      response = client.download_db_log_file_portion(
          DBInstanceIdentifier='string',
          LogFileName='string',
          Marker='string',
          NumberOfLines=123
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The customer-assigned name of the DB instance that contains the log files you want to list.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type LogFileName: string
    :param LogFileName: **[REQUIRED]** 

      The name of the log file to be downloaded.

      

    
    :type Marker: string
    :param Marker: 

      The pagination token provided in the previous request or "0". If the Marker parameter is specified the response includes only records beyond the marker until the end of the file or up to NumberOfLines.

      

    
    :type NumberOfLines: integer
    :param NumberOfLines: 

      The number of lines to download. If the number of lines specified results in a file over 1 MB in size, the file will be truncated at 1 MB in size.

       

      If the NumberOfLines parameter is specified, then the block of lines returned can be from the beginning or the end of the log file, depending on the value of the Marker parameter.

       

       
      * If neither Marker or NumberOfLines are specified, the entire log file is returned up to a maximum of 10000 lines, starting with the most recent log entries first. 
       
      * If NumberOfLines is specified and Marker is not specified, then the most recent lines from the end of the log file are returned. 
       
      * If Marker is specified as "0", then the specified number of lines from the beginning of the log file are returned. 
       
      * You can download the log file in blocks of lines by specifying the size of the block using the NumberOfLines parameter, and by specifying a value of "0" for the Marker parameter in your first request. Include the Marker value returned in the response as the Marker value for the next request, continuing until the AdditionalDataPending response element returns false. 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LogFileData': 'string',
            'Marker': 'string',
            'AdditionalDataPending': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 

        This data type is used as a response element to  DownloadDBLogFilePortion .

        
        

        - **LogFileData** *(string) --* 

          Entries from the specified log file.

          
        

        - **Marker** *(string) --* 

          A pagination token that can be used in a subsequent DownloadDBLogFilePortion request.

          
        

        - **AdditionalDataPending** *(boolean) --* 

          Boolean value that if true, indicates there is more data to be downloaded.

          
    

  .. py:method:: failover_db_cluster(**kwargs)

    

    Forces a failover for a DB cluster.

     

    A failover for a DB cluster promotes one of the read-only instances in the DB cluster to the master DB instance (the cluster writer) and deletes the current primary instance.

     

    Amazon Aurora will automatically fail over to a read-only instance, if one exists, when the primary instance fails. You can force a failover when you want to simulate a failure of a DB instance for testing. Because each instance in a DB cluster has its own endpoint address, you will need to clean up and re-establish any existing connections that use those endpoint addresses when the failover is complete.

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.failover_db_cluster(
          DBClusterIdentifier='string',
          TargetDBInstanceIdentifier='string'
      )
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: 

      A DB cluster identifier to force a failover for. This parameter is not case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type TargetDBInstanceIdentifier: string
    :param TargetDBInstanceIdentifier: 

      The name of the instance to promote to the primary instance.

       

      You must specify the instance identifier for an Aurora Replica in the DB cluster. For example, ``mydbcluster-replica1`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBCluster': {
                'AllocatedStorage': 123,
                'AvailabilityZones': [
                    'string',
                ],
                'BackupRetentionPeriod': 123,
                'CharacterSetName': 'string',
                'DatabaseName': 'string',
                'DBClusterIdentifier': 'string',
                'DBClusterParameterGroup': 'string',
                'DBSubnetGroup': 'string',
                'Status': 'string',
                'PercentProgress': 'string',
                'EarliestRestorableTime': datetime(2015, 1, 1),
                'Endpoint': 'string',
                'Engine': 'string',
                'EngineVersion': 'string',
                'LatestRestorableTime': datetime(2015, 1, 1),
                'Port': 123,
                'MasterUsername': 'string',
                'DBClusterOptionGroupMemberships': [
                    {
                        'DBClusterOptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'PreferredBackupWindow': 'string',
                'PreferredMaintenanceWindow': 'string',
                'ReplicationSourceIdentifier': 'string',
                'ReadReplicaIdentifiers': [
                    'string',
                ],
                'DBClusterMembers': [
                    {
                        'DBInstanceIdentifier': 'string',
                        'IsClusterWriter': True|False,
                        'DBClusterParameterGroupStatus': 'string',
                        'PromotionTier': 123
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'HostedZoneId': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbClusterResourceId': 'string',
                'DBClusterArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBCluster** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBCluster   
           
          *  DeleteDBCluster   
           
          *  FailoverDBCluster   
           
          *  ModifyDBCluster   
           
          *  RestoreDBClusterFromSnapshot   
           
          *  RestoreDBClusterToPointInTime   
           

           

          This data type is used as a response element in the  DescribeDBClusters action.

          
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

            
            

            - *(string) --* 
        
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this cluster is associated with.

            
          

          - **DatabaseName** *(string) --* 

            Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster.

            
          

          - **DBClusterParameterGroup** *(string) --* 

            Specifies the name of the DB cluster parameter group for the DB cluster.

            
          

          - **DBSubnetGroup** *(string) --* 

            Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group.

            
          

          - **Status** *(string) --* 

            Specifies the current state of this DB cluster.

            
          

          - **PercentProgress** *(string) --* 

            Specifies the progress of the operation as a percentage.

            
          

          - **EarliestRestorableTime** *(datetime) --* 

            Specifies the earliest time to which a database can be restored with point-in-time restore.

            
          

          - **Endpoint** *(string) --* 

            Specifies the connection endpoint for the primary instance of the DB cluster.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB cluster.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine is listening on.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB cluster.

            
          

          - **DBClusterOptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB cluster.

            
            

            - *(dict) --* 

              Contains status information for a DB cluster option group.

              
              

              - **DBClusterOptionGroupName** *(string) --* 

                Specifies the name of the DB cluster option group.

                
              

              - **Status** *(string) --* 

                Specifies the status of the DB cluster option group.

                
          
        
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **ReplicationSourceIdentifier** *(string) --* 

            Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

            
          

          - **ReadReplicaIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB cluster.

            
            

            - *(string) --* 
        
          

          - **DBClusterMembers** *(list) --* 

            Provides the list of instances that make up the DB cluster.

            
            

            - *(dict) --* 

              Contains information about an instance that is part of a DB cluster.

              
              

              - **DBInstanceIdentifier** *(string) --* 

                Specifies the instance identifier for this member of the DB cluster.

                
              

              - **IsClusterWriter** *(boolean) --* 

                Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

                
              

              - **DBClusterParameterGroupStatus** *(string) --* 

                Specifies the status of the DB cluster parameter group for this member of the DB cluster.

                
              

              - **PromotionTier** *(integer) --* 

                A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides a list of VPC security groups that the DB cluster belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **HostedZoneId** *(string) --* 

            Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

            
          

          - **DbClusterResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed.

            
          

          - **DBClusterArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster.

            
      
    

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

        


  .. py:method:: list_tags_for_resource(**kwargs)

    

    Lists all tags on an Amazon RDS resource.

     

    For an overview on tagging an Amazon RDS resource, see `Tagging Amazon RDS Resources`_ .

    

    **Request Syntax** 
    ::

      response = client.list_tags_for_resource(
          ResourceName='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ]
      )
    :type ResourceName: string
    :param ResourceName: **[REQUIRED]** 

      The Amazon RDS resource with tags to be listed. This value is an Amazon Resource Name (ARN). For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN)`_ .

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    
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

          List of tags returned by the ListTagsForResource operation.

          
          

          - *(dict) --* 

            Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

            
            

            - **Key** *(string) --* 

              A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

              
            

            - **Value** *(string) --* 

              A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

              
        
      
    

  .. py:method:: modify_db_cluster(**kwargs)

    

    Modify a setting for an Amazon Aurora DB cluster. You can change one or more database configuration parameters by specifying these parameters and the new values in the request. For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.modify_db_cluster(
          DBClusterIdentifier='string',
          NewDBClusterIdentifier='string',
          ApplyImmediately=True|False,
          BackupRetentionPeriod=123,
          DBClusterParameterGroupName='string',
          VpcSecurityGroupIds=[
              'string',
          ],
          Port=123,
          MasterUserPassword='string',
          OptionGroupName='string',
          PreferredBackupWindow='string',
          PreferredMaintenanceWindow='string'
      )
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: **[REQUIRED]** 

      The DB cluster identifier for the cluster being modified. This parameter is not case-sensitive.

       

      Constraints:

       

       
      * Must be the identifier for an existing DB cluster. 
       
      * Must contain from 1 to 63 alphanumeric characters or hyphens. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

      

    
    :type NewDBClusterIdentifier: string
    :param NewDBClusterIdentifier: 

      The new DB cluster identifier for the DB cluster when renaming a DB cluster. This value is stored as a lowercase string.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``my-cluster2``  

      

    
    :type ApplyImmediately: boolean
    :param ApplyImmediately: 

      A value that specifies whether the modifications in this request and any pending modifications are asynchronously applied as soon as possible, regardless of the ``PreferredMaintenanceWindow`` setting for the DB cluster. If this parameter is set to ``false`` , changes to the DB cluster are applied during the next maintenance window.

       

      The ``ApplyImmediately`` parameter only affects the ``NewDBClusterIdentifier`` and ``MasterUserPassword`` values. If you set the ``ApplyImmediately`` parameter value to false, then changes to the ``NewDBClusterIdentifier`` and ``MasterUserPassword`` values are applied during the next maintenance window. All other changes are applied immediately, regardless of the value of the ``ApplyImmediately`` parameter.

       

      Default: ``false``  

      

    
    :type BackupRetentionPeriod: integer
    :param BackupRetentionPeriod: 

      The number of days for which automated backups are retained. You must specify a minimum value of 1.

       

      Default: 1

       

      Constraints:

       

       
      * Must be a value from 1 to 35 
       

      

    
    :type DBClusterParameterGroupName: string
    :param DBClusterParameterGroupName: 

      The name of the DB cluster parameter group to use for the DB cluster.

      

    
    :type VpcSecurityGroupIds: list
    :param VpcSecurityGroupIds: 

      A lst of VPC security groups that the DB cluster will belong to.

      

    
      - *(string) --* 

      
  
    :type Port: integer
    :param Port: 

      The port number on which the DB cluster accepts connections.

       

      Constraints: Value must be ``1150-65535``  

       

      Default: The same port as the original DB cluster.

      

    
    :type MasterUserPassword: string
    :param MasterUserPassword: 

      The new password for the master database user. This password can contain any printable ASCII character except "/", """, or "@".

       

      Constraints: Must contain from 8 to 41 characters.

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      A value that indicates that the DB cluster should be associated with the specified option group. Changing this parameter does not result in an outage except in the following case, and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. If the parameter change results in an option group that enables OEM, this change can cause a brief (sub-second) period during which new connections are rejected but existing connections are not interrupted. 

       

      Permanent options cannot be removed from an option group. The option group cannot be removed from a DB cluster once it is associated with a DB cluster.

      

    
    :type PreferredBackupWindow: string
    :param PreferredBackupWindow: 

      The daily time range during which automated backups are created if automated backups are enabled, using the ``BackupRetentionPeriod`` parameter. 

       

      Default: A 30-minute window selected at random from an 8-hour block of time per region. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

       

      Constraints:

       

       
      * Must be in the format ``hh24:mi-hh24:mi`` . 
       
      * Times should be in Universal Coordinated Time (UTC). 
       
      * Must not conflict with the preferred maintenance window. 
       
      * Must be at least 30 minutes. 
       

      

    
    :type PreferredMaintenanceWindow: string
    :param PreferredMaintenanceWindow: 

      The weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

       

      Format: ``ddd:hh24:mi-ddd:hh24:mi``  

       

      Default: A 30-minute window selected at random from an 8-hour block of time per region, occurring on a random day of the week. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

       

      Valid Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun

       

      Constraints: Minimum 30-minute window.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBCluster': {
                'AllocatedStorage': 123,
                'AvailabilityZones': [
                    'string',
                ],
                'BackupRetentionPeriod': 123,
                'CharacterSetName': 'string',
                'DatabaseName': 'string',
                'DBClusterIdentifier': 'string',
                'DBClusterParameterGroup': 'string',
                'DBSubnetGroup': 'string',
                'Status': 'string',
                'PercentProgress': 'string',
                'EarliestRestorableTime': datetime(2015, 1, 1),
                'Endpoint': 'string',
                'Engine': 'string',
                'EngineVersion': 'string',
                'LatestRestorableTime': datetime(2015, 1, 1),
                'Port': 123,
                'MasterUsername': 'string',
                'DBClusterOptionGroupMemberships': [
                    {
                        'DBClusterOptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'PreferredBackupWindow': 'string',
                'PreferredMaintenanceWindow': 'string',
                'ReplicationSourceIdentifier': 'string',
                'ReadReplicaIdentifiers': [
                    'string',
                ],
                'DBClusterMembers': [
                    {
                        'DBInstanceIdentifier': 'string',
                        'IsClusterWriter': True|False,
                        'DBClusterParameterGroupStatus': 'string',
                        'PromotionTier': 123
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'HostedZoneId': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbClusterResourceId': 'string',
                'DBClusterArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBCluster** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBCluster   
           
          *  DeleteDBCluster   
           
          *  FailoverDBCluster   
           
          *  ModifyDBCluster   
           
          *  RestoreDBClusterFromSnapshot   
           
          *  RestoreDBClusterToPointInTime   
           

           

          This data type is used as a response element in the  DescribeDBClusters action.

          
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

            
            

            - *(string) --* 
        
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this cluster is associated with.

            
          

          - **DatabaseName** *(string) --* 

            Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster.

            
          

          - **DBClusterParameterGroup** *(string) --* 

            Specifies the name of the DB cluster parameter group for the DB cluster.

            
          

          - **DBSubnetGroup** *(string) --* 

            Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group.

            
          

          - **Status** *(string) --* 

            Specifies the current state of this DB cluster.

            
          

          - **PercentProgress** *(string) --* 

            Specifies the progress of the operation as a percentage.

            
          

          - **EarliestRestorableTime** *(datetime) --* 

            Specifies the earliest time to which a database can be restored with point-in-time restore.

            
          

          - **Endpoint** *(string) --* 

            Specifies the connection endpoint for the primary instance of the DB cluster.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB cluster.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine is listening on.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB cluster.

            
          

          - **DBClusterOptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB cluster.

            
            

            - *(dict) --* 

              Contains status information for a DB cluster option group.

              
              

              - **DBClusterOptionGroupName** *(string) --* 

                Specifies the name of the DB cluster option group.

                
              

              - **Status** *(string) --* 

                Specifies the status of the DB cluster option group.

                
          
        
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **ReplicationSourceIdentifier** *(string) --* 

            Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

            
          

          - **ReadReplicaIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB cluster.

            
            

            - *(string) --* 
        
          

          - **DBClusterMembers** *(list) --* 

            Provides the list of instances that make up the DB cluster.

            
            

            - *(dict) --* 

              Contains information about an instance that is part of a DB cluster.

              
              

              - **DBInstanceIdentifier** *(string) --* 

                Specifies the instance identifier for this member of the DB cluster.

                
              

              - **IsClusterWriter** *(boolean) --* 

                Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

                
              

              - **DBClusterParameterGroupStatus** *(string) --* 

                Specifies the status of the DB cluster parameter group for this member of the DB cluster.

                
              

              - **PromotionTier** *(integer) --* 

                A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides a list of VPC security groups that the DB cluster belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **HostedZoneId** *(string) --* 

            Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

            
          

          - **DbClusterResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed.

            
          

          - **DBClusterArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster.

            
      
    

  .. py:method:: modify_db_cluster_parameter_group(**kwargs)

    

    Modifies the parameters of a DB cluster parameter group. To modify more than one parameter, submit a list of the following: ``ParameterName`` , ``ParameterValue`` , and ``ApplyMethod`` . A maximum of 20 parameters can be modified in a single request. 

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

     

    .. note::

       

      Changes to dynamic parameters are applied immediately. Changes to static parameters require a reboot without failover to the DB cluster associated with the parameter group before the change can take effect.

       

     

    .. warning::

       

      After you create a DB cluster parameter group, you should wait at least 5 minutes before creating your first DB cluster that uses that DB cluster parameter group as the default parameter group. This allows Amazon RDS to fully complete the create action before the parameter group is used as the default for a new DB cluster. This is especially important for parameters that are critical when creating the default database for a DB cluster, such as the character set for the default database defined by the ``character_set_database`` parameter. You can use the *Parameter Groups* option of the `Amazon RDS console`_ or the  DescribeDBClusterParameters command to verify that your DB cluster parameter group has been created or modified.

       

    

    **Request Syntax** 
    ::

      response = client.modify_db_cluster_parameter_group(
          DBClusterParameterGroupName='string',
          Parameters=[
              {
                  'ParameterName': 'string',
                  'ParameterValue': 'string',
                  'Description': 'string',
                  'Source': 'string',
                  'ApplyType': 'string',
                  'DataType': 'string',
                  'AllowedValues': 'string',
                  'IsModifiable': True|False,
                  'MinimumEngineVersion': 'string',
                  'ApplyMethod': 'immediate'|'pending-reboot'
              },
          ]
      )
    :type DBClusterParameterGroupName: string
    :param DBClusterParameterGroupName: **[REQUIRED]** 

      The name of the DB cluster parameter group to modify.

      

    
    :type Parameters: list
    :param Parameters: **[REQUIRED]** 

      A list of parameters in the DB cluster parameter group to modify.

      

    
      - *(dict) --* 

        This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

         

        This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

        

      
        - **ParameterName** *(string) --* 

          Specifies the name of the parameter.

          

        
        - **ParameterValue** *(string) --* 

          Specifies the value of the parameter.

          

        
        - **Description** *(string) --* 

          Provides a description of the parameter.

          

        
        - **Source** *(string) --* 

          Indicates the source of the parameter value.

          

        
        - **ApplyType** *(string) --* 

          Specifies the engine specific parameters type.

          

        
        - **DataType** *(string) --* 

          Specifies the valid data type for the parameter.

          

        
        - **AllowedValues** *(string) --* 

          Specifies the valid range of values for the parameter.

          

        
        - **IsModifiable** *(boolean) --* 

          Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

          

        
        - **MinimumEngineVersion** *(string) --* 

          The earliest engine version to which the parameter can apply.

          

        
        - **ApplyMethod** *(string) --* 

          Indicates when to apply parameter updates.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBClusterParameterGroupName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        

        
        

        - **DBClusterParameterGroupName** *(string) --* 

          The name of the DB cluster parameter group.

           

          Constraints:

           

           
          * Must be 1 to 255 alphanumeric characters 
           
          * First character must be a letter 
           
          * Cannot end with a hyphen or contain two consecutive hyphens 
           

           

          .. note::

             

            This value is stored as a lowercase string.

             

          
    

  .. py:method:: modify_db_cluster_snapshot_attribute(**kwargs)

    

    Adds an attribute and values to, or removes an attribute and values from, a manual DB cluster snapshot.

     

    To share a manual DB cluster snapshot with other AWS accounts, specify ``restore`` as the ``AttributeName`` and use the ``ValuesToAdd`` parameter to add a list of IDs of the AWS accounts that are authorized to restore the manual DB cluster snapshot. Use the value ``all`` to make the manual DB cluster snapshot public, which means that it can be copied or restored by all AWS accounts. Do not add the ``all`` value for any manual DB cluster snapshots that contain private information that you don't want available to all AWS accounts.

     

    To view which AWS accounts have access to copy or restore a manual DB cluster snapshot, or whether a manual DB cluster snapshot public or private, use the  DescribeDBClusterSnapshotAttributes API action.

     

    If a manual DB cluster snapshot is encrypted, it cannot be shared.

    

    **Request Syntax** 
    ::

      response = client.modify_db_cluster_snapshot_attribute(
          DBClusterSnapshotIdentifier='string',
          AttributeName='string',
          ValuesToAdd=[
              'string',
          ],
          ValuesToRemove=[
              'string',
          ]
      )
    :type DBClusterSnapshotIdentifier: string
    :param DBClusterSnapshotIdentifier: **[REQUIRED]** 

      The identifier for the DB cluster snapshot to modify the attributes for.

      

    
    :type AttributeName: string
    :param AttributeName: **[REQUIRED]** 

      The name of the DB cluster snapshot attribute to modify.

       

      To manage authorization for other AWS accounts to copy or restore a manual DB cluster snapshot, set this value to ``restore`` .

      

    
    :type ValuesToAdd: list
    :param ValuesToAdd: 

      A list of DB cluster snapshot attributes to add to the attribute specified by ``AttributeName`` .

       

      To authorize other AWS accounts to copy or restore a manual DB cluster snapshot, set this list to include one or more AWS account IDs, or ``all`` to make the manual DB cluster snapshot restorable by any AWS account. Do not add the ``all`` value for any manual DB cluster snapshots that contain private information that you don't want available to all AWS accounts.

      

    
      - *(string) --* 

      
  
    :type ValuesToRemove: list
    :param ValuesToRemove: 

      A list of DB cluster snapshot attributes to remove from the attribute specified by ``AttributeName`` .

       

      To remove authorization for other AWS accounts to copy or restore a manual DB cluster snapshot, set this list to include one or more AWS account identifiers, or ``all`` to remove authorization for any AWS account to copy or restore the DB cluster snapshot. If you specify ``all`` , an AWS account whose account ID is explicitly added to the ``restore`` attribute can still copy or restore a manual DB cluster snapshot.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBClusterSnapshotAttributesResult': {
                'DBClusterSnapshotIdentifier': 'string',
                'DBClusterSnapshotAttributes': [
                    {
                        'AttributeName': 'string',
                        'AttributeValues': [
                            'string',
                        ]
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBClusterSnapshotAttributesResult** *(dict) --* 

          Contains the results of a successful call to the  DescribeDBClusterSnapshotAttributes API action.

           

          Manual DB cluster snapshot attributes are used to authorize other AWS accounts to copy or restore a manual DB cluster snapshot. For more information, see the  ModifyDBClusterSnapshotAttribute API action.

          
          

          - **DBClusterSnapshotIdentifier** *(string) --* 

            The identifier of the manual DB cluster snapshot that the attributes apply to.

            
          

          - **DBClusterSnapshotAttributes** *(list) --* 

            The list of attributes and values for the manual DB cluster snapshot.

            
            

            - *(dict) --* 

              Contains the name and values of a manual DB cluster snapshot attribute.

               

              Manual DB cluster snapshot attributes are used to authorize other AWS accounts to restore a manual DB cluster snapshot. For more information, see the  ModifyDBClusterSnapshotAttribute API action.

              
              

              - **AttributeName** *(string) --* 

                The name of the manual DB cluster snapshot attribute.

                 

                The attribute named ``restore`` refers to the list of AWS accounts that have permission to copy or restore the manual DB cluster snapshot. For more information, see the  ModifyDBClusterSnapshotAttribute API action.

                
              

              - **AttributeValues** *(list) --* 

                The value(s) for the manual DB cluster snapshot attribute.

                 

                If the ``AttributeName`` field is set to ``restore`` , then this element returns a list of IDs of the AWS accounts that are authorized to copy or restore the manual DB cluster snapshot. If a value of ``all`` is in the list, then the manual DB cluster snapshot is public and available for any AWS account to copy or restore.

                
                

                - *(string) --* 
            
          
        
      
    

  .. py:method:: modify_db_instance(**kwargs)

    

    Modifies settings for a DB instance. You can change one or more database configuration parameters by specifying these parameters and the new values in the request.

    

    **Request Syntax** 
    ::

      response = client.modify_db_instance(
          DBInstanceIdentifier='string',
          AllocatedStorage=123,
          DBInstanceClass='string',
          DBSubnetGroupName='string',
          DBSecurityGroups=[
              'string',
          ],
          VpcSecurityGroupIds=[
              'string',
          ],
          ApplyImmediately=True|False,
          MasterUserPassword='string',
          DBParameterGroupName='string',
          BackupRetentionPeriod=123,
          PreferredBackupWindow='string',
          PreferredMaintenanceWindow='string',
          MultiAZ=True|False,
          EngineVersion='string',
          AllowMajorVersionUpgrade=True|False,
          AutoMinorVersionUpgrade=True|False,
          LicenseModel='string',
          Iops=123,
          OptionGroupName='string',
          NewDBInstanceIdentifier='string',
          StorageType='string',
          TdeCredentialArn='string',
          TdeCredentialPassword='string',
          CACertificateIdentifier='string',
          Domain='string',
          CopyTagsToSnapshot=True|False,
          MonitoringInterval=123,
          DBPortNumber=123,
          PubliclyAccessible=True|False,
          MonitoringRoleArn='string',
          DomainIAMRoleName='string',
          PromotionTier=123
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The DB instance identifier. This value is stored as a lowercase string.

       

      Constraints:

       

       
      * Must be the identifier for an existing DB instance 
       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type AllocatedStorage: integer
    :param AllocatedStorage: 

      The new storage capacity of the RDS instance. Changing this setting does not result in an outage and the change is applied during the next maintenance window unless ``ApplyImmediately`` is set to ``true`` for this request. 

       

       **MySQL**  

       

      Default: Uses existing setting

       

      Valid Values: 5-6144

       

      Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value.

       

      Type: Integer

       

       **MariaDB**  

       

      Default: Uses existing setting

       

      Valid Values: 5-6144

       

      Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value.

       

      Type: Integer

       

       **PostgreSQL**  

       

      Default: Uses existing setting

       

      Valid Values: 5-6144

       

      Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value.

       

      Type: Integer

       

       **Oracle**  

       

      Default: Uses existing setting

       

      Valid Values: 10-6144

       

      Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value.

       

       **SQL Server**  

       

      Cannot be modified.

       

      If you choose to migrate your DB instance from using standard storage to using Provisioned IOPS, or from using Provisioned IOPS to using standard storage, the process can take time. The duration of the migration depends on several factors such as database load, storage size, storage type (standard or Provisioned IOPS), amount of IOPS provisioned (if any), and the number of prior scale storage operations. Typical migration times are under 24 hours, but the process can take up to several days in some cases. During the migration, the DB instance will be available for use, but might experience performance degradation. While the migration takes place, nightly backups for the instance will be suspended. No other Amazon RDS operations can take place for the instance, including modifying the instance, rebooting the instance, deleting the instance, creating a Read Replica for the instance, and creating a DB snapshot of the instance.

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The new compute and memory capacity of the DB instance. To determine the instance classes that are available for a particular DB engine, use the  DescribeOrderableDBInstanceOptions action. 

       

      Passing a value for this setting causes an outage during the change and is applied during the next maintenance window, unless ``ApplyImmediately`` is specified as ``true`` for this request. 

       

      Default: Uses existing setting

       

      Valid Values: ``db.t1.micro | db.m1.small | db.m1.medium | db.m1.large | db.m1.xlarge | db.m2.xlarge | db.m2.2xlarge | db.m2.4xlarge | db.m3.medium | db.m3.large | db.m3.xlarge | db.m3.2xlarge | db.m4.large | db.m4.xlarge | db.m4.2xlarge | db.m4.4xlarge | db.m4.10xlarge | db.r3.large | db.r3.xlarge | db.r3.2xlarge | db.r3.4xlarge | db.r3.8xlarge | db.t2.micro | db.t2.small | db.t2.medium | db.t2.large``  

      

    
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      The new DB subnet group for the DB instance. You can use this parameter to move your DB instance to a different VPC, or to a different subnet group in the same VPC. If your DB instance is not in a VPC, you can also use this parameter to move your DB instance into a VPC. For more information, see `Updating the VPC for a DB Instance`_ . 

       

      Changing the subnet group causes an outage during the change. The change is applied during the next maintenance window, unless you specify ``true`` for the ``ApplyImmediately`` parameter. 

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens.

       

      Example: ``mySubnetGroup``  

      

    
    :type DBSecurityGroups: list
    :param DBSecurityGroups: 

      A list of DB security groups to authorize on this DB instance. Changing this setting does not result in an outage and the change is asynchronously applied as soon as possible.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
      - *(string) --* 

      
  
    :type VpcSecurityGroupIds: list
    :param VpcSecurityGroupIds: 

      A list of EC2 VPC security groups to authorize on this DB instance. This change is asynchronously applied as soon as possible.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
      - *(string) --* 

      
  
    :type ApplyImmediately: boolean
    :param ApplyImmediately: 

      Specifies whether the modifications in this request and any pending modifications are asynchronously applied as soon as possible, regardless of the ``PreferredMaintenanceWindow`` setting for the DB instance. 

       

      If this parameter is set to ``false`` , changes to the DB instance are applied during the next maintenance window. Some parameter changes can cause an outage and will be applied on the next call to  RebootDBInstance , or the next failure reboot. Review the table of parameters in `Modifying a DB Instance and Using the Apply Immediately Parameter`_ to see the impact that setting ``ApplyImmediately`` to ``true`` or ``false`` has for each modified parameter and to determine when the changes will be applied. 

       

      Default: ``false``  

      

    
    :type MasterUserPassword: string
    :param MasterUserPassword: 

      The new password for the DB instance master user. Can be any printable ASCII character except "/", """, or "@".

       

      Changing this parameter does not result in an outage and the change is asynchronously applied as soon as possible. Between the time of the request and the completion of the request, the ``MasterUserPassword`` element exists in the ``PendingModifiedValues`` element of the operation response. 

       

      Default: Uses existing setting

       

      Constraints: Must be 8 to 41 alphanumeric characters (MySQL, MariaDB, and Amazon Aurora), 8 to 30 alphanumeric characters (Oracle), or 8 to 128 alphanumeric characters (SQL Server).

       

      .. note::

         

        Amazon RDS API actions never return the password, so this action provides a way to regain access to a primary instance user if the password is lost. This includes restoring privileges that might have been accidentally revoked.

         

      

    
    :type DBParameterGroupName: string
    :param DBParameterGroupName: 

      The name of the DB parameter group to apply to the DB instance. Changing this setting does not result in an outage. The parameter group name itself is changed immediately, but the actual parameter changes are not applied until you reboot the instance without failover. The db instance will NOT be rebooted automatically and the parameter changes will NOT be applied during the next maintenance window.

       

      Default: Uses existing setting

       

      Constraints: The DB parameter group must be in the same DB parameter group family as this DB instance.

      

    
    :type BackupRetentionPeriod: integer
    :param BackupRetentionPeriod: 

      The number of days to retain automated backups. Setting this parameter to a positive number enables backups. Setting this parameter to 0 disables automated backups.

       

      Changing this parameter can result in an outage if you change from 0 to a non-zero value or from a non-zero value to 0. These changes are applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. If you change the parameter from one non-zero value to another non-zero value, the change is asynchronously applied as soon as possible.

       

      Default: Uses existing setting

       

      Constraints:

       

       
      * Must be a value from 0 to 35 
       
      * Can be specified for a MySQL Read Replica only if the source is running MySQL 5.6 
       
      * Can be specified for a PostgreSQL Read Replica only if the source is running PostgreSQL 9.3.5 
       
      * Cannot be set to 0 if the DB instance is a source to Read Replicas 
       

      

    
    :type PreferredBackupWindow: string
    :param PreferredBackupWindow: 

      The daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` parameter. Changing this parameter does not result in an outage and the change is asynchronously applied as soon as possible. 

       

      Constraints:

       

       
      * Must be in the format hh24:mi-hh24:mi 
       
      * Times should be in Universal Time Coordinated (UTC) 
       
      * Must not conflict with the preferred maintenance window 
       
      * Must be at least 30 minutes 
       

      

    
    :type PreferredMaintenanceWindow: string
    :param PreferredMaintenanceWindow: 

      The weekly time range (in UTC) during which system maintenance can occur, which might result in an outage. Changing this parameter does not result in an outage, except in the following situation, and the change is asynchronously applied as soon as possible. If there are pending actions that cause a reboot, and the maintenance window is changed to include the current time, then changing this parameter will cause a reboot of the DB instance. If moving this window to the current time, there must be at least 30 minutes between the current time and end of the window to ensure pending changes are applied.

       

      Default: Uses existing setting

       

      Format: ddd:hh24:mi-ddd:hh24:mi

       

      Valid Days: Mon | Tue | Wed | Thu | Fri | Sat | Sun

       

      Constraints: Must be at least 30 minutes

      

    
    :type MultiAZ: boolean
    :param MultiAZ: 

      Specifies if the DB instance is a Multi-AZ deployment. Changing this parameter does not result in an outage and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. 

       

      Constraints: Cannot be specified if the DB instance is a Read Replica.

      

    
    :type EngineVersion: string
    :param EngineVersion: 

      The version number of the database engine to upgrade to. Changing this parameter results in an outage and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. 

       

      For major version upgrades, if a non-default DB parameter group is currently in use, a new DB parameter group in the DB parameter group family for the new engine version must be specified. The new DB parameter group can be the default for that DB parameter group family.

       

      For a list of valid engine versions, see  CreateDBInstance .

      

    
    :type AllowMajorVersionUpgrade: boolean
    :param AllowMajorVersionUpgrade: 

      Indicates that major version upgrades are allowed. Changing this parameter does not result in an outage and the change is asynchronously applied as soon as possible.

       

      Constraints: This parameter must be set to true when specifying a value for the EngineVersion parameter that is a different major version than the DB instance's current version.

      

    
    :type AutoMinorVersionUpgrade: boolean
    :param AutoMinorVersionUpgrade: 

      Indicates that minor version upgrades will be applied automatically to the DB instance during the maintenance window. Changing this parameter does not result in an outage except in the following case and the change is asynchronously applied as soon as possible. An outage will result if this parameter is set to ``true`` during the maintenance window, and a newer minor version is available, and RDS has enabled auto patching for that engine version. 

      

    
    :type LicenseModel: string
    :param LicenseModel: 

      The license model for the DB instance.

       

      Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

      

    
    :type Iops: integer
    :param Iops: 

      The new Provisioned IOPS (I/O operations per second) value for the RDS instance. Changing this setting does not result in an outage and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. 

       

      Default: Uses existing setting

       

      Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value. If you are migrating from Provisioned IOPS to standard storage, set this value to 0. The DB instance will require a reboot for the change in storage type to take effect.

       

       **SQL Server**  

       

      Setting the IOPS value for the SQL Server database engine is not supported.

       

      Type: Integer

       

      If you choose to migrate your DB instance from using standard storage to using Provisioned IOPS, or from using Provisioned IOPS to using standard storage, the process can take time. The duration of the migration depends on several factors such as database load, storage size, storage type (standard or Provisioned IOPS), amount of IOPS provisioned (if any), and the number of prior scale storage operations. Typical migration times are under 24 hours, but the process can take up to several days in some cases. During the migration, the DB instance will be available for use, but might experience performance degradation. While the migration takes place, nightly backups for the instance will be suspended. No other Amazon RDS operations can take place for the instance, including modifying the instance, rebooting the instance, deleting the instance, creating a Read Replica for the instance, and creating a DB snapshot of the instance.

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      Indicates that the DB instance should be associated with the specified option group. Changing this parameter does not result in an outage except in the following case and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. If the parameter change results in an option group that enables OEM, this change can cause a brief (sub-second) period during which new connections are rejected but existing connections are not interrupted. 

       

      Permanent options, such as the TDE option for Oracle Advanced Security TDE, cannot be removed from an option group, and that option group cannot be removed from a DB instance once it is associated with a DB instance

      

    
    :type NewDBInstanceIdentifier: string
    :param NewDBInstanceIdentifier: 

      The new DB instance identifier for the DB instance when renaming a DB instance. When you change the DB instance identifier, an instance reboot will occur immediately if you set ``Apply Immediately`` to true, or will occur during the next maintenance window if ``Apply Immediately`` to false. This value is stored as a lowercase string. 

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type StorageType: string
    :param StorageType: 

      Specifies the storage type to be associated with the DB instance.

       

      Valid values: ``standard | gp2 | io1``  

       

      If you specify ``io1`` , you must also include a value for the ``Iops`` parameter. 

       

      Default: ``io1`` if the ``Iops`` parameter is specified; otherwise ``standard``  

      

    
    :type TdeCredentialArn: string
    :param TdeCredentialArn: 

      The ARN from the Key Store with which to associate the instance for TDE encryption.

      

    
    :type TdeCredentialPassword: string
    :param TdeCredentialPassword: 

      The password for the given ARN from the Key Store in order to access the device.

      

    
    :type CACertificateIdentifier: string
    :param CACertificateIdentifier: 

      Indicates the certificate that needs to be associated with the instance.

      

    
    :type Domain: string
    :param Domain: 

      Specify the Active Directory Domain to move the instance to.

       

      The specified Active Directory Domain must be created prior to this operation. Currently only a SQL Server instance can be created in a Active Directory Domain.

      

    
    :type CopyTagsToSnapshot: boolean
    :param CopyTagsToSnapshot: 

      True to copy all tags from the DB instance to snapshots of the DB instance; otherwise false. The default is false.

      

    
    :type MonitoringInterval: integer
    :param MonitoringInterval: 

      The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance. To disable collecting Enhanced Monitoring metrics, specify 0. The default is 0.

       

      If ``MonitoringRoleArn`` is specified, then you must also set ``MonitoringInterval`` to a value other than 0.

       

      Valid Values: ``0, 1, 5, 10, 15, 30, 60``  

      

    
    :type DBPortNumber: integer
    :param DBPortNumber: 

      The port number on which the database accepts connections.

       

      The value of the ``DBPortNumber`` parameter must not match any of the port values specified for options in the option group for the DB instance.

       

      Your database will restart when you change the ``DBPortNumber`` value regardless of the value of the ``ApplyImmediately`` parameter.

       

       **MySQL**  

       

      Default: ``3306``  

       

      Valid Values: ``1150-65535``  

       

       **MariaDB**  

       

      Default: ``3306``  

       

      Valid Values: ``1150-65535``  

       

       **PostgreSQL**  

       

      Default: ``5432``  

       

      Valid Values: ``1150-65535``  

       

      Type: Integer

       

       **Oracle**  

       

      Default: ``1521``  

       

      Valid Values: ``1150-65535``  

       

       **SQL Server**  

       

      Default: ``1433``  

       

      Valid Values: ``1150-65535`` except for ``1434`` , ``3389`` , ``47001`` , ``49152`` , and ``49152`` through ``49156`` . 

       

       **Amazon Aurora**  

       

      Default: ``3306``  

       

      Valid Values: ``1150-65535``  

      

    
    :type PubliclyAccessible: boolean
    :param PubliclyAccessible: 

      Boolean value that indicates if the DB instance has a publicly resolvable DNS name. Set to ``True`` to make the DB instance Internet-facing with a publicly resolvable DNS name, which resolves to a public IP address. Set to ``False`` to make the DB instance internal with a DNS name that resolves to a private IP address. 

       

       ``PubliclyAccessible`` only applies to DB instances in a VPC. The DB instance must be part of a public subnet and ``PubliclyAccessible`` must be true in order for it to be publicly accessible. 

       

      Changes to the ``PubliclyAccessible`` parameter are applied immediately regardless of the value of the ``ApplyImmediately`` parameter.

       

      Default: false

      

    
    :type MonitoringRoleArn: string
    :param MonitoringRoleArn: 

      The ARN for the IAM role that permits RDS to send enhanced monitoring metrics to CloudWatch Logs. For example, ``arn:aws:iam:123456789012:role/emaccess`` . For information on creating a monitoring role, go to `To create an IAM role for Amazon RDS Enhanced Monitoring`_ .

       

      If ``MonitoringInterval`` is set to a value other than 0, then you must supply a ``MonitoringRoleArn`` value.

      

    
    :type DomainIAMRoleName: string
    :param DomainIAMRoleName: 

      Specify the name of the IAM role to be used when making API calls to the Directory Service.

      

    
    :type PromotionTier: integer
    :param PromotionTier: 

      A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

       

      Default: 1

       

      Valid Values: 0 - 15

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBInstance': {
                'DBInstanceIdentifier': 'string',
                'DBInstanceClass': 'string',
                'Engine': 'string',
                'DBInstanceStatus': 'string',
                'MasterUsername': 'string',
                'DBName': 'string',
                'Endpoint': {
                    'Address': 'string',
                    'Port': 123,
                    'HostedZoneId': 'string'
                },
                'AllocatedStorage': 123,
                'InstanceCreateTime': datetime(2015, 1, 1),
                'PreferredBackupWindow': 'string',
                'BackupRetentionPeriod': 123,
                'DBSecurityGroups': [
                    {
                        'DBSecurityGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'DBParameterGroups': [
                    {
                        'DBParameterGroupName': 'string',
                        'ParameterApplyStatus': 'string'
                    },
                ],
                'AvailabilityZone': 'string',
                'DBSubnetGroup': {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
                'PreferredMaintenanceWindow': 'string',
                'PendingModifiedValues': {
                    'DBInstanceClass': 'string',
                    'AllocatedStorage': 123,
                    'MasterUserPassword': 'string',
                    'Port': 123,
                    'BackupRetentionPeriod': 123,
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'DBInstanceIdentifier': 'string',
                    'StorageType': 'string',
                    'CACertificateIdentifier': 'string',
                    'DBSubnetGroupName': 'string'
                },
                'LatestRestorableTime': datetime(2015, 1, 1),
                'MultiAZ': True|False,
                'EngineVersion': 'string',
                'AutoMinorVersionUpgrade': True|False,
                'ReadReplicaSourceDBInstanceIdentifier': 'string',
                'ReadReplicaDBInstanceIdentifiers': [
                    'string',
                ],
                'LicenseModel': 'string',
                'Iops': 123,
                'OptionGroupMemberships': [
                    {
                        'OptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'CharacterSetName': 'string',
                'SecondaryAvailabilityZone': 'string',
                'PubliclyAccessible': True|False,
                'StatusInfos': [
                    {
                        'StatusType': 'string',
                        'Normal': True|False,
                        'Status': 'string',
                        'Message': 'string'
                    },
                ],
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'DbInstancePort': 123,
                'DBClusterIdentifier': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbiResourceId': 'string',
                'CACertificateIdentifier': 'string',
                'DomainMemberships': [
                    {
                        'Domain': 'string',
                        'Status': 'string',
                        'FQDN': 'string',
                        'IAMRoleName': 'string'
                    },
                ],
                'CopyTagsToSnapshot': True|False,
                'MonitoringInterval': 123,
                'EnhancedMonitoringResourceArn': 'string',
                'MonitoringRoleArn': 'string',
                'PromotionTier': 123,
                'DBInstanceArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBInstance** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBInstance   
           
          *  DeleteDBInstance   
           
          *  ModifyDBInstance   
           

           

          This data type is used as a response element in the  DescribeDBInstances action.

          
          

          - **DBInstanceIdentifier** *(string) --* 

            Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

            
          

          - **DBInstanceClass** *(string) --* 

            Contains the name of the compute and memory capacity class of the DB instance.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB instance.

            
          

          - **DBInstanceStatus** *(string) --* 

            Specifies the current state of this database.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB instance.

            
          

          - **DBName** *(string) --* 

            The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

             

             **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

             

            Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

             

            Type: String

             

             **Oracle**  

             

            Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

            
          

          - **Endpoint** *(dict) --* 

            Specifies the connection endpoint.

            
            

            - **Address** *(string) --* 

              Specifies the DNS address of the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine is listening on.

              
            

            - **HostedZoneId** *(string) --* 

              Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

              
        
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size specified in gigabytes.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Provides the date and time the DB instance was created.

            
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **DBSecurityGroups** *(list) --* 

            Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               
              *  RestoreDBInstanceToPointInTime   
               

              
              

              - **DBSecurityGroupName** *(string) --* 

                The name of the DB security group.

                
              

              - **Status** *(string) --* 

                The status of the DB security group.

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides List of VPC security group elements that the DB instance belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **DBParameterGroups** *(list) --* 

            Provides the list of DB parameter groups applied to this DB instance.

            
            

            - *(dict) --* 

              The status of the DB parameter group.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateDBInstance   
               
              *  CreateDBInstanceReadReplica   
               
              *  DeleteDBInstance   
               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               

              
              

              - **DBParameterGroupName** *(string) --* 

                The name of the DP parameter group.

                
              

              - **ParameterApplyStatus** *(string) --* 

                The status of parameter updates.

                
          
        
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance is located in.

            
          

          - **DBSubnetGroup** *(dict) --* 

            Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **PendingModifiedValues** *(dict) --* 

            Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

            
            

            - **DBInstanceClass** *(string) --* 

              Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

              
            

            - **AllocatedStorage** *(integer) --* 

              Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

              
            

            - **MasterUserPassword** *(string) --* 

              Contains the pending or in-progress change of the master credentials for the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the pending port for the DB instance.

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the pending number of days for which automated backups are retained.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the DB instance.

               

              Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

              
            

            - **Iops** *(integer) --* 

              Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type to be associated with the DB instance.

              
            

            - **CACertificateIdentifier** *(string) --* 

              Specifies the identifier of the CA certificate for the DB instance.

              
            

            - **DBSubnetGroupName** *(string) --* 

              The new DB subnet group for the DB instance. 

              
        
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **MultiAZ** *(boolean) --* 

            Specifies if the DB instance is a Multi-AZ deployment.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **AutoMinorVersionUpgrade** *(boolean) --* 

            Indicates that minor version patches are applied automatically.

            
          

          - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

            Contains the identifier of the source DB instance if this DB instance is a Read Replica.

            
          

          - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB instance.

            
            

            - *(string) --* 
        
          

          - **LicenseModel** *(string) --* 

            License model information for this DB instance.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value.

            
          

          - **OptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB instance.

            
            

            - *(dict) --* 

              Provides information on the option groups the DB instance is a member of.

              
              

              - **OptionGroupName** *(string) --* 

                The name of the option group that the instance belongs to.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                
          
        
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this instance is associated with.

            
          

          - **SecondaryAvailabilityZone** *(string) --* 

            If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

            
          

          - **PubliclyAccessible** *(boolean) --* 

            Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

             

            Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

             

             
            * **Default VPC:** true 
             
            * **VPC:** false 
             

             

            If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

            
          

          - **StatusInfos** *(list) --* 

            The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

            
            

            - *(dict) --* 

              Provides a list of status information for a DB instance.

              
              

              - **StatusType** *(string) --* 

                This value is currently "read replication."

                
              

              - **Normal** *(boolean) --* 

                Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                
              

              - **Status** *(string) --* 

                Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                
              

              - **Message** *(string) --* 

                Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                
          
        
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB instance.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which the instance is associated for TDE encryption.

            
          

          - **DbInstancePort** *(integer) --* 

            Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

            
          

          - **DBClusterIdentifier** *(string) --* 

            If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB instance is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

            
          

          - **DbiResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

            
          

          - **CACertificateIdentifier** *(string) --* 

            The identifier of the CA certificate for this DB instance.

            
          

          - **DomainMemberships** *(list) --* 

            The Active Directory Domain membership records associated with the DB instance.

            
            

            - *(dict) --* 

              An Active Directory Domain membership record associated with the DB instance.

              
              

              - **Domain** *(string) --* 

                The identifier of the Active Directory Domain.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                
              

              - **FQDN** *(string) --* 

                The fully qualified domain name of the Active Directory Domain.

                
              

              - **IAMRoleName** *(string) --* 

                The name of the IAM role to be used when making API calls to the Directory Service.

                
          
        
          

          - **CopyTagsToSnapshot** *(boolean) --* 

            Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

            
          

          - **MonitoringInterval** *(integer) --* 

            The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

            
          

          - **EnhancedMonitoringResourceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

            
          

          - **MonitoringRoleArn** *(string) --* 

            The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

            
          

          - **PromotionTier** *(integer) --* 

            A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

            
          

          - **DBInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB instance.

            
      
    

  .. py:method:: modify_db_parameter_group(**kwargs)

    

    Modifies the parameters of a DB parameter group. To modify more than one parameter, submit a list of the following: ``ParameterName`` , ``ParameterValue`` , and ``ApplyMethod`` . A maximum of 20 parameters can be modified in a single request. 

     

    .. note::

       

      Changes to dynamic parameters are applied immediately. Changes to static parameters require a reboot without failover to the DB instance associated with the parameter group before the change can take effect.

       

     

    .. warning::

       

      After you modify a DB parameter group, you should wait at least 5 minutes before creating your first DB instance that uses that DB parameter group as the default parameter group. This allows Amazon RDS to fully complete the modify action before the parameter group is used as the default for a new DB instance. This is especially important for parameters that are critical when creating the default database for a DB instance, such as the character set for the default database defined by the ``character_set_database`` parameter. You can use the *Parameter Groups* option of the `Amazon RDS console`_ or the *DescribeDBParameters* command to verify that your DB parameter group has been created or modified.

       

    

    **Request Syntax** 
    ::

      response = client.modify_db_parameter_group(
          DBParameterGroupName='string',
          Parameters=[
              {
                  'ParameterName': 'string',
                  'ParameterValue': 'string',
                  'Description': 'string',
                  'Source': 'string',
                  'ApplyType': 'string',
                  'DataType': 'string',
                  'AllowedValues': 'string',
                  'IsModifiable': True|False,
                  'MinimumEngineVersion': 'string',
                  'ApplyMethod': 'immediate'|'pending-reboot'
              },
          ]
      )
    :type DBParameterGroupName: string
    :param DBParameterGroupName: **[REQUIRED]** 

      The name of the DB parameter group.

       

      Constraints:

       

       
      * Must be the name of an existing DB parameter group 
       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Parameters: list
    :param Parameters: **[REQUIRED]** 

      An array of parameter names, values, and the apply method for the parameter update. At least one parameter name, value, and apply method must be supplied; subsequent arguments are optional. A maximum of 20 parameters can be modified in a single request.

       

      Valid Values (for the application method): ``immediate | pending-reboot``  

       

      .. note::

         

        You can use the immediate value with dynamic parameters only. You can use the pending-reboot value for both dynamic and static parameters, and changes are applied when you reboot the DB instance without failover.

         

      

    
      - *(dict) --* 

        This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

         

        This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

        

      
        - **ParameterName** *(string) --* 

          Specifies the name of the parameter.

          

        
        - **ParameterValue** *(string) --* 

          Specifies the value of the parameter.

          

        
        - **Description** *(string) --* 

          Provides a description of the parameter.

          

        
        - **Source** *(string) --* 

          Indicates the source of the parameter value.

          

        
        - **ApplyType** *(string) --* 

          Specifies the engine specific parameters type.

          

        
        - **DataType** *(string) --* 

          Specifies the valid data type for the parameter.

          

        
        - **AllowedValues** *(string) --* 

          Specifies the valid range of values for the parameter.

          

        
        - **IsModifiable** *(boolean) --* 

          Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

          

        
        - **MinimumEngineVersion** *(string) --* 

          The earliest engine version to which the parameter can apply.

          

        
        - **ApplyMethod** *(string) --* 

          Indicates when to apply parameter updates.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBParameterGroupName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  ModifyDBParameterGroup or  ResetDBParameterGroup action. 

        
        

        - **DBParameterGroupName** *(string) --* 

          Provides the name of the DB parameter group.

          
    

  .. py:method:: modify_db_snapshot_attribute(**kwargs)

    

    Adds an attribute and values to, or removes an attribute and values from, a manual DB snapshot.

     

    To share a manual DB snapshot with other AWS accounts, specify ``restore`` as the ``AttributeName`` and use the ``ValuesToAdd`` parameter to add a list of IDs of the AWS accounts that are authorized to restore the manual DB snapshot. Uses the value ``all`` to make the manual DB snapshot public, which means it can be copied or restored by all AWS accounts. Do not add the ``all`` value for any manual DB snapshots that contain private information that you don't want available to all AWS accounts.

     

    To view which AWS accounts have access to copy or restore a manual DB snapshot, or whether a manual DB snapshot public or private, use the  DescribeDBSnapshotAttributes API action.

     

    If the manual DB snapshot is encrypted, it cannot be shared.

    

    **Request Syntax** 
    ::

      response = client.modify_db_snapshot_attribute(
          DBSnapshotIdentifier='string',
          AttributeName='string',
          ValuesToAdd=[
              'string',
          ],
          ValuesToRemove=[
              'string',
          ]
      )
    :type DBSnapshotIdentifier: string
    :param DBSnapshotIdentifier: **[REQUIRED]** 

      The identifier for the DB snapshot to modify the attributes for.

      

    
    :type AttributeName: string
    :param AttributeName: **[REQUIRED]** 

      The name of the DB snapshot attribute to modify.

       

      To manage authorization for other AWS accounts to copy or restore a manual DB snapshot, set this value to ``restore`` .

      

    
    :type ValuesToAdd: list
    :param ValuesToAdd: 

      A list of DB snapshot attributes to add to the attribute specified by ``AttributeName`` .

       

      To authorize other AWS accounts to copy or restore a manual snapshot, set this list to include one or more AWS account IDs, or ``all`` to make the manual DB snapshot restorable by any AWS account. Do not add the ``all`` value for any manual DB snapshots that contain private information that you don't want available to all AWS accounts.

      

    
      - *(string) --* 

      
  
    :type ValuesToRemove: list
    :param ValuesToRemove: 

      A list of DB snapshot attributes to remove from the attribute specified by ``AttributeName`` .

       

      To remove authorization for other AWS accounts to copy or restore a manual snapshot, set this list to include one or more AWS account identifiers, or ``all`` to remove authorization for any AWS account to copy or restore the DB snapshot. If you specify ``all`` , an AWS account whose account ID is explicitly added to the ``restore`` attribute can still copy or restore the manual DB snapshot.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSnapshotAttributesResult': {
                'DBSnapshotIdentifier': 'string',
                'DBSnapshotAttributes': [
                    {
                        'AttributeName': 'string',
                        'AttributeValues': [
                            'string',
                        ]
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSnapshotAttributesResult** *(dict) --* 

          Contains the results of a successful call to the  DescribeDBSnapshotAttributes API action.

           

          Manual DB snapshot attributes are used to authorize other AWS accounts to copy or restore a manual DB snapshot. For more information, see the  ModifyDBSnapshotAttribute API action.

          
          

          - **DBSnapshotIdentifier** *(string) --* 

            The identifier of the manual DB snapshot that the attributes apply to.

            
          

          - **DBSnapshotAttributes** *(list) --* 

            The list of attributes and values for the manual DB snapshot.

            
            

            - *(dict) --* 

              Contains the name and values of a manual DB snapshot attribute

               

              Manual DB snapshot attributes are used to authorize other AWS accounts to restore a manual DB snapshot. For more information, see the  ModifyDBSnapshotAttribute API.

              
              

              - **AttributeName** *(string) --* 

                The name of the manual DB snapshot attribute.

                 

                The attribute named ``restore`` refers to the list of AWS accounts that have permission to copy or restore the manual DB cluster snapshot. For more information, see the  ModifyDBSnapshotAttribute API action.

                
              

              - **AttributeValues** *(list) --* 

                The value or values for the manual DB snapshot attribute.

                 

                If the ``AttributeName`` field is set to ``restore`` , then this element returns a list of IDs of the AWS accounts that are authorized to copy or restore the manual DB snapshot. If a value of ``all`` is in the list, then the manual DB snapshot is public and available for any AWS account to copy or restore.

                
                

                - *(string) --* 
            
          
        
      
    

  .. py:method:: modify_db_subnet_group(**kwargs)

    

    Modifies an existing DB subnet group. DB subnet groups must contain at least one subnet in at least two AZs in the region.

    

    **Request Syntax** 
    ::

      response = client.modify_db_subnet_group(
          DBSubnetGroupName='string',
          DBSubnetGroupDescription='string',
          SubnetIds=[
              'string',
          ]
      )
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: **[REQUIRED]** 

      The name for the DB subnet group. This value is stored as a lowercase string.

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    :type DBSubnetGroupDescription: string
    :param DBSubnetGroupDescription: 

      The description for the DB subnet group.

      

    
    :type SubnetIds: list
    :param SubnetIds: **[REQUIRED]** 

      The EC2 subnet IDs for the DB subnet group.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSubnetGroup': {
                'DBSubnetGroupName': 'string',
                'DBSubnetGroupDescription': 'string',
                'VpcId': 'string',
                'SubnetGroupStatus': 'string',
                'Subnets': [
                    {
                        'SubnetIdentifier': 'string',
                        'SubnetAvailabilityZone': {
                            'Name': 'string'
                        },
                        'SubnetStatus': 'string'
                    },
                ],
                'DBSubnetGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSubnetGroup** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBSubnetGroup   
           
          *  ModifyDBSubnetGroup   
           
          *  DescribeDBSubnetGroups   
           
          *  DeleteDBSubnetGroup   
           

           

          This data type is used as a response element in the  DescribeDBSubnetGroups action.

          
          

          - **DBSubnetGroupName** *(string) --* 

            The name of the DB subnet group.

            
          

          - **DBSubnetGroupDescription** *(string) --* 

            Provides the description of the DB subnet group.

            
          

          - **VpcId** *(string) --* 

            Provides the VpcId of the DB subnet group.

            
          

          - **SubnetGroupStatus** *(string) --* 

            Provides the status of the DB subnet group.

            
          

          - **Subnets** *(list) --* 

            Contains a list of  Subnet elements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the  DescribeDBSubnetGroups action. 

              
              

              - **SubnetIdentifier** *(string) --* 

                Specifies the identifier of the subnet.

                
              

              - **SubnetAvailabilityZone** *(dict) --* 

                Contains Availability Zone information.

                 

                This data type is used as an element in the following data type:

                 

                 
                *  OrderableDBInstanceOption   
                 

                
                

                - **Name** *(string) --* 

                  The name of the availability zone.

                  
            
              

              - **SubnetStatus** *(string) --* 

                Specifies the status of the subnet.

                
          
        
          

          - **DBSubnetGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB subnet group.

            
      
    

  .. py:method:: modify_event_subscription(**kwargs)

    

    Modifies an existing RDS event notification subscription. Note that you cannot modify the source identifiers using this call; to change source identifiers for a subscription, use the  AddSourceIdentifierToSubscription and  RemoveSourceIdentifierFromSubscription calls.

     

    You can see a list of the event categories for a given SourceType in the `Events`_ topic in the Amazon RDS User Guide or by using the **DescribeEventCategories** action.

    

    **Request Syntax** 
    ::

      response = client.modify_event_subscription(
          SubscriptionName='string',
          SnsTopicArn='string',
          SourceType='string',
          EventCategories=[
              'string',
          ],
          Enabled=True|False
      )
    :type SubscriptionName: string
    :param SubscriptionName: **[REQUIRED]** 

      The name of the RDS event notification subscription.

      

    
    :type SnsTopicArn: string
    :param SnsTopicArn: 

      The Amazon Resource Name (ARN) of the SNS topic created for event notification. The ARN is created by Amazon SNS when you create a topic and subscribe to it.

      

    
    :type SourceType: string
    :param SourceType: 

      The type of source that will be generating the events. For example, if you want to be notified of events generated by a DB instance, you would set this parameter to db-instance. if this value is not specified, all events are returned.

       

      Valid values: db-instance | db-parameter-group | db-security-group | db-snapshot

      

    
    :type EventCategories: list
    :param EventCategories: 

      A list of event categories for a SourceType that you want to subscribe to. You can see a list of the categories for a given SourceType in the `Events`_ topic in the Amazon RDS User Guide or by using the **DescribeEventCategories** action. 

      

    
      - *(string) --* 

      
  
    :type Enabled: boolean
    :param Enabled: 

      A Boolean value; set to **true** to activate the subscription. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EventSubscription': {
                'CustomerAwsId': 'string',
                'CustSubscriptionId': 'string',
                'SnsTopicArn': 'string',
                'Status': 'string',
                'SubscriptionCreationTime': 'string',
                'SourceType': 'string',
                'SourceIdsList': [
                    'string',
                ],
                'EventCategoriesList': [
                    'string',
                ],
                'Enabled': True|False,
                'EventSubscriptionArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **EventSubscription** *(dict) --* 

          Contains the results of a successful invocation of the  DescribeEventSubscriptions action.

          
          

          - **CustomerAwsId** *(string) --* 

            The AWS customer account associated with the RDS event notification subscription.

            
          

          - **CustSubscriptionId** *(string) --* 

            The RDS event notification subscription Id.

            
          

          - **SnsTopicArn** *(string) --* 

            The topic ARN of the RDS event notification subscription.

            
          

          - **Status** *(string) --* 

            The status of the RDS event notification subscription.

             

            Constraints:

             

            Can be one of the following: creating | modifying | deleting | active | no-permission | topic-not-exist

             

            The status "no-permission" indicates that RDS no longer has permission to post to the SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created.

            
          

          - **SubscriptionCreationTime** *(string) --* 

            The time the RDS event notification subscription was created.

            
          

          - **SourceType** *(string) --* 

            The source type for the RDS event notification subscription.

            
          

          - **SourceIdsList** *(list) --* 

            A list of source IDs for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **EventCategoriesList** *(list) --* 

            A list of event categories for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **Enabled** *(boolean) --* 

            A Boolean value indicating if the subscription is enabled. True indicates the subscription is enabled.

            
          

          - **EventSubscriptionArn** *(string) --* 

            The Amazon Resource Name (ARN) for the event subscription.

            
      
    

  .. py:method:: modify_option_group(**kwargs)

    

    Modifies an existing option group.

    

    **Request Syntax** 
    ::

      response = client.modify_option_group(
          OptionGroupName='string',
          OptionsToInclude=[
              {
                  'OptionName': 'string',
                  'Port': 123,
                  'OptionVersion': 'string',
                  'DBSecurityGroupMemberships': [
                      'string',
                  ],
                  'VpcSecurityGroupMemberships': [
                      'string',
                  ],
                  'OptionSettings': [
                      {
                          'Name': 'string',
                          'Value': 'string',
                          'DefaultValue': 'string',
                          'Description': 'string',
                          'ApplyType': 'string',
                          'DataType': 'string',
                          'AllowedValues': 'string',
                          'IsModifiable': True|False,
                          'IsCollection': True|False
                      },
                  ]
              },
          ],
          OptionsToRemove=[
              'string',
          ],
          ApplyImmediately=True|False
      )
    :type OptionGroupName: string
    :param OptionGroupName: **[REQUIRED]** 

      The name of the option group to be modified.

       

      Permanent options, such as the TDE option for Oracle Advanced Security TDE, cannot be removed from an option group, and that option group cannot be removed from a DB instance once it is associated with a DB instance

      

    
    :type OptionsToInclude: list
    :param OptionsToInclude: 

      Options in this list are added to the option group or, if already present, the specified configuration is used to update the existing configuration.

      

    
      - *(dict) --* 

        A list of all available options

        

      
        - **OptionName** *(string) --* **[REQUIRED]** 

          The configuration of options to include in a group.

          

        
        - **Port** *(integer) --* 

          The optional port for the option.

          

        
        - **OptionVersion** *(string) --* 

          The version for the option.

          

        
        - **DBSecurityGroupMemberships** *(list) --* 

          A list of DBSecurityGroupMemebrship name strings used for this option.

          

        
          - *(string) --* 

          
      
        - **VpcSecurityGroupMemberships** *(list) --* 

          A list of VpcSecurityGroupMemebrship name strings used for this option.

          

        
          - *(string) --* 

          
      
        - **OptionSettings** *(list) --* 

          The option settings to include in an option group.

          

        
          - *(dict) --* 

            Option settings are the actual settings being applied or configured for that option. It is used when you modify an option group or describe option groups. For example, the NATIVE_NETWORK_ENCRYPTION option has a setting called SQLNET.ENCRYPTION_SERVER that can have several different values.

            

          
            - **Name** *(string) --* 

              The name of the option that has settings that you can set.

              

            
            - **Value** *(string) --* 

              The current value of the option setting.

              

            
            - **DefaultValue** *(string) --* 

              The default value of the option setting.

              

            
            - **Description** *(string) --* 

              The description of the option setting.

              

            
            - **ApplyType** *(string) --* 

              The DB engine specific parameter type.

              

            
            - **DataType** *(string) --* 

              The data type of the option setting.

              

            
            - **AllowedValues** *(string) --* 

              The allowed values of the option setting.

              

            
            - **IsModifiable** *(boolean) --* 

              A Boolean value that, when true, indicates the option setting can be modified from the default.

              

            
            - **IsCollection** *(boolean) --* 

              Indicates if the option setting is part of a collection.

              

            
          
      
      
  
    :type OptionsToRemove: list
    :param OptionsToRemove: 

      Options in this list are removed from the option group.

      

    
      - *(string) --* 

      
  
    :type ApplyImmediately: boolean
    :param ApplyImmediately: 

      Indicates whether the changes should be applied immediately, or during the next maintenance window for each instance associated with the option group.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OptionGroup': {
                'OptionGroupName': 'string',
                'OptionGroupDescription': 'string',
                'EngineName': 'string',
                'MajorEngineVersion': 'string',
                'Options': [
                    {
                        'OptionName': 'string',
                        'OptionDescription': 'string',
                        'Persistent': True|False,
                        'Permanent': True|False,
                        'Port': 123,
                        'OptionVersion': 'string',
                        'OptionSettings': [
                            {
                                'Name': 'string',
                                'Value': 'string',
                                'DefaultValue': 'string',
                                'Description': 'string',
                                'ApplyType': 'string',
                                'DataType': 'string',
                                'AllowedValues': 'string',
                                'IsModifiable': True|False,
                                'IsCollection': True|False
                            },
                        ],
                        'DBSecurityGroupMemberships': [
                            {
                                'DBSecurityGroupName': 'string',
                                'Status': 'string'
                            },
                        ],
                        'VpcSecurityGroupMemberships': [
                            {
                                'VpcSecurityGroupId': 'string',
                                'Status': 'string'
                            },
                        ]
                    },
                ],
                'AllowsVpcAndNonVpcInstanceMemberships': True|False,
                'VpcId': 'string',
                'OptionGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **OptionGroup** *(dict) --* 

          

          
          

          - **OptionGroupName** *(string) --* 

            Specifies the name of the option group.

            
          

          - **OptionGroupDescription** *(string) --* 

            Provides a description of the option group.

            
          

          - **EngineName** *(string) --* 

            Indicates the name of the engine that this option group can be applied to.

            
          

          - **MajorEngineVersion** *(string) --* 

            Indicates the major engine version associated with this option group.

            
          

          - **Options** *(list) --* 

            Indicates what options are available in the option group.

            
            

            - *(dict) --* 

              Option details.

              
              

              - **OptionName** *(string) --* 

                The name of the option.

                
              

              - **OptionDescription** *(string) --* 

                The description of the option.

                
              

              - **Persistent** *(boolean) --* 

                Indicate if this option is persistent.

                
              

              - **Permanent** *(boolean) --* 

                Indicate if this option is permanent.

                
              

              - **Port** *(integer) --* 

                If required, the port configured for this option to use.

                
              

              - **OptionVersion** *(string) --* 

                The version of the option.

                
              

              - **OptionSettings** *(list) --* 

                The option settings for this option.

                
                

                - *(dict) --* 

                  Option settings are the actual settings being applied or configured for that option. It is used when you modify an option group or describe option groups. For example, the NATIVE_NETWORK_ENCRYPTION option has a setting called SQLNET.ENCRYPTION_SERVER that can have several different values.

                  
                  

                  - **Name** *(string) --* 

                    The name of the option that has settings that you can set.

                    
                  

                  - **Value** *(string) --* 

                    The current value of the option setting.

                    
                  

                  - **DefaultValue** *(string) --* 

                    The default value of the option setting.

                    
                  

                  - **Description** *(string) --* 

                    The description of the option setting.

                    
                  

                  - **ApplyType** *(string) --* 

                    The DB engine specific parameter type.

                    
                  

                  - **DataType** *(string) --* 

                    The data type of the option setting.

                    
                  

                  - **AllowedValues** *(string) --* 

                    The allowed values of the option setting.

                    
                  

                  - **IsModifiable** *(boolean) --* 

                    A Boolean value that, when true, indicates the option setting can be modified from the default.

                    
                  

                  - **IsCollection** *(boolean) --* 

                    Indicates if the option setting is part of a collection.

                    
              
            
              

              - **DBSecurityGroupMemberships** *(list) --* 

                If the option requires access to a port, then this DB security group allows access to the port.

                
                

                - *(dict) --* 

                  This data type is used as a response element in the following actions:

                   

                   
                  *  ModifyDBInstance   
                   
                  *  RebootDBInstance   
                   
                  *  RestoreDBInstanceFromDBSnapshot   
                   
                  *  RestoreDBInstanceToPointInTime   
                   

                  
                  

                  - **DBSecurityGroupName** *(string) --* 

                    The name of the DB security group.

                    
                  

                  - **Status** *(string) --* 

                    The status of the DB security group.

                    
              
            
              

              - **VpcSecurityGroupMemberships** *(list) --* 

                If the option requires access to a port, then this VPC security group allows access to the port.

                
                

                - *(dict) --* 

                  This data type is used as a response element for queries on VPC security group membership.

                  
                  

                  - **VpcSecurityGroupId** *(string) --* 

                    The name of the VPC security group.

                    
                  

                  - **Status** *(string) --* 

                    The status of the VPC security group.

                    
              
            
          
        
          

          - **AllowsVpcAndNonVpcInstanceMemberships** *(boolean) --* 

            Indicates whether this option group can be applied to both VPC and non-VPC instances. The value ``true`` indicates the option group can be applied to both VPC and non-VPC instances. 

            
          

          - **VpcId** *(string) --* 

            If **AllowsVpcAndNonVpcInstanceMemberships** is ``false`` , this field is blank. If **AllowsVpcAndNonVpcInstanceMemberships** is ``true`` and this field is blank, then this option group can be applied to both VPC and non-VPC instances. If this field contains a value, then this option group can only be applied to instances that are in the VPC indicated by this field. 

            
          

          - **OptionGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the option group.

            
      
    

  .. py:method:: promote_read_replica(**kwargs)

    

    Promotes a Read Replica DB instance to a standalone DB instance.

     

    .. note::

       

      We recommend that you enable automated backups on your Read Replica before promoting the Read Replica. This ensures that no backup is taken during the promotion process. Once the instance is promoted to a primary instance, backups are taken based on your backup settings.

       

    

    **Request Syntax** 
    ::

      response = client.promote_read_replica(
          DBInstanceIdentifier='string',
          BackupRetentionPeriod=123,
          PreferredBackupWindow='string'
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The DB instance identifier. This value is stored as a lowercase string.

       

      Constraints:

       

       
      * Must be the identifier for an existing Read Replica DB instance 
       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``mydbinstance``  

      

    
    :type BackupRetentionPeriod: integer
    :param BackupRetentionPeriod: 

      The number of days to retain automated backups. Setting this parameter to a positive number enables backups. Setting this parameter to 0 disables automated backups.

       

      Default: 1

       

      Constraints:

       

       
      * Must be a value from 0 to 8 
       

      

    
    :type PreferredBackupWindow: string
    :param PreferredBackupWindow: 

      The daily time range during which automated backups are created if automated backups are enabled, using the ``BackupRetentionPeriod`` parameter. 

       

      Default: A 30-minute window selected at random from an 8-hour block of time per region. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

       

      Constraints:

       

       
      * Must be in the format ``hh24:mi-hh24:mi`` . 
       
      * Times should be in Universal Coordinated Time (UTC). 
       
      * Must not conflict with the preferred maintenance window. 
       
      * Must be at least 30 minutes. 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBInstance': {
                'DBInstanceIdentifier': 'string',
                'DBInstanceClass': 'string',
                'Engine': 'string',
                'DBInstanceStatus': 'string',
                'MasterUsername': 'string',
                'DBName': 'string',
                'Endpoint': {
                    'Address': 'string',
                    'Port': 123,
                    'HostedZoneId': 'string'
                },
                'AllocatedStorage': 123,
                'InstanceCreateTime': datetime(2015, 1, 1),
                'PreferredBackupWindow': 'string',
                'BackupRetentionPeriod': 123,
                'DBSecurityGroups': [
                    {
                        'DBSecurityGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'DBParameterGroups': [
                    {
                        'DBParameterGroupName': 'string',
                        'ParameterApplyStatus': 'string'
                    },
                ],
                'AvailabilityZone': 'string',
                'DBSubnetGroup': {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
                'PreferredMaintenanceWindow': 'string',
                'PendingModifiedValues': {
                    'DBInstanceClass': 'string',
                    'AllocatedStorage': 123,
                    'MasterUserPassword': 'string',
                    'Port': 123,
                    'BackupRetentionPeriod': 123,
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'DBInstanceIdentifier': 'string',
                    'StorageType': 'string',
                    'CACertificateIdentifier': 'string',
                    'DBSubnetGroupName': 'string'
                },
                'LatestRestorableTime': datetime(2015, 1, 1),
                'MultiAZ': True|False,
                'EngineVersion': 'string',
                'AutoMinorVersionUpgrade': True|False,
                'ReadReplicaSourceDBInstanceIdentifier': 'string',
                'ReadReplicaDBInstanceIdentifiers': [
                    'string',
                ],
                'LicenseModel': 'string',
                'Iops': 123,
                'OptionGroupMemberships': [
                    {
                        'OptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'CharacterSetName': 'string',
                'SecondaryAvailabilityZone': 'string',
                'PubliclyAccessible': True|False,
                'StatusInfos': [
                    {
                        'StatusType': 'string',
                        'Normal': True|False,
                        'Status': 'string',
                        'Message': 'string'
                    },
                ],
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'DbInstancePort': 123,
                'DBClusterIdentifier': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbiResourceId': 'string',
                'CACertificateIdentifier': 'string',
                'DomainMemberships': [
                    {
                        'Domain': 'string',
                        'Status': 'string',
                        'FQDN': 'string',
                        'IAMRoleName': 'string'
                    },
                ],
                'CopyTagsToSnapshot': True|False,
                'MonitoringInterval': 123,
                'EnhancedMonitoringResourceArn': 'string',
                'MonitoringRoleArn': 'string',
                'PromotionTier': 123,
                'DBInstanceArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBInstance** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBInstance   
           
          *  DeleteDBInstance   
           
          *  ModifyDBInstance   
           

           

          This data type is used as a response element in the  DescribeDBInstances action.

          
          

          - **DBInstanceIdentifier** *(string) --* 

            Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

            
          

          - **DBInstanceClass** *(string) --* 

            Contains the name of the compute and memory capacity class of the DB instance.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB instance.

            
          

          - **DBInstanceStatus** *(string) --* 

            Specifies the current state of this database.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB instance.

            
          

          - **DBName** *(string) --* 

            The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

             

             **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

             

            Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

             

            Type: String

             

             **Oracle**  

             

            Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

            
          

          - **Endpoint** *(dict) --* 

            Specifies the connection endpoint.

            
            

            - **Address** *(string) --* 

              Specifies the DNS address of the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine is listening on.

              
            

            - **HostedZoneId** *(string) --* 

              Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

              
        
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size specified in gigabytes.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Provides the date and time the DB instance was created.

            
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **DBSecurityGroups** *(list) --* 

            Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               
              *  RestoreDBInstanceToPointInTime   
               

              
              

              - **DBSecurityGroupName** *(string) --* 

                The name of the DB security group.

                
              

              - **Status** *(string) --* 

                The status of the DB security group.

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides List of VPC security group elements that the DB instance belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **DBParameterGroups** *(list) --* 

            Provides the list of DB parameter groups applied to this DB instance.

            
            

            - *(dict) --* 

              The status of the DB parameter group.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateDBInstance   
               
              *  CreateDBInstanceReadReplica   
               
              *  DeleteDBInstance   
               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               

              
              

              - **DBParameterGroupName** *(string) --* 

                The name of the DP parameter group.

                
              

              - **ParameterApplyStatus** *(string) --* 

                The status of parameter updates.

                
          
        
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance is located in.

            
          

          - **DBSubnetGroup** *(dict) --* 

            Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **PendingModifiedValues** *(dict) --* 

            Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

            
            

            - **DBInstanceClass** *(string) --* 

              Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

              
            

            - **AllocatedStorage** *(integer) --* 

              Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

              
            

            - **MasterUserPassword** *(string) --* 

              Contains the pending or in-progress change of the master credentials for the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the pending port for the DB instance.

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the pending number of days for which automated backups are retained.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the DB instance.

               

              Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

              
            

            - **Iops** *(integer) --* 

              Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type to be associated with the DB instance.

              
            

            - **CACertificateIdentifier** *(string) --* 

              Specifies the identifier of the CA certificate for the DB instance.

              
            

            - **DBSubnetGroupName** *(string) --* 

              The new DB subnet group for the DB instance. 

              
        
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **MultiAZ** *(boolean) --* 

            Specifies if the DB instance is a Multi-AZ deployment.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **AutoMinorVersionUpgrade** *(boolean) --* 

            Indicates that minor version patches are applied automatically.

            
          

          - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

            Contains the identifier of the source DB instance if this DB instance is a Read Replica.

            
          

          - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB instance.

            
            

            - *(string) --* 
        
          

          - **LicenseModel** *(string) --* 

            License model information for this DB instance.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value.

            
          

          - **OptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB instance.

            
            

            - *(dict) --* 

              Provides information on the option groups the DB instance is a member of.

              
              

              - **OptionGroupName** *(string) --* 

                The name of the option group that the instance belongs to.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                
          
        
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this instance is associated with.

            
          

          - **SecondaryAvailabilityZone** *(string) --* 

            If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

            
          

          - **PubliclyAccessible** *(boolean) --* 

            Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

             

            Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

             

             
            * **Default VPC:** true 
             
            * **VPC:** false 
             

             

            If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

            
          

          - **StatusInfos** *(list) --* 

            The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

            
            

            - *(dict) --* 

              Provides a list of status information for a DB instance.

              
              

              - **StatusType** *(string) --* 

                This value is currently "read replication."

                
              

              - **Normal** *(boolean) --* 

                Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                
              

              - **Status** *(string) --* 

                Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                
              

              - **Message** *(string) --* 

                Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                
          
        
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB instance.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which the instance is associated for TDE encryption.

            
          

          - **DbInstancePort** *(integer) --* 

            Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

            
          

          - **DBClusterIdentifier** *(string) --* 

            If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB instance is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

            
          

          - **DbiResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

            
          

          - **CACertificateIdentifier** *(string) --* 

            The identifier of the CA certificate for this DB instance.

            
          

          - **DomainMemberships** *(list) --* 

            The Active Directory Domain membership records associated with the DB instance.

            
            

            - *(dict) --* 

              An Active Directory Domain membership record associated with the DB instance.

              
              

              - **Domain** *(string) --* 

                The identifier of the Active Directory Domain.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                
              

              - **FQDN** *(string) --* 

                The fully qualified domain name of the Active Directory Domain.

                
              

              - **IAMRoleName** *(string) --* 

                The name of the IAM role to be used when making API calls to the Directory Service.

                
          
        
          

          - **CopyTagsToSnapshot** *(boolean) --* 

            Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

            
          

          - **MonitoringInterval** *(integer) --* 

            The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

            
          

          - **EnhancedMonitoringResourceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

            
          

          - **MonitoringRoleArn** *(string) --* 

            The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

            
          

          - **PromotionTier** *(integer) --* 

            A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

            
          

          - **DBInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB instance.

            
      
    

  .. py:method:: promote_read_replica_db_cluster(**kwargs)

    

    Promotes a Read Replica DB cluster to a standalone DB cluster.

    

    **Request Syntax** 
    ::

      response = client.promote_read_replica_db_cluster(
          DBClusterIdentifier='string'
      )
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: **[REQUIRED]** 

      The identifier of the DB cluster Read Replica to promote. This parameter is not case-sensitive. 

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

       

      Example: ``my-cluster-replica1``  

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBCluster': {
                'AllocatedStorage': 123,
                'AvailabilityZones': [
                    'string',
                ],
                'BackupRetentionPeriod': 123,
                'CharacterSetName': 'string',
                'DatabaseName': 'string',
                'DBClusterIdentifier': 'string',
                'DBClusterParameterGroup': 'string',
                'DBSubnetGroup': 'string',
                'Status': 'string',
                'PercentProgress': 'string',
                'EarliestRestorableTime': datetime(2015, 1, 1),
                'Endpoint': 'string',
                'Engine': 'string',
                'EngineVersion': 'string',
                'LatestRestorableTime': datetime(2015, 1, 1),
                'Port': 123,
                'MasterUsername': 'string',
                'DBClusterOptionGroupMemberships': [
                    {
                        'DBClusterOptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'PreferredBackupWindow': 'string',
                'PreferredMaintenanceWindow': 'string',
                'ReplicationSourceIdentifier': 'string',
                'ReadReplicaIdentifiers': [
                    'string',
                ],
                'DBClusterMembers': [
                    {
                        'DBInstanceIdentifier': 'string',
                        'IsClusterWriter': True|False,
                        'DBClusterParameterGroupStatus': 'string',
                        'PromotionTier': 123
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'HostedZoneId': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbClusterResourceId': 'string',
                'DBClusterArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBCluster** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBCluster   
           
          *  DeleteDBCluster   
           
          *  FailoverDBCluster   
           
          *  ModifyDBCluster   
           
          *  RestoreDBClusterFromSnapshot   
           
          *  RestoreDBClusterToPointInTime   
           

           

          This data type is used as a response element in the  DescribeDBClusters action.

          
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

            
            

            - *(string) --* 
        
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this cluster is associated with.

            
          

          - **DatabaseName** *(string) --* 

            Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster.

            
          

          - **DBClusterParameterGroup** *(string) --* 

            Specifies the name of the DB cluster parameter group for the DB cluster.

            
          

          - **DBSubnetGroup** *(string) --* 

            Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group.

            
          

          - **Status** *(string) --* 

            Specifies the current state of this DB cluster.

            
          

          - **PercentProgress** *(string) --* 

            Specifies the progress of the operation as a percentage.

            
          

          - **EarliestRestorableTime** *(datetime) --* 

            Specifies the earliest time to which a database can be restored with point-in-time restore.

            
          

          - **Endpoint** *(string) --* 

            Specifies the connection endpoint for the primary instance of the DB cluster.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB cluster.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine is listening on.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB cluster.

            
          

          - **DBClusterOptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB cluster.

            
            

            - *(dict) --* 

              Contains status information for a DB cluster option group.

              
              

              - **DBClusterOptionGroupName** *(string) --* 

                Specifies the name of the DB cluster option group.

                
              

              - **Status** *(string) --* 

                Specifies the status of the DB cluster option group.

                
          
        
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **ReplicationSourceIdentifier** *(string) --* 

            Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

            
          

          - **ReadReplicaIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB cluster.

            
            

            - *(string) --* 
        
          

          - **DBClusterMembers** *(list) --* 

            Provides the list of instances that make up the DB cluster.

            
            

            - *(dict) --* 

              Contains information about an instance that is part of a DB cluster.

              
              

              - **DBInstanceIdentifier** *(string) --* 

                Specifies the instance identifier for this member of the DB cluster.

                
              

              - **IsClusterWriter** *(boolean) --* 

                Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

                
              

              - **DBClusterParameterGroupStatus** *(string) --* 

                Specifies the status of the DB cluster parameter group for this member of the DB cluster.

                
              

              - **PromotionTier** *(integer) --* 

                A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides a list of VPC security groups that the DB cluster belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **HostedZoneId** *(string) --* 

            Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

            
          

          - **DbClusterResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed.

            
          

          - **DBClusterArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster.

            
      
    

  .. py:method:: purchase_reserved_db_instances_offering(**kwargs)

    

    Purchases a reserved DB instance offering.

    

    **Request Syntax** 
    ::

      response = client.purchase_reserved_db_instances_offering(
          ReservedDBInstancesOfferingId='string',
          ReservedDBInstanceId='string',
          DBInstanceCount=123,
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type ReservedDBInstancesOfferingId: string
    :param ReservedDBInstancesOfferingId: **[REQUIRED]** 

      The ID of the Reserved DB instance offering to purchase.

       

      Example: 438012d3-4052-4cc7-b2e3-8d3372e0e706

      

    
    :type ReservedDBInstanceId: string
    :param ReservedDBInstanceId: 

      Customer-specified identifier to track this reservation.

       

      Example: myreservationID

      

    
    :type DBInstanceCount: integer
    :param DBInstanceCount: 

      The number of instances to reserve.

       

      Default: ``1``  

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ReservedDBInstance': {
                'ReservedDBInstanceId': 'string',
                'ReservedDBInstancesOfferingId': 'string',
                'DBInstanceClass': 'string',
                'StartTime': datetime(2015, 1, 1),
                'Duration': 123,
                'FixedPrice': 123.0,
                'UsagePrice': 123.0,
                'CurrencyCode': 'string',
                'DBInstanceCount': 123,
                'ProductDescription': 'string',
                'OfferingType': 'string',
                'MultiAZ': True|False,
                'State': 'string',
                'RecurringCharges': [
                    {
                        'RecurringChargeAmount': 123.0,
                        'RecurringChargeFrequency': 'string'
                    },
                ],
                'ReservedDBInstanceArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ReservedDBInstance** *(dict) --* 

          This data type is used as a response element in the  DescribeReservedDBInstances and  PurchaseReservedDBInstancesOffering actions. 

          
          

          - **ReservedDBInstanceId** *(string) --* 

            The unique identifier for the reservation.

            
          

          - **ReservedDBInstancesOfferingId** *(string) --* 

            The offering identifier.

            
          

          - **DBInstanceClass** *(string) --* 

            The DB instance class for the reserved DB instance.

            
          

          - **StartTime** *(datetime) --* 

            The time the reservation started.

            
          

          - **Duration** *(integer) --* 

            The duration of the reservation in seconds.

            
          

          - **FixedPrice** *(float) --* 

            The fixed price charged for this reserved DB instance.

            
          

          - **UsagePrice** *(float) --* 

            The hourly price charged for this reserved DB instance.

            
          

          - **CurrencyCode** *(string) --* 

            The currency code for the reserved DB instance.

            
          

          - **DBInstanceCount** *(integer) --* 

            The number of reserved DB instances.

            
          

          - **ProductDescription** *(string) --* 

            The description of the reserved DB instance.

            
          

          - **OfferingType** *(string) --* 

            The offering type of this reserved DB instance.

            
          

          - **MultiAZ** *(boolean) --* 

            Indicates if the reservation applies to Multi-AZ deployments.

            
          

          - **State** *(string) --* 

            The state of the reserved DB instance.

            
          

          - **RecurringCharges** *(list) --* 

            The recurring price charged to run this reserved DB instance.

            
            

            - *(dict) --* 

              This data type is used as a response element in the  DescribeReservedDBInstances and  DescribeReservedDBInstancesOfferings actions. 

              
              

              - **RecurringChargeAmount** *(float) --* 

                The amount of the recurring charge.

                
              

              - **RecurringChargeFrequency** *(string) --* 

                The frequency of the recurring charge.

                
          
        
          

          - **ReservedDBInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) for the reserved DB instance.

            
      
    

  .. py:method:: reboot_db_instance(**kwargs)

    

    Rebooting a DB instance restarts the database engine service. A reboot also applies to the DB instance any modifications to the associated DB parameter group that were pending. Rebooting a DB instance results in a momentary outage of the instance, during which the DB instance status is set to rebooting. If the RDS instance is configured for MultiAZ, it is possible that the reboot will be conducted through a failover. An Amazon RDS event is created when the reboot is completed.

     

    If your DB instance is deployed in multiple Availability Zones, you can force a failover from one AZ to the other during the reboot. You might force a failover to test the availability of your DB instance deployment or to restore operations to the original AZ after a failover occurs.

     

    The time required to reboot is a function of the specific database engine's crash recovery process. To improve the reboot time, we recommend that you reduce database activities as much as possible during the reboot process to reduce rollback activity for in-transit transactions.

    

    **Request Syntax** 
    ::

      response = client.reboot_db_instance(
          DBInstanceIdentifier='string',
          ForceFailover=True|False
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The DB instance identifier. This parameter is stored as a lowercase string.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type ForceFailover: boolean
    :param ForceFailover: 

      When ``true`` , the reboot will be conducted through a MultiAZ failover. 

       

      Constraint: You cannot specify ``true`` if the instance is not configured for MultiAZ.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBInstance': {
                'DBInstanceIdentifier': 'string',
                'DBInstanceClass': 'string',
                'Engine': 'string',
                'DBInstanceStatus': 'string',
                'MasterUsername': 'string',
                'DBName': 'string',
                'Endpoint': {
                    'Address': 'string',
                    'Port': 123,
                    'HostedZoneId': 'string'
                },
                'AllocatedStorage': 123,
                'InstanceCreateTime': datetime(2015, 1, 1),
                'PreferredBackupWindow': 'string',
                'BackupRetentionPeriod': 123,
                'DBSecurityGroups': [
                    {
                        'DBSecurityGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'DBParameterGroups': [
                    {
                        'DBParameterGroupName': 'string',
                        'ParameterApplyStatus': 'string'
                    },
                ],
                'AvailabilityZone': 'string',
                'DBSubnetGroup': {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
                'PreferredMaintenanceWindow': 'string',
                'PendingModifiedValues': {
                    'DBInstanceClass': 'string',
                    'AllocatedStorage': 123,
                    'MasterUserPassword': 'string',
                    'Port': 123,
                    'BackupRetentionPeriod': 123,
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'DBInstanceIdentifier': 'string',
                    'StorageType': 'string',
                    'CACertificateIdentifier': 'string',
                    'DBSubnetGroupName': 'string'
                },
                'LatestRestorableTime': datetime(2015, 1, 1),
                'MultiAZ': True|False,
                'EngineVersion': 'string',
                'AutoMinorVersionUpgrade': True|False,
                'ReadReplicaSourceDBInstanceIdentifier': 'string',
                'ReadReplicaDBInstanceIdentifiers': [
                    'string',
                ],
                'LicenseModel': 'string',
                'Iops': 123,
                'OptionGroupMemberships': [
                    {
                        'OptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'CharacterSetName': 'string',
                'SecondaryAvailabilityZone': 'string',
                'PubliclyAccessible': True|False,
                'StatusInfos': [
                    {
                        'StatusType': 'string',
                        'Normal': True|False,
                        'Status': 'string',
                        'Message': 'string'
                    },
                ],
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'DbInstancePort': 123,
                'DBClusterIdentifier': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbiResourceId': 'string',
                'CACertificateIdentifier': 'string',
                'DomainMemberships': [
                    {
                        'Domain': 'string',
                        'Status': 'string',
                        'FQDN': 'string',
                        'IAMRoleName': 'string'
                    },
                ],
                'CopyTagsToSnapshot': True|False,
                'MonitoringInterval': 123,
                'EnhancedMonitoringResourceArn': 'string',
                'MonitoringRoleArn': 'string',
                'PromotionTier': 123,
                'DBInstanceArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBInstance** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBInstance   
           
          *  DeleteDBInstance   
           
          *  ModifyDBInstance   
           

           

          This data type is used as a response element in the  DescribeDBInstances action.

          
          

          - **DBInstanceIdentifier** *(string) --* 

            Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

            
          

          - **DBInstanceClass** *(string) --* 

            Contains the name of the compute and memory capacity class of the DB instance.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB instance.

            
          

          - **DBInstanceStatus** *(string) --* 

            Specifies the current state of this database.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB instance.

            
          

          - **DBName** *(string) --* 

            The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

             

             **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

             

            Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

             

            Type: String

             

             **Oracle**  

             

            Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

            
          

          - **Endpoint** *(dict) --* 

            Specifies the connection endpoint.

            
            

            - **Address** *(string) --* 

              Specifies the DNS address of the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine is listening on.

              
            

            - **HostedZoneId** *(string) --* 

              Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

              
        
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size specified in gigabytes.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Provides the date and time the DB instance was created.

            
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **DBSecurityGroups** *(list) --* 

            Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               
              *  RestoreDBInstanceToPointInTime   
               

              
              

              - **DBSecurityGroupName** *(string) --* 

                The name of the DB security group.

                
              

              - **Status** *(string) --* 

                The status of the DB security group.

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides List of VPC security group elements that the DB instance belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **DBParameterGroups** *(list) --* 

            Provides the list of DB parameter groups applied to this DB instance.

            
            

            - *(dict) --* 

              The status of the DB parameter group.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateDBInstance   
               
              *  CreateDBInstanceReadReplica   
               
              *  DeleteDBInstance   
               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               

              
              

              - **DBParameterGroupName** *(string) --* 

                The name of the DP parameter group.

                
              

              - **ParameterApplyStatus** *(string) --* 

                The status of parameter updates.

                
          
        
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance is located in.

            
          

          - **DBSubnetGroup** *(dict) --* 

            Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **PendingModifiedValues** *(dict) --* 

            Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

            
            

            - **DBInstanceClass** *(string) --* 

              Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

              
            

            - **AllocatedStorage** *(integer) --* 

              Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

              
            

            - **MasterUserPassword** *(string) --* 

              Contains the pending or in-progress change of the master credentials for the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the pending port for the DB instance.

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the pending number of days for which automated backups are retained.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the DB instance.

               

              Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

              
            

            - **Iops** *(integer) --* 

              Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type to be associated with the DB instance.

              
            

            - **CACertificateIdentifier** *(string) --* 

              Specifies the identifier of the CA certificate for the DB instance.

              
            

            - **DBSubnetGroupName** *(string) --* 

              The new DB subnet group for the DB instance. 

              
        
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **MultiAZ** *(boolean) --* 

            Specifies if the DB instance is a Multi-AZ deployment.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **AutoMinorVersionUpgrade** *(boolean) --* 

            Indicates that minor version patches are applied automatically.

            
          

          - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

            Contains the identifier of the source DB instance if this DB instance is a Read Replica.

            
          

          - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB instance.

            
            

            - *(string) --* 
        
          

          - **LicenseModel** *(string) --* 

            License model information for this DB instance.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value.

            
          

          - **OptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB instance.

            
            

            - *(dict) --* 

              Provides information on the option groups the DB instance is a member of.

              
              

              - **OptionGroupName** *(string) --* 

                The name of the option group that the instance belongs to.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                
          
        
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this instance is associated with.

            
          

          - **SecondaryAvailabilityZone** *(string) --* 

            If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

            
          

          - **PubliclyAccessible** *(boolean) --* 

            Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

             

            Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

             

             
            * **Default VPC:** true 
             
            * **VPC:** false 
             

             

            If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

            
          

          - **StatusInfos** *(list) --* 

            The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

            
            

            - *(dict) --* 

              Provides a list of status information for a DB instance.

              
              

              - **StatusType** *(string) --* 

                This value is currently "read replication."

                
              

              - **Normal** *(boolean) --* 

                Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                
              

              - **Status** *(string) --* 

                Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                
              

              - **Message** *(string) --* 

                Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                
          
        
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB instance.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which the instance is associated for TDE encryption.

            
          

          - **DbInstancePort** *(integer) --* 

            Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

            
          

          - **DBClusterIdentifier** *(string) --* 

            If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB instance is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

            
          

          - **DbiResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

            
          

          - **CACertificateIdentifier** *(string) --* 

            The identifier of the CA certificate for this DB instance.

            
          

          - **DomainMemberships** *(list) --* 

            The Active Directory Domain membership records associated with the DB instance.

            
            

            - *(dict) --* 

              An Active Directory Domain membership record associated with the DB instance.

              
              

              - **Domain** *(string) --* 

                The identifier of the Active Directory Domain.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                
              

              - **FQDN** *(string) --* 

                The fully qualified domain name of the Active Directory Domain.

                
              

              - **IAMRoleName** *(string) --* 

                The name of the IAM role to be used when making API calls to the Directory Service.

                
          
        
          

          - **CopyTagsToSnapshot** *(boolean) --* 

            Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

            
          

          - **MonitoringInterval** *(integer) --* 

            The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

            
          

          - **EnhancedMonitoringResourceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

            
          

          - **MonitoringRoleArn** *(string) --* 

            The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

            
          

          - **PromotionTier** *(integer) --* 

            A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

            
          

          - **DBInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB instance.

            
      
    

  .. py:method:: remove_source_identifier_from_subscription(**kwargs)

    

    Removes a source identifier from an existing RDS event notification subscription.

    

    **Request Syntax** 
    ::

      response = client.remove_source_identifier_from_subscription(
          SubscriptionName='string',
          SourceIdentifier='string'
      )
    :type SubscriptionName: string
    :param SubscriptionName: **[REQUIRED]** 

      The name of the RDS event notification subscription you want to remove a source identifier from.

      

    
    :type SourceIdentifier: string
    :param SourceIdentifier: **[REQUIRED]** 

      The source identifier to be removed from the subscription, such as the **DB instance identifier** for a DB instance or the name of a security group. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EventSubscription': {
                'CustomerAwsId': 'string',
                'CustSubscriptionId': 'string',
                'SnsTopicArn': 'string',
                'Status': 'string',
                'SubscriptionCreationTime': 'string',
                'SourceType': 'string',
                'SourceIdsList': [
                    'string',
                ],
                'EventCategoriesList': [
                    'string',
                ],
                'Enabled': True|False,
                'EventSubscriptionArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **EventSubscription** *(dict) --* 

          Contains the results of a successful invocation of the  DescribeEventSubscriptions action.

          
          

          - **CustomerAwsId** *(string) --* 

            The AWS customer account associated with the RDS event notification subscription.

            
          

          - **CustSubscriptionId** *(string) --* 

            The RDS event notification subscription Id.

            
          

          - **SnsTopicArn** *(string) --* 

            The topic ARN of the RDS event notification subscription.

            
          

          - **Status** *(string) --* 

            The status of the RDS event notification subscription.

             

            Constraints:

             

            Can be one of the following: creating | modifying | deleting | active | no-permission | topic-not-exist

             

            The status "no-permission" indicates that RDS no longer has permission to post to the SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created.

            
          

          - **SubscriptionCreationTime** *(string) --* 

            The time the RDS event notification subscription was created.

            
          

          - **SourceType** *(string) --* 

            The source type for the RDS event notification subscription.

            
          

          - **SourceIdsList** *(list) --* 

            A list of source IDs for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **EventCategoriesList** *(list) --* 

            A list of event categories for the RDS event notification subscription.

            
            

            - *(string) --* 
        
          

          - **Enabled** *(boolean) --* 

            A Boolean value indicating if the subscription is enabled. True indicates the subscription is enabled.

            
          

          - **EventSubscriptionArn** *(string) --* 

            The Amazon Resource Name (ARN) for the event subscription.

            
      
    

  .. py:method:: remove_tags_from_resource(**kwargs)

    

    Removes metadata tags from an Amazon RDS resource.

     

    For an overview on tagging an Amazon RDS resource, see `Tagging Amazon RDS Resources`_ .

    

    **Request Syntax** 
    ::

      response = client.remove_tags_from_resource(
          ResourceName='string',
          TagKeys=[
              'string',
          ]
      )
    :type ResourceName: string
    :param ResourceName: **[REQUIRED]** 

      The Amazon RDS resource the tags will be removed from. This value is an Amazon Resource Name (ARN). For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN)`_ .

      

    
    :type TagKeys: list
    :param TagKeys: **[REQUIRED]** 

      The tag key (name) of the tag to be removed.

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: reset_db_cluster_parameter_group(**kwargs)

    

    Modifies the parameters of a DB cluster parameter group to the default value. To reset specific parameters submit a list of the following: ``ParameterName`` and ``ApplyMethod`` . To reset the entire DB cluster parameter group, specify the ``DBClusterParameterGroupName`` and ``ResetAllParameters`` parameters. 

     

    When resetting the entire group, dynamic parameters are updated immediately and static parameters are set to ``pending-reboot`` to take effect on the next DB instance restart or  RebootDBInstance request. You must call  RebootDBInstance for every DB instance in your DB cluster that you want the updated static parameter to apply to.

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.reset_db_cluster_parameter_group(
          DBClusterParameterGroupName='string',
          ResetAllParameters=True|False,
          Parameters=[
              {
                  'ParameterName': 'string',
                  'ParameterValue': 'string',
                  'Description': 'string',
                  'Source': 'string',
                  'ApplyType': 'string',
                  'DataType': 'string',
                  'AllowedValues': 'string',
                  'IsModifiable': True|False,
                  'MinimumEngineVersion': 'string',
                  'ApplyMethod': 'immediate'|'pending-reboot'
              },
          ]
      )
    :type DBClusterParameterGroupName: string
    :param DBClusterParameterGroupName: **[REQUIRED]** 

      The name of the DB cluster parameter group to reset.

      

    
    :type ResetAllParameters: boolean
    :param ResetAllParameters: 

      A value that is set to ``true`` to reset all parameters in the DB cluster parameter group to their default values, and ``false`` otherwise. You cannot use this parameter if there is a list of parameter names specified for the ``Parameters`` parameter.

      

    
    :type Parameters: list
    :param Parameters: 

      A list of parameter names in the DB cluster parameter group to reset to the default values. You cannot use this parameter if the ``ResetAllParameters`` parameter is set to ``true`` .

      

    
      - *(dict) --* 

        This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

         

        This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

        

      
        - **ParameterName** *(string) --* 

          Specifies the name of the parameter.

          

        
        - **ParameterValue** *(string) --* 

          Specifies the value of the parameter.

          

        
        - **Description** *(string) --* 

          Provides a description of the parameter.

          

        
        - **Source** *(string) --* 

          Indicates the source of the parameter value.

          

        
        - **ApplyType** *(string) --* 

          Specifies the engine specific parameters type.

          

        
        - **DataType** *(string) --* 

          Specifies the valid data type for the parameter.

          

        
        - **AllowedValues** *(string) --* 

          Specifies the valid range of values for the parameter.

          

        
        - **IsModifiable** *(boolean) --* 

          Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

          

        
        - **MinimumEngineVersion** *(string) --* 

          The earliest engine version to which the parameter can apply.

          

        
        - **ApplyMethod** *(string) --* 

          Indicates when to apply parameter updates.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBClusterParameterGroupName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        

        
        

        - **DBClusterParameterGroupName** *(string) --* 

          The name of the DB cluster parameter group.

           

          Constraints:

           

           
          * Must be 1 to 255 alphanumeric characters 
           
          * First character must be a letter 
           
          * Cannot end with a hyphen or contain two consecutive hyphens 
           

           

          .. note::

             

            This value is stored as a lowercase string.

             

          
    

  .. py:method:: reset_db_parameter_group(**kwargs)

    

    Modifies the parameters of a DB parameter group to the engine/system default value. To reset specific parameters submit a list of the following: ``ParameterName`` and ``ApplyMethod`` . To reset the entire DB parameter group, specify the ``DBParameterGroup`` name and ``ResetAllParameters`` parameters. When resetting the entire group, dynamic parameters are updated immediately and static parameters are set to ``pending-reboot`` to take effect on the next DB instance restart or ``RebootDBInstance`` request. 

    

    **Request Syntax** 
    ::

      response = client.reset_db_parameter_group(
          DBParameterGroupName='string',
          ResetAllParameters=True|False,
          Parameters=[
              {
                  'ParameterName': 'string',
                  'ParameterValue': 'string',
                  'Description': 'string',
                  'Source': 'string',
                  'ApplyType': 'string',
                  'DataType': 'string',
                  'AllowedValues': 'string',
                  'IsModifiable': True|False,
                  'MinimumEngineVersion': 'string',
                  'ApplyMethod': 'immediate'|'pending-reboot'
              },
          ]
      )
    :type DBParameterGroupName: string
    :param DBParameterGroupName: **[REQUIRED]** 

      The name of the DB parameter group.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type ResetAllParameters: boolean
    :param ResetAllParameters: 

      Specifies whether (``true`` ) or not (``false`` ) to reset all parameters in the DB parameter group to default values. 

       

      Default: ``true``  

      

    
    :type Parameters: list
    :param Parameters: 

      An array of parameter names, values, and the apply method for the parameter update. At least one parameter name, value, and apply method must be supplied; subsequent arguments are optional. A maximum of 20 parameters can be modified in a single request.

       

       **MySQL**  

       

      Valid Values (for Apply method): ``immediate`` | ``pending-reboot``  

       

      You can use the immediate value with dynamic parameters only. You can use the ``pending-reboot`` value for both dynamic and static parameters, and changes are applied when DB instance reboots.

       

       **MariaDB**  

       

      Valid Values (for Apply method): ``immediate`` | ``pending-reboot``  

       

      You can use the immediate value with dynamic parameters only. You can use the ``pending-reboot`` value for both dynamic and static parameters, and changes are applied when DB instance reboots.

       

       **Oracle**  

       

      Valid Values (for Apply method): ``pending-reboot``  

      

    
      - *(dict) --* 

        This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

         

        This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

        

      
        - **ParameterName** *(string) --* 

          Specifies the name of the parameter.

          

        
        - **ParameterValue** *(string) --* 

          Specifies the value of the parameter.

          

        
        - **Description** *(string) --* 

          Provides a description of the parameter.

          

        
        - **Source** *(string) --* 

          Indicates the source of the parameter value.

          

        
        - **ApplyType** *(string) --* 

          Specifies the engine specific parameters type.

          

        
        - **DataType** *(string) --* 

          Specifies the valid data type for the parameter.

          

        
        - **AllowedValues** *(string) --* 

          Specifies the valid range of values for the parameter.

          

        
        - **IsModifiable** *(boolean) --* 

          Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

          

        
        - **MinimumEngineVersion** *(string) --* 

          The earliest engine version to which the parameter can apply.

          

        
        - **ApplyMethod** *(string) --* 

          Indicates when to apply parameter updates.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBParameterGroupName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  ModifyDBParameterGroup or  ResetDBParameterGroup action. 

        
        

        - **DBParameterGroupName** *(string) --* 

          Provides the name of the DB parameter group.

          
    

  .. py:method:: restore_db_cluster_from_s3(**kwargs)

    

    Creates an Amazon Aurora DB cluster from data stored in an Amazon S3 bucket. Amazon RDS must be authorized to access the Amazon S3 bucket and the data must be created using the Percona XtraBackup utility as described in `Migrating Data from an External MySQL Database to an Amazon Aurora DB Cluster`_ .

    

    **Request Syntax** 
    ::

      response = client.restore_db_cluster_from_s3(
          AvailabilityZones=[
              'string',
          ],
          BackupRetentionPeriod=123,
          CharacterSetName='string',
          DatabaseName='string',
          DBClusterIdentifier='string',
          DBClusterParameterGroupName='string',
          VpcSecurityGroupIds=[
              'string',
          ],
          DBSubnetGroupName='string',
          Engine='string',
          EngineVersion='string',
          Port=123,
          MasterUsername='string',
          MasterUserPassword='string',
          OptionGroupName='string',
          PreferredBackupWindow='string',
          PreferredMaintenanceWindow='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          StorageEncrypted=True|False,
          KmsKeyId='string',
          SourceEngine='string',
          SourceEngineVersion='string',
          S3BucketName='string',
          S3Prefix='string',
          S3IngestionRoleArn='string'
      )
    :type AvailabilityZones: list
    :param AvailabilityZones: 

      A list of EC2 Availability Zones that instances in the restored DB cluster can be created in.

      

    
      - *(string) --* 

      
  
    :type BackupRetentionPeriod: integer
    :param BackupRetentionPeriod: 

      The number of days for which automated backups of the restored DB cluster are retained. You must specify a minimum value of 1.

       

      Default: 1

       

      Constraints:

       

       
      * Must be a value from 1 to 35 
       

      

    
    :type CharacterSetName: string
    :param CharacterSetName: 

      A value that indicates that the restored DB cluster should be associated with the specified CharacterSet.

      

    
    :type DatabaseName: string
    :param DatabaseName: 

      The database name for the restored DB cluster.

      

    
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: **[REQUIRED]** 

      The name of the DB cluster to create from the source data in the S3 bucket. This parameter is isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

       

      Example: ``my-cluster1``  

      

    
    :type DBClusterParameterGroupName: string
    :param DBClusterParameterGroupName: 

      The name of the DB cluster parameter group to associate with the restored DB cluster. If this argument is omitted, ``default.aurora5.6`` will be used. 

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type VpcSecurityGroupIds: list
    :param VpcSecurityGroupIds: 

      A list of EC2 VPC security groups to associate with the restored DB cluster.

      

    
      - *(string) --* 

      
  
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      A DB subnet group to associate with the restored DB cluster.

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    :type Engine: string
    :param Engine: **[REQUIRED]** 

      The name of the database engine to be used for the restored DB cluster.

       

      Valid Values: ``aurora``  

      

    
    :type EngineVersion: string
    :param EngineVersion: 

      The version number of the database engine to use.

       

       **Aurora**  

       

      Example: ``5.6.10a``  

      

    
    :type Port: integer
    :param Port: 

      The port number on which the instances in the restored DB cluster accept connections.

       

      Default: ``3306``  

      

    
    :type MasterUsername: string
    :param MasterUsername: **[REQUIRED]** 

      The name of the master user for the restored DB cluster.

       

      Constraints:

       

       
      * Must be 1 to 16 alphanumeric characters. 
       
      * First character must be a letter. 
       
      * Cannot be a reserved word for the chosen database engine. 
       

      

    
    :type MasterUserPassword: string
    :param MasterUserPassword: **[REQUIRED]** 

      The password for the master database user. This password can contain any printable ASCII character except "/", """, or "@".

       

      Constraints: Must contain from 8 to 41 characters.

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      A value that indicates that the restored DB cluster should be associated with the specified option group.

       

      Permanent options cannot be removed from an option group. An option group cannot be removed from a DB cluster once it is associated with a DB cluster.

      

    
    :type PreferredBackupWindow: string
    :param PreferredBackupWindow: 

      The daily time range during which automated backups are created if automated backups are enabled using the ``BackupRetentionPeriod`` parameter. 

       

      Default: A 30-minute window selected at random from an 8-hour block of time per region. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

       

      Constraints:

       

       
      * Must be in the format ``hh24:mi-hh24:mi`` . 
       
      * Times should be in Universal Coordinated Time (UTC). 
       
      * Must not conflict with the preferred maintenance window. 
       
      * Must be at least 30 minutes. 
       

      

    
    :type PreferredMaintenanceWindow: string
    :param PreferredMaintenanceWindow: 

      The weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

       

      Format: ``ddd:hh24:mi-ddd:hh24:mi``  

       

      Default: A 30-minute window selected at random from an 8-hour block of time per region, occurring on a random day of the week. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

       

      Valid Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun

       

      Constraints: Minimum 30-minute window.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    :type StorageEncrypted: boolean
    :param StorageEncrypted: 

      Specifies whether the restored DB cluster is encrypted.

      

    
    :type KmsKeyId: string
    :param KmsKeyId: 

      The KMS key identifier for an encrypted DB cluster.

       

      The KMS key identifier is the Amazon Resource Name (ARN) for the KMS encryption key. If you are creating a DB cluster with the same AWS account that owns the KMS encryption key used to encrypt the new DB cluster, then you can use the KMS key alias instead of the ARN for the KM encryption key.

       

      If the ``StorageEncrypted`` parameter is true, and you do not specify a value for the ``KmsKeyId`` parameter, then Amazon RDS will use your default encryption key. AWS KMS creates the default encryption key for your AWS account. Your AWS account has a different default encryption key for each AWS region.

      

    
    :type SourceEngine: string
    :param SourceEngine: **[REQUIRED]** 

      The identifier for the database engine that was backed up to create the files stored in the Amazon S3 bucket. 

       

      Valid values: ``mysql``  

      

    
    :type SourceEngineVersion: string
    :param SourceEngineVersion: **[REQUIRED]** 

      The version of the database that the backup files were created from.

       

      MySQL version 5.5 and 5.6 are supported. 

       

      Example: ``5.6.22``  

      

    
    :type S3BucketName: string
    :param S3BucketName: **[REQUIRED]** 

      The name of the Amazon S3 bucket that contains the data used to create the Amazon Aurora DB cluster.

      

    
    :type S3Prefix: string
    :param S3Prefix: 

      The prefix for all of the file names that contain the data used to create the Amazon Aurora DB cluster. If you do not specify a **SourceS3Prefix** value, then the Amazon Aurora DB cluster is created by using all of the files in the Amazon S3 bucket.

      

    
    :type S3IngestionRoleArn: string
    :param S3IngestionRoleArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that authorizes Amazon RDS to access the Amazon S3 bucket on your behalf.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBCluster': {
                'AllocatedStorage': 123,
                'AvailabilityZones': [
                    'string',
                ],
                'BackupRetentionPeriod': 123,
                'CharacterSetName': 'string',
                'DatabaseName': 'string',
                'DBClusterIdentifier': 'string',
                'DBClusterParameterGroup': 'string',
                'DBSubnetGroup': 'string',
                'Status': 'string',
                'PercentProgress': 'string',
                'EarliestRestorableTime': datetime(2015, 1, 1),
                'Endpoint': 'string',
                'Engine': 'string',
                'EngineVersion': 'string',
                'LatestRestorableTime': datetime(2015, 1, 1),
                'Port': 123,
                'MasterUsername': 'string',
                'DBClusterOptionGroupMemberships': [
                    {
                        'DBClusterOptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'PreferredBackupWindow': 'string',
                'PreferredMaintenanceWindow': 'string',
                'ReplicationSourceIdentifier': 'string',
                'ReadReplicaIdentifiers': [
                    'string',
                ],
                'DBClusterMembers': [
                    {
                        'DBInstanceIdentifier': 'string',
                        'IsClusterWriter': True|False,
                        'DBClusterParameterGroupStatus': 'string',
                        'PromotionTier': 123
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'HostedZoneId': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbClusterResourceId': 'string',
                'DBClusterArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBCluster** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBCluster   
           
          *  DeleteDBCluster   
           
          *  FailoverDBCluster   
           
          *  ModifyDBCluster   
           
          *  RestoreDBClusterFromSnapshot   
           
          *  RestoreDBClusterToPointInTime   
           

           

          This data type is used as a response element in the  DescribeDBClusters action.

          
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

            
            

            - *(string) --* 
        
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this cluster is associated with.

            
          

          - **DatabaseName** *(string) --* 

            Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster.

            
          

          - **DBClusterParameterGroup** *(string) --* 

            Specifies the name of the DB cluster parameter group for the DB cluster.

            
          

          - **DBSubnetGroup** *(string) --* 

            Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group.

            
          

          - **Status** *(string) --* 

            Specifies the current state of this DB cluster.

            
          

          - **PercentProgress** *(string) --* 

            Specifies the progress of the operation as a percentage.

            
          

          - **EarliestRestorableTime** *(datetime) --* 

            Specifies the earliest time to which a database can be restored with point-in-time restore.

            
          

          - **Endpoint** *(string) --* 

            Specifies the connection endpoint for the primary instance of the DB cluster.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB cluster.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine is listening on.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB cluster.

            
          

          - **DBClusterOptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB cluster.

            
            

            - *(dict) --* 

              Contains status information for a DB cluster option group.

              
              

              - **DBClusterOptionGroupName** *(string) --* 

                Specifies the name of the DB cluster option group.

                
              

              - **Status** *(string) --* 

                Specifies the status of the DB cluster option group.

                
          
        
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **ReplicationSourceIdentifier** *(string) --* 

            Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

            
          

          - **ReadReplicaIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB cluster.

            
            

            - *(string) --* 
        
          

          - **DBClusterMembers** *(list) --* 

            Provides the list of instances that make up the DB cluster.

            
            

            - *(dict) --* 

              Contains information about an instance that is part of a DB cluster.

              
              

              - **DBInstanceIdentifier** *(string) --* 

                Specifies the instance identifier for this member of the DB cluster.

                
              

              - **IsClusterWriter** *(boolean) --* 

                Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

                
              

              - **DBClusterParameterGroupStatus** *(string) --* 

                Specifies the status of the DB cluster parameter group for this member of the DB cluster.

                
              

              - **PromotionTier** *(integer) --* 

                A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides a list of VPC security groups that the DB cluster belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **HostedZoneId** *(string) --* 

            Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

            
          

          - **DbClusterResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed.

            
          

          - **DBClusterArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster.

            
      
    

  .. py:method:: restore_db_cluster_from_snapshot(**kwargs)

    

    Creates a new DB cluster from a DB cluster snapshot. The target DB cluster is created from the source DB cluster restore point with the same configuration as the original source DB cluster, except that the new DB cluster is created with the default security group.

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.restore_db_cluster_from_snapshot(
          AvailabilityZones=[
              'string',
          ],
          DBClusterIdentifier='string',
          SnapshotIdentifier='string',
          Engine='string',
          EngineVersion='string',
          Port=123,
          DBSubnetGroupName='string',
          DatabaseName='string',
          OptionGroupName='string',
          VpcSecurityGroupIds=[
              'string',
          ],
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          KmsKeyId='string'
      )
    :type AvailabilityZones: list
    :param AvailabilityZones: 

      Provides the list of EC2 Availability Zones that instances in the restored DB cluster can be created in.

      

    
      - *(string) --* 

      
  
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: **[REQUIRED]** 

      The name of the DB cluster to create from the DB cluster snapshot. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 255 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``my-snapshot-id``  

      

    
    :type SnapshotIdentifier: string
    :param SnapshotIdentifier: **[REQUIRED]** 

      The identifier for the DB cluster snapshot to restore from.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Engine: string
    :param Engine: **[REQUIRED]** 

      The database engine to use for the new DB cluster.

       

      Default: The same as source

       

      Constraint: Must be compatible with the engine of the source

      

    
    :type EngineVersion: string
    :param EngineVersion: 

      The version of the database engine to use for the new DB cluster.

      

    
    :type Port: integer
    :param Port: 

      The port number on which the new DB cluster accepts connections.

       

      Constraints: Value must be ``1150-65535``  

       

      Default: The same port as the original DB cluster.

      

    
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      The name of the DB subnet group to use for the new DB cluster.

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    :type DatabaseName: string
    :param DatabaseName: 

      The database name for the restored DB cluster.

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      The name of the option group to use for the restored DB cluster.

      

    
    :type VpcSecurityGroupIds: list
    :param VpcSecurityGroupIds: 

      A list of VPC security groups that the new DB cluster will belong to.

      

    
      - *(string) --* 

      
  
    :type Tags: list
    :param Tags: 

      The tags to be assigned to the restored DB cluster.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    :type KmsKeyId: string
    :param KmsKeyId: 

      The KMS key identifier to use when restoring an encrypted DB cluster from a DB cluster snapshot.

       

      The KMS key identifier is the Amazon Resource Name (ARN) for the KMS encryption key. If you are restoring a DB cluster with the same AWS account that owns the KMS encryption key used to encrypt the new DB cluster, then you can use the KMS key alias instead of the ARN for the KMS encryption key.

       

      If you do not specify a value for the ``KmsKeyId`` parameter, then the following will occur:

       

       
      * If the DB cluster snapshot is encrypted, then the restored DB cluster is encrypted using the KMS key that was used to encrypt the DB cluster snapshot. 
       
      * If the DB cluster snapshot is not encrypted, then the restored DB cluster is encrypted using the specified encryption key. 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBCluster': {
                'AllocatedStorage': 123,
                'AvailabilityZones': [
                    'string',
                ],
                'BackupRetentionPeriod': 123,
                'CharacterSetName': 'string',
                'DatabaseName': 'string',
                'DBClusterIdentifier': 'string',
                'DBClusterParameterGroup': 'string',
                'DBSubnetGroup': 'string',
                'Status': 'string',
                'PercentProgress': 'string',
                'EarliestRestorableTime': datetime(2015, 1, 1),
                'Endpoint': 'string',
                'Engine': 'string',
                'EngineVersion': 'string',
                'LatestRestorableTime': datetime(2015, 1, 1),
                'Port': 123,
                'MasterUsername': 'string',
                'DBClusterOptionGroupMemberships': [
                    {
                        'DBClusterOptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'PreferredBackupWindow': 'string',
                'PreferredMaintenanceWindow': 'string',
                'ReplicationSourceIdentifier': 'string',
                'ReadReplicaIdentifiers': [
                    'string',
                ],
                'DBClusterMembers': [
                    {
                        'DBInstanceIdentifier': 'string',
                        'IsClusterWriter': True|False,
                        'DBClusterParameterGroupStatus': 'string',
                        'PromotionTier': 123
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'HostedZoneId': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbClusterResourceId': 'string',
                'DBClusterArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBCluster** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBCluster   
           
          *  DeleteDBCluster   
           
          *  FailoverDBCluster   
           
          *  ModifyDBCluster   
           
          *  RestoreDBClusterFromSnapshot   
           
          *  RestoreDBClusterToPointInTime   
           

           

          This data type is used as a response element in the  DescribeDBClusters action.

          
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

            
            

            - *(string) --* 
        
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this cluster is associated with.

            
          

          - **DatabaseName** *(string) --* 

            Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster.

            
          

          - **DBClusterParameterGroup** *(string) --* 

            Specifies the name of the DB cluster parameter group for the DB cluster.

            
          

          - **DBSubnetGroup** *(string) --* 

            Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group.

            
          

          - **Status** *(string) --* 

            Specifies the current state of this DB cluster.

            
          

          - **PercentProgress** *(string) --* 

            Specifies the progress of the operation as a percentage.

            
          

          - **EarliestRestorableTime** *(datetime) --* 

            Specifies the earliest time to which a database can be restored with point-in-time restore.

            
          

          - **Endpoint** *(string) --* 

            Specifies the connection endpoint for the primary instance of the DB cluster.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB cluster.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine is listening on.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB cluster.

            
          

          - **DBClusterOptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB cluster.

            
            

            - *(dict) --* 

              Contains status information for a DB cluster option group.

              
              

              - **DBClusterOptionGroupName** *(string) --* 

                Specifies the name of the DB cluster option group.

                
              

              - **Status** *(string) --* 

                Specifies the status of the DB cluster option group.

                
          
        
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **ReplicationSourceIdentifier** *(string) --* 

            Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

            
          

          - **ReadReplicaIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB cluster.

            
            

            - *(string) --* 
        
          

          - **DBClusterMembers** *(list) --* 

            Provides the list of instances that make up the DB cluster.

            
            

            - *(dict) --* 

              Contains information about an instance that is part of a DB cluster.

              
              

              - **DBInstanceIdentifier** *(string) --* 

                Specifies the instance identifier for this member of the DB cluster.

                
              

              - **IsClusterWriter** *(boolean) --* 

                Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

                
              

              - **DBClusterParameterGroupStatus** *(string) --* 

                Specifies the status of the DB cluster parameter group for this member of the DB cluster.

                
              

              - **PromotionTier** *(integer) --* 

                A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides a list of VPC security groups that the DB cluster belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **HostedZoneId** *(string) --* 

            Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

            
          

          - **DbClusterResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed.

            
          

          - **DBClusterArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster.

            
      
    

  .. py:method:: restore_db_cluster_to_point_in_time(**kwargs)

    

    Restores a DB cluster to an arbitrary point in time. Users can restore to any point in time before ``LatestRestorableTime`` for up to ``BackupRetentionPeriod`` days. The target DB cluster is created from the source DB cluster with the same configuration as the original DB cluster, except that the new DB cluster is created with the default DB security group. 

     

    For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.*  

    

    **Request Syntax** 
    ::

      response = client.restore_db_cluster_to_point_in_time(
          DBClusterIdentifier='string',
          SourceDBClusterIdentifier='string',
          RestoreToTime=datetime(2015, 1, 1),
          UseLatestRestorableTime=True|False,
          Port=123,
          DBSubnetGroupName='string',
          OptionGroupName='string',
          VpcSecurityGroupIds=[
              'string',
          ],
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          KmsKeyId='string'
      )
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: **[REQUIRED]** 

      The name of the new DB cluster to be created.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type SourceDBClusterIdentifier: string
    :param SourceDBClusterIdentifier: **[REQUIRED]** 

      The identifier of the source DB cluster from which to restore.

       

      Constraints:

       

       
      * Must be the identifier of an existing database instance 
       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type RestoreToTime: datetime
    :param RestoreToTime: 

      The date and time to restore the DB cluster to.

       

      Valid Values: Value must be a time in Universal Coordinated Time (UTC) format

       

      Constraints:

       

       
      * Must be before the latest restorable time for the DB instance 
       
      * Cannot be specified if ``UseLatestRestorableTime`` parameter is true 
       

       

      Example: ``2015-03-07T23:45:00Z``  

      

    
    :type UseLatestRestorableTime: boolean
    :param UseLatestRestorableTime: 

      A value that is set to ``true`` to restore the DB cluster to the latest restorable backup time, and ``false`` otherwise. 

       

      Default: ``false``  

       

      Constraints: Cannot be specified if ``RestoreToTime`` parameter is provided.

      

    
    :type Port: integer
    :param Port: 

      The port number on which the new DB cluster accepts connections.

       

      Constraints: Value must be ``1150-65535``  

       

      Default: The same port as the original DB cluster.

      

    
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      The DB subnet group name to use for the new DB cluster.

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      The name of the option group for the new DB cluster.

      

    
    :type VpcSecurityGroupIds: list
    :param VpcSecurityGroupIds: 

      A lst of VPC security groups that the new DB cluster belongs to.

      

    
      - *(string) --* 

      
  
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    :type KmsKeyId: string
    :param KmsKeyId: 

      The KMS key identifier to use when restoring an encrypted DB cluster from an encrypted DB cluster.

       

      The KMS key identifier is the Amazon Resource Name (ARN) for the KMS encryption key. If you are restoring a DB cluster with the same AWS account that owns the KMS encryption key used to encrypt the new DB cluster, then you can use the KMS key alias instead of the ARN for the KMS encryption key.

       

      You can restore to a new DB cluster and encrypt the new DB cluster with a KMS key that is different than the KMS key used to encrypt the source DB cluster. The new DB cluster will be encrypted with the KMS key identified by the ``KmsKeyId`` parameter.

       

      If you do not specify a value for the ``KmsKeyId`` parameter, then the following will occur:

       

       
      * If the DB cluster is encrypted, then the restored DB cluster is encrypted using the KMS key that was used to encrypt the source DB cluster. 
       
      * If the DB cluster is not encrypted, then the restored DB cluster is not encrypted. 
       

       

      If ``DBClusterIdentifier`` refers to a DB cluster that is note encrypted, then the restore request is rejected.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBCluster': {
                'AllocatedStorage': 123,
                'AvailabilityZones': [
                    'string',
                ],
                'BackupRetentionPeriod': 123,
                'CharacterSetName': 'string',
                'DatabaseName': 'string',
                'DBClusterIdentifier': 'string',
                'DBClusterParameterGroup': 'string',
                'DBSubnetGroup': 'string',
                'Status': 'string',
                'PercentProgress': 'string',
                'EarliestRestorableTime': datetime(2015, 1, 1),
                'Endpoint': 'string',
                'Engine': 'string',
                'EngineVersion': 'string',
                'LatestRestorableTime': datetime(2015, 1, 1),
                'Port': 123,
                'MasterUsername': 'string',
                'DBClusterOptionGroupMemberships': [
                    {
                        'DBClusterOptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'PreferredBackupWindow': 'string',
                'PreferredMaintenanceWindow': 'string',
                'ReplicationSourceIdentifier': 'string',
                'ReadReplicaIdentifiers': [
                    'string',
                ],
                'DBClusterMembers': [
                    {
                        'DBInstanceIdentifier': 'string',
                        'IsClusterWriter': True|False,
                        'DBClusterParameterGroupStatus': 'string',
                        'PromotionTier': 123
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'HostedZoneId': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbClusterResourceId': 'string',
                'DBClusterArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBCluster** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBCluster   
           
          *  DeleteDBCluster   
           
          *  FailoverDBCluster   
           
          *  ModifyDBCluster   
           
          *  RestoreDBClusterFromSnapshot   
           
          *  RestoreDBClusterToPointInTime   
           

           

          This data type is used as a response element in the  DescribeDBClusters action.

          
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size in gigabytes (GB).

            
          

          - **AvailabilityZones** *(list) --* 

            Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

            
            

            - *(string) --* 
        
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this cluster is associated with.

            
          

          - **DatabaseName** *(string) --* 

            Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster.

            
          

          - **DBClusterIdentifier** *(string) --* 

            Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster.

            
          

          - **DBClusterParameterGroup** *(string) --* 

            Specifies the name of the DB cluster parameter group for the DB cluster.

            
          

          - **DBSubnetGroup** *(string) --* 

            Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group.

            
          

          - **Status** *(string) --* 

            Specifies the current state of this DB cluster.

            
          

          - **PercentProgress** *(string) --* 

            Specifies the progress of the operation as a percentage.

            
          

          - **EarliestRestorableTime** *(datetime) --* 

            Specifies the earliest time to which a database can be restored with point-in-time restore.

            
          

          - **Endpoint** *(string) --* 

            Specifies the connection endpoint for the primary instance of the DB cluster.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB cluster.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **Port** *(integer) --* 

            Specifies the port that the database engine is listening on.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB cluster.

            
          

          - **DBClusterOptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB cluster.

            
            

            - *(dict) --* 

              Contains status information for a DB cluster option group.

              
              

              - **DBClusterOptionGroupName** *(string) --* 

                Specifies the name of the DB cluster option group.

                
              

              - **Status** *(string) --* 

                Specifies the status of the DB cluster option group.

                
          
        
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **ReplicationSourceIdentifier** *(string) --* 

            Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

            
          

          - **ReadReplicaIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB cluster.

            
            

            - *(string) --* 
        
          

          - **DBClusterMembers** *(list) --* 

            Provides the list of instances that make up the DB cluster.

            
            

            - *(dict) --* 

              Contains information about an instance that is part of a DB cluster.

              
              

              - **DBInstanceIdentifier** *(string) --* 

                Specifies the instance identifier for this member of the DB cluster.

                
              

              - **IsClusterWriter** *(boolean) --* 

                Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

                
              

              - **DBClusterParameterGroupStatus** *(string) --* 

                Specifies the status of the DB cluster parameter group for this member of the DB cluster.

                
              

              - **PromotionTier** *(integer) --* 

                A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides a list of VPC security groups that the DB cluster belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **HostedZoneId** *(string) --* 

            Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB cluster is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

            
          

          - **DbClusterResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed.

            
          

          - **DBClusterArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB cluster.

            
      
    

  .. py:method:: restore_db_instance_from_db_snapshot(**kwargs)

    

    Creates a new DB instance from a DB snapshot. The target database is created from the source database restore point with the most of original configuration with the default security group and the default DB parameter group. By default, the new DB instance is created as a single-AZ deployment except when the instance is a SQL Server instance that has an option group that is associated with mirroring; in this case, the instance becomes a mirrored AZ deployment and not a single-AZ deployment.

     

    If your intent is to replace your original DB instance with the new, restored DB instance, then rename your original DB instance before you call the RestoreDBInstanceFromDBSnapshot action. RDS does not allow two DB instances with the same name. Once you have renamed your original DB instance with a different identifier, then you can pass the original name of the DB instance as the DBInstanceIdentifier in the call to the RestoreDBInstanceFromDBSnapshot action. The result is that you will replace the original DB instance with the DB instance created from the snapshot.

     

    If you are restoring from a shared manual DB snapshot, the ``DBSnapshotIdentifier`` must be the ARN of the shared DB snapshot.

    

    **Request Syntax** 
    ::

      response = client.restore_db_instance_from_db_snapshot(
          DBInstanceIdentifier='string',
          DBSnapshotIdentifier='string',
          DBInstanceClass='string',
          Port=123,
          AvailabilityZone='string',
          DBSubnetGroupName='string',
          MultiAZ=True|False,
          PubliclyAccessible=True|False,
          AutoMinorVersionUpgrade=True|False,
          LicenseModel='string',
          DBName='string',
          Engine='string',
          Iops=123,
          OptionGroupName='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          StorageType='string',
          TdeCredentialArn='string',
          TdeCredentialPassword='string',
          Domain='string',
          CopyTagsToSnapshot=True|False,
          DomainIAMRoleName='string'
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      Name of the DB instance to create from the DB snapshot. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens (1 to 15 for SQL Server) 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      Example: ``my-snapshot-id``  

      

    
    :type DBSnapshotIdentifier: string
    :param DBSnapshotIdentifier: **[REQUIRED]** 

      The identifier for the DB snapshot to restore from.

       

      Constraints:

       

       
      * Must contain from 1 to 255 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

       

      If you are restoring from a shared manual DB snapshot, the ``DBSnapshotIdentifier`` must be the ARN of the shared DB snapshot.

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The compute and memory capacity of the Amazon RDS DB instance.

       

      Valid Values: ``db.t1.micro | db.m1.small | db.m1.medium | db.m1.large | db.m1.xlarge | db.m2.2xlarge | db.m2.4xlarge | db.m3.medium | db.m3.large | db.m3.xlarge | db.m3.2xlarge | db.m4.large | db.m4.xlarge | db.m4.2xlarge | db.m4.4xlarge | db.m4.10xlarge | db.r3.large | db.r3.xlarge | db.r3.2xlarge | db.r3.4xlarge | db.r3.8xlarge | db.t2.micro | db.t2.small | db.t2.medium | db.t2.large``  

      

    
    :type Port: integer
    :param Port: 

      The port number on which the database accepts connections.

       

      Default: The same port as the original DB instance

       

      Constraints: Value must be ``1150-65535``  

      

    
    :type AvailabilityZone: string
    :param AvailabilityZone: 

      The EC2 Availability Zone that the database instance will be created in.

       

      Default: A random, system-chosen Availability Zone.

       

      Constraint: You cannot specify the AvailabilityZone parameter if the MultiAZ parameter is set to ``true`` .

       

      Example: ``us-east-1a``  

      

    
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      The DB subnet group name to use for the new instance.

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    :type MultiAZ: boolean
    :param MultiAZ: 

      Specifies if the DB instance is a Multi-AZ deployment.

       

      Constraint: You cannot specify the AvailabilityZone parameter if the MultiAZ parameter is set to ``true`` .

      

    
    :type PubliclyAccessible: boolean
    :param PubliclyAccessible: 

      Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

       

      Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

       

       
      * **Default VPC:** true 
       
      * **VPC:** false 
       

       

      If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

      

    
    :type AutoMinorVersionUpgrade: boolean
    :param AutoMinorVersionUpgrade: 

      Indicates that minor version upgrades will be applied automatically to the DB instance during the maintenance window.

      

    
    :type LicenseModel: string
    :param LicenseModel: 

      License model information for the restored DB instance.

       

      Default: Same as source.

       

      Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

      

    
    :type DBName: string
    :param DBName: 

      The database name for the restored DB instance.

       

      .. note::

         

        This parameter doesn't apply to the MySQL, PostgreSQL, or MariaDB engines.

         

      

    
    :type Engine: string
    :param Engine: 

      The database engine to use for the new instance.

       

      Default: The same as source

       

      Constraint: Must be compatible with the engine of the source

       

      Valid Values: ``MySQL`` | ``mariadb`` | ``oracle-se1`` | ``oracle-se`` | ``oracle-ee`` | ``sqlserver-ee`` | ``sqlserver-se`` | ``sqlserver-ex`` | ``sqlserver-web`` | ``postgres`` | ``aurora``  

      

    
    :type Iops: integer
    :param Iops: 

      Specifies the amount of provisioned IOPS for the DB instance, expressed in I/O operations per second. If this parameter is not specified, the IOPS value will be taken from the backup. If this parameter is set to 0, the new instance will be converted to a non-PIOPS instance, which will take additional time, though your DB instance will be available for connections before the conversion starts.

       

      Constraints: Must be an integer greater than 1000.

       

       **SQL Server**  

       

      Setting the IOPS value for the SQL Server database engine is not supported.

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      The name of the option group to be used for the restored DB instance.

       

      Permanent options, such as the TDE option for Oracle Advanced Security TDE, cannot be removed from an option group, and that option group cannot be removed from a DB instance once it is associated with a DB instance

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    :type StorageType: string
    :param StorageType: 

      Specifies the storage type to be associated with the DB instance.

       

      Valid values: ``standard | gp2 | io1``  

       

      If you specify ``io1`` , you must also include a value for the ``Iops`` parameter. 

       

      Default: ``io1`` if the ``Iops`` parameter is specified; otherwise ``standard``  

      

    
    :type TdeCredentialArn: string
    :param TdeCredentialArn: 

      The ARN from the Key Store with which to associate the instance for TDE encryption.

      

    
    :type TdeCredentialPassword: string
    :param TdeCredentialPassword: 

      The password for the given ARN from the Key Store in order to access the device.

      

    
    :type Domain: string
    :param Domain: 

      Specify the Active Directory Domain to restore the instance in.

      

    
    :type CopyTagsToSnapshot: boolean
    :param CopyTagsToSnapshot: 

      True to copy all tags from the restored DB instance to snapshots of the DB instance; otherwise false. The default is false.

      

    
    :type DomainIAMRoleName: string
    :param DomainIAMRoleName: 

      Specify the name of the IAM role to be used when making API calls to the Directory Service.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBInstance': {
                'DBInstanceIdentifier': 'string',
                'DBInstanceClass': 'string',
                'Engine': 'string',
                'DBInstanceStatus': 'string',
                'MasterUsername': 'string',
                'DBName': 'string',
                'Endpoint': {
                    'Address': 'string',
                    'Port': 123,
                    'HostedZoneId': 'string'
                },
                'AllocatedStorage': 123,
                'InstanceCreateTime': datetime(2015, 1, 1),
                'PreferredBackupWindow': 'string',
                'BackupRetentionPeriod': 123,
                'DBSecurityGroups': [
                    {
                        'DBSecurityGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'DBParameterGroups': [
                    {
                        'DBParameterGroupName': 'string',
                        'ParameterApplyStatus': 'string'
                    },
                ],
                'AvailabilityZone': 'string',
                'DBSubnetGroup': {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
                'PreferredMaintenanceWindow': 'string',
                'PendingModifiedValues': {
                    'DBInstanceClass': 'string',
                    'AllocatedStorage': 123,
                    'MasterUserPassword': 'string',
                    'Port': 123,
                    'BackupRetentionPeriod': 123,
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'DBInstanceIdentifier': 'string',
                    'StorageType': 'string',
                    'CACertificateIdentifier': 'string',
                    'DBSubnetGroupName': 'string'
                },
                'LatestRestorableTime': datetime(2015, 1, 1),
                'MultiAZ': True|False,
                'EngineVersion': 'string',
                'AutoMinorVersionUpgrade': True|False,
                'ReadReplicaSourceDBInstanceIdentifier': 'string',
                'ReadReplicaDBInstanceIdentifiers': [
                    'string',
                ],
                'LicenseModel': 'string',
                'Iops': 123,
                'OptionGroupMemberships': [
                    {
                        'OptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'CharacterSetName': 'string',
                'SecondaryAvailabilityZone': 'string',
                'PubliclyAccessible': True|False,
                'StatusInfos': [
                    {
                        'StatusType': 'string',
                        'Normal': True|False,
                        'Status': 'string',
                        'Message': 'string'
                    },
                ],
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'DbInstancePort': 123,
                'DBClusterIdentifier': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbiResourceId': 'string',
                'CACertificateIdentifier': 'string',
                'DomainMemberships': [
                    {
                        'Domain': 'string',
                        'Status': 'string',
                        'FQDN': 'string',
                        'IAMRoleName': 'string'
                    },
                ],
                'CopyTagsToSnapshot': True|False,
                'MonitoringInterval': 123,
                'EnhancedMonitoringResourceArn': 'string',
                'MonitoringRoleArn': 'string',
                'PromotionTier': 123,
                'DBInstanceArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBInstance** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBInstance   
           
          *  DeleteDBInstance   
           
          *  ModifyDBInstance   
           

           

          This data type is used as a response element in the  DescribeDBInstances action.

          
          

          - **DBInstanceIdentifier** *(string) --* 

            Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

            
          

          - **DBInstanceClass** *(string) --* 

            Contains the name of the compute and memory capacity class of the DB instance.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB instance.

            
          

          - **DBInstanceStatus** *(string) --* 

            Specifies the current state of this database.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB instance.

            
          

          - **DBName** *(string) --* 

            The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

             

             **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

             

            Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

             

            Type: String

             

             **Oracle**  

             

            Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

            
          

          - **Endpoint** *(dict) --* 

            Specifies the connection endpoint.

            
            

            - **Address** *(string) --* 

              Specifies the DNS address of the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine is listening on.

              
            

            - **HostedZoneId** *(string) --* 

              Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

              
        
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size specified in gigabytes.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Provides the date and time the DB instance was created.

            
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **DBSecurityGroups** *(list) --* 

            Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               
              *  RestoreDBInstanceToPointInTime   
               

              
              

              - **DBSecurityGroupName** *(string) --* 

                The name of the DB security group.

                
              

              - **Status** *(string) --* 

                The status of the DB security group.

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides List of VPC security group elements that the DB instance belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **DBParameterGroups** *(list) --* 

            Provides the list of DB parameter groups applied to this DB instance.

            
            

            - *(dict) --* 

              The status of the DB parameter group.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateDBInstance   
               
              *  CreateDBInstanceReadReplica   
               
              *  DeleteDBInstance   
               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               

              
              

              - **DBParameterGroupName** *(string) --* 

                The name of the DP parameter group.

                
              

              - **ParameterApplyStatus** *(string) --* 

                The status of parameter updates.

                
          
        
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance is located in.

            
          

          - **DBSubnetGroup** *(dict) --* 

            Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **PendingModifiedValues** *(dict) --* 

            Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

            
            

            - **DBInstanceClass** *(string) --* 

              Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

              
            

            - **AllocatedStorage** *(integer) --* 

              Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

              
            

            - **MasterUserPassword** *(string) --* 

              Contains the pending or in-progress change of the master credentials for the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the pending port for the DB instance.

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the pending number of days for which automated backups are retained.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the DB instance.

               

              Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

              
            

            - **Iops** *(integer) --* 

              Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type to be associated with the DB instance.

              
            

            - **CACertificateIdentifier** *(string) --* 

              Specifies the identifier of the CA certificate for the DB instance.

              
            

            - **DBSubnetGroupName** *(string) --* 

              The new DB subnet group for the DB instance. 

              
        
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **MultiAZ** *(boolean) --* 

            Specifies if the DB instance is a Multi-AZ deployment.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **AutoMinorVersionUpgrade** *(boolean) --* 

            Indicates that minor version patches are applied automatically.

            
          

          - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

            Contains the identifier of the source DB instance if this DB instance is a Read Replica.

            
          

          - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB instance.

            
            

            - *(string) --* 
        
          

          - **LicenseModel** *(string) --* 

            License model information for this DB instance.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value.

            
          

          - **OptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB instance.

            
            

            - *(dict) --* 

              Provides information on the option groups the DB instance is a member of.

              
              

              - **OptionGroupName** *(string) --* 

                The name of the option group that the instance belongs to.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                
          
        
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this instance is associated with.

            
          

          - **SecondaryAvailabilityZone** *(string) --* 

            If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

            
          

          - **PubliclyAccessible** *(boolean) --* 

            Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

             

            Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

             

             
            * **Default VPC:** true 
             
            * **VPC:** false 
             

             

            If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

            
          

          - **StatusInfos** *(list) --* 

            The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

            
            

            - *(dict) --* 

              Provides a list of status information for a DB instance.

              
              

              - **StatusType** *(string) --* 

                This value is currently "read replication."

                
              

              - **Normal** *(boolean) --* 

                Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                
              

              - **Status** *(string) --* 

                Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                
              

              - **Message** *(string) --* 

                Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                
          
        
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB instance.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which the instance is associated for TDE encryption.

            
          

          - **DbInstancePort** *(integer) --* 

            Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

            
          

          - **DBClusterIdentifier** *(string) --* 

            If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB instance is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

            
          

          - **DbiResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

            
          

          - **CACertificateIdentifier** *(string) --* 

            The identifier of the CA certificate for this DB instance.

            
          

          - **DomainMemberships** *(list) --* 

            The Active Directory Domain membership records associated with the DB instance.

            
            

            - *(dict) --* 

              An Active Directory Domain membership record associated with the DB instance.

              
              

              - **Domain** *(string) --* 

                The identifier of the Active Directory Domain.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                
              

              - **FQDN** *(string) --* 

                The fully qualified domain name of the Active Directory Domain.

                
              

              - **IAMRoleName** *(string) --* 

                The name of the IAM role to be used when making API calls to the Directory Service.

                
          
        
          

          - **CopyTagsToSnapshot** *(boolean) --* 

            Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

            
          

          - **MonitoringInterval** *(integer) --* 

            The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

            
          

          - **EnhancedMonitoringResourceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

            
          

          - **MonitoringRoleArn** *(string) --* 

            The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

            
          

          - **PromotionTier** *(integer) --* 

            A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

            
          

          - **DBInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB instance.

            
      
    

  .. py:method:: restore_db_instance_to_point_in_time(**kwargs)

    

    Restores a DB instance to an arbitrary point in time. You can restore to any point in time before the time identified by the LatestRestorableTime property. You can restore to a point up to the number of days specified by the BackupRetentionPeriod property.

     

    The target database is created with most of the original configuration, but in a system-selected availability zone, with the default security group, the default subnet group, and the default DB parameter group. By default, the new DB instance is created as a single-AZ deployment except when the instance is a SQL Server instance that has an option group that is associated with mirroring; in this case, the instance becomes a mirrored deployment and not a single-AZ deployment.

    

    **Request Syntax** 
    ::

      response = client.restore_db_instance_to_point_in_time(
          SourceDBInstanceIdentifier='string',
          TargetDBInstanceIdentifier='string',
          RestoreTime=datetime(2015, 1, 1),
          UseLatestRestorableTime=True|False,
          DBInstanceClass='string',
          Port=123,
          AvailabilityZone='string',
          DBSubnetGroupName='string',
          MultiAZ=True|False,
          PubliclyAccessible=True|False,
          AutoMinorVersionUpgrade=True|False,
          LicenseModel='string',
          DBName='string',
          Engine='string',
          Iops=123,
          OptionGroupName='string',
          CopyTagsToSnapshot=True|False,
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          StorageType='string',
          TdeCredentialArn='string',
          TdeCredentialPassword='string',
          Domain='string',
          DomainIAMRoleName='string'
      )
    :type SourceDBInstanceIdentifier: string
    :param SourceDBInstanceIdentifier: **[REQUIRED]** 

      The identifier of the source DB instance from which to restore.

       

      Constraints:

       

       
      * Must be the identifier of an existing database instance 
       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type TargetDBInstanceIdentifier: string
    :param TargetDBInstanceIdentifier: **[REQUIRED]** 

      The name of the new database instance to be created.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type RestoreTime: datetime
    :param RestoreTime: 

      The date and time to restore from.

       

      Valid Values: Value must be a time in Universal Coordinated Time (UTC) format

       

      Constraints:

       

       
      * Must be before the latest restorable time for the DB instance 
       
      * Cannot be specified if UseLatestRestorableTime parameter is true 
       

       

      Example: ``2009-09-07T23:45:00Z``  

      

    
    :type UseLatestRestorableTime: boolean
    :param UseLatestRestorableTime: 

      Specifies whether (``true`` ) or not (``false`` ) the DB instance is restored from the latest backup time. 

       

      Default: ``false``  

       

      Constraints: Cannot be specified if RestoreTime parameter is provided.

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The compute and memory capacity of the Amazon RDS DB instance.

       

      Valid Values: ``db.t1.micro | db.m1.small | db.m1.medium | db.m1.large | db.m1.xlarge | db.m2.2xlarge | db.m2.4xlarge | db.m3.medium | db.m3.large | db.m3.xlarge | db.m3.2xlarge | db.m4.large | db.m4.xlarge | db.m4.2xlarge | db.m4.4xlarge | db.m4.10xlarge | db.r3.large | db.r3.xlarge | db.r3.2xlarge | db.r3.4xlarge | db.r3.8xlarge | db.t2.micro | db.t2.small | db.t2.medium | db.t2.large``  

       

      Default: The same DBInstanceClass as the original DB instance.

      

    
    :type Port: integer
    :param Port: 

      The port number on which the database accepts connections.

       

      Constraints: Value must be ``1150-65535``  

       

      Default: The same port as the original DB instance.

      

    
    :type AvailabilityZone: string
    :param AvailabilityZone: 

      The EC2 Availability Zone that the database instance will be created in.

       

      Default: A random, system-chosen Availability Zone.

       

      Constraint: You cannot specify the AvailabilityZone parameter if the MultiAZ parameter is set to true.

       

      Example: ``us-east-1a``  

      

    
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      The DB subnet group name to use for the new instance.

       

      Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

       

      Example: ``mySubnetgroup``  

      

    
    :type MultiAZ: boolean
    :param MultiAZ: 

      Specifies if the DB instance is a Multi-AZ deployment.

       

      Constraint: You cannot specify the AvailabilityZone parameter if the MultiAZ parameter is set to ``true`` .

      

    
    :type PubliclyAccessible: boolean
    :param PubliclyAccessible: 

      Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

       

      Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

       

       
      * **Default VPC:** true 
       
      * **VPC:** false 
       

       

      If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

      

    
    :type AutoMinorVersionUpgrade: boolean
    :param AutoMinorVersionUpgrade: 

      Indicates that minor version upgrades will be applied automatically to the DB instance during the maintenance window.

      

    
    :type LicenseModel: string
    :param LicenseModel: 

      License model information for the restored DB instance.

       

      Default: Same as source.

       

      Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

      

    
    :type DBName: string
    :param DBName: 

      The database name for the restored DB instance.

       

      .. note::

         

        This parameter is not used for the MySQL or MariaDB engines.

         

      

    
    :type Engine: string
    :param Engine: 

      The database engine to use for the new instance.

       

      Default: The same as source

       

      Constraint: Must be compatible with the engine of the source

       

      Valid Values: ``MySQL`` | ``mariadb`` | ``oracle-se1`` | ``oracle-se`` | ``oracle-ee`` | ``sqlserver-ee`` | ``sqlserver-se`` | ``sqlserver-ex`` | ``sqlserver-web`` | ``postgres`` | ``aurora``  

      

    
    :type Iops: integer
    :param Iops: 

      The amount of Provisioned IOPS (input/output operations per second) to be initially allocated for the DB instance.

       

      Constraints: Must be an integer greater than 1000.

       

       **SQL Server**  

       

      Setting the IOPS value for the SQL Server database engine is not supported.

      

    
    :type OptionGroupName: string
    :param OptionGroupName: 

      The name of the option group to be used for the restored DB instance.

       

      Permanent options, such as the TDE option for Oracle Advanced Security TDE, cannot be removed from an option group, and that option group cannot be removed from a DB instance once it is associated with a DB instance

      

    
    :type CopyTagsToSnapshot: boolean
    :param CopyTagsToSnapshot: 

      True to copy all tags from the restored DB instance to snapshots of the DB instance; otherwise false. The default is false.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags.

      

    
      - *(dict) --* 

        Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

        

      
        - **Key** *(string) --* 

          A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
        - **Value** *(string) --* 

          A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

          

        
      
  
    :type StorageType: string
    :param StorageType: 

      Specifies the storage type to be associated with the DB instance.

       

      Valid values: ``standard | gp2 | io1``  

       

      If you specify ``io1`` , you must also include a value for the ``Iops`` parameter. 

       

      Default: ``io1`` if the ``Iops`` parameter is specified; otherwise ``standard``  

      

    
    :type TdeCredentialArn: string
    :param TdeCredentialArn: 

      The ARN from the Key Store with which to associate the instance for TDE encryption.

      

    
    :type TdeCredentialPassword: string
    :param TdeCredentialPassword: 

      The password for the given ARN from the Key Store in order to access the device.

      

    
    :type Domain: string
    :param Domain: 

      Specify the Active Directory Domain to restore the instance in.

      

    
    :type DomainIAMRoleName: string
    :param DomainIAMRoleName: 

      Specify the name of the IAM role to be used when making API calls to the Directory Service.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBInstance': {
                'DBInstanceIdentifier': 'string',
                'DBInstanceClass': 'string',
                'Engine': 'string',
                'DBInstanceStatus': 'string',
                'MasterUsername': 'string',
                'DBName': 'string',
                'Endpoint': {
                    'Address': 'string',
                    'Port': 123,
                    'HostedZoneId': 'string'
                },
                'AllocatedStorage': 123,
                'InstanceCreateTime': datetime(2015, 1, 1),
                'PreferredBackupWindow': 'string',
                'BackupRetentionPeriod': 123,
                'DBSecurityGroups': [
                    {
                        'DBSecurityGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'VpcSecurityGroups': [
                    {
                        'VpcSecurityGroupId': 'string',
                        'Status': 'string'
                    },
                ],
                'DBParameterGroups': [
                    {
                        'DBParameterGroupName': 'string',
                        'ParameterApplyStatus': 'string'
                    },
                ],
                'AvailabilityZone': 'string',
                'DBSubnetGroup': {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
                'PreferredMaintenanceWindow': 'string',
                'PendingModifiedValues': {
                    'DBInstanceClass': 'string',
                    'AllocatedStorage': 123,
                    'MasterUserPassword': 'string',
                    'Port': 123,
                    'BackupRetentionPeriod': 123,
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'DBInstanceIdentifier': 'string',
                    'StorageType': 'string',
                    'CACertificateIdentifier': 'string',
                    'DBSubnetGroupName': 'string'
                },
                'LatestRestorableTime': datetime(2015, 1, 1),
                'MultiAZ': True|False,
                'EngineVersion': 'string',
                'AutoMinorVersionUpgrade': True|False,
                'ReadReplicaSourceDBInstanceIdentifier': 'string',
                'ReadReplicaDBInstanceIdentifiers': [
                    'string',
                ],
                'LicenseModel': 'string',
                'Iops': 123,
                'OptionGroupMemberships': [
                    {
                        'OptionGroupName': 'string',
                        'Status': 'string'
                    },
                ],
                'CharacterSetName': 'string',
                'SecondaryAvailabilityZone': 'string',
                'PubliclyAccessible': True|False,
                'StatusInfos': [
                    {
                        'StatusType': 'string',
                        'Normal': True|False,
                        'Status': 'string',
                        'Message': 'string'
                    },
                ],
                'StorageType': 'string',
                'TdeCredentialArn': 'string',
                'DbInstancePort': 123,
                'DBClusterIdentifier': 'string',
                'StorageEncrypted': True|False,
                'KmsKeyId': 'string',
                'DbiResourceId': 'string',
                'CACertificateIdentifier': 'string',
                'DomainMemberships': [
                    {
                        'Domain': 'string',
                        'Status': 'string',
                        'FQDN': 'string',
                        'IAMRoleName': 'string'
                    },
                ],
                'CopyTagsToSnapshot': True|False,
                'MonitoringInterval': 123,
                'EnhancedMonitoringResourceArn': 'string',
                'MonitoringRoleArn': 'string',
                'PromotionTier': 123,
                'DBInstanceArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBInstance** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  CreateDBInstance   
           
          *  DeleteDBInstance   
           
          *  ModifyDBInstance   
           

           

          This data type is used as a response element in the  DescribeDBInstances action.

          
          

          - **DBInstanceIdentifier** *(string) --* 

            Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

            
          

          - **DBInstanceClass** *(string) --* 

            Contains the name of the compute and memory capacity class of the DB instance.

            
          

          - **Engine** *(string) --* 

            Provides the name of the database engine to be used for this DB instance.

            
          

          - **DBInstanceStatus** *(string) --* 

            Specifies the current state of this database.

            
          

          - **MasterUsername** *(string) --* 

            Contains the master username for the DB instance.

            
          

          - **DBName** *(string) --* 

            The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

             

             **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

             

            Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

             

            Type: String

             

             **Oracle**  

             

            Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

            
          

          - **Endpoint** *(dict) --* 

            Specifies the connection endpoint.

            
            

            - **Address** *(string) --* 

              Specifies the DNS address of the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine is listening on.

              
            

            - **HostedZoneId** *(string) --* 

              Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

              
        
          

          - **AllocatedStorage** *(integer) --* 

            Specifies the allocated storage size specified in gigabytes.

            
          

          - **InstanceCreateTime** *(datetime) --* 

            Provides the date and time the DB instance was created.

            
          

          - **PreferredBackupWindow** *(string) --* 

            Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

            
          

          - **BackupRetentionPeriod** *(integer) --* 

            Specifies the number of days for which automatic DB snapshots are retained.

            
          

          - **DBSecurityGroups** *(list) --* 

            Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               
              *  RestoreDBInstanceToPointInTime   
               

              
              

              - **DBSecurityGroupName** *(string) --* 

                The name of the DB security group.

                
              

              - **Status** *(string) --* 

                The status of the DB security group.

                
          
        
          

          - **VpcSecurityGroups** *(list) --* 

            Provides List of VPC security group elements that the DB instance belongs to.

            
            

            - *(dict) --* 

              This data type is used as a response element for queries on VPC security group membership.

              
              

              - **VpcSecurityGroupId** *(string) --* 

                The name of the VPC security group.

                
              

              - **Status** *(string) --* 

                The status of the VPC security group.

                
          
        
          

          - **DBParameterGroups** *(list) --* 

            Provides the list of DB parameter groups applied to this DB instance.

            
            

            - *(dict) --* 

              The status of the DB parameter group.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateDBInstance   
               
              *  CreateDBInstanceReadReplica   
               
              *  DeleteDBInstance   
               
              *  ModifyDBInstance   
               
              *  RebootDBInstance   
               
              *  RestoreDBInstanceFromDBSnapshot   
               

              
              

              - **DBParameterGroupName** *(string) --* 

                The name of the DP parameter group.

                
              

              - **ParameterApplyStatus** *(string) --* 

                The status of parameter updates.

                
          
        
          

          - **AvailabilityZone** *(string) --* 

            Specifies the name of the Availability Zone the DB instance is located in.

            
          

          - **DBSubnetGroup** *(dict) --* 

            Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
          

          - **PreferredMaintenanceWindow** *(string) --* 

            Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

            
          

          - **PendingModifiedValues** *(dict) --* 

            Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

            
            

            - **DBInstanceClass** *(string) --* 

              Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

              
            

            - **AllocatedStorage** *(integer) --* 

              Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

              
            

            - **MasterUserPassword** *(string) --* 

              Contains the pending or in-progress change of the master credentials for the DB instance.

              
            

            - **Port** *(integer) --* 

              Specifies the pending port for the DB instance.

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the pending number of days for which automated backups are retained.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the DB instance.

               

              Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

              
            

            - **Iops** *(integer) --* 

              Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type to be associated with the DB instance.

              
            

            - **CACertificateIdentifier** *(string) --* 

              Specifies the identifier of the CA certificate for the DB instance.

              
            

            - **DBSubnetGroupName** *(string) --* 

              The new DB subnet group for the DB instance. 

              
        
          

          - **LatestRestorableTime** *(datetime) --* 

            Specifies the latest time to which a database can be restored with point-in-time restore.

            
          

          - **MultiAZ** *(boolean) --* 

            Specifies if the DB instance is a Multi-AZ deployment.

            
          

          - **EngineVersion** *(string) --* 

            Indicates the database engine version.

            
          

          - **AutoMinorVersionUpgrade** *(boolean) --* 

            Indicates that minor version patches are applied automatically.

            
          

          - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

            Contains the identifier of the source DB instance if this DB instance is a Read Replica.

            
          

          - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

            Contains one or more identifiers of the Read Replicas associated with this DB instance.

            
            

            - *(string) --* 
        
          

          - **LicenseModel** *(string) --* 

            License model information for this DB instance.

            
          

          - **Iops** *(integer) --* 

            Specifies the Provisioned IOPS (I/O operations per second) value.

            
          

          - **OptionGroupMemberships** *(list) --* 

            Provides the list of option group memberships for this DB instance.

            
            

            - *(dict) --* 

              Provides information on the option groups the DB instance is a member of.

              
              

              - **OptionGroupName** *(string) --* 

                The name of the option group that the instance belongs to.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                
          
        
          

          - **CharacterSetName** *(string) --* 

            If present, specifies the name of the character set that this instance is associated with.

            
          

          - **SecondaryAvailabilityZone** *(string) --* 

            If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

            
          

          - **PubliclyAccessible** *(boolean) --* 

            Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

             

            Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

             

             
            * **Default VPC:** true 
             
            * **VPC:** false 
             

             

            If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

            
          

          - **StatusInfos** *(list) --* 

            The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

            
            

            - *(dict) --* 

              Provides a list of status information for a DB instance.

              
              

              - **StatusType** *(string) --* 

                This value is currently "read replication."

                
              

              - **Normal** *(boolean) --* 

                Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                
              

              - **Status** *(string) --* 

                Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                
              

              - **Message** *(string) --* 

                Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                
          
        
          

          - **StorageType** *(string) --* 

            Specifies the storage type associated with DB instance.

            
          

          - **TdeCredentialArn** *(string) --* 

            The ARN from the Key Store with which the instance is associated for TDE encryption.

            
          

          - **DbInstancePort** *(integer) --* 

            Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

            
          

          - **DBClusterIdentifier** *(string) --* 

            If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

            
          

          - **StorageEncrypted** *(boolean) --* 

            Specifies whether the DB instance is encrypted.

            
          

          - **KmsKeyId** *(string) --* 

            If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

            
          

          - **DbiResourceId** *(string) --* 

            The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

            
          

          - **CACertificateIdentifier** *(string) --* 

            The identifier of the CA certificate for this DB instance.

            
          

          - **DomainMemberships** *(list) --* 

            The Active Directory Domain membership records associated with the DB instance.

            
            

            - *(dict) --* 

              An Active Directory Domain membership record associated with the DB instance.

              
              

              - **Domain** *(string) --* 

                The identifier of the Active Directory Domain.

                
              

              - **Status** *(string) --* 

                The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                
              

              - **FQDN** *(string) --* 

                The fully qualified domain name of the Active Directory Domain.

                
              

              - **IAMRoleName** *(string) --* 

                The name of the IAM role to be used when making API calls to the Directory Service.

                
          
        
          

          - **CopyTagsToSnapshot** *(boolean) --* 

            Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

            
          

          - **MonitoringInterval** *(integer) --* 

            The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

            
          

          - **EnhancedMonitoringResourceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

            
          

          - **MonitoringRoleArn** *(string) --* 

            The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

            
          

          - **PromotionTier** *(integer) --* 

            A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

            
          

          - **DBInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB instance.

            
      
    

  .. py:method:: revoke_db_security_group_ingress(**kwargs)

    

    Revokes ingress from a DBSecurityGroup for previously authorized IP ranges or EC2 or VPC Security Groups. Required parameters for this API are one of CIDRIP, EC2SecurityGroupId for VPC, or (EC2SecurityGroupOwnerId and either EC2SecurityGroupName or EC2SecurityGroupId).

    

    **Request Syntax** 
    ::

      response = client.revoke_db_security_group_ingress(
          DBSecurityGroupName='string',
          CIDRIP='string',
          EC2SecurityGroupName='string',
          EC2SecurityGroupId='string',
          EC2SecurityGroupOwnerId='string'
      )
    :type DBSecurityGroupName: string
    :param DBSecurityGroupName: **[REQUIRED]** 

      The name of the DB security group to revoke ingress from.

      

    
    :type CIDRIP: string
    :param CIDRIP: 

      The IP range to revoke access from. Must be a valid CIDR range. If ``CIDRIP`` is specified, ``EC2SecurityGroupName`` , ``EC2SecurityGroupId`` and ``EC2SecurityGroupOwnerId`` cannot be provided. 

      

    
    :type EC2SecurityGroupName: string
    :param EC2SecurityGroupName: 

      The name of the EC2 security group to revoke access from. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, EC2SecurityGroupOwnerId and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

      

    
    :type EC2SecurityGroupId: string
    :param EC2SecurityGroupId: 

      The id of the EC2 security group to revoke access from. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, EC2SecurityGroupOwnerId and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

      

    
    :type EC2SecurityGroupOwnerId: string
    :param EC2SecurityGroupOwnerId: 

      The AWS Account Number of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` parameter. The AWS Access Key ID is not an acceptable value. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, EC2SecurityGroupOwnerId and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DBSecurityGroup': {
                'OwnerId': 'string',
                'DBSecurityGroupName': 'string',
                'DBSecurityGroupDescription': 'string',
                'VpcId': 'string',
                'EC2SecurityGroups': [
                    {
                        'Status': 'string',
                        'EC2SecurityGroupName': 'string',
                        'EC2SecurityGroupId': 'string',
                        'EC2SecurityGroupOwnerId': 'string'
                    },
                ],
                'IPRanges': [
                    {
                        'Status': 'string',
                        'CIDRIP': 'string'
                    },
                ],
                'DBSecurityGroupArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **DBSecurityGroup** *(dict) --* 

          Contains the result of a successful invocation of the following actions:

           

           
          *  DescribeDBSecurityGroups   
           
          *  AuthorizeDBSecurityGroupIngress   
           
          *  CreateDBSecurityGroup   
           
          *  RevokeDBSecurityGroupIngress   
           

           

          This data type is used as a response element in the  DescribeDBSecurityGroups action.

          
          

          - **OwnerId** *(string) --* 

            Provides the AWS ID of the owner of a specific DB security group.

            
          

          - **DBSecurityGroupName** *(string) --* 

            Specifies the name of the DB security group.

            
          

          - **DBSecurityGroupDescription** *(string) --* 

            Provides the description of the DB security group.

            
          

          - **VpcId** *(string) --* 

            Provides the VpcId of the DB security group.

            
          

          - **EC2SecurityGroups** *(list) --* 

            Contains a list of  EC2SecurityGroup elements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the following actions:

               

               
              *  AuthorizeDBSecurityGroupIngress   
               
              *  DescribeDBSecurityGroups   
               
              *  RevokeDBSecurityGroupIngress   
               

              
              

              - **Status** *(string) --* 

                Provides the status of the EC2 security group. Status can be "authorizing", "authorized", "revoking", and "revoked".

                
              

              - **EC2SecurityGroupName** *(string) --* 

                Specifies the name of the EC2 security group.

                
              

              - **EC2SecurityGroupId** *(string) --* 

                Specifies the id of the EC2 security group.

                
              

              - **EC2SecurityGroupOwnerId** *(string) --* 

                Specifies the AWS ID of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` field. 

                
          
        
          

          - **IPRanges** *(list) --* 

            Contains a list of  IPRange elements. 

            
            

            - *(dict) --* 

              This data type is used as a response element in the  DescribeDBSecurityGroups action. 

              
              

              - **Status** *(string) --* 

                Specifies the status of the IP range. Status can be "authorizing", "authorized", "revoking", and "revoked".

                
              

              - **CIDRIP** *(string) --* 

                Specifies the IP range.

                
          
        
          

          - **DBSecurityGroupArn** *(string) --* 

            The Amazon Resource Name (ARN) for the DB security group.

            
      
    

==========
Paginators
==========


The available paginators are:

* :py:class:`RDS.Paginator.DescribeDBClusterSnapshots`


* :py:class:`RDS.Paginator.DescribeDBEngineVersions`


* :py:class:`RDS.Paginator.DescribeDBInstances`


* :py:class:`RDS.Paginator.DescribeDBLogFiles`


* :py:class:`RDS.Paginator.DescribeDBParameterGroups`


* :py:class:`RDS.Paginator.DescribeDBParameters`


* :py:class:`RDS.Paginator.DescribeDBSecurityGroups`


* :py:class:`RDS.Paginator.DescribeDBSnapshots`


* :py:class:`RDS.Paginator.DescribeDBSubnetGroups`


* :py:class:`RDS.Paginator.DescribeEngineDefaultParameters`


* :py:class:`RDS.Paginator.DescribeEventSubscriptions`


* :py:class:`RDS.Paginator.DescribeEvents`


* :py:class:`RDS.Paginator.DescribeOptionGroupOptions`


* :py:class:`RDS.Paginator.DescribeOptionGroups`


* :py:class:`RDS.Paginator.DescribeOrderableDBInstanceOptions`


* :py:class:`RDS.Paginator.DescribeReservedDBInstances`


* :py:class:`RDS.Paginator.DescribeReservedDBInstancesOfferings`


* :py:class:`RDS.Paginator.DownloadDBLogFilePortion`



.. py:class:: RDS.Paginator.DescribeDBClusterSnapshots

  ::

    
    paginator = client.get_paginator('describe_db_cluster_snapshots')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_db_cluster_snapshots`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBClusterIdentifier='string',
          DBClusterSnapshotIdentifier='string',
          SnapshotType='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          IncludeShared=True|False,
          IncludePublic=True|False,
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type DBClusterIdentifier: string
    :param DBClusterIdentifier: 

      The ID of the DB cluster to retrieve the list of DB cluster snapshots for. This parameter cannot be used in conjunction with the ``DBClusterSnapshotIdentifier`` parameter. This parameter is not case-sensitive. 

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type DBClusterSnapshotIdentifier: string
    :param DBClusterSnapshotIdentifier: 

      A specific DB cluster snapshot identifier to describe. This parameter cannot be used in conjunction with the ``DBClusterIdentifier`` parameter. This value is stored as a lowercase string. 

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       
      * If this identifier is for an automated snapshot, the ``SnapshotType`` parameter must also be specified. 
       

      

    
    :type SnapshotType: string
    :param SnapshotType: 

      The type of DB cluster snapshots to be returned. You can specify one of the following values:

       

       
      * ``automated`` - Return all DB cluster snapshots that have been automatically taken by Amazon RDS for my AWS account. 
       
      * ``manual`` - Return all DB cluster snapshots that have been taken by my AWS account. 
       
      * ``shared`` - Return all manual DB cluster snapshots that have been shared to my AWS account. 
       
      * ``public`` - Return all DB cluster snapshots that have been marked as public. 
       

       

      If you don't specify a ``SnapshotType`` value, then both automated and manual DB cluster snapshots are returned. You can include shared DB cluster snapshots with these results by setting the ``IncludeShared`` parameter to ``true`` . You can include public DB cluster snapshots with these results by setting the ``IncludePublic`` parameter to ``true`` .

       

      The ``IncludeShared`` and ``IncludePublic`` parameters don't apply for ``SnapshotType`` values of ``manual`` or ``automated`` . The ``IncludePublic`` parameter doesn't apply when ``SnapshotType`` is set to ``shared`` . The ``IncludeShared`` parameter doesn't apply when ``SnapshotType`` is set to ``public`` .

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type IncludeShared: boolean
    :param IncludeShared: 

      Set this value to ``true`` to include shared manual DB cluster snapshots from other AWS accounts that this AWS account has been given permission to copy or restore, otherwise set this value to ``false`` . The default is ``false`` .

       

      You can give an AWS account permission to restore a manual DB cluster snapshot from another AWS account by the  ModifyDBClusterSnapshotAttribute API action.

      

    
    :type IncludePublic: boolean
    :param IncludePublic: 

      Set this value to ``true`` to include manual DB cluster snapshots that are public and can be copied or restored by any AWS account, otherwise set this value to ``false`` . The default is ``false`` . The default is false.

       

      You can share a manual DB cluster snapshot as public by using the  ModifyDBClusterSnapshotAttribute API action.

      

    
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
            'DBClusterSnapshots': [
                {
                    'AvailabilityZones': [
                        'string',
                    ],
                    'DBClusterSnapshotIdentifier': 'string',
                    'DBClusterIdentifier': 'string',
                    'SnapshotCreateTime': datetime(2015, 1, 1),
                    'Engine': 'string',
                    'AllocatedStorage': 123,
                    'Status': 'string',
                    'Port': 123,
                    'VpcId': 'string',
                    'ClusterCreateTime': datetime(2015, 1, 1),
                    'MasterUsername': 'string',
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'SnapshotType': 'string',
                    'PercentProgress': 123,
                    'StorageEncrypted': True|False,
                    'KmsKeyId': 'string',
                    'DBClusterSnapshotArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Provides a list of DB cluster snapshots for the user as the result of a call to the  DescribeDBClusterSnapshots action. 

        
        

        - **DBClusterSnapshots** *(list) --* 

          Provides a list of DB cluster snapshots for the user.

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  CreateDBClusterSnapshot   
             
            *  DeleteDBClusterSnapshot   
             

             

            This data type is used as a response element in the  DescribeDBClusterSnapshots action.

            
            

            - **AvailabilityZones** *(list) --* 

              Provides the list of EC2 Availability Zones that instances in the DB cluster snapshot can be restored in.

              
              

              - *(string) --* 
          
            

            - **DBClusterSnapshotIdentifier** *(string) --* 

              Specifies the identifier for the DB cluster snapshot.

              
            

            - **DBClusterIdentifier** *(string) --* 

              Specifies the DB cluster identifier of the DB cluster that this DB cluster snapshot was created from.

              
            

            - **SnapshotCreateTime** *(datetime) --* 

              Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

              
            

            - **Engine** *(string) --* 

              Specifies the name of the database engine.

              
            

            - **AllocatedStorage** *(integer) --* 

              Specifies the allocated storage size in gigabytes (GB).

              
            

            - **Status** *(string) --* 

              Specifies the status of this DB cluster snapshot.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the DB cluster was listening on at the time of the snapshot.

              
            

            - **VpcId** *(string) --* 

              Provides the VPC ID associated with the DB cluster snapshot.

              
            

            - **ClusterCreateTime** *(datetime) --* 

              Specifies the time when the DB cluster was created, in Universal Coordinated Time (UTC).

              
            

            - **MasterUsername** *(string) --* 

              Provides the master username for the DB cluster snapshot.

              
            

            - **EngineVersion** *(string) --* 

              Provides the version of the database engine for this DB cluster snapshot.

              
            

            - **LicenseModel** *(string) --* 

              Provides the license model information for this DB cluster snapshot.

              
            

            - **SnapshotType** *(string) --* 

              Provides the type of the DB cluster snapshot.

              
            

            - **PercentProgress** *(integer) --* 

              Specifies the percentage of the estimated data that has been transferred.

              
            

            - **StorageEncrypted** *(boolean) --* 

              Specifies whether the DB cluster snapshot is encrypted.

              
            

            - **KmsKeyId** *(string) --* 

              If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster snapshot.

              
            

            - **DBClusterSnapshotArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB cluster snapshot.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeDBEngineVersions

  ::

    
    paginator = client.get_paginator('describe_db_engine_versions')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_db_engine_versions`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          Engine='string',
          EngineVersion='string',
          DBParameterGroupFamily='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          DefaultOnly=True|False,
          ListSupportedCharacterSets=True|False,
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type Engine: string
    :param Engine: 

      The database engine to return.

      

    
    :type EngineVersion: string
    :param EngineVersion: 

      The database engine version to return.

       

      Example: ``5.1.49``  

      

    
    :type DBParameterGroupFamily: string
    :param DBParameterGroupFamily: 

      The name of a specific DB parameter group family to return details for.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      Not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type DefaultOnly: boolean
    :param DefaultOnly: 

      Indicates that only the default version of the specified engine or engine and major version combination is returned.

      

    
    :type ListSupportedCharacterSets: boolean
    :param ListSupportedCharacterSets: 

      If this parameter is specified, and if the requested engine supports the CharacterSetName parameter for CreateDBInstance, the response includes a list of supported character sets for each engine version.

      

    
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
            'DBEngineVersions': [
                {
                    'Engine': 'string',
                    'EngineVersion': 'string',
                    'DBParameterGroupFamily': 'string',
                    'DBEngineDescription': 'string',
                    'DBEngineVersionDescription': 'string',
                    'DefaultCharacterSet': {
                        'CharacterSetName': 'string',
                        'CharacterSetDescription': 'string'
                    },
                    'SupportedCharacterSets': [
                        {
                            'CharacterSetName': 'string',
                            'CharacterSetDescription': 'string'
                        },
                    ],
                    'ValidUpgradeTarget': [
                        {
                            'Engine': 'string',
                            'EngineVersion': 'string',
                            'Description': 'string',
                            'AutoUpgrade': True|False,
                            'IsMajorVersionUpgrade': True|False
                        },
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBEngineVersions action. 

        
        

        - **DBEngineVersions** *(list) --* 

          A list of ``DBEngineVersion`` elements. 

          
          

          - *(dict) --* 

            This data type is used as a response element in the action  DescribeDBEngineVersions . 

            
            

            - **Engine** *(string) --* 

              The name of the database engine.

              
            

            - **EngineVersion** *(string) --* 

              The version number of the database engine.

              
            

            - **DBParameterGroupFamily** *(string) --* 

              The name of the DB parameter group family for the database engine.

              
            

            - **DBEngineDescription** *(string) --* 

              The description of the database engine.

              
            

            - **DBEngineVersionDescription** *(string) --* 

              The description of the database engine version.

              
            

            - **DefaultCharacterSet** *(dict) --* 

              The default character set for new instances of this engine version, if the ``CharacterSetName`` parameter of the CreateDBInstance API is not specified. 

              
              

              - **CharacterSetName** *(string) --* 

                The name of the character set.

                
              

              - **CharacterSetDescription** *(string) --* 

                The description of the character set.

                
          
            

            - **SupportedCharacterSets** *(list) --* 

              A list of the character sets supported by this engine for the ``CharacterSetName`` parameter of the CreateDBInstance API. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the action  DescribeDBEngineVersions . 

                
                

                - **CharacterSetName** *(string) --* 

                  The name of the character set.

                  
                

                - **CharacterSetDescription** *(string) --* 

                  The description of the character set.

                  
            
          
            

            - **ValidUpgradeTarget** *(list) --* 

              A list of engine versions that this database engine version can be upgraded to.

              
              

              - *(dict) --* 

                The version of the database engine that a DB instance can be upgraded to.

                
                

                - **Engine** *(string) --* 

                  The name of the upgrade target database engine.

                  
                

                - **EngineVersion** *(string) --* 

                  The version number of the upgrade target database engine.

                  
                

                - **Description** *(string) --* 

                  The version of the database engine that a DB instance can be upgraded to.

                  
                

                - **AutoUpgrade** *(boolean) --* 

                  A value that indicates whether the target version will be applied to any source DB instances that have AutoMinorVersionUpgrade set to true.

                  
                

                - **IsMajorVersionUpgrade** *(boolean) --* 

                  A value that indicates whether a database engine will be upgraded to a major version.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeDBInstances

  ::

    
    paginator = client.get_paginator('describe_db_instances')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_db_instances`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBInstanceIdentifier='string',
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
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: 

      The user-supplied instance identifier. If this parameter is specified, information from only the specific DB instance is returned. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'DBInstances': [
                {
                    'DBInstanceIdentifier': 'string',
                    'DBInstanceClass': 'string',
                    'Engine': 'string',
                    'DBInstanceStatus': 'string',
                    'MasterUsername': 'string',
                    'DBName': 'string',
                    'Endpoint': {
                        'Address': 'string',
                        'Port': 123,
                        'HostedZoneId': 'string'
                    },
                    'AllocatedStorage': 123,
                    'InstanceCreateTime': datetime(2015, 1, 1),
                    'PreferredBackupWindow': 'string',
                    'BackupRetentionPeriod': 123,
                    'DBSecurityGroups': [
                        {
                            'DBSecurityGroupName': 'string',
                            'Status': 'string'
                        },
                    ],
                    'VpcSecurityGroups': [
                        {
                            'VpcSecurityGroupId': 'string',
                            'Status': 'string'
                        },
                    ],
                    'DBParameterGroups': [
                        {
                            'DBParameterGroupName': 'string',
                            'ParameterApplyStatus': 'string'
                        },
                    ],
                    'AvailabilityZone': 'string',
                    'DBSubnetGroup': {
                        'DBSubnetGroupName': 'string',
                        'DBSubnetGroupDescription': 'string',
                        'VpcId': 'string',
                        'SubnetGroupStatus': 'string',
                        'Subnets': [
                            {
                                'SubnetIdentifier': 'string',
                                'SubnetAvailabilityZone': {
                                    'Name': 'string'
                                },
                                'SubnetStatus': 'string'
                            },
                        ],
                        'DBSubnetGroupArn': 'string'
                    },
                    'PreferredMaintenanceWindow': 'string',
                    'PendingModifiedValues': {
                        'DBInstanceClass': 'string',
                        'AllocatedStorage': 123,
                        'MasterUserPassword': 'string',
                        'Port': 123,
                        'BackupRetentionPeriod': 123,
                        'MultiAZ': True|False,
                        'EngineVersion': 'string',
                        'LicenseModel': 'string',
                        'Iops': 123,
                        'DBInstanceIdentifier': 'string',
                        'StorageType': 'string',
                        'CACertificateIdentifier': 'string',
                        'DBSubnetGroupName': 'string'
                    },
                    'LatestRestorableTime': datetime(2015, 1, 1),
                    'MultiAZ': True|False,
                    'EngineVersion': 'string',
                    'AutoMinorVersionUpgrade': True|False,
                    'ReadReplicaSourceDBInstanceIdentifier': 'string',
                    'ReadReplicaDBInstanceIdentifiers': [
                        'string',
                    ],
                    'LicenseModel': 'string',
                    'Iops': 123,
                    'OptionGroupMemberships': [
                        {
                            'OptionGroupName': 'string',
                            'Status': 'string'
                        },
                    ],
                    'CharacterSetName': 'string',
                    'SecondaryAvailabilityZone': 'string',
                    'PubliclyAccessible': True|False,
                    'StatusInfos': [
                        {
                            'StatusType': 'string',
                            'Normal': True|False,
                            'Status': 'string',
                            'Message': 'string'
                        },
                    ],
                    'StorageType': 'string',
                    'TdeCredentialArn': 'string',
                    'DbInstancePort': 123,
                    'DBClusterIdentifier': 'string',
                    'StorageEncrypted': True|False,
                    'KmsKeyId': 'string',
                    'DbiResourceId': 'string',
                    'CACertificateIdentifier': 'string',
                    'DomainMemberships': [
                        {
                            'Domain': 'string',
                            'Status': 'string',
                            'FQDN': 'string',
                            'IAMRoleName': 'string'
                        },
                    ],
                    'CopyTagsToSnapshot': True|False,
                    'MonitoringInterval': 123,
                    'EnhancedMonitoringResourceArn': 'string',
                    'MonitoringRoleArn': 'string',
                    'PromotionTier': 123,
                    'DBInstanceArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBInstances action. 

        
        

        - **DBInstances** *(list) --* 

          A list of  DBInstance instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  CreateDBInstance   
             
            *  DeleteDBInstance   
             
            *  ModifyDBInstance   
             

             

            This data type is used as a response element in the  DescribeDBInstances action.

            
            

            - **DBInstanceIdentifier** *(string) --* 

              Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance.

              
            

            - **DBInstanceClass** *(string) --* 

              Contains the name of the compute and memory capacity class of the DB instance.

              
            

            - **Engine** *(string) --* 

              Provides the name of the database engine to be used for this DB instance.

              
            

            - **DBInstanceStatus** *(string) --* 

              Specifies the current state of this database.

              
            

            - **MasterUsername** *(string) --* 

              Contains the master username for the DB instance.

              
            

            - **DBName** *(string) --* 

              The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from CreateDBInstanceReadReplica since Read Replicas are only supported for these engines.

               

               **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

               

              Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance.

               

              Type: String

               

               **Oracle**  

               

              Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance.

              
            

            - **Endpoint** *(dict) --* 

              Specifies the connection endpoint.

              
              

              - **Address** *(string) --* 

                Specifies the DNS address of the DB instance.

                
              

              - **Port** *(integer) --* 

                Specifies the port that the database engine is listening on.

                
              

              - **HostedZoneId** *(string) --* 

                Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

                
          
            

            - **AllocatedStorage** *(integer) --* 

              Specifies the allocated storage size specified in gigabytes.

              
            

            - **InstanceCreateTime** *(datetime) --* 

              Provides the date and time the DB instance was created.

              
            

            - **PreferredBackupWindow** *(string) --* 

              Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

              
            

            - **BackupRetentionPeriod** *(integer) --* 

              Specifies the number of days for which automatic DB snapshots are retained.

              
            

            - **DBSecurityGroups** *(list) --* 

              Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the following actions:

                 

                 
                *  ModifyDBInstance   
                 
                *  RebootDBInstance   
                 
                *  RestoreDBInstanceFromDBSnapshot   
                 
                *  RestoreDBInstanceToPointInTime   
                 

                
                

                - **DBSecurityGroupName** *(string) --* 

                  The name of the DB security group.

                  
                

                - **Status** *(string) --* 

                  The status of the DB security group.

                  
            
          
            

            - **VpcSecurityGroups** *(list) --* 

              Provides List of VPC security group elements that the DB instance belongs to.

              
              

              - *(dict) --* 

                This data type is used as a response element for queries on VPC security group membership.

                
                

                - **VpcSecurityGroupId** *(string) --* 

                  The name of the VPC security group.

                  
                

                - **Status** *(string) --* 

                  The status of the VPC security group.

                  
            
          
            

            - **DBParameterGroups** *(list) --* 

              Provides the list of DB parameter groups applied to this DB instance.

              
              

              - *(dict) --* 

                The status of the DB parameter group.

                 

                This data type is used as a response element in the following actions:

                 

                 
                *  CreateDBInstance   
                 
                *  CreateDBInstanceReadReplica   
                 
                *  DeleteDBInstance   
                 
                *  ModifyDBInstance   
                 
                *  RebootDBInstance   
                 
                *  RestoreDBInstanceFromDBSnapshot   
                 

                
                

                - **DBParameterGroupName** *(string) --* 

                  The name of the DP parameter group.

                  
                

                - **ParameterApplyStatus** *(string) --* 

                  The status of parameter updates.

                  
            
          
            

            - **AvailabilityZone** *(string) --* 

              Specifies the name of the Availability Zone the DB instance is located in.

              
            

            - **DBSubnetGroup** *(dict) --* 

              Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group.

              
              

              - **DBSubnetGroupName** *(string) --* 

                The name of the DB subnet group.

                
              

              - **DBSubnetGroupDescription** *(string) --* 

                Provides the description of the DB subnet group.

                
              

              - **VpcId** *(string) --* 

                Provides the VpcId of the DB subnet group.

                
              

              - **SubnetGroupStatus** *(string) --* 

                Provides the status of the DB subnet group.

                
              

              - **Subnets** *(list) --* 

                Contains a list of  Subnet elements. 

                
                

                - *(dict) --* 

                  This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                  
                  

                  - **SubnetIdentifier** *(string) --* 

                    Specifies the identifier of the subnet.

                    
                  

                  - **SubnetAvailabilityZone** *(dict) --* 

                    Contains Availability Zone information.

                     

                    This data type is used as an element in the following data type:

                     

                     
                    *  OrderableDBInstanceOption   
                     

                    
                    

                    - **Name** *(string) --* 

                      The name of the availability zone.

                      
                
                  

                  - **SubnetStatus** *(string) --* 

                    Specifies the status of the subnet.

                    
              
            
              

              - **DBSubnetGroupArn** *(string) --* 

                The Amazon Resource Name (ARN) for the DB subnet group.

                
          
            

            - **PreferredMaintenanceWindow** *(string) --* 

              Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

              
            

            - **PendingModifiedValues** *(dict) --* 

              Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements.

              
              

              - **DBInstanceClass** *(string) --* 

                Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

                
              

              - **AllocatedStorage** *(integer) --* 

                Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

                
              

              - **MasterUserPassword** *(string) --* 

                Contains the pending or in-progress change of the master credentials for the DB instance.

                
              

              - **Port** *(integer) --* 

                Specifies the pending port for the DB instance.

                
              

              - **BackupRetentionPeriod** *(integer) --* 

                Specifies the pending number of days for which automated backups are retained.

                
              

              - **MultiAZ** *(boolean) --* 

                Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment.

                
              

              - **EngineVersion** *(string) --* 

                Indicates the database engine version.

                
              

              - **LicenseModel** *(string) --* 

                The license model for the DB instance.

                 

                Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

                
              

              - **Iops** *(integer) --* 

                Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

                
              

              - **DBInstanceIdentifier** *(string) --* 

                Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

                
              

              - **StorageType** *(string) --* 

                Specifies the storage type to be associated with the DB instance.

                
              

              - **CACertificateIdentifier** *(string) --* 

                Specifies the identifier of the CA certificate for the DB instance.

                
              

              - **DBSubnetGroupName** *(string) --* 

                The new DB subnet group for the DB instance. 

                
          
            

            - **LatestRestorableTime** *(datetime) --* 

              Specifies the latest time to which a database can be restored with point-in-time restore.

              
            

            - **MultiAZ** *(boolean) --* 

              Specifies if the DB instance is a Multi-AZ deployment.

              
            

            - **EngineVersion** *(string) --* 

              Indicates the database engine version.

              
            

            - **AutoMinorVersionUpgrade** *(boolean) --* 

              Indicates that minor version patches are applied automatically.

              
            

            - **ReadReplicaSourceDBInstanceIdentifier** *(string) --* 

              Contains the identifier of the source DB instance if this DB instance is a Read Replica.

              
            

            - **ReadReplicaDBInstanceIdentifiers** *(list) --* 

              Contains one or more identifiers of the Read Replicas associated with this DB instance.

              
              

              - *(string) --* 
          
            

            - **LicenseModel** *(string) --* 

              License model information for this DB instance.

              
            

            - **Iops** *(integer) --* 

              Specifies the Provisioned IOPS (I/O operations per second) value.

              
            

            - **OptionGroupMemberships** *(list) --* 

              Provides the list of option group memberships for this DB instance.

              
              

              - *(dict) --* 

                Provides information on the option groups the DB instance is a member of.

                
                

                - **OptionGroupName** *(string) --* 

                  The name of the option group that the instance belongs to.

                  
                

                - **Status** *(string) --* 

                  The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

                  
            
          
            

            - **CharacterSetName** *(string) --* 

              If present, specifies the name of the character set that this instance is associated with.

              
            

            - **SecondaryAvailabilityZone** *(string) --* 

              If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support.

              
            

            - **PubliclyAccessible** *(boolean) --* 

              Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

               

              Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

               

               
              * **Default VPC:** true 
               
              * **VPC:** false 
               

               

              If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

              
            

            - **StatusInfos** *(list) --* 

              The status of a Read Replica. If the instance is not a Read Replica, this will be blank.

              
              

              - *(dict) --* 

                Provides a list of status information for a DB instance.

                
                

                - **StatusType** *(string) --* 

                  This value is currently "read replication."

                  
                

                - **Normal** *(boolean) --* 

                  Boolean value that is true if the instance is operating normally, or false if the instance is in an error state.

                  
                

                - **Status** *(string) --* 

                  Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated.

                  
                

                - **Message** *(string) --* 

                  Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank.

                  
            
          
            

            - **StorageType** *(string) --* 

              Specifies the storage type associated with DB instance.

              
            

            - **TdeCredentialArn** *(string) --* 

              The ARN from the Key Store with which the instance is associated for TDE encryption.

              
            

            - **DbInstancePort** *(integer) --* 

              Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port.

              
            

            - **DBClusterIdentifier** *(string) --* 

              If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

              
            

            - **StorageEncrypted** *(boolean) --* 

              Specifies whether the DB instance is encrypted.

              
            

            - **KmsKeyId** *(string) --* 

              If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

              
            

            - **DbiResourceId** *(string) --* 

              The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed.

              
            

            - **CACertificateIdentifier** *(string) --* 

              The identifier of the CA certificate for this DB instance.

              
            

            - **DomainMemberships** *(list) --* 

              The Active Directory Domain membership records associated with the DB instance.

              
              

              - *(dict) --* 

                An Active Directory Domain membership record associated with the DB instance.

                
                

                - **Domain** *(string) --* 

                  The identifier of the Active Directory Domain.

                  
                

                - **Status** *(string) --* 

                  The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

                  
                

                - **FQDN** *(string) --* 

                  The fully qualified domain name of the Active Directory Domain.

                  
                

                - **IAMRoleName** *(string) --* 

                  The name of the IAM role to be used when making API calls to the Directory Service.

                  
            
          
            

            - **CopyTagsToSnapshot** *(boolean) --* 

              Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

              
            

            - **MonitoringInterval** *(integer) --* 

              The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

              
            

            - **EnhancedMonitoringResourceArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

              
            

            - **MonitoringRoleArn** *(string) --* 

              The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

              
            

            - **PromotionTier** *(integer) --* 

              A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster`_ . 

              
            

            - **DBInstanceArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB instance.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeDBLogFiles

  ::

    
    paginator = client.get_paginator('describe_db_log_files')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_db_log_files`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBInstanceIdentifier='string',
          FilenameContains='string',
          FileLastWritten=123,
          FileSize=123,
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
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The customer-assigned name of the DB instance that contains the log files you want to list.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type FilenameContains: string
    :param FilenameContains: 

      Filters the available log files for log file names that contain the specified string.

      

    
    :type FileLastWritten: integer
    :param FileLastWritten: 

      Filters the available log files for files written since the specified date, in POSIX timestamp format with milliseconds.

      

    
    :type FileSize: integer
    :param FileSize: 

      Filters the available log files for files larger than the specified size.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'DescribeDBLogFiles': [
                {
                    'LogFileName': 'string',
                    'LastWritten': 123,
                    'Size': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response from a call to  DescribeDBLogFiles . 

        
        

        - **DescribeDBLogFiles** *(list) --* 

          The DB log files returned.

          
          

          - *(dict) --* 

            This data type is used as a response element to  DescribeDBLogFiles .

            
            

            - **LogFileName** *(string) --* 

              The name of the log file for the specified DB instance.

              
            

            - **LastWritten** *(integer) --* 

              A POSIX timestamp when the last log entry was written.

              
            

            - **Size** *(integer) --* 

              The size, in bytes, of the log file for the specified DB instance.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeDBParameterGroups

  ::

    
    paginator = client.get_paginator('describe_db_parameter_groups')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_db_parameter_groups`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBParameterGroupName='string',
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
    :type DBParameterGroupName: string
    :param DBParameterGroupName: 

      The name of a specific DB parameter group to return details for.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'DBParameterGroups': [
                {
                    'DBParameterGroupName': 'string',
                    'DBParameterGroupFamily': 'string',
                    'Description': 'string',
                    'DBParameterGroupArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBParameterGroups action. 

        
        

        - **DBParameterGroups** *(list) --* 

          A list of  DBParameterGroup instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the  CreateDBParameterGroup action. 

             

            This data type is used as a request parameter in the  DeleteDBParameterGroup action, and as a response element in the  DescribeDBParameterGroups action. 

            
            

            - **DBParameterGroupName** *(string) --* 

              Provides the name of the DB parameter group.

              
            

            - **DBParameterGroupFamily** *(string) --* 

              Provides the name of the DB parameter group family that this DB parameter group is compatible with.

              
            

            - **Description** *(string) --* 

              Provides the customer-specified description for this DB parameter group.

              
            

            - **DBParameterGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB parameter group.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeDBParameters

  ::

    
    paginator = client.get_paginator('describe_db_parameters')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_db_parameters`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBParameterGroupName='string',
          Source='string',
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
    :type DBParameterGroupName: string
    :param DBParameterGroupName: **[REQUIRED]** 

      The name of a specific DB parameter group to return details for.

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Source: string
    :param Source: 

      The parameter types to return.

       

      Default: All parameter types returned

       

      Valid Values: ``user | system | engine-default``  

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'Parameters': [
                {
                    'ParameterName': 'string',
                    'ParameterValue': 'string',
                    'Description': 'string',
                    'Source': 'string',
                    'ApplyType': 'string',
                    'DataType': 'string',
                    'AllowedValues': 'string',
                    'IsModifiable': True|False,
                    'MinimumEngineVersion': 'string',
                    'ApplyMethod': 'immediate'|'pending-reboot'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBParameters action. 

        
        

        - **Parameters** *(list) --* 

          A list of  Parameter values. 

          
          

          - *(dict) --* 

            This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

             

            This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

            
            

            - **ParameterName** *(string) --* 

              Specifies the name of the parameter.

              
            

            - **ParameterValue** *(string) --* 

              Specifies the value of the parameter.

              
            

            - **Description** *(string) --* 

              Provides a description of the parameter.

              
            

            - **Source** *(string) --* 

              Indicates the source of the parameter value.

              
            

            - **ApplyType** *(string) --* 

              Specifies the engine specific parameters type.

              
            

            - **DataType** *(string) --* 

              Specifies the valid data type for the parameter.

              
            

            - **AllowedValues** *(string) --* 

              Specifies the valid range of values for the parameter.

              
            

            - **IsModifiable** *(boolean) --* 

              Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

              
            

            - **MinimumEngineVersion** *(string) --* 

              The earliest engine version to which the parameter can apply.

              
            

            - **ApplyMethod** *(string) --* 

              Indicates when to apply parameter updates.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeDBSecurityGroups

  ::

    
    paginator = client.get_paginator('describe_db_security_groups')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_db_security_groups`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBSecurityGroupName='string',
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
    :type DBSecurityGroupName: string
    :param DBSecurityGroupName: 

      The name of the DB security group to return details for.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'DBSecurityGroups': [
                {
                    'OwnerId': 'string',
                    'DBSecurityGroupName': 'string',
                    'DBSecurityGroupDescription': 'string',
                    'VpcId': 'string',
                    'EC2SecurityGroups': [
                        {
                            'Status': 'string',
                            'EC2SecurityGroupName': 'string',
                            'EC2SecurityGroupId': 'string',
                            'EC2SecurityGroupOwnerId': 'string'
                        },
                    ],
                    'IPRanges': [
                        {
                            'Status': 'string',
                            'CIDRIP': 'string'
                        },
                    ],
                    'DBSecurityGroupArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBSecurityGroups action. 

        
        

        - **DBSecurityGroups** *(list) --* 

          A list of  DBSecurityGroup instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  DescribeDBSecurityGroups   
             
            *  AuthorizeDBSecurityGroupIngress   
             
            *  CreateDBSecurityGroup   
             
            *  RevokeDBSecurityGroupIngress   
             

             

            This data type is used as a response element in the  DescribeDBSecurityGroups action.

            
            

            - **OwnerId** *(string) --* 

              Provides the AWS ID of the owner of a specific DB security group.

              
            

            - **DBSecurityGroupName** *(string) --* 

              Specifies the name of the DB security group.

              
            

            - **DBSecurityGroupDescription** *(string) --* 

              Provides the description of the DB security group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB security group.

              
            

            - **EC2SecurityGroups** *(list) --* 

              Contains a list of  EC2SecurityGroup elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the following actions:

                 

                 
                *  AuthorizeDBSecurityGroupIngress   
                 
                *  DescribeDBSecurityGroups   
                 
                *  RevokeDBSecurityGroupIngress   
                 

                
                

                - **Status** *(string) --* 

                  Provides the status of the EC2 security group. Status can be "authorizing", "authorized", "revoking", and "revoked".

                  
                

                - **EC2SecurityGroupName** *(string) --* 

                  Specifies the name of the EC2 security group.

                  
                

                - **EC2SecurityGroupId** *(string) --* 

                  Specifies the id of the EC2 security group.

                  
                

                - **EC2SecurityGroupOwnerId** *(string) --* 

                  Specifies the AWS ID of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` field. 

                  
            
          
            

            - **IPRanges** *(list) --* 

              Contains a list of  IPRange elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSecurityGroups action. 

                
                

                - **Status** *(string) --* 

                  Specifies the status of the IP range. Status can be "authorizing", "authorized", "revoking", and "revoked".

                  
                

                - **CIDRIP** *(string) --* 

                  Specifies the IP range.

                  
            
          
            

            - **DBSecurityGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB security group.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeDBSnapshots

  ::

    
    paginator = client.get_paginator('describe_db_snapshots')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_db_snapshots`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBInstanceIdentifier='string',
          DBSnapshotIdentifier='string',
          SnapshotType='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          IncludeShared=True|False,
          IncludePublic=True|False,
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: 

      The ID of the DB instance to retrieve the list of DB snapshots for. This parameter cannot be used in conjunction with ``DBSnapshotIdentifier`` . This parameter is not case-sensitive. 

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type DBSnapshotIdentifier: string
    :param DBSnapshotIdentifier: 

      A specific DB snapshot identifier to describe. This parameter cannot be used in conjunction with ``DBInstanceIdentifier`` . This value is stored as a lowercase string. 

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       
      * If this identifier is for an automated snapshot, the ``SnapshotType`` parameter must also be specified. 
       

      

    
    :type SnapshotType: string
    :param SnapshotType: 

      The type of snapshots to be returned. You can specify one of the following values:

       

       
      * ``automated`` - Return all DB snapshots that have been automatically taken by Amazon RDS for my AWS account. 
       
      * ``manual`` - Return all DB snapshots that have been taken by my AWS account. 
       
      * ``shared`` - Return all manual DB snapshots that have been shared to my AWS account. 
       
      * ``public`` - Return all DB snapshots that have been marked as public. 
       

       

      If you don't specify a ``SnapshotType`` value, then both automated and manual snapshots are returned. Shared and public DB snapshots are not included in the returned results by default. You can include shared snapshots with these results by setting the ``IncludeShared`` parameter to ``true`` . You can include public snapshots with these results by setting the ``IncludePublic`` parameter to ``true`` .

       

      The ``IncludeShared`` and ``IncludePublic`` parameters don't apply for ``SnapshotType`` values of ``manual`` or ``automated`` . The ``IncludePublic`` parameter doesn't apply when ``SnapshotType`` is set to ``shared`` . The ``IncludeShared`` parameter doesn't apply when ``SnapshotType`` is set to ``public`` .

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type IncludeShared: boolean
    :param IncludeShared: 

      Set this value to ``true`` to include shared manual DB snapshots from other AWS accounts that this AWS account has been given permission to copy or restore, otherwise set this value to ``false`` . The default is ``false`` .

       

      You can give an AWS account permission to restore a manual DB snapshot from another AWS account by using the  ModifyDBSnapshotAttribute API action.

      

    
    :type IncludePublic: boolean
    :param IncludePublic: 

      Set this value to ``true`` to include manual DB snapshots that are public and can be copied or restored by any AWS account, otherwise set this value to ``false`` . The default is ``false`` .

       

      You can share a manual DB snapshot as public by using the  ModifyDBSnapshotAttribute API.

      

    
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
            'DBSnapshots': [
                {
                    'DBSnapshotIdentifier': 'string',
                    'DBInstanceIdentifier': 'string',
                    'SnapshotCreateTime': datetime(2015, 1, 1),
                    'Engine': 'string',
                    'AllocatedStorage': 123,
                    'Status': 'string',
                    'Port': 123,
                    'AvailabilityZone': 'string',
                    'VpcId': 'string',
                    'InstanceCreateTime': datetime(2015, 1, 1),
                    'MasterUsername': 'string',
                    'EngineVersion': 'string',
                    'LicenseModel': 'string',
                    'SnapshotType': 'string',
                    'Iops': 123,
                    'OptionGroupName': 'string',
                    'PercentProgress': 123,
                    'SourceRegion': 'string',
                    'SourceDBSnapshotIdentifier': 'string',
                    'StorageType': 'string',
                    'TdeCredentialArn': 'string',
                    'Encrypted': True|False,
                    'KmsKeyId': 'string',
                    'DBSnapshotArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBSnapshots action. 

        
        

        - **DBSnapshots** *(list) --* 

          A list of  DBSnapshot instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  CreateDBSnapshot   
             
            *  DeleteDBSnapshot   
             

             

            This data type is used as a response element in the  DescribeDBSnapshots action.

            
            

            - **DBSnapshotIdentifier** *(string) --* 

              Specifies the identifier for the DB snapshot.

              
            

            - **DBInstanceIdentifier** *(string) --* 

              Specifies the DB instance identifier of the DB instance this DB snapshot was created from.

              
            

            - **SnapshotCreateTime** *(datetime) --* 

              Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

              
            

            - **Engine** *(string) --* 

              Specifies the name of the database engine.

              
            

            - **AllocatedStorage** *(integer) --* 

              Specifies the allocated storage size in gigabytes (GB).

              
            

            - **Status** *(string) --* 

              Specifies the status of this DB snapshot.

              
            

            - **Port** *(integer) --* 

              Specifies the port that the database engine was listening on at the time of the snapshot.

              
            

            - **AvailabilityZone** *(string) --* 

              Specifies the name of the Availability Zone the DB instance was located in at the time of the DB snapshot.

              
            

            - **VpcId** *(string) --* 

              Provides the VPC ID associated with the DB snapshot.

              
            

            - **InstanceCreateTime** *(datetime) --* 

              Specifies the time when the snapshot was taken, in Universal Coordinated Time (UTC).

              
            

            - **MasterUsername** *(string) --* 

              Provides the master username for the DB snapshot.

              
            

            - **EngineVersion** *(string) --* 

              Specifies the version of the database engine.

              
            

            - **LicenseModel** *(string) --* 

              License model information for the restored DB instance.

              
            

            - **SnapshotType** *(string) --* 

              Provides the type of the DB snapshot.

              
            

            - **Iops** *(integer) --* 

              Specifies the Provisioned IOPS (I/O operations per second) value of the DB instance at the time of the snapshot.

              
            

            - **OptionGroupName** *(string) --* 

              Provides the option group name for the DB snapshot.

              
            

            - **PercentProgress** *(integer) --* 

              The percentage of the estimated data that has been transferred.

              
            

            - **SourceRegion** *(string) --* 

              The region that the DB snapshot was created in or copied from.

              
            

            - **SourceDBSnapshotIdentifier** *(string) --* 

              The DB snapshot Arn that the DB snapshot was copied from. It only has value in case of cross customer or cross region copy.

              
            

            - **StorageType** *(string) --* 

              Specifies the storage type associated with DB Snapshot.

              
            

            - **TdeCredentialArn** *(string) --* 

              The ARN from the Key Store with which to associate the instance for TDE encryption.

              
            

            - **Encrypted** *(boolean) --* 

              Specifies whether the DB snapshot is encrypted.

              
            

            - **KmsKeyId** *(string) --* 

              If ``Encrypted`` is true, the KMS key identifier for the encrypted DB snapshot. 

              
            

            - **DBSnapshotArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB snapshot.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeDBSubnetGroups

  ::

    
    paginator = client.get_paginator('describe_db_subnet_groups')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_db_subnet_groups`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBSubnetGroupName='string',
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
    :type DBSubnetGroupName: string
    :param DBSubnetGroupName: 

      The name of the DB subnet group to return details for.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'DBSubnetGroups': [
                {
                    'DBSubnetGroupName': 'string',
                    'DBSubnetGroupDescription': 'string',
                    'VpcId': 'string',
                    'SubnetGroupStatus': 'string',
                    'Subnets': [
                        {
                            'SubnetIdentifier': 'string',
                            'SubnetAvailabilityZone': {
                                'Name': 'string'
                            },
                            'SubnetStatus': 'string'
                        },
                    ],
                    'DBSubnetGroupArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeDBSubnetGroups action. 

        
        

        - **DBSubnetGroups** *(list) --* 

          A list of  DBSubnetGroup instances. 

          
          

          - *(dict) --* 

            Contains the result of a successful invocation of the following actions:

             

             
            *  CreateDBSubnetGroup   
             
            *  ModifyDBSubnetGroup   
             
            *  DescribeDBSubnetGroups   
             
            *  DeleteDBSubnetGroup   
             

             

            This data type is used as a response element in the  DescribeDBSubnetGroups action.

            
            

            - **DBSubnetGroupName** *(string) --* 

              The name of the DB subnet group.

              
            

            - **DBSubnetGroupDescription** *(string) --* 

              Provides the description of the DB subnet group.

              
            

            - **VpcId** *(string) --* 

              Provides the VpcId of the DB subnet group.

              
            

            - **SubnetGroupStatus** *(string) --* 

              Provides the status of the DB subnet group.

              
            

            - **Subnets** *(list) --* 

              Contains a list of  Subnet elements. 

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeDBSubnetGroups action. 

                
                

                - **SubnetIdentifier** *(string) --* 

                  Specifies the identifier of the subnet.

                  
                

                - **SubnetAvailabilityZone** *(dict) --* 

                  Contains Availability Zone information.

                   

                  This data type is used as an element in the following data type:

                   

                   
                  *  OrderableDBInstanceOption   
                   

                  
                  

                  - **Name** *(string) --* 

                    The name of the availability zone.

                    
              
                

                - **SubnetStatus** *(string) --* 

                  Specifies the status of the subnet.

                  
            
          
            

            - **DBSubnetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the DB subnet group.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeEngineDefaultParameters

  ::

    
    paginator = client.get_paginator('describe_engine_default_parameters')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_engine_default_parameters`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBParameterGroupFamily='string',
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
    :type DBParameterGroupFamily: string
    :param DBParameterGroupFamily: **[REQUIRED]** 

      The name of the DB parameter group family.

      

    
    :type Filters: list
    :param Filters: 

      Not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'EngineDefaults': {
                'DBParameterGroupFamily': 'string',
                'Marker': 'string',
                'Parameters': [
                    {
                        'ParameterName': 'string',
                        'ParameterValue': 'string',
                        'Description': 'string',
                        'Source': 'string',
                        'ApplyType': 'string',
                        'DataType': 'string',
                        'AllowedValues': 'string',
                        'IsModifiable': True|False,
                        'MinimumEngineVersion': 'string',
                        'ApplyMethod': 'immediate'|'pending-reboot'
                    },
                ]
            },
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **EngineDefaults** *(dict) --* 

          Contains the result of a successful invocation of the  DescribeEngineDefaultParameters action. 

          
          

          - **DBParameterGroupFamily** *(string) --* 

            Specifies the name of the DB parameter group family that the engine default parameters apply to.

            
          

          - **Marker** *(string) --* 

            An optional pagination token provided by a previous EngineDefaults request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

            
          

          - **Parameters** *(list) --* 

            Contains a list of engine default parameters.

            
            

            - *(dict) --* 

              This data type is used as a request parameter in the  ModifyDBParameterGroup and  ResetDBParameterGroup actions. 

               

              This data type is used as a response element in the  DescribeEngineDefaultParameters and  DescribeDBParameters actions.

              
              

              - **ParameterName** *(string) --* 

                Specifies the name of the parameter.

                
              

              - **ParameterValue** *(string) --* 

                Specifies the value of the parameter.

                
              

              - **Description** *(string) --* 

                Provides a description of the parameter.

                
              

              - **Source** *(string) --* 

                Indicates the source of the parameter value.

                
              

              - **ApplyType** *(string) --* 

                Specifies the engine specific parameters type.

                
              

              - **DataType** *(string) --* 

                Specifies the valid data type for the parameter.

                
              

              - **AllowedValues** *(string) --* 

                Specifies the valid range of values for the parameter.

                
              

              - **IsModifiable** *(boolean) --* 

                Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

                
              

              - **MinimumEngineVersion** *(string) --* 

                The earliest engine version to which the parameter can apply.

                
              

              - **ApplyMethod** *(string) --* 

                Indicates when to apply parameter updates.

                
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeEventSubscriptions

  ::

    
    paginator = client.get_paginator('describe_event_subscriptions')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_event_subscriptions`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          SubscriptionName='string',
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
    :type SubscriptionName: string
    :param SubscriptionName: 

      The name of the RDS event notification subscription you want to describe.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'EventSubscriptionsList': [
                {
                    'CustomerAwsId': 'string',
                    'CustSubscriptionId': 'string',
                    'SnsTopicArn': 'string',
                    'Status': 'string',
                    'SubscriptionCreationTime': 'string',
                    'SourceType': 'string',
                    'SourceIdsList': [
                        'string',
                    ],
                    'EventCategoriesList': [
                        'string',
                    ],
                    'Enabled': True|False,
                    'EventSubscriptionArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Data returned by the **DescribeEventSubscriptions** action.

        
        

        - **EventSubscriptionsList** *(list) --* 

          A list of EventSubscriptions data types.

          
          

          - *(dict) --* 

            Contains the results of a successful invocation of the  DescribeEventSubscriptions action.

            
            

            - **CustomerAwsId** *(string) --* 

              The AWS customer account associated with the RDS event notification subscription.

              
            

            - **CustSubscriptionId** *(string) --* 

              The RDS event notification subscription Id.

              
            

            - **SnsTopicArn** *(string) --* 

              The topic ARN of the RDS event notification subscription.

              
            

            - **Status** *(string) --* 

              The status of the RDS event notification subscription.

               

              Constraints:

               

              Can be one of the following: creating | modifying | deleting | active | no-permission | topic-not-exist

               

              The status "no-permission" indicates that RDS no longer has permission to post to the SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created.

              
            

            - **SubscriptionCreationTime** *(string) --* 

              The time the RDS event notification subscription was created.

              
            

            - **SourceType** *(string) --* 

              The source type for the RDS event notification subscription.

              
            

            - **SourceIdsList** *(list) --* 

              A list of source IDs for the RDS event notification subscription.

              
              

              - *(string) --* 
          
            

            - **EventCategoriesList** *(list) --* 

              A list of event categories for the RDS event notification subscription.

              
              

              - *(string) --* 
          
            

            - **Enabled** *(boolean) --* 

              A Boolean value indicating if the subscription is enabled. True indicates the subscription is enabled.

              
            

            - **EventSubscriptionArn** *(string) --* 

              The Amazon Resource Name (ARN) for the event subscription.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeEvents

  ::

    
    paginator = client.get_paginator('describe_events')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_events`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          SourceIdentifier='string',
          SourceType='db-instance'|'db-parameter-group'|'db-security-group'|'db-snapshot'|'db-cluster'|'db-cluster-snapshot',
          StartTime=datetime(2015, 1, 1),
          EndTime=datetime(2015, 1, 1),
          Duration=123,
          EventCategories=[
              'string',
          ],
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
    :type SourceIdentifier: string
    :param SourceIdentifier: 

      The identifier of the event source for which events will be returned. If not specified, then all sources are included in the response.

       

      Constraints:

       

       
      * If SourceIdentifier is supplied, SourceType must also be provided. 
       
      * If the source type is ``DBInstance`` , then a ``DBInstanceIdentifier`` must be supplied. 
       
      * If the source type is ``DBSecurityGroup`` , a ``DBSecurityGroupName`` must be supplied. 
       
      * If the source type is ``DBParameterGroup`` , a ``DBParameterGroupName`` must be supplied. 
       
      * If the source type is ``DBSnapshot`` , a ``DBSnapshotIdentifier`` must be supplied. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

      

    
    :type SourceType: string
    :param SourceType: 

      The event source to retrieve events for. If no value is specified, all events are returned.

      

    
    :type StartTime: datetime
    :param StartTime: 

      The beginning of the time interval to retrieve events for, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page.`_  

       

      Example: 2009-07-08T18:00Z

      

    
    :type EndTime: datetime
    :param EndTime: 

      The end of the time interval for which to retrieve events, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page.`_  

       

      Example: 2009-07-08T18:00Z

      

    
    :type Duration: integer
    :param Duration: 

      The number of minutes to retrieve events for.

       

      Default: 60

      

    
    :type EventCategories: list
    :param EventCategories: 

      A list of event categories that trigger notifications for a event notification subscription.

      

    
      - *(string) --* 

      
  
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'Events': [
                {
                    'SourceIdentifier': 'string',
                    'SourceType': 'db-instance'|'db-parameter-group'|'db-security-group'|'db-snapshot'|'db-cluster'|'db-cluster-snapshot',
                    'Message': 'string',
                    'EventCategories': [
                        'string',
                    ],
                    'Date': datetime(2015, 1, 1),
                    'SourceArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeEvents action. 

        
        

        - **Events** *(list) --* 

          A list of  Event instances. 

          
          

          - *(dict) --* 

            This data type is used as a response element in the  DescribeEvents action. 

            
            

            - **SourceIdentifier** *(string) --* 

              Provides the identifier for the source of the event.

              
            

            - **SourceType** *(string) --* 

              Specifies the source type for this event.

              
            

            - **Message** *(string) --* 

              Provides the text of this event.

              
            

            - **EventCategories** *(list) --* 

              Specifies the category for the event.

              
              

              - *(string) --* 
          
            

            - **Date** *(datetime) --* 

              Specifies the date and time of the event.

              
            

            - **SourceArn** *(string) --* 

              The Amazon Resource Name (ARN) for the event.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeOptionGroupOptions

  ::

    
    paginator = client.get_paginator('describe_option_group_options')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_option_group_options`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          EngineName='string',
          MajorEngineVersion='string',
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
    :type EngineName: string
    :param EngineName: **[REQUIRED]** 

      A required parameter. Options available for the given engine name will be described.

      

    
    :type MajorEngineVersion: string
    :param MajorEngineVersion: 

      If specified, filters the results to include only options for the specified major engine version.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'OptionGroupOptions': [
                {
                    'Name': 'string',
                    'Description': 'string',
                    'EngineName': 'string',
                    'MajorEngineVersion': 'string',
                    'MinimumRequiredMinorEngineVersion': 'string',
                    'PortRequired': True|False,
                    'DefaultPort': 123,
                    'OptionsDependedOn': [
                        'string',
                    ],
                    'OptionsConflictsWith': [
                        'string',
                    ],
                    'Persistent': True|False,
                    'Permanent': True|False,
                    'OptionGroupOptionSettings': [
                        {
                            'SettingName': 'string',
                            'SettingDescription': 'string',
                            'DefaultValue': 'string',
                            'ApplyType': 'string',
                            'AllowedValues': 'string',
                            'IsModifiable': True|False
                        },
                    ],
                    'OptionGroupOptionVersions': [
                        {
                            'Version': 'string',
                            'IsDefault': True|False
                        },
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        

        
        

        - **OptionGroupOptions** *(list) --* 

          List of available option group options.

          
          

          - *(dict) --* 

            Available option.

            
            

            - **Name** *(string) --* 

              The name of the option.

              
            

            - **Description** *(string) --* 

              The description of the option.

              
            

            - **EngineName** *(string) --* 

              The name of the engine that this option can be applied to.

              
            

            - **MajorEngineVersion** *(string) --* 

              Indicates the major engine version that the option is available for.

              
            

            - **MinimumRequiredMinorEngineVersion** *(string) --* 

              The minimum required engine version for the option to be applied.

              
            

            - **PortRequired** *(boolean) --* 

              Specifies whether the option requires a port.

              
            

            - **DefaultPort** *(integer) --* 

              If the option requires a port, specifies the default port for the option.

              
            

            - **OptionsDependedOn** *(list) --* 

              The options that are prerequisites for this option.

              
              

              - *(string) --* 
          
            

            - **OptionsConflictsWith** *(list) --* 

              The options that conflict with this option.

              
              

              - *(string) --* 
          
            

            - **Persistent** *(boolean) --* 

              Persistent options can't be removed from an option group while DB instances are associated with the option group. If you disassociate all DB instances from the option group, your can remove the persistent option from the option group.

              
            

            - **Permanent** *(boolean) --* 

              Permanent options can never be removed from an option group. An option group containing a permanent option can't be removed from a DB instance.

              
            

            - **OptionGroupOptionSettings** *(list) --* 

              The option settings that are available (and the default value) for each option in an option group.

              
              

              - *(dict) --* 

                Option group option settings are used to display settings available for each option with their default values and other information. These values are used with the DescribeOptionGroupOptions action.

                
                

                - **SettingName** *(string) --* 

                  The name of the option group option.

                  
                

                - **SettingDescription** *(string) --* 

                  The description of the option group option.

                  
                

                - **DefaultValue** *(string) --* 

                  The default value for the option group option.

                  
                

                - **ApplyType** *(string) --* 

                  The DB engine specific parameter type for the option group option.

                  
                

                - **AllowedValues** *(string) --* 

                  Indicates the acceptable values for the option group option.

                  
                

                - **IsModifiable** *(boolean) --* 

                  Boolean value where true indicates that this option group option can be changed from the default value.

                  
            
          
            

            - **OptionGroupOptionVersions** *(list) --* 

              The versions that are available for the option.

              
              

              - *(dict) --* 

                The version for an option. Option group option versions are returned by the  DescribeOptionGroupOptions action.

                
                

                - **Version** *(string) --* 

                  The version of the option.

                  
                

                - **IsDefault** *(boolean) --* 

                  True if the version is the default version of the option; otherwise, false.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeOptionGroups

  ::

    
    paginator = client.get_paginator('describe_option_groups')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_option_groups`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          OptionGroupName='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          EngineName='string',
          MajorEngineVersion='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type OptionGroupName: string
    :param OptionGroupName: 

      The name of the option group to describe. Cannot be supplied together with EngineName or MajorEngineVersion.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type EngineName: string
    :param EngineName: 

      Filters the list of option groups to only include groups associated with a specific database engine.

      

    
    :type MajorEngineVersion: string
    :param MajorEngineVersion: 

      Filters the list of option groups to only include groups associated with a specific database engine version. If specified, then EngineName must also be specified.

      

    
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
            'OptionGroupsList': [
                {
                    'OptionGroupName': 'string',
                    'OptionGroupDescription': 'string',
                    'EngineName': 'string',
                    'MajorEngineVersion': 'string',
                    'Options': [
                        {
                            'OptionName': 'string',
                            'OptionDescription': 'string',
                            'Persistent': True|False,
                            'Permanent': True|False,
                            'Port': 123,
                            'OptionVersion': 'string',
                            'OptionSettings': [
                                {
                                    'Name': 'string',
                                    'Value': 'string',
                                    'DefaultValue': 'string',
                                    'Description': 'string',
                                    'ApplyType': 'string',
                                    'DataType': 'string',
                                    'AllowedValues': 'string',
                                    'IsModifiable': True|False,
                                    'IsCollection': True|False
                                },
                            ],
                            'DBSecurityGroupMemberships': [
                                {
                                    'DBSecurityGroupName': 'string',
                                    'Status': 'string'
                                },
                            ],
                            'VpcSecurityGroupMemberships': [
                                {
                                    'VpcSecurityGroupId': 'string',
                                    'Status': 'string'
                                },
                            ]
                        },
                    ],
                    'AllowsVpcAndNonVpcInstanceMemberships': True|False,
                    'VpcId': 'string',
                    'OptionGroupArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        List of option groups.

        
        

        - **OptionGroupsList** *(list) --* 

          List of option groups.

          
          

          - *(dict) --* 

            

            
            

            - **OptionGroupName** *(string) --* 

              Specifies the name of the option group.

              
            

            - **OptionGroupDescription** *(string) --* 

              Provides a description of the option group.

              
            

            - **EngineName** *(string) --* 

              Indicates the name of the engine that this option group can be applied to.

              
            

            - **MajorEngineVersion** *(string) --* 

              Indicates the major engine version associated with this option group.

              
            

            - **Options** *(list) --* 

              Indicates what options are available in the option group.

              
              

              - *(dict) --* 

                Option details.

                
                

                - **OptionName** *(string) --* 

                  The name of the option.

                  
                

                - **OptionDescription** *(string) --* 

                  The description of the option.

                  
                

                - **Persistent** *(boolean) --* 

                  Indicate if this option is persistent.

                  
                

                - **Permanent** *(boolean) --* 

                  Indicate if this option is permanent.

                  
                

                - **Port** *(integer) --* 

                  If required, the port configured for this option to use.

                  
                

                - **OptionVersion** *(string) --* 

                  The version of the option.

                  
                

                - **OptionSettings** *(list) --* 

                  The option settings for this option.

                  
                  

                  - *(dict) --* 

                    Option settings are the actual settings being applied or configured for that option. It is used when you modify an option group or describe option groups. For example, the NATIVE_NETWORK_ENCRYPTION option has a setting called SQLNET.ENCRYPTION_SERVER that can have several different values.

                    
                    

                    - **Name** *(string) --* 

                      The name of the option that has settings that you can set.

                      
                    

                    - **Value** *(string) --* 

                      The current value of the option setting.

                      
                    

                    - **DefaultValue** *(string) --* 

                      The default value of the option setting.

                      
                    

                    - **Description** *(string) --* 

                      The description of the option setting.

                      
                    

                    - **ApplyType** *(string) --* 

                      The DB engine specific parameter type.

                      
                    

                    - **DataType** *(string) --* 

                      The data type of the option setting.

                      
                    

                    - **AllowedValues** *(string) --* 

                      The allowed values of the option setting.

                      
                    

                    - **IsModifiable** *(boolean) --* 

                      A Boolean value that, when true, indicates the option setting can be modified from the default.

                      
                    

                    - **IsCollection** *(boolean) --* 

                      Indicates if the option setting is part of a collection.

                      
                
              
                

                - **DBSecurityGroupMemberships** *(list) --* 

                  If the option requires access to a port, then this DB security group allows access to the port.

                  
                  

                  - *(dict) --* 

                    This data type is used as a response element in the following actions:

                     

                     
                    *  ModifyDBInstance   
                     
                    *  RebootDBInstance   
                     
                    *  RestoreDBInstanceFromDBSnapshot   
                     
                    *  RestoreDBInstanceToPointInTime   
                     

                    
                    

                    - **DBSecurityGroupName** *(string) --* 

                      The name of the DB security group.

                      
                    

                    - **Status** *(string) --* 

                      The status of the DB security group.

                      
                
              
                

                - **VpcSecurityGroupMemberships** *(list) --* 

                  If the option requires access to a port, then this VPC security group allows access to the port.

                  
                  

                  - *(dict) --* 

                    This data type is used as a response element for queries on VPC security group membership.

                    
                    

                    - **VpcSecurityGroupId** *(string) --* 

                      The name of the VPC security group.

                      
                    

                    - **Status** *(string) --* 

                      The status of the VPC security group.

                      
                
              
            
          
            

            - **AllowsVpcAndNonVpcInstanceMemberships** *(boolean) --* 

              Indicates whether this option group can be applied to both VPC and non-VPC instances. The value ``true`` indicates the option group can be applied to both VPC and non-VPC instances. 

              
            

            - **VpcId** *(string) --* 

              If **AllowsVpcAndNonVpcInstanceMemberships** is ``false`` , this field is blank. If **AllowsVpcAndNonVpcInstanceMemberships** is ``true`` and this field is blank, then this option group can be applied to both VPC and non-VPC instances. If this field contains a value, then this option group can only be applied to instances that are in the VPC indicated by this field. 

              
            

            - **OptionGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) for the option group.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeOrderableDBInstanceOptions

  ::

    
    paginator = client.get_paginator('describe_orderable_db_instance_options')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_orderable_db_instance_options`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          Engine='string',
          EngineVersion='string',
          DBInstanceClass='string',
          LicenseModel='string',
          Vpc=True|False,
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
    :type Engine: string
    :param Engine: **[REQUIRED]** 

      The name of the engine to retrieve DB instance options for.

      

    
    :type EngineVersion: string
    :param EngineVersion: 

      The engine version filter value. Specify this parameter to show only the available offerings matching the specified engine version.

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The DB instance class filter value. Specify this parameter to show only the available offerings matching the specified DB instance class.

      

    
    :type LicenseModel: string
    :param LicenseModel: 

      The license model filter value. Specify this parameter to show only the available offerings matching the specified license model.

      

    
    :type Vpc: boolean
    :param Vpc: 

      The VPC filter value. Specify this parameter to show only the available VPC or non-VPC offerings.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'OrderableDBInstanceOptions': [
                {
                    'Engine': 'string',
                    'EngineVersion': 'string',
                    'DBInstanceClass': 'string',
                    'LicenseModel': 'string',
                    'AvailabilityZones': [
                        {
                            'Name': 'string'
                        },
                    ],
                    'MultiAZCapable': True|False,
                    'ReadReplicaCapable': True|False,
                    'Vpc': True|False,
                    'SupportsStorageEncryption': True|False,
                    'StorageType': 'string',
                    'SupportsIops': True|False,
                    'SupportsEnhancedMonitoring': True|False
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeOrderableDBInstanceOptions action. 

        
        

        - **OrderableDBInstanceOptions** *(list) --* 

          An  OrderableDBInstanceOption structure containing information about orderable options for the DB instance.

          
          

          - *(dict) --* 

            Contains a list of available options for a DB instance

             

            This data type is used as a response element in the  DescribeOrderableDBInstanceOptions action. 

            
            

            - **Engine** *(string) --* 

              The engine type of the orderable DB instance.

              
            

            - **EngineVersion** *(string) --* 

              The engine version of the orderable DB instance.

              
            

            - **DBInstanceClass** *(string) --* 

              The DB instance class for the orderable DB instance.

              
            

            - **LicenseModel** *(string) --* 

              The license model for the orderable DB instance.

              
            

            - **AvailabilityZones** *(list) --* 

              A list of Availability Zones for the orderable DB instance.

              
              

              - *(dict) --* 

                Contains Availability Zone information.

                 

                This data type is used as an element in the following data type:

                 

                 
                *  OrderableDBInstanceOption   
                 

                
                

                - **Name** *(string) --* 

                  The name of the availability zone.

                  
            
          
            

            - **MultiAZCapable** *(boolean) --* 

              Indicates whether this orderable DB instance is multi-AZ capable.

              
            

            - **ReadReplicaCapable** *(boolean) --* 

              Indicates whether this orderable DB instance can have a Read Replica.

              
            

            - **Vpc** *(boolean) --* 

              Indicates whether this is a VPC orderable DB instance.

              
            

            - **SupportsStorageEncryption** *(boolean) --* 

              Indicates whether this orderable DB instance supports encrypted storage.

              
            

            - **StorageType** *(string) --* 

              Indicates the storage type for this orderable DB instance.

              
            

            - **SupportsIops** *(boolean) --* 

              Indicates whether this orderable DB instance supports provisioned IOPS.

              
            

            - **SupportsEnhancedMonitoring** *(boolean) --* 

              Indicates whether the DB instance supports enhanced monitoring at intervals from 1 to 60 seconds.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeReservedDBInstances

  ::

    
    paginator = client.get_paginator('describe_reserved_db_instances')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_reserved_db_instances`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          ReservedDBInstanceId='string',
          ReservedDBInstancesOfferingId='string',
          DBInstanceClass='string',
          Duration='string',
          ProductDescription='string',
          OfferingType='string',
          MultiAZ=True|False,
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
    :type ReservedDBInstanceId: string
    :param ReservedDBInstanceId: 

      The reserved DB instance identifier filter value. Specify this parameter to show only the reservation that matches the specified reservation ID.

      

    
    :type ReservedDBInstancesOfferingId: string
    :param ReservedDBInstancesOfferingId: 

      The offering identifier filter value. Specify this parameter to show only purchased reservations matching the specified offering identifier.

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The DB instance class filter value. Specify this parameter to show only those reservations matching the specified DB instances class.

      

    
    :type Duration: string
    :param Duration: 

      The duration filter value, specified in years or seconds. Specify this parameter to show only reservations for this duration.

       

      Valid Values: ``1 | 3 | 31536000 | 94608000``  

      

    
    :type ProductDescription: string
    :param ProductDescription: 

      The product description filter value. Specify this parameter to show only those reservations matching the specified product description.

      

    
    :type OfferingType: string
    :param OfferingType: 

      The offering type filter value. Specify this parameter to show only the available offerings matching the specified offering type.

       

      Valid Values: ``"Partial Upfront" | "All Upfront" | "No Upfront"``  

      

    
    :type MultiAZ: boolean
    :param MultiAZ: 

      The Multi-AZ filter value. Specify this parameter to show only those reservations matching the specified Multi-AZ parameter.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'ReservedDBInstances': [
                {
                    'ReservedDBInstanceId': 'string',
                    'ReservedDBInstancesOfferingId': 'string',
                    'DBInstanceClass': 'string',
                    'StartTime': datetime(2015, 1, 1),
                    'Duration': 123,
                    'FixedPrice': 123.0,
                    'UsagePrice': 123.0,
                    'CurrencyCode': 'string',
                    'DBInstanceCount': 123,
                    'ProductDescription': 'string',
                    'OfferingType': 'string',
                    'MultiAZ': True|False,
                    'State': 'string',
                    'RecurringCharges': [
                        {
                            'RecurringChargeAmount': 123.0,
                            'RecurringChargeFrequency': 'string'
                        },
                    ],
                    'ReservedDBInstanceArn': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeReservedDBInstances action. 

        
        

        - **ReservedDBInstances** *(list) --* 

          A list of reserved DB instances.

          
          

          - *(dict) --* 

            This data type is used as a response element in the  DescribeReservedDBInstances and  PurchaseReservedDBInstancesOffering actions. 

            
            

            - **ReservedDBInstanceId** *(string) --* 

              The unique identifier for the reservation.

              
            

            - **ReservedDBInstancesOfferingId** *(string) --* 

              The offering identifier.

              
            

            - **DBInstanceClass** *(string) --* 

              The DB instance class for the reserved DB instance.

              
            

            - **StartTime** *(datetime) --* 

              The time the reservation started.

              
            

            - **Duration** *(integer) --* 

              The duration of the reservation in seconds.

              
            

            - **FixedPrice** *(float) --* 

              The fixed price charged for this reserved DB instance.

              
            

            - **UsagePrice** *(float) --* 

              The hourly price charged for this reserved DB instance.

              
            

            - **CurrencyCode** *(string) --* 

              The currency code for the reserved DB instance.

              
            

            - **DBInstanceCount** *(integer) --* 

              The number of reserved DB instances.

              
            

            - **ProductDescription** *(string) --* 

              The description of the reserved DB instance.

              
            

            - **OfferingType** *(string) --* 

              The offering type of this reserved DB instance.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates if the reservation applies to Multi-AZ deployments.

              
            

            - **State** *(string) --* 

              The state of the reserved DB instance.

              
            

            - **RecurringCharges** *(list) --* 

              The recurring price charged to run this reserved DB instance.

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeReservedDBInstances and  DescribeReservedDBInstancesOfferings actions. 

                
                

                - **RecurringChargeAmount** *(float) --* 

                  The amount of the recurring charge.

                  
                

                - **RecurringChargeFrequency** *(string) --* 

                  The frequency of the recurring charge.

                  
            
          
            

            - **ReservedDBInstanceArn** *(string) --* 

              The Amazon Resource Name (ARN) for the reserved DB instance.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DescribeReservedDBInstancesOfferings

  ::

    
    paginator = client.get_paginator('describe_reserved_db_instances_offerings')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.describe_reserved_db_instances_offerings`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          ReservedDBInstancesOfferingId='string',
          DBInstanceClass='string',
          Duration='string',
          ProductDescription='string',
          OfferingType='string',
          MultiAZ=True|False,
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
    :type ReservedDBInstancesOfferingId: string
    :param ReservedDBInstancesOfferingId: 

      The offering identifier filter value. Specify this parameter to show only the available offering that matches the specified reservation identifier.

       

      Example: ``438012d3-4052-4cc7-b2e3-8d3372e0e706``  

      

    
    :type DBInstanceClass: string
    :param DBInstanceClass: 

      The DB instance class filter value. Specify this parameter to show only the available offerings matching the specified DB instance class.

      

    
    :type Duration: string
    :param Duration: 

      Duration filter value, specified in years or seconds. Specify this parameter to show only reservations for this duration.

       

      Valid Values: ``1 | 3 | 31536000 | 94608000``  

      

    
    :type ProductDescription: string
    :param ProductDescription: 

      Product description filter value. Specify this parameter to show only the available offerings matching the specified product description.

      

    
    :type OfferingType: string
    :param OfferingType: 

      The offering type filter value. Specify this parameter to show only the available offerings matching the specified offering type.

       

      Valid Values: ``"Partial Upfront" | "All Upfront" | "No Upfront"``  

      

    
    :type MultiAZ: boolean
    :param MultiAZ: 

      The Multi-AZ filter value. Specify this parameter to show only the available offerings matching the specified Multi-AZ parameter.

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
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
            'ReservedDBInstancesOfferings': [
                {
                    'ReservedDBInstancesOfferingId': 'string',
                    'DBInstanceClass': 'string',
                    'Duration': 123,
                    'FixedPrice': 123.0,
                    'UsagePrice': 123.0,
                    'CurrencyCode': 'string',
                    'ProductDescription': 'string',
                    'OfferingType': 'string',
                    'MultiAZ': True|False,
                    'RecurringCharges': [
                        {
                            'RecurringChargeAmount': 123.0,
                            'RecurringChargeFrequency': 'string'
                        },
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the result of a successful invocation of the  DescribeReservedDBInstancesOfferings action. 

        
        

        - **ReservedDBInstancesOfferings** *(list) --* 

          A list of reserved DB instance offerings.

          
          

          - *(dict) --* 

            This data type is used as a response element in the  DescribeReservedDBInstancesOfferings action. 

            
            

            - **ReservedDBInstancesOfferingId** *(string) --* 

              The offering identifier.

              
            

            - **DBInstanceClass** *(string) --* 

              The DB instance class for the reserved DB instance.

              
            

            - **Duration** *(integer) --* 

              The duration of the offering in seconds.

              
            

            - **FixedPrice** *(float) --* 

              The fixed price charged for this offering.

              
            

            - **UsagePrice** *(float) --* 

              The hourly price charged for this offering.

              
            

            - **CurrencyCode** *(string) --* 

              The currency code for the reserved DB instance offering.

              
            

            - **ProductDescription** *(string) --* 

              The database engine used by the offering.

              
            

            - **OfferingType** *(string) --* 

              The offering type.

              
            

            - **MultiAZ** *(boolean) --* 

              Indicates if the offering applies to Multi-AZ deployments.

              
            

            - **RecurringCharges** *(list) --* 

              The recurring price charged to run this reserved DB instance.

              
              

              - *(dict) --* 

                This data type is used as a response element in the  DescribeReservedDBInstances and  DescribeReservedDBInstancesOfferings actions. 

                
                

                - **RecurringChargeAmount** *(float) --* 

                  The amount of the recurring charge.

                  
                

                - **RecurringChargeFrequency** *(string) --* 

                  The frequency of the recurring charge.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: RDS.Paginator.DownloadDBLogFilePortion

  ::

    
    paginator = client.get_paginator('download_db_log_file_portion')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`RDS.Client.download_db_log_file_portion`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          DBInstanceIdentifier='string',
          LogFileName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: **[REQUIRED]** 

      The customer-assigned name of the DB instance that contains the log files you want to list.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type LogFileName: string
    :param LogFileName: **[REQUIRED]** 

      The name of the log file to be downloaded.

      

    
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
            'LogFileData': 'string',
            'AdditionalDataPending': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This data type is used as a response element to  DownloadDBLogFilePortion .

        
        

        - **LogFileData** *(string) --* 

          Entries from the specified log file.

          
        

        - **AdditionalDataPending** *(boolean) --* 

          Boolean value that if true, indicates there is more data to be downloaded.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

=======
Waiters
=======


The available waiters are:

* :py:class:`RDS.Waiter.DBInstanceAvailable`


* :py:class:`RDS.Waiter.DBInstanceDeleted`


* :py:class:`RDS.Waiter.DBSnapshotCompleted`



.. py:class:: RDS.Waiter.DBInstanceAvailable

  ::

    
    waiter = client.get_waiter('db_instance_available')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`RDS.Client.describe_db_instances` every 30 seconds until a successful state is reached. An error is returned after 60 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          DBInstanceIdentifier='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: 

      The user-supplied instance identifier. If this parameter is specified, information from only the specific DB instance is returned. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBInstances`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :returns: None

.. py:class:: RDS.Waiter.DBInstanceDeleted

  ::

    
    waiter = client.get_waiter('db_instance_deleted')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`RDS.Client.describe_db_instances` every 30 seconds until a successful state is reached. An error is returned after 60 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          DBInstanceIdentifier='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string'
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: 

      The user-supplied instance identifier. If this parameter is specified, information from only the specific DB instance is returned. This parameter isn't case-sensitive.

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBInstances`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    
    :returns: None

.. py:class:: RDS.Waiter.DBSnapshotCompleted

  ::

    
    waiter = client.get_waiter('db_snapshot_completed')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`RDS.Client.describe_db_snapshots` every 15 seconds until a successful state is reached. An error is returned after 40 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          DBInstanceIdentifier='string',
          DBSnapshotIdentifier='string',
          SnapshotType='string',
          Filters=[
              {
                  'Name': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          MaxRecords=123,
          Marker='string',
          IncludeShared=True|False,
          IncludePublic=True|False
      )
    :type DBInstanceIdentifier: string
    :param DBInstanceIdentifier: 

      The ID of the DB instance to retrieve the list of DB snapshots for. This parameter cannot be used in conjunction with ``DBSnapshotIdentifier`` . This parameter is not case-sensitive. 

       

      Constraints:

       

       
      * Must contain from 1 to 63 alphanumeric characters or hyphens 
       
      * First character must be a letter 
       
      * Cannot end with a hyphen or contain two consecutive hyphens 
       

      

    
    :type DBSnapshotIdentifier: string
    :param DBSnapshotIdentifier: 

      A specific DB snapshot identifier to describe. This parameter cannot be used in conjunction with ``DBInstanceIdentifier`` . This value is stored as a lowercase string. 

       

      Constraints:

       

       
      * Must be 1 to 255 alphanumeric characters. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       
      * If this identifier is for an automated snapshot, the ``SnapshotType`` parameter must also be specified. 
       

      

    
    :type SnapshotType: string
    :param SnapshotType: 

      The type of snapshots to be returned. You can specify one of the following values:

       

       
      * ``automated`` - Return all DB snapshots that have been automatically taken by Amazon RDS for my AWS account. 
       
      * ``manual`` - Return all DB snapshots that have been taken by my AWS account. 
       
      * ``shared`` - Return all manual DB snapshots that have been shared to my AWS account. 
       
      * ``public`` - Return all DB snapshots that have been marked as public. 
       

       

      If you don't specify a ``SnapshotType`` value, then both automated and manual snapshots are returned. Shared and public DB snapshots are not included in the returned results by default. You can include shared snapshots with these results by setting the ``IncludeShared`` parameter to ``true`` . You can include public snapshots with these results by setting the ``IncludePublic`` parameter to ``true`` .

       

      The ``IncludeShared`` and ``IncludePublic`` parameters don't apply for ``SnapshotType`` values of ``manual`` or ``automated`` . The ``IncludePublic`` parameter doesn't apply when ``SnapshotType`` is set to ``shared`` . The ``IncludeShared`` parameter doesn't apply when ``SnapshotType`` is set to ``public`` .

      

    
    :type Filters: list
    :param Filters: 

      This parameter is not currently supported.

      

    
      - *(dict) --* 

        This type is not currently supported.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
        - **Values** *(list) --* **[REQUIRED]** 

          This parameter is not currently supported.

          

        
          - *(string) --* 

          
      
      
  
    :type MaxRecords: integer
    :param MaxRecords: 

      The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

       

      Default: 100

       

      Constraints: Minimum 20, maximum 100.

      

    
    :type Marker: string
    :param Marker: 

      An optional pagination token provided by a previous ``DescribeDBSnapshots`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

      

    
    :type IncludeShared: boolean
    :param IncludeShared: 

      Set this value to ``true`` to include shared manual DB snapshots from other AWS accounts that this AWS account has been given permission to copy or restore, otherwise set this value to ``false`` . The default is ``false`` .

       

      You can give an AWS account permission to restore a manual DB snapshot from another AWS account by using the  ModifyDBSnapshotAttribute API action.

      

    
    :type IncludePublic: boolean
    :param IncludePublic: 

      Set this value to ``true`` to include manual DB snapshots that are public and can be copied or restored by any AWS account, otherwise set this value to ``false`` . The default is ``false`` .

       

      You can share a manual DB snapshot as public by using the  ModifyDBSnapshotAttribute API.

      

    
    
    :returns: None