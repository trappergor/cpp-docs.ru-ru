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
ms.openlocfilehash: 8426c80af04b2c0906af150ea3e91304335e9f69
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500562"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Блок, относящийся только к системам Microsoft**

Отсоединяет инкапсулированный `VARIANT` объект от этого `_variant_t` объекта.

## <a name="syntax"></a>Синтаксис

```
VARIANT Detach( );
```

## <a name="return-value"></a>Возвращаемое значение

Инкапсулированный `VARIANT`.

## <a name="remarks"></a>Примечания

Извлекает и возвращает инкапсулированный `VARIANT`, а затем очищает этот `_variant_t` объект без его уничтожения. Эта функция члена удаляет `VARIANT` из инкапсуляции и `VARTYPE` задает для этого `_variant_t` объекта значение VT_EMPTY. Для освобождения возвращаемого `VARIANT` метода необходимо вызвать функцию [вариантклеар](/windows/win32/api/oleauto/nf-oleauto-variantclear) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)