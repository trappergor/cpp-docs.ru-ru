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
ms.openlocfilehash: 510267c7ab00fe22a93dc01342def5fc262ddb04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166222"
---
# <a name="varianttattach"></a>_variant_t::Attach

**Блок, относящийся только к системам Microsoft**

Присоединяет `VARIANT` в коллекцию **_variant_t** объекта.

## <a name="syntax"></a>Синтаксис

```
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>Параметры

*varSrc*<br/>
Объект `VARIANT` объекта должны быть присоединены к это **_variant_t** объекта.

## <a name="remarks"></a>Примечания

Принимает владельца `VARIANT` , инкапсулируя его. Эта функция-член освобождает все существующие инкапсулированные объекты `VARIANT`, затем копирует переданный `VARIANT`и задает его `VARTYPE` значение VT_EMPTY для убедитесь, что его ресурсы можно освободить только **_variant_t** деструктор.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)