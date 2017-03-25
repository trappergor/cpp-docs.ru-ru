---
title: "Класс cancellation_token_source | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancel
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::create_linked_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::get_token
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_source class
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: f41a4a21af5bc37ab612221152b8311a5a91d914
ms.lasthandoff: 03/17/2017

---
# <a name="cancellationtokensource-class"></a>Класс cancellation_token_source
Класс `cancellation_token_source` представляет возможность отмены некоторой отменяемой операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class cancellation_token_source;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[cancellation_token_source](#ctor)|Перегружен. Создает новый `cancellation_token_source`. Источник можно использовать, чтобы сигнализировать об отмене некоторой отменяемой операции.|  
|[~ cancellation_token_source деструктор](#dtor)||  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Отмена](#cancel)|Отменяет токен. Любой элемент `task_group`, `structured_task_group` или `task`, который использует этот токен, будет отменен при этом вызове и создаст исключение в следующей точке прерывания.|  
|[create_linked_source](#create_linked_source)|Перегружен. Создает `cancellation_token_source`, который отменяется при отмене предоставленного токена.|  
|[get_token](#get_token)|Возвращает токен отмены, связанный с данным источником. Возвращенный токен можно опрашивать на предмет отмены или предоставить обратный вызов, если и когда произойдет отмена.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `cancellation_token_source`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** pplcancellation_token.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="dtor"></a>~ cancellation_token_source 

```
~cancellation_token_source();
```  
  
##  <a name="cancel"></a>Отмена 

 Отменяет токен. Любой элемент `task_group`, `structured_task_group` или `task`, который использует этот токен, будет отменен при этом вызове и создаст исключение в следующей точке прерывания.  
  
```
void cancel() const;
```  
  
##  <a name="ctor"></a>cancellation_token_source 

 Создает новый `cancellation_token_source`. Источник можно использовать, чтобы сигнализировать об отмене некоторой отменяемой операции.  
  
```
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
##  <a name="create_linked_source"></a>create_linked_source 

 Создает `cancellation_token_source`, который отменяется при отмене предоставленного токена.  
  
```
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```  
  
### <a name="parameters"></a>Параметры  
 `_Iter`  
 `_Src`  
 Токен, отмена которого приведет к отмене возвращаемого источника токена. Обратите внимание, что возвращаемый источник токена также можно отменить независимо от источника, содержащегося в этом параметре.  
  
 `_Begin`  
 Итератор стандартной библиотеки C++, соответствующий началу диапазона токенов, которые требуется прослушивать отмены.  
  
 `_End`  
 Итератор стандартной библиотеки C++, соответствующий концу диапазона токенов требуется прослушивать на предмет отмены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `cancellation_token_source`, который отменяется при отмене токена, предоставляемого параметром `_Src`.  
  
##  <a name="get_token"></a>get_token 

 Возвращает токен отмены, связанный с данным источником. Возвращенный токен можно опрашивать на предмет отмены или предоставить обратный вызов, если и когда произойдет отмена.  
  
```
cancellation_token get_token() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Токен отмены, связанный с этим источником.  
  
##  <a name="operator_neq"></a>оператор! = 

```
bool operator!= (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="operator_eq"></a>оператор = 

```
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="operator_eq_eq"></a>оператор == 

```
bool operator== (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)

