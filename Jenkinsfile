pipeline {
    agent {
        label 'Slave'
    }
    stages {
        stage('Stage1') {
            steps {
                echo 'S1'
                //Git�Ńr���h�Ώۂ��擾
                //Git���|�W�g���̎w��
                git url: 'git@github.com:t-ozawa/Hellohoge.git', branch: 'master' 
            }
        }
        stage('Stage2') {
            steps {
                echo 'S2'
                //MSBuild�Ńr���h
                bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\BuildTools\\MSBuild\\15.0\\Bin\\MSBuild.exe" C:\\Jenkins\\workspace\\DemoPipeline20181029\\ConsoleApp_Hellohoge\\ConsoleApp_Hellohoge.sln'
            }
        }
        stage('Stage3') {
            steps {
                echo 'S3'
                //���ʕ��̕ۑ�
                archiveArtifacts artifacts: 'C:\\Jenkins\\workspace\\DemoPipeline20181029C\\ConsoleApp_Hellohoge\\*.exe', onlyIfSuccessful: true
            }
        }
    }
}