---
title: Макросы агрегирования и фабрики классов
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
ms.openlocfilehash: 38239942b99a29b5777deef8000d9f1ab85b10e6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492202"
---
# <a name="aggregation-and-class-factory-macros"></a>Макросы агрегирования и фабрики классов

Эти макросы предоставляют способы управления статистической обработкой и объявлением фабрик классов.

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Объявляет, что объект может быть агрегирован (по умолчанию).|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Объявляет фабрику класса для [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md), фабрику классов ATL по умолчанию.|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Объявляет объект фабрики класса как фабрику класса.|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) как фабрику класса.|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Объявляет [ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрику класса.|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Объявляет [ккомклассфакторисинглетон](../../atl/reference/ccomclassfactorysingleton-class.md) как фабрику класса.|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Объявляет виртуальную `GetControllingUnknown` функцию.|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Объявляет, что объект не может быть агрегирован.|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Объявляет, что объект должен быть агрегирован.|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Проверяет значение внешней неизвестной функции и объявляет статистическую обработку объекта или не подлежит статистической обработке, если это уместно.|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Защищает внешний объект от удаления во время создания внутреннего объекта.|
|[DECLARE_VIEW_STATUS](#declare_view_status)|Задает флаги ВИЕВСТАТУС для контейнера.|

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE

Указывает, что объект может быть агрегирован.

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя класса, который определяется как статистически обрабатываемый.

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит этот макрос для указания статистической модели по умолчанию. Чтобы переопределить это значение по умолчанию, укажите в определении класса макрос [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) или [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_classfactory"></a>DECLARE_CLASSFACTORY

Объявляет [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) как фабрику класса.

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) использует этот макрос для объявления фабрики класса по умолчанию для объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

##  <a name="ccomclassfactory_class"></a>Класс Ккомклассфактори

Этот класс реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) .

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Примечания

`CComClassFactory`реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) , который содержит методы для создания объекта определенного идентификатора CLSID, а также блокирует фабрику класса в памяти, чтобы новые объекты могли создаваться быстрее. `IClassFactory`должен быть реализован для каждого класса, регистрируемого в системном реестре и которому назначается идентификатор CLSID.

Объекты ATL обычно получают фабрику классов путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` фабрику классов по умолчанию. Чтобы переопределить это значение по умолчанию, укажите один из макросов DECLARE_CLASSFACTORY*xxx* в определении класса. Например, макрос [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) использует указанный класс для фабрики класса:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

Приведенное выше определение класса указывает `CMyClassFactory` , что будет использоваться в качестве фабрики класса по умолчанию для объекта. `CMyClassFactory`должен быть производным `CComClassFactory` от и `CreateInstance`переопределять.

ATL предоставляет три других макроса, которые объявляют фабрику класса:

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) Использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), который управляет созданием с помощью лицензии.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) Использует [ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) Использует [ккомклассфакторисинглетон](../../atl/reference/ccomclassfactorysingleton-class.md), который конструирует один объект [ккомобжектглобал](../../atl/reference/ccomobjectglobal-class.md) .

##  <a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX

`cf` Объявляется как фабрика класса.

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>Параметры

*CF*<br/>
окне Имя класса, реализующего объект фабрики класса.

### <a name="remarks"></a>Примечания

Параметр *CF* должен быть производным от [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) `CreateInstance` и переопределять метод.

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory) , который указывает `CComClassFactory` в качестве фабрики классов по умолчанию. Однако, включив макрос DECLARE_CLASSFACTORY_EX в определение класса объекта, вы переопределяете это значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

##  <a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2

Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) как фабрику класса.

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>Параметры

*LIC*<br/>
окне Класс, реализующий `VerifyLicenseKey`, `GetLicenseKey`и `IsLicenseValid`.

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory) , указывающий [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики класса по умолчанию. Однако, включив макрос DECLARE_CLASSFACTORY2 в определение класса объекта, вы переопределяете это значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

##  <a name="ccomclassfactory2_class"></a>Класс CComClassFactory2

Этот класс реализует интерфейс [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) .

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

`CComClassFactory2`реализует интерфейс [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) , который является расширением [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2`управляет созданием объектов с помощью лицензии. Фабрика класса, выполняемая на Лицензированном компьютере, может предоставить лицензионный ключ. Этот лицензионный ключ позволяет приложению создавать экземпляры объектов, если лицензия на компьютер не существует.

