---
title: "_get_wpgmptr | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_wpgmptr
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
- get_wpgmptr
- _get_wpgmptr
dev_langs:
- C++
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d80fddf79be3c94eda07958919a886735666dc0d
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
# <a name="getwpgmptr"></a>_get_wpgmptr
Получает текущее значение глобальной переменной `_wpgmptr`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _get_wpgmptr(   
   wchar_t **pValue   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pValue`  
 Указатель на строку, которая будет заполнена текущим значением переменной `_wpgmptr`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае ошибки. Если параметр `pValue` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Вызывать только `_get_wpgmptr` Если программа содержит точку входа в Интернете, таких как `wmain()` или `wWinMain()`. Глобальная переменная `_wpgmptr` содержит полный путь к исполняемому файлу, связанному с процессом, в виде строки двухбайтовых знаков. Дополнительные сведения см. в разделе [_pgmptr _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_get_wpgmptr`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [_get_pgmptr](../../c-runtime-library/reference/get-pgmptr.md)
