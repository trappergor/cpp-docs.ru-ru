---
title: "feraiseexcept | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feraiseexcept"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "HeaderDef"
f1_keywords: 
  - "feraiseexcept"
  - "fenv/feraiseexcept"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "функция feraiseexcept"
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# feraiseexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывает указанный исключения с плавающей запятой.  
  
## Синтаксис  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### Параметры  
 `excepts`  
 Исключения с плавающей запятой для вызова.  
  
## Возвращаемое значение  
 Если все заданные исключения вызываются успешно, возвращается 0.  
  
## Заметки  
 `feraiseexcept` Функция пытается вызвать исключения с плавающей запятой, определяемое `excepts`.`feraiseexcept` Функция поддерживает эти макросы исключений, определенных в \< fenv.h \>:  
  
|Исключение\-макрос|Описание|  
|------------------------|--------------|  
|FE\_DIVBYZERO|Произошла ошибка своеобразие или полюсе в ранее операции с плавающей запятой; значение бесконечности был создан.|  
|FE\_INEXACT|Функция была вынуждена округления хранимый результат ранее операции с плавающей запятой.|  
|FE\_INVALID|Ошибка домена в ранее операции с плавающей запятой.|  
|FE\_OVERFLOW|Ошибка диапазона; более ранние результат операции с плавающей запятой слишком велико для представления.|  
|FE\_UNDERFLOW|Ранее результат операции с плавающей запятой слишком мал для представления в точности; значение denormal был создан.|  
|FE\_ALLEXCEPT|Побитовое или всех поддерживаемых исключения с плавающей запятой.|  
  
 `excepts` Аргумент может иметь ноль, один значений макрос исключение или побитового или двух или более макросов, поддерживаемых исключение. Если один из макросов указанное исключение FE\_OVERFLOW или FE\_UNDERFLOW, FE\_INEXACT исключение может возникнуть как побочный эффект.  
  
 Чтобы использовать эту функцию, необходимо отключить параметр оптимизации с плавающей запятой, которые может предотвратить доступ с помощью `#pragma fenv_access(on)` директив до вызова метода. Дополнительные сведения см. в разделе [fenv\_access](../../preprocessor/fenv-access.md).  
  
 **Системам Microsoft:** исключения, указанного в `excepts` вызываются в порядке FE\_INVALID, FE\_DIVBYZERO, FE\_OVERFLOW, FE\_UNDERFLOW, FE\_INEXACT. Тем не менее, FE\_INEXACT может возникнуть при вызове FE\_OVERFLOW или FE\_UNDERFLOW, даже если не указаны в `excepts`.**Завершение блока, относящегося только к системам Майкрософт**  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`feraiseexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../Topic/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../Topic/fetestexcept1.md)   
 [feupdateenv](../Topic/feupdateenv.md)