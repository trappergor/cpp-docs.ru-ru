---
title: Оператор HStringReference::Operator ==-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
dev_langs:
- C++
ms.assetid: cad3d52d-cd67-4194-a270-5239b1121a09
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e369aa819c7bff372113b2e422fef2441485a85a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381379"
---
# <a name="hstringreferenceoperator-operator"></a>Оператор HStringReference::Operator==

Указывает, равны ли два параметра.

## <a name="syntax"></a>Синтаксис

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый параметр для сравнения. *LHS* может быть **HStringReference** объекта или дескриптором HSTRING.

*правая часть*<br/>
Второй параметр для сравнения.  *правая часть* может быть **HStringReference** объекта или дескриптором HSTRING.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* и *rhs* параметры равны; в противном случае — значение **false**.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HStringReference](../windows/hstringreference-class.md)