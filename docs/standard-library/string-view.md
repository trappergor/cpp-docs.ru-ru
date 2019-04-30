---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 8952416cf37fc4d8d281d6ced9b8264495ec3799
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346982"
---
# <a name="ltstringviewgt"></a>&lt;string_view&gt;

Определяет шаблон класса `basic_string_view` и связанные типы и операторы. (Необходимо использовать параметр компилятора [std: c ++ 17](../build/reference/std-specify-language-standard-version.md) или более поздней версии.)

## <a name="syntax"></a>Синтаксис

```cpp
#include <string_view>
```

## <a name="remarks"></a>Примечания

В специализации шаблона семейства string_view предоставляет эффективный способ передачи только для чтения, исключений, -владелец дескриптора в символьные данные любого строкового типа объектов с первого элемента последовательности нулевой позиции. Тип параметра функции `string_view` (который является typedef для `basic_string_view<char>`) могут принимать аргументы, такие как `std::string`, **char\***, или любому другому классу строкового типа узких символов, для которого неявным преобразование в `string_view` определен. Аналогичным образом, параметр `wstring_view`, `u16string_view` или `u32string_view` может принимать любой строковый тип, для которого определен неявное преобразование. Дополнительные сведения см. в разделе [basic_string_view класс](../standard-library/basic-string-view-class.md).

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|В специализации шаблона класса `basic_string_view` с элементами типа **char**.|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|В специализации шаблона класса `basic_string_view` с элементами типа **wchar_t**.|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|В специализации шаблона класса `basic_string_view` с элементами типа `char16_t`.|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|В специализации шаблона класса `basic_string_view` с элементами типа `char32_t`.|

### <a name="operators"></a>Операторы

\<String_view > операторы можно сравнить `string_view` к объектам, приводимым любые строковые типы.

|Оператор|Описание|
|-|-|
|[operator!=](../standard-library/string-view-operators.md#op_neq)|Проверяет неравенство объекта слева от оператора объекту справа от оператора.|
|[operator==](../standard-library/string-view-operators.md#op_eq_eq)|Проверяет равенство объекта слева от оператора объекту справа от оператора.|
|[оператор<](../standard-library/string-view-operators.md#op_lt)|Проверяет, если объект в левой части оператора меньше объекта справа от оператора.|
|[оператор<=](../standard-library/string-view-operators.md#op_lt_eq)|Проверяет, что объект слева от оператора меньше или равен объекту справа от оператора.|
|[оператор<\<](../standard-library/string-view-operators.md#op_lt_lt)|Функция шаблона, который вставляет `string_view` в поток вывода.|
|[оператор>](../standard-library/string-view-operators.md#op_gt)|Проверяет равенство объекта слева от оператора больше, чем объект справа от оператора.|
|[оператор>=](../standard-library/string-view-operators.md#op_gt_eq)|Проверяет, что объект слева от оператора больше или равен объекту справа от оператора.|

### <a name="literals"></a>Литералы

|Оператор|Описание|
|-|-|
|[sv](../standard-library/string-view-operators.md#op_sv)|Создает `string_view`, `wstring_view`, `u16string_view`, или `u32string_view` в зависимости от типа строкового литерала, к которому он добавляется.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс basic_string_view](../standard-library/basic-string-view-class.md)|Шаблон класса, которое предоставляет представление только для чтения в последовательность произвольных символьных объектов.|
|[hash](string-view-hash.md)|Объект функции, который создает хэш-string_view.|

## <a name="requirements"></a>Требования

- **Заголовок:** \<string_view >

- **Пространство имен:** std

- **Параметр компилятора:** std: c ++ 17 (или более поздней версии)

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
