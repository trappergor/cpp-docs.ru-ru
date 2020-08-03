---
title: Практическое руководство. Использование событий сборки в проектах MSBuild
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 7c35abbcabe62da2e60fbc2393c575e7c3872cf3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224010"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Практическое руководство. Использование событий сборки в проектах MSBuild

Событие сборки — это команда, которую MSBuild выполняет на определенном этапе процесса сборки. Событие *перед сборкой* возникает перед запуском сборки; событие *перед компоновкой* возникает перед запуском этапа компоновки; и событие *после сборки* возникает после успешного завершения сборки. Событие сборки возникает только в том случае, если выполняется соответствующий этап сборки. Например, событие перед компоновкой не возникает, если этап компоновки не запускается.

Каждое из этих трех событий сборки представлено в группе определений элементов элементом команды (`<Command>`), которая выполняется, и элементом сообщения (`<Message>`), которое отображается, когда **MSBuild** выполняет событие сборки. Эти элементы являются необязательными, и, если один и тот же элемент задан несколько раз, приоритет имеет тот, который указан последним.

В группе свойств можно задать необязательный элемент *UseInBuild* (`<`*событие_сборки*`UseInBuild>`), чтобы указать, выполняется ли событие сборки. Содержимое элемента *use-in-build* имеет значение **`true`** или **`false`** . По умолчанию событие сборки выполняется, если соответствующий ему элемент *use-in-build* не имеет значение **`false`** .

В следующей таблице перечислены все XML-элементы события сборки.

|XML-элемент|Описание|
|-----------------|-----------------|
|`PreBuildEvent`|Это событие выполняется перед началом сборки.|
|`PreLinkEvent`|Это событие выполняется перед началом этапа компоновки.|
|`PostBuildEvent`|Это событие выполняется после завершения сборки.|

В следующей таблице перечислены все элементы *UseInBuild*.

|XML-элемент|Описание|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|Указывает, следует ли выполнять событие *перед сборкой*.|
|`PreLinkEventUseInBuild`|Указывает, следует ли выполнять событие *перед компоновкой*.|
|`PostBuildEventUseInBuild`|Указывает, следует ли выполнять событие *после сборки*.|

## <a name="example"></a>Пример

Следующий пример можно добавить в элемент Project файла myproject.vcxproj, созданного в [пошаговом руководстве по использованию MSBuild для создания проекта C++](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md). Событие *перед сборкой* создает копию файла main.cpp; событие *перед компоновкой* создает копию файла main.obj; событие *после сборки* создает копию файла myproject.exe. Если при сборке проекта используется конфигурация выпуска, события сборки выполняются. Если при сборке проекта используется конфигурация отладки, события сборки не выполняются.

``` xml
<ItemDefinitionGroup>
  <PreBuildEvent>
    <Command>copy $(ProjectDir)main.cpp $(ProjectDir)copyOfMain.cpp</Command>
    <Message>Making a copy of main.cpp </Message>
  </PreBuildEvent>
  <PreLinkEvent>
    <Command>copy $(ProjectDir)$(Configuration)\main.obj $(ProjectDir)$(Configuration)\copyOfMain.obj</Command>
    <Message>Making a copy of main.obj</Message>
  </PreLinkEvent>
  <PostBuildEvent>
    <Command>copy $(ProjectDir)$(Configuration)\$(TargetFileName) $(ProjectDir)$(Configuration)\copyOfMyproject.exe</Command>
    <Message>Making a copy of myproject.exe</Message>
  </PostBuildEvent>
</ItemDefinitionGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
  <PreBuildEventUseInBuild>true</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>true</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>true</PostBuildEventUseInBuild>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
  <PreBuildEventUseInBuild>false</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>false</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>false</PostBuildEventUseInBuild>
</PropertyGroup>
```

## <a name="see-also"></a>См. также

[MSBuild в командной строке — C++](msbuild-visual-cpp.md)<br/>
[Пошаговое руководство: Использование MSBuild для создания проекта C++](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)
