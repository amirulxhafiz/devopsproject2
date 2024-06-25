
     pipeline {
         agent any

         stages {
             stage('Build') {
                 steps {
                     script {
                         sh 'npm install'
                     }
                 }
             }
             stage('Test') {
                 steps {
                     script {
                         sh 'npm test'
                     }
                 }
             }
             stage('Build Docker Image') {
                 steps {
                     script {
                         sh 'docker build -t amirulxhafiz/devopsproject .'
                     }
                 }
             }
             stage('Deploy to Kubernetes') {
                 steps {
                     script {
                         sh 'kubectl apply -f k8s/deployment.yaml'
                         sh 'kubectl apply -f k8s/service.yaml'
                     }
                 }
             }
         }
     }
