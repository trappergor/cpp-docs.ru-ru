---
title: vector&lt;bool&gt;::reference::operator bool | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00ccd9e9ffbab78534c5b6417b7567ba03d007ab
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963684"
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
