---
title: Класс CComObjectRootEx
ms.date: 11/04/2016
f1_keywords:
- CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::InternalAddRef
- ATLCOM/ATL::InternalRelease
- ATLCOM/ATL::Lock
- ATLCOM/ATL::Unlock
- ATLCOM/ATL::FinalConstruct
- ATLCOM/ATL::FinalRelease
- ATLCOM/ATL::OuterAddRef
- ATLCOM/ATL::OuterQueryInterface
- ATLCOM/ATL::OuterRelease
- ATLCOM/ATL::InternalQueryInterface
- ATLCOM/ATL::ObjectMain
- ATLCOM/ATL::m_dwRef
- ATLCOM/ATL::m_pOuterUnknown
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
ms.openlocfilehash: e8db86f6214f95cd9bb08d3b5f6c6c1a38ca475c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327606"
---
# <a name="ccomobjectrootex-class"></a>Класс CComObjectRootEx

Этот класс предоставляет методы для обработки управления счетом отсчета объектов как для неагрегированных, так и для агрегированных объектов.

## <a name="syntax"></a>Синтаксис

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>Параметры

*ThreadModel*<br/>
Класс, методы которого реализуют нужную модель потоков. Вы можете явно выбрать модель потоков, установив *ThreadModel* на [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), или [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md). Вы можете принять модель потока по умолчанию, установив *ThreadModel* на [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) или [CComGlobalsThreadModel.](atl-typedefs.md#ccomglobalsthreadmodel)

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CComObjectRootEx](#ccomobjectrootex)|Конструктор.|
|[InternalAddRef](#internaladdref)|Приращения отсчета ссылок на неагрегированный объект.|
|[Внутреннееосвобождение](#internalrelease)|Декретирует значение отсчета ссылок на неагрегированный объект.|
|[Блокировки](#lock)|Если модель потока многопонительна, получает право собственности на объект критического сечения.|
|[Разблокировать](#unlock)|Если модель потока многопонительна, освобождает право собственности на объект критического сечения.|

### <a name="ccomobjectrootbase-methods"></a>Методы CComObjectRootBase

|||
|-|-|
|[FinalConstruct](#finalconstruct)|Переопределение в классе для выполнения любой инициализации, требуемой вашим объектом.|
|[Окончательное освобождение](#finalrelease)|Переопределение в классе для выполнения любой очистки, требуемой объектом.|
|[OuterAddRef](#outeraddref)|Приравливывает значение отсчета ссылок на агрегированный объект.|
|[Внешний КевириИнтерфейс](#outerqueryinterface)|Делегаты на `IUnknown` внешнем агрегированном объекте.|
|[Внешнийрелиз](#outerrelease)|Декретирует значение подсчета ссылок на агрегированный объект.|

### <a name="static-functions"></a>Статические функции

|||
|-|-|
|[Внутренний КевириИнтерфейс](#internalqueryinterface)|Делегаты `IUnknown` неагрегированного объекта.|
|[ObjectMain](#objectmain)|Вызывается во время инициализации модуля и прекращения для производных классов, перечисленных на карте объекта.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_dwRef](#m_dwref)|С `m_pOuterUnknown`частью профсоюза. Используется, когда объект не агрегирован для `AddRef` `Release`удержания отсчета ссылок и .|
|[m_pOuterUnknown](#m_pouterunknown)|С `m_dwRef`частью профсоюза. Используется при агрегировании объекта для удержания указателя на внешний неизвестный.|

## <a name="remarks"></a>Remarks

`CComObjectRootEx`обрабатывает управление счетом ссылки объектов как для неагрегированных, так и для агрегированных объектов. Он удерживает значение ссылки объекта, если ваш объект не агрегируется, и удерживает указатель на внешний неизвестный, если ваш объект агрегируется. Для агрегированных объектов `CComObjectRootEx` методы могут использоваться для обработки отказа внутреннего объекта к построению и защиты внешнего объекта от удаления при освобождении внутренних интерфейсов или удалении внутреннего объекта.

Класс, реализуемый сервер `CComObjectRootEx` COM, должен наследовать или [CComObjectRoot.](../../atl/reference/ccomobjectroot-class.md)

Если определение класса определяет [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) макрос, ATL создает `CComPolyObject<CYourClass>` `IClassFactory::CreateInstance` экземпляр того, когда называется. Во время создания проверяется значение внешнего неизвестного. Если он NULL, `IUnknown` реализуется для неагрегированного объекта. Если внешний неизвестный `IUnknown` не является NULL, реализуется для агрегированного объекта.

Если ваш класс не указывает DECLARE_POLY_AGGREGATABLE макрос, `CAggComObject<CYourClass>` ATL создает экземпляр для `CComObject<CYourClass>` агрегированных объектов или экземпляр для неагрегированных объектов.

Преимущество использования `CComPolyObject` заключается в том, что вы избегаете как, так `CComAggObject` и `CComObject` в модуле для обработки агрегированных и неагрегированных дел. Один `CComPolyObject` объект обрабатывает оба случая. Таким образом, в модуле существует только одна копия vtable и одна копия функций. Если ваш vtable большой, это может существенно уменьшить размер модуля. Однако, если ваш vtable `CComPolyObject` небольшой, использование может привести к несколько большему размеру модуля, `CComAggObject` `CComObject`потому что он не оптимизирован для агрегированного или неагрегированного объекта, как есть и .

Если ваш объект агрегирован, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) реализуется `CComAggObject` или `CComPolyObject`. Эти `QueryInterface`классы делегируют `CComObjectRootEx`, `OuterQueryInterface` `AddRef` `OuterAddRef`, `OuterRelease` и `Release` призывает к 'ы , и направить к внешнему неизвестному. Как правило, `CComObjectRootEx::FinalConstruct` переопределение в классе для создания любых `CComObjectRootEx::FinalRelease` агрегированных объектов и переопределение для освобождения любых агрегированных объектов.

Если ваш объект не `IUnknown` агрегирован, реализован `CComObject` или `CComPolyObject`. В этом случае, `QueryInterface` `AddRef`звонки, `Release` и `CComObjectRootEx`делегируются на 'ы `InternalQueryInterface`, `InternalAddRef`, и `InternalRelease` для выполнения фактических операций.

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomobjectrootexccomobjectrootex"></a><a name="ccomobjectrootex"></a>CComObjectrootEx::CcomObjectrootEx

Конструктор инициализирует значение отсчета ссылок до 0.

```
CComObjectRootEx();
```

## <a name="ccomobjectrootexfinalconstruct"></a><a name="finalconstruct"></a>CComObjectRootEx::FinalConstruct

Вы можете переопределить этот метод в своем производном классе для выполнения любой инициализации, необходимой для вашего объекта.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Возвращаемое значение

Возврат S_OK на успех или один из стандартных значений HRESULT ошибки.

### <a name="remarks"></a>Remarks

По умолчанию, `CComObjectRootEx::FinalConstruct` просто возвращает S_OK.

Есть преимущества для выполнения `FinalConstruct` инициализации, а не конструктор вашего класса:

- Вы не можете вернуть код статуса от конструктора, но `FinalConstruct`вы можете вернуть HRESULT с помощью значения возврата. Когда объекты вашего класса создаются с использованием фабрики стандартного класса, предоставляемой ATL, это значение возврата распространяется обратно клиенту COM, что позволяет предоставить им подробную информацию об ошибках.

- Вы не можете вызывать виртуальные функции через виртуальный механизм функции от конструктора класса. Вызов виртуальной функции от конструктора класса приводит к статично разрешенным вызову к функции, как это определено на этом этапе иерархии наследования. Вызовы на чистые виртуальные функции приводят к ошибкам связующим звеном.

   Ваш класс не является самым производным классом в иерархии наследования — он опирается на производный класс, поставляемый ATL, чтобы обеспечить некоторые из его функциональных возможностей. Существует хороший шанс, что ваша инициализация будет нуждаться в использовании функций, предоставляемых этим классом (это, безусловно, верно, когда объекты вашего класса необходимо агрегировать другие объекты), но конструктор в вашем классе не имеет возможности получить доступ к этим функциям. Строительный код для вашего класса выполняется до полного построения самого производного класса.

   Тем `FinalConstruct` не менее, вызывается сразу же после того, как самый производный класс полностью построен, что позволяет вызывать виртуальные функции и использовать реализацию подсчета ссылок, предоставляемую ATL.

### <a name="example"></a>Пример

Как правило, переопределить этот метод `CComObjectRootEx` в классе, полученном из для создания любых агрегированных объектов. Пример:

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

Если конструкция не удается, вы можете вернуть ошибку. Вы также можете использовать [макро-DECLARE_PROTECT_FINAL_CONSTRUCT,](aggregation-and-class-factory-macros.md#declare_protect_final_construct) чтобы защитить ваш внешний объект от удаления, если во время создания, внутренний агрегированный объект приращения отсчета ссылки, то decrements рассчитывать до 0.

Вот типичный способ создания агрегата:

- Добавьте `IUnknown` указатель к объекту класса и инициализировать его в NULL в конструкторе.

- Переопределение `FinalConstruct` для создания агрегата.

- Используйте `IUnknown` указатель, который вы определили в качестве параметра для [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) макроса.

- Переопределение `FinalRelease` для `IUnknown` выпуска указателя.

## <a name="ccomobjectrootexfinalrelease"></a><a name="finalrelease"></a>CComObjectRootEx::FinalRelease

Вы можете переопределить этот метод в своем производном классе для выполнения любой очистки, необходимой для вашего объекта.

```
void FinalRelease();
```

### <a name="remarks"></a>Remarks

По умолчанию ничего `CComObjectRootEx::FinalRelease` не делает.

Выполнение очистки `FinalRelease` предпочтительнее добавления кода к деструктору вашего класса, так как объект `FinalRelease` все еще полностью построен в точке, в которой называется. Это позволяет безопасно получить доступ к методам, предоставляемым наиболее производным классом. Это особенно важно для освобождения любых агрегированных объектов перед удалением.

## <a name="ccomobjectrootexinternaladdref"></a><a name="internaladdref"></a>CComObjectrootEx::InternaladdRef

Приращения эталонного количества неагрегированного объекта по 1.

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

### <a name="remarks"></a>Remarks

Если модель потока многопонительна, `InterlockedIncrement` используется для предотвращения изменения количества ссылок в одно и то же время нескольких потоков.

## <a name="ccomobjectrootexinternalqueryinterface"></a><a name="internalqueryinterface"></a>CComObjectRootEx::InternalqueryInterface

Извлекает указатель на запрошенный интерфейс.

```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*pThis*<br/>
(в) Указатель на объект, содержащий карту интерфейсов `QueryInterface`COM, подверженных.

*pE записи*<br/>
(в) Указатель на `_ATL_INTMAP_ENTRY` структуру, которая получает доступ к карте доступных интерфейсов.

*Iid*<br/>
(в) GUID запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, указанный в *iid,* или NULL, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

`InternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM. Если ваш объект агрегирован, `InternalQueryInterface` не делегирует внешнему неизвестному. Вы можете ввести интерфейсы в таблицу карты COM с [макро-COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) или одним из его вариантов.

## <a name="ccomobjectrootexinternalrelease"></a><a name="internalrelease"></a>CComObjectRootEx::InternalRelease

Декретирует количество ссылок на неагрегированный объект по 1.

```
ULONG InternalRelease();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках, не отладивать, так и в отладке, эта функция возвращает значение, которое может быть полезно для диагностики или тестирования. Точное значение возвращается зависит от многих факторов, таких как операционная система используется, и может, или не может быть ссылка кол.

### <a name="remarks"></a>Remarks

Если модель потока многопонительна, `InterlockedDecrement` используется для предотвращения изменения количества ссылок в одно и то же время нескольких потоков.

## <a name="ccomobjectrootexlock"></a><a name="lock"></a>CComObjectRootEx::Lock

Если модель потока многопонительна, этот метод вызывает функцию In32 API [EnterCriticalSection,](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)которая ждет, пока поток может взять на себя ответственность за критический объект раздела, полученный через частного члена данных.

```
void Lock();
```

### <a name="remarks"></a>Remarks

Когда защищенный код завершает выполнение, поток должен `Unlock` вызвать для освобождения права собственности на критический раздел.

Если модель потока однопонительна, этот метод ничего не делает.

## <a name="ccomobjectrootexm_dwref"></a><a name="m_dwref"></a>CComObjectRootEx:::m_dwRef

Часть союза, который получает доступ к четырем байтам памяти.

```
long m_dwRef;
```

### <a name="remarks"></a>Remarks

С `m_pOuterUnknown`, частью союза:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Если объект не агрегирован, количество ссылок, доступное `AddRef` и `Release` хранящееся в `m_dwRef`. Если объект агрегирован, указатель на внешний неизвестный хранится в [m_pOuterUnknown.](#m_pouterunknown)

## <a name="ccomobjectrootexm_pouterunknown"></a><a name="m_pouterunknown"></a>CComObjectRootEx::m_pOuterUnknown

Часть союза, который получает доступ к четырем байтам памяти.

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>Remarks

С `m_dwRef`, частью союза:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Если объект агрегирован, указатель на внешний `m_pOuterUnknown`неизвестный хранится в . Если объект не агрегирован, количество ссылок, доступное `AddRef` и `Release` хранящееся в [m_dwRef.](#m_dwref)

## <a name="ccomobjectrootexobjectmain"></a><a name="objectmain"></a>CComObjectRootEx::ObjectMain

Для каждого класса, указанного на карте объектов, эта функция вызывается один раз, когда модуль инициализирован, и снова, когда он завершается.

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>Параметры

*bНачало*<br/>
(ваут) Значение является правдой, если класс инициализируется; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Значение параметра *bStarting* указывает, является ли модуль инициализированным или прекращенным. Реализация по `ObjectMain` умолчанию ничего не делает, но вы можете переопределить эту функцию в своем классе, чтобы инициализировать или очистить ресурсы, которые вы хотите выделить для класса. Обратите `ObjectMain` внимание, что вызывается до запроса любых экземпляров класса.

`ObjectMain`вызывается из точки входа DLL, поэтому тип операции, которую может выполнить функция точки входа, ограничен. Для получения дополнительной информации об этих ограничениях см. [DLLs и Visual C е время выполнения время библиотеки поведения](../../build/run-time-library-behavior.md) и [DllMain](/windows/win32/Dlls/dllmain).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]

## <a name="ccomobjectrootexouteraddref"></a><a name="outeraddref"></a>CComObjectrootEx:OuteraddRef

Приращения отсчета ссылок внешнего неизвестного агрегата.

```
ULONG OuterAddRef();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

## <a name="ccomobjectrootexouterqueryinterface"></a><a name="outerqueryinterface"></a>CComObjectRootEx::Внешний интерфейс

Извлекает непрямой указатель на запрашиваемый интерфейс.

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, указанный в *iid,* или NULL, если агрегация не поддерживает интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomobjectrootexouterrelease"></a><a name="outerrelease"></a>CComObjectRootEx::Внешний выпуск

Декретирует количество ссылок на внешнюю неизвестность агрегатации.

```
ULONG OuterRelease();
```

### <a name="return-value"></a>Возвращаемое значение

В неотлибуговых сборках всегда возвращается 0. В сборках отладок возвращается значение, которое может быть полезно для диагностики или тестирования.

## <a name="ccomobjectrootexunlock"></a><a name="unlock"></a>CComObjectRootEx::Разблокировка

Если модель потока многопонительна, этот метод вызывает функцию API Win32 [LeaveCriticalSection,](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)которая выпускает право собственности на объект критического раздела, полученный через частного члена данных.

```
void Unlock();
```

### <a name="remarks"></a>Remarks

Чтобы получить право собственности, поток должен позвонить. `Lock` Каждый `Lock` вызов требует соответствующего `Unlock` вызова для освобождения собственности на критический раздел.

Если модель потока однопонительна, этот метод ничего не делает.

## <a name="see-also"></a>См. также раздел

[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
