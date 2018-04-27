---
title: Структура char_traits&lt;&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iosfwd/std::char_traits<char>
- char_traits<char >
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char> class
ms.assetid: abd9373a-77db-4031-bf4b-f8ac15087581
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c74e00d9a1f8678539c4f722d48c409d1505b39
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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
