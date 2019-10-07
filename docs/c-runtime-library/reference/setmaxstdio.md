---
title: _setmaxstdio
ms.date: 05/21/2019
api_name:
- _setmaxstdio
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
- setmaxstdio
- _setmaxstdio
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
ms.openlocfilehash: 620213b4df9ea555189a1403b3c9e83b55cad6c6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948225"
---
# <a name="_setmaxstdio"></a>_setmaxstdio

Задает максимальное число одновременно открытых файлов на уровне потокового ввода-вывода.

## <a name="syntax"></a>Синтаксис

```C
int _setmaxstdio(
   int new_max
);
```

### <a name="parameters"></a>Параметры

*new_max*<br/>
Новое максимальное число одновременно открытых файлов на уровне потокового ввода-вывода.

## <a name="return-value"></a>Возвращаемое значение

Возвращает значение *new_max* в случае успешного выполнения; в противном случае возвращает значение –1.

Если *new_max* меньше значения **_IOB_ENTRIES** или превышает максимальное число дескрипторов, доступных в операционной системе, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает –1 и задает для **errno** значение **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **_setmaxstdio** изменяет максимальное значение числа файлов, которые могут быть одновременно открыты на уровне потокового ввода-вывода.

Ввод-вывод среды выполнения C теперь поддерживает до 8192 одновременно открытых файлов на [низком уровне ввода-вывода](../../c-runtime-library/low-level-i-o.md). Этот уровень включает в себя файлы, которые открыты и доступны для работы посредством семейства функций ввода-вывода **_open**, **_read** и **_write**. По умолчанию на [уровне потокового ввода-вывода](../../c-runtime-library/stream-i-o.md) может быть открыто одновременно 512 файлов. Этот уровень включает в себя файлы, которые открыты и доступны для работы посредством семейства функций **fopen**, **fgetc** и **fputc**. Ограничение в 512 открытых файлов на уровне потокового ввода-вывода можно увеличить до максимального значения 8192 с помощью функции **_setmaxstdio**.

Так как функции уровня потокового ввода-вывода, например функция **fopen**, созданы на основе функций низкого уровня ввода-вывода, максимальное значение, равное 8192, является верхним пределом для числа одновременно открытых файлов, доступных в библиотеке среды выполнения C.

> [!NOTE]
> Это пороговое значение может превышать ограничения, поддерживаемые определенной конфигурацией и платформой Win32.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Пример использования **_setmaxstdio** см. в разделе [_getmaxstdio](getmaxstdio.md).

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
