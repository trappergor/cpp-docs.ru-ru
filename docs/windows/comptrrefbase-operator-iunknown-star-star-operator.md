---
title: Оператор ComPtrRefBase::operator IUnknown ** | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs:
- C++
helpviewer_keywords:
- operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 839b0220497db7ff0355ea7ed3ab923126e3175e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420937"
---
# <a name="comptrrefbaseoperator-iunknown-operator"></a>Оператор ComPtrRefBase::operator IUnknown**

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
operator IUnknown**() const;
```

## <a name="remarks"></a>Примечания

Приводит текущие [ptr_](../windows/comptrrefbase-ptr-data-member.md) данные-член в указатель к a указатель to `IUnknown` интерфейс.

Ошибка создается в том случае, если текущий **ComPtrRefBase** не является производным от `IUnknown`.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс ComPtrRefBase](../windows/comptrrefbase-class.md)<br/>
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)