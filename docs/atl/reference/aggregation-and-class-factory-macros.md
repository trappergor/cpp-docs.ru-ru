---
title: Агрегирование и макросов фабрики класса
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
ms.openlocfilehash: c0e3b6903e382ad56be9500792bec895a7641f00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497196"
---
# <a name="aggregation-and-class-factory-macros"></a>Агрегирование и макросов фабрики класса

Эти макросы обеспечивают способы управления агрегирования и фабрик классов объявления.

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Объявляет, что объект может быть статистически (по умолчанию).|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Объявляет фабрики класса быть [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), фабрика классов ATL по умолчанию.|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Объявляет объект фабрики класса быть фабрики класса.|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) быть фабрики класса.|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Объявляет [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) быть фабрики класса.|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Объявляет [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) быть фабрики класса.|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Объявляет виртуальную `GetControllingUnknown` функции.|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Объявляет, что невозможно выполнить статистическую обработку объекта.|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Объявляет, что ваш объект должен быть агрегатом.|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Проверяет значение параметра внешняя Неизвестная строка и объявляет объект статистическую обработку или не подлежащий статистической обработке, соответствующим образом.|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Внешний объект защищает от удаления во время создания внутреннего объекта.|
|[DECLARE_VIEW_STATUS](#declare_view_status)|Указывает флаги, просмотр СОСТОЯНИЯ в контейнер.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="declare_aggregatable"></a>  DECLARE_AGGREGATABLE

Указывает, что объект может быть агрегировано.

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Имя класса, который был определен как подлежащий статистической обработке.

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит этот макрос, чтобы указать модель статистической обработки по умолчанию. Чтобы переопределить это поведение по умолчанию, укажите [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) или [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) макроса в определении класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_classfactory"></a>  DECLARE_CLASSFACTORY

Объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) быть фабрики класса.

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) использует этот макрос для объявления фабрики класса по умолчанию для объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

##  <a name="ccomclassfactory_class"></a>  Класс CComClassFactory

Этот класс реализует [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) интерфейс.

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Примечания

`CComClassFactory` реализует [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) интерфейс, который содержит методы для создания объекта определенного CLSID, а также для блокировки фабрики классов в памяти, позволяющие быстрее создавать новые объекты. `IClassFactory` должен быть реализован для каждого класса, который зарегистрирован в системном реестре и в которой назначения CLSID.

Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` как фабрики класса по умолчанию. Чтобы переопределить это поведение по умолчанию, укажите один из DECLARE_CLASSFACTORY*XXX* макросы в определении класса. Например [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) макрос использует указанный класс фабрики класса:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

Указывает, что выше определения класса `CMyClassFactory` будет использоваться в качестве фабрики класса по умолчанию для объекта. `CMyClassFactory` должен быть производным от `CComClassFactory` и Переопределите `CreateInstance`.

Библиотека ATL предоставляет три другие макросы, которые объявляют фабрику класса:

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), который отвечающей за создание через лицензию.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) использует [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) использует [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), которая создает один [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объекта.

##  <a name="declare_classfactory_ex"></a>  DECLARE_CLASSFACTORY_EX

Объявляет `cf` быть фабрики класса.

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>Параметры

*CF*<br/>
[in] Имя класса, реализующего объект фабрики класса.

### <a name="remarks"></a>Примечания

*Cf* параметр должен быть производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и переопределить `CreateInstance` метод.

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает в себя [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает `CComClassFactory` как фабрики класса по умолчанию. Однако в определении класса объекта, включая макрос DECLARE_CLASSFACTORY_EX, переопределить это значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

##  <a name="declare_classfactory2"></a>  DECLARE_CLASSFACTORY2

Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) быть фабрики класса.

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>Параметры

*Лицензионное соглашение*<br/>
[in] Класс, реализующий `VerifyLicenseKey`, `GetLicenseKey`, и `IsLicenseValid`.

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает в себя [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрики класса по умолчанию. Однако в определении класса объекта, включая макрос DECLARE_CLASSFACTORY2, переопределить это значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

##  <a name="ccomclassfactory2_class"></a>  Класс CComClassFactory2

Этот класс реализует [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) интерфейс.

```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>Параметры

*лицензии*<br/>
Класс, реализующий следующие статические функции:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>Примечания

