---
title: '&lt;limits&gt;'
ms.date: 11/04/2016
f1_keywords:
- limits/std::<limits>
- <limits>
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
ms.openlocfilehash: 3ad740975cfff4f65f9e1c800a709cfaca3367db
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687810"
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;

Определяет шаблон класса `numeric_limits` и два перечисления, касающиеся представления чисел с плавающей запятой и округления.

## <a name="requirements"></a>Требования

**Заголовок:** \<limits>

**Пространство имен:** std

## <a name="remarks"></a>Заметки

Явные специализации класса `numeric_limits` описывают множество свойств фундаментальных типов, включая символы, целые числа и типы с плавающей запятой, и **логическое** значение, которое определяется реализацией, а не фиксированными правилами C++ языке. Свойства, описанные в \<limits>, включают точность, представления минимального и максимального размера, округление и сообщение об ошибках типа.

## <a name="members"></a>Члены

### <a name="enumerations"></a>Перечисления

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Перечисление описывает различные методы, которые могут быть выбраны реализацией для представления ненормализованного значения с плавающей запятой, если оно мало для представления в качестве нормализованного значения:|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Перечисление описывает различные методы, которые могут быть выбраны реализацией для округления значения с плавающей запятой до целочисленного.|

### <a name="classes"></a>Классы

|||
|-|-|
|[Класс numeric_limits](../standard-library/numeric-limits-class.md)|Шаблон класса описывает арифметические свойства встроенных числовых типов.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
