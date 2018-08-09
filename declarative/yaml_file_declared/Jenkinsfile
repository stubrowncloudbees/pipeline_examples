pipeline {
    agent {
        kubernetes {
            label 'my-pod-template'
            defaultContainer 'jnlp'
            yamlFile 'declarative/yaml_file_declared/KubernetesPod.yaml'
        }
    }
    stages {
        stage('Run maven') {
            steps {
                container('maven') {
                    sh 'mvn -version'
                }
                container('busybox') {
                   script{
                       try {
                           sh 'exit 1'
                       }
                       catch (exc){
                           echo 'somthing failed'

                       }
                   }
                }
            }
        }
    }
}
