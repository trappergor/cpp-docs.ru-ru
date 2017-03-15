---
title: "/AI (указание каталогов метаданных) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.AdditionalUsingDirectories"
  - "VC.Project.VCNMakeTool.AssemblySearchPath"
  - "/AI"
  - "VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/AI - параметр компилятора [C++]"
  - "AI - параметр компилятора [C++]"
  - "-AI - параметр компилятора [C++]"
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /AI (указание каталогов метаданных)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает каталог, в котором компилятор будет производить поиск для разрешения ссылок, переданных в директиву `#using`.  
  
## Синтаксис  
  
```  
/AIdirectory  
```  
  
## Аргументы  
 `directory`  
 Каталог или путь, по которому компилятор будет выполнять поиск.  
  
## Заметки  
 При вызове **\/AI** может быть передан только один каталог.  Необходимо задавать по одному параметру **\/AI** для каждого пути, по которому необходимо выполнить поиск.  Например, чтобы добавить каталоги C:\\Project\\Meta и C:\\Common\\Meta в пути поиска компилятора для директив `#using`, укажите в командной строке компилятора параметры `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` или добавьте каждый каталог в свойство **Дополнительные каталоги \#using** в Visual Studio.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  В области навигации выберите **Свойства конфигурации**, **C\/C\+\+**, **Общие**.  
  
3.  Измените свойство **Дополнительные каталоги \#using**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)   
 [Директива \#using](../../preprocessor/hash-using-directive-cpp.md)