---
title: "stdin, stdout, stderr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdin"
  - "stderr"
  - "stdout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "стандартный поток сообщений об ошибках"
  - "стандартный входной поток"
  - "стандартный выходной поток"
  - "stderr - функция"
  - "stdin - функция"
  - "stdout - функция"
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# stdin, stdout, stderr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## Заметки  
 Это стандартные потоки для ввода, вывода и вывода ошибок.  
  
 По умолчанию стандартный ввод — чтение с клавиатуры, в то время как стандартный вывод и стандартный вывод ошибок печатаются на экран.  
  
 Следующие указатели потока доступны для получения стандартных потоков:  
  
|Указатель|Поток|  
|---------------|-----------|  
|`stdin`|Стандартный ввод|  
|**stdout**|Стандартный вывод|  
|`stderr`|Стандартный вывод ошибок|  
  
 Эти указатели можно использовать в качестве аргументов для функций.  Некоторые функции, например **getchar** и `putchar`, используют `stdin` и **stdout** автоматически.  
  
 Эти указатели являются константами и им не могут быть присвоены новые значения.  Функция `freopen` может быть использована, чтобы перенаправить потоки на файлы на диске или на другие устройства.  Операционная система позволяет перенаправлять стандартный ввод и вывод программы на командном уровне.  
  
## См. также  
 [Потоковый ввод\-вывод](../c-runtime-library/stream-i-o.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)