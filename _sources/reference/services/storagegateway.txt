

.. _EC2 API reference: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_Operations.html
.. _Storage Gateway Concepts: http://docs.aws.amazon.com/storagegateway/latest/userguide/StorageGatewayConcepts.html
.. _AWS Storage Gateway Detail Page: http://aws.amazon.com/storagegateway
.. _ListLocalDisks: http://docs.aws.amazon.com/storagegateway/latest/userguide/API_ListLocalDisks.html
.. _Welcome: http://docs.aws.amazon.com/storagegateway/latest/APIReference/Welcome.html
.. _Working With Snapshots in the AWS Storage Gateway Console: http://docs.aws.amazon.com/storagegateway/latest/userguide/WorkingWithSnapshots.html
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html#sg_region
.. _Activate the AWS Storage Gateway: http://docs.aws.amazon.com/storagegateway/latest/userguide/GettingStartedActivateGateway-common.html
.. _Customizing Your Linux iSCSI Settings: http://docs.aws.amazon.com/storagegateway/latest/userguide/ConfiguringiSCSIClientInitiatorRedHatClient.html#CustomizeLinuxiSCSISettings
.. _Customizing Your Windows iSCSI Settings: http://docs.aws.amazon.com/storagegateway/latest/userguide/ConfiguringiSCSIClientInitiatorWindowsClient.html#CustomizeWindowsiSCSISettings
.. _Working with Snapshots: http://docs.aws.amazon.com/storagegateway/latest/userguide/WorkingWithSnapshots.html
.. _DescribeSnapshots: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-DescribeSnapshots.html


