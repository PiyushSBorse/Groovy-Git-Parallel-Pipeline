pipeline
{
    agent none
    stages
    {

        stage('Non-Parallel Stage')
        {
            agent
            {
                label "Windows_Master"
            }
            steps
            {
                echo 'This will execute first'
            }
        }

        stage('Run Tests')
        {
            parallel
            {
                stage('Test On Windows')
                {
                    agent
                    {
                        label "Windows_Node"
                    }
                    steps
                    {
                        echo 'Task on agent Windows_Node'
                    }
                }
                stage('Test On Windows_Master')
                {
                    agent
                    {
                        label "Windows_Master"
                    }
                    steps
                    {
                        echo 'Task on agent Windows_Master Node'
                    }
                }
            }
        }
    }
}