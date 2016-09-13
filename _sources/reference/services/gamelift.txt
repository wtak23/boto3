

.. _Amazon GameLift Developer Guide: http://docs.aws.amazon.com/gamelift/latest/developerguide/
.. _Amazon EC2 Instance Types: https://aws.amazon.com/ec2/instance-types/
.. _Amazon S3 documentation: http://aws.amazon.com/documentation/s3/
.. _AWS Service Limits: http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html#limits_gamelift
.. _CIDR notation: https://tools.ietf.org/id/cidr
.. _service limits: http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html#limits_gamelift


********
GameLift
********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: GameLift.Client

  A low-level client representing Amazon GameLift::

    
    import boto3
    
    client = boto3.client('gamelift')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_alias`

  
  *   :py:meth:`create_build`

  
  *   :py:meth:`create_fleet`

  
  *   :py:meth:`create_game_session`

  
  *   :py:meth:`create_player_session`

  
  *   :py:meth:`create_player_sessions`

  
  *   :py:meth:`delete_alias`

  
  *   :py:meth:`delete_build`

  
  *   :py:meth:`delete_fleet`

  
  *   :py:meth:`delete_scaling_policy`

  
  *   :py:meth:`describe_alias`

  
  *   :py:meth:`describe_build`

  
  *   :py:meth:`describe_ec2_instance_limits`

  
  *   :py:meth:`describe_fleet_attributes`

  
  *   :py:meth:`describe_fleet_capacity`

  
  *   :py:meth:`describe_fleet_events`

  
  *   :py:meth:`describe_fleet_port_settings`

  
  *   :py:meth:`describe_fleet_utilization`

  
  *   :py:meth:`describe_game_session_details`

  
  *   :py:meth:`describe_game_sessions`

  
  *   :py:meth:`describe_player_sessions`

  
  *   :py:meth:`describe_runtime_configuration`

  
  *   :py:meth:`describe_scaling_policies`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_game_session_log_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_aliases`

  
  *   :py:meth:`list_builds`

  
  *   :py:meth:`list_fleets`

  
  *   :py:meth:`put_scaling_policy`

  
  *   :py:meth:`request_upload_credentials`

  
  *   :py:meth:`resolve_alias`

  
  *   :py:meth:`search_game_sessions`

  
  *   :py:meth:`update_alias`

  
  *   :py:meth:`update_build`

  
  *   :py:meth:`update_fleet_attributes`

  
  *   :py:meth:`update_fleet_capacity`

  
  *   :py:meth:`update_fleet_port_settings`

  
  *   :py:meth:`update_game_session`

  
  *   :py:meth:`update_runtime_configuration`

  

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


  .. py:method:: create_alias(**kwargs)

    

    Creates an alias for a fleet. You can use an alias to anonymize your fleet by referencing an alias instead of a specific fleet when you create game sessions. Amazon GameLift supports two types of routing strategies for aliases: simple and terminal. Use a simple alias to point to an active fleet. Use a terminal alias to display a message to incoming traffic instead of routing players to an active fleet. This option is useful when a game server is no longer supported but you want to provide better messaging than a standard 404 error.

     

    To create a fleet alias, specify an alias name, routing strategy, and optional description. If successful, a new alias record is returned, including an alias ID, which you can reference when creating a game session. To reassign the alias to another fleet ID, call  UpdateAlias .

    

    **Request Syntax** 
    ::

      response = client.create_alias(
          Name='string',
          Description='string',
          RoutingStrategy={
              'Type': 'SIMPLE'|'TERMINAL',
              'FleetId': 'string',
              'Message': 'string'
          }
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      Descriptive label associated with an alias. Alias names do not need to be unique.

      

    
    :type Description: string
    :param Description: 

      Human-readable description of an alias.

      

    
    :type RoutingStrategy: dict
    :param RoutingStrategy: **[REQUIRED]** 

      Object specifying the fleet and routing type to use for the alias.

      

    
      - **Type** *(string) --* 

        Type of routing strategy.

         

        Possible routing types include the following:

         

        
        * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets.
        
        * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded.
        

        

      
      - **FleetId** *(string) --* 

        Unique identifier for a fleet.

        

      
      - **Message** *(string) --* 

        Message text to be used with a terminal routing strategy.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Alias': {
                'AliasId': 'string',
                'Name': 'string',
                'Description': 'string',
                'RoutingStrategy': {
                    'Type': 'SIMPLE'|'TERMINAL',
                    'FleetId': 'string',
                    'Message': 'string'
                },
                'CreationTime': datetime(2015, 1, 1),
                'LastUpdatedTime': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Alias** *(dict) --* 

          Object containing the newly created alias record.

          
          

          - **AliasId** *(string) --* 

            Unique identifier for a fleet alias.

            
          

          - **Name** *(string) --* 

            Descriptive label associated with an alias. Alias names do not need to be unique.

            
          

          - **Description** *(string) --* 

            Human-readable description of an alias.

            
          

          - **RoutingStrategy** *(dict) --* 

            Routing configuration for a fleet alias. 

            
            

            - **Type** *(string) --* 

              Type of routing strategy.

               

              Possible routing types include the following:

               

              
              * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets.
              
              * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded.
              

              
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **Message** *(string) --* 

              Message text to be used with a terminal routing strategy.

              
        
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **LastUpdatedTime** *(datetime) --* 

            Time stamp indicating when this data object was last modified. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
      
    

  .. py:method:: create_build(**kwargs)

    

    Initializes a new build record and generates information required to upload a game build to Amazon GameLift. Once the build record has been created and its status is ``INITIALIZED`` , you can upload your game build.

     

    .. warning::

       

      Do not use this API action unless you are using your own Amazon Simple Storage Service (Amazon S3) client and need to manually upload your build files. Instead, to create a build, use the CLI command ``upload-build`` , which creates a new build record and uploads the build files in one step. (See the `Amazon GameLift Developer Guide`_ help on packaging and uploading your build.) 

       

     

    To create a new build, identify the operating system of the game server binaries. All game servers in a build must use the same operating system. Optionally, specify a build name and version; this metadata is stored with other properties in the build record and is displayed in the GameLift console (it is not visible to players). If successful, this action returns the newly created build record along with the Amazon S3 storage location and AWS account credentials. Use the location and credentials to upload your game build.

    

    **Request Syntax** 
    ::

      response = client.create_build(
          Name='string',
          Version='string',
          StorageLocation={
              'Bucket': 'string',
              'Key': 'string',
              'RoleArn': 'string'
          },
          OperatingSystem='WINDOWS_2012'|'AMAZON_LINUX'
      )
    :type Name: string
    :param Name: 

      Descriptive label associated with a build. Build names do not need to be unique. A build name can be changed later using `` UpdateBuild`` .

      

    
    :type Version: string
    :param Version: 

      Version associated with this build. Version strings do not need to be unique to a build. A build version can be changed later using `` UpdateBuild`` .

      

    
    :type StorageLocation: dict
    :param StorageLocation: 

      Location in Amazon Simple Storage Service (Amazon S3) where a build's files are stored. This location is assigned in response to a  CreateBuild call, and is always in the same region as the service used to create the build. For more details see the `Amazon S3 documentation`_ .

      

    
      - **Bucket** *(string) --* 

        Amazon S3 bucket identifier.

        

      
      - **Key** *(string) --* 

        Amazon S3 bucket key.

        

      
      - **RoleArn** *(string) --* 

        Amazon resource number for the cross-account access role that allows GameLift access to the S3 bucket.

        

      
    
    :type OperatingSystem: string
    :param OperatingSystem: 

      Operating system that the game server binaries are built to run on. This value determines the type of fleet resources that you can use for this build.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Build': {
                'BuildId': 'string',
                'Name': 'string',
                'Version': 'string',
                'Status': 'INITIALIZED'|'READY'|'FAILED',
                'SizeOnDisk': 123,
                'OperatingSystem': 'WINDOWS_2012'|'AMAZON_LINUX',
                'CreationTime': datetime(2015, 1, 1)
            },
            'UploadCredentials': {
                'AccessKeyId': 'string',
                'SecretAccessKey': 'string',
                'SessionToken': 'string'
            },
            'StorageLocation': {
                'Bucket': 'string',
                'Key': 'string',
                'RoleArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Build** *(dict) --* 

          Set of properties for the newly created build.

          
          

          - **BuildId** *(string) --* 

            Unique identifier for a build.

            
          

          - **Name** *(string) --* 

            Descriptive label associated with a build. Build names do not need to be unique. It can be set using  CreateBuild or  UpdateBuild .

            
          

          - **Version** *(string) --* 

            Version associated with this build. Version strings do not need to be unique to a build. This value can be set using  CreateBuild or  UpdateBuild .

            
          

          - **Status** *(string) --* 

            Current status of the build.

             

            Possible build statuses include the following:

             

            
            * **INITIALIZED** – A new build has been defined, but no files have been uploaded. You cannot create fleets for builds that are in this status. When a build is successfully created, the build status is set to this value. 
            
            * **READY** – The game build has been successfully uploaded. You can now create new fleets for this build.
            
            * **FAILED** – The game build upload failed. You cannot create new fleets for this build. 
            

            
          

          - **SizeOnDisk** *(integer) --* 

            File size of the uploaded game build, expressed in bytes. When the build status is ``INITIALIZED`` , this value is 0.

            
          

          - **OperatingSystem** *(string) --* 

            Operating system that the game server binaries are built to run on. This value determines the type of fleet resources that you can use for this build.

            
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
      
        

        - **UploadCredentials** *(dict) --* 

          AWS credentials required when uploading a game build to the storage location. These credentials have a limited lifespan and are valid only for the build they were issued for. If you need to get fresh credentials, call `` RequestUploadCredentials`` .

          
          

          - **AccessKeyId** *(string) --* 

            Access key for an AWS account.

            
          

          - **SecretAccessKey** *(string) --* 

            Secret key for an AWS account.

            
          

          - **SessionToken** *(string) --* 

            Token specific to a build ID.

            
      
        

        - **StorageLocation** *(dict) --* 

          Amazon S3 path and key, identifying where the game build files are stored.

          
          

          - **Bucket** *(string) --* 

            Amazon S3 bucket identifier.

            
          

          - **Key** *(string) --* 

            Amazon S3 bucket key.

            
          

          - **RoleArn** *(string) --* 

            Amazon resource number for the cross-account access role that allows GameLift access to the S3 bucket.

            
      
    

  .. py:method:: create_fleet(**kwargs)

    

    Creates a new fleet to run your game servers. A fleet is a set of Amazon Elastic Compute Cloud (Amazon EC2) instances, each of which can run multiple server processes to host game sessions. You configure a fleet to create instances with certain hardware specifications (see `Amazon EC2 Instance Types`_ for more information), and deploy a specified game build to each instance. A newly created fleet passes through several statuses; once it reaches the ``ACTIVE`` status, it can begin hosting game sessions.

     

    To create a new fleet, provide a fleet name, an EC2 instance type, and a build ID of the game build to deploy. You can also configure the new fleet with the following settings: (1) a runtime configuration describing what server processes to run on each instance in the fleet (required to create fleet), (2) access permissions for inbound traffic, (3) fleet-wide game session protection, and (4) the location of default log files for GameLift to upload and store.

     

    If the ``CreateFleet`` call is successful, Amazon GameLift performs the following tasks:

     

     
    * Creates a fleet record and sets the status to ``NEW`` (followed by other statuses as the fleet is activated).
     
    * Sets the fleet's capacity to 1 "desired", which causes GameLift to start one new EC2 instance.
     
    * Starts launching server processes on the instance. If the fleet is configured to run multiple server processes per instance, GameLift staggers each launch by a few seconds.
     
    * Begins writing events to the fleet event log, which can be accessed in the GameLift console.
     
    * Sets the fleet's status to ``ACTIVE`` once one server process in the fleet is ready to host a game session.
     

     

    After a fleet is created, use the following actions to change fleet properties and configuration:

     

     
    *  UpdateFleetAttributes -- Update fleet metadata, including name and description.
     
    *  UpdateFleetCapacity -- Increase or decrease the number of instances you want the fleet to maintain.
     
    *  UpdateFleetPortSettings -- Change the IP address and port ranges that allow access to incoming traffic.
     
    *  UpdateRuntimeConfiguration -- Change how server processes are launched in the fleet, including launch path, launch parameters, and the number of concurrent processes.
     

    

    **Request Syntax** 
    ::

      response = client.create_fleet(
          Name='string',
          Description='string',
          BuildId='string',
          ServerLaunchPath='string',
          ServerLaunchParameters='string',
          LogPaths=[
              'string',
          ],
          EC2InstanceType='t2.micro'|'t2.small'|'t2.medium'|'t2.large'|'c3.large'|'c3.xlarge'|'c3.2xlarge'|'c3.4xlarge'|'c3.8xlarge'|'c4.large'|'c4.xlarge'|'c4.2xlarge'|'c4.4xlarge'|'c4.8xlarge'|'r3.large'|'r3.xlarge'|'r3.2xlarge'|'r3.4xlarge'|'r3.8xlarge'|'m3.medium'|'m3.large'|'m3.xlarge'|'m3.2xlarge'|'m4.large'|'m4.xlarge'|'m4.2xlarge'|'m4.4xlarge'|'m4.10xlarge',
          EC2InboundPermissions=[
              {
                  'FromPort': 123,
                  'ToPort': 123,
                  'IpRange': 'string',
                  'Protocol': 'TCP'|'UDP'
              },
          ],
          NewGameSessionProtectionPolicy='NoProtection'|'FullProtection',
          RuntimeConfiguration={
              'ServerProcesses': [
                  {
                      'LaunchPath': 'string',
                      'Parameters': 'string',
                      'ConcurrentExecutions': 123
                  },
              ]
          }
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      Descriptive label associated with a fleet. Fleet names do not need to be unique.

      

    
    :type Description: string
    :param Description: 

      Human-readable description of a fleet.

      

    
    :type BuildId: string
    :param BuildId: **[REQUIRED]** 

      Unique identifier of the build to be deployed on the new fleet. The build must have been successfully uploaded to GameLift and be in a ``READY`` status. This fleet setting cannot be changed once the fleet is created.

      

    
    :type ServerLaunchPath: string
    :param ServerLaunchPath: 

      This parameter is no longer used. Instead, specify a server launch path using the ``RuntimeConfiguration`` parameter. (Requests that specify a server launch path and launch parameters instead of a runtime configuration will continue to work.)

      

    
    :type ServerLaunchParameters: string
    :param ServerLaunchParameters: 

      This parameter is no longer used. Instead, specify server launch parameters in the ``RuntimeConfiguration`` parameter. (Requests that specify a server launch path and launch parameters instead of a runtime configuration will continue to work.)

      

    
    :type LogPaths: list
    :param LogPaths: 

      Location of default log files. When a server process is shut down, Amazon GameLift captures and stores any log files in this location. These logs are in addition to game session logs; see more on game session logs in the `Amazon GameLift Developer Guide`_ . If no default log path for a fleet is specified, GameLift will automatically upload logs stored on each instance at ``C:\game\logs`` . Use the GameLift console to access stored logs. 

      

    
      - *(string) --* 

      
  
    :type EC2InstanceType: string
    :param EC2InstanceType: **[REQUIRED]** 

      Name of an EC2 instance type that is supported in Amazon GameLift. A fleet instance type determines the computing resources of each instance in the fleet, including CPU, memory, storage, and networking capacity. GameLift supports the following EC2 instance types. See `Amazon EC2 Instance Types`_ for detailed descriptions.

      

    
    :type EC2InboundPermissions: list
    :param EC2InboundPermissions: 

      Range of IP addresses and port settings that permit inbound traffic to access server processes running on the fleet. If no inbound permissions are set, including both IP address range and port range, the server processes in the fleet cannot accept connections. You can specify one or more sets of permissions for a fleet.

      

    
      - *(dict) --* 

        A range of IP addresses and port settings that allow inbound traffic to connect to server processes on GameLift. Each game session hosted on a fleet is assigned a unique combination of IP address and port number, which must fall into the fleet's allowed ranges. This combination is included in the  GameSession object. 

        

      
        - **FromPort** *(integer) --* **[REQUIRED]** 

          Starting value for a range of allowed port numbers. 

          

        
        - **ToPort** *(integer) --* **[REQUIRED]** 

          Ending value for a range of allowed port numbers. Port numbers are end-inclusive. This value must be higher than ``FromPort`` .

          

        
        - **IpRange** *(string) --* **[REQUIRED]** 

          Range of allowed IP addresses. This value must be expressed in `CIDR notation`_ . Example: "``000.000.000.000/[subnet mask]`` " or optionally the shortened version "``0.0.0.0/[subnet mask]`` ".

          

        
        - **Protocol** *(string) --* **[REQUIRED]** 

          Network communication protocol used by the fleet.

          

        
      
  
    :type NewGameSessionProtectionPolicy: string
    :param NewGameSessionProtectionPolicy: 

      Game session protection policy to apply to all instances in this fleet. If this parameter is not set, instances in this fleet default to no protection. You can change a fleet's protection policy using UpdateFleetAttributes, but this change will only affect sessions created after the policy change. You can also set protection for individual instances using  UpdateGameSession .

       

      
      * **NoProtection** – The game session can be terminated during a scale-down event.
       
      * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event.
      

      

    
    :type RuntimeConfiguration: dict
    :param RuntimeConfiguration: 

      Instructions for launching server processes on each instance in the fleet. The runtime configuration for a fleet has a collection of server process configurations, one for each type of server process to run on an instance. A server process configuration specifies the location of the server executable, launch parameters, and the number of concurrent processes with that configuration to maintain on each instance. A ``CreateFleet`` request must include a runtime configuration with at least one server process configuration; otherwise the request will fail with an invalid request exception. (This parameter replaces the parameters ``ServerLaunchPath`` and ``ServerLaunchParameters`` ; requests that contain values for these parameters instead of a runtime configuration will continue to work.) 

      

    
      - **ServerProcesses** *(list) --* 

        Collection of server process configurations describing what server processes to run on each instance in a fleet 

        

      
        - *(dict) --* 

          A set of instructions for launching server processes on each instance in a fleet. Each instruction set identifies the location of the server executable, optional launch parameters, and the number of server processes with this configuration to maintain concurrently on the instance. Server process configurations make up a fleet's `` RuntimeConfiguration`` .

          

        
          - **LaunchPath** *(string) --* **[REQUIRED]** 

            Location in the game build of the server executable. All game builds are installed on instances at the root ``C:\game\...`` , so an executable file located at ``MyGame\latest\server.exe`` has a launch path of "``C:\game\MyGame\latest\server.exe`` ". 

            

          
          - **Parameters** *(string) --* 

            Optional list of parameters to pass to the server executable on launch.

            

          
          - **ConcurrentExecutions** *(integer) --* **[REQUIRED]** 

            Number of server processes using this configuration to run concurrently on an instance. 

            

          
        
    
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FleetAttributes': {
                'FleetId': 'string',
                'Description': 'string',
                'Name': 'string',
                'CreationTime': datetime(2015, 1, 1),
                'TerminationTime': datetime(2015, 1, 1),
                'Status': 'NEW'|'DOWNLOADING'|'VALIDATING'|'BUILDING'|'ACTIVATING'|'ACTIVE'|'DELETING'|'ERROR'|'TERMINATED',
                'BuildId': 'string',
                'ServerLaunchPath': 'string',
                'ServerLaunchParameters': 'string',
                'LogPaths': [
                    'string',
                ],
                'NewGameSessionProtectionPolicy': 'NoProtection'|'FullProtection',
                'OperatingSystem': 'WINDOWS_2012'|'AMAZON_LINUX'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **FleetAttributes** *(dict) --* 

          Properties for the newly created fleet.

          
          

          - **FleetId** *(string) --* 

            Unique identifier for a fleet.

            
          

          - **Description** *(string) --* 

            Human-readable description of the fleet.

            
          

          - **Name** *(string) --* 

            Descriptive label associated with a fleet. Fleet names do not need to be unique.

            
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **TerminationTime** *(datetime) --* 

            Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **Status** *(string) --* 

            Current status of the fleet.

             

            Possible fleet statuses include the following:

             

            
            * **NEW** – A new fleet has been defined and desired instances is set to 1. 
            
            * **DOWNLOADING/VALIDATING/BUILDING/ACTIVATING** – GameLift is setting up the new fleet, creating new instances with the game build and starting server processes.
            
            * **ACTIVE** – Hosts can now accept game sessions.
            
            * **ERROR** – An error occurred when downloading, validating, building, or activating the fleet.
            
            * **DELETING** – Hosts are responding to a delete fleet request.
            
            * **TERMINATED** – The fleet no longer exists.
            

            
          

          - **BuildId** *(string) --* 

            Unique identifier for a build.

            
          

          - **ServerLaunchPath** *(string) --* 

            Path to a game server executable in the fleet's build, specified for fleets created prior to 2016-08-04 (or AWS SDK v. 0.12.16). Server launch paths for fleets created after this date are specified in the fleet's `` RuntimeConfiguration`` .

            
          

          - **ServerLaunchParameters** *(string) --* 

            Game server launch parameters specified for fleets created prior to 2016-08-04 (or AWS SDK v. 0.12.16). Server launch parameters for fleets created after this date are specified in the fleet's `` RuntimeConfiguration`` .

            
          

          - **LogPaths** *(list) --* 

            Location of default log files. When a server process is shut down, Amazon GameLift captures and stores any log files in this location. These logs are in addition to game session logs; see more on game session logs in the `Amazon GameLift Developer Guide`_ . If no default log path for a fleet is specified, GameLift will automatically upload logs stored on each instance at ``C:\game\logs`` . Use the GameLift console to access stored logs. 

            
            

            - *(string) --* 
        
          

          - **NewGameSessionProtectionPolicy** *(string) --* 

            Type of game session protection to set for all new instances started in the fleet.

             

            
            * **NoProtection** – The game session can be terminated during a scale-down event.
             
            * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event.
            

            
          

          - **OperatingSystem** *(string) --* 

            Operating system of the fleet's computing resources. A fleet's operating system depends on the OS specified for the build that is deployed on this fleet.

            
      
    

  .. py:method:: create_game_session(**kwargs)

    

    Creates a multiplayer game session for players. This action creates a game session record and assigns the new session to an instance in the specified fleet, which initializes a new server process to host the game session. A fleet must be in an ``ACTIVE`` status before a game session can be created in it.

     

    To create a game session, specify either a fleet ID or an alias ID and indicate the maximum number of players the game session allows. You can also provide a name and a set of properties for your game (optional). If successful, a  GameSession object is returned containing session properties, including an IP address. By default, newly created game sessions are set to accept adding any new players to the game session. Use  UpdateGameSession to change the creation policy.

    

    **Request Syntax** 
    ::

      response = client.create_game_session(
          FleetId='string',
          AliasId='string',
          MaximumPlayerSessionCount=123,
          Name='string',
          GameProperties=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type FleetId: string
    :param FleetId: 

      Unique identifier for a fleet. Each request must reference either a fleet ID or alias ID, but not both.

      

    
    :type AliasId: string
    :param AliasId: 

      Unique identifier for a fleet alias. Each request must reference either a fleet ID or alias ID, but not both.

      

    
    :type MaximumPlayerSessionCount: integer
    :param MaximumPlayerSessionCount: **[REQUIRED]** 

      Maximum number of players that can be connected simultaneously to the game session. 

      

    
    :type Name: string
    :param Name: 

      Descriptive label associated with a game session. Session names do not need to be unique.

      

    
    :type GameProperties: list
    :param GameProperties: 

      Set of properties used to administer a game session. These properties are passed to the server process hosting it. 

      

    
      - *(dict) --* 

        Set of key-value pairs containing information a server process requires to set up a game session. This object allows you to pass in any set of data needed for your game. For more information, see the `Amazon GameLift Developer Guide`_ .

        

      
        - **Key** *(string) --* **[REQUIRED]** 

        
        - **Value** *(string) --* **[REQUIRED]** 

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GameSession': {
                'GameSessionId': 'string',
                'Name': 'string',
                'FleetId': 'string',
                'CreationTime': datetime(2015, 1, 1),
                'TerminationTime': datetime(2015, 1, 1),
                'CurrentPlayerSessionCount': 123,
                'MaximumPlayerSessionCount': 123,
                'Status': 'ACTIVE'|'ACTIVATING'|'TERMINATED'|'TERMINATING',
                'GameProperties': [
                    {
                        'Key': 'string',
                        'Value': 'string'
                    },
                ],
                'IpAddress': 'string',
                'Port': 123,
                'PlayerSessionCreationPolicy': 'ACCEPT_ALL'|'DENY_ALL'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **GameSession** *(dict) --* 

          Object containing the newly created game session record.

          
          

          - **GameSessionId** *(string) --* 

            Unique identifier for a game session.

            
          

          - **Name** *(string) --* 

            Descriptive label associated with a game session. Session names do not need to be unique.

            
          

          - **FleetId** *(string) --* 

            Unique identifier for a fleet.

            
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **TerminationTime** *(datetime) --* 

            Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **CurrentPlayerSessionCount** *(integer) --* 

            Number of players currently in the game session.

            
          

          - **MaximumPlayerSessionCount** *(integer) --* 

            Maximum number of players allowed in the game session.

            
          

          - **Status** *(string) --* 

            Current status of the game session. A game session must be in an ``ACTIVE`` status to have player sessions.

            
          

          - **GameProperties** *(list) --* 

            Set of custom properties for the game session.

            
            

            - *(dict) --* 

              Set of key-value pairs containing information a server process requires to set up a game session. This object allows you to pass in any set of data needed for your game. For more information, see the `Amazon GameLift Developer Guide`_ .

              
              

              - **Key** *(string) --* 
              

              - **Value** *(string) --* 
          
        
          

          - **IpAddress** *(string) --* 

            IP address of the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

            
          

          - **Port** *(integer) --* 

            Port number for the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

            
          

          - **PlayerSessionCreationPolicy** *(string) --* 

            Indicates whether or not the game session is accepting new players.

            
      
    

  .. py:method:: create_player_session(**kwargs)

    

    Adds a player to a game session and creates a player session record. A game session must be in an ``ACTIVE`` status, have a creation policy of ``ALLOW_ALL`` , and have an open player slot before players can be added to the session.

     

    To create a player session, specify a game session ID and player ID. If successful, the player is added to the game session and a new  PlayerSession object is returned. 

    

    **Request Syntax** 
    ::

      response = client.create_player_session(
          GameSessionId='string',
          PlayerId='string'
      )
    :type GameSessionId: string
    :param GameSessionId: **[REQUIRED]** 

      Unique identifier for a game session. Specify the game session you want to add a player to.

      

    
    :type PlayerId: string
    :param PlayerId: **[REQUIRED]** 

      Unique identifier for the player to be added.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PlayerSession': {
                'PlayerSessionId': 'string',
                'PlayerId': 'string',
                'GameSessionId': 'string',
                'FleetId': 'string',
                'CreationTime': datetime(2015, 1, 1),
                'TerminationTime': datetime(2015, 1, 1),
                'Status': 'RESERVED'|'ACTIVE'|'COMPLETED'|'TIMEDOUT',
                'IpAddress': 'string',
                'Port': 123
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **PlayerSession** *(dict) --* 

          Object containing the newly created player session record.

          
          

          - **PlayerSessionId** *(string) --* 

            Unique identifier for a player session.

            
          

          - **PlayerId** *(string) --* 

            Unique identifier for a player.

            
          

          - **GameSessionId** *(string) --* 

            Unique identifier for a game session.

            
          

          - **FleetId** *(string) --* 

            Unique identifier for a fleet.

            
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **TerminationTime** *(datetime) --* 

            Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **Status** *(string) --* 

            Current status of the player session.

             

            Possible player session statuses include the following:

             

            
            * **RESERVED** – The player session request has been received, but the player has not yet connected to the server process and/or been validated. 
            
            * **ACTIVE** – The player has been validated by the server process and is currently connected.
            
            * **COMPLETED** – The player connection has been dropped.
            
            * **TIMEDOUT** – A player session request was received, but the player did not connect and/or was not validated within the time-out limit (60 seconds).
            

            
          

          - **IpAddress** *(string) --* 

            Game session IP address. All player sessions reference the game session location. 

            
          

          - **Port** *(integer) --* 

            Port number for the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

            
      
    

  .. py:method:: create_player_sessions(**kwargs)

    

    Adds a group of players to a game session. Similar to  CreatePlayerSession , this action allows you to add multiple players in a single call, which is useful for games that provide party and/or matchmaking features. A game session must be in an ``ACTIVE`` status, have a creation policy of ``ALLOW_ALL`` , and have an open player slot before players can be added to the session.

     

    To create player sessions, specify a game session ID and a list of player IDs. If successful, the players are added to the game session and a set of new  PlayerSession objects is returned. 

    

    **Request Syntax** 
    ::

      response = client.create_player_sessions(
          GameSessionId='string',
          PlayerIds=[
              'string',
          ]
      )
    :type GameSessionId: string
    :param GameSessionId: **[REQUIRED]** 

      Unique identifier for a game session. 

      

    
    :type PlayerIds: list
    :param PlayerIds: **[REQUIRED]** 

      List of unique identifiers for the players to be added.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PlayerSessions': [
                {
                    'PlayerSessionId': 'string',
                    'PlayerId': 'string',
                    'GameSessionId': 'string',
                    'FleetId': 'string',
                    'CreationTime': datetime(2015, 1, 1),
                    'TerminationTime': datetime(2015, 1, 1),
                    'Status': 'RESERVED'|'ACTIVE'|'COMPLETED'|'TIMEDOUT',
                    'IpAddress': 'string',
                    'Port': 123
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **PlayerSessions** *(list) --* 

          Collection of player session objects created for the added players.

          
          

          - *(dict) --* 

            Properties describing a player session.

            
            

            - **PlayerSessionId** *(string) --* 

              Unique identifier for a player session.

              
            

            - **PlayerId** *(string) --* 

              Unique identifier for a player.

              
            

            - **GameSessionId** *(string) --* 

              Unique identifier for a game session.

              
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **CreationTime** *(datetime) --* 

              Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **TerminationTime** *(datetime) --* 

              Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **Status** *(string) --* 

              Current status of the player session.

               

              Possible player session statuses include the following:

               

              
              * **RESERVED** – The player session request has been received, but the player has not yet connected to the server process and/or been validated. 
              
              * **ACTIVE** – The player has been validated by the server process and is currently connected.
              
              * **COMPLETED** – The player connection has been dropped.
              
              * **TIMEDOUT** – A player session request was received, but the player did not connect and/or was not validated within the time-out limit (60 seconds).
              

              
            

            - **IpAddress** *(string) --* 

              Game session IP address. All player sessions reference the game session location. 

              
            

            - **Port** *(integer) --* 

              Port number for the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

              
        
      
    

  .. py:method:: delete_alias(**kwargs)

    

    Deletes an alias. This action removes all record of the alias; game clients attempting to access a server process using the deleted alias receive an error. To delete an alias, specify the alias ID to be deleted.

    

    **Request Syntax** 
    ::

      response = client.delete_alias(
          AliasId='string'
      )
    :type AliasId: string
    :param AliasId: **[REQUIRED]** 

      Unique identifier for a fleet alias. Specify the alias you want to delete. 

      

    
    
    :returns: None

  .. py:method:: delete_build(**kwargs)

    

    Deletes a build. This action permanently deletes the build record and any uploaded build files.

     

    To delete a build, specify its ID. Deleting a build does not affect the status of any active fleets using the build, but you can no longer create new fleets with the deleted build.

    

    **Request Syntax** 
    ::

      response = client.delete_build(
          BuildId='string'
      )
    :type BuildId: string
    :param BuildId: **[REQUIRED]** 

      Unique identifier for the build you want to delete. 

      

    
    
    :returns: None

  .. py:method:: delete_fleet(**kwargs)

    

    Deletes everything related to a fleet. Before deleting a fleet, you must set the fleet's desired capacity to zero. See  UpdateFleetCapacity .

     

    This action removes the fleet's resources and the fleet record. Once a fleet is deleted, you can no longer use that fleet.

    

    **Request Syntax** 
    ::

      response = client.delete_fleet(
          FleetId='string'
      )
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier for the fleet you want to delete.

      

    
    
    :returns: None

  .. py:method:: delete_scaling_policy(**kwargs)

    

    Deletes a fleet scaling policy. This action means that the policy is no longer in force and removes all record of it. To delete a scaling policy, specify both the scaling policy name and the fleet ID it is associated with. 

    

    **Request Syntax** 
    ::

      response = client.delete_scaling_policy(
          Name='string',
          FleetId='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      Descriptive label associated with a scaling policy. Policy names do not need to be unique.

      

    
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier for a fleet.

      

    
    
    :returns: None

  .. py:method:: describe_alias(**kwargs)

    

    Retrieves properties for a specified alias. To get the alias, specify an alias ID. If successful, an  Alias object is returned.

    

    **Request Syntax** 
    ::

      response = client.describe_alias(
          AliasId='string'
      )
    :type AliasId: string
    :param AliasId: **[REQUIRED]** 

      Unique identifier for a fleet alias. Specify the alias you want to retrieve. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Alias': {
                'AliasId': 'string',
                'Name': 'string',
                'Description': 'string',
                'RoutingStrategy': {
                    'Type': 'SIMPLE'|'TERMINAL',
                    'FleetId': 'string',
                    'Message': 'string'
                },
                'CreationTime': datetime(2015, 1, 1),
                'LastUpdatedTime': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Alias** *(dict) --* 

          Object containing the requested alias.

          
          

          - **AliasId** *(string) --* 

            Unique identifier for a fleet alias.

            
          

          - **Name** *(string) --* 

            Descriptive label associated with an alias. Alias names do not need to be unique.

            
          

          - **Description** *(string) --* 

            Human-readable description of an alias.

            
          

          - **RoutingStrategy** *(dict) --* 

            Routing configuration for a fleet alias. 

            
            

            - **Type** *(string) --* 

              Type of routing strategy.

               

              Possible routing types include the following:

               

              
              * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets.
              
              * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded.
              

              
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **Message** *(string) --* 

              Message text to be used with a terminal routing strategy.

              
        
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **LastUpdatedTime** *(datetime) --* 

            Time stamp indicating when this data object was last modified. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
      
    

  .. py:method:: describe_build(**kwargs)

    

    Retrieves properties for a build. To get a build record, specify a build ID. If successful, an object containing the build properties is returned.

    

    **Request Syntax** 
    ::

      response = client.describe_build(
          BuildId='string'
      )
    :type BuildId: string
    :param BuildId: **[REQUIRED]** 

      Unique identifier of the build that you want to retrieve properties for. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Build': {
                'BuildId': 'string',
                'Name': 'string',
                'Version': 'string',
                'Status': 'INITIALIZED'|'READY'|'FAILED',
                'SizeOnDisk': 123,
                'OperatingSystem': 'WINDOWS_2012'|'AMAZON_LINUX',
                'CreationTime': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Build** *(dict) --* 

          Set of properties describing the requested build.

          
          

          - **BuildId** *(string) --* 

            Unique identifier for a build.

            
          

          - **Name** *(string) --* 

            Descriptive label associated with a build. Build names do not need to be unique. It can be set using  CreateBuild or  UpdateBuild .

            
          

          - **Version** *(string) --* 

            Version associated with this build. Version strings do not need to be unique to a build. This value can be set using  CreateBuild or  UpdateBuild .

            
          

          - **Status** *(string) --* 

            Current status of the build.

             

            Possible build statuses include the following:

             

            
            * **INITIALIZED** – A new build has been defined, but no files have been uploaded. You cannot create fleets for builds that are in this status. When a build is successfully created, the build status is set to this value. 
            
            * **READY** – The game build has been successfully uploaded. You can now create new fleets for this build.
            
            * **FAILED** – The game build upload failed. You cannot create new fleets for this build. 
            

            
          

          - **SizeOnDisk** *(integer) --* 

            File size of the uploaded game build, expressed in bytes. When the build status is ``INITIALIZED`` , this value is 0.

            
          

          - **OperatingSystem** *(string) --* 

            Operating system that the game server binaries are built to run on. This value determines the type of fleet resources that you can use for this build.

            
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
      
    

  .. py:method:: describe_ec2_instance_limits(**kwargs)

    

    Retrieves the following information for the specified EC2 instance type:

     

     
    * maximum number of instances allowed per AWS account (service limit)
     
    * current usage level for the AWS account 
     

     

    Service limits vary depending on region. Available regions for GameLift can be found in the AWS Management Console for GameLift (see the drop-down list in the upper right corner).

    

    **Request Syntax** 
    ::

      response = client.describe_ec2_instance_limits(
          EC2InstanceType='t2.micro'|'t2.small'|'t2.medium'|'t2.large'|'c3.large'|'c3.xlarge'|'c3.2xlarge'|'c3.4xlarge'|'c3.8xlarge'|'c4.large'|'c4.xlarge'|'c4.2xlarge'|'c4.4xlarge'|'c4.8xlarge'|'r3.large'|'r3.xlarge'|'r3.2xlarge'|'r3.4xlarge'|'r3.8xlarge'|'m3.medium'|'m3.large'|'m3.xlarge'|'m3.2xlarge'|'m4.large'|'m4.xlarge'|'m4.2xlarge'|'m4.4xlarge'|'m4.10xlarge'
      )
    :type EC2InstanceType: string
    :param EC2InstanceType: 

      Name of an EC2 instance type that is supported in Amazon GameLift. A fleet instance type determines the computing resources of each instance in the fleet, including CPU, memory, storage, and networking capacity. GameLift supports the following EC2 instance types. See `Amazon EC2 Instance Types`_ for detailed descriptions. Leave this parameter blank to retrieve limits for all types.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EC2InstanceLimits': [
                {
                    'EC2InstanceType': 't2.micro'|'t2.small'|'t2.medium'|'t2.large'|'c3.large'|'c3.xlarge'|'c3.2xlarge'|'c3.4xlarge'|'c3.8xlarge'|'c4.large'|'c4.xlarge'|'c4.2xlarge'|'c4.4xlarge'|'c4.8xlarge'|'r3.large'|'r3.xlarge'|'r3.2xlarge'|'r3.4xlarge'|'r3.8xlarge'|'m3.medium'|'m3.large'|'m3.xlarge'|'m3.2xlarge'|'m4.large'|'m4.xlarge'|'m4.2xlarge'|'m4.4xlarge'|'m4.10xlarge',
                    'CurrentInstances': 123,
                    'InstanceLimit': 123
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **EC2InstanceLimits** *(list) --* 

          Object containing the maximum number of instances for the specified instance type.

          
          

          - *(dict) --* 

            Maximum number of instances allowed based on the Amazon Elastic Compute Cloud (Amazon EC2) instance type. Instance limits can be retrieved by calling  DescribeEC2InstanceLimits .

            
            

            - **EC2InstanceType** *(string) --* 

              Name of an EC2 instance type that is supported in Amazon GameLift. A fleet instance type determines the computing resources of each instance in the fleet, including CPU, memory, storage, and networking capacity. GameLift supports the following EC2 instance types. See `Amazon EC2 Instance Types`_ for detailed descriptions.

              
            

            - **CurrentInstances** *(integer) --* 

              Number of instances of the specified type that are currently in use by this AWS account. 

              
            

            - **InstanceLimit** *(integer) --* 

              Number of instances allowed.

              
        
      
    

  .. py:method:: describe_fleet_attributes(**kwargs)

    

    Retrieves fleet properties, including metadata, status, and configuration, for one or more fleets. You can request attributes for all fleets, or specify a list of one or more fleet IDs. When requesting multiple fleets, use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  FleetAttributes object is returned for each requested fleet ID. When specifying a list of fleet IDs, attribute objects are returned only for fleets that currently exist. 

     

    .. note::

       

      Some API actions may limit the number of fleet IDs allowed in one request. If a request exceeds this limit, the request fails and the error message includes the maximum allowed.

       

    

    **Request Syntax** 
    ::

      response = client.describe_fleet_attributes(
          FleetIds=[
              'string',
          ],
          Limit=123,
          NextToken='string'
      )
    :type FleetIds: list
    :param FleetIds: 

      Unique identifiers for the fleet(s) that you want to retrieve attributes for. To request attributes for all fleets, leave this parameter empty.

      

    
      - *(string) --* 

      
  
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages. This parameter is ignored when the request specifies one or a list of fleet IDs.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. This parameter is ignored when the request specifies one or a list of fleet IDs.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FleetAttributes': [
                {
                    'FleetId': 'string',
                    'Description': 'string',
                    'Name': 'string',
                    'CreationTime': datetime(2015, 1, 1),
                    'TerminationTime': datetime(2015, 1, 1),
                    'Status': 'NEW'|'DOWNLOADING'|'VALIDATING'|'BUILDING'|'ACTIVATING'|'ACTIVE'|'DELETING'|'ERROR'|'TERMINATED',
                    'BuildId': 'string',
                    'ServerLaunchPath': 'string',
                    'ServerLaunchParameters': 'string',
                    'LogPaths': [
                        'string',
                    ],
                    'NewGameSessionProtectionPolicy': 'NoProtection'|'FullProtection',
                    'OperatingSystem': 'WINDOWS_2012'|'AMAZON_LINUX'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **FleetAttributes** *(list) --* 

          Collection of objects containing attribute metadata for each requested fleet ID. 

          
          

          - *(dict) --* 

            General properties describing a fleet.

            
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **Description** *(string) --* 

              Human-readable description of the fleet.

              
            

            - **Name** *(string) --* 

              Descriptive label associated with a fleet. Fleet names do not need to be unique.

              
            

            - **CreationTime** *(datetime) --* 

              Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **TerminationTime** *(datetime) --* 

              Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **Status** *(string) --* 

              Current status of the fleet.

               

              Possible fleet statuses include the following:

               

              
              * **NEW** – A new fleet has been defined and desired instances is set to 1. 
              
              * **DOWNLOADING/VALIDATING/BUILDING/ACTIVATING** – GameLift is setting up the new fleet, creating new instances with the game build and starting server processes.
              
              * **ACTIVE** – Hosts can now accept game sessions.
              
              * **ERROR** – An error occurred when downloading, validating, building, or activating the fleet.
              
              * **DELETING** – Hosts are responding to a delete fleet request.
              
              * **TERMINATED** – The fleet no longer exists.
              

              
            

            - **BuildId** *(string) --* 

              Unique identifier for a build.

              
            

            - **ServerLaunchPath** *(string) --* 

              Path to a game server executable in the fleet's build, specified for fleets created prior to 2016-08-04 (or AWS SDK v. 0.12.16). Server launch paths for fleets created after this date are specified in the fleet's `` RuntimeConfiguration`` .

              
            

            - **ServerLaunchParameters** *(string) --* 

              Game server launch parameters specified for fleets created prior to 2016-08-04 (or AWS SDK v. 0.12.16). Server launch parameters for fleets created after this date are specified in the fleet's `` RuntimeConfiguration`` .

              
            

            - **LogPaths** *(list) --* 

              Location of default log files. When a server process is shut down, Amazon GameLift captures and stores any log files in this location. These logs are in addition to game session logs; see more on game session logs in the `Amazon GameLift Developer Guide`_ . If no default log path for a fleet is specified, GameLift will automatically upload logs stored on each instance at ``C:\game\logs`` . Use the GameLift console to access stored logs. 

              
              

              - *(string) --* 
          
            

            - **NewGameSessionProtectionPolicy** *(string) --* 

              Type of game session protection to set for all new instances started in the fleet.

               

              
              * **NoProtection** – The game session can be terminated during a scale-down event.
               
              * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event.
              

              
            

            - **OperatingSystem** *(string) --* 

              Operating system of the fleet's computing resources. A fleet's operating system depends on the OS specified for the build that is deployed on this fleet.

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: describe_fleet_capacity(**kwargs)

    

    Retrieves the current status of fleet capacity for one or more fleets. This information includes the number of instances that have been requested for the fleet and the number currently active. You can request capacity for all fleets, or specify a list of one or more fleet IDs. When requesting multiple fleets, use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  FleetCapacity object is returned for each requested fleet ID. When specifying a list of fleet IDs, attribute objects are returned only for fleets that currently exist. 

     

    .. note::

       

      Some API actions may limit the number of fleet IDs allowed in one request. If a request exceeds this limit, the request fails and the error message includes the maximum allowed.

       

    

    **Request Syntax** 
    ::

      response = client.describe_fleet_capacity(
          FleetIds=[
              'string',
          ],
          Limit=123,
          NextToken='string'
      )
    :type FleetIds: list
    :param FleetIds: 

      Unique identifier for the fleet(s) you want to retrieve capacity information for. To request capacity information for all fleets, leave this parameter empty.

      

    
      - *(string) --* 

      
  
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages. This parameter is ignored when the request specifies one or a list of fleet IDs.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. This parameter is ignored when the request specifies one or a list of fleet IDs.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FleetCapacity': [
                {
                    'FleetId': 'string',
                    'InstanceType': 't2.micro'|'t2.small'|'t2.medium'|'t2.large'|'c3.large'|'c3.xlarge'|'c3.2xlarge'|'c3.4xlarge'|'c3.8xlarge'|'c4.large'|'c4.xlarge'|'c4.2xlarge'|'c4.4xlarge'|'c4.8xlarge'|'r3.large'|'r3.xlarge'|'r3.2xlarge'|'r3.4xlarge'|'r3.8xlarge'|'m3.medium'|'m3.large'|'m3.xlarge'|'m3.2xlarge'|'m4.large'|'m4.xlarge'|'m4.2xlarge'|'m4.4xlarge'|'m4.10xlarge',
                    'InstanceCounts': {
                        'DESIRED': 123,
                        'MINIMUM': 123,
                        'MAXIMUM': 123,
                        'PENDING': 123,
                        'ACTIVE': 123,
                        'IDLE': 123,
                        'TERMINATING': 123
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **FleetCapacity** *(list) --* 

          Collection of objects containing capacity information for each requested fleet ID. Leave this parameter empty to retrieve capacity information for all fleets.

          
          

          - *(dict) --* 

            Information about the fleet's capacity. Fleet capacity is measured in EC2 instances. By default, new fleets have a capacity of one instance, but can be updated as needed. The maximum number of instances for a fleet is determined by the fleet's instance type.

            
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **InstanceType** *(string) --* 

              Name of an EC2 instance type that is supported in Amazon GameLift. A fleet instance type determines the computing resources of each instance in the fleet, including CPU, memory, storage, and networking capacity. GameLift supports the following EC2 instance types. See `Amazon EC2 Instance Types`_ for detailed descriptions.

              
            

            - **InstanceCounts** *(dict) --* 

              Current status of fleet capacity.

              
              

              - **DESIRED** *(integer) --* 

                Ideal number of active instances in the fleet.

                
              

              - **MINIMUM** *(integer) --* 

                Minimum value allowed for the fleet's instance count.

                
              

              - **MAXIMUM** *(integer) --* 

                Maximum value allowed for the fleet's instance count.

                
              

              - **PENDING** *(integer) --* 

                Number of instances in the fleet that are starting but not yet active.

                
              

              - **ACTIVE** *(integer) --* 

                Actual number of active instances in the fleet.

                
              

              - **IDLE** *(integer) --* 

                Number of active instances in the fleet that are not currently hosting a game session.

                
              

              - **TERMINATING** *(integer) --* 

                Number of instances in the fleet that are no longer active but haven't yet been terminated. 

                
          
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: describe_fleet_events(**kwargs)

    

    Retrieves entries from the specified fleet's event log. You can specify a time range to limit the result set. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a collection of event log entries matching the request are returned.

    

    **Request Syntax** 
    ::

      response = client.describe_fleet_events(
          FleetId='string',
          StartTime=datetime(2015, 1, 1),
          EndTime=datetime(2015, 1, 1),
          Limit=123,
          NextToken='string'
      )
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier for the fleet to get event logs for. 

      

    
    :type StartTime: datetime
    :param StartTime: 

      Earliest date to retrieve event logs for. If no start time is specified, this call returns entries starting from when the fleet was created to the specified end time. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

      

    
    :type EndTime: datetime
    :param EndTime: 

      Most recent date to retrieve event logs for. If no end time is specified, this call returns entries from the specified start time up to the present. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

      

    
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Events': [
                {
                    'EventId': 'string',
                    'ResourceId': 'string',
                    'EventCode': 'GENERIC_EVENT'|'FLEET_CREATED'|'FLEET_DELETED'|'FLEET_SCALING_EVENT'|'FLEET_STATE_DOWNLOADING'|'FLEET_STATE_VALIDATING'|'FLEET_STATE_BUILDING'|'FLEET_STATE_ACTIVATING'|'FLEET_STATE_ACTIVE'|'FLEET_STATE_ERROR'|'FLEET_INITIALIZATION_FAILED'|'FLEET_BINARY_DOWNLOAD_FAILED'|'FLEET_VALIDATION_LAUNCH_PATH_NOT_FOUND'|'FLEET_VALIDATION_EXECUTABLE_RUNTIME_FAILURE'|'FLEET_VALIDATION_TIMED_OUT'|'FLEET_ACTIVATION_FAILED'|'FLEET_ACTIVATION_FAILED_NO_INSTANCES'|'FLEET_NEW_GAME_SESSION_PROTECTION_POLICY_UPDATED',
                    'Message': 'string',
                    'EventTime': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Events** *(list) --* 

          Collection of objects containing event log entries for the specified fleet.

          
          

          - *(dict) --* 

            Log entry describing an event involving an Amazon GameLift resource (such as a fleet).

            
            

            - **EventId** *(string) --* 

              Unique identifier for a fleet event.

              
            

            - **ResourceId** *(string) --* 

              Unique identifier for the resource, such as a fleet ID.

              
            

            - **EventCode** *(string) --* 

              Type of event being logged.

              
            

            - **Message** *(string) --* 

              Additional information related to the event.

              
            

            - **EventTime** *(datetime) --* 

              Time stamp indicating when this event occurred. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: describe_fleet_port_settings(**kwargs)

    

    Retrieves the inbound connection permissions for a fleet. Connection permissions include a range of IP addresses and port settings that incoming traffic can use to access server processes in the fleet. To get a fleet's inbound connection permissions, specify a fleet ID. If successful, a collection of  IpPermission objects is returned for the requested fleet ID. If the requested fleet has been deleted, the result set is empty.

    

    **Request Syntax** 
    ::

      response = client.describe_fleet_port_settings(
          FleetId='string'
      )
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier for the fleet you want to retrieve port settings for. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'InboundPermissions': [
                {
                    'FromPort': 123,
                    'ToPort': 123,
                    'IpRange': 'string',
                    'Protocol': 'TCP'|'UDP'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **InboundPermissions** *(list) --* 

          Object containing port settings for the requested fleet ID.

          
          

          - *(dict) --* 

            A range of IP addresses and port settings that allow inbound traffic to connect to server processes on GameLift. Each game session hosted on a fleet is assigned a unique combination of IP address and port number, which must fall into the fleet's allowed ranges. This combination is included in the  GameSession object. 

            
            

            - **FromPort** *(integer) --* 

              Starting value for a range of allowed port numbers. 

              
            

            - **ToPort** *(integer) --* 

              Ending value for a range of allowed port numbers. Port numbers are end-inclusive. This value must be higher than ``FromPort`` .

              
            

            - **IpRange** *(string) --* 

              Range of allowed IP addresses. This value must be expressed in `CIDR notation`_ . Example: "``000.000.000.000/[subnet mask]`` " or optionally the shortened version "``0.0.0.0/[subnet mask]`` ".

              
            

            - **Protocol** *(string) --* 

              Network communication protocol used by the fleet.

              
        
      
    

  .. py:method:: describe_fleet_utilization(**kwargs)

    

    Retrieves utilization statistics for one or more fleets. You can request utilization data for all fleets, or specify a list of one or more fleet IDs. When requesting multiple fleets, use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  FleetUtilization object is returned for each requested fleet ID. When specifying a list of fleet IDs, utilization objects are returned only for fleets that currently exist. 

     

    .. note::

       

      Some API actions may limit the number of fleet IDs allowed in one request. If a request exceeds this limit, the request fails and the error message includes the maximum allowed.

       

    

    **Request Syntax** 
    ::

      response = client.describe_fleet_utilization(
          FleetIds=[
              'string',
          ],
          Limit=123,
          NextToken='string'
      )
    :type FleetIds: list
    :param FleetIds: 

      Unique identifier for the fleet(s) you want to retrieve utilization data for. To request utilization data for all fleets, leave this parameter empty.

      

    
      - *(string) --* 

      
  
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages. This parameter is ignored when the request specifies one or a list of fleet IDs.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. This parameter is ignored when the request specifies one or a list of fleet IDs.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FleetUtilization': [
                {
                    'FleetId': 'string',
                    'ActiveServerProcessCount': 123,
                    'ActiveGameSessionCount': 123,
                    'CurrentPlayerSessionCount': 123,
                    'MaximumPlayerSessionCount': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **FleetUtilization** *(list) --* 

          Collection of objects containing utilization information for each requested fleet ID.

          
          

          - *(dict) --* 

            Current status of fleet utilization, including the number of game and player sessions being hosted.

            
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **ActiveServerProcessCount** *(integer) --* 

              Number of server processes in an ``ACTIVE`` status currently running across all instances in the fleet

              
            

            - **ActiveGameSessionCount** *(integer) --* 

              Number of active game sessions currently being hosted on all instances in the fleet.

              
            

            - **CurrentPlayerSessionCount** *(integer) --* 

              Number of active player sessions currently being hosted on all instances in the fleet.

              
            

            - **MaximumPlayerSessionCount** *(integer) --* 

              Maximum players allowed across all game sessions currently being hosted on all instances in the fleet.

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: describe_game_session_details(**kwargs)

    

    Retrieves properties, including the protection policy in force, for one or more game sessions. This action can be used in several ways: (1) provide a ``GameSessionId`` to request details for a specific game session; (2) provide either a ``FleetId`` or an ``AliasId`` to request properties for all game sessions running on a fleet. 

     

    To get game session record(s), specify just one of the following: game session ID, fleet ID, or alias ID. You can filter this request by game session status. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  GameSessionDetail object is returned for each session matching the request.

    

    **Request Syntax** 
    ::

      response = client.describe_game_session_details(
          FleetId='string',
          GameSessionId='string',
          AliasId='string',
          StatusFilter='string',
          Limit=123,
          NextToken='string'
      )
    :type FleetId: string
    :param FleetId: 

      Unique identifier for a fleet. Specify a fleet to retrieve information on all game sessions active on the fleet.

      

    
    :type GameSessionId: string
    :param GameSessionId: 

      Unique identifier for a game session. Specify the game session to retrieve information on.

      

    
    :type AliasId: string
    :param AliasId: 

      Unique identifier for a fleet alias. Specify an alias to retrieve information on all game sessions active on the fleet.

      

    
    :type StatusFilter: string
    :param StatusFilter: 

      Game session status to filter results on. Possible game session statuses include ACTIVE, ``TERMINATED`` , ``ACTIVATING`` and ``TERMINATING`` (the last two are transitory). 

      

    
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GameSessionDetails': [
                {
                    'GameSession': {
                        'GameSessionId': 'string',
                        'Name': 'string',
                        'FleetId': 'string',
                        'CreationTime': datetime(2015, 1, 1),
                        'TerminationTime': datetime(2015, 1, 1),
                        'CurrentPlayerSessionCount': 123,
                        'MaximumPlayerSessionCount': 123,
                        'Status': 'ACTIVE'|'ACTIVATING'|'TERMINATED'|'TERMINATING',
                        'GameProperties': [
                            {
                                'Key': 'string',
                                'Value': 'string'
                            },
                        ],
                        'IpAddress': 'string',
                        'Port': 123,
                        'PlayerSessionCreationPolicy': 'ACCEPT_ALL'|'DENY_ALL'
                    },
                    'ProtectionPolicy': 'NoProtection'|'FullProtection'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **GameSessionDetails** *(list) --* 

          Collection of objects containing game session properties and the protection policy currently in force for each session matching the request.

          
          

          - *(dict) --* 

            A game session's properties and the protection policy currently in force.

            
            

            - **GameSession** *(dict) --* 

              Properties describing a game session.

              
              

              - **GameSessionId** *(string) --* 

                Unique identifier for a game session.

                
              

              - **Name** *(string) --* 

                Descriptive label associated with a game session. Session names do not need to be unique.

                
              

              - **FleetId** *(string) --* 

                Unique identifier for a fleet.

                
              

              - **CreationTime** *(datetime) --* 

                Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

                
              

              - **TerminationTime** *(datetime) --* 

                Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

                
              

              - **CurrentPlayerSessionCount** *(integer) --* 

                Number of players currently in the game session.

                
              

              - **MaximumPlayerSessionCount** *(integer) --* 

                Maximum number of players allowed in the game session.

                
              

              - **Status** *(string) --* 

                Current status of the game session. A game session must be in an ``ACTIVE`` status to have player sessions.

                
              

              - **GameProperties** *(list) --* 

                Set of custom properties for the game session.

                
                

                - *(dict) --* 

                  Set of key-value pairs containing information a server process requires to set up a game session. This object allows you to pass in any set of data needed for your game. For more information, see the `Amazon GameLift Developer Guide`_ .

                  
                  

                  - **Key** *(string) --* 
                  

                  - **Value** *(string) --* 
              
            
              

              - **IpAddress** *(string) --* 

                IP address of the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

                
              

              - **Port** *(integer) --* 

                Port number for the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

                
              

              - **PlayerSessionCreationPolicy** *(string) --* 

                Indicates whether or not the game session is accepting new players.

                
          
            

            - **ProtectionPolicy** *(string) --* 

              Current status of protection for the game session.

               

              
              * **NoProtection** – The game session can be terminated during a scale-down event.
               
              * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event.
              

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: describe_game_sessions(**kwargs)

    

    Retrieves properties for one or more game sessions. This action can be used in several ways: (1) provide a ``GameSessionId`` to request properties for a specific game session; (2) provide a ``FleetId`` or an ``AliasId`` to request properties for all game sessions running on a fleet. 

     

    To get game session record(s), specify just one of the following: game session ID, fleet ID, or alias ID. You can filter this request by game session status. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  GameSession object is returned for each session matching the request.

    

    **Request Syntax** 
    ::

      response = client.describe_game_sessions(
          FleetId='string',
          GameSessionId='string',
          AliasId='string',
          StatusFilter='string',
          Limit=123,
          NextToken='string'
      )
    :type FleetId: string
    :param FleetId: 

      Unique identifier for a fleet. Specify a fleet to retrieve information on all game sessions active on the fleet.

      

    
    :type GameSessionId: string
    :param GameSessionId: 

      Unique identifier for a game session. Specify the game session to retrieve information on.

      

    
    :type AliasId: string
    :param AliasId: 

      Unique identifier for a fleet alias. Specify an alias to retrieve information on all game sessions active on the fleet.

      

    
    :type StatusFilter: string
    :param StatusFilter: 

      Game session status to filter results on. Possible game session statuses include ``ACTIVE`` , ``TERMINATED`` , ``ACTIVATING`` , and ``TERMINATING`` (the last two are transitory). 

      

    
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GameSessions': [
                {
                    'GameSessionId': 'string',
                    'Name': 'string',
                    'FleetId': 'string',
                    'CreationTime': datetime(2015, 1, 1),
                    'TerminationTime': datetime(2015, 1, 1),
                    'CurrentPlayerSessionCount': 123,
                    'MaximumPlayerSessionCount': 123,
                    'Status': 'ACTIVE'|'ACTIVATING'|'TERMINATED'|'TERMINATING',
                    'GameProperties': [
                        {
                            'Key': 'string',
                            'Value': 'string'
                        },
                    ],
                    'IpAddress': 'string',
                    'Port': 123,
                    'PlayerSessionCreationPolicy': 'ACCEPT_ALL'|'DENY_ALL'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **GameSessions** *(list) --* 

          Collection of objects containing game session properties for each session matching the request.

          
          

          - *(dict) --* 

            Properties describing a game session.

            
            

            - **GameSessionId** *(string) --* 

              Unique identifier for a game session.

              
            

            - **Name** *(string) --* 

              Descriptive label associated with a game session. Session names do not need to be unique.

              
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **CreationTime** *(datetime) --* 

              Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **TerminationTime** *(datetime) --* 

              Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **CurrentPlayerSessionCount** *(integer) --* 

              Number of players currently in the game session.

              
            

            - **MaximumPlayerSessionCount** *(integer) --* 

              Maximum number of players allowed in the game session.

              
            

            - **Status** *(string) --* 

              Current status of the game session. A game session must be in an ``ACTIVE`` status to have player sessions.

              
            

            - **GameProperties** *(list) --* 

              Set of custom properties for the game session.

              
              

              - *(dict) --* 

                Set of key-value pairs containing information a server process requires to set up a game session. This object allows you to pass in any set of data needed for your game. For more information, see the `Amazon GameLift Developer Guide`_ .

                
                

                - **Key** *(string) --* 
                

                - **Value** *(string) --* 
            
          
            

            - **IpAddress** *(string) --* 

              IP address of the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

              
            

            - **Port** *(integer) --* 

              Port number for the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

              
            

            - **PlayerSessionCreationPolicy** *(string) --* 

              Indicates whether or not the game session is accepting new players.

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: describe_player_sessions(**kwargs)

    

    Retrieves properties for one or more player sessions. This action can be used in several ways: (1) provide a ``PlayerSessionId`` parameter to request properties for a specific player session; (2) provide a ``GameSessionId`` parameter to request properties for all player sessions in the specified game session; (3) provide a ``PlayerId`` parameter to request properties for all player sessions of a specified player. 

     

    To get game session record(s), specify only one of the following: a player session ID, a game session ID, or a player ID. You can filter this request by player session status. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  PlayerSession object is returned for each session matching the request.

    

    **Request Syntax** 
    ::

      response = client.describe_player_sessions(
          GameSessionId='string',
          PlayerId='string',
          PlayerSessionId='string',
          PlayerSessionStatusFilter='string',
          Limit=123,
          NextToken='string'
      )
    :type GameSessionId: string
    :param GameSessionId: 

      Unique identifier for a game session.

      

    
    :type PlayerId: string
    :param PlayerId: 

      Unique identifier for a player.

      

    
    :type PlayerSessionId: string
    :param PlayerSessionId: 

      Unique identifier for a player session.

      

    
    :type PlayerSessionStatusFilter: string
    :param PlayerSessionStatusFilter: 

      Player session status to filter results on.

       

      Possible player session statuses include the following:

       

      
      * **RESERVED** – The player session request has been received, but the player has not yet connected to the server process and/or been validated. 
      
      * **ACTIVE** – The player has been validated by the server process and is currently connected.
      
      * **COMPLETED** – The player connection has been dropped.
      
      * **TIMEDOUT** – A player session request was received, but the player did not connect and/or was not validated within the time-out limit (60 seconds).
      

      

    
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages. If a player session ID is specified, this parameter is ignored.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. If a player session ID is specified, this parameter is ignored.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PlayerSessions': [
                {
                    'PlayerSessionId': 'string',
                    'PlayerId': 'string',
                    'GameSessionId': 'string',
                    'FleetId': 'string',
                    'CreationTime': datetime(2015, 1, 1),
                    'TerminationTime': datetime(2015, 1, 1),
                    'Status': 'RESERVED'|'ACTIVE'|'COMPLETED'|'TIMEDOUT',
                    'IpAddress': 'string',
                    'Port': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **PlayerSessions** *(list) --* 

          Collection of objects containing properties for each player session that matches the request.

          
          

          - *(dict) --* 

            Properties describing a player session.

            
            

            - **PlayerSessionId** *(string) --* 

              Unique identifier for a player session.

              
            

            - **PlayerId** *(string) --* 

              Unique identifier for a player.

              
            

            - **GameSessionId** *(string) --* 

              Unique identifier for a game session.

              
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **CreationTime** *(datetime) --* 

              Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **TerminationTime** *(datetime) --* 

              Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **Status** *(string) --* 

              Current status of the player session.

               

              Possible player session statuses include the following:

               

              
              * **RESERVED** – The player session request has been received, but the player has not yet connected to the server process and/or been validated. 
              
              * **ACTIVE** – The player has been validated by the server process and is currently connected.
              
              * **COMPLETED** – The player connection has been dropped.
              
              * **TIMEDOUT** – A player session request was received, but the player did not connect and/or was not validated within the time-out limit (60 seconds).
              

              
            

            - **IpAddress** *(string) --* 

              Game session IP address. All player sessions reference the game session location. 

              
            

            - **Port** *(integer) --* 

              Port number for the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: describe_runtime_configuration(**kwargs)

    

    Retrieves the current runtime configuration for the specified fleet. The runtime configuration tells GameLift how to launch server processes on instances in the fleet.

    

    **Request Syntax** 
    ::

      response = client.describe_runtime_configuration(
          FleetId='string'
      )
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier of the fleet to get the runtime configuration for.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RuntimeConfiguration': {
                'ServerProcesses': [
                    {
                        'LaunchPath': 'string',
                        'Parameters': 'string',
                        'ConcurrentExecutions': 123
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **RuntimeConfiguration** *(dict) --* 

          Instructions describing how server processes should be launched and maintained on each instance in the fleet.

          
          

          - **ServerProcesses** *(list) --* 

            Collection of server process configurations describing what server processes to run on each instance in a fleet 

            
            

            - *(dict) --* 

              A set of instructions for launching server processes on each instance in a fleet. Each instruction set identifies the location of the server executable, optional launch parameters, and the number of server processes with this configuration to maintain concurrently on the instance. Server process configurations make up a fleet's `` RuntimeConfiguration`` .

              
              

              - **LaunchPath** *(string) --* 

                Location in the game build of the server executable. All game builds are installed on instances at the root ``C:\game\...`` , so an executable file located at ``MyGame\latest\server.exe`` has a launch path of "``C:\game\MyGame\latest\server.exe`` ". 

                
              

              - **Parameters** *(string) --* 

                Optional list of parameters to pass to the server executable on launch.

                
              

              - **ConcurrentExecutions** *(integer) --* 

                Number of server processes using this configuration to run concurrently on an instance. 

                
          
        
      
    

  .. py:method:: describe_scaling_policies(**kwargs)

    

    Retrieves all scaling policies applied to a fleet. 

     

    To get a fleet's scaling policies, specify the fleet ID. You can filter this request by policy status, such as to retrieve only active scaling policies. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, set of  ScalingPolicy objects is returned for the fleet.

    

    **Request Syntax** 
    ::

      response = client.describe_scaling_policies(
          FleetId='string',
          StatusFilter='ACTIVE'|'UPDATE_REQUESTED'|'UPDATING'|'DELETE_REQUESTED'|'DELETING'|'DELETED'|'ERROR',
          Limit=123,
          NextToken='string'
      )
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier for a fleet. Specify the fleet to retrieve scaling policies for.

      

    
    :type StatusFilter: string
    :param StatusFilter: 

      Scaling policy status to filter results on. A scaling policy is only in force when in an ``ACTIVE`` status.

       

       
      * **ACTIVE** – The scaling policy is currently in force.
       
      * **UPDATEREQUESTED** – A request to update the scaling policy has been received.
       
      * **UPDATING** – A change is being made to the scaling policy.
       
      * **DELETEREQUESTED** – A request to delete the scaling policy has been received.
       
      * **DELETING** – The scaling policy is being deleted.
       
      * **DELETED** – The scaling policy has been deleted.
       
      * **ERROR** – An error occurred in creating the policy. It should be removed and recreated.
       

      

    
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ScalingPolicies': [
                {
                    'FleetId': 'string',
                    'Name': 'string',
                    'Status': 'ACTIVE'|'UPDATE_REQUESTED'|'UPDATING'|'DELETE_REQUESTED'|'DELETING'|'DELETED'|'ERROR',
                    'ScalingAdjustment': 123,
                    'ScalingAdjustmentType': 'ChangeInCapacity'|'ExactCapacity'|'PercentChangeInCapacity',
                    'ComparisonOperator': 'GreaterThanOrEqualToThreshold'|'GreaterThanThreshold'|'LessThanThreshold'|'LessThanOrEqualToThreshold',
                    'Threshold': 123.0,
                    'EvaluationPeriods': 123,
                    'MetricName': 'ActivatingGameSessions'|'ActiveGameSessions'|'ActiveInstances'|'AvailablePlayerSessions'|'CurrentPlayerSessions'|'IdleInstances'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **ScalingPolicies** *(list) --* 

          Collection of objects containing the scaling policies matching the request.

          
          

          - *(dict) --* 

            Rule that controls how a fleet is scaled. Scaling policies are uniquely identified by the combination of name and fleet ID.

            
            

            - **FleetId** *(string) --* 

              Unique identity for the fleet associated with this scaling policy.

              
            

            - **Name** *(string) --* 

              Descriptive label associated with a scaling policy. Policy names do not need to be unique.

              
            

            - **Status** *(string) --* 

              Current status of the scaling policy. The scaling policy is only in force when in an ``ACTIVE`` status.

               

               
              * **ACTIVE** – The scaling policy is currently in force.
               
              * **UPDATE_REQUESTED** – A request to update the scaling policy has been received.
               
              * **UPDATING** – A change is being made to the scaling policy.
               
              * **DELETE_REQUESTED** – A request to delete the scaling policy has been received.
               
              * **DELETING** – The scaling policy is being deleted.
               
              * **DELETED** – The scaling policy has been deleted.
               
              * **ERROR** – An error occurred in creating the policy. It should be removed and recreated.
               

              
            

            - **ScalingAdjustment** *(integer) --* 

              Amount of adjustment to make, based on the scaling adjustment type.

              
            

            - **ScalingAdjustmentType** *(string) --* 

              Type of adjustment to make to a fleet's instance count (see  FleetCapacity ):

               

               
              * **ChangeInCapacity** – add (or subtract) the scaling adjustment value from the current instance count. Positive values scale up while negative values scale down.
               
              * **ExactCapacity** – set the instance count to the scaling adjustment value.
               
              * **PercentChangeInCapacity** – increase or reduce the current instance count by the scaling adjustment, read as a percentage. Positive values scale up while negative values scale down.
               

              
            

            - **ComparisonOperator** *(string) --* 

              Comparison operator to use when measuring a metric against the threshold value. 

              
            

            - **Threshold** *(float) --* 

              Metric value used to trigger a scaling event.

              
            

            - **EvaluationPeriods** *(integer) --* 

              Length of time (in minutes) the metric must be at or beyond the threshold before a scaling event is triggered.

              
            

            - **MetricName** *(string) --* 

              Name of the GameLift-defined metric that is used to trigger an adjustment.

               

               
              * **ActivatingGameSessions** – number of game sessions in the process of being created (game session status = ``ACTIVATING`` ).
               
              * **ActiveGameSessions** – number of game sessions currently running (game session status = ``ACTIVE`` ).
               
              * **CurrentPlayerSessions** – number of active or reserved player sessions (player session status = ``ACTIVE`` or ``RESERVED`` ). 
               
              * **AvailablePlayerSessions** – number of player session slots currently available in active game sessions across the fleet, calculated by subtracting a game session's current player session count from its maximum player session count. This number does include game sessions that are not currently accepting players (game session ``PlayerSessionCreationPolicy`` = ``DENY_ALL`` ).
               
              * **ActiveInstances** – number of instances currently running a game session.
               
              * **IdleInstances** – number of instances not currently running a game session.
               

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

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


  .. py:method:: get_game_session_log_url(**kwargs)

    

    Retrieves the location of stored game session logs for a specified game session. When a game session is terminated, Amazon GameLift automatically stores the logs in Amazon S3. Use this URL to download the logs.

     

    .. note::

       

      See the `AWS Service Limits`_ page for maximum log file sizes. Log files that exceed this limit are not saved.

       

    

    **Request Syntax** 
    ::

      response = client.get_game_session_log_url(
          GameSessionId='string'
      )
    :type GameSessionId: string
    :param GameSessionId: **[REQUIRED]** 

      Unique identifier for a game session. Specify the game session you want to get logs for.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PreSignedUrl': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **PreSignedUrl** *(string) --* 

          Location of the requested game session logs, available for download.

          
    

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

        


  .. py:method:: list_aliases(**kwargs)

    

    Retrieves a collection of alias records for this AWS account. You can filter the result set by alias name and/or routing strategy type. Use the pagination parameters to retrieve results in sequential pages. 

     

    .. note::

       

      Aliases are not listed in any particular order.

       

    

    **Request Syntax** 
    ::

      response = client.list_aliases(
          RoutingStrategyType='SIMPLE'|'TERMINAL',
          Name='string',
          Limit=123,
          NextToken='string'
      )
    :type RoutingStrategyType: string
    :param RoutingStrategyType: 

      Type of routing to filter results on. Use this parameter to retrieve only aliases of a certain type. To retrieve all aliases, leave this parameter empty.

       

      Possible routing types include the following:

       

      
      * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets.
      
      * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded.
      

      

    
    :type Name: string
    :param Name: 

      Descriptive label associated with an alias. Alias names do not need to be unique.

      

    
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Aliases': [
                {
                    'AliasId': 'string',
                    'Name': 'string',
                    'Description': 'string',
                    'RoutingStrategy': {
                        'Type': 'SIMPLE'|'TERMINAL',
                        'FleetId': 'string',
                        'Message': 'string'
                    },
                    'CreationTime': datetime(2015, 1, 1),
                    'LastUpdatedTime': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Aliases** *(list) --* 

          Collection of alias records that match the list request. 

          
          

          - *(dict) --* 

            Properties describing a fleet alias.

            
            

            - **AliasId** *(string) --* 

              Unique identifier for a fleet alias.

              
            

            - **Name** *(string) --* 

              Descriptive label associated with an alias. Alias names do not need to be unique.

              
            

            - **Description** *(string) --* 

              Human-readable description of an alias.

              
            

            - **RoutingStrategy** *(dict) --* 

              Routing configuration for a fleet alias. 

              
              

              - **Type** *(string) --* 

                Type of routing strategy.

                 

                Possible routing types include the following:

                 

                
                * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets.
                
                * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded.
                

                
              

              - **FleetId** *(string) --* 

                Unique identifier for a fleet.

                
              

              - **Message** *(string) --* 

                Message text to be used with a terminal routing strategy.

                
          
            

            - **CreationTime** *(datetime) --* 

              Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **LastUpdatedTime** *(datetime) --* 

              Time stamp indicating when this data object was last modified. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: list_builds(**kwargs)

    

    Retrieves build records for all builds associated with the AWS account in use. You can limit results to builds that are in a specific status by using the ``Status`` parameter. Use the pagination parameters to retrieve results in a set of sequential pages. 

     

    .. note::

       

      Build records are not listed in any particular order.

       

    

    **Request Syntax** 
    ::

      response = client.list_builds(
          Status='INITIALIZED'|'READY'|'FAILED',
          Limit=123,
          NextToken='string'
      )
    :type Status: string
    :param Status: 

      Build status to filter results by. To retrieve all builds, leave this parameter empty.

       

      Possible build statuses include the following:

       

      
      * **INITIALIZED** – A new build has been defined, but no files have been uploaded. You cannot create fleets for builds that are in this status. When a build is successfully created, the build status is set to this value. 
      
      * **READY** – The game build has been successfully uploaded. You can now create new fleets for this build.
      
      * **FAILED** – The game build upload failed. You cannot create new fleets for this build. 
      

      

    
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Builds': [
                {
                    'BuildId': 'string',
                    'Name': 'string',
                    'Version': 'string',
                    'Status': 'INITIALIZED'|'READY'|'FAILED',
                    'SizeOnDisk': 123,
                    'OperatingSystem': 'WINDOWS_2012'|'AMAZON_LINUX',
                    'CreationTime': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Builds** *(list) --* 

          Collection of build records that match the request. 

          
          

          - *(dict) --* 

            Properties describing a game build.

            
            

            - **BuildId** *(string) --* 

              Unique identifier for a build.

              
            

            - **Name** *(string) --* 

              Descriptive label associated with a build. Build names do not need to be unique. It can be set using  CreateBuild or  UpdateBuild .

              
            

            - **Version** *(string) --* 

              Version associated with this build. Version strings do not need to be unique to a build. This value can be set using  CreateBuild or  UpdateBuild .

              
            

            - **Status** *(string) --* 

              Current status of the build.

               

              Possible build statuses include the following:

               

              
              * **INITIALIZED** – A new build has been defined, but no files have been uploaded. You cannot create fleets for builds that are in this status. When a build is successfully created, the build status is set to this value. 
              
              * **READY** – The game build has been successfully uploaded. You can now create new fleets for this build.
              
              * **FAILED** – The game build upload failed. You cannot create new fleets for this build. 
              

              
            

            - **SizeOnDisk** *(integer) --* 

              File size of the uploaded game build, expressed in bytes. When the build status is ``INITIALIZED`` , this value is 0.

              
            

            - **OperatingSystem** *(string) --* 

              Operating system that the game server binaries are built to run on. This value determines the type of fleet resources that you can use for this build.

              
            

            - **CreationTime** *(datetime) --* 

              Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: list_fleets(**kwargs)

    

    Retrieves a collection of fleet records for this AWS account. You can filter the result set by build ID. Use the pagination parameters to retrieve results in sequential pages. 

     

    .. note::

       

      Fleet records are not listed in any particular order.

       

    

    **Request Syntax** 
    ::

      response = client.list_fleets(
          BuildId='string',
          Limit=123,
          NextToken='string'
      )
    :type BuildId: string
    :param BuildId: 

      Unique identifier of the build to return fleets for. Use this parameter to return only fleets using the specified build. To retrieve all fleets, leave this parameter empty.

      

    
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FleetIds': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **FleetIds** *(list) --* 

          Set of fleet IDs matching the list request. You can retrieve additional information about all returned fleets by passing this result set to a call to  DescribeFleetAttributes ,  DescribeFleetCapacity , and  DescribeFleetUtilization .

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: put_scaling_policy(**kwargs)

    

    Creates or updates a scaling policy for a fleet. An active scaling policy prompts Amazon GameLift to track a certain metric for a fleet and automatically change the fleet's capacity in specific circumstances. Each scaling policy contains one rule statement. Fleets can have multiple scaling policies in force simultaneously.

     

    A scaling policy rule statement has the following structure:

     

    If ``[MetricName]`` is ``[ComparisonOperator]``  ``[Threshold]`` for ``[EvaluationPeriods]`` minutes, then ``[ScalingAdjustmentType]`` to/by ``[ScalingAdjustment]`` .

     

    For example, this policy: "If the number of idle instances exceeds 20 for more than 15 minutes, then reduce the fleet capacity by 10 instances" could be implemented as the following rule statement: 

     

    If [IdleInstances] is [GreaterThanOrEqualToThreshold] [20] for [15] minutes, then [ChangeInCapacity] by [-10]. 

     

    To create or update a scaling policy, specify a unique combination of name and fleet ID, and set the rule values. All parameters for this action are required. If successful, the policy name is returned. Scaling policies cannot be suspended or made inactive. To stop enforcing a scaling policy, call  DeleteScalingPolicy .

    

    **Request Syntax** 
    ::

      response = client.put_scaling_policy(
          Name='string',
          FleetId='string',
          ScalingAdjustment=123,
          ScalingAdjustmentType='ChangeInCapacity'|'ExactCapacity'|'PercentChangeInCapacity',
          Threshold=123.0,
          ComparisonOperator='GreaterThanOrEqualToThreshold'|'GreaterThanThreshold'|'LessThanThreshold'|'LessThanOrEqualToThreshold',
          EvaluationPeriods=123,
          MetricName='ActivatingGameSessions'|'ActiveGameSessions'|'ActiveInstances'|'AvailablePlayerSessions'|'CurrentPlayerSessions'|'IdleInstances'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      Descriptive label associated with a scaling policy. Policy names do not need to be unique. A fleet can have only one scaling policy with the same name.

      

    
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identity for the fleet to scale with this policy.

      

    
    :type ScalingAdjustment: integer
    :param ScalingAdjustment: **[REQUIRED]** 

      Amount of adjustment to make, based on the scaling adjustment type.

      

    
    :type ScalingAdjustmentType: string
    :param ScalingAdjustmentType: **[REQUIRED]** 

      Type of adjustment to make to a fleet's instance count (see  FleetCapacity ):

       

       
      * **ChangeInCapacity** – add (or subtract) the scaling adjustment value from the current instance count. Positive values scale up while negative values scale down.
       
      * **ExactCapacity** – set the instance count to the scaling adjustment value.
       
      * **PercentChangeInCapacity** – increase or reduce the current instance count by the scaling adjustment, read as a percentage. Positive values scale up while negative values scale down; for example, a value of "-10" scales the fleet down by 10%.
       

      

    
    :type Threshold: float
    :param Threshold: **[REQUIRED]** 

      Metric value used to trigger a scaling event.

      

    
    :type ComparisonOperator: string
    :param ComparisonOperator: **[REQUIRED]** 

      Comparison operator to use when measuring the metric against the threshold value. 

      

    
    :type EvaluationPeriods: integer
    :param EvaluationPeriods: **[REQUIRED]** 

      Length of time (in minutes) the metric must be at or beyond the threshold before a scaling event is triggered.

      

    
    :type MetricName: string
    :param MetricName: **[REQUIRED]** 

      Name of the Amazon GameLift-defined metric that is used to trigger an adjustment.

       

       
      * **ActivatingGameSessions** – number of game sessions in the process of being created (game session status = ``ACTIVATING`` ).
       
      * **ActiveGameSessions** – number of game sessions currently running (game session status = ``ACTIVE`` ).
       
      * **CurrentPlayerSessions** – number of active or reserved player sessions (player session status = ``ACTIVE`` or ``RESERVED`` ). 
       
      * **AvailablePlayerSessions** – number of player session slots currently available in active game sessions across the fleet, calculated by subtracting a game session's current player session count from its maximum player session count. This number includes game sessions that are not currently accepting players (game session ``PlayerSessionCreationPolicy`` = ``DENY_ALL`` ).
       
      * **ActiveInstances** – number of instances currently running a game session.
       
      * **IdleInstances** – number of instances not currently running a game session.
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Name': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Name** *(string) --* 

          Descriptive label associated with a scaling policy. Policy names do not need to be unique.

          
    

  .. py:method:: request_upload_credentials(**kwargs)

    

    Retrieves a fresh set of upload credentials and the assigned Amazon S3 storage location for a specific build. Valid credentials are required to upload your game build files to Amazon S3.

     

    .. warning::

       

      Call this action only if you need credentials for a build created with `` CreateBuild`` . This is a rare situation; in most cases, builds are created using the CLI command ``upload-build`` , which creates a build record and also uploads build files. 

       

     

    Upload credentials are returned when you create the build, but they have a limited lifespan. You can get fresh credentials and use them to re-upload game files until the status of that build changes to ``READY`` . Once this happens, you must create a brand new build.

    

    **Request Syntax** 
    ::

      response = client.request_upload_credentials(
          BuildId='string'
      )
    :type BuildId: string
    :param BuildId: **[REQUIRED]** 

      Unique identifier for the build you want to get credentials for. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UploadCredentials': {
                'AccessKeyId': 'string',
                'SecretAccessKey': 'string',
                'SessionToken': 'string'
            },
            'StorageLocation': {
                'Bucket': 'string',
                'Key': 'string',
                'RoleArn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **UploadCredentials** *(dict) --* 

          AWS credentials required when uploading a game build to the storage location. These credentials have a limited lifespan and are valid only for the build they were issued for.

          
          

          - **AccessKeyId** *(string) --* 

            Access key for an AWS account.

            
          

          - **SecretAccessKey** *(string) --* 

            Secret key for an AWS account.

            
          

          - **SessionToken** *(string) --* 

            Token specific to a build ID.

            
      
        

        - **StorageLocation** *(dict) --* 

          Amazon S3 path and key, identifying where the game build files are stored.

          
          

          - **Bucket** *(string) --* 

            Amazon S3 bucket identifier.

            
          

          - **Key** *(string) --* 

            Amazon S3 bucket key.

            
          

          - **RoleArn** *(string) --* 

            Amazon resource number for the cross-account access role that allows GameLift access to the S3 bucket.

            
      
    

  .. py:method:: resolve_alias(**kwargs)

    

    Retrieves the fleet ID that a specified alias is currently pointing to. 

    

    **Request Syntax** 
    ::

      response = client.resolve_alias(
          AliasId='string'
      )
    :type AliasId: string
    :param AliasId: **[REQUIRED]** 

      Unique identifier for the alias you want to resolve. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FleetId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **FleetId** *(string) --* 

          Fleet ID associated with the requested alias.

          
    

  .. py:method:: search_game_sessions(**kwargs)

    

    Retrieves a list of game sessions in a fleet that match a set of search criteria and sorts them in a specified order. Currently game session searches are limited to a single fleet. Search results include only game sessions that are in ACTIVE status.

     

    You can search or sort by the following game session attributes:

     

     
    * **gameSessionId** -- ID value assigned to a game session. This unique value is returned in a  GameSession object when a new game session is created. 
     
    * **gameSessionName** -- Name assigned to a game session. This value is set when requesting a new game session with  CreateGameSession or updating with  UpdateGameSession . Game session names do not need to be unique to a game session.
     
    * **creationTimeMillis** -- Value indicating when a game session was created. It is expressed in Unix time as milliseconds.
     
    * **playerSessionCount** -- Number of players currently connected to a game session. This value changes rapidly as players join the session or drop out.
     
    * **maximumSessions** -- Maximum number of player sessions allowed for a game session. This value is set when requesting a new game session with  CreateGameSession or updating with  UpdateGameSession .
     
    * **hasAvailablePlayerSessions** -- Boolean value indicating whether or not a game session has reached its maximum number of players. When searching with this attribute, the search value must be ``true`` or ``false`` . It is highly recommended that all search requests include this filter attribute to optimize search performance and return only sessions that players can join. 
     

     

    To search or sort, specify either a fleet ID or an alias ID, and provide a search filter expression, a sort expression, or both. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a collection of  GameSession objects matching the request is returned.

     

    .. note::

       

      Returned values for ``playerSessionCount`` and ``hasAvailablePlayerSessions`` change quickly as players join sessions and others drop out. Results should be considered a snapshot in time. Be sure to refresh search results often, and handle sessions that fill up before a player can join. 

       

    

    **Request Syntax** 
    ::

      response = client.search_game_sessions(
          FleetId='string',
          AliasId='string',
          FilterExpression='string',
          SortExpression='string',
          Limit=123,
          NextToken='string'
      )
    :type FleetId: string
    :param FleetId: 

      Unique identifier for a fleet. Each request must reference either a fleet ID or alias ID, but not both.

      

    
    :type AliasId: string
    :param AliasId: 

      Unique identifier for a fleet alias. Each request must reference either a fleet ID or alias ID, but not both.

      

    
    :type FilterExpression: string
    :param FilterExpression: 

      String containing the search criteria for the session search. If no filter expression is included, the request returns results for all game sessions in the fleet that are in ACTIVE status. 

       

      A filter expression can contain one or multiple conditions. Each condition consists of the following:

       

       
      * **Operand** -- Name of a game session attribute. Valid values are ``gameSessionName`` , ``gameSessionId`` , ``creationTimeMillis`` , ``playerSessionCount`` , ``maximumSessions`` , ``hasAvailablePlayerSessions`` .
       
      * **Comparator** -- Valid comparators are: ``=`` , ``lt;gt;`` , ``lt;`` , ``gt;`` , ``lt;=`` , ``gt;=`` . 
       
      * **Value** -- Value to be searched for. Values can be numbers, boolean values (true/false) or strings. String values are case sensitive, enclosed in single quotes. Special characters must be escaped. Boolean and string values can only be used with the comparators ``=`` and ``lt;gt;`` . For example, the following filter expression searches on ``gameSessionName`` : "``FilterExpression": "gameSessionName = 'Matt\\'s Awesome Game 1'"`` . 
       

       

      To chain multiple conditions in a single expression, use the logical keywords ``AND`` , ``OR`` , and ``NOT`` and parentheses as needed. For example: ``x AND y AND NOT z`` , ``NOT (x OR y)`` .

       

      Session search evaluates conditions from left to right using the following precedence rules: 

       

       
      * ``=`` , ``lt;gt;`` , ``lt;`` , ``gt;`` , ``lt;=`` , ``gt;=``  
       
      * Parentheses 
       
      * NOT
       
      * AND
       
      * OR
       

       

      For example, this filter expression retrieves game sessions hosting at least ten players that have an open player slot: ``"maximumSessionsgt;=10 AND hasAvailablePlayerSessions=true"`` . 

      

    
    :type SortExpression: string
    :param SortExpression: 

      Instructions on how to sort the search results. If no sort expression is included, the request returns results in random order. A sort expression consists of the following elements: 

       

       
      * **Operand** -- Name of a game session attribute. Valid values are ``gameSessionName`` , ``gameSessionId`` , ``creationTimeMillis`` , ``playerSessionCount`` , ``maximumSessions`` , ``hasAvailablePlayerSessions`` .
       
      * **Order** -- Valid sort orders are ``ASC`` (ascending) and ``DESC`` (descending).
       

       

      For example, this sort expression returns the oldest active sessions first: ``"SortExpression": "creationTimeMillis ASC"`` . Results with a null value for the sort operand are returned at the end of the list.

      

    
    :type Limit: integer
    :param Limit: 

      Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages. The maximum number of results returned is 20, even if this value is not set or is set higher than 20. 

      

    
    :type NextToken: string
    :param NextToken: 

      Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GameSessions': [
                {
                    'GameSessionId': 'string',
                    'Name': 'string',
                    'FleetId': 'string',
                    'CreationTime': datetime(2015, 1, 1),
                    'TerminationTime': datetime(2015, 1, 1),
                    'CurrentPlayerSessionCount': 123,
                    'MaximumPlayerSessionCount': 123,
                    'Status': 'ACTIVE'|'ACTIVATING'|'TERMINATED'|'TERMINATING',
                    'GameProperties': [
                        {
                            'Key': 'string',
                            'Value': 'string'
                        },
                    ],
                    'IpAddress': 'string',
                    'Port': 123,
                    'PlayerSessionCreationPolicy': 'ACCEPT_ALL'|'DENY_ALL'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **GameSessions** *(list) --* 

          Collection of objects containing game session properties for each session matching the request.

          
          

          - *(dict) --* 

            Properties describing a game session.

            
            

            - **GameSessionId** *(string) --* 

              Unique identifier for a game session.

              
            

            - **Name** *(string) --* 

              Descriptive label associated with a game session. Session names do not need to be unique.

              
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **CreationTime** *(datetime) --* 

              Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **TerminationTime** *(datetime) --* 

              Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

              
            

            - **CurrentPlayerSessionCount** *(integer) --* 

              Number of players currently in the game session.

              
            

            - **MaximumPlayerSessionCount** *(integer) --* 

              Maximum number of players allowed in the game session.

              
            

            - **Status** *(string) --* 

              Current status of the game session. A game session must be in an ``ACTIVE`` status to have player sessions.

              
            

            - **GameProperties** *(list) --* 

              Set of custom properties for the game session.

              
              

              - *(dict) --* 

                Set of key-value pairs containing information a server process requires to set up a game session. This object allows you to pass in any set of data needed for your game. For more information, see the `Amazon GameLift Developer Guide`_ .

                
                

                - **Key** *(string) --* 
                

                - **Value** *(string) --* 
            
          
            

            - **IpAddress** *(string) --* 

              IP address of the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

              
            

            - **Port** *(integer) --* 

              Port number for the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

              
            

            - **PlayerSessionCreationPolicy** *(string) --* 

              Indicates whether or not the game session is accepting new players.

              
        
      
        

        - **NextToken** *(string) --* 

          Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

           

          .. note::

             

            If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

             

          
    

  .. py:method:: update_alias(**kwargs)

    

    Updates properties for an alias. To update properties, specify the alias ID to be updated and provide the information to be changed. To reassign an alias to another fleet, provide an updated routing strategy. If successful, the updated alias record is returned.

    

    **Request Syntax** 
    ::

      response = client.update_alias(
          AliasId='string',
          Name='string',
          Description='string',
          RoutingStrategy={
              'Type': 'SIMPLE'|'TERMINAL',
              'FleetId': 'string',
              'Message': 'string'
          }
      )
    :type AliasId: string
    :param AliasId: **[REQUIRED]** 

      Unique identifier for a fleet alias. Specify the alias you want to update. 

      

    
    :type Name: string
    :param Name: 

      Descriptive label associated with an alias. Alias names do not need to be unique.

      

    
    :type Description: string
    :param Description: 

      Human-readable description of an alias.

      

    
    :type RoutingStrategy: dict
    :param RoutingStrategy: 

      Object specifying the fleet and routing type to use for the alias.

      

    
      - **Type** *(string) --* 

        Type of routing strategy.

         

        Possible routing types include the following:

         

        
        * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets.
        
        * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded.
        

        

      
      - **FleetId** *(string) --* 

        Unique identifier for a fleet.

        

      
      - **Message** *(string) --* 

        Message text to be used with a terminal routing strategy.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Alias': {
                'AliasId': 'string',
                'Name': 'string',
                'Description': 'string',
                'RoutingStrategy': {
                    'Type': 'SIMPLE'|'TERMINAL',
                    'FleetId': 'string',
                    'Message': 'string'
                },
                'CreationTime': datetime(2015, 1, 1),
                'LastUpdatedTime': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Alias** *(dict) --* 

          Object containing the updated alias configuration.

          
          

          - **AliasId** *(string) --* 

            Unique identifier for a fleet alias.

            
          

          - **Name** *(string) --* 

            Descriptive label associated with an alias. Alias names do not need to be unique.

            
          

          - **Description** *(string) --* 

            Human-readable description of an alias.

            
          

          - **RoutingStrategy** *(dict) --* 

            Routing configuration for a fleet alias. 

            
            

            - **Type** *(string) --* 

              Type of routing strategy.

               

              Possible routing types include the following:

               

              
              * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets.
              
              * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded.
              

              
            

            - **FleetId** *(string) --* 

              Unique identifier for a fleet.

              
            

            - **Message** *(string) --* 

              Message text to be used with a terminal routing strategy.

              
        
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **LastUpdatedTime** *(datetime) --* 

            Time stamp indicating when this data object was last modified. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
      
    

  .. py:method:: update_build(**kwargs)

    

    Updates metadata in a build record, including the build name and version. To update the metadata, specify the build ID to update and provide the new values. If successful, a build object containing the updated metadata is returned. 

    

    **Request Syntax** 
    ::

      response = client.update_build(
          BuildId='string',
          Name='string',
          Version='string'
      )
    :type BuildId: string
    :param BuildId: **[REQUIRED]** 

      Unique identifier of the build you want to update. 

      

    
    :type Name: string
    :param Name: 

      Descriptive label associated with a build. Build names do not need to be unique.

      

    
    :type Version: string
    :param Version: 

      Version associated with this build. Version strings do not need to be unique to a build.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Build': {
                'BuildId': 'string',
                'Name': 'string',
                'Version': 'string',
                'Status': 'INITIALIZED'|'READY'|'FAILED',
                'SizeOnDisk': 123,
                'OperatingSystem': 'WINDOWS_2012'|'AMAZON_LINUX',
                'CreationTime': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **Build** *(dict) --* 

          Object containing the updated build record.

          
          

          - **BuildId** *(string) --* 

            Unique identifier for a build.

            
          

          - **Name** *(string) --* 

            Descriptive label associated with a build. Build names do not need to be unique. It can be set using  CreateBuild or  UpdateBuild .

            
          

          - **Version** *(string) --* 

            Version associated with this build. Version strings do not need to be unique to a build. This value can be set using  CreateBuild or  UpdateBuild .

            
          

          - **Status** *(string) --* 

            Current status of the build.

             

            Possible build statuses include the following:

             

            
            * **INITIALIZED** – A new build has been defined, but no files have been uploaded. You cannot create fleets for builds that are in this status. When a build is successfully created, the build status is set to this value. 
            
            * **READY** – The game build has been successfully uploaded. You can now create new fleets for this build.
            
            * **FAILED** – The game build upload failed. You cannot create new fleets for this build. 
            

            
          

          - **SizeOnDisk** *(integer) --* 

            File size of the uploaded game build, expressed in bytes. When the build status is ``INITIALIZED`` , this value is 0.

            
          

          - **OperatingSystem** *(string) --* 

            Operating system that the game server binaries are built to run on. This value determines the type of fleet resources that you can use for this build.

            
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
      
    

  .. py:method:: update_fleet_attributes(**kwargs)

    

    Updates fleet properties, including name and description, for a fleet. To update metadata, specify the fleet ID and the property values you want to change. If successful, the fleet ID for the updated fleet is returned.

    

    **Request Syntax** 
    ::

      response = client.update_fleet_attributes(
          FleetId='string',
          Name='string',
          Description='string',
          NewGameSessionProtectionPolicy='NoProtection'|'FullProtection'
      )
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier for the fleet you want to update attribute metadata for. 

      

    
    :type Name: string
    :param Name: 

      Descriptive label associated with a fleet. Fleet names do not need to be unique.

      

    
    :type Description: string
    :param Description: 

      Human-readable description of a fleet.

      

    
    :type NewGameSessionProtectionPolicy: string
    :param NewGameSessionProtectionPolicy: 

      Game session protection policy to apply to all new instances created in this fleet. Instances that already exist are not affected. You can set protection for individual instances using  UpdateGameSession .

       

      
      * **NoProtection** – The game session can be terminated during a scale-down event.
       
      * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event.
      

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FleetId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **FleetId** *(string) --* 

          Unique identifier for the updated fleet.

          
    

  .. py:method:: update_fleet_capacity(**kwargs)

    

    Updates capacity settings for a fleet. Use this action to specify the number of EC2 instances (hosts) that you want this fleet to contain. Before calling this action, you may want to call  DescribeEC2InstanceLimits to get the maximum capacity based on the fleet's EC2 instance type.

     

    If you're using autoscaling (see  PutScalingPolicy ), you may want to specify a minimum and/or maximum capacity. If you don't provide these, autoscaling can set capacity anywhere between zero and the `service limits`_ .

     

    To update fleet capacity, specify the fleet ID and the number of instances you want the fleet to host. If successful, Amazon GameLift starts or terminates instances so that the fleet's active instance count matches the desired instance count. You can view a fleet's current capacity information by calling  DescribeFleetCapacity . If the desired instance count is higher than the instance type's limit, the "Limit Exceeded" exception occurs.

    

    **Request Syntax** 
    ::

      response = client.update_fleet_capacity(
          FleetId='string',
          DesiredInstances=123,
          MinSize=123,
          MaxSize=123
      )
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier for the fleet you want to update capacity for. 

      

    
    :type DesiredInstances: integer
    :param DesiredInstances: 

      Number of EC2 instances you want this fleet to host.

      

    
    :type MinSize: integer
    :param MinSize: 

      Minimum value allowed for the fleet's instance count. Default if not set is 0.

      

    
    :type MaxSize: integer
    :param MaxSize: 

      Maximum value allowed for the fleet's instance count. Default if not set is 1.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FleetId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **FleetId** *(string) --* 

          Unique identifier for the updated fleet.

          
    

  .. py:method:: update_fleet_port_settings(**kwargs)

    

    Updates port settings for a fleet. To update settings, specify the fleet ID to be updated and list the permissions you want to update. List the permissions you want to add in ``InboundPermissionAuthorizations`` , and permissions you want to remove in ``InboundPermissionRevocations`` . Permissions to be removed must match existing fleet permissions. If successful, the fleet ID for the updated fleet is returned.

    

    **Request Syntax** 
    ::

      response = client.update_fleet_port_settings(
          FleetId='string',
          InboundPermissionAuthorizations=[
              {
                  'FromPort': 123,
                  'ToPort': 123,
                  'IpRange': 'string',
                  'Protocol': 'TCP'|'UDP'
              },
          ],
          InboundPermissionRevocations=[
              {
                  'FromPort': 123,
                  'ToPort': 123,
                  'IpRange': 'string',
                  'Protocol': 'TCP'|'UDP'
              },
          ]
      )
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier for the fleet you want to update port settings for. 

      

    
    :type InboundPermissionAuthorizations: list
    :param InboundPermissionAuthorizations: 

      Collection of port settings to be added to the fleet record.

      

    
      - *(dict) --* 

        A range of IP addresses and port settings that allow inbound traffic to connect to server processes on GameLift. Each game session hosted on a fleet is assigned a unique combination of IP address and port number, which must fall into the fleet's allowed ranges. This combination is included in the  GameSession object. 

        

      
        - **FromPort** *(integer) --* **[REQUIRED]** 

          Starting value for a range of allowed port numbers. 

          

        
        - **ToPort** *(integer) --* **[REQUIRED]** 

          Ending value for a range of allowed port numbers. Port numbers are end-inclusive. This value must be higher than ``FromPort`` .

          

        
        - **IpRange** *(string) --* **[REQUIRED]** 

          Range of allowed IP addresses. This value must be expressed in `CIDR notation`_ . Example: "``000.000.000.000/[subnet mask]`` " or optionally the shortened version "``0.0.0.0/[subnet mask]`` ".

          

        
        - **Protocol** *(string) --* **[REQUIRED]** 

          Network communication protocol used by the fleet.

          

        
      
  
    :type InboundPermissionRevocations: list
    :param InboundPermissionRevocations: 

      Collection of port settings to be removed from the fleet record.

      

    
      - *(dict) --* 

        A range of IP addresses and port settings that allow inbound traffic to connect to server processes on GameLift. Each game session hosted on a fleet is assigned a unique combination of IP address and port number, which must fall into the fleet's allowed ranges. This combination is included in the  GameSession object. 

        

      
        - **FromPort** *(integer) --* **[REQUIRED]** 

          Starting value for a range of allowed port numbers. 

          

        
        - **ToPort** *(integer) --* **[REQUIRED]** 

          Ending value for a range of allowed port numbers. Port numbers are end-inclusive. This value must be higher than ``FromPort`` .

          

        
        - **IpRange** *(string) --* **[REQUIRED]** 

          Range of allowed IP addresses. This value must be expressed in `CIDR notation`_ . Example: "``000.000.000.000/[subnet mask]`` " or optionally the shortened version "``0.0.0.0/[subnet mask]`` ".

          

        
        - **Protocol** *(string) --* **[REQUIRED]** 

          Network communication protocol used by the fleet.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'FleetId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **FleetId** *(string) --* 

          Unique identifier for the updated fleet.

          
    

  .. py:method:: update_game_session(**kwargs)

    

    Updates game session properties. This includes the session name, maximum player count, protection policy, which controls whether or not an active game session can be terminated during a scale-down event, and the player session creation policy, which controls whether or not new players can join the session. To update a game session, specify the game session ID and the values you want to change. If successful, an updated  GameSession object is returned. 

    

    **Request Syntax** 
    ::

      response = client.update_game_session(
          GameSessionId='string',
          MaximumPlayerSessionCount=123,
          Name='string',
          PlayerSessionCreationPolicy='ACCEPT_ALL'|'DENY_ALL',
          ProtectionPolicy='NoProtection'|'FullProtection'
      )
    :type GameSessionId: string
    :param GameSessionId: **[REQUIRED]** 

      Unique identifier for a game session. Specify the game session you want to update. 

      

    
    :type MaximumPlayerSessionCount: integer
    :param MaximumPlayerSessionCount: 

      Maximum number of players that can be simultaneously connected to the game session.

      

    
    :type Name: string
    :param Name: 

      Descriptive label associated with a game session. Session names do not need to be unique.

      

    
    :type PlayerSessionCreationPolicy: string
    :param PlayerSessionCreationPolicy: 

      Policy determining whether or not the game session accepts new players.

      

    
    :type ProtectionPolicy: string
    :param ProtectionPolicy: 

      Game session protection policy to apply to this game session only.

       

      
      * **NoProtection** – The game session can be terminated during a scale-down event.
       
      * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event.
      

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GameSession': {
                'GameSessionId': 'string',
                'Name': 'string',
                'FleetId': 'string',
                'CreationTime': datetime(2015, 1, 1),
                'TerminationTime': datetime(2015, 1, 1),
                'CurrentPlayerSessionCount': 123,
                'MaximumPlayerSessionCount': 123,
                'Status': 'ACTIVE'|'ACTIVATING'|'TERMINATED'|'TERMINATING',
                'GameProperties': [
                    {
                        'Key': 'string',
                        'Value': 'string'
                    },
                ],
                'IpAddress': 'string',
                'Port': 123,
                'PlayerSessionCreationPolicy': 'ACCEPT_ALL'|'DENY_ALL'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **GameSession** *(dict) --* 

          Object containing the updated game session metadata.

          
          

          - **GameSessionId** *(string) --* 

            Unique identifier for a game session.

            
          

          - **Name** *(string) --* 

            Descriptive label associated with a game session. Session names do not need to be unique.

            
          

          - **FleetId** *(string) --* 

            Unique identifier for a fleet.

            
          

          - **CreationTime** *(datetime) --* 

            Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **TerminationTime** *(datetime) --* 

            Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057".

            
          

          - **CurrentPlayerSessionCount** *(integer) --* 

            Number of players currently in the game session.

            
          

          - **MaximumPlayerSessionCount** *(integer) --* 

            Maximum number of players allowed in the game session.

            
          

          - **Status** *(string) --* 

            Current status of the game session. A game session must be in an ``ACTIVE`` status to have player sessions.

            
          

          - **GameProperties** *(list) --* 

            Set of custom properties for the game session.

            
            

            - *(dict) --* 

              Set of key-value pairs containing information a server process requires to set up a game session. This object allows you to pass in any set of data needed for your game. For more information, see the `Amazon GameLift Developer Guide`_ .

              
              

              - **Key** *(string) --* 
              

              - **Value** *(string) --* 
          
        
          

          - **IpAddress** *(string) --* 

            IP address of the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

            
          

          - **Port** *(integer) --* 

            Port number for the game session. To connect to a GameLift server process, an app needs both the IP address and port number.

            
          

          - **PlayerSessionCreationPolicy** *(string) --* 

            Indicates whether or not the game session is accepting new players.

            
      
    

  .. py:method:: update_runtime_configuration(**kwargs)

    

    Updates the current runtime configuration for the specified fleet, which tells GameLift how to launch server processes on instances in the fleet. You can update a fleet's runtime configuration at any time after the fleet is created; it does not need to be in an ``ACTIVE`` status.

     

    To update runtime configuration, specify the fleet ID and provide a ``RuntimeConfiguration`` object with the updated collection of server process configurations.

     

    Each instance in a GameLift fleet checks regularly for an updated runtime configuration and changes how it launches server processes to comply with the latest version. Existing server processes are not affected by the update; they continue to run until they end, while GameLift simply adds new server processes to fit the current runtime configuration. As a result, the runtime configuration changes are applied gradually as existing processes shut down and new processes are launched in GameLift's normal process recycling activity.

    

    **Request Syntax** 
    ::

      response = client.update_runtime_configuration(
          FleetId='string',
          RuntimeConfiguration={
              'ServerProcesses': [
                  {
                      'LaunchPath': 'string',
                      'Parameters': 'string',
                      'ConcurrentExecutions': 123
                  },
              ]
          }
      )
    :type FleetId: string
    :param FleetId: **[REQUIRED]** 

      Unique identifier of the fleet to update runtime configuration for.

      

    
    :type RuntimeConfiguration: dict
    :param RuntimeConfiguration: **[REQUIRED]** 

      Instructions for launching server processes on each instance in the fleet. The runtime configuration for a fleet has a collection of server process configurations, one for each type of server process to run on an instance. A server process configuration specifies the location of the server executable, launch parameters, and the number of concurrent processes with that configuration to maintain on each instance.

      

    
      - **ServerProcesses** *(list) --* 

        Collection of server process configurations describing what server processes to run on each instance in a fleet 

        

      
        - *(dict) --* 

          A set of instructions for launching server processes on each instance in a fleet. Each instruction set identifies the location of the server executable, optional launch parameters, and the number of server processes with this configuration to maintain concurrently on the instance. Server process configurations make up a fleet's `` RuntimeConfiguration`` .

          

        
          - **LaunchPath** *(string) --* **[REQUIRED]** 

            Location in the game build of the server executable. All game builds are installed on instances at the root ``C:\game\...`` , so an executable file located at ``MyGame\latest\server.exe`` has a launch path of "``C:\game\MyGame\latest\server.exe`` ". 

            

          
          - **Parameters** *(string) --* 

            Optional list of parameters to pass to the server executable on launch.

            

          
          - **ConcurrentExecutions** *(integer) --* **[REQUIRED]** 

            Number of server processes using this configuration to run concurrently on an instance. 

            

          
        
    
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RuntimeConfiguration': {
                'ServerProcesses': [
                    {
                        'LaunchPath': 'string',
                        'Parameters': 'string',
                        'ConcurrentExecutions': 123
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the returned data in response to a request action.

        
        

        - **RuntimeConfiguration** *(dict) --* 

          The runtime configuration currently in force. If the update was successful, this object matches the one in the request.

          
          

          - **ServerProcesses** *(list) --* 

            Collection of server process configurations describing what server processes to run on each instance in a fleet 

            
            

            - *(dict) --* 

              A set of instructions for launching server processes on each instance in a fleet. Each instruction set identifies the location of the server executable, optional launch parameters, and the number of server processes with this configuration to maintain concurrently on the instance. Server process configurations make up a fleet's `` RuntimeConfiguration`` .

              
              

              - **LaunchPath** *(string) --* 

                Location in the game build of the server executable. All game builds are installed on instances at the root ``C:\game\...`` , so an executable file located at ``MyGame\latest\server.exe`` has a launch path of "``C:\game\MyGame\latest\server.exe`` ". 

                
              

              - **Parameters** *(string) --* 

                Optional list of parameters to pass to the server executable on launch.

                
              

              - **ConcurrentExecutions** *(integer) --* 

                Number of server processes using this configuration to run concurrently on an instance. 

                
          
        
      
    