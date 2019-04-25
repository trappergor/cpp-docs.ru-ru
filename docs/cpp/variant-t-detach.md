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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165935"
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