pipeline {
    agent {
        label 'Slave'
    }
    stages {
        stage('Stage1') {
            steps {
                echo 'S1'
                //Gitでビルド対象を取得
                //Gitリポジトリの指定
                git url:
                
                checkout changelog: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '54ff7eee-6633-4d52-8ad3-5f6b32434ed2', url: 'git@github.com:t-ozawa/JenkinsPipeline_DemoPipeline20181029.git']]]
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
            }
        }
    }
}