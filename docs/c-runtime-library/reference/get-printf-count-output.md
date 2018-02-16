---
title: "_get_printf_count_output | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 05184838f9ac68e697cc7ff326c33c266f865875
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output
Указывает, поддерживает ли семейство функций [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) формат `%n`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _get_printf_count_output();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение указывает на наличие поддержки `%n`, а 0 — на отсутствие поддержки `%n`.  
  
## <a name="remarks"></a>Примечания  
 Если `%n` не поддерживается (по умолчанию), при обнаружении `%n` в строке формата любой из функций `printf` будет вызван обработчик недопустимого параметра, как описывается в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если `%n` включена поддержка (см. [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)) затем `%n` будет вести себя, как описано в [синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_get_printf_count_output`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md).  
  
## <a name="see-also"></a>См. также  
[_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)  
