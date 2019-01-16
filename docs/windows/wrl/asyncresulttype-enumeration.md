---
title: AsyncResultType - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: 309ed876c71f453336ecc2ed10eedc07f2a80be8
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336495"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType - перечисление

Указывает тип результата, возвращенный `GetResults()` метод.

## <a name="syntax"></a>Синтаксис

```cpp
enum AsyncResultType;
```

## <a name="members"></a>Участники

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`MultipleResults`|Набор нескольких результатов, которые представлены постепенно между `Start` состояние и перед `Close()` вызывается.|
|`SingleResult`|Один результат, который представлен после `Complete` событием.|

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)