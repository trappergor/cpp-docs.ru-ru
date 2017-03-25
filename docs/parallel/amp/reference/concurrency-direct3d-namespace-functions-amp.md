---
title: "Пространство имен Concurrency::Direct3D функции (AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::direct3d::abs
- amp/Concurrency::direct3d::countbits
- amp/Concurrency::direct3d::create_accelerator_view
- amp/Concurrency::direct3d::d3d_access_lock
- amp/Concurrency::direct3d::d3d_access_unlock
- amp/Concurrency::direct3d::firstbithigh
- amp/Concurrency::direct3d::get_buffer
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
dev_langs: C++
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: ad00006c9ab4f25887cf28ed5b977551c35bda9e
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Пространство имен Concurrency::Direct3D функции (AMP)
||||  
|-|-|-|  
|[abs](#abs)|[Скоба](#clamp)|[countbits](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|||
|[d3d_access_lock](#d3d_access_lock)|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|  
|[firstbithigh](#firstbithigh)|[firstbitlow](#firstbitlow)|[get_buffer](#get_buffer)|  
|[iMax](#imax)|[imin](#imin)|[is_timeout_disabled](#is_timeout_disabled)|  
|[MAD](#mad)|[make_array](#make_array)|[шум](#noise)|  
|[радианы](#radians)|[rcp](#rcp)|[reversebits](#reversebits)|  
|[перегрузке](#saturate)|[вход](#sign)|[smoothstep](#smoothstep)|  
|[Шаг](#step)|[UMAX](#umax)|[umin](#umin)|  

## <a name="requirements"></a>Требования
**Заголовок:** amp.h **пространство имен:** параллелизма
  
##  <a name="abs"></a>  abs  
 Возвращает абсолютное значение аргумента  
  
```  
inline int abs(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает абсолютное значение аргумента.  
  
##  <a name="clamp"></a>Скоба  
 Вычисляет значение первого указанного аргумента ограниченный диапазон, определяемый указанным второй и третий аргументы.  
  
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
 `_X`  
 Значение, чтобы быть ограниченными  
  
 `_Min`  
 Нижняя граница диапазона отсечение.  
  
 `_Max`  
 Верхняя граница диапазона отсечение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение ограниченными `_X`.  
  
##  <a name="countbits"></a>countbits  
 Подсчитывает количество набор битов в _X  
  
```  
inline unsigned int countbits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение без знака  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество набор битов в _X  

## <a name="create_accelerator_view"></a>create_accelerator_view  
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
 `_Accelerator`  
 Сочетания клавиш, на которой будет создаваться новый accelerator_view.  
  
 `_D3D_device`  
 Указатель на интерфейс устройства Direct3D.  
  
 `_Disable_timeout`  
 Логический параметр, который указывает, нужно ли отключить время ожидания для только что созданный accelerator_view. Это соответствует флагу D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT для создания устройства Direct3D и используется для указания, если операционная система должна позволять рабочих нагрузок, которые принимают более 2 секунд на выполнение без сброса устройства в Windows механизмом обнаружения и механизм восстановления. Рекомендуется использовать этот флаг, если требуется выполнить задачи много времени на accelerator_view.  
  
 `_Qmode`  
 [Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) для только что созданный accelerator_view. Этот параметр имеет значение по умолчанию `queuing_mode_automatic`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `accelerator_view` Объект, созданный из переданного интерфейс устройства Direct3D.  
  
## <a name="remarks"></a>Примечания  
 Эта функция создает новую `accelerator_view` объекта из существующего указателя на интерфейс устройства Direct3D. Если успешного вызова функции параметра счетчик ссылок увеличивается с помощью параметра `AddRef` вызов интерфейса. Можно безопасно освободить объект, если он больше не требуется в коде DirectX. При сбое вызова метода [runtime_exception](runtime-exception-class.md) возникает исключение.  
  
 `accelerator_view` Объект, создаваемый с помощью этой функции является потокобезопасным. Необходимо синхронизировать совместное использование `accelerator_view` объекта. Несинхронизированные параллельного использования `accelerator_view` объекта и необработанные интерфейса ID3D11Device приводит к неопределенному поведению.  
  
 Среда выполнения C++ AMP предоставляет подробные сведения об ошибке в режиме отладки с помощью слоя D3D отладки при использовании `D3D11_CREATE_DEVICE_DEBUG` флаг.  
  
  
##  <a name="d3d_access_lock"></a>d3d_access_lock  
 Получить блокировку для безопасного выполнения операций D3D ресурсов, совместно с accelerator_view accelerator_view. Accelerator_view и все ресурсы C++ AMP, связанные с этой accelerator_view внутренне принять эту блокировку при выполнении операций и блокируются на время другой поток владеет блокировкой доступа D3D. Эта блокировка является нерекурсивного: это неопределенное поведение, необходимо вызвать эту функцию из потока, который уже удерживает блокировку. Это поведение не определено для выполнения операций над accelerator_view или любого контейнера данных, связанного с accelerator_view из потока, который удерживает блокировку доступа D3D. См. также scoped_d3d_access_lock класс стиля RAII блокировки на уровне области доступа D3D.  
  
```  
void __cdecl d3d_access_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Accelerator_view блокировки.  
  
##  <a name="d3d_access_try_lock"></a>d3d_access_try_lock  
 Попытка получить блокировку доступа D3D accelerator_view без блокировки.  
  
```  
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Accelerator_view блокировки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 значение true, если блокировка была получена, или false, если она в настоящее время удерживается другим потоком.  
  
##  <a name="d3d_access_unlock"></a>d3d_access_unlock  
 Снять блокировку доступа D3D данного accelerator_view. Если вызывающий поток не удерживает блокировку accelerator_view результаты не определены.  
  
```  
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Accelerator_view, для которого выполняется снятия блокировки.  
  
##  <a name="firstbithigh"></a>firstbithigh  
 Возвращает положение первого значащего разряда в _X, начиная с старший бит и перехода к бит низкого порядка.  
  
```  
inline int firstbithigh(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расположение первый установленный бит  
  
##  <a name="firstbitlow"></a>firstbitlow  
 Возвращает положение первого значащего разряда в _X, начиная с бит низкого порядка и работает над старший бит.  
  
```  
inline int firstbitlow(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает расположение первый установленный бит  
  
##  <a name="get_buffer"></a>get_buffer  
 Получите интерфейс Direct3D буфера, базовый в указанный массив.  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;  
```  
  
### <a name="parameters"></a>Параметры  
 `value_type`  
 Тип элементов в массиве.  
  
 `_Rank`  
 Ранг массива.  
  
 `_Array`  
 Массив accelerator_view Direct3D, для которого возвращается базовый интерфейс буфера Direct3D.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель интерфейса IUnknown, соответствующий базовый массив буфера Direct3D.  
  
##  <a name="imax"></a>iMax  
 Определите максимальное числовое значение аргументов  
  
```  
inline int imax(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
 `_Y`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает максимальное значение числового аргументов  
  
##  <a name="imin"></a>imin  
 Определите минимальное числовое значение аргументов  
  
```  
inline int imin(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
 `_Y`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минимальное значение числового аргументов  
  
##  <a name="is_timeout_disabled"></a>is_timeout_disabled  
 Возвращает указатель логического типа, указывающее, отключено ли время ожидания для указанного accelerator_view. Это соответствует флагу D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT для создания устройства Direct3D.  
  
```  
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```  
  
### <a name="parameters"></a>Параметры  
 `_Accelerator_view`  
 Объект запроса accelerator_view, для которого время ожидания в отключенном состоянии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логический флаг, указывающее, отключено ли время ожидания для указанного accelerator_view.  
  
##  <a name="mad"></a>MAD  
 Вычисляет произведение заданного аргумента, первый и второй, а затем добавляет указанный третий аргумент.  
  
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
 `_X`  
 Первый указанный аргумент.  
  
 `_Y`  
 Второй аргумент, указанный.  
  
 `_Z`  
 Третий аргумент указанного.  
  
### <a name="return-value"></a>Возвращаемое значение  
 The result of `_X` * `_Y` + `_Z`.  
  
##  <a name="make_array"></a>make_array  
 Создайте массив из указателя на интерфейс Direct3D буфера.  
  
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
 `value_type`  
 Тип элемента массива должен быть создан.  
  
 `_Rank`  
 Ранг массива должен быть создан.  
  
 `_Extent`  
 Экстент, описывающий форму статистическое выражение массива.  
  
 `_Rv`  
 Представление D3D сочетаний клавиш, на которой будет создаваться массива.  
  
 `_D3D_buffer`  
 Указатель на интерфейс IUnknown для создания массива из буфера D3D.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Массив, созданный с помощью предоставленного буфера Direct3D.  
  
##  <a name="noise"></a>шум  
 Создает случайное значение с помощью алгоритма шума Перлина  
  
```  
inline float noise(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, из которой создается шума Перлина  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение шума Перлина в диапазоне от -1 до 1  
  
##  <a name="radians"></a>радианы  
 Преобразует _X из градусов в радианы  
  
```  
inline float radians(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X преобразуется из градусов в радианы  
  
##  <a name="rcp"></a>rcp  
 Вычисляет обратное указанного аргумента с помощью быстрой аппроксимации.  
  
```  
inline float rcp(float _X) restrict(amp);

 
inline double rcp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение, для которого нужно вычислить обратное.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратное указанный аргумент.  
  
##  <a name="reversebits"></a>reversebits  
 Изменяет порядок битов _X  
  
```  
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение без знака  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение с порядком бит в _X в обратном порядке  
  
##  <a name="saturate"></a>перегрузке  
 Фиксирует _X в диапазоне от 0 до 1  
  
```  
inline float saturate(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X сжимается в диапазоне от 0 до 1  
  
##  <a name="sign"></a>вход  
 Определяет знак заданного аргумента.  
  
```  
inline int sign(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Знак аргумента.  
  
##  <a name="smoothstep"></a>smoothstep  
 Возвращает smooth Hermite интерполяцию между 0 и 1, если _X находится в диапазоне [_Min, _Max].  
  
```  
inline float smoothstep(
    float _Min,  
    float _Max,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Min`  
 Значение с плавающей запятой  
  
 `_Max`  
 Значение с плавающей запятой  
  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0, если _X меньше, чем _Min; 1, если _X больше, чем _Max; в противном случае — значение между 0 и 1, если _X находится в диапазоне [_Min, _Max]  
  
##  <a name="step"></a>Шаг  
 Сравнивает два значения и возвращает 0 или 1, в зависимости от того, какое значение больше.  
  
```  
inline float step(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Y`  
 Значение с плавающей запятой  
  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает 1, если _X больше или равно _Y; в противном случае — 0.  
  
##  <a name="umax"></a>UMAX  
 Определите максимальное числовое значение аргументов  
  
```  
inline unsigned int umax(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
 `_Y`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает максимальное значение числового аргументов  
  
##  <a name="umin"></a>umin  
 Определите минимальное числовое значение аргументов  
  
```  
inline unsigned int umin(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
 `_Y`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минимальное значение числового аргументов  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::direct3d](concurrency-direct3d-namespace.md)

