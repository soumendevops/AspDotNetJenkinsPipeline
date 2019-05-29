node {
	stage 'Checkout'
		checkout scm

	stage 'Build'
		bat '"C:\\software\\nuget.exe" restore AspDotNetJenkinsPipeline.sln'
		bat '"C:\\Program Files (x86)\\MSBuild\14.0\\Bin\\MSBuild.exe" AspDotNetJenkinsPipeline.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}'

	stage 'Archive'
		archive 'ProjectName/bin/Release/**'

}