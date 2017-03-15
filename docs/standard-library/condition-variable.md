---
title: "&lt;condition_variable&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <condition_variable>
dev_langs:
- C++
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 6002dcd4cd0fe35c99ce56a1d9fd3b5f3c23dd08
ms.lasthandoff: 02/24/2017

---
# <a name="ltconditionvariablegt"></a>&lt;condition_variable&gt;
Определяет классы [condition_variable](../standard-library/condition-variable-class.md) и [condition_variable_any](../standard-library/condition-variable-any-class.md) , используемые для создания объектов, которые ожидают условие, чтобы стать true.  
  
 Этот заголовок использует среду выполнения с параллелизмом (ConcRT), чтобы ее можно было использовать вместе с другими механизмами ConcRT. Дополнительные сведения о ConcRT см. в статье [Среда выполнения с параллелизмом](../parallel/concrt/concurrency-runtime.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
#include <condition_variable>  
```  
  
> [!NOTE]
>  В коде, который компилируется с помощью **/CLR**, этот заголовок будет заблокирован.  
  
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
  
 Каждый из этих методов имеет две перегруженные версии. Одна просто ожидает и может выполнить ложную активацию. Другая принимает дополнительный аргумент шаблона, который задает предикат. Возврат метода не происходит, пока этот предикат не получит значение `true`.  
  
 Каждый класс также имеет два метода, которые используются для уведомления переменной условия, что его условие `true`.  
  
- `notify_one` активирует один из потоков, ожидающий переменную условия.  
  
- `notify_all` активирует все потоки, ожидающие переменную условия.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Класс condition_variable](../standard-library/condition-variable-class.md)   
 [Класс condition_variable_any](../standard-library/condition-variable-any-class.md)

