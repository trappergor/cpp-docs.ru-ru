---
title: _variant_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
ms.openlocfilehash: 4b19e3c1615912550cdf1eb6a2b0b3f906ee4af9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522334"
---
# <a name="varianttdetach"></a>_variant_t::Detach

**Блок, относящийся только к системам Microsoft**

Отключает инкапсулированный `VARIANT` из данного `_variant_t` объекта.

## <a name="syntax"></a>Синтаксис

```
VARIANT Detach( );
```

## <a name="return-value"></a>Возвращаемое значение

Инкапсулированный `VARIANT`.

## <a name="remarks"></a>Примечания

Извлекает и возвращает инкапсулированный `VARIANT`, а затем очищает данный `_variant_t` объекта без его удаления. Эта функция-член удаляет `VARIANT` из инкапсуляции и задает `VARTYPE` этого `_variant_t` объекта значение VT_EMPTY. Вы выпуске возвращаемого `VARIANT` путем вызова [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear) функции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)