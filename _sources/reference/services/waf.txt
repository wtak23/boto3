

.. _AWS WAF Developer Guide: http://docs.aws.amazon.com/waf/latest/developerguide/
.. _Classless Inter-Domain Routing: https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing
.. _ISO 3166-1 alpha-2: https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2


***
WAF
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: WAF.Client

  A low-level client representing AWS WAF::

    
    import boto3
    
    client = boto3.client('waf')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_byte_match_set`

  
  *   :py:meth:`create_ip_set`

  
  *   :py:meth:`create_rule`

  
  *   :py:meth:`create_size_constraint_set`

  
  *   :py:meth:`create_sql_injection_match_set`

  
  *   :py:meth:`create_web_acl`

  
  *   :py:meth:`create_xss_match_set`

  
  *   :py:meth:`delete_byte_match_set`

  
  *   :py:meth:`delete_ip_set`

  
  *   :py:meth:`delete_rule`

  
  *   :py:meth:`delete_size_constraint_set`

  
  *   :py:meth:`delete_sql_injection_match_set`

  
  *   :py:meth:`delete_web_acl`

  
  *   :py:meth:`delete_xss_match_set`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_byte_match_set`

  
  *   :py:meth:`get_change_token`

  
  *   :py:meth:`get_change_token_status`

  
  *   :py:meth:`get_ip_set`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_rule`

  
  *   :py:meth:`get_sampled_requests`

  
  *   :py:meth:`get_size_constraint_set`

  
  *   :py:meth:`get_sql_injection_match_set`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`get_web_acl`

  
  *   :py:meth:`get_xss_match_set`

  
  *   :py:meth:`list_byte_match_sets`

  
  *   :py:meth:`list_ip_sets`

  
  *   :py:meth:`list_rules`

  
  *   :py:meth:`list_size_constraint_sets`

  
  *   :py:meth:`list_sql_injection_match_sets`

  
  *   :py:meth:`list_web_acls`

  
  *   :py:meth:`list_xss_match_sets`

  
  *   :py:meth:`update_byte_match_set`

  
  *   :py:meth:`update_ip_set`

  
  *   :py:meth:`update_rule`

  
  *   :py:meth:`update_size_constraint_set`

  
  *   :py:meth:`update_sql_injection_match_set`

  
  *   :py:meth:`update_web_acl`

  
  *   :py:meth:`update_xss_match_set`

  

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


  .. py:method:: create_byte_match_set(**kwargs)

    

    Creates a ``ByteMatchSet`` . You then use  UpdateByteMatchSet to identify the part of a web request that you want AWS WAF to inspect, such as the values of the ``User-Agent`` header or the query string. For example, you can create a ``ByteMatchSet`` that matches any requests with ``User-Agent`` headers that contain the string ``BadBot`` . You can then configure AWS WAF to reject those requests.

     

    To create and configure a ``ByteMatchSet`` , perform the following steps:

     

     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``CreateByteMatchSet`` request.
     
    * Submit a ``CreateByteMatchSet`` request.
     
    * Use ``GetChangeToken`` to get the change token that you provide in the ``ChangeToken`` parameter of an ``UpdateByteMatchSet`` request.
     
    * Submit an  UpdateByteMatchSet request to specify the part of the request that you want AWS WAF to inspect (for example, the header or the URI) and the value that you want AWS WAF to watch for.
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.create_byte_match_set(
          Name='string',
          ChangeToken='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      A friendly name or description of the  ByteMatchSet . You can't change ``Name`` after you create a ``ByteMatchSet`` .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ByteMatchSet': {
                'ByteMatchSetId': 'string',
                'Name': 'string',
                'ByteMatchTuples': [
                    {
                        'FieldToMatch': {
                            'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                            'Data': 'string'
                        },
                        'TargetString': b'bytes',
                        'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE',
                        'PositionalConstraint': 'EXACTLY'|'STARTS_WITH'|'ENDS_WITH'|'CONTAINS'|'CONTAINS_WORD'
                    },
                ]
            },
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ByteMatchSet** *(dict) --* 

          A  ByteMatchSet that contains no ``ByteMatchTuple`` objects.

          
          

          - **ByteMatchSetId** *(string) --* 

            The ``ByteMatchSetId`` for a ``ByteMatchSet`` . You use ``ByteMatchSetId`` to get information about a ``ByteMatchSet`` (see  GetByteMatchSet ), update a ``ByteMatchSet`` (see  UpdateByteMatchSet ), insert a ``ByteMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete a ``ByteMatchSet`` from AWS WAF (see  DeleteByteMatchSet ).

             

            ``ByteMatchSetId`` is returned by  CreateByteMatchSet and by  ListByteMatchSets .

            
          

          - **Name** *(string) --* 

            A friendly name or description of the  ByteMatchSet . You can't change ``Name`` after you create a ``ByteMatchSet`` .

            
          

          - **ByteMatchTuples** *(list) --* 

            Specifies the bytes (typically a string that corresponds with ASCII characters) that you want AWS WAF to search for in web requests, the location in requests that you want AWS WAF to search, and other settings.

            
            

            - *(dict) --* 

              The bytes (typically a string that corresponds with ASCII characters) that you want AWS WAF to search for in web requests, the location in requests that you want AWS WAF to search, and other settings.

              
              

              - **FieldToMatch** *(dict) --* 

                The part of a web request that you want AWS WAF to search, such as a specified header or a query string. For more information, see  FieldToMatch .

                
                

                - **Type** *(string) --* 

                  The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

                   

                   
                  * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
                   
                  * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                   
                  * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
                   
                  * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                   
                  * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                   

                  
                

                - **Data** *(string) --* 

                  When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

                   

                  The name of the header is not case sensitive.

                  
            
              

              - **TargetString** *(bytes) --* 

                The value that you want AWS WAF to search for. AWS WAF searches for the specified string in the part of web requests that you specified in ``FieldToMatch`` . The maximum length of the value is 50 bytes.

                 

                Valid values depend on the values that you specified for ``FieldToMatch`` :

                 

                 
                * ``HEADER`` : The value that you want AWS WAF to search for in the request header that you specified in  FieldToMatch , for example, the value of the ``User-Agent`` or ``Referer`` header.
                 
                * ``METHOD`` : The HTTP method, which indicates the type of operation specified in the request. CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                 
                * ``QUERY_STRING`` : The value that you want AWS WAF to search for in the query string, which is the part of a URL that appears after a ``?`` character.
                 
                * ``URI`` : The value that you want AWS WAF to search for in the part of a URL that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                 
                * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                 

                 

                If ``TargetString`` includes alphabetic characters A-Z and a-z, note that the value is case sensitive.

                 

                **If you're using the AWS WAF API** 

                 

                Specify a base64-encoded version of the value. The maximum length of the value before you base64-encode it is 50 bytes. 

                 

                For example, suppose the value of ``Type`` is ``HEADER`` and the value of ``Data`` is ``User-Agent`` . If you want to search the ``User-Agent`` header for the value ``BadBot`` , you base64-encode ``BadBot`` using MIME base64 encoding and include the resulting value, ``QmFkQm90`` , in the value of ``TargetString`` .

                 

                **If you're using the AWS CLI or one of the AWS SDKs** 

                 

                The value that you want AWS WAF to search for. The SDK automatically base64 encodes the value.

                
              

              - **TextTransformation** *(string) --* 

                Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``TargetString`` before inspecting a request for a match.

                 

                **CMD_LINE** 

                 

                When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

                 

                 
                * Delete the following characters: \ " ' ^
                 
                * Delete spaces before the following characters: / (
                 
                * Replace the following characters with a space: , ;
                 
                * Replace multiple spaces with one space
                 
                * Convert uppercase letters (A-Z) to lowercase (a-z)
                 

                 

                **COMPRESS_WHITE_SPACE** 

                 

                Use this option to replace the following characters with a space character (decimal 32):

                 

                 
                * \f, formfeed, decimal 12
                 
                * \t, tab, decimal 9
                 
                * \n, newline, decimal 10
                 
                * \r, carriage return, decimal 13
                 
                * \v, vertical tab, decimal 11
                 
                * non-breaking space, decimal 160
                 

                 

                ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

                 

                **HTML_ENTITY_DECODE** 

                 

                Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

                 

                 
                * Replaces ``(ampersand)quot;`` with ``"`` 
                 
                * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
                 
                * Replaces ``(ampersand)lt;`` with a "less than" symbol
                 
                * Replaces ``(ampersand)gt;`` with ``>`` 
                 
                * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
                 
                * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
                 

                 

                **LOWERCASE** 

                 

                Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

                 

                **URL_DECODE** 

                 

                Use this option to decode a URL-encoded value.

                 

                **NONE** 

                 

                Specify ``NONE`` if you don't want to perform any text transformations.

                
              

              - **PositionalConstraint** *(string) --* 

                Within the portion of a web request that you want to search (for example, in the query string, if any), specify where you want AWS WAF to search. Valid values include the following:

                 

                **CONTAINS** 

                 

                The specified part of the web request must include the value of ``TargetString`` , but the location doesn't matter.

                 

                **CONTAINS_WORD** 

                 

                The specified part of the web request must include the value of ``TargetString`` , and ``TargetString`` must contain only alphanumeric characters or underscore (A-Z, a-z, 0-9, or _). In addition, ``TargetString`` must be a word, which means one of the following:

                 

                 
                * ``TargetString`` exactly matches the value of the specified part of the web request, such as the value of a header.
                 
                * ``TargetString`` is at the beginning of the specified part of the web request and is followed by a character other than an alphanumeric character or underscore (_), for example, ``BadBot;`` .
                 
                * ``TargetString`` is at the end of the specified part of the web request and is preceded by a character other than an alphanumeric character or underscore (_), for example, ``;BadBot`` .
                 
                * ``TargetString`` is in the middle of the specified part of the web request and is preceded and followed by characters other than alphanumeric characters or underscore (_), for example, ``-BadBot;`` .
                 

                 

                **EXACTLY** 

                 

                The value of the specified part of the web request must exactly match the value of ``TargetString`` .

                 

                **STARTS_WITH** 

                 

                The value of ``TargetString`` must appear at the beginning of the specified part of the web request.

                 

                **ENDS_WITH** 

                 

                The value of ``TargetString`` must appear at the end of the specified part of the web request.

                
          
        
      
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``CreateByteMatchSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: create_ip_set(**kwargs)

    

    Creates an  IPSet , which you use to specify which web requests you want to allow or block based on the IP addresses that the requests originate from. For example, if you're receiving a lot of requests from one or more individual IP addresses or one or more ranges of IP addresses and you want to block the requests, you can create an ``IPSet`` that contains those IP addresses and then configure AWS WAF to block the requests. 

     

    To create and configure an ``IPSet`` , perform the following steps:

     

     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``CreateIPSet`` request.
     
    * Submit a ``CreateIPSet`` request.
     
    * Use ``GetChangeToken`` to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateIPSet request.
     
    * Submit an ``UpdateIPSet`` request to specify the IP addresses that you want AWS WAF to watch for.
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.create_ip_set(
          Name='string',
          ChangeToken='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      A friendly name or description of the  IPSet . You can't change ``Name`` after you create the ``IPSet`` .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'IPSet': {
                'IPSetId': 'string',
                'Name': 'string',
                'IPSetDescriptors': [
                    {
                        'Type': 'IPV4',
                        'Value': 'string'
                    },
                ]
            },
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **IPSet** *(dict) --* 

          The  IPSet returned in the ``CreateIPSet`` response.

          
          

          - **IPSetId** *(string) --* 

            The ``IPSetId`` for an ``IPSet`` . You use ``IPSetId`` to get information about an ``IPSet`` (see  GetIPSet ), update an ``IPSet`` (see  UpdateIPSet ), insert an ``IPSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete an ``IPSet`` from AWS WAF (see  DeleteIPSet ).

             

            ``IPSetId`` is returned by  CreateIPSet and by  ListIPSets .

            
          

          - **Name** *(string) --* 

            A friendly name or description of the  IPSet . You can't change the name of an ``IPSet`` after you create it.

            
          

          - **IPSetDescriptors** *(list) --* 

            The IP address type (``IPV4`` ) and the IP address range (in CIDR notation) that web requests originate from. If the ``WebACL`` is associated with a CloudFront distribution, this is the value of one of the following fields in CloudFront access logs:

             

             
            * ``c-ip`` , if the viewer did not use an HTTP proxy or a load balancer to send the request
             
            * ``x-forwarded-for`` , if the viewer did use an HTTP proxy or a load balancer to send the request
             

            
            

            - *(dict) --* 

              Specifies the IP address type (``IPV4`` ) and the IP address range (in CIDR format) that web requests originate from.

              
              

              - **Type** *(string) --* 

                Specify ``IPV4`` .

                
              

              - **Value** *(string) --* 

                Specify an IPv4 address by using CIDR notation. For example:

                 

                 
                * To configure AWS WAF to allow, block, or count requests that originated from the IP address 192.0.2.44, specify ``192.0.2.44/32`` .
                 
                * To configure AWS WAF to allow, block, or count requests that originated from IP addresses from 192.0.2.0 to 192.0.2.255, specify ``192.0.2.0/24`` .
                 

                 

                AWS WAF supports only /8, /16, /24, and /32 IP addresses.

                 

                For more information about CIDR notation, see the Wikipedia entry `Classless Inter-Domain Routing`_ .

                
          
        
      
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``CreateIPSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: create_rule(**kwargs)

    

    Creates a ``Rule`` , which contains the ``IPSet`` objects, ``ByteMatchSet`` objects, and other predicates that identify the requests that you want to block. If you add more than one predicate to a ``Rule`` , a request must match all of the specifications to be allowed or blocked. For example, suppose you add the following to a ``Rule`` :

     

     
    * An ``IPSet`` that matches the IP address ``192.0.2.44/32`` 
     
    * A ``ByteMatchSet`` that matches ``BadBot`` in the ``User-Agent`` header
     

     

    You then add the ``Rule`` to a ``WebACL`` and specify that you want to blocks requests that satisfy the ``Rule`` . For a request to be blocked, it must come from the IP address 192.0.2.44 *and* the ``User-Agent`` header in the request must contain the value ``BadBot`` .

     

    To create and configure a ``Rule`` , perform the following steps:

     

     
    * Create and update the predicates that you want to include in the ``Rule`` . For more information, see  CreateByteMatchSet ,  CreateIPSet , and  CreateSqlInjectionMatchSet .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``CreateRule`` request.
     
    * Submit a ``CreateRule`` request.
     
    * Use ``GetChangeToken`` to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateRule request.
     
    * Submit an ``UpdateRule`` request to specify the predicates that you want to include in the ``Rule`` .
     
    * Create and update a ``WebACL`` that contains the ``Rule`` . For more information, see  CreateWebACL .
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.create_rule(
          Name='string',
          MetricName='string',
          ChangeToken='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      A friendly name or description of the  Rule . You can't change the name of a ``Rule`` after you create it.

      

    
    :type MetricName: string
    :param MetricName: **[REQUIRED]** 

      A friendly name or description for the metrics for this ``Rule`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change the name of the metric after you create the ``Rule`` .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Rule': {
                'RuleId': 'string',
                'Name': 'string',
                'MetricName': 'string',
                'Predicates': [
                    {
                        'Negated': True|False,
                        'Type': 'IPMatch'|'ByteMatch'|'SqlInjectionMatch'|'SizeConstraint'|'XssMatch',
                        'DataId': 'string'
                    },
                ]
            },
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Rule** *(dict) --* 

          The  Rule returned in the ``CreateRule`` response.

          
          

          - **RuleId** *(string) --* 

            A unique identifier for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  GetRule ), update a ``Rule`` (see  UpdateRule ), insert a ``Rule`` into a ``WebACL`` or delete a one from a ``WebACL`` (see  UpdateWebACL ), or delete a ``Rule`` from AWS WAF (see  DeleteRule ).

             

            ``RuleId`` is returned by  CreateRule and by  ListRules .

            
          

          - **Name** *(string) --* 

            The friendly name or description for the ``Rule`` . You can't change the name of a ``Rule`` after you create it.

            
          

          - **MetricName** *(string) --* 
          

          - **Predicates** *(list) --* 

            The ``Predicates`` object contains one ``Predicate`` element for each  ByteMatchSet ,  IPSet , or  SqlInjectionMatchSet object that you want to include in a ``Rule`` .

            
            

            - *(dict) --* 

              Specifies the  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , and  SizeConstraintSet objects that you want to add to a ``Rule`` and, for each object, indicates whether you want to negate the settings, for example, requests that do NOT originate from the IP address 192.0.2.44. 

              
              

              - **Negated** *(boolean) --* 

                Set ``Negated`` to ``False`` if you want AWS WAF to allow, block, or count requests based on the settings in the specified  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow or block requests based on that IP address.

                 

                Set ``Negated`` to ``True`` if you want AWS WAF to allow or block a request based on the negation of the settings in the  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow, block, or count requests based on all IP addresses *except*  ``192.0.2.44`` .

                
              

              - **Type** *(string) --* 

                The type of predicate in a ``Rule`` , such as ``ByteMatchSet`` or ``IPSet`` .

                
              

              - **DataId** *(string) --* 

                A unique identifier for a predicate in a ``Rule`` , such as ``ByteMatchSetId`` or ``IPSetId`` . The ID is returned by the corresponding ``Create`` or ``List`` command.

                
          
        
      
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``CreateRule`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: create_size_constraint_set(**kwargs)

    

    Creates a ``SizeConstraintSet`` . You then use  UpdateSizeConstraintSet to identify the part of a web request that you want AWS WAF to check for length, such as the length of the ``User-Agent`` header or the length of the query string. For example, you can create a ``SizeConstraintSet`` that matches any requests that have a query string that is longer than 100 bytes. You can then configure AWS WAF to reject those requests.

     

    To create and configure a ``SizeConstraintSet`` , perform the following steps:

     

     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``CreateSizeConstraintSet`` request.
     
    * Submit a ``CreateSizeConstraintSet`` request.
     
    * Use ``GetChangeToken`` to get the change token that you provide in the ``ChangeToken`` parameter of an ``UpdateSizeConstraintSet`` request.
     
    * Submit an  UpdateSizeConstraintSet request to specify the part of the request that you want AWS WAF to inspect (for example, the header or the URI) and the value that you want AWS WAF to watch for.
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.create_size_constraint_set(
          Name='string',
          ChangeToken='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      A friendly name or description of the  SizeConstraintSet . You can't change ``Name`` after you create a ``SizeConstraintSet`` .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SizeConstraintSet': {
                'SizeConstraintSetId': 'string',
                'Name': 'string',
                'SizeConstraints': [
                    {
                        'FieldToMatch': {
                            'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                            'Data': 'string'
                        },
                        'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE',
                        'ComparisonOperator': 'EQ'|'NE'|'LE'|'LT'|'GE'|'GT',
                        'Size': 123
                    },
                ]
            },
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **SizeConstraintSet** *(dict) --* 

          A  SizeConstraintSet that contains no ``SizeConstraint`` objects.

          
          

          - **SizeConstraintSetId** *(string) --* 

            A unique identifier for a ``SizeConstraintSet`` . You use ``SizeConstraintSetId`` to get information about a ``SizeConstraintSet`` (see  GetSizeConstraintSet ), update a ``SizeConstraintSet`` (see  UpdateSizeConstraintSet ), insert a ``SizeConstraintSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete a ``SizeConstraintSet`` from AWS WAF (see  DeleteSizeConstraintSet ).

             

            ``SizeConstraintSetId`` is returned by  CreateSizeConstraintSet and by  ListSizeConstraintSets .

            
          

          - **Name** *(string) --* 

            The name, if any, of the ``SizeConstraintSet`` .

            
          

          - **SizeConstraints** *(list) --* 

            Specifies the parts of web requests that you want to inspect the size of.

            
            

            - *(dict) --* 

              Specifies a constraint on the size of a part of the web request. AWS WAF uses the ``Size`` , ``ComparisonOperator`` , and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

              
              

              - **FieldToMatch** *(dict) --* 

                Specifies where in a web request to look for ``TargetString`` .

                
                

                - **Type** *(string) --* 

                  The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

                   

                   
                  * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
                   
                  * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                   
                  * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
                   
                  * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                   
                  * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                   

                  
                

                - **Data** *(string) --* 

                  When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

                   

                  The name of the header is not case sensitive.

                  
            
              

              - **TextTransformation** *(string) --* 

                Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

                 

                Note that if you choose ``BODY`` for the value of ``Type`` , you must choose ``NONE`` for ``TextTransformation`` because CloudFront forwards only the first 8192 bytes for inspection. 

                 

                **NONE** 

                 

                Specify ``NONE`` if you don't want to perform any text transformations.

                 

                **CMD_LINE** 

                 

                When you're concerned that attackers are injecting an operating system command line command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

                 

                 
                * Delete the following characters: \ " ' ^
                 
                * Delete spaces before the following characters: / (
                 
                * Replace the following characters with a space: , ;
                 
                * Replace multiple spaces with one space
                 
                * Convert uppercase letters (A-Z) to lowercase (a-z)
                 

                 

                **COMPRESS_WHITE_SPACE** 

                 

                Use this option to replace the following characters with a space character (decimal 32):

                 

                 
                * \f, formfeed, decimal 12
                 
                * \t, tab, decimal 9
                 
                * \n, newline, decimal 10
                 
                * \r, carriage return, decimal 13
                 
                * \v, vertical tab, decimal 11
                 
                * non-breaking space, decimal 160
                 

                 

                ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

                 

                **HTML_ENTITY_DECODE** 

                 

                Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

                 

                 
                * Replaces ``(ampersand)quot;`` with ``"`` 
                 
                * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
                 
                * Replaces ``(ampersand)lt;`` with a "less than" symbol
                 
                * Replaces ``(ampersand)gt;`` with ``>`` 
                 
                * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
                 
                * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
                 

                 

                **LOWERCASE** 

                 

                Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

                 

                **URL_DECODE** 

                 

                Use this option to decode a URL-encoded value.

                
              

              - **ComparisonOperator** *(string) --* 

                The type of comparison you want AWS WAF to perform. AWS WAF uses this in combination with the provided ``Size`` and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

                 

                **EQ** : Used to test if the ``Size`` is equal to the size of the ``FieldToMatch`` 

                 

                **NE** : Used to test if the ``Size`` is not equal to the size of the ``FieldToMatch`` 

                 

                **LE** : Used to test if the ``Size`` is less than or equal to the size of the ``FieldToMatch`` 

                 

                **LT** : Used to test if the ``Size`` is strictly less than the size of the ``FieldToMatch`` 

                 

                **GE** : Used to test if the ``Size`` is greater than or equal to the size of the ``FieldToMatch`` 

                 

                **GT** : Used to test if the ``Size`` is strictly greater than the size of the ``FieldToMatch`` 

                
              

              - **Size** *(integer) --* 

                The size in bytes that you want AWS WAF to compare against the size of the specified ``FieldToMatch`` . AWS WAF uses this in combination with ``ComparisonOperator`` and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

                 

                Valid values for size are 0 - 21474836480 bytes (0 - 20 GB). 

                 

                If you specify ``URI`` for the value of ``Type`` , the / in the URI counts as one character. For example, the URI ``/logo.jpg`` is nine characters long.

                
          
        
      
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``CreateSizeConstraintSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: create_sql_injection_match_set(**kwargs)

    

    Creates a  SqlInjectionMatchSet , which you use to allow, block, or count requests that contain snippets of SQL code in a specified part of web requests. AWS WAF searches for character sequences that are likely to be malicious strings.

     

    To create and configure a ``SqlInjectionMatchSet`` , perform the following steps:

     

     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``CreateSqlInjectionMatchSet`` request.
     
    * Submit a ``CreateSqlInjectionMatchSet`` request.
     
    * Use ``GetChangeToken`` to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateSqlInjectionMatchSet request.
     
    * Submit an  UpdateSqlInjectionMatchSet request to specify the parts of web requests in which you want to allow, block, or count malicious SQL code.
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.create_sql_injection_match_set(
          Name='string',
          ChangeToken='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      A friendly name or description for the  SqlInjectionMatchSet that you're creating. You can't change ``Name`` after you create the ``SqlInjectionMatchSet`` .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SqlInjectionMatchSet': {
                'SqlInjectionMatchSetId': 'string',
                'Name': 'string',
                'SqlInjectionMatchTuples': [
                    {
                        'FieldToMatch': {
                            'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                            'Data': 'string'
                        },
                        'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE'
                    },
                ]
            },
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to a ``CreateSqlInjectionMatchSet`` request.

        
        

        - **SqlInjectionMatchSet** *(dict) --* 

          A  SqlInjectionMatchSet .

          
          

          - **SqlInjectionMatchSetId** *(string) --* 

            A unique identifier for a ``SqlInjectionMatchSet`` . You use ``SqlInjectionMatchSetId`` to get information about a ``SqlInjectionMatchSet`` (see  GetSqlInjectionMatchSet ), update a ``SqlInjectionMatchSet`` (see  UpdateSqlInjectionMatchSet ), insert a ``SqlInjectionMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete a ``SqlInjectionMatchSet`` from AWS WAF (see  DeleteSqlInjectionMatchSet ).

             

            ``SqlInjectionMatchSetId`` is returned by  CreateSqlInjectionMatchSet and by  ListSqlInjectionMatchSets .

            
          

          - **Name** *(string) --* 

            The name, if any, of the ``SqlInjectionMatchSet`` .

            
          

          - **SqlInjectionMatchTuples** *(list) --* 

            Specifies the parts of web requests that you want to inspect for snippets of malicious SQL code.

            
            

            - *(dict) --* 

              Specifies the part of a web request that you want AWS WAF to inspect for snippets of malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.

              
              

              - **FieldToMatch** *(dict) --* 

                Specifies where in a web request to look for ``TargetString`` .

                
                

                - **Type** *(string) --* 

                  The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

                   

                   
                  * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
                   
                  * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                   
                  * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
                   
                  * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                   
                  * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                   

                  
                

                - **Data** *(string) --* 

                  When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

                   

                  The name of the header is not case sensitive.

                  
            
              

              - **TextTransformation** *(string) --* 

                Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

                 

                **CMD_LINE** 

                 

                When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

                 

                 
                * Delete the following characters: \ " ' ^
                 
                * Delete spaces before the following characters: / (
                 
                * Replace the following characters with a space: , ;
                 
                * Replace multiple spaces with one space
                 
                * Convert uppercase letters (A-Z) to lowercase (a-z)
                 

                 

                **COMPRESS_WHITE_SPACE** 

                 

                Use this option to replace the following characters with a space character (decimal 32):

                 

                 
                * \f, formfeed, decimal 12
                 
                * \t, tab, decimal 9
                 
                * \n, newline, decimal 10
                 
                * \r, carriage return, decimal 13
                 
                * \v, vertical tab, decimal 11
                 
                * non-breaking space, decimal 160
                 

                 

                ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

                 

                **HTML_ENTITY_DECODE** 

                 

                Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

                 

                 
                * Replaces ``(ampersand)quot;`` with ``"`` 
                 
                * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
                 
                * Replaces ``(ampersand)lt;`` with a "less than" symbol
                 
                * Replaces ``(ampersand)gt;`` with ``>`` 
                 
                * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
                 
                * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
                 

                 

                **LOWERCASE** 

                 

                Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

                 

                **URL_DECODE** 

                 

                Use this option to decode a URL-encoded value.

                 

                **NONE** 

                 

                Specify ``NONE`` if you don't want to perform any text transformations.

                
          
        
      
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``CreateSqlInjectionMatchSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: create_web_acl(**kwargs)

    

    Creates a ``WebACL`` , which contains the ``Rules`` that identify the CloudFront web requests that you want to allow, block, or count. AWS WAF evaluates ``Rules`` in order based on the value of ``Priority`` for each ``Rule`` .

     

    You also specify a default action, either ``ALLOW`` or ``BLOCK`` . If a web request doesn't match any of the ``Rules`` in a ``WebACL`` , AWS WAF responds to the request with the default action. 

     

    To create and configure a ``WebACL`` , perform the following steps:

     

     
    * Create and update the ``ByteMatchSet`` objects and other predicates that you want to include in ``Rules`` . For more information, see  CreateByteMatchSet ,  UpdateByteMatchSet ,  CreateIPSet ,  UpdateIPSet ,  CreateSqlInjectionMatchSet , and  UpdateSqlInjectionMatchSet .
     
    * Create and update the ``Rules`` that you want to include in the ``WebACL`` . For more information, see  CreateRule and  UpdateRule .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``CreateWebACL`` request.
     
    * Submit a ``CreateWebACL`` request.
     
    * Use ``GetChangeToken`` to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateWebACL request.
     
    * Submit an  UpdateWebACL request to specify the ``Rules`` that you want to include in the ``WebACL`` , to specify the default action, and to associate the ``WebACL`` with a CloudFront distribution.
     

     

    For more information about how to use the AWS WAF API, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.create_web_acl(
          Name='string',
          MetricName='string',
          DefaultAction={
              'Type': 'BLOCK'|'ALLOW'|'COUNT'
          },
          ChangeToken='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      A friendly name or description of the  WebACL . You can't change ``Name`` after you create the ``WebACL`` .

      

    
    :type MetricName: string
    :param MetricName: **[REQUIRED]** 

      A friendly name or description for the metrics for this ``WebACL`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change ``MetricName`` after you create the ``WebACL`` .

      

    
    :type DefaultAction: dict
    :param DefaultAction: **[REQUIRED]** 

      The action that you want AWS WAF to take when a request doesn't match the criteria specified in any of the ``Rule`` objects that are associated with the ``WebACL`` .

      

    
      - **Type** *(string) --* **[REQUIRED]** 

        Specifies how you want AWS WAF to respond to requests that match the settings in a ``Rule`` . Valid settings include the following:

         

         
        * ``ALLOW`` : AWS WAF allows requests
         
        * ``BLOCK`` : AWS WAF blocks requests
         
        * ``COUNT`` : AWS WAF increments a counter of the requests that match all of the conditions in the rule. AWS WAF then continues to inspect the web request based on the remaining rules in the web ACL. You can't specify ``COUNT`` for the default action for a ``WebACL`` .
         

        

      
    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'WebACL': {
                'WebACLId': 'string',
                'Name': 'string',
                'MetricName': 'string',
                'DefaultAction': {
                    'Type': 'BLOCK'|'ALLOW'|'COUNT'
                },
                'Rules': [
                    {
                        'Priority': 123,
                        'RuleId': 'string',
                        'Action': {
                            'Type': 'BLOCK'|'ALLOW'|'COUNT'
                        }
                    },
                ]
            },
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **WebACL** *(dict) --* 

          The  WebACL returned in the ``CreateWebACL`` response.

          
          

          - **WebACLId** *(string) --* 

            A unique identifier for a ``WebACL`` . You use ``WebACLId`` to get information about a ``WebACL`` (see  GetWebACL ), update a ``WebACL`` (see  UpdateWebACL ), and delete a ``WebACL`` from AWS WAF (see  DeleteWebACL ).

             

            ``WebACLId`` is returned by  CreateWebACL and by  ListWebACLs .

            
          

          - **Name** *(string) --* 

            A friendly name or description of the ``WebACL`` . You can't change the name of a ``WebACL`` after you create it.

            
          

          - **MetricName** *(string) --* 
          

          - **DefaultAction** *(dict) --* 

            The action to perform if none of the ``Rules`` contained in the ``WebACL`` match. The action is specified by the  WafAction object.

            
            

            - **Type** *(string) --* 

              Specifies how you want AWS WAF to respond to requests that match the settings in a ``Rule`` . Valid settings include the following:

               

               
              * ``ALLOW`` : AWS WAF allows requests
               
              * ``BLOCK`` : AWS WAF blocks requests
               
              * ``COUNT`` : AWS WAF increments a counter of the requests that match all of the conditions in the rule. AWS WAF then continues to inspect the web request based on the remaining rules in the web ACL. You can't specify ``COUNT`` for the default action for a ``WebACL`` .
               

              
        
          

          - **Rules** *(list) --* 

            An array that contains the action for each ``Rule`` in a ``WebACL`` , the priority of the ``Rule`` , and the ID of the ``Rule`` .

            
            

            - *(dict) --* 

              The ``ActivatedRule`` object in an  UpdateWebACL request specifies a ``Rule`` that you want to insert or delete, the priority of the ``Rule`` in the ``WebACL`` , and the action that you want AWS WAF to take when a web request matches the ``Rule`` (``ALLOW`` , ``BLOCK`` , or ``COUNT`` ).

               

              To specify whether to insert or delete a ``Rule`` , use the ``Action`` parameter in the  WebACLUpdate data type.

              
              

              - **Priority** *(integer) --* 

                Specifies the order in which the ``Rules`` in a ``WebACL`` are evaluated. Rules with a lower value for ``Priority`` are evaluated before ``Rules`` with a higher value. The value must be a unique integer. If you add multiple ``Rules`` to a ``WebACL`` , the values don't need to be consecutive.

                
              

              - **RuleId** *(string) --* 

                The ``RuleId`` for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  GetRule ), update a ``Rule`` (see  UpdateRule ), insert a ``Rule`` into a ``WebACL`` or delete a one from a ``WebACL`` (see  UpdateWebACL ), or delete a ``Rule`` from AWS WAF (see  DeleteRule ).

                 

                ``RuleId`` is returned by  CreateRule and by  ListRules .

                
              

              - **Action** *(dict) --* 

                Specifies the action that CloudFront or AWS WAF takes when a web request matches the conditions in the ``Rule`` . Valid values for ``Action`` include the following:

                 

                 
                * ``ALLOW`` : CloudFront responds with the requested object.
                 
                * ``BLOCK`` : CloudFront responds with an HTTP 403 (Forbidden) status code.
                 
                * ``COUNT`` : AWS WAF increments a counter of requests that match the conditions in the rule and then continues to inspect the web request based on the remaining rules in the web ACL. 
                 

                
                

                - **Type** *(string) --* 

                  Specifies how you want AWS WAF to respond to requests that match the settings in a ``Rule`` . Valid settings include the following:

                   

                   
                  * ``ALLOW`` : AWS WAF allows requests
                   
                  * ``BLOCK`` : AWS WAF blocks requests
                   
                  * ``COUNT`` : AWS WAF increments a counter of the requests that match all of the conditions in the rule. AWS WAF then continues to inspect the web request based on the remaining rules in the web ACL. You can't specify ``COUNT`` for the default action for a ``WebACL`` .
                   

                  
            
          
        
      
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``CreateWebACL`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: create_xss_match_set(**kwargs)

    

    Creates an  XssMatchSet , which you use to allow, block, or count requests that contain cross-site scripting attacks in the specified part of web requests. AWS WAF searches for character sequences that are likely to be malicious strings.

     

    To create and configure an ``XssMatchSet`` , perform the following steps:

     

     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``CreateXssMatchSet`` request.
     
    * Submit a ``CreateXssMatchSet`` request.
     
    * Use ``GetChangeToken`` to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateXssMatchSet request.
     
    * Submit an  UpdateXssMatchSet request to specify the parts of web requests in which you want to allow, block, or count cross-site scripting attacks.
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.create_xss_match_set(
          Name='string',
          ChangeToken='string'
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      A friendly name or description for the  XssMatchSet that you're creating. You can't change ``Name`` after you create the ``XssMatchSet`` .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'XssMatchSet': {
                'XssMatchSetId': 'string',
                'Name': 'string',
                'XssMatchTuples': [
                    {
                        'FieldToMatch': {
                            'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                            'Data': 'string'
                        },
                        'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE'
                    },
                ]
            },
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to a ``CreateXssMatchSet`` request.

        
        

        - **XssMatchSet** *(dict) --* 

          An  XssMatchSet .

          
          

          - **XssMatchSetId** *(string) --* 

            A unique identifier for an ``XssMatchSet`` . You use ``XssMatchSetId`` to get information about an ``XssMatchSet`` (see  GetXssMatchSet ), update an ``XssMatchSet`` (see  UpdateXssMatchSet ), insert an ``XssMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete an ``XssMatchSet`` from AWS WAF (see  DeleteXssMatchSet ).

             

            ``XssMatchSetId`` is returned by  CreateXssMatchSet and by  ListXssMatchSets .

            
          

          - **Name** *(string) --* 

            The name, if any, of the ``XssMatchSet`` .

            
          

          - **XssMatchTuples** *(list) --* 

            Specifies the parts of web requests that you want to inspect for cross-site scripting attacks.

            
            

            - *(dict) --* 

              Specifies the part of a web request that you want AWS WAF to inspect for cross-site scripting attacks and, if you want AWS WAF to inspect a header, the name of the header.

              
              

              - **FieldToMatch** *(dict) --* 

                Specifies where in a web request to look for ``TargetString`` .

                
                

                - **Type** *(string) --* 

                  The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

                   

                   
                  * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
                   
                  * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                   
                  * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
                   
                  * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                   
                  * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                   

                  
                

                - **Data** *(string) --* 

                  When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

                   

                  The name of the header is not case sensitive.

                  
            
              

              - **TextTransformation** *(string) --* 

                Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

                 

                **CMD_LINE** 

                 

                When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

                 

                 
                * Delete the following characters: \ " ' ^
                 
                * Delete spaces before the following characters: / (
                 
                * Replace the following characters with a space: , ;
                 
                * Replace multiple spaces with one space
                 
                * Convert uppercase letters (A-Z) to lowercase (a-z)
                 

                 

                **COMPRESS_WHITE_SPACE** 

                 

                Use this option to replace the following characters with a space character (decimal 32):

                 

                 
                * \f, formfeed, decimal 12
                 
                * \t, tab, decimal 9
                 
                * \n, newline, decimal 10
                 
                * \r, carriage return, decimal 13
                 
                * \v, vertical tab, decimal 11
                 
                * non-breaking space, decimal 160
                 

                 

                ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

                 

                **HTML_ENTITY_DECODE** 

                 

                Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

                 

                 
                * Replaces ``(ampersand)quot;`` with ``"`` 
                 
                * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
                 
                * Replaces ``(ampersand)lt;`` with a "less than" symbol
                 
                * Replaces ``(ampersand)gt;`` with ``>`` 
                 
                * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
                 
                * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
                 

                 

                **LOWERCASE** 

                 

                Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

                 

                **URL_DECODE** 

                 

                Use this option to decode a URL-encoded value.

                 

                **NONE** 

                 

                Specify ``NONE`` if you don't want to perform any text transformations.

                
          
        
      
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``CreateXssMatchSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: delete_byte_match_set(**kwargs)

    

    Permanently deletes a  ByteMatchSet . You can't delete a ``ByteMatchSet`` if it's still used in any ``Rules`` or if it still includes any  ByteMatchTuple objects (any filters).

     

    If you just want to remove a ``ByteMatchSet`` from a ``Rule`` , use  UpdateRule .

     

    To permanently delete a ``ByteMatchSet`` , perform the following steps:

     

     
    * Update the ``ByteMatchSet`` to remove filters, if any. For more information, see  UpdateByteMatchSet .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``DeleteByteMatchSet`` request.
     
    * Submit a ``DeleteByteMatchSet`` request.
     

    

    **Request Syntax** 
    ::

      response = client.delete_byte_match_set(
          ByteMatchSetId='string',
          ChangeToken='string'
      )
    :type ByteMatchSetId: string
    :param ByteMatchSetId: **[REQUIRED]** 

      The ``ByteMatchSetId`` of the  ByteMatchSet that you want to delete. ``ByteMatchSetId`` is returned by  CreateByteMatchSet and by  ListByteMatchSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``DeleteByteMatchSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: delete_ip_set(**kwargs)

    

    Permanently deletes an  IPSet . You can't delete an ``IPSet`` if it's still used in any ``Rules`` or if it still includes any IP addresses.

     

    If you just want to remove an ``IPSet`` from a ``Rule`` , use  UpdateRule .

     

    To permanently delete an ``IPSet`` from AWS WAF, perform the following steps:

     

     
    * Update the ``IPSet`` to remove IP address ranges, if any. For more information, see  UpdateIPSet .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``DeleteIPSet`` request.
     
    * Submit a ``DeleteIPSet`` request.
     

    

    **Request Syntax** 
    ::

      response = client.delete_ip_set(
          IPSetId='string',
          ChangeToken='string'
      )
    :type IPSetId: string
    :param IPSetId: **[REQUIRED]** 

      The ``IPSetId`` of the  IPSet that you want to delete. ``IPSetId`` is returned by  CreateIPSet and by  ListIPSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``DeleteIPSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: delete_rule(**kwargs)

    

    Permanently deletes a  Rule . You can't delete a ``Rule`` if it's still used in any ``WebACL`` objects or if it still includes any predicates, such as ``ByteMatchSet`` objects.

     

    If you just want to remove a ``Rule`` from a ``WebACL`` , use  UpdateWebACL .

     

    To permanently delete a ``Rule`` from AWS WAF, perform the following steps:

     

     
    * Update the ``Rule`` to remove predicates, if any. For more information, see  UpdateRule .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``DeleteRule`` request.
     
    * Submit a ``DeleteRule`` request.
     

    

    **Request Syntax** 
    ::

      response = client.delete_rule(
          RuleId='string',
          ChangeToken='string'
      )
    :type RuleId: string
    :param RuleId: **[REQUIRED]** 

      The ``RuleId`` of the  Rule that you want to delete. ``RuleId`` is returned by  CreateRule and by  ListRules .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``DeleteRule`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: delete_size_constraint_set(**kwargs)

    

    Permanently deletes a  SizeConstraintSet . You can't delete a ``SizeConstraintSet`` if it's still used in any ``Rules`` or if it still includes any  SizeConstraint objects (any filters).

     

    If you just want to remove a ``SizeConstraintSet`` from a ``Rule`` , use  UpdateRule .

     

    To permanently delete a ``SizeConstraintSet`` , perform the following steps:

     

     
    * Update the ``SizeConstraintSet`` to remove filters, if any. For more information, see  UpdateSizeConstraintSet .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``DeleteSizeConstraintSet`` request.
     
    * Submit a ``DeleteSizeConstraintSet`` request.
     

    

    **Request Syntax** 
    ::

      response = client.delete_size_constraint_set(
          SizeConstraintSetId='string',
          ChangeToken='string'
      )
    :type SizeConstraintSetId: string
    :param SizeConstraintSetId: **[REQUIRED]** 

      The ``SizeConstraintSetId`` of the  SizeConstraintSet that you want to delete. ``SizeConstraintSetId`` is returned by  CreateSizeConstraintSet and by  ListSizeConstraintSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``DeleteSizeConstraintSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: delete_sql_injection_match_set(**kwargs)

    

    Permanently deletes a  SqlInjectionMatchSet . You can't delete a ``SqlInjectionMatchSet`` if it's still used in any ``Rules`` or if it still contains any  SqlInjectionMatchTuple objects.

     

    If you just want to remove a ``SqlInjectionMatchSet`` from a ``Rule`` , use  UpdateRule .

     

    To permanently delete a ``SqlInjectionMatchSet`` from AWS WAF, perform the following steps:

     

     
    * Update the ``SqlInjectionMatchSet`` to remove filters, if any. For more information, see  UpdateSqlInjectionMatchSet .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``DeleteSqlInjectionMatchSet`` request.
     
    * Submit a ``DeleteSqlInjectionMatchSet`` request.
     

    

    **Request Syntax** 
    ::

      response = client.delete_sql_injection_match_set(
          SqlInjectionMatchSetId='string',
          ChangeToken='string'
      )
    :type SqlInjectionMatchSetId: string
    :param SqlInjectionMatchSetId: **[REQUIRED]** 

      The ``SqlInjectionMatchSetId`` of the  SqlInjectionMatchSet that you want to delete. ``SqlInjectionMatchSetId`` is returned by  CreateSqlInjectionMatchSet and by  ListSqlInjectionMatchSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to a request to delete a  SqlInjectionMatchSet from AWS WAF.

        
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``DeleteSqlInjectionMatchSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: delete_web_acl(**kwargs)

    

    Permanently deletes a  WebACL . You can't delete a ``WebACL`` if it still contains any ``Rules`` .

     

    To delete a ``WebACL`` , perform the following steps:

     

     
    * Update the ``WebACL`` to remove ``Rules`` , if any. For more information, see  UpdateWebACL .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``DeleteWebACL`` request.
     
    * Submit a ``DeleteWebACL`` request.
     

    

    **Request Syntax** 
    ::

      response = client.delete_web_acl(
          WebACLId='string',
          ChangeToken='string'
      )
    :type WebACLId: string
    :param WebACLId: **[REQUIRED]** 

      The ``WebACLId`` of the  WebACL that you want to delete. ``WebACLId`` is returned by  CreateWebACL and by  ListWebACLs .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``DeleteWebACL`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: delete_xss_match_set(**kwargs)

    

    Permanently deletes an  XssMatchSet . You can't delete an ``XssMatchSet`` if it's still used in any ``Rules`` or if it still contains any  XssMatchTuple objects.

     

    If you just want to remove an ``XssMatchSet`` from a ``Rule`` , use  UpdateRule .

     

    To permanently delete an ``XssMatchSet`` from AWS WAF, perform the following steps:

     

     
    * Update the ``XssMatchSet`` to remove filters, if any. For more information, see  UpdateXssMatchSet .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of a ``DeleteXssMatchSet`` request.
     
    * Submit a ``DeleteXssMatchSet`` request.
     

    

    **Request Syntax** 
    ::

      response = client.delete_xss_match_set(
          XssMatchSetId='string',
          ChangeToken='string'
      )
    :type XssMatchSetId: string
    :param XssMatchSetId: **[REQUIRED]** 

      The ``XssMatchSetId`` of the  XssMatchSet that you want to delete. ``XssMatchSetId`` is returned by  CreateXssMatchSet and by  ListXssMatchSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to a request to delete an  XssMatchSet from AWS WAF.

        
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``DeleteXssMatchSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

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


  .. py:method:: get_byte_match_set(**kwargs)

    

    Returns the  ByteMatchSet specified by ``ByteMatchSetId`` .

    

    **Request Syntax** 
    ::

      response = client.get_byte_match_set(
          ByteMatchSetId='string'
      )
    :type ByteMatchSetId: string
    :param ByteMatchSetId: **[REQUIRED]** 

      The ``ByteMatchSetId`` of the  ByteMatchSet that you want to get. ``ByteMatchSetId`` is returned by  CreateByteMatchSet and by  ListByteMatchSets .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ByteMatchSet': {
                'ByteMatchSetId': 'string',
                'Name': 'string',
                'ByteMatchTuples': [
                    {
                        'FieldToMatch': {
                            'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                            'Data': 'string'
                        },
                        'TargetString': b'bytes',
                        'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE',
                        'PositionalConstraint': 'EXACTLY'|'STARTS_WITH'|'ENDS_WITH'|'CONTAINS'|'CONTAINS_WORD'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ByteMatchSet** *(dict) --* 

          Information about the  ByteMatchSet that you specified in the ``GetByteMatchSet`` request. For more information, see the following topics:

           

           
          *  ByteMatchSet : Contains ``ByteMatchSetId`` , ``ByteMatchTuples`` , and ``Name`` 
           
          * ``ByteMatchTuples`` : Contains an array of  ByteMatchTuple objects. Each ``ByteMatchTuple`` object contains  FieldToMatch , ``PositionalConstraint`` , ``TargetString`` , and ``TextTransformation`` 
           
          *  FieldToMatch : Contains ``Data`` and ``Type`` 
           

          
          

          - **ByteMatchSetId** *(string) --* 

            The ``ByteMatchSetId`` for a ``ByteMatchSet`` . You use ``ByteMatchSetId`` to get information about a ``ByteMatchSet`` (see  GetByteMatchSet ), update a ``ByteMatchSet`` (see  UpdateByteMatchSet ), insert a ``ByteMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete a ``ByteMatchSet`` from AWS WAF (see  DeleteByteMatchSet ).

             

            ``ByteMatchSetId`` is returned by  CreateByteMatchSet and by  ListByteMatchSets .

            
          

          - **Name** *(string) --* 

            A friendly name or description of the  ByteMatchSet . You can't change ``Name`` after you create a ``ByteMatchSet`` .

            
          

          - **ByteMatchTuples** *(list) --* 

            Specifies the bytes (typically a string that corresponds with ASCII characters) that you want AWS WAF to search for in web requests, the location in requests that you want AWS WAF to search, and other settings.

            
            

            - *(dict) --* 

              The bytes (typically a string that corresponds with ASCII characters) that you want AWS WAF to search for in web requests, the location in requests that you want AWS WAF to search, and other settings.

              
              

              - **FieldToMatch** *(dict) --* 

                The part of a web request that you want AWS WAF to search, such as a specified header or a query string. For more information, see  FieldToMatch .

                
                

                - **Type** *(string) --* 

                  The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

                   

                   
                  * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
                   
                  * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                   
                  * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
                   
                  * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                   
                  * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                   

                  
                

                - **Data** *(string) --* 

                  When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

                   

                  The name of the header is not case sensitive.

                  
            
              

              - **TargetString** *(bytes) --* 

                The value that you want AWS WAF to search for. AWS WAF searches for the specified string in the part of web requests that you specified in ``FieldToMatch`` . The maximum length of the value is 50 bytes.

                 

                Valid values depend on the values that you specified for ``FieldToMatch`` :

                 

                 
                * ``HEADER`` : The value that you want AWS WAF to search for in the request header that you specified in  FieldToMatch , for example, the value of the ``User-Agent`` or ``Referer`` header.
                 
                * ``METHOD`` : The HTTP method, which indicates the type of operation specified in the request. CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                 
                * ``QUERY_STRING`` : The value that you want AWS WAF to search for in the query string, which is the part of a URL that appears after a ``?`` character.
                 
                * ``URI`` : The value that you want AWS WAF to search for in the part of a URL that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                 
                * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                 

                 

                If ``TargetString`` includes alphabetic characters A-Z and a-z, note that the value is case sensitive.

                 

                **If you're using the AWS WAF API** 

                 

                Specify a base64-encoded version of the value. The maximum length of the value before you base64-encode it is 50 bytes. 

                 

                For example, suppose the value of ``Type`` is ``HEADER`` and the value of ``Data`` is ``User-Agent`` . If you want to search the ``User-Agent`` header for the value ``BadBot`` , you base64-encode ``BadBot`` using MIME base64 encoding and include the resulting value, ``QmFkQm90`` , in the value of ``TargetString`` .

                 

                **If you're using the AWS CLI or one of the AWS SDKs** 

                 

                The value that you want AWS WAF to search for. The SDK automatically base64 encodes the value.

                
              

              - **TextTransformation** *(string) --* 

                Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``TargetString`` before inspecting a request for a match.

                 

                **CMD_LINE** 

                 

                When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

                 

                 
                * Delete the following characters: \ " ' ^
                 
                * Delete spaces before the following characters: / (
                 
                * Replace the following characters with a space: , ;
                 
                * Replace multiple spaces with one space
                 
                * Convert uppercase letters (A-Z) to lowercase (a-z)
                 

                 

                **COMPRESS_WHITE_SPACE** 

                 

                Use this option to replace the following characters with a space character (decimal 32):

                 

                 
                * \f, formfeed, decimal 12
                 
                * \t, tab, decimal 9
                 
                * \n, newline, decimal 10
                 
                * \r, carriage return, decimal 13
                 
                * \v, vertical tab, decimal 11
                 
                * non-breaking space, decimal 160
                 

                 

                ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

                 

                **HTML_ENTITY_DECODE** 

                 

                Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

                 

                 
                * Replaces ``(ampersand)quot;`` with ``"`` 
                 
                * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
                 
                * Replaces ``(ampersand)lt;`` with a "less than" symbol
                 
                * Replaces ``(ampersand)gt;`` with ``>`` 
                 
                * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
                 
                * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
                 

                 

                **LOWERCASE** 

                 

                Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

                 

                **URL_DECODE** 

                 

                Use this option to decode a URL-encoded value.

                 

                **NONE** 

                 

                Specify ``NONE`` if you don't want to perform any text transformations.

                
              

              - **PositionalConstraint** *(string) --* 

                Within the portion of a web request that you want to search (for example, in the query string, if any), specify where you want AWS WAF to search. Valid values include the following:

                 

                **CONTAINS** 

                 

                The specified part of the web request must include the value of ``TargetString`` , but the location doesn't matter.

                 

                **CONTAINS_WORD** 

                 

                The specified part of the web request must include the value of ``TargetString`` , and ``TargetString`` must contain only alphanumeric characters or underscore (A-Z, a-z, 0-9, or _). In addition, ``TargetString`` must be a word, which means one of the following:

                 

                 
                * ``TargetString`` exactly matches the value of the specified part of the web request, such as the value of a header.
                 
                * ``TargetString`` is at the beginning of the specified part of the web request and is followed by a character other than an alphanumeric character or underscore (_), for example, ``BadBot;`` .
                 
                * ``TargetString`` is at the end of the specified part of the web request and is preceded by a character other than an alphanumeric character or underscore (_), for example, ``;BadBot`` .
                 
                * ``TargetString`` is in the middle of the specified part of the web request and is preceded and followed by characters other than alphanumeric characters or underscore (_), for example, ``-BadBot;`` .
                 

                 

                **EXACTLY** 

                 

                The value of the specified part of the web request must exactly match the value of ``TargetString`` .

                 

                **STARTS_WITH** 

                 

                The value of ``TargetString`` must appear at the beginning of the specified part of the web request.

                 

                **ENDS_WITH** 

                 

                The value of ``TargetString`` must appear at the end of the specified part of the web request.

                
          
        
      
    

  .. py:method:: get_change_token()

    

    When you want to create, update, or delete AWS WAF objects, get a change token and include the change token in the create, update, or delete request. Change tokens ensure that your application doesn't submit conflicting requests to AWS WAF.

     

    Each create, update, or delete request must use a unique change token. If your application submits a ``GetChangeToken`` request and then submits a second ``GetChangeToken`` request before submitting a create, update, or delete request, the second ``GetChangeToken`` request returns the same value as the first ``GetChangeToken`` request.

     

    When you use a change token in a create, update, or delete request, the status of the change token changes to ``PENDING`` , which indicates that AWS WAF is propagating the change to all AWS WAF servers. Use ``GetChangeTokenStatus`` to determine the status of your change token.

    

    **Request Syntax** 
    ::

      response = client.get_change_token()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used in the request. Use this value in a ``GetChangeTokenStatus`` request to get the current status of the request. 

          
    

  .. py:method:: get_change_token_status(**kwargs)

    

    Returns the status of a ``ChangeToken`` that you got by calling  GetChangeToken . ``ChangeTokenStatus`` is one of the following values:

     

     
    * ``PROVISIONED`` : You requested the change token by calling ``GetChangeToken`` , but you haven't used it yet in a call to create, update, or delete an AWS WAF object.
     
    * ``PENDING`` : AWS WAF is propagating the create, update, or delete request to all AWS WAF servers.
     
    * ``IN_SYNC`` : Propagation is complete.
     

    

    **Request Syntax** 
    ::

      response = client.get_change_token_status(
          ChangeToken='string'
      )
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The change token for which you want to get the status. This change token was previously returned in the ``GetChangeToken`` response.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeTokenStatus': 'PROVISIONED'|'PENDING'|'INSYNC'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeTokenStatus** *(string) --* 

          The status of the change token.

          
    

  .. py:method:: get_ip_set(**kwargs)

    

    Returns the  IPSet that is specified by ``IPSetId`` .

    

    **Request Syntax** 
    ::

      response = client.get_ip_set(
          IPSetId='string'
      )
    :type IPSetId: string
    :param IPSetId: **[REQUIRED]** 

      The ``IPSetId`` of the  IPSet that you want to get. ``IPSetId`` is returned by  CreateIPSet and by  ListIPSets .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'IPSet': {
                'IPSetId': 'string',
                'Name': 'string',
                'IPSetDescriptors': [
                    {
                        'Type': 'IPV4',
                        'Value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **IPSet** *(dict) --* 

          Information about the  IPSet that you specified in the ``GetIPSet`` request. For more information, see the following topics:

           

           
          *  IPSet : Contains ``IPSetDescriptors`` , ``IPSetId`` , and ``Name`` 
           
          * ``IPSetDescriptors`` : Contains an array of  IPSetDescriptor objects. Each ``IPSetDescriptor`` object contains ``Type`` and ``Value`` 
           

          
          

          - **IPSetId** *(string) --* 

            The ``IPSetId`` for an ``IPSet`` . You use ``IPSetId`` to get information about an ``IPSet`` (see  GetIPSet ), update an ``IPSet`` (see  UpdateIPSet ), insert an ``IPSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete an ``IPSet`` from AWS WAF (see  DeleteIPSet ).

             

            ``IPSetId`` is returned by  CreateIPSet and by  ListIPSets .

            
          

          - **Name** *(string) --* 

            A friendly name or description of the  IPSet . You can't change the name of an ``IPSet`` after you create it.

            
          

          - **IPSetDescriptors** *(list) --* 

            The IP address type (``IPV4`` ) and the IP address range (in CIDR notation) that web requests originate from. If the ``WebACL`` is associated with a CloudFront distribution, this is the value of one of the following fields in CloudFront access logs:

             

             
            * ``c-ip`` , if the viewer did not use an HTTP proxy or a load balancer to send the request
             
            * ``x-forwarded-for`` , if the viewer did use an HTTP proxy or a load balancer to send the request
             

            
            

            - *(dict) --* 

              Specifies the IP address type (``IPV4`` ) and the IP address range (in CIDR format) that web requests originate from.

              
              

              - **Type** *(string) --* 

                Specify ``IPV4`` .

                
              

              - **Value** *(string) --* 

                Specify an IPv4 address by using CIDR notation. For example:

                 

                 
                * To configure AWS WAF to allow, block, or count requests that originated from the IP address 192.0.2.44, specify ``192.0.2.44/32`` .
                 
                * To configure AWS WAF to allow, block, or count requests that originated from IP addresses from 192.0.2.0 to 192.0.2.255, specify ``192.0.2.0/24`` .
                 

                 

                AWS WAF supports only /8, /16, /24, and /32 IP addresses.

                 

                For more information about CIDR notation, see the Wikipedia entry `Classless Inter-Domain Routing`_ .

                
          
        
      
    

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


  .. py:method:: get_rule(**kwargs)

    

    Returns the  Rule that is specified by the ``RuleId`` that you included in the ``GetRule`` request.

    

    **Request Syntax** 
    ::

      response = client.get_rule(
          RuleId='string'
      )
    :type RuleId: string
    :param RuleId: **[REQUIRED]** 

      The ``RuleId`` of the  Rule that you want to get. ``RuleId`` is returned by  CreateRule and by  ListRules .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Rule': {
                'RuleId': 'string',
                'Name': 'string',
                'MetricName': 'string',
                'Predicates': [
                    {
                        'Negated': True|False,
                        'Type': 'IPMatch'|'ByteMatch'|'SqlInjectionMatch'|'SizeConstraint'|'XssMatch',
                        'DataId': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **Rule** *(dict) --* 

          Information about the  Rule that you specified in the ``GetRule`` request. For more information, see the following topics:

           

           
          *  Rule : Contains ``MetricName`` , ``Name`` , an array of ``Predicate`` objects, and ``RuleId`` 
           
          *  Predicate : Each ``Predicate`` object contains ``DataId`` , ``Negated`` , and ``Type`` 
           

          
          

          - **RuleId** *(string) --* 

            A unique identifier for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  GetRule ), update a ``Rule`` (see  UpdateRule ), insert a ``Rule`` into a ``WebACL`` or delete a one from a ``WebACL`` (see  UpdateWebACL ), or delete a ``Rule`` from AWS WAF (see  DeleteRule ).

             

            ``RuleId`` is returned by  CreateRule and by  ListRules .

            
          

          - **Name** *(string) --* 

            The friendly name or description for the ``Rule`` . You can't change the name of a ``Rule`` after you create it.

            
          

          - **MetricName** *(string) --* 
          

          - **Predicates** *(list) --* 

            The ``Predicates`` object contains one ``Predicate`` element for each  ByteMatchSet ,  IPSet , or  SqlInjectionMatchSet object that you want to include in a ``Rule`` .

            
            

            - *(dict) --* 

              Specifies the  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , and  SizeConstraintSet objects that you want to add to a ``Rule`` and, for each object, indicates whether you want to negate the settings, for example, requests that do NOT originate from the IP address 192.0.2.44. 

              
              

              - **Negated** *(boolean) --* 

                Set ``Negated`` to ``False`` if you want AWS WAF to allow, block, or count requests based on the settings in the specified  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow or block requests based on that IP address.

                 

                Set ``Negated`` to ``True`` if you want AWS WAF to allow or block a request based on the negation of the settings in the  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow, block, or count requests based on all IP addresses *except*  ``192.0.2.44`` .

                
              

              - **Type** *(string) --* 

                The type of predicate in a ``Rule`` , such as ``ByteMatchSet`` or ``IPSet`` .

                
              

              - **DataId** *(string) --* 

                A unique identifier for a predicate in a ``Rule`` , such as ``ByteMatchSetId`` or ``IPSetId`` . The ID is returned by the corresponding ``Create`` or ``List`` command.

                
          
        
      
    

  .. py:method:: get_sampled_requests(**kwargs)

    

    Gets detailed information about a specified number of requests--a sample--that AWS WAF randomly selects from among the first 5,000 requests that your AWS resource received during a time range that you choose. You can specify a sample size of up to 100 requests, and you can specify any time range in the previous three hours.

     

    ``GetSampledRequests`` returns a time range, which is usually the time range that you specified. However, if your resource (such as a CloudFront distribution) received 5,000 requests before the specified time range elapsed, ``GetSampledRequests`` returns an updated time range. This new time range indicates the actual period during which AWS WAF selected the requests in the sample.

    

    **Request Syntax** 
    ::

      response = client.get_sampled_requests(
          WebAclId='string',
          RuleId='string',
          TimeWindow={
              'StartTime': datetime(2015, 1, 1),
              'EndTime': datetime(2015, 1, 1)
          },
          MaxItems=123
      )
    :type WebAclId: string
    :param WebAclId: **[REQUIRED]** 

      The ``WebACLId`` of the ``WebACL`` for which you want ``GetSampledRequests`` to return a sample of requests.

      

    
    :type RuleId: string
    :param RuleId: **[REQUIRED]** 

      ``RuleId`` is one of two values:

       

       
      * The ``RuleId`` of the ``Rule`` for which you want ``GetSampledRequests`` to return a sample of requests.
       
      * ``Default_Action`` , which causes ``GetSampledRequests`` to return a sample of the requests that didn't match any of the rules in the specified ``WebACL`` .
       

      

    
    :type TimeWindow: dict
    :param TimeWindow: **[REQUIRED]** 

      The start date and time and the end date and time of the range for which you want ``GetSampledRequests`` to return a sample of requests. Specify the date and time in Unix time format (in seconds). You can specify any time range in the previous three hours.

      

    
      - **StartTime** *(datetime) --* **[REQUIRED]** 

        The beginning of the time range from which you want ``GetSampledRequests`` to return a sample of the requests that your AWS resource received. You can specify any time range in the previous three hours.

        

      
      - **EndTime** *(datetime) --* **[REQUIRED]** 

        The end of the time range from which you want ``GetSampledRequests`` to return a sample of the requests that your AWS resource received. You can specify any time range in the previous three hours.

        

      
    
    :type MaxItems: integer
    :param MaxItems: **[REQUIRED]** 

      The number of requests that you want AWS WAF to return from among the first 5,000 requests that your AWS resource received during the time range. If your resource received fewer requests than the value of ``MaxItems`` , ``GetSampledRequests`` returns information about all of them. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SampledRequests': [
                {
                    'Request': {
                        'ClientIP': 'string',
                        'Country': 'string',
                        'URI': 'string',
                        'Method': 'string',
                        'HTTPVersion': 'string',
                        'Headers': [
                            {
                                'Name': 'string',
                                'Value': 'string'
                            },
                        ]
                    },
                    'Weight': 123,
                    'Timestamp': datetime(2015, 1, 1),
                    'Action': 'string'
                },
            ],
            'PopulationSize': 123,
            'TimeWindow': {
                'StartTime': datetime(2015, 1, 1),
                'EndTime': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **SampledRequests** *(list) --* 

          A complex type that contains detailed information about each of the requests in the sample.

          
          

          - *(dict) --* 

            The response from a  GetSampledRequests request includes a ``SampledHTTPRequests`` complex type that appears as ``SampledRequests`` in the response syntax. ``SampledHTTPRequests`` contains one ``SampledHTTPRequest`` object for each web request that is returned by ``GetSampledRequests`` .

            
            

            - **Request** *(dict) --* 

              A complex type that contains detailed information about the request.

              
              

              - **ClientIP** *(string) --* 

                The IP address that the request originated from. If the ``WebACL`` is associated with a CloudFront distribution, this is the value of one of the following fields in CloudFront access logs:

                 

                 
                * ``c-ip`` , if the viewer did not use an HTTP proxy or a load balancer to send the request
                 
                * ``x-forwarded-for`` , if the viewer did use an HTTP proxy or a load balancer to send the request
                 

                
              

              - **Country** *(string) --* 

                The two-letter country code for the country that the request originated from. For a current list of country codes, see the Wikipedia entry `ISO 3166-1 alpha-2`_ .

                
              

              - **URI** *(string) --* 

                The part of a web request that identifies the resource, for example, ``/images/daily-ad.jpg`` .

                
              

              - **Method** *(string) --* 

                The HTTP method specified in the sampled web request. CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` . 

                
              

              - **HTTPVersion** *(string) --* 

                The HTTP version specified in the sampled web request, for example, ``HTTP/1.1`` .

                
              

              - **Headers** *(list) --* 

                A complex type that contains two values for each header in the sampled web request: the name of the header and the value of the header.

                
                

                - *(dict) --* 

                  The response from a  GetSampledRequests request includes an ``HTTPHeader`` complex type that appears as ``Headers`` in the response syntax. ``HTTPHeader`` contains the names and values of all of the headers that appear in one of the web requests that were returned by ``GetSampledRequests`` . 

                  
                  

                  - **Name** *(string) --* 

                    The name of one of the headers in the sampled web request.

                    
                  

                  - **Value** *(string) --* 

                    The value of one of the headers in the sampled web request.

                    
              
            
          
            

            - **Weight** *(integer) --* 

              A value that indicates how one result in the response relates proportionally to other results in the response. A result that has a weight of ``2`` represents roughly twice as many CloudFront web requests as a result that has a weight of ``1`` .

              
            

            - **Timestamp** *(datetime) --* 

              The time at which AWS WAF received the request from your AWS resource, in Unix time format (in seconds).

              
            

            - **Action** *(string) --* 

              The action for the ``Rule`` that the request matched: ``ALLOW`` , ``BLOCK`` , or ``COUNT`` .

              
        
      
        

        - **PopulationSize** *(integer) --* 

          The total number of requests from which ``GetSampledRequests`` got a sample of ``MaxItems`` requests. If ``PopulationSize`` is less than ``MaxItems`` , the sample includes every request that your AWS resource received during the specified time range.

          
        

        - **TimeWindow** *(dict) --* 

          Usually, ``TimeWindow`` is the time range that you specified in the ``GetSampledRequests`` request. However, if your AWS resource received more than 5,000 requests during the time range that you specified in the request, ``GetSampledRequests`` returns the time range for the first 5,000 requests.

          
          

          - **StartTime** *(datetime) --* 

            The beginning of the time range from which you want ``GetSampledRequests`` to return a sample of the requests that your AWS resource received. You can specify any time range in the previous three hours.

            
          

          - **EndTime** *(datetime) --* 

            The end of the time range from which you want ``GetSampledRequests`` to return a sample of the requests that your AWS resource received. You can specify any time range in the previous three hours.

            
      
    

  .. py:method:: get_size_constraint_set(**kwargs)

    

    Returns the  SizeConstraintSet specified by ``SizeConstraintSetId`` .

    

    **Request Syntax** 
    ::

      response = client.get_size_constraint_set(
          SizeConstraintSetId='string'
      )
    :type SizeConstraintSetId: string
    :param SizeConstraintSetId: **[REQUIRED]** 

      The ``SizeConstraintSetId`` of the  SizeConstraintSet that you want to get. ``SizeConstraintSetId`` is returned by  CreateSizeConstraintSet and by  ListSizeConstraintSets .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SizeConstraintSet': {
                'SizeConstraintSetId': 'string',
                'Name': 'string',
                'SizeConstraints': [
                    {
                        'FieldToMatch': {
                            'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                            'Data': 'string'
                        },
                        'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE',
                        'ComparisonOperator': 'EQ'|'NE'|'LE'|'LT'|'GE'|'GT',
                        'Size': 123
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **SizeConstraintSet** *(dict) --* 

          Information about the  SizeConstraintSet that you specified in the ``GetSizeConstraintSet`` request. For more information, see the following topics:

           

           
          *  SizeConstraintSet : Contains ``SizeConstraintSetId`` , ``SizeConstraints`` , and ``Name`` 
           
          * ``SizeConstraints`` : Contains an array of  SizeConstraint objects. Each ``SizeConstraint`` object contains  FieldToMatch , ``TextTransformation`` , ``ComparisonOperator`` , and ``Size`` 
           
          *  FieldToMatch : Contains ``Data`` and ``Type`` 
           

          
          

          - **SizeConstraintSetId** *(string) --* 

            A unique identifier for a ``SizeConstraintSet`` . You use ``SizeConstraintSetId`` to get information about a ``SizeConstraintSet`` (see  GetSizeConstraintSet ), update a ``SizeConstraintSet`` (see  UpdateSizeConstraintSet ), insert a ``SizeConstraintSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete a ``SizeConstraintSet`` from AWS WAF (see  DeleteSizeConstraintSet ).

             

            ``SizeConstraintSetId`` is returned by  CreateSizeConstraintSet and by  ListSizeConstraintSets .

            
          

          - **Name** *(string) --* 

            The name, if any, of the ``SizeConstraintSet`` .

            
          

          - **SizeConstraints** *(list) --* 

            Specifies the parts of web requests that you want to inspect the size of.

            
            

            - *(dict) --* 

              Specifies a constraint on the size of a part of the web request. AWS WAF uses the ``Size`` , ``ComparisonOperator`` , and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

              
              

              - **FieldToMatch** *(dict) --* 

                Specifies where in a web request to look for ``TargetString`` .

                
                

                - **Type** *(string) --* 

                  The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

                   

                   
                  * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
                   
                  * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                   
                  * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
                   
                  * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                   
                  * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                   

                  
                

                - **Data** *(string) --* 

                  When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

                   

                  The name of the header is not case sensitive.

                  
            
              

              - **TextTransformation** *(string) --* 

                Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

                 

                Note that if you choose ``BODY`` for the value of ``Type`` , you must choose ``NONE`` for ``TextTransformation`` because CloudFront forwards only the first 8192 bytes for inspection. 

                 

                **NONE** 

                 

                Specify ``NONE`` if you don't want to perform any text transformations.

                 

                **CMD_LINE** 

                 

                When you're concerned that attackers are injecting an operating system command line command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

                 

                 
                * Delete the following characters: \ " ' ^
                 
                * Delete spaces before the following characters: / (
                 
                * Replace the following characters with a space: , ;
                 
                * Replace multiple spaces with one space
                 
                * Convert uppercase letters (A-Z) to lowercase (a-z)
                 

                 

                **COMPRESS_WHITE_SPACE** 

                 

                Use this option to replace the following characters with a space character (decimal 32):

                 

                 
                * \f, formfeed, decimal 12
                 
                * \t, tab, decimal 9
                 
                * \n, newline, decimal 10
                 
                * \r, carriage return, decimal 13
                 
                * \v, vertical tab, decimal 11
                 
                * non-breaking space, decimal 160
                 

                 

                ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

                 

                **HTML_ENTITY_DECODE** 

                 

                Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

                 

                 
                * Replaces ``(ampersand)quot;`` with ``"`` 
                 
                * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
                 
                * Replaces ``(ampersand)lt;`` with a "less than" symbol
                 
                * Replaces ``(ampersand)gt;`` with ``>`` 
                 
                * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
                 
                * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
                 

                 

                **LOWERCASE** 

                 

                Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

                 

                **URL_DECODE** 

                 

                Use this option to decode a URL-encoded value.

                
              

              - **ComparisonOperator** *(string) --* 

                The type of comparison you want AWS WAF to perform. AWS WAF uses this in combination with the provided ``Size`` and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

                 

                **EQ** : Used to test if the ``Size`` is equal to the size of the ``FieldToMatch`` 

                 

                **NE** : Used to test if the ``Size`` is not equal to the size of the ``FieldToMatch`` 

                 

                **LE** : Used to test if the ``Size`` is less than or equal to the size of the ``FieldToMatch`` 

                 

                **LT** : Used to test if the ``Size`` is strictly less than the size of the ``FieldToMatch`` 

                 

                **GE** : Used to test if the ``Size`` is greater than or equal to the size of the ``FieldToMatch`` 

                 

                **GT** : Used to test if the ``Size`` is strictly greater than the size of the ``FieldToMatch`` 

                
              

              - **Size** *(integer) --* 

                The size in bytes that you want AWS WAF to compare against the size of the specified ``FieldToMatch`` . AWS WAF uses this in combination with ``ComparisonOperator`` and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

                 

                Valid values for size are 0 - 21474836480 bytes (0 - 20 GB). 

                 

                If you specify ``URI`` for the value of ``Type`` , the / in the URI counts as one character. For example, the URI ``/logo.jpg`` is nine characters long.

                
          
        
      
    

  .. py:method:: get_sql_injection_match_set(**kwargs)

    

    Returns the  SqlInjectionMatchSet that is specified by ``SqlInjectionMatchSetId`` .

    

    **Request Syntax** 
    ::

      response = client.get_sql_injection_match_set(
          SqlInjectionMatchSetId='string'
      )
    :type SqlInjectionMatchSetId: string
    :param SqlInjectionMatchSetId: **[REQUIRED]** 

      The ``SqlInjectionMatchSetId`` of the  SqlInjectionMatchSet that you want to get. ``SqlInjectionMatchSetId`` is returned by  CreateSqlInjectionMatchSet and by  ListSqlInjectionMatchSets .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SqlInjectionMatchSet': {
                'SqlInjectionMatchSetId': 'string',
                'Name': 'string',
                'SqlInjectionMatchTuples': [
                    {
                        'FieldToMatch': {
                            'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                            'Data': 'string'
                        },
                        'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to a  GetSqlInjectionMatchSet request.

        
        

        - **SqlInjectionMatchSet** *(dict) --* 

          Information about the  SqlInjectionMatchSet that you specified in the ``GetSqlInjectionMatchSet`` request. For more information, see the following topics:

           

           
          *  SqlInjectionMatchSet : Contains ``Name`` , ``SqlInjectionMatchSetId`` , and an array of ``SqlInjectionMatchTuple`` objects
           
          *  SqlInjectionMatchTuple : Each ``SqlInjectionMatchTuple`` object contains ``FieldToMatch`` and ``TextTransformation`` 
           
          *  FieldToMatch : Contains ``Data`` and ``Type`` 
           

          
          

          - **SqlInjectionMatchSetId** *(string) --* 

            A unique identifier for a ``SqlInjectionMatchSet`` . You use ``SqlInjectionMatchSetId`` to get information about a ``SqlInjectionMatchSet`` (see  GetSqlInjectionMatchSet ), update a ``SqlInjectionMatchSet`` (see  UpdateSqlInjectionMatchSet ), insert a ``SqlInjectionMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete a ``SqlInjectionMatchSet`` from AWS WAF (see  DeleteSqlInjectionMatchSet ).

             

            ``SqlInjectionMatchSetId`` is returned by  CreateSqlInjectionMatchSet and by  ListSqlInjectionMatchSets .

            
          

          - **Name** *(string) --* 

            The name, if any, of the ``SqlInjectionMatchSet`` .

            
          

          - **SqlInjectionMatchTuples** *(list) --* 

            Specifies the parts of web requests that you want to inspect for snippets of malicious SQL code.

            
            

            - *(dict) --* 

              Specifies the part of a web request that you want AWS WAF to inspect for snippets of malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.

              
              

              - **FieldToMatch** *(dict) --* 

                Specifies where in a web request to look for ``TargetString`` .

                
                

                - **Type** *(string) --* 

                  The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

                   

                   
                  * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
                   
                  * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                   
                  * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
                   
                  * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                   
                  * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                   

                  
                

                - **Data** *(string) --* 

                  When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

                   

                  The name of the header is not case sensitive.

                  
            
              

              - **TextTransformation** *(string) --* 

                Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

                 

                **CMD_LINE** 

                 

                When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

                 

                 
                * Delete the following characters: \ " ' ^
                 
                * Delete spaces before the following characters: / (
                 
                * Replace the following characters with a space: , ;
                 
                * Replace multiple spaces with one space
                 
                * Convert uppercase letters (A-Z) to lowercase (a-z)
                 

                 

                **COMPRESS_WHITE_SPACE** 

                 

                Use this option to replace the following characters with a space character (decimal 32):

                 

                 
                * \f, formfeed, decimal 12
                 
                * \t, tab, decimal 9
                 
                * \n, newline, decimal 10
                 
                * \r, carriage return, decimal 13
                 
                * \v, vertical tab, decimal 11
                 
                * non-breaking space, decimal 160
                 

                 

                ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

                 

                **HTML_ENTITY_DECODE** 

                 

                Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

                 

                 
                * Replaces ``(ampersand)quot;`` with ``"`` 
                 
                * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
                 
                * Replaces ``(ampersand)lt;`` with a "less than" symbol
                 
                * Replaces ``(ampersand)gt;`` with ``>`` 
                 
                * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
                 
                * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
                 

                 

                **LOWERCASE** 

                 

                Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

                 

                **URL_DECODE** 

                 

                Use this option to decode a URL-encoded value.

                 

                **NONE** 

                 

                Specify ``NONE`` if you don't want to perform any text transformations.

                
          
        
      
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: get_web_acl(**kwargs)

    

    Returns the  WebACL that is specified by ``WebACLId`` .

    

    **Request Syntax** 
    ::

      response = client.get_web_acl(
          WebACLId='string'
      )
    :type WebACLId: string
    :param WebACLId: **[REQUIRED]** 

      The ``WebACLId`` of the  WebACL that you want to get. ``WebACLId`` is returned by  CreateWebACL and by  ListWebACLs .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'WebACL': {
                'WebACLId': 'string',
                'Name': 'string',
                'MetricName': 'string',
                'DefaultAction': {
                    'Type': 'BLOCK'|'ALLOW'|'COUNT'
                },
                'Rules': [
                    {
                        'Priority': 123,
                        'RuleId': 'string',
                        'Action': {
                            'Type': 'BLOCK'|'ALLOW'|'COUNT'
                        }
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **WebACL** *(dict) --* 

          Information about the  WebACL that you specified in the ``GetWebACL`` request. For more information, see the following topics:

           

           
          *  WebACL : Contains ``DefaultAction`` , ``MetricName`` , ``Name`` , an array of ``Rule`` objects, and ``WebACLId`` 
           
          * ``DefaultAction`` (Data type is  WafAction ): Contains ``Type`` 
           
          * ``Rules`` : Contains an array of ``ActivatedRule`` objects, which contain ``Action`` , ``Priority`` , and ``RuleId`` 
           
          * ``Action`` : Contains ``Type`` 
           

          
          

          - **WebACLId** *(string) --* 

            A unique identifier for a ``WebACL`` . You use ``WebACLId`` to get information about a ``WebACL`` (see  GetWebACL ), update a ``WebACL`` (see  UpdateWebACL ), and delete a ``WebACL`` from AWS WAF (see  DeleteWebACL ).

             

            ``WebACLId`` is returned by  CreateWebACL and by  ListWebACLs .

            
          

          - **Name** *(string) --* 

            A friendly name or description of the ``WebACL`` . You can't change the name of a ``WebACL`` after you create it.

            
          

          - **MetricName** *(string) --* 
          

          - **DefaultAction** *(dict) --* 

            The action to perform if none of the ``Rules`` contained in the ``WebACL`` match. The action is specified by the  WafAction object.

            
            

            - **Type** *(string) --* 

              Specifies how you want AWS WAF to respond to requests that match the settings in a ``Rule`` . Valid settings include the following:

               

               
              * ``ALLOW`` : AWS WAF allows requests
               
              * ``BLOCK`` : AWS WAF blocks requests
               
              * ``COUNT`` : AWS WAF increments a counter of the requests that match all of the conditions in the rule. AWS WAF then continues to inspect the web request based on the remaining rules in the web ACL. You can't specify ``COUNT`` for the default action for a ``WebACL`` .
               

              
        
          

          - **Rules** *(list) --* 

            An array that contains the action for each ``Rule`` in a ``WebACL`` , the priority of the ``Rule`` , and the ID of the ``Rule`` .

            
            

            - *(dict) --* 

              The ``ActivatedRule`` object in an  UpdateWebACL request specifies a ``Rule`` that you want to insert or delete, the priority of the ``Rule`` in the ``WebACL`` , and the action that you want AWS WAF to take when a web request matches the ``Rule`` (``ALLOW`` , ``BLOCK`` , or ``COUNT`` ).

               

              To specify whether to insert or delete a ``Rule`` , use the ``Action`` parameter in the  WebACLUpdate data type.

              
              

              - **Priority** *(integer) --* 

                Specifies the order in which the ``Rules`` in a ``WebACL`` are evaluated. Rules with a lower value for ``Priority`` are evaluated before ``Rules`` with a higher value. The value must be a unique integer. If you add multiple ``Rules`` to a ``WebACL`` , the values don't need to be consecutive.

                
              

              - **RuleId** *(string) --* 

                The ``RuleId`` for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  GetRule ), update a ``Rule`` (see  UpdateRule ), insert a ``Rule`` into a ``WebACL`` or delete a one from a ``WebACL`` (see  UpdateWebACL ), or delete a ``Rule`` from AWS WAF (see  DeleteRule ).

                 

                ``RuleId`` is returned by  CreateRule and by  ListRules .

                
              

              - **Action** *(dict) --* 

                Specifies the action that CloudFront or AWS WAF takes when a web request matches the conditions in the ``Rule`` . Valid values for ``Action`` include the following:

                 

                 
                * ``ALLOW`` : CloudFront responds with the requested object.
                 
                * ``BLOCK`` : CloudFront responds with an HTTP 403 (Forbidden) status code.
                 
                * ``COUNT`` : AWS WAF increments a counter of requests that match the conditions in the rule and then continues to inspect the web request based on the remaining rules in the web ACL. 
                 

                
                

                - **Type** *(string) --* 

                  Specifies how you want AWS WAF to respond to requests that match the settings in a ``Rule`` . Valid settings include the following:

                   

                   
                  * ``ALLOW`` : AWS WAF allows requests
                   
                  * ``BLOCK`` : AWS WAF blocks requests
                   
                  * ``COUNT`` : AWS WAF increments a counter of the requests that match all of the conditions in the rule. AWS WAF then continues to inspect the web request based on the remaining rules in the web ACL. You can't specify ``COUNT`` for the default action for a ``WebACL`` .
                   

                  
            
          
        
      
    

  .. py:method:: get_xss_match_set(**kwargs)

    

    Returns the  XssMatchSet that is specified by ``XssMatchSetId`` .

    

    **Request Syntax** 
    ::

      response = client.get_xss_match_set(
          XssMatchSetId='string'
      )
    :type XssMatchSetId: string
    :param XssMatchSetId: **[REQUIRED]** 

      The ``XssMatchSetId`` of the  XssMatchSet that you want to get. ``XssMatchSetId`` is returned by  CreateXssMatchSet and by  ListXssMatchSets .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'XssMatchSet': {
                'XssMatchSetId': 'string',
                'Name': 'string',
                'XssMatchTuples': [
                    {
                        'FieldToMatch': {
                            'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                            'Data': 'string'
                        },
                        'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to a  GetXssMatchSet request.

        
        

        - **XssMatchSet** *(dict) --* 

          Information about the  XssMatchSet that you specified in the ``GetXssMatchSet`` request. For more information, see the following topics:

           

           
          *  XssMatchSet : Contains ``Name`` , ``XssMatchSetId`` , and an array of ``XssMatchTuple`` objects
           
          *  XssMatchTuple : Each ``XssMatchTuple`` object contains ``FieldToMatch`` and ``TextTransformation`` 
           
          *  FieldToMatch : Contains ``Data`` and ``Type`` 
           

          
          

          - **XssMatchSetId** *(string) --* 

            A unique identifier for an ``XssMatchSet`` . You use ``XssMatchSetId`` to get information about an ``XssMatchSet`` (see  GetXssMatchSet ), update an ``XssMatchSet`` (see  UpdateXssMatchSet ), insert an ``XssMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete an ``XssMatchSet`` from AWS WAF (see  DeleteXssMatchSet ).

             

            ``XssMatchSetId`` is returned by  CreateXssMatchSet and by  ListXssMatchSets .

            
          

          - **Name** *(string) --* 

            The name, if any, of the ``XssMatchSet`` .

            
          

          - **XssMatchTuples** *(list) --* 

            Specifies the parts of web requests that you want to inspect for cross-site scripting attacks.

            
            

            - *(dict) --* 

              Specifies the part of a web request that you want AWS WAF to inspect for cross-site scripting attacks and, if you want AWS WAF to inspect a header, the name of the header.

              
              

              - **FieldToMatch** *(dict) --* 

                Specifies where in a web request to look for ``TargetString`` .

                
                

                - **Type** *(string) --* 

                  The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

                   

                   
                  * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
                   
                  * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
                   
                  * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
                   
                  * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
                   
                  * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
                   

                  
                

                - **Data** *(string) --* 

                  When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

                   

                  The name of the header is not case sensitive.

                  
            
              

              - **TextTransformation** *(string) --* 

                Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

                 

                **CMD_LINE** 

                 

                When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

                 

                 
                * Delete the following characters: \ " ' ^
                 
                * Delete spaces before the following characters: / (
                 
                * Replace the following characters with a space: , ;
                 
                * Replace multiple spaces with one space
                 
                * Convert uppercase letters (A-Z) to lowercase (a-z)
                 

                 

                **COMPRESS_WHITE_SPACE** 

                 

                Use this option to replace the following characters with a space character (decimal 32):

                 

                 
                * \f, formfeed, decimal 12
                 
                * \t, tab, decimal 9
                 
                * \n, newline, decimal 10
                 
                * \r, carriage return, decimal 13
                 
                * \v, vertical tab, decimal 11
                 
                * non-breaking space, decimal 160
                 

                 

                ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

                 

                **HTML_ENTITY_DECODE** 

                 

                Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

                 

                 
                * Replaces ``(ampersand)quot;`` with ``"`` 
                 
                * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
                 
                * Replaces ``(ampersand)lt;`` with a "less than" symbol
                 
                * Replaces ``(ampersand)gt;`` with ``>`` 
                 
                * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
                 
                * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
                 

                 

                **LOWERCASE** 

                 

                Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

                 

                **URL_DECODE** 

                 

                Use this option to decode a URL-encoded value.

                 

                **NONE** 

                 

                Specify ``NONE`` if you don't want to perform any text transformations.

                
          
        
      
    

  .. py:method:: list_byte_match_sets(**kwargs)

    

    Returns an array of  ByteMatchSetSummary objects.

    

    **Request Syntax** 
    ::

      response = client.list_byte_match_sets(
          NextMarker='string',
          Limit=123
      )
    :type NextMarker: string
    :param NextMarker: 

      If you specify a value for ``Limit`` and you have more ``ByteMatchSets`` than the value of ``Limit`` , AWS WAF returns a ``NextMarker`` value in the response that allows you to list another group of ``ByteMatchSets`` . For the second and subsequent ``ListByteMatchSets`` requests, specify the value of ``NextMarker`` from the previous response to get information about another batch of ``ByteMatchSets`` .

      

    
    :type Limit: integer
    :param Limit: **[REQUIRED]** 

      Specifies the number of ``ByteMatchSet`` objects that you want AWS WAF to return for this request. If you have more ``ByteMatchSets`` objects than the number you specify for ``Limit`` , the response includes a ``NextMarker`` value that you can use to get another batch of ``ByteMatchSet`` objects.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NextMarker': 'string',
            'ByteMatchSets': [
                {
                    'ByteMatchSetId': 'string',
                    'Name': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **NextMarker** *(string) --* 

          If you have more ``ByteMatchSet`` objects than the number that you specified for ``Limit`` in the request, the response includes a ``NextMarker`` value. To list more ``ByteMatchSet`` objects, submit another ``ListByteMatchSets`` request, and specify the ``NextMarker`` value from the response in the ``NextMarker`` value in the next request.

          
        

        - **ByteMatchSets** *(list) --* 

          An array of  ByteMatchSetSummary objects.

          
          

          - *(dict) --* 

            Returned by  ListByteMatchSets . Each ``ByteMatchSetSummary`` object includes the ``Name`` and ``ByteMatchSetId`` for one  ByteMatchSet .

            
            

            - **ByteMatchSetId** *(string) --* 

              The ``ByteMatchSetId`` for a ``ByteMatchSet`` . You use ``ByteMatchSetId`` to get information about a ``ByteMatchSet`` , update a ``ByteMatchSet`` , remove a ``ByteMatchSet`` from a ``Rule`` , and delete a ``ByteMatchSet`` from AWS WAF.

               

              ``ByteMatchSetId`` is returned by  CreateByteMatchSet and by  ListByteMatchSets .

              
            

            - **Name** *(string) --* 

              A friendly name or description of the  ByteMatchSet . You can't change ``Name`` after you create a ``ByteMatchSet`` .

              
        
      
    

  .. py:method:: list_ip_sets(**kwargs)

    

    Returns an array of  IPSetSummary objects in the response.

    

    **Request Syntax** 
    ::

      response = client.list_ip_sets(
          NextMarker='string',
          Limit=123
      )
    :type NextMarker: string
    :param NextMarker: 

      If you specify a value for ``Limit`` and you have more ``IPSets`` than the value of ``Limit`` , AWS WAF returns a ``NextMarker`` value in the response that allows you to list another group of ``IPSets`` . For the second and subsequent ``ListIPSets`` requests, specify the value of ``NextMarker`` from the previous response to get information about another batch of ``ByteMatchSets`` .

      

    
    :type Limit: integer
    :param Limit: **[REQUIRED]** 

      Specifies the number of ``IPSet`` objects that you want AWS WAF to return for this request. If you have more ``IPSet`` objects than the number you specify for ``Limit`` , the response includes a ``NextMarker`` value that you can use to get another batch of ``IPSet`` objects.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NextMarker': 'string',
            'IPSets': [
                {
                    'IPSetId': 'string',
                    'Name': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **NextMarker** *(string) --* 

          If you have more ``IPSet`` objects than the number that you specified for ``Limit`` in the request, the response includes a ``NextMarker`` value. To list more ``IPSet`` objects, submit another ``ListIPSets`` request, and specify the ``NextMarker`` value from the response in the ``NextMarker`` value in the next request.

          
        

        - **IPSets** *(list) --* 

          An array of  IPSetSummary objects.

          
          

          - *(dict) --* 

            Contains the identifier and the name of the ``IPSet`` .

            
            

            - **IPSetId** *(string) --* 

              The ``IPSetId`` for an  IPSet . You can use ``IPSetId`` in a  GetIPSet request to get detailed information about an  IPSet .

              
            

            - **Name** *(string) --* 

              A friendly name or description of the  IPSet . You can't change the name of an ``IPSet`` after you create it.

              
        
      
    

  .. py:method:: list_rules(**kwargs)

    

    Returns an array of  RuleSummary objects.

    

    **Request Syntax** 
    ::

      response = client.list_rules(
          NextMarker='string',
          Limit=123
      )
    :type NextMarker: string
    :param NextMarker: 

      If you specify a value for ``Limit`` and you have more ``Rules`` than the value of ``Limit`` , AWS WAF returns a ``NextMarker`` value in the response that allows you to list another group of ``Rules`` . For the second and subsequent ``ListRules`` requests, specify the value of ``NextMarker`` from the previous response to get information about another batch of ``Rules`` .

      

    
    :type Limit: integer
    :param Limit: **[REQUIRED]** 

      Specifies the number of ``Rules`` that you want AWS WAF to return for this request. If you have more ``Rules`` than the number that you specify for ``Limit`` , the response includes a ``NextMarker`` value that you can use to get another batch of ``Rules`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NextMarker': 'string',
            'Rules': [
                {
                    'RuleId': 'string',
                    'Name': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **NextMarker** *(string) --* 

          If you have more ``Rules`` than the number that you specified for ``Limit`` in the request, the response includes a ``NextMarker`` value. To list more ``Rules`` , submit another ``ListRules`` request, and specify the ``NextMarker`` value from the response in the ``NextMarker`` value in the next request.

          
        

        - **Rules** *(list) --* 

          An array of  RuleSummary objects.

          
          

          - *(dict) --* 

            Contains the identifier and the friendly name or description of the ``Rule`` .

            
            

            - **RuleId** *(string) --* 

              A unique identifier for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  GetRule ), update a ``Rule`` (see  UpdateRule ), insert a ``Rule`` into a ``WebACL`` or delete one from a ``WebACL`` (see  UpdateWebACL ), or delete a ``Rule`` from AWS WAF (see  DeleteRule ).

               

              ``RuleId`` is returned by  CreateRule and by  ListRules .

              
            

            - **Name** *(string) --* 

              A friendly name or description of the  Rule . You can't change the name of a ``Rule`` after you create it.

              
        
      
    

  .. py:method:: list_size_constraint_sets(**kwargs)

    

    Returns an array of  SizeConstraintSetSummary objects.

    

    **Request Syntax** 
    ::

      response = client.list_size_constraint_sets(
          NextMarker='string',
          Limit=123
      )
    :type NextMarker: string
    :param NextMarker: 

      If you specify a value for ``Limit`` and you have more ``SizeConstraintSets`` than the value of ``Limit`` , AWS WAF returns a ``NextMarker`` value in the response that allows you to list another group of ``SizeConstraintSets`` . For the second and subsequent ``ListSizeConstraintSets`` requests, specify the value of ``NextMarker`` from the previous response to get information about another batch of ``SizeConstraintSets`` .

      

    
    :type Limit: integer
    :param Limit: **[REQUIRED]** 

      Specifies the number of ``SizeConstraintSet`` objects that you want AWS WAF to return for this request. If you have more ``SizeConstraintSets`` objects than the number you specify for ``Limit`` , the response includes a ``NextMarker`` value that you can use to get another batch of ``SizeConstraintSet`` objects.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NextMarker': 'string',
            'SizeConstraintSets': [
                {
                    'SizeConstraintSetId': 'string',
                    'Name': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **NextMarker** *(string) --* 

          If you have more ``SizeConstraintSet`` objects than the number that you specified for ``Limit`` in the request, the response includes a ``NextMarker`` value. To list more ``SizeConstraintSet`` objects, submit another ``ListSizeConstraintSets`` request, and specify the ``NextMarker`` value from the response in the ``NextMarker`` value in the next request.

          
        

        - **SizeConstraintSets** *(list) --* 

          An array of  SizeConstraintSetSummary objects.

          
          

          - *(dict) --* 

            The ``Id`` and ``Name`` of a ``SizeConstraintSet`` .

            
            

            - **SizeConstraintSetId** *(string) --* 

              A unique identifier for a ``SizeConstraintSet`` . You use ``SizeConstraintSetId`` to get information about a ``SizeConstraintSet`` (see  GetSizeConstraintSet ), update a ``SizeConstraintSet`` (see  UpdateSizeConstraintSet ), insert a ``SizeConstraintSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete a ``SizeConstraintSet`` from AWS WAF (see  DeleteSizeConstraintSet ).

               

              ``SizeConstraintSetId`` is returned by  CreateSizeConstraintSet and by  ListSizeConstraintSets .

              
            

            - **Name** *(string) --* 

              The name of the ``SizeConstraintSet`` , if any.

              
        
      
    

  .. py:method:: list_sql_injection_match_sets(**kwargs)

    

    Returns an array of  SqlInjectionMatchSet objects.

    

    **Request Syntax** 
    ::

      response = client.list_sql_injection_match_sets(
          NextMarker='string',
          Limit=123
      )
    :type NextMarker: string
    :param NextMarker: 

      If you specify a value for ``Limit`` and you have more  SqlInjectionMatchSet objects than the value of ``Limit`` , AWS WAF returns a ``NextMarker`` value in the response that allows you to list another group of ``SqlInjectionMatchSets`` . For the second and subsequent ``ListSqlInjectionMatchSets`` requests, specify the value of ``NextMarker`` from the previous response to get information about another batch of ``SqlInjectionMatchSets`` .

      

    
    :type Limit: integer
    :param Limit: **[REQUIRED]** 

      Specifies the number of  SqlInjectionMatchSet objects that you want AWS WAF to return for this request. If you have more ``SqlInjectionMatchSet`` objects than the number you specify for ``Limit`` , the response includes a ``NextMarker`` value that you can use to get another batch of ``Rules`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NextMarker': 'string',
            'SqlInjectionMatchSets': [
                {
                    'SqlInjectionMatchSetId': 'string',
                    'Name': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to a  ListSqlInjectionMatchSets request.

        
        

        - **NextMarker** *(string) --* 

          If you have more  SqlInjectionMatchSet objects than the number that you specified for ``Limit`` in the request, the response includes a ``NextMarker`` value. To list more ``SqlInjectionMatchSet`` objects, submit another ``ListSqlInjectionMatchSets`` request, and specify the ``NextMarker`` value from the response in the ``NextMarker`` value in the next request.

          
        

        - **SqlInjectionMatchSets** *(list) --* 

          An array of  SqlInjectionMatchSetSummary objects.

          
          

          - *(dict) --* 

            The ``Id`` and ``Name`` of a ``SqlInjectionMatchSet`` .

            
            

            - **SqlInjectionMatchSetId** *(string) --* 

              A unique identifier for a ``SqlInjectionMatchSet`` . You use ``SqlInjectionMatchSetId`` to get information about a ``SqlInjectionMatchSet`` (see  GetSqlInjectionMatchSet ), update a ``SqlInjectionMatchSet`` (see  UpdateSqlInjectionMatchSet ), insert a ``SqlInjectionMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete a ``SqlInjectionMatchSet`` from AWS WAF (see  DeleteSqlInjectionMatchSet ).

               

              ``SqlInjectionMatchSetId`` is returned by  CreateSqlInjectionMatchSet and by  ListSqlInjectionMatchSets .

              
            

            - **Name** *(string) --* 

              The name of the ``SqlInjectionMatchSet`` , if any, specified by ``Id`` .

              
        
      
    

  .. py:method:: list_web_acls(**kwargs)

    

    Returns an array of  WebACLSummary objects in the response.

    

    **Request Syntax** 
    ::

      response = client.list_web_acls(
          NextMarker='string',
          Limit=123
      )
    :type NextMarker: string
    :param NextMarker: 

      If you specify a value for ``Limit`` and you have more ``WebACL`` objects than the number that you specify for ``Limit`` , AWS WAF returns a ``NextMarker`` value in the response that allows you to list another group of ``WebACL`` objects. For the second and subsequent ``ListWebACLs`` requests, specify the value of ``NextMarker`` from the previous response to get information about another batch of ``WebACL`` objects.

      

    
    :type Limit: integer
    :param Limit: **[REQUIRED]** 

      Specifies the number of ``WebACL`` objects that you want AWS WAF to return for this request. If you have more ``WebACL`` objects than the number that you specify for ``Limit`` , the response includes a ``NextMarker`` value that you can use to get another batch of ``WebACL`` objects.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NextMarker': 'string',
            'WebACLs': [
                {
                    'WebACLId': 'string',
                    'Name': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **NextMarker** *(string) --* 

          If you have more ``WebACL`` objects than the number that you specified for ``Limit`` in the request, the response includes a ``NextMarker`` value. To list more ``WebACL`` objects, submit another ``ListWebACLs`` request, and specify the ``NextMarker`` value from the response in the ``NextMarker`` value in the next request.

          
        

        - **WebACLs** *(list) --* 

          An array of  WebACLSummary objects.

          
          

          - *(dict) --* 

            Contains the identifier and the name or description of the  WebACL .

            
            

            - **WebACLId** *(string) --* 

              A unique identifier for a ``WebACL`` . You use ``WebACLId`` to get information about a ``WebACL`` (see  GetWebACL ), update a ``WebACL`` (see  UpdateWebACL ), and delete a ``WebACL`` from AWS WAF (see  DeleteWebACL ).

               

              ``WebACLId`` is returned by  CreateWebACL and by  ListWebACLs .

              
            

            - **Name** *(string) --* 

              A friendly name or description of the  WebACL . You can't change the name of a ``WebACL`` after you create it.

              
        
      
    

  .. py:method:: list_xss_match_sets(**kwargs)

    

    Returns an array of  XssMatchSet objects.

    

    **Request Syntax** 
    ::

      response = client.list_xss_match_sets(
          NextMarker='string',
          Limit=123
      )
    :type NextMarker: string
    :param NextMarker: 

      If you specify a value for ``Limit`` and you have more  XssMatchSet objects than the value of ``Limit`` , AWS WAF returns a ``NextMarker`` value in the response that allows you to list another group of ``XssMatchSets`` . For the second and subsequent ``ListXssMatchSets`` requests, specify the value of ``NextMarker`` from the previous response to get information about another batch of ``XssMatchSets`` .

      

    
    :type Limit: integer
    :param Limit: **[REQUIRED]** 

      Specifies the number of  XssMatchSet objects that you want AWS WAF to return for this request. If you have more ``XssMatchSet`` objects than the number you specify for ``Limit`` , the response includes a ``NextMarker`` value that you can use to get another batch of ``Rules`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NextMarker': 'string',
            'XssMatchSets': [
                {
                    'XssMatchSetId': 'string',
                    'Name': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to a  ListXssMatchSets request.

        
        

        - **NextMarker** *(string) --* 

          If you have more  XssMatchSet objects than the number that you specified for ``Limit`` in the request, the response includes a ``NextMarker`` value. To list more ``XssMatchSet`` objects, submit another ``ListXssMatchSets`` request, and specify the ``NextMarker`` value from the response in the ``NextMarker`` value in the next request.

          
        

        - **XssMatchSets** *(list) --* 

          An array of  XssMatchSetSummary objects.

          
          

          - *(dict) --* 

            The ``Id`` and ``Name`` of an ``XssMatchSet`` .

            
            

            - **XssMatchSetId** *(string) --* 

              A unique identifier for an ``XssMatchSet`` . You use ``XssMatchSetId`` to get information about a ``XssMatchSet`` (see  GetXssMatchSet ), update an ``XssMatchSet`` (see  UpdateXssMatchSet ), insert an ``XssMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  UpdateRule ), and delete an ``XssMatchSet`` from AWS WAF (see  DeleteXssMatchSet ).

               

              ``XssMatchSetId`` is returned by  CreateXssMatchSet and by  ListXssMatchSets .

              
            

            - **Name** *(string) --* 

              The name of the ``XssMatchSet`` , if any, specified by ``Id`` .

              
        
      
    

  .. py:method:: update_byte_match_set(**kwargs)

    

    Inserts or deletes  ByteMatchTuple objects (filters) in a  ByteMatchSet . For each ``ByteMatchTuple`` object, you specify the following values: 

     

     
    * Whether to insert or delete the object from the array. If you want to change a ``ByteMatchSetUpdate`` object, you delete the existing object and add a new one.
     
    * The part of a web request that you want AWS WAF to inspect, such as a query string or the value of the ``User-Agent`` header. 
     
    * The bytes (typically a string that corresponds with ASCII characters) that you want AWS WAF to look for. For more information, including how you specify the values for the AWS WAF API and the AWS CLI or SDKs, see ``TargetString`` in the  ByteMatchTuple data type. 
     
    * Where to look, such as at the beginning or the end of a query string.
     
    * Whether to perform any conversions on the request, such as converting it to lowercase, before inspecting it for the specified string.
     

     

    For example, you can add a ``ByteMatchSetUpdate`` object that matches web requests in which ``User-Agent`` headers contain the string ``BadBot`` . You can then configure AWS WAF to block those requests.

     

    To create and configure a ``ByteMatchSet`` , perform the following steps:

     

     
    * Create a ``ByteMatchSet.`` For more information, see  CreateByteMatchSet .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of an ``UpdateByteMatchSet`` request.
     
    * Submit an ``UpdateByteMatchSet`` request to specify the part of the request that you want AWS WAF to inspect (for example, the header or the URI) and the value that you want AWS WAF to watch for.
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.update_byte_match_set(
          ByteMatchSetId='string',
          ChangeToken='string',
          Updates=[
              {
                  'Action': 'INSERT'|'DELETE',
                  'ByteMatchTuple': {
                      'FieldToMatch': {
                          'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                          'Data': 'string'
                      },
                      'TargetString': b'bytes',
                      'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE',
                      'PositionalConstraint': 'EXACTLY'|'STARTS_WITH'|'ENDS_WITH'|'CONTAINS'|'CONTAINS_WORD'
                  }
              },
          ]
      )
    :type ByteMatchSetId: string
    :param ByteMatchSetId: **[REQUIRED]** 

      The ``ByteMatchSetId`` of the  ByteMatchSet that you want to update. ``ByteMatchSetId`` is returned by  CreateByteMatchSet and by  ListByteMatchSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    :type Updates: list
    :param Updates: **[REQUIRED]** 

      An array of ``ByteMatchSetUpdate`` objects that you want to insert into or delete from a  ByteMatchSet . For more information, see the applicable data types:

       

       
      *  ByteMatchSetUpdate : Contains ``Action`` and ``ByteMatchTuple`` 
       
      *  ByteMatchTuple : Contains ``FieldToMatch`` , ``PositionalConstraint`` , ``TargetString`` , and ``TextTransformation`` 
       
      *  FieldToMatch : Contains ``Data`` and ``Type`` 
       

      

    
      - *(dict) --* 

        In an  UpdateByteMatchSet request, ``ByteMatchSetUpdate`` specifies whether to insert or delete a  ByteMatchTuple and includes the settings for the ``ByteMatchTuple`` .

        

      
        - **Action** *(string) --* **[REQUIRED]** 

          Specifies whether to insert or delete a  ByteMatchTuple .

          

        
        - **ByteMatchTuple** *(dict) --* **[REQUIRED]** 

          Information about the part of a web request that you want AWS WAF to inspect and the value that you want AWS WAF to search for. If you specify ``DELETE`` for the value of ``Action`` , the ``ByteMatchTuple`` values must exactly match the values in the ``ByteMatchTuple`` that you want to delete from the ``ByteMatchSet`` .

          

        
          - **FieldToMatch** *(dict) --* **[REQUIRED]** 

            The part of a web request that you want AWS WAF to search, such as a specified header or a query string. For more information, see  FieldToMatch .

            

          
            - **Type** *(string) --* **[REQUIRED]** 

              The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

               

               
              * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
               
              * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
               
              * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
               
              * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
               
              * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
               

              

            
            - **Data** *(string) --* 

              When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

               

              The name of the header is not case sensitive.

              

            
          
          - **TargetString** *(bytes) --* **[REQUIRED]** 

            The value that you want AWS WAF to search for. AWS WAF searches for the specified string in the part of web requests that you specified in ``FieldToMatch`` . The maximum length of the value is 50 bytes.

             

            Valid values depend on the values that you specified for ``FieldToMatch`` :

             

             
            * ``HEADER`` : The value that you want AWS WAF to search for in the request header that you specified in  FieldToMatch , for example, the value of the ``User-Agent`` or ``Referer`` header.
             
            * ``METHOD`` : The HTTP method, which indicates the type of operation specified in the request. CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
             
            * ``QUERY_STRING`` : The value that you want AWS WAF to search for in the query string, which is the part of a URL that appears after a ``?`` character.
             
            * ``URI`` : The value that you want AWS WAF to search for in the part of a URL that identifies a resource, for example, ``/images/daily-ad.jpg`` .
             
            * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
             

             

            If ``TargetString`` includes alphabetic characters A-Z and a-z, note that the value is case sensitive.

             

            **If you're using the AWS WAF API** 

             

            Specify a base64-encoded version of the value. The maximum length of the value before you base64-encode it is 50 bytes. 

             

            For example, suppose the value of ``Type`` is ``HEADER`` and the value of ``Data`` is ``User-Agent`` . If you want to search the ``User-Agent`` header for the value ``BadBot`` , you base64-encode ``BadBot`` using MIME base64 encoding and include the resulting value, ``QmFkQm90`` , in the value of ``TargetString`` .

             

            **If you're using the AWS CLI or one of the AWS SDKs** 

             

            The value that you want AWS WAF to search for. The SDK automatically base64 encodes the value.

            

          
          - **TextTransformation** *(string) --* **[REQUIRED]** 

            Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``TargetString`` before inspecting a request for a match.

             

            **CMD_LINE** 

             

            When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

             

             
            * Delete the following characters: \ " ' ^
             
            * Delete spaces before the following characters: / (
             
            * Replace the following characters with a space: , ;
             
            * Replace multiple spaces with one space
             
            * Convert uppercase letters (A-Z) to lowercase (a-z)
             

             

            **COMPRESS_WHITE_SPACE** 

             

            Use this option to replace the following characters with a space character (decimal 32):

             

             
            * \f, formfeed, decimal 12
             
            * \t, tab, decimal 9
             
            * \n, newline, decimal 10
             
            * \r, carriage return, decimal 13
             
            * \v, vertical tab, decimal 11
             
            * non-breaking space, decimal 160
             

             

            ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

             

            **HTML_ENTITY_DECODE** 

             

            Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

             

             
            * Replaces ``(ampersand)quot;`` with ``"`` 
             
            * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
             
            * Replaces ``(ampersand)lt;`` with a "less than" symbol
             
            * Replaces ``(ampersand)gt;`` with ``>`` 
             
            * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
             
            * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
             

             

            **LOWERCASE** 

             

            Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

             

            **URL_DECODE** 

             

            Use this option to decode a URL-encoded value.

             

            **NONE** 

             

            Specify ``NONE`` if you don't want to perform any text transformations.

            

          
          - **PositionalConstraint** *(string) --* **[REQUIRED]** 

            Within the portion of a web request that you want to search (for example, in the query string, if any), specify where you want AWS WAF to search. Valid values include the following:

             

            **CONTAINS** 

             

            The specified part of the web request must include the value of ``TargetString`` , but the location doesn't matter.

             

            **CONTAINS_WORD** 

             

            The specified part of the web request must include the value of ``TargetString`` , and ``TargetString`` must contain only alphanumeric characters or underscore (A-Z, a-z, 0-9, or _). In addition, ``TargetString`` must be a word, which means one of the following:

             

             
            * ``TargetString`` exactly matches the value of the specified part of the web request, such as the value of a header.
             
            * ``TargetString`` is at the beginning of the specified part of the web request and is followed by a character other than an alphanumeric character or underscore (_), for example, ``BadBot;`` .
             
            * ``TargetString`` is at the end of the specified part of the web request and is preceded by a character other than an alphanumeric character or underscore (_), for example, ``;BadBot`` .
             
            * ``TargetString`` is in the middle of the specified part of the web request and is preceded and followed by characters other than alphanumeric characters or underscore (_), for example, ``-BadBot;`` .
             

             

            **EXACTLY** 

             

            The value of the specified part of the web request must exactly match the value of ``TargetString`` .

             

            **STARTS_WITH** 

             

            The value of ``TargetString`` must appear at the beginning of the specified part of the web request.

             

            **ENDS_WITH** 

             

            The value of ``TargetString`` must appear at the end of the specified part of the web request.

            

          
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``UpdateByteMatchSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: update_ip_set(**kwargs)

    

    Inserts or deletes  IPSetDescriptor objects in an ``IPSet`` . For each ``IPSetDescriptor`` object, you specify the following values: 

     

     
    * Whether to insert or delete the object from the array. If you want to change an ``IPSetDescriptor`` object, you delete the existing object and add a new one.
     
    * The IP address version, ``IPv4`` . 
     
    * The IP address in CIDR notation, for example, ``192.0.2.0/24`` (for the range of IP addresses from ``192.0.2.0`` to ``192.0.2.255`` ) or ``192.0.2.44/32`` (for the individual IP address ``192.0.2.44`` ). 
     

     

    AWS WAF supports /8, /16, /24, and /32 IP address ranges. For more information about CIDR notation, see the Wikipedia entry `Classless Inter-Domain Routing`_ .

     

    You use an ``IPSet`` to specify which web requests you want to allow or block based on the IP addresses that the requests originated from. For example, if you're receiving a lot of requests from one or a small number of IP addresses and you want to block the requests, you can create an ``IPSet`` that specifies those IP addresses, and then configure AWS WAF to block the requests. 

     

    To create and configure an ``IPSet`` , perform the following steps:

     

     
    * Submit a  CreateIPSet request.
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateIPSet request.
     
    * Submit an ``UpdateIPSet`` request to specify the IP addresses that you want AWS WAF to watch for.
     

     

    When you update an ``IPSet`` , you specify the IP addresses that you want to add and/or the IP addresses that you want to delete. If you want to change an IP address, you delete the existing IP address and add the new one.

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.update_ip_set(
          IPSetId='string',
          ChangeToken='string',
          Updates=[
              {
                  'Action': 'INSERT'|'DELETE',
                  'IPSetDescriptor': {
                      'Type': 'IPV4',
                      'Value': 'string'
                  }
              },
          ]
      )
    :type IPSetId: string
    :param IPSetId: **[REQUIRED]** 

      The ``IPSetId`` of the  IPSet that you want to update. ``IPSetId`` is returned by  CreateIPSet and by  ListIPSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    :type Updates: list
    :param Updates: **[REQUIRED]** 

      An array of ``IPSetUpdate`` objects that you want to insert into or delete from an  IPSet . For more information, see the applicable data types:

       

       
      *  IPSetUpdate : Contains ``Action`` and ``IPSetDescriptor`` 
       
      *  IPSetDescriptor : Contains ``Type`` and ``Value`` 
       

      

    
      - *(dict) --* 

        Specifies the type of update to perform to an  IPSet with  UpdateIPSet .

        

      
        - **Action** *(string) --* **[REQUIRED]** 

          Specifies whether to insert or delete an IP address with  UpdateIPSet .

          

        
        - **IPSetDescriptor** *(dict) --* **[REQUIRED]** 

          The IP address type (``IPV4`` ) and the IP address range (in CIDR notation) that web requests originate from.

          

        
          - **Type** *(string) --* **[REQUIRED]** 

            Specify ``IPV4`` .

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Specify an IPv4 address by using CIDR notation. For example:

             

             
            * To configure AWS WAF to allow, block, or count requests that originated from the IP address 192.0.2.44, specify ``192.0.2.44/32`` .
             
            * To configure AWS WAF to allow, block, or count requests that originated from IP addresses from 192.0.2.0 to 192.0.2.255, specify ``192.0.2.0/24`` .
             

             

            AWS WAF supports only /8, /16, /24, and /32 IP addresses.

             

            For more information about CIDR notation, see the Wikipedia entry `Classless Inter-Domain Routing`_ .

            

          
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``UpdateIPSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: update_rule(**kwargs)

    

    Inserts or deletes  Predicate objects in a ``Rule`` . Each ``Predicate`` object identifies a predicate, such as a  ByteMatchSet or an  IPSet , that specifies the web requests that you want to allow, block, or count. If you add more than one predicate to a ``Rule`` , a request must match all of the specifications to be allowed, blocked, or counted. For example, suppose you add the following to a ``Rule`` : 

     

     
    * A ``ByteMatchSet`` that matches the value ``BadBot`` in the ``User-Agent`` header
     
    * An ``IPSet`` that matches the IP address ``192.0.2.44`` 
     

     

    You then add the ``Rule`` to a ``WebACL`` and specify that you want to block requests that satisfy the ``Rule`` . For a request to be blocked, the ``User-Agent`` header in the request must contain the value ``BadBot``  *and* the request must originate from the IP address 192.0.2.44.

     

    To create and configure a ``Rule`` , perform the following steps:

     

     
    * Create and update the predicates that you want to include in the ``Rule`` .
     
    * Create the ``Rule`` . See  CreateRule .
     
    * Use ``GetChangeToken`` to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateRule request.
     
    * Submit an ``UpdateRule`` request to add predicates to the ``Rule`` .
     
    * Create and update a ``WebACL`` that contains the ``Rule`` . See  CreateWebACL .
     

     

    If you want to replace one ``ByteMatchSet`` or ``IPSet`` with another, you delete the existing one and add the new one.

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.update_rule(
          RuleId='string',
          ChangeToken='string',
          Updates=[
              {
                  'Action': 'INSERT'|'DELETE',
                  'Predicate': {
                      'Negated': True|False,
                      'Type': 'IPMatch'|'ByteMatch'|'SqlInjectionMatch'|'SizeConstraint'|'XssMatch',
                      'DataId': 'string'
                  }
              },
          ]
      )
    :type RuleId: string
    :param RuleId: **[REQUIRED]** 

      The ``RuleId`` of the ``Rule`` that you want to update. ``RuleId`` is returned by ``CreateRule`` and by  ListRules .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    :type Updates: list
    :param Updates: **[REQUIRED]** 

      An array of ``RuleUpdate`` objects that you want to insert into or delete from a  Rule . For more information, see the applicable data types:

       

       
      *  RuleUpdate : Contains ``Action`` and ``Predicate`` 
       
      *  Predicate : Contains ``DataId`` , ``Negated`` , and ``Type`` 
       
      *  FieldToMatch : Contains ``Data`` and ``Type`` 
       

      

    
      - *(dict) --* 

        Specifies a ``Predicate`` (such as an ``IPSet`` ) and indicates whether you want to add it to a ``Rule`` or delete it from a ``Rule`` .

        

      
        - **Action** *(string) --* **[REQUIRED]** 

          Specify ``INSERT`` to add a ``Predicate`` to a ``Rule`` . Use ``DELETE`` to remove a ``Predicate`` from a ``Rule`` .

          

        
        - **Predicate** *(dict) --* **[REQUIRED]** 

          The ID of the ``Predicate`` (such as an ``IPSet`` ) that you want to add to a ``Rule`` .

          

        
          - **Negated** *(boolean) --* **[REQUIRED]** 

            Set ``Negated`` to ``False`` if you want AWS WAF to allow, block, or count requests based on the settings in the specified  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow or block requests based on that IP address.

             

            Set ``Negated`` to ``True`` if you want AWS WAF to allow or block a request based on the negation of the settings in the  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow, block, or count requests based on all IP addresses *except*  ``192.0.2.44`` .

            

          
          - **Type** *(string) --* **[REQUIRED]** 

            The type of predicate in a ``Rule`` , such as ``ByteMatchSet`` or ``IPSet`` .

            

          
          - **DataId** *(string) --* **[REQUIRED]** 

            A unique identifier for a predicate in a ``Rule`` , such as ``ByteMatchSetId`` or ``IPSetId`` . The ID is returned by the corresponding ``Create`` or ``List`` command.

            

          
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``UpdateRule`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: update_size_constraint_set(**kwargs)

    

    Inserts or deletes  SizeConstraint objects (filters) in a  SizeConstraintSet . For each ``SizeConstraint`` object, you specify the following values: 

     

     
    * Whether to insert or delete the object from the array. If you want to change a ``SizeConstraintSetUpdate`` object, you delete the existing object and add a new one.
     
    * The part of a web request that you want AWS WAF to evaluate, such as the length of a query string or the length of the ``User-Agent`` header.
     
    * Whether to perform any transformations on the request, such as converting it to lowercase, before checking its length. Note that transformations of the request body are not supported because the AWS resource forwards only the first ``8192`` bytes of your request to AWS WAF.
     
    * A ``ComparisonOperator`` used for evaluating the selected part of the request against the specified ``Size`` , such as equals, greater than, less than, and so on.
     
    * The length, in bytes, that you want AWS WAF to watch for in selected part of the request. The length is computed after applying the transformation.
     

     

    For example, you can add a ``SizeConstraintSetUpdate`` object that matches web requests in which the length of the ``User-Agent`` header is greater than 100 bytes. You can then configure AWS WAF to block those requests.

     

    To create and configure a ``SizeConstraintSet`` , perform the following steps:

     

     
    * Create a ``SizeConstraintSet.`` For more information, see  CreateSizeConstraintSet .
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of an ``UpdateSizeConstraintSet`` request.
     
    * Submit an ``UpdateSizeConstraintSet`` request to specify the part of the request that you want AWS WAF to inspect (for example, the header or the URI) and the value that you want AWS WAF to watch for.
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.update_size_constraint_set(
          SizeConstraintSetId='string',
          ChangeToken='string',
          Updates=[
              {
                  'Action': 'INSERT'|'DELETE',
                  'SizeConstraint': {
                      'FieldToMatch': {
                          'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                          'Data': 'string'
                      },
                      'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE',
                      'ComparisonOperator': 'EQ'|'NE'|'LE'|'LT'|'GE'|'GT',
                      'Size': 123
                  }
              },
          ]
      )
    :type SizeConstraintSetId: string
    :param SizeConstraintSetId: **[REQUIRED]** 

      The ``SizeConstraintSetId`` of the  SizeConstraintSet that you want to update. ``SizeConstraintSetId`` is returned by  CreateSizeConstraintSet and by  ListSizeConstraintSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    :type Updates: list
    :param Updates: **[REQUIRED]** 

      An array of ``SizeConstraintSetUpdate`` objects that you want to insert into or delete from a  SizeConstraintSet . For more information, see the applicable data types:

       

       
      *  SizeConstraintSetUpdate : Contains ``Action`` and ``SizeConstraint`` 
       
      *  SizeConstraint : Contains ``FieldToMatch`` , ``TextTransformation`` , ``ComparisonOperator`` , and ``Size`` 
       
      *  FieldToMatch : Contains ``Data`` and ``Type`` 
       

      

    
      - *(dict) --* 

        Specifies the part of a web request that you want to inspect the size of and indicates whether you want to add the specification to a  SizeConstraintSet or delete it from a ``SizeConstraintSet`` .

        

      
        - **Action** *(string) --* **[REQUIRED]** 

          Specify ``INSERT`` to add a  SizeConstraintSetUpdate to a  SizeConstraintSet . Use ``DELETE`` to remove a ``SizeConstraintSetUpdate`` from a ``SizeConstraintSet`` .

          

        
        - **SizeConstraint** *(dict) --* **[REQUIRED]** 

          Specifies a constraint on the size of a part of the web request. AWS WAF uses the ``Size`` , ``ComparisonOperator`` , and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

          

        
          - **FieldToMatch** *(dict) --* **[REQUIRED]** 

            Specifies where in a web request to look for ``TargetString`` .

            

          
            - **Type** *(string) --* **[REQUIRED]** 

              The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

               

               
              * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
               
              * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
               
              * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
               
              * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
               
              * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
               

              

            
            - **Data** *(string) --* 

              When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

               

              The name of the header is not case sensitive.

              

            
          
          - **TextTransformation** *(string) --* **[REQUIRED]** 

            Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

             

            Note that if you choose ``BODY`` for the value of ``Type`` , you must choose ``NONE`` for ``TextTransformation`` because CloudFront forwards only the first 8192 bytes for inspection. 

             

            **NONE** 

             

            Specify ``NONE`` if you don't want to perform any text transformations.

             

            **CMD_LINE** 

             

            When you're concerned that attackers are injecting an operating system command line command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

             

             
            * Delete the following characters: \ " ' ^
             
            * Delete spaces before the following characters: / (
             
            * Replace the following characters with a space: , ;
             
            * Replace multiple spaces with one space
             
            * Convert uppercase letters (A-Z) to lowercase (a-z)
             

             

            **COMPRESS_WHITE_SPACE** 

             

            Use this option to replace the following characters with a space character (decimal 32):

             

             
            * \f, formfeed, decimal 12
             
            * \t, tab, decimal 9
             
            * \n, newline, decimal 10
             
            * \r, carriage return, decimal 13
             
            * \v, vertical tab, decimal 11
             
            * non-breaking space, decimal 160
             

             

            ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

             

            **HTML_ENTITY_DECODE** 

             

            Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

             

             
            * Replaces ``(ampersand)quot;`` with ``"`` 
             
            * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
             
            * Replaces ``(ampersand)lt;`` with a "less than" symbol
             
            * Replaces ``(ampersand)gt;`` with ``>`` 
             
            * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
             
            * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
             

             

            **LOWERCASE** 

             

            Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

             

            **URL_DECODE** 

             

            Use this option to decode a URL-encoded value.

            

          
          - **ComparisonOperator** *(string) --* **[REQUIRED]** 

            The type of comparison you want AWS WAF to perform. AWS WAF uses this in combination with the provided ``Size`` and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

             

            **EQ** : Used to test if the ``Size`` is equal to the size of the ``FieldToMatch`` 

             

            **NE** : Used to test if the ``Size`` is not equal to the size of the ``FieldToMatch`` 

             

            **LE** : Used to test if the ``Size`` is less than or equal to the size of the ``FieldToMatch`` 

             

            **LT** : Used to test if the ``Size`` is strictly less than the size of the ``FieldToMatch`` 

             

            **GE** : Used to test if the ``Size`` is greater than or equal to the size of the ``FieldToMatch`` 

             

            **GT** : Used to test if the ``Size`` is strictly greater than the size of the ``FieldToMatch`` 

            

          
          - **Size** *(integer) --* **[REQUIRED]** 

            The size in bytes that you want AWS WAF to compare against the size of the specified ``FieldToMatch`` . AWS WAF uses this in combination with ``ComparisonOperator`` and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

             

            Valid values for size are 0 - 21474836480 bytes (0 - 20 GB). 

             

            If you specify ``URI`` for the value of ``Type`` , the / in the URI counts as one character. For example, the URI ``/logo.jpg`` is nine characters long.

            

          
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``UpdateSizeConstraintSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: update_sql_injection_match_set(**kwargs)

    

    Inserts or deletes  SqlInjectionMatchTuple objects (filters) in a  SqlInjectionMatchSet . For each ``SqlInjectionMatchTuple`` object, you specify the following values:

     

     
    * ``Action`` : Whether to insert the object into or delete the object from the array. To change a ``SqlInjectionMatchTuple`` , you delete the existing object and add a new one.
     
    * ``FieldToMatch`` : The part of web requests that you want AWS WAF to inspect and, if you want AWS WAF to inspect a header, the name of the header.
     
    * ``TextTransformation`` : Which text transformation, if any, to perform on the web request before inspecting the request for snippets of malicious SQL code.
     

     

    You use ``SqlInjectionMatchSet`` objects to specify which CloudFront requests you want to allow, block, or count. For example, if you're receiving requests that contain snippets of SQL code in the query string and you want to block the requests, you can create a ``SqlInjectionMatchSet`` with the applicable settings, and then configure AWS WAF to block the requests. 

     

    To create and configure a ``SqlInjectionMatchSet`` , perform the following steps:

     

     
    * Submit a  CreateSqlInjectionMatchSet request.
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateIPSet request.
     
    * Submit an ``UpdateSqlInjectionMatchSet`` request to specify the parts of web requests that you want AWS WAF to inspect for snippets of SQL code.
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.update_sql_injection_match_set(
          SqlInjectionMatchSetId='string',
          ChangeToken='string',
          Updates=[
              {
                  'Action': 'INSERT'|'DELETE',
                  'SqlInjectionMatchTuple': {
                      'FieldToMatch': {
                          'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                          'Data': 'string'
                      },
                      'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE'
                  }
              },
          ]
      )
    :type SqlInjectionMatchSetId: string
    :param SqlInjectionMatchSetId: **[REQUIRED]** 

      The ``SqlInjectionMatchSetId`` of the ``SqlInjectionMatchSet`` that you want to update. ``SqlInjectionMatchSetId`` is returned by  CreateSqlInjectionMatchSet and by  ListSqlInjectionMatchSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    :type Updates: list
    :param Updates: **[REQUIRED]** 

      An array of ``SqlInjectionMatchSetUpdate`` objects that you want to insert into or delete from a  SqlInjectionMatchSet . For more information, see the applicable data types:

       

       
      *  SqlInjectionMatchSetUpdate : Contains ``Action`` and ``SqlInjectionMatchTuple`` 
       
      *  SqlInjectionMatchTuple : Contains ``FieldToMatch`` and ``TextTransformation`` 
       
      *  FieldToMatch : Contains ``Data`` and ``Type`` 
       

      

    
      - *(dict) --* 

        Specifies the part of a web request that you want to inspect for snippets of malicious SQL code and indicates whether you want to add the specification to a  SqlInjectionMatchSet or delete it from a ``SqlInjectionMatchSet`` .

        

      
        - **Action** *(string) --* **[REQUIRED]** 

          Specify ``INSERT`` to add a  SqlInjectionMatchSetUpdate to a  SqlInjectionMatchSet . Use ``DELETE`` to remove a ``SqlInjectionMatchSetUpdate`` from a ``SqlInjectionMatchSet`` .

          

        
        - **SqlInjectionMatchTuple** *(dict) --* **[REQUIRED]** 

          Specifies the part of a web request that you want AWS WAF to inspect for snippets of malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.

          

        
          - **FieldToMatch** *(dict) --* **[REQUIRED]** 

            Specifies where in a web request to look for ``TargetString`` .

            

          
            - **Type** *(string) --* **[REQUIRED]** 

              The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

               

               
              * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
               
              * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
               
              * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
               
              * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
               
              * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
               

              

            
            - **Data** *(string) --* 

              When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

               

              The name of the header is not case sensitive.

              

            
          
          - **TextTransformation** *(string) --* **[REQUIRED]** 

            Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

             

            **CMD_LINE** 

             

            When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

             

             
            * Delete the following characters: \ " ' ^
             
            * Delete spaces before the following characters: / (
             
            * Replace the following characters with a space: , ;
             
            * Replace multiple spaces with one space
             
            * Convert uppercase letters (A-Z) to lowercase (a-z)
             

             

            **COMPRESS_WHITE_SPACE** 

             

            Use this option to replace the following characters with a space character (decimal 32):

             

             
            * \f, formfeed, decimal 12
             
            * \t, tab, decimal 9
             
            * \n, newline, decimal 10
             
            * \r, carriage return, decimal 13
             
            * \v, vertical tab, decimal 11
             
            * non-breaking space, decimal 160
             

             

            ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

             

            **HTML_ENTITY_DECODE** 

             

            Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

             

             
            * Replaces ``(ampersand)quot;`` with ``"`` 
             
            * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
             
            * Replaces ``(ampersand)lt;`` with a "less than" symbol
             
            * Replaces ``(ampersand)gt;`` with ``>`` 
             
            * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
             
            * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
             

             

            **LOWERCASE** 

             

            Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

             

            **URL_DECODE** 

             

            Use this option to decode a URL-encoded value.

             

            **NONE** 

             

            Specify ``NONE`` if you don't want to perform any text transformations.

            

          
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to an  UpdateSqlInjectionMatchSets request.

        
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``UpdateSqlInjectionMatchSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: update_web_acl(**kwargs)

    

    Inserts or deletes  ActivatedRule objects in a ``WebACL`` . Each ``Rule`` identifies web requests that you want to allow, block, or count. When you update a ``WebACL`` , you specify the following values:

     

     
    * A default action for the ``WebACL`` , either ``ALLOW`` or ``BLOCK`` . AWS WAF performs the default action if a request doesn't match the criteria in any of the ``Rules`` in a ``WebACL`` .
     
    * The ``Rules`` that you want to add and/or delete. If you want to replace one ``Rule`` with another, you delete the existing ``Rule`` and add the new one.
     
    * For each ``Rule`` , whether you want AWS WAF to allow requests, block requests, or count requests that match the conditions in the ``Rule`` .
     
    * The order in which you want AWS WAF to evaluate the ``Rules`` in a ``WebACL`` . If you add more than one ``Rule`` to a ``WebACL`` , AWS WAF evaluates each request against the ``Rules`` in order based on the value of ``Priority`` . (The ``Rule`` that has the lowest value for ``Priority`` is evaluated first.) When a web request matches all of the predicates (such as ``ByteMatchSets`` and ``IPSets`` ) in a ``Rule`` , AWS WAF immediately takes the corresponding action, allow or block, and doesn't evaluate the request against the remaining ``Rules`` in the ``WebACL`` , if any. 
     
    * The CloudFront distribution that you want to associate with the ``WebACL`` .
     

     

    To create and configure a ``WebACL`` , perform the following steps:

     

     
    * Create and update the predicates that you want to include in ``Rules`` . For more information, see  CreateByteMatchSet ,  UpdateByteMatchSet ,  CreateIPSet ,  UpdateIPSet ,  CreateSqlInjectionMatchSet , and  UpdateSqlInjectionMatchSet .
     
    * Create and update the ``Rules`` that you want to include in the ``WebACL`` . For more information, see  CreateRule and  UpdateRule .
     
    * Create a ``WebACL`` . See  CreateWebACL .
     
    * Use ``GetChangeToken`` to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateWebACL request.
     
    * Submit an ``UpdateWebACL`` request to specify the ``Rules`` that you want to include in the ``WebACL`` , to specify the default action, and to associate the ``WebACL`` with a CloudFront distribution. 
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.update_web_acl(
          WebACLId='string',
          ChangeToken='string',
          Updates=[
              {
                  'Action': 'INSERT'|'DELETE',
                  'ActivatedRule': {
                      'Priority': 123,
                      'RuleId': 'string',
                      'Action': {
                          'Type': 'BLOCK'|'ALLOW'|'COUNT'
                      }
                  }
              },
          ],
          DefaultAction={
              'Type': 'BLOCK'|'ALLOW'|'COUNT'
          }
      )
    :type WebACLId: string
    :param WebACLId: **[REQUIRED]** 

      The ``WebACLId`` of the  WebACL that you want to update. ``WebACLId`` is returned by  CreateWebACL and by  ListWebACLs .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    :type Updates: list
    :param Updates: 

      An array of updates to make to the  WebACL .

       

      An array of ``WebACLUpdate`` objects that you want to insert into or delete from a  WebACL . For more information, see the applicable data types:

       

       
      *  WebACLUpdate : Contains ``Action`` and ``ActivatedRule`` 
       
      *  ActivatedRule : Contains ``Action`` , ``Priority`` , and ``RuleId`` 
       
      *  WafAction : Contains ``Type`` 
       

      

    
      - *(dict) --* 

        Specifies whether to insert a ``Rule`` into or delete a ``Rule`` from a ``WebACL`` .

        

      
        - **Action** *(string) --* **[REQUIRED]** 

          Specifies whether to insert a ``Rule`` into or delete a ``Rule`` from a ``WebACL`` .

          

        
        - **ActivatedRule** *(dict) --* **[REQUIRED]** 

          The ``ActivatedRule`` object in an  UpdateWebACL request specifies a ``Rule`` that you want to insert or delete, the priority of the ``Rule`` in the ``WebACL`` , and the action that you want AWS WAF to take when a web request matches the ``Rule`` (``ALLOW`` , ``BLOCK`` , or ``COUNT`` ).

           

          To specify whether to insert or delete a ``Rule`` , use the ``Action`` parameter in the  WebACLUpdate data type.

          

        
          - **Priority** *(integer) --* **[REQUIRED]** 

            Specifies the order in which the ``Rules`` in a ``WebACL`` are evaluated. Rules with a lower value for ``Priority`` are evaluated before ``Rules`` with a higher value. The value must be a unique integer. If you add multiple ``Rules`` to a ``WebACL`` , the values don't need to be consecutive.

            

          
          - **RuleId** *(string) --* **[REQUIRED]** 

            The ``RuleId`` for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  GetRule ), update a ``Rule`` (see  UpdateRule ), insert a ``Rule`` into a ``WebACL`` or delete a one from a ``WebACL`` (see  UpdateWebACL ), or delete a ``Rule`` from AWS WAF (see  DeleteRule ).

             

            ``RuleId`` is returned by  CreateRule and by  ListRules .

            

          
          - **Action** *(dict) --* **[REQUIRED]** 

            Specifies the action that CloudFront or AWS WAF takes when a web request matches the conditions in the ``Rule`` . Valid values for ``Action`` include the following:

             

             
            * ``ALLOW`` : CloudFront responds with the requested object.
             
            * ``BLOCK`` : CloudFront responds with an HTTP 403 (Forbidden) status code.
             
            * ``COUNT`` : AWS WAF increments a counter of requests that match the conditions in the rule and then continues to inspect the web request based on the remaining rules in the web ACL. 
             

            

          
            - **Type** *(string) --* **[REQUIRED]** 

              Specifies how you want AWS WAF to respond to requests that match the settings in a ``Rule`` . Valid settings include the following:

               

               
              * ``ALLOW`` : AWS WAF allows requests
               
              * ``BLOCK`` : AWS WAF blocks requests
               
              * ``COUNT`` : AWS WAF increments a counter of the requests that match all of the conditions in the rule. AWS WAF then continues to inspect the web request based on the remaining rules in the web ACL. You can't specify ``COUNT`` for the default action for a ``WebACL`` .
               

              

            
          
        
      
  
    :type DefaultAction: dict
    :param DefaultAction: 

      For the action that is associated with a rule in a ``WebACL`` , specifies the action that you want AWS WAF to perform when a web request matches all of the conditions in a rule. For the default action in a ``WebACL`` , specifies the action that you want AWS WAF to take when a web request doesn't match all of the conditions in any of the rules in a ``WebACL`` . 

      

    
      - **Type** *(string) --* **[REQUIRED]** 

        Specifies how you want AWS WAF to respond to requests that match the settings in a ``Rule`` . Valid settings include the following:

         

         
        * ``ALLOW`` : AWS WAF allows requests
         
        * ``BLOCK`` : AWS WAF blocks requests
         
        * ``COUNT`` : AWS WAF increments a counter of the requests that match all of the conditions in the rule. AWS WAF then continues to inspect the web request based on the remaining rules in the web ACL. You can't specify ``COUNT`` for the default action for a ``WebACL`` .
         

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``UpdateWebACL`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    

  .. py:method:: update_xss_match_set(**kwargs)

    

    Inserts or deletes  XssMatchTuple objects (filters) in an  XssMatchSet . For each ``XssMatchTuple`` object, you specify the following values:

     

     
    * ``Action`` : Whether to insert the object into or delete the object from the array. To change a ``XssMatchTuple`` , you delete the existing object and add a new one.
     
    * ``FieldToMatch`` : The part of web requests that you want AWS WAF to inspect and, if you want AWS WAF to inspect a header, the name of the header.
     
    * ``TextTransformation`` : Which text transformation, if any, to perform on the web request before inspecting the request for cross-site scripting attacks.
     

     

    You use ``XssMatchSet`` objects to specify which CloudFront requests you want to allow, block, or count. For example, if you're receiving requests that contain cross-site scripting attacks in the request body and you want to block the requests, you can create an ``XssMatchSet`` with the applicable settings, and then configure AWS WAF to block the requests. 

     

    To create and configure an ``XssMatchSet`` , perform the following steps:

     

     
    * Submit a  CreateXssMatchSet request.
     
    * Use  GetChangeToken to get the change token that you provide in the ``ChangeToken`` parameter of an  UpdateIPSet request.
     
    * Submit an ``UpdateXssMatchSet`` request to specify the parts of web requests that you want AWS WAF to inspect for cross-site scripting attacks.
     

     

    For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .

    

    **Request Syntax** 
    ::

      response = client.update_xss_match_set(
          XssMatchSetId='string',
          ChangeToken='string',
          Updates=[
              {
                  'Action': 'INSERT'|'DELETE',
                  'XssMatchTuple': {
                      'FieldToMatch': {
                          'Type': 'URI'|'QUERY_STRING'|'HEADER'|'METHOD'|'BODY',
                          'Data': 'string'
                      },
                      'TextTransformation': 'NONE'|'COMPRESS_WHITE_SPACE'|'HTML_ENTITY_DECODE'|'LOWERCASE'|'CMD_LINE'|'URL_DECODE'
                  }
              },
          ]
      )
    :type XssMatchSetId: string
    :param XssMatchSetId: **[REQUIRED]** 

      The ``XssMatchSetId`` of the ``XssMatchSet`` that you want to update. ``XssMatchSetId`` is returned by  CreateXssMatchSet and by  ListXssMatchSets .

      

    
    :type ChangeToken: string
    :param ChangeToken: **[REQUIRED]** 

      The value returned by the most recent call to  GetChangeToken .

      

    
    :type Updates: list
    :param Updates: **[REQUIRED]** 

      An array of ``XssMatchSetUpdate`` objects that you want to insert into or delete from a  XssMatchSet . For more information, see the applicable data types:

       

       
      *  XssMatchSetUpdate : Contains ``Action`` and ``XssMatchTuple`` 
       
      *  XssMatchTuple : Contains ``FieldToMatch`` and ``TextTransformation`` 
       
      *  FieldToMatch : Contains ``Data`` and ``Type`` 
       

      

    
      - *(dict) --* 

        Specifies the part of a web request that you want to inspect for cross-site scripting attacks and indicates whether you want to add the specification to an  XssMatchSet or delete it from an ``XssMatchSet`` .

        

      
        - **Action** *(string) --* **[REQUIRED]** 

          Specify ``INSERT`` to add a  XssMatchSetUpdate to an  XssMatchSet . Use ``DELETE`` to remove a ``XssMatchSetUpdate`` from an ``XssMatchSet`` .

          

        
        - **XssMatchTuple** *(dict) --* **[REQUIRED]** 

          Specifies the part of a web request that you want AWS WAF to inspect for cross-site scripting attacks and, if you want AWS WAF to inspect a header, the name of the header.

          

        
          - **FieldToMatch** *(dict) --* **[REQUIRED]** 

            Specifies where in a web request to look for ``TargetString`` .

            

          
            - **Type** *(string) --* **[REQUIRED]** 

              The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

               

               
              * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` .
               
              * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` .
               
              * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any.
               
              * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` .
               
              * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  CreateSizeConstraintSet . 
               

              

            
            - **Data** *(string) --* 

              When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

               

              The name of the header is not case sensitive.

              

            
          
          - **TextTransformation** *(string) --* **[REQUIRED]** 

            Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

             

            **CMD_LINE** 

             

            When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

             

             
            * Delete the following characters: \ " ' ^
             
            * Delete spaces before the following characters: / (
             
            * Replace the following characters with a space: , ;
             
            * Replace multiple spaces with one space
             
            * Convert uppercase letters (A-Z) to lowercase (a-z)
             

             

            **COMPRESS_WHITE_SPACE** 

             

            Use this option to replace the following characters with a space character (decimal 32):

             

             
            * \f, formfeed, decimal 12
             
            * \t, tab, decimal 9
             
            * \n, newline, decimal 10
             
            * \r, carriage return, decimal 13
             
            * \v, vertical tab, decimal 11
             
            * non-breaking space, decimal 160
             

             

            ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

             

            **HTML_ENTITY_DECODE** 

             

            Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

             

             
            * Replaces ``(ampersand)quot;`` with ``"`` 
             
            * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160
             
            * Replaces ``(ampersand)lt;`` with a "less than" symbol
             
            * Replaces ``(ampersand)gt;`` with ``>`` 
             
            * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters
             
            * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters
             

             

            **LOWERCASE** 

             

            Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

             

            **URL_DECODE** 

             

            Use this option to decode a URL-encoded value.

             

            **NONE** 

             

            Specify ``NONE`` if you don't want to perform any text transformations.

            

          
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ChangeToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The response to an  UpdateXssMatchSets request.

        
        

        - **ChangeToken** *(string) --* 

          The ``ChangeToken`` that you used to submit the ``UpdateXssMatchSet`` request. You can also use this value to query the status of the request. For more information, see  GetChangeTokenStatus .

          
    