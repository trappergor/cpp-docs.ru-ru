---
title: "Класс source_link_manager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::source_link_manager
dev_langs:
- C++
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: 17
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
ms.openlocfilehash: b9323da4d2ccefe09ba38df088e546828d41f2ee
ms.lasthandoff: 02/24/2017

---
# <a name="sourcelinkmanager-class"></a>Класс source_link_manager
Объект `source_link_manager` управляет сетевыми соединениями блоков обмена сообщениями с блоками `ISource`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class _LinkRegistry>
class source_link_manager;
```  
  
#### <a name="parameters"></a>Параметры  
 `_LinkRegistry`  
 Реестр сетевых ссылок.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`const_pointer`|Тип, который предоставляет указатель на `const` элемент в `source_link_manager` объекта.|  
|`const_reference`|Тип, предоставляющий ссылку на `const` элемент хранится в `source_link_manager` объект для чтения и выполнения операций const.|  
|`iterator`|Тип, который предоставляет итератор, который может читать или изменять любой элемент в `source_link_manager` объекта.|  
|`type`|Тип реестр ссылок, который управляется `source_link_manager` объекта.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор source_link_manager](#ctor)|Создает объект `source_link_manager`.|  
|[~ source_link_manager деструктор](#dtor)|Уничтожает `source_link_manager` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Добавьте метод](#add)|Добавляет ссылку на источник `source_link_manager` объекта.|  
|[BEGIN-метод](#begin)|Возвращает итератор на первый элемент в `source_link_manager` объекта.|  
|[содержит метод](#contains)|Поиск `network_link_registry` в рамках этого `source_link_manager` объекта для указанного блока.|  
|[Count-метод](#count)|Подсчитывает количество связанных блоков в `source_link_manager` объекта.|  
|[ссылаться на метод](#reference)|Получает ссылку на `source_link_manager` объект.|  
|[register_target_block метод](#register_target_block)|Регистрирует целевой блок, который содержит это `source_link_manager` объекта.|  
|[Release-метод](#release)|Освобождает ссылку на `source_link_manager` объект.|  
|[Remove-метод](#remove)|Удаляет ссылку из `source_link_manager` объекта.|  
|[set_bound метод](#set_bound)|Задает максимальное число ссылок источника, который может быть добавлен к этому `source_link_manager` объекта.|  
  
## <a name="remarks"></a>Примечания  
 В настоящее время блоки источника подлежат подсчету. Это оболочка на `network_link_registry` объект, который допускает параллельный доступ к ссылкам и предоставляет возможность ссылаться на связи через обратные вызовы. Блоки сообщений ( `target_block`s или `propagator_block`s) следует использовать этот класс для связи их источника.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `source_link_manager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>добавить 

 Добавляет ссылку на источник `source_link_manager` объекта.  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок для добавления.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>начать 

 Возвращает итератор на первый элемент в `source_link_manager` объекта.  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, обращающийся к первому элементу в `source_link_manager` объекта.  
  
### <a name="remarks"></a>Примечания  
 Конечное состояние итератора обозначается `NULL` ссылку.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>содержит 

 Поиск `network_link_registry` в рамках этого `source_link_manager` объекта для указанного блока.  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок, который необходимо найти в `source_link_manager` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если указанная блокировка найдена, `false` в противном случае.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>число 

 Подсчитывает количество связанных блоков в `source_link_manager` объекта.  
  
```
size_t count();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число связанных блоков в `source_link_manager` объекта.  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>ссылка 

 Получает ссылку на `source_link_manager` объект.  
  
```
void reference();
```  
  
##  <a name="a-nameregistertargetblocka-registertargetblock"></a><a name="register_target_block"></a>register_target_block 

 Регистрирует целевой блок, который содержит это `source_link_manager` объекта.  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Целевой блок, содержащий это `source_link_manager` объекта.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>выпуск 

 Освобождает ссылку на `source_link_manager` объект.  
  
```
void release();
```  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>удалить 

 Удаляет ссылку из `source_link_manager` объекта.  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок удаляется, если найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ссылка была найдена и удалена, `false` в противном случае.  
  
##  <a name="a-namesetbounda-setbound"></a><a name="set_bound"></a>set_bound 

 Задает максимальное число ссылок источника, который может быть добавлен к этому `source_link_manager` объекта.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Параметры  
 `_MaxLinks`  
 Максимальное число ссылок.  
  
##  <a name="a-namectora-sourcelinkmanager"></a><a name="ctor"></a>source_link_manager 

 Создает объект `source_link_manager`.  
  
```
source_link_manager();
```  
  
##  <a name="a-namedtora-sourcelinkmanager"></a><a name="dtor"></a>~ source_link_manager 

 Уничтожает `source_link_manager` объекта.  
  
```
~source_link_manager();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс single_link_registry](single-link-registry-class.md)   
 [Класс multi_link_registry](multi-link-registry-class.md)

