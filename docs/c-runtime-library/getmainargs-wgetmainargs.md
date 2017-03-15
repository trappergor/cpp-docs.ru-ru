---
title: "__getmainargs, __wgetmainargs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__wgetmainargs"
  - "__getmainargs"
apilocation: 
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# __getmainargs, __wgetmainargs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывает синтаксический разбор аргументов в командной строке и копирует аргументы для `main()` с помощью переданных указателей.  
  
## Синтаксис  
  
```cpp  
int __getmainargs(  
    int * _Argc,   
   char *** _Argv,   
   char *** _Env,   
   int _DoWildCard,  
_startupinfo * _StartInfo);  
  
 int __wgetmainargs (  
   int *_Argc,  
   wchar_t ***_Argv,  
   wchar_t ***_Env,  
   int _DoWildCard,  
   _startupinfo * _StartInfo)  
  
```  
  
#### Параметры  
 `_Argc`  
 Целое число, которое содержит количество аргументов, следующих в `argv`.  Параметр `argc` всегда больше или равен 1.  
  
 `_Argv`  
 Массив завершающихся null строк, представляющих введенные пользователем программы аргументы командной строки.  По соглашению `argv[0]` — это команда, с помощью которой вызывается программа, argv\[1\] — это первый аргумент командной строки и так далее до argv\[argc\], который всегда имеет значение NULL.  Первый аргумент командной строки — всегда `argv[1]`, а последний — `argv[argc – 1]`.  
  
 `_Env`  
 Массив строк, представляющих переменные, заданные в среде пользователя.  Этот массив завершен записью NULL.  
  
 `_DoWildCard`  
 Целое число, которое разворачивает подстановочные знаки в аргументах командной строки, если установлено значение 1, и ничего не делает, если установлено значение 0.  
  
 `_StartInfo`  
 Другие данные, передаваемые в библиотеку CRT DLL.  
  
## Возвращаемое значение  
 0 если операция завершилась успешно; отрицательное значение, если нет.  
  
## Заметки  
 Используйте `__getmainargs` для платформ, которые не используют расширенные символы, и `__wgetmainargs` для платформ, которые их используют.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|\_\_getmainargs|internal.h|  
|\_\_wgetmainargs|internal.h|