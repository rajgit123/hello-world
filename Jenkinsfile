echo 'hello this is initialization of pipeline from jenkins'
pipeline {
    agent any
    
    stages {
        stage('Fetch SCM') {
            steps {
                git(
                    url: 'https://github.com/rajgit123/hello-world.git', // URL of your Git repository
                    credentialsId: 'your-credentials-id', // ID of the credentials configured in Jenkins for authentication
                    branch: 'master', // Branch to fetch from
                    clean: true // Optional: clean workspace before fetching
                )
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn clean package' // Example: build the project using Maven
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test' // Example: run tests using Maven
            }
        }
        
       // stage('Deploy') {
        //    steps {
                // Example: Deploy the application to a Tomcat server
           //     sh 'cp target/*.war /path/to/tomcat/webapps'
          //      sh '/path/to/tomcat/bin/catalina.sh run'
          //  }
       // }
    }
}

