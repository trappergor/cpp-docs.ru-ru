---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: d07e995be0ecd99974356a7516e7c4deee677637
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403273"
---
# <a name="varianttsetstring"></a>_variant_t::SetString

**Блок, относящийся только к системам Microsoft**

Присваивает строку данному объекту `_variant_t`.

## <a name="syntax"></a>Синтаксис

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Параметры

*pSrc*<br/>
Указатель на строку знаков.

## <a name="remarks"></a>Примечания

Преобразует символьную строку ANSI в строку `BSTR` Юникода и присваивает ее данному объекту `_variant_t`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)