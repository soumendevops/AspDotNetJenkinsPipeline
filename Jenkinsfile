pipeline {
  environment {
    MSBUILD = "C:\Program Files (x86)\MSBuild\14.0\Bin\MSBuild.exe"
    CONFIG = 'Release'
    PLATFORM = 'x64'
	NUGETPATH = "C:\software\nuget.exe"
  }
  stages {
    stage('Build') {
      steps {
        bat "\"${NUGETPATH}\" restore your_project.sln"
        bat "\"${MSBUILD}\" your_project.sln /p:Configuration=${env.CONFIG};Platform=${env.PLATFORM} /maxcpucount:%NUMBER_OF_PROCESSORS% /nodeReuse:false"
      }
    }
  }
}