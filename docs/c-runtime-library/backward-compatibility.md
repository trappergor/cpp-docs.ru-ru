---
title: "Обратная совместимость | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обратная совместимость"
  - "обратная совместимость, библиотеки времени выполнения С"
  - "совместимость, библиотеки времени выполнения С"
  - "CRT - библиотека, совместимость"
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Обратная совместимость
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для обеспечения совместимости между версиями продукта библиотека OLDNAMES.LIB сопоставляет старые имена в новые имена.  Например, `open` сопоставляется в `_open`.  Необходимо явно выполнять связывание с OLDNAMES.LIB только при компиляции со следующими параметрами командной строки:  
  
-   `/Zl` \(опустить имя библиотеки по умолчанию из объектного файла\) и `/Ze` \(по умолчанию — использование расширений Майкрософт\)  
  
-   `/link` \(управление компоновщиком\), `/NOD` \(отключить поиск библиотеки по умолчанию\), и `/Ze`  
  
 Дополнительные сведения о параметрах компилятора командной строки см. в разделе [Compiler Reference](../build/reference/compiler-options.md).  
  
## См. также  
 [Совместимость](../c-runtime-library/compatibility.md)