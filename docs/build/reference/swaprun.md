---
title: "/SWAPRUN | Microsoft Docs"
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
  - "/swaprun"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SWAPRUN - параметр программы editbin"
  - "SWAPRUN - параметр (программа editbin)"
  - "-SWAPRUN - параметр (программа editbin)"
ms.assetid: 6eefd7f3-ca47-48e3-8509-323d27cf4ae7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SWAPRUN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SWAPRUN:{[!]NET|[!]CD}  
```  
  
## Заметки  
 Данный параметр выполняет редактирование образа, чтобы операционная система выполнила копирование образа в файл подкачки и его запуск оттуда.  Данный параметр используется для образов, находящихся в сетевых или съемных хранилищах.  
  
 Можно добавить или удалить квалификаторы NET или CD.  
  
-   Квалификатор NET указывает на то, что образ находится в сетевом хранилище.  
  
-   Квалификатор CD указывает на то, что образ находится на компакт\-диске или подобном съемном устройстве.  
  
-   Квалификаторы \!NET и \!CD используются для отмены действия квалификаторов NET и CD.  
  
## См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)