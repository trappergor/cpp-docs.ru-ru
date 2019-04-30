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
ms.openlocfilehash: e0d26247868440f47c73422510ac0e998f8e8dee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403299"
---
# <a name="variantt-relational-operators"></a>Операторы отношения _variant_t

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

*varSrc*<br/>
Объект `VARIANT` для сравнения с `_variant_t` объекта.

*pSrc*<br/>
Указатель на `VARIANT` для сравнения с `_variant_t` объекта.

## <a name="return-value"></a>Возвращаемое значение

Возвращает **true** если содержит сравнение, **false** в противном случае.

## <a name="remarks"></a>Примечания

Сравнивает `_variant_t` со `VARIANT`, проверки равенства или неравенства.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)