---
title: Оператор ComPtrRefBase::operator IInspectable ** | Документы Microsoft
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
ms.openlocfilehash: e337f6bbc92718c839fc2bd12c9df9f0caa5d5aa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883463"
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>Оператор ComPtrRefBase::operator IInspectable**

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>Примечания

Приводит текущие [ptr_](../windows/comptrrefbase-ptr-data-member.md) данные-член к указателю к a указатель-интерфейс IInspectable.

Если текущий ComPtrRefBase не является производным от IInspectable, выдается ошибка.

Это приведение доступен, только если **&#95; &#95;WRL_CLASSIC_COM&#95; &#95;** определен.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Comptrrefbase-класс](../windows/comptrrefbase-class.md)   
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)