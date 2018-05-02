---
title: _setmbcp | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _setmbcp
- setmbcp
dev_langs:
- C++
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e879d4cf6ebc7cb7f61199b3bb52f1a5e3f5389
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="setmbcp"></a>_setmbcp

Задает новую многобайтовую кодовую страницу.

## <a name="syntax"></a>Синтаксис

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>Параметры

*Кодовая страница*<br/>
Новая кодовая страница для независимых от языкового стандарта многобайтовых подпрограмм.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если кодовая страница задана успешно. Если указано недопустимое значение кодовой страницы для *кодовую страницу*, возвращает -1 и кодовой страницы не изменяется. Наборы **errno** для **EINVAL** Если происходит сбой выделения памяти.

## <a name="remarks"></a>Примечания

**_Setmbcp** функция задает новую многобайтовую кодовую страницу. По умолчанию система времени выполнения автоматически устанавливает в качестве многобайтовой кодовой страницы кодовую страницу ANSI, используемую в системе по умолчанию. Заданная многобайтовая кодовая страница влияет на все не зависящие от языкового стандарта подпрограммы. Однако можно дать **_setmbcp** использовать кодовую страницу, определенную для текущего языкового стандарта (см. следующий список констант манифеста и соответствующих результатов поведения). Список подпрограмм, которые зависят от кодовой страницей языкового стандарта, а не от многобайтовой кодовой страницы, см. в разделе [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Многобайтовая кодовая страница также влияет на обработку многобайтовых символов следующими подпрограммами библиотеки времени выполнения:

||||
|-|-|-|
|[Функции _exec](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[Функции _spawn](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Кроме того, все подпрограммы библиотеки времени выполнения, которые получают многобайтовых символов *argv* или *envp* аргументы в качестве параметров программы (такие как **_exec** и **_spawn** семейств) обрабатывают эти строки в соответствии с многобайтовой кодовой страницей. Таким образом, эти процедуры также изменяется путем вызова **_setmbcp** , изменяющий многобайтовую кодовую страницу.

*Кодовую страницу* аргумент может быть присвоено любое из следующих значений:

- **_MB_CP_ANSI** кодовую страницу ANSI использования, полученная от операционной системы при запуске программы.

- **_MB_CP_LOCALE** используется кодовая страница текущего языкового стандарта, полученная из предыдущего вызова [setlocale](setlocale-wsetlocale.md).

- **_MB_CP_OEM** кодовую страницу OEM использования, полученная от операционной системы при запуске программы.

- **_MB_CP_SBCS** используется Однобайтовая кодовая страница. Если значение кодовой страницы **_MB_CP_SBCS**, подпрограммы, подобные [_ismbblead](ismbblead-ismbblead-l.md) всегда возвращает значение false.

- Любая другая допустимая кодовая страница, независимо от того, является ли значение ANSI, OEM или другой поддерживаемой операционной системой кодовой страницей (за исключением UTF-7 и UTF-8, которые не поддерживаются).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
