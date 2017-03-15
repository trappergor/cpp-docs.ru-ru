---
title: "Статистическая обработка и макросов фабрики класса | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
caps.latest.revision: 17
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4509f7be36e45cf96a938e30ec0f82ec0c9836b5
ms.lasthandoff: 02/24/2017

---
# <a name="aggregation-and-class-factory-macros"></a>Статистическая обработка и макросов фабрики классов
Эти макросы обеспечивают способы управления статистической обработки и объявления фабрики классов.  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Объявляет, что объект может быть статистически (по умолчанию).|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Объявляет класс фабрики для [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), фабрика классов ATL по умолчанию.|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Объявляет объект фабрики класса быть фабрики класса.|  
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) быть фабрики класса.|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Объявляет [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) быть фабрики класса.|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Объявляет [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) быть фабрики класса.|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Объявляет виртуальный `GetControllingUnknown` функции.|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Объявляет, что невозможно выполнить статистическую обработку объекта.|  
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Объявляет, что ваш объект должен быть агрегатом.|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Проверяет значение внешняя Неизвестная и объявляет объект статистическую обработку или невозможна, соответствующим образом.|  
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Внешний объект защищает от удаления при создании внутреннего объекта.|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|Указывает **Просмотр СОСТОЯНИЯ** флаги для контейнера.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
   
##  <a name="a-namedeclareaggregatablea--declareaggregatable"></a><a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE  
 Указывает, что объект может быть агрегатом.  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса, который был определен как статистическую обработку.  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит макрос, чтобы указать модель статистической обработки по умолчанию. Чтобы переопределить это поведение по умолчанию, укажите [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) или [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) макрос в определении класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="a-namedeclareclassfactorya--declareclassfactory"></a><a name="declare_classfactory"></a>DECLARE_CLASSFACTORY  
 Объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) использует этот макрос для объявления фабрики класса по умолчанию для объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#55;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="a-nameccomclassfactoryclassa--ccomclassfactory-class"></a><a name="ccomclassfactory_class"></a>Класс CComClassFactory  
 Этот класс реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейса.  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Примечания  
 `CComClassFactory`реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейс, который содержит методы для создания объекта для определенного идентификатора CLSID, а также блокировки фабрики классов в память позволяет более быстро создавать новые объекты. **IClassFactory** должен быть реализован для каждого класса, регистрация в системном реестре и который назначить CLSID.  
  
 Объекты ATL обычно получения фабрики класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` как фабрика класса по умолчанию. Чтобы переопределить это поведение по умолчанию, укажите одно из `DECLARE_CLASSFACTORY` *XXX* макросы в определении класса. Например [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) макрос использует указанный класс фабрики класса:  
  
 [!code-cpp[NVC_ATL_COM №&8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 Указывает, что выше определения класса **CMyClassFactory** будет использоваться как фабрика класса объекта по умолчанию. **CMyClassFactory** должен быть производным от `CComClassFactory` и Переопределите `CreateInstance`.  
  
 Библиотека ATL предоставляет три другие макросы, объявляющие фабрики класса:  
  
- [DECLARE_CLASSFACTORY2](#declare_classfactory2) использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), который контролирует создание с помощью лицензии.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) использует [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) использует [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), который создает один [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объекта.  
  
##  <a name="a-namedeclareclassfactoryexa--declareclassfactoryex"></a><a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX  
 Объявляет `cf` быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY_EX( cf )
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 [in] Имя класса, реализующего объект фабрики класса.  
  
### <a name="remarks"></a>Примечания  
 `cf` Параметр должен быть производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и Переопределите `CreateInstance` метод.  
  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) включает [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает `CComClassFactory` как фабрика класса по умолчанию. Тем не менее, в том числе `DECLARE_CLASSFACTORY_EX` макрос в определении класса объекта, можно переопределить поведение по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM №&8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="a-namedeclareclassfactory2a--declareclassfactory2"></a><a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2  
 Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>Параметры  
 *: лицензионное соглашение*  
 [in] Класс, реализующий `VerifyLicenseKey`, `GetLicenseKey`, и `IsLicenseValid`.  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) включает [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Тем не менее, в том числе `DECLARE_CLASSFACTORY2` макрос в определении класса объекта, можно переопределить поведение по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
##  <a name="a-nameccomclassfactory2classa--ccomclassfactory2-class"></a><a name="ccomclassfactory2_class"></a>Класс CComClassFactory2  
 Этот класс реализует [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) интерфейса.  
  
```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```    
  
### <a name="parameters"></a>Параметры  
 *лицензии*  
 Класс, реализующий следующие статические функции:  
  
- **VerifyLicenseKey статические BOOL (BSTR** `bstr` **);**  
  
- **GetLicenseKey статические BOOL (DWORD** `dwReserved` **, BSTR\* ** `pBstr` **);**  
  
- **статические (BOOL IsLicenseValid);**  
  
### <a name="remarks"></a>Примечания  
 `CComClassFactory2`реализует [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) интерфейс, который представляет собой расширение для [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** элементы управления объекта создание с помощью лицензии. Класс фабрики выполнение лицензированного компьютера можно предоставить ключ лицензии во время выполнения. Этот ключ лицензии позволяет приложению создавать экземпляры объектов, при полной машины лицензии не существует.  
  
 Объекты ATL обычно получения фабрики класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Для использования `CComClassFactory2`, укажите [DECLARE_CLASSFACTORY2](#declare_classfactory2) макрос в определении класса объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 **CMyLicense**, параметр шаблона `CComClassFactory2`, необходимо реализовать статические функции `VerifyLicenseKey`, `GetLicenseKey`, и `IsLicenseValid`. Ниже приведен пример класса простые лицензии:  
  
 [!code-cpp[NVC_ATL_COM&#3;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2`наследует от **CComClassFactory2Base** и *лицензий*. **CComClassFactory2Base**, в свою очередь, является производным от **IClassFactory2** и **CComObjectRootEx\< CComGlobalsThreadModel настроек**.  
  
