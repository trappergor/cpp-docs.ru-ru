---
title: "Класс source_link_manager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
dev_langs: C++
helpviewer_keywords: source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 75be5687e63fe38f1ffa8f91c41963dfa1171e48
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|`const_pointer`|Тип, предоставляющий указатель на `const` элемент в `source_link_manager` объекта.|  
|`const_reference`|Тип, предоставляющий ссылку на `const` элемент хранится в `source_link_manager` объект для чтения и выполнения операций const.|  
|`iterator`|Тип, предоставляющий итератор, который может считывать или изменять любой элемент в `source_link_manager` объекта.|  
|`type`|Тип реестр ссылок, которые управляются этим `source_link_manager` объекта.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[source_link_manager](#ctor)|Создает объект `source_link_manager`.|  
|[~ source_link_manager деструктор](#dtor)|Уничтожает `source_link_manager` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[add](#add)|Добавляет ссылку на источник `source_link_manager` объекта.|  
|[begin](#begin)|Возвращает итератор на первый элемент в `source_link_manager` объекта.|  
|[содержит](#contains)|Поиск `network_link_registry` в рамках этого `source_link_manager` объекта для указанного блока.|  
|[count](#count)|Подсчитывает количество связанных блоков в `source_link_manager` объекта.|  
|[reference](#reference)|Получает ссылку на `source_link_manager` объекта.|  
|[register_target_block](#register_target_block)|Регистрирует целевой блок, который содержит это `source_link_manager` объекта.|  
|[release](#release)|Освобождает ссылку на `source_link_manager` объекта.|  
|[remove](#remove)|Удаляет ссылку из `source_link_manager` объекта.|  
|[set_bound](#set_bound)|Задает максимальное число ссылок источника, который может быть добавлен к этому `source_link_manager` объекта.|  
  
## <a name="remarks"></a>Примечания  
 В настоящее время блоки источника имеется счетчик ссылок. Это оболочка на `network_link_registry` объект, который допускает параллельный доступ к ссылкам и предоставляет возможность обращаться ссылки через обратные вызовы. Блоки сообщений ( `target_block`s или `propagator_block`s) следует использовать этот класс для их связей "источник".  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `source_link_manager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="add"></a>добавить 

 Добавляет ссылку на источник `source_link_manager` объекта.  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок для добавления.  
  
##  <a name="begin"></a>начать 

 Возвращает итератор на первый элемент в `source_link_manager` объекта.  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, обращающийся к первому элементу в `source_link_manager` объекта.  
  
### <a name="remarks"></a>Примечания  
 Конечное состояние итератора обозначается `NULL` ссылку.  
  
##  <a name="contains"></a>содержит 

 Поиск `network_link_registry` в рамках этого `source_link_manager` объекта для указанного блока.  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок, который необходимо найти в `source_link_manager` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если указанная блокировка найдена, `false` в противном случае.  
  
##  <a name="count"></a>Счетчик 

 Подсчитывает количество связанных блоков в `source_link_manager` объекта.  
  
```
size_t count();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число связанных блоков в `source_link_manager` объекта.  
  
##  <a name="reference"></a>ссылка 

 Получает ссылку на `source_link_manager` объекта.  
  
```
void reference();
```  
  
##  <a name="register_target_block"></a>register_target_block 

 Регистрирует целевой блок, который содержит это `source_link_manager` объекта.  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Целевой блок, содержащий это `source_link_manager` объекта.  
  
##  <a name="release"></a>выпуск 

 Освобождает ссылку на `source_link_manager` объекта.  
  
```
void release();
```  
  
##  <a name="remove"></a>удалить 

 Удаляет ссылку из `source_link_manager` объекта.  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Параметры  
 `_Link`  
 Указатель на блок удалены, если найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ссылка была найдена и удалена, `false` в противном случае.  
  
##  <a name="set_bound"></a>set_bound 

 Задает максимальное число ссылок источника, который может быть добавлен к этому `source_link_manager` объекта.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Параметры  
 `_MaxLinks`  
 Максимальное число ссылок.  
  
##  <a name="ctor"></a>source_link_manager 

 Создает объект `source_link_manager`.  
  
```
source_link_manager();
```  
  
##  <a name="dtor"></a>~ source_link_manager 

 Уничтожает `source_link_manager` объекта.  
  
```
~source_link_manager();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс single_link_registry](single-link-registry-class.md)   
 [Класс multi_link_registry](multi-link-registry-class.md)
