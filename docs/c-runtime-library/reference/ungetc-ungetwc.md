---
title: ungetc, ungetwc
ms.date: 11/04/2016
apiname:
- ungetwc
- ungetc
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
- _ungettc
- ungetwc
- ungetc
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
ms.openlocfilehash: c504540f8fbbe14961fa051bb93ebef350c2c1da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155437"
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc

Помещает символ обратно в поток.

## <a name="syntax"></a>Синтаксис

```C
int ungetc(
   int c,
   FILE *stream
);
wint_t ungetwc(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ, который требуется поместить обратно.

*поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении, каждая из этих функций Возвращает аргумент символа *c*. Если *c* не удается отправить обратно или если ни один символ не считан, входной поток не меняется и **ungetc** возвращает **EOF**; **ungetwc** возвращает **WEOF**. Если *поток* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **EOF** или **WEOF** возвращается и **errno** присваивается **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Ungetc** функция помещает символ *c* обратно в *поток* и удаляет индикатор окончания файла. Поток должен быть открыт для чтения. Последующая операция чтения на *поток* начинается с *c*. Попытка отправить **EOF** на поток с помощью **ungetc** учитывается.

Символы, помещенные в поток с помощью **ungetc** могут быть удалены, если **fflush**, [fseek](fseek-fseeki64.md), **fsetpos**, или [rewind](rewind.md) вызывается перед считыванием символа из потока. Индикатор позиции в файле будет иметь значение, которое было до помещения символов обратно. Внешнее хранилище, соответствующее потоку, не изменяется. При успешном **ungetc** вызов для текстового потока индикатор позиции файла не указано, пока все помещенные обратно символы будут считаны или удалены. На каждом успешно **ungetc** вызов для двоичного потока индикатор позиции файла уменьшается; если его значение было равно 0, перед вызовом, значение не определено после вызова метода.

Результаты будут непредсказуемыми Если **ungetc** вызывается дважды без чтения или размещения в файле операции между вызовами. После вызова **fscanf**, вызов **ungetc** может завершиться ошибкой, если другая операция чтения (такие как **getc**) будет выполнена. Это обусловлено **fscanf** сам вызывает **ungetc**.

**ungetwc** — это двухбайтовая версия **ungetc**. Тем не менее, на каждом успешно **ungetwc** вызов для текстового или двоичного потока значение индикатора позиции файла не указано, пока все помещенные обратно символы будут считаны или удалены.

Эти функции являются потокобезопасными и блокируют конфиденциальные данные во время выполнения. Описание неблокирующей версии см. в разделе [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, которые связаны с консоли, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ungetc.c
// This program first converts a character
// representation of an unsigned integer to an integer. If
// the program encounters a character that is not a digit,
// the program uses ungetc to replace it in the  stream.
//

#include <stdio.h>
#include <ctype.h>

int main( void )
{
   int ch;
   int result = 0;

   // Read in and convert number:
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )
      result = result * 10 + ch - '0';    // Use digit.
   if( ch != EOF )
      ungetc( ch, stdin );                // Put nondigit back.
   printf( "Number = %d\nNext character in stream = '%c'",
            result, getchar() );
}
```

```Output

      521aNumber = 521
Next character in stream = 'a'
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
