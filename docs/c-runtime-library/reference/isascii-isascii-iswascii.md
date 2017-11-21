---
title: "isascii, __isascii, iswascii | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iswascii
- __isascii
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
dev_langs: C++
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6f321411fca27d22540d4dc63c56774522b04a5e
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="isascii-isascii-iswascii"></a>isascii, __isascii, iswascii

Определяет, является ли определенный символ символом ASCII.

## <a name="syntax"></a>Синтаксис

```C
int __isascii(
   int c
);
int iswascii(
   wint_t c
);

#define isascii __isascii
```

### <a name="parameters"></a>Параметры

*c*  
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих подпрограмм возвращает отличное от нуля значение, если `c` — конкретное представление символа ASCII. `__isascii`возвращает ненулевое значение, если `c` является символ ASCII (в диапазоне от 0x00 — 0x7F). `iswascii` возвращает ненулевое значение, если `c` является представлением символа ASCII в виде расширенного символа. Каждая из этих подпрограмм возвращает 0, если `c` не удовлетворяет проверяемому условию.

## <a name="remarks"></a>Примечания

`__isascii` и `iswascii` реализуются в виде макросов за исключением случаев, когда определен макрос препроцессора _CTYPE_DISABLE_MACROS.

Для обеспечения обратной совместимости `isascii` реализуется как макрос, только если [&#95; &#95; Директива STDC &#95; &#95; ](../../preprocessor/predefined-macros.md) не определено или задано значение 0; в противном случае значение не определено.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`isascii`, `__isascii`|C: \<ctype.h><br /><br /> C++: \<cctype> или \<ctype.h>|
|`iswascii`|C: \<wctype.h>, \<ctype.h> или \<wchar.h><br /><br /> C++: \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h> или \<wchar.h>|

Функции `isascii`, `__isascii` и `iswascii` относятся только к системам Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)   
[Языковой стандарт](../../c-runtime-library/locale.md)   
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)