---
title: Оператор HStringReference::Operator =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7045229cc15304a88253f97e1ad3c9f171f139a0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597132"
---
# <a name="hstringreferenceoperator-operator"></a>Оператор HStringReference::Operator=

Перемещает значение другого **HStringReference** объект с текущим **HStringReference** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
HStringReference& operator=(HStringReference&& other) throw()  
```

### <a name="parameters"></a>Параметры

*other*  
Существующий **HStringReference** объекта.

## <a name="remarks"></a>Примечания

Значение существующего *других* объект копируется в текущий **HStringReference** объекта, а затем *других* уничтожении объекта.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HStringReference](../windows/hstringreference-class.md)