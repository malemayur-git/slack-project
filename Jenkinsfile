pipeline {
        agent any
parameters {
  choice choices: ['Dev', 'QA', 'UAT'], name: 'ENV'
}
        stages {
            stage('Checkout') {
                steps {
                        checkout scm
                      }}
                stage('Build') {
                   steps {
                          sh '/home/mayur/Documents/DevOps-Software/apache-maven-3.9.6/bin/mvn install'
                         }}

                stage('Deployment'){
                   steps {
                sh 'cp target/slack-project.war /home/mayur/Documents/DevOps-Software/apache-tomcat-9.0.88/webapps'
                        }}
stage('slack') { 
steps { 
slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'ramtek', color: 'good', message: 'Slag integration has been done ', teamDomain: 'Student', tokenCredentialId: '6e717163-ac06-48df-af6b-4e5e7f5e6087', username: 'mayurmale'
}}
}}
