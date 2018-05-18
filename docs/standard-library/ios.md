---
title: '&lt;ios&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <ios>
- ios/std::<ios>
dev_langs:
- C++
helpviewer_keywords:
- ios header
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e7ae83cd92ac8441d842e704446d519f57d4f65
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="ltiosgt"></a>&lt;ios&gt;

Определяет несколько основных типов и функций при работе с потоками ввода-вывода. Этот заголовок обычно включается автоматически при использовании других заголовков потоков ввода-вывода. Его редко приходится включать напрямую.

## <a name="syntax"></a>Синтаксис

```cpp
#include <ios>

```

## <a name="remarks"></a>Примечания

Существует большая группа функций — манипуляторы. Манипулятор, объявленный в \<ios>, изменяет значения, хранящиеся в его аргументе — объекте класса [ios_base](../standard-library/ios-base-class.md). Другие манипуляторы выполняют действия над потоками, управляемыми объектами типа, производного от этого класса, например, специализацией одного из шаблонов классов [basic_istream](../standard-library/basic-istream-class.md) или [basic_ostream](../standard-library/basic-ostream-class.md). Например, [noskipws](../standard-library/ios-functions.md#noskipws)(**str**) очищает флаг формата `ios_base::skipws` в объекте **str**, который может быть одного из этих типов.

Вы можете также вызвать манипулятор путем вставки его в поток вывода или извлечения из потока ввода благодаря специальным операциям вставки и извлечения, доступным для классов, производных от `ios_base`. Пример:

```cpp
istr>> noskipws;
```

вызывает [noskipws](../standard-library/ios-functions.md#noskipws)(**istr**).

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[ios](../standard-library/ios-typedefs.md#ios)|Поддерживает класс ios из старой библиотеки iostream.|
|[streamoff](../standard-library/ios-typedefs.md#streamoff)|Поддерживает внутренние операции.|
|[streampos](../standard-library/ios-typedefs.md#streampos)|Содержит текущее положение указателя буфера или указателя файла.|
|[streamsize](../standard-library/ios-typedefs.md#streamsize)|Определяет размер потока.|
|[wios](../standard-library/ios-typedefs.md#wios)|Поддерживает класс wios из старой библиотеки iostream.|
|[wstreampos](../standard-library/ios-typedefs.md#wstreampos)|Содержит текущее положение указателя буфера или указателя файла.|

### <a name="manipulators"></a>Манипуляторы

|||
|-|-|
|[boolalpha](../standard-library/ios-functions.md#boolalpha)|Устанавливает режим отображения переменных типа [bool](../cpp/bool-cpp.md) в потоке в виде **true** или **false**.|
|[dec](../standard-library/ios-functions.md#dec)|Устанавливает режим отображения целочисленных переменных в нотации с основанием 10.|
|[defaultfloat](../standard-library/ios-functions.md#ios_defaultfloat)|Устанавливает флаги объекта `ios_base` в соответствии с форматом отображения значений с плавающей запятой, принятым по умолчанию.|
|[fixed](../standard-library/ios-functions.md#fixed)|Устанавливает режим отображения чисел с плавающей запятой в нотации фиксированного десятичного формата.|
|[hex](../standard-library/ios-functions.md#hex)|Устанавливает режим отображения целочисленных переменных в нотации с основанием 16.|
|[internal](../standard-library/ios-functions.md#internal)|Устанавливает режим выравнивания знака числа по левому краю, а самого числа — по правому краю.|
|[left](../standard-library/ios-functions.md#left)|Устанавливает режим добавления левого поля для текста, ширина которого меньше, чем ширина выходных данных, при представлении его в потоке.|
|[noboolalpha](../standard-library/ios-functions.md#noboolalpha)|Устанавливает режим отображения переменных типа [bool](../cpp/bool-cpp.md) в потоке в виде 1 или 0.|
|[noshowbase](../standard-library/ios-functions.md#noshowbase)|Отключает отображение основания нотации, в которой отображается число.|
|[noshowpoint](../standard-library/ios-functions.md#noshowpoint)|Отображает только целую часть числа с плавающей запятой, дробная часть которого равна нулю.|
|[noshowpos](../standard-library/ios-functions.md#noshowpos)|Устанавливает режим отображения положительных чисел без обязательного знака.|
|[noskipws](../standard-library/ios-functions.md#noskipws)|Устанавливает режим чтения пробелов потоком ввода.|
|[nounitbuf](../standard-library/ios-functions.md#nounitbuf)|Устанавливает режим использования буфера выходных данных и обработки данных при заполнении буфера.|
|[nouppercase](../standard-library/ios-functions.md#nouppercase)|Устанавливает режим отображения шестнадцатеричных цифр и показателя степени в экспоненциальном представлении в нижнем регистре.|
|[oct](../standard-library/ios-functions.md#oct)|Устанавливает режим отображения целочисленных переменных в нотации с основанием 8.|
|[right](../standard-library/ios-functions.md#right)|Устанавливает режим добавления правого поля для текста, ширина которого меньше, чем ширина выходных данных, при представлении его в потоке.|
|[scientific](../standard-library/ios-functions.md#scientific)|Устанавливает режим отображения чисел с плавающей запятой с использованием экспоненциального представления.|
|[showbase](../standard-library/ios-functions.md#showbase)|Включает отображение основания нотации, в которой отображается число.|
|[showpoint](../standard-library/ios-functions.md#showpoint)|Отображает целую часть числа с плавающей запятой и цифры справа от десятичной запятой даже в том случае, если дробная часть равна нулю.|
|[showpos](../standard-library/ios-functions.md#showpos)|Устанавливает режим отображения положительных чисел с обязательным знаком.|
|[skipws](../standard-library/ios-functions.md#skipws)|Устанавливает режим игнорирования пробелов потоком ввода.|
|[unitbuf](../standard-library/ios-functions.md#unitbuf)|Устанавливает режим обработки выходных данных при наличии данных в буфере.|
|[uppercase](../standard-library/ios-functions.md#uppercase)|Устанавливает режим отображения шестнадцатеричных цифр и показателя степени в экспоненциальном представлении в верхнем регистре.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[basic_ios](../standard-library/basic-ios-class.md)|Класс шаблона описывает хранилище и функции-члены, общие для обоих потоков (потока ввода — класс шаблона [basic_istream](../standard-library/basic-istream-class.md) и потока вывода — класс шаблона [basic_ostream](../standard-library/basic-ostream-class.md)), зависящих от параметров шаблона.|
|[fpos](../standard-library/fpos-class.md)|Класс шаблона описывает объект, который может хранить все сведения, необходимые для восстановления произвольного указателя позиции файла в любом потоке.|
|[ios_base](../standard-library/ios-base-class.md)|Этот класс описывает хранилище и функции-члены общие для обоих потоков (ввода и вывода), не зависящих от параметров шаблона.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
