---
title: 'Как: использование событий построения в проекты MSBuild | Документы Microsoft'
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
ms.openlocfilehash: 2367c85dbd4a4ef7b10d927592c0fb10a417f0e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369777"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Практическое руководство. Использование событий построения в проектах MSBuild
Событие построения — это команда, [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] выполняет на определенном этапе в процессе построения. *Перед построением* событие возникает перед началом построения; *перед компоновкой* событие возникает перед началом этапа компоновки; и *после построения* событие после построения успешно завершается. События построения происходит только в том случае, если возникает на этапе построения. Например событие перед компоновкой не возникает, если этап компоновки не выполняется.  
  
 Каждый из этих трех событий построения представляется в группе определения элементов элементом команды (`<Command>`), который выполняется и элементом сообщения (`<Message>`), отображается, когда **MSBuild** выполняет событие построения. Каждый элемент является необязательным, а если указать один элемент несколько раз, приоритет получает последнее вхождение.  
  
 Необязательный *использовать в построении* элемент (`<`* построения-событие ***UseInBuild**`>`) могут быть указаны в группу свойств, чтобы указать, выполняется ли данное событие построения. Значение содержимого *использовать в построении* — это либо `true` или `false`. По умолчанию событие построения выполняется, если его соответствующим *использовать в построении* задан равным `false`.  
  
 В следующей таблице перечислены каждый элемент XML событий построения:  
  
|XML-элемент|Описание|  
|-----------------|-----------------|  
|`PreBuildEvent`|Данное событие выполняется до начала построения.|  
|`PreLinkEvent`|Данное событие выполняется до начала этапа компоновки.|  
|`PostBuildEvent`|Данное событие выполняется после завершения построения.|  
  
 В следующей таблице перечислены все *использовать в построении* элемента:  
  
|XML-элемент|Описание|  
|-----------------|-----------------|  
|`PreBuildEventUseInBuild`|Указывает, следует ли выполнять *перед построением* событий.|  
|`PreLinkEventUseInBuild`|Указывает, следует ли выполнять *перед компоновкой* событий.|  
|`PostBuildEventUseInBuild`|Указывает, следует ли выполнять *после построения* событий.|  
  
## <a name="example"></a>Пример  
 Следующий пример можно добавить в проект элемент myproject.vcxproj файла, созданного в [Пошаговое руководство: использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md). Объект *перед построением* событий делает копию main.cpp; с помощью *перед компоновкой* событий делает копию main.obj; а также *после построения* событий создается копия myproject.exe. События построения выполняются, при построении проекта с помощью конфигурации выпуска. При построении проекта с помощью конфигурации отладки, то события построения не выполняются.  
  
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
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)   
 [Пошаговое руководство. Использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)