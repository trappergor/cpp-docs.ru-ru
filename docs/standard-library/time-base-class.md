---
title: Класс time_base | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c13cd76f5d353cf91997406c8e7f74b5383cf8e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854502"
---
# <a name="timebase-class"></a>Класс time_base

Этот класс используется как базовый класс для аспектов класса шаблона time_get, указав только **dateorder** перечисляемого типа и несколько констант этого типа.

## <a name="syntax"></a>Синтаксис

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```

## <a name="remarks"></a>Примечания

Каждая константа характеризует свой способ упорядочивания компонентов даты. Используются следующие константы:

- **no_order** не задает никакого определенного порядка.

- **dmy** задает порядок даты "день, месяц, год", как во "2 декабря 1979".

- **mdy** задает порядок даты "месяц, день, год", как в "декабрь, 2, 1979".

- **ymd** задает порядок даты "год, месяц, день", как в "1979/12/2".

- **ydm** задает порядок даты "год, день, месяц", как в "1979: 2 декабря".

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
