---
title: Метод Module::Terminate | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Terminate
dev_langs:
- C++
helpviewer_keywords:
- Terminate method
ms.assetid: cf358117-45dc-43c7-ac1e-1e1eedc59e41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 76f483c1c57c65c035bcbb0f8c82b4f72cbb06f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398734"
---
# <a name="moduleterminate-method"></a>Метод Module::Terminate

Приводит к завершению работы всех экземпляров фабрик, созданных модулем.

## <a name="syntax"></a>Синтаксис

```cpp
void Terminate();
```

## <a name="remarks"></a>Примечания

Освобождает фабрики в кэше.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](../windows/module-class.md)