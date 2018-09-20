---
title: 'Практическое: использование событий построения в проекты MSBuild | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.usebuildevents
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d875836cbfe9506d41a979a63d941d1ee5b467a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444337"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Практическое руководство. Использование событий построения в проектах MSBuild

Событие построения — команда, выполняющая MSBuild на определенном этапе процесса построения. *Перед сборкой* событие возникает перед началом сборки; *перед компоновкой* событие возникает перед началом этапа компоновки; и *после построения* событие после построения успешно завершается. События сборки происходит только в том случае, если происходит на этапе построения. Например событие перед компоновкой не возникает, если на шаге ссылки не выполняется.

Каждый из этих трех событий построения представлен в группу определений элемента элементом команды (`<Command>`), выполняется и элемент сообщения (`<Message>`) то есть отображается, когда **MSBuild** выполняет события построения. Каждый элемент является необязательным, и если указать тот же элемент несколько раз, последнего вхождения имеет более высокий приоритет.

Необязательный *использовать в построении* элемент (`<`*события построения*`UseInBuild>`) можно указать в группу свойств, чтобы указать, выполняется ли события построения. Значение содержимого *использовать в построении* — это либо `true` или `false`. По умолчанию событие построения выполняется, если соответствующим *использовать в построении* элементу присваивается `false`.

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

Следующий пример можно добавить в элемент проекта myproject.vcxproj файла, созданного в [Пошаговое руководство: использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md). Объект *перед сборкой* событий делает копию main.cpp; *перед компоновкой* событий делает копию main.obj; а также *после построения* событий создается копия myproject.exe. Если проект создается с помощью конфигурации release, выполняются события построения. Если проект создается с помощью конфигурации отладки, события сборки, не выполняются.

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

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
[Пошаговое руководство. Использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)