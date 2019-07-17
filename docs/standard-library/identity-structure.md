---
title: Структура identity
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 49b2c1eb3ca03f9bf9199bdbca49348866ff0a7e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246166"
---
# <a name="identity-structure"></a>Структура identity

Структура, предоставляющая определение типа как параметр шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
};
```

### <a name="parameters"></a>Параметры

*Слева*\
Значение, которое необходимо идентифицировать.

## <a name="remarks"></a>Примечания

Класс содержит определение открытого типа `type`, которое совпадает с типом параметра-шаблона. Он используется в сочетании с функцией шаблона [forward](../standard-library/utility-functions.md#forward) для проверки того, что параметр функции имеет требуемый тип.

Для совместимости со старым кодом этот класс также определяет функцию identity `operator()` которая возвращает свой аргумент *левой*.
