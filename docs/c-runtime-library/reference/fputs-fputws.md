---
title: fputs, fputws | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fputs
- fputws
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
- fputs
- fputws
- _fputts
dev_langs:
- C++
helpviewer_keywords:
- streams, writing strings to
- fputws function
- _fputts function
- fputs function
- fputts function
ms.assetid: d48c82b8-aa17-4830-8c7d-30442ddbb326
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94a8a872d88d42b2e76c5171b1adb22900b66436
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32400181"
---
# <a name="fputs-fputws"></a>fputs, fputws

Записывает строку в поток.

## <a name="syntax"></a>Синтаксис

```C
int fputs(
   const char *str,
   FILE *stream
);
int fputws(
   const wchar_t *str,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Выходная строка.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает неотрицательное значение при успешном выполнении. При возникновении ошибки **fputs** и **fputws** возвращают **EOF**. Если *str* или *поток* является пустым указателем, эти функции вызывают обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и затем **fputs** возвращает **EOF**, и  **fputws** возвращает **WEOF**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций копии *str* к выходу *поток* в текущей позиции. **fputws** копирует аргумента расширенных символов *str* для *поток* как строки многобайтовых символов или строку расширенных символов в соответствии с ли *поток*открыт в текстовом или двоичном режиме, соответственно. Ни одна из функций не копирует завершающий нуль-символ.

Эти две функции ведут себя одинаково, если поток открыт в режиме ANSI. **fputs** сейчас не поддерживает выходные данные в поток в кодировке Юникод.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputts**|**fputs**|**fputs**|**fputws**|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fputs**|\<stdio.h>|
|**fputws**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью —**stdin**, **stdout**, и **stderr**— необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fputs.c
// This program uses fputs to write
// a single line to the stdout stream.

#include <stdio.h>

int main( void )
{
   fputs( "Hello world from fputs.\n", stdout );
}
```

```Output
Hello world from fputs.
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
