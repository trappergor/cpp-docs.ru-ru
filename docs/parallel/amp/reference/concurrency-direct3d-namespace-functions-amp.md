---
title: Функции пространства имен Concurrency::Direct3D (AMP)
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
ms.openlocfilehash: 0a2977faf094aafb6290063e39e062ffaeaaec81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405590"
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Функции пространства имен Concurrency::Direct3D (AMP)

||||
|-|-|-|
|[abs](#abs)|[clamp](#clamp)|[countbits](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|[d3d_access_lock](#d3d_access_lock)||
|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|[firstbithigh](#firstbithigh)|
|[firstbitlow](#firstbitlow)|[get_buffer](#get_buffer)|[get_device](#get_device)|
|[imax](#imax)|[imin](#imin)|[is_timeout_disabled](#is_timeout_disabled)|
|[MAD](#mad)|[make_array](#make_array)|[шума](#noise)|
|[radians](#radians)|[rcp](#rcp)|[reversebits](#reversebits)|
|[saturate](#saturate)|[sign](#sign)|[smoothstep](#smoothstep)|
|[Шаг](#step)|[umax](#umax)|[umin](#umin)|

## <a name="requirements"></a>Требования

**Заголовок:** amp.h **пространство имен:** параллелизм

##  <a name="abs"></a>  abs

Возвращает абсолютное значение аргумента

```
inline int abs(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает абсолютное значение аргумента.

##  <a name="clamp"></a>  CLAMP

Вычисляет значение первого заданного аргумента, ограниченное диапазоном, определенным вторым и третьим заданными аргументами.

```
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

*_X*<br/>
Ограничиваемое значение

*_Min*<br/>
Нижняя граница граница диапазона ограничения.

*_Max*<br/>
Верхняя граница граница диапазона ограничения.

### <a name="return-value"></a>Возвращаемое значение

Ограниченное значение `_X`.

##  <a name="countbits"></a>  countbits

Подсчитывает число установленных битов в _X

```
inline unsigned int countbits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целое число без знака

### <a name="return-value"></a>Возвращаемое значение

Возвращает число установленных битов в _X

## <a name="create_accelerator_view"></a> create_accelerator_view

Создает [accelerator_view](accelerator-view-class.md) объекта из указателя на интерфейс устройства Direct3D.

## <a name="syntax"></a>Синтаксис

```
accelerator_view create_accelerator_view(
    IUnknown * _D3D_device
    queuing_mode _Qmode = queuing_mode_automatic);

accelerator_view create_accelerator_view(
    accelerator& _Accelerator,
    bool _Disable_timeout
    queuing_mode _Qmode = queuing_mode_automatic);
```

#### <a name="parameters"></a>Параметры

*_Accelerator*<br/>
Ускоритель, на которой будет создаваться новый accelerator_view.

*_D3D_device*<br/>
Указатель на интерфейс устройства Direct3D.

*_Disable_timeout*<br/>
Логический параметр, который указывает, следует ли отключить время ожидания для созданного accelerator_view. Это соответствует флагу d3d11_create_device_disable_gpu_timeout для создания устройства Direct3D и используется для указания того, если операционная система должна позволяет нагрузки, которые принимают более 2 секунд выполняться без сбросить устройство за время ожидания Windows механизм обнаружения и восстановления. Если вам нужно выполнять много времени задачи на accelerator_view, рекомендуется использовать этот флаг.

*_Qmode*<br/>
[Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) для созданного accelerator_view. Этот параметр имеет значение по умолчанию `queuing_mode_automatic`.

## <a name="return-value"></a>Возвращаемое значение

`accelerator_view` Объект, созданный из переданного интерфейса устройства Direct3D.

## <a name="remarks"></a>Примечания

Эта функция создает новую `accelerator_view` объекта из существующего указателя на интерфейс устройства Direct3D. Если вызов функции завершается успешно, счетчик ссылок параметра увеличивается посредством `AddRef` вызов к интерфейсу. Можно безопасно освободить объект, если он больше не требуется в вашем DirectX-коде. При сбое вызова метода [runtime_exception](runtime-exception-class.md) возникает исключение.

`accelerator_view` , Созданный с помощью этой функции является поточно-ориентированным. Необходимо синхронизировать параллельное использование объекта `accelerator_view` объекта. Несинхронизированное параллельное использование объекта `accelerator_view` объекта и исходного интерфейса ID3D11Device вызывает неопределенное поведение.

Среда выполнения C++ AMP предоставляет подробные сведения об ошибке в режиме отладки с помощью уровня отладки D3D при использовании `D3D11_CREATE_DEVICE_DEBUG` флаг.

##  <a name="d3d_access_lock"></a>  d3d_access_lock

Получить блокировку на accelerator_view для безопасного выполнения операций D3D на ресурсах общих с accelerator_view. Accelerator_view и все C++ AMP ресурсы, связанные с этим accelerator_view, внутренне принимают эту блокировку при выполнении операций и будут блокироваться, пока другой поток удерживает блокировку доступа D3D. Эта блокировка является нерекурсивным: Является неопределенным поведением, вызов этой функции из потока, который уже удерживает эту блокировку. Является неопределенным поведением для выполнения операций в accelerator_view или любых контейнерах данных, связанных с accelerator_view, из потока, который удерживает блокировку доступа D3D. См. также scoped_d3d_access_lock, класс стиле RAII для блокирования доступа D3D на уровне области.

```
void __cdecl d3d_access_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Accelerator_view, который требуется заблокировать.

##  <a name="d3d_access_try_lock"></a>  d3d_access_try_lock

Попытки получить блокировку доступа D3D на accelerator_view без блокировки.

```
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Accelerator_view, который требуется заблокировать.

### <a name="return-value"></a>Возвращаемое значение

значение true, если блокировка была получена, или значение false, если в данный момент удерживается другим потоком.

##  <a name="d3d_access_unlock"></a>  d3d_access_unlock

Снять блокировку доступа D3D для заданного accelerator_view. Если вызывающий поток не удерживает блокировку на accelerator_view, результаты будут неопределенными.

```
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Accelerator_view, для которого выполняется снятия блокировки.

##  <a name="firstbithigh"></a>  firstbithigh

Получает расположение первого установленного бита в _X, начиная с самого старшего бита и двигаясь к младшему биту.

```
inline int firstbithigh(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Расположение первого установленного бита

##  <a name="firstbitlow"></a>  firstbitlow

Получает расположение первого установленного бита в _X, начиная с младшего бита и двигаясь самого старшего бита.

```
inline int firstbitlow(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает расположение первого установленного бита

##  <a name="get_buffer"></a>  get_buffer

Получите интерфейс буфера Direct3D, лежащему в основе заданного массива.

```
template<
    typename value_type,
    int _Rank
>
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элементов в массиве.

*_Rank*<br/>
Ранг массива.

*_Array*<br/>
Массив на accelerator_view Direct3D, для которого возвращается базовый интерфейс буфера Direct3D.

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IUnknown, соответствующий буферу Direct3D, лежащему в основе массива.

## <a name="a-namegetdevice-getdevice"></a><a name="get_device"> get_device

Получите интерфейс устройства D3D, базовый accelerator_view.

```
IUnknown* get_device(const accelerator_view Av);
```

### <a name="parameters"></a>Параметры

*AV*<br/>
Accelerator_view D3D, для которого возвращается базовый интерфейс устройства D3D.

### <a name="return-value"></a>Возвращаемое значение

`IUnknown` Указатель на интерфейс устройства D3D базовый accelerator_view.

##  <a name="imax"></a>  imax

Определение максимального числового значения аргументов

```
inline int imax(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает максимальное числовое значение аргументов

##  <a name="imin"></a>  imin

Определение минимального числового значения аргументов

```
inline int imin(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает минимальное числовое значение аргументов

##  <a name="is_timeout_disabled"></a>  is_timeout_disabled

Возвращает логический флаг, указывающее, отключено ли время ожидания для заданного accelerator_view. Это соответствует флагу d3d11_create_device_disable_gpu_timeout для создания устройства Direct3D.

```
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```

### <a name="parameters"></a>Параметры

*_Accelerator_view*<br/>
Accelerator_view, для которого время ожидания в отключенном состоянии объект запроса.

### <a name="return-value"></a>Возвращаемое значение

Логический флаг, указывающее, отключено ли время ожидания для заданного accelerator_view.

##  <a name="mad"></a>  MAD

Вычисляет произведение первого и второго заданных аргументов, а затем добавляет третий заданный аргумент.

```
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

*_X*<br/>
Первый указанный аргумент.

*_Y*<br/>
Второй заданный аргумент.

*_Z*<br/>
Третий заданный аргумент.

### <a name="return-value"></a>Возвращаемое значение

Результат `_X` \* `_Y`  +  `_Z`.

##  <a name="make_array"></a>  make_array

Создайте массив из указателя интерфейса буфера Direct3D.

```
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

*value_type*<br/>
Тип элемента создаваемого массива.

*_Rank*<br/>
Ранг массива должен быть создан.

*_Extent*<br/>
Область памяти, которая описывает форму агрегата массива.

*_Rv*<br/>
Представление ускорителя D3D, на которой будет создаваться массива.

*_D3D_buffer*<br/>
Указатель на интерфейс IUnknown буфера D3D для создания массива.

### <a name="return-value"></a>Возвращаемое значение

Массив, созданный с помощью предоставленного буфера Direct3D.

##  <a name="noise"></a>  шума

Создает случайное значение с помощью алгоритма шума Перлина

```
inline float noise(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, из которого требуется создать шума Перлина

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение для уровня шума Перлина в диапазоне от -1 до 1

##  <a name="radians"></a>  RADIANS

Преобразовывает значение _X из градусов в радианы.

```
inline float radians(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X, преобразованное из градусов в радианы.

##  <a name="rcp"></a>  rcp

Вычисляет обратную величину заданного аргумента с помощью быстрого приближения.

```
inline float rcp(float _X) restrict(amp);

inline double rcp(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение, для которого вычисляется обратная величина.

### <a name="return-value"></a>Возвращаемое значение

Обратная величина указанного аргумента.

##  <a name="reversebits"></a>  reversebits

Изменяет порядок бит в _X на обратный

```
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целое число без знака

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение с порядком бит в _X в обратном порядке

##  <a name="saturate"></a>  saturate

Ограничивает _X в диапазоне от 0 до 1

```
inline float saturate(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X ограниченными в диапазоне от 0 до 1

##  <a name="sign"></a>  вход

Определяет знак заданного аргумента.

```
inline int sign(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Знак аргумента.

##  <a name="smoothstep"></a>  smoothstep

Возвращает гладкую Эрмитову интерполяцию между 0 и 1, если _X в диапазоне [_Min, _Max].

```
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

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если _X меньше, чем _Min; 1, если _X больше, чем _Max; в противном случае — значение от 0 до 1, если _X в диапазоне [_Min, _Max]

##  <a name="step"></a>  Шаг

Сравнивает два значения, возвращая 0 или 1, в зависимости от того, какое значение больше

```
inline float step(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Y*<br/>
Значение с плавающей запятой

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение 1, если _X не меньше _Y; в противном случае — 0

##  <a name="umax"></a>  UMAX

Определение максимального числового значения аргументов

```
inline unsigned int umax(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает максимальное числовое значение аргументов

##  <a name="umin"></a>  umin

Определение минимального числового значения аргументов

```
inline unsigned int umin(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает минимальное числовое значение аргументов

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::direct3d](concurrency-direct3d-namespace.md)
