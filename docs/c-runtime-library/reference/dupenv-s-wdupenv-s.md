---
title: _dupenv_s, _wdupenv_s
ms.date: 4/2/2020
api_name:
- _dupenv_s
- _wdupenv_s
- _o__dupenv_s
- _o__wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
ms.openlocfilehash: f65f1da3e8cef077df04d0bdb7eb2aaf75afd9fa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348060"
---
# <a name="_dupenv_s-_wdupenv_s"></a>_dupenv_s, _wdupenv_s

Получает значение из текущей среды.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _dupenv_s(
   char **buffer,
   size_t *numberOfElements,
   const char *varname
);
errno_t _wdupenv_s(
   wchar_t **buffer,
   size_t *numberOfElements,
   const wchar_t *varname
);
```

### <a name="parameters"></a>Параметры

*Буфера*<br/>
Буфер для хранения значения переменной.

*numberOfElements*<br/>
Размер *буфера*.

*варимя*<br/>
Имя переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном выполнении, код ошибки при сбое.

Эти функции проверяют их параметры; если *буфер* или *varname* **null,** то недействительный обработчик параметра вызывается как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функции, установленные **errno** **к EINVAL** и вернуть **EINVAL**.

Если эти функции не могут выделить достаточно памяти, они устанавливают *буфер* **NULL** и *numberOfElements* до 0, и возвращают **ENOMEM.**

## <a name="remarks"></a>Remarks

Функция **_dupenv_s** выполняет поиск по списку переменных среды для *varname.* Если переменная найдена, **_dupenv_s** выделяет буфер и копирует значение переменной в буфер. Адрес буфера и длина возвращаются в *буфере* и *numberOfElements.* Выделяя сам буфер, **_dupenv_s** обеспечивает более удобную альтернативу [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!NOTE]
> Ответственность за освобождение памяти путем вызова функции [free](free.md) лежит на вызывающей программе.

Если переменная не найдена, *буфер* устанавливается на **NULL,** *numberOfElements* установлен на 0, а значение возврата 0, потому что эта ситуация не считается условием ошибки.

Если вас не интересует размер буфера, вы можете пройти **NULL** для *numberOfElements.*

**_dupenv_s** не является чувствительным случаем в операционной системе Windows. **_dupenv_s** использует копию среды, на которую указывает глобальная переменная **_environ** для доступа к окружающей среде. Смотрите замечания в [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) для обсуждения **_environ**.

Значение в *буфере* является копией значения переменной среды; изменение его не влияет на окружающую среду. Чтобы изменить значение переменной среды, используйте функцию [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md).

**_wdupenv_s** является широкохарактерным вариантом **_dupenv_s;** аргументы **_wdupenv_s** являются широкохарактерными строками. **Глобальная** переменная _wenviron является широкохарактерной версией **_environ.** Смотрите замечания в [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) подробнее о **_wenviron**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h>|
|**_wdupenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_dupenv_s.c
#include  <stdlib.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );
   if ( err ) return -1;
   printf( "nonexistentvariable = %s\n", pValue );
   free( pValue ); // It's OK to call free with NULL
}
```

```Output
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl
nonexistentvariable = (null)
```

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Экологические константы](../../c-runtime-library/environmental-constants.md)<br/>
[_dupenv_s_dbg, _wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
