---
title: "Класс reader_writer_lock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
dev_langs:
- C++
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: b5107923baa7d22e6a98c6617a22a883c4d84125
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="readerwriterlock-class"></a>Класс reader_writer_lock
Блокировка чтения или записи на основе очередей с предпочтением записи только с локальным вращением. Блокировка предоставляет модулям записи доступ в порядке поступления и блокирует доступ модулей чтения при постоянной нагрузке модулей записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class reader_writer_lock;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс reader_writer_lock::scoped_lock](#scoped_lock_class)|Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокирует объекты, как модуль записи.|  
|[Класс reader_writer_lock::scoped_lock_read](#scoped_lock_read_class)|Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокировать объекты чтения.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[reader_writer_lock](#ctor)|Создает новый `reader_writer_lock` объекта.|  
|[~ reader_writer_lock деструктор](#dtor)|Уничтожает `reader_writer_lock` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[lock](#lock)|Получает блокировку чтения записи разработчику.|  
|[lock_read](#lock_read)|Получает блокировку чтения записи читателей. Если имеются писатели, активные читатели должны подождать, пока они выполняются. Средство чтения просто регистрирует интерес в блокировке и ожидает записи для его освобождения.|  
|[try_lock](#try_lock)|Пытается получить блокировку чтения записи в качестве модуля записи без блокировки.|  
|[try_lock_read](#try_lock_read)|Пытается получить блокировку чтения записи в качестве читателя без блокировки.|  
|[unlock](#unlock)|Снимает блокировку чтения записи, в зависимости от того, кто именно заблокировал, средство чтения или записи.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `reader_writer_lock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="lock"></a>Блокировка 

 Получает блокировку чтения записи разработчику.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Примечания  
 Часто безопаснее использовать [scoped_lock](#scoped_lock_class) конструкцию, чтобы получить и освободить `reader_writer_lock` объект как записывающий исключение безопасным способом.  
  
 После того как средство записи пытается получить блокировку, все будущие читатели будут блокироваться до тех пор, пока средства записи не получат и не снимут блокировку. Эта блокировка смещен в сторону записи и исключает доступ читателей под постоянной нагрузкой модулей записи.  
  
 Модули записи сцепляются, чтобы записи, выход из блокировки освобождает следующей записи в строке.  
  
 Если блокировка уже захвачена вызывающий контекст [improper_lock](improper-lock-class.md) будет создано исключение.  
  
##  <a name="lock_read"></a>lock_read 

 Получает блокировку чтения записи читателей. Если имеются писатели, активные читатели должны подождать, пока они выполняются. Средство чтения просто регистрирует интерес в блокировке и ожидает записи для его освобождения.  
  
```
void lock_read();
```  
  
### <a name="remarks"></a>Примечания  
 Часто безопаснее использовать [scoped_lock_read](#scoped_lock_read_class) конструкцию, чтобы получить и освободить `reader_writer_lock` объект как читатель исключение безопасным способом.  
  
 Если имеются ожидающие блокировку писатели, средство чтения будет ожидать, пока все писатели в строке получат и освободят блокировку. Эта блокировка смещен в сторону записи и исключает доступ читателей под постоянной нагрузкой модулей записи.  
  
##  <a name="ctor"></a>reader_writer_lock 

 Создает новый `reader_writer_lock` объекта.  
  
```
reader_writer_lock();
```  
  
##  <a name="dtor"></a>~ reader_writer_lock 

 Уничтожает `reader_writer_lock` объекта.  
  
```
~reader_writer_lock();
```  
  
### <a name="remarks"></a>Примечания  
 Ожидается, что больше не блокировку при выполнении деструктора. По-прежнему позволяя блокировки чтения записи приводит к неопределенному блокировка удерживается результатов к неопределенному поведению.  
  
##  <a name="scoped_lock_class"></a>Класс reader_writer_lock::scoped_lock  
 Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокирует объекты, как модуль записи.  
  
```
class scoped_lock;
``` 
## <a name="scoped_lock_ctor"></a>scoped_lock::scoped_lock 

Создает `scoped_lock` объекта и получает `reader_writer_lock` объект, передаваемый в `_Reader_writer_lock` параметра, как модуль записи. Если блокировка удерживается другим потоком, этот вызов блокируется.  
  
  
```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Параметры  
 `_Reader_writer_lock`  
 `reader_writer_lock` Объект для получения как модуль записи.  
  
## <a name="scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock 

Уничтожает `reader_writer_lock` объекта и освободит блокировку, переданную в конструкторе.   

```
~scoped_lock();
```  
  
##  <a name="scoped_lock_read_class"></a>Класс reader_writer_lock::scoped_lock_read  
 Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокировать объекты чтения.  
  
```
class scoped_lock_read;
```  
  
##  <a name="try_lock"></a>try_lock 

 Пытается получить блокировку чтения записи в качестве модуля записи без блокировки.  

## <a name="scoped_lock_read_ctor"></a>scoped_lock_read::scoped_lock_read 

Создает `scoped_lock_read` объекта и получает `reader_writer_lock` объект, передаваемый в `_Reader_writer_lock` параметр чтения. Если блокировка удерживается другим потоком как модуль записи или ожидаются модулями записи, этот вызов блокируется.  
  
```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Параметры  
 `_Reader_writer_lock`  
 `reader_writer_lock` Объект для получения как средство чтения.  
  
## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">reader_writer_lock::scoped_lock_read:: ~ scoped_lock_read деструктор
Уничтожает `scoped_lock_read` объекта и освободит блокировку, переданную в конструкторе.  

```
~scoped_lock_read();
```  
  
## <a name="try_lock"></a>try_lock 

```
bool try_lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если блокировка была получена, значение `true`; в противном случае — значение `false`.  
  
##  <a name="try_lock_read"></a>try_lock_read 

 Пытается получить блокировку чтения записи в качестве читателя без блокировки.  
  
```
bool try_lock_read();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если блокировка была получена, значение `true`; в противном случае — значение `false`.  
  
##  <a name="unlock"></a>разблокировать 

 Снимает блокировку чтения записи, в зависимости от того, кто именно заблокировал, средство чтения или записи.  
  
```
void unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Если имеются ожидающие блокировку писатели, выпуск блокировки всегда перейдет к следующей записи в порядке FIFO. Эта блокировка смещен в сторону записи и исключает доступ читателей под постоянной нагрузкой модулей записи.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс critical_section](critical-section-class.md)

