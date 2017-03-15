---
title: "Пространство имен Concurrency::Direct3D функции (AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 46cafc3c6d6f21eaf147ef0edfeca7f2c81d64e6
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Пространство имен Concurrency::Direct3D функции (AMP)
||||  
|-|-|-|  
|[Функция ABS](#abs)|[Функция CLAMP](#clamp)|[Функция countbits](#countbits)|
|[Функция create_accelerator_view](#create_accelerator_view)|||
|[Функция d3d_access_lock](#d3d_access_lock)|[Функция d3d_access_try_lock](#d3d_access_try_lock)|[Функция d3d_access_unlock](#d3d_access_unlock)|  
|[Функция firstbithigh](#firstbithigh)|[Функция firstbitlow](#firstbitlow)|[Функция get_buffer](#get_buffer)|  
|[Функция iMax](#imax)|[Функция imin](#imin)|[Функция is_timeout_disabled](#is_timeout_disabled)|  
|[Функция MAD](#mad)|[Функция make_array](#make_array)|[Функция noise](#noise)|  
|[Функция RADIANS](#radians)|[Функция rcp](#rcp)|[Функция reversebits](#reversebits)|  
|[Функция saturate](#saturate)|[Функция Sign](#sign)|[Функция smoothstep](#smoothstep)|  
|[Функция Step](#step)|[Функция UMAX](#umax)|[Функция umin](#umin)|  
  
##  <a name="a-nameabsa--abs-function"></a><a name="abs"></a>Функция ABS  
 Возвращает абсолютное значение аргумента  
  
```  
inline int abs(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает абсолютное значение аргумента.  
  
##  <a name="a-nameclampa--clamp-function"></a><a name="clamp"></a>Функция CLAMP  
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
  
##  <a name="a-namecountbitsa--countbits-function"></a><a name="countbits"></a>Функция countbits  
 Подсчитывает количество набор битов в _X  
  
```  
inline unsigned int countbits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение без знака  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество набор битов в _X  

## <a name="a-namecreateacceleratorviewa-createacceleratorview-function"></a><a name="create_accelerator_view"></a>Функция create_accelerator_view
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
  
  
##  <a name="a-named3daccesslocka--d3daccesslock-function"></a><a name="d3d_access_lock"></a>Функция d3d_access_lock  
 Получить блокировку для безопасного выполнения операций D3D ресурсов, совместно с accelerator_view accelerator_view. Accelerator_view и все ресурсы C++ AMP, связанные с этой accelerator_view внутренне принять эту блокировку при выполнении операций и блокируются на время другой поток владеет блокировкой доступа D3D. Эта блокировка является нерекурсивного: это неопределенное поведение, необходимо вызвать эту функцию из потока, который уже удерживает блокировку. Это поведение не определено для выполнения операций над accelerator_view или любого контейнера данных, связанного с accelerator_view из потока, который удерживает блокировку доступа D3D. См. также scoped_d3d_access_lock класс стиля RAII блокировки на уровне области доступа D3D.  
  
```  
void __cdecl d3d_access_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Accelerator_view блокировки.  
  
##  <a name="a-named3daccesstrylocka--d3daccesstrylock-function"></a><a name="d3d_access_try_lock"></a>Функция d3d_access_try_lock  
 Попытка получить блокировку доступа D3D accelerator_view без блокировки.  
  
```  
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Accelerator_view блокировки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 значение true, если блокировка была получена, или false, если она в настоящее время удерживается другим потоком.  
  
##  <a name="a-named3daccessunlocka--d3daccessunlock-function"></a><a name="d3d_access_unlock"></a>Функция d3d_access_unlock  
 Снять блокировку доступа D3D данного accelerator_view. Если вызывающий поток не удерживает блокировку accelerator_view результаты не определены.  
  
```  
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Accelerator_view, для которого выполняется снятия блокировки.  
  
##  <a name="a-namefirstbithigha--firstbithigh-function"></a><a name="firstbithigh"></a>Функция firstbithigh  
 Возвращает положение первого значащего разряда в _X, начиная с старший бит и перехода к бит низкого порядка.  
  
```  
inline int firstbithigh(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расположение первый установленный бит  
  
##  <a name="a-namefirstbitlowa--firstbitlow-function"></a><a name="firstbitlow"></a>Функция firstbitlow  
 Возвращает положение первого значащего разряда в _X, начиная с бит низкого порядка и работает над старший бит.  
  
```  
inline int firstbitlow(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает расположение первый установленный бит  
  
##  <a name="a-namegetbuffera--getbuffer-function"></a><a name="get_buffer"></a>Функция get_buffer  
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
  
##  <a name="a-nameimaxa--imax-function"></a><a name="imax"></a>Функция iMax  
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
  
##  <a name="a-nameimina--imin-function"></a><a name="imin"></a>Функция imin  
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
  
##  <a name="a-nameistimeoutdisableda--istimeoutdisabled-function"></a><a name="is_timeout_disabled"></a>Функция is_timeout_disabled  
 Возвращает указатель логического типа, указывающее, отключено ли время ожидания для указанного accelerator_view. Это соответствует флагу D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT для создания устройства Direct3D.  
  
```  
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```  
  
### <a name="parameters"></a>Параметры  
 `_Accelerator_view`  
 Объект запроса accelerator_view, для которого время ожидания в отключенном состоянии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логический флаг, указывающее, отключено ли время ожидания для указанного accelerator_view.  
  
##  <a name="a-namemada--mad-function"></a><a name="mad"></a>Функция MAD  
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
  
##  <a name="a-namemakearraya--makearray-function"></a><a name="make_array"></a>Функция make_array  
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
  
##  <a name="a-namenoisea--noise-function"></a><a name="noise"></a>Функция noise  
 Создает случайное значение с помощью алгоритма шума Перлина  
  
```  
inline float noise(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, из которой создается шума Перлина  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение шума Перлина в диапазоне от -1 до 1  
  
##  <a name="a-nameradiansa--radians-function"></a><a name="radians"></a>Функция RADIANS  
 Преобразует _X из градусов в радианы  
  
```  
inline float radians(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X преобразуется из градусов в радианы  
  
##  <a name="a-namercpa--rcp-function"></a><a name="rcp"></a>Функция rcp  
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
  
##  <a name="a-namereversebitsa--reversebits-function"></a><a name="reversebits"></a>Функция reversebits  
 Изменяет порядок битов _X  
  
```  
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целочисленное значение без знака  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение с порядком бит в _X в обратном порядке  
  
##  <a name="a-namesaturatea--saturate-function"></a><a name="saturate"></a>Функция saturate  
 Фиксирует _X в диапазоне от 0 до 1  
  
```  
inline float saturate(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X сжимается в диапазоне от 0 до 1  
  
##  <a name="a-namesigna--sign-function"></a><a name="sign"></a>Функция Sign  
 Определяет знак заданного аргумента.  
  
```  
inline int sign(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Знак аргумента.  
  
##  <a name="a-namesmoothstepa--smoothstep-function"></a><a name="smoothstep"></a>Функция smoothstep  
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
  
##  <a name="a-namestepa--step-function"></a><a name="step"></a>Функция Step  
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
  
##  <a name="a-nameumaxa--umax-function"></a><a name="umax"></a>Функция UMAX  
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
  
##  <a name="a-nameumina--umin-function"></a><a name="umin"></a>Функция umin  
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
 [Пространство имен Concurrency::Direct3D](concurrency-direct3d-namespace.md)

