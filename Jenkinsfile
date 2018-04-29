pipeline {
  agent any
  stages {
    stage('build app') {
      steps {
        bat 'nuget restore jenkinsbuildtests.sln'
        bat '\\"${tool \'MSBuild\'}\\" jenkinsbuildtests.sln /p:Configuration=Release /p:Platform=\\"Any CPU\\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}'
      }
    }
    stage('') {
      steps {
        archiveArtifacts 'ProjectName/bin/Release/**'
      }
    }
  }
}