---
title: '&lt;string_view&gt; typedefs'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: c3367afe1353ac70abb74a59658a255614ac8470
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865851"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view&gt; typedefs

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a>string_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа **char**.

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>Remarks

Следующие объявления являются равнозначными:

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string_view"></a>u16string_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа `char16_t`.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Remarks

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string_view"></a>u32string_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа `char32_t`.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Remarks

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring_view"></a>wstring_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа **wchar_t**.

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>Remarks

Следующие объявления являются равнозначными:

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> Размер **wchar_t** — два байта в Windows, но это необязательно для всех платформ. Если требуется string_view тип расширенных символов с шириной, которая гарантированно остается одинаковой на всех платформах, используйте [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) или [u32string_view](../standard-library/string-view-typedefs.md#u32string_view).

## <a name="see-also"></a>См. также раздел

[\<string_view >](../standard-library/string-view.md)
