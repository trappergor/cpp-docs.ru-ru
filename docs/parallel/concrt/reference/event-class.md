---
title: "Класс Event | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::event
dev_langs:
- C++
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: abda6512f391b59cb48c8e96a489714ee117ae68
ms.lasthandoff: 02/24/2017

---
# <a name="event-class"></a>Класс event
Сбрасываемое вручную событие, которое явно учитывает среду выполнения с параллелизмом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class event;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[~ событий деструктор](#dtor)|Уничтожает событие.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Reset](#reset)|Сбрасывает событие в несигнальное состояние.|  
|[Метод Set](#set)|Указывает события.|  
|[wait-метод](#wait)|Ожидает перехода события в сигнальное.|  
|[wait_for_multiple метод](#wait_for_multiple)|Ожидает в течение нескольких события в сигнальное.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Константа timeout_infinite](#timeout_infinite)|Значение, указывающее, что время ожидания никогда не должно истечь.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `event`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namectora-event"></a><a name="ctor"></a>событие 

 Создает новое событие.  
  
```
_CRTIMP event();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedtora-event"></a><a name="dtor"></a>~ событий 

 Уничтожает событие.  
  
```
~event();
```  
  
### <a name="remarks"></a>Примечания  
 Предполагается, что существуют потоки, ожидающие события при выполнении деструктор. Разрешение уничтожения события при наличии ожидающих его результатов потоков приводит к неопределенному поведению.  
  
##  <a name="a-namereseta-reset"></a><a name="reset"></a>Сброс 

 Сбрасывает событие в несигнальное состояние.  
  
```
void reset();
```  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>набор 

 Указывает события.  
  
```
void set();
```  
  
### <a name="remarks"></a>Примечания  
 Подача сигнала о событии может привести к тому, что произвольное число контекстов будет ожидать, когда событие станет готово к запуску.  
  
##  <a name="a-nametimeoutinfinitea-timeoutinfinite"></a><a name="timeout_infinite"></a>timeout_infinite 

 Значение, указывающее, что время ожидания никогда не должно истечь.  
  
```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>Ожидание 

 Ожидает перехода события в сигнальное.  
  
```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 `_Timeout`  
 Указывает количество миллисекунд до истечения срока ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` означает отсутствие времени ожидания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если было выполнено ожидания, значение `0` возвращается; в противном случае — значение `COOPERATIVE_WAIT_TIMEOUT` для указания, что истекло время ожидания без получения событием сигнала.  
  
> [!IMPORTANT]
>  В приложении [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] не следует вызывать `wait` в потоке ASTA, потому что такой вызов может заблокировать текущий поток и приложение перестанет отвечать.  
  
##  <a name="a-namewaitformultiplea-waitformultiple"></a><a name="wait_for_multiple"></a>wait_for_multiple 

 Ожидает в течение нескольких события в сигнальное.  
  
```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 `_PPEvents`  
 Массив событий для ожидания. Указывает количество событий в массиве `count` параметр.  
  
 `count`  
 Количество событий в массиве, указанном в `_PPEvents` параметр.  
  
 `_FWaitAll`  
 Если задано значение `true`, параметр указывает, что все события в массиве, указанное в `_PPEvents` параметр должен принимать сигнал, чтобы удовлетворить ожидания. Если задано значение `false`, указывает, что любое событие в массиве, указанное в `_PPEvents` параметр сигнал, будет удовлетворять ожидание.  
  
 `_Timeout`  
 Указывает количество миллисекунд до истечения срока ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` означает отсутствие времени ожидания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если было выполнено ожидания, индекс в массиве, переданный в `_PPEvents` параметр, который удовлетворяет условию ожидания; в противном случае — значение `COOPERATIVE_WAIT_TIMEOUT` для указания, что истекло время ожидания без условия.  
  
### <a name="remarks"></a>Примечания  
 Если параметр `_FWaitAll` присвоено значение `true` для указания, что все события должны принять сигнал, чтобы удовлетворить ожидания, возвращаемый функцией индекс не переносит специального значения за исключением того, что оно не равно значению `COOPERATIVE_WAIT_TIMEOUT`.  
  
> [!IMPORTANT]
>  В приложении [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] не следует вызывать `wait_for_multiple` в потоке ASTA, потому что такой вызов может заблокировать текущий поток и приложение перестанет отвечать.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

