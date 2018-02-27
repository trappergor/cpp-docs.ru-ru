---
title: "Класс single_link_registry | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 74167dcc03754c7f25d83058ec814798d40931a2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[single_link_registry](#ctor)|Создает объект `single_link_registry`.|  
|[~ single_link_registry деструктор](#dtor)|Уничтожает `single_link_registry` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[add](#add)|Добавляет ссылку на `single_link_registry` объекта. (Overrides [network_link_registry::add](network-link-registry-class.md#add).)|  
|[begin](#begin)|Возвращает итератор на первый элемент в `single_link_registry` объекта. (Overrides [network_link_registry::begin](network-link-registry-class.md#begin).)|  
|[содержит](#contains)|Поиск `single_link_registry` объекта для указанного блока. (Переопределяет [network_link_registry::contains](network-link-registry-class.md#contains).)|  
|[count](#count)|Подсчитывает количество элементов в `single_link_registry` объекта. (Overrides [network_link_registry::count](network-link-registry-class.md#count).)|  
|[remove](#remove)|Удаляет ссылку из `single_link_registry` объекта. (Переопределяет [network_link_registry::remove](network-link-registry-class.md#remove).)|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [network_link_registry](network-link-registry-class.md)  
  
 `single_link_registry`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="add"></a> Добавить 

 Добавляет ссылку на `single_link_registry` объекта.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок для добавления.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_link_target](invalid-link-target-class.md) исключение, если уже существует ссылка в данном реестре.  
  
##  <a name="begin"></a> начать 

 Возвращает итератор на первый элемент в `single_link_registry` объекта.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, обращающийся к первому элементу в `single_link_registry` объекта.  
  
### <a name="remarks"></a>Примечания  
 Конечное состояние обозначается `NULL` ссылку.  
  
##  <a name="contains"></a> содержит 

 Поиск `single_link_registry` объекта для указанного блока.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок, который необходимо найти в `single_link_registry` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если ссылка была найдена, `false` в противном случае.  
  
##  <a name="count"></a> Счетчик 

 Подсчитывает количество элементов в `single_link_registry` объекта.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в `single_link_registry` объекта.  
  
##  <a name="remove"></a> Удалить 

 Удаляет ссылку из `single_link_registry` объекта.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок удалены, если найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если ссылка была найдена и удалена, `false` в противном случае.  
  
##  <a name="ctor"></a> single_link_registry 

 Создает объект `single_link_registry`.  
  
```
single_link_registry();
```  
  
##  <a name="dtor"></a> ~single_link_registry 

 Уничтожает `single_link_registry` объекта.  
  
```
virtual ~single_link_registry();
```  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_operation](invalid-operation-class.md) исключение, если он вызывается до удаления ссылки.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс multi_link_registry](multi-link-registry-class.md)
