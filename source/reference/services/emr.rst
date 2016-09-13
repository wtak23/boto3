

.. _Tagging Amazon EMR Resources: http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/emr-plan-tags.html
.. _Launch a Job Flow on the MapR Distribution for Hadoop: http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/emr-mapr.html
.. _Amazon EMR Configurations: http://docs.aws.amazon.com/ElasticMapReduce/latest/API/EmrConfigurations.html
.. _AMI Versions Supported in Elastic MapReduce: http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/EnvironmentConfig_AMIVersion.html#ami-versions-supported
.. _Protecting a Job Flow from Termination: http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/UsingEMR_TerminationProtection.html
.. _Add More than 256 Steps to a Job Flow: http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/AddMoreThan256Steps.html
.. _Use Third Party Applications with Amazon EMR: http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/emr-supported-products.html


***
EMR
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: EMR.Client

  A low-level client representing Amazon Elastic MapReduce (EMR)::

    
    import boto3
    
    client = boto3.client('emr')

  
  These are the available methods:
  
  *   :py:meth:`add_instance_groups`

  
  *   :py:meth:`add_job_flow_steps`

  
  *   :py:meth:`add_tags`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`describe_cluster`

  
  *   :py:meth:`describe_job_flows`

  
  *   :py:meth:`describe_step`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_bootstrap_actions`

  
  *   :py:meth:`list_clusters`

  
  *   :py:meth:`list_instance_groups`

  
  *   :py:meth:`list_instances`

  
  *   :py:meth:`list_steps`

  
  *   :py:meth:`modify_instance_groups`

  
  *   :py:meth:`remove_tags`

  
  *   :py:meth:`run_job_flow`

  
  *   :py:meth:`set_termination_protection`

  
  *   :py:meth:`set_visible_to_all_users`

  
  *   :py:meth:`terminate_job_flows`

  

  .. py:method:: add_instance_groups(**kwargs)

    

    AddInstanceGroups adds an instance group to a running cluster.

    

    **Request Syntax** 
    ::

      response = client.add_instance_groups(
          InstanceGroups=[
              {
                  'Name': 'string',
                  'Market': 'ON_DEMAND'|'SPOT',
                  'InstanceRole': 'MASTER'|'CORE'|'TASK',
                  'BidPrice': 'string',
                  'InstanceType': 'string',
                  'InstanceCount': 123,
                  'Configurations': [
                      {
                          'Classification': 'string',
                          'Configurations': {'... recursive ...'},
                          'Properties': {
                              'string': 'string'
                          }
                      },
                  ],
                  'EbsConfiguration': {
                      'EbsBlockDeviceConfigs': [
                          {
                              'VolumeSpecification': {
                                  'VolumeType': 'string',
                                  'Iops': 123,
                                  'SizeInGB': 123
                              },
                              'VolumesPerInstance': 123
                          },
                      ],
                      'EbsOptimized': True|False
                  }
              },
          ],
          JobFlowId='string'
      )
    :type InstanceGroups: list
    :param InstanceGroups: **[REQUIRED]** 

      Instance Groups to add.

      

    
      - *(dict) --* 

        Configuration defining a new instance group.

        

      
        - **Name** *(string) --* 

          Friendly name given to the instance group.

          

        
        - **Market** *(string) --* 

          Market type of the Amazon EC2 instances used to create a cluster node.

          

        
        - **InstanceRole** *(string) --* **[REQUIRED]** 

          The role of the instance group in the cluster.

          

        
        - **BidPrice** *(string) --* 

          Bid price for each Amazon EC2 instance in the instance group when launching nodes as Spot Instances, expressed in USD.

          

        
        - **InstanceType** *(string) --* **[REQUIRED]** 

          The Amazon EC2 instance type for all instances in the instance group.

          

        
        - **InstanceCount** *(integer) --* **[REQUIRED]** 

          Target number of instances for the instance group.

          

        
        - **Configurations** *(list) --* 

          .. note::

             

            Amazon EMR releases 4.x or later.

             

           

          The list of configurations supplied for an EMR cluster instance group. You can specify a separate configuration for each instance group (master, core, and task).

          

        
          - *(dict) --* 

            .. note::

               

              Amazon EMR releases 4.x or later.

               

             

            Specifies a hardware and software configuration of the EMR cluster. This includes configurations for applications and software bundled with Amazon EMR. The Configuration object is a JSON object which is defined by a classification and a set of properties. Configurations can be nested, so a configuration may have its own Configuration objects listed.

            

          
            - **Classification** *(string) --* 

              The classification of a configuration. For more information see, `Amazon EMR Configurations`_ . 

              

            
            - **Configurations** *(list) --* 

              A list of configurations you apply to this configuration object.

              

            
            - **Properties** *(dict) --* 

              A set of properties supplied to the Configuration object.

              

            
              - *(string) --* 

              
                - *(string) --* 

                
          
        
          
      
        - **EbsConfiguration** *(dict) --* 

          EBS configurations that will be attached to each Amazon EC2 instance in the instance group.

          

        
          - **EbsBlockDeviceConfigs** *(list) --* 

          
            - *(dict) --* 

              Configuration of requested EBS block device associated with the instance group with count of volumes that will be associated to every instance.

              

            
              - **VolumeSpecification** *(dict) --* **[REQUIRED]** 

                EBS volume specifications such as volume type, IOPS, and size(GiB) that will be requested for the EBS volume attached to an EC2 instance in the cluster.

                

              
                - **VolumeType** *(string) --* **[REQUIRED]** 

                  The volume type. Volume types supported are gp2, io1, standard.

                  

                
                - **Iops** *(integer) --* 

                  The number of I/O operations per second (IOPS) that the volume supports.

                  

                
                - **SizeInGB** *(integer) --* **[REQUIRED]** 

                  The volume size, in gibibytes (GiB). This can be a number from 1 - 1024. If the volume type is EBS-optimized, the minimum value is 10.

                  

                
              
              - **VolumesPerInstance** *(integer) --* 

                Number of EBS volumes with specific volume configuration, that will be associated with every instance in the instance group

                

              
            
        
          - **EbsOptimized** *(boolean) --* 

          
        
      
  
    :type JobFlowId: string
    :param JobFlowId: **[REQUIRED]** 

      Job flow in which to add the instance groups.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'JobFlowId': 'string',
            'InstanceGroupIds': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Output from an AddInstanceGroups call.

        
        

        - **JobFlowId** *(string) --* 

          The job flow ID in which the instance groups are added.

          
        

        - **InstanceGroupIds** *(list) --* 

          Instance group IDs of the newly created instance groups.

          
          

          - *(string) --* 
      
    

  .. py:method:: add_job_flow_steps(**kwargs)

    

    AddJobFlowSteps adds new steps to a running job flow. A maximum of 256 steps are allowed in each job flow.

     

    If your job flow is long-running (such as a Hive data warehouse) or complex, you may require more than 256 steps to process your data. You can bypass the 256-step limitation in various ways, including using the SSH shell to connect to the master node and submitting queries directly to the software running on the master node, such as Hive and Hadoop. For more information on how to do this, go to `Add More than 256 Steps to a Job Flow`_ in the *Amazon Elastic MapReduce Developer's Guide* .

     

    A step specifies the location of a JAR file stored either on the master node of the job flow or in Amazon S3. Each step is performed by the main function of the main class of the JAR file. The main class can be specified either in the manifest of the JAR or by using the MainFunction parameter of the step.

     

    Elastic MapReduce executes each step in the order listed. For a step to be considered complete, the main function must exit with a zero exit code and all Hadoop jobs started while the step was running must have completed and run successfully.

     

    You can only add steps to a job flow that is in one of the following states: STARTING, BOOTSTRAPPING, RUNNING, or WAITING.

    

    **Request Syntax** 
    ::

      response = client.add_job_flow_steps(
          JobFlowId='string',
          Steps=[
              {
                  'Name': 'string',
                  'ActionOnFailure': 'TERMINATE_JOB_FLOW'|'TERMINATE_CLUSTER'|'CANCEL_AND_WAIT'|'CONTINUE',
                  'HadoopJarStep': {
                      'Properties': [
                          {
                              'Key': 'string',
                              'Value': 'string'
                          },
                      ],
                      'Jar': 'string',
                      'MainClass': 'string',
                      'Args': [
                          'string',
                      ]
                  }
              },
          ]
      )
    :type JobFlowId: string
    :param JobFlowId: **[REQUIRED]** 

      A string that uniquely identifies the job flow. This identifier is returned by  RunJobFlow and can also be obtained from  ListClusters . 

      

    
    :type Steps: list
    :param Steps: **[REQUIRED]** 

      A list of  StepConfig to be executed by the job flow. 

      

    
      - *(dict) --* 

        Specification of a job flow step.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the job flow step.

          

        
        - **ActionOnFailure** *(string) --* 

          The action to take if the job flow step fails.

          

        
        - **HadoopJarStep** *(dict) --* **[REQUIRED]** 

          The JAR file used for the job flow step.

          

        
          - **Properties** *(list) --* 

            A list of Java properties that are set when the step runs. You can use these properties to pass key value pairs to your main function.

            

          
            - *(dict) --* 

              A key value pair.

              

            
              - **Key** *(string) --* 

                The unique identifier of a key value pair.

                

              
              - **Value** *(string) --* 

                The value part of the identified key.

                

              
            
        
          - **Jar** *(string) --* **[REQUIRED]** 

            A path to a JAR file run during the step.

            

          
          - **MainClass** *(string) --* 

            The name of the main class in the specified Java file. If not specified, the JAR file should specify a Main-Class in its manifest file.

            

          
          - **Args** *(list) --* 

            A list of command line arguments passed to the JAR file's main function when executed.

            

          
            - *(string) --* 

            
        
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StepIds': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  AddJobFlowSteps operation. 

        
        

        - **StepIds** *(list) --* 

          The identifiers of the list of steps added to the job flow.

          
          

          - *(string) --* 
      
    

  .. py:method:: add_tags(**kwargs)

    

    Adds tags to an Amazon EMR resource. Tags make it easier to associate clusters in various ways, such as grouping clusters to track your Amazon EMR resource allocation costs. For more information, see `Tagging Amazon EMR Resources`_ . 

    

    **Request Syntax** 
    ::

      response = client.add_tags(
          ResourceId='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type ResourceId: string
    :param ResourceId: **[REQUIRED]** 

      The Amazon EMR resource identifier to which tags will be added. This value must be a cluster identifier.

      

    
    :type Tags: list
    :param Tags: **[REQUIRED]** 

      A list of tags to associate with a cluster and propagate to Amazon EC2 instances. Tags are user-defined key/value pairs that consist of a required key string with a maximum of 128 characters, and an optional value string with a maximum of 256 characters.

      

    
      - *(dict) --* 

        A key/value pair containing user-defined metadata that you can associate with an Amazon EMR resource. Tags make it easier to associate clusters in various ways, such as grouping clu\ sters to track your Amazon EMR resource allocation costs. For more information, see `Tagging Amazon EMR Resources`_ . 

        

      
        - **Key** *(string) --* 

          A user-defined key, which is the minimum required information for a valid tag. For more information, see `Tagging Amazon EMR Resources`_ . 

          

        
        - **Value** *(string) --* 

          A user-defined value, which is optional in a tag. For more information, see `Tagging Amazon EMR Resources`_ . 

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        This output indicates the result of adding tags to a resource.

        
    

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


  .. py:method:: describe_cluster(**kwargs)

    

    Provides cluster-level details including status, hardware and software configuration, VPC settings, and so on. For information about the cluster steps, see  ListSteps .

    

    **Request Syntax** 
    ::

      response = client.describe_cluster(
          ClusterId='string'
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The identifier of the cluster to describe.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Cluster': {
                'Id': 'string',
                'Name': 'string',
                'Status': {
                    'State': 'STARTING'|'BOOTSTRAPPING'|'RUNNING'|'WAITING'|'TERMINATING'|'TERMINATED'|'TERMINATED_WITH_ERRORS',
                    'StateChangeReason': {
                        'Code': 'INTERNAL_ERROR'|'VALIDATION_ERROR'|'INSTANCE_FAILURE'|'BOOTSTRAP_FAILURE'|'USER_REQUEST'|'STEP_FAILURE'|'ALL_STEPS_COMPLETED',
                        'Message': 'string'
                    },
                    'Timeline': {
                        'CreationDateTime': datetime(2015, 1, 1),
                        'ReadyDateTime': datetime(2015, 1, 1),
                        'EndDateTime': datetime(2015, 1, 1)
                    }
                },
                'Ec2InstanceAttributes': {
                    'Ec2KeyName': 'string',
                    'Ec2SubnetId': 'string',
                    'Ec2AvailabilityZone': 'string',
                    'IamInstanceProfile': 'string',
                    'EmrManagedMasterSecurityGroup': 'string',
                    'EmrManagedSlaveSecurityGroup': 'string',
                    'ServiceAccessSecurityGroup': 'string',
                    'AdditionalMasterSecurityGroups': [
                        'string',
                    ],
                    'AdditionalSlaveSecurityGroups': [
                        'string',
                    ]
                },
                'LogUri': 'string',
                'RequestedAmiVersion': 'string',
                'RunningAmiVersion': 'string',
                'ReleaseLabel': 'string',
                'AutoTerminate': True|False,
                'TerminationProtected': True|False,
                'VisibleToAllUsers': True|False,
                'Applications': [
                    {
                        'Name': 'string',
                        'Version': 'string',
                        'Args': [
                            'string',
                        ],
                        'AdditionalInfo': {
                            'string': 'string'
                        }
                    },
                ],
                'Tags': [
                    {
                        'Key': 'string',
                        'Value': 'string'
                    },
                ],
                'ServiceRole': 'string',
                'NormalizedInstanceHours': 123,
                'MasterPublicDnsName': 'string',
                'Configurations': [
                    {
                        'Classification': 'string',
                        'Configurations': {'... recursive ...'},
                        'Properties': {
                            'string': 'string'
                        }
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        This output contains the description of the cluster.

        
        

        - **Cluster** *(dict) --* 

          This output contains the details for the requested cluster.

          
          

          - **Id** *(string) --* 

            The unique identifier for the cluster.

            
          

          - **Name** *(string) --* 

            The name of the cluster.

            
          

          - **Status** *(dict) --* 

            The current status details about the cluster.

            
            

            - **State** *(string) --* 

              The current state of the cluster.

              
            

            - **StateChangeReason** *(dict) --* 

              The reason for the cluster status change.

              
              

              - **Code** *(string) --* 

                The programmatic code for the state change reason.

                
              

              - **Message** *(string) --* 

                The descriptive message for the state change reason.

                
          
            

            - **Timeline** *(dict) --* 

              A timeline that represents the status of a cluster over the lifetime of the cluster.

              
              

              - **CreationDateTime** *(datetime) --* 

                The creation date and time of the cluster.

                
              

              - **ReadyDateTime** *(datetime) --* 

                The date and time when the cluster was ready to execute steps.

                
              

              - **EndDateTime** *(datetime) --* 

                The date and time when the cluster was terminated.

                
          
        
          

          - **Ec2InstanceAttributes** *(dict) --* 

            Provides information about the EC2 instances in a cluster grouped by category. For example, key name, subnet ID, IAM instance profile, and so on.

            
            

            - **Ec2KeyName** *(string) --* 

              The name of the Amazon EC2 key pair to use when connecting with SSH into the master node as a user named "hadoop".

              
            

            - **Ec2SubnetId** *(string) --* 

              To launch the job flow in Amazon VPC, set this parameter to the identifier of the Amazon VPC subnet where you want the job flow to launch. If you do not specify this value, the job flow is launched in the normal AWS cloud, outside of a VPC.

               

              Amazon VPC currently does not support cluster compute quadruple extra large (cc1.4xlarge) instances. Thus, you cannot specify the cc1.4xlarge instance type for nodes of a job flow launched in a VPC.

              
            

            - **Ec2AvailabilityZone** *(string) --* 

              The Availability Zone in which the cluster will run.

              
            

            - **IamInstanceProfile** *(string) --* 

              The IAM role that was specified when the job flow was launched. The EC2 instances of the job flow assume this role.

              
            

            - **EmrManagedMasterSecurityGroup** *(string) --* 

              The identifier of the Amazon EC2 security group for the master node.

              
            

            - **EmrManagedSlaveSecurityGroup** *(string) --* 

              The identifier of the Amazon EC2 security group for the slave nodes.

              
            

            - **ServiceAccessSecurityGroup** *(string) --* 

              The identifier of the Amazon EC2 security group for the Amazon EMR service to access clusters in VPC private subnets.

              
            

            - **AdditionalMasterSecurityGroups** *(list) --* 

              A list of additional Amazon EC2 security group IDs for the master node.

              
              

              - *(string) --* 
          
            

            - **AdditionalSlaveSecurityGroups** *(list) --* 

              A list of additional Amazon EC2 security group IDs for the slave nodes.

              
              

              - *(string) --* 
          
        
          

          - **LogUri** *(string) --* 

            The path to the Amazon S3 location where logs for this cluster are stored.

            
          

          - **RequestedAmiVersion** *(string) --* 

            The AMI version requested for this cluster.

            
          

          - **RunningAmiVersion** *(string) --* 

            The AMI version running on this cluster.

            
          

          - **ReleaseLabel** *(string) --* 

            The release label for the Amazon EMR release. For Amazon EMR 3.x and 2.x AMIs, use amiVersion instead instead of ReleaseLabel.

            
          

          - **AutoTerminate** *(boolean) --* 

            Specifies whether the cluster should terminate after completing all steps.

            
          

          - **TerminationProtected** *(boolean) --* 

            Indicates whether Amazon EMR will lock the cluster to prevent the EC2 instances from being terminated by an API call or user intervention, or in the event of a cluster error.

            
          

          - **VisibleToAllUsers** *(boolean) --* 

            Indicates whether the job flow is visible to all IAM users of the AWS account associated with the job flow. If this value is set to ``true`` , all IAM users of that AWS account can view and manage the job flow if they have the proper policy permissions set. If this value is ``false`` , only the IAM user that created the cluster can view and manage it. This value can be changed using the  SetVisibleToAllUsers action.

            
          

          - **Applications** *(list) --* 

            The applications installed on this cluster.

            
            

            - *(dict) --* 

              An application is any Amazon or third-party software that you can add to the cluster. This structure contains a list of strings that indicates the software to use with the cluster and accepts a user argument list. Amazon EMR accepts and forwards the argument list to the corresponding installation script as bootstrap action argument. For more information, see `Launch a Job Flow on the MapR Distribution for Hadoop`_ . Currently supported values are:

               

               
              * "mapr-m3" - launch the job flow using MapR M3 Edition. 
               
              * "mapr-m5" - launch the job flow using MapR M5 Edition. 
               
              * "mapr" with the user arguments specifying "--edition,m3" or "--edition,m5" - launch the job flow using MapR M3 or M5 Edition, respectively. 
               

               

              .. note::

                 

                In Amazon EMR releases 4.0 and greater, the only accepted parameter is the application name. To pass arguments to applications, you supply a configuration for each application.

                 

              
              

              - **Name** *(string) --* 

                The name of the application.

                
              

              - **Version** *(string) --* 

                The version of the application.

                
              

              - **Args** *(list) --* 

                Arguments for Amazon EMR to pass to the application.

                
                

                - *(string) --* 
            
              

              - **AdditionalInfo** *(dict) --* 

                This option is for advanced users only. This is meta information about third-party applications that third-party vendors use for testing purposes.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
        
          

          - **Tags** *(list) --* 

            A list of tags associated with a cluster.

            
            

            - *(dict) --* 

              A key/value pair containing user-defined metadata that you can associate with an Amazon EMR resource. Tags make it easier to associate clusters in various ways, such as grouping clu\ sters to track your Amazon EMR resource allocation costs. For more information, see `Tagging Amazon EMR Resources`_ . 

              
              

              - **Key** *(string) --* 

                A user-defined key, which is the minimum required information for a valid tag. For more information, see `Tagging Amazon EMR Resources`_ . 

                
              

              - **Value** *(string) --* 

                A user-defined value, which is optional in a tag. For more information, see `Tagging Amazon EMR Resources`_ . 

                
          
        
          

          - **ServiceRole** *(string) --* 

            The IAM role that will be assumed by the Amazon EMR service to access AWS resources on your behalf.

            
          

          - **NormalizedInstanceHours** *(integer) --* 

            An approximation of the cost of the job flow, represented in m1.small/hours. This value is incremented one time for every hour an m1.small instance runs. Larger instances are weighted more, so an EC2 instance that is roughly four times more expensive would result in the normalized instance hours being incremented by four. This result is only an approximation and does not reflect the actual billing rate.

            
          

          - **MasterPublicDnsName** *(string) --* 

            The public DNS name of the master EC2 instance.

            
          

          - **Configurations** *(list) --* 

            .. note::

               

              Amazon EMR releases 4.x or later.

               

             

            The list of Configurations supplied to the EMR cluster.

            
            

            - *(dict) --* 

              .. note::

                 

                Amazon EMR releases 4.x or later.

                 

               

              Specifies a hardware and software configuration of the EMR cluster. This includes configurations for applications and software bundled with Amazon EMR. The Configuration object is a JSON object which is defined by a classification and a set of properties. Configurations can be nested, so a configuration may have its own Configuration objects listed.

              
              

              - **Classification** *(string) --* 

                The classification of a configuration. For more information see, `Amazon EMR Configurations`_ . 

                
              

              - **Configurations** *(list) --* 

                A list of configurations you apply to this configuration object.

                
              

              - **Properties** *(dict) --* 

                A set of properties supplied to the Configuration object.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
        
      
    

  .. py:method:: describe_job_flows(**kwargs)

    

    This API is deprecated and will eventually be removed. We recommend you use  ListClusters ,  DescribeCluster ,  ListSteps ,  ListInstanceGroups and  ListBootstrapActions instead.

     

    DescribeJobFlows returns a list of job flows that match all of the supplied parameters. The parameters can include a list of job flow IDs, job flow states, and restrictions on job flow creation date and time.

     

    Regardless of supplied parameters, only job flows created within the last two months are returned.

     

    If no parameters are supplied, then job flows matching either of the following criteria are returned:

     

     
    * Job flows created and completed in the last two weeks 
     
    * Job flows created within the last two months that are in one of the following states: ``RUNNING`` , ``WAITING`` , ``SHUTTING_DOWN`` , ``STARTING``   
     

     

    Amazon Elastic MapReduce can return a maximum of 512 job flow descriptions.

    

    **Request Syntax** 
    ::

      response = client.describe_job_flows(
          CreatedAfter=datetime(2015, 1, 1),
          CreatedBefore=datetime(2015, 1, 1),
          JobFlowIds=[
              'string',
          ],
          JobFlowStates=[
              'STARTING'|'BOOTSTRAPPING'|'RUNNING'|'WAITING'|'SHUTTING_DOWN'|'TERMINATED'|'COMPLETED'|'FAILED',
          ]
      )
    :type CreatedAfter: datetime
    :param CreatedAfter: 

      Return only job flows created after this date and time.

      

    
    :type CreatedBefore: datetime
    :param CreatedBefore: 

      Return only job flows created before this date and time.

      

    
    :type JobFlowIds: list
    :param JobFlowIds: 

      Return only job flows whose job flow ID is contained in this list.

      

    
      - *(string) --* 

      
  
    :type JobFlowStates: list
    :param JobFlowStates: 

      Return only job flows whose state is contained in this list.

      

    
      - *(string) --* 

        The type of instance.

        

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'JobFlows': [
                {
                    'JobFlowId': 'string',
                    'Name': 'string',
                    'LogUri': 'string',
                    'AmiVersion': 'string',
                    'ExecutionStatusDetail': {
                        'State': 'STARTING'|'BOOTSTRAPPING'|'RUNNING'|'WAITING'|'SHUTTING_DOWN'|'TERMINATED'|'COMPLETED'|'FAILED',
                        'CreationDateTime': datetime(2015, 1, 1),
                        'StartDateTime': datetime(2015, 1, 1),
                        'ReadyDateTime': datetime(2015, 1, 1),
                        'EndDateTime': datetime(2015, 1, 1),
                        'LastStateChangeReason': 'string'
                    },
                    'Instances': {
                        'MasterInstanceType': 'string',
                        'MasterPublicDnsName': 'string',
                        'MasterInstanceId': 'string',
                        'SlaveInstanceType': 'string',
                        'InstanceCount': 123,
                        'InstanceGroups': [
                            {
                                'InstanceGroupId': 'string',
                                'Name': 'string',
                                'Market': 'ON_DEMAND'|'SPOT',
                                'InstanceRole': 'MASTER'|'CORE'|'TASK',
                                'BidPrice': 'string',
                                'InstanceType': 'string',
                                'InstanceRequestCount': 123,
                                'InstanceRunningCount': 123,
                                'State': 'PROVISIONING'|'BOOTSTRAPPING'|'RUNNING'|'RESIZING'|'SUSPENDED'|'TERMINATING'|'TERMINATED'|'ARRESTED'|'SHUTTING_DOWN'|'ENDED',
                                'LastStateChangeReason': 'string',
                                'CreationDateTime': datetime(2015, 1, 1),
                                'StartDateTime': datetime(2015, 1, 1),
                                'ReadyDateTime': datetime(2015, 1, 1),
                                'EndDateTime': datetime(2015, 1, 1)
                            },
                        ],
                        'NormalizedInstanceHours': 123,
                        'Ec2KeyName': 'string',
                        'Ec2SubnetId': 'string',
                        'Placement': {
                            'AvailabilityZone': 'string'
                        },
                        'KeepJobFlowAliveWhenNoSteps': True|False,
                        'TerminationProtected': True|False,
                        'HadoopVersion': 'string'
                    },
                    'Steps': [
                        {
                            'StepConfig': {
                                'Name': 'string',
                                'ActionOnFailure': 'TERMINATE_JOB_FLOW'|'TERMINATE_CLUSTER'|'CANCEL_AND_WAIT'|'CONTINUE',
                                'HadoopJarStep': {
                                    'Properties': [
                                        {
                                            'Key': 'string',
                                            'Value': 'string'
                                        },
                                    ],
                                    'Jar': 'string',
                                    'MainClass': 'string',
                                    'Args': [
                                        'string',
                                    ]
                                }
                            },
                            'ExecutionStatusDetail': {
                                'State': 'PENDING'|'RUNNING'|'CONTINUE'|'COMPLETED'|'CANCELLED'|'FAILED'|'INTERRUPTED',
                                'CreationDateTime': datetime(2015, 1, 1),
                                'StartDateTime': datetime(2015, 1, 1),
                                'EndDateTime': datetime(2015, 1, 1),
                                'LastStateChangeReason': 'string'
                            }
                        },
                    ],
                    'BootstrapActions': [
                        {
                            'BootstrapActionConfig': {
                                'Name': 'string',
                                'ScriptBootstrapAction': {
                                    'Path': 'string',
                                    'Args': [
                                        'string',
                                    ]
                                }
                            }
                        },
                    ],
                    'SupportedProducts': [
                        'string',
                    ],
                    'VisibleToAllUsers': True|False,
                    'JobFlowRole': 'string',
                    'ServiceRole': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the  DescribeJobFlows operation. 

        
        

        - **JobFlows** *(list) --* 

          A list of job flows matching the parameters supplied.

          
          

          - *(dict) --* 

            A description of a job flow.

            
            

            - **JobFlowId** *(string) --* 

              The job flow identifier.

              
            

            - **Name** *(string) --* 

              The name of the job flow.

              
            

            - **LogUri** *(string) --* 

              The location in Amazon S3 where log files for the job are stored.

              
            

            - **AmiVersion** *(string) --* 

              The version of the AMI used to initialize Amazon EC2 instances in the job flow. For a list of AMI versions currently supported by Amazon ElasticMapReduce, go to `AMI Versions Supported in Elastic MapReduce`_ in the *Amazon Elastic MapReduce Developer Guide.*  

              
            

            - **ExecutionStatusDetail** *(dict) --* 

              Describes the execution status of the job flow.

              
              

              - **State** *(string) --* 

                The state of the job flow.

                
              

              - **CreationDateTime** *(datetime) --* 

                The creation date and time of the job flow.

                
              

              - **StartDateTime** *(datetime) --* 

                The start date and time of the job flow.

                
              

              - **ReadyDateTime** *(datetime) --* 

                The date and time when the job flow was ready to start running bootstrap actions.

                
              

              - **EndDateTime** *(datetime) --* 

                The completion date and time of the job flow.

                
              

              - **LastStateChangeReason** *(string) --* 

                Description of the job flow last changed state.

                
          
            

            - **Instances** *(dict) --* 

              Describes the Amazon EC2 instances of the job flow.

              
              

              - **MasterInstanceType** *(string) --* 

                The Amazon EC2 master node instance type.

                
              

              - **MasterPublicDnsName** *(string) --* 

                The DNS name of the master node.

                
              

              - **MasterInstanceId** *(string) --* 

                The Amazon EC2 instance identifier of the master node.

                
              

              - **SlaveInstanceType** *(string) --* 

                The Amazon EC2 slave node instance type.

                
              

              - **InstanceCount** *(integer) --* 

                The number of Amazon EC2 instances in the cluster. If the value is 1, the same instance serves as both the master and slave node. If the value is greater than 1, one instance is the master node and all others are slave nodes.

                
              

              - **InstanceGroups** *(list) --* 

                Details about the job flow's instance groups.

                
                

                - *(dict) --* 

                  Detailed information about an instance group.

                  
                  

                  - **InstanceGroupId** *(string) --* 

                    Unique identifier for the instance group.

                    
                  

                  - **Name** *(string) --* 

                    Friendly name for the instance group.

                    
                  

                  - **Market** *(string) --* 

                    Market type of the Amazon EC2 instances used to create a cluster node.

                    
                  

                  - **InstanceRole** *(string) --* 

                    Instance group role in the cluster

                    
                  

                  - **BidPrice** *(string) --* 

                    Bid price for EC2 Instances when launching nodes as Spot Instances, expressed in USD.

                    
                  

                  - **InstanceType** *(string) --* 

                    Amazon EC2 Instance type.

                    
                  

                  - **InstanceRequestCount** *(integer) --* 

                    Target number of instances to run in the instance group.

                    
                  

                  - **InstanceRunningCount** *(integer) --* 

                    Actual count of running instances.

                    
                  

                  - **State** *(string) --* 

                    State of instance group. The following values are deprecated: STARTING, TERMINATED, and FAILED.

                    
                  

                  - **LastStateChangeReason** *(string) --* 

                    Details regarding the state of the instance group.

                    
                  

                  - **CreationDateTime** *(datetime) --* 

                    The date/time the instance group was created.

                    
                  

                  - **StartDateTime** *(datetime) --* 

                    The date/time the instance group was started.

                    
                  

                  - **ReadyDateTime** *(datetime) --* 

                    The date/time the instance group was available to the cluster.

                    
                  

                  - **EndDateTime** *(datetime) --* 

                    The date/time the instance group was terminated.

                    
              
            
              

              - **NormalizedInstanceHours** *(integer) --* 

                An approximation of the cost of the job flow, represented in m1.small/hours. This value is incremented once for every hour an m1.small runs. Larger instances are weighted more, so an Amazon EC2 instance that is roughly four times more expensive would result in the normalized instance hours being incremented by four. This result is only an approximation and does not reflect the actual billing rate.

                
              

              - **Ec2KeyName** *(string) --* 

                The name of an Amazon EC2 key pair that can be used to ssh to the master node of job flow.

                
              

              - **Ec2SubnetId** *(string) --* 

                For job flows launched within Amazon Virtual Private Cloud, this value specifies the identifier of the subnet where the job flow was launched.

                
              

              - **Placement** *(dict) --* 

                The Amazon EC2 Availability Zone for the job flow.

                
                

                - **AvailabilityZone** *(string) --* 

                  The Amazon EC2 Availability Zone for the job flow.

                  
            
              

              - **KeepJobFlowAliveWhenNoSteps** *(boolean) --* 

                Specifies whether the job flow should terminate after completing all steps.

                
              

              - **TerminationProtected** *(boolean) --* 

                Specifies whether the Amazon EC2 instances in the cluster are protected from termination by API calls, user intervention, or in the event of a job flow error.

                
              

              - **HadoopVersion** *(string) --* 

                The Hadoop version for the job flow.

                
          
            

            - **Steps** *(list) --* 

              A list of steps run by the job flow.

              
              

              - *(dict) --* 

                Combines the execution state and configuration of a step.

                
                

                - **StepConfig** *(dict) --* 

                  The step configuration.

                  
                  

                  - **Name** *(string) --* 

                    The name of the job flow step.

                    
                  

                  - **ActionOnFailure** *(string) --* 

                    The action to take if the job flow step fails.

                    
                  

                  - **HadoopJarStep** *(dict) --* 

                    The JAR file used for the job flow step.

                    
                    

                    - **Properties** *(list) --* 

                      A list of Java properties that are set when the step runs. You can use these properties to pass key value pairs to your main function.

                      
                      

                      - *(dict) --* 

                        A key value pair.

                        
                        

                        - **Key** *(string) --* 

                          The unique identifier of a key value pair.

                          
                        

                        - **Value** *(string) --* 

                          The value part of the identified key.

                          
                    
                  
                    

                    - **Jar** *(string) --* 

                      A path to a JAR file run during the step.

                      
                    

                    - **MainClass** *(string) --* 

                      The name of the main class in the specified Java file. If not specified, the JAR file should specify a Main-Class in its manifest file.

                      
                    

                    - **Args** *(list) --* 

                      A list of command line arguments passed to the JAR file's main function when executed.

                      
                      

                      - *(string) --* 
                  
                
              
                

                - **ExecutionStatusDetail** *(dict) --* 

                  The description of the step status.

                  
                  

                  - **State** *(string) --* 

                    The state of the job flow step.

                    
                  

                  - **CreationDateTime** *(datetime) --* 

                    The creation date and time of the step.

                    
                  

                  - **StartDateTime** *(datetime) --* 

                    The start date and time of the step.

                    
                  

                  - **EndDateTime** *(datetime) --* 

                    The completion date and time of the step.

                    
                  

                  - **LastStateChangeReason** *(string) --* 

                    A description of the step's current state.

                    
              
            
          
            

            - **BootstrapActions** *(list) --* 

              A list of the bootstrap actions run by the job flow.

              
              

              - *(dict) --* 

                Reports the configuration of a bootstrap action in a job flow.

                
                

                - **BootstrapActionConfig** *(dict) --* 

                  A description of the bootstrap action.

                  
                  

                  - **Name** *(string) --* 

                    The name of the bootstrap action.

                    
                  

                  - **ScriptBootstrapAction** *(dict) --* 

                    The script run by the bootstrap action.

                    
                    

                    - **Path** *(string) --* 

                      Location of the script to run during a bootstrap action. Can be either a location in Amazon S3 or on a local file system.

                      
                    

                    - **Args** *(list) --* 

                      A list of command line arguments to pass to the bootstrap action script.

                      
                      

                      - *(string) --* 
                  
                
              
            
          
            

            - **SupportedProducts** *(list) --* 

              A list of strings set by third party software when the job flow is launched. If you are not using third party software to manage the job flow this value is empty.

              
              

              - *(string) --* 
          
            

            - **VisibleToAllUsers** *(boolean) --* 

              Specifies whether the job flow is visible to all IAM users of the AWS account associated with the job flow. If this value is set to ``true`` , all IAM users of that AWS account can view and (if they have the proper policy permissions set) manage the job flow. If it is set to ``false`` , only the IAM user that created the job flow can view and manage it. This value can be changed using the  SetVisibleToAllUsers action.

              
            

            - **JobFlowRole** *(string) --* 

              The IAM role that was specified when the job flow was launched. The EC2 instances of the job flow assume this role.

              
            

            - **ServiceRole** *(string) --* 

              The IAM role that will be assumed by the Amazon EMR service to access AWS resources on your behalf.

              
        
      
    

  .. py:method:: describe_step(**kwargs)

    

    Provides more detail about the cluster step.

    

    **Request Syntax** 
    ::

      response = client.describe_step(
          ClusterId='string',
          StepId='string'
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The identifier of the cluster with steps to describe.

      

    
    :type StepId: string
    :param StepId: **[REQUIRED]** 

      The identifier of the step to describe.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Step': {
                'Id': 'string',
                'Name': 'string',
                'Config': {
                    'Jar': 'string',
                    'Properties': {
                        'string': 'string'
                    },
                    'MainClass': 'string',
                    'Args': [
                        'string',
                    ]
                },
                'ActionOnFailure': 'TERMINATE_JOB_FLOW'|'TERMINATE_CLUSTER'|'CANCEL_AND_WAIT'|'CONTINUE',
                'Status': {
                    'State': 'PENDING'|'RUNNING'|'COMPLETED'|'CANCELLED'|'FAILED'|'INTERRUPTED',
                    'StateChangeReason': {
                        'Code': 'NONE',
                        'Message': 'string'
                    },
                    'FailureDetails': {
                        'Reason': 'string',
                        'Message': 'string',
                        'LogFile': 'string'
                    },
                    'Timeline': {
                        'CreationDateTime': datetime(2015, 1, 1),
                        'StartDateTime': datetime(2015, 1, 1),
                        'EndDateTime': datetime(2015, 1, 1)
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        This output contains the description of the cluster step.

        
        

        - **Step** *(dict) --* 

          The step details for the requested step identifier.

          
          

          - **Id** *(string) --* 

            The identifier of the cluster step.

            
          

          - **Name** *(string) --* 

            The name of the cluster step.

            
          

          - **Config** *(dict) --* 

            The Hadoop job configuration of the cluster step.

            
            

            - **Jar** *(string) --* 

              The path to the JAR file that runs during the step.

              
            

            - **Properties** *(dict) --* 

              The list of Java properties that are set when the step runs. You can use these properties to pass key value pairs to your main function.

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
            

            - **MainClass** *(string) --* 

              The name of the main class in the specified Java file. If not specified, the JAR file should specify a main class in its manifest file.

              
            

            - **Args** *(list) --* 

              The list of command line arguments to pass to the JAR file's main function for execution.

              
              

              - *(string) --* 
          
        
          

          - **ActionOnFailure** *(string) --* 

            This specifies what action to take when the cluster step fails. Possible values are TERMINATE_CLUSTER, CANCEL_AND_WAIT, and CONTINUE.

            
          

          - **Status** *(dict) --* 

            The current execution status details of the cluster step.

            
            

            - **State** *(string) --* 

              The execution state of the cluster step.

              
            

            - **StateChangeReason** *(dict) --* 

              The reason for the step execution status change.

              
              

              - **Code** *(string) --* 

                The programmable code for the state change reason. Note: Currently, the service provides no code for the state change.

                
              

              - **Message** *(string) --* 

                The descriptive message for the state change reason.

                
          
            

            - **FailureDetails** *(dict) --* 

              The details for the step failure including reason, message, and log file path where the root cause was identified.

              
              

              - **Reason** *(string) --* 

                The reason for the step failure. In the case where the service cannot successfully determine the root cause of the failure, it returns "Unknown Error" as a reason.

                
              

              - **Message** *(string) --* 

                The descriptive message including the error the EMR service has identified as the cause of step failure. This is text from an error log that describes the root cause of the failure.

                
              

              - **LogFile** *(string) --* 

                The path to the log file where the step failure root cause was originally recorded.

                
          
            

            - **Timeline** *(dict) --* 

              The timeline of the cluster step status over time.

              
              

              - **CreationDateTime** *(datetime) --* 

                The date and time when the cluster step was created.

                
              

              - **StartDateTime** *(datetime) --* 

                The date and time when the cluster step execution started.

                
              

              - **EndDateTime** *(datetime) --* 

                The date and time when the cluster step execution completed or failed.

                
          
        
      
    

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

        


  .. py:method:: list_bootstrap_actions(**kwargs)

    

    Provides information about the bootstrap actions associated with a cluster.

    

    **Request Syntax** 
    ::

      response = client.list_bootstrap_actions(
          ClusterId='string',
          Marker='string'
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The cluster identifier for the bootstrap actions to list .

      

    
    :type Marker: string
    :param Marker: 

      The pagination token that indicates the next set of results to retrieve .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'BootstrapActions': [
                {
                    'Name': 'string',
                    'ScriptPath': 'string',
                    'Args': [
                        'string',
                    ]
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This output contains the boostrap actions detail .

        
        

        - **BootstrapActions** *(list) --* 

          The bootstrap actions associated with the cluster .

          
          

          - *(dict) --* 

            An entity describing an executable that runs on a cluster.

            
            

            - **Name** *(string) --* 

              The name of the command.

              
            

            - **ScriptPath** *(string) --* 

              The Amazon S3 location of the command script.

              
            

            - **Args** *(list) --* 

              Arguments for Amazon EMR to pass to the command for execution.

              
              

              - *(string) --* 
          
        
      
        

        - **Marker** *(string) --* 

          The pagination token that indicates the next set of results to retrieve .

          
    

  .. py:method:: list_clusters(**kwargs)

    

    Provides the status of all clusters visible to this AWS account. Allows you to filter the list of clusters based on certain criteria; for example, filtering by cluster creation date and time or by status. This call returns a maximum of 50 clusters per call, but returns a marker to track the paging of the cluster list across multiple ListClusters calls.

    

    **Request Syntax** 
    ::

      response = client.list_clusters(
          CreatedAfter=datetime(2015, 1, 1),
          CreatedBefore=datetime(2015, 1, 1),
          ClusterStates=[
              'STARTING'|'BOOTSTRAPPING'|'RUNNING'|'WAITING'|'TERMINATING'|'TERMINATED'|'TERMINATED_WITH_ERRORS',
          ],
          Marker='string'
      )
    :type CreatedAfter: datetime
    :param CreatedAfter: 

      The creation date and time beginning value filter for listing clusters .

      

    
    :type CreatedBefore: datetime
    :param CreatedBefore: 

      The creation date and time end value filter for listing clusters .

      

    
    :type ClusterStates: list
    :param ClusterStates: 

      The cluster state filters to apply when listing clusters.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      The pagination token that indicates the next set of results to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Clusters': [
                {
                    'Id': 'string',
                    'Name': 'string',
                    'Status': {
                        'State': 'STARTING'|'BOOTSTRAPPING'|'RUNNING'|'WAITING'|'TERMINATING'|'TERMINATED'|'TERMINATED_WITH_ERRORS',
                        'StateChangeReason': {
                            'Code': 'INTERNAL_ERROR'|'VALIDATION_ERROR'|'INSTANCE_FAILURE'|'BOOTSTRAP_FAILURE'|'USER_REQUEST'|'STEP_FAILURE'|'ALL_STEPS_COMPLETED',
                            'Message': 'string'
                        },
                        'Timeline': {
                            'CreationDateTime': datetime(2015, 1, 1),
                            'ReadyDateTime': datetime(2015, 1, 1),
                            'EndDateTime': datetime(2015, 1, 1)
                        }
                    },
                    'NormalizedInstanceHours': 123
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This contains a ClusterSummaryList with the cluster details; for example, the cluster IDs, names, and status.

        
        

        - **Clusters** *(list) --* 

          The list of clusters for the account based on the given filters.

          
          

          - *(dict) --* 

            The summary description of the cluster.

            
            

            - **Id** *(string) --* 

              The unique identifier for the cluster.

              
            

            - **Name** *(string) --* 

              The name of the cluster.

              
            

            - **Status** *(dict) --* 

              The details about the current status of the cluster.

              
              

              - **State** *(string) --* 

                The current state of the cluster.

                
              

              - **StateChangeReason** *(dict) --* 

                The reason for the cluster status change.

                
                

                - **Code** *(string) --* 

                  The programmatic code for the state change reason.

                  
                

                - **Message** *(string) --* 

                  The descriptive message for the state change reason.

                  
            
              

              - **Timeline** *(dict) --* 

                A timeline that represents the status of a cluster over the lifetime of the cluster.

                
                

                - **CreationDateTime** *(datetime) --* 

                  The creation date and time of the cluster.

                  
                

                - **ReadyDateTime** *(datetime) --* 

                  The date and time when the cluster was ready to execute steps.

                  
                

                - **EndDateTime** *(datetime) --* 

                  The date and time when the cluster was terminated.

                  
            
          
            

            - **NormalizedInstanceHours** *(integer) --* 

              An approximation of the cost of the job flow, represented in m1.small/hours. This value is incremented one time for every hour an m1.small instance runs. Larger instances are weighted more, so an EC2 instance that is roughly four times more expensive would result in the normalized instance hours being incremented by four. This result is only an approximation and does not reflect the actual billing rate.

              
        
      
        

        - **Marker** *(string) --* 

          The pagination token that indicates the next set of results to retrieve.

          
    

  .. py:method:: list_instance_groups(**kwargs)

    

    Provides all available details about the instance groups in a cluster.

    

    **Request Syntax** 
    ::

      response = client.list_instance_groups(
          ClusterId='string',
          Marker='string'
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The identifier of the cluster for which to list the instance groups.

      

    
    :type Marker: string
    :param Marker: 

      The pagination token that indicates the next set of results to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'InstanceGroups': [
                {
                    'Id': 'string',
                    'Name': 'string',
                    'Market': 'ON_DEMAND'|'SPOT',
                    'InstanceGroupType': 'MASTER'|'CORE'|'TASK',
                    'BidPrice': 'string',
                    'InstanceType': 'string',
                    'RequestedInstanceCount': 123,
                    'RunningInstanceCount': 123,
                    'Status': {
                        'State': 'PROVISIONING'|'BOOTSTRAPPING'|'RUNNING'|'RESIZING'|'SUSPENDED'|'TERMINATING'|'TERMINATED'|'ARRESTED'|'SHUTTING_DOWN'|'ENDED',
                        'StateChangeReason': {
                            'Code': 'INTERNAL_ERROR'|'VALIDATION_ERROR'|'INSTANCE_FAILURE'|'CLUSTER_TERMINATED',
                            'Message': 'string'
                        },
                        'Timeline': {
                            'CreationDateTime': datetime(2015, 1, 1),
                            'ReadyDateTime': datetime(2015, 1, 1),
                            'EndDateTime': datetime(2015, 1, 1)
                        }
                    },
                    'Configurations': [
                        {
                            'Classification': 'string',
                            'Configurations': {'... recursive ...'},
                            'Properties': {
                                'string': 'string'
                            }
                        },
                    ],
                    'EbsBlockDevices': [
                        {
                            'VolumeSpecification': {
                                'VolumeType': 'string',
                                'Iops': 123,
                                'SizeInGB': 123
                            },
                            'Device': 'string'
                        },
                    ],
                    'EbsOptimized': True|False,
                    'ShrinkPolicy': {
                        'DecommissionTimeout': 123,
                        'InstanceResizePolicy': {
                            'InstancesToTerminate': [
                                'string',
                            ],
                            'InstancesToProtect': [
                                'string',
                            ],
                            'InstanceTerminationTimeout': 123
                        }
                    }
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This input determines which instance groups to retrieve.

        
        

        - **InstanceGroups** *(list) --* 

          The list of instance groups for the cluster and given filters.

          
          

          - *(dict) --* 

            This entity represents an instance group, which is a group of instances that have common purpose. For example, CORE instance group is used for HDFS.

            
            

            - **Id** *(string) --* 

              The identifier of the instance group.

              
            

            - **Name** *(string) --* 

              The name of the instance group.

              
            

            - **Market** *(string) --* 

              The marketplace to provision instances for this group. Valid values are ON_DEMAND or SPOT.

              
            

            - **InstanceGroupType** *(string) --* 

              The type of the instance group. Valid values are MASTER, CORE or TASK.

              
            

            - **BidPrice** *(string) --* 

              The bid price for each EC2 instance in the instance group when launching nodes as Spot Instances, expressed in USD.

              
            

            - **InstanceType** *(string) --* 

              The EC2 instance type for all instances in the instance group.

              
            

            - **RequestedInstanceCount** *(integer) --* 

              The target number of instances for the instance group.

              
            

            - **RunningInstanceCount** *(integer) --* 

              The number of instances currently running in this instance group.

              
            

            - **Status** *(dict) --* 

              The current status of the instance group.

              
              

              - **State** *(string) --* 

                The current state of the instance group.

                
              

              - **StateChangeReason** *(dict) --* 

                The status change reason details for the instance group.

                
                

                - **Code** *(string) --* 

                  The programmable code for the state change reason.

                  
                

                - **Message** *(string) --* 

                  The status change reason description.

                  
            
              

              - **Timeline** *(dict) --* 

                The timeline of the instance group status over time.

                
                

                - **CreationDateTime** *(datetime) --* 

                  The creation date and time of the instance group.

                  
                

                - **ReadyDateTime** *(datetime) --* 

                  The date and time when the instance group became ready to perform tasks.

                  
                

                - **EndDateTime** *(datetime) --* 

                  The date and time when the instance group terminated.

                  
            
          
            

            - **Configurations** *(list) --* 

              .. note::

                 

                Amazon EMR releases 4.x or later.

                 

               

              The list of configurations supplied for an EMR cluster instance group. You can specify a separate configuration for each instance group (master, core, and task).

              
              

              - *(dict) --* 

                .. note::

                   

                  Amazon EMR releases 4.x or later.

                   

                 

                Specifies a hardware and software configuration of the EMR cluster. This includes configurations for applications and software bundled with Amazon EMR. The Configuration object is a JSON object which is defined by a classification and a set of properties. Configurations can be nested, so a configuration may have its own Configuration objects listed.

                
                

                - **Classification** *(string) --* 

                  The classification of a configuration. For more information see, `Amazon EMR Configurations`_ . 

                  
                

                - **Configurations** *(list) --* 

                  A list of configurations you apply to this configuration object.

                  
                

                - **Properties** *(dict) --* 

                  A set of properties supplied to the Configuration object.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
          
            

            - **EbsBlockDevices** *(list) --* 

              The EBS block devices that are mapped to this instance group.

              
              

              - *(dict) --* 

                Configuration of requested EBS block device associated with the instance group.

                
                

                - **VolumeSpecification** *(dict) --* 

                  EBS volume specifications such as volume type, IOPS, and size(GiB) that will be requested for the EBS volume attached to an EC2 instance in the cluster.

                  
                  

                  - **VolumeType** *(string) --* 

                    The volume type. Volume types supported are gp2, io1, standard.

                    
                  

                  - **Iops** *(integer) --* 

                    The number of I/O operations per second (IOPS) that the volume supports.

                    
                  

                  - **SizeInGB** *(integer) --* 

                    The volume size, in gibibytes (GiB). This can be a number from 1 - 1024. If the volume type is EBS-optimized, the minimum value is 10.

                    
              
                

                - **Device** *(string) --* 

                  The device name that is exposed to the instance, such as /dev/sdh.

                  
            
          
            

            - **EbsOptimized** *(boolean) --* 

              If the instance group is EBS-optimized. An Amazon EBS-optimized instance uses an optimized configuration stack and provides additional, dedicated capacity for Amazon EBS I/O.

              
            

            - **ShrinkPolicy** *(dict) --* 

              Policy for customizing shrink operations.

              
              

              - **DecommissionTimeout** *(integer) --* 

                The desired timeout for decommissioning an instance. Overrides the default YARN decommissioning timeout.

                
              

              - **InstanceResizePolicy** *(dict) --* 

                Custom policy for requesting termination protection or termination of specific instances when shrinking an instance group.

                
                

                - **InstancesToTerminate** *(list) --* 

                  Specific list of instances to be terminated when shrinking an instance group.

                  
                  

                  - *(string) --* 
              
                

                - **InstancesToProtect** *(list) --* 

                  Specific list of instances to be protected when shrinking an instance group.

                  
                  

                  - *(string) --* 
              
                

                - **InstanceTerminationTimeout** *(integer) --* 

                  Decommissioning timeout override for the specific list of instances to be terminated.

                  
            
          
        
      
        

        - **Marker** *(string) --* 

          The pagination token that indicates the next set of results to retrieve.

          
    

  .. py:method:: list_instances(**kwargs)

    

    Provides information about the cluster instances that Amazon EMR provisions on behalf of a user when it creates the cluster. For example, this operation indicates when the EC2 instances reach the Ready state, when instances become available to Amazon EMR to use for jobs, and the IP addresses for cluster instances, etc.

    

    **Request Syntax** 
    ::

      response = client.list_instances(
          ClusterId='string',
          InstanceGroupId='string',
          InstanceGroupTypes=[
              'MASTER'|'CORE'|'TASK',
          ],
          InstanceStates=[
              'AWAITING_FULFILLMENT'|'PROVISIONING'|'BOOTSTRAPPING'|'RUNNING'|'TERMINATED',
          ],
          Marker='string'
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The identifier of the cluster for which to list the instances.

      

    
    :type InstanceGroupId: string
    :param InstanceGroupId: 

      The identifier of the instance group for which to list the instances.

      

    
    :type InstanceGroupTypes: list
    :param InstanceGroupTypes: 

      The type of instance group for which to list the instances.

      

    
      - *(string) --* 

      
  
    :type InstanceStates: list
    :param InstanceStates: 

      A list of instance states that will filter the instances returned with this request.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      The pagination token that indicates the next set of results to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Instances': [
                {
                    'Id': 'string',
                    'Ec2InstanceId': 'string',
                    'PublicDnsName': 'string',
                    'PublicIpAddress': 'string',
                    'PrivateDnsName': 'string',
                    'PrivateIpAddress': 'string',
                    'Status': {
                        'State': 'AWAITING_FULFILLMENT'|'PROVISIONING'|'BOOTSTRAPPING'|'RUNNING'|'TERMINATED',
                        'StateChangeReason': {
                            'Code': 'INTERNAL_ERROR'|'VALIDATION_ERROR'|'INSTANCE_FAILURE'|'BOOTSTRAP_FAILURE'|'CLUSTER_TERMINATED',
                            'Message': 'string'
                        },
                        'Timeline': {
                            'CreationDateTime': datetime(2015, 1, 1),
                            'ReadyDateTime': datetime(2015, 1, 1),
                            'EndDateTime': datetime(2015, 1, 1)
                        }
                    },
                    'InstanceGroupId': 'string',
                    'EbsVolumes': [
                        {
                            'Device': 'string',
                            'VolumeId': 'string'
                        },
                    ]
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This output contains the list of instances.

        
        

        - **Instances** *(list) --* 

          The list of instances for the cluster and given filters.

          
          

          - *(dict) --* 

            Represents an EC2 instance provisioned as part of cluster.

            
            

            - **Id** *(string) --* 

              The unique identifier for the instance in Amazon EMR.

              
            

            - **Ec2InstanceId** *(string) --* 

              The unique identifier of the instance in Amazon EC2.

              
            

            - **PublicDnsName** *(string) --* 

              The public DNS name of the instance.

              
            

            - **PublicIpAddress** *(string) --* 

              The public IP address of the instance.

              
            

            - **PrivateDnsName** *(string) --* 

              The private DNS name of the instance.

              
            

            - **PrivateIpAddress** *(string) --* 

              The private IP address of the instance.

              
            

            - **Status** *(dict) --* 

              The current status of the instance.

              
              

              - **State** *(string) --* 

                The current state of the instance.

                
              

              - **StateChangeReason** *(dict) --* 

                The details of the status change reason for the instance.

                
                

                - **Code** *(string) --* 

                  The programmable code for the state change reason.

                  
                

                - **Message** *(string) --* 

                  The status change reason description.

                  
            
              

              - **Timeline** *(dict) --* 

                The timeline of the instance status over time.

                
                

                - **CreationDateTime** *(datetime) --* 

                  The creation date and time of the instance.

                  
                

                - **ReadyDateTime** *(datetime) --* 

                  The date and time when the instance was ready to perform tasks.

                  
                

                - **EndDateTime** *(datetime) --* 

                  The date and time when the instance was terminated.

                  
            
          
            

            - **InstanceGroupId** *(string) --* 

              The identifier of the instance group to which this instance belongs.

              
            

            - **EbsVolumes** *(list) --* 

              The list of EBS volumes that are attached to this instance.

              
              

              - *(dict) --* 

                EBS block device that's attached to an EC2 instance.

                
                

                - **Device** *(string) --* 

                  The device name that is exposed to the instance, such as /dev/sdh.

                  
                

                - **VolumeId** *(string) --* 

                  The volume identifier of the EBS volume.

                  
            
          
        
      
        

        - **Marker** *(string) --* 

          The pagination token that indicates the next set of results to retrieve.

          
    

  .. py:method:: list_steps(**kwargs)

    

    Provides a list of steps for the cluster.

    

    **Request Syntax** 
    ::

      response = client.list_steps(
          ClusterId='string',
          StepStates=[
              'PENDING'|'RUNNING'|'COMPLETED'|'CANCELLED'|'FAILED'|'INTERRUPTED',
          ],
          StepIds=[
              'string',
          ],
          Marker='string'
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The identifier of the cluster for which to list the steps.

      

    
    :type StepStates: list
    :param StepStates: 

      The filter to limit the step list based on certain states.

      

    
      - *(string) --* 

      
  
    :type StepIds: list
    :param StepIds: 

      The filter to limit the step list based on the identifier of the steps.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      The pagination token that indicates the next set of results to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Steps': [
                {
                    'Id': 'string',
                    'Name': 'string',
                    'Config': {
                        'Jar': 'string',
                        'Properties': {
                            'string': 'string'
                        },
                        'MainClass': 'string',
                        'Args': [
                            'string',
                        ]
                    },
                    'ActionOnFailure': 'TERMINATE_JOB_FLOW'|'TERMINATE_CLUSTER'|'CANCEL_AND_WAIT'|'CONTINUE',
                    'Status': {
                        'State': 'PENDING'|'RUNNING'|'COMPLETED'|'CANCELLED'|'FAILED'|'INTERRUPTED',
                        'StateChangeReason': {
                            'Code': 'NONE',
                            'Message': 'string'
                        },
                        'FailureDetails': {
                            'Reason': 'string',
                            'Message': 'string',
                            'LogFile': 'string'
                        },
                        'Timeline': {
                            'CreationDateTime': datetime(2015, 1, 1),
                            'StartDateTime': datetime(2015, 1, 1),
                            'EndDateTime': datetime(2015, 1, 1)
                        }
                    }
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This output contains the list of steps returned in reverse order. This means that the last step is the first element in the list.

        
        

        - **Steps** *(list) --* 

          The filtered list of steps for the cluster.

          
          

          - *(dict) --* 

            The summary of the cluster step.

            
            

            - **Id** *(string) --* 

              The identifier of the cluster step.

              
            

            - **Name** *(string) --* 

              The name of the cluster step.

              
            

            - **Config** *(dict) --* 

              The Hadoop job configuration of the cluster step.

              
              

              - **Jar** *(string) --* 

                The path to the JAR file that runs during the step.

                
              

              - **Properties** *(dict) --* 

                The list of Java properties that are set when the step runs. You can use these properties to pass key value pairs to your main function.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **MainClass** *(string) --* 

                The name of the main class in the specified Java file. If not specified, the JAR file should specify a main class in its manifest file.

                
              

              - **Args** *(list) --* 

                The list of command line arguments to pass to the JAR file's main function for execution.

                
                

                - *(string) --* 
            
          
            

            - **ActionOnFailure** *(string) --* 

              This specifies what action to take when the cluster step fails. Possible values are TERMINATE_CLUSTER, CANCEL_AND_WAIT, and CONTINUE.

              
            

            - **Status** *(dict) --* 

              The current execution status details of the cluster step.

              
              

              - **State** *(string) --* 

                The execution state of the cluster step.

                
              

              - **StateChangeReason** *(dict) --* 

                The reason for the step execution status change.

                
                

                - **Code** *(string) --* 

                  The programmable code for the state change reason. Note: Currently, the service provides no code for the state change.

                  
                

                - **Message** *(string) --* 

                  The descriptive message for the state change reason.

                  
            
              

              - **FailureDetails** *(dict) --* 

                The details for the step failure including reason, message, and log file path where the root cause was identified.

                
                

                - **Reason** *(string) --* 

                  The reason for the step failure. In the case where the service cannot successfully determine the root cause of the failure, it returns "Unknown Error" as a reason.

                  
                

                - **Message** *(string) --* 

                  The descriptive message including the error the EMR service has identified as the cause of step failure. This is text from an error log that describes the root cause of the failure.

                  
                

                - **LogFile** *(string) --* 

                  The path to the log file where the step failure root cause was originally recorded.

                  
            
              

              - **Timeline** *(dict) --* 

                The timeline of the cluster step status over time.

                
                

                - **CreationDateTime** *(datetime) --* 

                  The date and time when the cluster step was created.

                  
                

                - **StartDateTime** *(datetime) --* 

                  The date and time when the cluster step execution started.

                  
                

                - **EndDateTime** *(datetime) --* 

                  The date and time when the cluster step execution completed or failed.

                  
            
          
        
      
        

        - **Marker** *(string) --* 

          The pagination token that indicates the next set of results to retrieve.

          
    

  .. py:method:: modify_instance_groups(**kwargs)

    

    ModifyInstanceGroups modifies the number of nodes and configuration settings of an instance group. The input parameters include the new target instance count for the group and the instance group ID. The call will either succeed or fail atomically.

    

    **Request Syntax** 
    ::

      response = client.modify_instance_groups(
          InstanceGroups=[
              {
                  'InstanceGroupId': 'string',
                  'InstanceCount': 123,
                  'EC2InstanceIdsToTerminate': [
                      'string',
                  ],
                  'ShrinkPolicy': {
                      'DecommissionTimeout': 123,
                      'InstanceResizePolicy': {
                          'InstancesToTerminate': [
                              'string',
                          ],
                          'InstancesToProtect': [
                              'string',
                          ],
                          'InstanceTerminationTimeout': 123
                      }
                  }
              },
          ]
      )
    :type InstanceGroups: list
    :param InstanceGroups: 

      Instance groups to change.

      

    
      - *(dict) --* 

        Modify an instance group size.

        

      
        - **InstanceGroupId** *(string) --* **[REQUIRED]** 

          Unique ID of the instance group to expand or shrink.

          

        
        - **InstanceCount** *(integer) --* 

          Target size for the instance group.

          

        
        - **EC2InstanceIdsToTerminate** *(list) --* 

          The EC2 InstanceIds to terminate. Once you terminate the instances, the instance group will not return to its original requested size.

          

        
          - *(string) --* 

          
      
        - **ShrinkPolicy** *(dict) --* 

          Policy for customizing shrink operations.

          

        
          - **DecommissionTimeout** *(integer) --* 

            The desired timeout for decommissioning an instance. Overrides the default YARN decommissioning timeout.

            

          
          - **InstanceResizePolicy** *(dict) --* 

            Custom policy for requesting termination protection or termination of specific instances when shrinking an instance group.

            

          
            - **InstancesToTerminate** *(list) --* 

              Specific list of instances to be terminated when shrinking an instance group.

              

            
              - *(string) --* 

              
          
            - **InstancesToProtect** *(list) --* 

              Specific list of instances to be protected when shrinking an instance group.

              

            
              - *(string) --* 

              
          
            - **InstanceTerminationTimeout** *(integer) --* 

              Decommissioning timeout override for the specific list of instances to be terminated.

              

            
          
        
      
  
    
    :returns: None

  .. py:method:: remove_tags(**kwargs)

    

    Removes tags from an Amazon EMR resource. Tags make it easier to associate clusters in various ways, such as grouping clusters to track your Amazon EMR resource allocation costs. For more information, see `Tagging Amazon EMR Resources`_ . 

     

    The following example removes the stack tag with value Prod from a cluster:

    

    **Request Syntax** 
    ::

      response = client.remove_tags(
          ResourceId='string',
          TagKeys=[
              'string',
          ]
      )
    :type ResourceId: string
    :param ResourceId: **[REQUIRED]** 

      The Amazon EMR resource identifier from which tags will be removed. This value must be a cluster identifier.

      

    
    :type TagKeys: list
    :param TagKeys: **[REQUIRED]** 

      A list of tag keys to remove from a resource.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        This output indicates the result of removing tags from a resource.

        
    

  .. py:method:: run_job_flow(**kwargs)

    

    RunJobFlow creates and starts running a new job flow. The job flow will run the steps specified. Once the job flow completes, the cluster is stopped and the HDFS partition is lost. To prevent loss of data, configure the last step of the job flow to store results in Amazon S3. If the  JobFlowInstancesConfig  ``KeepJobFlowAliveWhenNoSteps`` parameter is set to ``TRUE`` , the job flow will transition to the WAITING state rather than shutting down once the steps have completed. 

     

    For additional protection, you can set the  JobFlowInstancesConfig  ``TerminationProtected`` parameter to ``TRUE`` to lock the job flow and prevent it from being terminated by API call, user intervention, or in the event of a job flow error.

     

    A maximum of 256 steps are allowed in each job flow.

     

    If your job flow is long-running (such as a Hive data warehouse) or complex, you may require more than 256 steps to process your data. You can bypass the 256-step limitation in various ways, including using the SSH shell to connect to the master node and submitting queries directly to the software running on the master node, such as Hive and Hadoop. For more information on how to do this, go to `Add More than 256 Steps to a Job Flow`_ in the *Amazon Elastic MapReduce Developer's Guide* .

     

    For long running job flows, we recommend that you periodically store your results.

    

    **Request Syntax** 
    ::

      response = client.run_job_flow(
          Name='string',
          LogUri='string',
          AdditionalInfo='string',
          AmiVersion='string',
          ReleaseLabel='string',
          Instances={
              'MasterInstanceType': 'string',
              'SlaveInstanceType': 'string',
              'InstanceCount': 123,
              'InstanceGroups': [
                  {
                      'Name': 'string',
                      'Market': 'ON_DEMAND'|'SPOT',
                      'InstanceRole': 'MASTER'|'CORE'|'TASK',
                      'BidPrice': 'string',
                      'InstanceType': 'string',
                      'InstanceCount': 123,
                      'Configurations': [
                          {
                              'Classification': 'string',
                              'Configurations': {'... recursive ...'},
                              'Properties': {
                                  'string': 'string'
                              }
                          },
                      ],
                      'EbsConfiguration': {
                          'EbsBlockDeviceConfigs': [
                              {
                                  'VolumeSpecification': {
                                      'VolumeType': 'string',
                                      'Iops': 123,
                                      'SizeInGB': 123
                                  },
                                  'VolumesPerInstance': 123
                              },
                          ],
                          'EbsOptimized': True|False
                      }
                  },
              ],
              'Ec2KeyName': 'string',
              'Placement': {
                  'AvailabilityZone': 'string'
              },
              'KeepJobFlowAliveWhenNoSteps': True|False,
              'TerminationProtected': True|False,
              'HadoopVersion': 'string',
              'Ec2SubnetId': 'string',
              'EmrManagedMasterSecurityGroup': 'string',
              'EmrManagedSlaveSecurityGroup': 'string',
              'ServiceAccessSecurityGroup': 'string',
              'AdditionalMasterSecurityGroups': [
                  'string',
              ],
              'AdditionalSlaveSecurityGroups': [
                  'string',
              ]
          },
          Steps=[
              {
                  'Name': 'string',
                  'ActionOnFailure': 'TERMINATE_JOB_FLOW'|'TERMINATE_CLUSTER'|'CANCEL_AND_WAIT'|'CONTINUE',
                  'HadoopJarStep': {
                      'Properties': [
                          {
                              'Key': 'string',
                              'Value': 'string'
                          },
                      ],
                      'Jar': 'string',
                      'MainClass': 'string',
                      'Args': [
                          'string',
                      ]
                  }
              },
          ],
          BootstrapActions=[
              {
                  'Name': 'string',
                  'ScriptBootstrapAction': {
                      'Path': 'string',
                      'Args': [
                          'string',
                      ]
                  }
              },
          ],
          SupportedProducts=[
              'string',
          ],
          NewSupportedProducts=[
              {
                  'Name': 'string',
                  'Args': [
                      'string',
                  ]
              },
          ],
          Applications=[
              {
                  'Name': 'string',
                  'Version': 'string',
                  'Args': [
                      'string',
                  ],
                  'AdditionalInfo': {
                      'string': 'string'
                  }
              },
          ],
          Configurations=[
              {
                  'Classification': 'string',
                  'Configurations': {'... recursive ...'},
                  'Properties': {
                      'string': 'string'
                  }
              },
          ],
          VisibleToAllUsers=True|False,
          JobFlowRole='string',
          ServiceRole='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the job flow.

      

    
    :type LogUri: string
    :param LogUri: 

      The location in Amazon S3 to write the log files of the job flow. If a value is not provided, logs are not created.

      

    
    :type AdditionalInfo: string
    :param AdditionalInfo: 

      A JSON string for selecting additional features.

      

    
    :type AmiVersion: string
    :param AmiVersion: 

      .. note::

         

        For Amazon EMR releases 3.x and 2.x. For Amazon EMR releases 4.x and greater, use ReleaseLabel.

         

       

      The version of the Amazon Machine Image (AMI) to use when launching Amazon EC2 instances in the job flow. The following values are valid:

       

       
      * The version number of the AMI to use, for example, "2.0." 
       

       

      If the AMI supports multiple versions of Hadoop (for example, AMI 1.0 supports both Hadoop 0.18 and 0.20) you can use the  JobFlowInstancesConfig  ``HadoopVersion`` parameter to modify the version of Hadoop from the defaults shown above.

       

      For details about the AMI versions currently supported by Amazon Elastic MapReduce, go to `AMI Versions Supported in Elastic MapReduce`_ in the *Amazon Elastic MapReduce Developer's Guide.*  

      

    
    :type ReleaseLabel: string
    :param ReleaseLabel: 

      .. note::

         

        Amazon EMR releases 4.x or later.

         

       

      The release label for the Amazon EMR release. For Amazon EMR 3.x and 2.x AMIs, use amiVersion instead instead of ReleaseLabel.

      

    
    :type Instances: dict
    :param Instances: **[REQUIRED]** 

      A specification of the number and type of Amazon EC2 instances on which to run the job flow.

      

    
      - **MasterInstanceType** *(string) --* 

        The EC2 instance type of the master node.

        

      
      - **SlaveInstanceType** *(string) --* 

        The EC2 instance type of the slave nodes.

        

      
      - **InstanceCount** *(integer) --* 

        The number of Amazon EC2 instances used to execute the job flow.

        

      
      - **InstanceGroups** *(list) --* 

        Configuration for the job flow's instance groups.

        

      
        - *(dict) --* 

          Configuration defining a new instance group.

          

        
          - **Name** *(string) --* 

            Friendly name given to the instance group.

            

          
          - **Market** *(string) --* 

            Market type of the Amazon EC2 instances used to create a cluster node.

            

          
          - **InstanceRole** *(string) --* **[REQUIRED]** 

            The role of the instance group in the cluster.

            

          
          - **BidPrice** *(string) --* 

            Bid price for each Amazon EC2 instance in the instance group when launching nodes as Spot Instances, expressed in USD.

            

          
          - **InstanceType** *(string) --* **[REQUIRED]** 

            The Amazon EC2 instance type for all instances in the instance group.

            

          
          - **InstanceCount** *(integer) --* **[REQUIRED]** 

            Target number of instances for the instance group.

            

          
          - **Configurations** *(list) --* 

            .. note::

               

              Amazon EMR releases 4.x or later.

               

             

            The list of configurations supplied for an EMR cluster instance group. You can specify a separate configuration for each instance group (master, core, and task).

            

          
            - *(dict) --* 

              .. note::

                 

                Amazon EMR releases 4.x or later.

                 

               

              Specifies a hardware and software configuration of the EMR cluster. This includes configurations for applications and software bundled with Amazon EMR. The Configuration object is a JSON object which is defined by a classification and a set of properties. Configurations can be nested, so a configuration may have its own Configuration objects listed.

              

            
              - **Classification** *(string) --* 

                The classification of a configuration. For more information see, `Amazon EMR Configurations`_ . 

                

              
              - **Configurations** *(list) --* 

                A list of configurations you apply to this configuration object.

                

              
              - **Properties** *(dict) --* 

                A set of properties supplied to the Configuration object.

                

              
                - *(string) --* 

                
                  - *(string) --* 

                  
            
          
            
        
          - **EbsConfiguration** *(dict) --* 

            EBS configurations that will be attached to each Amazon EC2 instance in the instance group.

            

          
            - **EbsBlockDeviceConfigs** *(list) --* 

            
              - *(dict) --* 

                Configuration of requested EBS block device associated with the instance group with count of volumes that will be associated to every instance.

                

              
                - **VolumeSpecification** *(dict) --* **[REQUIRED]** 

                  EBS volume specifications such as volume type, IOPS, and size(GiB) that will be requested for the EBS volume attached to an EC2 instance in the cluster.

                  

                
                  - **VolumeType** *(string) --* **[REQUIRED]** 

                    The volume type. Volume types supported are gp2, io1, standard.

                    

                  
                  - **Iops** *(integer) --* 

                    The number of I/O operations per second (IOPS) that the volume supports.

                    

                  
                  - **SizeInGB** *(integer) --* **[REQUIRED]** 

                    The volume size, in gibibytes (GiB). This can be a number from 1 - 1024. If the volume type is EBS-optimized, the minimum value is 10.

                    

                  
                
                - **VolumesPerInstance** *(integer) --* 

                  Number of EBS volumes with specific volume configuration, that will be associated with every instance in the instance group

                  

                
              
          
            - **EbsOptimized** *(boolean) --* 

            
          
        
    
      - **Ec2KeyName** *(string) --* 

        The name of the Amazon EC2 key pair that can be used to ssh to the master node as the user called "hadoop."

        

      
      - **Placement** *(dict) --* 

        The Availability Zone the job flow will run in.

        

      
        - **AvailabilityZone** *(string) --* **[REQUIRED]** 

          The Amazon EC2 Availability Zone for the job flow.

          

        
      
      - **KeepJobFlowAliveWhenNoSteps** *(boolean) --* 

        Specifies whether the job flow should be kept alive after completing all steps.

        

      
      - **TerminationProtected** *(boolean) --* 

        Specifies whether to lock the job flow to prevent the Amazon EC2 instances from being terminated by API call, user intervention, or in the event of a job flow error.

        

      
      - **HadoopVersion** *(string) --* 

        The Hadoop version for the job flow. Valid inputs are "0.18" (deprecated), "0.20" (deprecated), "0.20.205" (deprecated), "1.0.3", "2.2.0", or "2.4.0". If you do not set this value, the default of 0.18 is used, unless the AmiVersion parameter is set in the RunJobFlow call, in which case the default version of Hadoop for that AMI version is used.

        

      
      - **Ec2SubnetId** *(string) --* 

        To launch the job flow in Amazon Virtual Private Cloud (Amazon VPC), set this parameter to the identifier of the Amazon VPC subnet where you want the job flow to launch. If you do not specify this value, the job flow is launched in the normal Amazon Web Services cloud, outside of an Amazon VPC.

         

        Amazon VPC currently does not support cluster compute quadruple extra large (cc1.4xlarge) instances. Thus you cannot specify the cc1.4xlarge instance type for nodes of a job flow launched in a Amazon VPC.

        

      
      - **EmrManagedMasterSecurityGroup** *(string) --* 

        The identifier of the Amazon EC2 security group for the master node.

        

      
      - **EmrManagedSlaveSecurityGroup** *(string) --* 

        The identifier of the Amazon EC2 security group for the slave nodes.

        

      
      - **ServiceAccessSecurityGroup** *(string) --* 

        The identifier of the Amazon EC2 security group for the Amazon EMR service to access clusters in VPC private subnets.

        

      
      - **AdditionalMasterSecurityGroups** *(list) --* 

        A list of additional Amazon EC2 security group IDs for the master node.

        

      
        - *(string) --* 

        
    
      - **AdditionalSlaveSecurityGroups** *(list) --* 

        A list of additional Amazon EC2 security group IDs for the slave nodes.

        

      
        - *(string) --* 

        
    
    
    :type Steps: list
    :param Steps: 

      A list of steps to be executed by the job flow.

      

    
      - *(dict) --* 

        Specification of a job flow step.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the job flow step.

          

        
        - **ActionOnFailure** *(string) --* 

          The action to take if the job flow step fails.

          

        
        - **HadoopJarStep** *(dict) --* **[REQUIRED]** 

          The JAR file used for the job flow step.

          

        
          - **Properties** *(list) --* 

            A list of Java properties that are set when the step runs. You can use these properties to pass key value pairs to your main function.

            

          
            - *(dict) --* 

              A key value pair.

              

            
              - **Key** *(string) --* 

                The unique identifier of a key value pair.

                

              
              - **Value** *(string) --* 

                The value part of the identified key.

                

              
            
        
          - **Jar** *(string) --* **[REQUIRED]** 

            A path to a JAR file run during the step.

            

          
          - **MainClass** *(string) --* 

            The name of the main class in the specified Java file. If not specified, the JAR file should specify a Main-Class in its manifest file.

            

          
          - **Args** *(list) --* 

            A list of command line arguments passed to the JAR file's main function when executed.

            

          
            - *(string) --* 

            
        
        
      
  
    :type BootstrapActions: list
    :param BootstrapActions: 

      A list of bootstrap actions that will be run before Hadoop is started on the cluster nodes.

      

    
      - *(dict) --* 

        Configuration of a bootstrap action.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the bootstrap action.

          

        
        - **ScriptBootstrapAction** *(dict) --* **[REQUIRED]** 

          The script run by the bootstrap action.

          

        
          - **Path** *(string) --* **[REQUIRED]** 

            Location of the script to run during a bootstrap action. Can be either a location in Amazon S3 or on a local file system.

            

          
          - **Args** *(list) --* 

            A list of command line arguments to pass to the bootstrap action script.

            

          
            - *(string) --* 

            
        
        
      
  
    :type SupportedProducts: list
    :param SupportedProducts: 

      .. note::

         

        For Amazon EMR releases 3.x and 2.x. For Amazon EMR releases 4.x and greater, use Applications.

         

       

      A list of strings that indicates third-party software to use with the job flow. For more information, go to `Use Third Party Applications with Amazon EMR`_ . Currently supported values are:

       

       
      * "mapr-m3" - launch the job flow using MapR M3 Edition. 
       
      * "mapr-m5" - launch the job flow using MapR M5 Edition. 
       

      

    
      - *(string) --* 

      
  
    :type NewSupportedProducts: list
    :param NewSupportedProducts: 

      .. note::

         

        For Amazon EMR releases 3.x and 2.x. For Amazon EMR releases 4.x and greater, use Applications.

         

       

      A list of strings that indicates third-party software to use with the job flow that accepts a user argument list. EMR accepts and forwards the argument list to the corresponding installation script as bootstrap action arguments. For more information, see `Launch a Job Flow on the MapR Distribution for Hadoop`_ . Currently supported values are:

       

       
      * "mapr-m3" - launch the cluster using MapR M3 Edition. 
       
      * "mapr-m5" - launch the cluster using MapR M5 Edition. 
       
      * "mapr" with the user arguments specifying "--edition,m3" or "--edition,m5" - launch the job flow using MapR M3 or M5 Edition respectively. 
       
      * "mapr-m7" - launch the cluster using MapR M7 Edition. 
       
      * "hunk" - launch the cluster with the Hunk Big Data Analtics Platform. 
       
      * "hue"- launch the cluster with Hue installed. 
       
      * "spark" - launch the cluster with Apache Spark installed. 
       
      * "ganglia" - launch the cluster with the Ganglia Monitoring System installed. 
       

      

    
      - *(dict) --* 

        The list of supported product configurations which allow user-supplied arguments. EMR accepts these arguments and forwards them to the corresponding installation script as bootstrap action arguments.

        

      
        - **Name** *(string) --* 

          The name of the product configuration.

          

        
        - **Args** *(list) --* 

          The list of user-supplied arguments.

          

        
          - *(string) --* 

          
      
      
  
    :type Applications: list
    :param Applications: 

      .. note::

         

        Amazon EMR releases 4.x or later.

         

       

      A list of applications for the cluster. Valid values are: "Hadoop", "Hive", "Mahout", "Pig", and "Spark." They are case insensitive.

      

    
      - *(dict) --* 

        An application is any Amazon or third-party software that you can add to the cluster. This structure contains a list of strings that indicates the software to use with the cluster and accepts a user argument list. Amazon EMR accepts and forwards the argument list to the corresponding installation script as bootstrap action argument. For more information, see `Launch a Job Flow on the MapR Distribution for Hadoop`_ . Currently supported values are:

         

         
        * "mapr-m3" - launch the job flow using MapR M3 Edition. 
         
        * "mapr-m5" - launch the job flow using MapR M5 Edition. 
         
        * "mapr" with the user arguments specifying "--edition,m3" or "--edition,m5" - launch the job flow using MapR M3 or M5 Edition, respectively. 
         

         

        .. note::

           

          In Amazon EMR releases 4.0 and greater, the only accepted parameter is the application name. To pass arguments to applications, you supply a configuration for each application.

           

        

      
        - **Name** *(string) --* 

          The name of the application.

          

        
        - **Version** *(string) --* 

          The version of the application.

          

        
        - **Args** *(list) --* 

          Arguments for Amazon EMR to pass to the application.

          

        
          - *(string) --* 

          
      
        - **AdditionalInfo** *(dict) --* 

          This option is for advanced users only. This is meta information about third-party applications that third-party vendors use for testing purposes.

          

        
          - *(string) --* 

          
            - *(string) --* 

            
      
    
      
  
    :type Configurations: list
    :param Configurations: 

      .. note::

         

        Amazon EMR releases 4.x or later.

         

       

      The list of configurations supplied for the EMR cluster you are creating.

      

    
      - *(dict) --* 

        .. note::

           

          Amazon EMR releases 4.x or later.

           

         

        Specifies a hardware and software configuration of the EMR cluster. This includes configurations for applications and software bundled with Amazon EMR. The Configuration object is a JSON object which is defined by a classification and a set of properties. Configurations can be nested, so a configuration may have its own Configuration objects listed.

        

      
        - **Classification** *(string) --* 

          The classification of a configuration. For more information see, `Amazon EMR Configurations`_ . 

          

        
        - **Configurations** *(list) --* 

          A list of configurations you apply to this configuration object.

          

        
        - **Properties** *(dict) --* 

          A set of properties supplied to the Configuration object.

          

        
          - *(string) --* 

          
            - *(string) --* 

            
      
    
      
  
    :type VisibleToAllUsers: boolean
    :param VisibleToAllUsers: 

      Whether the job flow is visible to all IAM users of the AWS account associated with the job flow. If this value is set to ``true`` , all IAM users of that AWS account can view and (if they have the proper policy permissions set) manage the job flow. If it is set to ``false`` , only the IAM user that created the job flow can view and manage it.

      

    
    :type JobFlowRole: string
    :param JobFlowRole: 

      Also called instance profile and EC2 role. An IAM role for an EMR cluster. The EC2 instances of the cluster assume this role. The default role is ``EMR_EC2_DefaultRole`` . In order to use the default role, you must have already created it using the CLI or console.

      

    
    :type ServiceRole: string
    :param ServiceRole: 

      The IAM role that will be assumed by the Amazon EMR service to access AWS resources on your behalf.

      

    
    :type Tags: list
    :param Tags: 

      A list of tags to associate with a cluster and propagate to Amazon EC2 instances.

      

    
      - *(dict) --* 

        A key/value pair containing user-defined metadata that you can associate with an Amazon EMR resource. Tags make it easier to associate clusters in various ways, such as grouping clu\ sters to track your Amazon EMR resource allocation costs. For more information, see `Tagging Amazon EMR Resources`_ . 

        

      
        - **Key** *(string) --* 

          A user-defined key, which is the minimum required information for a valid tag. For more information, see `Tagging Amazon EMR Resources`_ . 

          

        
        - **Value** *(string) --* 

          A user-defined value, which is optional in a tag. For more information, see `Tagging Amazon EMR Resources`_ . 

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'JobFlowId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the  RunJobFlow operation. 

        
        

        - **JobFlowId** *(string) --* 

          An unique identifier for the job flow.

          
    

  .. py:method:: set_termination_protection(**kwargs)

    

    SetTerminationProtection locks a job flow so the Amazon EC2 instances in the cluster cannot be terminated by user intervention, an API call, or in the event of a job-flow error. The cluster still terminates upon successful completion of the job flow. Calling SetTerminationProtection on a job flow is analogous to calling the Amazon EC2 DisableAPITermination API on all of the EC2 instances in a cluster.

     

    SetTerminationProtection is used to prevent accidental termination of a job flow and to ensure that in the event of an error, the instances will persist so you can recover any data stored in their ephemeral instance storage.

     

    To terminate a job flow that has been locked by setting SetTerminationProtection to ``true`` , you must first unlock the job flow by a subsequent call to SetTerminationProtection in which you set the value to ``false`` . 

     

    For more information, go to `Protecting a Job Flow from Termination`_ in the *Amazon Elastic MapReduce Developer's Guide.*  

    

    **Request Syntax** 
    ::

      response = client.set_termination_protection(
          JobFlowIds=[
              'string',
          ],
          TerminationProtected=True|False
      )
    :type JobFlowIds: list
    :param JobFlowIds: **[REQUIRED]** 

      A list of strings that uniquely identify the job flows to protect. This identifier is returned by  RunJobFlow and can also be obtained from  DescribeJobFlows . 

      

    
      - *(string) --* 

      
  
    :type TerminationProtected: boolean
    :param TerminationProtected: **[REQUIRED]** 

      A Boolean that indicates whether to protect the job flow and prevent the Amazon EC2 instances in the cluster from shutting down due to API calls, user intervention, or job-flow error.

      

    
    
    :returns: None

  .. py:method:: set_visible_to_all_users(**kwargs)

    

    Sets whether all AWS Identity and Access Management (IAM) users under your account can access the specified job flows. This action works on running job flows. You can also set the visibility of a job flow when you launch it using the ``VisibleToAllUsers`` parameter of  RunJobFlow . The SetVisibleToAllUsers action can be called only by an IAM user who created the job flow or the AWS account that owns the job flow.

    

    **Request Syntax** 
    ::

      response = client.set_visible_to_all_users(
          JobFlowIds=[
              'string',
          ],
          VisibleToAllUsers=True|False
      )
    :type JobFlowIds: list
    :param JobFlowIds: **[REQUIRED]** 

      Identifiers of the job flows to receive the new visibility setting.

      

    
      - *(string) --* 

      
  
    :type VisibleToAllUsers: boolean
    :param VisibleToAllUsers: **[REQUIRED]** 

      Whether the specified job flows are visible to all IAM users of the AWS account associated with the job flow. If this value is set to True, all IAM users of that AWS account can view and, if they have the proper IAM policy permissions set, manage the job flows. If it is set to False, only the IAM user that created a job flow can view and manage it.

      

    
    
    :returns: None

  .. py:method:: terminate_job_flows(**kwargs)

    

    TerminateJobFlows shuts a list of job flows down. When a job flow is shut down, any step not yet completed is canceled and the EC2 instances on which the job flow is running are stopped. Any log files not already saved are uploaded to Amazon S3 if a LogUri was specified when the job flow was created.

     

    The maximum number of JobFlows allowed is 10. The call to TerminateJobFlows is asynchronous. Depending on the configuration of the job flow, it may take up to 5-20 minutes for the job flow to completely terminate and release allocated resources, such as Amazon EC2 instances.

    

    **Request Syntax** 
    ::

      response = client.terminate_job_flows(
          JobFlowIds=[
              'string',
          ]
      )
    :type JobFlowIds: list
    :param JobFlowIds: **[REQUIRED]** 

      A list of job flows to be shutdown.

      

    
      - *(string) --* 

      
  
    
    :returns: None

==========
Paginators
==========


The available paginators are:

* :py:class:`EMR.Paginator.ListBootstrapActions`


* :py:class:`EMR.Paginator.ListClusters`


* :py:class:`EMR.Paginator.ListInstanceGroups`


* :py:class:`EMR.Paginator.ListInstances`


* :py:class:`EMR.Paginator.ListSteps`



.. py:class:: EMR.Paginator.ListBootstrapActions

  ::

    
    paginator = client.get_paginator('list_bootstrap_actions')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`EMR.Client.list_bootstrap_actions`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          ClusterId='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The cluster identifier for the bootstrap actions to list .

      

    
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
            'BootstrapActions': [
                {
                    'Name': 'string',
                    'ScriptPath': 'string',
                    'Args': [
                        'string',
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This output contains the boostrap actions detail .

        
        

        - **BootstrapActions** *(list) --* 

          The bootstrap actions associated with the cluster .

          
          

          - *(dict) --* 

            An entity describing an executable that runs on a cluster.

            
            

            - **Name** *(string) --* 

              The name of the command.

              
            

            - **ScriptPath** *(string) --* 

              The Amazon S3 location of the command script.

              
            

            - **Args** *(list) --* 

              Arguments for Amazon EMR to pass to the command for execution.

              
              

              - *(string) --* 
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: EMR.Paginator.ListClusters

  ::

    
    paginator = client.get_paginator('list_clusters')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`EMR.Client.list_clusters`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          CreatedAfter=datetime(2015, 1, 1),
          CreatedBefore=datetime(2015, 1, 1),
          ClusterStates=[
              'STARTING'|'BOOTSTRAPPING'|'RUNNING'|'WAITING'|'TERMINATING'|'TERMINATED'|'TERMINATED_WITH_ERRORS',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type CreatedAfter: datetime
    :param CreatedAfter: 

      The creation date and time beginning value filter for listing clusters .

      

    
    :type CreatedBefore: datetime
    :param CreatedBefore: 

      The creation date and time end value filter for listing clusters .

      

    
    :type ClusterStates: list
    :param ClusterStates: 

      The cluster state filters to apply when listing clusters.

      

    
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
            'Clusters': [
                {
                    'Id': 'string',
                    'Name': 'string',
                    'Status': {
                        'State': 'STARTING'|'BOOTSTRAPPING'|'RUNNING'|'WAITING'|'TERMINATING'|'TERMINATED'|'TERMINATED_WITH_ERRORS',
                        'StateChangeReason': {
                            'Code': 'INTERNAL_ERROR'|'VALIDATION_ERROR'|'INSTANCE_FAILURE'|'BOOTSTRAP_FAILURE'|'USER_REQUEST'|'STEP_FAILURE'|'ALL_STEPS_COMPLETED',
                            'Message': 'string'
                        },
                        'Timeline': {
                            'CreationDateTime': datetime(2015, 1, 1),
                            'ReadyDateTime': datetime(2015, 1, 1),
                            'EndDateTime': datetime(2015, 1, 1)
                        }
                    },
                    'NormalizedInstanceHours': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This contains a ClusterSummaryList with the cluster details; for example, the cluster IDs, names, and status.

        
        

        - **Clusters** *(list) --* 

          The list of clusters for the account based on the given filters.

          
          

          - *(dict) --* 

            The summary description of the cluster.

            
            

            - **Id** *(string) --* 

              The unique identifier for the cluster.

              
            

            - **Name** *(string) --* 

              The name of the cluster.

              
            

            - **Status** *(dict) --* 

              The details about the current status of the cluster.

              
              

              - **State** *(string) --* 

                The current state of the cluster.

                
              

              - **StateChangeReason** *(dict) --* 

                The reason for the cluster status change.

                
                

                - **Code** *(string) --* 

                  The programmatic code for the state change reason.

                  
                

                - **Message** *(string) --* 

                  The descriptive message for the state change reason.

                  
            
              

              - **Timeline** *(dict) --* 

                A timeline that represents the status of a cluster over the lifetime of the cluster.

                
                

                - **CreationDateTime** *(datetime) --* 

                  The creation date and time of the cluster.

                  
                

                - **ReadyDateTime** *(datetime) --* 

                  The date and time when the cluster was ready to execute steps.

                  
                

                - **EndDateTime** *(datetime) --* 

                  The date and time when the cluster was terminated.

                  
            
          
            

            - **NormalizedInstanceHours** *(integer) --* 

              An approximation of the cost of the job flow, represented in m1.small/hours. This value is incremented one time for every hour an m1.small instance runs. Larger instances are weighted more, so an EC2 instance that is roughly four times more expensive would result in the normalized instance hours being incremented by four. This result is only an approximation and does not reflect the actual billing rate.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: EMR.Paginator.ListInstanceGroups

  ::

    
    paginator = client.get_paginator('list_instance_groups')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`EMR.Client.list_instance_groups`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          ClusterId='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The identifier of the cluster for which to list the instance groups.

      

    
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
            'InstanceGroups': [
                {
                    'Id': 'string',
                    'Name': 'string',
                    'Market': 'ON_DEMAND'|'SPOT',
                    'InstanceGroupType': 'MASTER'|'CORE'|'TASK',
                    'BidPrice': 'string',
                    'InstanceType': 'string',
                    'RequestedInstanceCount': 123,
                    'RunningInstanceCount': 123,
                    'Status': {
                        'State': 'PROVISIONING'|'BOOTSTRAPPING'|'RUNNING'|'RESIZING'|'SUSPENDED'|'TERMINATING'|'TERMINATED'|'ARRESTED'|'SHUTTING_DOWN'|'ENDED',
                        'StateChangeReason': {
                            'Code': 'INTERNAL_ERROR'|'VALIDATION_ERROR'|'INSTANCE_FAILURE'|'CLUSTER_TERMINATED',
                            'Message': 'string'
                        },
                        'Timeline': {
                            'CreationDateTime': datetime(2015, 1, 1),
                            'ReadyDateTime': datetime(2015, 1, 1),
                            'EndDateTime': datetime(2015, 1, 1)
                        }
                    },
                    'Configurations': [
                        {
                            'Classification': 'string',
                            'Configurations': {'... recursive ...'},
                            'Properties': {
                                'string': 'string'
                            }
                        },
                    ],
                    'EbsBlockDevices': [
                        {
                            'VolumeSpecification': {
                                'VolumeType': 'string',
                                'Iops': 123,
                                'SizeInGB': 123
                            },
                            'Device': 'string'
                        },
                    ],
                    'EbsOptimized': True|False,
                    'ShrinkPolicy': {
                        'DecommissionTimeout': 123,
                        'InstanceResizePolicy': {
                            'InstancesToTerminate': [
                                'string',
                            ],
                            'InstancesToProtect': [
                                'string',
                            ],
                            'InstanceTerminationTimeout': 123
                        }
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This input determines which instance groups to retrieve.

        
        

        - **InstanceGroups** *(list) --* 

          The list of instance groups for the cluster and given filters.

          
          

          - *(dict) --* 

            This entity represents an instance group, which is a group of instances that have common purpose. For example, CORE instance group is used for HDFS.

            
            

            - **Id** *(string) --* 

              The identifier of the instance group.

              
            

            - **Name** *(string) --* 

              The name of the instance group.

              
            

            - **Market** *(string) --* 

              The marketplace to provision instances for this group. Valid values are ON_DEMAND or SPOT.

              
            

            - **InstanceGroupType** *(string) --* 

              The type of the instance group. Valid values are MASTER, CORE or TASK.

              
            

            - **BidPrice** *(string) --* 

              The bid price for each EC2 instance in the instance group when launching nodes as Spot Instances, expressed in USD.

              
            

            - **InstanceType** *(string) --* 

              The EC2 instance type for all instances in the instance group.

              
            

            - **RequestedInstanceCount** *(integer) --* 

              The target number of instances for the instance group.

              
            

            - **RunningInstanceCount** *(integer) --* 

              The number of instances currently running in this instance group.

              
            

            - **Status** *(dict) --* 

              The current status of the instance group.

              
              

              - **State** *(string) --* 

                The current state of the instance group.

                
              

              - **StateChangeReason** *(dict) --* 

                The status change reason details for the instance group.

                
                

                - **Code** *(string) --* 

                  The programmable code for the state change reason.

                  
                

                - **Message** *(string) --* 

                  The status change reason description.

                  
            
              

              - **Timeline** *(dict) --* 

                The timeline of the instance group status over time.

                
                

                - **CreationDateTime** *(datetime) --* 

                  The creation date and time of the instance group.

                  
                

                - **ReadyDateTime** *(datetime) --* 

                  The date and time when the instance group became ready to perform tasks.

                  
                

                - **EndDateTime** *(datetime) --* 

                  The date and time when the instance group terminated.

                  
            
          
            

            - **Configurations** *(list) --* 

              .. note::

                 

                Amazon EMR releases 4.x or later.

                 

               

              The list of configurations supplied for an EMR cluster instance group. You can specify a separate configuration for each instance group (master, core, and task).

              
              

              - *(dict) --* 

                .. note::

                   

                  Amazon EMR releases 4.x or later.

                   

                 

                Specifies a hardware and software configuration of the EMR cluster. This includes configurations for applications and software bundled with Amazon EMR. The Configuration object is a JSON object which is defined by a classification and a set of properties. Configurations can be nested, so a configuration may have its own Configuration objects listed.

                
                

                - **Classification** *(string) --* 

                  The classification of a configuration. For more information see, `Amazon EMR Configurations`_ . 

                  
                

                - **Configurations** *(list) --* 

                  A list of configurations you apply to this configuration object.

                  
                

                - **Properties** *(dict) --* 

                  A set of properties supplied to the Configuration object.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
          
            

            - **EbsBlockDevices** *(list) --* 

              The EBS block devices that are mapped to this instance group.

              
              

              - *(dict) --* 

                Configuration of requested EBS block device associated with the instance group.

                
                

                - **VolumeSpecification** *(dict) --* 

                  EBS volume specifications such as volume type, IOPS, and size(GiB) that will be requested for the EBS volume attached to an EC2 instance in the cluster.

                  
                  

                  - **VolumeType** *(string) --* 

                    The volume type. Volume types supported are gp2, io1, standard.

                    
                  

                  - **Iops** *(integer) --* 

                    The number of I/O operations per second (IOPS) that the volume supports.

                    
                  

                  - **SizeInGB** *(integer) --* 

                    The volume size, in gibibytes (GiB). This can be a number from 1 - 1024. If the volume type is EBS-optimized, the minimum value is 10.

                    
              
                

                - **Device** *(string) --* 

                  The device name that is exposed to the instance, such as /dev/sdh.

                  
            
          
            

            - **EbsOptimized** *(boolean) --* 

              If the instance group is EBS-optimized. An Amazon EBS-optimized instance uses an optimized configuration stack and provides additional, dedicated capacity for Amazon EBS I/O.

              
            

            - **ShrinkPolicy** *(dict) --* 

              Policy for customizing shrink operations.

              
              

              - **DecommissionTimeout** *(integer) --* 

                The desired timeout for decommissioning an instance. Overrides the default YARN decommissioning timeout.

                
              

              - **InstanceResizePolicy** *(dict) --* 

                Custom policy for requesting termination protection or termination of specific instances when shrinking an instance group.

                
                

                - **InstancesToTerminate** *(list) --* 

                  Specific list of instances to be terminated when shrinking an instance group.

                  
                  

                  - *(string) --* 
              
                

                - **InstancesToProtect** *(list) --* 

                  Specific list of instances to be protected when shrinking an instance group.

                  
                  

                  - *(string) --* 
              
                

                - **InstanceTerminationTimeout** *(integer) --* 

                  Decommissioning timeout override for the specific list of instances to be terminated.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: EMR.Paginator.ListInstances

  ::

    
    paginator = client.get_paginator('list_instances')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`EMR.Client.list_instances`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          ClusterId='string',
          InstanceGroupId='string',
          InstanceGroupTypes=[
              'MASTER'|'CORE'|'TASK',
          ],
          InstanceStates=[
              'AWAITING_FULFILLMENT'|'PROVISIONING'|'BOOTSTRAPPING'|'RUNNING'|'TERMINATED',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The identifier of the cluster for which to list the instances.

      

    
    :type InstanceGroupId: string
    :param InstanceGroupId: 

      The identifier of the instance group for which to list the instances.

      

    
    :type InstanceGroupTypes: list
    :param InstanceGroupTypes: 

      The type of instance group for which to list the instances.

      

    
      - *(string) --* 

      
  
    :type InstanceStates: list
    :param InstanceStates: 

      A list of instance states that will filter the instances returned with this request.

      

    
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
            'Instances': [
                {
                    'Id': 'string',
                    'Ec2InstanceId': 'string',
                    'PublicDnsName': 'string',
                    'PublicIpAddress': 'string',
                    'PrivateDnsName': 'string',
                    'PrivateIpAddress': 'string',
                    'Status': {
                        'State': 'AWAITING_FULFILLMENT'|'PROVISIONING'|'BOOTSTRAPPING'|'RUNNING'|'TERMINATED',
                        'StateChangeReason': {
                            'Code': 'INTERNAL_ERROR'|'VALIDATION_ERROR'|'INSTANCE_FAILURE'|'BOOTSTRAP_FAILURE'|'CLUSTER_TERMINATED',
                            'Message': 'string'
                        },
                        'Timeline': {
                            'CreationDateTime': datetime(2015, 1, 1),
                            'ReadyDateTime': datetime(2015, 1, 1),
                            'EndDateTime': datetime(2015, 1, 1)
                        }
                    },
                    'InstanceGroupId': 'string',
                    'EbsVolumes': [
                        {
                            'Device': 'string',
                            'VolumeId': 'string'
                        },
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This output contains the list of instances.

        
        

        - **Instances** *(list) --* 

          The list of instances for the cluster and given filters.

          
          

          - *(dict) --* 

            Represents an EC2 instance provisioned as part of cluster.

            
            

            - **Id** *(string) --* 

              The unique identifier for the instance in Amazon EMR.

              
            

            - **Ec2InstanceId** *(string) --* 

              The unique identifier of the instance in Amazon EC2.

              
            

            - **PublicDnsName** *(string) --* 

              The public DNS name of the instance.

              
            

            - **PublicIpAddress** *(string) --* 

              The public IP address of the instance.

              
            

            - **PrivateDnsName** *(string) --* 

              The private DNS name of the instance.

              
            

            - **PrivateIpAddress** *(string) --* 

              The private IP address of the instance.

              
            

            - **Status** *(dict) --* 

              The current status of the instance.

              
              

              - **State** *(string) --* 

                The current state of the instance.

                
              

              - **StateChangeReason** *(dict) --* 

                The details of the status change reason for the instance.

                
                

                - **Code** *(string) --* 

                  The programmable code for the state change reason.

                  
                

                - **Message** *(string) --* 

                  The status change reason description.

                  
            
              

              - **Timeline** *(dict) --* 

                The timeline of the instance status over time.

                
                

                - **CreationDateTime** *(datetime) --* 

                  The creation date and time of the instance.

                  
                

                - **ReadyDateTime** *(datetime) --* 

                  The date and time when the instance was ready to perform tasks.

                  
                

                - **EndDateTime** *(datetime) --* 

                  The date and time when the instance was terminated.

                  
            
          
            

            - **InstanceGroupId** *(string) --* 

              The identifier of the instance group to which this instance belongs.

              
            

            - **EbsVolumes** *(list) --* 

              The list of EBS volumes that are attached to this instance.

              
              

              - *(dict) --* 

                EBS block device that's attached to an EC2 instance.

                
                

                - **Device** *(string) --* 

                  The device name that is exposed to the instance, such as /dev/sdh.

                  
                

                - **VolumeId** *(string) --* 

                  The volume identifier of the EBS volume.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: EMR.Paginator.ListSteps

  ::

    
    paginator = client.get_paginator('list_steps')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`EMR.Client.list_steps`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          ClusterId='string',
          StepStates=[
              'PENDING'|'RUNNING'|'COMPLETED'|'CANCELLED'|'FAILED'|'INTERRUPTED',
          ],
          StepIds=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The identifier of the cluster for which to list the steps.

      

    
    :type StepStates: list
    :param StepStates: 

      The filter to limit the step list based on certain states.

      

    
      - *(string) --* 

      
  
    :type StepIds: list
    :param StepIds: 

      The filter to limit the step list based on the identifier of the steps.

      

    
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
            'Steps': [
                {
                    'Id': 'string',
                    'Name': 'string',
                    'Config': {
                        'Jar': 'string',
                        'Properties': {
                            'string': 'string'
                        },
                        'MainClass': 'string',
                        'Args': [
                            'string',
                        ]
                    },
                    'ActionOnFailure': 'TERMINATE_JOB_FLOW'|'TERMINATE_CLUSTER'|'CANCEL_AND_WAIT'|'CONTINUE',
                    'Status': {
                        'State': 'PENDING'|'RUNNING'|'COMPLETED'|'CANCELLED'|'FAILED'|'INTERRUPTED',
                        'StateChangeReason': {
                            'Code': 'NONE',
                            'Message': 'string'
                        },
                        'FailureDetails': {
                            'Reason': 'string',
                            'Message': 'string',
                            'LogFile': 'string'
                        },
                        'Timeline': {
                            'CreationDateTime': datetime(2015, 1, 1),
                            'StartDateTime': datetime(2015, 1, 1),
                            'EndDateTime': datetime(2015, 1, 1)
                        }
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        This output contains the list of steps returned in reverse order. This means that the last step is the first element in the list.

        
        

        - **Steps** *(list) --* 

          The filtered list of steps for the cluster.

          
          

          - *(dict) --* 

            The summary of the cluster step.

            
            

            - **Id** *(string) --* 

              The identifier of the cluster step.

              
            

            - **Name** *(string) --* 

              The name of the cluster step.

              
            

            - **Config** *(dict) --* 

              The Hadoop job configuration of the cluster step.

              
              

              - **Jar** *(string) --* 

                The path to the JAR file that runs during the step.

                
              

              - **Properties** *(dict) --* 

                The list of Java properties that are set when the step runs. You can use these properties to pass key value pairs to your main function.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **MainClass** *(string) --* 

                The name of the main class in the specified Java file. If not specified, the JAR file should specify a main class in its manifest file.

                
              

              - **Args** *(list) --* 

                The list of command line arguments to pass to the JAR file's main function for execution.

                
                

                - *(string) --* 
            
          
            

            - **ActionOnFailure** *(string) --* 

              This specifies what action to take when the cluster step fails. Possible values are TERMINATE_CLUSTER, CANCEL_AND_WAIT, and CONTINUE.

              
            

            - **Status** *(dict) --* 

              The current execution status details of the cluster step.

              
              

              - **State** *(string) --* 

                The execution state of the cluster step.

                
              

              - **StateChangeReason** *(dict) --* 

                The reason for the step execution status change.

                
                

                - **Code** *(string) --* 

                  The programmable code for the state change reason. Note: Currently, the service provides no code for the state change.

                  
                

                - **Message** *(string) --* 

                  The descriptive message for the state change reason.

                  
            
              

              - **FailureDetails** *(dict) --* 

                The details for the step failure including reason, message, and log file path where the root cause was identified.

                
                

                - **Reason** *(string) --* 

                  The reason for the step failure. In the case where the service cannot successfully determine the root cause of the failure, it returns "Unknown Error" as a reason.

                  
                

                - **Message** *(string) --* 

                  The descriptive message including the error the EMR service has identified as the cause of step failure. This is text from an error log that describes the root cause of the failure.

                  
                

                - **LogFile** *(string) --* 

                  The path to the log file where the step failure root cause was originally recorded.

                  
            
              

              - **Timeline** *(dict) --* 

                The timeline of the cluster step status over time.

                
                

                - **CreationDateTime** *(datetime) --* 

                  The date and time when the cluster step was created.

                  
                

                - **StartDateTime** *(datetime) --* 

                  The date and time when the cluster step execution started.

                  
                

                - **EndDateTime** *(datetime) --* 

                  The date and time when the cluster step execution completed or failed.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

=======
Waiters
=======


The available waiters are:

* :py:class:`EMR.Waiter.ClusterRunning`



.. py:class:: EMR.Waiter.ClusterRunning

  ::

    
    waiter = client.get_waiter('cluster_running')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`EMR.Client.describe_cluster` every 30 seconds until a successful state is reached. An error is returned after 60 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          ClusterId='string'
      )
    :type ClusterId: string
    :param ClusterId: **[REQUIRED]** 

      The identifier of the cluster to describe.

      

    
    
    :returns: None