pipeline {
  agent any
  tools { 
      maven 'MVN' 
      jdk 'JAVA_JDK' 
  }
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/linaylin/maven-samples', branch: 'master')
      }
    }

    stage('test') {
      steps {
        sh 'git bisect start 198644632661c67b6c32f59e9047c11a70685e15 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5'
      }
    }

    stage('run') {
      steps {
        sh 'git bisect run mvn clean test'
        sh 'git bisect reset'
      }
    }
  }
}
