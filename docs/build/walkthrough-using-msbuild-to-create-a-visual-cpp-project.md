---
title: "Пошаговое руководство. Использование MSBuild для создания проекта Visual C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.walkthrough.createproject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild (c++), пошаговое руководство: создание проекта"
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Пошаговое руководство. Использование MSBuild для создания проекта Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В данном пошаговом руководстве демонстрируется порядок использования [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] для построения проекта [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] в командной строке.  Будет показано создание исходных файлов C\+\+ и XML\-файла проекта для консольного приложения [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  После построения проекта будет показан порядок настройки процесса построения.  
  
 В данном пошаговом руководстве рассмотрены следующие задачи:  
  
-   создание исходных файлов C\+\+ для проекта;  
  
-   создание XML\-файла проекта [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)];  
  
-   использование [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] для построения проекта;  
  
-   использование [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] для настройки проекта.  
  
## Обязательные компоненты  
 Для выполнения данного пошагового руководства необходимо следующее:  
  
-   [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]  
  
-   общее понимание системы [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)].  
  
## Создание исходных файлов C\+\+  
 В данном пошаговом руководстве будет создан проект, имеющий исходный файл и файл заголовка.  Исходный файл main.cpp содержит главную функцию для консольного приложения.  Файл заголовка main.h содержит код, включающий файл заголовка iostream.  Эти файлы C\+\+ можно создать с помощью [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] или текстового редактора.  
  
#### Создание исходных файлов C\+\+ для проекта  
  
1.  Создайте каталог для проекта.  
  
2.  Создайте файл с именем main.cpp и добавьте в него следующий код:  
  
    ```cpp  
    // main.cpp : the application source code.  
    #include <iostream>  
    #include "main.h"  
    int main()  
    {  
       std::cout << "Hello, from MSBuild!\n";  
       return 0;  
    }  
    ```  
  
3.  Создайте файл с именем main.h и добавьте в него следующий код:  
  
    ```hlsl  
    // main.h: the application header code.  
    /* Additional source code to include. */  
    ```  
  
## Создание XML\-файла проекта MSBuild  
 Файл проекта [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] — это XML\-файл, содержащий корневой элемент проекта \(\<Project\>\).  В следующем примере проекта элемент \<Project\>\> содержит семь дочерних элементов:  
  
-   три тега группы элементов \(\<ItemGroup\>\), указывающие конфигурацию и платформу проекта, имя исходного файла и имя файла заголовка;  
  
-   Три тега импорта \(\<Import\>\), указывающие расположение параметров [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] Microsoft;  
  
-   тег группы свойств \(\<PropertyGroup\>\), указывающий параметры проекта.  
  
#### Создание файла проекта MSBuild  
  
1.  С помощью текстового редактора создайте файл проекта с именем `myproject.vcxproj`, а затем добавьте в него следующий корневой элемент \<Project\>.  Вставьте элементы в следующих этапах процедуры между тегами корневого элемента \<Project\>\>:  
  
    ```xml  
    <Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  Добавьте в элемент \<ItemGroup\> следующие два дочерних элемента \<ProjectConfiguration\>.  Этот дочерний элемент задает конфигурации отладки и выпуска для 32\-разрядной операционной системы Windows:  
  
    ```xml  
    <ItemGroup>  
      <ProjectConfiguration Include="Debug|Win32">  
        <Configuration>Debug</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
      <ProjectConfiguration Include="Release|Win32">  
        <Configuration>Release</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
    </ItemGroup>  
  
    ```  
  
3.  Добавьте следующий элемент \<Import\/\>, задающий путь к параметрам C\+\+ по умолчанию для этого проекта:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  
    ```  
  
4.  Добавьте следующий элемент группы свойств \(\<PropertyGroup\>\), задающий два свойства проекта:  
  
    ```xml  
    <PropertyGroup>  
      <ConfigurationType>Application</ConfigurationType>  
      <PlatformToolset>v120</PlatformToolset>  
    </PropertyGroup>  
    ```  
  
5.  Добавьте следующий элемент \<Import\/\>, задающий путь к текущим параметрам C\+\+ для этого проекта:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
    ```  
  
6.  Добавьте в элемент \<ImportGroup\> следующий дочерний элемент \<ClCompile\>.  Этот дочерний элемент задает имя исходного файла C\/C\+\+ для компиляции:  
  
    ```xml  
    <ItemGroup>  
      <ClCompile Include="main.cpp" />  
    </ItemGroup>  
    ```  
  
7.  Добавьте в элемент \<ImportGroup\> следующий дочерний элемент \<ClInclude\>.  Этот дочерний элемент задает имя файла заголовка для исходного файла C\/C\+\+:  
  
    ```xml  
    <ItemGroup>  
      <ClInclude Include="main.h" />  
    </ItemGroup>  
    ```  
  
8.  Добавьте следующий элемент \<Import\>, задающий путь к файлу, в котором определен целевой объект для этого проекта:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
  
    ```  
  
### Полный файл проекта  
 В следующем коде показан полный файл проекта, созданный на предыдущем этапе.  
  
