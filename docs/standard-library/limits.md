---
title: '&lt;limits&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66f9401bed0a6c9d0b1ffa09a10f98afa258069d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964760"
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

|Класс|Описание:|
|-|-|
|[Класс numeric_limits](../standard-library/numeric-limits-class.md)|Класс шаблона описывает арифметические свойства встроенных числовых типов.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
