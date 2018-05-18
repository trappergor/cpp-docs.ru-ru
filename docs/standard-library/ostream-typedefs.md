---
title: Определения типов &lt;ostream&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 3f5511cfbf73ddf74fa12954e1a108d8accf875e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="ltostreamgt-typedefs"></a>Определения типов &lt;ostream&gt;

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

Создает тип из basic_ostream, специализированного на `char` и `char_traits`, специализированного на `char`.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом класса шаблона [basic_ostream](../standard-library/basic-ostream-class.md), специализированного для элементов типа `char` с признаками символа по умолчанию.

## <a name="wostream"></a>  wostream

Создает тип из basic_ostream, специализированного на `wchar_t` и `char_traits`, специализированного на `wchar_t`.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом класса шаблона [basic_ostream](../standard-library/basic-ostream-class.md), специализированного для элементов типа `wchar_t` с признаками символа по умолчанию.

## <a name="see-also"></a>См. также

[\<ostream>](../standard-library/ostream.md)<br/>
