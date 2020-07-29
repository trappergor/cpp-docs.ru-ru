---
title: '&lt;оператор operator (Microsoft:: WRL)'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: b438f823814e21e2da43f698471d782c88626628
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226884"
---
# <a name="operatorlt-operator-microsoftwrl"></a>&lt;оператор operator (Microsoft:: WRL)

Определяет, является ли адрес одного объекта меньше другого.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>Параметры

*конкретного*<br/>
Левый объект.

*&*<br/>
Правый объект.

## <a name="return-value"></a>Возвращаемое значение

**`true`** Если адрес *меньше, чем* адрес *b*; в противном случае — **`false`** .

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также статью

[Пространство имен Microsoft:: WRL](microsoft-wrl-namespace.md)
