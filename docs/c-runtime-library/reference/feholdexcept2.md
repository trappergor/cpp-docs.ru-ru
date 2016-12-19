---
title: "feholdexcept | Microsoft Docs"
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
  - "feholdexcept"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "feholdexcept"
  - "fenv/feholdexcept"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "функция feholdexcept"
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# feholdexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сохраняет текущую среду с плавающей запятой в указанном объекте, очищает флаги состояния с плавающей запятой и, если это возможно, помещает среду с плавающей запятой в режиме без остановки.  
  
## Синтаксис  
  
```  
int feholdexcept(  
   fenv_t *penv  
);  
  
```  
  
#### Параметры  
 `penv`  
 Указатель на `fenv_t` объект, содержащий копию среды с плавающей запятой.  
  
## Возвращаемое значение  
 Возвращает ноль только в том случае, если функция является возможность успешного включения обработки исключений с плавающей запятой без остановки.  
  
## Заметки  
 `feholdexcept` Функция используется для сохранения состояния текущей среды с плавающей точкой в `fenv_t` объекта, на который указывает `penv`, и задать среду, чтобы не прерывать выполнение на исключения с плавающей запятой. Это известно как режим без остановки.  В этом режиме продолжается, пока среда восстанавливается с помощью [fesetenv](../Topic/fesetenv2.md) или [feupdateenv](../Topic/feupdateenv.md).  
  
 Эта функция используется в начале подпрограммы, который необходимо скрыть один или несколько исключений с плавающей запятой от вызывающей стороны. Сообщения об исключении, можно просто очистить нежелательных исключений с помощью [feclearexcept,](../../c-runtime-library/reference/feclearexcept1.md) и затем завершить режим бесперебойную работу с помощью вызова `feupdateenv`.  
  
 Чтобы использовать эту функцию, необходимо отключить параметр оптимизации с плавающей запятой, которые может предотвратить доступ с помощью `#pragma fenv_access(on)` директив до вызова метода. Дополнительные сведения см. в разделе [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`feholdexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](../Topic/fesetenv2.md)   
 [feupdateenv](../Topic/feupdateenv.md)