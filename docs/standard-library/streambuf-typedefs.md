---
title: Определения типов &lt;streambuf&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: a9629bd9721d1e6089352cfb7fa8c2b40cbc00b7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ltstreambufgt-typedefs"></a>Определения типов &lt;streambuf&gt;

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>  streambuf

Специализация `basic_streambuf`, использующая `char` в качестве параметров шаблона.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом класса шаблона [basic_streambuf](../standard-library/basic-streambuf-class.md), специализированного для элементов типа `char` с признаками символа по умолчанию.

## <a name="wstreambuf"></a>  wstreambuf

Специализация `basic_streambuf`, использующая `wchar_t` в качестве параметров шаблона.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом класса шаблона [basic_streambuf](../standard-library/basic-streambuf-class.md), специализированного для элементов типа `wchar_t` с признаками символа по умолчанию.

## <a name="see-also"></a>См. также

[\<streambuf>](../standard-library/streambuf.md)<br/>
