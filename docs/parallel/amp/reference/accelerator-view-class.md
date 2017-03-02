---
title: "Класс accelerator_view | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator_view
dev_langs:
- C++
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: 18
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
ms.openlocfilehash: 78569f1ff21af3ed05cb908a851f0fe05d5d271a
ms.lasthandoff: 02/24/2017

---
# <a name="acceleratorview-class"></a>Класс accelerator_view
Представляет абстракцию виртуального устройства в ускорителе C++ AMP параллельными данными.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
class accelerator_view;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор accelerator_view](#ctor)|Инициализирует новый экземпляр класса `accelerator_view`.|  
|[~ accelerator_view деструктор](#dtor)|Уничтожает `accelerator_view` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод create_marker](#create_marker)|Возвращает будущее отслеживать выполнение всех команд, переданных пока это `accelerator_view` объекта.|  
|[Flush-метод](#flush)|Отправляет все ожидающие команды в очереди на `accelerator_view` объект сочетания клавиш для выполнения.|  
|[get_accelerator метод](#get_accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|  
|[Метод get_is_auto_selection](#get_is_auto_selection)|Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при `accelerator_view` передается объект [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[get_is_debug метод](#get_is_debug)|Возвращает логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень отладки расширенные отчеты об ошибках.|  
|[get_queuing_mode метод](#get_queuing_mode)|Возвращает режим постановки в очередь для `accelerator_view` объекта.|  
|[get_version метод](#get_version)|Возвращает версию `accelerator_view`.|  
|[wait-метод](#wait)|Ожидания для всех команд, переданных `accelerator_view` завершения.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор! =-оператор](#operator_neq)|Сравнивает этот `accelerator_view` и возвращает объект с другим `false` , если они совпадают; в противном случае — возвращает `true`.|  
|[оператор =-оператор](#operator_eq)|Копирует содержимое указанного `accelerator_view` объекта в другой.|  
|[оператор ==-оператор](#operator_eq_eq)|Сравнивает этот `accelerator_view` и возвращает объект с другим `true` , если они совпадают; в противном случае — возвращает `false`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных сочетаний клавиш](#accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|  
|[is_auto_selection элемент данных](#is_auto_selection)|Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при `accelerator_view` передается объект [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[is_debug элемент данных](#is_debug)|Возвращает логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень отладки расширенные отчеты об ошибках.|  
|[queuing_mode элемент данных](#queuing_mode)|Получает режим постановки в очередь для `accelerator_view` объекта.|  
|[версия элемента данных](#version)|Возвращает версию сочетания клавиш.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `accelerator_view`  
  
### <a name="remarks"></a>Примечания  
 `accelerator_view` Представляет логический изолированное представление ускорителя. Одного физического вычислительного устройства может иметь множество логических, изолированное `accelerator_view` объектов. Каждый ускоритель по умолчанию имеет `accelerator_view` объекта. Дополнительные `accelerator_view` объекты могут быть созданы.  
  
 Физические устройства могут совместно использоваться многими потоками клиента. Клиентские потоки могут совместно использовать тот же `accelerator_view` объект ускоритель или каждый клиент может взаимодействовать с устройством вычислений через независимый `accelerator_view` объекта для изоляции от других потоков клиента.  
  
 `accelerator_view` Объект может иметь один из двух [перечисление queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) состояния. Если режим постановки в очередь `immediate`, такие команды как `copy` и `parallel_for_each` отправляются по мере их возвращения вызывающему соответствующее устройство сочетаний клавиш. Если режим постановки в очередь `deferred`, таких команд в очередь на очереди команд, которые соответствуют `accelerator_view` объекта. Команды не отправляются на самом деле устройства до `flush()` вызывается.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  

## <a name="a-nameacceleratora-accelerator"></a><a name="accelerator"></a>сочетаний клавиш 

Получает объект сочетаний клавиш для объекта accelerator_view.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
## <a name="a-namectora-acceleratorview"></a><a name="ctor"></a>accelerator_view 

Инициализирует новый экземпляр класса accelerator_view путем копирования существующего `accelerator_view` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
accelerator_view( const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект, подлежащий копированию.  
  
## <a name="a-nameacceleratorviewcreatemarkera-createmarker"></a><a name="accelerator_view__create_marker"></a>create_marker 

Возвращает будущее отслеживать выполнение всех команд, переданных пока это `accelerator_view` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
concurrency::completion_future create_marker();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Будущее отслеживать выполнение всех команд, переданных пока это `accelerator_view` объекта.  
  
## <a name="a-nameflusha-flush"></a><a name="flush"></a>Очистить 

Отправка всех ожидающих применения команд в очереди объекта accelerator_view accelerator для выполнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void flush();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  

## <a name="a-nameacceleratorviewgetacceleratora-getaccelerator"></a><a name="accelerator_view__get_accelerator"></a>get_accelerator 

Возвращает объект для объекта accelerator_view сочетаний клавиш.
### <a name="syntax"></a>Синтаксис
```
accelerator get_accelerator() const;
```
### <a name="return-value"></a>Возвращаемое значение
Объект сочетаний клавиш для объекта accelerator_view.

## <a name="a-nameacceleratorviewgetisautoselectiona-getisautoselection"></a><a name="accelerator_view__get_is_auto_selection"></a>get_is_auto_selection 

Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при передаче accelerator_view [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool get_is_auto_selection() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если среда выполнения автоматически выбирает соответствующий сочетаний клавиш; в противном случае — `false`.  
  
## <a name="a-nameacceleratorviewgetisdebuga-getisdebug"></a><a name="accelerator_view__get_is_debug"></a>get_is_debug 

Возвращает логическое значение, указывающее, имеет ли объект accelerator_view уровень отладки расширенные отчеты об ошибках.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool get_is_debug() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень отладки расширенные отчеты об ошибках.  

## <a name="a-nameacceleratorviewgetqueuingmodea-getqueuingmode"></a><a name="accelerator_view__get_queuing_mode"></a>get_queuing_mode 

Возвращает режим постановки в очередь для объекта accelerator_view.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
queuing_mode get_queuing_mode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Режим постановки в очередь для `accelerator_view` объекта.  
  
## <a name="a-nameacceleratorviewgetversiona-getversion"></a><a name="accelerator_view__get_version"></a>get_version 

Возвращает версию accelerator_view.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
unsigned int get_version() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия `accelerator_view`.  
  
## <a name="a-nameacceleratorviewisautoselectiona-isautoselection"></a><a name="accelerator_view__is_auto_selection"></a>is_auto_selection 

Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при передаче accelerator_view [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
## <a name="a-nameacceleratorviewisdebuga-isdebug"></a><a name="accelerator_view__is_debug"></a>is_debug 

Возвращает логическое значение, указывающее, имеет ли объект accelerator_view уровень отладки расширенные отчеты об ошибках.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
## <a name="a-nameacceleratorviewoperatorneqa-operator"></a><a name="accelerator_view__operator_neq"></a>оператор! = 

Сравнивает этот объект accelerator_view с другого и возвращает `false` , если они совпадают; в противном случае — возвращает `true`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool operator!= (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `false`, если объекты совпадают; в противном случае — значение `true`.  
  
## <a name="a-nameacceleratorviewoperatoreqa-operator"></a><a name="accelerator_view__operator_eq"></a>оператор = 

Копирует содержимое объекта указанного accelerator_view в другой.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
accelerator_view & operator= (    const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на измененный `accelerator_view` объекта.  
  
## <a name="a-nameacceleratorviewoperatoreqeqa-operator"></a><a name="accelerator_view__operator_eq_eq"></a>оператор == 

Сравнивает этот объект accelerator_view с другого и возвращает `true` , если они совпадают; в противном случае — возвращает `false`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool operator= = (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объекты совпадают; в противном случае — значение `false`.  
  
## <a name="a-nameacceleratorviewqueuingmodea-queuingmode"></a><a name="accelerator_view__queuing_mode"></a>queuing_mode 

Получает режим постановки в очередь для объекта accelerator_view.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
## <a name="a-nameacceleratorviewversiona-version"></a><a name="accelerator_view__version"></a>Версия 

Возвращает версию accelerator_view.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
## <a name="a-nameacceleratorviewwaita-wait"></a><a name="accelerator_view__wait"></a>Ожидание 

Ожидания для всех команд, переданных объекту accelerator_view, Готово.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void wait();  
```  
  
#### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  
  
#### <a name="remarks"></a>Примечания  
 Если [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) — `immediate`, этот метод завершается сразу без блокировки.  
  
##  <a name="a-namedtora-acceleratorview"></a><a name="dtor"></a>~ accelerator_view 

 Удаляет объект accelerator_view.  
  
#### <a name="syntax"></a>Синтаксис  
  
```  
~accelerator_view();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
 
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

