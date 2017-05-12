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
- thread/std::thread::id Class
- thread/std::thread::thread
- thread/std::thread::detach
- thread/std::thread::get_id
- thread/std::thread::hardware_concurrency
- thread/std::thread::join
- thread/std::thread::joinable
- thread/std::thread::native_handle
- thread/std::thread::swap
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: b1c5282d284a70917c6c14511bacda305180d778
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

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
|[Класс thread::id](#id_class)|Уникально идентифицирует соответствующий поток.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[thread](#thread)|Создает объект `thread`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[отсоединение](#detach)|Отсоединяет связанный поток от объекта `thread`.|  
|[get_id](#get_id)|Возвращает уникальный идентификатор связанного потока.|  
|[hardware_concurrency](#hardware_concurrency)|Статический. Возвращает приблизительное число контекстов аппаратного потока.|  
|[join](#join)|Блокируется до завершения соответствующего потока.|  
|[joinable](#joinable)|Указывает, возможно ли присоединение связанного потока.|  
|[native_handle](#native_handle)|Возвращает тип реализации, представляющий дескриптор потока.|  
|[swap](#swap)|Заменяет состояние потока заданным объектом `thread`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[thread::operator=](#op_eq)|Связывает поток с текущим объектом `thread`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<поток >  
  
 **Пространство имен:** std  
  
##  <a name="detach"></a>Thread::Detach
 Отсоединяет связанный поток. Операционная система становится ответственной за освобождение ресурсов потока при завершении.  
  
```
void detach();
```  
  
### <a name="remarks"></a>Примечания  
 После вызова `detach` последующие вызовы [get_id](#get_id) возвращают [id](#id_class).  
  
 Если поток, связанный с вызываемым объектом, присоединить невозможно, функция создает ошибку [system_error](../standard-library/system-error-class.md) с кодом `invalid_argument`.  
  
 Если поток, связанный с вызывающим объектом, является недопустимым, функция создает ошибку `system_error` с кодом `no_such_process`.  
  
##  <a name="get_id"></a>Thread::get_id
 Возвращает уникальный идентификатор связанного потока.  
  
```
id get_id() const noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [thread::id](#id_class), уникально идентифицирующий связанный поток, или `thread::id()`, если с объектом не связан никакой поток.  
  
##  <a name="hardware_concurrency"></a>Thread::hardware_concurrency
 Статический метод, который возвращает приблизительное число контекстов аппаратного потока.  
  
```
static unsigned int hardware_concurrency() noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Приблизительное число контекстов аппаратного потока. Если значение не может быть вычислено или не является правильно определенным, этот метод возвращает значение 0.  
  
##  <a name="id_class"></a> Класс thread::id  
 Предоставляет уникальный идентификатор для каждого потока выполнения в процессе.  
  
```
class thread::id {
    id() noexcept;
};
```  
  
### <a name="remarks"></a>Примечания  
 Конструктор по умолчанию создает объект, который не равен объекту `thread::id` ни для какого из существующих потоков.  
  
 Все созданные конструктором по умолчанию объекты `thread::id` равны.  
  
##  <a name="join"></a>Thread::JOIN
 Блокируется до завершения потока выполнения, связанного с вызывающим объектом.  
  
```
void join();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызов завершается успешно, последующие вызовы [get_id](#get_id) для вызывающего объекта возвращают значение по умолчанию [thread::id](#id_class), которое не равно значению `thread::id` ни одного из существующих потоков; если вызов завершается неудачно, возвращаемое `get_id` значение остается неизменным.  
  
##  <a name="joinable"></a>Thread::joinable
 Указывает, возможно ли *присоединение* связанного потока.  
  
```
bool joinable() const noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если связанный поток *присоединяем*; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Объект потока *присоединяем*, если `get_id() != id()`.  
  
##  <a name="native_handle"></a>Thread::native_handle
 Возвращает тип реализации, представляющий дескриптор потока. Дескриптор потока может использоваться разными способами в зависимости от реализации.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `native_handle_type` определяется как `HANDLE` Win32, который приводится к `void *`.  
  
##  <a name="op_eq"></a> thread::operator=  
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
  
##  <a name="swap"></a>Thread::Swap
 Заменяет состояние потока состоянием заданного объекта `thread`.  
  
```
void swap(thread& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Other`  
 Объект `thread`.  
  
##  <a name="thread"></a> Конструктор thread::thread  
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




