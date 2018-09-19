---
title: Класс reader_writer_lock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81acced9d3df85cd12c8306aed530728edf17e15
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106226"
---
# <a name="readerwriterlock-class"></a>Класс reader_writer_lock
Блокировка чтения или записи на основе очередей с предпочтением записи только с локальным вращением. Блокировка предоставляет модулям записи доступ в порядке поступления и блокирует доступ модулей чтения при постоянной нагрузке модулей записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class reader_writer_lock;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс reader_writer_lock::scoped_lock](#scoped_lock_class)|Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокировка объектов разработчиком.|  
|[Класс reader_writer_lock::scoped_lock_read](#scoped_lock_read_class)|Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокировка объектов в качестве средства чтения.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[reader_writer_lock](#ctor)|Создает новый `reader_writer_lock` объекта.|  
|[~ reader_writer_lock деструктор](#dtor)|Уничтожает `reader_writer_lock` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[lock](#lock)|Получает блокировку чтения записи писателя.|  
|[lock_read](#lock_read)|Получает блокировку чтения записи, как средство чтения. Если есть записи, активные модули нужно подождать, пока они выполняются. Средство чтения просто регистрирует интерес к блокировке и ожидает записи для его освобождения.|  
|[try_lock](#try_lock)|Пытается получить блокировку чтения записи писателя без блокировки.|  
|[try_lock_read](#try_lock_read)|Пытается получить блокировку чтения записи в качестве модуля чтения без блокировки.|  
|[unlock](#unlock)|Снимает блокировку чтения записи, в зависимости от того, кто заблокирована, он, чтения или записи.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `reader_writer_lock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="lock"></a> Блокировки 

 Получает блокировку чтения записи писателя.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Примечания  
 Часто лучше использовать [scoped_lock](#scoped_lock_class) конструкции для получения и освобождения `reader_writer_lock` объект как модуль записи к исключению безопасным способом.  
  
 После того как средство записи пытается получить блокировку, все будущие читатели будут блокироваться до тех пор, пока средства записи не получат и не снимут блокировку. Эта блокировка тяготеет к записи и может привести к дефициту модулей чтения при постоянной нагрузке модулей записи.  
  
 Модули записи объединяются в цепочки, чтобы модуль записи, выход из блокировки освобождает Далее модуль записи в строке.  
  
 Если вызывающий контекст уже удерживается блокировка [improper_lock](improper-lock-class.md) будет создано исключение.  
  
##  <a name="lock_read"></a> lock_read 

 Получает блокировку чтения записи, как средство чтения. Если есть записи, активные модули нужно подождать, пока они выполняются. Средство чтения просто регистрирует интерес к блокировке и ожидает записи для его освобождения.  
  
```
void lock_read();
```  
  
### <a name="remarks"></a>Примечания  
 Часто лучше использовать [scoped_lock_read](#scoped_lock_read_class) конструкции для получения и освобождения `reader_writer_lock` объект как модуль чтения к исключению безопасным способом.  
  
 Если имеются ожидающие блокировку записи, средство чтения будет ожидать, пока все записи в строке получена и не снимет блокировку. Эта блокировка тяготеет к записи и может привести к дефициту модулей чтения при постоянной нагрузке модулей записи.  
  
##  <a name="ctor"></a> reader_writer_lock 

 Создает новый `reader_writer_lock` объекта.  
  
```
reader_writer_lock();
```  
  
##  <a name="dtor"></a> ~ reader_writer_lock 

 Уничтожает `reader_writer_lock` объекта.  
  
```
~reader_writer_lock();
```  
  
### <a name="remarks"></a>Примечания  
 Предполагается, что больше не блокировку при выполнении деструктора. По-прежнему позволяя блокировкой записи средства чтения для уничтожения с блокировкой содержатся результаты в приведет к неопределенному поведению.  
  
##  <a name="scoped_lock_class"></a>  Класс reader_writer_lock::scoped_lock  
 Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокировка объектов разработчиком.  
  
```
class scoped_lock;
``` 
## <a name="scoped_lock_ctor"></a> scoped_lock::scoped_lock 

Создает `scoped_lock` объекта и получает `reader_writer_lock` переданный объект `_Reader_writer_lock` параметр как средство записи. Если блокировка удерживается другим потоком, этот вызов блокируется.  
  
  
```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Параметры  
*_Reader_writer_lock*<br/>
`reader_writer_lock` Объект для получения как модуль записи.  
  
## <a name="scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock 

Уничтожает `reader_writer_lock` объекта и снимает блокировку, переданную в конструкторе.   

```
~scoped_lock();
```  
  
##  <a name="scoped_lock_read_class"></a>  Класс reader_writer_lock::scoped_lock_read  
 Исключение безопасная оболочка RAII, можно использовать для получения `reader_writer_lock` блокировка объектов в качестве средства чтения.  
  
```
class scoped_lock_read;
```  
  
##  <a name="try_lock"></a> try_lock 

 Пытается получить блокировку чтения записи писателя без блокировки.  

## <a name="scoped_lock_read_ctor"></a> scoped_lock_read::scoped_lock_read 

Создает `scoped_lock_read` объекта и получает `reader_writer_lock` переданный объект `_Reader_writer_lock` параметр как средство чтения. Если блокировка удерживается другим потоком, разработчиком или существуют ожидающие записи, этот вызов блокируется.  
  
```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Параметры  
*_Reader_writer_lock*<br/>
`reader_writer_lock` Объект для получения как средство чтения.  
  
## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">  деструктор reader_writer_lock::scoped_lock_read:: ~ scoped_lock_read деструктор
Уничтожает `scoped_lock_read` объекта и снимает блокировку, переданную в конструкторе.  

```
~scoped_lock_read();
```  
  
## <a name="try_lock"></a> try_lock 

```
bool try_lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если блокировка была получена, значение `true`; в противном случае значение `false`.  
  
##  <a name="try_lock_read"></a> try_lock_read 

 Пытается получить блокировку чтения записи в качестве модуля чтения без блокировки.  
  
```
bool try_lock_read();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если блокировка была получена, значение `true`; в противном случае значение `false`.  
  
##  <a name="unlock"></a> разблокировать 

 Снимает блокировку чтения записи, в зависимости от того, кто заблокирована, он, чтения или записи.  
  
```
void unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Если имеются ожидающие блокировку записи, выпуск блокировки всегда переходит в следующий модуль записи в порядке FIFO. Эта блокировка тяготеет к записи и может привести к дефициту модулей чтения при постоянной нагрузке модулей записи.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс critical_section](critical-section-class.md)
