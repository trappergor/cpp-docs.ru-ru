---
title: "feraiseexcept | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- feraiseexcept
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
apitype: HeaderDef
f1_keywords:
- feraiseexcept
- fenv/feraiseexcept
dev_langs:
- C++
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aaaa1848af2c8a7831017f6332afa988c305fe05
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="feraiseexcept"></a>feraiseexcept
Вызывает указанные исключения с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `excepts`  
 Исключения с плавающей запятой, которые необходимо вызвать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если все заданные исключения вызваны успешно, возвращается 0.  
  
## <a name="remarks"></a>Примечания  
 Функция `feraiseexcept` пытается очистить исключения с плавающей запятой, заданные функцией `excepts`.   Функция `feraiseexcept` поддерживает макросы исключений, определенные в \<fenv.h>:  
  
|Макрос исключения|Описание:|  
|---------------------|-----------------|  
|FE_DIVBYZERO|При выполнении предыдущей операции с плавающей запятой произошла ошибка сингулярности или полюса, в результате чего было получено бесконечное значение.|  
|FE_INEXACT|Функция принудительно округлила сохраненный результат ранее выполненной операции с плавающей запятой.|  
|FE_INVALID|Ошибка домена в ранее выполненной операции с плавающей запятой.|  
|FE_OVERFLOW|Ошибка диапазона. Ранее выполненная операция с плавающей запятой возвратила слишком большое значение, которое не удается представить.|  
|FE_UNDERFLOW|Ранее выполненная операция с плавающей запятой возвратила слишком малое значение, которое не удается представить с полной точностью. Создано денормализованное значение.|  
|FE_ALLEXCEPT|Побитовая операция ИЛИ для всех поддерживаемых исключений с плавающей запятой.|  
  
 Аргумент `excepts` может быть равен нулю, значению одного из макросов исключений, побитовой операции ИЛИ двух или больше поддерживаемых макросов исключений. Если один из указанных макросов исключений имеет значение FE_OVERFLOW или FE_UNDERFLOW, в качестве побочного эффекта может быть вызвано исключение FE_INEXACT.  
  
 Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).  
  
 **Блок, относящийся только к системам Майкрософт:** исключения, указанные в `excepts`, вызываются в порядке FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT. При этом FE_INEXACT может вызываться при вызове исключений FE_OVERFLOW или FE_UNDERFLOW, даже если оно не указано в `excepts`. **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`feraiseexcept`|\<fenv.h>|\<cfenv>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)