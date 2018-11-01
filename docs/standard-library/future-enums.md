---
title: Перечисления &lt;future&gt;
ms.date: 11/04/2016
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 1e487128d4af5c6f9b3f29f5c71e52f616e1807a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655338"
---
# <a name="ltfuturegt-enums"></a>Перечисления &lt;future&gt;

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[запустить](#launch)|

## <a name="future_errc"></a>  Перечисление future_errc

Предоставляет символические имена для всех ошибок, о которых сообщает класс [future_error](../standard-library/future-error-class.md).

```cpp
class future_errc {
   broken_promise,
   future_already_retrieved,
   promise_already_satisfied,
   no_state
   };
```

## <a name="future_status"></a>  Перечисление future_status

Предоставляет символические имена по причинам, которые может возвращать привязанная по времени функция wait.

```cpp
enum future_status{
    ready,
    timeout,
    deferred
};
```

## <a name="launch"></a>  Перечисление launch

Представляет тип битовой маски, который описывает возможные режимы для функции-шаблона [async](../standard-library/future-functions.md#async).

```cpp
class launch{
   async,
   deferred
   };
```

## <a name="see-also"></a>См. также

[\<future>](../standard-library/future.md)<br/>
