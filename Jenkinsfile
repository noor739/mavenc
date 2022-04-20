pipeline
{ 
    agent any
    stages
    {
        stage('contionusDownload_loans')
        {
            steps
            {
                git 'https://github.com/noor739/mavenc.git'
            }
        }
            stage('contionusbuild_loans')
        {
            steps
            {
              sh 'mvn package'
           }
       }
    }
}
