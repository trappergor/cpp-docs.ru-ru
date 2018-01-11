---
title: "_get_doserrno | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_doserrno
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
- _get_doserrno
- get_doserrno
dev_langs: C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8eff0ac1a97c9a1d48b82601eb0d6dc0bb8bed0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="getdoserrno"></a>_get_doserrno
Получает значение ошибки, возвращенное операционной системой, до преобразования в значение `errno`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _get_doserrno(   
   int * pValue   
);   
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pValue`  
 Указатель на целое число, в которое должно быть подставлено текущее значение глобального макроса `_doserrno`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если макрос `_get_doserrno` выполняется успешно, он возвращает значение 0, в случае сбоя — код ошибки. Если параметр `pValue` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Глобальный макрос `_doserrno` задается равным нулю во время инициализации CRT (до начала выполнения обработки). Ему присваивается значение ошибки операционной системы, возвращаемое вызовом любой функции уровня системы. Вызов возвращает ошибку операционной системы и никогда не сбрасывается до нуля во время выполнения. При написании кода для проверки значения ошибки, возвращаемого функцией, всегда выполняйте сброс `_doserrno` с помощью функции [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md) до вызова функции. Поскольку другой вызов функции может перезаписать `_doserrno`, проверяйте значения, используя `_get_doserrno` сразу после вызова функции.  
  
 Рекомендуется использовать [_get_errno](../../c-runtime-library/reference/get-errno.md) вместо `_get_doserrno` для переносимых кодов ошибок.  
  
 Возможные значения `_doserrno` определяются в \<errno.h>.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_get_doserrno`|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h>, \<cerrno> (C++)|  
  
 `_get_doserrno` является расширением Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md)   
 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)