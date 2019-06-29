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
        stage('Run script')
        {
            steps
            {
                script
                {
                    writeFile encoding: 'UTF-8',file: './variables.groovy', text: GROOVY_SCRIPT
                    load './variables.groovy'
                    
                    sh "python ./${PYTHON_SCRIPT_FILE}"
                }
            }
        }
    }
}
