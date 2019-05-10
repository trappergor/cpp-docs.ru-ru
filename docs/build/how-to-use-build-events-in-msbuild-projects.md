---
title: Практическое руководство. Использование событий построения в проектах MSBuild
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 8f4ccea66f7346512df88fc4c6078752c624aaa9
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221469"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Практическое руководство. Использование событий построения в проектах MSBuild

Событие построения — команда, выполняющая MSBuild на определенном этапе процесса построения. *Перед сборкой* событие возникает перед началом сборки; *перед компоновкой* событие возникает перед началом этапа компоновки; и *после построения* событие после построения успешно завершается. События сборки происходит только в том случае, если происходит на этапе построения. Например событие перед компоновкой не возникает, если на шаге ссылки не выполняется.

Каждый из этих трех событий построения представлен в группу определений элемента элементом команды (`<Command>`), выполняется и элемент сообщения (`<Message>`) то есть отображается, когда **MSBuild** выполняет события построения. Каждый элемент является необязательным, и если указать тот же элемент несколько раз, последнего вхождения имеет более высокий приоритет.

Необязательный *использовать в построении* элемент (`<`*события построения*`UseInBuild>`) можно указать в группу свойств, чтобы указать, выполняется ли события построения. Значение содержимого *использовать в построении* — это либо **true** или **false**. По умолчанию событие построения выполняется, если соответствующим *использовать в построении* элементу присваивается `false`.

В следующей таблице перечислены каждый элемент XML события сборки:

|XML-элемент|Описание|
|-----------------|-----------------|
|`PreBuildEvent`|Это событие выполняется до начала построения.|
|`PreLinkEvent`|Это событие выполняется до начала этапа компоновки.|
|`PostBuildEvent`|Данное событие выполняется после завершения построения.|

В следующей таблице перечислены все *использовать в построении* элемент:

|XML-элемент|Описание|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|Указывает, следует ли выполнять *перед сборкой* событий.|
|`PreLinkEventUseInBuild`|Указывает, следует ли выполнять *перед компоновкой* событий.|
|`PostBuildEventUseInBuild`|Указывает, следует ли выполнять *после построения* событий.|

## <a name="example"></a>Пример

Следующий пример можно добавить в элемент проекта myproject.vcxproj файла, созданного в [Пошаговое руководство: Использование MSBuild для создания C++ проекта](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md). Объект *перед сборкой* событий делает копию main.cpp; *перед компоновкой* событий делает копию main.obj; а также *после построения* событий создается копия myproject.exe. Если проект создается с помощью конфигурации release, выполняются события построения. Если проект создается с помощью конфигурации отладки, события сборки, не выполняются.

```
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

[MSBuild в командной строке - C++](msbuild-visual-cpp.md)<br/>
[Пошаговое руководство: Использование MSBuild для создания проекта C++](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)
