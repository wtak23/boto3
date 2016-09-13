

.. _How Key State Affects the Use of a Customer Master Key: http://docs.aws.amazon.com/kms/latest/developerguide/key-state.html
.. _ReEncryptTo: http://docs.aws.amazon.com/kms/latest/APIReference/API_ReEncrypt.html
.. _Deleting Customer Master Keys: http://docs.aws.amazon.com/kms/latest/developerguide/deleting-keys.html
.. _Encrypt the Key Material: http://docs.aws.amazon.com/kms/latest/developerguide/importing-keys-encrypt-key-material.html
.. _Default Key Policy: http://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html#key-policy-default-allow-root-enable-iam
.. _Grant Tokens: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#grant_token
.. _AWS Key Management Service (AWS KMS): http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arn-syntax-kms
.. _AWS Key Management Service Concepts: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html
.. _Grants: http://docs.aws.amazon.com/kms/latest/developerguide/grants.html
.. _AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arn-syntax-iam
.. _Importing Key Material: http://docs.aws.amazon.com/kms/latest/developerguide/importing-keys.html
.. _Key Policies: http://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html
.. _Encryption Context: http://docs.aws.amazon.com/kms/latest/developerguide/encrypt-context.html
.. _ReEncryptFrom: http://docs.aws.amazon.com/kms/latest/APIReference/API_ReEncrypt.html
.. _Amazon Resource Name (ARN): http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Changes that I make are not always immediately visible: http://docs.aws.amazon.com/IAM/latest/UserGuide/troubleshoot_general.html#troubleshoot_general_eventual-consistency


