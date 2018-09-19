---
title: Класс Event | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- event
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
dev_langs:
- C++
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f4156720d7d02b0c96ab36101d88c941dbfbfdd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071542"
---
# <a name="event-class"></a>Класс event
Сбрасываемое вручную событие, которое явно учитывает среду выполнения с параллелизмом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class event;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[~ событий деструктор](#dtor)|Уничтожает событие.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[reset](#reset)|Сбрасывает события в сигнальное состояние.|  
|[set](#set)|Сигнализирует о событии.|  
|[wait](#wait)|Ожидает события в сигнальное.|  
|[wait_for_multiple](#wait_for_multiple)|Ожидает в течение нескольких события в сигнальное.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание|  
|----------|-----------------|  
|[timeout_infinite](#timeout_infinite)|Значение, указывающее, что время ожидания никогда не должно истечь.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `event`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a> Событие 

 Создает новое событие.  
  
```
_CRTIMP event();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="dtor"></a> ~ событий 

 Уничтожает событие.  
  
```
~event();
```  
  
### <a name="remarks"></a>Примечания  
 Предполагается, что отсутствуют потоки ожидают события при выполнении деструктора. Разрешение уничтожения события при наличии ожидающих его результатов потоков приводит к неопределенному поведению.  
  
##  <a name="reset"></a> Сброс 

 Сбрасывает события в сигнальное состояние.  
  
```
void reset();
```  
  
##  <a name="set"></a> Набор 

 Сигнализирует о событии.  
  
```
void set();
```  
  
### <a name="remarks"></a>Примечания  
 Подача сигнала о событии может привести к тому, что произвольное число контекстов будет ожидать, когда событие станет готово к запуску.  
  
##  <a name="timeout_infinite"></a> timeout_infinite 

 Значение, указывающее, что время ожидания никогда не должно истечь.  
  
```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```  
  
##  <a name="wait"></a> Подождите 

 Ожидает события в сигнальное.  
  
```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
*_Время ожидания*<br/>
Указывает количество миллисекунд до истечения срока ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` означает, что время ожидания отсутствует.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если было выполнено ожидания, значение `0` возвращается; в противном случае — значение `COOPERATIVE_WAIT_TIMEOUT` для указания, что истекло время ожидания без получения событием сигнала.  
  
> [!IMPORTANT]
>  В приложении универсальной платформы Windows (UWP), не следует вызывать `wait` в потоке ASTA, так как этот вызов может заблокировать текущий поток и может вызвать зависание приложения.  
  
##  <a name="wait_for_multiple"></a> wait_for_multiple 

 Ожидает в течение нескольких события в сигнальное.  
  
```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
*_PPEvents*<br/>
Массив событий для ожидания. Число событий в пределах массива обозначается `count` параметра.  
  
*count*<br/>
Количество событий в массиве, указанном в `_PPEvents` параметра.  
  
*_FWaitAll*<br/>
Если присвоено значение `true`, параметр указывает, что все события в массиве, предоставленный в `_PPEvents` параметра должны принять сигнал, чтобы удовлетворить ожидания. Если присвоено значение `false`, он указывает, что любое событие в массиве, предоставленный в `_PPEvents` параметр сигнал будет удовлетворять ожидание.  
  
*_Время ожидания*<br/>
Указывает количество миллисекунд до истечения срока ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` означает, что время ожидания отсутствует.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если было выполнено ожидания, индекс в массиве, переданный в `_PPEvents` параметр, который удовлетворяет условию ожидания; в противном случае — значение `COOPERATIVE_WAIT_TIMEOUT` для указания, что истекло время ожидания без соблюдении условия.  
  
### <a name="remarks"></a>Примечания  
 Если параметр `_FWaitAll` присвоено значение `true` чтобы указать, что все события должны стать сигнал, чтобы удовлетворить ожидания, возвращаемый функцией индекс не переносит специального значения за исключением того, что оно не равно значению `COOPERATIVE_WAIT_TIMEOUT`.  
  
> [!IMPORTANT]
>  В приложении универсальной платформы Windows (UWP), не следует вызывать `wait_for_multiple` в потоке ASTA, так как этот вызов может заблокировать текущий поток и может вызвать зависание приложения.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
