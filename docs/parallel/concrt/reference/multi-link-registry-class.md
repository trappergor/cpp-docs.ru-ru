---
title: "Класс multi_link_registry | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::multi_link_registry
dev_langs:
- C++
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1548d2f920cf5566cced499e189cdcc19bf757ee
ms.lasthandoff: 02/24/2017

---
# <a name="multilinkregistry-class"></a>Класс multi_link_registry
Объект `multi_link_registry` представляет собой `network_link_registry`, управляющий несколькими блоками источников или целевыми блоками.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>Параметры  
 `_Block`  
 Тип блока данных, хранимых в `multi_link_registry` объекта.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор multi_link_registry](#ctor)|Создает объект `multi_link_registry`.|  
|[~ multi_link_registry деструктор](#dtor)|Уничтожает `multi_link_registry` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Добавьте метод](#add)|Добавляет ссылку на `multi_link_registry` объект. (Переопределяет [network_link_registry::add](network-link-registry-class.md#add).)|  
|[BEGIN-метод](#begin)|Возвращает итератор на первый элемент в `multi_link_registry` объекта. (Переопределяет [network_link_registry::begin](network-link-registry-class.md#begin).)|  
|[содержит метод](#contains)|Поиск `multi_link_registry` объекта для указанного блока. (Переопределяет [network_link_registry::contains](network-link-registry-class.md#contains).)|  
|[Count-метод](#count)|Подсчитывает число элементов в `multi_link_registry` объекта. (Переопределяет [network_link_registry::count](network-link-registry-class.md#count).)|  
|[Remove-метод](#remove)|Удаляет ссылку из `multi_link_registry` объекта. (Переопределяет [network_link_registry::remove](network-link-registry-class.md#remove).)|  
|[set_bound метод](#set_bound)|Устанавливает верхний предел на число ссылок `multi_link_registry` могут храниться в объекте.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [network_link_registry](network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>добавить 

 Добавляет ссылку на `multi_link_registry` объект.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок для добавления.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_link_target](invalid-link-target-class.md) Если ссылка уже присутствует в реестре, или если ограничение уже было установлено исключение с `set_bound` функции и ссылки был удален.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>начать 

 Возвращает итератор на первый элемент в `multi_link_registry` объекта.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, обращающийся к первому элементу в `multi_link_registry` объекта.  
  
### <a name="remarks"></a>Примечания  
 Конечное состояние обозначается `NULL` ссылку.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>содержит 

 Поиск `multi_link_registry` объекта для указанного блока.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок, который необходимо найти в `multi_link_registry` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если указанная блокировка найдена, `false` в противном случае.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>число 

 Подсчитывает число элементов в `multi_link_registry` объекта.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в `multi_link_registry` объекта.  
  
##  <a name="a-namectora-multilinkregistry"></a><a name="ctor"></a>multi_link_registry 

 Создает объект `multi_link_registry`.  
  
```
multi_link_registry();
```  
  
##  <a name="a-namedtora-multilinkregistry"></a><a name="dtor"></a>~ multi_link_registry 

 Уничтожает `multi_link_registry` объекта.  
  
```
virtual ~multi_link_registry();
```  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_operation](invalid-operation-class.md) исключение, если вызывается до удаления всех связей.  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>удалить 

 Удаляет ссылку из `multi_link_registry` объекта.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок удаляется, если найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ссылка была найдена и удалена, `false` в противном случае.  
  
##  <a name="a-namesetbounda-setbound"></a><a name="set_bound"></a>set_bound 

 Устанавливает верхний предел на число ссылок `multi_link_registry` могут храниться в объекте.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Параметры  
 `_MaxLinks`  
 Максимальное число ссылок, `multi_link_registry` могут храниться в объекте.  
  
### <a name="remarks"></a>Примечания  
 После установки границы отсоединение записи приведет к тому, что объект `multi_link_registry` войдет в неизменяемое состояние, где дальнейшие вызовы `add` создадут исключение `invalid_link_target`.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс single_link_registry](single-link-registry-class.md)

