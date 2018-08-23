---
title: 'Пошаговое руководство: Использование MSBuild для создания проекта Visual C++ | Документация Майкрософт'
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.walkthrough.createproject
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8bb957f0ab1dd2ea7d05151257aee0e15561e8a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609703"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>Пошаговое руководство. Использование MSBuild для создания проекта Visual C++

В этом пошаговом руководстве показано, как использовать MSBuild для сборки проекта Visual C++ в командной строке. Вы узнаете, как для создания исходных файлов C++ и XML файла проекта для консольного приложения Visual C++. После создания проекта, вы узнаете, как настроить процесс сборки.

В данном пошаговом руководстве рассмотрены следующие задачи:

- Создание исходных файлов C++ для проекта.

- Создание файла проекта XML MSBuild.

- Использование MSBuild для сборки проекта.

- Использование MSBuild для настройки проекта.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения данного пошагового руководства необходимо следующее:

- Копия Visual Studio с **разработка классических приложений C++** установленной рабочей нагрузкой.

- Общее представление о системе MSBuild.

> [!NOTE]
> Не используйте этот подход, если вы собираетесь изменить файл проекта позже с помощью Visual Studio IDE. При создании VCXPROJ-файл вручную, Visual Studio IDE может оказаться возможность редактировать или загрузить его, особенно в том случае, если в проекте используются подстановочные знаки в элементах проекта.

> [!NOTE]
> Большая часть инструкций низкого уровня построения содержатся в **.targets** и **.props** файлы, которые определены в каталоге VCTargets, хранящегося в свойстве `$(VCTargetsPath)`. Путь по умолчанию для этих файлов в Visual Studio 2017 Enterprise Edition — C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Enterprise\\Common7\\IDE\\ VC\\VCTargets\\.

## <a name="creating-the-c-source-files"></a>Создание исходных файлов C++

В этом пошаговом руководстве вы создадите проект, имеющий исходный файл и файл заголовка. Исходный файл main.cpp содержит главную функцию для консольного приложения. Файл заголовка main.h содержит код, чтобы включить файл заголовка iostream. Эти файлы C++ можно создать с помощью Visual Studio или текстовый редактор, например Visual Studio Code.

### <a name="to-create-the-c-source-files-for-your-project"></a>Создание исходных файлов C++ для проекта

1. Создайте каталог для проекта.

2. Создайте файл с именем main.cpp и добавьте в этот файл следующий код:

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

3. Создайте файл с именем main.h и добавьте в этот файл следующий код:

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>Создание XML-файле проекта MSBuild

Файл проекта MSBuild — это XML-файл, содержащий корневой элемент проекта (\<проекта >). В следующем примере проекта \<проекта > элемент содержит семь дочерние элементы:

- Три тега группы элементов (\<ItemGroup >), укажите конфигурацию проекта и платформу, имя исходного файла и имя файла заголовка.

- Три тега импорта (\<импортировать >), укажите параметры размещения Microsoft Visual C++.

- Тег группы свойств (\<PropertyGroup >), указывающий параметры проекта.

### <a name="to-create-the-msbuild-project-file"></a>Создание файла проекта MSBuild

1. Используйте текстовый редактор для создания файла проекта, который называется `myproject.vcxproj`, а затем добавьте следующий корневой \<проекта > элемента. Вставить элементы, описанные ниже процедуры между корнем \<проекта > теги:

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

2. Добавьте следующие два \<ProjectConfiguration > дочерних элементов в \<ItemGroup > элемента. Этот дочерний элемент задает отладки и выпуска конфигураций для 32-разрядной операционной системы Windows:

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

3. Добавьте следующий \<Import / > элемент, задающий путь к параметрам C++ по умолчанию для этого проекта:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

4. Добавьте следующий элемент группы свойств (\<PropertyGroup >), задающий два свойства проекта:

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v141</PlatformToolset>
    </PropertyGroup>
    ```

5. Добавьте следующий \<Import / > элемент, задающий путь к текущим параметрам C++ для этого проекта:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

6. Добавьте следующий \<ClCompile > дочерний элемент в \<ItemGroup > элемента. Этот дочерний элемент задает имя исходного файла C/C++ для компиляции:

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > \<ClCompile > является *разрабатывать* и определен в **VCTargets** каталога.

7. Добавьте следующий \<ClInclude > дочерний элемент в \<ItemGroup > элемента. Этот дочерний элемент задает имя файла заголовка для исходного файла C/C++:

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

8. Добавьте следующий \<импорта > элемент, задающий путь к файлу, который определяет целевой объект для этого проекта:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>Полный файл проекта

Ниже приведен полный файл проекта, созданный в предыдущей процедуре.

```xml
<Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
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
    <PlatformToolset>v141</PlatformToolset>
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

