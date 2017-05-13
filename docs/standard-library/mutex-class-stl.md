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
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: e08c7c13d1e182bc3299f11769eddb699b03ab3f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

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
|[Мьютекс](#mutex)|Создает объект `mutex`.|  
|[Деструктор mutex::~mutex](#dtormutex_destructor)|Освобождает ресурсы, используемые объектом `mutex`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|  
|[native_handle](#native_handle)|Возвращает тип реализации, представляющий дескриптор мьютекса.|  
|[try_lock](#try_lock)|Попытки получить права владельца объекта `mutex` без блокировки.|  
|[unlock](#unlock)|Освобождает права владения объектом `mutex`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<мьютекс >  
  
 **Пространство имен:** std  
  
##  <a name="lock"></a>Mutex::LOCK
 Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже является владельцем `mutex`, поведение не определено.  
  
##  <a name="mutex"></a>  Конструктор mutex::mutex  
 Создает объект `mutex`, который не заблокирован.  
  
```cpp  
constexpr mutex() noexcept;
```  
  
##  <a name="dtormutex_destructor"></a>  Деструктор mutex::~mutex  
 Освобождает все ресурсы, используемые объектом `mutex`.  
  
```cpp  
~mutex();
```  
  
### <a name="remarks"></a>Примечания  
 Если при выполнении деструктора объект заблокирован, поведение не определено.  
  
##  <a name="native_handle"></a>Mutex::native_handle
 Возвращает тип реализации, представляющий дескриптор мьютекса. Дескриптор мьютекса может использоваться разными способами в зависимости от реализации.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `native_handle_type`определяется как `Concurrency::critical_section *`, которое приводится к `void *`.  
  
##  <a name="try_lock"></a>Mutex::try_lock
 Попытки получить права владельца объекта `mutex` без блокировки.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод успешно получает права владельца `mutex`; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже является владельцем `mutex`, поведение не определено.  
  
##  <a name="unlock"></a>Mutex::Unlock
 Освобождает права владения объектом `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток не является владельцем `mutex`, поведение не определено.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




