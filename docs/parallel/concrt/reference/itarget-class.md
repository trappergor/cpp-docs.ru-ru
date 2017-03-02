---
title: "Класс ITarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ITarget
dev_langs:
- C++
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
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
ms.openlocfilehash: aa9001de9ec35f20cd76f701d6b8acc5de7ffde0
ms.lasthandoff: 02/24/2017

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
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`filter_method`|Сигнатура любого метода, используемого блоком, который возвращает `bool` значение, чтобы определить, следует ли принять предложенное сообщение.|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[~ Деструктор ITarget](#dtor)|Уничтожает `ITarget` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Propagate-метод](#propagate)|При переопределении в производном классе асинхронно передает сообщение из исходного блока данному целевому блоку.|  
|[Send-метод](#send)|При переопределении в производном классе синхронно передает сообщение целевому блоку.|  
|[supports_anonymous_source метод](#supports_anonymous_source)|При переопределении в производном классе возвращает значение true или false в зависимости от того, принимает ли блок сообщений сообщения, предоставляемые не связанным с ним источником. Если переопределенный метод возвращает значение `true`, целевой объект не может отложить предоставленное сообщение, так как для использования отложенного сообщения позже требуется, чтобы источник был определен в реестре ссылок источников.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[link_source метод](#link_source)|При переопределении в производном классе связывает указанный исходный блок это `ITarget` блок.|  
|[unlink_source метод](#unlink_source)|При переопределении в производном классе удаляет связь указанного блока источника из этого `ITarget` блок.|  
|[unlink_sources метод](#unlink_sources)|При переопределении в производном классе удаляет связь всех исходных блоков от этого `ITarget` блок.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ITarget`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namedtora-itarget"></a><a name="dtor"></a>~ ITarget 

 Уничтожает `ITarget` объекта.  
  
```
virtual ~ITarget();
```  
  
##  <a name="a-namelinksourcea-linksource"></a><a name="link_source"></a>link_source 

 При переопределении в производном классе связывает указанный исходный блок это `ITarget` блок.  
  
```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 `ISource` Блока, связанным с это `ITarget` блок.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не должен вызываться непосредственно на `ITarget` блок. Блоки должны быть соединены друг с другом с помощью `link_target` метод `ISource` блоков, который будет вызывать `link_source` метод на соответствующий целевой объект.  
  
##  <a name="a-namepropagatea-propagate"></a><a name="propagate"></a>распространение 

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
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если любой `_PMessage` или `_PSource` параметр `NULL`.  
  
##  <a name="a-namesenda-send"></a><a name="send"></a>Отправить 

 При переопределении в производном классе синхронно передает сообщение целевому блоку.  
  
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
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если любой `_PMessage` или `_PSource` параметр `NULL`.  
  
 С помощью `send` метод вне инициации сообщения и для распространения сообщений внутри сети небезопасно и может привести к взаимоблокировке.  
  
 Если `send` возвращает сообщение либо уже было принято и передано в блок целевой или было отклонено целевым объектом.  
  
##  <a name="a-namesupportsanonymoussourcea-supportsanonymoussource"></a><a name="supports_anonymous_source"></a>supports_anonymous_source 

 При переопределении в производном классе возвращает значение true или false в зависимости от того, принимает ли блок сообщений сообщения, предоставляемые не связанным с ним источником. Если переопределенный метод возвращает значение `true`, целевой объект не может отложить предоставленное сообщение, так как для использования отложенного сообщения позже требуется, чтобы источник был определен в реестре ссылок источников.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если блок может принимать сообщения от не связанного с ним источника; в противном случае — значение `false`.  
  
##  <a name="a-nameunlinksourcea-unlinksource"></a><a name="unlink_source"></a>unlink_source 

 При переопределении в производном классе удаляет связь указанного блока источника из этого `ITarget` блок.  
  
```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 `ISource` Блока отсоединяется от этого `ITarget` блок.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не должен вызываться непосредственно на `ITarget` блок. Блоки должен быть отключен с помощью `unlink_target` или `unlink_targets` методы `ISource` блоков, который будет вызывать `unlink_source` метод на соответствующий целевой объект.  
  
##  <a name="a-nameunlinksourcesa-unlinksources"></a><a name="unlink_sources"></a>unlink_sources 

 При переопределении в производном классе удаляет связь всех исходных блоков от этого `ITarget` блок.  
  
```
virtual void unlink_sources() = 0;
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ISource](isource-class.md)

