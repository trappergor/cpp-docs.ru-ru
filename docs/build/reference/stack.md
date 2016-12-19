---
title: "/STACK | Microsoft Docs"
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
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/STACK - параметр программы editbin"
  - "STACK - параметр (программа editbin)"
  - "-STACK - параметр (программа editbin)"
  - "стек, установка размера"
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /STACK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## Заметки  
 Данный параметр задает размер стека в байтах и принимает аргументы в десятичной нотации или нотации языка C.  Параметр \/STACK применяется только к исполняемому файлу.  
  
 Аргумент *reserve* определяет общий объем виртуальной памяти, выделяемой под стек.  EDITBIN округляет указанное значение до ближайших 4 байт.  
  
 Необязательный аргумент `commit` интерпретируется операционной системой.  В Windows NT, Windows 95 и Windows 98 аргумент `commit` определяет объем одновременно выделяемой физической памяти.  Выделенная виртуальная память резервирует пространство в файле разбиения по страницам.  Увеличение значения `commit` позволяет сэкономить время, если приложению требуется больший объем стека, однако повышает требования к памяти и может увеличивать время запуска приложения.  
  
## См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)