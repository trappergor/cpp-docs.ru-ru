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
ms.openlocfilehash: cf539082ef88abb5fb27f09d92b73403dc2d03a5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611346"
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

*h*  
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