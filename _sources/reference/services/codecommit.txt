

.. _Viewing the Commit History: http://git-scm.com/book/ch2-3.html
.. _Limits: http://docs.aws.amazon.com/codecommit/latest/userguide/limits.html


**********
CodeCommit
**********

.. contents:: Table of Contents
   :depth: 2


======
Client
======



.. py:class:: CodeCommit.Client

  A low-level client representing AWS CodeCommit::

    
    import boto3
    
    client = boto3.client('codecommit')

  
  These are the available methods:
  
  *   :py:meth:`batch_get_repositories`

  
  *   :py:meth:`can_paginate`

  
  *   :py:meth:`create_branch`

  
  *   :py:meth:`create_repository`

  
  *   :py:meth:`delete_repository`

  
  *   :py:meth:`generate_presigned_url`

  
  *   :py:meth:`get_branch`

  
  *   :py:meth:`get_commit`

  
  *   :py:meth:`get_paginator`

  
  *   :py:meth:`get_repository`

  
  *   :py:meth:`get_repository_triggers`

  
  *   :py:meth:`get_waiter`

  
  *   :py:meth:`list_branches`

  
  *   :py:meth:`list_repositories`

  
  *   :py:meth:`put_repository_triggers`

  
  *   :py:meth:`test_repository_triggers`

  
  *   :py:meth:`update_default_branch`

  
  *   :py:meth:`update_repository_description`

  
  *   :py:meth:`update_repository_name`

  

  .. py:method:: batch_get_repositories(**kwargs)

    

    Returns information about one or more repositories.

     

    .. note::

      

      The description field for a repository accepts all HTML characters and all valid Unicode characters. Applications that do not HTML-encode the description and display it in a web page could expose users to potentially malicious code. Make sure that you HTML-encode the description field in any application that uses this API to display the repository description on a web page.

      

    

    **Request Syntax** 
    ::

      response = client.batch_get_repositories(
          repositoryNames=[
              'string',
          ]
      )
    :type repositoryNames: list
    :param repositoryNames: **[REQUIRED]** 

      The names of the repositories to get information about.

      

    
      - *(string) --* 

      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'repositories': [
                {
                    'accountId': 'string',
                    'repositoryId': 'string',
                    'repositoryName': 'string',
                    'repositoryDescription': 'string',
                    'defaultBranch': 'string',
                    'lastModifiedDate': datetime(2015, 1, 1),
                    'creationDate': datetime(2015, 1, 1),
                    'cloneUrlHttp': 'string',
                    'cloneUrlSsh': 'string',
                    'Arn': 'string'
                },
            ],
            'repositoriesNotFound': [
                'string',
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a batch get repositories operation.

        
        

        - **repositories** *(list) --* 

          A list of repositories returned by the batch get repositories operation.

          
          

          - *(dict) --* 

            Information about a repository.

            
            

            - **accountId** *(string) --* 

              The ID of the AWS account associated with the repository.

              
            

            - **repositoryId** *(string) --* 

              The ID of the repository.

              
            

            - **repositoryName** *(string) --* 

              The repository's name.

              
            

            - **repositoryDescription** *(string) --* 

              A comment or description about the repository.

              
            

            - **defaultBranch** *(string) --* 

              The repository's default branch name.

              
            

            - **lastModifiedDate** *(datetime) --* 

              The date and time the repository was last modified, in timestamp format.

              
            

            - **creationDate** *(datetime) --* 

              The date and time the repository was created, in timestamp format.

              
            

            - **cloneUrlHttp** *(string) --* 

              The URL to use for cloning the repository over HTTPS.

              
            

            - **cloneUrlSsh** *(string) --* 

              The URL to use for cloning the repository over SSH.

              
            

            - **Arn** *(string) --* 

              The Amazon Resource Name (ARN) of the repository.

              
        
      
        

        - **repositoriesNotFound** *(list) --* 

          Returns a list of repository names for which information could not be found.

          
          

          - *(string) --* 
      
    

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


  .. py:method:: create_branch(**kwargs)

    

    Creates a new branch in a repository and points the branch to a commit.

     

    .. note::

      

      Calling the create branch operation does not set a repository's default branch. To do this, call the update default branch operation.

      

    

    **Request Syntax** 
    ::

      response = client.create_branch(
          repositoryName='string',
          branchName='string',
          commitId='string'
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository in which you want to create the new branch.

      

    
    :type branchName: string
    :param branchName: **[REQUIRED]** 

      The name of the new branch to create.

      

    
    :type commitId: string
    :param commitId: **[REQUIRED]** 

      The ID of the commit to point the new branch to.

      

    
    
    :returns: None

  .. py:method:: create_repository(**kwargs)

    

    Creates a new, empty repository.

    

    **Request Syntax** 
    ::

      response = client.create_repository(
          repositoryName='string',
          repositoryDescription='string'
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the new repository to be created.

       

      .. note::

        

        The repository name must be unique across the calling AWS account. In addition, repository names are limited to 100 alphanumeric, dash, and underscore characters, and cannot include certain characters. For a full description of the limits on repository names, see `Limits`_ in the AWS CodeCommit User Guide. The suffix ".git" is prohibited.

        

      

    
    :type repositoryDescription: string
    :param repositoryDescription: 

      A comment or description about the new repository.

       

      .. note::

        

        The description field for a repository accepts all HTML characters and all valid Unicode characters. Applications that do not HTML-encode the description and display it in a web page could expose users to potentially malicious code. Make sure that you HTML-encode the description field in any application that uses this API to display the repository description on a web page.

        

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'repositoryMetadata': {
                'accountId': 'string',
                'repositoryId': 'string',
                'repositoryName': 'string',
                'repositoryDescription': 'string',
                'defaultBranch': 'string',
                'lastModifiedDate': datetime(2015, 1, 1),
                'creationDate': datetime(2015, 1, 1),
                'cloneUrlHttp': 'string',
                'cloneUrlSsh': 'string',
                'Arn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a create repository operation.

        
        

        - **repositoryMetadata** *(dict) --* 

          Information about the newly created repository.

          
          

          - **accountId** *(string) --* 

            The ID of the AWS account associated with the repository.

            
          

          - **repositoryId** *(string) --* 

            The ID of the repository.

            
          

          - **repositoryName** *(string) --* 

            The repository's name.

            
          

          - **repositoryDescription** *(string) --* 

            A comment or description about the repository.

            
          

          - **defaultBranch** *(string) --* 

            The repository's default branch name.

            
          

          - **lastModifiedDate** *(datetime) --* 

            The date and time the repository was last modified, in timestamp format.

            
          

          - **creationDate** *(datetime) --* 

            The date and time the repository was created, in timestamp format.

            
          

          - **cloneUrlHttp** *(string) --* 

            The URL to use for cloning the repository over HTTPS.

            
          

          - **cloneUrlSsh** *(string) --* 

            The URL to use for cloning the repository over SSH.

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) of the repository.

            
      
    

  .. py:method:: delete_repository(**kwargs)

    

    Deletes a repository. If a specified repository was already deleted, a null repository ID will be returned.

     

    .. warning::

      Deleting a repository also deletes all associated objects and metadata. After a repository is deleted, all future push calls to the deleted repository will fail.

    

    **Request Syntax** 
    ::

      response = client.delete_repository(
          repositoryName='string'
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository to delete.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'repositoryId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a delete repository operation.

        
        

        - **repositoryId** *(string) --* 

          The ID of the repository that was deleted.

          
    

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


  .. py:method:: get_branch(**kwargs)

    

    Returns information about a repository branch, including its name and the last commit ID.

    

    **Request Syntax** 
    ::

      response = client.get_branch(
          repositoryName='string',
          branchName='string'
      )
    :type repositoryName: string
    :param repositoryName: 

      The name of the repository that contains the branch for which you want to retrieve information.

      

    
    :type branchName: string
    :param branchName: 

      The name of the branch for which you want to retrieve information.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'branch': {
                'branchName': 'string',
                'commitId': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get branch operation.

        
        

        - **branch** *(dict) --* 

          The name of the branch.

          
          

          - **branchName** *(string) --* 

            The name of the branch.

            
          

          - **commitId** *(string) --* 

            The ID of the last commit made to the branch.

            
      
    

  .. py:method:: get_commit(**kwargs)

    

    Returns information about a commit, including commit message and committer information.

    

    **Request Syntax** 
    ::

      response = client.get_commit(
          repositoryName='string',
          commitId='string'
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository to which the commit was made.

      

    
    :type commitId: string
    :param commitId: **[REQUIRED]** 

      The commit ID.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'commit': {
                'treeId': 'string',
                'parents': [
                    'string',
                ],
                'message': 'string',
                'author': {
                    'name': 'string',
                    'email': 'string',
                    'date': 'string'
                },
                'committer': {
                    'name': 'string',
                    'email': 'string',
                    'date': 'string'
                },
                'additionalData': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get commit operation.

        
        

        - **commit** *(dict) --* 

          Information about the specified commit.

          
          

          - **treeId** *(string) --* 

            Tree information for the specified commit.

            
          

          - **parents** *(list) --* 

            The parent list for the specified commit.

            
            

            - *(string) --* 
        
          

          - **message** *(string) --* 

            The message associated with the specified commit.

            
          

          - **author** *(dict) --* 

            Information about the author of the specified commit.

            
            

            - **name** *(string) --* 

              The name of the user who made the specified commit.

              
            

            - **email** *(string) --* 

              The email address associated with the user who made the commit, if any.

              
            

            - **date** *(string) --* 

              The date when the specified commit was pushed to the repository.

              
        
          

          - **committer** *(dict) --* 

            Information about the person who committed the specified commit, also known as the committer. For more information about the difference between an author and a committer in Git, see `Viewing the Commit History`_ in Pro Git by Scott Chacon and Ben Straub.

            
            

            - **name** *(string) --* 

              The name of the user who made the specified commit.

              
            

            - **email** *(string) --* 

              The email address associated with the user who made the commit, if any.

              
            

            - **date** *(string) --* 

              The date when the specified commit was pushed to the repository.

              
        
          

          - **additionalData** *(string) --* 

            Any additional data associated with the specified commit.

            
      
    

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


  .. py:method:: get_repository(**kwargs)

    

    Returns information about a repository.

     

    .. note::

      

      The description field for a repository accepts all HTML characters and all valid Unicode characters. Applications that do not HTML-encode the description and display it in a web page could expose users to potentially malicious code. Make sure that you HTML-encode the description field in any application that uses this API to display the repository description on a web page.

      

    

    **Request Syntax** 
    ::

      response = client.get_repository(
          repositoryName='string'
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository to get information about.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'repositoryMetadata': {
                'accountId': 'string',
                'repositoryId': 'string',
                'repositoryName': 'string',
                'repositoryDescription': 'string',
                'defaultBranch': 'string',
                'lastModifiedDate': datetime(2015, 1, 1),
                'creationDate': datetime(2015, 1, 1),
                'cloneUrlHttp': 'string',
                'cloneUrlSsh': 'string',
                'Arn': 'string'
            }
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get repository operation.

        
        

        - **repositoryMetadata** *(dict) --* 

          Information about the repository.

          
          

          - **accountId** *(string) --* 

            The ID of the AWS account associated with the repository.

            
          

          - **repositoryId** *(string) --* 

            The ID of the repository.

            
          

          - **repositoryName** *(string) --* 

            The repository's name.

            
          

          - **repositoryDescription** *(string) --* 

            A comment or description about the repository.

            
          

          - **defaultBranch** *(string) --* 

            The repository's default branch name.

            
          

          - **lastModifiedDate** *(datetime) --* 

            The date and time the repository was last modified, in timestamp format.

            
          

          - **creationDate** *(datetime) --* 

            The date and time the repository was created, in timestamp format.

            
          

          - **cloneUrlHttp** *(string) --* 

            The URL to use for cloning the repository over HTTPS.

            
          

          - **cloneUrlSsh** *(string) --* 

            The URL to use for cloning the repository over SSH.

            
          

          - **Arn** *(string) --* 

            The Amazon Resource Name (ARN) of the repository.

            
      
    

  .. py:method:: get_repository_triggers(**kwargs)

    

    Gets information about triggers configured for a repository.

    

    **Request Syntax** 
    ::

      response = client.get_repository_triggers(
          repositoryName='string'
      )
    :type repositoryName: string
    :param repositoryName: 

      The name of the repository for which the trigger is configured.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'configurationId': 'string',
            'triggers': [
                {
                    'name': 'string',
                    'destinationArn': 'string',
                    'customData': 'string',
                    'branches': [
                        'string',
                    ],
                    'events': [
                        'all'|'updateReference'|'createReference'|'deleteReference',
                    ]
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a get repository triggers operation.

        
        

        - **configurationId** *(string) --* 

          The system-generated unique ID for the trigger.

          
        

        - **triggers** *(list) --* 

          The JSON block of configuration information for each trigger.

          
          

          - *(dict) --* 

            Information about a trigger for a repository.

            
            

            - **name** *(string) --* 

              The name of the trigger.

              
            

            - **destinationArn** *(string) --* 

              The ARN of the resource that is the target for a trigger. For example, the ARN of a topic in Amazon Simple Notification Service (SNS).

              
            

            - **customData** *(string) --* 

              Any custom data associated with the trigger that will be included in the information sent to the target of the trigger.

              
            

            - **branches** *(list) --* 

              The branches that will be included in the trigger configuration. If no branches are specified, the trigger will apply to all branches.

              
              

              - *(string) --* 
          
            

            - **events** *(list) --* 

              The repository events that will cause the trigger to run actions in another service, such as sending a notification through Amazon Simple Notification Service (SNS). If no events are specified, the trigger will run for all repository events.

              
              

              - *(string) --* 
          
        
      
    

  .. py:method:: get_waiter(waiter_name)

        


  .. py:method:: list_branches(**kwargs)

    

    Gets information about one or more branches in a repository.

    

    **Request Syntax** 
    ::

      response = client.list_branches(
          repositoryName='string',
          nextToken='string'
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository that contains the branches.

      

    
    :type nextToken: string
    :param nextToken: 

      An enumeration token that allows the operation to batch the results. 

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'branches': [
                'string',
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list branches operation.

        
        

        - **branches** *(list) --* 

          The list of branch names.

          
          

          - *(string) --* 
      
        

        - **nextToken** *(string) --* 

          An enumeration token that returns the batch of the results. 

          
    

  .. py:method:: list_repositories(**kwargs)

    

    Gets information about one or more repositories.

    

    **Request Syntax** 
    ::

      response = client.list_repositories(
          nextToken='string',
          sortBy='repositoryName'|'lastModifiedDate',
          order='ascending'|'descending'
      )
    :type nextToken: string
    :param nextToken: 

      An enumeration token that allows the operation to batch the results of the operation. Batch sizes are 1,000 for list repository operations. When the client sends the token back to AWS CodeCommit, another page of 1,000 records is retrieved.

      

    
    :type sortBy: string
    :param sortBy: 

      The criteria used to sort the results of a list repositories operation.

      

    
    :type order: string
    :param order: 

      The order in which to sort the results of a list repositories operation.

      

    
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'repositories': [
                {
                    'repositoryName': 'string',
                    'repositoryId': 'string'
                },
            ],
            'nextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list repositories operation.

        
        

        - **repositories** *(list) --* 

          Lists the repositories called by the list repositories operation.

          
          

          - *(dict) --* 

            Information about a repository name and ID.

            
            

            - **repositoryName** *(string) --* 

              The name associated with the repository.

              
            

            - **repositoryId** *(string) --* 

              The ID associated with the repository.

              
        
      
        

        - **nextToken** *(string) --* 

          An enumeration token that allows the operation to batch the results of the operation. Batch sizes are 1,000 for list repository operations. When the client sends the token back to AWS CodeCommit, another page of 1,000 records is retrieved.

          
    

  .. py:method:: put_repository_triggers(**kwargs)

    

    Replaces all triggers for a repository. This can be used to create or delete triggers.

    

    **Request Syntax** 
    ::

      response = client.put_repository_triggers(
          repositoryName='string',
          triggers=[
              {
                  'name': 'string',
                  'destinationArn': 'string',
                  'customData': 'string',
                  'branches': [
                      'string',
                  ],
                  'events': [
                      'all'|'updateReference'|'createReference'|'deleteReference',
                  ]
              },
          ]
      )
    :type repositoryName: string
    :param repositoryName: 

      The name of the repository where you want to create or update the trigger. 

      

    
    :type triggers: list
    :param triggers: 

      The JSON block of configuration information for each trigger. 

      

    
      - *(dict) --* 

        Information about a trigger for a repository.

        

      
        - **name** *(string) --* 

          The name of the trigger.

          

        
        - **destinationArn** *(string) --* 

          The ARN of the resource that is the target for a trigger. For example, the ARN of a topic in Amazon Simple Notification Service (SNS).

          

        
        - **customData** *(string) --* 

          Any custom data associated with the trigger that will be included in the information sent to the target of the trigger.

          

        
        - **branches** *(list) --* 

          The branches that will be included in the trigger configuration. If no branches are specified, the trigger will apply to all branches.

          

        
          - *(string) --* 

          
      
        - **events** *(list) --* 

          The repository events that will cause the trigger to run actions in another service, such as sending a notification through Amazon Simple Notification Service (SNS). If no events are specified, the trigger will run for all repository events.

          

        
          - *(string) --* 

          
      
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'configurationId': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a put repository triggers operation. 

        
        

        - **configurationId** *(string) --* 

          The system-generated unique ID for the create or update operation. 

          
    

  .. py:method:: test_repository_triggers(**kwargs)

    

    Tests the functionality of repository triggers by sending information to the trigger target. If real data is available in the repository, the test will send data from the last commit. If no data is available, sample data will be generated.

    

    **Request Syntax** 
    ::

      response = client.test_repository_triggers(
          repositoryName='string',
          triggers=[
              {
                  'name': 'string',
                  'destinationArn': 'string',
                  'customData': 'string',
                  'branches': [
                      'string',
                  ],
                  'events': [
                      'all'|'updateReference'|'createReference'|'deleteReference',
                  ]
              },
          ]
      )
    :type repositoryName: string
    :param repositoryName: 

      The name of the repository in which to test the triggers.

      

    
    :type triggers: list
    :param triggers: 

      The list of triggers to test.

      

    
      - *(dict) --* 

        Information about a trigger for a repository.

        

      
        - **name** *(string) --* 

          The name of the trigger.

          

        
        - **destinationArn** *(string) --* 

          The ARN of the resource that is the target for a trigger. For example, the ARN of a topic in Amazon Simple Notification Service (SNS).

          

        
        - **customData** *(string) --* 

          Any custom data associated with the trigger that will be included in the information sent to the target of the trigger.

          

        
        - **branches** *(list) --* 

          The branches that will be included in the trigger configuration. If no branches are specified, the trigger will apply to all branches.

          

        
          - *(string) --* 

          
      
        - **events** *(list) --* 

          The repository events that will cause the trigger to run actions in another service, such as sending a notification through Amazon Simple Notification Service (SNS). If no events are specified, the trigger will run for all repository events.

          

        
          - *(string) --* 

          
      
      
  
    
    :rtype: dict
    :returns: 
      
      **Response Syntax** 

      
      ::

        {
            'successfulExecutions': [
                'string',
            ],
            'failedExecutions': [
                {
                    'trigger': 'string',
                    'failureMessage': 'string'
                },
            ]
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a test repository triggers operation.

        
        

        - **successfulExecutions** *(list) --* 

          The list of triggers that were successfully tested. This list provides the names of the triggers that were successfully tested, separated by commas.

          
          

          - *(string) --* 
      
        

        - **failedExecutions** *(list) --* 

          The list of triggers that were not able to be tested. This list provides the names of the triggers that could not be tested, separated by commas.

          
          

          - *(dict) --* 

            A trigger failed to run.

            
            

            - **trigger** *(string) --* 

              The name of the trigger that did not run.

              
            

            - **failureMessage** *(string) --* 

              Additional message information about the trigger that did not run.

              
        
      
    

  .. py:method:: update_default_branch(**kwargs)

    

    Sets or changes the default branch name for the specified repository.

     

    .. note::

      

      If you use this operation to change the default branch name to the current default branch name, a success message is returned even though the default branch did not change.

      

    

    **Request Syntax** 
    ::

      response = client.update_default_branch(
          repositoryName='string',
          defaultBranchName='string'
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository to set or change the default branch for.

      

    
    :type defaultBranchName: string
    :param defaultBranchName: **[REQUIRED]** 

      The name of the branch to set as the default.

      

    
    
    :returns: None

  .. py:method:: update_repository_description(**kwargs)

    

    Sets or changes the comment or description for a repository.

     

    .. note::

      

      The description field for a repository accepts all HTML characters and all valid Unicode characters. Applications that do not HTML-encode the description and display it in a web page could expose users to potentially malicious code. Make sure that you HTML-encode the description field in any application that uses this API to display the repository description on a web page.

      

    

    **Request Syntax** 
    ::

      response = client.update_repository_description(
          repositoryName='string',
          repositoryDescription='string'
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository to set or change the comment or description for.

      

    
    :type repositoryDescription: string
    :param repositoryDescription: 

      The new comment or description for the specified repository. Repository descriptions are limited to 1,000 characters.

      

    
    
    :returns: None

  .. py:method:: update_repository_name(**kwargs)

    

    Renames a repository. The repository name must be unique across the calling AWS account. In addition, repository names are limited to 100 alphanumeric, dash, and underscore characters, and cannot include certain characters. The suffix ".git" is prohibited. For a full description of the limits on repository names, see `Limits`_ in the AWS CodeCommit User Guide.

    

    **Request Syntax** 
    ::

      response = client.update_repository_name(
          oldName='string',
          newName='string'
      )
    :type oldName: string
    :param oldName: **[REQUIRED]** 

      The existing name of the repository.

      

    
    :type newName: string
    :param newName: **[REQUIRED]** 

      The new name for the repository.

      

    
    
    :returns: None

==========
Paginators
==========


The available paginators are:

* :py:class:`CodeCommit.Paginator.ListBranches`


* :py:class:`CodeCommit.Paginator.ListRepositories`



.. py:class:: CodeCommit.Paginator.ListBranches

  ::

    
    paginator = client.get_paginator('list_branches')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CodeCommit.Client.list_branches`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          repositoryName='string',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type repositoryName: string
    :param repositoryName: **[REQUIRED]** 

      The name of the repository that contains the branches.

      

    
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
            'branches': [
                'string',
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list branches operation.

        
        

        - **branches** *(list) --* 

          The list of branch names.

          
          

          - *(string) --* 
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    

.. py:class:: CodeCommit.Paginator.ListRepositories

  ::

    
    paginator = client.get_paginator('list_repositories')

  
  

  .. py:method:: paginate(**kwargs)

    Creates an iterator that will paginate through responses from :py:meth:`CodeCommit.Client.list_repositories`.

    **Request Syntax** 
    ::

      response_iterator = paginator.paginate(
          sortBy='repositoryName'|'lastModifiedDate',
          order='ascending'|'descending',
          PaginationConfig={
              'MaxItems': 123,
              'PageSize': 123,
              'StartingToken': 'string'
          }
      )
    :type sortBy: string
    :param sortBy: 

      The criteria used to sort the results of a list repositories operation.

      

    
    :type order: string
    :param order: 

      The order in which to sort the results of a list repositories operation.

      

    
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
            'repositories': [
                {
                    'repositoryName': 'string',
                    'repositoryId': 'string'
                },
            ],
            'NextToken': 'string'
        }
      **Response Structure** 

      

      - *(dict) --* 

        Represents the output of a list repositories operation.

        
        

        - **repositories** *(list) --* 

          Lists the repositories called by the list repositories operation.

          
          

          - *(dict) --* 

            Information about a repository name and ID.

            
            

            - **repositoryName** *(string) --* 

              The name associated with the repository.

              
            

            - **repositoryId** *(string) --* 

              The ID associated with the repository.

              
        
      
        

        - **NextToken** *(string) --* 

          A token to resume pagination.

          
    