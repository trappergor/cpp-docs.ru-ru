---
title: fputs, fputws
ms.date: 4/2/2020
api_name:
- fputs
- fputws
- _o_fputs
- _o_fputws
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
- fputs
- fputws
- _fputts
helpviewer_keywords:
- streams, writing strings to
- fputws function
- _fputts function
- fputs function
- fputts function
ms.assetid: d48c82b8-aa17-4830-8c7d-30442ddbb326
ms.openlocfilehash: 0a6ac7770e88975a60e1e4aef522dddf901206fb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346220"
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

*Ул*<br/>
Выходная строка.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает неотрицательное значение при успешном выполнении. По **ошибке, fputs** и **fputws** возвращают **EOF.** Если *str* или *stream* является нулевой указатель, эти функции вызывают недействительным обработчик параметров, как описано в [параметрвалиции.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции установить **errno** **eINVAL,** а затем **fputs** возвращает **EOF**, и **fputws** возвращает **WEOF**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Каждая из этих функций копирует *стрещер* к выходу *потока* в текущем положении. **fputws** копирует широкохарактерный аргумент *str* для *потоковой* передачи в виде строки мультибайт-символа или строки широкого символа в зависимости от того, открывается ли *поток* в текстовом режиме или двоичном режиме, соответственно. Ни одна из функций не копирует завершающий нуль-символ.

Эти две функции ведут себя одинаково, если поток открыт в режиме ANSI. в настоящее время **fputs** не поддерживает выход в поток UNICODE.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputts**|**fputs**|**fputs**|**fputws**|

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fputs**|\<stdio.h>|
|**fputws**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях Universal Windows Platform (UWP). Стандартные ручьи потока, связанные с консолью –**stdin,** **stdout**и **stderr**— должны быть перенаправлены, прежде чем функции C run-time могут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
