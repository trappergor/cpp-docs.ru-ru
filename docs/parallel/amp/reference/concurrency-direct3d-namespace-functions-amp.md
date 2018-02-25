---
title: "Пространство имен Concurrency::Direct3D функции (AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b200ce8329c10fe2257ca3ce9ca8cb61125390fc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Пространство имен Concurrency::Direct3D функции (AMP)
||||  
|-|-|-|  
|[abs](#abs)|[clamp](#clamp)|[countbits](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|||
|[d3d_access_lock](#d3d_access_lock)|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|  
|[firstbithigh](#firstbithigh)|[firstbitlow](#firstbitlow)|[get_buffer](#get_buffer)|  
|[imax](#imax)|[imin](#imin)|[is_timeout_disabled](#is_timeout_disabled)|  
|[mad](#mad)|[make_array](#make_array)|[noise](#noise)|  
|[RADIANS](#radians)|[rcp](#rcp)|[reversebits](#reversebits)|  
|[saturate](#saturate)|[sign](#sign)|[smoothstep](#smoothstep)|  
|[step](#step)|[umax](#umax)|[umin](#umin)|  

## <a name="requirements"></a>Требования
**Заголовок:** amp.h **пространство имен:** параллелизма
  
##  <a name="abs"></a>  abs  
 Возвращает абсолютное значение аргумента  
  
```  
inline int abs(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает абсолютное значение аргумента.  
  
##  <a name="clamp"></a>  CLAMP  
 Вычисляет значение первого аргумента указанного ограниченный диапазон, определяемый указанным второго и третьего аргументов.  
  
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
 Значение будет ограничениями  
  
 `_Min`  
 Нижняя граница диапазона дат, отсечение.  
  
 `_Max`  
 Верхняя граница диапазона дат, отсечение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение ограниченными `_X`.  
  
##  <a name="countbits">countbits</a>  
 Подсчитывает количество набор бит в _X  
  
```  
inline unsigned int countbits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение без знака  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество набор бит в _X  

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
 `_Accelerator`  
 Сочетания клавиш, на которой будет создаваться новый accelerator_view.  
  
 `_D3D_device`  
 Указатель на интерфейс устройства Direct3D.  
  
 `_Disable_timeout`  
 Логический параметр, указывает, отключен ли время ожидания для только что созданный accelerator_view. Это соответствует флагу D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT для создания устройства Direct3D и используется для указания, если операционная система должна позволять рабочих нагрузок, которые выполняются более 2 секунд на выполнение без сброса устройства на время ожидания Windows механизм обнаружения и восстановления. Если требуется выполнять задачи требуется много времени на accelerator_view, рекомендуется использовать этот флаг.  
  
 `_Qmode`  
 [Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) для только что созданный accelerator_view. Этот параметр имеет значение по умолчанию `queuing_mode_automatic`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `accelerator_view` Объект, созданный из переданного интерфейса устройства Direct3D.  
  
## <a name="remarks"></a>Примечания  
 Эта функция создает новую `accelerator_view` объекта из существующего указателя на интерфейс устройства Direct3D. После успешного вызова функции, с помощью параметра увеличивается счетчик ссылок параметра `AddRef` вызов метода интерфейса. Можно безопасно освободить объект, если он больше не требуется в коде DirectX. Если вызов метода завершается ошибкой, [runtime_exception](runtime-exception-class.md) возникает исключение.  
  
 `accelerator_view` , Созданный с помощью этой функции является потокобезопасным. Необходимо синхронизировать одновременного использования `accelerator_view` объекта. Одновременное использование из несинхронизированного `accelerator_view` объекта и интерфейс необработанные ID3D11Device приводит к неопределенному поведению.  
  
 Среда выполнения C++ AMP предоставляет подробные сведения об ошибке в режиме отладки с помощью уровень D3D отладки, если вы используете `D3D11_CREATE_DEVICE_DEBUG` флаг.  
  
  
##  <a name="d3d_access_lock"></a>  d3d_access_lock  
 Получить блокировку accelerator_view, чтобы безопасно выполнять операции D3D ресурсы совместно с accelerator_view. Accelerator_view и все ресурсы C++ AMP, связанные с этой accelerator_view внутренне принять эту блокировку при выполнении операций и блокируется на время другой поток владеет блокировкой доступа D3D. Эта блокировка является нерекурсивным: неопределенное поведение, необходимо вызвать эту функцию из потока, который уже удерживает эту блокировку. Это поведение может быть непредсказуемо, для выполнения операций над accelerator_view, а также любой контейнер данных, связанные с accelerator_view из потока, который удерживает блокировку доступа D3D. См. также scoped_d3d_access_lock класса стилей RAII блокировки на уровне области доступа D3D.  
  
```  
void __cdecl d3d_access_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Accelerator_view блокировки.  
  
##  <a name="d3d_access_try_lock"></a>  d3d_access_try_lock  
 Попытка получить блокировку доступа D3D accelerator_view без блокировки.  
  
```  
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Accelerator_view блокировки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 значение true, если блокировка была получена, или значение false, если она в настоящее время удерживается другим потоком.  
  
##  <a name="d3d_access_unlock"></a>  d3d_access_unlock  
 Снять блокировку доступа D3D данного accelerator_view. Если вызывающий поток не удерживает блокировку accelerator_view результаты не определены.  
  
```  
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Accelerator_view, для которого выполняется снятия блокировки.  
  
##  <a name="firstbithigh">firstbithigh</a>  
 Возвращает расположение первый набор бит _X, начиная с старший бит и перемещение по направлению к младший бит.  
  
```  
inline int firstbithigh(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расположение первый установленный бит  
  
##  <a name="firstbitlow"></a>  firstbitlow  
 Возвращает расположение первый набор бит _X, начиная с младший бит и работает над старший бит.  
  
```  
inline int firstbitlow(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает расположение Первый значащий разряд  
  
##  <a name="get_buffer"></a>  get_buffer  
 Получение интерфейса буфера Direct3D базовый в указанный массив.  
  
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
 Массив на accelerator_view Direct3D, для которого возвращается базового интерфейса буфера Direct3D.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель интерфейса IUnknown, соответствующий базовый массив буфера Direct3D.  
  
##  <a name="imax"></a>  iMax  
 Определите максимальное числовое значение аргументов  
  
```  
inline int imax(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение  
  
 `_Y`  
 Целочисленное значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает максимальное числовое значение аргументов  
  
##  <a name="imin">imin</a>  
 Определите минимальное числовое значение аргументов  
  
```  
inline int imin(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение  
  
 `_Y`  
 Целочисленное значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минимальное числовое значение аргументов  
  
##  <a name="is_timeout_disabled"></a>  is_timeout_disabled  
 Возвращает логический флаг, указывающее, запрещен ли accelerator_view указанного времени ожидания. Это соответствует флагу D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT для создания устройства Direct3D.  
  
```  
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```  
  
### <a name="parameters"></a>Параметры  
 `_Accelerator_view`  
 Accelerator_view, для которого время ожидания в отключенном состоянии объект запроса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логический флаг, указывающее, запрещен ли accelerator_view указанного времени ожидания.  
  
##  <a name="mad"></a>  MAD  
 Вычисляет произведение первого и второго заданного аргумента, а затем добавляет указанный третий аргумент.  
  
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
 Второй аргумент указан.  
  
 `_Z`  
 Третий аргумент указан.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат `_X`  *  `_Y`  +  `_Z`.  
  
##  <a name="make_array"></a>  make_array  
 Создайте массив из буфера указатель на интерфейс Direct3D.  
  
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
 Указатель интерфейса IUnknown для создания массива из буфера D3D.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Массив, созданный с помощью предоставленного буфера Direct3D.  
  
##  <a name="noise"></a>  шума  
 Создает случайное значение с помощью алгоритма шума Перлина  
  
```  
inline float noise(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, из которого будут создаваться шума Перлина  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение шума Перлина в диапазоне от -1 до 1  
  
##  <a name="radians">RADIANS</a>  
 Преобразование _X из градусов в радианы  
  
```  
inline float radians(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X преобразован из градусов в радианы  
  
##  <a name="rcp"></a>  rcp  
 Вычисляет обратное указанного аргумента с помощью быстрого приближения.  
  
```  
inline float rcp(float _X) restrict(amp);

 
inline double rcp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение, для которых нужно вычислить обратное.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратное указанного аргумента.  
  
##  <a name="reversebits"></a>  reversebits  
 Изменяет порядок биты в _X  
  
```  
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение без знака  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение с обратным в _X порядком бит  
  
##  <a name="saturate">saturate</a>  
 Фиксирует _X в диапазоне от 0 до 1  
  
```  
inline float saturate(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X с ограничениями в диапазоне от 0 до 1  
  
##  <a name="sign"></a>  Вход  
 Определяет знак заданного аргумента.  
  
```  
inline int sign(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Знак значения аргумента.  
  
##  <a name="smoothstep"></a>  smoothstep  
 Возвращает smooth интерполяции Hermite между 0 и 1, если _X находится в диапазоне [_Min, _Max].  
  
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
 Возвращает 0, если _X меньше, чем _Min; 1, если _X больше, чем _Max; в противном случае — значение в диапазоне от 0 до 1, если _X находится в диапазоне [_Min, _Max]  
  
##  <a name="step"></a>  step  
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
  
##  <a name="umax"></a>  UMAX  
 Определите максимальное числовое значение аргументов  
  
```  
inline unsigned int umax(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение  
  
 `_Y`  
 Целочисленное значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает максимальное числовое значение аргументов  
  
##  <a name="umin">umin</a>  
 Определите минимальное числовое значение аргументов  
  
```  
inline unsigned int umin(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение  
  
 `_Y`  
 Целочисленное значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минимальное числовое значение аргументов  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::direct3d](concurrency-direct3d-namespace.md)
