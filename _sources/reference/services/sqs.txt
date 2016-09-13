

.. _Shared Queues: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/acp-overview.html
.. _epoch time: http://en.wikipedia.org/wiki/Unix_time
.. _Amazon SQS Long Poll: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-long-polling.html
.. _Responses: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/UnderstandingResponses.html
.. _Visibility Timeout: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AboutVT.html
.. _How Amazon SQS Queues Work: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSConcepts.html
.. _Message Attribute Items: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSMessageAttributes.html#SQSMessageAttributesNTV
.. _Message Attribute Data Types: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSMessageAttributes.html#SQSMessageAttributes.DataTypes
.. _Overview of AWS IAM Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/PoliciesOverview.html
.. _Resources Required to Process Messages: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/ApproximateNumber.html
.. _Understanding Permissions: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/acp-overview.html#PermissionTypes
.. _Your AWS Identifiers: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AWSCredentials.html
.. _Queue and Message Identifiers: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/ImportantIdentifiers.html
.. _SendMessage: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_SendMessage.html
.. _Using The Access Policy Language: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AccessPolicyLanguage.html
.. _http\://www.faqs.org/rfcs/rfc1321.html: http://www.faqs.org/rfcs/rfc1321.html
.. _http\://www.w3.org/TR/REC-xml/#charsets: http://www.w3.org/TR/REC-xml/#charsets
.. _http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters: http://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters
.. _Using Amazon SQS Dead Letter Queues: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSDeadLetterQueue.html
.. _principal: http://docs.aws.amazon.com/general/latest/gr/glos-chap.html#P


