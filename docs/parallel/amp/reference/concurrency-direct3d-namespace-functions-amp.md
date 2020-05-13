---
title: Функции пространства имен Concurrency::direct3d (AMP)
ms.date: 08/31/2018
f1_keywords:
- amp/Concurrency::direct3d::abs
- amp/Concurrency::direct3d::countbits
- amp/Concurrency::direct3d::create_accelerator_view
- amp/Concurrency::direct3d::d3d_access_lock
- amp/Concurrency::direct3d::d3d_access_unlock
- amp/Concurrency::direct3d::firstbithigh
- amp/Concurrency::direct3d::get_buffer
- amp/Concurrency::direct3d::get_device
- amp/Concurrency::direct3d::imax
- amp/Concurrency::direct3d::is_timeout_disabled
- amp/Concurrency::direct3d::mad
- amp/Concurrency::direct3d::noise
- amp/Concurrency::direct3d::radians
- amp/Concurrency::direct3d::reversebits
- amp/Concurrency::direct3d::saturate
- amp/Concurrency::direct3d::smoothstep
- amp/Concurrency::direct3d::step
- amp/Concurrency::direct3d::umin
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
ms.openlocfilehash: e21b1f2869ab81973b341abc5371714fbf8580e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375933"
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Функции пространства имен Concurrency::direct3d (AMP)

