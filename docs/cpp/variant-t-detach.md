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
ms.openlocfilehash: 719852c4556291747b612d54c44d4bf82caa9188
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519010"
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

Извлекает и возвращает инкапсулированный `VARIANT`, а затем очищает данный `_variant_t` объекта без его удаления. Эта функция-член удаляет `VARIANT` из инкапсуляции и задает `VARTYPE` этого `_variant_t` объекта значение VT_EMPTY. Вы выпуске возвращаемого `VARIANT` путем вызова [VariantClear](/windows/desktop/api/oleauto/nf-oleauto-variantclear) функции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)