---
title: Структура char_traits&lt;&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iosfwd/std::char_traits<char>
- char_traits<char >
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char> class
ms.assetid: abd9373a-77db-4031-bf4b-f8ac15087581
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a20e9c1df241feb8dd7f16891f1e2a67068f772
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33840398"
---
# <a name="chartraitsltchargt-struct"></a>Структура char_traits&lt;char&gt;

Структура, которая является специализацией структуры шаблона **char_traits\<CharType>** к элементу типа `char`.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
struct char_traits<char>;
```

## <a name="remarks"></a>Примечания

Специализация позволяет структуре использовать преимущества функций библиотеки, которые управляют объектами данного типа `char`.

## <a name="example"></a>Пример

См. определения типов и функции-члены класса шаблона [char_traits](../standard-library/char-traits-struct.md)
