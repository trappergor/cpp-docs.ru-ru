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
ms.openlocfilehash: 6e228eb538a0d281dff8066390b0c6dd2e7ea4d8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="ltfuturegt-enums"></a>Перечисления &lt;future&gt;

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[Запуск](#launch)|

## <a name="future_errc"></a>  Перечисление future_errc

Предоставляет символические имена для всех ошибок, о которых сообщает класс [future_error](../standard-library/future-error-class.md).

class future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };

## <a name="future_status"></a>  Перечисление future_status

Предоставляет символические имена по причинам, которые может возвращать привязанная по времени функция wait.

```cpp
enum future_status{    ready,
    timeout,
 deferred};
```

## <a name="launch"></a>  Перечисление launch

Представляет тип битовой маски, который описывает возможные режимы для функции-шаблона [async](../standard-library/future-functions.md#async).

class launch{ async, deferred };

## <a name="see-also"></a>См. также

[\<future>](../standard-library/future.md)<br/>
