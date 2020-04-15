---
title: Агрегация и класс заводские макросы
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_AGGREGATABLE
- atlcom/ATL::DECLARE_CLASSFACTORY
- atlcom/ATL::DECLARE_CLASSFACTORY_EX
- atlcom/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- atlcom/ATL::DECLARE_CLASSFACTORY_SINGLETON
- atlcom/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- atlcom/ATL::DECLARE_NOT_AGGREGATABLE
- atlcom/ATL::DECLARE_ONLY_AGGREGATABLE
- atlcom/ATL::DECLARE_POLY_AGGREGATABLE
- atlcom/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- atlcom/ATL::DECLARE_VIEW_STATUS
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
ms.openlocfilehash: 33f33043d1a2c824ada26399365541796178d21d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319335"
---
# <a name="aggregation-and-class-factory-macros"></a>Агрегация и класс заводские макросы

Эти макросы обеспечивают способы контроля агрегации и объявления фабрик класса.

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Объявляет, что ваш объект может быть агрегирован (по умолчанию).|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Объявляет фабрику класса [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), фабрику класса ATL по умолчанию.|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Объявляет заводский объект вашего класса фабрикой.|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) фабрикой класса.|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Объявляет [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) фабрикой класса.|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Объявляет [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) фабрикой класса.|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Объявляет виртуальную `GetControllingUnknown` функцию.|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Заявляет, что ваш объект не может быть агрегирован.|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Объявляет, что ваш объект должен быть агрегирован.|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Проверяет значение внешнего неизвестного и объявляет ваш объект агрегируемым или не агрегируемым, в случае необходимости.|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Защищает внешний объект от удаления при строительстве внутреннего объекта.|
|[DECLARE_VIEW_STATUS](#declare_view_status)|Увеяет флаги VIEWSTATUS в контейнер.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="declare_aggregatable"></a><a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE

Укажите, что ваш объект может быть агрегирован.

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Название класса, которое вы определяете как агрегируемый.

### <a name="remarks"></a>Remarks

[CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит этот макрос для определения модели агрегации по умолчанию. Чтобы переопределить этот по умолчанию, укажите в определении класса DECLARE_NOT_AGGREGATABLE [или](#declare_not_aggregatable) [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) макрос.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_classfactory"></a><a name="declare_classfactory"></a>DECLARE_CLASSFACTORY

Объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) фабрикой класса.

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>Remarks

[CComCoClass](../../atl/reference/ccomcoclass-class.md) использует этот макрос для объявления фабрики класса по умолчанию для вашего объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

## <a name="ccomclassfactory-class"></a><a name="ccomclassfactory_class"></a>Класс CComClassFactory

Этот класс реализует интерфейс [IClassFactory.](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Remarks

`CComClassFactory`реализует интерфейс [IClassFactory,](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) который содержит методы создания объекта конкретного CLSID, а также блокировку фабрики класса в памяти, чтобы позволить создавать новые объекты быстрее. `IClassFactory`должны быть реализованы для каждого класса, который вы регистрируетесь в системном реестре и которому вы назначаете CLSID.

Объекты ATL обычно приобретают фабрику класса, произвнося из [CComCoClass.](../../atl/reference/ccomcoclass-class.md) Этот класс включает в себя `CComClassFactory` [макро-DECLARE_CLASSFACTORY,](#declare_classfactory)который объявляется фабрикой класса по умолчанию. Чтобы переопределить этот по умолчанию, укажите один из DECLARE_CLASSFACTORY*макросов XXX* в определении класса. Например, [в DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) макросе используется указанный класс для фабрики класса:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

В приведенном выше определении `CMyClassFactory` класса указывается, что будет использоваться в качестве фабрики класса по умолчанию объекта. `CMyClassFactory`должны вытекать `CComClassFactory` из `CreateInstance`и переопределить .

ATL предоставляет три других макроса, которые объявляют фабрику класса:

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) Использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), который контролирует создание через лицензию.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) Использует [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких квартирах.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) Использует [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), который строит один объект [CComObjectGlobal.](../../atl/reference/ccomobjectglobal-class.md)

## <a name="declare_classfactory_ex"></a><a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX

`cf` Объявляется фабрикой класса.

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>Параметры

*CF*<br/>
(в) Название класса, реализуемого на заводе-объекте класса.

### <a name="remarks"></a>Remarks

Параметр *cf* должен быть получен из [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и переопределить `CreateInstance` метод.

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает в себя [DECLARE_CLASSFACTORY](#declare_classfactory) макрос, который `CComClassFactory` определяется как фабрика класса по умолчанию. Однако, включив DECLARE_CLASSFACTORY_EX макроса в определение класса объекта, вы переопределить этот по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

## <a name="declare_classfactory2"></a><a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2

Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) фабрикой класса.

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>Параметры

*Lic*<br/>
(в) Класс, который `VerifyLicenseKey`реализует, `GetLicenseKey` `IsLicenseValid`и .

### <a name="remarks"></a>Remarks

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает в себя [DECLARE_CLASSFACTORY](#declare_classfactory) макрос, который определяет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрику класса по умолчанию. Однако, включив DECLARE_CLASSFACTORY2 макроса в определение класса объекта, вы переопределить этот по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

## <a name="ccomclassfactory2-class"></a><a name="ccomclassfactory2_class"></a>Класс CComClassFactory2

Этот класс реализует интерфейс [IClassFactory2.](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)

```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>Параметры

*Лицензии*<br/>
Класс, который реализует следующие статические функции:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>Remarks

`CComClassFactory2`реализует интерфейс [IClassFactory2,](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) который является продолжением [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2`контролирует создание объекта через лицензию. Фабрика класса, исполняющая на лицензионной машине, может обеспечить ключ лицензии времени выполнения. Этот ключ лицензии позволяет приложению мгновенно использовать объекты, когда полной лицензии машины не существует.

Объекты ATL обычно приобретают фабрику класса, произвнося из [CComCoClass.](../../atl/reference/ccomcoclass-class.md) Этот класс включает в себя [макроDECLARE_CLASSFACTORY,](#declare_classfactory)который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) фабрикой класса по умолчанию. Для `CComClassFactory2`использования укажите [DECLARE_CLASSFACTORY2](#declare_classfactory2) макрос в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`, параметр `CComClassFactory2`шаблона к, `VerifyLicenseKey`должен `GetLicenseKey`реализовать `IsLicenseValid`статические функции, и . Ниже приводится пример простого класса лицензии:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2`вытекает из `CComClassFactory2Base` обоих и *лицензии*. `CComClassFactory2Base`, в свою очередь, происходит от `IClassFactory2` и **CComObjectRootEx\< CComGlobalsThreadModel >**.

## <a name="declare_classfactory_auto_thread"></a><a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD

Объявляет [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) фабрикой класса.

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>Remarks

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает в себя [DECLARE_CLASSFACTORY](#declare_classfactory) макрос, который определяет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрику класса по умолчанию. Однако, включив DECLARE_CLASSFACTORY_AUTO_THREAD макрос атакжем в определение класса объекта, вы переопределить этот по умолчанию.

When you create objects in multiple apartments (in an out-of-proc server), add DECLARE_CLASSFACTORY_AUTO_THREAD to your class.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="ccomclassfactoryautothread-class"></a><a name="ccomclassfactoryautothread_class"></a>Класс CComClassFactoryПоток

Этот класс реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) и позволяет создавать объекты в нескольких квартирах.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Remarks

`CComClassFactoryAutoThread`похож на [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), но позволяет объекты, которые будут созданы в нескольких квартирах. Чтобы воспользоваться этой поддержкой, выберите модуль EXE из [CComAutoThreadModule.](../../atl/reference/ccomautothreadmodule-class.md)

Объекты ATL обычно приобретают фабрику класса, произвнося из [CComCoClass.](../../atl/reference/ccomcoclass-class.md) Этот класс включает в себя [макроDECLARE_CLASSFACTORY,](#declare_classfactory)который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) фабрикой класса по умолчанию. Для `CComClassFactoryAutoThread`использования укажите [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) макрос в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="declare_classfactory_singleton"></a><a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON

Объявляет [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) фабрикой класса.

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>Параметры

*obj*<br/>
(в) Имя объекта класса.

### <a name="remarks"></a>Remarks

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает в себя [DECLARE_CLASSFACTORY](#declare_classfactory) макрос, который определяет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрику класса по умолчанию. Однако, включив DECLARE_CLASSFACTORY_SINGLETON макрос атакжем в определение класса объекта, вы переопределить этот по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="ccomclassfactorysingleton-class"></a><a name="ccomclassfactorysingleton_class"></a>Класс CComClassFactoryСинглтон

Этот класс происходит от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для построения одного объекта.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>Параметры

*T*<br/>
Твой класс.

`CComClassFactorySingleton`происходит от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для построения одного объекта. Каждый вызов `CreateInstance` метода просто запрашивает этот объект для указателя интерфейса.

### <a name="remarks"></a>Remarks

Объекты ATL обычно приобретают фабрику класса, произвнося из [CComCoClass.](../../atl/reference/ccomcoclass-class.md) Этот класс включает в себя `CComClassFactory` [макро-DECLARE_CLASSFACTORY,](#declare_classfactory)который объявляется фабрикой класса по умолчанию. Для `CComClassFactorySingleton`использования укажите [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) макрос в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="declare_get_controlling_unknown"></a><a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN

Объявляет виртуальную `GetControllingUnknown`функцию.

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>Remarks

Добавьте этот макрос к объекту, если `GetControllingUnknown` вы получите неопределенный сообщение об ошибке компилятора (например, в). `CComAggregateCreator`

## <a name="declare_not_aggregatable"></a><a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE

Укажите, что ваш объект не может быть агрегирован.

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Имя объекта класса, которое вы определяете как не агрегируемый.

### <a name="remarks"></a>Remarks

DECLARE_NOT_AGGREGATABLE `CreateInstance` причины возврата ошибки (CLASS_E_NOAGGREGATION), если сделана попытка агрегировать на объекте.

По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит [DECLARE_AGGREGATABLE](#declare_aggregatable) макрос, в котором указывается, что ваш объект может быть агрегирован. Чтобы переопределить это поведение по умолчанию, включите DECLARE_NOT_AGGREGATABLE в определение класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_only_aggregatable"></a><a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE

Укажите, что ваш объект должен быть агрегирован.

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Имя объекта класса, которое вы определяете как только агрегируемый.

### <a name="remarks"></a>Remarks

DECLARE_ONLY_AGGREGATABLE вызывает ошибку (E_FAIL), если `CoCreate` попытка сделана вашему объекту как неагрегированному объекту.

По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит [DECLARE_AGGREGATABLE](#declare_aggregatable) макрос, в котором указывается, что ваш объект может быть агрегирован. Чтобы переопределить это поведение по умолчанию, включите DECLARE_ONLY_AGGREGATABLE в определение класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

## <a name="declare_poly_aggregatable"></a><a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE

Укажите, что экземпляр **CComPolyObject \< ** *x* **>** создается при создании объекта.

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Название объекта класса, которое вы определяете как агрегируемый или не агрегируемый.

### <a name="remarks"></a>Remarks

Во время создания проверяется значение внешнего неизвестного. Если он NULL, `IUnknown` реализуется для неагрегированного объекта. Если внешний неизвестный `IUnknown` не является NULL, реализуется для агрегированного объекта.

Преимущество использования DECLARE_POLY_AGGREGATABLE заключается в `CComAggObject` том, что вы избегаете как, так и `CComObject` в модуле для обработки агрегированных и неагрегированных дел. Один `CComPolyObject` объект обрабатывает оба случая. Это означает, что в модуле существует только одна копия vtable и одна копия функций. Если ваш vtable большой, это может существенно уменьшить размер модуля. Однако, если ваш vtable `CComPolyObject` небольшой, использование может привести к несколько большему размеру модуля, `CComAggObject` `CComObject`потому что он не оптимизирован для агрегированного или неагрегированного объекта, как есть и .

Макрос DECLARE_POLY_AGGREGATABLE автоматически объявляется в объекте, если вы используете atL Control Wizard для создания полного управления.

## <a name="declare_protect_final_construct"></a><a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT

Защищает ваш объект от удаления, если (во время [FinalConstruct)](ccomobjectrootex-class.md#finalconstruct)внутренний агрегированный объект приращает значение отсчета ссылок, а затем декреционирует количество до 0.

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

## <a name="declare_view_status"></a><a name="declare_view_status"></a>DECLARE_VIEW_STATUS

Поместите этот макрос в класс управления ATL ActiveX, чтобы указать флаги VIEWSTATUS в контейнер.

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>Параметры

*статусФлаги*<br/>
(в) Флаги VIEWSTATUS. Смотрите [VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus) для списка флагов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
