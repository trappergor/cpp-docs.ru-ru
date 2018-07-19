---
title: Функции &lt;future&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: bbb724747052c6dd636199fd1cabdf97d2bd4045
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027401"
---
# <a name="ltfuturegt-functions"></a>Функции &lt;future&gt;

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[swap](#swap)|

## <a name="async"></a>  async

Представляет *асинхронного поставщика*.

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>Параметры

*политика* объект [запуска](../standard-library/future-enums.md#launch) значение.

### <a name="remarks"></a>Примечания

Определения сокращений:

|||
|-|-|
|*dfn*|Результат вызова метода `decay_copy(forward<Fn>(fn))`.|
|*dargs*|Результаты вызовов `decay_copy(forward<ArgsTypes>(args...))`.|
|*Ty*|Тип `result_of<Fn(ArgTypes...)>::type`.|

Первая функция-шаблон возвращает `async(launch::any, fn, args...)`.

Вторая функция возвращает объект `future<Ty>`, *связанное асинхронное состояние* которого содержит результат вместе со значениями функций *dfn* и *dargs* и объектом потока для управления отдельным потоком выполнения.

Пока `decay<Fn>::type` не станет типом, отличным от launch, вторая функция не участвует в разрешении перегрузки.

Стандарт C++ указывает, что, если параметр launch::async, функция создает новый поток. Тем не менее реализация Майкрософт в настоящее время не соответствующий требованиям. Он получает его потоков Windows ThreadPool, что в некоторых случаях может предоставлять перезапущен поток, а не ее заново. Это означает, что `launch::async` политики фактически реализуется как `launch::async|launch::deferred`.  Другой реализации на основе ThreadPool подразумевается, что нет гарантии того, что локальные переменные потока, уничтожается после завершения потока. Если поток уничтожен и передается новый вызов `async`, старый переменных по-прежнему будет существовать. Поэтому рекомендуется не использовать локальные переменные потока с `async`.

Если *политики* — `launch::deferred`, функция помечает свое связанное асинхронное состояние как имеющую *отложенную функцию* и возвращает. Первый вызов любой функции без учета времени, которая ожидает наступления связанного асинхронного состояния "ready", фактически вызывает отложенную функцию путем оценки `INVOKE(dfn, dargs..., Ty)`.

Во всех случаях связанное асинхронное состояние объекта `future` не становится *ready* до завершения оценки `INVOKE(dfn, dargs..., Ty)` либо путем создания исключения, либо путем обычного возвращения. Результатом связанного асинхронного состояния получается исключение, если таковое было создано, или любое значение, возвращаемое при оценке.

> [!NOTE]
> Для `future` — или последнего объекта [shared_future](../standard-library/shared-future-class.md), присоединенного к задаче, запущенной с`std::async`, деструктор выполняет блокировку, если задача не была завершена; то есть он выполняет блокировку, если этот поток еще не вызвал `.get()` или `.wait()`, а задача по-прежнему выполняется. Если `future`, полученный из `std::async`, перемещается за пределы локальной области, другой код, который его использует, должен знать, что деструктор может заблокировать переход в общее состояние "ready".

Псевдофункция `INVOKE` определена в [\<functional>](../standard-library/functional.md).

## <a name="future_category"></a>  future_category

Возвращает ссылку на объект [error_category](../standard-library/error-category-class.md), характеризующий ошибки, связанные с объектами `future`.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a>  make_error_code

Создает [error_code](../standard-library/error-code-class.md) вместе с объектом [error_category](../standard-library/error-category-class.md), характеризующий ошибки [future](../standard-library/future-class.md).

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Параметры

*Errno* объект [future_errc](../standard-library/future-enums.md#future_errc) значение, идентифицирующее ошибку.

### <a name="return-value"></a>Возвращаемое значение

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a>  make_error_condition

Создает [error_condition](../standard-library/error-condition-class.md) вместе с объектом [error_category](../standard-library/error-category-class.md), характеризующий ошибки [future](../standard-library/future-class.md).

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Параметры

*Errno* объект [future_errc](../standard-library/future-enums.md#future_errc) значение, идентифицирующее ошибку.

### <a name="return-value"></a>Возвращаемое значение

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a>  swap

Меняет местами *связанное асинхронное состояние* одного объекта `promise` с объектом другого объекта.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Параметры

*Слева* слева `promise` объекта.

*Справа* справа `promise` объекта.

## <a name="see-also"></a>См. также

[\<future>](../standard-library/future.md)<br/>
