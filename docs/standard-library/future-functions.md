---
title: Функции &lt;future&gt;
ms.date: 11/04/2016
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: 16c26212cac13602e981f42d8333518da90615fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370664"
---
# <a name="ltfuturegt-functions"></a>Функции &lt;future&gt;

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[Своп](#swap)|

## <a name="async"></a><a name="async"></a>Async

Представляет *собой асинхронного поставщика.*

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>Параметры

*Политики*\
Значение [launch](../standard-library/future-enums.md#launch).

### <a name="remarks"></a>Remarks

Определения сокращений:

|||
|-|-|
|*Dfn*|Результат вызова метода `decay_copy(forward<Fn>(fn))`.|
|*dargs*|Результаты вызовов `decay_copy(forward<ArgsTypes>(args...))`.|
|*Ty*|Тип `result_of<Fn(ArgTypes...)>::type`.|

Первая функция-шаблон возвращает `async(launch::any, fn, args...)`.

Вторая функция возвращает объект `future<Ty>`, *связанное асинхронное состояние* которого содержит результат вместе со значениями функций *dfn* и *dargs* и объектом потока для управления отдельным потоком выполнения.

Пока `decay<Fn>::type` не станет типом, отличным от launch, вторая функция не участвует в разрешении перегрузки.

Стандарт СЗЗ гласит, что если политика запущена::async, функция создает новый поток. Однако реализация Майкрософт в настоящее время не соответствует требованиям. Он получает свои потоки из Windows ThreadPool, который в некоторых случаях может обеспечить переработанный поток, а не новый. Это означает, `launch::async` что политика `launch::async|launch::deferred`фактически реализуется как .  Другим следствием реализации на основе ThreadPool является отсутствие гарантии того, что локальные переменные потока будут уничтожены по завершении потока. Если поток перерабатывается и предоставляется `async`новому вызову, старые переменные все равно будут существовать. Поэтому мы рекомендуем не использовать локальные переменные с помощью `async`.

Если *policy* политика `launch::deferred`, функция отмечает связанное с ней асинхронное состояние как удерживаемый *функцию* и возвращается. Первый вызов любой функции без учета времени, которая ожидает наступления связанного асинхронного состояния "ready", фактически вызывает отложенную функцию путем оценки `INVOKE(dfn, dargs..., Ty)`.

Во всех случаях связанное асинхронное состояние объекта `future` не становится *ready* до завершения оценки `INVOKE(dfn, dargs..., Ty)` либо путем создания исключения, либо путем обычного возвращения. Результатом связанного асинхронного состояния получается исключение, если таковое было создано, или любое значение, возвращаемое при оценке.

> [!NOTE]
> Для `future` — или последнего объекта [shared_future](../standard-library/shared-future-class.md), присоединенного к задаче, запущенной с`std::async`, деструктор выполняет блокировку, если задача не была завершена; то есть он выполняет блокировку, если этот поток еще не вызвал `.get()` или `.wait()`, а задача по-прежнему выполняется. Если `future`, полученный из `std::async`, перемещается за пределы локальной области, другой код, который его использует, должен знать, что деструктор может заблокировать переход в общее состояние "ready".

Псевдофункция `INVOKE` определяется в [ \<функциональном>. ](../standard-library/functional.md)

## <a name="future_category"></a><a name="future_category"></a>future_category

Возвращает ссылку на объект [error_category](../standard-library/error-category-class.md), характеризующий ошибки, связанные с объектами `future`.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a><a name="make_error_code"></a>make_error_code

Создает [error_code](../standard-library/error-code-class.md) вместе с объектом [error_category](../standard-library/error-category-class.md), характеризующий ошибки [future](../standard-library/future-class.md).

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Параметры

*Errno*\
Значение [future_errc](../standard-library/future-enums.md#future_errc), идентифицирующее ошибку.

### <a name="return-value"></a>Возвращаемое значение

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a><a name="make_error_condition"></a>make_error_condition

Создает [error_condition](../standard-library/error-condition-class.md) вместе с объектом [error_category](../standard-library/error-category-class.md), характеризующий ошибки [future](../standard-library/future-class.md).

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Параметры

*Errno*\
Значение [future_errc](../standard-library/future-enums.md#future_errc), идентифицирующее ошибку.

### <a name="return-value"></a>Возвращаемое значение

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a><a name="swap"></a>Своп

Обменивает *связанное асинхронное состояние* одного `promise` объекта на состояние другого.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Параметры

*Левой*\
Левый объект `promise`.

*Правильно*\
Правой объект `promise`.

## <a name="see-also"></a>См. также раздел

[\<будущие>](../standard-library/future.md)
