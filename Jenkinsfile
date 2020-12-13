node {
  stage ('Build') {
    git url: 'https://github.com/Suryam2498/MyDevops.git'
    withMaven {
     sh 'mvn clean package'
    } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
  }
}
