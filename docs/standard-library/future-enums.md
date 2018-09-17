---
title: Перечисления &lt;future&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 0056d54844e9396d517fd44c3649f1bc9605829b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700561"
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
