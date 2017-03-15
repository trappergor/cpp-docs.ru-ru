---
title: "Класс Message | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::message
dev_langs:
- C++
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 08d67f2899f27a92250d6fedbf755a5413e01ebd
ms.lasthandoff: 02/24/2017

---
# <a name="message-class"></a>Класс message
Основной конверт сообщения, содержащий полезные данные, передаваемые между блоками обмена сообщениями.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных полезных данных в сообщении.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор сообщения](#ctor)|Перегружен. Создает объект `message`.|  
|[~ сообщений деструктор](#dtor)|Уничтожает `message` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[add_ref метод](#add_ref)|Добавляет счетчик ссылок для `message` объекта. Используется для блоков сообщений, которым требуется подсчет ссылок, чтобы определить время жизни сообщения.|  
|[msg_id метод](#msg_id)|Возвращает идентификатор `message` объекта.|  
|[remove_ref метод](#remove_ref)|Вычитает из числа ссылок для `message` объекта. Используется для блоков сообщений, которым требуется подсчет ссылок, чтобы определить время жизни сообщения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных полезных данных](#payload)|Полезные данные `message` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `message`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameaddrefa-addref"></a><a name="add_ref"></a>add_ref 

 Добавляет счетчик ссылок для `message` объекта. Используется для блоков сообщений, которым требуется подсчет ссылок, чтобы определить время жизни сообщения.  
  
```
long add_ref();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новое значение счетчика ссылок.  
  
##  <a name="a-namectora-message"></a><a name="ctor"></a>Сообщение 

 Создает объект `message`.  
  
```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```  
  
### <a name="parameters"></a>Параметры  
 `_P`  
 Полезные данные сообщения.  
  
 `_Id`  
 Уникальный идентификатор этого сообщения.  
  
 `_Msg`  
 Ссылка или указатель на `message` объект.  
  
### <a name="remarks"></a>Примечания  
 Конструктор, который принимает указатель на `message` объектов как аргумент, создает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение при параметре `_Msg` — `NULL`.  
  
##  <a name="a-namedtora-message"></a><a name="dtor"></a>~ сообщения 

 Уничтожает `message` объекта.  
  
```
virtual ~message();
```  
  
##  <a name="a-namemsgida-msgid"></a><a name="msg_id"></a>msg_id 

 Возвращает идентификатор `message` объекта.  
  
```
runtime_object_identity msg_id() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `runtime_object_identity` Из `message` объекта.  
  
##  <a name="a-namepayloada-payload"></a><a name="payload"></a>полезные данные 

 Полезные данные `message` объекта.  
  
```
T const payload;
```  
  
##  <a name="a-nameremoverefa-removeref"></a><a name="remove_ref"></a>remove_ref 

 Вычитает из числа ссылок для `message` объекта. Используется для блоков сообщений, которым требуется подсчет ссылок, чтобы определить время жизни сообщения.  
  
```
long remove_ref();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новое значение счетчика ссылок.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

