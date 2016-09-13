

***
ECR
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: ECR.Client

  A low-level client representing Amazon EC2 Container Registry (ECR)::

    
    import boto3
    
    client = boto3.client('ecr')

  
  These are the available methods:
  
  *   :py:meth:`batch_check_layer_availability`

  
  *   :py:meth:`batch_delete_image`

  
  *   :py:meth:`batch_get_image`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`complete_layer_upload`

  
  *   :py:meth:`create_repository`

  
  *   :py:meth:`delete_repository`

  
  *   :py:meth:`delete_repository_policy`

  
  *   :py:meth:`describe_repositories`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_authorization_token`

  
  *   :py:meth:`get_download_url_for_layer`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_repository_policy`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`initiate_layer_upload`

  
  *   :py:meth:`list_images`

  
  *   :py:meth:`put_image`

  
  *   :py:meth:`set_repository_policy`

  
  *   :py:meth:`upload_layer_part`

  

  .. py:method:: batch_check_layer_availability(**kwargs)

    

    Check the availability of multiple image layers in a specified registry and repository.

     

    .. note::

       

      This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

       

    

    **Request Syntax** 
    ::

      response = client.batch_check_layer_availability(
          registryId='string',
          repositoryName='string',
          layerDigests=[
              'string',
          ]
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the image layers to check. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository that is associated with the image layers to check.

      

    
    :type layerDigests: list
    :param layerDigests: **[REQUIRED]** 

      The digests of the image layers to check.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'layers': [
                {
                    'layerDigest': 'string',
                    'layerAvailability': 'AVAILABLE'|'UNAVAILABLE',
                    'layerSize': 123
                },
            ],
            'failures': [
                {
                    'layerDigest': 'string',
                    'failureCode': 'InvalidLayerDigest'|'MissingLayerDigest',
                    'failureReason': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **layers** *(list) --* 

          A list of image layer objects corresponding to the image layer references in the request.

          
          

          - *(dict) --* 

            An object representing an Amazon ECR image layer.

            
            

            - **layerDigest** *(string) --* 

              The ``sha256`` digest of the image layer.

              
            

            - **layerAvailability** *(string) --* 

              The availability status of the image layer. Valid values are ``AVAILABLE`` and ``UNAVAILABLE`` .

              
            

            - **layerSize** *(integer) --* 

              The size, in bytes, of the image layer.

              
        
      
        

        - **failures** *(list) --* 

          Any failures associated with the call.

          
          

          - *(dict) --* 

            An object representing an Amazon ECR image layer failure.

            
            

            - **layerDigest** *(string) --* 

              The layer digest associated with the failure.

              
            

            - **failureCode** *(string) --* 

              The failure code associated with the failure.

              
            

            - **failureReason** *(string) --* 

              The reason for the failure.

              
        
      
    

  .. py:method:: batch_delete_image(**kwargs)

    

    Deletes a list of specified images within a specified repository. Images are specified with either ``imageTag`` or ``imageDigest`` .

    

    **Request Syntax** 
    ::

      response = client.batch_delete_image(
          registryId='string',
          repositoryName='string',
          imageIds=[
              {
                  'imageDigest': 'string',
                  'imageTag': 'string'
              },
          ]
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the image to delete. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The repository that contains the image to delete.

      

    
    :type imageIds: list
    :param imageIds: **[REQUIRED]** 

      A list of image ID references that correspond to images to delete. The format of the ``imageIds`` reference is ``imageTag=tag`` or ``imageDigest=digest`` .

      

    
      - *(dict) --* 

        An object with identifying information for an Amazon ECR image.

        

      
        - **imageDigest** *(string) --* 

          The ``sha256`` digest of the image manifest.

          

        
        - **imageTag** *(string) --* 

          The tag used for the image.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'imageIds': [
                {
                    'imageDigest': 'string',
                    'imageTag': 'string'
                },
            ],
            'failures': [
                {
                    'imageId': {
                        'imageDigest': 'string',
                        'imageTag': 'string'
                    },
                    'failureCode': 'InvalidImageDigest'|'InvalidImageTag'|'ImageTagDoesNotMatchDigest'|'ImageNotFound'|'MissingDigestAndTag',
                    'failureReason': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **imageIds** *(list) --* 

          The image IDs of the deleted images.

          
          

          - *(dict) --* 

            An object with identifying information for an Amazon ECR image.

            
            

            - **imageDigest** *(string) --* 

              The ``sha256`` digest of the image manifest.

              
            

            - **imageTag** *(string) --* 

              The tag used for the image.

              
        
      
        

        - **failures** *(list) --* 

          Any failures associated with the call.

          
          

          - *(dict) --* 

            An object representing an Amazon ECR image failure.

            
            

            - **imageId** *(dict) --* 

              The image ID associated with the failure.

              
              

              - **imageDigest** *(string) --* 

                The ``sha256`` digest of the image manifest.

                
              

              - **imageTag** *(string) --* 

                The tag used for the image.

                
          
            

            - **failureCode** *(string) --* 

              The code associated with the failure.

              
            

            - **failureReason** *(string) --* 

              The reason for the failure.

              
        
      
    

  .. py:method:: batch_get_image(**kwargs)

    

    Gets detailed information for specified images within a specified repository. Images are specified with either ``imageTag`` or ``imageDigest`` .

    

    **Request Syntax** 
    ::

      response = client.batch_get_image(
          registryId='string',
          repositoryName='string',
          imageIds=[
              {
                  'imageDigest': 'string',
                  'imageTag': 'string'
              },
          ]
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the images to describe. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The repository that contains the images to describe.

      

    
    :type imageIds: list
    :param imageIds: **[REQUIRED]** 

      A list of image ID references that correspond to images to describe. The format of the ``imageIds`` reference is ``imageTag=tag`` or ``imageDigest=digest`` .

      

    
      - *(dict) --* 

        An object with identifying information for an Amazon ECR image.

        

      
        - **imageDigest** *(string) --* 

          The ``sha256`` digest of the image manifest.

          

        
        - **imageTag** *(string) --* 

          The tag used for the image.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'images': [
                {
                    'registryId': 'string',
                    'repositoryName': 'string',
                    'imageId': {
                        'imageDigest': 'string',
                        'imageTag': 'string'
                    },
                    'imageManifest': 'string'
                },
            ],
            'failures': [
                {
                    'imageId': {
                        'imageDigest': 'string',
                        'imageTag': 'string'
                    },
                    'failureCode': 'InvalidImageDigest'|'InvalidImageTag'|'ImageTagDoesNotMatchDigest'|'ImageNotFound'|'MissingDigestAndTag',
                    'failureReason': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **images** *(list) --* 

          A list of image objects corresponding to the image references in the request.

          
          

          - *(dict) --* 

            An object representing an Amazon ECR image.

            
            

            - **registryId** *(string) --* 

              The AWS account ID associated with the registry containing the image.

              
            

            - **repositoryName** *(string) --* 

              The name of the repository associated with the image.

              
            

            - **imageId** *(dict) --* 

              An object containing the image tag and image digest associated with an image.

              
              

              - **imageDigest** *(string) --* 

                The ``sha256`` digest of the image manifest.

                
              

              - **imageTag** *(string) --* 

                The tag used for the image.

                
          
            

            - **imageManifest** *(string) --* 

              The image manifest associated with the image.

              
        
      
        

        - **failures** *(list) --* 

          Any failures associated with the call.

          
          

          - *(dict) --* 

            An object representing an Amazon ECR image failure.

            
            

            - **imageId** *(dict) --* 

              The image ID associated with the failure.

              
              

              - **imageDigest** *(string) --* 

                The ``sha256`` digest of the image manifest.

                
              

              - **imageTag** *(string) --* 

                The tag used for the image.

                
          
            

            - **failureCode** *(string) --* 

              The code associated with the failure.

              
            

            - **failureReason** *(string) --* 

              The reason for the failure.

              
        
      
    

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


  .. py:method:: complete_layer_upload(**kwargs)

    

    Inform Amazon ECR that the image layer upload for a specified registry, repository name, and upload ID, has completed. You can optionally provide a ``sha256`` digest of the image layer for data validation purposes.

     

    .. note::

       

      This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

       

    

    **Request Syntax** 
    ::

      response = client.complete_layer_upload(
          registryId='string',
          repositoryName='string',
          uploadId='string',
          layerDigests=[
              'string',
          ]
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry to which to upload layers. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository to associate with the image layer.

      

    
    :type uploadId: string
    :param uploadId: **[REQUIRED]** 

      The upload ID from a previous  InitiateLayerUpload operation to associate with the image layer.

      

    
    :type layerDigests: list
    :param layerDigests: **[REQUIRED]** 

      The ``sha256`` digest of the image layer.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'registryId': 'string',
            'repositoryName': 'string',
            'uploadId': 'string',
            'layerDigest': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **registryId** *(string) --* 

          The registry ID associated with the request.

          
        

        - **repositoryName** *(string) --* 

          The repository name associated with the request.

          
        

        - **uploadId** *(string) --* 

          The upload ID associated with the layer.

          
        

        - **layerDigest** *(string) --* 

          The ``sha256`` digest of the image layer.

          
    

  .. py:method:: create_repository(**kwargs)

    

    Creates an image repository.

    

    **Request Syntax** 
    ::

      response = client.create_repository(
          repositoryName='string'
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name to use for the repository. The repository name may be specified on its own (such as ``nginx-web-app`` ) or it can be prepended with a namespace to group the repository into a category (such as ``project-a/nginx-web-app`` ).

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'repository': {
                'repositoryArn': 'string',
                'registryId': 'string',
                'repositoryName': 'string',
                'repositoryUri': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **repository** *(dict) --* 

          An object representing a repository.

          
          

          - **repositoryArn** *(string) --* 

            The Amazon Resource Name (ARN) that identifies the repository. The ARN contains the ``arn:aws:ecr`` namespace, followed by the region of the repository, the AWS account ID of the repository owner, the repository namespace, and then the repository name. For example, ``arn:aws:ecr:region:012345678910:repository/test`` .

            
          

          - **registryId** *(string) --* 

            The AWS account ID associated with the registry that contains the repository.

            
          

          - **repositoryName** *(string) --* 

            The name of the repository.

            
          

          - **repositoryUri** *(string) --* 

            The URI for the repository. You can use this URI for Docker ``push`` and ``pull`` operations.

            
      
    

  .. py:method:: delete_repository(**kwargs)

    

    Deletes an existing image repository. If a repository contains images, you must use the ``force`` option to delete it.

    

    **Request Syntax** 
    ::

      response = client.delete_repository(
          registryId='string',
          repositoryName='string',
          force=True|False
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the repository to delete. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository to delete.

      

    
    :type force: boolean
    :param force: 

      Force the deletion of the repository if it contains images.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'repository': {
                'repositoryArn': 'string',
                'registryId': 'string',
                'repositoryName': 'string',
                'repositoryUri': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **repository** *(dict) --* 

          An object representing a repository.

          
          

          - **repositoryArn** *(string) --* 

            The Amazon Resource Name (ARN) that identifies the repository. The ARN contains the ``arn:aws:ecr`` namespace, followed by the region of the repository, the AWS account ID of the repository owner, the repository namespace, and then the repository name. For example, ``arn:aws:ecr:region:012345678910:repository/test`` .

            
          

          - **registryId** *(string) --* 

            The AWS account ID associated with the registry that contains the repository.

            
          

          - **repositoryName** *(string) --* 

            The name of the repository.

            
          

          - **repositoryUri** *(string) --* 

            The URI for the repository. You can use this URI for Docker ``push`` and ``pull`` operations.

            
      
    

  .. py:method:: delete_repository_policy(**kwargs)

    

    Deletes the repository policy from a specified repository.

    

    **Request Syntax** 
    ::

      response = client.delete_repository_policy(
          registryId='string',
          repositoryName='string'
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the repository policy to delete. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository that is associated with the repository policy to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'registryId': 'string',
            'repositoryName': 'string',
            'policyText': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **registryId** *(string) --* 

          The registry ID associated with the request.

          
        

        - **repositoryName** *(string) --* 

          The repository name associated with the request.

          
        

        - **policyText** *(string) --* 

          The JSON repository policy that was deleted from the repository.

          
    

  .. py:method:: describe_repositories(**kwargs)

    

    Describes image repositories in a registry.

    

    **Request Syntax** 
    ::

      response = client.describe_repositories(
          registryId='string',
          repositoryNames=[
              'string',
          ],
          nextToken='string',
          maxResults=123
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the repositories to be described. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryNames: list
    :param repositoryNames: 

      A list of repositories to describe. If this parameter is omitted, then all repositories in a registry are described.

      

    
      - *(string) --* 

      
  
    :type nextToken: string
    :param nextToken: 

      The ``nextToken`` value returned from a previous paginated ``DescribeRepositories`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

       

      .. note::

         

        This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

         

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of repository results returned by ``DescribeRepositories`` in paginated output. When this parameter is used, ``DescribeRepositories`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``DescribeRepositories`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``DescribeRepositories`` returns up to 100 results and a ``nextToken`` value, if applicable.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'repositories': [
                {
                    'repositoryArn': 'string',
                    'registryId': 'string',
                    'repositoryName': 'string',
                    'repositoryUri': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **repositories** *(list) --* 

          A list of repository objects corresponding to valid repositories.

          
          

          - *(dict) --* 

            An object representing a repository.

            
            

            - **repositoryArn** *(string) --* 

              The Amazon Resource Name (ARN) that identifies the repository. The ARN contains the ``arn:aws:ecr`` namespace, followed by the region of the repository, the AWS account ID of the repository owner, the repository namespace, and then the repository name. For example, ``arn:aws:ecr:region:012345678910:repository/test`` .

              
            

            - **registryId** *(string) --* 

              The AWS account ID associated with the registry that contains the repository.

              
            

            - **repositoryName** *(string) --* 

              The name of the repository.

              
            

            - **repositoryUri** *(string) --* 

              The URI for the repository. You can use this URI for Docker ``push`` and ``pull`` operations.

              
        
      
        

        - **nextToken** *(string) --* 

          The ``nextToken`` value to include in a future ``DescribeRepositories`` request. When the results of a ``DescribeRepositories`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

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


  .. py:method:: get_authorization_token(**kwargs)

    

    Retrieves a token that is valid for a specified registry for 12 hours. This command allows you to use the ``docker`` CLI to push and pull images with Amazon ECR. If you do not specify a registry, the default registry is assumed.

     

    The ``authorizationToken`` returned for each registry specified is a base64 encoded string that can be decoded and used in a ``docker login`` command to authenticate to a registry. The AWS CLI offers an ``aws ecr get-login`` command that simplifies the login process.

    

    **Request Syntax** 
    ::

      response = client.get_authorization_token(
          registryIds=[
              'string',
          ]
      )
    :type registryIds: list
    :param registryIds: 

      A list of AWS account IDs that are associated with the registries for which to get authorization tokens. If you do not specify a registry, the default registry is assumed.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'authorizationData': [
                {
                    'authorizationToken': 'string',
                    'expiresAt': datetime(2015, 1, 1),
                    'proxyEndpoint': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **authorizationData** *(list) --* 

          A list of authorization token data objects that correspond to the ``registryIds`` values in the request.

          
          

          - *(dict) --* 

            An object representing authorization data for an Amazon ECR registry.

            
            

            - **authorizationToken** *(string) --* 

              A base64-encoded string that contains authorization data for the specified Amazon ECR registry. When the string is decoded, it is presented in the format ``user:password`` for private registry authentication using ``docker login`` .

              
            

            - **expiresAt** *(datetime) --* 

              The Unix time in seconds and milliseconds when the authorization token expires. Authorization tokens are valid for 12 hours.

              
            

            - **proxyEndpoint** *(string) --* 

              The registry URL to use for this authorization token in a ``docker login`` command. The Amazon ECR registry URL format is ``https://aws_account_id.dkr.ecr.region.amazonaws.com`` . For example, ``https://012345678910.dkr.ecr.us-east-1.amazonaws.com`` .. 

              
        
      
    

  .. py:method:: get_download_url_for_layer(**kwargs)

    

    Retrieves the pre-signed Amazon S3 download URL corresponding to an image layer. You can only get URLs for image layers that are referenced in an image.

     

    .. note::

       

      This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

       

    

    **Request Syntax** 
    ::

      response = client.get_download_url_for_layer(
          registryId='string',
          repositoryName='string',
          layerDigest='string'
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the image layer to download. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository that is associated with the image layer to download.

      

    
    :type layerDigest: string
    :param layerDigest: **[REQUIRED]** 

      The digest of the image layer to download.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'downloadUrl': 'string',
            'layerDigest': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **downloadUrl** *(string) --* 

          The pre-signed Amazon S3 download URL for the requested layer.

          
        

        - **layerDigest** *(string) --* 

          The digest of the image layer to download.

          
    

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


  .. py:method:: get_repository_policy(**kwargs)

    

    Retrieves the repository policy for a specified repository.

    

    **Request Syntax** 
    ::

      response = client.get_repository_policy(
          registryId='string',
          repositoryName='string'
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the repository. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository whose policy you want to retrieve.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'registryId': 'string',
            'repositoryName': 'string',
            'policyText': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **registryId** *(string) --* 

          The registry ID associated with the request.

          
        

        - **repositoryName** *(string) --* 

          The repository name associated with the request.

          
        

        - **policyText** *(string) --* 

          The JSON repository policy text associated with the repository.

          
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: initiate_layer_upload(**kwargs)

    

    Notify Amazon ECR that you intend to upload an image layer.

     

    .. note::

       

      This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

       

    

    **Request Syntax** 
    ::

      response = client.initiate_layer_upload(
          registryId='string',
          repositoryName='string'
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that you intend to upload layers to. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository that you intend to upload layers to.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'uploadId': 'string',
            'partSize': 123
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **uploadId** *(string) --* 

          The upload ID for the layer upload. This parameter is passed to further  UploadLayerPart and  CompleteLayerUpload operations.

          
        

        - **partSize** *(integer) --* 

          The size, in bytes, that Amazon ECR expects future layer part uploads to be.

          
    

  .. py:method:: list_images(**kwargs)

    

    Lists all the image IDs for a given repository.

     

    You can filter images based on whether or not they are tagged by setting the ``tagStatus`` parameter to ``TAGGED`` or ``UNTAGGED`` . For example, you can filter your results to return only ``UNTAGGED`` images and then pipe that result to a  BatchDeleteImage operation to delete them. Or, you can filter your results to return only ``TAGGED`` images to list all of the tags in your repository.

    

    **Request Syntax** 
    ::

      response = client.list_images(
          registryId='string',
          repositoryName='string',
          nextToken='string',
          maxResults=123,
          filter={
              'tagStatus': 'TAGGED'|'UNTAGGED'
          }
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the repository to list images in. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The repository whose image IDs are to be listed.

      

    
    :type nextToken: string
    :param nextToken: 

      The ``nextToken`` value returned from a previous paginated ``ListImages`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

       

      .. note::

         

        This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

         

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of image results returned by ``ListImages`` in paginated output. When this parameter is used, ``ListImages`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``ListImages`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``ListImages`` returns up to 100 results and a ``nextToken`` value, if applicable.

      

    
    :type filter: dict
    :param filter: 

      The filter key and value with which to filter your ``ListImages`` results.

      

    
      - **tagStatus** *(string) --* 

        The tag status with which to filter your  ListImages results. You can filter results based on whether they are ``TAGGED`` or ``UNTAGGED`` .

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'imageIds': [
                {
                    'imageDigest': 'string',
                    'imageTag': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **imageIds** *(list) --* 

          The list of image IDs for the requested repository.

          
          

          - *(dict) --* 

            An object with identifying information for an Amazon ECR image.

            
            

            - **imageDigest** *(string) --* 

              The ``sha256`` digest of the image manifest.

              
            

            - **imageTag** *(string) --* 

              The tag used for the image.

              
        
      
        

        - **nextToken** *(string) --* 

          The ``nextToken`` value to include in a future ``ListImages`` request. When the results of a ``ListImages`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

  .. py:method:: put_image(**kwargs)

    

    Creates or updates the image manifest associated with an image.

     

    .. note::

       

      This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

       

    

    **Request Syntax** 
    ::

      response = client.put_image(
          registryId='string',
          repositoryName='string',
          imageManifest='string'
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the repository in which to put the image. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository in which to put the image.

      

    
    :type imageManifest: string
    :param imageManifest: **[REQUIRED]** 

      The image manifest corresponding to the image to be uploaded.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'image': {
                'registryId': 'string',
                'repositoryName': 'string',
                'imageId': {
                    'imageDigest': 'string',
                    'imageTag': 'string'
                },
                'imageManifest': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **image** *(dict) --* 

          Details of the image uploaded.

          
          

          - **registryId** *(string) --* 

            The AWS account ID associated with the registry containing the image.

            
          

          - **repositoryName** *(string) --* 

            The name of the repository associated with the image.

            
          

          - **imageId** *(dict) --* 

            An object containing the image tag and image digest associated with an image.

            
            

            - **imageDigest** *(string) --* 

              The ``sha256`` digest of the image manifest.

              
            

            - **imageTag** *(string) --* 

              The tag used for the image.

              
        
          

          - **imageManifest** *(string) --* 

            The image manifest associated with the image.

            
      
    

  .. py:method:: set_repository_policy(**kwargs)

    

    Applies a repository policy on a specified repository to control access permissions.

    

    **Request Syntax** 
    ::

      response = client.set_repository_policy(
          registryId='string',
          repositoryName='string',
          policyText='string',
          force=True|False
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the repository. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository to receive the policy.

      

    
    :type policyText: string
    :param policyText: **[REQUIRED]** 

      The JSON repository policy text to apply to the repository.

      

    
    :type force: boolean
    :param force: 

      If the policy you are attempting to set on a repository policy would prevent you from setting another policy in the future, you must force the  SetRepositoryPolicy operation. This is intended to prevent accidental repository lock outs.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'registryId': 'string',
            'repositoryName': 'string',
            'policyText': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **registryId** *(string) --* 

          The registry ID associated with the request.

          
        

        - **repositoryName** *(string) --* 

          The repository name associated with the request.

          
        

        - **policyText** *(string) --* 

          The JSON repository policy text applied to the repository.

          
    

  .. py:method:: upload_layer_part(**kwargs)

    

    Uploads an image layer part to Amazon ECR.

     

    .. note::

       

      This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

       

    

    **Request Syntax** 
    ::

      response = client.upload_layer_part(
          registryId='string',
          repositoryName='string',
          uploadId='string',
          partFirstByte=123,
          partLastByte=123,
          layerPartBlob=b'bytes'
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that you are uploading layer parts to. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository that you are uploading layer parts to.

      

    
    :type uploadId: string
    :param uploadId: **[REQUIRED]** 

      The upload ID from a previous  InitiateLayerUpload operation to associate with the layer part upload.

      

    
    :type partFirstByte: integer
    :param partFirstByte: **[REQUIRED]** 

      The integer value of the first byte of the layer part.

      

    
    :type partLastByte: integer
    :param partLastByte: **[REQUIRED]** 

      The integer value of the last byte of the layer part.

      

    
    :type layerPartBlob: bytes
    :param layerPartBlob: **[REQUIRED]** 

      The base64-encoded layer part payload.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'registryId': 'string',
            'repositoryName': 'string',
            'uploadId': 'string',
            'lastByteReceived': 123
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **registryId** *(string) --* 

          The registry ID associated with the request.

          
        

        - **repositoryName** *(string) --* 

          The repository name associated with the request.

          
        

        - **uploadId** *(string) --* 

          The upload ID associated with the request.

          
        

        - **lastByteReceived** *(integer) --* 

          The integer value of the last byte received in the request.

          
    

==========
Paginators
==========


The available paginators are:

* :py:class:`ECR.Paginator.ListImages`



.. py:class:: ECR.Paginator.ListImages

  ::

    
    paginator = client.get_paginator('list_images')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ECR.Client.list_images`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          registryId='string',
          repositoryName='string',
          filter={
              'tagStatus': 'TAGGED'|'UNTAGGED'
          },
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type registryId: string
    :param registryId: 

      The AWS account ID associated with the registry that contains the repository to list images in. If you do not specify a registry, the default registry is assumed.

      

    
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The repository whose image IDs are to be listed.

      

    
    :type filter: dict
    :param filter: 

      The filter key and value with which to filter your ``ListImages`` results.

      

    
      - **tagStatus** *(string) --* 

        The tag status with which to filter your  ListImages results. You can filter results based on whether they are ``TAGGED`` or ``UNTAGGED`` .

        

      
    
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
            'imageIds': [
                {
                    'imageDigest': 'string',
                    'imageTag': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **imageIds** *(list) --* 

          The list of image IDs for the requested repository.

          
          

          - *(dict) --* 

            An object with identifying information for an Amazon ECR image.

            
            

            - **imageDigest** *(string) --* 

              The ``sha256`` digest of the image manifest.

              
            

            - **imageTag** *(string) --* 

              The tag used for the image.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    