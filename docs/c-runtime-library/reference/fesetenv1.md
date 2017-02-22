---
title: "fesetenv1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fesetenv"
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
  - "fesetenv"
  - "fenv/fesetenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функция fesetenv"
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# fesetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает текущую среду с плавающей запятой.  
  
## Синтаксис  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
  
```  
  
#### Параметры  
 `penv`  
 Указатель на `fenv_t` объект, содержащий среде с плавающей запятой как набор путем вызова [fegetenv](../Topic/fegetenv2.md) или [feholdexcept](../Topic/feholdexcept1.md). С плавающей запятой среды загрузки по умолчанию также можно указать с помощью макроса FE\_DFL\_ENV.  
  
## Возвращаемое значение  
 Возвращает 0, если среде был успешно установлен. В противном случае — возвращает ненулевое значение.  
  
## Заметки  
 `fesetenv` Функция задает текущую среду с плавающей запятой из значения, хранящегося в `fenv_t` объекта, на который указывает `penv`. Значение с плавающей точки среды — это набор флагов состояния и управления режимов, которые влияют на вычислений с плавающей запятой. Включает режим округления и флаги состояния для исключения с плавающей запятой. Если `penv` не FE\_DFL\_ENV или не указывает на допустимый `fenv_t` объекта, последующее поведение не определено.  
  
 Вызов этой функции задает исключение флаги состояния, которые находятся в `penv` но не приводит к появлению этих исключений.  
  
 Чтобы использовать эту функцию, необходимо отключить параметр оптимизации с плавающей запятой, которые может предотвратить доступ с помощью `#pragma fenv_access(on)` директив до вызова метода. Для получения дополнительной информации см. [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`fesetenv`|\<fenv.h\>|\<cfenv\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../Topic/fesetexceptflag2.md)