## <a name="using-msbuild-to-build-your-project"></a>Использование MSBuild для построения проекта

Введите следующую команду в командной строке для создания консольного приложения:

`msbuild myproject.vcxproj /p:configuration=debug`

MSBuild создает каталог для выходных файлов и компилирует и связывает проект для создания программы Myproject.exe. После завершения процесса построения, используйте следующую команду для запуска приложения:

`myproject`

Приложение должно вывести «Hello, из MSBuild!» в окне консоли.

## <a name="customizing-your-project"></a>Настройка проекта

MSBuild можно запустить выполнение целевых объектов построения предопределенных, применяются определяемые пользователем свойства и использования настраиваемых инструментов, событий и шаги сборки. В этом разделе рассматриваются следующие задачи:

- Использование MSBuild с целевыми объектами построения.

- Использование MSBuild со свойствами построения.

- Использование MSBuild с 64-разрядный компилятор и средства.

- Использование MSBuild с различными наборами инструментов.

- Добавление настроек MSBuild.

### <a name="using-msbuild-with-build-targets"></a>Использование MSBuild с целевыми объектами построения

Объект *разрабатывать* — это именованный набор предварительно определенных или пользовательских команд, которые могут быть выполнены во время сборки. Используется параметр командной строки (**/t**) для указания целевого объекта построения. В случае использования `myproject` пример проекта, предварительно определенных **чистой** целевой удаляет все файлы в папке debug и создает новый файл журнала.

В командной строке введите следующую команду, чтобы очистить `myproject`.

`msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>Использование MSBuild со свойствами построения

Параметр командной строки (**/p**) позволяет переопределять свойство в файле построения проекта. В `myproject` пример конфигурации сборки проекта, выпуска или отладки задается `Configuration` свойство. И операционной системы, которое должно выполняться построенное приложение определяется `Platform` свойство.

В командной строке введите следующую команду для создания отладочной сборки `myproject` приложение, предназначенное для запуска в 32-разрядной Windows.

`msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

Предполагается, что `myproject` пример проекта также задает конфигурацию для 64-разрядной Windows и другую конфигурацию для пользовательской операционной системы с именем `myplatform`.

В командной строке введите следующую команду, чтобы создать выпуск сборку, которое выполняется на 64-разрядной Windows.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

В командной строке введите следующую команду, чтобы создать построение выпуска для `myplatform`.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>Использование MSBuild с 64-разрядный компилятор и средства

Если вы установили Visual C++ для 64-разрядной Windows, по умолчанию, будет установлена 64-разрядных x64 родных и кроссплатформенных средств. Можно настроить MSBuild для использования 64-разрядный компилятор и средства для построения приложения, задав `PreferredToolArchitecture` свойство. Это свойство не влияет на свойства конфигурации или платформы проекта. По умолчанию используется 32-разрядной версии средства. Чтобы указать 64-разрядной версии компилятора и инструментов, добавьте следующий элемент группы свойств в файл проекта Myproject.vcxproj после `Microsoft.Cpp.default.props` \<Import / > элемент:

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

В командной строке введите следующую команду, чтобы использовать 64-разрядные средства для построения приложения.

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>Использование MSBuild с другого набора инструментов

Если у вас наборов инструментов и библиотек для других версий Visual C++ установлен, MSBuild могут создавать приложения для любой текущей версии Visual C++ или для других установленных версий. Например, если вы установили Visual Studio 2012, чтобы указать набор инструментов Visual C++ 11.0 для Windows XP, добавьте следующий элемент группы свойств в файл проекта Myproject.vcxproj после Microsoft.Cpp.props `<Import />` элемент:

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Чтобы перестроить проект с набором инструментов Visual C++ 11.0 Windows XP, введите одну из следующих команд:

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

`msbuild myproject.vcxproj /t:rebuild`

### <a name="adding-msbuild-customizations"></a>Добавление настроек MSBuild

MSBuild предоставляет множество способов настройки процесса сборки. Как добавить настраиваемые этапы построения, инструментов и событий в проект MSBuild в следующих темах:

- [Практическое руководство. Добавление пользовательского шага сборки в проекты MSBuild](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [Практическое руководство. Добавление пользовательских средств сборки в проекты MSBuild](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)

- [Практическое руководство. Использование событий сборки в проектах MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)
