pipeline{
agent any
{
tools{
maven 'Maven'
}
stages{
stage('Checkout')
{
steps
{
git branch:'master', url:"https://www.github.com/shwetakumari3104/Ansible1.git";
}}
stage('Build')
{
steps{
sh 'mvn clean package'
}}
stage('Archive')
{
steps
{
archiveArtifacts artifacts="target/*.war", fingerprint=true;
}}
stage('Run')
{
steps
{
sh 'mvn clean package'
sh 'ansible-playbook ansible/playbook.yml -i hosts.ini'
}}}}

