---
title: "Класс Event | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2301e06554d99529c7d4e4e5215208dc4265970
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="event-class"></a>Класс event
Сбрасываемое вручную событие, которое явно учитывает среду выполнения с параллелизмом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class event;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[~ событий деструктор](#dtor)|Уничтожает событие.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[reset](#reset)|Сбрасывает несигнальное состояние события.|  
|[set](#set)|Указывает события.|  
|[Ожидание](#wait)|Ожидание события в сигнальное.|  
|[wait_for_multiple](#wait_for_multiple)|Ожидает несколько событий в сигнальное.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
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
 Ожидается, что нет потоков ожидают события при выполнении деструктора. Разрешение уничтожения события при наличии ожидающих его результатов потоков приводит к неопределенному поведению.  
  
##  <a name="reset"></a> Сброс 

 Сбрасывает несигнальное состояние события.  
  
```
void reset();
```  
  
##  <a name="set"></a> Набор 

 Указывает события.  
  
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
  
##  <a name="wait">Ожидание</a> 

 Ожидание события в сигнальное.  
  
```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 `_Timeout`  
 Указывает количество миллисекунд до истечения срока ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` означает отсутствие времени ожидания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если было выполнено ожидания, значение `0` возвращается; в противном случае — значение `COOPERATIVE_WAIT_TIMEOUT` для указания, что истекло время ожидания без получения событием сигнала.  
  
> [!IMPORTANT]
>  В приложении универсальной платформы Windows (UWP), не следует вызывать `wait` в потоке ASTA, потому что этот вызов может заблокировать текущий поток и может вызвать зависание приложения.  
  
##  <a name="wait_for_multiple"></a> wait_for_multiple 

 Ожидает несколько событий в сигнальное.  
  
```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 `_PPEvents`  
 Массив событий для ожидания. Количество событий в массиве указывается параметром `count` параметр.  
  
 `count`  
 Количество событий в массиве, указанном в `_PPEvents` параметра.  
  
 `_FWaitAll`  
 Если задано значение `true`, параметр указывает, что все события в массиве, представлены в `_PPEvents` параметра должны принять сигнал, чтобы удовлетворить ожидание. Если задано значение `false`, указывает, что любое событие в массиве, представлены в `_PPEvents` параметр сигнал будет удовлетворять ожидание.  
  
 `_Timeout`  
 Указывает количество миллисекунд до истечения срока ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` означает отсутствие времени ожидания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если было выполнено ожидания, индекс в массиве, переданный в `_PPEvents` параметр, который удовлетворяет условию ожидания; в противном случае — значение `COOPERATIVE_WAIT_TIMEOUT` для указания, что истекло время ожидания не будет выполнено условие.  
  
### <a name="remarks"></a>Примечания  
 Если параметр `_FWaitAll` присвоено значение `true` для указания, что все события должны принять сигнал для удовлетворения ожидания, возвращаемый функцией индекс не переносит специального значения за исключением того, что он не является значением `COOPERATIVE_WAIT_TIMEOUT`.  
  
> [!IMPORTANT]
>  В приложении универсальной платформы Windows (UWP), не следует вызывать `wait_for_multiple` в потоке ASTA, потому что этот вызов может заблокировать текущий поток и может вызвать зависание приложения.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
