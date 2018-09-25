
node ( 'Windows' )
{
	stage 'Checkout'
		checkout scm

	stage 'Build Release'
		bat "\"${tool 'MSBuild'}\" MvcMusicStore/MvcMusicStore.csproj /p:Configuration=Release /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
		
	stage 'Build Debug'
		bat "\"${tool 'MSBuild'}\" MvcMusicStore/MvcMusicStore.csproj /p:Configuration=Debug /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"

	stage 'Archive'
		archiveArtifacts artifacts: 'MvcMusicStore/bin/**/*'
}