node {
   def mvnHome
   stage('Preparation') { // for display purposes
    checkout scm: [$class: 'MercurialSCM', source: 'https://vcontext.net/hg/nmfs/status-of-fisheries', clean: true, credentialsId: 'jubalmercurial'], poll: false
   }
   stages {
   	stage('Clean') {
		if (isUnix()) {
			sh "'/opt/maven/bin/mvn' -Dmaven.test.failure.ignore clean"
		}
  	 } 
   	stage('Package') {
      		// Run the maven build
      		if (isUnix()) {
         		sh "'/opt/maven/bin/mvn' -Dmaven.test.failure.ignore package"
      		} 
   	}
   }
}
