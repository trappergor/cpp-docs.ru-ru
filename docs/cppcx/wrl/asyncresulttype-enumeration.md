---
title: AsyncResultType - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: d3f99fa85a777ae8361ed6f7cb82fe97ddd8d667
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028058"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType - перечисление

Указывает тип результата, возвращенный `GetResults()` метод.

## <a name="syntax"></a>Синтаксис

```cpp
enum AsyncResultType;
```

## <a name="members"></a>Участники

### <a name="values"></a>Значения

|name|Описание|
|----------|-----------------|
|`MultipleResults`|Набор нескольких результатов, которые представлены постепенно между `Start` состояние и перед `Close()` вызывается.|
|`SingleResult`|Один результат, который представлен после `Complete` событием.|

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)