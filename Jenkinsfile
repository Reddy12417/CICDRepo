node{
  stage('SCM Checkout'){
  git 'https://github.com/srinivasreddii/REST_API'
  }
  stage('SonarQube Analysis'){
    withSonarQubeEnv('Sonar'){
      bat 'mvn sonar:sonar'
    }  
  }
  stage('Compile and Package'){
  bat 'mvn clean package'
  }
  stage('Email Notification'){
  emailext body:  '''Jenkins build was successful.. :)
Thanks - Reddy''', subject: 'Jenkins Pipeline Build', to: 'sreenivasulu.g@slkgroup.com'
  }
   
}
