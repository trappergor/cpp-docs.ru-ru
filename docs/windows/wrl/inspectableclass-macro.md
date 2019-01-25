---
title: Макрос InspectableClass
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: cedf395ae98a423e0335851327b5fdda1a4bc7d6
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893279"
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