---
title: '&lt;iomanip&gt;'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
ms.openlocfilehash: b9da0de64bbb0ef48a6a9741ff941e6abda0e705
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449209"
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

Включите стандартный заголовок \<iomanip >, чтобы определить несколько манипуляторов, каждый из которых принимает один аргумент. `iostreams`

## <a name="syntax"></a>Синтаксис

```cpp
#include <iomanip>
```

## <a name="remarks"></a>Примечания

Каждый из этих `T1` манипуляторов возвращает неуказанный тип, вызываемый `T10`с помощью, который перегружает `basic_istream`оба \< **elem**, оператор **tr**>`::`[> >](../standard-library/istream-operators.md#op_gt_gt) и `basic_ostream` **Elem,** [оператор](../standard-library/ostream-operators.md#op_lt_lt) **tr**<<.> \<`::`

### <a name="manipulators"></a>Манипуляторы

|||
|-|-|
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|Получает денежную сумму (при необходимости в международном формате).|
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|Получает время в структуре времени с использованием указанного формата.|
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|Предоставляет денежную сумму (при необходимости в международном формате).|
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|Предоставляет время в структуре времени и строку формата, которую следует использовать.|
|[quoted](../standard-library/iomanip-functions.md#quoted)|Обеспечивает удобное обращение строк с помощью операторов вставки и извлечения.|
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|Удаляет указанные флаги.|
|[setbase](../standard-library/iomanip-functions.md#setbase)|Задает основание целых чисел.|
|[setfill](../standard-library/iomanip-functions.md#setfill)|Задает символ, который будет использоваться для заполнения пробелов на экране с выравниванием по правому краю.|
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|Задает указанные флаги.|
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|Задает точность для значений с плавающей запятой.|
|[setw](../standard-library/iomanip-functions.md#setw)|Задает ширину отображаемого поля.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