```xml  
<Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <ItemGroup>  
    <ProjectConfiguration Include="Debug|Win32">  
      <Configuration>Debug</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
    <ProjectConfiguration Include="Release|Win32">  
      <Configuration>Release</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  <PropertyGroup>  
    <ConfigurationType>Application</ConfigurationType>  
    <PlatformToolset>v120</PlatformToolset>  
  </PropertyGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
  <ItemGroup>  
    <ClCompile Include="main.cpp" />  
  </ItemGroup>  
  <ItemGroup>  
    <ClInclude Include="main.h" />  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
</Project>  
```  
  
## Использование MSBuild для построения проекта  
 Для построения консольного приложения введите в командной строке следующую команду:  
  
```  
msbuild myproject.vcxproj /p:configuration=debug  
```  
  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] создает каталог для выходных файлов, а затем компилирует и связывает проект для создания программы Myproject.exe.  После завершения процесса построения запустите приложение с помощью следующей команды:  
  
```  
myproject  
```  
  
 Приложение должно отобразить в окне консоли надпись "Hello, from MSBuild\!"  
  
## Настройка проекта  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] предоставляет возможность выполнения предварительно определенных целевых объектов построения, применения заданных пользователем свойств, а также использования настраиваемых инструментов, событий и этапов построения.  В данном разделе рассматриваются следующие задачи:  
  
-   использование [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] с целевыми объектами построения;  
  
-   использование [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] со свойствами построения;  
  
-   Использование [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] с 64\-разрядным компилятором и инструментами.  
  
-   использование [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] с различными наборами инструментов;  
  
-   добавление настроек [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)].  
  
### Использование MSBuild с целевыми объектами построения  
 *Целевой объект построения* — это именованный набор предварительно определенных или заданных пользователем команд, который могут выполняться во время построения.  Для указания целевого объекта построения используется параметр командной строки **\/t**.  В случае примера проекта `myproject` предварительно определенный целевой объект **clean** удаляет все файлы в папке отладки и создает новый файл журнала.  
  
 В командной строке введите следующую команду, чтобы очистить `myproject`:  
  
 `msbuild myproject.vcxproj /t:clean`  
  
### Использование MSBuild со свойствами построения  
 Параметр командной строки **\/p** позволяет переопределять свойство в файле построения проекта.  В примере проекта `myproject` конфигурация построения выпуска или отладки задается свойством `Configuration`.  Операционная система, в которой должно выполняться построенное приложение, задается свойством `Platform`.  
  
 Чтобы создать построение отладки приложения `myproject`, которое должно работать в 32\-разрядных версиях Windows, введите в командной строке следующую команду:  
  
 `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`  
  
 Предположим, что пример проекта `myproject` также задает конфигурацию для 64\-разрядных версий Windows и еще одну конфигурацию для пользовательской операционной системы с именем `myplatform`.  
  
 Чтобы создать построение выпуска для работы в 64\-разрядных версиях Windows, введите в командной строке следующую команду:  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`  
  
 Чтобы создать построение выпуска для `myplatform`, введите в командной строке следующую команду:  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`  
  
### Использование MSBuild с 64\-разрядным компилятором и инструментами  
 При установке [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] в 64\-разрядной ОС Windows, по умолчанию устанавливаются 64\-разрядные собственные инструменты x64 и межплатформенные инструменты.  Можно настроить [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] для использования 64 разрядного компилятора и инструментов сборки приложения, установив свойство `PreferredToolArchitecture`.  Это свойство не влияет на конфигурацию проекта или свойства платформы.  По умолчанию используются 32\-разрядные версии инструментов.  Чтобы задать 64\-разрядную версию компилятора и набора инструментов, добавьте следующий элемент группы свойств в файл проекта Myproject.vcxproj после элемента `Microsoft.Cpp.default.props` \<Import \/\>:  
  
```xml  
<PropertyGroup>  
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>  
</PropertyGroup>  
```  
  
 В командной строке введите следующую команду, чтобы использовать 64\-разрядные средства для сборки приложения.  
  
 `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### Использование MSBuild с другим набором инструментов  
 При наличии установленных наборов инструментов и библиотек для других версий [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] может выполнять сборку приложений как для текущей версии [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], так и для других установленных версий.  Например, если вы установили [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], чтобы задать набор инструментов [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 для Windows XP, добавьте следующий элемент группы свойств в файл проекта Myproject.vcxproj после элемента `<Import />` Microsoft.Cpp.props:  
  
```xml  
<PropertyGroup>  
    <PlatformToolset>v110_xp</PlatformToolset>  
</PropertyGroup>  
```  
  
 Чтобы заново построить проект с набором инструментов [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 Windows XP, введите какую\-либо из следующих команд:  
  
 `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`  
  
 `msbuild myproject.vcxproj /t:rebuild`  
  
### Добавление настроек MSBuild  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] предоставляет множество способов настройки процесса построения.  В следующих темах рассматривается порядок добавления пользовательских этапов построения, инструментов и событий в проект [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]:  
  
-   [Практическое руководство. Добавление пользовательского шага построения в проекты MSBuild](../Topic/How%20to:%20Add%20a%20Custom%20Build%20Step%20to%20MSBuild%20Projects.md)  
  
-   [Практическое руководство. Добавление пользовательских средств построения в проекты MSBuild](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)  
  
-   [Практическое руководство. Использование событий построения в проектах MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)