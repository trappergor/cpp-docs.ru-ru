---
title: _setmaxstdio
ms.date: 11/04/2016
apiname:
- _setmaxstdio
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
- setmaxstdio
- _setmaxstdio
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
ms.openlocfilehash: 58cffedf673e23a69c2d8040071b2e3353ff4502
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445088"
---
# <a name="setmaxstdio"></a>_setmaxstdio

Задает максимальное количество одновременно открытых файлов на **stdio** уровень.

## <a name="syntax"></a>Синтаксис

```C
int _setmaxstdio(
   int newmax
);
```

### <a name="parameters"></a>Параметры

*newmax*<br/>
Новое значение максимального числа одновременно открытых файлов на **stdio** уровень.

## <a name="return-value"></a>Возвращаемое значение

Возвращает *newmax* Если выполнение прошло успешно; в противном случае -1.

Если *newmax* — меньше, чем **_IOB_ENTRIES** или более поздней версии, то вызывается максимальное число дескрипторов, доступных в операционной системе, обработчик недопустимого параметра, как описано в разделе [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает -1 и задает **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Setmaxstdio** функция изменяет максимальное значение количества файлов, которые могут быть одновременно открыты на **stdio** уровень.

Ввод-вывод среды выполнения C теперь поддерживает большее число открытых файлов на базе платформ Win32, чем в предыдущих версиях. До 2048 файлов может быть открыто одновременно на [уровень lowio](../../c-runtime-library/low-level-i-o.md) (то есть, открыты и доступны с помощью параметра **_open**, **_read**, **_write**и так далее к семейству функций ввода-вывода). До 512 файлов может быть открыто одновременно на [уровень stdio](../../c-runtime-library/stream-i-o.md) (то есть, открыты и доступны с помощью параметра **fopen**, **fgetc**, **fputc** и так далее к семейству функций). Ограничение в 512 открытых файлов на **stdio** уровня можно увеличить до максимального значения 2048 с помощью параметра **_setmaxstdio** функции.

Так как **stdio**-уровня функции, такие как **fopen**, строятся на основе **lowio** функции, максимального значения 2048 является верхним пределом для числа одновременно Открытие файлов, доступных в библиотеке времени выполнения C.

> [!NOTE]
> Это пороговое значение может превышать ограничения, поддерживаемые определенной конфигурацией и платформой Win32.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. в разделе [_getmaxstdio](getmaxstdio.md) пример использования **_setmaxstdio**.

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
