---
title: "Класс mutex (Стандартная библиотека C++ ) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::mutex
dev_langs:
- C++
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ff3e7e71c678ffc9bdead79ec56ad94f8e297a16
ms.lasthandoff: 02/24/2017

---
# <a name="mutex-class-c-standard-library"></a>Класс mutex (Стандартная библиотека C++)
Представляет *тип мьютекса*. Используйте объекты этого типа для принудительного взаимного исключения в программе.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class mutex;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор mutex::mutex](#mutex__mutex_constructor)|Создает объект `mutex`.|  
|[Деструктор mutex::~mutex](#mutex___dtormutex_destructor)|Освобождает ресурсы, используемые объектом `mutex`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод mutex::lock](#mutex__lock_method)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|  
|[Метод mutex::native_handle](#mutex__native_handle_method)|Возвращает тип реализации, представляющий дескриптор мьютекса.|  
|[Метод mutex::try_lock](#mutex__try_lock_method)|Попытки получить права владельца объекта `mutex` без блокировки.|  
|[Метод mutex::unlock](#mutex__unlock_method)|Освобождает права владения объектом `mutex`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
##  <a name="a-namemutexlockmethoda--mutexlock-method"></a><a name="mutex__lock_method"></a>  Метод mutex::lock  
 Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже является владельцем `mutex`, поведение не определено.  
  
##  <a name="a-namemutexmutexconstructora--mutexmutex-constructor"></a><a name="mutex__mutex_constructor"></a>  Конструктор mutex::mutex  
 Создает объект `mutex`, который не заблокирован.  
  
```cpp  
constexpr mutex() noexcept;
```  
  
##  <a name="a-namemutexdtormutexdestructora--mutexmutex-destructor"></a><a name="mutex___dtormutex_destructor"></a>  Деструктор mutex::~mutex  
 Освобождает все ресурсы, используемые объектом `mutex`.  
  
```cpp  
~mutex();
```  
  
### <a name="remarks"></a>Примечания  
 Если при выполнении деструктора объект заблокирован, поведение не определено.  
  
##  <a name="a-namemutexnativehandlemethoda--mutexnativehandle-method"></a><a name="mutex__native_handle_method"></a>  Метод mutex::native_handle  
 Возвращает тип реализации, представляющий дескриптор мьютекса. Дескриптор мьютекса может использоваться разными способами в зависимости от реализации.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `native_handle_type`определяется как `Concurrency::critical_section *`, которое приводится к `void *`.  
  
##  <a name="a-namemutextrylockmethoda--mutextrylock-method"></a><a name="mutex__try_lock_method"></a>  Метод mutex::try_lock  
 Попытки получить права владельца объекта `mutex` без блокировки.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод успешно получает права владельца `mutex`; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже является владельцем `mutex`, поведение не определено.  
  
##  <a name="a-namemutexunlockmethoda--mutexunlock-method"></a><a name="mutex__unlock_method"></a>  Метод mutex::unlock  
 Освобождает права владения объектом `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток не является владельцем `mutex`, поведение не определено.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




