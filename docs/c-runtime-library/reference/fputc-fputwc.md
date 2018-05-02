---
title: fputc, fputwc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fputc
- fputwc
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
- fputc
- fputwc
- _fputtc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 707c6d7fa2e45a4fb0c841015f59ef786e539168
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="fputc-fputwc"></a>fputc, fputwc

Записывает символ в поток.

## <a name="syntax"></a>Синтаксис

```C
int fputc(
   int c,
   FILE *stream
);
wint_t fputwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ, который требуется записать.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает записанный символ. Для **fputc**, возвращаемое значение **EOF** указывает на ошибку. Для **fputwc**, возвращаемое значение **WEOF** указывает на ошибку. Если *поток* — **NULL**, эти функции вызывают обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, они возвращают **EOF** и задайте **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций записывает отдельный знак *c* файл в позиции показан индикатор позиции связанного файла (если она задана) и перемещает индикатор соответствующим образом. В случае использования **fputc** и **fputwc**, с которым связан файл *поток*. Если файл не поддерживает запросы позиционирования или был открыт в режиме добавления, символ добавляется в конец потока.

Эти две функции ведут себя одинаково, если поток открыт в режиме ANSI. **fputc** сейчас не поддерживает выходные данные в поток в кодировке Юникод.

Версии с суффиксом **_nolock** идентичны за исключением того, что они не защищены от помех со стороны других потоков. Дополнительные сведения см. в разделе [_fputc_nolock, _fputwc_nolock](fputc-nolock-fputwc-nolock.md).

Ниже приводятся примечания для конкретных подпрограмм.

|Подпрограмма|Примечания|
|-------------|-------------|
|**fputc**|Эквивалентно **putc**, но оно реализовано только как функция, а не как функция и макрос.|
|**fputwc**|Версия с расширенными символами из **fputc**. Записывает *c* как Многобайтовый или расширенный символ согласно ли *поток* открывается в текстовом или двоичном режиме.|

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputtc**|**fputc**|**fputc**|**fputwc**|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fputc**|\<stdio.h>|
|**fputwc**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью —**stdin**, **stdout**, и **stderr**— необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fputc.c
// This program uses fputc
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
   char strptr1[] = "This is a test of fputc!!\n";
   char *p;

   // Print line to stream using fputc.
   p = strptr1;
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;

}
```

```Output
This is a test of fputc!!
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