##  <a name="a-namedeclareclassfactoryautothreada--declareclassfactoryautothread"></a><a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD  
 Объявляет [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) включает [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Тем не менее, в том числе `DECLARE_CLASSFACTORY_AUTO_THREAD` макрос в определении класса объекта, можно переопределить поведение по умолчанию.  
  
 При создании объектов в нескольких подразделениях (на сервере вне процесса), добавление `DECLARE_CLASSFACTORY_AUTO_THREAD` к классу.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM №&9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="a-nameccomclassfactoryautothreadclassa--ccomclassfactoryautothread-class"></a><a name="ccomclassfactoryautothread_class"></a>Класс CComClassFactoryAutoThread  
 Этот класс реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейса и позволяет создавать в нескольких подразделениях объекты.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Примечания  
 `CComClassFactoryAutoThread`Аналогично [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), но позволяет создавать в нескольких подразделениях объекты. Чтобы использовать преимущества этой поддержки, являются производными модуль exe-ФАЙЛ из [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Объекты ATL обычно получения фабрики класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Для использования `CComClassFactoryAutoThread`, укажите [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) макрос в определении класса объекта. Например:  
  
 [!code-cpp[NVC_ATL_COM №&9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="a-namedeclareclassfactorysingletona--declareclassfactorysingleton"></a><a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON  
 Объявляет [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>Параметры  
 `obj`  
 [in] Имя класса объекта.  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) включает [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Тем не менее, в том числе `DECLARE_CLASSFACTORY_SINGLETON` макрос в определении класса объекта, можно переопределить поведение по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="a-nameccomclassfactorysingletonclassa--ccomclassfactorysingleton-class"></a><a name="ccomclassfactorysingleton_class"></a>Класс CComClassFactorySingleton  
 Этот класс является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Класс.  
  
 `CComClassFactorySingleton`является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта. Каждый вызов `CreateInstance` метод просто запрашивает этот объект для указателя на интерфейс.  
  
### <a name="remarks"></a>Примечания  
 Объекты ATL обычно получения фабрики класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` как фабрика класса по умолчанию. Для использования `CComClassFactorySingleton`, укажите [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) макрос в определении класса объекта. Например:  
  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="a-namedeclaregetcontrollingunknowna--declaregetcontrollingunknown"></a><a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN  
 Объявляет виртуальную функцию `GetControllingUnknown`.  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>Примечания  
 Добавьте этот макрос для объекта, если вы получаете сообщение об ошибке компилятора `GetControllingUnknown` не определен (например, в **CComAggregateCreator**).  
  
##  <a name="a-namedeclarenotaggregatablea--declarenotaggregatable"></a><a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE  
 Указывает, что невозможно выполнить статистическую обработку объекта.  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса объекта, который был определен как невозможна.  
  
### <a name="remarks"></a>Примечания  
 `DECLARE_NOT_AGGREGATABLE`вызывает `CreateInstance` будут возвращать ошибку ( **CLASS_E_NOAGGREGATION**) при попытке для статистической обработки на объект.  
  
 По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит [DECLARE_AGGREGATABLE](#declare_aggregatable) макросом, который указывает, что объект может быть агрегатом. Чтобы переопределить это поведение по умолчанию, включите `DECLARE_NOT_AGGREGATABLE` в определении класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="a-namedeclareonlyaggregatablea--declareonlyaggregatable"></a><a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE  
 Указывает, что ваш объект должен быть агрегатом.  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса объекта, который был определен как только статистическую обработку.  
  
### <a name="remarks"></a>Примечания  
 `DECLARE_ONLY_AGGREGATABLE`вызывает ошибку ( **E_FAIL**) при попытке **CoCreate** объект как неагрегированные объект.  
  
 По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит [DECLARE_AGGREGATABLE](#declare_aggregatable) макросом, который указывает, что объект может быть агрегатом. Чтобы переопределить это поведение по умолчанию, включите `DECLARE_ONLY_AGGREGATABLE` в определении класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#125;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="a-namedeclarepolyaggregatablea--declarepolyaggregatable"></a><a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE  
 Указывает, что экземпляр **CComPolyObject \< ** *x* ** > ** при создании объекта.  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса объекта, который был определен как статистическую обработку или невозможна.  
  
### <a name="remarks"></a>Примечания  
 Во время создания проверяется значение внешняя Неизвестная строка. Если это **NULL**, **IUnknown** реализуется неагрегированные объекта. Если внешняя Неизвестная не **NULL**, **IUnknown** реализуется для вычисляемого объекта.  
  
 Преимущество использования `DECLARE_POLY_AGGREGATABLE` — избежать необходимости оба `CComAggObject` и `CComObject` в модуле для обработки случаев, статистические и нестатистические. Один `CComPolyObject` объект обрабатывает в обоих случаях. Это означает, что существуют только одну копию таблицы vtable и одну копию функций в модуле. При большом вашей vtable это значительно уменьшить размер вашего модуля. Однако при небольших вашей виртуальной таблицы с помощью `CComPolyObject` может привести к немного больший размер модуля, поскольку он не оптимизирован для суммирования или неагрегированные объекта, как `CComAggObject` и `CComObject`.  
  
 `DECLARE_POLY_AGGREGATABLE` Макрос автоматически объявляются в объекте при использовании мастер элементов управления ATL, чтобы создать полный доступ.  
  
##  <a name="a-namedeclareprotectfinalconstructa--declareprotectfinalconstruct"></a><a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT  

 Защищает от удаляется, если объект (во время [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) внутреннего объекта агрегированные увеличивает счетчик ссылок, а затем уменьшает число 0.  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="a-namedeclareviewstatusa--declareviewstatus"></a><a name="declare_view_status"></a>DECLARE_VIEW_STATUS  
 Поместите этот макрос в класс элемента управления элемента управления ATL ActiveX для указания **Просмотр СОСТОЯНИЯ** флаги для контейнера.  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>Параметры  
 `statusFlags`  
 [in] **Просмотр СОСТОЯНИЯ** флаги. В разделе [Просмотр СОСТОЯНИЯ](http://msdn.microsoft.com/library/windows/desktop/ms687201) список флагов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#126;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)

