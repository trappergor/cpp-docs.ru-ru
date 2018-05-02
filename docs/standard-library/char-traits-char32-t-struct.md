---
title: Структура char_traits&lt;char32_t&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iosfwd/std::char_traits<char_32t>
- char_traits<char32_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char32_t> class
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ed195f6ed4d1319d079a58f736c65a03e397bd1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="chartraitsltchar32tgt-struct"></a>Структура char_traits&lt;char32_t&gt;

Структура, которая является специализацией структуры шаблона **char_traits\<CharType>** к элементу типа `char32_t`.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
struct char_traits<char32_t>;
```

## <a name="remarks"></a>Примечания

Специализация позволяет структуре использовать преимущества функций библиотеки, которые управляют объектами данного типа `char32_t`.

## <a name="requirements"></a>Требования

**Заголовок:** \<string>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<string>](../standard-library/string.md)<br/>
[Структура char_traits](../standard-library/char-traits-struct.md)<br/>
