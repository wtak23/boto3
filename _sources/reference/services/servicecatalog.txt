

**************
ServiceCatalog
**************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: ServiceCatalog.Client

  A low-level client representing AWS Service Catalog::

    
    import boto3
    
    client = boto3.client('servicecatalog')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`describe_product`

  
  *   :py:meth:`describe_product_view`

  
  *   :py:meth:`describe_provisioning_parameters`

  
  *   :py:meth:`describe_record`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_launch_paths`

  
  *   :py:meth:`list_record_history`

  
  *   :py:meth:`provision_product`

  
  *   :py:meth:`scan_provisioned_products`

  
  *   :py:meth:`search_products`

  
  *   :py:meth:`terminate_provisioned_product`

  
  *   :py:meth:`update_provisioned_product`

  

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


  .. py:method:: describe_product(**kwargs)

    

    Retrieves information about a specified product.

     

    This operation is functionally identical to  DescribeProductView except that it takes as input ``ProductId`` instead of ``ProductViewId`` .

    

    **Request Syntax** 
    ::

      response = client.describe_product(
          AcceptLanguage='string',
          Id='string'
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type Id: string
    :param Id: **[REQUIRED]** 

      The ``ProductId`` of the product to describe.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ProductViewSummary': {
                'Id': 'string',
                'ProductId': 'string',
                'Name': 'string',
                'Owner': 'string',
                'ShortDescription': 'string',
                'Type': 'string',
                'Distributor': 'string',
                'HasDefaultPath': True|False,
                'SupportEmail': 'string',
                'SupportDescription': 'string',
                'SupportUrl': 'string'
            },
            'ProvisioningArtifacts': [
                {
                    'Id': 'string',
                    'Name': 'string',
                    'Description': 'string',
                    'CreatedTime': datetime(2015, 1, 1)
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ProductViewSummary** *(dict) --* 

          The summary metadata about the specified product.

          
          

          - **Id** *(string) --* 

            The product view identifier.

            
          

          - **ProductId** *(string) --* 

            The product identifier.

            
          

          - **Name** *(string) --* 

            The name of the product.

            
          

          - **Owner** *(string) --* 

            The owner of the product. Contact the product administrator for the significance of this value.

            
          

          - **ShortDescription** *(string) --* 

            Short description of the product.

            
          

          - **Type** *(string) --* 

            The product type. Contact the product administrator for the significance of this value.

            
          

          - **Distributor** *(string) --* 

            The distributor of the product. Contact the product administrator for the significance of this value.

            
          

          - **HasDefaultPath** *(boolean) --* 

            A value of ``false`` indicates that the product does not have a default path, while a value of ``true`` indicates that it does. If it's false, call  ListLaunchPaths to disambiguate between paths. If true,  ListLaunchPaths is not required, and the output of the  ProductViewSummary operation can be used directly with  DescribeProvisioningParameters .

            
          

          - **SupportEmail** *(string) --* 

            The email contact information to obtain support for this Product.

            
          

          - **SupportDescription** *(string) --* 

            The description of the support for this Product.

            
          

          - **SupportUrl** *(string) --* 

            The URL information to obtain support for this Product.

            
      
        

        - **ProvisioningArtifacts** *(list) --* 

          A list of provisioning artifact objects for the specified product. The ``ProvisioningArtifacts`` parameter represent the ways the specified product can be provisioned.

          
          

          - *(dict) --* 

            Contains information indicating the ways in which a product can be provisioned.

            
            

            - **Id** *(string) --* 

              The identifier for the artifact.

              
            

            - **Name** *(string) --* 

              The name of the artifact.

              
            

            - **Description** *(string) --* 

              The text description of the artifact.

              
            

            - **CreatedTime** *(datetime) --* 

              The time that the artifact was created by the Administrator.

              
        
      
    

  .. py:method:: describe_product_view(**kwargs)

    

    Retrieves information about a specified product.

     

    This operation is functionally identical to  DescribeProduct except that it takes as input ``ProductViewId`` instead of ``ProductId`` .

    

    **Request Syntax** 
    ::

      response = client.describe_product_view(
          AcceptLanguage='string',
          Id='string'
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type Id: string
    :param Id: **[REQUIRED]** 

      The ``ProductViewId`` of the product to describe.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ProductViewSummary': {
                'Id': 'string',
                'ProductId': 'string',
                'Name': 'string',
                'Owner': 'string',
                'ShortDescription': 'string',
                'Type': 'string',
                'Distributor': 'string',
                'HasDefaultPath': True|False,
                'SupportEmail': 'string',
                'SupportDescription': 'string',
                'SupportUrl': 'string'
            },
            'ProvisioningArtifacts': [
                {
                    'Id': 'string',
                    'Name': 'string',
                    'Description': 'string',
                    'CreatedTime': datetime(2015, 1, 1)
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ProductViewSummary** *(dict) --* 

          The summary metadata about the specified product.

          
          

          - **Id** *(string) --* 

            The product view identifier.

            
          

          - **ProductId** *(string) --* 

            The product identifier.

            
          

          - **Name** *(string) --* 

            The name of the product.

            
          

          - **Owner** *(string) --* 

            The owner of the product. Contact the product administrator for the significance of this value.

            
          

          - **ShortDescription** *(string) --* 

            Short description of the product.

            
          

          - **Type** *(string) --* 

            The product type. Contact the product administrator for the significance of this value.

            
          

          - **Distributor** *(string) --* 

            The distributor of the product. Contact the product administrator for the significance of this value.

            
          

          - **HasDefaultPath** *(boolean) --* 

            A value of ``false`` indicates that the product does not have a default path, while a value of ``true`` indicates that it does. If it's false, call  ListLaunchPaths to disambiguate between paths. If true,  ListLaunchPaths is not required, and the output of the  ProductViewSummary operation can be used directly with  DescribeProvisioningParameters .

            
          

          - **SupportEmail** *(string) --* 

            The email contact information to obtain support for this Product.

            
          

          - **SupportDescription** *(string) --* 

            The description of the support for this Product.

            
          

          - **SupportUrl** *(string) --* 

            The URL information to obtain support for this Product.

            
      
        

        - **ProvisioningArtifacts** *(list) --* 

          A list of provisioning artifact objects for the specified product. The ``ProvisioningArtifacts`` represent the ways in which the specified product can be provisioned.

          
          

          - *(dict) --* 

            Contains information indicating the ways in which a product can be provisioned.

            
            

            - **Id** *(string) --* 

              The identifier for the artifact.

              
            

            - **Name** *(string) --* 

              The name of the artifact.

              
            

            - **Description** *(string) --* 

              The text description of the artifact.

              
            

            - **CreatedTime** *(datetime) --* 

              The time that the artifact was created by the Administrator.

              
        
      
    

  .. py:method:: describe_provisioning_parameters(**kwargs)

    

    Provides information about parameters required to provision a specified product in a specified manner. Use this operation to obtain the list of ``ProvisioningArtifactParameters`` parameters available to call the  ProvisionProduct operation for the specified product.

    

    **Request Syntax** 
    ::

      response = client.describe_provisioning_parameters(
          AcceptLanguage='string',
          ProductId='string',
          ProvisioningArtifactId='string',
          PathId='string'
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type ProductId: string
    :param ProductId: **[REQUIRED]** 

      The identifier of the product.

      

    
    :type ProvisioningArtifactId: string
    :param ProvisioningArtifactId: **[REQUIRED]** 

      The provisioning artifact identifier for this product.

      

    
    :type PathId: string
    :param PathId: 

      The identifier of the path for this product's provisioning. This value is optional if the product has a default path, and is required if there is more than one path for the specified product.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ProvisioningArtifactParameters': [
                {
                    'ParameterKey': 'string',
                    'DefaultValue': 'string',
                    'ParameterType': 'string',
                    'IsNoEcho': True|False,
                    'Description': 'string',
                    'ParameterConstraints': {
                        'AllowedValues': [
                            'string',
                        ]
                    }
                },
            ],
            'ConstraintSummaries': [
                {
                    'Type': 'string',
                    'Description': 'string'
                },
            ],
            'UsageInstructions': [
                {
                    'Type': 'string',
                    'Value': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ProvisioningArtifactParameters** *(list) --* 

          The list of parameters used to successfully provision the product. Each parameter includes a list of allowable values and additional metadata about each parameter.

          
          

          - *(dict) --* 

            A parameter used to successfully provision the product. This value includes a list of allowable values and additional metadata. 

            
            

            - **ParameterKey** *(string) --* 

              The parameter key. 

              
            

            - **DefaultValue** *(string) --* 

              The default value for this parameter.

              
            

            - **ParameterType** *(string) --* 

              The parameter type.

              
            

            - **IsNoEcho** *(boolean) --* 

              If this value is true, the value for this parameter is obfuscated from view when the parameter is retrieved. This parameter is used to hide sensitive information.

              
            

            - **Description** *(string) --* 

              The text description of the parameter.

              
            

            - **ParameterConstraints** *(dict) --* 

              The list of constraints that the administrator has put on the parameter.

              
              

              - **AllowedValues** *(list) --* 

                The values that the administrator has allowed for the parameter.

                
                

                - *(string) --* 
            
          
        
      
        

        - **ConstraintSummaries** *(list) --* 

          The list of constraint summaries that apply to provisioning this product.

          
          

          - *(dict) --* 

            An administrator-specified constraint to apply when provisioning a product.

            
            

            - **Type** *(string) --* 

              The type of the constraint. 

              
            

            - **Description** *(string) --* 

              The text description of the constraint.

              
        
      
        

        - **UsageInstructions** *(list) --* 

          Any additional metadata specifically related to the provisioning of the product. For example, see the ``Version`` field of the CloudFormation template.

          
          

          - *(dict) --* 

            Additional information provided by the administrator.

            
            

            - **Type** *(string) --* 

              The usage instruction type for the value.

              
            

            - **Value** *(string) --* 

              The usage instruction value for this type.

              
        
      
    

  .. py:method:: describe_record(**kwargs)

    

    Retrieves a paginated list of the full details of a specific request. Use this operation after calling a request operation ( ProvisionProduct ,  TerminateProvisionedProduct , or  UpdateProvisionedProduct ). 

    

    **Request Syntax** 
    ::

      response = client.describe_record(
          AcceptLanguage='string',
          Id='string',
          PageToken='string',
          PageSize=123
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type Id: string
    :param Id: **[REQUIRED]** 

      The record identifier of the ProvisionedProduct object for which to retrieve output information. This is the ``RecordDetail.RecordId`` obtained from the request operation's response.

      

    
    :type PageToken: string
    :param PageToken: 

      The page token of the first page retrieve. If null, this retrieves the first page of size ``PageSize`` .

      

    
    :type PageSize: integer
    :param PageSize: 

      The maximum number of items to return in the results. If more results exist than fit in the specified ``PageSize`` , the value of ``NextPageToken`` in the response is non-null.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RecordDetail': {
                'RecordId': 'string',
                'ProvisionedProductName': 'string',
                'Status': 'IN_PROGRESS'|'SUCCEEDED'|'ERROR',
                'CreatedTime': datetime(2015, 1, 1),
                'UpdatedTime': datetime(2015, 1, 1),
                'ProvisionedProductType': 'string',
                'RecordType': 'string',
                'ProvisionedProductId': 'string',
                'ProductId': 'string',
                'ProvisioningArtifactId': 'string',
                'PathId': 'string',
                'RecordErrors': [
                    {
                        'Code': 'string',
                        'Description': 'string'
                    },
                ],
                'RecordTags': [
                    {
                        'Key': 'string',
                        'Value': 'string'
                    },
                ]
            },
            'RecordOutputs': [
                {
                    'OutputKey': 'string',
                    'OutputValue': 'string',
                    'Description': 'string'
                },
            ],
            'NextPageToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **RecordDetail** *(dict) --* 

          Detailed record information for the specified product. 

          
          

          - **RecordId** *(string) --* 

            The identifier of the ProvisionedProduct object record.

            
          

          - **ProvisionedProductName** *(string) --* 

            The user-friendly name of the ProvisionedProduct object.

            
          

          - **Status** *(string) --* 

            The status of the ProvisionedProduct object.

            
          

          - **CreatedTime** *(datetime) --* 

            The time when the record for the ProvisionedProduct object was created.

            
          

          - **UpdatedTime** *(datetime) --* 

            The time when the record for the ProvisionedProduct object was last updated.

            
          

          - **ProvisionedProductType** *(string) --* 

            The type of the ProvisionedProduct object.

            
          

          - **RecordType** *(string) --* 

            The record type for this record.

            
          

          - **ProvisionedProductId** *(string) --* 

            The identifier of the ProvisionedProduct object.

            
          

          - **ProductId** *(string) --* 

            The identifier of the product.

            
          

          - **ProvisioningArtifactId** *(string) --* 

            The provisioning artifact identifier for this product.

            
          

          - **PathId** *(string) --* 

            The identifier of the path for this product's provisioning.

            
          

          - **RecordErrors** *(list) --* 

            A list of errors that occurred while processing the request.

            
            

            - *(dict) --* 

              The error code and description resulting from an operation.

              
              

              - **Code** *(string) --* 

                The numeric value of the error.

                
              

              - **Description** *(string) --* 

                The text description of the error.

                
          
        
          

          - **RecordTags** *(list) --* 

            List of tags associated with this record.

            
            

            - *(dict) --* 

              A tag associated with the record, stored as a key-value pair.

              
              

              - **Key** *(string) --* 

                The key for this tag.

                
              

              - **Value** *(string) --* 

                The value for this tag.

                
          
        
      
        

        - **RecordOutputs** *(list) --* 

          A list of outputs for the specified Product object created as the result of a request. For example, a CloudFormation-backed product that creates an S3 bucket would have an output for the S3 bucket URL.

          
          

          - *(dict) --* 

            An output for the specified Product object created as the result of a request. For example, a CloudFormation-backed product that creates an S3 bucket would have an output for the S3 bucket URL.

            
            

            - **OutputKey** *(string) --* 

              The output key.

              
            

            - **OutputValue** *(string) --* 

              The output value.

              
            

            - **Description** *(string) --* 

              The text description of the output.

              
        
      
        

        - **NextPageToken** *(string) --* 

          The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

          
    

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

        


  .. py:method:: list_launch_paths(**kwargs)

    

    Returns a paginated list of all paths to a specified product. A path is how the user has access to a specified product, and is necessary when provisioning a product. A path also determines the constraints put on the product.

    

    **Request Syntax** 
    ::

      response = client.list_launch_paths(
          AcceptLanguage='string',
          ProductId='string',
          PageSize=123,
          PageToken='string'
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type ProductId: string
    :param ProductId: **[REQUIRED]** 

      Identifies the product for which to retrieve ``LaunchPathSummaries`` information.

      

    
    :type PageSize: integer
    :param PageSize: 

      The maximum number of items to return in the results. If more results exist than fit in the specified ``PageSize`` , the value of ``NextPageToken`` in the response is non-null.

      

    
    :type PageToken: string
    :param PageToken: 

      The page token of the first page retrieve. If null, this retrieves the first page of size ``PageSize`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LaunchPathSummaries': [
                {
                    'Id': 'string',
                    'ConstraintSummaries': [
                        {
                            'Type': 'string',
                            'Description': 'string'
                        },
                    ],
                    'Tags': [
                        {
                            'Key': 'string',
                            'Value': 'string'
                        },
                    ],
                    'Name': 'string'
                },
            ],
            'NextPageToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **LaunchPathSummaries** *(list) --* 

          List of launch path information summaries for the specified ``PageToken`` .

          
          

          - *(dict) --* 

            Summary information about a path for a user to have access to a specified product.

            
            

            - **Id** *(string) --* 

              The unique identifier of the product path.

              
            

            - **ConstraintSummaries** *(list) --* 

              List of constraints on the portfolio-product relationship.

              
              

              - *(dict) --* 

                An administrator-specified constraint to apply when provisioning a product.

                
                

                - **Type** *(string) --* 

                  The type of the constraint. 

                  
                

                - **Description** *(string) --* 

                  The text description of the constraint.

                  
            
          
            

            - **Tags** *(list) --* 

              List of tags used by this launch path.

              
              

              - *(dict) --* 

                Optional key/value pairs to associate with this provisioning. These tags are propagated to the resources created in the provisioning.

                
                

                - **Key** *(string) --* 

                  The ``ProvisioningArtifactParameter.TagKey`` parameter from  DescribeProvisioningParameters .

                  
                

                - **Value** *(string) --* 

                  The esired value for this key.

                  
            
          
            

            - **Name** *(string) --* 

              Corresponds to the name of the portfolio to which the user was assigned.

              
        
      
        

        - **NextPageToken** *(string) --* 

          The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

          
    

  .. py:method:: list_record_history(**kwargs)

    

    Returns a paginated list of all performed requests, in the form of RecordDetails objects that are filtered as specified.

    

    **Request Syntax** 
    ::

      response = client.list_record_history(
          AcceptLanguage='string',
          SearchFilter={
              'Key': 'string',
              'Value': 'string'
          },
          PageSize=123,
          PageToken='string'
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type SearchFilter: dict
    :param SearchFilter: 

      (Optional) The filter to limit search results. 

      

    
      - **Key** *(string) --* 

        The filter key.

        

      
      - **Value** *(string) --* 

        The filter value for ``Key`` .

        

      
    
    :type PageSize: integer
    :param PageSize: 

      The maximum number of items to return in the results. If more results exist than fit in the specified ``PageSize`` , the value of ``NextPageToken`` in the response is non-null.

      

    
    :type PageToken: string
    :param PageToken: 

      The page token of the first page retrieve. If null, this retrieves the first page of size ``PageSize`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RecordDetails': [
                {
                    'RecordId': 'string',
                    'ProvisionedProductName': 'string',
                    'Status': 'IN_PROGRESS'|'SUCCEEDED'|'ERROR',
                    'CreatedTime': datetime(2015, 1, 1),
                    'UpdatedTime': datetime(2015, 1, 1),
                    'ProvisionedProductType': 'string',
                    'RecordType': 'string',
                    'ProvisionedProductId': 'string',
                    'ProductId': 'string',
                    'ProvisioningArtifactId': 'string',
                    'PathId': 'string',
                    'RecordErrors': [
                        {
                            'Code': 'string',
                            'Description': 'string'
                        },
                    ],
                    'RecordTags': [
                        {
                            'Key': 'string',
                            'Value': 'string'
                        },
                    ]
                },
            ],
            'NextPageToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **RecordDetails** *(list) --* 

          A list of record detail objects, listed in reverse chronological order.

          
          

          - *(dict) --* 

            The full details of a specific ProvisionedProduct object.

            
            

            - **RecordId** *(string) --* 

              The identifier of the ProvisionedProduct object record.

              
            

            - **ProvisionedProductName** *(string) --* 

              The user-friendly name of the ProvisionedProduct object.

              
            

            - **Status** *(string) --* 

              The status of the ProvisionedProduct object.

              
            

            - **CreatedTime** *(datetime) --* 

              The time when the record for the ProvisionedProduct object was created.

              
            

            - **UpdatedTime** *(datetime) --* 

              The time when the record for the ProvisionedProduct object was last updated.

              
            

            - **ProvisionedProductType** *(string) --* 

              The type of the ProvisionedProduct object.

              
            

            - **RecordType** *(string) --* 

              The record type for this record.

              
            

            - **ProvisionedProductId** *(string) --* 

              The identifier of the ProvisionedProduct object.

              
            

            - **ProductId** *(string) --* 

              The identifier of the product.

              
            

            - **ProvisioningArtifactId** *(string) --* 

              The provisioning artifact identifier for this product.

              
            

            - **PathId** *(string) --* 

              The identifier of the path for this product's provisioning.

              
            

            - **RecordErrors** *(list) --* 

              A list of errors that occurred while processing the request.

              
              

              - *(dict) --* 

                The error code and description resulting from an operation.

                
                

                - **Code** *(string) --* 

                  The numeric value of the error.

                  
                

                - **Description** *(string) --* 

                  The text description of the error.

                  
            
          
            

            - **RecordTags** *(list) --* 

              List of tags associated with this record.

              
              

              - *(dict) --* 

                A tag associated with the record, stored as a key-value pair.

                
                

                - **Key** *(string) --* 

                  The key for this tag.

                  
                

                - **Value** *(string) --* 

                  The value for this tag.

                  
            
          
        
      
        

        - **NextPageToken** *(string) --* 

          The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

          
    

  .. py:method:: provision_product(**kwargs)

    

    Requests a *Provision* of a specified product. A *ProvisionedProduct* is a resourced instance for a product. For example, provisioning a CloudFormation-template-backed product results in launching a CloudFormation stack and all the underlying resources that come with it. 

     

    You can check the status of this request using the  DescribeRecord operation.

    

    **Request Syntax** 
    ::

      response = client.provision_product(
          AcceptLanguage='string',
          ProductId='string',
          ProvisioningArtifactId='string',
          PathId='string',
          ProvisionedProductName='string',
          ProvisioningParameters=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ],
          NotificationArns=[
              'string',
          ],
          ProvisionToken='string'
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type ProductId: string
    :param ProductId: **[REQUIRED]** 

      The identifier of the product.

      

    
    :type ProvisioningArtifactId: string
    :param ProvisioningArtifactId: **[REQUIRED]** 

      The provisioning artifact identifier for this product.

      

    
    :type PathId: string
    :param PathId: 

      The identifier of the path for this product's provisioning. This value is optional if the product has a default path, and is required if there is more than one path for the specified product.

      

    
    :type ProvisionedProductName: string
    :param ProvisionedProductName: **[REQUIRED]** 

      A user-friendly name to identify the ProvisionedProduct object. This value must be unique for the AWS account and cannot be updated after the product is provisioned.

      

    
    :type ProvisioningParameters: list
    :param ProvisioningParameters: 

      Parameters specified by the administrator that are required for provisioning the product.

      

    
      - *(dict) --* 

        The arameter key/value pairs used to provision a product.

        

      
        - **Key** *(string) --* 

          The ``ProvisioningArtifactParameter.ParameterKey`` parameter from  DescribeProvisioningParameters .

          

        
        - **Value** *(string) --* 

          The value to use for provisioning. Any constraints on this value can be found in ``ProvisioningArtifactParameter`` for ``Key`` .

          

        
      
  
    :type Tags: list
    :param Tags: 

      (Optional) A list of tags to use as provisioning options.

      

    
      - *(dict) --* 

        Optional key/value pairs to associate with this provisioning. These tags are propagated to the resources created in the provisioning.

        

      
        - **Key** *(string) --* 

          The ``ProvisioningArtifactParameter.TagKey`` parameter from  DescribeProvisioningParameters .

          

        
        - **Value** *(string) --* 

          The esired value for this key.

          

        
      
  
    :type NotificationArns: list
    :param NotificationArns: 

      Passed to CloudFormation. The SNS topic ARNs to which to publish stack-related events.

      

    
      - *(string) --* 

      
  
    :type ProvisionToken: string
    :param ProvisionToken: **[REQUIRED]** 

      An idempotency token that uniquely identifies the provisioning request. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RecordDetail': {
                'RecordId': 'string',
                'ProvisionedProductName': 'string',
                'Status': 'IN_PROGRESS'|'SUCCEEDED'|'ERROR',
                'CreatedTime': datetime(2015, 1, 1),
                'UpdatedTime': datetime(2015, 1, 1),
                'ProvisionedProductType': 'string',
                'RecordType': 'string',
                'ProvisionedProductId': 'string',
                'ProductId': 'string',
                'ProvisioningArtifactId': 'string',
                'PathId': 'string',
                'RecordErrors': [
                    {
                        'Code': 'string',
                        'Description': 'string'
                    },
                ],
                'RecordTags': [
                    {
                        'Key': 'string',
                        'Value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **RecordDetail** *(dict) --* 

          The detailed result of the  ProvisionProduct request, containing the inputs made to that request, the current state of the request, a pointer to the ProvisionedProduct object of the request, and a list of any errors that the request encountered. 

          
          

          - **RecordId** *(string) --* 

            The identifier of the ProvisionedProduct object record.

            
          

          - **ProvisionedProductName** *(string) --* 

            The user-friendly name of the ProvisionedProduct object.

            
          

          - **Status** *(string) --* 

            The status of the ProvisionedProduct object.

            
          

          - **CreatedTime** *(datetime) --* 

            The time when the record for the ProvisionedProduct object was created.

            
          

          - **UpdatedTime** *(datetime) --* 

            The time when the record for the ProvisionedProduct object was last updated.

            
          

          - **ProvisionedProductType** *(string) --* 

            The type of the ProvisionedProduct object.

            
          

          - **RecordType** *(string) --* 

            The record type for this record.

            
          

          - **ProvisionedProductId** *(string) --* 

            The identifier of the ProvisionedProduct object.

            
          

          - **ProductId** *(string) --* 

            The identifier of the product.

            
          

          - **ProvisioningArtifactId** *(string) --* 

            The provisioning artifact identifier for this product.

            
          

          - **PathId** *(string) --* 

            The identifier of the path for this product's provisioning.

            
          

          - **RecordErrors** *(list) --* 

            A list of errors that occurred while processing the request.

            
            

            - *(dict) --* 

              The error code and description resulting from an operation.

              
              

              - **Code** *(string) --* 

                The numeric value of the error.

                
              

              - **Description** *(string) --* 

                The text description of the error.

                
          
        
          

          - **RecordTags** *(list) --* 

            List of tags associated with this record.

            
            

            - *(dict) --* 

              A tag associated with the record, stored as a key-value pair.

              
              

              - **Key** *(string) --* 

                The key for this tag.

                
              

              - **Value** *(string) --* 

                The value for this tag.

                
          
        
      
    

  .. py:method:: scan_provisioned_products(**kwargs)

    

    Returns a paginated list of all the ProvisionedProduct objects that are currently available (not terminated). 

    

    **Request Syntax** 
    ::

      response = client.scan_provisioned_products(
          AcceptLanguage='string',
          PageSize=123,
          PageToken='string'
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type PageSize: integer
    :param PageSize: 

      The maximum number of items to return in the results. If more results exist than fit in the specified ``PageSize`` , the value of ``NextPageToken`` in the response is non-null.

      

    
    :type PageToken: string
    :param PageToken: 

      The page token of the first page retrieve. If null, this retrieves the first page of size ``PageSize`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ProvisionedProducts': [
                {
                    'Name': 'string',
                    'Arn': 'string',
                    'Type': 'string',
                    'Id': 'string',
                    'Status': 'IN_PROGRESS'|'SUCCEEDED'|'ERROR',
                    'StatusMessage': 'string',
                    'CreatedTime': datetime(2015, 1, 1),
                    'IdempotencyToken': 'string',
                    'LastRecordId': 'string'
                },
            ],
            'NextPageToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ProvisionedProducts** *(list) --* 

          A list of ProvisionedProduct detail objects.

          
          

          - *(dict) --* 

            Detailed information about a ProvisionedProduct object.

            
            

            - **Name** *(string) --* 

              The user-friendly name of the ProvisionedProduct object.

              
            

            - **Arn** *(string) --* 

              The ARN associated with the ProvisionedProduct object.

              
            

            - **Type** *(string) --* 

              The type of the ProvisionedProduct object.

              
            

            - **Id** *(string) --* 

              The identifier of the ProvisionedProduct object.

              
            

            - **Status** *(string) --* 

              The current status of the ProvisionedProduct.

              
            

            - **StatusMessage** *(string) --* 

              The current status message of the ProvisionedProduct.

              
            

            - **CreatedTime** *(datetime) --* 

              The time the ProvisionedProduct was created.

              
            

            - **IdempotencyToken** *(string) --* 

              An idempotency token that uniquely identifies this ProvisionedProduct.

              
            

            - **LastRecordId** *(string) --* 

              The record identifier of the last request performed on this ProvisionedProduct object.

              
        
      
        

        - **NextPageToken** *(string) --* 

          The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

          
    

  .. py:method:: search_products(**kwargs)

    

    Returns a paginated list all of the ``Products`` objects to which the caller has access. 

     

    The output of this operation can be used as input for other operations, such as  DescribeProductView .

    

    **Request Syntax** 
    ::

      response = client.search_products(
          AcceptLanguage='string',
          Filters={
              'string': [
                  'string',
              ]
          },
          PageSize=123,
          SortBy='Title'|'VersionCount'|'CreationDate',
          SortOrder='ASCENDING'|'DESCENDING',
          PageToken='string'
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type Filters: dict
    :param Filters: 

      (Optional) The list of filters with which to limit search results. If no search filters are specified, the output is all the products to which the calling user has access. 

      

    
      - *(string) --* 

      
        - *(list) --* 

        
          - *(string) --* 

          
      
  

    :type PageSize: integer
    :param PageSize: 

      The maximum number of items to return in the results. If more results exist than fit in the specified ``PageSize`` , the value of ``NextPageToken`` in the response is non-null.

      

    
    :type SortBy: string
    :param SortBy: 

      (Optional) The sort field specifier. If no value is specified, results are not sorted.

      

    
    :type SortOrder: string
    :param SortOrder: 

      (Optional) The sort order specifier. If no value is specified, results are not sorted.

      

    
    :type PageToken: string
    :param PageToken: 

      The page token of the first page retrieve. If null, this retrieves the first page of size ``PageSize`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ProductViewSummaries': [
                {
                    'Id': 'string',
                    'ProductId': 'string',
                    'Name': 'string',
                    'Owner': 'string',
                    'ShortDescription': 'string',
                    'Type': 'string',
                    'Distributor': 'string',
                    'HasDefaultPath': True|False,
                    'SupportEmail': 'string',
                    'SupportDescription': 'string',
                    'SupportUrl': 'string'
                },
            ],
            'ProductViewAggregations': {
                'string': [
                    {
                        'Value': 'string',
                        'ApproximateCount': 123
                    },
                ]
            },
            'NextPageToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **ProductViewSummaries** *(list) --* 

          A list of the product view summary objects.

          
          

          - *(dict) --* 

            The summary metadata about the specified product.

            
            

            - **Id** *(string) --* 

              The product view identifier.

              
            

            - **ProductId** *(string) --* 

              The product identifier.

              
            

            - **Name** *(string) --* 

              The name of the product.

              
            

            - **Owner** *(string) --* 

              The owner of the product. Contact the product administrator for the significance of this value.

              
            

            - **ShortDescription** *(string) --* 

              Short description of the product.

              
            

            - **Type** *(string) --* 

              The product type. Contact the product administrator for the significance of this value.

              
            

            - **Distributor** *(string) --* 

              The distributor of the product. Contact the product administrator for the significance of this value.

              
            

            - **HasDefaultPath** *(boolean) --* 

              A value of ``false`` indicates that the product does not have a default path, while a value of ``true`` indicates that it does. If it's false, call  ListLaunchPaths to disambiguate between paths. If true,  ListLaunchPaths is not required, and the output of the  ProductViewSummary operation can be used directly with  DescribeProvisioningParameters .

              
            

            - **SupportEmail** *(string) --* 

              The email contact information to obtain support for this Product.

              
            

            - **SupportDescription** *(string) --* 

              The description of the support for this Product.

              
            

            - **SupportUrl** *(string) --* 

              The URL information to obtain support for this Product.

              
        
      
        

        - **ProductViewAggregations** *(dict) --* 

          A list of the product view aggregation value objects.

          
          

          - *(string) --* 
            

            - *(list) --* 
              

              - *(dict) --* 

                A single product view aggregation value/count pair, containing metadata about each product to which the calling user has access.

                
                

                - **Value** *(string) --* 

                  The value of the product view aggregation.

                  
                

                - **ApproximateCount** *(integer) --* 

                  An approximate count of the products that match the value.

                  
            
          
      
    
        

        - **NextPageToken** *(string) --* 

          The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

          
    

  .. py:method:: terminate_provisioned_product(**kwargs)

    

    Requests termination of an existing ProvisionedProduct object. If there are ``Tags`` associated with the object, they are terminated when the ProvisionedProduct object is terminated. 

     

    This operation does not delete any records associated with the ProvisionedProduct object.

     

    You can check the status of this request using the  DescribeRecord operation.

    

    **Request Syntax** 
    ::

      response = client.terminate_provisioned_product(
          ProvisionedProductName='string',
          ProvisionedProductId='string',
          TerminateToken='string',
          IgnoreErrors=True|False,
          AcceptLanguage='string'
      )
    :type ProvisionedProductName: string
    :param ProvisionedProductName: 

      The name of the ProvisionedProduct object to terminate. You must specify either ``ProvisionedProductName`` or ``ProvisionedProductId`` , but not both.

      

    
    :type ProvisionedProductId: string
    :param ProvisionedProductId: 

      The identifier of the ProvisionedProduct object to terminate. You must specify either ``ProvisionedProductName`` or ``ProvisionedProductId`` , but not both.

      

    
    :type TerminateToken: string
    :param TerminateToken: **[REQUIRED]** 

      An idempotency token that uniquely identifies the termination request. This token is only valid during the termination process. After the ProvisionedProduct object is terminated, further requests to terminate the same ProvisionedProduct object always return **ResourceNotFound** regardless of the value of ``TerminateToken`` .

      

    
    :type IgnoreErrors: boolean
    :param IgnoreErrors: 

      Optional Boolean parameter. If set to true, AWS Service Catalog stops managing the specified ProvisionedProduct object even if it cannot delete the underlying resources.

      

    
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RecordDetail': {
                'RecordId': 'string',
                'ProvisionedProductName': 'string',
                'Status': 'IN_PROGRESS'|'SUCCEEDED'|'ERROR',
                'CreatedTime': datetime(2015, 1, 1),
                'UpdatedTime': datetime(2015, 1, 1),
                'ProvisionedProductType': 'string',
                'RecordType': 'string',
                'ProvisionedProductId': 'string',
                'ProductId': 'string',
                'ProvisioningArtifactId': 'string',
                'PathId': 'string',
                'RecordErrors': [
                    {
                        'Code': 'string',
                        'Description': 'string'
                    },
                ],
                'RecordTags': [
                    {
                        'Key': 'string',
                        'Value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **RecordDetail** *(dict) --* 

          The detailed result of the  TerminateProvisionedProduct request, containing the inputs made to that request, the current state of the request, a pointer to the ProvisionedProduct object that the request is modifying, and a list of any errors that the request encountered.

          
          

          - **RecordId** *(string) --* 

            The identifier of the ProvisionedProduct object record.

            
          

          - **ProvisionedProductName** *(string) --* 

            The user-friendly name of the ProvisionedProduct object.

            
          

          - **Status** *(string) --* 

            The status of the ProvisionedProduct object.

            
          

          - **CreatedTime** *(datetime) --* 

            The time when the record for the ProvisionedProduct object was created.

            
          

          - **UpdatedTime** *(datetime) --* 

            The time when the record for the ProvisionedProduct object was last updated.

            
          

          - **ProvisionedProductType** *(string) --* 

            The type of the ProvisionedProduct object.

            
          

          - **RecordType** *(string) --* 

            The record type for this record.

            
          

          - **ProvisionedProductId** *(string) --* 

            The identifier of the ProvisionedProduct object.

            
          

          - **ProductId** *(string) --* 

            The identifier of the product.

            
          

          - **ProvisioningArtifactId** *(string) --* 

            The provisioning artifact identifier for this product.

            
          

          - **PathId** *(string) --* 

            The identifier of the path for this product's provisioning.

            
          

          - **RecordErrors** *(list) --* 

            A list of errors that occurred while processing the request.

            
            

            - *(dict) --* 

              The error code and description resulting from an operation.

              
              

              - **Code** *(string) --* 

                The numeric value of the error.

                
              

              - **Description** *(string) --* 

                The text description of the error.

                
          
        
          

          - **RecordTags** *(list) --* 

            List of tags associated with this record.

            
            

            - *(dict) --* 

              A tag associated with the record, stored as a key-value pair.

              
              

              - **Key** *(string) --* 

                The key for this tag.

                
              

              - **Value** *(string) --* 

                The value for this tag.

                
          
        
      
    

  .. py:method:: update_provisioned_product(**kwargs)

    

    Requests updates to the configuration of an existing ProvisionedProduct object. If there are tags associated with the object, they cannot be updated or added with this operation. Depending on the specific updates requested, this operation may update with no interruption, with some interruption, or replace the ProvisionedProduct object entirely. 

     

    You can check the status of this request using the  DescribeRecord operation.

    

    **Request Syntax** 
    ::

      response = client.update_provisioned_product(
          AcceptLanguage='string',
          ProvisionedProductName='string',
          ProvisionedProductId='string',
          ProductId='string',
          ProvisioningArtifactId='string',
          PathId='string',
          ProvisioningParameters=[
              {
                  'Key': 'string',
                  'Value': 'string',
                  'UsePreviousValue': True|False
              },
          ],
          UpdateToken='string'
      )
    :type AcceptLanguage: string
    :param AcceptLanguage: 

      Optional language code. Supported language codes are as follows:

       

      "en" (English)

       

      "jp" (Japanese)

       

      "zh" (Chinese)

       

      If no code is specified, "en" is used as the default.

      

    
    :type ProvisionedProductName: string
    :param ProvisionedProductName: 

      The updated name of the ProvisionedProduct object . You must specify either ``ProvisionedProductName`` or ``ProvisionedProductId`` , but not both.

      

    
    :type ProvisionedProductId: string
    :param ProvisionedProductId: 

      The identifier of the ProvisionedProduct object to update. You must specify either ``ProvisionedProductName`` or ``ProvisionedProductId`` , but not both.

      

    
    :type ProductId: string
    :param ProductId: 

      The identifier of the ProvisionedProduct object.

      

    
    :type ProvisioningArtifactId: string
    :param ProvisioningArtifactId: 

      The provisioning artifact identifier for this product.

      

    
    :type PathId: string
    :param PathId: 

      The identifier of the path to use in the updated ProvisionedProduct object. This value is optional if the product has a default path, and is required if there is more than one path for the specified product.

      

    
    :type ProvisioningParameters: list
    :param ProvisioningParameters: 

      A list of ``ProvisioningParameter`` objects used to update the ProvisionedProduct object.

      

    
      - *(dict) --* 

        The parameter key/value pair used to update a ProvisionedProduct object. If ``UsePreviousValue`` is set to true, ``Value`` is ignored and the value for ``Key`` is kept as previously set (current value).

        

      
        - **Key** *(string) --* 

          The ``ProvisioningArtifactParameter.ParameterKey`` parameter from  DescribeProvisioningParameters .

          

        
        - **Value** *(string) --* 

          The value to use for updating the product provisioning. Any constraints on this value can be found in the ``ProvisioningArtifactParameter`` parameter for ``Key`` .

          

        
        - **UsePreviousValue** *(boolean) --* 

          If true, uses the currently set value for ``Key`` , ignoring ``UpdateProvisioningParameter.Value`` .

          

        
      
  
    :type UpdateToken: string
    :param UpdateToken: **[REQUIRED]** 

      The idempotency token that uniquely identifies the provisioning update request.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'RecordDetail': {
                'RecordId': 'string',
                'ProvisionedProductName': 'string',
                'Status': 'IN_PROGRESS'|'SUCCEEDED'|'ERROR',
                'CreatedTime': datetime(2015, 1, 1),
                'UpdatedTime': datetime(2015, 1, 1),
                'ProvisionedProductType': 'string',
                'RecordType': 'string',
                'ProvisionedProductId': 'string',
                'ProductId': 'string',
                'ProvisioningArtifactId': 'string',
                'PathId': 'string',
                'RecordErrors': [
                    {
                        'Code': 'string',
                        'Description': 'string'
                    },
                ],
                'RecordTags': [
                    {
                        'Key': 'string',
                        'Value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **RecordDetail** *(dict) --* 

          The detailed result of the  UpdateProvisionedProduct request, containing the inputs made to that request, the current state of the request, a pointer to the ProvisionedProduct object that the request is modifying, and a list of any errors that the request encountered.

          
          

          - **RecordId** *(string) --* 

            The identifier of the ProvisionedProduct object record.

            
          

          - **ProvisionedProductName** *(string) --* 

            The user-friendly name of the ProvisionedProduct object.

            
          

          - **Status** *(string) --* 

            The status of the ProvisionedProduct object.

            
          

          - **CreatedTime** *(datetime) --* 

            The time when the record for the ProvisionedProduct object was created.

            
          

          - **UpdatedTime** *(datetime) --* 

            The time when the record for the ProvisionedProduct object was last updated.

            
          

          - **ProvisionedProductType** *(string) --* 

            The type of the ProvisionedProduct object.

            
          

          - **RecordType** *(string) --* 

            The record type for this record.

            
          

          - **ProvisionedProductId** *(string) --* 

            The identifier of the ProvisionedProduct object.

            
          

          - **ProductId** *(string) --* 

            The identifier of the product.

            
          

          - **ProvisioningArtifactId** *(string) --* 

            The provisioning artifact identifier for this product.

            
          

          - **PathId** *(string) --* 

            The identifier of the path for this product's provisioning.

            
          

          - **RecordErrors** *(list) --* 

            A list of errors that occurred while processing the request.

            
            

            - *(dict) --* 

              The error code and description resulting from an operation.

              
              

              - **Code** *(string) --* 

                The numeric value of the error.

                
              

              - **Description** *(string) --* 

                The text description of the error.

                
          
        
          

          - **RecordTags** *(list) --* 

            List of tags associated with this record.

            
            

            - *(dict) --* 

              A tag associated with the record, stored as a key-value pair.

              
              

              - **Key** *(string) --* 

                The key for this tag.

                
              

              - **Value** *(string) --* 

                The value for this tag.

                
          
        
      
    