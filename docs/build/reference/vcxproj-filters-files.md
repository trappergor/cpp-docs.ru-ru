---
title: Файлы Vcxproj.filters
ms.date: 09/25/2019
description: Используйте файлы фильтров в проектах Visual Studio C, чтобы определить пользовательские логические папки для файлов в Solution Explorer
helpviewer_keywords:
- vcxproj.filters
- filters file [C++]
ms.openlocfilehash: 57735246b543680243994b99b8c05c9ad1211f38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335933"
---
# <a name="vcxprojfilters-files"></a>файлы vcxproj.filters

Файл *фильтров* \*(.vcxproj.filters) — это файл XML в формате MSBuild, который находится в папке корневого проекта. В нем указывается, какие типы файлов попадают в логическую папку в **Solution Explorer.** В следующей иллюстрации файлы *.cpp* находятся под узлом **Исходных файлов.** файлы *.h* находятся под узелом **файлов заголовка,** а файлы *.ico* и *.rc* находятся под **файлами ресурсов.** Это размещение контролируется файлом фильтров.

![Логические папки в Solution Explorer](media/solution-explorer-filters.png)

## <a name="creating-a-custom-filters-file"></a>Создание файла пользовательских фильтров

Visual Studio создает этот файл автоматически. Для настольных приложений предопределенные логические папки (фильтры): **Исходные файлы,** **файлы заголовка** и **файлы ресурсов.** Другие типы проектов, такие как UWP, могут иметь другой набор папок по умолчанию. Visual Studio автоматически присваивает известные типы файлов каждой папке. Если вы хотите создать фильтр с пользовательским именем или фильтром, который содержит пользовательские типы файлов, вы можете создать свой собственный файл фильтров в корневой папке проекта или под существующим фильтром. **(Ссылки** и **внешние зависимости** являются специальными папками, которые не участвуют в фильтрации.)

## <a name="example"></a>Пример

В следующем примере показан файл фильтров для отображаемого ранее примера. Он имеет плоскую иерархию; другими словами, нет вложенных логических папок. Узел `UniqueIdentifier` является необязательным. Это позволяет Visual Studio автоматизации интерфейсов, чтобы найти фильтр. `Extensions`также не является обязательным. Когда новый файл добавляется в проект, он добавляется в верхний фильтр с соответствующим расширением файла. Чтобы добавить файл в определенный фильтр, нажмите правой кнопкой мыши на фильтр и **выберите Добавить новый элемент.**

`ItemGroup` Содержащий `ClInclude` узлы создается при первом запуске проекта. Если вы создаете собственные файлы vcxproj, убедитесь, что все элементы проекта также имеют запись в файле фильтров. Значения в `ClInclude` узеле переопределяют фильтрацию по умолчанию на основе расширений файлов. При использовании Visual Studio для добавления нового элемента в проект IDE добавит отдельный файл в файл фильтров. Фильтр не переназначается автоматически при изменении расширения файла.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup>
    <Filter Include="Source Files">
      <UniqueIdentifier>{4FC737F1-C7A5-4376-A066-2A32D752A2FF}</UniqueIdentifier>
      <Extensions>cpp;c;cc;cxx;def;odl;idl;hpj;bat;asm;asmx</Extensions>
    </Filter>
    <Filter Include="Header Files">
      <UniqueIdentifier>{93995380-89BD-4b04-88EB-625FBE52EBFB}</UniqueIdentifier>
      <Extensions>h;hh;hpp;hxx;hm;inl;inc;ipp;xsd</Extensions>
    </Filter>
    <Filter Include="Resource Files">
      <UniqueIdentifier>{67DA6AB6-F800-4c08-8B7A-83BB121AAD01}</UniqueIdentifier>
      <Extensions>rc;ico;cur;bmp;dlg;rc2;rct;bin;rgs;gif;jpg;jpeg;jpe;resx;tiff;tif;png;wav;mfcribbon-ms</Extensions>
    </Filter>
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="MFCApplication1.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="MFCApplication1Dlg.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="stdafx.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="targetver.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="Resource.h">
      <Filter>Header Files</Filter>
    </ClInclude>
  </ItemGroup>
  <ItemGroup>
    <ClCompile Include="MFCApplication1.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
    <ClCompile Include="MFCApplication1Dlg.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
    <ClCompile Include="stdafx.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
  </ItemGroup>
  <ItemGroup>
    <ResourceCompile Include="MFCApplication1.rc">
      <Filter>Resource Files</Filter>
    </ResourceCompile>
  </ItemGroup>
  <ItemGroup>
    <None Include="res\MFCApplication1.rc2">
      <Filter>Resource Files</Filter>
    </None>
  </ItemGroup>
  <ItemGroup>
    <Image Include="res\MFCApplication1.ico">
      <Filter>Resource Files</Filter>
    </Image>
  </ItemGroup>
</Project>
```

Чтобы создать вложенные логические папки, `ItemGroup` объявить все узлы в фильтрах, как показано ниже. Каждый детский узла должен провозгласить полный логический путь к самому верхнему родителю. В следующем примере `ParentFilter` пустой должен быть объявлен, поскольку на него ссылаются в более поздних узлах.

```xml
  <ItemGroup>
    <Filter Include="ParentFilter">
    </Filter>
    <Filter Include="ParentFilter\Source Files"> <!-- Full path to topmost parent.-->  
      <UniqueIdentifier>{4FC737F1-C7A5-4376-A066-2A32D752A2FF}</UniqueIdentifier> <!--  Optional-->
      <Extensions>cpp;c;cc;cxx;def;odl;idl;hpj;bat;asm;asmx</Extensions> <!-- Optional -->
    </Filter>
    <Filter Include="Header Files">
      <UniqueIdentifier>{93995380-89BD-4b04-88EB-625FBE52EBFB}</UniqueIdentifier>
      <Extensions>h;hh;hpp;hxx;hm;inl;inc;ipp;xsd</Extensions>
    </Filter>
  </ItemGroup>
```
