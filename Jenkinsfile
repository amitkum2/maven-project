pipeline
{
agent any
stages
{
stage('SCM Checkout')
{
steps
{
	git branch: 'master', url: 'https://github.com/amitkum2/maven-project'
}
}
	stage('Build the artifacts')
{
steps
{
withMaven(jdk:'java_local', maven:'local_maven')
	{
		sh 'mvn clean package'
	}
}
}
		stage('Archive the artifacts')
{
steps
{
archiveArtifacts '**/*.war'
}
}
}
}
