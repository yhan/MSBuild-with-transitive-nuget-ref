I encountered this problem in legacy .net framework.  
I will use ->, standing for "references".  

project a -> b, b -> c, c-> nuget pakcage log4net 
when I compile project a with msbuild,  
the log4net assembly is not in the output.  

What should I do to ensure the in the compile output contains 4 assemblies: a, b , c and log4net  

1. Install dotnet tool + run migration

   https://github.com/hvanbakel/CsprojToVs2017

2. Run msbuild

```powershell

# MsBuild used
PS C:\yi\repo\MsBuildNugetBuild\MsBuildNugetBuild> $env:Path -split ';'
c:\Program Files\Microsoft Visual Studio\2022\Community\MSBuild\Current\bin

# Run build
cd C:\yi\repo\MsBuildNugetBuild\MsBuildNugetBuild
msbuild .\MsBuildNugetBuild.csproj /t:Clean,Build -restore /p:Configuration=Release

```

```
dotnet new gitignore

git init
git add . 
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/yhan/MSBuild-with-transitive-nuget-ref.git
git push -u origin main

```

