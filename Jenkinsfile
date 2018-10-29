pipeline {
    agent {
        label 'Slave'
    }
    /*triggers {
        pollSCM('H/1 * * * *')
    }*/
    stages {
        stage('Stage1') {
            steps {
                echo 'S1'
            }
        }
        stage('Stage2') {
            steps {
                echo 'S2'
                //MSBuild‚Åƒrƒ‹ƒh
                bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\BuildTools\\MSBuild\\15.0\\Bin\\MSBuild.exe" C:\\Jenkins\\workspace\\DemoPipeline20181023\\ConsoleApp_Hellohoge\\ConsoleApp_Hellohoge.sln'
            }
        }
        stage('Stage3') {
            steps {
                echo 'S3'
            }
        }
    }
}