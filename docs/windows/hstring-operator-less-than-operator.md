---
title: Оператор HString::Operator&lt; оператора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs:
- C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa4a10235f37a3ea174965ad56f63d078e3cbde2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403595"
---
# <a name="hstringoperatorlt-operator"></a>Оператор HString::Operator&lt; оператор

Указывает, является ли первый параметр меньше значения второго параметра.

## <a name="syntax"></a>Синтаксис

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()  
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый параметр для сравнения. *LHS* можно ссылаться на **HString**.

*правая часть*<br/>
Второй параметр для сравнения. *правая часть* можно ссылаться на **HString**.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* параметр меньше, чем *rhs* параметра; в противном случае **false**.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)