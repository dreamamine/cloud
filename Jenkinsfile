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
                    docker build -t imech/php2019:1.0 .
                '''
            }
        }
        
    }
}
