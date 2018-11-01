---
title: puts, _putws
ms.date: 11/04/2016
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
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
ms.openlocfilehash: 0151d29f627a8f6b91142d619f64921333bb48f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667328"
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

Возвращает неотрицательное значение в случае успешного выполнения. Если **помещает** завершается ошибкой, возвращается **EOF**; Если **_putws** завершается ошибкой, возвращается **WEOF**. Если *str* является пустым указателем, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции задают **errno** для **EINVAL** и вернуть **EOF** или **WEOF**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Помещает** функцию записи *str* в стандартный выходной поток **stdout**, заменив строку завершающуюся нуль-символ («\0») с символом новой строки («\n») выходной поток.

**_putws** — это двухбайтовая версия **помещает**; обе функции ведут себя одинаково, если поток открыт в режиме ANSI. **Помещает** сейчас не поддерживает выходные данные в поток в кодировке Юникод.

**_putwch** записывает символы Юникода, используя текущий параметр языкового СТАНДАРТА КОНСОЛИ.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_putts**|**puts**|**puts**|**_putws**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**puts**|\<stdio.h>|
|**_putws**|\<stdio.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, которые связаны с консоли, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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
