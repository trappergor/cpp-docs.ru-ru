---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 13b6f5c63b9426fc4c31527f0d1ae8291d07807f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222216"
---
# <a name="ltstring_viewgt"></a>&lt;string_view&gt;

Определяет шаблон класса `basic_string_view` и связанные типы и операторы. (Требуется параметр компилятора [std: c++ 17](../build/reference/std-specify-language-standard-version.md) или более поздней версии.)

## <a name="syntax"></a>Синтаксис

```cpp
#include <string_view>
```

## <a name="remarks"></a>Remarks

String_view семейство специализаций шаблонов предоставляет эффективный способ передачи неответственного, доступного только для чтения, безотносительного и невладеющего обработчика к символьным данным любых строковых объектов, имеющих первый элемент последовательности в позиции 0. Параметр функции типа `string_view` (typedef для `basic_string_view<char>` ) может принимать аргументы, такие как `std::string` , **char \* **, или любой другой класс, подобный строковым, с узкими символами, для которых определено неявное преобразование `string_view` . Аналогичным образом, параметр `wstring_view` `u16string_view` или `u32string_view` может принимать любой строковый тип, для которого определено неявное преобразование. Дополнительные сведения см. в разделе [класс basic_string_view](../standard-library/basic-string-view-class.md).

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|Специализация шаблона класса `basic_string_view` с элементами типа **`char`** .|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|Специализация шаблона класса `basic_string_view` с элементами типа **`wchar_t`** .|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|Специализация шаблона класса `basic_string_view` с элементами типа **`char16_t`** .|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|Специализация шаблона класса `basic_string_view` с элементами типа **`char32_t`** .|

### <a name="operators"></a>Операторы

\<string_view>Операторы могут сравнивать `string_view` объекты с объектами любых преобразуемых строковых типов.

|Оператор|Описание|
|-|-|
|[operator! =](../standard-library/string-view-operators.md#op_neq)|Проверяет неравенство объекта слева от оператора объекту справа от оператора.|
|[Оператор = =](../standard-library/string-view-operators.md#op_eq_eq)|Проверяет равенство объекта слева от оператора объекту справа от оператора.|
|[Оператор<](../standard-library/string-view-operators.md#op_lt)|Проверяет, меньше ли объект в левой части оператора, чем объект с правой стороны.|
|[Оператор<=](../standard-library/string-view-operators.md#op_lt_eq)|Проверяет, что объект слева от оператора меньше или равен объекту справа от оператора.|
|[Оператор<\<](../standard-library/string-view-operators.md#op_lt_lt)|Функция шаблона, которая вставляет в `string_view` выходной поток.|
|[Оператор>](../standard-library/string-view-operators.md#op_gt)|Проверяет, больше ли объект в левой части оператора, чем объект с правой стороны.|
|[Оператор>=](../standard-library/string-view-operators.md#op_gt_eq)|Проверяет, что объект слева от оператора больше или равен объекту справа от оператора.|

### <a name="literals"></a>Литералы

|Оператор|Описание|
|-|-|
|[sv](../standard-library/string-view-operators.md#op_sv)|Конструирует `string_view` , `wstring_view` , или, в `u16string_view` `u32string_view` зависимости от типа строкового литерала, к которому он добавляется.|

### <a name="classes"></a>Классы

|Class|Описание|
|-|-|
|[Класс basic_string_view](../standard-library/basic-string-view-class.md)|Шаблон класса, предоставляющий представление, доступное только для чтения, к последовательности произвольных символьных объектов.|
|[hash](string-view-hash.md)|Объект функции, создающий хэш-значение для string_view.|

## <a name="requirements"></a>Требования

- **Заголовок:**\<string_view>

- **Пространство имен:** std

- **Параметр компилятора:** std: c++ 17 (или более поздней версии)

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
