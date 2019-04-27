---
title: оператор&lt; оператор (Microsoft::WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: 4887a7ebf3906edbc4a5a2a723caff0ad7732c46
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182929"
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

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)