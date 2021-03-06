Getting Started with App42PaaS-Grails-PostgreSQL Sample Application:
---------------------------------------------------------

This application is basically a simple User Input Form that takes input from user and saves it in database.

<b>[Download the source code from git.](https://github.com/shephertz/App42PaaS-Grails-PostgreSQL-Sample/archive/master.zip)</b>

Note: This project is build with grails 2.2.1 .


Project Configuration:
--------------------------

         1. Open DataSource.groovy (located in grails-app/conf folder).

         2. Update the details of your PostgreSql service in it.

                  environments {  
						production {  
							dataSource {  
								dbCreate = "update" // one of 'create', 'create-drop','update'  
								pooled = true  
								driverClassName = "org.postgresql.Driver"  
								username = "${username}"  
								password = "${password}"  
								url = "jdbc:postgresql://{host}:${port}/${databaseName}?autoReconnect=true"  
								dialect = "org.hibernate.dialect.PostgreSQLDialect"
								properties {  
									validationQuery="select 1"  
									testWhileIdle=true  
									timeBetweenEvictionRunsMillis=60000  
								}  
							}  
					}  
				}
				
         3. Run the following command to create war: 
				
				grails war
         
		 
Deploying Application on App42 PaaS using Binary:
---------------------------------------------------
				
		
	1. Run the app42 deploy command.
        
                  $ app42 deploy
                  $ Enter App Name: <your_app_name>
				  $ 1: Binary
				  $	2: Source
				  $ Choose Upload Type [Binary]: 1
                  $ Would you like to deploy from the current directory? [Yn]: n
                  $ Binary Deployment Path: <your_binary_path>
                  $ This process may take a while, be patient with it.
                  $ Deploying Application... OK
                  $ Please wait it may take few minutes.
                  $ Latest Status....|
                  $ App deployed successfully.
				  

Deploying Application on App42 PaaS using Source (Git):
--------------------------------------------------------

	1. Run the app42 deploy command.
	
				  $ app42 deploy
                  $ Enter App Name: <your_app_name>
				  $ 1: Binary
				  $	2: Source
				  $ Choose Upload Type [Binary]: 2
				  $ Enter Git URL?: <your_public_git_url>
				  $ Deploying Application... OK
                  $ Please wait it may take few minutes.
                  $ Latest Status....|
                  $ App deployed successfully.