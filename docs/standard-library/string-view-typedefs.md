---
title: '&lt;string_view&gt; типофы'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 0ec278484b7c1c9887771f6cbe7e5d0b05205dd7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376676"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view&gt; типофы

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a><a name="string_view"></a>string_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами **символа**типа.

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

## <a name="u16string_view"></a><a name="u16string_view"></a>u16string_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа. `char16_t`

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Remarks

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string_view"></a><a name="u32string_view"></a>u32string_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа. `char32_t`

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Remarks

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring_view"></a><a name="wstring_view"></a>wstring_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа **wchar_t.**

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
> Размер **wchar_t** составляет два байта на Windows, но это не обязательно относится ко всем платформам. Если вам нужен string_view широкий тип символов с шириной, которая гарантированно останется одинаковой на всех платформах, используйте [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) или [u32string_view.](../standard-library/string-view-typedefs.md#u32string_view)

## <a name="see-also"></a>См. также раздел

[\<string_view>](../standard-library/string-view.md)
