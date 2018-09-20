---
title: Оператор ComPtr::operator! =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator!=
dev_langs:
- C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce6e3357582abe94fdc538932e49e773c37f116b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384701"
---
# <a name="comptroperator-operator"></a>Оператор ComPtr::operator!=

Указывает ли два **ComPtr** объекты не равны.

## <a name="syntax"></a>Синтаксис

```cpp
bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)  
);

bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Параметры

*a*<br/>
Ссылку на **ComPtr** объекта.

*b*<br/>
Ссылка на другой **ComPtr** объекта.

## <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает **true** Если объект *a* не равен объекту *b*; в противном случае **false**.

Второй и третий операторы возвращают **true** Если объект *a* не равно **nullptr**; в противном случае **false**.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)<br/>
[Класс ComPtr](../windows/comptr-class.md)