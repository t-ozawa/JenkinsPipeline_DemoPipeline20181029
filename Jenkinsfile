pipeline {
    agent {
        label 'Slave'
    }
    stages {
        stage('Stage1') {
            steps {
                echo 'S1'
                //Gitでビルド対象を取得
                //Gitリポジトリの指定(git pullしてる)
                git url: 'git@github.com:t-ozawa/Hellohoge.git', branch: 'master' 
            }
        }
        stage('Stage2') {
            steps {
                echo 'S2'
                //MSBuildでビルド
                bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\BuildTools\\MSBuild\\15.0\\Bin\\MSBuild.exe" C:\\Jenkins\\workspace\\DemoPipeline20181023\\ConsoleApp_Hellohoge\\ConsoleApp_Hellohoge.sln'
            }
        }
        stage('Stage3') {
            steps {
                echo 'S3'
                //成果物の保存
                //archiveArtifacts artifacts: 'C:\\Jenkins\\workspace\\DemoPipeline20181029', onlyIfSuccessful: true
            }
        }
    }
}