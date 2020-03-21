---
title: Файлы vcxproj. Filters
ms.date: 09/25/2019
description: Использование файлов фильтров в проектах Visual C++ Studio для определения пользовательских логических папок для файлов в Обозреватель решений
helpviewer_keywords:
- vcxproj.filters
- filters file [C++]
ms.openlocfilehash: bdf40708a70d841cb3d3144fa8fa73a71e9e9ef2
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078281"
---
# <a name="vcxprojfilters-files"></a>Файлы vcxproj. Filters

Файл *фильтров* (\*. vcxproj. Filters) — это XML-файл в формате MSBuild, который находится в корневой папке проекта. Он указывает, какие типы файлов следует приступать к логической папке в **Обозреватель решений**. На следующем рисунке *cpp* файлы находятся в узле **исходные файлы** . *h* -файлы находятся в узле **файлы заголовков** , а файлы *ICO* и *RC* находятся в папке **файлы ресурсов**. Это размещение управляется файлом фильтров.

![Логические папки в обозреватель решений](media/solution-explorer-filters.png)

## <a name="creating-a-custom-filters-file"></a>Создание файла настраиваемых фильтров

Visual Studio создаст этот файл автоматически. Для настольных приложений предопределенные логические папки (фильтры): **исходные файлы**, **файлы заголовков** и **файлы ресурсов**. Другие типы проектов, например UWP, могут иметь другой набор папок по умолчанию. Visual Studio автоматически назначает для каждой папки известные типы файлов. Если вы хотите создать фильтр с пользовательским именем или фильтром, который содержит пользовательские типы файлов, можно создать собственный файл фильтров в корневой папке проекта или в существующем фильтре. (**Ссылки** и **внешние зависимости** — это специальные папки, которые не участвуют в фильтрации.)

## <a name="example"></a>Пример

В следующем примере показан файл фильтров для примера выше. Он имеет плоскую иерархию; Иными словами, нет вложенных логических папок. Узел `UniqueIdentifier` является необязательным. Он позволяет интерфейсам автоматизации Visual Studio находить фильтр. `Extensions` также является необязательным. При добавлении нового файла в проект он добавляется в самый верхний фильтр с соответствующим расширением файла. Чтобы добавить файл в конкретный фильтр, щелкните правой кнопкой мыши фильтр и выберите команду **Добавить новый элемент**.

При первом запуске проекта создается `ItemGroup`, содержащая узлы `ClInclude`. При создании собственных файлов VCXPROJ убедитесь, что все элементы проекта также имеют запись в файле фильтров. Значения в `ClInclude` узле переопределяют фильтрацию по умолчанию на основе расширений файлов. При добавлении нового элемента в проект с помощью Visual Studio интегрированная среда разработки добавит запись отдельного файла в файл фильтров. Если изменить расширение файла, фильтр не будет автоматически переназначен.

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

Чтобы создать вложенные логические папки, объявите все узлы в фильтрах `ItemGroup` как показано ниже. Каждый дочерний узел должен объявлять полный логический путь к самому верхнему родительскому элементу. В следующем примере необходимо объявить пустой `ParentFilter`, так как на него ссылаются более поздние узлы.

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
