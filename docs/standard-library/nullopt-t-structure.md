---
title: Структура nullopt_t
ms.date: 08/04/2019
f1_keywords:
- optional/std::nullopt_t
- optional/std::nullopt
ms.openlocfilehash: 1f453a5d75de3f6dedb133d55c094a4f4274e08f
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957044"
---
# <a name="nullopt_t-struct"></a>Структура nullopt_t

Тип `nullopt_t` — уникальный, пустой тип, который указывает, что [необязательный](optional-class.md) объект не содержит значения.

Константа `nullopt` типа `nullopt_t` указывает `optional` , что тип имеет неинициализированное состояние. Его можно использовать для инициализации `optional` объекта или по сравнению с одним.

## <a name="syntax"></a>Синтаксис

```cpp
struct nullopt_t;
inline constexpr nullopt_t nullopt{ /*implementation-defined*/ };
```

## <a name="see-also"></a>См. также

[\<Необязательный >](optional.md)\
[необязательный класс](optional-class.md)
