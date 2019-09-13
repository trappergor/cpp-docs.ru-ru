---
title: Макрос InspectableClass
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: ee2a76edb967923a03ce6720b4163baf1cc48c32
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500481"
---
# <a name="inspectableclass-macro"></a>Макрос InspectableClass

Задает имя класса среды выполнения и уровень доверия.

## <a name="syntax"></a>Синтаксис

```cpp
InspectableClass(
   runtimeClassName,
   trustLevel)
```

### <a name="parameters"></a>Параметры

*рунтимекласснаме*<br/>
Полное текстовое имя класса среды выполнения.

*trustLevel*<br/>
Одно из перечисляемых значений [TrustLevel](/windows/win32/api/inspectable/ne-inspectable-trustlevel) .

## <a name="remarks"></a>Примечания

Макрос **InspectableClass** можно использовать только с типами среда выполнения Windows.

## <a name="requirements"></a>Требования

**Заголовок:** Implements. h

**Пространство имен:** Microsoft:: WRL

## <a name="see-also"></a>См. также

[Класс RuntimeClass](runtimeclass-class.md)