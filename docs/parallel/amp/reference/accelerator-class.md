---
title: Класс accelerator
ms.date: 11/04/2016
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
helpviewer_keywords:
- accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
ms.openlocfilehash: 72a570ab28696730f835c42748a6ea12b865ca55
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855926"
---
# <a name="accelerator-class"></a>Класс accelerator

Ускоритель — это аппаратная возможность, оптимизированная для параллельных вычислений с данными. Ускорителем может быть устройство, подключенное к шине PCIe (например, GPU), или расширенный набор инструкций на основном ЦП.

## <a name="syntax"></a>Синтаксис

```cpp
class accelerator;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Конструктор ускорителя](#ctor)|Инициализирует новый экземпляр класса `accelerator`.|
|[~ Деструктор](#ctor)|Уничтожает объект `accelerator`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[create_view](#create_view)|Создает и возвращает объект `accelerator_view` для этого ускорителя.|
|[get_all](#get_all)|Возвращает вектор объектов `accelerator`, которые представляют все доступные ускорители.|
|[get_auto_selection_view](#get_auto_selection_view)|Возвращает `accelerator_view`автоматического выбора.|
|[get_dedicated_memory](#get_dedicated_memory)|Возвращает выделенную память для `accelerator`в килобайтах.|
|[get_default_cpu_access_type](#get_default_cpu_access_type)|Возвращает [access_type](concurrency-namespace-enums-amp.md#access_type) по умолчанию для буферов, созданных для этого ускорителя.|
|[get_default_view](#get_default_view)|Возвращает объект `accelerator_view` по умолчанию, связанный с `accelerator`.|
|[get_description](#get_description)|Возвращает краткое описание устройства `accelerator`.|
|[get_device_path](#get_device_path)|Возвращает путь к устройству.|
|[get_has_display](#get_has_display)|Определяет, присоединен ли `accelerator` к отображению.|
|[get_is_debug](#get_is_debug)|Определяет, включен ли уровень отладки для `accelerator` для расширенных отчетов об ошибках.|
|[get_is_emulated](#get_is_emulated)|Определяет, эмулируется ли `accelerator`.|
|[get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|Определяет, поддерживает ли `accelerator` общую память|
|[get_supports_double_precision](#get_supports_double_precision)|Определяет, присоединен ли `accelerator` к отображению.|
|[get_supports_limited_double_precision](#get_supports_limited_double_precision)|Определяет, имеет ли `accelerator` ограниченную поддержку математических функций двойной точности.|
|[get_version](#get_version)|Возвращает версию `accelerator`.|
|[set_default](#set_default)|Возвращает путь ускорителя по умолчанию.|
|[set_default_cpu_access_type](#set_default_cpu_access_type)|Задает [ACCESS_TYPE](concurrency-namespace-enums-amp.md#access_type)ЦП по умолчанию для массивов и неявных выделений памяти, сделанных на этом `accelerator`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[operator!=](#operator_neq)|Сравнивает этот объект `accelerator` с другим и возвращает **значение false** , если они одинаковы; в противном случае возвращает **значение true**.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `accelerator` в этот объект.|
|[operator==](#operator_eq_eq)|Сравнивает этот объект `accelerator` с другим и возвращает **значение true** , если они одинаковы; в противном случае возвращает **значение false**.|

### <a name="public-data-members"></a>Открытые элементы данных

|Имя|Description|
|----------|-----------------|
|[cpu_accelerator](#cpu_accelerator)|Возвращает строковую константу для `accelerator`ЦП.|
|[dedicated_memory](#dedicated_memory)|Возвращает выделенную память для `accelerator`в килобайтах.|
|[default_accelerator](#default_accelerator)|Возвращает строковую константу для `accelerator`по умолчанию.|
|[default_cpu_access_type](#default_cpu_access_type)|Возвращает или задает [ACCESS_TYPE](concurrency-namespace-enums-amp.md#access_type)ЦП по умолчанию для массивов и неявных выделений памяти, сделанных на этом `accelerator`.|
|[default_view](#default_view)|Возвращает объект `accelerator_view` по умолчанию, связанный с `accelerator`.|
|[Описание](#description)|Возвращает краткое описание устройства `accelerator`.|
|[device_path](#device_path)|Возвращает путь к устройству.|
|[direct3d_ref](#direct3d_ref)|Возвращает строковую константу для ссылки Direct3D `accelerator`.|
|[direct3d_warp](#direct3d_warp)|Возвращает строковую константу для объекта `accelerator`, который можно использовать для исполнения C++ кода amp на многоядерных ЦП, использующих расширения Streaming SIMD (SSE).|
|[has_display](#has_display)|Возвращает логическое значение, указывающее, присоединен ли `accelerator` к отображению.|
|[is_debug](#is_debug)|Указывает, включен ли уровень отладки для `accelerator` для расширенных отчетов об ошибках.|
|[is_emulated](#is_emulated)|Указывает, эмулируется ли `accelerator`.|
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|Указывает, поддерживает ли `accelerator` общую память.|
|[supports_double_precision](#supports_double_precision)|Указывает, поддерживает ли сочетание клавиш двойной точности.|
|[supports_limited_double_precision](#supports_limited_double_precision)|Указывает, имеет ли сочетание клавиш ограниченную поддержку математических функций двойной точности.|
|[version](#version)|Получает версию объекта `accelerator`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`accelerator`

## <a name="remarks"></a>Remarks

Ускоритель — это аппаратная возможность, оптимизированная для параллельных вычислений с данными. Ускоритель часто является дискретным графическим процессором, но он также может быть виртуальной сущностью на стороне узла, такой как устройство DirectX REF, деформации (устройство со стороны процессора, которое ускоряется с помощью инструкций SSE) или самого процессора.

Чтобы создать объект `accelerator`, можно перечислить доступные устройства или получить устройство по умолчанию, эталонное устройство или устройство деформации.

## <a name="requirements"></a>Требования

**Заголовок:** ампрт. h

**Пространство имен** : Concurrency

## <a name="dtor"></a></a> ~ Accelerator

Уничтожает объект `accelerator`.

```cpp
~accelerator();
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="ctor"></a>Accelerator

