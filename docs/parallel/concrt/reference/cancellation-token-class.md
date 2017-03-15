---
title: "Класс cancellation_token | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pplcancellation_token/concurrency::cancellation_token
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token class
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
caps.latest.revision: 10
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
ms.openlocfilehash: 93d5abe132203a53f3ffac8490fe32604e7e896e
ms.lasthandoff: 02/24/2017

---
# <a name="cancellationtoken-class"></a>Класс cancellation_token
Класс `cancellation_token` представляет возможность определить, получала ли некоторая операция запрос на отмену. Заданный токен можно связать с `task_group`, `structured_task_group` или `task` для предоставления неявной отмены. Его также можно опрашивать на предмет отмены или зарегистрировать обратный вызов для той ситуации, когда отменяется связанный `cancellation_token_source`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class cancellation_token;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор cancellation_token](#ctor)||  
|[~ cancellation_token деструктор](#dtor)||  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[deregister_callback метод](#deregister_callback)|Удаляет обратный вызов, ранее зарегистрированный с помощью метода `register` на основании объекта `cancellation_token_registration`, возвращенного во время регистрации.|  
|[is_cancelable метод](#is_cancelable)|Возвращает значение, указывающее, может ли этот токен быть отменен или нет.|  
|[is_canceled метод](#is_canceled)|Возвращает `true`, если токен был отменен.|  
|[ни один метод](#none)|Возвращает токен отмены, который никогда не может подвергаться отмене.|  
|[register_callback метод](#register_callback)|Регистрирует функцию обратного вызова в токене. Если и когда токен отменяется, выполняется обратный вызов. Обратите внимание, что если токен уже отменен в той точке, где вызывается этот метод, обратный вызов будет выполнен немедленно и синхронно.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор! =-оператор](#operator_neq)||  
|[оператор =-оператор](#operator_eq)||  
|[оператор ==-оператор](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `cancellation_token`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** pplcancellation_token.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namedtora-cancellationtoken"></a><a name="dtor"></a>~ cancellation_token 

```
~cancellation_token();
```  
  
##  <a name="a-namectora-cancellationtoken"></a><a name="ctor"></a>cancellation_token 

```
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
##  <a name="a-namederegistercallbacka-deregistercallback"></a><a name="deregister_callback"></a>deregister_callback 

 Удаляет обратный вызов, ранее зарегистрированный с помощью метода `register` на основании объекта `cancellation_token_registration`, возвращенного во время регистрации.  
  
```
void deregister_callback(const cancellation_token_registration& _Registration) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Registration`  
 Объект `cancellation_token_registration`, соответствующий обратному вызову, регистрацию которого требуется отменить. Этот токен должен быть предварительно возвращен из вызова метода `register`.  
  
##  <a name="a-nameiscancelablea-iscancelable"></a><a name="is_cancelable"></a>is_cancelable 

 Возвращает значение, указывающее, может ли этот токен быть отменен или нет.  
  
```
bool is_cancelable() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индикация того, может ли этот токен быть отменен.  
  
##  <a name="a-nameiscanceleda-iscanceled"></a><a name="is_canceled"></a>is_canceled 

 Возвращает `true`, если токен был отменен.  
  
```
bool is_canceled() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если токен был отменен; в противном случае — значение `false`.  
  
##  <a name="a-namenonea-none"></a><a name="none"></a>Нет 

 Возвращает токен отмены, который никогда не может подвергаться отмене.  
  
```
static cancellation_token none();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Токен отмены, который невозможно отменить.  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>оператор! = 

```
bool operator!= (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

```
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>оператор == 

```
bool operator== (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameregistercallbacka-registercallback"></a><a name="register_callback"></a>register_callback 

 Регистрирует функцию обратного вызова в токене. Если и когда токен отменяется, выполняется обратный вызов. Обратите внимание, что если токен уже отменен в той точке, где вызывается этот метод, обратный вызов будет выполнен немедленно и синхронно.  
  
```
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Function`  
 Тип объекта функции, вызываемого при отмене этого `cancellation_token`.  
  
 `_Func`  
 Объект функции, вызываемый при отмене этого `cancellation_token`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `cancellation_token_registration`, который можно использовать в методе `deregister` для отмены регистрации ранее зарегистрированного обратного вызова и предотвращения его выполнения. Метод создает исключение [invalid_operation](invalid-operation-class.md) исключение, если он вызывается для `cancellation_token` объект, который был создан с помощью [cancellation_token::none](#none) метод.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

