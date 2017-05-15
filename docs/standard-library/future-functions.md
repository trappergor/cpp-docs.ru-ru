---
title: "Функции &lt;future&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: c542e696e0e5ddef350d40b45fe16f4c3a77882d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="ltfuturegt-functions"></a>Функции &lt;future&gt;
||||  
|-|-|-|  
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|  
|[make_error_condition](#make_error_condition)|[swap](#swap)|  
  
##  <a name="async"></a>  async  
 Представляет *асинхронного поставщика*.  
  
```
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```  
  
### <a name="parameters"></a>Параметры  
 `policy`  
 Значение [launch](../standard-library/future-enums.md#launch).  
  
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
  
 Если `policy` — `launch::any`, функция может выбрать `launch::async` или `launch::deferred`. В этой реализации функция использует `launch::async`.  
  
 Если `policy` — `launch::async`, функция создает поток, который вычисляет `INVOKE(dfn, dargs..., Ty)`. Функция выполняет возврат после создания потока, не ожидая результатов. Если система не может запустить новый поток, функция создает [system_error](../standard-library/system-error-class.md) с кодом ошибки `resource_unavailable_try_again`.  
  
 Если `policy` — `launch::deferred`, функция помечает свое связанное асинхронное состояние как имеющую *отложенную функцию* и возвращается. Первый вызов любой функции без учета времени, которая ожидает наступления связанного асинхронного состояния "ready", фактически вызывает отложенную функцию путем оценки `INVOKE(dfn, dargs..., Ty)`.  
  
 Во всех случаях связанное асинхронное состояние объекта `future` не становится *ready* до завершения оценки `INVOKE(dfn, dargs..., Ty)` либо путем создания исключения, либо путем обычного возвращения. Результатом связанного асинхронного состояния получается исключение, если таковое было создано, или любое значение, возвращаемое при оценке.  
  
> [!NOTE]
>  Для `future` — или последнего объекта [shared_future](../standard-library/shared-future-class.md), присоединенного к задаче, запущенной с`std::async`, деструктор выполняет блокировку, если задача не была завершена; то есть он выполняет блокировку, если этот поток еще не вызвал `.get()` или `.wait()`, а задача по-прежнему выполняется. Если `future`, полученный из `std::async`, перемещается за пределы локальной области, другой код, который его использует, должен знать, что деструктор может заблокировать переход в общее состояние "ready".  
  
 Псевдофункция `INVOKE` определена в [\<functional>](../standard-library/functional.md).  
  
##  <a name="future_category"></a>  future_category  
 Возвращает ссылку на объект [error_category](../standard-library/error-category-class.md), характеризующий ошибки, связанные с объектами `future`.  
  
```
const error_category& future_category() noexcept;
```  
  
##  <a name="make_error_code"></a>  make_error_code  
 Создает [error_code](../standard-library/error-code-class.md) вместе с объектом [error_category](../standard-library/error-category-class.md), характеризующий ошибки [future](../standard-library/future-class.md).  
  
```
inline error_code make_error_code(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Errno`  
 Значение [future_errc](../standard-library/future-enums.md#future_errc), идентифицирующее ошибку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `error_code(static_cast<int>(Errno), future_category());`  
  
##  <a name="make_error_condition"></a>  make_error_condition  
 Создает [error_condition](../standard-library/error-condition-class.md) вместе с объектом [error_category](../standard-library/error-category-class.md), характеризующий ошибки [future](../standard-library/future-class.md).  
  
```
inline error_condition make_error_condition(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Errno`  
 Значение [future_errc](../standard-library/future-enums.md#future_errc), идентифицирующее ошибку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `error_condition(static_cast<int>(Errno), future_category());`  
  
##  <a name="swap"></a>  swap  
 Меняет местами *связанное асинхронное состояние* одного объекта `promise` с объектом другого объекта.  
  
```
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Left`  
 Левый объект `promise`.  
  
 `Right`  
 Правой объект `promise`.  
  
## <a name="see-also"></a>См. также  
 [\<future>](../standard-library/future.md)




