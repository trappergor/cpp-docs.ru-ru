---
title: "Класс single_link_registry | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
dev_langs:
- C++
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
caps.latest.revision: 19
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
ms.openlocfilehash: fc99e9af586520d60c20302e8b828a188df9efda
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="singlelinkregistry-class"></a>Класс single_link_registry
Объект `single_link_registry` представляет собой `network_link_registry`, управляющий только одним блоком источника или целевым блоком.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>Параметры  
 `_Block`  
 Тип блока данных, хранимых в `single_link_registry` объекта.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[single_link_registry](#ctor)|Создает объект `single_link_registry`.|  
|[~ single_link_registry деструктор](#dtor)|Уничтожает `single_link_registry` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[add](#add)|Добавляет ссылку на `single_link_registry` объект. (Переопределяет [network_link_registry::add](network-link-registry-class.md#add).)|  
|[begin](#begin)|Возвращает итератор на первый элемент в `single_link_registry` объекта. (Переопределяет [network_link_registry::begin](network-link-registry-class.md#begin).)|  
|[содержит](#contains)|Поиск `single_link_registry` объекта для указанного блока. (Переопределяет [network_link_registry::contains](network-link-registry-class.md#contains).)|  
|[count](#count)|Подсчитывает число элементов в `single_link_registry` объекта. (Переопределяет [network_link_registry::count](network-link-registry-class.md#count).)|  
|[remove](#remove)|Удаляет ссылку из `single_link_registry` объекта. (Переопределяет [network_link_registry::remove](network-link-registry-class.md#remove).)|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [network_link_registry](network-link-registry-class.md)  
  
 `single_link_registry`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="add"></a>добавить 

 Добавляет ссылку на `single_link_registry` объект.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок для добавления.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_link_target](invalid-link-target-class.md) исключение, если уже существует ссылка в реестр.  
  
##  <a name="begin"></a>начать 

 Возвращает итератор на первый элемент в `single_link_registry` объекта.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, обращающийся к первому элементу в `single_link_registry` объекта.  
  
### <a name="remarks"></a>Примечания  
 Конечное состояние обозначается `NULL` ссылку.  
  
##  <a name="contains"></a>содержит 

 Поиск `single_link_registry` объекта для указанного блока.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок, который необходимо найти в `single_link_registry` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если связь было обнаружено, `false` в противном случае.  
  
##  <a name="count"></a>число 

 Подсчитывает число элементов в `single_link_registry` объекта.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в `single_link_registry` объекта.  
  
##  <a name="remove"></a>удалить 

 Удаляет ссылку из `single_link_registry` объекта.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок удаляется, если найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ссылка была найдена и удалена, `false` в противном случае.  
  
##  <a name="ctor"></a>single_link_registry 

 Создает объект `single_link_registry`.  
  
```
single_link_registry();
```  
  
##  <a name="dtor"></a>~ single_link_registry 

 Уничтожает `single_link_registry` объекта.  
  
```
virtual ~single_link_registry();
```  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_operation](invalid-operation-class.md) исключение, если он вызывается до удаления ссылки.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс multi_link_registry](multi-link-registry-class.md)

