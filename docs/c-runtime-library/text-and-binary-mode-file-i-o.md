---
title: "Файловый ввод-вывод в текстовом и двоичном режиме | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "двоичный доступ"
  - "двоичный доступ, ввод и вывод файла двоичного режима"
  - "файлы [C++], открытые функции"
  - "функции [CRT], доступ к файлам"
  - "Ввод и вывод [CRT], двоичные"
  - "Ввод и вывод [CRT], текстовые файлы"
  - "Ввод и вывод [CRT], режимы перевода"
  - "текстовые файлы, Ввод и вывод"
  - "режимы перевода (файловый ввод и вывод)"
  - "преобразование, режимы"
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Файловый ввод-вывод в текстовом и двоичном режиме
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Операции файлового ввода\-вывода происходят в одном из двух режимов преобразования, текстовом или бинарном, в зависимости от режима, в котором файл открыт.  Файлы данных обычно обрабатываются в текстовом режиме.  Для контроля режима преобразования файла можно:  
  
-   Сохранить текущий параметр по умолчанию и указать альтернативный режим только при открытии выбранных файлов.  
  
-   Используйте функцию [\_set\_fmode](../c-runtime-library/reference/set-fmode.md) для изменения режима по умолчанию для вновь открытых файлов.  Используйте [\_get\_fmode](../c-runtime-library/reference/get-fmode.md), чтобы найти текущий режим по умолчанию.  Изначальный параметр по умолчанию — режим текста \(`_O_TEXT`\).  
  
-   Изменить режим преобразования по умолчанию непосредственно с помощью установки глобальной переменной [\_fmode](../c-runtime-library/fmode.md) в программе.  Функция `_set_fmode` устанавливает значение этой переменной, но ее можно также установить непосредственно.  
  
 При вызове функции, открывающей файл, например [\_open](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [\_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) или [\_sopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md), можно переопределить текущее значение параметра по умолчанию `_fmode` путем указания соответствующего аргумента функции [\_set\_fmode](../c-runtime-library/reference/set-fmode.md).  Потоки `stdin`, `stdout` и `stderr` всегда открываются в текстовом режиме по умолчанию; можно также переопределить это значение по умолчанию при открытии любого из этих файлов.  Используйте [\_setmode](../c-runtime-library/reference/setmode.md) для изменения режима преобразования с помощью дескриптора файла после открытия файла.  
  
## См. также  
 [Ввод и вывод](../Topic/Input%20and%20Output.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)