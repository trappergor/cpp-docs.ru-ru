---
title: Определения типов &lt;streambuf&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 81c7cd875c6083ee77701116f6b1179760373ec0
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953996"
---
# <a name="ltstreambufgt-typedefs"></a>Определения типов &lt;streambuf&gt;

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>  streambuf

Специализация `basic_streambuf` , использующий **char** в качестве параметров шаблона.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Примечания

Тип является синонимом класса шаблона [basic_streambuf](../standard-library/basic-streambuf-class.md), специализированного для элементов типа **char** с признаками символа по умолчанию.

## <a name="wstreambuf"></a>  wstreambuf

Специализация `basic_streambuf` , использующий **wchar_t** в качестве параметров шаблона.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Примечания

Тип является синонимом класса шаблона [basic_streambuf](../standard-library/basic-streambuf-class.md), специализированного для элементов типа **wchar_t** с признаками символа по умолчанию.

## <a name="see-also"></a>См. также

[\<streambuf>](../standard-library/streambuf.md)<br/>