Объекты ATL обычно получают фабрику классов путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики классов по умолчанию. Чтобы использовать `CComClassFactory2`, укажите макрос [DECLARE_CLASSFACTORY2](#declare_classfactory2) в определении класса объекта. Например:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`, параметр шаблона `CComClassFactory2`для должен реализовывать статические функции `VerifyLicenseKey`, `GetLicenseKey`и `IsLicenseValid`. Ниже приведен пример простого класса License:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2`является производным от `CComClassFactory2Base` *лицензии*и. `CComClassFactory2Base`, в свою очередь, является производным от `IClassFactory2` и **CComObjectRootEx\< ккомглобалссреадмодел >** .

##  <a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD

Объявляет [ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрику класса.

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory) , указывающий [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики класса по умолчанию. Однако, включив макрос DECLARE_CLASSFACTORY_AUTO_THREAD в определение класса объекта, вы переопределяете это значение по умолчанию.

При создании объектов в нескольких подразделениях (на сервере вне процесса) добавьте DECLARE_CLASSFACTORY_AUTO_THREAD в свой класс.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="ccomclassfactoryautothread_class"></a>Класс Ккомклассфакторяутосреад

Этот класс реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) и позволяет создавать объекты в нескольких подразделениях.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Примечания

`CComClassFactoryAutoThread`аналогичен [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md), но позволяет создавать объекты в нескольких апартаментах. Чтобы воспользоваться этой поддержкой, создайте свой модуль EXE из [ккомаутосреадмодуле](../../atl/reference/ccomautothreadmodule-class.md).

Объекты ATL обычно получают фабрику классов путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики классов по умолчанию. Чтобы использовать `CComClassFactoryAutoThread`, укажите макрос [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) в определении класса объекта. Например:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON

Объявляет [ккомклассфакторисинглетон](../../atl/reference/ccomclassfactorysingleton-class.md) как фабрику класса.

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>Параметры

*obj*<br/>
окне Имя объекта класса.

### <a name="remarks"></a>Примечания

[CComCoClass](../../atl/reference/ccomcoclass-class.md) включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory) , указывающий [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) в качестве фабрики класса по умолчанию. Однако, включив макрос DECLARE_CLASSFACTORY_SINGLETON в определение класса объекта, вы переопределяете это значение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="ccomclassfactorysingleton_class"></a>Класс Ккомклассфакторисинглетон

Этот класс является производным от [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) и использует [ккомобжектглобал](../../atl/reference/ccomobjectglobal-class.md) для создания одного объекта.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс.

`CComClassFactorySingleton`является производным от [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) и использует [ккомобжектглобал](../../atl/reference/ccomobjectglobal-class.md) для создания одного объекта. Каждый вызов `CreateInstance` метода просто запрашивает этот объект для указателя интерфейса.

### <a name="remarks"></a>Примечания

Объекты ATL обычно получают фабрику классов путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` фабрику классов по умолчанию. Чтобы использовать `CComClassFactorySingleton`, укажите макрос [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) в определении класса объекта. Например:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN

Объявляет виртуальную функцию `GetControllingUnknown`.

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>Примечания

Добавьте этот макрос в объект, `GetControllingUnknown` если вы получаете неопределенное сообщение об ошибке компилятора (например, в `CComAggregateCreator`).

##  <a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE

Указывает, что невозможно выполнить статистическую обработку объекта.

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя объекта класса, который вы определяете как не подлежащий статистической обработке.

### <a name="remarks"></a>Примечания

DECLARE_NOT_AGGREGATABLE приводит `CreateInstance` к возвращению ошибки (CLASS_E_NOAGGREGATION), если предпринимается попытка выполнить статистическую обработку на объекте.

По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит макрос [DECLARE_AGGREGATABLE](#declare_aggregatable) , который указывает, что объект может быть агрегирован. Чтобы переопределить это поведение по умолчанию, включите DECLARE_NOT_AGGREGATABLE в определение класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE

Указывает, что объект должен быть агрегирован.

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя объекта класса, который вы определяете как Статистическое вычисление.

### <a name="remarks"></a>Примечания

DECLARE_ONLY_AGGREGATABLE вызывает ошибку (E_FAIL) при попытке обращения к `CoCreate` объекту в качестве неагрегированного объекта.

По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит макрос [DECLARE_AGGREGATABLE](#declare_aggregatable) , который указывает, что объект может быть агрегирован. Чтобы переопределить это поведение по умолчанию, включите DECLARE_ONLY_AGGREGATABLE в определение класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

##  <a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE

Указывает, что при создании объекта создается экземпляр **CComPolyObject \<**  *x* **>** .

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя объекта класса, который определяется как агрегированный или не подлежащий статистической обработке.

### <a name="remarks"></a>Примечания

Во время создания проверяется значение внешней неизвестной. Если он равен null, `IUnknown` реализуется для неагрегированного объекта. Если внешнее неизвестное значение не `IUnknown` равно null, реализуется для агрегированного объекта.

Преимущество использования DECLARE_POLY_AGGREGATABLE заключается в том, что вы не `CComAggObject` должны использовать и `CComObject` в модуле, чтобы обрабатывать агрегированные и неагрегированные варианты. В обоих `CComPolyObject` случаях обрабатывается один объект. Это означает, что в модуле существует только одна копия таблицы vtable и одна копия функций. Если таблица vtable велика, это может значительно снизить размер модуля. Однако если таблица vtable невелика, использование `CComPolyObject` может привести к тому, что размер модуля будет немного больше, поскольку он не оптимизирован для агрегированного или неагрегированного объекта, `CComAggObject` как `CComObject`и.

Макрос DECLARE_POLY_AGGREGATABLE автоматически объявляется в объекте, если для создания полного доступа используется мастер элементов управления ATL.

##  <a name="declare_protect_final_construct"></a>  DECLARE_PROTECT_FINAL_CONSTRUCT

Защищает объект от удаления, если (во время [финалконструкт](ccomobjectrootex-class.md#finalconstruct)) внутренний агрегированный объект увеличивает число ссылок, а затем уменьшает значение на 0.

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

##  <a name="declare_view_status"></a>DECLARE_VIEW_STATUS

Поместите этот макрос в класс элемента управления ActiveX ATL, чтобы указать флаги ВИЕВСТАТУС для контейнера.

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>Параметры

*статусфлагс*<br/>
окне Флаги ВИЕВСТАТУС. Список флагов см. в разделе [виевстатус](/windows/win32/api/ocidl/ne-ocidl-viewstatus) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
