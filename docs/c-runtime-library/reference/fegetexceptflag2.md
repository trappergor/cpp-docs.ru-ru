---
title: "fegetexceptflag2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fegetexceptflag
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetexceptflag
- fenv/fegetexceptflag
dev_langs:
- C++
helpviewer_keywords:
- fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 12d2046182c6778d7d6067e4ce60a7fc90ec850a
ms.lasthandoff: 02/24/2017

---
# <a name="fegetexceptflag"></a>fegetexceptflag
Сохраняет текущее состояние указанных флагов исключений с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fegetexceptflag(   
   fexcept_t* pstatus,   
   int excepts   
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `pstatus`  
 Указатель на объект `fexcept_t`, содержащий текущие значения флагов исключений, определяемых функцией `excepts`.  
  
 `excepts`  
 Флаги исключений с плавающей запятой, которые требуется сохранить в `pstatus`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении возвращается 0. В противном случае возвращается ненулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Функция `fegetexceptflag` сохраняет текущее состояние флагов состояния исключения с плавающей запятой, заданное с помощью функции `excepts`, в объекте `fexcept_t`, на который указывает `pstatus`.  Указатель `pstatus` должен указывать на допустимый объект `fexcept_t`. В противном случае последующее поведение функции будет неопределенным. Функция `fegetexceptflag` поддерживает макросы исключений, определенные в \<fenv.h>:  
  
|Макрос исключения|Описание|  
|---------------------|-----------------|  
|FE_DIVBYZERO|При выполнении предыдущей операции с плавающей запятой произошла ошибка сингулярности или полюса, в результате чего было получено бесконечное значение.|  
|FE_INEXACT|Функция принудительно округлила сохраненный результат ранее выполненной операции с плавающей запятой.|  
|FE_INVALID|Ошибка домена в ранее выполненной операции с плавающей запятой.|  
|FE_OVERFLOW|Ошибка диапазона. Ранее выполненная операция с плавающей запятой возвратила слишком большое значение, которое не удается представить.|  
|FE_UNDERFLOW|Ранее выполненная операция с плавающей запятой возвратила слишком малое значение, которое не удается представить с полной точностью. Создано денормализованное значение.|  
|FE_ALLEXCEPT|Побитовая операция ИЛИ для всех поддерживаемых исключений с плавающей запятой.|  
  
 Аргумент `excepts` может быть равен нулю. Кроме того, он может определяться с помощью поддерживаемого макроса исключения с плавающей запятой, а также побитовой операции ИЛИ для нескольких макросов. Действие любого другого значения аргумента не определено.  
  
 Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`fegetexceptflag`|\<fenv.h>|\<cfenv>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)
