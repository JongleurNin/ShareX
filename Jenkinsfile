node {
	stage 'Checkout'
		checkout scm

	stage 'Build'
		bat 'nuget restore ShareX.sln'
		bat "\"${tool 'MSBuild'}\" ShareX.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"

	stage 'Archive'
		archive 'ShareX/bin/Release/**'

}
