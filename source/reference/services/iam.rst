

.. _Letting IAM Users Change Their Own Passwords: http://docs.aws.amazon.com/IAM/latest/UserGuide/HowToPwdIAMUser.html
.. _Permissions and Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/PermissionsAndPolicies.html
.. _Versioning for Managed Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-versions.html
.. _Limitations on Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
.. _Managing Passwords: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingLogins.html
.. _Getting Credential Reports: http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html
.. _regex pattern: http://wikipedia.org/wiki/regex
.. _About SAML 2.0-based Federation: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_saml.html
.. _GetFederationToken: http://docs.aws.amazon.com/IAM/latest/APIReference/API_GetFederationToken.html
.. _DeleteLoadBalancerListeners: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/APIReference/API_DeleteLoadBalancerListeners.html
.. _Enabling SAML 2.0 Federated Users to Access the AWS Management Console: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_enable-console-saml.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
.. _RFC3548: http://www.ietf.org/rfc/rfc3548.txt
.. _Signature Version 4: http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html
.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Limitations on IAM Entities and Objects: http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_iam-limits.html
.. _How IAM Roles Differ from Resource-based Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_compare-resource-policies.html
.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Renaming Users and Groups: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_WorkingWithGroupsAndUsers.html
.. _Obtaining the Thumbprint for an OpenID Connect Provider: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-oidc-obtain-thumbprint.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Managing an IAM Password Policy: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingPasswordPolicies.html
.. _Set up AWS CodeCommit for SSH Connections: http://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-credentials-ssh.html
.. _Working with Roles: http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html
.. _Calling the API by Making HTTP Query Requests: http://docs.aws.amazon.com/IAM/latest/UserGuide/programming.html
.. _RFC 3986: https://tools.ietf.org/html/rfc3986
.. _Credential Reports: http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html
.. _Limitations on IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
.. _regex: http://wikipedia.org/wiki/regex
.. _AssumeRole: http://docs.aws.amazon.com/IAM/latest/APIReference/API_AssumeRole.html
.. _About Instance Profiles: http://docs.aws.amazon.com/IAM/latest/UserGuide/AboutInstanceProfiles.html
.. _Renaming an IAM User: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_manage.html#id_users_renaming
.. _Supported Platforms: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-supported-platforms.html
.. _Using Roles to Delegate Permissions and Federate Identities: http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html
.. _Renaming an IAM Group: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_manage_rename.html
.. _Using a Virtual MFA Device: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_VirtualMFA.html
.. _Using an Alias for Your AWS Account ID: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html
.. _Access Management: http://docs.aws.amazon.com/IAM/latest/UserGuide/access.html
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html
.. _OpenID Connect (OIDC): http://openid.net/connect/
.. _Renaming a Server Certificate: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs_manage.html#RenamingServerCerts
.. _Working with Server Certificates: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs.html
.. _Managing Keys and Certificates: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingCredentials.html
.. _Signing AWS API Requests: http://docs.aws.amazon.com/general/latest/gr/signing_aws_api_requests.html
.. _Making Query Requests: http://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UsingQueryAPI.html


***
IAM
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: IAM.Client

  A low-level client representing AWS Identity and Access Management (IAM)::

    
    import boto3
    
    client = boto3.client('iam')

  
  These are the available methods:
  
  *   :py:meth:`add_client_id_to_open_id_connect_provider`

  
  *   :py:meth:`add_role_to_instance_profile`

  
  *   :py:meth:`add_user_to_group`

  
  *   :py:meth:`attach_group_policy`

  
  *   :py:meth:`attach_role_policy`

  
  *   :py:meth:`attach_user_policy`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`change_password`

  
  *   :py:meth:`create_access_key`

  
  *   :py:meth:`create_account_alias`

  
  *   :py:meth:`create_group`

  
  *   :py:meth:`create_instance_profile`

  
  *   :py:meth:`create_login_profile`

  
  *   :py:meth:`create_open_id_connect_provider`

  
  *   :py:meth:`create_policy`

  
  *   :py:meth:`create_policy_version`

  
  *   :py:meth:`create_role`

  
  *   :py:meth:`create_saml_provider`

  
  *   :py:meth:`create_user`

  
  *   :py:meth:`create_virtual_mfa_device`

  
  *   :py:meth:`deactivate_mfa_device`

  
  *   :py:meth:`delete_access_key`

  
  *   :py:meth:`delete_account_alias`

  
  *   :py:meth:`delete_account_password_policy`

  
  *   :py:meth:`delete_group`

  
  *   :py:meth:`delete_group_policy`

  
  *   :py:meth:`delete_instance_profile`

  
  *   :py:meth:`delete_login_profile`

  
  *   :py:meth:`delete_open_id_connect_provider`

  
  *   :py:meth:`delete_policy`

  
  *   :py:meth:`delete_policy_version`

  
  *   :py:meth:`delete_role`

  
  *   :py:meth:`delete_role_policy`

  
  *   :py:meth:`delete_saml_provider`

  
  *   :py:meth:`delete_server_certificate`

  
  *   :py:meth:`delete_signing_certificate`

  
  *   :py:meth:`delete_ssh_public_key`

  
  *   :py:meth:`delete_user`

  
  *   :py:meth:`delete_user_policy`

  
  *   :py:meth:`delete_virtual_mfa_device`

  
  *   :py:meth:`detach_group_policy`

  
  *   :py:meth:`detach_role_policy`

  
  *   :py:meth:`detach_user_policy`

  
  *   :py:meth:`enable_mfa_device`

  
  *   :py:meth:`generate_credential_report`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_access_key_last_used`

  
  *   :py:meth:`get_account_authorization_details`

  
  *   :py:meth:`get_account_password_policy`

  
  *   :py:meth:`get_account_summary`

  
  *   :py:meth:`get_context_keys_for_custom_policy`

  
  *   :py:meth:`get_context_keys_for_principal_policy`

  
  *   :py:meth:`get_credential_report`

  
  *   :py:meth:`get_group`

  
  *   :py:meth:`get_group_policy`

  
  *   :py:meth:`get_instance_profile`

  
  *   :py:meth:`get_login_profile`

  
  *   :py:meth:`get_open_id_connect_provider`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_policy`

  
  *   :py:meth:`get_policy_version`

  
  *   :py:meth:`get_role`

  
  *   :py:meth:`get_role_policy`

  
  *   :py:meth:`get_saml_provider`

  
  *   :py:meth:`get_server_certificate`

  
  *   :py:meth:`get_ssh_public_key`

  
  *   :py:meth:`get_user`

  
  *   :py:meth:`get_user_policy`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_access_keys`

  
  *   :py:meth:`list_account_aliases`

  
  *   :py:meth:`list_attached_group_policies`

  
  *   :py:meth:`list_attached_role_policies`

  
  *   :py:meth:`list_attached_user_policies`

  
  *   :py:meth:`list_entities_for_policy`

  
  *   :py:meth:`list_group_policies`

  
  *   :py:meth:`list_groups`

  
  *   :py:meth:`list_groups_for_user`

  
  *   :py:meth:`list_instance_profiles`

  
  *   :py:meth:`list_instance_profiles_for_role`

  
  *   :py:meth:`list_mfa_devices`

  
  *   :py:meth:`list_open_id_connect_providers`

  
  *   :py:meth:`list_policies`

  
  *   :py:meth:`list_policy_versions`

  
  *   :py:meth:`list_role_policies`

  
  *   :py:meth:`list_roles`

  
  *   :py:meth:`list_saml_providers`

  
  *   :py:meth:`list_server_certificates`

  
  *   :py:meth:`list_signing_certificates`

  
  *   :py:meth:`list_ssh_public_keys`

  
  *   :py:meth:`list_user_policies`

  
  *   :py:meth:`list_users`

  
  *   :py:meth:`list_virtual_mfa_devices`

  
  *   :py:meth:`put_group_policy`

  
  *   :py:meth:`put_role_policy`

  
  *   :py:meth:`put_user_policy`

  
  *   :py:meth:`remove_client_id_from_open_id_connect_provider`

  
  *   :py:meth:`remove_role_from_instance_profile`

  
  *   :py:meth:`remove_user_from_group`

  
  *   :py:meth:`resync_mfa_device`

  
  *   :py:meth:`set_default_policy_version`

  
  *   :py:meth:`simulate_custom_policy`

  
  *   :py:meth:`simulate_principal_policy`

  
  *   :py:meth:`update_access_key`

  
  *   :py:meth:`update_account_password_policy`

  
  *   :py:meth:`update_assume_role_policy`

  
  *   :py:meth:`update_group`

  
  *   :py:meth:`update_login_profile`

  
  *   :py:meth:`update_open_id_connect_provider_thumbprint`

  
  *   :py:meth:`update_saml_provider`

  
  *   :py:meth:`update_server_certificate`

  
  *   :py:meth:`update_signing_certificate`

  
  *   :py:meth:`update_ssh_public_key`

  
  *   :py:meth:`update_user`

  
  *   :py:meth:`upload_server_certificate`

  
  *   :py:meth:`upload_signing_certificate`

  
  *   :py:meth:`upload_ssh_public_key`

  

  .. py:method:: add_client_id_to_open_id_connect_provider(**kwargs)

    

    Adds a new client ID (also known as audience) to the list of client IDs already registered for the specified IAM OpenID Connect (OIDC) provider resource.

     

    This action is idempotent; it does not fail or return an error if you add an existing client ID to the provider.

    

    **Request Syntax** 
    ::

      response = client.add_client_id_to_open_id_connect_provider(
          OpenIDConnectProviderArn='string',
          ClientID='string'
      )
    :type OpenIDConnectProviderArn: string
    :param OpenIDConnectProviderArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM OpenID Connect (OIDC) provider resource to add the client ID to. You can get a list of OIDC provider ARNs by using the  ListOpenIDConnectProviders action.

      

    
    :type ClientID: string
    :param ClientID: **[REQUIRED]** 

      The client ID (also known as audience) to add to the IAM OpenID Connect provider resource.

      

    
    
    :returns: None

  .. py:method:: add_role_to_instance_profile(**kwargs)

    

    Adds the specified IAM role to the specified instance profile.

     

    .. note::

       

      The caller of this API must be granted the ``PassRole`` permission on the IAM role by a permission policy.

       

     

    For more information about roles, go to `Working with Roles`_ . For more information about instance profiles, go to `About Instance Profiles`_ .

    

    **Request Syntax** 
    ::

      response = client.add_role_to_instance_profile(
          InstanceProfileName='string',
          RoleName='string'
      )
    :type InstanceProfileName: string
    :param InstanceProfileName: **[REQUIRED]** 

      The name of the instance profile to update.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to add.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: add_user_to_group(**kwargs)

    

    Adds the specified user to the specified group.

    

    **Request Syntax** 
    ::

      response = client.add_user_to_group(
          GroupName='string',
          UserName='string'
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group to update.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to add.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: attach_group_policy(**kwargs)

    

    Attaches the specified managed policy to the specified IAM group.

     

    You use this API to attach a managed policy to a group. To embed an inline policy in a group, use  PutGroupPolicy .

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.attach_group_policy(
          GroupName='string',
          PolicyArn='string'
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the group to attach the policy to.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to attach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: attach_role_policy(**kwargs)

    

    Attaches the specified managed policy to the specified IAM role.

     

    When you attach a managed policy to a role, the managed policy becomes part of the role's permission (access) policy. You cannot use a managed policy as the role's trust policy. The role's trust policy is created at the same time as the role, using  CreateRole . You can update a role's trust policy using  UpdateAssumeRolePolicy .

     

    Use this API to attach a *managed* policy to a role. To embed an inline policy in a role, use  PutRolePolicy . For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.attach_role_policy(
          RoleName='string',
          PolicyArn='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the role to attach the policy to.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to attach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: attach_user_policy(**kwargs)

    

    Attaches the specified managed policy to the specified user.

     

    You use this API to attach a *managed* policy to a user. To embed an inline policy in a user, use  PutUserPolicy .

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.attach_user_policy(
          UserName='string',
          PolicyArn='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the IAM user to attach the policy to.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to attach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

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

    

    Changes the password of the IAM user who is calling this action. The root account password is not affected by this action.

     

    To change the password for a different user, see  UpdateLoginProfile . For more information about modifying passwords, see `Managing Passwords`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.change_password(
          OldPassword='string',
          NewPassword='string'
      )
    :type OldPassword: string
    :param OldPassword: **[REQUIRED]** 

      The IAM user's current password.

      

    
    :type NewPassword: string
    :param NewPassword: **[REQUIRED]** 

      The new password. The new password must conform to the AWS account's password policy, if one exists.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of almost any printable ASCII character from the space (\u0020) through the end of the ASCII character range (\u00FF). You can also include the tab (\u0009), line feed (\u000A), and carriage return (\u000D) characters. Although any of these characters are valid in a password, note that many tools, such as the AWS Management Console, might restrict the ability to enter certain characters because they have special meaning within that tool.

      

    
    
    :returns: None

  .. py:method:: create_access_key(**kwargs)

    

    Creates a new AWS secret access key and corresponding AWS access key ID for the specified user. The default status for new keys is ``Active`` .

     

    If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    For information about limits on the number of keys you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. warning::

       

      To ensure the security of your AWS account, the secret access key is accessible only during key and user creation. You must save the key (for example, in a text file) if you want to be able to access it again. If a secret key is lost, you can delete the access keys for the associated user and then create new keys.

       

    

    **Request Syntax** 
    ::

      response = client.create_access_key(
          UserName='string'
      )
    :type UserName: string
    :param UserName: 

      The name of the IAM user that the new key will belong to.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AccessKey': {
                'UserName': 'string',
                'AccessKeyId': 'string',
                'Status': 'Active'|'Inactive',
                'SecretAccessKey': 'string',
                'CreateDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreateAccessKey request. 

        
        

        - **AccessKey** *(dict) --* 

          A structure with details about the access key.

          
          

          - **UserName** *(string) --* 

            The name of the IAM user that the access key is associated with.

            
          

          - **AccessKeyId** *(string) --* 

            The ID for this access key.

            
          

          - **Status** *(string) --* 

            The status of the access key. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not. 

            
          

          - **SecretAccessKey** *(string) --* 

            The secret key used to sign requests.

            
          

          - **CreateDate** *(datetime) --* 

            The date when the access key was created.

            
      
    

  .. py:method:: create_account_alias(**kwargs)

    

    Creates an alias for your AWS account. For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_account_alias(
          AccountAlias='string'
      )
    :type AccountAlias: string
    :param AccountAlias: **[REQUIRED]** 

      The account alias to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of lowercase letters, digits, and dashes. You cannot start or finish with a dash, nor can you have two dashes in a row.

      

    
    
    :returns: None

  .. py:method:: create_group(**kwargs)

    

    Creates a new group.

     

    For information about the number of groups you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_group(
          Path='string',
          GroupName='string'
      )
    :type Path: string
    :param Path: 

      The path to the group. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group to create. Do not include the path in this value.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-. The group name must be unique within the account. Group names are not distinguished by case. For example, you cannot create groups named both "ADMINS" and "admins".

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Group': {
                'Path': 'string',
                'GroupName': 'string',
                'GroupId': 'string',
                'Arn': 'string',
                'CreateDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreateGroup request. 

        
        

        - **Group** *(dict) --* 

          A structure containing details about the new group.

          
          

          - **Path** *(string) --* 

            The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **GroupName** *(string) --* 

            The friendly name that identifies the group.

            
          

          - **GroupId** *(string) --* 

            The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the group was created.

            
      
    

  .. py:method:: create_instance_profile(**kwargs)

    

    Creates a new instance profile. For information about instance profiles, go to `About Instance Profiles`_ .

     

    For information about the number of instance profiles you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_instance_profile(
          InstanceProfileName='string',
          Path='string'
      )
    :type InstanceProfileName: string
    :param InstanceProfileName: **[REQUIRED]** 

      The name of the instance profile to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Path: string
    :param Path: 

      The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'InstanceProfile': {
                'Path': 'string',
                'InstanceProfileName': 'string',
                'InstanceProfileId': 'string',
                'Arn': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'Roles': [
                    {
                        'Path': 'string',
                        'RoleName': 'string',
                        'RoleId': 'string',
                        'Arn': 'string',
                        'CreateDate': datetime(2015, 1, 1),
                        'AssumeRolePolicyDocument': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreateInstanceProfile request. 

        
        

        - **InstanceProfile** *(dict) --* 

          A structure containing details about the new instance profile.

          
          

          - **Path** *(string) --* 

            The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **InstanceProfileName** *(string) --* 

            The name identifying the instance profile.

            
          

          - **InstanceProfileId** *(string) --* 

            The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **CreateDate** *(datetime) --* 

            The date when the instance profile was created.

            
          

          - **Roles** *(list) --* 

            The role associated with the instance profile.

            
            

            - *(dict) --* 

              Contains information about an IAM role.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateRole   
               
              *  GetRole   
               
              *  ListRoles   
               

              
              

              - **Path** *(string) --* 

                The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                
              

              - **RoleName** *(string) --* 

                The friendly name that identifies the role.

                
              

              - **RoleId** *(string) --* 

                The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                
              

              - **Arn** *(string) --* 

                The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                
              

              - **CreateDate** *(datetime) --* 

                The date and time, in `ISO 8601 date-time format`_ , when the role was created.

                
              

              - **AssumeRolePolicyDocument** *(string) --* 

                The policy that grants an entity permission to assume the role.

                
          
        
      
    

  .. py:method:: create_login_profile(**kwargs)

    

    Creates a password for the specified user, giving the user the ability to access AWS services through the AWS Management Console. For more information about managing passwords, see `Managing Passwords`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_login_profile(
          UserName='string',
          Password='string',
          PasswordResetRequired=True|False
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the IAM user to create a password for. The user must already exist.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Password: string
    :param Password: **[REQUIRED]** 

      The new password for the user.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of almost any printable ASCII character from the space (\u0020) through the end of the ASCII character range (\u00FF). You can also include the tab (\u0009), line feed (\u000A), and carriage return (\u000D) characters. Although any of these characters are valid in a password, note that many tools, such as the AWS Management Console, might restrict the ability to enter certain characters because they have special meaning within that tool.

      

    
    :type PasswordResetRequired: boolean
    :param PasswordResetRequired: 

      Specifies whether the user is required to set a new password on next sign-in.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LoginProfile': {
                'UserName': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'PasswordResetRequired': True|False
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreateLoginProfile request. 

        
        

        - **LoginProfile** *(dict) --* 

          A structure containing the user name and password create date.

          
          

          - **UserName** *(string) --* 

            The name of the user, which can be used for signing in to the AWS Management Console.

            
          

          - **CreateDate** *(datetime) --* 

            The date when the password for the user was created.

            
          

          - **PasswordResetRequired** *(boolean) --* 

            Specifies whether the user is required to set a new password on next sign-in.

            
      
    

  .. py:method:: create_open_id_connect_provider(**kwargs)

    

    Creates an IAM entity to describe an identity provider (IdP) that supports `OpenID Connect (OIDC)`_ .

     

    The OIDC provider that you create with this operation can be used as a principal in a role's trust policy to establish a trust relationship between AWS and the OIDC provider.

     

    When you create the IAM OIDC provider, you specify the URL of the OIDC identity provider (IdP) to trust, a list of client IDs (also known as audiences) that identify the application or applications that are allowed to authenticate using the OIDC provider, and a list of thumbprints of the server certificate(s) that the IdP uses. You get all of this information from the OIDC IdP that you want to use for access to AWS.

     

    .. note::

       

      Because trust for the OIDC provider is ultimately derived from the IAM provider that this action creates, it is a best practice to limit access to the  CreateOpenIDConnectProvider action to highly-privileged users.

       

    

    **Request Syntax** 
    ::

      response = client.create_open_id_connect_provider(
          Url='string',
          ClientIDList=[
              'string',
          ],
          ThumbprintList=[
              'string',
          ]
      )
    :type Url: string
    :param Url: **[REQUIRED]** 

      The URL of the identity provider. The URL must begin with "https://" and should correspond to the ``iss`` claim in the provider's OpenID Connect ID tokens. Per the OIDC standard, path components are allowed but query parameters are not. Typically the URL consists of only a host name, like "https://server.example.org" or "https://example.com".

       

      You cannot register the same provider multiple times in a single AWS account. If you try to submit a URL that has already been used for an OpenID Connect provider in the AWS account, you will get an error.

      

    
    :type ClientIDList: list
    :param ClientIDList: 

      A list of client IDs (also known as audiences). When a mobile or web app registers with an OpenID Connect provider, they establish a value that identifies the application. (This is the value that's sent as the ``client_id`` parameter on OAuth requests.)

       

      You can register multiple client IDs with the same provider. For example, you might have multiple applications that use the same OIDC provider. You cannot register more than 100 client IDs with a single IAM OIDC provider.

       

      There is no defined format for a client ID. The ``CreateOpenIDConnectProviderRequest`` action accepts client IDs up to 255 characters long.

      

    
      - *(string) --* 

      
  
    :type ThumbprintList: list
    :param ThumbprintList: **[REQUIRED]** 

      A list of server certificate thumbprints for the OpenID Connect (OIDC) identity provider's server certificate(s). Typically this list includes only one entry. However, IAM lets you have up to five thumbprints for an OIDC provider. This lets you maintain multiple thumbprints if the identity provider is rotating certificates.

       

      The server certificate thumbprint is the hex-encoded SHA-1 hash value of the X.509 certificate used by the domain where the OpenID Connect provider makes its keys available. It is always a 40-character string.

       

      You must provide at least one thumbprint when creating an IAM OIDC provider. For example, if the OIDC provider is ``server.example.com`` and the provider stores its keys at "https://keys.server.example.com/openid-connect", the thumbprint string would be the hex-encoded SHA-1 hash value of the certificate used by https://keys.server.example.com.

       

      For more information about obtaining the OIDC provider's thumbprint, see `Obtaining the Thumbprint for an OpenID Connect Provider`_ in the *IAM User Guide* .

      

    
      - *(string) --* 

        Contains a thumbprint for an identity provider's server certificate.

         

        The identity provider's server certificate thumbprint is the hex-encoded SHA-1 hash value of the self-signed X.509 certificate used by the domain where the OpenID Connect provider makes its keys available. It is always a 40-character string.

        

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OpenIDConnectProviderArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreateOpenIDConnectProvider request. 

        
        

        - **OpenIDConnectProviderArn** *(string) --* 

          The Amazon Resource Name (ARN) of the new IAM OpenID Connect provider that is created. For more information, see  OpenIDConnectProviderListEntry . 

          
    

  .. py:method:: create_policy(**kwargs)

    

    Creates a new managed policy for your AWS account.

     

    This operation creates a policy version with a version identifier of ``v1`` and sets v1 as the policy's default version. For more information about policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

     

    For more information about managed policies in general, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_policy(
          PolicyName='string',
          Path='string',
          PolicyDocument='string',
          Description='string'
      )
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The friendly name of the policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Path: string
    :param Path: 

      The path for the policy.

       

      For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The JSON policy document that you want to use as the content for the new policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type Description: string
    :param Description: 

      A friendly description of the policy.

       

      Typically used to store information about the permissions defined in the policy. For example, "Grants access to production DynamoDB tables."

       

      The policy description is immutable. After a value is assigned, it cannot be changed.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Policy': {
                'PolicyName': 'string',
                'PolicyId': 'string',
                'Arn': 'string',
                'Path': 'string',
                'DefaultVersionId': 'string',
                'AttachmentCount': 123,
                'IsAttachable': True|False,
                'Description': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'UpdateDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreatePolicy request. 

        
        

        - **Policy** *(dict) --* 

          A structure containing details about the new policy.

          
          

          - **PolicyName** *(string) --* 

            The friendly name (not ARN) identifying the policy.

            
          

          - **PolicyId** *(string) --* 

            The stable and unique string identifying the policy.

             

            For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

             

            For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

            
          

          - **Path** *(string) --* 

            The path to the policy.

             

            For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

            
          

          - **DefaultVersionId** *(string) --* 

            The identifier for the version of the policy that is set as the default version.

            
          

          - **AttachmentCount** *(integer) --* 

            The number of entities (users, groups, and roles) that the policy is attached to.

            
          

          - **IsAttachable** *(boolean) --* 

            Specifies whether the policy can be attached to an IAM user, group, or role.

            
          

          - **Description** *(string) --* 

            A friendly description of the policy.

             

            This element is included in the response to the  GetPolicy operation. It is not included in the response to the  ListPolicies operation. 

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the policy was created.

            
          

          - **UpdateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the policy was last updated.

             

            When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created.

            
      
    

  .. py:method:: create_policy_version(**kwargs)

    

    Creates a new version of the specified managed policy. To update a managed policy, you create a new policy version. A managed policy can have up to five versions. If the policy has five versions, you must delete an existing version using  DeletePolicyVersion before you create a new version.

     

    Optionally, you can set the new version as the policy's default version. The default version is the version that is in effect for the IAM users, groups, and roles to which the policy is attached.

     

    For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_policy_version(
          PolicyArn='string',
          PolicyDocument='string',
          SetAsDefault=True|False
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy to which you want to add a new version.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The JSON policy document that you want to use as the content for this new version of the policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type SetAsDefault: boolean
    :param SetAsDefault: 

      Specifies whether to set this version as the policy's default version.

       

      When this parameter is ``true`` , the new policy version becomes the operative version; that is, the version that is in effect for the IAM users, groups, and roles that the policy is attached to.

       

      For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyVersion': {
                'Document': 'string',
                'VersionId': 'string',
                'IsDefaultVersion': True|False,
                'CreateDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreatePolicyVersion request. 

        
        

        - **PolicyVersion** *(dict) --* 

          A structure containing details about the new policy version.

          
          

          - **Document** *(string) --* 

            The policy document.

             

            The policy document is returned in the response to the  GetPolicyVersion and  GetAccountAuthorizationDetails operations. It is not returned in the response to the  CreatePolicyVersion or  ListPolicyVersions operations. 

            
          

          - **VersionId** *(string) --* 

            The identifier for the policy version.

             

            Policy version identifiers always begin with ``v`` (always lowercase). When a policy is created, the first policy version is ``v1`` . 

            
          

          - **IsDefaultVersion** *(boolean) --* 

            Specifies whether the policy version is set as the policy's default version.

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the policy version was created.

            
      
    

  .. py:method:: create_role(**kwargs)

    

    Creates a new role for your AWS account. For more information about roles, go to `Working with Roles`_ . For information about limitations on role names and the number of roles you can create, go to `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_role(
          Path='string',
          RoleName='string',
          AssumeRolePolicyDocument='string'
      )
    :type Path: string
    :param Path: 

      The path to the role. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-. Role names are not distinguished by case. For example, you cannot create roles named both "PRODROLE" and "prodrole".

      

    
    :type AssumeRolePolicyDocument: string
    :param AssumeRolePolicyDocument: **[REQUIRED]** 

      The trust relationship policy document that grants an entity permission to assume the role.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Role': {
                'Path': 'string',
                'RoleName': 'string',
                'RoleId': 'string',
                'Arn': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'AssumeRolePolicyDocument': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreateRole request. 

        
        

        - **Role** *(dict) --* 

          A structure containing details about the new role.

          
          

          - **Path** *(string) --* 

            The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **RoleName** *(string) --* 

            The friendly name that identifies the role.

            
          

          - **RoleId** *(string) --* 

            The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the role was created.

            
          

          - **AssumeRolePolicyDocument** *(string) --* 

            The policy that grants an entity permission to assume the role.

            
      
    

  .. py:method:: create_saml_provider(**kwargs)

    

    Creates an IAM resource that describes an identity provider (IdP) that supports SAML 2.0.

     

    The SAML provider resource that you create with this operation can be used as a principal in an IAM role's trust policy to enable federated users who sign-in using the SAML IdP to assume the role. You can create an IAM role that supports Web-based single sign-on (SSO) to the AWS Management Console or one that supports API access to AWS.

     

    When you create the SAML provider resource, you upload an a SAML metadata document that you get from your IdP and that includes the issuer's name, expiration information, and keys that can be used to validate the SAML authentication response (assertions) that the IdP sends. You must generate the metadata document using the identity management software that is used as your organization's IdP.

     

    .. note::

       

      This operation requires `Signature Version 4`_ .

       

     

    For more information, see `Enabling SAML 2.0 Federated Users to Access the AWS Management Console`_ and `About SAML 2.0-based Federation`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_saml_provider(
          SAMLMetadataDocument='string',
          Name='string'
      )
    :type SAMLMetadataDocument: string
    :param SAMLMetadataDocument: **[REQUIRED]** 

      An XML document generated by an identity provider (IdP) that supports SAML 2.0. The document includes the issuer's name, expiration information, and keys that can be used to validate the SAML authentication response (assertions) that are received from the IdP. You must generate the metadata document using the identity management software that is used as your organization's IdP.

       

      For more information, see `About SAML 2.0-based Federation`_ in the *IAM User Guide*  

      

    
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the provider to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SAMLProviderArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreateSAMLProvider request. 

        
        

        - **SAMLProviderArn** *(string) --* 

          The Amazon Resource Name (ARN) of the new SAML provider resource in IAM.

          
    

  .. py:method:: create_user(**kwargs)

    

    Creates a new IAM user for your AWS account.

     

    For information about limitations on the number of IAM users you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_user(
          Path='string',
          UserName='string'
      )
    :type Path: string
    :param Path: 

      The path for the user name. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-. User names are not distinguished by case. For example, you cannot create users named both "TESTUSER" and "testuser".

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'User': {
                'Path': 'string',
                'UserName': 'string',
                'UserId': 'string',
                'Arn': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'PasswordLastUsed': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreateUser request. 

        
        

        - **User** *(dict) --* 

          A structure with details about the new IAM user.

          
          

          - **Path** *(string) --* 

            The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

            
          

          - **UserName** *(string) --* 

            The friendly name identifying the user.

            
          

          - **UserId** *(string) --* 

            The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the user was created.

            
          

          - **PasswordLastUsed** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

             

             
            * The user does not have a password 
             
            * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
             
            * there is no sign-in data associated with the user 
             

             

            This value is returned only in the  GetUser and  ListUsers actions. 

            
      
    

  .. py:method:: create_virtual_mfa_device(**kwargs)

    

    Creates a new virtual MFA device for the AWS account. After creating the virtual MFA, use  EnableMFADevice to attach the MFA device to an IAM user. For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device`_ in the *IAM User Guide* .

     

    For information about limits on the number of MFA devices you can create, see `Limitations on Entities`_ in the *IAM User Guide* .

     

    .. warning::

       

      The seed information contained in the QR code and the Base32 string should be treated like any other secret access information, such as your AWS access keys or your passwords. After you provision your virtual device, you should ensure that the information is destroyed following secure procedures.

       

    

    **Request Syntax** 
    ::

      response = client.create_virtual_mfa_device(
          Path='string',
          VirtualMFADeviceName='string'
      )
    :type Path: string
    :param Path: 

      The path for the virtual MFA device. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type VirtualMFADeviceName: string
    :param VirtualMFADeviceName: **[REQUIRED]** 

      The name of the virtual MFA device. Use with path to uniquely identify a virtual MFA device.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VirtualMFADevice': {
                'SerialNumber': 'string',
                'Base32StringSeed': b'bytes',
                'QRCodePNG': b'bytes',
                'User': {
                    'Path': 'string',
                    'UserName': 'string',
                    'UserId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'PasswordLastUsed': datetime(2015, 1, 1)
                },
                'EnableDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  CreateVirtualMFADevice request. 

        
        

        - **VirtualMFADevice** *(dict) --* 

          A structure containing details about the new virtual MFA device.

          
          

          - **SerialNumber** *(string) --* 

            The serial number associated with ``VirtualMFADevice`` .

            
          

          - **Base32StringSeed** *(bytes) --* 

            The Base32 seed defined as specified in `RFC3548`_ . The ``Base32StringSeed`` is Base64-encoded. 

            
          

          - **QRCodePNG** *(bytes) --* 

            A QR code PNG image that encodes ``otpauth://totp/$virtualMFADeviceName@$AccountName?secret=$Base32String`` where ``$virtualMFADeviceName`` is one of the create call arguments, ``AccountName`` is the user name if set (otherwise, the account ID otherwise), and ``Base32String`` is the seed in Base32 format. The ``Base32String`` value is Base64-encoded. 

            
          

          - **User** *(dict) --* 

            Contains information about an IAM user entity.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateUser   
             
            *  GetUser   
             
            *  ListUsers   
             

            
            

            - **Path** *(string) --* 

              The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **UserName** *(string) --* 

              The friendly name identifying the user.

              
            

            - **UserId** *(string) --* 

              The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user was created.

              
            

            - **PasswordLastUsed** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

               

               
              * The user does not have a password 
               
              * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
               
              * there is no sign-in data associated with the user 
               

               

              This value is returned only in the  GetUser and  ListUsers actions. 

              
        
          

          - **EnableDate** *(datetime) --* 

            The date and time on which the virtual MFA device was enabled.

            
      
    

  .. py:method:: deactivate_mfa_device(**kwargs)

    

    Deactivates the specified MFA device and removes it from association with the user name for which it was originally enabled.

     

    For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.deactivate_mfa_device(
          UserName='string',
          SerialNumber='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user whose MFA device you want to deactivate.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type SerialNumber: string
    :param SerialNumber: **[REQUIRED]** 

      The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =/:,.@-

      

    
    
    :returns: None

  .. py:method:: delete_access_key(**kwargs)

    

    Deletes the access key pair associated with the specified IAM user.

     

    If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

    

    **Request Syntax** 
    ::

      response = client.delete_access_key(
          UserName='string',
          AccessKeyId='string'
      )
    :type UserName: string
    :param UserName: 

      The name of the user whose access key pair you want to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type AccessKeyId: string
    :param AccessKeyId: **[REQUIRED]** 

      The access key ID for the access key ID and secret access key you want to delete.

       

      The `regex pattern`_ for this parameter is a string of characters that can consist of any upper or lowercased letter or digit.

      

    
    
    :returns: None

  .. py:method:: delete_account_alias(**kwargs)

    

    Deletes the specified AWS account alias. For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.delete_account_alias(
          AccountAlias='string'
      )
    :type AccountAlias: string
    :param AccountAlias: **[REQUIRED]** 

      The name of the account alias to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of lowercase letters, digits, and dashes. You cannot start or finish with a dash, nor can you have two dashes in a row.

      

    
    
    :returns: None

  .. py:method:: delete_account_password_policy()

    

    Deletes the password policy for the AWS account. There are no parameters.

    

    **Request Syntax** 

    ::

      response = client.delete_account_password_policy()
    :returns: None

  .. py:method:: delete_group(**kwargs)

    

    Deletes the specified IAM group. The group must not contain any users or have any attached policies.

    

    **Request Syntax** 
    ::

      response = client.delete_group(
          GroupName='string'
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the IAM group to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete_group_policy(**kwargs)

    

    Deletes the specified inline policy that is embedded in the specified IAM group.

     

    A group can also have managed policies attached to it. To detach a managed policy from a group, use  DetachGroupPolicy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.delete_group_policy(
          GroupName='string',
          PolicyName='string'
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name (friendly name, not ARN) identifying the group that the policy is embedded in.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name identifying the policy document to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete_instance_profile(**kwargs)

    

    Deletes the specified instance profile. The instance profile must not have an associated role.

     

    .. warning::

       

      Make sure you do not have any Amazon EC2 instances running with the instance profile you are about to delete. Deleting a role or instance profile that is associated with a running instance will break any applications running on the instance.

       

     

    For more information about instance profiles, go to `About Instance Profiles`_ .

    

    **Request Syntax** 
    ::

      response = client.delete_instance_profile(
          InstanceProfileName='string'
      )
    :type InstanceProfileName: string
    :param InstanceProfileName: **[REQUIRED]** 

      The name of the instance profile to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete_login_profile(**kwargs)

    

    Deletes the password for the specified IAM user, which terminates the user's ability to access AWS services through the AWS Management Console.

     

    .. warning::

       

      Deleting a user's password does not prevent a user from accessing AWS through the command line interface or the API. To prevent all user access you must also either make any access keys inactive or delete them. For more information about making keys inactive or deleting them, see  UpdateAccessKey and  DeleteAccessKey . 

       

    

    **Request Syntax** 
    ::

      response = client.delete_login_profile(
          UserName='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user whose password you want to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete_open_id_connect_provider(**kwargs)

    

    Deletes an OpenID Connect identity provider (IdP) resource object in IAM.

     

    Deleting an IAM OIDC provider resource does not update any roles that reference the provider as a principal in their trust policies. Any attempt to assume a role that references a deleted provider fails.

     

    This action is idempotent; it does not fail or return an error if you call the action for a provider that does not exist.

    

    **Request Syntax** 
    ::

      response = client.delete_open_id_connect_provider(
          OpenIDConnectProviderArn='string'
      )
    :type OpenIDConnectProviderArn: string
    :param OpenIDConnectProviderArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM OpenID Connect provider resource object to delete. You can get a list of OpenID Connect provider resource ARNs by using the  ListOpenIDConnectProviders action.

      

    
    
    :returns: None

  .. py:method:: delete_policy(**kwargs)

    

    Deletes the specified managed policy.

     

    Before you can delete a managed policy, you must first detach the policy from all users, groups, and roles that it is attached to, and you must delete all of the policy's versions. The following steps describe the process for deleting a managed policy:

     

     
    * Detach the policy from all users, groups, and roles that the policy is attached to, using the  DetachUserPolicy ,  DetachGroupPolicy , or  DetachRolePolicy APIs. To list all the users, groups, and roles that a policy is attached to, use  ListEntitiesForPolicy . 
     
    * Delete all versions of the policy using  DeletePolicyVersion . To list the policy's versions, use  ListPolicyVersions . You cannot use  DeletePolicyVersion to delete the version that is marked as the default version. You delete the policy's default version in the next step of the process. 
     
    * Delete the policy (this automatically deletes the policy's default version) using this API. 
     

     

    For information about managed policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.delete_policy(
          PolicyArn='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to delete.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: delete_policy_version(**kwargs)

    

    Deletes the specified version from the specified managed policy.

     

    You cannot delete the default version from a policy using this API. To delete the default version from a policy, use  DeletePolicy . To find out which version of a policy is marked as the default version, use  ListPolicyVersions .

     

    For information about versions for managed policies, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.delete_policy_version(
          PolicyArn='string',
          VersionId='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy from which you want to delete a version.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type VersionId: string
    :param VersionId: **[REQUIRED]** 

      The policy version to delete.

       

      The `regex pattern`_ for this parameter is a string of characters that consists of the lowercase letter 'v' followed by one or two digits, and optionally followed by a period '.' and a string of letters and digits.

       

      For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

      

    
    
    :returns: None

  .. py:method:: delete_role(**kwargs)

    

    Deletes the specified role. The role must not have any policies attached. For more information about roles, go to `Working with Roles`_ .

     

    .. warning::

       

      Make sure you do not have any Amazon EC2 instances running with the role you are about to delete. Deleting a role or instance profile that is associated with a running instance will break any applications running on the instance.

       

    

    **Request Syntax** 
    ::

      response = client.delete_role(
          RoleName='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete_role_policy(**kwargs)

    

    Deletes the specified inline policy that is embedded in the specified IAM role.

     

    A role can also have managed policies attached to it. To detach a managed policy from a role, use  DetachRolePolicy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.delete_role_policy(
          RoleName='string',
          PolicyName='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name (friendly name, not ARN) identifying the role that the policy is embedded in.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the inline policy to delete from the specified IAM role.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete_saml_provider(**kwargs)

    

    Deletes a SAML provider resource in IAM.

     

    Deleting the provider resource from IAM does not update any roles that reference the SAML provider resource's ARN as a principal in their trust policies. Any attempt to assume a role that references a non-existent provider resource ARN fails.

     

    .. note::

       

      This operation requires `Signature Version 4`_ .

       

    

    **Request Syntax** 
    ::

      response = client.delete_saml_provider(
          SAMLProviderArn='string'
      )
    :type SAMLProviderArn: string
    :param SAMLProviderArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the SAML provider to delete.

      

    
    
    :returns: None

  .. py:method:: delete_server_certificate(**kwargs)

    

    Deletes the specified server certificate.

     

    For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

     

    .. warning::

       

      If you are using a server certificate with Elastic Load Balancing, deleting the certificate could have implications for your application. If Elastic Load Balancing doesn't detect the deletion of bound certificates, it may continue to use the certificates. This could cause Elastic Load Balancing to stop accepting traffic. We recommend that you remove the reference to the certificate from Elastic Load Balancing before using this command to delete the certificate. For more information, go to `DeleteLoadBalancerListeners`_ in the *Elastic Load Balancing API Reference* .

       

    

    **Request Syntax** 
    ::

      response = client.delete_server_certificate(
          ServerCertificateName='string'
      )
    :type ServerCertificateName: string
    :param ServerCertificateName: **[REQUIRED]** 

      The name of the server certificate you want to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete_signing_certificate(**kwargs)

    

    Deletes a signing certificate associated with the specified IAM user.

     

    If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated IAM users.

    

    **Request Syntax** 
    ::

      response = client.delete_signing_certificate(
          UserName='string',
          CertificateId='string'
      )
    :type UserName: string
    :param UserName: 

      The name of the user the signing certificate belongs to.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type CertificateId: string
    :param CertificateId: **[REQUIRED]** 

      The ID of the signing certificate to delete.

       

      The format of this parameter, as described by its `regex`_ pattern, is a string of characters that can be upper- or lower-cased letters or digits.

      

    
    
    :returns: None

  .. py:method:: delete_ssh_public_key(**kwargs)

    

    Deletes the specified SSH public key.

     

    The SSH public key deleted by this action is used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .

    

    **Request Syntax** 
    ::

      response = client.delete_ssh_public_key(
          UserName='string',
          SSHPublicKeyId='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the IAM user associated with the SSH public key.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type SSHPublicKeyId: string
    :param SSHPublicKeyId: **[REQUIRED]** 

      The unique identifier for the SSH public key.

       

      The `regex pattern`_ for this parameter is a string of characters that can consist of any upper or lowercased letter or digit.

      

    
    
    :returns: None

  .. py:method:: delete_user(**kwargs)

    

    Deletes the specified IAM user. The user must not belong to any groups or have any access keys, signing certificates, or attached policies.

    

    **Request Syntax** 
    ::

      response = client.delete_user(
          UserName='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete_user_policy(**kwargs)

    

    Deletes the specified inline policy that is embedded in the specified IAM user.

     

    A user can also have managed policies attached to it. To detach a managed policy from a user, use  DetachUserPolicy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.delete_user_policy(
          UserName='string',
          PolicyName='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name (friendly name, not ARN) identifying the user that the policy is embedded in.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name identifying the policy document to delete.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete_virtual_mfa_device(**kwargs)

    

    Deletes a virtual MFA device.

     

    .. note::

       

      You must deactivate a user's virtual MFA device before you can delete it. For information about deactivating MFA devices, see  DeactivateMFADevice . 

       

    

    **Request Syntax** 
    ::

      response = client.delete_virtual_mfa_device(
          SerialNumber='string'
      )
    :type SerialNumber: string
    :param SerialNumber: **[REQUIRED]** 

      The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the same as the ARN.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =/:,.@-

      

    
    
    :returns: None

  .. py:method:: detach_group_policy(**kwargs)

    

    Removes the specified managed policy from the specified IAM group.

     

    A group can also have inline policies embedded with it. To delete an inline policy, use the  DeleteGroupPolicy API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.detach_group_policy(
          GroupName='string',
          PolicyArn='string'
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the IAM group to detach the policy from.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to detach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: detach_role_policy(**kwargs)

    

    Removes the specified managed policy from the specified role.

     

    A role can also have inline policies embedded with it. To delete an inline policy, use the  DeleteRolePolicy API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.detach_role_policy(
          RoleName='string',
          PolicyArn='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the IAM role to detach the policy from.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to detach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: detach_user_policy(**kwargs)

    

    Removes the specified managed policy from the specified user.

     

    A user can also have inline policies embedded with it. To delete an inline policy, use the  DeleteUserPolicy API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.detach_user_policy(
          UserName='string',
          PolicyArn='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the IAM user to detach the policy from.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to detach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: enable_mfa_device(**kwargs)

    

    Enables the specified MFA device and associates it with the specified IAM user. When enabled, the MFA device is required for every subsequent login by the IAM user associated with the device.

    

    **Request Syntax** 
    ::

      response = client.enable_mfa_device(
          UserName='string',
          SerialNumber='string',
          AuthenticationCode1='string',
          AuthenticationCode2='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the IAM user for whom you want to enable the MFA device.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type SerialNumber: string
    :param SerialNumber: **[REQUIRED]** 

      The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =/:,.@-

      

    
    :type AuthenticationCode1: string
    :param AuthenticationCode1: **[REQUIRED]** 

      An authentication code emitted by the device.

       

      The format for this parameter is a string of 6 digits.

      

    
    :type AuthenticationCode2: string
    :param AuthenticationCode2: **[REQUIRED]** 

      A subsequent authentication code emitted by the device.

       

      The format for this parameter is a string of 6 digits.

      

    
    
    :returns: None

  .. py:method:: generate_credential_report()

    

    Generates a credential report for the AWS account. For more information about the credential report, see `Getting Credential Reports`_ in the *IAM User Guide* .

    

    **Request Syntax** 

    ::

      response = client.generate_credential_report()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'State': 'STARTED'|'INPROGRESS'|'COMPLETE',
            'Description': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GenerateCredentialReport request. 

        
        

        - **State** *(string) --* 

          Information about the state of the credential report.

          
        

        - **Description** *(string) --* 

          Information about the credential report.

          
    

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


  .. py:method:: get_access_key_last_used(**kwargs)

    

    Retrieves information about when the specified access key was last used. The information includes the date and time of last use, along with the AWS service and region that were specified in the last request made with that key.

    

    **Request Syntax** 
    ::

      response = client.get_access_key_last_used(
          AccessKeyId='string'
      )
    :type AccessKeyId: string
    :param AccessKeyId: **[REQUIRED]** 

      The identifier of an access key.

       

      The `regex pattern`_ for this parameter is a string of characters that can consist of any upper or lowercased letter or digit.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserName': 'string',
            'AccessKeyLastUsed': {
                'LastUsedDate': datetime(2015, 1, 1),
                'ServiceName': 'string',
                'Region': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetAccessKeyLastUsed request. It is also returned as a member of the  AccessKeyMetaData structure returned by the  ListAccessKeys action.

        
        

        - **UserName** *(string) --* 

          The name of the AWS IAM user that owns this access key.

           

          

          
        

        - **AccessKeyLastUsed** *(dict) --* 

          Contains information about the last time the access key was used.

          
          

          - **LastUsedDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the access key was most recently used. This field is null when:

             

             
            * The user does not have an access key. 
             
            * An access key exists but has never been used, at least not since IAM started tracking this information on April 22nd, 2015. 
             
            * There is no sign-in data associated with the user 
             

            
          

          - **ServiceName** *(string) --* 

            The name of the AWS service with which this access key was most recently used. This field is null when:

             

             
            * The user does not have an access key. 
             
            * An access key exists but has never been used, at least not since IAM started tracking this information on April 22nd, 2015. 
             
            * There is no sign-in data associated with the user 
             

            
          

          - **Region** *(string) --* 

            The AWS region where this access key was most recently used. This field is null when:

             

             
            * The user does not have an access key. 
             
            * An access key exists but has never been used, at least not since IAM started tracking this information on April 22nd, 2015. 
             
            * There is no sign-in data associated with the user 
             

             

            For more information about AWS regions, see `Regions and Endpoints`_ in the Amazon Web Services General Reference.

            
      
    

  .. py:method:: get_account_authorization_details(**kwargs)

    

    Retrieves information about all IAM users, groups, roles, and policies in your AWS account, including their relationships to one another. Use this API to obtain a snapshot of the configuration of IAM permissions (users, groups, roles, and policies) in your account.

     

    You can optionally filter the results using the ``Filter`` parameter. You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.get_account_authorization_details(
          Filter=[
              'User'|'Role'|'Group'|'LocalManagedPolicy'|'AWSManagedPolicy',
          ],
          MaxItems=123,
          Marker='string'
      )
    :type Filter: list
    :param Filter: 

      A list of entity types used to filter the results. Only the entities that match the types you specify are included in the output. Use the value ``LocalManagedPolicy`` to include customer managed policies.

       

      The format for this parameter is a comma-separated (if more than one) list of strings. Each string value in the list must be one of the valid values listed below.

      

    
      - *(string) --* 

      
  
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserDetailList': [
                {
                    'Path': 'string',
                    'UserName': 'string',
                    'UserId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'UserPolicyList': [
                        {
                            'PolicyName': 'string',
                            'PolicyDocument': 'string'
                        },
                    ],
                    'GroupList': [
                        'string',
                    ],
                    'AttachedManagedPolicies': [
                        {
                            'PolicyName': 'string',
                            'PolicyArn': 'string'
                        },
                    ]
                },
            ],
            'GroupDetailList': [
                {
                    'Path': 'string',
                    'GroupName': 'string',
                    'GroupId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'GroupPolicyList': [
                        {
                            'PolicyName': 'string',
                            'PolicyDocument': 'string'
                        },
                    ],
                    'AttachedManagedPolicies': [
                        {
                            'PolicyName': 'string',
                            'PolicyArn': 'string'
                        },
                    ]
                },
            ],
            'RoleDetailList': [
                {
                    'Path': 'string',
                    'RoleName': 'string',
                    'RoleId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'AssumeRolePolicyDocument': 'string',
                    'InstanceProfileList': [
                        {
                            'Path': 'string',
                            'InstanceProfileName': 'string',
                            'InstanceProfileId': 'string',
                            'Arn': 'string',
                            'CreateDate': datetime(2015, 1, 1),
                            'Roles': [
                                {
                                    'Path': 'string',
                                    'RoleName': 'string',
                                    'RoleId': 'string',
                                    'Arn': 'string',
                                    'CreateDate': datetime(2015, 1, 1),
                                    'AssumeRolePolicyDocument': 'string'
                                },
                            ]
                        },
                    ],
                    'RolePolicyList': [
                        {
                            'PolicyName': 'string',
                            'PolicyDocument': 'string'
                        },
                    ],
                    'AttachedManagedPolicies': [
                        {
                            'PolicyName': 'string',
                            'PolicyArn': 'string'
                        },
                    ]
                },
            ],
            'Policies': [
                {
                    'PolicyName': 'string',
                    'PolicyId': 'string',
                    'Arn': 'string',
                    'Path': 'string',
                    'DefaultVersionId': 'string',
                    'AttachmentCount': 123,
                    'IsAttachable': True|False,
                    'Description': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'UpdateDate': datetime(2015, 1, 1),
                    'PolicyVersionList': [
                        {
                            'Document': 'string',
                            'VersionId': 'string',
                            'IsDefaultVersion': True|False,
                            'CreateDate': datetime(2015, 1, 1)
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetAccountAuthorizationDetails request. 

        
        

        - **UserDetailList** *(list) --* 

          A list containing information about IAM users.

          
          

          - *(dict) --* 

            Contains information about an IAM user, including all the user's policies and all the IAM groups the user is in.

             

            This data type is used as a response element in the  GetAccountAuthorizationDetails action.

            
            

            - **Path** *(string) --* 

              The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **UserName** *(string) --* 

              The friendly name identifying the user.

              
            

            - **UserId** *(string) --* 

              The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user was created.

              
            

            - **UserPolicyList** *(list) --* 

              A list of the inline policies embedded in the user.

              
              

              - *(dict) --* 

                Contains information about an IAM policy, including the policy document.

                 

                This data type is used as a response element in the  GetAccountAuthorizationDetails action.

                
                

                - **PolicyName** *(string) --* 

                  The name of the policy.

                  
                

                - **PolicyDocument** *(string) --* 

                  The policy document.

                  
            
          
            

            - **GroupList** *(list) --* 

              A list of IAM groups that the user is in.

              
              

              - *(string) --* 
          
            

            - **AttachedManagedPolicies** *(list) --* 

              A list of the managed policies attached to the user.

              
              

              - *(dict) --* 

                Contains information about an attached policy.

                 

                An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

                 

                For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

                
                

                - **PolicyName** *(string) --* 

                  The friendly name of the attached policy.

                  
                

                - **PolicyArn** *(string) --* 

                  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

                   

                  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

                  
            
          
        
      
        

        - **GroupDetailList** *(list) --* 

          A list containing information about IAM groups.

          
          

          - *(dict) --* 

            Contains information about an IAM group, including all of the group's policies.

             

            This data type is used as a response element in the  GetAccountAuthorizationDetails action.

            
            

            - **Path** *(string) --* 

              The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **GroupName** *(string) --* 

              The friendly name that identifies the group.

              
            

            - **GroupId** *(string) --* 

              The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the group was created.

              
            

            - **GroupPolicyList** *(list) --* 

              A list of the inline policies embedded in the group.

              
              

              - *(dict) --* 

                Contains information about an IAM policy, including the policy document.

                 

                This data type is used as a response element in the  GetAccountAuthorizationDetails action.

                
                

                - **PolicyName** *(string) --* 

                  The name of the policy.

                  
                

                - **PolicyDocument** *(string) --* 

                  The policy document.

                  
            
          
            

            - **AttachedManagedPolicies** *(list) --* 

              A list of the managed policies attached to the group.

              
              

              - *(dict) --* 

                Contains information about an attached policy.

                 

                An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

                 

                For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

                
                

                - **PolicyName** *(string) --* 

                  The friendly name of the attached policy.

                  
                

                - **PolicyArn** *(string) --* 

                  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

                   

                  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

                  
            
          
        
      
        

        - **RoleDetailList** *(list) --* 

          A list containing information about IAM roles.

          
          

          - *(dict) --* 

            Contains information about an IAM role, including all of the role's policies.

             

            This data type is used as a response element in the  GetAccountAuthorizationDetails action.

            
            

            - **Path** *(string) --* 

              The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **RoleName** *(string) --* 

              The friendly name that identifies the role.

              
            

            - **RoleId** *(string) --* 

              The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the role was created.

              
            

            - **AssumeRolePolicyDocument** *(string) --* 

              The trust policy that grants permission to assume the role.

              
            

            - **InstanceProfileList** *(list) --* 

              Contains a list of instance profiles.

              
              

              - *(dict) --* 

                Contains information about an instance profile.

                 

                This data type is used as a response element in the following actions:

                 

                 
                *  CreateInstanceProfile   
                 
                *  GetInstanceProfile   
                 
                *  ListInstanceProfiles   
                 
                *  ListInstanceProfilesForRole   
                 

                
                

                - **Path** *(string) --* 

                  The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **InstanceProfileName** *(string) --* 

                  The name identifying the instance profile.

                  
                

                - **InstanceProfileId** *(string) --* 

                  The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **Arn** *(string) --* 

                  The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **CreateDate** *(datetime) --* 

                  The date when the instance profile was created.

                  
                

                - **Roles** *(list) --* 

                  The role associated with the instance profile.

                  
                  

                  - *(dict) --* 

                    Contains information about an IAM role.

                     

                    This data type is used as a response element in the following actions:

                     

                     
                    *  CreateRole   
                     
                    *  GetRole   
                     
                    *  ListRoles   
                     

                    
                    

                    - **Path** *(string) --* 

                      The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                      
                    

                    - **RoleName** *(string) --* 

                      The friendly name that identifies the role.

                      
                    

                    - **RoleId** *(string) --* 

                      The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                      
                    

                    - **Arn** *(string) --* 

                      The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                      
                    

                    - **CreateDate** *(datetime) --* 

                      The date and time, in `ISO 8601 date-time format`_ , when the role was created.

                      
                    

                    - **AssumeRolePolicyDocument** *(string) --* 

                      The policy that grants an entity permission to assume the role.

                      
                
              
            
          
            

            - **RolePolicyList** *(list) --* 

              A list of inline policies embedded in the role. These policies are the role's access (permissions) policies.

              
              

              - *(dict) --* 

                Contains information about an IAM policy, including the policy document.

                 

                This data type is used as a response element in the  GetAccountAuthorizationDetails action.

                
                

                - **PolicyName** *(string) --* 

                  The name of the policy.

                  
                

                - **PolicyDocument** *(string) --* 

                  The policy document.

                  
            
          
            

            - **AttachedManagedPolicies** *(list) --* 

              A list of managed policies attached to the role. These policies are the role's access (permissions) policies.

              
              

              - *(dict) --* 

                Contains information about an attached policy.

                 

                An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

                 

                For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

                
                

                - **PolicyName** *(string) --* 

                  The friendly name of the attached policy.

                  
                

                - **PolicyArn** *(string) --* 

                  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

                   

                  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

                  
            
          
        
      
        

        - **Policies** *(list) --* 

          A list containing information about managed policies.

          
          

          - *(dict) --* 

            Contains information about a managed policy, including the policy's ARN, versions, and the number of principal entities (users, groups, and roles) that the policy is attached to.

             

            This data type is used as a response element in the  GetAccountAuthorizationDetails action.

             

            For more information about managed policies, see `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name (not ARN) identifying the policy.

              
            

            - **PolicyId** *(string) --* 

              The stable and unique string identifying the policy.

               

              For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **Path** *(string) --* 

              The path to the policy.

               

              For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **DefaultVersionId** *(string) --* 

              The identifier for the version of the policy that is set as the default (operative) version.

               

              For more information about policy versions, see `Versioning for Managed Policies`_ in the *Using IAM* guide. 

              
            

            - **AttachmentCount** *(integer) --* 

              The number of principal entities (users, groups, and roles) that the policy is attached to.

              
            

            - **IsAttachable** *(boolean) --* 

              Specifies whether the policy can be attached to an IAM user, group, or role.

              
            

            - **Description** *(string) --* 

              A friendly description of the policy.

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy was created.

              
            

            - **UpdateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy was last updated.

               

              When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created.

              
            

            - **PolicyVersionList** *(list) --* 

              A list containing information about the versions of the policy.

              
              

              - *(dict) --* 

                Contains information about a version of a managed policy.

                 

                This data type is used as a response element in the  CreatePolicyVersion ,  GetPolicyVersion ,  ListPolicyVersions , and  GetAccountAuthorizationDetails actions. 

                 

                For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

                
                

                - **Document** *(string) --* 

                  The policy document.

                   

                  The policy document is returned in the response to the  GetPolicyVersion and  GetAccountAuthorizationDetails operations. It is not returned in the response to the  CreatePolicyVersion or  ListPolicyVersions operations. 

                  
                

                - **VersionId** *(string) --* 

                  The identifier for the policy version.

                   

                  Policy version identifiers always begin with ``v`` (always lowercase). When a policy is created, the first policy version is ``v1`` . 

                  
                

                - **IsDefaultVersion** *(boolean) --* 

                  Specifies whether the policy version is set as the policy's default version.

                  
                

                - **CreateDate** *(datetime) --* 

                  The date and time, in `ISO 8601 date-time format`_ , when the policy version was created.

                  
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: get_account_password_policy()

    

    Retrieves the password policy for the AWS account. For more information about using a password policy, go to `Managing an IAM Password Policy`_ .

    

    **Request Syntax** 

    ::

      response = client.get_account_password_policy()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PasswordPolicy': {
                'MinimumPasswordLength': 123,
                'RequireSymbols': True|False,
                'RequireNumbers': True|False,
                'RequireUppercaseCharacters': True|False,
                'RequireLowercaseCharacters': True|False,
                'AllowUsersToChangePassword': True|False,
                'ExpirePasswords': True|False,
                'MaxPasswordAge': 123,
                'PasswordReusePrevention': 123,
                'HardExpiry': True|False
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetAccountPasswordPolicy request. 

        
        

        - **PasswordPolicy** *(dict) --* 

          Contains information about the account password policy.

           

          This data type is used as a response element in the  GetAccountPasswordPolicy action. 

          
          

          - **MinimumPasswordLength** *(integer) --* 

            Minimum length to require for IAM user passwords.

            
          

          - **RequireSymbols** *(boolean) --* 

            Specifies whether to require symbols for IAM user passwords.

            
          

          - **RequireNumbers** *(boolean) --* 

            Specifies whether to require numbers for IAM user passwords.

            
          

          - **RequireUppercaseCharacters** *(boolean) --* 

            Specifies whether to require uppercase characters for IAM user passwords.

            
          

          - **RequireLowercaseCharacters** *(boolean) --* 

            Specifies whether to require lowercase characters for IAM user passwords.

            
          

          - **AllowUsersToChangePassword** *(boolean) --* 

            Specifies whether IAM users are allowed to change their own password.

            
          

          - **ExpirePasswords** *(boolean) --* 

            Indicates whether passwords in the account expire. Returns true if MaxPasswordAge is contains a value greater than 0. Returns false if MaxPasswordAge is 0 or not present.

            
          

          - **MaxPasswordAge** *(integer) --* 

            The number of days that an IAM user password is valid.

            
          

          - **PasswordReusePrevention** *(integer) --* 

            Specifies the number of previous passwords that IAM users are prevented from reusing.

            
          

          - **HardExpiry** *(boolean) --* 

            Specifies whether IAM users are prevented from setting a new password after their password has expired.

            
      
    

  .. py:method:: get_account_summary()

    

    Retrieves information about IAM entity usage and IAM quotas in the AWS account.

     

    For information about limitations on IAM entities, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 

    ::

      response = client.get_account_summary()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SummaryMap': {
                'string': 123
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetAccountSummary request. 

        
        

        - **SummaryMap** *(dict) --* 

          A set of key value pairs containing information about IAM entity usage and IAM quotas.

          
          

          - *(string) --* 
            

            - *(integer) --* 
      
    
    

  .. py:method:: get_context_keys_for_custom_policy(**kwargs)

    

    Gets a list of all of the context keys referenced in the input policies. The policies are supplied as a list of one or more strings. To get the context keys from policies associated with an IAM user, group, or role, use  GetContextKeysForPrincipalPolicy .

     

    Context keys are variables maintained by AWS and its services that provide details about the context of an API query request, and can be evaluated by testing against a value specified in an IAM policy. Use GetContextKeysForCustomPolicy to understand what key names and values you must supply when you call  SimulateCustomPolicy . Note that all parameters are shown in unencoded form here for clarity, but must be URL encoded to be included as a part of a real HTML request.

    

    **Request Syntax** 
    ::

      response = client.get_context_keys_for_custom_policy(
          PolicyInputList=[
              'string',
          ]
      )
    :type PolicyInputList: list
    :param PolicyInputList: **[REQUIRED]** 

      A list of policies for which you want the list of context keys referenced in those policies. Each document is specified as a string containing the complete, valid JSON text of an IAM policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ContextKeyNames': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetContextKeysForPrincipalPolicy or  GetContextKeysForCustomPolicy request. 

        
        

        - **ContextKeyNames** *(list) --* 

          The list of context keys that are referenced in the input policies.

          
          

          - *(string) --* 
      
    

  .. py:method:: get_context_keys_for_principal_policy(**kwargs)

    

    Gets a list of all of the context keys referenced in all of the IAM policies attached to the specified IAM entity. The entity can be an IAM user, group, or role. If you specify a user, then the request also includes all of the policies attached to groups that the user is a member of.

     

    You can optionally include a list of one or more additional policies, specified as strings. If you want to include *only* a list of policies by string, use  GetContextKeysForCustomPolicy instead.

     

     **Note:** This API discloses information about the permissions granted to other users. If you do not want users to see other user's permissions, then consider allowing them to use  GetContextKeysForCustomPolicy instead.

     

    Context keys are variables maintained by AWS and its services that provide details about the context of an API query request, and can be evaluated by testing against a value in an IAM policy. Use  GetContextKeysForPrincipalPolicy to understand what key names and values you must supply when you call  SimulatePrincipalPolicy .

    

    **Request Syntax** 
    ::

      response = client.get_context_keys_for_principal_policy(
          PolicySourceArn='string',
          PolicyInputList=[
              'string',
          ]
      )
    :type PolicySourceArn: string
    :param PolicySourceArn: **[REQUIRED]** 

      The ARN of a user, group, or role whose policies contain the context keys that you want listed. If you specify a user, the list includes context keys that are found in all policies attached to the user as well as to all groups that the user is a member of. If you pick a group or a role, then it includes only those context keys that are found in policies attached to that entity. Note that all parameters are shown in unencoded form here for clarity, but must be URL encoded to be included as a part of a real HTML request.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type PolicyInputList: list
    :param PolicyInputList: 

      An optional list of additional policies for which you want the list of context keys that are referenced.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ContextKeyNames': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetContextKeysForPrincipalPolicy or  GetContextKeysForCustomPolicy request. 

        
        

        - **ContextKeyNames** *(list) --* 

          The list of context keys that are referenced in the input policies.

          
          

          - *(string) --* 
      
    

  .. py:method:: get_credential_report()

    

    Retrieves a credential report for the AWS account. For more information about the credential report, see `Getting Credential Reports`_ in the *IAM User Guide* .

    

    **Request Syntax** 

    ::

      response = client.get_credential_report()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Content': b'bytes',
            'ReportFormat': 'text/csv',
            'GeneratedTime': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetCredentialReport request. 

        
        

        - **Content** *(bytes) --* 

          Contains the credential report. The report is Base64-encoded.

          
        

        - **ReportFormat** *(string) --* 

          The format (MIME type) of the credential report.

          
        

        - **GeneratedTime** *(datetime) --* 

          The date and time when the credential report was created, in `ISO 8601 date-time format`_ .

          
    

  .. py:method:: get_group(**kwargs)

    

    Returns a list of IAM users that are in the specified IAM group. You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.get_group(
          GroupName='string',
          Marker='string',
          MaxItems=123
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Group': {
                'Path': 'string',
                'GroupName': 'string',
                'GroupId': 'string',
                'Arn': 'string',
                'CreateDate': datetime(2015, 1, 1)
            },
            'Users': [
                {
                    'Path': 'string',
                    'UserName': 'string',
                    'UserId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'PasswordLastUsed': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetGroup request. 

        
        

        - **Group** *(dict) --* 

          A structure that contains details about the group.

          
          

          - **Path** *(string) --* 

            The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **GroupName** *(string) --* 

            The friendly name that identifies the group.

            
          

          - **GroupId** *(string) --* 

            The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the group was created.

            
      
        

        - **Users** *(list) --* 

          A list of users in the group.

          
          

          - *(dict) --* 

            Contains information about an IAM user entity.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateUser   
             
            *  GetUser   
             
            *  ListUsers   
             

            
            

            - **Path** *(string) --* 

              The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **UserName** *(string) --* 

              The friendly name identifying the user.

              
            

            - **UserId** *(string) --* 

              The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user was created.

              
            

            - **PasswordLastUsed** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

               

               
              * The user does not have a password 
               
              * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
               
              * there is no sign-in data associated with the user 
               

               

              This value is returned only in the  GetUser and  ListUsers actions. 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: get_group_policy(**kwargs)

    

    Retrieves the specified inline policy document that is embedded in the specified IAM group.

     

    .. note::

       

      Policies returned by this API are URL-encoded compliant with `RFC 3986`_ . You can use a URL decoding method to convert the policy back to plain JSON text. For example, if you use Java, you can use the ``decode`` method of the ``java.net.URLDecoder`` utility class in the Java SDK. Other languages and SDKs provide similar functionality.

       

     

    An IAM group can also have managed policies attached to it. To retrieve a managed policy document that is attached to a group, use  GetPolicy to determine the policy's default version, then use  GetPolicyVersion to retrieve the policy document.

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.get_group_policy(
          GroupName='string',
          PolicyName='string'
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group the policy is associated with.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy document to get.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'GroupName': 'string',
            'PolicyName': 'string',
            'PolicyDocument': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetGroupPolicy request. 

        
        

        - **GroupName** *(string) --* 

          The group the policy is associated with.

          
        

        - **PolicyName** *(string) --* 

          The name of the policy.

          
        

        - **PolicyDocument** *(string) --* 

          The policy document.

          
    

  .. py:method:: get_instance_profile(**kwargs)

    

    Retrieves information about the specified instance profile, including the instance profile's path, GUID, ARN, and role. For more information about instance profiles, see `About Instance Profiles`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.get_instance_profile(
          InstanceProfileName='string'
      )
    :type InstanceProfileName: string
    :param InstanceProfileName: **[REQUIRED]** 

      The name of the instance profile to get information about.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'InstanceProfile': {
                'Path': 'string',
                'InstanceProfileName': 'string',
                'InstanceProfileId': 'string',
                'Arn': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'Roles': [
                    {
                        'Path': 'string',
                        'RoleName': 'string',
                        'RoleId': 'string',
                        'Arn': 'string',
                        'CreateDate': datetime(2015, 1, 1),
                        'AssumeRolePolicyDocument': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetInstanceProfile request. 

        
        

        - **InstanceProfile** *(dict) --* 

          A structure containing details about the instance profile.

          
          

          - **Path** *(string) --* 

            The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **InstanceProfileName** *(string) --* 

            The name identifying the instance profile.

            
          

          - **InstanceProfileId** *(string) --* 

            The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **CreateDate** *(datetime) --* 

            The date when the instance profile was created.

            
          

          - **Roles** *(list) --* 

            The role associated with the instance profile.

            
            

            - *(dict) --* 

              Contains information about an IAM role.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateRole   
               
              *  GetRole   
               
              *  ListRoles   
               

              
              

              - **Path** *(string) --* 

                The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                
              

              - **RoleName** *(string) --* 

                The friendly name that identifies the role.

                
              

              - **RoleId** *(string) --* 

                The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                
              

              - **Arn** *(string) --* 

                The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                
              

              - **CreateDate** *(datetime) --* 

                The date and time, in `ISO 8601 date-time format`_ , when the role was created.

                
              

              - **AssumeRolePolicyDocument** *(string) --* 

                The policy that grants an entity permission to assume the role.

                
          
        
      
    

  .. py:method:: get_login_profile(**kwargs)

    

    Retrieves the user name and password-creation date for the specified IAM user. If the user has not been assigned a password, the action returns a 404 (``NoSuchEntity`` ) error.

    

    **Request Syntax** 
    ::

      response = client.get_login_profile(
          UserName='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user whose login profile you want to retrieve.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LoginProfile': {
                'UserName': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'PasswordResetRequired': True|False
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetLoginProfile request. 

        
        

        - **LoginProfile** *(dict) --* 

          A structure containing the user name and password create date for the user.

          
          

          - **UserName** *(string) --* 

            The name of the user, which can be used for signing in to the AWS Management Console.

            
          

          - **CreateDate** *(datetime) --* 

            The date when the password for the user was created.

            
          

          - **PasswordResetRequired** *(boolean) --* 

            Specifies whether the user is required to set a new password on next sign-in.

            
      
    

  .. py:method:: get_open_id_connect_provider(**kwargs)

    

    Returns information about the specified OpenID Connect (OIDC) provider resource object in IAM.

    

    **Request Syntax** 
    ::

      response = client.get_open_id_connect_provider(
          OpenIDConnectProviderArn='string'
      )
    :type OpenIDConnectProviderArn: string
    :param OpenIDConnectProviderArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the OIDC provider resource object in IAM to get information for. You can get a list of OIDC provider resource ARNs by using the  ListOpenIDConnectProviders action.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Url': 'string',
            'ClientIDList': [
                'string',
            ],
            'ThumbprintList': [
                'string',
            ],
            'CreateDate': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetOpenIDConnectProvider request. 

        
        

        - **Url** *(string) --* 

          The URL that the IAM OIDC provider resource object is associated with. For more information, see  CreateOpenIDConnectProvider .

          
        

        - **ClientIDList** *(list) --* 

          A list of client IDs (also known as audiences) that are associated with the specified IAM OIDC provider resource object. For more information, see  CreateOpenIDConnectProvider .

          
          

          - *(string) --* 
      
        

        - **ThumbprintList** *(list) --* 

          A list of certificate thumbprints that are associated with the specified IAM OIDC provider resource object. For more information, see  CreateOpenIDConnectProvider . 

          
          

          - *(string) --* 

            Contains a thumbprint for an identity provider's server certificate.

             

            The identity provider's server certificate thumbprint is the hex-encoded SHA-1 hash value of the self-signed X.509 certificate used by the domain where the OpenID Connect provider makes its keys available. It is always a 40-character string.

            
      
        

        - **CreateDate** *(datetime) --* 

          The date and time when the IAM OIDC provider resource object was created in the AWS account.

          
    

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

    

    Retrieves information about the specified managed policy, including the policy's default version and the total number of IAM users, groups, and roles to which the policy is attached. To retrieve the list of the specific users, groups, and roles that the policy is attached to, use the  ListEntitiesForPolicy API. This API returns metadata about the policy. To retrieve the actual policy document for a specific version of the policy, use  GetPolicyVersion .

     

    This API retrieves information about managed policies. To retrieve information about an inline policy that is embedded with an IAM user, group, or role, use the  GetUserPolicy ,  GetGroupPolicy , or  GetRolePolicy API.

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.get_policy(
          PolicyArn='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the managed policy that you want information about.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Policy': {
                'PolicyName': 'string',
                'PolicyId': 'string',
                'Arn': 'string',
                'Path': 'string',
                'DefaultVersionId': 'string',
                'AttachmentCount': 123,
                'IsAttachable': True|False,
                'Description': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'UpdateDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetPolicy request. 

        
        

        - **Policy** *(dict) --* 

          A structure containing details about the policy.

          
          

          - **PolicyName** *(string) --* 

            The friendly name (not ARN) identifying the policy.

            
          

          - **PolicyId** *(string) --* 

            The stable and unique string identifying the policy.

             

            For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

             

            For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

            
          

          - **Path** *(string) --* 

            The path to the policy.

             

            For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

            
          

          - **DefaultVersionId** *(string) --* 

            The identifier for the version of the policy that is set as the default version.

            
          

          - **AttachmentCount** *(integer) --* 

            The number of entities (users, groups, and roles) that the policy is attached to.

            
          

          - **IsAttachable** *(boolean) --* 

            Specifies whether the policy can be attached to an IAM user, group, or role.

            
          

          - **Description** *(string) --* 

            A friendly description of the policy.

             

            This element is included in the response to the  GetPolicy operation. It is not included in the response to the  ListPolicies operation. 

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the policy was created.

            
          

          - **UpdateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the policy was last updated.

             

            When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created.

            
      
    

  .. py:method:: get_policy_version(**kwargs)

    

    Retrieves information about the specified version of the specified managed policy, including the policy document.

     

    .. note::

       

      Policies returned by this API are URL-encoded compliant with `RFC 3986`_ . You can use a URL decoding method to convert the policy back to plain JSON text. For example, if you use Java, you can use the ``decode`` method of the ``java.net.URLDecoder`` utility class in the Java SDK. Other languages and SDKs provide similar functionality.

       

     

    To list the available versions for a policy, use  ListPolicyVersions .

     

    This API retrieves information about managed policies. To retrieve information about an inline policy that is embedded in a user, group, or role, use the  GetUserPolicy ,  GetGroupPolicy , or  GetRolePolicy API.

     

    For more information about the types of policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.get_policy_version(
          PolicyArn='string',
          VersionId='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the managed policy that you want information about.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type VersionId: string
    :param VersionId: **[REQUIRED]** 

      Identifies the policy version to retrieve.

       

      The `regex pattern`_ for this parameter is a string of characters that consists of the lowercase letter 'v' followed by one or two digits, and optionally followed by a period '.' and a string of letters and digits.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyVersion': {
                'Document': 'string',
                'VersionId': 'string',
                'IsDefaultVersion': True|False,
                'CreateDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetPolicyVersion request. 

        
        

        - **PolicyVersion** *(dict) --* 

          A structure containing details about the policy version.

          
          

          - **Document** *(string) --* 

            The policy document.

             

            The policy document is returned in the response to the  GetPolicyVersion and  GetAccountAuthorizationDetails operations. It is not returned in the response to the  CreatePolicyVersion or  ListPolicyVersions operations. 

            
          

          - **VersionId** *(string) --* 

            The identifier for the policy version.

             

            Policy version identifiers always begin with ``v`` (always lowercase). When a policy is created, the first policy version is ``v1`` . 

            
          

          - **IsDefaultVersion** *(boolean) --* 

            Specifies whether the policy version is set as the policy's default version.

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the policy version was created.

            
      
    

  .. py:method:: get_role(**kwargs)

    

    Retrieves information about the specified role, including the role's path, GUID, ARN, and the role's trust policy that grants permission to assume the role. For more information about roles, see `Working with Roles`_ .

     

    .. note::

       

      Policies returned by this API are URL-encoded compliant with `RFC 3986`_ . You can use a URL decoding method to convert the policy back to plain JSON text. For example, if you use Java, you can use the ``decode`` method of the ``java.net.URLDecoder`` utility class in the Java SDK. Other languages and SDKs provide similar functionality.

       

    

    **Request Syntax** 
    ::

      response = client.get_role(
          RoleName='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the IAM role to get information about.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Role': {
                'Path': 'string',
                'RoleName': 'string',
                'RoleId': 'string',
                'Arn': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'AssumeRolePolicyDocument': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetRole request. 

        
        

        - **Role** *(dict) --* 

          A structure containing details about the IAM role.

          
          

          - **Path** *(string) --* 

            The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **RoleName** *(string) --* 

            The friendly name that identifies the role.

            
          

          - **RoleId** *(string) --* 

            The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the role was created.

            
          

          - **AssumeRolePolicyDocument** *(string) --* 

            The policy that grants an entity permission to assume the role.

            
      
    

  .. py:method:: get_role_policy(**kwargs)

    

    Retrieves the specified inline policy document that is embedded with the specified IAM role.

     

    .. note::

       

      Policies returned by this API are URL-encoded compliant with `RFC 3986`_ . You can use a URL decoding method to convert the policy back to plain JSON text. For example, if you use Java, you can use the ``decode`` method of the ``java.net.URLDecoder`` utility class in the Java SDK. Other languages and SDKs provide similar functionality.

       

     

    An IAM role can also have managed policies attached to it. To retrieve a managed policy document that is attached to a role, use  GetPolicy to determine the policy's default version, then use  GetPolicyVersion to retrieve the policy document.

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For more information about roles, see `Using Roles to Delegate Permissions and Federate Identities`_ .

    

    **Request Syntax** 
    ::

      response = client.get_role_policy(
          RoleName='string',
          PolicyName='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role associated with the policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy document to get.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RoleName': 'string',
            'PolicyName': 'string',
            'PolicyDocument': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetRolePolicy request. 

        
        

        - **RoleName** *(string) --* 

          The role the policy is associated with.

          
        

        - **PolicyName** *(string) --* 

          The name of the policy.

          
        

        - **PolicyDocument** *(string) --* 

          The policy document.

          
    

  .. py:method:: get_saml_provider(**kwargs)

    

    Returns the SAML provider metadocument that was uploaded when the IAM SAML provider resource object was created or updated.

     

    .. note::

       

      This operation requires `Signature Version 4`_ .

       

    

    **Request Syntax** 
    ::

      response = client.get_saml_provider(
          SAMLProviderArn='string'
      )
    :type SAMLProviderArn: string
    :param SAMLProviderArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the SAML provider resource object in IAM to get information about.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SAMLMetadataDocument': 'string',
            'CreateDate': datetime(2015, 1, 1),
            'ValidUntil': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetSAMLProvider request. 

        
        

        - **SAMLMetadataDocument** *(string) --* 

          The XML metadata document that includes information about an identity provider.

          
        

        - **CreateDate** *(datetime) --* 

          The date and time when the SAML provider was created.

          
        

        - **ValidUntil** *(datetime) --* 

          The expiration date and time for the SAML provider.

          
    

  .. py:method:: get_server_certificate(**kwargs)

    

    Retrieves information about the specified server certificate stored in IAM.

     

    For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.get_server_certificate(
          ServerCertificateName='string'
      )
    :type ServerCertificateName: string
    :param ServerCertificateName: **[REQUIRED]** 

      The name of the server certificate you want to retrieve information about.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ServerCertificate': {
                'ServerCertificateMetadata': {
                    'Path': 'string',
                    'ServerCertificateName': 'string',
                    'ServerCertificateId': 'string',
                    'Arn': 'string',
                    'UploadDate': datetime(2015, 1, 1),
                    'Expiration': datetime(2015, 1, 1)
                },
                'CertificateBody': 'string',
                'CertificateChain': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetServerCertificate request. 

        
        

        - **ServerCertificate** *(dict) --* 

          A structure containing details about the server certificate.

          
          

          - **ServerCertificateMetadata** *(dict) --* 

            The meta information of the server certificate, such as its name, path, ID, and ARN.

            
            

            - **Path** *(string) --* 

              The path to the server certificate. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **ServerCertificateName** *(string) --* 

              The name that identifies the server certificate.

              
            

            - **ServerCertificateId** *(string) --* 

              The stable and unique string identifying the server certificate. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the server certificate. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **UploadDate** *(datetime) --* 

              The date when the server certificate was uploaded.

              
            

            - **Expiration** *(datetime) --* 

              The date on which the certificate is set to expire.

              
        
          

          - **CertificateBody** *(string) --* 

            The contents of the public key certificate.

            
          

          - **CertificateChain** *(string) --* 

            The contents of the public key certificate chain.

            
      
    

  .. py:method:: get_ssh_public_key(**kwargs)

    

    Retrieves the specified SSH public key, including metadata about the key.

     

    The SSH public key retrieved by this action is used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .

    

    **Request Syntax** 
    ::

      response = client.get_ssh_public_key(
          UserName='string',
          SSHPublicKeyId='string',
          Encoding='SSH'|'PEM'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the IAM user associated with the SSH public key.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type SSHPublicKeyId: string
    :param SSHPublicKeyId: **[REQUIRED]** 

      The unique identifier for the SSH public key.

       

      The `regex pattern`_ for this parameter is a string of characters that can consist of any upper or lowercased letter or digit.

      

    
    :type Encoding: string
    :param Encoding: **[REQUIRED]** 

      Specifies the public key encoding format to use in the response. To retrieve the public key in ssh-rsa format, use ``SSH`` . To retrieve the public key in PEM format, use ``PEM`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SSHPublicKey': {
                'UserName': 'string',
                'SSHPublicKeyId': 'string',
                'Fingerprint': 'string',
                'SSHPublicKeyBody': 'string',
                'Status': 'Active'|'Inactive',
                'UploadDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetSSHPublicKey request.

        
        

        - **SSHPublicKey** *(dict) --* 

          A structure containing details about the SSH public key.

          
          

          - **UserName** *(string) --* 

            The name of the IAM user associated with the SSH public key.

            
          

          - **SSHPublicKeyId** *(string) --* 

            The unique identifier for the SSH public key.

            
          

          - **Fingerprint** *(string) --* 

            The MD5 message digest of the SSH public key.

            
          

          - **SSHPublicKeyBody** *(string) --* 

            The SSH public key.

            
          

          - **Status** *(string) --* 

            The status of the SSH public key. ``Active`` means the key can be used for authentication with an AWS CodeCommit repository. ``Inactive`` means the key cannot be used.

            
          

          - **UploadDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the SSH public key was uploaded.

            
      
    

  .. py:method:: get_user(**kwargs)

    

    Retrieves information about the specified IAM user, including the user's creation date, path, unique ID, and ARN.

     

    If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID used to sign the request to this API.

    

    **Request Syntax** 
    ::

      response = client.get_user(
          UserName='string'
      )
    :type UserName: string
    :param UserName: 

      The name of the user to get information about.

       

      This parameter is optional. If it is not included, it defaults to the user making the request. The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'User': {
                'Path': 'string',
                'UserName': 'string',
                'UserId': 'string',
                'Arn': 'string',
                'CreateDate': datetime(2015, 1, 1),
                'PasswordLastUsed': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetUser request. 

        
        

        - **User** *(dict) --* 

          A structure containing details about the IAM user.

          
          

          - **Path** *(string) --* 

            The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

            
          

          - **UserName** *(string) --* 

            The friendly name identifying the user.

            
          

          - **UserId** *(string) --* 

            The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the user was created.

            
          

          - **PasswordLastUsed** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

             

             
            * The user does not have a password 
             
            * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
             
            * there is no sign-in data associated with the user 
             

             

            This value is returned only in the  GetUser and  ListUsers actions. 

            
      
    

  .. py:method:: get_user_policy(**kwargs)

    

    Retrieves the specified inline policy document that is embedded in the specified IAM user.

     

    .. note::

       

      Policies returned by this API are URL-encoded compliant with `RFC 3986`_ . You can use a URL decoding method to convert the policy back to plain JSON text. For example, if you use Java, you can use the ``decode`` method of the ``java.net.URLDecoder`` utility class in the Java SDK. Other languages and SDKs provide similar functionality.

       

     

    An IAM user can also have managed policies attached to it. To retrieve a managed policy document that is attached to a user, use  GetPolicy to determine the policy's default version, then use  GetPolicyVersion to retrieve the policy document.

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.get_user_policy(
          UserName='string',
          PolicyName='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user who the policy is associated with.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy document to get.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'UserName': 'string',
            'PolicyName': 'string',
            'PolicyDocument': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetUserPolicy request. 

        
        

        - **UserName** *(string) --* 

          The user the policy is associated with.

          
        

        - **PolicyName** *(string) --* 

          The name of the policy.

          
        

        - **PolicyDocument** *(string) --* 

          The policy document.

          
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: list_access_keys(**kwargs)

    

    Returns information about the access key IDs associated with the specified IAM user. If there are none, the action returns an empty list.

     

    Although each user is limited to a small number of keys, you can still paginate the results using the ``MaxItems`` and ``Marker`` parameters.

     

    If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    .. note::

       

      To ensure the security of your AWS account, the secret access key is accessible only during key and user creation.

       

    

    **Request Syntax** 
    ::

      response = client.list_access_keys(
          UserName='string',
          Marker='string',
          MaxItems=123
      )
    :type UserName: string
    :param UserName: 

      The name of the user.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AccessKeyMetadata': [
                {
                    'UserName': 'string',
                    'AccessKeyId': 'string',
                    'Status': 'Active'|'Inactive',
                    'CreateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAccessKeys request. 

        
        

        - **AccessKeyMetadata** *(list) --* 

          A list of objects containing metadata about the access keys.

          
          

          - *(dict) --* 

            Contains information about an AWS access key, without its secret key.

             

            This data type is used as a response element in the  ListAccessKeys action.

            
            

            - **UserName** *(string) --* 

              The name of the IAM user that the key is associated with.

              
            

            - **AccessKeyId** *(string) --* 

              The ID for this access key.

              
            

            - **Status** *(string) --* 

              The status of the access key. ``Active`` means the key is valid for API calls; ``Inactive`` means it is not.

              
            

            - **CreateDate** *(datetime) --* 

              The date when the access key was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_account_aliases(**kwargs)

    

    Lists the account alias associated with the AWS account (Note: you can have only one). For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.list_account_aliases(
          Marker='string',
          MaxItems=123
      )
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AccountAliases': [
                'string',
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAccountAliases request. 

        
        

        - **AccountAliases** *(list) --* 

          A list of aliases associated with the account. AWS supports only one alias per account.

          
          

          - *(string) --* 
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_attached_group_policies(**kwargs)

    

    Lists all managed policies that are attached to the specified IAM group.

     

    An IAM group can also have inline policies embedded with it. To list the inline policies for a group, use the  ListGroupPolicies API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. You can use the ``PathPrefix`` parameter to limit the list of policies to only those matching the specified path prefix. If there are no policies attached to the specified group (or none that match the specified path prefix), the action returns an empty list.

    

    **Request Syntax** 
    ::

      response = client.list_attached_group_policies(
          GroupName='string',
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the group to list attached policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AttachedPolicies': [
                {
                    'PolicyName': 'string',
                    'PolicyArn': 'string'
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAttachedGroupPolicies request. 

        
        

        - **AttachedPolicies** *(list) --* 

          A list of the attached policies.

          
          

          - *(dict) --* 

            Contains information about an attached policy.

             

            An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name of the attached policy.

              
            

            - **PolicyArn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_attached_role_policies(**kwargs)

    

    Lists all managed policies that are attached to the specified IAM role.

     

    An IAM role can also have inline policies embedded with it. To list the inline policies for a role, use the  ListRolePolicies API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. You can use the ``PathPrefix`` parameter to limit the list of policies to only those matching the specified path prefix. If there are no policies attached to the specified role (or none that match the specified path prefix), the action returns an empty list.

    

    **Request Syntax** 
    ::

      response = client.list_attached_role_policies(
          RoleName='string',
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the role to list attached policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AttachedPolicies': [
                {
                    'PolicyName': 'string',
                    'PolicyArn': 'string'
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAttachedRolePolicies request. 

        
        

        - **AttachedPolicies** *(list) --* 

          A list of the attached policies.

          
          

          - *(dict) --* 

            Contains information about an attached policy.

             

            An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name of the attached policy.

              
            

            - **PolicyArn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_attached_user_policies(**kwargs)

    

    Lists all managed policies that are attached to the specified IAM user.

     

    An IAM user can also have inline policies embedded with it. To list the inline policies for a user, use the  ListUserPolicies API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. You can use the ``PathPrefix`` parameter to limit the list of policies to only those matching the specified path prefix. If there are no policies attached to the specified group (or none that match the specified path prefix), the action returns an empty list.

    

    **Request Syntax** 
    ::

      response = client.list_attached_user_policies(
          UserName='string',
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the user to list attached policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AttachedPolicies': [
                {
                    'PolicyName': 'string',
                    'PolicyArn': 'string'
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAttachedUserPolicies request. 

        
        

        - **AttachedPolicies** *(list) --* 

          A list of the attached policies.

          
          

          - *(dict) --* 

            Contains information about an attached policy.

             

            An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name of the attached policy.

              
            

            - **PolicyArn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_entities_for_policy(**kwargs)

    

    Lists all IAM users, groups, and roles that the specified managed policy is attached to.

     

    You can use the optional ``EntityFilter`` parameter to limit the results to a particular type of entity (users, groups, or roles). For example, to list only the roles that are attached to the specified policy, set ``EntityFilter`` to ``Role`` .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_entities_for_policy(
          PolicyArn='string',
          EntityFilter='User'|'Role'|'Group'|'LocalManagedPolicy'|'AWSManagedPolicy',
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy for which you want the versions.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type EntityFilter: string
    :param EntityFilter: 

      The entity type to use for filtering the results.

       

      For example, when ``EntityFilter`` is ``Role`` , only the roles that are attached to the specified policy are returned. This parameter is optional. If it is not included, all attached entities (users, groups, and roles) are returned. The argument for this parameter must be one of the valid values listed below.

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all entities.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyGroups': [
                {
                    'GroupName': 'string',
                    'GroupId': 'string'
                },
            ],
            'PolicyUsers': [
                {
                    'UserName': 'string',
                    'UserId': 'string'
                },
            ],
            'PolicyRoles': [
                {
                    'RoleName': 'string',
                    'RoleId': 'string'
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListEntitiesForPolicy request. 

        
        

        - **PolicyGroups** *(list) --* 

          A list of IAM groups that the policy is attached to.

          
          

          - *(dict) --* 

            Contains information about a group that a managed policy is attached to.

             

            This data type is used as a response element in the  ListEntitiesForPolicy action. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **GroupName** *(string) --* 

              The name (friendly name, not ARN) identifying the group.

              
            

            - **GroupId** *(string) --* 

              The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *IAM User Guide* .

              
        
      
        

        - **PolicyUsers** *(list) --* 

          A list of IAM users that the policy is attached to.

          
          

          - *(dict) --* 

            Contains information about a user that a managed policy is attached to.

             

            This data type is used as a response element in the  ListEntitiesForPolicy action. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **UserName** *(string) --* 

              The name (friendly name, not ARN) identifying the user.

              
            

            - **UserId** *(string) --* 

              The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *IAM User Guide* .

              
        
      
        

        - **PolicyRoles** *(list) --* 

          A list of IAM roles that the policy is attached to.

          
          

          - *(dict) --* 

            Contains information about a role that a managed policy is attached to.

             

            This data type is used as a response element in the  ListEntitiesForPolicy action. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **RoleName** *(string) --* 

              The name (friendly name, not ARN) identifying the role.

              
            

            - **RoleId** *(string) --* 

              The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *IAM User Guide* .

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_group_policies(**kwargs)

    

    Lists the names of the inline policies that are embedded in the specified IAM group.

     

    An IAM group can also have managed policies attached to it. To list the managed policies that are attached to a group, use  ListAttachedGroupPolicies . For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. If there are no inline policies embedded with the specified group, the action returns an empty list.

    

    **Request Syntax** 
    ::

      response = client.list_group_policies(
          GroupName='string',
          Marker='string',
          MaxItems=123
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group to list policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyNames': [
                'string',
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListGroupPolicies request. 

        
        

        - **PolicyNames** *(list) --* 

          A list of policy names.

          
          

          - *(string) --* 
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_groups(**kwargs)

    

    Lists the IAM groups that have the specified path prefix.

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_groups(
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example, the prefix ``/division_abc/subdivision_xyz/`` gets all groups whose path starts with ``/division_abc/subdivision_xyz/`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all groups. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Groups': [
                {
                    'Path': 'string',
                    'GroupName': 'string',
                    'GroupId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListGroups request. 

        
        

        - **Groups** *(list) --* 

          A list of groups.

          
          

          - *(dict) --* 

            Contains information about an IAM group entity.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateGroup   
             
            *  GetGroup   
             
            *  ListGroups   
             

            
            

            - **Path** *(string) --* 

              The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **GroupName** *(string) --* 

              The friendly name that identifies the group.

              
            

            - **GroupId** *(string) --* 

              The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the group was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_groups_for_user(**kwargs)

    

    Lists the IAM groups that the specified IAM user belongs to.

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_groups_for_user(
          UserName='string',
          Marker='string',
          MaxItems=123
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to list groups for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Groups': [
                {
                    'Path': 'string',
                    'GroupName': 'string',
                    'GroupId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListGroupsForUser request. 

        
        

        - **Groups** *(list) --* 

          A list of groups.

          
          

          - *(dict) --* 

            Contains information about an IAM group entity.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateGroup   
             
            *  GetGroup   
             
            *  ListGroups   
             

            
            

            - **Path** *(string) --* 

              The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **GroupName** *(string) --* 

              The friendly name that identifies the group.

              
            

            - **GroupId** *(string) --* 

              The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the group was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_instance_profiles(**kwargs)

    

    Lists the instance profiles that have the specified path prefix. If there are none, the action returns an empty list. For more information about instance profiles, go to `About Instance Profiles`_ .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_instance_profiles(
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example, the prefix ``/application_abc/component_xyz/`` gets all instance profiles whose path starts with ``/application_abc/component_xyz/`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all instance profiles. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'InstanceProfiles': [
                {
                    'Path': 'string',
                    'InstanceProfileName': 'string',
                    'InstanceProfileId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'Roles': [
                        {
                            'Path': 'string',
                            'RoleName': 'string',
                            'RoleId': 'string',
                            'Arn': 'string',
                            'CreateDate': datetime(2015, 1, 1),
                            'AssumeRolePolicyDocument': 'string'
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListInstanceProfiles request. 

        
        

        - **InstanceProfiles** *(list) --* 

          A list of instance profiles.

          
          

          - *(dict) --* 

            Contains information about an instance profile.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateInstanceProfile   
             
            *  GetInstanceProfile   
             
            *  ListInstanceProfiles   
             
            *  ListInstanceProfilesForRole   
             

            
            

            - **Path** *(string) --* 

              The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **InstanceProfileName** *(string) --* 

              The name identifying the instance profile.

              
            

            - **InstanceProfileId** *(string) --* 

              The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date when the instance profile was created.

              
            

            - **Roles** *(list) --* 

              The role associated with the instance profile.

              
              

              - *(dict) --* 

                Contains information about an IAM role.

                 

                This data type is used as a response element in the following actions:

                 

                 
                *  CreateRole   
                 
                *  GetRole   
                 
                *  ListRoles   
                 

                
                

                - **Path** *(string) --* 

                  The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **RoleName** *(string) --* 

                  The friendly name that identifies the role.

                  
                

                - **RoleId** *(string) --* 

                  The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **Arn** *(string) --* 

                  The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **CreateDate** *(datetime) --* 

                  The date and time, in `ISO 8601 date-time format`_ , when the role was created.

                  
                

                - **AssumeRolePolicyDocument** *(string) --* 

                  The policy that grants an entity permission to assume the role.

                  
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_instance_profiles_for_role(**kwargs)

    

    Lists the instance profiles that have the specified associated IAM role. If there are none, the action returns an empty list. For more information about instance profiles, go to `About Instance Profiles`_ .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_instance_profiles_for_role(
          RoleName='string',
          Marker='string',
          MaxItems=123
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to list instance profiles for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'InstanceProfiles': [
                {
                    'Path': 'string',
                    'InstanceProfileName': 'string',
                    'InstanceProfileId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'Roles': [
                        {
                            'Path': 'string',
                            'RoleName': 'string',
                            'RoleId': 'string',
                            'Arn': 'string',
                            'CreateDate': datetime(2015, 1, 1),
                            'AssumeRolePolicyDocument': 'string'
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListInstanceProfilesForRole request. 

        
        

        - **InstanceProfiles** *(list) --* 

          A list of instance profiles.

          
          

          - *(dict) --* 

            Contains information about an instance profile.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateInstanceProfile   
             
            *  GetInstanceProfile   
             
            *  ListInstanceProfiles   
             
            *  ListInstanceProfilesForRole   
             

            
            

            - **Path** *(string) --* 

              The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **InstanceProfileName** *(string) --* 

              The name identifying the instance profile.

              
            

            - **InstanceProfileId** *(string) --* 

              The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date when the instance profile was created.

              
            

            - **Roles** *(list) --* 

              The role associated with the instance profile.

              
              

              - *(dict) --* 

                Contains information about an IAM role.

                 

                This data type is used as a response element in the following actions:

                 

                 
                *  CreateRole   
                 
                *  GetRole   
                 
                *  ListRoles   
                 

                
                

                - **Path** *(string) --* 

                  The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **RoleName** *(string) --* 

                  The friendly name that identifies the role.

                  
                

                - **RoleId** *(string) --* 

                  The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **Arn** *(string) --* 

                  The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **CreateDate** *(datetime) --* 

                  The date and time, in `ISO 8601 date-time format`_ , when the role was created.

                  
                

                - **AssumeRolePolicyDocument** *(string) --* 

                  The policy that grants an entity permission to assume the role.

                  
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_mfa_devices(**kwargs)

    

    Lists the MFA devices for an IAM user. If the request includes a IAM user name, then this action lists all the MFA devices associated with the specified user. If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request for this API.

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_mfa_devices(
          UserName='string',
          Marker='string',
          MaxItems=123
      )
    :type UserName: string
    :param UserName: 

      The name of the user whose MFA devices you want to list.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MFADevices': [
                {
                    'UserName': 'string',
                    'SerialNumber': 'string',
                    'EnableDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListMFADevices request. 

        
        

        - **MFADevices** *(list) --* 

          A list of MFA devices.

          
          

          - *(dict) --* 

            Contains information about an MFA device.

             

            This data type is used as a response element in the  ListMFADevices action.

            
            

            - **UserName** *(string) --* 

              The user with whom the MFA device is associated.

              
            

            - **SerialNumber** *(string) --* 

              The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN.

              
            

            - **EnableDate** *(datetime) --* 

              The date when the MFA device was enabled for the user.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_open_id_connect_providers()

    

    Lists information about the IAM OpenID Connect (OIDC) provider resource objects defined in the AWS account.

    

    **Request Syntax** 
    ::

      response = client.list_open_id_connect_providers()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OpenIDConnectProviderList': [
                {
                    'Arn': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListOpenIDConnectProviders request. 

        
        

        - **OpenIDConnectProviderList** *(list) --* 

          The list of IAM OIDC provider resource objects defined in the AWS account.

          
          

          - *(dict) --* 

            Contains the Amazon Resource Name (ARN) for an IAM OpenID Connect provider.

            
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
        
      
    

  .. py:method:: list_policies(**kwargs)

    

    Lists all the managed policies that are available in your AWS account, including your own customer-defined managed policies and all AWS managed policies.

     

    You can filter the list of policies that is returned using the optional ``OnlyAttached`` , ``Scope`` , and ``PathPrefix`` parameters. For example, to list only the customer managed policies in your AWS account, set ``Scope`` to ``Local`` . To list only AWS managed policies, set ``Scope`` to ``AWS`` .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

     

    For more information about managed policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.list_policies(
          Scope='All'|'AWS'|'Local',
          OnlyAttached=True|False,
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type Scope: string
    :param Scope: 

      The scope to use for filtering the results.

       

      To list only AWS managed policies, set ``Scope`` to ``AWS`` . To list only the customer managed policies in your AWS account, set ``Scope`` to ``Local`` .

       

      This parameter is optional. If it is not included, or if it is set to ``All`` , all policies are returned.

      

    
    :type OnlyAttached: boolean
    :param OnlyAttached: 

      A flag to filter the results to only the attached policies.

       

      When ``OnlyAttached`` is ``true`` , the returned list contains only the policies that are attached to an IAM user, group, or role. When ``OnlyAttached`` is ``false`` , or when the parameter is not included, all policies are returned.

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Policies': [
                {
                    'PolicyName': 'string',
                    'PolicyId': 'string',
                    'Arn': 'string',
                    'Path': 'string',
                    'DefaultVersionId': 'string',
                    'AttachmentCount': 123,
                    'IsAttachable': True|False,
                    'Description': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'UpdateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListPolicies request. 

        
        

        - **Policies** *(list) --* 

          A list of policies.

          
          

          - *(dict) --* 

            Contains information about a managed policy.

             

            This data type is used as a response element in the  CreatePolicy ,  GetPolicy , and  ListPolicies actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name (not ARN) identifying the policy.

              
            

            - **PolicyId** *(string) --* 

              The stable and unique string identifying the policy.

               

              For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **Path** *(string) --* 

              The path to the policy.

               

              For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **DefaultVersionId** *(string) --* 

              The identifier for the version of the policy that is set as the default version.

              
            

            - **AttachmentCount** *(integer) --* 

              The number of entities (users, groups, and roles) that the policy is attached to.

              
            

            - **IsAttachable** *(boolean) --* 

              Specifies whether the policy can be attached to an IAM user, group, or role.

              
            

            - **Description** *(string) --* 

              A friendly description of the policy.

               

              This element is included in the response to the  GetPolicy operation. It is not included in the response to the  ListPolicies operation. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy was created.

              
            

            - **UpdateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy was last updated.

               

              When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_policy_versions(**kwargs)

    

    Lists information about the versions of the specified managed policy, including the version that is currently set as the policy's default version.

     

    For more information about managed policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.list_policy_versions(
          PolicyArn='string',
          Marker='string',
          MaxItems=123
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy for which you want the versions.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Versions': [
                {
                    'Document': 'string',
                    'VersionId': 'string',
                    'IsDefaultVersion': True|False,
                    'CreateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListPolicyVersions request. 

        
        

        - **Versions** *(list) --* 

          A list of policy versions.

           

          For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

          
          

          - *(dict) --* 

            Contains information about a version of a managed policy.

             

            This data type is used as a response element in the  CreatePolicyVersion ,  GetPolicyVersion ,  ListPolicyVersions , and  GetAccountAuthorizationDetails actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **Document** *(string) --* 

              The policy document.

               

              The policy document is returned in the response to the  GetPolicyVersion and  GetAccountAuthorizationDetails operations. It is not returned in the response to the  CreatePolicyVersion or  ListPolicyVersions operations. 

              
            

            - **VersionId** *(string) --* 

              The identifier for the policy version.

               

              Policy version identifiers always begin with ``v`` (always lowercase). When a policy is created, the first policy version is ``v1`` . 

              
            

            - **IsDefaultVersion** *(boolean) --* 

              Specifies whether the policy version is set as the policy's default version.

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy version was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_role_policies(**kwargs)

    

    Lists the names of the inline policies that are embedded in the specified IAM role.

     

    An IAM role can also have managed policies attached to it. To list the managed policies that are attached to a role, use  ListAttachedRolePolicies . For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. If there are no inline policies embedded with the specified role, the action returns an empty list.

    

    **Request Syntax** 
    ::

      response = client.list_role_policies(
          RoleName='string',
          Marker='string',
          MaxItems=123
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to list policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyNames': [
                'string',
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListRolePolicies request. 

        
        

        - **PolicyNames** *(list) --* 

          A list of policy names.

          
          

          - *(string) --* 
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_roles(**kwargs)

    

    Lists the IAM roles that have the specified path prefix. If there are none, the action returns an empty list. For more information about roles, go to `Working with Roles`_ .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_roles(
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example, the prefix ``/application_abc/component_xyz/`` gets all roles whose path starts with ``/application_abc/component_xyz/`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all roles. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Roles': [
                {
                    'Path': 'string',
                    'RoleName': 'string',
                    'RoleId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'AssumeRolePolicyDocument': 'string'
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListRoles request. 

        
        

        - **Roles** *(list) --* 

          A list of roles.

          
          

          - *(dict) --* 

            Contains information about an IAM role.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateRole   
             
            *  GetRole   
             
            *  ListRoles   
             

            
            

            - **Path** *(string) --* 

              The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **RoleName** *(string) --* 

              The friendly name that identifies the role.

              
            

            - **RoleId** *(string) --* 

              The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the role was created.

              
            

            - **AssumeRolePolicyDocument** *(string) --* 

              The policy that grants an entity permission to assume the role.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_saml_providers()

    

    Lists the SAML provider resource objects defined in IAM in the account.

     

    .. note::

       

      This operation requires `Signature Version 4`_ .

       

    

    **Request Syntax** 
    ::

      response = client.list_saml_providers()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SAMLProviderList': [
                {
                    'Arn': 'string',
                    'ValidUntil': datetime(2015, 1, 1),
                    'CreateDate': datetime(2015, 1, 1)
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListSAMLProviders request. 

        
        

        - **SAMLProviderList** *(list) --* 

          The list of SAML provider resource objects defined in IAM for this AWS account.

          
          

          - *(dict) --* 

            Contains the list of SAML providers for this account.

            
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) of the SAML provider.

              
            

            - **ValidUntil** *(datetime) --* 

              The expiration date and time for the SAML provider.

              
            

            - **CreateDate** *(datetime) --* 

              The date and time when the SAML provider was created.

              
        
      
    

  .. py:method:: list_server_certificates(**kwargs)

    

    Lists the server certificates stored in IAM that have the specified path prefix. If none exist, the action returns an empty list.

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

     

    For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.list_server_certificates(
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example: ``/company/servercerts`` would get all server certificates for which the path starts with ``/company/servercerts`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all server certificates. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ServerCertificateMetadataList': [
                {
                    'Path': 'string',
                    'ServerCertificateName': 'string',
                    'ServerCertificateId': 'string',
                    'Arn': 'string',
                    'UploadDate': datetime(2015, 1, 1),
                    'Expiration': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListServerCertificates request. 

        
        

        - **ServerCertificateMetadataList** *(list) --* 

          A list of server certificates.

          
          

          - *(dict) --* 

            Contains information about a server certificate without its certificate body, certificate chain, and private key.

             

            This data type is used as a response element in the  UploadServerCertificate and  ListServerCertificates actions. 

            
            

            - **Path** *(string) --* 

              The path to the server certificate. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **ServerCertificateName** *(string) --* 

              The name that identifies the server certificate.

              
            

            - **ServerCertificateId** *(string) --* 

              The stable and unique string identifying the server certificate. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the server certificate. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **UploadDate** *(datetime) --* 

              The date when the server certificate was uploaded.

              
            

            - **Expiration** *(datetime) --* 

              The date on which the certificate is set to expire.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_signing_certificates(**kwargs)

    

    Returns information about the signing certificates associated with the specified IAM user. If there are none, the action returns an empty list.

     

    Although each user is limited to a small number of signing certificates, you can still paginate the results using the ``MaxItems`` and ``Marker`` parameters.

     

    If the ``UserName`` field is not specified, the user name is determined implicitly based on the AWS access key ID used to sign the request for this API. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

    

    **Request Syntax** 
    ::

      response = client.list_signing_certificates(
          UserName='string',
          Marker='string',
          MaxItems=123
      )
    :type UserName: string
    :param UserName: 

      The name of the IAM user whose signing certificates you want to examine.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Certificates': [
                {
                    'UserName': 'string',
                    'CertificateId': 'string',
                    'CertificateBody': 'string',
                    'Status': 'Active'|'Inactive',
                    'UploadDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListSigningCertificates request. 

        
        

        - **Certificates** *(list) --* 

          A list of the user's signing certificate information.

          
          

          - *(dict) --* 

            Contains information about an X.509 signing certificate.

             

            This data type is used as a response element in the  UploadSigningCertificate and  ListSigningCertificates actions. 

            
            

            - **UserName** *(string) --* 

              The name of the user the signing certificate is associated with.

              
            

            - **CertificateId** *(string) --* 

              The ID for the signing certificate.

              
            

            - **CertificateBody** *(string) --* 

              The contents of the signing certificate.

              
            

            - **Status** *(string) --* 

              The status of the signing certificate. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not.

              
            

            - **UploadDate** *(datetime) --* 

              The date when the signing certificate was uploaded.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_ssh_public_keys(**kwargs)

    

    Returns information about the SSH public keys associated with the specified IAM user. If there are none, the action returns an empty list.

     

    The SSH public keys returned by this action are used only for authenticating the IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .

     

    Although each user is limited to a small number of keys, you can still paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_ssh_public_keys(
          UserName='string',
          Marker='string',
          MaxItems=123
      )
    :type UserName: string
    :param UserName: 

      The name of the IAM user to list SSH public keys for. If none is specified, the UserName field is determined implicitly based on the AWS access key used to sign the request.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SSHPublicKeys': [
                {
                    'UserName': 'string',
                    'SSHPublicKeyId': 'string',
                    'Status': 'Active'|'Inactive',
                    'UploadDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListSSHPublicKeys request.

        
        

        - **SSHPublicKeys** *(list) --* 

          A list of the SSH public keys assigned to IAM user.

          
          

          - *(dict) --* 

            Contains information about an SSH public key, without the key's body or fingerprint.

             

            This data type is used as a response element in the  ListSSHPublicKeys action.

            
            

            - **UserName** *(string) --* 

              The name of the IAM user associated with the SSH public key.

              
            

            - **SSHPublicKeyId** *(string) --* 

              The unique identifier for the SSH public key.

              
            

            - **Status** *(string) --* 

              The status of the SSH public key. ``Active`` means the key can be used for authentication with an AWS CodeCommit repository. ``Inactive`` means the key cannot be used.

              
            

            - **UploadDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the SSH public key was uploaded.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_user_policies(**kwargs)

    

    Lists the names of the inline policies embedded in the specified IAM user.

     

    An IAM user can also have managed policies attached to it. To list the managed policies that are attached to a user, use  ListAttachedUserPolicies . For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. If there are no inline policies embedded with the specified user, the action returns an empty list.

    

    **Request Syntax** 
    ::

      response = client.list_user_policies(
          UserName='string',
          Marker='string',
          MaxItems=123
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to list policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyNames': [
                'string',
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListUserPolicies request. 

        
        

        - **PolicyNames** *(list) --* 

          A list of policy names.

          
          

          - *(string) --* 
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_users(**kwargs)

    

    Lists the IAM users that have the specified path prefix. If no path prefix is specified, the action returns all users in the AWS account. If there are none, the action returns an empty list.

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_users(
          PathPrefix='string',
          Marker='string',
          MaxItems=123
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example: ``/division_abc/subdivision_xyz/`` , which would get all user names whose path starts with ``/division_abc/subdivision_xyz/`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all user names. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Users': [
                {
                    'Path': 'string',
                    'UserName': 'string',
                    'UserId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'PasswordLastUsed': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListUsers request. 

        
        

        - **Users** *(list) --* 

          A list of users.

          
          

          - *(dict) --* 

            Contains information about an IAM user entity.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateUser   
             
            *  GetUser   
             
            *  ListUsers   
             

            
            

            - **Path** *(string) --* 

              The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **UserName** *(string) --* 

              The friendly name identifying the user.

              
            

            - **UserId** *(string) --* 

              The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user was created.

              
            

            - **PasswordLastUsed** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

               

               
              * The user does not have a password 
               
              * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
               
              * there is no sign-in data associated with the user 
               

               

              This value is returned only in the  GetUser and  ListUsers actions. 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: list_virtual_mfa_devices(**kwargs)

    

    Lists the virtual MFA devices defined in the AWS account by assignment status. If you do not specify an assignment status, the action returns a list of all virtual MFA devices. Assignment status can be ``Assigned`` , ``Unassigned`` , or ``Any`` .

     

    You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

    

    **Request Syntax** 
    ::

      response = client.list_virtual_mfa_devices(
          AssignmentStatus='Assigned'|'Unassigned'|'Any',
          Marker='string',
          MaxItems=123
      )
    :type AssignmentStatus: string
    :param AssignmentStatus: 

      The status (``Unassigned`` or ``Assigned`` ) of the devices to list. If you do not specify an ``AssignmentStatus`` , the action defaults to ``Any`` which lists both assigned and unassigned virtual MFA devices.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VirtualMFADevices': [
                {
                    'SerialNumber': 'string',
                    'Base32StringSeed': b'bytes',
                    'QRCodePNG': b'bytes',
                    'User': {
                        'Path': 'string',
                        'UserName': 'string',
                        'UserId': 'string',
                        'Arn': 'string',
                        'CreateDate': datetime(2015, 1, 1),
                        'PasswordLastUsed': datetime(2015, 1, 1)
                    },
                    'EnableDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListVirtualMFADevices request. 

        
        

        - **VirtualMFADevices** *(list) --* 

          The list of virtual MFA devices in the current account that match the ``AssignmentStatus`` value that was passed in the request.

          
          

          - *(dict) --* 

            Contains information about a virtual MFA device.

            
            

            - **SerialNumber** *(string) --* 

              The serial number associated with ``VirtualMFADevice`` .

              
            

            - **Base32StringSeed** *(bytes) --* 

              The Base32 seed defined as specified in `RFC3548`_ . The ``Base32StringSeed`` is Base64-encoded. 

              
            

            - **QRCodePNG** *(bytes) --* 

              A QR code PNG image that encodes ``otpauth://totp/$virtualMFADeviceName@$AccountName?secret=$Base32String`` where ``$virtualMFADeviceName`` is one of the create call arguments, ``AccountName`` is the user name if set (otherwise, the account ID otherwise), and ``Base32String`` is the seed in Base32 format. The ``Base32String`` value is Base64-encoded. 

              
            

            - **User** *(dict) --* 

              Contains information about an IAM user entity.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateUser   
               
              *  GetUser   
               
              *  ListUsers   
               

              
              

              - **Path** *(string) --* 

                The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

                
              

              - **UserName** *(string) --* 

                The friendly name identifying the user.

                
              

              - **UserId** *(string) --* 

                The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

                
              

              - **Arn** *(string) --* 

                The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                
              

              - **CreateDate** *(datetime) --* 

                The date and time, in `ISO 8601 date-time format`_ , when the user was created.

                
              

              - **PasswordLastUsed** *(datetime) --* 

                The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

                 

                 
                * The user does not have a password 
                 
                * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
                 
                * there is no sign-in data associated with the user 
                 

                 

                This value is returned only in the  GetUser and  ListUsers actions. 

                
          
            

            - **EnableDate** *(datetime) --* 

              The date and time on which the virtual MFA device was enabled.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: put_group_policy(**kwargs)

    

    Adds or updates an inline policy document that is embedded in the specified IAM group.

     

    A user can also have managed policies attached to it. To attach a managed policy to a group, use  AttachGroupPolicy . To create a new managed policy, use  CreatePolicy . For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For information about limits on the number of inline policies that you can embed in a group, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. note::

       

      Because policy documents can be large, you should use POST rather than GET when calling ``PutGroupPolicy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      response = client.put_group_policy(
          GroupName='string',
          PolicyName='string',
          PolicyDocument='string'
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group to associate the policy with.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :returns: None

  .. py:method:: put_role_policy(**kwargs)

    

    Adds or updates an inline policy document that is embedded in the specified IAM role.

     

    When you embed an inline policy in a role, the inline policy is used as part of the role's access (permissions) policy. The role's trust policy is created at the same time as the role, using  CreateRole . You can update a role's trust policy using  UpdateAssumeRolePolicy . For more information about IAM roles, go to `Using Roles to Delegate Permissions and Federate Identities`_ .

     

    A role can also have a managed policy attached to it. To attach a managed policy to a role, use  AttachRolePolicy . To create a new managed policy, use  CreatePolicy . For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For information about limits on the number of inline policies that you can embed with a role, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. note::

       

      Because policy documents can be large, you should use POST rather than GET when calling ``PutRolePolicy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      response = client.put_role_policy(
          RoleName='string',
          PolicyName='string',
          PolicyDocument='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to associate the policy with.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :returns: None

  .. py:method:: put_user_policy(**kwargs)

    

    Adds or updates an inline policy document that is embedded in the specified IAM user.

     

    An IAM user can also have a managed policy attached to it. To attach a managed policy to a user, use  AttachUserPolicy . To create a new managed policy, use  CreatePolicy . For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For information about limits on the number of inline policies that you can embed in a user, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. note::

       

      Because policy documents can be large, you should use POST rather than GET when calling ``PutUserPolicy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      response = client.put_user_policy(
          UserName='string',
          PolicyName='string',
          PolicyDocument='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to associate the policy with.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :returns: None

  .. py:method:: remove_client_id_from_open_id_connect_provider(**kwargs)

    

    Removes the specified client ID (also known as audience) from the list of client IDs registered for the specified IAM OpenID Connect (OIDC) provider resource object.

     

    This action is idempotent; it does not fail or return an error if you try to remove a client ID that does not exist.

    

    **Request Syntax** 
    ::

      response = client.remove_client_id_from_open_id_connect_provider(
          OpenIDConnectProviderArn='string',
          ClientID='string'
      )
    :type OpenIDConnectProviderArn: string
    :param OpenIDConnectProviderArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM OIDC provider resource to remove the client ID from. You can get a list of OIDC provider ARNs by using the  ListOpenIDConnectProviders action.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type ClientID: string
    :param ClientID: **[REQUIRED]** 

      The client ID (also known as audience) to remove from the IAM OIDC provider resource. For more information about client IDs, see  CreateOpenIDConnectProvider .

      

    
    
    :returns: None

  .. py:method:: remove_role_from_instance_profile(**kwargs)

    

    Removes the specified IAM role from the specified EC2 instance profile.

     

    .. warning::

       

      Make sure you do not have any Amazon EC2 instances running with the role you are about to remove from the instance profile. Removing a role from an instance profile that is associated with a running instance break any applications running on the instance.

       

     

    For more information about IAM roles, go to `Working with Roles`_ . For more information about instance profiles, go to `About Instance Profiles`_ .

    

    **Request Syntax** 
    ::

      response = client.remove_role_from_instance_profile(
          InstanceProfileName='string',
          RoleName='string'
      )
    :type InstanceProfileName: string
    :param InstanceProfileName: **[REQUIRED]** 

      The name of the instance profile to update.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to remove.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: remove_user_from_group(**kwargs)

    

    Removes the specified user from the specified group.

    

    **Request Syntax** 
    ::

      response = client.remove_user_from_group(
          GroupName='string',
          UserName='string'
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group to update.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to remove.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: resync_mfa_device(**kwargs)

    

    Synchronizes the specified MFA device with its IAM resource object on the AWS servers.

     

    For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.resync_mfa_device(
          UserName='string',
          SerialNumber='string',
          AuthenticationCode1='string',
          AuthenticationCode2='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user whose MFA device you want to resynchronize.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type SerialNumber: string
    :param SerialNumber: **[REQUIRED]** 

      Serial number that uniquely identifies the MFA device.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type AuthenticationCode1: string
    :param AuthenticationCode1: **[REQUIRED]** 

      An authentication code emitted by the device.

       

      The format for this parameter is a sequence of six digits.

      

    
    :type AuthenticationCode2: string
    :param AuthenticationCode2: **[REQUIRED]** 

      A subsequent authentication code emitted by the device.

       

      The format for this parameter is a sequence of six digits.

      

    
    
    :returns: None

  .. py:method:: set_default_policy_version(**kwargs)

    

    Sets the specified version of the specified policy as the policy's default (operative) version.

     

    This action affects all users, groups, and roles that the policy is attached to. To list the users, groups, and roles that the policy is attached to, use the  ListEntitiesForPolicy API.

     

    For information about managed policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.set_default_policy_version(
          PolicyArn='string',
          VersionId='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy whose default version you want to set.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type VersionId: string
    :param VersionId: **[REQUIRED]** 

      The version of the policy to set as the default (operative) version.

       

      For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

      

    
    
    :returns: None

  .. py:method:: simulate_custom_policy(**kwargs)

    

    Simulate how a set of IAM policies and optionally a resource-based policy works with a list of API actions and AWS resources to determine the policies' effective permissions. The policies are provided as strings.

     

    The simulation does not perform the API actions; it only checks the authorization to determine if the simulated policies allow or deny the actions.

     

    If you want to simulate existing policies attached to an IAM user, group, or role, use  SimulatePrincipalPolicy instead.

     

    Context keys are variables maintained by AWS and its services that provide details about the context of an API query request. You can use the ``Condition`` element of an IAM policy to evaluate context keys. To get the list of context keys that the policies require for correct simulation, use  GetContextKeysForCustomPolicy .

     

    If the output is long, you can use ``MaxItems`` and ``Marker`` parameters to paginate the results.

    

    **Request Syntax** 
    ::

      response = client.simulate_custom_policy(
          PolicyInputList=[
              'string',
          ],
          ActionNames=[
              'string',
          ],
          ResourceArns=[
              'string',
          ],
          ResourcePolicy='string',
          ResourceOwner='string',
          CallerArn='string',
          ContextEntries=[
              {
                  'ContextKeyName': 'string',
                  'ContextKeyValues': [
                      'string',
                  ],
                  'ContextKeyType': 'string'|'stringList'|'numeric'|'numericList'|'boolean'|'booleanList'|'ip'|'ipList'|'binary'|'binaryList'|'date'|'dateList'
              },
          ],
          ResourceHandlingOption='string',
          MaxItems=123,
          Marker='string'
      )
    :type PolicyInputList: list
    :param PolicyInputList: **[REQUIRED]** 

      A list of policy documents to include in the simulation. Each document is specified as a string containing the complete, valid JSON text of an IAM policy. Do not include any resource-based policies in this parameter. Any resource-based policy must be submitted with the ``ResourcePolicy`` parameter. The policies cannot be "scope-down" policies, such as you could include in a call to `GetFederationToken`_ or one of the `AssumeRole`_ APIs to restrict what a user can do while using the temporary credentials.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
      - *(string) --* 

      
  
    :type ActionNames: list
    :param ActionNames: **[REQUIRED]** 

      A list of names of API actions to evaluate in the simulation. Each action is evaluated against each resource. Each action must include the service identifier, such as ``iam:CreateUser`` .

      

    
      - *(string) --* 

      
  
    :type ResourceArns: list
    :param ResourceArns: 

      A list of ARNs of AWS resources to include in the simulation. If this parameter is not provided then the value defaults to ``*`` (all resources). Each API in the ``ActionNames`` parameter is evaluated for each resource in this list. The simulation determines the access result (allowed or denied) of each combination and reports it in the response.

       

      The simulation does not automatically retrieve policies for the specified resources. If you want to include a resource policy in the simulation, then you must include the policy as a string in the ``ResourcePolicy`` parameter.

       

      If you include a ``ResourcePolicy`` , then it must be applicable to all of the resources included in the simulation or you receive an invalid input error.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
      - *(string) --* 

      
  
    :type ResourcePolicy: string
    :param ResourcePolicy: 

      A resource-based policy to include in the simulation provided as a string. Each resource in the simulation is treated as if it had this policy attached. You can include only one resource-based policy in a simulation.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type ResourceOwner: string
    :param ResourceOwner: 

      An AWS account ID that specifies the owner of any simulated resource that does not identify its owner in the resource ARN, such as an S3 bucket or object. If ``ResourceOwner`` is specified, it is also used as the account owner of any ``ResourcePolicy`` included in the simulation. If the ``ResourceOwner`` parameter is not specified, then the owner of the resources and the resource policy defaults to the account of the identity provided in ``CallerArn`` . This parameter is required only if you specify a resource-based policy and account that owns the resource is different from the account that owns the simulated calling user ``CallerArn`` .

      

    
    :type CallerArn: string
    :param CallerArn: 

      The ARN of the IAM user that you want to use as the simulated caller of the APIs. ``CallerArn`` is required if you include a ``ResourcePolicy`` so that the policy's ``Principal`` element has a value to use in evaluating the policy.

       

      You can specify only the ARN of an IAM user. You cannot specify the ARN of an assumed role, federated user, or a service principal.

      

    
    :type ContextEntries: list
    :param ContextEntries: 

      A list of context keys and corresponding values for the simulation to use. Whenever a context key is evaluated in one of the simulated IAM permission policies, the corresponding value is supplied.

      

    
      - *(dict) --* 

        Contains information about a condition context key. It includes the name of the key and specifies the value (or values, if the context key supports multiple values) to use in the simulation. This information is used when evaluating the ``Condition`` elements of the input policies.

         

        This data type is used as an input parameter to ``  SimulateCustomPolicy `` and ``  SimulateCustomPolicy `` .

        

      
        - **ContextKeyName** *(string) --* 

          The full name of a condition context key, including the service prefix. For example, ``aws:SourceIp`` or ``s3:VersionId`` .

          

        
        - **ContextKeyValues** *(list) --* 

          The value (or values, if the condition context key supports multiple values) to provide to the simulation for use when the key is referenced by a ``Condition`` element in an input policy.

          

        
          - *(string) --* 

          
      
        - **ContextKeyType** *(string) --* 

          The data type of the value (or values) specified in the ``ContextKeyValues`` parameter.

          

        
      
  
    :type ResourceHandlingOption: string
    :param ResourceHandlingOption: 

      Specifies the type of simulation to run. Different APIs that support resource-based policies require different combinations of resources. By specifying the type of simulation to run, you enable the policy simulator to enforce the presence of the required resources to ensure reliable simulation results. If your simulation does not match one of the following scenarios, then you can omit this parameter. The following list shows each of the supported scenario values and the resources that you must define to run the simulation.

       

      Each of the EC2 scenarios requires that you specify instance, image, and security-group resources. If your scenario includes an EBS volume, then you must specify that volume as a resource. If the EC2 scenario includes VPC, then you must supply the network-interface resource. If it includes an IP subnet, then you must specify the subnet resource. For more information on the EC2 scenario options, see `Supported Platforms`_ in the *AWS EC2 User Guide* .

       

       
      * **EC2-Classic-InstanceStore**   instance, image, security-group 
       
      * **EC2-Classic-EBS**   instance, image, security-group, volume 
       
      * **EC2-VPC-InstanceStore**   instance, image, security-group, network-interface 
       
      * **EC2-VPC-InstanceStore-Subnet**   instance, image, security-group, network-interface, subnet 
       
      * **EC2-VPC-EBS**   instance, image, security-group, network-interface, volume 
       
      * **EC2-VPC-EBS-Subnet**   instance, image, security-group, network-interface, subnet, volume 
       

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EvaluationResults': [
                {
                    'EvalActionName': 'string',
                    'EvalResourceName': 'string',
                    'EvalDecision': 'allowed'|'explicitDeny'|'implicitDeny',
                    'MatchedStatements': [
                        {
                            'SourcePolicyId': 'string',
                            'SourcePolicyType': 'user'|'group'|'role'|'aws-managed'|'user-managed'|'resource'|'none',
                            'StartPosition': {
                                'Line': 123,
                                'Column': 123
                            },
                            'EndPosition': {
                                'Line': 123,
                                'Column': 123
                            }
                        },
                    ],
                    'MissingContextValues': [
                        'string',
                    ],
                    'EvalDecisionDetails': {
                        'string': 'allowed'|'explicitDeny'|'implicitDeny'
                    },
                    'ResourceSpecificResults': [
                        {
                            'EvalResourceName': 'string',
                            'EvalResourceDecision': 'allowed'|'explicitDeny'|'implicitDeny',
                            'MatchedStatements': [
                                {
                                    'SourcePolicyId': 'string',
                                    'SourcePolicyType': 'user'|'group'|'role'|'aws-managed'|'user-managed'|'resource'|'none',
                                    'StartPosition': {
                                        'Line': 123,
                                        'Column': 123
                                    },
                                    'EndPosition': {
                                        'Line': 123,
                                        'Column': 123
                                    }
                                },
                            ],
                            'MissingContextValues': [
                                'string',
                            ],
                            'EvalDecisionDetails': {
                                'string': 'allowed'|'explicitDeny'|'implicitDeny'
                            }
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  SimulatePrincipalPolicy or  SimulateCustomPolicy request.

        
        

        - **EvaluationResults** *(list) --* 

          The results of the simulation.

          
          

          - *(dict) --* 

            Contains the results of a simulation.

             

            This data type is used by the return parameter of ``  SimulateCustomPolicy `` and ``  SimulatePrincipalPolicy `` .

            
            

            - **EvalActionName** *(string) --* 

              The name of the API action tested on the indicated resource.

              
            

            - **EvalResourceName** *(string) --* 

              The ARN of the resource that the indicated API action was tested on.

              
            

            - **EvalDecision** *(string) --* 

              The result of the simulation.

              
            

            - **MatchedStatements** *(list) --* 

              A list of the statements in the input policies that determine the result for this scenario. Remember that even if multiple statements allow the action on the resource, if only one statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

              
              

              - *(dict) --* 

                Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

                 

                This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

                
                

                - **SourcePolicyId** *(string) --* 

                  The identifier of the policy that was provided as an input.

                  
                

                - **SourcePolicyType** *(string) --* 

                  The type of the policy.

                  
                

                - **StartPosition** *(dict) --* 

                  The row and column of the beginning of the ``Statement`` in an IAM policy.

                  
                  

                  - **Line** *(integer) --* 

                    The line containing the specified position in the document.

                    
                  

                  - **Column** *(integer) --* 

                    The column in the line containing the specified position in the document.

                    
              
                

                - **EndPosition** *(dict) --* 

                  The row and column of the end of a ``Statement`` in an IAM policy.

                  
                  

                  - **Line** *(integer) --* 

                    The line containing the specified position in the document.

                    
                  

                  - **Column** *(integer) --* 

                    The column in the line containing the specified position in the document.

                    
              
            
          
            

            - **MissingContextValues** *(list) --* 

              A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when the resource in a simulation is "*", either explicitly, or when the ``ResourceArns`` parameter blank. If you include a list of resources, then any missing context values are instead included under the ``ResourceSpecificResults`` section. To discover the context keys used by a set of policies, you can call  GetContextKeysForCustomPolicy or  GetContextKeysForPrincipalPolicy .

              
              

              - *(string) --* 
          
            

            - **EvalDecisionDetails** *(dict) --* 

              Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access. See `How IAM Roles Differ from Resource-based Policies`_  

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
            

            - **ResourceSpecificResults** *(list) --* 

              The individual results of the simulation of the API action specified in EvalActionName on each resource.

              
              

              - *(dict) --* 

                Contains the result of the simulation of a single API action call on a single resource.

                 

                This data type is used by a member of the  EvaluationResult data type.

                
                

                - **EvalResourceName** *(string) --* 

                  The name of the simulated resource, in Amazon Resource Name (ARN) format.

                  
                

                - **EvalResourceDecision** *(string) --* 

                  The result of the simulation of the simulated API action on the resource specified in ``EvalResourceName`` .

                  
                

                - **MatchedStatements** *(list) --* 

                  A list of the statements in the input policies that determine the result for this part of the simulation. Remember that even if multiple statements allow the action on the resource, if *any* statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

                  
                  

                  - *(dict) --* 

                    Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

                     

                    This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

                    
                    

                    - **SourcePolicyId** *(string) --* 

                      The identifier of the policy that was provided as an input.

                      
                    

                    - **SourcePolicyType** *(string) --* 

                      The type of the policy.

                      
                    

                    - **StartPosition** *(dict) --* 

                      The row and column of the beginning of the ``Statement`` in an IAM policy.

                      
                      

                      - **Line** *(integer) --* 

                        The line containing the specified position in the document.

                        
                      

                      - **Column** *(integer) --* 

                        The column in the line containing the specified position in the document.

                        
                  
                    

                    - **EndPosition** *(dict) --* 

                      The row and column of the end of a ``Statement`` in an IAM policy.

                      
                      

                      - **Line** *(integer) --* 

                        The line containing the specified position in the document.

                        
                      

                      - **Column** *(integer) --* 

                        The column in the line containing the specified position in the document.

                        
                  
                
              
                

                - **MissingContextValues** *(list) --* 

                  A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when a list of ARNs is included in the ``ResourceArns`` parameter instead of "*". If you do not specify individual resources, by setting ``ResourceArns`` to "*" or by not including the ``ResourceArns`` parameter, then any missing context values are instead included under the ``EvaluationResults`` section. To discover the context keys used by a set of policies, you can call  GetContextKeysForCustomPolicy or  GetContextKeysForPrincipalPolicy .

                  
                  

                  - *(string) --* 
              
                

                - **EvalDecisionDetails** *(dict) --* 

                  Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: simulate_principal_policy(**kwargs)

    

    Simulate how a set of IAM policies attached to an IAM entity works with a list of API actions and AWS resources to determine the policies' effective permissions. The entity can be an IAM user, group, or role. If you specify a user, then the simulation also includes all of the policies that are attached to groups that the user belongs to .

     

    You can optionally include a list of one or more additional policies specified as strings to include in the simulation. If you want to simulate only policies specified as strings, use  SimulateCustomPolicy instead.

     

    You can also optionally include one resource-based policy to be evaluated with each of the resources included in the simulation.

     

    The simulation does not perform the API actions, it only checks the authorization to determine if the simulated policies allow or deny the actions.

     

     **Note:** This API discloses information about the permissions granted to other users. If you do not want users to see other user's permissions, then consider allowing them to use  SimulateCustomPolicy instead.

     

    Context keys are variables maintained by AWS and its services that provide details about the context of an API query request. You can use the ``Condition`` element of an IAM policy to evaluate context keys. To get the list of context keys that the policies require for correct simulation, use  GetContextKeysForPrincipalPolicy .

     

    If the output is long, you can use the ``MaxItems`` and ``Marker`` parameters to paginate the results.

    

    **Request Syntax** 
    ::

      response = client.simulate_principal_policy(
          PolicySourceArn='string',
          PolicyInputList=[
              'string',
          ],
          ActionNames=[
              'string',
          ],
          ResourceArns=[
              'string',
          ],
          ResourcePolicy='string',
          ResourceOwner='string',
          CallerArn='string',
          ContextEntries=[
              {
                  'ContextKeyName': 'string',
                  'ContextKeyValues': [
                      'string',
                  ],
                  'ContextKeyType': 'string'|'stringList'|'numeric'|'numericList'|'boolean'|'booleanList'|'ip'|'ipList'|'binary'|'binaryList'|'date'|'dateList'
              },
          ],
          ResourceHandlingOption='string',
          MaxItems=123,
          Marker='string'
      )
    :type PolicySourceArn: string
    :param PolicySourceArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of a user, group, or role whose policies you want to include in the simulation. If you specify a user, group, or role, the simulation includes all policies that are associated with that entity. If you specify a user, the simulation also includes all policies that are attached to any groups the user belongs to.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type PolicyInputList: list
    :param PolicyInputList: 

      An optional list of additional policy documents to include in the simulation. Each document is specified as a string containing the complete, valid JSON text of an IAM policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
      - *(string) --* 

      
  
    :type ActionNames: list
    :param ActionNames: **[REQUIRED]** 

      A list of names of API actions to evaluate in the simulation. Each action is evaluated for each resource. Each action must include the service identifier, such as ``iam:CreateUser`` .

      

    
      - *(string) --* 

      
  
    :type ResourceArns: list
    :param ResourceArns: 

      A list of ARNs of AWS resources to include in the simulation. If this parameter is not provided then the value defaults to ``*`` (all resources). Each API in the ``ActionNames`` parameter is evaluated for each resource in this list. The simulation determines the access result (allowed or denied) of each combination and reports it in the response.

       

      The simulation does not automatically retrieve policies for the specified resources. If you want to include a resource policy in the simulation, then you must include the policy as a string in the ``ResourcePolicy`` parameter.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
      - *(string) --* 

      
  
    :type ResourcePolicy: string
    :param ResourcePolicy: 

      A resource-based policy to include in the simulation provided as a string. Each resource in the simulation is treated as if it had this policy attached. You can include only one resource-based policy in a simulation.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type ResourceOwner: string
    :param ResourceOwner: 

      An AWS account ID that specifies the owner of any simulated resource that does not identify its owner in the resource ARN, such as an S3 bucket or object. If ``ResourceOwner`` is specified, it is also used as the account owner of any ``ResourcePolicy`` included in the simulation. If the ``ResourceOwner`` parameter is not specified, then the owner of the resources and the resource policy defaults to the account of the identity provided in ``CallerArn`` . This parameter is required only if you specify a resource-based policy and account that owns the resource is different from the account that owns the simulated calling user ``CallerArn`` .

      

    
    :type CallerArn: string
    :param CallerArn: 

      The ARN of the IAM user that you want to specify as the simulated caller of the APIs. If you do not specify a ``CallerArn`` , it defaults to the ARN of the user that you specify in ``PolicySourceArn`` , if you specified a user. If you include both a ``PolicySourceArn`` (for example, ``arn:aws:iam::123456789012:user/David`` ) and a ``CallerArn`` (for example, ``arn:aws:iam::123456789012:user/Bob`` ), the result is that you simulate calling the APIs as Bob, as if Bob had David's policies.

       

      You can specify only the ARN of an IAM user. You cannot specify the ARN of an assumed role, federated user, or a service principal.

       

       ``CallerArn`` is required if you include a ``ResourcePolicy`` and the ``PolicySourceArn`` is not the ARN for an IAM user. This is required so that the resource-based policy's ``Principal`` element has a value to use in evaluating the policy.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type ContextEntries: list
    :param ContextEntries: 

      A list of context keys and corresponding values for the simulation to use. Whenever a context key is evaluated in one of the simulated IAM permission policies, the corresponding value is supplied.

      

    
      - *(dict) --* 

        Contains information about a condition context key. It includes the name of the key and specifies the value (or values, if the context key supports multiple values) to use in the simulation. This information is used when evaluating the ``Condition`` elements of the input policies.

         

        This data type is used as an input parameter to ``  SimulateCustomPolicy `` and ``  SimulateCustomPolicy `` .

        

      
        - **ContextKeyName** *(string) --* 

          The full name of a condition context key, including the service prefix. For example, ``aws:SourceIp`` or ``s3:VersionId`` .

          

        
        - **ContextKeyValues** *(list) --* 

          The value (or values, if the condition context key supports multiple values) to provide to the simulation for use when the key is referenced by a ``Condition`` element in an input policy.

          

        
          - *(string) --* 

          
      
        - **ContextKeyType** *(string) --* 

          The data type of the value (or values) specified in the ``ContextKeyValues`` parameter.

          

        
      
  
    :type ResourceHandlingOption: string
    :param ResourceHandlingOption: 

      Specifies the type of simulation to run. Different APIs that support resource-based policies require different combinations of resources. By specifying the type of simulation to run, you enable the policy simulator to enforce the presence of the required resources to ensure reliable simulation results. If your simulation does not match one of the following scenarios, then you can omit this parameter. The following list shows each of the supported scenario values and the resources that you must define to run the simulation.

       

      Each of the EC2 scenarios requires that you specify instance, image, and security-group resources. If your scenario includes an EBS volume, then you must specify that volume as a resource. If the EC2 scenario includes VPC, then you must supply the network-interface resource. If it includes an IP subnet, then you must specify the subnet resource. For more information on the EC2 scenario options, see `Supported Platforms`_ in the *AWS EC2 User Guide* .

       

       
      * **EC2-Classic-InstanceStore**   instance, image, security-group 
       
      * **EC2-Classic-EBS**   instance, image, security-group, volume 
       
      * **EC2-VPC-InstanceStore**   instance, image, security-group, network-interface 
       
      * **EC2-VPC-InstanceStore-Subnet**   instance, image, security-group, network-interface, subnet 
       
      * **EC2-VPC-EBS**   instance, image, security-group, network-interface, volume 
       
      * **EC2-VPC-EBS-Subnet**   instance, image, security-group, network-interface, subnet, volume 
       

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

       

      This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

      

    
    :type Marker: string
    :param Marker: 

      Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'EvaluationResults': [
                {
                    'EvalActionName': 'string',
                    'EvalResourceName': 'string',
                    'EvalDecision': 'allowed'|'explicitDeny'|'implicitDeny',
                    'MatchedStatements': [
                        {
                            'SourcePolicyId': 'string',
                            'SourcePolicyType': 'user'|'group'|'role'|'aws-managed'|'user-managed'|'resource'|'none',
                            'StartPosition': {
                                'Line': 123,
                                'Column': 123
                            },
                            'EndPosition': {
                                'Line': 123,
                                'Column': 123
                            }
                        },
                    ],
                    'MissingContextValues': [
                        'string',
                    ],
                    'EvalDecisionDetails': {
                        'string': 'allowed'|'explicitDeny'|'implicitDeny'
                    },
                    'ResourceSpecificResults': [
                        {
                            'EvalResourceName': 'string',
                            'EvalResourceDecision': 'allowed'|'explicitDeny'|'implicitDeny',
                            'MatchedStatements': [
                                {
                                    'SourcePolicyId': 'string',
                                    'SourcePolicyType': 'user'|'group'|'role'|'aws-managed'|'user-managed'|'resource'|'none',
                                    'StartPosition': {
                                        'Line': 123,
                                        'Column': 123
                                    },
                                    'EndPosition': {
                                        'Line': 123,
                                        'Column': 123
                                    }
                                },
                            ],
                            'MissingContextValues': [
                                'string',
                            ],
                            'EvalDecisionDetails': {
                                'string': 'allowed'|'explicitDeny'|'implicitDeny'
                            }
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'Marker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  SimulatePrincipalPolicy or  SimulateCustomPolicy request.

        
        

        - **EvaluationResults** *(list) --* 

          The results of the simulation.

          
          

          - *(dict) --* 

            Contains the results of a simulation.

             

            This data type is used by the return parameter of ``  SimulateCustomPolicy `` and ``  SimulatePrincipalPolicy `` .

            
            

            - **EvalActionName** *(string) --* 

              The name of the API action tested on the indicated resource.

              
            

            - **EvalResourceName** *(string) --* 

              The ARN of the resource that the indicated API action was tested on.

              
            

            - **EvalDecision** *(string) --* 

              The result of the simulation.

              
            

            - **MatchedStatements** *(list) --* 

              A list of the statements in the input policies that determine the result for this scenario. Remember that even if multiple statements allow the action on the resource, if only one statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

              
              

              - *(dict) --* 

                Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

                 

                This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

                
                

                - **SourcePolicyId** *(string) --* 

                  The identifier of the policy that was provided as an input.

                  
                

                - **SourcePolicyType** *(string) --* 

                  The type of the policy.

                  
                

                - **StartPosition** *(dict) --* 

                  The row and column of the beginning of the ``Statement`` in an IAM policy.

                  
                  

                  - **Line** *(integer) --* 

                    The line containing the specified position in the document.

                    
                  

                  - **Column** *(integer) --* 

                    The column in the line containing the specified position in the document.

                    
              
                

                - **EndPosition** *(dict) --* 

                  The row and column of the end of a ``Statement`` in an IAM policy.

                  
                  

                  - **Line** *(integer) --* 

                    The line containing the specified position in the document.

                    
                  

                  - **Column** *(integer) --* 

                    The column in the line containing the specified position in the document.

                    
              
            
          
            

            - **MissingContextValues** *(list) --* 

              A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when the resource in a simulation is "*", either explicitly, or when the ``ResourceArns`` parameter blank. If you include a list of resources, then any missing context values are instead included under the ``ResourceSpecificResults`` section. To discover the context keys used by a set of policies, you can call  GetContextKeysForCustomPolicy or  GetContextKeysForPrincipalPolicy .

              
              

              - *(string) --* 
          
            

            - **EvalDecisionDetails** *(dict) --* 

              Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access. See `How IAM Roles Differ from Resource-based Policies`_  

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
            

            - **ResourceSpecificResults** *(list) --* 

              The individual results of the simulation of the API action specified in EvalActionName on each resource.

              
              

              - *(dict) --* 

                Contains the result of the simulation of a single API action call on a single resource.

                 

                This data type is used by a member of the  EvaluationResult data type.

                
                

                - **EvalResourceName** *(string) --* 

                  The name of the simulated resource, in Amazon Resource Name (ARN) format.

                  
                

                - **EvalResourceDecision** *(string) --* 

                  The result of the simulation of the simulated API action on the resource specified in ``EvalResourceName`` .

                  
                

                - **MatchedStatements** *(list) --* 

                  A list of the statements in the input policies that determine the result for this part of the simulation. Remember that even if multiple statements allow the action on the resource, if *any* statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

                  
                  

                  - *(dict) --* 

                    Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

                     

                    This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

                    
                    

                    - **SourcePolicyId** *(string) --* 

                      The identifier of the policy that was provided as an input.

                      
                    

                    - **SourcePolicyType** *(string) --* 

                      The type of the policy.

                      
                    

                    - **StartPosition** *(dict) --* 

                      The row and column of the beginning of the ``Statement`` in an IAM policy.

                      
                      

                      - **Line** *(integer) --* 

                        The line containing the specified position in the document.

                        
                      

                      - **Column** *(integer) --* 

                        The column in the line containing the specified position in the document.

                        
                  
                    

                    - **EndPosition** *(dict) --* 

                      The row and column of the end of a ``Statement`` in an IAM policy.

                      
                      

                      - **Line** *(integer) --* 

                        The line containing the specified position in the document.

                        
                      

                      - **Column** *(integer) --* 

                        The column in the line containing the specified position in the document.

                        
                  
                
              
                

                - **MissingContextValues** *(list) --* 

                  A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when a list of ARNs is included in the ``ResourceArns`` parameter instead of "*". If you do not specify individual resources, by setting ``ResourceArns`` to "*" or by not including the ``ResourceArns`` parameter, then any missing context values are instead included under the ``EvaluationResults`` section. To discover the context keys used by a set of policies, you can call  GetContextKeysForCustomPolicy or  GetContextKeysForPrincipalPolicy .

                  
                  

                  - *(string) --* 
              
                

                - **EvalDecisionDetails** *(dict) --* 

                  Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **Marker** *(string) --* 

          When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

          
    

  .. py:method:: update_access_key(**kwargs)

    

    Changes the status of the specified access key from Active to Inactive, or vice versa. This action can be used to disable a user's key as part of a key rotation work flow.

     

    If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    For information about rotating keys, see `Managing Keys and Certificates`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.update_access_key(
          UserName='string',
          AccessKeyId='string',
          Status='Active'|'Inactive'
      )
    :type UserName: string
    :param UserName: 

      The name of the user whose key you want to update.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type AccessKeyId: string
    :param AccessKeyId: **[REQUIRED]** 

      The access key ID of the secret access key you want to update.

       

      The `regex pattern`_ for this parameter is a string of characters that can consist of any upper or lowercased letter or digit.

      

    
    :type Status: string
    :param Status: **[REQUIRED]** 

      The status you want to assign to the secret access key. ``Active`` means the key can be used for API calls to AWS, while ``Inactive`` means the key cannot be used.

      

    
    
    :returns: None

  .. py:method:: update_account_password_policy(**kwargs)

    

    Updates the password policy settings for the AWS account.

     

    .. note::

       

      This action does not support partial updates. No parameters are required, but if you do not specify a parameter, that parameter's value reverts to its default value. See the **Request Parameters** section for each parameter's default value.

       

     

    For more information about using a password policy, see `Managing an IAM Password Policy`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.update_account_password_policy(
          MinimumPasswordLength=123,
          RequireSymbols=True|False,
          RequireNumbers=True|False,
          RequireUppercaseCharacters=True|False,
          RequireLowercaseCharacters=True|False,
          AllowUsersToChangePassword=True|False,
          MaxPasswordAge=123,
          PasswordReusePrevention=123,
          HardExpiry=True|False
      )
    :type MinimumPasswordLength: integer
    :param MinimumPasswordLength: 

      The minimum number of characters allowed in an IAM user password.

       

      Default value: 6

      

    
    :type RequireSymbols: boolean
    :param RequireSymbols: 

      Specifies whether IAM user passwords must contain at least one of the following non-alphanumeric characters:

       

      ! @ # $ % ^ amp; * ( ) _ + - = [ ] { } | '

       

      Default value: false

      

    
    :type RequireNumbers: boolean
    :param RequireNumbers: 

      Specifies whether IAM user passwords must contain at least one numeric character (0 to 9).

       

      Default value: false

      

    
    :type RequireUppercaseCharacters: boolean
    :param RequireUppercaseCharacters: 

      Specifies whether IAM user passwords must contain at least one uppercase character from the ISO basic Latin alphabet (A to Z).

       

      Default value: false

      

    
    :type RequireLowercaseCharacters: boolean
    :param RequireLowercaseCharacters: 

      Specifies whether IAM user passwords must contain at least one lowercase character from the ISO basic Latin alphabet (a to z).

       

      Default value: false

      

    
    :type AllowUsersToChangePassword: boolean
    :param AllowUsersToChangePassword: 

      Allows all IAM users in your account to use the AWS Management Console to change their own passwords. For more information, see `Letting IAM Users Change Their Own Passwords`_ in the *IAM User Guide* .

       

      Default value: false

      

    
    :type MaxPasswordAge: integer
    :param MaxPasswordAge: 

      The number of days that an IAM user password is valid. The default value of 0 means IAM user passwords never expire.

       

      Default value: 0

      

    
    :type PasswordReusePrevention: integer
    :param PasswordReusePrevention: 

      Specifies the number of previous passwords that IAM users are prevented from reusing. The default value of 0 means IAM users are not prevented from reusing previous passwords.

       

      Default value: 0

      

    
    :type HardExpiry: boolean
    :param HardExpiry: 

      Prevents IAM users from setting a new password after their password has expired.

       

      Default value: false

      

    
    
    :returns: None

  .. py:method:: update_assume_role_policy(**kwargs)

    

    Updates the policy that grants an IAM entity permission to assume a role. This is typically referred to as the "role trust policy". For more information about roles, go to `Using Roles to Delegate Permissions and Federate Identities`_ .

    

    **Request Syntax** 
    ::

      response = client.update_assume_role_policy(
          RoleName='string',
          PolicyDocument='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to update with the new policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy that grants an entity permission to assume the role.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :returns: None

  .. py:method:: update_group(**kwargs)

    

    Updates the name and/or the path of the specified IAM group.

     

    .. warning::

       

      You should understand the implications of changing a group's path or name. For more information, see `Renaming Users and Groups`_ in the *IAM User Guide* .

       

     

    .. note::

       

      To change an IAM group name the requester must have appropriate permissions on both the source object and the target object. For example, to change "Managers" to "MGRs", the entity making the request must have permission on both "Managers" and "MGRs", or must have permission on all (*). For more information about permissions, see `Permissions and Policies`_ . 

       

    

    **Request Syntax** 
    ::

      response = client.update_group(
          GroupName='string',
          NewPath='string',
          NewGroupName='string'
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      Name of the IAM group to update. If you're changing the name of the group, this is the original name.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type NewPath: string
    :param NewPath: 

      New path for the IAM group. Only include this if changing the group's path.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type NewGroupName: string
    :param NewGroupName: 

      New name for the IAM group. Only include this if changing the group's name.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: update_login_profile(**kwargs)

    

    Changes the password for the specified IAM user.

     

    IAM users can change their own passwords by calling  ChangePassword . For more information about modifying passwords, see `Managing Passwords`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = client.update_login_profile(
          UserName='string',
          Password='string',
          PasswordResetRequired=True|False
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user whose password you want to update.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Password: string
    :param Password: 

      The new password for the specified IAM user.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D). However, the format can be further restricted by the account administrator by setting a password policy on the AWS account. For more information, see  UpdateAccountPasswordPolicy .

      

    
    :type PasswordResetRequired: boolean
    :param PasswordResetRequired: 

      Allows this new password to be used only once by requiring the specified IAM user to set a new password on next sign-in.

      

    
    
    :returns: None

  .. py:method:: update_open_id_connect_provider_thumbprint(**kwargs)

    

    Replaces the existing list of server certificate thumbprints associated with an OpenID Connect (OIDC) provider resource object with a new list of thumbprints.

     

    The list that you pass with this action completely replaces the existing list of thumbprints. (The lists are not merged.)

     

    Typically, you need to update a thumbprint only when the identity provider's certificate changes, which occurs rarely. However, if the provider's certificate *does* change, any attempt to assume an IAM role that specifies the OIDC provider as a principal fails until the certificate thumbprint is updated.

     

    .. note::

       

      Because trust for the OIDC provider is ultimately derived from the provider's certificate and is validated by the thumbprint, it is a best practice to limit access to the ``UpdateOpenIDConnectProviderThumbprint`` action to highly-privileged users.

       

    

    **Request Syntax** 
    ::

      response = client.update_open_id_connect_provider_thumbprint(
          OpenIDConnectProviderArn='string',
          ThumbprintList=[
              'string',
          ]
      )
    :type OpenIDConnectProviderArn: string
    :param OpenIDConnectProviderArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM OIDC provider resource object for which you want to update the thumbprint. You can get a list of OIDC provider ARNs by using the  ListOpenIDConnectProviders action.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type ThumbprintList: list
    :param ThumbprintList: **[REQUIRED]** 

      A list of certificate thumbprints that are associated with the specified IAM OpenID Connect provider. For more information, see  CreateOpenIDConnectProvider . 

      

    
      - *(string) --* 

        Contains a thumbprint for an identity provider's server certificate.

         

        The identity provider's server certificate thumbprint is the hex-encoded SHA-1 hash value of the self-signed X.509 certificate used by the domain where the OpenID Connect provider makes its keys available. It is always a 40-character string.

        

      
  
    
    :returns: None

  .. py:method:: update_saml_provider(**kwargs)

    

    Updates the metadata document for an existing SAML provider resource object.

     

    .. note::

       

      This operation requires `Signature Version 4`_ .

       

    

    **Request Syntax** 
    ::

      response = client.update_saml_provider(
          SAMLMetadataDocument='string',
          SAMLProviderArn='string'
      )
    :type SAMLMetadataDocument: string
    :param SAMLMetadataDocument: **[REQUIRED]** 

      An XML document generated by an identity provider (IdP) that supports SAML 2.0. The document includes the issuer's name, expiration information, and keys that can be used to validate the SAML authentication response (assertions) that are received from the IdP. You must generate the metadata document using the identity management software that is used as your organization's IdP.

      

    
    :type SAMLProviderArn: string
    :param SAMLProviderArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the SAML provider to update.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SAMLProviderArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  UpdateSAMLProvider request. 

        
        

        - **SAMLProviderArn** *(string) --* 

          The Amazon Resource Name (ARN) of the SAML provider that was updated.

          
    

  .. py:method:: update_server_certificate(**kwargs)

    

    Updates the name and/or the path of the specified server certificate stored in IAM.

     

    For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

     

    .. warning::

       

      You should understand the implications of changing a server certificate's path or name. For more information, see `Renaming a Server Certificate`_ in the *IAM User Guide* .

       

     

    .. note::

       

      To change a server certificate name the requester must have appropriate permissions on both the source object and the target object. For example, to change the name from "ProductionCert" to "ProdCert", the entity making the request must have permission on "ProductionCert" and "ProdCert", or must have permission on all (*). For more information about permissions, see `Access Management`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      response = client.update_server_certificate(
          ServerCertificateName='string',
          NewPath='string',
          NewServerCertificateName='string'
      )
    :type ServerCertificateName: string
    :param ServerCertificateName: **[REQUIRED]** 

      The name of the server certificate that you want to update.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type NewPath: string
    :param NewPath: 

      The new path for the server certificate. Include this only if you are updating the server certificate's path.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type NewServerCertificateName: string
    :param NewServerCertificateName: 

      The new name for the server certificate. Include this only if you are updating the server certificate's name. The name of the certificate cannot contain any spaces.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: update_signing_certificate(**kwargs)

    

    Changes the status of the specified user signing certificate from active to disabled, or vice versa. This action can be used to disable an IAM user's signing certificate as part of a certificate rotation work flow.

     

    If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

    

    **Request Syntax** 
    ::

      response = client.update_signing_certificate(
          UserName='string',
          CertificateId='string',
          Status='Active'|'Inactive'
      )
    :type UserName: string
    :param UserName: 

      The name of the IAM user the signing certificate belongs to.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type CertificateId: string
    :param CertificateId: **[REQUIRED]** 

      The ID of the signing certificate you want to update.

       

      The `regex pattern`_ for this parameter is a string of characters that can consist of any upper or lowercased letter or digit.

      

    
    :type Status: string
    :param Status: **[REQUIRED]** 

      The status you want to assign to the certificate. ``Active`` means the certificate can be used for API calls to AWS, while ``Inactive`` means the certificate cannot be used.

      

    
    
    :returns: None

  .. py:method:: update_ssh_public_key(**kwargs)

    

    Sets the status of an IAM user's SSH public key to active or inactive. SSH public keys that are inactive cannot be used for authentication. This action can be used to disable a user's SSH public key as part of a key rotation work flow.

     

    The SSH public key affected by this action is used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .

    

    **Request Syntax** 
    ::

      response = client.update_ssh_public_key(
          UserName='string',
          SSHPublicKeyId='string',
          Status='Active'|'Inactive'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the IAM user associated with the SSH public key.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type SSHPublicKeyId: string
    :param SSHPublicKeyId: **[REQUIRED]** 

      The unique identifier for the SSH public key.

       

      The `regex pattern`_ for this parameter is a string of characters that can consist of any upper or lowercased letter or digit.

      

    
    :type Status: string
    :param Status: **[REQUIRED]** 

      The status to assign to the SSH public key. ``Active`` means the key can be used for authentication with an AWS CodeCommit repository. ``Inactive`` means the key cannot be used.

      

    
    
    :returns: None

  .. py:method:: update_user(**kwargs)

    

    Updates the name and/or the path of the specified IAM user.

     

    .. warning::

       

      You should understand the implications of changing an IAM user's path or name. For more information, see `Renaming an IAM User`_ and `Renaming an IAM Group`_ in the *IAM User Guide* .

       

     

    .. note::

       

      To change a user name the requester must have appropriate permissions on both the source object and the target object. For example, to change Bob to Robert, the entity making the request must have permission on Bob and Robert, or must have permission on all (*). For more information about permissions, see `Permissions and Policies`_ . 

       

    

    **Request Syntax** 
    ::

      response = client.update_user(
          UserName='string',
          NewPath='string',
          NewUserName='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      Name of the user to update. If you're changing the name of the user, this is the original user name.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type NewPath: string
    :param NewPath: 

      New path for the IAM user. Include this parameter only if you're changing the user's path.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type NewUserName: string
    :param NewUserName: 

      New name for the user. Include this parameter only if you're changing the user's name.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: upload_server_certificate(**kwargs)

    

    Uploads a server certificate entity for the AWS account. The server certificate entity includes a public key certificate, a private key, and an optional certificate chain, which should all be PEM-encoded.

     

    For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

     

    For information about the number of server certificates you can upload, see `Limitations on IAM Entities and Objects`_ in the *IAM User Guide* .

     

    .. note::

       

      Because the body of the public key certificate, private key, and the certificate chain can be large, you should use POST rather than GET when calling ``UploadServerCertificate`` . For information about setting up signatures and authorization through the API, go to `Signing AWS API Requests`_ in the *AWS General Reference* . For general information about using the Query API with IAM, go to `Calling the API by Making HTTP Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      response = client.upload_server_certificate(
          Path='string',
          ServerCertificateName='string',
          CertificateBody='string',
          PrivateKey='string',
          CertificateChain='string'
      )
    :type Path: string
    :param Path: 

      The path for the server certificate. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/). The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

       

      .. note::

         

        If you are uploading a server certificate specifically for use with Amazon CloudFront distributions, you must specify a path using the ``--path`` option. The path must begin with ``/cloudfront`` and must include a trailing slash (for example, ``/cloudfront/test/`` ).

         

      

    
    :type ServerCertificateName: string
    :param ServerCertificateName: **[REQUIRED]** 

      The name for the server certificate. Do not include the path in this value. The name of the certificate cannot contain any spaces.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type CertificateBody: string
    :param CertificateBody: **[REQUIRED]** 

      The contents of the public key certificate in PEM-encoded format.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type PrivateKey: string
    :param PrivateKey: **[REQUIRED]** 

      The contents of the private key in PEM-encoded format.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type CertificateChain: string
    :param CertificateChain: 

      The contents of the certificate chain. This is typically a concatenation of the PEM-encoded public key certificates of the chain.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ServerCertificateMetadata': {
                'Path': 'string',
                'ServerCertificateName': 'string',
                'ServerCertificateId': 'string',
                'Arn': 'string',
                'UploadDate': datetime(2015, 1, 1),
                'Expiration': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  UploadServerCertificate request. 

        
        

        - **ServerCertificateMetadata** *(dict) --* 

          The meta information of the uploaded server certificate without its certificate body, certificate chain, and private key.

          
          

          - **Path** *(string) --* 

            The path to the server certificate. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **ServerCertificateName** *(string) --* 

            The name that identifies the server certificate.

            
          

          - **ServerCertificateId** *(string) --* 

            The stable and unique string identifying the server certificate. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) specifying the server certificate. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **UploadDate** *(datetime) --* 

            The date when the server certificate was uploaded.

            
          

          - **Expiration** *(datetime) --* 

            The date on which the certificate is set to expire.

            
      
    

  .. py:method:: upload_signing_certificate(**kwargs)

    

    Uploads an X.509 signing certificate and associates it with the specified IAM user. Some AWS services use X.509 signing certificates to validate requests that are signed with a corresponding private key. When you upload the certificate, its default status is ``Active`` .

     

    If the ``UserName`` field is not specified, the IAM user name is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    .. note::

       

      Because the body of a X.509 certificate can be large, you should use POST rather than GET when calling ``UploadSigningCertificate`` . For information about setting up signatures and authorization through the API, go to `Signing AWS API Requests`_ in the *AWS General Reference* . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      response = client.upload_signing_certificate(
          UserName='string',
          CertificateBody='string'
      )
    :type UserName: string
    :param UserName: 

      The name of the user the signing certificate is for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type CertificateBody: string
    :param CertificateBody: **[REQUIRED]** 

      The contents of the signing certificate.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Certificate': {
                'UserName': 'string',
                'CertificateId': 'string',
                'CertificateBody': 'string',
                'Status': 'Active'|'Inactive',
                'UploadDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  UploadSigningCertificate request. 

        
        

        - **Certificate** *(dict) --* 

          Information about the certificate.

          
          

          - **UserName** *(string) --* 

            The name of the user the signing certificate is associated with.

            
          

          - **CertificateId** *(string) --* 

            The ID for the signing certificate.

            
          

          - **CertificateBody** *(string) --* 

            The contents of the signing certificate.

            
          

          - **Status** *(string) --* 

            The status of the signing certificate. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not.

            
          

          - **UploadDate** *(datetime) --* 

            The date when the signing certificate was uploaded.

            
      
    

  .. py:method:: upload_ssh_public_key(**kwargs)

    

    Uploads an SSH public key and associates it with the specified IAM user.

     

    The SSH public key uploaded by this action can be used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .

    

    **Request Syntax** 
    ::

      response = client.upload_ssh_public_key(
          UserName='string',
          SSHPublicKeyBody='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the IAM user to associate the SSH public key with.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type SSHPublicKeyBody: string
    :param SSHPublicKeyBody: **[REQUIRED]** 

      The SSH public key. The public key must be encoded in ssh-rsa format or PEM format.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SSHPublicKey': {
                'UserName': 'string',
                'SSHPublicKeyId': 'string',
                'Fingerprint': 'string',
                'SSHPublicKeyBody': 'string',
                'Status': 'Active'|'Inactive',
                'UploadDate': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  UploadSSHPublicKey request.

        
        

        - **SSHPublicKey** *(dict) --* 

          Contains information about the SSH public key.

          
          

          - **UserName** *(string) --* 

            The name of the IAM user associated with the SSH public key.

            
          

          - **SSHPublicKeyId** *(string) --* 

            The unique identifier for the SSH public key.

            
          

          - **Fingerprint** *(string) --* 

            The MD5 message digest of the SSH public key.

            
          

          - **SSHPublicKeyBody** *(string) --* 

            The SSH public key.

            
          

          - **Status** *(string) --* 

            The status of the SSH public key. ``Active`` means the key can be used for authentication with an AWS CodeCommit repository. ``Inactive`` means the key cannot be used.

            
          

          - **UploadDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the SSH public key was uploaded.

            
      
    

==========
Paginators
==========


The available paginators are:

* :py:class:`IAM.Paginator.GetAccountAuthorizationDetails`


* :py:class:`IAM.Paginator.GetGroup`


* :py:class:`IAM.Paginator.ListAccessKeys`


* :py:class:`IAM.Paginator.ListAccountAliases`


* :py:class:`IAM.Paginator.ListAttachedGroupPolicies`


* :py:class:`IAM.Paginator.ListAttachedRolePolicies`


* :py:class:`IAM.Paginator.ListAttachedUserPolicies`


* :py:class:`IAM.Paginator.ListEntitiesForPolicy`


* :py:class:`IAM.Paginator.ListGroupPolicies`


* :py:class:`IAM.Paginator.ListGroups`


* :py:class:`IAM.Paginator.ListGroupsForUser`


* :py:class:`IAM.Paginator.ListInstanceProfiles`


* :py:class:`IAM.Paginator.ListInstanceProfilesForRole`


* :py:class:`IAM.Paginator.ListMFADevices`


* :py:class:`IAM.Paginator.ListPolicies`


* :py:class:`IAM.Paginator.ListPolicyVersions`


* :py:class:`IAM.Paginator.ListRolePolicies`


* :py:class:`IAM.Paginator.ListRoles`


* :py:class:`IAM.Paginator.ListSSHPublicKeys`


* :py:class:`IAM.Paginator.ListServerCertificates`


* :py:class:`IAM.Paginator.ListSigningCertificates`


* :py:class:`IAM.Paginator.ListUserPolicies`


* :py:class:`IAM.Paginator.ListUsers`


* :py:class:`IAM.Paginator.ListVirtualMFADevices`


* :py:class:`IAM.Paginator.SimulateCustomPolicy`


* :py:class:`IAM.Paginator.SimulatePrincipalPolicy`



.. py:class:: IAM.Paginator.GetAccountAuthorizationDetails

  ::

    
    paginator = client.get_paginator('get_account_authorization_details')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.get_account_authorization_details`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          Filter=[
              'User'|'Role'|'Group'|'LocalManagedPolicy'|'AWSManagedPolicy',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type Filter: list
    :param Filter: 

      A list of entity types used to filter the results. Only the entities that match the types you specify are included in the output. Use the value ``LocalManagedPolicy`` to include customer managed policies.

       

      The format for this parameter is a comma-separated (if more than one) list of strings. Each string value in the list must be one of the valid values listed below.

      

    
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
            'UserDetailList': [
                {
                    'Path': 'string',
                    'UserName': 'string',
                    'UserId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'UserPolicyList': [
                        {
                            'PolicyName': 'string',
                            'PolicyDocument': 'string'
                        },
                    ],
                    'GroupList': [
                        'string',
                    ],
                    'AttachedManagedPolicies': [
                        {
                            'PolicyName': 'string',
                            'PolicyArn': 'string'
                        },
                    ]
                },
            ],
            'GroupDetailList': [
                {
                    'Path': 'string',
                    'GroupName': 'string',
                    'GroupId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'GroupPolicyList': [
                        {
                            'PolicyName': 'string',
                            'PolicyDocument': 'string'
                        },
                    ],
                    'AttachedManagedPolicies': [
                        {
                            'PolicyName': 'string',
                            'PolicyArn': 'string'
                        },
                    ]
                },
            ],
            'RoleDetailList': [
                {
                    'Path': 'string',
                    'RoleName': 'string',
                    'RoleId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'AssumeRolePolicyDocument': 'string',
                    'InstanceProfileList': [
                        {
                            'Path': 'string',
                            'InstanceProfileName': 'string',
                            'InstanceProfileId': 'string',
                            'Arn': 'string',
                            'CreateDate': datetime(2015, 1, 1),
                            'Roles': [
                                {
                                    'Path': 'string',
                                    'RoleName': 'string',
                                    'RoleId': 'string',
                                    'Arn': 'string',
                                    'CreateDate': datetime(2015, 1, 1),
                                    'AssumeRolePolicyDocument': 'string'
                                },
                            ]
                        },
                    ],
                    'RolePolicyList': [
                        {
                            'PolicyName': 'string',
                            'PolicyDocument': 'string'
                        },
                    ],
                    'AttachedManagedPolicies': [
                        {
                            'PolicyName': 'string',
                            'PolicyArn': 'string'
                        },
                    ]
                },
            ],
            'Policies': [
                {
                    'PolicyName': 'string',
                    'PolicyId': 'string',
                    'Arn': 'string',
                    'Path': 'string',
                    'DefaultVersionId': 'string',
                    'AttachmentCount': 123,
                    'IsAttachable': True|False,
                    'Description': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'UpdateDate': datetime(2015, 1, 1),
                    'PolicyVersionList': [
                        {
                            'Document': 'string',
                            'VersionId': 'string',
                            'IsDefaultVersion': True|False,
                            'CreateDate': datetime(2015, 1, 1)
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetAccountAuthorizationDetails request. 

        
        

        - **UserDetailList** *(list) --* 

          A list containing information about IAM users.

          
          

          - *(dict) --* 

            Contains information about an IAM user, including all the user's policies and all the IAM groups the user is in.

             

            This data type is used as a response element in the  GetAccountAuthorizationDetails action.

            
            

            - **Path** *(string) --* 

              The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **UserName** *(string) --* 

              The friendly name identifying the user.

              
            

            - **UserId** *(string) --* 

              The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user was created.

              
            

            - **UserPolicyList** *(list) --* 

              A list of the inline policies embedded in the user.

              
              

              - *(dict) --* 

                Contains information about an IAM policy, including the policy document.

                 

                This data type is used as a response element in the  GetAccountAuthorizationDetails action.

                
                

                - **PolicyName** *(string) --* 

                  The name of the policy.

                  
                

                - **PolicyDocument** *(string) --* 

                  The policy document.

                  
            
          
            

            - **GroupList** *(list) --* 

              A list of IAM groups that the user is in.

              
              

              - *(string) --* 
          
            

            - **AttachedManagedPolicies** *(list) --* 

              A list of the managed policies attached to the user.

              
              

              - *(dict) --* 

                Contains information about an attached policy.

                 

                An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

                 

                For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

                
                

                - **PolicyName** *(string) --* 

                  The friendly name of the attached policy.

                  
                

                - **PolicyArn** *(string) --* 

                  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

                   

                  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

                  
            
          
        
      
        

        - **GroupDetailList** *(list) --* 

          A list containing information about IAM groups.

          
          

          - *(dict) --* 

            Contains information about an IAM group, including all of the group's policies.

             

            This data type is used as a response element in the  GetAccountAuthorizationDetails action.

            
            

            - **Path** *(string) --* 

              The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **GroupName** *(string) --* 

              The friendly name that identifies the group.

              
            

            - **GroupId** *(string) --* 

              The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the group was created.

              
            

            - **GroupPolicyList** *(list) --* 

              A list of the inline policies embedded in the group.

              
              

              - *(dict) --* 

                Contains information about an IAM policy, including the policy document.

                 

                This data type is used as a response element in the  GetAccountAuthorizationDetails action.

                
                

                - **PolicyName** *(string) --* 

                  The name of the policy.

                  
                

                - **PolicyDocument** *(string) --* 

                  The policy document.

                  
            
          
            

            - **AttachedManagedPolicies** *(list) --* 

              A list of the managed policies attached to the group.

              
              

              - *(dict) --* 

                Contains information about an attached policy.

                 

                An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

                 

                For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

                
                

                - **PolicyName** *(string) --* 

                  The friendly name of the attached policy.

                  
                

                - **PolicyArn** *(string) --* 

                  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

                   

                  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

                  
            
          
        
      
        

        - **RoleDetailList** *(list) --* 

          A list containing information about IAM roles.

          
          

          - *(dict) --* 

            Contains information about an IAM role, including all of the role's policies.

             

            This data type is used as a response element in the  GetAccountAuthorizationDetails action.

            
            

            - **Path** *(string) --* 

              The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **RoleName** *(string) --* 

              The friendly name that identifies the role.

              
            

            - **RoleId** *(string) --* 

              The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the role was created.

              
            

            - **AssumeRolePolicyDocument** *(string) --* 

              The trust policy that grants permission to assume the role.

              
            

            - **InstanceProfileList** *(list) --* 

              Contains a list of instance profiles.

              
              

              - *(dict) --* 

                Contains information about an instance profile.

                 

                This data type is used as a response element in the following actions:

                 

                 
                *  CreateInstanceProfile   
                 
                *  GetInstanceProfile   
                 
                *  ListInstanceProfiles   
                 
                *  ListInstanceProfilesForRole   
                 

                
                

                - **Path** *(string) --* 

                  The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **InstanceProfileName** *(string) --* 

                  The name identifying the instance profile.

                  
                

                - **InstanceProfileId** *(string) --* 

                  The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **Arn** *(string) --* 

                  The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **CreateDate** *(datetime) --* 

                  The date when the instance profile was created.

                  
                

                - **Roles** *(list) --* 

                  The role associated with the instance profile.

                  
                  

                  - *(dict) --* 

                    Contains information about an IAM role.

                     

                    This data type is used as a response element in the following actions:

                     

                     
                    *  CreateRole   
                     
                    *  GetRole   
                     
                    *  ListRoles   
                     

                    
                    

                    - **Path** *(string) --* 

                      The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                      
                    

                    - **RoleName** *(string) --* 

                      The friendly name that identifies the role.

                      
                    

                    - **RoleId** *(string) --* 

                      The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                      
                    

                    - **Arn** *(string) --* 

                      The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                      
                    

                    - **CreateDate** *(datetime) --* 

                      The date and time, in `ISO 8601 date-time format`_ , when the role was created.

                      
                    

                    - **AssumeRolePolicyDocument** *(string) --* 

                      The policy that grants an entity permission to assume the role.

                      
                
              
            
          
            

            - **RolePolicyList** *(list) --* 

              A list of inline policies embedded in the role. These policies are the role's access (permissions) policies.

              
              

              - *(dict) --* 

                Contains information about an IAM policy, including the policy document.

                 

                This data type is used as a response element in the  GetAccountAuthorizationDetails action.

                
                

                - **PolicyName** *(string) --* 

                  The name of the policy.

                  
                

                - **PolicyDocument** *(string) --* 

                  The policy document.

                  
            
          
            

            - **AttachedManagedPolicies** *(list) --* 

              A list of managed policies attached to the role. These policies are the role's access (permissions) policies.

              
              

              - *(dict) --* 

                Contains information about an attached policy.

                 

                An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

                 

                For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

                
                

                - **PolicyName** *(string) --* 

                  The friendly name of the attached policy.

                  
                

                - **PolicyArn** *(string) --* 

                  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

                   

                  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

                  
            
          
        
      
        

        - **Policies** *(list) --* 

          A list containing information about managed policies.

          
          

          - *(dict) --* 

            Contains information about a managed policy, including the policy's ARN, versions, and the number of principal entities (users, groups, and roles) that the policy is attached to.

             

            This data type is used as a response element in the  GetAccountAuthorizationDetails action.

             

            For more information about managed policies, see `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name (not ARN) identifying the policy.

              
            

            - **PolicyId** *(string) --* 

              The stable and unique string identifying the policy.

               

              For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **Path** *(string) --* 

              The path to the policy.

               

              For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **DefaultVersionId** *(string) --* 

              The identifier for the version of the policy that is set as the default (operative) version.

               

              For more information about policy versions, see `Versioning for Managed Policies`_ in the *Using IAM* guide. 

              
            

            - **AttachmentCount** *(integer) --* 

              The number of principal entities (users, groups, and roles) that the policy is attached to.

              
            

            - **IsAttachable** *(boolean) --* 

              Specifies whether the policy can be attached to an IAM user, group, or role.

              
            

            - **Description** *(string) --* 

              A friendly description of the policy.

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy was created.

              
            

            - **UpdateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy was last updated.

               

              When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created.

              
            

            - **PolicyVersionList** *(list) --* 

              A list containing information about the versions of the policy.

              
              

              - *(dict) --* 

                Contains information about a version of a managed policy.

                 

                This data type is used as a response element in the  CreatePolicyVersion ,  GetPolicyVersion ,  ListPolicyVersions , and  GetAccountAuthorizationDetails actions. 

                 

                For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

                
                

                - **Document** *(string) --* 

                  The policy document.

                   

                  The policy document is returned in the response to the  GetPolicyVersion and  GetAccountAuthorizationDetails operations. It is not returned in the response to the  CreatePolicyVersion or  ListPolicyVersions operations. 

                  
                

                - **VersionId** *(string) --* 

                  The identifier for the policy version.

                   

                  Policy version identifiers always begin with ``v`` (always lowercase). When a policy is created, the first policy version is ``v1`` . 

                  
                

                - **IsDefaultVersion** *(boolean) --* 

                  Specifies whether the policy version is set as the policy's default version.

                  
                

                - **CreateDate** *(datetime) --* 

                  The date and time, in `ISO 8601 date-time format`_ , when the policy version was created.

                  
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.GetGroup

  ::

    
    paginator = client.get_paginator('get_group')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.get_group`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          GroupName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'Group': {
                'Path': 'string',
                'GroupName': 'string',
                'GroupId': 'string',
                'Arn': 'string',
                'CreateDate': datetime(2015, 1, 1)
            },
            'Users': [
                {
                    'Path': 'string',
                    'UserName': 'string',
                    'UserId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'PasswordLastUsed': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  GetGroup request. 

        
        

        - **Group** *(dict) --* 

          A structure that contains details about the group.

          
          

          - **Path** *(string) --* 

            The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **GroupName** *(string) --* 

            The friendly name that identifies the group.

            
          

          - **GroupId** *(string) --* 

            The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

            
          

          - **CreateDate** *(datetime) --* 

            The date and time, in `ISO 8601 date-time format`_ , when the group was created.

            
      
        

        - **Users** *(list) --* 

          A list of users in the group.

          
          

          - *(dict) --* 

            Contains information about an IAM user entity.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateUser   
             
            *  GetUser   
             
            *  ListUsers   
             

            
            

            - **Path** *(string) --* 

              The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **UserName** *(string) --* 

              The friendly name identifying the user.

              
            

            - **UserId** *(string) --* 

              The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user was created.

              
            

            - **PasswordLastUsed** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

               

               
              * The user does not have a password 
               
              * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
               
              * there is no sign-in data associated with the user 
               

               

              This value is returned only in the  GetUser and  ListUsers actions. 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListAccessKeys

  ::

    
    paginator = client.get_paginator('list_access_keys')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_access_keys`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          UserName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type UserName: string
    :param UserName: 

      The name of the user.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'AccessKeyMetadata': [
                {
                    'UserName': 'string',
                    'AccessKeyId': 'string',
                    'Status': 'Active'|'Inactive',
                    'CreateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAccessKeys request. 

        
        

        - **AccessKeyMetadata** *(list) --* 

          A list of objects containing metadata about the access keys.

          
          

          - *(dict) --* 

            Contains information about an AWS access key, without its secret key.

             

            This data type is used as a response element in the  ListAccessKeys action.

            
            

            - **UserName** *(string) --* 

              The name of the IAM user that the key is associated with.

              
            

            - **AccessKeyId** *(string) --* 

              The ID for this access key.

              
            

            - **Status** *(string) --* 

              The status of the access key. ``Active`` means the key is valid for API calls; ``Inactive`` means it is not.

              
            

            - **CreateDate** *(datetime) --* 

              The date when the access key was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListAccountAliases

  ::

    
    paginator = client.get_paginator('list_account_aliases')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_account_aliases`.

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
            'AccountAliases': [
                'string',
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAccountAliases request. 

        
        

        - **AccountAliases** *(list) --* 

          A list of aliases associated with the account. AWS supports only one alias per account.

          
          

          - *(string) --* 
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListAttachedGroupPolicies

  ::

    
    paginator = client.get_paginator('list_attached_group_policies')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_attached_group_policies`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          GroupName='string',
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the group to list attached policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'AttachedPolicies': [
                {
                    'PolicyName': 'string',
                    'PolicyArn': 'string'
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAttachedGroupPolicies request. 

        
        

        - **AttachedPolicies** *(list) --* 

          A list of the attached policies.

          
          

          - *(dict) --* 

            Contains information about an attached policy.

             

            An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name of the attached policy.

              
            

            - **PolicyArn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListAttachedRolePolicies

  ::

    
    paginator = client.get_paginator('list_attached_role_policies')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_attached_role_policies`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          RoleName='string',
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the role to list attached policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'AttachedPolicies': [
                {
                    'PolicyName': 'string',
                    'PolicyArn': 'string'
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAttachedRolePolicies request. 

        
        

        - **AttachedPolicies** *(list) --* 

          A list of the attached policies.

          
          

          - *(dict) --* 

            Contains information about an attached policy.

             

            An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name of the attached policy.

              
            

            - **PolicyArn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListAttachedUserPolicies

  ::

    
    paginator = client.get_paginator('list_attached_user_policies')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_attached_user_policies`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          UserName='string',
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the user to list attached policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'AttachedPolicies': [
                {
                    'PolicyName': 'string',
                    'PolicyArn': 'string'
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListAttachedUserPolicies request. 

        
        

        - **AttachedPolicies** *(list) --* 

          A list of the attached policies.

          
          

          - *(dict) --* 

            Contains information about an attached policy.

             

            An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  ListAttachedGroupPolicies ,  ListAttachedRolePolicies ,  ListAttachedUserPolicies , and  GetAccountAuthorizationDetails actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name of the attached policy.

              
            

            - **PolicyArn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListEntitiesForPolicy

  ::

    
    paginator = client.get_paginator('list_entities_for_policy')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_entities_for_policy`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PolicyArn='string',
          EntityFilter='User'|'Role'|'Group'|'LocalManagedPolicy'|'AWSManagedPolicy',
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy for which you want the versions.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type EntityFilter: string
    :param EntityFilter: 

      The entity type to use for filtering the results.

       

      For example, when ``EntityFilter`` is ``Role`` , only the roles that are attached to the specified policy are returned. This parameter is optional. If it is not included, all attached entities (users, groups, and roles) are returned. The argument for this parameter must be one of the valid values listed below.

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all entities.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'PolicyGroups': [
                {
                    'GroupName': 'string',
                    'GroupId': 'string'
                },
            ],
            'PolicyUsers': [
                {
                    'UserName': 'string',
                    'UserId': 'string'
                },
            ],
            'PolicyRoles': [
                {
                    'RoleName': 'string',
                    'RoleId': 'string'
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListEntitiesForPolicy request. 

        
        

        - **PolicyGroups** *(list) --* 

          A list of IAM groups that the policy is attached to.

          
          

          - *(dict) --* 

            Contains information about a group that a managed policy is attached to.

             

            This data type is used as a response element in the  ListEntitiesForPolicy action. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **GroupName** *(string) --* 

              The name (friendly name, not ARN) identifying the group.

              
            

            - **GroupId** *(string) --* 

              The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *IAM User Guide* .

              
        
      
        

        - **PolicyUsers** *(list) --* 

          A list of IAM users that the policy is attached to.

          
          

          - *(dict) --* 

            Contains information about a user that a managed policy is attached to.

             

            This data type is used as a response element in the  ListEntitiesForPolicy action. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **UserName** *(string) --* 

              The name (friendly name, not ARN) identifying the user.

              
            

            - **UserId** *(string) --* 

              The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *IAM User Guide* .

              
        
      
        

        - **PolicyRoles** *(list) --* 

          A list of IAM roles that the policy is attached to.

          
          

          - *(dict) --* 

            Contains information about a role that a managed policy is attached to.

             

            This data type is used as a response element in the  ListEntitiesForPolicy action. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **RoleName** *(string) --* 

              The name (friendly name, not ARN) identifying the role.

              
            

            - **RoleId** *(string) --* 

              The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *IAM User Guide* .

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListGroupPolicies

  ::

    
    paginator = client.get_paginator('list_group_policies')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_group_policies`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          GroupName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group to list policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListGroupPolicies request. 

        
        

        - **PolicyNames** *(list) --* 

          A list of policy names.

          
          

          - *(string) --* 
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListGroups

  ::

    
    paginator = client.get_paginator('list_groups')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_groups`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example, the prefix ``/division_abc/subdivision_xyz/`` gets all groups whose path starts with ``/division_abc/subdivision_xyz/`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all groups. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'Groups': [
                {
                    'Path': 'string',
                    'GroupName': 'string',
                    'GroupId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListGroups request. 

        
        

        - **Groups** *(list) --* 

          A list of groups.

          
          

          - *(dict) --* 

            Contains information about an IAM group entity.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateGroup   
             
            *  GetGroup   
             
            *  ListGroups   
             

            
            

            - **Path** *(string) --* 

              The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **GroupName** *(string) --* 

              The friendly name that identifies the group.

              
            

            - **GroupId** *(string) --* 

              The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the group was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListGroupsForUser

  ::

    
    paginator = client.get_paginator('list_groups_for_user')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_groups_for_user`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          UserName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to list groups for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'Groups': [
                {
                    'Path': 'string',
                    'GroupName': 'string',
                    'GroupId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListGroupsForUser request. 

        
        

        - **Groups** *(list) --* 

          A list of groups.

          
          

          - *(dict) --* 

            Contains information about an IAM group entity.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateGroup   
             
            *  GetGroup   
             
            *  ListGroups   
             

            
            

            - **Path** *(string) --* 

              The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **GroupName** *(string) --* 

              The friendly name that identifies the group.

              
            

            - **GroupId** *(string) --* 

              The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the group was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListInstanceProfiles

  ::

    
    paginator = client.get_paginator('list_instance_profiles')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_instance_profiles`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example, the prefix ``/application_abc/component_xyz/`` gets all instance profiles whose path starts with ``/application_abc/component_xyz/`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all instance profiles. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'InstanceProfiles': [
                {
                    'Path': 'string',
                    'InstanceProfileName': 'string',
                    'InstanceProfileId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'Roles': [
                        {
                            'Path': 'string',
                            'RoleName': 'string',
                            'RoleId': 'string',
                            'Arn': 'string',
                            'CreateDate': datetime(2015, 1, 1),
                            'AssumeRolePolicyDocument': 'string'
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListInstanceProfiles request. 

        
        

        - **InstanceProfiles** *(list) --* 

          A list of instance profiles.

          
          

          - *(dict) --* 

            Contains information about an instance profile.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateInstanceProfile   
             
            *  GetInstanceProfile   
             
            *  ListInstanceProfiles   
             
            *  ListInstanceProfilesForRole   
             

            
            

            - **Path** *(string) --* 

              The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **InstanceProfileName** *(string) --* 

              The name identifying the instance profile.

              
            

            - **InstanceProfileId** *(string) --* 

              The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date when the instance profile was created.

              
            

            - **Roles** *(list) --* 

              The role associated with the instance profile.

              
              

              - *(dict) --* 

                Contains information about an IAM role.

                 

                This data type is used as a response element in the following actions:

                 

                 
                *  CreateRole   
                 
                *  GetRole   
                 
                *  ListRoles   
                 

                
                

                - **Path** *(string) --* 

                  The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **RoleName** *(string) --* 

                  The friendly name that identifies the role.

                  
                

                - **RoleId** *(string) --* 

                  The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **Arn** *(string) --* 

                  The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **CreateDate** *(datetime) --* 

                  The date and time, in `ISO 8601 date-time format`_ , when the role was created.

                  
                

                - **AssumeRolePolicyDocument** *(string) --* 

                  The policy that grants an entity permission to assume the role.

                  
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListInstanceProfilesForRole

  ::

    
    paginator = client.get_paginator('list_instance_profiles_for_role')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_instance_profiles_for_role`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          RoleName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to list instance profiles for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'InstanceProfiles': [
                {
                    'Path': 'string',
                    'InstanceProfileName': 'string',
                    'InstanceProfileId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'Roles': [
                        {
                            'Path': 'string',
                            'RoleName': 'string',
                            'RoleId': 'string',
                            'Arn': 'string',
                            'CreateDate': datetime(2015, 1, 1),
                            'AssumeRolePolicyDocument': 'string'
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListInstanceProfilesForRole request. 

        
        

        - **InstanceProfiles** *(list) --* 

          A list of instance profiles.

          
          

          - *(dict) --* 

            Contains information about an instance profile.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateInstanceProfile   
             
            *  GetInstanceProfile   
             
            *  ListInstanceProfiles   
             
            *  ListInstanceProfilesForRole   
             

            
            

            - **Path** *(string) --* 

              The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **InstanceProfileName** *(string) --* 

              The name identifying the instance profile.

              
            

            - **InstanceProfileId** *(string) --* 

              The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date when the instance profile was created.

              
            

            - **Roles** *(list) --* 

              The role associated with the instance profile.

              
              

              - *(dict) --* 

                Contains information about an IAM role.

                 

                This data type is used as a response element in the following actions:

                 

                 
                *  CreateRole   
                 
                *  GetRole   
                 
                *  ListRoles   
                 

                
                

                - **Path** *(string) --* 

                  The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **RoleName** *(string) --* 

                  The friendly name that identifies the role.

                  
                

                - **RoleId** *(string) --* 

                  The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **Arn** *(string) --* 

                  The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                  
                

                - **CreateDate** *(datetime) --* 

                  The date and time, in `ISO 8601 date-time format`_ , when the role was created.

                  
                

                - **AssumeRolePolicyDocument** *(string) --* 

                  The policy that grants an entity permission to assume the role.

                  
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListMFADevices

  ::

    
    paginator = client.get_paginator('list_mfa_devices')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_mfa_devices`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          UserName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type UserName: string
    :param UserName: 

      The name of the user whose MFA devices you want to list.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'MFADevices': [
                {
                    'UserName': 'string',
                    'SerialNumber': 'string',
                    'EnableDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListMFADevices request. 

        
        

        - **MFADevices** *(list) --* 

          A list of MFA devices.

          
          

          - *(dict) --* 

            Contains information about an MFA device.

             

            This data type is used as a response element in the  ListMFADevices action.

            
            

            - **UserName** *(string) --* 

              The user with whom the MFA device is associated.

              
            

            - **SerialNumber** *(string) --* 

              The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN.

              
            

            - **EnableDate** *(datetime) --* 

              The date when the MFA device was enabled for the user.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListPolicies

  ::

    
    paginator = client.get_paginator('list_policies')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_policies`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          Scope='All'|'AWS'|'Local',
          OnlyAttached=True|False,
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type Scope: string
    :param Scope: 

      The scope to use for filtering the results.

       

      To list only AWS managed policies, set ``Scope`` to ``AWS`` . To list only the customer managed policies in your AWS account, set ``Scope`` to ``Local`` .

       

      This parameter is optional. If it is not included, or if it is set to ``All`` , all policies are returned.

      

    
    :type OnlyAttached: boolean
    :param OnlyAttached: 

      A flag to filter the results to only the attached policies.

       

      When ``OnlyAttached`` is ``true`` , the returned list contains only the policies that are attached to an IAM user, group, or role. When ``OnlyAttached`` is ``false`` , or when the parameter is not included, all policies are returned.

      

    
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'Policies': [
                {
                    'PolicyName': 'string',
                    'PolicyId': 'string',
                    'Arn': 'string',
                    'Path': 'string',
                    'DefaultVersionId': 'string',
                    'AttachmentCount': 123,
                    'IsAttachable': True|False,
                    'Description': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'UpdateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListPolicies request. 

        
        

        - **Policies** *(list) --* 

          A list of policies.

          
          

          - *(dict) --* 

            Contains information about a managed policy.

             

            This data type is used as a response element in the  CreatePolicy ,  GetPolicy , and  ListPolicies actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **PolicyName** *(string) --* 

              The friendly name (not ARN) identifying the policy.

              
            

            - **PolicyId** *(string) --* 

              The stable and unique string identifying the policy.

               

              For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

               

              For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

              
            

            - **Path** *(string) --* 

              The path to the policy.

               

              For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **DefaultVersionId** *(string) --* 

              The identifier for the version of the policy that is set as the default version.

              
            

            - **AttachmentCount** *(integer) --* 

              The number of entities (users, groups, and roles) that the policy is attached to.

              
            

            - **IsAttachable** *(boolean) --* 

              Specifies whether the policy can be attached to an IAM user, group, or role.

              
            

            - **Description** *(string) --* 

              A friendly description of the policy.

               

              This element is included in the response to the  GetPolicy operation. It is not included in the response to the  ListPolicies operation. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy was created.

              
            

            - **UpdateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy was last updated.

               

              When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListPolicyVersions

  ::

    
    paginator = client.get_paginator('list_policy_versions')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_policy_versions`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PolicyArn='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy for which you want the versions.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
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
            'Versions': [
                {
                    'Document': 'string',
                    'VersionId': 'string',
                    'IsDefaultVersion': True|False,
                    'CreateDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListPolicyVersions request. 

        
        

        - **Versions** *(list) --* 

          A list of policy versions.

           

          For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

          
          

          - *(dict) --* 

            Contains information about a version of a managed policy.

             

            This data type is used as a response element in the  CreatePolicyVersion ,  GetPolicyVersion ,  ListPolicyVersions , and  GetAccountAuthorizationDetails actions. 

             

            For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

            
            

            - **Document** *(string) --* 

              The policy document.

               

              The policy document is returned in the response to the  GetPolicyVersion and  GetAccountAuthorizationDetails operations. It is not returned in the response to the  CreatePolicyVersion or  ListPolicyVersions operations. 

              
            

            - **VersionId** *(string) --* 

              The identifier for the policy version.

               

              Policy version identifiers always begin with ``v`` (always lowercase). When a policy is created, the first policy version is ``v1`` . 

              
            

            - **IsDefaultVersion** *(boolean) --* 

              Specifies whether the policy version is set as the policy's default version.

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the policy version was created.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListRolePolicies

  ::

    
    paginator = client.get_paginator('list_role_policies')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_role_policies`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          RoleName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to list policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListRolePolicies request. 

        
        

        - **PolicyNames** *(list) --* 

          A list of policy names.

          
          

          - *(string) --* 
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListRoles

  ::

    
    paginator = client.get_paginator('list_roles')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_roles`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example, the prefix ``/application_abc/component_xyz/`` gets all roles whose path starts with ``/application_abc/component_xyz/`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all roles. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'Roles': [
                {
                    'Path': 'string',
                    'RoleName': 'string',
                    'RoleId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'AssumeRolePolicyDocument': 'string'
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListRoles request. 

        
        

        - **Roles** *(list) --* 

          A list of roles.

          
          

          - *(dict) --* 

            Contains information about an IAM role.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateRole   
             
            *  GetRole   
             
            *  ListRoles   
             

            
            

            - **Path** *(string) --* 

              The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **RoleName** *(string) --* 

              The friendly name that identifies the role.

              
            

            - **RoleId** *(string) --* 

              The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the role was created.

              
            

            - **AssumeRolePolicyDocument** *(string) --* 

              The policy that grants an entity permission to assume the role.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListSSHPublicKeys

  ::

    
    paginator = client.get_paginator('list_ssh_public_keys')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_ssh_public_keys`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          UserName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type UserName: string
    :param UserName: 

      The name of the IAM user to list SSH public keys for. If none is specified, the UserName field is determined implicitly based on the AWS access key used to sign the request.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'SSHPublicKeys': [
                {
                    'UserName': 'string',
                    'SSHPublicKeyId': 'string',
                    'Status': 'Active'|'Inactive',
                    'UploadDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListSSHPublicKeys request.

        
        

        - **SSHPublicKeys** *(list) --* 

          A list of the SSH public keys assigned to IAM user.

          
          

          - *(dict) --* 

            Contains information about an SSH public key, without the key's body or fingerprint.

             

            This data type is used as a response element in the  ListSSHPublicKeys action.

            
            

            - **UserName** *(string) --* 

              The name of the IAM user associated with the SSH public key.

              
            

            - **SSHPublicKeyId** *(string) --* 

              The unique identifier for the SSH public key.

              
            

            - **Status** *(string) --* 

              The status of the SSH public key. ``Active`` means the key can be used for authentication with an AWS CodeCommit repository. ``Inactive`` means the key cannot be used.

              
            

            - **UploadDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the SSH public key was uploaded.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListServerCertificates

  ::

    
    paginator = client.get_paginator('list_server_certificates')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_server_certificates`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example: ``/company/servercerts`` would get all server certificates for which the path starts with ``/company/servercerts`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all server certificates. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'ServerCertificateMetadataList': [
                {
                    'Path': 'string',
                    'ServerCertificateName': 'string',
                    'ServerCertificateId': 'string',
                    'Arn': 'string',
                    'UploadDate': datetime(2015, 1, 1),
                    'Expiration': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListServerCertificates request. 

        
        

        - **ServerCertificateMetadataList** *(list) --* 

          A list of server certificates.

          
          

          - *(dict) --* 

            Contains information about a server certificate without its certificate body, certificate chain, and private key.

             

            This data type is used as a response element in the  UploadServerCertificate and  ListServerCertificates actions. 

            
            

            - **Path** *(string) --* 

              The path to the server certificate. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **ServerCertificateName** *(string) --* 

              The name that identifies the server certificate.

              
            

            - **ServerCertificateId** *(string) --* 

              The stable and unique string identifying the server certificate. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) specifying the server certificate. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **UploadDate** *(datetime) --* 

              The date when the server certificate was uploaded.

              
            

            - **Expiration** *(datetime) --* 

              The date on which the certificate is set to expire.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListSigningCertificates

  ::

    
    paginator = client.get_paginator('list_signing_certificates')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_signing_certificates`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          UserName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type UserName: string
    :param UserName: 

      The name of the IAM user whose signing certificates you want to examine.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'Certificates': [
                {
                    'UserName': 'string',
                    'CertificateId': 'string',
                    'CertificateBody': 'string',
                    'Status': 'Active'|'Inactive',
                    'UploadDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListSigningCertificates request. 

        
        

        - **Certificates** *(list) --* 

          A list of the user's signing certificate information.

          
          

          - *(dict) --* 

            Contains information about an X.509 signing certificate.

             

            This data type is used as a response element in the  UploadSigningCertificate and  ListSigningCertificates actions. 

            
            

            - **UserName** *(string) --* 

              The name of the user the signing certificate is associated with.

              
            

            - **CertificateId** *(string) --* 

              The ID for the signing certificate.

              
            

            - **CertificateBody** *(string) --* 

              The contents of the signing certificate.

              
            

            - **Status** *(string) --* 

              The status of the signing certificate. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not.

              
            

            - **UploadDate** *(datetime) --* 

              The date when the signing certificate was uploaded.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListUserPolicies

  ::

    
    paginator = client.get_paginator('list_user_policies')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_user_policies`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          UserName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to list policies for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
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
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListUserPolicies request. 

        
        

        - **PolicyNames** *(list) --* 

          A list of policy names.

          
          

          - *(string) --* 
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListUsers

  ::

    
    paginator = client.get_paginator('list_users')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_users`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PathPrefix='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type PathPrefix: string
    :param PathPrefix: 

      The path prefix for filtering the results. For example: ``/division_abc/subdivision_xyz/`` , which would get all user names whose path starts with ``/division_abc/subdivision_xyz/`` .

       

      This parameter is optional. If it is not included, it defaults to a slash (/), listing all user names. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
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
            'Users': [
                {
                    'Path': 'string',
                    'UserName': 'string',
                    'UserId': 'string',
                    'Arn': 'string',
                    'CreateDate': datetime(2015, 1, 1),
                    'PasswordLastUsed': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListUsers request. 

        
        

        - **Users** *(list) --* 

          A list of users.

          
          

          - *(dict) --* 

            Contains information about an IAM user entity.

             

            This data type is used as a response element in the following actions:

             

             
            *  CreateUser   
             
            *  GetUser   
             
            *  ListUsers   
             

            
            

            - **Path** *(string) --* 

              The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **UserName** *(string) --* 

              The friendly name identifying the user.

              
            

            - **UserId** *(string) --* 

              The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

              
            

            - **CreateDate** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user was created.

              
            

            - **PasswordLastUsed** *(datetime) --* 

              The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

               

               
              * The user does not have a password 
               
              * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
               
              * there is no sign-in data associated with the user 
               

               

              This value is returned only in the  GetUser and  ListUsers actions. 

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.ListVirtualMFADevices

  ::

    
    paginator = client.get_paginator('list_virtual_mfa_devices')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.list_virtual_mfa_devices`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          AssignmentStatus='Assigned'|'Unassigned'|'Any',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type AssignmentStatus: string
    :param AssignmentStatus: 

      The status (``Unassigned`` or ``Assigned`` ) of the devices to list. If you do not specify an ``AssignmentStatus`` , the action defaults to ``Any`` which lists both assigned and unassigned virtual MFA devices.

      

    
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
            'VirtualMFADevices': [
                {
                    'SerialNumber': 'string',
                    'Base32StringSeed': b'bytes',
                    'QRCodePNG': b'bytes',
                    'User': {
                        'Path': 'string',
                        'UserName': 'string',
                        'UserId': 'string',
                        'Arn': 'string',
                        'CreateDate': datetime(2015, 1, 1),
                        'PasswordLastUsed': datetime(2015, 1, 1)
                    },
                    'EnableDate': datetime(2015, 1, 1)
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  ListVirtualMFADevices request. 

        
        

        - **VirtualMFADevices** *(list) --* 

          The list of virtual MFA devices in the current account that match the ``AssignmentStatus`` value that was passed in the request.

          
          

          - *(dict) --* 

            Contains information about a virtual MFA device.

            
            

            - **SerialNumber** *(string) --* 

              The serial number associated with ``VirtualMFADevice`` .

              
            

            - **Base32StringSeed** *(bytes) --* 

              The Base32 seed defined as specified in `RFC3548`_ . The ``Base32StringSeed`` is Base64-encoded. 

              
            

            - **QRCodePNG** *(bytes) --* 

              A QR code PNG image that encodes ``otpauth://totp/$virtualMFADeviceName@$AccountName?secret=$Base32String`` where ``$virtualMFADeviceName`` is one of the create call arguments, ``AccountName`` is the user name if set (otherwise, the account ID otherwise), and ``Base32String`` is the seed in Base32 format. The ``Base32String`` value is Base64-encoded. 

              
            

            - **User** *(dict) --* 

              Contains information about an IAM user entity.

               

              This data type is used as a response element in the following actions:

               

               
              *  CreateUser   
               
              *  GetUser   
               
              *  ListUsers   
               

              
              

              - **Path** *(string) --* 

                The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

                
              

              - **UserName** *(string) --* 

                The friendly name identifying the user.

                
              

              - **UserId** *(string) --* 

                The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

                
              

              - **Arn** *(string) --* 

                The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

                
              

              - **CreateDate** *(datetime) --* 

                The date and time, in `ISO 8601 date-time format`_ , when the user was created.

                
              

              - **PasswordLastUsed** *(datetime) --* 

                The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

                 

                 
                * The user does not have a password 
                 
                * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
                 
                * there is no sign-in data associated with the user 
                 

                 

                This value is returned only in the  GetUser and  ListUsers actions. 

                
          
            

            - **EnableDate** *(datetime) --* 

              The date and time on which the virtual MFA device was enabled.

              
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.SimulateCustomPolicy

  ::

    
    paginator = client.get_paginator('simulate_custom_policy')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.simulate_custom_policy`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PolicyInputList=[
              'string',
          ],
          ActionNames=[
              'string',
          ],
          ResourceArns=[
              'string',
          ],
          ResourcePolicy='string',
          ResourceOwner='string',
          CallerArn='string',
          ContextEntries=[
              {
                  'ContextKeyName': 'string',
                  'ContextKeyValues': [
                      'string',
                  ],
                  'ContextKeyType': 'string'|'stringList'|'numeric'|'numericList'|'boolean'|'booleanList'|'ip'|'ipList'|'binary'|'binaryList'|'date'|'dateList'
              },
          ],
          ResourceHandlingOption='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type PolicyInputList: list
    :param PolicyInputList: **[REQUIRED]** 

      A list of policy documents to include in the simulation. Each document is specified as a string containing the complete, valid JSON text of an IAM policy. Do not include any resource-based policies in this parameter. Any resource-based policy must be submitted with the ``ResourcePolicy`` parameter. The policies cannot be "scope-down" policies, such as you could include in a call to `GetFederationToken`_ or one of the `AssumeRole`_ APIs to restrict what a user can do while using the temporary credentials.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
      - *(string) --* 

      
  
    :type ActionNames: list
    :param ActionNames: **[REQUIRED]** 

      A list of names of API actions to evaluate in the simulation. Each action is evaluated against each resource. Each action must include the service identifier, such as ``iam:CreateUser`` .

      

    
      - *(string) --* 

      
  
    :type ResourceArns: list
    :param ResourceArns: 

      A list of ARNs of AWS resources to include in the simulation. If this parameter is not provided then the value defaults to ``*`` (all resources). Each API in the ``ActionNames`` parameter is evaluated for each resource in this list. The simulation determines the access result (allowed or denied) of each combination and reports it in the response.

       

      The simulation does not automatically retrieve policies for the specified resources. If you want to include a resource policy in the simulation, then you must include the policy as a string in the ``ResourcePolicy`` parameter.

       

      If you include a ``ResourcePolicy`` , then it must be applicable to all of the resources included in the simulation or you receive an invalid input error.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
      - *(string) --* 

      
  
    :type ResourcePolicy: string
    :param ResourcePolicy: 

      A resource-based policy to include in the simulation provided as a string. Each resource in the simulation is treated as if it had this policy attached. You can include only one resource-based policy in a simulation.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type ResourceOwner: string
    :param ResourceOwner: 

      An AWS account ID that specifies the owner of any simulated resource that does not identify its owner in the resource ARN, such as an S3 bucket or object. If ``ResourceOwner`` is specified, it is also used as the account owner of any ``ResourcePolicy`` included in the simulation. If the ``ResourceOwner`` parameter is not specified, then the owner of the resources and the resource policy defaults to the account of the identity provided in ``CallerArn`` . This parameter is required only if you specify a resource-based policy and account that owns the resource is different from the account that owns the simulated calling user ``CallerArn`` .

      

    
    :type CallerArn: string
    :param CallerArn: 

      The ARN of the IAM user that you want to use as the simulated caller of the APIs. ``CallerArn`` is required if you include a ``ResourcePolicy`` so that the policy's ``Principal`` element has a value to use in evaluating the policy.

       

      You can specify only the ARN of an IAM user. You cannot specify the ARN of an assumed role, federated user, or a service principal.

      

    
    :type ContextEntries: list
    :param ContextEntries: 

      A list of context keys and corresponding values for the simulation to use. Whenever a context key is evaluated in one of the simulated IAM permission policies, the corresponding value is supplied.

      

    
      - *(dict) --* 

        Contains information about a condition context key. It includes the name of the key and specifies the value (or values, if the context key supports multiple values) to use in the simulation. This information is used when evaluating the ``Condition`` elements of the input policies.

         

        This data type is used as an input parameter to ``  SimulateCustomPolicy `` and ``  SimulateCustomPolicy `` .

        

      
        - **ContextKeyName** *(string) --* 

          The full name of a condition context key, including the service prefix. For example, ``aws:SourceIp`` or ``s3:VersionId`` .

          

        
        - **ContextKeyValues** *(list) --* 

          The value (or values, if the condition context key supports multiple values) to provide to the simulation for use when the key is referenced by a ``Condition`` element in an input policy.

          

        
          - *(string) --* 

          
      
        - **ContextKeyType** *(string) --* 

          The data type of the value (or values) specified in the ``ContextKeyValues`` parameter.

          

        
      
  
    :type ResourceHandlingOption: string
    :param ResourceHandlingOption: 

      Specifies the type of simulation to run. Different APIs that support resource-based policies require different combinations of resources. By specifying the type of simulation to run, you enable the policy simulator to enforce the presence of the required resources to ensure reliable simulation results. If your simulation does not match one of the following scenarios, then you can omit this parameter. The following list shows each of the supported scenario values and the resources that you must define to run the simulation.

       

      Each of the EC2 scenarios requires that you specify instance, image, and security-group resources. If your scenario includes an EBS volume, then you must specify that volume as a resource. If the EC2 scenario includes VPC, then you must supply the network-interface resource. If it includes an IP subnet, then you must specify the subnet resource. For more information on the EC2 scenario options, see `Supported Platforms`_ in the *AWS EC2 User Guide* .

       

       
      * **EC2-Classic-InstanceStore**   instance, image, security-group 
       
      * **EC2-Classic-EBS**   instance, image, security-group, volume 
       
      * **EC2-VPC-InstanceStore**   instance, image, security-group, network-interface 
       
      * **EC2-VPC-InstanceStore-Subnet**   instance, image, security-group, network-interface, subnet 
       
      * **EC2-VPC-EBS**   instance, image, security-group, network-interface, volume 
       
      * **EC2-VPC-EBS-Subnet**   instance, image, security-group, network-interface, subnet, volume 
       

      

    
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
            'EvaluationResults': [
                {
                    'EvalActionName': 'string',
                    'EvalResourceName': 'string',
                    'EvalDecision': 'allowed'|'explicitDeny'|'implicitDeny',
                    'MatchedStatements': [
                        {
                            'SourcePolicyId': 'string',
                            'SourcePolicyType': 'user'|'group'|'role'|'aws-managed'|'user-managed'|'resource'|'none',
                            'StartPosition': {
                                'Line': 123,
                                'Column': 123
                            },
                            'EndPosition': {
                                'Line': 123,
                                'Column': 123
                            }
                        },
                    ],
                    'MissingContextValues': [
                        'string',
                    ],
                    'EvalDecisionDetails': {
                        'string': 'allowed'|'explicitDeny'|'implicitDeny'
                    },
                    'ResourceSpecificResults': [
                        {
                            'EvalResourceName': 'string',
                            'EvalResourceDecision': 'allowed'|'explicitDeny'|'implicitDeny',
                            'MatchedStatements': [
                                {
                                    'SourcePolicyId': 'string',
                                    'SourcePolicyType': 'user'|'group'|'role'|'aws-managed'|'user-managed'|'resource'|'none',
                                    'StartPosition': {
                                        'Line': 123,
                                        'Column': 123
                                    },
                                    'EndPosition': {
                                        'Line': 123,
                                        'Column': 123
                                    }
                                },
                            ],
                            'MissingContextValues': [
                                'string',
                            ],
                            'EvalDecisionDetails': {
                                'string': 'allowed'|'explicitDeny'|'implicitDeny'
                            }
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  SimulatePrincipalPolicy or  SimulateCustomPolicy request.

        
        

        - **EvaluationResults** *(list) --* 

          The results of the simulation.

          
          

          - *(dict) --* 

            Contains the results of a simulation.

             

            This data type is used by the return parameter of ``  SimulateCustomPolicy `` and ``  SimulatePrincipalPolicy `` .

            
            

            - **EvalActionName** *(string) --* 

              The name of the API action tested on the indicated resource.

              
            

            - **EvalResourceName** *(string) --* 

              The ARN of the resource that the indicated API action was tested on.

              
            

            - **EvalDecision** *(string) --* 

              The result of the simulation.

              
            

            - **MatchedStatements** *(list) --* 

              A list of the statements in the input policies that determine the result for this scenario. Remember that even if multiple statements allow the action on the resource, if only one statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

              
              

              - *(dict) --* 

                Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

                 

                This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

                
                

                - **SourcePolicyId** *(string) --* 

                  The identifier of the policy that was provided as an input.

                  
                

                - **SourcePolicyType** *(string) --* 

                  The type of the policy.

                  
                

                - **StartPosition** *(dict) --* 

                  The row and column of the beginning of the ``Statement`` in an IAM policy.

                  
                  

                  - **Line** *(integer) --* 

                    The line containing the specified position in the document.

                    
                  

                  - **Column** *(integer) --* 

                    The column in the line containing the specified position in the document.

                    
              
                

                - **EndPosition** *(dict) --* 

                  The row and column of the end of a ``Statement`` in an IAM policy.

                  
                  

                  - **Line** *(integer) --* 

                    The line containing the specified position in the document.

                    
                  

                  - **Column** *(integer) --* 

                    The column in the line containing the specified position in the document.

                    
              
            
          
            

            - **MissingContextValues** *(list) --* 

              A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when the resource in a simulation is "*", either explicitly, or when the ``ResourceArns`` parameter blank. If you include a list of resources, then any missing context values are instead included under the ``ResourceSpecificResults`` section. To discover the context keys used by a set of policies, you can call  GetContextKeysForCustomPolicy or  GetContextKeysForPrincipalPolicy .

              
              

              - *(string) --* 
          
            

            - **EvalDecisionDetails** *(dict) --* 

              Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access. See `How IAM Roles Differ from Resource-based Policies`_  

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
            

            - **ResourceSpecificResults** *(list) --* 

              The individual results of the simulation of the API action specified in EvalActionName on each resource.

              
              

              - *(dict) --* 

                Contains the result of the simulation of a single API action call on a single resource.

                 

                This data type is used by a member of the  EvaluationResult data type.

                
                

                - **EvalResourceName** *(string) --* 

                  The name of the simulated resource, in Amazon Resource Name (ARN) format.

                  
                

                - **EvalResourceDecision** *(string) --* 

                  The result of the simulation of the simulated API action on the resource specified in ``EvalResourceName`` .

                  
                

                - **MatchedStatements** *(list) --* 

                  A list of the statements in the input policies that determine the result for this part of the simulation. Remember that even if multiple statements allow the action on the resource, if *any* statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

                  
                  

                  - *(dict) --* 

                    Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

                     

                    This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

                    
                    

                    - **SourcePolicyId** *(string) --* 

                      The identifier of the policy that was provided as an input.

                      
                    

                    - **SourcePolicyType** *(string) --* 

                      The type of the policy.

                      
                    

                    - **StartPosition** *(dict) --* 

                      The row and column of the beginning of the ``Statement`` in an IAM policy.

                      
                      

                      - **Line** *(integer) --* 

                        The line containing the specified position in the document.

                        
                      

                      - **Column** *(integer) --* 

                        The column in the line containing the specified position in the document.

                        
                  
                    

                    - **EndPosition** *(dict) --* 

                      The row and column of the end of a ``Statement`` in an IAM policy.

                      
                      

                      - **Line** *(integer) --* 

                        The line containing the specified position in the document.

                        
                      

                      - **Column** *(integer) --* 

                        The column in the line containing the specified position in the document.

                        
                  
                
              
                

                - **MissingContextValues** *(list) --* 

                  A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when a list of ARNs is included in the ``ResourceArns`` parameter instead of "*". If you do not specify individual resources, by setting ``ResourceArns`` to "*" or by not including the ``ResourceArns`` parameter, then any missing context values are instead included under the ``EvaluationResults`` section. To discover the context keys used by a set of policies, you can call  GetContextKeysForCustomPolicy or  GetContextKeysForPrincipalPolicy .

                  
                  

                  - *(string) --* 
              
                

                - **EvalDecisionDetails** *(dict) --* 

                  Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: IAM.Paginator.SimulatePrincipalPolicy

  ::

    
    paginator = client.get_paginator('simulate_principal_policy')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`IAM.Client.simulate_principal_policy`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          PolicySourceArn='string',
          PolicyInputList=[
              'string',
          ],
          ActionNames=[
              'string',
          ],
          ResourceArns=[
              'string',
          ],
          ResourcePolicy='string',
          ResourceOwner='string',
          CallerArn='string',
          ContextEntries=[
              {
                  'ContextKeyName': 'string',
                  'ContextKeyValues': [
                      'string',
                  ],
                  'ContextKeyType': 'string'|'stringList'|'numeric'|'numericList'|'boolean'|'booleanList'|'ip'|'ipList'|'binary'|'binaryList'|'date'|'dateList'
              },
          ],
          ResourceHandlingOption='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type PolicySourceArn: string
    :param PolicySourceArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of a user, group, or role whose policies you want to include in the simulation. If you specify a user, group, or role, the simulation includes all policies that are associated with that entity. If you specify a user, the simulation also includes all policies that are attached to any groups the user belongs to.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type PolicyInputList: list
    :param PolicyInputList: 

      An optional list of additional policy documents to include in the simulation. Each document is specified as a string containing the complete, valid JSON text of an IAM policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
      - *(string) --* 

      
  
    :type ActionNames: list
    :param ActionNames: **[REQUIRED]** 

      A list of names of API actions to evaluate in the simulation. Each action is evaluated for each resource. Each action must include the service identifier, such as ``iam:CreateUser`` .

      

    
      - *(string) --* 

      
  
    :type ResourceArns: list
    :param ResourceArns: 

      A list of ARNs of AWS resources to include in the simulation. If this parameter is not provided then the value defaults to ``*`` (all resources). Each API in the ``ActionNames`` parameter is evaluated for each resource in this list. The simulation determines the access result (allowed or denied) of each combination and reports it in the response.

       

      The simulation does not automatically retrieve policies for the specified resources. If you want to include a resource policy in the simulation, then you must include the policy as a string in the ``ResourcePolicy`` parameter.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
      - *(string) --* 

      
  
    :type ResourcePolicy: string
    :param ResourcePolicy: 

      A resource-based policy to include in the simulation provided as a string. Each resource in the simulation is treated as if it had this policy attached. You can include only one resource-based policy in a simulation.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type ResourceOwner: string
    :param ResourceOwner: 

      An AWS account ID that specifies the owner of any simulated resource that does not identify its owner in the resource ARN, such as an S3 bucket or object. If ``ResourceOwner`` is specified, it is also used as the account owner of any ``ResourcePolicy`` included in the simulation. If the ``ResourceOwner`` parameter is not specified, then the owner of the resources and the resource policy defaults to the account of the identity provided in ``CallerArn`` . This parameter is required only if you specify a resource-based policy and account that owns the resource is different from the account that owns the simulated calling user ``CallerArn`` .

      

    
    :type CallerArn: string
    :param CallerArn: 

      The ARN of the IAM user that you want to specify as the simulated caller of the APIs. If you do not specify a ``CallerArn`` , it defaults to the ARN of the user that you specify in ``PolicySourceArn`` , if you specified a user. If you include both a ``PolicySourceArn`` (for example, ``arn:aws:iam::123456789012:user/David`` ) and a ``CallerArn`` (for example, ``arn:aws:iam::123456789012:user/Bob`` ), the result is that you simulate calling the APIs as Bob, as if Bob had David's policies.

       

      You can specify only the ARN of an IAM user. You cannot specify the ARN of an assumed role, federated user, or a service principal.

       

       ``CallerArn`` is required if you include a ``ResourcePolicy`` and the ``PolicySourceArn`` is not the ARN for an IAM user. This is required so that the resource-based policy's ``Principal`` element has a value to use in evaluating the policy.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    :type ContextEntries: list
    :param ContextEntries: 

      A list of context keys and corresponding values for the simulation to use. Whenever a context key is evaluated in one of the simulated IAM permission policies, the corresponding value is supplied.

      

    
      - *(dict) --* 

        Contains information about a condition context key. It includes the name of the key and specifies the value (or values, if the context key supports multiple values) to use in the simulation. This information is used when evaluating the ``Condition`` elements of the input policies.

         

        This data type is used as an input parameter to ``  SimulateCustomPolicy `` and ``  SimulateCustomPolicy `` .

        

      
        - **ContextKeyName** *(string) --* 

          The full name of a condition context key, including the service prefix. For example, ``aws:SourceIp`` or ``s3:VersionId`` .

          

        
        - **ContextKeyValues** *(list) --* 

          The value (or values, if the condition context key supports multiple values) to provide to the simulation for use when the key is referenced by a ``Condition`` element in an input policy.

          

        
          - *(string) --* 

          
      
        - **ContextKeyType** *(string) --* 

          The data type of the value (or values) specified in the ``ContextKeyValues`` parameter.

          

        
      
  
    :type ResourceHandlingOption: string
    :param ResourceHandlingOption: 

      Specifies the type of simulation to run. Different APIs that support resource-based policies require different combinations of resources. By specifying the type of simulation to run, you enable the policy simulator to enforce the presence of the required resources to ensure reliable simulation results. If your simulation does not match one of the following scenarios, then you can omit this parameter. The following list shows each of the supported scenario values and the resources that you must define to run the simulation.

       

      Each of the EC2 scenarios requires that you specify instance, image, and security-group resources. If your scenario includes an EBS volume, then you must specify that volume as a resource. If the EC2 scenario includes VPC, then you must supply the network-interface resource. If it includes an IP subnet, then you must specify the subnet resource. For more information on the EC2 scenario options, see `Supported Platforms`_ in the *AWS EC2 User Guide* .

       

       
      * **EC2-Classic-InstanceStore**   instance, image, security-group 
       
      * **EC2-Classic-EBS**   instance, image, security-group, volume 
       
      * **EC2-VPC-InstanceStore**   instance, image, security-group, network-interface 
       
      * **EC2-VPC-InstanceStore-Subnet**   instance, image, security-group, network-interface, subnet 
       
      * **EC2-VPC-EBS**   instance, image, security-group, network-interface, volume 
       
      * **EC2-VPC-EBS-Subnet**   instance, image, security-group, network-interface, subnet, volume 
       

      

    
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
            'EvaluationResults': [
                {
                    'EvalActionName': 'string',
                    'EvalResourceName': 'string',
                    'EvalDecision': 'allowed'|'explicitDeny'|'implicitDeny',
                    'MatchedStatements': [
                        {
                            'SourcePolicyId': 'string',
                            'SourcePolicyType': 'user'|'group'|'role'|'aws-managed'|'user-managed'|'resource'|'none',
                            'StartPosition': {
                                'Line': 123,
                                'Column': 123
                            },
                            'EndPosition': {
                                'Line': 123,
                                'Column': 123
                            }
                        },
                    ],
                    'MissingContextValues': [
                        'string',
                    ],
                    'EvalDecisionDetails': {
                        'string': 'allowed'|'explicitDeny'|'implicitDeny'
                    },
                    'ResourceSpecificResults': [
                        {
                            'EvalResourceName': 'string',
                            'EvalResourceDecision': 'allowed'|'explicitDeny'|'implicitDeny',
                            'MatchedStatements': [
                                {
                                    'SourcePolicyId': 'string',
                                    'SourcePolicyType': 'user'|'group'|'role'|'aws-managed'|'user-managed'|'resource'|'none',
                                    'StartPosition': {
                                        'Line': 123,
                                        'Column': 123
                                    },
                                    'EndPosition': {
                                        'Line': 123,
                                        'Column': 123
                                    }
                                },
                            ],
                            'MissingContextValues': [
                                'string',
                            ],
                            'EvalDecisionDetails': {
                                'string': 'allowed'|'explicitDeny'|'implicitDeny'
                            }
                        },
                    ]
                },
            ],
            'IsTruncated': True|False,
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  SimulatePrincipalPolicy or  SimulateCustomPolicy request.

        
        

        - **EvaluationResults** *(list) --* 

          The results of the simulation.

          
          

          - *(dict) --* 

            Contains the results of a simulation.

             

            This data type is used by the return parameter of ``  SimulateCustomPolicy `` and ``  SimulatePrincipalPolicy `` .

            
            

            - **EvalActionName** *(string) --* 

              The name of the API action tested on the indicated resource.

              
            

            - **EvalResourceName** *(string) --* 

              The ARN of the resource that the indicated API action was tested on.

              
            

            - **EvalDecision** *(string) --* 

              The result of the simulation.

              
            

            - **MatchedStatements** *(list) --* 

              A list of the statements in the input policies that determine the result for this scenario. Remember that even if multiple statements allow the action on the resource, if only one statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

              
              

              - *(dict) --* 

                Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

                 

                This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

                
                

                - **SourcePolicyId** *(string) --* 

                  The identifier of the policy that was provided as an input.

                  
                

                - **SourcePolicyType** *(string) --* 

                  The type of the policy.

                  
                

                - **StartPosition** *(dict) --* 

                  The row and column of the beginning of the ``Statement`` in an IAM policy.

                  
                  

                  - **Line** *(integer) --* 

                    The line containing the specified position in the document.

                    
                  

                  - **Column** *(integer) --* 

                    The column in the line containing the specified position in the document.

                    
              
                

                - **EndPosition** *(dict) --* 

                  The row and column of the end of a ``Statement`` in an IAM policy.

                  
                  

                  - **Line** *(integer) --* 

                    The line containing the specified position in the document.

                    
                  

                  - **Column** *(integer) --* 

                    The column in the line containing the specified position in the document.

                    
              
            
          
            

            - **MissingContextValues** *(list) --* 

              A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when the resource in a simulation is "*", either explicitly, or when the ``ResourceArns`` parameter blank. If you include a list of resources, then any missing context values are instead included under the ``ResourceSpecificResults`` section. To discover the context keys used by a set of policies, you can call  GetContextKeysForCustomPolicy or  GetContextKeysForPrincipalPolicy .

              
              

              - *(string) --* 
          
            

            - **EvalDecisionDetails** *(dict) --* 

              Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access. See `How IAM Roles Differ from Resource-based Policies`_  

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
            

            - **ResourceSpecificResults** *(list) --* 

              The individual results of the simulation of the API action specified in EvalActionName on each resource.

              
              

              - *(dict) --* 

                Contains the result of the simulation of a single API action call on a single resource.

                 

                This data type is used by a member of the  EvaluationResult data type.

                
                

                - **EvalResourceName** *(string) --* 

                  The name of the simulated resource, in Amazon Resource Name (ARN) format.

                  
                

                - **EvalResourceDecision** *(string) --* 

                  The result of the simulation of the simulated API action on the resource specified in ``EvalResourceName`` .

                  
                

                - **MatchedStatements** *(list) --* 

                  A list of the statements in the input policies that determine the result for this part of the simulation. Remember that even if multiple statements allow the action on the resource, if *any* statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

                  
                  

                  - *(dict) --* 

                    Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

                     

                    This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

                    
                    

                    - **SourcePolicyId** *(string) --* 

                      The identifier of the policy that was provided as an input.

                      
                    

                    - **SourcePolicyType** *(string) --* 

                      The type of the policy.

                      
                    

                    - **StartPosition** *(dict) --* 

                      The row and column of the beginning of the ``Statement`` in an IAM policy.

                      
                      

                      - **Line** *(integer) --* 

                        The line containing the specified position in the document.

                        
                      

                      - **Column** *(integer) --* 

                        The column in the line containing the specified position in the document.

                        
                  
                    

                    - **EndPosition** *(dict) --* 

                      The row and column of the end of a ``Statement`` in an IAM policy.

                      
                      

                      - **Line** *(integer) --* 

                        The line containing the specified position in the document.

                        
                      

                      - **Column** *(integer) --* 

                        The column in the line containing the specified position in the document.

                        
                  
                
              
                

                - **MissingContextValues** *(list) --* 

                  A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when a list of ARNs is included in the ``ResourceArns`` parameter instead of "*". If you do not specify individual resources, by setting ``ResourceArns`` to "*" or by not including the ``ResourceArns`` parameter, then any missing context values are instead included under the ``EvaluationResults`` section. To discover the context keys used by a set of policies, you can call  GetContextKeysForCustomPolicy or  GetContextKeysForPrincipalPolicy .

                  
                  

                  - *(string) --* 
              
                

                - **EvalDecisionDetails** *(dict) --* 

                  Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
          
        
      
        

        - **IsTruncated** *(boolean) --* 

          A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

          
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

=======
Waiters
=======


The available waiters are:

* :py:class:`IAM.Waiter.InstanceProfileExists`


* :py:class:`IAM.Waiter.UserExists`



.. py:class:: IAM.Waiter.InstanceProfileExists

  ::

    
    waiter = client.get_waiter('instance_profile_exists')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`IAM.Client.get_instance_profile` every 1 seconds until a successful state is reached. An error is returned after 40 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          InstanceProfileName='string'
      )
    :type InstanceProfileName: string
    :param InstanceProfileName: **[REQUIRED]** 

      The name of the instance profile to get information about.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

.. py:class:: IAM.Waiter.UserExists

  ::

    
    waiter = client.get_waiter('user_exists')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`IAM.Client.get_user` every 1 seconds until a successful state is reached. An error is returned after 20 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          UserName='string'
      )
    :type UserName: string
    :param UserName: 

      The name of the user to get information about.

       

      This parameter is optional. If it is not included, it defaults to the user making the request. The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

================
Service Resource
================



.. py:class:: IAM.ServiceResource()

  A resource representing AWS Identity and Access Management (IAM)::

    
    import boto3
    
    iam = boto3.resource('iam')

  
  These are the resource's available actions:
  
  *   :py:meth:`change_password()`

  
  *   :py:meth:`create_account_alias()`

  
  *   :py:meth:`create_account_password_policy()`

  
  *   :py:meth:`create_group()`

  
  *   :py:meth:`create_instance_profile()`

  
  *   :py:meth:`create_policy()`

  
  *   :py:meth:`create_role()`

  
  *   :py:meth:`create_saml_provider()`

  
  *   :py:meth:`create_server_certificate()`

  
  *   :py:meth:`create_signing_certificate()`

  
  *   :py:meth:`create_user()`

  
  *   :py:meth:`create_virtual_mfa_device()`

  
  *   :py:meth:`get_available_subresources()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`AccessKey()`

  
  *   :py:meth:`AccessKeyPair()`

  
  *   :py:meth:`AccountPasswordPolicy()`

  
  *   :py:meth:`AccountSummary()`

  
  *   :py:meth:`AssumeRolePolicy()`

  
  *   :py:meth:`CurrentUser()`

  
  *   :py:meth:`Group()`

  
  *   :py:meth:`GroupPolicy()`

  
  *   :py:meth:`InstanceProfile()`

  
  *   :py:meth:`LoginProfile()`

  
  *   :py:meth:`MfaDevice()`

  
  *   :py:meth:`Policy()`

  
  *   :py:meth:`PolicyVersion()`

  
  *   :py:meth:`Role()`

  
  *   :py:meth:`RolePolicy()`

  
  *   :py:meth:`SamlProvider()`

  
  *   :py:meth:`ServerCertificate()`

  
  *   :py:meth:`SigningCertificate()`

  
  *   :py:meth:`User()`

  
  *   :py:meth:`UserPolicy()`

  
  *   :py:meth:`VirtualMfaDevice()`

  
  These are the resource's available collections:
  
  *   :py:attr:`groups`

  
  *   :py:attr:`instance_profiles`

  
  *   :py:attr:`policies`

  
  *   :py:attr:`roles`

  
  *   :py:attr:`saml_providers`

  
  *   :py:attr:`server_certificates`

  
  *   :py:attr:`users`

  
  *   :py:attr:`virtual_mfa_devices`

  
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: change_password(**kwargs)

    

    Changes the password of the IAM user who is calling this action. The root account password is not affected by this action.

     

    To change the password for a different user, see  UpdateLoginProfile . For more information about modifying passwords, see `Managing Passwords`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = iam.change_password(
          OldPassword='string',
          NewPassword='string'
      )
    :type OldPassword: string
    :param OldPassword: **[REQUIRED]** 

      The IAM user's current password.

      

    
    :type NewPassword: string
    :param NewPassword: **[REQUIRED]** 

      The new password. The new password must conform to the AWS account's password policy, if one exists.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of almost any printable ASCII character from the space (\u0020) through the end of the ASCII character range (\u00FF). You can also include the tab (\u0009), line feed (\u000A), and carriage return (\u000D) characters. Although any of these characters are valid in a password, note that many tools, such as the AWS Management Console, might restrict the ability to enter certain characters because they have special meaning within that tool.

      

    
    
    :returns: None

  .. py:method:: create_account_alias(**kwargs)

    

    Creates an alias for your AWS account. For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = iam.create_account_alias(
          AccountAlias='string'
      )
    :type AccountAlias: string
    :param AccountAlias: **[REQUIRED]** 

      The account alias to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of lowercase letters, digits, and dashes. You cannot start or finish with a dash, nor can you have two dashes in a row.

      

    
    
    :returns: None

  .. py:method:: create_account_password_policy(**kwargs)

    

    Updates the password policy settings for the AWS account.

     

    .. note::

       

      This action does not support partial updates. No parameters are required, but if you do not specify a parameter, that parameter's value reverts to its default value. See the **Request Parameters** section for each parameter's default value.

       

     

    For more information about using a password policy, see `Managing an IAM Password Policy`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      account_password_policy = iam.create_account_password_policy(
          MinimumPasswordLength=123,
          RequireSymbols=True|False,
          RequireNumbers=True|False,
          RequireUppercaseCharacters=True|False,
          RequireLowercaseCharacters=True|False,
          AllowUsersToChangePassword=True|False,
          MaxPasswordAge=123,
          PasswordReusePrevention=123,
          HardExpiry=True|False
      )
    :type MinimumPasswordLength: integer
    :param MinimumPasswordLength: 

      The minimum number of characters allowed in an IAM user password.

       

      Default value: 6

      

    
    :type RequireSymbols: boolean
    :param RequireSymbols: 

      Specifies whether IAM user passwords must contain at least one of the following non-alphanumeric characters:

       

      ! @ # $ % ^ amp; * ( ) _ + - = [ ] { } | '

       

      Default value: false

      

    
    :type RequireNumbers: boolean
    :param RequireNumbers: 

      Specifies whether IAM user passwords must contain at least one numeric character (0 to 9).

       

      Default value: false

      

    
    :type RequireUppercaseCharacters: boolean
    :param RequireUppercaseCharacters: 

      Specifies whether IAM user passwords must contain at least one uppercase character from the ISO basic Latin alphabet (A to Z).

       

      Default value: false

      

    
    :type RequireLowercaseCharacters: boolean
    :param RequireLowercaseCharacters: 

      Specifies whether IAM user passwords must contain at least one lowercase character from the ISO basic Latin alphabet (a to z).

       

      Default value: false

      

    
    :type AllowUsersToChangePassword: boolean
    :param AllowUsersToChangePassword: 

      Allows all IAM users in your account to use the AWS Management Console to change their own passwords. For more information, see `Letting IAM Users Change Their Own Passwords`_ in the *IAM User Guide* .

       

      Default value: false

      

    
    :type MaxPasswordAge: integer
    :param MaxPasswordAge: 

      The number of days that an IAM user password is valid. The default value of 0 means IAM user passwords never expire.

       

      Default value: 0

      

    
    :type PasswordReusePrevention: integer
    :param PasswordReusePrevention: 

      Specifies the number of previous passwords that IAM users are prevented from reusing. The default value of 0 means IAM users are not prevented from reusing previous passwords.

       

      Default value: 0

      

    
    :type HardExpiry: boolean
    :param HardExpiry: 

      Prevents IAM users from setting a new password after their password has expired.

       

      Default value: false

      

    
    
    :rtype: :py:class:`iam.AccountPasswordPolicy`
    :returns: AccountPasswordPolicy resource
    

  .. py:method:: create_group(**kwargs)

    

    Creates a new group.

     

    For information about the number of groups you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      group = iam.create_group(
          Path='string',
          GroupName='string'
      )
    :type Path: string
    :param Path: 

      The path to the group. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group to create. Do not include the path in this value.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-. The group name must be unique within the account. Group names are not distinguished by case. For example, you cannot create groups named both "ADMINS" and "admins".

      

    
    
    :rtype: :py:class:`iam.Group`
    :returns: Group resource
    

  .. py:method:: create_instance_profile(**kwargs)

    

    Creates a new instance profile. For information about instance profiles, go to `About Instance Profiles`_ .

     

    For information about the number of instance profiles you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      instance_profile = iam.create_instance_profile(
          InstanceProfileName='string',
          Path='string'
      )
    :type InstanceProfileName: string
    :param InstanceProfileName: **[REQUIRED]** 

      The name of the instance profile to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Path: string
    :param Path: 

      The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    
    :rtype: :py:class:`iam.InstanceProfile`
    :returns: InstanceProfile resource
    

  .. py:method:: create_policy(**kwargs)

    

    Creates a new managed policy for your AWS account.

     

    This operation creates a policy version with a version identifier of ``v1`` and sets v1 as the policy's default version. For more information about policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

     

    For more information about managed policies in general, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      policy = iam.create_policy(
          PolicyName='string',
          Path='string',
          PolicyDocument='string',
          Description='string'
      )
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The friendly name of the policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type Path: string
    :param Path: 

      The path for the policy.

       

      For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The JSON policy document that you want to use as the content for the new policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type Description: string
    :param Description: 

      A friendly description of the policy.

       

      Typically used to store information about the permissions defined in the policy. For example, "Grants access to production DynamoDB tables."

       

      The policy description is immutable. After a value is assigned, it cannot be changed.

      

    
    
    :rtype: :py:class:`iam.Policy`
    :returns: Policy resource
    

  .. py:method:: create_role(**kwargs)

    

    Creates a new role for your AWS account. For more information about roles, go to `Working with Roles`_ . For information about limitations on role names and the number of roles you can create, go to `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      role = iam.create_role(
          Path='string',
          RoleName='string',
          AssumeRolePolicyDocument='string'
      )
    :type Path: string
    :param Path: 

      The path to the role. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-. Role names are not distinguished by case. For example, you cannot create roles named both "PRODROLE" and "prodrole".

      

    
    :type AssumeRolePolicyDocument: string
    :param AssumeRolePolicyDocument: **[REQUIRED]** 

      The trust relationship policy document that grants an entity permission to assume the role.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :rtype: :py:class:`iam.Role`
    :returns: Role resource
    

  .. py:method:: create_saml_provider(**kwargs)

    

    Creates an IAM resource that describes an identity provider (IdP) that supports SAML 2.0.

     

    The SAML provider resource that you create with this operation can be used as a principal in an IAM role's trust policy to enable federated users who sign-in using the SAML IdP to assume the role. You can create an IAM role that supports Web-based single sign-on (SSO) to the AWS Management Console or one that supports API access to AWS.

     

    When you create the SAML provider resource, you upload an a SAML metadata document that you get from your IdP and that includes the issuer's name, expiration information, and keys that can be used to validate the SAML authentication response (assertions) that the IdP sends. You must generate the metadata document using the identity management software that is used as your organization's IdP.

     

    .. note::

       

      This operation requires `Signature Version 4`_ .

       

     

    For more information, see `Enabling SAML 2.0 Federated Users to Access the AWS Management Console`_ and `About SAML 2.0-based Federation`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      saml_provider = iam.create_saml_provider(
          SAMLMetadataDocument='string',
          Name='string'
      )
    :type SAMLMetadataDocument: string
    :param SAMLMetadataDocument: **[REQUIRED]** 

      An XML document generated by an identity provider (IdP) that supports SAML 2.0. The document includes the issuer's name, expiration information, and keys that can be used to validate the SAML authentication response (assertions) that are received from the IdP. You must generate the metadata document using the identity management software that is used as your organization's IdP.

       

      For more information, see `About SAML 2.0-based Federation`_ in the *IAM User Guide*  

      

    
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the provider to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: :py:class:`iam.SamlProvider`
    :returns: SamlProvider resource
    

  .. py:method:: create_server_certificate(**kwargs)

    

    Uploads a server certificate entity for the AWS account. The server certificate entity includes a public key certificate, a private key, and an optional certificate chain, which should all be PEM-encoded.

     

    For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

     

    For information about the number of server certificates you can upload, see `Limitations on IAM Entities and Objects`_ in the *IAM User Guide* .

     

    .. note::

       

      Because the body of the public key certificate, private key, and the certificate chain can be large, you should use POST rather than GET when calling ``UploadServerCertificate`` . For information about setting up signatures and authorization through the API, go to `Signing AWS API Requests`_ in the *AWS General Reference* . For general information about using the Query API with IAM, go to `Calling the API by Making HTTP Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      server_certificate = iam.create_server_certificate(
          Path='string',
          ServerCertificateName='string',
          CertificateBody='string',
          PrivateKey='string',
          CertificateChain='string'
      )
    :type Path: string
    :param Path: 

      The path for the server certificate. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/). The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

       

      .. note::

         

        If you are uploading a server certificate specifically for use with Amazon CloudFront distributions, you must specify a path using the ``--path`` option. The path must begin with ``/cloudfront`` and must include a trailing slash (for example, ``/cloudfront/test/`` ).

         

      

    
    :type ServerCertificateName: string
    :param ServerCertificateName: **[REQUIRED]** 

      The name for the server certificate. Do not include the path in this value. The name of the certificate cannot contain any spaces.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type CertificateBody: string
    :param CertificateBody: **[REQUIRED]** 

      The contents of the public key certificate in PEM-encoded format.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type PrivateKey: string
    :param PrivateKey: **[REQUIRED]** 

      The contents of the private key in PEM-encoded format.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type CertificateChain: string
    :param CertificateChain: 

      The contents of the certificate chain. This is typically a concatenation of the PEM-encoded public key certificates of the chain.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :rtype: :py:class:`iam.ServerCertificate`
    :returns: ServerCertificate resource
    

  .. py:method:: create_signing_certificate(**kwargs)

    

    Uploads an X.509 signing certificate and associates it with the specified IAM user. Some AWS services use X.509 signing certificates to validate requests that are signed with a corresponding private key. When you upload the certificate, its default status is ``Active`` .

     

    If the ``UserName`` field is not specified, the IAM user name is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    .. note::

       

      Because the body of a X.509 certificate can be large, you should use POST rather than GET when calling ``UploadSigningCertificate`` . For information about setting up signatures and authorization through the API, go to `Signing AWS API Requests`_ in the *AWS General Reference* . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      signing_certificate = iam.create_signing_certificate(
          UserName='string',
          CertificateBody='string'
      )
    :type UserName: string
    :param UserName: 

      The name of the user the signing certificate is for.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type CertificateBody: string
    :param CertificateBody: **[REQUIRED]** 

      The contents of the signing certificate.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :rtype: :py:class:`iam.SigningCertificate`
    :returns: SigningCertificate resource
    

  .. py:method:: create_user(**kwargs)

    

    Creates a new IAM user for your AWS account.

     

    For information about limitations on the number of IAM users you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      user = iam.create_user(
          Path='string',
          UserName='string'
      )
    :type Path: string
    :param Path: 

      The path for the user name. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to create.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-. User names are not distinguished by case. For example, you cannot create users named both "TESTUSER" and "testuser".

      

    
    
    :rtype: :py:class:`iam.User`
    :returns: User resource
    

  .. py:method:: create_virtual_mfa_device(**kwargs)

    

    Creates a new virtual MFA device for the AWS account. After creating the virtual MFA, use  EnableMFADevice to attach the MFA device to an IAM user. For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device`_ in the *IAM User Guide* .

     

    For information about limits on the number of MFA devices you can create, see `Limitations on Entities`_ in the *IAM User Guide* .

     

    .. warning::

       

      The seed information contained in the QR code and the Base32 string should be treated like any other secret access information, such as your AWS access keys or your passwords. After you provision your virtual device, you should ensure that the information is destroyed following secure procedures.

       

    

    **Request Syntax** 
    ::

      virtual_mfa_device = iam.create_virtual_mfa_device(
          Path='string',
          VirtualMFADeviceName='string'
      )
    :type Path: string
    :param Path: 

      The path for the virtual MFA device. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type VirtualMFADeviceName: string
    :param VirtualMFADeviceName: **[REQUIRED]** 

      The name of the virtual MFA device. Use with path to uniquely identify a virtual MFA device.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: :py:class:`iam.VirtualMfaDevice`
    :returns: VirtualMfaDevice resource
    

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str

  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: AccessKey(user_name,id)

    Creates a AccessKey resource.::

      access_key = iam.AccessKey('user_name','id')

    :type user_name: string
    :param user_name: The AccessKey's user_name identifier. This **must** be set.
    :type id: string
    :param id: The AccessKey's id identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.AccessKey`
    :returns: A AccessKey resource
    

  .. py:method:: AccessKeyPair(user_name,id,secret)

    Creates a AccessKeyPair resource.::

      access_key_pair = iam.AccessKeyPair('user_name','id','secret')

    :type user_name: string
    :param user_name: The AccessKeyPair's user_name identifier. This **must** be set.
    :type id: string
    :param id: The AccessKeyPair's id identifier. This **must** be set.
    :type secret: string
    :param secret: The AccessKeyPair's secret identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.AccessKeyPair`
    :returns: A AccessKeyPair resource
    

  .. py:method:: AccountPasswordPolicy()

    Creates a AccountPasswordPolicy resource.::

      account_password_policy = iam.AccountPasswordPolicy()

    
    :rtype: :py:class:`IAM.AccountPasswordPolicy`
    :returns: A AccountPasswordPolicy resource
    

  .. py:method:: AccountSummary()

    Creates a AccountSummary resource.::

      account_summary = iam.AccountSummary()

    
    :rtype: :py:class:`IAM.AccountSummary`
    :returns: A AccountSummary resource
    

  .. py:method:: AssumeRolePolicy(role_name)

    Creates a AssumeRolePolicy resource.::

      assume_role_policy = iam.AssumeRolePolicy('role_name')

    :type role_name: string
    :param role_name: The AssumeRolePolicy's role_name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.AssumeRolePolicy`
    :returns: A AssumeRolePolicy resource
    

  .. py:method:: CurrentUser()

    Creates a CurrentUser resource.::

      current_user = iam.CurrentUser()

    
    :rtype: :py:class:`IAM.CurrentUser`
    :returns: A CurrentUser resource
    

  .. py:method:: Group(name)

    Creates a Group resource.::

      group = iam.Group('name')

    :type name: string
    :param name: The Group's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.Group`
    :returns: A Group resource
    

  .. py:method:: GroupPolicy(group_name,name)

    Creates a GroupPolicy resource.::

      group_policy = iam.GroupPolicy('group_name','name')

    :type group_name: string
    :param group_name: The GroupPolicy's group_name identifier. This **must** be set.
    :type name: string
    :param name: The GroupPolicy's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.GroupPolicy`
    :returns: A GroupPolicy resource
    

  .. py:method:: InstanceProfile(name)

    Creates a InstanceProfile resource.::

      instance_profile = iam.InstanceProfile('name')

    :type name: string
    :param name: The InstanceProfile's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.InstanceProfile`
    :returns: A InstanceProfile resource
    

  .. py:method:: LoginProfile(user_name)

    Creates a LoginProfile resource.::

      login_profile = iam.LoginProfile('user_name')

    :type user_name: string
    :param user_name: The LoginProfile's user_name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.LoginProfile`
    :returns: A LoginProfile resource
    

  .. py:method:: MfaDevice(user_name,serial_number)

    Creates a MfaDevice resource.::

      mfa_device = iam.MfaDevice('user_name','serial_number')

    :type user_name: string
    :param user_name: The MfaDevice's user_name identifier. This **must** be set.
    :type serial_number: string
    :param serial_number: The MfaDevice's serial_number identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.MfaDevice`
    :returns: A MfaDevice resource
    

  .. py:method:: Policy(policy_arn)

    Creates a Policy resource.::

      policy = iam.Policy('policy_arn')

    :type policy_arn: string
    :param policy_arn: The Policy's policy_arn identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.Policy`
    :returns: A Policy resource
    

  .. py:method:: PolicyVersion(arn,version_id)

    Creates a PolicyVersion resource.::

      policy_version = iam.PolicyVersion('arn','version_id')

    :type arn: string
    :param arn: The PolicyVersion's arn identifier. This **must** be set.
    :type version_id: string
    :param version_id: The PolicyVersion's version_id identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.PolicyVersion`
    :returns: A PolicyVersion resource
    

  .. py:method:: Role(name)

    Creates a Role resource.::

      role = iam.Role('name')

    :type name: string
    :param name: The Role's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.Role`
    :returns: A Role resource
    

  .. py:method:: RolePolicy(role_name,name)

    Creates a RolePolicy resource.::

      role_policy = iam.RolePolicy('role_name','name')

    :type role_name: string
    :param role_name: The RolePolicy's role_name identifier. This **must** be set.
    :type name: string
    :param name: The RolePolicy's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.RolePolicy`
    :returns: A RolePolicy resource
    

  .. py:method:: SamlProvider(arn)

    Creates a SamlProvider resource.::

      saml_provider = iam.SamlProvider('arn')

    :type arn: string
    :param arn: The SamlProvider's arn identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.SamlProvider`
    :returns: A SamlProvider resource
    

  .. py:method:: ServerCertificate(name)

    Creates a ServerCertificate resource.::

      server_certificate = iam.ServerCertificate('name')

    :type name: string
    :param name: The ServerCertificate's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.ServerCertificate`
    :returns: A ServerCertificate resource
    

  .. py:method:: SigningCertificate(user_name,id)

    Creates a SigningCertificate resource.::

      signing_certificate = iam.SigningCertificate('user_name','id')

    :type user_name: string
    :param user_name: The SigningCertificate's user_name identifier. This **must** be set.
    :type id: string
    :param id: The SigningCertificate's id identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.SigningCertificate`
    :returns: A SigningCertificate resource
    

  .. py:method:: User(name)

    Creates a User resource.::

      user = iam.User('name')

    :type name: string
    :param name: The User's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.User`
    :returns: A User resource
    

  .. py:method:: UserPolicy(user_name,name)

    Creates a UserPolicy resource.::

      user_policy = iam.UserPolicy('user_name','name')

    :type user_name: string
    :param user_name: The UserPolicy's user_name identifier. This **must** be set.
    :type name: string
    :param name: The UserPolicy's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.UserPolicy`
    :returns: A UserPolicy resource
    

  .. py:method:: VirtualMfaDevice(serial_number)

    Creates a VirtualMfaDevice resource.::

      virtual_mfa_device = iam.VirtualMfaDevice('serial_number')

    :type serial_number: string
    :param serial_number: The VirtualMfaDevice's serial_number identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.VirtualMfaDevice`
    :returns: A VirtualMfaDevice resource
    
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: groups

    A collection of Group resources

    .. py:method:: all()

      Creates an iterable of all Group resources in the collection.

      **Request Syntax** 
      ::

        group_iterator = iam.groups.all()
        
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Group resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        group_iterator = iam.groups.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. For example, the prefix ``/division_abc/subdivision_xyz/`` gets all groups whose path starts with ``/division_abc/subdivision_xyz/`` .

         

        This parameter is optional. If it is not included, it defaults to a slash (/), listing all groups. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Group resources in the collection.

      **Request Syntax** 
      ::

        group_iterator = iam.groups.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Group resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        group_iterator = iam.groups.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

  .. py:attribute:: instance_profiles

    A collection of InstanceProfile resources

    .. py:method:: all()

      Creates an iterable of all InstanceProfile resources in the collection.

      **Request Syntax** 
      ::

        instance_profile_iterator = iam.instance_profiles.all()
        
      
      :rtype: list(:py:class:`iam.InstanceProfile`)
      :returns: A list of InstanceProfile resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all InstanceProfile resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        instance_profile_iterator = iam.instance_profiles.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. For example, the prefix ``/application_abc/component_xyz/`` gets all instance profiles whose path starts with ``/application_abc/component_xyz/`` .

         

        This parameter is optional. If it is not included, it defaults to a slash (/), listing all instance profiles. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.InstanceProfile`)
      :returns: A list of InstanceProfile resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of InstanceProfile resources in the collection.

      **Request Syntax** 
      ::

        instance_profile_iterator = iam.instance_profiles.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.InstanceProfile`)
      :returns: A list of InstanceProfile resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all InstanceProfile resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        instance_profile_iterator = iam.instance_profiles.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.InstanceProfile`)
      :returns: A list of InstanceProfile resources
      

  .. py:attribute:: policies

    A collection of Policy resources

    .. py:method:: all()

      Creates an iterable of all Policy resources in the collection.

      **Request Syntax** 
      ::

        policy_iterator = iam.policies.all()
        
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Policy resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        policy_iterator = iam.policies.filter(
            Scope='All'|'AWS'|'Local',
            OnlyAttached=True|False,
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type Scope: string
      :param Scope: 

        The scope to use for filtering the results.

         

        To list only AWS managed policies, set ``Scope`` to ``AWS`` . To list only the customer managed policies in your AWS account, set ``Scope`` to ``Local`` .

         

        This parameter is optional. If it is not included, or if it is set to ``All`` , all policies are returned.

        

      
      :type OnlyAttached: boolean
      :param OnlyAttached: 

        A flag to filter the results to only the attached policies.

         

        When ``OnlyAttached`` is ``true`` , the returned list contains only the policies that are attached to an IAM user, group, or role. When ``OnlyAttached`` is ``false`` , or when the parameter is not included, all policies are returned.

        

      
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Policy resources in the collection.

      **Request Syntax** 
      ::

        policy_iterator = iam.policies.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Policy resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        policy_iterator = iam.policies.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

  .. py:attribute:: roles

    A collection of Role resources

    .. py:method:: all()

      Creates an iterable of all Role resources in the collection.

      **Request Syntax** 
      ::

        role_iterator = iam.roles.all()
        
      
      :rtype: list(:py:class:`iam.Role`)
      :returns: A list of Role resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Role resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        role_iterator = iam.roles.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. For example, the prefix ``/application_abc/component_xyz/`` gets all roles whose path starts with ``/application_abc/component_xyz/`` .

         

        This parameter is optional. If it is not included, it defaults to a slash (/), listing all roles. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.Role`)
      :returns: A list of Role resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Role resources in the collection.

      **Request Syntax** 
      ::

        role_iterator = iam.roles.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.Role`)
      :returns: A list of Role resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Role resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        role_iterator = iam.roles.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.Role`)
      :returns: A list of Role resources
      

  .. py:attribute:: saml_providers

    A collection of SamlProvider resources

    .. py:method:: all()

      Creates an iterable of all SamlProvider resources in the collection.

      **Request Syntax** 
      ::

        saml_provider_iterator = iam.saml_providers.all()
        
      
      :rtype: list(:py:class:`iam.SamlProvider`)
      :returns: A list of SamlProvider resources
      

    .. py:method:: filter()

      Creates an iterable of all SamlProvider resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        saml_provider_iterator = iam.saml_providers.filter()
        
      
      :rtype: list(:py:class:`iam.SamlProvider`)
      :returns: A list of SamlProvider resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of SamlProvider resources in the collection.

      **Request Syntax** 
      ::

        saml_provider_iterator = iam.saml_providers.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.SamlProvider`)
      :returns: A list of SamlProvider resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all SamlProvider resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        saml_provider_iterator = iam.saml_providers.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.SamlProvider`)
      :returns: A list of SamlProvider resources
      

  .. py:attribute:: server_certificates

    A collection of ServerCertificate resources

    .. py:method:: all()

      Creates an iterable of all ServerCertificate resources in the collection.

      **Request Syntax** 
      ::

        server_certificate_iterator = iam.server_certificates.all()
        
      
      :rtype: list(:py:class:`iam.ServerCertificate`)
      :returns: A list of ServerCertificate resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all ServerCertificate resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        server_certificate_iterator = iam.server_certificates.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. For example: ``/company/servercerts`` would get all server certificates for which the path starts with ``/company/servercerts`` .

         

        This parameter is optional. If it is not included, it defaults to a slash (/), listing all server certificates. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.ServerCertificate`)
      :returns: A list of ServerCertificate resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of ServerCertificate resources in the collection.

      **Request Syntax** 
      ::

        server_certificate_iterator = iam.server_certificates.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.ServerCertificate`)
      :returns: A list of ServerCertificate resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all ServerCertificate resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        server_certificate_iterator = iam.server_certificates.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.ServerCertificate`)
      :returns: A list of ServerCertificate resources
      

  .. py:attribute:: users

    A collection of User resources

    .. py:method:: all()

      Creates an iterable of all User resources in the collection.

      **Request Syntax** 
      ::

        user_iterator = iam.users.all()
        
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all User resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        user_iterator = iam.users.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. For example: ``/division_abc/subdivision_xyz/`` , which would get all user names whose path starts with ``/division_abc/subdivision_xyz/`` .

         

        This parameter is optional. If it is not included, it defaults to a slash (/), listing all user names. The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of User resources in the collection.

      **Request Syntax** 
      ::

        user_iterator = iam.users.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all User resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        user_iterator = iam.users.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

  .. py:attribute:: virtual_mfa_devices

    A collection of VirtualMfaDevice resources

    .. py:method:: all()

      Creates an iterable of all VirtualMfaDevice resources in the collection.

      **Request Syntax** 
      ::

        virtual_mfa_device_iterator = iam.virtual_mfa_devices.all()
        
      
      :rtype: list(:py:class:`iam.VirtualMfaDevice`)
      :returns: A list of VirtualMfaDevice resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all VirtualMfaDevice resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        virtual_mfa_device_iterator = iam.virtual_mfa_devices.filter(
            AssignmentStatus='Assigned'|'Unassigned'|'Any',
            Marker='string',
            MaxItems=123
        )
      :type AssignmentStatus: string
      :param AssignmentStatus: 

        The status (``Unassigned`` or ``Assigned`` ) of the devices to list. If you do not specify an ``AssignmentStatus`` , the action defaults to ``Any`` which lists both assigned and unassigned virtual MFA devices.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.VirtualMfaDevice`)
      :returns: A list of VirtualMfaDevice resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of VirtualMfaDevice resources in the collection.

      **Request Syntax** 
      ::

        virtual_mfa_device_iterator = iam.virtual_mfa_devices.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.VirtualMfaDevice`)
      :returns: A list of VirtualMfaDevice resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all VirtualMfaDevice resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        virtual_mfa_device_iterator = iam.virtual_mfa_devices.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.VirtualMfaDevice`)
      :returns: A list of VirtualMfaDevice resources
      

=========
AccessKey
=========



.. py:class:: IAM.AccessKey(user_name,id)

  A resource representing an AWS Identity and Access Management (IAM) AccessKey::

    
    import boto3
    
    iam = boto3.resource('iam')
    access_key = iam.AccessKey('user_name','id')

  :type user_name: string
  :param user_name: The AccessKey's user_name identifier. This **must** be set.
  :type id: string
  :param id: The AccessKey's id identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`user_name`

  
  *   :py:attr:`id`

  
  These are the resource's available attributes:
  
  *   :py:attr:`access_key_id`

  
  *   :py:attr:`create_date`

  
  *   :py:attr:`status`

  
  These are the resource's available actions:
  
  *   :py:meth:`activate()`

  
  *   :py:meth:`deactivate()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`User()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: user_name

    *(string)* The AccessKey's user_name identifier. This **must** be set.

  .. py:attribute:: id

    *(string)* The AccessKey's id identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: access_key_id

    

    - *(string) --* 

      The ID for this access key.

      

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date when the access key was created.

      

  .. py:attribute:: status

    

    - *(string) --* 

      The status of the access key. ``Active`` means the key is valid for API calls; ``Inactive`` means it is not.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: activate()

    

    Changes the status of the specified access key from Active to Inactive, or vice versa. This action can be used to disable a user's key as part of a key rotation work flow.

     

    If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    For information about rotating keys, see `Managing Keys and Certificates`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = access_key.activate()
      
    
    :returns: None

  .. py:method:: deactivate()

    

    Changes the status of the specified access key from Active to Inactive, or vice versa. This action can be used to disable a user's key as part of a key rotation work flow.

     

    If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    For information about rotating keys, see `Managing Keys and Certificates`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = access_key.deactivate()
      
    
    :returns: None

  .. py:method:: delete()

    

    Deletes the access key pair associated with the specified IAM user.

     

    If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

    

    **Request Syntax** 
    ::

      response = access_key.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str

  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: User()

    Creates a User resource.::

      user = access_key.User()

    
    :rtype: :py:class:`IAM.User`
    :returns: A User resource
    

=============
AccessKeyPair
=============



.. py:class:: IAM.AccessKeyPair(user_name,id,secret)

  A resource representing an AWS Identity and Access Management (IAM) AccessKeyPair::

    
    import boto3
    
    iam = boto3.resource('iam')
    access_key_pair = iam.AccessKeyPair('user_name','id','secret')

  :type user_name: string
  :param user_name: The AccessKeyPair's user_name identifier. This **must** be set.
  :type id: string
  :param id: The AccessKeyPair's id identifier. This **must** be set.
  :type secret: string
  :param secret: The AccessKeyPair's secret identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`user_name`

  
  *   :py:attr:`id`

  
  *   :py:attr:`secret`

  
  These are the resource's available attributes:
  
  *   :py:attr:`access_key_id`

  
  *   :py:attr:`create_date`

  
  *   :py:attr:`secret_access_key`

  
  *   :py:attr:`status`

  
  These are the resource's available actions:
  
  *   :py:meth:`activate()`

  
  *   :py:meth:`deactivate()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: user_name

    *(string)* The AccessKeyPair's user_name identifier. This **must** be set.

  .. py:attribute:: id

    *(string)* The AccessKeyPair's id identifier. This **must** be set.

  .. py:attribute:: secret

    *(string)* The AccessKeyPair's secret identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: access_key_id

    

    - *(string) --* 

      The ID for this access key.

      

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date when the access key was created.

      

  .. py:attribute:: secret_access_key

    

    - *(string) --* 

      The secret key used to sign requests.

      

  .. py:attribute:: status

    

    - *(string) --* 

      The status of the access key. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not. 

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: activate()

    

    Changes the status of the specified access key from Active to Inactive, or vice versa. This action can be used to disable a user's key as part of a key rotation work flow.

     

    If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    For information about rotating keys, see `Managing Keys and Certificates`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = access_key_pair.activate()
      
    
    :returns: None

  .. py:method:: deactivate()

    

    Changes the status of the specified access key from Active to Inactive, or vice versa. This action can be used to disable a user's key as part of a key rotation work flow.

     

    If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    For information about rotating keys, see `Managing Keys and Certificates`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = access_key_pair.deactivate()
      
    
    :returns: None

  .. py:method:: delete()

    

    Deletes the access key pair associated with the specified IAM user.

     

    If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

    

    **Request Syntax** 
    ::

      response = access_key_pair.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


=====================
AccountPasswordPolicy
=====================



.. py:class:: IAM.AccountPasswordPolicy()

  A resource representing an AWS Identity and Access Management (IAM) AccountPasswordPolicy::

    
    import boto3
    
    iam = boto3.resource('iam')
    account_password_policy = iam.AccountPasswordPolicy()

  
  These are the resource's available attributes:
  
  *   :py:attr:`allow_users_to_change_password`

  
  *   :py:attr:`expire_passwords`

  
  *   :py:attr:`hard_expiry`

  
  *   :py:attr:`max_password_age`

  
  *   :py:attr:`minimum_password_length`

  
  *   :py:attr:`password_reuse_prevention`

  
  *   :py:attr:`require_lowercase_characters`

  
  *   :py:attr:`require_numbers`

  
  *   :py:attr:`require_symbols`

  
  *   :py:attr:`require_uppercase_characters`

  
  These are the resource's available actions:
  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`update()`

  
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: allow_users_to_change_password

    

    - *(boolean) --* 

      Specifies whether IAM users are allowed to change their own password.

      

  .. py:attribute:: expire_passwords

    

    - *(boolean) --* 

      Indicates whether passwords in the account expire. Returns true if MaxPasswordAge is contains a value greater than 0. Returns false if MaxPasswordAge is 0 or not present.

      

  .. py:attribute:: hard_expiry

    

    - *(boolean) --* 

      Specifies whether IAM users are prevented from setting a new password after their password has expired.

      

  .. py:attribute:: max_password_age

    

    - *(integer) --* 

      The number of days that an IAM user password is valid.

      

  .. py:attribute:: minimum_password_length

    

    - *(integer) --* 

      Minimum length to require for IAM user passwords.

      

  .. py:attribute:: password_reuse_prevention

    

    - *(integer) --* 

      Specifies the number of previous passwords that IAM users are prevented from reusing.

      

  .. py:attribute:: require_lowercase_characters

    

    - *(boolean) --* 

      Specifies whether to require lowercase characters for IAM user passwords.

      

  .. py:attribute:: require_numbers

    

    - *(boolean) --* 

      Specifies whether to require numbers for IAM user passwords.

      

  .. py:attribute:: require_symbols

    

    - *(boolean) --* 

      Specifies whether to require symbols for IAM user passwords.

      

  .. py:attribute:: require_uppercase_characters

    

    - *(boolean) --* 

      Specifies whether to require uppercase characters for IAM user passwords.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: delete()

    

    Deletes the password policy for the AWS account. There are no parameters.

    

    **Request Syntax** 

    ::

      response = account_password_policy.delete()
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_account_password_policy` to update the attributes of the AccountPasswordPolicy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      account_password_policy.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_account_password_policy` to update the attributes of the AccountPasswordPolicy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      account_password_policy.reload()
    :returns: None

  .. py:method:: update(**kwargs)

    

    Updates the password policy settings for the AWS account.

     

    .. note::

       

      This action does not support partial updates. No parameters are required, but if you do not specify a parameter, that parameter's value reverts to its default value. See the **Request Parameters** section for each parameter's default value.

       

     

    For more information about using a password policy, see `Managing an IAM Password Policy`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = account_password_policy.update(
          MinimumPasswordLength=123,
          RequireSymbols=True|False,
          RequireNumbers=True|False,
          RequireUppercaseCharacters=True|False,
          RequireLowercaseCharacters=True|False,
          AllowUsersToChangePassword=True|False,
          MaxPasswordAge=123,
          PasswordReusePrevention=123,
          HardExpiry=True|False
      )
    :type MinimumPasswordLength: integer
    :param MinimumPasswordLength: 

      The minimum number of characters allowed in an IAM user password.

       

      Default value: 6

      

    
    :type RequireSymbols: boolean
    :param RequireSymbols: 

      Specifies whether IAM user passwords must contain at least one of the following non-alphanumeric characters:

       

      ! @ # $ % ^ amp; * ( ) _ + - = [ ] { } | '

       

      Default value: false

      

    
    :type RequireNumbers: boolean
    :param RequireNumbers: 

      Specifies whether IAM user passwords must contain at least one numeric character (0 to 9).

       

      Default value: false

      

    
    :type RequireUppercaseCharacters: boolean
    :param RequireUppercaseCharacters: 

      Specifies whether IAM user passwords must contain at least one uppercase character from the ISO basic Latin alphabet (A to Z).

       

      Default value: false

      

    
    :type RequireLowercaseCharacters: boolean
    :param RequireLowercaseCharacters: 

      Specifies whether IAM user passwords must contain at least one lowercase character from the ISO basic Latin alphabet (a to z).

       

      Default value: false

      

    
    :type AllowUsersToChangePassword: boolean
    :param AllowUsersToChangePassword: 

      Allows all IAM users in your account to use the AWS Management Console to change their own passwords. For more information, see `Letting IAM Users Change Their Own Passwords`_ in the *IAM User Guide* .

       

      Default value: false

      

    
    :type MaxPasswordAge: integer
    :param MaxPasswordAge: 

      The number of days that an IAM user password is valid. The default value of 0 means IAM user passwords never expire.

       

      Default value: 0

      

    
    :type PasswordReusePrevention: integer
    :param PasswordReusePrevention: 

      Specifies the number of previous passwords that IAM users are prevented from reusing. The default value of 0 means IAM users are not prevented from reusing previous passwords.

       

      Default value: 0

      

    
    :type HardExpiry: boolean
    :param HardExpiry: 

      Prevents IAM users from setting a new password after their password has expired.

       

      Default value: false

      

    
    
    :returns: None

==============
AccountSummary
==============



.. py:class:: IAM.AccountSummary()

  A resource representing an AWS Identity and Access Management (IAM) AccountSummary::

    
    import boto3
    
    iam = boto3.resource('iam')
    account_summary = iam.AccountSummary()

  
  These are the resource's available attributes:
  
  *   :py:attr:`summary_map`

  
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: summary_map

    

    - *(dict) --* 

      A set of key value pairs containing information about IAM entity usage and IAM quotas.

      
      

      - *(string) --* 
        

        - *(integer) --* 
  


================
AssumeRolePolicy
================



.. py:class:: IAM.AssumeRolePolicy(role_name)

  A resource representing an AWS Identity and Access Management (IAM) AssumeRolePolicy::

    
    import boto3
    
    iam = boto3.resource('iam')
    assume_role_policy = iam.AssumeRolePolicy('role_name')

  :type role_name: string
  :param role_name: The AssumeRolePolicy's role_name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`role_name`

  
  These are the resource's available actions:
  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`update()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Role()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: role_name

    *(string)* The AssumeRolePolicy's role_name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: update(**kwargs)

    

    Updates the policy that grants an IAM entity permission to assume a role. This is typically referred to as the "role trust policy". For more information about roles, go to `Using Roles to Delegate Permissions and Federate Identities`_ .

    

    **Request Syntax** 
    ::

      response = assume_role_policy.update(
          PolicyDocument='string'
      )
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy that grants an entity permission to assume the role.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :returns: None
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Role()

    Creates a Role resource.::

      role = assume_role_policy.Role()

    
    :rtype: :py:class:`IAM.Role`
    :returns: A Role resource
    

===========
CurrentUser
===========



.. py:class:: IAM.CurrentUser()

  A resource representing an AWS Identity and Access Management (IAM) CurrentUser::

    
    import boto3
    
    iam = boto3.resource('iam')
    current_user = iam.CurrentUser()

  
  These are the resource's available attributes:
  
  *   :py:attr:`arn`

  
  *   :py:attr:`create_date`

  
  *   :py:attr:`password_last_used`

  
  *   :py:attr:`path`

  
  *   :py:attr:`user_id`

  
  *   :py:attr:`user_name`

  
  These are the resource's available references:
  
  *   :py:attr:`user`

  
  These are the resource's available collections:
  
  *   :py:attr:`access_keys`

  
  *   :py:attr:`mfa_devices`

  
  *   :py:attr:`signing_certificates`

  
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: arn

    

    - *(string) --* 

      The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date and time, in `ISO 8601 date-time format`_ , when the user was created.

      

  .. py:attribute:: password_last_used

    

    - *(datetime) --* 

      The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

       

       
      * The user does not have a password 
       
      * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
       
      * there is no sign-in data associated with the user 
       

       

      This value is returned only in the  GetUser and  ListUsers actions. 

      

  .. py:attribute:: path

    

    - *(string) --* 

      The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

      

  .. py:attribute:: user_id

    

    - *(string) --* 

      The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

      

  .. py:attribute:: user_name

    

    - *(string) --* 

      The friendly name identifying the user.

      
  .. rst-class:: admonition-title
  
  References
  
  References are related resource instances that have a belongs-to relationship.
  For more information about references refer to the :ref:`Resources Introduction Guide<references_intro>`.
  

  .. py:attribute:: user

    (:py:class:`User`) The related user if set, otherwise ``None``.
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: access_keys

    A collection of AccessKey resources

    .. py:method:: all()

      Creates an iterable of all AccessKey resources in the collection.

      **Request Syntax** 
      ::

        access_key_iterator = current_user.access_keys.all()
        
      
      :rtype: list(:py:class:`iam.AccessKey`)
      :returns: A list of AccessKey resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all AccessKey resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        access_key_iterator = current_user.access_keys.filter(
            UserName='string',
            Marker='string',
            MaxItems=123
        )
      :type UserName: string
      :param UserName: 

        The name of the user.

         

        The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.AccessKey`)
      :returns: A list of AccessKey resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of AccessKey resources in the collection.

      **Request Syntax** 
      ::

        access_key_iterator = current_user.access_keys.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.AccessKey`)
      :returns: A list of AccessKey resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all AccessKey resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        access_key_iterator = current_user.access_keys.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.AccessKey`)
      :returns: A list of AccessKey resources
      

  .. py:attribute:: mfa_devices

    A collection of MfaDevice resources

    .. py:method:: all()

      Creates an iterable of all MfaDevice resources in the collection.

      **Request Syntax** 
      ::

        mfa_device_iterator = current_user.mfa_devices.all()
        
      
      :rtype: list(:py:class:`iam.MfaDevice`)
      :returns: A list of MfaDevice resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all MfaDevice resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        mfa_device_iterator = current_user.mfa_devices.filter(
            UserName='string',
            Marker='string',
            MaxItems=123
        )
      :type UserName: string
      :param UserName: 

        The name of the user whose MFA devices you want to list.

         

        The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.MfaDevice`)
      :returns: A list of MfaDevice resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of MfaDevice resources in the collection.

      **Request Syntax** 
      ::

        mfa_device_iterator = current_user.mfa_devices.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.MfaDevice`)
      :returns: A list of MfaDevice resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all MfaDevice resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        mfa_device_iterator = current_user.mfa_devices.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.MfaDevice`)
      :returns: A list of MfaDevice resources
      

  .. py:attribute:: signing_certificates

    A collection of SigningCertificate resources

    .. py:method:: all()

      Creates an iterable of all SigningCertificate resources in the collection.

      **Request Syntax** 
      ::

        signing_certificate_iterator = current_user.signing_certificates.all()
        
      
      :rtype: list(:py:class:`iam.SigningCertificate`)
      :returns: A list of SigningCertificate resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all SigningCertificate resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        signing_certificate_iterator = current_user.signing_certificates.filter(
            UserName='string',
            Marker='string',
            MaxItems=123
        )
      :type UserName: string
      :param UserName: 

        The name of the IAM user whose signing certificates you want to examine.

         

        The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.SigningCertificate`)
      :returns: A list of SigningCertificate resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of SigningCertificate resources in the collection.

      **Request Syntax** 
      ::

        signing_certificate_iterator = current_user.signing_certificates.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.SigningCertificate`)
      :returns: A list of SigningCertificate resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all SigningCertificate resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        signing_certificate_iterator = current_user.signing_certificates.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.SigningCertificate`)
      :returns: A list of SigningCertificate resources
      

=====
Group
=====



.. py:class:: IAM.Group(name)

  A resource representing an AWS Identity and Access Management (IAM) Group::

    
    import boto3
    
    iam = boto3.resource('iam')
    group = iam.Group('name')

  :type name: string
  :param name: The Group's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`arn`

  
  *   :py:attr:`create_date`

  
  *   :py:attr:`group_id`

  
  *   :py:attr:`group_name`

  
  *   :py:attr:`path`

  
  These are the resource's available actions:
  
  *   :py:meth:`add_user()`

  
  *   :py:meth:`attach_policy()`

  
  *   :py:meth:`create()`

  
  *   :py:meth:`create_policy()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`detach_policy()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`remove_user()`

  
  *   :py:meth:`update()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Policy()`

  
  These are the resource's available collections:
  
  *   :py:attr:`attached_policies`

  
  *   :py:attr:`policies`

  
  *   :py:attr:`users`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: name

    *(string)* The Group's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: arn

    

    - *(string) --* 

      The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date and time, in `ISO 8601 date-time format`_ , when the group was created.

      

  .. py:attribute:: group_id

    

    - *(string) --* 

      The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: group_name

    

    - *(string) --* 

      The friendly name that identifies the group.

      

  .. py:attribute:: path

    

    - *(string) --* 

      The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: add_user(**kwargs)

    

    Adds the specified user to the specified group.

    

    **Request Syntax** 
    ::

      response = group.add_user(
          UserName='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to add.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: attach_policy(**kwargs)

    

    Attaches the specified managed policy to the specified IAM group.

     

    You use this API to attach a managed policy to a group. To embed an inline policy in a group, use  PutGroupPolicy .

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = group.attach_policy(
          PolicyArn='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to attach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: create(**kwargs)

    

    Creates a new group.

     

    For information about the number of groups you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      group = group.create(
          Path='string',
          
      )
    :type Path: string
    :param Path: 

      The path to the group. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    
    :rtype: :py:class:`iam.Group`
    :returns: Group resource
    

  .. py:method:: create_policy(**kwargs)

    

    Adds or updates an inline policy document that is embedded in the specified IAM group.

     

    A user can also have managed policies attached to it. To attach a managed policy to a group, use  AttachGroupPolicy . To create a new managed policy, use  CreatePolicy . For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For information about limits on the number of inline policies that you can embed in a group, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. note::

       

      Because policy documents can be large, you should use POST rather than GET when calling ``PutGroupPolicy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      group_policy = group.create_policy(
          PolicyName='string',
          PolicyDocument='string'
      )
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :rtype: :py:class:`iam.GroupPolicy`
    :returns: GroupPolicy resource
    

  .. py:method:: delete()

    

    Deletes the specified IAM group. The group must not contain any users or have any attached policies.

    

    **Request Syntax** 
    ::

      response = group.delete()
      
    
    :returns: None

  .. py:method:: detach_policy(**kwargs)

    

    Removes the specified managed policy from the specified IAM group.

     

    A group can also have inline policies embedded with it. To delete an inline policy, use the  DeleteGroupPolicy API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = group.detach_policy(
          PolicyArn='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to detach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_group` to update the attributes of the Group resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      group.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_group` to update the attributes of the Group resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      group.reload()
    :returns: None

  .. py:method:: remove_user(**kwargs)

    

    Removes the specified user from the specified group.

    

    **Request Syntax** 
    ::

      response = group.remove_user(
          UserName='string'
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name of the user to remove.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: update(**kwargs)

    

    Updates the name and/or the path of the specified IAM group.

     

    .. warning::

       

      You should understand the implications of changing a group's path or name. For more information, see `Renaming Users and Groups`_ in the *IAM User Guide* .

       

     

    .. note::

       

      To change an IAM group name the requester must have appropriate permissions on both the source object and the target object. For example, to change "Managers" to "MGRs", the entity making the request must have permission on both "Managers" and "MGRs", or must have permission on all (*). For more information about permissions, see `Permissions and Policies`_ . 

       

    

    **Request Syntax** 
    ::

      group = group.update(
          NewPath='string',
          NewGroupName='string'
      )
    :type NewPath: string
    :param NewPath: 

      New path for the IAM group. Only include this if changing the group's path.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type NewGroupName: string
    :param NewGroupName: 

      New name for the IAM group. Only include this if changing the group's name.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: :py:class:`iam.Group`
    :returns: Group resource
    
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Policy(name)

    Creates a GroupPolicy resource.::

      group_policy = group.Policy('name')

    :type name: string
    :param name: The Policy's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.GroupPolicy`
    :returns: A GroupPolicy resource
    
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: attached_policies

    A collection of Policy resources

    .. py:method:: all()

      Creates an iterable of all Policy resources in the collection.

      **Request Syntax** 
      ::

        policy_iterator = group.attached_policies.all()
        
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Policy resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        policy_iterator = group.attached_policies.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

         

        The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Policy resources in the collection.

      **Request Syntax** 
      ::

        policy_iterator = group.attached_policies.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Policy resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        policy_iterator = group.attached_policies.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

  .. py:attribute:: policies

    A collection of GroupPolicy resources

    .. py:method:: all()

      Creates an iterable of all GroupPolicy resources in the collection.

      **Request Syntax** 
      ::

        group_policy_iterator = group.policies.all()
        
      
      :rtype: list(:py:class:`iam.GroupPolicy`)
      :returns: A list of GroupPolicy resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all GroupPolicy resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        group_policy_iterator = group.policies.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.GroupPolicy`)
      :returns: A list of GroupPolicy resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of GroupPolicy resources in the collection.

      **Request Syntax** 
      ::

        group_policy_iterator = group.policies.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.GroupPolicy`)
      :returns: A list of GroupPolicy resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all GroupPolicy resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        group_policy_iterator = group.policies.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.GroupPolicy`)
      :returns: A list of GroupPolicy resources
      

  .. py:attribute:: users

    A collection of User resources

    .. py:method:: all()

      Creates an iterable of all User resources in the collection.

      **Request Syntax** 
      ::

        user_iterator = group.users.all()
        
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all User resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        user_iterator = group.users.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of User resources in the collection.

      **Request Syntax** 
      ::

        user_iterator = group.users.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all User resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        user_iterator = group.users.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

===========
GroupPolicy
===========



.. py:class:: IAM.GroupPolicy(group_name,name)

  A resource representing an AWS Identity and Access Management (IAM) GroupPolicy::

    
    import boto3
    
    iam = boto3.resource('iam')
    group_policy = iam.GroupPolicy('group_name','name')

  :type group_name: string
  :param group_name: The GroupPolicy's group_name identifier. This **must** be set.
  :type name: string
  :param name: The GroupPolicy's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`group_name`

  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`policy_document`

  
  *   :py:attr:`policy_name`

  
  These are the resource's available actions:
  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`put()`

  
  *   :py:meth:`reload()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Group()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: group_name

    *(string)* The GroupPolicy's group_name identifier. This **must** be set.

  .. py:attribute:: name

    *(string)* The GroupPolicy's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: policy_document

    

    - *(string) --* 

      The policy document.

      

  .. py:attribute:: policy_name

    

    - *(string) --* 

      The name of the policy.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: delete()

    

    Deletes the specified inline policy that is embedded in the specified IAM group.

     

    A group can also have managed policies attached to it. To detach a managed policy from a group, use  DetachGroupPolicy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = group_policy.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_group_policy` to update the attributes of the GroupPolicy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      group_policy.load()
    :returns: None

  .. py:method:: put(**kwargs)

    

    Adds or updates an inline policy document that is embedded in the specified IAM group.

     

    A user can also have managed policies attached to it. To attach a managed policy to a group, use  AttachGroupPolicy . To create a new managed policy, use  CreatePolicy . For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For information about limits on the number of inline policies that you can embed in a group, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. note::

       

      Because policy documents can be large, you should use POST rather than GET when calling ``PutGroupPolicy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      response = group_policy.put(
          PolicyDocument='string'
      )
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_group_policy` to update the attributes of the GroupPolicy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      group_policy.reload()
    :returns: None
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Group()

    Creates a Group resource.::

      group = group_policy.Group()

    
    :rtype: :py:class:`IAM.Group`
    :returns: A Group resource
    

===============
InstanceProfile
===============



.. py:class:: IAM.InstanceProfile(name)

  A resource representing an AWS Identity and Access Management (IAM) InstanceProfile::

    
    import boto3
    
    iam = boto3.resource('iam')
    instance_profile = iam.InstanceProfile('name')

  :type name: string
  :param name: The InstanceProfile's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`arn`

  
  *   :py:attr:`create_date`

  
  *   :py:attr:`instance_profile_id`

  
  *   :py:attr:`instance_profile_name`

  
  *   :py:attr:`path`

  
  *   :py:attr:`roles_attribute`

  
  These are the resource's available references:
  
  *   :py:attr:`roles`

  
  These are the resource's available actions:
  
  *   :py:meth:`add_role()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`remove_role()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: name

    *(string)* The InstanceProfile's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: arn

    

    - *(string) --* 

      The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date when the instance profile was created.

      

  .. py:attribute:: instance_profile_id

    

    - *(string) --* 

      The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: instance_profile_name

    

    - *(string) --* 

      The name identifying the instance profile.

      

  .. py:attribute:: path

    

    - *(string) --* 

      The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: roles_attribute

    

    - *(list) --* 

      The role associated with the instance profile.

      
      

      - *(dict) --* 

        Contains information about an IAM role.

         

        This data type is used as a response element in the following actions:

         

         
        *  CreateRole   
         
        *  GetRole   
         
        *  ListRoles   
         

        
        

        - **Path** *(string) --* 

          The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

          
        

        - **RoleName** *(string) --* 

          The friendly name that identifies the role.

          
        

        - **RoleId** *(string) --* 

          The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

          
        

        - **Arn** *(string) --* 

          The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

          
        

        - **CreateDate** *(datetime) --* 

          The date and time, in `ISO 8601 date-time format`_ , when the role was created.

          
        

        - **AssumeRolePolicyDocument** *(string) --* 

          The policy that grants an entity permission to assume the role.

          
    
  
  .. rst-class:: admonition-title
  
  References
  
  References are related resource instances that have a belongs-to relationship.
  For more information about references refer to the :ref:`Resources Introduction Guide<references_intro>`.
  

  .. py:attribute:: roles

    (:py:class:`Role`) The related roles if set, otherwise ``None``.
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: add_role(**kwargs)

    

    Adds the specified IAM role to the specified instance profile.

     

    .. note::

       

      The caller of this API must be granted the ``PassRole`` permission on the IAM role by a permission policy.

       

     

    For more information about roles, go to `Working with Roles`_ . For more information about instance profiles, go to `About Instance Profiles`_ .

    

    **Request Syntax** 
    ::

      response = instance_profile.add_role(
          RoleName='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to add.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: delete()

    

    Deletes the specified instance profile. The instance profile must not have an associated role.

     

    .. warning::

       

      Make sure you do not have any Amazon EC2 instances running with the instance profile you are about to delete. Deleting a role or instance profile that is associated with a running instance will break any applications running on the instance.

       

     

    For more information about instance profiles, go to `About Instance Profiles`_ .

    

    **Request Syntax** 
    ::

      response = instance_profile.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_instance_profile` to update the attributes of the InstanceProfile resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      instance_profile.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_instance_profile` to update the attributes of the InstanceProfile resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      instance_profile.reload()
    :returns: None

  .. py:method:: remove_role(**kwargs)

    

    Removes the specified IAM role from the specified EC2 instance profile.

     

    .. warning::

       

      Make sure you do not have any Amazon EC2 instances running with the role you are about to remove from the instance profile. Removing a role from an instance profile that is associated with a running instance break any applications running on the instance.

       

     

    For more information about IAM roles, go to `Working with Roles`_ . For more information about instance profiles, go to `About Instance Profiles`_ .

    

    **Request Syntax** 
    ::

      response = instance_profile.remove_role(
          RoleName='string'
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name of the role to remove.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

============
LoginProfile
============



.. py:class:: IAM.LoginProfile(user_name)

  A resource representing an AWS Identity and Access Management (IAM) LoginProfile::

    
    import boto3
    
    iam = boto3.resource('iam')
    login_profile = iam.LoginProfile('user_name')

  :type user_name: string
  :param user_name: The LoginProfile's user_name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`user_name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`create_date`

  
  *   :py:attr:`password_reset_required`

  
  These are the resource's available actions:
  
  *   :py:meth:`create()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`update()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`User()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: user_name

    *(string)* The LoginProfile's user_name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date when the password for the user was created.

      

  .. py:attribute:: password_reset_required

    

    - *(boolean) --* 

      Specifies whether the user is required to set a new password on next sign-in.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: create(**kwargs)

    

    Creates a password for the specified user, giving the user the ability to access AWS services through the AWS Management Console. For more information about managing passwords, see `Managing Passwords`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      login_profile = login_profile.create(
          Password='string',
          PasswordResetRequired=True|False
      )
    :type Password: string
    :param Password: **[REQUIRED]** 

      The new password for the user.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of almost any printable ASCII character from the space (\u0020) through the end of the ASCII character range (\u00FF). You can also include the tab (\u0009), line feed (\u000A), and carriage return (\u000D) characters. Although any of these characters are valid in a password, note that many tools, such as the AWS Management Console, might restrict the ability to enter certain characters because they have special meaning within that tool.

      

    
    :type PasswordResetRequired: boolean
    :param PasswordResetRequired: 

      Specifies whether the user is required to set a new password on next sign-in.

      

    
    
    :rtype: :py:class:`iam.LoginProfile`
    :returns: LoginProfile resource
    

  .. py:method:: delete()

    

    Deletes the password for the specified IAM user, which terminates the user's ability to access AWS services through the AWS Management Console.

     

    .. warning::

       

      Deleting a user's password does not prevent a user from accessing AWS through the command line interface or the API. To prevent all user access you must also either make any access keys inactive or delete them. For more information about making keys inactive or deleting them, see  UpdateAccessKey and  DeleteAccessKey . 

       

    

    **Request Syntax** 
    ::

      response = login_profile.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_login_profile` to update the attributes of the LoginProfile resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      login_profile.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_login_profile` to update the attributes of the LoginProfile resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      login_profile.reload()
    :returns: None

  .. py:method:: update(**kwargs)

    

    Changes the password for the specified IAM user.

     

    IAM users can change their own passwords by calling  ChangePassword . For more information about modifying passwords, see `Managing Passwords`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = login_profile.update(
          Password='string',
          PasswordResetRequired=True|False
      )
    :type Password: string
    :param Password: 

      The new password for the specified IAM user.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D). However, the format can be further restricted by the account administrator by setting a password policy on the AWS account. For more information, see  UpdateAccountPasswordPolicy .

      

    
    :type PasswordResetRequired: boolean
    :param PasswordResetRequired: 

      Allows this new password to be used only once by requiring the specified IAM user to set a new password on next sign-in.

      

    
    
    :returns: None
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: User()

    Creates a User resource.::

      user = login_profile.User()

    
    :rtype: :py:class:`IAM.User`
    :returns: A User resource
    

=========
MfaDevice
=========



.. py:class:: IAM.MfaDevice(user_name,serial_number)

  A resource representing an AWS Identity and Access Management (IAM) MfaDevice::

    
    import boto3
    
    iam = boto3.resource('iam')
    mfa_device = iam.MfaDevice('user_name','serial_number')

  :type user_name: string
  :param user_name: The MfaDevice's user_name identifier. This **must** be set.
  :type serial_number: string
  :param serial_number: The MfaDevice's serial_number identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`user_name`

  
  *   :py:attr:`serial_number`

  
  These are the resource's available attributes:
  
  *   :py:attr:`enable_date`

  
  These are the resource's available actions:
  
  *   :py:meth:`associate()`

  
  *   :py:meth:`disassociate()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`resync()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`User()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: user_name

    *(string)* The MfaDevice's user_name identifier. This **must** be set.

  .. py:attribute:: serial_number

    *(string)* The MfaDevice's serial_number identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: enable_date

    

    - *(datetime) --* 

      The date when the MFA device was enabled for the user.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: associate(**kwargs)

    

    Enables the specified MFA device and associates it with the specified IAM user. When enabled, the MFA device is required for every subsequent login by the IAM user associated with the device.

    

    **Request Syntax** 
    ::

      response = mfa_device.associate(
          AuthenticationCode1='string',
          AuthenticationCode2='string'
      )
    :type AuthenticationCode1: string
    :param AuthenticationCode1: **[REQUIRED]** 

      An authentication code emitted by the device.

       

      The format for this parameter is a string of 6 digits.

      

    
    :type AuthenticationCode2: string
    :param AuthenticationCode2: **[REQUIRED]** 

      A subsequent authentication code emitted by the device.

       

      The format for this parameter is a string of 6 digits.

      

    
    
    :returns: None

  .. py:method:: disassociate()

    

    Deactivates the specified MFA device and removes it from association with the user name for which it was originally enabled.

     

    For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = mfa_device.disassociate()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: resync(**kwargs)

    

    Synchronizes the specified MFA device with its IAM resource object on the AWS servers.

     

    For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = mfa_device.resync(
          AuthenticationCode1='string',
          AuthenticationCode2='string'
      )
    :type AuthenticationCode1: string
    :param AuthenticationCode1: **[REQUIRED]** 

      An authentication code emitted by the device.

       

      The format for this parameter is a sequence of six digits.

      

    
    :type AuthenticationCode2: string
    :param AuthenticationCode2: **[REQUIRED]** 

      A subsequent authentication code emitted by the device.

       

      The format for this parameter is a sequence of six digits.

      

    
    
    :returns: None
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: User()

    Creates a User resource.::

      user = mfa_device.User()

    
    :rtype: :py:class:`IAM.User`
    :returns: A User resource
    

======
Policy
======



.. py:class:: IAM.Policy(arn)

  A resource representing an AWS Identity and Access Management (IAM) Policy::

    
    import boto3
    
    iam = boto3.resource('iam')
    policy = iam.Policy('arn')

  :type arn: string
  :param arn: The Policy's arn identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`arn`

  
  These are the resource's available attributes:
  
  *   :py:attr:`attachment_count`

  
  *   :py:attr:`create_date`

  
  *   :py:attr:`default_version_id`

  
  *   :py:attr:`description`

  
  *   :py:attr:`is_attachable`

  
  *   :py:attr:`path`

  
  *   :py:attr:`policy_id`

  
  *   :py:attr:`policy_name`

  
  *   :py:attr:`update_date`

  
  These are the resource's available references:
  
  *   :py:attr:`default_version`

  
  These are the resource's available actions:
  
  *   :py:meth:`attach_group()`

  
  *   :py:meth:`attach_role()`

  
  *   :py:meth:`attach_user()`

  
  *   :py:meth:`create_version()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`detach_group()`

  
  *   :py:meth:`detach_role()`

  
  *   :py:meth:`detach_user()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  These are the resource's available collections:
  
  *   :py:attr:`attached_groups`

  
  *   :py:attr:`attached_roles`

  
  *   :py:attr:`attached_users`

  
  *   :py:attr:`versions`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: arn

    *(string)* The Policy's arn identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: attachment_count

    

    - *(integer) --* 

      The number of entities (users, groups, and roles) that the policy is attached to.

      

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date and time, in `ISO 8601 date-time format`_ , when the policy was created.

      

  .. py:attribute:: default_version_id

    

    - *(string) --* 

      The identifier for the version of the policy that is set as the default version.

      

  .. py:attribute:: description

    

    - *(string) --* 

      A friendly description of the policy.

       

      This element is included in the response to the  GetPolicy operation. It is not included in the response to the  ListPolicies operation. 

      

  .. py:attribute:: is_attachable

    

    - *(boolean) --* 

      Specifies whether the policy can be attached to an IAM user, group, or role.

      

  .. py:attribute:: path

    

    - *(string) --* 

      The path to the policy.

       

      For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

      

  .. py:attribute:: policy_id

    

    - *(string) --* 

      The stable and unique string identifying the policy.

       

      For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

      

  .. py:attribute:: policy_name

    

    - *(string) --* 

      The friendly name (not ARN) identifying the policy.

      

  .. py:attribute:: update_date

    

    - *(datetime) --* 

      The date and time, in `ISO 8601 date-time format`_ , when the policy was last updated.

       

      When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created.

      
  .. rst-class:: admonition-title
  
  References
  
  References are related resource instances that have a belongs-to relationship.
  For more information about references refer to the :ref:`Resources Introduction Guide<references_intro>`.
  

  .. py:attribute:: default_version

    (:py:class:`PolicyVersion`) The related default_version if set, otherwise ``None``.
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: attach_group(**kwargs)

    

    Attaches the specified managed policy to the specified IAM group.

     

    You use this API to attach a managed policy to a group. To embed an inline policy in a group, use  PutGroupPolicy .

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = policy.attach_group(
          GroupName='string',
          
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the group to attach the policy to.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: attach_role(**kwargs)

    

    Attaches the specified managed policy to the specified IAM role.

     

    When you attach a managed policy to a role, the managed policy becomes part of the role's permission (access) policy. You cannot use a managed policy as the role's trust policy. The role's trust policy is created at the same time as the role, using  CreateRole . You can update a role's trust policy using  UpdateAssumeRolePolicy .

     

    Use this API to attach a *managed* policy to a role. To embed an inline policy in a role, use  PutRolePolicy . For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = policy.attach_role(
          RoleName='string',
          
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the role to attach the policy to.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: attach_user(**kwargs)

    

    Attaches the specified managed policy to the specified user.

     

    You use this API to attach a *managed* policy to a user. To embed an inline policy in a user, use  PutUserPolicy .

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = policy.attach_user(
          UserName='string',
          
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the IAM user to attach the policy to.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: create_version(**kwargs)

    

    Creates a new version of the specified managed policy. To update a managed policy, you create a new policy version. A managed policy can have up to five versions. If the policy has five versions, you must delete an existing version using  DeletePolicyVersion before you create a new version.

     

    Optionally, you can set the new version as the policy's default version. The default version is the version that is in effect for the IAM users, groups, and roles to which the policy is attached.

     

    For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      policy_version = policy.create_version(
          PolicyDocument='string',
          SetAsDefault=True|False
      )
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The JSON policy document that you want to use as the content for this new version of the policy.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    :type SetAsDefault: boolean
    :param SetAsDefault: 

      Specifies whether to set this version as the policy's default version.

       

      When this parameter is ``true`` , the new policy version becomes the operative version; that is, the version that is in effect for the IAM users, groups, and roles that the policy is attached to.

       

      For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

      

    
    
    :rtype: :py:class:`iam.PolicyVersion`
    :returns: PolicyVersion resource
    

  .. py:method:: delete()

    

    Deletes the specified managed policy.

     

    Before you can delete a managed policy, you must first detach the policy from all users, groups, and roles that it is attached to, and you must delete all of the policy's versions. The following steps describe the process for deleting a managed policy:

     

     
    * Detach the policy from all users, groups, and roles that the policy is attached to, using the  DetachUserPolicy ,  DetachGroupPolicy , or  DetachRolePolicy APIs. To list all the users, groups, and roles that a policy is attached to, use  ListEntitiesForPolicy . 
     
    * Delete all versions of the policy using  DeletePolicyVersion . To list the policy's versions, use  ListPolicyVersions . You cannot use  DeletePolicyVersion to delete the version that is marked as the default version. You delete the policy's default version in the next step of the process. 
     
    * Delete the policy (this automatically deletes the policy's default version) using this API. 
     

     

    For information about managed policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = policy.delete()
      
    
    :returns: None

  .. py:method:: detach_group(**kwargs)

    

    Removes the specified managed policy from the specified IAM group.

     

    A group can also have inline policies embedded with it. To delete an inline policy, use the  DeleteGroupPolicy API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = policy.detach_group(
          GroupName='string',
          
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the IAM group to detach the policy from.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: detach_role(**kwargs)

    

    Removes the specified managed policy from the specified role.

     

    A role can also have inline policies embedded with it. To delete an inline policy, use the  DeleteRolePolicy API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = policy.detach_role(
          RoleName='string',
          
      )
    :type RoleName: string
    :param RoleName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the IAM role to detach the policy from.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: detach_user(**kwargs)

    

    Removes the specified managed policy from the specified user.

     

    A user can also have inline policies embedded with it. To delete an inline policy, use the  DeleteUserPolicy API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = policy.detach_user(
          UserName='string',
          
      )
    :type UserName: string
    :param UserName: **[REQUIRED]** 

      The name (friendly name, not ARN) of the IAM user to detach the policy from.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_policy` to update the attributes of the Policy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      policy.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_policy` to update the attributes of the Policy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      policy.reload()
    :returns: None
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: attached_groups

    A collection of Group resources

    .. py:method:: all()

      Creates an iterable of all Group resources in the collection.

      **Request Syntax** 
      ::

        group_iterator = policy.attached_groups.all()
        
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Group resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        group_iterator = policy.attached_groups.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all entities.

         

        The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Group resources in the collection.

      **Request Syntax** 
      ::

        group_iterator = policy.attached_groups.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Group resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        group_iterator = policy.attached_groups.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

  .. py:attribute:: attached_roles

    A collection of Role resources

    .. py:method:: all()

      Creates an iterable of all Role resources in the collection.

      **Request Syntax** 
      ::

        role_iterator = policy.attached_roles.all()
        
      
      :rtype: list(:py:class:`iam.Role`)
      :returns: A list of Role resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Role resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        role_iterator = policy.attached_roles.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all entities.

         

        The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.Role`)
      :returns: A list of Role resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Role resources in the collection.

      **Request Syntax** 
      ::

        role_iterator = policy.attached_roles.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.Role`)
      :returns: A list of Role resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Role resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        role_iterator = policy.attached_roles.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.Role`)
      :returns: A list of Role resources
      

  .. py:attribute:: attached_users

    A collection of User resources

    .. py:method:: all()

      Creates an iterable of all User resources in the collection.

      **Request Syntax** 
      ::

        user_iterator = policy.attached_users.all()
        
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all User resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        user_iterator = policy.attached_users.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all entities.

         

        The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of User resources in the collection.

      **Request Syntax** 
      ::

        user_iterator = policy.attached_users.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all User resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        user_iterator = policy.attached_users.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.User`)
      :returns: A list of User resources
      

  .. py:attribute:: versions

    A collection of PolicyVersion resources

    .. py:method:: all()

      Creates an iterable of all PolicyVersion resources in the collection.

      **Request Syntax** 
      ::

        policy_version_iterator = policy.versions.all()
        
      
      :rtype: list(:py:class:`iam.PolicyVersion`)
      :returns: A list of PolicyVersion resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all PolicyVersion resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        policy_version_iterator = policy.versions.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.PolicyVersion`)
      :returns: A list of PolicyVersion resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of PolicyVersion resources in the collection.

      **Request Syntax** 
      ::

        policy_version_iterator = policy.versions.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.PolicyVersion`)
      :returns: A list of PolicyVersion resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all PolicyVersion resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        policy_version_iterator = policy.versions.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.PolicyVersion`)
      :returns: A list of PolicyVersion resources
      

=============
PolicyVersion
=============



.. py:class:: IAM.PolicyVersion(arn,version_id)

  A resource representing an AWS Identity and Access Management (IAM) PolicyVersion::

    
    import boto3
    
    iam = boto3.resource('iam')
    policy_version = iam.PolicyVersion('arn','version_id')

  :type arn: string
  :param arn: The PolicyVersion's arn identifier. This **must** be set.
  :type version_id: string
  :param version_id: The PolicyVersion's version_id identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`arn`

  
  *   :py:attr:`version_id`

  
  These are the resource's available attributes:
  
  *   :py:attr:`create_date`

  
  *   :py:attr:`document`

  
  *   :py:attr:`is_default_version`

  
  These are the resource's available actions:
  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`set_as_default()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: arn

    *(string)* The PolicyVersion's arn identifier. This **must** be set.

  .. py:attribute:: version_id

    *(string)* The PolicyVersion's version_id identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date and time, in `ISO 8601 date-time format`_ , when the policy version was created.

      

  .. py:attribute:: document

    

    - *(string) --* 

      The policy document.

       

      The policy document is returned in the response to the  GetPolicyVersion and  GetAccountAuthorizationDetails operations. It is not returned in the response to the  CreatePolicyVersion or  ListPolicyVersions operations. 

      

  .. py:attribute:: is_default_version

    

    - *(boolean) --* 

      Specifies whether the policy version is set as the policy's default version.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: delete()

    

    Deletes the specified version from the specified managed policy.

     

    You cannot delete the default version from a policy using this API. To delete the default version from a policy, use  DeletePolicy . To find out which version of a policy is marked as the default version, use  ListPolicyVersions .

     

    For information about versions for managed policies, see `Versioning for Managed Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = policy_version.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_policy_version` to update the attributes of the PolicyVersion resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      policy_version.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_policy_version` to update the attributes of the PolicyVersion resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      policy_version.reload()
    :returns: None

  .. py:method:: set_as_default()

    

    Sets the specified version of the specified policy as the policy's default (operative) version.

     

    This action affects all users, groups, and roles that the policy is attached to. To list the users, groups, and roles that the policy is attached to, use the  ListEntitiesForPolicy API.

     

    For information about managed policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = policy_version.set_as_default()
      
    
    :returns: None

====
Role
====



.. py:class:: IAM.Role(name)

  A resource representing an AWS Identity and Access Management (IAM) Role::

    
    import boto3
    
    iam = boto3.resource('iam')
    role = iam.Role('name')

  :type name: string
  :param name: The Role's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`arn`

  
  *   :py:attr:`assume_role_policy_document`

  
  *   :py:attr:`create_date`

  
  *   :py:attr:`path`

  
  *   :py:attr:`role_id`

  
  *   :py:attr:`role_name`

  
  These are the resource's available actions:
  
  *   :py:meth:`attach_policy()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`detach_policy()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`AssumeRolePolicy()`

  
  *   :py:meth:`Policy()`

  
  These are the resource's available collections:
  
  *   :py:attr:`attached_policies`

  
  *   :py:attr:`instance_profiles`

  
  *   :py:attr:`policies`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: name

    *(string)* The Role's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: arn

    

    - *(string) --* 

      The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: assume_role_policy_document

    

    - *(string) --* 

      The policy that grants an entity permission to assume the role.

      

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date and time, in `ISO 8601 date-time format`_ , when the role was created.

      

  .. py:attribute:: path

    

    - *(string) --* 

      The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: role_id

    

    - *(string) --* 

      The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: role_name

    

    - *(string) --* 

      The friendly name that identifies the role.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: attach_policy(**kwargs)

    

    Attaches the specified managed policy to the specified IAM role.

     

    When you attach a managed policy to a role, the managed policy becomes part of the role's permission (access) policy. You cannot use a managed policy as the role's trust policy. The role's trust policy is created at the same time as the role, using  CreateRole . You can update a role's trust policy using  UpdateAssumeRolePolicy .

     

    Use this API to attach a *managed* policy to a role. To embed an inline policy in a role, use  PutRolePolicy . For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = role.attach_policy(
          PolicyArn='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to attach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: delete()

    

    Deletes the specified role. The role must not have any policies attached. For more information about roles, go to `Working with Roles`_ .

     

    .. warning::

       

      Make sure you do not have any Amazon EC2 instances running with the role you are about to delete. Deleting a role or instance profile that is associated with a running instance will break any applications running on the instance.

       

    

    **Request Syntax** 
    ::

      response = role.delete()
      
    
    :returns: None

  .. py:method:: detach_policy(**kwargs)

    

    Removes the specified managed policy from the specified role.

     

    A role can also have inline policies embedded with it. To delete an inline policy, use the  DeleteRolePolicy API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = role.detach_policy(
          PolicyArn='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to detach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_role` to update the attributes of the Role resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      role.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_role` to update the attributes of the Role resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      role.reload()
    :returns: None
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: AssumeRolePolicy()

    Creates a AssumeRolePolicy resource.::

      assume_role_policy = role.AssumeRolePolicy()

    
    :rtype: :py:class:`IAM.AssumeRolePolicy`
    :returns: A AssumeRolePolicy resource
    

  .. py:method:: Policy(name)

    Creates a RolePolicy resource.::

      role_policy = role.Policy('name')

    :type name: string
    :param name: The Policy's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.RolePolicy`
    :returns: A RolePolicy resource
    
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: attached_policies

    A collection of Policy resources

    .. py:method:: all()

      Creates an iterable of all Policy resources in the collection.

      **Request Syntax** 
      ::

        policy_iterator = role.attached_policies.all()
        
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Policy resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        policy_iterator = role.attached_policies.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

         

        The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Policy resources in the collection.

      **Request Syntax** 
      ::

        policy_iterator = role.attached_policies.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Policy resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        policy_iterator = role.attached_policies.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

  .. py:attribute:: instance_profiles

    A collection of InstanceProfile resources

    .. py:method:: all()

      Creates an iterable of all InstanceProfile resources in the collection.

      **Request Syntax** 
      ::

        instance_profile_iterator = role.instance_profiles.all()
        
      
      :rtype: list(:py:class:`iam.InstanceProfile`)
      :returns: A list of InstanceProfile resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all InstanceProfile resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        instance_profile_iterator = role.instance_profiles.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.InstanceProfile`)
      :returns: A list of InstanceProfile resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of InstanceProfile resources in the collection.

      **Request Syntax** 
      ::

        instance_profile_iterator = role.instance_profiles.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.InstanceProfile`)
      :returns: A list of InstanceProfile resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all InstanceProfile resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        instance_profile_iterator = role.instance_profiles.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.InstanceProfile`)
      :returns: A list of InstanceProfile resources
      

  .. py:attribute:: policies

    A collection of RolePolicy resources

    .. py:method:: all()

      Creates an iterable of all RolePolicy resources in the collection.

      **Request Syntax** 
      ::

        role_policy_iterator = role.policies.all()
        
      
      :rtype: list(:py:class:`iam.RolePolicy`)
      :returns: A list of RolePolicy resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all RolePolicy resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        role_policy_iterator = role.policies.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.RolePolicy`)
      :returns: A list of RolePolicy resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of RolePolicy resources in the collection.

      **Request Syntax** 
      ::

        role_policy_iterator = role.policies.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.RolePolicy`)
      :returns: A list of RolePolicy resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all RolePolicy resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        role_policy_iterator = role.policies.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.RolePolicy`)
      :returns: A list of RolePolicy resources
      

==========
RolePolicy
==========



.. py:class:: IAM.RolePolicy(role_name,name)

  A resource representing an AWS Identity and Access Management (IAM) RolePolicy::

    
    import boto3
    
    iam = boto3.resource('iam')
    role_policy = iam.RolePolicy('role_name','name')

  :type role_name: string
  :param role_name: The RolePolicy's role_name identifier. This **must** be set.
  :type name: string
  :param name: The RolePolicy's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`role_name`

  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`policy_document`

  
  *   :py:attr:`policy_name`

  
  These are the resource's available actions:
  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`put()`

  
  *   :py:meth:`reload()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Role()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: role_name

    *(string)* The RolePolicy's role_name identifier. This **must** be set.

  .. py:attribute:: name

    *(string)* The RolePolicy's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: policy_document

    

    - *(string) --* 

      The policy document.

      

  .. py:attribute:: policy_name

    

    - *(string) --* 

      The name of the policy.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: delete()

    

    Deletes the specified inline policy that is embedded in the specified IAM role.

     

    A role can also have managed policies attached to it. To detach a managed policy from a role, use  DetachRolePolicy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = role_policy.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_role_policy` to update the attributes of the RolePolicy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      role_policy.load()
    :returns: None

  .. py:method:: put(**kwargs)

    

    Adds or updates an inline policy document that is embedded in the specified IAM role.

     

    When you embed an inline policy in a role, the inline policy is used as part of the role's access (permissions) policy. The role's trust policy is created at the same time as the role, using  CreateRole . You can update a role's trust policy using  UpdateAssumeRolePolicy . For more information about IAM roles, go to `Using Roles to Delegate Permissions and Federate Identities`_ .

     

    A role can also have a managed policy attached to it. To attach a managed policy to a role, use  AttachRolePolicy . To create a new managed policy, use  CreatePolicy . For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For information about limits on the number of inline policies that you can embed with a role, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. note::

       

      Because policy documents can be large, you should use POST rather than GET when calling ``PutRolePolicy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      response = role_policy.put(
          PolicyDocument='string'
      )
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_role_policy` to update the attributes of the RolePolicy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      role_policy.reload()
    :returns: None
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Role()

    Creates a Role resource.::

      role = role_policy.Role()

    
    :rtype: :py:class:`IAM.Role`
    :returns: A Role resource
    

============
SamlProvider
============



.. py:class:: IAM.SamlProvider(arn)

  A resource representing an AWS Identity and Access Management (IAM) SamlProvider::

    
    import boto3
    
    iam = boto3.resource('iam')
    saml_provider = iam.SamlProvider('arn')

  :type arn: string
  :param arn: The SamlProvider's arn identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`arn`

  
  These are the resource's available attributes:
  
  *   :py:attr:`create_date`

  
  *   :py:attr:`saml_metadata_document`

  
  *   :py:attr:`valid_until`

  
  These are the resource's available actions:
  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`update()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: arn

    *(string)* The SamlProvider's arn identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date and time when the SAML provider was created.

      

  .. py:attribute:: saml_metadata_document

    

    - *(string) --* 

      The XML metadata document that includes information about an identity provider.

      

  .. py:attribute:: valid_until

    

    - *(datetime) --* 

      The expiration date and time for the SAML provider.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: delete()

    

    Deletes a SAML provider resource in IAM.

     

    Deleting the provider resource from IAM does not update any roles that reference the SAML provider resource's ARN as a principal in their trust policies. Any attempt to assume a role that references a non-existent provider resource ARN fails.

     

    .. note::

       

      This operation requires `Signature Version 4`_ .

       

    

    **Request Syntax** 
    ::

      response = saml_provider.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_saml_provider` to update the attributes of the SamlProvider resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      saml_provider.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_saml_provider` to update the attributes of the SamlProvider resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      saml_provider.reload()
    :returns: None

  .. py:method:: update(**kwargs)

    

    Updates the metadata document for an existing SAML provider resource object.

     

    .. note::

       

      This operation requires `Signature Version 4`_ .

       

    

    **Request Syntax** 
    ::

      response = saml_provider.update(
          SAMLMetadataDocument='string',
          
      )
    :type SAMLMetadataDocument: string
    :param SAMLMetadataDocument: **[REQUIRED]** 

      An XML document generated by an identity provider (IdP) that supports SAML 2.0. The document includes the issuer's name, expiration information, and keys that can be used to validate the SAML authentication response (assertions) that are received from the IdP. You must generate the metadata document using the identity management software that is used as your organization's IdP.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SAMLProviderArn': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the response to a successful  UpdateSAMLProvider request. 

        
        

        - **SAMLProviderArn** *(string) --* 

          The Amazon Resource Name (ARN) of the SAML provider that was updated.

          
    

=================
ServerCertificate
=================



.. py:class:: IAM.ServerCertificate(name)

  A resource representing an AWS Identity and Access Management (IAM) ServerCertificate::

    
    import boto3
    
    iam = boto3.resource('iam')
    server_certificate = iam.ServerCertificate('name')

  :type name: string
  :param name: The ServerCertificate's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`certificate_body`

  
  *   :py:attr:`certificate_chain`

  
  *   :py:attr:`server_certificate_metadata`

  
  These are the resource's available actions:
  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`update()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: name

    *(string)* The ServerCertificate's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: certificate_body

    

    - *(string) --* 

      The contents of the public key certificate.

      

  .. py:attribute:: certificate_chain

    

    - *(string) --* 

      The contents of the public key certificate chain.

      

  .. py:attribute:: server_certificate_metadata

    

    - *(dict) --* 

      The meta information of the server certificate, such as its name, path, ID, and ARN.

      
      

      - **Path** *(string) --* 

        The path to the server certificate. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

        
      

      - **ServerCertificateName** *(string) --* 

        The name that identifies the server certificate.

        
      

      - **ServerCertificateId** *(string) --* 

        The stable and unique string identifying the server certificate. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

        
      

      - **Arn** *(string) --* 

        The Amazon Resource Name (ARN) specifying the server certificate. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

        
      

      - **UploadDate** *(datetime) --* 

        The date when the server certificate was uploaded.

        
      

      - **Expiration** *(datetime) --* 

        The date on which the certificate is set to expire.

        
  
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: delete()

    

    Deletes the specified server certificate.

     

    For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

     

    .. warning::

       

      If you are using a server certificate with Elastic Load Balancing, deleting the certificate could have implications for your application. If Elastic Load Balancing doesn't detect the deletion of bound certificates, it may continue to use the certificates. This could cause Elastic Load Balancing to stop accepting traffic. We recommend that you remove the reference to the certificate from Elastic Load Balancing before using this command to delete the certificate. For more information, go to `DeleteLoadBalancerListeners`_ in the *Elastic Load Balancing API Reference* .

       

    

    **Request Syntax** 
    ::

      response = server_certificate.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_server_certificate` to update the attributes of the ServerCertificate resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      server_certificate.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_server_certificate` to update the attributes of the ServerCertificate resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      server_certificate.reload()
    :returns: None

  .. py:method:: update(**kwargs)

    

    Updates the name and/or the path of the specified server certificate stored in IAM.

     

    For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

     

    .. warning::

       

      You should understand the implications of changing a server certificate's path or name. For more information, see `Renaming a Server Certificate`_ in the *IAM User Guide* .

       

     

    .. note::

       

      To change a server certificate name the requester must have appropriate permissions on both the source object and the target object. For example, to change the name from "ProductionCert" to "ProdCert", the entity making the request must have permission on "ProductionCert" and "ProdCert", or must have permission on all (*). For more information about permissions, see `Access Management`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      server_certificate = server_certificate.update(
          NewPath='string',
          NewServerCertificateName='string'
      )
    :type NewPath: string
    :param NewPath: 

      The new path for the server certificate. Include this only if you are updating the server certificate's path.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type NewServerCertificateName: string
    :param NewServerCertificateName: 

      The new name for the server certificate. Include this only if you are updating the server certificate's name. The name of the certificate cannot contain any spaces.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: :py:class:`iam.ServerCertificate`
    :returns: ServerCertificate resource
    

==================
SigningCertificate
==================



.. py:class:: IAM.SigningCertificate(user_name,id)

  A resource representing an AWS Identity and Access Management (IAM) SigningCertificate::

    
    import boto3
    
    iam = boto3.resource('iam')
    signing_certificate = iam.SigningCertificate('user_name','id')

  :type user_name: string
  :param user_name: The SigningCertificate's user_name identifier. This **must** be set.
  :type id: string
  :param id: The SigningCertificate's id identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`user_name`

  
  *   :py:attr:`id`

  
  These are the resource's available attributes:
  
  *   :py:attr:`certificate_body`

  
  *   :py:attr:`certificate_id`

  
  *   :py:attr:`status`

  
  *   :py:attr:`upload_date`

  
  These are the resource's available actions:
  
  *   :py:meth:`activate()`

  
  *   :py:meth:`deactivate()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`User()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: user_name

    *(string)* The SigningCertificate's user_name identifier. This **must** be set.

  .. py:attribute:: id

    *(string)* The SigningCertificate's id identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: certificate_body

    

    - *(string) --* 

      The contents of the signing certificate.

      

  .. py:attribute:: certificate_id

    

    - *(string) --* 

      The ID for the signing certificate.

      

  .. py:attribute:: status

    

    - *(string) --* 

      The status of the signing certificate. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not.

      

  .. py:attribute:: upload_date

    

    - *(datetime) --* 

      The date when the signing certificate was uploaded.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: activate()

    

    Changes the status of the specified user signing certificate from active to disabled, or vice versa. This action can be used to disable an IAM user's signing certificate as part of a certificate rotation work flow.

     

    If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

    

    **Request Syntax** 
    ::

      response = signing_certificate.activate()
      
    
    :returns: None

  .. py:method:: deactivate()

    

    Changes the status of the specified user signing certificate from active to disabled, or vice versa. This action can be used to disable an IAM user's signing certificate as part of a certificate rotation work flow.

     

    If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

    

    **Request Syntax** 
    ::

      response = signing_certificate.deactivate()
      
    
    :returns: None

  .. py:method:: delete()

    

    Deletes a signing certificate associated with the specified IAM user.

     

    If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated IAM users.

    

    **Request Syntax** 
    ::

      response = signing_certificate.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str

  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: User()

    Creates a User resource.::

      user = signing_certificate.User()

    
    :rtype: :py:class:`IAM.User`
    :returns: A User resource
    

====
User
====



.. py:class:: IAM.User(name)

  A resource representing an AWS Identity and Access Management (IAM) User::

    
    import boto3
    
    iam = boto3.resource('iam')
    user = iam.User('name')

  :type name: string
  :param name: The User's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`arn`

  
  *   :py:attr:`create_date`

  
  *   :py:attr:`password_last_used`

  
  *   :py:attr:`path`

  
  *   :py:attr:`user_id`

  
  *   :py:attr:`user_name`

  
  These are the resource's available actions:
  
  *   :py:meth:`add_group()`

  
  *   :py:meth:`attach_policy()`

  
  *   :py:meth:`create()`

  
  *   :py:meth:`create_access_key_pair()`

  
  *   :py:meth:`create_login_profile()`

  
  *   :py:meth:`create_policy()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`detach_policy()`

  
  *   :py:meth:`enable_mfa()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`remove_group()`

  
  *   :py:meth:`update()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`AccessKey()`

  
  *   :py:meth:`LoginProfile()`

  
  *   :py:meth:`MfaDevice()`

  
  *   :py:meth:`Policy()`

  
  *   :py:meth:`SigningCertificate()`

  
  These are the resource's available collections:
  
  *   :py:attr:`access_keys`

  
  *   :py:attr:`attached_policies`

  
  *   :py:attr:`groups`

  
  *   :py:attr:`mfa_devices`

  
  *   :py:attr:`policies`

  
  *   :py:attr:`signing_certificates`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: name

    *(string)* The User's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: arn

    

    - *(string) --* 

      The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

  .. py:attribute:: create_date

    

    - *(datetime) --* 

      The date and time, in `ISO 8601 date-time format`_ , when the user was created.

      

  .. py:attribute:: password_last_used

    

    - *(datetime) --* 

      The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

       

       
      * The user does not have a password 
       
      * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
       
      * there is no sign-in data associated with the user 
       

       

      This value is returned only in the  GetUser and  ListUsers actions. 

      

  .. py:attribute:: path

    

    - *(string) --* 

      The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

      

  .. py:attribute:: user_id

    

    - *(string) --* 

      The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

      

  .. py:attribute:: user_name

    

    - *(string) --* 

      The friendly name identifying the user.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: add_group(**kwargs)

    

    Adds the specified user to the specified group.

    

    **Request Syntax** 
    ::

      response = user.add_group(
          GroupName='string',
          
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group to update.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: attach_policy(**kwargs)

    

    Attaches the specified managed policy to the specified user.

     

    You use this API to attach a *managed* policy to a user. To embed an inline policy in a user, use  PutUserPolicy .

     

    For more information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = user.attach_policy(
          PolicyArn='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to attach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: create(**kwargs)

    

    Creates a new IAM user for your AWS account.

     

    For information about limitations on the number of IAM users you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      user = user.create(
          Path='string',
          
      )
    :type Path: string
    :param Path: 

      The path for the user name. For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* .

       

      This parameter is optional. If it is not included, it defaults to a slash (/).

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    
    :rtype: :py:class:`iam.User`
    :returns: User resource
    

  .. py:method:: create_access_key_pair()

    

    Creates a new AWS secret access key and corresponding AWS access key ID for the specified user. The default status for new keys is ``Active`` .

     

    If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

     

    For information about limits on the number of keys you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. warning::

       

      To ensure the security of your AWS account, the secret access key is accessible only during key and user creation. You must save the key (for example, in a text file) if you want to be able to access it again. If a secret key is lost, you can delete the access keys for the associated user and then create new keys.

       

    

    **Request Syntax** 
    ::

      access_key_pair = user.create_access_key_pair()
      
    
    :rtype: :py:class:`iam.AccessKeyPair`
    :returns: AccessKeyPair resource
    

  .. py:method:: create_login_profile(**kwargs)

    

    Creates a password for the specified user, giving the user the ability to access AWS services through the AWS Management Console. For more information about managing passwords, see `Managing Passwords`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      login_profile = user.create_login_profile(
          Password='string',
          PasswordResetRequired=True|False
      )
    :type Password: string
    :param Password: **[REQUIRED]** 

      The new password for the user.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of almost any printable ASCII character from the space (\u0020) through the end of the ASCII character range (\u00FF). You can also include the tab (\u0009), line feed (\u000A), and carriage return (\u000D) characters. Although any of these characters are valid in a password, note that many tools, such as the AWS Management Console, might restrict the ability to enter certain characters because they have special meaning within that tool.

      

    
    :type PasswordResetRequired: boolean
    :param PasswordResetRequired: 

      Specifies whether the user is required to set a new password on next sign-in.

      

    
    
    :rtype: :py:class:`iam.LoginProfile`
    :returns: LoginProfile resource
    

  .. py:method:: create_policy(**kwargs)

    

    Adds or updates an inline policy document that is embedded in the specified IAM user.

     

    An IAM user can also have a managed policy attached to it. To attach a managed policy to a user, use  AttachUserPolicy . To create a new managed policy, use  CreatePolicy . For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For information about limits on the number of inline policies that you can embed in a user, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. note::

       

      Because policy documents can be large, you should use POST rather than GET when calling ``PutUserPolicy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      user_policy = user.create_policy(
          PolicyName='string',
          PolicyDocument='string'
      )
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :rtype: :py:class:`iam.UserPolicy`
    :returns: UserPolicy resource
    

  .. py:method:: delete()

    

    Deletes the specified IAM user. The user must not belong to any groups or have any access keys, signing certificates, or attached policies.

    

    **Request Syntax** 
    ::

      response = user.delete()
      
    
    :returns: None

  .. py:method:: detach_policy(**kwargs)

    

    Removes the specified managed policy from the specified user.

     

    A user can also have inline policies embedded with it. To delete an inline policy, use the  DeleteUserPolicy API. For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = user.detach_policy(
          PolicyArn='string'
      )
    :type PolicyArn: string
    :param PolicyArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the IAM policy you want to detach.

       

      For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* .

      

    
    
    :returns: None

  .. py:method:: enable_mfa(**kwargs)

    

    Enables the specified MFA device and associates it with the specified IAM user. When enabled, the MFA device is required for every subsequent login by the IAM user associated with the device.

    

    **Request Syntax** 
    ::

      mfa_device = user.enable_mfa(
          SerialNumber='string',
          AuthenticationCode1='string',
          AuthenticationCode2='string'
      )
    :type SerialNumber: string
    :param SerialNumber: **[REQUIRED]** 

      The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =/:,.@-

      

    
    :type AuthenticationCode1: string
    :param AuthenticationCode1: **[REQUIRED]** 

      An authentication code emitted by the device.

       

      The format for this parameter is a string of 6 digits.

      

    
    :type AuthenticationCode2: string
    :param AuthenticationCode2: **[REQUIRED]** 

      A subsequent authentication code emitted by the device.

       

      The format for this parameter is a string of 6 digits.

      

    
    
    :rtype: :py:class:`iam.MfaDevice`
    :returns: MfaDevice resource
    

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_user` to update the attributes of the User resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      user.load()
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_user` to update the attributes of the User resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      user.reload()
    :returns: None

  .. py:method:: remove_group(**kwargs)

    

    Removes the specified user from the specified group.

    

    **Request Syntax** 
    ::

      response = user.remove_group(
          GroupName='string',
          
      )
    :type GroupName: string
    :param GroupName: **[REQUIRED]** 

      The name of the group to update.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :returns: None

  .. py:method:: update(**kwargs)

    

    Updates the name and/or the path of the specified IAM user.

     

    .. warning::

       

      You should understand the implications of changing an IAM user's path or name. For more information, see `Renaming an IAM User`_ and `Renaming an IAM Group`_ in the *IAM User Guide* .

       

     

    .. note::

       

      To change a user name the requester must have appropriate permissions on both the source object and the target object. For example, to change Bob to Robert, the entity making the request must have permission on Bob and Robert, or must have permission on all (*). For more information about permissions, see `Permissions and Policies`_ . 

       

    

    **Request Syntax** 
    ::

      user = user.update(
          NewPath='string',
          NewUserName='string'
      )
    :type NewPath: string
    :param NewPath: 

      New path for the IAM user. Include this parameter only if you're changing the user's path.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

      

    
    :type NewUserName: string
    :param NewUserName: 

      New name for the user. Include this parameter only if you're changing the user's name.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

      

    
    
    :rtype: :py:class:`iam.User`
    :returns: User resource
    
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: AccessKey(id)

    Creates a AccessKey resource.::

      access_key = user.AccessKey('id')

    :type id: string
    :param id: The AccessKey's id identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.AccessKey`
    :returns: A AccessKey resource
    

  .. py:method:: LoginProfile()

    Creates a LoginProfile resource.::

      login_profile = user.LoginProfile()

    
    :rtype: :py:class:`IAM.LoginProfile`
    :returns: A LoginProfile resource
    

  .. py:method:: MfaDevice(serial_number)

    Creates a MfaDevice resource.::

      mfa_device = user.MfaDevice('serial_number')

    :type serial_number: string
    :param serial_number: The MfaDevice's serial_number identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.MfaDevice`
    :returns: A MfaDevice resource
    

  .. py:method:: Policy(name)

    Creates a UserPolicy resource.::

      user_policy = user.Policy('name')

    :type name: string
    :param name: The Policy's name identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.UserPolicy`
    :returns: A UserPolicy resource
    

  .. py:method:: SigningCertificate(id)

    Creates a SigningCertificate resource.::

      signing_certificate = user.SigningCertificate('id')

    :type id: string
    :param id: The SigningCertificate's id identifier. This **must** be set.
    
    :rtype: :py:class:`IAM.SigningCertificate`
    :returns: A SigningCertificate resource
    
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: access_keys

    A collection of AccessKey resources

    .. py:method:: all()

      Creates an iterable of all AccessKey resources in the collection.

      **Request Syntax** 
      ::

        access_key_iterator = user.access_keys.all()
        
      
      :rtype: list(:py:class:`iam.AccessKey`)
      :returns: A list of AccessKey resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all AccessKey resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        access_key_iterator = user.access_keys.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.AccessKey`)
      :returns: A list of AccessKey resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of AccessKey resources in the collection.

      **Request Syntax** 
      ::

        access_key_iterator = user.access_keys.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.AccessKey`)
      :returns: A list of AccessKey resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all AccessKey resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        access_key_iterator = user.access_keys.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.AccessKey`)
      :returns: A list of AccessKey resources
      

  .. py:attribute:: attached_policies

    A collection of Policy resources

    .. py:method:: all()

      Creates an iterable of all Policy resources in the collection.

      **Request Syntax** 
      ::

        policy_iterator = user.attached_policies.all()
        
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Policy resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        policy_iterator = user.attached_policies.filter(
            PathPrefix='string',
            Marker='string',
            MaxItems=123
        )
      :type PathPrefix: string
      :param PathPrefix: 

        The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

         

        The `regex pattern`_ for this parameter is a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

        

      
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Policy resources in the collection.

      **Request Syntax** 
      ::

        policy_iterator = user.attached_policies.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Policy resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        policy_iterator = user.attached_policies.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.Policy`)
      :returns: A list of Policy resources
      

  .. py:attribute:: groups

    A collection of Group resources

    .. py:method:: all()

      Creates an iterable of all Group resources in the collection.

      **Request Syntax** 
      ::

        group_iterator = user.groups.all()
        
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Group resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        group_iterator = user.groups.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Group resources in the collection.

      **Request Syntax** 
      ::

        group_iterator = user.groups.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Group resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        group_iterator = user.groups.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.Group`)
      :returns: A list of Group resources
      

  .. py:attribute:: mfa_devices

    A collection of MfaDevice resources

    .. py:method:: all()

      Creates an iterable of all MfaDevice resources in the collection.

      **Request Syntax** 
      ::

        mfa_device_iterator = user.mfa_devices.all()
        
      
      :rtype: list(:py:class:`iam.MfaDevice`)
      :returns: A list of MfaDevice resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all MfaDevice resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        mfa_device_iterator = user.mfa_devices.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.MfaDevice`)
      :returns: A list of MfaDevice resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of MfaDevice resources in the collection.

      **Request Syntax** 
      ::

        mfa_device_iterator = user.mfa_devices.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.MfaDevice`)
      :returns: A list of MfaDevice resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all MfaDevice resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        mfa_device_iterator = user.mfa_devices.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.MfaDevice`)
      :returns: A list of MfaDevice resources
      

  .. py:attribute:: policies

    A collection of UserPolicy resources

    .. py:method:: all()

      Creates an iterable of all UserPolicy resources in the collection.

      **Request Syntax** 
      ::

        user_policy_iterator = user.policies.all()
        
      
      :rtype: list(:py:class:`iam.UserPolicy`)
      :returns: A list of UserPolicy resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all UserPolicy resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        user_policy_iterator = user.policies.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.UserPolicy`)
      :returns: A list of UserPolicy resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of UserPolicy resources in the collection.

      **Request Syntax** 
      ::

        user_policy_iterator = user.policies.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.UserPolicy`)
      :returns: A list of UserPolicy resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all UserPolicy resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        user_policy_iterator = user.policies.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.UserPolicy`)
      :returns: A list of UserPolicy resources
      

  .. py:attribute:: signing_certificates

    A collection of SigningCertificate resources

    .. py:method:: all()

      Creates an iterable of all SigningCertificate resources in the collection.

      **Request Syntax** 
      ::

        signing_certificate_iterator = user.signing_certificates.all()
        
      
      :rtype: list(:py:class:`iam.SigningCertificate`)
      :returns: A list of SigningCertificate resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all SigningCertificate resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        signing_certificate_iterator = user.signing_certificates.filter(
            Marker='string',
            MaxItems=123
        )
      :type Marker: string
      :param Marker: 

        Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

        

      
      :type MaxItems: integer
      :param MaxItems: 

        Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

         

        This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from.

        

      
      
      :rtype: list(:py:class:`iam.SigningCertificate`)
      :returns: A list of SigningCertificate resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of SigningCertificate resources in the collection.

      **Request Syntax** 
      ::

        signing_certificate_iterator = user.signing_certificates.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`iam.SigningCertificate`)
      :returns: A list of SigningCertificate resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all SigningCertificate resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        signing_certificate_iterator = user.signing_certificates.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`iam.SigningCertificate`)
      :returns: A list of SigningCertificate resources
      

==========
UserPolicy
==========



.. py:class:: IAM.UserPolicy(user_name,name)

  A resource representing an AWS Identity and Access Management (IAM) UserPolicy::

    
    import boto3
    
    iam = boto3.resource('iam')
    user_policy = iam.UserPolicy('user_name','name')

  :type user_name: string
  :param user_name: The UserPolicy's user_name identifier. This **must** be set.
  :type name: string
  :param name: The UserPolicy's name identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`user_name`

  
  *   :py:attr:`name`

  
  These are the resource's available attributes:
  
  *   :py:attr:`policy_document`

  
  *   :py:attr:`policy_name`

  
  These are the resource's available actions:
  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`put()`

  
  *   :py:meth:`reload()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`User()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: user_name

    *(string)* The UserPolicy's user_name identifier. This **must** be set.

  .. py:attribute:: name

    *(string)* The UserPolicy's name identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: policy_document

    

    - *(string) --* 

      The policy document.

      

  .. py:attribute:: policy_name

    

    - *(string) --* 

      The name of the policy.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: delete()

    

    Deletes the specified inline policy that is embedded in the specified IAM user.

     

    A user can also have managed policies attached to it. To detach a managed policy from a user, use  DetachUserPolicy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

    

    **Request Syntax** 
    ::

      response = user_policy.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`IAM.Client.get_user_policy` to update the attributes of the UserPolicy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      user_policy.load()
    :returns: None

  .. py:method:: put(**kwargs)

    

    Adds or updates an inline policy document that is embedded in the specified IAM user.

     

    An IAM user can also have a managed policy attached to it. To attach a managed policy to a user, use  AttachUserPolicy . To create a new managed policy, use  CreatePolicy . For information about policies, see `Managed Policies and Inline Policies`_ in the *IAM User Guide* .

     

    For information about limits on the number of inline policies that you can embed in a user, see `Limitations on IAM Entities`_ in the *IAM User Guide* .

     

    .. note::

       

      Because policy documents can be large, you should use POST rather than GET when calling ``PutUserPolicy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *IAM User Guide* .

       

    

    **Request Syntax** 
    ::

      response = user_policy.put(
          PolicyDocument='string'
      )
    :type PolicyDocument: string
    :param PolicyDocument: **[REQUIRED]** 

      The policy document.

       

      The `regex pattern`_ for this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range (\u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

      

    
    
    :returns: None

  .. py:method:: reload()

    Calls :py:meth:`IAM.Client.get_user_policy` to update the attributes of the UserPolicy resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      user_policy.reload()
    :returns: None
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: User()

    Creates a User resource.::

      user = user_policy.User()

    
    :rtype: :py:class:`IAM.User`
    :returns: A User resource
    

================
VirtualMfaDevice
================



.. py:class:: IAM.VirtualMfaDevice(serial_number)

  A resource representing an AWS Identity and Access Management (IAM) VirtualMfaDevice::

    
    import boto3
    
    iam = boto3.resource('iam')
    virtual_mfa_device = iam.VirtualMfaDevice('serial_number')

  :type serial_number: string
  :param serial_number: The VirtualMfaDevice's serial_number identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`serial_number`

  
  These are the resource's available attributes:
  
  *   :py:attr:`base_32_string_seed`

  
  *   :py:attr:`enable_date`

  
  *   :py:attr:`qr_code_png`

  
  *   :py:attr:`user_attribute`

  
  These are the resource's available references:
  
  *   :py:attr:`user`

  
  These are the resource's available actions:
  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: serial_number

    *(string)* The VirtualMfaDevice's serial_number identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: base_32_string_seed

    

    - *(bytes) --* 

      The Base32 seed defined as specified in `RFC3548`_ . The ``Base32StringSeed`` is Base64-encoded. 

      

  .. py:attribute:: enable_date

    

    - *(datetime) --* 

      The date and time on which the virtual MFA device was enabled.

      

  .. py:attribute:: qr_code_png

    

    - *(bytes) --* 

      A QR code PNG image that encodes ``otpauth://totp/$virtualMFADeviceName@$AccountName?secret=$Base32String`` where ``$virtualMFADeviceName`` is one of the create call arguments, ``AccountName`` is the user name if set (otherwise, the account ID otherwise), and ``Base32String`` is the seed in Base32 format. The ``Base32String`` value is Base64-encoded. 

      

  .. py:attribute:: user_attribute

    

    - *(dict) --* 

      Contains information about an IAM user entity.

       

      This data type is used as a response element in the following actions:

       

       
      *  CreateUser   
       
      *  GetUser   
       
      *  ListUsers   
       

      
      

      - **Path** *(string) --* 

        The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

        
      

      - **UserName** *(string) --* 

        The friendly name identifying the user.

        
      

      - **UserId** *(string) --* 

        The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

        
      

      - **Arn** *(string) --* 

        The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

        
      

      - **CreateDate** *(datetime) --* 

        The date and time, in `ISO 8601 date-time format`_ , when the user was created.

        
      

      - **PasswordLastUsed** *(datetime) --* 

        The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

         

         
        * The user does not have a password 
         
        * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
         
        * there is no sign-in data associated with the user 
         

         

        This value is returned only in the  GetUser and  ListUsers actions. 

        
  
  .. rst-class:: admonition-title
  
  References
  
  References are related resource instances that have a belongs-to relationship.
  For more information about references refer to the :ref:`Resources Introduction Guide<references_intro>`.
  

  .. py:attribute:: user

    (:py:class:`User`) The related user if set, otherwise ``None``.
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: delete()

    

    Deletes a virtual MFA device.

     

    .. note::

       

      You must deactivate a user's virtual MFA device before you can delete it. For information about deactivating MFA devices, see  DeactivateMFADevice . 

       

    

    **Request Syntax** 
    ::

      response = virtual_mfa_device.delete()
      
    
    :returns: None

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str
