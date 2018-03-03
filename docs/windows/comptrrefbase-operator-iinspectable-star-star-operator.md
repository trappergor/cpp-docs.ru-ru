---
title: "Оператор ComPtrRefBase::operator IInspectable ** | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs:
- C++
helpviewer_keywords:
- operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d83580537a81b1c75f44e32e6aa43b2b014c8373
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

Это приведение доступен, только если **&#95; &#95; WRL_CLASSIC_COM &#95; &#95;**  определен.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Comptrrefbase-класс](../windows/comptrrefbase-class.md)   
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)