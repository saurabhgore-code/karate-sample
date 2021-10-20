podTemplate(containers: [
    containerTemplate(name: 'karate-maven', image: 'karate-docker', command: 'sleep', args: '99d')
  ]) {

    node(POD_LABEL) {
        stage('Get a Maven project') {
            git 'https://github.com/saurabhgore-code/karate-sample.git'
            container('selenium-maven') {
                stage('Build a Maven project') {
                    sh 'mvn -B -ntp clean install -Dtest=DemoTest'
                }
            }
        }
    }
}
