---
title: '&lt;valarray&gt;'
ms.date: 11/04/2016
f1_keywords:
- <valarray>
helpviewer_keywords:
- valarray header
ms.assetid: 30835415-21c1-4801-8f24-6bbef7dd8ecd
ms.openlocfilehash: efd3e750abb68ad84eb8894ea6b53fe8e29e0e17
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447792"
---
# <a name="ltvalarraygt"></a>&lt;valarray&gt;

Определяет класс шаблона valarray и многочисленные вспомогательные классы и функции шаблонов.

## <a name="syntax"></a>Синтаксис

```cpp
#include <valarray>

```

## <a name="remarks"></a>Примечания

Эти классы и функции обладают нестандартной широтой для повышения производительности. В частности, любая функция, возвращающая объект типа **valarray\<** T1**>**, может возвращать объект другого типа T2. В этом случае любая функция, которая принимает один или несколько аргументов типа **valarray\<** T2**>**, должна иметь перегрузки, которые принимают произвольные сочетания этих аргументов, каждый из которых заменяется аргументом типа T2.

### <a name="functions"></a>Функции

|Функция|Описание|
|-|-|
|[abs](../standard-library/valarray-functions.md#abs)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны абсолютному значению элементов входного valarray.|
|[acos](../standard-library/valarray-functions.md#acos)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны арккосинусу элементов входного valarray.|
|[asin](../standard-library/valarray-functions.md#asin)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны арксинусу элементов входного valarray.|
|[atan](../standard-library/valarray-functions.md#atan)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны арифметическому значению арктангенса элементов входного valarray.|
|[atan2](../standard-library/valarray-functions.md#atan2)|Возвращает valarray, элементы которого равны арктангенсу декартовых компонентов, заданных сочетанием констант и элементов массивов valarray.|
|[cos](../standard-library/valarray-functions.md#cos)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны косинусу элементов входного valarray.|
|[cosh](../standard-library/valarray-functions.md#cosh)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны гиперболическому косинусу элементов входного valarray.|
|[exp](../standard-library/valarray-functions.md#exp)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны натуральной экспоненте элементов входного valarray.|
|[log](../standard-library/valarray-functions.md#log)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны натуральному логарифму элементов входного valarray.|
|[log10](../standard-library/valarray-functions.md#log10)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны десятичному логарифму элементов входного valarray.|
|[pow](../standard-library/valarray-functions.md#pow)|Обрабатывает элементы входных объектов valarray и констант, возвращая массив valarray, элементы которого равны основанию, заданному элементами входного valarray, или константу, возведенную в степень, заданную элементами входного valarray или константой.|
|[sin](../standard-library/valarray-functions.md#sin)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны синусу элементов входного valarray.|
|[sinh](../standard-library/valarray-functions.md#sinh)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны гиперболическому синусу элементов входного valarray.|
|[sqrt](../standard-library/valarray-functions.md#sqrt)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны квадратному корню элементов входного valarray.|
|[swap](../standard-library/valarray-functions.md#swap)||
|[tan](../standard-library/valarray-functions.md#tan)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны тангенсу элементов входного valarray.|
|[tanh](../standard-library/valarray-functions.md#tanh)|Обрабатывает элементы входного valarray, возвращая массив valarray, элементы которого равны гиперболическому тангенсу элементов входного valarray.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](../standard-library/valarray-operators.md#op_neq)|Проверяет, не равны ли соответствующие элементы двух одинаковых по размеру valarray или не равны ли все элементы valarray указанному значению типа элемента valarray.|
|[оператор%](../standard-library/valarray-operators.md#op_mod)|Возвращает остаток от деления соответствующих элементов двух одинаковых по размеру valarray или от деления valarray на указанное значение типа элемента valarray или от деления указанного значения на valarray.|
|[оператор&](../standard-library/valarray-operators.md#op_amp)|Получает результат применения побитовой операции `AND` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента.|
|[оператор&&](../standard-library/valarray-operators.md#op_amp_amp)|Получает результат применения логической операции `AND` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента valarray.|
|[оператор>](../standard-library/valarray-operators.md#op_gt)|Проверяет, больше ли элементы одного valarray, чем элементы одинакового по размеру valarray либо больше или меньше ли все элементы valarray, чем указанное значение типа элемента valarray.|
|[оператор>=](../standard-library/valarray-operators.md#op_gt_eq)|Проверяет, больше или равны ли элементы одного valarray элементам одинакового по размеру valarray, или проверяет, больше или равны ли либо меньше или равны ли все элементы valarray указанному значению.|
|[оператор>>](../standard-library/valarray-operators.md#op_gt_gt)|Сдвигает вправо биты для каждого элемента valarray на указанное число позиций или на поэлементную сумму, указанную вторым valarray.|
|[оператор<](../standard-library/valarray-operators.md#op_lt)|Проверяет, меньше ли элементы одного valarray, чем элементы одинакового по размеру valarray или больше ли либо меньше ли все элементы valarray, чем указанное значение.|
|[оператор<=](../standard-library/valarray-operators.md#op_lt_eq)|Проверяет, меньше или равны ли элементы одного valarray элементам одинакового по размеру valarray, или проверяет, больше или равны ли либо меньше или равны ли все элементы valarray указанному значению.|
|[оператор<<](../standard-library/valarray-operators.md#op_lt_lt)|Сдвигает влево биты для каждого элемента valarray на указанное число позиций или на поэлементную сумму, указанную вторым valarray.|
|[оператор*](../standard-library/valarray-operators.md#op_star)|Получает результат поэлементного умножения соответствующих элементов двух одинаковых по размеру valarray или умножения valarray и указанного значения типа элемента valarray.|
|[operator+](../standard-library/valarray-operators.md#op_add)|Получает результат поэлементной суммы соответствующих элементов двух одинаковых по размеру valarray или суммы valarray и указанного значения типа элемента valarray.|
|[operator-](../standard-library/valarray-operators.md#operator-)|Получает результат поэлементного вычитания соответствующих элементов двух одинаковых по размеру valarray или вычитания valarray и указанного значения типа элемента valarray.|
|[оператор/](../standard-library/valarray-operators.md#op_div)|Получает результат поэлементного деления соответствующих элементов двух одинаковых по размеру valarray или деления valarray на указанное значение типа элемента valarray.|
|[operator==](../standard-library/valarray-operators.md#op_eq_eq)|Проверяет, равны ли соответствующие элементы двух одинаковых по размеру valarray или равны ли все элементы valarray указанному значению типа элемента valarray.|
|[оператор^](../standard-library/valarray-operators.md#op_xor)|Получает результат применения побитовой эксклюзивной операции `OR` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента.|
|[оператор|](../standard-library/valarray-operators.md#op_or)|Получает результат применения побитовой операции `OR` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента.|
|[оператор||](../standard-library/valarray-operators.md#op_lor)|Получает результат применения логической операции `OR` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента valarray.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс gslice](../standard-library/gslice-class.md)|Служебный класс, используемый для определения многомерных срезов valarray.|
|[Класс gslice_array](../standard-library/gslice-array-class.md)|Внутренний, вспомогательный класс шаблона, который поддерживает общие объекты срезов, предоставляя операции между массивами подмножеств, заданные общим срезом valarray.|
|[Класс indirect_array](../standard-library/indirect-array-class.md)|Внутренний, вспомогательный класс шаблона, который поддерживает объекты, представляющие подмножества valarray, предоставляя операции между массивами подмножеств, заданных в виде подмножества индексов родительского valarray.|
|[Класс mask_array](../standard-library/mask-array-class.md)|Внутренний, вспомогательный класс шаблона, который поддерживает объекты, представляющие подмножества родительских valarray, указанных логическим выражением, предоставляя операции между массивами подмножеств.|
|[Класс slice](../standard-library/slice-class.md)|Служебный класс, используемый для определения одномерных векторных подмножеств valarray.|
|[Класс slice_array](../standard-library/slice-array-class.md)|Внутренний, вспомогательный класс шаблона, который поддерживает объекты срезов, предоставляя операции между массивами подмножеств, заданные срезом valarray.|
|[Класс valarray](../standard-library/valarray-class.md)|Класс шаблона описывает объект, управляющий последовательностью элементов типа `Type` , которые хранятся в виде массива и предназначены для быстрого выполнения математических операций, оптимизированы для повышения производительности вычислений.|

### <a name="specializations"></a>Специализации

|||
|-|-|
|Класс [valarray\<bool>](../standard-library/valarray-bool-class.md)|Специализированная версия класса шаблона valarray\<**тип**> для элементов типа **bool**.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
