---
title: "Проверка затирания памяти | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "память, перезаписи"
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Проверка затирания памяти
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если при вызове функции обработки кучи возникает нарушение прав доступа, возможно, программа повредила кучу.  Типичные симптомы такой ситуации следующие:  
  
```  
Access Violation in _searchseg  
```  
  
 Функция [\_heapchk](../../c-runtime-library/reference/heapchk.md) доступна как в отладочном построении, так и в построении выпуска \(только Windows NT\) для проверки целостности кучи библиотеки времени выполнения.  Вы можете использовать функцию `_heapchk` так же как функцию `AfxCheckMemory` для изолирования затирания памяти, например:  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 В случае отказа функции необходимо изолировать точку, в которой куча была повреждена.  
  
## См. также  
 [Устранение проблем построения выпуска](../../build/reference/fixing-release-build-problems.md)