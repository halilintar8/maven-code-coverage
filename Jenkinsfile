// stage 'SonarCloud'
// // Split https://github.com/organization/repository/pull/123
// def urlcomponents = env.CHANGE_URL.split("/")
// def org = urlcomponents[3]
// def repo = urlcomponents[4]
// // withSonarQubeEnv('SonarCloud') {
// withSonarQubeEnv('sonarcloud8') {
//     sh "./mvnw sonar:sonar \
//     -Dsonar.pullrequest.provider=GitHub \
//     -Dsonar.pullrequest.github.repository=${org}/${repo} \
//     -Dsonar.pullrequest.key=${env.CHANGE_ID} \
//     -Dsonar.pullrequest.branch=${env.CHANGE_BRANCH}"
// }


// node {
//     // stage('Checkout') {
//     //     checkout scm
//     // }

//     stage('Clean Verify') {
//         sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar'
//     }
    
// }

pipeline {
    agent any
    tools { 
      maven 'maven' 
      jdk 'jdk' 
    }
    stages {
      stage ('Build') {
        steps {
          sh 'mvn -B -ntp -Dmaven.test.failure.ignore verify'
        }
      }

    }
}

