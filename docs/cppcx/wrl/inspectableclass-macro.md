---
title: Макрос InspectableClass
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: 9d194f5a87ac4a142301bc896cb3ed172f119473
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398201"
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