***
SQS
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: SQS.Client

  A low-level client representing Amazon Simple Queue Service (SQS)::

    
    import boto3
    
    client = boto3.client('sqs')

  
  These are the available methods:
  
  *   :py:meth:`add_permission`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`change_message_visibility`

  
  *   :py:meth:`change_message_visibility_batch`

  
  *   :py:meth:`create_queue`

  
  *   :py:meth:`delete_message`

  
  *   :py:meth:`delete_message_batch`

  
  *   :py:meth:`delete_queue`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_queue_attributes`

  
  *   :py:meth:`get_queue_url`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_dead_letter_source_queues`

  
  *   :py:meth:`list_queues`

  
  *   :py:meth:`purge_queue`

  
  *   :py:meth:`receive_message`

  
  *   :py:meth:`remove_permission`

  
  *   :py:meth:`send_message`

  
  *   :py:meth:`send_message_batch`

  
  *   :py:meth:`set_queue_attributes`

  

  .. py:method:: add_permission(**kwargs)

    

    Adds a permission to a queue for a specific `principal`_ . This allows for sharing access to the queue.

     

    When you create a queue, you have full control access rights for the queue. Only you (as owner of the queue) can grant or deny permissions to the queue. For more information about these permissions, see `Shared Queues`_ in the *Amazon SQS Developer Guide* .

     

    .. note::

       

      ``AddPermission`` writes an Amazon SQS-generated policy. If you want to write your own policy, use  SetQueueAttributes to upload your policy. For more information about writing your own policy, see `Using The Access Policy Language`_ in the *Amazon SQS Developer Guide* .

       

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = client.add_permission(
          QueueUrl='string',
          Label='string',
          AWSAccountIds=[
              'string',
          ],
          Actions=[
              'string',
          ]
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type Label: string
    :param Label: **[REQUIRED]** 

      The unique identification of the permission you're setting (e.g., ``AliceSendMessage`` ). Constraints: Maximum 80 characters; alphanumeric characters, hyphens (-), and underscores (_) are allowed.

      

    
    :type AWSAccountIds: list
    :param AWSAccountIds: **[REQUIRED]** 

      The AWS account number of the `principal`_ who will be given permission. The principal must have an AWS account, but does not need to be signed up for Amazon SQS. For information about locating the AWS account identification, see `Your AWS Identifiers`_ in the *Amazon SQS Developer Guide* .

      

    
      - *(string) --* 

      
  
    :type Actions: list
    :param Actions: **[REQUIRED]** 

      The action the client wants to allow for the specified principal. The following are valid values: ``* | SendMessage | ReceiveMessage | DeleteMessage | ChangeMessageVisibility | GetQueueAttributes | GetQueueUrl`` . For more information about these actions, see `Understanding Permissions`_ in the *Amazon SQS Developer Guide* .

       

      Specifying ``SendMessage`` , ``DeleteMessage`` , or ``ChangeMessageVisibility`` for the ``ActionName.n`` also grants permissions for the corresponding batch versions of those actions: ``SendMessageBatch`` , ``DeleteMessageBatch`` , and ``ChangeMessageVisibilityBatch`` .

      

    
      - *(string) --* 

      
  
    
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


  .. py:method:: change_message_visibility(**kwargs)

    

    Changes the visibility timeout of a specified message in a queue to a new value. The maximum allowed timeout value you can set the value to is 12 hours. This means you can't extend the timeout of a message in an existing queue to more than a total visibility timeout of 12 hours. (For more information visibility timeout, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* .)

     

    For example, let's say you have a message and its default message visibility timeout is 5 minutes. After 3 minutes, you call ``ChangeMessageVisiblity`` with a timeout of 10 minutes. At that time, the timeout for the message would be extended by 10 minutes beyond the time of the ChangeMessageVisibility call. This results in a total visibility timeout of 13 minutes. You can continue to call ChangeMessageVisibility to extend the visibility timeout to a maximum of 12 hours. If you try to extend beyond 12 hours, the request will be rejected.

     

    .. note::

      

      There is a 120,000 limit for the number of inflight messages per queue. Messages are inflight after they have been received from the queue by a consuming component, but have not yet been deleted from the queue. If you reach the 120,000 limit, you will receive an OverLimit error message from Amazon SQS. To help avoid reaching the limit, you should delete the messages from the queue after they have been processed. You can also increase the number of queues you use to process the messages. 

      

     

    .. warning::

      

      If you attempt to set the ``VisibilityTimeout`` to an amount more than the maximum time left, Amazon SQS returns an error. It will not automatically recalculate and increase the timeout to the maximum time remaining.

      

     

    .. warning::

      

      Unlike with a queue, when you change the visibility timeout for a specific message, that timeout value is applied immediately but is not saved in memory for that message. If you don't delete a message after it is received, the visibility timeout for the message the next time it is received reverts to the original timeout value, not the value you set with the ``ChangeMessageVisibility`` action.

      

    

    **Request Syntax** 
    ::

      response = client.change_message_visibility(
          QueueUrl='string',
          ReceiptHandle='string',
          VisibilityTimeout=123
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type ReceiptHandle: string
    :param ReceiptHandle: **[REQUIRED]** 

      The receipt handle associated with the message whose visibility timeout should be changed. This parameter is returned by the  ReceiveMessage action.

      

    
    :type VisibilityTimeout: integer
    :param VisibilityTimeout: **[REQUIRED]** 

      The new value (in seconds - from 0 to 43200 - maximum 12 hours) for the message's visibility timeout.

      

    
    
    :returns: None

  .. py:method:: change_message_visibility_batch(**kwargs)

    

    Changes the visibility timeout of multiple messages. This is a batch version of  ChangeMessageVisibility . The result of the action on each message is reported individually in the response. You can send up to 10  ChangeMessageVisibility requests with each ``ChangeMessageVisibilityBatch`` action.

     

    .. warning::

      

      Because the batch request can result in a combination of successful and unsuccessful actions, you should check for batch errors even when the call returns an HTTP status code of 200.

      

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = client.change_message_visibility_batch(
          QueueUrl='string',
          Entries=[
              {
                  'Id': 'string',
                  'ReceiptHandle': 'string',
                  'VisibilityTimeout': 123
              },
          ]
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type Entries: list
    :param Entries: **[REQUIRED]** 

      A list of receipt handles of the messages for which the visibility timeout must be changed.

      

    
      - *(dict) --* 

        Encloses a receipt handle and an entry id for each message in  ChangeMessageVisibilityBatch . 

         

        .. warning::

           

          All of the following parameters are list parameters that must be prefixed with ``ChangeMessageVisibilityBatchRequestEntry.n`` , where ``n`` is an integer value starting with 1. For example, a parameter list for this action might look like this:

           

         

        ```` 

         

        ```` 

         

        ```` 

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          An identifier for this particular receipt handle. This is used to communicate the result. Note that the ``Id`` s of a batch request need to be unique within the request.

          

        
        - **ReceiptHandle** *(string) --* **[REQUIRED]** 

          A receipt handle.

          

        
        - **VisibilityTimeout** *(integer) --* 

          The new value (in seconds) for the message's visibility timeout.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Successful': [
                {
                    'Id': 'string'
                },
            ],
            'Failed': [
                {
                    'Id': 'string',
                    'SenderFault': True|False,
                    'Code': 'string',
                    'Message': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        For each message in the batch, the response contains a  ChangeMessageVisibilityBatchResultEntry tag if the message succeeds or a  BatchResultErrorEntry tag if the message fails. 

        
        

        - **Successful** *(list) --* 

          A list of  ChangeMessageVisibilityBatchResultEntry items.

          
          

          - *(dict) --* 

            Encloses the id of an entry in  ChangeMessageVisibilityBatch .

            
            

            - **Id** *(string) --* 

              Represents a message whose visibility timeout has been changed successfully.

              
        
      
        

        - **Failed** *(list) --* 

          A list of  BatchResultErrorEntry items.

          
          

          - *(dict) --* 

            This is used in the responses of batch API to give a detailed description of the result of an action on each entry in the request.

            
            

            - **Id** *(string) --* 

              The id of an entry in a batch request.

              
            

            - **SenderFault** *(boolean) --* 

              Whether the error happened due to the sender's fault.

              
            

            - **Code** *(string) --* 

              An error code representing why the action failed on this entry.

              
            

            - **Message** *(string) --* 

              A message explaining why the action failed on this entry.

              
        
      
    

  .. py:method:: create_queue(**kwargs)

    

    Creates a new queue, or returns the URL of an existing one. When you request ``CreateQueue`` , you provide a name for the queue. To successfully create a new queue, you must provide a name that is unique within the scope of your own queues.

     

    .. note::

       

      If you delete a queue, you must wait at least 60 seconds before creating a queue with the same name.

       

     

    You may pass one or more attributes in the request. If you do not provide a value for any attribute, the queue will have the default value for that attribute.

     

    .. note::

      

      Use  GetQueueUrl to get a queue's URL.  GetQueueUrl requires only the ``QueueName`` parameter.

      

     

    If you provide the name of an existing queue, along with the exact names and values of all the queue's attributes, ``CreateQueue`` returns the queue URL for the existing queue. If the queue name, attribute names, or attribute values do not match an existing queue, ``CreateQueue`` returns an error.

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = client.create_queue(
          QueueName='string',
          Attributes={
              'string': 'string'
          }
      )
    :type QueueName: string
    :param QueueName: **[REQUIRED]** 

      The name for the queue to be created.

       

      Queue names are case-sensitive.

      

    
    :type Attributes: dict
    :param Attributes: 

      A map of attributes with their corresponding values.

       

      The following lists the names, descriptions, and values of the special request parameters the ``CreateQueue`` action uses:

       

       
      * ``DelaySeconds`` - The time in seconds that the delivery of all messages in the queue will be delayed. An integer from 0 to 900 (15 minutes). The default for this attribute is 0 (zero).
       
      * ``MaximumMessageSize`` - The limit of how many bytes a message can contain before Amazon SQS rejects it. An integer from 1024 bytes (1 KiB) up to 262144 bytes (256 KiB). The default for this attribute is 262144 (256 KiB).
       
      * ``MessageRetentionPeriod`` - The number of seconds Amazon SQS retains a message. Integer representing seconds, from 60 (1 minute) to 1209600 (14 days). The default for this attribute is 345600 (4 days).
       
      * ``Policy`` - The queue's policy. A valid AWS policy. For more information about policy structure, see `Overview of AWS IAM Policies`_ in the *Amazon IAM User Guide* .
       
      * ``ReceiveMessageWaitTimeSeconds`` - The time for which a  ReceiveMessage call will wait for a message to arrive. An integer from 0 to 20 (seconds). The default for this attribute is 0.
       
      * ``RedrivePolicy`` - The parameters for dead letter queue functionality of the source queue. For more information about RedrivePolicy and dead letter queues, see `Using Amazon SQS Dead Letter Queues`_ in the *Amazon SQS Developer Guide* .
       
      * ``VisibilityTimeout`` - The visibility timeout for the queue. An integer from 0 to 43200 (12 hours). The default for this attribute is 30. For more information about visibility timeout, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* .
       

       

      Any other valid special request parameters that are specified (such as ``ApproximateNumberOfMessages`` , ``ApproximateNumberOfMessagesDelayed`` , ``ApproximateNumberOfMessagesNotVisible`` , ``CreatedTimestamp`` , ``LastModifiedTimestamp`` , and ``QueueArn`` ) will be ignored.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'QueueUrl': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Returns the QueueUrl element of the created queue.

        
        

        - **QueueUrl** *(string) --* 

          The URL for the created Amazon SQS queue.

          
    

    **Examples** 

    The following operation creates an SQS queue named MyQueue.
    ::

      response = client.create_queue(
          QueueName='MyQueue',
      )
      
      print(response)

    
    Expected Output:
    ::

      {
          'QueueUrl': 'https://queue.amazonaws.com/012345678910/MyQueue',
          'ResponseMetadata': {
              '...': '...',
          },
      }

    

  .. py:method:: delete_message(**kwargs)

    

    Deletes the specified message from the specified queue. You specify the message by using the message's ``receipt handle`` and not the ``message ID`` you received when you sent the message. Even if the message is locked by another reader due to the visibility timeout setting, it is still deleted from the queue. If you leave a message in the queue for longer than the queue's configured retention period, Amazon SQS automatically deletes it. 

     

    .. note::

       

      The receipt handle is associated with a specific instance of receiving the message. If you receive a message more than once, the receipt handle you get each time you receive the message is different. When you request ``DeleteMessage`` , if you don't provide the most recently received receipt handle for the message, the request will still succeed, but the message might not be deleted. 

       

     

    .. warning::

       

      It is possible you will receive a message even after you have deleted it. This might happen on rare occasions if one of the servers storing a copy of the message is unavailable when you request to delete the message. The copy remains on the server and might be returned to you again on a subsequent receive request. You should create your system to be idempotent so that receiving a particular message more than once is not a problem. 

       

    

    **Request Syntax** 
    ::

      response = client.delete_message(
          QueueUrl='string',
          ReceiptHandle='string'
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type ReceiptHandle: string
    :param ReceiptHandle: **[REQUIRED]** 

      The receipt handle associated with the message to delete.

      

    
    
    :returns: None

  .. py:method:: delete_message_batch(**kwargs)

    

    Deletes up to ten messages from the specified queue. This is a batch version of  DeleteMessage . The result of the delete action on each message is reported individually in the response.

     

    .. warning::

       

      Because the batch request can result in a combination of successful and unsuccessful actions, you should check for batch errors even when the call returns an HTTP status code of 200. 

       

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = client.delete_message_batch(
          QueueUrl='string',
          Entries=[
              {
                  'Id': 'string',
                  'ReceiptHandle': 'string'
              },
          ]
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type Entries: list
    :param Entries: **[REQUIRED]** 

      A list of receipt handles for the messages to be deleted.

      

    
      - *(dict) --* 

        Encloses a receipt handle and an identifier for it.

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          An identifier for this particular receipt handle. This is used to communicate the result. Note that the ``Id`` s of a batch request need to be unique within the request.

          

        
        - **ReceiptHandle** *(string) --* **[REQUIRED]** 

          A receipt handle.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Successful': [
                {
                    'Id': 'string'
                },
            ],
            'Failed': [
                {
                    'Id': 'string',
                    'SenderFault': True|False,
                    'Code': 'string',
                    'Message': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        For each message in the batch, the response contains a  DeleteMessageBatchResultEntry tag if the message is deleted or a  BatchResultErrorEntry tag if the message cannot be deleted. 

        
        

        - **Successful** *(list) --* 

          A list of  DeleteMessageBatchResultEntry items.

          
          

          - *(dict) --* 

            Encloses the id an entry in  DeleteMessageBatch .

            
            

            - **Id** *(string) --* 

              Represents a successfully deleted message.

              
        
      
        

        - **Failed** *(list) --* 

          A list of  BatchResultErrorEntry items.

          
          

          - *(dict) --* 

            This is used in the responses of batch API to give a detailed description of the result of an action on each entry in the request.

            
            

            - **Id** *(string) --* 

              The id of an entry in a batch request.

              
            

            - **SenderFault** *(boolean) --* 

              Whether the error happened due to the sender's fault.

              
            

            - **Code** *(string) --* 

              An error code representing why the action failed on this entry.

              
            

            - **Message** *(string) --* 

              A message explaining why the action failed on this entry.

              
        
      
    

  .. py:method:: delete_queue(**kwargs)

    

    Deletes the queue specified by the **queue URL** , regardless of whether the queue is empty. If the specified queue does not exist, Amazon SQS returns a successful response. 

     

    .. warning::

       

      Use ``DeleteQueue`` with care; once you delete your queue, any messages in the queue are no longer available. 

       

     

    When you delete a queue, the deletion process takes up to 60 seconds. Requests you send involving that queue during the 60 seconds might succeed. For example, a  SendMessage request might succeed, but after the 60 seconds, the queue and that message you sent no longer exist. Also, when you delete a queue, you must wait at least 60 seconds before creating a queue with the same name. 

     

    We reserve the right to delete queues that have had no activity for more than 30 days. For more information, see `How Amazon SQS Queues Work`_ in the *Amazon SQS Developer Guide* . 

    

    **Request Syntax** 
    ::

      response = client.delete_queue(
          QueueUrl='string'
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    
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


  .. py:method:: get_queue_attributes(**kwargs)

    

    Gets attributes for the specified queue.

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = client.get_queue_attributes(
          QueueUrl='string',
          AttributeNames=[
              'Policy'|'VisibilityTimeout'|'MaximumMessageSize'|'MessageRetentionPeriod'|'ApproximateNumberOfMessages'|'ApproximateNumberOfMessagesNotVisible'|'CreatedTimestamp'|'LastModifiedTimestamp'|'QueueArn'|'ApproximateNumberOfMessagesDelayed'|'DelaySeconds'|'ReceiveMessageWaitTimeSeconds'|'RedrivePolicy',
          ]
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type AttributeNames: list
    :param AttributeNames: 

      A list of attributes to retrieve information for. The following attributes are supported:

       

       
      * ``All`` - returns all values.
       
      * ``ApproximateNumberOfMessages`` - returns the approximate number of visible messages in a queue. For more information, see `Resources Required to Process Messages`_ in the *Amazon SQS Developer Guide* .
       
      * ``ApproximateNumberOfMessagesNotVisible`` - returns the approximate number of messages that are not timed-out and not deleted. For more information, see `Resources Required to Process Messages`_ in the *Amazon SQS Developer Guide* .
       
      * ``VisibilityTimeout`` - returns the visibility timeout for the queue. For more information about visibility timeout, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* .
       
      * ``CreatedTimestamp`` - returns the time when the queue was created (epoch time in seconds).
       
      * ``LastModifiedTimestamp`` - returns the time when the queue was last changed (epoch time in seconds).
       
      * ``Policy`` - returns the queue's policy.
       
      * ``MaximumMessageSize`` - returns the limit of how many bytes a message can contain before Amazon SQS rejects it.
       
      * ``MessageRetentionPeriod`` - returns the number of seconds Amazon SQS retains a message.
       
      * ``QueueArn`` - returns the queue's Amazon resource name (ARN).
       
      * ``ApproximateNumberOfMessagesDelayed`` - returns the approximate number of messages that are pending to be added to the queue.
       
      * ``DelaySeconds`` - returns the default delay on the queue in seconds.
       
      * ``ReceiveMessageWaitTimeSeconds`` - returns the time for which a ReceiveMessage call will wait for a message to arrive.
       
      * ``RedrivePolicy`` - returns the parameters for dead letter queue functionality of the source queue. For more information about RedrivePolicy and dead letter queues, see `Using Amazon SQS Dead Letter Queues`_ in the *Amazon SQS Developer Guide* .
       

       

      .. note::

        

        Going forward, new attributes might be added. If you are writing code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully.

        

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Attributes': {
                'string': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of returned queue attributes.

        
        

        - **Attributes** *(dict) --* 

          A map of attributes to the respective values.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
    

  .. py:method:: get_queue_url(**kwargs)

    

    Returns the URL of an existing queue. This action provides a simple way to retrieve the URL of an Amazon SQS queue. 

     

    To access a queue that belongs to another AWS account, use the ``QueueOwnerAWSAccountId`` parameter to specify the account ID of the queue's owner. The queue's owner must grant you permission to access the queue. For more information about shared queue access, see  AddPermission or go to `Shared Queues`_ in the *Amazon SQS Developer Guide* . 

    

    **Request Syntax** 
    ::

      response = client.get_queue_url(
          QueueName='string',
          QueueOwnerAWSAccountId='string'
      )
    :type QueueName: string
    :param QueueName: **[REQUIRED]** 

      The name of the queue whose URL must be fetched. Maximum 80 characters; alphanumeric characters, hyphens (-), and underscores (_) are allowed.

       

      Queue names are case-sensitive.

      

    
    :type QueueOwnerAWSAccountId: string
    :param QueueOwnerAWSAccountId: 

      The AWS account ID of the account that created the queue.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'QueueUrl': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        For more information, see `Responses`_ in the *Amazon SQS Developer Guide* .

        
        

        - **QueueUrl** *(string) --* 

          The URL for the queue.

          
    

    **Examples** 

    The following example retrieves the queue ARN.
    ::

      response = client.get_queue_url(
          QueueName='MyQueue',
          QueueOwnerAWSAccountId='12345678910',
      )
      
      print(response)

    
    Expected Output:
    ::

      {
          'QueueUrl': 'https://queue.amazonaws.com/123456789101112/MyQueue',
          'ResponseMetadata': {
              '...': '...',
          },
      }

    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: list_dead_letter_source_queues(**kwargs)

    

    Returns a list of your queues that have the RedrivePolicy queue attribute configured with a dead letter queue.

     

    For more information about using dead letter queues, see `Using Amazon SQS Dead Letter Queues`_ .

    

    **Request Syntax** 
    ::

      response = client.list_dead_letter_source_queues(
          QueueUrl='string'
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The queue URL of a dead letter queue.

       

      Queue URLs are case-sensitive.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'queueUrls': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of your dead letter source queues.

        
        

        - **queueUrls** *(list) --* 

          A list of source queue URLs that have the RedrivePolicy queue attribute configured with a dead letter queue.

          
          

          - *(string) --* 
      
    

  .. py:method:: list_queues(**kwargs)

    

    Returns a list of your queues. The maximum number of queues that can be returned is 1000. If you specify a value for the optional ``QueueNamePrefix`` parameter, only queues with a name beginning with the specified value are returned.

    

    **Request Syntax** 
    ::

      response = client.list_queues(
          QueueNamePrefix='string'
      )
    :type QueueNamePrefix: string
    :param QueueNamePrefix: 

      A string to use for filtering the list results. Only those queues whose name begins with the specified string are returned.

       

      Queue names are case-sensitive.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'QueueUrls': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of your queues.

        
        

        - **QueueUrls** *(list) --* 

          A list of queue URLs, up to 1000 entries.

          
          

          - *(string) --* 
      
    

  .. py:method:: purge_queue(**kwargs)

    

    Deletes the messages in a queue specified by the **queue URL** .

     

    .. warning::

      

      When you use the ``PurgeQueue`` API, the deleted messages in the queue cannot be retrieved.

      

     

    When you purge a queue, the message deletion process takes up to 60 seconds. All messages sent to the queue before calling ``PurgeQueue`` will be deleted; messages sent to the queue while it is being purged may be deleted. While the queue is being purged, messages sent to the queue before ``PurgeQueue`` was called may be received, but will be deleted within the next minute.

    

    **Request Syntax** 
    ::

      response = client.purge_queue(
          QueueUrl='string'
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The queue URL of the queue to delete the messages from when using the ``PurgeQueue`` API.

       

      Queue URLs are case-sensitive.

      

    
    
    :returns: None

  .. py:method:: receive_message(**kwargs)

    

    Retrieves one or more messages, with a maximum limit of 10 messages, from the specified queue. Long poll support is enabled by using the ``WaitTimeSeconds`` parameter. For more information, see `Amazon SQS Long Poll`_ in the *Amazon SQS Developer Guide* . 

     

    Short poll is the default behavior where a weighted random set of machines is sampled on a ``ReceiveMessage`` call. This means only the messages on the sampled machines are returned. If the number of messages in the queue is small (less than 1000), it is likely you will get fewer messages than you requested per ``ReceiveMessage`` call. If the number of messages in the queue is extremely small, you might not receive any messages in a particular ``ReceiveMessage`` response; in which case you should repeat the request. 

     

    For each message returned, the response includes the following: 

     

     
    * Message body  
     
    * MD5 digest of the message body. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .  
     
    * Message ID you received when you sent the message to the queue.  
     
    * Receipt handle.  
     
    * Message attributes.  
     
    * MD5 digest of the message attributes.  
     

     

    The receipt handle is the identifier you must provide when deleting the message. For more information, see `Queue and Message Identifiers`_ in the *Amazon SQS Developer Guide* . 

     

    You can provide the ``VisibilityTimeout`` parameter in your request, which will be applied to the messages that Amazon SQS returns in the response. If you do not include the parameter, the overall visibility timeout for the queue is used for the returned messages. For more information, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* . 

     

    .. note::

       

      Going forward, new attributes might be added. If you are writing code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully. 

       

    

    **Request Syntax** 
    ::

      response = client.receive_message(
          QueueUrl='string',
          AttributeNames=[
              'Policy'|'VisibilityTimeout'|'MaximumMessageSize'|'MessageRetentionPeriod'|'ApproximateNumberOfMessages'|'ApproximateNumberOfMessagesNotVisible'|'CreatedTimestamp'|'LastModifiedTimestamp'|'QueueArn'|'ApproximateNumberOfMessagesDelayed'|'DelaySeconds'|'ReceiveMessageWaitTimeSeconds'|'RedrivePolicy',
          ],
          MessageAttributeNames=[
              'string',
          ],
          MaxNumberOfMessages=123,
          VisibilityTimeout=123,
          WaitTimeSeconds=123
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type AttributeNames: list
    :param AttributeNames: 

      A list of attributes that need to be returned along with each message. These attributes include:

       

       
      * ``All`` - returns all values.
       
      * ``ApproximateFirstReceiveTimestamp`` - returns the time when the message was first received from the queue (epoch time in milliseconds).
       
      * ``ApproximateReceiveCount`` - returns the number of times a message has been received from the queue but not deleted.
       
      * ``SenderId`` - returns the AWS account number (or the IP address, if anonymous access is allowed) of the sender.
       
      * ``SentTimestamp`` - returns the time when the message was sent to the queue (epoch time in milliseconds).
       

       

      Any other valid special request parameters that are specified (such as ``ApproximateNumberOfMessages`` , ``ApproximateNumberOfMessagesDelayed`` , ``ApproximateNumberOfMessagesNotVisible`` , ``CreatedTimestamp`` , ``DelaySeconds`` , ``LastModifiedTimestamp`` , ``MaximumMessageSize`` , ``MessageRetentionPeriod`` , ``Policy`` , ``QueueArn`` , ``ReceiveMessageWaitTimeSeconds`` , ``RedrivePolicy`` , and ``VisibilityTimeout`` ) will be ignored.

      

    
      - *(string) --* 

      
  
    :type MessageAttributeNames: list
    :param MessageAttributeNames: 

      The name of the message attribute, where *N* is the index. The message attribute name can contain the following characters: A-Z, a-z, 0-9, underscore (_), hyphen (-), and period (.). The name must not start or end with a period, and it should not have successive periods. The name is case sensitive and must be unique among all attribute names for the message. The name can be up to 256 characters long. The name cannot start with "AWS." or "Amazon." (or any variations in casing), because these prefixes are reserved for use by Amazon Web Services.

       

      When using ``ReceiveMessage`` , you can send a list of attribute names to receive, or you can return all of the attributes by specifying "All" or ".*" in your request. You can also use "bar.*" to return all message attributes starting with the "bar" prefix.

      

    
      - *(string) --* 

      
  
    :type MaxNumberOfMessages: integer
    :param MaxNumberOfMessages: 

      The maximum number of messages to return. Amazon SQS never returns more messages than this value but may return fewer. Values can be from 1 to 10. Default is 1.

       

      All of the messages are not necessarily returned.

      

    
    :type VisibilityTimeout: integer
    :param VisibilityTimeout: 

      The duration (in seconds) that the received messages are hidden from subsequent retrieve requests after being retrieved by a ``ReceiveMessage`` request.

      

    
    :type WaitTimeSeconds: integer
    :param WaitTimeSeconds: 

      The duration (in seconds) for which the call will wait for a message to arrive in the queue before returning. If a message is available, the call will return sooner than WaitTimeSeconds.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Messages': [
                {
                    'MessageId': 'string',
                    'ReceiptHandle': 'string',
                    'MD5OfBody': 'string',
                    'Body': 'string',
                    'Attributes': {
                        'string': 'string'
                    },
                    'MD5OfMessageAttributes': 'string',
                    'MessageAttributes': {
                        'string': {
                            'StringValue': 'string',
                            'BinaryValue': b'bytes',
                            'StringListValues': [
                                'string',
                            ],
                            'BinaryListValues': [
                                b'bytes',
                            ],
                            'DataType': 'string'
                        }
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of received messages.

        
        

        - **Messages** *(list) --* 

          A list of messages.

          
          

          - *(dict) --* 

            An Amazon SQS message.

            
            

            - **MessageId** *(string) --* 

              A unique identifier for the message. Message IDs are considered unique across all AWS accounts for an extended period of time.

              
            

            - **ReceiptHandle** *(string) --* 

              An identifier associated with the act of receiving the message. A new receipt handle is returned every time you receive a message. When deleting a message, you provide the last received receipt handle to delete the message.

              
            

            - **MD5OfBody** *(string) --* 

              An MD5 digest of the non-URL-encoded message body string.

              
            

            - **Body** *(string) --* 

              The message's contents (not URL-encoded).

              
            

            - **Attributes** *(dict) --* 

              ``SenderId`` , ``SentTimestamp`` , ``ApproximateReceiveCount`` , and/or ``ApproximateFirstReceiveTimestamp`` . ``SentTimestamp`` and ``ApproximateFirstReceiveTimestamp`` are each returned as an integer representing the `epoch time`_ in milliseconds.

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
            

            - **MD5OfMessageAttributes** *(string) --* 

              An MD5 digest of the non-URL-encoded message attribute string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

              
            

            - **MessageAttributes** *(dict) --* 

              Each message attribute consists of a Name, Type, and Value. For more information, see `Message Attribute Items`_ .

              
              

              - *(string) --* 
                

                - *(dict) --* 

                  The user-specified message attribute value. For string data types, the value attribute has the same restrictions on the content as the message body. For more information, see `SendMessage`_ .

                   

                  Name, type, and value must not be empty or null. In addition, the message body should not be empty or null. All parts of the message attribute, including name, type, and value, are included in the message size restriction, which is currently 256 KB (262,144 bytes).

                  
                  

                  - **StringValue** *(string) --* 

                    Strings are Unicode with UTF8 binary encoding. For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ .

                    
                  

                  - **BinaryValue** *(bytes) --* 

                    Binary type attributes can store any binary data, for example, compressed data, encrypted data, or images.

                    
                  

                  - **StringListValues** *(list) --* 

                    Not implemented. Reserved for future use.

                    
                    

                    - *(string) --* 
                
                  

                  - **BinaryListValues** *(list) --* 

                    Not implemented. Reserved for future use.

                    
                    

                    - *(bytes) --* 
                
                  

                  - **DataType** *(string) --* 

                    Amazon SQS supports the following logical data types: String, Number, and Binary. For the Number data type, you must use StringValue.

                     

                    You can also append custom labels. For more information, see `Message Attribute Data Types`_ .

                    
              
          
        
        
      
    

  .. py:method:: remove_permission(**kwargs)

    

    Revokes any permissions in the queue policy that matches the specified ``Label`` parameter. Only the owner of the queue can remove permissions.

    

    **Request Syntax** 
    ::

      response = client.remove_permission(
          QueueUrl='string',
          Label='string'
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type Label: string
    :param Label: **[REQUIRED]** 

      The identification of the permission to remove. This is the label added with the  AddPermission action.

      

    
    
    :returns: None

  .. py:method:: send_message(**kwargs)

    

    Delivers a message to the specified queue. With Amazon SQS, you now have the ability to send large payload messages that are up to 256KB (262,144 bytes) in size. To send large payloads, you must use an AWS SDK that supports SigV4 signing. To verify whether SigV4 is supported for an AWS SDK, check the SDK release notes. 

     

    .. warning::

       

      The following list shows the characters (in Unicode) allowed in your message, according to the W3C XML specification. For more information, go to `http\://www.w3.org/TR/REC-xml/#charsets`_ If you send any characters not included in the list, your request will be rejected. 

       

      #x9 | #xA | #xD | [#x20 to #xD7FF] | [#xE000 to #xFFFD] | [#x10000 to #x10FFFF] 

       

    

    **Request Syntax** 
    ::

      response = client.send_message(
          QueueUrl='string',
          MessageBody='string',
          DelaySeconds=123,
          MessageAttributes={
              'string': {
                  'StringValue': 'string',
                  'BinaryValue': b'bytes',
                  'StringListValues': [
                      'string',
                  ],
                  'BinaryListValues': [
                      b'bytes',
                  ],
                  'DataType': 'string'
              }
          }
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type MessageBody: string
    :param MessageBody: **[REQUIRED]** 

      The message to send. String maximum 256 KB in size. For a list of allowed characters, see the preceding important note.

      

    
    :type DelaySeconds: integer
    :param DelaySeconds: 

      The number of seconds (0 to 900 - 15 minutes) to delay a specific message. Messages with a positive ``DelaySeconds`` value become available for processing after the delay time is finished. If you don't specify a value, the default value for the queue applies. 

      

    
    :type MessageAttributes: dict
    :param MessageAttributes: 

      Each message attribute consists of a Name, Type, and Value. For more information, see `Message Attribute Items`_ .

      

    
      - *(string) --* 

      
        - *(dict) --* 

          The user-specified message attribute value. For string data types, the value attribute has the same restrictions on the content as the message body. For more information, see `SendMessage`_ .

           

          Name, type, and value must not be empty or null. In addition, the message body should not be empty or null. All parts of the message attribute, including name, type, and value, are included in the message size restriction, which is currently 256 KB (262,144 bytes).

          

        
          - **StringValue** *(string) --* 

            Strings are Unicode with UTF8 binary encoding. For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ .

            

          
          - **BinaryValue** *(bytes) --* 

            Binary type attributes can store any binary data, for example, compressed data, encrypted data, or images.

            

          
          - **StringListValues** *(list) --* 

            Not implemented. Reserved for future use.

            

          
            - *(string) --* 

            
        
          - **BinaryListValues** *(list) --* 

            Not implemented. Reserved for future use.

            

          
            - *(bytes) --* 

            
        
          - **DataType** *(string) --* **[REQUIRED]** 

            Amazon SQS supports the following logical data types: String, Number, and Binary. For the Number data type, you must use StringValue.

             

            You can also append custom labels. For more information, see `Message Attribute Data Types`_ .

            

          
        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MD5OfMessageBody': 'string',
            'MD5OfMessageAttributes': 'string',
            'MessageId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The MD5OfMessageBody and MessageId elements.

        
        

        - **MD5OfMessageBody** *(string) --* 

          An MD5 digest of the non-URL-encoded message body string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

          
        

        - **MD5OfMessageAttributes** *(string) --* 

          An MD5 digest of the non-URL-encoded message attribute string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

          
        

        - **MessageId** *(string) --* 

          An element containing the message ID of the message sent to the queue. For more information, see `Queue and Message Identifiers`_ in the *Amazon SQS Developer Guide* . 

          
    

  .. py:method:: send_message_batch(**kwargs)

    

    Delivers up to ten messages to the specified queue. This is a batch version of  SendMessage . The result of the send action on each message is reported individually in the response. The maximum allowed individual message size is 256 KB (262,144 bytes).

     

    The maximum total payload size (i.e., the sum of all a batch's individual message lengths) is also 256 KB (262,144 bytes).

     

    If the ``DelaySeconds`` parameter is not specified for an entry, the default for the queue is used.

     

    .. warning::

      

      The following list shows the characters (in Unicode) that are allowed in your message, according to the W3C XML specification. For more information, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ . If you send any characters that are not included in the list, your request will be rejected.

       

      #x9 | #xA | #xD | [#x20 to #xD7FF] | [#xE000 to #xFFFD] | [#x10000 to #x10FFFF]

       

     

    .. warning::

       

      Because the batch request can result in a combination of successful and unsuccessful actions, you should check for batch errors even when the call returns an HTTP status code of 200.

       

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this: 

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = client.send_message_batch(
          QueueUrl='string',
          Entries=[
              {
                  'Id': 'string',
                  'MessageBody': 'string',
                  'DelaySeconds': 123,
                  'MessageAttributes': {
                      'string': {
                          'StringValue': 'string',
                          'BinaryValue': b'bytes',
                          'StringListValues': [
                              'string',
                          ],
                          'BinaryListValues': [
                              b'bytes',
                          ],
                          'DataType': 'string'
                      }
                  }
              },
          ]
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type Entries: list
    :param Entries: **[REQUIRED]** 

      A list of  SendMessageBatchRequestEntry items.

      

    
      - *(dict) --* 

        Contains the details of a single Amazon SQS message along with a ``Id`` . 

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          An identifier for the message in this batch. This is used to communicate the result. Note that the ``Id`` s of a batch request need to be unique within the request.

          

        
        - **MessageBody** *(string) --* **[REQUIRED]** 

          Body of the message.

          

        
        - **DelaySeconds** *(integer) --* 

          The number of seconds for which the message has to be delayed.

          

        
        - **MessageAttributes** *(dict) --* 

          Each message attribute consists of a Name, Type, and Value. For more information, see `Message Attribute Items`_ .

          

        
          - *(string) --* 

          
            - *(dict) --* 

              The user-specified message attribute value. For string data types, the value attribute has the same restrictions on the content as the message body. For more information, see `SendMessage`_ .

               

              Name, type, and value must not be empty or null. In addition, the message body should not be empty or null. All parts of the message attribute, including name, type, and value, are included in the message size restriction, which is currently 256 KB (262,144 bytes).

              

            
              - **StringValue** *(string) --* 

                Strings are Unicode with UTF8 binary encoding. For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ .

                

              
              - **BinaryValue** *(bytes) --* 

                Binary type attributes can store any binary data, for example, compressed data, encrypted data, or images.

                

              
              - **StringListValues** *(list) --* 

                Not implemented. Reserved for future use.

                

              
                - *(string) --* 

                
            
              - **BinaryListValues** *(list) --* 

                Not implemented. Reserved for future use.

                

              
                - *(bytes) --* 

                
            
              - **DataType** *(string) --* **[REQUIRED]** 

                Amazon SQS supports the following logical data types: String, Number, and Binary. For the Number data type, you must use StringValue.

                 

                You can also append custom labels. For more information, see `Message Attribute Data Types`_ .

                

              
            
      
    
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Successful': [
                {
                    'Id': 'string',
                    'MessageId': 'string',
                    'MD5OfMessageBody': 'string',
                    'MD5OfMessageAttributes': 'string'
                },
            ],
            'Failed': [
                {
                    'Id': 'string',
                    'SenderFault': True|False,
                    'Code': 'string',
                    'Message': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        For each message in the batch, the response contains a  SendMessageBatchResultEntry tag if the message succeeds or a  BatchResultErrorEntry tag if the message fails.

        
        

        - **Successful** *(list) --* 

          A list of  SendMessageBatchResultEntry items.

          
          

          - *(dict) --* 

            Encloses a message ID for successfully enqueued message of a  SendMessageBatch .

            
            

            - **Id** *(string) --* 

              An identifier for the message in this batch.

              
            

            - **MessageId** *(string) --* 

              An identifier for the message.

              
            

            - **MD5OfMessageBody** *(string) --* 

              An MD5 digest of the non-URL-encoded message body string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

              
            

            - **MD5OfMessageAttributes** *(string) --* 

              An MD5 digest of the non-URL-encoded message attribute string. This can be used to verify that Amazon SQS received the message batch correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

              
        
      
        

        - **Failed** *(list) --* 

          A list of  BatchResultErrorEntry items with the error detail about each message that could not be enqueued.

          
          

          - *(dict) --* 

            This is used in the responses of batch API to give a detailed description of the result of an action on each entry in the request.

            
            

            - **Id** *(string) --* 

              The id of an entry in a batch request.

              
            

            - **SenderFault** *(boolean) --* 

              Whether the error happened due to the sender's fault.

              
            

            - **Code** *(string) --* 

              An error code representing why the action failed on this entry.

              
            

            - **Message** *(string) --* 

              A message explaining why the action failed on this entry.

              
        
      
    

  .. py:method:: set_queue_attributes(**kwargs)

    

    Sets the value of one or more queue attributes. When you change a queue's attributes, the change can take up to 60 seconds for most of the attributes to propagate throughout the SQS system. Changes made to the ``MessageRetentionPeriod`` attribute can take up to 15 minutes.

     

    .. note::

      

      Going forward, new attributes might be added. If you are writing code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully.

      

    

    **Request Syntax** 
    ::

      response = client.set_queue_attributes(
          QueueUrl='string',
          Attributes={
              'string': 'string'
          }
      )
    :type QueueUrl: string
    :param QueueUrl: **[REQUIRED]** 

      The URL of the Amazon SQS queue to take action on.

       

      Queue URLs are case-sensitive.

      

    
    :type Attributes: dict
    :param Attributes: **[REQUIRED]** 

      A map of attributes to set.

       

      The following lists the names, descriptions, and values of the special request parameters the ``SetQueueAttributes`` action uses:

       

       
      * ``DelaySeconds`` - The time in seconds that the delivery of all messages in the queue will be delayed. An integer from 0 to 900 (15 minutes). The default for this attribute is 0 (zero).
       
      * ``MaximumMessageSize`` - The limit of how many bytes a message can contain before Amazon SQS rejects it. An integer from 1024 bytes (1 KiB) up to 262144 bytes (256 KiB). The default for this attribute is 262144 (256 KiB).
       
      * ``MessageRetentionPeriod`` - The number of seconds Amazon SQS retains a message. Integer representing seconds, from 60 (1 minute) to 1209600 (14 days). The default for this attribute is 345600 (4 days).
       
      * ``Policy`` - The queue's policy. A valid AWS policy. For more information about policy structure, see `Overview of AWS IAM Policies`_ in the *Amazon IAM User Guide* .
       
      * ``ReceiveMessageWaitTimeSeconds`` - The time for which a ReceiveMessage call will wait for a message to arrive. An integer from 0 to 20 (seconds). The default for this attribute is 0.
       
      * ``VisibilityTimeout`` - The visibility timeout for the queue. An integer from 0 to 43200 (12 hours). The default for this attribute is 30. For more information about visibility timeout, see Visibility Timeout in the *Amazon SQS Developer Guide* .
       
      * ``RedrivePolicy`` - The parameters for dead letter queue functionality of the source queue. For more information about RedrivePolicy and dead letter queues, see Using Amazon SQS Dead Letter Queues in the *Amazon SQS Developer Guide* .
       

       

      Any other valid special request parameters that are specified (such as ``ApproximateNumberOfMessages`` , ``ApproximateNumberOfMessagesDelayed`` , ``ApproximateNumberOfMessagesNotVisible`` , ``CreatedTimestamp`` , ``LastModifiedTimestamp`` , and ``QueueArn`` ) will be ignored.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :returns: None

================
Service Resource
================



.. py:class:: SQS.ServiceResource()

  A resource representing Amazon Simple Queue Service (SQS)::

    
    import boto3
    
    sqs = boto3.resource('sqs')

  
  These are the resource's available actions:
  
  *   :py:meth:`create_queue()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`get_queue_by_name()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Message()`

  
  *   :py:meth:`Queue()`

  
  These are the resource's available collections:
  
  *   :py:attr:`queues`

  
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: create_queue(**kwargs)

    

    Creates a new queue, or returns the URL of an existing one. When you request ``CreateQueue`` , you provide a name for the queue. To successfully create a new queue, you must provide a name that is unique within the scope of your own queues.

     

    .. note::

       

      If you delete a queue, you must wait at least 60 seconds before creating a queue with the same name.

       

     

    You may pass one or more attributes in the request. If you do not provide a value for any attribute, the queue will have the default value for that attribute.

     

    .. note::

      

      Use  GetQueueUrl to get a queue's URL.  GetQueueUrl requires only the ``QueueName`` parameter.

      

     

    If you provide the name of an existing queue, along with the exact names and values of all the queue's attributes, ``CreateQueue`` returns the queue URL for the existing queue. If the queue name, attribute names, or attribute values do not match an existing queue, ``CreateQueue`` returns an error.

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      queue = sqs.create_queue(
          QueueName='string',
          Attributes={
              'string': 'string'
          }
      )
    :type QueueName: string
    :param QueueName: **[REQUIRED]** 

      The name for the queue to be created.

       

      Queue names are case-sensitive.

      

    
    :type Attributes: dict
    :param Attributes: 

      A map of attributes with their corresponding values.

       

      The following lists the names, descriptions, and values of the special request parameters the ``CreateQueue`` action uses:

       

       
      * ``DelaySeconds`` - The time in seconds that the delivery of all messages in the queue will be delayed. An integer from 0 to 900 (15 minutes). The default for this attribute is 0 (zero).
       
      * ``MaximumMessageSize`` - The limit of how many bytes a message can contain before Amazon SQS rejects it. An integer from 1024 bytes (1 KiB) up to 262144 bytes (256 KiB). The default for this attribute is 262144 (256 KiB).
       
      * ``MessageRetentionPeriod`` - The number of seconds Amazon SQS retains a message. Integer representing seconds, from 60 (1 minute) to 1209600 (14 days). The default for this attribute is 345600 (4 days).
       
      * ``Policy`` - The queue's policy. A valid AWS policy. For more information about policy structure, see `Overview of AWS IAM Policies`_ in the *Amazon IAM User Guide* .
       
      * ``ReceiveMessageWaitTimeSeconds`` - The time for which a  ReceiveMessage call will wait for a message to arrive. An integer from 0 to 20 (seconds). The default for this attribute is 0.
       
      * ``RedrivePolicy`` - The parameters for dead letter queue functionality of the source queue. For more information about RedrivePolicy and dead letter queues, see `Using Amazon SQS Dead Letter Queues`_ in the *Amazon SQS Developer Guide* .
       
      * ``VisibilityTimeout`` - The visibility timeout for the queue. An integer from 0 to 43200 (12 hours). The default for this attribute is 30. For more information about visibility timeout, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* .
       

       

      Any other valid special request parameters that are specified (such as ``ApproximateNumberOfMessages`` , ``ApproximateNumberOfMessagesDelayed`` , ``ApproximateNumberOfMessagesNotVisible`` , ``CreatedTimestamp`` , ``LastModifiedTimestamp`` , and ``QueueArn`` ) will be ignored.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: :py:class:`sqs.Queue`
    :returns: Queue resource
    

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: get_queue_by_name(**kwargs)

    

    Returns the URL of an existing queue. This action provides a simple way to retrieve the URL of an Amazon SQS queue. 

     

    To access a queue that belongs to another AWS account, use the ``QueueOwnerAWSAccountId`` parameter to specify the account ID of the queue's owner. The queue's owner must grant you permission to access the queue. For more information about shared queue access, see  AddPermission or go to `Shared Queues`_ in the *Amazon SQS Developer Guide* . 

    

    **Request Syntax** 
    ::

      queue = sqs.get_queue_by_name(
          QueueName='string',
          QueueOwnerAWSAccountId='string'
      )
    :type QueueName: string
    :param QueueName: **[REQUIRED]** 

      The name of the queue whose URL must be fetched. Maximum 80 characters; alphanumeric characters, hyphens (-), and underscores (_) are allowed.

       

      Queue names are case-sensitive.

      

    
    :type QueueOwnerAWSAccountId: string
    :param QueueOwnerAWSAccountId: 

      The AWS account ID of the account that created the queue.

      

    
    
    :rtype: :py:class:`sqs.Queue`
    :returns: Queue resource
    
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Message(queue_url,receipt_handle)

    Creates a Message resource.::

      message = sqs.Message('queue_url','receipt_handle')

    :type queue_url: string
    :param queue_url: The Message's queue_url identifier. This **must** be set.
    :type receipt_handle: string
    :param receipt_handle: The Message's receipt_handle identifier. This **must** be set.
    
    :rtype: :py:class:`SQS.Message`
    :returns: A Message resource
    

  .. py:method:: Queue(url)

    Creates a Queue resource.::

      queue = sqs.Queue('url')

    :type url: string
    :param url: The Queue's url identifier. This **must** be set.
    
    :rtype: :py:class:`SQS.Queue`
    :returns: A Queue resource
    
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: queues

    A collection of Queue resources

    .. py:method:: all()

      Creates an iterable of all Queue resources in the collection.

      **Request Syntax** 
      ::

        queue_iterator = sqs.queues.all()
        
      
      :rtype: list(:py:class:`sqs.Queue`)
      :returns: A list of Queue resources
      

    .. py:method:: filter(**kwargs)

      Creates an iterable of all Queue resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        queue_iterator = sqs.queues.filter(
            QueueNamePrefix='string'
        )
      :type QueueNamePrefix: string
      :param QueueNamePrefix: 

        A string to use for filtering the list results. Only those queues whose name begins with the specified string are returned.

         

        Queue names are case-sensitive.

        

      
      
      :rtype: list(:py:class:`sqs.Queue`)
      :returns: A list of Queue resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Queue resources in the collection.

      **Request Syntax** 
      ::

        queue_iterator = sqs.queues.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`sqs.Queue`)
      :returns: A list of Queue resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Queue resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        queue_iterator = sqs.queues.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`sqs.Queue`)
      :returns: A list of Queue resources
      

=======
Message
=======



.. py:class:: SQS.Message(queue_url,receipt_handle)

  A resource representing an Amazon Simple Queue Service (SQS) Message::

    
    import boto3
    
    sqs = boto3.resource('sqs')
    message = sqs.Message('queue_url','receipt_handle')

  :type queue_url: string
  :param queue_url: The Message's queue_url identifier. This **must** be set.
  :type receipt_handle: string
  :param receipt_handle: The Message's receipt_handle identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`queue_url`

  
  *   :py:attr:`receipt_handle`

  
  These are the resource's available attributes:
  
  *   :py:attr:`attributes`

  
  *   :py:attr:`body`

  
  *   :py:attr:`md5_of_body`

  
  *   :py:attr:`md5_of_message_attributes`

  
  *   :py:attr:`message_attributes`

  
  *   :py:attr:`message_id`

  
  These are the resource's available actions:
  
  *   :py:meth:`change_visibility()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`get_available_subresources()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Queue()`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: queue_url

    *(string)* The Message's queue_url identifier. This **must** be set.

  .. py:attribute:: receipt_handle

    *(string)* The Message's receipt_handle identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: attributes

    

    - *(dict) --* 

      ``SenderId`` , ``SentTimestamp`` , ``ApproximateReceiveCount`` , and/or ``ApproximateFirstReceiveTimestamp`` . ``SentTimestamp`` and ``ApproximateFirstReceiveTimestamp`` are each returned as an integer representing the `epoch time`_ in milliseconds.

      
      

      - *(string) --* 
        

        - *(string) --* 
  


  .. py:attribute:: body

    

    - *(string) --* 

      The message's contents (not URL-encoded).

      

  .. py:attribute:: md5_of_body

    

    - *(string) --* 

      An MD5 digest of the non-URL-encoded message body string.

      

  .. py:attribute:: md5_of_message_attributes

    

    - *(string) --* 

      An MD5 digest of the non-URL-encoded message attribute string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

      

  .. py:attribute:: message_attributes

    

    - *(dict) --* 

      Each message attribute consists of a Name, Type, and Value. For more information, see `Message Attribute Items`_ .

      
      

      - *(string) --* 
        

        - *(dict) --* 

          The user-specified message attribute value. For string data types, the value attribute has the same restrictions on the content as the message body. For more information, see `SendMessage`_ .

           

          Name, type, and value must not be empty or null. In addition, the message body should not be empty or null. All parts of the message attribute, including name, type, and value, are included in the message size restriction, which is currently 256 KB (262,144 bytes).

          
          

          - **StringValue** *(string) --* 

            Strings are Unicode with UTF8 binary encoding. For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ .

            
          

          - **BinaryValue** *(bytes) --* 

            Binary type attributes can store any binary data, for example, compressed data, encrypted data, or images.

            
          

          - **StringListValues** *(list) --* 

            Not implemented. Reserved for future use.

            
            

            - *(string) --* 
        
          

          - **BinaryListValues** *(list) --* 

            Not implemented. Reserved for future use.

            
            

            - *(bytes) --* 
        
          

          - **DataType** *(string) --* 

            Amazon SQS supports the following logical data types: String, Number, and Binary. For the Number data type, you must use StringValue.

             

            You can also append custom labels. For more information, see `Message Attribute Data Types`_ .

            
      
  


  .. py:attribute:: message_id

    

    - *(string) --* 

      A unique identifier for the message. Message IDs are considered unique across all AWS accounts for an extended period of time.

      
  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: change_visibility(**kwargs)

    

    Changes the visibility timeout of a specified message in a queue to a new value. The maximum allowed timeout value you can set the value to is 12 hours. This means you can't extend the timeout of a message in an existing queue to more than a total visibility timeout of 12 hours. (For more information visibility timeout, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* .)

     

    For example, let's say you have a message and its default message visibility timeout is 5 minutes. After 3 minutes, you call ``ChangeMessageVisiblity`` with a timeout of 10 minutes. At that time, the timeout for the message would be extended by 10 minutes beyond the time of the ChangeMessageVisibility call. This results in a total visibility timeout of 13 minutes. You can continue to call ChangeMessageVisibility to extend the visibility timeout to a maximum of 12 hours. If you try to extend beyond 12 hours, the request will be rejected.

     

    .. note::

      

      There is a 120,000 limit for the number of inflight messages per queue. Messages are inflight after they have been received from the queue by a consuming component, but have not yet been deleted from the queue. If you reach the 120,000 limit, you will receive an OverLimit error message from Amazon SQS. To help avoid reaching the limit, you should delete the messages from the queue after they have been processed. You can also increase the number of queues you use to process the messages. 

      

     

    .. warning::

      

      If you attempt to set the ``VisibilityTimeout`` to an amount more than the maximum time left, Amazon SQS returns an error. It will not automatically recalculate and increase the timeout to the maximum time remaining.

      

     

    .. warning::

      

      Unlike with a queue, when you change the visibility timeout for a specific message, that timeout value is applied immediately but is not saved in memory for that message. If you don't delete a message after it is received, the visibility timeout for the message the next time it is received reverts to the original timeout value, not the value you set with the ``ChangeMessageVisibility`` action.

      

    

    **Request Syntax** 
    ::

      response = message.change_visibility(
          VisibilityTimeout=123
      )
    :type VisibilityTimeout: integer
    :param VisibilityTimeout: **[REQUIRED]** 

      The new value (in seconds - from 0 to 43200 - maximum 12 hours) for the message's visibility timeout.

      

    
    
    :returns: None

  .. py:method:: delete()

    

    Deletes the specified message from the specified queue. You specify the message by using the message's ``receipt handle`` and not the ``message ID`` you received when you sent the message. Even if the message is locked by another reader due to the visibility timeout setting, it is still deleted from the queue. If you leave a message in the queue for longer than the queue's configured retention period, Amazon SQS automatically deletes it. 

     

    .. note::

       

      The receipt handle is associated with a specific instance of receiving the message. If you receive a message more than once, the receipt handle you get each time you receive the message is different. When you request ``DeleteMessage`` , if you don't provide the most recently received receipt handle for the message, the request will still succeed, but the message might not be deleted. 

       

     

    .. warning::

       

      It is possible you will receive a message even after you have deleted it. This might happen on rare occasions if one of the servers storing a copy of the message is unavailable when you request to delete the message. The copy remains on the server and might be returned to you again on a subsequent receive request. You should create your system to be idempotent so that receiving a particular message more than once is not a problem. 

       

    

    **Request Syntax** 
    ::

      response = message.delete()
      
    
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
  

  .. py:method:: Queue()

    Creates a Queue resource.::

      queue = message.Queue()

    
    :rtype: :py:class:`SQS.Queue`
    :returns: A Queue resource
    

=====
Queue
=====



.. py:class:: SQS.Queue(url)

  A resource representing an Amazon Simple Queue Service (SQS) Queue::

    
    import boto3
    
    sqs = boto3.resource('sqs')
    queue = sqs.Queue('url')

  :type url: string
  :param url: The Queue's url identifier. This **must** be set.
  
  These are the resource's available identifiers:
  
  *   :py:attr:`url`

  
  These are the resource's available attributes:
  
  *   :py:attr:`attributes`

  
  These are the resource's available actions:
  
  *   :py:meth:`add_permission()`

  
  *   :py:meth:`change_message_visibility_batch()`

  
  *   :py:meth:`delete()`

  
  *   :py:meth:`delete_messages()`

  
  *   :py:meth:`get_available_subresources()`

  
  *   :py:meth:`load()`

  
  *   :py:meth:`purge()`

  
  *   :py:meth:`receive_messages()`

  
  *   :py:meth:`reload()`

  
  *   :py:meth:`remove_permission()`

  
  *   :py:meth:`send_message()`

  
  *   :py:meth:`send_messages()`

  
  *   :py:meth:`set_attributes()`

  
  These are the resource's available sub-resources:
  
  *   :py:meth:`Message()`

  
  These are the resource's available collections:
  
  *   :py:attr:`dead_letter_source_queues`

  
  .. rst-class:: admonition-title
  
  Identifiers
  
  Identifiers are properties of a resource that are set upon instantation of the resource.
  For more information about identifiers refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: url

    *(string)* The Queue's url identifier. This **must** be set.
  .. rst-class:: admonition-title
  
  Attributes
  
  Attributes provide access to the properties of a resource. Attributes are lazy-loaded the first time one is accessed via the :py:meth:`load` method.
  For more information about attributes refer to the :ref:`Resources Introduction Guide<identifiers_attributes_intro>`.
  

  .. py:attribute:: attributes

    

    - *(dict) --* 

      A map of attributes to the respective values.

      
      

      - *(string) --* 
        

        - *(string) --* 
  

  .. rst-class:: admonition-title
  
  Actions
  
  Actions call operations on resources.  They may automatically handle the passing in of arguments set from identifiers and some attributes.
  For more information about actions refer to the :ref:`Resources Introduction Guide<actions_intro>`.
  

  .. py:method:: add_permission(**kwargs)

    

    Adds a permission to a queue for a specific `principal`_ . This allows for sharing access to the queue.

     

    When you create a queue, you have full control access rights for the queue. Only you (as owner of the queue) can grant or deny permissions to the queue. For more information about these permissions, see `Shared Queues`_ in the *Amazon SQS Developer Guide* .

     

    .. note::

       

      ``AddPermission`` writes an Amazon SQS-generated policy. If you want to write your own policy, use  SetQueueAttributes to upload your policy. For more information about writing your own policy, see `Using The Access Policy Language`_ in the *Amazon SQS Developer Guide* .

       

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = queue.add_permission(
          Label='string',
          AWSAccountIds=[
              'string',
          ],
          Actions=[
              'string',
          ]
      )
    :type Label: string
    :param Label: **[REQUIRED]** 

      The unique identification of the permission you're setting (e.g., ``AliceSendMessage`` ). Constraints: Maximum 80 characters; alphanumeric characters, hyphens (-), and underscores (_) are allowed.

      

    
    :type AWSAccountIds: list
    :param AWSAccountIds: **[REQUIRED]** 

      The AWS account number of the `principal`_ who will be given permission. The principal must have an AWS account, but does not need to be signed up for Amazon SQS. For information about locating the AWS account identification, see `Your AWS Identifiers`_ in the *Amazon SQS Developer Guide* .

      

    
      - *(string) --* 

      
  
    :type Actions: list
    :param Actions: **[REQUIRED]** 

      The action the client wants to allow for the specified principal. The following are valid values: ``* | SendMessage | ReceiveMessage | DeleteMessage | ChangeMessageVisibility | GetQueueAttributes | GetQueueUrl`` . For more information about these actions, see `Understanding Permissions`_ in the *Amazon SQS Developer Guide* .

       

      Specifying ``SendMessage`` , ``DeleteMessage`` , or ``ChangeMessageVisibility`` for the ``ActionName.n`` also grants permissions for the corresponding batch versions of those actions: ``SendMessageBatch`` , ``DeleteMessageBatch`` , and ``ChangeMessageVisibilityBatch`` .

      

    
      - *(string) --* 

      
  
    
    :returns: None

  .. py:method:: change_message_visibility_batch(**kwargs)

    

    Changes the visibility timeout of multiple messages. This is a batch version of  ChangeMessageVisibility . The result of the action on each message is reported individually in the response. You can send up to 10  ChangeMessageVisibility requests with each ``ChangeMessageVisibilityBatch`` action.

     

    .. warning::

      

      Because the batch request can result in a combination of successful and unsuccessful actions, you should check for batch errors even when the call returns an HTTP status code of 200.

      

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = queue.change_message_visibility_batch(
          Entries=[
              {
                  'Id': 'string',
                  'ReceiptHandle': 'string',
                  'VisibilityTimeout': 123
              },
          ]
      )
    :type Entries: list
    :param Entries: **[REQUIRED]** 

      A list of receipt handles of the messages for which the visibility timeout must be changed.

      

    
      - *(dict) --* 

        Encloses a receipt handle and an entry id for each message in  ChangeMessageVisibilityBatch . 

         

        .. warning::

           

          All of the following parameters are list parameters that must be prefixed with ``ChangeMessageVisibilityBatchRequestEntry.n`` , where ``n`` is an integer value starting with 1. For example, a parameter list for this action might look like this:

           

         

        ```` 

         

        ```` 

         

        ```` 

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          An identifier for this particular receipt handle. This is used to communicate the result. Note that the ``Id`` s of a batch request need to be unique within the request.

          

        
        - **ReceiptHandle** *(string) --* **[REQUIRED]** 

          A receipt handle.

          

        
        - **VisibilityTimeout** *(integer) --* 

          The new value (in seconds) for the message's visibility timeout.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Successful': [
                {
                    'Id': 'string'
                },
            ],
            'Failed': [
                {
                    'Id': 'string',
                    'SenderFault': True|False,
                    'Code': 'string',
                    'Message': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        For each message in the batch, the response contains a  ChangeMessageVisibilityBatchResultEntry tag if the message succeeds or a  BatchResultErrorEntry tag if the message fails. 

        
        

        - **Successful** *(list) --* 

          A list of  ChangeMessageVisibilityBatchResultEntry items.

          
          

          - *(dict) --* 

            Encloses the id of an entry in  ChangeMessageVisibilityBatch .

            
            

            - **Id** *(string) --* 

              Represents a message whose visibility timeout has been changed successfully.

              
        
      
        

        - **Failed** *(list) --* 

          A list of  BatchResultErrorEntry items.

          
          

          - *(dict) --* 

            This is used in the responses of batch API to give a detailed description of the result of an action on each entry in the request.

            
            

            - **Id** *(string) --* 

              The id of an entry in a batch request.

              
            

            - **SenderFault** *(boolean) --* 

              Whether the error happened due to the sender's fault.

              
            

            - **Code** *(string) --* 

              An error code representing why the action failed on this entry.

              
            

            - **Message** *(string) --* 

              A message explaining why the action failed on this entry.

              
        
      
    

  .. py:method:: delete()

    

    Deletes the queue specified by the **queue URL** , regardless of whether the queue is empty. If the specified queue does not exist, Amazon SQS returns a successful response. 

     

    .. warning::

       

      Use ``DeleteQueue`` with care; once you delete your queue, any messages in the queue are no longer available. 

       

     

    When you delete a queue, the deletion process takes up to 60 seconds. Requests you send involving that queue during the 60 seconds might succeed. For example, a  SendMessage request might succeed, but after the 60 seconds, the queue and that message you sent no longer exist. Also, when you delete a queue, you must wait at least 60 seconds before creating a queue with the same name. 

     

    We reserve the right to delete queues that have had no activity for more than 30 days. For more information, see `How Amazon SQS Queues Work`_ in the *Amazon SQS Developer Guide* . 

    

    **Request Syntax** 
    ::

      response = queue.delete()
      
    
    :returns: None

  .. py:method:: delete_messages(**kwargs)

    

    Deletes up to ten messages from the specified queue. This is a batch version of  DeleteMessage . The result of the delete action on each message is reported individually in the response.

     

    .. warning::

       

      Because the batch request can result in a combination of successful and unsuccessful actions, you should check for batch errors even when the call returns an HTTP status code of 200. 

       

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = queue.delete_messages(
          Entries=[
              {
                  'Id': 'string',
                  'ReceiptHandle': 'string'
              },
          ]
      )
    :type Entries: list
    :param Entries: **[REQUIRED]** 

      A list of receipt handles for the messages to be deleted.

      

    
      - *(dict) --* 

        Encloses a receipt handle and an identifier for it.

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          An identifier for this particular receipt handle. This is used to communicate the result. Note that the ``Id`` s of a batch request need to be unique within the request.

          

        
        - **ReceiptHandle** *(string) --* **[REQUIRED]** 

          A receipt handle.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Successful': [
                {
                    'Id': 'string'
                },
            ],
            'Failed': [
                {
                    'Id': 'string',
                    'SenderFault': True|False,
                    'Code': 'string',
                    'Message': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        For each message in the batch, the response contains a  DeleteMessageBatchResultEntry tag if the message is deleted or a  BatchResultErrorEntry tag if the message cannot be deleted. 

        
        

        - **Successful** *(list) --* 

          A list of  DeleteMessageBatchResultEntry items.

          
          

          - *(dict) --* 

            Encloses the id an entry in  DeleteMessageBatch .

            
            

            - **Id** *(string) --* 

              Represents a successfully deleted message.

              
        
      
        

        - **Failed** *(list) --* 

          A list of  BatchResultErrorEntry items.

          
          

          - *(dict) --* 

            This is used in the responses of batch API to give a detailed description of the result of an action on each entry in the request.

            
            

            - **Id** *(string) --* 

              The id of an entry in a batch request.

              
            

            - **SenderFault** *(boolean) --* 

              Whether the error happened due to the sender's fault.

              
            

            - **Code** *(string) --* 

              An error code representing why the action failed on this entry.

              
            

            - **Message** *(string) --* 

              A message explaining why the action failed on this entry.

              
        
      
    

  .. py:method:: get_available_subresources()

        
    Returns a list of all the available sub-resources for this
    Resource.
    
    :returns: A list containing the name of each sub-resource for this
        resource
    :rtype: list of str


  .. py:method:: load()

    Calls :py:meth:`SQS.Client.get_queue_attributes` to update the attributes of the Queue resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      queue.load()
    :returns: None

  .. py:method:: purge()

    

    Deletes the messages in a queue specified by the **queue URL** .

     

    .. warning::

      

      When you use the ``PurgeQueue`` API, the deleted messages in the queue cannot be retrieved.

      

     

    When you purge a queue, the message deletion process takes up to 60 seconds. All messages sent to the queue before calling ``PurgeQueue`` will be deleted; messages sent to the queue while it is being purged may be deleted. While the queue is being purged, messages sent to the queue before ``PurgeQueue`` was called may be received, but will be deleted within the next minute.

    

    **Request Syntax** 
    ::

      response = queue.purge()
      
    
    :returns: None

  .. py:method:: receive_messages(**kwargs)

    

    Retrieves one or more messages, with a maximum limit of 10 messages, from the specified queue. Long poll support is enabled by using the ``WaitTimeSeconds`` parameter. For more information, see `Amazon SQS Long Poll`_ in the *Amazon SQS Developer Guide* . 

     

    Short poll is the default behavior where a weighted random set of machines is sampled on a ``ReceiveMessage`` call. This means only the messages on the sampled machines are returned. If the number of messages in the queue is small (less than 1000), it is likely you will get fewer messages than you requested per ``ReceiveMessage`` call. If the number of messages in the queue is extremely small, you might not receive any messages in a particular ``ReceiveMessage`` response; in which case you should repeat the request. 

     

    For each message returned, the response includes the following: 

     

     
    * Message body  
     
    * MD5 digest of the message body. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .  
     
    * Message ID you received when you sent the message to the queue.  
     
    * Receipt handle.  
     
    * Message attributes.  
     
    * MD5 digest of the message attributes.  
     

     

    The receipt handle is the identifier you must provide when deleting the message. For more information, see `Queue and Message Identifiers`_ in the *Amazon SQS Developer Guide* . 

     

    You can provide the ``VisibilityTimeout`` parameter in your request, which will be applied to the messages that Amazon SQS returns in the response. If you do not include the parameter, the overall visibility timeout for the queue is used for the returned messages. For more information, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* . 

     

    .. note::

       

      Going forward, new attributes might be added. If you are writing code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully. 

       

    

    **Request Syntax** 
    ::

      message = queue.receive_messages(
          AttributeNames=[
              'Policy'|'VisibilityTimeout'|'MaximumMessageSize'|'MessageRetentionPeriod'|'ApproximateNumberOfMessages'|'ApproximateNumberOfMessagesNotVisible'|'CreatedTimestamp'|'LastModifiedTimestamp'|'QueueArn'|'ApproximateNumberOfMessagesDelayed'|'DelaySeconds'|'ReceiveMessageWaitTimeSeconds'|'RedrivePolicy',
          ],
          MessageAttributeNames=[
              'string',
          ],
          MaxNumberOfMessages=123,
          VisibilityTimeout=123,
          WaitTimeSeconds=123
      )
    :type AttributeNames: list
    :param AttributeNames: 

      A list of attributes that need to be returned along with each message. These attributes include:

       

       
      * ``All`` - returns all values.
       
      * ``ApproximateFirstReceiveTimestamp`` - returns the time when the message was first received from the queue (epoch time in milliseconds).
       
      * ``ApproximateReceiveCount`` - returns the number of times a message has been received from the queue but not deleted.
       
      * ``SenderId`` - returns the AWS account number (or the IP address, if anonymous access is allowed) of the sender.
       
      * ``SentTimestamp`` - returns the time when the message was sent to the queue (epoch time in milliseconds).
       

       

      Any other valid special request parameters that are specified (such as ``ApproximateNumberOfMessages`` , ``ApproximateNumberOfMessagesDelayed`` , ``ApproximateNumberOfMessagesNotVisible`` , ``CreatedTimestamp`` , ``DelaySeconds`` , ``LastModifiedTimestamp`` , ``MaximumMessageSize`` , ``MessageRetentionPeriod`` , ``Policy`` , ``QueueArn`` , ``ReceiveMessageWaitTimeSeconds`` , ``RedrivePolicy`` , and ``VisibilityTimeout`` ) will be ignored.

      

    
      - *(string) --* 

      
  
    :type MessageAttributeNames: list
    :param MessageAttributeNames: 

      The name of the message attribute, where *N* is the index. The message attribute name can contain the following characters: A-Z, a-z, 0-9, underscore (_), hyphen (-), and period (.). The name must not start or end with a period, and it should not have successive periods. The name is case sensitive and must be unique among all attribute names for the message. The name can be up to 256 characters long. The name cannot start with "AWS." or "Amazon." (or any variations in casing), because these prefixes are reserved for use by Amazon Web Services.

       

      When using ``ReceiveMessage`` , you can send a list of attribute names to receive, or you can return all of the attributes by specifying "All" or ".*" in your request. You can also use "bar.*" to return all message attributes starting with the "bar" prefix.

      

    
      - *(string) --* 

      
  
    :type MaxNumberOfMessages: integer
    :param MaxNumberOfMessages: 

      The maximum number of messages to return. Amazon SQS never returns more messages than this value but may return fewer. Values can be from 1 to 10. Default is 1.

       

      All of the messages are not necessarily returned.

      

    
    :type VisibilityTimeout: integer
    :param VisibilityTimeout: 

      The duration (in seconds) that the received messages are hidden from subsequent retrieve requests after being retrieved by a ``ReceiveMessage`` request.

      

    
    :type WaitTimeSeconds: integer
    :param WaitTimeSeconds: 

      The duration (in seconds) for which the call will wait for a message to arrive in the queue before returning. If a message is available, the call will return sooner than WaitTimeSeconds.

      

    
    
    :rtype: list(:py:class:`sqs.Message`)
    :returns: A list of Message resources
    

  .. py:method:: reload()

    Calls :py:meth:`SQS.Client.get_queue_attributes` to update the attributes of the Queue resource. Note that the load and reload methods are the same method and can be used interchangeably.

    **Request Syntax** 

    ::

      queue.reload()
    :returns: None

  .. py:method:: remove_permission(**kwargs)

    

    Revokes any permissions in the queue policy that matches the specified ``Label`` parameter. Only the owner of the queue can remove permissions.

    

    **Request Syntax** 
    ::

      response = queue.remove_permission(
          Label='string'
      )
    :type Label: string
    :param Label: **[REQUIRED]** 

      The identification of the permission to remove. This is the label added with the  AddPermission action.

      

    
    
    :returns: None

  .. py:method:: send_message(**kwargs)

    

    Delivers a message to the specified queue. With Amazon SQS, you now have the ability to send large payload messages that are up to 256KB (262,144 bytes) in size. To send large payloads, you must use an AWS SDK that supports SigV4 signing. To verify whether SigV4 is supported for an AWS SDK, check the SDK release notes. 

     

    .. warning::

       

      The following list shows the characters (in Unicode) allowed in your message, according to the W3C XML specification. For more information, go to `http\://www.w3.org/TR/REC-xml/#charsets`_ If you send any characters not included in the list, your request will be rejected. 

       

      #x9 | #xA | #xD | [#x20 to #xD7FF] | [#xE000 to #xFFFD] | [#x10000 to #x10FFFF] 

       

    

    **Request Syntax** 
    ::

      response = queue.send_message(
          MessageBody='string',
          DelaySeconds=123,
          MessageAttributes={
              'string': {
                  'StringValue': 'string',
                  'BinaryValue': b'bytes',
                  'StringListValues': [
                      'string',
                  ],
                  'BinaryListValues': [
                      b'bytes',
                  ],
                  'DataType': 'string'
              }
          }
      )
    :type MessageBody: string
    :param MessageBody: **[REQUIRED]** 

      The message to send. String maximum 256 KB in size. For a list of allowed characters, see the preceding important note.

      

    
    :type DelaySeconds: integer
    :param DelaySeconds: 

      The number of seconds (0 to 900 - 15 minutes) to delay a specific message. Messages with a positive ``DelaySeconds`` value become available for processing after the delay time is finished. If you don't specify a value, the default value for the queue applies. 

      

    
    :type MessageAttributes: dict
    :param MessageAttributes: 

      Each message attribute consists of a Name, Type, and Value. For more information, see `Message Attribute Items`_ .

      

    
      - *(string) --* 

      
        - *(dict) --* 

          The user-specified message attribute value. For string data types, the value attribute has the same restrictions on the content as the message body. For more information, see `SendMessage`_ .

           

          Name, type, and value must not be empty or null. In addition, the message body should not be empty or null. All parts of the message attribute, including name, type, and value, are included in the message size restriction, which is currently 256 KB (262,144 bytes).

          

        
          - **StringValue** *(string) --* 

            Strings are Unicode with UTF8 binary encoding. For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ .

            

          
          - **BinaryValue** *(bytes) --* 

            Binary type attributes can store any binary data, for example, compressed data, encrypted data, or images.

            

          
          - **StringListValues** *(list) --* 

            Not implemented. Reserved for future use.

            

          
            - *(string) --* 

            
        
          - **BinaryListValues** *(list) --* 

            Not implemented. Reserved for future use.

            

          
            - *(bytes) --* 

            
        
          - **DataType** *(string) --* **[REQUIRED]** 

            Amazon SQS supports the following logical data types: String, Number, and Binary. For the Number data type, you must use StringValue.

             

            You can also append custom labels. For more information, see `Message Attribute Data Types`_ .

            

          
        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MD5OfMessageBody': 'string',
            'MD5OfMessageAttributes': 'string',
            'MessageId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The MD5OfMessageBody and MessageId elements.

        
        

        - **MD5OfMessageBody** *(string) --* 

          An MD5 digest of the non-URL-encoded message body string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

          
        

        - **MD5OfMessageAttributes** *(string) --* 

          An MD5 digest of the non-URL-encoded message attribute string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

          
        

        - **MessageId** *(string) --* 

          An element containing the message ID of the message sent to the queue. For more information, see `Queue and Message Identifiers`_ in the *Amazon SQS Developer Guide* . 

          
    

  .. py:method:: send_messages(**kwargs)

    

    Delivers up to ten messages to the specified queue. This is a batch version of  SendMessage . The result of the send action on each message is reported individually in the response. The maximum allowed individual message size is 256 KB (262,144 bytes).

     

    The maximum total payload size (i.e., the sum of all a batch's individual message lengths) is also 256 KB (262,144 bytes).

     

    If the ``DelaySeconds`` parameter is not specified for an entry, the default for the queue is used.

     

    .. warning::

      

      The following list shows the characters (in Unicode) that are allowed in your message, according to the W3C XML specification. For more information, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ . If you send any characters that are not included in the list, your request will be rejected.

       

      #x9 | #xA | #xD | [#x20 to #xD7FF] | [#xE000 to #xFFFD] | [#x10000 to #x10FFFF]

       

     

    .. warning::

       

      Because the batch request can result in a combination of successful and unsuccessful actions, you should check for batch errors even when the call returns an HTTP status code of 200.

       

     

    .. note::

      

      Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this: 

       

     

    ```` 

     

    ```` 

    

    **Request Syntax** 
    ::

      response = queue.send_messages(
          Entries=[
              {
                  'Id': 'string',
                  'MessageBody': 'string',
                  'DelaySeconds': 123,
                  'MessageAttributes': {
                      'string': {
                          'StringValue': 'string',
                          'BinaryValue': b'bytes',
                          'StringListValues': [
                              'string',
                          ],
                          'BinaryListValues': [
                              b'bytes',
                          ],
                          'DataType': 'string'
                      }
                  }
              },
          ]
      )
    :type Entries: list
    :param Entries: **[REQUIRED]** 

      A list of  SendMessageBatchRequestEntry items.

      

    
      - *(dict) --* 

        Contains the details of a single Amazon SQS message along with a ``Id`` . 

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          An identifier for the message in this batch. This is used to communicate the result. Note that the ``Id`` s of a batch request need to be unique within the request.

          

        
        - **MessageBody** *(string) --* **[REQUIRED]** 

          Body of the message.

          

        
        - **DelaySeconds** *(integer) --* 

          The number of seconds for which the message has to be delayed.

          

        
        - **MessageAttributes** *(dict) --* 

          Each message attribute consists of a Name, Type, and Value. For more information, see `Message Attribute Items`_ .

          

        
          - *(string) --* 

          
            - *(dict) --* 

              The user-specified message attribute value. For string data types, the value attribute has the same restrictions on the content as the message body. For more information, see `SendMessage`_ .

               

              Name, type, and value must not be empty or null. In addition, the message body should not be empty or null. All parts of the message attribute, including name, type, and value, are included in the message size restriction, which is currently 256 KB (262,144 bytes).

              

            
              - **StringValue** *(string) --* 

                Strings are Unicode with UTF8 binary encoding. For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ .

                

              
              - **BinaryValue** *(bytes) --* 

                Binary type attributes can store any binary data, for example, compressed data, encrypted data, or images.

                

              
              - **StringListValues** *(list) --* 

                Not implemented. Reserved for future use.

                

              
                - *(string) --* 

                
            
              - **BinaryListValues** *(list) --* 

                Not implemented. Reserved for future use.

                

              
                - *(bytes) --* 

                
            
              - **DataType** *(string) --* **[REQUIRED]** 

                Amazon SQS supports the following logical data types: String, Number, and Binary. For the Number data type, you must use StringValue.

                 

                You can also append custom labels. For more information, see `Message Attribute Data Types`_ .

                

              
            
      
    
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Successful': [
                {
                    'Id': 'string',
                    'MessageId': 'string',
                    'MD5OfMessageBody': 'string',
                    'MD5OfMessageAttributes': 'string'
                },
            ],
            'Failed': [
                {
                    'Id': 'string',
                    'SenderFault': True|False,
                    'Code': 'string',
                    'Message': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        For each message in the batch, the response contains a  SendMessageBatchResultEntry tag if the message succeeds or a  BatchResultErrorEntry tag if the message fails.

        
        

        - **Successful** *(list) --* 

          A list of  SendMessageBatchResultEntry items.

          
          

          - *(dict) --* 

            Encloses a message ID for successfully enqueued message of a  SendMessageBatch .

            
            

            - **Id** *(string) --* 

              An identifier for the message in this batch.

              
            

            - **MessageId** *(string) --* 

              An identifier for the message.

              
            

            - **MD5OfMessageBody** *(string) --* 

              An MD5 digest of the non-URL-encoded message body string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

              
            

            - **MD5OfMessageAttributes** *(string) --* 

              An MD5 digest of the non-URL-encoded message attribute string. This can be used to verify that Amazon SQS received the message batch correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

              
        
      
        

        - **Failed** *(list) --* 

          A list of  BatchResultErrorEntry items with the error detail about each message that could not be enqueued.

          
          

          - *(dict) --* 

            This is used in the responses of batch API to give a detailed description of the result of an action on each entry in the request.

            
            

            - **Id** *(string) --* 

              The id of an entry in a batch request.

              
            

            - **SenderFault** *(boolean) --* 

              Whether the error happened due to the sender's fault.

              
            

            - **Code** *(string) --* 

              An error code representing why the action failed on this entry.

              
            

            - **Message** *(string) --* 

              A message explaining why the action failed on this entry.

              
        
      
    

  .. py:method:: set_attributes(**kwargs)

    

    Sets the value of one or more queue attributes. When you change a queue's attributes, the change can take up to 60 seconds for most of the attributes to propagate throughout the SQS system. Changes made to the ``MessageRetentionPeriod`` attribute can take up to 15 minutes.

     

    .. note::

      

      Going forward, new attributes might be added. If you are writing code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully.

      

    

    **Request Syntax** 
    ::

      response = queue.set_attributes(
          Attributes={
              'string': 'string'
          }
      )
    :type Attributes: dict
    :param Attributes: **[REQUIRED]** 

      A map of attributes to set.

       

      The following lists the names, descriptions, and values of the special request parameters the ``SetQueueAttributes`` action uses:

       

       
      * ``DelaySeconds`` - The time in seconds that the delivery of all messages in the queue will be delayed. An integer from 0 to 900 (15 minutes). The default for this attribute is 0 (zero).
       
      * ``MaximumMessageSize`` - The limit of how many bytes a message can contain before Amazon SQS rejects it. An integer from 1024 bytes (1 KiB) up to 262144 bytes (256 KiB). The default for this attribute is 262144 (256 KiB).
       
      * ``MessageRetentionPeriod`` - The number of seconds Amazon SQS retains a message. Integer representing seconds, from 60 (1 minute) to 1209600 (14 days). The default for this attribute is 345600 (4 days).
       
      * ``Policy`` - The queue's policy. A valid AWS policy. For more information about policy structure, see `Overview of AWS IAM Policies`_ in the *Amazon IAM User Guide* .
       
      * ``ReceiveMessageWaitTimeSeconds`` - The time for which a ReceiveMessage call will wait for a message to arrive. An integer from 0 to 20 (seconds). The default for this attribute is 0.
       
      * ``VisibilityTimeout`` - The visibility timeout for the queue. An integer from 0 to 43200 (12 hours). The default for this attribute is 30. For more information about visibility timeout, see Visibility Timeout in the *Amazon SQS Developer Guide* .
       
      * ``RedrivePolicy`` - The parameters for dead letter queue functionality of the source queue. For more information about RedrivePolicy and dead letter queues, see Using Amazon SQS Dead Letter Queues in the *Amazon SQS Developer Guide* .
       

       

      Any other valid special request parameters that are specified (such as ``ApproximateNumberOfMessages`` , ``ApproximateNumberOfMessagesDelayed`` , ``ApproximateNumberOfMessagesNotVisible`` , ``CreatedTimestamp`` , ``LastModifiedTimestamp`` , and ``QueueArn`` ) will be ignored.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :returns: None
  .. rst-class:: admonition-title
  
  Sub-resources
  
  Sub-resources are methods that create a new instance of a child resource. This resource's identifiers get passed along to the child.
  For more information about sub-resources refer to the :ref:`Resources Introduction Guide<subresources_intro>`.
  

  .. py:method:: Message(receipt_handle)

    Creates a Message resource.::

      message = queue.Message('receipt_handle')

    :type receipt_handle: string
    :param receipt_handle: The Message's receipt_handle identifier. This **must** be set.
    
    :rtype: :py:class:`SQS.Message`
    :returns: A Message resource
    
  .. rst-class:: admonition-title
  
  Collections
  
  Collections provide an interface to iterate over and manipulate groups of resources. 
  For more information about collections refer to the :ref:`Resources Introduction Guide<guide_collections>`.
  

  .. py:attribute:: dead_letter_source_queues

    A collection of Queue resources

    .. py:method:: all()

      Creates an iterable of all Queue resources in the collection.

      **Request Syntax** 
      ::

        queue_iterator = queue.dead_letter_source_queues.all()
        
      
      :rtype: list(:py:class:`sqs.Queue`)
      :returns: A list of Queue resources
      

    .. py:method:: filter()

      Creates an iterable of all Queue resources in the collection filtered by kwargs passed to method.

      **Request Syntax** 
      ::

        queue_iterator = queue.dead_letter_source_queues.filter()
        
      
      :rtype: list(:py:class:`sqs.Queue`)
      :returns: A list of Queue resources
      

    .. py:method:: limit(**kwargs)

      Creates an iterable up to a specified amount of Queue resources in the collection.

      **Request Syntax** 
      ::

        queue_iterator = queue.dead_letter_source_queues.limit(
            count=123
        )
      :type count: integer
      :param count: The limit to the number of resources in the iterable.

      
      
      :rtype: list(:py:class:`sqs.Queue`)
      :returns: A list of Queue resources
      

    .. py:method:: page_size(**kwargs)

      Creates an iterable of all Queue resources in the collection, but limits the number of items returned by each service call by the specified amount.

      **Request Syntax** 
      ::

        queue_iterator = queue.dead_letter_source_queues.page_size(
            count=123
        )
      :type count: integer
      :param count: The number of items returned by each service call

      
      
      :rtype: list(:py:class:`sqs.Queue`)
      :returns: A list of Queue resources
      