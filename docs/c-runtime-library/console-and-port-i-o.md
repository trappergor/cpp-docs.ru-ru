---
title: "Ввод-вывод на консоль и порт | Microsoft Docs"
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
  - "Ввод и вывод [CRT], консоль"
  - "Ввод и вывод [CRT], порт"
  - "процедуры ввода и вывода, Ввод и вывод на консоль и порт"
  - "порты, процедуры ввода и вывода"
  - "процедуры"
  - "процедуры, Ввод и вывод на консоль и порт"
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ввод-вывод на консоль и порт
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти функции производят запись и чтение из консоли или указанного порта.  Подпрограммы ввода\-вывода на консоль несовместимы с вводом\-выводом в поток или низкоуровневыми библиотечными процедурами ввода\-вывода.  Не требуется открывать или закрывать консоль или порт для выполнения ввода\-вывода, поэтому не существует никаких процедур открытия или закрытия для данной категории.  В операционных системах Windows результат выполнения этих функций всегда направлен на консоль и не может быть перенаправлен.  
  
### Подпрограммы ввода\-вывода на консоль и порт  
  
|Подпрограмма|Применение|  
|------------------|----------------|  
|[\_cgets, \_cgetws](../c-runtime-library/cgets-cgetws.md), [\_cgets\_s, \_cgetws\_s](../Topic/_cgets_s,%20_cgetws_s.md)|Чтение строки из консоли|  
|[\_cprintf, \_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md), [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Вывод данных на консоль с форматированием|  
|[\_cputs](../Topic/_cputs,%20_cputws.md)|Вывод строки на консоль|  
|[\_cscanf, \_cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md), [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Чтение данных из консоли с форматированием|  
|[\_getch, \_getwch](../Topic/_getch,%20_getwch.md)|Чтение символа из консоли|  
|[\_getche, \_getwche](../Topic/_getch,%20_getwch.md)|Чтение символа из консоли и его вывод|  
|[\_inp](../c-runtime-library/inp-inpw-inpd.md)|Чтение одного байта из указанного порта ввода\-вывода|  
|[\_inpd](../c-runtime-library/inp-inpw-inpd.md)|Чтение двойного слова из указанного порта ввода\-вывода|  
|[\_inpw](../c-runtime-library/inp-inpw-inpd.md)|Чтение 2\-байтового слова из указанного порта ввода\-вывода|  
|[\_kbhit](../c-runtime-library/reference/kbhit.md)|Проверка нажатия клавиши в консоли: используется перед попыткой чтения из консоли|  
|[\_outp](../Topic/_outp,%20_outpw,%20_outpd.md)|Вывод одного байта в указанный порт ввода\-вывода|  
|[\_outpd](../Topic/_outp,%20_outpw,%20_outpd.md)|Вывод двойного слова в указанный порт ввода\-вывода|  
|[\_outpw](../Topic/_outp,%20_outpw,%20_outpd.md)|Вывод слова в указанный порт ввода\-вывода|  
|[\_putch, \_putwch](../Topic/_putch,%20_putwch.md)|Вывод символа на консоль|  
|[\_ungetch, \_ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|Отмена чтения последнего символа из консоли, таким образом данный символ станет следующим символом для чтения.|  
  
## См. также  
 [Ввод и вывод](../Topic/Input%20and%20Output.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)