podTemplate(containers: [
    containerTemplate(name: 'karate-maven', image: 'markhobson/maven-chrome:jdk-11', command: 'sleep', args: '99d')
  ]) {

    node(POD_LABEL) {
        stage('Get a Maven project') {
            git 'https://github.com/saurabhgore-code/karate-sample.git'
            container('karate-maven') {
                stage('Build a Maven project') {
                    sh 'mvn -B -ntp clean install -Dtest=DemoTest'
                }
            }
        }
    }
}
