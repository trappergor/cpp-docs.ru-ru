---
title: Класс time_base
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: ddaf9905e859c062031940d35adfa2a3393dbb5a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685788"
---
# <a name="time_base-class"></a>Класс time_base

Класс выступает в качестве базового класса для аспектов шаблона класса time_get, определяя только перечислимый тип `dateorder` и несколько констант этого типа.

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

## <a name="remarks"></a>Заметки

Каждая константа характеризует свой способ упорядочивания компонентов даты. Используются следующие константы:

- `no_order` не указывает определенный порядок.

- `dmy` указывает день заказа, месяц, год, как в 2 декабря 1979.

- `mdy` указывает номер месяца, день, год, как в декабре 2 1979.

- `ymd` указывает порядковый номер года, месяца и дня, например 1979/12/2.

- `ydm` указывает номер года, день и месяц, как в 1979:2 декабря.

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
