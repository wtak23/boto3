

.. _https\://docs.docker.com/userguide/dockerlinks/: https://docs.docker.com/userguide/dockerlinks/
.. _Service Load Balancing: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-load-balancing.html
.. _CPU share constraint: https://docs.docker.com/reference/run/#cpu-share-constraint
.. _available on GitHub: https://github.com/aws/amazon-ecs-agent
.. _IAM Roles for Tasks: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-iam-roles.html
.. _Amazon ECS Container Agent Configuration: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-agent-config.html
.. _Network settings: https://docs.docker.com/engine/reference/run/#network-settings
.. _Application Architecture: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/application_architecture.html
.. _Configure logging drivers: https://docs.docker.com/engine/admin/logging/overview/
.. _https\://docs.docker.com/reference/builder/#cmd: https://docs.docker.com/reference/builder/#cmd
.. _Manually Updating the Amazon ECS Container Agent: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-agent-update.html#manually_update_agent
.. _amazon-ecs-agent: https://github.com/aws/amazon-ecs-agent/commits/master
.. _https\://docs.docker.com/reference/builder/#entrypoint: https://docs.docker.com/reference/builder/#entrypoint
.. _Amazon EC2 Instances: http://aws.amazon.com/ec2/instance-types/
.. _docker run: https://docs.docker.com/reference/commandline/run/
.. _Friendly Names and Paths: http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html#identifiers-friendly-names
.. _Amazon ECS Task Definitions: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_defintions.html
.. _Create a container: https://docs.docker.com/reference/api/docker_remote_api_v1.23/#create-a-container
.. _Docker Remote API: https://docs.docker.com/reference/api/docker_remote_api_v1.23/


