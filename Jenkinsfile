pipeline {
agent { node { label 'centos' } } 
stages {
stage("Checkout") {
steps {
git  branch: 'main', url: 'https://github.com/ajay253517/calculator-ci-cd.git'
}
}
stage("Compile"){
steps {
sh "./gradlew compileJava"
}
}
stage("Unit Test"){
steps {
sh "./gradlew test"
}
}
stage("Code coverage") {
               steps {
                    sh "./gradlew jacocoTestReport"
                    sh "./gradlew jacocoTestCoverageVerification"
               }
          }
stage("Static code analysis") {
               steps {
                    sh "./gradlew checkstyleMain"
               }
          }
stage("Package") {
               steps {
                    sh "./gradlew build"
               }
          }
stage("Docker build") {
               steps {
                    sh "docker build -t ajay2012/calculator:${BUILD_TIMESTAMP} ."
               }
          }

}
}