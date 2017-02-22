---
title: "LIBRARY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LIBRARY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIBRARY - оператор DEF-файла"
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# LIBRARY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает LINK для создания библиотеки DLL.  В то же время, LINK создает библиотеку импорта, если EXP\-файл не используется в построении.  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## Заметки  
 Аргумент *library* указывает имя библиотеки DLL.  Также можно использовать параметр компоновщика [\/OUT](../../build/reference/out-output-file-name.md), чтобы указать выходное имя библиотеки DLL.  
  
 Аргумент BASE\=*address* задает базовый адрес, который операционная система использует для загрузки библиотеки DLL.  Этот аргумент переопределяет расположение библиотеки DLL по умолчанию 0x10000000.  Подробные сведения о базовых адресах см. в описании параметра [\/BASE](../../build/reference/base-base-address.md).  
  
 При построении библиотеки DLL следует помнить об использовании параметра компоновщика [\/DLL](../../build/reference/dll-build-a-dll.md).  
  
## См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)