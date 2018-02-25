---
title: "Класс mutex (Стандартная библиотека C++ ) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::mutex [C++]
- std::mutex [C++], mutex
- std::mutex [C++], lock
- std::mutex [C++], native_handle
- std::mutex [C++], try_lock
- std::mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: acc1d6625bcf8d76f88e8571cba34ef974856177
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="mutex-class-c-standard-library"></a>Класс mutex (Стандартная библиотека C++)
Представляет *тип мьютекса*. Используйте объекты этого типа для принудительного взаимного исключения в программе.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class mutex;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Мьютекс](#mutex)|Создает объект `mutex`.|  
|[Деструктор mutex::~mutex](#dtormutex_destructor)|Освобождает ресурсы, используемые объектом `mutex`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|  
|[native_handle](#native_handle)|Возвращает тип реализации, представляющий дескриптор мьютекса.|  
|[try_lock](#try_lock)|Попытки получить права владельца объекта `mutex` без блокировки.|  
|[unlock](#unlock)|Освобождает права владения объектом `mutex`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<мьютекс >  
  
 **Пространство имен:** std  
  
##  <a name="lock"></a>  mutex::lock
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
  
##  <a name="native_handle"></a>  mutex::native_handle
 Возвращает тип реализации, представляющий дескриптор мьютекса. Дескриптор мьютекса может использоваться разными способами в зависимости от реализации.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `native_handle_type`определяется как `Concurrency::critical_section *`, которое приводится к `void *`.  
  
##  <a name="try_lock"></a>  mutex::try_lock
 Попытки получить права владельца объекта `mutex` без блокировки.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод успешно получает права владельца `mutex`; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже является владельцем `mutex`, поведение не определено.  
  
##  <a name="unlock"></a>  mutex::unlock
 Освобождает права владения объектом `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток не является владельцем `mutex`, поведение не определено.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



