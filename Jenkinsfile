pipeline {
  agent {
  label 'tomcat_slave'
}
 stages {
  stage('git checkout') {
    steps {
      git branch: 'sree', url: 'https://github.com/sreelekha2327/spark.git'
    }
  }

  stage('Build') {
    steps {
     sh 'mvn clean install'
    }
  }

  stage('Push Artifactory') {
    steps {
      sh 'sleep 15'
    }
  }

  stage('Deploy') {
    steps {
      	  sh '''sudo cp /home/ec2-user/jenkins_slave1/workspace/Tomcat_pipeline/target/*.war /opt/apache-tomcat-10.0.22/webapps'''
    }
  }

}
}
