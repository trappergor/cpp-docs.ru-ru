---
title: Константа ArgTraitsHelper::args | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
dev_langs:
- C++
helpviewer_keywords:
- args constant
ms.assetid: 1c0efa32-c072-43e3-bbd9-a3f6aec069a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e4817d0f0082ef4ec0a9a588982405772d733fe0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598036"
---
# <a name="argtraitshelperargs-constant"></a>Константа ArgTraitsHelper::args

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
static const int args = Traits::args;
```

## <a name="remarks"></a>Примечания

Помогает [ArgTraitsHelper::args](../windows/argtraitshelper-args-constant.md) следить счетчик числа параметров `Invoke` метод для интерфейса делегата.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура ArgTraitsHelper](../windows/argtraitshelper-structure.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)