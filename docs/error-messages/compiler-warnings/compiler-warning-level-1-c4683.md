---
title: Предупреждение компилятора (уровень 1) C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: 264753ece6cbabded21df8e6b9dbb463f811e8a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375162"
---
# <a name="compiler-warning-level-1-c4683"></a>Предупреждение компилятора (уровень 1) C4683

> "*функция*": у источника события имеется «out»-параметра; соблюдайте осторожность при использовании нескольких обработчиков события

## <a name="remarks"></a>Примечания

Если более чем одному приемнику событий ожидает передачи данных для источника событий модели COM, могут игнорироваться значение выходного параметра.

Учтите, что утечка памяти будет происходить в следующих ситуациях:

1. Если метод имеет параметр out, который выделяется внутри него, например BSTR *.

2. Если событие имеет несколько обработчиков (является событие многоадресной рассылки).

Причиной утечки является выходной параметр будет задается несколько обработчиков, но возвращается к месту вызова только по последним обработчиком.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4683 и показаны способы ее устранения:

```cpp
// C4683.cpp
// compile with: /W1 /LD
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="xx") ];

[ object ]
__interface I {
   HRESULT f([out] int* pi);
   // try the following line instead
   // HRESULT f(int* pi);
};

[ coclass, event_source(com) ]
struct E {
   __event __interface I;   // C4683
};
```