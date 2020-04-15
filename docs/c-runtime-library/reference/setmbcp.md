---
title: _setmbcp
ms.date: 4/2/2020
api_name:
- _setmbcp
- _o__setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _setmbcp
- setmbcp
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
ms.openlocfilehash: 61086471c6194aaa8434d291647978bf891a8aea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337593"
---
# <a name="_setmbcp"></a>_setmbcp

Задает новую многобайтовую кодовую страницу.

## <a name="syntax"></a>Синтаксис

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>Параметры

*Codepage*<br/>
Новая кодовая страница для независимых от языкового стандарта многобайтовых подпрограмм.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если кодовая страница задана успешно. Если для *страницы кода*поставляется недействительное значение страницы кода, возвращается -1, а настройка страницы кода остается неизменной. Устанавливает **errno** в **EINVAL,** если происходит сбой выделения памяти.

## <a name="remarks"></a>Remarks

Функция **_setmbcp** определяет новую страницу мультибайтного кода. По умолчанию система времени выполнения автоматически устанавливает в качестве многобайтовой кодовой страницы кодовую страницу ANSI, используемую в системе по умолчанию. Заданная многобайтовая кодовая страница влияет на все не зависящие от языкового стандарта подпрограммы. Однако можно поручить **_setmbcp** использовать страницу кода, определенную для текущего локализации (см. следующий список констант и связанных с ними результатов поведения). Список подпрограмм, которые зависят от кодовой страницей языкового стандарта, а не от многобайтовой кодовой страницы, см. в разделе [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Многобайтовая кодовая страница также влияет на обработку многобайтовых символов следующими подпрограммами библиотеки времени выполнения:

||||
|-|-|-|
|[Функции _exec](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[Функции _spawn](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Кроме того, все процедуры библиотеки времени выполнения, которые получают *аргументы мультибайт-символа argv* или *envp* в качестве параметров (например, **_exec** и **_spawn** семейства), обрабатывают эти строки в соответствии со страницей мультибайта кода. Таким образом, на эти процедуры также влияет призыв к **_setmbcp,** изменяющие страницу мультибайтного кода.

Аргумент *кодирования* может быть установлен на любое из следующих значений:

- **_MB_CP_ANSI** Используйте страницу кода ANSI, полученную от операционной системы при запуске программы.

- **_MB_CP_LOCALE** Используйте страницу кода текущего локализации, полученную от предыдущего вызова для [установки.](setlocale-wsetlocale.md)

- **_MB_CP_OEM** Используйте страницу Кода OEM, полученную от операционной системы при запуске программы.

- **_MB_CP_SBCS** Используйте страницу кода с одним байтом. Когда страница кода установлена на **_MB_CP_SBCS,** рутина, такая как [_ismbblead](ismbblead-ismbblead-l.md) всегда возвращается ложно.

- **_MB_CP_UTF8** Используйте UTF-8.  Когда страница кода установлена на **_MB_CP_UTF8,** рутина, такая как [_ismbblead](ismbblead-ismbblead-l.md) всегда возвращается ложно.

- Любое другое допустимое значение страницы кода, независимо от того, является ли значение ANSI, OEM или другой страницею кода, поддерживаемой операционной системой (кроме UTF-7, которая не поддерживается).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
