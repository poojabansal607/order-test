node ("master") {
   stage 'Code Checkout'
       checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'poojabansal607@gmail.com', url: 'https://github.com/poojabansal607/OrderManagement.git']]])
       def mvnHome = tool 'M3'
   		//echo 'Hello World 1'
   stage 'OrderManagementBuild'
      
	  // def pom = readMavenPom file: 'pom.xml'
	  // def version = pom.version.replace("-SNAPSHOT", ".${currentBuild.number}")
	   sh "${mvnHome}/bin/mvn clean test install"
      // sh ''/usr/share/mvn' clean install' 
	   // input 'Publish?'
	     // Email for build 
	    emailext body: '''Hi,
		Build is successful.
		Regards,
		Pooja''', compressLog: true, recipientProviders: [[$class: 'DevelopersRecipientProvider']], subject: 'Build is successful', to: 'pbansal13@sapient.com'
   		//echo 'Hello World 2'
   stage 'RunSonar'
   		echo 'Hello World 3'
   stage 'Deployment to QA'
        echo 'Hello World 4'
   stage 'Run Acceptance tests'
        echo 'Hello World 5'
   stage 'Run Jmeter Tests'
        echo 'Hello World 6'
   stage 'Nexus'
         echo 'Hello World 7'
   stage 'Deployment to UAT'
         echo 'Hello World 8'			 
} 