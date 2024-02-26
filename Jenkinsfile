pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                sh "rm -rf node_modules" // Không sử dụng sudo ở đây
                sh "npm install" // Không sử dụng sudo ở đây
                sh "npm run build" // Tương tự, không cần sudo
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/react-app" // Xóa thư mục đích nếu tồn tại
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/react-app/"
            }
        }
    }
}