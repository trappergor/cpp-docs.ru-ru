---
title: "/LINKERMEMBER | Microsoft Docs"
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
  - "/linkermember"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINKERMEMBER - параметр программы dumpbin"
  - "LINKERMEMBER - параметр (программа dumpbin)"
  - "-LINKERMEMBER - параметр (программа dumpbin)"
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LINKERMEMBER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINKERMEMBER[:{1|2}]  
```  
  
## Заметки  
 Этот параметр выводит открытые символы, определенные в библиотеке.  Аргумент 1 позволяет вывести символы в объектном порядке вместе с их смещениями.  Аргумент 2 позволяет вывести смещения и индексные номера объектов, после чего выводится список символов вместе с их объектными индексами, упорядоченный по алфавиту.  Чтобы вывести всю эту информацию, параметр \/LINKERMEMBER следует использовать без численного аргумента.  
  
 В файлах, созданных с использованием параметра компилятора [\/GL](../../build/reference/gl-whole-program-optimization.md), может использоваться только параметр DUMPBIN [\/HEADERS](../../build/reference/headers.md).  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)