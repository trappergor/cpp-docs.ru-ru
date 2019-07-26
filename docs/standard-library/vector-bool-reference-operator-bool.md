---
title: vector&lt;bool&gt;::reference::operator bool
ms.date: 11/04/2016
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
ms.openlocfilehash: ca2d21a7706248cd84ca3591eb717e4081972f9c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452125"
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

Обеспечивает неявное преобразование `vector<bool>::reference` из в **bool**.

## <a name="syntax"></a>Синтаксис

```cpp
operator bool() const;
```

## <a name="return-value"></a>Возвращаемое значение

Логическое значение элемента объекта [vector\<bool>](../standard-library/vector-bool-class.md).

## <a name="remarks"></a>Примечания

Объект `vector<bool>` невозможно изменить при помощи данного оператора.

## <a name="requirements"></a>Требования

**Заголовок:** \<vector>

**Пространство имен:** std

## <a name="see-also"></a>См. также

Класс [vector\<bool>::reference](../standard-library/vector-bool-reference-class.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
