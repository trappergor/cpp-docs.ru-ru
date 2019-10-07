---
title: toascii, __toascii
ms.date: 11/04/2016
api_name:
- __toascii
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
ms.openlocfilehash: 09df829511b38b87cb41e32a59bee9f38a9b8f32
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957464"
---
# <a name="toascii-__toascii"></a>toascii, __toascii

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

**__toascii** преобразует значение *c* в 7-разрядный диапазон ASCII и возвращает результат. Возвращаемое значение для указания ошибки не зарезервировано.

## <a name="remarks"></a>Примечания

Подпрограммы **__toascii** преобразуют заданный символ в символ ASCII, округляя его до 7 битов нижнего порядка. Никакие другие преобразования не применяются.

Подпрограммы **__toascii** определяются как макрос, если не определен макрос препроцессора _CTYPE_DISABLE_MACROS. В целях обратной совместимости **toascii** определяется как макрос, только если [ &#95; &#95;STDC&#95; ](../../preprocessor/predefined-macros.md) не определен или определен как 0. в противном случае он не определен.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**toascii**, **__toascii**|C: \<ctype.h><br /><br /> C++: \<cctype> или \<ctype.h>|

Макрос **toascii** является расширением POSIX, а **__toascii** — реализацией модуля POSIX для Microsoft. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
[Функции to](../../c-runtime-library/to-functions.md)<br/>
