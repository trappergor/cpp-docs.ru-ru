---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 47924c3d6bd1a2f45cdbac648f4f563c57ce8939
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459121"
---
# <a name="ltstringviewgt"></a>&lt;string_view&gt;

Определяет шаблон `basic_string_view` класса и связанные типы и операторы. (Требуется параметр компилятора [std: c++ 17](../build/reference/std-specify-language-standard-version.md) или более поздней версии.)

## <a name="syntax"></a>Синтаксис

```cpp
#include <string_view>
```

## <a name="remarks"></a>Примечания

Семейство специализаций шаблонов string_view предоставляет эффективный способ передачи неответственного (только для чтения) обработчика, который не является владельцем, в символьные данные любых строковых объектов, имеющих первый элемент последовательности в позиции 0. Параметр функции типа `string_view` (typedef для `basic_string_view<char>`) может принимать аргументы, такие как `std::string`, **char\*** или любые другие строковые классы с узкими символами, для которых неявное преобразование в `string_view`определено. Аналогичным образом, параметр `wstring_view` `u16string_view` или `u32string_view` может принимать любой строковый тип, для которого определено неявное преобразование. Дополнительные сведения см. в разделе [класс basic_string_view](../standard-library/basic-string-view-class.md).

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|Специализация шаблона `basic_string_view` класса с элементами типа **char**.|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|Специализация шаблона `basic_string_view` класса с элементами типа **wchar_t**.|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|Специализация шаблона `basic_string_view` класса с элементами типа `char16_t`.|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|Специализация шаблона `basic_string_view` класса с элементами типа `char32_t`.|

### <a name="operators"></a>Операторы

`string_view` Операторы > \<string_view могут сравнивать объекты с объектами любых преобразуемых строковых типов.

|Оператор|Описание|
|-|-|
|[operator!=](../standard-library/string-view-operators.md#op_neq)|Проверяет неравенство объекта слева от оператора объекту справа от оператора.|
|[operator==](../standard-library/string-view-operators.md#op_eq_eq)|Проверяет равенство объекта слева от оператора объекту справа от оператора.|
|[оператор<](../standard-library/string-view-operators.md#op_lt)|Проверяет, меньше ли объект в левой части оператора, чем объект с правой стороны.|
|[оператор<=](../standard-library/string-view-operators.md#op_lt_eq)|Проверяет, что объект слева от оператора меньше или равен объекту справа от оператора.|
|[оператор<\<](../standard-library/string-view-operators.md#op_lt_lt)|Функция шаблона, которая вставляет `string_view` в выходной поток.|
|[оператор>](../standard-library/string-view-operators.md#op_gt)|Проверяет, больше ли объект в левой части оператора, чем объект с правой стороны.|
|[оператор>=](../standard-library/string-view-operators.md#op_gt_eq)|Проверяет, что объект слева от оператора больше или равен объекту справа от оператора.|

### <a name="literals"></a>Литералы

|Оператор|Описание|
|-|-|
|[календар](../standard-library/string-view-operators.md#op_sv)|`wstring_view`Конструирует, ,`u16string_view`или ,`u32string_view` в зависимости от типа строкового литерала, к которому он `string_view`добавляется.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс basic_string_view](../standard-library/basic-string-view-class.md)|Шаблон класса, предоставляющий представление, доступное только для чтения, к последовательности произвольных символьных объектов.|
|[hash](string-view-hash.md)|Объект функции, создающий хэш-значение для string_view.|

## <a name="requirements"></a>Требования

- **Заголовок:** \<string_view >

- **Пространство имен:** std

- **Параметр компилятора:** std: c++ 17 (или более поздней версии)

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
