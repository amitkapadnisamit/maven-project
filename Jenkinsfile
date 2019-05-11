Pipeline{
		any agent{
					Stages{
									Stage('SCM Checkout'){
									steps{
											git 'https://github.com/amitkapadnisamit/maven-project'
										 }
									}
									Stage('Compile source code'){
									steps{
											withMaven(maven: 'MavenAmit')
											sh 'mvn clean compile'
									     }
									}
									Stage('Test Source code'){
									steps{
						                 withMaven(maven: 'MavenAmit')
											sh 'mvn test'
										 }
									}
									Stage('Create Pakage'){
									steps{
									     withMaven(maven: 'MavenAmit')
											sh 'mvn package'
									     }
									}
									Stage('Install package'){
									steps{
											withMaven(maven: 'MavenAmit')
											sh 'mvn install'
									     }
									}
						}
				}
		}
