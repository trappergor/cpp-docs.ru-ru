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
ms.openlocfilehash: b07df3dc50704a87883e1a387fe9c842c1732b54
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610537"
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

*lhs*  
Первый параметр для сравнения. *LHS* может быть **HStringReference** объекта или дескриптором HSTRING.

*правая часть*  
Второй параметр для сравнения.  *правая часть* может быть **HStringReference** объекта или дескриптором HSTRING.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* и *rhs* параметры равны; в противном случае — значение **false**.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HStringReference](../windows/hstringreference-class.md)