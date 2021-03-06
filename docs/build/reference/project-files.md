---
title: Пример файла проекта
ms.date: 08/19/2019
helpviewer_keywords:
- .vcxproj files
- C++ projects, project file format
ms.assetid: 5261cf45-3136-40a6-899e-dc1339551401
ms.openlocfilehash: eef28961ab8c4d3a34a74999c7e0c69a4fc3fced
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924010"
---
# <a name="project-files"></a>Файлы проекта

Файл проекта C++ в Visual Studio — это файл на основе XML с расширением VCXPROJ и содержащий сведения, необходимые для построения проекта C++. Обратите внимание, что файл проекта импортирует различные файлы проекта, имеющие расширение ". props" или ". targets". Эти файлы содержат дополнительные сведения о сборке и могут ссылаться на другие файлы ". props" и ". targets". Макросы в пути к файлу (например, `$(VCTargetsPath)`) зависят от текущей установки Visual Studio. Дополнительные сведения об этих макросах и файлах ". props" и ". targets" см. в разделе [Страница свойств каталогов VC + +](vcpp-directories-property-page.md), [Установка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md) и [Общие макросы для команд и свойств сборки](common-macros-for-build-commands-and-properties.md).

## <a name="example"></a>Пример

::: moniker range=">=msvc-160"

Следующий пример файла VCXPROJ был создан с помощью **мастера рабочего стола Windows** в диалоговом окне " **Создание проекта** ". Для обработки файла проекта используйте средство msbuild.exe из командной строки или команду **Сборка** в IDE. (Этот образец не может быть обработан, так как не предоставлены требуемые исходный файл и файлы заголовка.) Дополнительные сведения об элементах XML в файле проекта см. в разделе [Справочник по схеме файла проекта](/visualstudio/msbuild/msbuild-project-file-schema-reference).

::: moniker-end

::: moniker range="<=msvc-150"

Для создания приведенного ниже примера файла VCXPROJ было задано значение **Консольное приложение Win32** в диалоговом окне **Новый проект** . Для обработки файла проекта используйте средство msbuild.exe из командной строки или команду **Сборка** в IDE. (Этот образец не может быть обработан, так как не предоставлены требуемые исходный файл и файлы заголовка.) Дополнительные сведения об элементах XML в файле проекта см. в разделе [Справочник по схеме файла проекта](/visualstudio/msbuild/msbuild-project-file-schema-reference).

::: moniker-end

>[!NOTE]
> Для проектов в Visual Studio 2017 и более ранних версий измените `pch.h` на `stdafx.h` и `pch.cpp` на `stdafx.cpp` .

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup Label="ProjectConfigurations">
    <ProjectConfiguration Include="Debug|Win32">
      <Configuration>Debug</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
    <ProjectConfiguration Include="Release|Win32">
      <Configuration>Release</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
  </ItemGroup>
  <PropertyGroup Label="Globals">
    <ProjectGuid>{96F21549-A7BF-4695-A1B1-B43625B91A14}</ProjectGuid>
    <Keyword>Win32Proj</Keyword>
    <RootNamespace>SomeProjName</RootNamespace>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Default.props" />
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <CharacterSet>Unicode</CharacterSet>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <WholeProgramOptimization>true</WholeProgramOptimization>
    <CharacterSet>Unicode</CharacterSet>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ImportGroup Label="ExtensionSettings">
  </ImportGroup>
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />
  </ImportGroup>
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />
  </ImportGroup>
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <LinkIncremental>true</LinkIncremental>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <LinkIncremental>false</LinkIncremental>
  </PropertyGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <ClCompile>
      <PrecompiledHeader>Use</PrecompiledHeader>
      <WarningLevel>Level3</WarningLevel>
      <MinimalRebuild>true</MinimalRebuild>
      <DebugInformationFormat>EditAndContinue</DebugInformationFormat>
      <Optimization>Disabled</Optimization>
      <BasicRuntimeChecks>EnableFastChecks</BasicRuntimeChecks>
      <RuntimeLibrary>MultiThreadedDebugDLL</RuntimeLibrary>
      <PreprocessorDefinitions>WIN32;_DEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>
    </ClCompile>
    <Link>
      <SubSystem>Console</SubSystem>
      <GenerateDebugInformation>true</GenerateDebugInformation>
    </Link>
  </ItemDefinitionGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <ClCompile>
      <WarningLevel>Level3</WarningLevel>
      <PrecompiledHeader>Use</PrecompiledHeader>
      <DebugInformationFormat>ProgramDatabase</DebugInformationFormat>
      <Optimization>MaxSpeed</Optimization>
      <RuntimeLibrary>MultiThreadedDLL</RuntimeLibrary>
      <FunctionLevelLinking>true</FunctionLevelLinking>
      <IntrinsicFunctions>true</IntrinsicFunctions>
      <PreprocessorDefinitions>WIN32;NDEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>
    </ClCompile>
    <Link>
      <SubSystem>Console</SubSystem>
      <GenerateDebugInformation>true</GenerateDebugInformation>
      <EnableCOMDATFolding>true</EnableCOMDATFolding>
      <OptimizeReferences>true</OptimizeReferences>
    </Link>
  </ItemDefinitionGroup>
  <ItemGroup>
    <None Include="ReadMe.txt" />
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="pch.h" />
    <ClInclude Include="targetver.h" />
  </ItemGroup>
  <ItemGroup>
    <ClCompile Include="SomeProjName.cpp" />
    <ClCompile Include="pch.cpp">
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">Create</PrecompiledHeader>
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">Create</PrecompiledHeader>
    </ClCompile>
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
  <ImportGroup Label="ExtensionTargets">
  </ImportGroup>
</Project>
```

## <a name="see-also"></a>См. также

[Проекты Visual Studio — C++](../creating-and-managing-visual-cpp-projects.md)<br>
[Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md)
