---
title: ungetc, ungetwc
ms.date: 4/2/2020
api_name:
- ungetwc
- ungetc
- _o_ungetc
- _o_ungetwc
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 484af7b72f860a8a9d12cf0b62444871caad4675
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361293"
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

*C*<br/>
Символ, который требуется поместить обратно.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха, каждая из этих функций возвращает характер аргумент *c*. Если *c* не может быть отодвинут или если символ не был прочитан, поток ввода не изменим и **ungetc** возвращает **EOF;** **ungetwc** возвращает **WEOF**. Если *поток* **NULL,** вызовуется недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **EOF** или **WEOF** возвращается и **errno** устанавливается **eINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **ungetc** толкает персонажа *c* обратно на *поток* и очищает индикатор конца файла. Поток должен быть открыт для чтения. Последующая операция чтения на *потоке* начинается с *c*. Попытка подтолкнуть **EOF** на поток с помощью **ungetc** игнорируется.

Персонажи, размещенные на потоке **ungetc,** могут быть стерты, если **fflush,** [fseek,](fseek-fseeki64.md) **fsetpos**или [перемотайте назад,](rewind.md) то до того, как персонаж будет прочитан из потока. Индикатор позиции в файле будет иметь значение, которое было до помещения символов обратно. Внешнее хранилище, соответствующее потоку, не изменяется. При успешном вызове **ungetc** против текстового потока индикатор позиции файла не указывается до тех пор, пока все оттесненные символы не будут прочитаны или отброшены. На каждом успешном вызове **ungetc** против двоичного потока индикатор позиции файла является decremented; если его значение составляло 0 до вызова, значение не определено после вызова.

Результаты непредсказуемы, если **ungetc** вызывается дважды без операции чтения или позиционирования файлов между двумя вызовами. После вызова **в fscanf,** вызов **ungetc** может выйти из строя, если другой читать операции (например, **getc**) была выполнена. Это потому, что **fscanf** сам называет **ungetc**.

**ungetwc** является широкохарактерным вариантом **ungetc**. Однако при каждом успешном **вызове ungetwc** против текста или двоичного потока значение индикатора позиции файла не указывается до тех пор, пока все отображенные символы не будут прочитаны или отброшены.

Эти функции являются потокобезопасными и блокируют конфиденциальные данные во время выполнения. Описание неблокирующей версии см. в разделе [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях Universal Windows Platform (UWP). Стандартные ручьи потока, связанные с консолью, **stdin,** **stdout**и **stderr,** должны быть перенаправлены, прежде чем функции C run-time могут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
