

.. _AWS IoT SQL Reference: http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference
.. _Unix timestamp: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#about_timestamp
.. _metric unit: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#Unit
.. _AmazonCognito Identity format: http://docs.aws.amazon.com/cognitoidentity/latest/APIReference/API_GetCredentialsForIdentity.html#API_GetCredentialsForIdentity_RequestSyntax


***
IoT
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: IoT.Client

  A low-level client representing AWS IoT::

    
    import boto3
    
    client = boto3.client('iot')

  
  These are the available methods:
  
  *   :py:meth:`accept_certificate_transfer`

  
  *   :py:meth:`attach_principal_policy`

  
  *   :py:meth:`attach_thing_principal`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`cancel_certificate_transfer`

  
  *   :py:meth:`create_certificate_from_csr`

  
  *   :py:meth:`create_keys_and_certificate`

  
  *   :py:meth:`create_policy`

  
  *   :py:meth:`create_policy_version`

  
  *   :py:meth:`create_thing`

  
  *   :py:meth:`create_thing_type`

  
  *   :py:meth:`create_topic_rule`

  
  *   :py:meth:`delete_ca_certificate`

  
  *   :py:meth:`delete_certificate`

  
  *   :py:meth:`delete_policy`

  
  *   :py:meth:`delete_policy_version`

  
  *   :py:meth:`delete_registration_code`

  
  *   :py:meth:`delete_thing`

  
  *   :py:meth:`delete_thing_type`

  
  *   :py:meth:`delete_topic_rule`

  
  *   :py:meth:`deprecate_thing_type`

  
  *   :py:meth:`describe_ca_certificate`

  
  *   :py:meth:`describe_certificate`

  
  *   :py:meth:`describe_endpoint`

  
  *   :py:meth:`describe_thing`

  
  *   :py:meth:`describe_thing_type`

  
  *   :py:meth:`detach_principal_policy`

  
  *   :py:meth:`detach_thing_principal`

  
  *   :py:meth:`disable_topic_rule`

  
  *   :py:meth:`enable_topic_rule`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_logging_options`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_policy`

  
  *   :py:meth:`get_policy_version`

  
  *   :py:meth:`get_registration_code`

  
  *   :py:meth:`get_topic_rule`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_ca_certificates`

  
  *   :py:meth:`list_certificates`

  
  *   :py:meth:`list_certificates_by_ca`

  
  *   :py:meth:`list_outgoing_certificates`

  
  *   :py:meth:`list_policies`

  
  *   :py:meth:`list_policy_principals`

  
  *   :py:meth:`list_policy_versions`

  
  *   :py:meth:`list_principal_policies`

  
  *   :py:meth:`list_principal_things`

  
  *   :py:meth:`list_thing_principals`

  
  *   :py:meth:`list_thing_types`

  
  *   :py:meth:`list_things`

  
  *   :py:meth:`list_topic_rules`

  
  *   :py:meth:`register_ca_certificate`

  
  *   :py:meth:`register_certificate`

  
  *   :py:meth:`reject_certificate_transfer`

  
  *   :py:meth:`replace_topic_rule`

  
  *   :py:meth:`set_default_policy_version`

  
  *   :py:meth:`set_logging_options`

  
  *   :py:meth:`transfer_certificate`

  
  *   :py:meth:`update_ca_certificate`

  
  *   :py:meth:`update_certificate`

  
  *   :py:meth:`update_thing`

  

  .. py:method:: accept_certificate_transfer(**kwargs)

    

    Accepts a pending certificate transfer. The default state of the certificate is INACTIVE.

     

    To check for pending certificate transfers, call  ListCertificates to enumerate your certificates.

    

    **Request Syntax** 
    ::

      response = client.accept_certificate_transfer(
          certificateId='string',
          setAsActive=True|False
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The ID of the certificate.

      

    
    :type setAsActive: boolean
    :param setAsActive: 

      Specifies whether the certificate is active.

      

    
    
    :returns: None

  .. py:method:: attach_principal_policy(**kwargs)

    

    Attaches the specified policy to the specified principal (certificate or other credential).

    

    **Request Syntax** 
    ::

      response = client.attach_principal_policy(
          policyName='string',
          principal='string'
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The policy name.

      

    
    :type principal: string
    :param principal: **[REQUIRED]** 

      The principal, which can be a certificate ARN (as returned from the CreateCertificate operation) or an Amazon Cognito ID.

      

    
    
    :returns: None

  .. py:method:: attach_thing_principal(**kwargs)

    

    Attaches the specified principal to the specified thing.

    

    **Request Syntax** 
    ::

      response = client.attach_thing_principal(
          thingName='string',
          principal='string'
      )
    :type thingName: string
    :param thingName: **[REQUIRED]** 

      The name of the thing.

      

    
    :type principal: string
    :param principal: **[REQUIRED]** 

      The principal, such as a certificate or other credential.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output from the AttachThingPrincipal operation.

        
    

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


  .. py:method:: cancel_certificate_transfer(**kwargs)

    

    Cancels a pending transfer for the specified certificate.

     

    **Note** Only the transfer source account can use this operation to cancel a transfer. (Transfer destinations can use  RejectCertificateTransfer instead.) After transfer, AWS IoT returns the certificate to the source account in the INACTIVE state. After the destination account has accepted the transfer, the transfer cannot be cancelled.

     

    After a certificate transfer is cancelled, the status of the certificate changes from PENDING_TRANSFER to INACTIVE.

    

    **Request Syntax** 
    ::

      response = client.cancel_certificate_transfer(
          certificateId='string'
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The ID of the certificate.

      

    
    
    :returns: None

  .. py:method:: create_certificate_from_csr(**kwargs)

    

    Creates an X.509 certificate using the specified certificate signing request.

     

    **Note** Reusing the same certificate signing request (CSR) results in a distinct certificate.

     

    You can create multiple certificates in a batch by creating a directory, copying multiple .csr files into that directory, and then specifying that directory on the command line. The following commands show how to create a batch of certificates given a batch of CSRs. 

     

    Assuming a set of CSRs are located inside of the directory my-csr-directory:

     

    On Linux and OS X, the command is:

     

    $ ls my-csr-directory/ | xargs -I {} aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/{}

     

    This command lists all of the CSRs in my-csr-directory and pipes each CSR file name to the aws iot create-certificate-from-csr AWS CLI command to create a certificate for the corresponding CSR. 

     

    The aws iot create-certificate-from-csr part of the command can also be run in parallel to speed up the certificate creation process: 

     

    $ ls my-csr-directory/ | xargs -P 10 -I {} aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/{} 

     

    On Windows PowerShell, the command to create certificates for all CSRs in my-csr-directory is: 

     

     ls -Name my-csr-directory | %{aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/$_} 

     

    On a Windows command prompt, the command to create certificates for all CSRs in my-csr-directory is: 

     

     forfiles /p my-csr-directory /c "cmd /c aws iot create-certificate-from-csr --certificate-signing-request file://@path"

    

    **Request Syntax** 
    ::

      response = client.create_certificate_from_csr(
          certificateSigningRequest='string',
          setAsActive=True|False
      )
    :type certificateSigningRequest: string
    :param certificateSigningRequest: **[REQUIRED]** 

      The certificate signing request (CSR).

      

    
    :type setAsActive: boolean
    :param setAsActive: 

      Specifies whether the certificate is active.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'certificateArn': 'string',
            'certificateId': 'string',
            'certificatePem': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the CreateCertificateFromCsr operation.

        
        

        - **certificateArn** *(string) --* 

          The Amazon Resource Name (ARN) of the certificate. You can use the ARN as a principal for policy operations.

          
        

        - **certificateId** *(string) --* 

          The ID of the certificate. Certificate management operations only take a certificateId.

          
        

        - **certificatePem** *(string) --* 

          The certificate data, in PEM format.

          
    

  .. py:method:: create_keys_and_certificate(**kwargs)

    

    Creates a 2048-bit RSA key pair and issues an X.509 certificate using the issued public key.

     

    **Note** This is the only time AWS IoT issues the private key for this certificate, so it is important to keep it in a secure location.

    

    **Request Syntax** 
    ::

      response = client.create_keys_and_certificate(
          setAsActive=True|False
      )
    :type setAsActive: boolean
    :param setAsActive: 

      Specifies whether the certificate is active.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'certificateArn': 'string',
            'certificateId': 'string',
            'certificatePem': 'string',
            'keyPair': {
                'PublicKey': 'string',
                'PrivateKey': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output of the CreateKeysAndCertificate operation.

        
        

        - **certificateArn** *(string) --* 

          The ARN of the certificate.

          
        

        - **certificateId** *(string) --* 

          The ID of the certificate. AWS IoT issues a default subject name for the certificate (for example, AWS IoT Certificate).

          
        

        - **certificatePem** *(string) --* 

          The certificate data, in PEM format.

          
        

        - **keyPair** *(dict) --* 

          The generated key pair.

          
          

          - **PublicKey** *(string) --* 

            The public key.

            
          

          - **PrivateKey** *(string) --* 

            The private key.

            
      
    

  .. py:method:: create_policy(**kwargs)

    

    Creates an AWS IoT policy.

     

    The created policy is the default version for the policy. This operation creates a policy version with a version identifier of **1** and sets **1** as the policy's default version.

    

    **Request Syntax** 
    ::

      response = client.create_policy(
          policyName='string',
          policyDocument='string'
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The policy name.

      

    
    :type policyDocument: string
    :param policyDocument: **[REQUIRED]** 

      The JSON document that describes the policy. **policyDocument** must have a minimum length of 1, with a maximum length of 2048, excluding whitespace.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'policyName': 'string',
            'policyArn': 'string',
            'policyDocument': 'string',
            'policyVersionId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the CreatePolicy operation.

        
        

        - **policyName** *(string) --* 

          The policy name.

          
        

        - **policyArn** *(string) --* 

          The policy ARN.

          
        

        - **policyDocument** *(string) --* 

          The JSON document that describes the policy.

          
        

        - **policyVersionId** *(string) --* 

          The policy version ID.

          
    

  .. py:method:: create_policy_version(**kwargs)

    

    Creates a new version of the specified AWS IoT policy. To update a policy, create a new policy version. A managed policy can have up to five versions. If the policy has five versions, you must use  DeletePolicyVersion to delete an existing version before you create a new one.

     

    Optionally, you can set the new version as the policy's default version. The default version is the operative version (that is, the version that is in effect for the certificates to which the policy is attached).

    

    **Request Syntax** 
    ::

      response = client.create_policy_version(
          policyName='string',
          policyDocument='string',
          setAsDefault=True|False
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The policy name.

      

    
    :type policyDocument: string
    :param policyDocument: **[REQUIRED]** 

      The JSON document that describes the policy. Minimum length of 1. Maximum length of 2048, excluding whitespaces

      

    
    :type setAsDefault: boolean
    :param setAsDefault: 

      Specifies whether the policy version is set as the default. When this parameter is true, the new policy version becomes the operative version (that is, the version that is in effect for the certificates to which the policy is attached).

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'policyArn': 'string',
            'policyDocument': 'string',
            'policyVersionId': 'string',
            'isDefaultVersion': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output of the CreatePolicyVersion operation.

        
        

        - **policyArn** *(string) --* 

          The policy ARN.

          
        

        - **policyDocument** *(string) --* 

          The JSON document that describes the policy.

          
        

        - **policyVersionId** *(string) --* 

          The policy version ID.

          
        

        - **isDefaultVersion** *(boolean) --* 

          Specifies whether the policy version is the default.

          
    

  .. py:method:: create_thing(**kwargs)

    

    Creates a thing record in the thing registry.

    

    **Request Syntax** 
    ::

      response = client.create_thing(
          thingName='string',
          thingTypeName='string',
          attributePayload={
              'attributes': {
                  'string': 'string'
              },
              'merge': True|False
          }
      )
    :type thingName: string
    :param thingName: **[REQUIRED]** 

      The name of the thing to create.

      

    
    :type thingTypeName: string
    :param thingTypeName: 

      The name of the thing type associated with the new thing.

      

    
    :type attributePayload: dict
    :param attributePayload: 

      The attribute payload, which consists of up to three name/value pairs in a JSON document. For example:

       

      ``{\"attributes\":{\"string1\":\"string2\"}})`` 

      

    
      - **attributes** *(dict) --* 

        A JSON string containing up to three key-value pair in JSON format. For example:

         

        ``{\"attributes\":{\"string1\":\"string2\"}})`` 

        

      
        - *(string) --* 

        
          - *(string) --* An attribute value for an Thing. An empty or null value in Update means that existing value for that attribute should be deleted. Empty and null values in create are ignored.

          
    
  
      - **merge** *(boolean) --* 

        Specifies whether the list of attributes provided in the ``AttributePayload`` is merged with the attributes stored in the registry, instead of overwriting them.

         

        To remove an attribute, call ``UpdateThing`` with an empty attribute value.

         

        .. note::

           

          The ``merge`` attribute is only valid when calling ``UpdateThing`` .

           

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'thingName': 'string',
            'thingArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output of the CreateThing operation.

        
        

        - **thingName** *(string) --* 

          The name of the new thing.

          
        

        - **thingArn** *(string) --* 

          The ARN of the new thing.

          
    

  .. py:method:: create_thing_type(**kwargs)

    

    Creates a new thing type.

    

    **Request Syntax** 
    ::

      response = client.create_thing_type(
          thingTypeName='string',
          thingTypeProperties={
              'thingTypeDescription': 'string',
              'searchableAttributes': [
                  'string',
              ]
          }
      )
    :type thingTypeName: string
    :param thingTypeName: **[REQUIRED]** 

      The name of the thing type.

      

    
    :type thingTypeProperties: dict
    :param thingTypeProperties: 

      The ThingTypeProperties for the thing type to create. It contains information about the new thing type including a description, and a list of searchable thing attribute names.

      

    
      - **thingTypeDescription** *(string) --* 

        The description of the thing type.

        

      
      - **searchableAttributes** *(list) --* 

        A list of searchable thing attribute names.

        

      
        - *(string) --* 

        
    
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'thingTypeName': 'string',
            'thingTypeArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output of the CreateThingType operation.

        
        

        - **thingTypeName** *(string) --* 

          The name of the thing type.

          
        

        - **thingTypeArn** *(string) --* 

          The Amazon Resource Name (ARN) of the thing type.

          
    

  .. py:method:: create_topic_rule(**kwargs)

    

    Creates a rule. Creating rules is an administrator-level action. Any user who has permission to create rules will be able to access data processed by the rule.

    

    **Request Syntax** 
    ::

      response = client.create_topic_rule(
          ruleName='string',
          topicRulePayload={
              'sql': 'string',
              'description': 'string',
              'actions': [
                  {
                      'dynamoDB': {
                          'tableName': 'string',
                          'roleArn': 'string',
                          'operation': 'string',
                          'hashKeyField': 'string',
                          'hashKeyValue': 'string',
                          'hashKeyType': 'STRING'|'NUMBER',
                          'rangeKeyField': 'string',
                          'rangeKeyValue': 'string',
                          'rangeKeyType': 'STRING'|'NUMBER',
                          'payloadField': 'string'
                      },
                      'lambda': {
                          'functionArn': 'string'
                      },
                      'sns': {
                          'targetArn': 'string',
                          'roleArn': 'string',
                          'messageFormat': 'RAW'|'JSON'
                      },
                      'sqs': {
                          'roleArn': 'string',
                          'queueUrl': 'string',
                          'useBase64': True|False
                      },
                      'kinesis': {
                          'roleArn': 'string',
                          'streamName': 'string',
                          'partitionKey': 'string'
                      },
                      'republish': {
                          'roleArn': 'string',
                          'topic': 'string'
                      },
                      's3': {
                          'roleArn': 'string',
                          'bucketName': 'string',
                          'key': 'string'
                      },
                      'firehose': {
                          'roleArn': 'string',
                          'deliveryStreamName': 'string',
                          'separator': 'string'
                      },
                      'cloudwatchMetric': {
                          'roleArn': 'string',
                          'metricNamespace': 'string',
                          'metricName': 'string',
                          'metricValue': 'string',
                          'metricUnit': 'string',
                          'metricTimestamp': 'string'
                      },
                      'cloudwatchAlarm': {
                          'roleArn': 'string',
                          'alarmName': 'string',
                          'stateReason': 'string',
                          'stateValue': 'string'
                      },
                      'elasticsearch': {
                          'roleArn': 'string',
                          'endpoint': 'string',
                          'index': 'string',
                          'type': 'string',
                          'id': 'string'
                      }
                  },
              ],
              'ruleDisabled': True|False,
              'awsIotSqlVersion': 'string'
          }
      )
    :type ruleName: string
    :param ruleName: **[REQUIRED]** 

      The name of the rule.

      

    
    :type topicRulePayload: dict
    :param topicRulePayload: **[REQUIRED]** 

      The rule payload.

      

    
      - **sql** *(string) --* **[REQUIRED]** 

        The SQL statement used to query the topic. For more information, see `AWS IoT SQL Reference`_ in the *AWS IoT Developer Guide* .

        

      
      - **description** *(string) --* 

        The description of the rule.

        

      
      - **actions** *(list) --* **[REQUIRED]** 

        The actions associated with the rule.

        

      
        - *(dict) --* 

          Describes the actions associated with a rule.

          

        
          - **dynamoDB** *(dict) --* 

            Write to a DynamoDB table.

            

          
            - **tableName** *(string) --* **[REQUIRED]** 

              The name of the DynamoDB table.

              

            
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access to the DynamoDB table.

              

            
            - **operation** *(string) --* 

              The type of operation to be performed. This follows the substitution template, so it can be ``${operation}`` , but the substitution must result in one of the following: ``INSERT`` , ``UPDATE`` , or ``DELETE`` .

              

            
            - **hashKeyField** *(string) --* **[REQUIRED]** 

              The hash key name.

              

            
            - **hashKeyValue** *(string) --* **[REQUIRED]** 

              The hash key value.

              

            
            - **hashKeyType** *(string) --* 

              The hash key type. Valid values are "STRING" or "NUMBER"

              

            
            - **rangeKeyField** *(string) --* 

              The range key name.

              

            
            - **rangeKeyValue** *(string) --* 

              The range key value.

              

            
            - **rangeKeyType** *(string) --* 

              The range key type. Valid values are "STRING" or "NUMBER"

              

            
            - **payloadField** *(string) --* 

              The action payload. This name can be customized.

              

            
          
          - **lambda** *(dict) --* 

            Invoke a Lambda function.

            

          
            - **functionArn** *(string) --* **[REQUIRED]** 

              The ARN of the Lambda function.

              

            
          
          - **sns** *(dict) --* 

            Publish to an Amazon SNS topic.

            

          
            - **targetArn** *(string) --* **[REQUIRED]** 

              The ARN of the SNS topic.

              

            
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access.

              

            
            - **messageFormat** *(string) --* 

              The message format of the message to publish. Optional. Accepted values are "JSON" and "RAW". The default value of the attribute is "RAW". SNS uses this setting to determine if the payload should be parsed and relevant platform-specific bits of the payload should be extracted. To read more about SNS message formats, see `<http://docs.aws.amazon.com/sns/latest/dg/json-formats.html>`_ refer to their official documentation.

              

            
          
          - **sqs** *(dict) --* 

            Publish to an Amazon SQS queue.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access.

              

            
            - **queueUrl** *(string) --* **[REQUIRED]** 

              The URL of the Amazon SQS queue.

              

            
            - **useBase64** *(boolean) --* 

              Specifies whether to use Base64 encoding.

              

            
          
          - **kinesis** *(dict) --* 

            Write data to an Amazon Kinesis stream.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access to the Amazon Kinesis stream.

              

            
            - **streamName** *(string) --* **[REQUIRED]** 

              The name of the Amazon Kinesis stream.

              

            
            - **partitionKey** *(string) --* 

              The partition key.

              

            
          
          - **republish** *(dict) --* 

            Publish to another MQTT topic.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access.

              

            
            - **topic** *(string) --* **[REQUIRED]** 

              The name of the MQTT topic.

              

            
          
          - **s3** *(dict) --* 

            Write to an Amazon S3 bucket.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access.

              

            
            - **bucketName** *(string) --* **[REQUIRED]** 

              The Amazon S3 bucket.

              

            
            - **key** *(string) --* **[REQUIRED]** 

              The object key.

              

            
          
          - **firehose** *(dict) --* 

            Write to an Amazon Kinesis Firehose stream.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The IAM role that grants access to the Amazon Kinesis Firehost stream.

              

            
            - **deliveryStreamName** *(string) --* **[REQUIRED]** 

              The delivery stream name.

              

            
            - **separator** *(string) --* 

              A character separator that will be used to separate records written to the firehose stream. Valid values are: '\n' (newline), '\t' (tab), '\r\n' (Windows newline), ',' (comma).

              

            
          
          - **cloudwatchMetric** *(dict) --* 

            Capture a CloudWatch metric.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The IAM role that allows access to the CloudWatch metric.

              

            
            - **metricNamespace** *(string) --* **[REQUIRED]** 

              The CloudWatch metric namespace name.

              

            
            - **metricName** *(string) --* **[REQUIRED]** 

              The CloudWatch metric name.

              

            
            - **metricValue** *(string) --* **[REQUIRED]** 

              The CloudWatch metric value.

              

            
            - **metricUnit** *(string) --* **[REQUIRED]** 

              The `metric unit`_ supported by CloudWatch.

              

            
            - **metricTimestamp** *(string) --* 

              An optional `Unix timestamp`_ .

              

            
          
          - **cloudwatchAlarm** *(dict) --* 

            Change the state of a CloudWatch alarm.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The IAM role that allows access to the CloudWatch alarm.

              

            
            - **alarmName** *(string) --* **[REQUIRED]** 

              The CloudWatch alarm name.

              

            
            - **stateReason** *(string) --* **[REQUIRED]** 

              The reason for the alarm change.

              

            
            - **stateValue** *(string) --* **[REQUIRED]** 

              The value of the alarm state. Acceptable values are: OK, ALARM, INSUFFICIENT_DATA.

              

            
          
          - **elasticsearch** *(dict) --* 

            Write data to an Amazon Elasticsearch Service; domain.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The IAM role ARN that has access to Elasticsearch.

              

            
            - **endpoint** *(string) --* **[REQUIRED]** 

              The endpoint of your Elasticsearch domain.

              

            
            - **index** *(string) --* **[REQUIRED]** 

              The Elasticsearch index where you want to store your data.

              

            
            - **type** *(string) --* **[REQUIRED]** 

              The type of document you are storing.

              

            
            - **id** *(string) --* **[REQUIRED]** 

              The unique identifier for the document you are storing.

              

            
          
        
    
      - **ruleDisabled** *(boolean) --* 

        Specifies whether the rule is disabled.

        

      
      - **awsIotSqlVersion** *(string) --* 

        The version of the SQL rules engine to use when evaluating the rule.

        

      
    
    
    :returns: None

  .. py:method:: delete_ca_certificate(**kwargs)

    

    Deletes a registered CA certificate.

    

    **Request Syntax** 
    ::

      response = client.delete_ca_certificate(
          certificateId='string'
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The ID of the certificate to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output for the DeleteCACertificate operation.

        
    

  .. py:method:: delete_certificate(**kwargs)

    

    Deletes the specified certificate.

     

    A certificate cannot be deleted if it has a policy attached to it or if its status is set to ACTIVE. To delete a certificate, first use the  DetachPrincipalPolicy API to detach all policies. Next, use the  UpdateCertificate API to set the certificate to the INACTIVE status.

    

    **Request Syntax** 
    ::

      response = client.delete_certificate(
          certificateId='string'
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The ID of the certificate.

      

    
    
    :returns: None

  .. py:method:: delete_policy(**kwargs)

    

    Deletes the specified policy.

     

    A policy cannot be deleted if it has non-default versions or it is attached to any certificate.

     

    To delete a policy, use the DeletePolicyVersion API to delete all non-default versions of the policy; use the DetachPrincipalPolicy API to detach the policy from any certificate; and then use the DeletePolicy API to delete the policy.

     

    When a policy is deleted using DeletePolicy, its default version is deleted with it.

    

    **Request Syntax** 
    ::

      response = client.delete_policy(
          policyName='string'
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The name of the policy to delete.

      

    
    
    :returns: None

  .. py:method:: delete_policy_version(**kwargs)

    

    Deletes the specified version of the specified policy. You cannot delete the default version of a policy using this API. To delete the default version of a policy, use  DeletePolicy . To find out which version of a policy is marked as the default version, use ListPolicyVersions.

    

    **Request Syntax** 
    ::

      response = client.delete_policy_version(
          policyName='string',
          policyVersionId='string'
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The name of the policy.

      

    
    :type policyVersionId: string
    :param policyVersionId: **[REQUIRED]** 

      The policy version ID.

      

    
    
    :returns: None

  .. py:method:: delete_registration_code()

    

    Deletes a CA certificate registration code.

    

    **Request Syntax** 
    ::

      response = client.delete_registration_code()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output for the DeleteRegistrationCode operation. 

        
    

  .. py:method:: delete_thing(**kwargs)

    

    Deletes the specified thing.

    

    **Request Syntax** 
    ::

      response = client.delete_thing(
          thingName='string',
          expectedVersion=123
      )
    :type thingName: string
    :param thingName: **[REQUIRED]** 

      The name of the thing to delete.

      

    
    :type expectedVersion: integer
    :param expectedVersion: 

      The expected version of the thing record in the registry. If the version of the record in the registry does not match the expected version specified in the request, the ``DeleteThing`` request is rejected with a ``VersionConflictException`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output of the DeleteThing operation.

        
    

  .. py:method:: delete_thing_type(**kwargs)

    

    Deletes the specified thing type . You cannot delete a thing type if it has things associated with it. To delete a thing type, first mark it as deprecated by calling  DeprecateThingType , then remove any associated things by calling  UpdateThing to change the thing type on any associated thing, and finally use  DeleteThingType to delete the thing type.

    

    **Request Syntax** 
    ::

      response = client.delete_thing_type(
          thingTypeName='string'
      )
    :type thingTypeName: string
    :param thingTypeName: **[REQUIRED]** 

      The name of the thing type.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output for the DeleteThingType operation.

        
    

  .. py:method:: delete_topic_rule(**kwargs)

    

    Deletes the specified rule.

    

    **Request Syntax** 
    ::

      response = client.delete_topic_rule(
          ruleName='string'
      )
    :type ruleName: string
    :param ruleName: **[REQUIRED]** 

      The name of the rule.

      

    
    
    :returns: None

  .. py:method:: deprecate_thing_type(**kwargs)

    

    Deprecates a thing type. You can not associate new things with deprecated thing type.

    

    **Request Syntax** 
    ::

      response = client.deprecate_thing_type(
          thingTypeName='string',
          undoDeprecate=True|False
      )
    :type thingTypeName: string
    :param thingTypeName: **[REQUIRED]** 

      The name of the thing type to deprecate.

      

    
    :type undoDeprecate: boolean
    :param undoDeprecate: 

      Whether to undeprecate a deprecated thing type. If **true** , the thing type will not be deprecated anymore and you can associate it with things.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output for the DeprecateThingType operation.

        
    

  .. py:method:: describe_ca_certificate(**kwargs)

    

    Describes a registered CA certificate.

    

    **Request Syntax** 
    ::

      response = client.describe_ca_certificate(
          certificateId='string'
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The CA certificate identifier.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'certificateDescription': {
                'certificateArn': 'string',
                'certificateId': 'string',
                'status': 'ACTIVE'|'INACTIVE',
                'certificatePem': 'string',
                'ownedBy': 'string',
                'creationDate': datetime(2015, 1, 1),
                'autoRegistrationStatus': 'ENABLE'|'DISABLE'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the DescribeCACertificate operation.

        
        

        - **certificateDescription** *(dict) --* 

          The CA certificate description.

          
          

          - **certificateArn** *(string) --* 

            The CA certificate ARN.

            
          

          - **certificateId** *(string) --* 

            The CA certificate ID.

            
          

          - **status** *(string) --* 

            The status of a CA certificate.

            
          

          - **certificatePem** *(string) --* 

            The CA certificate data, in PEM format.

            
          

          - **ownedBy** *(string) --* 

            The owner of the CA certificate.

            
          

          - **creationDate** *(datetime) --* 

            The date the CA certificate was created.

            
          

          - **autoRegistrationStatus** *(string) --* 

            Whether the CA certificate configured for auto registration of device certificates. Valid values are "ENABLE" and "DISABLE"

            
      
    

  .. py:method:: describe_certificate(**kwargs)

    

    Gets information about the specified certificate.

    

    **Request Syntax** 
    ::

      response = client.describe_certificate(
          certificateId='string'
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The ID of the certificate.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'certificateDescription': {
                'certificateArn': 'string',
                'certificateId': 'string',
                'caCertificateId': 'string',
                'status': 'ACTIVE'|'INACTIVE'|'REVOKED'|'PENDING_TRANSFER'|'REGISTER_INACTIVE'|'PENDING_ACTIVATION',
                'certificatePem': 'string',
                'ownedBy': 'string',
                'previousOwnedBy': 'string',
                'creationDate': datetime(2015, 1, 1),
                'lastModifiedDate': datetime(2015, 1, 1),
                'transferData': {
                    'transferMessage': 'string',
                    'rejectReason': 'string',
                    'transferDate': datetime(2015, 1, 1),
                    'acceptDate': datetime(2015, 1, 1),
                    'rejectDate': datetime(2015, 1, 1)
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output of the DescribeCertificate operation.

        
        

        - **certificateDescription** *(dict) --* 

          The description of the certificate.

          
          

          - **certificateArn** *(string) --* 

            The ARN of the certificate.

            
          

          - **certificateId** *(string) --* 

            The ID of the certificate.

            
          

          - **caCertificateId** *(string) --* 

            The certificate ID of the CA certificate used to sign this certificate.

            
          

          - **status** *(string) --* 

            The status of the certificate.

            
          

          - **certificatePem** *(string) --* 

            The certificate data, in PEM format.

            
          

          - **ownedBy** *(string) --* 

            The ID of the AWS account that owns the certificate.

            
          

          - **previousOwnedBy** *(string) --* 

            The ID of the AWS account of the previous owner of the certificate.

            
          

          - **creationDate** *(datetime) --* 

            The date and time the certificate was created.

            
          

          - **lastModifiedDate** *(datetime) --* 

            The date and time the certificate was last modified.

            
          

          - **transferData** *(dict) --* 

            The transfer data.

            
            

            - **transferMessage** *(string) --* 

              The transfer message.

              
            

            - **rejectReason** *(string) --* 

              The reason why the transfer was rejected.

              
            

            - **transferDate** *(datetime) --* 

              The date the transfer took place.

              
            

            - **acceptDate** *(datetime) --* 

              The date the transfer was accepted.

              
            

            - **rejectDate** *(datetime) --* 

              The date the transfer was rejected.

              
        
      
    

  .. py:method:: describe_endpoint()

    

    Returns a unique endpoint specific to the AWS account making the call.

    

    **Request Syntax** 
    ::

      response = client.describe_endpoint()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'endpointAddress': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the DescribeEndpoint operation.

        
        

        - **endpointAddress** *(string) --* 

          The endpoint. The format of the endpoint is as follows: *identifier* .iot.*region* .amazonaws.com.

          
    

  .. py:method:: describe_thing(**kwargs)

    

    Gets information about the specified thing.

    

    **Request Syntax** 
    ::

      response = client.describe_thing(
          thingName='string'
      )
    :type thingName: string
    :param thingName: **[REQUIRED]** 

      The name of the thing.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'defaultClientId': 'string',
            'thingName': 'string',
            'thingTypeName': 'string',
            'attributes': {
                'string': 'string'
            },
            'version': 123
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the DescribeThing operation.

        
        

        - **defaultClientId** *(string) --* 

          The default client ID.

          
        

        - **thingName** *(string) --* 

          The name of the thing.

          
        

        - **thingTypeName** *(string) --* 

          The thing type name.

          
        

        - **attributes** *(dict) --* 

          The thing attributes.

          
          

          - *(string) --* 
            

            - *(string) --* An attribute value for an Thing. An empty or null value in Update means that existing value for that attribute should be deleted. Empty and null values in create are ignored.
      
    
        

        - **version** *(integer) --* 

          The current version of the thing record in the registry.

           

          .. note::

             

            To avoid unintentional changes to the information in the registry, you can pass the version information in the ``expectedVersion`` parameter of the ``UpdateThing`` and ``DeleteThing`` calls.

             

          
    

  .. py:method:: describe_thing_type(**kwargs)

    

    Gets information about the specified thing type.

    

    **Request Syntax** 
    ::

      response = client.describe_thing_type(
          thingTypeName='string'
      )
    :type thingTypeName: string
    :param thingTypeName: **[REQUIRED]** 

      The name of the thing type.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'thingTypeName': 'string',
            'thingTypeProperties': {
                'thingTypeDescription': 'string',
                'searchableAttributes': [
                    'string',
                ]
            },
            'thingTypeMetadata': {
                'deprecated': True|False,
                'deprecationDate': datetime(2015, 1, 1),
                'creationDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the DescribeThingType operation.

        
        

        - **thingTypeName** *(string) --* 

          The name of the thing type.

          
        

        - **thingTypeProperties** *(dict) --* 

          The ThingTypeProperties contains information about the thing type including description, and a list of searchable thing attribute names.

          
          

          - **thingTypeDescription** *(string) --* 

            The description of the thing type.

            
          

          - **searchableAttributes** *(list) --* 

            A list of searchable thing attribute names.

            
            

            - *(string) --* 
        
      
        

        - **thingTypeMetadata** *(dict) --* 

          The ThingTypeMetadata contains additional information about the thing type including: creation date and time, a value indicating whether the thing type is deprecated, and a date and time when time was deprecated.

          
          

          - **deprecated** *(boolean) --* 

            Whether the thing type is deprecated. If **true** , no new things could be associated with this type.

            
          

          - **deprecationDate** *(datetime) --* 

            The date and time when the thing type was deprecated.

            
          

          - **creationDate** *(datetime) --* 

            The date and time when the thing type was created.

            
      
    

  .. py:method:: detach_principal_policy(**kwargs)

    

    Removes the specified policy from the specified certificate.

    

    **Request Syntax** 
    ::

      response = client.detach_principal_policy(
          policyName='string',
          principal='string'
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The name of the policy to detach.

      

    
    :type principal: string
    :param principal: **[REQUIRED]** 

      The principal.

       

      If the principal is a certificate, specify the certificate ARN. If the principal is an Amazon Cognito identity, specify the identity ID.

      

    
    
    :returns: None

  .. py:method:: detach_thing_principal(**kwargs)

    

    Detaches the specified principal from the specified thing.

    

    **Request Syntax** 
    ::

      response = client.detach_thing_principal(
          thingName='string',
          principal='string'
      )
    :type thingName: string
    :param thingName: **[REQUIRED]** 

      The name of the thing.

      

    
    :type principal: string
    :param principal: **[REQUIRED]** 

      If the principal is a certificate, this value must be ARN of the certificate. If the principal is an Amazon Cognito identity, this value must be the ID of the Amazon Cognito identity.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output from the DetachThingPrincipal operation.

        
    

  .. py:method:: disable_topic_rule(**kwargs)

    

    Disables the specified rule.

    

    **Request Syntax** 
    ::

      response = client.disable_topic_rule(
          ruleName='string'
      )
    :type ruleName: string
    :param ruleName: **[REQUIRED]** 

      The name of the rule to disable.

      

    
    
    :returns: None

  .. py:method:: enable_topic_rule(**kwargs)

    

    Enables the specified rule.

    

    **Request Syntax** 
    ::

      response = client.enable_topic_rule(
          ruleName='string'
      )
    :type ruleName: string
    :param ruleName: **[REQUIRED]** 

      The name of the topic rule to enable.

      

    
    
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


  .. py:method:: get_logging_options()

    

    Gets the logging options.

    

    **Request Syntax** 
    ::

      response = client.get_logging_options()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'roleArn': 'string',
            'logLevel': 'DEBUG'|'INFO'|'ERROR'|'WARN'|'DISABLED'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the GetLoggingOptions operation.

        
        

        - **roleArn** *(string) --* 

          The ARN of the IAM role that grants access.

          
        

        - **logLevel** *(string) --* 

          The logging level.

          
    

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


  .. py:method:: get_policy(**kwargs)

    

    Gets information about the specified policy with the policy document of the default version.

    

    **Request Syntax** 
    ::

      response = client.get_policy(
          policyName='string'
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The name of the policy.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'policyName': 'string',
            'policyArn': 'string',
            'policyDocument': 'string',
            'defaultVersionId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the GetPolicy operation.

        
        

        - **policyName** *(string) --* 

          The policy name.

          
        

        - **policyArn** *(string) --* 

          The policy ARN.

          
        

        - **policyDocument** *(string) --* 

          The JSON document that describes the policy.

          
        

        - **defaultVersionId** *(string) --* 

          The default policy version ID.

          
    

  .. py:method:: get_policy_version(**kwargs)

    

    Gets information about the specified policy version.

    

    **Request Syntax** 
    ::

      response = client.get_policy_version(
          policyName='string',
          policyVersionId='string'
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The name of the policy.

      

    
    :type policyVersionId: string
    :param policyVersionId: **[REQUIRED]** 

      The policy version ID.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'policyArn': 'string',
            'policyName': 'string',
            'policyDocument': 'string',
            'policyVersionId': 'string',
            'isDefaultVersion': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the GetPolicyVersion operation.

        
        

        - **policyArn** *(string) --* 

          The policy ARN.

          
        

        - **policyName** *(string) --* 

          The policy name.

          
        

        - **policyDocument** *(string) --* 

          The JSON document that describes the policy.

          
        

        - **policyVersionId** *(string) --* 

          The policy version ID.

          
        

        - **isDefaultVersion** *(boolean) --* 

          Specifies whether the policy version is the default.

          
    

  .. py:method:: get_registration_code()

    

    Gets a registration code used to register a CA certificate with AWS IoT.

    

    **Request Syntax** 
    ::

      response = client.get_registration_code()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'registrationCode': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the GetRegistrationCode operation.

        
        

        - **registrationCode** *(string) --* 

          The CA certificate registration code.

          
    

  .. py:method:: get_topic_rule(**kwargs)

    

    Gets information about the specified rule.

    

    **Request Syntax** 
    ::

      response = client.get_topic_rule(
          ruleName='string'
      )
    :type ruleName: string
    :param ruleName: **[REQUIRED]** 

      The name of the rule.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ruleArn': 'string',
            'rule': {
                'ruleName': 'string',
                'sql': 'string',
                'description': 'string',
                'createdAt': datetime(2015, 1, 1),
                'actions': [
                    {
                        'dynamoDB': {
                            'tableName': 'string',
                            'roleArn': 'string',
                            'operation': 'string',
                            'hashKeyField': 'string',
                            'hashKeyValue': 'string',
                            'hashKeyType': 'STRING'|'NUMBER',
                            'rangeKeyField': 'string',
                            'rangeKeyValue': 'string',
                            'rangeKeyType': 'STRING'|'NUMBER',
                            'payloadField': 'string'
                        },
                        'lambda': {
                            'functionArn': 'string'
                        },
                        'sns': {
                            'targetArn': 'string',
                            'roleArn': 'string',
                            'messageFormat': 'RAW'|'JSON'
                        },
                        'sqs': {
                            'roleArn': 'string',
                            'queueUrl': 'string',
                            'useBase64': True|False
                        },
                        'kinesis': {
                            'roleArn': 'string',
                            'streamName': 'string',
                            'partitionKey': 'string'
                        },
                        'republish': {
                            'roleArn': 'string',
                            'topic': 'string'
                        },
                        's3': {
                            'roleArn': 'string',
                            'bucketName': 'string',
                            'key': 'string'
                        },
                        'firehose': {
                            'roleArn': 'string',
                            'deliveryStreamName': 'string',
                            'separator': 'string'
                        },
                        'cloudwatchMetric': {
                            'roleArn': 'string',
                            'metricNamespace': 'string',
                            'metricName': 'string',
                            'metricValue': 'string',
                            'metricUnit': 'string',
                            'metricTimestamp': 'string'
                        },
                        'cloudwatchAlarm': {
                            'roleArn': 'string',
                            'alarmName': 'string',
                            'stateReason': 'string',
                            'stateValue': 'string'
                        },
                        'elasticsearch': {
                            'roleArn': 'string',
                            'endpoint': 'string',
                            'index': 'string',
                            'type': 'string',
                            'id': 'string'
                        }
                    },
                ],
                'ruleDisabled': True|False,
                'awsIotSqlVersion': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the GetTopicRule operation.

        
        

        - **ruleArn** *(string) --* 

          The rule ARN.

          
        

        - **rule** *(dict) --* 

          The rule.

          
          

          - **ruleName** *(string) --* 

            The name of the rule.

            
          

          - **sql** *(string) --* 

            The SQL statement used to query the topic. When using a SQL query with multiple lines, be sure to escape the newline characters.

            
          

          - **description** *(string) --* 

            The description of the rule.

            
          

          - **createdAt** *(datetime) --* 

            The date and time the rule was created.

            
          

          - **actions** *(list) --* 

            The actions associated with the rule.

            
            

            - *(dict) --* 

              Describes the actions associated with a rule.

              
              

              - **dynamoDB** *(dict) --* 

                Write to a DynamoDB table.

                
                

                - **tableName** *(string) --* 

                  The name of the DynamoDB table.

                  
                

                - **roleArn** *(string) --* 

                  The ARN of the IAM role that grants access to the DynamoDB table.

                  
                

                - **operation** *(string) --* 

                  The type of operation to be performed. This follows the substitution template, so it can be ``${operation}`` , but the substitution must result in one of the following: ``INSERT`` , ``UPDATE`` , or ``DELETE`` .

                  
                

                - **hashKeyField** *(string) --* 

                  The hash key name.

                  
                

                - **hashKeyValue** *(string) --* 

                  The hash key value.

                  
                

                - **hashKeyType** *(string) --* 

                  The hash key type. Valid values are "STRING" or "NUMBER"

                  
                

                - **rangeKeyField** *(string) --* 

                  The range key name.

                  
                

                - **rangeKeyValue** *(string) --* 

                  The range key value.

                  
                

                - **rangeKeyType** *(string) --* 

                  The range key type. Valid values are "STRING" or "NUMBER"

                  
                

                - **payloadField** *(string) --* 

                  The action payload. This name can be customized.

                  
            
              

              - **lambda** *(dict) --* 

                Invoke a Lambda function.

                
                

                - **functionArn** *(string) --* 

                  The ARN of the Lambda function.

                  
            
              

              - **sns** *(dict) --* 

                Publish to an Amazon SNS topic.

                
                

                - **targetArn** *(string) --* 

                  The ARN of the SNS topic.

                  
                

                - **roleArn** *(string) --* 

                  The ARN of the IAM role that grants access.

                  
                

                - **messageFormat** *(string) --* 

                  The message format of the message to publish. Optional. Accepted values are "JSON" and "RAW". The default value of the attribute is "RAW". SNS uses this setting to determine if the payload should be parsed and relevant platform-specific bits of the payload should be extracted. To read more about SNS message formats, see `<http://docs.aws.amazon.com/sns/latest/dg/json-formats.html>`_ refer to their official documentation.

                  
            
              

              - **sqs** *(dict) --* 

                Publish to an Amazon SQS queue.

                
                

                - **roleArn** *(string) --* 

                  The ARN of the IAM role that grants access.

                  
                

                - **queueUrl** *(string) --* 

                  The URL of the Amazon SQS queue.

                  
                

                - **useBase64** *(boolean) --* 

                  Specifies whether to use Base64 encoding.

                  
            
              

              - **kinesis** *(dict) --* 

                Write data to an Amazon Kinesis stream.

                
                

                - **roleArn** *(string) --* 

                  The ARN of the IAM role that grants access to the Amazon Kinesis stream.

                  
                

                - **streamName** *(string) --* 

                  The name of the Amazon Kinesis stream.

                  
                

                - **partitionKey** *(string) --* 

                  The partition key.

                  
            
              

              - **republish** *(dict) --* 

                Publish to another MQTT topic.

                
                

                - **roleArn** *(string) --* 

                  The ARN of the IAM role that grants access.

                  
                

                - **topic** *(string) --* 

                  The name of the MQTT topic.

                  
            
              

              - **s3** *(dict) --* 

                Write to an Amazon S3 bucket.

                
                

                - **roleArn** *(string) --* 

                  The ARN of the IAM role that grants access.

                  
                

                - **bucketName** *(string) --* 

                  The Amazon S3 bucket.

                  
                

                - **key** *(string) --* 

                  The object key.

                  
            
              

              - **firehose** *(dict) --* 

                Write to an Amazon Kinesis Firehose stream.

                
                

                - **roleArn** *(string) --* 

                  The IAM role that grants access to the Amazon Kinesis Firehost stream.

                  
                

                - **deliveryStreamName** *(string) --* 

                  The delivery stream name.

                  
                

                - **separator** *(string) --* 

                  A character separator that will be used to separate records written to the firehose stream. Valid values are: '\n' (newline), '\t' (tab), '\r\n' (Windows newline), ',' (comma).

                  
            
              

              - **cloudwatchMetric** *(dict) --* 

                Capture a CloudWatch metric.

                
                

                - **roleArn** *(string) --* 

                  The IAM role that allows access to the CloudWatch metric.

                  
                

                - **metricNamespace** *(string) --* 

                  The CloudWatch metric namespace name.

                  
                

                - **metricName** *(string) --* 

                  The CloudWatch metric name.

                  
                

                - **metricValue** *(string) --* 

                  The CloudWatch metric value.

                  
                

                - **metricUnit** *(string) --* 

                  The `metric unit`_ supported by CloudWatch.

                  
                

                - **metricTimestamp** *(string) --* 

                  An optional `Unix timestamp`_ .

                  
            
              

              - **cloudwatchAlarm** *(dict) --* 

                Change the state of a CloudWatch alarm.

                
                

                - **roleArn** *(string) --* 

                  The IAM role that allows access to the CloudWatch alarm.

                  
                

                - **alarmName** *(string) --* 

                  The CloudWatch alarm name.

                  
                

                - **stateReason** *(string) --* 

                  The reason for the alarm change.

                  
                

                - **stateValue** *(string) --* 

                  The value of the alarm state. Acceptable values are: OK, ALARM, INSUFFICIENT_DATA.

                  
            
              

              - **elasticsearch** *(dict) --* 

                Write data to an Amazon Elasticsearch Service; domain.

                
                

                - **roleArn** *(string) --* 

                  The IAM role ARN that has access to Elasticsearch.

                  
                

                - **endpoint** *(string) --* 

                  The endpoint of your Elasticsearch domain.

                  
                

                - **index** *(string) --* 

                  The Elasticsearch index where you want to store your data.

                  
                

                - **type** *(string) --* 

                  The type of document you are storing.

                  
                

                - **id** *(string) --* 

                  The unique identifier for the document you are storing.

                  
            
          
        
          

          - **ruleDisabled** *(boolean) --* 

            Specifies whether the rule is disabled.

            
          

          - **awsIotSqlVersion** *(string) --* 

            The version of the SQL rules engine to use when evaluating the rule.

            
      
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: list_ca_certificates(**kwargs)

    

    Lists the CA certificates registered for your AWS account.

     

    The results are paginated with a default page size of 25. You can use the returned marker to retrieve additional results.

    

    **Request Syntax** 
    ::

      response = client.list_ca_certificates(
          pageSize=123,
          marker='string',
          ascendingOrder=True|False
      )
    :type pageSize: integer
    :param pageSize: 

      The result page size.

      

    
    :type marker: string
    :param marker: 

      The marker for the next set of results.

      

    
    :type ascendingOrder: boolean
    :param ascendingOrder: 

      Determines the order of the results.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'certificates': [
                {
                    'certificateArn': 'string',
                    'certificateId': 'string',
                    'status': 'ACTIVE'|'INACTIVE',
                    'creationDate': datetime(2015, 1, 1)
                },
            ],
            'nextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListCACertificates operation.

        
        

        - **certificates** *(list) --* 

          The CA certificates registered in your AWS account.

          
          

          - *(dict) --* 

            A CA certificate.

            
            

            - **certificateArn** *(string) --* 

              The ARN of the CA certificate.

              
            

            - **certificateId** *(string) --* 

              The ID of the CA certificate.

              
            

            - **status** *(string) --* 

              The status of the CA certificate. 

               

              The status value REGISTER_INACTIVE is deprecated and should not be used.

              
            

            - **creationDate** *(datetime) --* 

              The date the CA certificate was created.

              
        
      
        

        - **nextMarker** *(string) --* 

          The current position within the list of CA certificates.

          
    

  .. py:method:: list_certificates(**kwargs)

    

    Lists the certificates registered in your AWS account.

     

    The results are paginated with a default page size of 25. You can use the returned marker to retrieve additional results.

    

    **Request Syntax** 
    ::

      response = client.list_certificates(
          pageSize=123,
          marker='string',
          ascendingOrder=True|False
      )
    :type pageSize: integer
    :param pageSize: 

      The result page size.

      

    
    :type marker: string
    :param marker: 

      The marker for the next set of results.

      

    
    :type ascendingOrder: boolean
    :param ascendingOrder: 

      Specifies the order for results. If True, the results are returned in ascending order, based on the creation date.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'certificates': [
                {
                    'certificateArn': 'string',
                    'certificateId': 'string',
                    'status': 'ACTIVE'|'INACTIVE'|'REVOKED'|'PENDING_TRANSFER'|'REGISTER_INACTIVE'|'PENDING_ACTIVATION',
                    'creationDate': datetime(2015, 1, 1)
                },
            ],
            'nextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output of the ListCertificates operation.

        
        

        - **certificates** *(list) --* 

          The descriptions of the certificates.

          
          

          - *(dict) --* 

            Information about a certificate.

            
            

            - **certificateArn** *(string) --* 

              The ARN of the certificate.

              
            

            - **certificateId** *(string) --* 

              The ID of the certificate.

              
            

            - **status** *(string) --* 

              The status of the certificate.

               

              The status value REGISTER_INACTIVE is deprecated and should not be used.

              
            

            - **creationDate** *(datetime) --* 

              The date and time the certificate was created.

              
        
      
        

        - **nextMarker** *(string) --* 

          The marker for the next set of results, or null if there are no additional results.

          
    

  .. py:method:: list_certificates_by_ca(**kwargs)

    

    List the device certificates signed by the specified CA certificate.

    

    **Request Syntax** 
    ::

      response = client.list_certificates_by_ca(
          caCertificateId='string',
          pageSize=123,
          marker='string',
          ascendingOrder=True|False
      )
    :type caCertificateId: string
    :param caCertificateId: **[REQUIRED]** 

      The ID of the CA certificate. This operation will list all registered device certificate that were signed by this CA certificate. 

      

    
    :type pageSize: integer
    :param pageSize: 

      The result page size.

      

    
    :type marker: string
    :param marker: 

      The marker for the next set of results.

      

    
    :type ascendingOrder: boolean
    :param ascendingOrder: 

      Specifies the order for results. If True, the results are returned in ascending order, based on the creation date.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'certificates': [
                {
                    'certificateArn': 'string',
                    'certificateId': 'string',
                    'status': 'ACTIVE'|'INACTIVE'|'REVOKED'|'PENDING_TRANSFER'|'REGISTER_INACTIVE'|'PENDING_ACTIVATION',
                    'creationDate': datetime(2015, 1, 1)
                },
            ],
            'nextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output of the ListCertificatesByCA operation.

        
        

        - **certificates** *(list) --* 

          The device certificates signed by the specified CA certificate.

          
          

          - *(dict) --* 

            Information about a certificate.

            
            

            - **certificateArn** *(string) --* 

              The ARN of the certificate.

              
            

            - **certificateId** *(string) --* 

              The ID of the certificate.

              
            

            - **status** *(string) --* 

              The status of the certificate.

               

              The status value REGISTER_INACTIVE is deprecated and should not be used.

              
            

            - **creationDate** *(datetime) --* 

              The date and time the certificate was created.

              
        
      
        

        - **nextMarker** *(string) --* 

          The marker for the next set of results, or null if there are no additional results.

          
    

  .. py:method:: list_outgoing_certificates(**kwargs)

    

    Lists certificates that are being transfered but not yet accepted.

    

    **Request Syntax** 
    ::

      response = client.list_outgoing_certificates(
          pageSize=123,
          marker='string',
          ascendingOrder=True|False
      )
    :type pageSize: integer
    :param pageSize: 

      The result page size.

      

    
    :type marker: string
    :param marker: 

      The marker for the next set of results.

      

    
    :type ascendingOrder: boolean
    :param ascendingOrder: 

      Specifies the order for results. If True, the results are returned in ascending order, based on the creation date.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'outgoingCertificates': [
                {
                    'certificateArn': 'string',
                    'certificateId': 'string',
                    'transferredTo': 'string',
                    'transferDate': datetime(2015, 1, 1),
                    'transferMessage': 'string',
                    'creationDate': datetime(2015, 1, 1)
                },
            ],
            'nextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListOutgoingCertificates operation.

        
        

        - **outgoingCertificates** *(list) --* 

          The certificates that are being transfered but not yet accepted.

          
          

          - *(dict) --* 

            A certificate that has been transfered but not yet accepted.

            
            

            - **certificateArn** *(string) --* 

              The certificate ARN.

              
            

            - **certificateId** *(string) --* 

              The certificate ID.

              
            

            - **transferredTo** *(string) --* 

              The AWS account to which the transfer was made.

              
            

            - **transferDate** *(datetime) --* 

              The date the transfer was initiated.

              
            

            - **transferMessage** *(string) --* 

              The transfer message.

              
            

            - **creationDate** *(datetime) --* 

              The certificate creation date.

              
        
      
        

        - **nextMarker** *(string) --* 

          The marker for the next set of results.

          
    

  .. py:method:: list_policies(**kwargs)

    

    Lists your policies.

    

    **Request Syntax** 
    ::

      response = client.list_policies(
          marker='string',
          pageSize=123,
          ascendingOrder=True|False
      )
    :type marker: string
    :param marker: 

      The marker for the next set of results.

      

    
    :type pageSize: integer
    :param pageSize: 

      The result page size.

      

    
    :type ascendingOrder: boolean
    :param ascendingOrder: 

      Specifies the order for results. If true, the results are returned in ascending creation order.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'policies': [
                {
                    'policyName': 'string',
                    'policyArn': 'string'
                },
            ],
            'nextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListPolicies operation.

        
        

        - **policies** *(list) --* 

          The descriptions of the policies.

          
          

          - *(dict) --* 

            Describes an AWS IoT policy.

            
            

            - **policyName** *(string) --* 

              The policy name.

              
            

            - **policyArn** *(string) --* 

              The policy ARN.

              
        
      
        

        - **nextMarker** *(string) --* 

          The marker for the next set of results, or null if there are no additional results.

          
    

  .. py:method:: list_policy_principals(**kwargs)

    

    Lists the principals associated with the specified policy.

    

    **Request Syntax** 
    ::

      response = client.list_policy_principals(
          policyName='string',
          marker='string',
          pageSize=123,
          ascendingOrder=True|False
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The policy name.

      

    
    :type marker: string
    :param marker: 

      The marker for the next set of results.

      

    
    :type pageSize: integer
    :param pageSize: 

      The result page size.

      

    
    :type ascendingOrder: boolean
    :param ascendingOrder: 

      Specifies the order for results. If true, the results are returned in ascending creation order.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'principals': [
                'string',
            ],
            'nextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListPolicyPrincipals operation.

        
        

        - **principals** *(list) --* 

          The descriptions of the principals.

          
          

          - *(string) --* 
      
        

        - **nextMarker** *(string) --* 

          The marker for the next set of results, or null if there are no additional results.

          
    

  .. py:method:: list_policy_versions(**kwargs)

    

    Lists the versions of the specified policy and identifies the default version.

    

    **Request Syntax** 
    ::

      response = client.list_policy_versions(
          policyName='string'
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The policy name.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'policyVersions': [
                {
                    'versionId': 'string',
                    'isDefaultVersion': True|False,
                    'createDate': datetime(2015, 1, 1)
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListPolicyVersions operation.

        
        

        - **policyVersions** *(list) --* 

          The policy versions.

          
          

          - *(dict) --* 

            Describes a policy version.

            
            

            - **versionId** *(string) --* 

              The policy version ID.

              
            

            - **isDefaultVersion** *(boolean) --* 

              Specifies whether the policy version is the default.

              
            

            - **createDate** *(datetime) --* 

              The date and time the policy was created.

              
        
      
    

  .. py:method:: list_principal_policies(**kwargs)

    

    Lists the policies attached to the specified principal. If you use an Cognito identity, the ID must be in `AmazonCognito Identity format`_ .

    

    **Request Syntax** 
    ::

      response = client.list_principal_policies(
          principal='string',
          marker='string',
          pageSize=123,
          ascendingOrder=True|False
      )
    :type principal: string
    :param principal: **[REQUIRED]** 

      The principal.

      

    
    :type marker: string
    :param marker: 

      The marker for the next set of results.

      

    
    :type pageSize: integer
    :param pageSize: 

      The result page size.

      

    
    :type ascendingOrder: boolean
    :param ascendingOrder: 

      Specifies the order for results. If true, results are returned in ascending creation order.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'policies': [
                {
                    'policyName': 'string',
                    'policyArn': 'string'
                },
            ],
            'nextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListPrincipalPolicies operation.

        
        

        - **policies** *(list) --* 

          The policies.

          
          

          - *(dict) --* 

            Describes an AWS IoT policy.

            
            

            - **policyName** *(string) --* 

              The policy name.

              
            

            - **policyArn** *(string) --* 

              The policy ARN.

              
        
      
        

        - **nextMarker** *(string) --* 

          The marker for the next set of results, or null if there are no additional results.

          
    

  .. py:method:: list_principal_things(**kwargs)

    

    Lists the things associated with the specified principal.

    

    **Request Syntax** 
    ::

      response = client.list_principal_things(
          nextToken='string',
          maxResults=123,
          principal='string'
      )
    :type nextToken: string
    :param nextToken: 

      The token for the next set of results, or **null** if there are no additional results.

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of results to return in this operation.

      

    
    :type principal: string
    :param principal: **[REQUIRED]** 

      The principal.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'things': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListPrincipalThings operation.

        
        

        - **things** *(list) --* 

          The things.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          The token for the next set of results, or **null** if there are no additional results.

          
    

  .. py:method:: list_thing_principals(**kwargs)

    

    Lists the principals associated with the specified thing.

    

    **Request Syntax** 
    ::

      response = client.list_thing_principals(
          thingName='string'
      )
    :type thingName: string
    :param thingName: **[REQUIRED]** 

      The name of the thing.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'principals': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListThingPrincipals operation.

        
        

        - **principals** *(list) --* 

          The principals associated with the thing.

          
          

          - *(string) --* 
      
    

  .. py:method:: list_thing_types(**kwargs)

    

    Lists the existing thing types.

    

    **Request Syntax** 
    ::

      response = client.list_thing_types(
          nextToken='string',
          maxResults=123,
          thingTypeName='string'
      )
    :type nextToken: string
    :param nextToken: 

      The token for the next set of results, or **null** if there are no additional results.

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of results to return in this operation.

      

    
    :type thingTypeName: string
    :param thingTypeName: 

      The name of the thing type.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'thingTypes': [
                {
                    'thingTypeName': 'string',
                    'thingTypeProperties': {
                        'thingTypeDescription': 'string',
                        'searchableAttributes': [
                            'string',
                        ]
                    },
                    'thingTypeMetadata': {
                        'deprecated': True|False,
                        'deprecationDate': datetime(2015, 1, 1),
                        'creationDate': datetime(2015, 1, 1)
                    }
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output for the ListThingTypes operation.

        
        

        - **thingTypes** *(list) --* 

          The thing types.

          
          

          - *(dict) --* 

            The definition of the thing type, including thing type name and description.

            
            

            - **thingTypeName** *(string) --* 

              The name of the thing type.

              
            

            - **thingTypeProperties** *(dict) --* 

              The ThingTypeProperties for the thing type.

              
              

              - **thingTypeDescription** *(string) --* 

                The description of the thing type.

                
              

              - **searchableAttributes** *(list) --* 

                A list of searchable thing attribute names.

                
                

                - *(string) --* 
            
          
            

            - **thingTypeMetadata** *(dict) --* 

              The ThingTypeMetadata contains additional information about the thing type including: creation date and time, a value indicating whether the thing type is deprecated, and a date and time when time was deprecated.

              
              

              - **deprecated** *(boolean) --* 

                Whether the thing type is deprecated. If **true** , no new things could be associated with this type.

                
              

              - **deprecationDate** *(datetime) --* 

                The date and time when the thing type was deprecated.

                
              

              - **creationDate** *(datetime) --* 

                The date and time when the thing type was created.

                
          
        
      
        

        - **nextToken** *(string) --* 

          The token for the next set of results, or **null** if there are no additional results.

          
    

  .. py:method:: list_things(**kwargs)

    

    Lists your things. Use the **attributeName** and **attributeValue** parameters to filter your things. For example, calling ``ListThings`` with attributeName=Color and attributeValue=Red retrieves all things in the registry that contain an attribute **Color** with the value **Red** . 

    

    **Request Syntax** 
    ::

      response = client.list_things(
          nextToken='string',
          maxResults=123,
          attributeName='string',
          attributeValue='string',
          thingTypeName='string'
      )
    :type nextToken: string
    :param nextToken: 

      The token for the next set of results, or **null** if there are no additional results.

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of results to return in this operation.

      

    
    :type attributeName: string
    :param attributeName: 

      The attribute name used to search for things.

      

    
    :type attributeValue: string
    :param attributeValue: 

      The attribute value used to search for things.

      

    
    :type thingTypeName: string
    :param thingTypeName: 

      The name of the thing type used to search for things.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'things': [
                {
                    'thingName': 'string',
                    'thingTypeName': 'string',
                    'attributes': {
                        'string': 'string'
                    },
                    'version': 123
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListThings operation.

        
        

        - **things** *(list) --* 

          The things.

          
          

          - *(dict) --* 

            The properties of the thing, including thing name, thing type name, and a list of thing attributes.

            
            

            - **thingName** *(string) --* 

              The name of the thing.

              
            

            - **thingTypeName** *(string) --* 

              The name of the thing type, if the thing has been associated with a type.

              
            

            - **attributes** *(dict) --* 

              A list of thing attributes which are name-value pairs.

              
              

              - *(string) --* 
                

                - *(string) --* An attribute value for an Thing. An empty or null value in Update means that existing value for that attribute should be deleted. Empty and null values in create are ignored.
          
        
            

            - **version** *(integer) --* 

              The version of the thing record in the registry.

              
        
      
        

        - **nextToken** *(string) --* 

          The token for the next set of results, or **null** if there are no additional results.

          
    

  .. py:method:: list_topic_rules(**kwargs)

    

    Lists the rules for the specific topic.

    

    **Request Syntax** 
    ::

      response = client.list_topic_rules(
          topic='string',
          maxResults=123,
          nextToken='string',
          ruleDisabled=True|False
      )
    :type topic: string
    :param topic: 

      The topic.

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of results to return.

      

    
    :type nextToken: string
    :param nextToken: 

      A token used to retrieve the next value.

      

    
    :type ruleDisabled: boolean
    :param ruleDisabled: 

      Specifies whether the rule is disabled.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'rules': [
                {
                    'ruleArn': 'string',
                    'ruleName': 'string',
                    'topicPattern': 'string',
                    'createdAt': datetime(2015, 1, 1),
                    'ruleDisabled': True|False
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the ListTopicRules operation.

        
        

        - **rules** *(list) --* 

          The rules.

          
          

          - *(dict) --* 

            Describes a rule.

            
            

            - **ruleArn** *(string) --* 

              The rule ARN.

              
            

            - **ruleName** *(string) --* 

              The name of the rule.

              
            

            - **topicPattern** *(string) --* 

              The pattern for the topic names that apply.

              
            

            - **createdAt** *(datetime) --* 

              The date and time the rule was created.

              
            

            - **ruleDisabled** *(boolean) --* 

              Specifies whether the rule is disabled.

              
        
      
        

        - **nextToken** *(string) --* 

          A token used to retrieve the next value.

          
    

  .. py:method:: register_ca_certificate(**kwargs)

    

    Registers a CA certificate with AWS IoT. This CA certificate can then be used to sign device certificates, which can be then registered with AWS IoT. You can register up to 10 CA certificates per AWS account that have the same subject field and public key. This enables you to have up to 10 certificate authorities sign your device certificates. If you have more than one CA certificate registered, make sure you pass the CA certificate when you register your device certificates with the RegisterCertificate API.

    

    **Request Syntax** 
    ::

      response = client.register_ca_certificate(
          caCertificate='string',
          verificationCertificate='string',
          setAsActive=True|False,
          allowAutoRegistration=True|False
      )
    :type caCertificate: string
    :param caCertificate: **[REQUIRED]** 

      The CA certificate.

      

    
    :type verificationCertificate: string
    :param verificationCertificate: **[REQUIRED]** 

      The private key verification certificate.

      

    
    :type setAsActive: boolean
    :param setAsActive: 

      A boolean value that specifies if the CA certificate is set to active.

      

    
    :type allowAutoRegistration: boolean
    :param allowAutoRegistration: 

      Allows this CA certificate to be used for auto registration of device certificates.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'certificateArn': 'string',
            'certificateId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the RegisterCACertificateResponse operation.

        
        

        - **certificateArn** *(string) --* 

          The CA certificate ARN.

          
        

        - **certificateId** *(string) --* 

          The CA certificate identifier.

          
    

  .. py:method:: register_certificate(**kwargs)

    

    Registers a device certificate with AWS IoT. If you have more than one CA certificate that has the same subject field, you must specify the CA certificate that was used to sign the device certificate being registered.

    

    **Request Syntax** 
    ::

      response = client.register_certificate(
          certificatePem='string',
          caCertificatePem='string',
          setAsActive=True|False
      )
    :type certificatePem: string
    :param certificatePem: **[REQUIRED]** 

      The certificate data, in PEM format.

      

    
    :type caCertificatePem: string
    :param caCertificatePem: 

      The CA certificate used to sign the device certificate being registered.

      

    
    :type setAsActive: boolean
    :param setAsActive: 

      A boolean value that specifies if the CA certificate is set to active.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'certificateArn': 'string',
            'certificateId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the RegisterCertificate operation.

        
        

        - **certificateArn** *(string) --* 

          The certificate ARN.

          
        

        - **certificateId** *(string) --* 

          The certificate identifier.

          
    

  .. py:method:: reject_certificate_transfer(**kwargs)

    

    Rejects a pending certificate transfer. After AWS IoT rejects a certificate transfer, the certificate status changes from **PENDING_TRANSFER** to **INACTIVE** .

     

    To check for pending certificate transfers, call  ListCertificates to enumerate your certificates.

     

    This operation can only be called by the transfer destination. After it is called, the certificate will be returned to the source's account in the INACTIVE state.

    

    **Request Syntax** 
    ::

      response = client.reject_certificate_transfer(
          certificateId='string',
          rejectReason='string'
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The ID of the certificate.

      

    
    :type rejectReason: string
    :param rejectReason: 

      The reason the certificate transfer was rejected.

      

    
    
    :returns: None

  .. py:method:: replace_topic_rule(**kwargs)

    

    Replaces the specified rule. You must specify all parameters for the new rule. Creating rules is an administrator-level action. Any user who has permission to create rules will be able to access data processed by the rule.

    

    **Request Syntax** 
    ::

      response = client.replace_topic_rule(
          ruleName='string',
          topicRulePayload={
              'sql': 'string',
              'description': 'string',
              'actions': [
                  {
                      'dynamoDB': {
                          'tableName': 'string',
                          'roleArn': 'string',
                          'operation': 'string',
                          'hashKeyField': 'string',
                          'hashKeyValue': 'string',
                          'hashKeyType': 'STRING'|'NUMBER',
                          'rangeKeyField': 'string',
                          'rangeKeyValue': 'string',
                          'rangeKeyType': 'STRING'|'NUMBER',
                          'payloadField': 'string'
                      },
                      'lambda': {
                          'functionArn': 'string'
                      },
                      'sns': {
                          'targetArn': 'string',
                          'roleArn': 'string',
                          'messageFormat': 'RAW'|'JSON'
                      },
                      'sqs': {
                          'roleArn': 'string',
                          'queueUrl': 'string',
                          'useBase64': True|False
                      },
                      'kinesis': {
                          'roleArn': 'string',
                          'streamName': 'string',
                          'partitionKey': 'string'
                      },
                      'republish': {
                          'roleArn': 'string',
                          'topic': 'string'
                      },
                      's3': {
                          'roleArn': 'string',
                          'bucketName': 'string',
                          'key': 'string'
                      },
                      'firehose': {
                          'roleArn': 'string',
                          'deliveryStreamName': 'string',
                          'separator': 'string'
                      },
                      'cloudwatchMetric': {
                          'roleArn': 'string',
                          'metricNamespace': 'string',
                          'metricName': 'string',
                          'metricValue': 'string',
                          'metricUnit': 'string',
                          'metricTimestamp': 'string'
                      },
                      'cloudwatchAlarm': {
                          'roleArn': 'string',
                          'alarmName': 'string',
                          'stateReason': 'string',
                          'stateValue': 'string'
                      },
                      'elasticsearch': {
                          'roleArn': 'string',
                          'endpoint': 'string',
                          'index': 'string',
                          'type': 'string',
                          'id': 'string'
                      }
                  },
              ],
              'ruleDisabled': True|False,
              'awsIotSqlVersion': 'string'
          }
      )
    :type ruleName: string
    :param ruleName: **[REQUIRED]** 

      The name of the rule.

      

    
    :type topicRulePayload: dict
    :param topicRulePayload: **[REQUIRED]** 

      The rule payload.

      

    
      - **sql** *(string) --* **[REQUIRED]** 

        The SQL statement used to query the topic. For more information, see `AWS IoT SQL Reference`_ in the *AWS IoT Developer Guide* .

        

      
      - **description** *(string) --* 

        The description of the rule.

        

      
      - **actions** *(list) --* **[REQUIRED]** 

        The actions associated with the rule.

        

      
        - *(dict) --* 

          Describes the actions associated with a rule.

          

        
          - **dynamoDB** *(dict) --* 

            Write to a DynamoDB table.

            

          
            - **tableName** *(string) --* **[REQUIRED]** 

              The name of the DynamoDB table.

              

            
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access to the DynamoDB table.

              

            
            - **operation** *(string) --* 

              The type of operation to be performed. This follows the substitution template, so it can be ``${operation}`` , but the substitution must result in one of the following: ``INSERT`` , ``UPDATE`` , or ``DELETE`` .

              

            
            - **hashKeyField** *(string) --* **[REQUIRED]** 

              The hash key name.

              

            
            - **hashKeyValue** *(string) --* **[REQUIRED]** 

              The hash key value.

              

            
            - **hashKeyType** *(string) --* 

              The hash key type. Valid values are "STRING" or "NUMBER"

              

            
            - **rangeKeyField** *(string) --* 

              The range key name.

              

            
            - **rangeKeyValue** *(string) --* 

              The range key value.

              

            
            - **rangeKeyType** *(string) --* 

              The range key type. Valid values are "STRING" or "NUMBER"

              

            
            - **payloadField** *(string) --* 

              The action payload. This name can be customized.

              

            
          
          - **lambda** *(dict) --* 

            Invoke a Lambda function.

            

          
            - **functionArn** *(string) --* **[REQUIRED]** 

              The ARN of the Lambda function.

              

            
          
          - **sns** *(dict) --* 

            Publish to an Amazon SNS topic.

            

          
            - **targetArn** *(string) --* **[REQUIRED]** 

              The ARN of the SNS topic.

              

            
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access.

              

            
            - **messageFormat** *(string) --* 

              The message format of the message to publish. Optional. Accepted values are "JSON" and "RAW". The default value of the attribute is "RAW". SNS uses this setting to determine if the payload should be parsed and relevant platform-specific bits of the payload should be extracted. To read more about SNS message formats, see `<http://docs.aws.amazon.com/sns/latest/dg/json-formats.html>`_ refer to their official documentation.

              

            
          
          - **sqs** *(dict) --* 

            Publish to an Amazon SQS queue.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access.

              

            
            - **queueUrl** *(string) --* **[REQUIRED]** 

              The URL of the Amazon SQS queue.

              

            
            - **useBase64** *(boolean) --* 

              Specifies whether to use Base64 encoding.

              

            
          
          - **kinesis** *(dict) --* 

            Write data to an Amazon Kinesis stream.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access to the Amazon Kinesis stream.

              

            
            - **streamName** *(string) --* **[REQUIRED]** 

              The name of the Amazon Kinesis stream.

              

            
            - **partitionKey** *(string) --* 

              The partition key.

              

            
          
          - **republish** *(dict) --* 

            Publish to another MQTT topic.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access.

              

            
            - **topic** *(string) --* **[REQUIRED]** 

              The name of the MQTT topic.

              

            
          
          - **s3** *(dict) --* 

            Write to an Amazon S3 bucket.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The ARN of the IAM role that grants access.

              

            
            - **bucketName** *(string) --* **[REQUIRED]** 

              The Amazon S3 bucket.

              

            
            - **key** *(string) --* **[REQUIRED]** 

              The object key.

              

            
          
          - **firehose** *(dict) --* 

            Write to an Amazon Kinesis Firehose stream.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The IAM role that grants access to the Amazon Kinesis Firehost stream.

              

            
            - **deliveryStreamName** *(string) --* **[REQUIRED]** 

              The delivery stream name.

              

            
            - **separator** *(string) --* 

              A character separator that will be used to separate records written to the firehose stream. Valid values are: '\n' (newline), '\t' (tab), '\r\n' (Windows newline), ',' (comma).

              

            
          
          - **cloudwatchMetric** *(dict) --* 

            Capture a CloudWatch metric.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The IAM role that allows access to the CloudWatch metric.

              

            
            - **metricNamespace** *(string) --* **[REQUIRED]** 

              The CloudWatch metric namespace name.

              

            
            - **metricName** *(string) --* **[REQUIRED]** 

              The CloudWatch metric name.

              

            
            - **metricValue** *(string) --* **[REQUIRED]** 

              The CloudWatch metric value.

              

            
            - **metricUnit** *(string) --* **[REQUIRED]** 

              The `metric unit`_ supported by CloudWatch.

              

            
            - **metricTimestamp** *(string) --* 

              An optional `Unix timestamp`_ .

              

            
          
          - **cloudwatchAlarm** *(dict) --* 

            Change the state of a CloudWatch alarm.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The IAM role that allows access to the CloudWatch alarm.

              

            
            - **alarmName** *(string) --* **[REQUIRED]** 

              The CloudWatch alarm name.

              

            
            - **stateReason** *(string) --* **[REQUIRED]** 

              The reason for the alarm change.

              

            
            - **stateValue** *(string) --* **[REQUIRED]** 

              The value of the alarm state. Acceptable values are: OK, ALARM, INSUFFICIENT_DATA.

              

            
          
          - **elasticsearch** *(dict) --* 

            Write data to an Amazon Elasticsearch Service; domain.

            

          
            - **roleArn** *(string) --* **[REQUIRED]** 

              The IAM role ARN that has access to Elasticsearch.

              

            
            - **endpoint** *(string) --* **[REQUIRED]** 

              The endpoint of your Elasticsearch domain.

              

            
            - **index** *(string) --* **[REQUIRED]** 

              The Elasticsearch index where you want to store your data.

              

            
            - **type** *(string) --* **[REQUIRED]** 

              The type of document you are storing.

              

            
            - **id** *(string) --* **[REQUIRED]** 

              The unique identifier for the document you are storing.

              

            
          
        
    
      - **ruleDisabled** *(boolean) --* 

        Specifies whether the rule is disabled.

        

      
      - **awsIotSqlVersion** *(string) --* 

        The version of the SQL rules engine to use when evaluating the rule.

        

      
    
    
    :returns: None

  .. py:method:: set_default_policy_version(**kwargs)

    

    Sets the specified version of the specified policy as the policy's default (operative) version. This action affects all certificates to which the policy is attached. To list the principals the policy is attached to, use the ListPrincipalPolicy API.

    

    **Request Syntax** 
    ::

      response = client.set_default_policy_version(
          policyName='string',
          policyVersionId='string'
      )
    :type policyName: string
    :param policyName: **[REQUIRED]** 

      The policy name.

      

    
    :type policyVersionId: string
    :param policyVersionId: **[REQUIRED]** 

      The policy version ID.

      

    
    
    :returns: None

  .. py:method:: set_logging_options(**kwargs)

    

    Sets the logging options.

    

    **Request Syntax** 
    ::

      response = client.set_logging_options(
          loggingOptionsPayload={
              'roleArn': 'string',
              'logLevel': 'DEBUG'|'INFO'|'ERROR'|'WARN'|'DISABLED'
          }
      )
    :type loggingOptionsPayload: dict
    :param loggingOptionsPayload: **[REQUIRED]** 

      The logging options payload.

      

    
      - **roleArn** *(string) --* **[REQUIRED]** 

        The ARN of the IAM role that grants access.

        

      
      - **logLevel** *(string) --* 

        The logging level.

        

      
    
    
    :returns: None

  .. py:method:: transfer_certificate(**kwargs)

    

    Transfers the specified certificate to the specified AWS account.

     

    You can cancel the transfer until it is acknowledged by the recipient.

     

    No notification is sent to the transfer destination's account. It is up to the caller to notify the transfer target.

     

    The certificate being transferred must not be in the ACTIVE state. You can use the UpdateCertificate API to deactivate it.

     

    The certificate must not have any policies attached to it. You can use the DetachPrincipalPolicy API to detach them.

    

    **Request Syntax** 
    ::

      response = client.transfer_certificate(
          certificateId='string',
          targetAwsAccount='string',
          transferMessage='string'
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The ID of the certificate.

      

    
    :type targetAwsAccount: string
    :param targetAwsAccount: **[REQUIRED]** 

      The AWS account.

      

    
    :type transferMessage: string
    :param transferMessage: 

      The transfer message.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'transferredCertificateArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The output from the TransferCertificate operation.

        
        

        - **transferredCertificateArn** *(string) --* 

          The ARN of the certificate.

          
    

  .. py:method:: update_ca_certificate(**kwargs)

    

    Updates a registered CA certificate.

    

    **Request Syntax** 
    ::

      response = client.update_ca_certificate(
          certificateId='string',
          newStatus='ACTIVE'|'INACTIVE',
          newAutoRegistrationStatus='ENABLE'|'DISABLE'
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The CA certificate identifier.

      

    
    :type newStatus: string
    :param newStatus: 

      The updated status of the CA certificate.

       

      **Note:** The status value REGISTER_INACTIVE is deprecated and should not be used.

      

    
    :type newAutoRegistrationStatus: string
    :param newAutoRegistrationStatus: 

      The new value for the auto registration status. Valid values are: "ENABLE" or "DISABLE".

      

    
    
    :returns: None

  .. py:method:: update_certificate(**kwargs)

    

    Updates the status of the specified certificate. This operation is idempotent.

     

    Moving a certificate from the ACTIVE state (including REVOKED) will not disconnect currently connected devices, but these devices will be unable to reconnect.

     

    The ACTIVE state is required to authenticate devices connecting to AWS IoT using a certificate.

    

    **Request Syntax** 
    ::

      response = client.update_certificate(
          certificateId='string',
          newStatus='ACTIVE'|'INACTIVE'|'REVOKED'|'PENDING_TRANSFER'|'REGISTER_INACTIVE'|'PENDING_ACTIVATION'
      )
    :type certificateId: string
    :param certificateId: **[REQUIRED]** 

      The ID of the certificate.

      

    
    :type newStatus: string
    :param newStatus: **[REQUIRED]** 

      The new status.

       

      **Note:** Setting the status to PENDING_TRANSFER will result in an exception being thrown. PENDING_TRANSFER is a status used internally by AWS IoT. It is not intended for developer use.

       

      **Note:** The status value REGISTER_INACTIVE is deprecated and should not be used.

      

    
    
    :returns: None

  .. py:method:: update_thing(**kwargs)

    

    Updates the data for a thing.

    

    **Request Syntax** 
    ::

      response = client.update_thing(
          thingName='string',
          thingTypeName='string',
          attributePayload={
              'attributes': {
                  'string': 'string'
              },
              'merge': True|False
          },
          expectedVersion=123,
          removeThingType=True|False
      )
    :type thingName: string
    :param thingName: **[REQUIRED]** 

      The name of the thing to update.

      

    
    :type thingTypeName: string
    :param thingTypeName: 

      The name of the thing type.

      

    
    :type attributePayload: dict
    :param attributePayload: 

      A list of thing attributes, a JSON string containing name-value pairs. For example:

       

      ``{\"attributes\":{\"name1\":\"value2\"}})`` 

       

      This data is used to add new attributes or update existing attributes.

      

    
      - **attributes** *(dict) --* 

        A JSON string containing up to three key-value pair in JSON format. For example:

         

        ``{\"attributes\":{\"string1\":\"string2\"}})`` 

        

      
        - *(string) --* 

        
          - *(string) --* An attribute value for an Thing. An empty or null value in Update means that existing value for that attribute should be deleted. Empty and null values in create are ignored.

          
    
  
      - **merge** *(boolean) --* 

        Specifies whether the list of attributes provided in the ``AttributePayload`` is merged with the attributes stored in the registry, instead of overwriting them.

         

        To remove an attribute, call ``UpdateThing`` with an empty attribute value.

         

        .. note::

           

          The ``merge`` attribute is only valid when calling ``UpdateThing`` .

           

        

      
    
    :type expectedVersion: integer
    :param expectedVersion: 

      The expected version of the thing record in the registry. If the version of the record in the registry does not match the expected version specified in the request, the ``UpdateThing`` request is rejected with a ``VersionConflictException`` .

      

    
    :type removeThingType: boolean
    :param removeThingType: 

      Remove a thing type association. If **true** , the assocation is removed.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The output from the UpdateThing operation.

        
    