---
title: '&lt;iomanip&gt;'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
ms.openlocfilehash: f6470f98495362149b4e99c6d1e3fe521800438b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487923"
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

Включить `iostreams` стандартный заголовок \<iomanip > для определения нескольких манипуляторов, каждый принимают один аргумент.

## <a name="syntax"></a>Синтаксис

```cpp
#include <iomanip>

```

## <a name="remarks"></a>Примечания

Все эти манипуляторы возвращают неопределенный тип, с именем `T1` через `T10`, который перегружает как `basic_istream` \< **Elem**, **Tr** > `::` [оператор >>](../standard-library/istream-operators.md#op_gt_gt) и `basic_ostream` \< **Elem**, **Tr** > `::` [оператор <<](../standard-library/ostream-operators.md#op_lt_lt).

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

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
