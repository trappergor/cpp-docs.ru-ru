---
title: "_get_tzname | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_tzname
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
- _get_tzname
- get_tzname
dev_langs: C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a1b5f7db562dc0173cda49212425b237a44c0610
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="gettzname"></a>_get_tzname
Возвращает представление названия часового пояса или названия часового пояса с переходом на летнее время (DST) в виде строки символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pReturnValue`  
 Длина строки `timeZoneName` включая завершающий нуль-символ.  
  
 [выходной] `timeZoneName`  
 Адрес строки символов, представляющей название часового пояса или название часового пояса с переходом летнее время (DST), в зависимости от значения `index`.  
  
 [in] `sizeInBytes`  
 Размер строки символов `timeZoneName` в байтах.  
  
 [in] `index`  
 Индекс, определяющий извлечение одного или двух названий часовых поясов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ноль в случае успешного выполнения; в противном случае — значение типа `errno`.  
  
 Если `timeZoneName` имеет значение `NULL`, либо значение `sizeInBytes` равно нулю или меньше нуля (но не одновременно), вызывается обработчик недопустимого параметра, как описывается в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `EINVAL`.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|Возвращаемое значение|Содержимое `timeZoneName`|  
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|  
|Длина названия часового пояса|`NULL`|0|0 или 1|0|не изменено|  
|Длина названия часового пояса|any|> 0|0 или 1|0|Название часового пояса|  
|не изменено|`NULL`|> 0|любые|`EINVAL`|не изменено|  
|не изменено|any|нуль|любые|`EINVAL`|не изменено|  
|не изменено|any|> 0|> 1|`EINVAL`|не изменено|  
  
## <a name="remarks"></a>Примечания  
 Функция `_get_tzname` извлекает представление названия часового пояса или названия часового пояса с переходом на летнее время (DST) в виде строки символов по адресу параметра `timeZoneName` в зависимости от значения index, а также размер строки в `pReturnValue`. Если `timeZoneName` равно `NULL` и `sizeInBytes` равно нулю, в `pReturnValue` возвращается только размер строки соответствующего часового пояса в байтах. Значение индекса должно быть равно 0 для стандартного часового пояса или 1 для часового пояса с переходом на летнее время. Другие значения индекса дают неопределенные результаты.  
  
### <a name="index-values"></a>Значения индекса  
  
|`index`|Содержимое `timeZoneName`|Значение `timeZoneName` по умолчанию|  
|-------------|--------------------------------|----------------------------------|  
|0|Название часового пояса|"PST"|  
|1|Название часового пояса с переходом на летнее время|"PDT"|  
|> 1 или < 0|`errno` имеет значение `EINVAL`|не изменено|  
  
 Если значения не изменяются явным образом во время выполнения, по умолчанию используются значения "PST" и "PDT" соответственно.  Размеры этих массивов знаков регламентируются значением `TZNAME_MAX`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_get_tzname`|\<time.h>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME_MAX](../../c-runtime-library/tzname-max.md)