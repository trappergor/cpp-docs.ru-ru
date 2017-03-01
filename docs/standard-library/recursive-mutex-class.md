---
title: "Класс recursive_mutex | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_mutex
dev_langs:
- C++
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
caps.latest.revision: 9
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
ms.openlocfilehash: c82c8302be5d3e01de90adda2049a022100b8443
ms.lasthandoff: 02/24/2017

---
# <a name="recursivemutex-class"></a>Класс recursive_mutex
Представляет *тип мьютекса*. В отличие от класса [mutex](../standard-library/mutex-class-stl.md), поведение вызовов методов блокировки для объектов, которые уже заблокированы, четко определено.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class recursive_mutex;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор recursive_mutex](#recursive_mutex__recursive_mutex_constructor)|Создает объект `recursive_mutex`.|  
|[Деструктор ~recursive_mutex](#recursive_mutex___dtorrecursive_mutex_destructor)|Освобождает все ресурсы, используемые объектом `recursive_mutex`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[lock](#recursive_mutex__lock_method)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца мьютекса.|  
|[try_lock](#recursive_mutex__try_lock_method)|Попытки получить права владельца мьютекса без блокировки.|  
|[unlock](#recursive_mutex__unlock_method)|Освобождает права владения мьютексом.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
##  <a name="a-namerecursivemutexlockmethoda--lock"></a><a name="recursive_mutex__lock_method"></a>  lock  
 Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает значение и предыдущая блокировка остается в силе.  
  
##  <a name="a-namerecursivemutexrecursivemutexconstructora--recursivemutex"></a><a name="recursive_mutex__recursive_mutex_constructor"></a>  recursive_mutex  
 Создает объект `recursive_mutex`, который не заблокирован.  
  
```cpp  
recursive_mutex();
```  
  
##  <a name="a-namerecursivemutexdtorrecursivemutexdestructora--recursivemutex"></a><a name="recursive_mutex___dtorrecursive_mutex_destructor"></a>  ~recursive_mutex  
 Освобождает все ресурсы, используемые объектом.  
  
```cpp  
~recursive_mutex();
```  
  
### <a name="remarks"></a>Примечания  
 Если при выполнении деструктора объект заблокирован, поведение не определено.  
  
##  <a name="a-namerecursivemutextrylockmethoda--trylock"></a><a name="recursive_mutex__try_lock_method"></a>  try_lock  
 Попытки получить права владельца объекта `mutex` без блокировки.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если метод успешно получает права владельца `mutex` или если вызывающий поток уже владеет `mutex`; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает `true` и предыдущая блокировка остается в силе.  
  
##  <a name="a-namerecursivemutexunlockmethoda--unlock"></a><a name="recursive_mutex__unlock_method"></a>  unlock  
 Освобождает права владения мьютексом.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод освобождает владение `mutex` только после его вызова столько раз, сколько [lock](#recursive_mutex__lock_method) и [try_lock](#recursive_mutex__try_lock_method) были успешно вызваны для объекта`recursive_mutex`.  
  
 Если вызывающий поток не является владельцем `mutex`, поведение не определено.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




