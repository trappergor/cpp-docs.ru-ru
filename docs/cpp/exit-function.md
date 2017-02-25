---
title: "Функция exit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit - функция"
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Функция exit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Функция **exit**, объявленная в стандартном включаемом файле STDLIB.H, завершает программу на языке C\+\+.  
  
 Значение, переданное в аргументе функции **exit**, возвращается операционной системе как код возврата или завершения программы.  Принято, чтобы нулевым кодом возврата обозначалось, что программа завершена успешно.  
  
> [!NOTE]
>  При помощи констант `EXIT_FAILURE` и `EXIT_SUCCESS`, которые определены во включаемом файле STDLIB.H, можно указать, была ли программа завершена успешно или с ошибкой.  
  
 Определить оператор `return` в функции **main** — это то же самое, что вызвать функцию **exit** с возвращаемым значением в качестве аргумента.  
  
 Дополнительные сведения см. в описании функции [exit](../c-runtime-library/reference/exit-exit-exit.md) в *Справочнике по библиотеке времени выполнения*.  
  
## См. также  
 [Завершение программы](../Topic/Program%20Termination.md)