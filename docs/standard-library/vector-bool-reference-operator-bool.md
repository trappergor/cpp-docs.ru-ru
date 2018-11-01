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
ms.openlocfilehash: 7fa95b3037538ccbbf27fa5b9749dc21f72670cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492704"
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

Предоставляет неявное преобразование из `vector<bool>::reference` для **bool**.

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

[вектор\<bool >:: ссылаться на класс](../standard-library/vector-bool-reference-class.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
