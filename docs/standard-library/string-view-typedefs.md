---
title: '&lt;string_view&gt; определения типов'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 16d7ba49facf24dcffb7df444e445d83d92255e0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346972"
---
# <a name="ltstringviewgt-typedefs"></a>&lt;string_view&gt; определения типов

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a> string_view

Тип, описывающий специализацию класса-шаблона [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа **char**.

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>Примечания

Следующие объявления являются равнозначными:

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string_view"></a> u16string_view

Тип, описывающий специализацию класса-шаблона [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа `char16_t`.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Примечания

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string_view"></a> u32string_view

Тип, описывающий специализацию класса-шаблона [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа `char32_t`.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Примечания

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring_view"></a>  wstring_view

Тип, описывающий специализацию класса-шаблона [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа **wchar_t**.

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>Примечания

Следующие объявления являются равнозначными:

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> Размер **wchar_t** два байта на Windows, но это не обязательно так для всех платформ. Если вам требуется расширенный символ типа string_view, ширина которого гарантированно останется одинаковой на всех платформах, использовать [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) или [u32string_view](../standard-library/string-view-typedefs.md#u32string_view).

## <a name="see-also"></a>См. также

[\<string_view >](../standard-library/string-view.md)<br/>
