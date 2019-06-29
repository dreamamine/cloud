pipeline
{
   
    agent
    {
        dockerfile
        {
            filename 'Dockerfile'
            args "-u root -v /var/run/docker.sock:/var/run/docker.sock"
        }
    }
 
    stages
    {
        
        stage('image push')
        {
            steps
            {
                sh '''
                dockerFingerprintFrom dockerfile: 'Dockerfile', image: 'php2019'
                docker build -t "php2019:Dockerfile" .
                '''
            }
        }
        
    }
}
