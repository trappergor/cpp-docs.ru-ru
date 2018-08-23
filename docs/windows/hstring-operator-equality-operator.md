---
title: Оператор HString::Operator ==-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
dev_langs:
- C++
ms.assetid: 77ff4c1a-e62a-4256-bf9d-0f017137c630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed3a93ac964841028b252aa09a6b70c18ed202e9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602992"
---
# <a name="hstringoperator-operator"></a>Оператор HString::Operator==

Указывает, равны ли два параметра.

## <a name="syntax"></a>Синтаксис

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>Параметры

*lhs*  
Первый параметр для сравнения. *LHS* может быть **HString** или `HStringReference` объекта или дескриптором HSTRING.

*правая часть*  
Второй параметр для сравнения. *rhs* может быть **HString** или `HStringReference` объекта или дескриптором HSTRING.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* и *rhs* параметры равны; в противном случае — значение **false**.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)