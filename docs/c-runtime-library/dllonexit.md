---
title: "__dllonexit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__dllonexit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr120_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__dllonexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__dllonexit"
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# __dllonexit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Регистрирует процедуру, вызываемую во время выхода.  
  
## Синтаксис  
  
```  
_onexit_t __dllonexit(  
   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### Параметры  
 `func`  
 Указатель на функцию, которая должна выполняться при выходе.  
  
 `pbegin`  
 Указатель на переменную, которая указывает на начало списка функций для выполнения при отсоединении.  
  
 `pend`  
 Указатель на переменную, которая указывает на конец списка функций для выполнения при отсоединении.  
  
## Возвращаемое значение  
 В случае успеха указатель на функцию пользователя.  В противном случае пустой указатель.  
  
## Заметки  
 Функция `__dllonexit` аналогична функции [\_onexit](../c-runtime-library/reference/onexit-onexit-m.md), за исключением того, что глобальные переменные, используемые этой функцией, не видны в этой процедуре.  Вместо глобальных переменных эта функция использует параметры `pbegin` и `pend`.  
  
 Функции `_onexit` и `atexit` в DLL, скомпонованных с библиотекой MSVCRT.LIB, должны вести собственный список atexit\/\_onexit.  Это рабочая процедура, которая вызывается такими библиотеками DLL.  
  
 Тип `_PVFV` определен как `typedef void (__cdecl *_PVFV)(void)`.  
  
## Требования  
  
|Подпрограмма|Требуемый файлы|  
|------------------|---------------------|  
|\_\_dllonexit|onexit.c|  
  
## См. также  
 [\_onexit, \_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md)