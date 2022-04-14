pipeline
{ 
    agent any
    stages
    {
        stage('contionusDownload')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
            stage('contionusbuild')
        {
            steps
            {
              sh 'mvn package'
            }
        }
         stage('contionusDeployment')
        {
            steps
            {
              deploy adapters: [tomcat9(credentialsId: 'a8e8f778-2e00-4674-a50c-ce3fa09b94e4', path: '', url: 'http://172.31.17.162:8080')], contextPath: 'qaapp', war: '**/*.war'
            }
        }
            stage('contionusTesting')
        {
            steps
            {
              git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
              sh 'java -jar testing.jar'
              
           }
       }
        stage('contionusDelivery')
        {
            steps
            {
              input message: 'required approvals', submitter: 'sravan'  
              deploy adapters: [tomcat9(credentialsId: '28c7e7f1-01a8-42fc-b16e-0ff35c736e32', path: '', url: 'http://172.31.91.127:8080')], contextPath: 'myapp', war: '**/*.war'
              
           }
       }
    }
}
