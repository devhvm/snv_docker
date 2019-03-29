#!/usr/bin/env groovy

node {
    stage('checkout') {
        checkout scm
    }

    gitlabCommitStatus('build') {
        docker.image('jhipster/jhipster:v5.8.2').inside('-u jhipster') {
            stage('check java') {
                sh "java -version"
            }

        }

        def dockerImage
        stage('build docker') {
        }

        stage('publish docker') {
            docker.withRegistry('http://vtools.xyz:5050', 'docker-login') {
                dockerImage.push 'latest'
            }
        }
    }
}
