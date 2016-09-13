

.. _Enable custom authorization: http://docs.aws.amazon.com/apigateway/latest/developerguide/use-custom-authorizer.html
.. _Models and Mappings: http://docs.aws.amazon.com/apigateway/latest/developerguide/models-mappings.html
.. _Manage Usage in a Usage Plan: http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-create-usage-plans-with-console.html#api-gateway-usage-plan-manage-usage
.. _Creating an API: http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-create-api.html
.. _$util.urlDecode(): http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-mapping-template-reference.html#util-templat-reference
.. _AWS SDKs: https://aws.amazon.com/tools/
.. _API Gateway Error Codes: http://docs.aws.amazon.com/apigateway/api-reference/handling-errors/#api-error-codes
.. _Amazon CloudFront documentation: http://aws.amazon.com/documentation/cloudfront/
.. _ISO 8601 format: http://www.iso.org/iso/home/standards/iso8601.htm
.. _Deploying API in Stages: http://docs.aws.amazon.com/apigateway/latest/developerguide/stages.html
.. _open identity claims: http://openid.net/specs/openid-connect-core-1_0.html#StandardClaims
.. _Create and Use Usage Plans: http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-api-usage-plans.html
.. _Test API using the API Gateway console: http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-test-method.html#how-to-test-method-console
.. _Deploying an API: http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-deploy-api.html
.. _RFC-3986 specification: https://www.ietf.org/rfc/rfc3986.txt
.. _Enable custom authorizers: http://docs.aws.amazon.com/apigateway/latest/developerguide/use-custom-authorizer.html
.. _Set up an API's method: http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-method-settings.html
.. _Mapping Templates: http://docs.aws.amazon.com/apigateway/latest/developerguide/models-mappings.html#models-mappings-mappings
.. _API Gateway Limits: http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-limits.html
.. _JSON Pointer: https://tools.ietf.org/html/draft-ietf-appsawg-json-pointer-08
.. _JSON-schema draft v4: http://json-schema.org/documentation.html
.. _AWS CLI: http://docs.aws.amazon.com/cli/latest/reference/apigateway/get-integration.html
.. _Velocity Template Language (VTL): http://velocity.apache.org/engine/devel/vtl-reference-guide.html
.. _Use Custom Domain Names: http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-custom-domains.html
.. _Create an API: http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-create-api.html
.. _Developer Guide: http://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html
.. _Deploy an API: http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-deploy-api.html
.. _Use Client-Side Certificate: http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-custom-domains.html
.. _API Key File Format: http://docs.aws.amazon.com/apigateway/latest/developerguide/api-key-file-format.html
.. _Use API Keys: http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-api-keys.html


