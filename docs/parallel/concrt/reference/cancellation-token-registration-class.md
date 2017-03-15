---
title: "Класс cancellation_token_registration | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pplcancellation_token/concurrency::cancellation_token_registration
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
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
ms.openlocfilehash: 72c317bb95b646a3a97b361ac3248f015cd0f29a
ms.lasthandoff: 02/24/2017

---
# <a name="cancellationtokenregistration-class"></a>Класс cancellation_token_registration
Класс `cancellation_token_registration` представляет уведомление обратного вызова из `cancellation_token`. При использовании метода `register` на `cancellation_token` для получения уведомления о времени выполнения отмены объект `cancellation_token_registration` возвращается как дескриптор для обратного вызова, чтобы вызывающий код мог запросить, чтобы определенный обратный вызов больше не выполнялся с помощью метода `deregister`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class cancellation_token_registration;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор cancellation_token_registration](#ctor)||  
|[~ cancellation_token_registration деструктор](#dtor)||  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор! =-оператор](#operator_neq)||  
|[оператор =-оператор](#operator_eq)||  
|[оператор ==-оператор](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `cancellation_token_registration`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** pplcancellation_token.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namedtora-cancellationtokenregistration"></a><a name="dtor"></a>~ cancellation_token_registration 

```
~cancellation_token_registration();
```  
  
##  <a name="a-namectora-cancellationtokenregistration"></a><a name="ctor"></a>cancellation_token_registration 

```
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>оператор! = 

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>оператор == 

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

