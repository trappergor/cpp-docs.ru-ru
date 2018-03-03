---
title: "Класс CComObjectRootEx | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bab27a9d8b5af8315d9d3468933ea016b12e3399
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx-класс
Этот класс предоставляет методы для обработки объекта управления счетчиками ссылок для неагрегированные и статистические объекты.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>Параметры  
 `ThreadModel`  
 Класс, методы которого реализации требуемой потоковую модель. Можно явно выбрать потоковую модель, задав `ThreadModel` для [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), или [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md). Вы можете принять модель потоков сервера по умолчанию, задав `ThreadModel` для [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) или [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel).  

  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|Конструктор.|  
|[InternalAddRef](#internaladdref)|Увеличивает счетчик ссылок для неагрегированные объекта.|  
|[InternalRelease](#internalrelease)|Уменьшает счетчик ссылок для неагрегированные объекта.|  
|[Блокировка](#lock)|Если модель является многопоточным, получает права владельца объекта критической секции.|  
|[Снятие блокировки](#unlock)|Если модель является многопоточным, освобождает владение объект критической секции.|  
  
### <a name="ccomobjectrootbase-methods"></a>Методы CComObjectRootBase  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|Переопределить в классе для выполнения любой инициализации, необходимые для вашего объекта.|  
|[FinalRelease](#finalrelease)|Переопределения в классе, чтобы выполнить очистку для вашего объекта.|  
|[OuterAddRef](#outeraddref)|Увеличивает счетчик ссылок для вычисляемого объекта.|  
|[OuterQueryInterface](#outerqueryinterface)|Делегаты для внешнего **IUnknown** агрегированных объекта.|  
|[OuterRelease](#outerrelease)|Уменьшает счетчик ссылок для вычисляемого объекта.|  
  
### <a name="static-functions"></a>Статические функции  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|Делегирует **IUnknown** неагрегированные объекта.|  
|[ObjectMain](#objectmain)|Вызван во время инициализации модуля и завершения для производных классов, перечисленных в карте объектов.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|С `m_pOuterUnknown`, часть объединения. Используется, если объект не является агрегатом для хранения количество ссылок на `AddRef` и **выпуска**.|  
|[m_pOuterUnknown](#m_pouterunknown)|С `m_dwRef`, часть объединения. Используется, когда объект является статистическим выражением, чтобы хранить указатель внешняя Неизвестная строка.|  
  
## <a name="remarks"></a>Примечания  
 `CComObjectRootEx`обрабатывает объект управления счетчиками ссылок для неагрегированные и статистические объекты. Она содержит счетчик ссылок объекта, если объект не выполняется статистическая обработка и хранит указатель на внешняя Неизвестная строка, если объект выполняется статистическая обработка. Для статистических объектов `CComObjectRootEx` методы могут использоваться для обработки удалось создать внутренний объект, а для защиты внешний объект от удаления при выпуске внутреннего интерфейсов или внутренний объект удаляется.  
  
 Класс, который реализует COM-сервера должен наследовать от `CComObjectRootEx` или [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 При определении класса указывает [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) макрос, ATL создает экземпляр **CComPolyObject\<окне отслеживания TRACE появляется >** при **IClassFactory:: CreateInstance** вызывается. Во время создания проверяется значение внешняя Неизвестная строка. Если это **NULL**, **IUnknown** реализуется для неагрегированные объекта. Если внешняя Неизвестная строка не **NULL**, **IUnknown** реализуется для вычисляемого объекта.  
  
 Если класс не указывает `DECLARE_POLY_AGGREGATABLE` макрос, ATL создает экземпляр **CAggComObject\<окне отслеживания TRACE появляется >** статистические объекты или экземпляр **CComObject\<окне отслеживания TRACE появляется >** неагрегированные объектов.  
  
 Преимущество использования `CComPolyObject` — избежать обладает и разрешением `CComAggObject` и `CComObject` в модуле для обработки случаев, статистические и нестатистические. Один `CComPolyObject` объект обрабатывает в обоих случаях. Таким образом только одна копия виртуальной таблице и одна копия функции существуют в модуле. При большом вашей vtable это существенно уменьшить размер вашего модуля. Тем не менее, используемой при небольших вашей vtable `CComPolyObject` может привести к немного больший размер модуля, так как он не оптимизирован для суммирования или неагрегированные объекта, как `CComAggObject` и `CComObject`.  
  
 Если объект является статистическим выражением, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) реализуется `CComAggObject` или `CComPolyObject`. Эти классы делегировать `QueryInterface`, `AddRef`, и **выпуска** вызовы `CComObjectRootEx` `OuterQueryInterface`, `OuterAddRef`, и `OuterRelease` переслать внешняя Неизвестная строка. Как правило, можно переопределить `CComObjectRootEx::FinalConstruct` в классе, чтобы создать статистические объекты и Переопределите `CComObjectRootEx::FinalRelease` чтобы освободить все статистическая обработка объектов.  
  
 Если объект не является статистическим выражением, **IUnknown** реализуется `CComObject` или `CComPolyObject`. В этом случае вызовы `QueryInterface`, `AddRef`, и **выпуска** делегируются `CComObjectRootEx` `InternalQueryInterface`, `InternalAddRef`, и `InternalRelease` для выполнения фактического операций.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="ccomobjectrootex"></a>CComObjectRootEx::CComObjectRootEx  
 Конструктор инициализирует счетчик ссылок на 0.  
  
```
CComObjectRootEx();
```  
  
##  <a name="finalconstruct"></a>CComObjectRootEx::FinalConstruct  
 Этот метод можно переопределить в производном классе для выполнения любой инициализации, необходимые для объекта.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вернуть `S_OK` на успех или одну из стандартных ошибок `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CComObjectRootEx::FinalConstruct` просто возвращает `S_OK`.  
  
 Преимущества для выполнения инициализации в `FinalConstruct` вместо того чтобы конструктор класса:  
  
-   Код состояния не может возвращать из конструктора, но можно вернуть `HRESULT` с помощью параметра `FinalConstruct`возвращаемое значение. Это возвращаемое значение объектов класса создаются с помощью стандартного класса фабрики, предоставляемые ATL, распространяется обратно клиенту COM, что позволяет предоставить подробные сведения об ошибке.  
  
-   Нельзя вызывать виртуальные функции посредством механизма виртуальных функций из конструктора класса. Вызов виртуальной функции из конструктора класса приводит к статически разрешаемые вызову функции, как это определено в этой точке в иерархии наследования. Вызовы чистые виртуальные функции приводят к ошибкам компоновщика.  
  
     Класс не является наиболее производный класс в иерархии наследования, зависит от производного класса, предоставляемые ATL для обеспечения некоторые функции. Есть риск, что ваш инициализации потребуется использовать функции, предоставляемые этим классом (Это определенно значение true, если объекты этого класса должны статистическую обработку других объектов), но конструктор класса не имеет возможности доступа к ним. Код создания для класса выполняется до наиболее производного класса полностью созданы.  
  
     Однако `FinalConstruct` вызывается сразу после наиболее производный класс полностью созданы, что позволяет вызывать виртуальные функции и использовать реализацию подсчета ссылок, предоставляемые ATL.  
  
### <a name="example"></a>Пример  
 Как правило, переопределите этот метод в класс, производный от `CComObjectRootEx` для создания любой статистическая обработка объектов. Пример:  
  
 [!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 При сбое построения может возвращать ошибку. Можно также использовать макрос [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) для защиты вашей внешний объект дают удалены, если во время создания внутреннего объекта статистические увеличивает счетчик ссылок, а затем уменьшает число 0.  
  
 Ниже приведен типичный способ создания статистического выражения:  
  
-   Добавить **IUnknown** указатель к классу и инициализируйте его, чтобы **NULL** в конструкторе.  
  
-   Переопределить `FinalConstruct` для создания агрегата.  
  
-   Используйте **IUnknown** указателя, определенных как параметр для [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) макрос.  
  
-   Переопределить `FinalRelease` для освобождения **IUnknown** указателя.  
  
##  <a name="finalrelease"></a>CComObjectRootEx::FinalRelease  
 Этот метод можно переопределить в производном классе позволяет выполнить очистку, необходимые для объекта.  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CComObjectRootEx::FinalRelease` не выполняет никаких действий.  
  
 Выполнение очистки в `FinalRelease` рекомендуется добавить код деструктор класса, поскольку объект по-прежнему полностью создан в той точке, с которой `FinalRelease` вызывается. Это позволяет осуществлять безопасный доступ к методы, предоставляемые наиболее производного класса. Это особенно важно для освобождения любые статистические объекты перед удалением.  
  
##  <a name="internaladdref"></a>CComObjectRootEx::InternalAddRef  
 Увеличивает счетчик ссылок объекта неагрегированные на 1.  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
### <a name="remarks"></a>Примечания  
 Если модель является многопоточным, **InterlockedIncrement** используется для предотвращения изменения счетчик ссылок в то же время более чем одним потоком.  
  
##  <a name="internalqueryinterface"></a>CComObjectRootEx::InternalQueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pThis`  
 [in] Указатель на объект, содержащий схему COM интерфейсы, предоставляемые в `QueryInterface`.  
  
 `pEntries`  
 [in] Указатель на **_ATL_INTMAP_ENTRY** структуру, которая обращается к карте доступные интерфейсы.  
  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, указанного в `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 `InternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM. Если объект является статистическим выражением, `InternalQueryInterface` не делегировать внешняя Неизвестная строка. Вы можете ввести интерфейсы в таблицу сопоставлений COM с помощью макроса [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) или одного из его вариантов.  
  
##  <a name="internalrelease"></a>CComObjectRootEx::InternalRelease  
 Уменьшает счетчик ссылок объекта неагрегированные на 1.  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В и не предназначенных для отладки и сборки для отладки, эта функция возвращает значение, которое могут быть полезны для диагностики и тестирования. Возвращаемое точное значение зависит от многих факторов, таких как операционную систему, используемую, может и не может, быть счетчик ссылок.  
  
### <a name="remarks"></a>Примечания  
 Если модель является многопоточным, **InterlockedDecrement** используется для предотвращения изменения счетчик ссылок в то же время более чем одним потоком.  
  
##  <a name="lock"></a>CComObjectRootEx::Lock  
 Если модель является многопоточным, этот метод вызывает функцию Win32 API [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), которого ожидает, пока поток может стать владельцем объект критической секции, полученного через закрытый элемент данных.  
  
```
void Lock();
```  
  
### <a name="remarks"></a>Примечания  
 По завершении выполнения защищенный код поток должен вызвать `Unlock` владения критической секции.  
  
 Если модель поток выполняется в одном потоке, этот метод не выполняет никаких действий.  
  
##  <a name="m_dwref"></a>CComObjectRootEx::m_dwRef  
 Часть объединение, которое обращается к памяти четыре байта.  
  
```
long m_dwRef;
```  
  
### <a name="remarks"></a>Примечания  
 С `m_pOuterUnknown`, часть объединения:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 Если объект не является статистическим выражением, счетчик ссылок недоступна для `AddRef` и **выпуска** хранится в `m_dwRef`. Если объект является статистическим выражением, указатель на внешняя Неизвестная строка сохраняется в [m_pOuterUnknown](#m_pouterunknown).  
  
##  <a name="m_pouterunknown"></a>CComObjectRootEx::m_pOuterUnknown  
 Часть объединение, которое обращается к памяти четыре байта.  
  
```
IUnknown*
    m_pOuterUnknown;
```     
  
### <a name="remarks"></a>Примечания  
 С `m_dwRef`, часть объединения:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 Если объект является статистическим выражением, указатель на внешняя Неизвестная строка сохраняется в `m_pOuterUnknown`. Если объект не является статистическим выражением, счетчик ссылок недоступна для `AddRef` и **выпуска** хранится в [m_dwRef](#m_dwref).  
  
##  <a name="objectmain"></a>CComObjectRootEx::ObjectMain  
 Для каждого класса, перечисленных в [схеме объекта](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f), эта функция вызывается один раз при инициализации модуля, и еще раз при его выполнение завершается.  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>Параметры  
 `bStarting`  
 [out] Значение равно **true** класса осуществляется инициализирован; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Значение `bStarting` параметр указывает, является ли модуль инициализируется или завершен. Реализация по умолчанию `ObjectMain` не выполняет никаких действий, но можно переопределить эту функцию в классе для инициализации или освобождения ресурсов, которые нужно выделить для класса. Обратите внимание, что `ObjectMain` вызывается перед запрашиваются все экземпляры класса.  
  
 `ObjectMain`вызывается из точки входа библиотеки DLL, поэтому ограничен тип операции, которые может выполнить функцию точки входа. Дополнительные сведения об этих ограничениях см. в разделе [библиотек DLL и Visual C++ поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md) и [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="outeraddref"></a>CComObjectRootEx::OuterAddRef  
 Увеличивает счетчик ссылок внешняя Неизвестная строка статистической обработки.  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="outerqueryinterface"></a>CComObjectRootEx::OuterQueryInterface  
 Извлекает косвенный указатель на запрошенный интерфейс.  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, указанного в `iid`, или **NULL** если статистическая схема не поддерживает интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
##  <a name="outerrelease"></a>CComObjectRootEx::OuterRelease  
 Уменьшает значение счетчика ссылок для внешняя Неизвестная строка статистической обработки.  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В неотладочных сборках всегда возвращает 0. В отладочных построениях возвращает значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="unlock"></a>CComObjectRootEx::Unlock  
 Если модель является многопоточным, этот метод вызывает функцию Win32 API [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), какие выпуски владельцем объекта критической секции, полученного через закрытый элемент данных.  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы получить права владельца, необходимо вызвать поток `Lock`. Каждый вызов `Lock` требуется соответствующий вызов `Unlock` для освобождения владения критической секции.  
  
 Если модель поток выполняется в одном потоке, этот метод не выполняет никаких действий.  
  
## <a name="see-also"></a>См. также  
 [Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
