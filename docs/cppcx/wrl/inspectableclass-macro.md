---
title: Макрос InspectableClass
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: cedf395ae98a423e0335851327b5fdda1a4bc7d6
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58786092"
---
# <a name="inspectableclass-macro"></a>Макрос InspectableClass

Задает уровень имя и доверия класса среды выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
InspectableClass(
   runtimeClassName,
   trustLevel)
```

### <a name="parameters"></a>Параметры

*runtimeClassName*<br/>
Полное текстовое имя класса среды выполнения.

*trustLevel*<br/>
Один из [TrustLevel](/windows/desktop/api/inspectable/ne-inspectable-trustlevel) значений перечисления.

## <a name="remarks"></a>Примечания

**InspectableClass** макрос может использоваться только с типами среды выполнения Windows.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс RuntimeClass](runtimeclass-class.md)