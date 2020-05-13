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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 18712661b2bda1eaaf0c583b922ad73a781b4abc
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918829"
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

*страница*<br/>
Новая кодовая страница для независимых от языкового стандарта многобайтовых подпрограмм.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если кодовая страница задана успешно. Если для *кодовой*страницы указана недопустимая кодовая страница, функция возвращает значение-1, а параметр Кодовая страница не изменяется. Устанавливает **значение** **еинвал** , если происходит сбой выделения памяти.

## <a name="remarks"></a>Remarks

Функция **_setmbcp** указывает новую многобайтовую кодовую страницу. По умолчанию система времени выполнения автоматически устанавливает в качестве многобайтовой кодовой страницы кодовую страницу ANSI, используемую в системе по умолчанию. Заданная многобайтовая кодовая страница влияет на все не зависящие от языкового стандарта подпрограммы. Однако можно указать **_setmbcp** использовать кодовую страницу, определенную для текущего языкового стандарта (см. следующий список констант манифеста и связанные результаты поведения). Список подпрограмм, которые зависят от кодовой страницей языкового стандарта, а не от многобайтовой кодовой страницы, см. в разделе [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Многобайтовая кодовая страница также влияет на обработку многобайтовых символов следующими подпрограммами библиотеки времени выполнения:

||||
|-|-|-|
|[Функции _exec](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[Функции _spawn](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Кроме того, все подпрограммы библиотеки времени выполнения, которые получают аргументы многобайтовых *argv* или *envp* в качестве параметров (например, семейства **_exec** и **_spawn** ), обрабатывают эти строки в соответствии с многобайтовой кодовой страницей. Поэтому на эти подпрограммы также влияет вызов **_setmbcp** , который изменяет многобайтовую кодовую страницу.

Аргумент *codepage* может принимать любое из следующих значений:

- **_MB_CP_ANSI** Используйте кодовую страницу ANSI, полученную из операционной системы при запуске программы.

- **_MB_CP_LOCALE** Использовать кодовую страницу текущего языкового стандарта, полученную при предыдущем вызове [setlocale](setlocale-wsetlocale.md).

- **_MB_CP_OEM** Используйте кодовую страницу OEM, полученную из операционной системы при запуске программы.

- **_MB_CP_SBCS** Использовать однобайтовую кодовую страницу. Если кодовая страница имеет значение **_MB_CP_SBCS**, то такая подпрограмма, как [_ismbblead](ismbblead-ismbblead-l.md) , всегда возвращает значение false.

- **_MB_CP_UTF8** Используйте UTF-8.  Если кодовая страница имеет значение **_MB_CP_UTF8**, то такая подпрограмма, как [_ismbblead](ismbblead-ismbblead-l.md) , всегда возвращает значение false.

- Любое другое допустимое значение кодовой страницы, независимо от того, является ли значение ANSI, OEM или другой поддерживаемой операционной системой кодовой страницей (кроме UTF-7, которая не поддерживается).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
