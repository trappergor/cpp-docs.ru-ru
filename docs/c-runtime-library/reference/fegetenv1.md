---
title: "fegetenv | Microsoft Docs"
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
  - "fetegenv"
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
  - "fegetenv"
  - "fenv/fegetenv"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "функция fetegenv"
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fegetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сохраняет текущую среду с плавающей запятой в указанном объекте.  
  
## Синтаксис  
  
```  
int fegetenv(  
   fenv_t *penv  
);  
  
```  
  
#### Параметры  
 `penv`  
 Указатель на `fenv_t` объект, содержащий текущие значения с плавающей запятой среды.  
  
## Возвращаемое значение  
 Возвращает 0, если в среде с плавающей запятой успешно сохранена в `penv`. В противном случае — возвращает ненулевое значение.  
  
## Заметки  
 `fegetenv` Функция сохраняет текущую среду с плавающей запятой в объекте, на который указывает `penv`. Значение с плавающей точки среды — это набор флагов состояния и управления режимов, которые влияют на вычислений с плавающей запятой. Включает режим округления направление и флаги состояния для исключения с плавающей запятой. Если `penv` не указывает на допустимый `fenv_t` объекта, последующее поведение не определено.  
  
 Чтобы использовать эту функцию, необходимо отключить параметр оптимизации с плавающей запятой, которые может предотвратить доступ с помощью `#pragma fenv_access(on)` директив до вызова метода. Для получения дополнительной информации см. [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`fegetenv`|\<fenv.h\>|\<cfenv\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetenv](../../c-runtime-library/reference/fesetenv1.md)