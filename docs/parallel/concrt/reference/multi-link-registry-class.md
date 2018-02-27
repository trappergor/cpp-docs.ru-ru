---
title: "Класс multi_link_registry | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
dev_langs:
- C++
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f87da4852fff0256b5ca55cfd47d839531b8a03
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[multi_link_registry](#ctor)|Создает объект `multi_link_registry`.|  
|[~ multi_link_registry деструктор](#dtor)|Уничтожает `multi_link_registry` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[add](#add)|Добавляет ссылку на `multi_link_registry` объекта. (Overrides [network_link_registry::add](network-link-registry-class.md#add).)|  
|[begin](#begin)|Возвращает итератор на первый элемент в `multi_link_registry` объекта. (Overrides [network_link_registry::begin](network-link-registry-class.md#begin).)|  
|[содержит](#contains)|Поиск `multi_link_registry` объекта для указанного блока. (Переопределяет [network_link_registry::contains](network-link-registry-class.md#contains).)|  
|[count](#count)|Подсчитывает количество элементов в `multi_link_registry` объекта. (Overrides [network_link_registry::count](network-link-registry-class.md#count).)|  
|[remove](#remove)|Удаляет ссылку из `multi_link_registry` объекта. (Переопределяет [network_link_registry::remove](network-link-registry-class.md#remove).)|  
|[set_bound](#set_bound)|Устанавливает верхний предел на число ссылок `multi_link_registry` могут храниться в объекте.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [network_link_registry](network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="add"></a> Добавить 

 Добавляет ссылку на `multi_link_registry` объекта.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок для добавления.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_link_target](invalid-link-target-class.md) Если связь уже существует в реестре или если ограничение уже было установлено исключение с `set_bound` функции и ссылки был удален.  
  
##  <a name="begin"></a> начать 

 Возвращает итератор на первый элемент в `multi_link_registry` объекта.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, обращающийся к первому элементу в `multi_link_registry` объекта.  
  
### <a name="remarks"></a>Примечания  
 Конечное состояние обозначается `NULL` ссылку.  
  
##  <a name="contains"></a> содержит 

 Поиск `multi_link_registry` объекта для указанного блока.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок, который необходимо найти в `multi_link_registry` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если указанная блокировка найдена, `false` в противном случае.  
  
##  <a name="count"></a> Счетчик 

 Подсчитывает количество элементов в `multi_link_registry` объекта.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в `multi_link_registry` объекта.  
  
##  <a name="ctor"></a> multi_link_registry 

 Создает объект `multi_link_registry`.  
  
```
multi_link_registry();
```  
  
##  <a name="dtor"></a> ~multi_link_registry 

 Уничтожает `multi_link_registry` объекта.  
  
```
virtual ~multi_link_registry();
```  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_operation](invalid-operation-class.md) исключение, если вызывается до удаления всех связей.  
  
##  <a name="remove"></a> Удалить 

 Удаляет ссылку из `multi_link_registry` объекта.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок удалены, если найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если ссылка была найдена и удалена, `false` в противном случае.  
  
##  <a name="set_bound"></a> set_bound 

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
