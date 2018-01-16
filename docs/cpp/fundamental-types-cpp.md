---
title: "Фундаментальные типы (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
dev_langs: C++
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++], C++ data types
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1bb52d6a987289ed77d7b63a5497323ddad2b467
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fundamental-types--c"></a>Фундаментальные типы (C++)
Основные типы в С++ делятся на три категории: целочисленные, с плавающей запятой и void. Целочисленные типы позволяют обрабатывать целые числа. Типы с плавающей запятой позволяют задавать значения, которые могут иметь дробные части.  
  
 Типом [void](../cpp/void-cpp.md) описывается пустой набор значений. Задание переменных типа `void` невозможно. Этот тип служит в основном для объявления функций, не возвращающих значения, или универсальных указателей на нетипизированные или произвольно типизированные данные. Любое выражение можно явно преобразовать или привести к типу `void`. Однако такие выражения можно использовать только в следующих операторах и операндах:  
  
-   в операторе выражения (дополнительные сведения см. в разделе [Выражения](../cpp/expressions-cpp.md));  
  
-   в левом операнде оператора запятой (дополнительные сведения см. в разделе [Оператор "запятая"](../cpp/comma-operator.md) );  
  
-   Втором и третьем операндах условного оператора (`? :`). (дополнительные сведения см. в разделе [Выражения с условным оператором](../cpp/conditional-operator-q.md) );  
  
 В следующей таблице объясняются ограничения на размеры типов. Эти ограничения не зависят от реализации Microsoft.  
  
### <a name="fundamental-types-of-the-c-language"></a>Основные типы языка C++  
  
|Категория|Тип|Описание|  
|--------------|----------|--------------|  
|Целые числа|`char`|`char` — это целочисленный тип, обычно содержащий члены основной кодировки выполнения (по умолчанию в Microsoft C++ это кодировка ASCII).<br /><br /> Компилятор C++ обрабатывает переменные типа `char`, `signed` `char`и `unsigned` `char` как переменные разных типов. Переменные типа `char` повышаются до типа `int` , как если бы по умолчанию они имели тип `signed` `char` , если не используется параметр компиляции /J. В этом случае они рассматриваются как тип `unsigned` `char` и повышаются до типа `int` без расширения знака.|  
||`bool`|`bool` — это целочисленный тип, который может иметь одно из двух значений: `true` или `false`. Его размер не определен.|  
||`short`|`short` `int` (или просто `short`) — это целочисленный тип, размер которого больше или равен размеру типа `char`и меньше или равен размеру типа `int`.<br /><br /> Объекты типа `short` могут объявляться как объекты типа `signed` `short` или `unsigned short`. `Signed short` — синоним `short`.|  
||`int`|`int` — это целочисленный тип, размер которого больше или равен размеру типа `short` `int`и меньше или равен размеру типа `long`.<br /><br /> Объекты типа `int` могут объявляться как объекты типа `signed` `int` или `unsigned` `int`. `Signed` `int` — синоним `int`.|  
||`__int8`, `__int16`, `__int32`, `__int64`|Целое число с указанием размера `__int n`, где `n` — размер в битах целочисленной переменной. `__int8`, `__int16`, `__int32` и `__int64` — ключевые слова для систем Майкрософт. Не все типы доступны для всех архитектур. `(__int128`не поддерживается.)|  
||`long`|`long` (или `long` `int`) — это целочисленный тип, размер которого больше или равен размеру типа `int`.<br /><br /> Объекты типа `long` могут объявляться как объекты типа `signed` `long` или `unsigned` `long`. `Signed` `long` — синоним `long`.|  
||`long` `long`|Больше, чем unsigned `long`.<br /><br /> Объекты типа `long long` могут объявляться как объекты типа `signed` `long long` или `unsigned` `long long`. `signed``long long` является синонимом `long long`.|  
||`wchar_t`, `__wchar_t`|Переменная типа `wchar_t` обозначает расширенный символьный или многобайтовый символьный тип. По умолчанию тип `wchar_t` является машинным типом, однако вы можете использовать [/Zc:wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) , чтобы сделать `wchar_t` определением типа для `unsigned short`. `__wchar_t` — синоним для машинного типа `wchar_t` для систем Майкрософт.<br /><br /> Чтобы задать расширенный символьный тип, перед символьным или строковым литералом следует использовать префикс L.|  
|С плавающей запятой|`float`|`float` — это тип с плавающей запятой наименьшего размера.|  
||`double`|`double` — это тип с плавающей запятой, размер которого больше или равен размеру типа `float`, но меньше или равен размеру типа `long` `double`.<br /><br /> Для систем Майкрософт: представление `long double` и `double` идентично. Однако типы `long double` и `double` — это отдельные типы.|  
||`long double`|`long` `double` — это тип с плавающей запятой, размер которого больше или равен размеру типа `double`.|  
  
 **Блок, относящийся только к системам Microsoft**  
  
 В следующей таблице указаны объемы памяти, необходимые для основных типов в Microsoft C++.  
  
### <a name="sizes-of-fundamental-types"></a>Размеры основных типов  
  
|Тип|Размер|  
|----------|----------|  
|`bool`, `char`, `unsigned char`, `signed char`, `__int8`|1 байт|  
|`__int16`, `short`, `unsigned short`, `wchar_t`, `__wchar_t`|2 байта|  
|`float`, `__int32`, `int`, `unsigned int`, `long`, `unsigned long`|4 байта|  
|`double`, `__int64`, `long double`, `long long`|8 байт|  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
 Сводку по диапазонам значений каждого типа см. в разделе [Диапазоны типов данных](../cpp/data-type-ranges.md) .  
  
 Дополнительные сведения о преобразовании типов см. в разделе [Стандартные преобразования](../cpp/standard-conversions.md).  
  
## <a name="see-also"></a>См. также  
 [Диапазоны типов данных](../cpp/data-type-ranges.md)