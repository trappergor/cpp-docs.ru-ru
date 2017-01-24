---
title: "Практическое руководство. Использование событий построения в проектах MSBuild | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.usebuildevents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild (c++), практическое руководство: использование событий построения в проектах"
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Практическое руководство. Использование событий построения в проектах MSBuild
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Событие построения — это команда, которую [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] выполняет на определенном этапе процесса построения.  Событие *перед построением* возникает перед началом построения; событие *перед компоновкой* возникает перед началом этапа компоновки; и событие *после построения* возникает после успешного окончания построения.  Событие построения возникает, только если происходит связанный с ним этап построения.  Например, событие перед компоновкой не возникает, если этап компоновки не выполняется.  
  
 Каждое из этих трех событий построения представлено в группе определения элементов элементом команды \(`<Command>`\) и элементом сообщения \(`<Message>`\). Элемент команды выполняется, а элемент сообщения отображается, когда **MSBuild** выполняет событие построения.  Эти элементы являются необязательными, и если указать один элемент несколько раз, то преимущество будет иметь последний.  
  
 Необязательный элемент *использовать* \(`<`*build\-event***UseInBuild**`>`\) можно указать, что в группе свойств, выполняется ли событие построения.  Элемент *использовать при построении* имеет значение `true` или `false`.  По умолчанию событие построения выполняется, если для соответствующего ему элемента *использовать при построении* не задано значение `false`.  
  
 В следующей таблице приведены все XML\-элементы события построения.  
  
|XML\-элемент|Описание|  
|------------------|--------------|  
|`PreBuildEvent`|Данное событие выполняется до начала построения.|  
|`PreLinkEvent`|Данное событие выполняется до начала этапа компоновки.|  
|`PostBuildEvent`|Данное событие выполняется после окончания построения.|  
  
 В следующей таблице приведены все элементы *использовать при построении*.  
  
|XML\-элемент|Описание|  
|------------------|--------------|  
|`PreBuildEventUseInBuild`|Указывает, следует ли выполнять событие *перед построением*.|  
|`PreLinkEventUseInBuild`|Указывает, следует ли выполнять событие *перед компоновкой*.|  
|`PostBuildEventUseInBuild`|Указывает, следует ли выполнять событие *после построения*.|  
  
## Пример  
 Следующий пример можно добавить в элемент Project файла myproject.vcxproj, созданного в руководстве [Пошаговое руководство. Использование MSBuild для создания проекта Visual C\+\+](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).  Событие *перед построением* создает копию main.cpp; событие *перед компоновкой* создает копию main.obj; событие *после построения* создает копию myproject.exe.  Если построение проекта выполняется с помощью конфигурации выпуска, то события построения выполняются.  Если построение проекта выполняется с помощью конфигурации отладки, то события построения не выполняются.  
  
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
  
## См. также  
 [MSBuild \(Visual C\+\+\)](../Topic/MSBuild%20\(Visual%20C++\).md)   
 [Пошаговое руководство. Использование MSBuild для создания проекта Visual C\+\+](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)