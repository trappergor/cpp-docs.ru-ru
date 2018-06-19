---
title: Структура char_traits&lt;char32_t&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iosfwd/std::char_traits<char_32t>
- char_traits<char32_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char32_t> class
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6caffb278fbcb94eff1042716adc384b56ae6050
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847017"
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
