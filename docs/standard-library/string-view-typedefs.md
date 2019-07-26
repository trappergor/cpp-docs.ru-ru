---
title: '&lt;определения&gt; типов string_view'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: c3367afe1353ac70abb74a59658a255614ac8470
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459181"
---
# <a name="ltstringviewgt-typedefs"></a>&lt;определения&gt; типов string_view

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a>string_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа **char**.

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

## <a name="u16string_view"></a>u16string_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа `char16_t`.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Примечания

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string_view"></a>u32string_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа `char32_t`.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Примечания

Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring_view"></a>wstring_view

Тип, описывающий специализацию шаблона класса [basic_string_view](../standard-library/basic-string-view-class.md) с элементами типа **wchar_t**.

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
> Размер **wchar_t** составляет два байта в Windows, но это необязательно относится ко всем платформам. Если требуется тип расширенных символов string_view с шириной, которая гарантированно останется одинаковой на всех платформах, используйте [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) или [u32string_view](../standard-library/string-view-typedefs.md#u32string_view).

## <a name="see-also"></a>См. также

[\<string_view >](../standard-library/string-view.md)
