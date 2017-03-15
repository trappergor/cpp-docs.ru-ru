---
title: "Класс network_link_registry | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::network_link_registry
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 8b39ab676db0072d279ee4058693769ef6f7eb3f
ms.lasthandoff: 02/24/2017

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
|[Добавьте метод](#add)|При переопределении в производном классе, добавляет ссылку на `network_link_registry` объект.|  
|[BEGIN-метод](#begin)|При переопределении в производном классе возвращает итератор на первый элемент в `network_link_registry` объекта.|  
|[содержит метод](#contains)|При переопределении в производном классе выполняет `network_link_registry` объекта для указанного блока.|  
|[Count-метод](#count)|При переопределении в производном классе, возвращает количество элементов в `network_link_registry` объекта.|  
|[Remove-метод](#remove)|При переопределении в производном классе удаляет заданный блок из `network_link_registry` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `network link registry` Не является безопасным для параллельного доступа.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `network_link_registry`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>добавить 

 При переопределении в производном классе, добавляет ссылку на `network_link_registry` объект.  
  
```
virtual void add(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок для добавления.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>начать 

 При переопределении в производном классе возвращает итератор на первый элемент в `network_link_registry` объекта.  
  
```
virtual iterator begin() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, обращающийся к первому элементу в `network_link_registry` объекта.  
  
### <a name="remarks"></a>Примечания  
 Конечное состояние итератора обозначается `NULL` ссылку.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>содержит 

 При переопределении в производном классе выполняет `network_link_registry` объекта для указанного блока.  
  
```
virtual bool contains(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок, которая ищется в `network_link_registry` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если блокировка была найдена, `false` в противном случае.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>число 

 При переопределении в производном классе, возвращает количество элементов в `network_link_registry` объекта.  
  
```
virtual size_t count() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в `network_link_registry` объекта.  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>удалить 

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

