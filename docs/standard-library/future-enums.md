---
title: Перечисления &lt;future&gt;
ms.date: 11/04/2016
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 0f1064fdf434560c3130d1254512470cc5bc1ee0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370697"
---
# <a name="ltfuturegt-enums"></a>Перечисления &lt;future&gt;

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[Запуска](#launch)|

## <a name="future_errc-enumeration"></a><a name="future_errc"></a>future_errc Инумерация

Предоставляет символические имена для всех ошибок, о которых сообщает класс [future_error](../standard-library/future-error-class.md).

```cpp
class future_errc {
   broken_promise,
   future_already_retrieved,
   promise_already_satisfied,
   no_state
   };
```

## <a name="future_status-enumeration"></a><a name="future_status"></a>future_status Инумерация

Предоставляет символические имена по причинам, которые может возвращать привязанная по времени функция wait.

```cpp
enum future_status{
    ready,
    timeout,
    deferred
};
```

## <a name="launch-enumeration"></a><a name="launch"></a>запуск Enumeration

Представляет тип битовой маски, который описывает возможные режимы для функции-шаблона [async](../standard-library/future-functions.md#async).

```cpp
class launch{
   async,
   deferred
   };
```

## <a name="see-also"></a>См. также раздел

[\<будущие>](../standard-library/future.md)