**************
StorageGateway
**************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: StorageGateway.Client

  A low-level client representing AWS Storage Gateway::

    
    import boto3
    
    client = boto3.client('storagegateway')

  
  These are the available methods:
  
  *   :py:meth:`activate_gateway`

  
  *   :py:meth:`add_cache`

  
  *   :py:meth:`add_tags_to_resource`

  
  *   :py:meth:`add_upload_buffer`

  
  *   :py:meth:`add_working_storage`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`cancel_archival`

  
  *   :py:meth:`cancel_retrieval`

  
  *   :py:meth:`create_cached_iscsi_volume`

  
  *   :py:meth:`create_snapshot`

  
  *   :py:meth:`create_snapshot_from_volume_recovery_point`

  
  *   :py:meth:`create_stored_iscsi_volume`

  
  *   :py:meth:`create_tape_with_barcode`

  
  *   :py:meth:`create_tapes`

  
  *   :py:meth:`delete_bandwidth_rate_limit`

  
  *   :py:meth:`delete_chap_credentials`

  
  *   :py:meth:`delete_gateway`

  
  *   :py:meth:`delete_snapshot_schedule`

  
  *   :py:meth:`delete_tape`

  
  *   :py:meth:`delete_tape_archive`

  
  *   :py:meth:`delete_volume`

  
  *   :py:meth:`describe_bandwidth_rate_limit`

  
  *   :py:meth:`describe_cache`

  
  *   :py:meth:`describe_cached_iscsi_volumes`

  
  *   :py:meth:`describe_chap_credentials`

  
  *   :py:meth:`describe_gateway_information`

  
  *   :py:meth:`describe_maintenance_start_time`

  
  *   :py:meth:`describe_snapshot_schedule`

  
  *   :py:meth:`describe_stored_iscsi_volumes`

  
  *   :py:meth:`describe_tape_archives`

  
  *   :py:meth:`describe_tape_recovery_points`

  
  *   :py:meth:`describe_tapes`

  
  *   :py:meth:`describe_upload_buffer`

  
  *   :py:meth:`describe_vtl_devices`

  
  *   :py:meth:`describe_working_storage`

  
  *   :py:meth:`disable_gateway`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_gateways`

  
  *   :py:meth:`list_local_disks`

  
  *   :py:meth:`list_tags_for_resource`

  
  *   :py:meth:`list_tapes`

  
  *   :py:meth:`list_volume_initiators`

  
  *   :py:meth:`list_volume_recovery_points`

  
  *   :py:meth:`list_volumes`

  
  *   :py:meth:`remove_tags_from_resource`

  
  *   :py:meth:`reset_cache`

  
  *   :py:meth:`retrieve_tape_archive`

  
  *   :py:meth:`retrieve_tape_recovery_point`

  
  *   :py:meth:`set_local_console_password`

  
  *   :py:meth:`shutdown_gateway`

  
  *   :py:meth:`start_gateway`

  
  *   :py:meth:`update_bandwidth_rate_limit`

  
  *   :py:meth:`update_chap_credentials`

  
  *   :py:meth:`update_gateway_information`

  
  *   :py:meth:`update_gateway_software_now`

  
  *   :py:meth:`update_maintenance_start_time`

  
  *   :py:meth:`update_snapshot_schedule`

  
  *   :py:meth:`update_vtl_device_type`

  

  .. py:method:: activate_gateway(**kwargs)

    

    Activates the gateway you previously deployed on your host. For more information, see `Activate the AWS Storage Gateway`_ . In the activation process, you specify information such as the you want to use for storing snapshots, the time zone for scheduled snapshots the gateway snapshot schedule window, an activation key, and a name for your gateway. The activation process also associates your gateway with your account; for more information, see  UpdateGatewayInformation .

     

    .. note::

      

      You must turn on the gateway VM before you can activate your gateway.

       

    

    **Request Syntax** 
    ::

      response = client.activate_gateway(
          ActivationKey='string',
          GatewayName='string',
          GatewayTimezone='string',
          GatewayRegion='string',
          GatewayType='string',
          TapeDriveType='string',
          MediumChangerType='string'
      )
    :type ActivationKey: string
    :param ActivationKey: **[REQUIRED]** 

      Your gateway activation key. You can obtain the activation key by sending an HTTP GET request with redirects enabled to the gateway IP address (port 80). The redirect URL returned in the response provides you the activation key for your gateway in the query string parameter ``activationKey`` . It may also include other activation-related parameters, however, these are merely defaults -- the arguments you pass to the ``ActivateGateway`` API call determine the actual configuration of your gateway.

      

    
    :type GatewayName: string
    :param GatewayName: **[REQUIRED]** 

      The name you configured for your gateway.

      

    
    :type GatewayTimezone: string
    :param GatewayTimezone: **[REQUIRED]** 

      A value that indicates the time zone you want to set for the gateway. The time zone is used, for example, for scheduling snapshots and your gateway's maintenance schedule.

      

    
    :type GatewayRegion: string
    :param GatewayRegion: **[REQUIRED]** 

      A value that indicates the region where you want to store the snapshot backups. The gateway region specified must be the same region as the region in your ``Host`` header in the request. For more information about available regions and endpoints for AWS Storage Gateway, see `Regions and Endpoints`_ in the *Amazon Web Services Glossary* .

       

      Valid Values: "us-east-1", "us-west-1", "us-west-2", "eu-west-1", "eu-central-1", "ap-northeast-1", "ap-northeast-2", "ap-southeast-1", "ap-southeast-2", "sa-east-1"

      

    
    :type GatewayType: string
    :param GatewayType: 

      A value that defines the type of gateway to activate. The type specified is critical to all later functions of the gateway and cannot be changed after activation. The default value is ``STORED`` . 

      

    
    :type TapeDriveType: string
    :param TapeDriveType: 

      The value that indicates the type of tape drive to use for gateway-VTL. This field is optional.

       

      Valid Values: "IBM-ULT3580-TD5" 

      

    
    :type MediumChangerType: string
    :param MediumChangerType: 

      The value that indicates the type of medium changer to use for gateway-VTL. This field is optional.

       

      Valid Values: "STK-L700", "AWS-Gateway-VTL"

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        AWS Storage Gateway returns the Amazon Resource Name (ARN) of the activated gateway. It is a string made of information such as your account, gateway name, and region. This ARN is used to reference the gateway in other API operations as well as resource-based authorization.

         

        .. note::

          

          For gateways activated prior to September 02, 2015 the gateway ARN contains the gateway name rather than the gateway id. Changing the name of the gateway has no effect on the gateway ARN.

           

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: add_cache(**kwargs)

    

    Configures one or more gateway local disks as cache for a cached-volume gateway. This operation is supported only for the gateway-cached volume architecture (see `Storage Gateway Concepts`_ ).

     

    In the request, you specify the gateway Amazon Resource Name (ARN) to which you want to add cache, and one or more disk IDs that you want to configure as cache.

    

    **Request Syntax** 
    ::

      response = client.add_cache(
          GatewayARN='string',
          DiskIds=[
              'string',
          ]
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type DiskIds: list
    :param DiskIds: **[REQUIRED]** 

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: add_tags_to_resource(**kwargs)

    

    Adds one or more tags to the specified resource. You use tags to add metadata to resources, which you can use to categorize these resources. For example, you can categorize resources by purpose, owner, environment, or team. Each tag consists of a key and a value, which you define. You can add tags to the following AWS Storage Gateway resources:

     

     
    * Storage gateways of all types 
     

     

     
    * Storage Volumes 
     

     

     
    * Virtual Tapes 
     

     

    You can create a maximum of 10 tags for each resource. Virtual tapes and storage volumes that are recovered to a new gateway maintain their tags.

    

    **Request Syntax** 
    ::

      response = client.add_tags_to_resource(
          ResourceARN='string',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type ResourceARN: string
    :param ResourceARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the resource you want to add tags to.

      

    
    :type Tags: list
    :param Tags: **[REQUIRED]** 

      The key-value pair that represents the tag you want to add to the resource. The value can be an empty string.

       

      .. note::

         

        Valid characters for key and value are letters, spaces, and numbers representable in UTF-8 format, and the following special characters: + - = . _ : / @.

         

      

    
      - *(dict) --* 

      
        - **Key** *(string) --* **[REQUIRED]** 

        
        - **Value** *(string) --* **[REQUIRED]** 

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ResourceARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        AddTagsToResourceOutput

        
        

        - **ResourceARN** *(string) --* 

          The Amazon Resource Name (ARN) of the resource you want to add tags to.

          
    

  .. py:method:: add_upload_buffer(**kwargs)

    

    Configures one or more gateway local disks as upload buffer for a specified gateway. This operation is supported for both the gateway-stored and gateway-cached volume architectures.

     

    In the request, you specify the gateway Amazon Resource Name (ARN) to which you want to add upload buffer, and one or more disk IDs that you want to configure as upload buffer.

    

    **Request Syntax** 
    ::

      response = client.add_upload_buffer(
          GatewayARN='string',
          DiskIds=[
              'string',
          ]
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type DiskIds: list
    :param DiskIds: **[REQUIRED]** 

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: add_working_storage(**kwargs)

    

    Configures one or more gateway local disks as working storage for a gateway. This operation is supported only for the gateway-stored volume architecture. This operation is deprecated in cached-volumes API version 20120630. Use  AddUploadBuffer instead.

     

    .. note::

       

      Working storage is also referred to as upload buffer. You can also use the  AddUploadBuffer operation to add upload buffer to a stored-volume gateway.

       

     

    In the request, you specify the gateway Amazon Resource Name (ARN) to which you want to add working storage, and one or more disk IDs that you want to configure as working storage.

    

    **Request Syntax** 
    ::

      response = client.add_working_storage(
          GatewayARN='string',
          DiskIds=[
              'string',
          ]
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type DiskIds: list
    :param DiskIds: **[REQUIRED]** 

      An array of strings that identify disks that are to be configured as working storage. Each string have a minimum length of 1 and maximum length of 300. You can get the disk IDs from the  ListLocalDisks API.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the of the gateway for which working storage was configured.

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

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


  .. py:method:: cancel_archival(**kwargs)

    

    Cancels archiving of a virtual tape to the virtual tape shelf (VTS) after the archiving process is initiated.

    

    **Request Syntax** 
    ::

      response = client.cancel_archival(
          GatewayARN='string',
          TapeARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type TapeARN: string
    :param TapeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the virtual tape you want to cancel archiving for.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        CancelArchivalOutput

        
        

        - **TapeARN** *(string) --* 

          The Amazon Resource Name (ARN) of the virtual tape for which archiving was canceled.

          
    

  .. py:method:: cancel_retrieval(**kwargs)

    

    Cancels retrieval of a virtual tape from the virtual tape shelf (VTS) to a gateway after the retrieval process is initiated. The virtual tape is returned to the VTS.

    

    **Request Syntax** 
    ::

      response = client.cancel_retrieval(
          GatewayARN='string',
          TapeARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type TapeARN: string
    :param TapeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the virtual tape you want to cancel retrieval for.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        CancelRetrievalOutput

        
        

        - **TapeARN** *(string) --* 

          The Amazon Resource Name (ARN) of the virtual tape for which retrieval was canceled.

          
    

  .. py:method:: create_cached_iscsi_volume(**kwargs)

    

    Creates a cached volume on a specified cached gateway. This operation is supported only for the gateway-cached volume architecture.

     

    .. note::

      

      Cache storage must be allocated to the gateway before you can create a cached volume. Use the  AddCache operation to add cache storage to a gateway. 

       

     

    In the request, you must specify the gateway, size of the volume in bytes, the iSCSI target name, an IP address on which to expose the target, and a unique client token. In response, AWS Storage Gateway creates the volume and returns information about it such as the volume Amazon Resource Name (ARN), its size, and the iSCSI target ARN that initiators can use to connect to the volume target.

    

    **Request Syntax** 
    ::

      response = client.create_cached_iscsi_volume(
          GatewayARN='string',
          VolumeSizeInBytes=123,
          SnapshotId='string',
          TargetName='string',
          NetworkInterfaceId='string',
          ClientToken='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type VolumeSizeInBytes: integer
    :param VolumeSizeInBytes: **[REQUIRED]** 

    
    :type SnapshotId: string
    :param SnapshotId: 

    
    :type TargetName: string
    :param TargetName: **[REQUIRED]** 

    
    :type NetworkInterfaceId: string
    :param NetworkInterfaceId: **[REQUIRED]** 

    
    :type ClientToken: string
    :param ClientToken: **[REQUIRED]** 

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VolumeARN': 'string',
            'TargetARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **VolumeARN** *(string) --* 
        

        - **TargetARN** *(string) --* 
    

  .. py:method:: create_snapshot(**kwargs)

    

    Initiates a snapshot of a volume.

     

    AWS Storage Gateway provides the ability to back up point-in-time snapshots of your data to Amazon Simple Storage (S3) for durable off-site recovery, as well as import the data to an Amazon Elastic Block Store (EBS) volume in Amazon Elastic Compute Cloud (EC2). You can take snapshots of your gateway volume on a scheduled or ad-hoc basis. This API enables you to take ad-hoc snapshot. For more information, see `Working With Snapshots in the AWS Storage Gateway Console`_ .

     

    In the CreateSnapshot request you identify the volume by providing its Amazon Resource Name (ARN). You must also provide description for the snapshot. When AWS Storage Gateway takes the snapshot of specified volume, the snapshot and description appears in the AWS Storage Gateway Console. In response, AWS Storage Gateway returns you a snapshot ID. You can use this snapshot ID to check the snapshot progress or later use it when you want to create a volume from a snapshot.

     

    .. note::

      

      To list or delete a snapshot, you must use the Amazon EC2 API. For more information, see DescribeSnapshots or DeleteSnapshot in the `EC2 API reference`_ .

       

     

    .. warning::

       

      Volume and snapshot IDs are changing to a longer length ID format. For more information, see the important note on the `Welcome`_ page.

       

    

    **Request Syntax** 
    ::

      response = client.create_snapshot(
          VolumeARN='string',
          SnapshotDescription='string'
      )
    :type VolumeARN: string
    :param VolumeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the volume. Use the  ListVolumes operation to return a list of gateway volumes.

      

    
    :type SnapshotDescription: string
    :param SnapshotDescription: **[REQUIRED]** 

      Textual description of the snapshot that appears in the Amazon EC2 console, Elastic Block Store snapshots panel in the **Description** field, and in the AWS Storage Gateway snapshot **Details** pane, **Description** field

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VolumeARN': 'string',
            'SnapshotId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the following fields:

        
        

        - **VolumeARN** *(string) --* 

          The Amazon Resource Name (ARN) of the volume of which the snapshot was taken.

          
        

        - **SnapshotId** *(string) --* 

          The snapshot ID that is used to refer to the snapshot in future operations such as describing snapshots (Amazon Elastic Compute Cloud API ``DescribeSnapshots`` ) or creating a volume from a snapshot ( CreateStorediSCSIVolume ).

          
    

  .. py:method:: create_snapshot_from_volume_recovery_point(**kwargs)

    

    Initiates a snapshot of a gateway from a volume recovery point. This operation is supported only for the gateway-cached volume architecture.

     

    A volume recovery point is a point in time at which all data of the volume is consistent and from which you can create a snapshot. To get a list of volume recovery point for gateway-cached volumes, use  ListVolumeRecoveryPoints .

     

    In the ``CreateSnapshotFromVolumeRecoveryPoint`` request, you identify the volume by providing its Amazon Resource Name (ARN). You must also provide a description for the snapshot. When AWS Storage Gateway takes a snapshot of the specified volume, the snapshot and its description appear in the AWS Storage Gateway console. In response, AWS Storage Gateway returns you a snapshot ID. You can use this snapshot ID to check the snapshot progress or later use it when you want to create a volume from a snapshot.

     

    .. note::

       

      To list or delete a snapshot, you must use the Amazon EC2 API. For more information, in *Amazon Elastic Compute Cloud API Reference* .

       

    

    **Request Syntax** 
    ::

      response = client.create_snapshot_from_volume_recovery_point(
          VolumeARN='string',
          SnapshotDescription='string'
      )
    :type VolumeARN: string
    :param VolumeARN: **[REQUIRED]** 

    
    :type SnapshotDescription: string
    :param SnapshotDescription: **[REQUIRED]** 

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SnapshotId': 'string',
            'VolumeARN': 'string',
            'VolumeRecoveryPointTime': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **SnapshotId** *(string) --* 
        

        - **VolumeARN** *(string) --* 
        

        - **VolumeRecoveryPointTime** *(string) --* 
    

  .. py:method:: create_stored_iscsi_volume(**kwargs)

    

    Creates a volume on a specified gateway. This operation is supported only for the gateway-stored volume architecture.

     

    The size of the volume to create is inferred from the disk size. You can choose to preserve existing data on the disk, create volume from an existing snapshot, or create an empty volume. If you choose to create an empty gateway volume, then any existing data on the disk is erased.

     

    In the request you must specify the gateway and the disk information on which you are creating the volume. In response, AWS Storage Gateway creates the volume and returns volume information such as the volume Amazon Resource Name (ARN), its size, and the iSCSI target ARN that initiators can use to connect to the volume target.

    

    **Request Syntax** 
    ::

      response = client.create_stored_iscsi_volume(
          GatewayARN='string',
          DiskId='string',
          SnapshotId='string',
          PreserveExistingData=True|False,
          TargetName='string',
          NetworkInterfaceId='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type DiskId: string
    :param DiskId: **[REQUIRED]** 

      The unique identifier for the gateway local disk that is configured as a stored volume. Use `ListLocalDisks`_ to list disk IDs for a gateway.

      

    
    :type SnapshotId: string
    :param SnapshotId: 

      The snapshot ID (e.g. "snap-1122aabb") of the snapshot to restore as the new stored volume. Specify this field if you want to create the iSCSI storage volume from a snapshot otherwise do not include this field. To list snapshots for your account use `DescribeSnapshots`_ in the *Amazon Elastic Compute Cloud API Reference* .

      

    
    :type PreserveExistingData: boolean
    :param PreserveExistingData: **[REQUIRED]** 

      Specify this field as true if you want to preserve the data on the local disk. Otherwise, specifying this field as false creates an empty volume.

       

      Valid Values: true, false

      

    
    :type TargetName: string
    :param TargetName: **[REQUIRED]** 

      The name of the iSCSI target used by initiators to connect to the target and as a suffix for the target ARN. For example, specifying ``TargetName`` as *myvolume* results in the target ARN of arn:aws:storagegateway:us-east-1:111122223333:gateway/sgw-12A3456B/target/iqn.1997-05.com.amazon:myvolume. The target name must be unique across all volumes of a gateway.

      

    
    :type NetworkInterfaceId: string
    :param NetworkInterfaceId: **[REQUIRED]** 

      The network interface of the gateway on which to expose the iSCSI target. Only IPv4 addresses are accepted. Use  DescribeGatewayInformation to get a list of the network interfaces available on a gateway.

       

      Valid Values: A valid IP address.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VolumeARN': 'string',
            'VolumeSizeInBytes': 123,
            'TargetARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the following fields:

        
        

        - **VolumeARN** *(string) --* 

          The Amazon Resource Name (ARN) of the configured volume.

          
        

        - **VolumeSizeInBytes** *(integer) --* 

          The size of the volume in bytes.

          
        

        - **TargetARN** *(string) --* 

          he Amazon Resource Name (ARN) of the volume target that includes the iSCSI name that initiators can use to connect to the target.

          
    

  .. py:method:: create_tape_with_barcode(**kwargs)

    

    Creates a virtual tape by using your own barcode. You write data to the virtual tape and then archive the tape.

     

    .. note::

      

      Cache storage must be allocated to the gateway before you can create a virtual tape. Use the  AddCache operation to add cache storage to a gateway.

       

    

    **Request Syntax** 
    ::

      response = client.create_tape_with_barcode(
          GatewayARN='string',
          TapeSizeInBytes=123,
          TapeBarcode='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The unique Amazon Resource Name (ARN) that represents the gateway to associate the virtual tape with. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type TapeSizeInBytes: integer
    :param TapeSizeInBytes: **[REQUIRED]** 

      The size, in bytes, of the virtual tape that you want to create.

       

      .. note::

        

        The size must be aligned by gigabyte (1024*1024*1024 byte).

         

      

    
    :type TapeBarcode: string
    :param TapeBarcode: **[REQUIRED]** 

      The barcode that you want to assign to the tape.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        CreateTapeOutput

        
        

        - **TapeARN** *(string) --* 

          A unique Amazon Resource Name (ARN) that represents the virtual tape that was created.

          
    

  .. py:method:: create_tapes(**kwargs)

    

    Creates one or more virtual tapes. You write data to the virtual tapes and then archive the tapes.

     

    .. note::

      

      Cache storage must be allocated to the gateway before you can create virtual tapes. Use the  AddCache operation to add cache storage to a gateway. 

       

    

    **Request Syntax** 
    ::

      response = client.create_tapes(
          GatewayARN='string',
          TapeSizeInBytes=123,
          ClientToken='string',
          NumTapesToCreate=123,
          TapeBarcodePrefix='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The unique Amazon Resource Name (ARN) that represents the gateway to associate the virtual tapes with. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type TapeSizeInBytes: integer
    :param TapeSizeInBytes: **[REQUIRED]** 

      The size, in bytes, of the virtual tapes that you want to create.

       

      .. note::

        

        The size must be aligned by gigabyte (1024*1024*1024 byte).

         

      

    
    :type ClientToken: string
    :param ClientToken: **[REQUIRED]** 

      A unique identifier that you use to retry a request. If you retry a request, use the same ``ClientToken`` you specified in the initial request.

       

      .. note::

        

        Using the same ``ClientToken`` prevents creating the tape multiple times.

         

      

    
    :type NumTapesToCreate: integer
    :param NumTapesToCreate: **[REQUIRED]** 

      The number of virtual tapes that you want to create.

      

    
    :type TapeBarcodePrefix: string
    :param TapeBarcodePrefix: **[REQUIRED]** 

      A prefix that you append to the barcode of the virtual tape you are creating. This prefix makes the barcode unique.

       

      .. note::

        

        The prefix must be 1 to 4 characters in length and must be one of the uppercase letters from A to Z.

         

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeARNs': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        CreateTapeOutput

        
        

        - **TapeARNs** *(list) --* 

          A list of unique Amazon Resource Names (ARNs) that represents the virtual tapes that were created.

          
          

          - *(string) --* 
      
    

  .. py:method:: delete_bandwidth_rate_limit(**kwargs)

    

    Deletes the bandwidth rate limits of a gateway. You can delete either the upload and download bandwidth rate limit, or you can delete both. If you delete only one of the limits, the other limit remains unchanged. To specify which gateway to work with, use the Amazon Resource Name (ARN) of the gateway in your request.

    

    **Request Syntax** 
    ::

      response = client.delete_bandwidth_rate_limit(
          GatewayARN='string',
          BandwidthType='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type BandwidthType: string
    :param BandwidthType: **[REQUIRED]** 

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the of the gateway whose bandwidth rate information was deleted.

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: delete_chap_credentials(**kwargs)

    

    Deletes Challenge-Handshake Authentication Protocol (CHAP) credentials for a specified iSCSI target and initiator pair.

    

    **Request Syntax** 
    ::

      response = client.delete_chap_credentials(
          TargetARN='string',
          InitiatorName='string'
      )
    :type TargetARN: string
    :param TargetARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the iSCSI volume target. Use the  DescribeStorediSCSIVolumes operation to return to retrieve the TargetARN for specified VolumeARN.

      

    
    :type InitiatorName: string
    :param InitiatorName: **[REQUIRED]** 

      The iSCSI initiator that connects to the target.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TargetARN': 'string',
            'InitiatorName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the following fields:

        
        

        - **TargetARN** *(string) --* 

          The Amazon Resource Name (ARN) of the target.

          
        

        - **InitiatorName** *(string) --* 

          The iSCSI initiator that connects to the target.

          
    

  .. py:method:: delete_gateway(**kwargs)

    

    Deletes a gateway. To specify which gateway to delete, use the Amazon Resource Name (ARN) of the gateway in your request. The operation deletes the gateway; however, it does not delete the gateway virtual machine (VM) from your host computer.

     

    After you delete a gateway, you cannot reactivate it. Completed snapshots of the gateway volumes are not deleted upon deleting the gateway, however, pending snapshots will not complete. After you delete a gateway, your next step is to remove it from your environment.

     

    .. warning::

       

      You no longer pay software charges after the gateway is deleted; however, your existing Amazon EBS snapshots persist and you will continue to be billed for these snapshots. You can choose to remove all remaining Amazon EBS snapshots by canceling your Amazon EC2 subscription. If you prefer not to cancel your Amazon EC2 subscription, you can delete your snapshots using the Amazon EC2 console. For more information, see the `AWS Storage Gateway Detail Page`_ . 

       

    

    **Request Syntax** 
    ::

      response = client.delete_gateway(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the id of the deleted gateway.

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: delete_snapshot_schedule(**kwargs)

    

    Deletes a snapshot of a volume.

     

    You can take snapshots of your gateway volumes on a scheduled or ad hoc basis. This API action enables you to delete a snapshot schedule for a volume. For more information, see `Working with Snapshots`_ . In the ``DeleteSnapshotSchedule`` request, you identify the volume by providing its Amazon Resource Name (ARN). 

     

    .. note::

       

      To list or delete a snapshot, you must use the Amazon EC2 API. in *Amazon Elastic Compute Cloud API Reference* .

       

    

    **Request Syntax** 
    ::

      response = client.delete_snapshot_schedule(
          VolumeARN='string'
      )
    :type VolumeARN: string
    :param VolumeARN: **[REQUIRED]** 

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VolumeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **VolumeARN** *(string) --* 
    

  .. py:method:: delete_tape(**kwargs)

    

    Deletes the specified virtual tape.

    

    **Request Syntax** 
    ::

      response = client.delete_tape(
          GatewayARN='string',
          TapeARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The unique Amazon Resource Name (ARN) of the gateway that the virtual tape to delete is associated with. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type TapeARN: string
    :param TapeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the virtual tape to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DeleteTapeOutput

        
        

        - **TapeARN** *(string) --* 

          The Amazon Resource Name (ARN) of the deleted virtual tape.

          
    

  .. py:method:: delete_tape_archive(**kwargs)

    

    Deletes the specified virtual tape from the virtual tape shelf (VTS).

    

    **Request Syntax** 
    ::

      response = client.delete_tape_archive(
          TapeARN='string'
      )
    :type TapeARN: string
    :param TapeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the virtual tape to delete from the virtual tape shelf (VTS).

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DeleteTapeArchiveOutput

        
        

        - **TapeARN** *(string) --* 

          The Amazon Resource Name (ARN) of the virtual tape that was deleted from the virtual tape shelf (VTS).

          
    

  .. py:method:: delete_volume(**kwargs)

    

    Deletes the specified gateway volume that you previously created using the  CreateCachediSCSIVolume or  CreateStorediSCSIVolume API. For gateway-stored volumes, the local disk that was configured as the storage volume is not deleted. You can reuse the local disk to create another storage volume. 

     

    Before you delete a gateway volume, make sure there are no iSCSI connections to the volume you are deleting. You should also make sure there is no snapshot in progress. You can use the Amazon Elastic Compute Cloud (Amazon EC2) API to query snapshots on the volume you are deleting and check the snapshot status. For more information, go to `DescribeSnapshots`_ in the *Amazon Elastic Compute Cloud API Reference* .

     

    In the request, you must provide the Amazon Resource Name (ARN) of the storage volume you want to delete.

    

    **Request Syntax** 
    ::

      response = client.delete_volume(
          VolumeARN='string'
      )
    :type VolumeARN: string
    :param VolumeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the volume. Use the  ListVolumes operation to return a list of gateway volumes.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VolumeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the of the storage volume that was deleted

        
        

        - **VolumeARN** *(string) --* 

          The Amazon Resource Name (ARN) of the storage volume that was deleted. It is the same ARN you provided in the request.

          
    

  .. py:method:: describe_bandwidth_rate_limit(**kwargs)

    

    Returns the bandwidth rate limits of a gateway. By default, these limits are not set, which means no bandwidth rate limiting is in effect.

     

    This operation only returns a value for a bandwidth rate limit only if the limit is set. If no limits are set for the gateway, then this operation returns only the gateway ARN in the response body. To specify which gateway to describe, use the Amazon Resource Name (ARN) of the gateway in your request.

    

    **Request Syntax** 
    ::

      response = client.describe_bandwidth_rate_limit(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'AverageUploadRateLimitInBitsPerSec': 123,
            'AverageDownloadRateLimitInBitsPerSec': 123
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the following fields:

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **AverageUploadRateLimitInBitsPerSec** *(integer) --* 

          The average upload bandwidth rate limit in bits per second. This field does not appear in the response if the upload rate limit is not set.

          
        

        - **AverageDownloadRateLimitInBitsPerSec** *(integer) --* 

          The average download bandwidth rate limit in bits per second. This field does not appear in the response if the download rate limit is not set.

          
    

  .. py:method:: describe_cache(**kwargs)

    

    Returns information about the cache of a gateway. This operation is supported only for the gateway-cached volume architecture.

     

    The response includes disk IDs that are configured as cache, and it includes the amount of cache allocated and used.

    

    **Request Syntax** 
    ::

      response = client.describe_cache(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'DiskIds': [
                'string',
            ],
            'CacheAllocatedInBytes': 123,
            'CacheUsedPercentage': 123.0,
            'CacheDirtyPercentage': 123.0,
            'CacheHitPercentage': 123.0,
            'CacheMissPercentage': 123.0
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **DiskIds** *(list) --* 
          

          - *(string) --* 
      
        

        - **CacheAllocatedInBytes** *(integer) --* 
        

        - **CacheUsedPercentage** *(float) --* 
        

        - **CacheDirtyPercentage** *(float) --* 
        

        - **CacheHitPercentage** *(float) --* 
        

        - **CacheMissPercentage** *(float) --* 
    

  .. py:method:: describe_cached_iscsi_volumes(**kwargs)

    

    Returns a description of the gateway volumes specified in the request. This operation is supported only for the gateway-cached volume architecture.

     

    The list of gateway volumes in the request must be from one gateway. In the response Amazon Storage Gateway returns volume information sorted by volume Amazon Resource Name (ARN).

    

    **Request Syntax** 
    ::

      response = client.describe_cached_iscsi_volumes(
          VolumeARNs=[
              'string',
          ]
      )
    :type VolumeARNs: list
    :param VolumeARNs: **[REQUIRED]** 

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CachediSCSIVolumes': [
                {
                    'VolumeARN': 'string',
                    'VolumeId': 'string',
                    'VolumeType': 'string',
                    'VolumeStatus': 'string',
                    'VolumeSizeInBytes': 123,
                    'VolumeProgress': 123.0,
                    'SourceSnapshotId': 'string',
                    'VolumeiSCSIAttributes': {
                        'TargetARN': 'string',
                        'NetworkInterfaceId': 'string',
                        'NetworkInterfacePort': 123,
                        'LunNumber': 123,
                        'ChapEnabled': True|False
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the following fields:

        
        

        - **CachediSCSIVolumes** *(list) --* 

          An array of objects where each object contains metadata about one cached volume.

          
          

          - *(dict) --* 
            

            - **VolumeARN** *(string) --* 
            

            - **VolumeId** *(string) --* 
            

            - **VolumeType** *(string) --* 
            

            - **VolumeStatus** *(string) --* 
            

            - **VolumeSizeInBytes** *(integer) --* 
            

            - **VolumeProgress** *(float) --* 
            

            - **SourceSnapshotId** *(string) --* 
            

            - **VolumeiSCSIAttributes** *(dict) --* 

              Lists iSCSI information about a volume.

              
              

              - **TargetARN** *(string) --* 

                The Amazon Resource Name (ARN) of the volume target.

                
              

              - **NetworkInterfaceId** *(string) --* 

                The network interface identifier.

                
              

              - **NetworkInterfacePort** *(integer) --* 

                The port used to communicate with iSCSI targets.

                
              

              - **LunNumber** *(integer) --* 

                The logical disk number.

                
              

              - **ChapEnabled** *(boolean) --* 

                Indicates whether mutual CHAP is enabled for the iSCSI target.

                
          
        
      
    

  .. py:method:: describe_chap_credentials(**kwargs)

    

    Returns an array of Challenge-Handshake Authentication Protocol (CHAP) credentials information for a specified iSCSI target, one for each target-initiator pair.

    

    **Request Syntax** 
    ::

      response = client.describe_chap_credentials(
          TargetARN='string'
      )
    :type TargetARN: string
    :param TargetARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the iSCSI volume target. Use the  DescribeStorediSCSIVolumes operation to return to retrieve the TargetARN for specified VolumeARN.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChapCredentials': [
                {
                    'TargetARN': 'string',
                    'SecretToAuthenticateInitiator': 'string',
                    'InitiatorName': 'string',
                    'SecretToAuthenticateTarget': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing a .

        
        

        - **ChapCredentials** *(list) --* 

          An array of  ChapInfo objects that represent CHAP credentials. Each object in the array contains CHAP credential information for one target-initiator pair. If no CHAP credentials are set, an empty array is returned. CHAP credential information is provided in a JSON object with the following fields:

           

           
          * **InitiatorName** : The iSCSI initiator that connects to the target. 
           
          * **SecretToAuthenticateInitiator** : The secret key that the initiator (for example, the Windows client) must provide to participate in mutual CHAP with the target. 
           
          * **SecretToAuthenticateTarget** : The secret key that the target must provide to participate in mutual CHAP with the initiator (e.g. Windows client). 
           
          * **TargetARN** : The Amazon Resource Name (ARN) of the storage volume. 
           

          
          

          - *(dict) --* 

            Describes Challenge-Handshake Authentication Protocol (CHAP) information that supports authentication between your gateway and iSCSI initiators.

            
            

            - **TargetARN** *(string) --* 

              The Amazon Resource Name (ARN) of the volume.

               

              Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

              
            

            - **SecretToAuthenticateInitiator** *(string) --* 

              The secret key that the initiator (for example, the Windows client) must provide to participate in mutual CHAP with the target.

              
            

            - **InitiatorName** *(string) --* 

              The iSCSI initiator that connects to the target.

              
            

            - **SecretToAuthenticateTarget** *(string) --* 

              The secret key that the target must provide to participate in mutual CHAP with the initiator (e.g. Windows client).

              
        
      
    

  .. py:method:: describe_gateway_information(**kwargs)

    

    Returns metadata about a gateway such as its name, network interfaces, configured time zone, and the state (whether the gateway is running or not). To specify which gateway to describe, use the Amazon Resource Name (ARN) of the gateway in your request.

    

    **Request Syntax** 
    ::

      response = client.describe_gateway_information(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'GatewayId': 'string',
            'GatewayName': 'string',
            'GatewayTimezone': 'string',
            'GatewayState': 'string',
            'GatewayNetworkInterfaces': [
                {
                    'Ipv4Address': 'string',
                    'MacAddress': 'string',
                    'Ipv6Address': 'string'
                },
            ],
            'GatewayType': 'string',
            'NextUpdateAvailabilityDate': 'string',
            'LastSoftwareUpdate': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the following fields:

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **GatewayId** *(string) --* 

          The unique identifier assigned to your gateway during activation. This ID becomes part of the gateway Amazon Resource Name (ARN), which you use as input for other operations.

          
        

        - **GatewayName** *(string) --* 

          The name you configured for your gateway.

          
        

        - **GatewayTimezone** *(string) --* 

          A value that indicates the time zone configured for the gateway.

          
        

        - **GatewayState** *(string) --* 

          A value that indicates the operating state of the gateway.

          
        

        - **GatewayNetworkInterfaces** *(list) --* 

          A  NetworkInterface array that contains descriptions of the gateway network interfaces.

          
          

          - *(dict) --* 

            Describes a gateway's network interface.

            
            

            - **Ipv4Address** *(string) --* 

              The Internet Protocol version 4 (IPv4) address of the interface.

              
            

            - **MacAddress** *(string) --* 

              The Media Access Control (MAC) address of the interface.

               

              .. note::

                

                This is currently unsupported and will not be returned in output.

                 

              
            

            - **Ipv6Address** *(string) --* 

              The Internet Protocol version 6 (IPv6) address of the interface. *Currently not supported* .

              
        
      
        

        - **GatewayType** *(string) --* 

          The type of the gateway.

          
        

        - **NextUpdateAvailabilityDate** *(string) --* 

          The date on which an update to the gateway is available. This date is in the time zone of the gateway. If the gateway is not available for an update this field is not returned in the response.

          
        

        - **LastSoftwareUpdate** *(string) --* 

          The date on which the last software update was applied to the gateway. If the gateway has never been updated, this field does not return a value in the response.

          
    

  .. py:method:: describe_maintenance_start_time(**kwargs)

    

    Returns your gateway's weekly maintenance start time including the day and time of the week. Note that values are in terms of the gateway's time zone.

    

    **Request Syntax** 
    ::

      response = client.describe_maintenance_start_time(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'HourOfDay': 123,
            'MinuteOfHour': 123,
            'DayOfWeek': 123,
            'Timezone': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **HourOfDay** *(integer) --* 
        

        - **MinuteOfHour** *(integer) --* 
        

        - **DayOfWeek** *(integer) --* 
        

        - **Timezone** *(string) --* 
    

  .. py:method:: describe_snapshot_schedule(**kwargs)

    

    Describes the snapshot schedule for the specified gateway volume. The snapshot schedule information includes intervals at which snapshots are automatically initiated on the volume.

    

    **Request Syntax** 
    ::

      response = client.describe_snapshot_schedule(
          VolumeARN='string'
      )
    :type VolumeARN: string
    :param VolumeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the volume. Use the  ListVolumes operation to return a list of gateway volumes.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VolumeARN': 'string',
            'StartAt': 123,
            'RecurrenceInHours': 123,
            'Description': 'string',
            'Timezone': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **VolumeARN** *(string) --* 
        

        - **StartAt** *(integer) --* 
        

        - **RecurrenceInHours** *(integer) --* 
        

        - **Description** *(string) --* 
        

        - **Timezone** *(string) --* 
    

  .. py:method:: describe_stored_iscsi_volumes(**kwargs)

    

    Returns the description of the gateway volumes specified in the request. The list of gateway volumes in the request must be from one gateway. In the response Amazon Storage Gateway returns volume information sorted by volume ARNs.

    

    **Request Syntax** 
    ::

      response = client.describe_stored_iscsi_volumes(
          VolumeARNs=[
              'string',
          ]
      )
    :type VolumeARNs: list
    :param VolumeARNs: **[REQUIRED]** 

      An array of strings where each string represents the Amazon Resource Name (ARN) of a stored volume. All of the specified stored volumes must from the same gateway. Use  ListVolumes to get volume ARNs for a gateway.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'StorediSCSIVolumes': [
                {
                    'VolumeARN': 'string',
                    'VolumeId': 'string',
                    'VolumeType': 'string',
                    'VolumeStatus': 'string',
                    'VolumeSizeInBytes': 123,
                    'VolumeProgress': 123.0,
                    'VolumeDiskId': 'string',
                    'SourceSnapshotId': 'string',
                    'PreservedExistingData': True|False,
                    'VolumeiSCSIAttributes': {
                        'TargetARN': 'string',
                        'NetworkInterfaceId': 'string',
                        'NetworkInterfacePort': 123,
                        'LunNumber': 123,
                        'ChapEnabled': True|False
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **StorediSCSIVolumes** *(list) --* 
          

          - *(dict) --* 
            

            - **VolumeARN** *(string) --* 
            

            - **VolumeId** *(string) --* 
            

            - **VolumeType** *(string) --* 
            

            - **VolumeStatus** *(string) --* 
            

            - **VolumeSizeInBytes** *(integer) --* 
            

            - **VolumeProgress** *(float) --* 
            

            - **VolumeDiskId** *(string) --* 
            

            - **SourceSnapshotId** *(string) --* 
            

            - **PreservedExistingData** *(boolean) --* 
            

            - **VolumeiSCSIAttributes** *(dict) --* 

              Lists iSCSI information about a volume.

              
              

              - **TargetARN** *(string) --* 

                The Amazon Resource Name (ARN) of the volume target.

                
              

              - **NetworkInterfaceId** *(string) --* 

                The network interface identifier.

                
              

              - **NetworkInterfacePort** *(integer) --* 

                The port used to communicate with iSCSI targets.

                
              

              - **LunNumber** *(integer) --* 

                The logical disk number.

                
              

              - **ChapEnabled** *(boolean) --* 

                Indicates whether mutual CHAP is enabled for the iSCSI target.

                
          
        
      
    

  .. py:method:: describe_tape_archives(**kwargs)

    

    Returns a description of specified virtual tapes in the virtual tape shelf (VTS).

     

    If a specific ``TapeARN`` is not specified, AWS Storage Gateway returns a description of all virtual tapes found in the VTS associated with your account.

    

    **Request Syntax** 
    ::

      response = client.describe_tape_archives(
          TapeARNs=[
              'string',
          ],
          Marker='string',
          Limit=123
      )
    :type TapeARNs: list
    :param TapeARNs: 

      Specifies one or more unique Amazon Resource Names (ARNs) that represent the virtual tapes you want to describe.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      An opaque string that indicates the position at which to begin describing virtual tapes.

      

    
    :type Limit: integer
    :param Limit: 

      Specifies that the number of virtual tapes descried be limited to the specified number.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeArchives': [
                {
                    'TapeARN': 'string',
                    'TapeBarcode': 'string',
                    'TapeSizeInBytes': 123,
                    'CompletionTime': datetime(2015, 1, 1),
                    'RetrievedTo': 'string',
                    'TapeStatus': 'string'
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DescribeTapeArchivesOutput

        
        

        - **TapeArchives** *(list) --* 

          An array of virtual tape objects in the virtual tape shelf (VTS). The description includes of the Amazon Resource Name(ARN) of the virtual tapes. The information returned includes the Amazon Resource Names (ARNs) of the tapes, size of the tapes, status of the tapes, progress of the description and tape barcode.

          
          

          - *(dict) --* 

            Represents a virtual tape that is archived in the virtual tape shelf (VTS).

            
            

            - **TapeARN** *(string) --* 

              The Amazon Resource Name (ARN) of an archived virtual tape.

              
            

            - **TapeBarcode** *(string) --* 

              The barcode that identifies the archived virtual tape.

              
            

            - **TapeSizeInBytes** *(integer) --* 

              The size, in bytes, of the archived virtual tape.

              
            

            - **CompletionTime** *(datetime) --* 

              The time that the archiving of the virtual tape was completed.

               

              The string format of the completion time is in the ISO8601 extended YYYY-MM-DD'T'HH:MM:SS'Z' format.

              
            

            - **RetrievedTo** *(string) --* 

              The Amazon Resource Name (ARN) of the gateway-VTL that the virtual tape is being retrieved to.

               

              The virtual tape is retrieved from the virtual tape shelf (VTS).

              
            

            - **TapeStatus** *(string) --* 

              The current state of the archived virtual tape.

              
        
      
        

        - **Marker** *(string) --* 

          An opaque string that indicates the position at which the virtual tapes that were fetched for description ended. Use this marker in your next request to fetch the next set of virtual tapes in the virtual tape shelf (VTS). If there are no more virtual tapes to describe, this field does not appear in the response.

          
    

  .. py:method:: describe_tape_recovery_points(**kwargs)

    

    Returns a list of virtual tape recovery points that are available for the specified gateway-VTL.

     

    A recovery point is a point-in-time view of a virtual tape at which all the data on the virtual tape is consistent. If your gateway crashes, virtual tapes that have recovery points can be recovered to a new gateway.

    

    **Request Syntax** 
    ::

      response = client.describe_tape_recovery_points(
          GatewayARN='string',
          Marker='string',
          Limit=123
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type Marker: string
    :param Marker: 

      An opaque string that indicates the position at which to begin describing the virtual tape recovery points.

      

    
    :type Limit: integer
    :param Limit: 

      Specifies that the number of virtual tape recovery points that are described be limited to the specified number.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'TapeRecoveryPointInfos': [
                {
                    'TapeARN': 'string',
                    'TapeRecoveryPointTime': datetime(2015, 1, 1),
                    'TapeSizeInBytes': 123,
                    'TapeStatus': 'string'
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DescribeTapeRecoveryPointsOutput

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **TapeRecoveryPointInfos** *(list) --* 

          An array of TapeRecoveryPointInfos that are available for the specified gateway.

          
          

          - *(dict) --* 

            Describes a recovery point.

            
            

            - **TapeARN** *(string) --* 

              The Amazon Resource Name (ARN) of the virtual tape.

              
            

            - **TapeRecoveryPointTime** *(datetime) --* 

              The time when the point-in-time view of the virtual tape was replicated for later recovery.

               

              The string format of the tape recovery point time is in the ISO8601 extended YYYY-MM-DD'T'HH:MM:SS'Z' format.

              
            

            - **TapeSizeInBytes** *(integer) --* 

              The size, in bytes, of the virtual tapes to recover.

              
            

            - **TapeStatus** *(string) --* 
        
      
        

        - **Marker** *(string) --* 

          An opaque string that indicates the position at which the virtual tape recovery points that were listed for description ended.

           

          Use this marker in your next request to list the next set of virtual tape recovery points in the list. If there are no more recovery points to describe, this field does not appear in the response.

          
    

  .. py:method:: describe_tapes(**kwargs)

    

    Returns a description of the specified Amazon Resource Name (ARN) of virtual tapes. If a ``TapeARN`` is not specified, returns a description of all virtual tapes associated with the specified gateway.

    

    **Request Syntax** 
    ::

      response = client.describe_tapes(
          GatewayARN='string',
          TapeARNs=[
              'string',
          ],
          Marker='string',
          Limit=123
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type TapeARNs: list
    :param TapeARNs: 

      Specifies one or more unique Amazon Resource Names (ARNs) that represent the virtual tapes you want to describe. If this parameter is not specified, AWS Storage Gateway returns a description of all virtual tapes associated with the specified gateway.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      A marker value, obtained in a previous call to ``DescribeTapes`` . This marker indicates which page of results to retrieve. 

       

      If not specified, the first page of results is retrieved.

      

    
    :type Limit: integer
    :param Limit: 

      Specifies that the number of virtual tapes described be limited to the specified number.

       

      .. note::

        

        Amazon Web Services may impose its own limit, if this field is not set.

         

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Tapes': [
                {
                    'TapeARN': 'string',
                    'TapeBarcode': 'string',
                    'TapeSizeInBytes': 123,
                    'TapeStatus': 'string',
                    'VTLDevice': 'string',
                    'Progress': 123.0
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DescribeTapesOutput

        
        

        - **Tapes** *(list) --* 

          An array of virtual tape descriptions.

          
          

          - *(dict) --* 

            Describes a virtual tape object.

            
            

            - **TapeARN** *(string) --* 

              The Amazon Resource Name (ARN) of the virtual tape.

              
            

            - **TapeBarcode** *(string) --* 

              The barcode that identifies a specific virtual tape.

              
            

            - **TapeSizeInBytes** *(integer) --* 

              The size, in bytes, of the virtual tape.

              
            

            - **TapeStatus** *(string) --* 

              The current state of the virtual tape.

              
            

            - **VTLDevice** *(string) --* 

              The virtual tape library (VTL) device that the virtual tape is associated with.

              
            

            - **Progress** *(float) --* 

              For archiving virtual tapes, indicates how much data remains to be uploaded before archiving is complete.

               

              Range: 0 (not started) to 100 (complete).

              
        
      
        

        - **Marker** *(string) --* 

          An opaque string which can be used as part of a subsequent DescribeTapes call to retrieve the next page of results.

           

          If a response does not contain a marker, then there are no more results to be retrieved.

          
    

  .. py:method:: describe_upload_buffer(**kwargs)

    

    Returns information about the upload buffer of a gateway. This operation is supported for both the gateway-stored and gateway-cached volume architectures.

     

    The response includes disk IDs that are configured as upload buffer space, and it includes the amount of upload buffer space allocated and used.

    

    **Request Syntax** 
    ::

      response = client.describe_upload_buffer(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'DiskIds': [
                'string',
            ],
            'UploadBufferUsedInBytes': 123,
            'UploadBufferAllocatedInBytes': 123
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **DiskIds** *(list) --* 
          

          - *(string) --* 
      
        

        - **UploadBufferUsedInBytes** *(integer) --* 
        

        - **UploadBufferAllocatedInBytes** *(integer) --* 
    

  .. py:method:: describe_vtl_devices(**kwargs)

    

    Returns a description of virtual tape library (VTL) devices for the specified gateway. In the response, AWS Storage Gateway returns VTL device information.

     

    The list of VTL devices must be from one gateway.

    

    **Request Syntax** 
    ::

      response = client.describe_vtl_devices(
          GatewayARN='string',
          VTLDeviceARNs=[
              'string',
          ],
          Marker='string',
          Limit=123
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type VTLDeviceARNs: list
    :param VTLDeviceARNs: 

      An array of strings, where each string represents the Amazon Resource Name (ARN) of a VTL device.

       

      .. note::

        

        All of the specified VTL devices must be from the same gateway. If no VTL devices are specified, the result will contain all devices on the specified gateway.

         

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      An opaque string that indicates the position at which to begin describing the VTL devices.

      

    
    :type Limit: integer
    :param Limit: 

      Specifies that the number of VTL devices described be limited to the specified number.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'VTLDevices': [
                {
                    'VTLDeviceARN': 'string',
                    'VTLDeviceType': 'string',
                    'VTLDeviceVendor': 'string',
                    'VTLDeviceProductIdentifier': 'string',
                    'DeviceiSCSIAttributes': {
                        'TargetARN': 'string',
                        'NetworkInterfaceId': 'string',
                        'NetworkInterfacePort': 123,
                        'ChapEnabled': True|False
                    }
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DescribeVTLDevicesOutput

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **VTLDevices** *(list) --* 

          An array of VTL device objects composed of the Amazon Resource Name(ARN) of the VTL devices.

          
          

          - *(dict) --* 

            Represents a device object associated with a gateway-VTL.

            
            

            - **VTLDeviceARN** *(string) --* 

              Specifies the unique Amazon Resource Name (ARN) of the device (tape drive or media changer).

              
            

            - **VTLDeviceType** *(string) --* 
            

            - **VTLDeviceVendor** *(string) --* 
            

            - **VTLDeviceProductIdentifier** *(string) --* 
            

            - **DeviceiSCSIAttributes** *(dict) --* 

              A list of iSCSI information about a VTL device.

              
              

              - **TargetARN** *(string) --* 

                Specifies the unique Amazon Resource Name(ARN) that encodes the iSCSI qualified name(iqn) of a tape drive or media changer target.

                
              

              - **NetworkInterfaceId** *(string) --* 

                The network interface identifier of the VTL device.

                
              

              - **NetworkInterfacePort** *(integer) --* 

                The port used to communicate with iSCSI VTL device targets.

                
              

              - **ChapEnabled** *(boolean) --* 

                Indicates whether mutual CHAP is enabled for the iSCSI target.

                
          
        
      
        

        - **Marker** *(string) --* 

          An opaque string that indicates the position at which the VTL devices that were fetched for description ended. Use the marker in your next request to fetch the next set of VTL devices in the list. If there are no more VTL devices to describe, this field does not appear in the response.

          
    

  .. py:method:: describe_working_storage(**kwargs)

    

    Returns information about the working storage of a gateway. This operation is supported only for the gateway-stored volume architecture. This operation is deprecated in cached-volumes API version (20120630). Use DescribeUploadBuffer instead.

     

    .. note::

       

      Working storage is also referred to as upload buffer. You can also use the DescribeUploadBuffer operation to add upload buffer to a stored-volume gateway.

       

     

    The response includes disk IDs that are configured as working storage, and it includes the amount of working storage allocated and used.

    

    **Request Syntax** 
    ::

      response = client.describe_working_storage(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'DiskIds': [
                'string',
            ],
            'WorkingStorageUsedInBytes': 123,
            'WorkingStorageAllocatedInBytes': 123
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the following fields:

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **DiskIds** *(list) --* 

          An array of the gateway's local disk IDs that are configured as working storage. Each local disk ID is specified as a string (minimum length of 1 and maximum length of 300). If no local disks are configured as working storage, then the DiskIds array is empty.

          
          

          - *(string) --* 
      
        

        - **WorkingStorageUsedInBytes** *(integer) --* 

          The total working storage in bytes in use by the gateway. If no working storage is configured for the gateway, this field returns 0.

          
        

        - **WorkingStorageAllocatedInBytes** *(integer) --* 

          The total working storage in bytes allocated for the gateway. If no working storage is configured for the gateway, this field returns 0.

          
    

  .. py:method:: disable_gateway(**kwargs)

    

    Disables a gateway when the gateway is no longer functioning. For example, if your gateway VM is damaged, you can disable the gateway so you can recover virtual tapes.

     

    Use this operation for a gateway-VTL that is not reachable or not functioning.

     

    .. warning::

      

      Once a gateway is disabled it cannot be enabled.

       

    

    **Request Syntax** 
    ::

      response = client.disable_gateway(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DisableGatewayOutput

        
        

        - **GatewayARN** *(string) --* 

          The unique Amazon Resource Name of the disabled gateway.

          
    

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

        


  .. py:method:: list_gateways(**kwargs)

    

    Lists gateways owned by an AWS account in a region specified in the request. The returned list is ordered by gateway Amazon Resource Name (ARN).

     

    By default, the operation returns a maximum of 100 gateways. This operation supports pagination that allows you to optionally reduce the number of gateways returned in a response.

     

    If you have more gateways than are returned in a response (that is, the response returns only a truncated list of your gateways), the response contains a marker that you can specify in your next request to fetch the next page of gateways.

    

    **Request Syntax** 
    ::

      response = client.list_gateways(
          Marker='string',
          Limit=123
      )
    :type Marker: string
    :param Marker: 

      An opaque string that indicates the position at which to begin the returned list of gateways.

      

    
    :type Limit: integer
    :param Limit: 

      Specifies that the list of gateways returned be limited to the specified number of items.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Gateways': [
                {
                    'GatewayId': 'string',
                    'GatewayARN': 'string',
                    'GatewayType': 'string',
                    'GatewayOperationalState': 'string',
                    'GatewayName': 'string'
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Gateways** *(list) --* 
          

          - *(dict) --* 

            Describes a gateway object.

            
            

            - **GatewayId** *(string) --* 

              The unique identifier assigned to your gateway during activation. This ID becomes part of the gateway Amazon Resource Name (ARN), which you use as input for other operations.

              
            

            - **GatewayARN** *(string) --* 

              The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

              
            

            - **GatewayType** *(string) --* 

              The type of the gateway.

              
            

            - **GatewayOperationalState** *(string) --* 

              The state of the gateway.

               

              Valid Values: DISABLED or ACTIVE

              
            

            - **GatewayName** *(string) --* 

              The name of the gateway.

              
        
      
        

        - **Marker** *(string) --* 
    

  .. py:method:: list_local_disks(**kwargs)

    

    Returns a list of the gateway's local disks. To specify which gateway to describe, you use the Amazon Resource Name (ARN) of the gateway in the body of the request.

     

    The request returns a list of all disks, specifying which are configured as working storage, cache storage, or stored volume or not configured at all. The response includes a ``DiskStatus`` field. This field can have a value of present (the disk is available to use), missing (the disk is no longer connected to the gateway), or mismatch (the disk node is occupied by a disk that has incorrect metadata or the disk content is corrupted). 

    

    **Request Syntax** 
    ::

      response = client.list_local_disks(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'Disks': [
                {
                    'DiskId': 'string',
                    'DiskPath': 'string',
                    'DiskNode': 'string',
                    'DiskStatus': 'string',
                    'DiskSizeInBytes': 123,
                    'DiskAllocationType': 'string',
                    'DiskAllocationResource': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **Disks** *(list) --* 
          

          - *(dict) --* 
            

            - **DiskId** *(string) --* 
            

            - **DiskPath** *(string) --* 
            

            - **DiskNode** *(string) --* 
            

            - **DiskStatus** *(string) --* 
            

            - **DiskSizeInBytes** *(integer) --* 
            

            - **DiskAllocationType** *(string) --* 
            

            - **DiskAllocationResource** *(string) --* 
        
      
    

  .. py:method:: list_tags_for_resource(**kwargs)

    

    Lists the tags that have been added to the specified resource.

    

    **Request Syntax** 
    ::

      response = client.list_tags_for_resource(
          ResourceARN='string',
          Marker='string',
          Limit=123
      )
    :type ResourceARN: string
    :param ResourceARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the resource for which you want to list tags.

      

    
    :type Marker: string
    :param Marker: 

      An opaque string that indicates the position at which to begin returning the list of tags.

      

    
    :type Limit: integer
    :param Limit: 

      Specifies that the list of tags returned be limited to the specified number of items.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ResourceARN': 'string',
            'Marker': 'string',
            'Tags': [
                {
                    'Key': 'string',
                    'Value': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        ListTagsForResourceOutput

        
        

        - **ResourceARN** *(string) --* 

          he Amazon Resource Name (ARN) of the resource for which you want to list tags.

          
        

        - **Marker** *(string) --* 

          An opaque string that indicates the position at which to stop returning the list of tags.

          
        

        - **Tags** *(list) --* 

          An array that contains the tags for the specified resource.

          
          

          - *(dict) --* 
            

            - **Key** *(string) --* 
            

            - **Value** *(string) --* 
        
      
    

  .. py:method:: list_tapes(**kwargs)

    

    Lists virtual tapes in your virtual tape library (VTL) and your virtual tape shelf (VTS). You specify the tapes to list by specifying one or more tape Amazon Resource Names (ARNs). If you don't specify a tape ARN, the operation lists all virtual tapes in both your VTL and VTS.

     

    This operation supports pagination. By default, the operation returns a maximum of up to 100 tapes. You can optionally specify the ``Limit`` parameter in the body to limit the number of tapes in the response. If the number of tapes returned in the response is truncated, the response includes a ``Marker`` element that you can use in your subsequent request to retrieve the next set of tapes.

    

    **Request Syntax** 
    ::

      response = client.list_tapes(
          TapeARNs=[
              'string',
          ],
          Marker='string',
          Limit=123
      )
    :type TapeARNs: list
    :param TapeARNs: 

      The Amazon Resource Name (ARN) of each of the tapes you want to list. If you don't specify a tape ARN, the response lists all tapes in both your VTL and VTS.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      A string that indicates the position at which to begin the returned list of tapes.

      

    
    :type Limit: integer
    :param Limit: 

      An optional number limit for the tapes in the list returned by this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeInfos': [
                {
                    'TapeARN': 'string',
                    'TapeBarcode': 'string',
                    'TapeSizeInBytes': 123,
                    'TapeStatus': 'string',
                    'GatewayARN': 'string'
                },
            ],
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the following fields:

         

         
        *  ListTapesOutput$Marker   
         
        *  ListTapesOutput$VolumeInfos   
         

        
        

        - **TapeInfos** *(list) --* 

          An array of  TapeInfo objects, where each object describes an a single tape. If there not tapes in the tape library or VTS, then the ``TapeInfos`` is an empty array.

          
          

          - *(dict) --* 

            Describes a virtual tape.

            
            

            - **TapeARN** *(string) --* 

              The Amazon Resource Name (ARN) of a virtual tape.

              
            

            - **TapeBarcode** *(string) --* 

              The barcode that identifies a specific virtual tape.

              
            

            - **TapeSizeInBytes** *(integer) --* 

              The size, in bytes, of a virtual tape.

              
            

            - **TapeStatus** *(string) --* 

              The status of the tape.

              
            

            - **GatewayARN** *(string) --* 

              The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

              
        
      
        

        - **Marker** *(string) --* 

          A string that indicates the position at which to begin returning the next list of tapes. Use the marker in your next request to continue pagination of tapes. If there are no more tapes to list, this element does not appear in the response body.

          
    

  .. py:method:: list_volume_initiators(**kwargs)

    

    Lists iSCSI initiators that are connected to a volume. You can use this operation to determine whether a volume is being used or not.

    

    **Request Syntax** 
    ::

      response = client.list_volume_initiators(
          VolumeARN='string'
      )
    :type VolumeARN: string
    :param VolumeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the volume. Use the  ListVolumes operation to return a list of gateway volumes for the gateway.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Initiators': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        ListVolumeInitiatorsOutput

        
        

        - **Initiators** *(list) --* 

          The host names and port numbers of all iSCSI initiators that are connected to the gateway.

          
          

          - *(string) --* 
      
    

  .. py:method:: list_volume_recovery_points(**kwargs)

    

    Lists the recovery points for a specified gateway. This operation is supported only for the gateway-cached volume architecture.

     

    Each gateway-cached volume has one recovery point. A volume recovery point is a point in time at which all data of the volume is consistent and from which you can create a snapshot. To create a snapshot from a volume recovery point use the  CreateSnapshotFromVolumeRecoveryPoint operation.

    

    **Request Syntax** 
    ::

      response = client.list_volume_recovery_points(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'VolumeRecoveryPointInfos': [
                {
                    'VolumeARN': 'string',
                    'VolumeSizeInBytes': 123,
                    'VolumeUsageInBytes': 123,
                    'VolumeRecoveryPointTime': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **VolumeRecoveryPointInfos** *(list) --* 
          

          - *(dict) --* 
            

            - **VolumeARN** *(string) --* 
            

            - **VolumeSizeInBytes** *(integer) --* 
            

            - **VolumeUsageInBytes** *(integer) --* 
            

            - **VolumeRecoveryPointTime** *(string) --* 
        
      
    

  .. py:method:: list_volumes(**kwargs)

    

    Lists the iSCSI stored volumes of a gateway. Results are sorted by volume ARN. The response includes only the volume ARNs. If you want additional volume information, use the  DescribeStorediSCSIVolumes API.

     

    The operation supports pagination. By default, the operation returns a maximum of up to 100 volumes. You can optionally specify the ``Limit`` field in the body to limit the number of volumes in the response. If the number of volumes returned in the response is truncated, the response includes a Marker field. You can use this Marker value in your subsequent request to retrieve the next set of volumes.

    

    **Request Syntax** 
    ::

      response = client.list_volumes(
          GatewayARN='string',
          Marker='string',
          Limit=123
      )
    :type GatewayARN: string
    :param GatewayARN: 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type Marker: string
    :param Marker: 

      A string that indicates the position at which to begin the returned list of volumes. Obtain the marker from the response of a previous List iSCSI Volumes request.

      

    
    :type Limit: integer
    :param Limit: 

      Specifies that the list of volumes returned be limited to the specified number of items.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'Marker': 'string',
            'VolumeInfos': [
                {
                    'VolumeARN': 'string',
                    'VolumeId': 'string',
                    'GatewayARN': 'string',
                    'GatewayId': 'string',
                    'VolumeType': 'string',
                    'VolumeSizeInBytes': 123
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **Marker** *(string) --* 
        

        - **VolumeInfos** *(list) --* 
          

          - *(dict) --* 

            Describes a storage volume object.

            
            

            - **VolumeARN** *(string) --* 

              The Amazon Resource Name (ARN) for the storage volume. For example, the following is a valid ARN:

               

               ``arn:aws:storagegateway:us-east-1:111122223333:gateway/sgw-12A3456B/volume/vol-1122AABB``  

               

              Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

              
            

            - **VolumeId** *(string) --* 

              The unique identifier assigned to the volume. This ID becomes part of the volume Amazon Resource Name (ARN), which you use as input for other operations.

               

              Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

              
            

            - **GatewayARN** *(string) --* 

              The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

              
            

            - **GatewayId** *(string) --* 

              The unique identifier assigned to your gateway during activation. This ID becomes part of the gateway Amazon Resource Name (ARN), which you use as input for other operations.

               

              Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

              
            

            - **VolumeType** *(string) --* 
            

            - **VolumeSizeInBytes** *(integer) --* 

              The size, in bytes, of the volume.

               

              Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

              
        
      
    

  .. py:method:: remove_tags_from_resource(**kwargs)

    

    Removes one or more tags from the specified resource.

    

    **Request Syntax** 
    ::

      response = client.remove_tags_from_resource(
          ResourceARN='string',
          TagKeys=[
              'string',
          ]
      )
    :type ResourceARN: string
    :param ResourceARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the resource you want to remove the tags from.

      

    
    :type TagKeys: list
    :param TagKeys: **[REQUIRED]** 

      The keys of the tags you want to remove from the specified resource. A tag is composed of a key/value pair.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ResourceARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        RemoveTagsFromResourceOutput

        
        

        - **ResourceARN** *(string) --* 

          The Amazon Resource Name (ARN) of the resource that the tags were removed from.

          
    

  .. py:method:: reset_cache(**kwargs)

    

    Resets all cache disks that have encountered a error and makes the disks available for reconfiguration as cache storage. If your cache disk encounters a error, the gateway prevents read and write operations on virtual tapes in the gateway. For example, an error can occur when a disk is corrupted or removed from the gateway. When a cache is reset, the gateway loses its cache storage. At this point you can reconfigure the disks as cache disks.

     

    .. warning::

       

      If the cache disk you are resetting contains data that has not been uploaded to Amazon S3 yet, that data can be lost. After you reset cache disks, there will be no configured cache disks left in the gateway, so you must configure at least one new cache disk for your gateway to function properly.

       

    

    **Request Syntax** 
    ::

      response = client.reset_cache(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: retrieve_tape_archive(**kwargs)

    

    Retrieves an archived virtual tape from the virtual tape shelf (VTS) to a gateway-VTL. Virtual tapes archived in the VTS are not associated with any gateway. However after a tape is retrieved, it is associated with a gateway, even though it is also listed in the VTS.

     

    Once a tape is successfully retrieved to a gateway, it cannot be retrieved again to another gateway. You must archive the tape again before you can retrieve it to another gateway.

    

    **Request Syntax** 
    ::

      response = client.retrieve_tape_archive(
          TapeARN='string',
          GatewayARN='string'
      )
    :type TapeARN: string
    :param TapeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the virtual tape you want to retrieve from the virtual tape shelf (VTS).

      

    
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway you want to retrieve the virtual tape to. Use the  ListGateways operation to return a list of gateways for your account and region.

       

      You retrieve archived virtual tapes to only one gateway and the gateway must be a gateway-VTL.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        RetrieveTapeArchiveOutput

        
        

        - **TapeARN** *(string) --* 

          The Amazon Resource Name (ARN) of the retrieved virtual tape.

          
    

  .. py:method:: retrieve_tape_recovery_point(**kwargs)

    

    Retrieves the recovery point for the specified virtual tape.

     

    A recovery point is a point in time view of a virtual tape at which all the data on the tape is consistent. If your gateway crashes, virtual tapes that have recovery points can be recovered to a new gateway.

     

    .. note::

      

      The virtual tape can be retrieved to only one gateway. The retrieved tape is read-only. The virtual tape can be retrieved to only a gateway-VTL. There is no charge for retrieving recovery points.

       

    

    **Request Syntax** 
    ::

      response = client.retrieve_tape_recovery_point(
          TapeARN='string',
          GatewayARN='string'
      )
    :type TapeARN: string
    :param TapeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the virtual tape for which you want to retrieve the recovery point.

      

    
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TapeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        RetrieveTapeRecoveryPointOutput

        
        

        - **TapeARN** *(string) --* 

          The Amazon Resource Name (ARN) of the virtual tape for which the recovery point was retrieved.

          
    

  .. py:method:: set_local_console_password(**kwargs)

    

    Sets the password for your VM local console. When you log in to the local console for the first time, you log in to the VM with the default credentials. We recommend that you set a new password. You don't need to know the default password to set a new password.

    

    **Request Syntax** 
    ::

      response = client.set_local_console_password(
          GatewayARN='string',
          LocalConsolePassword='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type LocalConsolePassword: string
    :param LocalConsolePassword: **[REQUIRED]** 

      The password you want to set for your VM local console.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: shutdown_gateway(**kwargs)

    

    Shuts down a gateway. To specify which gateway to shut down, use the Amazon Resource Name (ARN) of the gateway in the body of your request.

     

    The operation shuts down the gateway service component running in the storage gateway's virtual machine (VM) and not the VM.

     

    .. note::

      

      If you want to shut down the VM, it is recommended that you first shut down the gateway component in the VM to avoid unpredictable conditions.

       

     

    After the gateway is shutdown, you cannot call any other API except  StartGateway ,  DescribeGatewayInformation , and  ListGateways . For more information, see  ActivateGateway . Your applications cannot read from or write to the gateway's storage volumes, and there are no snapshots taken.

     

    .. note::

      

      When you make a shutdown request, you will get a ``200 OK`` success response immediately. However, it might take some time for the gateway to shut down. You can call the  DescribeGatewayInformation API to check the status. For more information, see  ActivateGateway .

       

     

    If do not intend to use the gateway again, you must delete the gateway (using  DeleteGateway ) to no longer pay software charges associated with the gateway.

    

    **Request Syntax** 
    ::

      response = client.shutdown_gateway(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the of the gateway that was shut down.

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: start_gateway(**kwargs)

    

    Starts a gateway that you previously shut down (see  ShutdownGateway ). After the gateway starts, you can then make other API calls, your applications can read from or write to the gateway's storage volumes and you will be able to take snapshot backups.

     

    .. note::

      

      When you make a request, you will get a 200 OK success response immediately. However, it might take some time for the gateway to be ready. You should call  DescribeGatewayInformation and check the status before making any additional API calls. For more information, see  ActivateGateway .

       

     

    To specify which gateway to start, use the Amazon Resource Name (ARN) of the gateway in your request.

    

    **Request Syntax** 
    ::

      response = client.start_gateway(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the of the gateway that was restarted.

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: update_bandwidth_rate_limit(**kwargs)

    

    Updates the bandwidth rate limits of a gateway. You can update both the upload and download bandwidth rate limit or specify only one of the two. If you don't set a bandwidth rate limit, the existing rate limit remains.

     

    By default, a gateway's bandwidth rate limits are not set. If you don't set any limit, the gateway does not have any limitations on its bandwidth usage and could potentially use the maximum available bandwidth.

     

    To specify which gateway to update, use the Amazon Resource Name (ARN) of the gateway in your request.

    

    **Request Syntax** 
    ::

      response = client.update_bandwidth_rate_limit(
          GatewayARN='string',
          AverageUploadRateLimitInBitsPerSec=123,
          AverageDownloadRateLimitInBitsPerSec=123
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type AverageUploadRateLimitInBitsPerSec: integer
    :param AverageUploadRateLimitInBitsPerSec: 

      The average upload bandwidth rate limit in bits per second.

      

    
    :type AverageDownloadRateLimitInBitsPerSec: integer
    :param AverageDownloadRateLimitInBitsPerSec: 

      The average download bandwidth rate limit in bits per second.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the of the gateway whose throttle information was updated.

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: update_chap_credentials(**kwargs)

    

    Updates the Challenge-Handshake Authentication Protocol (CHAP) credentials for a specified iSCSI target. By default, a gateway does not have CHAP enabled; however, for added security, you might use it.

     

    .. warning::

       

      When you update CHAP credentials, all existing connections on the target are closed and initiators must reconnect with the new credentials.

       

    

    **Request Syntax** 
    ::

      response = client.update_chap_credentials(
          TargetARN='string',
          SecretToAuthenticateInitiator='string',
          InitiatorName='string',
          SecretToAuthenticateTarget='string'
      )
    :type TargetARN: string
    :param TargetARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the iSCSI volume target. Use the  DescribeStorediSCSIVolumes operation to return the TargetARN for specified VolumeARN.

      

    
    :type SecretToAuthenticateInitiator: string
    :param SecretToAuthenticateInitiator: **[REQUIRED]** 

      The secret key that the initiator (for example, the Windows client) must provide to participate in mutual CHAP with the target.

       

      .. note::

        

        The secret key must be between 12 and 16 bytes when encoded in UTF-8.

         

      

    
    :type InitiatorName: string
    :param InitiatorName: **[REQUIRED]** 

      The iSCSI initiator that connects to the target.

      

    
    :type SecretToAuthenticateTarget: string
    :param SecretToAuthenticateTarget: 

      The secret key that the target must provide to participate in mutual CHAP with the initiator (e.g. Windows client).

       

      Byte constraints: Minimum bytes of 12. Maximum bytes of 16.

       

      .. note::

        

        The secret key must be between 12 and 16 bytes when encoded in UTF-8.

         

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TargetARN': 'string',
            'InitiatorName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the following fields:

        
        

        - **TargetARN** *(string) --* 

          The Amazon Resource Name (ARN) of the target. This is the same target specified in the request.

          
        

        - **InitiatorName** *(string) --* 

          The iSCSI initiator that connects to the target. This is the same initiator name specified in the request.

          
    

  .. py:method:: update_gateway_information(**kwargs)

    

    Updates a gateway's metadata, which includes the gateway's name and time zone. To specify which gateway to update, use the Amazon Resource Name (ARN) of the gateway in your request.

     

    .. note::

      

      For Gateways activated after September 2, 2015, the gateway's ARN contains the gateway ID rather than the gateway name. However, changing the name of the gateway has no effect on the gateway's ARN.

       

    

    **Request Syntax** 
    ::

      response = client.update_gateway_information(
          GatewayARN='string',
          GatewayName='string',
          GatewayTimezone='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type GatewayName: string
    :param GatewayName: 

      The name you configured for your gateway.

      

    
    :type GatewayTimezone: string
    :param GatewayTimezone: 

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string',
            'GatewayName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the ARN of the gateway that was updated.

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **GatewayName** *(string) --* 
    

  .. py:method:: update_gateway_software_now(**kwargs)

    

    Updates the gateway virtual machine (VM) software. The request immediately triggers the software update.

     

    .. note::

      

      When you make this request, you get a ``200 OK`` success response immediately. However, it might take some time for the update to complete. You can call  DescribeGatewayInformation to verify the gateway is in the ``STATE_RUNNING`` state.

       

     

    .. warning::

      

      A software update forces a system restart of your gateway. You can minimize the chance of any disruption to your applications by increasing your iSCSI Initiators' timeouts. For more information about increasing iSCSI Initiator timeouts for Windows and Linux, see `Customizing Your Windows iSCSI Settings`_ and `Customizing Your Linux iSCSI Settings`_ , respectively.

       

    

    **Request Syntax** 
    ::

      response = client.update_gateway_software_now(
          GatewayARN='string'
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the of the gateway that was updated.

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: update_maintenance_start_time(**kwargs)

    

    Updates a gateway's weekly maintenance start time information, including day and time of the week. The maintenance time is the time in your gateway's time zone.

    

    **Request Syntax** 
    ::

      response = client.update_maintenance_start_time(
          GatewayARN='string',
          HourOfDay=123,
          MinuteOfHour=123,
          DayOfWeek=123
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type HourOfDay: integer
    :param HourOfDay: **[REQUIRED]** 

      The hour component of the maintenance start time represented as *hh* , where *hh* is the hour (00 to 23). The hour of the day is in the time zone of the gateway.

      

    
    :type MinuteOfHour: integer
    :param MinuteOfHour: **[REQUIRED]** 

      The minute component of the maintenance start time represented as *mm* , where *mm* is the minute (00 to 59). The minute of the hour is in the time zone of the gateway.

      

    
    :type DayOfWeek: integer
    :param DayOfWeek: **[REQUIRED]** 

      The maintenance start time day of the week.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GatewayARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the of the gateway whose maintenance start time is updated.

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
    

  .. py:method:: update_snapshot_schedule(**kwargs)

    

    Updates a snapshot schedule configured for a gateway volume.

     

    The default snapshot schedule for volume is once every 24 hours, starting at the creation time of the volume. You can use this API to change the snapshot schedule configured for the volume.

     

    In the request you must identify the gateway volume whose snapshot schedule you want to update, and the schedule information, including when you want the snapshot to begin on a day and the frequency (in hours) of snapshots.

    

    **Request Syntax** 
    ::

      response = client.update_snapshot_schedule(
          VolumeARN='string',
          StartAt=123,
          RecurrenceInHours=123,
          Description='string'
      )
    :type VolumeARN: string
    :param VolumeARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the volume. Use the  ListVolumes operation to return a list of gateway volumes.

      

    
    :type StartAt: integer
    :param StartAt: **[REQUIRED]** 

      The hour of the day at which the snapshot schedule begins represented as *hh* , where *hh* is the hour (0 to 23). The hour of the day is in the time zone of the gateway.

      

    
    :type RecurrenceInHours: integer
    :param RecurrenceInHours: **[REQUIRED]** 

      Frequency of snapshots. Specify the number of hours between snapshots.

      

    
    :type Description: string
    :param Description: 

      Optional description of the snapshot that overwrites the existing description.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VolumeARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A JSON object containing the of the updated storage volume.

        
        

        - **VolumeARN** *(string) --* 

          

          
    

  .. py:method:: update_vtl_device_type(**kwargs)

    

    Updates the type of medium changer in a gateway-VTL. When you activate a gateway-VTL, you select a medium changer type for the gateway-VTL. This operation enables you to select a different type of medium changer after a gateway-VTL is activated.

    

    **Request Syntax** 
    ::

      response = client.update_vtl_device_type(
          VTLDeviceARN='string',
          DeviceType='string'
      )
    :type VTLDeviceARN: string
    :param VTLDeviceARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the medium changer you want to select.

      

    
    :type DeviceType: string
    :param DeviceType: **[REQUIRED]** 

      The type of medium changer you want to select.

       

      Valid Values: "STK-L700", "AWS-Gateway-VTL"

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VTLDeviceARN': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        UpdateVTLDeviceTypeOutput

        
        

        - **VTLDeviceARN** *(string) --* 

          The Amazon Resource Name (ARN) of the medium changer you have selected.

          
    

==========
Paginators
==========


The available paginators are:

* :py:class:`StorageGateway.Paginator.DescribeTapeArchives`


* :py:class:`StorageGateway.Paginator.DescribeTapeRecoveryPoints`


* :py:class:`StorageGateway.Paginator.DescribeTapes`


* :py:class:`StorageGateway.Paginator.DescribeVTLDevices`


* :py:class:`StorageGateway.Paginator.ListGateways`


* :py:class:`StorageGateway.Paginator.ListVolumes`



.. py:class:: StorageGateway.Paginator.DescribeTapeArchives

  ::

    
    paginator = client.get_paginator('describe_tape_archives')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`StorageGateway.Client.describe_tape_archives`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          TapeARNs=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type TapeARNs: list
    :param TapeARNs: 

      Specifies one or more unique Amazon Resource Names (ARNs) that represent the virtual tapes you want to describe.

      

    
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
            'TapeArchives': [
                {
                    'TapeARN': 'string',
                    'TapeBarcode': 'string',
                    'TapeSizeInBytes': 123,
                    'CompletionTime': datetime(2015, 1, 1),
                    'RetrievedTo': 'string',
                    'TapeStatus': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DescribeTapeArchivesOutput

        
        

        - **TapeArchives** *(list) --* 

          An array of virtual tape objects in the virtual tape shelf (VTS). The description includes of the Amazon Resource Name(ARN) of the virtual tapes. The information returned includes the Amazon Resource Names (ARNs) of the tapes, size of the tapes, status of the tapes, progress of the description and tape barcode.

          
          

          - *(dict) --* 

            Represents a virtual tape that is archived in the virtual tape shelf (VTS).

            
            

            - **TapeARN** *(string) --* 

              The Amazon Resource Name (ARN) of an archived virtual tape.

              
            

            - **TapeBarcode** *(string) --* 

              The barcode that identifies the archived virtual tape.

              
            

            - **TapeSizeInBytes** *(integer) --* 

              The size, in bytes, of the archived virtual tape.

              
            

            - **CompletionTime** *(datetime) --* 

              The time that the archiving of the virtual tape was completed.

               

              The string format of the completion time is in the ISO8601 extended YYYY-MM-DD'T'HH:MM:SS'Z' format.

              
            

            - **RetrievedTo** *(string) --* 

              The Amazon Resource Name (ARN) of the gateway-VTL that the virtual tape is being retrieved to.

               

              The virtual tape is retrieved from the virtual tape shelf (VTS).

              
            

            - **TapeStatus** *(string) --* 

              The current state of the archived virtual tape.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: StorageGateway.Paginator.DescribeTapeRecoveryPoints

  ::

    
    paginator = client.get_paginator('describe_tape_recovery_points')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`StorageGateway.Client.describe_tape_recovery_points`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          GatewayARN='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
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
            'GatewayARN': 'string',
            'TapeRecoveryPointInfos': [
                {
                    'TapeARN': 'string',
                    'TapeRecoveryPointTime': datetime(2015, 1, 1),
                    'TapeSizeInBytes': 123,
                    'TapeStatus': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DescribeTapeRecoveryPointsOutput

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **TapeRecoveryPointInfos** *(list) --* 

          An array of TapeRecoveryPointInfos that are available for the specified gateway.

          
          

          - *(dict) --* 

            Describes a recovery point.

            
            

            - **TapeARN** *(string) --* 

              The Amazon Resource Name (ARN) of the virtual tape.

              
            

            - **TapeRecoveryPointTime** *(datetime) --* 

              The time when the point-in-time view of the virtual tape was replicated for later recovery.

               

              The string format of the tape recovery point time is in the ISO8601 extended YYYY-MM-DD'T'HH:MM:SS'Z' format.

              
            

            - **TapeSizeInBytes** *(integer) --* 

              The size, in bytes, of the virtual tapes to recover.

              
            

            - **TapeStatus** *(string) --* 
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: StorageGateway.Paginator.DescribeTapes

  ::

    
    paginator = client.get_paginator('describe_tapes')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`StorageGateway.Client.describe_tapes`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          GatewayARN='string',
          TapeARNs=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type TapeARNs: list
    :param TapeARNs: 

      Specifies one or more unique Amazon Resource Names (ARNs) that represent the virtual tapes you want to describe. If this parameter is not specified, AWS Storage Gateway returns a description of all virtual tapes associated with the specified gateway.

      

    
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
            'Tapes': [
                {
                    'TapeARN': 'string',
                    'TapeBarcode': 'string',
                    'TapeSizeInBytes': 123,
                    'TapeStatus': 'string',
                    'VTLDevice': 'string',
                    'Progress': 123.0
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DescribeTapesOutput

        
        

        - **Tapes** *(list) --* 

          An array of virtual tape descriptions.

          
          

          - *(dict) --* 

            Describes a virtual tape object.

            
            

            - **TapeARN** *(string) --* 

              The Amazon Resource Name (ARN) of the virtual tape.

              
            

            - **TapeBarcode** *(string) --* 

              The barcode that identifies a specific virtual tape.

              
            

            - **TapeSizeInBytes** *(integer) --* 

              The size, in bytes, of the virtual tape.

              
            

            - **TapeStatus** *(string) --* 

              The current state of the virtual tape.

              
            

            - **VTLDevice** *(string) --* 

              The virtual tape library (VTL) device that the virtual tape is associated with.

              
            

            - **Progress** *(float) --* 

              For archiving virtual tapes, indicates how much data remains to be uploaded before archiving is complete.

               

              Range: 0 (not started) to 100 (complete).

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: StorageGateway.Paginator.DescribeVTLDevices

  ::

    
    paginator = client.get_paginator('describe_vtl_devices')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`StorageGateway.Client.describe_vtl_devices`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          GatewayARN='string',
          VTLDeviceARNs=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type GatewayARN: string
    :param GatewayARN: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
    :type VTLDeviceARNs: list
    :param VTLDeviceARNs: 

      An array of strings, where each string represents the Amazon Resource Name (ARN) of a VTL device.

       

      .. note::

        

        All of the specified VTL devices must be from the same gateway. If no VTL devices are specified, the result will contain all devices on the specified gateway.

         

      

    
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
            'GatewayARN': 'string',
            'VTLDevices': [
                {
                    'VTLDeviceARN': 'string',
                    'VTLDeviceType': 'string',
                    'VTLDeviceVendor': 'string',
                    'VTLDeviceProductIdentifier': 'string',
                    'DeviceiSCSIAttributes': {
                        'TargetARN': 'string',
                        'NetworkInterfaceId': 'string',
                        'NetworkInterfacePort': 123,
                        'ChapEnabled': True|False
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        DescribeVTLDevicesOutput

        
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **VTLDevices** *(list) --* 

          An array of VTL device objects composed of the Amazon Resource Name(ARN) of the VTL devices.

          
          

          - *(dict) --* 

            Represents a device object associated with a gateway-VTL.

            
            

            - **VTLDeviceARN** *(string) --* 

              Specifies the unique Amazon Resource Name (ARN) of the device (tape drive or media changer).

              
            

            - **VTLDeviceType** *(string) --* 
            

            - **VTLDeviceVendor** *(string) --* 
            

            - **VTLDeviceProductIdentifier** *(string) --* 
            

            - **DeviceiSCSIAttributes** *(dict) --* 

              A list of iSCSI information about a VTL device.

              
              

              - **TargetARN** *(string) --* 

                Specifies the unique Amazon Resource Name(ARN) that encodes the iSCSI qualified name(iqn) of a tape drive or media changer target.

                
              

              - **NetworkInterfaceId** *(string) --* 

                The network interface identifier of the VTL device.

                
              

              - **NetworkInterfacePort** *(integer) --* 

                The port used to communicate with iSCSI VTL device targets.

                
              

              - **ChapEnabled** *(boolean) --* 

                Indicates whether mutual CHAP is enabled for the iSCSI target.

                
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: StorageGateway.Paginator.ListGateways

  ::

    
    paginator = client.get_paginator('list_gateways')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`StorageGateway.Client.list_gateways`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
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
            'Gateways': [
                {
                    'GatewayId': 'string',
                    'GatewayARN': 'string',
                    'GatewayType': 'string',
                    'GatewayOperationalState': 'string',
                    'GatewayName': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Gateways** *(list) --* 
          

          - *(dict) --* 

            Describes a gateway object.

            
            

            - **GatewayId** *(string) --* 

              The unique identifier assigned to your gateway during activation. This ID becomes part of the gateway Amazon Resource Name (ARN), which you use as input for other operations.

              
            

            - **GatewayARN** *(string) --* 

              The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

              
            

            - **GatewayType** *(string) --* 

              The type of the gateway.

              
            

            - **GatewayOperationalState** *(string) --* 

              The state of the gateway.

               

              Valid Values: DISABLED or ACTIVE

              
            

            - **GatewayName** *(string) --* 

              The name of the gateway.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: StorageGateway.Paginator.ListVolumes

  ::

    
    paginator = client.get_paginator('list_volumes')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`StorageGateway.Client.list_volumes`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          GatewayARN='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type GatewayARN: string
    :param GatewayARN: 

      The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

      

    
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
            'GatewayARN': 'string',
            'VolumeInfos': [
                {
                    'VolumeARN': 'string',
                    'VolumeId': 'string',
                    'GatewayARN': 'string',
                    'GatewayId': 'string',
                    'VolumeType': 'string',
                    'VolumeSizeInBytes': 123
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GatewayARN** *(string) --* 

          The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

          
        

        - **VolumeInfos** *(list) --* 
          

          - *(dict) --* 

            Describes a storage volume object.

            
            

            - **VolumeARN** *(string) --* 

              The Amazon Resource Name (ARN) for the storage volume. For example, the following is a valid ARN:

               

               ``arn:aws:storagegateway:us-east-1:111122223333:gateway/sgw-12A3456B/volume/vol-1122AABB``  

               

              Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

              
            

            - **VolumeId** *(string) --* 

              The unique identifier assigned to the volume. This ID becomes part of the volume Amazon Resource Name (ARN), which you use as input for other operations.

               

              Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

              
            

            - **GatewayARN** *(string) --* 

              The Amazon Resource Name (ARN) of the gateway. Use the  ListGateways operation to return a list of gateways for your account and region.

              
            

            - **GatewayId** *(string) --* 

              The unique identifier assigned to your gateway during activation. This ID becomes part of the gateway Amazon Resource Name (ARN), which you use as input for other operations.

               

              Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

              
            

            - **VolumeType** *(string) --* 
            

            - **VolumeSizeInBytes** *(integer) --* 

              The size, in bytes, of the volume.

               

              Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    