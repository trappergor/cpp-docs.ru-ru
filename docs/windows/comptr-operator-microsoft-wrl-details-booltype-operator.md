---
title: 'Оператор ComPtr::operator:: Booltype | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 135c6d851be5de8f2eb976baf015f2ef449600c0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595977"
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>Оператор ComPtr::operator Microsoft::WRL::Details::BoolType

Указывает ли **ComPtr** управление временем существования объектов интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

## <a name="return-value"></a>Возвращаемое значение

Если интерфейс связан с данным **ComPtr**, адрес [BoolStruct::Member](../windows/boolstruct-member-data-member.md) данные-член; в противном случае **nullptr**.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ComPtr](../windows/comptr-class.md)  
[Метод ComPtr::Get](../windows/comptr-get-method.md)