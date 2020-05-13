---
title: Операторы отношения _variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
ms.openlocfilehash: e0d7ea1a0bcaf8329cff0cdfb0c01154f3c5a73b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187574"
---
# <a name="_variant_t-relational-operators"></a>Операторы отношения _variant_t

**Блок, относящийся только к системам Microsoft**

Сравнивает два объекта `_variant_t` и определяет, равны ли они.

## <a name="syntax"></a>Синтаксис

```
bool operator==(
   const VARIANT& varSrc) const;
bool operator==(
   const VARIANT* pSrc) const;
bool operator!=(
   const VARIANT& varSrc) const;
bool operator!=(
   const VARIANT* pSrc) const;
```

#### <a name="parameters"></a>Параметры

*варсрк*<br/>
`VARIANT`, сравниваемый с объектом `_variant_t`.

*pSrc*<br/>
Указатель на `VARIANT`, сравниваемый с объектом `_variant_t`.

## <a name="return-value"></a>Возвращаемое значение

Возвращает **значение true** , если сравнение содержит, **значение false** , если нет.

## <a name="remarks"></a>Remarks

Сравнивает объект `_variant_t` с `VARIANT`, проверяя на равенство или неравенство.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _variant_t](../cpp/variant-t-class.md)
