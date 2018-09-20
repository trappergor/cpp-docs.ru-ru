---
title: оператор&lt; оператор (Microsoft::WRL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
dev_langs:
- C++
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 077f21c92ea1d731b1427635ce5b60c45af0f5f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443362"
---
# <a name="operatorlt-operator-microsoftwrl"></a>оператор&lt; оператор (Microsoft::WRL)

Определяет, является ли адрес один объект меньше другого.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>Параметры

*a*<br/>
Левый объект.

*b*<br/>
Правый объект.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если адрес *a* меньше, чем адрес *b*; в противном случае **false**.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)