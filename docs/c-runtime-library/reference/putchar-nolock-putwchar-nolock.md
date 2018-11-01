---
title: _putchar_nolock, _putwchar_nolock
ms.date: 11/04/2016
apiname:
- _putchar_nolock
- _putwchar_nolock
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
apitype: DLLExport
f1_keywords:
- putwchar_nolock
- _puttchar_nolock
- _putchar_nolock
- _putwchar_nolock
- putchar_nolock
helpviewer_keywords:
- _puttchar_nolock function
- putchar_nolock function
- characters, writing
- standard output, writing to
- putwchar_nolock function
- _putchar_nolock function
- _putwchar_nolock function
- puttchar_nolock function
ms.assetid: 9ac68092-bfc3-4352-b486-c3e780220575
ms.openlocfilehash: 5b7c0b4fcdbb7c29c48d9489cb262d2b1a1cf401
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580886"
---
# <a name="putcharnolock-putwcharnolock"></a>_putchar_nolock, _putwchar_nolock

Записывает символ в поток **stdout** без блокировки потока.

## <a name="syntax"></a>Синтаксис

```C
int _putchar_nolock(
   int c
);
wint_t _putwchar_nolock(
   wchar_t c
);

```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ, который требуется записать.

## <a name="return-value"></a>Возвращаемое значение

См. описание функций **putchar, putwchar**.

## <a name="remarks"></a>Примечания

**putchar_nolock** и **_putwchar_nolock** идентичны версиям без **_nolock** суффикса, за исключением того, что они не защищены от помех со стороны других потоков. Они могут выполняться быстрее, поскольку не создают дополнительную нагрузку, связанную с блокировкой работы других потоков. Используйте эти функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_puttchar_nolock**|**_putchar_nolock**|**_putchar_nolock**|**_putwchar_nolock**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_putchar_nolock**|\<stdio.h>|
|**_putwchar_nolock**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, которые связаны с консоли, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_putchar_nolock.c
/* This program uses putchar to write buffer
* to stdout. If an error occurs, the program
* stops before writing the entire buffer.
*/

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char *p, buffer[] = "This is the line of output\n";
   int  ch;

   ch = 0;

   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = _putchar_nolock( *p );
}
```

### <a name="output"></a>Вывод

```Output
This is the line of output
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
