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
ms.openlocfilehash: 19e04f5415f9f7a736371c888dff7559df6c6c66
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462340"
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

Это приведение доступна только если **&#95; &#95;WRL_CLASSIC_COM&#95; &#95;** определен.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также
[Comptrrefbase-класс](../windows/comptrrefbase-class.md)   
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)