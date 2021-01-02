pipeline{

tools{
 jdk 'MyJava'
 maven 'MyMaven'
}

agent none
stages{
    stage ('Checkout'){
agent any
steps{
git 'https://github.com/devops-trainer/DevOpsClassCodes.git'
}
}
stage ('Compile'){
agent any
steps{
sh 'mvn compile'
}
}
stage ('CodeReview'){
agent any
steps{
sh 'mvn pmd:pmd'
}
}
stage ('Unittest'){
agent any
steps{
sh 'mvn test'
}
}
stage ('MetricCheck'){
agent any
steps {
sh 'mvn cobertura:cobertura'
   }
}

stage ('Package'){
agent any
steps{
sh 'mvn package'
}
}
}
}
