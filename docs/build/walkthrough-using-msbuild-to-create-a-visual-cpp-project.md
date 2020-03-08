---
title: Пошаговое руководство. Использование MSBuild для создания проекта Visual C++
ms.date: 05/16/2019
helpviewer_keywords:
- 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
ms.openlocfilehash: c93867f3be3b17f703c549aa5c05f3d327934c26
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856291"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>Пошаговое руководство. Использование MSBuild для создания проекта Visual C++

В этом пошаговом руководстве показано, как создать проект Visual Studio C++ из командной строки с помощью MSBuild. Вы узнаете, как создать исходные файлы C++ и файл проекта на основе XML для консольного приложения Visual C++. После сборки проекта вы узнаете, как настроить процесс сборки.

В этом пошаговом руководстве описаны следующие задачи:

- Создание исходных файлов C++ для проекта

- Создание XML-файла проекта MSBuild

- Сборка проекта с помощью MSBuild

- Настройка проекта с помощью MSBuild

## <a name="prerequisites"></a>предварительные требования

Для выполнения данного пошагового руководства необходимо следующее:

- Копия Visual Studio с установленной рабочей нагрузкой **Разработка классических приложений на C++** .

- Общее представление о системе MSBuild.

> [!NOTE]
> Не используйте этот подход, если позднее вы намереваетесь изменять файл проекта с помощью интегрированной среды разработки Visual Studio. Если вы создадите файл VCXPROJ вручную, есть вероятность того, что среде Visual Studio не удастся загрузить или изменить его, особенно если в элементах проекта используются подстановочные знаки.

> [!NOTE]
> Большинство низкоуровневых инструкций сборки содержится в файлах **TARGETS** и **PROPS** в каталоге VCTargets, который хранится в свойстве `$(VCTargetsPath)`. Путь по умолчанию к этим файлам в Visual Studio 2019 Enterprise Edition: C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\MSBuild\Microsoft\VC\v160\Microsoft.Cpp.Common.props.

## <a name="creating-the-c-source-files"></a>Создание исходных файлов C++

В этом пошаговом руководстве будет создан проект, включающий в себя исходный файл и файл заголовка. Исходный файл main.cpp содержит функцию main для консольного приложения. Файл заголовка main.h содержит код для включения файла заголовка iostream. Эти файлы C++ можно создать в Visual Studio или текстовом редакторе, таком как Visual Studio Code.

### <a name="to-create-the-c-source-files-for-your-project"></a>Создание исходных файлов C++ для проекта

1. Создайте каталог для проекта.

1. Создайте файл с именем main.cpp и добавьте в него следующий код:

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

1. Создайте файл с именем main.h и добавьте в него следующий код:

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>Создание XML-файла проекта MSBuild

Файл проекта MSBuild — это XML-файл, содержащий корневой элемент проекта (`<Project>`). В следующем примере элемент `<Project>` содержит семь дочерних элементов:

- Три тега групп элементов (`<ItemGroup>`) определяют конфигурацию и платформу проекта, имя исходного файла и имя файла заголовка.

- Три тега импорта (`<Import>`) определяют расположение параметров Microsoft Visual C++.

- Тег группы свойств (`<PropertyGroup>`) определяет параметры проекта.

### <a name="to-create-the-msbuild-project-file"></a>Создание файла проекта MSBuild

1. В текстовом редакторе создайте файл проекта с именем `myproject.vcxproj`, а затем добавьте приведенный ниже корневой элемент `<Project>`. В следующих шагах между корневыми тегами `<Project>` будут вставлены элементы. (Используйте ToolsVersion="15.0", если применяется Visual Studio 2017, или ToolsVersion="16.0", если применяется Visual Studio 2019.)

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

1. В элемент `<ProjectConfiguration>` добавьте приведенные ниже дочерние элементы `<ItemGroup>`. Они определяют конфигурации отладки и выпуска для 32-разрядной операционной системы Windows:

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

1. Добавьте следующий элемент `<Import>`, определяющий путь к параметрам C++ по умолчанию для проекта:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

1. Добавьте приведенный ниже элемент группы свойств (`<PropertyGroup>`), определяющий два свойства проекта. (Используйте v141, если применяется Visual Studio 2017, или v142, если применяется Visual Studio 2019.)

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v142</PlatformToolset>
    </PropertyGroup>
    ```

1. Добавьте следующий элемент `<Import>`, определяющий путь к текущим параметрам C++ для проекта:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

1. Добавьте в элемент `<ClCompile>` приведенный ниже дочерний элемент `<ItemGroup>`. Он указывает имя исходного файла C/C++, подлежащего компиляции:

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > `<ClCompile>` — это *цель сборки*, которая определяется в каталоге **VCTargets**.

1. Добавьте в элемент `<ClInclude>` приведенный ниже дочерний элемент `<ItemGroup>`. Он указывает имя файла заголовка для исходного файла C/C++:

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

1. Добавьте следующий элемент `<Import>`, определяющий путь к файлу, в котором определен целевой объект проекта:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>Полный файл проекта

Ниже приведен полный код файла проекта, созданного в предыдущей процедуре. (Для Visual Studio 2017 используйте ToolsVersion="15.0".)

```xml
<Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
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
    <PlatformToolset>v142</PlatformToolset>
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

