---
title: puts, _putws | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _putws
- puts
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
- _putts
- _putws
- puts
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8a0b4f0c4924970905cb541d82450a807de1357
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404533"
---
# <a name="puts-putws"></a>puts, _putws

Записывает строку в поток **stdout**.

## <a name="syntax"></a>Синтаксис

```C
int puts(
   const char *str
);
int _putws(
   const wchar_t *str
);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Выходная строка.

## <a name="return-value"></a>Возвращаемое значение

Возвращает неотрицательное значение в случае успешного выполнения. Если **помещает** завершается ошибкой, возвращается **EOF**; Если **_putws** завершается ошибкой, возвращается **WEOF**. Если *str* является пустым указателем, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, функции задают **errno** для **EINVAL** и возвращают **EOF** или **WEOF**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Помещает** функция записывает *str* в стандартный выходной поток **stdout**, заменив строку завершающуюся нуль-символ («\0») символом перевода строки («\n») выходной поток.

**_putws** — это двухбайтовая версия **помещает**; две функции ведут себя одинаково, если поток открыт в режиме ANSI. **Помещает** сейчас не поддерживает выходные данные в поток в кодировке Юникод.

**_putwch** записывает знаки Юникода, используя текущий параметр языкового СТАНДАРТА КОНСОЛИ.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_putts**|**puts**|**puts**|**_putws**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**puts**|\<stdio.h>|
|**_putws**|\<stdio.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_puts.c
// This program uses puts to write a string to stdout.

#include <stdio.h>

int main( void )
{
   puts( "Hello world from puts!" );
}
```

### <a name="output"></a>Вывод

```Output
Hello world from puts!
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
