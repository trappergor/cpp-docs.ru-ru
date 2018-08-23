---
title: Метод HandleT::Detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b66d5c65dd084da564067cd62242b315f6da182
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591378"
---
# <a name="handletdetach-method"></a>Метод HandleT::Detach

Отсоединяет текущий **HandleT** объект из его базовый дескриптор.

## <a name="syntax"></a>Синтаксис

```cpp
typename HandleTraits::Type Detach();
```

## <a name="return-value"></a>Возвращаемое значение

Базовый дескриптор.

## <a name="remarks"></a>Примечания

После завершения операции текущего **HandleT** присваивается недопустимое состояние.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HandleT](../windows/handlet-class.md)