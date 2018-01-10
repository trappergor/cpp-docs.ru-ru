---
title: "Пошаговое руководство: Использование MSBuild для создания проекта Visual C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: msbuild.cpp.walkthrough.createproject
dev_langs: C++
helpviewer_keywords: 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92b954f334517adc22ca17f8324ec1a78819d9f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>Пошаговое руководство. Использование MSBuild для создания проекта Visual C++
В этом пошаговом руководстве демонстрируется использование [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] для построения проекта Visual C++ из командной строки. Вы узнаете, как для создания исходных файлов C++ и XML файла проекта для консольного приложения Visual C++. После создания проекта, вы узнаете, как настроить процесс построения.  
  
 В данном пошаговом руководстве рассмотрены следующие задачи:  
  
-   Создание исходных файлов C++ для проекта.  
  
-   Создание XML- [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] файл проекта.  
  
-   С помощью [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] для построения проекта.  
  
-   С помощью [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] для настройки проекта.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства необходимо следующее:  
  
-   [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]  
  
-   Общее представление о [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] системы.  
  
## <a name="creating-the-c-source-files"></a>Создание исходных файлов C++  
 В этом пошаговом руководстве вы создадите проект, имеющий исходный файл и файл заголовка. Исходный файл main.cpp содержит функцию main консольного приложения. Файл заголовка main.h содержит код, чтобы включить файл заголовка iostream. Эти файлы C++ можно создать с помощью [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] или текстовом редакторе.  
  
#### <a name="to-create-the-c-source-files-for-your-project"></a>Для создания исходных файлов для проекта C++  
  
1.  Создайте каталог для проекта.  
  
2.  Создайте файл с именем main.cpp и добавьте в этот файл следующий код:  
  
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
  
3.  Создайте файл с именем main.h и добавьте в этот файл следующий код:  
  
    ```hlsl  
    // main.h: the application header code.  
    /* Additional source code to include. */  
    ```  
  
## <a name="creating-the-xml-msbuild-project-file"></a>Создание XML-файла проекта MSBuild  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] Файл проекта доступен в XML-файл, содержащий корневой элемент проекта (\<проекта >). В следующем примере проекта \<проекта > элемент содержит семь дочерних элементов:  
  
-   Три тега группы элементов (\<ItemGroup >), укажите конфигурации проекта и платформы, имя исходного файла и имя файла заголовка.  
  
-   Три Импорт тегов (\<импорта >), указать параметры размещения Microsoft Visual C++.  
  
-   Тег группы свойств (\<PropertyGroup >), указывающий параметры проекта.  
  
#### <a name="to-create-the-msbuild-project-file"></a>Для создания файла проекта MSBuild  
  
1.  Используйте текстовый редактор для создания файла проекта, который называется `myproject.vcxproj`, а затем добавьте следующий корневой \<проекта > элемент. Вставить элементы в следующих этапах процедуры между корневой \<проекта > тегов:  
  
    ```xml  
    <Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  Добавьте следующие два \<ProjectConfiguration > дочерние элементы в \<ItemGroup > элемент. Этот дочерний элемент задает отладка и выпуск конфигураций для 32-разрядной операционной системе Windows:  
  
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
  
3.  Добавьте следующие \<импорта / > элемент, задающий путь к параметрам C++ по умолчанию для этого проекта:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  
    ```  
  
4.  Добавьте следующий элемент группы свойств (\<PropertyGroup >), задающий два свойства проекта:  
  
    ```xml  
    <PropertyGroup>  
      <ConfigurationType>Application</ConfigurationType>  
      <PlatformToolset>v120</PlatformToolset>  
    </PropertyGroup>  
    ```  
  
5.  Добавьте следующие \<импорта / > элемента, которое указывает путь к текущим параметрам C++ для этого проекта:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
    ```  
  
6.  Добавьте следующие \<ClCompile > дочерний элемент в \<ItemGroup > элемент. Этот дочерний элемент задает имя исходного файла C/C++ для компиляции:  
  
    ```xml  
    <ItemGroup>  
      <ClCompile Include="main.cpp" />  
    </ItemGroup>  
    ```  
  
7.  Добавьте следующие \<ClInclude > дочерний элемент в \<ItemGroup > элемент. Этот дочерний элемент задает имя файла заголовка для исходного файла C/C++:  
  
    ```xml  
    <ItemGroup>  
      <ClInclude Include="main.h" />  
    </ItemGroup>  
    ```  
  
8.  Добавьте следующие \<импорта > элемент, который задает путь к файлу, который определяет целевой объект для этого проекта:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
  
    ```  
  
### <a name="complete-project-file"></a>Полный файл проекта  
 Ниже приведен полный файл проекта, созданный в предыдущей процедуре.  
  
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
  
## <a name="using-msbuild-to-build-your-project"></a>Использование MSBuild для сборки проекта  
 Введите следующую команду в командной строке для создания консольного приложения:  
  
