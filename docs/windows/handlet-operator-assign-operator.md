---
title: HandleT::operator =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c6aeca188f51f35c739c32f5290aac011781b41
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396900"
---
# <a name="handletoperator-operator"></a>Оператор HandleT::operator=

Перемещает значение указанного **HandleT** объект с текущим **HandleT** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на дескриптор.

## <a name="return-value"></a>Возвращаемое значение

Ссылку на текущий **HandleT** объекта.

## <a name="remarks"></a>Примечания

Эта операция делает недействительным **HandleT** объекта, указанного параметром *h*.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HandleT](../windows/handlet-class.md)