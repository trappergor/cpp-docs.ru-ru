---
title: ComPtrRef::operator ==-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator==
dev_langs:
- C++
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abf78644f7cad90d25d365f6237407aeaeb6917b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575707"
---
# <a name="comptrrefoperator-operator"></a>Оператор ComPtrRef::operator==

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)  
);

bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Параметры

*a*  
Ссылку на **ComPtrRef** объекта.

*b*  
Ссылка на другой **ComPtrRef** объект или указатель на анонимный тип (`void*`).

## <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает **true** Если объект *a* равен объекту *b*; в противном случае **false**.

Второй и третий операторы возвращают **true** Если объект *a* равен **nullptr**; в противном случае **false**.

Четвертый и пятый операторы yield **true** Если объект *a* равен объекту *b*; в противном случае **false**.

## <a name="remarks"></a>Примечания

Указывает ли два **ComPtrRef** объекты равны.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)  
[Класс ComPtrRef](../windows/comptrref-class.md)