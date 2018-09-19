node ( 'Windows' )
{
	stage 'Checkout'
		checkout scm

	stage 'Build Release'
		def msbuild = tool name: 'MSBuild', type: 'hudson.plugins.msbuild.MsBuildInstallation'
    bat "${msbuild} MvcMusicStore/MvcMusicStore.csproj /p:Configuration=Release /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
		
	stage 'Build Debug'
		bat "${msbuild} MvcMusicStore/MvcMusicStore.csproj /p:Configuration=Debug /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
	
  stage 'Archive'
		archiveArtifacts artifacts: 'MvcMusicStore/bin/**/*'
}