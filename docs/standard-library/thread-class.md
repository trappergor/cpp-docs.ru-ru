---
title: "Класс thread | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::thread
dev_langs:
- C++
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 848a51faa24498dd1505483894aa47ce959240a7
ms.lasthandoff: 02/24/2017

---
# <a name="thread-class"></a>Класс thread
Определяет объект, который позволяет наблюдать за потоком выполнения в приложении и управлять этим потоком.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class thread;
```  
  
## <a name="remarks"></a>Примечания  
 Объект `thread` можно использовать для наблюдения за потоком выполнения в приложении и управления этим потоком. Объект потока, который создан с помощью конструктора по умолчанию, не связан ни с каким потоком выполнения. Объект потока, который создается с использованием вызываемого объекта, создает новый поток выполнения и вызывает вызываемый объект в этом потоке. Объекты потока можно переместить, но не копировать. Следовательно, поток выполнения может быть связан только с одним объектом потока.  
  
 Каждый поток выполнения имеет уникальный идентификатор типа `thread::id`. Функция `this_thread::get_id` возвращает идентификатор вызывающего потока. Функция-член `thread::get_id` возвращает идентификатор потока, который управляется объектом потока. Для объекта потока, созданного конструктором по умолчанию, метод `thread::get_id` возвращает объект с одинаковым значением для всех объектов потока, созданных конструктором по умолчанию; это значение отличается от значения, которое возвращается `this_thread::get_id` для любого потока выполнения, который может быть присоединен во время вызова.  
  
## <a name="members"></a>Члены  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс thread::id](#thread__id_class)|Уникально идентифицирует соответствующий поток.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор thread::thread](#thread__thread_constructor)|Создает объект `thread`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод thread::detach](#thread__detach_method)|Отсоединяет связанный поток от объекта `thread`.|  
|[Метод thread::get_id](#thread__get_id_method)|Возвращает уникальный идентификатор связанного потока.|  
|[Метод thread::hardware_concurrency](#thread__hardware_concurrency_method)|Статический. Возвращает приблизительное число контекстов аппаратного потока.|  
|[Метод thread::join](#thread__join_method)|Блокируется до завершения соответствующего потока.|  
|[Метод thread::joinable](#thread__joinable_method)|Указывает, возможно ли присоединение связанного потока.|  
|[Метод thread::native_handle](#thread__native_handle_method)|Возвращает тип реализации, представляющий дескриптор потока.|  
|[Метод thread::swap](#thread__swap_method)|Заменяет состояние потока заданным объектом `thread`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[thread::operator=](#thread__operator_eq)|Связывает поток с текущим объектом `thread`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** thread  
  
 **Пространство имен:** std  
  
##  <a name="a-namethreaddetachmethoda--threaddetach-method"></a><a name="thread__detach_method"></a> Метод thread::detach  
 Отсоединяет связанный поток. Операционная система становится ответственной за освобождение ресурсов потока при завершении.  
  
```
void detach();
```  
  
### <a name="remarks"></a>Примечания  
 После вызова `detach` последующие вызовы [get_id](#thread__get_id_method) возвращают [id](#thread__id_class).  
  
 Если поток, связанный с вызываемым объектом, присоединить невозможно, функция создает ошибку [system_error](../standard-library/system-error-class.md) с кодом `invalid_argument`.  
  
 Если поток, связанный с вызывающим объектом, является недопустимым, функция создает ошибку `system_error` с кодом `no_such_process`.  
  
##  <a name="a-namethreadgetidmethoda--threadgetid-method"></a><a name="thread__get_id_method"></a> Метод thread::get_id  
 Возвращает уникальный идентификатор связанного потока.  
  
```
id get_id() const noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [thread::id](#thread__id_class), уникально идентифицирующий связанный поток, или `thread::id()`, если с объектом не связан никакой поток.  
  
##  <a name="a-namethreadhardwareconcurrencymethoda--threadhardwareconcurrency-method"></a><a name="thread__hardware_concurrency_method"></a> Метод thread::hardware_concurrency  
 Статический метод, который возвращает приблизительное число контекстов аппаратного потока.  
  
```
static unsigned int hardware_concurrency() noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Приблизительное число контекстов аппаратного потока. Если значение не может быть вычислено или не является правильно определенным, этот метод возвращает значение 0.  
  
##  <a name="a-namethreadidclassa--threadid-class"></a><a name="thread__id_class"></a> Класс thread::id  
 Предоставляет уникальный идентификатор для каждого потока выполнения в процессе.  
  
```
class thread::id {
    id() noexcept;
};
```  
  
### <a name="remarks"></a>Примечания  
 Конструктор по умолчанию создает объект, который не равен объекту `thread::id` ни для какого из существующих потоков.  
  
 Все созданные конструктором по умолчанию объекты `thread::id` равны.  
  
##  <a name="a-namethreadjoinmethoda--threadjoin-method"></a><a name="thread__join_method"></a> Метод thread::join  
 Блокируется до завершения потока выполнения, связанного с вызывающим объектом.  
  
```
void join();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызов завершается успешно, последующие вызовы [get_id](#thread__get_id_method) для вызывающего объекта возвращают значение по умолчанию [thread::id](#thread__id_class), которое не равно значению `thread::id` ни одного из существующих потоков; если вызов завершается неудачно, возвращаемое `get_id` значение остается неизменным.  
  
##  <a name="a-namethreadjoinablemethoda--threadjoinable-method"></a><a name="thread__joinable_method"></a> Метод thread::joinable  
 Указывает, возможно ли *присоединение* связанного потока.  
  
```
bool joinable() const noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если связанный поток *присоединяем*; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Объект потока *присоединяем*, если `get_id() != id()`.  
  
##  <a name="a-namethreadnativehandlemethoda--threadnativehandle-method"></a><a name="thread__native_handle_method"></a> Метод thread::native_handle  
 Возвращает тип реализации, представляющий дескриптор потока. Дескриптор потока может использоваться разными способами в зависимости от реализации.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `native_handle_type` определяется как `HANDLE` Win32, который приводится к `void *`.  
  
##  <a name="a-namethreadoperatoreqa--threadoperator"></a><a name="thread__operator_eq"></a> thread::operator=  
 Связывает поток заданного объекта с текущим объектом.  
  
```
thread& operator=(thread&& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Other`  
 Объект `thread`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `*this`  
  
### <a name="remarks"></a>Примечания  
 Вызовы метода удаляются окончательно, если вызывающий объект присоединяем.  
  
 После установления связи `Other` присваивается состояние, созданное по умолчанию.  
  
##  <a name="a-namethreadswapmethoda--threadswap-method"></a><a name="thread__swap_method"></a> Метод thread::swap  
 Заменяет состояние потока состоянием заданного объекта `thread`.  
  
```
void swap(thread& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Other`  
 Объект `thread`.  
  
##  <a name="a-namethreadthreadconstructora--threadthread-constructor"></a><a name="thread__thread_constructor"></a> Конструктор thread::thread  
 Создает объект `thread`.  
  
```
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `F`  
 Определяемая приложением функция, которая должна быть выполнена потоком.  
  
 `A`  
 Список аргументов, которые необходимо передать `F`.  
  
 `Other`  
 Существующий объект `thread`.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает объект, который не связан с потоком выполнения. Значение, возвращаемое вызовом `get_id` для созданного объекта, — это `thread::id()`.  
  
 Второй конструктор создает объект, который связан с новым потоком выполнения, и выполняет псевдофункцию `INVOKE`, которая определена в [\<functional>](../standard-library/functional.md). Если не хватает ресурсов для начала нового потока, функция создает объект [system_error](../standard-library/system-error-class.md) с кодом ошибки `resource_unavailable_try_again`. Если вызов `F` завершается с неперехваченным исключением, вызывается метод [terminate](../standard-library/exception-functions.md#terminate).  
  
 Третий конструктор создает объект, связанный с потоком, который, в свою очередь, связан с `Other`. `Other` затем присваивается состояние, созданное по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread>](../standard-library/thread.md)