`CComClassFactory2` реализует [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) интерфейс, который представляет собой расширение из [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2` Создание элементов управления объекта через лицензию. Класс фабрики выполнение лицензированного компьютера можно предоставить ключ лицензии времени выполнения. Этот ключ лицензии позволяет приложению создавать экземпляры объектов, если лицензия весь компьютер не существует.

Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрики класса по умолчанию. Чтобы использовать `CComClassFactory2`, укажите [DECLARE_CLASSFACTORY2](#declare_classfactory2) макроса в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`, для параметра-шаблона `CComClassFactory2`, необходимо реализовать статические функции `VerifyLicenseKey`, `GetLicenseKey`, и `IsLicenseValid`. Ниже приведен пример класса простой лицензии:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2` наследует от `CComClassFactory2Base` и *лицензии*. `CComClassFactory2Base`, в свою очередь, является производным от `IClassFactory2` и **CComObjectRootEx\< CComGlobalsThreadModel >**.

##  <a name="declare_classfactory_auto_thread"></a>  DECLARE_CLASSFACTORY_AUTO_THREAD

Объявляет [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) быть фабрики класса.

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает в себя [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрики класса по умолчанию. Однако в определении класса объекта, включая макрос DECLARE_CLASSFACTORY_AUTO_THREAD, переопределить это значение по умолчанию.

При создании объектов в нескольких подразделениях (на сервере вне процесса), добавьте в класс DECLARE_CLASSFACTORY_AUTO_THREAD.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="ccomclassfactoryautothread_class"></a>  Класс CComClassFactoryAutoThread

Этот класс реализует [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) интерфейс и позволяет создавать в нескольких подразделениях объекты.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Примечания

`CComClassFactoryAutoThread` аналогичен [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), но позволяет создавать в нескольких подразделениях объекты. Чтобы воспользоваться преимуществами этой поддержки, являются производными модуле exe-файла из [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрики класса по умолчанию. Чтобы использовать `CComClassFactoryAutoThread`, укажите [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) макроса в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="declare_classfactory_singleton"></a>  DECLARE_CLASSFACTORY_SINGLETON

Объявляет [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) быть фабрики класса.

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>Параметры

*obj*<br/>
[in] Имя класса объекта.

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает в себя [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрики класса по умолчанию. Однако в определении класса объекта, включая макрос DECLARE_CLASSFACTORY_SINGLETON, переопределить это значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="ccomclassfactorysingleton_class"></a>  Класс CComClassFactorySingleton

Этот класс является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс.

`CComClassFactorySingleton` является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта. Каждый вызов `CreateInstance` метод просто запрашивает этот объект для указателя на интерфейс.

### <a name="remarks"></a>Примечания

Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` как фабрики класса по умолчанию. Чтобы использовать `CComClassFactorySingleton`, укажите [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) макроса в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="declare_get_controlling_unknown"></a>  DECLARE_GET_CONTROLLING_UNKNOWN

Объявляет виртуальную функцию `GetControllingUnknown`.

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>Примечания

Добавьте этот макрос для объекта, если вы получаете сообщение об ошибке компилятора `GetControllingUnknown` не определен (например, в `CComAggregateCreator`).

##  <a name="declare_not_aggregatable"></a>  DECLARE_NOT_AGGREGATABLE

Указывает, что невозможно выполнить статистическую обработку объекта.

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Имя объекта класса был определен как невозможна.

### <a name="remarks"></a>Примечания

Вызывает DECLARE_NOT_AGGREGATABLE `CreateInstance` будут возвращать ошибку (CLASS_E_NOAGGREGATION) в том случае, если предпринята попытка установить для выполнения статистического вычисления на объект.

По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит [DECLARE_AGGREGATABLE](#declare_aggregatable) макросом, который указывает, что объект может быть агрегировано. Чтобы переопределить это поведение по умолчанию, включите DECLARE_NOT_AGGREGATABLE в определении класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_only_aggregatable"></a>  DECLARE_ONLY_AGGREGATABLE

Указывает, что объект должен быть агрегированными.

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Имя объекта класса вы определяете как только статистически.

### <a name="remarks"></a>Примечания

DECLARE_ONLY_AGGREGATABLE вызывает ошибку (E_FAIL), если предпринята попытка `CoCreate` объект как неагрегированные объект.

По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит [DECLARE_AGGREGATABLE](#declare_aggregatable) макросом, который указывает, что объект может быть агрегировано. Чтобы переопределить это поведение по умолчанию, включите DECLARE_ONLY_AGGREGATABLE в определении класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

##  <a name="declare_poly_aggregatable"></a>  DECLARE_POLY_AGGREGATABLE

Указывает, что экземпляр **CComPolyObject \<**  *x* **>** при создании объекта.

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Имя объекта класса был определен как статистическую обработку или невозможна.

### <a name="remarks"></a>Примечания

Во время создания проверяется значение внешняя Неизвестная строка. Если он равен NULL, `IUnknown` реализуется для объекта неагрегированные. Если внешняя Неизвестная строка не равно NULL, `IUnknown` реализуется для объединенного объекта.

С помощью DECLARE_POLY_AGGREGATABLE удобен тем, что избавляет от необходимости оба `CComAggObject` и `CComObject` в модуле для обработки вариантов, статистические и неагрегированные. Один `CComPolyObject` объект обрабатывает в обоих случаях. Это означает, что только одна копия таблицы vtable и одна копия функции существуют в модуле. Если в таблице vtable имеет большой размер, это может значительно снизить размер вашего модуля. Тем не менее, если в таблице vtable невелик, с помощью `CComPolyObject` может привести к немного больший размер модуля, поскольку метод не оптимизирован для суммирования или неагрегированные объекта, так как `CComAggObject` и `CComObject`.

Макрос DECLARE_POLY_AGGREGATABLE автоматически объявляется в объекте, при использовании мастер элементов управления ATL, чтобы создать полный доступ.

##  <a name="declare_protect_final_construct"></a>  DECLARE_PROTECT_FINAL_CONSTRUCT

Позволяет защитить объект от удаления Если (во время [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) внутренний объект агрегированные увеличивает счетчик ссылок, а затем уменьшает счетчик 0.

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

##  <a name="declare_view_status"></a>  DECLARE_VIEW_STATUS

Поместите этот макрос в элемент управления ActiveX библиотеки ATL класс элемента управления, чтобы указать флаги Просмотр СОСТОЯНИЯ в контейнер.

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>Параметры

*statusFlags*<br/>
[in] Просмотр СОСТОЯНИЯ флаги. См. в разделе [Просмотр СОСТОЯНИЯ](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) список флагов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
