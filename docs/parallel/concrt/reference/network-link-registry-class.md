---
title: "Класс network_link_registry | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
dev_langs:
- C++
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 28c13f1e2bf80624da3a7aba441944c051790d27
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="networklinkregistry-class"></a>Класс network_link_registry
Абстрактный базовый класс `network_link_registry` управляет связями между блоками источников и целевыми блоками.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class _Block>
class network_link_registry;
```  
  
#### <a name="parameters"></a>Параметры  
 `_Block`  
 Тип блока данных, хранимых в `network_link_registry`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`const_pointer`|Тип, который предоставляет указатель на `const` элемент в `network_link_registry` объекта.|  
|`const_reference`|Тип, предоставляющий ссылку на `const` элемент хранится в `network_link_registry` объект для чтения и выполнения операций const.|  
|`iterator`|Тип, который предоставляет итератор, который может читать или изменять любой элемент в `network_link_registry` объекта.|  
|`type`|Тип, представляющий тип блока, хранящиеся в `network_link_registry` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[add](#add)|При переопределении в производном классе, добавляет ссылку на `network_link_registry` объект.|  
|[begin](#begin)|При переопределении в производном классе возвращает итератор на первый элемент в `network_link_registry` объекта.|  
|[содержит](#contains)|При переопределении в производном классе выполняет `network_link_registry` объекта для указанного блока.|  
|[count](#count)|При переопределении в производном классе, возвращает количество элементов в `network_link_registry` объекта.|  
|[remove](#remove)|При переопределении в производном классе удаляет заданный блок из `network_link_registry` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `network link registry` Не является безопасным для параллельного доступа.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `network_link_registry`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="add"></a>добавить 

 При переопределении в производном классе, добавляет ссылку на `network_link_registry` объект.  
  
```
virtual void add(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок для добавления.  
  
##  <a name="begin"></a>начать 

 При переопределении в производном классе возвращает итератор на первый элемент в `network_link_registry` объекта.  
  
```
virtual iterator begin() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, обращающийся к первому элементу в `network_link_registry` объекта.  
  
### <a name="remarks"></a>Примечания  
 Конечное состояние итератора обозначается `NULL` ссылку.  
  
##  <a name="contains"></a>содержит 

 При переопределении в производном классе выполняет `network_link_registry` объекта для указанного блока.  
  
```
virtual bool contains(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок, которая ищется в `network_link_registry` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если блокировка была найдена, `false` в противном случае.  
  
##  <a name="count"></a>число 

 При переопределении в производном классе, возвращает количество элементов в `network_link_registry` объекта.  
  
```
virtual size_t count() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в `network_link_registry` объекта.  
  
##  <a name="remove"></a>удалить 

 При переопределении в производном классе удаляет заданный блок из `network_link_registry` объекта.  
  
```
virtual bool remove(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок удаляется, если найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ссылка была найдена и удалена, `false` в противном случае.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс single_link_registry](single-link-registry-class.md)   
 [Класс multi_link_registry](multi-link-registry-class.md)

