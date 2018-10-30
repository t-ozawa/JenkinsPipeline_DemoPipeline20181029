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
                git url: 'git@github.com:t-ozawa/Hellohoge.git', branch: 'master' 
            }
        }
        stage('Stage2') {
            steps {
                echo 'S2'
                //MSBuildでビルド
                bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\BuildTools\\MSBuild\\15.0\\Bin\\MSBuild.exe" C:\\Jenkins\\workspace\\DemoPipeline20181029\\ConsoleApp_Hellohoge\\ConsoleApp_Hellohoge.sln'
            }
        }
        stage('Stage3') {
            steps {
                echo 'S3'
                //実行したジョブのworkspaceがカレントディレクトリになっているので注意(Jenkins特有のScript実行時のみ)
                //成果物の保存
                archiveArtifacts artifacts: 'ConsoleApp_Hellohoge\\x64\\Debug\\**.exe', onlyIfSuccessful: true
                //成果物ファイルの移動
                bat 'copy C:\\Jenkins\\workspace\\DemoPipeline20181029\\ConsoleApp_Hellohoge\\x64\\Debug\\ConsoleApp.exe  C:\\Jenkins\\workspace\\DemoPipeline20181029\\ConsoleApp_Hellohoge'
            }
        }
    }
}