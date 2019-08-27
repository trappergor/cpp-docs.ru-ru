---
title: Практическое руководство. Использование событий сборки в проектах MSBuild
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 3fe205223b6cf381bbf3e2872b1a84f9d81a3cb7
ms.sourcegitcommit: 2da5c42928739ca8cd683a9002598f28d8ec5f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70060067"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Практическое руководство. Использование событий сборки в проектах MSBuild

Событие сборки — это команда, которую MSBuild выполняет на определенном этапе процесса сборки. Событие *перед сборкой* происходит перед запуском сборки; событие *перед компоновкой* происходит перед запуском шага компоновки; и событие после *сборки* происходит после успешного завершения сборки. Событие сборки происходит только в том случае, если выполняется связанный этап сборки. Например, событие перед компоновкой не происходит, если шаг ссылки не выполняется.

Каждое из трех событий сборки представлено в группе определений элементов с помощью выполняемого элемента Command (`<Command>`) и элемента Message (`<Message>`), который отображается, когда **MSBuild** выполняет событие сборки. Каждый элемент является необязательным, и если один и тот же элемент указан несколько раз, приоритет имеет последнее вхождение.

Необязательный элемент *использования в сборке* (`<`*Build-Event*`UseInBuild>`) можно указать в группе свойств, чтобы указать, выполняется ли событие сборки. Содержимое элемента *использования в сборке* имеет значение **true** или **false**. По умолчанию выполняется событие сборки, если его соответствующий элемент *use-in-Build* не имеет значение `false`.

В следующей таблице перечислены все XML-элементы события сборки.

|XML-элемент|Описание|
|-----------------|-----------------|
|`PreBuildEvent`|Это событие выполняется до начала сборки.|
|`PreLinkEvent`|Это событие выполняется перед началом шага компоновки.|
|`PostBuildEvent`|Это событие выполняется после завершения сборки.|

В следующей таблице перечислены все элементы, *используемые в сборке* .

|XML-элемент|Описание|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|Указывает, следует ли выполнять событие *перед сборкой* .|
|`PreLinkEventUseInBuild`|Указывает, следует ли выполнять событие *перед компоновкой* .|
|`PostBuildEventUseInBuild`|Указывает, следует ли выполнять событие *после сборки* .|

## <a name="example"></a>Пример

Следующий пример можно добавить в элемент проекта файла MyProject. vcxproj, созданного в [пошаговом руководстве: Использование MSBuild для создания C++ проекта.](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md) Событие *перед сборкой* создает копию файла main. cpp; событие, *выполняемое перед компоновкой* , создает копию файла main. obj; и событие *после сборки* создает копию MyProject. exe. Если проект построен с использованием конфигурации выпуска, выполняются события сборки. Если проект построен с использованием конфигурации отладки, события сборки не выполняются.

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
