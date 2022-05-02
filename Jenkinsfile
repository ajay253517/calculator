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
stage("Code Coverage"){
steps {
sh "./gradlew jacocoTestReport"
publishHTML (target: [
reportDir: 'build/reports/jacoco/test/html',
reportFiles: 'index.html',
reportName: "JaCoCo Report"
])
sh "./gradlew test jacocoTestCoverageVerification"
}
}
stage("Static code analysis"){
steps {
publishHTML (target: [
allowMissing: false,
reportDir: 'build/reports/checkstyle',
reportFiles: 'main.html',
reportName: "Checkstyle Report"
])
sh "./gradlew checkstyleMain"
}
}
}
}
