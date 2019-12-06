---
title: iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l
ms.date: 11/04/2016
api_name:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _iswcsym_l
- _iswcsymf_l
- iscsymf
- iswcsymf
- __iswcsym
- __iswcsymf
- iscsym
- iswcsym
- __iscsym
- _iscsym_l
- _iscsymf_l
- __iscsymf
- ctype/iscsym
- ctype/iscsymf
- ctype/__iscsym
- ctype/__iscsymf
- ctype/__iscsym_l
- ctype/__iscsymf_l
- ctype/__iswcsym
- ctype/__iswcsymf
- ctype/__iswcsym_l
- ctype/__iswcsymf_l
helpviewer_keywords:
- iscsymf_l function
- iswsym_l function
- _iswcsym_l function
- iscsym_l function
- _iscsymf_l function
- _iswcsymf_l function
- _iscsym_l function
- __iscsym function
- __iswcsymf function
- iswsymf_l function
- __iscsymf function
- __iswcsym function
- iscsym function
- iscsymf function
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
ms.openlocfilehash: bc38e72818446a94a51a37b8df5c8c8582971b3f
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857766"
---
# <a name="iscsym-iscsymf-__iscsym-__iswcsym-__iscsymf-__iswcsymf-_iscsym_l-_iswcsym_l-_iscsymf_l-_iswcsymf_l"></a>iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l

Определяет, представляет ли целое число символ, который может использоваться в идентификаторе.

## <a name="syntax"></a>Синтаксис

```C
int __iscsym(
   int c
);
int __iswcsym(
   wint_t c
);
int __iscsymf(
   int c
);
int __iswcsymf(
   wint_t c
);
int _iscsym_l(
   int c,
   _locale_t locale
);
int _iswcsym_l(
   wint_t c,
   _locale_t locale
);
int _iscsymf_l(
   int c,
   _locale_t locale
);
int _iswcsymf_l(
   wint_t c,
   _locale_t locale
);
#define iscsym __iscsym
#define iscsymf __iscsymf
```

### <a name="parameters"></a>Параметры

*c*<br/>
Проверяемое целое число. значение *c* должно быть в диапазоне от 0-255 до версии с узким символом функции.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Как **__iscsym** , так и **__iswcsym** возвращают ненулевое значение, если *c* — буква, символ подчеркивания или цифра. Как **__iscsymf** , так и **__iswcsymf** возвращают ненулевое значение, если *c* — буква или символ подчеркивания. Каждая из этих подпрограмм возвращает 0, если *c* не удовлетворяет условию теста. Версии этих функций с суффиксом **_l** идентичны за исключением того, что они используют переданный *языковой стандарт* вместо текущего языкового стандарта для поведения, зависящего от языкового стандарта. Дополнительные сведения см. в разделе [Locale](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Заметки

Эти подпрограммы реализуются в виде макросов за исключением случаев, когда определен макрос препроцессора _CTYPE_DISABLE_MACROS. При использовании версий этих подпрограмм, реализованных в виде макроса, аргументы могут вычисляться несколько раз. При использовании выражений со списками аргументов следует соблюдать осторожность.

Для обеспечения обратной совместимости **исксим** и **исксимф** определяются как макросы только в том случае, если [ &#95; &#95;STDC&#95; ](../../preprocessor/predefined-macros.md) не определена или определена как 0. в противном случае они не определены.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**исксим**, **исксимф**, **__iscsym**, **__iswcsym**, **__iscsymf**, **__iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, **_iswcsymf_l**|C: \<ctype.h><br /><br /> C++: \<cctype> или \<ctype.h>|

Подпрограммы **исксим**, **исксимф**, **__iscsym**, **__iswcsym**, **__iscsymf** **,** **__Iswcsymf**, _iscsym_l **, _iswcsym_l, _iscsymf_l**и **_iswcsymf_l** являются специфичными для Microsoft. Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также:

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
