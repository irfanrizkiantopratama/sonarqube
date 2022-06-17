node
{
    stage('clonning from GIT'){
git branch: 'main', credentialsId: 'github-irfan', url: 'git@github.com:devopshint/jenkins-nexus.git'
     }

stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarQube'
      withSonarQubeEnv('SonarQube') {
      sh """/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarQube/bin/sonar-scanner \
     -D sonar.projectVersion=1.0-SNAPSHOT \
       -D sonar.login=admin \
      -D sonar.password=irfan123 \
      -D sonar.projectBaseDir=/var/lib/jenkins/workspace/jenkins-sonar/ \
        -D sonar.projectKey=my-app1 \
        -D sonar.sourceEncoding=UTF-8 \
        -D sonar.language=java \
        -D sonar.sources=my-app/src/main \
        -D sonar.tests=my-app/src/test \
        -D sonar.host.url=http://sonarqube.devoptech.my.id/"""
        }
}
}
