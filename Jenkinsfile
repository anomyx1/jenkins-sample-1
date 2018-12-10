// Powered by Infostretch 

timestamps {

node () {
	env.JAVA_HOME="${tool 'JDK-8'}"
	stage ('App-IC - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-login', url: 'https://github.com/anomyx1/jenkins-sample-1.git']]]) 
	}
	stage ('App-IC - Build') {
 			// Maven build step
	withMaven(maven: 'maven') { 
 			if(isUnix()) {
 				sh "mvn clean
package " 
			} else { 
 				bat "mvn clean
package " 
			} 
 		} 
	}
}
}
