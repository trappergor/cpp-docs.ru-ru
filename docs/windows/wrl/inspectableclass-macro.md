---
title: Макрос InspectableClass
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: bdc3dc5b54aa28280f22b1481a9be20ee0be22c6
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336760"
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
Один из [TrustLevel](https://msdn.microsoft.com/library/br224625.aspx) значений перечисления.

## <a name="remarks"></a>Примечания

**InspectableClass** макрос может использоваться только с типами среды выполнения Windows.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс RuntimeClass](runtimeclass-class.md)