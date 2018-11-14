---
title: '&lt;limits&gt;'
ms.date: 11/04/2016
f1_keywords:
- limits/std::<limits>
- <limits>
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
ms.openlocfilehash: c029095d5298048874a7eb6f1a41209d6a6f4779
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524889"
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;

Определяет класс шаблона `numeric_limits` и два перечисления, касающиеся представления значений с плавающей запятой и округления.

## <a name="syntax"></a>Синтаксис

```cpp
#include <limits>
```

## <a name="remarks"></a>Примечания

Явные специализации `numeric_limits` описывают множество свойств базовых типов, включая символ, целое число и типы с плавающей запятой и **bool** , являются реализацией определен, а не исправить с помощью правила языка C++. Свойства, описанные в \<limits>, включают точность, представления минимального и максимального размера, округление и сообщение об ошибках типа.

### <a name="enumerations"></a>Перечисления

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Перечисление описывает различные методы, которые могут быть выбраны реализацией для представления ненормализованного значения с плавающей запятой, если оно мало для представления в качестве нормализованного значения:|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Перечисление описывает различные методы, которые могут быть выбраны реализацией для округления значения с плавающей запятой до целочисленного.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс numeric_limits](../standard-library/numeric-limits-class.md)|Класс шаблона описывает арифметические свойства встроенных числовых типов.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
