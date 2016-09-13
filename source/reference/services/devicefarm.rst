

.. _aws-devicefarm-support@amazon.com: mailto:aws-devicefarm-support@amazon.com
.. _AWS Device Farm terminology: http://docs.aws.amazon.com/devicefarm/latest/developerguide/welcome.html#welcome-terminology


**********
DeviceFarm
**********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: DeviceFarm.Client

  A low-level client representing AWS Device Farm::

    
    import boto3
    
    client = boto3.client('devicefarm')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_device_pool`

  
  *   :py:meth:`create_project`

  
  *   :py:meth:`create_remote_access_session`

  
  *   :py:meth:`create_upload`

  
  *   :py:meth:`delete_device_pool`

  
  *   :py:meth:`delete_project`

  
  *   :py:meth:`delete_remote_access_session`

  
  *   :py:meth:`delete_run`

  
  *   :py:meth:`delete_upload`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_account_settings`

  
  *   :py:meth:`get_device`

  
  *   :py:meth:`get_device_pool`

  
  *   :py:meth:`get_device_pool_compatibility`

  
  *   :py:meth:`get_job`

  
  *   :py:meth:`get_offering_status`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_project`

  
  *   :py:meth:`get_remote_access_session`

  
  *   :py:meth:`get_run`

  
  *   :py:meth:`get_suite`

  
  *   :py:meth:`get_test`

  
  *   :py:meth:`get_upload`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`install_to_remote_access_session`

  
  *   :py:meth:`list_artifacts`

  
  *   :py:meth:`list_device_pools`

  
  *   :py:meth:`list_devices`

  
  *   :py:meth:`list_jobs`

  
  *   :py:meth:`list_offering_transactions`

  
  *   :py:meth:`list_offerings`

  
  *   :py:meth:`list_projects`

  
  *   :py:meth:`list_remote_access_sessions`

  
  *   :py:meth:`list_runs`

  
  *   :py:meth:`list_samples`

  
  *   :py:meth:`list_suites`

  
  *   :py:meth:`list_tests`

  
  *   :py:meth:`list_unique_problems`

  
  *   :py:meth:`list_uploads`

  
  *   :py:meth:`purchase_offering`

  
  *   :py:meth:`renew_offering`

  
  *   :py:meth:`schedule_run`

  
  *   :py:meth:`stop_remote_access_session`

  
  *   :py:meth:`stop_run`

  
  *   :py:meth:`update_device_pool`

  
  *   :py:meth:`update_project`

  

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


  .. py:method:: create_device_pool(**kwargs)

    

    Creates a device pool.

    

    **Request Syntax** 
    ::

      response = client.create_device_pool(
          projectArn='string',
          name='string',
          description='string',
          rules=[
              {
                  'attribute': 'ARN'|'PLATFORM'|'FORM_FACTOR'|'MANUFACTURER'|'REMOTE_ACCESS_ENABLED',
                  'operator': 'EQUALS'|'LESS_THAN'|'GREATER_THAN'|'IN'|'NOT_IN',
                  'value': 'string'
              },
          ]
      )
    :type projectArn: string
    :param projectArn: **[REQUIRED]** 

      The ARN of the project for the device pool.

      

    
    :type name: string
    :param name: **[REQUIRED]** 

      The device pool's name.

      

    
    :type description: string
    :param description: 

      The device pool's description.

      

    
    :type rules: list
    :param rules: **[REQUIRED]** 

      The device pool's rules.

      

    
      - *(dict) --* 

        Represents a condition for a device pool.

        

      
        - **attribute** *(string) --* 

          The rule's stringified attribute. For example, specify the value as ``"\"abc\""`` .

           

          Allowed values include:

           

           
          * ARN: The ARN.
           
          * FORM_FACTOR: The form factor (for example, phone or tablet).
           
          * MANUFACTURER: The manufacturer.
           
          * PLATFORM: The platform (for example, Android or iOS).
           

          

        
        - **operator** *(string) --* 

          The rule's operator.

           

           
          * EQUALS: The equals operator.
           
          * GREATER_THAN: The greater-than operator.
           
          * IN: The in operator.
           
          * LESS_THAN: The less-than operator.
           
          * NOT_IN: The not-in operator.
           

          

        
        - **value** *(string) --* 

          The rule's value.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'devicePool': {
                'arn': 'string',
                'name': 'string',
                'description': 'string',
                'type': 'CURATED'|'PRIVATE',
                'rules': [
                    {
                        'attribute': 'ARN'|'PLATFORM'|'FORM_FACTOR'|'MANUFACTURER'|'REMOTE_ACCESS_ENABLED',
                        'operator': 'EQUALS'|'LESS_THAN'|'GREATER_THAN'|'IN'|'NOT_IN',
                        'value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a create device pool request.

        
        

        - **devicePool** *(dict) --* 

          The newly created device pool.

          
          

          - **arn** *(string) --* 

            The device pool's ARN.

            
          

          - **name** *(string) --* 

            The device pool's name.

            
          

          - **description** *(string) --* 

            The device pool's description.

            
          

          - **type** *(string) --* 

            The device pool's type.

             

            Allowed values include:

             

             
            * CURATED: A device pool that is created and managed by AWS Device Farm.
             
            * PRIVATE: A device pool that is created and managed by the device pool developer.
             

            
          

          - **rules** *(list) --* 

            Information about the device pool's rules.

            
            

            - *(dict) --* 

              Represents a condition for a device pool.

              
              

              - **attribute** *(string) --* 

                The rule's stringified attribute. For example, specify the value as ``"\"abc\""`` .

                 

                Allowed values include:

                 

                 
                * ARN: The ARN.
                 
                * FORM_FACTOR: The form factor (for example, phone or tablet).
                 
                * MANUFACTURER: The manufacturer.
                 
                * PLATFORM: The platform (for example, Android or iOS).
                 

                
              

              - **operator** *(string) --* 

                The rule's operator.

                 

                 
                * EQUALS: The equals operator.
                 
                * GREATER_THAN: The greater-than operator.
                 
                * IN: The in operator.
                 
                * LESS_THAN: The less-than operator.
                 
                * NOT_IN: The not-in operator.
                 

                
              

              - **value** *(string) --* 

                The rule's value.

                
          
        
      
    

  .. py:method:: create_project(**kwargs)

    

    Creates a new project.

    

    **Request Syntax** 
    ::

      response = client.create_project(
          name='string'
      )
    :type name: string
    :param name: **[REQUIRED]** 

      The project's name.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'project': {
                'arn': 'string',
                'name': 'string',
                'created': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a create project request.

        
        

        - **project** *(dict) --* 

          The newly created project.

          
          

          - **arn** *(string) --* 

            The project's ARN.

            
          

          - **name** *(string) --* 

            The project's name.

            
          

          - **created** *(datetime) --* 

            When the project was created.

            
      
    

  .. py:method:: create_remote_access_session(**kwargs)

    

    Specifies and starts a remote access session.

    

    **Request Syntax** 
    ::

      response = client.create_remote_access_session(
          projectArn='string',
          deviceArn='string',
          name='string',
          configuration={
              'billingMethod': 'METERED'|'UNMETERED'
          }
      )
    :type projectArn: string
    :param projectArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the project for which you want to create a remote access session.

      

    
    :type deviceArn: string
    :param deviceArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the device for which you want to create a remote access session.

      

    
    :type name: string
    :param name: 

      The name of the remote access session that you wish to create.

      

    
    :type configuration: dict
    :param configuration: 

      The configuration information for the remote access session request.

      

    
      - **billingMethod** *(string) --* 

        Returns the billing method for purposes of configuring a remote access session.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'remoteAccessSession': {
                'arn': 'string',
                'name': 'string',
                'created': datetime(2015, 1, 1),
                'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                'message': 'string',
                'started': datetime(2015, 1, 1),
                'stopped': datetime(2015, 1, 1),
                'device': {
                    'arn': 'string',
                    'name': 'string',
                    'manufacturer': 'string',
                    'model': 'string',
                    'formFactor': 'PHONE'|'TABLET',
                    'platform': 'ANDROID'|'IOS',
                    'os': 'string',
                    'cpu': {
                        'frequency': 'string',
                        'architecture': 'string',
                        'clock': 123.0
                    },
                    'resolution': {
                        'width': 123,
                        'height': 123
                    },
                    'heapSize': 123,
                    'memory': 123,
                    'image': 'string',
                    'carrier': 'string',
                    'radio': 'string',
                    'remoteAccessEnabled': True|False,
                    'fleetType': 'string',
                    'fleetName': 'string'
                },
                'billingMethod': 'METERED'|'UNMETERED',
                'deviceMinutes': {
                    'total': 123.0,
                    'metered': 123.0,
                    'unmetered': 123.0
                },
                'endpoint': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the server response from a request to create a remote access session.

        
        

        - **remoteAccessSession** *(dict) --* 

          A container that describes the remote access session when the request to create a remote access session is sent.

          
          

          - **arn** *(string) --* 

            The Amazon Resource Name (ARN) of the remote access session.

            
          

          - **name** *(string) --* 

            The name of the remote access session.

            
          

          - **created** *(datetime) --* 

            The date and time the remote access session was created.

            
          

          - **status** *(string) --* 

            The status of the remote access session. Can be any of the following:

             

             
            * PENDING: A pending status.
             
            * PENDING_CONCURRENCY: A pending concurrency status.
             
            * PENDING_DEVICE: A pending device status.
             
            * PROCESSING: A processing status.
             
            * SCHEDULING: A scheduling status.
             
            * PREPARING: A preparing status.
             
            * RUNNING: A running status.
             
            * COMPLETED: A completed status.
             
            * STOPPING: A stopping status.
             

            
          

          - **result** *(string) --* 

            The result of the remote access session. Can be any of the following:

             

             
            * PENDING: A pending condition.
             
            * PASSED: A passing condition.
             
            * WARNED: A warning condition.
             
            * FAILED: A failed condition.
             
            * SKIPPED: A skipped condition.
             
            * ERRORED: An error condition.
             
            * STOPPED: A stopped condition.
             

            
          

          - **message** *(string) --* 

            A message about the remote access session.

            
          

          - **started** *(datetime) --* 

            The date and time the remote access session was started.

            
          

          - **stopped** *(datetime) --* 

            The date and time the remote access session was stopped.

            
          

          - **device** *(dict) --* 

            Represents a device type that an app is tested against.

            
            

            - **arn** *(string) --* 

              The device's ARN.

              
            

            - **name** *(string) --* 

              The device's display name.

              
            

            - **manufacturer** *(string) --* 

              The device's manufacturer name.

              
            

            - **model** *(string) --* 

              The device's model name.

              
            

            - **formFactor** *(string) --* 

              The device's form factor.

               

              Allowed values include:

               

               
              * PHONE: The phone form factor.
               
              * TABLET: The tablet form factor.
               

              
            

            - **platform** *(string) --* 

              The device's platform.

               

              Allowed values include:

               

               
              * ANDROID: The Android platform.
               
              * IOS: The iOS platform.
               

              
            

            - **os** *(string) --* 

              The device's operating system type.

              
            

            - **cpu** *(dict) --* 

              Information about the device's CPU.

              
              

              - **frequency** *(string) --* 

                The CPU's frequency.

                
              

              - **architecture** *(string) --* 

                The CPU's architecture, for example x86 or ARM.

                
              

              - **clock** *(float) --* 

                The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                
          
            

            - **resolution** *(dict) --* 

              Represents the screen resolution of a device in height and width, expressed in pixels.

              
              

              - **width** *(integer) --* 

                The screen resolution's width, expressed in pixels.

                
              

              - **height** *(integer) --* 

                The screen resolution's height, expressed in pixels.

                
          
            

            - **heapSize** *(integer) --* 

              The device's heap size, expressed in bytes.

              
            

            - **memory** *(integer) --* 

              The device's total memory size, expressed in bytes.

              
            

            - **image** *(string) --* 

              The device's image name.

              
            

            - **carrier** *(string) --* 

              The device's carrier.

              
            

            - **radio** *(string) --* 

              The device's radio.

              
            

            - **remoteAccessEnabled** *(boolean) --* 

              Specifies whether remote access has been enabled for the specified device.

              
            

            - **fleetType** *(string) --* 

              The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

              
            

            - **fleetName** *(string) --* 

              The name of the fleet to which this device belongs.

              
        
          

          - **billingMethod** *(string) --* 

            The billing method of the remote access session. Possible values include ``METERED`` or ``UNMETERED`` . For more information about metered devices, see `AWS Device Farm terminology`_ ."

            
          

          - **deviceMinutes** *(dict) --* 

            Represents the total (metered or unmetered) minutes used by the resource to run tests. Contains the sum of minutes consumed by all children.

            
            

            - **total** *(float) --* 

              When specified, represents the total minutes used by the resource to run tests.

              
            

            - **metered** *(float) --* 

              When specified, represents only the sum of metered minutes used by the resource to run tests.

              
            

            - **unmetered** *(float) --* 

              When specified, represents only the sum of unmetered minutes used by the resource to run tests.

              
        
          

          - **endpoint** *(string) --* 

            The endpoint for the remote access sesssion.

            
      
    

  .. py:method:: create_upload(**kwargs)

    

    Uploads an app or test scripts.

    

    **Request Syntax** 
    ::

      response = client.create_upload(
          projectArn='string',
          name='string',
          type='ANDROID_APP'|'IOS_APP'|'WEB_APP'|'EXTERNAL_DATA'|'APPIUM_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_PYTHON_TEST_PACKAGE'|'APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_WEB_PYTHON_TEST_PACKAGE'|'CALABASH_TEST_PACKAGE'|'INSTRUMENTATION_TEST_PACKAGE'|'UIAUTOMATION_TEST_PACKAGE'|'UIAUTOMATOR_TEST_PACKAGE'|'XCTEST_TEST_PACKAGE'|'XCTEST_UI_TEST_PACKAGE',
          contentType='string'
      )
    :type projectArn: string
    :param projectArn: **[REQUIRED]** 

      The ARN of the project for the upload.

      

    
    :type name: string
    :param name: **[REQUIRED]** 

      The upload's file name. The name should not contain the '/' character.

      

    
    :type type: string
    :param type: **[REQUIRED]** 

      The upload's upload type.

       

      Must be one of the following values:

       

       
      * ANDROID_APP: An Android upload.
       
      * IOS_APP: An iOS upload.
       
      * WEB_APP: A web appliction upload.
       
      * EXTERNAL_DATA: An external data upload.
       
      * APPIUM_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
       
      * APPIUM_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
       
      * APPIUM_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
       
      * APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
       
      * APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
       
      * APPIUM_WEB_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
       
      * CALABASH_TEST_PACKAGE: A Calabash test package upload.
       
      * INSTRUMENTATION_TEST_PACKAGE: An instrumentation upload.
       
      * UIAUTOMATION_TEST_PACKAGE: A uiautomation test package upload.
       
      * UIAUTOMATOR_TEST_PACKAGE: A uiautomator test package upload.
       
      * XCTEST_TEST_PACKAGE: An XCode test package upload.
       
      * XCTEST_UI_TEST_PACKAGE: An XCode UI test package upload.
       

       

      **Note** If you call ``CreateUpload`` with ``WEB_APP`` specified, AWS Device Farm throws an ``ArgumentException`` error.

      

    
    :type contentType: string
    :param contentType: 

      The upload's content type (for example, "application/octet-stream").

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'upload': {
                'arn': 'string',
                'name': 'string',
                'created': datetime(2015, 1, 1),
                'type': 'ANDROID_APP'|'IOS_APP'|'WEB_APP'|'EXTERNAL_DATA'|'APPIUM_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_PYTHON_TEST_PACKAGE'|'APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_WEB_PYTHON_TEST_PACKAGE'|'CALABASH_TEST_PACKAGE'|'INSTRUMENTATION_TEST_PACKAGE'|'UIAUTOMATION_TEST_PACKAGE'|'UIAUTOMATOR_TEST_PACKAGE'|'XCTEST_TEST_PACKAGE'|'XCTEST_UI_TEST_PACKAGE',
                'status': 'INITIALIZED'|'PROCESSING'|'SUCCEEDED'|'FAILED',
                'url': 'string',
                'metadata': 'string',
                'contentType': 'string',
                'message': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a create upload request.

        
        

        - **upload** *(dict) --* 

          The newly created upload.

          
          

          - **arn** *(string) --* 

            The upload's ARN.

            
          

          - **name** *(string) --* 

            The upload's file name.

            
          

          - **created** *(datetime) --* 

            When the upload was created.

            
          

          - **type** *(string) --* 

            The upload's type.

             

            Must be one of the following values:

             

             
            * ANDROID_APP: An Android upload.
             
            * IOS_APP: An iOS upload.
             
            * WEB_APP: A web appliction upload.
             
            * EXTERNAL_DATA: An external data upload.
             
            * APPIUM_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
             
            * APPIUM_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
             
            * APPIUM_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
             
            * APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
             
            * APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
             
            * APPIUM_WEB_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
             
            * CALABASH_TEST_PACKAGE: A Calabash test package upload.
             
            * INSTRUMENTATION_TEST_PACKAGE: An instrumentation upload.
             
            * UIAUTOMATION_TEST_PACKAGE: A uiautomation test package upload.
             
            * UIAUTOMATOR_TEST_PACKAGE: A uiautomator test package upload.
             
            * XCTEST_TEST_PACKAGE: An XCode test package upload.
             
            * XCTEST_UI_TEST_PACKAGE: An XCode UI test package upload.
             

            
          

          - **status** *(string) --* 

            The upload's status.

             

            Must be one of the following values:

             

             
            * FAILED: A failed status.
             
            * INITIALIZED: An initialized status.
             
            * PROCESSING: A processing status.
             
            * SUCCEEDED: A succeeded status.
             

            
          

          - **url** *(string) --* 

            The pre-signed Amazon S3 URL that was used to store a file through a corresponding PUT request.

            
          

          - **metadata** *(string) --* 

            The upload's metadata. For example, for Android, this contains information that is parsed from the manifest and is displayed in the AWS Device Farm console after the associated app is uploaded.

            
          

          - **contentType** *(string) --* 

            The upload's content type (for example, "application/octet-stream").

            
          

          - **message** *(string) --* 

            A message about the upload's result.

            
      
    

  .. py:method:: delete_device_pool(**kwargs)

    

    Deletes a device pool given the pool ARN. Does not allow deletion of curated pools owned by the system.

    

    **Request Syntax** 
    ::

      response = client.delete_device_pool(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      Represents the Amazon Resource Name (ARN) of the Device Farm device pool you wish to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a delete device pool request.

        
    

  .. py:method:: delete_project(**kwargs)

    

    Deletes an AWS Device Farm project, given the project ARN.

     

    **Note** Deleting this resource does not stop an in-progress run.

    

    **Request Syntax** 
    ::

      response = client.delete_project(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      Represents the Amazon Resource Name (ARN) of the Device Farm project you wish to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a delete project request.

        
    

  .. py:method:: delete_remote_access_session(**kwargs)

    

    Deletes a completed remote access session and its results.

    

    **Request Syntax** 
    ::

      response = client.delete_remote_access_session(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the sesssion for which you want to delete remote access.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The response from the server when a request is made to delete the remote access session.

        
    

  .. py:method:: delete_run(**kwargs)

    

    Deletes the run, given the run ARN.

     

    **Note** Deleting this resource does not stop an in-progress run.

    

    **Request Syntax** 
    ::

      response = client.delete_run(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) for the run you wish to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a delete run request.

        
    

  .. py:method:: delete_upload(**kwargs)

    

    Deletes an upload given the upload ARN.

    

    **Request Syntax** 
    ::

      response = client.delete_upload(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      Represents the Amazon Resource Name (ARN) of the Device Farm upload you wish to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a delete upload request.

        
    

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


  .. py:method:: get_account_settings()

    

    Returns the number of unmetered iOS and/or unmetered Android devices that have been purchased by the account.

    

    **Request Syntax** 
    ::

      response = client.get_account_settings()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'accountSettings': {
                'awsAccountNumber': 'string',
                'unmeteredDevices': {
                    'string': 123
                },
                'unmeteredRemoteAccessDevices': {
                    'string': 123
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the account settings return values from the ``GetAccountSettings`` request.

        
        

        - **accountSettings** *(dict) --* 

          A container for account-level settings within AWS Device Farm.

          
          

          - **awsAccountNumber** *(string) --* 

            The AWS account number specified in the ``AccountSettings`` container.

            
          

          - **unmeteredDevices** *(dict) --* 

            Returns the unmetered devices you have purchased or want to purchase.

            
            

            - *(string) --* 
              

              - *(integer) --* 
        
      
          

          - **unmeteredRemoteAccessDevices** *(dict) --* 

            Returns the unmetered remote access devices you have purchased or want to purchase.

            
            

            - *(string) --* 
              

              - *(integer) --* 
        
      
      
    

  .. py:method:: get_device(**kwargs)

    

    Gets information about a unique device type.

    

    **Request Syntax** 
    ::

      response = client.get_device(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The device type's ARN.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'device': {
                'arn': 'string',
                'name': 'string',
                'manufacturer': 'string',
                'model': 'string',
                'formFactor': 'PHONE'|'TABLET',
                'platform': 'ANDROID'|'IOS',
                'os': 'string',
                'cpu': {
                    'frequency': 'string',
                    'architecture': 'string',
                    'clock': 123.0
                },
                'resolution': {
                    'width': 123,
                    'height': 123
                },
                'heapSize': 123,
                'memory': 123,
                'image': 'string',
                'carrier': 'string',
                'radio': 'string',
                'remoteAccessEnabled': True|False,
                'fleetType': 'string',
                'fleetName': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a get device request.

        
        

        - **device** *(dict) --* 

          Represents a device type that an app is tested against.

          
          

          - **arn** *(string) --* 

            The device's ARN.

            
          

          - **name** *(string) --* 

            The device's display name.

            
          

          - **manufacturer** *(string) --* 

            The device's manufacturer name.

            
          

          - **model** *(string) --* 

            The device's model name.

            
          

          - **formFactor** *(string) --* 

            The device's form factor.

             

            Allowed values include:

             

             
            * PHONE: The phone form factor.
             
            * TABLET: The tablet form factor.
             

            
          

          - **platform** *(string) --* 

            The device's platform.

             

            Allowed values include:

             

             
            * ANDROID: The Android platform.
             
            * IOS: The iOS platform.
             

            
          

          - **os** *(string) --* 

            The device's operating system type.

            
          

          - **cpu** *(dict) --* 

            Information about the device's CPU.

            
            

            - **frequency** *(string) --* 

              The CPU's frequency.

              
            

            - **architecture** *(string) --* 

              The CPU's architecture, for example x86 or ARM.

              
            

            - **clock** *(float) --* 

              The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

              
        
          

          - **resolution** *(dict) --* 

            Represents the screen resolution of a device in height and width, expressed in pixels.

            
            

            - **width** *(integer) --* 

              The screen resolution's width, expressed in pixels.

              
            

            - **height** *(integer) --* 

              The screen resolution's height, expressed in pixels.

              
        
          

          - **heapSize** *(integer) --* 

            The device's heap size, expressed in bytes.

            
          

          - **memory** *(integer) --* 

            The device's total memory size, expressed in bytes.

            
          

          - **image** *(string) --* 

            The device's image name.

            
          

          - **carrier** *(string) --* 

            The device's carrier.

            
          

          - **radio** *(string) --* 

            The device's radio.

            
          

          - **remoteAccessEnabled** *(boolean) --* 

            Specifies whether remote access has been enabled for the specified device.

            
          

          - **fleetType** *(string) --* 

            The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

            
          

          - **fleetName** *(string) --* 

            The name of the fleet to which this device belongs.

            
      
    

  .. py:method:: get_device_pool(**kwargs)

    

    Gets information about a device pool.

    

    **Request Syntax** 
    ::

      response = client.get_device_pool(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The device pool's ARN.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'devicePool': {
                'arn': 'string',
                'name': 'string',
                'description': 'string',
                'type': 'CURATED'|'PRIVATE',
                'rules': [
                    {
                        'attribute': 'ARN'|'PLATFORM'|'FORM_FACTOR'|'MANUFACTURER'|'REMOTE_ACCESS_ENABLED',
                        'operator': 'EQUALS'|'LESS_THAN'|'GREATER_THAN'|'IN'|'NOT_IN',
                        'value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a get device pool request.

        
        

        - **devicePool** *(dict) --* 

          Represents a collection of device types.

          
          

          - **arn** *(string) --* 

            The device pool's ARN.

            
          

          - **name** *(string) --* 

            The device pool's name.

            
          

          - **description** *(string) --* 

            The device pool's description.

            
          

          - **type** *(string) --* 

            The device pool's type.

             

            Allowed values include:

             

             
            * CURATED: A device pool that is created and managed by AWS Device Farm.
             
            * PRIVATE: A device pool that is created and managed by the device pool developer.
             

            
          

          - **rules** *(list) --* 

            Information about the device pool's rules.

            
            

            - *(dict) --* 

              Represents a condition for a device pool.

              
              

              - **attribute** *(string) --* 

                The rule's stringified attribute. For example, specify the value as ``"\"abc\""`` .

                 

                Allowed values include:

                 

                 
                * ARN: The ARN.
                 
                * FORM_FACTOR: The form factor (for example, phone or tablet).
                 
                * MANUFACTURER: The manufacturer.
                 
                * PLATFORM: The platform (for example, Android or iOS).
                 

                
              

              - **operator** *(string) --* 

                The rule's operator.

                 

                 
                * EQUALS: The equals operator.
                 
                * GREATER_THAN: The greater-than operator.
                 
                * IN: The in operator.
                 
                * LESS_THAN: The less-than operator.
                 
                * NOT_IN: The not-in operator.
                 

                
              

              - **value** *(string) --* 

                The rule's value.

                
          
        
      
    

  .. py:method:: get_device_pool_compatibility(**kwargs)

    

    Gets information about compatibility with a device pool.

    

    **Request Syntax** 
    ::

      response = client.get_device_pool_compatibility(
          devicePoolArn='string',
          appArn='string',
          testType='BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI'
      )
    :type devicePoolArn: string
    :param devicePoolArn: **[REQUIRED]** 

      The device pool's ARN.

      

    
    :type appArn: string
    :param appArn: 

      The ARN of the app that is associated with the specified device pool.

      

    
    :type testType: string
    :param testType: 

      The test type for the specified device pool.

       

      Allowed values include the following:

       

       
      * BUILTIN_FUZZ: The built-in fuzz type.
       
      * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
       
      * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
       
      * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
       
      * APPIUM_PYTHON: The Appium Python type.
       
      * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
       
      * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
       
      * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
       
      * CALABASH: The Calabash type.
       
      * INSTRUMENTATION: The Instrumentation type.
       
      * UIAUTOMATION: The uiautomation type.
       
      * UIAUTOMATOR: The uiautomator type.
       
      * XCTEST: The XCode test type.
       
      * XCTEST_UI: The XCode UI test type.
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'compatibleDevices': [
                {
                    'device': {
                        'arn': 'string',
                        'name': 'string',
                        'manufacturer': 'string',
                        'model': 'string',
                        'formFactor': 'PHONE'|'TABLET',
                        'platform': 'ANDROID'|'IOS',
                        'os': 'string',
                        'cpu': {
                            'frequency': 'string',
                            'architecture': 'string',
                            'clock': 123.0
                        },
                        'resolution': {
                            'width': 123,
                            'height': 123
                        },
                        'heapSize': 123,
                        'memory': 123,
                        'image': 'string',
                        'carrier': 'string',
                        'radio': 'string',
                        'remoteAccessEnabled': True|False,
                        'fleetType': 'string',
                        'fleetName': 'string'
                    },
                    'compatible': True|False,
                    'incompatibilityMessages': [
                        {
                            'message': 'string',
                            'type': 'ARN'|'PLATFORM'|'FORM_FACTOR'|'MANUFACTURER'|'REMOTE_ACCESS_ENABLED'
                        },
                    ]
                },
            ],
            'incompatibleDevices': [
                {
                    'device': {
                        'arn': 'string',
                        'name': 'string',
                        'manufacturer': 'string',
                        'model': 'string',
                        'formFactor': 'PHONE'|'TABLET',
                        'platform': 'ANDROID'|'IOS',
                        'os': 'string',
                        'cpu': {
                            'frequency': 'string',
                            'architecture': 'string',
                            'clock': 123.0
                        },
                        'resolution': {
                            'width': 123,
                            'height': 123
                        },
                        'heapSize': 123,
                        'memory': 123,
                        'image': 'string',
                        'carrier': 'string',
                        'radio': 'string',
                        'remoteAccessEnabled': True|False,
                        'fleetType': 'string',
                        'fleetName': 'string'
                    },
                    'compatible': True|False,
                    'incompatibilityMessages': [
                        {
                            'message': 'string',
                            'type': 'ARN'|'PLATFORM'|'FORM_FACTOR'|'MANUFACTURER'|'REMOTE_ACCESS_ENABLED'
                        },
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of describe device pool compatibility request.

        
        

        - **compatibleDevices** *(list) --* 

          Information about compatible devices.

          
          

          - *(dict) --* 

            Represents a device pool compatibility result.

            
            

            - **device** *(dict) --* 

              Represents a device type that an app is tested against.

              
              

              - **arn** *(string) --* 

                The device's ARN.

                
              

              - **name** *(string) --* 

                The device's display name.

                
              

              - **manufacturer** *(string) --* 

                The device's manufacturer name.

                
              

              - **model** *(string) --* 

                The device's model name.

                
              

              - **formFactor** *(string) --* 

                The device's form factor.

                 

                Allowed values include:

                 

                 
                * PHONE: The phone form factor.
                 
                * TABLET: The tablet form factor.
                 

                
              

              - **platform** *(string) --* 

                The device's platform.

                 

                Allowed values include:

                 

                 
                * ANDROID: The Android platform.
                 
                * IOS: The iOS platform.
                 

                
              

              - **os** *(string) --* 

                The device's operating system type.

                
              

              - **cpu** *(dict) --* 

                Information about the device's CPU.

                
                

                - **frequency** *(string) --* 

                  The CPU's frequency.

                  
                

                - **architecture** *(string) --* 

                  The CPU's architecture, for example x86 or ARM.

                  
                

                - **clock** *(float) --* 

                  The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                  
            
              

              - **resolution** *(dict) --* 

                Represents the screen resolution of a device in height and width, expressed in pixels.

                
                

                - **width** *(integer) --* 

                  The screen resolution's width, expressed in pixels.

                  
                

                - **height** *(integer) --* 

                  The screen resolution's height, expressed in pixels.

                  
            
              

              - **heapSize** *(integer) --* 

                The device's heap size, expressed in bytes.

                
              

              - **memory** *(integer) --* 

                The device's total memory size, expressed in bytes.

                
              

              - **image** *(string) --* 

                The device's image name.

                
              

              - **carrier** *(string) --* 

                The device's carrier.

                
              

              - **radio** *(string) --* 

                The device's radio.

                
              

              - **remoteAccessEnabled** *(boolean) --* 

                Specifies whether remote access has been enabled for the specified device.

                
              

              - **fleetType** *(string) --* 

                The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

                
              

              - **fleetName** *(string) --* 

                The name of the fleet to which this device belongs.

                
          
            

            - **compatible** *(boolean) --* 

              Whether the result was compatible with the device pool.

              
            

            - **incompatibilityMessages** *(list) --* 

              Information about the compatibility.

              
              

              - *(dict) --* 

                Represents information about incompatibility.

                
                

                - **message** *(string) --* 

                  A message about the incompatibility.

                  
                

                - **type** *(string) --* 

                  The type of incompatibility.

                   

                  Allowed values include:

                   

                   
                  * ARN: The ARN.
                   
                  * FORM_FACTOR: The form factor (for example, phone or tablet).
                   
                  * MANUFACTURER: The manufacturer.
                   
                  * PLATFORM: The platform (for example, Android or iOS).
                   

                  
            
          
        
      
        

        - **incompatibleDevices** *(list) --* 

          Information about incompatible devices.

          
          

          - *(dict) --* 

            Represents a device pool compatibility result.

            
            

            - **device** *(dict) --* 

              Represents a device type that an app is tested against.

              
              

              - **arn** *(string) --* 

                The device's ARN.

                
              

              - **name** *(string) --* 

                The device's display name.

                
              

              - **manufacturer** *(string) --* 

                The device's manufacturer name.

                
              

              - **model** *(string) --* 

                The device's model name.

                
              

              - **formFactor** *(string) --* 

                The device's form factor.

                 

                Allowed values include:

                 

                 
                * PHONE: The phone form factor.
                 
                * TABLET: The tablet form factor.
                 

                
              

              - **platform** *(string) --* 

                The device's platform.

                 

                Allowed values include:

                 

                 
                * ANDROID: The Android platform.
                 
                * IOS: The iOS platform.
                 

                
              

              - **os** *(string) --* 

                The device's operating system type.

                
              

              - **cpu** *(dict) --* 

                Information about the device's CPU.

                
                

                - **frequency** *(string) --* 

                  The CPU's frequency.

                  
                

                - **architecture** *(string) --* 

                  The CPU's architecture, for example x86 or ARM.

                  
                

                - **clock** *(float) --* 

                  The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                  
            
              

              - **resolution** *(dict) --* 

                Represents the screen resolution of a device in height and width, expressed in pixels.

                
                

                - **width** *(integer) --* 

                  The screen resolution's width, expressed in pixels.

                  
                

                - **height** *(integer) --* 

                  The screen resolution's height, expressed in pixels.

                  
            
              

              - **heapSize** *(integer) --* 

                The device's heap size, expressed in bytes.

                
              

              - **memory** *(integer) --* 

                The device's total memory size, expressed in bytes.

                
              

              - **image** *(string) --* 

                The device's image name.

                
              

              - **carrier** *(string) --* 

                The device's carrier.

                
              

              - **radio** *(string) --* 

                The device's radio.

                
              

              - **remoteAccessEnabled** *(boolean) --* 

                Specifies whether remote access has been enabled for the specified device.

                
              

              - **fleetType** *(string) --* 

                The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

                
              

              - **fleetName** *(string) --* 

                The name of the fleet to which this device belongs.

                
          
            

            - **compatible** *(boolean) --* 

              Whether the result was compatible with the device pool.

              
            

            - **incompatibilityMessages** *(list) --* 

              Information about the compatibility.

              
              

              - *(dict) --* 

                Represents information about incompatibility.

                
                

                - **message** *(string) --* 

                  A message about the incompatibility.

                  
                

                - **type** *(string) --* 

                  The type of incompatibility.

                   

                  Allowed values include:

                   

                   
                  * ARN: The ARN.
                   
                  * FORM_FACTOR: The form factor (for example, phone or tablet).
                   
                  * MANUFACTURER: The manufacturer.
                   
                  * PLATFORM: The platform (for example, Android or iOS).
                   

                  
            
          
        
      
    

  .. py:method:: get_job(**kwargs)

    

    Gets information about a job.

    

    **Request Syntax** 
    ::

      response = client.get_job(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The job's ARN.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'job': {
                'arn': 'string',
                'name': 'string',
                'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                'created': datetime(2015, 1, 1),
                'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                'started': datetime(2015, 1, 1),
                'stopped': datetime(2015, 1, 1),
                'counters': {
                    'total': 123,
                    'passed': 123,
                    'failed': 123,
                    'warned': 123,
                    'errored': 123,
                    'stopped': 123,
                    'skipped': 123
                },
                'message': 'string',
                'device': {
                    'arn': 'string',
                    'name': 'string',
                    'manufacturer': 'string',
                    'model': 'string',
                    'formFactor': 'PHONE'|'TABLET',
                    'platform': 'ANDROID'|'IOS',
                    'os': 'string',
                    'cpu': {
                        'frequency': 'string',
                        'architecture': 'string',
                        'clock': 123.0
                    },
                    'resolution': {
                        'width': 123,
                        'height': 123
                    },
                    'heapSize': 123,
                    'memory': 123,
                    'image': 'string',
                    'carrier': 'string',
                    'radio': 'string',
                    'remoteAccessEnabled': True|False,
                    'fleetType': 'string',
                    'fleetName': 'string'
                },
                'deviceMinutes': {
                    'total': 123.0,
                    'metered': 123.0,
                    'unmetered': 123.0
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a get job request.

        
        

        - **job** *(dict) --* 

          Represents a device.

          
          

          - **arn** *(string) --* 

            The job's ARN.

            
          

          - **name** *(string) --* 

            The job's name.

            
          

          - **type** *(string) --* 

            The job's type.

             

            Allowed values include the following:

             

             
            * BUILTIN_FUZZ: The built-in fuzz type.
             
            * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
             
            * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
             
            * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
             
            * APPIUM_PYTHON: The Appium Python type.
             
            * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
             
            * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
             
            * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
             
            * CALABASH: The Calabash type.
             
            * INSTRUMENTATION: The Instrumentation type.
             
            * UIAUTOMATION: The uiautomation type.
             
            * UIAUTOMATOR: The uiautomator type.
             
            * XCTEST: The XCode test type.
             
            * XCTEST_UI: The XCode UI test type.
             

            
          

          - **created** *(datetime) --* 

            When the job was created.

            
          

          - **status** *(string) --* 

            The job's status.

             

            Allowed values include:

             

             
            * PENDING: A pending status.
             
            * PENDING_CONCURRENCY: A pending concurrency status.
             
            * PENDING_DEVICE: A pending device status.
             
            * PROCESSING: A processing status.
             
            * SCHEDULING: A scheduling status.
             
            * PREPARING: A preparing status.
             
            * RUNNING: A running status.
             
            * COMPLETED: A completed status.
             
            * STOPPING: A stopping status.
             

            
          

          - **result** *(string) --* 

            The job's result.

             

            Allowed values include:

             

             
            * PENDING: A pending condition.
             
            * PASSED: A passing condition.
             
            * WARNED: A warning condition.
             
            * FAILED: A failed condition.
             
            * SKIPPED: A skipped condition.
             
            * ERRORED: An error condition.
             
            * STOPPED: A stopped condition.
             

            
          

          - **started** *(datetime) --* 

            The job's start time.

            
          

          - **stopped** *(datetime) --* 

            The job's stop time.

            
          

          - **counters** *(dict) --* 

            The job's result counters.

            
            

            - **total** *(integer) --* 

              The total number of entities.

              
            

            - **passed** *(integer) --* 

              The number of passed entities.

              
            

            - **failed** *(integer) --* 

              The number of failed entities.

              
            

            - **warned** *(integer) --* 

              The number of warned entities.

              
            

            - **errored** *(integer) --* 

              The number of errored entities.

              
            

            - **stopped** *(integer) --* 

              The number of stopped entities.

              
            

            - **skipped** *(integer) --* 

              The number of skipped entities.

              
        
          

          - **message** *(string) --* 

            A message about the job's result.

            
          

          - **device** *(dict) --* 

            Represents a device type that an app is tested against.

            
            

            - **arn** *(string) --* 

              The device's ARN.

              
            

            - **name** *(string) --* 

              The device's display name.

              
            

            - **manufacturer** *(string) --* 

              The device's manufacturer name.

              
            

            - **model** *(string) --* 

              The device's model name.

              
            

            - **formFactor** *(string) --* 

              The device's form factor.

               

              Allowed values include:

               

               
              * PHONE: The phone form factor.
               
              * TABLET: The tablet form factor.
               

              
            

            - **platform** *(string) --* 

              The device's platform.

               

              Allowed values include:

               

               
              * ANDROID: The Android platform.
               
              * IOS: The iOS platform.
               

              
            

            - **os** *(string) --* 

              The device's operating system type.

              
            

            - **cpu** *(dict) --* 

              Information about the device's CPU.

              
              

              - **frequency** *(string) --* 

                The CPU's frequency.

                
              

              - **architecture** *(string) --* 

                The CPU's architecture, for example x86 or ARM.

                
              

              - **clock** *(float) --* 

                The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                
          
            

            - **resolution** *(dict) --* 

              Represents the screen resolution of a device in height and width, expressed in pixels.

              
              

              - **width** *(integer) --* 

                The screen resolution's width, expressed in pixels.

                
              

              - **height** *(integer) --* 

                The screen resolution's height, expressed in pixels.

                
          
            

            - **heapSize** *(integer) --* 

              The device's heap size, expressed in bytes.

              
            

            - **memory** *(integer) --* 

              The device's total memory size, expressed in bytes.

              
            

            - **image** *(string) --* 

              The device's image name.

              
            

            - **carrier** *(string) --* 

              The device's carrier.

              
            

            - **radio** *(string) --* 

              The device's radio.

              
            

            - **remoteAccessEnabled** *(boolean) --* 

              Specifies whether remote access has been enabled for the specified device.

              
            

            - **fleetType** *(string) --* 

              The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

              
            

            - **fleetName** *(string) --* 

              The name of the fleet to which this device belongs.

              
        
          

          - **deviceMinutes** *(dict) --* 

            Represents the total (metered or unmetered) minutes used by the job.

            
            

            - **total** *(float) --* 

              When specified, represents the total minutes used by the resource to run tests.

              
            

            - **metered** *(float) --* 

              When specified, represents only the sum of metered minutes used by the resource to run tests.

              
            

            - **unmetered** *(float) --* 

              When specified, represents only the sum of unmetered minutes used by the resource to run tests.

              
        
      
    

  .. py:method:: get_offering_status(**kwargs)

    

    Gets the current status and future status of all offerings purchased by an AWS account. The response indicates how many offerings are currently available and the offerings that will be available in the next period. The API returns a ``NotEligible`` error if the user is not permitted to invoke the operation. Please contact `aws-devicefarm-support@amazon.com`_ if you believe that you should be able to invoke this operation.

    

    **Request Syntax** 
    ::

      response = client.get_offering_status(
          nextToken='string'
      )
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'current': {
                'string': {
                    'type': 'PURCHASE'|'RENEW'|'SYSTEM',
                    'offering': {
                        'id': 'string',
                        'description': 'string',
                        'type': 'RECURRING',
                        'platform': 'ANDROID'|'IOS',
                        'recurringCharges': [
                            {
                                'cost': {
                                    'amount': 123.0,
                                    'currencyCode': 'USD'
                                },
                                'frequency': 'MONTHLY'
                            },
                        ]
                    },
                    'quantity': 123,
                    'effectiveOn': datetime(2015, 1, 1)
                }
            },
            'nextPeriod': {
                'string': {
                    'type': 'PURCHASE'|'RENEW'|'SYSTEM',
                    'offering': {
                        'id': 'string',
                        'description': 'string',
                        'type': 'RECURRING',
                        'platform': 'ANDROID'|'IOS',
                        'recurringCharges': [
                            {
                                'cost': {
                                    'amount': 123.0,
                                    'currencyCode': 'USD'
                                },
                                'frequency': 'MONTHLY'
                            },
                        ]
                    },
                    'quantity': 123,
                    'effectiveOn': datetime(2015, 1, 1)
                }
            },
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Returns the status result for a device offering.

        
        

        - **current** *(dict) --* 

          When specified, gets the offering status for the current period.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              The status of the offering.

              
              

              - **type** *(string) --* 

                The type specified for the offering status.

                
              

              - **offering** *(dict) --* 

                Represents the metadata of an offering status.

                
                

                - **id** *(string) --* 

                  The ID that corresponds to a device offering.

                  
                

                - **description** *(string) --* 

                  A string describing the offering.

                  
                

                - **type** *(string) --* 

                  The type of offering (e.g., "RECURRING") for a device.

                  
                

                - **platform** *(string) --* 

                  The platform of the device (e.g., ANDROID or IOS).

                  
                

                - **recurringCharges** *(list) --* 

                  Specifies whether there are recurring charges for the offering.

                  
                  

                  - *(dict) --* 

                    Specifies whether charges for devices will be recurring.

                    
                    

                    - **cost** *(dict) --* 

                      The cost of the recurring charge.

                      
                      

                      - **amount** *(float) --* 

                        The numerical amount of an offering or transaction.

                        
                      

                      - **currencyCode** *(string) --* 

                        The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

                        
                  
                    

                    - **frequency** *(string) --* 

                      The frequency in which charges will recur.

                      
                
              
            
              

              - **quantity** *(integer) --* 

                The number of available devices in the offering.

                
              

              - **effectiveOn** *(datetime) --* 

                The date on which the offering is effective.

                
          
      
    
        

        - **nextPeriod** *(dict) --* 

          When specified, gets the offering status for the next period.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              The status of the offering.

              
              

              - **type** *(string) --* 

                The type specified for the offering status.

                
              

              - **offering** *(dict) --* 

                Represents the metadata of an offering status.

                
                

                - **id** *(string) --* 

                  The ID that corresponds to a device offering.

                  
                

                - **description** *(string) --* 

                  A string describing the offering.

                  
                

                - **type** *(string) --* 

                  The type of offering (e.g., "RECURRING") for a device.

                  
                

                - **platform** *(string) --* 

                  The platform of the device (e.g., ANDROID or IOS).

                  
                

                - **recurringCharges** *(list) --* 

                  Specifies whether there are recurring charges for the offering.

                  
                  

                  - *(dict) --* 

                    Specifies whether charges for devices will be recurring.

                    
                    

                    - **cost** *(dict) --* 

                      The cost of the recurring charge.

                      
                      

                      - **amount** *(float) --* 

                        The numerical amount of an offering or transaction.

                        
                      

                      - **currencyCode** *(string) --* 

                        The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

                        
                  
                    

                    - **frequency** *(string) --* 

                      The frequency in which charges will recur.

                      
                
              
            
              

              - **quantity** *(integer) --* 

                The number of available devices in the offering.

                
              

              - **effectiveOn** *(datetime) --* 

                The date on which the offering is effective.

                
          
      
    
        

        - **nextToken** *(string) --* 

          An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

          
    

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


  .. py:method:: get_project(**kwargs)

    

    Gets information about a project.

    

    **Request Syntax** 
    ::

      response = client.get_project(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The project's ARN.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'project': {
                'arn': 'string',
                'name': 'string',
                'created': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a get project request.

        
        

        - **project** *(dict) --* 

          Represents an operating-system neutral workspace for running and managing tests.

          
          

          - **arn** *(string) --* 

            The project's ARN.

            
          

          - **name** *(string) --* 

            The project's name.

            
          

          - **created** *(datetime) --* 

            When the project was created.

            
      
    

  .. py:method:: get_remote_access_session(**kwargs)

    

    Returns a link to a currently running remote access session.

    

    **Request Syntax** 
    ::

      response = client.get_remote_access_session(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the remote access session about which you want to get session information.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'remoteAccessSession': {
                'arn': 'string',
                'name': 'string',
                'created': datetime(2015, 1, 1),
                'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                'message': 'string',
                'started': datetime(2015, 1, 1),
                'stopped': datetime(2015, 1, 1),
                'device': {
                    'arn': 'string',
                    'name': 'string',
                    'manufacturer': 'string',
                    'model': 'string',
                    'formFactor': 'PHONE'|'TABLET',
                    'platform': 'ANDROID'|'IOS',
                    'os': 'string',
                    'cpu': {
                        'frequency': 'string',
                        'architecture': 'string',
                        'clock': 123.0
                    },
                    'resolution': {
                        'width': 123,
                        'height': 123
                    },
                    'heapSize': 123,
                    'memory': 123,
                    'image': 'string',
                    'carrier': 'string',
                    'radio': 'string',
                    'remoteAccessEnabled': True|False,
                    'fleetType': 'string',
                    'fleetName': 'string'
                },
                'billingMethod': 'METERED'|'UNMETERED',
                'deviceMinutes': {
                    'total': 123.0,
                    'metered': 123.0,
                    'unmetered': 123.0
                },
                'endpoint': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server that lists detailed information about the remote access session.

        
        

        - **remoteAccessSession** *(dict) --* 

          A container that lists detailed information about the remote access session.

          
          

          - **arn** *(string) --* 

            The Amazon Resource Name (ARN) of the remote access session.

            
          

          - **name** *(string) --* 

            The name of the remote access session.

            
          

          - **created** *(datetime) --* 

            The date and time the remote access session was created.

            
          

          - **status** *(string) --* 

            The status of the remote access session. Can be any of the following:

             

             
            * PENDING: A pending status.
             
            * PENDING_CONCURRENCY: A pending concurrency status.
             
            * PENDING_DEVICE: A pending device status.
             
            * PROCESSING: A processing status.
             
            * SCHEDULING: A scheduling status.
             
            * PREPARING: A preparing status.
             
            * RUNNING: A running status.
             
            * COMPLETED: A completed status.
             
            * STOPPING: A stopping status.
             

            
          

          - **result** *(string) --* 

            The result of the remote access session. Can be any of the following:

             

             
            * PENDING: A pending condition.
             
            * PASSED: A passing condition.
             
            * WARNED: A warning condition.
             
            * FAILED: A failed condition.
             
            * SKIPPED: A skipped condition.
             
            * ERRORED: An error condition.
             
            * STOPPED: A stopped condition.
             

            
          

          - **message** *(string) --* 

            A message about the remote access session.

            
          

          - **started** *(datetime) --* 

            The date and time the remote access session was started.

            
          

          - **stopped** *(datetime) --* 

            The date and time the remote access session was stopped.

            
          

          - **device** *(dict) --* 

            Represents a device type that an app is tested against.

            
            

            - **arn** *(string) --* 

              The device's ARN.

              
            

            - **name** *(string) --* 

              The device's display name.

              
            

            - **manufacturer** *(string) --* 

              The device's manufacturer name.

              
            

            - **model** *(string) --* 

              The device's model name.

              
            

            - **formFactor** *(string) --* 

              The device's form factor.

               

              Allowed values include:

               

               
              * PHONE: The phone form factor.
               
              * TABLET: The tablet form factor.
               

              
            

            - **platform** *(string) --* 

              The device's platform.

               

              Allowed values include:

               

               
              * ANDROID: The Android platform.
               
              * IOS: The iOS platform.
               

              
            

            - **os** *(string) --* 

              The device's operating system type.

              
            

            - **cpu** *(dict) --* 

              Information about the device's CPU.

              
              

              - **frequency** *(string) --* 

                The CPU's frequency.

                
              

              - **architecture** *(string) --* 

                The CPU's architecture, for example x86 or ARM.

                
              

              - **clock** *(float) --* 

                The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                
          
            

            - **resolution** *(dict) --* 

              Represents the screen resolution of a device in height and width, expressed in pixels.

              
              

              - **width** *(integer) --* 

                The screen resolution's width, expressed in pixels.

                
              

              - **height** *(integer) --* 

                The screen resolution's height, expressed in pixels.

                
          
            

            - **heapSize** *(integer) --* 

              The device's heap size, expressed in bytes.

              
            

            - **memory** *(integer) --* 

              The device's total memory size, expressed in bytes.

              
            

            - **image** *(string) --* 

              The device's image name.

              
            

            - **carrier** *(string) --* 

              The device's carrier.

              
            

            - **radio** *(string) --* 

              The device's radio.

              
            

            - **remoteAccessEnabled** *(boolean) --* 

              Specifies whether remote access has been enabled for the specified device.

              
            

            - **fleetType** *(string) --* 

              The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

              
            

            - **fleetName** *(string) --* 

              The name of the fleet to which this device belongs.

              
        
          

          - **billingMethod** *(string) --* 

            The billing method of the remote access session. Possible values include ``METERED`` or ``UNMETERED`` . For more information about metered devices, see `AWS Device Farm terminology`_ ."

            
          

          - **deviceMinutes** *(dict) --* 

            Represents the total (metered or unmetered) minutes used by the resource to run tests. Contains the sum of minutes consumed by all children.

            
            

            - **total** *(float) --* 

              When specified, represents the total minutes used by the resource to run tests.

              
            

            - **metered** *(float) --* 

              When specified, represents only the sum of metered minutes used by the resource to run tests.

              
            

            - **unmetered** *(float) --* 

              When specified, represents only the sum of unmetered minutes used by the resource to run tests.

              
        
          

          - **endpoint** *(string) --* 

            The endpoint for the remote access sesssion.

            
      
    

  .. py:method:: get_run(**kwargs)

    

    Gets information about a run.

    

    **Request Syntax** 
    ::

      response = client.get_run(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The run's ARN.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'run': {
                'arn': 'string',
                'name': 'string',
                'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                'platform': 'ANDROID'|'IOS',
                'created': datetime(2015, 1, 1),
                'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                'started': datetime(2015, 1, 1),
                'stopped': datetime(2015, 1, 1),
                'counters': {
                    'total': 123,
                    'passed': 123,
                    'failed': 123,
                    'warned': 123,
                    'errored': 123,
                    'stopped': 123,
                    'skipped': 123
                },
                'message': 'string',
                'totalJobs': 123,
                'completedJobs': 123,
                'billingMethod': 'METERED'|'UNMETERED',
                'deviceMinutes': {
                    'total': 123.0,
                    'metered': 123.0,
                    'unmetered': 123.0
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a get run request.

        
        

        - **run** *(dict) --* 

          Represents an app on a set of devices with a specific test and configuration.

          
          

          - **arn** *(string) --* 

            The run's ARN.

            
          

          - **name** *(string) --* 

            The run's name.

            
          

          - **type** *(string) --* 

            The run's type.

             

            Must be one of the following values:

             

             
            * BUILTIN_FUZZ: The built-in fuzz type.
             
            * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
             
            * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
             
            * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
             
            * APPIUM_PYTHON: The Appium Python type.
             
            * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
             
            * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
             
            * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
             
            * CALABASH: The Calabash type.
             
            * INSTRUMENTATION: The Instrumentation type.
             
            * UIAUTOMATION: The uiautomation type.
             
            * UIAUTOMATOR: The uiautomator type.
             
            * XCTEST: The XCode test type.
             
            * XCTEST_UI: The XCode UI test type.
             

            
          

          - **platform** *(string) --* 

            The run's platform.

             

            Allowed values include:

             

             
            * ANDROID: The Android platform.
             
            * IOS: The iOS platform.
             

            
          

          - **created** *(datetime) --* 

            When the run was created.

            
          

          - **status** *(string) --* 

            The run's status.

             

            Allowed values include:

             

             
            * PENDING: A pending status.
             
            * PENDING_CONCURRENCY: A pending concurrency status.
             
            * PENDING_DEVICE: A pending device status.
             
            * PROCESSING: A processing status.
             
            * SCHEDULING: A scheduling status.
             
            * PREPARING: A preparing status.
             
            * RUNNING: A running status.
             
            * COMPLETED: A completed status.
             
            * STOPPING: A stopping status.
             

            
          

          - **result** *(string) --* 

            The run's result.

             

            Allowed values include:

             

             
            * PENDING: A pending condition.
             
            * PASSED: A passing condition.
             
            * WARNED: A warning condition.
             
            * FAILED: A failed condition.
             
            * SKIPPED: A skipped condition.
             
            * ERRORED: An error condition.
             
            * STOPPED: A stopped condition.
             

            
          

          - **started** *(datetime) --* 

            The run's start time.

            
          

          - **stopped** *(datetime) --* 

            The run's stop time.

            
          

          - **counters** *(dict) --* 

            The run's result counters.

            
            

            - **total** *(integer) --* 

              The total number of entities.

              
            

            - **passed** *(integer) --* 

              The number of passed entities.

              
            

            - **failed** *(integer) --* 

              The number of failed entities.

              
            

            - **warned** *(integer) --* 

              The number of warned entities.

              
            

            - **errored** *(integer) --* 

              The number of errored entities.

              
            

            - **stopped** *(integer) --* 

              The number of stopped entities.

              
            

            - **skipped** *(integer) --* 

              The number of skipped entities.

              
        
          

          - **message** *(string) --* 

            A message about the run's result.

            
          

          - **totalJobs** *(integer) --* 

            The total number of jobs for the run.

            
          

          - **completedJobs** *(integer) --* 

            The total number of completed jobs.

            
          

          - **billingMethod** *(string) --* 

            Specifies the billing method for a test run: ``metered`` or ``unmetered`` . If the parameter is not specified, the default value is ``unmetered`` .

            
          

          - **deviceMinutes** *(dict) --* 

            Represents the total (metered or unmetered) minutes used by the test run.

            
            

            - **total** *(float) --* 

              When specified, represents the total minutes used by the resource to run tests.

              
            

            - **metered** *(float) --* 

              When specified, represents only the sum of metered minutes used by the resource to run tests.

              
            

            - **unmetered** *(float) --* 

              When specified, represents only the sum of unmetered minutes used by the resource to run tests.

              
        
      
    

  .. py:method:: get_suite(**kwargs)

    

    Gets information about a suite.

    

    **Request Syntax** 
    ::

      response = client.get_suite(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The suite's ARN.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'suite': {
                'arn': 'string',
                'name': 'string',
                'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                'created': datetime(2015, 1, 1),
                'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                'started': datetime(2015, 1, 1),
                'stopped': datetime(2015, 1, 1),
                'counters': {
                    'total': 123,
                    'passed': 123,
                    'failed': 123,
                    'warned': 123,
                    'errored': 123,
                    'stopped': 123,
                    'skipped': 123
                },
                'message': 'string',
                'deviceMinutes': {
                    'total': 123.0,
                    'metered': 123.0,
                    'unmetered': 123.0
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a get suite request.

        
        

        - **suite** *(dict) --* 

          Represents a collection of one or more tests.

          
          

          - **arn** *(string) --* 

            The suite's ARN.

            
          

          - **name** *(string) --* 

            The suite's name.

            
          

          - **type** *(string) --* 

            The suite's type.

             

            Must be one of the following values:

             

             
            * BUILTIN_FUZZ: The built-in fuzz type.
             
            * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
             
            * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
             
            * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
             
            * APPIUM_PYTHON: The Appium Python type.
             
            * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
             
            * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
             
            * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
             
            * CALABASH: The Calabash type.
             
            * INSTRUMENTATION: The Instrumentation type.
             
            * UIAUTOMATION: The uiautomation type.
             
            * UIAUTOMATOR: The uiautomator type.
             
            * XCTEST: The XCode test type.
             
            * XCTEST_UI: The XCode UI test type.
             

            
          

          - **created** *(datetime) --* 

            When the suite was created.

            
          

          - **status** *(string) --* 

            The suite's status.

             

            Allowed values include:

             

             
            * PENDING: A pending status.
             
            * PENDING_CONCURRENCY: A pending concurrency status.
             
            * PENDING_DEVICE: A pending device status.
             
            * PROCESSING: A processing status.
             
            * SCHEDULING: A scheduling status.
             
            * PREPARING: A preparing status.
             
            * RUNNING: A running status.
             
            * COMPLETED: A completed status.
             
            * STOPPING: A stopping status.
             

            
          

          - **result** *(string) --* 

            The suite's result.

             

            Allowed values include:

             

             
            * PENDING: A pending condition.
             
            * PASSED: A passing condition.
             
            * WARNED: A warning condition.
             
            * FAILED: A failed condition.
             
            * SKIPPED: A skipped condition.
             
            * ERRORED: An error condition.
             
            * STOPPED: A stopped condition.
             

            
          

          - **started** *(datetime) --* 

            The suite's start time.

            
          

          - **stopped** *(datetime) --* 

            The suite's stop time.

            
          

          - **counters** *(dict) --* 

            The suite's result counters.

            
            

            - **total** *(integer) --* 

              The total number of entities.

              
            

            - **passed** *(integer) --* 

              The number of passed entities.

              
            

            - **failed** *(integer) --* 

              The number of failed entities.

              
            

            - **warned** *(integer) --* 

              The number of warned entities.

              
            

            - **errored** *(integer) --* 

              The number of errored entities.

              
            

            - **stopped** *(integer) --* 

              The number of stopped entities.

              
            

            - **skipped** *(integer) --* 

              The number of skipped entities.

              
        
          

          - **message** *(string) --* 

            A message about the suite's result.

            
          

          - **deviceMinutes** *(dict) --* 

            Represents the total (metered or unmetered) minutes used by the test suite.

            
            

            - **total** *(float) --* 

              When specified, represents the total minutes used by the resource to run tests.

              
            

            - **metered** *(float) --* 

              When specified, represents only the sum of metered minutes used by the resource to run tests.

              
            

            - **unmetered** *(float) --* 

              When specified, represents only the sum of unmetered minutes used by the resource to run tests.

              
        
      
    

  .. py:method:: get_test(**kwargs)

    

    Gets information about a test.

    

    **Request Syntax** 
    ::

      response = client.get_test(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The test's ARN.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'test': {
                'arn': 'string',
                'name': 'string',
                'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                'created': datetime(2015, 1, 1),
                'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                'started': datetime(2015, 1, 1),
                'stopped': datetime(2015, 1, 1),
                'counters': {
                    'total': 123,
                    'passed': 123,
                    'failed': 123,
                    'warned': 123,
                    'errored': 123,
                    'stopped': 123,
                    'skipped': 123
                },
                'message': 'string',
                'deviceMinutes': {
                    'total': 123.0,
                    'metered': 123.0,
                    'unmetered': 123.0
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a get test request.

        
        

        - **test** *(dict) --* 

          Represents a condition that is evaluated.

          
          

          - **arn** *(string) --* 

            The test's ARN.

            
          

          - **name** *(string) --* 

            The test's name.

            
          

          - **type** *(string) --* 

            The test's type.

             

            Must be one of the following values:

             

             
            * BUILTIN_FUZZ: The built-in fuzz type.
             
            * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
             
            * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
             
            * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
             
            * APPIUM_PYTHON: The Appium Python type.
             
            * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
             
            * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
             
            * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
             
            * CALABASH: The Calabash type.
             
            * INSTRUMENTATION: The Instrumentation type.
             
            * UIAUTOMATION: The uiautomation type.
             
            * UIAUTOMATOR: The uiautomator type.
             
            * XCTEST: The XCode test type.
             
            * XCTEST_UI: The XCode UI test type.
             

            
          

          - **created** *(datetime) --* 

            When the test was created.

            
          

          - **status** *(string) --* 

            The test's status.

             

            Allowed values include:

             

             
            * PENDING: A pending status.
             
            * PENDING_CONCURRENCY: A pending concurrency status.
             
            * PENDING_DEVICE: A pending device status.
             
            * PROCESSING: A processing status.
             
            * SCHEDULING: A scheduling status.
             
            * PREPARING: A preparing status.
             
            * RUNNING: A running status.
             
            * COMPLETED: A completed status.
             
            * STOPPING: A stopping status.
             

            
          

          - **result** *(string) --* 

            The test's result.

             

            Allowed values include:

             

             
            * PENDING: A pending condition.
             
            * PASSED: A passing condition.
             
            * WARNED: A warning condition.
             
            * FAILED: A failed condition.
             
            * SKIPPED: A skipped condition.
             
            * ERRORED: An error condition.
             
            * STOPPED: A stopped condition.
             

            
          

          - **started** *(datetime) --* 

            The test's start time.

            
          

          - **stopped** *(datetime) --* 

            The test's stop time.

            
          

          - **counters** *(dict) --* 

            The test's result counters.

            
            

            - **total** *(integer) --* 

              The total number of entities.

              
            

            - **passed** *(integer) --* 

              The number of passed entities.

              
            

            - **failed** *(integer) --* 

              The number of failed entities.

              
            

            - **warned** *(integer) --* 

              The number of warned entities.

              
            

            - **errored** *(integer) --* 

              The number of errored entities.

              
            

            - **stopped** *(integer) --* 

              The number of stopped entities.

              
            

            - **skipped** *(integer) --* 

              The number of skipped entities.

              
        
          

          - **message** *(string) --* 

            A message about the test's result.

            
          

          - **deviceMinutes** *(dict) --* 

            Represents the total (metered or unmetered) minutes used by the test.

            
            

            - **total** *(float) --* 

              When specified, represents the total minutes used by the resource to run tests.

              
            

            - **metered** *(float) --* 

              When specified, represents only the sum of metered minutes used by the resource to run tests.

              
            

            - **unmetered** *(float) --* 

              When specified, represents only the sum of unmetered minutes used by the resource to run tests.

              
        
      
    

  .. py:method:: get_upload(**kwargs)

    

    Gets information about an upload.

    

    **Request Syntax** 
    ::

      response = client.get_upload(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The upload's ARN.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'upload': {
                'arn': 'string',
                'name': 'string',
                'created': datetime(2015, 1, 1),
                'type': 'ANDROID_APP'|'IOS_APP'|'WEB_APP'|'EXTERNAL_DATA'|'APPIUM_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_PYTHON_TEST_PACKAGE'|'APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_WEB_PYTHON_TEST_PACKAGE'|'CALABASH_TEST_PACKAGE'|'INSTRUMENTATION_TEST_PACKAGE'|'UIAUTOMATION_TEST_PACKAGE'|'UIAUTOMATOR_TEST_PACKAGE'|'XCTEST_TEST_PACKAGE'|'XCTEST_UI_TEST_PACKAGE',
                'status': 'INITIALIZED'|'PROCESSING'|'SUCCEEDED'|'FAILED',
                'url': 'string',
                'metadata': 'string',
                'contentType': 'string',
                'message': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a get upload request.

        
        

        - **upload** *(dict) --* 

          An app or a set of one or more tests to upload or that have been uploaded.

          
          

          - **arn** *(string) --* 

            The upload's ARN.

            
          

          - **name** *(string) --* 

            The upload's file name.

            
          

          - **created** *(datetime) --* 

            When the upload was created.

            
          

          - **type** *(string) --* 

            The upload's type.

             

            Must be one of the following values:

             

             
            * ANDROID_APP: An Android upload.
             
            * IOS_APP: An iOS upload.
             
            * WEB_APP: A web appliction upload.
             
            * EXTERNAL_DATA: An external data upload.
             
            * APPIUM_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
             
            * APPIUM_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
             
            * APPIUM_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
             
            * APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
             
            * APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
             
            * APPIUM_WEB_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
             
            * CALABASH_TEST_PACKAGE: A Calabash test package upload.
             
            * INSTRUMENTATION_TEST_PACKAGE: An instrumentation upload.
             
            * UIAUTOMATION_TEST_PACKAGE: A uiautomation test package upload.
             
            * UIAUTOMATOR_TEST_PACKAGE: A uiautomator test package upload.
             
            * XCTEST_TEST_PACKAGE: An XCode test package upload.
             
            * XCTEST_UI_TEST_PACKAGE: An XCode UI test package upload.
             

            
          

          - **status** *(string) --* 

            The upload's status.

             

            Must be one of the following values:

             

             
            * FAILED: A failed status.
             
            * INITIALIZED: An initialized status.
             
            * PROCESSING: A processing status.
             
            * SUCCEEDED: A succeeded status.
             

            
          

          - **url** *(string) --* 

            The pre-signed Amazon S3 URL that was used to store a file through a corresponding PUT request.

            
          

          - **metadata** *(string) --* 

            The upload's metadata. For example, for Android, this contains information that is parsed from the manifest and is displayed in the AWS Device Farm console after the associated app is uploaded.

            
          

          - **contentType** *(string) --* 

            The upload's content type (for example, "application/octet-stream").

            
          

          - **message** *(string) --* 

            A message about the upload's result.

            
      
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: install_to_remote_access_session(**kwargs)

    

    Installs an application to the device in a remote access session. For Android applications, the file must be in .apk format. For iOS applications, the file must be in .ipa format.

    

    **Request Syntax** 
    ::

      response = client.install_to_remote_access_session(
          remoteAccessSessionArn='string',
          appArn='string'
      )
    :type remoteAccessSessionArn: string
    :param remoteAccessSessionArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the remote access session about which you are requesting information.

      

    
    :type appArn: string
    :param appArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the app about which you are requesting information.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'appUpload': {
                'arn': 'string',
                'name': 'string',
                'created': datetime(2015, 1, 1),
                'type': 'ANDROID_APP'|'IOS_APP'|'WEB_APP'|'EXTERNAL_DATA'|'APPIUM_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_PYTHON_TEST_PACKAGE'|'APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_WEB_PYTHON_TEST_PACKAGE'|'CALABASH_TEST_PACKAGE'|'INSTRUMENTATION_TEST_PACKAGE'|'UIAUTOMATION_TEST_PACKAGE'|'UIAUTOMATOR_TEST_PACKAGE'|'XCTEST_TEST_PACKAGE'|'XCTEST_UI_TEST_PACKAGE',
                'status': 'INITIALIZED'|'PROCESSING'|'SUCCEEDED'|'FAILED',
                'url': 'string',
                'metadata': 'string',
                'contentType': 'string',
                'message': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server after AWS Device Farm makes a request to install to a remote access session.

        
        

        - **appUpload** *(dict) --* 

          An app or a set of one or more tests to upload or that have been uploaded.

          
          

          - **arn** *(string) --* 

            The upload's ARN.

            
          

          - **name** *(string) --* 

            The upload's file name.

            
          

          - **created** *(datetime) --* 

            When the upload was created.

            
          

          - **type** *(string) --* 

            The upload's type.

             

            Must be one of the following values:

             

             
            * ANDROID_APP: An Android upload.
             
            * IOS_APP: An iOS upload.
             
            * WEB_APP: A web appliction upload.
             
            * EXTERNAL_DATA: An external data upload.
             
            * APPIUM_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
             
            * APPIUM_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
             
            * APPIUM_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
             
            * APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
             
            * APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
             
            * APPIUM_WEB_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
             
            * CALABASH_TEST_PACKAGE: A Calabash test package upload.
             
            * INSTRUMENTATION_TEST_PACKAGE: An instrumentation upload.
             
            * UIAUTOMATION_TEST_PACKAGE: A uiautomation test package upload.
             
            * UIAUTOMATOR_TEST_PACKAGE: A uiautomator test package upload.
             
            * XCTEST_TEST_PACKAGE: An XCode test package upload.
             
            * XCTEST_UI_TEST_PACKAGE: An XCode UI test package upload.
             

            
          

          - **status** *(string) --* 

            The upload's status.

             

            Must be one of the following values:

             

             
            * FAILED: A failed status.
             
            * INITIALIZED: An initialized status.
             
            * PROCESSING: A processing status.
             
            * SUCCEEDED: A succeeded status.
             

            
          

          - **url** *(string) --* 

            The pre-signed Amazon S3 URL that was used to store a file through a corresponding PUT request.

            
          

          - **metadata** *(string) --* 

            The upload's metadata. For example, for Android, this contains information that is parsed from the manifest and is displayed in the AWS Device Farm console after the associated app is uploaded.

            
          

          - **contentType** *(string) --* 

            The upload's content type (for example, "application/octet-stream").

            
          

          - **message** *(string) --* 

            A message about the upload's result.

            
      
    

  .. py:method:: list_artifacts(**kwargs)

    

    Gets information about artifacts.

    

    **Request Syntax** 
    ::

      response = client.list_artifacts(
          arn='string',
          type='SCREENSHOT'|'FILE'|'LOG',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The Run, Job, Suite, or Test ARN.

      

    
    :type type: string
    :param type: **[REQUIRED]** 

      The artifacts' type.

       

      Allowed values include:

       

       
      * FILE: The artifacts are files.
       
      * LOG: The artifacts are logs.
       
      * SCREENSHOT: The artifacts are screenshots.
       

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'artifacts': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'UNKNOWN'|'SCREENSHOT'|'DEVICE_LOG'|'MESSAGE_LOG'|'VIDEO_LOG'|'RESULT_LOG'|'SERVICE_LOG'|'WEBKIT_LOG'|'INSTRUMENTATION_OUTPUT'|'EXERCISER_MONKEY_OUTPUT'|'CALABASH_JSON_OUTPUT'|'CALABASH_PRETTY_OUTPUT'|'CALABASH_STANDARD_OUTPUT'|'CALABASH_JAVA_XML_OUTPUT'|'AUTOMATION_OUTPUT'|'APPIUM_SERVER_OUTPUT'|'APPIUM_JAVA_OUTPUT'|'APPIUM_JAVA_XML_OUTPUT'|'APPIUM_PYTHON_OUTPUT'|'APPIUM_PYTHON_XML_OUTPUT'|'EXPLORER_EVENT_LOG'|'EXPLORER_SUMMARY_LOG'|'APPLICATION_CRASH_REPORT'|'XCTEST_LOG'|'VIDEO',
                    'extension': 'string',
                    'url': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list artifacts operation.

        
        

        - **artifacts** *(list) --* 

          Information about the artifacts.

          
          

          - *(dict) --* 

            Represents the output of a test. Examples of artifacts include logs and screenshots.

            
            

            - **arn** *(string) --* 

              The artifact's ARN.

              
            

            - **name** *(string) --* 

              The artifact's name.

              
            

            - **type** *(string) --* 

              The artifact's type.

               

              Allowed values include the following:

               

               
              * UNKNOWN: An unknown type.
               
              * SCREENSHOT: The screenshot type.
               
              * DEVICE_LOG: The device log type.
               
              * MESSAGE_LOG: The message log type.
               
              * RESULT_LOG: The result log type.
               
              * SERVICE_LOG: The service log type.
               
              * WEBKIT_LOG: The web kit log type.
               
              * INSTRUMENTATION_OUTPUT: The instrumentation type.
               
              * EXERCISER_MONKEY_OUTPUT: For Android, the artifact (log) generated by an Android fuzz test.
               
              * CALABASH_JSON_OUTPUT: The Calabash JSON output type.
               
              * CALABASH_PRETTY_OUTPUT: The Calabash pretty output type.
               
              * CALABASH_STANDARD_OUTPUT: The Calabash standard output type.
               
              * CALABASH_JAVA_XML_OUTPUT: The Calabash Java XML output type.
               
              * AUTOMATION_OUTPUT: The automation output type.
               
              * APPIUM_SERVER_OUTPUT: The Appium server output type.
               
              * APPIUM_JAVA_OUTPUT: The Appium Java output type.
               
              * APPIUM_JAVA_XML_OUTPUT: The Appium Java XML output type.
               
              * APPIUM_PYTHON_OUTPUT: The Appium Python output type.
               
              * APPIUM_PYTHON_XML_OUTPUT: The Appium Python XML output type.
               
              * EXPLORER_EVENT_LOG: The Explorer event log output type.
               
              * EXPLORER_SUMMARY_LOG: The Explorer summary log output type.
               
              * APPLICATION_CRASH_REPORT: The application crash report output type.
               
              * XCTEST_LOG: The XCode test output type.
               

              
            

            - **extension** *(string) --* 

              The artifact's file extension.

              
            

            - **url** *(string) --* 

              The pre-signed Amazon S3 URL that can be used with a corresponding GET request to download the artifact's file.

              
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_device_pools(**kwargs)

    

    Gets information about device pools.

    

    **Request Syntax** 
    ::

      response = client.list_device_pools(
          arn='string',
          type='CURATED'|'PRIVATE',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The project ARN.

      

    
    :type type: string
    :param type: 

      The device pools' type.

       

      Allowed values include:

       

       
      * CURATED: A device pool that is created and managed by AWS Device Farm.
       
      * PRIVATE: A device pool that is created and managed by the device pool developer.
       

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'devicePools': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'description': 'string',
                    'type': 'CURATED'|'PRIVATE',
                    'rules': [
                        {
                            'attribute': 'ARN'|'PLATFORM'|'FORM_FACTOR'|'MANUFACTURER'|'REMOTE_ACCESS_ENABLED',
                            'operator': 'EQUALS'|'LESS_THAN'|'GREATER_THAN'|'IN'|'NOT_IN',
                            'value': 'string'
                        },
                    ]
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list device pools request.

        
        

        - **devicePools** *(list) --* 

          Information about the device pools.

          
          

          - *(dict) --* 

            Represents a collection of device types.

            
            

            - **arn** *(string) --* 

              The device pool's ARN.

              
            

            - **name** *(string) --* 

              The device pool's name.

              
            

            - **description** *(string) --* 

              The device pool's description.

              
            

            - **type** *(string) --* 

              The device pool's type.

               

              Allowed values include:

               

               
              * CURATED: A device pool that is created and managed by AWS Device Farm.
               
              * PRIVATE: A device pool that is created and managed by the device pool developer.
               

              
            

            - **rules** *(list) --* 

              Information about the device pool's rules.

              
              

              - *(dict) --* 

                Represents a condition for a device pool.

                
                

                - **attribute** *(string) --* 

                  The rule's stringified attribute. For example, specify the value as ``"\"abc\""`` .

                   

                  Allowed values include:

                   

                   
                  * ARN: The ARN.
                   
                  * FORM_FACTOR: The form factor (for example, phone or tablet).
                   
                  * MANUFACTURER: The manufacturer.
                   
                  * PLATFORM: The platform (for example, Android or iOS).
                   

                  
                

                - **operator** *(string) --* 

                  The rule's operator.

                   

                   
                  * EQUALS: The equals operator.
                   
                  * GREATER_THAN: The greater-than operator.
                   
                  * IN: The in operator.
                   
                  * LESS_THAN: The less-than operator.
                   
                  * NOT_IN: The not-in operator.
                   

                  
                

                - **value** *(string) --* 

                  The rule's value.

                  
            
          
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_devices(**kwargs)

    

    Gets information about unique device types.

    

    **Request Syntax** 
    ::

      response = client.list_devices(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: 

      The device types' ARNs.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'devices': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'manufacturer': 'string',
                    'model': 'string',
                    'formFactor': 'PHONE'|'TABLET',
                    'platform': 'ANDROID'|'IOS',
                    'os': 'string',
                    'cpu': {
                        'frequency': 'string',
                        'architecture': 'string',
                        'clock': 123.0
                    },
                    'resolution': {
                        'width': 123,
                        'height': 123
                    },
                    'heapSize': 123,
                    'memory': 123,
                    'image': 'string',
                    'carrier': 'string',
                    'radio': 'string',
                    'remoteAccessEnabled': True|False,
                    'fleetType': 'string',
                    'fleetName': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list devices operation.

        
        

        - **devices** *(list) --* 

          Information about the devices.

          
          

          - *(dict) --* 

            Represents a device type that an app is tested against.

            
            

            - **arn** *(string) --* 

              The device's ARN.

              
            

            - **name** *(string) --* 

              The device's display name.

              
            

            - **manufacturer** *(string) --* 

              The device's manufacturer name.

              
            

            - **model** *(string) --* 

              The device's model name.

              
            

            - **formFactor** *(string) --* 

              The device's form factor.

               

              Allowed values include:

               

               
              * PHONE: The phone form factor.
               
              * TABLET: The tablet form factor.
               

              
            

            - **platform** *(string) --* 

              The device's platform.

               

              Allowed values include:

               

               
              * ANDROID: The Android platform.
               
              * IOS: The iOS platform.
               

              
            

            - **os** *(string) --* 

              The device's operating system type.

              
            

            - **cpu** *(dict) --* 

              Information about the device's CPU.

              
              

              - **frequency** *(string) --* 

                The CPU's frequency.

                
              

              - **architecture** *(string) --* 

                The CPU's architecture, for example x86 or ARM.

                
              

              - **clock** *(float) --* 

                The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                
          
            

            - **resolution** *(dict) --* 

              Represents the screen resolution of a device in height and width, expressed in pixels.

              
              

              - **width** *(integer) --* 

                The screen resolution's width, expressed in pixels.

                
              

              - **height** *(integer) --* 

                The screen resolution's height, expressed in pixels.

                
          
            

            - **heapSize** *(integer) --* 

              The device's heap size, expressed in bytes.

              
            

            - **memory** *(integer) --* 

              The device's total memory size, expressed in bytes.

              
            

            - **image** *(string) --* 

              The device's image name.

              
            

            - **carrier** *(string) --* 

              The device's carrier.

              
            

            - **radio** *(string) --* 

              The device's radio.

              
            

            - **remoteAccessEnabled** *(boolean) --* 

              Specifies whether remote access has been enabled for the specified device.

              
            

            - **fleetType** *(string) --* 

              The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

              
            

            - **fleetName** *(string) --* 

              The name of the fleet to which this device belongs.

              
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_jobs(**kwargs)

    

    Gets information about jobs.

    

    **Request Syntax** 
    ::

      response = client.list_jobs(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The jobs' ARNs.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'jobs': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                    'created': datetime(2015, 1, 1),
                    'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                    'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                    'started': datetime(2015, 1, 1),
                    'stopped': datetime(2015, 1, 1),
                    'counters': {
                        'total': 123,
                        'passed': 123,
                        'failed': 123,
                        'warned': 123,
                        'errored': 123,
                        'stopped': 123,
                        'skipped': 123
                    },
                    'message': 'string',
                    'device': {
                        'arn': 'string',
                        'name': 'string',
                        'manufacturer': 'string',
                        'model': 'string',
                        'formFactor': 'PHONE'|'TABLET',
                        'platform': 'ANDROID'|'IOS',
                        'os': 'string',
                        'cpu': {
                            'frequency': 'string',
                            'architecture': 'string',
                            'clock': 123.0
                        },
                        'resolution': {
                            'width': 123,
                            'height': 123
                        },
                        'heapSize': 123,
                        'memory': 123,
                        'image': 'string',
                        'carrier': 'string',
                        'radio': 'string',
                        'remoteAccessEnabled': True|False,
                        'fleetType': 'string',
                        'fleetName': 'string'
                    },
                    'deviceMinutes': {
                        'total': 123.0,
                        'metered': 123.0,
                        'unmetered': 123.0
                    }
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list jobs request.

        
        

        - **jobs** *(list) --* 

          Information about the jobs.

          
          

          - *(dict) --* 

            Represents a device.

            
            

            - **arn** *(string) --* 

              The job's ARN.

              
            

            - **name** *(string) --* 

              The job's name.

              
            

            - **type** *(string) --* 

              The job's type.

               

              Allowed values include the following:

               

               
              * BUILTIN_FUZZ: The built-in fuzz type.
               
              * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
               
              * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
               
              * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
               
              * APPIUM_PYTHON: The Appium Python type.
               
              * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
               
              * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
               
              * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
               
              * CALABASH: The Calabash type.
               
              * INSTRUMENTATION: The Instrumentation type.
               
              * UIAUTOMATION: The uiautomation type.
               
              * UIAUTOMATOR: The uiautomator type.
               
              * XCTEST: The XCode test type.
               
              * XCTEST_UI: The XCode UI test type.
               

              
            

            - **created** *(datetime) --* 

              When the job was created.

              
            

            - **status** *(string) --* 

              The job's status.

               

              Allowed values include:

               

               
              * PENDING: A pending status.
               
              * PENDING_CONCURRENCY: A pending concurrency status.
               
              * PENDING_DEVICE: A pending device status.
               
              * PROCESSING: A processing status.
               
              * SCHEDULING: A scheduling status.
               
              * PREPARING: A preparing status.
               
              * RUNNING: A running status.
               
              * COMPLETED: A completed status.
               
              * STOPPING: A stopping status.
               

              
            

            - **result** *(string) --* 

              The job's result.

               

              Allowed values include:

               

               
              * PENDING: A pending condition.
               
              * PASSED: A passing condition.
               
              * WARNED: A warning condition.
               
              * FAILED: A failed condition.
               
              * SKIPPED: A skipped condition.
               
              * ERRORED: An error condition.
               
              * STOPPED: A stopped condition.
               

              
            

            - **started** *(datetime) --* 

              The job's start time.

              
            

            - **stopped** *(datetime) --* 

              The job's stop time.

              
            

            - **counters** *(dict) --* 

              The job's result counters.

              
              

              - **total** *(integer) --* 

                The total number of entities.

                
              

              - **passed** *(integer) --* 

                The number of passed entities.

                
              

              - **failed** *(integer) --* 

                The number of failed entities.

                
              

              - **warned** *(integer) --* 

                The number of warned entities.

                
              

              - **errored** *(integer) --* 

                The number of errored entities.

                
              

              - **stopped** *(integer) --* 

                The number of stopped entities.

                
              

              - **skipped** *(integer) --* 

                The number of skipped entities.

                
          
            

            - **message** *(string) --* 

              A message about the job's result.

              
            

            - **device** *(dict) --* 

              Represents a device type that an app is tested against.

              
              

              - **arn** *(string) --* 

                The device's ARN.

                
              

              - **name** *(string) --* 

                The device's display name.

                
              

              - **manufacturer** *(string) --* 

                The device's manufacturer name.

                
              

              - **model** *(string) --* 

                The device's model name.

                
              

              - **formFactor** *(string) --* 

                The device's form factor.

                 

                Allowed values include:

                 

                 
                * PHONE: The phone form factor.
                 
                * TABLET: The tablet form factor.
                 

                
              

              - **platform** *(string) --* 

                The device's platform.

                 

                Allowed values include:

                 

                 
                * ANDROID: The Android platform.
                 
                * IOS: The iOS platform.
                 

                
              

              - **os** *(string) --* 

                The device's operating system type.

                
              

              - **cpu** *(dict) --* 

                Information about the device's CPU.

                
                

                - **frequency** *(string) --* 

                  The CPU's frequency.

                  
                

                - **architecture** *(string) --* 

                  The CPU's architecture, for example x86 or ARM.

                  
                

                - **clock** *(float) --* 

                  The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                  
            
              

              - **resolution** *(dict) --* 

                Represents the screen resolution of a device in height and width, expressed in pixels.

                
                

                - **width** *(integer) --* 

                  The screen resolution's width, expressed in pixels.

                  
                

                - **height** *(integer) --* 

                  The screen resolution's height, expressed in pixels.

                  
            
              

              - **heapSize** *(integer) --* 

                The device's heap size, expressed in bytes.

                
              

              - **memory** *(integer) --* 

                The device's total memory size, expressed in bytes.

                
              

              - **image** *(string) --* 

                The device's image name.

                
              

              - **carrier** *(string) --* 

                The device's carrier.

                
              

              - **radio** *(string) --* 

                The device's radio.

                
              

              - **remoteAccessEnabled** *(boolean) --* 

                Specifies whether remote access has been enabled for the specified device.

                
              

              - **fleetType** *(string) --* 

                The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

                
              

              - **fleetName** *(string) --* 

                The name of the fleet to which this device belongs.

                
          
            

            - **deviceMinutes** *(dict) --* 

              Represents the total (metered or unmetered) minutes used by the job.

              
              

              - **total** *(float) --* 

                When specified, represents the total minutes used by the resource to run tests.

                
              

              - **metered** *(float) --* 

                When specified, represents only the sum of metered minutes used by the resource to run tests.

                
              

              - **unmetered** *(float) --* 

                When specified, represents only the sum of unmetered minutes used by the resource to run tests.

                
          
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_offering_transactions(**kwargs)

    

    Returns a list of all historical purchases, renewals, and system renewal transactions for an AWS account. The list is paginated and ordered by a descending timestamp (most recent transactions are first). The API returns a ``NotEligible`` error if the user is not permitted to invoke the operation. Please contact `aws-devicefarm-support@amazon.com`_ if you believe that you should be able to invoke this operation.

    

    **Request Syntax** 
    ::

      response = client.list_offering_transactions(
          nextToken='string'
      )
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'offeringTransactions': [
                {
                    'offeringStatus': {
                        'type': 'PURCHASE'|'RENEW'|'SYSTEM',
                        'offering': {
                            'id': 'string',
                            'description': 'string',
                            'type': 'RECURRING',
                            'platform': 'ANDROID'|'IOS',
                            'recurringCharges': [
                                {
                                    'cost': {
                                        'amount': 123.0,
                                        'currencyCode': 'USD'
                                    },
                                    'frequency': 'MONTHLY'
                                },
                            ]
                        },
                        'quantity': 123,
                        'effectiveOn': datetime(2015, 1, 1)
                    },
                    'transactionId': 'string',
                    'createdOn': datetime(2015, 1, 1),
                    'cost': {
                        'amount': 123.0,
                        'currencyCode': 'USD'
                    }
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Returns the transaction log of the specified offerings.

        
        

        - **offeringTransactions** *(list) --* 

          The audit log of subscriptions you have purchased and modified through AWS Device Farm.

          
          

          - *(dict) --* 

            Represents the metadata of an offering transaction.

            
            

            - **offeringStatus** *(dict) --* 

              The status of an offering transaction.

              
              

              - **type** *(string) --* 

                The type specified for the offering status.

                
              

              - **offering** *(dict) --* 

                Represents the metadata of an offering status.

                
                

                - **id** *(string) --* 

                  The ID that corresponds to a device offering.

                  
                

                - **description** *(string) --* 

                  A string describing the offering.

                  
                

                - **type** *(string) --* 

                  The type of offering (e.g., "RECURRING") for a device.

                  
                

                - **platform** *(string) --* 

                  The platform of the device (e.g., ANDROID or IOS).

                  
                

                - **recurringCharges** *(list) --* 

                  Specifies whether there are recurring charges for the offering.

                  
                  

                  - *(dict) --* 

                    Specifies whether charges for devices will be recurring.

                    
                    

                    - **cost** *(dict) --* 

                      The cost of the recurring charge.

                      
                      

                      - **amount** *(float) --* 

                        The numerical amount of an offering or transaction.

                        
                      

                      - **currencyCode** *(string) --* 

                        The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

                        
                  
                    

                    - **frequency** *(string) --* 

                      The frequency in which charges will recur.

                      
                
              
            
              

              - **quantity** *(integer) --* 

                The number of available devices in the offering.

                
              

              - **effectiveOn** *(datetime) --* 

                The date on which the offering is effective.

                
          
            

            - **transactionId** *(string) --* 

              The transaction ID of the offering transaction.

              
            

            - **createdOn** *(datetime) --* 

              The date on which an offering transaction was created.

              
            

            - **cost** *(dict) --* 

              The cost of an offering transaction.

              
              

              - **amount** *(float) --* 

                The numerical amount of an offering or transaction.

                
              

              - **currencyCode** *(string) --* 

                The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

                
          
        
      
        

        - **nextToken** *(string) --* 

          An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

          
    

  .. py:method:: list_offerings(**kwargs)

    

    Returns a list of products or offerings that the user can manage through the API. Each offering record indicates the recurring price per unit and the frequency for that offering. The API returns a ``NotEligible`` error if the user is not permitted to invoke the operation. Please contact `aws-devicefarm-support@amazon.com`_ if you believe that you should be able to invoke this operation.

    

    **Request Syntax** 
    ::

      response = client.list_offerings(
          nextToken='string'
      )
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'offerings': [
                {
                    'id': 'string',
                    'description': 'string',
                    'type': 'RECURRING',
                    'platform': 'ANDROID'|'IOS',
                    'recurringCharges': [
                        {
                            'cost': {
                                'amount': 123.0,
                                'currencyCode': 'USD'
                            },
                            'frequency': 'MONTHLY'
                        },
                    ]
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the return values of the list of offerings.

        
        

        - **offerings** *(list) --* 

          A value representing the list offering results.

          
          

          - *(dict) --* 

            Represents the metadata of a device offering.

            
            

            - **id** *(string) --* 

              The ID that corresponds to a device offering.

              
            

            - **description** *(string) --* 

              A string describing the offering.

              
            

            - **type** *(string) --* 

              The type of offering (e.g., "RECURRING") for a device.

              
            

            - **platform** *(string) --* 

              The platform of the device (e.g., ANDROID or IOS).

              
            

            - **recurringCharges** *(list) --* 

              Specifies whether there are recurring charges for the offering.

              
              

              - *(dict) --* 

                Specifies whether charges for devices will be recurring.

                
                

                - **cost** *(dict) --* 

                  The cost of the recurring charge.

                  
                  

                  - **amount** *(float) --* 

                    The numerical amount of an offering or transaction.

                    
                  

                  - **currencyCode** *(string) --* 

                    The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

                    
              
                

                - **frequency** *(string) --* 

                  The frequency in which charges will recur.

                  
            
          
        
      
        

        - **nextToken** *(string) --* 

          An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

          
    

  .. py:method:: list_projects(**kwargs)

    

    Gets information about projects.

    

    **Request Syntax** 
    ::

      response = client.list_projects(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: 

      The projects' ARNs.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'projects': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'created': datetime(2015, 1, 1)
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list projects request.

        
        

        - **projects** *(list) --* 

          Information about the projects.

          
          

          - *(dict) --* 

            Represents an operating-system neutral workspace for running and managing tests.

            
            

            - **arn** *(string) --* 

              The project's ARN.

              
            

            - **name** *(string) --* 

              The project's name.

              
            

            - **created** *(datetime) --* 

              When the project was created.

              
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_remote_access_sessions(**kwargs)

    

    Returns a list of all currently running remote access sessions.

    

    **Request Syntax** 
    ::

      response = client.list_remote_access_sessions(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the remote access session about which you are requesting information.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'remoteAccessSessions': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'created': datetime(2015, 1, 1),
                    'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                    'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                    'message': 'string',
                    'started': datetime(2015, 1, 1),
                    'stopped': datetime(2015, 1, 1),
                    'device': {
                        'arn': 'string',
                        'name': 'string',
                        'manufacturer': 'string',
                        'model': 'string',
                        'formFactor': 'PHONE'|'TABLET',
                        'platform': 'ANDROID'|'IOS',
                        'os': 'string',
                        'cpu': {
                            'frequency': 'string',
                            'architecture': 'string',
                            'clock': 123.0
                        },
                        'resolution': {
                            'width': 123,
                            'height': 123
                        },
                        'heapSize': 123,
                        'memory': 123,
                        'image': 'string',
                        'carrier': 'string',
                        'radio': 'string',
                        'remoteAccessEnabled': True|False,
                        'fleetType': 'string',
                        'fleetName': 'string'
                    },
                    'billingMethod': 'METERED'|'UNMETERED',
                    'deviceMinutes': {
                        'total': 123.0,
                        'metered': 123.0,
                        'unmetered': 123.0
                    },
                    'endpoint': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server after AWS Device Farm makes a request to return information about the remote access session.

        
        

        - **remoteAccessSessions** *(list) --* 

          A container representing the metadata from the service about each remote access session you are requesting.

          
          

          - *(dict) --* 

            Represents information about the remote access session.

            
            

            - **arn** *(string) --* 

              The Amazon Resource Name (ARN) of the remote access session.

              
            

            - **name** *(string) --* 

              The name of the remote access session.

              
            

            - **created** *(datetime) --* 

              The date and time the remote access session was created.

              
            

            - **status** *(string) --* 

              The status of the remote access session. Can be any of the following:

               

               
              * PENDING: A pending status.
               
              * PENDING_CONCURRENCY: A pending concurrency status.
               
              * PENDING_DEVICE: A pending device status.
               
              * PROCESSING: A processing status.
               
              * SCHEDULING: A scheduling status.
               
              * PREPARING: A preparing status.
               
              * RUNNING: A running status.
               
              * COMPLETED: A completed status.
               
              * STOPPING: A stopping status.
               

              
            

            - **result** *(string) --* 

              The result of the remote access session. Can be any of the following:

               

               
              * PENDING: A pending condition.
               
              * PASSED: A passing condition.
               
              * WARNED: A warning condition.
               
              * FAILED: A failed condition.
               
              * SKIPPED: A skipped condition.
               
              * ERRORED: An error condition.
               
              * STOPPED: A stopped condition.
               

              
            

            - **message** *(string) --* 

              A message about the remote access session.

              
            

            - **started** *(datetime) --* 

              The date and time the remote access session was started.

              
            

            - **stopped** *(datetime) --* 

              The date and time the remote access session was stopped.

              
            

            - **device** *(dict) --* 

              Represents a device type that an app is tested against.

              
              

              - **arn** *(string) --* 

                The device's ARN.

                
              

              - **name** *(string) --* 

                The device's display name.

                
              

              - **manufacturer** *(string) --* 

                The device's manufacturer name.

                
              

              - **model** *(string) --* 

                The device's model name.

                
              

              - **formFactor** *(string) --* 

                The device's form factor.

                 

                Allowed values include:

                 

                 
                * PHONE: The phone form factor.
                 
                * TABLET: The tablet form factor.
                 

                
              

              - **platform** *(string) --* 

                The device's platform.

                 

                Allowed values include:

                 

                 
                * ANDROID: The Android platform.
                 
                * IOS: The iOS platform.
                 

                
              

              - **os** *(string) --* 

                The device's operating system type.

                
              

              - **cpu** *(dict) --* 

                Information about the device's CPU.

                
                

                - **frequency** *(string) --* 

                  The CPU's frequency.

                  
                

                - **architecture** *(string) --* 

                  The CPU's architecture, for example x86 or ARM.

                  
                

                - **clock** *(float) --* 

                  The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                  
            
              

              - **resolution** *(dict) --* 

                Represents the screen resolution of a device in height and width, expressed in pixels.

                
                

                - **width** *(integer) --* 

                  The screen resolution's width, expressed in pixels.

                  
                

                - **height** *(integer) --* 

                  The screen resolution's height, expressed in pixels.

                  
            
              

              - **heapSize** *(integer) --* 

                The device's heap size, expressed in bytes.

                
              

              - **memory** *(integer) --* 

                The device's total memory size, expressed in bytes.

                
              

              - **image** *(string) --* 

                The device's image name.

                
              

              - **carrier** *(string) --* 

                The device's carrier.

                
              

              - **radio** *(string) --* 

                The device's radio.

                
              

              - **remoteAccessEnabled** *(boolean) --* 

                Specifies whether remote access has been enabled for the specified device.

                
              

              - **fleetType** *(string) --* 

                The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

                
              

              - **fleetName** *(string) --* 

                The name of the fleet to which this device belongs.

                
          
            

            - **billingMethod** *(string) --* 

              The billing method of the remote access session. Possible values include ``METERED`` or ``UNMETERED`` . For more information about metered devices, see `AWS Device Farm terminology`_ ."

              
            

            - **deviceMinutes** *(dict) --* 

              Represents the total (metered or unmetered) minutes used by the resource to run tests. Contains the sum of minutes consumed by all children.

              
              

              - **total** *(float) --* 

                When specified, represents the total minutes used by the resource to run tests.

                
              

              - **metered** *(float) --* 

                When specified, represents only the sum of metered minutes used by the resource to run tests.

                
              

              - **unmetered** *(float) --* 

                When specified, represents only the sum of unmetered minutes used by the resource to run tests.

                
          
            

            - **endpoint** *(string) --* 

              The endpoint for the remote access sesssion.

              
        
      
        

        - **nextToken** *(string) --* 

          An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

          
    

  .. py:method:: list_runs(**kwargs)

    

    Gets information about runs.

    

    **Request Syntax** 
    ::

      response = client.list_runs(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The runs' ARNs.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'runs': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                    'platform': 'ANDROID'|'IOS',
                    'created': datetime(2015, 1, 1),
                    'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                    'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                    'started': datetime(2015, 1, 1),
                    'stopped': datetime(2015, 1, 1),
                    'counters': {
                        'total': 123,
                        'passed': 123,
                        'failed': 123,
                        'warned': 123,
                        'errored': 123,
                        'stopped': 123,
                        'skipped': 123
                    },
                    'message': 'string',
                    'totalJobs': 123,
                    'completedJobs': 123,
                    'billingMethod': 'METERED'|'UNMETERED',
                    'deviceMinutes': {
                        'total': 123.0,
                        'metered': 123.0,
                        'unmetered': 123.0
                    }
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list runs request.

        
        

        - **runs** *(list) --* 

          Information about the runs.

          
          

          - *(dict) --* 

            Represents an app on a set of devices with a specific test and configuration.

            
            

            - **arn** *(string) --* 

              The run's ARN.

              
            

            - **name** *(string) --* 

              The run's name.

              
            

            - **type** *(string) --* 

              The run's type.

               

              Must be one of the following values:

               

               
              * BUILTIN_FUZZ: The built-in fuzz type.
               
              * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
               
              * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
               
              * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
               
              * APPIUM_PYTHON: The Appium Python type.
               
              * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
               
              * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
               
              * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
               
              * CALABASH: The Calabash type.
               
              * INSTRUMENTATION: The Instrumentation type.
               
              * UIAUTOMATION: The uiautomation type.
               
              * UIAUTOMATOR: The uiautomator type.
               
              * XCTEST: The XCode test type.
               
              * XCTEST_UI: The XCode UI test type.
               

              
            

            - **platform** *(string) --* 

              The run's platform.

               

              Allowed values include:

               

               
              * ANDROID: The Android platform.
               
              * IOS: The iOS platform.
               

              
            

            - **created** *(datetime) --* 

              When the run was created.

              
            

            - **status** *(string) --* 

              The run's status.

               

              Allowed values include:

               

               
              * PENDING: A pending status.
               
              * PENDING_CONCURRENCY: A pending concurrency status.
               
              * PENDING_DEVICE: A pending device status.
               
              * PROCESSING: A processing status.
               
              * SCHEDULING: A scheduling status.
               
              * PREPARING: A preparing status.
               
              * RUNNING: A running status.
               
              * COMPLETED: A completed status.
               
              * STOPPING: A stopping status.
               

              
            

            - **result** *(string) --* 

              The run's result.

               

              Allowed values include:

               

               
              * PENDING: A pending condition.
               
              * PASSED: A passing condition.
               
              * WARNED: A warning condition.
               
              * FAILED: A failed condition.
               
              * SKIPPED: A skipped condition.
               
              * ERRORED: An error condition.
               
              * STOPPED: A stopped condition.
               

              
            

            - **started** *(datetime) --* 

              The run's start time.

              
            

            - **stopped** *(datetime) --* 

              The run's stop time.

              
            

            - **counters** *(dict) --* 

              The run's result counters.

              
              

              - **total** *(integer) --* 

                The total number of entities.

                
              

              - **passed** *(integer) --* 

                The number of passed entities.

                
              

              - **failed** *(integer) --* 

                The number of failed entities.

                
              

              - **warned** *(integer) --* 

                The number of warned entities.

                
              

              - **errored** *(integer) --* 

                The number of errored entities.

                
              

              - **stopped** *(integer) --* 

                The number of stopped entities.

                
              

              - **skipped** *(integer) --* 

                The number of skipped entities.

                
          
            

            - **message** *(string) --* 

              A message about the run's result.

              
            

            - **totalJobs** *(integer) --* 

              The total number of jobs for the run.

              
            

            - **completedJobs** *(integer) --* 

              The total number of completed jobs.

              
            

            - **billingMethod** *(string) --* 

              Specifies the billing method for a test run: ``metered`` or ``unmetered`` . If the parameter is not specified, the default value is ``unmetered`` .

              
            

            - **deviceMinutes** *(dict) --* 

              Represents the total (metered or unmetered) minutes used by the test run.

              
              

              - **total** *(float) --* 

                When specified, represents the total minutes used by the resource to run tests.

                
              

              - **metered** *(float) --* 

                When specified, represents only the sum of metered minutes used by the resource to run tests.

                
              

              - **unmetered** *(float) --* 

                When specified, represents only the sum of unmetered minutes used by the resource to run tests.

                
          
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_samples(**kwargs)

    

    Gets information about samples.

    

    **Request Syntax** 
    ::

      response = client.list_samples(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The samples' ARNs.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'samples': [
                {
                    'arn': 'string',
                    'type': 'CPU'|'MEMORY'|'THREADS'|'RX_RATE'|'TX_RATE'|'RX'|'TX'|'NATIVE_FRAMES'|'NATIVE_FPS'|'NATIVE_MIN_DRAWTIME'|'NATIVE_AVG_DRAWTIME'|'NATIVE_MAX_DRAWTIME'|'OPENGL_FRAMES'|'OPENGL_FPS'|'OPENGL_MIN_DRAWTIME'|'OPENGL_AVG_DRAWTIME'|'OPENGL_MAX_DRAWTIME',
                    'url': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list samples request.

        
        

        - **samples** *(list) --* 

          Information about the samples.

          
          

          - *(dict) --* 

            Represents a sample of performance data.

            
            

            - **arn** *(string) --* 

              The sample's ARN.

              
            

            - **type** *(string) --* 

              The sample's type.

               

              Must be one of the following values:

               

               
              * CPU: A CPU sample type. This is expressed as the app processing CPU time (including child processes) as reported by process, as a percentage.
               
              * MEMORY: A memory usage sample type. This is expressed as the total proportional set size of an app process, in kilobytes.
               
              * NATIVE_AVG_DRAWTIME
               
              * NATIVE_FPS
               
              * NATIVE_FRAMES
               
              * NATIVE_MAX_DRAWTIME
               
              * NATIVE_MIN_DRAWTIME
               
              * OPENGL_AVG_DRAWTIME
               
              * OPENGL_FPS
               
              * OPENGL_FRAMES
               
              * OPENGL_MAX_DRAWTIME
               
              * OPENGL_MIN_DRAWTIME
               
              * RX
               
              * RX_RATE: The total number of bytes per second (TCP and UDP) that are sent, by app process.
               
              * THREADS: A threads sample type. This is expressed as the total number of threads per app process.
               
              * TX
               
              * TX_RATE: The total number of bytes per second (TCP and UDP) that are received, by app process.
               

              
            

            - **url** *(string) --* 

              The pre-signed Amazon S3 URL that can be used with a corresponding GET request to download the sample's file.

              
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_suites(**kwargs)

    

    Gets information about suites.

    

    **Request Syntax** 
    ::

      response = client.list_suites(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The suites' ARNs.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'suites': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                    'created': datetime(2015, 1, 1),
                    'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                    'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                    'started': datetime(2015, 1, 1),
                    'stopped': datetime(2015, 1, 1),
                    'counters': {
                        'total': 123,
                        'passed': 123,
                        'failed': 123,
                        'warned': 123,
                        'errored': 123,
                        'stopped': 123,
                        'skipped': 123
                    },
                    'message': 'string',
                    'deviceMinutes': {
                        'total': 123.0,
                        'metered': 123.0,
                        'unmetered': 123.0
                    }
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list suites request.

        
        

        - **suites** *(list) --* 

          Information about the suites.

          
          

          - *(dict) --* 

            Represents a collection of one or more tests.

            
            

            - **arn** *(string) --* 

              The suite's ARN.

              
            

            - **name** *(string) --* 

              The suite's name.

              
            

            - **type** *(string) --* 

              The suite's type.

               

              Must be one of the following values:

               

               
              * BUILTIN_FUZZ: The built-in fuzz type.
               
              * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
               
              * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
               
              * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
               
              * APPIUM_PYTHON: The Appium Python type.
               
              * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
               
              * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
               
              * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
               
              * CALABASH: The Calabash type.
               
              * INSTRUMENTATION: The Instrumentation type.
               
              * UIAUTOMATION: The uiautomation type.
               
              * UIAUTOMATOR: The uiautomator type.
               
              * XCTEST: The XCode test type.
               
              * XCTEST_UI: The XCode UI test type.
               

              
            

            - **created** *(datetime) --* 

              When the suite was created.

              
            

            - **status** *(string) --* 

              The suite's status.

               

              Allowed values include:

               

               
              * PENDING: A pending status.
               
              * PENDING_CONCURRENCY: A pending concurrency status.
               
              * PENDING_DEVICE: A pending device status.
               
              * PROCESSING: A processing status.
               
              * SCHEDULING: A scheduling status.
               
              * PREPARING: A preparing status.
               
              * RUNNING: A running status.
               
              * COMPLETED: A completed status.
               
              * STOPPING: A stopping status.
               

              
            

            - **result** *(string) --* 

              The suite's result.

               

              Allowed values include:

               

               
              * PENDING: A pending condition.
               
              * PASSED: A passing condition.
               
              * WARNED: A warning condition.
               
              * FAILED: A failed condition.
               
              * SKIPPED: A skipped condition.
               
              * ERRORED: An error condition.
               
              * STOPPED: A stopped condition.
               

              
            

            - **started** *(datetime) --* 

              The suite's start time.

              
            

            - **stopped** *(datetime) --* 

              The suite's stop time.

              
            

            - **counters** *(dict) --* 

              The suite's result counters.

              
              

              - **total** *(integer) --* 

                The total number of entities.

                
              

              - **passed** *(integer) --* 

                The number of passed entities.

                
              

              - **failed** *(integer) --* 

                The number of failed entities.

                
              

              - **warned** *(integer) --* 

                The number of warned entities.

                
              

              - **errored** *(integer) --* 

                The number of errored entities.

                
              

              - **stopped** *(integer) --* 

                The number of stopped entities.

                
              

              - **skipped** *(integer) --* 

                The number of skipped entities.

                
          
            

            - **message** *(string) --* 

              A message about the suite's result.

              
            

            - **deviceMinutes** *(dict) --* 

              Represents the total (metered or unmetered) minutes used by the test suite.

              
              

              - **total** *(float) --* 

                When specified, represents the total minutes used by the resource to run tests.

                
              

              - **metered** *(float) --* 

                When specified, represents only the sum of metered minutes used by the resource to run tests.

                
              

              - **unmetered** *(float) --* 

                When specified, represents only the sum of unmetered minutes used by the resource to run tests.

                
          
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_tests(**kwargs)

    

    Gets information about tests.

    

    **Request Syntax** 
    ::

      response = client.list_tests(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The tests' ARNs.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'tests': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                    'created': datetime(2015, 1, 1),
                    'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                    'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                    'started': datetime(2015, 1, 1),
                    'stopped': datetime(2015, 1, 1),
                    'counters': {
                        'total': 123,
                        'passed': 123,
                        'failed': 123,
                        'warned': 123,
                        'errored': 123,
                        'stopped': 123,
                        'skipped': 123
                    },
                    'message': 'string',
                    'deviceMinutes': {
                        'total': 123.0,
                        'metered': 123.0,
                        'unmetered': 123.0
                    }
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list tests request.

        
        

        - **tests** *(list) --* 

          Information about the tests.

          
          

          - *(dict) --* 

            Represents a condition that is evaluated.

            
            

            - **arn** *(string) --* 

              The test's ARN.

              
            

            - **name** *(string) --* 

              The test's name.

              
            

            - **type** *(string) --* 

              The test's type.

               

              Must be one of the following values:

               

               
              * BUILTIN_FUZZ: The built-in fuzz type.
               
              * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
               
              * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
               
              * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
               
              * APPIUM_PYTHON: The Appium Python type.
               
              * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
               
              * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
               
              * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
               
              * CALABASH: The Calabash type.
               
              * INSTRUMENTATION: The Instrumentation type.
               
              * UIAUTOMATION: The uiautomation type.
               
              * UIAUTOMATOR: The uiautomator type.
               
              * XCTEST: The XCode test type.
               
              * XCTEST_UI: The XCode UI test type.
               

              
            

            - **created** *(datetime) --* 

              When the test was created.

              
            

            - **status** *(string) --* 

              The test's status.

               

              Allowed values include:

               

               
              * PENDING: A pending status.
               
              * PENDING_CONCURRENCY: A pending concurrency status.
               
              * PENDING_DEVICE: A pending device status.
               
              * PROCESSING: A processing status.
               
              * SCHEDULING: A scheduling status.
               
              * PREPARING: A preparing status.
               
              * RUNNING: A running status.
               
              * COMPLETED: A completed status.
               
              * STOPPING: A stopping status.
               

              
            

            - **result** *(string) --* 

              The test's result.

               

              Allowed values include:

               

               
              * PENDING: A pending condition.
               
              * PASSED: A passing condition.
               
              * WARNED: A warning condition.
               
              * FAILED: A failed condition.
               
              * SKIPPED: A skipped condition.
               
              * ERRORED: An error condition.
               
              * STOPPED: A stopped condition.
               

              
            

            - **started** *(datetime) --* 

              The test's start time.

              
            

            - **stopped** *(datetime) --* 

              The test's stop time.

              
            

            - **counters** *(dict) --* 

              The test's result counters.

              
              

              - **total** *(integer) --* 

                The total number of entities.

                
              

              - **passed** *(integer) --* 

                The number of passed entities.

                
              

              - **failed** *(integer) --* 

                The number of failed entities.

                
              

              - **warned** *(integer) --* 

                The number of warned entities.

                
              

              - **errored** *(integer) --* 

                The number of errored entities.

                
              

              - **stopped** *(integer) --* 

                The number of stopped entities.

                
              

              - **skipped** *(integer) --* 

                The number of skipped entities.

                
          
            

            - **message** *(string) --* 

              A message about the test's result.

              
            

            - **deviceMinutes** *(dict) --* 

              Represents the total (metered or unmetered) minutes used by the test.

              
              

              - **total** *(float) --* 

                When specified, represents the total minutes used by the resource to run tests.

                
              

              - **metered** *(float) --* 

                When specified, represents only the sum of metered minutes used by the resource to run tests.

                
              

              - **unmetered** *(float) --* 

                When specified, represents only the sum of unmetered minutes used by the resource to run tests.

                
          
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_unique_problems(**kwargs)

    

    Gets information about unique problems.

    

    **Request Syntax** 
    ::

      response = client.list_unique_problems(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The unique problems' ARNs.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'uniqueProblems': {
                'string': [
                    {
                        'message': 'string',
                        'problems': [
                            {
                                'run': {
                                    'arn': 'string',
                                    'name': 'string'
                                },
                                'job': {
                                    'arn': 'string',
                                    'name': 'string'
                                },
                                'suite': {
                                    'arn': 'string',
                                    'name': 'string'
                                },
                                'test': {
                                    'arn': 'string',
                                    'name': 'string'
                                },
                                'device': {
                                    'arn': 'string',
                                    'name': 'string',
                                    'manufacturer': 'string',
                                    'model': 'string',
                                    'formFactor': 'PHONE'|'TABLET',
                                    'platform': 'ANDROID'|'IOS',
                                    'os': 'string',
                                    'cpu': {
                                        'frequency': 'string',
                                        'architecture': 'string',
                                        'clock': 123.0
                                    },
                                    'resolution': {
                                        'width': 123,
                                        'height': 123
                                    },
                                    'heapSize': 123,
                                    'memory': 123,
                                    'image': 'string',
                                    'carrier': 'string',
                                    'radio': 'string',
                                    'remoteAccessEnabled': True|False,
                                    'fleetType': 'string',
                                    'fleetName': 'string'
                                },
                                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                                'message': 'string'
                            },
                        ]
                    },
                ]
            },
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list unique problems request.

        
        

        - **uniqueProblems** *(dict) --* 

          Information about the unique problems.

           

          Allowed values include:

           

           
          * PENDING: A pending condition.
           
          * PASSED: A passing condition.
           
          * WARNED: A warning condition.
           
          * FAILED: A failed condition.
           
          * SKIPPED: A skipped condition.
           
          * ERRORED: An error condition.
           
          * STOPPED: A stopped condition.
           

          
          

          - *(string) --* 
            

            - *(list) --* 
              

              - *(dict) --* 

                A collection of one or more problems, grouped by their result.

                
                

                - **message** *(string) --* 

                  A message about the unique problems' result.

                  
                

                - **problems** *(list) --* 

                  Information about the problems.

                  
                  

                  - *(dict) --* 

                    Represents a specific warning or failure.

                    
                    

                    - **run** *(dict) --* 

                      Information about the associated run.

                      
                      

                      - **arn** *(string) --* 

                        The problem detail's ARN.

                        
                      

                      - **name** *(string) --* 

                        The problem detail's name.

                        
                  
                    

                    - **job** *(dict) --* 

                      Information about the associated job.

                      
                      

                      - **arn** *(string) --* 

                        The problem detail's ARN.

                        
                      

                      - **name** *(string) --* 

                        The problem detail's name.

                        
                  
                    

                    - **suite** *(dict) --* 

                      Information about the associated suite.

                      
                      

                      - **arn** *(string) --* 

                        The problem detail's ARN.

                        
                      

                      - **name** *(string) --* 

                        The problem detail's name.

                        
                  
                    

                    - **test** *(dict) --* 

                      Information about the associated test.

                      
                      

                      - **arn** *(string) --* 

                        The problem detail's ARN.

                        
                      

                      - **name** *(string) --* 

                        The problem detail's name.

                        
                  
                    

                    - **device** *(dict) --* 

                      Information about the associated device.

                      
                      

                      - **arn** *(string) --* 

                        The device's ARN.

                        
                      

                      - **name** *(string) --* 

                        The device's display name.

                        
                      

                      - **manufacturer** *(string) --* 

                        The device's manufacturer name.

                        
                      

                      - **model** *(string) --* 

                        The device's model name.

                        
                      

                      - **formFactor** *(string) --* 

                        The device's form factor.

                         

                        Allowed values include:

                         

                         
                        * PHONE: The phone form factor.
                         
                        * TABLET: The tablet form factor.
                         

                        
                      

                      - **platform** *(string) --* 

                        The device's platform.

                         

                        Allowed values include:

                         

                         
                        * ANDROID: The Android platform.
                         
                        * IOS: The iOS platform.
                         

                        
                      

                      - **os** *(string) --* 

                        The device's operating system type.

                        
                      

                      - **cpu** *(dict) --* 

                        Information about the device's CPU.

                        
                        

                        - **frequency** *(string) --* 

                          The CPU's frequency.

                          
                        

                        - **architecture** *(string) --* 

                          The CPU's architecture, for example x86 or ARM.

                          
                        

                        - **clock** *(float) --* 

                          The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                          
                    
                      

                      - **resolution** *(dict) --* 

                        Represents the screen resolution of a device in height and width, expressed in pixels.

                        
                        

                        - **width** *(integer) --* 

                          The screen resolution's width, expressed in pixels.

                          
                        

                        - **height** *(integer) --* 

                          The screen resolution's height, expressed in pixels.

                          
                    
                      

                      - **heapSize** *(integer) --* 

                        The device's heap size, expressed in bytes.

                        
                      

                      - **memory** *(integer) --* 

                        The device's total memory size, expressed in bytes.

                        
                      

                      - **image** *(string) --* 

                        The device's image name.

                        
                      

                      - **carrier** *(string) --* 

                        The device's carrier.

                        
                      

                      - **radio** *(string) --* 

                        The device's radio.

                        
                      

                      - **remoteAccessEnabled** *(boolean) --* 

                        Specifies whether remote access has been enabled for the specified device.

                        
                      

                      - **fleetType** *(string) --* 

                        The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

                        
                      

                      - **fleetName** *(string) --* 

                        The name of the fleet to which this device belongs.

                        
                  
                    

                    - **result** *(string) --* 

                      The problem's result.

                       

                      Allowed values include:

                       

                       
                      * PENDING: A pending condition.
                       
                      * PASSED: A passing condition.
                       
                      * WARNED: A warning condition.
                       
                      * FAILED: A failed condition.
                       
                      * SKIPPED: A skipped condition.
                       
                      * ERRORED: An error condition.
                       
                      * STOPPED: A stopped condition.
                       

                      
                    

                    - **message** *(string) --* 

                      A message about the problem's result.

                      
                
              
            
          
      
    
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: list_uploads(**kwargs)

    

    Gets information about uploads.

    

    **Request Syntax** 
    ::

      response = client.list_uploads(
          arn='string',
          nextToken='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The uploads' ARNs.

      

    
    :type nextToken: string
    :param nextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'uploads': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'created': datetime(2015, 1, 1),
                    'type': 'ANDROID_APP'|'IOS_APP'|'WEB_APP'|'EXTERNAL_DATA'|'APPIUM_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_PYTHON_TEST_PACKAGE'|'APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_WEB_PYTHON_TEST_PACKAGE'|'CALABASH_TEST_PACKAGE'|'INSTRUMENTATION_TEST_PACKAGE'|'UIAUTOMATION_TEST_PACKAGE'|'UIAUTOMATOR_TEST_PACKAGE'|'XCTEST_TEST_PACKAGE'|'XCTEST_UI_TEST_PACKAGE',
                    'status': 'INITIALIZED'|'PROCESSING'|'SUCCEEDED'|'FAILED',
                    'url': 'string',
                    'metadata': 'string',
                    'contentType': 'string',
                    'message': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list uploads request.

        
        

        - **uploads** *(list) --* 

          Information about the uploads.

          
          

          - *(dict) --* 

            An app or a set of one or more tests to upload or that have been uploaded.

            
            

            - **arn** *(string) --* 

              The upload's ARN.

              
            

            - **name** *(string) --* 

              The upload's file name.

              
            

            - **created** *(datetime) --* 

              When the upload was created.

              
            

            - **type** *(string) --* 

              The upload's type.

               

              Must be one of the following values:

               

               
              * ANDROID_APP: An Android upload.
               
              * IOS_APP: An iOS upload.
               
              * WEB_APP: A web appliction upload.
               
              * EXTERNAL_DATA: An external data upload.
               
              * APPIUM_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
               
              * APPIUM_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
               
              * APPIUM_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
               
              * APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
               
              * APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
               
              * APPIUM_WEB_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
               
              * CALABASH_TEST_PACKAGE: A Calabash test package upload.
               
              * INSTRUMENTATION_TEST_PACKAGE: An instrumentation upload.
               
              * UIAUTOMATION_TEST_PACKAGE: A uiautomation test package upload.
               
              * UIAUTOMATOR_TEST_PACKAGE: A uiautomator test package upload.
               
              * XCTEST_TEST_PACKAGE: An XCode test package upload.
               
              * XCTEST_UI_TEST_PACKAGE: An XCode UI test package upload.
               

              
            

            - **status** *(string) --* 

              The upload's status.

               

              Must be one of the following values:

               

               
              * FAILED: A failed status.
               
              * INITIALIZED: An initialized status.
               
              * PROCESSING: A processing status.
               
              * SUCCEEDED: A succeeded status.
               

              
            

            - **url** *(string) --* 

              The pre-signed Amazon S3 URL that was used to store a file through a corresponding PUT request.

              
            

            - **metadata** *(string) --* 

              The upload's metadata. For example, for Android, this contains information that is parsed from the manifest and is displayed in the AWS Device Farm console after the associated app is uploaded.

              
            

            - **contentType** *(string) --* 

              The upload's content type (for example, "application/octet-stream").

              
            

            - **message** *(string) --* 

              A message about the upload's result.

              
        
      
        

        - **nextToken** *(string) --* 

          If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

          
    

  .. py:method:: purchase_offering(**kwargs)

    

    Immediately purchases offerings for an AWS account. Offerings renew with the latest total purchased quantity for an offering, unless the renewal was overridden. The API returns a ``NotEligible`` error if the user is not permitted to invoke the operation. Please contact `aws-devicefarm-support@amazon.com`_ if you believe that you should be able to invoke this operation.

    

    **Request Syntax** 
    ::

      response = client.purchase_offering(
          offeringId='string',
          quantity=123
      )
    :type offeringId: string
    :param offeringId: 

      The ID of the offering.

      

    
    :type quantity: integer
    :param quantity: 

      The number of device slots you wish to purchase in an offering request.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'offeringTransaction': {
                'offeringStatus': {
                    'type': 'PURCHASE'|'RENEW'|'SYSTEM',
                    'offering': {
                        'id': 'string',
                        'description': 'string',
                        'type': 'RECURRING',
                        'platform': 'ANDROID'|'IOS',
                        'recurringCharges': [
                            {
                                'cost': {
                                    'amount': 123.0,
                                    'currencyCode': 'USD'
                                },
                                'frequency': 'MONTHLY'
                            },
                        ]
                    },
                    'quantity': 123,
                    'effectiveOn': datetime(2015, 1, 1)
                },
                'transactionId': 'string',
                'createdOn': datetime(2015, 1, 1),
                'cost': {
                    'amount': 123.0,
                    'currencyCode': 'USD'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of the purchase offering (e.g., success or failure).

        
        

        - **offeringTransaction** *(dict) --* 

          Represents the offering transaction for the purchase result.

          
          

          - **offeringStatus** *(dict) --* 

            The status of an offering transaction.

            
            

            - **type** *(string) --* 

              The type specified for the offering status.

              
            

            - **offering** *(dict) --* 

              Represents the metadata of an offering status.

              
              

              - **id** *(string) --* 

                The ID that corresponds to a device offering.

                
              

              - **description** *(string) --* 

                A string describing the offering.

                
              

              - **type** *(string) --* 

                The type of offering (e.g., "RECURRING") for a device.

                
              

              - **platform** *(string) --* 

                The platform of the device (e.g., ANDROID or IOS).

                
              

              - **recurringCharges** *(list) --* 

                Specifies whether there are recurring charges for the offering.

                
                

                - *(dict) --* 

                  Specifies whether charges for devices will be recurring.

                  
                  

                  - **cost** *(dict) --* 

                    The cost of the recurring charge.

                    
                    

                    - **amount** *(float) --* 

                      The numerical amount of an offering or transaction.

                      
                    

                    - **currencyCode** *(string) --* 

                      The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

                      
                
                  

                  - **frequency** *(string) --* 

                    The frequency in which charges will recur.

                    
              
            
          
            

            - **quantity** *(integer) --* 

              The number of available devices in the offering.

              
            

            - **effectiveOn** *(datetime) --* 

              The date on which the offering is effective.

              
        
          

          - **transactionId** *(string) --* 

            The transaction ID of the offering transaction.

            
          

          - **createdOn** *(datetime) --* 

            The date on which an offering transaction was created.

            
          

          - **cost** *(dict) --* 

            The cost of an offering transaction.

            
            

            - **amount** *(float) --* 

              The numerical amount of an offering or transaction.

              
            

            - **currencyCode** *(string) --* 

              The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

              
        
      
    

  .. py:method:: renew_offering(**kwargs)

    

    Explicitly sets the quantity of devices to renew for an offering, starting from the ``effectiveDate`` of the next period. The API returns a ``NotEligible`` error if the user is not permitted to invoke the operation. Please contact `aws-devicefarm-support@amazon.com`_ if you believe that you should be able to invoke this operation.

    

    **Request Syntax** 
    ::

      response = client.renew_offering(
          offeringId='string',
          quantity=123
      )
    :type offeringId: string
    :param offeringId: 

      The ID of a request to renew an offering.

      

    
    :type quantity: integer
    :param quantity: 

      The quantity requested in an offering renewal.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'offeringTransaction': {
                'offeringStatus': {
                    'type': 'PURCHASE'|'RENEW'|'SYSTEM',
                    'offering': {
                        'id': 'string',
                        'description': 'string',
                        'type': 'RECURRING',
                        'platform': 'ANDROID'|'IOS',
                        'recurringCharges': [
                            {
                                'cost': {
                                    'amount': 123.0,
                                    'currencyCode': 'USD'
                                },
                                'frequency': 'MONTHLY'
                            },
                        ]
                    },
                    'quantity': 123,
                    'effectiveOn': datetime(2015, 1, 1)
                },
                'transactionId': 'string',
                'createdOn': datetime(2015, 1, 1),
                'cost': {
                    'amount': 123.0,
                    'currencyCode': 'USD'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The result of a renewal offering.

        
        

        - **offeringTransaction** *(dict) --* 

          Represents the status of the offering transaction for the renewal.

          
          

          - **offeringStatus** *(dict) --* 

            The status of an offering transaction.

            
            

            - **type** *(string) --* 

              The type specified for the offering status.

              
            

            - **offering** *(dict) --* 

              Represents the metadata of an offering status.

              
              

              - **id** *(string) --* 

                The ID that corresponds to a device offering.

                
              

              - **description** *(string) --* 

                A string describing the offering.

                
              

              - **type** *(string) --* 

                The type of offering (e.g., "RECURRING") for a device.

                
              

              - **platform** *(string) --* 

                The platform of the device (e.g., ANDROID or IOS).

                
              

              - **recurringCharges** *(list) --* 

                Specifies whether there are recurring charges for the offering.

                
                

                - *(dict) --* 

                  Specifies whether charges for devices will be recurring.

                  
                  

                  - **cost** *(dict) --* 

                    The cost of the recurring charge.

                    
                    

                    - **amount** *(float) --* 

                      The numerical amount of an offering or transaction.

                      
                    

                    - **currencyCode** *(string) --* 

                      The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

                      
                
                  

                  - **frequency** *(string) --* 

                    The frequency in which charges will recur.

                    
              
            
          
            

            - **quantity** *(integer) --* 

              The number of available devices in the offering.

              
            

            - **effectiveOn** *(datetime) --* 

              The date on which the offering is effective.

              
        
          

          - **transactionId** *(string) --* 

            The transaction ID of the offering transaction.

            
          

          - **createdOn** *(datetime) --* 

            The date on which an offering transaction was created.

            
          

          - **cost** *(dict) --* 

            The cost of an offering transaction.

            
            

            - **amount** *(float) --* 

              The numerical amount of an offering or transaction.

              
            

            - **currencyCode** *(string) --* 

              The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

              
        
      
    

  .. py:method:: schedule_run(**kwargs)

    

    Schedules a run.

    

    **Request Syntax** 
    ::

      response = client.schedule_run(
          projectArn='string',
          appArn='string',
          devicePoolArn='string',
          name='string',
          test={
              'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
              'testPackageArn': 'string',
              'filter': 'string',
              'parameters': {
                  'string': 'string'
              }
          },
          configuration={
              'extraDataPackageArn': 'string',
              'networkProfileArn': 'string',
              'locale': 'string',
              'location': {
                  'latitude': 123.0,
                  'longitude': 123.0
              },
              'radios': {
                  'wifi': True|False,
                  'bluetooth': True|False,
                  'nfc': True|False,
                  'gps': True|False
              },
              'auxiliaryApps': [
                  'string',
              ],
              'billingMethod': 'METERED'|'UNMETERED'
          }
      )
    :type projectArn: string
    :param projectArn: **[REQUIRED]** 

      The ARN of the project for the run to be scheduled.

      

    
    :type appArn: string
    :param appArn: 

      The ARN of the app to schedule a run.

      

    
    :type devicePoolArn: string
    :param devicePoolArn: **[REQUIRED]** 

      The ARN of the device pool for the run to be scheduled.

      

    
    :type name: string
    :param name: 

      The name for the run to be scheduled.

      

    
    :type test: dict
    :param test: **[REQUIRED]** 

      Information about the test for the run to be scheduled.

      

    
      - **type** *(string) --* **[REQUIRED]** 

        The test's type.

         

        Must be one of the following values:

         

         
        * BUILTIN_FUZZ: The built-in fuzz type.
         
        * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
         
        * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
         
        * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
         
        * APPIUM_PYTHON: The Appium Python type.
         
        * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
         
        * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
         
        * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
         
        * CALABASH: The Calabash type.
         
        * INSTRUMENTATION: The Instrumentation type.
         
        * UIAUTOMATION: The uiautomation type.
         
        * UIAUTOMATOR: The uiautomator type.
         
        * XCTEST: The XCode test type.
         
        * XCTEST_UI: The XCode UI test type.
         

        

      
      - **testPackageArn** *(string) --* 

        The ARN of the uploaded test that will be run.

        

      
      - **filter** *(string) --* 

        The test's filter.

        

      
      - **parameters** *(dict) --* 

        The test's parameters, such as test framework parameters and fixture settings.

        

      
        - *(string) --* 

        
          - *(string) --* 

          
    
  
    
    :type configuration: dict
    :param configuration: 

      Information about the settings for the run to be scheduled.

      

    
      - **extraDataPackageArn** *(string) --* 

        The ARN of the extra data for the run. The extra data is a .zip file that AWS Device Farm will extract to external data for Android or the app's sandbox for iOS.

        

      
      - **networkProfileArn** *(string) --* 

        Reserved for internal use.

        

      
      - **locale** *(string) --* 

        Information about the locale that is used for the run.

        

      
      - **location** *(dict) --* 

        Information about the location that is used for the run.

        

      
        - **latitude** *(float) --* **[REQUIRED]** 

          The latitude.

          

        
        - **longitude** *(float) --* **[REQUIRED]** 

          The longitude.

          

        
      
      - **radios** *(dict) --* 

        Information about the radio states for the run.

        

      
        - **wifi** *(boolean) --* 

          True if Wi-Fi is enabled at the beginning of the test; otherwise, false.

          

        
        - **bluetooth** *(boolean) --* 

          True if Bluetooth is enabled at the beginning of the test; otherwise, false.

          

        
        - **nfc** *(boolean) --* 

          True if NFC is enabled at the beginning of the test; otherwise, false.

          

        
        - **gps** *(boolean) --* 

          True if GPS is enabled at the beginning of the test; otherwise, false.

          

        
      
      - **auxiliaryApps** *(list) --* 

        A list of auxiliary apps for the run.

        

      
        - *(string) --* 

        
    
      - **billingMethod** *(string) --* 

        Specifies the billing method for a test run: ``metered`` or ``unmetered`` . If the parameter is not specified, the default value is ``unmetered`` .

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'run': {
                'arn': 'string',
                'name': 'string',
                'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                'platform': 'ANDROID'|'IOS',
                'created': datetime(2015, 1, 1),
                'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                'started': datetime(2015, 1, 1),
                'stopped': datetime(2015, 1, 1),
                'counters': {
                    'total': 123,
                    'passed': 123,
                    'failed': 123,
                    'warned': 123,
                    'errored': 123,
                    'stopped': 123,
                    'skipped': 123
                },
                'message': 'string',
                'totalJobs': 123,
                'completedJobs': 123,
                'billingMethod': 'METERED'|'UNMETERED',
                'deviceMinutes': {
                    'total': 123.0,
                    'metered': 123.0,
                    'unmetered': 123.0
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a schedule run request.

        
        

        - **run** *(dict) --* 

          Information about the scheduled run.

          
          

          - **arn** *(string) --* 

            The run's ARN.

            
          

          - **name** *(string) --* 

            The run's name.

            
          

          - **type** *(string) --* 

            The run's type.

             

            Must be one of the following values:

             

             
            * BUILTIN_FUZZ: The built-in fuzz type.
             
            * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
             
            * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
             
            * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
             
            * APPIUM_PYTHON: The Appium Python type.
             
            * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
             
            * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
             
            * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
             
            * CALABASH: The Calabash type.
             
            * INSTRUMENTATION: The Instrumentation type.
             
            * UIAUTOMATION: The uiautomation type.
             
            * UIAUTOMATOR: The uiautomator type.
             
            * XCTEST: The XCode test type.
             
            * XCTEST_UI: The XCode UI test type.
             

            
          

          - **platform** *(string) --* 

            The run's platform.

             

            Allowed values include:

             

             
            * ANDROID: The Android platform.
             
            * IOS: The iOS platform.
             

            
          

          - **created** *(datetime) --* 

            When the run was created.

            
          

          - **status** *(string) --* 

            The run's status.

             

            Allowed values include:

             

             
            * PENDING: A pending status.
             
            * PENDING_CONCURRENCY: A pending concurrency status.
             
            * PENDING_DEVICE: A pending device status.
             
            * PROCESSING: A processing status.
             
            * SCHEDULING: A scheduling status.
             
            * PREPARING: A preparing status.
             
            * RUNNING: A running status.
             
            * COMPLETED: A completed status.
             
            * STOPPING: A stopping status.
             

            
          

          - **result** *(string) --* 

            The run's result.

             

            Allowed values include:

             

             
            * PENDING: A pending condition.
             
            * PASSED: A passing condition.
             
            * WARNED: A warning condition.
             
            * FAILED: A failed condition.
             
            * SKIPPED: A skipped condition.
             
            * ERRORED: An error condition.
             
            * STOPPED: A stopped condition.
             

            
          

          - **started** *(datetime) --* 

            The run's start time.

            
          

          - **stopped** *(datetime) --* 

            The run's stop time.

            
          

          - **counters** *(dict) --* 

            The run's result counters.

            
            

            - **total** *(integer) --* 

              The total number of entities.

              
            

            - **passed** *(integer) --* 

              The number of passed entities.

              
            

            - **failed** *(integer) --* 

              The number of failed entities.

              
            

            - **warned** *(integer) --* 

              The number of warned entities.

              
            

            - **errored** *(integer) --* 

              The number of errored entities.

              
            

            - **stopped** *(integer) --* 

              The number of stopped entities.

              
            

            - **skipped** *(integer) --* 

              The number of skipped entities.

              
        
          

          - **message** *(string) --* 

            A message about the run's result.

            
          

          - **totalJobs** *(integer) --* 

            The total number of jobs for the run.

            
          

          - **completedJobs** *(integer) --* 

            The total number of completed jobs.

            
          

          - **billingMethod** *(string) --* 

            Specifies the billing method for a test run: ``metered`` or ``unmetered`` . If the parameter is not specified, the default value is ``unmetered`` .

            
          

          - **deviceMinutes** *(dict) --* 

            Represents the total (metered or unmetered) minutes used by the test run.

            
            

            - **total** *(float) --* 

              When specified, represents the total minutes used by the resource to run tests.

              
            

            - **metered** *(float) --* 

              When specified, represents only the sum of metered minutes used by the resource to run tests.

              
            

            - **unmetered** *(float) --* 

              When specified, represents only the sum of unmetered minutes used by the resource to run tests.

              
        
      
    

  .. py:method:: stop_remote_access_session(**kwargs)

    

    Ends a specified remote access session.

    

    **Request Syntax** 
    ::

      response = client.stop_remote_access_session(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the remote access session you wish to stop.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'remoteAccessSession': {
                'arn': 'string',
                'name': 'string',
                'created': datetime(2015, 1, 1),
                'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                'message': 'string',
                'started': datetime(2015, 1, 1),
                'stopped': datetime(2015, 1, 1),
                'device': {
                    'arn': 'string',
                    'name': 'string',
                    'manufacturer': 'string',
                    'model': 'string',
                    'formFactor': 'PHONE'|'TABLET',
                    'platform': 'ANDROID'|'IOS',
                    'os': 'string',
                    'cpu': {
                        'frequency': 'string',
                        'architecture': 'string',
                        'clock': 123.0
                    },
                    'resolution': {
                        'width': 123,
                        'height': 123
                    },
                    'heapSize': 123,
                    'memory': 123,
                    'image': 'string',
                    'carrier': 'string',
                    'radio': 'string',
                    'remoteAccessEnabled': True|False,
                    'fleetType': 'string',
                    'fleetName': 'string'
                },
                'billingMethod': 'METERED'|'UNMETERED',
                'deviceMinutes': {
                    'total': 123.0,
                    'metered': 123.0,
                    'unmetered': 123.0
                },
                'endpoint': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server that describes the remote access session when AWS Device Farm stops the session.

        
        

        - **remoteAccessSession** *(dict) --* 

          A container representing the metadata from the service about the remote access session you are stopping.

          
          

          - **arn** *(string) --* 

            The Amazon Resource Name (ARN) of the remote access session.

            
          

          - **name** *(string) --* 

            The name of the remote access session.

            
          

          - **created** *(datetime) --* 

            The date and time the remote access session was created.

            
          

          - **status** *(string) --* 

            The status of the remote access session. Can be any of the following:

             

             
            * PENDING: A pending status.
             
            * PENDING_CONCURRENCY: A pending concurrency status.
             
            * PENDING_DEVICE: A pending device status.
             
            * PROCESSING: A processing status.
             
            * SCHEDULING: A scheduling status.
             
            * PREPARING: A preparing status.
             
            * RUNNING: A running status.
             
            * COMPLETED: A completed status.
             
            * STOPPING: A stopping status.
             

            
          

          - **result** *(string) --* 

            The result of the remote access session. Can be any of the following:

             

             
            * PENDING: A pending condition.
             
            * PASSED: A passing condition.
             
            * WARNED: A warning condition.
             
            * FAILED: A failed condition.
             
            * SKIPPED: A skipped condition.
             
            * ERRORED: An error condition.
             
            * STOPPED: A stopped condition.
             

            
          

          - **message** *(string) --* 

            A message about the remote access session.

            
          

          - **started** *(datetime) --* 

            The date and time the remote access session was started.

            
          

          - **stopped** *(datetime) --* 

            The date and time the remote access session was stopped.

            
          

          - **device** *(dict) --* 

            Represents a device type that an app is tested against.

            
            

            - **arn** *(string) --* 

              The device's ARN.

              
            

            - **name** *(string) --* 

              The device's display name.

              
            

            - **manufacturer** *(string) --* 

              The device's manufacturer name.

              
            

            - **model** *(string) --* 

              The device's model name.

              
            

            - **formFactor** *(string) --* 

              The device's form factor.

               

              Allowed values include:

               

               
              * PHONE: The phone form factor.
               
              * TABLET: The tablet form factor.
               

              
            

            - **platform** *(string) --* 

              The device's platform.

               

              Allowed values include:

               

               
              * ANDROID: The Android platform.
               
              * IOS: The iOS platform.
               

              
            

            - **os** *(string) --* 

              The device's operating system type.

              
            

            - **cpu** *(dict) --* 

              Information about the device's CPU.

              
              

              - **frequency** *(string) --* 

                The CPU's frequency.

                
              

              - **architecture** *(string) --* 

                The CPU's architecture, for example x86 or ARM.

                
              

              - **clock** *(float) --* 

                The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                
          
            

            - **resolution** *(dict) --* 

              Represents the screen resolution of a device in height and width, expressed in pixels.

              
              

              - **width** *(integer) --* 

                The screen resolution's width, expressed in pixels.

                
              

              - **height** *(integer) --* 

                The screen resolution's height, expressed in pixels.

                
          
            

            - **heapSize** *(integer) --* 

              The device's heap size, expressed in bytes.

              
            

            - **memory** *(integer) --* 

              The device's total memory size, expressed in bytes.

              
            

            - **image** *(string) --* 

              The device's image name.

              
            

            - **carrier** *(string) --* 

              The device's carrier.

              
            

            - **radio** *(string) --* 

              The device's radio.

              
            

            - **remoteAccessEnabled** *(boolean) --* 

              Specifies whether remote access has been enabled for the specified device.

              
            

            - **fleetType** *(string) --* 

              The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

              
            

            - **fleetName** *(string) --* 

              The name of the fleet to which this device belongs.

              
        
          

          - **billingMethod** *(string) --* 

            The billing method of the remote access session. Possible values include ``METERED`` or ``UNMETERED`` . For more information about metered devices, see `AWS Device Farm terminology`_ ."

            
          

          - **deviceMinutes** *(dict) --* 

            Represents the total (metered or unmetered) minutes used by the resource to run tests. Contains the sum of minutes consumed by all children.

            
            

            - **total** *(float) --* 

              When specified, represents the total minutes used by the resource to run tests.

              
            

            - **metered** *(float) --* 

              When specified, represents only the sum of metered minutes used by the resource to run tests.

              
            

            - **unmetered** *(float) --* 

              When specified, represents only the sum of unmetered minutes used by the resource to run tests.

              
        
          

          - **endpoint** *(string) --* 

            The endpoint for the remote access sesssion.

            
      
    

  .. py:method:: stop_run(**kwargs)

    

    Initiates a stop request for the current test run. AWS Device Farm will immediately stop the run on devices where tests have not started executing, and you will not be billed for these devices. On devices where tests have started executing, Setup Suite and Teardown Suite tests will run to completion before stopping execution on those devices. You will be billed for Setup, Teardown, and any tests that were in progress or already completed.

    

    **Request Syntax** 
    ::

      response = client.stop_run(
          arn='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      Represents the Amazon Resource Name (ARN) of the Device Farm run you wish to stop.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'run': {
                'arn': 'string',
                'name': 'string',
                'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                'platform': 'ANDROID'|'IOS',
                'created': datetime(2015, 1, 1),
                'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                'started': datetime(2015, 1, 1),
                'stopped': datetime(2015, 1, 1),
                'counters': {
                    'total': 123,
                    'passed': 123,
                    'failed': 123,
                    'warned': 123,
                    'errored': 123,
                    'stopped': 123,
                    'skipped': 123
                },
                'message': 'string',
                'totalJobs': 123,
                'completedJobs': 123,
                'billingMethod': 'METERED'|'UNMETERED',
                'deviceMinutes': {
                    'total': 123.0,
                    'metered': 123.0,
                    'unmetered': 123.0
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the results of your stop run attempt.

        
        

        - **run** *(dict) --* 

          Represents an app on a set of devices with a specific test and configuration.

          
          

          - **arn** *(string) --* 

            The run's ARN.

            
          

          - **name** *(string) --* 

            The run's name.

            
          

          - **type** *(string) --* 

            The run's type.

             

            Must be one of the following values:

             

             
            * BUILTIN_FUZZ: The built-in fuzz type.
             
            * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
             
            * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
             
            * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
             
            * APPIUM_PYTHON: The Appium Python type.
             
            * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
             
            * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
             
            * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
             
            * CALABASH: The Calabash type.
             
            * INSTRUMENTATION: The Instrumentation type.
             
            * UIAUTOMATION: The uiautomation type.
             
            * UIAUTOMATOR: The uiautomator type.
             
            * XCTEST: The XCode test type.
             
            * XCTEST_UI: The XCode UI test type.
             

            
          

          - **platform** *(string) --* 

            The run's platform.

             

            Allowed values include:

             

             
            * ANDROID: The Android platform.
             
            * IOS: The iOS platform.
             

            
          

          - **created** *(datetime) --* 

            When the run was created.

            
          

          - **status** *(string) --* 

            The run's status.

             

            Allowed values include:

             

             
            * PENDING: A pending status.
             
            * PENDING_CONCURRENCY: A pending concurrency status.
             
            * PENDING_DEVICE: A pending device status.
             
            * PROCESSING: A processing status.
             
            * SCHEDULING: A scheduling status.
             
            * PREPARING: A preparing status.
             
            * RUNNING: A running status.
             
            * COMPLETED: A completed status.
             
            * STOPPING: A stopping status.
             

            
          

          - **result** *(string) --* 

            The run's result.

             

            Allowed values include:

             

             
            * PENDING: A pending condition.
             
            * PASSED: A passing condition.
             
            * WARNED: A warning condition.
             
            * FAILED: A failed condition.
             
            * SKIPPED: A skipped condition.
             
            * ERRORED: An error condition.
             
            * STOPPED: A stopped condition.
             

            
          

          - **started** *(datetime) --* 

            The run's start time.

            
          

          - **stopped** *(datetime) --* 

            The run's stop time.

            
          

          - **counters** *(dict) --* 

            The run's result counters.

            
            

            - **total** *(integer) --* 

              The total number of entities.

              
            

            - **passed** *(integer) --* 

              The number of passed entities.

              
            

            - **failed** *(integer) --* 

              The number of failed entities.

              
            

            - **warned** *(integer) --* 

              The number of warned entities.

              
            

            - **errored** *(integer) --* 

              The number of errored entities.

              
            

            - **stopped** *(integer) --* 

              The number of stopped entities.

              
            

            - **skipped** *(integer) --* 

              The number of skipped entities.

              
        
          

          - **message** *(string) --* 

            A message about the run's result.

            
          

          - **totalJobs** *(integer) --* 

            The total number of jobs for the run.

            
          

          - **completedJobs** *(integer) --* 

            The total number of completed jobs.

            
          

          - **billingMethod** *(string) --* 

            Specifies the billing method for a test run: ``metered`` or ``unmetered`` . If the parameter is not specified, the default value is ``unmetered`` .

            
          

          - **deviceMinutes** *(dict) --* 

            Represents the total (metered or unmetered) minutes used by the test run.

            
            

            - **total** *(float) --* 

              When specified, represents the total minutes used by the resource to run tests.

              
            

            - **metered** *(float) --* 

              When specified, represents only the sum of metered minutes used by the resource to run tests.

              
            

            - **unmetered** *(float) --* 

              When specified, represents only the sum of unmetered minutes used by the resource to run tests.

              
        
      
    

  .. py:method:: update_device_pool(**kwargs)

    

    Modifies the name, description, and rules in a device pool given the attributes and the pool ARN. Rule updates are all-or-nothing, meaning they can only be updated as a whole (or not at all).

    

    **Request Syntax** 
    ::

      response = client.update_device_pool(
          arn='string',
          name='string',
          description='string',
          rules=[
              {
                  'attribute': 'ARN'|'PLATFORM'|'FORM_FACTOR'|'MANUFACTURER'|'REMOTE_ACCESS_ENABLED',
                  'operator': 'EQUALS'|'LESS_THAN'|'GREATER_THAN'|'IN'|'NOT_IN',
                  'value': 'string'
              },
          ]
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The Amazon Resourc Name (ARN) of the Device Farm device pool you wish to update.

      

    
    :type name: string
    :param name: 

      A string representing the name of the device pool you wish to update.

      

    
    :type description: string
    :param description: 

      A description of the device pool you wish to update.

      

    
    :type rules: list
    :param rules: 

      Represents the rules you wish to modify for the device pool. Updating rules is optional; however, if you choose to update rules for your request, the update will replace the existing rules.

      

    
      - *(dict) --* 

        Represents a condition for a device pool.

        

      
        - **attribute** *(string) --* 

          The rule's stringified attribute. For example, specify the value as ``"\"abc\""`` .

           

          Allowed values include:

           

           
          * ARN: The ARN.
           
          * FORM_FACTOR: The form factor (for example, phone or tablet).
           
          * MANUFACTURER: The manufacturer.
           
          * PLATFORM: The platform (for example, Android or iOS).
           

          

        
        - **operator** *(string) --* 

          The rule's operator.

           

           
          * EQUALS: The equals operator.
           
          * GREATER_THAN: The greater-than operator.
           
          * IN: The in operator.
           
          * LESS_THAN: The less-than operator.
           
          * NOT_IN: The not-in operator.
           

          

        
        - **value** *(string) --* 

          The rule's value.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'devicePool': {
                'arn': 'string',
                'name': 'string',
                'description': 'string',
                'type': 'CURATED'|'PRIVATE',
                'rules': [
                    {
                        'attribute': 'ARN'|'PLATFORM'|'FORM_FACTOR'|'MANUFACTURER'|'REMOTE_ACCESS_ENABLED',
                        'operator': 'EQUALS'|'LESS_THAN'|'GREATER_THAN'|'IN'|'NOT_IN',
                        'value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of an update device pool request.

        
        

        - **devicePool** *(dict) --* 

          Represents a collection of device types.

          
          

          - **arn** *(string) --* 

            The device pool's ARN.

            
          

          - **name** *(string) --* 

            The device pool's name.

            
          

          - **description** *(string) --* 

            The device pool's description.

            
          

          - **type** *(string) --* 

            The device pool's type.

             

            Allowed values include:

             

             
            * CURATED: A device pool that is created and managed by AWS Device Farm.
             
            * PRIVATE: A device pool that is created and managed by the device pool developer.
             

            
          

          - **rules** *(list) --* 

            Information about the device pool's rules.

            
            

            - *(dict) --* 

              Represents a condition for a device pool.

              
              

              - **attribute** *(string) --* 

                The rule's stringified attribute. For example, specify the value as ``"\"abc\""`` .

                 

                Allowed values include:

                 

                 
                * ARN: The ARN.
                 
                * FORM_FACTOR: The form factor (for example, phone or tablet).
                 
                * MANUFACTURER: The manufacturer.
                 
                * PLATFORM: The platform (for example, Android or iOS).
                 

                
              

              - **operator** *(string) --* 

                The rule's operator.

                 

                 
                * EQUALS: The equals operator.
                 
                * GREATER_THAN: The greater-than operator.
                 
                * IN: The in operator.
                 
                * LESS_THAN: The less-than operator.
                 
                * NOT_IN: The not-in operator.
                 

                
              

              - **value** *(string) --* 

                The rule's value.

                
          
        
      
    

  .. py:method:: update_project(**kwargs)

    

    Modifies the specified project name, given the project ARN and a new name.

    

    **Request Syntax** 
    ::

      response = client.update_project(
          arn='string',
          name='string'
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the project whose name you wish to update.

      

    
    :type name: string
    :param name: 

      A string representing the new name of the project that you are updating.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'project': {
                'arn': 'string',
                'name': 'string',
                'created': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of an update project request.

        
        

        - **project** *(dict) --* 

          Represents an operating-system neutral workspace for running and managing tests.

          
          

          - **arn** *(string) --* 

            The project's ARN.

            
          

          - **name** *(string) --* 

            The project's name.

            
          

          - **created** *(datetime) --* 

            When the project was created.

            
      
    

==========
Paginators
==========


The available paginators are:

* :py:class:`DeviceFarm.Paginator.ListArtifacts`


* :py:class:`DeviceFarm.Paginator.ListDevicePools`


* :py:class:`DeviceFarm.Paginator.ListDevices`


* :py:class:`DeviceFarm.Paginator.ListJobs`


* :py:class:`DeviceFarm.Paginator.ListProjects`


* :py:class:`DeviceFarm.Paginator.ListRuns`


* :py:class:`DeviceFarm.Paginator.ListSamples`


* :py:class:`DeviceFarm.Paginator.ListSuites`


* :py:class:`DeviceFarm.Paginator.ListTests`


* :py:class:`DeviceFarm.Paginator.ListUniqueProblems`


* :py:class:`DeviceFarm.Paginator.ListUploads`



.. py:class:: DeviceFarm.Paginator.ListArtifacts

  ::

    
    paginator = client.get_paginator('list_artifacts')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_artifacts`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          type='SCREENSHOT'|'FILE'|'LOG',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The Run, Job, Suite, or Test ARN.

      

    
    :type type: string
    :param type: **[REQUIRED]** 

      The artifacts' type.

       

      Allowed values include:

       

       
      * FILE: The artifacts are files.
       
      * LOG: The artifacts are logs.
       
      * SCREENSHOT: The artifacts are screenshots.
       

      

    
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
            'artifacts': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'UNKNOWN'|'SCREENSHOT'|'DEVICE_LOG'|'MESSAGE_LOG'|'VIDEO_LOG'|'RESULT_LOG'|'SERVICE_LOG'|'WEBKIT_LOG'|'INSTRUMENTATION_OUTPUT'|'EXERCISER_MONKEY_OUTPUT'|'CALABASH_JSON_OUTPUT'|'CALABASH_PRETTY_OUTPUT'|'CALABASH_STANDARD_OUTPUT'|'CALABASH_JAVA_XML_OUTPUT'|'AUTOMATION_OUTPUT'|'APPIUM_SERVER_OUTPUT'|'APPIUM_JAVA_OUTPUT'|'APPIUM_JAVA_XML_OUTPUT'|'APPIUM_PYTHON_OUTPUT'|'APPIUM_PYTHON_XML_OUTPUT'|'EXPLORER_EVENT_LOG'|'EXPLORER_SUMMARY_LOG'|'APPLICATION_CRASH_REPORT'|'XCTEST_LOG'|'VIDEO',
                    'extension': 'string',
                    'url': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list artifacts operation.

        
        

        - **artifacts** *(list) --* 

          Information about the artifacts.

          
          

          - *(dict) --* 

            Represents the output of a test. Examples of artifacts include logs and screenshots.

            
            

            - **arn** *(string) --* 

              The artifact's ARN.

              
            

            - **name** *(string) --* 

              The artifact's name.

              
            

            - **type** *(string) --* 

              The artifact's type.

               

              Allowed values include the following:

               

               
              * UNKNOWN: An unknown type.
               
              * SCREENSHOT: The screenshot type.
               
              * DEVICE_LOG: The device log type.
               
              * MESSAGE_LOG: The message log type.
               
              * RESULT_LOG: The result log type.
               
              * SERVICE_LOG: The service log type.
               
              * WEBKIT_LOG: The web kit log type.
               
              * INSTRUMENTATION_OUTPUT: The instrumentation type.
               
              * EXERCISER_MONKEY_OUTPUT: For Android, the artifact (log) generated by an Android fuzz test.
               
              * CALABASH_JSON_OUTPUT: The Calabash JSON output type.
               
              * CALABASH_PRETTY_OUTPUT: The Calabash pretty output type.
               
              * CALABASH_STANDARD_OUTPUT: The Calabash standard output type.
               
              * CALABASH_JAVA_XML_OUTPUT: The Calabash Java XML output type.
               
              * AUTOMATION_OUTPUT: The automation output type.
               
              * APPIUM_SERVER_OUTPUT: The Appium server output type.
               
              * APPIUM_JAVA_OUTPUT: The Appium Java output type.
               
              * APPIUM_JAVA_XML_OUTPUT: The Appium Java XML output type.
               
              * APPIUM_PYTHON_OUTPUT: The Appium Python output type.
               
              * APPIUM_PYTHON_XML_OUTPUT: The Appium Python XML output type.
               
              * EXPLORER_EVENT_LOG: The Explorer event log output type.
               
              * EXPLORER_SUMMARY_LOG: The Explorer summary log output type.
               
              * APPLICATION_CRASH_REPORT: The application crash report output type.
               
              * XCTEST_LOG: The XCode test output type.
               

              
            

            - **extension** *(string) --* 

              The artifact's file extension.

              
            

            - **url** *(string) --* 

              The pre-signed Amazon S3 URL that can be used with a corresponding GET request to download the artifact's file.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListDevicePools

  ::

    
    paginator = client.get_paginator('list_device_pools')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_device_pools`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          type='CURATED'|'PRIVATE',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The project ARN.

      

    
    :type type: string
    :param type: 

      The device pools' type.

       

      Allowed values include:

       

       
      * CURATED: A device pool that is created and managed by AWS Device Farm.
       
      * PRIVATE: A device pool that is created and managed by the device pool developer.
       

      

    
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
            'devicePools': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'description': 'string',
                    'type': 'CURATED'|'PRIVATE',
                    'rules': [
                        {
                            'attribute': 'ARN'|'PLATFORM'|'FORM_FACTOR'|'MANUFACTURER'|'REMOTE_ACCESS_ENABLED',
                            'operator': 'EQUALS'|'LESS_THAN'|'GREATER_THAN'|'IN'|'NOT_IN',
                            'value': 'string'
                        },
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list device pools request.

        
        

        - **devicePools** *(list) --* 

          Information about the device pools.

          
          

          - *(dict) --* 

            Represents a collection of device types.

            
            

            - **arn** *(string) --* 

              The device pool's ARN.

              
            

            - **name** *(string) --* 

              The device pool's name.

              
            

            - **description** *(string) --* 

              The device pool's description.

              
            

            - **type** *(string) --* 

              The device pool's type.

               

              Allowed values include:

               

               
              * CURATED: A device pool that is created and managed by AWS Device Farm.
               
              * PRIVATE: A device pool that is created and managed by the device pool developer.
               

              
            

            - **rules** *(list) --* 

              Information about the device pool's rules.

              
              

              - *(dict) --* 

                Represents a condition for a device pool.

                
                

                - **attribute** *(string) --* 

                  The rule's stringified attribute. For example, specify the value as ``"\"abc\""`` .

                   

                  Allowed values include:

                   

                   
                  * ARN: The ARN.
                   
                  * FORM_FACTOR: The form factor (for example, phone or tablet).
                   
                  * MANUFACTURER: The manufacturer.
                   
                  * PLATFORM: The platform (for example, Android or iOS).
                   

                  
                

                - **operator** *(string) --* 

                  The rule's operator.

                   

                   
                  * EQUALS: The equals operator.
                   
                  * GREATER_THAN: The greater-than operator.
                   
                  * IN: The in operator.
                   
                  * LESS_THAN: The less-than operator.
                   
                  * NOT_IN: The not-in operator.
                   

                  
                

                - **value** *(string) --* 

                  The rule's value.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListDevices

  ::

    
    paginator = client.get_paginator('list_devices')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_devices`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: 

      The device types' ARNs.

      

    
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
            'devices': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'manufacturer': 'string',
                    'model': 'string',
                    'formFactor': 'PHONE'|'TABLET',
                    'platform': 'ANDROID'|'IOS',
                    'os': 'string',
                    'cpu': {
                        'frequency': 'string',
                        'architecture': 'string',
                        'clock': 123.0
                    },
                    'resolution': {
                        'width': 123,
                        'height': 123
                    },
                    'heapSize': 123,
                    'memory': 123,
                    'image': 'string',
                    'carrier': 'string',
                    'radio': 'string',
                    'remoteAccessEnabled': True|False,
                    'fleetType': 'string',
                    'fleetName': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list devices operation.

        
        

        - **devices** *(list) --* 

          Information about the devices.

          
          

          - *(dict) --* 

            Represents a device type that an app is tested against.

            
            

            - **arn** *(string) --* 

              The device's ARN.

              
            

            - **name** *(string) --* 

              The device's display name.

              
            

            - **manufacturer** *(string) --* 

              The device's manufacturer name.

              
            

            - **model** *(string) --* 

              The device's model name.

              
            

            - **formFactor** *(string) --* 

              The device's form factor.

               

              Allowed values include:

               

               
              * PHONE: The phone form factor.
               
              * TABLET: The tablet form factor.
               

              
            

            - **platform** *(string) --* 

              The device's platform.

               

              Allowed values include:

               

               
              * ANDROID: The Android platform.
               
              * IOS: The iOS platform.
               

              
            

            - **os** *(string) --* 

              The device's operating system type.

              
            

            - **cpu** *(dict) --* 

              Information about the device's CPU.

              
              

              - **frequency** *(string) --* 

                The CPU's frequency.

                
              

              - **architecture** *(string) --* 

                The CPU's architecture, for example x86 or ARM.

                
              

              - **clock** *(float) --* 

                The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                
          
            

            - **resolution** *(dict) --* 

              Represents the screen resolution of a device in height and width, expressed in pixels.

              
              

              - **width** *(integer) --* 

                The screen resolution's width, expressed in pixels.

                
              

              - **height** *(integer) --* 

                The screen resolution's height, expressed in pixels.

                
          
            

            - **heapSize** *(integer) --* 

              The device's heap size, expressed in bytes.

              
            

            - **memory** *(integer) --* 

              The device's total memory size, expressed in bytes.

              
            

            - **image** *(string) --* 

              The device's image name.

              
            

            - **carrier** *(string) --* 

              The device's carrier.

              
            

            - **radio** *(string) --* 

              The device's radio.

              
            

            - **remoteAccessEnabled** *(boolean) --* 

              Specifies whether remote access has been enabled for the specified device.

              
            

            - **fleetType** *(string) --* 

              The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

              
            

            - **fleetName** *(string) --* 

              The name of the fleet to which this device belongs.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListJobs

  ::

    
    paginator = client.get_paginator('list_jobs')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_jobs`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The jobs' ARNs.

      

    
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
            'jobs': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                    'created': datetime(2015, 1, 1),
                    'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                    'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                    'started': datetime(2015, 1, 1),
                    'stopped': datetime(2015, 1, 1),
                    'counters': {
                        'total': 123,
                        'passed': 123,
                        'failed': 123,
                        'warned': 123,
                        'errored': 123,
                        'stopped': 123,
                        'skipped': 123
                    },
                    'message': 'string',
                    'device': {
                        'arn': 'string',
                        'name': 'string',
                        'manufacturer': 'string',
                        'model': 'string',
                        'formFactor': 'PHONE'|'TABLET',
                        'platform': 'ANDROID'|'IOS',
                        'os': 'string',
                        'cpu': {
                            'frequency': 'string',
                            'architecture': 'string',
                            'clock': 123.0
                        },
                        'resolution': {
                            'width': 123,
                            'height': 123
                        },
                        'heapSize': 123,
                        'memory': 123,
                        'image': 'string',
                        'carrier': 'string',
                        'radio': 'string',
                        'remoteAccessEnabled': True|False,
                        'fleetType': 'string',
                        'fleetName': 'string'
                    },
                    'deviceMinutes': {
                        'total': 123.0,
                        'metered': 123.0,
                        'unmetered': 123.0
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list jobs request.

        
        

        - **jobs** *(list) --* 

          Information about the jobs.

          
          

          - *(dict) --* 

            Represents a device.

            
            

            - **arn** *(string) --* 

              The job's ARN.

              
            

            - **name** *(string) --* 

              The job's name.

              
            

            - **type** *(string) --* 

              The job's type.

               

              Allowed values include the following:

               

               
              * BUILTIN_FUZZ: The built-in fuzz type.
               
              * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
               
              * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
               
              * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
               
              * APPIUM_PYTHON: The Appium Python type.
               
              * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
               
              * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
               
              * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
               
              * CALABASH: The Calabash type.
               
              * INSTRUMENTATION: The Instrumentation type.
               
              * UIAUTOMATION: The uiautomation type.
               
              * UIAUTOMATOR: The uiautomator type.
               
              * XCTEST: The XCode test type.
               
              * XCTEST_UI: The XCode UI test type.
               

              
            

            - **created** *(datetime) --* 

              When the job was created.

              
            

            - **status** *(string) --* 

              The job's status.

               

              Allowed values include:

               

               
              * PENDING: A pending status.
               
              * PENDING_CONCURRENCY: A pending concurrency status.
               
              * PENDING_DEVICE: A pending device status.
               
              * PROCESSING: A processing status.
               
              * SCHEDULING: A scheduling status.
               
              * PREPARING: A preparing status.
               
              * RUNNING: A running status.
               
              * COMPLETED: A completed status.
               
              * STOPPING: A stopping status.
               

              
            

            - **result** *(string) --* 

              The job's result.

               

              Allowed values include:

               

               
              * PENDING: A pending condition.
               
              * PASSED: A passing condition.
               
              * WARNED: A warning condition.
               
              * FAILED: A failed condition.
               
              * SKIPPED: A skipped condition.
               
              * ERRORED: An error condition.
               
              * STOPPED: A stopped condition.
               

              
            

            - **started** *(datetime) --* 

              The job's start time.

              
            

            - **stopped** *(datetime) --* 

              The job's stop time.

              
            

            - **counters** *(dict) --* 

              The job's result counters.

              
              

              - **total** *(integer) --* 

                The total number of entities.

                
              

              - **passed** *(integer) --* 

                The number of passed entities.

                
              

              - **failed** *(integer) --* 

                The number of failed entities.

                
              

              - **warned** *(integer) --* 

                The number of warned entities.

                
              

              - **errored** *(integer) --* 

                The number of errored entities.

                
              

              - **stopped** *(integer) --* 

                The number of stopped entities.

                
              

              - **skipped** *(integer) --* 

                The number of skipped entities.

                
          
            

            - **message** *(string) --* 

              A message about the job's result.

              
            

            - **device** *(dict) --* 

              Represents a device type that an app is tested against.

              
              

              - **arn** *(string) --* 

                The device's ARN.

                
              

              - **name** *(string) --* 

                The device's display name.

                
              

              - **manufacturer** *(string) --* 

                The device's manufacturer name.

                
              

              - **model** *(string) --* 

                The device's model name.

                
              

              - **formFactor** *(string) --* 

                The device's form factor.

                 

                Allowed values include:

                 

                 
                * PHONE: The phone form factor.
                 
                * TABLET: The tablet form factor.
                 

                
              

              - **platform** *(string) --* 

                The device's platform.

                 

                Allowed values include:

                 

                 
                * ANDROID: The Android platform.
                 
                * IOS: The iOS platform.
                 

                
              

              - **os** *(string) --* 

                The device's operating system type.

                
              

              - **cpu** *(dict) --* 

                Information about the device's CPU.

                
                

                - **frequency** *(string) --* 

                  The CPU's frequency.

                  
                

                - **architecture** *(string) --* 

                  The CPU's architecture, for example x86 or ARM.

                  
                

                - **clock** *(float) --* 

                  The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                  
            
              

              - **resolution** *(dict) --* 

                Represents the screen resolution of a device in height and width, expressed in pixels.

                
                

                - **width** *(integer) --* 

                  The screen resolution's width, expressed in pixels.

                  
                

                - **height** *(integer) --* 

                  The screen resolution's height, expressed in pixels.

                  
            
              

              - **heapSize** *(integer) --* 

                The device's heap size, expressed in bytes.

                
              

              - **memory** *(integer) --* 

                The device's total memory size, expressed in bytes.

                
              

              - **image** *(string) --* 

                The device's image name.

                
              

              - **carrier** *(string) --* 

                The device's carrier.

                
              

              - **radio** *(string) --* 

                The device's radio.

                
              

              - **remoteAccessEnabled** *(boolean) --* 

                Specifies whether remote access has been enabled for the specified device.

                
              

              - **fleetType** *(string) --* 

                The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

                
              

              - **fleetName** *(string) --* 

                The name of the fleet to which this device belongs.

                
          
            

            - **deviceMinutes** *(dict) --* 

              Represents the total (metered or unmetered) minutes used by the job.

              
              

              - **total** *(float) --* 

                When specified, represents the total minutes used by the resource to run tests.

                
              

              - **metered** *(float) --* 

                When specified, represents only the sum of metered minutes used by the resource to run tests.

                
              

              - **unmetered** *(float) --* 

                When specified, represents only the sum of unmetered minutes used by the resource to run tests.

                
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListProjects

  ::

    
    paginator = client.get_paginator('list_projects')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_projects`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: 

      The projects' ARNs.

      

    
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
            'projects': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'created': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list projects request.

        
        

        - **projects** *(list) --* 

          Information about the projects.

          
          

          - *(dict) --* 

            Represents an operating-system neutral workspace for running and managing tests.

            
            

            - **arn** *(string) --* 

              The project's ARN.

              
            

            - **name** *(string) --* 

              The project's name.

              
            

            - **created** *(datetime) --* 

              When the project was created.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListRuns

  ::

    
    paginator = client.get_paginator('list_runs')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_runs`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The runs' ARNs.

      

    
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
            'runs': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                    'platform': 'ANDROID'|'IOS',
                    'created': datetime(2015, 1, 1),
                    'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                    'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                    'started': datetime(2015, 1, 1),
                    'stopped': datetime(2015, 1, 1),
                    'counters': {
                        'total': 123,
                        'passed': 123,
                        'failed': 123,
                        'warned': 123,
                        'errored': 123,
                        'stopped': 123,
                        'skipped': 123
                    },
                    'message': 'string',
                    'totalJobs': 123,
                    'completedJobs': 123,
                    'billingMethod': 'METERED'|'UNMETERED',
                    'deviceMinutes': {
                        'total': 123.0,
                        'metered': 123.0,
                        'unmetered': 123.0
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list runs request.

        
        

        - **runs** *(list) --* 

          Information about the runs.

          
          

          - *(dict) --* 

            Represents an app on a set of devices with a specific test and configuration.

            
            

            - **arn** *(string) --* 

              The run's ARN.

              
            

            - **name** *(string) --* 

              The run's name.

              
            

            - **type** *(string) --* 

              The run's type.

               

              Must be one of the following values:

               

               
              * BUILTIN_FUZZ: The built-in fuzz type.
               
              * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
               
              * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
               
              * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
               
              * APPIUM_PYTHON: The Appium Python type.
               
              * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
               
              * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
               
              * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
               
              * CALABASH: The Calabash type.
               
              * INSTRUMENTATION: The Instrumentation type.
               
              * UIAUTOMATION: The uiautomation type.
               
              * UIAUTOMATOR: The uiautomator type.
               
              * XCTEST: The XCode test type.
               
              * XCTEST_UI: The XCode UI test type.
               

              
            

            - **platform** *(string) --* 

              The run's platform.

               

              Allowed values include:

               

               
              * ANDROID: The Android platform.
               
              * IOS: The iOS platform.
               

              
            

            - **created** *(datetime) --* 

              When the run was created.

              
            

            - **status** *(string) --* 

              The run's status.

               

              Allowed values include:

               

               
              * PENDING: A pending status.
               
              * PENDING_CONCURRENCY: A pending concurrency status.
               
              * PENDING_DEVICE: A pending device status.
               
              * PROCESSING: A processing status.
               
              * SCHEDULING: A scheduling status.
               
              * PREPARING: A preparing status.
               
              * RUNNING: A running status.
               
              * COMPLETED: A completed status.
               
              * STOPPING: A stopping status.
               

              
            

            - **result** *(string) --* 

              The run's result.

               

              Allowed values include:

               

               
              * PENDING: A pending condition.
               
              * PASSED: A passing condition.
               
              * WARNED: A warning condition.
               
              * FAILED: A failed condition.
               
              * SKIPPED: A skipped condition.
               
              * ERRORED: An error condition.
               
              * STOPPED: A stopped condition.
               

              
            

            - **started** *(datetime) --* 

              The run's start time.

              
            

            - **stopped** *(datetime) --* 

              The run's stop time.

              
            

            - **counters** *(dict) --* 

              The run's result counters.

              
              

              - **total** *(integer) --* 

                The total number of entities.

                
              

              - **passed** *(integer) --* 

                The number of passed entities.

                
              

              - **failed** *(integer) --* 

                The number of failed entities.

                
              

              - **warned** *(integer) --* 

                The number of warned entities.

                
              

              - **errored** *(integer) --* 

                The number of errored entities.

                
              

              - **stopped** *(integer) --* 

                The number of stopped entities.

                
              

              - **skipped** *(integer) --* 

                The number of skipped entities.

                
          
            

            - **message** *(string) --* 

              A message about the run's result.

              
            

            - **totalJobs** *(integer) --* 

              The total number of jobs for the run.

              
            

            - **completedJobs** *(integer) --* 

              The total number of completed jobs.

              
            

            - **billingMethod** *(string) --* 

              Specifies the billing method for a test run: ``metered`` or ``unmetered`` . If the parameter is not specified, the default value is ``unmetered`` .

              
            

            - **deviceMinutes** *(dict) --* 

              Represents the total (metered or unmetered) minutes used by the test run.

              
              

              - **total** *(float) --* 

                When specified, represents the total minutes used by the resource to run tests.

                
              

              - **metered** *(float) --* 

                When specified, represents only the sum of metered minutes used by the resource to run tests.

                
              

              - **unmetered** *(float) --* 

                When specified, represents only the sum of unmetered minutes used by the resource to run tests.

                
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListSamples

  ::

    
    paginator = client.get_paginator('list_samples')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_samples`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The samples' ARNs.

      

    
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
            'samples': [
                {
                    'arn': 'string',
                    'type': 'CPU'|'MEMORY'|'THREADS'|'RX_RATE'|'TX_RATE'|'RX'|'TX'|'NATIVE_FRAMES'|'NATIVE_FPS'|'NATIVE_MIN_DRAWTIME'|'NATIVE_AVG_DRAWTIME'|'NATIVE_MAX_DRAWTIME'|'OPENGL_FRAMES'|'OPENGL_FPS'|'OPENGL_MIN_DRAWTIME'|'OPENGL_AVG_DRAWTIME'|'OPENGL_MAX_DRAWTIME',
                    'url': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list samples request.

        
        

        - **samples** *(list) --* 

          Information about the samples.

          
          

          - *(dict) --* 

            Represents a sample of performance data.

            
            

            - **arn** *(string) --* 

              The sample's ARN.

              
            

            - **type** *(string) --* 

              The sample's type.

               

              Must be one of the following values:

               

               
              * CPU: A CPU sample type. This is expressed as the app processing CPU time (including child processes) as reported by process, as a percentage.
               
              * MEMORY: A memory usage sample type. This is expressed as the total proportional set size of an app process, in kilobytes.
               
              * NATIVE_AVG_DRAWTIME
               
              * NATIVE_FPS
               
              * NATIVE_FRAMES
               
              * NATIVE_MAX_DRAWTIME
               
              * NATIVE_MIN_DRAWTIME
               
              * OPENGL_AVG_DRAWTIME
               
              * OPENGL_FPS
               
              * OPENGL_FRAMES
               
              * OPENGL_MAX_DRAWTIME
               
              * OPENGL_MIN_DRAWTIME
               
              * RX
               
              * RX_RATE: The total number of bytes per second (TCP and UDP) that are sent, by app process.
               
              * THREADS: A threads sample type. This is expressed as the total number of threads per app process.
               
              * TX
               
              * TX_RATE: The total number of bytes per second (TCP and UDP) that are received, by app process.
               

              
            

            - **url** *(string) --* 

              The pre-signed Amazon S3 URL that can be used with a corresponding GET request to download the sample's file.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListSuites

  ::

    
    paginator = client.get_paginator('list_suites')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_suites`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The suites' ARNs.

      

    
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
            'suites': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                    'created': datetime(2015, 1, 1),
                    'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                    'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                    'started': datetime(2015, 1, 1),
                    'stopped': datetime(2015, 1, 1),
                    'counters': {
                        'total': 123,
                        'passed': 123,
                        'failed': 123,
                        'warned': 123,
                        'errored': 123,
                        'stopped': 123,
                        'skipped': 123
                    },
                    'message': 'string',
                    'deviceMinutes': {
                        'total': 123.0,
                        'metered': 123.0,
                        'unmetered': 123.0
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list suites request.

        
        

        - **suites** *(list) --* 

          Information about the suites.

          
          

          - *(dict) --* 

            Represents a collection of one or more tests.

            
            

            - **arn** *(string) --* 

              The suite's ARN.

              
            

            - **name** *(string) --* 

              The suite's name.

              
            

            - **type** *(string) --* 

              The suite's type.

               

              Must be one of the following values:

               

               
              * BUILTIN_FUZZ: The built-in fuzz type.
               
              * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
               
              * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
               
              * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
               
              * APPIUM_PYTHON: The Appium Python type.
               
              * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
               
              * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
               
              * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
               
              * CALABASH: The Calabash type.
               
              * INSTRUMENTATION: The Instrumentation type.
               
              * UIAUTOMATION: The uiautomation type.
               
              * UIAUTOMATOR: The uiautomator type.
               
              * XCTEST: The XCode test type.
               
              * XCTEST_UI: The XCode UI test type.
               

              
            

            - **created** *(datetime) --* 

              When the suite was created.

              
            

            - **status** *(string) --* 

              The suite's status.

               

              Allowed values include:

               

               
              * PENDING: A pending status.
               
              * PENDING_CONCURRENCY: A pending concurrency status.
               
              * PENDING_DEVICE: A pending device status.
               
              * PROCESSING: A processing status.
               
              * SCHEDULING: A scheduling status.
               
              * PREPARING: A preparing status.
               
              * RUNNING: A running status.
               
              * COMPLETED: A completed status.
               
              * STOPPING: A stopping status.
               

              
            

            - **result** *(string) --* 

              The suite's result.

               

              Allowed values include:

               

               
              * PENDING: A pending condition.
               
              * PASSED: A passing condition.
               
              * WARNED: A warning condition.
               
              * FAILED: A failed condition.
               
              * SKIPPED: A skipped condition.
               
              * ERRORED: An error condition.
               
              * STOPPED: A stopped condition.
               

              
            

            - **started** *(datetime) --* 

              The suite's start time.

              
            

            - **stopped** *(datetime) --* 

              The suite's stop time.

              
            

            - **counters** *(dict) --* 

              The suite's result counters.

              
              

              - **total** *(integer) --* 

                The total number of entities.

                
              

              - **passed** *(integer) --* 

                The number of passed entities.

                
              

              - **failed** *(integer) --* 

                The number of failed entities.

                
              

              - **warned** *(integer) --* 

                The number of warned entities.

                
              

              - **errored** *(integer) --* 

                The number of errored entities.

                
              

              - **stopped** *(integer) --* 

                The number of stopped entities.

                
              

              - **skipped** *(integer) --* 

                The number of skipped entities.

                
          
            

            - **message** *(string) --* 

              A message about the suite's result.

              
            

            - **deviceMinutes** *(dict) --* 

              Represents the total (metered or unmetered) minutes used by the test suite.

              
              

              - **total** *(float) --* 

                When specified, represents the total minutes used by the resource to run tests.

                
              

              - **metered** *(float) --* 

                When specified, represents only the sum of metered minutes used by the resource to run tests.

                
              

              - **unmetered** *(float) --* 

                When specified, represents only the sum of unmetered minutes used by the resource to run tests.

                
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListTests

  ::

    
    paginator = client.get_paginator('list_tests')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_tests`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The tests' ARNs.

      

    
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
            'tests': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'type': 'BUILTIN_FUZZ'|'BUILTIN_EXPLORER'|'APPIUM_JAVA_JUNIT'|'APPIUM_JAVA_TESTNG'|'APPIUM_PYTHON'|'APPIUM_WEB_JAVA_JUNIT'|'APPIUM_WEB_JAVA_TESTNG'|'APPIUM_WEB_PYTHON'|'CALABASH'|'INSTRUMENTATION'|'UIAUTOMATION'|'UIAUTOMATOR'|'XCTEST'|'XCTEST_UI',
                    'created': datetime(2015, 1, 1),
                    'status': 'PENDING'|'PENDING_CONCURRENCY'|'PENDING_DEVICE'|'PROCESSING'|'SCHEDULING'|'PREPARING'|'RUNNING'|'COMPLETED'|'STOPPING',
                    'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                    'started': datetime(2015, 1, 1),
                    'stopped': datetime(2015, 1, 1),
                    'counters': {
                        'total': 123,
                        'passed': 123,
                        'failed': 123,
                        'warned': 123,
                        'errored': 123,
                        'stopped': 123,
                        'skipped': 123
                    },
                    'message': 'string',
                    'deviceMinutes': {
                        'total': 123.0,
                        'metered': 123.0,
                        'unmetered': 123.0
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list tests request.

        
        

        - **tests** *(list) --* 

          Information about the tests.

          
          

          - *(dict) --* 

            Represents a condition that is evaluated.

            
            

            - **arn** *(string) --* 

              The test's ARN.

              
            

            - **name** *(string) --* 

              The test's name.

              
            

            - **type** *(string) --* 

              The test's type.

               

              Must be one of the following values:

               

               
              * BUILTIN_FUZZ: The built-in fuzz type.
               
              * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
               
              * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
               
              * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
               
              * APPIUM_PYTHON: The Appium Python type.
               
              * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
               
              * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
               
              * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
               
              * CALABASH: The Calabash type.
               
              * INSTRUMENTATION: The Instrumentation type.
               
              * UIAUTOMATION: The uiautomation type.
               
              * UIAUTOMATOR: The uiautomator type.
               
              * XCTEST: The XCode test type.
               
              * XCTEST_UI: The XCode UI test type.
               

              
            

            - **created** *(datetime) --* 

              When the test was created.

              
            

            - **status** *(string) --* 

              The test's status.

               

              Allowed values include:

               

               
              * PENDING: A pending status.
               
              * PENDING_CONCURRENCY: A pending concurrency status.
               
              * PENDING_DEVICE: A pending device status.
               
              * PROCESSING: A processing status.
               
              * SCHEDULING: A scheduling status.
               
              * PREPARING: A preparing status.
               
              * RUNNING: A running status.
               
              * COMPLETED: A completed status.
               
              * STOPPING: A stopping status.
               

              
            

            - **result** *(string) --* 

              The test's result.

               

              Allowed values include:

               

               
              * PENDING: A pending condition.
               
              * PASSED: A passing condition.
               
              * WARNED: A warning condition.
               
              * FAILED: A failed condition.
               
              * SKIPPED: A skipped condition.
               
              * ERRORED: An error condition.
               
              * STOPPED: A stopped condition.
               

              
            

            - **started** *(datetime) --* 

              The test's start time.

              
            

            - **stopped** *(datetime) --* 

              The test's stop time.

              
            

            - **counters** *(dict) --* 

              The test's result counters.

              
              

              - **total** *(integer) --* 

                The total number of entities.

                
              

              - **passed** *(integer) --* 

                The number of passed entities.

                
              

              - **failed** *(integer) --* 

                The number of failed entities.

                
              

              - **warned** *(integer) --* 

                The number of warned entities.

                
              

              - **errored** *(integer) --* 

                The number of errored entities.

                
              

              - **stopped** *(integer) --* 

                The number of stopped entities.

                
              

              - **skipped** *(integer) --* 

                The number of skipped entities.

                
          
            

            - **message** *(string) --* 

              A message about the test's result.

              
            

            - **deviceMinutes** *(dict) --* 

              Represents the total (metered or unmetered) minutes used by the test.

              
              

              - **total** *(float) --* 

                When specified, represents the total minutes used by the resource to run tests.

                
              

              - **metered** *(float) --* 

                When specified, represents only the sum of metered minutes used by the resource to run tests.

                
              

              - **unmetered** *(float) --* 

                When specified, represents only the sum of unmetered minutes used by the resource to run tests.

                
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListUniqueProblems

  ::

    
    paginator = client.get_paginator('list_unique_problems')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_unique_problems`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The unique problems' ARNs.

      

    
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
            'uniqueProblems': {
                'string': [
                    {
                        'message': 'string',
                        'problems': [
                            {
                                'run': {
                                    'arn': 'string',
                                    'name': 'string'
                                },
                                'job': {
                                    'arn': 'string',
                                    'name': 'string'
                                },
                                'suite': {
                                    'arn': 'string',
                                    'name': 'string'
                                },
                                'test': {
                                    'arn': 'string',
                                    'name': 'string'
                                },
                                'device': {
                                    'arn': 'string',
                                    'name': 'string',
                                    'manufacturer': 'string',
                                    'model': 'string',
                                    'formFactor': 'PHONE'|'TABLET',
                                    'platform': 'ANDROID'|'IOS',
                                    'os': 'string',
                                    'cpu': {
                                        'frequency': 'string',
                                        'architecture': 'string',
                                        'clock': 123.0
                                    },
                                    'resolution': {
                                        'width': 123,
                                        'height': 123
                                    },
                                    'heapSize': 123,
                                    'memory': 123,
                                    'image': 'string',
                                    'carrier': 'string',
                                    'radio': 'string',
                                    'remoteAccessEnabled': True|False,
                                    'fleetType': 'string',
                                    'fleetName': 'string'
                                },
                                'result': 'PENDING'|'PASSED'|'WARNED'|'FAILED'|'SKIPPED'|'ERRORED'|'STOPPED',
                                'message': 'string'
                            },
                        ]
                    },
                ]
            },
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list unique problems request.

        
        

        - **uniqueProblems** *(dict) --* 

          Information about the unique problems.

           

          Allowed values include:

           

           
          * PENDING: A pending condition.
           
          * PASSED: A passing condition.
           
          * WARNED: A warning condition.
           
          * FAILED: A failed condition.
           
          * SKIPPED: A skipped condition.
           
          * ERRORED: An error condition.
           
          * STOPPED: A stopped condition.
           

          
          

          - *(string) --* 
            

            - *(list) --* 
              

              - *(dict) --* 

                A collection of one or more problems, grouped by their result.

                
                

                - **message** *(string) --* 

                  A message about the unique problems' result.

                  
                

                - **problems** *(list) --* 

                  Information about the problems.

                  
                  

                  - *(dict) --* 

                    Represents a specific warning or failure.

                    
                    

                    - **run** *(dict) --* 

                      Information about the associated run.

                      
                      

                      - **arn** *(string) --* 

                        The problem detail's ARN.

                        
                      

                      - **name** *(string) --* 

                        The problem detail's name.

                        
                  
                    

                    - **job** *(dict) --* 

                      Information about the associated job.

                      
                      

                      - **arn** *(string) --* 

                        The problem detail's ARN.

                        
                      

                      - **name** *(string) --* 

                        The problem detail's name.

                        
                  
                    

                    - **suite** *(dict) --* 

                      Information about the associated suite.

                      
                      

                      - **arn** *(string) --* 

                        The problem detail's ARN.

                        
                      

                      - **name** *(string) --* 

                        The problem detail's name.

                        
                  
                    

                    - **test** *(dict) --* 

                      Information about the associated test.

                      
                      

                      - **arn** *(string) --* 

                        The problem detail's ARN.

                        
                      

                      - **name** *(string) --* 

                        The problem detail's name.

                        
                  
                    

                    - **device** *(dict) --* 

                      Information about the associated device.

                      
                      

                      - **arn** *(string) --* 

                        The device's ARN.

                        
                      

                      - **name** *(string) --* 

                        The device's display name.

                        
                      

                      - **manufacturer** *(string) --* 

                        The device's manufacturer name.

                        
                      

                      - **model** *(string) --* 

                        The device's model name.

                        
                      

                      - **formFactor** *(string) --* 

                        The device's form factor.

                         

                        Allowed values include:

                         

                         
                        * PHONE: The phone form factor.
                         
                        * TABLET: The tablet form factor.
                         

                        
                      

                      - **platform** *(string) --* 

                        The device's platform.

                         

                        Allowed values include:

                         

                         
                        * ANDROID: The Android platform.
                         
                        * IOS: The iOS platform.
                         

                        
                      

                      - **os** *(string) --* 

                        The device's operating system type.

                        
                      

                      - **cpu** *(dict) --* 

                        Information about the device's CPU.

                        
                        

                        - **frequency** *(string) --* 

                          The CPU's frequency.

                          
                        

                        - **architecture** *(string) --* 

                          The CPU's architecture, for example x86 or ARM.

                          
                        

                        - **clock** *(float) --* 

                          The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

                          
                    
                      

                      - **resolution** *(dict) --* 

                        Represents the screen resolution of a device in height and width, expressed in pixels.

                        
                        

                        - **width** *(integer) --* 

                          The screen resolution's width, expressed in pixels.

                          
                        

                        - **height** *(integer) --* 

                          The screen resolution's height, expressed in pixels.

                          
                    
                      

                      - **heapSize** *(integer) --* 

                        The device's heap size, expressed in bytes.

                        
                      

                      - **memory** *(integer) --* 

                        The device's total memory size, expressed in bytes.

                        
                      

                      - **image** *(string) --* 

                        The device's image name.

                        
                      

                      - **carrier** *(string) --* 

                        The device's carrier.

                        
                      

                      - **radio** *(string) --* 

                        The device's radio.

                        
                      

                      - **remoteAccessEnabled** *(boolean) --* 

                        Specifies whether remote access has been enabled for the specified device.

                        
                      

                      - **fleetType** *(string) --* 

                        The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

                        
                      

                      - **fleetName** *(string) --* 

                        The name of the fleet to which this device belongs.

                        
                  
                    

                    - **result** *(string) --* 

                      The problem's result.

                       

                      Allowed values include:

                       

                       
                      * PENDING: A pending condition.
                       
                      * PASSED: A passing condition.
                       
                      * WARNED: A warning condition.
                       
                      * FAILED: A failed condition.
                       
                      * SKIPPED: A skipped condition.
                       
                      * ERRORED: An error condition.
                       
                      * STOPPED: A stopped condition.
                       

                      
                    

                    - **message** *(string) --* 

                      A message about the problem's result.

                      
                
              
            
          
      
    
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: DeviceFarm.Paginator.ListUploads

  ::

    
    paginator = client.get_paginator('list_uploads')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`DeviceFarm.Client.list_uploads`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          arn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type arn: string
    :param arn: **[REQUIRED]** 

      The uploads' ARNs.

      

    
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
            'uploads': [
                {
                    'arn': 'string',
                    'name': 'string',
                    'created': datetime(2015, 1, 1),
                    'type': 'ANDROID_APP'|'IOS_APP'|'WEB_APP'|'EXTERNAL_DATA'|'APPIUM_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_PYTHON_TEST_PACKAGE'|'APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE'|'APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE'|'APPIUM_WEB_PYTHON_TEST_PACKAGE'|'CALABASH_TEST_PACKAGE'|'INSTRUMENTATION_TEST_PACKAGE'|'UIAUTOMATION_TEST_PACKAGE'|'UIAUTOMATOR_TEST_PACKAGE'|'XCTEST_TEST_PACKAGE'|'XCTEST_UI_TEST_PACKAGE',
                    'status': 'INITIALIZED'|'PROCESSING'|'SUCCEEDED'|'FAILED',
                    'url': 'string',
                    'metadata': 'string',
                    'contentType': 'string',
                    'message': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the result of a list uploads request.

        
        

        - **uploads** *(list) --* 

          Information about the uploads.

          
          

          - *(dict) --* 

            An app or a set of one or more tests to upload or that have been uploaded.

            
            

            - **arn** *(string) --* 

              The upload's ARN.

              
            

            - **name** *(string) --* 

              The upload's file name.

              
            

            - **created** *(datetime) --* 

              When the upload was created.

              
            

            - **type** *(string) --* 

              The upload's type.

               

              Must be one of the following values:

               

               
              * ANDROID_APP: An Android upload.
               
              * IOS_APP: An iOS upload.
               
              * WEB_APP: A web appliction upload.
               
              * EXTERNAL_DATA: An external data upload.
               
              * APPIUM_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
               
              * APPIUM_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
               
              * APPIUM_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
               
              * APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
               
              * APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
               
              * APPIUM_WEB_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
               
              * CALABASH_TEST_PACKAGE: A Calabash test package upload.
               
              * INSTRUMENTATION_TEST_PACKAGE: An instrumentation upload.
               
              * UIAUTOMATION_TEST_PACKAGE: A uiautomation test package upload.
               
              * UIAUTOMATOR_TEST_PACKAGE: A uiautomator test package upload.
               
              * XCTEST_TEST_PACKAGE: An XCode test package upload.
               
              * XCTEST_UI_TEST_PACKAGE: An XCode UI test package upload.
               

              
            

            - **status** *(string) --* 

              The upload's status.

               

              Must be one of the following values:

               

               
              * FAILED: A failed status.
               
              * INITIALIZED: An initialized status.
               
              * PROCESSING: A processing status.
               
              * SUCCEEDED: A succeeded status.
               

              
            

            - **url** *(string) --* 

              The pre-signed Amazon S3 URL that was used to store a file through a corresponding PUT request.

              
            

            - **metadata** *(string) --* 

              The upload's metadata. For example, for Android, this contains information that is parsed from the manifest and is displayed in the AWS Device Farm console after the associated app is uploaded.

              
            

            - **contentType** *(string) --* 

              The upload's content type (for example, "application/octet-stream").

              
            

            - **message** *(string) --* 

              A message about the upload's result.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    