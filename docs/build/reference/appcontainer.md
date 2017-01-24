---
title: "/APPCONTAINER | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/APPCONTAINER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/APPCONTAINER - параметр editbin"
  - "APPCONTAINER - параметр editbin"
  - "-APPCONTAINER - параметр editbin"
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /APPCONTAINER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Помечает исполняемый файл, который должен выполняться в контейнере приложения, например [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] или универсальное приложение Windows.  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## Заметки  
 Исполняемый файл, для которого задан параметр **\/APPCONTAINER**, может выполняться только в контейнере приложения, то есть в среде изоляции процессов, которая была введена в Windows 8. Для [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] и универсальных приложений Windows этот параметр должен быть установлен.  
  
## См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)   
 [Что такое универсальное приложение Windows?](http://go.microsoft.com/fwlink/p/?LinkID=522074)