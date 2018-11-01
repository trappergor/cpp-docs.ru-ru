---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: affaefd8af4802836733587af62977171ba01410
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537804"
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach

**Блок, относящийся только к системам Microsoft**

Извлекает и возвращает инкапсулированный указатель на интерфейс.

## <a name="syntax"></a>Синтаксис

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>Примечания

Извлекает и возвращает инкапсулированный указатель на интерфейс и затем очищает область хранения инкапсулированного указателя в значение NULL. Поэтому указатель на интерфейс удаляется из инкапсуляции. Это следует вызвать метод `Release` на возвращаемый указатель интерфейса.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)