---
title: puts, _putws
ms.date: 4/2/2020
api_name:
- _putws
- puts
- _o__putws
- _o_puts
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
ms.openlocfilehash: 9681373ccf338daf05be3120fbadd39ba471e86a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332959"
---
# <a name="puts-_putws"></a>puts, _putws

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

*Ул*<br/>
Выходная строка.

## <a name="return-value"></a>Возвращаемое значение

Возвращает неотрицательное значение в случае успешного выполнения. Если **ставит** не удается, он возвращает **EOF**; если **_putws** не удается, он возвращает **WEOF**. Если *str* является нулевой указателем, вызовуется обработчик параметров недействительных, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функции установить **errno** **eINVAL** и вернуть **EOF** или **WEOF**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **ставит** *строку* в стандартный выходной поток **stdout,** заменив строку, прекращающийнулевой нулевой символ (''0') с новым символом строки ('n') в потоке вывода.

**_putws** является широкохарактерный вариант **ставит**; две функции ведут себя одинаково, если поток открыт в режиме ANSI. **в** настоящее время не поддерживает выход в поток UNICODE.

**_putwch** записывает символы Unicode с помощью текущей настройки CONSOLE LOCALE.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_putts**|**puts**|**puts**|**_putws**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**puts**|\<stdio.h>|
|**_putws**|\<stdio.h>|

Консоль не поддерживается в приложениях Universal Windows Platform (UWP). Стандартные ручьи потока, связанные с консолью, **stdin,** **stdout**и **stderr,** должны быть перенаправлены, прежде чем функции C run-time могут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

### <a name="output"></a>Выходные данные

```Output
Hello world from puts!
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
