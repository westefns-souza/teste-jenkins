pipeline {
	agent any
	stages {
		stage('Source'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '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', url: 'https://github.com/westefns-souza/teste-jenkins.git']]])
			}
		}
		stage('Build') {		
				steps {
					bat "\"${tool 'MSBuild'}\" Teste.Jenkins.sln /t:restore /p:DeployOnBuild=true /p:DeployDefaultTarget=WebPublish /p:WebPublishMethod=FileSystem /p:SkipInvalidConfigurations=true /t:build /p:Configuration=Release /p:Platform=\"Any CPU\" /p:DeleteExistingFiles=True /p:publishUrl=c:\\inetpub\\wwwroot"
				}
		}
	}
}
