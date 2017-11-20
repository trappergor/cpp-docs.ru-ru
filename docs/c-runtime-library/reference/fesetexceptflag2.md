---
title: "fesetexceptflag2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: fesetexceptflag
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
- fesetexceptflag
- fenv/fesetexceptflag
dev_langs: C++
helpviewer_keywords: fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 786970d63482f2cede5e6b20af605accebe87da7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fesetexceptflag"></a>fesetexceptflag
Задает указанные флаги состояний с плавающей запятой в текущей среде вычислений с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fesetexceptflag(  
     const fexcept_t *pstatus,  
     int excepts  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pstatus`  
 Указатель на объект `fexcept_t`, содержащий значения, которым будут присваиваться флаги состояний исключения. Объект может задаваться в рамках предыдущего вызова функции [fegetexceptflag](fegetexceptflag2.md).  
  
 `excepts`  
 Флаги состояний исключения с плавающей запятой, которые требуется задать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если успешно заданы все указанные флаги состояний исключения, возвращает 0. В противном случае возвращается ненулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Функция `fesetexceptflag` присваивает состоянию флагов состояний исключения с плавающей запятой, заданных с помощью `excepts`, соответствующие значения объекта `fexcept_t`, на который указывает `pstatus`.  При этом не вызывается исключение. Указатель `pstatus` должен указывать на допустимый объект `fexcept_t`. В противном случае последующее поведение функции будет неопределенным. Функция `fesetexceptflag` поддерживает следующие значения макросов исключений в `excepts`, которые определены в \<fenv.h>:  
  
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
|`fesetexceptflag`|\<fenv.h>|\<cfenv>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetexceptflag](../../c-runtime-library/reference/fegetexceptflag2.md)