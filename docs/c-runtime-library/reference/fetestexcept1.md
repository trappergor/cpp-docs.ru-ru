---
title: "fetestexcept1 | Документы Майкрософт"
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
- fetestexcept
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
- fetestexcept
- fenv/fetestexcept
dev_langs:
- C++
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
caps.latest.revision: 5
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
ms.openlocfilehash: 8b452efec193017684121607a30dfe5f937b053d
ms.lasthandoff: 02/24/2017

---
# <a name="fetestexcept"></a>fetestexcept
Определяет, какие из указанных флагов состояний исключения с плавающей запятой в настоящее время заданы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fetestexcept(  
   int excepts  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `excepts`  
 Побитовая операция ИЛИ для флагов состояний с плавающей запятой, которые требуется проверить.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает битовую маску, содержащую побитовую операцию ИЛИ для макросов исключений с плавающей запятой, которая соответствует установленным в данный момент флагам состояний исключения. Если исключения не заданы, возвращает 0.  
  
## <a name="remarks"></a>Примечания  
 Чтобы определить исключения, которые были вызваны операцией с плавающей запятой, используйте функцию fetestexcept. Чтобы указать флаги состояний исключения, которые требуется проверить, используйте параметр `excepts`. Функция `fetestexcept` использует следующие макросы исключений, определенные в файле \<fenv.h> в объекте `excepts` и возвращаемом значении:  
  
|Макрос исключения|Описание|  
|---------------------|-----------------|  
|FE_DIVBYZERO|При выполнении предыдущей операции с плавающей запятой произошла ошибка сингулярности или полюса, в результате чего было получено бесконечное значение.|  
|FE_INEXACT|Функция принудительно округлила сохраненный результат ранее выполненной операции с плавающей запятой.|  
|FE_INVALID|Ошибка домена в ранее выполненной операции с плавающей запятой.|  
|FE_OVERFLOW|Ошибка диапазона. Ранее выполненная операция с плавающей запятой возвратила слишком большое значение, которое не удается представить.|  
|FE_UNDERFLOW|Ранее выполненная операция с плавающей запятой возвратила слишком малое значение, которое не удается представить с полной точностью. Создано денормализованное значение.|  
|FE_ALLEXCEPT|Побитовая операция ИЛИ для всех поддерживаемых исключений с плавающей запятой.|  
  
 Аргумент `excepts` может быть равен 0. Кроме того, он может определяться с помощью поддерживаемого макроса исключения с плавающей запятой, а также побитовой операции ИЛИ для нескольких макросов. Действие любого другого значения аргумента `excepts` не определено.  
  
 Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`fetestexcept`|\<fenv.h>|\<cfenv>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feraiseexcept](../../c-runtime-library/reference/feraiseexcept.md)
