---
title: "iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
dev_langs: C++
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
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 839e02d84255c1604d83228682f36a45d9d7e609
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="iscsym-iscsymf-iscsym-iswcsym-iscsymf-iswcsymf-iscsyml-iswcsyml-iscsymfl-iswcsymfl"></a>iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l

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

*c*  
Проверяемое целое число. *c* должно быть в диапазоне от 0 до 255 для узких символов версии функции.

*locale*  
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Оба `__iscsym` и `__iswcsym` возвращает ненулевое значение, если *c* — это буква, символ подчеркивания или цифра. Оба `__iscsymf` и `__iswcsymf` возвращает ненулевое значение, если *c* буквы или символа подчеркивания. Каждая из этих подпрограмм возвращает 0, если *c* не удовлетворяет условию теста. Версии этих функций с `_l` суффиксом идентичны, за исключением того, что они используют *языкового стандарта* их поведения, зависящего от языкового стандарта, переданный вместо текущего языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Примечания

Эти подпрограммы реализуются в виде макросов за исключением случаев, когда определен макрос препроцессора _CTYPE_DISABLE_MACROS. При использовании версий этих подпрограмм, реализованных в виде макроса, аргументы могут вычисляться несколько раз. При использовании выражений со списками аргументов следует соблюдать осторожность.

Для обеспечения обратной совместимости `iscsym` и `iscsymf` определены как макросы только если [&#95; &#95; Директива STDC &#95; &#95; ](../../preprocessor/predefined-macros.md) не определено или задано значение 0; в противном случае они определены.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, `_iswcsymf_l`|C: \<ctype.h><br /><br /> C++: \<cctype> или \<ctype.h>|

Подпрограммы `iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l` и `_iswcsymf_l` относятся только к системам Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)   
[Языковой стандарт](../../c-runtime-library/locale.md)   
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)