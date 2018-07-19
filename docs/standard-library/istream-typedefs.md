---
title: Определения типов &lt;istream&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: bea06c9799783feafaff1f68f4019463e452a4f2
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958859"
---
# <a name="ltistreamgt-typedefs"></a>Определения типов &lt;istream&gt;

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

Тип `basic_iostream` специализированный на **char**.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Примечания

Тип является синонимом класса шаблона [basic_iostream](../standard-library/basic-iostream-class.md), специализированного для элементов типа **char** с признаками символа по умолчанию.

## <a name="istream"></a>  istream

Тип `basic_istream` специализированный на **char**.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Примечания

Тип является синонимом класса шаблона [basic_istream](../standard-library/basic-istream-class.md), специализированного для элементов типа **char** с признаками символа по умолчанию.

## <a name="wiostream"></a>  wiostream

Тип `basic_iostream` специализированный на **wchar_t**.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Примечания

Тип является синонимом класса шаблона [basic_iostream](../standard-library/basic-iostream-class.md), специализированного для элементов типа **wchar_t** с признаками символа по умолчанию.

## <a name="wistream"></a>  wistream

Тип `basic_istream` специализированный на **wchar_t**.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Примечания

Тип является синонимом класса шаблона [basic_istream](../standard-library/basic-istream-class.md), специализированного для элементов типа **wchar_t** с признаками символа по умолчанию.

## <a name="see-also"></a>См. также

[\<istream>](../standard-library/istream.md)<br/>