## <a name="using-msbuild-to-build-your-project"></a>Сборка проекта с помощью MSBuild

Чтобы выполнить сборку консольного приложения, в командной строке введите следующую команду:

`msbuild myproject.vcxproj /p:configuration=debug`

MSBuild создаст каталог для выходных файлов, а затем скомпилирует и скомпонует проект для создания программы Myproject.exe. По завершении процесса сборки используйте следующую команду для запуска приложения из папки отладки:

`myproject`

Приложение должно вывести сообщение "Hello, from MSBuild!" в окне консоли.

## <a name="customizing-your-project"></a>Настройка проекта

MSBuild позволяет выполнять предварительно определенные целевые объекты сборки, применять пользовательские свойства и использовать настраиваемые средства, события и этапы сборки. В этом разделе рассмотрены следующие задачи:

- Использование MSBuild с целевыми объектами сборки

- Использование MSBuild со свойствами сборки

- Использование MSBuild с 64-разрядным компилятором и средствами

- Использование MSBuild с разными наборами средств

- Добавление настроек MSBuild

### <a name="using-msbuild-with-build-targets"></a>Использование MSBuild с целевыми объектами сборки

*Целевой объект сборки* — это именованный набор предварительно определенных или пользовательских команд, которые могут выполняться во время сборки. Для указания целевого объекта сборки используйте параметр командной строки target (`/t`). В примере проекта `myproject` предварительно определенный целевой объект **clean** удаляет все файлы в папке отладки и создает новый файл журнала.

В командной строке введите приведенную ниже команду, чтобы очистить `myproject`.

`msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>Использование MSBuild со свойствами сборки

Параметр командной строки property (`/p`) позволяет переопределить свойство в файле сборки проекта. В примере проекта `myproject` конфигурация сборки выпуска или отладки указывается в свойстве `Configuration`. Операционная система, в которой должно выполняться собранное приложение, указывается в свойстве `Platform`.

В командной строке введите приведенную ниже команду, чтобы создать сборку отладки приложения `myproject`, предназначенную для выполнения в 32-разрядной версии Windows.

`msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

Допустим, что в примере проекта `myproject` также определена конфигурация для 64-разрядной версии Windows и еще одна конфигурация для пользовательской операционной системы `myplatform`.

В командной строке введите приведенную ниже команду, чтобы создать сборку выпуска, предназначенную для выполнения в 64-разрядной версии Windows.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

В командной строке введите приведенную ниже команду, чтобы создать сборку выпуска для `myplatform`.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>Использование MSBuild с 64-разрядным компилятором и средствами

Если вы установили Visual Studio в 64-разрядной версии Windows, по умолчанию были также установлены 64-разрядные собственные и кроссплатформенные средства. Чтобы настроить сборку приложения с использованием 64-разрядного компилятора и средств в MSBuild, задайте свойство `PreferredToolArchitecture`. Оно не влияет на конфигурацию проекта или свойства платформы. По умолчанию используется 32-разрядная версия средств. Чтобы указать 64-разрядную версию компилятора и средств, добавьте следующий элемент группы свойств в файл проекта myproject. vcxproj после `Microsoft.Cpp.default.props` \<элемент import/>.

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

Чтобы выполнить сборку приложения с помощью 64-разрядных средств, в командной строке введите приведенную ниже команду.

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>Использование MSBuild с другим набором средств

Если у вас установлены наборы средств и библиотеки для других версий Visual C++, MSBuild может выполнять сборку приложений как для текущей версии Visual C++, так и для других установленных версий. Например, если вы установили Visual Studio 2012, чтобы указать набор инструментов Visual C++ 11,0 для Windows XP, добавьте следующий элемент группы свойств в файл проекта myproject. vcxproj после `Microsoft.Cpp.props` \<элемент Import/>.

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Чтобы выполнить повторную сборку проекта с использованием набора средств Visual C++ 11.0 для Windows XP, введите следующие команды:

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

### <a name="adding-msbuild-customizations"></a>Добавление настроек MSBuild

MSBuild предоставляет различные способы настройки процесса сборки. В следующих статьях рассказывается о том, как можно добавить пользовательские этапы сборки, средства и события в проект MSBuild:

- [Практическое руководство. Добавление пользовательского шага сборки в проекты MSBuild](how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [Практическое руководство. Добавление пользовательских средств сборки в проекты MSBuild](how-to-add-custom-build-tools-to-msbuild-projects.md)

- [Практическое руководство. Использование событий сборки в проектах MSBuild](how-to-use-build-events-in-msbuild-projects.md)
