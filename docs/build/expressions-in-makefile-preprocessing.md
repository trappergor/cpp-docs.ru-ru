---
title: "Выражения в предобработке файлов makefile | Microsoft Docs"
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
  - "выражения [C++], предварительная обработка файла makefile"
  - "makefile - файлы, предварительная обработка"
  - "предварительная обработка файлов makefile"
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Выражения в предобработке файлов makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Константное выражение `constantexpression` в операторах **\!IF** и **\!ELSE IF** состоит из целочисленных констант \(в десятичной нотации или нотации языка C\), строковых констант или команд.  Для группировки выражений используются круглые скобки.  В выражениях используется арифметика знаковых целых чисел типа long в стиле C; числа имеют 32\-битную форму с дополнением до двух в диапазоне от 2 147 483 648 до 2 147 483 647.  
  
 В выражениях могут использоваться операторы, применяемые к константным значениям, кодам возврата команд, строкам, макросам и путям файловой системы.  
  
## Дополнительные сведения  
 [Операторы предобработки файлов makefile](../Topic/Makefile%20Preprocessing%20Operators.md)  
  
 [Выполнение программ в ходе предобработки](../build/executing-a-program-in-preprocessing.md)  
  
## См. также  
 [Предварительная обработка файла makefile](../Topic/Makefile%20Preprocessing.md)