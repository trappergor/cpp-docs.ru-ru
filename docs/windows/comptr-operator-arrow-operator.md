---
title: Оператор ComPtr::operator -&gt; оператора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator->
dev_langs:
- C++
helpviewer_keywords:
- operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 417fd11017f9f70ee8cc247898e23741488ae5e7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599992"
---
# <a name="comptroperator-gt-operator"></a>Оператор ComPtr::operator -&gt; оператор

Извлекает указатель на тип, заданный текущим параметром шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на тип, заданный текущим именем типа шаблона.

## <a name="remarks"></a>Примечания

Эта вспомогательная функция удаляет лишнюю нагрузку, вызванную использованием макроса STDMETHOD. Эта функция делает `IUnknown` типы **частного** вместо **виртуального**.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ComPtr](../windows/comptr-class.md)