---
title: "_get_timezone | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_timezone
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_timezone
- get_timezone
dev_langs: C++
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c83765da12b7e29d3e90037508a3cba4aa6d1ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="gettimezone"></a>_get_timezone
Извлекает разницу в секундах между временем в формате UTC и местным временем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      error_t _get_timezone(   
    long* seconds  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `seconds`  
 Разница в секундах между временем в формате UTC и местным временем.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль в случае успешного выполнения или значение `errno` при возникновении ошибки.  
  
## <a name="remarks"></a>Примечания  
 Функция `_get_timezone` извлекает целое число, представляющее разницу в секундах между временем UTC и местным временем. Значение по умолчанию — 28800 секунд (тихоокеанское время, на 8 часов отстающее от UTC).  
  
 Если параметр `seconds` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_get_timezone`|\<time.h>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)