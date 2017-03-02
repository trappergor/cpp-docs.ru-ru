---
title: "Класс Accelerator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator
dev_langs:
- C++
helpviewer_keywords:
- accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: 29
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
ms.openlocfilehash: b1bdd7f6979094658d1de6f9690bc44dc50ee8bb
ms.lasthandoff: 02/24/2017

---
# <a name="accelerator-class"></a>Класс accelerator
Ускоритель является возможностью оборудования, оптимизированный для данных параллельных вычислений. Ускоритель может быть устройство, подключенное к шине PCIe (например, GPU), или может быть расширенный набор основных ЦП инструкций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор сочетаний клавиш](#ctor)|Инициализирует новый экземпляр класса `accelerator`.|  
|[~ accelerator деструктор](#ctor)|Уничтожает `accelerator` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[create_view метод](#create_view)|Создает и возвращает `accelerator_view` объекта на это решение.|  
|[Метод get_all](#get_all)|Возвращает вектор `accelerator` объекты, представляющие все доступные ускорители.|  
|[Метод get_auto_selection_view](#get_auto_selection_view)|Возвращает автоматический выбор `accelerator_view`.|  
|[get_dedicated_memory метод](#get_dedicated_memory)|Возвращает выделенную память для `accelerator`, в килобайтах.|  
|[Метод get_default_cpu_access_type](#get_default_cpu_access_type)|Возвращает значение по умолчанию [access_type](concurrency-namespace-enums-amp.md#access_type) для буферы, созданные на это решение.|  
|[get_default_view метод](#get_default_view)|Возвращает значение по умолчанию `accelerator_view` , связанный с `accelerator`.|  
|[get_description метод](#get_description)|Возвращает краткое описание `accelerator` устройства.|  
|[get_device_path метод](#get_device_path)|Возвращает путь к устройству.|  
|[get_has_display метод](#get_has_display)|Определяет, является ли `accelerator` подключен на экран.|  
|[get_is_debug метод](#get_is_debug)|Определяет, является ли `accelerator` имеет уровень отладки расширенные отчеты об ошибках.|  
|[get_is_emulated метод](#get_is_emulated)|Определяет, является ли `accelerator` эмулируется.|  
|[Метод get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|Определяет, является ли `accelerator` поддерживает общей памяти|  
|[Метод get_supports_double_precision](#get_supports_double_precision)|Определяет, является ли `accelerator` подключен на экран.|  
|[Метод get_supports_limited_double_precision](#get_supports_limited_double_precision)|Определяет, является ли `accelerator` имеет ограниченную поддержку математические двойной точности.|  
|[get_version метод](#get_version)|Возвращает версию `accelerator`.|  
|[Метод set_default](#set_default)|Возвращает путь по умолчанию сочетания клавиш.|  
|[Метод set_default_cpu_access_type](#set_default_cpu_access_type)|Задает ЦП по умолчанию [access_type](concurrency-namespace-enums-amp.md#access_type)для массивов и выделения памяти неявное об этом `accelerator`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор! =-оператор](#operator_neq)|Сравнивает этот `accelerator` и возвращает объект с другим `false` , если они совпадают; в противном случае — возвращает `true`.|  
|[оператор =-оператор](#operator_eq)|Копирует содержимое указанного `accelerator` этого объекта.|  
|[оператор ==-оператор](#operator_eq_eq)|Сравнивает этот `accelerator` и возвращает объект с другим `true` , если они совпадают; в противном случае — возвращает `false`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[cpu_accelerator элемент данных](#cpu_accelerator)|Возвращает строку, постоянное ЦП `accelerator`.|  
|[dedicated_memory элемент данных](#dedicated_memory)|Возвращает объем памяти, выделенной для `accelerator`, в килобайтах.|  
|[default_accelerator элемент данных](#default_accelerator)|Возвращает строку, константой по умолчанию `accelerator`.|  
|[default_cpu_access_type элемент данных](#default_cpu_access_type)|Возвращает или задает ЦП по умолчанию [access_type](concurrency-namespace-enums-amp.md#access_type)для массивов и выделения памяти неявное об этом `accelerator`.|  
|[default_view элемент данных](#default_view)|Возвращает значение по умолчанию `accelerator_view` , связанный с `accelerator`.|  
|[Описание элемента данных](#description)|Возвращает краткое описание `accelerator` устройства.|  
|[device_path элемент данных](#device_path)|Возвращает путь к устройству.|  
|[direct3d_ref-элемент данных](#direct3d_ref)|Получает строку константу для ссылки на Direct3D `accelerator`.|  
|[direct3d_warp-элемент данных](#direct3d_warp)|Получает константу для строки `accelerator` объекта можно использовать для выполнения кода C++ AMP на многоядерных процессорах, использующих Streaming SIMD Extensions (SSE).|  
|[has_display элемент данных](#has_display)|Возвращает логическое значение, указывающее, является ли `accelerator` подключен на экран.|  
|[is_debug элемент данных](#is_debug)|Указывает, является ли `accelerator` имеет уровень отладки расширенные отчеты об ошибках.|  
|[is_emulated элемент данных](#is_emulated)|Указывает, является ли `accelerator` эмулируется.|  
|[supports_cpu_shared_memory элемент данных](#supports_cpu_shared_memory)|Указывает, является ли `accelerator` поддерживает общей памяти.|  
|[supports_double_precision элемент данных](#supports_double_precision)|Указывает, поддерживает ли ускоритель математические двойной точности.|  
|[supports_limited_double_precision элемент данных](#supports_limited_double_precision)|Указывает ли сочетания клавиш имеет ограниченную поддержку математические двойной точности.|  
|[версия элемента данных](#version)|Возвращает версию `accelerator`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `accelerator`  
  
## <a name="remarks"></a>Примечания  
 Ускоритель является возможностью оборудования, оптимизированный для данных параллельных вычислений. Чаще всего ускоритель дискретных GPU, но также может быть виртуальная сущность стороне главного приложения, например устройство DirectX REF, ДЕФОРМАЦИИ (стороне ЦП устройство, которое ускоряет загрузку при помощи инструкции SSE) или самим ЦП.  
  
 Можно создать `accelerator` объекта путем перечисления доступных устройств или путем получения устройство по умолчанию, ДЕФОРМАЦИИ устройства или устройства ссылки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  
  
##  <a name="dtor"></a></a> ~ accelerator 

 Уничтожает `accelerator` объекта.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-namectora-accelerator"></a><a name="ctor"></a>сочетаний клавиш 

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
  
##  <a name="a-namecpuacceleratora-cpuaccelerator"></a><a name="cpu_accelerator"></a>cpu_accelerator 

 Возвращает строку, постоянное ускорителя ЦП.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="a-namecreateviewa-createview"></a><a name="create_view"></a>create_view 

 Создает и возвращает `accelerator_view` объекта на это решение, используя указанный режим постановки в очередь. Если не указан режим постановки в очередь, новый `accelerator_view` использует [queuing_mode::immediate](concurrency-namespace-enums-amp.md#queuing_mode) режим постановки в очередь.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>Параметры  
 `qmode`  
 Режим постановки в очередь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый `accelerator_view` объекта на это решение, используя указанный режим постановки в очередь.  
  
##  <a name="a-namededicatedmemorya-dedicatedmemory"></a><a name="dedicated_memory"></a>dedicated_memory 

 Возвращает объем памяти, выделенной для `accelerator`, в килобайтах.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="a-namedefaultacceleratora-defaultaccelerator"></a><a name="default_accelerator"></a>default_accelerator 

 Возвращает строку, константой по умолчанию `accelerator`.  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="a-namedefaultcpuaccesstypea-defaultcpuaccesstype"></a><a name="default_cpu_access_type"></a>default_cpu_access_type 

 Значение по умолчанию ЦП [access_type](concurrency-namespace-enums-amp.md#access_type)для массивов и выделения памяти неявное на этом `accelerator`.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="a-namedefaultviewa-defaultview"></a><a name="default_view"></a>default_view 

 Возвращает представление сочетаний клавиш по умолчанию, связанные с `accelerator`.  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="a-namedescriptiona-description"></a><a name="description"></a>Описание 

 Возвращает краткое описание `accelerator` устройства.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="a-namedevicepatha-devicepath"></a><a name="device_path"></a>device_path 

 Возвращает путь сочетания клавиш. Путь является уникальным в системе.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="a-namedirect3drefa-direct3dref"></a><a name="direct3d_ref"></a>direct3d_ref 

 Возвращает строку, константы для ускоритель ссылку Direct3D.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="a-namedirect3dwarpa-direct3dwarp"></a><a name="direct3d_warp"></a>direct3d_warp 

 Получает константу для строки `accelerator` объекта можно использовать для выполнения кода C++ AMP на многоядерных процессоров с помощью Streaming SIMD Extensions (SSE).  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="a-namegetalla-getall"></a><a name="get_all"></a>get_all 

 Возвращает вектор `accelerator` объекты, представляющие все доступные ускорители.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вектор доступных ускорителей  
  
##  <a name="a-namegetautoselectionviewa-getautoselectionview"></a><a name="get_auto_selection_view"></a>get_auto_selection_view 

 Возвращает accelerator_view выбора auto, который в случае указан как целевой parallel_for_each результаты в accelerator_view целевой ядра parallel_for_each автоматически выделяется средой выполнения. Для других целей accelerator_view, возвращаемый этим методом является accelerator_view по умолчанию ускорителя по умолчанию  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Accelerator_view Выбор автоматически.  
  
##  <a name="a-namegetdedicatedmemorya-getdedicatedmemory"></a><a name="get_dedicated_memory"></a>get_dedicated_memory 

 Возвращает выделенную память для `accelerator`, в килобайтах.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выделенной памяти для `accelerator`, в килобайтах.  
  
##  <a name="a-namegetdefaultcpuaccesstypea-getdefaultcpuaccesstype"></a><a name="get_default_cpu_access_type"></a>get_default_cpu_access_type 

 Возвращает access_type ЦП по умолчанию буферы, созданные на этом сочетаний клавиш  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Access_type ЦП по умолчанию для буферы, созданные на это решение.  
  
##  <a name="a-namegetdefaultviewa-getdefaultview"></a><a name="get_default_view"></a>get_default_view 

 Возвращает значение по умолчанию `accelerator_view` , связанный с `accelerator`.  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение по умолчанию `accelerator_view` , связанный с `accelerator`.  
  
##  <a name="a-namegetdescriptiona-getdescription"></a><a name="get_description"></a>get_description 

 Возвращает краткое описание `accelerator` устройства.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Краткое описание `accelerator` устройства.  
  
##  <a name="a-namegetdevicepatha-getdevicepath"></a><a name="get_device_path"></a>get_device_path 

 Возвращает путь сочетания клавиш. Путь является уникальным в системе.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Путь к экземпляру устройства уникальным во всей системе.  
  
##  <a name="a-namegethasdisplaya-gethasdisplay"></a><a name="get_has_display"></a>get_has_display 

 Возвращает логическое значение, указывающее, является ли `accelerator` можно вывести на экран.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если `accelerator` можно вывести на экран; в противном случае — `false`.  
  
##  <a name="a-namegetisdebuga-getisdebug"></a><a name="get_is_debug"></a>get_is_debug 

 Определяет, является ли `accelerator` имеет уровень отладки расширенные отчеты об ошибках.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если `accelerator` имеет уровень отладки расширенные отчеты об ошибках. В противном случае — значение `false`.  
  
##  <a name="a-namegetisemulateda-getisemulated"></a><a name="get_is_emulated"></a>get_is_emulated 

 Определяет, является ли `accelerator` эмулируется.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если `accelerator` эмулируется. В противном случае — значение `false`.  
  
##  <a name="a-namegetsupportscpusharedmemorya-getsupportscpusharedmemory"></a><a name="get_supports_cpu_shared_memory"></a>get_supports_cpu_shared_memory 

 Возвращает логическое значение, указывающее, поддерживает ли сочетания клавиш памяти, доступный как сочетания клавиш и ЦП.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ускоритель поддерживает ЦП общей памяти; в противном случае — `false`.  
  
##  <a name="a-namegetsupportsdoubleprecisiona-getsupportsdoubleprecision"></a><a name="get_supports_double_precision"></a>get_supports_double_precision 

 Возвращает логическое значение, указывающее ли ускоритель поддерживает двойной точности math, включая совмещенного умножения добавьте (FMA), деления и обратное, приведение между `int` и `double`.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ускоритель поддерживает двойной точности math; в противном случае — `false`.  
  
##  <a name="a-namegetsupportslimiteddoubleprecisiona-getsupportslimiteddoubleprecision"></a><a name="get_supports_limited_double_precision"></a>get_supports_limited_double_precision 

 Возвращает логическое значение, указывающее ли сочетания клавиш имеет ограниченную поддержку для двойной точности math. Если ускоритель имеет только ограниченную поддержку, затем умножьте совмещенного добавьте (FMA), деления и обратное, приведение между `int` и `double` не поддерживаются.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если ускоритель имеет ограниченную поддержку для двойной точности math; в противном случае — `false`.  
  
##  <a name="a-namegetversiona-getversion"></a><a name="get_version"></a>get_version 

 Возвращает версию `accelerator`.  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия `accelerator`.  
  
##  <a name="a-namehasdisplaya-hasdisplay"></a><a name="has_display"></a>has_display 

 Возвращает логическое значение, указывающее, является ли `accelerator` можно вывести на экран.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="a-nameisdebuga-isdebug"></a><a name="is_debug"></a>is_debug 

 Возвращает логическое значение, указывающее, является ли `accelerator` имеет уровень отладки расширенные отчеты об ошибках.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameisemulateda-isemulated"></a><a name="is_emulated"></a>is_emulated 

 Возвращает логическое значение, указывающее, является ли `accelerator` эмулируется.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>оператор! = 

 Сравнивает этот `accelerator` и возвращает объект с другим `false` , если они совпадают; в противном случае — возвращает `true`.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `false`Если два `accelerator` объекты совпадают; в противном случае — `true`.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

 Копирует содержимое указанного `accelerator` этого объекта.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `accelerator` объекта.  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>оператор == 

 Сравнивает этот `accelerator` и возвращает объект с другим `true` , если они совпадают; в противном случае — возвращает `false`.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если другой `accelerator` объект является такой же, как это `accelerator` объекта; в противном случае — `false`.  
  
##  <a name="a-namesetdefaulta-setdefault"></a><a name="set_default"></a>set_default 

 Задает используемый для любой операции, неявно использует по умолчанию ускорителя по умолчанию ускорителя. Этот метод завершается успешно, только если accelerator установлен по умолчанию среда выполнения не уже используется в операции, неявно использует сочетания клавиш по умолчанию  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>Параметры  
 `_Path`  
 Путь к сочетания клавиш.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если вызов осуществляется на уровне сочетания клавиш по умолчанию. В противном случае — значение `false`.  
  
##  <a name="a-namesetdefaultcpuaccesstypea-setdefaultcpuaccesstype"></a><a name="set_default_cpu_access_type"></a>set_default_cpu_access_type 

 Задайте access_type ЦП по умолчанию для массивов, созданных на это решение, или для выделения памяти неявное как часть array_views недоступен на этом это решение. Этот метод завершается успешно, только если default_cpu_access_type для сочетания клавиш еще не был переопределен в результате предыдущего вызова этого метода и default_cpu_access_type выбранной среды выполнения для это решение имеет еще не использовался для выделение памяти для массива или неявные памяти, резервном array_view доступ осуществляется через этот ускоритель.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>Параметры  
 `_Default_cpu_access_type`  
 Access_type ЦП по умолчанию, используемый для выделения памяти массив или array_view это решение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, был успешно установлен access_type ЦП по умолчанию для сочетания клавиш.  
  
##  <a name="a-namesupportscpusharedmemorya-supportscpusharedmemory"></a><a name="supports_cpu_shared_memory"></a>supports_cpu_shared_memory 

 Возвращает логическое значение, указывающее, является ли `accelerator` поддерживает общей памяти.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="a-namesupportsdoubleprecisiona-supportsdoubleprecision"></a><a name="supports_double_precision"></a>supports_double_precision 

 Возвращает логическое значение, указывающее, поддерживает ли ускоритель математические двойной точности.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="a-namesupportslimiteddoubleprecisiona-supportslimiteddoubleprecision"></a><a name="supports_limited_double_precision"></a>supports_limited_double_precision 

 Возвращает логическое значение, указывающее ли сочетания клавиш имеет ограниченную поддержку для двойной точности math. Если ускоритель имеет только ограниченную поддержку, затем умножьте совмещенного добавьте (FMA), деления и обратное, приведение между `int` и `double` не поддерживаются.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="a-nameversiona-version"></a><a name="version"></a>Версия 

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
  
##  <a name="a-nameacceleratora-accelerator"></a><a name="accelerator"></a>сочетаний клавиш 

 Возвращает `accelerator` для объекта [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="a-namectora-acceleratorview"></a><a name="ctor"></a>accelerator_view 

 Инициализирует новый экземпляр [accelerator_view](accelerator-view-class.md) класса путем копирования существующего `accelerator_view` объекта.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект, подлежащий копированию.  
  
##  <a name="a-namecreatemarkera-createmarker"></a><a name="create_marker"></a>create_marker 

 Возвращает будущее отслеживать выполнение всех команд, переданных пока это `accelerator_view` объекта.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Будущее отслеживать выполнение всех команд, переданных пока это `accelerator_view` объекта.  
  
##  <a name="a-nameflusha-flush"></a><a name="flush"></a>Очистить 

 Отправляет все ожидающие команды в очереди на [accelerator_view](accelerator-view-class.md) объекта сочетания клавиш для выполнения.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  
  
##  <a name="a-namegetacceleratora-getaccelerator"></a><a name="get_accelerator"></a>get_accelerator 

 Возвращает `accelerator` для объекта [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `accelerator` Для объекта `accelerator_view` объекта.  
  
##  <a name="a-namegetisautoselectiona-getisautoselection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection 

 Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при передаче accelerator_view [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если среда выполнения автоматически выбирает соответствующий сочетаний клавиш; в противном случае — `false`.  
  
##  <a name="a-namegetisdebuga-getisdebug"></a><a name="get_is_debug"></a>get_is_debug 

 Возвращает логическое значение, указывающее, является ли [accelerator_view](accelerator-view-class.md) объект имеет уровень отладки расширенные отчеты об ошибках.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень отладки расширенные отчеты об ошибках.  
  
##  <a name="a-namegetqueuingmodea-getqueuingmode"></a><a name="get_queuing_mode"></a>get_queuing_mode 

 Возвращает режим постановки в очередь для [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Режим постановки в очередь для `accelerator_view` объекта.  
  
##  <a name="a-namegetversiona-getversion"></a><a name="get_version"></a>get_version 

 Возвращает версию [accelerator_view](accelerator-view-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия `accelerator_view`.  
  
##  <a name="a-nameisautoselectiona-isautoselection"></a><a name="is_auto_selection"></a>is_auto_selection 

 Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при передаче accelerator_view [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="a-nameisdebuga-isdebug"></a><a name="is_debug"></a>is_debug 

 Возвращает логическое значение, указывающее, является ли [accelerator_view](accelerator-view-class.md) объект имеет уровень отладки расширенные отчеты об ошибках.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>оператор! = 

 Сравнивает этот [accelerator_view](accelerator-view-class.md) и возвращает объект с другим `false` , если они совпадают; в противном случае — возвращает `true`.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `false`, если объекты совпадают; в противном случае — значение `true`.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

 Копирует содержимое указанного [accelerator_view](accelerator-view-class.md) объекта в другой.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на измененный `accelerator_view` объекта.  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>оператор == 

 Сравнивает этот [accelerator_view](accelerator-view-class.md) и возвращает объект с другим `true` , если они совпадают; в противном случае — возвращает `false`.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `accelerator_view` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объекты совпадают; в противном случае — значение `false`.  
  
##  <a name="a-namequeuingmodea-queuingmode"></a><a name="queuing_mode"></a>queuing_mode 

 Получает режим постановки в очередь для [accelerator_view](accelerator-view-class.md) объекта.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="a-nameversiona-version"></a><a name="version"></a>Версия 

 Возвращает версию [accelerator_view](accelerator-view-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>Ожидание 

 Ожидания для всех команд, переданных [accelerator_view](accelerator-view-class.md) завершения.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

