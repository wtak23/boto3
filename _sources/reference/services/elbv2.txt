

.. _Target Groups for Your Application Load Balancers: http://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html
.. _Limits for Your Application Load Balancer: http://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-limits.html
.. _Listeners for Your Application Load Balancers: http://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html


**********************
ElasticLoadBalancingv2
**********************

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: ElasticLoadBalancingv2.Client

  A low-level client representing Elastic Load Balancing (Elastic Load Balancing v2)::

    
    import boto3
    
    client = boto3.client('elbv2')

  
  These are the available methods:
  
  *   :py:meth:`add_tags`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_listener`

  
  *   :py:meth:`create_load_balancer`

  
  *   :py:meth:`create_rule`

  
  *   :py:meth:`create_target_group`

  
  *   :py:meth:`delete_listener`

  
  *   :py:meth:`delete_load_balancer`

  
  *   :py:meth:`delete_rule`

  
  *   :py:meth:`delete_target_group`

  
  *   :py:meth:`deregister_targets`

  
  *   :py:meth:`describe_listeners`

  
  *   :py:meth:`describe_load_balancer_attributes`

  
  *   :py:meth:`describe_load_balancers`

  
  *   :py:meth:`describe_rules`

  
  *   :py:meth:`describe_ssl_policies`

  
  *   :py:meth:`describe_tags`

  
  *   :py:meth:`describe_target_group_attributes`

  
  *   :py:meth:`describe_target_groups`

  
  *   :py:meth:`describe_target_health`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`modify_listener`

  
  *   :py:meth:`modify_load_balancer_attributes`

  
  *   :py:meth:`modify_rule`

  
  *   :py:meth:`modify_target_group`

  
  *   :py:meth:`modify_target_group_attributes`

  
  *   :py:meth:`register_targets`

  
  *   :py:meth:`remove_tags`

  
  *   :py:meth:`set_rule_priorities`

  
  *   :py:meth:`set_security_groups`

  
  *   :py:meth:`set_subnets`

  

  .. py:method:: add_tags(**kwargs)

    

    Adds the specified tags to the specified resource. You can tag your Application load balancers and your target groups.

     

    Each tag consists of a key and an optional value. If a resource already has a tag with the same key, ``AddTags`` updates its value.

     

    To list the current tags for your resources, use  DescribeTags . To remove tags from your resources, use  RemoveTags .

    

    **Request Syntax** 
    ::

      response = client.add_tags(
          ResourceArns=[
              'string',
          ],
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type ResourceArns: list
    :param ResourceArns: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the resource.

      

    
      - *(string) --* 

      
  
    :type Tags: list
    :param Tags: **[REQUIRED]** 

      The tags. Each resource can have a maximum of 10 tags.

      

    
      - *(dict) --* 

        Information about a tag.

        

      
        - **Key** *(string) --* **[REQUIRED]** 

          The key of the tag.

          

        
        - **Value** *(string) --* 

          The value of the tag.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of AddTags.

        
    

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


  .. py:method:: create_listener(**kwargs)

    

    Creates a listener for the specified Application load balancer.

     

    To update a listener, use  ModifyListener . When you are finished with a listener, you can delete it using  DeleteListener . If you are finished with both the listener and the load balancer, you can delete them both using  DeleteLoadBalancer .

     

    For more information, see `Listeners for Your Application Load Balancers`_ in the *Application Load Balancers Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_listener(
          LoadBalancerArn='string',
          Protocol='HTTP'|'HTTPS',
          Port=123,
          SslPolicy='string',
          Certificates=[
              {
                  'CertificateArn': 'string'
              },
          ],
          DefaultActions=[
              {
                  'Type': 'forward',
                  'TargetGroupArn': 'string'
              },
          ]
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    :type Protocol: string
    :param Protocol: **[REQUIRED]** 

      The protocol for connections from clients to the load balancer.

      

    
    :type Port: integer
    :param Port: **[REQUIRED]** 

      The port on which the load balancer is listening.

      

    
    :type SslPolicy: string
    :param SslPolicy: 

      The security policy that defines which ciphers and protocols are supported. The default is the current predefined security policy.

      

    
    :type Certificates: list
    :param Certificates: 

      The SSL server certificate. You must provide exactly one certificate if the protocol is HTTPS.

      

    
      - *(dict) --* 

        Information about an SSL server certificate deployed on a load balancer.

        

      
        - **CertificateArn** *(string) --* 

          The Amazon Resource Name (ARN) of the certificate.

          

        
      
  
    :type DefaultActions: list
    :param DefaultActions: **[REQUIRED]** 

      The default actions for the listener.

      

    
      - *(dict) --* 

        Information about an action.

        

      
        - **Type** *(string) --* **[REQUIRED]** 

          The type of action.

          

        
        - **TargetGroupArn** *(string) --* **[REQUIRED]** 

          The Amazon Resource Name (ARN) of the target group.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Listeners': [
                {
                    'ListenerArn': 'string',
                    'LoadBalancerArn': 'string',
                    'Port': 123,
                    'Protocol': 'HTTP'|'HTTPS',
                    'Certificates': [
                        {
                            'CertificateArn': 'string'
                        },
                    ],
                    'SslPolicy': 'string',
                    'DefaultActions': [
                        {
                            'Type': 'forward',
                            'TargetGroupArn': 'string'
                        },
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of CreateListener.

        
        

        - **Listeners** *(list) --* 

          Information about the listener.

          
          

          - *(dict) --* 

            Information about a listener.

            
            

            - **ListenerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the listener.

              
            

            - **LoadBalancerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the load balancer.

              
            

            - **Port** *(integer) --* 

              The port on which the load balancer is listening.

              
            

            - **Protocol** *(string) --* 

              The protocol for connections from clients to the load balancer.

              
            

            - **Certificates** *(list) --* 

              The SSL server certificate. You must provide a certificate if the protocol is HTTPS.

              
              

              - *(dict) --* 

                Information about an SSL server certificate deployed on a load balancer.

                
                

                - **CertificateArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the certificate.

                  
            
          
            

            - **SslPolicy** *(string) --* 

              The security policy that defines which ciphers and protocols are supported. The default is the current predefined security policy.

              
            

            - **DefaultActions** *(list) --* 

              The default actions for the listener.

              
              

              - *(dict) --* 

                Information about an action.

                
                

                - **Type** *(string) --* 

                  The type of action.

                  
                

                - **TargetGroupArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the target group.

                  
            
          
        
      
    

  .. py:method:: create_load_balancer(**kwargs)

    

    Creates an Application load balancer.

     

    To create listeners for your load balancer, use  CreateListener . You can add security groups, subnets, and tags when you create your load balancer, or you can add them later using  SetSecurityGroups ,  SetSubnets , and  AddTags .

     

    To describe your current load balancers, see  DescribeLoadBalancers . When you are finished with a load balancer, you can delete it using  DeleteLoadBalancer .

     

    You can create up to 20 load balancers per region per account. You can request an increase for the number of load balancers for your account. For more information, see `Limits for Your Application Load Balancer`_ in the *Application Load Balancers Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_load_balancer(
          Name='string',
          Subnets=[
              'string',
          ],
          SecurityGroups=[
              'string',
          ],
          Scheme='internet-facing'|'internal',
          Tags=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the load balancer.

       

      This name must be unique within your AWS account, can have a maximum of 32 characters, must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen.

      

    
    :type Subnets: list
    :param Subnets: **[REQUIRED]** 

      The IDs of the subnets to attach to the load balancer. You can specify only one subnet per Availability Zone. You must specify subnets from at least two Availability Zones.

      

    
      - *(string) --* 

      
  
    :type SecurityGroups: list
    :param SecurityGroups: 

      The IDs of the security groups to assign to the load balancer.

      

    
      - *(string) --* 

      
  
    :type Scheme: string
    :param Scheme: 

      The nodes of an Internet-facing load balancer have public IP addresses. The DNS name of an Internet-facing load balancer is publicly resolvable to the public IP addresses of the nodes. Therefore, Internet-facing load balancers can route requests from clients over the Internet.

       

      The nodes of an internal load balancer have only private IP addresses. The DNS name of an internal load balancer is publicly resolvable to the private IP addresses of the nodes. Therefore, internal load balancers can only route requests from clients with access to the VPC for the load balancer.

       

      The default is an Internet-facing load balancer.

      

    
    :type Tags: list
    :param Tags: 

      One or more tags to assign to the load balancer.

      

    
      - *(dict) --* 

        Information about a tag.

        

      
        - **Key** *(string) --* **[REQUIRED]** 

          The key of the tag.

          

        
        - **Value** *(string) --* 

          The value of the tag.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LoadBalancers': [
                {
                    'LoadBalancerArn': 'string',
                    'DNSName': 'string',
                    'CanonicalHostedZoneId': 'string',
                    'CreatedTime': datetime(2015, 1, 1),
                    'LoadBalancerName': 'string',
                    'Scheme': 'internet-facing'|'internal',
                    'VpcId': 'string',
                    'State': {
                        'Code': 'active'|'provisioning'|'failed',
                        'Reason': 'string'
                    },
                    'Type': 'application',
                    'AvailabilityZones': [
                        {
                            'ZoneName': 'string',
                            'SubnetId': 'string'
                        },
                    ],
                    'SecurityGroups': [
                        'string',
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of CreateLoadBalancer.

        
        

        - **LoadBalancers** *(list) --* 

          Information about the load balancer.

          
          

          - *(dict) --* 

            Information about a load balancer.

            
            

            - **LoadBalancerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the load balancer.

              
            

            - **DNSName** *(string) --* 

              The public DNS name of the load balancer.

              
            

            - **CanonicalHostedZoneId** *(string) --* 

              The ID of the Amazon Route 53 hosted zone associated with the load balancer.

              
            

            - **CreatedTime** *(datetime) --* 

              The date and time the load balancer was created.

              
            

            - **LoadBalancerName** *(string) --* 

              The name of the load balancer.

              
            

            - **Scheme** *(string) --* 

              The nodes of an Internet-facing load balancer have public IP addresses. The DNS name of an Internet-facing load balancer is publicly resolvable to the public IP addresses of the nodes. Therefore, Internet-facing load balancers can route requests from clients over the Internet.

               

              The nodes of an internal load balancer have only private IP addresses. The DNS name of an internal load balancer is publicly resolvable to the private IP addresses of the nodes. Therefore, internal load balancers can only route requests from clients with access to the VPC for the load balancer.

              
            

            - **VpcId** *(string) --* 

              The ID of the VPC for the load balancer.

              
            

            - **State** *(dict) --* 

              The state of the load balancer.

              
              

              - **Code** *(string) --* 

                The state code. The initial state of the load balancer is ``provisioning`` . After the load balancer is fully set up and ready to route traffic, its state is ``active`` . If the load balancer could not be set up, its state is ``failed`` .

                
              

              - **Reason** *(string) --* 

                A description of the state.

                
          
            

            - **Type** *(string) --* 

              The type of load balancer.

              
            

            - **AvailabilityZones** *(list) --* 

              The Availability Zones for the load balancer.

              
              

              - *(dict) --* 

                Information about an Availability Zone.

                
                

                - **ZoneName** *(string) --* 

                  The name of the Availability Zone.

                  
                

                - **SubnetId** *(string) --* 

                  The ID of the subnet.

                  
            
          
            

            - **SecurityGroups** *(list) --* 

              The IDs of the security groups for the load balancer.

              
              

              - *(string) --* 
          
        
      
    

  .. py:method:: create_rule(**kwargs)

    

    Creates a rule for the specified listener.

     

    A rule consists conditions and actions. Rules are evaluated in priority order, from the lowest value to the highest value. When the conditions for a rule are met, the specified actions are taken. If no rule's conditions are met, the default actions for the listener are taken.

     

    To view your current rules, use  DescribeRules . To update a rule, use  ModifyRule . To set the priorities of your rules, use  SetRulePriorities . To delete a rule, use  DeleteRule .

    

    **Request Syntax** 
    ::

      response = client.create_rule(
          ListenerArn='string',
          Conditions=[
              {
                  'Field': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          Priority=123,
          Actions=[
              {
                  'Type': 'forward',
                  'TargetGroupArn': 'string'
              },
          ]
      )
    :type ListenerArn: string
    :param ListenerArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the listener.

      

    
    :type Conditions: list
    :param Conditions: **[REQUIRED]** 

      The conditions.

      

    
      - *(dict) --* 

        Information about a condition for a rule.

        

      
        - **Field** *(string) --* 

          The name of the field. The possible value is ``path-pattern`` .

          

        
        - **Values** *(list) --* 

          The values for the field.

           

          A path pattern is case sensitive, can be up to 255 characters in length, and can contain any of the following characters:

           

           
          * A-Z, a-z, 0-9 
           
          * _ - . $ / ~ " ' @ : + 
           
          * amp; (using amp;amp;) 
           
          * * (matches 0 or more characters) 
           
          * ? (matches exactly 1 character) 
           

          

        
          - *(string) --* 

          
      
      
  
    :type Priority: integer
    :param Priority: **[REQUIRED]** 

      The priority for the rule. A listener can't have multiple rules with the same priority.

      

    
    :type Actions: list
    :param Actions: **[REQUIRED]** 

      The actions for the rule.

      

    
      - *(dict) --* 

        Information about an action.

        

      
        - **Type** *(string) --* **[REQUIRED]** 

          The type of action.

          

        
        - **TargetGroupArn** *(string) --* **[REQUIRED]** 

          The Amazon Resource Name (ARN) of the target group.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Rules': [
                {
                    'RuleArn': 'string',
                    'Priority': 'string',
                    'Conditions': [
                        {
                            'Field': 'string',
                            'Values': [
                                'string',
                            ]
                        },
                    ],
                    'Actions': [
                        {
                            'Type': 'forward',
                            'TargetGroupArn': 'string'
                        },
                    ],
                    'IsDefault': True|False
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of CreateRule.

        
        

        - **Rules** *(list) --* 

          Information about the rule.

          
          

          - *(dict) --* 

            Information about a rule.

            
            

            - **RuleArn** *(string) --* 

              The Amazon Resource Name (ARN) of the rule.

              
            

            - **Priority** *(string) --* 

              The priority.

              
            

            - **Conditions** *(list) --* 

              The conditions.

              
              

              - *(dict) --* 

                Information about a condition for a rule.

                
                

                - **Field** *(string) --* 

                  The name of the field. The possible value is ``path-pattern`` .

                  
                

                - **Values** *(list) --* 

                  The values for the field.

                   

                  A path pattern is case sensitive, can be up to 255 characters in length, and can contain any of the following characters:

                   

                   
                  * A-Z, a-z, 0-9 
                   
                  * _ - . $ / ~ " ' @ : + 
                   
                  * amp; (using amp;amp;) 
                   
                  * * (matches 0 or more characters) 
                   
                  * ? (matches exactly 1 character) 
                   

                  
                  

                  - *(string) --* 
              
            
          
            

            - **Actions** *(list) --* 

              The actions.

              
              

              - *(dict) --* 

                Information about an action.

                
                

                - **Type** *(string) --* 

                  The type of action.

                  
                

                - **TargetGroupArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the target group.

                  
            
          
            

            - **IsDefault** *(boolean) --* 

              Indicates whether this is the default rule.

              
        
      
    

  .. py:method:: create_target_group(**kwargs)

    

    Creates a target group.

     

    To register targets with the target group, use  RegisterTargets . To update the health check settings for the target group, use  ModifyTargetGroup . To monitor the health of targets in the target group, use  DescribeTargetHealth .

     

    To route traffic to the targets in a target group, specify the target group in an action using  CreateListener or  CreateRule .

     

    To delete a target group, use  DeleteTargetGroup .

     

    For more information, see `Target Groups for Your Application Load Balancers`_ in the *Application Load Balancers Guide* .

    

    **Request Syntax** 
    ::

      response = client.create_target_group(
          Name='string',
          Protocol='HTTP'|'HTTPS',
          Port=123,
          VpcId='string',
          HealthCheckProtocol='HTTP'|'HTTPS',
          HealthCheckPort='string',
          HealthCheckPath='string',
          HealthCheckIntervalSeconds=123,
          HealthCheckTimeoutSeconds=123,
          HealthyThresholdCount=123,
          UnhealthyThresholdCount=123,
          Matcher={
              'HttpCode': 'string'
          }
      )
    :type Name: string
    :param Name: **[REQUIRED]** 

      The name of the target group.

      

    
    :type Protocol: string
    :param Protocol: **[REQUIRED]** 

      The protocol to use for routing traffic to the targets.

      

    
    :type Port: integer
    :param Port: **[REQUIRED]** 

      The port on which the targets receive traffic. This port is used unless you specify a port override when registering the target.

      

    
    :type VpcId: string
    :param VpcId: **[REQUIRED]** 

      The identifier of the virtual private cloud (VPC).

      

    
    :type HealthCheckProtocol: string
    :param HealthCheckProtocol: 

      The protocol the load balancer uses when performing health checks on targets. The default is the HTTP protocol.

      

    
    :type HealthCheckPort: string
    :param HealthCheckPort: 

      The port the load balancer uses when performing health checks on targets. The default is ``traffic-port`` , which indicates the port on which each target receives traffic from the load balancer.

      

    
    :type HealthCheckPath: string
    :param HealthCheckPath: 

      The ping path that is the destination on the targets for health checks. The default is /.

      

    
    :type HealthCheckIntervalSeconds: integer
    :param HealthCheckIntervalSeconds: 

      The approximate amount of time, in seconds, between health checks of an individual target. The default is 30 seconds.

      

    
    :type HealthCheckTimeoutSeconds: integer
    :param HealthCheckTimeoutSeconds: 

      The amount of time, in seconds, during which no response from a target means a failed health check. The default is 5 seconds.

      

    
    :type HealthyThresholdCount: integer
    :param HealthyThresholdCount: 

      The number of consecutive health checks successes required before considering an unhealthy target healthy. The default is 5.

      

    
    :type UnhealthyThresholdCount: integer
    :param UnhealthyThresholdCount: 

      The number of consecutive health check failures required before considering a target unhealthy. The default is 2.

      

    
    :type Matcher: dict
    :param Matcher: 

      The HTTP codes to use when checking for a successful response from a target. The default is 200.

      

    
      - **HttpCode** *(string) --* **[REQUIRED]** 

        The HTTP codes. The default value is 200. You can specify multiple values (for example, "200,202") or a range of values (for example, "200-299").

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TargetGroups': [
                {
                    'TargetGroupArn': 'string',
                    'TargetGroupName': 'string',
                    'Protocol': 'HTTP'|'HTTPS',
                    'Port': 123,
                    'VpcId': 'string',
                    'HealthCheckProtocol': 'HTTP'|'HTTPS',
                    'HealthCheckPort': 'string',
                    'HealthCheckIntervalSeconds': 123,
                    'HealthCheckTimeoutSeconds': 123,
                    'HealthyThresholdCount': 123,
                    'UnhealthyThresholdCount': 123,
                    'HealthCheckPath': 'string',
                    'Matcher': {
                        'HttpCode': 'string'
                    },
                    'LoadBalancerArns': [
                        'string',
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of CreateTargetGroup.

        
        

        - **TargetGroups** *(list) --* 

          Information about the target group.

          
          

          - *(dict) --* 

            Information about a target group.

            
            

            - **TargetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) of the target group.

              
            

            - **TargetGroupName** *(string) --* 

              The name of the target group.

              
            

            - **Protocol** *(string) --* 

              The protocol to use for routing traffic to the targets.

              
            

            - **Port** *(integer) --* 

              The port on which the targets are listening.

              
            

            - **VpcId** *(string) --* 

              The ID of the VPC for the targets.

              
            

            - **HealthCheckProtocol** *(string) --* 

              The protocol to use to connect with the target.

              
            

            - **HealthCheckPort** *(string) --* 

              The port to use to connect with the target.

              
            

            - **HealthCheckIntervalSeconds** *(integer) --* 

              The approximate amount of time, in seconds, between health checks of an individual target.

              
            

            - **HealthCheckTimeoutSeconds** *(integer) --* 

              The amount of time, in seconds, during which no response means a failed health check.

              
            

            - **HealthyThresholdCount** *(integer) --* 

              The number of consecutive health checks successes required before considering an unhealthy target healthy.

              
            

            - **UnhealthyThresholdCount** *(integer) --* 

              The number of consecutive health check failures required before considering the target unhealthy.

              
            

            - **HealthCheckPath** *(string) --* 

              The destination for the health check request.

              
            

            - **Matcher** *(dict) --* 

              The HTTP codes to use when checking for a successful response from a target.

              
              

              - **HttpCode** *(string) --* 

                The HTTP codes. The default value is 200. You can specify multiple values (for example, "200,202") or a range of values (for example, "200-299").

                
          
            

            - **LoadBalancerArns** *(list) --* 

              The Amazon Resource Names (ARN) of the load balancers that route traffic to this target group.

              
              

              - *(string) --* 
          
        
      
    

  .. py:method:: delete_listener(**kwargs)

    

    Deletes the specified listener.

     

    Alternatively, your listener is deleted when you delete the load balancer it is attached to using  DeleteLoadBalancer .

    

    **Request Syntax** 
    ::

      response = client.delete_listener(
          ListenerArn='string'
      )
    :type ListenerArn: string
    :param ListenerArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the listener.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DeleteListener.

        
    

  .. py:method:: delete_load_balancer(**kwargs)

    

    Deletes the specified load balancer and its attached listeners.

     

    You can't delete a load balancer if deletion protection is enabled. If the load balancer does not exist or has already been deleted, the call succeeds.

     

    Deleting a load balancer does not affect its registered targets. For example, your EC2 instances continue to run and are still registered to their target groups. If you no longer need these EC2 instances, you can stop or terminate them.

    

    **Request Syntax** 
    ::

      response = client.delete_load_balancer(
          LoadBalancerArn='string'
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DeleteLoadBalancer.

        
    

  .. py:method:: delete_rule(**kwargs)

    

    Deletes the specified rule.

    

    **Request Syntax** 
    ::

      response = client.delete_rule(
          RuleArn='string'
      )
    :type RuleArn: string
    :param RuleArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the rule.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DeleteRule.

        
    

  .. py:method:: delete_target_group(**kwargs)

    

    Deletes the specified target group.

     

    You can delete a target group if it is not referenced by any actions. Deleting a target group also deletes any associated health checks.

    

    **Request Syntax** 
    ::

      response = client.delete_target_group(
          TargetGroupArn='string'
      )
    :type TargetGroupArn: string
    :param TargetGroupArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the target group.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DeleteTargetGroup.

        
    

  .. py:method:: deregister_targets(**kwargs)

    

    Deregisters the specified targets from the specified target group. After the targets are deregistered, they no longer receive traffic from the load balancer.

    

    **Request Syntax** 
    ::

      response = client.deregister_targets(
          TargetGroupArn='string',
          Targets=[
              {
                  'Id': 'string',
                  'Port': 123
              },
          ]
      )
    :type TargetGroupArn: string
    :param TargetGroupArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the target group.

      

    
    :type Targets: list
    :param Targets: **[REQUIRED]** 

      The targets.

      

    
      - *(dict) --* 

        Information about a target.

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          The ID of the target.

          

        
        - **Port** *(integer) --* 

          The port on which the target is listening.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DeregisterTargets.

        
    

  .. py:method:: describe_listeners(**kwargs)

    

    Describes the specified listeners or the listeners for the specified load balancer. You must specify either a load balancer or one or more listeners.

    

    **Request Syntax** 
    ::

      response = client.describe_listeners(
          LoadBalancerArn='string',
          ListenerArns=[
              'string',
          ],
          Marker='string',
          PageSize=123
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    :type ListenerArns: list
    :param ListenerArns: 

      The Amazon Resource Names (ARN) of the listeners.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      The marker for the next set of results. (You received this marker from a previous call.)

      

    
    :type PageSize: integer
    :param PageSize: 

      The maximum number of results to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Listeners': [
                {
                    'ListenerArn': 'string',
                    'LoadBalancerArn': 'string',
                    'Port': 123,
                    'Protocol': 'HTTP'|'HTTPS',
                    'Certificates': [
                        {
                            'CertificateArn': 'string'
                        },
                    ],
                    'SslPolicy': 'string',
                    'DefaultActions': [
                        {
                            'Type': 'forward',
                            'TargetGroupArn': 'string'
                        },
                    ]
                },
            ],
            'NextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeListeners.

        
        

        - **Listeners** *(list) --* 

          Information about the listeners.

          
          

          - *(dict) --* 

            Information about a listener.

            
            

            - **ListenerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the listener.

              
            

            - **LoadBalancerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the load balancer.

              
            

            - **Port** *(integer) --* 

              The port on which the load balancer is listening.

              
            

            - **Protocol** *(string) --* 

              The protocol for connections from clients to the load balancer.

              
            

            - **Certificates** *(list) --* 

              The SSL server certificate. You must provide a certificate if the protocol is HTTPS.

              
              

              - *(dict) --* 

                Information about an SSL server certificate deployed on a load balancer.

                
                

                - **CertificateArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the certificate.

                  
            
          
            

            - **SslPolicy** *(string) --* 

              The security policy that defines which ciphers and protocols are supported. The default is the current predefined security policy.

              
            

            - **DefaultActions** *(list) --* 

              The default actions for the listener.

              
              

              - *(dict) --* 

                Information about an action.

                
                

                - **Type** *(string) --* 

                  The type of action.

                  
                

                - **TargetGroupArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the target group.

                  
            
          
        
      
        

        - **NextMarker** *(string) --* 

          The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

          
    

  .. py:method:: describe_load_balancer_attributes(**kwargs)

    

    Describes the attributes for the specified load balancer.

    

    **Request Syntax** 
    ::

      response = client.describe_load_balancer_attributes(
          LoadBalancerArn='string'
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Attributes': [
                {
                    'Key': 'string',
                    'Value': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeLoadBalancerAttributes.

        
        

        - **Attributes** *(list) --* 

          Information about the load balancer attributes.

          
          

          - *(dict) --* 

            Information about a load balancer attribute.

            
            

            - **Key** *(string) --* 

              The name of the attribute.

               

               
              * ``access_logs.s3.enabled`` - Indicates whether access logs stored in Amazon S3 are enabled. 
               
              * ``access_logs.s3.bucket`` - The name of the S3 bucket for the access logs. This attribute is required if access logs in Amazon S3 are enabled. The bucket must exist in the same region as the load balancer and have a bucket policy that grants Elastic Load Balancing permission to write to the bucket. 
               
              * ``access_logs.s3.prefix`` - The prefix for the location in the S3 bucket. If you don't specify a prefix, the access logs are stored in the root of the bucket. 
               
              * ``deletion_protection.enabled`` - Indicates whether deletion protection is enabled. 
               
              * ``idle_timeout.timeout_seconds`` - The idle timeout value, in seconds. The valid range is 1-3600. The default is 60 seconds. 
               

              
            

            - **Value** *(string) --* 

              The value of the attribute.

              
        
      
    

  .. py:method:: describe_load_balancers(**kwargs)

    

    Describes the specified Application load balancers or all of your Application load balancers.

     

    To describe the listeners for a load balancer, use  DescribeListeners . To describe the attributes for a load balancer, use  DescribeLoadBalancerAttributes .

    

    **Request Syntax** 
    ::

      response = client.describe_load_balancers(
          LoadBalancerArns=[
              'string',
          ],
          Names=[
              'string',
          ],
          Marker='string',
          PageSize=123
      )
    :type LoadBalancerArns: list
    :param LoadBalancerArns: 

      The Amazon Resource Names (ARN) of the load balancers.

      

    
      - *(string) --* 

      
  
    :type Names: list
    :param Names: 

      The names of the load balancers.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      The marker for the next set of results. (You received this marker from a previous call.)

      

    
    :type PageSize: integer
    :param PageSize: 

      The maximum number of results to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'LoadBalancers': [
                {
                    'LoadBalancerArn': 'string',
                    'DNSName': 'string',
                    'CanonicalHostedZoneId': 'string',
                    'CreatedTime': datetime(2015, 1, 1),
                    'LoadBalancerName': 'string',
                    'Scheme': 'internet-facing'|'internal',
                    'VpcId': 'string',
                    'State': {
                        'Code': 'active'|'provisioning'|'failed',
                        'Reason': 'string'
                    },
                    'Type': 'application',
                    'AvailabilityZones': [
                        {
                            'ZoneName': 'string',
                            'SubnetId': 'string'
                        },
                    ],
                    'SecurityGroups': [
                        'string',
                    ]
                },
            ],
            'NextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeLoadBalancers.

        
        

        - **LoadBalancers** *(list) --* 

          Information about the load balancers.

          
          

          - *(dict) --* 

            Information about a load balancer.

            
            

            - **LoadBalancerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the load balancer.

              
            

            - **DNSName** *(string) --* 

              The public DNS name of the load balancer.

              
            

            - **CanonicalHostedZoneId** *(string) --* 

              The ID of the Amazon Route 53 hosted zone associated with the load balancer.

              
            

            - **CreatedTime** *(datetime) --* 

              The date and time the load balancer was created.

              
            

            - **LoadBalancerName** *(string) --* 

              The name of the load balancer.

              
            

            - **Scheme** *(string) --* 

              The nodes of an Internet-facing load balancer have public IP addresses. The DNS name of an Internet-facing load balancer is publicly resolvable to the public IP addresses of the nodes. Therefore, Internet-facing load balancers can route requests from clients over the Internet.

               

              The nodes of an internal load balancer have only private IP addresses. The DNS name of an internal load balancer is publicly resolvable to the private IP addresses of the nodes. Therefore, internal load balancers can only route requests from clients with access to the VPC for the load balancer.

              
            

            - **VpcId** *(string) --* 

              The ID of the VPC for the load balancer.

              
            

            - **State** *(dict) --* 

              The state of the load balancer.

              
              

              - **Code** *(string) --* 

                The state code. The initial state of the load balancer is ``provisioning`` . After the load balancer is fully set up and ready to route traffic, its state is ``active`` . If the load balancer could not be set up, its state is ``failed`` .

                
              

              - **Reason** *(string) --* 

                A description of the state.

                
          
            

            - **Type** *(string) --* 

              The type of load balancer.

              
            

            - **AvailabilityZones** *(list) --* 

              The Availability Zones for the load balancer.

              
              

              - *(dict) --* 

                Information about an Availability Zone.

                
                

                - **ZoneName** *(string) --* 

                  The name of the Availability Zone.

                  
                

                - **SubnetId** *(string) --* 

                  The ID of the subnet.

                  
            
          
            

            - **SecurityGroups** *(list) --* 

              The IDs of the security groups for the load balancer.

              
              

              - *(string) --* 
          
        
      
        

        - **NextMarker** *(string) --* 

          The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

          
    

  .. py:method:: describe_rules(**kwargs)

    

    Describes the specified rules or the rules for the specified listener. You must specify either a listener or one or more rules.

    

    **Request Syntax** 
    ::

      response = client.describe_rules(
          ListenerArn='string',
          RuleArns=[
              'string',
          ]
      )
    :type ListenerArn: string
    :param ListenerArn: 

      The Amazon Resource Name (ARN) of the listener.

      

    
    :type RuleArns: list
    :param RuleArns: 

      The Amazon Resource Names (ARN) of the rules.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Rules': [
                {
                    'RuleArn': 'string',
                    'Priority': 'string',
                    'Conditions': [
                        {
                            'Field': 'string',
                            'Values': [
                                'string',
                            ]
                        },
                    ],
                    'Actions': [
                        {
                            'Type': 'forward',
                            'TargetGroupArn': 'string'
                        },
                    ],
                    'IsDefault': True|False
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeRules.

        
        

        - **Rules** *(list) --* 

          Information about the rules.

          
          

          - *(dict) --* 

            Information about a rule.

            
            

            - **RuleArn** *(string) --* 

              The Amazon Resource Name (ARN) of the rule.

              
            

            - **Priority** *(string) --* 

              The priority.

              
            

            - **Conditions** *(list) --* 

              The conditions.

              
              

              - *(dict) --* 

                Information about a condition for a rule.

                
                

                - **Field** *(string) --* 

                  The name of the field. The possible value is ``path-pattern`` .

                  
                

                - **Values** *(list) --* 

                  The values for the field.

                   

                  A path pattern is case sensitive, can be up to 255 characters in length, and can contain any of the following characters:

                   

                   
                  * A-Z, a-z, 0-9 
                   
                  * _ - . $ / ~ " ' @ : + 
                   
                  * amp; (using amp;amp;) 
                   
                  * * (matches 0 or more characters) 
                   
                  * ? (matches exactly 1 character) 
                   

                  
                  

                  - *(string) --* 
              
            
          
            

            - **Actions** *(list) --* 

              The actions.

              
              

              - *(dict) --* 

                Information about an action.

                
                

                - **Type** *(string) --* 

                  The type of action.

                  
                

                - **TargetGroupArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the target group.

                  
            
          
            

            - **IsDefault** *(boolean) --* 

              Indicates whether this is the default rule.

              
        
      
    

  .. py:method:: describe_ssl_policies(**kwargs)

    

    Describes the specified policies or all policies used for SSL negotiation.

     

    Note that the only supported policy at this time is ELBSecurityPolicy-2015-05.

    

    **Request Syntax** 
    ::

      response = client.describe_ssl_policies(
          Names=[
              'string',
          ],
          Marker='string',
          PageSize=123
      )
    :type Names: list
    :param Names: 

      The names of the policies.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      The marker for the next set of results. (You received this marker from a previous call.)

      

    
    :type PageSize: integer
    :param PageSize: 

      The maximum number of results to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SslPolicies': [
                {
                    'SslProtocols': [
                        'string',
                    ],
                    'Ciphers': [
                        {
                            'Name': 'string',
                            'Priority': 123
                        },
                    ],
                    'Name': 'string'
                },
            ],
            'NextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeSSLPolicies.

        
        

        - **SslPolicies** *(list) --* 

          Information about the policies.

          
          

          - *(dict) --* 

            Information about a policy used for SSL negotiation.

            
            

            - **SslProtocols** *(list) --* 

              The protocols.

              
              

              - *(string) --* 
          
            

            - **Ciphers** *(list) --* 

              The ciphers.

              
              

              - *(dict) --* 

                Information about a cipher used in a policy.

                
                

                - **Name** *(string) --* 

                  The name of the cipher.

                  
                

                - **Priority** *(integer) --* 

                  The priority of the cipher.

                  
            
          
            

            - **Name** *(string) --* 

              The name of the policy.

              
        
      
        

        - **NextMarker** *(string) --* 

          The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

          
    

  .. py:method:: describe_tags(**kwargs)

    

    Describes the tags for the specified resources.

    

    **Request Syntax** 
    ::

      response = client.describe_tags(
          ResourceArns=[
              'string',
          ]
      )
    :type ResourceArns: list
    :param ResourceArns: **[REQUIRED]** 

      The Amazon Resource Names (ARN) of the resources.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TagDescriptions': [
                {
                    'ResourceArn': 'string',
                    'Tags': [
                        {
                            'Key': 'string',
                            'Value': 'string'
                        },
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeTags.

        
        

        - **TagDescriptions** *(list) --* 

          Information about the tags.

          
          

          - *(dict) --* 

            The tags associated with a resource.

            
            

            - **ResourceArn** *(string) --* 

              The Amazon Resource Name (ARN) of the resource.

              
            

            - **Tags** *(list) --* 

              Information about the tags.

              
              

              - *(dict) --* 

                Information about a tag.

                
                

                - **Key** *(string) --* 

                  The key of the tag.

                  
                

                - **Value** *(string) --* 

                  The value of the tag.

                  
            
          
        
      
    

  .. py:method:: describe_target_group_attributes(**kwargs)

    

    Describes the attributes for the specified target group.

    

    **Request Syntax** 
    ::

      response = client.describe_target_group_attributes(
          TargetGroupArn='string'
      )
    :type TargetGroupArn: string
    :param TargetGroupArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the target group.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Attributes': [
                {
                    'Key': 'string',
                    'Value': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeTargetGroupAttributes.

        
        

        - **Attributes** *(list) --* 

          Information about the target group attributes

          
          

          - *(dict) --* 

            Information about a target group attribute.

            
            

            - **Key** *(string) --* 

              The name of the attribute.

               

               
              * ``deregistration_delay.timeout_seconds`` - The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from ``draining`` to ``unused`` . The range is 0-3600 seconds. The default value is 300 seconds. 
               
              * ``stickiness.enabled`` - Indicates whether sticky sessions are enabled. 
               
              * ``stickiness.type`` - The type of sticky sessions. The possible value is ``lb_cookie`` . 
               
              * ``stickiness.lb_cookie.duration_seconds`` - The time period, in seconds, during which requests from a client should be routed to the same target. After this time period expires, the load balancer-generated cookie is considered stale. The range is 1 second to 1 week (604800 seconds). The default value is 1 day (86400 seconds). 
               

              
            

            - **Value** *(string) --* 

              The value of the attribute.

              
        
      
    

  .. py:method:: describe_target_groups(**kwargs)

    

    Describes the specified target groups or all of your target groups. By default, all target groups are described. Alternatively, you can specify one of the following to filter the results: the ARN of the load balancer, the names of one or more target groups, or the ARNs of one or more target groups.

     

    To describe the targets for a target group, use  DescribeTargetHealth . To describe the attributes of a target group, use  DescribeTargetGroupAttributes .

    

    **Request Syntax** 
    ::

      response = client.describe_target_groups(
          LoadBalancerArn='string',
          TargetGroupArns=[
              'string',
          ],
          Names=[
              'string',
          ],
          Marker='string',
          PageSize=123
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    :type TargetGroupArns: list
    :param TargetGroupArns: 

      The Amazon Resource Names (ARN) of the target groups.

      

    
      - *(string) --* 

      
  
    :type Names: list
    :param Names: 

      The names of the target groups.

      

    
      - *(string) --* 

      
  
    :type Marker: string
    :param Marker: 

      The marker for the next set of results. (You received this marker from a previous call.)

      

    
    :type PageSize: integer
    :param PageSize: 

      The maximum number of results to return with this call.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TargetGroups': [
                {
                    'TargetGroupArn': 'string',
                    'TargetGroupName': 'string',
                    'Protocol': 'HTTP'|'HTTPS',
                    'Port': 123,
                    'VpcId': 'string',
                    'HealthCheckProtocol': 'HTTP'|'HTTPS',
                    'HealthCheckPort': 'string',
                    'HealthCheckIntervalSeconds': 123,
                    'HealthCheckTimeoutSeconds': 123,
                    'HealthyThresholdCount': 123,
                    'UnhealthyThresholdCount': 123,
                    'HealthCheckPath': 'string',
                    'Matcher': {
                        'HttpCode': 'string'
                    },
                    'LoadBalancerArns': [
                        'string',
                    ]
                },
            ],
            'NextMarker': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeTargetGroups.

        
        

        - **TargetGroups** *(list) --* 

          Information about the target groups.

          
          

          - *(dict) --* 

            Information about a target group.

            
            

            - **TargetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) of the target group.

              
            

            - **TargetGroupName** *(string) --* 

              The name of the target group.

              
            

            - **Protocol** *(string) --* 

              The protocol to use for routing traffic to the targets.

              
            

            - **Port** *(integer) --* 

              The port on which the targets are listening.

              
            

            - **VpcId** *(string) --* 

              The ID of the VPC for the targets.

              
            

            - **HealthCheckProtocol** *(string) --* 

              The protocol to use to connect with the target.

              
            

            - **HealthCheckPort** *(string) --* 

              The port to use to connect with the target.

              
            

            - **HealthCheckIntervalSeconds** *(integer) --* 

              The approximate amount of time, in seconds, between health checks of an individual target.

              
            

            - **HealthCheckTimeoutSeconds** *(integer) --* 

              The amount of time, in seconds, during which no response means a failed health check.

              
            

            - **HealthyThresholdCount** *(integer) --* 

              The number of consecutive health checks successes required before considering an unhealthy target healthy.

              
            

            - **UnhealthyThresholdCount** *(integer) --* 

              The number of consecutive health check failures required before considering the target unhealthy.

              
            

            - **HealthCheckPath** *(string) --* 

              The destination for the health check request.

              
            

            - **Matcher** *(dict) --* 

              The HTTP codes to use when checking for a successful response from a target.

              
              

              - **HttpCode** *(string) --* 

                The HTTP codes. The default value is 200. You can specify multiple values (for example, "200,202") or a range of values (for example, "200-299").

                
          
            

            - **LoadBalancerArns** *(list) --* 

              The Amazon Resource Names (ARN) of the load balancers that route traffic to this target group.

              
              

              - *(string) --* 
          
        
      
        

        - **NextMarker** *(string) --* 

          The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

          
    

  .. py:method:: describe_target_health(**kwargs)

    

    Describes the health of the specified targets or all of your targets.

    

    **Request Syntax** 
    ::

      response = client.describe_target_health(
          TargetGroupArn='string',
          Targets=[
              {
                  'Id': 'string',
                  'Port': 123
              },
          ]
      )
    :type TargetGroupArn: string
    :param TargetGroupArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the target group.

      

    
    :type Targets: list
    :param Targets: 

      The targets.

      

    
      - *(dict) --* 

        Information about a target.

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          The ID of the target.

          

        
        - **Port** *(integer) --* 

          The port on which the target is listening.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TargetHealthDescriptions': [
                {
                    'Target': {
                        'Id': 'string',
                        'Port': 123
                    },
                    'HealthCheckPort': 'string',
                    'TargetHealth': {
                        'State': 'initial'|'healthy'|'unhealthy'|'unused'|'draining',
                        'Reason': 'Elb.RegistrationInProgress'|'Elb.InitialHealthChecking'|'Target.ResponseCodeMismatch'|'Target.Timeout'|'Target.FailedHealthChecks'|'Target.NotRegistered'|'Target.NotInUse'|'Target.DeregistrationInProgress'|'Target.InvalidState'|'Elb.InternalError',
                        'Description': 'string'
                    }
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeTargetHealth.

        
        

        - **TargetHealthDescriptions** *(list) --* 

          Information about the health of the targets.

          
          

          - *(dict) --* 

            Information about the health of a target.

            
            

            - **Target** *(dict) --* 

              The description of the target.

              
              

              - **Id** *(string) --* 

                The ID of the target.

                
              

              - **Port** *(integer) --* 

                The port on which the target is listening.

                
          
            

            - **HealthCheckPort** *(string) --* 

              The port to use to connect with the target.

              
            

            - **TargetHealth** *(dict) --* 

              The health information for the target.

              
              

              - **State** *(string) --* 

                The state of the target.

                
              

              - **Reason** *(string) --* 

                The reason code. If the target state is ``healthy`` , a reason code is not provided.

                 

                If the target state is ``initial`` , the reason code can be one of the following values:

                 

                 
                * ``Elb.RegistrationInProgress`` - The target is in the process of being registered with the load balancer. 
                 
                * ``Elb.InitialHealthChecking`` - The load balancer is still sending the target the minimum number of health checks required to determine its health status. 
                 

                 

                If the target state is ``unhealthy`` , the reason code can be one of the following values:

                 

                 
                * ``Target.ResponseCodeMismatch`` - The health checks did not return an expected HTTP code. 
                 
                * ``Target.Timeout`` - The health check requests timed out. 
                 
                * ``Target.FailedHealthChecks`` - The health checks failed because the connection to the target timed out, the target response was malformed, or the target failed the health check for an unknown reason. 
                 
                * ``Elb.InternalError`` - The health checks failed due to an internal error. 
                 

                 

                If the target state is ``unused`` , the reason code can be one of the following values:

                 

                 
                * ``Target.NotRegistered`` - The target is not registered with the target group. 
                 
                * ``Target.NotInUse`` - The target group is not used by any load balancer or the target is in an Availability Zone that is not enabled for its load balancer. 
                 
                * ``Target.InvalidState`` - The target is in the stopped or terminated state. 
                 

                 

                If the target state is ``draining`` , the reason code can be the following value:

                 

                 
                * ``Target.DeregistrationInProgress`` - The target is in the process of being deregistered and the deregistration delay period has not expired. 
                 

                
              

              - **Description** *(string) --* 

                A description of the target health that provides additional details. If the state is ``healthy`` , a description is not provided.

                
          
        
      
    

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

        


  .. py:method:: modify_listener(**kwargs)

    

    Modifies the specified properties of the specified listener.

     

    Any properties that you do not specify retain their current values. However, changing the protocol from HTTPS to HTTP removes the security policy and SSL certificate properties. If you change the protocol from HTTP to HTTPS, you must add the security policy.

    

    **Request Syntax** 
    ::

      response = client.modify_listener(
          ListenerArn='string',
          Port=123,
          Protocol='HTTP'|'HTTPS',
          SslPolicy='string',
          Certificates=[
              {
                  'CertificateArn': 'string'
              },
          ],
          DefaultActions=[
              {
                  'Type': 'forward',
                  'TargetGroupArn': 'string'
              },
          ]
      )
    :type ListenerArn: string
    :param ListenerArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the listener.

      

    
    :type Port: integer
    :param Port: 

      The port for connections from clients to the load balancer.

      

    
    :type Protocol: string
    :param Protocol: 

      The protocol for connections from clients to the load balancer.

      

    
    :type SslPolicy: string
    :param SslPolicy: 

      The security policy that defines which ciphers and protocols are supported.

      

    
    :type Certificates: list
    :param Certificates: 

      The SSL server certificate.

      

    
      - *(dict) --* 

        Information about an SSL server certificate deployed on a load balancer.

        

      
        - **CertificateArn** *(string) --* 

          The Amazon Resource Name (ARN) of the certificate.

          

        
      
  
    :type DefaultActions: list
    :param DefaultActions: 

      The default actions.

      

    
      - *(dict) --* 

        Information about an action.

        

      
        - **Type** *(string) --* **[REQUIRED]** 

          The type of action.

          

        
        - **TargetGroupArn** *(string) --* **[REQUIRED]** 

          The Amazon Resource Name (ARN) of the target group.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Listeners': [
                {
                    'ListenerArn': 'string',
                    'LoadBalancerArn': 'string',
                    'Port': 123,
                    'Protocol': 'HTTP'|'HTTPS',
                    'Certificates': [
                        {
                            'CertificateArn': 'string'
                        },
                    ],
                    'SslPolicy': 'string',
                    'DefaultActions': [
                        {
                            'Type': 'forward',
                            'TargetGroupArn': 'string'
                        },
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of ModifyListener.

        
        

        - **Listeners** *(list) --* 

          Information about the modified listeners.

          
          

          - *(dict) --* 

            Information about a listener.

            
            

            - **ListenerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the listener.

              
            

            - **LoadBalancerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the load balancer.

              
            

            - **Port** *(integer) --* 

              The port on which the load balancer is listening.

              
            

            - **Protocol** *(string) --* 

              The protocol for connections from clients to the load balancer.

              
            

            - **Certificates** *(list) --* 

              The SSL server certificate. You must provide a certificate if the protocol is HTTPS.

              
              

              - *(dict) --* 

                Information about an SSL server certificate deployed on a load balancer.

                
                

                - **CertificateArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the certificate.

                  
            
          
            

            - **SslPolicy** *(string) --* 

              The security policy that defines which ciphers and protocols are supported. The default is the current predefined security policy.

              
            

            - **DefaultActions** *(list) --* 

              The default actions for the listener.

              
              

              - *(dict) --* 

                Information about an action.

                
                

                - **Type** *(string) --* 

                  The type of action.

                  
                

                - **TargetGroupArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the target group.

                  
            
          
        
      
    

  .. py:method:: modify_load_balancer_attributes(**kwargs)

    

    Modifies the specified attributes of the specified load balancer.

     

    If any of the specified attributes can't be modified as requested, the call fails. Any existing attributes that you do not modify retain their current values.

    

    **Request Syntax** 
    ::

      response = client.modify_load_balancer_attributes(
          LoadBalancerArn='string',
          Attributes=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    :type Attributes: list
    :param Attributes: **[REQUIRED]** 

      The load balancer attributes.

      

    
      - *(dict) --* 

        Information about a load balancer attribute.

        

      
        - **Key** *(string) --* 

          The name of the attribute.

           

           
          * ``access_logs.s3.enabled`` - Indicates whether access logs stored in Amazon S3 are enabled. 
           
          * ``access_logs.s3.bucket`` - The name of the S3 bucket for the access logs. This attribute is required if access logs in Amazon S3 are enabled. The bucket must exist in the same region as the load balancer and have a bucket policy that grants Elastic Load Balancing permission to write to the bucket. 
           
          * ``access_logs.s3.prefix`` - The prefix for the location in the S3 bucket. If you don't specify a prefix, the access logs are stored in the root of the bucket. 
           
          * ``deletion_protection.enabled`` - Indicates whether deletion protection is enabled. 
           
          * ``idle_timeout.timeout_seconds`` - The idle timeout value, in seconds. The valid range is 1-3600. The default is 60 seconds. 
           

          

        
        - **Value** *(string) --* 

          The value of the attribute.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Attributes': [
                {
                    'Key': 'string',
                    'Value': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of ModifyLoadBalancerAttributes.

        
        

        - **Attributes** *(list) --* 

          Information about the load balancer attributes.

          
          

          - *(dict) --* 

            Information about a load balancer attribute.

            
            

            - **Key** *(string) --* 

              The name of the attribute.

               

               
              * ``access_logs.s3.enabled`` - Indicates whether access logs stored in Amazon S3 are enabled. 
               
              * ``access_logs.s3.bucket`` - The name of the S3 bucket for the access logs. This attribute is required if access logs in Amazon S3 are enabled. The bucket must exist in the same region as the load balancer and have a bucket policy that grants Elastic Load Balancing permission to write to the bucket. 
               
              * ``access_logs.s3.prefix`` - The prefix for the location in the S3 bucket. If you don't specify a prefix, the access logs are stored in the root of the bucket. 
               
              * ``deletion_protection.enabled`` - Indicates whether deletion protection is enabled. 
               
              * ``idle_timeout.timeout_seconds`` - The idle timeout value, in seconds. The valid range is 1-3600. The default is 60 seconds. 
               

              
            

            - **Value** *(string) --* 

              The value of the attribute.

              
        
      
    

  .. py:method:: modify_rule(**kwargs)

    

    Modifies the specified rule.

     

    Any existing properties that you do not modify retain their current values.

     

    To modify the default action, use  ModifyListener .

    

    **Request Syntax** 
    ::

      response = client.modify_rule(
          RuleArn='string',
          Conditions=[
              {
                  'Field': 'string',
                  'Values': [
                      'string',
                  ]
              },
          ],
          Actions=[
              {
                  'Type': 'forward',
                  'TargetGroupArn': 'string'
              },
          ]
      )
    :type RuleArn: string
    :param RuleArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the rule.

      

    
    :type Conditions: list
    :param Conditions: 

      The conditions.

      

    
      - *(dict) --* 

        Information about a condition for a rule.

        

      
        - **Field** *(string) --* 

          The name of the field. The possible value is ``path-pattern`` .

          

        
        - **Values** *(list) --* 

          The values for the field.

           

          A path pattern is case sensitive, can be up to 255 characters in length, and can contain any of the following characters:

           

           
          * A-Z, a-z, 0-9 
           
          * _ - . $ / ~ " ' @ : + 
           
          * amp; (using amp;amp;) 
           
          * * (matches 0 or more characters) 
           
          * ? (matches exactly 1 character) 
           

          

        
          - *(string) --* 

          
      
      
  
    :type Actions: list
    :param Actions: 

      The actions.

      

    
      - *(dict) --* 

        Information about an action.

        

      
        - **Type** *(string) --* **[REQUIRED]** 

          The type of action.

          

        
        - **TargetGroupArn** *(string) --* **[REQUIRED]** 

          The Amazon Resource Name (ARN) of the target group.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Rules': [
                {
                    'RuleArn': 'string',
                    'Priority': 'string',
                    'Conditions': [
                        {
                            'Field': 'string',
                            'Values': [
                                'string',
                            ]
                        },
                    ],
                    'Actions': [
                        {
                            'Type': 'forward',
                            'TargetGroupArn': 'string'
                        },
                    ],
                    'IsDefault': True|False
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of ModifyRules.

        
        

        - **Rules** *(list) --* 

          Information about the rule.

          
          

          - *(dict) --* 

            Information about a rule.

            
            

            - **RuleArn** *(string) --* 

              The Amazon Resource Name (ARN) of the rule.

              
            

            - **Priority** *(string) --* 

              The priority.

              
            

            - **Conditions** *(list) --* 

              The conditions.

              
              

              - *(dict) --* 

                Information about a condition for a rule.

                
                

                - **Field** *(string) --* 

                  The name of the field. The possible value is ``path-pattern`` .

                  
                

                - **Values** *(list) --* 

                  The values for the field.

                   

                  A path pattern is case sensitive, can be up to 255 characters in length, and can contain any of the following characters:

                   

                   
                  * A-Z, a-z, 0-9 
                   
                  * _ - . $ / ~ " ' @ : + 
                   
                  * amp; (using amp;amp;) 
                   
                  * * (matches 0 or more characters) 
                   
                  * ? (matches exactly 1 character) 
                   

                  
                  

                  - *(string) --* 
              
            
          
            

            - **Actions** *(list) --* 

              The actions.

              
              

              - *(dict) --* 

                Information about an action.

                
                

                - **Type** *(string) --* 

                  The type of action.

                  
                

                - **TargetGroupArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the target group.

                  
            
          
            

            - **IsDefault** *(boolean) --* 

              Indicates whether this is the default rule.

              
        
      
    

  .. py:method:: modify_target_group(**kwargs)

    

    Modifies the health checks used when evaluating the health state of the targets in the specified target group.

     

    To monitor the health of the targets, use  DescribeTargetHealth .

    

    **Request Syntax** 
    ::

      response = client.modify_target_group(
          TargetGroupArn='string',
          HealthCheckProtocol='HTTP'|'HTTPS',
          HealthCheckPort='string',
          HealthCheckPath='string',
          HealthCheckIntervalSeconds=123,
          HealthCheckTimeoutSeconds=123,
          HealthyThresholdCount=123,
          UnhealthyThresholdCount=123,
          Matcher={
              'HttpCode': 'string'
          }
      )
    :type TargetGroupArn: string
    :param TargetGroupArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the target group.

      

    
    :type HealthCheckProtocol: string
    :param HealthCheckProtocol: 

      The protocol to use to connect with the target.

      

    
    :type HealthCheckPort: string
    :param HealthCheckPort: 

      The port to use to connect with the target.

      

    
    :type HealthCheckPath: string
    :param HealthCheckPath: 

      The ping path that is the destination for the health check request.

      

    
    :type HealthCheckIntervalSeconds: integer
    :param HealthCheckIntervalSeconds: 

      The approximate amount of time, in seconds, between health checks of an individual target.

      

    
    :type HealthCheckTimeoutSeconds: integer
    :param HealthCheckTimeoutSeconds: 

      The amount of time, in seconds, during which no response means a failed health check.

      

    
    :type HealthyThresholdCount: integer
    :param HealthyThresholdCount: 

      The number of consecutive health checks successes required before considering an unhealthy target healthy.

      

    
    :type UnhealthyThresholdCount: integer
    :param UnhealthyThresholdCount: 

      The number of consecutive health check failures required before considering the target unhealthy.

      

    
    :type Matcher: dict
    :param Matcher: 

      The HTTP codes to use when checking for a successful response from a target.

      

    
      - **HttpCode** *(string) --* **[REQUIRED]** 

        The HTTP codes. The default value is 200. You can specify multiple values (for example, "200,202") or a range of values (for example, "200-299").

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'TargetGroups': [
                {
                    'TargetGroupArn': 'string',
                    'TargetGroupName': 'string',
                    'Protocol': 'HTTP'|'HTTPS',
                    'Port': 123,
                    'VpcId': 'string',
                    'HealthCheckProtocol': 'HTTP'|'HTTPS',
                    'HealthCheckPort': 'string',
                    'HealthCheckIntervalSeconds': 123,
                    'HealthCheckTimeoutSeconds': 123,
                    'HealthyThresholdCount': 123,
                    'UnhealthyThresholdCount': 123,
                    'HealthCheckPath': 'string',
                    'Matcher': {
                        'HttpCode': 'string'
                    },
                    'LoadBalancerArns': [
                        'string',
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of ModifyTargetGroup.

        
        

        - **TargetGroups** *(list) --* 

          Information about the target group.

          
          

          - *(dict) --* 

            Information about a target group.

            
            

            - **TargetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) of the target group.

              
            

            - **TargetGroupName** *(string) --* 

              The name of the target group.

              
            

            - **Protocol** *(string) --* 

              The protocol to use for routing traffic to the targets.

              
            

            - **Port** *(integer) --* 

              The port on which the targets are listening.

              
            

            - **VpcId** *(string) --* 

              The ID of the VPC for the targets.

              
            

            - **HealthCheckProtocol** *(string) --* 

              The protocol to use to connect with the target.

              
            

            - **HealthCheckPort** *(string) --* 

              The port to use to connect with the target.

              
            

            - **HealthCheckIntervalSeconds** *(integer) --* 

              The approximate amount of time, in seconds, between health checks of an individual target.

              
            

            - **HealthCheckTimeoutSeconds** *(integer) --* 

              The amount of time, in seconds, during which no response means a failed health check.

              
            

            - **HealthyThresholdCount** *(integer) --* 

              The number of consecutive health checks successes required before considering an unhealthy target healthy.

              
            

            - **UnhealthyThresholdCount** *(integer) --* 

              The number of consecutive health check failures required before considering the target unhealthy.

              
            

            - **HealthCheckPath** *(string) --* 

              The destination for the health check request.

              
            

            - **Matcher** *(dict) --* 

              The HTTP codes to use when checking for a successful response from a target.

              
              

              - **HttpCode** *(string) --* 

                The HTTP codes. The default value is 200. You can specify multiple values (for example, "200,202") or a range of values (for example, "200-299").

                
          
            

            - **LoadBalancerArns** *(list) --* 

              The Amazon Resource Names (ARN) of the load balancers that route traffic to this target group.

              
              

              - *(string) --* 
          
        
      
    

  .. py:method:: modify_target_group_attributes(**kwargs)

    

    Modifies the specified attributes of the specified target group.

    

    **Request Syntax** 
    ::

      response = client.modify_target_group_attributes(
          TargetGroupArn='string',
          Attributes=[
              {
                  'Key': 'string',
                  'Value': 'string'
              },
          ]
      )
    :type TargetGroupArn: string
    :param TargetGroupArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the target group.

      

    
    :type Attributes: list
    :param Attributes: **[REQUIRED]** 

      The attributes.

      

    
      - *(dict) --* 

        Information about a target group attribute.

        

      
        - **Key** *(string) --* 

          The name of the attribute.

           

           
          * ``deregistration_delay.timeout_seconds`` - The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from ``draining`` to ``unused`` . The range is 0-3600 seconds. The default value is 300 seconds. 
           
          * ``stickiness.enabled`` - Indicates whether sticky sessions are enabled. 
           
          * ``stickiness.type`` - The type of sticky sessions. The possible value is ``lb_cookie`` . 
           
          * ``stickiness.lb_cookie.duration_seconds`` - The time period, in seconds, during which requests from a client should be routed to the same target. After this time period expires, the load balancer-generated cookie is considered stale. The range is 1 second to 1 week (604800 seconds). The default value is 1 day (86400 seconds). 
           

          

        
        - **Value** *(string) --* 

          The value of the attribute.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Attributes': [
                {
                    'Key': 'string',
                    'Value': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of ModifyTargetGroupAttributes.

        
        

        - **Attributes** *(list) --* 

          Information about the attributes.

          
          

          - *(dict) --* 

            Information about a target group attribute.

            
            

            - **Key** *(string) --* 

              The name of the attribute.

               

               
              * ``deregistration_delay.timeout_seconds`` - The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from ``draining`` to ``unused`` . The range is 0-3600 seconds. The default value is 300 seconds. 
               
              * ``stickiness.enabled`` - Indicates whether sticky sessions are enabled. 
               
              * ``stickiness.type`` - The type of sticky sessions. The possible value is ``lb_cookie`` . 
               
              * ``stickiness.lb_cookie.duration_seconds`` - The time period, in seconds, during which requests from a client should be routed to the same target. After this time period expires, the load balancer-generated cookie is considered stale. The range is 1 second to 1 week (604800 seconds). The default value is 1 day (86400 seconds). 
               

              
            

            - **Value** *(string) --* 

              The value of the attribute.

              
        
      
    

  .. py:method:: register_targets(**kwargs)

    

    Registers the specified targets with the specified target group.

     

    The target must be in the virtual private cloud (VPC) that you specified for the target group.

     

    To remove a target from a target group, use  DeregisterTargets .

    

    **Request Syntax** 
    ::

      response = client.register_targets(
          TargetGroupArn='string',
          Targets=[
              {
                  'Id': 'string',
                  'Port': 123
              },
          ]
      )
    :type TargetGroupArn: string
    :param TargetGroupArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the target group.

      

    
    :type Targets: list
    :param Targets: **[REQUIRED]** 

      The targets.

      

    
      - *(dict) --* 

        Information about a target.

        

      
        - **Id** *(string) --* **[REQUIRED]** 

          The ID of the target.

          

        
        - **Port** *(integer) --* 

          The port on which the target is listening.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of RegisterTargets.

        
    

  .. py:method:: remove_tags(**kwargs)

    

    Removes the specified tags from the specified resource.

     

    To list the current tags for your resources, use  DescribeTags .

    

    **Request Syntax** 
    ::

      response = client.remove_tags(
          ResourceArns=[
              'string',
          ],
          TagKeys=[
              'string',
          ]
      )
    :type ResourceArns: list
    :param ResourceArns: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the resource.

      

    
      - *(string) --* 

      
  
    :type TagKeys: list
    :param TagKeys: **[REQUIRED]** 

      The tag keys for the tags to remove.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {}
        
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of RemoveTags.

        
    

  .. py:method:: set_rule_priorities(**kwargs)

    

    Sets the priorities of the specified rules.

     

    You can reorder the rules as long as there are no priority conflicts in the new order. Any existing rules that you do not specify retain their current priority.

    

    **Request Syntax** 
    ::

      response = client.set_rule_priorities(
          RulePriorities=[
              {
                  'RuleArn': 'string',
                  'Priority': 123
              },
          ]
      )
    :type RulePriorities: list
    :param RulePriorities: **[REQUIRED]** 

      The rule priorities.

      

    
      - *(dict) --* 

        Information about the priorities for the rules for a listener.

        

      
        - **RuleArn** *(string) --* 

          The Amazon Resource Name (ARN) of the rule.

          

        
        - **Priority** *(integer) --* 

          The rule priority.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'Rules': [
                {
                    'RuleArn': 'string',
                    'Priority': 'string',
                    'Conditions': [
                        {
                            'Field': 'string',
                            'Values': [
                                'string',
                            ]
                        },
                    ],
                    'Actions': [
                        {
                            'Type': 'forward',
                            'TargetGroupArn': 'string'
                        },
                    ],
                    'IsDefault': True|False
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of SetRulePriorities.

        
        

        - **Rules** *(list) --* 

          Information about the rules.

          
          

          - *(dict) --* 

            Information about a rule.

            
            

            - **RuleArn** *(string) --* 

              The Amazon Resource Name (ARN) of the rule.

              
            

            - **Priority** *(string) --* 

              The priority.

              
            

            - **Conditions** *(list) --* 

              The conditions.

              
              

              - *(dict) --* 

                Information about a condition for a rule.

                
                

                - **Field** *(string) --* 

                  The name of the field. The possible value is ``path-pattern`` .

                  
                

                - **Values** *(list) --* 

                  The values for the field.

                   

                  A path pattern is case sensitive, can be up to 255 characters in length, and can contain any of the following characters:

                   

                   
                  * A-Z, a-z, 0-9 
                   
                  * _ - . $ / ~ " ' @ : + 
                   
                  * amp; (using amp;amp;) 
                   
                  * * (matches 0 or more characters) 
                   
                  * ? (matches exactly 1 character) 
                   

                  
                  

                  - *(string) --* 
              
            
          
            

            - **Actions** *(list) --* 

              The actions.

              
              

              - *(dict) --* 

                Information about an action.

                
                

                - **Type** *(string) --* 

                  The type of action.

                  
                

                - **TargetGroupArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the target group.

                  
            
          
            

            - **IsDefault** *(boolean) --* 

              Indicates whether this is the default rule.

              
        
      
    

  .. py:method:: set_security_groups(**kwargs)

    

    Associates the specified security groups with the specified load balancer. The specified security groups override the previously associated security groups.

    

    **Request Syntax** 
    ::

      response = client.set_security_groups(
          LoadBalancerArn='string',
          SecurityGroups=[
              'string',
          ]
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    :type SecurityGroups: list
    :param SecurityGroups: **[REQUIRED]** 

      The IDs of the security groups.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'SecurityGroupIds': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of SetSecurityGroups.

        
        

        - **SecurityGroupIds** *(list) --* 

          The IDs of the security groups associated with the load balancer.

          
          

          - *(string) --* 
      
    

  .. py:method:: set_subnets(**kwargs)

    

    Enables the Availability Zone for the specified subnets for the specified load balancer. The specified subnets replace the previously enabled subnets.

    

    **Request Syntax** 
    ::

      response = client.set_subnets(
          LoadBalancerArn='string',
          Subnets=[
              'string',
          ]
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: **[REQUIRED]** 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    :type Subnets: list
    :param Subnets: **[REQUIRED]** 

      The IDs of the subnets. You must specify at least two subnets. You can add only one subnet per Availability Zone.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'AvailabilityZones': [
                {
                    'ZoneName': 'string',
                    'SubnetId': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of SetSubnets.

        
        

        - **AvailabilityZones** *(list) --* 

          Information about the subnet and Availability Zone.

          
          

          - *(dict) --* 

            Information about an Availability Zone.

            
            

            - **ZoneName** *(string) --* 

              The name of the Availability Zone.

              
            

            - **SubnetId** *(string) --* 

              The ID of the subnet.

              
        
      
    

==========
Paginators
==========


The available paginators are:

* :py:class:`ElasticLoadBalancingv2.Paginator.DescribeListeners`


* :py:class:`ElasticLoadBalancingv2.Paginator.DescribeLoadBalancers`


* :py:class:`ElasticLoadBalancingv2.Paginator.DescribeTargetGroups`



.. py:class:: ElasticLoadBalancingv2.Paginator.DescribeListeners

  ::

    
    paginator = client.get_paginator('describe_listeners')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ElasticLoadBalancingv2.Client.describe_listeners`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          LoadBalancerArn='string',
          ListenerArns=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    :type ListenerArns: list
    :param ListenerArns: 

      The Amazon Resource Names (ARN) of the listeners.

      

    
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
            'Listeners': [
                {
                    'ListenerArn': 'string',
                    'LoadBalancerArn': 'string',
                    'Port': 123,
                    'Protocol': 'HTTP'|'HTTPS',
                    'Certificates': [
                        {
                            'CertificateArn': 'string'
                        },
                    ],
                    'SslPolicy': 'string',
                    'DefaultActions': [
                        {
                            'Type': 'forward',
                            'TargetGroupArn': 'string'
                        },
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeListeners.

        
        

        - **Listeners** *(list) --* 

          Information about the listeners.

          
          

          - *(dict) --* 

            Information about a listener.

            
            

            - **ListenerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the listener.

              
            

            - **LoadBalancerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the load balancer.

              
            

            - **Port** *(integer) --* 

              The port on which the load balancer is listening.

              
            

            - **Protocol** *(string) --* 

              The protocol for connections from clients to the load balancer.

              
            

            - **Certificates** *(list) --* 

              The SSL server certificate. You must provide a certificate if the protocol is HTTPS.

              
              

              - *(dict) --* 

                Information about an SSL server certificate deployed on a load balancer.

                
                

                - **CertificateArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the certificate.

                  
            
          
            

            - **SslPolicy** *(string) --* 

              The security policy that defines which ciphers and protocols are supported. The default is the current predefined security policy.

              
            

            - **DefaultActions** *(list) --* 

              The default actions for the listener.

              
              

              - *(dict) --* 

                Information about an action.

                
                

                - **Type** *(string) --* 

                  The type of action.

                  
                

                - **TargetGroupArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the target group.

                  
            
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: ElasticLoadBalancingv2.Paginator.DescribeLoadBalancers

  ::

    
    paginator = client.get_paginator('describe_load_balancers')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ElasticLoadBalancingv2.Client.describe_load_balancers`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          LoadBalancerArns=[
              'string',
          ],
          Names=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type LoadBalancerArns: list
    :param LoadBalancerArns: 

      The Amazon Resource Names (ARN) of the load balancers.

      

    
      - *(string) --* 

      
  
    :type Names: list
    :param Names: 

      The names of the load balancers.

      

    
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
            'LoadBalancers': [
                {
                    'LoadBalancerArn': 'string',
                    'DNSName': 'string',
                    'CanonicalHostedZoneId': 'string',
                    'CreatedTime': datetime(2015, 1, 1),
                    'LoadBalancerName': 'string',
                    'Scheme': 'internet-facing'|'internal',
                    'VpcId': 'string',
                    'State': {
                        'Code': 'active'|'provisioning'|'failed',
                        'Reason': 'string'
                    },
                    'Type': 'application',
                    'AvailabilityZones': [
                        {
                            'ZoneName': 'string',
                            'SubnetId': 'string'
                        },
                    ],
                    'SecurityGroups': [
                        'string',
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeLoadBalancers.

        
        

        - **LoadBalancers** *(list) --* 

          Information about the load balancers.

          
          

          - *(dict) --* 

            Information about a load balancer.

            
            

            - **LoadBalancerArn** *(string) --* 

              The Amazon Resource Name (ARN) of the load balancer.

              
            

            - **DNSName** *(string) --* 

              The public DNS name of the load balancer.

              
            

            - **CanonicalHostedZoneId** *(string) --* 

              The ID of the Amazon Route 53 hosted zone associated with the load balancer.

              
            

            - **CreatedTime** *(datetime) --* 

              The date and time the load balancer was created.

              
            

            - **LoadBalancerName** *(string) --* 

              The name of the load balancer.

              
            

            - **Scheme** *(string) --* 

              The nodes of an Internet-facing load balancer have public IP addresses. The DNS name of an Internet-facing load balancer is publicly resolvable to the public IP addresses of the nodes. Therefore, Internet-facing load balancers can route requests from clients over the Internet.

               

              The nodes of an internal load balancer have only private IP addresses. The DNS name of an internal load balancer is publicly resolvable to the private IP addresses of the nodes. Therefore, internal load balancers can only route requests from clients with access to the VPC for the load balancer.

              
            

            - **VpcId** *(string) --* 

              The ID of the VPC for the load balancer.

              
            

            - **State** *(dict) --* 

              The state of the load balancer.

              
              

              - **Code** *(string) --* 

                The state code. The initial state of the load balancer is ``provisioning`` . After the load balancer is fully set up and ready to route traffic, its state is ``active`` . If the load balancer could not be set up, its state is ``failed`` .

                
              

              - **Reason** *(string) --* 

                A description of the state.

                
          
            

            - **Type** *(string) --* 

              The type of load balancer.

              
            

            - **AvailabilityZones** *(list) --* 

              The Availability Zones for the load balancer.

              
              

              - *(dict) --* 

                Information about an Availability Zone.

                
                

                - **ZoneName** *(string) --* 

                  The name of the Availability Zone.

                  
                

                - **SubnetId** *(string) --* 

                  The ID of the subnet.

                  
            
          
            

            - **SecurityGroups** *(list) --* 

              The IDs of the security groups for the load balancer.

              
              

              - *(string) --* 
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: ElasticLoadBalancingv2.Paginator.DescribeTargetGroups

  ::

    
    paginator = client.get_paginator('describe_target_groups')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ElasticLoadBalancingv2.Client.describe_target_groups`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          LoadBalancerArn='string',
          TargetGroupArns=[
              'string',
          ],
          Names=[
              'string',
          ],
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type LoadBalancerArn: string
    :param LoadBalancerArn: 

      The Amazon Resource Name (ARN) of the load balancer.

      

    
    :type TargetGroupArns: list
    :param TargetGroupArns: 

      The Amazon Resource Names (ARN) of the target groups.

      

    
      - *(string) --* 

      
  
    :type Names: list
    :param Names: 

      The names of the target groups.

      

    
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
            'TargetGroups': [
                {
                    'TargetGroupArn': 'string',
                    'TargetGroupName': 'string',
                    'Protocol': 'HTTP'|'HTTPS',
                    'Port': 123,
                    'VpcId': 'string',
                    'HealthCheckProtocol': 'HTTP'|'HTTPS',
                    'HealthCheckPort': 'string',
                    'HealthCheckIntervalSeconds': 123,
                    'HealthCheckTimeoutSeconds': 123,
                    'HealthyThresholdCount': 123,
                    'UnhealthyThresholdCount': 123,
                    'HealthCheckPath': 'string',
                    'Matcher': {
                        'HttpCode': 'string'
                    },
                    'LoadBalancerArns': [
                        'string',
                    ]
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Contains the output of DescribeTargetGroups.

        
        

        - **TargetGroups** *(list) --* 

          Information about the target groups.

          
          

          - *(dict) --* 

            Information about a target group.

            
            

            - **TargetGroupArn** *(string) --* 

              The Amazon Resource Name (ARN) of the target group.

              
            

            - **TargetGroupName** *(string) --* 

              The name of the target group.

              
            

            - **Protocol** *(string) --* 

              The protocol to use for routing traffic to the targets.

              
            

            - **Port** *(integer) --* 

              The port on which the targets are listening.

              
            

            - **VpcId** *(string) --* 

              The ID of the VPC for the targets.

              
            

            - **HealthCheckProtocol** *(string) --* 

              The protocol to use to connect with the target.

              
            

            - **HealthCheckPort** *(string) --* 

              The port to use to connect with the target.

              
            

            - **HealthCheckIntervalSeconds** *(integer) --* 

              The approximate amount of time, in seconds, between health checks of an individual target.

              
            

            - **HealthCheckTimeoutSeconds** *(integer) --* 

              The amount of time, in seconds, during which no response means a failed health check.

              
            

            - **HealthyThresholdCount** *(integer) --* 

              The number of consecutive health checks successes required before considering an unhealthy target healthy.

              
            

            - **UnhealthyThresholdCount** *(integer) --* 

              The number of consecutive health check failures required before considering the target unhealthy.

              
            

            - **HealthCheckPath** *(string) --* 

              The destination for the health check request.

              
            

            - **Matcher** *(dict) --* 

              The HTTP codes to use when checking for a successful response from a target.

              
              

              - **HttpCode** *(string) --* 

                The HTTP codes. The default value is 200. You can specify multiple values (for example, "200,202") or a range of values (for example, "200-299").

                
          
            

            - **LoadBalancerArns** *(list) --* 

              The Amazon Resource Names (ARN) of the load balancers that route traffic to this target group.

              
              

              - *(string) --* 
          
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    