```  
msbuild myproject.vcxproj /p:configuration=debug  
```  
  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]создает каталог для выходных файлов и компилирует и связывает проект для создания программы Myproject.exe. После завершения процесса сборки, используйте следующую команду для запуска приложения:  
  
```  
myproject  
```  
  
 Приложение должно вывести «Hello, из MSBuild!» в окне консоли.  
  
## <a name="customizing-your-project"></a>Настройка проекта  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]позволяет выполнения целевых объектов построения стандартных, применяются пользовательские свойства и использования настраиваемых инструментов, событий и этапов построения. В этом разделе рассмотрены следующие задачи:  
  
-   С помощью [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] с целевыми объектами построения.  
  
-   С помощью [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] со свойствами построения.  
  
-   С помощью [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 64-разрядный компилятор и средства.  
  
-   С помощью [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] с различными наборами инструментов.  
  
-   Добавление [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] настроек.  
  
### <a name="using-msbuild-with-build-targets"></a>Использование MSBuild с целевыми объектами построения  
 Объект *собран* — это именованный набор предварительно определенных или пользовательских команд, которые могут быть выполнены во время сборки. Используется параметр командной строки (**/t**) для указания цели построения. В случае использования `myproject` пример проекта, предопределенные **чистой** целевой удаляет все файлы в папке debug и создает новый файл журнала.  
  
 В командной строке введите следующую команду для очистки `myproject`.  
  
 `msbuild myproject.vcxproj /t:clean`  
  
### <a name="using-msbuild-with-build-properties"></a>Использование MSBuild со свойствами построения  
 Параметр командной строки (**/p**) позволяет переопределять свойство в файле построения проекта. В `myproject` пример конфигурации построения проектов, выпуска или отладки задается `Configuration` свойство. И операционной системы, предназначенный для выполнения сборки приложения определяется `Platform` свойство.  
  
 В командной строке введите следующую команду для создания отладочной сборки `myproject` приложение, которое должно выполняться в 32-разрядной Windows.  
  
 `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`  
  
 Предполагается, что `myproject` пример проекта также задает конфигурацию для 64-разрядной версии Windows и другую конфигурацию для пользовательской операционной системы с именем `myplatform`.  
  
 В командной строке следующую команду, чтобы создать выпуск сборки, типа выполняется на 64-разрядной версии Windows.  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`  
  
 В командной строке введите следующую команду, чтобы создать построение выпуска для `myplatform`.  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`  
  
### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>Использование MSBuild с 64-разрядный компилятор и средства  
 Если вы установили Visual C++ для 64-разрядной версии Windows, по умолчанию, 64-разрядных x64 машинная компиляция и кросс средства будут установлены. Можно настроить [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] использовать 64-разрядный компилятор и средства для построения приложения, задав `PreferredToolArchitecture` свойство. Это свойство не влияет на свойства конфигурации или платформы проекта. По умолчанию используется 32-разрядной версии инструментов. Чтобы указать 64-разрядной версии компилятора и инструментов, добавьте следующий элемент группы свойств в файл проекта Myproject.vcxproj после `Microsoft.Cpp.default.props` \<импорта / > элемента:  
  
```xml  
<PropertyGroup>  
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>  
</PropertyGroup>  
```  
  
 В командной строке введите следующую команду, чтобы использовать 64-разрядные средства для построения приложения.  
  
 `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="using-msbuild-with-a-different-toolset"></a>Использование MSBuild с использованием другого набора инструментов  
 Если у вас есть наборы инструментов и библиотек для других версий Visual C++ установлен, [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] могут создавать приложения, либо для текущей версии Visual C++ или для других установленных версий. Например, если вы установили [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], чтобы указать набор инструментов Visual C++ 11.0 для Windows XP, добавьте следующий элемент группы свойств в файл проекта Myproject.vcxproj после файла Microsoft.Cpp.props `<Import />` элемента:  
  
```xml  
<PropertyGroup>  
    <PlatformToolset>v110_xp</PlatformToolset>  
</PropertyGroup>  
```  
  
 Чтобы перестроить проект с помощью набора средств Visual C++ 11.0 Windows XP, введите одну из следующих команд:  
  
 `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`  
  
 `msbuild myproject.vcxproj /t:rebuild`  
  
### <a name="adding-msbuild-customizations"></a>Добавление настроек MSBuild  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]предоставляет различные способы для настройки процесса построения. Следующие разделы показывают, как добавить пользовательские шаги построения, инструменты и события для вашего [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] проекта:  
  
-   [Практическое руководство. Добавление пользовательского шага сборки в проекты MSBuild](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)  
  
-   [Практическое руководство. Добавление пользовательских средств сборки в проекты MSBuild](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)  
  
-   [Практическое руководство. Использование событий сборки в проектах MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)