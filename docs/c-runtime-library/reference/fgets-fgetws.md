---
title: fgets, fgetws
ms.date: 4/2/2020
api_name:
- fgets
- fgetws
- _o_fgets
- _o_fgetws
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
- _fgetts
- fgetws
- fgets
helpviewer_keywords:
- _fgetts function
- streams, getting strings from
- streams, reading from
- fgets function
- fgetws function
- fgetts function
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
ms.openlocfilehash: a1120529157801aac5cf1c4fd61f844fde443bed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346869"
---
# <a name="fgets-fgetws"></a>fgets, fgetws

Получает строку из потока.

## <a name="syntax"></a>Синтаксис

```C
char *fgets(
   char *str,
   int numChars,
   FILE *stream
);
wchar_t *fgetws(
   wchar_t *str,
   int numChars,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Место хранения данных.

*numChars*<br/>
Максимальное число считываемых символов.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает *str*. **NULL** возвращается для указания ошибки или состояния конца файла. Используйте **feof** или **ferror,** чтобы определить, произошла ли ошибка. Если *str* или *stream* является нулевой указатель, или *numChars* меньше, чем или равна нулю, эта функция вызывает недействительным обработчик параметров, как описано в [параметре проверки](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, **errno** устанавливается **в EINVAL** и функция возвращает **NULL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **fgets** считывает строку из *аргумента* потока ввода и хранит ее в *str.* **fgets** читает символы от текущего положения потока и в том числе первый символ новой строки, до конца потока, или до тех пор, пока количество символов читать *равна numChars* - 1, в зависимости от того, приходит первым. Результат, хранящийся в *str,* приложен нулевым символом. Считываемый символ новой строки (если такой есть) включается в строку.

**fgetws** является широкохарактерным вариантом **fgets**.

**fgetws** читает широкий характер аргумент *str* как многобайт-символ строки или широкий символ строки в зависимости от того, *поток* открыт в текстовом режиме или двоичного режима, соответственно. Дополнительные сведения об использовании текстового и двоичного режима в Юникоде и многобайтовом потоковом вводе-выводе см. в разделах [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md) и [Ввод-вывод в поток в кодировке Юникод в текстовом и двоичном режиме](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgetts**|**fgets**|**fgets**|**fgetws**|

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fgets**|\<stdio.h>|
|**fgetws**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fgets.c
// This program uses fgets to display
// the first line from a file.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[100];

   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )
   {
      if( fgets( line, 100, stream ) == NULL)
         printf( "fgets error\numChars" );
      else
         printf( "%s", line);
      fclose( stream );
   }
}
```

### <a name="input-crt_fgetstxt"></a>Входные данные: crt_fgets.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Выходные данные

```Output
Line one.
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
