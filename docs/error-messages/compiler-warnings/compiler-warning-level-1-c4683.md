---
title: Предупреждение компилятора (уровень 1) C4683 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a157d3beb7c2efa7f1144a961973652e2ce384f7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194201"
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