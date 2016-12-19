---
title: "_setjmp3 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setjmp3"
apilocation: 
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "setjmp3"
  - "_setjmp3"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setjmp3 - функция"
  - "setjmp3 - функция"
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _setjmp3
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внутренняя функция CRT.  Новая реализация функции `setjmp`.  
  
## Синтаксис  
  
```  
int _setjmp3(    OUT jmp_buf env,    int count,    (optional parameters) );  
```  
  
#### Параметры  
 \[выходной\] `env`  
 Адрес буфера для хранения сведений о состоянии.  
  
 \[входной\] `count`  
 Число дополнительных `DWORD` данных, хранимых в `optional parameters`.  
  
 \[входной\] `optional parameters`  
 Дополнительные данные, отправленные встроенной функцией `setjmp`.  Первое `DWORD` — это указатель функции, которая используется для очистки лишних данных и возврата к состоянию неизменяемого регистра.  Второе `DWORD` — уровень повторной попытки, который необходимо восстановить.  Все дальнейшие данные сохраняются в массиве универсальных данных в `jmp_buf`.  
  
## Возвращаемое значение  
 Всегда возвращает 0.  
  
## Заметки  
 Не используйте эту функцию в программе C\+\+.  Это встроенная функция, не поддерживающая C\+\+.  Дополнительные сведения об использовании `setjmp` см. в разделе [Использование setjmp\/longjmp](../cpp/using-setjmp-longjmp.md).  
  
## Требования  
  
## См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [setjmp](../c-runtime-library/reference/setjmp.md)