---
title: 'RoInitializeWrapper:: ~ RoInitializeWrapper деструктор | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
dev_langs:
- C++
ms.assetid: afef4c1f-ffde-4cd2-8654-8de4182eb5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5548eb413f0d5cd4c72983e00bdf65f61bb98f6d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597927"
---
# <a name="roinitializewrapperroinitializewrapper-destructor"></a>Деструктор RoInitializeWrapper::~RoInitializeWrapper

Отменяет инициализацию среды выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
~RoInitializeWrapper()  
```

## <a name="remarks"></a>Примечания

**RoInitializeWrapper** класс вызывает `Windows::Foundation::Uninitialize()`.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HandleT](../windows/handlet-class.md)