---
title: toascii, __toascii | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __toascii
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
dev_langs:
- C++
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cead516a7e298e56d13d8f1a09a054057796ca64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408426"
---
# <a name="toascii-toascii"></a>toascii, __toascii

Преобразуют символы в 7-разрядный код ASCII методом усечения.

## <a name="syntax"></a>Синтаксис

```C
int __toascii(
   int c
);
#define toascii __toascii
```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ для преобразования.

## <a name="return-value"></a>Возвращаемое значение

**__toascii** преобразует значение *c* в 7-битной кодировке ASCII в диапазоне и возвращает результат. Возвращаемое значение для указания ошибки не зарезервировано.

## <a name="remarks"></a>Примечания

**__Toascii** подпрограммы преобразует данный символ в символ в кодировке ASCII, обрезано до 7 бит низкого порядка. Никакие другие преобразования не применяются.

**__Toascii** определяется как макрос не определен макрос препроцессора _CTYPE_DISABLE_MACROS. Для обеспечения обратной совместимости **toascii** определяется как макрос только если [ &#95; &#95;директива STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) не определено или задано значение 0; в противном случае значение не определено.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**toascii**, **__toascii**|C: \<ctype.h><br /><br /> C++: \<cctype> или \<ctype.h>|

**Toascii** макрос является расширением POSIX и **__toascii** является реализацией Майкрософт расширения POSIX. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
[Функции to](../../c-runtime-library/to-functions.md)<br/>
