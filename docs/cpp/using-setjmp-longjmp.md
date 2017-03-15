---
title: "Использование setjmp/longjmp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "longjmp"
  - "setjmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка исключений С++, setjmp/longjmp - функции"
  - "функция longjmp в программах C++"
  - "setjmp - функция"
  - "setjmp - функция, программы C++"
  - "SETJMP.H"
  - "SETJMPEX.H"
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Использование setjmp/longjmp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если [setjmp](../c-runtime-library/reference/setjmp.md) и [longjmp](../c-runtime-library/reference/longjmp.md) используются вместе, они предоставляют способ выполнения нелокального `goto`.  Обычно они используются для передачи элемента управления выполнением в код обработки ошибок или восстановления в вызванной ранее подпрограмме без использования стандартных соглашений вызова или возврата.  
  
> [!CAUTION]
>  Однако, поскольку `setjmp` и `longjmp` не поддерживают семантику объектов C\+\+, а также могут снизить производительность, не позволяя оптимизировать локальные переменные, использовать их в программах на C\+\+ не рекомендуется.  Вместо этого рекомендуется использовать конструкции `try`\/`catch`.  
  
 Если принято решение использовать `setjmp`\/`longjmp` в программе C\+\+, необходимо также включить SETJMP.H или SETJMPEX.H, чтобы обеспечить правильное взаимодействие между функциями и обработкой исключений C\+\+.  Если [\/EH](../build/reference/eh-exception-handling-model.md) используется для компиляции, деструкторы для локальных объектов вызываются во время очистки стека.  При использовании **\/EHs** для компиляции, если одна из функций вызывает функцию, которая использует [nothrow](../Topic/nothrow%20\(C++\).md), и функция, которая использует `nothrow`, вызывает `longjmp`, очистка деструкторов может не произойти в зависимости от оптимизатора.  
  
 В переносимом коде при выполнении нелокального оператора `goto`, вызывающего `longjmp`, правильное удаление основанных на кадре объектов может быть ненадежным.  
  
## См. также  
 [Сочетание исключений C \(структурированные\) и C\+\+](../Topic/Mixing%20C%20\(Structured\)%20and%20C++%20Exceptions.md)