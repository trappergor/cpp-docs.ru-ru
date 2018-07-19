---
title: Класс ITarget | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
dev_langs:
- C++
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9780e4b9ff8950511601b03e8423764c3def77a1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691505"
---
# <a name="itarget-class"></a>Класс ITarget
Класс `ITarget` является интерфейсом для всех целевых блоков. Целевые блоки потребляют сообщения, предлагаемые ими блоками `ISource`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class ITarget;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных полезных данных внутри сообщений, принятых в целевой блок.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`filter_method`|Подпись метода, используемая блоком, который возвращает `bool` значение, чтобы определить, следует ли принять предложенное сообщение.|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[~ Деструктор ITarget](#dtor)|Уничтожает `ITarget` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[распространение](#propagate)|При переопределении в производном классе асинхронно передает сообщение из исходного блока данному целевому блоку.|  
|[send](#send)|При переопределении в производном классе синхронно передает сообщение в целевой блок.|  
|[supports_anonymous_source](#supports_anonymous_source)|При переопределении в производном классе возвращает значение true или false в зависимости от того, принимает ли блок сообщений сообщения, предоставляемые не связанным с ним источником. Если переопределенный метод возвращает значение `true`, целевой объект не может отложить предоставленное сообщение, так как для использования отложенного сообщения позже требуется, чтобы источник был определен в реестре ссылок источников.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[link_source](#link_source)|При переопределении в производном классе связывает указанный исходный блок это `ITarget` блока.|  
|[unlink_source](#unlink_source)|При переопределении в производном классе удаляет связь указанного блока источника из этого `ITarget` блока.|  
|[unlink_sources](#unlink_sources)|При переопределении в производном классе удаляет связь всех исходных блоков из этого `ITarget` блока.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ITarget`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="dtor"></a> ~ ITarget 

 Уничтожает `ITarget` объекта.  
  
```
virtual ~ITarget();
```  
  
##  <a name="link_source"></a> link_source 

 При переопределении в производном классе связывает указанный исходный блок это `ITarget` блока.  
  
```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 `ISource` Блокировать, связанным с это `ITarget` блока.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не должен вызываться непосредственно на `ITarget` блока. Блоки должны быть соединены друг с другом с помощью `link_target` метод `ISource` блоков, который будет вызывать `link_source` метод в соответствующий целевой объект.  
  
##  <a name="propagate"></a> распространение 

 При переопределении в производном классе асинхронно передает сообщение из исходного блока данному целевому блоку.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на объект `message`.  
  
 `_PSource`  
 Указатель на исходный блок, предлагающий сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) , указывающее, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если параметр `_PMessage` или `_PSource` параметр `NULL`.  
  
##  <a name="send"></a> Отправить 

 При переопределении в производном классе синхронно передает сообщение в целевой блок.  
  
```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на объект `message`.  
  
 `_PSource`  
 Указатель на исходный блок, предлагающий сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) , указывающее, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если параметр `_PMessage` или `_PSource` параметр `NULL`.  
  
 С помощью `send` метод вне инициации сообщения и передавать сообщения в сети является опасной операцией и может привести к взаимоблокировке.  
  
 Если `send` возвращает сообщение либо уже было принято и передачи в блок целевой или было отклонено целевым объектом.  
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 При переопределении в производном классе возвращает значение true или false в зависимости от того, принимает ли блок сообщений сообщения, предоставляемые не связанным с ним источником. Если переопределенный метод возвращает значение `true`, целевой объект не может отложить предоставленное сообщение, так как для использования отложенного сообщения позже требуется, чтобы источник был определен в реестре ссылок источников.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если блок может принимать сообщения от не связанного с ним источника; в противном случае — значение `false`.  
  
##  <a name="unlink_source"></a> unlink_source 

 При переопределении в производном классе удаляет связь указанного блока источника из этого `ITarget` блока.  
  
```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 `ISource` Блок, связь которого с это `ITarget` блока.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не должен вызываться непосредственно на `ITarget` блока. Блоки должен быть отключен с помощью `unlink_target` или `unlink_targets` методы `ISource` блоков, который будет вызывать `unlink_source` метод в соответствующий целевой объект.  
  
##  <a name="unlink_sources"></a> unlink_sources 

 При переопределении в производном классе удаляет связь всех исходных блоков из этого `ITarget` блока.  
  
```
virtual void unlink_sources() = 0;
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ISource](isource-class.md)
