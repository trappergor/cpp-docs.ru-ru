---
title: Класс time_base
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: 85565dc0c0ec904551eb8dd981cfacc9a2e1f256
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460041"
---
# <a name="timebase-class"></a>Класс time_base

Класс выступает в качестве базового класса для аспектов класса шаблона time_get, определяя только перечислимый тип `dateorder` и несколько констант этого типа.

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

- `no_order`Указывает, что порядок не определен.

- `dmy`Указывает день заказа, месяц, год, как в 2 декабря 1979.

- `mdy`Указывает Заказный месяц, день и год, как в 2 декабря 1979 г.

- `ymd`Указывает порядковый номер года, месяца и дня, например 1979/12/2.

- `ydm`Указывает порядковый номер года, день, месяц, как в 1979: 2 декабря.

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