||||
|-|-|-|
|[Abs](#abs)|[Зажим](#clamp)|[счет-биты](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|[d3d_access_lock](#d3d_access_lock)||
|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|[firstbithigh](#firstbithigh)|
|[firstbitlow](#firstbitlow)|[get_buffer](#get_buffer)|[get_device](#get_device)|
|[iMax](#imax)|[имин](#imin)|[is_timeout_disabled](#is_timeout_disabled)|
|[Сумасшедший](#mad)|[make_array](#make_array)|[Шум](#noise)|
|[Радианах](#radians)|[rcp](#rcp)|[реверсбиты](#reversebits)|
|[Насытить](#saturate)|[Знак](#sign)|[гладкий шаг](#smoothstep)|
|[Шаг](#step)|[Umax](#umax)|[Umin](#umin)|

## <a name="requirements"></a>Требования

**Заголовок:** amp.h **Namespace:** Параллелизм

## <a name="abs"></a><a name="abs"></a>Abs

Возвращает абсолютное значение аргумента

```cpp
inline int abs(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает абсолютное значение аргумента.

## <a name="clamp"></a><a name="clamp"></a>Зажим

Вычисляет значение первого указанного аргумента, зажатого к диапазону, определенному вторым и третьим указанным аргументами.

```cpp
inline float clamp(
    float _X,
    float _Min,
    float _Max) restrict(amp);

inline int clamp(
    int _X,
    int _Min,
    int _Max) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение, подавленное

*_Min*<br/>
Нижняя граница диапазона зажима.

*_Max*<br/>
Верхняя граница зажима.

### <a name="return-value"></a>Возвращаемое значение

Зажатое `_X`значение .

## <a name="countbits"></a><a name="countbits"></a>счет-биты

Подсчитывает количество наборбитов в _X

```cpp
inline unsigned int countbits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Неподписанное значение ажероприра

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество набор битов в _X

## <a name="create_accelerator_view"></a><a name="create_accelerator_view"></a>create_accelerator_view

Создает [accelerator_view](accelerator-view-class.md) объект от указателя до интерфейса устройства Direct3D.

## <a name="syntax"></a>Синтаксис

```cpp
accelerator_view create_accelerator_view(
    IUnknown * _D3D_device
    queuing_mode _Qmode = queuing_mode_automatic);

accelerator_view create_accelerator_view(
    accelerator& _Accelerator,
    bool _Disable_timeout
    queuing_mode _Qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>Параметры

*_Accelerator*<br/>
Ускоритель, на котором будет создан новый accelerator_view.

*_D3D_device*<br/>
Указатель на интерфейс устройства Direct3D.

*_Disable_timeout*<br/>
Параметр Boolean, который определяет, следует ли отключать тайм-аут для вновь созданных accelerator_view. Это соответствует D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT флагу для создания устройства Direct3D и используется для указания, должна ли операционная система позволить выполнять рабочие нагрузки, которые занимают более 2 секунд, не сбросив устройство на механизм обнаружения и восстановления тайм-аута Windows. Использование этого флага рекомендуется, если вам нужно выполнять трудоемкие задачи на accelerator_view.

*_Qmode*<br/>
Queuing_mode [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) будет использоваться для вновь созданных accelerator_view. Этот параметр имеет `queuing_mode_automatic`значение по умолчанию.

## <a name="return-value"></a>Возвращаемое значение

Объект, `accelerator_view` созданный из интерфейса устройства Direct3D.

## <a name="remarks"></a>Remarks

Эта функция создает `accelerator_view` новый объект от существующего указателя до интерфейса устройства Direct3D. Если вызов функции удается, количество ссылок параметра приращается с помощью `AddRef` вызова к интерфейсу. Вы можете безопасно освободить объект, когда он больше не требуется в коде DirectX. Если вызов метода не удается, [runtime_exception](runtime-exception-class.md) брошен.

Объект, созданный `accelerator_view` с помощью этой функции, является безопасным потоком. Необходимо синхронизировать одновременное `accelerator_view` использование объекта. Несинхронизированное одновременное использование `accelerator_view` объекта и необработанного интерфейса ID3D11Device вызывает неопределенное поведение.

Время выполнения AMP предоставляет подробную информацию об ошибках в режиме отладки, используя слой D3D Debug при использовании флага. `D3D11_CREATE_DEVICE_DEBUG`

## <a name="d3d_access_lock"></a><a name="d3d_access_lock"></a>d3d_access_lock

Приобретите блокировку accelerator_view с целью безопасного выполнения D3D-операций на ресурсах, совместно с accelerator_view. Accelerator_view и все ресурсы АМП, связанные с этим accelerator_view внутренне забирают этот замок при выполнении операций и будут блокировать, в то время как другой поток удерживает блокировку доступа D3D. Этот замок не рекурсивный: вызов этой функции из потока, который уже удерживает блокировку, неопределенен. Неопределенный тип поведения выполняет операции на accelerator_view или любой контейнер данных, связанный с accelerator_view из потока, вмещающего блокировку доступа D3D. Смотрите также scoped_d3d_access_lock, класс RAII-стиля для блокировки доступа D3D на основе области.

```cpp
void __cdecl d3d_access_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Accelerator_view зафиксировать.

## <a name="d3d_access_try_lock"></a><a name="d3d_access_try_lock"></a>d3d_access_try_lock

Попытка приобрести блокировку доступа D3D на accelerator_view без блокировки.

```cpp
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Accelerator_view зафиксировать.

### <a name="return-value"></a>Возвращаемое значение

верно, если блокировка была приобретена, или ложная, если она в настоящее время удерживается другим потоком.

## <a name="d3d_access_unlock"></a><a name="d3d_access_unlock"></a>d3d_access_unlock

Освободите блокировку доступа D3D на данном accelerator_view. Если поток вызова не удерживает блокировку на accelerator_view результаты не определены.

```cpp
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
В accelerator_view, для которого блокировка должна быть освобождена.

## <a name="firstbithigh"></a><a name="firstbithigh"></a>firstbithigh

Получает расположение первого бита в _X, начиная с бита самого высокого порядка и двигаясь к биту с самым низким уровнем порядка.

```cpp
inline int firstbithigh(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Расположение первого набора бит

## <a name="firstbitlow"></a><a name="firstbitlow"></a>firstbitlow

Получает расположение первого бита в _X, начиная с бита с самым низким заказом и работая в направлении бита самого высокого порядка.

```cpp
inline int firstbitlow(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает местоположение первого бита набора

## <a name="get_buffer"></a><a name="get_buffer"></a>get_buffer

Получите интерфейс буфера Direct3D, лежащий в основе указанного массива.

```cpp
template<
    typename value_type,
    int _Rank
>
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;
```

### <a name="parameters"></a>Параметры

*Value_type*<br/>
Тип элементов в массиве.

*_Rank*<br/>
Ранг массива.

*_Array*<br/>
Массив на accelerator_view Direct3D, для которого возвращается базовый интерфейс буфера Direct3D.

### <a name="return-value"></a>Возвращаемое значение

Указатель интерфейса IUnknown, соответствующий буферу Direct3D, лежащему в основе массива.

## <a name="a-nameget_device-get_device"></a><a name="get_device">get_device

Получите интерфейс устройства D3D, лежащий в основе accelerator_view.

```cpp
IUnknown* get_device(const accelerator_view Av);
```

### <a name="parameters"></a>Параметры

*Av*<br/>
D3D accelerator_view для которого возвращается базовый интерфейс устройства D3D.

### <a name="return-value"></a>Возвращаемое значение

Указатель `IUnknown` интерфейса устройства D3D, лежащего в основе accelerator_view.

## <a name="imax"></a><a name="imax"></a>Imax

Определение максимального численного значения аргументов

```cpp
inline int imax(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

*_y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Вернуть максимальное числовое значение аргументов

## <a name="imin"></a><a name="imin"></a>имин

Определение минимального численного значения аргументов

```cpp
inline int imin(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

*_y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Вернуть минимальное числовое значение аргументов

## <a name="is_timeout_disabled"></a><a name="is_timeout_disabled"></a>is_timeout_disabled

Возвращает флаг boolean с указанием, если тайм-аут отключен для указанного accelerator_view. Это соответствует D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT флагу для создания устройства Direct3D.

```cpp
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```

### <a name="parameters"></a>Параметры

*_Accelerator_view*<br/>
В accelerator_view, для которых параметр тайм-аута отключен.

### <a name="return-value"></a>Возвращаемое значение

Флаг boolean, указывающий, отключен ли тайм-аут для указанного accelerator_view.

## <a name="mad"></a><a name="mad"></a>Сумасшедший

Вычисляет продукт первого и второго указанного аргумента, затем добавляет третий указанный аргумент.

```cpp
inline float mad(
    float _X,
    float _Y,
    float _Z) restrict(amp);

inline double mad(
    double _X,
    double _Y,
    double _Z) restrict(amp);

inline int mad(
    int _X,
    int _Y,
    int _Z) restrict(amp);

inline unsigned int mad(
    unsigned int _X,
    unsigned int _Y,
    unsigned int _Z) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Первый указанный аргумент.

*_y*<br/>
Второй указанный аргумент.

*_Z*<br/>
Третий указанный аргумент.

### <a name="return-value"></a>Возвращаемое значение

`_X` \* Результат `_Y`  + . `_Z`

## <a name="make_array"></a><a name="make_array"></a>make_array

Создайте массив из указателя интерфейса буфера Direct3D.

```cpp
template<
    typename value_type,
    int _Rank
>
array<value_type, _Rank> make_array(
    const extent<_Rank>& _Extent,
    const Concurrency::accelerator_view& _Rv,
    IUnknown* _D3D_buffer)  ;
```

### <a name="parameters"></a>Параметры

*Value_type*<br/>
Тип элемента создаваемого массива.

*_Rank*<br/>
Ранг массива, который будет создан.

*_Extent*<br/>
Степень, описывающая форму агрегата массива.

*_Rv*<br/>
Представление ускорителя D3D, на котором должен быть создан массив.

*_D3D_buffer*<br/>
IUnknown интерфейс указатель буфера D3D для создания массива из.

### <a name="return-value"></a>Возвращаемое значение

Массив, созданный с помощью предоставленного буфера Direct3D.

## <a name="noise"></a><a name="noise"></a>Шум

Генерирует случайное значение с помощью алгоритма шума Perlin

```cpp
inline float noise(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение плавающей точки, из которого можно создавать шум Perlin

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение шума Perlin в диапазоне от -1 до 1

## <a name="radians"></a><a name="radians"></a>Радианах

Преобразует _X из степеней в радианов

```cpp
inline float radians(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X преобразованы из степеней в радианов

## <a name="rcp"></a><a name="rcp"></a>Rcp

Вычисляет взаимный указанный аргумент с помощью быстрого приближения.

```cpp
inline float rcp(float _X) restrict(amp);

inline double rcp(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение, для которого вычислять взаимное.

### <a name="return-value"></a>Возвращаемое значение

Взаимный указанный аргумент.

## <a name="reversebits"></a><a name="reversebits"></a>реверсбиты

Обратный порядок битов в _X

```cpp
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Неподписанное значение ажероприра

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение с ордером бита, отмененным в _X

## <a name="saturate"></a><a name="saturate"></a>Насытить

Зажимы _X в пределах от 0 до 1

```cpp
inline float saturate(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X зажат в пределах 0 к 1

## <a name="sign"></a><a name="sign"></a>Знак

Определяет признак указанного аргумента.

```cpp
inline int sign(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Признак аргумента.

## <a name="smoothstep"></a><a name="smoothstep"></a>гладкий шаг

Возвращает гладкую интерполяцию отherситов между 0 и 1, если _X находится в диапазоне «_Min, _Max».

```cpp
inline float smoothstep(
    float _Min,
    float _Max,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Min*<br/>
Значение с плавающей запятой

*_Max*<br/>
Значение с плавающей запятой

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если _X меньше _Min; 1, если _X больше, чем _Max; в противном случае значение от 0 до 1, если _X находится в диапазоне «_Min, _Max»

## <a name="step"></a><a name="step"></a>Шаг

Сравнивает два значения, возвращающие 0 или 1 на основе того значения, которое больше

```cpp
inline float step(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_y*<br/>
Значение с плавающей запятой

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 1, если _X больше или равен _Y; в противном случае, 0

## <a name="umax"></a><a name="umax"></a>Umax

Определение максимального численного значения аргументов

```cpp
inline unsigned int umax(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

*_y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Вернуть максимальное числовое значение аргументов

## <a name="umin"></a><a name="umin"></a>Umin

Определение минимального численного значения аргументов

```cpp
inline unsigned int umin(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

*_y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Вернуть минимальное числовое значение аргументов

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency::direct3d](concurrency-direct3d-namespace.md)
