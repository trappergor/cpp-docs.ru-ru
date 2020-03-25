---
title: _variant_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
ms.openlocfilehash: 3792ed4d0fcd86c4a4e846771c450413fda130b5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187769"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Блок, относящийся только к системам Microsoft**

Присоединяет объект `VARIANT` к объекту **_variant_t** .

## <a name="syntax"></a>Синтаксис

```
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>Параметры

*варсрк*<br/>
Объект `VARIANT` для присоединения к этому **_variant_t** объекту.

## <a name="remarks"></a>Remarks

Принимает владение `VARIANT`, инкапсулирует его. Эта функция члена освобождает все существующие инкапсулированные `VARIANT`, затем копирует предоставленный `VARIANT`и задает для его `VARTYPE` значение VT_EMPTY, чтобы гарантировать, что его ресурсы могут быть освобождены только деструктором **_variant_t** .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _variant_t](../cpp/variant-t-class.md)
