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
ms.openlocfilehash: 933d332ce2653fd8ea907a5fafda524ae0220906
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409003"
---
# <a name="hstringreferenceoperator-operator"></a>Оператор HStringReference::Operator=

Перемещает значение другого **HStringReference** объект с текущим **HStringReference** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
HStringReference& operator=(HStringReference&& other) throw()  
```

### <a name="parameters"></a>Параметры

*other*<br/>
Существующий **HStringReference** объекта.

## <a name="remarks"></a>Примечания

Значение существующего *других* объект копируется в текущий **HStringReference** объекта, а затем *других* уничтожении объекта.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HStringReference](../windows/hstringreference-class.md)