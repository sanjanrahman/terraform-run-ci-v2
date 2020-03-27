pipeline{
 agent{label'master'}
 stages{stage('checkout'){
  steps{
   script{
    echo"TARGET_ENVIRONMENT: ${params.TARGET_ENVIRONMENT}"
    git(branch: 'master',credentialsId: '2728c86cfafd4002ba293e2ef50181c51f0659f4',url: 'https://github.com/sanjanrahman/test-run-terraform-ci',changelog: true)}}}
    stage('build') {
     steps {
     echo "...Building. terraform"
     sh 'cd $WORKSPACE'
     dir ('test-run-terraform-ci/projects/A') {
     sh 'terraform init'
    }
     echo "done init"
    }
   }
  }
}
