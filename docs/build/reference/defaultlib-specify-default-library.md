---
title: "/DEFAULTLIB (определение библиотеки по умолчанию) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.DefaultLibraries"
  - "/defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEFAULTLIB - параметр компоновщика"
  - "DEFAULTLIB - параметр компоновщика"
  - "-DEFAULTLIB - параметр компоновщика"
  - "библиотеки, добавление в список"
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEFAULTLIB (определение библиотеки по умолчанию)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEFAULTLIB:library  
```  
  
## Заметки  
 Здесь:  
  
 *library*  
 Имя библиотеки, в которой следует выполнять поиск при разрешении внешних ссылок.  
  
## Заметки  
 Параметр \/DEFAULTLIB добавляет одну *библиотеку* в список библиотек, в которых LINK выполняет поиск при разрешении ссылок.  Поиск в библиотеке, заданной с помощью параметра \/DEFAULTLIB, выполняется после выполнения поиска в библиотеках, заданных в командной строке, и до выполнения поиска в библиотеках по умолчанию, перечисленных в OBJ\-файлах.  
  
 Параметр [Игнорировать все библиотеки по умолчанию](../../build/reference/nodefaultlib-ignore-libraries.md) \(\/NODEFAULTLIB\) переопределяет параметр \/DEFAULTLIB:*библиотека*.  Параметр [Игнорировать библиотеки](../../build/reference/nodefaultlib-ignore-libraries.md) \(\/NODEFAULTLIB:*библиотека*\) переопределяет параметр \/DEFAULTLIB:*библиотека*, если для обоих параметров задано одинаковое имя *библиотеки*.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
-   Данный параметр компоновщика недоступен в среде разработки Visual Studio.  Чтобы добавить библиотеку в стадию компоновщика, следует использовать свойство **Дополнительные зависимости** на странице свойств **Ввод**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)