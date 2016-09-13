

.. _"Renewal, restoration, and deletion times": http://wiki.gandi.net/en/domains/renew#renewal_restoration_and_deletion_times
.. _Domains that You Can Register with Amazon Route 53: http://docs.aws.amazon.com/console/route53/domain-tld-list
.. _Gandi privacy features: http://www.gandi.net/domain/whois/?currency=USD&amp;lang=en
.. _Transferring Registration for a Domain to Amazon Route 53: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-transfer-to-route-53.html
.. _ICANN website: https://www.icann.org/
.. _Amazon Route 53 Pricing: http://aws.amazon.com/route53/pricing/
.. _Renewing Registration for a Domain: http://docs.aws.amazon.com/console/route53/domain-renew


**************
Route53Domains
**************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: Route53Domains.Client

  A low-level client representing Amazon Route 53 Domains::

    
    import boto3
    
    client = boto3.client('route53domains')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`check_domain_availability`

  
  *   :py:meth:`delete_tags_for_domain`

  
  *   :py:meth:`disable_domain_auto_renew`

  
  *   :py:meth:`disable_domain_transfer_lock`

  
  *   :py:meth:`enable_domain_auto_renew`

  
  *   :py:meth:`enable_domain_transfer_lock`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_contact_reachability_status`

  
  *   :py:meth:`get_domain_detail`

  
  *   :py:meth:`get_domain_suggestions`

  
  *   :py:meth:`get_operation_detail`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_domains`

  
  *   :py:meth:`list_operations`

  
  *   :py:meth:`list_tags_for_domain`

  
  *   :py:meth:`register_domain`

  
  *   :py:meth:`renew_domain`

  
  *   :py:meth:`resend_contact_reachability_email`

  
  *   :py:meth:`retrieve_domain_auth_code`

  
  *   :py:meth:`transfer_domain`

  
  *   :py:meth:`update_domain_contact`

  
  *   :py:meth:`update_domain_contact_privacy`

  
  *   :py:meth:`update_domain_nameservers`

  
  *   :py:meth:`update_tags_for_domain`

  
  *   :py:meth:`view_billing`

  

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


  .. py:method:: check_domain_availability(**kwargs)

    

    This operation checks the availability of one domain name. Note that if the availability status of a domain is pending, you must submit another request to determine the availability of the domain name.

    

    **Request Syntax** 
    ::

      response = client.check_domain_availability(
          DomainName='string',
          IdnLangCode='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    :type IdnLangCode: string
    :param IdnLangCode: 

      Reserved for future use.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Availability': 'AVAILABLE'|'AVAILABLE_RESERVED'|'AVAILABLE_PREORDER'|'UNAVAILABLE'|'UNAVAILABLE_PREMIUM'|'UNAVAILABLE_RESTRICTED'|'RESERVED'|'DONT_KNOW'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The CheckDomainAvailability response includes the following elements.

        
        

        - **Availability** *(string) --* 

          Whether the domain name is available for registering.

           

          .. note::

             

            You can only register domains designated as ``AVAILABLE`` .

             

           

          Type: String

           

          Valid values:

           

           
          * ``AVAILABLE`` – The domain name is available.
           
          * ``AVAILABLE_RESERVED`` – The domain name is reserved under specific conditions.
           
          * ``AVAILABLE_PREORDER`` – The domain name is available and can be preordered.
           
          * ``UNAVAILABLE`` – The domain name is not available.
           
          * ``UNAVAILABLE_PREMIUM`` – The domain name is not available.
           
          * ``UNAVAILABLE_RESTRICTED`` – The domain name is forbidden.
           
          * ``RESERVED`` – The domain name has been reserved for another person or organization.
           
          * ``DONT_KNOW`` – The TLD registry didn't reply with a definitive answer about whether the domain name is available. Amazon Route 53 can return this response for a variety of reasons, for example, the registry is performing maintenance. Try again later.
           

          
    

  .. py:method:: delete_tags_for_domain(**kwargs)

    

    This operation deletes the specified tags for a domain.

     

    All tag operations are eventually consistent; subsequent operations may not immediately represent all issued operations.

    

    **Request Syntax** 
    ::

      response = client.delete_tags_for_domain(
          DomainName='string',
          TagsToDelete=[
              'string',
          ]
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The domain for which you want to delete one or more tags.

       

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Hyphens are allowed only when theyre surrounded by letters, numbers, or other hyphens. You cant specify a hyphen at the beginning or end of a label. To specify an Internationalized Domain Name, you must convert the name to Punycode.

       

      Required: Yes

      

    
    :type TagsToDelete: list
    :param TagsToDelete: **[REQUIRED]** 

      A list of tag keys to delete.

       

      Type: A list that contains the keys of the tags that you want to delete.

       

      Default: None

       

      Required: No

      '>

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: disable_domain_auto_renew(**kwargs)

    

    This operation disables automatic renewal of domain registration for the specified domain.

    

    **Request Syntax** 
    ::

      response = client.disable_domain_auto_renew(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: disable_domain_transfer_lock(**kwargs)

    

    This operation removes the transfer lock on the domain (specifically the ``clientTransferProhibited`` status) to allow domain transfers. We recommend you refrain from performing this action unless you intend to transfer the domain to a different registrar. Successful submission returns an operation ID that you can use to track the progress and completion of the action. If the request is not completed successfully, the domain registrant will be notified by email.

    

    **Request Syntax** 
    ::

      response = client.disable_domain_transfer_lock(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OperationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The DisableDomainTransferLock response includes the following element.

        
        

        - **OperationId** *(string) --* 

          Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

           

          Type: String

           

          Default: None

           

          Constraints: Maximum 255 characters.

          
    

  .. py:method:: enable_domain_auto_renew(**kwargs)

    

    This operation configures Amazon Route 53 to automatically renew the specified domain before the domain registration expires. The cost of renewing your domain registration is billed to your AWS account.

     

    The period during which you can renew a domain name varies by TLD. For a list of TLDs and their renewal policies, see `"Renewal, restoration, and deletion times"`_ on the website for our registrar partner, Gandi. Route 53 requires that you renew before the end of the renewal period that is listed on the Gandi website so we can complete processing before the deadline.

    

    **Request Syntax** 
    ::

      response = client.enable_domain_auto_renew(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: enable_domain_transfer_lock(**kwargs)

    

    This operation sets the transfer lock on the domain (specifically the ``clientTransferProhibited`` status) to prevent domain transfers. Successful submission returns an operation ID that you can use to track the progress and completion of the action. If the request is not completed successfully, the domain registrant will be notified by email.

    

    **Request Syntax** 
    ::

      response = client.enable_domain_transfer_lock(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OperationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The EnableDomainTransferLock response includes the following elements.

        
        

        - **OperationId** *(string) --* 

          Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

           

          Type: String

           

          Default: None

           

          Constraints: Maximum 255 characters.

          
    

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


  .. py:method:: get_contact_reachability_status(**kwargs)

    

    For operations that require confirmation that the email address for the registrant contact is valid, such as registering a new domain, this operation returns information about whether the registrant contact has responded.

     

    If you want us to resend the email, use the ``ResendContactReachabilityEmail`` operation.

    

    **Request Syntax** 
    ::

      response = client.get_contact_reachability_status(
          domainName='string'
      )
    :type domainName: string
    :param domainName: 

      The name of the domain for which you want to know whether the registrant contact has confirmed that the email address is valid.

       

      Type: String

       

      Default: None

       

      Required: Yes

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'domainName': 'string',
            'status': 'PENDING'|'DONE'|'EXPIRED'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **domainName** *(string) --* 

          The domain name for which you requested the reachability status.

          
        

        - **status** *(string) --* 

          Whether the registrant contact has responded. ``PENDING`` indicates that we sent the confirmation email and haven't received a response yet, ``DONE`` indicates that we sent the email and got confirmation from the registrant contact, and ``EXPIRED`` indicates that the time limit expired before the registrant contact responded. 

           

          Type: String

           

          Valid values: ``PENDING`` , ``DONE`` , ``EXPIRED`` 

          
    

  .. py:method:: get_domain_detail(**kwargs)

    

    This operation returns detailed information about the domain. The domain's contact information is also returned as part of the output.

    

    **Request Syntax** 
    ::

      response = client.get_domain_detail(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'DomainName': 'string',
            'Nameservers': [
                {
                    'Name': 'string',
                    'GlueIps': [
                        'string',
                    ]
                },
            ],
            'AutoRenew': True|False,
            'AdminContact': {
                'FirstName': 'string',
                'LastName': 'string',
                'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
                'OrganizationName': 'string',
                'AddressLine1': 'string',
                'AddressLine2': 'string',
                'City': 'string',
                'State': 'string',
                'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
                'ZipCode': 'string',
                'PhoneNumber': 'string',
                'Email': 'string',
                'Fax': 'string',
                'ExtraParams': [
                    {
                        'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                        'Value': 'string'
                    },
                ]
            },
            'RegistrantContact': {
                'FirstName': 'string',
                'LastName': 'string',
                'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
                'OrganizationName': 'string',
                'AddressLine1': 'string',
                'AddressLine2': 'string',
                'City': 'string',
                'State': 'string',
                'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
                'ZipCode': 'string',
                'PhoneNumber': 'string',
                'Email': 'string',
                'Fax': 'string',
                'ExtraParams': [
                    {
                        'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                        'Value': 'string'
                    },
                ]
            },
            'TechContact': {
                'FirstName': 'string',
                'LastName': 'string',
                'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
                'OrganizationName': 'string',
                'AddressLine1': 'string',
                'AddressLine2': 'string',
                'City': 'string',
                'State': 'string',
                'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
                'ZipCode': 'string',
                'PhoneNumber': 'string',
                'Email': 'string',
                'Fax': 'string',
                'ExtraParams': [
                    {
                        'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                        'Value': 'string'
                    },
                ]
            },
            'AdminPrivacy': True|False,
            'RegistrantPrivacy': True|False,
            'TechPrivacy': True|False,
            'RegistrarName': 'string',
            'WhoIsServer': 'string',
            'RegistrarUrl': 'string',
            'AbuseContactEmail': 'string',
            'AbuseContactPhone': 'string',
            'RegistryDomainId': 'string',
            'CreationDate': datetime(2015, 1, 1),
            'UpdatedDate': datetime(2015, 1, 1),
            'ExpirationDate': datetime(2015, 1, 1),
            'Reseller': 'string',
            'DnsSec': 'string',
            'StatusList': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The GetDomainDetail response includes the following elements.

        
        

        - **DomainName** *(string) --* 

          The name of a domain.

           

          Type: String

          
        

        - **Nameservers** *(list) --* 

          The name of the domain.

           

          Type: String

          
          

          - *(dict) --* 

            Nameserver includes the following elements.

            
            

            - **Name** *(string) --* 

              The fully qualified host name of the name server.

               

              Type: String

               

              Constraint: Maximum 255 characterss

               

              Parent: ``Nameservers`` 

              
            

            - **GlueIps** *(list) --* 

              Glue IP address of a name server entry. Glue IP addresses are required only when the name of the name server is a subdomain of the domain. For example, if your domain is example.com and the name server for the domain is ns.example.com, you need to specify the IP address for ns.example.com.

               

              Type: List of IP addresses.

               

              Constraints: The list can contain only one IPv4 and one IPv6 address.

               

              Parent: ``Nameservers`` 

              
              

              - *(string) --* 
          
        
      
        

        - **AutoRenew** *(boolean) --* 

          Specifies whether the domain registration is set to renew automatically.

           

          Type: Boolean

          
        

        - **AdminContact** *(dict) --* 

          Provides details about the domain administrative contact. 

           

          Type: Complex

           

          Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

          
          

          - **FirstName** *(string) --* 

            First name of contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

             

            Required: Yes

            
          

          - **LastName** *(string) --* 

            Last name of contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **ContactType** *(string) --* 

            Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

             

            Required: Yes

            
          

          - **OrganizationName** *(string) --* 

            Name of the organization for contact types other than ``PERSON`` .

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **AddressLine1** *(string) --* 

            First line of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **AddressLine2** *(string) --* 

            Second line of contacts address, if any.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **City** *(string) --* 

            The city of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **State** *(string) --* 

            The state or province of the contacts city.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **CountryCode** *(string) --* 

            Code for the country of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **ZipCode** *(string) --* 

            The zip or postal code of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **PhoneNumber** *(string) --* 

            The phone number of the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **Email** *(string) --* 

            Email address of the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 254 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

             

            Required: Yes

            
          

          - **Fax** *(string) --* 

            Fax number of the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **ExtraParams** *(list) --* 

            A list of name-value pairs for parameters required by certain top-level domains.

             

            Type: Complex

             

            Default: None

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Children: ``Name`` , ``Value`` 

             

            Required: No

            
            

            - *(dict) --* 

              ExtraParam includes the following elements.

              
              

              - **Name** *(string) --* 

                Name of the additional parameter required by the top-level domain.

                 

                Type: String

                 

                Default: None

                 

                Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

                 

                Parent: ``ExtraParams`` 

                 

                Required: Yes

                
              

              - **Value** *(string) --* 

                Values corresponding to the additional parameter names required by some top-level domains.

                 

                Type: String

                 

                Default: None

                 

                Constraints: Maximum 2048 characters.

                 

                Parent: ``ExtraParams`` 

                 

                Required: Yes

                
          
        
      
        

        - **RegistrantContact** *(dict) --* 

          Provides details about the domain registrant. 

           

          Type: Complex

           

          Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

          
          

          - **FirstName** *(string) --* 

            First name of contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

             

            Required: Yes

            
          

          - **LastName** *(string) --* 

            Last name of contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **ContactType** *(string) --* 

            Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

             

            Required: Yes

            
          

          - **OrganizationName** *(string) --* 

            Name of the organization for contact types other than ``PERSON`` .

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **AddressLine1** *(string) --* 

            First line of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **AddressLine2** *(string) --* 

            Second line of contacts address, if any.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **City** *(string) --* 

            The city of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **State** *(string) --* 

            The state or province of the contacts city.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **CountryCode** *(string) --* 

            Code for the country of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **ZipCode** *(string) --* 

            The zip or postal code of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **PhoneNumber** *(string) --* 

            The phone number of the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **Email** *(string) --* 

            Email address of the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 254 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

             

            Required: Yes

            
          

          - **Fax** *(string) --* 

            Fax number of the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **ExtraParams** *(list) --* 

            A list of name-value pairs for parameters required by certain top-level domains.

             

            Type: Complex

             

            Default: None

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Children: ``Name`` , ``Value`` 

             

            Required: No

            
            

            - *(dict) --* 

              ExtraParam includes the following elements.

              
              

              - **Name** *(string) --* 

                Name of the additional parameter required by the top-level domain.

                 

                Type: String

                 

                Default: None

                 

                Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

                 

                Parent: ``ExtraParams`` 

                 

                Required: Yes

                
              

              - **Value** *(string) --* 

                Values corresponding to the additional parameter names required by some top-level domains.

                 

                Type: String

                 

                Default: None

                 

                Constraints: Maximum 2048 characters.

                 

                Parent: ``ExtraParams`` 

                 

                Required: Yes

                
          
        
      
        

        - **TechContact** *(dict) --* 

          Provides details about the domain technical contact.

           

          Type: Complex

           

          Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

          
          

          - **FirstName** *(string) --* 

            First name of contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

             

            Required: Yes

            
          

          - **LastName** *(string) --* 

            Last name of contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **ContactType** *(string) --* 

            Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

             

            Required: Yes

            
          

          - **OrganizationName** *(string) --* 

            Name of the organization for contact types other than ``PERSON`` .

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **AddressLine1** *(string) --* 

            First line of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **AddressLine2** *(string) --* 

            Second line of contacts address, if any.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **City** *(string) --* 

            The city of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **State** *(string) --* 

            The state or province of the contacts city.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **CountryCode** *(string) --* 

            Code for the country of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **ZipCode** *(string) --* 

            The zip or postal code of the contacts address.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 255 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **PhoneNumber** *(string) --* 

            The phone number of the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: Yes

            
          

          - **Email** *(string) --* 

            Email address of the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 254 characters.

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

             

            Required: Yes

            
          

          - **Fax** *(string) --* 

            Fax number of the contact.

             

            Type: String

             

            Default: None

             

            Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Required: No

            
          

          - **ExtraParams** *(list) --* 

            A list of name-value pairs for parameters required by certain top-level domains.

             

            Type: Complex

             

            Default: None

             

            Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

             

            Children: ``Name`` , ``Value`` 

             

            Required: No

            
            

            - *(dict) --* 

              ExtraParam includes the following elements.

              
              

              - **Name** *(string) --* 

                Name of the additional parameter required by the top-level domain.

                 

                Type: String

                 

                Default: None

                 

                Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

                 

                Parent: ``ExtraParams`` 

                 

                Required: Yes

                
              

              - **Value** *(string) --* 

                Values corresponding to the additional parameter names required by some top-level domains.

                 

                Type: String

                 

                Default: None

                 

                Constraints: Maximum 2048 characters.

                 

                Parent: ``ExtraParams`` 

                 

                Required: Yes

                
          
        
      
        

        - **AdminPrivacy** *(boolean) --* 

          Specifies whether contact information for the admin contact is concealed from WHOIS queries. If the value is ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

           

          Type: Boolean

          
        

        - **RegistrantPrivacy** *(boolean) --* 

          Specifies whether contact information for the registrant contact is concealed from WHOIS queries. If the value is ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

           

          Type: Boolean

          
        

        - **TechPrivacy** *(boolean) --* 

          Specifies whether contact information for the tech contact is concealed from WHOIS queries. If the value is ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

           

          Type: Boolean

          
        

        - **RegistrarName** *(string) --* 

          Name of the registrar of the domain as identified in the registry. Amazon Route 53 domains are registered by registrar Gandi. The value is ``"GANDI SAS"`` . 

           

          Type: String

          
        

        - **WhoIsServer** *(string) --* 

          The fully qualified name of the WHOIS server that can answer the WHOIS query for the domain.

           

          Type: String

          
        

        - **RegistrarUrl** *(string) --* 

          Web address of the registrar.

           

          Type: String

          
        

        - **AbuseContactEmail** *(string) --* 

          Email address to contact to report incorrect contact information for a domain, to report that the domain is being used to send spam, to report that someone is cybersquatting on a domain name, or report some other type of abuse. 

           

          Type: String

          
        

        - **AbuseContactPhone** *(string) --* 

          Phone number for reporting abuse. 

           

          Type: String

          
        

        - **RegistryDomainId** *(string) --* 

          Reserved for future use.

          
        

        - **CreationDate** *(datetime) --* 

          The date when the domain was created as found in the response to a WHOIS query. The date format is Unix time.

          
        

        - **UpdatedDate** *(datetime) --* 

          The last updated date of the domain as found in the response to a WHOIS query. The date format is Unix time.

          
        

        - **ExpirationDate** *(datetime) --* 

          The date when the registration for the domain is set to expire. The date format is Unix time.

          
        

        - **Reseller** *(string) --* 

          Reseller of the domain. Domains registered or transferred using Amazon Route 53 domains will have ``"Amazon"`` as the reseller. 

           

          Type: String

          
        

        - **DnsSec** *(string) --* 

          Reserved for future use.

          
        

        - **StatusList** *(list) --* 

          An array of domain name status codes, also known as Extensible Provisioning Protocol (EPP) status codes.

           

          ICANN, the organization that maintains a central database of domain names, has developed a set of domain name status codes that tell you the status of a variety of operations on a domain name, for example, registering a domain name, transferring a domain name to another registrar, renewing the registration for a domain name, and so on. All registrars use this same set of status codes.

           

          For a current list of domain name status codes and an explanation of what each code means, go to the `ICANN website`_ and search for ``epp status codes`` . (Search on the ICANN website; web searches sometimes return an old version of the document.)

           

          Type: Array of String

          
          

          - *(string) --* 
      
    

  .. py:method:: get_domain_suggestions(**kwargs)

    

    The GetDomainSuggestions operation returns a list of suggested domain names given a string, which can either be a domain name or simply a word or phrase (without spaces).

     

    Parameters: 

    
    * DomainName (string): The basis for your domain suggestion search, a string with (or without) top-level domain specified.
     
    * SuggestionCount (int): The number of domain suggestions to be returned, maximum 50, minimum 1.
     
    * OnlyAvailable (bool): If true, availability check will be performed on suggestion results, and only available domains will be returned. If false, suggestions will be returned without checking whether the domain is actually available, and caller will have to call checkDomainAvailability for each suggestion to determine availability for registration.
     

     

    

    **Request Syntax** 
    ::

      response = client.get_domain_suggestions(
          DomainName='string',
          SuggestionCount=123,
          OnlyAvailable=True|False
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

    
    :type SuggestionCount: integer
    :param SuggestionCount: **[REQUIRED]** 

    
    :type OnlyAvailable: boolean
    :param OnlyAvailable: **[REQUIRED]** 

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SuggestionsList': [
                {
                    'DomainName': 'string',
                    'Availability': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **SuggestionsList** *(list) --* 
          

          - *(dict) --* 
            

            - **DomainName** *(string) --* 
            

            - **Availability** *(string) --* 
        
      
    

  .. py:method:: get_operation_detail(**kwargs)

    

    This operation returns the current status of an operation that is not completed.

    

    **Request Syntax** 
    ::

      response = client.get_operation_detail(
          OperationId='string'
      )
    :type OperationId: string
    :param OperationId: **[REQUIRED]** 

      The identifier for the operation for which you want to get the status. Amazon Route 53 returned the identifier in the response to the original request.

       

      Type: String

       

      Default: None

       

      Required: Yes

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OperationId': 'string',
            'Status': 'SUBMITTED'|'IN_PROGRESS'|'ERROR'|'SUCCESSFUL'|'FAILED',
            'Message': 'string',
            'DomainName': 'string',
            'Type': 'REGISTER_DOMAIN'|'DELETE_DOMAIN'|'TRANSFER_IN_DOMAIN'|'UPDATE_DOMAIN_CONTACT'|'UPDATE_NAMESERVER'|'CHANGE_PRIVACY_PROTECTION'|'DOMAIN_LOCK',
            'SubmittedDate': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        The GetOperationDetail response includes the following elements.

        
        

        - **OperationId** *(string) --* 

          The identifier for the operation.

           

          Type: String

          
        

        - **Status** *(string) --* 

          The current status of the requested operation in the system.

           

          Type: String

          
        

        - **Message** *(string) --* 

          Detailed information on the status including possible errors.

           

          Type: String

          
        

        - **DomainName** *(string) --* 

          The name of a domain.

           

          Type: String

          
        

        - **Type** *(string) --* 

          The type of operation that was requested.

           

          Type: String

          
        

        - **SubmittedDate** *(datetime) --* 

          The date when the request was submitted.

          
    

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

        


  .. py:method:: list_domains(**kwargs)

    

    This operation returns all the domain names registered with Amazon Route 53 for the current AWS account.

    

    **Request Syntax** 
    ::

      response = client.list_domains(
          Marker='string',
          MaxItems=123
      )
    :type Marker: string
    :param Marker: 

      For an initial request for a list of domains, omit this element. If the number of domains that are associated with the current AWS account is greater than the value that you specified for ``MaxItems`` , you can use ``Marker`` to return additional domains. Get the value of ``NextPageMarker`` from the previous response, and submit another request that includes the value of ``NextPageMarker`` in the ``Marker`` element.

       

      Type: String

       

      Default: None

       

      Constraints: The marker must match the value specified in the previous request. 

       

      Required: No

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Number of domains to be returned.

       

      Type: Integer

       

      Default: 20

       

      Constraints: A numeral between 1 and 100.

       

      Required: No

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Domains': [
                {
                    'DomainName': 'string',
                    'AutoRenew': True|False,
                    'TransferLock': True|False,
                    'Expiry': datetime(2015, 1, 1)
                },
            ],
            'NextPageMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The ListDomains response includes the following elements.

        
        

        - **Domains** *(list) --* 

          A summary of domains.

           

          Type: Complex type containing a list of domain summaries.

           

          Children: ``AutoRenew`` , ``DomainName`` , ``Expiry`` , ``TransferLock`` 

          
          

          - *(dict) --* 
            

            - **DomainName** *(string) --* 

              The name of a domain.

               

              Type: String

              
            

            - **AutoRenew** *(boolean) --* 

              Indicates whether the domain is automatically renewed upon expiration.

               

              Type: Boolean

               

              Valid values: ``True`` | ``False`` 

              
            

            - **TransferLock** *(boolean) --* 

              Indicates whether a domain is locked from unauthorized transfer to another party.

               

              Type: Boolean

               

              Valid values: ``True`` | ``False`` 

              
            

            - **Expiry** *(datetime) --* 

              Expiration date of the domain in Coordinated Universal Time (UTC).

               

              Type: Long

              
        
      
        

        - **NextPageMarker** *(string) --* 

          If there are more domains than you specified for ``MaxItems`` in the request, submit another request and include the value of ``NextPageMarker`` in the value of ``Marker`` .

           

          Type: String

           

          Parent: ``Operations`` 

          
    

  .. py:method:: list_operations(**kwargs)

    

    This operation returns the operation IDs of operations that are not yet complete.

    

    **Request Syntax** 
    ::

      response = client.list_operations(
          Marker='string',
          MaxItems=123
      )
    :type Marker: string
    :param Marker: 

      For an initial request for a list of operations, omit this element. If the number of operations that are not yet complete is greater than the value that you specified for ``MaxItems`` , you can use ``Marker`` to return additional operations. Get the value of ``NextPageMarker`` from the previous response, and submit another request that includes the value of ``NextPageMarker`` in the ``Marker`` element.

       

      Type: String

       

      Default: None

       

      Required: No

      

    
    :type MaxItems: integer
    :param MaxItems: 

      Number of domains to be returned.

       

      Type: Integer

       

      Default: 20

       

      Constraints: A value between 1 and 100.

       

      Required: No

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Operations': [
                {
                    'OperationId': 'string',
                    'Status': 'SUBMITTED'|'IN_PROGRESS'|'ERROR'|'SUCCESSFUL'|'FAILED',
                    'Type': 'REGISTER_DOMAIN'|'DELETE_DOMAIN'|'TRANSFER_IN_DOMAIN'|'UPDATE_DOMAIN_CONTACT'|'UPDATE_NAMESERVER'|'CHANGE_PRIVACY_PROTECTION'|'DOMAIN_LOCK',
                    'SubmittedDate': datetime(2015, 1, 1)
                },
            ],
            'NextPageMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The ListOperations response includes the following elements.

        
        

        - **Operations** *(list) --* 

          Lists summaries of the operations.

           

          Type: Complex type containing a list of operation summaries

           

          Children: ``OperationId`` , ``Status`` , ``SubmittedDate`` , ``Type`` 

          
          

          - *(dict) --* 

            OperationSummary includes the following elements.

            
            

            - **OperationId** *(string) --* 

              Identifier returned to track the requested action.

               

              Type: String

              
            

            - **Status** *(string) --* 

              The current status of the requested operation in the system.

               

              Type: String

              
            

            - **Type** *(string) --* 

              Type of the action requested.

               

              Type: String

               

              Valid values: ``REGISTER_DOMAIN`` | ``DELETE_DOMAIN`` | ``TRANSFER_IN_DOMAIN`` | ``UPDATE_DOMAIN_CONTACT`` | ``UPDATE_NAMESERVER`` | ``CHANGE_PRIVACY_PROTECTION`` | ``DOMAIN_LOCK`` 

              
            

            - **SubmittedDate** *(datetime) --* 

              The date when the request was submitted.

              
        
      
        

        - **NextPageMarker** *(string) --* 

          If there are more operations than you specified for ``MaxItems`` in the request, submit another request and include the value of ``NextPageMarker`` in the value of ``Marker`` .

           

          Type: String

           

          Parent: ``Operations`` 

          
    

  .. py:method:: list_tags_for_domain(**kwargs)

    

    This operation returns all of the tags that are associated with the specified domain.

     

    All tag operations are eventually consistent; subsequent operations may not immediately represent all issued operations.

    

    **Request Syntax** 
    ::

      response = client.list_tags_for_domain(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The domain for which you want to get a list of tags.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TagList': [
                {
                    'Key': 'string',
                    'Value': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The ListTagsForDomain response includes the following elements.

        
        

        - **TagList** *(list) --* 

          A list of the tags that are associated with the specified domain.

           

          Type: A complex type containing a list of tags

           

          Each tag includes the following elements.

           

           
          * Key The key (name) of a tag. Type: String 
           
          * Value The value of a tag. Type: String 
           

          
          

          - *(dict) --* 

            Each tag includes the following elements.

            
            

            - **Key** *(string) --* 

              The key (name) of a tag.

               

              Type: String

               

              Default: None

               

              Valid values: A-Z, a-z, 0-9, space, ".:/=+\-@"

               

              Constraints: Each key can be 1-128 characters long.

               

              Required: Yes

              
            

            - **Value** *(string) --* 

              The value of a tag.

               

              Type: String

               

              Default: None

               

              Valid values: A-Z, a-z, 0-9, space, ".:/=+\-@"

               

              Constraints: Each value can be 0-256 characters long.

               

              Required: Yes

              
        
      
    

  .. py:method:: register_domain(**kwargs)

    

    This operation registers a domain. Domains are registered by the AWS registrar partner, Gandi. For some top-level domains (TLDs), this operation requires extra parameters.

     

    When you register a domain, Amazon Route 53 does the following:

     

     
    * Creates a Amazon Route 53 hosted zone that has the same name as the domain. Amazon Route 53 assigns four name servers to your hosted zone and automatically updates your domain registration with the names of these name servers.
     
    * Enables autorenew, so your domain registration will renew automatically each year. We'll notify you in advance of the renewal date so you can choose whether to renew the registration.
     
    * Optionally enables privacy protection, so WHOIS queries return contact information for our registrar partner, Gandi, instead of the information you entered for registrant, admin, and tech contacts.
     
    * If registration is successful, returns an operation ID that you can use to track the progress and completion of the action. If the request is not completed successfully, the domain registrant is notified by email.
     
    * Charges your AWS account an amount based on the top-level domain. For more information, see `Amazon Route 53 Pricing`_ .
     

    

    **Request Syntax** 
    ::

      response = client.register_domain(
          DomainName='string',
          IdnLangCode='string',
          DurationInYears=123,
          AutoRenew=True|False,
          AdminContact={
              'FirstName': 'string',
              'LastName': 'string',
              'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
              'OrganizationName': 'string',
              'AddressLine1': 'string',
              'AddressLine2': 'string',
              'City': 'string',
              'State': 'string',
              'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
              'ZipCode': 'string',
              'PhoneNumber': 'string',
              'Email': 'string',
              'Fax': 'string',
              'ExtraParams': [
                  {
                      'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                      'Value': 'string'
                  },
              ]
          },
          RegistrantContact={
              'FirstName': 'string',
              'LastName': 'string',
              'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
              'OrganizationName': 'string',
              'AddressLine1': 'string',
              'AddressLine2': 'string',
              'City': 'string',
              'State': 'string',
              'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
              'ZipCode': 'string',
              'PhoneNumber': 'string',
              'Email': 'string',
              'Fax': 'string',
              'ExtraParams': [
                  {
                      'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                      'Value': 'string'
                  },
              ]
          },
          TechContact={
              'FirstName': 'string',
              'LastName': 'string',
              'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
              'OrganizationName': 'string',
              'AddressLine1': 'string',
              'AddressLine2': 'string',
              'City': 'string',
              'State': 'string',
              'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
              'ZipCode': 'string',
              'PhoneNumber': 'string',
              'Email': 'string',
              'Fax': 'string',
              'ExtraParams': [
                  {
                      'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                      'Value': 'string'
                  },
              ]
          },
          PrivacyProtectAdminContact=True|False,
          PrivacyProtectRegistrantContact=True|False,
          PrivacyProtectTechContact=True|False
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    :type IdnLangCode: string
    :param IdnLangCode: 

      Reserved for future use.

      

    
    :type DurationInYears: integer
    :param DurationInYears: **[REQUIRED]** 

      The number of years the domain will be registered. Domains are registered for a minimum of one year. The maximum period depends on the top-level domain.

       

      Type: Integer

       

      Default: 1

       

      Valid values: Integer from 1 to 10

       

      Required: Yes

      

    
    :type AutoRenew: boolean
    :param AutoRenew: 

      Indicates whether the domain will be automatically renewed (``true`` ) or not (``false`` ). Autorenewal only takes effect after the account is charged.

       

      Type: Boolean

       

      Valid values: ``true`` | ``false`` 

       

      Default: ``true`` 

       

      Required: No

      

    
    :type AdminContact: dict
    :param AdminContact: **[REQUIRED]** 

      Provides detailed contact information.

       

      Type: Complex

       

      Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

       

      Required: Yes

      

    
      - **FirstName** *(string) --* 

        First name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **LastName** *(string) --* 

        Last name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ContactType** *(string) --* 

        Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **OrganizationName** *(string) --* 

        Name of the organization for contact types other than ``PERSON`` .

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **AddressLine1** *(string) --* 

        First line of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **AddressLine2** *(string) --* 

        Second line of contacts address, if any.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **City** *(string) --* 

        The city of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **State** *(string) --* 

        The state or province of the contacts city.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **CountryCode** *(string) --* 

        Code for the country of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ZipCode** *(string) --* 

        The zip or postal code of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **PhoneNumber** *(string) --* 

        The phone number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **Email** *(string) --* 

        Email address of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 254 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **Fax** *(string) --* 

        Fax number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **ExtraParams** *(list) --* 

        A list of name-value pairs for parameters required by certain top-level domains.

         

        Type: Complex

         

        Default: None

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Children: ``Name`` , ``Value`` 

         

        Required: No

        

      
        - *(dict) --* 

          ExtraParam includes the following elements.

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            Name of the additional parameter required by the top-level domain.

             

            Type: String

             

            Default: None

             

            Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Values corresponding to the additional parameter names required by some top-level domains.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 2048 characters.

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
        
    
    
    :type RegistrantContact: dict
    :param RegistrantContact: **[REQUIRED]** 

      Provides detailed contact information.

       

      Type: Complex

       

      Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

       

      Required: Yes

      

    
      - **FirstName** *(string) --* 

        First name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **LastName** *(string) --* 

        Last name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ContactType** *(string) --* 

        Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **OrganizationName** *(string) --* 

        Name of the organization for contact types other than ``PERSON`` .

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **AddressLine1** *(string) --* 

        First line of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **AddressLine2** *(string) --* 

        Second line of contacts address, if any.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **City** *(string) --* 

        The city of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **State** *(string) --* 

        The state or province of the contacts city.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **CountryCode** *(string) --* 

        Code for the country of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ZipCode** *(string) --* 

        The zip or postal code of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **PhoneNumber** *(string) --* 

        The phone number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **Email** *(string) --* 

        Email address of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 254 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **Fax** *(string) --* 

        Fax number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **ExtraParams** *(list) --* 

        A list of name-value pairs for parameters required by certain top-level domains.

         

        Type: Complex

         

        Default: None

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Children: ``Name`` , ``Value`` 

         

        Required: No

        

      
        - *(dict) --* 

          ExtraParam includes the following elements.

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            Name of the additional parameter required by the top-level domain.

             

            Type: String

             

            Default: None

             

            Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Values corresponding to the additional parameter names required by some top-level domains.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 2048 characters.

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
        
    
    
    :type TechContact: dict
    :param TechContact: **[REQUIRED]** 

      Provides detailed contact information.

       

      Type: Complex

       

      Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

       

      Required: Yes

      

    
      - **FirstName** *(string) --* 

        First name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **LastName** *(string) --* 

        Last name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ContactType** *(string) --* 

        Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **OrganizationName** *(string) --* 

        Name of the organization for contact types other than ``PERSON`` .

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **AddressLine1** *(string) --* 

        First line of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **AddressLine2** *(string) --* 

        Second line of contacts address, if any.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **City** *(string) --* 

        The city of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **State** *(string) --* 

        The state or province of the contacts city.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **CountryCode** *(string) --* 

        Code for the country of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ZipCode** *(string) --* 

        The zip or postal code of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **PhoneNumber** *(string) --* 

        The phone number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **Email** *(string) --* 

        Email address of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 254 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **Fax** *(string) --* 

        Fax number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **ExtraParams** *(list) --* 

        A list of name-value pairs for parameters required by certain top-level domains.

         

        Type: Complex

         

        Default: None

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Children: ``Name`` , ``Value`` 

         

        Required: No

        

      
        - *(dict) --* 

          ExtraParam includes the following elements.

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            Name of the additional parameter required by the top-level domain.

             

            Type: String

             

            Default: None

             

            Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Values corresponding to the additional parameter names required by some top-level domains.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 2048 characters.

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
        
    
    
    :type PrivacyProtectAdminContact: boolean
    :param PrivacyProtectAdminContact: 

      Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

       

      Type: Boolean

       

      Default: ``true`` 

       

      Valid values: ``true`` | ``false`` 

       

      Required: No

      

    
    :type PrivacyProtectRegistrantContact: boolean
    :param PrivacyProtectRegistrantContact: 

      Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

       

      Type: Boolean

       

      Default: ``true`` 

       

      Valid values: ``true`` | ``false`` 

       

      Required: No

      

    
    :type PrivacyProtectTechContact: boolean
    :param PrivacyProtectTechContact: 

      Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

       

      Type: Boolean

       

      Default: ``true`` 

       

      Valid values: ``true`` | ``false`` 

       

      Required: No

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OperationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The RegisterDomain response includes the following element.

        
        

        - **OperationId** *(string) --* 

          Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

           

          Type: String

           

          Default: None

           

          Constraints: Maximum 255 characters.

          
    

  .. py:method:: renew_domain(**kwargs)

    

    This operation renews a domain for the specified number of years. The cost of renewing your domain is billed to your AWS account.

     

    We recommend that you renew your domain several weeks before the expiration date. Some TLD registries delete domains before the expiration date if you haven't renewed far enough in advance. For more information about renewing domain registration, see `Renewing Registration for a Domain`_ in the Amazon Route 53 documentation.

    

    **Request Syntax** 
    ::

      response = client.renew_domain(
          DomainName='string',
          DurationInYears=123,
          CurrentExpiryYear=123
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

    
    :type DurationInYears: integer
    :param DurationInYears: 

      The number of years that you want to renew the domain for. The maximum number of years depends on the top-level domain. For the range of valid values for your domain, see `Domains that You Can Register with Amazon Route 53`_ in the Amazon Route 53 documentation.

       

      Type: Integer

       

      Default: 1

       

      Valid values: Integer from 1 to 10

       

      Required: No

      

    
    :type CurrentExpiryYear: integer
    :param CurrentExpiryYear: **[REQUIRED]** 

      The year when the registration for the domain is set to expire. This value must match the current expiration date for the domain.

       

      Type: Integer

       

      Default: None

       

      Valid values: Integer

       

      Required: Yes

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OperationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **OperationId** *(string) --* 
    

  .. py:method:: resend_contact_reachability_email(**kwargs)

    

    For operations that require confirmation that the email address for the registrant contact is valid, such as registering a new domain, this operation resends the confirmation email to the current email address for the registrant contact. 

    

    **Request Syntax** 
    ::

      response = client.resend_contact_reachability_email(
          domainName='string'
      )
    :type domainName: string
    :param domainName: 

      The name of the domain for which you want Amazon Route 53 to resend a confirmation email to the registrant contact.

       

      Type: String

       

      Default: None

       

      Required: Yes

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'domainName': 'string',
            'emailAddress': 'string',
            'isAlreadyVerified': True|False
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **domainName** *(string) --* 

          The domain name for which you requested a confirmation email.

          
        

        - **emailAddress** *(string) --* 

          The email address for the registrant contact at the time that we sent the verification email.

          
        

        - **isAlreadyVerified** *(boolean) --* 

          True if the email address for the registrant contact has already been verified, and false otherwise. If the email address has already been verified, we don't send another confirmation email.

          
    

  .. py:method:: retrieve_domain_auth_code(**kwargs)

    

    This operation returns the AuthCode for the domain. To transfer a domain to another registrar, you provide this value to the new registrar.

    

    **Request Syntax** 
    ::

      response = client.retrieve_domain_auth_code(
          DomainName='string'
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AuthCode': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The RetrieveDomainAuthCode response includes the following element.

        
        

        - **AuthCode** *(string) --* 

          The authorization code for the domain.

           

          Type: String

          
    

  .. py:method:: transfer_domain(**kwargs)

    

    This operation transfers a domain from another registrar to Amazon Route 53. When the transfer is complete, the domain is registered with the AWS registrar partner, Gandi.

     

    For transfer requirements, a detailed procedure, and information about viewing the status of a domain transfer, see `Transferring Registration for a Domain to Amazon Route 53`_ in the Amazon Route 53 Developer Guide.

     

    If the registrar for your domain is also the DNS service provider for the domain, we highly recommend that you consider transferring your DNS service to Amazon Route 53 or to another DNS service provider before you transfer your registration. Some registrars provide free DNS service when you purchase a domain registration. When you transfer the registration, the previous registrar will not renew your domain registration and could end your DNS service at any time.

     

    .. note::

      Caution! If the registrar for your domain is also the DNS service provider for the domain and you don't transfer DNS service to another provider, your website, email, and the web applications associated with the domain might become unavailable.

     

    If the transfer is successful, this method returns an operation ID that you can use to track the progress and completion of the action. If the transfer doesn't complete successfully, the domain registrant will be notified by email.

    

    **Request Syntax** 
    ::

      response = client.transfer_domain(
          DomainName='string',
          IdnLangCode='string',
          DurationInYears=123,
          Nameservers=[
              {
                  'Name': 'string',
                  'GlueIps': [
                      'string',
                  ]
              },
          ],
          AuthCode='string',
          AutoRenew=True|False,
          AdminContact={
              'FirstName': 'string',
              'LastName': 'string',
              'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
              'OrganizationName': 'string',
              'AddressLine1': 'string',
              'AddressLine2': 'string',
              'City': 'string',
              'State': 'string',
              'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
              'ZipCode': 'string',
              'PhoneNumber': 'string',
              'Email': 'string',
              'Fax': 'string',
              'ExtraParams': [
                  {
                      'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                      'Value': 'string'
                  },
              ]
          },
          RegistrantContact={
              'FirstName': 'string',
              'LastName': 'string',
              'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
              'OrganizationName': 'string',
              'AddressLine1': 'string',
              'AddressLine2': 'string',
              'City': 'string',
              'State': 'string',
              'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
              'ZipCode': 'string',
              'PhoneNumber': 'string',
              'Email': 'string',
              'Fax': 'string',
              'ExtraParams': [
                  {
                      'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                      'Value': 'string'
                  },
              ]
          },
          TechContact={
              'FirstName': 'string',
              'LastName': 'string',
              'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
              'OrganizationName': 'string',
              'AddressLine1': 'string',
              'AddressLine2': 'string',
              'City': 'string',
              'State': 'string',
              'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
              'ZipCode': 'string',
              'PhoneNumber': 'string',
              'Email': 'string',
              'Fax': 'string',
              'ExtraParams': [
                  {
                      'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                      'Value': 'string'
                  },
              ]
          },
          PrivacyProtectAdminContact=True|False,
          PrivacyProtectRegistrantContact=True|False,
          PrivacyProtectTechContact=True|False
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    :type IdnLangCode: string
    :param IdnLangCode: 

      Reserved for future use.

      

    
    :type DurationInYears: integer
    :param DurationInYears: **[REQUIRED]** 

      The number of years the domain will be registered. Domains are registered for a minimum of one year. The maximum period depends on the top-level domain.

       

      Type: Integer

       

      Default: 1

       

      Valid values: Integer from 1 to 10

       

      Required: Yes

      

    
    :type Nameservers: list
    :param Nameservers: 

      Contains details for the host and glue IP addresses.

       

      Type: Complex

       

      Children: ``GlueIps`` , ``Name`` 

       

      Required: No

      

    
      - *(dict) --* 

        Nameserver includes the following elements.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The fully qualified host name of the name server.

           

          Type: String

           

          Constraint: Maximum 255 characterss

           

          Parent: ``Nameservers`` 

          

        
        - **GlueIps** *(list) --* 

          Glue IP address of a name server entry. Glue IP addresses are required only when the name of the name server is a subdomain of the domain. For example, if your domain is example.com and the name server for the domain is ns.example.com, you need to specify the IP address for ns.example.com.

           

          Type: List of IP addresses.

           

          Constraints: The list can contain only one IPv4 and one IPv6 address.

           

          Parent: ``Nameservers`` 

          

        
          - *(string) --* 

          
      
      
  
    :type AuthCode: string
    :param AuthCode: 

      The authorization code for the domain. You get this value from the current registrar.

       

      Type: String

       

      Required: Yes

      

    
    :type AutoRenew: boolean
    :param AutoRenew: 

      Indicates whether the domain will be automatically renewed (true) or not (false). Autorenewal only takes effect after the account is charged.

       

      Type: Boolean

       

      Valid values: ``true`` | ``false`` 

       

      Default: true

       

      Required: No

      

    
    :type AdminContact: dict
    :param AdminContact: **[REQUIRED]** 

      Provides detailed contact information.

       

      Type: Complex

       

      Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

       

      Required: Yes

      

    
      - **FirstName** *(string) --* 

        First name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **LastName** *(string) --* 

        Last name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ContactType** *(string) --* 

        Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **OrganizationName** *(string) --* 

        Name of the organization for contact types other than ``PERSON`` .

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **AddressLine1** *(string) --* 

        First line of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **AddressLine2** *(string) --* 

        Second line of contacts address, if any.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **City** *(string) --* 

        The city of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **State** *(string) --* 

        The state or province of the contacts city.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **CountryCode** *(string) --* 

        Code for the country of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ZipCode** *(string) --* 

        The zip or postal code of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **PhoneNumber** *(string) --* 

        The phone number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **Email** *(string) --* 

        Email address of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 254 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **Fax** *(string) --* 

        Fax number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **ExtraParams** *(list) --* 

        A list of name-value pairs for parameters required by certain top-level domains.

         

        Type: Complex

         

        Default: None

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Children: ``Name`` , ``Value`` 

         

        Required: No

        

      
        - *(dict) --* 

          ExtraParam includes the following elements.

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            Name of the additional parameter required by the top-level domain.

             

            Type: String

             

            Default: None

             

            Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Values corresponding to the additional parameter names required by some top-level domains.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 2048 characters.

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
        
    
    
    :type RegistrantContact: dict
    :param RegistrantContact: **[REQUIRED]** 

      Provides detailed contact information.

       

      Type: Complex

       

      Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

       

      Required: Yes

      

    
      - **FirstName** *(string) --* 

        First name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **LastName** *(string) --* 

        Last name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ContactType** *(string) --* 

        Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **OrganizationName** *(string) --* 

        Name of the organization for contact types other than ``PERSON`` .

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **AddressLine1** *(string) --* 

        First line of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **AddressLine2** *(string) --* 

        Second line of contacts address, if any.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **City** *(string) --* 

        The city of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **State** *(string) --* 

        The state or province of the contacts city.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **CountryCode** *(string) --* 

        Code for the country of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ZipCode** *(string) --* 

        The zip or postal code of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **PhoneNumber** *(string) --* 

        The phone number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **Email** *(string) --* 

        Email address of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 254 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **Fax** *(string) --* 

        Fax number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **ExtraParams** *(list) --* 

        A list of name-value pairs for parameters required by certain top-level domains.

         

        Type: Complex

         

        Default: None

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Children: ``Name`` , ``Value`` 

         

        Required: No

        

      
        - *(dict) --* 

          ExtraParam includes the following elements.

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            Name of the additional parameter required by the top-level domain.

             

            Type: String

             

            Default: None

             

            Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Values corresponding to the additional parameter names required by some top-level domains.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 2048 characters.

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
        
    
    
    :type TechContact: dict
    :param TechContact: **[REQUIRED]** 

      Provides detailed contact information.

       

      Type: Complex

       

      Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

       

      Required: Yes

      

    
      - **FirstName** *(string) --* 

        First name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **LastName** *(string) --* 

        Last name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ContactType** *(string) --* 

        Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **OrganizationName** *(string) --* 

        Name of the organization for contact types other than ``PERSON`` .

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **AddressLine1** *(string) --* 

        First line of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **AddressLine2** *(string) --* 

        Second line of contacts address, if any.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **City** *(string) --* 

        The city of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **State** *(string) --* 

        The state or province of the contacts city.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **CountryCode** *(string) --* 

        Code for the country of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ZipCode** *(string) --* 

        The zip or postal code of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **PhoneNumber** *(string) --* 

        The phone number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **Email** *(string) --* 

        Email address of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 254 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **Fax** *(string) --* 

        Fax number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **ExtraParams** *(list) --* 

        A list of name-value pairs for parameters required by certain top-level domains.

         

        Type: Complex

         

        Default: None

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Children: ``Name`` , ``Value`` 

         

        Required: No

        

      
        - *(dict) --* 

          ExtraParam includes the following elements.

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            Name of the additional parameter required by the top-level domain.

             

            Type: String

             

            Default: None

             

            Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Values corresponding to the additional parameter names required by some top-level domains.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 2048 characters.

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
        
    
    
    :type PrivacyProtectAdminContact: boolean
    :param PrivacyProtectAdminContact: 

      Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

       

      Type: Boolean

       

      Default: ``true`` 

       

      Valid values: ``true`` | ``false`` 

       

      Required: No

      

    
    :type PrivacyProtectRegistrantContact: boolean
    :param PrivacyProtectRegistrantContact: 

      Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

       

      Type: Boolean

       

      Default: ``true`` 

       

      Valid values: ``true`` | ``false`` 

       

      Required: No

      

    
    :type PrivacyProtectTechContact: boolean
    :param PrivacyProtectTechContact: 

      Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

       

      Type: Boolean

       

      Default: ``true`` 

       

      Valid values: ``true`` | ``false`` 

       

      Required: No

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OperationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The TranserDomain response includes the following element.

        
        

        - **OperationId** *(string) --* 

          Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

           

          Type: String

           

          Default: None

           

          Constraints: Maximum 255 characters.

          
    

  .. py:method:: update_domain_contact(**kwargs)

    

    This operation updates the contact information for a particular domain. Information for at least one contact (registrant, administrator, or technical) must be supplied for update.

     

    If the update is successful, this method returns an operation ID that you can use to track the progress and completion of the action. If the request is not completed successfully, the domain registrant will be notified by email.

    

    **Request Syntax** 
    ::

      response = client.update_domain_contact(
          DomainName='string',
          AdminContact={
              'FirstName': 'string',
              'LastName': 'string',
              'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
              'OrganizationName': 'string',
              'AddressLine1': 'string',
              'AddressLine2': 'string',
              'City': 'string',
              'State': 'string',
              'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
              'ZipCode': 'string',
              'PhoneNumber': 'string',
              'Email': 'string',
              'Fax': 'string',
              'ExtraParams': [
                  {
                      'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                      'Value': 'string'
                  },
              ]
          },
          RegistrantContact={
              'FirstName': 'string',
              'LastName': 'string',
              'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
              'OrganizationName': 'string',
              'AddressLine1': 'string',
              'AddressLine2': 'string',
              'City': 'string',
              'State': 'string',
              'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
              'ZipCode': 'string',
              'PhoneNumber': 'string',
              'Email': 'string',
              'Fax': 'string',
              'ExtraParams': [
                  {
                      'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                      'Value': 'string'
                  },
              ]
          },
          TechContact={
              'FirstName': 'string',
              'LastName': 'string',
              'ContactType': 'PERSON'|'COMPANY'|'ASSOCIATION'|'PUBLIC_BODY'|'RESELLER',
              'OrganizationName': 'string',
              'AddressLine1': 'string',
              'AddressLine2': 'string',
              'City': 'string',
              'State': 'string',
              'CountryCode': 'AD'|'AE'|'AF'|'AG'|'AI'|'AL'|'AM'|'AN'|'AO'|'AQ'|'AR'|'AS'|'AT'|'AU'|'AW'|'AZ'|'BA'|'BB'|'BD'|'BE'|'BF'|'BG'|'BH'|'BI'|'BJ'|'BL'|'BM'|'BN'|'BO'|'BR'|'BS'|'BT'|'BW'|'BY'|'BZ'|'CA'|'CC'|'CD'|'CF'|'CG'|'CH'|'CI'|'CK'|'CL'|'CM'|'CN'|'CO'|'CR'|'CU'|'CV'|'CX'|'CY'|'CZ'|'DE'|'DJ'|'DK'|'DM'|'DO'|'DZ'|'EC'|'EE'|'EG'|'ER'|'ES'|'ET'|'FI'|'FJ'|'FK'|'FM'|'FO'|'FR'|'GA'|'GB'|'GD'|'GE'|'GH'|'GI'|'GL'|'GM'|'GN'|'GQ'|'GR'|'GT'|'GU'|'GW'|'GY'|'HK'|'HN'|'HR'|'HT'|'HU'|'ID'|'IE'|'IL'|'IM'|'IN'|'IQ'|'IR'|'IS'|'IT'|'JM'|'JO'|'JP'|'KE'|'KG'|'KH'|'KI'|'KM'|'KN'|'KP'|'KR'|'KW'|'KY'|'KZ'|'LA'|'LB'|'LC'|'LI'|'LK'|'LR'|'LS'|'LT'|'LU'|'LV'|'LY'|'MA'|'MC'|'MD'|'ME'|'MF'|'MG'|'MH'|'MK'|'ML'|'MM'|'MN'|'MO'|'MP'|'MR'|'MS'|'MT'|'MU'|'MV'|'MW'|'MX'|'MY'|'MZ'|'NA'|'NC'|'NE'|'NG'|'NI'|'NL'|'NO'|'NP'|'NR'|'NU'|'NZ'|'OM'|'PA'|'PE'|'PF'|'PG'|'PH'|'PK'|'PL'|'PM'|'PN'|'PR'|'PT'|'PW'|'PY'|'QA'|'RO'|'RS'|'RU'|'RW'|'SA'|'SB'|'SC'|'SD'|'SE'|'SG'|'SH'|'SI'|'SK'|'SL'|'SM'|'SN'|'SO'|'SR'|'ST'|'SV'|'SY'|'SZ'|'TC'|'TD'|'TG'|'TH'|'TJ'|'TK'|'TL'|'TM'|'TN'|'TO'|'TR'|'TT'|'TV'|'TW'|'TZ'|'UA'|'UG'|'US'|'UY'|'UZ'|'VA'|'VC'|'VE'|'VG'|'VI'|'VN'|'VU'|'WF'|'WS'|'YE'|'YT'|'ZA'|'ZM'|'ZW',
              'ZipCode': 'string',
              'PhoneNumber': 'string',
              'Email': 'string',
              'Fax': 'string',
              'ExtraParams': [
                  {
                      'Name': 'DUNS_NUMBER'|'BRAND_NUMBER'|'BIRTH_DEPARTMENT'|'BIRTH_DATE_IN_YYYY_MM_DD'|'BIRTH_COUNTRY'|'BIRTH_CITY'|'DOCUMENT_NUMBER'|'AU_ID_NUMBER'|'AU_ID_TYPE'|'CA_LEGAL_TYPE'|'CA_BUSINESS_ENTITY_TYPE'|'ES_IDENTIFICATION'|'ES_IDENTIFICATION_TYPE'|'ES_LEGAL_FORM'|'FI_BUSINESS_NUMBER'|'FI_ID_NUMBER'|'IT_PIN'|'RU_PASSPORT_DATA'|'SE_ID_NUMBER'|'SG_ID_NUMBER'|'VAT_NUMBER',
                      'Value': 'string'
                  },
              ]
          }
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    :type AdminContact: dict
    :param AdminContact: 

      Provides detailed contact information.

       

      Type: Complex

       

      Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

       

      Required: Yes

      

    
      - **FirstName** *(string) --* 

        First name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **LastName** *(string) --* 

        Last name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ContactType** *(string) --* 

        Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **OrganizationName** *(string) --* 

        Name of the organization for contact types other than ``PERSON`` .

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **AddressLine1** *(string) --* 

        First line of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **AddressLine2** *(string) --* 

        Second line of contacts address, if any.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **City** *(string) --* 

        The city of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **State** *(string) --* 

        The state or province of the contacts city.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **CountryCode** *(string) --* 

        Code for the country of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ZipCode** *(string) --* 

        The zip or postal code of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **PhoneNumber** *(string) --* 

        The phone number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **Email** *(string) --* 

        Email address of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 254 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **Fax** *(string) --* 

        Fax number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **ExtraParams** *(list) --* 

        A list of name-value pairs for parameters required by certain top-level domains.

         

        Type: Complex

         

        Default: None

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Children: ``Name`` , ``Value`` 

         

        Required: No

        

      
        - *(dict) --* 

          ExtraParam includes the following elements.

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            Name of the additional parameter required by the top-level domain.

             

            Type: String

             

            Default: None

             

            Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Values corresponding to the additional parameter names required by some top-level domains.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 2048 characters.

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
        
    
    
    :type RegistrantContact: dict
    :param RegistrantContact: 

      Provides detailed contact information.

       

      Type: Complex

       

      Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

       

      Required: Yes

      

    
      - **FirstName** *(string) --* 

        First name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **LastName** *(string) --* 

        Last name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ContactType** *(string) --* 

        Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **OrganizationName** *(string) --* 

        Name of the organization for contact types other than ``PERSON`` .

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **AddressLine1** *(string) --* 

        First line of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **AddressLine2** *(string) --* 

        Second line of contacts address, if any.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **City** *(string) --* 

        The city of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **State** *(string) --* 

        The state or province of the contacts city.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **CountryCode** *(string) --* 

        Code for the country of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ZipCode** *(string) --* 

        The zip or postal code of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **PhoneNumber** *(string) --* 

        The phone number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **Email** *(string) --* 

        Email address of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 254 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **Fax** *(string) --* 

        Fax number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **ExtraParams** *(list) --* 

        A list of name-value pairs for parameters required by certain top-level domains.

         

        Type: Complex

         

        Default: None

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Children: ``Name`` , ``Value`` 

         

        Required: No

        

      
        - *(dict) --* 

          ExtraParam includes the following elements.

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            Name of the additional parameter required by the top-level domain.

             

            Type: String

             

            Default: None

             

            Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Values corresponding to the additional parameter names required by some top-level domains.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 2048 characters.

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
        
    
    
    :type TechContact: dict
    :param TechContact: 

      Provides detailed contact information.

       

      Type: Complex

       

      Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

       

      Required: Yes

      

    
      - **FirstName** *(string) --* 

        First name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **LastName** *(string) --* 

        Last name of contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ContactType** *(string) --* 

        Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you cant enable privacy protection for the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **OrganizationName** *(string) --* 

        Name of the organization for contact types other than ``PERSON`` .

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **AddressLine1** *(string) --* 

        First line of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **AddressLine2** *(string) --* 

        Second line of contacts address, if any.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **City** *(string) --* 

        The city of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **State** *(string) --* 

        The state or province of the contacts city.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **CountryCode** *(string) --* 

        Code for the country of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **ZipCode** *(string) --* 

        The zip or postal code of the contacts address.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 255 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **PhoneNumber** *(string) --* 

        The phone number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code>]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: Yes

        

      
      - **Email** *(string) --* 

        Email address of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 254 characters.

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

         

        Required: Yes

        

      
      - **Fax** *(string) --* 

        Fax number of the contact.

         

        Type: String

         

        Default: None

         

        Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Required: No

        

      
      - **ExtraParams** *(list) --* 

        A list of name-value pairs for parameters required by certain top-level domains.

         

        Type: Complex

         

        Default: None

         

        Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

         

        Children: ``Name`` , ``Value`` 

         

        Required: No

        

      
        - *(dict) --* 

          ExtraParam includes the following elements.

          

        
          - **Name** *(string) --* **[REQUIRED]** 

            Name of the additional parameter required by the top-level domain.

             

            Type: String

             

            Default: None

             

            Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``CA_BUSINESS_ENTITY_TYPE`` |``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
          - **Value** *(string) --* **[REQUIRED]** 

            Values corresponding to the additional parameter names required by some top-level domains.

             

            Type: String

             

            Default: None

             

            Constraints: Maximum 2048 characters.

             

            Parent: ``ExtraParams`` 

             

            Required: Yes

            

          
        
    
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OperationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The UpdateDomainContact response includes the following element.

        
        

        - **OperationId** *(string) --* 

          Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

           

          Type: String

           

          Default: None

           

          Constraints: Maximum 255 characters.

          
    

  .. py:method:: update_domain_contact_privacy(**kwargs)

    

    This operation updates the specified domain contact's privacy setting. When the privacy option is enabled, personal information such as postal or email address is hidden from the results of a public WHOIS query. The privacy services are provided by the AWS registrar, Gandi. For more information, see the `Gandi privacy features`_ .

     

    This operation only affects the privacy of the specified contact type (registrant, administrator, or tech). Successful acceptance returns an operation ID that you can use with GetOperationDetail to track the progress and completion of the action. If the request is not completed successfully, the domain registrant will be notified by email.

    

    **Request Syntax** 
    ::

      response = client.update_domain_contact_privacy(
          DomainName='string',
          AdminPrivacy=True|False,
          RegistrantPrivacy=True|False,
          TechPrivacy=True|False
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    :type AdminPrivacy: boolean
    :param AdminPrivacy: 

      Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

       

      Type: Boolean

       

      Default: None

       

      Valid values: ``true`` | ``false`` 

       

      Required: No

      

    
    :type RegistrantPrivacy: boolean
    :param RegistrantPrivacy: 

      Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

       

      Type: Boolean

       

      Default: None

       

      Valid values: ``true`` | ``false`` 

       

      Required: No

      

    
    :type TechPrivacy: boolean
    :param TechPrivacy: 

      Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

       

      Type: Boolean

       

      Default: None

       

      Valid values: ``true`` | ``false`` 

       

      Required: No

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OperationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The UpdateDomainContactPrivacy response includes the following element.

        
        

        - **OperationId** *(string) --* 

          Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

           

          Type: String

           

          Default: None

           

          Constraints: Maximum 255 characters.

          
    

  .. py:method:: update_domain_nameservers(**kwargs)

    

    This operation replaces the current set of name servers for the domain with the specified set of name servers. If you use Amazon Route 53 as your DNS service, specify the four name servers in the delegation set for the hosted zone for the domain. 

     

    If successful, this operation returns an operation ID that you can use to track the progress and completion of the action. If the request is not completed successfully, the domain registrant will be notified by email.

    

    **Request Syntax** 
    ::

      response = client.update_domain_nameservers(
          DomainName='string',
          FIAuthKey='string',
          Nameservers=[
              {
                  'Name': 'string',
                  'GlueIps': [
                      'string',
                  ]
              },
          ]
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

       

      Required: Yes

      

    
    :type FIAuthKey: string
    :param FIAuthKey: 

      The authorization key for .fi domains

      

    
    :type Nameservers: list
    :param Nameservers: **[REQUIRED]** 

      A list of new name servers for the domain.

       

      Type: Complex

       

      Children: ``Name`` , ``GlueIps`` 

       

      Required: Yes

      

    
      - *(dict) --* 

        Nameserver includes the following elements.

        

      
        - **Name** *(string) --* **[REQUIRED]** 

          The fully qualified host name of the name server.

           

          Type: String

           

          Constraint: Maximum 255 characterss

           

          Parent: ``Nameservers`` 

          

        
        - **GlueIps** *(list) --* 

          Glue IP address of a name server entry. Glue IP addresses are required only when the name of the name server is a subdomain of the domain. For example, if your domain is example.com and the name server for the domain is ns.example.com, you need to specify the IP address for ns.example.com.

           

          Type: List of IP addresses.

           

          Constraints: The list can contain only one IPv4 and one IPv6 address.

           

          Parent: ``Nameservers`` 

          

        
          - *(string) --* 

          
      
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'OperationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The UpdateDomainNameservers response includes the following element.

        
        

        - **OperationId** *(string) --* 

          Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

           

          Type: String

           

          Default: None

           

          Constraints: Maximum 255 characters.

          
    

  .. py:method:: update_tags_for_domain(**kwargs)

    

    This operation adds or updates tags for a specified domain.

     

    All tag operations are eventually consistent; subsequent operations may not immediately represent all issued operations.

    

    **Request Syntax** 
    ::

      response = client.update_tags_for_domain(
          DomainName='string',
          TagsToUpdate=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type DomainName: string
    :param DomainName: **[REQUIRED]** 

      The domain for which you want to add or update tags.

       

      The name of a domain.

       

      Type: String

       

      Default: None

       

      Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Hyphens are allowed only when theyre surrounded by letters, numbers, or other hyphens. You cant specify a hyphen at the beginning or end of a label. To specify an Internationalized Domain Name, you must convert the name to Punycode.

       

      Required: Yes

      

    
    :type TagsToUpdate: list
    :param TagsToUpdate: 

      A list of the tag keys and values that you want to add or update. If you specify a key that already exists, the corresponding value will be replaced.

       

      Type: A complex type containing a list of tags

       

      Default: None

       

      Required: No

      '> 

      Each tag includes the following elements:

       

       
      * Key The key (name) of a tag. Type: String Default: None Valid values: Unicode characters including alphanumeric, space, and ".:/=+\-@" Constraints: Each key can be 1-128 characters long. Required: Yes 
       
      * Value The value of a tag. Type: String Default: None Valid values: Unicode characters including alphanumeric, space, and ".:/=+\-@" Constraints: Each value can be 0-256 characters long. Required: Yes 
       

      

    
      - *(dict) --* 

        Each tag includes the following elements.

        

      
        - **Key** *(string) --* 

          The key (name) of a tag.

           

          Type: String

           

          Default: None

           

          Valid values: A-Z, a-z, 0-9, space, ".:/=+\-@"

           

          Constraints: Each key can be 1-128 characters long.

           

          Required: Yes

          

        
        - **Value** *(string) --* 

          The value of a tag.

           

          Type: String

           

          Default: None

           

          Valid values: A-Z, a-z, 0-9, space, ".:/=+\-@"

           

          Constraints: Each value can be 0-256 characters long.

           

          Required: Yes

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 
    

  .. py:method:: view_billing(**kwargs)

    

    This operation returns all the domain-related billing records for the current AWS account for a specified period

    

    **Request Syntax** 
    ::

      response = client.view_billing(
          Start=datetime(2015, 1, 1),
          End=datetime(2015, 1, 1),
          Marker='string',
          MaxItems=123
      )
    :type Start: datetime
    :param Start: 

      The beginning date and time for the time period for which you want a list of billing records. Specify the date in Unix time format.

       

      Type: Double

       

      Default: None

       

      Required: Yes

      

    
    :type End: datetime
    :param End: 

      The end date and time for the time period for which you want a list of billing records. Specify the date in Unix time format.

       

      Type: Double

       

      Default: None

       

      Required: Yes

      

    
    :type Marker: string
    :param Marker: 

      For an initial request for a list of billing records, omit this element. If the number of billing records that are associated with the current AWS account during the specified period is greater than the value that you specified for ``MaxItems`` , you can use ``Marker`` to return additional billing records. Get the value of ``NextPageMarker`` from the previous response, and submit another request that includes the value of ``NextPageMarker`` in the ``Marker`` element. 

       

      Type: String

       

      Default: None

       

      Constraints: The marker must match the value of ``NextPageMarker`` that was returned in the previous response.

       

      Required: No

      

    
    :type MaxItems: integer
    :param MaxItems: 

      The number of billing records to be returned.

       

      Type: Integer

       

      Default: 20

       

      Constraints: A value between 1 and 100.

       

      Required: No

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'NextPageMarker': 'string',
            'BillingRecords': [
                {
                    'DomainName': 'string',
                    'Operation': 'REGISTER_DOMAIN'|'DELETE_DOMAIN'|'TRANSFER_IN_DOMAIN'|'UPDATE_DOMAIN_CONTACT'|'UPDATE_NAMESERVER'|'CHANGE_PRIVACY_PROTECTION'|'DOMAIN_LOCK',
                    'InvoiceId': 'string',
                    'BillDate': datetime(2015, 1, 1),
                    'Price': 123.0
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The ViewBilling response includes the following elements.

        
        

        - **NextPageMarker** *(string) --* 

          If there are more billing records than you specified for ``MaxItems`` in the request, submit another request and include the value of ``NextPageMarker`` in the value of ``Marker`` .

           

          Type: String

           

          Parent: ``BillingRecords`` 

          
        

        - **BillingRecords** *(list) --* 

          A summary of billing records.

           

          Type: Complex type containing a list of billing record summaries.

           

          Children: ``DomainName`` , ``Operation`` , ``InvoiceId`` , ``BillDate`` and ``Price`` 

          
          

          - *(dict) --* 
            

            - **DomainName** *(string) --* 

              The name of a domain.

               

              Type: String

              
            

            - **Operation** *(string) --* 

              The operation that you were charged for.

               

              Type: String

               

              Valid values: 

               
              * ``REGISTER_DOMAIN`` 
               
              * ``TRANSFER_IN_DOMAIN`` 
               
              * ``RENEW_DOMAIN`` 
               
              * ``CHANGE_DOMAIN_OWNER`` 
               

               

              
            

            - **InvoiceId** *(string) --* 

              The ID of the invoice that is associated with the billing record.

               

              Type: String

              
            

            - **BillDate** *(datetime) --* 

              The date that the operation was billed, in Unix format.

               

              Type: Double

              
            

            - **Price** *(float) --* 

              The price that you were charged for the operation, in US dollars.

               

              Type: Double

               

              Example value: 12.0

              
        
      
    

==========
Paginators
==========


The available paginators are:

* :py:class:`Route53Domains.Paginator.ListDomains`


* :py:class:`Route53Domains.Paginator.ListOperations`



.. py:class:: Route53Domains.Paginator.ListDomains

  ::

    
    paginator = client.get_paginator('list_domains')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`Route53Domains.Client.list_domains`.

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
            'Domains': [
                {
                    'DomainName': 'string',
                    'AutoRenew': True|False,
                    'TransferLock': True|False,
                    'Expiry': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The ListDomains response includes the following elements.

        
        

        - **Domains** *(list) --* 

          A summary of domains.

           

          Type: Complex type containing a list of domain summaries.

           

          Children: ``AutoRenew`` , ``DomainName`` , ``Expiry`` , ``TransferLock`` 

          
          

          - *(dict) --* 
            

            - **DomainName** *(string) --* 

              The name of a domain.

               

              Type: String

              
            

            - **AutoRenew** *(boolean) --* 

              Indicates whether the domain is automatically renewed upon expiration.

               

              Type: Boolean

               

              Valid values: ``True`` | ``False`` 

              
            

            - **TransferLock** *(boolean) --* 

              Indicates whether a domain is locked from unauthorized transfer to another party.

               

              Type: Boolean

               

              Valid values: ``True`` | ``False`` 

              
            

            - **Expiry** *(datetime) --* 

              Expiration date of the domain in Coordinated Universal Time (UTC).

               

              Type: Long

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: Route53Domains.Paginator.ListOperations

  ::

    
    paginator = client.get_paginator('list_operations')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`Route53Domains.Client.list_operations`.

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
            'Operations': [
                {
                    'OperationId': 'string',
                    'Status': 'SUBMITTED'|'IN_PROGRESS'|'ERROR'|'SUCCESSFUL'|'FAILED',
                    'Type': 'REGISTER_DOMAIN'|'DELETE_DOMAIN'|'TRANSFER_IN_DOMAIN'|'UPDATE_DOMAIN_CONTACT'|'UPDATE_NAMESERVER'|'CHANGE_PRIVACY_PROTECTION'|'DOMAIN_LOCK',
                    'SubmittedDate': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        The ListOperations response includes the following elements.

        
        

        - **Operations** *(list) --* 

          Lists summaries of the operations.

           

          Type: Complex type containing a list of operation summaries

           

          Children: ``OperationId`` , ``Status`` , ``SubmittedDate`` , ``Type`` 

          
          

          - *(dict) --* 

            OperationSummary includes the following elements.

            
            

            - **OperationId** *(string) --* 

              Identifier returned to track the requested action.

               

              Type: String

              
            

            - **Status** *(string) --* 

              The current status of the requested operation in the system.

               

              Type: String

              
            

            - **Type** *(string) --* 

              Type of the action requested.

               

              Type: String

               

              Valid values: ``REGISTER_DOMAIN`` | ``DELETE_DOMAIN`` | ``TRANSFER_IN_DOMAIN`` | ``UPDATE_DOMAIN_CONTACT`` | ``UPDATE_NAMESERVER`` | ``CHANGE_PRIVACY_PROTECTION`` | ``DOMAIN_LOCK`` 

              
            

            - **SubmittedDate** *(datetime) --* 

              The date when the request was submitted.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    