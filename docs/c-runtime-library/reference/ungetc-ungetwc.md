---
title: ungetc, ungetwc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6618e3e92d605d9e706331b44b352b41d29d6a61
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414591"
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

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении, каждая из этих функций возвращает символьный аргумент *c*. Если *c* не может быть отложена или если невозможно считать ни один знак, входного потока не меняется и **ungetc** возвращает ** EOF`; **ungetwc` возвращает **WEOF**. Если *поток* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **EOF** или **WEOF** возвращается и **errno** равно **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Ungetc** функция помещает символ *c* обратно в *поток* и очищает индикатор end of file. Поток должен быть открыт для чтения. Последующие операции чтения на *поток* начинается с *c*. Попытка отправить **EOF** на поток с помощью **ungetc** учитывается.

Символы помещены в потоке, **ungetc** могут быть удалены, если **fflush**, [fseek](fseek-fseeki64.md), **fsetpos**, или [rewind](rewind.md) вызывается до знак, считанных из потока. Индикатор позиции в файле будет иметь значение, которое было до помещения символов обратно. Внешнее хранилище, соответствующее потоку, не изменяется. При успешном **ungetc** вызова для текстового потока, индикатор позиции файла не указан, пока все символы обратной передаче чтения или отменены. На каждом успешно **ungetc** уменьшается вызова для двоичного потока указателя позиции файла; если его значение было равно 0, перед вызовом, значение не определено после вызова метода.

Результаты будут непредсказуемыми Если **ungetc** вызывается дважды без чтения или расположение файла операции между этими двумя вызовами. После вызова **fscanf**, вызов **ungetc** может завершиться ошибкой, если другой операции чтения (такие как **getc**) выполнено. Это вызвано **fscanf** сама вызывает функцию **ungetc**.

**ungetwc** — это двухбайтовая версия **ungetc**. Однако на каждом успешно **ungetwc** вызов с текстовым или двоичным потоком значения индикатора позиции файла не указан, пока не считываются или отменены все символы обратной передаче.

Эти функции являются потокобезопасными и блокируют конфиденциальные данные во время выполнения. Описание неблокирующей версии см. в разделе [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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
