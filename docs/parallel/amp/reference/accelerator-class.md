---
title: "Класс accelerator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::accelerator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator - класс"
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# Класс accelerator
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ускоритель является возможностью оборудования, оптимизированный для данных параллельных вычислений. Ускоритель может быть устройство, подключенное к шине PCIe (например, GPU), или может быть расширенный набор основных ЦП инструкций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор Accelerator::Accelerator](#accelerator__accelerator_constructor)|Инициализирует новый экземпляр класса `accelerator`.|  
|[Accelerator:: ~ accelerator деструктор](#accelerator___dtoraccelerator_destructor)|Уничтожает `accelerator` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Accelerator::create_view](#accelerator__create_view_method)|Создает и возвращает `accelerator_view` объекта на это решение.|  
|[Метод Accelerator::get_all](#accelerator__get_all_method)|Возвращает вектор `accelerator` объекты, представляющие все доступные ускорители.|  
|[Метод Accelerator::get_auto_selection_view](#accelerator__get_auto_selection_view_method)|Возвращает автоматический выбор `accelerator_view`.|  
|[Метод Accelerator::get_dedicated_memory](#accelerator__get_dedicated_memory_method)|Возвращает выделенную память для `accelerator`, в килобайтах.|  
|[Метод Accelerator::get_default_cpu_access_type](#accelerator__get_default_cpu_access_type_method)|Возвращает значение по умолчанию [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) для буферы, созданные на это решение.|  
|[Метод Accelerator::get_default_view](#accelerator__get_default_view_method)|Возвращает значение по умолчанию `accelerator_view` связанный с `accelerator`.|  
|[Метод Accelerator::get_description](#accelerator__get_description_method)|Возвращает краткое описание `accelerator` устройства.|  
|[Метод Accelerator::get_device_path](#accelerator__get_device_path_method)|Возвращает путь к устройству.|  
|[Метод Accelerator::get_has_display](#accelerator__get_has_display_method)|Определяет, является ли `accelerator` подключен на экран.|  
|[Метод Accelerator::get_is_debug](#accelerator__get_is_debug_method)|Определяет, является ли `accelerator` имеет уровень ОТЛАДКИ расширенные отчеты об ошибках.|  
|[Метод Accelerator::get_is_emulated](#accelerator__get_is_emulated_method)|Определяет, является ли `accelerator` эмулируется.|  
|[Метод Accelerator::get_supports_cpu_shared_memory](#accelerator__get_supports_cpu_shared_memory_method)|Определяет, является ли `accelerator` поддерживает общей памяти|  
|[Метод Accelerator::get_supports_double_precision](#accelerator__get_supports_double_precision_method)|Определяет, является ли `accelerator` подключен на экран.|  
|[Метод Accelerator::get_supports_limited_double_precision](#accelerator__get_supports_limited_double_precision_method)|Определяет, является ли `accelerator` имеет ограниченную поддержку математические двойной точности.|  
|[Метод Accelerator::get_version](#accelerator__get_version_method)|Возвращает версию `accelerator`.|  
|[Метод Accelerator::set_default](#accelerator__set_default_method)|Возвращает путь по умолчанию сочетания клавиш.|  
|[Метод Accelerator::set_default_cpu_access_type](#accelerator__set_default_cpu_access_type_method)|Задает ЦП по умолчанию [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) для массивов и выделения памяти неявное об этом `accelerator`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Accelerator::operator! =-оператор](#accelerator__operator_neq_operator)|Сравнивает этот `accelerator` объект с другим и возвращает `false` если они совпадают; в противном случае — возвращает `true`.|  
|[Accelerator::operator =-оператор](#accelerator__operator_eq_operator)|Копирует содержимое указанного `accelerator` этого объекта.|  
|[Accelerator::operator ==-оператор](#accelerator__operator_eq_eq_operator)|Сравнивает этот `accelerator` объект с другим и возвращает `true` если они совпадают; в противном случае — возвращает `false`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[элемент данных Accelerator::cpu_accelerator](#accelerator__cpu_accelerator_data_member)|Возвращает строку, постоянное ЦП `accelerator`.|  
|[элемент данных Accelerator::dedicated_memory](#accelerator__dedicated_memory_data_member)|Возвращает объем памяти, выделенной для `accelerator`, в килобайтах.|  
|[элемент данных Accelerator::default_accelerator](#accelerator__default_accelerator_data_member)|Возвращает строку, константой по умолчанию `accelerator`.|  
|[элемент данных Accelerator::default_cpu_access_type](#accelerator__default_cpu_access_type_data_member)|Возвращает или задает ЦП по умолчанию [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) для массивов и выделения памяти неявное об этом `accelerator`.|  
|[элемент данных Accelerator::default_view](#accelerator__default_view_data_member)|Возвращает значение по умолчанию `accelerator_view` связанный с `accelerator`.|  
|[элемент данных Accelerator::Description](#accelerator__description_data_member)|Возвращает краткое описание `accelerator` устройства.|  
|[элемент данных Accelerator::device_path](#accelerator__device_path_data_member)|Возвращает путь к устройству.|  
|[элемент данных Accelerator::direct3d_ref](#accelerator__direct3d_ref_data_member)|Получает строку константу для ссылки на Direct3D `accelerator`.|  
|[элемент данных Accelerator::direct3d_warp](#accelerator__direct3d_warp_data_member)|Получает константу для строки [accelerator](../../../parallel/amp/reference/accelerator-class.md) объекта можно использовать для выполнения кода C++ AMP на многоядерных процессорах, использующих Streaming SIMD Extensions (SSE).|  
|[элемент данных Accelerator::has_display](#accelerator__has_display_data_member)|Возвращает логическое значение, указывающее, является ли `accelerator` подключен на экран.|  
|[элемент данных Accelerator::is_debug](#accelerator__is_debug_data_member)|Указывает, является ли `accelerator` имеет уровень ОТЛАДКИ расширенные отчеты об ошибках.|  
|[элемент данных Accelerator::is_emulated](#accelerator__is_emulated_data_member)|Указывает, является ли `accelerator` эмулируется.|  
|[элемент данных Accelerator::supports_cpu_shared_memory](#accelerator__supports_cpu_shared_memory_data_member)|Указывает, является ли `accelerator` поддерживает общей памяти.|  
|[элемент данных Accelerator::supports_double_precision](#accelerator__supports_double_precision_data_member)|Указывает, поддерживает ли ускоритель математические двойной точности.|  
|[элемент данных Accelerator::supports_limited_double_precision](#accelerator__supports_limited_double_precision_data_member)|Указывает ли сочетания клавиш имеет ограниченную поддержку математические двойной точности.|  
|[элемент данных Accelerator::Version](#accelerator__version_data_member)|Возвращает версию `accelerator`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `accelerator`  
  
## <a name="remarks"></a>Примечания  
 Ускоритель является возможностью оборудования, оптимизированный для данных параллельных вычислений. Чаще всего ускоритель дискретных GPU, но также может быть виртуальная сущность стороне главного приложения, например устройство DirectX REF, ДЕФОРМАЦИИ (стороне ЦП устройство, которое ускоряет загрузку при помощи инструкции SSE) или самим ЦП.  
  
 Можно создать `accelerator` объекта путем перечисления доступных устройств или путем получения устройство по умолчанию, ДЕФОРМАЦИИ устройства или устройства ссылки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  
  
##  <a name="a-nameacceleratordtoracceleratordestructora-acceleratoraccelerator-destructor"></a><a name="accelerator___dtoraccelerator_destructor"></a>  Accelerator:: ~ accelerator деструктор  
 Уничтожает [accelerator](../../../parallel/amp/reference/accelerator-class.md) объекта.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameacceleratoracceleratorconstructora-acceleratoraccelerator-constructor"></a><a name="accelerator__accelerator_constructor"></a>  Конструктор Accelerator::Accelerator  
 Инициализирует новый экземпляр [accelerator-класс](../../../parallel/amp/reference/accelerator-class.md).  
  
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
  
##  <a name="a-nameacceleratorcpuacceleratordatamembera-acceleratorcpuaccelerator-data-member"></a><a name="accelerator__cpu_accelerator_data_member"></a>  элемент данных Accelerator::cpu_accelerator  
 Возвращает строку, постоянное ускорителя ЦП.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="a-nameacceleratorcreateviewmethoda-acceleratorcreateview-method"></a><a name="accelerator__create_view_method"></a>  Метод Accelerator::create_view  
 Создает и возвращает `accelerator_view` объекта на это решение, используя указанный режим постановки в очередь. Если не указан режим постановки в очередь, новый `accelerator_view` использует [queuing_mode::immediate](../Topic/concurrency%20namespace%20enums.md#queuing_mode) режим постановки в очередь.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>Параметры  
 `qmode`  
 Режим постановки в очередь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый `accelerator_view` объекта на это решение, используя указанный режим постановки в очередь.  
  
##  <a name="a-nameacceleratordedicatedmemorydatamembera-acceleratordedicatedmemory-data-member"></a><a name="accelerator__dedicated_memory_data_member"></a>  элемент данных Accelerator::dedicated_memory  
 Возвращает объем памяти, выделенной для [accelerator](../../../parallel/amp/reference/accelerator-class.md), в килобайтах.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="a-nameacceleratordefaultacceleratordatamembera-acceleratordefaultaccelerator-data-member"></a><a name="accelerator__default_accelerator_data_member"></a>  элемент данных Accelerator::default_accelerator  
 Возвращает строку, константой по умолчанию [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="a-nameacceleratordefaultcpuaccesstypedatamembera-acceleratordefaultcpuaccesstype-data-member"></a><a name="accelerator__default_cpu_access_type_data_member"></a>  элемент данных Accelerator::default_cpu_access_type  
 Значение по умолчанию ЦП [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) для массивов и выделения памяти неявное на этом `accelerator`.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="a-nameacceleratordefaultviewdatamembera-acceleratordefaultview-data-member"></a><a name="accelerator__default_view_data_member"></a>  элемент данных Accelerator::default_view  
 Возвращает представление сочетаний клавиш по умолчанию, связанные с [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="a-nameacceleratordescriptiondatamembera-acceleratordescription-data-member"></a><a name="accelerator__description_data_member"></a>  элемент данных Accelerator::Description  
 Возвращает краткое описание [accelerator](../../../parallel/amp/reference/accelerator-class.md) устройства.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="a-nameacceleratordevicepathdatamembera-acceleratordevicepath-data-member"></a><a name="accelerator__device_path_data_member"></a>  элемент данных Accelerator::device_path  
 Возвращает путь сочетания клавиш. Путь является уникальным в системе.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="a-nameacceleratordirect3drefdatamembera-acceleratordirect3dref-data-member"></a><a name="accelerator__direct3d_ref_data_member"></a>  элемент данных Accelerator::direct3d_ref  
 Возвращает строку, константы для ускоритель ссылку Direct3D.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="a-nameacceleratordirect3dwarpdatamembera-acceleratordirect3dwarp-data-member"></a><a name="accelerator__direct3d_warp_data_member"></a>  элемент данных Accelerator::direct3d_warp  
 Получает константу для строки [accelerator](../../../parallel/amp/reference/accelerator-class.md) объекта можно использовать для выполнения кода C++ AMP на многоядерных процессоров с помощью Streaming SIMD Extensions (SSE).  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="a-nameacceleratorgetallmethoda-acceleratorgetall-method"></a><a name="accelerator__get_all_method"></a>  Метод Accelerator::get_all  
 Возвращает вектор `accelerator` объекты, представляющие все доступные ускорители.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вектор доступных ускорителей  
  
##  <a name="a-nameacceleratorgetautoselectionviewmethoda-acceleratorgetautoselectionview-method"></a><a name="accelerator__get_auto_selection_view_method"></a>  Метод Accelerator::get_auto_selection_view  
 Возвращает accelerator_view выбора auto, который в случае указан как целевой parallel_for_each результаты в accelerator_view целевой ядра parallel_for_each автоматически выделяется средой выполнения. Для других целей accelerator_view, возвращаемый этим методом является accelerator_view по умолчанию ускорителя по умолчанию  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Accelerator_view Выбор автоматически.  
  
##  <a name="a-nameacceleratorgetdedicatedmemorymethoda-acceleratorgetdedicatedmemory-method"></a><a name="accelerator__get_dedicated_memory_method"></a>  Метод Accelerator::get_dedicated_memory  
 Возвращает выделенную память для [accelerator](../../../parallel/amp/reference/accelerator-class.md), в килобайтах.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выделенной памяти для `accelerator`, в килобайтах.  
  
##  <a name="a-nameacceleratorgetdefaultcpuaccesstypemethoda-acceleratorgetdefaultcpuaccesstype-method"></a><a name="accelerator__get_default_cpu_access_type_method"></a>  Метод Accelerator::get_default_cpu_access_type  
 Возвращает access_type ЦП по умолчанию буферы, созданные на этом сочетаний клавиш  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Access_type ЦП по умолчанию для буферы, созданные на это решение.  
  
##  <a name="a-nameacceleratorgetdefaultviewmethoda-acceleratorgetdefaultview-method"></a><a name="accelerator__get_default_view_method"></a>  Метод Accelerator::get_default_view  
 Возвращает значение по умолчанию `accelerator_view` объекта, с которым связан [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение по умолчанию `accelerator_view` связанный с `accelerator`.  
  
##  <a name="a-nameacceleratorgetdescriptionmethoda-acceleratorgetdescription-method"></a><a name="accelerator__get_description_method"></a>  Метод Accelerator::get_description  
 Возвращает краткое описание [accelerator](../../../parallel/amp/reference/accelerator-class.md) устройства.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Краткое описание `accelerator` устройства.  
  
##  <a name="a-nameacceleratorgetdevicepathmethoda-acceleratorgetdevicepath-method"></a><a name="accelerator__get_device_path_method"></a>  Метод Accelerator::get_device_path  
 Возвращает путь сочетания клавиш. Путь является уникальным в системе.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Путь к экземпляру устройства уникальным во всей системе.  
  
##  <a name="a-nameacceleratorgethasdisplaymethoda-acceleratorgethasdisplay-method"></a><a name="accelerator__get_has_display_method"></a>  Метод Accelerator::get_has_display  
 Возвращает логическое значение, указывающее, является ли [accelerator](../../../parallel/amp/reference/accelerator-class.md) может выводить на экран.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если `accelerator` можно вывести на экран; в противном случае — `false`.  
  
##  <a name="a-nameacceleratorgetisdebugmethoda-acceleratorgetisdebug-method"></a><a name="accelerator__get_is_debug_method"></a>  Метод Accelerator::get_is_debug  
 Определяет, является ли [accelerator](../../../parallel/amp/reference/accelerator-class.md) имеет уровень ОТЛАДКИ расширенные отчеты об ошибках.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если `accelerator` имеет уровень ОТЛАДКИ расширенные отчеты об ошибках. В противном случае — значение `false`.  
  
##  <a name="a-nameacceleratorgetisemulatedmethoda-acceleratorgetisemulated-method"></a><a name="accelerator__get_is_emulated_method"></a>  Метод Accelerator::get_is_emulated  
 Определяет, является ли [accelerator](../../../parallel/amp/reference/accelerator-class.md) эмулируется.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если `accelerator` эмулируется. В противном случае — значение `false`.  
  
##  <a name="a-nameacceleratorgetsupportscpusharedmemorymethoda-acceleratorgetsupportscpusharedmemory-method"></a><a name="accelerator__get_supports_cpu_shared_memory_method"></a>  Метод Accelerator::get_supports_cpu_shared_memory  
 Возвращает логическое значение, указывающее, поддерживает ли сочетания клавиш памяти, доступный как сочетания клавиш и ЦП.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если ускоритель поддерживает ЦП общей памяти; в противном случае — `false`.  
  
##  <a name="a-nameacceleratorgetsupportsdoubleprecisionmethoda-acceleratorgetsupportsdoubleprecision-method"></a><a name="accelerator__get_supports_double_precision_method"></a>  Метод Accelerator::get_supports_double_precision  
 Возвращает логическое значение, указывающее ли ускоритель поддерживает двойной точности math, включая совмещенного умножения добавьте (FMA), деления и обратное, приведение между `int` и `double`.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если ускоритель поддерживает двойной точности math; в противном случае — `false`.  
  
##  <a name="a-nameacceleratorgetsupportslimiteddoubleprecisionmethoda-acceleratorgetsupportslimiteddoubleprecision-method"></a><a name="accelerator__get_supports_limited_double_precision_method"></a>  Метод Accelerator::get_supports_limited_double_precision  
 Возвращает логическое значение, указывающее ли сочетания клавиш имеет ограниченную поддержку для двойной точности math. Если ускоритель имеет только ограниченную поддержку, затем умножьте совмещенного добавьте (FMA), деления и обратное, приведение между `int` и `double` не поддерживаются.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если ускоритель имеет ограниченную поддержку для двойной точности math; в противном случае — `false`.  
  
##  <a name="a-nameacceleratorgetversionmethoda-acceleratorgetversion-method"></a><a name="accelerator__get_version_method"></a>  Метод Accelerator::get_version  
 Возвращает версию [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия `accelerator`.  
  
##  <a name="a-nameacceleratorhasdisplaydatamembera-acceleratorhasdisplay-data-member"></a><a name="accelerator__has_display_data_member"></a>  элемент данных Accelerator::has_display  
 Возвращает логическое значение, указывающее, является ли [accelerator](../../../parallel/amp/reference/accelerator-class.md) может выводить на экран.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="a-nameacceleratorisdebugdatamembera-acceleratorisdebug-data-member"></a><a name="accelerator__is_debug_data_member"></a>  элемент данных Accelerator::is_debug  
 Возвращает логическое значение, указывающее, является ли [accelerator](../../../parallel/amp/reference/accelerator-class.md) имеет уровень ОТЛАДКИ расширенные отчеты об ошибках.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorisemulateddatamembera-acceleratorisemulated-data-member"></a><a name="accelerator__is_emulated_data_member"></a>  элемент данных Accelerator::is_emulated  
 Возвращает логическое значение, указывающее, является ли [accelerator](../../../parallel/amp/reference/accelerator-class.md) эмулируется.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="a-nameacceleratoroperatorneqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_neq_operator"></a>  Accelerator::operator! =-оператор  
 Сравнивает этот `accelerator` объект с другим и возвращает `false` если они совпадают; в противном случае — возвращает `true`.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
  `accelerator` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `false` Если два `accelerator` объекты совпадают; в противном случае — `true`.  
  
##  <a name="a-nameacceleratoroperatoreqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_operator"></a>  Accelerator::operator =-оператор  
 Копирует содержимое указанного [accelerator](../../../parallel/amp/reference/accelerator-class.md) этого объекта.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
  `accelerator` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `accelerator` объекта.  
  
##  <a name="a-nameacceleratoroperatoreqeqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_eq_operator"></a>  Accelerator::operator ==-оператор  
 Сравнивает этот [accelerator](../../../parallel/amp/reference/accelerator-class.md) объект с другим и возвращает `true` если они совпадают; в противном случае — возвращает `false`.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
  `accelerator` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если другой `accelerator` объект является такой же, как это `accelerator` объекта; в противном случае — `false`.  
  
##  <a name="a-nameacceleratorsetdefaultmethoda-acceleratorsetdefault-method"></a><a name="accelerator__set_default_method"></a>  Метод Accelerator::set_default  
 Задает используемый для любой операции, неявно использует по умолчанию ускорителя по умолчанию ускорителя. Этот метод завершается успешно, только если accelerator установлен по умолчанию среда выполнения не уже используется в операции, неявно использует сочетания клавиш по умолчанию  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>Параметры  
 `_Path`  
 Путь к сочетания клавиш.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если вызов осуществляется на уровне сочетания клавиш по умолчанию. В противном случае — значение `false`.  
  
##  <a name="a-nameacceleratorsetdefaultcpuaccesstypemethoda-acceleratorsetdefaultcpuaccesstype-method"></a><a name="accelerator__set_default_cpu_access_type_method"></a>  Метод Accelerator::set_default_cpu_access_type  
 Задайте access_type ЦП по умолчанию для массивов, созданных на это решение, или для выделения памяти неявное как часть array_views недоступен на этом это решение. Этот метод завершается успешно, только если default_cpu_access_type для сочетания клавиш еще не был переопределен в результате предыдущего вызова этого метода и default_cpu_access_type выбранной среды выполнения для это решение имеет еще не использовался для выделение памяти для массива или неявные памяти, резервном array_view доступ осуществляется через этот ускоритель.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>Параметры  
 `_Default_cpu_access_type`  
 Access_type ЦП по умолчанию, используемый для выделения памяти массив или array_view это решение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, был успешно установлен access_type ЦП по умолчанию для сочетания клавиш.  
  
##  <a name="a-nameacceleratorsupportscpusharedmemorydatamembera-acceleratorsupportscpusharedmemory-data-member"></a><a name="accelerator__supports_cpu_shared_memory_data_member"></a>  элемент данных Accelerator::supports_cpu_shared_memory  
 Возвращает логическое значение, указывающее, является ли `accelerator` поддерживает общей памяти.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="a-nameacceleratorsupportsdoubleprecisiondatamembera-acceleratorsupportsdoubleprecision-data-member"></a><a name="accelerator__supports_double_precision_data_member"></a>  элемент данных Accelerator::supports_double_precision  
 Возвращает логическое значение, указывающее, поддерживает ли ускоритель математические двойной точности.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="a-nameacceleratorsupportslimiteddoubleprecisiondatamembera-acceleratorsupportslimiteddoubleprecision-data-member"></a><a name="accelerator__supports_limited_double_precision_data_member"></a>  элемент данных Accelerator::supports_limited_double_precision  
 Возвращает логическое значение, указывающее ли сочетания клавиш имеет ограниченную поддержку для двойной точности math. Если ускоритель имеет только ограниченную поддержку, затем умножьте совмещенного добавьте (FMA), деления и обратное, приведение между `int` и `double` не поддерживаются.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="a-nameacceleratorversiondatamembera-acceleratorversion-data-member"></a><a name="accelerator__version_data_member"></a>  элемент данных Accelerator::Version  
 Возвращает версию [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewdtoracceleratorviewdestructora-acceleratorviewacceleratorview-destructor"></a><a name="accelerator_view___dtoraccelerator_view_destructor"></a>  accelerator_view:: ~ accelerator_view деструктор  
 Уничтожает [accelerator_view](../Topic/accelerator_view%20Class.md) объекта.  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameacceleratorviewacceleratordatamembera-acceleratorviewaccelerator-data-member"></a><a name="accelerator_view__accelerator_data_member"></a>  элемент данных accelerator_view::Accelerator  
 Возвращает [accelerator](../../../parallel/amp/reference/accelerator-class.md) для объекта [accelerator_view](../Topic/accelerator_view%20Class.md) объекта.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="a-nameacceleratorviewacceleratorviewconstructora-acceleratorviewacceleratorview-constructor"></a><a name="accelerator_view__accelerator_view_constructor"></a>  Конструктор accelerator_view::accelerator_view  
 Инициализирует новый экземпляр [accelerator_view](../Topic/accelerator_view%20Class.md) класса путем копирования существующего `accelerator_view` объекта.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
  `accelerator_view` Объект, подлежащий копированию.  
  
##  <a name="a-nameacceleratorviewcreatemarkermethoda-acceleratorviewcreatemarker-method"></a><a name="accelerator_view__create_marker_method"></a>  Метод accelerator_view::create_marker  
 Возвращает будущее отслеживать выполнение всех команд, переданных пока это `accelerator_view` объекта.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Будущее отслеживать выполнение всех команд, переданных пока это `accelerator_view` объекта.  
  
##  <a name="a-nameacceleratorviewflushmethoda-acceleratorviewflush-method"></a><a name="accelerator_view__flush_method"></a>  Метод accelerator_view::Flush  
 Отправляет все ожидающие команды в очереди на [accelerator_view](../Topic/accelerator_view%20Class.md) объекта сочетания клавиш для выполнения.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  
  
##  <a name="a-nameacceleratorviewgetacceleratormethoda-acceleratorviewgetaccelerator-method"></a><a name="accelerator_view__get_accelerator_method"></a>  Метод accelerator_view::get_accelerator  
 Возвращает [accelerator](../../../parallel/amp/reference/accelerator-class.md) для объекта [accelerator_view](../Topic/accelerator_view%20Class.md) объекта.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  `accelerator` Для объекта `accelerator_view` объекта.  
  
##  <a name="a-nameacceleratorviewgetisautoselectionmethoda-acceleratorviewgetisautoselection-method"></a><a name="accelerator_view__get_is_auto_selection_method"></a>  Метод accelerator_view::get_is_auto_selection  
 Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при передаче accelerator_view [parallel_for_each](../Topic/concurrency%20namespace%20functions.md#parallel_for_each).  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если среда выполнения автоматически выбирает соответствующий сочетаний клавиш; в противном случае — `false`.  
  
##  <a name="a-nameacceleratorviewgetisdebugmethoda-acceleratorviewgetisdebug-method"></a><a name="accelerator_view__get_is_debug_method"></a>  Метод accelerator_view::get_is_debug  
 Возвращает логическое значение, указывающее, является ли [accelerator_view](../Topic/accelerator_view%20Class.md) объект имеет уровень ОТЛАДКИ расширенные отчеты об ошибках.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень ОТЛАДКИ расширенные отчеты об ошибках.  
  
##  <a name="a-nameacceleratorviewgetqueuingmodemethoda-acceleratorviewgetqueuingmode-method"></a><a name="accelerator_view__get_queuing_mode_method"></a>  Метод accelerator_view::get_queuing_mode  
 Возвращает режим постановки в очередь для [accelerator_view](../Topic/accelerator_view%20Class.md) объекта.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Режим постановки в очередь для `accelerator_view` объекта.  
  
##  <a name="a-nameacceleratorviewgetversionmethoda-acceleratorviewgetversion-method"></a><a name="accelerator_view__get_version_method"></a>  Метод accelerator_view::get_version  
 Возвращает версию [accelerator_view](../Topic/accelerator_view%20Class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия `accelerator_view`.  
  
##  <a name="a-nameacceleratorviewisautoselectiondatamembera-acceleratorviewisautoselection-data-member"></a><a name="accelerator_view__is_auto_selection_data_member"></a>  элемент данных accelerator_view::is_auto_selection  
 Возвращает логическое значение, указывающее ли среда выполнения автоматически выбирает соответствующий ускоритель при передаче accelerator_view [parallel_for_each](concurrency%20namespace%20functions.md#parallel_for_each).  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="a-nameacceleratorviewisdebugdatamembera-acceleratorviewisdebug-data-member"></a><a name="accelerator_view__is_debug_data_member"></a>  элемент данных accelerator_view::is_debug  
 Возвращает логическое значение, указывающее, является ли [accelerator_view](../Topic/accelerator_view%20Class.md) объект имеет уровень ОТЛАДКИ расширенные отчеты об ошибках.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorviewoperatorneqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_neq_operator"></a>  accelerator_view::operator! =-оператор  
 Сравнивает этот [accelerator_view](../Topic/accelerator_view%20Class.md) объект с другим и возвращает `false` если они совпадают; в противном случае — возвращает `true`.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
  `accelerator_view` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `false`, если объекты совпадают; в противном случае — значение `true`.  
  
##  <a name="a-nameacceleratorviewoperatoreqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_operator"></a>  accelerator_view::operator =-оператор  
 Копирует содержимое указанного [accelerator_view](../Topic/accelerator_view%20Class.md) объекта в другой.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
  `accelerator_view` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на измененный `accelerator_view` объекта.  
  
##  <a name="a-nameacceleratorviewoperatoreqeqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_eq_operator"></a>  accelerator_view::operator ==-оператор  
 Сравнивает этот [accelerator_view](../Topic/accelerator_view%20Class.md) объект с другим и возвращает `true` если они совпадают; в противном случае — возвращает `false`.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
  `accelerator_view` Объект, сравниваемый с данным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объекты совпадают; в противном случае — значение `false`.  
  
##  <a name="a-nameacceleratorviewqueuingmodedatamembera-acceleratorviewqueuingmode-data-member"></a><a name="accelerator_view__queuing_mode_data_member"></a>  элемент данных accelerator_view::queuing_mode  
 Получает режим постановки в очередь для [accelerator_view](../Topic/accelerator_view%20Class.md) объекта.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="a-nameacceleratorviewversiondatamembera-acceleratorviewversion-data-member"></a><a name="accelerator_view__version_data_member"></a>  элемент данных accelerator_view::Version  
 Возвращает версию [accelerator_view](../Topic/accelerator_view%20Class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewwaitmethoda-acceleratorviewwait-method"></a><a name="accelerator_view__wait_method"></a>  Метод accelerator_view::wait  
 Ожидания для всех команд, переданных [accelerator_view](../Topic/accelerator_view%20Class.md) завершения.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `void`.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
