

***********************
CognitoIdentityProvider
***********************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: CognitoIdentityProvider.Client

  A low-level client representing Amazon Cognito Identity Provider::

    
    import boto3
    
    client = boto3.client('cognito-idp')

  
  These are the available methods:
  
  *   :py:meth:`add_custom_attributes`

  
  *   :py:meth:`admin_confirm_sign_up`

  
  *   :py:meth:`admin_delete_user`

  
  *   :py:meth:`admin_delete_user_attributes`

  
  *   :py:meth:`admin_disable_user`

  
  *   :py:meth:`admin_enable_user`

  
  *   :py:meth:`admin_forget_device`

  
  *   :py:meth:`admin_get_device`

  
  *   :py:meth:`admin_get_user`

  
  *   :py:meth:`admin_initiate_auth`

  
  *   :py:meth:`admin_list_devices`

  
  *   :py:meth:`admin_reset_user_password`

  
  *   :py:meth:`admin_respond_to_auth_challenge`

  
  *   :py:meth:`admin_set_user_settings`

  
  *   :py:meth:`admin_update_device_status`

  
  *   :py:meth:`admin_update_user_attributes`

  
  *   :py:meth:`admin_user_global_sign_out`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`change_password`

  
  *   :py:meth:`confirm_device`

  
  *   :py:meth:`confirm_forgot_password`

  
  *   :py:meth:`confirm_sign_up`

  
  *   :py:meth:`create_user_import_job`

  
  *   :py:meth:`create_user_pool`

  
  *   :py:meth:`create_user_pool_client`

  
  *   :py:meth:`delete_user`

  
  *   :py:meth:`delete_user_attributes`

  
  *   :py:meth:`delete_user_pool`

  
  *   :py:meth:`delete_user_pool_client`

  
  *   :py:meth:`describe_user_import_job`

  
  *   :py:meth:`describe_user_pool`

  
  *   :py:meth:`describe_user_pool_client`

  
  *   :py:meth:`forget_device`

  
  *   :py:meth:`forgot_password`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_csv_header`

  
  *   :py:meth:`get_device`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_user`

  
  *   :py:meth:`get_user_attribute_verification_code`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`global_sign_out`

  
  *   :py:meth:`initiate_auth`

  
  *   :py:meth:`list_devices`

  
  *   :py:meth:`list_user_import_jobs`

  
  *   :py:meth:`list_user_pool_clients`

  
  *   :py:meth:`list_user_pools`

  
  *   :py:meth:`list_users`

  
  *   :py:meth:`resend_confirmation_code`

  
  *   :py:meth:`respond_to_auth_challenge`

  
  *   :py:meth:`set_user_settings`

  
  *   :py:meth:`sign_up`

  
  *   :py:meth:`start_user_import_job`

  
  *   :py:meth:`stop_user_import_job`

  
  *   :py:meth:`update_device_status`

  
  *   :py:meth:`update_user_attributes`

  
  *   :py:meth:`update_user_pool`

  
  *   :py:meth:`update_user_pool_client`

  
  *   :py:meth:`verify_user_attribute`

  

  .. py:method:: add_custom_attributes(**kwargs)

    

    Adds additional user attributes to the user pool schema.

    

    **Request Syntax** 
    ::

      response = client.add_custom_attributes(
          UserPoolId='string',
          CustomAttributes=[
              {
                  'Name': 'string',
                  'AttributeDataType': 'String'|'Number'|'DateTime'|'Boolean',
                  'DeveloperOnlyAttribute': True|False,
                  'Mutable': True|False,
                  'Required': True|False,
                  'NumberAttributeConstraints': {
                      'MinValue': 'string',
                      'MaxValue': 'string'
                  },
                  'StringAttributeConstraints': {
                      'MinLength': 'string',
                      'MaxLength': 'string'
                  }
              },
          ]
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to add custom attributes.

      

    
    :type CustomAttributes: list
    :param CustomAttributes: **[REQUIRED]** 

      An array of custom attributes, such as Mutable and Name.

      

    
      - *(dict) --* 

        Contains information about the schema attribute.

        

      
        - **Name** *(string) --* 

          A schema attribute of the name type.

          

        
        - **AttributeDataType** *(string) --* 

          The attribute data type.

          

        
        - **DeveloperOnlyAttribute** *(boolean) --* 

          Specifies whether the attribute type is developer only.

          

        
        - **Mutable** *(boolean) --* 

          Specifies whether the attribute can be changed once it has been created.

          

        
        - **Required** *(boolean) --* 

          Specifies whether a user pool attribute is required. If the attribute is required and the user does not provide a value, registration or sign-in will fail.

          

        
        - **NumberAttributeConstraints** *(dict) --* 

          Specifies the constraints for an attribute of the number type.

          

        
          - **MinValue** *(string) --* 

            The minimum value of an attribute that is of the number data type.

            

          
          - **MaxValue** *(string) --* 

            The maximum value of an attribute that is of the number data type.

            

          
        
        - **StringAttributeConstraints** *(dict) --* 

          Specifies the constraints for an attribute of the string type.

          

        
          - **MinLength** *(string) --* 

            The minimum length of an attribute value of the string type.

            

          
          - **MaxLength** *(string) --* 

            The maximum length of an attribute value of the string type.

            

          
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server for the request to add custom attributes.

        
    

  .. py:method:: admin_confirm_sign_up(**kwargs)

    

    Confirms user registration as an admin without using a confirmation code. Works on any user.

    

    **Request Syntax** 
    ::

      response = client.admin_confirm_sign_up(
          UserPoolId='string',
          Username='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for which you want to confirm user registration.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name for which you want to confirm user registration.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server for the request to confirm registration.

        
    

  .. py:method:: admin_delete_user(**kwargs)

    

    Deletes a user as an administrator. Works on any user.

    

    **Request Syntax** 
    ::

      response = client.admin_delete_user(
          UserPoolId='string',
          Username='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to delete the user.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user you wish to delete.

      

    
    
    :returns: None

  .. py:method:: admin_delete_user_attributes(**kwargs)

    

    Deletes the user attributes in a user pool as an administrator. Works on any user.

    

    **Request Syntax** 
    ::

      response = client.admin_delete_user_attributes(
          UserPoolId='string',
          Username='string',
          UserAttributeNames=[
              'string',
          ]
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to delete user attributes.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user from which you would like to delete attributes.

      

    
    :type UserAttributeNames: list
    :param UserAttributeNames: **[REQUIRED]** 

      An array of strings representing the user attribute names you wish to delete.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response received from the server for a request to delete user attributes.

        
    

  .. py:method:: admin_disable_user(**kwargs)

    

    Disables the specified user as an administrator. Works on any user.

    

    **Request Syntax** 
    ::

      response = client.admin_disable_user(
          UserPoolId='string',
          Username='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to disable the user.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user you wish to disable.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response received from the server to disable the user as an administrator.

        
    

  .. py:method:: admin_enable_user(**kwargs)

    

    Enables the specified user as an administrator. Works on any user.

    

    **Request Syntax** 
    ::

      response = client.admin_enable_user(
          UserPoolId='string',
          Username='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to enable the user.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user you wish to ebable.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server for the request to enable a user as an administrator.

        
    

  .. py:method:: admin_forget_device(**kwargs)

    

    Forgets the device, as an administrator.

    

    **Request Syntax** 
    ::

      response = client.admin_forget_device(
          UserPoolId='string',
          Username='string',
          DeviceKey='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name.

      

    
    :type DeviceKey: string
    :param DeviceKey: **[REQUIRED]** 

      The device key.

      

    
    
    :returns: None

  .. py:method:: admin_get_device(**kwargs)

    

    Gets the device, as an administrator.

    

    **Request Syntax** 
    ::

      response = client.admin_get_device(
          DeviceKey='string',
          UserPoolId='string',
          Username='string'
      )
    :type DeviceKey: string
    :param DeviceKey: **[REQUIRED]** 

      The device key.

      

    
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Device': {
                'DeviceKey': 'string',
                'DeviceAttributes': [
                    {
                        'Name': 'string',
                        'Value': 'string'
                    },
                ],
                'DeviceCreateDate': datetime(2015, 1, 1),
                'DeviceLastModifiedDate': datetime(2015, 1, 1),
                'DeviceLastAuthenticatedDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Gets the device response, as an administrator.

        
        

        - **Device** *(dict) --* 

          The device.

          
          

          - **DeviceKey** *(string) --* 

            The device key.

            
          

          - **DeviceAttributes** *(list) --* 

            The device attributes.

            
            

            - *(dict) --* 

              Specifies whether the attribute is standard or custom.

              
              

              - **Name** *(string) --* 

                The name of the attribute.

                
              

              - **Value** *(string) --* 

                The value of the attribute.

                
          
        
          

          - **DeviceCreateDate** *(datetime) --* 

            The creation date of the device.

            
          

          - **DeviceLastModifiedDate** *(datetime) --* 

            The last modified date of the device.

            
          

          - **DeviceLastAuthenticatedDate** *(datetime) --* 

            The date in which the device was last authenticated.

            
      
    

  .. py:method:: admin_get_user(**kwargs)

    

    Gets the specified user by user name in a user pool as an administrator. Works on any user.

    

    **Request Syntax** 
    ::

      response = client.admin_get_user(
          UserPoolId='string',
          Username='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to get information about the user.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user you wish to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Username': 'string',
            'UserAttributes': [
                {
                    'Name': 'string',
                    'Value': 'string'
                },
            ],
            'UserCreateDate': datetime(2015, 1, 1),
            'UserLastModifiedDate': datetime(2015, 1, 1),
            'Enabled': True|False,
            'UserStatus': 'UNCONFIRMED'|'CONFIRMED'|'ARCHIVED'|'COMPROMISED'|'UNKNOWN'|'RESET_REQUIRED',
            'MFAOptions': [
                {
                    'DeliveryMedium': 'SMS'|'EMAIL',
                    'AttributeName': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server from the request to get the specified user as an administrator.

        
        

        - **Username** *(string) --* 

          The user name of the user about whom you are receiving information.

          
        

        - **UserAttributes** *(list) --* 

          An array of name-value pairs representing user attributes.

          
          

          - *(dict) --* 

            Specifies whether the attribute is standard or custom.

            
            

            - **Name** *(string) --* 

              The name of the attribute.

              
            

            - **Value** *(string) --* 

              The value of the attribute.

              
        
      
        

        - **UserCreateDate** *(datetime) --* 

          The date the user was created.

          
        

        - **UserLastModifiedDate** *(datetime) --* 

          The date the user was last modified.

          
        

        - **Enabled** *(boolean) --* 

          Indicates that the status is enabled.

          
        

        - **UserStatus** *(string) --* 

          The user status. Can be one of the following:

           

           
          * UNCONFIRMED - User has been created but not confirmed.
           
          * CONFIRMED - User has been confirmed.
           
          * ARCHIVED - User is no longer active.
           
          * COMPROMISED - User is disabled due to a potential security threat.
           
          * UNKNOWN - User status is not known.
           

          
        

        - **MFAOptions** *(list) --* 

          Specifies the options for MFA (e.g., email or phone number).

          
          

          - *(dict) --* 

            Specifies the different settings for multi-factor authentication (MFA).

            
            

            - **DeliveryMedium** *(string) --* 

              The delivery medium (email message or SMS message) to send the MFA code.

              
            

            - **AttributeName** *(string) --* 

              The attribute name of the MFA option type.

              
        
      
    

  .. py:method:: admin_initiate_auth(**kwargs)

    

    Initiates the authentication flow, as an administrator.

    

    **Request Syntax** 
    ::

      response = client.admin_initiate_auth(
          UserPoolId='string',
          ClientId='string',
          AuthFlow='USER_SRP_AUTH'|'REFRESH_TOKEN_AUTH'|'REFRESH_TOKEN'|'CUSTOM_AUTH'|'ADMIN_NO_SRP_AUTH',
          AuthParameters={
              'string': 'string'
          },
          ClientMetadata={
              'string': 'string'
          }
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The ID of the Amazon Cognito user pool.

      

    
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The client app ID.

      

    
    :type AuthFlow: string
    :param AuthFlow: **[REQUIRED]** 

      The authentication flow.

      

    
    :type AuthParameters: dict
    :param AuthParameters: 

      The authentication parameters.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type ClientMetadata: dict
    :param ClientMetadata: 

      The client app metadata.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChallengeName': 'SMS_MFA'|'PASSWORD_VERIFIER'|'CUSTOM_CHALLENGE'|'DEVICE_SRP_AUTH'|'DEVICE_PASSWORD_VERIFIER'|'ADMIN_NO_SRP_AUTH',
            'Session': 'string',
            'ChallengeParameters': {
                'string': 'string'
            },
            'AuthenticationResult': {
                'AccessToken': 'string',
                'ExpiresIn': 123,
                'TokenType': 'string',
                'RefreshToken': 'string',
                'IdToken': 'string',
                'NewDeviceMetadata': {
                    'DeviceKey': 'string',
                    'DeviceGroupKey': 'string'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Initiates the authentication response, as an administrator.

        
        

        - **ChallengeName** *(string) --* 

          The name of the challenge.

          
        

        - **Session** *(string) --* 

          The session.

          
        

        - **ChallengeParameters** *(dict) --* 

          The challenge parameters.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **AuthenticationResult** *(dict) --* 

          The result type of the authentication result.

          
          

          - **AccessToken** *(string) --* 

            The access token of the authentication result.

            
          

          - **ExpiresIn** *(integer) --* 

            The expiration period of the authentication result.

            
          

          - **TokenType** *(string) --* 

            The token type of the authentication result.

            
          

          - **RefreshToken** *(string) --* 

            The refresh token of the authentication result.

            
          

          - **IdToken** *(string) --* 

            The ID token of the authentication result.

            
          

          - **NewDeviceMetadata** *(dict) --* 

            The new device metadata from an authentication result.

            
            

            - **DeviceKey** *(string) --* 

              The device key.

              
            

            - **DeviceGroupKey** *(string) --* 

              The device group key.

              
        
      
    

  .. py:method:: admin_list_devices(**kwargs)

    

    Lists devices, as an administrator.

    

    **Request Syntax** 
    ::

      response = client.admin_list_devices(
          UserPoolId='string',
          Username='string',
          Limit=123,
          PaginationToken='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name.

      

    
    :type Limit: integer
    :param Limit: 

      The limit of the devices request.

      

    
    :type PaginationToken: string
    :param PaginationToken: 

      The pagination token.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Devices': [
                {
                    'DeviceKey': 'string',
                    'DeviceAttributes': [
                        {
                            'Name': 'string',
                            'Value': 'string'
                        },
                    ],
                    'DeviceCreateDate': datetime(2015, 1, 1),
                    'DeviceLastModifiedDate': datetime(2015, 1, 1),
                    'DeviceLastAuthenticatedDate': datetime(2015, 1, 1)
                },
            ],
            'PaginationToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Lists the device's response, as an administrator.

        
        

        - **Devices** *(list) --* 

          The devices in the list of devices response.

          
          

          - *(dict) --* 

            The device type.

            
            

            - **DeviceKey** *(string) --* 

              The device key.

              
            

            - **DeviceAttributes** *(list) --* 

              The device attributes.

              
              

              - *(dict) --* 

                Specifies whether the attribute is standard or custom.

                
                

                - **Name** *(string) --* 

                  The name of the attribute.

                  
                

                - **Value** *(string) --* 

                  The value of the attribute.

                  
            
          
            

            - **DeviceCreateDate** *(datetime) --* 

              The creation date of the device.

              
            

            - **DeviceLastModifiedDate** *(datetime) --* 

              The last modified date of the device.

              
            

            - **DeviceLastAuthenticatedDate** *(datetime) --* 

              The date in which the device was last authenticated.

              
        
      
        

        - **PaginationToken** *(string) --* 

          The pagination token.

          
    

  .. py:method:: admin_reset_user_password(**kwargs)

    

    Resets the specified user's password in a user pool as an administrator. Works on any user.

     

    When a developer calls this API, the current password is invalidated, so it must be changed. If a user tries to sign in after the API is called, the app will get a PasswordResetRequiredException exception back and should direct the user down the flow to reset the password, which is the same as the forgot password flow. In addition, if the user pool has phone verification selected and a verified phone number exists for the user, or if email verification is selected and a verified email exists for the user, calling this API will also result in sending a message to the end user with the code to change their password.

    

    **Request Syntax** 
    ::

      response = client.admin_reset_user_password(
          UserPoolId='string',
          Username='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to reset the user's password.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user whose password you wish to reset.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to reset a user password as an administrator.

        
    

  .. py:method:: admin_respond_to_auth_challenge(**kwargs)

    

    Responds to an authentication challenge, as an administrator.

    

    **Request Syntax** 
    ::

      response = client.admin_respond_to_auth_challenge(
          UserPoolId='string',
          ClientId='string',
          ChallengeName='SMS_MFA'|'PASSWORD_VERIFIER'|'CUSTOM_CHALLENGE'|'DEVICE_SRP_AUTH'|'DEVICE_PASSWORD_VERIFIER'|'ADMIN_NO_SRP_AUTH',
          ChallengeResponses={
              'string': 'string'
          },
          Session='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The ID of the Amazon Cognito user pool.

      

    
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The client ID.

      

    
    :type ChallengeName: string
    :param ChallengeName: **[REQUIRED]** 

      The name of the challenge.

      

    
    :type ChallengeResponses: dict
    :param ChallengeResponses: 

      The challenge response.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type Session: string
    :param Session: 

      The session.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChallengeName': 'SMS_MFA'|'PASSWORD_VERIFIER'|'CUSTOM_CHALLENGE'|'DEVICE_SRP_AUTH'|'DEVICE_PASSWORD_VERIFIER'|'ADMIN_NO_SRP_AUTH',
            'Session': 'string',
            'ChallengeParameters': {
                'string': 'string'
            },
            'AuthenticationResult': {
                'AccessToken': 'string',
                'ExpiresIn': 123,
                'TokenType': 'string',
                'RefreshToken': 'string',
                'IdToken': 'string',
                'NewDeviceMetadata': {
                    'DeviceKey': 'string',
                    'DeviceGroupKey': 'string'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Responds to the authentication challenge, as an administrator.

        
        

        - **ChallengeName** *(string) --* 

          The name of the challenge.

          
        

        - **Session** *(string) --* 

          The session.

          
        

        - **ChallengeParameters** *(dict) --* 

          The challenge parameters.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **AuthenticationResult** *(dict) --* 

          The result type of the authentication result.

          
          

          - **AccessToken** *(string) --* 

            The access token of the authentication result.

            
          

          - **ExpiresIn** *(integer) --* 

            The expiration period of the authentication result.

            
          

          - **TokenType** *(string) --* 

            The token type of the authentication result.

            
          

          - **RefreshToken** *(string) --* 

            The refresh token of the authentication result.

            
          

          - **IdToken** *(string) --* 

            The ID token of the authentication result.

            
          

          - **NewDeviceMetadata** *(dict) --* 

            The new device metadata from an authentication result.

            
            

            - **DeviceKey** *(string) --* 

              The device key.

              
            

            - **DeviceGroupKey** *(string) --* 

              The device group key.

              
        
      
    

  .. py:method:: admin_set_user_settings(**kwargs)

    

    Sets all the user settings for a specified user name. Works on any user.

    

    **Request Syntax** 
    ::

      response = client.admin_set_user_settings(
          UserPoolId='string',
          Username='string',
          MFAOptions=[
              {
                  'DeliveryMedium': 'SMS'|'EMAIL',
                  'AttributeName': 'string'
              },
          ]
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to set the user's settings, such as MFA options.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user for whom you wish to set user settings.

      

    
    :type MFAOptions: list
    :param MFAOptions: **[REQUIRED]** 

      Specifies the options for MFA (e.g., email or phone number).

      

    
      - *(dict) --* 

        Specifies the different settings for multi-factor authentication (MFA).

        

      
        - **DeliveryMedium** *(string) --* 

          The delivery medium (email message or SMS message) to send the MFA code.

          

        
        - **AttributeName** *(string) --* 

          The attribute name of the MFA option type.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to set user settings as an administrator.

        
    

  .. py:method:: admin_update_device_status(**kwargs)

    

    Updates the device status as an administrator.

    

    **Request Syntax** 
    ::

      response = client.admin_update_device_status(
          UserPoolId='string',
          Username='string',
          DeviceKey='string',
          DeviceRememberedStatus='remembered'|'not_remembered'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID>

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name.

      

    
    :type DeviceKey: string
    :param DeviceKey: **[REQUIRED]** 

      The device key.

      

    
    :type DeviceRememberedStatus: string
    :param DeviceRememberedStatus: 

      The status indicating whether a device has been remembered or not.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The status response from the request to update the device, as an administrator.

        
    

  .. py:method:: admin_update_user_attributes(**kwargs)

    

    Updates the specified user's attributes, including developer attributes, as an administrator. Works on any user.

    

    **Request Syntax** 
    ::

      response = client.admin_update_user_attributes(
          UserPoolId='string',
          Username='string',
          UserAttributes=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to update user attributes.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user for whom you want to update user attributes.

      

    
    :type UserAttributes: list
    :param UserAttributes: **[REQUIRED]** 

      An array of name-value pairs representing user attributes.

      

    
      - *(dict) --* 

        Specifies whether the attribute is standard or custom.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the attribute.

          

        
        - **Value** *(string) --* 

          The value of the attribute.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server for the request to update user attributes as an administrator.

        
    

  .. py:method:: admin_user_global_sign_out(**kwargs)

    

    Signs out users from all devices, as an administrator.

    

    **Request Syntax** 
    ::

      response = client.admin_user_global_sign_out(
          UserPoolId='string',
          Username='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The global sign-out response, as an administrator.

        
    

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


  .. py:method:: change_password(**kwargs)

    

    Changes the password for a specified user in a user pool.

    

    **Request Syntax** 
    ::

      response = client.change_password(
          PreviousPassword='string',
          ProposedPassword='string',
          AccessToken='string'
      )
    :type PreviousPassword: string
    :param PreviousPassword: **[REQUIRED]** 

      The old password in the change password request.

      

    
    :type ProposedPassword: string
    :param ProposedPassword: **[REQUIRED]** 

      The new password in the change password request.

      

    
    :type AccessToken: string
    :param AccessToken: 

      The access token in the change password request.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The response from the server to the change password request.

        
    

  .. py:method:: confirm_device(**kwargs)

    

    Confirms tracking of the device. This API call is the call that beings device tracking.

    

    **Request Syntax** 
    ::

      response = client.confirm_device(
          AccessToken='string',
          DeviceKey='string',
          DeviceSecretVerifierConfig={
              'PasswordVerifier': 'string',
              'Salt': 'string'
          },
          DeviceName='string'
      )
    :type AccessToken: string
    :param AccessToken: **[REQUIRED]** 

      The access token.

      

    
    :type DeviceKey: string
    :param DeviceKey: **[REQUIRED]** 

      The device key.

      

    
    :type DeviceSecretVerifierConfig: dict
    :param DeviceSecretVerifierConfig: 

      The configuration of the device secret verifier.

      

    
      - **PasswordVerifier** *(string) --* 

        The password verifier.

        

      
      - **Salt** *(string) --* 

        The salt.

        

      
    
    :type DeviceName: string
    :param DeviceName: 

      The device name.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserConfirmationNecessary': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 

        Confirms the device response.

        
        

        - **UserConfirmationNecessary** *(boolean) --* 

          Indicates whether the user confirmation is necessary to confirm the device response.

          
    

  .. py:method:: confirm_forgot_password(**kwargs)

    

    Allows a user to enter a code provided when they reset their password to update their password.

    

    **Request Syntax** 
    ::

      response = client.confirm_forgot_password(
          ClientId='string',
          SecretHash='string',
          Username='string',
          ConfirmationCode='string',
          Password='string'
      )
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The ID of the client associated with the user pool.

      

    
    :type SecretHash: string
    :param SecretHash: 

      A keyed-hash message authentication code (HMAC) calculated using the secret key of a user pool client and username plus the client ID in the message.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user for whom you want to enter a code to retrieve a forgotten password.

      

    
    :type ConfirmationCode: string
    :param ConfirmationCode: **[REQUIRED]** 

      The confirmation code sent by a user's request to retrieve a forgotten password.

      

    
    :type Password: string
    :param Password: **[REQUIRED]** 

      The password sent by sent by a user's request to retrieve a forgotten password.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The response from the server that results from a user's request to retrieve a forgotten password.

        
    

  .. py:method:: confirm_sign_up(**kwargs)

    

    Confirms registration of a user and handles the existing alias from a previous user.

    

    **Request Syntax** 
    ::

      response = client.confirm_sign_up(
          ClientId='string',
          SecretHash='string',
          Username='string',
          ConfirmationCode='string',
          ForceAliasCreation=True|False
      )
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The ID of the client associated with the user pool.

      

    
    :type SecretHash: string
    :param SecretHash: 

      A keyed-hash message authentication code (HMAC) calculated using the secret key of a user pool client and username plus the client ID in the message.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user whose registration you wish to confirm.

      

    
    :type ConfirmationCode: string
    :param ConfirmationCode: **[REQUIRED]** 

      The confirmation code sent by a user's request to confirm registration.

      

    
    :type ForceAliasCreation: boolean
    :param ForceAliasCreation: 

      Boolean to be specified to force user confirmation irrespective of existing alias. By default set to False. If this parameter is set to True and the phone number/email used for sign up confirmation already exists as an alias with a different user, the API call will migrate the alias from the previous user to the newly created user being confirmed. If set to False, the API will throw an **AliasExistsException** error.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server for the registration confirmation.

        
    

  .. py:method:: create_user_import_job(**kwargs)

    

    Creates the user import job.

    

    **Request Syntax** 
    ::

      response = client.create_user_import_job(
          JobName='string',
          UserPoolId='string',
          CloudWatchLogsRoleArn='string'
      )
    :type JobName: string
    :param JobName: **[REQUIRED]** 

      The job name for the user import job.

      

    
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool that the users are being imported into.

      

    
    :type CloudWatchLogsRoleArn: string
    :param CloudWatchLogsRoleArn: **[REQUIRED]** 

      The role ARN for the Amazon CloudWatch Logging role for the user import job.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserImportJob': {
                'JobName': 'string',
                'JobId': 'string',
                'UserPoolId': 'string',
                'PreSignedUrl': 'string',
                'CreationDate': datetime(2015, 1, 1),
                'StartDate': datetime(2015, 1, 1),
                'CompletionDate': datetime(2015, 1, 1),
                'Status': 'Created'|'Pending'|'InProgress'|'Stopping'|'Expired'|'Stopped'|'Failed'|'Succeeded',
                'CloudWatchLogsRoleArn': 'string',
                'ImportedUsers': 123,
                'SkippedUsers': 123,
                'FailedUsers': 123,
                'CompletionMessage': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to the request to create the user import job.

        
        

        - **UserImportJob** *(dict) --* 

          The job object that represents the user import job.

          
          

          - **JobName** *(string) --* 

            The job name for the user import job.

            
          

          - **JobId** *(string) --* 

            The job ID for the user import job.

            
          

          - **UserPoolId** *(string) --* 

            The user pool ID for the user pool that the users are being imported into.

            
          

          - **PreSignedUrl** *(string) --* 

            The pre-signed URL to be used to upload the .csv file.

            
          

          - **CreationDate** *(datetime) --* 

            The date when the user import job was created.

            
          

          - **StartDate** *(datetime) --* 

            The date when the user import job was started.

            
          

          - **CompletionDate** *(datetime) --* 

            The date when the user imoprt job was completed.

            
          

          - **Status** *(string) --* 

            The status of the user import job. One of the following:

             

             
            * Created - The job was created but not started.
             
            * Pending - A transition state. You have started the job, but it has not begun importing users yet.
             
            * InProgress - The job has started, and users are being imported.
             
            * Stopping - You have stopped the job, but the job has not stopped importing users yet.
             
            * Stopped - You have stopped the job, and the job has stopped importing users.
             
            * Succeeded - The job has completed successfully.
             
            * Failed - The job has stopped due to an error.
             
            * Expired - You created a job, but did not start the job within 24-48 hours. All data associated with the job was deleted, and the job cannot be started.
             

            
          

          - **CloudWatchLogsRoleArn** *(string) --* 

            The role ARN for the Amazon CloudWatch Logging role for the user import job. For more information, see "Creating the CloudWatch Logs IAM Role" in the Amazon Cognito Developer Guide.

            
          

          - **ImportedUsers** *(integer) --* 

            The number of users that were successfully imported.

            
          

          - **SkippedUsers** *(integer) --* 

            The number of users that were skipped.

            
          

          - **FailedUsers** *(integer) --* 

            The number of users that could not be imported.

            
          

          - **CompletionMessage** *(string) --* 

            The message returned when the user import job is completed.

            
      
    

  .. py:method:: create_user_pool(**kwargs)

    

    Creates a new Amazon Cognito user pool and sets the password policy for the pool.

    

    **Request Syntax** 
    ::

      response = client.create_user_pool(
          PoolName='string',
          Policies={
              'PasswordPolicy': {
                  'MinimumLength': 123,
                  'RequireUppercase': True|False,
                  'RequireLowercase': True|False,
                  'RequireNumbers': True|False,
                  'RequireSymbols': True|False
              }
          },
          LambdaConfig={
              'PreSignUp': 'string',
              'CustomMessage': 'string',
              'PostConfirmation': 'string',
              'PreAuthentication': 'string',
              'PostAuthentication': 'string',
              'DefineAuthChallenge': 'string',
              'CreateAuthChallenge': 'string',
              'VerifyAuthChallengeResponse': 'string'
          },
          AutoVerifiedAttributes=[
              'phone_number'|'email',
          ],
          AliasAttributes=[
              'phone_number'|'email'|'preferred_username',
          ],
          SmsVerificationMessage='string',
          EmailVerificationMessage='string',
          EmailVerificationSubject='string',
          SmsAuthenticationMessage='string',
          MfaConfiguration='OFF'|'ON'|'OPTIONAL',
          DeviceConfiguration={
              'ChallengeRequiredOnNewDevice': True|False,
              'DeviceOnlyRememberedOnUserPrompt': True|False
          },
          EmailConfiguration={
              'SourceArn': 'string',
              'ReplyToEmailAddress': 'string'
          },
          SmsConfiguration={
              'SnsCallerArn': 'string',
              'ExternalId': 'string'
          }
      )
    :type PoolName: string
    :param PoolName: **[REQUIRED]** 

      A string used to name the user pool.

      

    
    :type Policies: dict
    :param Policies: 

      The policies associated with the new user pool.

      

    
      - **PasswordPolicy** *(dict) --* 

        A container with information about the user pool password policy.

        

      
        - **MinimumLength** *(integer) --* 

          The minimum length of the password policy that you have set. Cannot be less than 6.

          

        
        - **RequireUppercase** *(boolean) --* 

          In the password policy that you have set, refers to whether you have required users to use at least one uppercase letter in their password.

          

        
        - **RequireLowercase** *(boolean) --* 

          In the password policy that you have set, refers to whether you have required users to use at least one lowercase letter in their password.

          

        
        - **RequireNumbers** *(boolean) --* 

          In the password policy that you have set, refers to whether you have required users to use at least one number in their password.

          

        
        - **RequireSymbols** *(boolean) --* 

          In the password policy that you have set, refers to whether you have required users to use at least one symbol in their password.

          

        
      
    
    :type LambdaConfig: dict
    :param LambdaConfig: 

      The Lambda trigger configuration information for the new user pool.

      

    
      - **PreSignUp** *(string) --* 

        A pre-registration AWS Lambda trigger.

        

      
      - **CustomMessage** *(string) --* 

        A custom Message AWS Lambda trigger.

        

      
      - **PostConfirmation** *(string) --* 

        A post-confirmation AWS Lambda trigger.

        

      
      - **PreAuthentication** *(string) --* 

        A pre-authentication AWS Lambda trigger.

        

      
      - **PostAuthentication** *(string) --* 

        A post-authentication AWS Lambda trigger.

        

      
      - **DefineAuthChallenge** *(string) --* 

        Defines the authentication challenge.

        

      
      - **CreateAuthChallenge** *(string) --* 

        Creates an authentication challenge.

        

      
      - **VerifyAuthChallengeResponse** *(string) --* 

        Verifies the authentication challenge response.

        

      
    
    :type AutoVerifiedAttributes: list
    :param AutoVerifiedAttributes: 

      The attributes to be auto-verified. Possible values: **email** , **phone_number** .

      

    
      - *(string) --* 

      
  
    :type AliasAttributes: list
    :param AliasAttributes: 

      Attributes supported as an alias for this user pool. Possible values: **phone_number** , **email** , or **preferred_username** .

      

    
      - *(string) --* 

      
  
    :type SmsVerificationMessage: string
    :param SmsVerificationMessage: 

      A string representing the SMS verification message.

      

    
    :type EmailVerificationMessage: string
    :param EmailVerificationMessage: 

      A string representing the email verification message.

      

    
    :type EmailVerificationSubject: string
    :param EmailVerificationSubject: 

      A string representing the email verification subject.

      

    
    :type SmsAuthenticationMessage: string
    :param SmsAuthenticationMessage: 

      A string representing the SMS authentication message.

      

    
    :type MfaConfiguration: string
    :param MfaConfiguration: 

      Specifies MFA configuration details.

      

    
    :type DeviceConfiguration: dict
    :param DeviceConfiguration: 

      The device configuration.

      

    
      - **ChallengeRequiredOnNewDevice** *(boolean) --* 

        Indicates whether a challenge is required on a new device. Only applicable to a new device.

        

      
      - **DeviceOnlyRememberedOnUserPrompt** *(boolean) --* 

        If true, a device is only remembered on user prompt.

        

      
    
    :type EmailConfiguration: dict
    :param EmailConfiguration: 

      The email configuration.

      

    
      - **SourceArn** *(string) --* 

        The Amazon Resource Name (ARN) of the email source.

        

      
      - **ReplyToEmailAddress** *(string) --* 

        The REPLY-TO email address.

        

      
    
    :type SmsConfiguration: dict
    :param SmsConfiguration: 

      The SMS configuration.

      

    
      - **SnsCallerArn** *(string) --* 

        The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) caller.

        

      
      - **ExternalId** *(string) --* 

        The external ID.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserPool': {
                'Id': 'string',
                'Name': 'string',
                'Policies': {
                    'PasswordPolicy': {
                        'MinimumLength': 123,
                        'RequireUppercase': True|False,
                        'RequireLowercase': True|False,
                        'RequireNumbers': True|False,
                        'RequireSymbols': True|False
                    }
                },
                'LambdaConfig': {
                    'PreSignUp': 'string',
                    'CustomMessage': 'string',
                    'PostConfirmation': 'string',
                    'PreAuthentication': 'string',
                    'PostAuthentication': 'string',
                    'DefineAuthChallenge': 'string',
                    'CreateAuthChallenge': 'string',
                    'VerifyAuthChallengeResponse': 'string'
                },
                'Status': 'Enabled'|'Disabled',
                'LastModifiedDate': datetime(2015, 1, 1),
                'CreationDate': datetime(2015, 1, 1),
                'SchemaAttributes': [
                    {
                        'Name': 'string',
                        'AttributeDataType': 'String'|'Number'|'DateTime'|'Boolean',
                        'DeveloperOnlyAttribute': True|False,
                        'Mutable': True|False,
                        'Required': True|False,
                        'NumberAttributeConstraints': {
                            'MinValue': 'string',
                            'MaxValue': 'string'
                        },
                        'StringAttributeConstraints': {
                            'MinLength': 'string',
                            'MaxLength': 'string'
                        }
                    },
                ],
                'AutoVerifiedAttributes': [
                    'phone_number'|'email',
                ],
                'AliasAttributes': [
                    'phone_number'|'email'|'preferred_username',
                ],
                'SmsVerificationMessage': 'string',
                'EmailVerificationMessage': 'string',
                'EmailVerificationSubject': 'string',
                'SmsAuthenticationMessage': 'string',
                'MfaConfiguration': 'OFF'|'ON'|'OPTIONAL',
                'DeviceConfiguration': {
                    'ChallengeRequiredOnNewDevice': True|False,
                    'DeviceOnlyRememberedOnUserPrompt': True|False
                },
                'EstimatedNumberOfUsers': 123,
                'EmailConfiguration': {
                    'SourceArn': 'string',
                    'ReplyToEmailAddress': 'string'
                },
                'SmsConfiguration': {
                    'SnsCallerArn': 'string',
                    'ExternalId': 'string'
                },
                'SmsConfigurationFailure': 'string',
                'EmailConfigurationFailure': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server for the request to create a user pool.

        
        

        - **UserPool** *(dict) --* 

          A container for the user pool details.

          
          

          - **Id** *(string) --* 

            The ID of the user pool.

            
          

          - **Name** *(string) --* 

            The name of the user pool.

            
          

          - **Policies** *(dict) --* 

            A container describing the policies associated with a user pool.

            
            

            - **PasswordPolicy** *(dict) --* 

              A container with information about the user pool password policy.

              
              

              - **MinimumLength** *(integer) --* 

                The minimum length of the password policy that you have set. Cannot be less than 6.

                
              

              - **RequireUppercase** *(boolean) --* 

                In the password policy that you have set, refers to whether you have required users to use at least one uppercase letter in their password.

                
              

              - **RequireLowercase** *(boolean) --* 

                In the password policy that you have set, refers to whether you have required users to use at least one lowercase letter in their password.

                
              

              - **RequireNumbers** *(boolean) --* 

                In the password policy that you have set, refers to whether you have required users to use at least one number in their password.

                
              

              - **RequireSymbols** *(boolean) --* 

                In the password policy that you have set, refers to whether you have required users to use at least one symbol in their password.

                
          
        
          

          - **LambdaConfig** *(dict) --* 

            A container describing the AWS Lambda triggers associated with a user pool.

            
            

            - **PreSignUp** *(string) --* 

              A pre-registration AWS Lambda trigger.

              
            

            - **CustomMessage** *(string) --* 

              A custom Message AWS Lambda trigger.

              
            

            - **PostConfirmation** *(string) --* 

              A post-confirmation AWS Lambda trigger.

              
            

            - **PreAuthentication** *(string) --* 

              A pre-authentication AWS Lambda trigger.

              
            

            - **PostAuthentication** *(string) --* 

              A post-authentication AWS Lambda trigger.

              
            

            - **DefineAuthChallenge** *(string) --* 

              Defines the authentication challenge.

              
            

            - **CreateAuthChallenge** *(string) --* 

              Creates an authentication challenge.

              
            

            - **VerifyAuthChallengeResponse** *(string) --* 

              Verifies the authentication challenge response.

              
        
          

          - **Status** *(string) --* 

            The status of a user pool.

            
          

          - **LastModifiedDate** *(datetime) --* 

            The last modified date of a user pool.

            
          

          - **CreationDate** *(datetime) --* 

            The creation date of a user pool.

            
          

          - **SchemaAttributes** *(list) --* 

            A container with the schema attributes of a user pool.

            
            

            - *(dict) --* 

              Contains information about the schema attribute.

              
              

              - **Name** *(string) --* 

                A schema attribute of the name type.

                
              

              - **AttributeDataType** *(string) --* 

                The attribute data type.

                
              

              - **DeveloperOnlyAttribute** *(boolean) --* 

                Specifies whether the attribute type is developer only.

                
              

              - **Mutable** *(boolean) --* 

                Specifies whether the attribute can be changed once it has been created.

                
              

              - **Required** *(boolean) --* 

                Specifies whether a user pool attribute is required. If the attribute is required and the user does not provide a value, registration or sign-in will fail.

                
              

              - **NumberAttributeConstraints** *(dict) --* 

                Specifies the constraints for an attribute of the number type.

                
                

                - **MinValue** *(string) --* 

                  The minimum value of an attribute that is of the number data type.

                  
                

                - **MaxValue** *(string) --* 

                  The maximum value of an attribute that is of the number data type.

                  
            
              

              - **StringAttributeConstraints** *(dict) --* 

                Specifies the constraints for an attribute of the string type.

                
                

                - **MinLength** *(string) --* 

                  The minimum length of an attribute value of the string type.

                  
                

                - **MaxLength** *(string) --* 

                  The maximum length of an attribute value of the string type.

                  
            
          
        
          

          - **AutoVerifiedAttributes** *(list) --* 

            Specifies the attributes that are auto-verified in a user pool.

            
            

            - *(string) --* 
        
          

          - **AliasAttributes** *(list) --* 

            Specifies the attributes that are aliased in a user pool.

            
            

            - *(string) --* 
        
          

          - **SmsVerificationMessage** *(string) --* 

            The contents of the SMS verification message.

            
          

          - **EmailVerificationMessage** *(string) --* 

            The contents of the email verification message.

            
          

          - **EmailVerificationSubject** *(string) --* 

            The subject of the email verification message.

            
          

          - **SmsAuthenticationMessage** *(string) --* 

            The contents of the SMS authentication message.

            
          

          - **MfaConfiguration** *(string) --* 

            Can be one of the following values:

             

             
            * ``OFF`` - MFA tokens are not required and cannot be specified during user registration.
             
            * ``ON`` - MFA tokens are required for all user registrations. You can only specify required when you are initially creating a user pool.
             
            * ``OPTIONAL`` - Users have the option when registering to create an MFA token.
             

            
          

          - **DeviceConfiguration** *(dict) --* 

            The device configuration.

            
            

            - **ChallengeRequiredOnNewDevice** *(boolean) --* 

              Indicates whether a challenge is required on a new device. Only applicable to a new device.

              
            

            - **DeviceOnlyRememberedOnUserPrompt** *(boolean) --* 

              If true, a device is only remembered on user prompt.

              
        
          

          - **EstimatedNumberOfUsers** *(integer) --* 

            A number estimating the size of the user pool.

            
          

          - **EmailConfiguration** *(dict) --* 

            The email configuration.

            
            

            - **SourceArn** *(string) --* 

              The Amazon Resource Name (ARN) of the email source.

              
            

            - **ReplyToEmailAddress** *(string) --* 

              The REPLY-TO email address.

              
        
          

          - **SmsConfiguration** *(dict) --* 

            The SMS configuration.

            
            

            - **SnsCallerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) caller.

              
            

            - **ExternalId** *(string) --* 

              The external ID.

              
        
          

          - **SmsConfigurationFailure** *(string) --* 

            The reason why the SMS configuration cannot send the message(s) to your users.

            
          

          - **EmailConfigurationFailure** *(string) --* 

            The reason why the email configuration cannot send the messages to your users.

            
      
    

  .. py:method:: create_user_pool_client(**kwargs)

    

    Creates the user pool client.

    

    **Request Syntax** 
    ::

      response = client.create_user_pool_client(
          UserPoolId='string',
          ClientName='string',
          GenerateSecret=True|False,
          RefreshTokenValidity=123,
          ReadAttributes=[
              'string',
          ],
          WriteAttributes=[
              'string',
          ],
          ExplicitAuthFlows=[
              'ADMIN_NO_SRP_AUTH'|'CUSTOM_AUTH_FLOW_ONLY',
          ]
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to create a user pool client.

      

    
    :type ClientName: string
    :param ClientName: **[REQUIRED]** 

      The client name for the user pool client you would like to create.

      

    
    :type GenerateSecret: boolean
    :param GenerateSecret: 

      Boolean to specify whether you want to generate a secret for the user pool client being created.

      

    
    :type RefreshTokenValidity: integer
    :param RefreshTokenValidity: 

      Refreshes the token validity.

      

    
    :type ReadAttributes: list
    :param ReadAttributes: 

      The read attributes.

      

    
      - *(string) --* 

      
  
    :type WriteAttributes: list
    :param WriteAttributes: 

      The write attributes.

      

    
      - *(string) --* 

      
  
    :type ExplicitAuthFlows: list
    :param ExplicitAuthFlows: 

      The explicit authentication flows.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserPoolClient': {
                'UserPoolId': 'string',
                'ClientName': 'string',
                'ClientId': 'string',
                'ClientSecret': 'string',
                'LastModifiedDate': datetime(2015, 1, 1),
                'CreationDate': datetime(2015, 1, 1),
                'RefreshTokenValidity': 123,
                'ReadAttributes': [
                    'string',
                ],
                'WriteAttributes': [
                    'string',
                ],
                'ExplicitAuthFlows': [
                    'ADMIN_NO_SRP_AUTH'|'CUSTOM_AUTH_FLOW_ONLY',
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to create a user pool client.

        
        

        - **UserPoolClient** *(dict) --* 

          The user pool client that was just created.

          
          

          - **UserPoolId** *(string) --* 

            The user pool ID for the user pool client.

            
          

          - **ClientName** *(string) --* 

            The client name from the user pool request of the client type.

            
          

          - **ClientId** *(string) --* 

            The ID of the client associated with the user pool.

            
          

          - **ClientSecret** *(string) --* 

            The client secret from the user pool request of the client type.

            
          

          - **LastModifiedDate** *(datetime) --* 

            The last modified date from the user pool request of the client type.

            
          

          - **CreationDate** *(datetime) --* 

            The creation date from the user pool request of the client type.

            
          

          - **RefreshTokenValidity** *(integer) --* 

            The validity of the refresh token.

            
          

          - **ReadAttributes** *(list) --* 

            The Read-only attributes.

            
            

            - *(string) --* 
        
          

          - **WriteAttributes** *(list) --* 

            The writeable attributes.

            
            

            - *(string) --* 
        
          

          - **ExplicitAuthFlows** *(list) --* 

            The explicit authentication flows.

            
            

            - *(string) --* 
        
      
    

  .. py:method:: delete_user(**kwargs)

    

    Allows a user to delete one's self.

    

    **Request Syntax** 
    ::

      response = client.delete_user(
          AccessToken='string'
      )
    :type AccessToken: string
    :param AccessToken: 

      The access token from a request to delete a user.

      

    
    
    :returns: None

  .. py:method:: delete_user_attributes(**kwargs)

    

    Deletes the attributes for a user.

    

    **Request Syntax** 
    ::

      response = client.delete_user_attributes(
          UserAttributeNames=[
              'string',
          ],
          AccessToken='string'
      )
    :type UserAttributeNames: list
    :param UserAttributeNames: **[REQUIRED]** 

      An array of strings representing the user attribute names you wish to delete.

      

    
      - *(string) --* 

      
  
    :type AccessToken: string
    :param AccessToken: 

      The access token used in the request to delete user attributes.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to delete user attributes.

        
    

  .. py:method:: delete_user_pool(**kwargs)

    

    Deletes the specified Amazon Cognito user pool.

    

    **Request Syntax** 
    ::

      response = client.delete_user_pool(
          UserPoolId='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool you want to delete.

      

    
    
    :returns: None

  .. py:method:: delete_user_pool_client(**kwargs)

    

    Allows the developer to delete the user pool client.

    

    **Request Syntax** 
    ::

      response = client.delete_user_pool_client(
          UserPoolId='string',
          ClientId='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to delete the client.

      

    
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The ID of the client associated with the user pool.

      

    
    
    :returns: None

  .. py:method:: describe_user_import_job(**kwargs)

    

    Describes the user import job.

    

    **Request Syntax** 
    ::

      response = client.describe_user_import_job(
          UserPoolId='string',
          JobId='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool that the users are being imported into.

      

    
    :type JobId: string
    :param JobId: **[REQUIRED]** 

      The job ID for the user import job.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserImportJob': {
                'JobName': 'string',
                'JobId': 'string',
                'UserPoolId': 'string',
                'PreSignedUrl': 'string',
                'CreationDate': datetime(2015, 1, 1),
                'StartDate': datetime(2015, 1, 1),
                'CompletionDate': datetime(2015, 1, 1),
                'Status': 'Created'|'Pending'|'InProgress'|'Stopping'|'Expired'|'Stopped'|'Failed'|'Succeeded',
                'CloudWatchLogsRoleArn': 'string',
                'ImportedUsers': 123,
                'SkippedUsers': 123,
                'FailedUsers': 123,
                'CompletionMessage': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to the request to describe the user import job.

        
        

        - **UserImportJob** *(dict) --* 

          The job object that represents the user import job.

          
          

          - **JobName** *(string) --* 

            The job name for the user import job.

            
          

          - **JobId** *(string) --* 

            The job ID for the user import job.

            
          

          - **UserPoolId** *(string) --* 

            The user pool ID for the user pool that the users are being imported into.

            
          

          - **PreSignedUrl** *(string) --* 

            The pre-signed URL to be used to upload the .csv file.

            
          

          - **CreationDate** *(datetime) --* 

            The date when the user import job was created.

            
          

          - **StartDate** *(datetime) --* 

            The date when the user import job was started.

            
          

          - **CompletionDate** *(datetime) --* 

            The date when the user imoprt job was completed.

            
          

          - **Status** *(string) --* 

            The status of the user import job. One of the following:

             

             
            * Created - The job was created but not started.
             
            * Pending - A transition state. You have started the job, but it has not begun importing users yet.
             
            * InProgress - The job has started, and users are being imported.
             
            * Stopping - You have stopped the job, but the job has not stopped importing users yet.
             
            * Stopped - You have stopped the job, and the job has stopped importing users.
             
            * Succeeded - The job has completed successfully.
             
            * Failed - The job has stopped due to an error.
             
            * Expired - You created a job, but did not start the job within 24-48 hours. All data associated with the job was deleted, and the job cannot be started.
             

            
          

          - **CloudWatchLogsRoleArn** *(string) --* 

            The role ARN for the Amazon CloudWatch Logging role for the user import job. For more information, see "Creating the CloudWatch Logs IAM Role" in the Amazon Cognito Developer Guide.

            
          

          - **ImportedUsers** *(integer) --* 

            The number of users that were successfully imported.

            
          

          - **SkippedUsers** *(integer) --* 

            The number of users that were skipped.

            
          

          - **FailedUsers** *(integer) --* 

            The number of users that could not be imported.

            
          

          - **CompletionMessage** *(string) --* 

            The message returned when the user import job is completed.

            
      
    

  .. py:method:: describe_user_pool(**kwargs)

    

    Returns the configuration information and metadata of the specified user pool.

    

    **Request Syntax** 
    ::

      response = client.describe_user_pool(
          UserPoolId='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool you want to describe.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserPool': {
                'Id': 'string',
                'Name': 'string',
                'Policies': {
                    'PasswordPolicy': {
                        'MinimumLength': 123,
                        'RequireUppercase': True|False,
                        'RequireLowercase': True|False,
                        'RequireNumbers': True|False,
                        'RequireSymbols': True|False
                    }
                },
                'LambdaConfig': {
                    'PreSignUp': 'string',
                    'CustomMessage': 'string',
                    'PostConfirmation': 'string',
                    'PreAuthentication': 'string',
                    'PostAuthentication': 'string',
                    'DefineAuthChallenge': 'string',
                    'CreateAuthChallenge': 'string',
                    'VerifyAuthChallengeResponse': 'string'
                },
                'Status': 'Enabled'|'Disabled',
                'LastModifiedDate': datetime(2015, 1, 1),
                'CreationDate': datetime(2015, 1, 1),
                'SchemaAttributes': [
                    {
                        'Name': 'string',
                        'AttributeDataType': 'String'|'Number'|'DateTime'|'Boolean',
                        'DeveloperOnlyAttribute': True|False,
                        'Mutable': True|False,
                        'Required': True|False,
                        'NumberAttributeConstraints': {
                            'MinValue': 'string',
                            'MaxValue': 'string'
                        },
                        'StringAttributeConstraints': {
                            'MinLength': 'string',
                            'MaxLength': 'string'
                        }
                    },
                ],
                'AutoVerifiedAttributes': [
                    'phone_number'|'email',
                ],
                'AliasAttributes': [
                    'phone_number'|'email'|'preferred_username',
                ],
                'SmsVerificationMessage': 'string',
                'EmailVerificationMessage': 'string',
                'EmailVerificationSubject': 'string',
                'SmsAuthenticationMessage': 'string',
                'MfaConfiguration': 'OFF'|'ON'|'OPTIONAL',
                'DeviceConfiguration': {
                    'ChallengeRequiredOnNewDevice': True|False,
                    'DeviceOnlyRememberedOnUserPrompt': True|False
                },
                'EstimatedNumberOfUsers': 123,
                'EmailConfiguration': {
                    'SourceArn': 'string',
                    'ReplyToEmailAddress': 'string'
                },
                'SmsConfiguration': {
                    'SnsCallerArn': 'string',
                    'ExternalId': 'string'
                },
                'SmsConfigurationFailure': 'string',
                'EmailConfigurationFailure': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response to describe the user pool.

        
        

        - **UserPool** *(dict) --* 

          The container of metadata returned by the server to describe the pool.

          
          

          - **Id** *(string) --* 

            The ID of the user pool.

            
          

          - **Name** *(string) --* 

            The name of the user pool.

            
          

          - **Policies** *(dict) --* 

            A container describing the policies associated with a user pool.

            
            

            - **PasswordPolicy** *(dict) --* 

              A container with information about the user pool password policy.

              
              

              - **MinimumLength** *(integer) --* 

                The minimum length of the password policy that you have set. Cannot be less than 6.

                
              

              - **RequireUppercase** *(boolean) --* 

                In the password policy that you have set, refers to whether you have required users to use at least one uppercase letter in their password.

                
              

              - **RequireLowercase** *(boolean) --* 

                In the password policy that you have set, refers to whether you have required users to use at least one lowercase letter in their password.

                
              

              - **RequireNumbers** *(boolean) --* 

                In the password policy that you have set, refers to whether you have required users to use at least one number in their password.

                
              

              - **RequireSymbols** *(boolean) --* 

                In the password policy that you have set, refers to whether you have required users to use at least one symbol in their password.

                
          
        
          

          - **LambdaConfig** *(dict) --* 

            A container describing the AWS Lambda triggers associated with a user pool.

            
            

            - **PreSignUp** *(string) --* 

              A pre-registration AWS Lambda trigger.

              
            

            - **CustomMessage** *(string) --* 

              A custom Message AWS Lambda trigger.

              
            

            - **PostConfirmation** *(string) --* 

              A post-confirmation AWS Lambda trigger.

              
            

            - **PreAuthentication** *(string) --* 

              A pre-authentication AWS Lambda trigger.

              
            

            - **PostAuthentication** *(string) --* 

              A post-authentication AWS Lambda trigger.

              
            

            - **DefineAuthChallenge** *(string) --* 

              Defines the authentication challenge.

              
            

            - **CreateAuthChallenge** *(string) --* 

              Creates an authentication challenge.

              
            

            - **VerifyAuthChallengeResponse** *(string) --* 

              Verifies the authentication challenge response.

              
        
          

          - **Status** *(string) --* 

            The status of a user pool.

            
          

          - **LastModifiedDate** *(datetime) --* 

            The last modified date of a user pool.

            
          

          - **CreationDate** *(datetime) --* 

            The creation date of a user pool.

            
          

          - **SchemaAttributes** *(list) --* 

            A container with the schema attributes of a user pool.

            
            

            - *(dict) --* 

              Contains information about the schema attribute.

              
              

              - **Name** *(string) --* 

                A schema attribute of the name type.

                
              

              - **AttributeDataType** *(string) --* 

                The attribute data type.

                
              

              - **DeveloperOnlyAttribute** *(boolean) --* 

                Specifies whether the attribute type is developer only.

                
              

              - **Mutable** *(boolean) --* 

                Specifies whether the attribute can be changed once it has been created.

                
              

              - **Required** *(boolean) --* 

                Specifies whether a user pool attribute is required. If the attribute is required and the user does not provide a value, registration or sign-in will fail.

                
              

              - **NumberAttributeConstraints** *(dict) --* 

                Specifies the constraints for an attribute of the number type.

                
                

                - **MinValue** *(string) --* 

                  The minimum value of an attribute that is of the number data type.

                  
                

                - **MaxValue** *(string) --* 

                  The maximum value of an attribute that is of the number data type.

                  
            
              

              - **StringAttributeConstraints** *(dict) --* 

                Specifies the constraints for an attribute of the string type.

                
                

                - **MinLength** *(string) --* 

                  The minimum length of an attribute value of the string type.

                  
                

                - **MaxLength** *(string) --* 

                  The maximum length of an attribute value of the string type.

                  
            
          
        
          

          - **AutoVerifiedAttributes** *(list) --* 

            Specifies the attributes that are auto-verified in a user pool.

            
            

            - *(string) --* 
        
          

          - **AliasAttributes** *(list) --* 

            Specifies the attributes that are aliased in a user pool.

            
            

            - *(string) --* 
        
          

          - **SmsVerificationMessage** *(string) --* 

            The contents of the SMS verification message.

            
          

          - **EmailVerificationMessage** *(string) --* 

            The contents of the email verification message.

            
          

          - **EmailVerificationSubject** *(string) --* 

            The subject of the email verification message.

            
          

          - **SmsAuthenticationMessage** *(string) --* 

            The contents of the SMS authentication message.

            
          

          - **MfaConfiguration** *(string) --* 

            Can be one of the following values:

             

             
            * ``OFF`` - MFA tokens are not required and cannot be specified during user registration.
             
            * ``ON`` - MFA tokens are required for all user registrations. You can only specify required when you are initially creating a user pool.
             
            * ``OPTIONAL`` - Users have the option when registering to create an MFA token.
             

            
          

          - **DeviceConfiguration** *(dict) --* 

            The device configuration.

            
            

            - **ChallengeRequiredOnNewDevice** *(boolean) --* 

              Indicates whether a challenge is required on a new device. Only applicable to a new device.

              
            

            - **DeviceOnlyRememberedOnUserPrompt** *(boolean) --* 

              If true, a device is only remembered on user prompt.

              
        
          

          - **EstimatedNumberOfUsers** *(integer) --* 

            A number estimating the size of the user pool.

            
          

          - **EmailConfiguration** *(dict) --* 

            The email configuration.

            
            

            - **SourceArn** *(string) --* 

              The Amazon Resource Name (ARN) of the email source.

              
            

            - **ReplyToEmailAddress** *(string) --* 

              The REPLY-TO email address.

              
        
          

          - **SmsConfiguration** *(dict) --* 

            The SMS configuration.

            
            

            - **SnsCallerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) caller.

              
            

            - **ExternalId** *(string) --* 

              The external ID.

              
        
          

          - **SmsConfigurationFailure** *(string) --* 

            The reason why the SMS configuration cannot send the message(s) to your users.

            
          

          - **EmailConfigurationFailure** *(string) --* 

            The reason why the email configuration cannot send the messages to your users.

            
      
    

  .. py:method:: describe_user_pool_client(**kwargs)

    

    Client method for returning the configuration information and metadata of the specified user pool client.

    

    **Request Syntax** 
    ::

      response = client.describe_user_pool_client(
          UserPoolId='string',
          ClientId='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool you want to describe.

      

    
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The ID of the client associated with the user pool.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserPoolClient': {
                'UserPoolId': 'string',
                'ClientName': 'string',
                'ClientId': 'string',
                'ClientSecret': 'string',
                'LastModifiedDate': datetime(2015, 1, 1),
                'CreationDate': datetime(2015, 1, 1),
                'RefreshTokenValidity': 123,
                'ReadAttributes': [
                    'string',
                ],
                'WriteAttributes': [
                    'string',
                ],
                'ExplicitAuthFlows': [
                    'ADMIN_NO_SRP_AUTH'|'CUSTOM_AUTH_FLOW_ONLY',
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server from a request to describe the user pool client.

        
        

        - **UserPoolClient** *(dict) --* 

          The user pool client from a server response to describe the user pool client.

          
          

          - **UserPoolId** *(string) --* 

            The user pool ID for the user pool client.

            
          

          - **ClientName** *(string) --* 

            The client name from the user pool request of the client type.

            
          

          - **ClientId** *(string) --* 

            The ID of the client associated with the user pool.

            
          

          - **ClientSecret** *(string) --* 

            The client secret from the user pool request of the client type.

            
          

          - **LastModifiedDate** *(datetime) --* 

            The last modified date from the user pool request of the client type.

            
          

          - **CreationDate** *(datetime) --* 

            The creation date from the user pool request of the client type.

            
          

          - **RefreshTokenValidity** *(integer) --* 

            The validity of the refresh token.

            
          

          - **ReadAttributes** *(list) --* 

            The Read-only attributes.

            
            

            - *(string) --* 
        
          

          - **WriteAttributes** *(list) --* 

            The writeable attributes.

            
            

            - *(string) --* 
        
          

          - **ExplicitAuthFlows** *(list) --* 

            The explicit authentication flows.

            
            

            - *(string) --* 
        
      
    

  .. py:method:: forget_device(**kwargs)

    

    Forgets the specified device.

    

    **Request Syntax** 
    ::

      response = client.forget_device(
          AccessToken='string',
          DeviceKey='string'
      )
    :type AccessToken: string
    :param AccessToken: 

      The access token for the forgotten device request.

      

    
    :type DeviceKey: string
    :param DeviceKey: **[REQUIRED]** 

      The device key.

      

    
    
    :returns: None

  .. py:method:: forgot_password(**kwargs)

    

    Retrieves the password for the specified client ID or username.

    

    **Request Syntax** 
    ::

      response = client.forgot_password(
          ClientId='string',
          SecretHash='string',
          Username='string'
      )
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The ID of the client associated with the user pool.

      

    
    :type SecretHash: string
    :param SecretHash: 

      A keyed-hash message authentication code (HMAC) calculated using the secret key of a user pool client and username plus the client ID in the message.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user for whom you want to enter a code to retrieve a forgotten password.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CodeDeliveryDetails': {
                'Destination': 'string',
                'DeliveryMedium': 'SMS'|'EMAIL',
                'AttributeName': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Respresents the response from the server regarding the request to reset a password.

        
        

        - **CodeDeliveryDetails** *(dict) --* 

          The type of code delivery details being returned from the server.

          
          

          - **Destination** *(string) --* 

            The destination for the code delivery details.

            
          

          - **DeliveryMedium** *(string) --* 

            The delivery medium (email message or phone number).

            
          

          - **AttributeName** *(string) --* 

            The name of the attribute in the code delivery details type.

            
      
    

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


  .. py:method:: get_csv_header(**kwargs)

    

    Gets the header information for the .csv file to be used as input for the user import job.

    

    **Request Syntax** 
    ::

      response = client.get_csv_header(
          UserPoolId='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool that the users are to be imported into.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserPoolId': 'string',
            'CSVHeader': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to the request to get the header information for the .csv file for the user import job.

        
        

        - **UserPoolId** *(string) --* 

          The user pool ID for the user pool that the users are to be imported into.

          
        

        - **CSVHeader** *(list) --* 

          The header information for the .csv file for the user import job.

          
          

          - *(string) --* 
      
    

  .. py:method:: get_device(**kwargs)

    

    Gets the device.

    

    **Request Syntax** 
    ::

      response = client.get_device(
          DeviceKey='string',
          AccessToken='string'
      )
    :type DeviceKey: string
    :param DeviceKey: **[REQUIRED]** 

      The device key.

      

    
    :type AccessToken: string
    :param AccessToken: 

      The access token.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Device': {
                'DeviceKey': 'string',
                'DeviceAttributes': [
                    {
                        'Name': 'string',
                        'Value': 'string'
                    },
                ],
                'DeviceCreateDate': datetime(2015, 1, 1),
                'DeviceLastModifiedDate': datetime(2015, 1, 1),
                'DeviceLastAuthenticatedDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Gets the device response.

        
        

        - **Device** *(dict) --* 

          The device.

          
          

          - **DeviceKey** *(string) --* 

            The device key.

            
          

          - **DeviceAttributes** *(list) --* 

            The device attributes.

            
            

            - *(dict) --* 

              Specifies whether the attribute is standard or custom.

              
              

              - **Name** *(string) --* 

                The name of the attribute.

                
              

              - **Value** *(string) --* 

                The value of the attribute.

                
          
        
          

          - **DeviceCreateDate** *(datetime) --* 

            The creation date of the device.

            
          

          - **DeviceLastModifiedDate** *(datetime) --* 

            The last modified date of the device.

            
          

          - **DeviceLastAuthenticatedDate** *(datetime) --* 

            The date in which the device was last authenticated.

            
      
    

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


  .. py:method:: get_user(**kwargs)

    

    Gets the user attributes and metadata for a user.

    

    **Request Syntax** 
    ::

      response = client.get_user(
          AccessToken='string'
      )
    :type AccessToken: string
    :param AccessToken: 

      The access token returned by the server response to get information about the user.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Username': 'string',
            'UserAttributes': [
                {
                    'Name': 'string',
                    'Value': 'string'
                },
            ],
            'MFAOptions': [
                {
                    'DeliveryMedium': 'SMS'|'EMAIL',
                    'AttributeName': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server from the request to get information about the user.

        
        

        - **Username** *(string) --* 

          The user name of the user you wish to retrieve from the get user request.

          
        

        - **UserAttributes** *(list) --* 

          An array of name-value pairs representing user attributes.

          
          

          - *(dict) --* 

            Specifies whether the attribute is standard or custom.

            
            

            - **Name** *(string) --* 

              The name of the attribute.

              
            

            - **Value** *(string) --* 

              The value of the attribute.

              
        
      
        

        - **MFAOptions** *(list) --* 

          Specifies the options for MFA (e.g., email or phone number).

          
          

          - *(dict) --* 

            Specifies the different settings for multi-factor authentication (MFA).

            
            

            - **DeliveryMedium** *(string) --* 

              The delivery medium (email message or SMS message) to send the MFA code.

              
            

            - **AttributeName** *(string) --* 

              The attribute name of the MFA option type.

              
        
      
    

  .. py:method:: get_user_attribute_verification_code(**kwargs)

    

    Gets the user attribute verification code for the specified attribute name.

    

    **Request Syntax** 
    ::

      response = client.get_user_attribute_verification_code(
          AccessToken='string',
          AttributeName='string'
      )
    :type AccessToken: string
    :param AccessToken: 

      The access token returned by the server response to get the user attribute verification code.

      

    
    :type AttributeName: string
    :param AttributeName: **[REQUIRED]** 

      The attribute name returned by the server response to get the user attribute verification code.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CodeDeliveryDetails': {
                'Destination': 'string',
                'DeliveryMedium': 'SMS'|'EMAIL',
                'AttributeName': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The verification code response returned by the server response to get the user attribute verification code.

        
        

        - **CodeDeliveryDetails** *(dict) --* 

          The code delivery details returned by the server response to get the user attribute verification code.

          
          

          - **Destination** *(string) --* 

            The destination for the code delivery details.

            
          

          - **DeliveryMedium** *(string) --* 

            The delivery medium (email message or phone number).

            
          

          - **AttributeName** *(string) --* 

            The name of the attribute in the code delivery details type.

            
      
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: global_sign_out(**kwargs)

    

    Signs out users from all devices.

    

    **Request Syntax** 
    ::

      response = client.global_sign_out(
          AccessToken='string'
      )
    :type AccessToken: string
    :param AccessToken: 

      The access token.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The response to the request to sign out all devices.

        
    

  .. py:method:: initiate_auth(**kwargs)

    

    Initiates the authentication flow.

    

    **Request Syntax** 
    ::

      response = client.initiate_auth(
          AuthFlow='USER_SRP_AUTH'|'REFRESH_TOKEN_AUTH'|'REFRESH_TOKEN'|'CUSTOM_AUTH'|'ADMIN_NO_SRP_AUTH',
          AuthParameters={
              'string': 'string'
          },
          ClientMetadata={
              'string': 'string'
          },
          ClientId='string'
      )
    :type AuthFlow: string
    :param AuthFlow: **[REQUIRED]** 

      The authentication flow.

      

    
    :type AuthParameters: dict
    :param AuthParameters: 

      The authentication parameters.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type ClientMetadata: dict
    :param ClientMetadata: 

      The client app's metadata.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The client ID.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChallengeName': 'SMS_MFA'|'PASSWORD_VERIFIER'|'CUSTOM_CHALLENGE'|'DEVICE_SRP_AUTH'|'DEVICE_PASSWORD_VERIFIER'|'ADMIN_NO_SRP_AUTH',
            'Session': 'string',
            'ChallengeParameters': {
                'string': 'string'
            },
            'AuthenticationResult': {
                'AccessToken': 'string',
                'ExpiresIn': 123,
                'TokenType': 'string',
                'RefreshToken': 'string',
                'IdToken': 'string',
                'NewDeviceMetadata': {
                    'DeviceKey': 'string',
                    'DeviceGroupKey': 'string'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Initiates the authentication response.

        
        

        - **ChallengeName** *(string) --* 

          The name of the challenge.

          
        

        - **Session** *(string) --* 

          The session.

          
        

        - **ChallengeParameters** *(dict) --* 

          The challenge parameters.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **AuthenticationResult** *(dict) --* 

          The result type of the authentication result.

          
          

          - **AccessToken** *(string) --* 

            The access token of the authentication result.

            
          

          - **ExpiresIn** *(integer) --* 

            The expiration period of the authentication result.

            
          

          - **TokenType** *(string) --* 

            The token type of the authentication result.

            
          

          - **RefreshToken** *(string) --* 

            The refresh token of the authentication result.

            
          

          - **IdToken** *(string) --* 

            The ID token of the authentication result.

            
          

          - **NewDeviceMetadata** *(dict) --* 

            The new device metadata from an authentication result.

            
            

            - **DeviceKey** *(string) --* 

              The device key.

              
            

            - **DeviceGroupKey** *(string) --* 

              The device group key.

              
        
      
    

  .. py:method:: list_devices(**kwargs)

    

    Lists the devices.

    

    **Request Syntax** 
    ::

      response = client.list_devices(
          AccessToken='string',
          Limit=123,
          PaginationToken='string'
      )
    :type AccessToken: string
    :param AccessToken: **[REQUIRED]** 

      The access tokens for the request to list devices.

      

    
    :type Limit: integer
    :param Limit: 

      The limit of the device request.

      

    
    :type PaginationToken: string
    :param PaginationToken: 

      The pagination token for the list request.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Devices': [
                {
                    'DeviceKey': 'string',
                    'DeviceAttributes': [
                        {
                            'Name': 'string',
                            'Value': 'string'
                        },
                    ],
                    'DeviceCreateDate': datetime(2015, 1, 1),
                    'DeviceLastModifiedDate': datetime(2015, 1, 1),
                    'DeviceLastAuthenticatedDate': datetime(2015, 1, 1)
                },
            ],
            'PaginationToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response to list devices.

        
        

        - **Devices** *(list) --* 

          The devices returned in the list devices response.

          
          

          - *(dict) --* 

            The device type.

            
            

            - **DeviceKey** *(string) --* 

              The device key.

              
            

            - **DeviceAttributes** *(list) --* 

              The device attributes.

              
              

              - *(dict) --* 

                Specifies whether the attribute is standard or custom.

                
                

                - **Name** *(string) --* 

                  The name of the attribute.

                  
                

                - **Value** *(string) --* 

                  The value of the attribute.

                  
            
          
            

            - **DeviceCreateDate** *(datetime) --* 

              The creation date of the device.

              
            

            - **DeviceLastModifiedDate** *(datetime) --* 

              The last modified date of the device.

              
            

            - **DeviceLastAuthenticatedDate** *(datetime) --* 

              The date in which the device was last authenticated.

              
        
      
        

        - **PaginationToken** *(string) --* 

          The pagination token for the list device response.

          
    

  .. py:method:: list_user_import_jobs(**kwargs)

    

    Lists the user import jobs.

    

    **Request Syntax** 
    ::

      response = client.list_user_import_jobs(
          UserPoolId='string',
          MaxResults=123,
          PaginationToken='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool that the users are being imported into.

      

    
    :type MaxResults: integer
    :param MaxResults: **[REQUIRED]** 

      The maximum number of import jobs you want the request to return.

      

    
    :type PaginationToken: string
    :param PaginationToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of import jobs in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserImportJobs': [
                {
                    'JobName': 'string',
                    'JobId': 'string',
                    'UserPoolId': 'string',
                    'PreSignedUrl': 'string',
                    'CreationDate': datetime(2015, 1, 1),
                    'StartDate': datetime(2015, 1, 1),
                    'CompletionDate': datetime(2015, 1, 1),
                    'Status': 'Created'|'Pending'|'InProgress'|'Stopping'|'Expired'|'Stopped'|'Failed'|'Succeeded',
                    'CloudWatchLogsRoleArn': 'string',
                    'ImportedUsers': 123,
                    'SkippedUsers': 123,
                    'FailedUsers': 123,
                    'CompletionMessage': 'string'
                },
            ],
            'PaginationToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to the request to list the user import jobs.

        
        

        - **UserImportJobs** *(list) --* 

          The user import jobs.

          
          

          - *(dict) --* 

            The user import job type.

            
            

            - **JobName** *(string) --* 

              The job name for the user import job.

              
            

            - **JobId** *(string) --* 

              The job ID for the user import job.

              
            

            - **UserPoolId** *(string) --* 

              The user pool ID for the user pool that the users are being imported into.

              
            

            - **PreSignedUrl** *(string) --* 

              The pre-signed URL to be used to upload the .csv file.

              
            

            - **CreationDate** *(datetime) --* 

              The date when the user import job was created.

              
            

            - **StartDate** *(datetime) --* 

              The date when the user import job was started.

              
            

            - **CompletionDate** *(datetime) --* 

              The date when the user imoprt job was completed.

              
            

            - **Status** *(string) --* 

              The status of the user import job. One of the following:

               

               
              * Created - The job was created but not started.
               
              * Pending - A transition state. You have started the job, but it has not begun importing users yet.
               
              * InProgress - The job has started, and users are being imported.
               
              * Stopping - You have stopped the job, but the job has not stopped importing users yet.
               
              * Stopped - You have stopped the job, and the job has stopped importing users.
               
              * Succeeded - The job has completed successfully.
               
              * Failed - The job has stopped due to an error.
               
              * Expired - You created a job, but did not start the job within 24-48 hours. All data associated with the job was deleted, and the job cannot be started.
               

              
            

            - **CloudWatchLogsRoleArn** *(string) --* 

              The role ARN for the Amazon CloudWatch Logging role for the user import job. For more information, see "Creating the CloudWatch Logs IAM Role" in the Amazon Cognito Developer Guide.

              
            

            - **ImportedUsers** *(integer) --* 

              The number of users that were successfully imported.

              
            

            - **SkippedUsers** *(integer) --* 

              The number of users that were skipped.

              
            

            - **FailedUsers** *(integer) --* 

              The number of users that could not be imported.

              
            

            - **CompletionMessage** *(string) --* 

              The message returned when the user import job is completed.

              
        
      
        

        - **PaginationToken** *(string) --* 

          An identifier that can be used to return the next set of user import jobs in the list.

          
    

  .. py:method:: list_user_pool_clients(**kwargs)

    

    Lists the clients that have been created for the specified user pool.

    

    **Request Syntax** 
    ::

      response = client.list_user_pool_clients(
          UserPoolId='string',
          MaxResults=123,
          NextToken='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to list user pool clients.

      

    
    :type MaxResults: integer
    :param MaxResults: 

      The maximum number of results you want the request to return when listing the user pool clients.

      

    
    :type NextToken: string
    :param NextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserPoolClients': [
                {
                    'ClientId': 'string',
                    'UserPoolId': 'string',
                    'ClientName': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server that lists user pool clients.

        
        

        - **UserPoolClients** *(list) --* 

          The user pool clients in the response that lists user pool clients.

          
          

          - *(dict) --* 

            The description of the user poool client.

            
            

            - **ClientId** *(string) --* 

              The ID of the client associated with the user pool.

              
            

            - **UserPoolId** *(string) --* 

              The user pool ID for the user pool where you want to describe the user pool client.

              
            

            - **ClientName** *(string) --* 

              The client name from the user pool client description.

              
        
      
        

        - **NextToken** *(string) --* 

          An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

          
    

  .. py:method:: list_user_pools(**kwargs)

    

    Lists the user pools associated with an AWS account.

    

    **Request Syntax** 
    ::

      response = client.list_user_pools(
          NextToken='string',
          MaxResults=123
      )
    :type NextToken: string
    :param NextToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    :type MaxResults: integer
    :param MaxResults: **[REQUIRED]** 

      The maximum number of results you want the request to return when listing the user pools.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserPools': [
                {
                    'Id': 'string',
                    'Name': 'string',
                    'LambdaConfig': {
                        'PreSignUp': 'string',
                        'CustomMessage': 'string',
                        'PostConfirmation': 'string',
                        'PreAuthentication': 'string',
                        'PostAuthentication': 'string',
                        'DefineAuthChallenge': 'string',
                        'CreateAuthChallenge': 'string',
                        'VerifyAuthChallengeResponse': 'string'
                    },
                    'Status': 'Enabled'|'Disabled',
                    'LastModifiedDate': datetime(2015, 1, 1),
                    'CreationDate': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response to list user pools.

        
        

        - **UserPools** *(list) --* 

          The user pools from the response to list users.

          
          

          - *(dict) --* 

            A user pool description.

            
            

            - **Id** *(string) --* 

              The ID in a user pool description.

              
            

            - **Name** *(string) --* 

              The name in a user pool description.

              
            

            - **LambdaConfig** *(dict) --* 

              The AWS Lambda configuration information in a user pool description.

              
              

              - **PreSignUp** *(string) --* 

                A pre-registration AWS Lambda trigger.

                
              

              - **CustomMessage** *(string) --* 

                A custom Message AWS Lambda trigger.

                
              

              - **PostConfirmation** *(string) --* 

                A post-confirmation AWS Lambda trigger.

                
              

              - **PreAuthentication** *(string) --* 

                A pre-authentication AWS Lambda trigger.

                
              

              - **PostAuthentication** *(string) --* 

                A post-authentication AWS Lambda trigger.

                
              

              - **DefineAuthChallenge** *(string) --* 

                Defines the authentication challenge.

                
              

              - **CreateAuthChallenge** *(string) --* 

                Creates an authentication challenge.

                
              

              - **VerifyAuthChallengeResponse** *(string) --* 

                Verifies the authentication challenge response.

                
          
            

            - **Status** *(string) --* 

              The user pool status in a user pool description.

              
            

            - **LastModifiedDate** *(datetime) --* 

              The last modified date in a user pool description.

              
            

            - **CreationDate** *(datetime) --* 

              The creation date in a user pool description.

              
        
      
        

        - **NextToken** *(string) --* 

          An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

          
    

  .. py:method:: list_users(**kwargs)

    

    Lists the users in the Amazon Cognito user pool.

    

    **Request Syntax** 
    ::

      response = client.list_users(
          UserPoolId='string',
          AttributesToGet=[
              'string',
          ],
          Limit=123,
          PaginationToken='string',
          Filter='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for which you want to list users.

      

    
    :type AttributesToGet: list
    :param AttributesToGet: 

      The attributes to get from the request to list users.

      

    
      - *(string) --* 

      
  
    :type Limit: integer
    :param Limit: 

      The limit of the request to list users.

      

    
    :type PaginationToken: string
    :param PaginationToken: 

      An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

      

    
    :type Filter: string
    :param Filter: 

      The filter for the list users request.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Users': [
                {
                    'Username': 'string',
                    'Attributes': [
                        {
                            'Name': 'string',
                            'Value': 'string'
                        },
                    ],
                    'UserCreateDate': datetime(2015, 1, 1),
                    'UserLastModifiedDate': datetime(2015, 1, 1),
                    'Enabled': True|False,
                    'UserStatus': 'UNCONFIRMED'|'CONFIRMED'|'ARCHIVED'|'COMPROMISED'|'UNKNOWN'|'RESET_REQUIRED'
                },
            ],
            'PaginationToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response from the request to list users.

        
        

        - **Users** *(list) --* 

          The users returned in the request to list users.

          
          

          - *(dict) --* 

            The user type.

            
            

            - **Username** *(string) --* 

              The user name of the user you wish to describe.

              
            

            - **Attributes** *(list) --* 

              A container with information about the user type attributes.

              
              

              - *(dict) --* 

                Specifies whether the attribute is standard or custom.

                
                

                - **Name** *(string) --* 

                  The name of the attribute.

                  
                

                - **Value** *(string) --* 

                  The value of the attribute.

                  
            
          
            

            - **UserCreateDate** *(datetime) --* 

              The creation date of the user.

              
            

            - **UserLastModifiedDate** *(datetime) --* 

              The last modified date of the user.

              
            

            - **Enabled** *(boolean) --* 

              Specifies whether the user is enabled.

              
            

            - **UserStatus** *(string) --* 

              The user status. Can be one of the following:

               

               
              * UNCONFIRMED - User has been created but not confirmed.
               
              * CONFIRMED - User has been confirmed.
               
              * ARCHIVED - User is no longer active.
               
              * COMPROMISED - User is disabled due to a potential security threat.
               
              * UNKNOWN - User status is not known.
               

              
        
      
        

        - **PaginationToken** *(string) --* 

          An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

          
    

  .. py:method:: resend_confirmation_code(**kwargs)

    

    Resends the confirmation (for confirmation of registration) to a specific user in the user pool.

    

    **Request Syntax** 
    ::

      response = client.resend_confirmation_code(
          ClientId='string',
          SecretHash='string',
          Username='string'
      )
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The ID of the client associated with the user pool.

      

    
    :type SecretHash: string
    :param SecretHash: 

      A keyed-hash message authentication code (HMAC) calculated using the secret key of a user pool client and username plus the client ID in the message.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user to whom you wish to resend a confirmation code.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CodeDeliveryDetails': {
                'Destination': 'string',
                'DeliveryMedium': 'SMS'|'EMAIL',
                'AttributeName': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response from the server when the Amazon Cognito service makes the request to resend a confirmation code.

        
        

        - **CodeDeliveryDetails** *(dict) --* 

          The type of code delivery details being returned from the server.

          
          

          - **Destination** *(string) --* 

            The destination for the code delivery details.

            
          

          - **DeliveryMedium** *(string) --* 

            The delivery medium (email message or phone number).

            
          

          - **AttributeName** *(string) --* 

            The name of the attribute in the code delivery details type.

            
      
    

  .. py:method:: respond_to_auth_challenge(**kwargs)

    

    Responds to the authentication challenge.

    

    **Request Syntax** 
    ::

      response = client.respond_to_auth_challenge(
          ClientId='string',
          ChallengeName='SMS_MFA'|'PASSWORD_VERIFIER'|'CUSTOM_CHALLENGE'|'DEVICE_SRP_AUTH'|'DEVICE_PASSWORD_VERIFIER'|'ADMIN_NO_SRP_AUTH',
          Session='string',
          ChallengeResponses={
              'string': 'string'
          }
      )
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The client ID.

      

    
    :type ChallengeName: string
    :param ChallengeName: **[REQUIRED]** 

      The name of the challenge.

      

    
    :type Session: string
    :param Session: 

      The session.

      

    
    :type ChallengeResponses: dict
    :param ChallengeResponses: 

      The responses to the authentication challenge.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChallengeName': 'SMS_MFA'|'PASSWORD_VERIFIER'|'CUSTOM_CHALLENGE'|'DEVICE_SRP_AUTH'|'DEVICE_PASSWORD_VERIFIER'|'ADMIN_NO_SRP_AUTH',
            'Session': 'string',
            'ChallengeParameters': {
                'string': 'string'
            },
            'AuthenticationResult': {
                'AccessToken': 'string',
                'ExpiresIn': 123,
                'TokenType': 'string',
                'RefreshToken': 'string',
                'IdToken': 'string',
                'NewDeviceMetadata': {
                    'DeviceKey': 'string',
                    'DeviceGroupKey': 'string'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to respond to the authentication challenge.

        
        

        - **ChallengeName** *(string) --* 

          The challenge name.

          
        

        - **Session** *(string) --* 

          The session.

          
        

        - **ChallengeParameters** *(dict) --* 

          The challenge parameters.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **AuthenticationResult** *(dict) --* 

          The result type of the authentication result.

          
          

          - **AccessToken** *(string) --* 

            The access token of the authentication result.

            
          

          - **ExpiresIn** *(integer) --* 

            The expiration period of the authentication result.

            
          

          - **TokenType** *(string) --* 

            The token type of the authentication result.

            
          

          - **RefreshToken** *(string) --* 

            The refresh token of the authentication result.

            
          

          - **IdToken** *(string) --* 

            The ID token of the authentication result.

            
          

          - **NewDeviceMetadata** *(dict) --* 

            The new device metadata from an authentication result.

            
            

            - **DeviceKey** *(string) --* 

              The device key.

              
            

            - **DeviceGroupKey** *(string) --* 

              The device group key.

              
        
      
    

  .. py:method:: set_user_settings(**kwargs)

    

    Sets the user settings like multi-factor authentication (MFA). If MFA is to be removed for a particular attribute pass the attribute with code delivery as null. If null list is passed, all MFA options are removed.

    

    **Request Syntax** 
    ::

      response = client.set_user_settings(
          AccessToken='string',
          MFAOptions=[
              {
                  'DeliveryMedium': 'SMS'|'EMAIL',
                  'AttributeName': 'string'
              },
          ]
      )
    :type AccessToken: string
    :param AccessToken: **[REQUIRED]** 

      The access token for the set user settings request.

      

    
    :type MFAOptions: list
    :param MFAOptions: **[REQUIRED]** 

      Specifies the options for MFA (e.g., email or phone number).

      

    
      - *(dict) --* 

        Specifies the different settings for multi-factor authentication (MFA).

        

      
        - **DeliveryMedium** *(string) --* 

          The delivery medium (email message or SMS message) to send the MFA code.

          

        
        - **AttributeName** *(string) --* 

          The attribute name of the MFA option type.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The response from the server for a set user settings request.

        
    

  .. py:method:: sign_up(**kwargs)

    

    Registers the user in the specified user pool and creates a user name, password, and user attributes.

    

    **Request Syntax** 
    ::

      response = client.sign_up(
          ClientId='string',
          SecretHash='string',
          Username='string',
          Password='string',
          UserAttributes=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ],
          ValidationData=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The ID of the client associated with the user pool.

      

    
    :type SecretHash: string
    :param SecretHash: 

      A keyed-hash message authentication code (HMAC) calculated using the secret key of a user pool client and username plus the client ID in the message.

      

    
    :type Username: string
    :param Username: **[REQUIRED]** 

      The user name of the user you wish to register.

      

    
    :type Password: string
    :param Password: **[REQUIRED]** 

      The password of the user you wish to register.

      

    
    :type UserAttributes: list
    :param UserAttributes: 

      An array of name-value pairs representing user attributes.

      

    
      - *(dict) --* 

        Specifies whether the attribute is standard or custom.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the attribute.

          

        
        - **Value** *(string) --* 

          The value of the attribute.

          

        
      
  
    :type ValidationData: list
    :param ValidationData: 

      The validation data in the request to register a user.

      

    
      - *(dict) --* 

        Specifies whether the attribute is standard or custom.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the attribute.

          

        
        - **Value** *(string) --* 

          The value of the attribute.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserConfirmed': True|False,
            'CodeDeliveryDetails': {
                'Destination': 'string',
                'DeliveryMedium': 'SMS'|'EMAIL',
                'AttributeName': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response from the server for a registration request.

        
        

        - **UserConfirmed** *(boolean) --* 

          A response from the server indicating that a user registration has been confirmed.

          
        

        - **CodeDeliveryDetails** *(dict) --* 

          The type of code delivery details being returned from the server.

          
          

          - **Destination** *(string) --* 

            The destination for the code delivery details.

            
          

          - **DeliveryMedium** *(string) --* 

            The delivery medium (email message or phone number).

            
          

          - **AttributeName** *(string) --* 

            The name of the attribute in the code delivery details type.

            
      
    

  .. py:method:: start_user_import_job(**kwargs)

    

    Starts the user import.

    

    **Request Syntax** 
    ::

      response = client.start_user_import_job(
          UserPoolId='string',
          JobId='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool that the users are being imported into.

      

    
    :type JobId: string
    :param JobId: **[REQUIRED]** 

      The job ID for the user import job.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserImportJob': {
                'JobName': 'string',
                'JobId': 'string',
                'UserPoolId': 'string',
                'PreSignedUrl': 'string',
                'CreationDate': datetime(2015, 1, 1),
                'StartDate': datetime(2015, 1, 1),
                'CompletionDate': datetime(2015, 1, 1),
                'Status': 'Created'|'Pending'|'InProgress'|'Stopping'|'Expired'|'Stopped'|'Failed'|'Succeeded',
                'CloudWatchLogsRoleArn': 'string',
                'ImportedUsers': 123,
                'SkippedUsers': 123,
                'FailedUsers': 123,
                'CompletionMessage': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to the request to start the user import job.

        
        

        - **UserImportJob** *(dict) --* 

          The job object that represents the user import job.

          
          

          - **JobName** *(string) --* 

            The job name for the user import job.

            
          

          - **JobId** *(string) --* 

            The job ID for the user import job.

            
          

          - **UserPoolId** *(string) --* 

            The user pool ID for the user pool that the users are being imported into.

            
          

          - **PreSignedUrl** *(string) --* 

            The pre-signed URL to be used to upload the .csv file.

            
          

          - **CreationDate** *(datetime) --* 

            The date when the user import job was created.

            
          

          - **StartDate** *(datetime) --* 

            The date when the user import job was started.

            
          

          - **CompletionDate** *(datetime) --* 

            The date when the user imoprt job was completed.

            
          

          - **Status** *(string) --* 

            The status of the user import job. One of the following:

             

             
            * Created - The job was created but not started.
             
            * Pending - A transition state. You have started the job, but it has not begun importing users yet.
             
            * InProgress - The job has started, and users are being imported.
             
            * Stopping - You have stopped the job, but the job has not stopped importing users yet.
             
            * Stopped - You have stopped the job, and the job has stopped importing users.
             
            * Succeeded - The job has completed successfully.
             
            * Failed - The job has stopped due to an error.
             
            * Expired - You created a job, but did not start the job within 24-48 hours. All data associated with the job was deleted, and the job cannot be started.
             

            
          

          - **CloudWatchLogsRoleArn** *(string) --* 

            The role ARN for the Amazon CloudWatch Logging role for the user import job. For more information, see "Creating the CloudWatch Logs IAM Role" in the Amazon Cognito Developer Guide.

            
          

          - **ImportedUsers** *(integer) --* 

            The number of users that were successfully imported.

            
          

          - **SkippedUsers** *(integer) --* 

            The number of users that were skipped.

            
          

          - **FailedUsers** *(integer) --* 

            The number of users that could not be imported.

            
          

          - **CompletionMessage** *(string) --* 

            The message returned when the user import job is completed.

            
      
    

  .. py:method:: stop_user_import_job(**kwargs)

    

    Stops the user import job.

    

    **Request Syntax** 
    ::

      response = client.stop_user_import_job(
          UserPoolId='string',
          JobId='string'
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool that the users are being imported into.

      

    
    :type JobId: string
    :param JobId: **[REQUIRED]** 

      The job ID for the user import job.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserImportJob': {
                'JobName': 'string',
                'JobId': 'string',
                'UserPoolId': 'string',
                'PreSignedUrl': 'string',
                'CreationDate': datetime(2015, 1, 1),
                'StartDate': datetime(2015, 1, 1),
                'CompletionDate': datetime(2015, 1, 1),
                'Status': 'Created'|'Pending'|'InProgress'|'Stopping'|'Expired'|'Stopped'|'Failed'|'Succeeded',
                'CloudWatchLogsRoleArn': 'string',
                'ImportedUsers': 123,
                'SkippedUsers': 123,
                'FailedUsers': 123,
                'CompletionMessage': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to the request to stop the user import job.

        
        

        - **UserImportJob** *(dict) --* 

          The job object that represents the user import job.

          
          

          - **JobName** *(string) --* 

            The job name for the user import job.

            
          

          - **JobId** *(string) --* 

            The job ID for the user import job.

            
          

          - **UserPoolId** *(string) --* 

            The user pool ID for the user pool that the users are being imported into.

            
          

          - **PreSignedUrl** *(string) --* 

            The pre-signed URL to be used to upload the .csv file.

            
          

          - **CreationDate** *(datetime) --* 

            The date when the user import job was created.

            
          

          - **StartDate** *(datetime) --* 

            The date when the user import job was started.

            
          

          - **CompletionDate** *(datetime) --* 

            The date when the user imoprt job was completed.

            
          

          - **Status** *(string) --* 

            The status of the user import job. One of the following:

             

             
            * Created - The job was created but not started.
             
            * Pending - A transition state. You have started the job, but it has not begun importing users yet.
             
            * InProgress - The job has started, and users are being imported.
             
            * Stopping - You have stopped the job, but the job has not stopped importing users yet.
             
            * Stopped - You have stopped the job, and the job has stopped importing users.
             
            * Succeeded - The job has completed successfully.
             
            * Failed - The job has stopped due to an error.
             
            * Expired - You created a job, but did not start the job within 24-48 hours. All data associated with the job was deleted, and the job cannot be started.
             

            
          

          - **CloudWatchLogsRoleArn** *(string) --* 

            The role ARN for the Amazon CloudWatch Logging role for the user import job. For more information, see "Creating the CloudWatch Logs IAM Role" in the Amazon Cognito Developer Guide.

            
          

          - **ImportedUsers** *(integer) --* 

            The number of users that were successfully imported.

            
          

          - **SkippedUsers** *(integer) --* 

            The number of users that were skipped.

            
          

          - **FailedUsers** *(integer) --* 

            The number of users that could not be imported.

            
          

          - **CompletionMessage** *(string) --* 

            The message returned when the user import job is completed.

            
      
    

  .. py:method:: update_device_status(**kwargs)

    

    Updates the device status.

    

    **Request Syntax** 
    ::

      response = client.update_device_status(
          AccessToken='string',
          DeviceKey='string',
          DeviceRememberedStatus='remembered'|'not_remembered'
      )
    :type AccessToken: string
    :param AccessToken: **[REQUIRED]** 

      The access token.

      

    
    :type DeviceKey: string
    :param DeviceKey: **[REQUIRED]** 

      The device key.

      

    
    :type DeviceRememberedStatus: string
    :param DeviceRememberedStatus: 

      The status of whether a device is remembered.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        The response to the request to update the device status.

        
    

  .. py:method:: update_user_attributes(**kwargs)

    

    Allows a user to update a specific attribute (one at a time).

    

    **Request Syntax** 
    ::

      response = client.update_user_attributes(
          UserAttributes=[
              {
                  'Name': 'string',
                  'Value': 'string'
              },
          ],
          AccessToken='string'
      )
    :type UserAttributes: list
    :param UserAttributes: **[REQUIRED]** 

      An array of name-value pairs representing user attributes.

      

    
      - *(dict) --* 

        Specifies whether the attribute is standard or custom.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The name of the attribute.

          

        
        - **Value** *(string) --* 

          The value of the attribute.

          

        
      
  
    :type AccessToken: string
    :param AccessToken: 

      The access token for the request to update user attributes.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'CodeDeliveryDetailsList': [
                {
                    'Destination': 'string',
                    'DeliveryMedium': 'SMS'|'EMAIL',
                    'AttributeName': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server for the request to update user attributes.

        
        

        - **CodeDeliveryDetailsList** *(list) --* 

          The code delivery details list from the server for the request to update user attributes.

          
          

          - *(dict) --* 

            The type of code delivery details being returned from the server.

            
            

            - **Destination** *(string) --* 

              The destination for the code delivery details.

              
            

            - **DeliveryMedium** *(string) --* 

              The delivery medium (email message or phone number).

              
            

            - **AttributeName** *(string) --* 

              The name of the attribute in the code delivery details type.

              
        
      
    

  .. py:method:: update_user_pool(**kwargs)

    

    Updates the specified user pool with the specified attributes.

    

    **Request Syntax** 
    ::

      response = client.update_user_pool(
          UserPoolId='string',
          Policies={
              'PasswordPolicy': {
                  'MinimumLength': 123,
                  'RequireUppercase': True|False,
                  'RequireLowercase': True|False,
                  'RequireNumbers': True|False,
                  'RequireSymbols': True|False
              }
          },
          LambdaConfig={
              'PreSignUp': 'string',
              'CustomMessage': 'string',
              'PostConfirmation': 'string',
              'PreAuthentication': 'string',
              'PostAuthentication': 'string',
              'DefineAuthChallenge': 'string',
              'CreateAuthChallenge': 'string',
              'VerifyAuthChallengeResponse': 'string'
          },
          AutoVerifiedAttributes=[
              'phone_number'|'email',
          ],
          SmsVerificationMessage='string',
          EmailVerificationMessage='string',
          EmailVerificationSubject='string',
          SmsAuthenticationMessage='string',
          MfaConfiguration='OFF'|'ON'|'OPTIONAL',
          DeviceConfiguration={
              'ChallengeRequiredOnNewDevice': True|False,
              'DeviceOnlyRememberedOnUserPrompt': True|False
          },
          EmailConfiguration={
              'SourceArn': 'string',
              'ReplyToEmailAddress': 'string'
          },
          SmsConfiguration={
              'SnsCallerArn': 'string',
              'ExternalId': 'string'
          }
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool you want to update.

      

    
    :type Policies: dict
    :param Policies: 

      A container with the policies you wish to update in a user pool.

      

    
      - **PasswordPolicy** *(dict) --* 

        A container with information about the user pool password policy.

        

      
        - **MinimumLength** *(integer) --* 

          The minimum length of the password policy that you have set. Cannot be less than 6.

          

        
        - **RequireUppercase** *(boolean) --* 

          In the password policy that you have set, refers to whether you have required users to use at least one uppercase letter in their password.

          

        
        - **RequireLowercase** *(boolean) --* 

          In the password policy that you have set, refers to whether you have required users to use at least one lowercase letter in their password.

          

        
        - **RequireNumbers** *(boolean) --* 

          In the password policy that you have set, refers to whether you have required users to use at least one number in their password.

          

        
        - **RequireSymbols** *(boolean) --* 

          In the password policy that you have set, refers to whether you have required users to use at least one symbol in their password.

          

        
      
    
    :type LambdaConfig: dict
    :param LambdaConfig: 

      The AWS Lambda configuration information from the request to update the user pool.

      

    
      - **PreSignUp** *(string) --* 

        A pre-registration AWS Lambda trigger.

        

      
      - **CustomMessage** *(string) --* 

        A custom Message AWS Lambda trigger.

        

      
      - **PostConfirmation** *(string) --* 

        A post-confirmation AWS Lambda trigger.

        

      
      - **PreAuthentication** *(string) --* 

        A pre-authentication AWS Lambda trigger.

        

      
      - **PostAuthentication** *(string) --* 

        A post-authentication AWS Lambda trigger.

        

      
      - **DefineAuthChallenge** *(string) --* 

        Defines the authentication challenge.

        

      
      - **CreateAuthChallenge** *(string) --* 

        Creates an authentication challenge.

        

      
      - **VerifyAuthChallengeResponse** *(string) --* 

        Verifies the authentication challenge response.

        

      
    
    :type AutoVerifiedAttributes: list
    :param AutoVerifiedAttributes: 

      The attributes that are automatically verified when the Amazon Cognito service makes a request to update user pools.

      

    
      - *(string) --* 

      
  
    :type SmsVerificationMessage: string
    :param SmsVerificationMessage: 

      A container with information about the SMS verification message.

      

    
    :type EmailVerificationMessage: string
    :param EmailVerificationMessage: 

      The contents of the email verification message.

      

    
    :type EmailVerificationSubject: string
    :param EmailVerificationSubject: 

      The subject of the email verfication message

      

    
    :type SmsAuthenticationMessage: string
    :param SmsAuthenticationMessage: 

      The contents of the SMS authentication message.

      

    
    :type MfaConfiguration: string
    :param MfaConfiguration: 

      Can be one of the following values:

       

       
      * ``OFF`` - MFA tokens are not required and cannot be specified during user registration.
       
      * ``ON`` - MFA tokens are required for all user registrations. You can only specify required when you are initially creating a user pool.
       
      * ``OPTIONAL`` - Users have the option when registering to create an MFA token.
       

      

    
    :type DeviceConfiguration: dict
    :param DeviceConfiguration: 

      Device configuration.

      

    
      - **ChallengeRequiredOnNewDevice** *(boolean) --* 

        Indicates whether a challenge is required on a new device. Only applicable to a new device.

        

      
      - **DeviceOnlyRememberedOnUserPrompt** *(boolean) --* 

        If true, a device is only remembered on user prompt.

        

      
    
    :type EmailConfiguration: dict
    :param EmailConfiguration: 

      Email configuration.

      

    
      - **SourceArn** *(string) --* 

        The Amazon Resource Name (ARN) of the email source.

        

      
      - **ReplyToEmailAddress** *(string) --* 

        The REPLY-TO email address.

        

      
    
    :type SmsConfiguration: dict
    :param SmsConfiguration: 

      SMS configuration.

      

    
      - **SnsCallerArn** *(string) --* 

        The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) caller.

        

      
      - **ExternalId** *(string) --* 

        The external ID.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server when you make a request to update the user pool.

        
    

  .. py:method:: update_user_pool_client(**kwargs)

    

    Allows the developer to update the specified user pool client and password policy.

    

    **Request Syntax** 
    ::

      response = client.update_user_pool_client(
          UserPoolId='string',
          ClientId='string',
          ClientName='string',
          RefreshTokenValidity=123,
          ReadAttributes=[
              'string',
          ],
          WriteAttributes=[
              'string',
          ],
          ExplicitAuthFlows=[
              'ADMIN_NO_SRP_AUTH'|'CUSTOM_AUTH_FLOW_ONLY',
          ]
      )
    :type UserPoolId: string
    :param UserPoolId: **[REQUIRED]** 

      The user pool ID for the user pool where you want to update the user pool client.

      

    
    :type ClientId: string
    :param ClientId: **[REQUIRED]** 

      The ID of the client associated with the user pool.

      

    
    :type ClientName: string
    :param ClientName: 

      The client name from the update user pool client request.

      

    
    :type RefreshTokenValidity: integer
    :param RefreshTokenValidity: 

      The validity of the refresh token.

      

    
    :type ReadAttributes: list
    :param ReadAttributes: 

      The read-only attributes of the user pool.

      

    
      - *(string) --* 

      
  
    :type WriteAttributes: list
    :param WriteAttributes: 

      The writeable attributes of the user pool.

      

    
      - *(string) --* 

      
  
    :type ExplicitAuthFlows: list
    :param ExplicitAuthFlows: 

      Explicit authentication flows.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserPoolClient': {
                'UserPoolId': 'string',
                'ClientName': 'string',
                'ClientId': 'string',
                'ClientSecret': 'string',
                'LastModifiedDate': datetime(2015, 1, 1),
                'CreationDate': datetime(2015, 1, 1),
                'RefreshTokenValidity': 123,
                'ReadAttributes': [
                    'string',
                ],
                'WriteAttributes': [
                    'string',
                ],
                'ExplicitAuthFlows': [
                    'ADMIN_NO_SRP_AUTH'|'CUSTOM_AUTH_FLOW_ONLY',
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response from the server to the request to update the user pool client.

        
        

        - **UserPoolClient** *(dict) --* 

          The user pool client value from the response from the server when an update user pool client request is made.

          
          

          - **UserPoolId** *(string) --* 

            The user pool ID for the user pool client.

            
          

          - **ClientName** *(string) --* 

            The client name from the user pool request of the client type.

            
          

          - **ClientId** *(string) --* 

            The ID of the client associated with the user pool.

            
          

          - **ClientSecret** *(string) --* 

            The client secret from the user pool request of the client type.

            
          

          - **LastModifiedDate** *(datetime) --* 

            The last modified date from the user pool request of the client type.

            
          

          - **CreationDate** *(datetime) --* 

            The creation date from the user pool request of the client type.

            
          

          - **RefreshTokenValidity** *(integer) --* 

            The validity of the refresh token.

            
          

          - **ReadAttributes** *(list) --* 

            The Read-only attributes.

            
            

            - *(string) --* 
        
          

          - **WriteAttributes** *(list) --* 

            The writeable attributes.

            
            

            - *(string) --* 
        
          

          - **ExplicitAuthFlows** *(list) --* 

            The explicit authentication flows.

            
            

            - *(string) --* 
        
      
    

  .. py:method:: verify_user_attribute(**kwargs)

    

    Verifies the specified user attributes in the user pool.

    

    **Request Syntax** 
    ::

      response = client.verify_user_attribute(
          AccessToken='string',
          AttributeName='string',
          Code='string'
      )
    :type AccessToken: string
    :param AccessToken: 

      Represents the access token of the request to verify user attributes.

      

    
    :type AttributeName: string
    :param AttributeName: **[REQUIRED]** 

      The attribute name in the request to verify user attributes.

      

    
    :type Code: string
    :param Code: **[REQUIRED]** 

      The verification code in the request to verify user attributes.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        A container representing the response from the server from the request to verify user attributes.

        
    