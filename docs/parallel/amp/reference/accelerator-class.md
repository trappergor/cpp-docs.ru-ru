---
title: "Класс Accelerator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMPRT/accelerator
- AMPRT/Concurrency::accelerator::accelerator
- AMPRT/Concurrency::accelerator::create_view
- AMPRT/Concurrency::accelerator::get_all
- AMPRT/Concurrency::accelerator::get_auto_selection_view
- AMPRT/Concurrency::accelerator::get_dedicated_memory
- AMPRT/Concurrency::accelerator::get_default_cpu_access_type
- AMPRT/Concurrency::accelerator::get_default_view
- AMPRT/Concurrency::accelerator::get_description
- AMPRT/Concurrency::accelerator::get_device_path
- AMPRT/Concurrency::accelerator::get_has_display
- AMPRT/Concurrency::accelerator::get_is_debug
- AMPRT/Concurrency::accelerator::get_is_emulated
- AMPRT/Concurrency::accelerator::get_supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::get_supports_double_precision
- AMPRT/Concurrency::accelerator::get_supports_limited_double_precision
- AMPRT/Concurrency::accelerator::get_version
- AMPRT/Concurrency::accelerator::set_default
- AMPRT/Concurrency::accelerator::set_default_cpu_access_type
- AMPRT/Concurrency::accelerator::cpu_accelerator
- AMPRT/Concurrency::accelerator::dedicated_memory
- AMPRT/Concurrency::accelerator::default_accelerator
- AMPRT/Concurrency::accelerator::default_cpu_access_type
- AMPRT/Concurrency::accelerator::default_view
- AMPRT/Concurrency::accelerator::description
- AMPRT/Concurrency::accelerator::device_path
- AMPRT/Concurrency::accelerator::direct3d_ref
- AMPRT/Concurrency::accelerator::direct3d_warp
- AMPRT/Concurrency::accelerator::has_display
- AMPRT/Concurrency::accelerator::is_debug
- AMPRT/Concurrency::accelerator::is_emulated
- AMPRT/Concurrency::accelerator::supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::supports_double_precision
- AMPRT/Concurrency::accelerator::supports_limited_double_precision
- AMPRT/Concurrency::accelerator::version
dev_langs: C++
helpviewer_keywords: accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: "29"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff64eeedb324d3a849029b15744cd630603aef67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-class"></a>Класс accelerator
Ускоритель — возможность оборудования, оптимальна для работы с параллельными данными. Ускоритель возможно, устройство, подключенное к шине PCIe (GPU) или может быть инструкция расширенной задать для основного ЦП.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор сочетаний клавиш](#ctor)|Инициализирует новый экземпляр класса `accelerator`.|  
|[~ accelerator, деструктор](#ctor)|Уничтожает `accelerator` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[create_view](#create_view)|Создает и возвращает `accelerator_view` объект на этом сочетаний клавиш.|  
|[get_all](#get_all)|Возвращает вектор `accelerator` объектов, представляющих доступные сочетания клавиш.|  
|[get_auto_selection_view](#get_auto_selection_view)|Возвращает автоматический выбор `accelerator_view`.|  
|[get_dedicated_memory](#get_dedicated_memory)|Возвращает выделенную память для `accelerator`, в килобайтах.|  
|[get_default_cpu_access_type](#get_default_cpu_access_type)|Возвращает значение по умолчанию [access_type](concurrency-namespace-enums-amp.md#access_type) буферы, созданные на этом сочетаний клавиш.|  
|[get_default_view](#get_default_view)|Возвращает значение по умолчанию `accelerator_view` объекта, с которым связан `accelerator`.|  
|[get_description](#get_description)|Возвращает краткое описание `accelerator` устройства.|  
|[get_device_path](#get_device_path)|Возвращает путь к устройству.|  
|[get_has_display](#get_has_display)|Определяет, является ли `accelerator` подключен на экран.|  
|[get_is_debug](#get_is_debug)|Определяет, является ли `accelerator` имеет уровень отладки расширенные отчеты об ошибках.|  
|[get_is_emulated](#get_is_emulated)|Определяет, является ли `accelerator` эмулируется.|  
|[get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|Определяет, является ли `accelerator` поддерживает общей памяти|  
|[get_supports_double_precision](#get_supports_double_precision)|Определяет, является ли `accelerator` подключен на экран.|  
|[get_supports_limited_double_precision](#get_supports_limited_double_precision)|Определяет, является ли `accelerator` имеет ограниченную поддержку математические двойной точности.|  
|[get_version](#get_version)|Возвращает версию `accelerator`.|  
|[set_default](#set_default)|Возвращает путь по умолчанию сочетания клавиш.|  
|[set_default_cpu_access_type](#set_default_cpu_access_type)|Задает ЦП по умолчанию [access_type](concurrency-namespace-enums-amp.md#access_type)для массивов и выделения памяти неявное, сделанные в этом `accelerator`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[оператор!=](#operator_neq)|Сравнивает этот `accelerator` с другим и возвращает `false` если они совпадают; в противном случае возвращает `true`.|  
|[оператор=](#operator_eq)|Копирует содержимое указанного `accelerator` этого объекта.|  
|[оператор==](#operator_eq_eq)|Сравнивает этот `accelerator` с другим и возвращает `true` если они совпадают; в противном случае возвращает `false`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[cpu_accelerator](#cpu_accelerator)|Получает строку константу для ЦП `accelerator`.|  
|[dedicated_memory](#dedicated_memory)|Возвращает объем памяти, выделенной для `accelerator`, в килобайтах.|  
|[default_accelerator](#default_accelerator)|Возвращает строку константой по умолчанию `accelerator`.|  
|[default_cpu_access_type](#default_cpu_access_type)|Возвращает или задает ЦП по умолчанию [access_type](concurrency-namespace-enums-amp.md#access_type)для массивов и выделения памяти неявное, сделанные в этом `accelerator`.|  
|[default_view](#default_view)|Возвращает значение по умолчанию `accelerator_view` объекта, с которым связан `accelerator`.|  
|[description](#description)|Возвращает краткое описание `accelerator` устройства.|  
|[device_path](#device_path)|Возвращает путь к устройству.|  
|[direct3d_ref](#direct3d_ref)|Получает строку константу для ссылки на Direct3D `accelerator`.|  
|[direct3d_warp](#direct3d_warp)|Возвращает строку для константы `accelerator` , который можно использовать для выполнения кода C++ AMP на многоядерных процессорах, использующих Streaming SIMD расширения (SSE).|  
|[has_display](#has_display)|Возвращает логическое значение, указывающее, является ли `accelerator` подключен на экран.|  
|[is_debug](#is_debug)|Указывает, является ли `accelerator` имеет уровень отладки расширенные отчеты об ошибках.|  
|[is_emulated](#is_emulated)|Указывает, является ли `accelerator` эмулируется.|  
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|Указывает, является ли `accelerator` поддерживает общую память.|  
|[supports_double_precision](#supports_double_precision)|Указывает, поддерживает ли сочетания клавиш математические двойной точности.|  
|[supports_limited_double_precision](#supports_limited_double_precision)|Указывает ли сочетания клавиш имеет ограниченную поддержку математические двойной точности.|  
|[version](#version)|Возвращает версию `accelerator`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `accelerator`  
  
## <a name="remarks"></a>Примечания  
 Ускоритель — возможность оборудования, оптимальна для работы с параллельными данными. Чаще всего ускоритель дискретных графического Процессора, но это также может быть это виртуальная сущность главного узла, например устройств DirectX REF, WARP (стороне ЦП устройство, которое accelerated посредством инструкции SSE) или самим ЦП.  
  
 Можно создать `accelerator` объекта путем перечисления доступных устройств или при получении устройства по умолчанию, ссылка устройства или устройства WARP.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  
  
##  <a name="dtor"></a></a> ~ accelerator 

 Уничтожает `accelerator` объекта.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="ctor"></a>сочетаний клавиш 

 Инициализирует новый экземпляр [класс accelerator](accelerator-class.md).  
  
```  
accelerator();

 
explicit accelerator(const std::wstring& _Device_path);

 
accelerator(const accelerator& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Device_path`  
 Путь к физическому устройству.  
  
 `_Other`  
 Сочетания клавиш для копирования.  
  
##  <a name="cpu_accelerator"></a>cpu_accelerator 

 Возвращает строку, константы для ЦП сочетания клавиш.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="create_view"></a>create_view 

 Создает и возвращает `accelerator_view` объекта на сочетаний клавиш, используя указанный режим постановки в очередь. Если не указан режим постановки в очередь, новый `accelerator_view` использует [queuing_mode::immediate](concurrency-namespace-enums-amp.md#queuing_mode) режим постановки в очередь.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>Параметры  
 `qmode`  
 Режим постановки в очередь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый `accelerator_view` объекта на сочетаний клавиш, используя указанный режим постановки в очередь.  
  
##  <a name="dedicated_memory"></a>dedicated_memory 

 Возвращает объем памяти, выделенной для `accelerator`, в килобайтах.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="default_accelerator"></a>default_accelerator 

 Возвращает строку константой по умолчанию `accelerator`.  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="default_cpu_access_type"></a>default_cpu_access_type 

 Значение по умолчанию ЦП [access_type](concurrency-namespace-enums-amp.md#access_type)для массивов и выделения памяти неявное, сделанные на это `accelerator`.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="default_view"></a>default_view 

 Возвращает представление сочетаний клавиш по умолчанию, связанные с `accelerator`.  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="description"></a>Описание 

 Возвращает краткое описание `accelerator` устройства.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="device_path"></a>device_path 

 Получает путь сочетания клавиш. Путь является уникальным в системе.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="direct3d_ref"></a>direct3d_ref 

 Возвращает строку, константы для сочетаний клавиш ссылки Direct3D.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="direct3d_warp"></a>direct3d_warp 

 Возвращает строку для константы `accelerator` , можно использовать для выполнения кода C++ AMP на многоядерных процессорах с помощью потоковой передачи расширений SIMD (SSE).  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="get_all"></a>get_all 

 Возвращает вектор `accelerator` объектов, представляющих доступные сочетания клавиш.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вектор доступные сочетания клавиш  
  
##  <a name="get_auto_selection_view"></a>get_auto_selection_view 

 Возвращает accelerator_view выбора автоматически, что после указан как целевой parallel_for_each результаты в accelerator_view целевой для выполнения ядра parallel_for_each автоматически выделяется средой выполнения. Для других целей accelerator_view, возвращаемый этим методом является accelerator_view по умолчанию сочетания клавиш по умолчанию  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Accelerator_view выбора автоматически.  
  
##  <a name="get_dedicated_memory"></a>get_dedicated_memory 

 Возвращает выделенную память для `accelerator`, в килобайтах.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выделенной памяти для `accelerator`, в килобайтах.  
  
##  <a name="get_default_cpu_access_type"></a>get_default_cpu_access_type 

 Возвращает access_type ЦП по умолчанию для буферов, созданные на этом сочетаний клавиш  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Access_type ЦП по умолчанию для буферов, созданные на этом сочетаний клавиш.  
  
##  <a name="get_default_view"></a>get_default_view 

 Возвращает значение по умолчанию `accelerator_view` объекта, с которым связан `accelerator`.  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение по умолчанию `accelerator_view` объекта, с которым связан `accelerator`.  
  
##  <a name="get_description"></a>get_description 

 Возвращает краткое описание `accelerator` устройства.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Краткое описание `accelerator` устройства.  
  
##  <a name="get_device_path"></a>get_device_path 

 Возвращает путь сочетания клавиш. Путь является уникальным в системе.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Путь к экземпляру устройства уникальным во всей системе.  
  
##  <a name="get_has_display"></a>get_has_display 

 Возвращает логическое значение, указывающее, является ли `accelerator` можно вывести на экран.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если `accelerator` можно вывести на экран; в противном случае `false`.  
  
##  <a name="get_is_debug"></a>get_is_debug 

 Определяет, является ли `accelerator` имеет уровень отладки расширенные отчеты об ошибках.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если `accelerator` имеет уровень отладки расширенные отчеты об ошибках. В противном случае — значение `false`.  
  
##  <a name="get_is_emulated"></a>get_is_emulated 

 Определяет, является ли `accelerator` эмулируется.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если `accelerator` эмулируется. В противном случае — значение `false`.  
  
##  <a name="get_supports_cpu_shared_memory"></a>get_supports_cpu_shared_memory 

 Возвращает логическое значение, указывающее, поддерживает ли сочетания клавиш памяти, доступный как сочетания клавиш и ЦП.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ускоритель поддерживает ЦП общей памяти; в противном случае `false`.  
  
##  <a name="get_supports_double_precision"></a>get_supports_double_precision 

 Возвращает логическое значение, указывающее, сочетания клавиш, поддержку двойной точности математические, включая совмещенного умножения добавить (FMA), деление, обратное и приведение между `int` и `double`.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ускоритель поддерживает двойной точности math; в противном случае `false`.  
  
##  <a name="get_supports_limited_double_precision"></a>get_supports_limited_double_precision 

 Возвращает логическое значение, указывающее ли сочетания клавиш имеет ограниченную поддержку двойной точности math. Если ускоритель имеет только ограниченную поддержку, затем совмещенного умножить добавить (FMA), деление, обратное и приведение между `int` и `double` не поддерживаются.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ускоритель имеет ограниченную поддержку двойной точности math; в противном случае `false`.  
  
##  <a name="get_version"></a>get_version 

 Возвращает версию `accelerator`.  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия `accelerator`.  
  
##  <a name="has_display"></a>has_display 

 Возвращает логическое значение, указывающее, является ли `accelerator` можно вывести на экран.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="is_debug"></a>is_debug 

 Возвращает логическое значение, указывающее, является ли `accelerator` имеет уровень отладки расширенные отчеты об ошибках.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="is_emulated"></a>is_emulated 

 Возвращает логическое значение, указывающее, является ли `accelerator` эмулируется.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="operator_neq"></a>оператор! = 

 Сравнивает этот `accelerator` с другим и возвращает `false` если они совпадают; в противном случае возвращает `true`.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator` Объект, сравниваемый с этим параметром.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `false`Если два `accelerator` объекты совпадают; в противном случае `true`.  
  
##  <a name="operator_eq"></a>оператор = 

 Копирует содержимое указанного `accelerator` этого объекта.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator` Объект для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `accelerator` объекта.  
  
##  <a name="operator_eq_eq"></a>оператор == 

 Сравнивает этот `accelerator` с другим и возвращает `true` если они совпадают; в противном случае возвращает `false`.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator` Объект, сравниваемый с этим параметром.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если другой `accelerator` объект является такой же, как это `accelerator` объекта; в противном случае `false`.  
  
##  <a name="set_default"></a>set_default 

 Задает сочетания клавиш по умолчанию для любой операции, неявно использует сочетания клавиш по умолчанию. Этот метод завершается успешно, только если установлен по умолчанию сочетания клавиш среды выполнения не уже используется в операции, неявно использует сочетания клавиш по умолчанию  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>Параметры  
 `_Path`  
 Путь к сочетания клавиш.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если вызов завершается успешно, на уровне сочетания клавиш по умолчанию. В противном случае — значение `false`.  
  
##  <a name="set_default_cpu_access_type"></a>set_default_cpu_access_type 

 Задайте access_type ЦП по умолчанию для массивов, созданных на этом сочетаний клавиш или для выделения памяти неявное как часть array_views доступны на это это решение. Этот метод завершается успешно, только если default_cpu_access_type для сочетания клавиш еще не был переопределен в результате предыдущего вызова этого метода и default_cpu_access_type среды выполнения выбран клавиш имеет еще не использовался для выделение памяти для массива или неявные области памяти резервное array_view, доступ к на это решение.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>Параметры  
 `_Default_cpu_access_type`  
 Access_type ЦП по умолчанию, используемый для выделения памяти массива или array_view это решение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, был успешно задан access_type ЦП по умолчанию для сочетания клавиш.  
  
##  <a name="supports_cpu_shared_memory"></a>supports_cpu_shared_memory 

 Возвращает логическое значение, указывающее, является ли `accelerator` поддерживает общую память.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="supports_double_precision"></a>supports_double_precision 

 Возвращает логическое значение, указывающее, поддерживает ли сочетания клавиш математические двойной точности.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="supports_limited_double_precision"></a>supports_limited_double_precision 

 Возвращает логическое значение, указывающее ли сочетания клавиш имеет ограниченную поддержку двойной точности math. Если ускоритель имеет только ограниченную поддержку, затем совмещенного умножить добавить (FMA), деление, обратное и приведение между `int` и `double` не поддерживаются.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="version"></a>Версия 

 Возвращает версию `accelerator`.  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="dtor"></a></a> ~ accelerator_view 

 Уничтожает [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="accelerator"></a>сочетаний клавиш 

 Возвращает `accelerator` для объекта [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="ctor"></a>accelerator_view 

 Инициализирует новый экземпляр [accelerator_view](accelerator-view-class.md) класса путем копирования существующего `accelerator_view` объекта.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект, подлежащий копированию.  
  
##  <a name="create_marker"></a>create_marker 

 Возвращает будущее отслеживать выполнение всех команд, переданных в данный момент к этому `accelerator_view` объекта.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Будущее отслеживать выполнение всех команд, переданных в данный момент к этому `accelerator_view` объекта.  
  
##  <a name="flush"></a>диск 

 Отправляет все команды, ожидающие в очереди на [accelerator_view](accelerator-view-class.md) объект для сочетания клавиш для выполнения.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  
  
##  <a name="get_accelerator"></a>get_accelerator 

 Возвращает `accelerator` для объекта [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `accelerator` Для объекта `accelerator_view` объекта.  
  
##  <a name="get_is_auto_selection"></a>get_is_auto_selection 

 Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при передаче accelerator_view [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если среда выполнения автоматически выбирает соответствующий сочетаний клавиш; в противном случае `false`.  
  
##  <a name="get_is_debug"></a>get_is_debug 

 Возвращает логическое значение, указывающее, является ли [accelerator_view](accelerator-view-class.md) объект имеет уровень отладки расширенные отчеты об ошибках.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень отладки расширенные отчеты об ошибках.  
  
##  <a name="get_queuing_mode"></a>get_queuing_mode 

 Возвращает режим постановки в очередь для [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Режим постановки в очередь для `accelerator_view` объекта.  
  
##  <a name="get_version"></a>get_version 

 Возвращает версию [accelerator_view](accelerator-view-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия `accelerator_view`.  
  
##  <a name="is_auto_selection"></a>is_auto_selection 

 Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при передаче accelerator_view [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="is_debug"></a>is_debug 

 Возвращает логическое значение, указывающее, является ли [accelerator_view](accelerator-view-class.md) объект имеет уровень отладки расширенные отчеты об ошибках.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="operator_neq"></a>оператор! = 

 Сравнивает этот [accelerator_view](accelerator-view-class.md) с другим и возвращает `false` если они совпадают; в противном случае возвращает `true`.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект, сравниваемый с этим параметром.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `false`, если объекты совпадают; в противном случае — значение `true`.  
  
##  <a name="operator_eq"></a>оператор = 

 Копирует содержимое указанного [accelerator_view](accelerator-view-class.md) объекта в другой.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на измененный `accelerator_view` объекта.  
  
##  <a name="operator_eq_eq"></a>оператор == 

 Сравнивает этот [accelerator_view](accelerator-view-class.md) с другим и возвращает `true` если они совпадают; в противном случае возвращает `false`.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект, сравниваемый с этим параметром.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объекты совпадают; в противном случае — значение `false`.  
  
##  <a name="queuing_mode"></a>queuing_mode 

 Получает режим постановки в очередь для [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="version"></a>Версия 

 Возвращает версию [accelerator_view](accelerator-view-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="wait"></a>Ожидание 

 Ожидания для всех команд, переданных [accelerator_view](accelerator-view-class.md) завершения.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
