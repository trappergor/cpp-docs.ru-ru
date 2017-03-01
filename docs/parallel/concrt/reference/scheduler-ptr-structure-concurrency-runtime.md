---
title: "Структура scheduler_ptr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pplinterface/concurrency::scheduler_ptr
dev_langs:
- C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 022b5fafc437a8103fe17967a9a5ea54d5b82a39
ms.lasthandoff: 02/24/2017

---
# <a name="schedulerptr-structure"></a>Структура scheduler_ptr
Представляет указатель на планировщик. Этот класс существует для того, чтобы обеспечить возможность использования спецификации общего времени жизни путем применения shared_ptr или простой ссылки с помощью необработанного указателя.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct scheduler_ptr;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор scheduler_ptr::scheduler_ptr](#ctor)|Перегружен. Создает указатель планировщика из shared_ptr планировщику|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод scheduler_ptr::Get](#get)|Возвращает необработанный указатель планировщику|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор scheduler_ptr::operator bool](#operator_bool)|Проверьте, является ли указатель планировщика отличным от null|  
|[scheduler_ptr::operator -&gt; оператор](#operator_ptr)|Поведение, как у указателя|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `scheduler_ptr`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** pplinterface.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namegeta--schedulerptrget-method"></a><a name="get"></a>Метод scheduler_ptr::Get  
 Возвращает необработанный указатель планировщику  
  
```
scheduler_interface* get() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameoperatorboola--schedulerptroperator-bool"></a><a name="operator_bool"></a>scheduler_ptr::operator bool   
 Проверьте, является ли указатель планировщика отличным от null  
  
''' bool() оператор const;
```  
  
##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;   
 Behave like a pointer  
  
```
operator->() scheduler_interface * const;
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
явные scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);</scheduler_interface>

явные scheduler_ptr (_In_opt_ pScheduler scheduler_interface *);
```  
  
### Parameters  
 `scheduler`  
 `pScheduler`  
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)

