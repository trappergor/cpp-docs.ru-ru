---
title: "Неустранимая ошибка C1311 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1311"
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Неустранимая ошибка C1311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

формат COFF не может выполнить статическую инициализацию "var" для адреса с размером в байтах  
  
 Адрес, значение которого неизвестно во время компиляции, не может быть статически назначен для переменной, тип которой имеет хранилище размером менее четырех байт.  
  
 Данная ошибка может возникнуть в коде, который в ином случае является допустимым кодом C\+\+.  
  
 В следующем примере показано одно условие, которое может вызвать ошибку C1311.  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```