***
ECS
***

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: ECS.Client

  A low-level client representing Amazon EC2 Container Service (ECS)::

    
    import boto3
    
    client = boto3.client('ecs')

  
  These are the available methods:
  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_cluster`

  
  *   :py:meth:`create_service`

  
  *   :py:meth:`delete_cluster`

  
  *   :py:meth:`delete_service`

  
  *   :py:meth:`deregister_container_instance`

  
  *   :py:meth:`deregister_task_definition`

  
  *   :py:meth:`describe_clusters`

  
  *   :py:meth:`describe_container_instances`

  
  *   :py:meth:`describe_services`

  
  *   :py:meth:`describe_task_definition`

  
  *   :py:meth:`describe_tasks`

  
  *   :py:meth:`discover_poll_endpoint`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_clusters`

  
  *   :py:meth:`list_container_instances`

  
  *   :py:meth:`list_services`

  
  *   :py:meth:`list_task_definition_families`

  
  *   :py:meth:`list_task_definitions`

  
  *   :py:meth:`list_tasks`

  
  *   :py:meth:`register_container_instance`

  
  *   :py:meth:`register_task_definition`

  
  *   :py:meth:`run_task`

  
  *   :py:meth:`start_task`

  
  *   :py:meth:`stop_task`

  
  *   :py:meth:`submit_container_state_change`

  
  *   :py:meth:`submit_task_state_change`

  
  *   :py:meth:`update_container_agent`

  
  *   :py:meth:`update_service`

  

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


  .. py:method:: create_cluster(**kwargs)

    

    Creates a new Amazon ECS cluster. By default, your account receives a ``default`` cluster when you launch your first container instance. However, you can create your own cluster with a unique name with the ``CreateCluster`` action.

    

    **Request Syntax** 
    ::

      response = client.create_cluster(
          clusterName='string'
      )
    :type clusterName: string
    :param clusterName: 

      The name of your cluster. If you do not specify a name for your cluster, you create a cluster named ``default`` . Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'cluster': {
                'clusterArn': 'string',
                'clusterName': 'string',
                'status': 'string',
                'registeredContainerInstancesCount': 123,
                'runningTasksCount': 123,
                'pendingTasksCount': 123,
                'activeServicesCount': 123
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **cluster** *(dict) --* 

          The full description of your new cluster.

          
          

          - **clusterArn** *(string) --* 

            The Amazon Resource Name (ARN) that identifies the cluster. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the cluster, the AWS account ID of the cluster owner, the ``cluster`` namespace, and then the cluster name. For example, ``arn:aws:ecs:*region* :*012345678910* :cluster/*test* `` ..

            
          

          - **clusterName** *(string) --* 

            A user-generated string that you use to identify your cluster.

            
          

          - **status** *(string) --* 

            The status of the cluster. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that you can register container instances with the cluster and the associated instances can accept tasks.

            
          

          - **registeredContainerInstancesCount** *(integer) --* 

            The number of container instances registered into the cluster.

            
          

          - **runningTasksCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``RUNNING`` state.

            
          

          - **pendingTasksCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``PENDING`` state.

            
          

          - **activeServicesCount** *(integer) --* 

            The number of services that are running on the cluster in an ``ACTIVE`` state. You can view these services with  ListServices .

            
      
    

  .. py:method:: create_service(**kwargs)

    

    Runs and maintains a desired number of tasks from a specified task definition. If the number of tasks running in a service drops below ``desiredCount`` , Amazon ECS spawns another instantiation of the task in the specified cluster. To update an existing service, see  UpdateService .

     

    In addition to maintaining the desired count of tasks in your service, you can optionally run your service behind a load balancer. The load balancer distributes traffic across the tasks that are associated with the service. For more information, see `Service Load Balancing`_ in the *Amazon EC2 Container Service Developer Guide* .

     

    You can optionally specify a deployment configuration for your service. During a deployment (which is triggered by changing the task definition of a service with an  UpdateService operation), the service scheduler uses the ``minimumHealthyPercent`` and ``maximumPercent`` parameters to determine the deployment strategy.

     

    If the ``minimumHealthyPercent`` is below 100%, the scheduler can ignore the ``desiredCount`` temporarily during a deployment. For example, if your service has a ``desiredCount`` of four tasks, a ``minimumHealthyPercent`` of 50% allows the scheduler to stop two existing tasks before starting two new tasks. Tasks for services that *do not* use a load balancer are considered healthy if they are in the ``RUNNING`` state; tasks for services that *do* use a load balancer are considered healthy if they are in the ``RUNNING`` state and the container instance it is hosted on is reported as healthy by the load balancer. The default value for ``minimumHealthyPercent`` is 50% in the console and 100% for the AWS CLI, the AWS SDKs, and the APIs.

     

    The ``maximumPercent`` parameter represents an upper limit on the number of running tasks during a deployment, which enables you to define the deployment batch size. For example, if your service has a ``desiredCount`` of four tasks, a ``maximumPercent`` value of 200% starts four new tasks before stopping the four older tasks (provided that the cluster resources required to do this are available). The default value for ``maximumPercent`` is 200%.

     

    When the service scheduler launches new tasks, it attempts to balance them across the Availability Zones in your cluster with the following logic:

     

     
    * Determine which of the container instances in your cluster can support your service's task definition (for example, they have the required CPU, memory, ports, and container instance attributes). 
     
    * Sort the valid container instances by the fewest number of running tasks for this service in the same Availability Zone as the instance. For example, if zone A has one running service task and zones B and C each have zero, valid container instances in either zone B or C are considered optimal for placement. 
     
    * Place the new service task on a valid container instance in an optimal Availability Zone (based on the previous steps), favoring container instances with the fewest number of running tasks for this service. 
     

    

    **Request Syntax** 
    ::

      response = client.create_service(
          cluster='string',
          serviceName='string',
          taskDefinition='string',
          loadBalancers=[
              {
                  'targetGroupArn': 'string',
                  'loadBalancerName': 'string',
                  'containerName': 'string',
                  'containerPort': 123
              },
          ],
          desiredCount=123,
          clientToken='string',
          role='string',
          deploymentConfiguration={
              'maximumPercent': 123,
              'minimumHealthyPercent': 123
          }
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster on which to run your service. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type serviceName: string
    :param serviceName: **[REQUIRED]** 

      The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a region or across multiple regions.

      

    
    :type taskDefinition: string
    :param taskDefinition: **[REQUIRED]** 

      The ``family`` and ``revision`` (``family:revision`` ) or full Amazon Resource Name (ARN) of the task definition to run in your service. If a ``revision`` is not specified, the latest ``ACTIVE`` revision is used.

      

    
    :type loadBalancers: list
    :param loadBalancers: 

      A load balancer object representing the load balancer to use with your service. Currently, you are limited to one load balancer per service. After you create a service, the load balancer name, container name, and container port specified in the service definition are immutable.

       

      For Elastic Load Balancing Classic load balancers, this object must contain the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer. When a task from this service is placed on a container instance, the container instance is registered with the load balancer specified here.

       

      For Elastic Load Balancing Application load balancers, this object must contain the load balancer target group ARN, the container name (as it appears in a container definition), and the container port to access from the load balancer. When a task from this service is placed on a container instance, the container instance and port combination is registered as a target in the target group specified here.

      

    
      - *(dict) --* 

        Details on a load balancer that is used with a service.

        

      
        - **targetGroupArn** *(string) --* 

          The full Amazon Resource Name (ARN) of the Elastic Load Balancing target group associated with a service.

          

        
        - **loadBalancerName** *(string) --* 

          The name of the load balancer.

          

        
        - **containerName** *(string) --* 

          The name of the container (as it appears in a container definition) to associate with the load balancer.

          

        
        - **containerPort** *(integer) --* 

          The port on the container to associate with the load balancer. This port must correspond to a ``containerPort`` in the service's task definition. Your container instances must allow ingress traffic on the ``hostPort`` of the port mapping.

          

        
      
  
    :type desiredCount: integer
    :param desiredCount: **[REQUIRED]** 

      The number of instantiations of the specified task definition to place and keep running on your cluster.

      

    
    :type clientToken: string
    :param clientToken: 

      Unique, case-sensitive identifier you provide to ensure the idempotency of the request. Up to 32 ASCII characters are allowed.

      

    
    :type role: string
    :param role: 

      The name or full Amazon Resource Name (ARN) of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service. If you specify the ``role`` parameter, you must also specify a load balancer object with the ``loadBalancers`` parameter.

       

      If your specified role has a path other than ``/`` , then you must either specify the full role ARN (this is recommended) or prefix the role name with the path. For example, if a role with the name ``bar`` has a path of ``/foo/`` then you would specify ``/foo/bar`` as the role name. For more information, see `Friendly Names and Paths`_ in the *IAM User Guide* .

      

    
    :type deploymentConfiguration: dict
    :param deploymentConfiguration: 

      Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

      

    
      - **maximumPercent** *(integer) --* 

        The upper limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that can be running in a service during a deployment. The maximum number of tasks during a deployment is the ``desiredCount`` multiplied by the ``maximumPercent`` /100, rounded down to the nearest integer value.

        

      
      - **minimumHealthyPercent** *(integer) --* 

        The lower limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that must remain running and healthy in a service during a deployment. The minimum healthy tasks during a deployment is the ``desiredCount`` multiplied by the ``minimumHealthyPercent`` /100, rounded up to the nearest integer value.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'service': {
                'serviceArn': 'string',
                'serviceName': 'string',
                'clusterArn': 'string',
                'loadBalancers': [
                    {
                        'targetGroupArn': 'string',
                        'loadBalancerName': 'string',
                        'containerName': 'string',
                        'containerPort': 123
                    },
                ],
                'status': 'string',
                'desiredCount': 123,
                'runningCount': 123,
                'pendingCount': 123,
                'taskDefinition': 'string',
                'deploymentConfiguration': {
                    'maximumPercent': 123,
                    'minimumHealthyPercent': 123
                },
                'deployments': [
                    {
                        'id': 'string',
                        'status': 'string',
                        'taskDefinition': 'string',
                        'desiredCount': 123,
                        'pendingCount': 123,
                        'runningCount': 123,
                        'createdAt': datetime(2015, 1, 1),
                        'updatedAt': datetime(2015, 1, 1)
                    },
                ],
                'roleArn': 'string',
                'events': [
                    {
                        'id': 'string',
                        'createdAt': datetime(2015, 1, 1),
                        'message': 'string'
                    },
                ],
                'createdAt': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **service** *(dict) --* 

          The full description of your service following the create call.

          
          

          - **serviceArn** *(string) --* 

            The Amazon Resource Name (ARN) that identifies the service. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the service, the AWS account ID of the service owner, the ``service`` namespace, and then the service name. For example, ``arn:aws:ecs:*region* :*012345678910* :service/*my-service* `` .

            
          

          - **serviceName** *(string) --* 

            The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a region or across multiple regions.

            
          

          - **clusterArn** *(string) --* 

            The Amazon Resource Name (ARN) of the cluster that hosts the service.

            
          

          - **loadBalancers** *(list) --* 

            A list of Elastic Load Balancing load balancer objects, containing the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer.

            
            

            - *(dict) --* 

              Details on a load balancer that is used with a service.

              
              

              - **targetGroupArn** *(string) --* 

                The full Amazon Resource Name (ARN) of the Elastic Load Balancing target group associated with a service.

                
              

              - **loadBalancerName** *(string) --* 

                The name of the load balancer.

                
              

              - **containerName** *(string) --* 

                The name of the container (as it appears in a container definition) to associate with the load balancer.

                
              

              - **containerPort** *(integer) --* 

                The port on the container to associate with the load balancer. This port must correspond to a ``containerPort`` in the service's task definition. Your container instances must allow ingress traffic on the ``hostPort`` of the port mapping.

                
          
        
          

          - **status** *(string) --* 

            The status of the service. The valid values are ``ACTIVE`` , ``DRAINING`` , or ``INACTIVE`` .

            
          

          - **desiredCount** *(integer) --* 

            The desired number of instantiations of the task definition to keep running on the service. This value is specified when the service is created with  CreateService , and it can be modified with  UpdateService .

            
          

          - **runningCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``RUNNING`` state.

            
          

          - **pendingCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``PENDING`` state.

            
          

          - **taskDefinition** *(string) --* 

            The task definition to use for tasks in the service. This value is specified when the service is created with  CreateService , and it can be modified with  UpdateService .

            
          

          - **deploymentConfiguration** *(dict) --* 

            Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

            
            

            - **maximumPercent** *(integer) --* 

              The upper limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that can be running in a service during a deployment. The maximum number of tasks during a deployment is the ``desiredCount`` multiplied by the ``maximumPercent`` /100, rounded down to the nearest integer value.

              
            

            - **minimumHealthyPercent** *(integer) --* 

              The lower limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that must remain running and healthy in a service during a deployment. The minimum healthy tasks during a deployment is the ``desiredCount`` multiplied by the ``minimumHealthyPercent`` /100, rounded up to the nearest integer value.

              
        
          

          - **deployments** *(list) --* 

            The current state of deployments for the service.

            
            

            - *(dict) --* 

              The details of an Amazon ECS service deployment.

              
              

              - **id** *(string) --* 

                The ID of the deployment.

                
              

              - **status** *(string) --* 

                The status of the deployment. Valid values are ``PRIMARY`` (for the most recent deployment), ``ACTIVE`` (for previous deployments that still have tasks running, but are being replaced with the ``PRIMARY`` deployment), and ``INACTIVE`` (for deployments that have been completely replaced).

                
              

              - **taskDefinition** *(string) --* 

                The most recent task definition that was specified for the service to use.

                
              

              - **desiredCount** *(integer) --* 

                The most recent desired count of tasks that was specified for the service to deploy or maintain.

                
              

              - **pendingCount** *(integer) --* 

                The number of tasks in the deployment that are in the ``PENDING`` status.

                
              

              - **runningCount** *(integer) --* 

                The number of tasks in the deployment that are in the ``RUNNING`` status.

                
              

              - **createdAt** *(datetime) --* 

                The Unix timestamp for when the service was created.

                
              

              - **updatedAt** *(datetime) --* 

                The Unix timestamp for when the service was last updated.

                
          
        
          

          - **roleArn** *(string) --* 

            The Amazon Resource Name (ARN) of the IAM role associated with the service that allows the Amazon ECS container agent to register container instances with an Elastic Load Balancing load balancer.

            
          

          - **events** *(list) --* 

            The event stream for your service. A maximum of 100 of the latest events are displayed.

            
            

            - *(dict) --* 

              Details on an event associated with a service.

              
              

              - **id** *(string) --* 

                The ID string of the event.

                
              

              - **createdAt** *(datetime) --* 

                The Unix timestamp for when the event was triggered.

                
              

              - **message** *(string) --* 

                The event message.

                
          
        
          

          - **createdAt** *(datetime) --* 

            The Unix timestamp for when the service was created.

            
      
    

  .. py:method:: delete_cluster(**kwargs)

    

    Deletes the specified cluster. You must deregister all container instances from this cluster before you may delete it. You can list the container instances in a cluster with  ListContainerInstances and deregister them with  DeregisterContainerInstance .

    

    **Request Syntax** 
    ::

      response = client.delete_cluster(
          cluster='string'
      )
    :type cluster: string
    :param cluster: **[REQUIRED]** 

      The short name or full Amazon Resource Name (ARN) of the cluster to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'cluster': {
                'clusterArn': 'string',
                'clusterName': 'string',
                'status': 'string',
                'registeredContainerInstancesCount': 123,
                'runningTasksCount': 123,
                'pendingTasksCount': 123,
                'activeServicesCount': 123
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **cluster** *(dict) --* 

          The full description of the deleted cluster.

          
          

          - **clusterArn** *(string) --* 

            The Amazon Resource Name (ARN) that identifies the cluster. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the cluster, the AWS account ID of the cluster owner, the ``cluster`` namespace, and then the cluster name. For example, ``arn:aws:ecs:*region* :*012345678910* :cluster/*test* `` ..

            
          

          - **clusterName** *(string) --* 

            A user-generated string that you use to identify your cluster.

            
          

          - **status** *(string) --* 

            The status of the cluster. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that you can register container instances with the cluster and the associated instances can accept tasks.

            
          

          - **registeredContainerInstancesCount** *(integer) --* 

            The number of container instances registered into the cluster.

            
          

          - **runningTasksCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``RUNNING`` state.

            
          

          - **pendingTasksCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``PENDING`` state.

            
          

          - **activeServicesCount** *(integer) --* 

            The number of services that are running on the cluster in an ``ACTIVE`` state. You can view these services with  ListServices .

            
      
    

  .. py:method:: delete_service(**kwargs)

    

    Deletes a specified service within a cluster. You can delete a service if you have no running tasks in it and the desired task count is zero. If the service is actively maintaining tasks, you cannot delete it, and you must update the service to a desired task count of zero. For more information, see  UpdateService .

     

    .. note::

       

      When you delete a service, if there are still running tasks that require cleanup, the service status moves from ``ACTIVE`` to ``DRAINING`` , and the service is no longer visible in the console or in  ListServices API operations. After the tasks have stopped, then the service status moves from ``DRAINING`` to ``INACTIVE`` . Services in the ``DRAINING`` or ``INACTIVE`` status can still be viewed with  DescribeServices API operations; however, in the future, ``INACTIVE`` services may be cleaned up and purged from Amazon ECS record keeping, and  DescribeServices API operations on those services will return a ``ServiceNotFoundException`` error.

       

    

    **Request Syntax** 
    ::

      response = client.delete_service(
          cluster='string',
          service='string'
      )
    :type cluster: string
    :param cluster: 

      The name of the cluster that hosts the service to delete. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type service: string
    :param service: **[REQUIRED]** 

      The name of the service to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'service': {
                'serviceArn': 'string',
                'serviceName': 'string',
                'clusterArn': 'string',
                'loadBalancers': [
                    {
                        'targetGroupArn': 'string',
                        'loadBalancerName': 'string',
                        'containerName': 'string',
                        'containerPort': 123
                    },
                ],
                'status': 'string',
                'desiredCount': 123,
                'runningCount': 123,
                'pendingCount': 123,
                'taskDefinition': 'string',
                'deploymentConfiguration': {
                    'maximumPercent': 123,
                    'minimumHealthyPercent': 123
                },
                'deployments': [
                    {
                        'id': 'string',
                        'status': 'string',
                        'taskDefinition': 'string',
                        'desiredCount': 123,
                        'pendingCount': 123,
                        'runningCount': 123,
                        'createdAt': datetime(2015, 1, 1),
                        'updatedAt': datetime(2015, 1, 1)
                    },
                ],
                'roleArn': 'string',
                'events': [
                    {
                        'id': 'string',
                        'createdAt': datetime(2015, 1, 1),
                        'message': 'string'
                    },
                ],
                'createdAt': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **service** *(dict) --* 

          The full description of the deleted service.

          
          

          - **serviceArn** *(string) --* 

            The Amazon Resource Name (ARN) that identifies the service. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the service, the AWS account ID of the service owner, the ``service`` namespace, and then the service name. For example, ``arn:aws:ecs:*region* :*012345678910* :service/*my-service* `` .

            
          

          - **serviceName** *(string) --* 

            The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a region or across multiple regions.

            
          

          - **clusterArn** *(string) --* 

            The Amazon Resource Name (ARN) of the cluster that hosts the service.

            
          

          - **loadBalancers** *(list) --* 

            A list of Elastic Load Balancing load balancer objects, containing the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer.

            
            

            - *(dict) --* 

              Details on a load balancer that is used with a service.

              
              

              - **targetGroupArn** *(string) --* 

                The full Amazon Resource Name (ARN) of the Elastic Load Balancing target group associated with a service.

                
              

              - **loadBalancerName** *(string) --* 

                The name of the load balancer.

                
              

              - **containerName** *(string) --* 

                The name of the container (as it appears in a container definition) to associate with the load balancer.

                
              

              - **containerPort** *(integer) --* 

                The port on the container to associate with the load balancer. This port must correspond to a ``containerPort`` in the service's task definition. Your container instances must allow ingress traffic on the ``hostPort`` of the port mapping.

                
          
        
          

          - **status** *(string) --* 

            The status of the service. The valid values are ``ACTIVE`` , ``DRAINING`` , or ``INACTIVE`` .

            
          

          - **desiredCount** *(integer) --* 

            The desired number of instantiations of the task definition to keep running on the service. This value is specified when the service is created with  CreateService , and it can be modified with  UpdateService .

            
          

          - **runningCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``RUNNING`` state.

            
          

          - **pendingCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``PENDING`` state.

            
          

          - **taskDefinition** *(string) --* 

            The task definition to use for tasks in the service. This value is specified when the service is created with  CreateService , and it can be modified with  UpdateService .

            
          

          - **deploymentConfiguration** *(dict) --* 

            Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

            
            

            - **maximumPercent** *(integer) --* 

              The upper limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that can be running in a service during a deployment. The maximum number of tasks during a deployment is the ``desiredCount`` multiplied by the ``maximumPercent`` /100, rounded down to the nearest integer value.

              
            

            - **minimumHealthyPercent** *(integer) --* 

              The lower limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that must remain running and healthy in a service during a deployment. The minimum healthy tasks during a deployment is the ``desiredCount`` multiplied by the ``minimumHealthyPercent`` /100, rounded up to the nearest integer value.

              
        
          

          - **deployments** *(list) --* 

            The current state of deployments for the service.

            
            

            - *(dict) --* 

              The details of an Amazon ECS service deployment.

              
              

              - **id** *(string) --* 

                The ID of the deployment.

                
              

              - **status** *(string) --* 

                The status of the deployment. Valid values are ``PRIMARY`` (for the most recent deployment), ``ACTIVE`` (for previous deployments that still have tasks running, but are being replaced with the ``PRIMARY`` deployment), and ``INACTIVE`` (for deployments that have been completely replaced).

                
              

              - **taskDefinition** *(string) --* 

                The most recent task definition that was specified for the service to use.

                
              

              - **desiredCount** *(integer) --* 

                The most recent desired count of tasks that was specified for the service to deploy or maintain.

                
              

              - **pendingCount** *(integer) --* 

                The number of tasks in the deployment that are in the ``PENDING`` status.

                
              

              - **runningCount** *(integer) --* 

                The number of tasks in the deployment that are in the ``RUNNING`` status.

                
              

              - **createdAt** *(datetime) --* 

                The Unix timestamp for when the service was created.

                
              

              - **updatedAt** *(datetime) --* 

                The Unix timestamp for when the service was last updated.

                
          
        
          

          - **roleArn** *(string) --* 

            The Amazon Resource Name (ARN) of the IAM role associated with the service that allows the Amazon ECS container agent to register container instances with an Elastic Load Balancing load balancer.

            
          

          - **events** *(list) --* 

            The event stream for your service. A maximum of 100 of the latest events are displayed.

            
            

            - *(dict) --* 

              Details on an event associated with a service.

              
              

              - **id** *(string) --* 

                The ID string of the event.

                
              

              - **createdAt** *(datetime) --* 

                The Unix timestamp for when the event was triggered.

                
              

              - **message** *(string) --* 

                The event message.

                
          
        
          

          - **createdAt** *(datetime) --* 

            The Unix timestamp for when the service was created.

            
      
    

  .. py:method:: deregister_container_instance(**kwargs)

    

    Deregisters an Amazon ECS container instance from the specified cluster. This instance is no longer available to run tasks.

     

    If you intend to use the container instance for some other purpose after deregistration, you should stop all of the tasks running on the container instance before deregistration to avoid any orphaned tasks from consuming resources.

     

    Deregistering a container instance removes the instance from a cluster, but it does not terminate the EC2 instance; if you are finished using the instance, be sure to terminate it in the Amazon EC2 console to stop billing.

     

    .. note::

       

      If you terminate a running container instance with a connected Amazon ECS container agent, the agent automatically deregisters the instance from your cluster (stopped container instances or instances with disconnected agents are not automatically deregistered when terminated).

       

    

    **Request Syntax** 
    ::

      response = client.deregister_container_instance(
          cluster='string',
          containerInstance='string',
          force=True|False
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instance to deregister. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type containerInstance: string
    :param containerInstance: **[REQUIRED]** 

      The container instance ID or full Amazon Resource Name (ARN) of the container instance to deregister. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, ``arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* `` .

      

    
    :type force: boolean
    :param force: 

      Forces the deregistration of the container instance. If you have tasks running on the container instance when you deregister it with the ``force`` option, these tasks remain running and they continue to pass Elastic Load Balancing load balancer health checks until you terminate the instance or the tasks stop through some other means, but they are orphaned (no longer monitored or accounted for by Amazon ECS). If an orphaned task on your container instance is part of an Amazon ECS service, then the service scheduler starts another copy of that task, on a different container instance if possible.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'containerInstance': {
                'containerInstanceArn': 'string',
                'ec2InstanceId': 'string',
                'versionInfo': {
                    'agentVersion': 'string',
                    'agentHash': 'string',
                    'dockerVersion': 'string'
                },
                'remainingResources': [
                    {
                        'name': 'string',
                        'type': 'string',
                        'doubleValue': 123.0,
                        'longValue': 123,
                        'integerValue': 123,
                        'stringSetValue': [
                            'string',
                        ]
                    },
                ],
                'registeredResources': [
                    {
                        'name': 'string',
                        'type': 'string',
                        'doubleValue': 123.0,
                        'longValue': 123,
                        'integerValue': 123,
                        'stringSetValue': [
                            'string',
                        ]
                    },
                ],
                'status': 'string',
                'agentConnected': True|False,
                'runningTasksCount': 123,
                'pendingTasksCount': 123,
                'agentUpdateStatus': 'PENDING'|'STAGING'|'STAGED'|'UPDATING'|'UPDATED'|'FAILED',
                'attributes': [
                    {
                        'name': 'string',
                        'value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **containerInstance** *(dict) --* 

          An EC2 instance that is running the Amazon ECS agent and has been registered with a cluster.

          
          

          - **containerInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, ``arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* `` .

            
          

          - **ec2InstanceId** *(string) --* 

            The EC2 instance ID of the container instance.

            
          

          - **versionInfo** *(dict) --* 

            The version information for the Amazon ECS container agent and Docker daemon running on the container instance.

            
            

            - **agentVersion** *(string) --* 

              The version number of the Amazon ECS container agent.

              
            

            - **agentHash** *(string) --* 

              The Git commit hash for the Amazon ECS container agent build on the `amazon-ecs-agent`_ GitHub repository.

              
            

            - **dockerVersion** *(string) --* 

              The Docker version running on the container instance.

              
        
          

          - **remainingResources** *(list) --* 

            The remaining resources of the container instance that are available for new tasks.

            
            

            - *(dict) --* 

              Describes the resources available for a container instance.

              
              

              - **name** *(string) --* 

                The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

                
              

              - **type** *(string) --* 

                The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

                
              

              - **doubleValue** *(float) --* 

                When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

                
              

              - **longValue** *(integer) --* 

                When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

                
              

              - **integerValue** *(integer) --* 

                When the ``integerValue`` type is set, the value of the resource must be an integer.

                
              

              - **stringSetValue** *(list) --* 

                When the ``stringSetValue`` type is set, the value of the resource must be a string type.

                
                

                - *(string) --* 
            
          
        
          

          - **registeredResources** *(list) --* 

            The registered resources on the container instance that are in use by current tasks.

            
            

            - *(dict) --* 

              Describes the resources available for a container instance.

              
              

              - **name** *(string) --* 

                The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

                
              

              - **type** *(string) --* 

                The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

                
              

              - **doubleValue** *(float) --* 

                When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

                
              

              - **longValue** *(integer) --* 

                When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

                
              

              - **integerValue** *(integer) --* 

                When the ``integerValue`` type is set, the value of the resource must be an integer.

                
              

              - **stringSetValue** *(list) --* 

                When the ``stringSetValue`` type is set, the value of the resource must be a string type.

                
                

                - *(string) --* 
            
          
        
          

          - **status** *(string) --* 

            The status of the container instance. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that the container instance can accept tasks.

            
          

          - **agentConnected** *(boolean) --* 

            This parameter returns ``true`` if the agent is actually connected to Amazon ECS. Registered instances with an agent that may be unhealthy or stopped return ``false`` , and instances without a connected agent cannot accept placement requests.

            
          

          - **runningTasksCount** *(integer) --* 

            The number of tasks on the container instance that are in the ``RUNNING`` status.

            
          

          - **pendingTasksCount** *(integer) --* 

            The number of tasks on the container instance that are in the ``PENDING`` status.

            
          

          - **agentUpdateStatus** *(string) --* 

            The status of the most recent agent update. If an update has never been requested, this value is ``NULL`` .

            
          

          - **attributes** *(list) --* 

            The attributes set for the container instance by the Amazon ECS container agent at instance registration.

            
            

            - *(dict) --* 

              The attributes applicable to a container instance when it is registered.

              
              

              - **name** *(string) --* 

                The name of the container instance attribute.

                
              

              - **value** *(string) --* 

                The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

                
          
        
      
    

  .. py:method:: deregister_task_definition(**kwargs)

    

    Deregisters the specified task definition by family and revision. Upon deregistration, the task definition is marked as ``INACTIVE`` . Existing tasks and services that reference an ``INACTIVE`` task definition continue to run without disruption. Existing services that reference an ``INACTIVE`` task definition can still scale up or down by modifying the service's desired count.

     

    You cannot use an ``INACTIVE`` task definition to run new tasks or create new services, and you cannot update an existing service to reference an ``INACTIVE`` task definition (although there may be up to a 10 minute window following deregistration where these restrictions have not yet taken effect).

    

    **Request Syntax** 
    ::

      response = client.deregister_task_definition(
          taskDefinition='string'
      )
    :type taskDefinition: string
    :param taskDefinition: **[REQUIRED]** 

      The ``family`` and ``revision`` (``family:revision`` ) or full Amazon Resource Name (ARN) of the task definition to deregister. You must specify a ``revision`` .

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'taskDefinition': {
                'taskDefinitionArn': 'string',
                'containerDefinitions': [
                    {
                        'name': 'string',
                        'image': 'string',
                        'cpu': 123,
                        'memory': 123,
                        'memoryReservation': 123,
                        'links': [
                            'string',
                        ],
                        'portMappings': [
                            {
                                'containerPort': 123,
                                'hostPort': 123,
                                'protocol': 'tcp'|'udp'
                            },
                        ],
                        'essential': True|False,
                        'entryPoint': [
                            'string',
                        ],
                        'command': [
                            'string',
                        ],
                        'environment': [
                            {
                                'name': 'string',
                                'value': 'string'
                            },
                        ],
                        'mountPoints': [
                            {
                                'sourceVolume': 'string',
                                'containerPath': 'string',
                                'readOnly': True|False
                            },
                        ],
                        'volumesFrom': [
                            {
                                'sourceContainer': 'string',
                                'readOnly': True|False
                            },
                        ],
                        'hostname': 'string',
                        'user': 'string',
                        'workingDirectory': 'string',
                        'disableNetworking': True|False,
                        'privileged': True|False,
                        'readonlyRootFilesystem': True|False,
                        'dnsServers': [
                            'string',
                        ],
                        'dnsSearchDomains': [
                            'string',
                        ],
                        'extraHosts': [
                            {
                                'hostname': 'string',
                                'ipAddress': 'string'
                            },
                        ],
                        'dockerSecurityOptions': [
                            'string',
                        ],
                        'dockerLabels': {
                            'string': 'string'
                        },
                        'ulimits': [
                            {
                                'name': 'core'|'cpu'|'data'|'fsize'|'locks'|'memlock'|'msgqueue'|'nice'|'nofile'|'nproc'|'rss'|'rtprio'|'rttime'|'sigpending'|'stack',
                                'softLimit': 123,
                                'hardLimit': 123
                            },
                        ],
                        'logConfiguration': {
                            'logDriver': 'json-file'|'syslog'|'journald'|'gelf'|'fluentd'|'awslogs'|'splunk',
                            'options': {
                                'string': 'string'
                            }
                        }
                    },
                ],
                'family': 'string',
                'taskRoleArn': 'string',
                'networkMode': 'bridge'|'host'|'none',
                'revision': 123,
                'volumes': [
                    {
                        'name': 'string',
                        'host': {
                            'sourcePath': 'string'
                        }
                    },
                ],
                'status': 'ACTIVE'|'INACTIVE',
                'requiresAttributes': [
                    {
                        'name': 'string',
                        'value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **taskDefinition** *(dict) --* 

          The full description of the deregistered task.

          
          

          - **taskDefinitionArn** *(string) --* 

            The full Amazon Resource Name (ARN) of the task definition.

            
          

          - **containerDefinitions** *(list) --* 

            A list of container definitions in JSON format that describe the different containers that make up your task. For more information about container definition parameters and defaults, see `Amazon ECS Task Definitions`_ in the *Amazon EC2 Container Service Developer Guide* .

            
            

            - *(dict) --* 

              Container definitions are used in task definitions to describe the different containers that are launched as part of a task.

              
              

              - **name** *(string) --* 

                The name of a container. If you are linking multiple containers together in a task definition, the ``name`` of one container can be entered in the ``links`` of another container to connect the containers. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This parameter maps to ``name`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--name`` option to `docker run`_ . 

                
              

              - **image** *(string) --* 

                The image used to start a container. This string is passed directly to the Docker daemon. Images in the Docker Hub registry are available by default. Other repositories are specified with `` *repository-url* /*image* :*tag* `` . Up to 255 letters (uppercase and lowercase), numbers, hyphens, underscores, colons, periods, forward slashes, and number signs are allowed. This parameter maps to ``Image`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``IMAGE`` parameter of `docker run`_ .

                 

                 
                * Images in official repositories on Docker Hub use a single name (for example, ``ubuntu`` or ``mongo`` ). 
                 
                * Images in other repositories on Docker Hub are qualified with an organization name (for example, ``amazon/amazon-ecs-agent`` ). 
                 
                * Images in other online repositories are qualified further by a domain name (for example, ``quay.io/assemblyline/ubuntu`` ). 
                 

                
              

              - **cpu** *(integer) --* 

                The number of ``cpu`` units reserved for the container. A container instance has 1,024 ``cpu`` units for every CPU core. This parameter specifies the minimum amount of CPU to reserve for a container, and containers share unallocated CPU units with other containers on the instance with the same ratio as their allocated amount. This parameter maps to ``CpuShares`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--cpu-shares`` option to `docker run`_ .

                 

                .. note::

                   

                  You can determine the number of CPU units that are available per EC2 instance type by multiplying the vCPUs listed for that instance type on the `Amazon EC2 Instances`_ detail page by 1,024.

                   

                 

                For example, if you run a single-container task on a single-core instance type with 512 CPU units specified for that container, and that is the only task running on the container instance, that container could use the full 1,024 CPU unit share at any given time. However, if you launched another copy of the same task on that container instance, each task would be guaranteed a minimum of 512 CPU units when needed, and each container could float to higher CPU usage if the other container was not using it, but if both tasks were 100% active all of the time, they would be limited to 512 CPU units.

                 

                The Docker daemon on the container instance uses the CPU value to calculate the relative CPU share ratios for running containers. For more information, see `CPU share constraint`_ in the Docker documentation. The minimum valid CPU share value that the Linux kernel allows is 2; however, the CPU parameter is not required, and you can use CPU values below 2 in your container definitions. For CPU values below 2 (including null), the behavior varies based on your Amazon ECS container agent version:

                 

                 
                * **Agent versions less than or equal to 1.1.0:** Null and zero CPU values are passed to Docker as 0, which Docker then converts to 1,024 CPU shares. CPU values of 1 are passed to Docker as 1, which the Linux kernel converts to 2 CPU shares. 
                 
                * **Agent versions greater than or equal to 1.2.0:** Null, zero, and CPU values of 1 are passed to Docker as 2. 
                 

                
              

              - **memory** *(integer) --* 

                The hard limit (in MiB) of memory to present to the container. If your container attempts to exceed the memory specified here, the container is killed. This parameter maps to ``Memory`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--memory`` option to `docker run`_ .

                 

                You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

                 

                The Docker daemon reserves a minimum of 4 MiB of memory for a container, so you should not specify fewer than 4 MiB of memory for your containers. 

                
              

              - **memoryReservation** *(integer) --* 

                The soft limit (in MiB) of memory to reserve for the container. When system memory is under heavy contention, Docker attempts to keep the container memory to this soft limit; however, your container can consume more memory when it needs to, up to either the hard limit specified with the ``memory`` parameter (if applicable), or all of the available memory on the container instance, whichever comes first. This parameter maps to ``MemoryReservation`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--memory-reservation`` option to `docker run`_ .

                 

                You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

                 

                For example, if your container normally uses 128 MiB of memory, but occasionally bursts to 256 MiB of memory for short periods of time, you can set a ``memoryReservation`` of 128 MiB, and a ``memory`` hard limit of 300 MiB. This configuration would allow the container to only reserve 128 MiB of memory from the remaining resources on the container instance, but also allow the container to consume more memory resources when needed.

                
              

              - **links** *(list) --* 

                The ``link`` parameter allows containers to communicate with each other without the need for port mappings, using the ``name`` parameter and optionally, an ``alias`` for the link. This construct is analogous to ``name:alias`` in Docker links. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed for each ``name`` and ``alias`` . For more information on linking Docker containers, see `https\://docs.docker.com/userguide/dockerlinks/`_ . This parameter maps to ``Links`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--link`` option to `docker run`_ .

                 

                .. warning::

                   

                  Containers that are collocated on a single container instance may be able to communicate with each other without requiring links or host port mappings. Network isolation is achieved on the container instance using security groups and VPC settings.

                   

                
                

                - *(string) --* 
            
              

              - **portMappings** *(list) --* 

                The list of port mappings for the container. Port mappings allow containers to access ports on the host container instance to send or receive traffic. This parameter maps to ``PortBindings`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--publish`` option to `docker run`_ . If the network mode of a task definition is set to ``none`` , then you cannot specify port mappings. If the network mode of a task definition is set to ``host`` , then host ports must either be undefined or they must match the container port in the port mapping.

                 

                .. note::

                   

                  After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the **Network Bindings** section of a container description of a selected task in the Amazon ECS console, or the ``networkBindings`` section  DescribeTasks responses.

                   

                
                

                - *(dict) --* 

                  Port mappings allow containers to access ports on the host container instance to send or receive traffic. Port mappings are specified as part of the container definition. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  DescribeTasks API responses.

                  
                  

                  - **containerPort** *(integer) --* 

                    The port number on the container that is bound to the user-specified or automatically assigned host port. If you specify a container port and not a host port, your container automatically receives a host port in the ephemeral port range (for more information, see ``hostPort`` ). Port mappings that are automatically assigned in this way do not count toward the 100 reserved ports limit of a container instance.

                    
                  

                  - **hostPort** *(integer) --* 

                    The port number on the container instance to reserve for your container. You can specify a non-reserved host port for your container port mapping, or you can omit the ``hostPort`` (or set it to ``0`` ) while specifying a ``containerPort`` and your container automatically receives a port in the ephemeral port range for your container instance operating system and Docker version.

                     

                    The default ephemeral port range is 49153 to 65535, and this range is used for Docker versions prior to 1.6.0. For Docker version 1.6.0 and later, the Docker daemon tries to read the ephemeral port range from ``/proc/sys/net/ipv4/ip_local_port_range`` ; if this kernel parameter is unavailable, the default ephemeral port range is used. You should not attempt to specify a host port in the ephemeral port range, because these are reserved for automatic assignment. In general, ports below 32768 are outside of the ephemeral port range.

                     

                    The default reserved ports are 22 for SSH, the Docker ports 2375 and 2376, and the Amazon ECS container agent port 51678. Any host port that was previously specified in a running task is also reserved while the task is running (after a task stops, the host port is released).The current reserved ports are displayed in the ``remainingResources`` of  DescribeContainerInstances output, and a container instance may have up to 100 reserved ports at a time, including the default reserved ports (automatically assigned ports do not count toward the 100 reserved ports limit).

                    
                  

                  - **protocol** *(string) --* 

                    The protocol used for the port mapping. Valid values are ``tcp`` and ``udp`` . The default is ``tcp`` .

                    
              
            
              

              - **essential** *(boolean) --* 

                If the ``essential`` parameter of a container is marked as ``true`` , and that container fails or stops for any reason, all other containers that are part of the task are stopped. If the ``essential`` parameter of a container is marked as ``false`` , then its failure does not affect the rest of the containers in a task. If this parameter is omitted, a container is assumed to be essential.

                 

                All tasks must have at least one essential container. If you have an application that is composed of multiple containers, you should group containers that are used for a common purpose into components, and separate the different components into multiple task definitions. For more information, see `Application Architecture`_ in the *Amazon EC2 Container Service Developer Guide* .

                
              

              - **entryPoint** *(list) --* 

                .. warning::

                   

                  Early versions of the Amazon ECS container agent do not properly handle ``entryPoint`` parameters. If you have problems using ``entryPoint`` , update your container agent or enter your commands and arguments as ``command`` array items instead.

                   

                 

                The entry point that is passed to the container. This parameter maps to ``Entrypoint`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--entrypoint`` option to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#entrypoint`_ .

                
                

                - *(string) --* 
            
              

              - **command** *(list) --* 

                The command that is passed to the container. This parameter maps to ``Cmd`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``COMMAND`` parameter to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#cmd`_ .

                
                

                - *(string) --* 
            
              

              - **environment** *(list) --* 

                The environment variables to pass to a container. This parameter maps to ``Env`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--env`` option to `docker run`_ .

                 

                .. warning::

                   

                  We do not recommend using plain text environment variables for sensitive information, such as credential data.

                   

                
                

                - *(dict) --* 

                  A key and value pair object.

                  
                  

                  - **name** *(string) --* 

                    The name of the key value pair. For environment variables, this is the name of the environment variable.

                    
                  

                  - **value** *(string) --* 

                    The value of the key value pair. For environment variables, this is the value of the environment variable.

                    
              
            
              

              - **mountPoints** *(list) --* 

                The mount points for data volumes in your container. This parameter maps to ``Volumes`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volume`` option to `docker run`_ .

                
                

                - *(dict) --* 

                  Details on a volume mount point that is used in a container definition.

                  
                  

                  - **sourceVolume** *(string) --* 

                    The name of the volume to mount.

                    
                  

                  - **containerPath** *(string) --* 

                    The path on the container to mount the host volume at.

                    
                  

                  - **readOnly** *(boolean) --* 

                    If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

                    
              
            
              

              - **volumesFrom** *(list) --* 

                Data volumes to mount from another container. This parameter maps to ``VolumesFrom`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volumes-from`` option to `docker run`_ .

                
                

                - *(dict) --* 

                  Details on a data volume from another container.

                  
                  

                  - **sourceContainer** *(string) --* 

                    The name of the container to mount volumes from.

                    
                  

                  - **readOnly** *(boolean) --* 

                    If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

                    
              
            
              

              - **hostname** *(string) --* 

                The hostname to use for your container. This parameter maps to ``Hostname`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--hostname`` option to `docker run`_ .

                
              

              - **user** *(string) --* 

                The user name to use inside the container. This parameter maps to ``User`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--user`` option to `docker run`_ .

                
              

              - **workingDirectory** *(string) --* 

                The working directory in which to run commands inside the container. This parameter maps to ``WorkingDir`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--workdir`` option to `docker run`_ .

                
              

              - **disableNetworking** *(boolean) --* 

                When this parameter is true, networking is disabled within the container. This parameter maps to ``NetworkDisabled`` in the `Create a container`_ section of the `Docker Remote API`_ .

                
              

              - **privileged** *(boolean) --* 

                When this parameter is true, the container is given elevated privileges on the host container instance (similar to the ``root`` user). This parameter maps to ``Privileged`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--privileged`` option to `docker run`_ .

                
              

              - **readonlyRootFilesystem** *(boolean) --* 

                When this parameter is true, the container is given read-only access to its root file system. This parameter maps to ``ReadonlyRootfs`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--read-only`` option to ``docker run`` .

                
              

              - **dnsServers** *(list) --* 

                A list of DNS servers that are presented to the container. This parameter maps to ``Dns`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns`` option to `docker run`_ .

                
                

                - *(string) --* 
            
              

              - **dnsSearchDomains** *(list) --* 

                A list of DNS search domains that are presented to the container. This parameter maps to ``DnsSearch`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns-search`` option to `docker run`_ .

                
                

                - *(string) --* 
            
              

              - **extraHosts** *(list) --* 

                A list of hostnames and IP address mappings to append to the ``/etc/hosts`` file on the container. This parameter maps to ``ExtraHosts`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--add-host`` option to `docker run`_ .

                
                

                - *(dict) --* 

                  Hostnames and IP address entries that are added to the ``/etc/hosts`` file of a container via the ``extraHosts`` parameter of its  ContainerDefinition . 

                  
                  

                  - **hostname** *(string) --* 

                    The hostname to use in the ``/etc/hosts`` entry.

                    
                  

                  - **ipAddress** *(string) --* 

                    The IP address to use in the ``/etc/hosts`` entry.

                    
              
            
              

              - **dockerSecurityOptions** *(list) --* 

                A list of strings to provide custom labels for SELinux and AppArmor multi-level security systems. This parameter maps to ``SecurityOpt`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--security-opt`` option to `docker run`_ .

                 

                .. note::

                   

                  The Amazon ECS container agent running on a container instance must register with the ``ECS_SELINUX_CAPABLE=true`` or ``ECS_APPARMOR_CAPABLE=true`` environment variables before containers placed on that instance can use these security options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

                   

                
                

                - *(string) --* 
            
              

              - **dockerLabels** *(dict) --* 

                A key/value map of labels to add to the container. This parameter maps to ``Labels`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--label`` option to `docker run`_ . This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **ulimits** *(list) --* 

                A list of ``ulimits`` to set in the container. This parameter maps to ``Ulimits`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--ulimit`` option to `docker run`_ . Valid naming values are displayed in the  Ulimit data type. This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                
                

                - *(dict) --* 

                  The ``ulimit`` settings to pass to the container.

                  
                  

                  - **name** *(string) --* 

                    The ``type`` of the ``ulimit`` .

                    
                  

                  - **softLimit** *(integer) --* 

                    The soft limit for the ulimit type.

                    
                  

                  - **hardLimit** *(integer) --* 

                    The hard limit for the ulimit type.

                    
              
            
              

              - **logConfiguration** *(dict) --* 

                The log configuration specification for the container. This parameter maps to ``LogConfig`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--log-driver`` option to `docker run`_ . By default, containers use the same logging driver that the Docker daemon uses; however the container may use a different logging driver than the Docker daemon by specifying a log driver with this parameter in the container definition. To use a different logging driver for a container, the log system must be configured properly on the container instance (or on a different log server for remote logging options). For more information on the options for different supported log drivers, see `Configure logging drivers`_ in the Docker documentation.

                 

                .. note::

                   

                  Amazon ECS currently supports a subset of the logging drivers available to the Docker daemon (shown in the  LogConfiguration data type). Currently unsupported log drivers may be available in future releases of the Amazon ECS container agent.

                   

                 

                This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                 

                .. note::

                   

                  The Amazon ECS container agent running on a container instance must register the logging drivers available on that instance with the ``ECS_AVAILABLE_LOGGING_DRIVERS`` environment variable before containers placed on that instance can use these log configuration options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

                   

                
                

                - **logDriver** *(string) --* 

                  The log driver to use for the container. The valid values listed for this parameter are log drivers that the Amazon ECS container agent can communicate with by default. 

                   

                  .. note::

                     

                    If you have a custom driver that is not listed above that you would like to work with the Amazon ECS container agent, you can fork the Amazon ECS container agent project that is `available on GitHub`_ and customize it to work with that driver. We encourage you to submit pull requests for changes that you would like to have included. However, Amazon Web Services does not currently provide support for running modified copies of this software.

                     

                   

                  This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                  
                

                - **options** *(dict) --* 

                  The configuration options to send to the log driver. This parameter requires version 1.19 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
          
        
          

          - **family** *(string) --* 

            The family of your task definition, used as the definition name.

            
          

          - **taskRoleArn** *(string) --* 

            The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

            
          

          - **networkMode** *(string) --* 

            The Docker networking mode to use for the containers in the task. The valid values are ``none`` , ``bridge`` , and ``host`` . 

             

            If the network mode is ``none`` , the containers do not have external connectivity. The default Docker network mode is ``bridge`` . The ``host`` network mode offers the highest networking performance for containers because it uses the host network stack instead of the virtualized network stack provided by the ``bridge`` mode.

             

            For more information, see `Network settings`_ in the *Docker run reference* .

            
          

          - **revision** *(integer) --* 

            The revision of the task in a particular family. The revision is a version number of a task definition in a family. When you register a task definition for the first time, the revision is ``1`` ; each time you register a new revision of a task definition in the same family, the revision value always increases by one (even if you have deregistered previous revisions in this family).

            
          

          - **volumes** *(list) --* 

            The list of volumes in a task. For more information about volume definition parameters and defaults, see `Amazon ECS Task Definitions`_ in the *Amazon EC2 Container Service Developer Guide* .

            
            

            - *(dict) --* 

              A data volume used in a task definition.

              
              

              - **name** *(string) --* 

                The name of the volume. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This name is referenced in the ``sourceVolume`` parameter of container definition ``mountPoints`` .

                
              

              - **host** *(dict) --* 

                The contents of the ``host`` parameter determine whether your data volume persists on the host container instance and where it is stored. If the host parameter is empty, then the Docker daemon assigns a host path for your data volume, but the data is not guaranteed to persist after the containers associated with it stop running.

                
                

                - **sourcePath** *(string) --* 

                  The path on the host container instance that is presented to the container. If this parameter is empty, then the Docker daemon has assigned a host path for you. If the ``host`` parameter contains a ``sourcePath`` file location, then the data volume persists at the specified location on the host container instance until you delete it manually. If the ``sourcePath`` value does not exist on the host container instance, the Docker daemon creates it. If the location does exist, the contents of the source path folder are exported.

                  
            
          
        
          

          - **status** *(string) --* 

            The status of the task definition.

            
          

          - **requiresAttributes** *(list) --* 

            The container instance attributes required by your task.

            
            

            - *(dict) --* 

              The attributes applicable to a container instance when it is registered.

              
              

              - **name** *(string) --* 

                The name of the container instance attribute.

                
              

              - **value** *(string) --* 

                The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

                
          
        
      
    

  .. py:method:: describe_clusters(**kwargs)

    

    Describes one or more of your clusters.

    

    **Request Syntax** 
    ::

      response = client.describe_clusters(
          clusters=[
              'string',
          ]
      )
    :type clusters: list
    :param clusters: 

      A space-separated list of up to 100 cluster names or full cluster Amazon Resource Name (ARN) entries. If you do not specify a cluster, the default cluster is assumed.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'clusters': [
                {
                    'clusterArn': 'string',
                    'clusterName': 'string',
                    'status': 'string',
                    'registeredContainerInstancesCount': 123,
                    'runningTasksCount': 123,
                    'pendingTasksCount': 123,
                    'activeServicesCount': 123
                },
            ],
            'failures': [
                {
                    'arn': 'string',
                    'reason': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **clusters** *(list) --* 

          The list of clusters.

          
          

          - *(dict) --* 

            A regional grouping of one or more container instances on which you can run task requests. Each account receives a default cluster the first time you use the Amazon ECS service, but you may also create other clusters. Clusters may contain more than one instance type simultaneously.

            
            

            - **clusterArn** *(string) --* 

              The Amazon Resource Name (ARN) that identifies the cluster. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the cluster, the AWS account ID of the cluster owner, the ``cluster`` namespace, and then the cluster name. For example, ``arn:aws:ecs:*region* :*012345678910* :cluster/*test* `` ..

              
            

            - **clusterName** *(string) --* 

              A user-generated string that you use to identify your cluster.

              
            

            - **status** *(string) --* 

              The status of the cluster. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that you can register container instances with the cluster and the associated instances can accept tasks.

              
            

            - **registeredContainerInstancesCount** *(integer) --* 

              The number of container instances registered into the cluster.

              
            

            - **runningTasksCount** *(integer) --* 

              The number of tasks in the cluster that are in the ``RUNNING`` state.

              
            

            - **pendingTasksCount** *(integer) --* 

              The number of tasks in the cluster that are in the ``PENDING`` state.

              
            

            - **activeServicesCount** *(integer) --* 

              The number of services that are running on the cluster in an ``ACTIVE`` state. You can view these services with  ListServices .

              
        
      
        

        - **failures** *(list) --* 

          Any failures associated with the call.

          
          

          - *(dict) --* 

            A failed resource.

            
            

            - **arn** *(string) --* 

              The Amazon Resource Name (ARN) of the failed resource.

              
            

            - **reason** *(string) --* 

              The reason for the failure.

              
        
      
    

  .. py:method:: describe_container_instances(**kwargs)

    

    Describes Amazon EC2 Container Service container instances. Returns metadata about registered and remaining resources on each container instance requested.

    

    **Request Syntax** 
    ::

      response = client.describe_container_instances(
          cluster='string',
          containerInstances=[
              'string',
          ]
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instances to describe. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type containerInstances: list
    :param containerInstances: **[REQUIRED]** 

      A space-separated list of container instance IDs or full Amazon Resource Name (ARN) entries.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'containerInstances': [
                {
                    'containerInstanceArn': 'string',
                    'ec2InstanceId': 'string',
                    'versionInfo': {
                        'agentVersion': 'string',
                        'agentHash': 'string',
                        'dockerVersion': 'string'
                    },
                    'remainingResources': [
                        {
                            'name': 'string',
                            'type': 'string',
                            'doubleValue': 123.0,
                            'longValue': 123,
                            'integerValue': 123,
                            'stringSetValue': [
                                'string',
                            ]
                        },
                    ],
                    'registeredResources': [
                        {
                            'name': 'string',
                            'type': 'string',
                            'doubleValue': 123.0,
                            'longValue': 123,
                            'integerValue': 123,
                            'stringSetValue': [
                                'string',
                            ]
                        },
                    ],
                    'status': 'string',
                    'agentConnected': True|False,
                    'runningTasksCount': 123,
                    'pendingTasksCount': 123,
                    'agentUpdateStatus': 'PENDING'|'STAGING'|'STAGED'|'UPDATING'|'UPDATED'|'FAILED',
                    'attributes': [
                        {
                            'name': 'string',
                            'value': 'string'
                        },
                    ]
                },
            ],
            'failures': [
                {
                    'arn': 'string',
                    'reason': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **containerInstances** *(list) --* 

          The list of container instances.

          
          

          - *(dict) --* 

            An EC2 instance that is running the Amazon ECS agent and has been registered with a cluster.

            
            

            - **containerInstanceArn** *(string) --* 

              The Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, ``arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* `` .

              
            

            - **ec2InstanceId** *(string) --* 

              The EC2 instance ID of the container instance.

              
            

            - **versionInfo** *(dict) --* 

              The version information for the Amazon ECS container agent and Docker daemon running on the container instance.

              
              

              - **agentVersion** *(string) --* 

                The version number of the Amazon ECS container agent.

                
              

              - **agentHash** *(string) --* 

                The Git commit hash for the Amazon ECS container agent build on the `amazon-ecs-agent`_ GitHub repository.

                
              

              - **dockerVersion** *(string) --* 

                The Docker version running on the container instance.

                
          
            

            - **remainingResources** *(list) --* 

              The remaining resources of the container instance that are available for new tasks.

              
              

              - *(dict) --* 

                Describes the resources available for a container instance.

                
                

                - **name** *(string) --* 

                  The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

                  
                

                - **type** *(string) --* 

                  The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

                  
                

                - **doubleValue** *(float) --* 

                  When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

                  
                

                - **longValue** *(integer) --* 

                  When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

                  
                

                - **integerValue** *(integer) --* 

                  When the ``integerValue`` type is set, the value of the resource must be an integer.

                  
                

                - **stringSetValue** *(list) --* 

                  When the ``stringSetValue`` type is set, the value of the resource must be a string type.

                  
                  

                  - *(string) --* 
              
            
          
            

            - **registeredResources** *(list) --* 

              The registered resources on the container instance that are in use by current tasks.

              
              

              - *(dict) --* 

                Describes the resources available for a container instance.

                
                

                - **name** *(string) --* 

                  The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

                  
                

                - **type** *(string) --* 

                  The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

                  
                

                - **doubleValue** *(float) --* 

                  When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

                  
                

                - **longValue** *(integer) --* 

                  When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

                  
                

                - **integerValue** *(integer) --* 

                  When the ``integerValue`` type is set, the value of the resource must be an integer.

                  
                

                - **stringSetValue** *(list) --* 

                  When the ``stringSetValue`` type is set, the value of the resource must be a string type.

                  
                  

                  - *(string) --* 
              
            
          
            

            - **status** *(string) --* 

              The status of the container instance. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that the container instance can accept tasks.

              
            

            - **agentConnected** *(boolean) --* 

              This parameter returns ``true`` if the agent is actually connected to Amazon ECS. Registered instances with an agent that may be unhealthy or stopped return ``false`` , and instances without a connected agent cannot accept placement requests.

              
            

            - **runningTasksCount** *(integer) --* 

              The number of tasks on the container instance that are in the ``RUNNING`` status.

              
            

            - **pendingTasksCount** *(integer) --* 

              The number of tasks on the container instance that are in the ``PENDING`` status.

              
            

            - **agentUpdateStatus** *(string) --* 

              The status of the most recent agent update. If an update has never been requested, this value is ``NULL`` .

              
            

            - **attributes** *(list) --* 

              The attributes set for the container instance by the Amazon ECS container agent at instance registration.

              
              

              - *(dict) --* 

                The attributes applicable to a container instance when it is registered.

                
                

                - **name** *(string) --* 

                  The name of the container instance attribute.

                  
                

                - **value** *(string) --* 

                  The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

                  
            
          
        
      
        

        - **failures** *(list) --* 

          Any failures associated with the call.

          
          

          - *(dict) --* 

            A failed resource.

            
            

            - **arn** *(string) --* 

              The Amazon Resource Name (ARN) of the failed resource.

              
            

            - **reason** *(string) --* 

              The reason for the failure.

              
        
      
    

  .. py:method:: describe_services(**kwargs)

    

    Describes the specified services running in your cluster.

    

    **Request Syntax** 
    ::

      response = client.describe_services(
          cluster='string',
          services=[
              'string',
          ]
      )
    :type cluster: string
    :param cluster: 

      The name of the cluster that hosts the service to describe. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type services: list
    :param services: **[REQUIRED]** 

      A list of services to describe.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'services': [
                {
                    'serviceArn': 'string',
                    'serviceName': 'string',
                    'clusterArn': 'string',
                    'loadBalancers': [
                        {
                            'targetGroupArn': 'string',
                            'loadBalancerName': 'string',
                            'containerName': 'string',
                            'containerPort': 123
                        },
                    ],
                    'status': 'string',
                    'desiredCount': 123,
                    'runningCount': 123,
                    'pendingCount': 123,
                    'taskDefinition': 'string',
                    'deploymentConfiguration': {
                        'maximumPercent': 123,
                        'minimumHealthyPercent': 123
                    },
                    'deployments': [
                        {
                            'id': 'string',
                            'status': 'string',
                            'taskDefinition': 'string',
                            'desiredCount': 123,
                            'pendingCount': 123,
                            'runningCount': 123,
                            'createdAt': datetime(2015, 1, 1),
                            'updatedAt': datetime(2015, 1, 1)
                        },
                    ],
                    'roleArn': 'string',
                    'events': [
                        {
                            'id': 'string',
                            'createdAt': datetime(2015, 1, 1),
                            'message': 'string'
                        },
                    ],
                    'createdAt': datetime(2015, 1, 1)
                },
            ],
            'failures': [
                {
                    'arn': 'string',
                    'reason': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **services** *(list) --* 

          The list of services described.

          
          

          - *(dict) --* 

            Details on a service within a cluster

            
            

            - **serviceArn** *(string) --* 

              The Amazon Resource Name (ARN) that identifies the service. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the service, the AWS account ID of the service owner, the ``service`` namespace, and then the service name. For example, ``arn:aws:ecs:*region* :*012345678910* :service/*my-service* `` .

              
            

            - **serviceName** *(string) --* 

              The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a region or across multiple regions.

              
            

            - **clusterArn** *(string) --* 

              The Amazon Resource Name (ARN) of the cluster that hosts the service.

              
            

            - **loadBalancers** *(list) --* 

              A list of Elastic Load Balancing load balancer objects, containing the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer.

              
              

              - *(dict) --* 

                Details on a load balancer that is used with a service.

                
                

                - **targetGroupArn** *(string) --* 

                  The full Amazon Resource Name (ARN) of the Elastic Load Balancing target group associated with a service.

                  
                

                - **loadBalancerName** *(string) --* 

                  The name of the load balancer.

                  
                

                - **containerName** *(string) --* 

                  The name of the container (as it appears in a container definition) to associate with the load balancer.

                  
                

                - **containerPort** *(integer) --* 

                  The port on the container to associate with the load balancer. This port must correspond to a ``containerPort`` in the service's task definition. Your container instances must allow ingress traffic on the ``hostPort`` of the port mapping.

                  
            
          
            

            - **status** *(string) --* 

              The status of the service. The valid values are ``ACTIVE`` , ``DRAINING`` , or ``INACTIVE`` .

              
            

            - **desiredCount** *(integer) --* 

              The desired number of instantiations of the task definition to keep running on the service. This value is specified when the service is created with  CreateService , and it can be modified with  UpdateService .

              
            

            - **runningCount** *(integer) --* 

              The number of tasks in the cluster that are in the ``RUNNING`` state.

              
            

            - **pendingCount** *(integer) --* 

              The number of tasks in the cluster that are in the ``PENDING`` state.

              
            

            - **taskDefinition** *(string) --* 

              The task definition to use for tasks in the service. This value is specified when the service is created with  CreateService , and it can be modified with  UpdateService .

              
            

            - **deploymentConfiguration** *(dict) --* 

              Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

              
              

              - **maximumPercent** *(integer) --* 

                The upper limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that can be running in a service during a deployment. The maximum number of tasks during a deployment is the ``desiredCount`` multiplied by the ``maximumPercent`` /100, rounded down to the nearest integer value.

                
              

              - **minimumHealthyPercent** *(integer) --* 

                The lower limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that must remain running and healthy in a service during a deployment. The minimum healthy tasks during a deployment is the ``desiredCount`` multiplied by the ``minimumHealthyPercent`` /100, rounded up to the nearest integer value.

                
          
            

            - **deployments** *(list) --* 

              The current state of deployments for the service.

              
              

              - *(dict) --* 

                The details of an Amazon ECS service deployment.

                
                

                - **id** *(string) --* 

                  The ID of the deployment.

                  
                

                - **status** *(string) --* 

                  The status of the deployment. Valid values are ``PRIMARY`` (for the most recent deployment), ``ACTIVE`` (for previous deployments that still have tasks running, but are being replaced with the ``PRIMARY`` deployment), and ``INACTIVE`` (for deployments that have been completely replaced).

                  
                

                - **taskDefinition** *(string) --* 

                  The most recent task definition that was specified for the service to use.

                  
                

                - **desiredCount** *(integer) --* 

                  The most recent desired count of tasks that was specified for the service to deploy or maintain.

                  
                

                - **pendingCount** *(integer) --* 

                  The number of tasks in the deployment that are in the ``PENDING`` status.

                  
                

                - **runningCount** *(integer) --* 

                  The number of tasks in the deployment that are in the ``RUNNING`` status.

                  
                

                - **createdAt** *(datetime) --* 

                  The Unix timestamp for when the service was created.

                  
                

                - **updatedAt** *(datetime) --* 

                  The Unix timestamp for when the service was last updated.

                  
            
          
            

            - **roleArn** *(string) --* 

              The Amazon Resource Name (ARN) of the IAM role associated with the service that allows the Amazon ECS container agent to register container instances with an Elastic Load Balancing load balancer.

              
            

            - **events** *(list) --* 

              The event stream for your service. A maximum of 100 of the latest events are displayed.

              
              

              - *(dict) --* 

                Details on an event associated with a service.

                
                

                - **id** *(string) --* 

                  The ID string of the event.

                  
                

                - **createdAt** *(datetime) --* 

                  The Unix timestamp for when the event was triggered.

                  
                

                - **message** *(string) --* 

                  The event message.

                  
            
          
            

            - **createdAt** *(datetime) --* 

              The Unix timestamp for when the service was created.

              
        
      
        

        - **failures** *(list) --* 

          Any failures associated with the call.

          
          

          - *(dict) --* 

            A failed resource.

            
            

            - **arn** *(string) --* 

              The Amazon Resource Name (ARN) of the failed resource.

              
            

            - **reason** *(string) --* 

              The reason for the failure.

              
        
      
    

  .. py:method:: describe_task_definition(**kwargs)

    

    Describes a task definition. You can specify a ``family`` and ``revision`` to find information about a specific task definition, or you can simply specify the family to find the latest ``ACTIVE`` revision in that family.

     

    .. note::

       

      You can only describe ``INACTIVE`` task definitions while an active task or service references them.

       

    

    **Request Syntax** 
    ::

      response = client.describe_task_definition(
          taskDefinition='string'
      )
    :type taskDefinition: string
    :param taskDefinition: **[REQUIRED]** 

      The ``family`` for the latest ``ACTIVE`` revision, ``family`` and ``revision`` (``family:revision`` ) for a specific revision in the family, or full Amazon Resource Name (ARN) of the task definition to describe.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'taskDefinition': {
                'taskDefinitionArn': 'string',
                'containerDefinitions': [
                    {
                        'name': 'string',
                        'image': 'string',
                        'cpu': 123,
                        'memory': 123,
                        'memoryReservation': 123,
                        'links': [
                            'string',
                        ],
                        'portMappings': [
                            {
                                'containerPort': 123,
                                'hostPort': 123,
                                'protocol': 'tcp'|'udp'
                            },
                        ],
                        'essential': True|False,
                        'entryPoint': [
                            'string',
                        ],
                        'command': [
                            'string',
                        ],
                        'environment': [
                            {
                                'name': 'string',
                                'value': 'string'
                            },
                        ],
                        'mountPoints': [
                            {
                                'sourceVolume': 'string',
                                'containerPath': 'string',
                                'readOnly': True|False
                            },
                        ],
                        'volumesFrom': [
                            {
                                'sourceContainer': 'string',
                                'readOnly': True|False
                            },
                        ],
                        'hostname': 'string',
                        'user': 'string',
                        'workingDirectory': 'string',
                        'disableNetworking': True|False,
                        'privileged': True|False,
                        'readonlyRootFilesystem': True|False,
                        'dnsServers': [
                            'string',
                        ],
                        'dnsSearchDomains': [
                            'string',
                        ],
                        'extraHosts': [
                            {
                                'hostname': 'string',
                                'ipAddress': 'string'
                            },
                        ],
                        'dockerSecurityOptions': [
                            'string',
                        ],
                        'dockerLabels': {
                            'string': 'string'
                        },
                        'ulimits': [
                            {
                                'name': 'core'|'cpu'|'data'|'fsize'|'locks'|'memlock'|'msgqueue'|'nice'|'nofile'|'nproc'|'rss'|'rtprio'|'rttime'|'sigpending'|'stack',
                                'softLimit': 123,
                                'hardLimit': 123
                            },
                        ],
                        'logConfiguration': {
                            'logDriver': 'json-file'|'syslog'|'journald'|'gelf'|'fluentd'|'awslogs'|'splunk',
                            'options': {
                                'string': 'string'
                            }
                        }
                    },
                ],
                'family': 'string',
                'taskRoleArn': 'string',
                'networkMode': 'bridge'|'host'|'none',
                'revision': 123,
                'volumes': [
                    {
                        'name': 'string',
                        'host': {
                            'sourcePath': 'string'
                        }
                    },
                ],
                'status': 'ACTIVE'|'INACTIVE',
                'requiresAttributes': [
                    {
                        'name': 'string',
                        'value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **taskDefinition** *(dict) --* 

          The full task definition description.

          
          

          - **taskDefinitionArn** *(string) --* 

            The full Amazon Resource Name (ARN) of the task definition.

            
          

          - **containerDefinitions** *(list) --* 

            A list of container definitions in JSON format that describe the different containers that make up your task. For more information about container definition parameters and defaults, see `Amazon ECS Task Definitions`_ in the *Amazon EC2 Container Service Developer Guide* .

            
            

            - *(dict) --* 

              Container definitions are used in task definitions to describe the different containers that are launched as part of a task.

              
              

              - **name** *(string) --* 

                The name of a container. If you are linking multiple containers together in a task definition, the ``name`` of one container can be entered in the ``links`` of another container to connect the containers. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This parameter maps to ``name`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--name`` option to `docker run`_ . 

                
              

              - **image** *(string) --* 

                The image used to start a container. This string is passed directly to the Docker daemon. Images in the Docker Hub registry are available by default. Other repositories are specified with `` *repository-url* /*image* :*tag* `` . Up to 255 letters (uppercase and lowercase), numbers, hyphens, underscores, colons, periods, forward slashes, and number signs are allowed. This parameter maps to ``Image`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``IMAGE`` parameter of `docker run`_ .

                 

                 
                * Images in official repositories on Docker Hub use a single name (for example, ``ubuntu`` or ``mongo`` ). 
                 
                * Images in other repositories on Docker Hub are qualified with an organization name (for example, ``amazon/amazon-ecs-agent`` ). 
                 
                * Images in other online repositories are qualified further by a domain name (for example, ``quay.io/assemblyline/ubuntu`` ). 
                 

                
              

              - **cpu** *(integer) --* 

                The number of ``cpu`` units reserved for the container. A container instance has 1,024 ``cpu`` units for every CPU core. This parameter specifies the minimum amount of CPU to reserve for a container, and containers share unallocated CPU units with other containers on the instance with the same ratio as their allocated amount. This parameter maps to ``CpuShares`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--cpu-shares`` option to `docker run`_ .

                 

                .. note::

                   

                  You can determine the number of CPU units that are available per EC2 instance type by multiplying the vCPUs listed for that instance type on the `Amazon EC2 Instances`_ detail page by 1,024.

                   

                 

                For example, if you run a single-container task on a single-core instance type with 512 CPU units specified for that container, and that is the only task running on the container instance, that container could use the full 1,024 CPU unit share at any given time. However, if you launched another copy of the same task on that container instance, each task would be guaranteed a minimum of 512 CPU units when needed, and each container could float to higher CPU usage if the other container was not using it, but if both tasks were 100% active all of the time, they would be limited to 512 CPU units.

                 

                The Docker daemon on the container instance uses the CPU value to calculate the relative CPU share ratios for running containers. For more information, see `CPU share constraint`_ in the Docker documentation. The minimum valid CPU share value that the Linux kernel allows is 2; however, the CPU parameter is not required, and you can use CPU values below 2 in your container definitions. For CPU values below 2 (including null), the behavior varies based on your Amazon ECS container agent version:

                 

                 
                * **Agent versions less than or equal to 1.1.0:** Null and zero CPU values are passed to Docker as 0, which Docker then converts to 1,024 CPU shares. CPU values of 1 are passed to Docker as 1, which the Linux kernel converts to 2 CPU shares. 
                 
                * **Agent versions greater than or equal to 1.2.0:** Null, zero, and CPU values of 1 are passed to Docker as 2. 
                 

                
              

              - **memory** *(integer) --* 

                The hard limit (in MiB) of memory to present to the container. If your container attempts to exceed the memory specified here, the container is killed. This parameter maps to ``Memory`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--memory`` option to `docker run`_ .

                 

                You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

                 

                The Docker daemon reserves a minimum of 4 MiB of memory for a container, so you should not specify fewer than 4 MiB of memory for your containers. 

                
              

              - **memoryReservation** *(integer) --* 

                The soft limit (in MiB) of memory to reserve for the container. When system memory is under heavy contention, Docker attempts to keep the container memory to this soft limit; however, your container can consume more memory when it needs to, up to either the hard limit specified with the ``memory`` parameter (if applicable), or all of the available memory on the container instance, whichever comes first. This parameter maps to ``MemoryReservation`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--memory-reservation`` option to `docker run`_ .

                 

                You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

                 

                For example, if your container normally uses 128 MiB of memory, but occasionally bursts to 256 MiB of memory for short periods of time, you can set a ``memoryReservation`` of 128 MiB, and a ``memory`` hard limit of 300 MiB. This configuration would allow the container to only reserve 128 MiB of memory from the remaining resources on the container instance, but also allow the container to consume more memory resources when needed.

                
              

              - **links** *(list) --* 

                The ``link`` parameter allows containers to communicate with each other without the need for port mappings, using the ``name`` parameter and optionally, an ``alias`` for the link. This construct is analogous to ``name:alias`` in Docker links. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed for each ``name`` and ``alias`` . For more information on linking Docker containers, see `https\://docs.docker.com/userguide/dockerlinks/`_ . This parameter maps to ``Links`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--link`` option to `docker run`_ .

                 

                .. warning::

                   

                  Containers that are collocated on a single container instance may be able to communicate with each other without requiring links or host port mappings. Network isolation is achieved on the container instance using security groups and VPC settings.

                   

                
                

                - *(string) --* 
            
              

              - **portMappings** *(list) --* 

                The list of port mappings for the container. Port mappings allow containers to access ports on the host container instance to send or receive traffic. This parameter maps to ``PortBindings`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--publish`` option to `docker run`_ . If the network mode of a task definition is set to ``none`` , then you cannot specify port mappings. If the network mode of a task definition is set to ``host`` , then host ports must either be undefined or they must match the container port in the port mapping.

                 

                .. note::

                   

                  After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the **Network Bindings** section of a container description of a selected task in the Amazon ECS console, or the ``networkBindings`` section  DescribeTasks responses.

                   

                
                

                - *(dict) --* 

                  Port mappings allow containers to access ports on the host container instance to send or receive traffic. Port mappings are specified as part of the container definition. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  DescribeTasks API responses.

                  
                  

                  - **containerPort** *(integer) --* 

                    The port number on the container that is bound to the user-specified or automatically assigned host port. If you specify a container port and not a host port, your container automatically receives a host port in the ephemeral port range (for more information, see ``hostPort`` ). Port mappings that are automatically assigned in this way do not count toward the 100 reserved ports limit of a container instance.

                    
                  

                  - **hostPort** *(integer) --* 

                    The port number on the container instance to reserve for your container. You can specify a non-reserved host port for your container port mapping, or you can omit the ``hostPort`` (or set it to ``0`` ) while specifying a ``containerPort`` and your container automatically receives a port in the ephemeral port range for your container instance operating system and Docker version.

                     

                    The default ephemeral port range is 49153 to 65535, and this range is used for Docker versions prior to 1.6.0. For Docker version 1.6.0 and later, the Docker daemon tries to read the ephemeral port range from ``/proc/sys/net/ipv4/ip_local_port_range`` ; if this kernel parameter is unavailable, the default ephemeral port range is used. You should not attempt to specify a host port in the ephemeral port range, because these are reserved for automatic assignment. In general, ports below 32768 are outside of the ephemeral port range.

                     

                    The default reserved ports are 22 for SSH, the Docker ports 2375 and 2376, and the Amazon ECS container agent port 51678. Any host port that was previously specified in a running task is also reserved while the task is running (after a task stops, the host port is released).The current reserved ports are displayed in the ``remainingResources`` of  DescribeContainerInstances output, and a container instance may have up to 100 reserved ports at a time, including the default reserved ports (automatically assigned ports do not count toward the 100 reserved ports limit).

                    
                  

                  - **protocol** *(string) --* 

                    The protocol used for the port mapping. Valid values are ``tcp`` and ``udp`` . The default is ``tcp`` .

                    
              
            
              

              - **essential** *(boolean) --* 

                If the ``essential`` parameter of a container is marked as ``true`` , and that container fails or stops for any reason, all other containers that are part of the task are stopped. If the ``essential`` parameter of a container is marked as ``false`` , then its failure does not affect the rest of the containers in a task. If this parameter is omitted, a container is assumed to be essential.

                 

                All tasks must have at least one essential container. If you have an application that is composed of multiple containers, you should group containers that are used for a common purpose into components, and separate the different components into multiple task definitions. For more information, see `Application Architecture`_ in the *Amazon EC2 Container Service Developer Guide* .

                
              

              - **entryPoint** *(list) --* 

                .. warning::

                   

                  Early versions of the Amazon ECS container agent do not properly handle ``entryPoint`` parameters. If you have problems using ``entryPoint`` , update your container agent or enter your commands and arguments as ``command`` array items instead.

                   

                 

                The entry point that is passed to the container. This parameter maps to ``Entrypoint`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--entrypoint`` option to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#entrypoint`_ .

                
                

                - *(string) --* 
            
              

              - **command** *(list) --* 

                The command that is passed to the container. This parameter maps to ``Cmd`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``COMMAND`` parameter to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#cmd`_ .

                
                

                - *(string) --* 
            
              

              - **environment** *(list) --* 

                The environment variables to pass to a container. This parameter maps to ``Env`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--env`` option to `docker run`_ .

                 

                .. warning::

                   

                  We do not recommend using plain text environment variables for sensitive information, such as credential data.

                   

                
                

                - *(dict) --* 

                  A key and value pair object.

                  
                  

                  - **name** *(string) --* 

                    The name of the key value pair. For environment variables, this is the name of the environment variable.

                    
                  

                  - **value** *(string) --* 

                    The value of the key value pair. For environment variables, this is the value of the environment variable.

                    
              
            
              

              - **mountPoints** *(list) --* 

                The mount points for data volumes in your container. This parameter maps to ``Volumes`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volume`` option to `docker run`_ .

                
                

                - *(dict) --* 

                  Details on a volume mount point that is used in a container definition.

                  
                  

                  - **sourceVolume** *(string) --* 

                    The name of the volume to mount.

                    
                  

                  - **containerPath** *(string) --* 

                    The path on the container to mount the host volume at.

                    
                  

                  - **readOnly** *(boolean) --* 

                    If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

                    
              
            
              

              - **volumesFrom** *(list) --* 

                Data volumes to mount from another container. This parameter maps to ``VolumesFrom`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volumes-from`` option to `docker run`_ .

                
                

                - *(dict) --* 

                  Details on a data volume from another container.

                  
                  

                  - **sourceContainer** *(string) --* 

                    The name of the container to mount volumes from.

                    
                  

                  - **readOnly** *(boolean) --* 

                    If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

                    
              
            
              

              - **hostname** *(string) --* 

                The hostname to use for your container. This parameter maps to ``Hostname`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--hostname`` option to `docker run`_ .

                
              

              - **user** *(string) --* 

                The user name to use inside the container. This parameter maps to ``User`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--user`` option to `docker run`_ .

                
              

              - **workingDirectory** *(string) --* 

                The working directory in which to run commands inside the container. This parameter maps to ``WorkingDir`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--workdir`` option to `docker run`_ .

                
              

              - **disableNetworking** *(boolean) --* 

                When this parameter is true, networking is disabled within the container. This parameter maps to ``NetworkDisabled`` in the `Create a container`_ section of the `Docker Remote API`_ .

                
              

              - **privileged** *(boolean) --* 

                When this parameter is true, the container is given elevated privileges on the host container instance (similar to the ``root`` user). This parameter maps to ``Privileged`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--privileged`` option to `docker run`_ .

                
              

              - **readonlyRootFilesystem** *(boolean) --* 

                When this parameter is true, the container is given read-only access to its root file system. This parameter maps to ``ReadonlyRootfs`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--read-only`` option to ``docker run`` .

                
              

              - **dnsServers** *(list) --* 

                A list of DNS servers that are presented to the container. This parameter maps to ``Dns`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns`` option to `docker run`_ .

                
                

                - *(string) --* 
            
              

              - **dnsSearchDomains** *(list) --* 

                A list of DNS search domains that are presented to the container. This parameter maps to ``DnsSearch`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns-search`` option to `docker run`_ .

                
                

                - *(string) --* 
            
              

              - **extraHosts** *(list) --* 

                A list of hostnames and IP address mappings to append to the ``/etc/hosts`` file on the container. This parameter maps to ``ExtraHosts`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--add-host`` option to `docker run`_ .

                
                

                - *(dict) --* 

                  Hostnames and IP address entries that are added to the ``/etc/hosts`` file of a container via the ``extraHosts`` parameter of its  ContainerDefinition . 

                  
                  

                  - **hostname** *(string) --* 

                    The hostname to use in the ``/etc/hosts`` entry.

                    
                  

                  - **ipAddress** *(string) --* 

                    The IP address to use in the ``/etc/hosts`` entry.

                    
              
            
              

              - **dockerSecurityOptions** *(list) --* 

                A list of strings to provide custom labels for SELinux and AppArmor multi-level security systems. This parameter maps to ``SecurityOpt`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--security-opt`` option to `docker run`_ .

                 

                .. note::

                   

                  The Amazon ECS container agent running on a container instance must register with the ``ECS_SELINUX_CAPABLE=true`` or ``ECS_APPARMOR_CAPABLE=true`` environment variables before containers placed on that instance can use these security options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

                   

                
                

                - *(string) --* 
            
              

              - **dockerLabels** *(dict) --* 

                A key/value map of labels to add to the container. This parameter maps to ``Labels`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--label`` option to `docker run`_ . This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **ulimits** *(list) --* 

                A list of ``ulimits`` to set in the container. This parameter maps to ``Ulimits`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--ulimit`` option to `docker run`_ . Valid naming values are displayed in the  Ulimit data type. This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                
                

                - *(dict) --* 

                  The ``ulimit`` settings to pass to the container.

                  
                  

                  - **name** *(string) --* 

                    The ``type`` of the ``ulimit`` .

                    
                  

                  - **softLimit** *(integer) --* 

                    The soft limit for the ulimit type.

                    
                  

                  - **hardLimit** *(integer) --* 

                    The hard limit for the ulimit type.

                    
              
            
              

              - **logConfiguration** *(dict) --* 

                The log configuration specification for the container. This parameter maps to ``LogConfig`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--log-driver`` option to `docker run`_ . By default, containers use the same logging driver that the Docker daemon uses; however the container may use a different logging driver than the Docker daemon by specifying a log driver with this parameter in the container definition. To use a different logging driver for a container, the log system must be configured properly on the container instance (or on a different log server for remote logging options). For more information on the options for different supported log drivers, see `Configure logging drivers`_ in the Docker documentation.

                 

                .. note::

                   

                  Amazon ECS currently supports a subset of the logging drivers available to the Docker daemon (shown in the  LogConfiguration data type). Currently unsupported log drivers may be available in future releases of the Amazon ECS container agent.

                   

                 

                This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                 

                .. note::

                   

                  The Amazon ECS container agent running on a container instance must register the logging drivers available on that instance with the ``ECS_AVAILABLE_LOGGING_DRIVERS`` environment variable before containers placed on that instance can use these log configuration options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

                   

                
                

                - **logDriver** *(string) --* 

                  The log driver to use for the container. The valid values listed for this parameter are log drivers that the Amazon ECS container agent can communicate with by default. 

                   

                  .. note::

                     

                    If you have a custom driver that is not listed above that you would like to work with the Amazon ECS container agent, you can fork the Amazon ECS container agent project that is `available on GitHub`_ and customize it to work with that driver. We encourage you to submit pull requests for changes that you would like to have included. However, Amazon Web Services does not currently provide support for running modified copies of this software.

                     

                   

                  This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                  
                

                - **options** *(dict) --* 

                  The configuration options to send to the log driver. This parameter requires version 1.19 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
          
        
          

          - **family** *(string) --* 

            The family of your task definition, used as the definition name.

            
          

          - **taskRoleArn** *(string) --* 

            The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

            
          

          - **networkMode** *(string) --* 

            The Docker networking mode to use for the containers in the task. The valid values are ``none`` , ``bridge`` , and ``host`` . 

             

            If the network mode is ``none`` , the containers do not have external connectivity. The default Docker network mode is ``bridge`` . The ``host`` network mode offers the highest networking performance for containers because it uses the host network stack instead of the virtualized network stack provided by the ``bridge`` mode.

             

            For more information, see `Network settings`_ in the *Docker run reference* .

            
          

          - **revision** *(integer) --* 

            The revision of the task in a particular family. The revision is a version number of a task definition in a family. When you register a task definition for the first time, the revision is ``1`` ; each time you register a new revision of a task definition in the same family, the revision value always increases by one (even if you have deregistered previous revisions in this family).

            
          

          - **volumes** *(list) --* 

            The list of volumes in a task. For more information about volume definition parameters and defaults, see `Amazon ECS Task Definitions`_ in the *Amazon EC2 Container Service Developer Guide* .

            
            

            - *(dict) --* 

              A data volume used in a task definition.

              
              

              - **name** *(string) --* 

                The name of the volume. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This name is referenced in the ``sourceVolume`` parameter of container definition ``mountPoints`` .

                
              

              - **host** *(dict) --* 

                The contents of the ``host`` parameter determine whether your data volume persists on the host container instance and where it is stored. If the host parameter is empty, then the Docker daemon assigns a host path for your data volume, but the data is not guaranteed to persist after the containers associated with it stop running.

                
                

                - **sourcePath** *(string) --* 

                  The path on the host container instance that is presented to the container. If this parameter is empty, then the Docker daemon has assigned a host path for you. If the ``host`` parameter contains a ``sourcePath`` file location, then the data volume persists at the specified location on the host container instance until you delete it manually. If the ``sourcePath`` value does not exist on the host container instance, the Docker daemon creates it. If the location does exist, the contents of the source path folder are exported.

                  
            
          
        
          

          - **status** *(string) --* 

            The status of the task definition.

            
          

          - **requiresAttributes** *(list) --* 

            The container instance attributes required by your task.

            
            

            - *(dict) --* 

              The attributes applicable to a container instance when it is registered.

              
              

              - **name** *(string) --* 

                The name of the container instance attribute.

                
              

              - **value** *(string) --* 

                The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

                
          
        
      
    

  .. py:method:: describe_tasks(**kwargs)

    

    Describes a specified task or tasks.

    

    **Request Syntax** 
    ::

      response = client.describe_tasks(
          cluster='string',
          tasks=[
              'string',
          ]
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task to describe. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type tasks: list
    :param tasks: **[REQUIRED]** 

      A space-separated list of task IDs or full Amazon Resource Name (ARN) entries.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'tasks': [
                {
                    'taskArn': 'string',
                    'clusterArn': 'string',
                    'taskDefinitionArn': 'string',
                    'containerInstanceArn': 'string',
                    'overrides': {
                        'containerOverrides': [
                            {
                                'name': 'string',
                                'command': [
                                    'string',
                                ],
                                'environment': [
                                    {
                                        'name': 'string',
                                        'value': 'string'
                                    },
                                ]
                            },
                        ],
                        'taskRoleArn': 'string'
                    },
                    'lastStatus': 'string',
                    'desiredStatus': 'string',
                    'containers': [
                        {
                            'containerArn': 'string',
                            'taskArn': 'string',
                            'name': 'string',
                            'lastStatus': 'string',
                            'exitCode': 123,
                            'reason': 'string',
                            'networkBindings': [
                                {
                                    'bindIP': 'string',
                                    'containerPort': 123,
                                    'hostPort': 123,
                                    'protocol': 'tcp'|'udp'
                                },
                            ]
                        },
                    ],
                    'startedBy': 'string',
                    'stoppedReason': 'string',
                    'createdAt': datetime(2015, 1, 1),
                    'startedAt': datetime(2015, 1, 1),
                    'stoppedAt': datetime(2015, 1, 1)
                },
            ],
            'failures': [
                {
                    'arn': 'string',
                    'reason': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **tasks** *(list) --* 

          The list of tasks.

          
          

          - *(dict) --* 

            Details on a task in a cluster.

            
            

            - **taskArn** *(string) --* 

              The Amazon Resource Name (ARN) of the task.

              
            

            - **clusterArn** *(string) --* 

              The Amazon Resource Name (ARN) of the cluster that hosts the task.

              
            

            - **taskDefinitionArn** *(string) --* 

              The Amazon Resource Name (ARN) of the task definition that creates the task.

              
            

            - **containerInstanceArn** *(string) --* 

              The Amazon Resource Name (ARN) of the container instances that host the task.

              
            

            - **overrides** *(dict) --* 

              One or more container overrides.

              
              

              - **containerOverrides** *(list) --* 

                One or more container overrides sent to a task.

                
                

                - *(dict) --* 

                  The overrides that should be sent to a container.

                  
                  

                  - **name** *(string) --* 

                    The name of the container that receives the override.

                    
                  

                  - **command** *(list) --* 

                    The command to send to the container that overrides the default command from the Docker image or the task definition.

                    
                    

                    - *(string) --* 
                
                  

                  - **environment** *(list) --* 

                    The environment variables to send to the container. You can add new environment variables, which are added to the container at launch, or you can override the existing environment variables from the Docker image or the task definition.

                    
                    

                    - *(dict) --* 

                      A key and value pair object.

                      
                      

                      - **name** *(string) --* 

                        The name of the key value pair. For environment variables, this is the name of the environment variable.

                        
                      

                      - **value** *(string) --* 

                        The value of the key value pair. For environment variables, this is the value of the environment variable.

                        
                  
                
              
            
              

              - **taskRoleArn** *(string) --* 

                The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

                
          
            

            - **lastStatus** *(string) --* 

              The last known status of the task.

              
            

            - **desiredStatus** *(string) --* 

              The desired status of the task.

              
            

            - **containers** *(list) --* 

              The containers associated with the task.

              
              

              - *(dict) --* 

                A Docker container that is part of a task.

                
                

                - **containerArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the container.

                  
                

                - **taskArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the task.

                  
                

                - **name** *(string) --* 

                  The name of the container.

                  
                

                - **lastStatus** *(string) --* 

                  The last known status of the container.

                  
                

                - **exitCode** *(integer) --* 

                  The exit code returned from the container.

                  
                

                - **reason** *(string) --* 

                  A short (255 max characters) human-readable string to provide additional detail about a running or stopped container.

                  
                

                - **networkBindings** *(list) --* 

                  The network bindings associated with the container.

                  
                  

                  - *(dict) --* 

                    Details on the network bindings between a container and its host container instance. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  DescribeTasks API responses.

                    
                    

                    - **bindIP** *(string) --* 

                      The IP address that the container is bound to on the container instance.

                      
                    

                    - **containerPort** *(integer) --* 

                      The port number on the container that is be used with the network binding.

                      
                    

                    - **hostPort** *(integer) --* 

                      The port number on the host that is used with the network binding.

                      
                    

                    - **protocol** *(string) --* 

                      The protocol used for the network binding.

                      
                
              
            
          
            

            - **startedBy** *(string) --* 

              The tag specified when a task is started. If the task is started by an Amazon ECS service, then the ``startedBy`` parameter contains the deployment ID of the service that starts it.

              
            

            - **stoppedReason** *(string) --* 

              The reason the task was stopped.

              
            

            - **createdAt** *(datetime) --* 

              The Unix timestamp for when the task was created (the task entered the ``PENDING`` state).

              
            

            - **startedAt** *(datetime) --* 

              The Unix timestamp for when the task was started (the task transitioned from the ``PENDING`` state to the ``RUNNING`` state).

              
            

            - **stoppedAt** *(datetime) --* 

              The Unix timestamp for when the task was stopped (the task transitioned from the ``RUNNING`` state to the ``STOPPED`` state).

              
        
      
        

        - **failures** *(list) --* 

          Any failures associated with the call.

          
          

          - *(dict) --* 

            A failed resource.

            
            

            - **arn** *(string) --* 

              The Amazon Resource Name (ARN) of the failed resource.

              
            

            - **reason** *(string) --* 

              The reason for the failure.

              
        
      
    

  .. py:method:: discover_poll_endpoint(**kwargs)

    

    .. note::

       

      This action is only used by the Amazon EC2 Container Service agent, and it is not intended for use outside of the agent.

       

     

    Returns an endpoint for the Amazon EC2 Container Service agent to poll for updates.

    

    **Request Syntax** 
    ::

      response = client.discover_poll_endpoint(
          containerInstance='string',
          cluster='string'
      )
    :type containerInstance: string
    :param containerInstance: 

      The container instance ID or full Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, ``arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* `` .

      

    
    :type cluster: string
    :param cluster: 

      The cluster that the container instance belongs to.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'endpoint': 'string',
            'telemetryEndpoint': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **endpoint** *(string) --* 

          The endpoint for the Amazon ECS agent to poll.

          
        

        - **telemetryEndpoint** *(string) --* 

          The telemetry endpoint for the Amazon ECS agent.

          
    

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

        


  .. py:method:: list_clusters(**kwargs)

    

    Returns a list of existing clusters.

    

    **Request Syntax** 
    ::

      response = client.list_clusters(
          nextToken='string',
          maxResults=123
      )
    :type nextToken: string
    :param nextToken: 

      The ``nextToken`` value returned from a previous paginated ``ListClusters`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

       

      .. note::

         

        This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

         

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of cluster results returned by ``ListClusters`` in paginated output. When this parameter is used, ``ListClusters`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``ListClusters`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``ListClusters`` returns up to 100 results and a ``nextToken`` value if applicable.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'clusterArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **clusterArns** *(list) --* 

          The list of full Amazon Resource Name (ARN) entries for each cluster associated with your account.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          The ``nextToken`` value to include in a future ``ListClusters`` request. When the results of a ``ListClusters`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

  .. py:method:: list_container_instances(**kwargs)

    

    Returns a list of container instances in a specified cluster.

    

    **Request Syntax** 
    ::

      response = client.list_container_instances(
          cluster='string',
          nextToken='string',
          maxResults=123
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instances to list. If you do not specify a cluster, the default cluster is assumed..

      

    
    :type nextToken: string
    :param nextToken: 

      The ``nextToken`` value returned from a previous paginated ``ListContainerInstances`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

       

      .. note::

         

        This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

         

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of container instance results returned by ``ListContainerInstances`` in paginated output. When this parameter is used, ``ListContainerInstances`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``ListContainerInstances`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``ListContainerInstances`` returns up to 100 results and a ``nextToken`` value if applicable.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'containerInstanceArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **containerInstanceArns** *(list) --* 

          The list of container instances with full Amazon Resource Name (ARN) entries for each container instance associated with the specified cluster.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          The ``nextToken`` value to include in a future ``ListContainerInstances`` request. When the results of a ``ListContainerInstances`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

  .. py:method:: list_services(**kwargs)

    

    Lists the services that are running in a specified cluster.

    

    **Request Syntax** 
    ::

      response = client.list_services(
          cluster='string',
          nextToken='string',
          maxResults=123
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the services to list. If you do not specify a cluster, the default cluster is assumed..

      

    
    :type nextToken: string
    :param nextToken: 

      The ``nextToken`` value returned from a previous paginated ``ListServices`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

       

      .. note::

         

        This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

         

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of container instance results returned by ``ListServices`` in paginated output. When this parameter is used, ``ListServices`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``ListServices`` request with the returned ``nextToken`` value. This value can be between 1 and 10. If this parameter is not used, then ``ListServices`` returns up to 10 results and a ``nextToken`` value if applicable.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'serviceArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **serviceArns** *(list) --* 

          The list of full Amazon Resource Name (ARN) entries for each service associated with the specified cluster.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          The ``nextToken`` value to include in a future ``ListServices`` request. When the results of a ``ListServices`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

  .. py:method:: list_task_definition_families(**kwargs)

    

    Returns a list of task definition families that are registered to your account (which may include task definition families that no longer have any ``ACTIVE`` task definition revisions).

     

    You can filter out task definition families that do not contain any ``ACTIVE`` task definition revisions by setting the ``status`` parameter to ``ACTIVE`` . You can also filter the results with the ``familyPrefix`` parameter.

    

    **Request Syntax** 
    ::

      response = client.list_task_definition_families(
          familyPrefix='string',
          status='ACTIVE'|'INACTIVE'|'ALL',
          nextToken='string',
          maxResults=123
      )
    :type familyPrefix: string
    :param familyPrefix: 

      The ``familyPrefix`` is a string that is used to filter the results of ``ListTaskDefinitionFamilies`` . If you specify a ``familyPrefix`` , only task definition family names that begin with the ``familyPrefix`` string are returned.

      

    
    :type status: string
    :param status: 

      The task definition family status with which to filter the ``ListTaskDefinitionFamilies`` results. By default, both ``ACTIVE`` and ``INACTIVE`` task definition families are listed. If this parameter is set to ``ACTIVE`` , only task definition families that have an ``ACTIVE`` task definition revision are returned. If this parameter is set to ``INACTIVE`` , only task definition families that do not have any ``ACTIVE`` task definition revisions are returned. If you paginate the resulting output, be sure to keep the ``status`` value constant in each subsequent request.

      

    
    :type nextToken: string
    :param nextToken: 

      The ``nextToken`` value returned from a previous paginated ``ListTaskDefinitionFamilies`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

       

      .. note::

         

        This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

         

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of task definition family results returned by ``ListTaskDefinitionFamilies`` in paginated output. When this parameter is used, ``ListTaskDefinitions`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``ListTaskDefinitionFamilies`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``ListTaskDefinitionFamilies`` returns up to 100 results and a ``nextToken`` value if applicable.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'families': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **families** *(list) --* 

          The list of task definition family names that match the ``ListTaskDefinitionFamilies`` request.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          The ``nextToken`` value to include in a future ``ListTaskDefinitionFamilies`` request. When the results of a ``ListTaskDefinitionFamilies`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

  .. py:method:: list_task_definitions(**kwargs)

    

    Returns a list of task definitions that are registered to your account. You can filter the results by family name with the ``familyPrefix`` parameter or by status with the ``status`` parameter.

    

    **Request Syntax** 
    ::

      response = client.list_task_definitions(
          familyPrefix='string',
          status='ACTIVE'|'INACTIVE',
          sort='ASC'|'DESC',
          nextToken='string',
          maxResults=123
      )
    :type familyPrefix: string
    :param familyPrefix: 

      The full family name with which to filter the ``ListTaskDefinitions`` results. Specifying a ``familyPrefix`` limits the listed task definitions to task definition revisions that belong to that family.

      

    
    :type status: string
    :param status: 

      The task definition status with which to filter the ``ListTaskDefinitions`` results. By default, only ``ACTIVE`` task definitions are listed. By setting this parameter to ``INACTIVE`` , you can view task definitions that are ``INACTIVE`` as long as an active task or service still references them. If you paginate the resulting output, be sure to keep the ``status`` value constant in each subsequent request.

      

    
    :type sort: string
    :param sort: 

      The order in which to sort the results. Valid values are ``ASC`` and ``DESC`` . By default (``ASC`` ), task definitions are listed lexicographically by family name and in ascending numerical order by revision so that the newest task definitions in a family are listed last. Setting this parameter to ``DESC`` reverses the sort order on family name and revision so that the newest task definitions in a family are listed first.

      

    
    :type nextToken: string
    :param nextToken: 

      The ``nextToken`` value returned from a previous paginated ``ListTaskDefinitions`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

       

      .. note::

         

        This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

         

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of task definition results returned by ``ListTaskDefinitions`` in paginated output. When this parameter is used, ``ListTaskDefinitions`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``ListTaskDefinitions`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``ListTaskDefinitions`` returns up to 100 results and a ``nextToken`` value if applicable.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'taskDefinitionArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **taskDefinitionArns** *(list) --* 

          The list of task definition Amazon Resource Name (ARN) entries for the ``ListTaskDefinitions`` request.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          The ``nextToken`` value to include in a future ``ListTaskDefinitions`` request. When the results of a ``ListTaskDefinitions`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

  .. py:method:: list_tasks(**kwargs)

    

    Returns a list of tasks for a specified cluster. You can filter the results by family name, by a particular container instance, or by the desired status of the task with the ``family`` , ``containerInstance`` , and ``desiredStatus`` parameters.

     

    Recently-stopped tasks might appear in the returned results. Currently, stopped tasks appear in the returned results for at least one hour. 

    

    **Request Syntax** 
    ::

      response = client.list_tasks(
          cluster='string',
          containerInstance='string',
          family='string',
          nextToken='string',
          maxResults=123,
          startedBy='string',
          serviceName='string',
          desiredStatus='RUNNING'|'PENDING'|'STOPPED'
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the tasks to list. If you do not specify a cluster, the default cluster is assumed..

      

    
    :type containerInstance: string
    :param containerInstance: 

      The container instance ID or full Amazon Resource Name (ARN) of the container instance with which to filter the ``ListTasks`` results. Specifying a ``containerInstance`` limits the results to tasks that belong to that container instance.

      

    
    :type family: string
    :param family: 

      The name of the family with which to filter the ``ListTasks`` results. Specifying a ``family`` limits the results to tasks that belong to that family.

      

    
    :type nextToken: string
    :param nextToken: 

      The ``nextToken`` value returned from a previous paginated ``ListTasks`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

       

      .. note::

         

        This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

         

      

    
    :type maxResults: integer
    :param maxResults: 

      The maximum number of task results returned by ``ListTasks`` in paginated output. When this parameter is used, ``ListTasks`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``ListTasks`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``ListTasks`` returns up to 100 results and a ``nextToken`` value if applicable.

      

    
    :type startedBy: string
    :param startedBy: 

      The ``startedBy`` value with which to filter the task results. Specifying a ``startedBy`` value limits the results to tasks that were started with that value.

      

    
    :type serviceName: string
    :param serviceName: 

      The name of the service with which to filter the ``ListTasks`` results. Specifying a ``serviceName`` limits the results to tasks that belong to that service.

      

    
    :type desiredStatus: string
    :param desiredStatus: 

      The task desired status with which to filter the ``ListTasks`` results. Specifying a ``desiredStatus`` of ``STOPPED`` limits the results to tasks that ECS has set the desired status to ``STOPPED`` , which can be useful for debugging tasks that are not starting properly or have died or finished. The default status filter is ``RUNNING`` , which shows tasks that ECS has set the desired status to ``RUNNING`` .

       

      .. note::

         

        Although you can filter results based on a desired status of ``PENDING`` , this will not return any results because ECS never sets the desired status of a task to that value (only a task's ``lastStatus`` may have a value of ``PENDING`` ).

         

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'taskArns': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **taskArns** *(list) --* 

          The list of task Amazon Resource Name (ARN) entries for the ``ListTasks`` request.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          The ``nextToken`` value to include in a future ``ListTasks`` request. When the results of a ``ListTasks`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

          
    

  .. py:method:: register_container_instance(**kwargs)

    

    .. note::

       

      This action is only used by the Amazon EC2 Container Service agent, and it is not intended for use outside of the agent.

       

     

    Registers an EC2 instance into the specified cluster. This instance becomes available to place containers on.

    

    **Request Syntax** 
    ::

      response = client.register_container_instance(
          cluster='string',
          instanceIdentityDocument='string',
          instanceIdentityDocumentSignature='string',
          totalResources=[
              {
                  'name': 'string',
                  'type': 'string',
                  'doubleValue': 123.0,
                  'longValue': 123,
                  'integerValue': 123,
                  'stringSetValue': [
                      'string',
                  ]
              },
          ],
          versionInfo={
              'agentVersion': 'string',
              'agentHash': 'string',
              'dockerVersion': 'string'
          },
          containerInstanceArn='string',
          attributes=[
              {
                  'name': 'string',
                  'value': 'string'
              },
          ]
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster with which to register your container instance. If you do not specify a cluster, the default cluster is assumed..

      

    
    :type instanceIdentityDocument: string
    :param instanceIdentityDocument: 

      The instance identity document for the EC2 instance to register. This document can be found by running the following command from the instance: ``curl http://169.254.169.254/latest/dynamic/instance-identity/document/``  

      

    
    :type instanceIdentityDocumentSignature: string
    :param instanceIdentityDocumentSignature: 

      The instance identity document signature for the EC2 instance to register. This signature can be found by running the following command from the instance: ``curl http://169.254.169.254/latest/dynamic/instance-identity/signature/``  

      

    
    :type totalResources: list
    :param totalResources: 

      The resources available on the instance.

      

    
      - *(dict) --* 

        Describes the resources available for a container instance.

        

      
        - **name** *(string) --* 

          The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

          

        
        - **type** *(string) --* 

          The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

          

        
        - **doubleValue** *(float) --* 

          When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

          

        
        - **longValue** *(integer) --* 

          When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

          

        
        - **integerValue** *(integer) --* 

          When the ``integerValue`` type is set, the value of the resource must be an integer.

          

        
        - **stringSetValue** *(list) --* 

          When the ``stringSetValue`` type is set, the value of the resource must be a string type.

          

        
          - *(string) --* 

          
      
      
  
    :type versionInfo: dict
    :param versionInfo: 

      The version information for the Amazon ECS container agent and Docker daemon running on the container instance.

      

    
      - **agentVersion** *(string) --* 

        The version number of the Amazon ECS container agent.

        

      
      - **agentHash** *(string) --* 

        The Git commit hash for the Amazon ECS container agent build on the `amazon-ecs-agent`_ GitHub repository.

        

      
      - **dockerVersion** *(string) --* 

        The Docker version running on the container instance.

        

      
    
    :type containerInstanceArn: string
    :param containerInstanceArn: 

      The Amazon Resource Name (ARN) of the container instance (if it was previously registered).

      

    
    :type attributes: list
    :param attributes: 

      The container instance attributes that this container instance supports.

      

    
      - *(dict) --* 

        The attributes applicable to a container instance when it is registered.

        

      
        - **name** *(string) --* **[REQUIRED]** 

          The name of the container instance attribute.

          

        
        - **value** *(string) --* 

          The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'containerInstance': {
                'containerInstanceArn': 'string',
                'ec2InstanceId': 'string',
                'versionInfo': {
                    'agentVersion': 'string',
                    'agentHash': 'string',
                    'dockerVersion': 'string'
                },
                'remainingResources': [
                    {
                        'name': 'string',
                        'type': 'string',
                        'doubleValue': 123.0,
                        'longValue': 123,
                        'integerValue': 123,
                        'stringSetValue': [
                            'string',
                        ]
                    },
                ],
                'registeredResources': [
                    {
                        'name': 'string',
                        'type': 'string',
                        'doubleValue': 123.0,
                        'longValue': 123,
                        'integerValue': 123,
                        'stringSetValue': [
                            'string',
                        ]
                    },
                ],
                'status': 'string',
                'agentConnected': True|False,
                'runningTasksCount': 123,
                'pendingTasksCount': 123,
                'agentUpdateStatus': 'PENDING'|'STAGING'|'STAGED'|'UPDATING'|'UPDATED'|'FAILED',
                'attributes': [
                    {
                        'name': 'string',
                        'value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **containerInstance** *(dict) --* 

          An EC2 instance that is running the Amazon ECS agent and has been registered with a cluster.

          
          

          - **containerInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, ``arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* `` .

            
          

          - **ec2InstanceId** *(string) --* 

            The EC2 instance ID of the container instance.

            
          

          - **versionInfo** *(dict) --* 

            The version information for the Amazon ECS container agent and Docker daemon running on the container instance.

            
            

            - **agentVersion** *(string) --* 

              The version number of the Amazon ECS container agent.

              
            

            - **agentHash** *(string) --* 

              The Git commit hash for the Amazon ECS container agent build on the `amazon-ecs-agent`_ GitHub repository.

              
            

            - **dockerVersion** *(string) --* 

              The Docker version running on the container instance.

              
        
          

          - **remainingResources** *(list) --* 

            The remaining resources of the container instance that are available for new tasks.

            
            

            - *(dict) --* 

              Describes the resources available for a container instance.

              
              

              - **name** *(string) --* 

                The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

                
              

              - **type** *(string) --* 

                The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

                
              

              - **doubleValue** *(float) --* 

                When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

                
              

              - **longValue** *(integer) --* 

                When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

                
              

              - **integerValue** *(integer) --* 

                When the ``integerValue`` type is set, the value of the resource must be an integer.

                
              

              - **stringSetValue** *(list) --* 

                When the ``stringSetValue`` type is set, the value of the resource must be a string type.

                
                

                - *(string) --* 
            
          
        
          

          - **registeredResources** *(list) --* 

            The registered resources on the container instance that are in use by current tasks.

            
            

            - *(dict) --* 

              Describes the resources available for a container instance.

              
              

              - **name** *(string) --* 

                The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

                
              

              - **type** *(string) --* 

                The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

                
              

              - **doubleValue** *(float) --* 

                When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

                
              

              - **longValue** *(integer) --* 

                When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

                
              

              - **integerValue** *(integer) --* 

                When the ``integerValue`` type is set, the value of the resource must be an integer.

                
              

              - **stringSetValue** *(list) --* 

                When the ``stringSetValue`` type is set, the value of the resource must be a string type.

                
                

                - *(string) --* 
            
          
        
          

          - **status** *(string) --* 

            The status of the container instance. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that the container instance can accept tasks.

            
          

          - **agentConnected** *(boolean) --* 

            This parameter returns ``true`` if the agent is actually connected to Amazon ECS. Registered instances with an agent that may be unhealthy or stopped return ``false`` , and instances without a connected agent cannot accept placement requests.

            
          

          - **runningTasksCount** *(integer) --* 

            The number of tasks on the container instance that are in the ``RUNNING`` status.

            
          

          - **pendingTasksCount** *(integer) --* 

            The number of tasks on the container instance that are in the ``PENDING`` status.

            
          

          - **agentUpdateStatus** *(string) --* 

            The status of the most recent agent update. If an update has never been requested, this value is ``NULL`` .

            
          

          - **attributes** *(list) --* 

            The attributes set for the container instance by the Amazon ECS container agent at instance registration.

            
            

            - *(dict) --* 

              The attributes applicable to a container instance when it is registered.

              
              

              - **name** *(string) --* 

                The name of the container instance attribute.

                
              

              - **value** *(string) --* 

                The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

                
          
        
      
    

  .. py:method:: register_task_definition(**kwargs)

    

    Registers a new task definition from the supplied ``family`` and ``containerDefinitions`` . Optionally, you can add data volumes to your containers with the ``volumes`` parameter. For more information about task definition parameters and defaults, see `Amazon ECS Task Definitions`_ in the *Amazon EC2 Container Service Developer Guide* .

     

    You can specify an IAM role for your task with the ``taskRoleArn`` parameter. When you specify an IAM role for a task, its containers can then use the latest versions of the AWS CLI or SDKs to make API requests to the AWS services that are specified in the IAM policy associated with the role. For more information, see `IAM Roles for Tasks`_ in the *Amazon EC2 Container Service Developer Guide* .

     

    You can specify a Docker networking mode for the containers in your task definition with the ``networkMode`` parameter. The available network modes correspond to those described in `Network settings`_ in the Docker run reference.

    

    **Request Syntax** 
    ::

      response = client.register_task_definition(
          family='string',
          taskRoleArn='string',
          networkMode='bridge'|'host'|'none',
          containerDefinitions=[
              {
                  'name': 'string',
                  'image': 'string',
                  'cpu': 123,
                  'memory': 123,
                  'memoryReservation': 123,
                  'links': [
                      'string',
                  ],
                  'portMappings': [
                      {
                          'containerPort': 123,
                          'hostPort': 123,
                          'protocol': 'tcp'|'udp'
                      },
                  ],
                  'essential': True|False,
                  'entryPoint': [
                      'string',
                  ],
                  'command': [
                      'string',
                  ],
                  'environment': [
                      {
                          'name': 'string',
                          'value': 'string'
                      },
                  ],
                  'mountPoints': [
                      {
                          'sourceVolume': 'string',
                          'containerPath': 'string',
                          'readOnly': True|False
                      },
                  ],
                  'volumesFrom': [
                      {
                          'sourceContainer': 'string',
                          'readOnly': True|False
                      },
                  ],
                  'hostname': 'string',
                  'user': 'string',
                  'workingDirectory': 'string',
                  'disableNetworking': True|False,
                  'privileged': True|False,
                  'readonlyRootFilesystem': True|False,
                  'dnsServers': [
                      'string',
                  ],
                  'dnsSearchDomains': [
                      'string',
                  ],
                  'extraHosts': [
                      {
                          'hostname': 'string',
                          'ipAddress': 'string'
                      },
                  ],
                  'dockerSecurityOptions': [
                      'string',
                  ],
                  'dockerLabels': {
                      'string': 'string'
                  },
                  'ulimits': [
                      {
                          'name': 'core'|'cpu'|'data'|'fsize'|'locks'|'memlock'|'msgqueue'|'nice'|'nofile'|'nproc'|'rss'|'rtprio'|'rttime'|'sigpending'|'stack',
                          'softLimit': 123,
                          'hardLimit': 123
                      },
                  ],
                  'logConfiguration': {
                      'logDriver': 'json-file'|'syslog'|'journald'|'gelf'|'fluentd'|'awslogs'|'splunk',
                      'options': {
                          'string': 'string'
                      }
                  }
              },
          ],
          volumes=[
              {
                  'name': 'string',
                  'host': {
                      'sourcePath': 'string'
                  }
              },
          ]
      )
    :type family: string
    :param family: **[REQUIRED]** 

      You must specify a ``family`` for a task definition, which allows you to track multiple versions of the same task definition. The ``family`` is used as a name for your task definition. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed.

      

    
    :type taskRoleArn: string
    :param taskRoleArn: 

      The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

      

    
    :type networkMode: string
    :param networkMode: 

      The Docker networking mode to use for the containers in the task. The valid values are ``none`` , ``bridge`` , and ``host`` . 

       

      The default Docker network mode is ``bridge`` . If the network mode is set to ``none`` , you cannot specify port mappings in your container definitions, and the task's containers do not have external connectivity. The ``host`` network mode offers the highest networking performance for containers because they use the host network stack instead of the virtualized network stack provided by the ``bridge`` mode; however, exposed container ports are mapped directly to the corresponding host port, so you cannot take advantage of dynamic host port mappings or run multiple instantiations of the same task on a single container instance if port mappings are used.

       

      For more information, see `Network settings`_ in the *Docker run reference* .

      

    
    :type containerDefinitions: list
    :param containerDefinitions: **[REQUIRED]** 

      A list of container definitions in JSON format that describe the different containers that make up your task.

      

    
      - *(dict) --* 

        Container definitions are used in task definitions to describe the different containers that are launched as part of a task.

        

      
        - **name** *(string) --* 

          The name of a container. If you are linking multiple containers together in a task definition, the ``name`` of one container can be entered in the ``links`` of another container to connect the containers. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This parameter maps to ``name`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--name`` option to `docker run`_ . 

          

        
        - **image** *(string) --* 

          The image used to start a container. This string is passed directly to the Docker daemon. Images in the Docker Hub registry are available by default. Other repositories are specified with `` *repository-url* /*image* :*tag* `` . Up to 255 letters (uppercase and lowercase), numbers, hyphens, underscores, colons, periods, forward slashes, and number signs are allowed. This parameter maps to ``Image`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``IMAGE`` parameter of `docker run`_ .

           

           
          * Images in official repositories on Docker Hub use a single name (for example, ``ubuntu`` or ``mongo`` ). 
           
          * Images in other repositories on Docker Hub are qualified with an organization name (for example, ``amazon/amazon-ecs-agent`` ). 
           
          * Images in other online repositories are qualified further by a domain name (for example, ``quay.io/assemblyline/ubuntu`` ). 
           

          

        
        - **cpu** *(integer) --* 

          The number of ``cpu`` units reserved for the container. A container instance has 1,024 ``cpu`` units for every CPU core. This parameter specifies the minimum amount of CPU to reserve for a container, and containers share unallocated CPU units with other containers on the instance with the same ratio as their allocated amount. This parameter maps to ``CpuShares`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--cpu-shares`` option to `docker run`_ .

           

          .. note::

             

            You can determine the number of CPU units that are available per EC2 instance type by multiplying the vCPUs listed for that instance type on the `Amazon EC2 Instances`_ detail page by 1,024.

             

           

          For example, if you run a single-container task on a single-core instance type with 512 CPU units specified for that container, and that is the only task running on the container instance, that container could use the full 1,024 CPU unit share at any given time. However, if you launched another copy of the same task on that container instance, each task would be guaranteed a minimum of 512 CPU units when needed, and each container could float to higher CPU usage if the other container was not using it, but if both tasks were 100% active all of the time, they would be limited to 512 CPU units.

           

          The Docker daemon on the container instance uses the CPU value to calculate the relative CPU share ratios for running containers. For more information, see `CPU share constraint`_ in the Docker documentation. The minimum valid CPU share value that the Linux kernel allows is 2; however, the CPU parameter is not required, and you can use CPU values below 2 in your container definitions. For CPU values below 2 (including null), the behavior varies based on your Amazon ECS container agent version:

           

           
          * **Agent versions less than or equal to 1.1.0:** Null and zero CPU values are passed to Docker as 0, which Docker then converts to 1,024 CPU shares. CPU values of 1 are passed to Docker as 1, which the Linux kernel converts to 2 CPU shares. 
           
          * **Agent versions greater than or equal to 1.2.0:** Null, zero, and CPU values of 1 are passed to Docker as 2. 
           

          

        
        - **memory** *(integer) --* 

          The hard limit (in MiB) of memory to present to the container. If your container attempts to exceed the memory specified here, the container is killed. This parameter maps to ``Memory`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--memory`` option to `docker run`_ .

           

          You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

           

          The Docker daemon reserves a minimum of 4 MiB of memory for a container, so you should not specify fewer than 4 MiB of memory for your containers. 

          

        
        - **memoryReservation** *(integer) --* 

          The soft limit (in MiB) of memory to reserve for the container. When system memory is under heavy contention, Docker attempts to keep the container memory to this soft limit; however, your container can consume more memory when it needs to, up to either the hard limit specified with the ``memory`` parameter (if applicable), or all of the available memory on the container instance, whichever comes first. This parameter maps to ``MemoryReservation`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--memory-reservation`` option to `docker run`_ .

           

          You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

           

          For example, if your container normally uses 128 MiB of memory, but occasionally bursts to 256 MiB of memory for short periods of time, you can set a ``memoryReservation`` of 128 MiB, and a ``memory`` hard limit of 300 MiB. This configuration would allow the container to only reserve 128 MiB of memory from the remaining resources on the container instance, but also allow the container to consume more memory resources when needed.

          

        
        - **links** *(list) --* 

          The ``link`` parameter allows containers to communicate with each other without the need for port mappings, using the ``name`` parameter and optionally, an ``alias`` for the link. This construct is analogous to ``name:alias`` in Docker links. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed for each ``name`` and ``alias`` . For more information on linking Docker containers, see `https\://docs.docker.com/userguide/dockerlinks/`_ . This parameter maps to ``Links`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--link`` option to `docker run`_ .

           

          .. warning::

             

            Containers that are collocated on a single container instance may be able to communicate with each other without requiring links or host port mappings. Network isolation is achieved on the container instance using security groups and VPC settings.

             

          

        
          - *(string) --* 

          
      
        - **portMappings** *(list) --* 

          The list of port mappings for the container. Port mappings allow containers to access ports on the host container instance to send or receive traffic. This parameter maps to ``PortBindings`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--publish`` option to `docker run`_ . If the network mode of a task definition is set to ``none`` , then you cannot specify port mappings. If the network mode of a task definition is set to ``host`` , then host ports must either be undefined or they must match the container port in the port mapping.

           

          .. note::

             

            After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the **Network Bindings** section of a container description of a selected task in the Amazon ECS console, or the ``networkBindings`` section  DescribeTasks responses.

             

          

        
          - *(dict) --* 

            Port mappings allow containers to access ports on the host container instance to send or receive traffic. Port mappings are specified as part of the container definition. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  DescribeTasks API responses.

            

          
            - **containerPort** *(integer) --* 

              The port number on the container that is bound to the user-specified or automatically assigned host port. If you specify a container port and not a host port, your container automatically receives a host port in the ephemeral port range (for more information, see ``hostPort`` ). Port mappings that are automatically assigned in this way do not count toward the 100 reserved ports limit of a container instance.

              

            
            - **hostPort** *(integer) --* 

              The port number on the container instance to reserve for your container. You can specify a non-reserved host port for your container port mapping, or you can omit the ``hostPort`` (or set it to ``0`` ) while specifying a ``containerPort`` and your container automatically receives a port in the ephemeral port range for your container instance operating system and Docker version.

               

              The default ephemeral port range is 49153 to 65535, and this range is used for Docker versions prior to 1.6.0. For Docker version 1.6.0 and later, the Docker daemon tries to read the ephemeral port range from ``/proc/sys/net/ipv4/ip_local_port_range`` ; if this kernel parameter is unavailable, the default ephemeral port range is used. You should not attempt to specify a host port in the ephemeral port range, because these are reserved for automatic assignment. In general, ports below 32768 are outside of the ephemeral port range.

               

              The default reserved ports are 22 for SSH, the Docker ports 2375 and 2376, and the Amazon ECS container agent port 51678. Any host port that was previously specified in a running task is also reserved while the task is running (after a task stops, the host port is released).The current reserved ports are displayed in the ``remainingResources`` of  DescribeContainerInstances output, and a container instance may have up to 100 reserved ports at a time, including the default reserved ports (automatically assigned ports do not count toward the 100 reserved ports limit).

              

            
            - **protocol** *(string) --* 

              The protocol used for the port mapping. Valid values are ``tcp`` and ``udp`` . The default is ``tcp`` .

              

            
          
      
        - **essential** *(boolean) --* 

          If the ``essential`` parameter of a container is marked as ``true`` , and that container fails or stops for any reason, all other containers that are part of the task are stopped. If the ``essential`` parameter of a container is marked as ``false`` , then its failure does not affect the rest of the containers in a task. If this parameter is omitted, a container is assumed to be essential.

           

          All tasks must have at least one essential container. If you have an application that is composed of multiple containers, you should group containers that are used for a common purpose into components, and separate the different components into multiple task definitions. For more information, see `Application Architecture`_ in the *Amazon EC2 Container Service Developer Guide* .

          

        
        - **entryPoint** *(list) --* 

          .. warning::

             

            Early versions of the Amazon ECS container agent do not properly handle ``entryPoint`` parameters. If you have problems using ``entryPoint`` , update your container agent or enter your commands and arguments as ``command`` array items instead.

             

           

          The entry point that is passed to the container. This parameter maps to ``Entrypoint`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--entrypoint`` option to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#entrypoint`_ .

          

        
          - *(string) --* 

          
      
        - **command** *(list) --* 

          The command that is passed to the container. This parameter maps to ``Cmd`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``COMMAND`` parameter to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#cmd`_ .

          

        
          - *(string) --* 

          
      
        - **environment** *(list) --* 

          The environment variables to pass to a container. This parameter maps to ``Env`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--env`` option to `docker run`_ .

           

          .. warning::

             

            We do not recommend using plain text environment variables for sensitive information, such as credential data.

             

          

        
          - *(dict) --* 

            A key and value pair object.

            

          
            - **name** *(string) --* 

              The name of the key value pair. For environment variables, this is the name of the environment variable.

              

            
            - **value** *(string) --* 

              The value of the key value pair. For environment variables, this is the value of the environment variable.

              

            
          
      
        - **mountPoints** *(list) --* 

          The mount points for data volumes in your container. This parameter maps to ``Volumes`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volume`` option to `docker run`_ .

          

        
          - *(dict) --* 

            Details on a volume mount point that is used in a container definition.

            

          
            - **sourceVolume** *(string) --* 

              The name of the volume to mount.

              

            
            - **containerPath** *(string) --* 

              The path on the container to mount the host volume at.

              

            
            - **readOnly** *(boolean) --* 

              If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

              

            
          
      
        - **volumesFrom** *(list) --* 

          Data volumes to mount from another container. This parameter maps to ``VolumesFrom`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volumes-from`` option to `docker run`_ .

          

        
          - *(dict) --* 

            Details on a data volume from another container.

            

          
            - **sourceContainer** *(string) --* 

              The name of the container to mount volumes from.

              

            
            - **readOnly** *(boolean) --* 

              If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

              

            
          
      
        - **hostname** *(string) --* 

          The hostname to use for your container. This parameter maps to ``Hostname`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--hostname`` option to `docker run`_ .

          

        
        - **user** *(string) --* 

          The user name to use inside the container. This parameter maps to ``User`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--user`` option to `docker run`_ .

          

        
        - **workingDirectory** *(string) --* 

          The working directory in which to run commands inside the container. This parameter maps to ``WorkingDir`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--workdir`` option to `docker run`_ .

          

        
        - **disableNetworking** *(boolean) --* 

          When this parameter is true, networking is disabled within the container. This parameter maps to ``NetworkDisabled`` in the `Create a container`_ section of the `Docker Remote API`_ .

          

        
        - **privileged** *(boolean) --* 

          When this parameter is true, the container is given elevated privileges on the host container instance (similar to the ``root`` user). This parameter maps to ``Privileged`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--privileged`` option to `docker run`_ .

          

        
        - **readonlyRootFilesystem** *(boolean) --* 

          When this parameter is true, the container is given read-only access to its root file system. This parameter maps to ``ReadonlyRootfs`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--read-only`` option to ``docker run`` .

          

        
        - **dnsServers** *(list) --* 

          A list of DNS servers that are presented to the container. This parameter maps to ``Dns`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns`` option to `docker run`_ .

          

        
          - *(string) --* 

          
      
        - **dnsSearchDomains** *(list) --* 

          A list of DNS search domains that are presented to the container. This parameter maps to ``DnsSearch`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns-search`` option to `docker run`_ .

          

        
          - *(string) --* 

          
      
        - **extraHosts** *(list) --* 

          A list of hostnames and IP address mappings to append to the ``/etc/hosts`` file on the container. This parameter maps to ``ExtraHosts`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--add-host`` option to `docker run`_ .

          

        
          - *(dict) --* 

            Hostnames and IP address entries that are added to the ``/etc/hosts`` file of a container via the ``extraHosts`` parameter of its  ContainerDefinition . 

            

          
            - **hostname** *(string) --* **[REQUIRED]** 

              The hostname to use in the ``/etc/hosts`` entry.

              

            
            - **ipAddress** *(string) --* **[REQUIRED]** 

              The IP address to use in the ``/etc/hosts`` entry.

              

            
          
      
        - **dockerSecurityOptions** *(list) --* 

          A list of strings to provide custom labels for SELinux and AppArmor multi-level security systems. This parameter maps to ``SecurityOpt`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--security-opt`` option to `docker run`_ .

           

          .. note::

             

            The Amazon ECS container agent running on a container instance must register with the ``ECS_SELINUX_CAPABLE=true`` or ``ECS_APPARMOR_CAPABLE=true`` environment variables before containers placed on that instance can use these security options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

             

          

        
          - *(string) --* 

          
      
        - **dockerLabels** *(dict) --* 

          A key/value map of labels to add to the container. This parameter maps to ``Labels`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--label`` option to `docker run`_ . This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

          

        
          - *(string) --* 

          
            - *(string) --* 

            
      
    
        - **ulimits** *(list) --* 

          A list of ``ulimits`` to set in the container. This parameter maps to ``Ulimits`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--ulimit`` option to `docker run`_ . Valid naming values are displayed in the  Ulimit data type. This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

          

        
          - *(dict) --* 

            The ``ulimit`` settings to pass to the container.

            

          
            - **name** *(string) --* **[REQUIRED]** 

              The ``type`` of the ``ulimit`` .

              

            
            - **softLimit** *(integer) --* **[REQUIRED]** 

              The soft limit for the ulimit type.

              

            
            - **hardLimit** *(integer) --* **[REQUIRED]** 

              The hard limit for the ulimit type.

              

            
          
      
        - **logConfiguration** *(dict) --* 

          The log configuration specification for the container. This parameter maps to ``LogConfig`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--log-driver`` option to `docker run`_ . By default, containers use the same logging driver that the Docker daemon uses; however the container may use a different logging driver than the Docker daemon by specifying a log driver with this parameter in the container definition. To use a different logging driver for a container, the log system must be configured properly on the container instance (or on a different log server for remote logging options). For more information on the options for different supported log drivers, see `Configure logging drivers`_ in the Docker documentation.

           

          .. note::

             

            Amazon ECS currently supports a subset of the logging drivers available to the Docker daemon (shown in the  LogConfiguration data type). Currently unsupported log drivers may be available in future releases of the Amazon ECS container agent.

             

           

          This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

           

          .. note::

             

            The Amazon ECS container agent running on a container instance must register the logging drivers available on that instance with the ``ECS_AVAILABLE_LOGGING_DRIVERS`` environment variable before containers placed on that instance can use these log configuration options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

             

          

        
          - **logDriver** *(string) --* **[REQUIRED]** 

            The log driver to use for the container. The valid values listed for this parameter are log drivers that the Amazon ECS container agent can communicate with by default. 

             

            .. note::

               

              If you have a custom driver that is not listed above that you would like to work with the Amazon ECS container agent, you can fork the Amazon ECS container agent project that is `available on GitHub`_ and customize it to work with that driver. We encourage you to submit pull requests for changes that you would like to have included. However, Amazon Web Services does not currently provide support for running modified copies of this software.

               

             

            This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

            

          
          - **options** *(dict) --* 

            The configuration options to send to the log driver. This parameter requires version 1.19 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

            

          
            - *(string) --* 

            
              - *(string) --* 

              
        
      
        
      
  
    :type volumes: list
    :param volumes: 

      A list of volume definitions in JSON format that containers in your task may use.

      

    
      - *(dict) --* 

        A data volume used in a task definition.

        

      
        - **name** *(string) --* 

          The name of the volume. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This name is referenced in the ``sourceVolume`` parameter of container definition ``mountPoints`` .

          

        
        - **host** *(dict) --* 

          The contents of the ``host`` parameter determine whether your data volume persists on the host container instance and where it is stored. If the host parameter is empty, then the Docker daemon assigns a host path for your data volume, but the data is not guaranteed to persist after the containers associated with it stop running.

          

        
          - **sourcePath** *(string) --* 

            The path on the host container instance that is presented to the container. If this parameter is empty, then the Docker daemon has assigned a host path for you. If the ``host`` parameter contains a ``sourcePath`` file location, then the data volume persists at the specified location on the host container instance until you delete it manually. If the ``sourcePath`` value does not exist on the host container instance, the Docker daemon creates it. If the location does exist, the contents of the source path folder are exported.

            

          
        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'taskDefinition': {
                'taskDefinitionArn': 'string',
                'containerDefinitions': [
                    {
                        'name': 'string',
                        'image': 'string',
                        'cpu': 123,
                        'memory': 123,
                        'memoryReservation': 123,
                        'links': [
                            'string',
                        ],
                        'portMappings': [
                            {
                                'containerPort': 123,
                                'hostPort': 123,
                                'protocol': 'tcp'|'udp'
                            },
                        ],
                        'essential': True|False,
                        'entryPoint': [
                            'string',
                        ],
                        'command': [
                            'string',
                        ],
                        'environment': [
                            {
                                'name': 'string',
                                'value': 'string'
                            },
                        ],
                        'mountPoints': [
                            {
                                'sourceVolume': 'string',
                                'containerPath': 'string',
                                'readOnly': True|False
                            },
                        ],
                        'volumesFrom': [
                            {
                                'sourceContainer': 'string',
                                'readOnly': True|False
                            },
                        ],
                        'hostname': 'string',
                        'user': 'string',
                        'workingDirectory': 'string',
                        'disableNetworking': True|False,
                        'privileged': True|False,
                        'readonlyRootFilesystem': True|False,
                        'dnsServers': [
                            'string',
                        ],
                        'dnsSearchDomains': [
                            'string',
                        ],
                        'extraHosts': [
                            {
                                'hostname': 'string',
                                'ipAddress': 'string'
                            },
                        ],
                        'dockerSecurityOptions': [
                            'string',
                        ],
                        'dockerLabels': {
                            'string': 'string'
                        },
                        'ulimits': [
                            {
                                'name': 'core'|'cpu'|'data'|'fsize'|'locks'|'memlock'|'msgqueue'|'nice'|'nofile'|'nproc'|'rss'|'rtprio'|'rttime'|'sigpending'|'stack',
                                'softLimit': 123,
                                'hardLimit': 123
                            },
                        ],
                        'logConfiguration': {
                            'logDriver': 'json-file'|'syslog'|'journald'|'gelf'|'fluentd'|'awslogs'|'splunk',
                            'options': {
                                'string': 'string'
                            }
                        }
                    },
                ],
                'family': 'string',
                'taskRoleArn': 'string',
                'networkMode': 'bridge'|'host'|'none',
                'revision': 123,
                'volumes': [
                    {
                        'name': 'string',
                        'host': {
                            'sourcePath': 'string'
                        }
                    },
                ],
                'status': 'ACTIVE'|'INACTIVE',
                'requiresAttributes': [
                    {
                        'name': 'string',
                        'value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **taskDefinition** *(dict) --* 

          The full description of the registered task definition.

          
          

          - **taskDefinitionArn** *(string) --* 

            The full Amazon Resource Name (ARN) of the task definition.

            
          

          - **containerDefinitions** *(list) --* 

            A list of container definitions in JSON format that describe the different containers that make up your task. For more information about container definition parameters and defaults, see `Amazon ECS Task Definitions`_ in the *Amazon EC2 Container Service Developer Guide* .

            
            

            - *(dict) --* 

              Container definitions are used in task definitions to describe the different containers that are launched as part of a task.

              
              

              - **name** *(string) --* 

                The name of a container. If you are linking multiple containers together in a task definition, the ``name`` of one container can be entered in the ``links`` of another container to connect the containers. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This parameter maps to ``name`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--name`` option to `docker run`_ . 

                
              

              - **image** *(string) --* 

                The image used to start a container. This string is passed directly to the Docker daemon. Images in the Docker Hub registry are available by default. Other repositories are specified with `` *repository-url* /*image* :*tag* `` . Up to 255 letters (uppercase and lowercase), numbers, hyphens, underscores, colons, periods, forward slashes, and number signs are allowed. This parameter maps to ``Image`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``IMAGE`` parameter of `docker run`_ .

                 

                 
                * Images in official repositories on Docker Hub use a single name (for example, ``ubuntu`` or ``mongo`` ). 
                 
                * Images in other repositories on Docker Hub are qualified with an organization name (for example, ``amazon/amazon-ecs-agent`` ). 
                 
                * Images in other online repositories are qualified further by a domain name (for example, ``quay.io/assemblyline/ubuntu`` ). 
                 

                
              

              - **cpu** *(integer) --* 

                The number of ``cpu`` units reserved for the container. A container instance has 1,024 ``cpu`` units for every CPU core. This parameter specifies the minimum amount of CPU to reserve for a container, and containers share unallocated CPU units with other containers on the instance with the same ratio as their allocated amount. This parameter maps to ``CpuShares`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--cpu-shares`` option to `docker run`_ .

                 

                .. note::

                   

                  You can determine the number of CPU units that are available per EC2 instance type by multiplying the vCPUs listed for that instance type on the `Amazon EC2 Instances`_ detail page by 1,024.

                   

                 

                For example, if you run a single-container task on a single-core instance type with 512 CPU units specified for that container, and that is the only task running on the container instance, that container could use the full 1,024 CPU unit share at any given time. However, if you launched another copy of the same task on that container instance, each task would be guaranteed a minimum of 512 CPU units when needed, and each container could float to higher CPU usage if the other container was not using it, but if both tasks were 100% active all of the time, they would be limited to 512 CPU units.

                 

                The Docker daemon on the container instance uses the CPU value to calculate the relative CPU share ratios for running containers. For more information, see `CPU share constraint`_ in the Docker documentation. The minimum valid CPU share value that the Linux kernel allows is 2; however, the CPU parameter is not required, and you can use CPU values below 2 in your container definitions. For CPU values below 2 (including null), the behavior varies based on your Amazon ECS container agent version:

                 

                 
                * **Agent versions less than or equal to 1.1.0:** Null and zero CPU values are passed to Docker as 0, which Docker then converts to 1,024 CPU shares. CPU values of 1 are passed to Docker as 1, which the Linux kernel converts to 2 CPU shares. 
                 
                * **Agent versions greater than or equal to 1.2.0:** Null, zero, and CPU values of 1 are passed to Docker as 2. 
                 

                
              

              - **memory** *(integer) --* 

                The hard limit (in MiB) of memory to present to the container. If your container attempts to exceed the memory specified here, the container is killed. This parameter maps to ``Memory`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--memory`` option to `docker run`_ .

                 

                You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

                 

                The Docker daemon reserves a minimum of 4 MiB of memory for a container, so you should not specify fewer than 4 MiB of memory for your containers. 

                
              

              - **memoryReservation** *(integer) --* 

                The soft limit (in MiB) of memory to reserve for the container. When system memory is under heavy contention, Docker attempts to keep the container memory to this soft limit; however, your container can consume more memory when it needs to, up to either the hard limit specified with the ``memory`` parameter (if applicable), or all of the available memory on the container instance, whichever comes first. This parameter maps to ``MemoryReservation`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--memory-reservation`` option to `docker run`_ .

                 

                You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

                 

                For example, if your container normally uses 128 MiB of memory, but occasionally bursts to 256 MiB of memory for short periods of time, you can set a ``memoryReservation`` of 128 MiB, and a ``memory`` hard limit of 300 MiB. This configuration would allow the container to only reserve 128 MiB of memory from the remaining resources on the container instance, but also allow the container to consume more memory resources when needed.

                
              

              - **links** *(list) --* 

                The ``link`` parameter allows containers to communicate with each other without the need for port mappings, using the ``name`` parameter and optionally, an ``alias`` for the link. This construct is analogous to ``name:alias`` in Docker links. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed for each ``name`` and ``alias`` . For more information on linking Docker containers, see `https\://docs.docker.com/userguide/dockerlinks/`_ . This parameter maps to ``Links`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--link`` option to `docker run`_ .

                 

                .. warning::

                   

                  Containers that are collocated on a single container instance may be able to communicate with each other without requiring links or host port mappings. Network isolation is achieved on the container instance using security groups and VPC settings.

                   

                
                

                - *(string) --* 
            
              

              - **portMappings** *(list) --* 

                The list of port mappings for the container. Port mappings allow containers to access ports on the host container instance to send or receive traffic. This parameter maps to ``PortBindings`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--publish`` option to `docker run`_ . If the network mode of a task definition is set to ``none`` , then you cannot specify port mappings. If the network mode of a task definition is set to ``host`` , then host ports must either be undefined or they must match the container port in the port mapping.

                 

                .. note::

                   

                  After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the **Network Bindings** section of a container description of a selected task in the Amazon ECS console, or the ``networkBindings`` section  DescribeTasks responses.

                   

                
                

                - *(dict) --* 

                  Port mappings allow containers to access ports on the host container instance to send or receive traffic. Port mappings are specified as part of the container definition. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  DescribeTasks API responses.

                  
                  

                  - **containerPort** *(integer) --* 

                    The port number on the container that is bound to the user-specified or automatically assigned host port. If you specify a container port and not a host port, your container automatically receives a host port in the ephemeral port range (for more information, see ``hostPort`` ). Port mappings that are automatically assigned in this way do not count toward the 100 reserved ports limit of a container instance.

                    
                  

                  - **hostPort** *(integer) --* 

                    The port number on the container instance to reserve for your container. You can specify a non-reserved host port for your container port mapping, or you can omit the ``hostPort`` (or set it to ``0`` ) while specifying a ``containerPort`` and your container automatically receives a port in the ephemeral port range for your container instance operating system and Docker version.

                     

                    The default ephemeral port range is 49153 to 65535, and this range is used for Docker versions prior to 1.6.0. For Docker version 1.6.0 and later, the Docker daemon tries to read the ephemeral port range from ``/proc/sys/net/ipv4/ip_local_port_range`` ; if this kernel parameter is unavailable, the default ephemeral port range is used. You should not attempt to specify a host port in the ephemeral port range, because these are reserved for automatic assignment. In general, ports below 32768 are outside of the ephemeral port range.

                     

                    The default reserved ports are 22 for SSH, the Docker ports 2375 and 2376, and the Amazon ECS container agent port 51678. Any host port that was previously specified in a running task is also reserved while the task is running (after a task stops, the host port is released).The current reserved ports are displayed in the ``remainingResources`` of  DescribeContainerInstances output, and a container instance may have up to 100 reserved ports at a time, including the default reserved ports (automatically assigned ports do not count toward the 100 reserved ports limit).

                    
                  

                  - **protocol** *(string) --* 

                    The protocol used for the port mapping. Valid values are ``tcp`` and ``udp`` . The default is ``tcp`` .

                    
              
            
              

              - **essential** *(boolean) --* 

                If the ``essential`` parameter of a container is marked as ``true`` , and that container fails or stops for any reason, all other containers that are part of the task are stopped. If the ``essential`` parameter of a container is marked as ``false`` , then its failure does not affect the rest of the containers in a task. If this parameter is omitted, a container is assumed to be essential.

                 

                All tasks must have at least one essential container. If you have an application that is composed of multiple containers, you should group containers that are used for a common purpose into components, and separate the different components into multiple task definitions. For more information, see `Application Architecture`_ in the *Amazon EC2 Container Service Developer Guide* .

                
              

              - **entryPoint** *(list) --* 

                .. warning::

                   

                  Early versions of the Amazon ECS container agent do not properly handle ``entryPoint`` parameters. If you have problems using ``entryPoint`` , update your container agent or enter your commands and arguments as ``command`` array items instead.

                   

                 

                The entry point that is passed to the container. This parameter maps to ``Entrypoint`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--entrypoint`` option to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#entrypoint`_ .

                
                

                - *(string) --* 
            
              

              - **command** *(list) --* 

                The command that is passed to the container. This parameter maps to ``Cmd`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``COMMAND`` parameter to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#cmd`_ .

                
                

                - *(string) --* 
            
              

              - **environment** *(list) --* 

                The environment variables to pass to a container. This parameter maps to ``Env`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--env`` option to `docker run`_ .

                 

                .. warning::

                   

                  We do not recommend using plain text environment variables for sensitive information, such as credential data.

                   

                
                

                - *(dict) --* 

                  A key and value pair object.

                  
                  

                  - **name** *(string) --* 

                    The name of the key value pair. For environment variables, this is the name of the environment variable.

                    
                  

                  - **value** *(string) --* 

                    The value of the key value pair. For environment variables, this is the value of the environment variable.

                    
              
            
              

              - **mountPoints** *(list) --* 

                The mount points for data volumes in your container. This parameter maps to ``Volumes`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volume`` option to `docker run`_ .

                
                

                - *(dict) --* 

                  Details on a volume mount point that is used in a container definition.

                  
                  

                  - **sourceVolume** *(string) --* 

                    The name of the volume to mount.

                    
                  

                  - **containerPath** *(string) --* 

                    The path on the container to mount the host volume at.

                    
                  

                  - **readOnly** *(boolean) --* 

                    If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

                    
              
            
              

              - **volumesFrom** *(list) --* 

                Data volumes to mount from another container. This parameter maps to ``VolumesFrom`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volumes-from`` option to `docker run`_ .

                
                

                - *(dict) --* 

                  Details on a data volume from another container.

                  
                  

                  - **sourceContainer** *(string) --* 

                    The name of the container to mount volumes from.

                    
                  

                  - **readOnly** *(boolean) --* 

                    If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

                    
              
            
              

              - **hostname** *(string) --* 

                The hostname to use for your container. This parameter maps to ``Hostname`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--hostname`` option to `docker run`_ .

                
              

              - **user** *(string) --* 

                The user name to use inside the container. This parameter maps to ``User`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--user`` option to `docker run`_ .

                
              

              - **workingDirectory** *(string) --* 

                The working directory in which to run commands inside the container. This parameter maps to ``WorkingDir`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--workdir`` option to `docker run`_ .

                
              

              - **disableNetworking** *(boolean) --* 

                When this parameter is true, networking is disabled within the container. This parameter maps to ``NetworkDisabled`` in the `Create a container`_ section of the `Docker Remote API`_ .

                
              

              - **privileged** *(boolean) --* 

                When this parameter is true, the container is given elevated privileges on the host container instance (similar to the ``root`` user). This parameter maps to ``Privileged`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--privileged`` option to `docker run`_ .

                
              

              - **readonlyRootFilesystem** *(boolean) --* 

                When this parameter is true, the container is given read-only access to its root file system. This parameter maps to ``ReadonlyRootfs`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--read-only`` option to ``docker run`` .

                
              

              - **dnsServers** *(list) --* 

                A list of DNS servers that are presented to the container. This parameter maps to ``Dns`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns`` option to `docker run`_ .

                
                

                - *(string) --* 
            
              

              - **dnsSearchDomains** *(list) --* 

                A list of DNS search domains that are presented to the container. This parameter maps to ``DnsSearch`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns-search`` option to `docker run`_ .

                
                

                - *(string) --* 
            
              

              - **extraHosts** *(list) --* 

                A list of hostnames and IP address mappings to append to the ``/etc/hosts`` file on the container. This parameter maps to ``ExtraHosts`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--add-host`` option to `docker run`_ .

                
                

                - *(dict) --* 

                  Hostnames and IP address entries that are added to the ``/etc/hosts`` file of a container via the ``extraHosts`` parameter of its  ContainerDefinition . 

                  
                  

                  - **hostname** *(string) --* 

                    The hostname to use in the ``/etc/hosts`` entry.

                    
                  

                  - **ipAddress** *(string) --* 

                    The IP address to use in the ``/etc/hosts`` entry.

                    
              
            
              

              - **dockerSecurityOptions** *(list) --* 

                A list of strings to provide custom labels for SELinux and AppArmor multi-level security systems. This parameter maps to ``SecurityOpt`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--security-opt`` option to `docker run`_ .

                 

                .. note::

                   

                  The Amazon ECS container agent running on a container instance must register with the ``ECS_SELINUX_CAPABLE=true`` or ``ECS_APPARMOR_CAPABLE=true`` environment variables before containers placed on that instance can use these security options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

                   

                
                

                - *(string) --* 
            
              

              - **dockerLabels** *(dict) --* 

                A key/value map of labels to add to the container. This parameter maps to ``Labels`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--label`` option to `docker run`_ . This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                
                

                - *(string) --* 
                  

                  - *(string) --* 
            
          
              

              - **ulimits** *(list) --* 

                A list of ``ulimits`` to set in the container. This parameter maps to ``Ulimits`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--ulimit`` option to `docker run`_ . Valid naming values are displayed in the  Ulimit data type. This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                
                

                - *(dict) --* 

                  The ``ulimit`` settings to pass to the container.

                  
                  

                  - **name** *(string) --* 

                    The ``type`` of the ``ulimit`` .

                    
                  

                  - **softLimit** *(integer) --* 

                    The soft limit for the ulimit type.

                    
                  

                  - **hardLimit** *(integer) --* 

                    The hard limit for the ulimit type.

                    
              
            
              

              - **logConfiguration** *(dict) --* 

                The log configuration specification for the container. This parameter maps to ``LogConfig`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--log-driver`` option to `docker run`_ . By default, containers use the same logging driver that the Docker daemon uses; however the container may use a different logging driver than the Docker daemon by specifying a log driver with this parameter in the container definition. To use a different logging driver for a container, the log system must be configured properly on the container instance (or on a different log server for remote logging options). For more information on the options for different supported log drivers, see `Configure logging drivers`_ in the Docker documentation.

                 

                .. note::

                   

                  Amazon ECS currently supports a subset of the logging drivers available to the Docker daemon (shown in the  LogConfiguration data type). Currently unsupported log drivers may be available in future releases of the Amazon ECS container agent.

                   

                 

                This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                 

                .. note::

                   

                  The Amazon ECS container agent running on a container instance must register the logging drivers available on that instance with the ``ECS_AVAILABLE_LOGGING_DRIVERS`` environment variable before containers placed on that instance can use these log configuration options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

                   

                
                

                - **logDriver** *(string) --* 

                  The log driver to use for the container. The valid values listed for this parameter are log drivers that the Amazon ECS container agent can communicate with by default. 

                   

                  .. note::

                     

                    If you have a custom driver that is not listed above that you would like to work with the Amazon ECS container agent, you can fork the Amazon ECS container agent project that is `available on GitHub`_ and customize it to work with that driver. We encourage you to submit pull requests for changes that you would like to have included. However, Amazon Web Services does not currently provide support for running modified copies of this software.

                     

                   

                  This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                  
                

                - **options** *(dict) --* 

                  The configuration options to send to the log driver. This parameter requires version 1.19 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

                  
                  

                  - *(string) --* 
                    

                    - *(string) --* 
              
            
            
          
        
          

          - **family** *(string) --* 

            The family of your task definition, used as the definition name.

            
          

          - **taskRoleArn** *(string) --* 

            The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

            
          

          - **networkMode** *(string) --* 

            The Docker networking mode to use for the containers in the task. The valid values are ``none`` , ``bridge`` , and ``host`` . 

             

            If the network mode is ``none`` , the containers do not have external connectivity. The default Docker network mode is ``bridge`` . The ``host`` network mode offers the highest networking performance for containers because it uses the host network stack instead of the virtualized network stack provided by the ``bridge`` mode.

             

            For more information, see `Network settings`_ in the *Docker run reference* .

            
          

          - **revision** *(integer) --* 

            The revision of the task in a particular family. The revision is a version number of a task definition in a family. When you register a task definition for the first time, the revision is ``1`` ; each time you register a new revision of a task definition in the same family, the revision value always increases by one (even if you have deregistered previous revisions in this family).

            
          

          - **volumes** *(list) --* 

            The list of volumes in a task. For more information about volume definition parameters and defaults, see `Amazon ECS Task Definitions`_ in the *Amazon EC2 Container Service Developer Guide* .

            
            

            - *(dict) --* 

              A data volume used in a task definition.

              
              

              - **name** *(string) --* 

                The name of the volume. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This name is referenced in the ``sourceVolume`` parameter of container definition ``mountPoints`` .

                
              

              - **host** *(dict) --* 

                The contents of the ``host`` parameter determine whether your data volume persists on the host container instance and where it is stored. If the host parameter is empty, then the Docker daemon assigns a host path for your data volume, but the data is not guaranteed to persist after the containers associated with it stop running.

                
                

                - **sourcePath** *(string) --* 

                  The path on the host container instance that is presented to the container. If this parameter is empty, then the Docker daemon has assigned a host path for you. If the ``host`` parameter contains a ``sourcePath`` file location, then the data volume persists at the specified location on the host container instance until you delete it manually. If the ``sourcePath`` value does not exist on the host container instance, the Docker daemon creates it. If the location does exist, the contents of the source path folder are exported.

                  
            
          
        
          

          - **status** *(string) --* 

            The status of the task definition.

            
          

          - **requiresAttributes** *(list) --* 

            The container instance attributes required by your task.

            
            

            - *(dict) --* 

              The attributes applicable to a container instance when it is registered.

              
              

              - **name** *(string) --* 

                The name of the container instance attribute.

                
              

              - **value** *(string) --* 

                The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

                
          
        
      
    

  .. py:method:: run_task(**kwargs)

    

    Start a task using random placement and the default Amazon ECS scheduler. To use your own scheduler or place a task on a specific container instance, use ``StartTask`` instead.

     

    .. warning::

       

      The ``count`` parameter is limited to 10 tasks per call.

       

    

    **Request Syntax** 
    ::

      response = client.run_task(
          cluster='string',
          taskDefinition='string',
          overrides={
              'containerOverrides': [
                  {
                      'name': 'string',
                      'command': [
                          'string',
                      ],
                      'environment': [
                          {
                              'name': 'string',
                              'value': 'string'
                          },
                      ]
                  },
              ],
              'taskRoleArn': 'string'
          },
          count=123,
          startedBy='string'
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster on which to run your task. If you do not specify a cluster, the default cluster is assumed..

      

    
    :type taskDefinition: string
    :param taskDefinition: **[REQUIRED]** 

      The ``family`` and ``revision`` (``family:revision`` ) or full Amazon Resource Name (ARN) of the task definition to run. If a ``revision`` is not specified, the latest ``ACTIVE`` revision is used.

      

    
    :type overrides: dict
    :param overrides: 

      A list of container overrides in JSON format that specify the name of a container in the specified task definition and the overrides it should receive. You can override the default command for a container (that is specified in the task definition or Docker image) with a ``command`` override. You can also override existing environment variables (that are specified in the task definition or Docker image) on a container or add new environment variables to it with an ``environment`` override.

       

      .. note::

         

        A total of 8192 characters are allowed for overrides. This limit includes the JSON formatting characters of the override structure.

         

      

    
      - **containerOverrides** *(list) --* 

        One or more container overrides sent to a task.

        

      
        - *(dict) --* 

          The overrides that should be sent to a container.

          

        
          - **name** *(string) --* 

            The name of the container that receives the override.

            

          
          - **command** *(list) --* 

            The command to send to the container that overrides the default command from the Docker image or the task definition.

            

          
            - *(string) --* 

            
        
          - **environment** *(list) --* 

            The environment variables to send to the container. You can add new environment variables, which are added to the container at launch, or you can override the existing environment variables from the Docker image or the task definition.

            

          
            - *(dict) --* 

              A key and value pair object.

              

            
              - **name** *(string) --* 

                The name of the key value pair. For environment variables, this is the name of the environment variable.

                

              
              - **value** *(string) --* 

                The value of the key value pair. For environment variables, this is the value of the environment variable.

                

              
            
        
        
    
      - **taskRoleArn** *(string) --* 

        The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

        

      
    
    :type count: integer
    :param count: 

      The number of instantiations of the specified task to place on your cluster.

       

      .. warning::

         

        The ``count`` parameter is limited to 10 tasks per call.

         

      

    
    :type startedBy: string
    :param startedBy: 

      An optional tag specified when a task is started. For example if you automatically trigger a task to run a batch process job, you could apply a unique identifier for that job to your task with the ``startedBy`` parameter. You can then identify which tasks belong to that job by filtering the results of a  ListTasks call with the ``startedBy`` value. Up to 36 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed.

       

      If a task is started by an Amazon ECS service, then the ``startedBy`` parameter contains the deployment ID of the service that starts it.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'tasks': [
                {
                    'taskArn': 'string',
                    'clusterArn': 'string',
                    'taskDefinitionArn': 'string',
                    'containerInstanceArn': 'string',
                    'overrides': {
                        'containerOverrides': [
                            {
                                'name': 'string',
                                'command': [
                                    'string',
                                ],
                                'environment': [
                                    {
                                        'name': 'string',
                                        'value': 'string'
                                    },
                                ]
                            },
                        ],
                        'taskRoleArn': 'string'
                    },
                    'lastStatus': 'string',
                    'desiredStatus': 'string',
                    'containers': [
                        {
                            'containerArn': 'string',
                            'taskArn': 'string',
                            'name': 'string',
                            'lastStatus': 'string',
                            'exitCode': 123,
                            'reason': 'string',
                            'networkBindings': [
                                {
                                    'bindIP': 'string',
                                    'containerPort': 123,
                                    'hostPort': 123,
                                    'protocol': 'tcp'|'udp'
                                },
                            ]
                        },
                    ],
                    'startedBy': 'string',
                    'stoppedReason': 'string',
                    'createdAt': datetime(2015, 1, 1),
                    'startedAt': datetime(2015, 1, 1),
                    'stoppedAt': datetime(2015, 1, 1)
                },
            ],
            'failures': [
                {
                    'arn': 'string',
                    'reason': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **tasks** *(list) --* 

          A full description of the tasks that were run. Each task that was successfully placed on your cluster are described here.

          
          

          - *(dict) --* 

            Details on a task in a cluster.

            
            

            - **taskArn** *(string) --* 

              The Amazon Resource Name (ARN) of the task.

              
            

            - **clusterArn** *(string) --* 

              The Amazon Resource Name (ARN) of the cluster that hosts the task.

              
            

            - **taskDefinitionArn** *(string) --* 

              The Amazon Resource Name (ARN) of the task definition that creates the task.

              
            

            - **containerInstanceArn** *(string) --* 

              The Amazon Resource Name (ARN) of the container instances that host the task.

              
            

            - **overrides** *(dict) --* 

              One or more container overrides.

              
              

              - **containerOverrides** *(list) --* 

                One or more container overrides sent to a task.

                
                

                - *(dict) --* 

                  The overrides that should be sent to a container.

                  
                  

                  - **name** *(string) --* 

                    The name of the container that receives the override.

                    
                  

                  - **command** *(list) --* 

                    The command to send to the container that overrides the default command from the Docker image or the task definition.

                    
                    

                    - *(string) --* 
                
                  

                  - **environment** *(list) --* 

                    The environment variables to send to the container. You can add new environment variables, which are added to the container at launch, or you can override the existing environment variables from the Docker image or the task definition.

                    
                    

                    - *(dict) --* 

                      A key and value pair object.

                      
                      

                      - **name** *(string) --* 

                        The name of the key value pair. For environment variables, this is the name of the environment variable.

                        
                      

                      - **value** *(string) --* 

                        The value of the key value pair. For environment variables, this is the value of the environment variable.

                        
                  
                
              
            
              

              - **taskRoleArn** *(string) --* 

                The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

                
          
            

            - **lastStatus** *(string) --* 

              The last known status of the task.

              
            

            - **desiredStatus** *(string) --* 

              The desired status of the task.

              
            

            - **containers** *(list) --* 

              The containers associated with the task.

              
              

              - *(dict) --* 

                A Docker container that is part of a task.

                
                

                - **containerArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the container.

                  
                

                - **taskArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the task.

                  
                

                - **name** *(string) --* 

                  The name of the container.

                  
                

                - **lastStatus** *(string) --* 

                  The last known status of the container.

                  
                

                - **exitCode** *(integer) --* 

                  The exit code returned from the container.

                  
                

                - **reason** *(string) --* 

                  A short (255 max characters) human-readable string to provide additional detail about a running or stopped container.

                  
                

                - **networkBindings** *(list) --* 

                  The network bindings associated with the container.

                  
                  

                  - *(dict) --* 

                    Details on the network bindings between a container and its host container instance. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  DescribeTasks API responses.

                    
                    

                    - **bindIP** *(string) --* 

                      The IP address that the container is bound to on the container instance.

                      
                    

                    - **containerPort** *(integer) --* 

                      The port number on the container that is be used with the network binding.

                      
                    

                    - **hostPort** *(integer) --* 

                      The port number on the host that is used with the network binding.

                      
                    

                    - **protocol** *(string) --* 

                      The protocol used for the network binding.

                      
                
              
            
          
            

            - **startedBy** *(string) --* 

              The tag specified when a task is started. If the task is started by an Amazon ECS service, then the ``startedBy`` parameter contains the deployment ID of the service that starts it.

              
            

            - **stoppedReason** *(string) --* 

              The reason the task was stopped.

              
            

            - **createdAt** *(datetime) --* 

              The Unix timestamp for when the task was created (the task entered the ``PENDING`` state).

              
            

            - **startedAt** *(datetime) --* 

              The Unix timestamp for when the task was started (the task transitioned from the ``PENDING`` state to the ``RUNNING`` state).

              
            

            - **stoppedAt** *(datetime) --* 

              The Unix timestamp for when the task was stopped (the task transitioned from the ``RUNNING`` state to the ``STOPPED`` state).

              
        
      
        

        - **failures** *(list) --* 

          Any failures associated with the call.

          
          

          - *(dict) --* 

            A failed resource.

            
            

            - **arn** *(string) --* 

              The Amazon Resource Name (ARN) of the failed resource.

              
            

            - **reason** *(string) --* 

              The reason for the failure.

              
        
      
    

  .. py:method:: start_task(**kwargs)

    

    Starts a new task from the specified task definition on the specified container instance or instances. To use the default Amazon ECS scheduler to place your task, use ``RunTask`` instead.

     

    .. warning::

       

      The list of container instances to start tasks on is limited to 10.

       

    

    **Request Syntax** 
    ::

      response = client.start_task(
          cluster='string',
          taskDefinition='string',
          overrides={
              'containerOverrides': [
                  {
                      'name': 'string',
                      'command': [
                          'string',
                      ],
                      'environment': [
                          {
                              'name': 'string',
                              'value': 'string'
                          },
                      ]
                  },
              ],
              'taskRoleArn': 'string'
          },
          containerInstances=[
              'string',
          ],
          startedBy='string'
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster on which to start your task. If you do not specify a cluster, the default cluster is assumed..

      

    
    :type taskDefinition: string
    :param taskDefinition: **[REQUIRED]** 

      The ``family`` and ``revision`` (``family:revision`` ) or full Amazon Resource Name (ARN) of the task definition to start. If a ``revision`` is not specified, the latest ``ACTIVE`` revision is used.

      

    
    :type overrides: dict
    :param overrides: 

      A list of container overrides in JSON format that specify the name of a container in the specified task definition and the overrides it should receive. You can override the default command for a container (that is specified in the task definition or Docker image) with a ``command`` override. You can also override existing environment variables (that are specified in the task definition or Docker image) on a container or add new environment variables to it with an ``environment`` override.

       

      .. note::

         

        A total of 8192 characters are allowed for overrides. This limit includes the JSON formatting characters of the override structure.

         

      

    
      - **containerOverrides** *(list) --* 

        One or more container overrides sent to a task.

        

      
        - *(dict) --* 

          The overrides that should be sent to a container.

          

        
          - **name** *(string) --* 

            The name of the container that receives the override.

            

          
          - **command** *(list) --* 

            The command to send to the container that overrides the default command from the Docker image or the task definition.

            

          
            - *(string) --* 

            
        
          - **environment** *(list) --* 

            The environment variables to send to the container. You can add new environment variables, which are added to the container at launch, or you can override the existing environment variables from the Docker image or the task definition.

            

          
            - *(dict) --* 

              A key and value pair object.

              

            
              - **name** *(string) --* 

                The name of the key value pair. For environment variables, this is the name of the environment variable.

                

              
              - **value** *(string) --* 

                The value of the key value pair. For environment variables, this is the value of the environment variable.

                

              
            
        
        
    
      - **taskRoleArn** *(string) --* 

        The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

        

      
    
    :type containerInstances: list
    :param containerInstances: **[REQUIRED]** 

      The container instance IDs or full Amazon Resource Name (ARN) entries for the container instances on which you would like to place your task.

       

      .. warning::

         

        The list of container instances to start tasks on is limited to 10.

         

      

    
      - *(string) --* 

      
  
    :type startedBy: string
    :param startedBy: 

      An optional tag specified when a task is started. For example if you automatically trigger a task to run a batch process job, you could apply a unique identifier for that job to your task with the ``startedBy`` parameter. You can then identify which tasks belong to that job by filtering the results of a  ListTasks call with the ``startedBy`` value. Up to 36 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed.

       

      If a task is started by an Amazon ECS service, then the ``startedBy`` parameter contains the deployment ID of the service that starts it.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'tasks': [
                {
                    'taskArn': 'string',
                    'clusterArn': 'string',
                    'taskDefinitionArn': 'string',
                    'containerInstanceArn': 'string',
                    'overrides': {
                        'containerOverrides': [
                            {
                                'name': 'string',
                                'command': [
                                    'string',
                                ],
                                'environment': [
                                    {
                                        'name': 'string',
                                        'value': 'string'
                                    },
                                ]
                            },
                        ],
                        'taskRoleArn': 'string'
                    },
                    'lastStatus': 'string',
                    'desiredStatus': 'string',
                    'containers': [
                        {
                            'containerArn': 'string',
                            'taskArn': 'string',
                            'name': 'string',
                            'lastStatus': 'string',
                            'exitCode': 123,
                            'reason': 'string',
                            'networkBindings': [
                                {
                                    'bindIP': 'string',
                                    'containerPort': 123,
                                    'hostPort': 123,
                                    'protocol': 'tcp'|'udp'
                                },
                            ]
                        },
                    ],
                    'startedBy': 'string',
                    'stoppedReason': 'string',
                    'createdAt': datetime(2015, 1, 1),
                    'startedAt': datetime(2015, 1, 1),
                    'stoppedAt': datetime(2015, 1, 1)
                },
            ],
            'failures': [
                {
                    'arn': 'string',
                    'reason': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **tasks** *(list) --* 

          A full description of the tasks that were started. Each task that was successfully placed on your container instances are described here.

          
          

          - *(dict) --* 

            Details on a task in a cluster.

            
            

            - **taskArn** *(string) --* 

              The Amazon Resource Name (ARN) of the task.

              
            

            - **clusterArn** *(string) --* 

              The Amazon Resource Name (ARN) of the cluster that hosts the task.

              
            

            - **taskDefinitionArn** *(string) --* 

              The Amazon Resource Name (ARN) of the task definition that creates the task.

              
            

            - **containerInstanceArn** *(string) --* 

              The Amazon Resource Name (ARN) of the container instances that host the task.

              
            

            - **overrides** *(dict) --* 

              One or more container overrides.

              
              

              - **containerOverrides** *(list) --* 

                One or more container overrides sent to a task.

                
                

                - *(dict) --* 

                  The overrides that should be sent to a container.

                  
                  

                  - **name** *(string) --* 

                    The name of the container that receives the override.

                    
                  

                  - **command** *(list) --* 

                    The command to send to the container that overrides the default command from the Docker image or the task definition.

                    
                    

                    - *(string) --* 
                
                  

                  - **environment** *(list) --* 

                    The environment variables to send to the container. You can add new environment variables, which are added to the container at launch, or you can override the existing environment variables from the Docker image or the task definition.

                    
                    

                    - *(dict) --* 

                      A key and value pair object.

                      
                      

                      - **name** *(string) --* 

                        The name of the key value pair. For environment variables, this is the name of the environment variable.

                        
                      

                      - **value** *(string) --* 

                        The value of the key value pair. For environment variables, this is the value of the environment variable.

                        
                  
                
              
            
              

              - **taskRoleArn** *(string) --* 

                The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

                
          
            

            - **lastStatus** *(string) --* 

              The last known status of the task.

              
            

            - **desiredStatus** *(string) --* 

              The desired status of the task.

              
            

            - **containers** *(list) --* 

              The containers associated with the task.

              
              

              - *(dict) --* 

                A Docker container that is part of a task.

                
                

                - **containerArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the container.

                  
                

                - **taskArn** *(string) --* 

                  The Amazon Resource Name (ARN) of the task.

                  
                

                - **name** *(string) --* 

                  The name of the container.

                  
                

                - **lastStatus** *(string) --* 

                  The last known status of the container.

                  
                

                - **exitCode** *(integer) --* 

                  The exit code returned from the container.

                  
                

                - **reason** *(string) --* 

                  A short (255 max characters) human-readable string to provide additional detail about a running or stopped container.

                  
                

                - **networkBindings** *(list) --* 

                  The network bindings associated with the container.

                  
                  

                  - *(dict) --* 

                    Details on the network bindings between a container and its host container instance. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  DescribeTasks API responses.

                    
                    

                    - **bindIP** *(string) --* 

                      The IP address that the container is bound to on the container instance.

                      
                    

                    - **containerPort** *(integer) --* 

                      The port number on the container that is be used with the network binding.

                      
                    

                    - **hostPort** *(integer) --* 

                      The port number on the host that is used with the network binding.

                      
                    

                    - **protocol** *(string) --* 

                      The protocol used for the network binding.

                      
                
              
            
          
            

            - **startedBy** *(string) --* 

              The tag specified when a task is started. If the task is started by an Amazon ECS service, then the ``startedBy`` parameter contains the deployment ID of the service that starts it.

              
            

            - **stoppedReason** *(string) --* 

              The reason the task was stopped.

              
            

            - **createdAt** *(datetime) --* 

              The Unix timestamp for when the task was created (the task entered the ``PENDING`` state).

              
            

            - **startedAt** *(datetime) --* 

              The Unix timestamp for when the task was started (the task transitioned from the ``PENDING`` state to the ``RUNNING`` state).

              
            

            - **stoppedAt** *(datetime) --* 

              The Unix timestamp for when the task was stopped (the task transitioned from the ``RUNNING`` state to the ``STOPPED`` state).

              
        
      
        

        - **failures** *(list) --* 

          Any failures associated with the call.

          
          

          - *(dict) --* 

            A failed resource.

            
            

            - **arn** *(string) --* 

              The Amazon Resource Name (ARN) of the failed resource.

              
            

            - **reason** *(string) --* 

              The reason for the failure.

              
        
      
    

  .. py:method:: stop_task(**kwargs)

    

    Stops a running task.

     

    When  StopTask is called on a task, the equivalent of ``docker stop`` is issued to the containers running in the task. This results in a ``SIGTERM`` and a 30-second timeout, after which ``SIGKILL`` is sent and the containers are forcibly stopped. If the container handles the ``SIGTERM`` gracefully and exits within 30 seconds from receiving it, no ``SIGKILL`` is sent.

    

    **Request Syntax** 
    ::

      response = client.stop_task(
          cluster='string',
          task='string',
          reason='string'
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task to stop. If you do not specify a cluster, the default cluster is assumed..

      

    
    :type task: string
    :param task: **[REQUIRED]** 

      The task ID or full Amazon Resource Name (ARN) entry of the task to stop.

      

    
    :type reason: string
    :param reason: 

      An optional message specified when a task is stopped. For example, if you are using a custom scheduler, you can use this parameter to specify the reason for stopping the task here, and the message will appear in subsequent  DescribeTasks API operations on this task. Up to 255 characters are allowed in this message.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'task': {
                'taskArn': 'string',
                'clusterArn': 'string',
                'taskDefinitionArn': 'string',
                'containerInstanceArn': 'string',
                'overrides': {
                    'containerOverrides': [
                        {
                            'name': 'string',
                            'command': [
                                'string',
                            ],
                            'environment': [
                                {
                                    'name': 'string',
                                    'value': 'string'
                                },
                            ]
                        },
                    ],
                    'taskRoleArn': 'string'
                },
                'lastStatus': 'string',
                'desiredStatus': 'string',
                'containers': [
                    {
                        'containerArn': 'string',
                        'taskArn': 'string',
                        'name': 'string',
                        'lastStatus': 'string',
                        'exitCode': 123,
                        'reason': 'string',
                        'networkBindings': [
                            {
                                'bindIP': 'string',
                                'containerPort': 123,
                                'hostPort': 123,
                                'protocol': 'tcp'|'udp'
                            },
                        ]
                    },
                ],
                'startedBy': 'string',
                'stoppedReason': 'string',
                'createdAt': datetime(2015, 1, 1),
                'startedAt': datetime(2015, 1, 1),
                'stoppedAt': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **task** *(dict) --* 

          Details on a task in a cluster.

          
          

          - **taskArn** *(string) --* 

            The Amazon Resource Name (ARN) of the task.

            
          

          - **clusterArn** *(string) --* 

            The Amazon Resource Name (ARN) of the cluster that hosts the task.

            
          

          - **taskDefinitionArn** *(string) --* 

            The Amazon Resource Name (ARN) of the task definition that creates the task.

            
          

          - **containerInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the container instances that host the task.

            
          

          - **overrides** *(dict) --* 

            One or more container overrides.

            
            

            - **containerOverrides** *(list) --* 

              One or more container overrides sent to a task.

              
              

              - *(dict) --* 

                The overrides that should be sent to a container.

                
                

                - **name** *(string) --* 

                  The name of the container that receives the override.

                  
                

                - **command** *(list) --* 

                  The command to send to the container that overrides the default command from the Docker image or the task definition.

                  
                  

                  - *(string) --* 
              
                

                - **environment** *(list) --* 

                  The environment variables to send to the container. You can add new environment variables, which are added to the container at launch, or you can override the existing environment variables from the Docker image or the task definition.

                  
                  

                  - *(dict) --* 

                    A key and value pair object.

                    
                    

                    - **name** *(string) --* 

                      The name of the key value pair. For environment variables, this is the name of the environment variable.

                      
                    

                    - **value** *(string) --* 

                      The value of the key value pair. For environment variables, this is the value of the environment variable.

                      
                
              
            
          
            

            - **taskRoleArn** *(string) --* 

              The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

              
        
          

          - **lastStatus** *(string) --* 

            The last known status of the task.

            
          

          - **desiredStatus** *(string) --* 

            The desired status of the task.

            
          

          - **containers** *(list) --* 

            The containers associated with the task.

            
            

            - *(dict) --* 

              A Docker container that is part of a task.

              
              

              - **containerArn** *(string) --* 

                The Amazon Resource Name (ARN) of the container.

                
              

              - **taskArn** *(string) --* 

                The Amazon Resource Name (ARN) of the task.

                
              

              - **name** *(string) --* 

                The name of the container.

                
              

              - **lastStatus** *(string) --* 

                The last known status of the container.

                
              

              - **exitCode** *(integer) --* 

                The exit code returned from the container.

                
              

              - **reason** *(string) --* 

                A short (255 max characters) human-readable string to provide additional detail about a running or stopped container.

                
              

              - **networkBindings** *(list) --* 

                The network bindings associated with the container.

                
                

                - *(dict) --* 

                  Details on the network bindings between a container and its host container instance. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  DescribeTasks API responses.

                  
                  

                  - **bindIP** *(string) --* 

                    The IP address that the container is bound to on the container instance.

                    
                  

                  - **containerPort** *(integer) --* 

                    The port number on the container that is be used with the network binding.

                    
                  

                  - **hostPort** *(integer) --* 

                    The port number on the host that is used with the network binding.

                    
                  

                  - **protocol** *(string) --* 

                    The protocol used for the network binding.

                    
              
            
          
        
          

          - **startedBy** *(string) --* 

            The tag specified when a task is started. If the task is started by an Amazon ECS service, then the ``startedBy`` parameter contains the deployment ID of the service that starts it.

            
          

          - **stoppedReason** *(string) --* 

            The reason the task was stopped.

            
          

          - **createdAt** *(datetime) --* 

            The Unix timestamp for when the task was created (the task entered the ``PENDING`` state).

            
          

          - **startedAt** *(datetime) --* 

            The Unix timestamp for when the task was started (the task transitioned from the ``PENDING`` state to the ``RUNNING`` state).

            
          

          - **stoppedAt** *(datetime) --* 

            The Unix timestamp for when the task was stopped (the task transitioned from the ``RUNNING`` state to the ``STOPPED`` state).

            
      
    

  .. py:method:: submit_container_state_change(**kwargs)

    

    .. note::

       

      This action is only used by the Amazon EC2 Container Service agent, and it is not intended for use outside of the agent.

       

     

    Sent to acknowledge that a container changed states.

    

    **Request Syntax** 
    ::

      response = client.submit_container_state_change(
          cluster='string',
          task='string',
          containerName='string',
          status='string',
          exitCode=123,
          reason='string',
          networkBindings=[
              {
                  'bindIP': 'string',
                  'containerPort': 123,
                  'hostPort': 123,
                  'protocol': 'tcp'|'udp'
              },
          ]
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container.

      

    
    :type task: string
    :param task: 

      The task ID or full Amazon Resource Name (ARN) of the task that hosts the container.

      

    
    :type containerName: string
    :param containerName: 

      The name of the container.

      

    
    :type status: string
    :param status: 

      The status of the state change request.

      

    
    :type exitCode: integer
    :param exitCode: 

      The exit code returned for the state change request.

      

    
    :type reason: string
    :param reason: 

      The reason for the state change request.

      

    
    :type networkBindings: list
    :param networkBindings: 

      The network bindings of the container.

      

    
      - *(dict) --* 

        Details on the network bindings between a container and its host container instance. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  DescribeTasks API responses.

        

      
        - **bindIP** *(string) --* 

          The IP address that the container is bound to on the container instance.

          

        
        - **containerPort** *(integer) --* 

          The port number on the container that is be used with the network binding.

          

        
        - **hostPort** *(integer) --* 

          The port number on the host that is used with the network binding.

          

        
        - **protocol** *(string) --* 

          The protocol used for the network binding.

          

        
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'acknowledgment': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **acknowledgment** *(string) --* 

          Acknowledgement of the state change.

          
    

  .. py:method:: submit_task_state_change(**kwargs)

    

    .. note::

       

      This action is only used by the Amazon EC2 Container Service agent, and it is not intended for use outside of the agent.

       

     

    Sent to acknowledge that a task changed states.

    

    **Request Syntax** 
    ::

      response = client.submit_task_state_change(
          cluster='string',
          task='string',
          status='string',
          reason='string'
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task.

      

    
    :type task: string
    :param task: 

      The task ID or full Amazon Resource Name (ARN) of the task in the state change request.

      

    
    :type status: string
    :param status: 

      The status of the state change request.

      

    
    :type reason: string
    :param reason: 

      The reason for the state change request.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'acknowledgment': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **acknowledgment** *(string) --* 

          Acknowledgement of the state change.

          
    

  .. py:method:: update_container_agent(**kwargs)

    

    Updates the Amazon ECS container agent on a specified container instance. Updating the Amazon ECS container agent does not interrupt running tasks or services on the container instance. The process for updating the agent differs depending on whether your container instance was launched with the Amazon ECS-optimized AMI or another operating system.

     

     ``UpdateContainerAgent`` requires the Amazon ECS-optimized AMI or Amazon Linux with the ``ecs-init`` service installed and running. For help updating the Amazon ECS container agent on other operating systems, see `Manually Updating the Amazon ECS Container Agent`_ in the *Amazon EC2 Container Service Developer Guide* .

    

    **Request Syntax** 
    ::

      response = client.update_container_agent(
          cluster='string',
          containerInstance='string'
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that your container instance is running on. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type containerInstance: string
    :param containerInstance: **[REQUIRED]** 

      The container instance ID or full Amazon Resource Name (ARN) entries for the container instance on which you would like to update the Amazon ECS container agent.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'containerInstance': {
                'containerInstanceArn': 'string',
                'ec2InstanceId': 'string',
                'versionInfo': {
                    'agentVersion': 'string',
                    'agentHash': 'string',
                    'dockerVersion': 'string'
                },
                'remainingResources': [
                    {
                        'name': 'string',
                        'type': 'string',
                        'doubleValue': 123.0,
                        'longValue': 123,
                        'integerValue': 123,
                        'stringSetValue': [
                            'string',
                        ]
                    },
                ],
                'registeredResources': [
                    {
                        'name': 'string',
                        'type': 'string',
                        'doubleValue': 123.0,
                        'longValue': 123,
                        'integerValue': 123,
                        'stringSetValue': [
                            'string',
                        ]
                    },
                ],
                'status': 'string',
                'agentConnected': True|False,
                'runningTasksCount': 123,
                'pendingTasksCount': 123,
                'agentUpdateStatus': 'PENDING'|'STAGING'|'STAGED'|'UPDATING'|'UPDATED'|'FAILED',
                'attributes': [
                    {
                        'name': 'string',
                        'value': 'string'
                    },
                ]
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **containerInstance** *(dict) --* 

          An EC2 instance that is running the Amazon ECS agent and has been registered with a cluster.

          
          

          - **containerInstanceArn** *(string) --* 

            The Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, ``arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* `` .

            
          

          - **ec2InstanceId** *(string) --* 

            The EC2 instance ID of the container instance.

            
          

          - **versionInfo** *(dict) --* 

            The version information for the Amazon ECS container agent and Docker daemon running on the container instance.

            
            

            - **agentVersion** *(string) --* 

              The version number of the Amazon ECS container agent.

              
            

            - **agentHash** *(string) --* 

              The Git commit hash for the Amazon ECS container agent build on the `amazon-ecs-agent`_ GitHub repository.

              
            

            - **dockerVersion** *(string) --* 

              The Docker version running on the container instance.

              
        
          

          - **remainingResources** *(list) --* 

            The remaining resources of the container instance that are available for new tasks.

            
            

            - *(dict) --* 

              Describes the resources available for a container instance.

              
              

              - **name** *(string) --* 

                The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

                
              

              - **type** *(string) --* 

                The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

                
              

              - **doubleValue** *(float) --* 

                When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

                
              

              - **longValue** *(integer) --* 

                When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

                
              

              - **integerValue** *(integer) --* 

                When the ``integerValue`` type is set, the value of the resource must be an integer.

                
              

              - **stringSetValue** *(list) --* 

                When the ``stringSetValue`` type is set, the value of the resource must be a string type.

                
                

                - *(string) --* 
            
          
        
          

          - **registeredResources** *(list) --* 

            The registered resources on the container instance that are in use by current tasks.

            
            

            - *(dict) --* 

              Describes the resources available for a container instance.

              
              

              - **name** *(string) --* 

                The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

                
              

              - **type** *(string) --* 

                The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

                
              

              - **doubleValue** *(float) --* 

                When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

                
              

              - **longValue** *(integer) --* 

                When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

                
              

              - **integerValue** *(integer) --* 

                When the ``integerValue`` type is set, the value of the resource must be an integer.

                
              

              - **stringSetValue** *(list) --* 

                When the ``stringSetValue`` type is set, the value of the resource must be a string type.

                
                

                - *(string) --* 
            
          
        
          

          - **status** *(string) --* 

            The status of the container instance. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that the container instance can accept tasks.

            
          

          - **agentConnected** *(boolean) --* 

            This parameter returns ``true`` if the agent is actually connected to Amazon ECS. Registered instances with an agent that may be unhealthy or stopped return ``false`` , and instances without a connected agent cannot accept placement requests.

            
          

          - **runningTasksCount** *(integer) --* 

            The number of tasks on the container instance that are in the ``RUNNING`` status.

            
          

          - **pendingTasksCount** *(integer) --* 

            The number of tasks on the container instance that are in the ``PENDING`` status.

            
          

          - **agentUpdateStatus** *(string) --* 

            The status of the most recent agent update. If an update has never been requested, this value is ``NULL`` .

            
          

          - **attributes** *(list) --* 

            The attributes set for the container instance by the Amazon ECS container agent at instance registration.

            
            

            - *(dict) --* 

              The attributes applicable to a container instance when it is registered.

              
              

              - **name** *(string) --* 

                The name of the container instance attribute.

                
              

              - **value** *(string) --* 

                The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

                
          
        
      
    

  .. py:method:: update_service(**kwargs)

    

    Modifies the desired count, deployment configuration, or task definition used in a service.

     

    You can add to or subtract from the number of instantiations of a task definition in a service by specifying the cluster that the service is running in and a new ``desiredCount`` parameter.

     

    You can use  UpdateService to modify your task definition and deploy a new version of your service.

     

    You can also update the deployment configuration of a service. When a deployment is triggered by updating the task definition of a service, the service scheduler uses the deployment configuration parameters, ``minimumHealthyPercent`` and ``maximumPercent`` , to determine the deployment strategy.

     

    If the ``minimumHealthyPercent`` is below 100%, the scheduler can ignore the ``desiredCount`` temporarily during a deployment. For example, if your service has a ``desiredCount`` of four tasks, a ``minimumHealthyPercent`` of 50% allows the scheduler to stop two existing tasks before starting two new tasks. Tasks for services that *do not* use a load balancer are considered healthy if they are in the ``RUNNING`` state; tasks for services that *do* use a load balancer are considered healthy if they are in the ``RUNNING`` state and the container instance it is hosted on is reported as healthy by the load balancer.

     

    The ``maximumPercent`` parameter represents an upper limit on the number of running tasks during a deployment, which enables you to define the deployment batch size. For example, if your service has a ``desiredCount`` of four tasks, a ``maximumPercent`` value of 200% starts four new tasks before stopping the four older tasks (provided that the cluster resources required to do this are available).

     

    When  UpdateService stops a task during a deployment, the equivalent of ``docker stop`` is issued to the containers running in the task. This results in a ``SIGTERM`` and a 30-second timeout, after which ``SIGKILL`` is sent and the containers are forcibly stopped. If the container handles the ``SIGTERM`` gracefully and exits within 30 seconds from receiving it, no ``SIGKILL`` is sent.

     

    When the service scheduler launches new tasks, it attempts to balance them across the Availability Zones in your cluster with the following logic:

     

     
    * Determine which of the container instances in your cluster can support your service's task definition (for example, they have the required CPU, memory, ports, and container instance attributes). 
     
    * Sort the valid container instances by the fewest number of running tasks for this service in the same Availability Zone as the instance. For example, if zone A has one running service task and zones B and C each have zero, valid container instances in either zone B or C are considered optimal for placement. 
     
    * Place the new service task on a valid container instance in an optimal Availability Zone (based on the previous steps), favoring container instances with the fewest number of running tasks for this service. 
     

    

    **Request Syntax** 
    ::

      response = client.update_service(
          cluster='string',
          service='string',
          desiredCount=123,
          taskDefinition='string',
          deploymentConfiguration={
              'maximumPercent': 123,
              'minimumHealthyPercent': 123
          }
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that your service is running on. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type service: string
    :param service: **[REQUIRED]** 

      The name of the service to update.

      

    
    :type desiredCount: integer
    :param desiredCount: 

      The number of instantiations of the task to place and keep running in your service.

      

    
    :type taskDefinition: string
    :param taskDefinition: 

      The ``family`` and ``revision`` (``family:revision`` ) or full Amazon Resource Name (ARN) of the task definition to run in your service. If a ``revision`` is not specified, the latest ``ACTIVE`` revision is used. If you modify the task definition with ``UpdateService`` , Amazon ECS spawns a task with the new version of the task definition and then stops an old task after the new version is running.

      

    
    :type deploymentConfiguration: dict
    :param deploymentConfiguration: 

      Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

      

    
      - **maximumPercent** *(integer) --* 

        The upper limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that can be running in a service during a deployment. The maximum number of tasks during a deployment is the ``desiredCount`` multiplied by the ``maximumPercent`` /100, rounded down to the nearest integer value.

        

      
      - **minimumHealthyPercent** *(integer) --* 

        The lower limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that must remain running and healthy in a service during a deployment. The minimum healthy tasks during a deployment is the ``desiredCount`` multiplied by the ``minimumHealthyPercent`` /100, rounded up to the nearest integer value.

        

      
    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'service': {
                'serviceArn': 'string',
                'serviceName': 'string',
                'clusterArn': 'string',
                'loadBalancers': [
                    {
                        'targetGroupArn': 'string',
                        'loadBalancerName': 'string',
                        'containerName': 'string',
                        'containerPort': 123
                    },
                ],
                'status': 'string',
                'desiredCount': 123,
                'runningCount': 123,
                'pendingCount': 123,
                'taskDefinition': 'string',
                'deploymentConfiguration': {
                    'maximumPercent': 123,
                    'minimumHealthyPercent': 123
                },
                'deployments': [
                    {
                        'id': 'string',
                        'status': 'string',
                        'taskDefinition': 'string',
                        'desiredCount': 123,
                        'pendingCount': 123,
                        'runningCount': 123,
                        'createdAt': datetime(2015, 1, 1),
                        'updatedAt': datetime(2015, 1, 1)
                    },
                ],
                'roleArn': 'string',
                'events': [
                    {
                        'id': 'string',
                        'createdAt': datetime(2015, 1, 1),
                        'message': 'string'
                    },
                ],
                'createdAt': datetime(2015, 1, 1)
            }
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **service** *(dict) --* 

          The full description of your service following the update call.

          
          

          - **serviceArn** *(string) --* 

            The Amazon Resource Name (ARN) that identifies the service. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the service, the AWS account ID of the service owner, the ``service`` namespace, and then the service name. For example, ``arn:aws:ecs:*region* :*012345678910* :service/*my-service* `` .

            
          

          - **serviceName** *(string) --* 

            The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a region or across multiple regions.

            
          

          - **clusterArn** *(string) --* 

            The Amazon Resource Name (ARN) of the cluster that hosts the service.

            
          

          - **loadBalancers** *(list) --* 

            A list of Elastic Load Balancing load balancer objects, containing the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer.

            
            

            - *(dict) --* 

              Details on a load balancer that is used with a service.

              
              

              - **targetGroupArn** *(string) --* 

                The full Amazon Resource Name (ARN) of the Elastic Load Balancing target group associated with a service.

                
              

              - **loadBalancerName** *(string) --* 

                The name of the load balancer.

                
              

              - **containerName** *(string) --* 

                The name of the container (as it appears in a container definition) to associate with the load balancer.

                
              

              - **containerPort** *(integer) --* 

                The port on the container to associate with the load balancer. This port must correspond to a ``containerPort`` in the service's task definition. Your container instances must allow ingress traffic on the ``hostPort`` of the port mapping.

                
          
        
          

          - **status** *(string) --* 

            The status of the service. The valid values are ``ACTIVE`` , ``DRAINING`` , or ``INACTIVE`` .

            
          

          - **desiredCount** *(integer) --* 

            The desired number of instantiations of the task definition to keep running on the service. This value is specified when the service is created with  CreateService , and it can be modified with  UpdateService .

            
          

          - **runningCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``RUNNING`` state.

            
          

          - **pendingCount** *(integer) --* 

            The number of tasks in the cluster that are in the ``PENDING`` state.

            
          

          - **taskDefinition** *(string) --* 

            The task definition to use for tasks in the service. This value is specified when the service is created with  CreateService , and it can be modified with  UpdateService .

            
          

          - **deploymentConfiguration** *(dict) --* 

            Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

            
            

            - **maximumPercent** *(integer) --* 

              The upper limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that can be running in a service during a deployment. The maximum number of tasks during a deployment is the ``desiredCount`` multiplied by the ``maximumPercent`` /100, rounded down to the nearest integer value.

              
            

            - **minimumHealthyPercent** *(integer) --* 

              The lower limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that must remain running and healthy in a service during a deployment. The minimum healthy tasks during a deployment is the ``desiredCount`` multiplied by the ``minimumHealthyPercent`` /100, rounded up to the nearest integer value.

              
        
          

          - **deployments** *(list) --* 

            The current state of deployments for the service.

            
            

            - *(dict) --* 

              The details of an Amazon ECS service deployment.

              
              

              - **id** *(string) --* 

                The ID of the deployment.

                
              

              - **status** *(string) --* 

                The status of the deployment. Valid values are ``PRIMARY`` (for the most recent deployment), ``ACTIVE`` (for previous deployments that still have tasks running, but are being replaced with the ``PRIMARY`` deployment), and ``INACTIVE`` (for deployments that have been completely replaced).

                
              

              - **taskDefinition** *(string) --* 

                The most recent task definition that was specified for the service to use.

                
              

              - **desiredCount** *(integer) --* 

                The most recent desired count of tasks that was specified for the service to deploy or maintain.

                
              

              - **pendingCount** *(integer) --* 

                The number of tasks in the deployment that are in the ``PENDING`` status.

                
              

              - **runningCount** *(integer) --* 

                The number of tasks in the deployment that are in the ``RUNNING`` status.

                
              

              - **createdAt** *(datetime) --* 

                The Unix timestamp for when the service was created.

                
              

              - **updatedAt** *(datetime) --* 

                The Unix timestamp for when the service was last updated.

                
          
        
          

          - **roleArn** *(string) --* 

            The Amazon Resource Name (ARN) of the IAM role associated with the service that allows the Amazon ECS container agent to register container instances with an Elastic Load Balancing load balancer.

            
          

          - **events** *(list) --* 

            The event stream for your service. A maximum of 100 of the latest events are displayed.

            
            

            - *(dict) --* 

              Details on an event associated with a service.

              
              

              - **id** *(string) --* 

                The ID string of the event.

                
              

              - **createdAt** *(datetime) --* 

                The Unix timestamp for when the event was triggered.

                
              

              - **message** *(string) --* 

                The event message.

                
          
        
          

          - **createdAt** *(datetime) --* 

            The Unix timestamp for when the service was created.

            
      
    

==========
Paginators
==========


The available paginators are:

* :py:class:`ECS.Paginator.ListClusters`


* :py:class:`ECS.Paginator.ListContainerInstances`


* :py:class:`ECS.Paginator.ListServices`


* :py:class:`ECS.Paginator.ListTaskDefinitionFamilies`


* :py:class:`ECS.Paginator.ListTaskDefinitions`


* :py:class:`ECS.Paginator.ListTasks`



.. py:class:: ECS.Paginator.ListClusters

  ::

    
    paginator = client.get_paginator('list_clusters')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ECS.Client.list_clusters`.

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
            'clusterArns': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **clusterArns** *(list) --* 

          The list of full Amazon Resource Name (ARN) entries for each cluster associated with your account.

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: ECS.Paginator.ListContainerInstances

  ::

    
    paginator = client.get_paginator('list_container_instances')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ECS.Client.list_container_instances`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          cluster='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instances to list. If you do not specify a cluster, the default cluster is assumed..

      

    
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
            'containerInstanceArns': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **containerInstanceArns** *(list) --* 

          The list of container instances with full Amazon Resource Name (ARN) entries for each container instance associated with the specified cluster.

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: ECS.Paginator.ListServices

  ::

    
    paginator = client.get_paginator('list_services')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ECS.Client.list_services`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          cluster='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the services to list. If you do not specify a cluster, the default cluster is assumed..

      

    
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
            'serviceArns': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **serviceArns** *(list) --* 

          The list of full Amazon Resource Name (ARN) entries for each service associated with the specified cluster.

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: ECS.Paginator.ListTaskDefinitionFamilies

  ::

    
    paginator = client.get_paginator('list_task_definition_families')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ECS.Client.list_task_definition_families`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          familyPrefix='string',
          status='ACTIVE'|'INACTIVE'|'ALL',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type familyPrefix: string
    :param familyPrefix: 

      The ``familyPrefix`` is a string that is used to filter the results of ``ListTaskDefinitionFamilies`` . If you specify a ``familyPrefix`` , only task definition family names that begin with the ``familyPrefix`` string are returned.

      

    
    :type status: string
    :param status: 

      The task definition family status with which to filter the ``ListTaskDefinitionFamilies`` results. By default, both ``ACTIVE`` and ``INACTIVE`` task definition families are listed. If this parameter is set to ``ACTIVE`` , only task definition families that have an ``ACTIVE`` task definition revision are returned. If this parameter is set to ``INACTIVE`` , only task definition families that do not have any ``ACTIVE`` task definition revisions are returned. If you paginate the resulting output, be sure to keep the ``status`` value constant in each subsequent request.

      

    
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
            'families': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **families** *(list) --* 

          The list of task definition family names that match the ``ListTaskDefinitionFamilies`` request.

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: ECS.Paginator.ListTaskDefinitions

  ::

    
    paginator = client.get_paginator('list_task_definitions')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ECS.Client.list_task_definitions`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          familyPrefix='string',
          status='ACTIVE'|'INACTIVE',
          sort='ASC'|'DESC',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type familyPrefix: string
    :param familyPrefix: 

      The full family name with which to filter the ``ListTaskDefinitions`` results. Specifying a ``familyPrefix`` limits the listed task definitions to task definition revisions that belong to that family.

      

    
    :type status: string
    :param status: 

      The task definition status with which to filter the ``ListTaskDefinitions`` results. By default, only ``ACTIVE`` task definitions are listed. By setting this parameter to ``INACTIVE`` , you can view task definitions that are ``INACTIVE`` as long as an active task or service still references them. If you paginate the resulting output, be sure to keep the ``status`` value constant in each subsequent request.

      

    
    :type sort: string
    :param sort: 

      The order in which to sort the results. Valid values are ``ASC`` and ``DESC`` . By default (``ASC`` ), task definitions are listed lexicographically by family name and in ascending numerical order by revision so that the newest task definitions in a family are listed last. Setting this parameter to ``DESC`` reverses the sort order on family name and revision so that the newest task definitions in a family are listed first.

      

    
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
            'taskDefinitionArns': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **taskDefinitionArns** *(list) --* 

          The list of task definition Amazon Resource Name (ARN) entries for the ``ListTaskDefinitions`` request.

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: ECS.Paginator.ListTasks

  ::

    
    paginator = client.get_paginator('list_tasks')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`ECS.Client.list_tasks`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          cluster='string',
          containerInstance='string',
          family='string',
          startedBy='string',
          serviceName='string',
          desiredStatus='RUNNING'|'PENDING'|'STOPPED',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the tasks to list. If you do not specify a cluster, the default cluster is assumed..

      

    
    :type containerInstance: string
    :param containerInstance: 

      The container instance ID or full Amazon Resource Name (ARN) of the container instance with which to filter the ``ListTasks`` results. Specifying a ``containerInstance`` limits the results to tasks that belong to that container instance.

      

    
    :type family: string
    :param family: 

      The name of the family with which to filter the ``ListTasks`` results. Specifying a ``family`` limits the results to tasks that belong to that family.

      

    
    :type startedBy: string
    :param startedBy: 

      The ``startedBy`` value with which to filter the task results. Specifying a ``startedBy`` value limits the results to tasks that were started with that value.

      

    
    :type serviceName: string
    :param serviceName: 

      The name of the service with which to filter the ``ListTasks`` results. Specifying a ``serviceName`` limits the results to tasks that belong to that service.

      

    
    :type desiredStatus: string
    :param desiredStatus: 

      The task desired status with which to filter the ``ListTasks`` results. Specifying a ``desiredStatus`` of ``STOPPED`` limits the results to tasks that ECS has set the desired status to ``STOPPED`` , which can be useful for debugging tasks that are not starting properly or have died or finished. The default status filter is ``RUNNING`` , which shows tasks that ECS has set the desired status to ``RUNNING`` .

       

      .. note::

         

        Although you can filter results based on a desired status of ``PENDING`` , this will not return any results because ECS never sets the desired status of a task to that value (only a task's ``lastStatus`` may have a value of ``PENDING`` ).

         

      

    
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
            'taskArns': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 
        

        - **taskArns** *(list) --* 

          The list of task Amazon Resource Name (ARN) entries for the ``ListTasks`` request.

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

=======
Waiters
=======


The available waiters are:

* :py:class:`ECS.Waiter.ServicesInactive`


* :py:class:`ECS.Waiter.ServicesStable`


* :py:class:`ECS.Waiter.TasksRunning`


* :py:class:`ECS.Waiter.TasksStopped`



.. py:class:: ECS.Waiter.ServicesInactive

  ::

    
    waiter = client.get_waiter('services_inactive')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`ECS.Client.describe_services` every 15 seconds until a successful state is reached. An error is returned after 40 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          cluster='string',
          services=[
              'string',
          ]
      )
    :type cluster: string
    :param cluster: 

      The name of the cluster that hosts the service to describe. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type services: list
    :param services: **[REQUIRED]** 

      A list of services to describe.

      

    
      - *(string) --* 

      
  
    
    :returns: None

.. py:class:: ECS.Waiter.ServicesStable

  ::

    
    waiter = client.get_waiter('services_stable')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`ECS.Client.describe_services` every 15 seconds until a successful state is reached. An error is returned after 40 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          cluster='string',
          services=[
              'string',
          ]
      )
    :type cluster: string
    :param cluster: 

      The name of the cluster that hosts the service to describe. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type services: list
    :param services: **[REQUIRED]** 

      A list of services to describe.

      

    
      - *(string) --* 

      
  
    
    :returns: None

.. py:class:: ECS.Waiter.TasksRunning

  ::

    
    waiter = client.get_waiter('tasks_running')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`ECS.Client.describe_tasks` every 6 seconds until a successful state is reached. An error is returned after 100 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          cluster='string',
          tasks=[
              'string',
          ]
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task to describe. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type tasks: list
    :param tasks: **[REQUIRED]** 

      A space-separated list of task IDs or full Amazon Resource Name (ARN) entries.

      

    
      - *(string) --* 

      
  
    
    :returns: None

.. py:class:: ECS.Waiter.TasksStopped

  ::

    
    waiter = client.get_waiter('tasks_stopped')

  
  

  .. py:method:: wait(**kwargs)

    Polls :py:meth:`ECS.Client.describe_tasks` every 6 seconds until a successful state is reached. An error is returned after 100 failed checks.

    **Request Syntax** 
    ::

      waiter.wait(
          cluster='string',
          tasks=[
              'string',
          ]
      )
    :type cluster: string
    :param cluster: 

      The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task to describe. If you do not specify a cluster, the default cluster is assumed.

      

    
    :type tasks: list
    :param tasks: **[REQUIRED]** 

      A space-separated list of task IDs or full Amazon Resource Name (ARN) entries.

      

    
      - *(string) --* 

      
  
    
    :returns: None