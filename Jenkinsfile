pipeline{
 agent{label'master'}
 stages{stage('checkout'){
  steps{
   script{
    echo"TARGET_ENVIRONMENT: ${params.TARGET_ENVIRONMENT}"
//echo 'checkout the code from the develop'
    git(branch: 'master',credentialsId: '6b4562bd-e947-4f59-ab5e-4b3f96d1f519',url: 'https://github.com/sanjanrahman/test-run-terraform-ci',changelog: true)}}}}
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
