pipeline {
    agent { label "project1" }

    stages {
        stage('1st stage- git clone') {
            steps {
                git branch: 'main', url: 'https://github.com/mohithpk/green-age.git'
            }
        }
        stage('2nd stage- docker build') {
            steps {
                sh 'docker build -t green-age .'
            }
        }
        stage('3rd stage- docker tag') {
            steps {
                sh 'docker tag green-age mohithp/green-age'
            }
        }
        stage('4th stage- docker run') {
            steps {
               sh 'docker run -d --name green-age -p 94:80 mohithp/green-age'
            }
        }
        stage('5th stage- docker login') {
            steps {
               sh 'docker login -u mohithp -p Tvisha123@'
            }
        }
        stage('6th stage- docker push') {
            steps {
               sh 'docker push mohithp/green-age'
            }
        }
    }
}
