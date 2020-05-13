---
title: Определения типов &lt;regex&gt;
ms.date: 11/04/2016
f1_keywords:
- regex/std::cmatch
- regex/std::cregex_iterator
- regex/std::cregex_token_iterator
- regex/std::csub_match
- regex/std::regex
- regex/std::smatch
- regex/std::sregex_iterator
- regex/std::sregex_token_iterator
- regex/std::ssub_match
- regex/std::wcmatch
- regex/std::wcregex_iterator
- regex/std::wcregex_token_iterator
- regex/std::wcsub_match
- regex/std::wregex
- regex/std::wsmatch
- regex/std::wsregex_iterator
- regex/std::wsregex_token_iterator
- regex/std::wssub_match
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
ms.openlocfilehash: 5dbda2df4877da7594dd633e9f203a3780b4adb1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368547"
---
# <a name="ltregexgt-typedefs"></a>Определения типов &lt;regex&gt;

||||
|-|-|-|
|[cmatch](#cmatch)|[cregex_iterator](#cregex_iterator)|[cregex_token_iterator](#cregex_token_iterator)|
|[csub_match](#csub_match)|[Regex](#regex)|[smatch](#smatch)|
|[sregex_iterator](#sregex_iterator)|[sregex_token_iterator](#sregex_token_iterator)|[ssub_match](#ssub_match)|
|[wcmatch](#wcmatch)|[wcregex_iterator](#wcregex_iterator)|[wcregex_token_iterator](#wcregex_token_iterator)|
|[wcsub_match](#wcsub_match)|[wregex](#wregex)|[wsmatch](#wsmatch)|
|[wsregex_iterator](#wsregex_iterator)|[wsregex_token_iterator](#wsregex_token_iterator)|[wssub_match](#wssub_match)|

## <a name="cmatch-typedef"></a><a name="cmatch"></a>cmatch Typedef

Определение типа для char match_results.

```cpp
typedef match_results<const char*> cmatch;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [match_results класса](../standard-library/match-results-class.md) `const char*`для итераторов типа.

## <a name="cregex_iterator-typedef"></a><a name="cregex_iterator"></a>cregex_iterator Типдеф

Определение типа для char regex_iterator.

```cpp
typedef regex_iterator<const char*> cregex_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [regex_iterator класса](../standard-library/regex-iterator-class.md) `const char*`для итераторов типа.

## <a name="cregex_token_iterator-typedef"></a><a name="cregex_token_iterator"></a>cregex_token_iterator Типдеф

Определение типа для char regex_token_iterator

```cpp
typedef regex_token_iterator<const char*> cregex_token_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [regex_token_iterator класса](../standard-library/regex-token-iterator-class.md) `const char*`для итераторов типа.

## <a name="csub_match-typedef"></a><a name="csub_match"></a>csub_match Типдеф

Определение типа для char sub_match.

```cpp
typedef sub_match<const char*> csub_match;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [sub_match класса](../standard-library/sub-match-class.md) `const char*`для итераторов типа.

## <a name="regex-typedef"></a><a name="regex"></a>regex Typedef

Определение типа для char basic_regex.

```cpp
typedef basic_regex<char> regex;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [basic_regex класса](../standard-library/basic-regex-class.md) для элементов типа **char.**

> [!NOTE]
> Символы старших разрядов будут иметь непредсказуемые результаты с `regex`. Значения вне диапазона от 0 до 127 могут привести к неопределенному поведению.

## <a name="smatch-typedef"></a><a name="smatch"></a>smatch Typedef

Определение типа для string match_results.

```cpp
typedef match_results<string::const_iterator> smatch;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [match_results класса](../standard-library/match-results-class.md) `string::const_iterator`для итераторов типа.

## <a name="sregex_iterator-typedef"></a><a name="sregex_iterator"></a>sregex_iterator Типдеф

Определение типа для string regex_iterator.

```cpp
typedef regex_iterator<string::const_iterator> sregex_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [regex_iterator класса](../standard-library/regex-iterator-class.md) `string::const_iterator`для итераторов типа.

## <a name="sregex_token_iterator-typedef"></a><a name="sregex_token_iterator"></a>sregex_token_iterator Типдеф

Определение типа для string regex_token_iterator.

```cpp
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [regex_token_iterator класса](../standard-library/regex-token-iterator-class.md) `string::const_iterator`для итераторов типа.

## <a name="ssub_match-typedef"></a><a name="ssub_match"></a>ssub_match Типдеф

Определение типа для string sub_match.

```cpp
typedef sub_match<string::const_iterator> ssub_match;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [sub_match класса](../standard-library/sub-match-class.md) `string::const_iterator`для итераторов типа.

## <a name="wcmatch-typedef"></a><a name="wcmatch"></a>WCmatch Typedef

Определение типа для wchar_t match_results.

```cpp
typedef match_results<const wchar_t *> wcmatch;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [match_results класса](../standard-library/match-results-class.md) `const wchar_t*`для итераторов типа.

## <a name="wcregex_iterator-typedef"></a><a name="wcregex_iterator"></a>wcregex_iterator Типдеф

Определение типа для wchar_t regex_iterator.

```cpp
typedef regex_iterator<const wchar_t*> wcregex_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [regex_iterator класса](../standard-library/regex-iterator-class.md) `const wchar_t*`для итераторов типа.

## <a name="wcregex_token_iterator-typedef"></a><a name="wcregex_token_iterator"></a>wcregex_token_iterator Типдеф

Определение типа для wchar_t regex_token_iterator.

```cpp
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [regex_token_iterator класса](../standard-library/regex-token-iterator-class.md) `const wchar_t*`для итераторов типа.

## <a name="wcsub_match-typedef"></a><a name="wcsub_match"></a>wcsub_match Типдеф

Определение типа для wchar_t sub_match.

```cpp
typedef sub_match<const wchar_t*> wcsub_match;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [sub_match класса](../standard-library/sub-match-class.md) `const wchar_t*`для итераторов типа.

## <a name="wregex-typedef"></a><a name="wregex"></a>wregex Typedef

Определение типа для wchar_t basic_regex.

```cpp
typedef basic_regex<wchar_t> wregex;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [basic_regex класса](../standard-library/basic-regex-class.md) для элементов **типа wchar_t.**

## <a name="wsmatch-typedef"></a><a name="wsmatch"></a>wsmatch Typedef

Определение типа для wstring match_results.

```cpp
typedef match_results<wstring::const_iterator> wsmatch;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [match_results класса](../standard-library/match-results-class.md) `wstring::const_iterator`для итераторов типа.

## <a name="wsregex_iterator-typedef"></a><a name="wsregex_iterator"></a>wsregex_iterator Типдеф

Определение типа для wstring regex_iterator.

```cpp
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [regex_iterator класса](../standard-library/regex-iterator-class.md) `wstring::const_iterator`для итераторов типа.

## <a name="wsregex_token_iterator-typedef"></a><a name="wsregex_token_iterator"></a>wsregex_token_iterator Типдеф

Определение типа для wstring regex_token_iterator.

```cpp
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [regex_token_iterator класса](../standard-library/regex-token-iterator-class.md) `wstring::const_iterator`для итераторов типа.

## <a name="wssub_match-typedef"></a><a name="wssub_match"></a>wssub_match Типдеф

Определение типа для wstring sub_match.

```cpp
typedef sub_match<wstring::const_iterator> wssub_match;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [sub_match класса](../standard-library/sub-match-class.md) `wstring::const_iterator`для итераторов типа.

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)\
[класс regex_constants](../standard-library/regex-constants-class.md)\
[regex_error класс](../standard-library/regex-error-class.md)\
[\<функции regex>](../standard-library/regex-functions.md)\
[класс regex_iterator](../standard-library/regex-iterator-class.md)\
[\<операторы regex>](../standard-library/regex-operators.md)\
[класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)\
[Класс regex_traits](../standard-library/regex-traits-class.md)
