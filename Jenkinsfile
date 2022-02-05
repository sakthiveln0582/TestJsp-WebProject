    node {    
    	def tomcatWeb = 'C:\\Tomcat-8.5.75\\webapps'
	def tomcatBin = 'C:\\Tomcat-8.5.75\\bin'
	def tomcatStatus = ''
    
    stage('SCM checkout') {
        git url: 'https://github.com/sakthiveln0582/TestJsp-WebProject.git'
    }
	stage('Compile-Package-Create-war-file') {
		def mvnHome = tool name:'Maven';type:'maven'
		bat="${mvnHome}/bin/mvn package"        
    }
	stage('Deploy to Tomcat') {
		bat="copy target\\TestJsp-WebProject.war \"${tomcatWeb}\\TestJsp-WebProject.war"        
    }
	stage('Start Tomcat Server') {
        sleep(time:5,unit:"SECONDS")
		bat="${tomcatBin}\\startup.bat" 		
		sleep(time:100,unit:"SECONDS")
    }
    
    }