**********
APIGateway
**********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: APIGateway.Client

  A low-level client representing Amazon API Gateway::

    
    import boto3
    
    client = boto3.client('apigateway')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_api_key`

  
  *   :py:meth:`create_authorizer`

  
  *   :py:meth:`create_base_path_mapping`

  
  *   :py:meth:`create_deployment`

  
  *   :py:meth:`create_domain_name`

  
  *   :py:meth:`create_model`

  
  *   :py:meth:`create_resource`

  
  *   :py:meth:`create_rest_api`

  
  *   :py:meth:`create_stage`

  
  *   :py:meth:`create_usage_plan`

  
  *   :py:meth:`create_usage_plan_key`

  
  *   :py:meth:`delete_api_key`

  
  *   :py:meth:`delete_authorizer`

  
  *   :py:meth:`delete_base_path_mapping`

  
  *   :py:meth:`delete_client_certificate`

  
  *   :py:meth:`delete_deployment`

  
  *   :py:meth:`delete_domain_name`

  
  *   :py:meth:`delete_integration`

  
  *   :py:meth:`delete_integration_response`

  
  *   :py:meth:`delete_method`

  
  *   :py:meth:`delete_method_response`

  
  *   :py:meth:`delete_model`

  
  *   :py:meth:`delete_resource`

  
  *   :py:meth:`delete_rest_api`

  
  *   :py:meth:`delete_stage`

  
  *   :py:meth:`delete_usage_plan`

  
  *   :py:meth:`delete_usage_plan_key`

  
  *   :py:meth:`flush_stage_authorizers_cache`

  
  *   :py:meth:`flush_stage_cache`

  
  *   :py:meth:`generate_client_certificate`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_account`

  
  *   :py:meth:`get_api_key`

  
  *   :py:meth:`get_api_keys`

  
  *   :py:meth:`get_authorizer`

  
  *   :py:meth:`get_authorizers`

  
  *   :py:meth:`get_base_path_mapping`

  
  *   :py:meth:`get_base_path_mappings`

  
  *   :py:meth:`get_client_certificate`

  
  *   :py:meth:`get_client_certificates`

  
  *   :py:meth:`get_deployment`

  
  *   :py:meth:`get_deployments`

  
  *   :py:meth:`get_domain_name`

  
  *   :py:meth:`get_domain_names`

  
  *   :py:meth:`get_export`

  
  *   :py:meth:`get_integration`

  
  *   :py:meth:`get_integration_response`

  
  *   :py:meth:`get_method`

  
  *   :py:meth:`get_method_response`

  
  *   :py:meth:`get_model`

  
  *   :py:meth:`get_model_template`

  
  *   :py:meth:`get_models`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_resource`

  
  *   :py:meth:`get_resources`

  
  *   :py:meth:`get_rest_api`

  
  *   :py:meth:`get_rest_apis`

  
  *   :py:meth:`get_sdk`

  
  *   :py:meth:`get_stage`

  
  *   :py:meth:`get_stages`

  
  *   :py:meth:`get_usage`

  
  *   :py:meth:`get_usage_plan`

  
  *   :py:meth:`get_usage_plan_key`

  
  *   :py:meth:`get_usage_plan_keys`

  
  *   :py:meth:`get_usage_plans`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`import_api_keys`

  
  *   :py:meth:`import_rest_api`

  
  *   :py:meth:`put_integration`

  
  *   :py:meth:`put_integration_response`

  
  *   :py:meth:`put_method`

  
  *   :py:meth:`put_method_response`

  
  *   :py:meth:`put_rest_api`

  
  *   :py:meth:`test_invoke_authorizer`

  
  *   :py:meth:`test_invoke_method`

  
  *   :py:meth:`update_account`

  
  *   :py:meth:`update_api_key`

  
  *   :py:meth:`update_authorizer`

  
  *   :py:meth:`update_base_path_mapping`

  
  *   :py:meth:`update_client_certificate`

  
  *   :py:meth:`update_deployment`

  
  *   :py:meth:`update_domain_name`

  
  *   :py:meth:`update_integration`

  
  *   :py:meth:`update_integration_response`

  
  *   :py:meth:`update_method`

  
  *   :py:meth:`update_method_response`

  
  *   :py:meth:`update_model`

  
  *   :py:meth:`update_resource`

  
  *   :py:meth:`update_rest_api`

  
  *   :py:meth:`update_stage`

  
  *   :py:meth:`update_usage`

  
  *   :py:meth:`update_usage_plan`

  

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


  .. py:method:: create_api_key(**kwargs)

    

    Create an  ApiKey resource. 

     `AWS CLI`_ 

    **Request Syntax** 
    ::

      response = client.create_api_key(
          name='string',
          description='string',
          enabled=True|False,
          generateDistinctId=True|False,
          value='string',
          stageKeys=[
              {
                  'restApiId': 'string',
                  'stageName': 'string'
              },
          ]
      )
    :type name: string
    :param name: 

      The name of the  ApiKey .

      

    
    :type description: string
    :param description: 

      The description of the  ApiKey .

      

    
    :type enabled: boolean
    :param enabled: 

      Specifies whether the  ApiKey can be used by callers.

      

    
    :type generateDistinctId: boolean
    :param generateDistinctId: 

      Specifies whether (``true`` ) or not (``false`` ) the key identifier is distinct from the created API key value.

      

    
    :type value: string
    :param value: 

      Specifies a value of the API key.

      

    
    :type stageKeys: list
    :param stageKeys: 

      DEPRECATED FOR USAGE PLANS - Specifies stages associated with the API key.

      

    
      - *(dict) --* 

        A reference to a unique stage identified in the format ``{restApiId}/{stage}`` .

        

      
        - **restApiId** *(string) --* 

          A list of  Stage resources that are associated with the  ApiKey resource.

          

        
        - **stageName** *(string) --* 

          The stage name in the  RestApi that the stage key references.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'value': 'string',
            'name': 'string',
            'description': 'string',
            'enabled': True|False,
            'createdDate': datetime(2015, 1, 1),
            'lastUpdatedDate': datetime(2015, 1, 1),
            'stageKeys': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A resource that can be distributed to callers for executing  Method resources that require an API key. API keys can be mapped to any  Stage on any  RestApi , which indicates that the callers with the API key can make requests to that stage.

          `Use API Keys`_  
        

        - **id** *(string) --* 

          The identifier of the API Key.

          
        

        - **value** *(string) --* 

          The value of the API Key.

          
        

        - **name** *(string) --* 

          The name of the API Key.

          
        

        - **description** *(string) --* 

          The description of the API Key.

          
        

        - **enabled** *(boolean) --* 

          Specifies whether the API Key can be used by callers.

          
        

        - **createdDate** *(datetime) --* 

          The date when the API Key was created, in `ISO 8601 format`_ .

          
        

        - **lastUpdatedDate** *(datetime) --* 

          When the API Key was last updated, in ISO 8601 format.

          
        

        - **stageKeys** *(list) --* 

          A list of  Stage resources that are associated with the  ApiKey resource.

          
          

          - *(string) --* 
      
    

  .. py:method:: create_authorizer(**kwargs)

    

    Adds a new  Authorizer resource to an existing  RestApi resource.

     `AWS CLI`_ 

    **Request Syntax** 
    ::

      response = client.create_authorizer(
          restApiId='string',
          name='string',
          type='TOKEN'|'COGNITO_USER_POOLS',
          providerARNs=[
              'string',
          ],
          authType='string',
          authorizerUri='string',
          authorizerCredentials='string',
          identitySource='string',
          identityValidationExpression='string',
          authorizerResultTtlInSeconds=123
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier under which the  Authorizer will be created.

      

    
    :type name: string
    :param name: **[REQUIRED]** 

      [Required] The name of the authorizer.

      

    
    :type type: string
    :param type: **[REQUIRED]** 

      [Required] The type of the authorizer.

      

    
    :type providerARNs: list
    :param providerARNs: 

      A list of the Cognito Your User Pool authorizer's provider ARNs.

      

    
      - *(string) --* 

      
  
    :type authType: string
    :param authType: 

      Optional customer-defined field, used in Swagger imports/exports. Has no functional impact.

      

    
    :type authorizerUri: string
    :param authorizerUri: 

      [Required] Specifies the authorizer's Uniform Resource Identifier (URI).

      

    
    :type authorizerCredentials: string
    :param authorizerCredentials: 

      Specifies the credentials required for the authorizer, if any.

      

    
    :type identitySource: string
    :param identitySource: **[REQUIRED]** 

      [Required] The source of the identity in an incoming request.

      

    
    :type identityValidationExpression: string
    :param identityValidationExpression: 

      A validation expression for the incoming identity.

      

    
    :type authorizerResultTtlInSeconds: integer
    :param authorizerResultTtlInSeconds: 

      The TTL of cached authorizer results.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'type': 'TOKEN'|'COGNITO_USER_POOLS',
            'providerARNs': [
                'string',
            ],
            'authType': 'string',
            'authorizerUri': 'string',
            'authorizerCredentials': 'string',
            'identitySource': 'string',
            'identityValidationExpression': 'string',
            'authorizerResultTtlInSeconds': 123
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an authorization layer for methods. If enabled on a method, API Gateway will activate the authorizer when a client calls the method.

          `Enable custom authorization`_  
        

        - **id** *(string) --* 

          The identifier for the authorizer resource.

          
        

        - **name** *(string) --* 

          [Required] The name of the authorizer.

          
        

        - **type** *(string) --* 

          [Required] The type of the authorizer. Currently, the only valid type is TOKEN.

          
        

        - **providerARNs** *(list) --* 

          A list of the provider ARNs of the authorizer.

          
          

          - *(string) --* 
      
        

        - **authType** *(string) --* 

          Optional customer-defined field, used in Swagger imports/exports. Has no functional impact.

          
        

        - **authorizerUri** *(string) --* 

          [Required] Specifies the authorizer's Uniform Resource Identifier (URI). For TOKEN authorizers, this must be a well-formed Lambda function URI. The URI should be of the form ``arn:aws:apigateway:{region}:lambda:path/{service_api}`` . ``Region`` is used to determine the right endpoint. In this case, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` . For Lambda functions, this is usually of the form /2015-03-31/functions/[FunctionARN]/invocations

          
        

        - **authorizerCredentials** *(string) --* 

          Specifies the credentials required for the authorizer, if any. Two options are available. To specify an IAM role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To use resource-based permissions on the Lambda function, specify null.

          
        

        - **identitySource** *(string) --* 

          [Required] The source of the identity in an incoming request. For TOKEN authorizers, this value is a mapping expression with the same syntax as integration parameter mappings. The only valid source for tokens is 'header', so the expression should match 'method.request.header.[headerName]'. The value of the header '[headerName]' will be interpreted as the incoming token.

          
        

        - **identityValidationExpression** *(string) --* 

          A validation expression for the incoming identity. For TOKEN authorizers, this value should be a regular expression. The incoming token from the client is matched against this expression, and will proceed if the token matches. If the token doesn't match, the client receives a 401 Unauthorized response.

          
        

        - **authorizerResultTtlInSeconds** *(integer) --* 

          The TTL in seconds of cached authorizer results. If greater than 0, API Gateway will cache authorizer responses. If this field is not set, the default value is 300. The maximum value is 3600, or 1 hour.

          
    

  .. py:method:: create_base_path_mapping(**kwargs)

    

    Creates a new  BasePathMapping resource.

    

    **Request Syntax** 
    ::

      response = client.create_base_path_mapping(
          domainName='string',
          basePath='string',
          restApiId='string',
          stage='string'
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The domain name of the  BasePathMapping resource to create.

      

    
    :type basePath: string
    :param basePath: 

      The base path name that callers of the API must provide as part of the URL after the domain name. This value must be unique for all of the mappings across a single API. Leave this blank if you do not want callers to specify a base path name after the domain name.

      

    
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The name of the API that you want to apply this mapping to.

      

    
    :type stage: string
    :param stage: 

      The name of the API's stage that you want to use for this mapping. Leave this blank if you do not want callers to explicitly specify the stage name after any base path name.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'basePath': 'string',
            'restApiId': 'string',
            'stage': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the base path that callers of the API must provide as part of the URL after the domain name.

         A custom domain name plus a ``BasePathMapping`` specification identifies a deployed  RestApi in a given stage of the owner  Account .  `Use Custom Domain Names`_  
        

        - **basePath** *(string) --* 

          The base path name that callers of the API must provide as part of the URL after the domain name.

          
        

        - **restApiId** *(string) --* 

          The name of the API.

          
        

        - **stage** *(string) --* 

          The name of the API's stage.

          
    

  .. py:method:: create_deployment(**kwargs)

    

    Creates a  Deployment resource, which makes a specified  RestApi callable over the internet.

    

    **Request Syntax** 
    ::

      response = client.create_deployment(
          restApiId='string',
          stageName='string',
          stageDescription='string',
          description='string',
          cacheClusterEnabled=True|False,
          cacheClusterSize='0.5'|'1.6'|'6.1'|'13.5'|'28.4'|'58.2'|'118'|'237',
          variables={
              'string': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi resource identifier for the  Deployment resource to create.

      

    
    :type stageName: string
    :param stageName: **[REQUIRED]** 

      The name of the  Stage resource for the  Deployment resource to create.

      

    
    :type stageDescription: string
    :param stageDescription: 

      The description of the  Stage resource for the  Deployment resource to create.

      

    
    :type description: string
    :param description: 

      The description for the  Deployment resource to create.

      

    
    :type cacheClusterEnabled: boolean
    :param cacheClusterEnabled: 

      Enables a cache cluster for the  Stage resource specified in the input.

      

    
    :type cacheClusterSize: string
    :param cacheClusterSize: 

      Specifies the cache cluster size for the  Stage resource specified in the input, if a cache cluster is enabled.

      

    
    :type variables: dict
    :param variables: 

      A map that defines the stage variables for the  Stage resource that is associated with the new deployment. Variable names can have alphanumeric and underscore characters, and the values must match ``[A-Za-z0-9-._~:/?#=,]+`` .

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'description': 'string',
            'createdDate': datetime(2015, 1, 1),
            'apiSummary': {
                'string': {
                    'string': {
                        'authorizationType': 'string',
                        'apiKeyRequired': True|False
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        An immutable representation of a  RestApi resource that can be called by users using  Stages . A deployment must be associated with a  Stage for it to be callable over the Internet.

         To create a deployment, call ``POST`` on the  Deployments resource of a  RestApi . To view, update, or delete a deployment, call ``GET`` , ``PATCH`` , or ``DELETE`` on the specified deployment resource (``/restapis/{restapi_id}/deployments/{deployment_id}`` ).  RestApi ,  Deployments ,  Stage , `AWS CLI`_ , `AWS SDKs`_  
        

        - **id** *(string) --* 

          The identifier for the deployment resource.

          
        

        - **description** *(string) --* 

          The description for the deployment resource.

          
        

        - **createdDate** *(datetime) --* 

          The date and time that the deployment resource was created.

          
        

        - **apiSummary** *(dict) --* 

          A summary of the  RestApi at the date and time that the deployment resource was created.

          
          

          - *(string) --* 
            

            - *(dict) --* 
              

              - *(string) --* 
                

                - *(dict) --* 

                  Represents a summary of a  Method resource, given a particular date and time.

                  
                  

                  - **authorizationType** *(string) --* 

                    Specifies the type of authorization used for the method.

                    
                  

                  - **apiKeyRequired** *(boolean) --* 

                    Specifies whether the method requires a valid  ApiKey .

                    
              
          
        
      
    
    

  .. py:method:: create_domain_name(**kwargs)

    

    Creates a new domain name.

    

    **Request Syntax** 
    ::

      response = client.create_domain_name(
          domainName='string',
          certificateName='string',
          certificateBody='string',
          certificatePrivateKey='string',
          certificateChain='string'
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The name of the  DomainName resource.

      

    
    :type certificateName: string
    :param certificateName: **[REQUIRED]** 

      The name of the certificate.

      

    
    :type certificateBody: string
    :param certificateBody: **[REQUIRED]** 

      The body of the server certificate provided by your certificate authority.

      

    
    :type certificatePrivateKey: string
    :param certificatePrivateKey: **[REQUIRED]** 

      Your certificate's private key.

      

    
    :type certificateChain: string
    :param certificateChain: **[REQUIRED]** 

      The intermediate certificates and optionally the root certificate, one after the other without any blank lines. If you include the root certificate, your certificate chain must start with intermediate certificates and end with the root certificate. Use the intermediate certificates that were provided by your certificate authority. Do not include any intermediaries that are not in the chain of trust path.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'domainName': 'string',
            'certificateName': 'string',
            'certificateUploadDate': datetime(2015, 1, 1),
            'distributionDomainName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a domain name that is contained in a simpler, more intuitive URL that can be called.

          `Use Client-Side Certificate`_  
        

        - **domainName** *(string) --* 

          The name of the  DomainName resource.

          
        

        - **certificateName** *(string) --* 

          The name of the certificate.

          
        

        - **certificateUploadDate** *(datetime) --* 

          The date when the certificate was uploaded, in `ISO 8601 format`_ .

          
        

        - **distributionDomainName** *(string) --* 

          The domain name of the Amazon CloudFront distribution. For more information, see the `Amazon CloudFront documentation`_ .

          
    

  .. py:method:: create_model(**kwargs)

    

    Adds a new  Model resource to an existing  RestApi resource.

    

    **Request Syntax** 
    ::

      response = client.create_model(
          restApiId='string',
          name='string',
          description='string',
          schema='string',
          contentType='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier under which the  Model will be created.

      

    
    :type name: string
    :param name: **[REQUIRED]** 

      The name of the model.

      

    
    :type description: string
    :param description: 

      The description of the model.

      

    
    :type schema: string
    :param schema: 

      The schema for the model. For ``application/json`` models, this should be `JSON-schema draft v4`_ model.

      

    
    :type contentType: string
    :param contentType: **[REQUIRED]** 

      The content-type for the model.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'schema': 'string',
            'contentType': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the data structure of a method's request or response payload.

          

        A request model defines the data structure of the client-supplied request payload. A response model defines the data structure of the response payload returned by the back end. Although not required, models are useful for mapping payloads between the front end and back end.

         

        A model is used for generating an API's SDK, validating the input request body, and creating a skeletal mapping template.

            Method ,  MethodResponse , `Models and Mappings`_  
        

        - **id** *(string) --* 

          The identifier for the model resource.

          
        

        - **name** *(string) --* 

          The name of the model.

          
        

        - **description** *(string) --* 

          The description of the model.

          
        

        - **schema** *(string) --* 

          The schema for the model. For ``application/json`` models, this should be `JSON-schema draft v4`_ model. Do not include "\*/" characters in the description of any properties because such "\*/" characters may be interpreted as the closing marker for comments in some languages, such as Java or JavaScript, causing the installation of your API's SDK generated by API Gateway to fail.

          
        

        - **contentType** *(string) --* 

          The content-type for the model.

          
    

  .. py:method:: create_resource(**kwargs)

    

    Creates a  Resource resource.

    

    **Request Syntax** 
    ::

      response = client.create_resource(
          restApiId='string',
          parentId='string',
          pathPart='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi for the resource. 

      

    
    :type parentId: string
    :param parentId: **[REQUIRED]** 

      The parent resource's identifier.

      

    
    :type pathPart: string
    :param pathPart: **[REQUIRED]** 

      The last path segment for this resource.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'parentId': 'string',
            'pathPart': 'string',
            'path': 'string',
            'resourceMethods': {
                'string': {
                    'httpMethod': 'string',
                    'authorizationType': 'string',
                    'authorizerId': 'string',
                    'apiKeyRequired': True|False,
                    'requestParameters': {
                        'string': True|False
                    },
                    'requestModels': {
                        'string': 'string'
                    },
                    'methodResponses': {
                        'string': {
                            'statusCode': 'string',
                            'responseParameters': {
                                'string': True|False
                            },
                            'responseModels': {
                                'string': 'string'
                            }
                        }
                    },
                    'methodIntegration': {
                        'type': 'HTTP'|'AWS'|'MOCK',
                        'httpMethod': 'string',
                        'uri': 'string',
                        'credentials': 'string',
                        'requestParameters': {
                            'string': 'string'
                        },
                        'requestTemplates': {
                            'string': 'string'
                        },
                        'passthroughBehavior': 'string',
                        'cacheNamespace': 'string',
                        'cacheKeyParameters': [
                            'string',
                        ],
                        'integrationResponses': {
                            'string': {
                                'statusCode': 'string',
                                'selectionPattern': 'string',
                                'responseParameters': {
                                    'string': 'string'
                                },
                                'responseTemplates': {
                                    'string': 'string'
                                }
                            }
                        }
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an API resource.

          `Create an API`_  
        

        - **id** *(string) --* 

          The resource's identifier.

          
        

        - **parentId** *(string) --* 

          The parent resource's identifier.

          
        

        - **pathPart** *(string) --* 

          The last path segment for this resource.

          
        

        - **path** *(string) --* 

          The full path for this resource.

          
        

        - **resourceMethods** *(dict) --* 

          Gets an API resource's method of a given HTTP verb.

            

          The resource methods are a map of methods indexed by methods' HTTP verbs enabled on the resource. This method map is included in the ``200 OK`` response of the ``GET /restapis/{restapi_id}/resources/{resource_id}`` or ``GET /restapis/{restapi_id}/resources/{resource_id}?embed=methods`` request.

           Example: Get the GET method of an API resource Request ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160608T031827Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160608/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": false, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

          If the ``OPTIONS`` is enabled on the resource, you can follow the example here to get that method. Just replace the ``GET`` of the last path segment in the request URL with ``OPTIONS`` .

             
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents a client-facing interface by which the client calls the API to access back-end resources. A **Method** resource is integrated with an  Integration resource. Both consist of a request and one or more responses. The method request takes the client input that is passed to the back end through the integration request. A method response returns the output from the back end to the client through an integration response. A method request is embodied in a **Method** resource, whereas an integration request is embodied in an  Integration resource. On the other hand, a method response is represented by a  MethodResponse resource, whereas an integration response is represented by an  IntegrationResponse resource. 

                

              

               Example: Retrive the GET method on a specified resource Request 

              The following example request retrieves the information about the GET method on an API resource (``3kzxbg5sa2`` ) of an API (``fugvjdxtri`` ). 

               ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T210259Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

              The successful response returns a ``200 OK`` status code and a payload similar to the following:

               ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": true, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E\")" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

              In the example above, the response template for the ``200 OK`` response maps the JSON output from the ``ListStreams`` action in the back end to an XML output. The mapping template is URL-encoded as ``%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E`` and the output is decoded using the `$util.urlDecode()`_ helper function.

                  MethodResponse ,  Integration ,  IntegrationResponse ,  Resource , `Set up an API's method`_  
              

              - **httpMethod** *(string) --* 

                The method's HTTP verb.

                
              

              - **authorizationType** *(string) --* 

                The method's authorization type.

                
              

              - **authorizerId** *(string) --* 

                The identifier of an  Authorizer to use on this method. The ``authorizationType`` must be ``CUSTOM`` .

                
              

              - **apiKeyRequired** *(boolean) --* 

                A boolean flag specifying whether a valid  ApiKey is required to invoke this method.

                
              

              - **requestParameters** *(dict) --* 

                A key-value map defining required or optional method request parameters that can be accepted by Amazon API Gateway. A key is a method request parameter name matching the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` is a valid and unique parameter name. The value associated with the key is a Boolean flag indicating whether the parameter is required (``true`` ) or optional (``false`` ). The method request parameter names defined here are available in  Integration to be mapped to integration request parameters or templates.

                
                

                - *(string) --* 
                  

                  - *(boolean) --* 
            
          
              

              - **requestModels** *(dict) --* 

                A key-value map specifying data schemas, represented by  Model resources, (as the mapped value) of the request payloads of given content types (as the mapping key).

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **methodResponses** *(dict) --* 

                Gets a method response associated with a given HTTP status code. 

                  

                The collection of method responses are encapsulated in a key-value map, where the key is a response's HTTP status code and the value is a  MethodResponse resource that specifies the response returned to the caller from the back end through the integration response.

                 Example: Get a 200 OK response of a GET method Request 

                

                 ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T215008Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                The successful response returns a ``200 OK`` status code and a payload similar to the following:

                 ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.operator": false, "method.response.header.operand_2": false, "method.response.header.operand_1": false }, "statusCode": "200" }``  

                

                   `AWS CLI`_  
                

                - *(string) --* 
                  

                  - *(dict) --* 

                    Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

                      

                    

                     Example: A **MethodResponse** instance of an API Request 

                    The example request retrieves a **MethodResponse** of the 200 status code.

                     ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                    The successful response returns ``200 OK`` status and a payload as follows:

                     ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

                    

                        Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
                    

                    - **statusCode** *(string) --* 

                      The method response's status code.

                      
                    

                    - **responseParameters** *(dict) --* 

                      A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

                      
                      

                      - *(string) --* 
                        

                        - *(boolean) --* 
                  
                
                    

                    - **responseModels** *(dict) --* 

                      Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

                      
                      

                      - *(string) --* 
                        

                        - *(string) --* 
                  
                
                
            
          
              

              - **methodIntegration** *(dict) --* 

                Gets the method's integration responsible for passing the client-submitted request to the back end and performing necessary transformations to make the request compliant with the back end.

                  

                

                 Example:  Request 

                

                 ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T213210Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                The successful response returns a ``200 OK`` status code and a payload similar to the following:

                 ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true } ], "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:responses": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "0cjtch", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestTemplates": { "application/json": "{\n \"a\": \"$input.params('operand1')\",\n \"b\": \"$input.params('operand2')\", \n \"op\": \"$input.params('operator')\" \n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-west-2:lambda:path//2015-03-31/functions/arn:aws:lambda:us-west-2:123456789012:function:Calc/invocations", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.operator": "integration.response.body.op", "method.response.header.operand_2": "integration.response.body.b", "method.response.header.operand_1": "integration.response.body.a" }, "responseTemplates": { "application/json": "#set($res = $input.path('$'))\n{\n \"result\": \"$res.a, $res.b, $res.op => $res.c\",\n \"a\" : \"$res.a\",\n \"b\" : \"$res.b\",\n \"op\" : \"$res.op\",\n \"c\" : \"$res.c\"\n}" }, "selectionPattern": "", "statusCode": "200" } } }``  

                

                   `AWS CLI`_  
                

                - **type** *(string) --* 

                  Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

                  
                

                - **httpMethod** *(string) --* 

                  Specifies the integration's HTTP method type.

                  
                

                - **uri** *(string) --* 

                  Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

                  
                

                - **credentials** *(string) --* 

                  Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

                  
                

                - **requestParameters** *(dict) --* 

                  A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
                

                - **requestTemplates** *(dict) --* 

                  Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
                

                - **passthroughBehavior** *(string) --*  

                  Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

                   

                   
                  * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
                   
                  * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
                   
                  * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
                   

                   
                

                - **cacheNamespace** *(string) --* 

                  Specifies the integration's cache namespace.

                  
                

                - **cacheKeyParameters** *(list) --* 

                  Specifies the integration's cache key parameters.

                  
                  

                  - *(string) --* 
              
                

                - **integrationResponses** *(dict) --* 

                  Specifies the integration's responses.

                    

                  

                   Example: Get integration responses of a method Request 

                  

                   ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                  The successful response returns ``200 OK`` status and a payload as follows:

                   ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

                  

                     `Creating an API`_  
                  

                  - *(string) --* 
                    

                    - *(dict) --* 

                      Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                        `Creating an API`_  
                      

                      - **statusCode** *(string) --* 

                        Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                        
                      

                      - **selectionPattern** *(string) --* 

                        Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                        
                      

                      - **responseParameters** *(dict) --* 

                        A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                        
                        

                        - *(string) --* 
                          

                          - *(string) --* 
                    
                  
                      

                      - **responseTemplates** *(dict) --* 

                        Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                        
                        

                        - *(string) --* 
                          

                          - *(string) --* 
                    
                  
                  
              
            
            
          
      
    
    

  .. py:method:: create_rest_api(**kwargs)

    

    Creates a new  RestApi resource.

    

    **Request Syntax** 
    ::

      response = client.create_rest_api(
          name='string',
          description='string',
          cloneFrom='string'
      )
    :type name: string
    :param name: **[REQUIRED]** 

      The name of the  RestApi .

      

    
    :type description: string
    :param description: 

      The description of the  RestApi .

      

    
    :type cloneFrom: string
    :param cloneFrom: 

      The ID of the  RestApi that you want to clone from.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'createdDate': datetime(2015, 1, 1),
            'warnings': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a REST API.

          `Create an API`_  
        

        - **id** *(string) --* 

          The API's identifier. This identifier is unique across all of your APIs in Amazon API Gateway.

          
        

        - **name** *(string) --* 

          The API's name.

          
        

        - **description** *(string) --* 

          The API's description.

          
        

        - **createdDate** *(datetime) --* 

          The date when the API was created, in `ISO 8601 format`_ .

          
        

        - **warnings** *(list) --* 

          The warning messages reported when ``failonwarnings`` is turned on during API import.

          
          

          - *(string) --* 
      
    

  .. py:method:: create_stage(**kwargs)

    

    Creates a new  Stage resource that references a pre-existing  Deployment for the API. 

    

    **Request Syntax** 
    ::

      response = client.create_stage(
          restApiId='string',
          stageName='string',
          deploymentId='string',
          description='string',
          cacheClusterEnabled=True|False,
          cacheClusterSize='0.5'|'1.6'|'6.1'|'13.5'|'28.4'|'58.2'|'118'|'237',
          variables={
              'string': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi resource for the  Stage resource to create.

      

    
    :type stageName: string
    :param stageName: **[REQUIRED]** 

      The name for the  Stage resource.

      

    
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      The identifier of the  Deployment resource for the  Stage resource.

      

    
    :type description: string
    :param description: 

      The description of the  Stage resource.

      

    
    :type cacheClusterEnabled: boolean
    :param cacheClusterEnabled: 

      Whether cache clustering is enabled for the stage.

      

    
    :type cacheClusterSize: string
    :param cacheClusterSize: 

      The stage's cache cluster size.

      

    
    :type variables: dict
    :param variables: 

      A map that defines the stage variables for the new  Stage resource. Variable names can have alphanumeric and underscore characters, and the values must match ``[A-Za-z0-9-._~:/?#=,]+`` .

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentId': 'string',
            'clientCertificateId': 'string',
            'stageName': 'string',
            'description': 'string',
            'cacheClusterEnabled': True|False,
            'cacheClusterSize': '0.5'|'1.6'|'6.1'|'13.5'|'28.4'|'58.2'|'118'|'237',
            'cacheClusterStatus': 'CREATE_IN_PROGRESS'|'AVAILABLE'|'DELETE_IN_PROGRESS'|'NOT_AVAILABLE'|'FLUSH_IN_PROGRESS',
            'methodSettings': {
                'string': {
                    'metricsEnabled': True|False,
                    'loggingLevel': 'string',
                    'dataTraceEnabled': True|False,
                    'throttlingBurstLimit': 123,
                    'throttlingRateLimit': 123.0,
                    'cachingEnabled': True|False,
                    'cacheTtlInSeconds': 123,
                    'cacheDataEncrypted': True|False,
                    'requireAuthorizationForCacheControl': True|False,
                    'unauthorizedCacheControlHeaderStrategy': 'FAIL_WITH_403'|'SUCCEED_WITH_RESPONSE_HEADER'|'SUCCEED_WITHOUT_RESPONSE_HEADER'
                }
            },
            'variables': {
                'string': 'string'
            },
            'createdDate': datetime(2015, 1, 1),
            'lastUpdatedDate': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a unique identifier for a version of a deployed  RestApi that is callable by users.

          `Deploy an API`_  
        

        - **deploymentId** *(string) --* 

          The identifier of the  Deployment that the stage points to.

          
        

        - **clientCertificateId** *(string) --* 

          The identifier of a client certificate for an API stage.

          
        

        - **stageName** *(string) --* 

          The name of the stage is the first path segment in the Uniform Resource Identifier (URI) of a call to Amazon API Gateway.

          
        

        - **description** *(string) --* 

          The stage's description.

          
        

        - **cacheClusterEnabled** *(boolean) --* 

          Specifies whether a cache cluster is enabled for the stage.

          
        

        - **cacheClusterSize** *(string) --* 

          The size of the cache cluster for the stage, if enabled.

          
        

        - **cacheClusterStatus** *(string) --* 

          The status of the cache cluster for the stage, if enabled.

          
        

        - **methodSettings** *(dict) --* 

          A map that defines the method settings for a  Stage resource. Keys (designated as ``/{method_setting_key`` below) are method paths defined as ``{resource_path}/{http_method}`` for an individual method override, or ``/\*/\*`` for overriding all methods in the stage. Any forward slash ("/") characters in the ``resource_path`` part must be encoded as "~1" as in, for example, ``~1resource~1sub-resource/GET`` .

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Specifies the method setting properties.

              
              

              - **metricsEnabled** *(boolean) --* 

                Specifies whether Amazon CloudWatch metrics are enabled for this method. The PATCH path for this setting is ``/{method_setting_key}/metrics/enabled`` , and the value is a Boolean.

                
              

              - **loggingLevel** *(string) --* 

                Specifies the logging level for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/loglevel`` , and the available levels are ``OFF`` , ``ERROR`` , and ``INFO`` .

                
              

              - **dataTraceEnabled** *(boolean) --* 

                Specifies whether data trace logging is enabled for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/dataTrace`` , and the value is a Boolean.

                
              

              - **throttlingBurstLimit** *(integer) --* 

                Specifies the throttling burst limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/burstLimit`` , and the value is an integer.

                
              

              - **throttlingRateLimit** *(float) --* 

                Specifies the throttling rate limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/rateLimit`` , and the value is a double.

                
              

              - **cachingEnabled** *(boolean) --* 

                Specifies whether responses should be cached and returned for requests. A cache cluster must be enabled on the stage for responses to be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/enabled`` , and the value is a Boolean.

                
              

              - **cacheTtlInSeconds** *(integer) --* 

                Specifies the time to live (TTL), in seconds, for cached responses. The higher the TTL, the longer the response will be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/ttlInSeconds`` , and the value is an integer.

                
              

              - **cacheDataEncrypted** *(boolean) --* 

                Specifies whether the cached responses are encrypted. The PATCH path for this setting is ``/{method_setting_key}/caching/dataEncrypted`` , and the value is a Boolean.

                
              

              - **requireAuthorizationForCacheControl** *(boolean) --* 

                Specifies whether authorization is required for a cache invalidation request. The PATCH path for this setting is ``/{method_setting_key}/caching/requireAuthorizationForCacheControl`` , and the value is a Boolean.

                
              

              - **unauthorizedCacheControlHeaderStrategy** *(string) --* 

                Specifies how to handle unauthorized requests for cache invalidation. The PATCH path for this setting is ``/{method_setting_key}/caching/unauthorizedCacheControlHeaderStrategy`` , and the available values are ``FAIL_WITH_403`` , ``SUCCEED_WITH_RESPONSE_HEADER`` , ``SUCCEED_WITHOUT_RESPONSE_HEADER`` .

                
          
      
    
        

        - **variables** *(dict) --* 

          A map that defines the stage variables for a  Stage resource. Variable names can have alphanumeric and underscore characters, and the values must match ``[A-Za-z0-9-._~:/?#=,]+`` .

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **createdDate** *(datetime) --* 

          The date and time that the stage was created, in `ISO 8601 format`_ .

          
        

        - **lastUpdatedDate** *(datetime) --* 

          The date and time that information about the stage was last updated, in `ISO 8601 format`_ .

          
    

  .. py:method:: create_usage_plan(**kwargs)

    

    Creates a usage plan with the throttle and quota limits, as well as the associated API stages, specified in the payload. 

    

    **Request Syntax** 
    ::

      response = client.create_usage_plan(
          name='string',
          description='string',
          apiStages=[
              {
                  'apiId': 'string',
                  'stage': 'string'
              },
          ],
          throttle={
              'burstLimit': 123,
              'rateLimit': 123.0
          },
          quota={
              'limit': 123,
              'offset': 123,
              'period': 'DAY'|'WEEK'|'MONTH'
          }
      )
    :type name: string
    :param name: **[REQUIRED]** 

      The name of the usage plan.

      

    
    :type description: string
    :param description: 

      The description of the usage plan.

      

    
    :type apiStages: list
    :param apiStages: 

      The associated API stages of the usage plan.

      

    
      - *(dict) --* 

        API stage name of the associated API stage in a usage plan.

        

      
        - **apiId** *(string) --* 

          API Id of the associated API stage in a usage plan.

          

        
        - **stage** *(string) --* 

          API stage name of the associated API stage in a usage plan.

          

        
      
  
    :type throttle: dict
    :param throttle: 

      The throttling limits of the usage plan.

      

    
      - **burstLimit** *(integer) --* 

        The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

        

      
      - **rateLimit** *(float) --* 

        The API request steady-state rate limit.

        

      
    
    :type quota: dict
    :param quota: 

      The quota of the usage plan.

      

    
      - **limit** *(integer) --* 

        The maximum number of requests that can be made in a given time period.

        

      
      - **offset** *(integer) --* 

        The number of requests subtracted from the given limit in the initial time period.

        

      
      - **period** *(string) --* 

        The time period in which the limit applies. Valid values are "DAY", "WEEK" or "MONTH".

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'apiStages': [
                {
                    'apiId': 'string',
                    'stage': 'string'
                },
            ],
            'throttle': {
                'burstLimit': 123,
                'rateLimit': 123.0
            },
            'quota': {
                'limit': 123,
                'offset': 123,
                'period': 'DAY'|'WEEK'|'MONTH'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a usage plan than can specify who can assess associated API stages with specified request limits and quotas.

          

        In a usage plan, you associate an API by specifying the API's Id and a stage name of the specified API. You add plan customers by adding API keys to the plan. 

           `Create and Use Usage Plans`_  
        

        - **id** *(string) --* 

          The identifier of a  UsagePlan resource.

          
        

        - **name** *(string) --* 

          The name of a usage plan.

          
        

        - **description** *(string) --* 

          The description of a usage plan.

          
        

        - **apiStages** *(list) --* 

          The associated API stages of a usage plan.

          
          

          - *(dict) --* 

            API stage name of the associated API stage in a usage plan.

            
            

            - **apiId** *(string) --* 

              API Id of the associated API stage in a usage plan.

              
            

            - **stage** *(string) --* 

              API stage name of the associated API stage in a usage plan.

              
        
      
        

        - **throttle** *(dict) --* 

          The request throttle limits of a usage plan.

          
          

          - **burstLimit** *(integer) --* 

            The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

            
          

          - **rateLimit** *(float) --* 

            The API request steady-state rate limit.

            
      
        

        - **quota** *(dict) --* 

          The maximum number of permitted requests per a given unit time interval.

          
          

          - **limit** *(integer) --* 

            The maximum number of requests that can be made in a given time period.

            
          

          - **offset** *(integer) --* 

            The number of requests subtracted from the given limit in the initial time period.

            
          

          - **period** *(string) --* 

            The time period in which the limit applies. Valid values are "DAY", "WEEK" or "MONTH".

            
      
    

  .. py:method:: create_usage_plan_key(**kwargs)

    

    Creates a usage plan key for adding an existing API key to a usage plan.

    

    **Request Syntax** 
    ::

      response = client.create_usage_plan_key(
          usagePlanId='string',
          keyId='string',
          keyType='string'
      )
    :type usagePlanId: string
    :param usagePlanId: **[REQUIRED]** 

      The Id of the  UsagePlan resource representing the usage plan containing the to-be-created  UsagePlanKey resource representing a plan customer.

      

    
    :type keyId: string
    :param keyId: **[REQUIRED]** 

      The identifier of a  UsagePlanKey resource for a plan customer.

      

    
    :type keyType: string
    :param keyType: **[REQUIRED]** 

      The type of a  UsagePlanKey resource for a plan customer.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'type': 'string',
            'value': 'string',
            'name': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a usage plan key to identify a plan customer.

          

        To associate an API stage with a selected API key in a usage plan, you must create a UsagePlanKey resource to represent the selected  ApiKey .

         "  `Create and Use Usage Plans`_  
        

        - **id** *(string) --* 

          The Id of a usage plan key.

          
        

        - **type** *(string) --* 

          The type of a usage plan key. Currently, the valid key type is ``API_KEY`` .

          
        

        - **value** *(string) --* 

          The value of a usage plan key.

          
        

        - **name** *(string) --* 

          The name of a usage plan key.

          
    

  .. py:method:: delete_api_key(**kwargs)

    

    Deletes the  ApiKey resource.

    

    **Request Syntax** 
    ::

      response = client.delete_api_key(
          apiKey='string'
      )
    :type apiKey: string
    :param apiKey: **[REQUIRED]** 

      The identifier of the  ApiKey resource to be deleted.

      

    
    
    :returns: None

  .. py:method:: delete_authorizer(**kwargs)

    

    Deletes an existing  Authorizer resource.

     `AWS CLI`_ 

    **Request Syntax** 
    ::

      response = client.delete_authorizer(
          restApiId='string',
          authorizerId='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Authorizer resource.

      

    
    :type authorizerId: string
    :param authorizerId: **[REQUIRED]** 

      The identifier of the  Authorizer resource.

      

    
    
    :returns: None

  .. py:method:: delete_base_path_mapping(**kwargs)

    

    Deletes the  BasePathMapping resource.

    

    **Request Syntax** 
    ::

      response = client.delete_base_path_mapping(
          domainName='string',
          basePath='string'
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The domain name of the  BasePathMapping resource to delete.

      

    
    :type basePath: string
    :param basePath: **[REQUIRED]** 

      The base path name of the  BasePathMapping resource to delete.

      

    
    
    :returns: None

  .. py:method:: delete_client_certificate(**kwargs)

    

    Deletes the  ClientCertificate resource.

    

    **Request Syntax** 
    ::

      response = client.delete_client_certificate(
          clientCertificateId='string'
      )
    :type clientCertificateId: string
    :param clientCertificateId: **[REQUIRED]** 

      The identifier of the  ClientCertificate resource to be deleted.

      

    
    
    :returns: None

  .. py:method:: delete_deployment(**kwargs)

    

    Deletes a  Deployment resource. Deleting a deployment will only succeed if there are no  Stage resources associated with it.

    

    **Request Syntax** 
    ::

      response = client.delete_deployment(
          restApiId='string',
          deploymentId='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi resource for the  Deployment resource to delete.

      

    
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      The identifier of the  Deployment resource to delete.

      

    
    
    :returns: None

  .. py:method:: delete_domain_name(**kwargs)

    

    Deletes the  DomainName resource.

    

    **Request Syntax** 
    ::

      response = client.delete_domain_name(
          domainName='string'
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The name of the  DomainName resource to be deleted.

      

    
    
    :returns: None

  .. py:method:: delete_integration(**kwargs)

    

    Represents a delete integration.

    

    **Request Syntax** 
    ::

      response = client.delete_integration(
          restApiId='string',
          resourceId='string',
          httpMethod='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Specifies a delete integration request's API identifier.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      Specifies a delete integration request's resource identifier.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies a delete integration request's HTTP method.

      

    
    
    :returns: None

  .. py:method:: delete_integration_response(**kwargs)

    

    Represents a delete integration response.

    

    **Request Syntax** 
    ::

      response = client.delete_integration_response(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          statusCode='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Specifies a delete integration response request's API identifier.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      Specifies a delete integration response request's resource identifier.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies a delete integration response request's HTTP method.

      

    
    :type statusCode: string
    :param statusCode: **[REQUIRED]** 

      Specifies a delete integration response request's status code.

      

    
    
    :returns: None

  .. py:method:: delete_method(**kwargs)

    

    Deletes an existing  Method resource.

    

    **Request Syntax** 
    ::

      response = client.delete_method(
          restApiId='string',
          resourceId='string',
          httpMethod='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Method resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The  Resource identifier for the  Method resource.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      The HTTP verb of the  Method resource.

      

    
    
    :returns: None

  .. py:method:: delete_method_response(**kwargs)

    

    Deletes an existing  MethodResponse resource.

    

    **Request Syntax** 
    ::

      response = client.delete_method_response(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          statusCode='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  MethodResponse resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The  Resource identifier for the  MethodResponse resource.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      The HTTP verb of the  Method resource.

      

    
    :type statusCode: string
    :param statusCode: **[REQUIRED]** 

      The status code identifier for the  MethodResponse resource.

      

    
    
    :returns: None

  .. py:method:: delete_model(**kwargs)

    

    Deletes a model.

    

    **Request Syntax** 
    ::

      response = client.delete_model(
          restApiId='string',
          modelName='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi under which the model will be deleted.

      

    
    :type modelName: string
    :param modelName: **[REQUIRED]** 

      The name of the model to delete.

      

    
    
    :returns: None

  .. py:method:: delete_resource(**kwargs)

    

    Deletes a  Resource resource.

    

    **Request Syntax** 
    ::

      response = client.delete_resource(
          restApiId='string',
          resourceId='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Resource resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The identifier of the  Resource resource.

      

    
    
    :returns: None

  .. py:method:: delete_rest_api(**kwargs)

    

    Deletes the specified API.

    

    **Request Syntax** 
    ::

      response = client.delete_rest_api(
          restApiId='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The ID of the  RestApi you want to delete.

      

    
    
    :returns: None

  .. py:method:: delete_stage(**kwargs)

    

    Deletes a  Stage resource.

    

    **Request Syntax** 
    ::

      response = client.delete_stage(
          restApiId='string',
          stageName='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi resource for the  Stage resource to delete.

      

    
    :type stageName: string
    :param stageName: **[REQUIRED]** 

      The name of the  Stage resource to delete.

      

    
    
    :returns: None

  .. py:method:: delete_usage_plan(**kwargs)

    

    Deletes a usage plan of a given plan Id.

    

    **Request Syntax** 
    ::

      response = client.delete_usage_plan(
          usagePlanId='string'
      )
    :type usagePlanId: string
    :param usagePlanId: **[REQUIRED]** 

      The Id of the to-be-deleted usage plan.

      

    
    
    :returns: None

  .. py:method:: delete_usage_plan_key(**kwargs)

    

    Deletes a usage plan key and remove the underlying API key from the associated usage plan.

    

    **Request Syntax** 
    ::

      response = client.delete_usage_plan_key(
          usagePlanId='string',
          keyId='string'
      )
    :type usagePlanId: string
    :param usagePlanId: **[REQUIRED]** 

      The Id of the  UsagePlan resource representing the usage plan containing the to-be-deleted  UsagePlanKey resource representing a plan customer.

      

    
    :type keyId: string
    :param keyId: **[REQUIRED]** 

      The Id of the  UsagePlanKey resource to be deleted.

      

    
    
    :returns: None

  .. py:method:: flush_stage_authorizers_cache(**kwargs)

    

    Flushes all authorizer cache entries on a stage.

    

    **Request Syntax** 
    ::

      response = client.flush_stage_authorizers_cache(
          restApiId='string',
          stageName='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The API identifier of the stage to flush.

      

    
    :type stageName: string
    :param stageName: **[REQUIRED]** 

      The name of the stage to flush.

      

    
    
    :returns: None

  .. py:method:: flush_stage_cache(**kwargs)

    

    Flushes a stage's cache.

    

    **Request Syntax** 
    ::

      response = client.flush_stage_cache(
          restApiId='string',
          stageName='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The API identifier of the stage to flush its cache.

      

    
    :type stageName: string
    :param stageName: **[REQUIRED]** 

      The name of the stage to flush its cache.

      

    
    
    :returns: None

  .. py:method:: generate_client_certificate(**kwargs)

    

    Generates a  ClientCertificate resource.

    

    **Request Syntax** 
    ::

      response = client.generate_client_certificate(
          description='string'
      )
    :type description: string
    :param description: 

      The description of the  ClientCertificate .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'clientCertificateId': 'string',
            'description': 'string',
            'pemEncodedCertificate': 'string',
            'createdDate': datetime(2015, 1, 1),
            'expirationDate': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a client certificate used to configure client-side SSL authentication while sending requests to the integration endpoint.

         Client certificates are used authenticate an API by the back-end server. To authenticate an API client (or user), use a custom  Authorizer .  `Use Client-Side Certificate`_  
        

        - **clientCertificateId** *(string) --* 

          The identifier of the client certificate.

          
        

        - **description** *(string) --* 

          The description of the client certificate.

          
        

        - **pemEncodedCertificate** *(string) --* 

          The PEM-encoded public key of the client certificate, which can be used to configure certificate authentication in the integration endpoint .

          
        

        - **createdDate** *(datetime) --* 

          The date when the client certificate was created, in `ISO 8601 format`_ .

          
        

        - **expirationDate** *(datetime) --* 

          The date when the client certificate will expire, in `ISO 8601 format`_ .

          
    

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


  .. py:method:: get_account()

    

    Gets information about the current  Account resource.

    

    **Request Syntax** 
    ::

      response = client.get_account()
      
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'cloudwatchRoleArn': 'string',
            'throttleSettings': {
                'burstLimit': 123,
                'rateLimit': 123.0
            },
            'features': [
                'string',
            ],
            'apiKeyVersion': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an AWS account that is associated with Amazon API Gateway.

          

        To view the account info, call ``GET`` on this resource.

         Error Codes 

        The following exception may be thrown when the request fails.

         

         
        * UnauthorizedException
         
        * NotFoundException
         
        * TooManyRequestsException
         

         

        For detailed error code information, including the corresponding HTTP Status Codes, see `API Gateway Error Codes`_ 

         Example: Get the information about an account. Request ``GET /account HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160531T184618Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

        The successful response returns a ``200 OK`` status code and a payload similar to the following:

         ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/account-apigateway-{rel}.html", "name": "account", "templated": true }, "self": { "href": "/account" }, "account:update": { "href": "/account" } }, "cloudwatchRoleArn": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "throttleSettings": { "rateLimit": 500, "burstLimit": 1000 } }``  

        In addition to making the REST API call directly, you can use the AWS CLI and an AWS SDK to access this resource.

           `API Gateway Limits`_  `Developer Guide`_ , `AWS CLI`_  
        

        - **cloudwatchRoleArn** *(string) --* 

          The ARN of an Amazon CloudWatch role for the current  Account . 

          
        

        - **throttleSettings** *(dict) --* 

          Specifies the API request limits configured for the current  Account .

          
          

          - **burstLimit** *(integer) --* 

            The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

            
          

          - **rateLimit** *(float) --* 

            The API request steady-state rate limit.

            
      
        

        - **features** *(list) --* 

          A list of features supported for the account. When usage plans are enabled, the features list will include an entry of ``"UsagePlans"`` .

          
          

          - *(string) --* 
      
        

        - **apiKeyVersion** *(string) --* 

          The version of the API keys used for the account.

          
    

  .. py:method:: get_api_key(**kwargs)

    

    Gets information about the current  ApiKey resource.

    

    **Request Syntax** 
    ::

      response = client.get_api_key(
          apiKey='string',
          includeValue=True|False
      )
    :type apiKey: string
    :param apiKey: **[REQUIRED]** 

      The identifier of the  ApiKey resource.

      

    
    :type includeValue: boolean
    :param includeValue: 

      A boolean flag to specify whether (``true`` ) or not (``false`` ) the result contains the key value.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'value': 'string',
            'name': 'string',
            'description': 'string',
            'enabled': True|False,
            'createdDate': datetime(2015, 1, 1),
            'lastUpdatedDate': datetime(2015, 1, 1),
            'stageKeys': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A resource that can be distributed to callers for executing  Method resources that require an API key. API keys can be mapped to any  Stage on any  RestApi , which indicates that the callers with the API key can make requests to that stage.

          `Use API Keys`_  
        

        - **id** *(string) --* 

          The identifier of the API Key.

          
        

        - **value** *(string) --* 

          The value of the API Key.

          
        

        - **name** *(string) --* 

          The name of the API Key.

          
        

        - **description** *(string) --* 

          The description of the API Key.

          
        

        - **enabled** *(boolean) --* 

          Specifies whether the API Key can be used by callers.

          
        

        - **createdDate** *(datetime) --* 

          The date when the API Key was created, in `ISO 8601 format`_ .

          
        

        - **lastUpdatedDate** *(datetime) --* 

          When the API Key was last updated, in ISO 8601 format.

          
        

        - **stageKeys** *(list) --* 

          A list of  Stage resources that are associated with the  ApiKey resource.

          
          

          - *(string) --* 
      
    

  .. py:method:: get_api_keys(**kwargs)

    

    Gets information about the current  ApiKeys resource.

    

    **Request Syntax** 
    ::

      response = client.get_api_keys(
          position='string',
          limit=123,
          nameQuery='string',
          includeValues=True|False
      )
    :type position: string
    :param position: 

      The position of the current  ApiKeys resource to get information about.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of  ApiKeys to get information about.

      

    
    :type nameQuery: string
    :param nameQuery: 

      The name of queried API keys.

      

    
    :type includeValues: boolean
    :param includeValues: 

      A boolean flag to specify whether (``true`` ) or not (``false`` ) the result contains key values.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'warnings': [
                'string',
            ],
            'position': 'string',
            'items': [
                {
                    'id': 'string',
                    'value': 'string',
                    'name': 'string',
                    'description': 'string',
                    'enabled': True|False,
                    'createdDate': datetime(2015, 1, 1),
                    'lastUpdatedDate': datetime(2015, 1, 1),
                    'stageKeys': [
                        'string',
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of API keys as represented by an  ApiKeys resource.

          `Use API Keys`_  
        

        - **warnings** *(list) --* 

          A list of warning messages logged during the import of API keys when the ``failOnWarnings`` option is set to true.

          
          

          - *(string) --* 
      
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          The current page of any  ApiKey resources in the collection of  ApiKey resources.

          
          

          - *(dict) --* 

            A resource that can be distributed to callers for executing  Method resources that require an API key. API keys can be mapped to any  Stage on any  RestApi , which indicates that the callers with the API key can make requests to that stage.

              `Use API Keys`_  
            

            - **id** *(string) --* 

              The identifier of the API Key.

              
            

            - **value** *(string) --* 

              The value of the API Key.

              
            

            - **name** *(string) --* 

              The name of the API Key.

              
            

            - **description** *(string) --* 

              The description of the API Key.

              
            

            - **enabled** *(boolean) --* 

              Specifies whether the API Key can be used by callers.

              
            

            - **createdDate** *(datetime) --* 

              The date when the API Key was created, in `ISO 8601 format`_ .

              
            

            - **lastUpdatedDate** *(datetime) --* 

              When the API Key was last updated, in ISO 8601 format.

              
            

            - **stageKeys** *(list) --* 

              A list of  Stage resources that are associated with the  ApiKey resource.

              
              

              - *(string) --* 
          
        
      
    

  .. py:method:: get_authorizer(**kwargs)

    

    Describe an existing  Authorizer resource.

     `AWS CLI`_ 

    **Request Syntax** 
    ::

      response = client.get_authorizer(
          restApiId='string',
          authorizerId='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Authorizer resource.

      

    
    :type authorizerId: string
    :param authorizerId: **[REQUIRED]** 

      The identifier of the  Authorizer resource.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'type': 'TOKEN'|'COGNITO_USER_POOLS',
            'providerARNs': [
                'string',
            ],
            'authType': 'string',
            'authorizerUri': 'string',
            'authorizerCredentials': 'string',
            'identitySource': 'string',
            'identityValidationExpression': 'string',
            'authorizerResultTtlInSeconds': 123
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an authorization layer for methods. If enabled on a method, API Gateway will activate the authorizer when a client calls the method.

          `Enable custom authorization`_  
        

        - **id** *(string) --* 

          The identifier for the authorizer resource.

          
        

        - **name** *(string) --* 

          [Required] The name of the authorizer.

          
        

        - **type** *(string) --* 

          [Required] The type of the authorizer. Currently, the only valid type is TOKEN.

          
        

        - **providerARNs** *(list) --* 

          A list of the provider ARNs of the authorizer.

          
          

          - *(string) --* 
      
        

        - **authType** *(string) --* 

          Optional customer-defined field, used in Swagger imports/exports. Has no functional impact.

          
        

        - **authorizerUri** *(string) --* 

          [Required] Specifies the authorizer's Uniform Resource Identifier (URI). For TOKEN authorizers, this must be a well-formed Lambda function URI. The URI should be of the form ``arn:aws:apigateway:{region}:lambda:path/{service_api}`` . ``Region`` is used to determine the right endpoint. In this case, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` . For Lambda functions, this is usually of the form /2015-03-31/functions/[FunctionARN]/invocations

          
        

        - **authorizerCredentials** *(string) --* 

          Specifies the credentials required for the authorizer, if any. Two options are available. To specify an IAM role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To use resource-based permissions on the Lambda function, specify null.

          
        

        - **identitySource** *(string) --* 

          [Required] The source of the identity in an incoming request. For TOKEN authorizers, this value is a mapping expression with the same syntax as integration parameter mappings. The only valid source for tokens is 'header', so the expression should match 'method.request.header.[headerName]'. The value of the header '[headerName]' will be interpreted as the incoming token.

          
        

        - **identityValidationExpression** *(string) --* 

          A validation expression for the incoming identity. For TOKEN authorizers, this value should be a regular expression. The incoming token from the client is matched against this expression, and will proceed if the token matches. If the token doesn't match, the client receives a 401 Unauthorized response.

          
        

        - **authorizerResultTtlInSeconds** *(integer) --* 

          The TTL in seconds of cached authorizer results. If greater than 0, API Gateway will cache authorizer responses. If this field is not set, the default value is 300. The maximum value is 3600, or 1 hour.

          
    

  .. py:method:: get_authorizers(**kwargs)

    

    Describe an existing  Authorizers resource.

     `AWS CLI`_ 

    **Request Syntax** 
    ::

      response = client.get_authorizers(
          restApiId='string',
          position='string',
          limit=123
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Authorizers resource.

      

    
    :type position: string
    :param position: 

      If not all  Authorizer resources in the response were present, the position will specify where to start the next page of results.

      

    
    :type limit: integer
    :param limit: 

      Limit the number of  Authorizer resources in the response.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'id': 'string',
                    'name': 'string',
                    'type': 'TOKEN'|'COGNITO_USER_POOLS',
                    'providerARNs': [
                        'string',
                    ],
                    'authType': 'string',
                    'authorizerUri': 'string',
                    'authorizerCredentials': 'string',
                    'identitySource': 'string',
                    'identityValidationExpression': 'string',
                    'authorizerResultTtlInSeconds': 123
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  Authorizer resources.

          `Enable custom authorization`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          Gets the current list of  Authorizer resources in the collection.

          
          

          - *(dict) --* 

            Represents an authorization layer for methods. If enabled on a method, API Gateway will activate the authorizer when a client calls the method.

              `Enable custom authorization`_  
            

            - **id** *(string) --* 

              The identifier for the authorizer resource.

              
            

            - **name** *(string) --* 

              [Required] The name of the authorizer.

              
            

            - **type** *(string) --* 

              [Required] The type of the authorizer. Currently, the only valid type is TOKEN.

              
            

            - **providerARNs** *(list) --* 

              A list of the provider ARNs of the authorizer.

              
              

              - *(string) --* 
          
            

            - **authType** *(string) --* 

              Optional customer-defined field, used in Swagger imports/exports. Has no functional impact.

              
            

            - **authorizerUri** *(string) --* 

              [Required] Specifies the authorizer's Uniform Resource Identifier (URI). For TOKEN authorizers, this must be a well-formed Lambda function URI. The URI should be of the form ``arn:aws:apigateway:{region}:lambda:path/{service_api}`` . ``Region`` is used to determine the right endpoint. In this case, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` . For Lambda functions, this is usually of the form /2015-03-31/functions/[FunctionARN]/invocations

              
            

            - **authorizerCredentials** *(string) --* 

              Specifies the credentials required for the authorizer, if any. Two options are available. To specify an IAM role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To use resource-based permissions on the Lambda function, specify null.

              
            

            - **identitySource** *(string) --* 

              [Required] The source of the identity in an incoming request. For TOKEN authorizers, this value is a mapping expression with the same syntax as integration parameter mappings. The only valid source for tokens is 'header', so the expression should match 'method.request.header.[headerName]'. The value of the header '[headerName]' will be interpreted as the incoming token.

              
            

            - **identityValidationExpression** *(string) --* 

              A validation expression for the incoming identity. For TOKEN authorizers, this value should be a regular expression. The incoming token from the client is matched against this expression, and will proceed if the token matches. If the token doesn't match, the client receives a 401 Unauthorized response.

              
            

            - **authorizerResultTtlInSeconds** *(integer) --* 

              The TTL in seconds of cached authorizer results. If greater than 0, API Gateway will cache authorizer responses. If this field is not set, the default value is 300. The maximum value is 3600, or 1 hour.

              
        
      
    

  .. py:method:: get_base_path_mapping(**kwargs)

    

    Describe a  BasePathMapping resource.

    

    **Request Syntax** 
    ::

      response = client.get_base_path_mapping(
          domainName='string',
          basePath='string'
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The domain name of the  BasePathMapping resource to be described.

      

    
    :type basePath: string
    :param basePath: **[REQUIRED]** 

      The base path name that callers of the API must provide as part of the URL after the domain name. This value must be unique for all of the mappings across a single API. Leave this blank if you do not want callers to specify any base path name after the domain name.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'basePath': 'string',
            'restApiId': 'string',
            'stage': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the base path that callers of the API must provide as part of the URL after the domain name.

         A custom domain name plus a ``BasePathMapping`` specification identifies a deployed  RestApi in a given stage of the owner  Account .  `Use Custom Domain Names`_  
        

        - **basePath** *(string) --* 

          The base path name that callers of the API must provide as part of the URL after the domain name.

          
        

        - **restApiId** *(string) --* 

          The name of the API.

          
        

        - **stage** *(string) --* 

          The name of the API's stage.

          
    

  .. py:method:: get_base_path_mappings(**kwargs)

    

    Represents a collection of  BasePathMapping resources.

    

    **Request Syntax** 
    ::

      response = client.get_base_path_mappings(
          domainName='string',
          position='string',
          limit=123
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The domain name of a  BasePathMapping resource.

      

    
    :type position: string
    :param position: 

      The position of the current  BasePathMapping resource in the collection to get information about.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of  BasePathMapping resources in the collection to get information about. The default limit is 25. It should be an integer between 1 - 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'basePath': 'string',
                    'restApiId': 'string',
                    'stage': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  BasePathMapping resources.

          `Use Custom Domain Names`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          The current page of any  BasePathMapping resources in the collection of base path mapping resources.

          
          

          - *(dict) --* 

            Represents the base path that callers of the API must provide as part of the URL after the domain name.

             A custom domain name plus a ``BasePathMapping`` specification identifies a deployed  RestApi in a given stage of the owner  Account .  `Use Custom Domain Names`_  
            

            - **basePath** *(string) --* 

              The base path name that callers of the API must provide as part of the URL after the domain name.

              
            

            - **restApiId** *(string) --* 

              The name of the API.

              
            

            - **stage** *(string) --* 

              The name of the API's stage.

              
        
      
    

  .. py:method:: get_client_certificate(**kwargs)

    

    Gets information about the current  ClientCertificate resource.

    

    **Request Syntax** 
    ::

      response = client.get_client_certificate(
          clientCertificateId='string'
      )
    :type clientCertificateId: string
    :param clientCertificateId: **[REQUIRED]** 

      The identifier of the  ClientCertificate resource to be described.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'clientCertificateId': 'string',
            'description': 'string',
            'pemEncodedCertificate': 'string',
            'createdDate': datetime(2015, 1, 1),
            'expirationDate': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a client certificate used to configure client-side SSL authentication while sending requests to the integration endpoint.

         Client certificates are used authenticate an API by the back-end server. To authenticate an API client (or user), use a custom  Authorizer .  `Use Client-Side Certificate`_  
        

        - **clientCertificateId** *(string) --* 

          The identifier of the client certificate.

          
        

        - **description** *(string) --* 

          The description of the client certificate.

          
        

        - **pemEncodedCertificate** *(string) --* 

          The PEM-encoded public key of the client certificate, which can be used to configure certificate authentication in the integration endpoint .

          
        

        - **createdDate** *(datetime) --* 

          The date when the client certificate was created, in `ISO 8601 format`_ .

          
        

        - **expirationDate** *(datetime) --* 

          The date when the client certificate will expire, in `ISO 8601 format`_ .

          
    

  .. py:method:: get_client_certificates(**kwargs)

    

    Gets a collection of  ClientCertificate resources.

    

    **Request Syntax** 
    ::

      response = client.get_client_certificates(
          position='string',
          limit=123
      )
    :type position: string
    :param position: 

      The position of the current  ClientCertificate resource in the collection to get information about.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of  ClientCertificate resources in the collection to get information about. The default limit is 25. It should be an integer between 1 - 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'clientCertificateId': 'string',
                    'description': 'string',
                    'pemEncodedCertificate': 'string',
                    'createdDate': datetime(2015, 1, 1),
                    'expirationDate': datetime(2015, 1, 1)
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  ClientCertificate resources.

          `Use Client-Side Certificate`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          The current page of any  ClientCertificate resources in the collection of  ClientCertificate resources.

          
          

          - *(dict) --* 

            Represents a client certificate used to configure client-side SSL authentication while sending requests to the integration endpoint.

             Client certificates are used authenticate an API by the back-end server. To authenticate an API client (or user), use a custom  Authorizer .  `Use Client-Side Certificate`_  
            

            - **clientCertificateId** *(string) --* 

              The identifier of the client certificate.

              
            

            - **description** *(string) --* 

              The description of the client certificate.

              
            

            - **pemEncodedCertificate** *(string) --* 

              The PEM-encoded public key of the client certificate, which can be used to configure certificate authentication in the integration endpoint .

              
            

            - **createdDate** *(datetime) --* 

              The date when the client certificate was created, in `ISO 8601 format`_ .

              
            

            - **expirationDate** *(datetime) --* 

              The date when the client certificate will expire, in `ISO 8601 format`_ .

              
        
      
    

  .. py:method:: get_deployment(**kwargs)

    

    Gets information about a  Deployment resource.

    

    **Request Syntax** 
    ::

      response = client.get_deployment(
          restApiId='string',
          deploymentId='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi resource for the  Deployment resource to get information about.

      

    
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      The identifier of the  Deployment resource to get information about.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'description': 'string',
            'createdDate': datetime(2015, 1, 1),
            'apiSummary': {
                'string': {
                    'string': {
                        'authorizationType': 'string',
                        'apiKeyRequired': True|False
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        An immutable representation of a  RestApi resource that can be called by users using  Stages . A deployment must be associated with a  Stage for it to be callable over the Internet.

         To create a deployment, call ``POST`` on the  Deployments resource of a  RestApi . To view, update, or delete a deployment, call ``GET`` , ``PATCH`` , or ``DELETE`` on the specified deployment resource (``/restapis/{restapi_id}/deployments/{deployment_id}`` ).  RestApi ,  Deployments ,  Stage , `AWS CLI`_ , `AWS SDKs`_  
        

        - **id** *(string) --* 

          The identifier for the deployment resource.

          
        

        - **description** *(string) --* 

          The description for the deployment resource.

          
        

        - **createdDate** *(datetime) --* 

          The date and time that the deployment resource was created.

          
        

        - **apiSummary** *(dict) --* 

          A summary of the  RestApi at the date and time that the deployment resource was created.

          
          

          - *(string) --* 
            

            - *(dict) --* 
              

              - *(string) --* 
                

                - *(dict) --* 

                  Represents a summary of a  Method resource, given a particular date and time.

                  
                  

                  - **authorizationType** *(string) --* 

                    Specifies the type of authorization used for the method.

                    
                  

                  - **apiKeyRequired** *(boolean) --* 

                    Specifies whether the method requires a valid  ApiKey .

                    
              
          
        
      
    
    

  .. py:method:: get_deployments(**kwargs)

    

    Gets information about a  Deployments collection.

    

    **Request Syntax** 
    ::

      response = client.get_deployments(
          restApiId='string',
          position='string',
          limit=123
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi resource for the collection of  Deployment resources to get information about.

      

    
    :type position: string
    :param position: 

      The position of the current  Deployment resource in the collection to get information about.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of  Deployment resources in the collection to get information about. The default limit is 25. It should be an integer between 1 - 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'id': 'string',
                    'description': 'string',
                    'createdDate': datetime(2015, 1, 1),
                    'apiSummary': {
                        'string': {
                            'string': {
                                'authorizationType': 'string',
                                'apiKeyRequired': True|False
                            }
                        }
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection resource that contains zero or more references to your existing deployments, and links that guide you on how to interact with your collection. The collection offers a paginated view of the contained deployments.

         To create a new deployment of a  RestApi , make a ``POST`` request against this resource. To view, update, or delete an existing deployment, make a ``GET`` , ``PATCH`` , or ``DELETE`` request, respectively, on a specified  Deployment resource.  `Deploying an API`_ , `AWS CLI`_ , `AWS SDKs`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          The current page of any  Deployment resources in the collection of deployment resources.

          
          

          - *(dict) --* 

            An immutable representation of a  RestApi resource that can be called by users using  Stages . A deployment must be associated with a  Stage for it to be callable over the Internet.

             To create a deployment, call ``POST`` on the  Deployments resource of a  RestApi . To view, update, or delete a deployment, call ``GET`` , ``PATCH`` , or ``DELETE`` on the specified deployment resource (``/restapis/{restapi_id}/deployments/{deployment_id}`` ).  RestApi ,  Deployments ,  Stage , `AWS CLI`_ , `AWS SDKs`_  
            

            - **id** *(string) --* 

              The identifier for the deployment resource.

              
            

            - **description** *(string) --* 

              The description for the deployment resource.

              
            

            - **createdDate** *(datetime) --* 

              The date and time that the deployment resource was created.

              
            

            - **apiSummary** *(dict) --* 

              A summary of the  RestApi at the date and time that the deployment resource was created.

              
              

              - *(string) --* 
                

                - *(dict) --* 
                  

                  - *(string) --* 
                    

                    - *(dict) --* 

                      Represents a summary of a  Method resource, given a particular date and time.

                      
                      

                      - **authorizationType** *(string) --* 

                        Specifies the type of authorization used for the method.

                        
                      

                      - **apiKeyRequired** *(boolean) --* 

                        Specifies whether the method requires a valid  ApiKey .

                        
                  
              
            
          
        
        
      
    

  .. py:method:: get_domain_name(**kwargs)

    

    Represents a domain name that is contained in a simpler, more intuitive URL that can be called.

    

    **Request Syntax** 
    ::

      response = client.get_domain_name(
          domainName='string'
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The name of the  DomainName resource.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'domainName': 'string',
            'certificateName': 'string',
            'certificateUploadDate': datetime(2015, 1, 1),
            'distributionDomainName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a domain name that is contained in a simpler, more intuitive URL that can be called.

          `Use Client-Side Certificate`_  
        

        - **domainName** *(string) --* 

          The name of the  DomainName resource.

          
        

        - **certificateName** *(string) --* 

          The name of the certificate.

          
        

        - **certificateUploadDate** *(datetime) --* 

          The date when the certificate was uploaded, in `ISO 8601 format`_ .

          
        

        - **distributionDomainName** *(string) --* 

          The domain name of the Amazon CloudFront distribution. For more information, see the `Amazon CloudFront documentation`_ .

          
    

  .. py:method:: get_domain_names(**kwargs)

    

    Represents a collection of  DomainName resources.

    

    **Request Syntax** 
    ::

      response = client.get_domain_names(
          position='string',
          limit=123
      )
    :type position: string
    :param position: 

      The position of the current domain names to get information about.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of  DomainName resources in the collection to get information about. The default limit is 25. It should be an integer between 1 - 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'domainName': 'string',
                    'certificateName': 'string',
                    'certificateUploadDate': datetime(2015, 1, 1),
                    'distributionDomainName': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  DomainName resources.

          `Use Client-Side Certificate`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          The current page of any  DomainName resources in the collection of  DomainName resources.

          
          

          - *(dict) --* 

            Represents a domain name that is contained in a simpler, more intuitive URL that can be called.

              `Use Client-Side Certificate`_  
            

            - **domainName** *(string) --* 

              The name of the  DomainName resource.

              
            

            - **certificateName** *(string) --* 

              The name of the certificate.

              
            

            - **certificateUploadDate** *(datetime) --* 

              The date when the certificate was uploaded, in `ISO 8601 format`_ .

              
            

            - **distributionDomainName** *(string) --* 

              The domain name of the Amazon CloudFront distribution. For more information, see the `Amazon CloudFront documentation`_ .

              
        
      
    

  .. py:method:: get_export(**kwargs)

    

    Exports a deployed version of a  RestApi in a specified format.

    

    **Request Syntax** 
    ::

      response = client.get_export(
          restApiId='string',
          stageName='string',
          exportType='string',
          parameters={
              'string': 'string'
          },
          accepts='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi to be exported.

      

    
    :type stageName: string
    :param stageName: **[REQUIRED]** 

      The name of the  Stage that will be exported.

      

    
    :type exportType: string
    :param exportType: **[REQUIRED]** 

      The type of export. Currently only 'swagger' is supported.

      

    
    :type parameters: dict
    :param parameters: 

      A key-value map of query string parameters that specify properties of the export, depending on the requested ``exportType`` . For ``exportType``  ``swagger`` , any combination of the following parameters are supported: ``integrations`` will export the API with x-amazon-apigateway-integration extensions. ``authorizers`` will export the API with x-amazon-apigateway-authorizer extensions. ``postman`` will export the API with Postman extensions, allowing for import to the Postman tool

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type accepts: string
    :param accepts: 

      The content-type of the export, for example ``application/json`` . Currently ``application/json`` and ``application/yaml`` are supported for ``exportType`` of ``swagger`` . This should be specified in the ``Accept`` header for direct API requests.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'contentType': 'string',
            'contentDisposition': 'string',
            'body': StreamingBody()
        }
      **Response Structure** 

      

      - *(dict) --* 

        The binary blob response to  GetExport , which contains the generated SDK.

        
        

        - **contentType** *(string) --* 

          The content-type header value in the HTTP response. This will correspond to a valid 'accept' type in the request.

          
        

        - **contentDisposition** *(string) --* 

          The content-disposition header value in the HTTP response.

          
        

        - **body** (:class:`.StreamingBody`) -- 

          The binary blob response to  GetExport , which contains the export.

          
    

  .. py:method:: get_integration(**kwargs)

    

    Represents a get integration.

    

    **Request Syntax** 
    ::

      response = client.get_integration(
          restApiId='string',
          resourceId='string',
          httpMethod='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Specifies a get integration request's API identifier.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      Specifies a get integration request's resource identifier

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies a get integration request's HTTP method.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'type': 'HTTP'|'AWS'|'MOCK',
            'httpMethod': 'string',
            'uri': 'string',
            'credentials': 'string',
            'requestParameters': {
                'string': 'string'
            },
            'requestTemplates': {
                'string': 'string'
            },
            'passthroughBehavior': 'string',
            'cacheNamespace': 'string',
            'cacheKeyParameters': [
                'string',
            ],
            'integrationResponses': {
                'string': {
                    'statusCode': 'string',
                    'selectionPattern': 'string',
                    'responseParameters': {
                        'string': 'string'
                    },
                    'responseTemplates': {
                        'string': 'string'
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an HTTP, AWS, or Mock integration.

         In the API Gateway console, the built-in Lambda integration is an AWS integration.  `Creating an API`_  
        

        - **type** *(string) --* 

          Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

          
        

        - **httpMethod** *(string) --* 

          Specifies the integration's HTTP method type.

          
        

        - **uri** *(string) --* 

          Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

          
        

        - **credentials** *(string) --* 

          Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

          
        

        - **requestParameters** *(dict) --* 

          A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **requestTemplates** *(dict) --* 

          Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **passthroughBehavior** *(string) --*  

          Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

           

           
          * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
           
          * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
           
          * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
           

           
        

        - **cacheNamespace** *(string) --* 

          Specifies the integration's cache namespace.

          
        

        - **cacheKeyParameters** *(list) --* 

          Specifies the integration's cache key parameters.

          
          

          - *(string) --* 
      
        

        - **integrationResponses** *(dict) --* 

          Specifies the integration's responses.

            

          

           Example: Get integration responses of a method Request 

          

           ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

          The successful response returns ``200 OK`` status and a payload as follows:

           ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

          

             `Creating an API`_  
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                `Creating an API`_  
              

              - **statusCode** *(string) --* 

                Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                
              

              - **selectionPattern** *(string) --* 

                Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                
              

              - **responseParameters** *(dict) --* 

                A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **responseTemplates** *(dict) --* 

                Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
      
    
    

  .. py:method:: get_integration_response(**kwargs)

    

    Represents a get integration response.

    

    **Request Syntax** 
    ::

      response = client.get_integration_response(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          statusCode='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Specifies a get integration response request's API identifier.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      Specifies a get integration response request's resource identifier.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies a get integration response request's HTTP method.

      

    
    :type statusCode: string
    :param statusCode: **[REQUIRED]** 

      Specifies a get integration response request's status code.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'statusCode': 'string',
            'selectionPattern': 'string',
            'responseParameters': {
                'string': 'string'
            },
            'responseTemplates': {
                'string': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

          `Creating an API`_  
        

        - **statusCode** *(string) --* 

          Specifies the status code that is used to map the integration response to an existing  MethodResponse .

          
        

        - **selectionPattern** *(string) --* 

          Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

          
        

        - **responseParameters** *(dict) --* 

          A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **responseTemplates** *(dict) --* 

          Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
    

  .. py:method:: get_method(**kwargs)

    

    Describe an existing  Method resource.

    

    **Request Syntax** 
    ::

      response = client.get_method(
          restApiId='string',
          resourceId='string',
          httpMethod='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Method resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The  Resource identifier for the  Method resource.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies the method request's HTTP method type.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'httpMethod': 'string',
            'authorizationType': 'string',
            'authorizerId': 'string',
            'apiKeyRequired': True|False,
            'requestParameters': {
                'string': True|False
            },
            'requestModels': {
                'string': 'string'
            },
            'methodResponses': {
                'string': {
                    'statusCode': 'string',
                    'responseParameters': {
                        'string': True|False
                    },
                    'responseModels': {
                        'string': 'string'
                    }
                }
            },
            'methodIntegration': {
                'type': 'HTTP'|'AWS'|'MOCK',
                'httpMethod': 'string',
                'uri': 'string',
                'credentials': 'string',
                'requestParameters': {
                    'string': 'string'
                },
                'requestTemplates': {
                    'string': 'string'
                },
                'passthroughBehavior': 'string',
                'cacheNamespace': 'string',
                'cacheKeyParameters': [
                    'string',
                ],
                'integrationResponses': {
                    'string': {
                        'statusCode': 'string',
                        'selectionPattern': 'string',
                        'responseParameters': {
                            'string': 'string'
                        },
                        'responseTemplates': {
                            'string': 'string'
                        }
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a client-facing interface by which the client calls the API to access back-end resources. A **Method** resource is integrated with an  Integration resource. Both consist of a request and one or more responses. The method request takes the client input that is passed to the back end through the integration request. A method response returns the output from the back end to the client through an integration response. A method request is embodied in a **Method** resource, whereas an integration request is embodied in an  Integration resource. On the other hand, a method response is represented by a  MethodResponse resource, whereas an integration response is represented by an  IntegrationResponse resource. 

          

        

         Example: Retrive the GET method on a specified resource Request 

        The following example request retrieves the information about the GET method on an API resource (``3kzxbg5sa2`` ) of an API (``fugvjdxtri`` ). 

         ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T210259Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

        The successful response returns a ``200 OK`` status code and a payload similar to the following:

         ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": true, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E\")" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

        In the example above, the response template for the ``200 OK`` response maps the JSON output from the ``ListStreams`` action in the back end to an XML output. The mapping template is URL-encoded as ``%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E`` and the output is decoded using the `$util.urlDecode()`_ helper function.

            MethodResponse ,  Integration ,  IntegrationResponse ,  Resource , `Set up an API's method`_  
        

        - **httpMethod** *(string) --* 

          The method's HTTP verb.

          
        

        - **authorizationType** *(string) --* 

          The method's authorization type.

          
        

        - **authorizerId** *(string) --* 

          The identifier of an  Authorizer to use on this method. The ``authorizationType`` must be ``CUSTOM`` .

          
        

        - **apiKeyRequired** *(boolean) --* 

          A boolean flag specifying whether a valid  ApiKey is required to invoke this method.

          
        

        - **requestParameters** *(dict) --* 

          A key-value map defining required or optional method request parameters that can be accepted by Amazon API Gateway. A key is a method request parameter name matching the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` is a valid and unique parameter name. The value associated with the key is a Boolean flag indicating whether the parameter is required (``true`` ) or optional (``false`` ). The method request parameter names defined here are available in  Integration to be mapped to integration request parameters or templates.

          
          

          - *(string) --* 
            

            - *(boolean) --* 
      
    
        

        - **requestModels** *(dict) --* 

          A key-value map specifying data schemas, represented by  Model resources, (as the mapped value) of the request payloads of given content types (as the mapping key).

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **methodResponses** *(dict) --* 

          Gets a method response associated with a given HTTP status code. 

            

          The collection of method responses are encapsulated in a key-value map, where the key is a response's HTTP status code and the value is a  MethodResponse resource that specifies the response returned to the caller from the back end through the integration response.

           Example: Get a 200 OK response of a GET method Request 

          

           ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T215008Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

          The successful response returns a ``200 OK`` status code and a payload similar to the following:

           ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.operator": false, "method.response.header.operand_2": false, "method.response.header.operand_1": false }, "statusCode": "200" }``  

          

             `AWS CLI`_  
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

                

              

               Example: A **MethodResponse** instance of an API Request 

              The example request retrieves a **MethodResponse** of the 200 status code.

               ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

              The successful response returns ``200 OK`` status and a payload as follows:

               ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

              

                  Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
              

              - **statusCode** *(string) --* 

                The method response's status code.

                
              

              - **responseParameters** *(dict) --* 

                A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

                
                

                - *(string) --* 
                  

                  - *(boolean) --* 
            
          
              

              - **responseModels** *(dict) --* 

                Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
      
    
        

        - **methodIntegration** *(dict) --* 

          Gets the method's integration responsible for passing the client-submitted request to the back end and performing necessary transformations to make the request compliant with the back end.

            

          

           Example:  Request 

          

           ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T213210Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

          The successful response returns a ``200 OK`` status code and a payload similar to the following:

           ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true } ], "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:responses": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "0cjtch", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestTemplates": { "application/json": "{\n \"a\": \"$input.params('operand1')\",\n \"b\": \"$input.params('operand2')\", \n \"op\": \"$input.params('operator')\" \n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-west-2:lambda:path//2015-03-31/functions/arn:aws:lambda:us-west-2:123456789012:function:Calc/invocations", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.operator": "integration.response.body.op", "method.response.header.operand_2": "integration.response.body.b", "method.response.header.operand_1": "integration.response.body.a" }, "responseTemplates": { "application/json": "#set($res = $input.path('$'))\n{\n \"result\": \"$res.a, $res.b, $res.op => $res.c\",\n \"a\" : \"$res.a\",\n \"b\" : \"$res.b\",\n \"op\" : \"$res.op\",\n \"c\" : \"$res.c\"\n}" }, "selectionPattern": "", "statusCode": "200" } } }``  

          

             `AWS CLI`_  
          

          - **type** *(string) --* 

            Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

            
          

          - **httpMethod** *(string) --* 

            Specifies the integration's HTTP method type.

            
          

          - **uri** *(string) --* 

            Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

            
          

          - **credentials** *(string) --* 

            Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

            
          

          - **requestParameters** *(dict) --* 

            A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

            
            

            - *(string) --* 
              

              - *(string) --* 
        
      
          

          - **requestTemplates** *(dict) --* 

            Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

            
            

            - *(string) --* 
              

              - *(string) --* 
        
      
          

          - **passthroughBehavior** *(string) --*  

            Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

             

             
            * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
             
            * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
             
            * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
             

             
          

          - **cacheNamespace** *(string) --* 

            Specifies the integration's cache namespace.

            
          

          - **cacheKeyParameters** *(list) --* 

            Specifies the integration's cache key parameters.

            
            

            - *(string) --* 
        
          

          - **integrationResponses** *(dict) --* 

            Specifies the integration's responses.

              

            

             Example: Get integration responses of a method Request 

            

             ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

            The successful response returns ``200 OK`` status and a payload as follows:

             ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

            

               `Creating an API`_  
            

            - *(string) --* 
              

              - *(dict) --* 

                Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                  `Creating an API`_  
                

                - **statusCode** *(string) --* 

                  Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                  
                

                - **selectionPattern** *(string) --* 

                  Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                  
                

                - **responseParameters** *(dict) --* 

                  A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
                

                - **responseTemplates** *(dict) --* 

                  Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
        
      
      
    

  .. py:method:: get_method_response(**kwargs)

    

    Describes a  MethodResponse resource.

    

    **Request Syntax** 
    ::

      response = client.get_method_response(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          statusCode='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  MethodResponse resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The  Resource identifier for the  MethodResponse resource.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      The HTTP verb of the  Method resource.

      

    
    :type statusCode: string
    :param statusCode: **[REQUIRED]** 

      The status code for the  MethodResponse resource.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'statusCode': 'string',
            'responseParameters': {
                'string': True|False
            },
            'responseModels': {
                'string': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

          

        

         Example: A **MethodResponse** instance of an API Request 

        The example request retrieves a **MethodResponse** of the 200 status code.

         ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

        The successful response returns ``200 OK`` status and a payload as follows:

         ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

        

            Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
        

        - **statusCode** *(string) --* 

          The method response's status code.

          
        

        - **responseParameters** *(dict) --* 

          A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

          
          

          - *(string) --* 
            

            - *(boolean) --* 
      
    
        

        - **responseModels** *(dict) --* 

          Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
    

  .. py:method:: get_model(**kwargs)

    

    Describes an existing model defined for a  RestApi resource.

    

    **Request Syntax** 
    ::

      response = client.get_model(
          restApiId='string',
          modelName='string',
          flatten=True|False
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier under which the  Model exists.

      

    
    :type modelName: string
    :param modelName: **[REQUIRED]** 

      The name of the model as an identifier.

      

    
    :type flatten: boolean
    :param flatten: 

      A query parameter of a Boolean value to resolve (``true`` ) all external model references and returns a flattened model schema or not (``false`` ) The default is ``false`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'schema': 'string',
            'contentType': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the data structure of a method's request or response payload.

          

        A request model defines the data structure of the client-supplied request payload. A response model defines the data structure of the response payload returned by the back end. Although not required, models are useful for mapping payloads between the front end and back end.

         

        A model is used for generating an API's SDK, validating the input request body, and creating a skeletal mapping template.

            Method ,  MethodResponse , `Models and Mappings`_  
        

        - **id** *(string) --* 

          The identifier for the model resource.

          
        

        - **name** *(string) --* 

          The name of the model.

          
        

        - **description** *(string) --* 

          The description of the model.

          
        

        - **schema** *(string) --* 

          The schema for the model. For ``application/json`` models, this should be `JSON-schema draft v4`_ model. Do not include "\*/" characters in the description of any properties because such "\*/" characters may be interpreted as the closing marker for comments in some languages, such as Java or JavaScript, causing the installation of your API's SDK generated by API Gateway to fail.

          
        

        - **contentType** *(string) --* 

          The content-type for the model.

          
    

  .. py:method:: get_model_template(**kwargs)

    

    Generates a sample mapping template that can be used to transform a payload into the structure of a model.

    

    **Request Syntax** 
    ::

      response = client.get_model_template(
          restApiId='string',
          modelName='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The ID of the  RestApi under which the model exists.

      

    
    :type modelName: string
    :param modelName: **[REQUIRED]** 

      The name of the model for which to generate a template.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'value': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a mapping template used to transform a payload.

          `Mapping Templates`_  
        

        - **value** *(string) --* 

          The Apache `Velocity Template Language (VTL)`_ template content used for the template resource.

          
    

  .. py:method:: get_models(**kwargs)

    

    Describes existing  Models defined for a  RestApi resource.

    

    **Request Syntax** 
    ::

      response = client.get_models(
          restApiId='string',
          position='string',
          limit=123
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier.

      

    
    :type position: string
    :param position: 

      The position of the next set of results in the  Models resource to get information about.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of models in the collection to get information about. The default limit is 25. It should be an integer between 1 - 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'id': 'string',
                    'name': 'string',
                    'description': 'string',
                    'schema': 'string',
                    'contentType': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  Model resources.

           Method ,  MethodResponse , `Models and Mappings`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          Gets the current  Model resource in the collection.

          
          

          - *(dict) --* 

            Represents the data structure of a method's request or response payload.

              

            A request model defines the data structure of the client-supplied request payload. A response model defines the data structure of the response payload returned by the back end. Although not required, models are useful for mapping payloads between the front end and back end.

             

            A model is used for generating an API's SDK, validating the input request body, and creating a skeletal mapping template.

                Method ,  MethodResponse , `Models and Mappings`_  
            

            - **id** *(string) --* 

              The identifier for the model resource.

              
            

            - **name** *(string) --* 

              The name of the model.

              
            

            - **description** *(string) --* 

              The description of the model.

              
            

            - **schema** *(string) --* 

              The schema for the model. For ``application/json`` models, this should be `JSON-schema draft v4`_ model. Do not include "\*/" characters in the description of any properties because such "\*/" characters may be interpreted as the closing marker for comments in some languages, such as Java or JavaScript, causing the installation of your API's SDK generated by API Gateway to fail.

              
            

            - **contentType** *(string) --* 

              The content-type for the model.

              
        
      
    

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


  .. py:method:: get_resource(**kwargs)

    

    Lists information about a resource.

    

    **Request Syntax** 
    ::

      response = client.get_resource(
          restApiId='string',
          resourceId='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The identifier for the  Resource resource.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'parentId': 'string',
            'pathPart': 'string',
            'path': 'string',
            'resourceMethods': {
                'string': {
                    'httpMethod': 'string',
                    'authorizationType': 'string',
                    'authorizerId': 'string',
                    'apiKeyRequired': True|False,
                    'requestParameters': {
                        'string': True|False
                    },
                    'requestModels': {
                        'string': 'string'
                    },
                    'methodResponses': {
                        'string': {
                            'statusCode': 'string',
                            'responseParameters': {
                                'string': True|False
                            },
                            'responseModels': {
                                'string': 'string'
                            }
                        }
                    },
                    'methodIntegration': {
                        'type': 'HTTP'|'AWS'|'MOCK',
                        'httpMethod': 'string',
                        'uri': 'string',
                        'credentials': 'string',
                        'requestParameters': {
                            'string': 'string'
                        },
                        'requestTemplates': {
                            'string': 'string'
                        },
                        'passthroughBehavior': 'string',
                        'cacheNamespace': 'string',
                        'cacheKeyParameters': [
                            'string',
                        ],
                        'integrationResponses': {
                            'string': {
                                'statusCode': 'string',
                                'selectionPattern': 'string',
                                'responseParameters': {
                                    'string': 'string'
                                },
                                'responseTemplates': {
                                    'string': 'string'
                                }
                            }
                        }
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an API resource.

          `Create an API`_  
        

        - **id** *(string) --* 

          The resource's identifier.

          
        

        - **parentId** *(string) --* 

          The parent resource's identifier.

          
        

        - **pathPart** *(string) --* 

          The last path segment for this resource.

          
        

        - **path** *(string) --* 

          The full path for this resource.

          
        

        - **resourceMethods** *(dict) --* 

          Gets an API resource's method of a given HTTP verb.

            

          The resource methods are a map of methods indexed by methods' HTTP verbs enabled on the resource. This method map is included in the ``200 OK`` response of the ``GET /restapis/{restapi_id}/resources/{resource_id}`` or ``GET /restapis/{restapi_id}/resources/{resource_id}?embed=methods`` request.

           Example: Get the GET method of an API resource Request ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160608T031827Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160608/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": false, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

          If the ``OPTIONS`` is enabled on the resource, you can follow the example here to get that method. Just replace the ``GET`` of the last path segment in the request URL with ``OPTIONS`` .

             
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents a client-facing interface by which the client calls the API to access back-end resources. A **Method** resource is integrated with an  Integration resource. Both consist of a request and one or more responses. The method request takes the client input that is passed to the back end through the integration request. A method response returns the output from the back end to the client through an integration response. A method request is embodied in a **Method** resource, whereas an integration request is embodied in an  Integration resource. On the other hand, a method response is represented by a  MethodResponse resource, whereas an integration response is represented by an  IntegrationResponse resource. 

                

              

               Example: Retrive the GET method on a specified resource Request 

              The following example request retrieves the information about the GET method on an API resource (``3kzxbg5sa2`` ) of an API (``fugvjdxtri`` ). 

               ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T210259Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

              The successful response returns a ``200 OK`` status code and a payload similar to the following:

               ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": true, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E\")" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

              In the example above, the response template for the ``200 OK`` response maps the JSON output from the ``ListStreams`` action in the back end to an XML output. The mapping template is URL-encoded as ``%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E`` and the output is decoded using the `$util.urlDecode()`_ helper function.

                  MethodResponse ,  Integration ,  IntegrationResponse ,  Resource , `Set up an API's method`_  
              

              - **httpMethod** *(string) --* 

                The method's HTTP verb.

                
              

              - **authorizationType** *(string) --* 

                The method's authorization type.

                
              

              - **authorizerId** *(string) --* 

                The identifier of an  Authorizer to use on this method. The ``authorizationType`` must be ``CUSTOM`` .

                
              

              - **apiKeyRequired** *(boolean) --* 

                A boolean flag specifying whether a valid  ApiKey is required to invoke this method.

                
              

              - **requestParameters** *(dict) --* 

                A key-value map defining required or optional method request parameters that can be accepted by Amazon API Gateway. A key is a method request parameter name matching the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` is a valid and unique parameter name. The value associated with the key is a Boolean flag indicating whether the parameter is required (``true`` ) or optional (``false`` ). The method request parameter names defined here are available in  Integration to be mapped to integration request parameters or templates.

                
                

                - *(string) --* 
                  

                  - *(boolean) --* 
            
          
              

              - **requestModels** *(dict) --* 

                A key-value map specifying data schemas, represented by  Model resources, (as the mapped value) of the request payloads of given content types (as the mapping key).

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **methodResponses** *(dict) --* 

                Gets a method response associated with a given HTTP status code. 

                  

                The collection of method responses are encapsulated in a key-value map, where the key is a response's HTTP status code and the value is a  MethodResponse resource that specifies the response returned to the caller from the back end through the integration response.

                 Example: Get a 200 OK response of a GET method Request 

                

                 ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T215008Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                The successful response returns a ``200 OK`` status code and a payload similar to the following:

                 ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.operator": false, "method.response.header.operand_2": false, "method.response.header.operand_1": false }, "statusCode": "200" }``  

                

                   `AWS CLI`_  
                

                - *(string) --* 
                  

                  - *(dict) --* 

                    Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

                      

                    

                     Example: A **MethodResponse** instance of an API Request 

                    The example request retrieves a **MethodResponse** of the 200 status code.

                     ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                    The successful response returns ``200 OK`` status and a payload as follows:

                     ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

                    

                        Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
                    

                    - **statusCode** *(string) --* 

                      The method response's status code.

                      
                    

                    - **responseParameters** *(dict) --* 

                      A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

                      
                      

                      - *(string) --* 
                        

                        - *(boolean) --* 
                  
                
                    

                    - **responseModels** *(dict) --* 

                      Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

                      
                      

                      - *(string) --* 
                        

                        - *(string) --* 
                  
                
                
            
          
              

              - **methodIntegration** *(dict) --* 

                Gets the method's integration responsible for passing the client-submitted request to the back end and performing necessary transformations to make the request compliant with the back end.

                  

                

                 Example:  Request 

                

                 ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T213210Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                The successful response returns a ``200 OK`` status code and a payload similar to the following:

                 ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true } ], "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:responses": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "0cjtch", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestTemplates": { "application/json": "{\n \"a\": \"$input.params('operand1')\",\n \"b\": \"$input.params('operand2')\", \n \"op\": \"$input.params('operator')\" \n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-west-2:lambda:path//2015-03-31/functions/arn:aws:lambda:us-west-2:123456789012:function:Calc/invocations", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.operator": "integration.response.body.op", "method.response.header.operand_2": "integration.response.body.b", "method.response.header.operand_1": "integration.response.body.a" }, "responseTemplates": { "application/json": "#set($res = $input.path('$'))\n{\n \"result\": \"$res.a, $res.b, $res.op => $res.c\",\n \"a\" : \"$res.a\",\n \"b\" : \"$res.b\",\n \"op\" : \"$res.op\",\n \"c\" : \"$res.c\"\n}" }, "selectionPattern": "", "statusCode": "200" } } }``  

                

                   `AWS CLI`_  
                

                - **type** *(string) --* 

                  Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

                  
                

                - **httpMethod** *(string) --* 

                  Specifies the integration's HTTP method type.

                  
                

                - **uri** *(string) --* 

                  Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

                  
                

                - **credentials** *(string) --* 

                  Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

                  
                

                - **requestParameters** *(dict) --* 

                  A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
                

                - **requestTemplates** *(dict) --* 

                  Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
                

                - **passthroughBehavior** *(string) --*  

                  Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

                   

                   
                  * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
                   
                  * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
                   
                  * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
                   

                   
                

                - **cacheNamespace** *(string) --* 

                  Specifies the integration's cache namespace.

                  
                

                - **cacheKeyParameters** *(list) --* 

                  Specifies the integration's cache key parameters.

                  
                  

                  - *(string) --* 
              
                

                - **integrationResponses** *(dict) --* 

                  Specifies the integration's responses.

                    

                  

                   Example: Get integration responses of a method Request 

                  

                   ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                  The successful response returns ``200 OK`` status and a payload as follows:

                   ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

                  

                     `Creating an API`_  
                  

                  - *(string) --* 
                    

                    - *(dict) --* 

                      Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                        `Creating an API`_  
                      

                      - **statusCode** *(string) --* 

                        Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                        
                      

                      - **selectionPattern** *(string) --* 

                        Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                        
                      

                      - **responseParameters** *(dict) --* 

                        A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                        
                        

                        - *(string) --* 
                          

                          - *(string) --* 
                    
                  
                      

                      - **responseTemplates** *(dict) --* 

                        Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                        
                        

                        - *(string) --* 
                          

                          - *(string) --* 
                    
                  
                  
              
            
            
          
      
    
    

  .. py:method:: get_resources(**kwargs)

    

    Lists information about a collection of  Resource resources.

    

    **Request Syntax** 
    ::

      response = client.get_resources(
          restApiId='string',
          position='string',
          limit=123
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the Resource.

      

    
    :type position: string
    :param position: 

      The position of the next set of results in the current  Resources resource to get information about.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of  Resource resources in the collection to get information about. The default limit is 25. It should be an integer between 1 - 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'id': 'string',
                    'parentId': 'string',
                    'pathPart': 'string',
                    'path': 'string',
                    'resourceMethods': {
                        'string': {
                            'httpMethod': 'string',
                            'authorizationType': 'string',
                            'authorizerId': 'string',
                            'apiKeyRequired': True|False,
                            'requestParameters': {
                                'string': True|False
                            },
                            'requestModels': {
                                'string': 'string'
                            },
                            'methodResponses': {
                                'string': {
                                    'statusCode': 'string',
                                    'responseParameters': {
                                        'string': True|False
                                    },
                                    'responseModels': {
                                        'string': 'string'
                                    }
                                }
                            },
                            'methodIntegration': {
                                'type': 'HTTP'|'AWS'|'MOCK',
                                'httpMethod': 'string',
                                'uri': 'string',
                                'credentials': 'string',
                                'requestParameters': {
                                    'string': 'string'
                                },
                                'requestTemplates': {
                                    'string': 'string'
                                },
                                'passthroughBehavior': 'string',
                                'cacheNamespace': 'string',
                                'cacheKeyParameters': [
                                    'string',
                                ],
                                'integrationResponses': {
                                    'string': {
                                        'statusCode': 'string',
                                        'selectionPattern': 'string',
                                        'responseParameters': {
                                            'string': 'string'
                                        },
                                        'responseTemplates': {
                                            'string': 'string'
                                        }
                                    }
                                }
                            }
                        }
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  Resource resources.

          `Create an API`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          Gets the current  Resource resource in the collection.

          
          

          - *(dict) --* 

            Represents an API resource.

              `Create an API`_  
            

            - **id** *(string) --* 

              The resource's identifier.

              
            

            - **parentId** *(string) --* 

              The parent resource's identifier.

              
            

            - **pathPart** *(string) --* 

              The last path segment for this resource.

              
            

            - **path** *(string) --* 

              The full path for this resource.

              
            

            - **resourceMethods** *(dict) --* 

              Gets an API resource's method of a given HTTP verb.

                

              The resource methods are a map of methods indexed by methods' HTTP verbs enabled on the resource. This method map is included in the ``200 OK`` response of the ``GET /restapis/{restapi_id}/resources/{resource_id}`` or ``GET /restapis/{restapi_id}/resources/{resource_id}?embed=methods`` request.

               Example: Get the GET method of an API resource Request ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160608T031827Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160608/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": false, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

              If the ``OPTIONS`` is enabled on the resource, you can follow the example here to get that method. Just replace the ``GET`` of the last path segment in the request URL with ``OPTIONS`` .

                 
              

              - *(string) --* 
                

                - *(dict) --* 

                  Represents a client-facing interface by which the client calls the API to access back-end resources. A **Method** resource is integrated with an  Integration resource. Both consist of a request and one or more responses. The method request takes the client input that is passed to the back end through the integration request. A method response returns the output from the back end to the client through an integration response. A method request is embodied in a **Method** resource, whereas an integration request is embodied in an  Integration resource. On the other hand, a method response is represented by a  MethodResponse resource, whereas an integration response is represented by an  IntegrationResponse resource. 

                    

                  

                   Example: Retrive the GET method on a specified resource Request 

                  The following example request retrieves the information about the GET method on an API resource (``3kzxbg5sa2`` ) of an API (``fugvjdxtri`` ). 

                   ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T210259Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                  The successful response returns a ``200 OK`` status code and a payload similar to the following:

                   ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": true, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E\")" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

                  In the example above, the response template for the ``200 OK`` response maps the JSON output from the ``ListStreams`` action in the back end to an XML output. The mapping template is URL-encoded as ``%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E`` and the output is decoded using the `$util.urlDecode()`_ helper function.

                      MethodResponse ,  Integration ,  IntegrationResponse ,  Resource , `Set up an API's method`_  
                  

                  - **httpMethod** *(string) --* 

                    The method's HTTP verb.

                    
                  

                  - **authorizationType** *(string) --* 

                    The method's authorization type.

                    
                  

                  - **authorizerId** *(string) --* 

                    The identifier of an  Authorizer to use on this method. The ``authorizationType`` must be ``CUSTOM`` .

                    
                  

                  - **apiKeyRequired** *(boolean) --* 

                    A boolean flag specifying whether a valid  ApiKey is required to invoke this method.

                    
                  

                  - **requestParameters** *(dict) --* 

                    A key-value map defining required or optional method request parameters that can be accepted by Amazon API Gateway. A key is a method request parameter name matching the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` is a valid and unique parameter name. The value associated with the key is a Boolean flag indicating whether the parameter is required (``true`` ) or optional (``false`` ). The method request parameter names defined here are available in  Integration to be mapped to integration request parameters or templates.

                    
                    

                    - *(string) --* 
                      

                      - *(boolean) --* 
                
              
                  

                  - **requestModels** *(dict) --* 

                    A key-value map specifying data schemas, represented by  Model resources, (as the mapped value) of the request payloads of given content types (as the mapping key).

                    
                    

                    - *(string) --* 
                      

                      - *(string) --* 
                
              
                  

                  - **methodResponses** *(dict) --* 

                    Gets a method response associated with a given HTTP status code. 

                      

                    The collection of method responses are encapsulated in a key-value map, where the key is a response's HTTP status code and the value is a  MethodResponse resource that specifies the response returned to the caller from the back end through the integration response.

                     Example: Get a 200 OK response of a GET method Request 

                    

                     ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T215008Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                    The successful response returns a ``200 OK`` status code and a payload similar to the following:

                     ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.operator": false, "method.response.header.operand_2": false, "method.response.header.operand_1": false }, "statusCode": "200" }``  

                    

                       `AWS CLI`_  
                    

                    - *(string) --* 
                      

                      - *(dict) --* 

                        Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

                          

                        

                         Example: A **MethodResponse** instance of an API Request 

                        The example request retrieves a **MethodResponse** of the 200 status code.

                         ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                        The successful response returns ``200 OK`` status and a payload as follows:

                         ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

                        

                            Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
                        

                        - **statusCode** *(string) --* 

                          The method response's status code.

                          
                        

                        - **responseParameters** *(dict) --* 

                          A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

                          
                          

                          - *(string) --* 
                            

                            - *(boolean) --* 
                      
                    
                        

                        - **responseModels** *(dict) --* 

                          Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

                          
                          

                          - *(string) --* 
                            

                            - *(string) --* 
                      
                    
                    
                
              
                  

                  - **methodIntegration** *(dict) --* 

                    Gets the method's integration responsible for passing the client-submitted request to the back end and performing necessary transformations to make the request compliant with the back end.

                      

                    

                     Example:  Request 

                    

                     ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T213210Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                    The successful response returns a ``200 OK`` status code and a payload similar to the following:

                     ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true } ], "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:responses": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "0cjtch", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestTemplates": { "application/json": "{\n \"a\": \"$input.params('operand1')\",\n \"b\": \"$input.params('operand2')\", \n \"op\": \"$input.params('operator')\" \n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-west-2:lambda:path//2015-03-31/functions/arn:aws:lambda:us-west-2:123456789012:function:Calc/invocations", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.operator": "integration.response.body.op", "method.response.header.operand_2": "integration.response.body.b", "method.response.header.operand_1": "integration.response.body.a" }, "responseTemplates": { "application/json": "#set($res = $input.path('$'))\n{\n \"result\": \"$res.a, $res.b, $res.op => $res.c\",\n \"a\" : \"$res.a\",\n \"b\" : \"$res.b\",\n \"op\" : \"$res.op\",\n \"c\" : \"$res.c\"\n}" }, "selectionPattern": "", "statusCode": "200" } } }``  

                    

                       `AWS CLI`_  
                    

                    - **type** *(string) --* 

                      Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

                      
                    

                    - **httpMethod** *(string) --* 

                      Specifies the integration's HTTP method type.

                      
                    

                    - **uri** *(string) --* 

                      Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

                      
                    

                    - **credentials** *(string) --* 

                      Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

                      
                    

                    - **requestParameters** *(dict) --* 

                      A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

                      
                      

                      - *(string) --* 
                        

                        - *(string) --* 
                  
                
                    

                    - **requestTemplates** *(dict) --* 

                      Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

                      
                      

                      - *(string) --* 
                        

                        - *(string) --* 
                  
                
                    

                    - **passthroughBehavior** *(string) --*  

                      Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

                       

                       
                      * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
                       
                      * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
                       
                      * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
                       

                       
                    

                    - **cacheNamespace** *(string) --* 

                      Specifies the integration's cache namespace.

                      
                    

                    - **cacheKeyParameters** *(list) --* 

                      Specifies the integration's cache key parameters.

                      
                      

                      - *(string) --* 
                  
                    

                    - **integrationResponses** *(dict) --* 

                      Specifies the integration's responses.

                        

                      

                       Example: Get integration responses of a method Request 

                      

                       ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                      The successful response returns ``200 OK`` status and a payload as follows:

                       ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

                      

                         `Creating an API`_  
                      

                      - *(string) --* 
                        

                        - *(dict) --* 

                          Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                            `Creating an API`_  
                          

                          - **statusCode** *(string) --* 

                            Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                            
                          

                          - **selectionPattern** *(string) --* 

                            Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                            
                          

                          - **responseParameters** *(dict) --* 

                            A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                            
                            

                            - *(string) --* 
                              

                              - *(string) --* 
                        
                      
                          

                          - **responseTemplates** *(dict) --* 

                            Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                            
                            

                            - *(string) --* 
                              

                              - *(string) --* 
                        
                      
                      
                  
                
                
              
          
        
        
      
    

  .. py:method:: get_rest_api(**kwargs)

    

    Lists the  RestApi resource in the collection.

    

    **Request Syntax** 
    ::

      response = client.get_rest_api(
          restApiId='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi resource.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'createdDate': datetime(2015, 1, 1),
            'warnings': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a REST API.

          `Create an API`_  
        

        - **id** *(string) --* 

          The API's identifier. This identifier is unique across all of your APIs in Amazon API Gateway.

          
        

        - **name** *(string) --* 

          The API's name.

          
        

        - **description** *(string) --* 

          The API's description.

          
        

        - **createdDate** *(datetime) --* 

          The date when the API was created, in `ISO 8601 format`_ .

          
        

        - **warnings** *(list) --* 

          The warning messages reported when ``failonwarnings`` is turned on during API import.

          
          

          - *(string) --* 
      
    

  .. py:method:: get_rest_apis(**kwargs)

    

    Lists the  RestApis resources for your collection.

    

    **Request Syntax** 
    ::

      response = client.get_rest_apis(
          position='string',
          limit=123
      )
    :type position: string
    :param position: 

      The position of the current  RestApis resource in the collection to get information about.

      

    
    :type limit: integer
    :param limit: 

      The maximum number of  RestApi resources in the collection to get information about. The default limit is 25. It should be an integer between 1 - 500.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'id': 'string',
                    'name': 'string',
                    'description': 'string',
                    'createdDate': datetime(2015, 1, 1),
                    'warnings': [
                        'string',
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains references to your APIs and links that guide you in how to interact with your collection. A collection offers a paginated view of your APIs.

          `Create an API`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          An array of links to the current page of  RestApi resources.

          
          

          - *(dict) --* 

            Represents a REST API.

              `Create an API`_  
            

            - **id** *(string) --* 

              The API's identifier. This identifier is unique across all of your APIs in Amazon API Gateway.

              
            

            - **name** *(string) --* 

              The API's name.

              
            

            - **description** *(string) --* 

              The API's description.

              
            

            - **createdDate** *(datetime) --* 

              The date when the API was created, in `ISO 8601 format`_ .

              
            

            - **warnings** *(list) --* 

              The warning messages reported when ``failonwarnings`` is turned on during API import.

              
              

              - *(string) --* 
          
        
      
    

  .. py:method:: get_sdk(**kwargs)

    

    Generates a client SDK for a  RestApi and  Stage .

    

    **Request Syntax** 
    ::

      response = client.get_sdk(
          restApiId='string',
          stageName='string',
          sdkType='string',
          parameters={
              'string': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi that the SDK will use.

      

    
    :type stageName: string
    :param stageName: **[REQUIRED]** 

      The name of the  Stage that the SDK will use.

      

    
    :type sdkType: string
    :param sdkType: **[REQUIRED]** 

      The language for the generated SDK. Currently ``javascript`` , ``android`` , and ``objectivec`` (for iOS) are supported.

      

    
    :type parameters: dict
    :param parameters: 

      A key-value map of query string parameters that specify properties of the SDK, depending on the requested ``sdkType`` . For ``sdkType`` of ``objectivec`` , a parameter named ``classPrefix`` is required. For ``sdkType`` of ``android`` , parameters named ``groupId`` , ``artifactId`` , ``artifactVersion`` , and ``invokerPackage`` are required.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'contentType': 'string',
            'contentDisposition': 'string',
            'body': StreamingBody()
        }
      **Response Structure** 

      

      - *(dict) --* 

        The binary blob response to  GetSdk , which contains the generated SDK.

        
        

        - **contentType** *(string) --* 

          The content-type header value in the HTTP response.

          
        

        - **contentDisposition** *(string) --* 

          The content-disposition header value in the HTTP response.

          
        

        - **body** (:class:`.StreamingBody`) -- 

          The binary blob response to  GetSdk , which contains the generated SDK.

          
    

  .. py:method:: get_stage(**kwargs)

    

    Gets information about a  Stage resource.

    

    **Request Syntax** 
    ::

      response = client.get_stage(
          restApiId='string',
          stageName='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi resource for the  Stage resource to get information about.

      

    
    :type stageName: string
    :param stageName: **[REQUIRED]** 

      The name of the  Stage resource to get information about.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentId': 'string',
            'clientCertificateId': 'string',
            'stageName': 'string',
            'description': 'string',
            'cacheClusterEnabled': True|False,
            'cacheClusterSize': '0.5'|'1.6'|'6.1'|'13.5'|'28.4'|'58.2'|'118'|'237',
            'cacheClusterStatus': 'CREATE_IN_PROGRESS'|'AVAILABLE'|'DELETE_IN_PROGRESS'|'NOT_AVAILABLE'|'FLUSH_IN_PROGRESS',
            'methodSettings': {
                'string': {
                    'metricsEnabled': True|False,
                    'loggingLevel': 'string',
                    'dataTraceEnabled': True|False,
                    'throttlingBurstLimit': 123,
                    'throttlingRateLimit': 123.0,
                    'cachingEnabled': True|False,
                    'cacheTtlInSeconds': 123,
                    'cacheDataEncrypted': True|False,
                    'requireAuthorizationForCacheControl': True|False,
                    'unauthorizedCacheControlHeaderStrategy': 'FAIL_WITH_403'|'SUCCEED_WITH_RESPONSE_HEADER'|'SUCCEED_WITHOUT_RESPONSE_HEADER'
                }
            },
            'variables': {
                'string': 'string'
            },
            'createdDate': datetime(2015, 1, 1),
            'lastUpdatedDate': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a unique identifier for a version of a deployed  RestApi that is callable by users.

          `Deploy an API`_  
        

        - **deploymentId** *(string) --* 

          The identifier of the  Deployment that the stage points to.

          
        

        - **clientCertificateId** *(string) --* 

          The identifier of a client certificate for an API stage.

          
        

        - **stageName** *(string) --* 

          The name of the stage is the first path segment in the Uniform Resource Identifier (URI) of a call to Amazon API Gateway.

          
        

        - **description** *(string) --* 

          The stage's description.

          
        

        - **cacheClusterEnabled** *(boolean) --* 

          Specifies whether a cache cluster is enabled for the stage.

          
        

        - **cacheClusterSize** *(string) --* 

          The size of the cache cluster for the stage, if enabled.

          
        

        - **cacheClusterStatus** *(string) --* 

          The status of the cache cluster for the stage, if enabled.

          
        

        - **methodSettings** *(dict) --* 

          A map that defines the method settings for a  Stage resource. Keys (designated as ``/{method_setting_key`` below) are method paths defined as ``{resource_path}/{http_method}`` for an individual method override, or ``/\*/\*`` for overriding all methods in the stage. Any forward slash ("/") characters in the ``resource_path`` part must be encoded as "~1" as in, for example, ``~1resource~1sub-resource/GET`` .

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Specifies the method setting properties.

              
              

              - **metricsEnabled** *(boolean) --* 

                Specifies whether Amazon CloudWatch metrics are enabled for this method. The PATCH path for this setting is ``/{method_setting_key}/metrics/enabled`` , and the value is a Boolean.

                
              

              - **loggingLevel** *(string) --* 

                Specifies the logging level for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/loglevel`` , and the available levels are ``OFF`` , ``ERROR`` , and ``INFO`` .

                
              

              - **dataTraceEnabled** *(boolean) --* 

                Specifies whether data trace logging is enabled for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/dataTrace`` , and the value is a Boolean.

                
              

              - **throttlingBurstLimit** *(integer) --* 

                Specifies the throttling burst limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/burstLimit`` , and the value is an integer.

                
              

              - **throttlingRateLimit** *(float) --* 

                Specifies the throttling rate limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/rateLimit`` , and the value is a double.

                
              

              - **cachingEnabled** *(boolean) --* 

                Specifies whether responses should be cached and returned for requests. A cache cluster must be enabled on the stage for responses to be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/enabled`` , and the value is a Boolean.

                
              

              - **cacheTtlInSeconds** *(integer) --* 

                Specifies the time to live (TTL), in seconds, for cached responses. The higher the TTL, the longer the response will be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/ttlInSeconds`` , and the value is an integer.

                
              

              - **cacheDataEncrypted** *(boolean) --* 

                Specifies whether the cached responses are encrypted. The PATCH path for this setting is ``/{method_setting_key}/caching/dataEncrypted`` , and the value is a Boolean.

                
              

              - **requireAuthorizationForCacheControl** *(boolean) --* 

                Specifies whether authorization is required for a cache invalidation request. The PATCH path for this setting is ``/{method_setting_key}/caching/requireAuthorizationForCacheControl`` , and the value is a Boolean.

                
              

              - **unauthorizedCacheControlHeaderStrategy** *(string) --* 

                Specifies how to handle unauthorized requests for cache invalidation. The PATCH path for this setting is ``/{method_setting_key}/caching/unauthorizedCacheControlHeaderStrategy`` , and the available values are ``FAIL_WITH_403`` , ``SUCCEED_WITH_RESPONSE_HEADER`` , ``SUCCEED_WITHOUT_RESPONSE_HEADER`` .

                
          
      
    
        

        - **variables** *(dict) --* 

          A map that defines the stage variables for a  Stage resource. Variable names can have alphanumeric and underscore characters, and the values must match ``[A-Za-z0-9-._~:/?#=,]+`` .

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **createdDate** *(datetime) --* 

          The date and time that the stage was created, in `ISO 8601 format`_ .

          
        

        - **lastUpdatedDate** *(datetime) --* 

          The date and time that information about the stage was last updated, in `ISO 8601 format`_ .

          
    

  .. py:method:: get_stages(**kwargs)

    

    Gets information about one or more  Stage resources.

    

    **Request Syntax** 
    ::

      response = client.get_stages(
          restApiId='string',
          deploymentId='string'
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The stages' API identifiers.

      

    
    :type deploymentId: string
    :param deploymentId: 

      The stages' deployment identifiers.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'item': [
                {
                    'deploymentId': 'string',
                    'clientCertificateId': 'string',
                    'stageName': 'string',
                    'description': 'string',
                    'cacheClusterEnabled': True|False,
                    'cacheClusterSize': '0.5'|'1.6'|'6.1'|'13.5'|'28.4'|'58.2'|'118'|'237',
                    'cacheClusterStatus': 'CREATE_IN_PROGRESS'|'AVAILABLE'|'DELETE_IN_PROGRESS'|'NOT_AVAILABLE'|'FLUSH_IN_PROGRESS',
                    'methodSettings': {
                        'string': {
                            'metricsEnabled': True|False,
                            'loggingLevel': 'string',
                            'dataTraceEnabled': True|False,
                            'throttlingBurstLimit': 123,
                            'throttlingRateLimit': 123.0,
                            'cachingEnabled': True|False,
                            'cacheTtlInSeconds': 123,
                            'cacheDataEncrypted': True|False,
                            'requireAuthorizationForCacheControl': True|False,
                            'unauthorizedCacheControlHeaderStrategy': 'FAIL_WITH_403'|'SUCCEED_WITH_RESPONSE_HEADER'|'SUCCEED_WITHOUT_RESPONSE_HEADER'
                        }
                    },
                    'variables': {
                        'string': 'string'
                    },
                    'createdDate': datetime(2015, 1, 1),
                    'lastUpdatedDate': datetime(2015, 1, 1)
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A list of  Stage resources that are associated with the  ApiKey resource.

         `Deploying API in Stages`_ 
        

        - **item** *(list) --* 

          An individual  Stage resource.

          
          

          - *(dict) --* 

            Represents a unique identifier for a version of a deployed  RestApi that is callable by users.

              `Deploy an API`_  
            

            - **deploymentId** *(string) --* 

              The identifier of the  Deployment that the stage points to.

              
            

            - **clientCertificateId** *(string) --* 

              The identifier of a client certificate for an API stage.

              
            

            - **stageName** *(string) --* 

              The name of the stage is the first path segment in the Uniform Resource Identifier (URI) of a call to Amazon API Gateway.

              
            

            - **description** *(string) --* 

              The stage's description.

              
            

            - **cacheClusterEnabled** *(boolean) --* 

              Specifies whether a cache cluster is enabled for the stage.

              
            

            - **cacheClusterSize** *(string) --* 

              The size of the cache cluster for the stage, if enabled.

              
            

            - **cacheClusterStatus** *(string) --* 

              The status of the cache cluster for the stage, if enabled.

              
            

            - **methodSettings** *(dict) --* 

              A map that defines the method settings for a  Stage resource. Keys (designated as ``/{method_setting_key`` below) are method paths defined as ``{resource_path}/{http_method}`` for an individual method override, or ``/\*/\*`` for overriding all methods in the stage. Any forward slash ("/") characters in the ``resource_path`` part must be encoded as "~1" as in, for example, ``~1resource~1sub-resource/GET`` .

              
              

              - *(string) --* 
                

                - *(dict) --* 

                  Specifies the method setting properties.

                  
                  

                  - **metricsEnabled** *(boolean) --* 

                    Specifies whether Amazon CloudWatch metrics are enabled for this method. The PATCH path for this setting is ``/{method_setting_key}/metrics/enabled`` , and the value is a Boolean.

                    
                  

                  - **loggingLevel** *(string) --* 

                    Specifies the logging level for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/loglevel`` , and the available levels are ``OFF`` , ``ERROR`` , and ``INFO`` .

                    
                  

                  - **dataTraceEnabled** *(boolean) --* 

                    Specifies whether data trace logging is enabled for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/dataTrace`` , and the value is a Boolean.

                    
                  

                  - **throttlingBurstLimit** *(integer) --* 

                    Specifies the throttling burst limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/burstLimit`` , and the value is an integer.

                    
                  

                  - **throttlingRateLimit** *(float) --* 

                    Specifies the throttling rate limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/rateLimit`` , and the value is a double.

                    
                  

                  - **cachingEnabled** *(boolean) --* 

                    Specifies whether responses should be cached and returned for requests. A cache cluster must be enabled on the stage for responses to be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/enabled`` , and the value is a Boolean.

                    
                  

                  - **cacheTtlInSeconds** *(integer) --* 

                    Specifies the time to live (TTL), in seconds, for cached responses. The higher the TTL, the longer the response will be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/ttlInSeconds`` , and the value is an integer.

                    
                  

                  - **cacheDataEncrypted** *(boolean) --* 

                    Specifies whether the cached responses are encrypted. The PATCH path for this setting is ``/{method_setting_key}/caching/dataEncrypted`` , and the value is a Boolean.

                    
                  

                  - **requireAuthorizationForCacheControl** *(boolean) --* 

                    Specifies whether authorization is required for a cache invalidation request. The PATCH path for this setting is ``/{method_setting_key}/caching/requireAuthorizationForCacheControl`` , and the value is a Boolean.

                    
                  

                  - **unauthorizedCacheControlHeaderStrategy** *(string) --* 

                    Specifies how to handle unauthorized requests for cache invalidation. The PATCH path for this setting is ``/{method_setting_key}/caching/unauthorizedCacheControlHeaderStrategy`` , and the available values are ``FAIL_WITH_403`` , ``SUCCEED_WITH_RESPONSE_HEADER`` , ``SUCCEED_WITHOUT_RESPONSE_HEADER`` .

                    
              
          
        
            

            - **variables** *(dict) --* 

              A map that defines the stage variables for a  Stage resource. Variable names can have alphanumeric and underscore characters, and the values must match ``[A-Za-z0-9-._~:/?#=,]+`` .

              
              

              - *(string) --* 
                

                - *(string) --* 
          
        
            

            - **createdDate** *(datetime) --* 

              The date and time that the stage was created, in `ISO 8601 format`_ .

              
            

            - **lastUpdatedDate** *(datetime) --* 

              The date and time that information about the stage was last updated, in `ISO 8601 format`_ .

              
        
      
    

  .. py:method:: get_usage(**kwargs)

    

    Gets the usage data of a usage plan in a specified time interval.

    

    **Request Syntax** 
    ::

      response = client.get_usage(
          usagePlanId='string',
          keyId='string',
          startDate='string',
          endDate='string',
          position='string',
          limit=123
      )
    :type usagePlanId: string
    :param usagePlanId: **[REQUIRED]** 

      The Id of the usage plan associated with the usage data.

      

    
    :type keyId: string
    :param keyId: 

      The Id of the API key associated with the resultant usage data.

      

    
    :type startDate: string
    :param startDate: **[REQUIRED]** 

      The starting date (e.g., 2016-01-01) of the usage data.

      

    
    :type endDate: string
    :param endDate: **[REQUIRED]** 

      The ending date (e.g., 2016-12-31) of the usage data.

      

    
    :type position: string
    :param position: 

      Position

      

    
    :type limit: integer
    :param limit: 

      The maximum number of results to be returned.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'usagePlanId': 'string',
            'startDate': 'string',
            'endDate': 'string',
            'position': 'string',
            'items': {
                'string': [
                    [
                        123,
                    ],
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the usage data of a usage plan.

           `Create and Use Usage Plans`_ , `Manage Usage in a Usage Plan`_  
        

        - **usagePlanId** *(string) --* 

          The plan Id associated with this usage data.

          
        

        - **startDate** *(string) --* 

          The starting date of the usage data.

          
        

        - **endDate** *(string) --* 

          The ending date of the usage data.

          
        

        - **position** *(string) --* 
        

        - **items** *(dict) --* 

          The usage data, as daily logs of used and remaining quotas, over the specified time interval indexed over the API keys in a usage plan. For example, ``{..., "values" : { "{api_key}" : [ [0, 100], [10, 90], [100, 10]]}`` , where ``{api_key}`` stands for an API key value and the daily log entry is of the format ``[used quota, remaining quota]`` .

          
          

          - *(string) --* 
            

            - *(list) --* 
              

              - *(list) --* 
                

                - *(integer) --* 
            
          
      
    
    

  .. py:method:: get_usage_plan(**kwargs)

    

    Gets a usage plan of a given plan identifier.

    

    **Request Syntax** 
    ::

      response = client.get_usage_plan(
          usagePlanId='string'
      )
    :type usagePlanId: string
    :param usagePlanId: **[REQUIRED]** 

      The identifier of the  UsagePlan resource to be retrieved.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'apiStages': [
                {
                    'apiId': 'string',
                    'stage': 'string'
                },
            ],
            'throttle': {
                'burstLimit': 123,
                'rateLimit': 123.0
            },
            'quota': {
                'limit': 123,
                'offset': 123,
                'period': 'DAY'|'WEEK'|'MONTH'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a usage plan than can specify who can assess associated API stages with specified request limits and quotas.

          

        In a usage plan, you associate an API by specifying the API's Id and a stage name of the specified API. You add plan customers by adding API keys to the plan. 

           `Create and Use Usage Plans`_  
        

        - **id** *(string) --* 

          The identifier of a  UsagePlan resource.

          
        

        - **name** *(string) --* 

          The name of a usage plan.

          
        

        - **description** *(string) --* 

          The description of a usage plan.

          
        

        - **apiStages** *(list) --* 

          The associated API stages of a usage plan.

          
          

          - *(dict) --* 

            API stage name of the associated API stage in a usage plan.

            
            

            - **apiId** *(string) --* 

              API Id of the associated API stage in a usage plan.

              
            

            - **stage** *(string) --* 

              API stage name of the associated API stage in a usage plan.

              
        
      
        

        - **throttle** *(dict) --* 

          The request throttle limits of a usage plan.

          
          

          - **burstLimit** *(integer) --* 

            The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

            
          

          - **rateLimit** *(float) --* 

            The API request steady-state rate limit.

            
      
        

        - **quota** *(dict) --* 

          The maximum number of permitted requests per a given unit time interval.

          
          

          - **limit** *(integer) --* 

            The maximum number of requests that can be made in a given time period.

            
          

          - **offset** *(integer) --* 

            The number of requests subtracted from the given limit in the initial time period.

            
          

          - **period** *(string) --* 

            The time period in which the limit applies. Valid values are "DAY", "WEEK" or "MONTH".

            
      
    

  .. py:method:: get_usage_plan_key(**kwargs)

    

    Gets a usage plan key of a given key identifier.

    

    **Request Syntax** 
    ::

      response = client.get_usage_plan_key(
          usagePlanId='string',
          keyId='string'
      )
    :type usagePlanId: string
    :param usagePlanId: **[REQUIRED]** 

      The Id of the  UsagePlan resource representing the usage plan containing the to-be-retrieved  UsagePlanKey resource representing a plan customer.

      

    
    :type keyId: string
    :param keyId: **[REQUIRED]** 

      The key Id of the to-be-retrieved  UsagePlanKey resource representing a plan customer.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'type': 'string',
            'value': 'string',
            'name': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a usage plan key to identify a plan customer.

          

        To associate an API stage with a selected API key in a usage plan, you must create a UsagePlanKey resource to represent the selected  ApiKey .

         "  `Create and Use Usage Plans`_  
        

        - **id** *(string) --* 

          The Id of a usage plan key.

          
        

        - **type** *(string) --* 

          The type of a usage plan key. Currently, the valid key type is ``API_KEY`` .

          
        

        - **value** *(string) --* 

          The value of a usage plan key.

          
        

        - **name** *(string) --* 

          The name of a usage plan key.

          
    

  .. py:method:: get_usage_plan_keys(**kwargs)

    

    Gets all the usage plan keys representing the API keys added to a specified usage plan.

    

    **Request Syntax** 
    ::

      response = client.get_usage_plan_keys(
          usagePlanId='string',
          position='string',
          limit=123,
          nameQuery='string'
      )
    :type usagePlanId: string
    :param usagePlanId: **[REQUIRED]** 

      The Id of the  UsagePlan resource representing the usage plan containing the to-be-retrieved  UsagePlanKey resource representing a plan customer.

      

    
    :type position: string
    :param position: 

      A query parameter specifying the zero-based index specifying the position of a usage plan key.

      

    
    :type limit: integer
    :param limit: 

      A query parameter specifying the maximum number usage plan keys returned by the GET request.

      

    
    :type nameQuery: string
    :param nameQuery: 

      A query parameter specifying the name of the to-be-returned usage plan keys.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'id': 'string',
                    'type': 'string',
                    'value': 'string',
                    'name': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the collection of usage plan keys added to usage plans for the associated API keys and, possibly, other types of keys.

          `Create and Use Usage Plans`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          Gets the current item of the usage plan keys collection.

          
          

          - *(dict) --* 

            Represents a usage plan key to identify a plan customer.

              

            To associate an API stage with a selected API key in a usage plan, you must create a UsagePlanKey resource to represent the selected  ApiKey .

             "  `Create and Use Usage Plans`_  
            

            - **id** *(string) --* 

              The Id of a usage plan key.

              
            

            - **type** *(string) --* 

              The type of a usage plan key. Currently, the valid key type is ``API_KEY`` .

              
            

            - **value** *(string) --* 

              The value of a usage plan key.

              
            

            - **name** *(string) --* 

              The name of a usage plan key.

              
        
      
    

  .. py:method:: get_usage_plans(**kwargs)

    

    Gets all the usage plans of the caller's account.

    

    **Request Syntax** 
    ::

      response = client.get_usage_plans(
          position='string',
          keyId='string',
          limit=123
      )
    :type position: string
    :param position: 

      The zero-based array index specifying the position of the to-be-retrieved  UsagePlan resource.

      

    
    :type keyId: string
    :param keyId: 

      The identifier of the API key associated with the usage plans.

      

    
    :type limit: integer
    :param limit: 

      The number of  UsagePlan resources to be returned as the result.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'position': 'string',
            'items': [
                {
                    'id': 'string',
                    'name': 'string',
                    'description': 'string',
                    'apiStages': [
                        {
                            'apiId': 'string',
                            'stage': 'string'
                        },
                    ],
                    'throttle': {
                        'burstLimit': 123,
                        'rateLimit': 123.0
                    },
                    'quota': {
                        'limit': 123,
                        'offset': 123,
                        'period': 'DAY'|'WEEK'|'MONTH'
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of usage plans for an AWS account.

          `Create and Use Usage Plans`_  
        

        - **position** *(string) --* 
        

        - **items** *(list) --* 

          Gets the current item when enumerating the collection of  UsagePlan .

          
          

          - *(dict) --* 

            Represents a usage plan than can specify who can assess associated API stages with specified request limits and quotas.

              

            In a usage plan, you associate an API by specifying the API's Id and a stage name of the specified API. You add plan customers by adding API keys to the plan. 

               `Create and Use Usage Plans`_  
            

            - **id** *(string) --* 

              The identifier of a  UsagePlan resource.

              
            

            - **name** *(string) --* 

              The name of a usage plan.

              
            

            - **description** *(string) --* 

              The description of a usage plan.

              
            

            - **apiStages** *(list) --* 

              The associated API stages of a usage plan.

              
              

              - *(dict) --* 

                API stage name of the associated API stage in a usage plan.

                
                

                - **apiId** *(string) --* 

                  API Id of the associated API stage in a usage plan.

                  
                

                - **stage** *(string) --* 

                  API stage name of the associated API stage in a usage plan.

                  
            
          
            

            - **throttle** *(dict) --* 

              The request throttle limits of a usage plan.

              
              

              - **burstLimit** *(integer) --* 

                The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

                
              

              - **rateLimit** *(float) --* 

                The API request steady-state rate limit.

                
          
            

            - **quota** *(dict) --* 

              The maximum number of permitted requests per a given unit time interval.

              
              

              - **limit** *(integer) --* 

                The maximum number of requests that can be made in a given time period.

                
              

              - **offset** *(integer) --* 

                The number of requests subtracted from the given limit in the initial time period.

                
              

              - **period** *(string) --* 

                The time period in which the limit applies. Valid values are "DAY", "WEEK" or "MONTH".

                
          
        
      
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: import_api_keys(**kwargs)

    

    Import API keys from an external source, such as a CSV-formatted file.

    

    **Request Syntax** 
    ::

      response = client.import_api_keys(
          body=b'bytes'|file,
          format='csv',
          failOnWarnings=True|False
      )
    :type body: bytes or seekable file-like object
    :param body: **[REQUIRED]** 

      The payload of the POST request to import API keys. For the payload format, see `API Key File Format`_ .

      

    
    :type format: string
    :param format: **[REQUIRED]** 

      A query parameter to specify the input format to imported API keys. Currently, only the ``csv`` format is supported.

      

    
    :type failOnWarnings: boolean
    :param failOnWarnings: 

      A query parameter to indicate whether to rollback  ApiKey importation (``true`` ) or not (``false`` ) when error is encountered.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'ids': [
                'string',
            ],
            'warnings': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        The identifier of an API key used to reference an API key in a usage plan.

        
        

        - **ids** *(list) --* 

          A list of all the  ApiKey identifiers.

          
          

          - *(string) --* 
      
        

        - **warnings** *(list) --* 

          A list of warning messages.

          
          

          - *(string) --* 
      
    

  .. py:method:: import_rest_api(**kwargs)

    

    A feature of the Amazon API Gateway control service for creating a new API from an external API definition file.

    

    **Request Syntax** 
    ::

      response = client.import_rest_api(
          failOnWarnings=True|False,
          parameters={
              'string': 'string'
          },
          body=b'bytes'|file
      )
    :type failOnWarnings: boolean
    :param failOnWarnings: 

      A query parameter to indicate whether to rollback the API creation (``true`` ) or not (``false`` ) when a warning is encountered. The default value is ``false`` .

      

    
    :type parameters: dict
    :param parameters: 

      Custom header parameters as part of the request.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type body: bytes or seekable file-like object
    :param body: **[REQUIRED]** 

      The POST request body containing external API definitions. Currently, only Swagger definition JSON files are supported.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'createdDate': datetime(2015, 1, 1),
            'warnings': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a REST API.

          `Create an API`_  
        

        - **id** *(string) --* 

          The API's identifier. This identifier is unique across all of your APIs in Amazon API Gateway.

          
        

        - **name** *(string) --* 

          The API's name.

          
        

        - **description** *(string) --* 

          The API's description.

          
        

        - **createdDate** *(datetime) --* 

          The date when the API was created, in `ISO 8601 format`_ .

          
        

        - **warnings** *(list) --* 

          The warning messages reported when ``failonwarnings`` is turned on during API import.

          
          

          - *(string) --* 
      
    

  .. py:method:: put_integration(**kwargs)

    

    Represents a put integration.

    

    **Request Syntax** 
    ::

      response = client.put_integration(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          type='HTTP'|'AWS'|'MOCK',
          integrationHttpMethod='string',
          uri='string',
          credentials='string',
          requestParameters={
              'string': 'string'
          },
          requestTemplates={
              'string': 'string'
          },
          passthroughBehavior='string',
          cacheNamespace='string',
          cacheKeyParameters=[
              'string',
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Specifies a put integration request's API identifier.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      Specifies a put integration request's resource ID.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies a put integration request's HTTP method.

      

    
    :type type: string
    :param type: **[REQUIRED]** 

      Specifies a put integration input's type.

      

    
    :type integrationHttpMethod: string
    :param integrationHttpMethod: 

      Specifies a put integration HTTP method. When the integration type is HTTP or AWS, this field is required.

      

    
    :type uri: string
    :param uri: 

      Specifies a put integration input's Uniform Resource Identifier (URI). When the integration type is HTTP or AWS, this field is required. For integration with Lambda as an AWS service proxy, this value is of the 'arn:aws:apigateway:region:lambda:path/2015-03-31/functions/functionArn/invocations' format.

      

    
    :type credentials: string
    :param credentials: 

      Specifies whether credentials are required for a put integration.

      

    
    :type requestParameters: dict
    :param requestParameters: 

      A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type requestTemplates: dict
    :param requestTemplates: 

      Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type passthroughBehavior: string
    :param passthroughBehavior: 

      Specifies the pass-through behavior for incoming requests based on the Content-Type header in the request, and the available mapping templates specified as the ``requestTemplates`` property on the Integration resource. There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

       

       
      * ``WHEN_NO_MATCH`` passes the request body for unmapped content types through to the integration back end without transformation.
       
      * ``NEVER`` rejects unmapped content types with an HTTP 415 'Unsupported Media Type' response.
       
      * ``WHEN_NO_TEMPLATES`` allows pass-through when the integration has NO content types mapped to templates. However if there is at least one content type defined, unmapped content types will be rejected with the same 415 response.
       

      

    
    :type cacheNamespace: string
    :param cacheNamespace: 

      Specifies a put integration input's cache namespace.

      

    
    :type cacheKeyParameters: list
    :param cacheKeyParameters: 

      Specifies a put integration input's cache key parameters.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'type': 'HTTP'|'AWS'|'MOCK',
            'httpMethod': 'string',
            'uri': 'string',
            'credentials': 'string',
            'requestParameters': {
                'string': 'string'
            },
            'requestTemplates': {
                'string': 'string'
            },
            'passthroughBehavior': 'string',
            'cacheNamespace': 'string',
            'cacheKeyParameters': [
                'string',
            ],
            'integrationResponses': {
                'string': {
                    'statusCode': 'string',
                    'selectionPattern': 'string',
                    'responseParameters': {
                        'string': 'string'
                    },
                    'responseTemplates': {
                        'string': 'string'
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an HTTP, AWS, or Mock integration.

         In the API Gateway console, the built-in Lambda integration is an AWS integration.  `Creating an API`_  
        

        - **type** *(string) --* 

          Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

          
        

        - **httpMethod** *(string) --* 

          Specifies the integration's HTTP method type.

          
        

        - **uri** *(string) --* 

          Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

          
        

        - **credentials** *(string) --* 

          Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

          
        

        - **requestParameters** *(dict) --* 

          A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **requestTemplates** *(dict) --* 

          Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **passthroughBehavior** *(string) --*  

          Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

           

           
          * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
           
          * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
           
          * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
           

           
        

        - **cacheNamespace** *(string) --* 

          Specifies the integration's cache namespace.

          
        

        - **cacheKeyParameters** *(list) --* 

          Specifies the integration's cache key parameters.

          
          

          - *(string) --* 
      
        

        - **integrationResponses** *(dict) --* 

          Specifies the integration's responses.

            

          

           Example: Get integration responses of a method Request 

          

           ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

          The successful response returns ``200 OK`` status and a payload as follows:

           ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

          

             `Creating an API`_  
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                `Creating an API`_  
              

              - **statusCode** *(string) --* 

                Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                
              

              - **selectionPattern** *(string) --* 

                Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                
              

              - **responseParameters** *(dict) --* 

                A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **responseTemplates** *(dict) --* 

                Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
      
    
    

  .. py:method:: put_integration_response(**kwargs)

    

    Represents a put integration.

    

    **Request Syntax** 
    ::

      response = client.put_integration_response(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          statusCode='string',
          selectionPattern='string',
          responseParameters={
              'string': 'string'
          },
          responseTemplates={
              'string': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Specifies a put integration response request's API identifier.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      Specifies a put integration response request's resource identifier.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies a put integration response request's HTTP method.

      

    
    :type statusCode: string
    :param statusCode: **[REQUIRED]** 

      Specifies the status code that is used to map the integration response to an existing  MethodResponse .

      

    
    :type selectionPattern: string
    :param selectionPattern: 

      Specifies the selection pattern of a put integration response.

      

    
    :type responseParameters: dict
    :param responseParameters: 

      A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` must be a valid and unique response header name and ``JSON-expression`` a valid JSON expression without the ``$`` prefix.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type responseTemplates: dict
    :param responseTemplates: 

      Specifies a put integration response's templates.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'statusCode': 'string',
            'selectionPattern': 'string',
            'responseParameters': {
                'string': 'string'
            },
            'responseTemplates': {
                'string': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

          `Creating an API`_  
        

        - **statusCode** *(string) --* 

          Specifies the status code that is used to map the integration response to an existing  MethodResponse .

          
        

        - **selectionPattern** *(string) --* 

          Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

          
        

        - **responseParameters** *(dict) --* 

          A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **responseTemplates** *(dict) --* 

          Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
    

  .. py:method:: put_method(**kwargs)

    

    Add a method to an existing  Resource resource.

    

    **Request Syntax** 
    ::

      response = client.put_method(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          authorizationType='string',
          authorizerId='string',
          apiKeyRequired=True|False,
          requestParameters={
              'string': True|False
          },
          requestModels={
              'string': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the new  Method resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The  Resource identifier for the new  Method resource.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies the method request's HTTP method type.

      

    
    :type authorizationType: string
    :param authorizationType: **[REQUIRED]** 

      Specifies the type of authorization used for the method.

      

    
    :type authorizerId: string
    :param authorizerId: 

      Specifies the identifier of an  Authorizer to use on this Method, if the type is CUSTOM.

      

    
    :type apiKeyRequired: boolean
    :param apiKeyRequired: 

      Specifies whether the method required a valid  ApiKey .

      

    
    :type requestParameters: dict
    :param requestParameters: 

      A key-value map defining required or optional method request parameters that can be accepted by Amazon API Gateway. A key defines a method request parameter name matching the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` is a valid and unique parameter name. The value associated with the key is a Boolean flag indicating whether the parameter is required (``true`` ) or optional (``false`` ). The method request parameter names defined here are available in  Integration to be mapped to integration request parameters or body-mapping templates.

      

    
      - *(string) --* 

      
        - *(boolean) --* 

        
  

    :type requestModels: dict
    :param requestModels: 

      Specifies the  Model resources used for the request's content type. Request models are represented as a key/value map, with a content type as the key and a  Model name as the value.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'httpMethod': 'string',
            'authorizationType': 'string',
            'authorizerId': 'string',
            'apiKeyRequired': True|False,
            'requestParameters': {
                'string': True|False
            },
            'requestModels': {
                'string': 'string'
            },
            'methodResponses': {
                'string': {
                    'statusCode': 'string',
                    'responseParameters': {
                        'string': True|False
                    },
                    'responseModels': {
                        'string': 'string'
                    }
                }
            },
            'methodIntegration': {
                'type': 'HTTP'|'AWS'|'MOCK',
                'httpMethod': 'string',
                'uri': 'string',
                'credentials': 'string',
                'requestParameters': {
                    'string': 'string'
                },
                'requestTemplates': {
                    'string': 'string'
                },
                'passthroughBehavior': 'string',
                'cacheNamespace': 'string',
                'cacheKeyParameters': [
                    'string',
                ],
                'integrationResponses': {
                    'string': {
                        'statusCode': 'string',
                        'selectionPattern': 'string',
                        'responseParameters': {
                            'string': 'string'
                        },
                        'responseTemplates': {
                            'string': 'string'
                        }
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a client-facing interface by which the client calls the API to access back-end resources. A **Method** resource is integrated with an  Integration resource. Both consist of a request and one or more responses. The method request takes the client input that is passed to the back end through the integration request. A method response returns the output from the back end to the client through an integration response. A method request is embodied in a **Method** resource, whereas an integration request is embodied in an  Integration resource. On the other hand, a method response is represented by a  MethodResponse resource, whereas an integration response is represented by an  IntegrationResponse resource. 

          

        

         Example: Retrive the GET method on a specified resource Request 

        The following example request retrieves the information about the GET method on an API resource (``3kzxbg5sa2`` ) of an API (``fugvjdxtri`` ). 

         ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T210259Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

        The successful response returns a ``200 OK`` status code and a payload similar to the following:

         ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": true, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E\")" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

        In the example above, the response template for the ``200 OK`` response maps the JSON output from the ``ListStreams`` action in the back end to an XML output. The mapping template is URL-encoded as ``%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E`` and the output is decoded using the `$util.urlDecode()`_ helper function.

            MethodResponse ,  Integration ,  IntegrationResponse ,  Resource , `Set up an API's method`_  
        

        - **httpMethod** *(string) --* 

          The method's HTTP verb.

          
        

        - **authorizationType** *(string) --* 

          The method's authorization type.

          
        

        - **authorizerId** *(string) --* 

          The identifier of an  Authorizer to use on this method. The ``authorizationType`` must be ``CUSTOM`` .

          
        

        - **apiKeyRequired** *(boolean) --* 

          A boolean flag specifying whether a valid  ApiKey is required to invoke this method.

          
        

        - **requestParameters** *(dict) --* 

          A key-value map defining required or optional method request parameters that can be accepted by Amazon API Gateway. A key is a method request parameter name matching the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` is a valid and unique parameter name. The value associated with the key is a Boolean flag indicating whether the parameter is required (``true`` ) or optional (``false`` ). The method request parameter names defined here are available in  Integration to be mapped to integration request parameters or templates.

          
          

          - *(string) --* 
            

            - *(boolean) --* 
      
    
        

        - **requestModels** *(dict) --* 

          A key-value map specifying data schemas, represented by  Model resources, (as the mapped value) of the request payloads of given content types (as the mapping key).

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **methodResponses** *(dict) --* 

          Gets a method response associated with a given HTTP status code. 

            

          The collection of method responses are encapsulated in a key-value map, where the key is a response's HTTP status code and the value is a  MethodResponse resource that specifies the response returned to the caller from the back end through the integration response.

           Example: Get a 200 OK response of a GET method Request 

          

           ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T215008Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

          The successful response returns a ``200 OK`` status code and a payload similar to the following:

           ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.operator": false, "method.response.header.operand_2": false, "method.response.header.operand_1": false }, "statusCode": "200" }``  

          

             `AWS CLI`_  
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

                

              

               Example: A **MethodResponse** instance of an API Request 

              The example request retrieves a **MethodResponse** of the 200 status code.

               ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

              The successful response returns ``200 OK`` status and a payload as follows:

               ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

              

                  Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
              

              - **statusCode** *(string) --* 

                The method response's status code.

                
              

              - **responseParameters** *(dict) --* 

                A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

                
                

                - *(string) --* 
                  

                  - *(boolean) --* 
            
          
              

              - **responseModels** *(dict) --* 

                Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
      
    
        

        - **methodIntegration** *(dict) --* 

          Gets the method's integration responsible for passing the client-submitted request to the back end and performing necessary transformations to make the request compliant with the back end.

            

          

           Example:  Request 

          

           ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T213210Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

          The successful response returns a ``200 OK`` status code and a payload similar to the following:

           ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true } ], "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:responses": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "0cjtch", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestTemplates": { "application/json": "{\n \"a\": \"$input.params('operand1')\",\n \"b\": \"$input.params('operand2')\", \n \"op\": \"$input.params('operator')\" \n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-west-2:lambda:path//2015-03-31/functions/arn:aws:lambda:us-west-2:123456789012:function:Calc/invocations", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.operator": "integration.response.body.op", "method.response.header.operand_2": "integration.response.body.b", "method.response.header.operand_1": "integration.response.body.a" }, "responseTemplates": { "application/json": "#set($res = $input.path('$'))\n{\n \"result\": \"$res.a, $res.b, $res.op => $res.c\",\n \"a\" : \"$res.a\",\n \"b\" : \"$res.b\",\n \"op\" : \"$res.op\",\n \"c\" : \"$res.c\"\n}" }, "selectionPattern": "", "statusCode": "200" } } }``  

          

             `AWS CLI`_  
          

          - **type** *(string) --* 

            Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

            
          

          - **httpMethod** *(string) --* 

            Specifies the integration's HTTP method type.

            
          

          - **uri** *(string) --* 

            Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

            
          

          - **credentials** *(string) --* 

            Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

            
          

          - **requestParameters** *(dict) --* 

            A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

            
            

            - *(string) --* 
              

              - *(string) --* 
        
      
          

          - **requestTemplates** *(dict) --* 

            Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

            
            

            - *(string) --* 
              

              - *(string) --* 
        
      
          

          - **passthroughBehavior** *(string) --*  

            Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

             

             
            * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
             
            * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
             
            * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
             

             
          

          - **cacheNamespace** *(string) --* 

            Specifies the integration's cache namespace.

            
          

          - **cacheKeyParameters** *(list) --* 

            Specifies the integration's cache key parameters.

            
            

            - *(string) --* 
        
          

          - **integrationResponses** *(dict) --* 

            Specifies the integration's responses.

              

            

             Example: Get integration responses of a method Request 

            

             ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

            The successful response returns ``200 OK`` status and a payload as follows:

             ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

            

               `Creating an API`_  
            

            - *(string) --* 
              

              - *(dict) --* 

                Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                  `Creating an API`_  
                

                - **statusCode** *(string) --* 

                  Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                  
                

                - **selectionPattern** *(string) --* 

                  Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                  
                

                - **responseParameters** *(dict) --* 

                  A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
                

                - **responseTemplates** *(dict) --* 

                  Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
        
      
      
    

  .. py:method:: put_method_response(**kwargs)

    

    Adds a  MethodResponse to an existing  Method resource.

    

    **Request Syntax** 
    ::

      response = client.put_method_response(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          statusCode='string',
          responseParameters={
              'string': True|False
          },
          responseModels={
              'string': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Method resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The  Resource identifier for the  Method resource.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      The HTTP verb of the  Method resource.

      

    
    :type statusCode: string
    :param statusCode: **[REQUIRED]** 

      The method response's status code.

      

    
    :type responseParameters: dict
    :param responseParameters: 

      A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header name and the associated value is a Boolean flag indicating whether the method response parameter is required or not. The method response header names must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The response parameter names defined here are available in the integration response to be mapped from an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

      

    
      - *(string) --* 

      
        - *(boolean) --* 

        
  

    :type responseModels: dict
    :param responseModels: 

      Specifies the  Model resources used for the response's content type. Response models are represented as a key/value map, with a content type as the key and a  Model name as the value.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'statusCode': 'string',
            'responseParameters': {
                'string': True|False
            },
            'responseModels': {
                'string': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

          

        

         Example: A **MethodResponse** instance of an API Request 

        The example request retrieves a **MethodResponse** of the 200 status code.

         ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

        The successful response returns ``200 OK`` status and a payload as follows:

         ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

        

            Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
        

        - **statusCode** *(string) --* 

          The method response's status code.

          
        

        - **responseParameters** *(dict) --* 

          A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

          
          

          - *(string) --* 
            

            - *(boolean) --* 
      
    
        

        - **responseModels** *(dict) --* 

          Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
    

  .. py:method:: put_rest_api(**kwargs)

    

    A feature of the Amazon API Gateway control service for updating an existing API with an input of external API definitions. The update can take the form of merging the supplied definition into the existing API or overwriting the existing API.

    

    **Request Syntax** 
    ::

      response = client.put_rest_api(
          restApiId='string',
          mode='merge'|'overwrite',
          failOnWarnings=True|False,
          parameters={
              'string': 'string'
          },
          body=b'bytes'|file
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi to be updated. 

      

    
    :type mode: string
    :param mode: 

      The ``mode`` query parameter to specify the update mode. Valid values are "merge" and "overwrite". By default, the update mode is "merge".

      

    
    :type failOnWarnings: boolean
    :param failOnWarnings: 

      A query parameter to indicate whether to rollback the API update (``true`` ) or not (``false`` ) when a warning is encountered. The default value is ``false`` .

      

    
    :type parameters: dict
    :param parameters: 

      Custom headers supplied as part of the request. 

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type body: bytes or seekable file-like object
    :param body: **[REQUIRED]** 

      The PUT request body containing external API definitions. Currently, only Swagger definition JSON files are supported.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'createdDate': datetime(2015, 1, 1),
            'warnings': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a REST API.

          `Create an API`_  
        

        - **id** *(string) --* 

          The API's identifier. This identifier is unique across all of your APIs in Amazon API Gateway.

          
        

        - **name** *(string) --* 

          The API's name.

          
        

        - **description** *(string) --* 

          The API's description.

          
        

        - **createdDate** *(datetime) --* 

          The date when the API was created, in `ISO 8601 format`_ .

          
        

        - **warnings** *(list) --* 

          The warning messages reported when ``failonwarnings`` is turned on during API import.

          
          

          - *(string) --* 
      
    

  .. py:method:: test_invoke_authorizer(**kwargs)

    

    Simulate the execution of an  Authorizer in your  RestApi with headers, parameters, and an incoming request body.

      `Enable custom authorizers`_  

    **Request Syntax** 
    ::

      response = client.test_invoke_authorizer(
          restApiId='string',
          authorizerId='string',
          headers={
              'string': 'string'
          },
          pathWithQueryString='string',
          body='string',
          stageVariables={
              'string': 'string'
          },
          additionalContext={
              'string': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Specifies a test invoke authorizer request's  RestApi identifier.

      

    
    :type authorizerId: string
    :param authorizerId: **[REQUIRED]** 

      Specifies a test invoke authorizer request's  Authorizer ID.

      

    
    :type headers: dict
    :param headers: 

      [Required] A key-value map of headers to simulate an incoming invocation request. This is where the incoming authorization token, or identity source, should be specified.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type pathWithQueryString: string
    :param pathWithQueryString: 

      [Optional] The URI path, including query string, of the simulated invocation request. Use this to specify path parameters and query string parameters.

      

    
    :type body: string
    :param body: 

      [Optional] The simulated request body of an incoming invocation request.

      

    
    :type stageVariables: dict
    :param stageVariables: 

      A key-value map of stage variables to simulate an invocation on a deployed  Stage .

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type additionalContext: dict
    :param additionalContext: 

      [Optional] A key-value map of additional context variables.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'clientStatus': 123,
            'log': 'string',
            'latency': 123,
            'principalId': 'string',
            'policy': 'string',
            'authorization': {
                'string': [
                    'string',
                ]
            },
            'claims': {
                'string': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response of the test invoke request for a custom  Authorizer 

        
        

        - **clientStatus** *(integer) --* 

          The HTTP status code that the client would have received. Value is 0 if the authorizer succeeded.

          
        

        - **log** *(string) --* 

          The Amazon API Gateway execution log for the test authorizer request.

          
        

        - **latency** *(integer) --* 

          The execution latency of the test authorizer request.

          
        

        - **principalId** *(string) --* 

          The principal identity returned by the  Authorizer 

          
        

        - **policy** *(string) --* 

          The JSON policy document returned by the  Authorizer 

          
        

        - **authorization** *(dict) --* 
          

          - *(string) --* 
            

            - *(list) --* 
              

              - *(string) --* 
          
      
    
        

        - **claims** *(dict) --* 

          The `open identity claims`_ , with any supported custom attributes, returned from the Cognito Your User Pool configured for the API.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
    

  .. py:method:: test_invoke_method(**kwargs)

    

    Simulate the execution of a  Method in your  RestApi with headers, parameters, and an incoming request body.

    

    **Request Syntax** 
    ::

      response = client.test_invoke_method(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          pathWithQueryString='string',
          body='string',
          headers={
              'string': 'string'
          },
          clientCertificateId='string',
          stageVariables={
              'string': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Specifies a test invoke method request's API identifier.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      Specifies a test invoke method request's resource ID.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies a test invoke method request's HTTP method.

      

    
    :type pathWithQueryString: string
    :param pathWithQueryString: 

      The URI path, including query string, of the simulated invocation request. Use this to specify path parameters and query string parameters.

      

    
    :type body: string
    :param body: 

      The simulated request body of an incoming invocation request.

      

    
    :type headers: dict
    :param headers: 

      A key-value map of headers to simulate an incoming invocation request.

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    :type clientCertificateId: string
    :param clientCertificateId: 

      A  ClientCertificate identifier to use in the test invocation. API Gateway will use the certificate when making the HTTPS request to the defined back-end endpoint.

      

    
    :type stageVariables: dict
    :param stageVariables: 

      A key-value map of stage variables to simulate an invocation on a deployed  Stage .

      

    
      - *(string) --* 

      
        - *(string) --* 

        
  

    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'status': 123,
            'body': 'string',
            'headers': {
                'string': 'string'
            },
            'log': 'string',
            'latency': 123
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the response of the test invoke request in the HTTP method.

          `Test API using the API Gateway console`_  
        

        - **status** *(integer) --* 

          The HTTP status code.

          
        

        - **body** *(string) --* 

          The body of the HTTP response.

          
        

        - **headers** *(dict) --* 

          The headers of the HTTP response.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **log** *(string) --* 

          The Amazon API Gateway execution log for the test invoke request.

          
        

        - **latency** *(integer) --* 

          The execution latency of the test invoke request.

          
    

  .. py:method:: update_account(**kwargs)

    

    Changes information about the current  Account resource.

    

    **Request Syntax** 
    ::

      response = client.update_account(
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'cloudwatchRoleArn': 'string',
            'throttleSettings': {
                'burstLimit': 123,
                'rateLimit': 123.0
            },
            'features': [
                'string',
            ],
            'apiKeyVersion': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an AWS account that is associated with Amazon API Gateway.

          

        To view the account info, call ``GET`` on this resource.

         Error Codes 

        The following exception may be thrown when the request fails.

         

         
        * UnauthorizedException
         
        * NotFoundException
         
        * TooManyRequestsException
         

         

        For detailed error code information, including the corresponding HTTP Status Codes, see `API Gateway Error Codes`_ 

         Example: Get the information about an account. Request ``GET /account HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160531T184618Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

        The successful response returns a ``200 OK`` status code and a payload similar to the following:

         ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/account-apigateway-{rel}.html", "name": "account", "templated": true }, "self": { "href": "/account" }, "account:update": { "href": "/account" } }, "cloudwatchRoleArn": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "throttleSettings": { "rateLimit": 500, "burstLimit": 1000 } }``  

        In addition to making the REST API call directly, you can use the AWS CLI and an AWS SDK to access this resource.

           `API Gateway Limits`_  `Developer Guide`_ , `AWS CLI`_  
        

        - **cloudwatchRoleArn** *(string) --* 

          The ARN of an Amazon CloudWatch role for the current  Account . 

          
        

        - **throttleSettings** *(dict) --* 

          Specifies the API request limits configured for the current  Account .

          
          

          - **burstLimit** *(integer) --* 

            The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

            
          

          - **rateLimit** *(float) --* 

            The API request steady-state rate limit.

            
      
        

        - **features** *(list) --* 

          A list of features supported for the account. When usage plans are enabled, the features list will include an entry of ``"UsagePlans"`` .

          
          

          - *(string) --* 
      
        

        - **apiKeyVersion** *(string) --* 

          The version of the API keys used for the account.

          
    

  .. py:method:: update_api_key(**kwargs)

    

    Changes information about an  ApiKey resource.

    

    **Request Syntax** 
    ::

      response = client.update_api_key(
          apiKey='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type apiKey: string
    :param apiKey: **[REQUIRED]** 

      The identifier of the  ApiKey resource to be updated.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'value': 'string',
            'name': 'string',
            'description': 'string',
            'enabled': True|False,
            'createdDate': datetime(2015, 1, 1),
            'lastUpdatedDate': datetime(2015, 1, 1),
            'stageKeys': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        A resource that can be distributed to callers for executing  Method resources that require an API key. API keys can be mapped to any  Stage on any  RestApi , which indicates that the callers with the API key can make requests to that stage.

          `Use API Keys`_  
        

        - **id** *(string) --* 

          The identifier of the API Key.

          
        

        - **value** *(string) --* 

          The value of the API Key.

          
        

        - **name** *(string) --* 

          The name of the API Key.

          
        

        - **description** *(string) --* 

          The description of the API Key.

          
        

        - **enabled** *(boolean) --* 

          Specifies whether the API Key can be used by callers.

          
        

        - **createdDate** *(datetime) --* 

          The date when the API Key was created, in `ISO 8601 format`_ .

          
        

        - **lastUpdatedDate** *(datetime) --* 

          When the API Key was last updated, in ISO 8601 format.

          
        

        - **stageKeys** *(list) --* 

          A list of  Stage resources that are associated with the  ApiKey resource.

          
          

          - *(string) --* 
      
    

  .. py:method:: update_authorizer(**kwargs)

    

    Updates an existing  Authorizer resource.

     `AWS CLI`_ 

    **Request Syntax** 
    ::

      response = client.update_authorizer(
          restApiId='string',
          authorizerId='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Authorizer resource.

      

    
    :type authorizerId: string
    :param authorizerId: **[REQUIRED]** 

      The identifier of the  Authorizer resource.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'type': 'TOKEN'|'COGNITO_USER_POOLS',
            'providerARNs': [
                'string',
            ],
            'authType': 'string',
            'authorizerUri': 'string',
            'authorizerCredentials': 'string',
            'identitySource': 'string',
            'identityValidationExpression': 'string',
            'authorizerResultTtlInSeconds': 123
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an authorization layer for methods. If enabled on a method, API Gateway will activate the authorizer when a client calls the method.

          `Enable custom authorization`_  
        

        - **id** *(string) --* 

          The identifier for the authorizer resource.

          
        

        - **name** *(string) --* 

          [Required] The name of the authorizer.

          
        

        - **type** *(string) --* 

          [Required] The type of the authorizer. Currently, the only valid type is TOKEN.

          
        

        - **providerARNs** *(list) --* 

          A list of the provider ARNs of the authorizer.

          
          

          - *(string) --* 
      
        

        - **authType** *(string) --* 

          Optional customer-defined field, used in Swagger imports/exports. Has no functional impact.

          
        

        - **authorizerUri** *(string) --* 

          [Required] Specifies the authorizer's Uniform Resource Identifier (URI). For TOKEN authorizers, this must be a well-formed Lambda function URI. The URI should be of the form ``arn:aws:apigateway:{region}:lambda:path/{service_api}`` . ``Region`` is used to determine the right endpoint. In this case, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` . For Lambda functions, this is usually of the form /2015-03-31/functions/[FunctionARN]/invocations

          
        

        - **authorizerCredentials** *(string) --* 

          Specifies the credentials required for the authorizer, if any. Two options are available. To specify an IAM role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To use resource-based permissions on the Lambda function, specify null.

          
        

        - **identitySource** *(string) --* 

          [Required] The source of the identity in an incoming request. For TOKEN authorizers, this value is a mapping expression with the same syntax as integration parameter mappings. The only valid source for tokens is 'header', so the expression should match 'method.request.header.[headerName]'. The value of the header '[headerName]' will be interpreted as the incoming token.

          
        

        - **identityValidationExpression** *(string) --* 

          A validation expression for the incoming identity. For TOKEN authorizers, this value should be a regular expression. The incoming token from the client is matched against this expression, and will proceed if the token matches. If the token doesn't match, the client receives a 401 Unauthorized response.

          
        

        - **authorizerResultTtlInSeconds** *(integer) --* 

          The TTL in seconds of cached authorizer results. If greater than 0, API Gateway will cache authorizer responses. If this field is not set, the default value is 300. The maximum value is 3600, or 1 hour.

          
    

  .. py:method:: update_base_path_mapping(**kwargs)

    

    Changes information about the  BasePathMapping resource.

    

    **Request Syntax** 
    ::

      response = client.update_base_path_mapping(
          domainName='string',
          basePath='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The domain name of the  BasePathMapping resource to change.

      

    
    :type basePath: string
    :param basePath: **[REQUIRED]** 

      The base path of the  BasePathMapping resource to change.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'basePath': 'string',
            'restApiId': 'string',
            'stage': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the base path that callers of the API must provide as part of the URL after the domain name.

         A custom domain name plus a ``BasePathMapping`` specification identifies a deployed  RestApi in a given stage of the owner  Account .  `Use Custom Domain Names`_  
        

        - **basePath** *(string) --* 

          The base path name that callers of the API must provide as part of the URL after the domain name.

          
        

        - **restApiId** *(string) --* 

          The name of the API.

          
        

        - **stage** *(string) --* 

          The name of the API's stage.

          
    

  .. py:method:: update_client_certificate(**kwargs)

    

    Changes information about an  ClientCertificate resource.

    

    **Request Syntax** 
    ::

      response = client.update_client_certificate(
          clientCertificateId='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type clientCertificateId: string
    :param clientCertificateId: **[REQUIRED]** 

      The identifier of the  ClientCertificate resource to be updated.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'clientCertificateId': 'string',
            'description': 'string',
            'pemEncodedCertificate': 'string',
            'createdDate': datetime(2015, 1, 1),
            'expirationDate': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a client certificate used to configure client-side SSL authentication while sending requests to the integration endpoint.

         Client certificates are used authenticate an API by the back-end server. To authenticate an API client (or user), use a custom  Authorizer .  `Use Client-Side Certificate`_  
        

        - **clientCertificateId** *(string) --* 

          The identifier of the client certificate.

          
        

        - **description** *(string) --* 

          The description of the client certificate.

          
        

        - **pemEncodedCertificate** *(string) --* 

          The PEM-encoded public key of the client certificate, which can be used to configure certificate authentication in the integration endpoint .

          
        

        - **createdDate** *(datetime) --* 

          The date when the client certificate was created, in `ISO 8601 format`_ .

          
        

        - **expirationDate** *(datetime) --* 

          The date when the client certificate will expire, in `ISO 8601 format`_ .

          
    

  .. py:method:: update_deployment(**kwargs)

    

    Changes information about a  Deployment resource.

    

    **Request Syntax** 
    ::

      response = client.update_deployment(
          restApiId='string',
          deploymentId='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The replacement identifier of the  RestApi resource for the  Deployment resource to change information about.

      

    
    :type deploymentId: string
    :param deploymentId: **[REQUIRED]** 

      The replacement identifier for the  Deployment resource to change information about.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'description': 'string',
            'createdDate': datetime(2015, 1, 1),
            'apiSummary': {
                'string': {
                    'string': {
                        'authorizationType': 'string',
                        'apiKeyRequired': True|False
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        An immutable representation of a  RestApi resource that can be called by users using  Stages . A deployment must be associated with a  Stage for it to be callable over the Internet.

         To create a deployment, call ``POST`` on the  Deployments resource of a  RestApi . To view, update, or delete a deployment, call ``GET`` , ``PATCH`` , or ``DELETE`` on the specified deployment resource (``/restapis/{restapi_id}/deployments/{deployment_id}`` ).  RestApi ,  Deployments ,  Stage , `AWS CLI`_ , `AWS SDKs`_  
        

        - **id** *(string) --* 

          The identifier for the deployment resource.

          
        

        - **description** *(string) --* 

          The description for the deployment resource.

          
        

        - **createdDate** *(datetime) --* 

          The date and time that the deployment resource was created.

          
        

        - **apiSummary** *(dict) --* 

          A summary of the  RestApi at the date and time that the deployment resource was created.

          
          

          - *(string) --* 
            

            - *(dict) --* 
              

              - *(string) --* 
                

                - *(dict) --* 

                  Represents a summary of a  Method resource, given a particular date and time.

                  
                  

                  - **authorizationType** *(string) --* 

                    Specifies the type of authorization used for the method.

                    
                  

                  - **apiKeyRequired** *(boolean) --* 

                    Specifies whether the method requires a valid  ApiKey .

                    
              
          
        
      
    
    

  .. py:method:: update_domain_name(**kwargs)

    

    Changes information about the  DomainName resource.

    

    **Request Syntax** 
    ::

      response = client.update_domain_name(
          domainName='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The name of the  DomainName resource to be changed.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'domainName': 'string',
            'certificateName': 'string',
            'certificateUploadDate': datetime(2015, 1, 1),
            'distributionDomainName': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a domain name that is contained in a simpler, more intuitive URL that can be called.

          `Use Client-Side Certificate`_  
        

        - **domainName** *(string) --* 

          The name of the  DomainName resource.

          
        

        - **certificateName** *(string) --* 

          The name of the certificate.

          
        

        - **certificateUploadDate** *(datetime) --* 

          The date when the certificate was uploaded, in `ISO 8601 format`_ .

          
        

        - **distributionDomainName** *(string) --* 

          The domain name of the Amazon CloudFront distribution. For more information, see the `Amazon CloudFront documentation`_ .

          
    

  .. py:method:: update_integration(**kwargs)

    

    Represents an update integration.

    

    **Request Syntax** 
    ::

      response = client.update_integration(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Represents an update integration request's API identifier.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      Represents an update integration request's resource identifier.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Represents an update integration request's HTTP method.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'type': 'HTTP'|'AWS'|'MOCK',
            'httpMethod': 'string',
            'uri': 'string',
            'credentials': 'string',
            'requestParameters': {
                'string': 'string'
            },
            'requestTemplates': {
                'string': 'string'
            },
            'passthroughBehavior': 'string',
            'cacheNamespace': 'string',
            'cacheKeyParameters': [
                'string',
            ],
            'integrationResponses': {
                'string': {
                    'statusCode': 'string',
                    'selectionPattern': 'string',
                    'responseParameters': {
                        'string': 'string'
                    },
                    'responseTemplates': {
                        'string': 'string'
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an HTTP, AWS, or Mock integration.

         In the API Gateway console, the built-in Lambda integration is an AWS integration.  `Creating an API`_  
        

        - **type** *(string) --* 

          Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

          
        

        - **httpMethod** *(string) --* 

          Specifies the integration's HTTP method type.

          
        

        - **uri** *(string) --* 

          Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

          
        

        - **credentials** *(string) --* 

          Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

          
        

        - **requestParameters** *(dict) --* 

          A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **requestTemplates** *(dict) --* 

          Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **passthroughBehavior** *(string) --*  

          Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

           

           
          * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
           
          * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
           
          * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
           

           
        

        - **cacheNamespace** *(string) --* 

          Specifies the integration's cache namespace.

          
        

        - **cacheKeyParameters** *(list) --* 

          Specifies the integration's cache key parameters.

          
          

          - *(string) --* 
      
        

        - **integrationResponses** *(dict) --* 

          Specifies the integration's responses.

            

          

           Example: Get integration responses of a method Request 

          

           ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

          The successful response returns ``200 OK`` status and a payload as follows:

           ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

          

             `Creating an API`_  
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                `Creating an API`_  
              

              - **statusCode** *(string) --* 

                Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                
              

              - **selectionPattern** *(string) --* 

                Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                
              

              - **responseParameters** *(dict) --* 

                A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **responseTemplates** *(dict) --* 

                Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
      
    
    

  .. py:method:: update_integration_response(**kwargs)

    

    Represents an update integration response.

    

    **Request Syntax** 
    ::

      response = client.update_integration_response(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          statusCode='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      Specifies an update integration response request's API identifier.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      Specifies an update integration response request's resource identifier.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      Specifies an update integration response request's HTTP method.

      

    
    :type statusCode: string
    :param statusCode: **[REQUIRED]** 

      Specifies an update integration response request's status code.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'statusCode': 'string',
            'selectionPattern': 'string',
            'responseParameters': {
                'string': 'string'
            },
            'responseTemplates': {
                'string': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

          `Creating an API`_  
        

        - **statusCode** *(string) --* 

          Specifies the status code that is used to map the integration response to an existing  MethodResponse .

          
        

        - **selectionPattern** *(string) --* 

          Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

          
        

        - **responseParameters** *(dict) --* 

          A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **responseTemplates** *(dict) --* 

          Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
    

  .. py:method:: update_method(**kwargs)

    

    Updates an existing  Method resource.

    

    **Request Syntax** 
    ::

      response = client.update_method(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Method resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The  Resource identifier for the  Method resource.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      The HTTP verb of the  Method resource.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'httpMethod': 'string',
            'authorizationType': 'string',
            'authorizerId': 'string',
            'apiKeyRequired': True|False,
            'requestParameters': {
                'string': True|False
            },
            'requestModels': {
                'string': 'string'
            },
            'methodResponses': {
                'string': {
                    'statusCode': 'string',
                    'responseParameters': {
                        'string': True|False
                    },
                    'responseModels': {
                        'string': 'string'
                    }
                }
            },
            'methodIntegration': {
                'type': 'HTTP'|'AWS'|'MOCK',
                'httpMethod': 'string',
                'uri': 'string',
                'credentials': 'string',
                'requestParameters': {
                    'string': 'string'
                },
                'requestTemplates': {
                    'string': 'string'
                },
                'passthroughBehavior': 'string',
                'cacheNamespace': 'string',
                'cacheKeyParameters': [
                    'string',
                ],
                'integrationResponses': {
                    'string': {
                        'statusCode': 'string',
                        'selectionPattern': 'string',
                        'responseParameters': {
                            'string': 'string'
                        },
                        'responseTemplates': {
                            'string': 'string'
                        }
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a client-facing interface by which the client calls the API to access back-end resources. A **Method** resource is integrated with an  Integration resource. Both consist of a request and one or more responses. The method request takes the client input that is passed to the back end through the integration request. A method response returns the output from the back end to the client through an integration response. A method request is embodied in a **Method** resource, whereas an integration request is embodied in an  Integration resource. On the other hand, a method response is represented by a  MethodResponse resource, whereas an integration response is represented by an  IntegrationResponse resource. 

          

        

         Example: Retrive the GET method on a specified resource Request 

        The following example request retrieves the information about the GET method on an API resource (``3kzxbg5sa2`` ) of an API (``fugvjdxtri`` ). 

         ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T210259Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

        The successful response returns a ``200 OK`` status code and a payload similar to the following:

         ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": true, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E\")" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

        In the example above, the response template for the ``200 OK`` response maps the JSON output from the ``ListStreams`` action in the back end to an XML output. The mapping template is URL-encoded as ``%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E`` and the output is decoded using the `$util.urlDecode()`_ helper function.

            MethodResponse ,  Integration ,  IntegrationResponse ,  Resource , `Set up an API's method`_  
        

        - **httpMethod** *(string) --* 

          The method's HTTP verb.

          
        

        - **authorizationType** *(string) --* 

          The method's authorization type.

          
        

        - **authorizerId** *(string) --* 

          The identifier of an  Authorizer to use on this method. The ``authorizationType`` must be ``CUSTOM`` .

          
        

        - **apiKeyRequired** *(boolean) --* 

          A boolean flag specifying whether a valid  ApiKey is required to invoke this method.

          
        

        - **requestParameters** *(dict) --* 

          A key-value map defining required or optional method request parameters that can be accepted by Amazon API Gateway. A key is a method request parameter name matching the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` is a valid and unique parameter name. The value associated with the key is a Boolean flag indicating whether the parameter is required (``true`` ) or optional (``false`` ). The method request parameter names defined here are available in  Integration to be mapped to integration request parameters or templates.

          
          

          - *(string) --* 
            

            - *(boolean) --* 
      
    
        

        - **requestModels** *(dict) --* 

          A key-value map specifying data schemas, represented by  Model resources, (as the mapped value) of the request payloads of given content types (as the mapping key).

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **methodResponses** *(dict) --* 

          Gets a method response associated with a given HTTP status code. 

            

          The collection of method responses are encapsulated in a key-value map, where the key is a response's HTTP status code and the value is a  MethodResponse resource that specifies the response returned to the caller from the back end through the integration response.

           Example: Get a 200 OK response of a GET method Request 

          

           ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T215008Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

          The successful response returns a ``200 OK`` status code and a payload similar to the following:

           ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.operator": false, "method.response.header.operand_2": false, "method.response.header.operand_1": false }, "statusCode": "200" }``  

          

             `AWS CLI`_  
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

                

              

               Example: A **MethodResponse** instance of an API Request 

              The example request retrieves a **MethodResponse** of the 200 status code.

               ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

              The successful response returns ``200 OK`` status and a payload as follows:

               ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

              

                  Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
              

              - **statusCode** *(string) --* 

                The method response's status code.

                
              

              - **responseParameters** *(dict) --* 

                A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

                
                

                - *(string) --* 
                  

                  - *(boolean) --* 
            
          
              

              - **responseModels** *(dict) --* 

                Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
          
      
    
        

        - **methodIntegration** *(dict) --* 

          Gets the method's integration responsible for passing the client-submitted request to the back end and performing necessary transformations to make the request compliant with the back end.

            

          

           Example:  Request 

          

           ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T213210Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

          The successful response returns a ``200 OK`` status code and a payload similar to the following:

           ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true } ], "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:responses": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "0cjtch", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestTemplates": { "application/json": "{\n \"a\": \"$input.params('operand1')\",\n \"b\": \"$input.params('operand2')\", \n \"op\": \"$input.params('operator')\" \n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-west-2:lambda:path//2015-03-31/functions/arn:aws:lambda:us-west-2:123456789012:function:Calc/invocations", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.operator": "integration.response.body.op", "method.response.header.operand_2": "integration.response.body.b", "method.response.header.operand_1": "integration.response.body.a" }, "responseTemplates": { "application/json": "#set($res = $input.path('$'))\n{\n \"result\": \"$res.a, $res.b, $res.op => $res.c\",\n \"a\" : \"$res.a\",\n \"b\" : \"$res.b\",\n \"op\" : \"$res.op\",\n \"c\" : \"$res.c\"\n}" }, "selectionPattern": "", "statusCode": "200" } } }``  

          

             `AWS CLI`_  
          

          - **type** *(string) --* 

            Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

            
          

          - **httpMethod** *(string) --* 

            Specifies the integration's HTTP method type.

            
          

          - **uri** *(string) --* 

            Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

            
          

          - **credentials** *(string) --* 

            Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

            
          

          - **requestParameters** *(dict) --* 

            A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

            
            

            - *(string) --* 
              

              - *(string) --* 
        
      
          

          - **requestTemplates** *(dict) --* 

            Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

            
            

            - *(string) --* 
              

              - *(string) --* 
        
      
          

          - **passthroughBehavior** *(string) --*  

            Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

             

             
            * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
             
            * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
             
            * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
             

             
          

          - **cacheNamespace** *(string) --* 

            Specifies the integration's cache namespace.

            
          

          - **cacheKeyParameters** *(list) --* 

            Specifies the integration's cache key parameters.

            
            

            - *(string) --* 
        
          

          - **integrationResponses** *(dict) --* 

            Specifies the integration's responses.

              

            

             Example: Get integration responses of a method Request 

            

             ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

            The successful response returns ``200 OK`` status and a payload as follows:

             ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

            

               `Creating an API`_  
            

            - *(string) --* 
              

              - *(dict) --* 

                Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                  `Creating an API`_  
                

                - **statusCode** *(string) --* 

                  Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                  
                

                - **selectionPattern** *(string) --* 

                  Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                  
                

                - **responseParameters** *(dict) --* 

                  A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
                

                - **responseTemplates** *(dict) --* 

                  Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
        
      
      
    

  .. py:method:: update_method_response(**kwargs)

    

    Updates an existing  MethodResponse resource.

    

    **Request Syntax** 
    ::

      response = client.update_method_response(
          restApiId='string',
          resourceId='string',
          httpMethod='string',
          statusCode='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  MethodResponse resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The  Resource identifier for the  MethodResponse resource.

      

    
    :type httpMethod: string
    :param httpMethod: **[REQUIRED]** 

      The HTTP verb of the  Method resource.

      

    
    :type statusCode: string
    :param statusCode: **[REQUIRED]** 

      The status code for the  MethodResponse resource.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'statusCode': 'string',
            'responseParameters': {
                'string': True|False
            },
            'responseModels': {
                'string': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

          

        

         Example: A **MethodResponse** instance of an API Request 

        The example request retrieves a **MethodResponse** of the 200 status code.

         ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

        The successful response returns ``200 OK`` status and a payload as follows:

         ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

        

            Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
        

        - **statusCode** *(string) --* 

          The method response's status code.

          
        

        - **responseParameters** *(dict) --* 

          A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

          
          

          - *(string) --* 
            

            - *(boolean) --* 
      
    
        

        - **responseModels** *(dict) --* 

          Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
    

  .. py:method:: update_model(**kwargs)

    

    Changes information about a model.

    

    **Request Syntax** 
    ::

      response = client.update_model(
          restApiId='string',
          modelName='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier under which the model exists.

      

    
    :type modelName: string
    :param modelName: **[REQUIRED]** 

      The name of the model to update.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'schema': 'string',
            'contentType': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the data structure of a method's request or response payload.

          

        A request model defines the data structure of the client-supplied request payload. A response model defines the data structure of the response payload returned by the back end. Although not required, models are useful for mapping payloads between the front end and back end.

         

        A model is used for generating an API's SDK, validating the input request body, and creating a skeletal mapping template.

            Method ,  MethodResponse , `Models and Mappings`_  
        

        - **id** *(string) --* 

          The identifier for the model resource.

          
        

        - **name** *(string) --* 

          The name of the model.

          
        

        - **description** *(string) --* 

          The description of the model.

          
        

        - **schema** *(string) --* 

          The schema for the model. For ``application/json`` models, this should be `JSON-schema draft v4`_ model. Do not include "\*/" characters in the description of any properties because such "\*/" characters may be interpreted as the closing marker for comments in some languages, such as Java or JavaScript, causing the installation of your API's SDK generated by API Gateway to fail.

          
        

        - **contentType** *(string) --* 

          The content-type for the model.

          
    

  .. py:method:: update_resource(**kwargs)

    

    Changes information about a  Resource resource.

    

    **Request Syntax** 
    ::

      response = client.update_resource(
          restApiId='string',
          resourceId='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the  Resource resource.

      

    
    :type resourceId: string
    :param resourceId: **[REQUIRED]** 

      The identifier of the  Resource resource.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'parentId': 'string',
            'pathPart': 'string',
            'path': 'string',
            'resourceMethods': {
                'string': {
                    'httpMethod': 'string',
                    'authorizationType': 'string',
                    'authorizerId': 'string',
                    'apiKeyRequired': True|False,
                    'requestParameters': {
                        'string': True|False
                    },
                    'requestModels': {
                        'string': 'string'
                    },
                    'methodResponses': {
                        'string': {
                            'statusCode': 'string',
                            'responseParameters': {
                                'string': True|False
                            },
                            'responseModels': {
                                'string': 'string'
                            }
                        }
                    },
                    'methodIntegration': {
                        'type': 'HTTP'|'AWS'|'MOCK',
                        'httpMethod': 'string',
                        'uri': 'string',
                        'credentials': 'string',
                        'requestParameters': {
                            'string': 'string'
                        },
                        'requestTemplates': {
                            'string': 'string'
                        },
                        'passthroughBehavior': 'string',
                        'cacheNamespace': 'string',
                        'cacheKeyParameters': [
                            'string',
                        ],
                        'integrationResponses': {
                            'string': {
                                'statusCode': 'string',
                                'selectionPattern': 'string',
                                'responseParameters': {
                                    'string': 'string'
                                },
                                'responseTemplates': {
                                    'string': 'string'
                                }
                            }
                        }
                    }
                }
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents an API resource.

          `Create an API`_  
        

        - **id** *(string) --* 

          The resource's identifier.

          
        

        - **parentId** *(string) --* 

          The parent resource's identifier.

          
        

        - **pathPart** *(string) --* 

          The last path segment for this resource.

          
        

        - **path** *(string) --* 

          The full path for this resource.

          
        

        - **resourceMethods** *(dict) --* 

          Gets an API resource's method of a given HTTP verb.

            

          The resource methods are a map of methods indexed by methods' HTTP verbs enabled on the resource. This method map is included in the ``200 OK`` response of the ``GET /restapis/{restapi_id}/resources/{resource_id}`` or ``GET /restapis/{restapi_id}/resources/{resource_id}?embed=methods`` request.

           Example: Get the GET method of an API resource Request ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160608T031827Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160608/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": false, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

          If the ``OPTIONS`` is enabled on the resource, you can follow the example here to get that method. Just replace the ``GET`` of the last path segment in the request URL with ``OPTIONS`` .

             
          

          - *(string) --* 
            

            - *(dict) --* 

              Represents a client-facing interface by which the client calls the API to access back-end resources. A **Method** resource is integrated with an  Integration resource. Both consist of a request and one or more responses. The method request takes the client input that is passed to the back end through the integration request. A method response returns the output from the back end to the client through an integration response. A method request is embodied in a **Method** resource, whereas an integration request is embodied in an  Integration resource. On the other hand, a method response is represented by a  MethodResponse resource, whereas an integration response is represented by an  IntegrationResponse resource. 

                

              

               Example: Retrive the GET method on a specified resource Request 

              The following example request retrieves the information about the GET method on an API resource (``3kzxbg5sa2`` ) of an API (``fugvjdxtri`` ). 

               ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T210259Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

              The successful response returns a ``200 OK`` status code and a payload similar to the following:

               ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": true, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E\")" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

              In the example above, the response template for the ``200 OK`` response maps the JSON output from the ``ListStreams`` action in the back end to an XML output. The mapping template is URL-encoded as ``%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E`` and the output is decoded using the `$util.urlDecode()`_ helper function.

                  MethodResponse ,  Integration ,  IntegrationResponse ,  Resource , `Set up an API's method`_  
              

              - **httpMethod** *(string) --* 

                The method's HTTP verb.

                
              

              - **authorizationType** *(string) --* 

                The method's authorization type.

                
              

              - **authorizerId** *(string) --* 

                The identifier of an  Authorizer to use on this method. The ``authorizationType`` must be ``CUSTOM`` .

                
              

              - **apiKeyRequired** *(boolean) --* 

                A boolean flag specifying whether a valid  ApiKey is required to invoke this method.

                
              

              - **requestParameters** *(dict) --* 

                A key-value map defining required or optional method request parameters that can be accepted by Amazon API Gateway. A key is a method request parameter name matching the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` is a valid and unique parameter name. The value associated with the key is a Boolean flag indicating whether the parameter is required (``true`` ) or optional (``false`` ). The method request parameter names defined here are available in  Integration to be mapped to integration request parameters or templates.

                
                

                - *(string) --* 
                  

                  - *(boolean) --* 
            
          
              

              - **requestModels** *(dict) --* 

                A key-value map specifying data schemas, represented by  Model resources, (as the mapped value) of the request payloads of given content types (as the mapping key).

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **methodResponses** *(dict) --* 

                Gets a method response associated with a given HTTP status code. 

                  

                The collection of method responses are encapsulated in a key-value map, where the key is a response's HTTP status code and the value is a  MethodResponse resource that specifies the response returned to the caller from the back end through the integration response.

                 Example: Get a 200 OK response of a GET method Request 

                

                 ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T215008Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                The successful response returns a ``200 OK`` status code and a payload similar to the following:

                 ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.operator": false, "method.response.header.operand_2": false, "method.response.header.operand_1": false }, "statusCode": "200" }``  

                

                   `AWS CLI`_  
                

                - *(string) --* 
                  

                  - *(dict) --* 

                    Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

                      

                    

                     Example: A **MethodResponse** instance of an API Request 

                    The example request retrieves a **MethodResponse** of the 200 status code.

                     ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                    The successful response returns ``200 OK`` status and a payload as follows:

                     ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

                    

                        Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
                    

                    - **statusCode** *(string) --* 

                      The method response's status code.

                      
                    

                    - **responseParameters** *(dict) --* 

                      A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

                      
                      

                      - *(string) --* 
                        

                        - *(boolean) --* 
                  
                
                    

                    - **responseModels** *(dict) --* 

                      Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

                      
                      

                      - *(string) --* 
                        

                        - *(string) --* 
                  
                
                
            
          
              

              - **methodIntegration** *(dict) --* 

                Gets the method's integration responsible for passing the client-submitted request to the back end and performing necessary transformations to make the request compliant with the back end.

                  

                

                 Example:  Request 

                

                 ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T213210Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                The successful response returns a ``200 OK`` status code and a payload similar to the following:

                 ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true } ], "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:responses": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "0cjtch", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestTemplates": { "application/json": "{\n \"a\": \"$input.params('operand1')\",\n \"b\": \"$input.params('operand2')\", \n \"op\": \"$input.params('operator')\" \n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-west-2:lambda:path//2015-03-31/functions/arn:aws:lambda:us-west-2:123456789012:function:Calc/invocations", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.operator": "integration.response.body.op", "method.response.header.operand_2": "integration.response.body.b", "method.response.header.operand_1": "integration.response.body.a" }, "responseTemplates": { "application/json": "#set($res = $input.path('$'))\n{\n \"result\": \"$res.a, $res.b, $res.op => $res.c\",\n \"a\" : \"$res.a\",\n \"b\" : \"$res.b\",\n \"op\" : \"$res.op\",\n \"c\" : \"$res.c\"\n}" }, "selectionPattern": "", "statusCode": "200" } } }``  

                

                   `AWS CLI`_  
                

                - **type** *(string) --* 

                  Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

                  
                

                - **httpMethod** *(string) --* 

                  Specifies the integration's HTTP method type.

                  
                

                - **uri** *(string) --* 

                  Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

                  
                

                - **credentials** *(string) --* 

                  Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

                  
                

                - **requestParameters** *(dict) --* 

                  A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
                

                - **requestTemplates** *(dict) --* 

                  Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
                

                - **passthroughBehavior** *(string) --*  

                  Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

                   

                   
                  * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
                   
                  * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
                   
                  * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
                   

                   
                

                - **cacheNamespace** *(string) --* 

                  Specifies the integration's cache namespace.

                  
                

                - **cacheKeyParameters** *(list) --* 

                  Specifies the integration's cache key parameters.

                  
                  

                  - *(string) --* 
              
                

                - **integrationResponses** *(dict) --* 

                  Specifies the integration's responses.

                    

                  

                   Example: Get integration responses of a method Request 

                  

                   ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                  The successful response returns ``200 OK`` status and a payload as follows:

                   ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

                  

                     `Creating an API`_  
                  

                  - *(string) --* 
                    

                    - *(dict) --* 

                      Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                        `Creating an API`_  
                      

                      - **statusCode** *(string) --* 

                        Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                        
                      

                      - **selectionPattern** *(string) --* 

                        Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                        
                      

                      - **responseParameters** *(dict) --* 

                        A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                        
                        

                        - *(string) --* 
                          

                          - *(string) --* 
                    
                  
                      

                      - **responseTemplates** *(dict) --* 

                        Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                        
                        

                        - *(string) --* 
                          

                          - *(string) --* 
                    
                  
                  
              
            
            
          
      
    
    

  .. py:method:: update_rest_api(**kwargs)

    

    Changes information about the specified API.

    

    **Request Syntax** 
    ::

      response = client.update_rest_api(
          restApiId='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The ID of the  RestApi you want to update.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'createdDate': datetime(2015, 1, 1),
            'warnings': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a REST API.

          `Create an API`_  
        

        - **id** *(string) --* 

          The API's identifier. This identifier is unique across all of your APIs in Amazon API Gateway.

          
        

        - **name** *(string) --* 

          The API's name.

          
        

        - **description** *(string) --* 

          The API's description.

          
        

        - **createdDate** *(datetime) --* 

          The date when the API was created, in `ISO 8601 format`_ .

          
        

        - **warnings** *(list) --* 

          The warning messages reported when ``failonwarnings`` is turned on during API import.

          
          

          - *(string) --* 
      
    

  .. py:method:: update_stage(**kwargs)

    

    Changes information about a  Stage resource.

    

    **Request Syntax** 
    ::

      response = client.update_stage(
          restApiId='string',
          stageName='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi resource for the  Stage resource to change information about.

      

    
    :type stageName: string
    :param stageName: **[REQUIRED]** 

      The name of the  Stage resource to change information about.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'deploymentId': 'string',
            'clientCertificateId': 'string',
            'stageName': 'string',
            'description': 'string',
            'cacheClusterEnabled': True|False,
            'cacheClusterSize': '0.5'|'1.6'|'6.1'|'13.5'|'28.4'|'58.2'|'118'|'237',
            'cacheClusterStatus': 'CREATE_IN_PROGRESS'|'AVAILABLE'|'DELETE_IN_PROGRESS'|'NOT_AVAILABLE'|'FLUSH_IN_PROGRESS',
            'methodSettings': {
                'string': {
                    'metricsEnabled': True|False,
                    'loggingLevel': 'string',
                    'dataTraceEnabled': True|False,
                    'throttlingBurstLimit': 123,
                    'throttlingRateLimit': 123.0,
                    'cachingEnabled': True|False,
                    'cacheTtlInSeconds': 123,
                    'cacheDataEncrypted': True|False,
                    'requireAuthorizationForCacheControl': True|False,
                    'unauthorizedCacheControlHeaderStrategy': 'FAIL_WITH_403'|'SUCCEED_WITH_RESPONSE_HEADER'|'SUCCEED_WITHOUT_RESPONSE_HEADER'
                }
            },
            'variables': {
                'string': 'string'
            },
            'createdDate': datetime(2015, 1, 1),
            'lastUpdatedDate': datetime(2015, 1, 1)
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a unique identifier for a version of a deployed  RestApi that is callable by users.

          `Deploy an API`_  
        

        - **deploymentId** *(string) --* 

          The identifier of the  Deployment that the stage points to.

          
        

        - **clientCertificateId** *(string) --* 

          The identifier of a client certificate for an API stage.

          
        

        - **stageName** *(string) --* 

          The name of the stage is the first path segment in the Uniform Resource Identifier (URI) of a call to Amazon API Gateway.

          
        

        - **description** *(string) --* 

          The stage's description.

          
        

        - **cacheClusterEnabled** *(boolean) --* 

          Specifies whether a cache cluster is enabled for the stage.

          
        

        - **cacheClusterSize** *(string) --* 

          The size of the cache cluster for the stage, if enabled.

          
        

        - **cacheClusterStatus** *(string) --* 

          The status of the cache cluster for the stage, if enabled.

          
        

        - **methodSettings** *(dict) --* 

          A map that defines the method settings for a  Stage resource. Keys (designated as ``/{method_setting_key`` below) are method paths defined as ``{resource_path}/{http_method}`` for an individual method override, or ``/\*/\*`` for overriding all methods in the stage. Any forward slash ("/") characters in the ``resource_path`` part must be encoded as "~1" as in, for example, ``~1resource~1sub-resource/GET`` .

          
          

          - *(string) --* 
            

            - *(dict) --* 

              Specifies the method setting properties.

              
              

              - **metricsEnabled** *(boolean) --* 

                Specifies whether Amazon CloudWatch metrics are enabled for this method. The PATCH path for this setting is ``/{method_setting_key}/metrics/enabled`` , and the value is a Boolean.

                
              

              - **loggingLevel** *(string) --* 

                Specifies the logging level for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/loglevel`` , and the available levels are ``OFF`` , ``ERROR`` , and ``INFO`` .

                
              

              - **dataTraceEnabled** *(boolean) --* 

                Specifies whether data trace logging is enabled for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/dataTrace`` , and the value is a Boolean.

                
              

              - **throttlingBurstLimit** *(integer) --* 

                Specifies the throttling burst limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/burstLimit`` , and the value is an integer.

                
              

              - **throttlingRateLimit** *(float) --* 

                Specifies the throttling rate limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/rateLimit`` , and the value is a double.

                
              

              - **cachingEnabled** *(boolean) --* 

                Specifies whether responses should be cached and returned for requests. A cache cluster must be enabled on the stage for responses to be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/enabled`` , and the value is a Boolean.

                
              

              - **cacheTtlInSeconds** *(integer) --* 

                Specifies the time to live (TTL), in seconds, for cached responses. The higher the TTL, the longer the response will be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/ttlInSeconds`` , and the value is an integer.

                
              

              - **cacheDataEncrypted** *(boolean) --* 

                Specifies whether the cached responses are encrypted. The PATCH path for this setting is ``/{method_setting_key}/caching/dataEncrypted`` , and the value is a Boolean.

                
              

              - **requireAuthorizationForCacheControl** *(boolean) --* 

                Specifies whether authorization is required for a cache invalidation request. The PATCH path for this setting is ``/{method_setting_key}/caching/requireAuthorizationForCacheControl`` , and the value is a Boolean.

                
              

              - **unauthorizedCacheControlHeaderStrategy** *(string) --* 

                Specifies how to handle unauthorized requests for cache invalidation. The PATCH path for this setting is ``/{method_setting_key}/caching/unauthorizedCacheControlHeaderStrategy`` , and the available values are ``FAIL_WITH_403`` , ``SUCCEED_WITH_RESPONSE_HEADER`` , ``SUCCEED_WITHOUT_RESPONSE_HEADER`` .

                
          
      
    
        

        - **variables** *(dict) --* 

          A map that defines the stage variables for a  Stage resource. Variable names can have alphanumeric and underscore characters, and the values must match ``[A-Za-z0-9-._~:/?#=,]+`` .

          
          

          - *(string) --* 
            

            - *(string) --* 
      
    
        

        - **createdDate** *(datetime) --* 

          The date and time that the stage was created, in `ISO 8601 format`_ .

          
        

        - **lastUpdatedDate** *(datetime) --* 

          The date and time that information about the stage was last updated, in `ISO 8601 format`_ .

          
    

  .. py:method:: update_usage(**kwargs)

    

    Grants a temporary extension to the reamining quota of a usage plan associated with a specified API key.

    

    **Request Syntax** 
    ::

      response = client.update_usage(
          usagePlanId='string',
          keyId='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type usagePlanId: string
    :param usagePlanId: **[REQUIRED]** 

      The Id of the usage plan associated with the usage data.

      

    
    :type keyId: string
    :param keyId: **[REQUIRED]** 

      The identifier of the API key associated with the usage plan in which a temporary extension is granted to the remaining quota.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'usagePlanId': 'string',
            'startDate': 'string',
            'endDate': 'string',
            'position': 'string',
            'items': {
                'string': [
                    [
                        123,
                    ],
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the usage data of a usage plan.

           `Create and Use Usage Plans`_ , `Manage Usage in a Usage Plan`_  
        

        - **usagePlanId** *(string) --* 

          The plan Id associated with this usage data.

          
        

        - **startDate** *(string) --* 

          The starting date of the usage data.

          
        

        - **endDate** *(string) --* 

          The ending date of the usage data.

          
        

        - **position** *(string) --* 
        

        - **items** *(dict) --* 

          The usage data, as daily logs of used and remaining quotas, over the specified time interval indexed over the API keys in a usage plan. For example, ``{..., "values" : { "{api_key}" : [ [0, 100], [10, 90], [100, 10]]}`` , where ``{api_key}`` stands for an API key value and the daily log entry is of the format ``[used quota, remaining quota]`` .

          
          

          - *(string) --* 
            

            - *(list) --* 
              

              - *(list) --* 
                

                - *(integer) --* 
            
          
      
    
    

  .. py:method:: update_usage_plan(**kwargs)

    

    Updates a usage plan of a given plan Id.

    

    **Request Syntax** 
    ::

      response = client.update_usage_plan(
          usagePlanId='string',
          patchOperations=[
              {
                  'op': 'add'|'remove'|'replace'|'move'|'copy'|'test',
                  'path': 'string',
                  'value': 'string',
                  'from': 'string'
              },
          ]
      )
    :type usagePlanId: string
    :param usagePlanId: **[REQUIRED]** 

      The Id of the to-be-updated usage plan.

      

    
    :type patchOperations: list
    :param patchOperations: 

      A list of update operations to be applied to the specified resource and in the order specified in this list.

      

    
      - *(dict) --* A single patch operation to apply to the specified resource. Please refer to http://tools.ietf.org/html/rfc6902#section-4 for an explanation of how each operation is used.

      
        - **op** *(string) --* 

          An update operation to be performed with this PATCH request. The valid value can be "add", "remove", or "replace". Not all valid operations are supported for a given resource. Support of the operations depends on specific operational contexts. Attempts to apply an unsupported operation on a resource will return an error message.

          

        
        - **path** *(string) --* 

          The ``op`` operation's target, as identified by a `JSON Pointer`_ value that references a location within the targeted resource. For example, if the target resource has an updateable property of ``{"name":"value"}`` , the path for this property is ``/name`` . If the ``name`` property value is a JSON object (e.g., ``{"name": {"child/name": "child-value"}}`` ), the path for the ``child/name`` property will be ``/name/child~1name`` . Any slash ("/") character appearing in path names must be escaped with "~1", as shown in the example above. Each ``op`` operation can have only one ``path`` associated with it.

          

        
        - **value** *(string) --* 

          The new target value of the update operation. 

          

        
        - **from** *(string) --* 

          Not supported.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'id': 'string',
            'name': 'string',
            'description': 'string',
            'apiStages': [
                {
                    'apiId': 'string',
                    'stage': 'string'
                },
            ],
            'throttle': {
                'burstLimit': 123,
                'rateLimit': 123.0
            },
            'quota': {
                'limit': 123,
                'offset': 123,
                'period': 'DAY'|'WEEK'|'MONTH'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a usage plan than can specify who can assess associated API stages with specified request limits and quotas.

          

        In a usage plan, you associate an API by specifying the API's Id and a stage name of the specified API. You add plan customers by adding API keys to the plan. 

           `Create and Use Usage Plans`_  
        

        - **id** *(string) --* 

          The identifier of a  UsagePlan resource.

          
        

        - **name** *(string) --* 

          The name of a usage plan.

          
        

        - **description** *(string) --* 

          The description of a usage plan.

          
        

        - **apiStages** *(list) --* 

          The associated API stages of a usage plan.

          
          

          - *(dict) --* 

            API stage name of the associated API stage in a usage plan.

            
            

            - **apiId** *(string) --* 

              API Id of the associated API stage in a usage plan.

              
            

            - **stage** *(string) --* 

              API stage name of the associated API stage in a usage plan.

              
        
      
        

        - **throttle** *(dict) --* 

          The request throttle limits of a usage plan.

          
          

          - **burstLimit** *(integer) --* 

            The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

            
          

          - **rateLimit** *(float) --* 

            The API request steady-state rate limit.

            
      
        

        - **quota** *(dict) --* 

          The maximum number of permitted requests per a given unit time interval.

          
          

          - **limit** *(integer) --* 

            The maximum number of requests that can be made in a given time period.

            
          

          - **offset** *(integer) --* 

            The number of requests subtracted from the given limit in the initial time period.

            
          

          - **period** *(string) --* 

            The time period in which the limit applies. Valid values are "DAY", "WEEK" or "MONTH".

            
      
    

==========
Paginators
==========


The available paginators are:

* :py:class:`APIGateway.Paginator.GetApiKeys`


* :py:class:`APIGateway.Paginator.GetBasePathMappings`


* :py:class:`APIGateway.Paginator.GetClientCertificates`


* :py:class:`APIGateway.Paginator.GetDeployments`


* :py:class:`APIGateway.Paginator.GetDomainNames`


* :py:class:`APIGateway.Paginator.GetModels`


* :py:class:`APIGateway.Paginator.GetResources`


* :py:class:`APIGateway.Paginator.GetRestApis`



.. py:class:: APIGateway.Paginator.GetApiKeys

  ::

    
    paginator = client.get_paginator('get_api_keys')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`APIGateway.Client.get_api_keys`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          nameQuery='string',
          includeValues=True|False,
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type nameQuery: string
    :param nameQuery: 

      The name of queried API keys.

      

    
    :type includeValues: boolean
    :param includeValues: 

      A boolean flag to specify whether (``true`` ) or not (``false`` ) the result contains key values.

      

    
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
            'warnings': [
                'string',
            ],
            'items': [
                {
                    'id': 'string',
                    'value': 'string',
                    'name': 'string',
                    'description': 'string',
                    'enabled': True|False,
                    'createdDate': datetime(2015, 1, 1),
                    'lastUpdatedDate': datetime(2015, 1, 1),
                    'stageKeys': [
                        'string',
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of API keys as represented by an  ApiKeys resource.

          `Use API Keys`_  
        

        - **warnings** *(list) --* 

          A list of warning messages logged during the import of API keys when the ``failOnWarnings`` option is set to true.

          
          

          - *(string) --* 
      
        

        - **items** *(list) --* 

          The current page of any  ApiKey resources in the collection of  ApiKey resources.

          
          

          - *(dict) --* 

            A resource that can be distributed to callers for executing  Method resources that require an API key. API keys can be mapped to any  Stage on any  RestApi , which indicates that the callers with the API key can make requests to that stage.

              `Use API Keys`_  
            

            - **id** *(string) --* 

              The identifier of the API Key.

              
            

            - **value** *(string) --* 

              The value of the API Key.

              
            

            - **name** *(string) --* 

              The name of the API Key.

              
            

            - **description** *(string) --* 

              The description of the API Key.

              
            

            - **enabled** *(boolean) --* 

              Specifies whether the API Key can be used by callers.

              
            

            - **createdDate** *(datetime) --* 

              The date when the API Key was created, in `ISO 8601 format`_ .

              
            

            - **lastUpdatedDate** *(datetime) --* 

              When the API Key was last updated, in ISO 8601 format.

              
            

            - **stageKeys** *(list) --* 

              A list of  Stage resources that are associated with the  ApiKey resource.

              
              

              - *(string) --* 
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: APIGateway.Paginator.GetBasePathMappings

  ::

    
    paginator = client.get_paginator('get_base_path_mappings')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`APIGateway.Client.get_base_path_mappings`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          domainName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type domainName: string
    :param domainName: **[REQUIRED]** 

      The domain name of a  BasePathMapping resource.

      

    
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
            'items': [
                {
                    'basePath': 'string',
                    'restApiId': 'string',
                    'stage': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  BasePathMapping resources.

          `Use Custom Domain Names`_  
        

        - **items** *(list) --* 

          The current page of any  BasePathMapping resources in the collection of base path mapping resources.

          
          

          - *(dict) --* 

            Represents the base path that callers of the API must provide as part of the URL after the domain name.

             A custom domain name plus a ``BasePathMapping`` specification identifies a deployed  RestApi in a given stage of the owner  Account .  `Use Custom Domain Names`_  
            

            - **basePath** *(string) --* 

              The base path name that callers of the API must provide as part of the URL after the domain name.

              
            

            - **restApiId** *(string) --* 

              The name of the API.

              
            

            - **stage** *(string) --* 

              The name of the API's stage.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: APIGateway.Paginator.GetClientCertificates

  ::

    
    paginator = client.get_paginator('get_client_certificates')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`APIGateway.Client.get_client_certificates`.

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
            'items': [
                {
                    'clientCertificateId': 'string',
                    'description': 'string',
                    'pemEncodedCertificate': 'string',
                    'createdDate': datetime(2015, 1, 1),
                    'expirationDate': datetime(2015, 1, 1)
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  ClientCertificate resources.

          `Use Client-Side Certificate`_  
        

        - **items** *(list) --* 

          The current page of any  ClientCertificate resources in the collection of  ClientCertificate resources.

          
          

          - *(dict) --* 

            Represents a client certificate used to configure client-side SSL authentication while sending requests to the integration endpoint.

             Client certificates are used authenticate an API by the back-end server. To authenticate an API client (or user), use a custom  Authorizer .  `Use Client-Side Certificate`_  
            

            - **clientCertificateId** *(string) --* 

              The identifier of the client certificate.

              
            

            - **description** *(string) --* 

              The description of the client certificate.

              
            

            - **pemEncodedCertificate** *(string) --* 

              The PEM-encoded public key of the client certificate, which can be used to configure certificate authentication in the integration endpoint .

              
            

            - **createdDate** *(datetime) --* 

              The date when the client certificate was created, in `ISO 8601 format`_ .

              
            

            - **expirationDate** *(datetime) --* 

              The date when the client certificate will expire, in `ISO 8601 format`_ .

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: APIGateway.Paginator.GetDeployments

  ::

    
    paginator = client.get_paginator('get_deployments')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`APIGateway.Client.get_deployments`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          restApiId='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The identifier of the  RestApi resource for the collection of  Deployment resources to get information about.

      

    
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
            'items': [
                {
                    'id': 'string',
                    'description': 'string',
                    'createdDate': datetime(2015, 1, 1),
                    'apiSummary': {
                        'string': {
                            'string': {
                                'authorizationType': 'string',
                                'apiKeyRequired': True|False
                            }
                        }
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection resource that contains zero or more references to your existing deployments, and links that guide you on how to interact with your collection. The collection offers a paginated view of the contained deployments.

         To create a new deployment of a  RestApi , make a ``POST`` request against this resource. To view, update, or delete an existing deployment, make a ``GET`` , ``PATCH`` , or ``DELETE`` request, respectively, on a specified  Deployment resource.  `Deploying an API`_ , `AWS CLI`_ , `AWS SDKs`_  
        

        - **items** *(list) --* 

          The current page of any  Deployment resources in the collection of deployment resources.

          
          

          - *(dict) --* 

            An immutable representation of a  RestApi resource that can be called by users using  Stages . A deployment must be associated with a  Stage for it to be callable over the Internet.

             To create a deployment, call ``POST`` on the  Deployments resource of a  RestApi . To view, update, or delete a deployment, call ``GET`` , ``PATCH`` , or ``DELETE`` on the specified deployment resource (``/restapis/{restapi_id}/deployments/{deployment_id}`` ).  RestApi ,  Deployments ,  Stage , `AWS CLI`_ , `AWS SDKs`_  
            

            - **id** *(string) --* 

              The identifier for the deployment resource.

              
            

            - **description** *(string) --* 

              The description for the deployment resource.

              
            

            - **createdDate** *(datetime) --* 

              The date and time that the deployment resource was created.

              
            

            - **apiSummary** *(dict) --* 

              A summary of the  RestApi at the date and time that the deployment resource was created.

              
              

              - *(string) --* 
                

                - *(dict) --* 
                  

                  - *(string) --* 
                    

                    - *(dict) --* 

                      Represents a summary of a  Method resource, given a particular date and time.

                      
                      

                      - **authorizationType** *(string) --* 

                        Specifies the type of authorization used for the method.

                        
                      

                      - **apiKeyRequired** *(boolean) --* 

                        Specifies whether the method requires a valid  ApiKey .

                        
                  
              
            
          
        
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: APIGateway.Paginator.GetDomainNames

  ::

    
    paginator = client.get_paginator('get_domain_names')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`APIGateway.Client.get_domain_names`.

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
            'items': [
                {
                    'domainName': 'string',
                    'certificateName': 'string',
                    'certificateUploadDate': datetime(2015, 1, 1),
                    'distributionDomainName': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  DomainName resources.

          `Use Client-Side Certificate`_  
        

        - **items** *(list) --* 

          The current page of any  DomainName resources in the collection of  DomainName resources.

          
          

          - *(dict) --* 

            Represents a domain name that is contained in a simpler, more intuitive URL that can be called.

              `Use Client-Side Certificate`_  
            

            - **domainName** *(string) --* 

              The name of the  DomainName resource.

              
            

            - **certificateName** *(string) --* 

              The name of the certificate.

              
            

            - **certificateUploadDate** *(datetime) --* 

              The date when the certificate was uploaded, in `ISO 8601 format`_ .

              
            

            - **distributionDomainName** *(string) --* 

              The domain name of the Amazon CloudFront distribution. For more information, see the `Amazon CloudFront documentation`_ .

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: APIGateway.Paginator.GetModels

  ::

    
    paginator = client.get_paginator('get_models')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`APIGateway.Client.get_models`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          restApiId='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier.

      

    
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
            'items': [
                {
                    'id': 'string',
                    'name': 'string',
                    'description': 'string',
                    'schema': 'string',
                    'contentType': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  Model resources.

           Method ,  MethodResponse , `Models and Mappings`_  
        

        - **items** *(list) --* 

          Gets the current  Model resource in the collection.

          
          

          - *(dict) --* 

            Represents the data structure of a method's request or response payload.

              

            A request model defines the data structure of the client-supplied request payload. A response model defines the data structure of the response payload returned by the back end. Although not required, models are useful for mapping payloads between the front end and back end.

             

            A model is used for generating an API's SDK, validating the input request body, and creating a skeletal mapping template.

                Method ,  MethodResponse , `Models and Mappings`_  
            

            - **id** *(string) --* 

              The identifier for the model resource.

              
            

            - **name** *(string) --* 

              The name of the model.

              
            

            - **description** *(string) --* 

              The description of the model.

              
            

            - **schema** *(string) --* 

              The schema for the model. For ``application/json`` models, this should be `JSON-schema draft v4`_ model. Do not include "\*/" characters in the description of any properties because such "\*/" characters may be interpreted as the closing marker for comments in some languages, such as Java or JavaScript, causing the installation of your API's SDK generated by API Gateway to fail.

              
            

            - **contentType** *(string) --* 

              The content-type for the model.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: APIGateway.Paginator.GetResources

  ::

    
    paginator = client.get_paginator('get_resources')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`APIGateway.Client.get_resources`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          restApiId='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type restApiId: string
    :param restApiId: **[REQUIRED]** 

      The  RestApi identifier for the Resource.

      

    
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
            'items': [
                {
                    'id': 'string',
                    'parentId': 'string',
                    'pathPart': 'string',
                    'path': 'string',
                    'resourceMethods': {
                        'string': {
                            'httpMethod': 'string',
                            'authorizationType': 'string',
                            'authorizerId': 'string',
                            'apiKeyRequired': True|False,
                            'requestParameters': {
                                'string': True|False
                            },
                            'requestModels': {
                                'string': 'string'
                            },
                            'methodResponses': {
                                'string': {
                                    'statusCode': 'string',
                                    'responseParameters': {
                                        'string': True|False
                                    },
                                    'responseModels': {
                                        'string': 'string'
                                    }
                                }
                            },
                            'methodIntegration': {
                                'type': 'HTTP'|'AWS'|'MOCK',
                                'httpMethod': 'string',
                                'uri': 'string',
                                'credentials': 'string',
                                'requestParameters': {
                                    'string': 'string'
                                },
                                'requestTemplates': {
                                    'string': 'string'
                                },
                                'passthroughBehavior': 'string',
                                'cacheNamespace': 'string',
                                'cacheKeyParameters': [
                                    'string',
                                ],
                                'integrationResponses': {
                                    'string': {
                                        'statusCode': 'string',
                                        'selectionPattern': 'string',
                                        'responseParameters': {
                                            'string': 'string'
                                        },
                                        'responseTemplates': {
                                            'string': 'string'
                                        }
                                    }
                                }
                            }
                        }
                    }
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents a collection of  Resource resources.

          `Create an API`_  
        

        - **items** *(list) --* 

          Gets the current  Resource resource in the collection.

          
          

          - *(dict) --* 

            Represents an API resource.

              `Create an API`_  
            

            - **id** *(string) --* 

              The resource's identifier.

              
            

            - **parentId** *(string) --* 

              The parent resource's identifier.

              
            

            - **pathPart** *(string) --* 

              The last path segment for this resource.

              
            

            - **path** *(string) --* 

              The full path for this resource.

              
            

            - **resourceMethods** *(dict) --* 

              Gets an API resource's method of a given HTTP verb.

                

              The resource methods are a map of methods indexed by methods' HTTP verbs enabled on the resource. This method map is included in the ``200 OK`` response of the ``GET /restapis/{restapi_id}/resources/{resource_id}`` or ``GET /restapis/{restapi_id}/resources/{resource_id}?embed=methods`` request.

               Example: Get the GET method of an API resource Request ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160608T031827Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160608/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": false, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

              If the ``OPTIONS`` is enabled on the resource, you can follow the example here to get that method. Just replace the ``GET`` of the last path segment in the request URL with ``OPTIONS`` .

                 
              

              - *(string) --* 
                

                - *(dict) --* 

                  Represents a client-facing interface by which the client calls the API to access back-end resources. A **Method** resource is integrated with an  Integration resource. Both consist of a request and one or more responses. The method request takes the client input that is passed to the back end through the integration request. A method response returns the output from the back end to the client through an integration response. A method request is embodied in a **Method** resource, whereas an integration request is embodied in an  Integration resource. On the other hand, a method response is represented by a  MethodResponse resource, whereas an integration response is represented by an  IntegrationResponse resource. 

                    

                  

                   Example: Retrive the GET method on a specified resource Request 

                  The following example request retrieves the information about the GET method on an API resource (``3kzxbg5sa2`` ) of an API (``fugvjdxtri`` ). 

                   ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T210259Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                  The successful response returns a ``200 OK`` status code and a payload similar to the following:

                   ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-{rel}.html", "name": "method", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true } ], "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET", "name": "GET", "title": "GET" }, "integration:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "method:integration": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "method:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "method:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET" }, "methodresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/{status_code}", "templated": true } }, "apiKeyRequired": true, "authorizationType": "NONE", "httpMethod": "GET", "_embedded": { "method:integration": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integration:responses": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "3kzxbg5sa2", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestParameters": { "integration.request.header.Content-Type": "'application/x-amz-json-1.1'" }, "requestTemplates": { "application/json": "{\n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-east-1:kinesis:action/ListStreams", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E\")" }, "statusCode": "200" } } }, "method:responses": { "_links": { "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "name": "200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" } } }``  

                  In the example above, the response template for the ``200 OK`` response maps the JSON output from the ``ListStreams`` action in the back end to an XML output. The mapping template is URL-encoded as ``%3CkinesisStreams%3E%23foreach(%24stream%20in%20%24input.path(%27%24.StreamNames%27))%3Cstream%3E%3Cname%3E%24stream%3C%2Fname%3E%3C%2Fstream%3E%23end%3C%2FkinesisStreams%3E`` and the output is decoded using the `$util.urlDecode()`_ helper function.

                      MethodResponse ,  Integration ,  IntegrationResponse ,  Resource , `Set up an API's method`_  
                  

                  - **httpMethod** *(string) --* 

                    The method's HTTP verb.

                    
                  

                  - **authorizationType** *(string) --* 

                    The method's authorization type.

                    
                  

                  - **authorizerId** *(string) --* 

                    The identifier of an  Authorizer to use on this method. The ``authorizationType`` must be ``CUSTOM`` .

                    
                  

                  - **apiKeyRequired** *(boolean) --* 

                    A boolean flag specifying whether a valid  ApiKey is required to invoke this method.

                    
                  

                  - **requestParameters** *(dict) --* 

                    A key-value map defining required or optional method request parameters that can be accepted by Amazon API Gateway. A key is a method request parameter name matching the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` is a valid and unique parameter name. The value associated with the key is a Boolean flag indicating whether the parameter is required (``true`` ) or optional (``false`` ). The method request parameter names defined here are available in  Integration to be mapped to integration request parameters or templates.

                    
                    

                    - *(string) --* 
                      

                      - *(boolean) --* 
                
              
                  

                  - **requestModels** *(dict) --* 

                    A key-value map specifying data schemas, represented by  Model resources, (as the mapped value) of the request payloads of given content types (as the mapping key).

                    
                    

                    - *(string) --* 
                      

                      - *(string) --* 
                
              
                  

                  - **methodResponses** *(dict) --* 

                    Gets a method response associated with a given HTTP status code. 

                      

                    The collection of method responses are encapsulated in a key-value map, where the key is a response's HTTP status code and the value is a  MethodResponse resource that specifies the response returned to the caller from the back end through the integration response.

                     Example: Get a 200 OK response of a GET method Request 

                    

                     ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T215008Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                    The successful response returns a ``200 OK`` status code and a payload similar to the following:

                     ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.operator": false, "method.response.header.operand_2": false, "method.response.header.operand_1": false }, "statusCode": "200" }``  

                    

                       `AWS CLI`_  
                    

                    - *(string) --* 
                      

                      - *(dict) --* 

                        Represents a method response of a given HTTP status code returned to the client. The method response is passed from the back end through the associated integration response that can be transformed using a mapping template. 

                          

                        

                         Example: A **MethodResponse** instance of an API Request 

                        The example request retrieves a **MethodResponse** of the 200 status code.

                         ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160603T222952Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160603/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                        The successful response returns ``200 OK`` status and a payload as follows:

                         ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-method-response-{rel}.html", "name": "methodresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200", "title": "200" }, "methodresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" }, "methodresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/responses/200" } }, "responseModels": { "application/json": "Empty" }, "responseParameters": { "method.response.header.Content-Type": false }, "statusCode": "200" }``  

                        

                            Method ,  IntegrationResponse ,  Integration  `Creating an API`_  
                        

                        - **statusCode** *(string) --* 

                          The method response's status code.

                          
                        

                        - **responseParameters** *(dict) --* 

                          A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

                          
                          

                          - *(string) --* 
                            

                            - *(boolean) --* 
                      
                    
                        

                        - **responseModels** *(dict) --* 

                          Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

                          
                          

                          - *(string) --* 
                            

                            - *(string) --* 
                      
                    
                    
                
              
                  

                  - **methodIntegration** *(dict) --* 

                    Gets the method's integration responsible for passing the client-submitted request to the back end and performing necessary transformations to make the request compliant with the back end.

                      

                    

                     Example:  Request 

                    

                     ``GET /restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com Content-Length: 117 X-Amz-Date: 20160613T213210Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160613/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                    The successful response returns a ``200 OK`` status code and a payload similar to the following:

                     ``{ "_links": { "curies": [ { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-{rel}.html", "name": "integration", "templated": true }, { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true } ], "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integration:responses": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integration:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration" }, "integrationresponse:put": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/{status_code}", "templated": true } }, "cacheKeyParameters": [], "cacheNamespace": "0cjtch", "credentials": "arn:aws:iam::123456789012:role/apigAwsProxyRole", "httpMethod": "POST", "passthroughBehavior": "WHEN_NO_MATCH", "requestTemplates": { "application/json": "{\n \"a\": \"$input.params('operand1')\",\n \"b\": \"$input.params('operand2')\", \n \"op\": \"$input.params('operator')\" \n}" }, "type": "AWS", "uri": "arn:aws:apigateway:us-west-2:lambda:path//2015-03-31/functions/arn:aws:lambda:us-west-2:123456789012:function:Calc/invocations", "_embedded": { "integration:responses": { "_links": { "self": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200", "name": "200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/uojnr9hd57/resources/0cjtch/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.operator": "integration.response.body.op", "method.response.header.operand_2": "integration.response.body.b", "method.response.header.operand_1": "integration.response.body.a" }, "responseTemplates": { "application/json": "#set($res = $input.path('$'))\n{\n \"result\": \"$res.a, $res.b, $res.op => $res.c\",\n \"a\" : \"$res.a\",\n \"b\" : \"$res.b\",\n \"op\" : \"$res.op\",\n \"c\" : \"$res.c\"\n}" }, "selectionPattern": "", "statusCode": "200" } } }``  

                    

                       `AWS CLI`_  
                    

                    - **type** *(string) --* 

                      Specifies the integration's type. The valid value is ``HTTP`` , ``AWS`` , or ``MOCK`` .

                      
                    

                    - **httpMethod** *(string) --* 

                      Specifies the integration's HTTP method type.

                      
                    

                    - **uri** *(string) --* 

                      Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

                      
                    

                    - **credentials** *(string) --* 

                      Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

                      
                    

                    - **requestParameters** *(dict) --* 

                      A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

                      
                      

                      - *(string) --* 
                        

                        - *(string) --* 
                  
                
                    

                    - **requestTemplates** *(dict) --* 

                      Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

                      
                      

                      - *(string) --* 
                        

                        - *(string) --* 
                  
                
                    

                    - **passthroughBehavior** *(string) --*  

                      Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

                       

                       
                      * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
                       
                      * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
                       
                      * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
                       

                       
                    

                    - **cacheNamespace** *(string) --* 

                      Specifies the integration's cache namespace.

                      
                    

                    - **cacheKeyParameters** *(list) --* 

                      Specifies the integration's cache key parameters.

                      
                      

                      - *(string) --* 
                  
                    

                    - **integrationResponses** *(dict) --* 

                      Specifies the integration's responses.

                        

                      

                       Example: Get integration responses of a method Request 

                      

                       ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

                      The successful response returns ``200 OK`` status and a payload as follows:

                       ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

                      

                         `Creating an API`_  
                      

                      - *(string) --* 
                        

                        - *(dict) --* 

                          Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

                            `Creating an API`_  
                          

                          - **statusCode** *(string) --* 

                            Specifies the status code that is used to map the integration response to an existing  MethodResponse .

                            
                          

                          - **selectionPattern** *(string) --* 

                            Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

                            
                          

                          - **responseParameters** *(dict) --* 

                            A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

                            
                            

                            - *(string) --* 
                              

                              - *(string) --* 
                        
                      
                          

                          - **responseTemplates** *(dict) --* 

                            Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

                            
                            

                            - *(string) --* 
                              

                              - *(string) --* 
                        
                      
                      
                  
                
                
              
          
        
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: APIGateway.Paginator.GetRestApis

  ::

    
    paginator = client.get_paginator('get_rest_apis')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`APIGateway.Client.get_rest_apis`.

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
            'items': [
                {
                    'id': 'string',
                    'name': 'string',
                    'description': 'string',
                    'createdDate': datetime(2015, 1, 1),
                    'warnings': [
                        'string',
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains references to your APIs and links that guide you in how to interact with your collection. A collection offers a paginated view of your APIs.

          `Create an API`_  
        

        - **items** *(list) --* 

          An array of links to the current page of  RestApi resources.

          
          

          - *(dict) --* 

            Represents a REST API.

              `Create an API`_  
            

            - **id** *(string) --* 

              The API's identifier. This identifier is unique across all of your APIs in Amazon API Gateway.

              
            

            - **name** *(string) --* 

              The API's name.

              
            

            - **description** *(string) --* 

              The API's description.

              
            

            - **createdDate** *(datetime) --* 

              The date when the API was created, in `ISO 8601 format`_ .

              
            

            - **warnings** *(list) --* 

              The warning messages reported when ``failonwarnings`` is turned on during API import.

              
              

              - *(string) --* 
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    