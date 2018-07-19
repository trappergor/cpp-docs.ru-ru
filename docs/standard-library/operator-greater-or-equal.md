---
title: оператор&gt;= | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- operator>=
- std::>=
- std.operator>=
- '>='
- std.>=
- std::operator>=
dev_langs:
- C++
helpviewer_keywords:
- '>= operator, comparing specific objects'
- operator >=
- operator>=
ms.assetid: 14fbebf5-8b75-4afa-a51b-3112d31c07cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 958d87b0c9eb07c3d5c0fea5f2ff06f7b12aee75
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855816"
---
# <a name="operatorgt"></a>оператор&gt;=

> [!NOTE]
> Данный раздел включен в документацию Visual C++ в качестве нефункционального примера контейнеров, используемых в стандартной библиотеке C++. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Перегружает **оператор>=** для сравнения двух объектов класса шаблона [контейнер](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
bool operator>=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает `!(left < right)`.

## <a name="see-also"></a>См. также

[\<образец контейнера>](../standard-library/sample-container.md)<br/>
