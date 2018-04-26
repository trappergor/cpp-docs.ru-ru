---
title: _dupenv_s _wdupenv_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _dupenv_s
- _wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
dev_langs:
- C++
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e2a89679c8ca564236e1c9d1eccfee274eb4116
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="dupenvs-wdupenvs"></a>_dupenv_s, _wdupenv_s

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

*buffer*<br/>
Буфер для хранения значения переменной.

*numberOfElements*<br/>
Размер *буфера*.

*varname*<br/>
Имя переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном выполнении, код ошибки при сбое.

Эти функции проверяют свои параметры; Если *буфера* или *varname* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, функции задают **errno** для **EINVAL** и возвращают **EINVAL**.

Если эти функции не может выделить достаточно памяти, они задают *буфера* для **NULL** и *numberOfElements* значение 0 и возвращают **ENOMEM**.

## <a name="remarks"></a>Примечания

**_Dupenv_s** функция выполняет поиск в списке переменных среды для *varname*. Если переменная найдена, **_dupenv_s** выделяет буфер и копирует значение переменной в буфер. Адрес и длина буфера возвращаются в *буфера* и *numberOfElements*. Путем выделения буфера, **_dupenv_s** более удобным, чем [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!NOTE]
> Ответственность за освобождение памяти путем вызова функции [free](free.md) лежит на вызывающей программе.

Если переменная не найдена, затем *буфера* равно **NULL**, *numberOfElements* имеет значение 0, и возвращаемое значение равно 0, поскольку в этой ситуации не рассматривается как ошибка условие.

Если вас не интересует размер буфера можно передать **NULL** для *numberOfElements*.

**_dupenv_s** регистр не учитывается в операционной системе Windows. **_dupenv_s** использует копию среды, на который указывает глобальная переменная **_environ** для доступа к среде. См. в примечаниях [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) обсуждение **_environ**.

Значение в *буфера* является копией значения переменной среды; его изменение не оказывает влияния на среду. Чтобы изменить значение переменной среды, используйте функцию [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md).

**_wdupenv_s** — это двухбайтовая версия **_dupenv_s**; аргументы **_wdupenv_s** представляют собой строки расширенных символов. **_Wenviron** глобальная переменная — это двухбайтовая версия **_environ**. См. в примечаниях [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) для получения дополнительных сведений о **_wenviron**.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h>|
|**_wdupenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Константы среды](../../c-runtime-library/environmental-constants.md)<br/>
[_dupenv_s_dbg, _wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
