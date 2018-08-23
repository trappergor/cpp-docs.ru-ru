---
title: Оператор HStringReference::Operator! =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
dev_langs:
- C++
ms.assetid: 01ab6691-1fc7-4feb-85f0-fe795593a160
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 91ad2c531ffefa0ac832e63dffeaa2b292243cf6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596232"
---
# <a name="hstringreferenceoperator-operator"></a>Оператор HStringReference::O

Указывает, действительно ли два параметра не равны.

## <a name="syntax"></a>Синтаксис

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>Параметры

*lhs*  
Первый параметр для сравнения. *LHS* может быть **HStringReference** объекта или дескриптором HSTRING.

*правая часть*  
Второй параметр для сравнения.  *правая часть* может быть **HStringReference** объекта или дескриптором HSTRING.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* и *rhs* параметры не равны; в противном случае — значение **false**.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HStringReference](../windows/hstringreference-class.md)