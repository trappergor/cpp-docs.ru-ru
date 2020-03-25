---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: 0cd300a09c29668c496d93109d1bc862947e948c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187561"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Блок, относящийся только к системам Microsoft**

Присваивает строку данному объекту `_variant_t`.

## <a name="syntax"></a>Синтаксис

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Параметры

*pSrc*<br/>
Указатель на строку знаков.

## <a name="remarks"></a>Remarks

Преобразует символьную строку ANSI в строку `BSTR` Юникода и присваивает ее данному объекту `_variant_t`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _variant_t](../cpp/variant-t-class.md)
