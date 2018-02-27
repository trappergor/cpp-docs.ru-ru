---
title: "Класс reader_writer_lock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75bea63c6e2f73ebd58434874758c4f20444958a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="readerwriterlock-class"></a>Класс reader_writer_lock
Блокировка чтения или записи на основе очередей с предпочтением записи только с локальным вращением. Блокировка предоставляет модулям записи доступ в порядке поступления и блокирует доступ модулей чтения при постоянной нагрузке модулей записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class reader_writer_lock;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[reader_writer_lock::scoped_lock Class](#scoped_lock_class)|Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокирует объекты, как средство записи.|  
|[reader_writer_lock::scoped_lock_read Class](#scoped_lock_read_class)|Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокировать объекты в качестве читателя.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[reader_writer_lock](#ctor)|Создает новое `reader_writer_lock` объекта.|  
|[~reader_writer_lock Destructor](#dtor)|Уничтожает `reader_writer_lock` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[lock](#lock)|Получает блокировку чтения записи, как средство записи.|  
|[lock_read](#lock_read)|Чтения получает блокировку чтения записи. При наличии модулей записи, активные читатели должны подождать, пока они выполняются. Средство чтения просто регистрирует интерес в блокировке и ожидает записи для ее снятия.|  
|[try_lock](#try_lock)|Пытается получить блокировку чтения записи в качестве модуля записи без блокировки.|  
|[try_lock_read](#try_lock_read)|Пытается получить блокировку чтения записи в качестве читателя без блокировки.|  
|[unlock](#unlock)|Снимает блокировку чтения записи, в зависимости от того, кто именно заблокировал его, чтения или записи.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `reader_writer_lock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="lock"></a> Блокировка 

 Получает блокировку чтения записи, как средство записи.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Примечания  
 Часто безопаснее использовать [scoped_lock](#scoped_lock_class) конструкцию, чтобы получить и освободить `reader_writer_lock` объект как модуль записи, исключение безопасным способом.  
  
 После того как средство записи пытается получить блокировку, все будущие читатели будут блокироваться до тех пор, пока средства записи не получат и не снимут блокировку. Эта блокировка склонна модулей записи и может привести к дефициту чтения при постоянной нагрузке модулей записи.  
  
 Модули записи соединяются так, что модуль записи, выход из блокировки освобождает следующей записи в строке.  
  
 Если блокировка уже захвачена вызывающий контекст [improper_lock](improper-lock-class.md) будет создано исключение.  
  
##  <a name="lock_read"></a> lock_read 

 Чтения получает блокировку чтения записи. При наличии модулей записи, активные читатели должны подождать, пока они выполняются. Средство чтения просто регистрирует интерес в блокировке и ожидает записи для ее снятия.  
  
```
void lock_read();
```  
  
### <a name="remarks"></a>Примечания  
 Часто безопаснее использовать [scoped_lock_read](#scoped_lock_read_class) конструкцию, чтобы получить и освободить `reader_writer_lock` объект как модуль чтения к исключению безопасным способом.  
  
 Если имеются ожидающие блокировку писатели, средство чтения будет ждать всех модулей записи в строке получат и освободят блокировку. Эта блокировка склонна модулей записи и может привести к дефициту чтения при постоянной нагрузке модулей записи.  
  
##  <a name="ctor"></a> reader_writer_lock 

 Создает новое `reader_writer_lock` объекта.  
  
```
reader_writer_lock();
```  
  
##  <a name="dtor"></a> ~reader_writer_lock 

 Уничтожает `reader_writer_lock` объекта.  
  
```
~reader_writer_lock();
```  
  
### <a name="remarks"></a>Примечания  
 Ожидается, что больше не блокировки при выполнении деструктора. По-прежнему позволяя блокировки чтения записи приводит к неопределенному блокировки удерживаются результатов к неопределенному поведению.  
  
##  <a name="scoped_lock_class"></a>  reader_writer_lock::scoped_lock Class  
 Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокирует объекты, как средство записи.  
  
```
class scoped_lock;
``` 
## <a name="scoped_lock_ctor"></a> scoped_lock::scoped_lock 

Создает `scoped_lock` объекта и получает `reader_writer_lock` переданный объект `_Reader_writer_lock` параметр как средство записи. Если блокировка удерживается другим потоком, этот вызов блокируется.  
  
  
```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Параметры  
 `_Reader_writer_lock`  
 `reader_writer_lock` Объект для получения как средство записи.  
  
## <a name="scoped_lock_dtor"></a> scoped_lock::~scoped_lock 

Уничтожает `reader_writer_lock` объекта и снимает блокировку, переданную в конструкторе.   

```
~scoped_lock();
```  
  
##  <a name="scoped_lock_read_class"></a>  reader_writer_lock::scoped_lock_read Class  
 Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокировать объекты в качестве читателя.  
  
```
class scoped_lock_read;
```  
  
##  <a name="try_lock"></a> try_lock 

 Пытается получить блокировку чтения записи в качестве модуля записи без блокировки.  

## <a name="scoped_lock_read_ctor"></a> scoped_lock_read::scoped_lock_read 

Создает `scoped_lock_read` объекта и получает `reader_writer_lock` переданный объект `_Reader_writer_lock` параметр как средство чтения. Если блокировка удерживается другим потоком как модуль записи или ожидаются модулями записи, этот вызов блокируется.  
  
```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Параметры  
 `_Reader_writer_lock`  
 `reader_writer_lock` Объект для получения как модуль чтения.  
  
## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">  reader_writer_lock::scoped_lock_read::~scoped_lock_read Destructor
Уничтожает `scoped_lock_read` объекта и снимает блокировку, переданную в конструкторе.  

```
~scoped_lock_read();
```  
  
## <a name="try_lock"></a> try_lock 

```
bool try_lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если была получена блокировка, значение `true`; в противном случае — значение `false`.  
  
##  <a name="try_lock_read"></a> try_lock_read 

 Пытается получить блокировку чтения записи в качестве читателя без блокировки.  
  
```
bool try_lock_read();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если была получена блокировка, значение `true`; в противном случае — значение `false`.  
  
##  <a name="unlock"></a> Снятие блокировки 

 Снимает блокировку чтения записи, в зависимости от того, кто именно заблокировал его, чтения или записи.  
  
```
void unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Если имеются ожидающие блокировку писатели, выпуск блокировки всегда перейдет в следующей записи в порядке FIFO. Эта блокировка склонна модулей записи и может привести к дефициту чтения при постоянной нагрузке модулей записи.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс critical_section](critical-section-class.md)
