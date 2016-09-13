

.. _RFC 2047: http://tools.ietf.org/html/rfc2047
.. _RFC 5321: https://tools.ietf.org/html/rfc5321
.. _AWS Java SDK: http://aws.amazon.com/sdk-for-java/
.. _Amazon S3 Developer Guide: http://alpha-docs-aws.amazon.com/AmazonS3/latest/dev/UsingClientSideEncryption.html
.. _Amazon WorkMail Administrator Guide: http://docs.aws.amazon.com/workmail/latest/adminguide/organizations_overview.html
.. _AWS Lambda Developer Guide: http://docs.aws.amazon.com/lambda/latest/dg/API_Invoke.html
.. _RFC 2317: https://tools.ietf.org/html/rfc2317
.. _AWS KMS Developer Guide: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html
.. _RFC 822: https://www.ietf.org/rfc/rfc0822.txt
.. _RFC 3464: https://tools.ietf.org/html/rfc3464
.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/easy-dkim-dns-records.html
.. _RFC 3798: https://tools.ietf.org/html/rfc3798
.. _RFC 3463: https://tools.ietf.org/html/rfc3463
.. _Amazon SNS Developer Guide: http://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html
.. _AWS Ruby SDK: http://aws.amazon.com/sdk-for-ruby/


***
SES
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: SES.Client

  A low-level client representing Amazon Simple Email Service (SES)::

    
    import boto3
    
    client = boto3.client('ses')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`clone_receipt_rule_set`

  
  *   :py:meth:`create_receipt_filter`

  
  *   :py:meth:`create_receipt_rule`

  
  *   :py:meth:`create_receipt_rule_set`

  
  *   :py:meth:`delete_identity`

  
  *   :py:meth:`delete_identity_policy`

  
  *   :py:meth:`delete_receipt_filter`

  
  *   :py:meth:`delete_receipt_rule`

  
  *   :py:meth:`delete_receipt_rule_set`

  
  *   :py:meth:`delete_verified_email_address`

  
  *   :py:meth:`describe_active_receipt_rule_set`

  
  *   :py:meth:`describe_receipt_rule`

  
  *   :py:meth:`describe_receipt_rule_set`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_identity_dkim_attributes`

  
  *   :py:meth:`get_identity_mail_from_domain_attributes`

  
  *   :py:meth:`get_identity_notification_attributes`

  
  *   :py:meth:`get_identity_policies`

  
  *   :py:meth:`get_identity_verification_attributes`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_send_quota`

  
  *   :py:meth:`get_send_statistics`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_identities`

  
  *   :py:meth:`list_identity_policies`

  
  *   :py:meth:`list_receipt_filters`

  
  *   :py:meth:`list_receipt_rule_sets`

  
  *   :py:meth:`list_verified_email_addresses`

  
  *   :py:meth:`put_identity_policy`

  
  *   :py:meth:`reorder_receipt_rule_set`

  
  *   :py:meth:`send_bounce`

  
  *   :py:meth:`send_email`

  
  *   :py:meth:`send_raw_email`

  
  *   :py:meth:`set_active_receipt_rule_set`

  
  *   :py:meth:`set_identity_dkim_enabled`

  
  *   :py:meth:`set_identity_feedback_forwarding_enabled`

  
  *   :py:meth:`set_identity_headers_in_notifications_enabled`

  
  *   :py:meth:`set_identity_mail_from_domain`

  
  *   :py:meth:`set_identity_notification_topic`

  
  *   :py:meth:`set_receipt_rule_position`

  
  *   :py:meth:`update_receipt_rule`

  
  *   :py:meth:`verify_domain_dkim`

  
  *   :py:meth:`verify_domain_identity`

  
  *   :py:meth:`verify_email_address`

  
  *   :py:meth:`verify_email_identity`

  

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


  .. py:method:: clone_receipt_rule_set(**kwargs)

    

    Creates a receipt rule set by cloning an existing one. All receipt rules and configurations are copied to the new receipt rule set and are completely independent of the source rule set.

     

    For information about setting up rule sets, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.clone_receipt_rule_set(
          RuleSetName='string',
          OriginalRuleSetName='string'
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the rule set to create. The name must:

       

       
      * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
       
      * Start and end with a letter or number. 
       
      * Contain less than 64 characters. 
       

      

    
    :type OriginalRuleSetName: string
    :param OriginalRuleSetName: **[REQUIRED]** 

      The name of the rule set to clone.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: create_receipt_filter(**kwargs)

    

    Creates a new IP address filter.

     

    For information about setting up IP address filters, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.create_receipt_filter(
          Filter={
              'Name': 'string',
              'IpFilter': {
                  'Policy': 'Block'|'Allow',
                  'Cidr': 'string'
              }
          }
      )
    :type Filter: dict
    :param Filter: **[REQUIRED]** 

      A data structure that describes the IP address filter to create, which consists of a name, an IP address range, and whether to allow or block mail from it.

      

    
      - **Name** *(string) --* **[REQUIRED]** 

        The name of the IP address filter. The name must:

         

         
        * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
         
        * Start and end with a letter or number. 
         
        * Contain less than 64 characters. 
         

        

      
      - **IpFilter** *(dict) --* **[REQUIRED]** 

        A structure that provides the IP addresses to block or allow, and whether to block or allow incoming mail from them.

        

      
        - **Policy** *(string) --* **[REQUIRED]** 

          Indicates whether to block or allow incoming mail from the specified IP addresses.

          

        
        - **Cidr** *(string) --* **[REQUIRED]** 

          A single IP address or a range of IP addresses that you want to block or allow, specified in Classless Inter-Domain Routing (CIDR) notation. An example of a single email address is 10.0.0.1. An example of a range of IP addresses is 10.0.0.1/24. For more information about CIDR notation, see `RFC 2317`_ .

          

        
      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: create_receipt_rule(**kwargs)

    

    Creates a receipt rule.

     

    For information about setting up receipt rules, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.create_receipt_rule(
          RuleSetName='string',
          After='string',
          Rule={
              'Name': 'string',
              'Enabled': True|False,
              'TlsPolicy': 'Require'|'Optional',
              'Recipients': [
                  'string',
              ],
              'Actions': [
                  {
                      'S3Action': {
                          'TopicArn': 'string',
                          'BucketName': 'string',
                          'ObjectKeyPrefix': 'string',
                          'KmsKeyArn': 'string'
                      },
                      'BounceAction': {
                          'TopicArn': 'string',
                          'SmtpReplyCode': 'string',
                          'StatusCode': 'string',
                          'Message': 'string',
                          'Sender': 'string'
                      },
                      'WorkmailAction': {
                          'TopicArn': 'string',
                          'OrganizationArn': 'string'
                      },
                      'LambdaAction': {
                          'TopicArn': 'string',
                          'FunctionArn': 'string',
                          'InvocationType': 'Event'|'RequestResponse'
                      },
                      'StopAction': {
                          'Scope': 'RuleSet',
                          'TopicArn': 'string'
                      },
                      'AddHeaderAction': {
                          'HeaderName': 'string',
                          'HeaderValue': 'string'
                      },
                      'SNSAction': {
                          'TopicArn': 'string',
                          'Encoding': 'UTF-8'|'Base64'
                      }
                  },
              ],
              'ScanEnabled': True|False
          }
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the rule set to which to add the rule.

      

    
    :type After: string
    :param After: 

      The name of an existing rule after which the new rule will be placed. If this parameter is null, the new rule will be inserted at the beginning of the rule list.

      

    
    :type Rule: dict
    :param Rule: **[REQUIRED]** 

      A data structure that contains the specified rule's name, actions, recipients, domains, enabled status, scan status, and TLS policy.

      

    
      - **Name** *(string) --* **[REQUIRED]** 

        The name of the receipt rule. The name must:

         

         
        * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
         
        * Start and end with a letter or number. 
         
        * Contain less than 64 characters. 
         

        

      
      - **Enabled** *(boolean) --* 

        If ``true`` , the receipt rule is active. The default value is ``false`` .

        

      
      - **TlsPolicy** *(string) --* 

        Specifies whether Amazon SES should require that incoming email is delivered over a connection encrypted with Transport Layer Security (TLS). If this parameter is set to ``Require`` , Amazon SES will bounce emails that are not received over TLS. The default is ``Optional`` .

        

      
      - **Recipients** *(list) --* 

        The recipient domains and email addresses to which the receipt rule applies. If this field is not specified, this rule will match all recipients under all verified domains.

        

      
        - *(string) --* 

        
    
      - **Actions** *(list) --* 

        An ordered list of actions to perform on messages that match at least one of the recipient email addresses or domains specified in the receipt rule.

        

      
        - *(dict) --* 

          An action that Amazon SES can take when it receives an email on behalf of one or more email addresses or domains that you own. An instance of this data type can represent only one action.

           

          For information about setting up receipt rules, see the `Amazon SES Developer Guide`_ .

          

        
          - **S3Action** *(dict) --* 

            Saves the received message to an Amazon Simple Storage Service (Amazon S3) bucket and, optionally, publishes a notification to Amazon SNS.

            

          
            - **TopicArn** *(string) --* 

              The ARN of the Amazon SNS topic to notify when the message is saved to the Amazon S3 bucket. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **BucketName** *(string) --* **[REQUIRED]** 

              The name of the Amazon S3 bucket to which to save the received email.

              

            
            - **ObjectKeyPrefix** *(string) --* 

              The key prefix of the Amazon S3 bucket. The key prefix is similar to a directory name that enables you to store similar data under the same directory in a bucket.

              

            
            - **KmsKeyArn** *(string) --* 

              The customer master key that Amazon SES should use to encrypt your emails before saving them to the Amazon S3 bucket. You can use the default master key or a custom master key you created in AWS KMS as follows:

               

               
              * To use the default master key, provide an ARN in the form of ``arn:aws:kms:REGION:ACCOUNT-ID-WITHOUT-HYPHENS:alias/aws/ses`` . For example, if your AWS account ID is 123456789012 and you want to use the default master key in the US West (Oregon) region, the ARN of the default master key would be ``arn:aws:kms:us-west-2:123456789012:alias/aws/ses`` . If you use the default master key, you don't need to perform any extra steps to give Amazon SES permission to use the key. 
               
              * To use a custom master key you created in AWS KMS, provide the ARN of the master key and ensure that you add a statement to your key's policy to give Amazon SES permission to use it. For more information about giving permissions, see the `Amazon SES Developer Guide`_ . 
               

               

              For more information about key policies, see the `AWS KMS Developer Guide`_ . If you do not specify a master key, Amazon SES will not encrypt your emails.

               

              .. warning::

                 

                Your mail is encrypted by Amazon SES using the Amazon S3 encryption client before the mail is submitted to Amazon S3 for storage. It is not encrypted using Amazon S3 server-side encryption. This means that you must use the Amazon S3 encryption client to decrypt the email after retrieving it from Amazon S3, as the service has no access to use your AWS KMS keys for decryption. This encryption client is currently available with the `AWS Java SDK`_ and `AWS Ruby SDK`_ only. For more information about client-side encryption using AWS KMS master keys, see the `Amazon S3 Developer Guide`_ .

                 

              

            
          
          - **BounceAction** *(dict) --* 

            Rejects the received email by returning a bounce response to the sender and, optionally, publishes a notification to Amazon Simple Notification Service (Amazon SNS).

            

          
            - **TopicArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the bounce action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **SmtpReplyCode** *(string) --* **[REQUIRED]** 

              The SMTP reply code, as defined by `RFC 5321`_ .

              

            
            - **StatusCode** *(string) --* 

              The SMTP enhanced status code, as defined by `RFC 3463`_ .

              

            
            - **Message** *(string) --* **[REQUIRED]** 

              Human-readable text to include in the bounce message.

              

            
            - **Sender** *(string) --* **[REQUIRED]** 

              The email address of the sender of the bounced email. This is the address from which the bounce message will be sent.

              

            
          
          - **WorkmailAction** *(dict) --* 

            Calls Amazon WorkMail and, optionally, publishes a notification to Amazon SNS.

            

          
            - **TopicArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the WorkMail action is called. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **OrganizationArn** *(string) --* **[REQUIRED]** 

              The ARN of the Amazon WorkMail organization. An example of an Amazon WorkMail organization ARN is ``arn:aws:workmail:us-west-2:123456789012:organization/m-68755160c4cb4e29a2b2f8fb58f359d7`` . For information about Amazon WorkMail organizations, see the `Amazon WorkMail Administrator Guide`_ .

              

            
          
          - **LambdaAction** *(dict) --* 

            Calls an AWS Lambda function, and optionally, publishes a notification to Amazon SNS.

            

          
            - **TopicArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the Lambda action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **FunctionArn** *(string) --* **[REQUIRED]** 

              The Amazon Resource Name (ARN) of the AWS Lambda function. An example of an AWS Lambda function ARN is ``arn:aws:lambda:us-west-2:account-id:function:MyFunction`` . For more information about AWS Lambda, see the `AWS Lambda Developer Guide`_ .

              

            
            - **InvocationType** *(string) --* 

              The invocation type of the AWS Lambda function. An invocation type of ``RequestResponse`` means that the execution of the function will immediately result in a response, and a value of ``Event`` means that the function will be invoked asynchronously. The default value is ``Event`` . For information about AWS Lambda invocation types, see the `AWS Lambda Developer Guide`_ .

               

              .. warning::

                 

                There is a 30-second timeout on ``RequestResponse`` invocations. You should use ``Event`` invocation in most cases. Use ``RequestResponse`` only when you want to make a mail flow decision, such as whether to stop the receipt rule or the receipt rule set.

                 

              

            
          
          - **StopAction** *(dict) --* 

            Terminates the evaluation of the receipt rule set and optionally publishes a notification to Amazon SNS.

            

          
            - **Scope** *(string) --* **[REQUIRED]** 

              The scope to which the Stop action applies. That is, what is being stopped.

              

            
            - **TopicArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the stop action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
          
          - **AddHeaderAction** *(dict) --* 

            Adds a header to the received email.

            

          
            - **HeaderName** *(string) --* **[REQUIRED]** 

              The name of the header to add. Must be between 1 and 50 characters, inclusive, and consist of alphanumeric (a-z, A-Z, 0-9) characters and dashes only.

              

            
            - **HeaderValue** *(string) --* **[REQUIRED]** 

              Must be less than 2048 characters, and must not contain newline characters ("\r" or "\n").

              

            
          
          - **SNSAction** *(dict) --* 

            Publishes the email content within a notification to Amazon SNS.

            

          
            - **TopicArn** *(string) --* **[REQUIRED]** 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **Encoding** *(string) --* 

              The encoding to use for the email within the Amazon SNS notification. UTF-8 is easier to use, but may not preserve all special characters when a message was encoded with a different encoding format. Base64 preserves all special characters. The default value is UTF-8.

              

            
          
        
    
      - **ScanEnabled** *(boolean) --* 

        If ``true`` , then messages to which this receipt rule applies are scanned for spam and viruses. The default value is ``false`` .

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: create_receipt_rule_set(**kwargs)

    

    Creates an empty receipt rule set.

     

    For information about setting up receipt rule sets, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.create_receipt_rule_set(
          RuleSetName='string'
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the rule set to create. The name must:

       

       
      * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
       
      * Start and end with a letter or number. 
       
      * Contain less than 64 characters. 
       

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: delete_identity(**kwargs)

    

    Deletes the specified identity (an email address or a domain) from the list of verified identities.

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.delete_identity(
          Identity='string'
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The identity to be removed from the list of identities for the AWS Account.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: delete_identity_policy(**kwargs)

    

    Deletes the specified sending authorization policy for the given identity (an email address or a domain). This API returns successfully even if a policy with the specified name does not exist.

     

    .. note::

       

      This API is for the identity owner only. If you have not verified the identity, this API will return an error.

       

     

    Sending authorization is a feature that enables an identity owner to authorize other senders to use its identities. For information about using sending authorization, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.delete_identity_policy(
          Identity='string',
          PolicyName='string'
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The identity that is associated with the policy that you want to delete. You can specify the identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

       

      To successfully call this API, you must own the identity.

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy to be deleted.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: delete_receipt_filter(**kwargs)

    

    Deletes the specified IP address filter.

     

    For information about managing IP address filters, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.delete_receipt_filter(
          FilterName='string'
      )
    :type FilterName: string
    :param FilterName: **[REQUIRED]** 

      The name of the IP address filter to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: delete_receipt_rule(**kwargs)

    

    Deletes the specified receipt rule.

     

    For information about managing receipt rules, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.delete_receipt_rule(
          RuleSetName='string',
          RuleName='string'
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the receipt rule set that contains the receipt rule to delete.

      

    
    :type RuleName: string
    :param RuleName: **[REQUIRED]** 

      The name of the receipt rule to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: delete_receipt_rule_set(**kwargs)

    

    Deletes the specified receipt rule set and all of the receipt rules it contains.

     

    .. note::

       

      The currently active rule set cannot be deleted.

       

     

    For information about managing receipt rule sets, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.delete_receipt_rule_set(
          RuleSetName='string'
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the receipt rule set to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: delete_verified_email_address(**kwargs)

    

    Deletes the specified email address from the list of verified addresses.

     

    .. warning::

       

      The DeleteVerifiedEmailAddress action is deprecated as of the May 15, 2012 release of Domain Verification. The DeleteIdentity action is now preferred.

       

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.delete_verified_email_address(
          EmailAddress='string'
      )
    :type EmailAddress: string
    :param EmailAddress: **[REQUIRED]** 

      An email address to be removed from the list of verified addresses.

      

    
    
    :returns: None

  .. py:method:: describe_active_receipt_rule_set()

    

    Returns the metadata and receipt rules for the receipt rule set that is currently active.

     

    For information about setting up receipt rule sets, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.describe_active_receipt_rule_set()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Metadata': {
                'Name': 'string',
                'CreatedTimestamp': datetime(2015, 1, 1)
            },
            'Rules': [
                {
                    'Name': 'string',
                    'Enabled': True|False,
                    'TlsPolicy': 'Require'|'Optional',
                    'Recipients': [
                        'string',
                    ],
                    'Actions': [
                        {
                            'S3Action': {
                                'TopicArn': 'string',
                                'BucketName': 'string',
                                'ObjectKeyPrefix': 'string',
                                'KmsKeyArn': 'string'
                            },
                            'BounceAction': {
                                'TopicArn': 'string',
                                'SmtpReplyCode': 'string',
                                'StatusCode': 'string',
                                'Message': 'string',
                                'Sender': 'string'
                            },
                            'WorkmailAction': {
                                'TopicArn': 'string',
                                'OrganizationArn': 'string'
                            },
                            'LambdaAction': {
                                'TopicArn': 'string',
                                'FunctionArn': 'string',
                                'InvocationType': 'Event'|'RequestResponse'
                            },
                            'StopAction': {
                                'Scope': 'RuleSet',
                                'TopicArn': 'string'
                            },
                            'AddHeaderAction': {
                                'HeaderName': 'string',
                                'HeaderValue': 'string'
                            },
                            'SNSAction': {
                                'TopicArn': 'string',
                                'Encoding': 'UTF-8'|'Base64'
                            }
                        },
                    ],
                    'ScanEnabled': True|False
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the metadata and receipt rules for the receipt rule set that is currently active.

        
        

        - **Metadata** *(dict) --* 

          The metadata for the currently active receipt rule set. The metadata consists of the rule set name and a timestamp of when the rule set was created.

          
          

          - **Name** *(string) --* 

            The name of the receipt rule set. The name must:

             

             
            * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
             
            * Start and end with a letter or number. 
             
            * Contain less than 64 characters. 
             

            
          

          - **CreatedTimestamp** *(datetime) --* 

            The date and time the receipt rule set was created.

            
      
        

        - **Rules** *(list) --* 

          The receipt rules that belong to the active rule set.

          
          

          - *(dict) --* 

            Receipt rules enable you to specify which actions Amazon SES should take when it receives mail on behalf of one or more email addresses or domains that you own.

             

            Each receipt rule defines a set of email addresses or domains to which it applies. If the email addresses or domains match at least one recipient address of the message, Amazon SES executes all of the receipt rule's actions on the message.

             

            For information about setting up receipt rules, see the `Amazon SES Developer Guide`_ .

            
            

            - **Name** *(string) --* 

              The name of the receipt rule. The name must:

               

               
              * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
               
              * Start and end with a letter or number. 
               
              * Contain less than 64 characters. 
               

              
            

            - **Enabled** *(boolean) --* 

              If ``true`` , the receipt rule is active. The default value is ``false`` .

              
            

            - **TlsPolicy** *(string) --* 

              Specifies whether Amazon SES should require that incoming email is delivered over a connection encrypted with Transport Layer Security (TLS). If this parameter is set to ``Require`` , Amazon SES will bounce emails that are not received over TLS. The default is ``Optional`` .

              
            

            - **Recipients** *(list) --* 

              The recipient domains and email addresses to which the receipt rule applies. If this field is not specified, this rule will match all recipients under all verified domains.

              
              

              - *(string) --* 
          
            

            - **Actions** *(list) --* 

              An ordered list of actions to perform on messages that match at least one of the recipient email addresses or domains specified in the receipt rule.

              
              

              - *(dict) --* 

                An action that Amazon SES can take when it receives an email on behalf of one or more email addresses or domains that you own. An instance of this data type can represent only one action.

                 

                For information about setting up receipt rules, see the `Amazon SES Developer Guide`_ .

                
                

                - **S3Action** *(dict) --* 

                  Saves the received message to an Amazon Simple Storage Service (Amazon S3) bucket and, optionally, publishes a notification to Amazon SNS.

                  
                  

                  - **TopicArn** *(string) --* 

                    The ARN of the Amazon SNS topic to notify when the message is saved to the Amazon S3 bucket. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **BucketName** *(string) --* 

                    The name of the Amazon S3 bucket to which to save the received email.

                    
                  

                  - **ObjectKeyPrefix** *(string) --* 

                    The key prefix of the Amazon S3 bucket. The key prefix is similar to a directory name that enables you to store similar data under the same directory in a bucket.

                    
                  

                  - **KmsKeyArn** *(string) --* 

                    The customer master key that Amazon SES should use to encrypt your emails before saving them to the Amazon S3 bucket. You can use the default master key or a custom master key you created in AWS KMS as follows:

                     

                     
                    * To use the default master key, provide an ARN in the form of ``arn:aws:kms:REGION:ACCOUNT-ID-WITHOUT-HYPHENS:alias/aws/ses`` . For example, if your AWS account ID is 123456789012 and you want to use the default master key in the US West (Oregon) region, the ARN of the default master key would be ``arn:aws:kms:us-west-2:123456789012:alias/aws/ses`` . If you use the default master key, you don't need to perform any extra steps to give Amazon SES permission to use the key. 
                     
                    * To use a custom master key you created in AWS KMS, provide the ARN of the master key and ensure that you add a statement to your key's policy to give Amazon SES permission to use it. For more information about giving permissions, see the `Amazon SES Developer Guide`_ . 
                     

                     

                    For more information about key policies, see the `AWS KMS Developer Guide`_ . If you do not specify a master key, Amazon SES will not encrypt your emails.

                     

                    .. warning::

                       

                      Your mail is encrypted by Amazon SES using the Amazon S3 encryption client before the mail is submitted to Amazon S3 for storage. It is not encrypted using Amazon S3 server-side encryption. This means that you must use the Amazon S3 encryption client to decrypt the email after retrieving it from Amazon S3, as the service has no access to use your AWS KMS keys for decryption. This encryption client is currently available with the `AWS Java SDK`_ and `AWS Ruby SDK`_ only. For more information about client-side encryption using AWS KMS master keys, see the `Amazon S3 Developer Guide`_ .

                       

                    
              
                

                - **BounceAction** *(dict) --* 

                  Rejects the received email by returning a bounce response to the sender and, optionally, publishes a notification to Amazon Simple Notification Service (Amazon SNS).

                  
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the bounce action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **SmtpReplyCode** *(string) --* 

                    The SMTP reply code, as defined by `RFC 5321`_ .

                    
                  

                  - **StatusCode** *(string) --* 

                    The SMTP enhanced status code, as defined by `RFC 3463`_ .

                    
                  

                  - **Message** *(string) --* 

                    Human-readable text to include in the bounce message.

                    
                  

                  - **Sender** *(string) --* 

                    The email address of the sender of the bounced email. This is the address from which the bounce message will be sent.

                    
              
                

                - **WorkmailAction** *(dict) --* 

                  Calls Amazon WorkMail and, optionally, publishes a notification to Amazon SNS.

                  
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the WorkMail action is called. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **OrganizationArn** *(string) --* 

                    The ARN of the Amazon WorkMail organization. An example of an Amazon WorkMail organization ARN is ``arn:aws:workmail:us-west-2:123456789012:organization/m-68755160c4cb4e29a2b2f8fb58f359d7`` . For information about Amazon WorkMail organizations, see the `Amazon WorkMail Administrator Guide`_ .

                    
              
                

                - **LambdaAction** *(dict) --* 

                  Calls an AWS Lambda function, and optionally, publishes a notification to Amazon SNS.

                  
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the Lambda action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **FunctionArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the AWS Lambda function. An example of an AWS Lambda function ARN is ``arn:aws:lambda:us-west-2:account-id:function:MyFunction`` . For more information about AWS Lambda, see the `AWS Lambda Developer Guide`_ .

                    
                  

                  - **InvocationType** *(string) --* 

                    The invocation type of the AWS Lambda function. An invocation type of ``RequestResponse`` means that the execution of the function will immediately result in a response, and a value of ``Event`` means that the function will be invoked asynchronously. The default value is ``Event`` . For information about AWS Lambda invocation types, see the `AWS Lambda Developer Guide`_ .

                     

                    .. warning::

                       

                      There is a 30-second timeout on ``RequestResponse`` invocations. You should use ``Event`` invocation in most cases. Use ``RequestResponse`` only when you want to make a mail flow decision, such as whether to stop the receipt rule or the receipt rule set.

                       

                    
              
                

                - **StopAction** *(dict) --* 

                  Terminates the evaluation of the receipt rule set and optionally publishes a notification to Amazon SNS.

                  
                  

                  - **Scope** *(string) --* 

                    The scope to which the Stop action applies. That is, what is being stopped.

                    
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the stop action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
              
                

                - **AddHeaderAction** *(dict) --* 

                  Adds a header to the received email.

                  
                  

                  - **HeaderName** *(string) --* 

                    The name of the header to add. Must be between 1 and 50 characters, inclusive, and consist of alphanumeric (a-z, A-Z, 0-9) characters and dashes only.

                    
                  

                  - **HeaderValue** *(string) --* 

                    Must be less than 2048 characters, and must not contain newline characters ("\r" or "\n").

                    
              
                

                - **SNSAction** *(dict) --* 

                  Publishes the email content within a notification to Amazon SNS.

                  
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **Encoding** *(string) --* 

                    The encoding to use for the email within the Amazon SNS notification. UTF-8 is easier to use, but may not preserve all special characters when a message was encoded with a different encoding format. Base64 preserves all special characters. The default value is UTF-8.

                    
              
            
          
            

            - **ScanEnabled** *(boolean) --* 

              If ``true`` , then messages to which this receipt rule applies are scanned for spam and viruses. The default value is ``false`` .

              
        
      
    

  .. py:method:: describe_receipt_rule(**kwargs)

    

    Returns the details of the specified receipt rule.

     

    For information about setting up receipt rules, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.describe_receipt_rule(
          RuleSetName='string',
          RuleName='string'
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the receipt rule set to which the receipt rule belongs.

      

    
    :type RuleName: string
    :param RuleName: **[REQUIRED]** 

      The name of the receipt rule.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Rule': {
                'Name': 'string',
                'Enabled': True|False,
                'TlsPolicy': 'Require'|'Optional',
                'Recipients': [
                    'string',
                ],
                'Actions': [
                    {
                        'S3Action': {
                            'TopicArn': 'string',
                            'BucketName': 'string',
                            'ObjectKeyPrefix': 'string',
                            'KmsKeyArn': 'string'
                        },
                        'BounceAction': {
                            'TopicArn': 'string',
                            'SmtpReplyCode': 'string',
                            'StatusCode': 'string',
                            'Message': 'string',
                            'Sender': 'string'
                        },
                        'WorkmailAction': {
                            'TopicArn': 'string',
                            'OrganizationArn': 'string'
                        },
                        'LambdaAction': {
                            'TopicArn': 'string',
                            'FunctionArn': 'string',
                            'InvocationType': 'Event'|'RequestResponse'
                        },
                        'StopAction': {
                            'Scope': 'RuleSet',
                            'TopicArn': 'string'
                        },
                        'AddHeaderAction': {
                            'HeaderName': 'string',
                            'HeaderValue': 'string'
                        },
                        'SNSAction': {
                            'TopicArn': 'string',
                            'Encoding': 'UTF-8'|'Base64'
                        }
                    },
                ],
                'ScanEnabled': True|False
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the details of a receipt rule.

        
        

        - **Rule** *(dict) --* 

          A data structure that contains the specified receipt rule's name, actions, recipients, domains, enabled status, scan status, and Transport Layer Security (TLS) policy.

          
          

          - **Name** *(string) --* 

            The name of the receipt rule. The name must:

             

             
            * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
             
            * Start and end with a letter or number. 
             
            * Contain less than 64 characters. 
             

            
          

          - **Enabled** *(boolean) --* 

            If ``true`` , the receipt rule is active. The default value is ``false`` .

            
          

          - **TlsPolicy** *(string) --* 

            Specifies whether Amazon SES should require that incoming email is delivered over a connection encrypted with Transport Layer Security (TLS). If this parameter is set to ``Require`` , Amazon SES will bounce emails that are not received over TLS. The default is ``Optional`` .

            
          

          - **Recipients** *(list) --* 

            The recipient domains and email addresses to which the receipt rule applies. If this field is not specified, this rule will match all recipients under all verified domains.

            
            

            - *(string) --* 
        
          

          - **Actions** *(list) --* 

            An ordered list of actions to perform on messages that match at least one of the recipient email addresses or domains specified in the receipt rule.

            
            

            - *(dict) --* 

              An action that Amazon SES can take when it receives an email on behalf of one or more email addresses or domains that you own. An instance of this data type can represent only one action.

               

              For information about setting up receipt rules, see the `Amazon SES Developer Guide`_ .

              
              

              - **S3Action** *(dict) --* 

                Saves the received message to an Amazon Simple Storage Service (Amazon S3) bucket and, optionally, publishes a notification to Amazon SNS.

                
                

                - **TopicArn** *(string) --* 

                  The ARN of the Amazon SNS topic to notify when the message is saved to the Amazon S3 bucket. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                  
                

                - **BucketName** *(string) --* 

                  The name of the Amazon S3 bucket to which to save the received email.

                  
                

                - **ObjectKeyPrefix** *(string) --* 

                  The key prefix of the Amazon S3 bucket. The key prefix is similar to a directory name that enables you to store similar data under the same directory in a bucket.

                  
                

                - **KmsKeyArn** *(string) --* 

                  The customer master key that Amazon SES should use to encrypt your emails before saving them to the Amazon S3 bucket. You can use the default master key or a custom master key you created in AWS KMS as follows:

                   

                   
                  * To use the default master key, provide an ARN in the form of ``arn:aws:kms:REGION:ACCOUNT-ID-WITHOUT-HYPHENS:alias/aws/ses`` . For example, if your AWS account ID is 123456789012 and you want to use the default master key in the US West (Oregon) region, the ARN of the default master key would be ``arn:aws:kms:us-west-2:123456789012:alias/aws/ses`` . If you use the default master key, you don't need to perform any extra steps to give Amazon SES permission to use the key. 
                   
                  * To use a custom master key you created in AWS KMS, provide the ARN of the master key and ensure that you add a statement to your key's policy to give Amazon SES permission to use it. For more information about giving permissions, see the `Amazon SES Developer Guide`_ . 
                   

                   

                  For more information about key policies, see the `AWS KMS Developer Guide`_ . If you do not specify a master key, Amazon SES will not encrypt your emails.

                   

                  .. warning::

                     

                    Your mail is encrypted by Amazon SES using the Amazon S3 encryption client before the mail is submitted to Amazon S3 for storage. It is not encrypted using Amazon S3 server-side encryption. This means that you must use the Amazon S3 encryption client to decrypt the email after retrieving it from Amazon S3, as the service has no access to use your AWS KMS keys for decryption. This encryption client is currently available with the `AWS Java SDK`_ and `AWS Ruby SDK`_ only. For more information about client-side encryption using AWS KMS master keys, see the `Amazon S3 Developer Guide`_ .

                     

                  
            
              

              - **BounceAction** *(dict) --* 

                Rejects the received email by returning a bounce response to the sender and, optionally, publishes a notification to Amazon Simple Notification Service (Amazon SNS).

                
                

                - **TopicArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the bounce action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                  
                

                - **SmtpReplyCode** *(string) --* 

                  The SMTP reply code, as defined by `RFC 5321`_ .

                  
                

                - **StatusCode** *(string) --* 

                  The SMTP enhanced status code, as defined by `RFC 3463`_ .

                  
                

                - **Message** *(string) --* 

                  Human-readable text to include in the bounce message.

                  
                

                - **Sender** *(string) --* 

                  The email address of the sender of the bounced email. This is the address from which the bounce message will be sent.

                  
            
              

              - **WorkmailAction** *(dict) --* 

                Calls Amazon WorkMail and, optionally, publishes a notification to Amazon SNS.

                
                

                - **TopicArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the WorkMail action is called. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                  
                

                - **OrganizationArn** *(string) --* 

                  The ARN of the Amazon WorkMail organization. An example of an Amazon WorkMail organization ARN is ``arn:aws:workmail:us-west-2:123456789012:organization/m-68755160c4cb4e29a2b2f8fb58f359d7`` . For information about Amazon WorkMail organizations, see the `Amazon WorkMail Administrator Guide`_ .

                  
            
              

              - **LambdaAction** *(dict) --* 

                Calls an AWS Lambda function, and optionally, publishes a notification to Amazon SNS.

                
                

                - **TopicArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the Lambda action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                  
                

                - **FunctionArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the AWS Lambda function. An example of an AWS Lambda function ARN is ``arn:aws:lambda:us-west-2:account-id:function:MyFunction`` . For more information about AWS Lambda, see the `AWS Lambda Developer Guide`_ .

                  
                

                - **InvocationType** *(string) --* 

                  The invocation type of the AWS Lambda function. An invocation type of ``RequestResponse`` means that the execution of the function will immediately result in a response, and a value of ``Event`` means that the function will be invoked asynchronously. The default value is ``Event`` . For information about AWS Lambda invocation types, see the `AWS Lambda Developer Guide`_ .

                   

                  .. warning::

                     

                    There is a 30-second timeout on ``RequestResponse`` invocations. You should use ``Event`` invocation in most cases. Use ``RequestResponse`` only when you want to make a mail flow decision, such as whether to stop the receipt rule or the receipt rule set.

                     

                  
            
              

              - **StopAction** *(dict) --* 

                Terminates the evaluation of the receipt rule set and optionally publishes a notification to Amazon SNS.

                
                

                - **Scope** *(string) --* 

                  The scope to which the Stop action applies. That is, what is being stopped.

                  
                

                - **TopicArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the stop action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                  
            
              

              - **AddHeaderAction** *(dict) --* 

                Adds a header to the received email.

                
                

                - **HeaderName** *(string) --* 

                  The name of the header to add. Must be between 1 and 50 characters, inclusive, and consist of alphanumeric (a-z, A-Z, 0-9) characters and dashes only.

                  
                

                - **HeaderValue** *(string) --* 

                  Must be less than 2048 characters, and must not contain newline characters ("\r" or "\n").

                  
            
              

              - **SNSAction** *(dict) --* 

                Publishes the email content within a notification to Amazon SNS.

                
                

                - **TopicArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the Amazon SNS topic to notify. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                  
                

                - **Encoding** *(string) --* 

                  The encoding to use for the email within the Amazon SNS notification. UTF-8 is easier to use, but may not preserve all special characters when a message was encoded with a different encoding format. Base64 preserves all special characters. The default value is UTF-8.

                  
            
          
        
          

          - **ScanEnabled** *(boolean) --* 

            If ``true`` , then messages to which this receipt rule applies are scanned for spam and viruses. The default value is ``false`` .

            
      
    

  .. py:method:: describe_receipt_rule_set(**kwargs)

    

    Returns the details of the specified receipt rule set.

     

    For information about managing receipt rule sets, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.describe_receipt_rule_set(
          RuleSetName='string'
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the receipt rule set to describe.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Metadata': {
                'Name': 'string',
                'CreatedTimestamp': datetime(2015, 1, 1)
            },
            'Rules': [
                {
                    'Name': 'string',
                    'Enabled': True|False,
                    'TlsPolicy': 'Require'|'Optional',
                    'Recipients': [
                        'string',
                    ],
                    'Actions': [
                        {
                            'S3Action': {
                                'TopicArn': 'string',
                                'BucketName': 'string',
                                'ObjectKeyPrefix': 'string',
                                'KmsKeyArn': 'string'
                            },
                            'BounceAction': {
                                'TopicArn': 'string',
                                'SmtpReplyCode': 'string',
                                'StatusCode': 'string',
                                'Message': 'string',
                                'Sender': 'string'
                            },
                            'WorkmailAction': {
                                'TopicArn': 'string',
                                'OrganizationArn': 'string'
                            },
                            'LambdaAction': {
                                'TopicArn': 'string',
                                'FunctionArn': 'string',
                                'InvocationType': 'Event'|'RequestResponse'
                            },
                            'StopAction': {
                                'Scope': 'RuleSet',
                                'TopicArn': 'string'
                            },
                            'AddHeaderAction': {
                                'HeaderName': 'string',
                                'HeaderValue': 'string'
                            },
                            'SNSAction': {
                                'TopicArn': 'string',
                                'Encoding': 'UTF-8'|'Base64'
                            }
                        },
                    ],
                    'ScanEnabled': True|False
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the details of the specified receipt rule set.

        
        

        - **Metadata** *(dict) --* 

          The metadata for the receipt rule set, which consists of the rule set name and the timestamp of when the rule set was created.

          
          

          - **Name** *(string) --* 

            The name of the receipt rule set. The name must:

             

             
            * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
             
            * Start and end with a letter or number. 
             
            * Contain less than 64 characters. 
             

            
          

          - **CreatedTimestamp** *(datetime) --* 

            The date and time the receipt rule set was created.

            
      
        

        - **Rules** *(list) --* 

          A list of the receipt rules that belong to the specified receipt rule set.

          
          

          - *(dict) --* 

            Receipt rules enable you to specify which actions Amazon SES should take when it receives mail on behalf of one or more email addresses or domains that you own.

             

            Each receipt rule defines a set of email addresses or domains to which it applies. If the email addresses or domains match at least one recipient address of the message, Amazon SES executes all of the receipt rule's actions on the message.

             

            For information about setting up receipt rules, see the `Amazon SES Developer Guide`_ .

            
            

            - **Name** *(string) --* 

              The name of the receipt rule. The name must:

               

               
              * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
               
              * Start and end with a letter or number. 
               
              * Contain less than 64 characters. 
               

              
            

            - **Enabled** *(boolean) --* 

              If ``true`` , the receipt rule is active. The default value is ``false`` .

              
            

            - **TlsPolicy** *(string) --* 

              Specifies whether Amazon SES should require that incoming email is delivered over a connection encrypted with Transport Layer Security (TLS). If this parameter is set to ``Require`` , Amazon SES will bounce emails that are not received over TLS. The default is ``Optional`` .

              
            

            - **Recipients** *(list) --* 

              The recipient domains and email addresses to which the receipt rule applies. If this field is not specified, this rule will match all recipients under all verified domains.

              
              

              - *(string) --* 
          
            

            - **Actions** *(list) --* 

              An ordered list of actions to perform on messages that match at least one of the recipient email addresses or domains specified in the receipt rule.

              
              

              - *(dict) --* 

                An action that Amazon SES can take when it receives an email on behalf of one or more email addresses or domains that you own. An instance of this data type can represent only one action.

                 

                For information about setting up receipt rules, see the `Amazon SES Developer Guide`_ .

                
                

                - **S3Action** *(dict) --* 

                  Saves the received message to an Amazon Simple Storage Service (Amazon S3) bucket and, optionally, publishes a notification to Amazon SNS.

                  
                  

                  - **TopicArn** *(string) --* 

                    The ARN of the Amazon SNS topic to notify when the message is saved to the Amazon S3 bucket. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **BucketName** *(string) --* 

                    The name of the Amazon S3 bucket to which to save the received email.

                    
                  

                  - **ObjectKeyPrefix** *(string) --* 

                    The key prefix of the Amazon S3 bucket. The key prefix is similar to a directory name that enables you to store similar data under the same directory in a bucket.

                    
                  

                  - **KmsKeyArn** *(string) --* 

                    The customer master key that Amazon SES should use to encrypt your emails before saving them to the Amazon S3 bucket. You can use the default master key or a custom master key you created in AWS KMS as follows:

                     

                     
                    * To use the default master key, provide an ARN in the form of ``arn:aws:kms:REGION:ACCOUNT-ID-WITHOUT-HYPHENS:alias/aws/ses`` . For example, if your AWS account ID is 123456789012 and you want to use the default master key in the US West (Oregon) region, the ARN of the default master key would be ``arn:aws:kms:us-west-2:123456789012:alias/aws/ses`` . If you use the default master key, you don't need to perform any extra steps to give Amazon SES permission to use the key. 
                     
                    * To use a custom master key you created in AWS KMS, provide the ARN of the master key and ensure that you add a statement to your key's policy to give Amazon SES permission to use it. For more information about giving permissions, see the `Amazon SES Developer Guide`_ . 
                     

                     

                    For more information about key policies, see the `AWS KMS Developer Guide`_ . If you do not specify a master key, Amazon SES will not encrypt your emails.

                     

                    .. warning::

                       

                      Your mail is encrypted by Amazon SES using the Amazon S3 encryption client before the mail is submitted to Amazon S3 for storage. It is not encrypted using Amazon S3 server-side encryption. This means that you must use the Amazon S3 encryption client to decrypt the email after retrieving it from Amazon S3, as the service has no access to use your AWS KMS keys for decryption. This encryption client is currently available with the `AWS Java SDK`_ and `AWS Ruby SDK`_ only. For more information about client-side encryption using AWS KMS master keys, see the `Amazon S3 Developer Guide`_ .

                       

                    
              
                

                - **BounceAction** *(dict) --* 

                  Rejects the received email by returning a bounce response to the sender and, optionally, publishes a notification to Amazon Simple Notification Service (Amazon SNS).

                  
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the bounce action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **SmtpReplyCode** *(string) --* 

                    The SMTP reply code, as defined by `RFC 5321`_ .

                    
                  

                  - **StatusCode** *(string) --* 

                    The SMTP enhanced status code, as defined by `RFC 3463`_ .

                    
                  

                  - **Message** *(string) --* 

                    Human-readable text to include in the bounce message.

                    
                  

                  - **Sender** *(string) --* 

                    The email address of the sender of the bounced email. This is the address from which the bounce message will be sent.

                    
              
                

                - **WorkmailAction** *(dict) --* 

                  Calls Amazon WorkMail and, optionally, publishes a notification to Amazon SNS.

                  
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the WorkMail action is called. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **OrganizationArn** *(string) --* 

                    The ARN of the Amazon WorkMail organization. An example of an Amazon WorkMail organization ARN is ``arn:aws:workmail:us-west-2:123456789012:organization/m-68755160c4cb4e29a2b2f8fb58f359d7`` . For information about Amazon WorkMail organizations, see the `Amazon WorkMail Administrator Guide`_ .

                    
              
                

                - **LambdaAction** *(dict) --* 

                  Calls an AWS Lambda function, and optionally, publishes a notification to Amazon SNS.

                  
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the Lambda action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **FunctionArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the AWS Lambda function. An example of an AWS Lambda function ARN is ``arn:aws:lambda:us-west-2:account-id:function:MyFunction`` . For more information about AWS Lambda, see the `AWS Lambda Developer Guide`_ .

                    
                  

                  - **InvocationType** *(string) --* 

                    The invocation type of the AWS Lambda function. An invocation type of ``RequestResponse`` means that the execution of the function will immediately result in a response, and a value of ``Event`` means that the function will be invoked asynchronously. The default value is ``Event`` . For information about AWS Lambda invocation types, see the `AWS Lambda Developer Guide`_ .

                     

                    .. warning::

                       

                      There is a 30-second timeout on ``RequestResponse`` invocations. You should use ``Event`` invocation in most cases. Use ``RequestResponse`` only when you want to make a mail flow decision, such as whether to stop the receipt rule or the receipt rule set.

                       

                    
              
                

                - **StopAction** *(dict) --* 

                  Terminates the evaluation of the receipt rule set and optionally publishes a notification to Amazon SNS.

                  
                  

                  - **Scope** *(string) --* 

                    The scope to which the Stop action applies. That is, what is being stopped.

                    
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the stop action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
              
                

                - **AddHeaderAction** *(dict) --* 

                  Adds a header to the received email.

                  
                  

                  - **HeaderName** *(string) --* 

                    The name of the header to add. Must be between 1 and 50 characters, inclusive, and consist of alphanumeric (a-z, A-Z, 0-9) characters and dashes only.

                    
                  

                  - **HeaderValue** *(string) --* 

                    Must be less than 2048 characters, and must not contain newline characters ("\r" or "\n").

                    
              
                

                - **SNSAction** *(dict) --* 

                  Publishes the email content within a notification to Amazon SNS.

                  
                  

                  - **TopicArn** *(string) --* 

                    The Amazon Resource Name (ARN) of the Amazon SNS topic to notify. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

                    
                  

                  - **Encoding** *(string) --* 

                    The encoding to use for the email within the Amazon SNS notification. UTF-8 is easier to use, but may not preserve all special characters when a message was encoded with a different encoding format. Base64 preserves all special characters. The default value is UTF-8.

                    
              
            
          
            

            - **ScanEnabled** *(boolean) --* 

              If ``true`` , then messages to which this receipt rule applies are scanned for spam and viruses. The default value is ``false`` .

              
        
      
    

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


  .. py:method:: get_identity_dkim_attributes(**kwargs)

    

    Returns the current status of Easy DKIM signing for an entity. For domain name identities, this action also returns the DKIM tokens that are required for Easy DKIM signing, and whether Amazon SES has successfully verified that these tokens have been published.

     

    This action takes a list of identities as input and returns the following information for each:

     

     
    * Whether Easy DKIM signing is enabled or disabled. 
     
    * A set of DKIM tokens that represent the identity. If the identity is an email address, the tokens represent the domain of that address. 
     
    * Whether Amazon SES has successfully verified the DKIM tokens published in the domain's DNS. This information is only returned for domain name identities, not for email addresses. 
     

     

    This action is throttled at one request per second and can only get DKIM attributes for up to 100 identities at a time.

     

    For more information about creating DNS records using DKIM tokens, go to the `Amazon SES Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.get_identity_dkim_attributes(
          Identities=[
              'string',
          ]
      )
    :type Identities: list
    :param Identities: **[REQUIRED]** 

      A list of one or more verified identities - email addresses, domains, or both.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DkimAttributes': {
                'string': {
                    'DkimEnabled': True|False,
                    'DkimVerificationStatus': 'Pending'|'Success'|'Failed'|'TemporaryFailure'|'NotStarted',
                    'DkimTokens': [
                        'string',
                    ]
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the status of Amazon SES Easy DKIM signing for an identity. For domain identities, this response also contains the DKIM tokens that are required for Easy DKIM signing, and whether Amazon SES successfully verified that these tokens were published.

        
        

        - **DkimAttributes** *(dict) --* 

          The DKIM attributes for an email address or a domain.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents the DKIM attributes of a verified email address or a domain.

              
              

              - **DkimEnabled** *(boolean) --* 

                True if DKIM signing is enabled for email sent from the identity; false otherwise.

                
              

              - **DkimVerificationStatus** *(string) --* 

                Describes whether Amazon SES has successfully verified the DKIM DNS records (tokens) published in the domain name's DNS. (This only applies to domain identities, not email address identities.)

                
              

              - **DkimTokens** *(list) --* 

                A set of character strings that represent the domain's identity. Using these tokens, you will need to create DNS CNAME records that point to DKIM public keys hosted by Amazon SES. Amazon Web Services will eventually detect that you have updated your DNS records; this detection process may take up to 72 hours. Upon successful detection, Amazon SES will be able to DKIM-sign email originating from that domain. (This only applies to domain identities, not email address identities.)

                 

                For more information about creating DNS records using DKIM tokens, go to the `Amazon SES Developer Guide`_ .

                
                

                - *(string) --* 
            
          
      
    
    

  .. py:method:: get_identity_mail_from_domain_attributes(**kwargs)

    

    Returns the custom MAIL FROM attributes for a list of identities (email addresses and/or domains).

     

    This action is throttled at one request per second and can only get custom MAIL FROM attributes for up to 100 identities at a time.

    

    **Request Syntax** 
    ::

      response = client.get_identity_mail_from_domain_attributes(
          Identities=[
              'string',
          ]
      )
    :type Identities: list
    :param Identities: **[REQUIRED]** 

      A list of one or more identities.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MailFromDomainAttributes': {
                'string': {
                    'MailFromDomain': 'string',
                    'MailFromDomainStatus': 'Pending'|'Success'|'Failed'|'TemporaryFailure',
                    'BehaviorOnMXFailure': 'UseDefaultValue'|'RejectMessage'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the custom MAIL FROM attributes for a list of identities.

        
        

        - **MailFromDomainAttributes** *(dict) --* 

          A map of identities to custom MAIL FROM attributes.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents the custom MAIL FROM domain attributes of a verified identity (email address or domain).

              
              

              - **MailFromDomain** *(string) --* 

                The custom MAIL FROM domain that the identity is configured to use.

                
              

              - **MailFromDomainStatus** *(string) --* 

                The state that indicates whether Amazon SES has successfully read the MX record required for custom MAIL FROM domain setup. If the state is ``Success`` , Amazon SES uses the specified custom MAIL FROM domain when the verified identity sends an email. All other states indicate that Amazon SES takes the action described by ``BehaviorOnMXFailure`` .

                
              

              - **BehaviorOnMXFailure** *(string) --* 

                The action that Amazon SES takes if it cannot successfully read the required MX record when you send an email. A value of ``UseDefaultValue`` indicates that if Amazon SES cannot read the required MX record, it uses amazonses.com (or a subdomain of that) as the MAIL FROM domain. A value of ``RejectMessage`` indicates that if Amazon SES cannot read the required MX record, Amazon SES returns a ``MailFromDomainNotVerified`` error and does not send the email.

                 

                The custom MAIL FROM setup states that result in this behavior are ``Pending`` , ``Failed`` , and ``TemporaryFailure`` .

                
          
      
    
    

  .. py:method:: get_identity_notification_attributes(**kwargs)

    

    Given a list of verified identities (email addresses and/or domains), returns a structure describing identity notification attributes.

     

    This action is throttled at one request per second and can only get notification attributes for up to 100 identities at a time.

     

    For more information about using notifications with Amazon SES, see the `Amazon SES Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.get_identity_notification_attributes(
          Identities=[
              'string',
          ]
      )
    :type Identities: list
    :param Identities: **[REQUIRED]** 

      A list of one or more identities. You can specify an identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NotificationAttributes': {
                'string': {
                    'BounceTopic': 'string',
                    'ComplaintTopic': 'string',
                    'DeliveryTopic': 'string',
                    'ForwardingEnabled': True|False,
                    'HeadersInBounceNotificationsEnabled': True|False,
                    'HeadersInComplaintNotificationsEnabled': True|False,
                    'HeadersInDeliveryNotificationsEnabled': True|False
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the notification attributes for a list of identities.

        
        

        - **NotificationAttributes** *(dict) --* 

          A map of Identity to IdentityNotificationAttributes.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents the notification attributes of an identity, including whether an identity has Amazon Simple Notification Service (Amazon SNS) topics set for bounce, complaint, and/or delivery notifications, and whether feedback forwarding is enabled for bounce and complaint notifications.

              
              

              - **BounceTopic** *(string) --* 

                The Amazon Resource Name (ARN) of the Amazon SNS topic where Amazon SES will publish bounce notifications.

                
              

              - **ComplaintTopic** *(string) --* 

                The Amazon Resource Name (ARN) of the Amazon SNS topic where Amazon SES will publish complaint notifications.

                
              

              - **DeliveryTopic** *(string) --* 

                The Amazon Resource Name (ARN) of the Amazon SNS topic where Amazon SES will publish delivery notifications.

                
              

              - **ForwardingEnabled** *(boolean) --* 

                Describes whether Amazon SES will forward bounce and complaint notifications as email. ``true`` indicates that Amazon SES will forward bounce and complaint notifications as email, while ``false`` indicates that bounce and complaint notifications will be published only to the specified bounce and complaint Amazon SNS topics.

                
              

              - **HeadersInBounceNotificationsEnabled** *(boolean) --* 

                Describes whether Amazon SES includes the original email headers in Amazon SNS notifications of type ``Bounce`` . A value of ``true`` specifies that Amazon SES will include headers in bounce notifications, and a value of ``false`` specifies that Amazon SES will not include headers in bounce notifications.

                
              

              - **HeadersInComplaintNotificationsEnabled** *(boolean) --* 

                Describes whether Amazon SES includes the original email headers in Amazon SNS notifications of type ``Complaint`` . A value of ``true`` specifies that Amazon SES will include headers in complaint notifications, and a value of ``false`` specifies that Amazon SES will not include headers in complaint notifications.

                
              

              - **HeadersInDeliveryNotificationsEnabled** *(boolean) --* 

                Describes whether Amazon SES includes the original email headers in Amazon SNS notifications of type ``Delivery`` . A value of ``true`` specifies that Amazon SES will include headers in delivery notifications, and a value of ``false`` specifies that Amazon SES will not include headers in delivery notifications.

                
          
      
    
    

  .. py:method:: get_identity_policies(**kwargs)

    

    Returns the requested sending authorization policies for the given identity (an email address or a domain). The policies are returned as a map of policy names to policy contents. You can retrieve a maximum of 20 policies at a time.

     

    .. note::

       

      This API is for the identity owner only. If you have not verified the identity, this API will return an error.

       

     

    Sending authorization is a feature that enables an identity owner to authorize other senders to use its identities. For information about using sending authorization, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.get_identity_policies(
          Identity='string',
          PolicyNames=[
              'string',
          ]
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The identity for which the policies will be retrieved. You can specify an identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

       

      To successfully call this API, you must own the identity.

      

    
    :type PolicyNames: list
    :param PolicyNames: **[REQUIRED]** 

      A list of the names of policies to be retrieved. You can retrieve a maximum of 20 policies at a time. If you do not know the names of the policies that are attached to the identity, you can use ``ListIdentityPolicies`` .

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Policies': {
                'string': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the requested sending authorization policies.

        
        

        - **Policies** *(dict) --* 

          A map of policy names to policies.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
    

  .. py:method:: get_identity_verification_attributes(**kwargs)

    

    Given a list of identities (email addresses and/or domains), returns the verification status and (for domain identities) the verification token for each identity.

     

    This action is throttled at one request per second and can only get verification attributes for up to 100 identities at a time.

    

    **Request Syntax** 
    ::

      response = client.get_identity_verification_attributes(
          Identities=[
              'string',
          ]
      )
    :type Identities: list
    :param Identities: **[REQUIRED]** 

      A list of identities.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VerificationAttributes': {
                'string': {
                    'VerificationStatus': 'Pending'|'Success'|'Failed'|'TemporaryFailure'|'NotStarted',
                    'VerificationToken': 'string'
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The Amazon SES verification status of a list of identities. For domain identities, this response also contains the verification token.

        
        

        - **VerificationAttributes** *(dict) --* 

          A map of Identities to IdentityVerificationAttributes objects.

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents the verification attributes of a single identity.

              
              

              - **VerificationStatus** *(string) --* 

                The verification status of the identity: "Pending", "Success", "Failed", or "TemporaryFailure".

                
              

              - **VerificationToken** *(string) --* 

                The verification token for a domain identity. Null for email address identities.

                
          
      
    
    

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


  .. py:method:: get_send_quota()

    

    Returns the user's current sending limits.

     

    This action is throttled at one request per second.

    

    **Request Syntax** 

    ::

      response = client.get_send_quota()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Max24HourSend': 123.0,
            'MaxSendRate': 123.0,
            'SentLast24Hours': 123.0
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents your Amazon SES daily sending quota, maximum send rate, and the number of emails you have sent in the last 24 hours.

        
        

        - **Max24HourSend** *(float) --* 

          The maximum number of emails the user is allowed to send in a 24-hour interval. A value of -1 signifies an unlimited quota.

          
        

        - **MaxSendRate** *(float) --* 

          The maximum number of emails that Amazon SES can accept from the user's account per second.

           

          .. note::

             

            The rate at which Amazon SES accepts the user's messages might be less than the maximum send rate.

             

          
        

        - **SentLast24Hours** *(float) --* 

          The number of emails sent during the previous 24 hours.

          
    

  .. py:method:: get_send_statistics()

    

    Returns the user's sending statistics. The result is a list of data points, representing the last two weeks of sending activity.

     

    Each data point in the list contains statistics for a 15-minute interval.

     

    This action is throttled at one request per second.

    

    **Request Syntax** 

    ::

      response = client.get_send_statistics()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SendDataPoints': [
                {
                    'Timestamp': datetime(2015, 1, 1),
                    'DeliveryAttempts': 123,
                    'Bounces': 123,
                    'Complaints': 123,
                    'Rejects': 123
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a list of data points. This list contains aggregated data from the previous two weeks of your sending activity with Amazon SES.

        
        

        - **SendDataPoints** *(list) --* 

          A list of data points, each of which represents 15 minutes of activity.

          
          

          - *(dict) --* 

            Represents sending statistics data. Each ``SendDataPoint`` contains statistics for a 15-minute period of sending activity. 

            
            

            - **Timestamp** *(datetime) --* 

              Time of the data point.

              
            

            - **DeliveryAttempts** *(integer) --* 

              Number of emails that have been enqueued for sending.

              
            

            - **Bounces** *(integer) --* 

              Number of emails that have bounced.

              
            

            - **Complaints** *(integer) --* 

              Number of unwanted emails that were rejected by recipients.

              
            

            - **Rejects** *(integer) --* 

              Number of emails rejected by Amazon SES.

              
        
      
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: list_identities(**kwargs)

    

    Returns a list containing all of the identities (email addresses and domains) for your AWS account, regardless of verification status.

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.list_identities(
          IdentityType='EmailAddress'|'Domain',
          NextToken='string',
          MaxItems=123
      )
    :type IdentityType: string
    :param IdentityType: 

      The type of the identities to list. Possible values are "EmailAddress" and "Domain". If this parameter is omitted, then all identities will be listed.

      

    
    :type NextToken: string
    :param NextToken: 

      The token to use for pagination.

      

    
    :type MaxItems: integer
    :param MaxItems: 

      The maximum number of identities per page. Possible values are 1-1000 inclusive.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Identities': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of all identities that you have attempted to verify under your AWS account, regardless of verification status.

        
        

        - **Identities** *(list) --* 

          A list of identities.

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          The token used for pagination.

          
    

  .. py:method:: list_identity_policies(**kwargs)

    

    Returns a list of sending authorization policies that are attached to the given identity (an email address or a domain). This API returns only a list. If you want the actual policy content, you can use ``GetIdentityPolicies`` .

     

    .. note::

       

      This API is for the identity owner only. If you have not verified the identity, this API will return an error.

       

     

    Sending authorization is a feature that enables an identity owner to authorize other senders to use its identities. For information about using sending authorization, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.list_identity_policies(
          Identity='string'
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The identity that is associated with the policy for which the policies will be listed. You can specify an identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

       

      To successfully call this API, you must own the identity.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'PolicyNames': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of names of sending authorization policies that apply to an identity.

        
        

        - **PolicyNames** *(list) --* 

          A list of names of policies that apply to the specified identity.

          
          

          - *(string) --* 
      
    

  .. py:method:: list_receipt_filters()

    

    Lists the IP address filters associated with your AWS account.

     

    For information about managing IP address filters, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.list_receipt_filters()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Filters': [
                {
                    'Name': 'string',
                    'IpFilter': {
                        'Policy': 'Block'|'Allow',
                        'Cidr': 'string'
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of IP address filters that exist under your AWS account.

        
        

        - **Filters** *(list) --* 

          A list of IP address filter data structures, which each consist of a name, an IP address range, and whether to allow or block mail from it.

          
          

          - *(dict) --* 

            A receipt IP address filter enables you to specify whether to accept or reject mail originating from an IP address or range of IP addresses.

             

            For information about setting up IP address filters, see the `Amazon SES Developer Guide`_ .

            
            

            - **Name** *(string) --* 

              The name of the IP address filter. The name must:

               

               
              * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
               
              * Start and end with a letter or number. 
               
              * Contain less than 64 characters. 
               

              
            

            - **IpFilter** *(dict) --* 

              A structure that provides the IP addresses to block or allow, and whether to block or allow incoming mail from them.

              
              

              - **Policy** *(string) --* 

                Indicates whether to block or allow incoming mail from the specified IP addresses.

                
              

              - **Cidr** *(string) --* 

                A single IP address or a range of IP addresses that you want to block or allow, specified in Classless Inter-Domain Routing (CIDR) notation. An example of a single email address is 10.0.0.1. An example of a range of IP addresses is 10.0.0.1/24. For more information about CIDR notation, see `RFC 2317`_ .

                
          
        
      
    

  .. py:method:: list_receipt_rule_sets(**kwargs)

    

    Lists the receipt rule sets that exist under your AWS account. If there are additional receipt rule sets to be retrieved, you will receive a ``NextToken`` that you can provide to the next call to ``ListReceiptRuleSets`` to retrieve the additional entries.

     

    For information about managing receipt rule sets, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.list_receipt_rule_sets(
          NextToken='string'
      )
    :type NextToken: string
    :param NextToken: 

      A token returned from a previous call to ``ListReceiptRuleSets`` to indicate the position in the receipt rule set list.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RuleSets': [
                {
                    'Name': 'string',
                    'CreatedTimestamp': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of receipt rule sets that exist under your AWS account.

        
        

        - **RuleSets** *(list) --* 

          The metadata for the currently active receipt rule set. The metadata consists of the rule set name and the timestamp of when the rule set was created.

          
          

          - *(dict) --* 

            Information about a receipt rule set.

             

            A receipt rule set is a collection of rules that specify what Amazon SES should do with mail it receives on behalf of your account's verified domains.

             

            For information about setting up receipt rule sets, see the `Amazon SES Developer Guide`_ .

            
            

            - **Name** *(string) --* 

              The name of the receipt rule set. The name must:

               

               
              * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
               
              * Start and end with a letter or number. 
               
              * Contain less than 64 characters. 
               

              
            

            - **CreatedTimestamp** *(datetime) --* 

              The date and time the receipt rule set was created.

              
        
      
        

        - **NextToken** *(string) --* 

          A token indicating that there are additional receipt rule sets available to be listed. Pass this token to successive calls of ``ListReceiptRuleSets`` to retrieve up to 100 receipt rule sets at a time.

          
    

  .. py:method:: list_verified_email_addresses()

    

    Returns a list containing all of the email addresses that have been verified.

     

    .. warning::

       

      The ListVerifiedEmailAddresses action is deprecated as of the May 15, 2012 release of Domain Verification. The ListIdentities action is now preferred.

       

     

    This action is throttled at one request per second.

    

    **Request Syntax** 

    ::

      response = client.list_verified_email_addresses()
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VerifiedEmailAddresses': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of email addresses that you have verified with Amazon SES under your AWS account.

        
        

        - **VerifiedEmailAddresses** *(list) --* 

          A list of email addresses that have been verified.

          
          

          - *(string) --* 
      
    

  .. py:method:: put_identity_policy(**kwargs)

    

    Adds or updates a sending authorization policy for the specified identity (an email address or a domain).

     

    .. note::

       

      This API is for the identity owner only. If you have not verified the identity, this API will return an error.

       

     

    Sending authorization is a feature that enables an identity owner to authorize other senders to use its identities. For information about using sending authorization, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.put_identity_policy(
          Identity='string',
          PolicyName='string',
          Policy='string'
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The identity to which the policy will apply. You can specify an identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

       

      To successfully call this API, you must own the identity.

      

    
    :type PolicyName: string
    :param PolicyName: **[REQUIRED]** 

      The name of the policy.

       

      The policy name cannot exceed 64 characters and can only include alphanumeric characters, dashes, and underscores.

      

    
    :type Policy: string
    :param Policy: **[REQUIRED]** 

      The text of the policy in JSON format. The policy cannot exceed 4 KB.

       

      For information about the syntax of sending authorization policies, see the `Amazon SES Developer Guide`_ . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: reorder_receipt_rule_set(**kwargs)

    

    Reorders the receipt rules within a receipt rule set.

     

    .. note::

       

      All of the rules in the rule set must be represented in this request. That is, this API will return an error if the reorder request doesn't explicitly position all of the rules.

       

     

    For information about managing receipt rule sets, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.reorder_receipt_rule_set(
          RuleSetName='string',
          RuleNames=[
              'string',
          ]
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the receipt rule set to reorder.

      

    
    :type RuleNames: list
    :param RuleNames: **[REQUIRED]** 

      A list of the specified receipt rule set's receipt rules in the order that you want to put them.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: send_bounce(**kwargs)

    

    Generates and sends a bounce message to the sender of an email you received through Amazon SES. You can only use this API on an email up to 24 hours after you receive it.

     

    .. note::

       

      You cannot use this API to send generic bounces for mail that was not received by Amazon SES.

       

     

    For information about receiving email through Amazon SES, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.send_bounce(
          OriginalMessageId='string',
          BounceSender='string',
          Explanation='string',
          MessageDsn={
              'ReportingMta': 'string',
              'ArrivalDate': datetime(2015, 1, 1),
              'ExtensionFields': [
                  {
                      'Name': 'string',
                      'Value': 'string'
                  },
              ]
          },
          BouncedRecipientInfoList=[
              {
                  'Recipient': 'string',
                  'RecipientArn': 'string',
                  'BounceType': 'DoesNotExist'|'MessageTooLarge'|'ExceededQuota'|'ContentRejected'|'Undefined'|'TemporaryFailure',
                  'RecipientDsnFields': {
                      'FinalRecipient': 'string',
                      'Action': 'failed'|'delayed'|'delivered'|'relayed'|'expanded',
                      'RemoteMta': 'string',
                      'Status': 'string',
                      'DiagnosticCode': 'string',
                      'LastAttemptDate': datetime(2015, 1, 1),
                      'ExtensionFields': [
                          {
                              'Name': 'string',
                              'Value': 'string'
                          },
                      ]
                  }
              },
          ],
          BounceSenderArn='string'
      )
    :type OriginalMessageId: string
    :param OriginalMessageId: **[REQUIRED]** 

      The message ID of the message to be bounced.

      

    
    :type BounceSender: string
    :param BounceSender: **[REQUIRED]** 

      The address to use in the "From" header of the bounce message. This must be an identity that you have verified with Amazon SES.

      

    
    :type Explanation: string
    :param Explanation: 

      Human-readable text for the bounce message to explain the failure. If not specified, the text will be auto-generated based on the bounced recipient information.

      

    
    :type MessageDsn: dict
    :param MessageDsn: 

      Message-related DSN fields. If not specified, Amazon SES will choose the values.

      

    
      - **ReportingMta** *(string) --* **[REQUIRED]** 

        The reporting MTA that attempted to deliver the message, formatted as specified in `RFC 3464`_ (``mta-name-type; mta-name`` ). The default value is ``dns; inbound-smtp.[region].amazonaws.com`` .

        

      
      - **ArrivalDate** *(datetime) --* 

        When the message was received by the reporting mail transfer agent (MTA), in `RFC 822`_ date-time format.

        

      
      - **ExtensionFields** *(list) --* 

        Additional X-headers to include in the DSN.

        

      
        - *(dict) --* 

          Additional X-headers to include in the Delivery Status Notification (DSN) when an email that Amazon SES receives on your behalf bounces.

           

          For information about receiving email through Amazon SES, see the `Amazon SES Developer Guide`_ .

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            The name of the header to add. Must be between 1 and 50 characters, inclusive, and consist of alphanumeric (a-z, A-Z, 0-9) characters and dashes only.

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            The value of the header to add. Must be less than 2048 characters, and must not contain newline characters ("\r" or "\n").

            

          
        
    
    
    :type BouncedRecipientInfoList: list
    :param BouncedRecipientInfoList: **[REQUIRED]** 

      A list of recipients of the bounced message, including the information required to create the Delivery Status Notifications (DSNs) for the recipients. You must specify at least one ``BouncedRecipientInfo`` in the list.

      

    
      - *(dict) --* 

        Recipient-related information to include in the Delivery Status Notification (DSN) when an email that Amazon SES receives on your behalf bounces.

         

        For information about receiving email through Amazon SES, see the `Amazon SES Developer Guide`_ .

        

      
        - **Recipient** *(string) --* **[REQUIRED]** 

          The email address of the recipient of the bounced email.

          

        
        - **RecipientArn** *(string) --* 

          This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to receive email for the recipient of the bounced email. For more information about sending authorization, see the `Amazon SES Developer Guide`_ .

          

        
        - **BounceType** *(string) --* 

          The reason for the bounce. You must provide either this parameter or ``RecipientDsnFields`` .

          

        
        - **RecipientDsnFields** *(dict) --* 

          Recipient-related DSN fields, most of which would normally be filled in automatically when provided with a ``BounceType`` . You must provide either this parameter or ``BounceType`` .

          

        
          - **FinalRecipient** *(string) --* 

            The email address to which the message was ultimately delivered. This corresponds to the ``Final-Recipient`` in the DSN. If not specified, ``FinalRecipient`` will be set to the ``Recipient`` specified in the ``BouncedRecipientInfo`` structure. Either ``FinalRecipient`` or the recipient in ``BouncedRecipientInfo`` must be a recipient of the original bounced message.

             

            .. note::

               

              Do not prepend the ``FinalRecipient`` email address with ``rfc 822;`` , as described in `RFC 3798`_ .

               

            

          
          - **Action** *(string) --* **[REQUIRED]** 

            The action performed by the reporting mail transfer agent (MTA) as a result of its attempt to deliver the message to the recipient address. This is required by `RFC 3464`_ .

            

          
          - **RemoteMta** *(string) --* 

            The MTA to which the remote MTA attempted to deliver the message, formatted as specified in `RFC 3464`_ (``mta-name-type; mta-name`` ). This parameter typically applies only to propagating synchronous bounces.

            

          
          - **Status** *(string) --* **[REQUIRED]** 

            The status code that indicates what went wrong. This is required by `RFC 3464`_ .

            

          
          - **DiagnosticCode** *(string) --* 

            An extended explanation of what went wrong; this is usually an SMTP response. See `RFC 3463`_ for the correct formatting of this parameter.

            

          
          - **LastAttemptDate** *(datetime) --* 

            The time the final delivery attempt was made, in `RFC 822`_ date-time format.

            

          
          - **ExtensionFields** *(list) --* 

            Additional X-headers to include in the DSN.

            

          
            - *(dict) --* 

              Additional X-headers to include in the Delivery Status Notification (DSN) when an email that Amazon SES receives on your behalf bounces.

               

              For information about receiving email through Amazon SES, see the `Amazon SES Developer Guide`_ .

              

            
              - **Name** *(string) --* **[REQUIRED]** 

                The name of the header to add. Must be between 1 and 50 characters, inclusive, and consist of alphanumeric (a-z, A-Z, 0-9) characters and dashes only.

                

              
              - **Value** *(string) --* **[REQUIRED]** 

                The value of the header to add. Must be less than 2048 characters, and must not contain newline characters ("\r" or "\n").

                

              
            
        
        
      
  
    :type BounceSenderArn: string
    :param BounceSenderArn: 

      This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to use the address in the "From" header of the bounce. For more information about sending authorization, see the `Amazon SES Developer Guide`_ .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MessageId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a unique message ID.

        
        

        - **MessageId** *(string) --* 

          The message ID of the bounce message.

          
    

  .. py:method:: send_email(**kwargs)

    

    Composes an email message based on input data, and then immediately queues the message for sending.

     

    There are several important points to know about ``SendEmail`` :

     

     
    * You can only send email from verified email addresses and domains; otherwise, you will get an "Email address not verified" error. If your account is still in the Amazon SES sandbox, you must also verify every recipient email address except for the recipients provided by the Amazon SES mailbox simulator. For more information, go to the `Amazon SES Developer Guide`_ . 
     
    * The total size of the message cannot exceed 10 MB. This includes any attachments that are part of the message. 
     
    * Amazon SES has a limit on the total number of recipients per message. The combined number of To:, CC: and BCC: email addresses cannot exceed 50. If you need to send an email message to a larger audience, you can divide your recipient list into groups of 50 or fewer, and then call Amazon SES repeatedly to send the message to each group. 
     
    * For every message that you send, the total number of recipients (To:, CC: and BCC:) is counted against your sending quota - the maximum number of emails you can send in a 24-hour period. For information about your sending quota, go to the `Amazon SES Developer Guide`_ . 
     

    

    **Request Syntax** 
    ::

      response = client.send_email(
          Source='string',
          Destination={
              'ToAddresses': [
                  'string',
              ],
              'CcAddresses': [
                  'string',
              ],
              'BccAddresses': [
                  'string',
              ]
          },
          Message={
              'Subject': {
                  'Data': 'string',
                  'Charset': 'string'
              },
              'Body': {
                  'Text': {
                      'Data': 'string',
                      'Charset': 'string'
                  },
                  'Html': {
                      'Data': 'string',
                      'Charset': 'string'
                  }
              }
          },
          ReplyToAddresses=[
              'string',
          ],
          ReturnPath='string',
          SourceArn='string',
          ReturnPathArn='string'
      )
    :type Source: string
    :param Source: **[REQUIRED]** 

      The email address that is sending the email. This email address must be either individually verified with Amazon SES, or from a domain that has been verified with Amazon SES. For information about verifying identities, see the `Amazon SES Developer Guide`_ .

       

      If you are sending on behalf of another user and have been permitted to do so by a sending authorization policy, then you must also specify the ``SourceArn`` parameter. For more information about sending authorization, see the `Amazon SES Developer Guide`_ .

       

      In all cases, the email address must be 7-bit ASCII. If the text must contain any other characters, then you must use MIME encoded-word syntax (RFC 2047) instead of a literal string. MIME encoded-word syntax uses the following form: ``=?charset?encoding?encoded-text?=`` . For more information, see `RFC 2047`_ . 

      

    
    :type Destination: dict
    :param Destination: **[REQUIRED]** 

      The destination for this email, composed of To:, CC:, and BCC: fields.

      

    
      - **ToAddresses** *(list) --* 

        The To: field(s) of the message.

        

      
        - *(string) --* 

        
    
      - **CcAddresses** *(list) --* 

        The CC: field(s) of the message.

        

      
        - *(string) --* 

        
    
      - **BccAddresses** *(list) --* 

        The BCC: field(s) of the message.

        

      
        - *(string) --* 

        
    
    
    :type Message: dict
    :param Message: **[REQUIRED]** 

      The message to be sent.

      

    
      - **Subject** *(dict) --* **[REQUIRED]** 

        The subject of the message: A short summary of the content, which will appear in the recipient's inbox.

        

      
        - **Data** *(string) --* **[REQUIRED]** 

          The textual data of the content.

          

        
        - **Charset** *(string) --* 

          The character set of the content.

          

        
      
      - **Body** *(dict) --* **[REQUIRED]** 

        The message body.

        

      
        - **Text** *(dict) --* 

          The content of the message, in text format. Use this for text-based email clients, or clients on high-latency networks (such as mobile devices).

          

        
          - **Data** *(string) --* **[REQUIRED]** 

            The textual data of the content.

            

          
          - **Charset** *(string) --* 

            The character set of the content.

            

          
        
        - **Html** *(dict) --* 

          The content of the message, in HTML format. Use this for email clients that can process HTML. You can include clickable links, formatted text, and much more in an HTML message.

          

        
          - **Data** *(string) --* **[REQUIRED]** 

            The textual data of the content.

            

          
          - **Charset** *(string) --* 

            The character set of the content.

            

          
        
      
    
    :type ReplyToAddresses: list
    :param ReplyToAddresses: 

      The reply-to email address(es) for the message. If the recipient replies to the message, each reply-to address will receive the reply.

      

    
      - *(string) --* 

      
  
    :type ReturnPath: string
    :param ReturnPath: 

      The email address to which bounces and complaints are to be forwarded when feedback forwarding is enabled. If the message cannot be delivered to the recipient, then an error message will be returned from the recipient's ISP; this message will then be forwarded to the email address specified by the ``ReturnPath`` parameter. The ``ReturnPath`` parameter is never overwritten. This email address must be either individually verified with Amazon SES, or from a domain that has been verified with Amazon SES. 

      

    
    :type SourceArn: string
    :param SourceArn: 

      This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to send for the email address specified in the ``Source`` parameter.

       

      For example, if the owner of ``example.com`` (which has ARN ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` ) attaches a policy to it that authorizes you to send from ``user@example.com`` , then you would specify the ``SourceArn`` to be ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` , and the ``Source`` to be ``user@example.com`` .

       

      For more information about sending authorization, see the `Amazon SES Developer Guide`_ . 

      

    
    :type ReturnPathArn: string
    :param ReturnPathArn: 

      This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to use the email address specified in the ``ReturnPath`` parameter.

       

      For example, if the owner of ``example.com`` (which has ARN ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` ) attaches a policy to it that authorizes you to use ``feedback@example.com`` , then you would specify the ``ReturnPathArn`` to be ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` , and the ``ReturnPath`` to be ``feedback@example.com`` .

       

      For more information about sending authorization, see the `Amazon SES Developer Guide`_ . 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MessageId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a unique message ID.

        
        

        - **MessageId** *(string) --* 

          The unique message identifier returned from the ``SendEmail`` action. 

          
    

  .. py:method:: send_raw_email(**kwargs)

    

    Sends an email message, with header and content specified by the client. The ``SendRawEmail`` action is useful for sending multipart MIME emails. The raw text of the message must comply with Internet email standards; otherwise, the message cannot be sent. 

     

    There are several important points to know about ``SendRawEmail`` :

     

     
    * You can only send email from verified email addresses and domains; otherwise, you will get an "Email address not verified" error. If your account is still in the Amazon SES sandbox, you must also verify every recipient email address except for the recipients provided by the Amazon SES mailbox simulator. For more information, go to the `Amazon SES Developer Guide`_ . 
     
    * The total size of the message cannot exceed 10 MB. This includes any attachments that are part of the message. 
     
    * Amazon SES has a limit on the total number of recipients per message. The combined number of To:, CC: and BCC: email addresses cannot exceed 50. If you need to send an email message to a larger audience, you can divide your recipient list into groups of 50 or fewer, and then call Amazon SES repeatedly to send the message to each group. 
     
    * The To:, CC:, and BCC: headers in the raw message can contain a group list. Note that each recipient in a group list counts towards the 50-recipient limit. 
     
    * Amazon SES overrides any Message-ID and Date headers you provide. 
     
    * For every message that you send, the total number of recipients (To:, CC: and BCC:) is counted against your sending quota - the maximum number of emails you can send in a 24-hour period. For information about your sending quota, go to the `Amazon SES Developer Guide`_ . 
     
    * If you are using sending authorization to send on behalf of another user, ``SendRawEmail`` enables you to specify the cross-account identity for the email's "Source," "From," and "Return-Path" parameters in one of two ways: you can pass optional parameters ``SourceArn`` , ``FromArn`` , and/or ``ReturnPathArn`` to the API, or you can include the following X-headers in the header of your raw email: 

       
      * ``X-SES-SOURCE-ARN``   
       
      * ``X-SES-FROM-ARN``   
       
      * ``X-SES-RETURN-PATH-ARN``   
       

     

    .. warning::

       

      Do not include these X-headers in the DKIM signature, because they are removed by Amazon SES before sending the email.

       

     

    For the most common sending authorization use case, we recommend that you specify the ``SourceIdentityArn`` and do not specify either the ``FromIdentityArn`` or ``ReturnPathIdentityArn`` . (The same note applies to the corresponding X-headers.) If you only specify the ``SourceIdentityArn`` , Amazon SES will simply set the "From" address and the "Return Path" address to the identity specified in ``SourceIdentityArn`` . For more information about sending authorization, see the `Amazon SES Developer Guide`_ .

     
     

    

    **Request Syntax** 
    ::

      response = client.send_raw_email(
          Source='string',
          Destinations=[
              'string',
          ],
          RawMessage={
              'Data': b'bytes'
          },
          FromArn='string',
          SourceArn='string',
          ReturnPathArn='string'
      )
    :type Source: string
    :param Source: 

      The identity's email address. If you do not provide a value for this parameter, you must specify a "From" address in the raw text of the message. (You can also specify both.)

       

      By default, the string must be 7-bit ASCII. If the text must contain any other characters, then you must use MIME encoded-word syntax (RFC 2047) instead of a literal string. MIME encoded-word syntax uses the following form: ``=?charset?encoding?encoded-text?=`` . For more information, see `RFC 2047`_ . 

       

      .. note::

         

        If you specify the ``Source`` parameter and have feedback forwarding enabled, then bounces and complaints will be sent to this email address. This takes precedence over any *Return-Path* header that you might include in the raw text of the message.

         

      

    
    :type Destinations: list
    :param Destinations: 

      A list of destinations for the message, consisting of To:, CC:, and BCC: addresses.

      

    
      - *(string) --* 

      
  
    :type RawMessage: dict
    :param RawMessage: **[REQUIRED]** 

      The raw text of the message. The client is responsible for ensuring the following:

       

       
      * Message must contain a header and a body, separated by a blank line. 
       
      * All required header fields must be present. 
       
      * Each part of a multipart MIME message must be formatted properly. 
       
      * MIME content types must be among those supported by Amazon SES. For more information, go to the `Amazon SES Developer Guide`_ . 
       
      * Must be base64-encoded. 
       

      

    
      - **Data** *(bytes) --* **[REQUIRED]** 

        The raw data of the message. The client must ensure that the message format complies with Internet email standards regarding email header fields, MIME types, MIME encoding, and base64 encoding.

         

        The To:, CC:, and BCC: headers in the raw message can contain a group list.

         

        If you are using ``SendRawEmail`` with sending authorization, you can include X-headers in the raw message to specify the "Source," "From," and "Return-Path" addresses. For more information, see the documentation for ``SendRawEmail`` . 

         

        .. warning::

           

          Do not include these X-headers in the DKIM signature, because they are removed by Amazon SES before sending the email.

           

         

        For more information, go to the `Amazon SES Developer Guide`_ . 

        

      
    
    :type FromArn: string
    :param FromArn: 

      This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to specify a particular "From" address in the header of the raw email.

       

      Instead of using this parameter, you can use the X-header ``X-SES-FROM-ARN`` in the raw message of the email. If you use both the ``FromArn`` parameter and the corresponding X-header, Amazon SES uses the value of the ``FromArn`` parameter.

       

      .. note::

         

        For information about when to use this parameter, see the description of ``SendRawEmail`` in this guide, or see the `Amazon SES Developer Guide`_ .

         

      

    
    :type SourceArn: string
    :param SourceArn: 

      This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to send for the email address specified in the ``Source`` parameter.

       

      For example, if the owner of ``example.com`` (which has ARN ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` ) attaches a policy to it that authorizes you to send from ``user@example.com`` , then you would specify the ``SourceArn`` to be ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` , and the ``Source`` to be ``user@example.com`` .

       

      Instead of using this parameter, you can use the X-header ``X-SES-SOURCE-ARN`` in the raw message of the email. If you use both the ``SourceArn`` parameter and the corresponding X-header, Amazon SES uses the value of the ``SourceArn`` parameter.

       

      .. note::

         

        For information about when to use this parameter, see the description of ``SendRawEmail`` in this guide, or see the `Amazon SES Developer Guide`_ .

         

      

    
    :type ReturnPathArn: string
    :param ReturnPathArn: 

      This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to use the email address specified in the ``ReturnPath`` parameter.

       

      For example, if the owner of ``example.com`` (which has ARN ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` ) attaches a policy to it that authorizes you to use ``feedback@example.com`` , then you would specify the ``ReturnPathArn`` to be ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` , and the ``ReturnPath`` to be ``feedback@example.com`` .

       

      Instead of using this parameter, you can use the X-header ``X-SES-RETURN-PATH-ARN`` in the raw message of the email. If you use both the ``ReturnPathArn`` parameter and the corresponding X-header, Amazon SES uses the value of the ``ReturnPathArn`` parameter.

       

      .. note::

         

        For information about when to use this parameter, see the description of ``SendRawEmail`` in this guide, or see the `Amazon SES Developer Guide`_ .

         

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MessageId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a unique message ID.

        
        

        - **MessageId** *(string) --* 

          The unique message identifier returned from the ``SendRawEmail`` action. 

          
    

  .. py:method:: set_active_receipt_rule_set(**kwargs)

    

    Sets the specified receipt rule set as the active receipt rule set.

     

    .. note::

       

      To disable your email-receiving through Amazon SES completely, you can call this API with RuleSetName set to null.

       

     

    For information about managing receipt rule sets, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.set_active_receipt_rule_set(
          RuleSetName='string'
      )
    :type RuleSetName: string
    :param RuleSetName: 

      The name of the receipt rule set to make active. Setting this value to null disables all email receiving.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: set_identity_dkim_enabled(**kwargs)

    

    Enables or disables Easy DKIM signing of email sent from an identity:

     

     
    * If Easy DKIM signing is enabled for a domain name identity (e.g., ``example.com`` ), then Amazon SES will DKIM-sign all email sent by addresses under that domain name (e.g., ``user@example.com`` ). 
     
    * If Easy DKIM signing is enabled for an email address, then Amazon SES will DKIM-sign all email sent by that email address. 
     

     

    For email addresses (e.g., ``user@example.com`` ), you can only enable Easy DKIM signing if the corresponding domain (e.g., ``example.com`` ) has been set up for Easy DKIM using the AWS Console or the ``VerifyDomainDkim`` action.

     

    This action is throttled at one request per second.

     

    For more information about Easy DKIM signing, go to the `Amazon SES Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.set_identity_dkim_enabled(
          Identity='string',
          DkimEnabled=True|False
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The identity for which DKIM signing should be enabled or disabled.

      

    
    :type DkimEnabled: boolean
    :param DkimEnabled: **[REQUIRED]** 

      Sets whether DKIM signing is enabled for an identity. Set to ``true`` to enable DKIM signing for this identity; ``false`` to disable it. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: set_identity_feedback_forwarding_enabled(**kwargs)

    

    Given an identity (an email address or a domain), enables or disables whether Amazon SES forwards bounce and complaint notifications as email. Feedback forwarding can only be disabled when Amazon Simple Notification Service (Amazon SNS) topics are specified for both bounces and complaints.

     

    .. note::

       

      Feedback forwarding does not apply to delivery notifications. Delivery notifications are only available through Amazon SNS.

       

     

    This action is throttled at one request per second.

     

    For more information about using notifications with Amazon SES, see the `Amazon SES Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.set_identity_feedback_forwarding_enabled(
          Identity='string',
          ForwardingEnabled=True|False
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The identity for which to set bounce and complaint notification forwarding. Examples: ``user@example.com`` , ``example.com`` .

      

    
    :type ForwardingEnabled: boolean
    :param ForwardingEnabled: **[REQUIRED]** 

      Sets whether Amazon SES will forward bounce and complaint notifications as email. ``true`` specifies that Amazon SES will forward bounce and complaint notifications as email, in addition to any Amazon SNS topic publishing otherwise specified. ``false`` specifies that Amazon SES will publish bounce and complaint notifications only through Amazon SNS. This value can only be set to ``false`` when Amazon SNS topics are set for both ``Bounce`` and ``Complaint`` notification types.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: set_identity_headers_in_notifications_enabled(**kwargs)

    

    Given an identity (an email address or a domain), sets whether Amazon SES includes the original email headers in the Amazon Simple Notification Service (Amazon SNS) notifications of a specified type.

     

    This action is throttled at one request per second.

     

    For more information about using notifications with Amazon SES, see the `Amazon SES Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.set_identity_headers_in_notifications_enabled(
          Identity='string',
          NotificationType='Bounce'|'Complaint'|'Delivery',
          Enabled=True|False
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The identity for which to enable or disable headers in notifications. Examples: ``user@example.com`` , ``example.com`` .

      

    
    :type NotificationType: string
    :param NotificationType: **[REQUIRED]** 

      The notification type for which to enable or disable headers in notifications. 

      

    
    :type Enabled: boolean
    :param Enabled: **[REQUIRED]** 

      Sets whether Amazon SES includes the original email headers in Amazon SNS notifications of the specified notification type. A value of ``true`` specifies that Amazon SES will include headers in notifications, and a value of ``false`` specifies that Amazon SES will not include headers in notifications.

       

      This value can only be set when ``NotificationType`` is already set to use a particular Amazon SNS topic.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: set_identity_mail_from_domain(**kwargs)

    

    Enables or disables the custom MAIL FROM domain setup for a verified identity (an email address or a domain).

     

    .. warning::

       

      To send emails using the specified MAIL FROM domain, you must add an MX record to your MAIL FROM domain's DNS settings. If you want your emails to pass Sender Policy Framework (SPF) checks, you must also add or update an SPF record. For more information, see the `Amazon SES Developer Guide`_ .

       

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.set_identity_mail_from_domain(
          Identity='string',
          MailFromDomain='string',
          BehaviorOnMXFailure='UseDefaultValue'|'RejectMessage'
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The verified identity for which you want to enable or disable the specified custom MAIL FROM domain.

      

    
    :type MailFromDomain: string
    :param MailFromDomain: 

      The custom MAIL FROM domain that you want the verified identity to use. The MAIL FROM domain must 1) be a subdomain of the verified identity, 2) not be used in a "From" address if the MAIL FROM domain is the destination of email feedback forwarding (for more information, see the `Amazon SES Developer Guide`_ ), and 3) not be used to receive emails. A value of ``null`` disables the custom MAIL FROM setting for the identity.

      

    
    :type BehaviorOnMXFailure: string
    :param BehaviorOnMXFailure: 

      The action that you want Amazon SES to take if it cannot successfully read the required MX record when you send an email. If you choose ``UseDefaultValue`` , Amazon SES will use amazonses.com (or a subdomain of that) as the MAIL FROM domain. If you choose ``RejectMessage`` , Amazon SES will return a ``MailFromDomainNotVerified`` error and not send the email.

       

      The action specified in ``BehaviorOnMXFailure`` is taken when the custom MAIL FROM domain setup is in the ``Pending`` , ``Failed`` , and ``TemporaryFailure`` states.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: set_identity_notification_topic(**kwargs)

    

    Given an identity (an email address or a domain), sets the Amazon Simple Notification Service (Amazon SNS) topic to which Amazon SES will publish bounce, complaint, and/or delivery notifications for emails sent with that identity as the ``Source`` .

     

    .. note::

       

      Unless feedback forwarding is enabled, you must specify Amazon SNS topics for bounce and complaint notifications. For more information, see ``SetIdentityFeedbackForwardingEnabled`` .

       

     

    This action is throttled at one request per second.

     

    For more information about feedback notification, see the `Amazon SES Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.set_identity_notification_topic(
          Identity='string',
          NotificationType='Bounce'|'Complaint'|'Delivery',
          SnsTopic='string'
      )
    :type Identity: string
    :param Identity: **[REQUIRED]** 

      The identity for which the Amazon SNS topic will be set. You can specify an identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

      

    
    :type NotificationType: string
    :param NotificationType: **[REQUIRED]** 

      The type of notifications that will be published to the specified Amazon SNS topic.

      

    
    :type SnsTopic: string
    :param SnsTopic: 

      The Amazon Resource Name (ARN) of the Amazon SNS topic. If the parameter is omitted from the request or a null value is passed, ``SnsTopic`` is cleared and publishing is disabled.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: set_receipt_rule_position(**kwargs)

    

    Sets the position of the specified receipt rule in the receipt rule set.

     

    For information about managing receipt rules, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.set_receipt_rule_position(
          RuleSetName='string',
          RuleName='string',
          After='string'
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the receipt rule set that contains the receipt rule to reposition.

      

    
    :type RuleName: string
    :param RuleName: **[REQUIRED]** 

      The name of the receipt rule to reposition.

      

    
    :type After: string
    :param After: 

      The name of the receipt rule after which to place the specified receipt rule.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: update_receipt_rule(**kwargs)

    

    Updates a receipt rule.

     

    For information about managing receipt rules, see the `Amazon SES Developer Guide`_ .

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.update_receipt_rule(
          RuleSetName='string',
          Rule={
              'Name': 'string',
              'Enabled': True|False,
              'TlsPolicy': 'Require'|'Optional',
              'Recipients': [
                  'string',
              ],
              'Actions': [
                  {
                      'S3Action': {
                          'TopicArn': 'string',
                          'BucketName': 'string',
                          'ObjectKeyPrefix': 'string',
                          'KmsKeyArn': 'string'
                      },
                      'BounceAction': {
                          'TopicArn': 'string',
                          'SmtpReplyCode': 'string',
                          'StatusCode': 'string',
                          'Message': 'string',
                          'Sender': 'string'
                      },
                      'WorkmailAction': {
                          'TopicArn': 'string',
                          'OrganizationArn': 'string'
                      },
                      'LambdaAction': {
                          'TopicArn': 'string',
                          'FunctionArn': 'string',
                          'InvocationType': 'Event'|'RequestResponse'
                      },
                      'StopAction': {
                          'Scope': 'RuleSet',
                          'TopicArn': 'string'
                      },
                      'AddHeaderAction': {
                          'HeaderName': 'string',
                          'HeaderValue': 'string'
                      },
                      'SNSAction': {
                          'TopicArn': 'string',
                          'Encoding': 'UTF-8'|'Base64'
                      }
                  },
              ],
              'ScanEnabled': True|False
          }
      )
    :type RuleSetName: string
    :param RuleSetName: **[REQUIRED]** 

      The name of the receipt rule set to which the receipt rule belongs.

      

    
    :type Rule: dict
    :param Rule: **[REQUIRED]** 

      A data structure that contains the updated receipt rule information.

      

    
      - **Name** *(string) --* **[REQUIRED]** 

        The name of the receipt rule. The name must:

         

         
        * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
         
        * Start and end with a letter or number. 
         
        * Contain less than 64 characters. 
         

        

      
      - **Enabled** *(boolean) --* 

        If ``true`` , the receipt rule is active. The default value is ``false`` .

        

      
      - **TlsPolicy** *(string) --* 

        Specifies whether Amazon SES should require that incoming email is delivered over a connection encrypted with Transport Layer Security (TLS). If this parameter is set to ``Require`` , Amazon SES will bounce emails that are not received over TLS. The default is ``Optional`` .

        

      
      - **Recipients** *(list) --* 

        The recipient domains and email addresses to which the receipt rule applies. If this field is not specified, this rule will match all recipients under all verified domains.

        

      
        - *(string) --* 

        
    
      - **Actions** *(list) --* 

        An ordered list of actions to perform on messages that match at least one of the recipient email addresses or domains specified in the receipt rule.

        

      
        - *(dict) --* 

          An action that Amazon SES can take when it receives an email on behalf of one or more email addresses or domains that you own. An instance of this data type can represent only one action.

           

          For information about setting up receipt rules, see the `Amazon SES Developer Guide`_ .

          

        
          - **S3Action** *(dict) --* 

            Saves the received message to an Amazon Simple Storage Service (Amazon S3) bucket and, optionally, publishes a notification to Amazon SNS.

            

          
            - **TopicArn** *(string) --* 

              The ARN of the Amazon SNS topic to notify when the message is saved to the Amazon S3 bucket. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **BucketName** *(string) --* **[REQUIRED]** 

              The name of the Amazon S3 bucket to which to save the received email.

              

            
            - **ObjectKeyPrefix** *(string) --* 

              The key prefix of the Amazon S3 bucket. The key prefix is similar to a directory name that enables you to store similar data under the same directory in a bucket.

              

            
            - **KmsKeyArn** *(string) --* 

              The customer master key that Amazon SES should use to encrypt your emails before saving them to the Amazon S3 bucket. You can use the default master key or a custom master key you created in AWS KMS as follows:

               

               
              * To use the default master key, provide an ARN in the form of ``arn:aws:kms:REGION:ACCOUNT-ID-WITHOUT-HYPHENS:alias/aws/ses`` . For example, if your AWS account ID is 123456789012 and you want to use the default master key in the US West (Oregon) region, the ARN of the default master key would be ``arn:aws:kms:us-west-2:123456789012:alias/aws/ses`` . If you use the default master key, you don't need to perform any extra steps to give Amazon SES permission to use the key. 
               
              * To use a custom master key you created in AWS KMS, provide the ARN of the master key and ensure that you add a statement to your key's policy to give Amazon SES permission to use it. For more information about giving permissions, see the `Amazon SES Developer Guide`_ . 
               

               

              For more information about key policies, see the `AWS KMS Developer Guide`_ . If you do not specify a master key, Amazon SES will not encrypt your emails.

               

              .. warning::

                 

                Your mail is encrypted by Amazon SES using the Amazon S3 encryption client before the mail is submitted to Amazon S3 for storage. It is not encrypted using Amazon S3 server-side encryption. This means that you must use the Amazon S3 encryption client to decrypt the email after retrieving it from Amazon S3, as the service has no access to use your AWS KMS keys for decryption. This encryption client is currently available with the `AWS Java SDK`_ and `AWS Ruby SDK`_ only. For more information about client-side encryption using AWS KMS master keys, see the `Amazon S3 Developer Guide`_ .

                 

              

            
          
          - **BounceAction** *(dict) --* 

            Rejects the received email by returning a bounce response to the sender and, optionally, publishes a notification to Amazon Simple Notification Service (Amazon SNS).

            

          
            - **TopicArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the bounce action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **SmtpReplyCode** *(string) --* **[REQUIRED]** 

              The SMTP reply code, as defined by `RFC 5321`_ .

              

            
            - **StatusCode** *(string) --* 

              The SMTP enhanced status code, as defined by `RFC 3463`_ .

              

            
            - **Message** *(string) --* **[REQUIRED]** 

              Human-readable text to include in the bounce message.

              

            
            - **Sender** *(string) --* **[REQUIRED]** 

              The email address of the sender of the bounced email. This is the address from which the bounce message will be sent.

              

            
          
          - **WorkmailAction** *(dict) --* 

            Calls Amazon WorkMail and, optionally, publishes a notification to Amazon SNS.

            

          
            - **TopicArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the WorkMail action is called. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **OrganizationArn** *(string) --* **[REQUIRED]** 

              The ARN of the Amazon WorkMail organization. An example of an Amazon WorkMail organization ARN is ``arn:aws:workmail:us-west-2:123456789012:organization/m-68755160c4cb4e29a2b2f8fb58f359d7`` . For information about Amazon WorkMail organizations, see the `Amazon WorkMail Administrator Guide`_ .

              

            
          
          - **LambdaAction** *(dict) --* 

            Calls an AWS Lambda function, and optionally, publishes a notification to Amazon SNS.

            

          
            - **TopicArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the Lambda action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **FunctionArn** *(string) --* **[REQUIRED]** 

              The Amazon Resource Name (ARN) of the AWS Lambda function. An example of an AWS Lambda function ARN is ``arn:aws:lambda:us-west-2:account-id:function:MyFunction`` . For more information about AWS Lambda, see the `AWS Lambda Developer Guide`_ .

              

            
            - **InvocationType** *(string) --* 

              The invocation type of the AWS Lambda function. An invocation type of ``RequestResponse`` means that the execution of the function will immediately result in a response, and a value of ``Event`` means that the function will be invoked asynchronously. The default value is ``Event`` . For information about AWS Lambda invocation types, see the `AWS Lambda Developer Guide`_ .

               

              .. warning::

                 

                There is a 30-second timeout on ``RequestResponse`` invocations. You should use ``Event`` invocation in most cases. Use ``RequestResponse`` only when you want to make a mail flow decision, such as whether to stop the receipt rule or the receipt rule set.

                 

              

            
          
          - **StopAction** *(dict) --* 

            Terminates the evaluation of the receipt rule set and optionally publishes a notification to Amazon SNS.

            

          
            - **Scope** *(string) --* **[REQUIRED]** 

              The scope to which the Stop action applies. That is, what is being stopped.

              

            
            - **TopicArn** *(string) --* 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the stop action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
          
          - **AddHeaderAction** *(dict) --* 

            Adds a header to the received email.

            

          
            - **HeaderName** *(string) --* **[REQUIRED]** 

              The name of the header to add. Must be between 1 and 50 characters, inclusive, and consist of alphanumeric (a-z, A-Z, 0-9) characters and dashes only.

              

            
            - **HeaderValue** *(string) --* **[REQUIRED]** 

              Must be less than 2048 characters, and must not contain newline characters ("\r" or "\n").

              

            
          
          - **SNSAction** *(dict) --* 

            Publishes the email content within a notification to Amazon SNS.

            

          
            - **TopicArn** *(string) --* **[REQUIRED]** 

              The Amazon Resource Name (ARN) of the Amazon SNS topic to notify. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide`_ .

              

            
            - **Encoding** *(string) --* 

              The encoding to use for the email within the Amazon SNS notification. UTF-8 is easier to use, but may not preserve all special characters when a message was encoded with a different encoding format. Base64 preserves all special characters. The default value is UTF-8.

              

            
          
        
    
      - **ScanEnabled** *(boolean) --* 

        If ``true`` , then messages to which this receipt rule applies are scanned for spam and viruses. The default value is ``false`` .

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

  .. py:method:: verify_domain_dkim(**kwargs)

    

    Returns a set of DKIM tokens for a domain. DKIM *tokens* are character strings that represent your domain's identity. Using these tokens, you will need to create DNS CNAME records that point to DKIM public keys hosted by Amazon SES. Amazon Web Services will eventually detect that you have updated your DNS records; this detection process may take up to 72 hours. Upon successful detection, Amazon SES will be able to DKIM-sign email originating from that domain.

     

    This action is throttled at one request per second.

     

    To enable or disable Easy DKIM signing for a domain, use the ``SetIdentityDkimEnabled`` action.

     

    For more information about creating DNS records using DKIM tokens, go to the `Amazon SES Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.verify_domain_dkim(
          Domain='string'
      )
    :type Domain: string
    :param Domain: **[REQUIRED]** 

      The name of the domain to be verified for Easy DKIM signing.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DkimTokens': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Returns CNAME records that you must publish to the DNS server of your domain to set up Easy DKIM with Amazon SES.

        
        

        - **DkimTokens** *(list) --* 

          A set of character strings that represent the domain's identity. If the identity is an email address, the tokens represent the domain of that address.

           

          Using these tokens, you will need to create DNS CNAME records that point to DKIM public keys hosted by Amazon SES. Amazon Web Services will eventually detect that you have updated your DNS records; this detection process may take up to 72 hours. Upon successful detection, Amazon SES will be able to DKIM-sign emails originating from that domain.

           

          For more information about creating DNS records using DKIM tokens, go to the `Amazon SES Developer Guide`_ .

          
          

          - *(string) --* 
      
    

  .. py:method:: verify_domain_identity(**kwargs)

    

    Verifies a domain.

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.verify_domain_identity(
          Domain='string'
      )
    :type Domain: string
    :param Domain: **[REQUIRED]** 

      The domain to be verified.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'VerificationToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Returns a TXT record that you must publish to the DNS server of your domain to complete domain verification with Amazon SES.

        
        

        - **VerificationToken** *(string) --* 

          A TXT record that must be placed in the DNS settings for the domain, in order to complete domain verification.

          
    

  .. py:method:: verify_email_address(**kwargs)

    

    Verifies an email address. This action causes a confirmation email message to be sent to the specified address.

     

    .. warning::

       

      The VerifyEmailAddress action is deprecated as of the May 15, 2012 release of Domain Verification. The VerifyEmailIdentity action is now preferred.

       

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.verify_email_address(
          EmailAddress='string'
      )
    :type EmailAddress: string
    :param EmailAddress: **[REQUIRED]** 

      The email address to be verified.

      

    
    
    :returns: None

  .. py:method:: verify_email_identity(**kwargs)

    

    Verifies an email address. This action causes a confirmation email message to be sent to the specified address.

     

    This action is throttled at one request per second.

    

    **Request Syntax** 
    ::

      response = client.verify_email_identity(
          EmailAddress='string'
      )
    :type EmailAddress: string
    :param EmailAddress: **[REQUIRED]** 

      The email address to be verified.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        An empty element returned on a successful request.

        
    

==========
Paginators
==========


The available paginators are:

* :py:class:`SES.Paginator.ListIdentities`



.. py:class:: SES.Paginator.ListIdentities

  ::

    
    paginator = client.get_paginator('list_identities')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`SES.Client.list_identities`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          IdentityType='EmailAddress'|'Domain',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type IdentityType: string
    :param IdentityType: 

      The type of the identities to list. Possible values are "EmailAddress" and "Domain". If this parameter is omitted, then all identities will be listed.

      

    
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
            'Identities': [
                'string',
            ],
            
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of all identities that you have attempted to verify under your AWS account, regardless of verification status.

        
        

        - **Identities** *(list) --* 

          A list of identities.

          
          

          - *(string) --* 
      
    

=======
Waiters
=======


The available waiters are:

* :py:class:`SES.Waiter.IdentityExists`



.. py:class:: SES.Waiter.IdentityExists

  ::

    
    waiter = client.get_waiter('identity_exists')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`SES.Client.get_identity_verification_attributes` every 3 seconds until a successful state is reached. An error is returned after 20 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          Identities=[
              'string',
          ]
      )
    :type Identities: list
    :param Identities: **[REQUIRED]** 

      A list of identities.

      

    
      - *(string) --* 

      
  
    
    :returns: None