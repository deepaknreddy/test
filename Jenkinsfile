#! groovy
pipeline
{
    agent any
    stages
    {
        stage("DEVELOPMENT")
        {
            when
            {
                expression{ env.BRANCH_NAME == 'development'}
            }
            steps
            {
                script
                {
                   sh 'ssh -o StrictHostKeyChecking=no deepu@3.111.198.170 " /home/deepu/deployment.sh"'
                }
            }
        }
        stage ("MASTER")
        {
            when
            {
                expression{env.BRANCH_NAME=='master'}
            }
            steps
            {
                script
                {
                   sh 'ssh -o StrictHostKeyChecking=no deepu@3.6.88.34 "/home/deepu/deployment.sh"'
                }
            }
        }
        stage( "QA")
        {
          when
         {
         expression{ env.BRANCH_NAME == 'qa' }
         }
            steps
            {
                script
                {
                   sh 'ssh -o StrictHostKeyChecking=no deepu@52.66.197.158 "sh /home/deepu/deployment.sh"'
                }
            }
        }
    }
}
