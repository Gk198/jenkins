pipeline {
  agent any
    stages {
        stage('Seq1') {
            steps {
                sh 'echo Hello'
            }
        }
        stage('Par1') {
            parallel {
                stage('p1') {
                    steps {
                        sh 'sleep 10'
                    }
                }
                stage('p2') {
                    steps {
                        sh 'sleep 100'
                    }
                }
                stage('p3') {
                    steps {
                        sh 'sleep 10'
                   }
               }
           }
        }
        stage('Par2') {
            parallel {
                stage('p1') {
                   steps {
                       sh 'sleep 10'
                    }
                }
                stage('p2') {
                    steps {
                        sh 'sleep 100'
                   }
                }
                stage('p3') {
                    steps {
                        sh 'sleep 10'
                    }
                }
            }
        }
//        stage('Seq2') {
//            steps {
//                sh 'echo Hello'
//            }
//        }
//    }
//}