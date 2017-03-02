---
title: "Класс CComObjectRootEx | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComObjectRootEx
- ATL::CComObjectRootEx<ThreadModel>
- CComObjectRootEx
- ATL::CComObjectRootEx
- ATL.CComObjectRootEx<ThreadModel>
dev_langs:
- C++
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f3a6d26ddb4f612824f959ca3046531dc3bbf2a9
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectrootex-class"></a>Класс CComObjectRootEx
Этот класс предоставляет методы для обработки объекта управления счетчиками ссылок для объектов неагрегированные и объединены.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>Параметры  
 `ThreadModel`  
 Класс, методы которого реализации требуемой потоковой модели. Можно явно выбрать потоковую модель, задав `ThreadModel` для [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), или [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md). Можно принять модель потоков сервера по умолчанию, задав `ThreadModel` для [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) или [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel).  

  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|Конструктор.|  
|[InternalAddRef](#internaladdref)|Увеличивает значение счетчика ссылок для неагрегированные объекта.|  
|[InternalRelease](#internalrelease)|Уменьшает счетчик ссылок для неагрегированные объекта.|  
|[Блокировка](#lock)|Если модель потоков многопоточного, получает права владельца объекта критической секции.|  
|[Разблокировать](#unlock)|Если модель потоков многопоточного, освобождает владение объект критической секции.|  
  
### <a name="ccomobjectrootbase-methods"></a>Методы CComObjectRootBase  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|Переопределить в классе для выполнения любой инициализации, необходимые для вашего объекта.|  
|[FinalRelease](#finalrelease)|Переопределить в классе, чтобы выполнить очистку для вашего объекта.|  
|[OuterAddRef](#outeraddref)|Увеличивает значение счетчика ссылок для вычисляемого объекта.|  
|[OuterQueryInterface](#outerqueryinterface)|Делегаты для внешнего **IUnknown** статистические объекта.|  
|[OuterRelease](#outerrelease)|Уменьшает счетчик ссылок для вычисляемого объекта.|  
  
### <a name="static-functions"></a>Статические функции  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|Делегирует **IUnknown** неагрегированные объекта.|  
|[ObjectMain](#objectmain)|Вызываемый при инициализации модуля и завершения для производных классов, перечисленных в карте объектов.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|С `m_pOuterUnknown`, часть объединения. Используется, если объект не является агрегатом для хранения числа ссылок `AddRef` и **версии**.|  
|[m_pOuterUnknown](#m_pouterunknown)|С `m_dwRef`, часть объединения. Используется, когда объект собираются для хранения указателя внешняя Неизвестная.|  
  
## <a name="remarks"></a>Примечания  
 `CComObjectRootEx`обрабатывает объект управления счетчиками ссылок для объектов неагрегированные и объединены. Он содержит счетчик ссылок объекта, если объект не выполняется статистическая обработка и удерживает указатель внешняя Неизвестная строка, если статистическая обработка объекта. Для статистических объектов `CComObjectRootEx` методы могут использоваться для обработки сбоя внутреннего объекта для создания, а также для защиты внешний объект от удаления при выпуске внутреннего интерфейсов или внутренний объект удаляется.  
  
 Класс, реализующий COM-сервер должен наследовать из `CComObjectRootEx` или [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 Если определение класса указывает [DECLARE_POLY_AGGREGATABLE](http://msdn.microsoft.com/library/7569e738-cfbc-4404-ba1d-78dcefa3bdb3) макрос, ATL создает экземпляр **CComPolyObject\<окне отслеживания TRACE появляется настроек** при **IClassFactory::CreateInstance** вызывается. Во время создания проверяется значение внешняя Неизвестная строка. Если это **NULL**, **IUnknown** реализуется неагрегированные объекта. Если внешняя Неизвестная не **NULL**, **IUnknown** реализуется для вычисляемого объекта.  
  
 Если не указать класс `DECLARE_POLY_AGGREGATABLE` макрос, ATL создает экземпляр **CAggComObject\<окне отслеживания TRACE появляется настроек** статистические объекты или экземпляр **CComObject\<окне отслеживания TRACE появляется настроек** неагрегированные объектов.  
  
 Преимущество использования `CComPolyObject` — избежать необходимости оба `CComAggObject` и `CComObject` в модуле для обработки случаев, статистические и нестатистические. Один `CComPolyObject` объект обрабатывает в обоих случаях. Таким образом только одна копия виртуальной таблице и одну копию функции существуют в модуле. При большом вашей vtable это значительно уменьшить размер вашего модуля. Однако при небольших вашей виртуальной таблицы с помощью `CComPolyObject` может привести к немного больший размер модуля, поскольку он не оптимизирован для суммирования или неагрегированные объекта, как `CComAggObject` и `CComObject`.  
  
 Если объект является статистическим выражением, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) реализуется `CComAggObject` или `CComPolyObject`. Делегировать эти классы `QueryInterface`, `AddRef`, и **выпуска** вызовы `CComObjectRootEx` `OuterQueryInterface`, `OuterAddRef`, и `OuterRelease` для пересылки внешняя Неизвестная строка. Как правило, необходимо переопределить `CComObjectRootEx::FinalConstruct` в класс и создать статистические объекты и Переопределите `CComObjectRootEx::FinalRelease` чтобы освободить все объединяемых объектов.  
  
 Если объект не является агрегатом, **IUnknown** реализуется `CComObject` или `CComPolyObject`. В этом случае вызовы `QueryInterface`, `AddRef`, и **выпуска** делегируются `CComObjectRootEx` `InternalQueryInterface`, `InternalAddRef`, и `InternalRelease` для выполнения фактических операций.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-nameccomobjectrootexa--ccomobjectrootexccomobjectrootex"></a><a name="ccomobjectrootex"></a>CComObjectRootEx::CComObjectRootEx  
 Конструктор инициализирует счетчик ссылок на 0.  
  
```
CComObjectRootEx();
```  
  
##  <a name="a-namefinalconstructa--ccomobjectrootexfinalconstruct"></a><a name="finalconstruct"></a>CComObjectRootEx::FinalConstruct  
 Этот метод можно переопределить в производном классе для выполнения любой инициализации, необходимые для объекта.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вернуть `S_OK` успех или одним из стандартной ошибки `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CComObjectRootEx::FinalConstruct` просто возвращает `S_OK`.  
  
 Преимущества для выполнения инициализации в `FinalConstruct` вместо того чтобы конструктор класса:  
  
-   Конструктор не может вернуть код состояния, он может возвращать `HRESULT` с помощью параметра `FinalConstruct`в возвращаемое значение. Объекты этого класса создаются с помощью стандартного класса фабрики, предоставляемые ATL, это свойство возвращает значение распространяется с клиентом COM, что позволяет предоставить подробные сведения об ошибке.  
  
-   Нельзя вызывать виртуальные функции посредством механизма виртуальных функций из конструктора класса. Вызов виртуальной функции из конструктора класса приводит к статически разрешаемые вызова функции, как это определено в этот момент в иерархии наследования. Вызовы чистые виртуальные функции приведет к ошибках компоновщика.  
  
     Класс не является наиболее производного класса в иерархии наследования, он основан на производном классе, предоставляемые ATL для обеспечения части функциональных возможностей. Есть шанс, что ваш инициализации необходимо использовать возможности, предоставляемые этим классом (Это определенно значение true, когда нужно объединить другие объекты класса), но конструктор в класс не имеет возможности доступа к ним. Код конструкции для класса выполняется до наиболее производного класса создается полностью.  
  
     Однако `FinalConstruct` вызывается сразу после наиболее производный класс полностью созданы, что позволяет вызывать виртуальные функции и использовать реализацию подсчет ссылок, предоставляемые ATL.  
  
### <a name="example"></a>Пример  
 Как правило, переопределите этот метод в классе, производном от `CComObjectRootEx` для создания объединяемых объектов. Пример:  
  
 [!code-cpp[NVC_ATL_COM&#40;](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 В случае сбоя создания может возвращать ошибку. Можно также использовать макрос [DECLARE_PROTECT_FINAL_CONSTRUCT](http://msdn.microsoft.com/library/2d2e5ddc-057a-43ca-87c8-d3477a8193a0) для защиты вашего внешнего объекта дают удалены, если при создании внутреннего объекта статистические увеличивает счетчик ссылок, а затем уменьшает счетчик 0.  
  
 Вот типичный способ создания статистического выражения:  
  
-   Добавить **IUnknown** указатель к классу объекта и инициализируйте ее значением **NULL** в конструкторе.  
  
-   Переопределение `FinalConstruct` для создания агрегата.  
  
-   Используйте **IUnknown** указателя, определенных как параметр для [COM_INTERFACE_ENTRY_AGGREGATE](http://msdn.microsoft.com/library/c671fa40-a57b-4797-ae88-c9762dabd4dc) макрос.  
  
-   Переопределение `FinalRelease` для освобождения **IUnknown** указателя.  
  
##  <a name="a-namefinalreleasea--ccomobjectrootexfinalrelease"></a><a name="finalrelease"></a>CComObjectRootEx::FinalRelease  
 Этот метод можно переопределить в производном классе позволяет выполнить очистку для объекта.  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CComObjectRootEx::FinalRelease` не выполняет никаких действий.  
  
 Выполнение очистки в `FinalRelease` рекомендуется добавить код деструктор класса, поскольку объект по-прежнему полностью создается в точке пересечения `FinalRelease` вызывается. Это позволяет осуществлять безопасный доступ к методы, предоставленные наиболее производного класса. Это особенно важно для освобождения любые статистические объекты перед удалением.  
  
##  <a name="a-nameinternaladdrefa--ccomobjectrootexinternaladdref"></a><a name="internaladdref"></a>CComObjectRootEx::InternalAddRef  
 Увеличивает счетчик ссылок объекта неагрегированные на 1.  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
### <a name="remarks"></a>Примечания  
 Если модель является многопоточным, **InterlockedIncrement** используется для предотвращения изменения счетчик ссылок в то же время более чем одним потоком.  
  
##  <a name="a-nameinternalqueryinterfacea--ccomobjectrootexinternalqueryinterface"></a><a name="internalqueryinterface"></a>CComObjectRootEx::InternalQueryInterface  
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
 [in] Указатель на объект, содержащий сопоставления COM из интерфейсов, предоставляемых `QueryInterface`.  
  
 `pEntries`  
 [in] Указатель на **_ATL_INTMAP_ENTRY** структуры, который обращается к карте доступные интерфейсы.  
  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, заданный в `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 `InternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM. Если объект является статистическим выражением, `InternalQueryInterface` не делегировать внешняя Неизвестная строка. Вы можете ввести интерфейсы в таблицу сопоставлений COM с помощью макроса [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) или одного из его вариантов.  
  
##  <a name="a-nameinternalreleasea--ccomobjectrootexinternalrelease"></a><a name="internalrelease"></a>CComObjectRootEx::InternalRelease  
 Уменьшает счетчик ссылок объекта неагрегированные на 1.  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В обоих неотладочные и отладочные построения, эта функция возвращает значение, которое может быть полезно для диагностики и тестирования. Возвращаемое точное значение зависит от многих факторов, таких как операционную систему, используемую, может и не может, быть счетчик ссылок.  
  
### <a name="remarks"></a>Примечания  
 Если модель является многопоточным, **InterlockedDecrement** используется для предотвращения изменения счетчик ссылок в то же время более чем одним потоком.  
  
##  <a name="a-namelocka--ccomobjectrootexlock"></a><a name="lock"></a>CComObjectRootEx::Lock  
 Если модель потоков многопоточного, этот метод вызывает функцию Win32 API [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), который ожидает, пока поток может стать владельцем объект критической секции, полученного через закрытый член данных.  
  
```
void Lock();
```  
  
### <a name="remarks"></a>Примечания  
 По завершении выполнения защищенный код поток должен вызвать `Unlock` владения критический раздел.  
  
 Если модель потоков в одном потоке, этот метод не выполняет никаких действий.  
  
##  <a name="a-namemdwrefa--ccomobjectrootexmdwref"></a><a name="m_dwref"></a>CComObjectRootEx::m_dwRef  
 Часть объединения, который обращается к четыре байта памяти.  
  
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
  
 Если объект не является агрегатом, счетчик ссылок доступ `AddRef` и **выпуска** хранится в `m_dwRef`. Если объект является агрегатом, указатель на внешняя Неизвестная строка хранится в [m_pOuterUnknown](#m_pouterunknown).  
  
##  <a name="a-namempouterunknowna--ccomobjectrootexmpouterunknown"></a><a name="m_pouterunknown"></a>CComObjectRootEx::m_pOuterUnknown  
 Часть объединения, который обращается к четыре байта памяти.  
  
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
  
 Если объект является агрегатом, указатель внешняя Неизвестная строка сохраняется в `m_pOuterUnknown`. Если объект не является агрегатом, счетчик ссылок доступ `AddRef` и **выпуска** хранится в [m_dwRef](#m_dwref).  
  
##  <a name="a-nameobjectmaina--ccomobjectrootexobjectmain"></a><a name="objectmain"></a>CComObjectRootEx::ObjectMain  
 Для каждого класса, перечисленных в [карту объектов](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f), эта функция вызывается один раз при инициализации модуля и снова при его завершении.  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>Параметры  
 `bStarting`  
 [out] Значение **true** класса осуществляется инициализирован; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Значение `bStarting` параметр указывает, является ли модуль инициализируется или завершен. Реализация по умолчанию `ObjectMain` не выполняет никаких действий, но можно переопределить эту функцию в классе инициализации или очистки ресурсов, которые нужно выделить для класса. Обратите внимание, что `ObjectMain` вызывается до того, как все экземпляры класса.  
  
 `ObjectMain`вызывается из точки входа библиотеки DLL, поэтому ограниченный тип операции, которые могут выполнять функции точки входа. Дополнительные сведения об этих ограничениях см. в разделе [поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md) и [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#41;](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="a-nameouteraddrefa--ccomobjectrootexouteraddref"></a><a name="outeraddref"></a>CComObjectRootEx::OuterAddRef  
 Увеличивает счетчик ссылок внешняя Неизвестная статистической обработки.  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="a-nameouterqueryinterfacea--ccomobjectrootexouterqueryinterface"></a><a name="outerqueryinterface"></a>CComObjectRootEx::OuterQueryInterface  
 Извлекает косвенный указатель на запрошенный интерфейс.  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, заданный в `iid`, или **NULL** если статистическая схема не поддерживает интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
##  <a name="a-nameouterreleasea--ccomobjectrootexouterrelease"></a><a name="outerrelease"></a>CComObjectRootEx::OuterRelease  
 Уменьшает значение счетчика ссылок для внешняя Неизвестная статистической обработки.  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В сборках неотладочные всегда возвращает значение 0. В отладочных построениях возвращает значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="a-nameunlocka--ccomobjectrootexunlock"></a><a name="unlock"></a>CComObjectRootEx::Unlock  
 Если модель потоков многопоточного, этот метод вызывает функцию Win32 API [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), какие выпуски владельцем объекта критической секции, полученные через закрытый член данных.  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Для получения прав на владение, поток должен вызвать `Lock`. Каждый вызов `Lock` требует соответствующего вызова `Unlock` владения критический раздел.  
  
 Если модель потоков в одном потоке, этот метод не выполняет никаких действий.  
  
## <a name="see-also"></a>См. также  
 [Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

