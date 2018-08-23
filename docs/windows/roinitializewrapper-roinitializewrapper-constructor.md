---
title: Конструктор RoInitializeWrapper::RoInitializeWrapper | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 528c66da24c4cbf6c22af5b1b5f8dd3afffff64f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604650"
---
# <a name="roinitializewrapperroinitializewrapper-constructor"></a>Конструктор RoInitializeWrapper::RoInitializeWrapper

Инициализирует новый экземпляр класса **RoInitializeWrapper** класса.

## <a name="syntax"></a>Синтаксис

```cpp
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```

### <a name="parameters"></a>Параметры

*flags*  
Одно из перечислений RO_INIT_TYPE, которые задает поддержку, предоставляемые средой выполнения Windows.

## <a name="remarks"></a>Примечания

**RoInitializeWrapper** класс вызывает `Windows::Foundation::Initialize(flags)`.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HandleT](../windows/handlet-class.md)