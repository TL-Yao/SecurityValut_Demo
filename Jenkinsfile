pipeline {
    agent {
     docker {
       image 'scantist/backend-jenkins:latest'
       args '-u root:root -v /var/run/docker.sock:/var/run/docker.sock'
     }
   }

    stages {
        stage('Set up environment') {
                steps {
                    script {
                        echo 'Setting up environment...'
                        // 例如，安装所需的 Python 包
                        sh 'pip install -r requirements.txt'
                    }
                }
        }
        stage('Build') {  // 定义一个名为 'Build' 的阶段
            steps {
                echo 'Building...'  // 这个阶段执行的步骤
                // 这里可以添加构建步骤，例如编译代码
            }
        }
        stage('Test') {  // 定义一个名为 'Test' 的阶段
            steps {
                echo 'Testing...'  // 这个阶段执行的步骤
                // 这里可以添加测试步骤，例如运行单元测试
            }
        }
        stage('Deploy') {  // 定义一个名为 'Deploy' 的阶段
            steps {
                echo 'Deploying...'  // 这个阶段执行的步骤
                // 这里可以添加部署步骤，例如部署到服务器
            }
        }
    }

    post {  // 定义在 pipeline 执行完成后的操作
        always {
            echo 'This will always run'  // 总是执行的步骤
        }
        success {
            echo 'This will run only if successful'  // 仅在成功时执行的步骤
        }
        failure {
            echo 'This will run only if failed'  // 仅在失败时执行的步骤
        }
    }
}