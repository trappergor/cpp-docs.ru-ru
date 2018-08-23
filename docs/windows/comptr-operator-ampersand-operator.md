---
title: Оператор ComPtr::operator&amp; оператора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f513ac83e0ee83109f42cf87b80b4fcc4960db1f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598607"
---
# <a name="comptroperatoramp-operator"></a>Оператор ComPtr::operator&amp; оператор

Освобождает интерфейс, связанный с данным **ComPtr** объекта, а затем извлекает адрес **ComPtr** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

## <a name="return-value"></a>Возвращаемое значение

Слабая ссылка на текущий **ComPtr**.

## <a name="remarks"></a>Примечания

Этот метод отличается от [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md) в том, что данный метод освобождает ссылку на указатель интерфейса. Используйте метод `ComPtr::GetAddressOf`, если необходим адрес указателя интерфейса, но этот интерфейс освобождать не требуется.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ComPtr](../windows/comptr-class.md)