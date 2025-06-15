
pipeline {
    agent any
    tools {
        maven "MAVEN3.9"
        jdk "JDK17"
    }

    environment {
        registryCredential = 'ecr:ap-south-1:awscreds'
        appRegistry = "575108947352.dkr.ecr.ap-south-1.amazonaws.com/gitops"
        vprofileRegistry = "https://575108947352.dkr.ecr.ap-south-1.amazonaws.com/gitops"
        cluster = "gitopscluster"
        service = "gitopssvc"
    }

    stages {

        stage('Fetch code') {
            steps {
                git branch: 'docker', url: 'https://github.com/tech-pratik/vprofile-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn install -DskipTests'
            }
            post {
                success {
                    echo 'Now Archiving it...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        stage('UNIT TEST') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Checkstyle Analysis') {
            steps {
                sh 'mvn checkstyle:checkstyle'
            }
        }

        stage('Build App Image') {
            steps {
                script {
                    dockerImage = docker.build(appRegistry + ":$BUILD_NUMBER", "./Docker-files/app/multistage/")
                }
            }
        }

        stage('Upload App Image') {
            steps {
                script {
                    docker.withRegistry(vprofileRegistry, registryCredential) {
                        dockerImage.push('latest')
                    }
                }
            }
        }

        stage('Remove Container Images') {
            steps {
                sh 'docker rmi -f $(docker images -a -q)'
            }
        }

        stage('Deploy to ECS') {
            steps {
                withAWS(credentials: 'awscreds', region: 'ap-south-1') {
                    sh 'aws ecs update-service --cluster ${cluster} --service ${service} --force-new-deployment'
                }
            }
        }
    }
}