***
KMS
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: KMS.Client

  A low-level client representing AWS Key Management Service (KMS)::

    
    import boto3
    
    client = boto3.client('kms')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`cancel_key_deletion`

  
  *   :py:meth:`create_alias`

  
  *   :py:meth:`create_grant`

  
  *   :py:meth:`create_key`

  
  *   :py:meth:`decrypt`

  
  *   :py:meth:`delete_alias`

  
  *   :py:meth:`delete_imported_key_material`

  
  *   :py:meth:`describe_key`

  
  *   :py:meth:`disable_key`

  
  *   :py:meth:`disable_key_rotation`

  
  *   :py:meth:`enable_key`

  
  *   :py:meth:`enable_key_rotation`

  
  *   :py:meth:`encrypt`

  
  *   :py:meth:`generate_data_key`

  
  *   :py:meth:`generate_data_key_without_plaintext`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`generate_random`

  
  *   :py:meth:`get_key_policy`

  
  *   :py:meth:`get_key_rotation_status`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_parameters_for_import`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`import_key_material`

  
  *   :py:meth:`list_aliases`

  
  *   :py:meth:`list_grants`

  
  *   :py:meth:`list_key_policies`

  
  *   :py:meth:`list_keys`

  
  *   :py:meth:`list_retirable_grants`

  
  *   :py:meth:`put_key_policy`

  
  *   :py:meth:`re_encrypt`

  
  *   :py:meth:`retire_grant`

  
  *   :py:meth:`revoke_grant`

  
  *   :py:meth:`schedule_key_deletion`

  
  *   :py:meth:`update_alias`

  
  *   :py:meth:`update_key_description`

  

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


  .. py:method:: cancel_key_deletion(**kwargs)

    

    Cancels the deletion of a customer master key (CMK). When this operation is successful, the CMK is set to the ``Disabled`` state. To enable a CMK, use  EnableKey .

     

    For more information about scheduling and canceling deletion of a CMK, see `Deleting Customer Master Keys`_ in the *AWS Key Management Service Developer Guide* .

    

    **Request Syntax** 
    ::

      response = client.cancel_key_deletion(
          KeyId='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      The unique identifier for the customer master key (CMK) for which to cancel deletion.

       

      To specify this value, use the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

       

       
      * Unique key ID: 1234abcd-12ab-34cd-56ef-1234567890ab 
       
      * Key ARN: arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab 
       

       

      To obtain the unique key ID and key ARN for a given CMK, use  ListKeys or  DescribeKey .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'KeyId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **KeyId** *(string) --* 

          The unique identifier of the master key for which deletion is canceled.

          
    

  .. py:method:: create_alias(**kwargs)

    

    Creates a display name for a customer master key. An alias can be used to identify a key and should be unique. The console enforces a one-to-one mapping between the alias and a key. An alias name can contain only alphanumeric characters, forward slashes (/), underscores (_), and dashes (-). An alias must start with the word "alias" followed by a forward slash (alias/). An alias that begins with "aws" after the forward slash (alias/aws...) is reserved by Amazon Web Services (AWS).

     

    The alias and the key it is mapped to must be in the same AWS account and the same region.

     

    To map an alias to a different key, call  UpdateAlias .

    

    **Request Syntax** 
    ::

      response = client.create_alias(
          AliasName='string',
          TargetKeyId='string'
      )
    :type AliasName: string
    :param AliasName: **[REQUIRED]** 

      String that contains the display name. The name must start with the word "alias" followed by a forward slash (alias/). Aliases that begin with "alias/AWS" are reserved.

      

    
    :type TargetKeyId: string
    :param TargetKeyId: **[REQUIRED]** 

      An identifier of the key for which you are creating the alias. This value cannot be another alias but can be a globally unique identifier or a fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    
    :returns: None

  .. py:method:: create_grant(**kwargs)

    

    Adds a grant to a key to specify who can use the key and under what conditions. Grants are alternate permission mechanisms to key policies.

     

    For more information about grants, see `Grants`_ in the *AWS Key Management Service Developer Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_grant(
          KeyId='string',
          GranteePrincipal='string',
          RetiringPrincipal='string',
          Operations=[
              'Decrypt'|'Encrypt'|'GenerateDataKey'|'GenerateDataKeyWithoutPlaintext'|'ReEncryptFrom'|'ReEncryptTo'|'CreateGrant'|'RetireGrant'|'DescribeKey',
          ],
          Constraints={
              'EncryptionContextSubset': {
                  'string': 'string'
              },
              'EncryptionContextEquals': {
                  'string': 'string'
              }
          },
          GrantTokens=[
              'string',
          ],
          Name='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      The unique identifier for the customer master key (CMK) that the grant applies to.

       

      To specify this value, use the globally unique key ID or the Amazon Resource Name (ARN) of the key. Examples:

       

       
      * Globally unique key ID: 12345678-1234-1234-1234-123456789012 
       
      * Key ARN: arn:aws:kms:us-west-2:123456789012:key/12345678-1234-1234-1234-123456789012 
       

      

    
    :type GranteePrincipal: string
    :param GranteePrincipal: **[REQUIRED]** 

      The principal that is given permission to perform the operations that the grant permits.

       

      To specify the principal, use the `Amazon Resource Name (ARN)`_ of an AWS principal. Valid AWS principals include AWS accounts (root), IAM users, federated users, and assumed role users. For examples of the ARN syntax to use for specifying a principal, see `AWS Identity and Access Management (IAM)`_ in the Example ARNs section of the *AWS General Reference* .

      

    
    :type RetiringPrincipal: string
    :param RetiringPrincipal: 

      The principal that is given permission to retire the grant by using  RetireGrant operation.

       

      To specify the principal, use the `Amazon Resource Name (ARN)`_ of an AWS principal. Valid AWS principals include AWS accounts (root), IAM users, federated users, and assumed role users. For examples of the ARN syntax to use for specifying a principal, see `AWS Identity and Access Management (IAM)`_ in the Example ARNs section of the *AWS General Reference* .

      

    
    :type Operations: list
    :param Operations: 

      A list of operations that the grant permits. The list can contain any combination of one or more of the following values:

       

       
      *  Decrypt   
       
      *  Encrypt   
       
      *  GenerateDataKey   
       
      *  GenerateDataKeyWithoutPlaintext   
       
      * `ReEncryptFrom`_   
       
      * `ReEncryptTo`_   
       
      *  CreateGrant   
       
      *  RetireGrant   
       
      *  DescribeKey   
       

      

    
      - *(string) --* 

      
  
    :type Constraints: dict
    :param Constraints: 

      The conditions under which the operations permitted by the grant are allowed.

       

      You can use this value to allow the operations permitted by the grant only when a specified encryption context is present. For more information, see `Encryption Context`_ in the *AWS Key Management Service Developer Guide* .

      

    
      - **EncryptionContextSubset** *(dict) --* 

        Contains a list of key-value pairs, a subset of which must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list or is a subset of this list, the grant allows the operation. Otherwise, the operation is not allowed.

        

      
        - *(string) --* 

        
          - *(string) --* 

          
    
  
      - **EncryptionContextEquals** *(dict) --* 

        Contains a list of key-value pairs that must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list, the grant allows the operation. Otherwise, the operation is not allowed.

        

      
        - *(string) --* 

        
          - *(string) --* 

          
    
  
    
    :type GrantTokens: list
    :param GrantTokens: 

      A list of grant tokens.

       

      For more information, see `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

      

    
      - *(string) --* 

      
  
    :type Name: string
    :param Name: 

      A friendly name for identifying the grant. Use this value to prevent unintended creation of duplicate grants when retrying this request.

       

      When this value is absent, all ``CreateGrant`` requests result in a new grant with a unique ``GrantId`` even if all the supplied parameters are identical. This can result in unintended duplicates when you retry the ``CreateGrant`` request.

       

      When this value is present, you can retry a ``CreateGrant`` request with identical parameters; if the grant already exists, the original ``GrantId`` is returned without creating a new grant. Note that the returned grant token is unique with every ``CreateGrant`` request, even when a duplicate ``GrantId`` is returned. All grant tokens obtained in this way can be used interchangeably.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GrantToken': 'string',
            'GrantId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **GrantToken** *(string) --* 

          The grant token.

           

          For more information, see `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

          
        

        - **GrantId** *(string) --* 

          The unique identifier for the grant.

           

          You can use the ``GrantId`` in a subsequent  RetireGrant or  RevokeGrant operation.

          
    

  .. py:method:: create_key(**kwargs)

    

    Creates a customer master key (CMK).

     

    You can use a CMK to encrypt small amounts of data (4 KiB or less) directly, but CMKs are more commonly used to encrypt data encryption keys (DEKs), which are used to encrypt raw data. For more information about DEKs and the difference between CMKs and DEKs, see the following:

     

     
    * The  GenerateDataKey operation 
     
    * `AWS Key Management Service Concepts`_ in the *AWS Key Management Service Developer Guide*   
     

    

    **Request Syntax** 
    ::

      response = client.create_key(
          Policy='string',
          Description='string',
          KeyUsage='ENCRYPT_DECRYPT',
          Origin='AWS_KMS'|'EXTERNAL',
          BypassPolicyLockoutSafetyCheck=True|False
      )
    :type Policy: string
    :param Policy: 

      The key policy to attach to the CMK.

       

      If you specify a policy and do not set ``BypassPolicyLockoutSafetyCheck`` to true, the policy must meet the following criteria:

       

       
      * It must allow the principal making the ``CreateKey`` request to make a subsequent  PutKeyPolicy request on the CMK. This reduces the likelihood that the CMK becomes unmanageable. For more information, refer to the scenario in the `Default Key Policy`_ section in the *AWS Key Management Service Developer Guide* . 
       
      * The principal(s) specified in the key policy must exist and be visible to AWS KMS. When you create a new AWS principal (for example, an IAM user or role), you might need to enforce a delay before specifying the new principal in a key policy because the new principal might not immediately be visible to AWS KMS. For more information, see `Changes that I make are not always immediately visible`_ in the *IAM User Guide* . 
       

       

      If you do not specify a policy, AWS KMS attaches a default key policy to the CMK. For more information, see `Default Key Policy`_ in the *AWS Key Management Service Developer Guide* .

       

      The policy size limit is 32 KiB (32768 bytes).

      

    
    :type Description: string
    :param Description: 

      A description of the CMK.

       

      Use a description that helps you decide whether the CMK is appropriate for a task.

      

    
    :type KeyUsage: string
    :param KeyUsage: 

      The intended use of the CMK.

       

      You can use CMKs only for symmetric encryption and decryption.

      

    
    :type Origin: string
    :param Origin: 

      The source of the CMK's key material.

       

      The default is ``AWS_KMS`` , which means AWS KMS creates the key material. When this parameter is set to ``EXTERNAL`` , the request creates a CMK without key material so that you can import key material from your existing key management infrastructure. For more information about importing key material into AWS KMS, see `Importing Key Material`_ in the *AWS Key Management Service Developer Guide* .

       

      The CMK's ``Origin`` is immutable and is set when the CMK is created.

      

    
    :type BypassPolicyLockoutSafetyCheck: boolean
    :param BypassPolicyLockoutSafetyCheck: 

      A flag to indicate whether to bypass the key policy lockout safety check.

       

      .. warning::

         

        Setting this value to true increases the likelihood that the CMK becomes unmanageable. Do not set this value to true indiscriminately.

         

        For more information, refer to the scenario in the `Default Key Policy`_ section in the *AWS Key Management Service Developer Guide* .

         

       

      Use this parameter only when you include a policy in the request and you intend to prevent the principal making the request from making a subsequent  PutKeyPolicy request on the CMK.

       

      The default value is false.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'KeyMetadata': {
                'AWSAccountId': 'string',
                'KeyId': 'string',
                'Arn': 'string',
                'CreationDate': datetime(2015, 1, 1),
                'Enabled': True|False,
                'Description': 'string',
                'KeyUsage': 'ENCRYPT_DECRYPT',
                'KeyState': 'Enabled'|'Disabled'|'PendingDeletion'|'PendingImport',
                'DeletionDate': datetime(2015, 1, 1),
                'ValidTo': datetime(2015, 1, 1),
                'Origin': 'AWS_KMS'|'EXTERNAL',
                'ExpirationModel': 'KEY_MATERIAL_EXPIRES'|'KEY_MATERIAL_DOES_NOT_EXPIRE'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **KeyMetadata** *(dict) --* 

          Metadata associated with the CMK.

          
          

          - **AWSAccountId** *(string) --* 

            The twelve-digit account ID of the AWS account that owns the CMK.

            
          

          - **KeyId** *(string) --* 

            The globally unique identifier for the CMK.

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) of the CMK. For examples, see `AWS Key Management Service (AWS KMS)`_ in the Example ARNs section of the *AWS General Reference* .

            
          

          - **CreationDate** *(datetime) --* 

            The date and time when the CMK was created.

            
          

          - **Enabled** *(boolean) --* 

            Specifies whether the CMK is enabled. When ``KeyState`` is ``Enabled`` this value is true, otherwise it is false.

            
          

          - **Description** *(string) --* 

            The description of the CMK.

            
          

          - **KeyUsage** *(string) --* 

            The cryptographic operations for which you can use the CMK. Currently the only allowed value is ``ENCRYPT_DECRYPT`` , which means you can use the CMK for the  Encrypt and  Decrypt operations.

            
          

          - **KeyState** *(string) --* 

            The state of the CMK.

             

            For more information about how key state affects the use of a CMK, see `How Key State Affects the Use of a Customer Master Key`_ in the *AWS Key Management Service Developer Guide* .

            
          

          - **DeletionDate** *(datetime) --* 

            The date and time after which AWS KMS deletes the CMK. This value is present only when ``KeyState`` is ``PendingDeletion`` , otherwise this value is omitted.

            
          

          - **ValidTo** *(datetime) --* 

            The time at which the imported key material expires. When the key material expires, AWS KMS deletes the key material and the CMK becomes unusable. This value is present only for CMKs whose ``Origin`` is ``EXTERNAL`` and whose ``ExpirationModel`` is ``KEY_MATERIAL_EXPIRES`` , otherwise this value is omitted.

            
          

          - **Origin** *(string) --* 

            The source of the CMK's key material. When this value is ``AWS_KMS`` , AWS KMS created the key material. When this value is ``EXTERNAL`` , the key material was imported from your existing key management infrastructure or the CMK lacks key material.

            
          

          - **ExpirationModel** *(string) --* 

            Specifies whether the CMK's key material expires. This value is present only when ``Origin`` is ``EXTERNAL`` , otherwise this value is omitted.

            
      
    

  .. py:method:: decrypt(**kwargs)

    

    Decrypts ciphertext. Ciphertext is plaintext that has been previously encrypted by using any of the following functions:

     

     
    *  GenerateDataKey   
     
    *  GenerateDataKeyWithoutPlaintext   
     
    *  Encrypt   
     

     

    Note that if a caller has been granted access permissions to all keys (through, for example, IAM user policies that grant ``Decrypt`` permission on all resources), then ciphertext encrypted by using keys in other accounts where the key grants access to the caller can be decrypted. To remedy this, we recommend that you do not grant ``Decrypt`` access in an IAM user policy. Instead grant ``Decrypt`` access only in key policies. If you must grant ``Decrypt`` access in an IAM user policy, you should scope the resource to specific keys or to specific trusted accounts.

    

    **Request Syntax** 
    ::

      response = client.decrypt(
          CiphertextBlob=b'bytes',
          EncryptionContext={
              'string': 'string'
          },
          GrantTokens=[
              'string',
          ]
      )
    :type CiphertextBlob: bytes
    :param CiphertextBlob: **[REQUIRED]** 

      Ciphertext to be decrypted. The blob includes metadata.

      

    
    :type EncryptionContext: dict
    :param EncryptionContext: 

      The encryption context. If this was specified in the  Encrypt function, it must be specified here or the decryption operation will fail. For more information, see `Encryption Context`_ .

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type GrantTokens: list
    :param GrantTokens: 

      A list of grant tokens.

       

      For more information, see `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'KeyId': 'string',
            'Plaintext': b'bytes'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **KeyId** *(string) --* 

          ARN of the key used to perform the decryption. This value is returned if no errors are encountered during the operation.

          
        

        - **Plaintext** *(bytes) --* 

          Decrypted plaintext data. This value may not be returned if the customer master key is not available or if you didn't have permission to use it.

          
    

  .. py:method:: delete_alias(**kwargs)

    

    Deletes the specified alias. To map an alias to a different key, call  UpdateAlias .

    

    **Request Syntax** 
    ::

      response = client.delete_alias(
          AliasName='string'
      )
    :type AliasName: string
    :param AliasName: **[REQUIRED]** 

      The alias to be deleted. The name must start with the word "alias" followed by a forward slash (alias/). Aliases that begin with "alias/AWS" are reserved.

      

    
    
    :returns: None

  .. py:method:: delete_imported_key_material(**kwargs)

    

    Deletes key material that you previously imported and makes the specified customer master key (CMK) unusable. For more information about importing key material into AWS KMS, see `Importing Key Material`_ in the *AWS Key Management Service Developer Guide* .

     

    When the specified CMK is in the ``PendingDeletion`` state, this operation does not change the CMK's state. Otherwise, it changes the CMK's state to ``PendingImport`` .

     

    After you delete key material, you can use  ImportKeyMaterial to reimport the same key material into the CMK.

    

    **Request Syntax** 
    ::

      response = client.delete_imported_key_material(
          KeyId='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      The identifier of the CMK whose key material to delete. The CMK's ``Origin`` must be ``EXTERNAL`` .

       

      A valid identifier is the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

       

       
      * Unique key ID: ``1234abcd-12ab-34cd-56ef-1234567890ab``   
       
      * Key ARN: ``arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab``   
       

      

    
    
    :returns: None

  .. py:method:: describe_key(**kwargs)

    

    Provides detailed information about the specified customer master key.

    

    **Request Syntax** 
    ::

      response = client.describe_key(
          KeyId='string',
          GrantTokens=[
              'string',
          ]
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/".

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       
      * Alias Name Example - alias/MyAliasName 
       

      

    
    :type GrantTokens: list
    :param GrantTokens: 

      A list of grant tokens.

       

      For more information, see `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'KeyMetadata': {
                'AWSAccountId': 'string',
                'KeyId': 'string',
                'Arn': 'string',
                'CreationDate': datetime(2015, 1, 1),
                'Enabled': True|False,
                'Description': 'string',
                'KeyUsage': 'ENCRYPT_DECRYPT',
                'KeyState': 'Enabled'|'Disabled'|'PendingDeletion'|'PendingImport',
                'DeletionDate': datetime(2015, 1, 1),
                'ValidTo': datetime(2015, 1, 1),
                'Origin': 'AWS_KMS'|'EXTERNAL',
                'ExpirationModel': 'KEY_MATERIAL_EXPIRES'|'KEY_MATERIAL_DOES_NOT_EXPIRE'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **KeyMetadata** *(dict) --* 

          Metadata associated with the key.

          
          

          - **AWSAccountId** *(string) --* 

            The twelve-digit account ID of the AWS account that owns the CMK.

            
          

          - **KeyId** *(string) --* 

            The globally unique identifier for the CMK.

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) of the CMK. For examples, see `AWS Key Management Service (AWS KMS)`_ in the Example ARNs section of the *AWS General Reference* .

            
          

          - **CreationDate** *(datetime) --* 

            The date and time when the CMK was created.

            
          

          - **Enabled** *(boolean) --* 

            Specifies whether the CMK is enabled. When ``KeyState`` is ``Enabled`` this value is true, otherwise it is false.

            
          

          - **Description** *(string) --* 

            The description of the CMK.

            
          

          - **KeyUsage** *(string) --* 

            The cryptographic operations for which you can use the CMK. Currently the only allowed value is ``ENCRYPT_DECRYPT`` , which means you can use the CMK for the  Encrypt and  Decrypt operations.

            
          

          - **KeyState** *(string) --* 

            The state of the CMK.

             

            For more information about how key state affects the use of a CMK, see `How Key State Affects the Use of a Customer Master Key`_ in the *AWS Key Management Service Developer Guide* .

            
          

          - **DeletionDate** *(datetime) --* 

            The date and time after which AWS KMS deletes the CMK. This value is present only when ``KeyState`` is ``PendingDeletion`` , otherwise this value is omitted.

            
          

          - **ValidTo** *(datetime) --* 

            The time at which the imported key material expires. When the key material expires, AWS KMS deletes the key material and the CMK becomes unusable. This value is present only for CMKs whose ``Origin`` is ``EXTERNAL`` and whose ``ExpirationModel`` is ``KEY_MATERIAL_EXPIRES`` , otherwise this value is omitted.

            
          

          - **Origin** *(string) --* 

            The source of the CMK's key material. When this value is ``AWS_KMS`` , AWS KMS created the key material. When this value is ``EXTERNAL`` , the key material was imported from your existing key management infrastructure or the CMK lacks key material.

            
          

          - **ExpirationModel** *(string) --* 

            Specifies whether the CMK's key material expires. This value is present only when ``Origin`` is ``EXTERNAL`` , otherwise this value is omitted.

            
      
    

  .. py:method:: disable_key(**kwargs)

    

    Sets the state of a customer master key (CMK) to disabled, thereby preventing its use for cryptographic operations. For more information about how key state affects the use of a CMK, see `How Key State Affects the Use of a Customer Master Key`_ in the *AWS Key Management Service Developer Guide* .

    

    **Request Syntax** 
    ::

      response = client.disable_key(
          KeyId='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the CMK.

       

      Use the CMK's unique identifier or its Amazon Resource Name (ARN). For example:

       

       
      * Unique ID: 1234abcd-12ab-34cd-56ef-1234567890ab 
       
      * ARN: arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab 
       

      

    
    
    :returns: None

  .. py:method:: disable_key_rotation(**kwargs)

    

    Disables rotation of the specified key.

    

    **Request Syntax** 
    ::

      response = client.disable_key_rotation(
          KeyId='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    
    :returns: None

  .. py:method:: enable_key(**kwargs)

    

    Marks a key as enabled, thereby permitting its use.

    

    **Request Syntax** 
    ::

      response = client.enable_key(
          KeyId='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    
    :returns: None

  .. py:method:: enable_key_rotation(**kwargs)

    

    Enables rotation of the specified customer master key.

    

    **Request Syntax** 
    ::

      response = client.enable_key_rotation(
          KeyId='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    
    :returns: None

  .. py:method:: encrypt(**kwargs)

    

    Encrypts plaintext into ciphertext by using a customer master key. The ``Encrypt`` function has two primary use cases:

     

     
    * You can encrypt up to 4 KB of arbitrary data such as an RSA key, a database password, or other sensitive customer information. 
     
    * If you are moving encrypted data from one region to another, you can use this API to encrypt in the new region the plaintext data key that was used to encrypt the data in the original region. This provides you with an encrypted copy of the data key that can be decrypted in the new region and used there to decrypt the encrypted data. 
     

     

    Unless you are moving encrypted data from one region to another, you don't use this function to encrypt a generated data key within a region. You retrieve data keys already encrypted by calling the  GenerateDataKey or  GenerateDataKeyWithoutPlaintext function. Data keys don't need to be encrypted again by calling ``Encrypt`` .

     

    If you want to encrypt data locally in your application, you can use the ``GenerateDataKey`` function to return a plaintext data encryption key and a copy of the key encrypted under the customer master key (CMK) of your choosing.

    

    **Request Syntax** 
    ::

      response = client.encrypt(
          KeyId='string',
          Plaintext=b'bytes',
          EncryptionContext={
              'string': 'string'
          },
          GrantTokens=[
              'string',
          ]
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/".

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       
      * Alias Name Example - alias/MyAliasName 
       

      

    
    :type Plaintext: bytes
    :param Plaintext: **[REQUIRED]** 

      Data to be encrypted.

      

    
    :type EncryptionContext: dict
    :param EncryptionContext: 

      Name/value pair that specifies the encryption context to be used for authenticated encryption. If used here, the same value must be supplied to the ``Decrypt`` API or decryption will fail. For more information, see `Encryption Context`_ .

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type GrantTokens: list
    :param GrantTokens: 

      A list of grant tokens.

       

      For more information, see `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CiphertextBlob': b'bytes',
            'KeyId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **CiphertextBlob** *(bytes) --* 

          The encrypted plaintext. If you are using the CLI, the value is Base64 encoded. Otherwise, it is not encoded.

          
        

        - **KeyId** *(string) --* 

          The ID of the key used during encryption.

          
    

  .. py:method:: generate_data_key(**kwargs)

    

    Generates a data key that you can use in your application to locally encrypt data. This call returns a plaintext version of the key in the ``Plaintext`` field of the response object and an encrypted copy of the key in the ``CiphertextBlob`` field. The key is encrypted by using the master key specified by the ``KeyId`` field. To decrypt the encrypted key, pass it to the ``Decrypt`` API.

     

    We recommend that you use the following pattern to locally encrypt data: call the ``GenerateDataKey`` API, use the key returned in the ``Plaintext`` response field to locally encrypt data, and then erase the plaintext data key from memory. Store the encrypted data key (contained in the ``CiphertextBlob`` field) alongside of the locally encrypted data.

     

    .. note::

       

      You should not call the ``Encrypt`` function to re-encrypt your data keys within a region. ``GenerateDataKey`` always returns the data key encrypted and tied to the customer master key that will be used to decrypt it. There is no need to decrypt it twice.

       

     

    If you decide to use the optional ``EncryptionContext`` parameter, you must also store the context in full or at least store enough information along with the encrypted data to be able to reconstruct the context when submitting the ciphertext to the ``Decrypt`` API. It is a good practice to choose a context that you can reconstruct on the fly to better secure the ciphertext. For more information about how this parameter is used, see `Encryption Context`_ .

     

    To decrypt data, pass the encrypted data key to the ``Decrypt`` API. ``Decrypt`` uses the associated master key to decrypt the encrypted data key and returns it as plaintext. Use the plaintext data key to locally decrypt your data and then erase the key from memory. You must specify the encryption context, if any, that you specified when you generated the key. The encryption context is logged by CloudTrail, and you can use this log to help track the use of particular data.

    

    **Request Syntax** 
    ::

      response = client.generate_data_key(
          KeyId='string',
          EncryptionContext={
              'string': 'string'
          },
          NumberOfBytes=123,
          KeySpec='AES_256'|'AES_128',
          GrantTokens=[
              'string',
          ]
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/".

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       
      * Alias Name Example - alias/MyAliasName 
       

      

    
    :type EncryptionContext: dict
    :param EncryptionContext: 

      Name/value pair that contains additional data to be authenticated during the encryption and decryption processes that use the key. This value is logged by AWS CloudTrail to provide context around the data encrypted by the key.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type NumberOfBytes: integer
    :param NumberOfBytes: 

      Integer that contains the number of bytes to generate. Common values are 128, 256, 512, and 1024. 1024 is the current limit. We recommend that you use the ``KeySpec`` parameter instead.

      

    
    :type KeySpec: string
    :param KeySpec: 

      Value that identifies the encryption algorithm and key size to generate a data key for. Currently this can be AES_128 or AES_256.

      

    
    :type GrantTokens: list
    :param GrantTokens: 

      A list of grant tokens.

       

      For more information, see `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CiphertextBlob': b'bytes',
            'Plaintext': b'bytes',
            'KeyId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **CiphertextBlob** *(bytes) --* 

          Ciphertext that contains the encrypted data key. You must store the blob and enough information to reconstruct the encryption context so that the data encrypted by using the key can later be decrypted. You must provide both the ciphertext blob and the encryption context to the  Decrypt API to recover the plaintext data key and decrypt the object.

           

          If you are using the CLI, the value is Base64 encoded. Otherwise, it is not encoded.

          
        

        - **Plaintext** *(bytes) --* 

          Plaintext that contains the data key. Use this for encryption and decryption and then remove it from memory as soon as possible.

          
        

        - **KeyId** *(string) --* 

          System generated unique identifier of the key to be used to decrypt the encrypted copy of the data key.

          
    

  .. py:method:: generate_data_key_without_plaintext(**kwargs)

    

    Returns a data key encrypted by a customer master key without the plaintext copy of that key. Otherwise, this API functions exactly like  GenerateDataKey . You can use this API to, for example, satisfy an audit requirement that an encrypted key be made available without exposing the plaintext copy of that key.

    

    **Request Syntax** 
    ::

      response = client.generate_data_key_without_plaintext(
          KeyId='string',
          EncryptionContext={
              'string': 'string'
          },
          KeySpec='AES_256'|'AES_128',
          NumberOfBytes=123,
          GrantTokens=[
              'string',
          ]
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/".

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       
      * Alias Name Example - alias/MyAliasName 
       

      

    
    :type EncryptionContext: dict
    :param EncryptionContext: 

      Name:value pair that contains additional data to be authenticated during the encryption and decryption processes.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type KeySpec: string
    :param KeySpec: 

      Value that identifies the encryption algorithm and key size. Currently this can be AES_128 or AES_256.

      

    
    :type NumberOfBytes: integer
    :param NumberOfBytes: 

      Integer that contains the number of bytes to generate. Common values are 128, 256, 512, 1024 and so on. We recommend that you use the ``KeySpec`` parameter instead.

      

    
    :type GrantTokens: list
    :param GrantTokens: 

      A list of grant tokens.

       

      For more information, see `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CiphertextBlob': b'bytes',
            'KeyId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **CiphertextBlob** *(bytes) --* 

          Ciphertext that contains the wrapped data key. You must store the blob and encryption context so that the key can be used in a future decrypt operation.

           

          If you are using the CLI, the value is Base64 encoded. Otherwise, it is not encoded.

          
        

        - **KeyId** *(string) --* 

          System generated unique identifier of the key to be used to decrypt the encrypted copy of the data key.

          
    

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


  .. py:method:: generate_random(**kwargs)

    

    Generates an unpredictable byte string.

    

    **Request Syntax** 
    ::

      response = client.generate_random(
          NumberOfBytes=123
      )
    :type NumberOfBytes: integer
    :param NumberOfBytes: 

      Integer that contains the number of bytes to generate. Common values are 128, 256, 512, 1024 and so on. The current limit is 1024 bytes.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Plaintext': b'bytes'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Plaintext** *(bytes) --* 

          Plaintext that contains the unpredictable byte string.

          
    

  .. py:method:: get_key_policy(**kwargs)

    

    Retrieves a policy attached to the specified key.

    

    **Request Syntax** 
    ::

      response = client.get_key_policy(
          KeyId='string',
          PolicyName='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      String that contains the name of the policy. Currently, this must be "default". Policy names can be discovered by calling  ListKeyPolicies .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Policy': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Policy** *(string) --* 

          A policy document in JSON format.

          
    

  .. py:method:: get_key_rotation_status(**kwargs)

    

    Retrieves a Boolean value that indicates whether key rotation is enabled for the specified key.

    

    **Request Syntax** 
    ::

      response = client.get_key_rotation_status(
          KeyId='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'KeyRotationEnabled': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **KeyRotationEnabled** *(boolean) --* 

          A Boolean value that specifies whether key rotation is enabled.

          
    

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


  .. py:method:: get_parameters_for_import(**kwargs)

    

    Returns the items you need in order to import key material into AWS KMS from your existing key management infrastructure. For more information about importing key material into AWS KMS, see `Importing Key Material`_ in the *AWS Key Management Service Developer Guide* .

     

    You must specify the key ID of the customer master key (CMK) into which you will import key material. This CMK's ``Origin`` must be ``EXTERNAL`` . You must also specify the wrapping algorithm and type of wrapping key (public key) that you will use to encrypt the key material.

     

    This operation returns a public key and an import token. Use the public key to encrypt the key material. Store the import token to send with a subsequent  ImportKeyMaterial request. The public key and import token from the same response must be used together. These items are valid for 24 hours, after which they cannot be used for a subsequent  ImportKeyMaterial request. To retrieve new ones, send another ``GetParametersForImport`` request.

    

    **Request Syntax** 
    ::

      response = client.get_parameters_for_import(
          KeyId='string',
          WrappingAlgorithm='RSAES_PKCS1_V1_5'|'RSAES_OAEP_SHA_1'|'RSAES_OAEP_SHA_256',
          WrappingKeySpec='RSA_2048'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      The identifier of the CMK into which you will import key material. The CMK's ``Origin`` must be ``EXTERNAL`` .

       

      A valid identifier is the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

       

       
      * Unique key ID: ``1234abcd-12ab-34cd-56ef-1234567890ab``   
       
      * Key ARN: ``arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab``   
       

      

    
    :type WrappingAlgorithm: string
    :param WrappingAlgorithm: **[REQUIRED]** 

      The algorithm you will use to encrypt the key material before importing it with  ImportKeyMaterial . For more information, see `Encrypt the Key Material`_ in the *AWS Key Management Service Developer Guide* .

      

    
    :type WrappingKeySpec: string
    :param WrappingKeySpec: **[REQUIRED]** 

      The type of wrapping key (public key) to return in the response. Only 2048-bit RSA public keys are supported.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'KeyId': 'string',
            'ImportToken': b'bytes',
            'PublicKey': b'bytes',
            'ParametersValidTo': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **KeyId** *(string) --* 

          The identifier of the CMK to use in a subsequent  ImportKeyMaterial request. This is the same CMK specified in the ``GetParametersForImport`` request.

          
        

        - **ImportToken** *(bytes) --* 

          The import token to send in a subsequent  ImportKeyMaterial request.

          
        

        - **PublicKey** *(bytes) --* 

          The public key to use to encrypt the key material before importing it with  ImportKeyMaterial .

          
        

        - **ParametersValidTo** *(datetime) --* 

          The time at which the import token and public key are no longer valid. After this time, you cannot use them to make an  ImportKeyMaterial request and you must send another ``GetParametersForImport`` request to retrieve new ones.

          
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: import_key_material(**kwargs)

    

    Imports key material into an AWS KMS customer master key (CMK) from your existing key management infrastructure. For more information about importing key material into AWS KMS, see `Importing Key Material`_ in the *AWS Key Management Service Developer Guide* .

     

    You must specify the key ID of the CMK to import the key material into. This CMK's ``Origin`` must be ``EXTERNAL`` . You must also send an import token and the encrypted key material. Send the import token that you received in the same  GetParametersForImport response that contained the public key that you used to encrypt the key material. You must also specify whether the key material expires and if so, when. When the key material expires, AWS KMS deletes the key material and the CMK becomes unusable. To use the CMK again, you can reimport the same key material. If you set an expiration date, you can change it only by reimporting the same key material and specifying a new expiration date.

     

    When this operation is successful, the specified CMK's key state changes to ``Enabled`` , and you can use the CMK.

     

    After you successfully import key material into a CMK, you can reimport the same key material into that CMK, but you cannot import different key material.

    

    **Request Syntax** 
    ::

      response = client.import_key_material(
          KeyId='string',
          ImportToken=b'bytes',
          EncryptedKeyMaterial=b'bytes',
          ValidTo=datetime(2015, 1, 1),
          ExpirationModel='KEY_MATERIAL_EXPIRES'|'KEY_MATERIAL_DOES_NOT_EXPIRE'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      The identifier of the CMK to import the key material into. The CMK's ``Origin`` must be ``EXTERNAL`` .

       

      A valid identifier is the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

       

       
      * Unique key ID: ``1234abcd-12ab-34cd-56ef-1234567890ab``   
       
      * Key ARN: ``arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab``   
       

      

    
    :type ImportToken: bytes
    :param ImportToken: **[REQUIRED]** 

      The import token that you received in the response to a previous  GetParametersForImport request. It must be from the same response that contained the public key that you used to encrypt the key material.

      

    
    :type EncryptedKeyMaterial: bytes
    :param EncryptedKeyMaterial: **[REQUIRED]** 

      The encrypted key material to import. It must be encrypted with the public key that you received in the response to a previous  GetParametersForImport request, using the wrapping algorithm that you specified in that request.

      

    
    :type ValidTo: datetime
    :param ValidTo: 

      The time at which the imported key material expires. When the key material expires, AWS KMS deletes the key material and the CMK becomes unusable. You must omit this parameter when the ``ExpirationModel`` parameter is set to ``KEY_MATERIAL_DOES_NOT_EXPIRE`` . Otherwise it is required.

      

    
    :type ExpirationModel: string
    :param ExpirationModel: 

      Specifies whether the key material expires. The default is ``KEY_MATERIAL_EXPIRES`` , in which case you must include the ``ValidTo`` parameter. When this parameter is set to ``KEY_MATERIAL_DOES_NOT_EXPIRE`` , you must omit the ``ValidTo`` parameter.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: list_aliases(**kwargs)

    

    Lists all of the key aliases in the account.

    

    **Request Syntax** 
    ::

      response = client.list_aliases(
          Limit=123,
          Marker='string'
      )
    :type Limit: integer
    :param Limit: 

      When paginating results, specify the maximum number of items to return in the response. If additional items exist beyond the number you specify, the ``Truncated`` element in the response is set to true.

       

      This value is optional. If you include a value, it must be between 1 and 100, inclusive. If you do not include a value, it defaults to 50.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only in a subsequent request after you receive a response with truncated results. Set it to the value of ``NextMarker`` from the response you just received.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Aliases': [
                {
                    'AliasName': 'string',
                    'AliasArn': 'string',
                    'TargetKeyId': 'string'
                },
            ],
            'NextMarker': 'string',
            'Truncated': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Aliases** *(list) --* 

          A list of key aliases in the user's account.

          
          

          - *(dict) --* 

            Contains information about an alias.

            
            

            - **AliasName** *(string) --* 

              String that contains the alias.

              
            

            - **AliasArn** *(string) --* 

              String that contains the key ARN.

              
            

            - **TargetKeyId** *(string) --* 

              String that contains the key identifier pointed to by the alias.

              
        
      
        

        - **NextMarker** *(string) --* 

          When ``Truncated`` is true, this value is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
        

        - **Truncated** *(boolean) --* 

          A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

          
    

  .. py:method:: list_grants(**kwargs)

    

    List the grants for a specified key.

    

    **Request Syntax** 
    ::

      response = client.list_grants(
          Limit=123,
          Marker='string',
          KeyId='string'
      )
    :type Limit: integer
    :param Limit: 

      When paginating results, specify the maximum number of items to return in the response. If additional items exist beyond the number you specify, the ``Truncated`` element in the response is set to true.

       

      This value is optional. If you include a value, it must be between 1 and 100, inclusive. If you do not include a value, it defaults to 50.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only in a subsequent request after you receive a response with truncated results. Set it to the value of ``NextMarker`` from the response you just received.

      

    
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Grants': [
                {
                    'KeyId': 'string',
                    'GrantId': 'string',
                    'Name': 'string',
                    'CreationDate': datetime(2015, 1, 1),
                    'GranteePrincipal': 'string',
                    'RetiringPrincipal': 'string',
                    'IssuingAccount': 'string',
                    'Operations': [
                        'Decrypt'|'Encrypt'|'GenerateDataKey'|'GenerateDataKeyWithoutPlaintext'|'ReEncryptFrom'|'ReEncryptTo'|'CreateGrant'|'RetireGrant'|'DescribeKey',
                    ],
                    'Constraints': {
                        'EncryptionContextSubset': {
                            'string': 'string'
                        },
                        'EncryptionContextEquals': {
                            'string': 'string'
                        }
                    }
                },
            ],
            'NextMarker': 'string',
            'Truncated': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Grants** *(list) --* 

          A list of grants.

          
          

          - *(dict) --* 

            Contains information about an entry in a list of grants.

            
            

            - **KeyId** *(string) --* 

              The unique identifier for the customer master key (CMK) to which the grant applies.

              
            

            - **GrantId** *(string) --* 

              The unique identifier for the grant.

              
            

            - **Name** *(string) --* 

              The friendly name that identifies the grant. If a name was provided in the  CreateGrant request, that name is returned. Otherwise this value is null.

              
            

            - **CreationDate** *(datetime) --* 

              The date and time when the grant was created.

              
            

            - **GranteePrincipal** *(string) --* 

              The principal that receives the grant's permissions.

              
            

            - **RetiringPrincipal** *(string) --* 

              The principal that can retire the grant.

              
            

            - **IssuingAccount** *(string) --* 

              The AWS account under which the grant was issued.

              
            

            - **Operations** *(list) --* 

              The list of operations permitted by the grant.

              
              

              - *(string) --* 
          
            

            - **Constraints** *(dict) --* 

              The conditions under which the grant's operations are allowed.

              
              

              - **EncryptionContextSubset** *(dict) --* 

                Contains a list of key-value pairs, a subset of which must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list or is a subset of this list, the grant allows the operation. Otherwise, the operation is not allowed.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **EncryptionContextEquals** *(dict) --* 

                Contains a list of key-value pairs that must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list, the grant allows the operation. Otherwise, the operation is not allowed.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
        
      
        

        - **NextMarker** *(string) --* 

          When ``Truncated`` is true, this value is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
        

        - **Truncated** *(boolean) --* 

          A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

          
    

  .. py:method:: list_key_policies(**kwargs)

    

    Retrieves a list of policies attached to a key.

    

    **Request Syntax** 
    ::

      response = client.list_key_policies(
          KeyId='string',
          Limit=123,
          Marker='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/".

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       
      * Alias Name Example - alias/MyAliasName 
       

      

    
    :type Limit: integer
    :param Limit: 

      When paginating results, specify the maximum number of items to return in the response. If additional items exist beyond the number you specify, the ``Truncated`` element in the response is set to true.

       

      This value is optional. If you include a value, it must be between 1 and 1000, inclusive. If you do not include a value, it defaults to 100.

       

      Currently only 1 policy can be attached to a key.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only in a subsequent request after you receive a response with truncated results. Set it to the value of ``NextMarker`` from the response you just received.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyNames': [
                'string',
            ],
            'NextMarker': 'string',
            'Truncated': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **PolicyNames** *(list) --* 

          A list of policy names. Currently, there is only one policy and it is named "Default".

          
          

          - *(string) --* 
      
        

        - **NextMarker** *(string) --* 

          When ``Truncated`` is true, this value is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
        

        - **Truncated** *(boolean) --* 

          A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

          
    

  .. py:method:: list_keys(**kwargs)

    

    Lists the customer master keys.

    

    **Request Syntax** 
    ::

      response = client.list_keys(
          Limit=123,
          Marker='string'
      )
    :type Limit: integer
    :param Limit: 

      When paginating results, specify the maximum number of items to return in the response. If additional items exist beyond the number you specify, the ``Truncated`` element in the response is set to true.

       

      This value is optional. If you include a value, it must be between 1 and 1000, inclusive. If you do not include a value, it defaults to 100.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only in a subsequent request after you receive a response with truncated results. Set it to the value of ``NextMarker`` from the response you just received.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Keys': [
                {
                    'KeyId': 'string',
                    'KeyArn': 'string'
                },
            ],
            'NextMarker': 'string',
            'Truncated': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Keys** *(list) --* 

          A list of keys.

          
          

          - *(dict) --* 

            Contains information about each entry in the key list.

            
            

            - **KeyId** *(string) --* 

              Unique identifier of the key.

              
            

            - **KeyArn** *(string) --* 

              ARN of the key.

              
        
      
        

        - **NextMarker** *(string) --* 

          When ``Truncated`` is true, this value is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
        

        - **Truncated** *(boolean) --* 

          A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

          
    

  .. py:method:: list_retirable_grants(**kwargs)

    

    Returns a list of all grants for which the grant's ``RetiringPrincipal`` matches the one specified.

     

    A typical use is to list all grants that you are able to retire. To retire a grant, use  RetireGrant .

    

    **Request Syntax** 
    ::

      response = client.list_retirable_grants(
          Limit=123,
          Marker='string',
          RetiringPrincipal='string'
      )
    :type Limit: integer
    :param Limit: 

      When paginating results, specify the maximum number of items to return in the response. If additional items exist beyond the number you specify, the ``Truncated`` element in the response is set to true.

       

      This value is optional. If you include a value, it must be between 1 and 100, inclusive. If you do not include a value, it defaults to 50.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only in a subsequent request after you receive a response with truncated results. Set it to the value of ``NextMarker`` from the response you just received.

      

    
    :type RetiringPrincipal: string
    :param RetiringPrincipal: **[REQUIRED]** 

      The retiring principal for which to list grants.

       

      To specify the retiring principal, use the `Amazon Resource Name (ARN)`_ of an AWS principal. Valid AWS principals include AWS accounts (root), IAM users, federated users, and assumed role users. For examples of the ARN syntax for specifying a principal, see `AWS Identity and Access Management (IAM)`_ in the Example ARNs section of the *Amazon Web Services General Reference* .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Grants': [
                {
                    'KeyId': 'string',
                    'GrantId': 'string',
                    'Name': 'string',
                    'CreationDate': datetime(2015, 1, 1),
                    'GranteePrincipal': 'string',
                    'RetiringPrincipal': 'string',
                    'IssuingAccount': 'string',
                    'Operations': [
                        'Decrypt'|'Encrypt'|'GenerateDataKey'|'GenerateDataKeyWithoutPlaintext'|'ReEncryptFrom'|'ReEncryptTo'|'CreateGrant'|'RetireGrant'|'DescribeKey',
                    ],
                    'Constraints': {
                        'EncryptionContextSubset': {
                            'string': 'string'
                        },
                        'EncryptionContextEquals': {
                            'string': 'string'
                        }
                    }
                },
            ],
            'NextMarker': 'string',
            'Truncated': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Grants** *(list) --* 

          A list of grants.

          
          

          - *(dict) --* 

            Contains information about an entry in a list of grants.

            
            

            - **KeyId** *(string) --* 

              The unique identifier for the customer master key (CMK) to which the grant applies.

              
            

            - **GrantId** *(string) --* 

              The unique identifier for the grant.

              
            

            - **Name** *(string) --* 

              The friendly name that identifies the grant. If a name was provided in the  CreateGrant request, that name is returned. Otherwise this value is null.

              
            

            - **CreationDate** *(datetime) --* 

              The date and time when the grant was created.

              
            

            - **GranteePrincipal** *(string) --* 

              The principal that receives the grant's permissions.

              
            

            - **RetiringPrincipal** *(string) --* 

              The principal that can retire the grant.

              
            

            - **IssuingAccount** *(string) --* 

              The AWS account under which the grant was issued.

              
            

            - **Operations** *(list) --* 

              The list of operations permitted by the grant.

              
              

              - *(string) --* 
          
            

            - **Constraints** *(dict) --* 

              The conditions under which the grant's operations are allowed.

              
              

              - **EncryptionContextSubset** *(dict) --* 

                Contains a list of key-value pairs, a subset of which must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list or is a subset of this list, the grant allows the operation. Otherwise, the operation is not allowed.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **EncryptionContextEquals** *(dict) --* 

                Contains a list of key-value pairs that must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list, the grant allows the operation. Otherwise, the operation is not allowed.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
        
      
        

        - **NextMarker** *(string) --* 

          When ``Truncated`` is true, this value is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
        

        - **Truncated** *(boolean) --* 

          A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

          
    

  .. py:method:: put_key_policy(**kwargs)

    

    Attaches a key policy to the specified customer master key (CMK).

     

    For more information about key policies, see `Key Policies`_ in the *AWS Key Management Service Developer Guide* .

    

    **Request Syntax** 
    ::

      response = client.put_key_policy(
          KeyId='string',
          PolicyName='string',
          Policy='string',
          BypassPolicyLockoutSafetyCheck=True|False
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the CMK.

       

      Use the CMK's unique identifier or its Amazon Resource Name (ARN). For example:

       

       
      * Unique ID: 1234abcd-12ab-34cd-56ef-1234567890ab 
       
      * ARN: arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab 
       

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the key policy.

       

      This value must be ``default`` .

      

    
    :type Policy: string
    :param Policy: **[REQUIRED]** 

      The key policy to attach to the CMK.

       

      If you do not set ``BypassPolicyLockoutSafetyCheck`` to true, the policy must meet the following criteria:

       

       
      * It must allow the principal making the ``PutKeyPolicy`` request to make a subsequent ``PutKeyPolicy`` request on the CMK. This reduces the likelihood that the CMK becomes unmanageable. For more information, refer to the scenario in the `Default Key Policy`_ section in the *AWS Key Management Service Developer Guide* . 
       
      * The principal(s) specified in the key policy must exist and be visible to AWS KMS. When you create a new AWS principal (for example, an IAM user or role), you might need to enforce a delay before specifying the new principal in a key policy because the new principal might not immediately be visible to AWS KMS. For more information, see `Changes that I make are not always immediately visible`_ in the *IAM User Guide* . 
       

       

      The policy size limit is 32 KiB (32768 bytes).

      

    
    :type BypassPolicyLockoutSafetyCheck: boolean
    :param BypassPolicyLockoutSafetyCheck: 

      A flag to indicate whether to bypass the key policy lockout safety check.

       

      .. warning::

         

        Setting this value to true increases the likelihood that the CMK becomes unmanageable. Do not set this value to true indiscriminately.

         

        For more information, refer to the scenario in the `Default Key Policy`_ section in the *AWS Key Management Service Developer Guide* .

         

       

      Use this parameter only when you intend to prevent the principal making the request from making a subsequent ``PutKeyPolicy`` request on the CMK.

       

      The default value is false.

      

    
    
    :returns: None

  .. py:method:: re_encrypt(**kwargs)

    

    Encrypts data on the server side with a new customer master key without exposing the plaintext of the data on the client side. The data is first decrypted and then encrypted. This operation can also be used to change the encryption context of a ciphertext.

     

    Unlike other actions, ``ReEncrypt`` is authorized twice - once as ``ReEncryptFrom`` on the source key and once as ``ReEncryptTo`` on the destination key. We therefore recommend that you include the ``"action":"kms:ReEncrypt*"`` statement in your key policies to permit re-encryption from or to the key. The statement is included automatically when you authorize use of the key through the console but must be included manually when you set a policy by using the  PutKeyPolicy function.

    

    **Request Syntax** 
    ::

      response = client.re_encrypt(
          CiphertextBlob=b'bytes',
          SourceEncryptionContext={
              'string': 'string'
          },
          DestinationKeyId='string',
          DestinationEncryptionContext={
              'string': 'string'
          },
          GrantTokens=[
              'string',
          ]
      )
    :type CiphertextBlob: bytes
    :param CiphertextBlob: **[REQUIRED]** 

      Ciphertext of the data to re-encrypt.

      

    
    :type SourceEncryptionContext: dict
    :param SourceEncryptionContext: 

      Encryption context used to encrypt and decrypt the data specified in the ``CiphertextBlob`` parameter.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type DestinationKeyId: string
    :param DestinationKeyId: **[REQUIRED]** 

      A unique identifier for the customer master key used to re-encrypt the data. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/".

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       
      * Alias Name Example - alias/MyAliasName 
       

      

    
    :type DestinationEncryptionContext: dict
    :param DestinationEncryptionContext: 

      Encryption context to be used when the data is re-encrypted.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type GrantTokens: list
    :param GrantTokens: 

      A list of grant tokens.

       

      For more information, see `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CiphertextBlob': b'bytes',
            'SourceKeyId': 'string',
            'KeyId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **CiphertextBlob** *(bytes) --* 

          The re-encrypted data. If you are using the CLI, the value is Base64 encoded. Otherwise, it is not encoded.

          
        

        - **SourceKeyId** *(string) --* 

          Unique identifier of the key used to originally encrypt the data.

          
        

        - **KeyId** *(string) --* 

          Unique identifier of the key used to re-encrypt the data.

          
    

  .. py:method:: retire_grant(**kwargs)

    

    Retires a grant. You can retire a grant when you're done using it to clean up. You should revoke a grant when you intend to actively deny operations that depend on it. The following are permitted to call this API:

     

     
    * The account that created the grant 
     
    * The ``RetiringPrincipal`` , if present 
     
    * The ``GranteePrincipal`` , if ``RetireGrant`` is a grantee operation 
     

     

    The grant to retire must be identified by its grant token or by a combination of the key ARN and the grant ID. A grant token is a unique variable-length base64-encoded string. A grant ID is a 64 character unique identifier of a grant. Both are returned by the ``CreateGrant`` function.

    

    **Request Syntax** 
    ::

      response = client.retire_grant(
          GrantToken='string',
          KeyId='string',
          GrantId='string'
      )
    :type GrantToken: string
    :param GrantToken: 

      Token that identifies the grant to be retired.

      

    
    :type KeyId: string
    :param KeyId: 

      A unique identifier for the customer master key associated with the grant. This value can be a globally unique identifier or a fully specified ARN of the key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    :type GrantId: string
    :param GrantId: 

      Unique identifier of the grant to be retired. The grant ID is returned by the ``CreateGrant`` function.

       

       
      * Grant ID Example - 0123456789012345678901234567890123456789012345678901234567890123 
       

      

    
    
    :returns: None

  .. py:method:: revoke_grant(**kwargs)

    

    Revokes a grant. You can revoke a grant to actively deny operations that depend on it.

    

    **Request Syntax** 
    ::

      response = client.revoke_grant(
          KeyId='string',
          GrantId='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key associated with the grant. This value can be a globally unique identifier or the fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    :type GrantId: string
    :param GrantId: **[REQUIRED]** 

      Identifier of the grant to be revoked.

      

    
    
    :returns: None

  .. py:method:: schedule_key_deletion(**kwargs)

    

    Schedules the deletion of a customer master key (CMK). You may provide a waiting period, specified in days, before deletion occurs. If you do not provide a waiting period, the default period of 30 days is used. When this operation is successful, the state of the CMK changes to ``PendingDeletion`` . Before the waiting period ends, you can use  CancelKeyDeletion to cancel the deletion of the CMK. After the waiting period ends, AWS KMS deletes the CMK and all AWS KMS data associated with it, including all aliases that point to it.

     

    .. warning::

       

      Deleting a CMK is a destructive and potentially dangerous operation. When a CMK is deleted, all data that was encrypted under the CMK is rendered unrecoverable. To restrict the use of a CMK without deleting it, use  DisableKey .

       

     

    For more information about scheduling a CMK for deletion, see `Deleting Customer Master Keys`_ in the *AWS Key Management Service Developer Guide* .

    

    **Request Syntax** 
    ::

      response = client.schedule_key_deletion(
          KeyId='string',
          PendingWindowInDays=123
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      The unique identifier for the customer master key (CMK) to delete.

       

      To specify this value, use the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

       

       
      * Unique key ID: 1234abcd-12ab-34cd-56ef-1234567890ab 
       
      * Key ARN: arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab 
       

       

      To obtain the unique key ID and key ARN for a given CMK, use  ListKeys or  DescribeKey .

      

    
    :type PendingWindowInDays: integer
    :param PendingWindowInDays: 

      The waiting period, specified in number of days. After the waiting period ends, AWS KMS deletes the customer master key (CMK).

       

      This value is optional. If you include a value, it must be between 7 and 30, inclusive. If you do not include a value, it defaults to 30.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'KeyId': 'string',
            'DeletionDate': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **KeyId** *(string) --* 

          The unique identifier of the customer master key (CMK) for which deletion is scheduled.

          
        

        - **DeletionDate** *(datetime) --* 

          The date and time after which AWS KMS deletes the customer master key (CMK).

          
    

  .. py:method:: update_alias(**kwargs)

    

    Updates an alias to map it to a different key.

     

    An alias is not a property of a key. Therefore, an alias can be mapped to and unmapped from an existing key without changing the properties of the key.

     

    An alias name can contain only alphanumeric characters, forward slashes (/), underscores (_), and dashes (-). An alias must start with the word "alias" followed by a forward slash (alias/). An alias that begins with "aws" after the forward slash (alias/aws...) is reserved by Amazon Web Services (AWS).

     

    The alias and the key it is mapped to must be in the same AWS account and the same region.

    

    **Request Syntax** 
    ::

      response = client.update_alias(
          AliasName='string',
          TargetKeyId='string'
      )
    :type AliasName: string
    :param AliasName: **[REQUIRED]** 

      String that contains the name of the alias to be modified. The name must start with the word "alias" followed by a forward slash (alias/). Aliases that begin with "alias/aws" are reserved.

      

    
    :type TargetKeyId: string
    :param TargetKeyId: **[REQUIRED]** 

      Unique identifier of the customer master key to be mapped to the alias. This value can be a globally unique identifier or the fully specified ARN of a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

       

      You can call  ListAliases to verify that the alias is mapped to the correct ``TargetKeyId`` .

      

    
    
    :returns: None

  .. py:method:: update_key_description(**kwargs)

    

    Updates the description of a key.

    

    **Request Syntax** 
    ::

      response = client.update_key_description(
          KeyId='string',
          Description='string'
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
    :type Description: string
    :param Description: **[REQUIRED]** 

      New description for the key.

      

    
    
    :returns: None

==========
Paginators
==========


The available paginators are:

* :py:class:`KMS.Paginator.ListAliases`


* :py:class:`KMS.Paginator.ListGrants`


* :py:class:`KMS.Paginator.ListKeyPolicies`


* :py:class:`KMS.Paginator.ListKeys`



.. py:class:: KMS.Paginator.ListAliases

  ::

    
    paginator = client.get_paginator('list_aliases')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`KMS.Client.list_aliases`.

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
            'Aliases': [
                {
                    'AliasName': 'string',
                    'AliasArn': 'string',
                    'TargetKeyId': 'string'
                },
            ],
            'Truncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Aliases** *(list) --* 

          A list of key aliases in the user's account.

          
          

          - *(dict) --* 

            Contains information about an alias.

            
            

            - **AliasName** *(string) --* 

              String that contains the alias.

              
            

            - **AliasArn** *(string) --* 

              String that contains the key ARN.

              
            

            - **TargetKeyId** *(string) --* 

              String that contains the key identifier pointed to by the alias.

              
        
      
        

        - **Truncated** *(boolean) --* 

          A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: KMS.Paginator.ListGrants

  ::

    
    paginator = client.get_paginator('list_grants')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`KMS.Client.list_grants`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          KeyId='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key.

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       

      

    
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
            'Grants': [
                {
                    'KeyId': 'string',
                    'GrantId': 'string',
                    'Name': 'string',
                    'CreationDate': datetime(2015, 1, 1),
                    'GranteePrincipal': 'string',
                    'RetiringPrincipal': 'string',
                    'IssuingAccount': 'string',
                    'Operations': [
                        'Decrypt'|'Encrypt'|'GenerateDataKey'|'GenerateDataKeyWithoutPlaintext'|'ReEncryptFrom'|'ReEncryptTo'|'CreateGrant'|'RetireGrant'|'DescribeKey',
                    ],
                    'Constraints': {
                        'EncryptionContextSubset': {
                            'string': 'string'
                        },
                        'EncryptionContextEquals': {
                            'string': 'string'
                        }
                    }
                },
            ],
            'Truncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Grants** *(list) --* 

          A list of grants.

          
          

          - *(dict) --* 

            Contains information about an entry in a list of grants.

            
            

            - **KeyId** *(string) --* 

              The unique identifier for the customer master key (CMK) to which the grant applies.

              
            

            - **GrantId** *(string) --* 

              The unique identifier for the grant.

              
            

            - **Name** *(string) --* 

              The friendly name that identifies the grant. If a name was provided in the  CreateGrant request, that name is returned. Otherwise this value is null.

              
            

            - **CreationDate** *(datetime) --* 

              The date and time when the grant was created.

              
            

            - **GranteePrincipal** *(string) --* 

              The principal that receives the grant's permissions.

              
            

            - **RetiringPrincipal** *(string) --* 

              The principal that can retire the grant.

              
            

            - **IssuingAccount** *(string) --* 

              The AWS account under which the grant was issued.

              
            

            - **Operations** *(list) --* 

              The list of operations permitted by the grant.

              
              

              - *(string) --* 
          
            

            - **Constraints** *(dict) --* 

              The conditions under which the grant's operations are allowed.

              
              

              - **EncryptionContextSubset** *(dict) --* 

                Contains a list of key-value pairs, a subset of which must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list or is a subset of this list, the grant allows the operation. Otherwise, the operation is not allowed.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **EncryptionContextEquals** *(dict) --* 

                Contains a list of key-value pairs that must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list, the grant allows the operation. Otherwise, the operation is not allowed.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
        
      
        

        - **Truncated** *(boolean) --* 

          A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: KMS.Paginator.ListKeyPolicies

  ::

    
    paginator = client.get_paginator('list_key_policies')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`KMS.Client.list_key_policies`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          KeyId='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type KeyId: string
    :param KeyId: **[REQUIRED]** 

      A unique identifier for the customer master key. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/".

       

       
      * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
       
      * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName 
       
      * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
       
      * Alias Name Example - alias/MyAliasName 
       

      

    
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
            'PolicyNames': [
                'string',
            ],
            'Truncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **PolicyNames** *(list) --* 

          A list of policy names. Currently, there is only one policy and it is named "Default".

          
          

          - *(string) --* 
      
        

        - **Truncated** *(boolean) --* 

          A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: KMS.Paginator.ListKeys

  ::

    
    paginator = client.get_paginator('list_keys')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`KMS.Client.list_keys`.

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
            'Keys': [
                {
                    'KeyId': 'string',
                    'KeyArn': 'string'
                },
            ],
            'Truncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Keys** *(list) --* 

          A list of keys.

          
          

          - *(dict) --* 

            Contains information about each entry in the key list.

            
            

            - **KeyId** *(string) --* 

              Unique identifier of the key.

              
            

            - **KeyArn** *(string) --* 

              ARN of the key.

              
        
      
        

        - **Truncated** *(boolean) --* 

          A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    