Инициализирует новый экземпляр [класса ускорителя](accelerator-class.md).

```cpp
accelerator();

explicit accelerator(const std::wstring& _Device_path);

accelerator(const accelerator& _Other);
```

### <a name="parameters"></a>Параметры

*_Device_path*<br/>
Путь физического устройства.

*_Other*<br/>
Копируемый ускоритель.

## <a name="cpu_accelerator"></a>cpu_accelerator

Возвращает строковую константу для ускорителя ЦП.

```cpp
static const wchar_t cpu_accelerator[];
```

## <a name="create_view"></a>create_view

Создает и возвращает объект `accelerator_view` для этого ускорителя, используя указанный режим очереди. Если режим очереди не указан, новый `accelerator_view` использует режим очереди [queuing_mode:: immediate](concurrency-namespace-enums-amp.md#queuing_mode) .

```cpp
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>Параметры

*кмоде*<br/>
Режим очереди.

### <a name="return-value"></a>Возвращаемое значение

Новый объект `accelerator_view` в этом ускорителе с использованием указанного режима очереди.

## <a name="dedicated_memory"></a>dedicated_memory

Возвращает выделенную память для `accelerator`в килобайтах.

```cpp
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;
```

## <a name="default_accelerator"></a>default_accelerator

Возвращает строковую константу для `accelerator`по умолчанию.

```cpp
static const wchar_t default_accelerator[];
```

## <a name="default_cpu_access_type"></a>default_cpu_access_type

[Access_type](concurrency-namespace-enums-amp.md#access_type)ЦП по умолчанию для массивов и неявных выделений памяти, сделанных на этом `accelerator`.

```cpp
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;
```

## <a name="default_view"></a>default_view

Возвращает представление ускорителя по умолчанию, связанное с `accelerator`.

```cpp
__declspec(property(get= get_default_view)) accelerator_view default_view;
```

## <a name="description"></a>nописание

Возвращает краткое описание устройства `accelerator`.

```cpp
__declspec(property(get= get_description)) std::wstring description;
```

## <a name="device_path"></a>device_path

Возвращает путь ускорителя. Путь уникален в системе.

```cpp
__declspec(property(get= get_device_path)) std::wstring device_path;
```

## <a name="direct3d_ref"></a>direct3d_ref

Возвращает строковую константу для Справочника по Direct3D.

```cpp
static const wchar_t direct3d_ref[];
```

## <a name="direct3d_warp"></a>direct3d_warp

Возвращает строковую константу для объекта `accelerator`, который можно использовать для исполнения кода C++ amp на многоядерных ЦП с помощью расширений Streaming SIMD (SSE).

```cpp
static const wchar_t direct3d_warp[];
```

## <a name="get_all"></a>get_all

Возвращает вектор объектов `accelerator`, которые представляют все доступные ускорители.

```cpp
static inline std::vector<accelerator> get_all();
```

### <a name="return-value"></a>Возвращаемое значение

Вектор доступных ускорителей

## <a name="get_auto_selection_view"></a>get_auto_selection_view

Возвращает accelerator_view автоматического выбора, которое при указании в качестве целевого объекта parallel_for_each приводит к выбору целевого accelerator_view для выполнения parallel_for_eachого ядра автоматически в среде выполнения. Для всех других целей accelerator_view, возвращаемые этим методом, совпадают с accelerator_view по умолчанию ускорителя по умолчанию.

```cpp
static accelerator_view __cdecl get_auto_selection_view();
```

### <a name="return-value"></a>Возвращаемое значение

Accelerator_view автоматического выбора.

## <a name="get_dedicated_memory"></a>get_dedicated_memory

Возвращает выделенную память для `accelerator`в килобайтах.

```cpp
size_t get_dedicated_memory() const;
```

### <a name="return-value"></a>Возвращаемое значение

Выделенная память для `accelerator`в килобайтах.

## <a name="get_default_cpu_access_type"></a>get_default_cpu_access_type

Получает access_type ЦП по умолчанию для буферов, созданных для этого ускорителя

```cpp
access_type get_default_cpu_access_type() const;
```

### <a name="return-value"></a>Возвращаемое значение

Access_type ЦП по умолчанию для буферов, созданных для этого ускорителя.

## <a name="get_default_view"></a>get_default_view

Возвращает объект `accelerator_view` по умолчанию, связанный с `accelerator`.

```cpp
accelerator_view get_default_view() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `accelerator_view` по умолчанию, связанный с `accelerator`.

## <a name="get_description"></a>get_description

Возвращает краткое описание устройства `accelerator`.

```cpp
std::wstring get_description() const;
```

### <a name="return-value"></a>Возвращаемое значение

Краткое описание устройства `accelerator`.

## <a name="get_device_path"></a>get_device_path

Возвращает путь ускорителя. Путь уникален в системе.

```cpp
std::wstring get_device_path() const;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный путь к экземпляру устройства в масштабе всей системы.

## <a name="get_has_display"></a>get_has_display

Возвращает логическое значение, указывающее, может ли `accelerator` выводить данные на экран.

```cpp
bool get_has_display() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если `accelerator` может выводить данные на экран; в противном случае — **значение false**.

## <a name="get_is_debug"></a>get_is_debug

Определяет, включен ли уровень отладки для `accelerator` для расширенных отчетов об ошибках.

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если на `accelerator` включен слой отладки для расширенных отчетов об ошибках. В противном случае — **false**.

## <a name="get_is_emulated"></a>get_is_emulated

Определяет, эмулируется ли `accelerator`.

```cpp
bool get_is_emulated() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если `accelerator` эмулируется. В противном случае — **false**.

## <a name="get_supports_cpu_shared_memory"></a>get_supports_cpu_shared_memory

Возвращает логическое значение, указывающее, поддерживает ли ускоритель памяти, доступный как ускорителю, так и ЦП.

```cpp
bool get_supports_cpu_shared_memory() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если ускоритель поддерживает общую память ЦП; в противном случае — **значение false**.

## <a name="get_supports_double_precision"></a>get_supports_double_precision

Возвращает логическое значение, указывающее, поддерживает ли сочетание клавиш двойной точности, включая добавление предохранителей (FMA), деление, взаимное и приведение между **int** и **Double**

```cpp
bool get_supports_double_precision() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если ускоритель поддерживает математические вычисления с двойной точностью; в противном случае — **значение false**.

## <a name="get_supports_limited_double_precision"></a>get_supports_limited_double_precision

Возвращает логическое значение, указывающее, имеет ли сочетание клавиш ограниченную поддержку математических вычислений с двойной точностью. Если у ускорителя только ограниченная поддержка, то добавление с помощью предохранителя (FMA), деления, обратного и приведения между **int** и **Double** не поддерживается.

```cpp
bool get_supports_limited_double_precision() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если сочетание клавиш имеет ограниченную поддержку математической двойной точности; в противном случае — **значение false**.

## <a name="get_version"></a>get_version

Возвращает версию `accelerator`.

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия объекта `accelerator`.

## <a name="has_display"></a>has_display

Возвращает логическое значение, указывающее, может ли `accelerator` выводить данные на экран.

```cpp
__declspec(property(get= get_has_display)) bool has_display;
```

## <a name="is_debug"></a>is_debug

Возвращает логическое значение, указывающее, включен ли уровень отладки для `accelerator` для расширенных отчетов об ошибках.

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="is_emulated"></a>is_emulated

Возвращает логическое значение, указывающее, эмулируется ли `accelerator`.

```cpp
__declspec(property(get= get_is_emulated)) bool is_emulated;
```

## <a name="operator_neq"></a>operator! =

Сравнивает этот объект `accelerator` с другим и возвращает **значение false** , если они одинаковы; в противном случае возвращает **значение true**.

```cpp
bool operator!= (const accelerator& _Other) const;
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект `accelerator` для сравнения с данным объектом.

### <a name="return-value"></a>Возвращаемое значение

**значение false** , если два объекта `accelerator` совпадают. в противном случае — **значение true**.

## <a name="operator_eq"></a>Оператор =

Копирует содержимое указанного объекта `accelerator` в этот объект.

```cpp
accelerator& operator= (const accelerator& _Other);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект `accelerator`, из которого производится копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект `accelerator`.

## <a name="operator_eq_eq"></a>Оператор = =

Сравнивает этот объект `accelerator` с другим и возвращает **значение true** , если они одинаковы; в противном случае возвращает **значение false**.

```cpp
bool operator== (const accelerator& _Other) const;
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект `accelerator` для сравнения с данным объектом.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если другой объект `accelerator` совпадает с объектом `accelerator`; в противном случае — **значение false**.

## <a name="set_default"></a>set_default

Задает ускоритель по умолчанию, используемый для любой операции, которая неявно использует ускоритель по умолчанию. Этот метод выполняется успешно только в том случае, если выбранный по умолчанию ускоритель среды выполнения еще не использовался в операции, которая неявно использует ускоритель по умолчанию.

```cpp
static inline bool set_default(std::wstring _Path);
```

### <a name="parameters"></a>Параметры

*_Path*<br/>
Путь к сочетанию клавиш.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если вызов выполняется при установке ускорителя по умолчанию. В противном случае — **false**.

## <a name="set_default_cpu_access_type"></a>set_default_cpu_access_type

Задайте access_type ЦП по умолчанию для массивов, созданных в этом ускорителе, или для неявного выделения памяти в рамках array_views, доступного в этом ускорителе. Этот метод можно выполнить только в том случае, если default_cpu_access_type для ускорителя еще не были переопределены предыдущим вызовом этого метода, и среда выполнения, выбранная default_cpu_access_type для этого ускорителя, еще не использовалась для выделения массива или для неявное выделение памяти для доступа к array_view, доступ к которому осуществляется в этом ускорителе.

```cpp
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```

### <a name="parameters"></a>Параметры

*_Default_cpu_access_type*<br/>
Access_type ЦП по умолчанию, используемый для выделения памяти массива или array_view в этом ускорителе.

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, указывающее, был ли успешно установлен access_type ЦП по умолчанию для ускорителя.

## <a name="supports_cpu_shared_memory"></a>supports_cpu_shared_memory

Возвращает логическое значение, указывающее, поддерживает ли `accelerator` общую память.

```cpp
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;
```

## <a name="supports_double_precision"></a>supports_double_precision

Возвращает логическое значение, указывающее, поддерживает ли сочетание клавиш двойной точности.

```cpp
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;
```

## <a name="supports_limited_double_precision"></a>supports_limited_double_precision

Возвращает логическое значение, указывающее, имеет ли сочетание клавиш ограниченную поддержку математических функций с двойной точностью. Если у ускорителя только ограниченная поддержка, то добавление с помощью предохранителя (FMA), деления, взаимного и приведения между `int` и `double` не поддерживается.

```cpp
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;
```

## <a name="version"></a>Версия

Получает версию объекта `accelerator`.

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
