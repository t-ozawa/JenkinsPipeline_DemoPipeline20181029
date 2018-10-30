pipeline {
    agent any
    stages {
        stage('chekout') {
            checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '54ff7eee-6633-4d52-8ad3-5f6b32434ed2', url: 'git@github.com:t-ozawa/JenkinsPipeline_DemoPipeline20181029.git']]])
        }
    }
    agent {
        label 'Slave'
    }
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