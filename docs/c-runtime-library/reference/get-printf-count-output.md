---
title: _get_printf_count_output | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 216df8d973f391db2b6114d9bbcb50dcf509c5b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398374"
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output

Указывает, является ли [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-семейство функций поддержки **%n** формат.

## <a name="syntax"></a>Синтаксис

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Возвращаемое значение

Не равно нулю, если **%n** поддерживается, 0, если **%n** не поддерживается.

## <a name="remarks"></a>Примечания

Если **%n** — не поддерживается (по умолчанию), возникновения **%n** в строке форматирования любого **printf** функции вызывают обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если **%n** включена поддержка (см. [_set_printf_count_output](set-printf-count-output.md)) затем **%n** будет вести себя, как описано в [синтаксис описания формата: функции printf и wprintf Функции](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_set_printf_count_output](set-printf-count-output.md).

## <a name="see-also"></a>См. также

[_set_printf_count_output](set-printf-count-output.md)<br/>
