pipeline {

agent any

  environment {
    MSBUILD = "C:\\Program Files\\Microsoft Visual Studio\\2022\\Community\\MSBuild\\Current\\Bin\\MSBuild.exe"
    CONFIG = "Release"
    PLATFORM = '"Any CPU"'
	NUGETPATH = "C:\\Program Files\\MSBuild"
  }
  stages {
    stage('Build') {
      steps {
        bat "\"${NUGETPATH}\" restore AspDotNetJenkinsPipeline.sln"
        bat "\"${MSBUILD}\" AspDotNetJenkinsPipeline.sln /p:Configuration=${env.CONFIG};Platform=${env.PLATFORM} /maxcpucount:%NUMBER_OF_PROCESSORS% /nodeReuse:false /p:OutputPath=C:\\test"
      }
    }
  }
}
