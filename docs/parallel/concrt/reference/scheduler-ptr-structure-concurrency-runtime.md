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
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 4bef1995724d078c9702669806ff61d5563ac465
ms.lasthandoff: 03/17/2017

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
|[scheduler_ptr::scheduler_ptr](#ctor)|Перегружен. Создает указатель планировщика из shared_ptr планировщику|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[scheduler_ptr::Get](#get)|Возвращает необработанный указатель планировщику|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[scheduler_ptr::operator bool](#operator_bool)|Проверьте, является ли указатель планировщика отличным от null|  
|[scheduler_ptr::operator-&gt;](#operator_ptr)|Поведение, как у указателя|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `scheduler_ptr`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** pplinterface.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="get"></a>Метод scheduler_ptr::Get  
 Возвращает необработанный указатель планировщику  
  
```
scheduler_interface* get() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="operator_bool"></a>scheduler_ptr::operator bool   
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

