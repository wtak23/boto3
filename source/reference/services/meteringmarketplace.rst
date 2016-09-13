

*******************
MarketplaceMetering
*******************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: MarketplaceMetering.Client

  A low-level client representing AWSMarketplace Metering::

    
    import boto3
    
    client = boto3.client('meteringmarketplace')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`meter_usage`

  

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

        


  .. py:method:: meter_usage(**kwargs)

    

    API to emit metering records. For identical requests, the API is idempotent. It simply returns the metering record ID. 

    

    **Request Syntax** 
    ::

      response = client.meter_usage(
          ProductCode='string',
          Timestamp=datetime(2015, 1, 1),
          UsageDimension='string',
          UsageQuantity=123,
          DryRun=True|False
      )
    :type ProductCode: string
    :param ProductCode: **[REQUIRED]** 

      Product code is used to uniquely identify a product in AWS Marketplace. The product code should be the same as the one used during the publishing of a new product.

      

    
    :type Timestamp: datetime
    :param Timestamp: **[REQUIRED]** 

      Timestamp of the hour, recorded in UTC. The seconds and milliseconds portions of the timestamp will be ignored. 

      

    
    :type UsageDimension: string
    :param UsageDimension: **[REQUIRED]** 

      It will be one of the 'fcp dimension name' provided during the publishing of the product.

      

    
    :type UsageQuantity: integer
    :param UsageQuantity: **[REQUIRED]** 

      Consumption value for the hour.

      

    
    :type DryRun: boolean
    :param DryRun: **[REQUIRED]** 

      Checks whether you have the permissions required for the action, but does not make the request. If you have the permissions, the request returns DryRunOperation; otherwise, it returns UnauthorizedException. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'MeteringRecordId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **MeteringRecordId** *(string) --* 
    