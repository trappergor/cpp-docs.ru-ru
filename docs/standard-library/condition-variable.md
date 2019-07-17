---
title: '&lt;condition_variable&gt;'
ms.date: 11/04/2016
f1_keywords:
- <condition_variable>
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
ms.openlocfilehash: ed98966f651df76078fa47b05f5a2d8ae1b71d05
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244581"
---
# <a name="ltconditionvariablegt"></a>&lt;condition_variable&gt;

Определяет классы [condition_variable](../standard-library/condition-variable-class.md) и [condition_variable_any](../standard-library/condition-variable-any-class.md) , используемые для создания объектов, которые ожидают условие, чтобы стать true.

Этот заголовок использует среду выполнения с параллелизмом (ConcRT), чтобы ее можно было использовать вместе с другими механизмами ConcRT. Дополнительные сведения о ConcRT см. в статье [Среда выполнения с параллелизмом](../parallel/concrt/concurrency-runtime.md).

## <a name="requirements"></a>Требования

**Заголовок:** \<condition_variable >

**Пространство имен:** std

> [!NOTE]
> В коде, скомпилированном с помощью **/CLR**, этот заголовок блокируется.

### <a name="remarks"></a>Примечания

Код, который ожидает переменную условия, должен также использовать `mutex`. Вызывающий поток должен заблокировать `mutex` перед вызовом функции, ожидающей переменную условия. Затем блокируется `mutex` при возврате вызванной функции. `mutex` не блокируется, пока поток ожидает, когда условие станет истинным. Таким образом, нет никаких непредсказуемых результатов, все потоки, ожидающие переменную условия, должны использовать один и тот же объект `mutex`.

Объекты типа `condition_variable_any` можно использовать с mutex любого типа. Используемый тип mutex не должен предоставлять метод `try_lock`. Объекты типа `condition_variable` можно использовать с mutex типа `unique_lock<mutex>`. Объекты этого типа могут быть быстрее, чем объекты типа `condition_variable_any<unique_lock<mutex>>`.

Чтобы дождаться события, сначала блокируется mutex, а затем вызывается один из методов `wait` в переменной условия. Вызов `wait` блокируется, пока другой поток не сигнализирует о переменной условия.

*Ложные активации* возникают, когда потоки, ожидающие переменных условия, становятся разблокированными без соответствующих уведомлений. Чтобы распознать такие ложные активации, код, который ожидает, пока условие станет истинным, должен явно проверять это условие при возврате кода из функции wait. Обычно это делается с помощью цикла; можно использовать `wait(unique_lock<mutex>& lock, Predicate pred)` для выполнения этого цикла.

```cpp
while (condition is false)
    wait for condition variable;
```

Классы `condition_variable_any` и `condition_variable` имеют по три метода, которые ожидают условие.

- Метод `wait` ожидает в течение неограниченного времени.

- Метод `wait_until` ожидает до указанного `time`.

- Метод `wait_for` ожидает в течение указанного `time interval`.

Каждый из этих методов имеет две перегруженные версии. Одна просто ожидает и может выполнить ложную активацию. Другая принимает дополнительный аргумент шаблона, который задает предикат. Метод не возвращает до предикат **true**.

Каждый класс также содержит два метода, которые используются для уведомления переменной условия, что его условие **true**.

- `notify_one` активирует один из потоков, ожидающий переменную условия.

- `notify_all` активирует все потоки, ожидающие переменную условия.

## <a name="functions-and-enums"></a>Функции и перечислений

```cpp
void notify_all_at_thread_exit(condition_variable& cond, unique_lock<mutex> lk);

enum class cv_status { no_timeout, timeout };
```

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Класс condition_variable](../standard-library/condition-variable-class.md)<br/>
[Класс condition_variable_any](../standard-library/condition-variable-any-class.md)<br/>
