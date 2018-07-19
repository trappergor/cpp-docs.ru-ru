---
title: Класс CComObjectRootEx | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55da0705027d6625d4140691b1b91912fb94c555
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027531"
---
# <a name="ccomobjectrootex-class"></a>Класс CComObjectRootEx
Этот класс предоставляет методы для обработки объекта управления счетчиками ссылок для объектов неагрегированные и объединены.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>Параметры  
 *ThreadModel*  
 Класс, методы которого реализовать нужный потоковой модели. Можно явно выбрать потоковую модель, задав *ThreadModel* для [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), или [ CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md). Вы можете принять потоковую модель сервера по умолчанию, задав *ThreadModel* для [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) или [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel).  

  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|Конструктор.|  
|[InternalAddRef](#internaladdref)|Увеличивает счетчик ссылок для объекта неагрегированные.|  
|[InternalRelease](#internalrelease)|Уменьшает счетчик ссылок для объекта неагрегированные.|  
|[Блокировки](#lock)|Если модель является многопоточным, получает права владельца объекта критической секции.|  
|[разблокировать](#unlock)|Если модель является многопоточным, освобождает владение объектом критический раздел.|  
  
### <a name="ccomobjectrootbase-methods"></a>Методы CComObjectRootBase  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|Переопределите в классе для выполнения любой инициализации, для вашего объекта.|  
|[FinalRelease](#finalrelease)|Переопределите в классе позволяет выполнить очистку для вашего объекта.|  
|[OuterAddRef](#outeraddref)|Увеличивает счетчик ссылок для объединенного объекта.|  
|[OuterQueryInterface](#outerqueryinterface)|Делегаты на внешний `IUnknown` из объединенного объекта.|  
|[OuterRelease](#outerrelease)|Уменьшает счетчик ссылок для объединенного объекта.|  
  
### <a name="static-functions"></a>Статические функции  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|Делегирует `IUnknown` неагрегированные объекта.|  
|[ObjectMain](#objectmain)|Вызывается в ходе инициализации модуля и завершения для производных классов, перечисленных в карте объектов.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|С помощью `m_pOuterUnknown`, являющийся частью объединения. Используется, если объект не является статистическим для хранения количество ссылок на `AddRef` и `Release`.|  
|[m_pOuterUnknown](#m_pouterunknown)|С помощью `m_dwRef`, являющийся частью объединения. Используется, если объект является статистическим для хранения указателя на внешняя Неизвестная строка.|  
  
## <a name="remarks"></a>Примечания  
 `CComObjectRootEx` обрабатывает объект управления счетчиками ссылок для объектов неагрегированные и объединены. Он содержит счетчик ссылок объекта, если объект не выполняется статистическая обработка и содержит указатель на внешняя Неизвестная строка, если объект выполняется статистическая обработка. Для агрегированных объектов `CComObjectRootEx` методы могут использоваться для обработки ошибки внутреннего объекта для создания, а также для защиты от удаления при выходе внутренние интерфейсы внешний объект или внутренний объект удаляется.  
  
 Класс, реализующий COM-сервера должен наследовать от `CComObjectRootEx` или [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 При определении класса указывает [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) макрос, ATL создает экземпляр класса `CComPolyObject<CYourClass>` при `IClassFactory::CreateInstance` вызывается. Во время создания проверяется значение внешняя Неизвестная строка. Если он равен NULL, `IUnknown` реализуется для объекта неагрегированные. Если внешняя Неизвестная строка не равно NULL, `IUnknown` реализуется для объединенного объекта.  
  
 Если ваш класс не содержит макрос DECLARE_POLY_AGGREGATABLE, ATL создает экземпляр класса `CAggComObject<CYourClass>` для агрегированных объектов или экземпляр `CComObject<CYourClass>` неагрегированные объектов.  
  
 Преимущество использования `CComPolyObject` — избежать обеих `CComAggObject` и `CComObject` в модуле для обработки вариантов, статистические и неагрегированные. Один `CComPolyObject` объект обрабатывает в обоих случаях. Таким образом только одна копия таблицы vtable и одна копия функции существуют в модуле. Если в таблице vtable имеет большой размер, это может значительно снизить размер вашего модуля. Тем не менее, если в таблице vtable невелик, с помощью `CComPolyObject` может привести к немного больший размер модуля, поскольку метод не оптимизирован для суммирования или неагрегированные объекта, так как `CComAggObject` и `CComObject`.  
  
 Если объект является статистическим, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) реализуется `CComAggObject` или `CComPolyObject`. Эти классы делегировать `QueryInterface`, `AddRef`, и `Release` вызовы `CComObjectRootEx` `OuterQueryInterface`, `OuterAddRef`, и `OuterRelease` переслать внешняя Неизвестная строка. Как правило, можно переопределить `CComObjectRootEx::FinalConstruct` в классе позволяет создать все объединенные объекты и переопределить `CComObjectRootEx::FinalRelease` чтобы освободить все статистическая обработка объектов.  
  
 Если объект не является агрегатом, `IUnknown` реализуется `CComObject` или `CComPolyObject`. В этом случае вызовы `QueryInterface`, `AddRef`, и `Release` делегируются `CComObjectRootEx` `InternalQueryInterface`, `InternalAddRef`, и `InternalRelease` для выполнения фактических операций.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="ccomobjectrootex"></a>  CComObjectRootEx::CComObjectRootEx  
 Конструктор инициализирует счетчик ссылок значение 0.  
  
```
CComObjectRootEx();
```  
  
##  <a name="finalconstruct"></a>  CComObjectRootEx::FinalConstruct  
 Этот метод можно переопределить в производном классе для выполнения любой инициализации, необходимые для объекта.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращать S_OK в случае успеха или один из стандартной ошибки значения HRESULT.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CComObjectRootEx::FinalConstruct` просто возвращает значение S_OK.  
  
 Преимущества для выполнения инициализации в `FinalConstruct` вместо того чтобы конструктор класса:  
  
-   Нельзя вернуть код состояния из конструктора, но может возвращать значение HRESULT с помощью параметра `FinalConstruct`в возвращаемое значение. Это возвращаемое значение объектов класса создаются с помощью стандартного класса фабрики, предоставляемые ATL, распространяется обратно клиенту COM, позволяя им предоставлены подробные сведения об ошибке.  
  
-   Нельзя вызывать виртуальные функции посредством механизма виртуальных функций из конструктора класса. Вызов виртуальной функции из конструктора класса приводит к статически разрешаемым вызову функции, как это определено в этот момент в иерархии наследования. Вызовов чистых виртуальных функций к ошибкам компоновщика.  
  
     Класс не является наиболее производный класс в иерархии наследования, он основывается на производном классе, предоставляемые ATL для обеспечения части функциональных возможностей. Есть шанс, что инициализации будет необходимо использовать возможности, предоставляемые этим классом, (Это безусловно относится когда объектов класса, необходимы для статистической обработки других объектов), но в конструктор в класс не имеет доступ к этим функциям. Код создания для класса выполняется до наиболее производного класса создается полностью.  
  
     Тем не менее `FinalConstruct` вызывается сразу после наиболее производный класс полностью созданы, что позволяет вызывать виртуальные функции и использовать реализацию подсчет ссылок, предоставляемые ATL.  
  
### <a name="example"></a>Пример  
 Как правило, переопределите этот метод в класс, производный от `CComObjectRootEx` для создания статистическая обработка объектов. Пример:  
  
 [!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 В случае сбоя создания может возвращать ошибку. Можно также использовать макрос [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) для защиты вашего внешнего объекта препятствия удалены, если во время создания внутреннего объекта агрегированные увеличивает счетчик ссылок, а затем уменьшает счетчик 0.  
  
 Вот типичный способ создания агрегата:  
  
-   Добавление `IUnknown` указатель на класс и инициализируйте его в значение NULL в конструктор.  
  
-   Переопределить `FinalConstruct` для создания агрегата.  
  
-   Используйте `IUnknown` указателя, определенных как параметр для [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) макрос.  
  
-   Переопределить `FinalRelease` для освобождения `IUnknown` указатель.  
  
##  <a name="finalrelease"></a>  CComObjectRootEx::FinalRelease  
 Этот метод можно переопределить в производном классе позволяет выполнять очистку, требуемую для объекта.  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CComObjectRootEx::FinalRelease` не выполняет никаких действий.  
  
 Выполнение очистки в `FinalRelease` рекомендуется добавить код деструктор класса, так как объект по-прежнему полностью создается в точке, в которой `FinalRelease` вызывается. Это позволяет безопасно обращаться к методам, предоставляемые наиболее производный класс. Это особенно важно для освобождения все объединенные объекты перед удалением.  
  
##  <a name="internaladdref"></a>  CComObjectRootEx::InternalAddRef  
 Увеличивает счетчик ссылок объекта неагрегированные на 1.  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
### <a name="remarks"></a>Примечания  
 Если модель является многопоточным, `InterlockedIncrement` используется для предотвращения изменения счетчик ссылок в то же время более одного потока.  
  
##  <a name="internalqueryinterface"></a>  CComObjectRootEx::InternalQueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 *pThis*  
 [in] Указатель на объект, содержащий карту COM интерфейсы, предоставляемые в `QueryInterface`.  
  
 *pEntries*  
 [in] Указатель на `_ATL_INTMAP_ENTRY` структуры, который обращается к карту доступных интерфейсов.  
  
 *IID*  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 *ppvObject*  
 [out] Указатель на указатель интерфейса, заданный в *iid*, или значение NULL, если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `InternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM. Если объект является статистическим, `InternalQueryInterface` не делегировать внешняя Неизвестная строка. Вы можете ввести интерфейсы в таблицу сопоставлений COM с помощью макроса [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) или одного из его вариантов.  
  
##  <a name="internalrelease"></a>  CComObjectRootEx::InternalRelease  
 Уменьшает счетчик ссылок объекта неагрегированные на 1.  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В обоих без отладки и отладочные сборки, эта функция возвращает значение, которое может быть полезно для диагностики или тестирования. Возвращаемое точное значение зависит от многих факторов, включая операционную систему, используемую, может и не имеете права, быть счетчик ссылок.  
  
### <a name="remarks"></a>Примечания  
 Если модель является многопоточным, `InterlockedDecrement` используется для предотвращения изменения счетчик ссылок в то же время более одного потока.  
  
##  <a name="lock"></a>  CComObjectRootEx::Lock  
 Если модель является многопоточным, этот метод вызывает функцию интерфейса API Win32 [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), которого ожидает, пока поток может стать владельцем объект критической секции, полученные через закрытый элемент данных.  
  
```
void Lock();
```  
  
### <a name="remarks"></a>Примечания  
 Когда защищенный код завершает работу, поток должен вызвать `Unlock` для освобождения владения критический раздел.  
  
 Если модель является однопоточным, этот метод не выполняет никаких действий.  
  
##  <a name="m_dwref"></a>  CComObjectRootEx::m_dwRef  
 Часть объединения, который обращается к четырех байтов памяти.  
  
```
long m_dwRef;
```  
  
### <a name="remarks"></a>Примечания  
 С помощью `m_pOuterUnknown`, являющийся частью объединения:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 Если объект не является статистическим, счетчик ссылок осуществляется `AddRef` и `Release` хранится в `m_dwRef`. Если объект является статистическим, указатель на внешняя Неизвестная строка сохраняется в [m_pOuterUnknown](#m_pouterunknown).  
  
##  <a name="m_pouterunknown"></a>  CComObjectRootEx::m_pOuterUnknown  
 Часть объединения, который обращается к четырех байтов памяти.  
  
```
IUnknown*
    m_pOuterUnknown;
```     
  
### <a name="remarks"></a>Примечания  
 С помощью `m_dwRef`, являющийся частью объединения:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 Если объект является статистическим, указатель на внешняя Неизвестная строка сохраняется в `m_pOuterUnknown`. Если объект не является статистическим, счетчик ссылок осуществляется `AddRef` и `Release` хранится в [m_dwRef](#m_dwref).  
  
##  <a name="objectmain"></a>  CComObjectRootEx::ObjectMain  
 Для каждого класса, перечисленного в [карте объектов](http://msdn.microsoft.com/b57619cc-534f-4b8f-bfd4-0c12f937202f), эта функция вызывается один раз при инициализации модуля, и еще раз при его выполнение завершается.  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>Параметры  
 *bStarting*  
 [out] Имеет значение TRUE, если инициализируемого класса; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Значение *bStarting* параметр указывает, является ли модуль инициализируется или завершен. Реализация по умолчанию `ObjectMain` не выполняет никаких действий, но эту функцию можно переопределить в классе для инициализации или очистки ресурсов, которые нужно выделить для класса. Обратите внимание, что `ObjectMain` вызывается перед запрашиваются все экземпляры класса.  
  
 `ObjectMain` вызывается из точки входа библиотеки DLL, поэтому тип операции, которая может выполнять функцию точки входа ограничен. Дополнительные сведения об этих ограничениях см. в разделе [библиотеки DLL и Visual C++ поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md) и [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="outeraddref"></a>  CComObjectRootEx::OuterAddRef  
 Увеличивает значение счетчика ссылок внешняя Неизвестная строка статистической обработки.  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="outerqueryinterface"></a>  CComObjectRootEx::OuterQueryInterface  
 Извлекает косвенный указатель на запрашиваемый интерфейс.  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 *IID*  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 *ppvObject*  
 [out] Указатель на указатель интерфейса, заданный в *iid*, или значение NULL, если статистическая обработка не поддерживает интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="outerrelease"></a>  CComObjectRootEx::OuterRelease  
 Уменьшает счетчик ссылок внешняя Неизвестная строка статистической обработки.  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В неотладочных сборках всегда возвращает 0. В отладочных сборках возвращает значение, которое может быть полезно для диагностики или тестирования.  
  
##  <a name="unlock"></a>  CComObjectRootEx::Unlock  
 Если модель является многопоточным, этот метод вызывает функцию интерфейса API Win32 [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), какие выпуски владение объект критической секции, полученные через закрытый элемент данных.  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы получить права владельца, необходимо вызвать поток `Lock`. Каждый вызов `Lock` требует соответствующего вызова `Unlock` для освобождения владения критический раздел.  
  
 Если модель является однопоточным, этот метод не выполняет никаких действий.  
  
## <a name="see-also"></a>См. также  
 [Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
