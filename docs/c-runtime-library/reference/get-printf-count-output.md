---
title: _get_printf_count_output
ms.date: 11/04/2016
api_name:
- _get_printf_count_output
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
ms.openlocfilehash: 15b37ac759821ad56cc5c03c9b98719d8f0cc19a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955712"
---
# <a name="_get_printf_count_output"></a>_get_printf_count_output

Указывает, поддерживают ли функции [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Family формат **% n** .

## <a name="syntax"></a>Синтаксис

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Возвращаемое значение

Не равно нулю, если **% n** поддерживается, 0, если **% n** не поддерживается.

## <a name="remarks"></a>Примечания

Если **% n** не поддерживается (по умолчанию), при обнаружении **% n** в строке формата любой из функций **printf** вызовет обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если поддержка **% n** включена (см. [_set_printf_count_output](set-printf-count-output.md)), то **% n** будет работать, как описано в разделе [синтаксис спецификации формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_set_printf_count_output](set-printf-count-output.md).

## <a name="see-also"></a>См. также

[_set_printf_count_output](set-printf-count-output.md)<br/>
