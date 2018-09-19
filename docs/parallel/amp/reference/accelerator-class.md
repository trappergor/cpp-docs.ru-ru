---
title: Класс Accelerator | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dee005091c95bbac5fca64851f631b443bd33cca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106776"
---
# <a name="accelerator-class"></a>Класс accelerator
Ускоритель — это возможность оборудования, которая оптимизирована для параллельной обработки данных. Ускоритель может быть устройство, подключенное к шине PCIe (например, GPU), или может быть расширенным набором инструкций на главном ЦП.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор сочетаний клавиш](#ctor)|Инициализирует новый экземпляр класса `accelerator`.|  
|[~ accelerator, деструктор](#ctor)|Уничтожает `accelerator` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[create_view](#create_view)|Создает и возвращает `accelerator_view` на этом ускорителе.|  
|[get_all](#get_all)|Возвращает вектор `accelerator` объекты, которые представляют все допустимые ускорители.|  
|[get_auto_selection_view](#get_auto_selection_view)|Возвращает Автовыбор `accelerator_view`.|  
|[get_dedicated_memory](#get_dedicated_memory)|Возвращает специальную память для `accelerator`, в килобайтах.|  
|[get_default_cpu_access_type](#get_default_cpu_access_type)|Возвращает значение по умолчанию [access_type](concurrency-namespace-enums-amp.md#access_type) для буферов, созданных на этом ускорителе.|  
|[get_default_view](#get_default_view)|Возвращает значение по умолчанию `accelerator_view` объекта, связанного с `accelerator`.|  
|[get_description](#get_description)|Возвращает краткое описание `accelerator` устройства.|  
|[get_device_path](#get_device_path)|Возвращает путь к устройству.|  
|[get_has_display](#get_has_display)|Определяет, является ли `accelerator` вложенным для отображения.|  
|[get_is_debug](#get_is_debug)|Определяет, является ли `accelerator` имеет уровень DEBUG для расширенных отчетов об ошибках.|  
|[get_is_emulated](#get_is_emulated)|Определяет, является ли `accelerator` эмулируется.|  
|[get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|Определяет, является ли `accelerator` поддерживает общей памяти|  
|[get_supports_double_precision](#get_supports_double_precision)|Определяет, является ли `accelerator` вложенным для отображения.|  
|[get_supports_limited_double_precision](#get_supports_limited_double_precision)|Определяет, является ли `accelerator` ограниченной поддержкой математики двойной точности.|  
|[get_version](#get_version)|Возвращает версию `accelerator`.|  
|[set_default](#set_default)|Возвращает путь ускорителя по умолчанию.|  
|[set_default_cpu_access_type](#set_default_cpu_access_type)|Задает ЦП по умолчанию [access_type](concurrency-namespace-enums-amp.md#access_type)для массивов и неявных выделений памяти для данного `accelerator`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор!=](#operator_neq)|Сравнивает этот `accelerator` объект с другим и возвращает `false` если они совпадают; в противном случае возвращает `true`.|  
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `accelerator` в данный объект.|  
|[оператор==](#operator_eq_eq)|Сравнивает этот `accelerator` объект с другим и возвращает `true` если они совпадают; в противном случае возвращает `false`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[cpu_accelerator](#cpu_accelerator)|Получает строковую константу для ЦП `accelerator`.|  
|[dedicated_memory](#dedicated_memory)|Получает выделенную память для `accelerator`, в килобайтах.|  
|[default_accelerator](#default_accelerator)|Получает строковую константу для применяемого по умолчанию `accelerator`.|  
|[default_cpu_access_type](#default_cpu_access_type)|Возвращает или задает ЦП по умолчанию [access_type](concurrency-namespace-enums-amp.md#access_type)для массивов и неявных выделений памяти для данного `accelerator`.|  
|[default_view](#default_view)|Получает значение по умолчанию `accelerator_view` объекта, связанного с `accelerator`.|  
|[description](#description)|Возвращает краткое описание `accelerator` устройства.|  
|[device_path](#device_path)|Получает путь к устройству.|  
|[direct3d_ref](#direct3d_ref)|Получает строковую константу для ссылки на Direct3D `accelerator`.|  
|[direct3d_warp](#direct3d_warp)|Получает строковую константу для `accelerator` который можно использовать для выполнения кода C++ AMP на многоядерных процессорах, использующих Streaming SIMD Extensions (SSE).|  
|[has_display](#has_display)|Возвращает логическое значение, указывающее, является ли `accelerator` вложенным для отображения.|  
|[is_debug](#is_debug)|Указывает, является ли `accelerator` имеет уровень DEBUG для расширенных отчетов об ошибках.|  
|[is_emulated](#is_emulated)|Указывает, является ли `accelerator` эмулируется.|  
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|Указывает, является ли `accelerator` поддерживает общую память.|  
|[supports_double_precision](#supports_double_precision)|Указывает, поддерживает ли ускоритель математики двойной точности.|  
|[supports_limited_double_precision](#supports_limited_double_precision)|Указывает ли ускоритель ограниченной поддержкой математики двойной точности.|  
|[version](#version)|Получает версию `accelerator`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `accelerator`  
  
## <a name="remarks"></a>Примечания  
 Ускоритель — это возможность оборудования, которая оптимизирована для параллельной обработки данных. Ускоритель часто является отдельным GPU, но это также может быть виртуальной сущностью стороне главного приложения, такие как устройство DirectX REF, WARP (со стороны ЦП устройство, которое ускоряется с помощью инструкции SSE) или самим ЦП.  
  
 Вы можете создать `accelerator` объекта, перечисляя доступные устройства или путем получения устройства по умолчанию, устройства ссылки или устройства WARP.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  
  
##  <a name="dtor"></a> </a> ~ accelerator 

 Уничтожает `accelerator` объекта.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="ctor"></a> сочетаний клавиш 

 Инициализирует новый экземпляр класса [accelerator-класс](accelerator-class.md).  
  
```  
accelerator();

 
explicit accelerator(const std::wstring& _Device_path);

 
accelerator(const accelerator& _Other);
```  
  
### <a name="parameters"></a>Параметры  
*_Device_path*<br/>
Путь к физическому устройству.  
  
*_Другое*<br/>
Ускоритель, подлежащий копированию.  
  
##  <a name="cpu_accelerator"></a> cpu_accelerator 

 Получает строковую константу для Процессорного ускорителя.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="create_view"></a> create_view 

 Создает и возвращает `accelerator_view` на этом ускорителе, используя указанный режим организации очереди. Если режим организации очереди не указан, новый `accelerator_view` использует [queuing_mode::immediate](concurrency-namespace-enums-amp.md#queuing_mode) режим организации очереди.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>Параметры  
*qmode*<br/>
Режим организации очереди.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый `accelerator_view` на этом ускорителе, используя указанный режим организации очереди.  
  
##  <a name="dedicated_memory"></a> dedicated_memory 

 Получает выделенную память для `accelerator`, в килобайтах.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="default_accelerator"></a> default_accelerator 

 Получает строковую константу для применяемого по умолчанию `accelerator`.  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="default_cpu_access_type"></a> default_cpu_access_type 

 Значение по умолчанию ЦП [access_type](concurrency-namespace-enums-amp.md#access_type)для массивов и неявных выделений памяти для данного `accelerator`.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="default_view"></a> default_view 

 Возвращает представление ускорителя по умолчанию, с которым связан `accelerator`.  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="description"></a> Описание 

 Возвращает краткое описание `accelerator` устройства.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="device_path"></a> device_path 

 Получает путь к ускорителю. Путь является уникальным в системе.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="direct3d_ref"></a> direct3d_ref 

 Получает строковую константу для ссылки ускорителем Direct3D.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="direct3d_warp"></a> direct3d_warp 

 Получает строковую константу для `accelerator` который можно использовать для выполнения кода C++ AMP на многоядерных ЦП, с помощью Streaming SIMD Extensions (SSE).  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="get_all"></a> get_all 

 Возвращает вектор `accelerator` объекты, которые представляют все допустимые ускорители.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вектор доступных ускорителей  
  
##  <a name="get_auto_selection_view"></a> get_auto_selection_view 

 Возвращает автоматическое accelerator_view выделения, который, будучи указан как целевой объект parallel_for_each приводит к accelerator_view целевого объекта для выполнения ядро parallel_for_each автоматически выделяется средой выполнения. Для других целей accelerator_view, возвращаемый этим методом совпадает со значением по умолчанию accelerator_view ускорителя по умолчанию  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Автоматическое выделение accelerator_view.  
  
##  <a name="get_dedicated_memory"></a> get_dedicated_memory 

 Возвращает специальную память для `accelerator`, в килобайтах.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выделенная память для `accelerator`, в килобайтах.  
  
##  <a name="get_default_cpu_access_type"></a> get_default_cpu_access_type 

 Получает access_type ЦП по умолчанию для буферов, созданных на этом сочетание клавиш  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Access_type ЦП по умолчанию для буферов, созданных на этом ускорителе.  
  
##  <a name="get_default_view"></a> get_default_view 

 Возвращает значение по умолчанию `accelerator_view` объекта, связанного с `accelerator`.  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение по умолчанию `accelerator_view` объекта, связанного с `accelerator`.  
  
##  <a name="get_description"></a> get_description 

 Возвращает краткое описание `accelerator` устройства.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Краткое описание `accelerator` устройства.  
  
##  <a name="get_device_path"></a> get_device_path 

 Возвращает путь к ускорителю. Путь является уникальным в системе.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Путь к экземпляру устройства уникальным во всей системе.  
  
##  <a name="get_has_display"></a> get_has_display 

 Возвращает логическое значение, указывающее, является ли `accelerator` можно выводить данные на дисплей.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если `accelerator` можно выводить данные на дисплей; в противном случае `false`.  
  
##  <a name="get_is_debug"></a> get_is_debug 

 Определяет, является ли `accelerator` имеет уровень DEBUG для расширенных отчетов об ошибках.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если `accelerator` имеет уровень DEBUG для расширенных отчетов об ошибках. В противном случае — значение `false`.  
  
##  <a name="get_is_emulated"></a> get_is_emulated 

 Определяет, является ли `accelerator` эмулируется.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если `accelerator` эмулируется. В противном случае — значение `false`.  
  
##  <a name="get_supports_cpu_shared_memory"></a> get_supports_cpu_shared_memory 

 Возвращает логическое значение, указывающее, поддерживает ли ускоритель память доступной оба сочетанием клавиш и ЦП.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если ускоритель поддерживает общую память с ЦП; в противном случае `false`.  
  
##  <a name="get_supports_double_precision"></a> get_supports_double_precision 

 Возвращает логическое значение, указывающее, поддерживает ли ускоритель математические операции двойной точности, включая совмещенного умножения-сложения (FMA), деления, обратная величина и приведения между `int` и `double`.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если ускоритель поддерживает математические операции двойной точности; в противном случае `false`.  
  
##  <a name="get_supports_limited_double_precision"></a> get_supports_limited_double_precision 

 Возвращает логическое значение, указывающее, является ли ускоритель имеет ограниченную поддержку математические операции двойной точности. Если ускоритель имеет только ограниченную поддержку, затем совмещенного умножения сложения (FMA), деления, обратная величина и приведения между `int` и `double` не поддерживаются.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если ускоритель имеет ограниченную поддержку математические операции двойной точности; в противном случае `false`.  
  
##  <a name="get_version"></a> get_version 

 Возвращает версию `accelerator`.  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия `accelerator`.  
  
##  <a name="has_display"></a> has_display 

 Возвращает логическое значение, указывающее, является ли `accelerator` можно выводить данные на дисплей.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="is_debug"></a> is_debug 

 Возвращает логическое значение, указывающее, является ли `accelerator` имеет уровень DEBUG для расширенных отчетов об ошибках.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="is_emulated"></a> is_emulated 

 Возвращает логическое значение, указывающее, является ли `accelerator` эмулируется.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="operator_neq"></a> оператор! = 

 Сравнивает этот `accelerator` объект с другим и возвращает `false` если они совпадают; в противном случае возвращает `true`.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
*_Другое*<br/>
`accelerator` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `false` Если два `accelerator` объекты совпадают; в противном случае `true`.  
  
##  <a name="operator_eq"></a> оператор = 

 Копирует содержимое указанного объекта `accelerator` в данный объект.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>Параметры  
*_Другое*<br/>
`accelerator` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на этот `accelerator` объекта.  
  
##  <a name="operator_eq_eq"></a> оператор == 

 Сравнивает этот `accelerator` объект с другим и возвращает `true` если они совпадают; в противном случае возвращает `false`.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
*_Другое*<br/>
`accelerator` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если другой `accelerator` объект то же, что это `accelerator` объекта; в противном случае `false`.  
  
##  <a name="set_default"></a> set_default 

 Задает сочетания клавиш по умолчанию использоваться для любой операции, которая неявно использует сочетание клавиш по умолчанию. Этот метод завершается успешно, только если установлен по умолчанию сочетания клавиш среды выполнения не уже используется в операции, которая неявно использует сочетание клавиш по умолчанию  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>Параметры  
*_Путь*<br/>
Путь к ускорителю.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если вызов завершается успешно задан ускоритель по умолчанию. В противном случае — значение `false`.  
  
##  <a name="set_default_cpu_access_type"></a> set_default_cpu_access_type 

 Задайте access_type ЦП по умолчанию для массивов, созданных на этом ускорителе, или для неявных выделений памяти как часть array_views, доступ на этом ускорителе. Этот метод завершается успешно, только если default_cpu_access_type для сочетания клавиш еще не переопределенное предыдущим вызовом этого метода и default_cpu_access_type для этот ускоритель имеет еще не использовался для выделения массива или неявного выделения памяти дублируя array_view, доступ на этом ускорителе.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>Параметры  
*_Default_cpu_access_type*<br/>
Access_type ЦП по умолчанию, используемый для выделения памяти массива или array_view на этом ускорителе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, был успешно задан access_type ЦП по умолчанию для сочетания клавиш.  
  
##  <a name="supports_cpu_shared_memory"></a> supports_cpu_shared_memory 

 Возвращает логическое значение, указывающее, является ли `accelerator` поддерживает общую память.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="supports_double_precision"></a> supports_double_precision 

 Возвращает логическое значение, указывающее, поддерживает ли ускоритель математики двойной точности.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="supports_limited_double_precision"></a> supports_limited_double_precision 

 Возвращает логическое значение, указывающее, является ли ускоритель имеет ограниченную поддержку математические операции двойной точности. Если ускоритель имеет только ограниченную поддержку, затем совмещенного умножения сложения (FMA), деления, обратная величина и приведения между `int` и `double` не поддерживаются.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="version"></a> Версия 

 Получает версию `accelerator`.  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="dtor"></a> </a> ~ accelerator_view 

 Уничтожает [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="accelerator"></a> сочетаний клавиш 

 Получает `accelerator` для объекта [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="ctor"></a> accelerator_view 

 Инициализирует новый экземпляр класса [accelerator_view](accelerator-view-class.md) класса путем копирования существующего `accelerator_view` объекта.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Параметры  
*_Другое*<br/>
`accelerator_view` Копируемый объект.  
  
##  <a name="create_marker"></a> create_marker 

 Возвращает фьючерс для отслеживания выполнения всех команд, отправленных до сих данному `accelerator_view` объекта.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект фьючерса для отслеживания выполнения всех команд, отправленных до сих к этому `accelerator_view` объекта.  
  
##  <a name="flush"></a> Очистить 

 Отправляет все команды, ожидающие в очереди на [accelerator_view](accelerator-view-class.md) объект для выполнения на ускорителе.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  
  
##  <a name="get_accelerator"></a> get_accelerator 

 Возвращает `accelerator` для объекта [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `accelerator` Для объекта `accelerator_view` объекта.  
  
##  <a name="get_is_auto_selection"></a> get_is_auto_selection 

 Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующий ускоритель при передаче accelerator_view [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если среда выполнения будет автоматически выбирать соответствующий ускоритель; в противном случае `false`.  
  
##  <a name="get_is_debug"></a> get_is_debug 

 Возвращает логическое значение, указывающее, является ли [accelerator_view](accelerator-view-class.md) объект имеет уровень DEBUG для расширенных отчетов об ошибках.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень DEBUG для расширенных отчетов об ошибках.  
  
##  <a name="get_queuing_mode"></a> get_queuing_mode 

 Возвращает режим организации очереди для [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Режим организации очереди для `accelerator_view` объекта.  
  
##  <a name="get_version"></a> get_version 

 Возвращает версию [accelerator_view](accelerator-view-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия `accelerator_view`.  
  
##  <a name="is_auto_selection"></a> is_auto_selection 

 Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующий ускоритель при передаче accelerator_view [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="is_debug"></a> is_debug 

 Возвращает логическое значение, указывающее, является ли [accelerator_view](accelerator-view-class.md) объект имеет уровень DEBUG для расширенных отчетов об ошибках.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="operator_neq"></a> оператор! = 

 Сравнивает этот [accelerator_view](accelerator-view-class.md) объект с другим и возвращает `false` если они совпадают; в противном случае возвращает `true`.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
*_Другое*<br/>
`accelerator_view` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `false`, если объекты совпадают; в противном случае — значение `true`.  
  
##  <a name="operator_eq"></a> оператор = 

 Копирует содержимое указанного объекта [accelerator_view](accelerator-view-class.md) в данный объект.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Параметры  
*_Другое*<br/>
`accelerator_view` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на измененный `accelerator_view` объекта.  
  
##  <a name="operator_eq_eq"></a> оператор == 

 Сравнивает этот [accelerator_view](accelerator-view-class.md) объект с другим и возвращает `true` если они совпадают; в противном случае возвращает `false`.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
*_Другое*<br/>
`accelerator_view` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объекты совпадают; в противном случае — значение `false`.  
  
##  <a name="queuing_mode"></a> queuing_mode 

 Получает режим организации очереди для [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="version"></a> Версия 

 Получает версию [accelerator_view](accelerator-view-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="wait"></a> Подождите 

 Ожидает в течение всех команд, отправленных [accelerator_view](accelerator-view-class.md) объекта до конца.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
