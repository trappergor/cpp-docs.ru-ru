---
title: Оператор ComPtr::operator ==-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator==
dev_langs:
- C++
ms.assetid: 6a26e936-29d4-4b7d-b44a-7c575ad07509
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24ca52eccc814b82e5f9bdd6ddac6458fb5992fe
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607140"
---
# <a name="comptroperator-operator"></a>Оператор ComPtr::operator==

Указывает ли два **ComPtr** объекты равны.

## <a name="syntax"></a>Синтаксис

```cpp
bool operator==(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator==(
   const ComPtr<T>& a,
   decltype(__nullptr)  
);

bool operator==(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Параметры

*a*  
Ссылку на **ComPtr** объекта.

*b*  
Ссылка на другой **ComPtr** объекта.

## <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает **true** Если объект *a* равен объекту *b*; в противном случае **false**.

Второй и третий операторы возвращают **true** Если объект *a* равен **nullptr**; в противном случае **false**.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)  
[Класс ComPtr](../windows/comptr-class.md)