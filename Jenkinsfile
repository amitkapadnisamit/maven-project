
Pipeline{
		any agent{
					Stages{
									Stage('SCM Checkout'){
									steps{
											git 'My git URL'
										 }
									}
									Stage('Compile source code'){
									steps{
											withMaven(maven: 'LocalMaven')
											sh 'mvn compile'
									     }
									}
									Stage('Test Source code'){
									steps{
						                 withMaven(maven: 'LocalMaven')
											sh 'mvn test'
										 }
									}
									Stage('Create Pakage'){
									steps{
									     withMaven(maven: 'LocalMaven')
											sh 'mvn package'
									     }
									}
									Stage('Install package'){
									steps{
											withMaven(maven: 'LocalMaven')
											sh 'mvn install'
									     }
									}
						}
				}
		}
