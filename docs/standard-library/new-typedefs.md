---
title: Определения типов &lt;new&gt;
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 85c8d0c2974f734783e3d9c2ad1269f84d605dec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549127"
---
# <a name="ltnewgt-typedefs"></a>Определения типов &lt;new&gt;

| |
| - |
|[new_handler](#new_handler)|

## <a name="new_handler"></a>  new_handler

Тип указывает на функцию, подходящую для использования в качестве нового обработчика.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Примечания

Этот тип функции обработчика вызывается **operator new** или `operator new[]`, если они не могут удовлетворить запрос на дополнительное хранилище.

### <a name="example"></a>Пример

См. [set_new_handler](../standard-library/new-functions.md#set_new_handler) с примером использования `new_handler` в качестве как возвращаемого значения.

## <a name="see-also"></a>См. также

[\<new>](../standard-library/new.md)<br/>
