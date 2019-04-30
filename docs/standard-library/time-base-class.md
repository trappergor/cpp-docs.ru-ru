---
title: Класс time_base
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: e790237e506aa32bafdb39938d841307bbc4d9c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412024"
---
# <a name="timebase-class"></a>Класс time_base

Этот класс служит базовый класс для аспектов класса шаблона time_get, указав только что перечисляемого типа `dateorder` и несколько констант этого типа.

## <a name="syntax"></a>Синтаксис

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>Примечания

Каждая константа характеризует свой способ упорядочивания компонентов даты. Используются следующие константы:

- `no_order` Указывает без упорядочения.

- `dmy` Указывает порядок день, месяц, то год, как и в 2 декабря 1979.

- `mdy` Указывает порядок месяц, день, а затем года, как и в 2 декабря 1979.

- `ymd` Указывает порядок год, месяц, а затем день, как в 1979/12/2.

- `ydm` Указывает год заказа, день, а затем месяца, например 1979: 2 декабря.

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
