---
title: Оператор ComPtrRefBase::operator IInspectable ** | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs:
- C++
helpviewer_keywords:
- operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4683305b9f7f396168bd9404f6f2501502db3d01
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645026"
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>ComPtrRefBase::operator IInspectable\* \* оператор

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>Примечания

Приводит текущие [ptr_](../windows/comptrrefbase-ptr-data-member.md) данные-член в указатель к a указатель to `IInspectable` интерфейс.

Ошибка создается в том случае, если текущий **ComPtrRefBase** не является производным от `IInspectable`.

Это приведение доступна только если `__WRL_CLASSIC_COM__` определен.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также
[Comptrrefbase-класс](../windows/comptrrefbase-class.md)   
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)