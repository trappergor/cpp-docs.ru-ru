---
title: "Агрегирование и макросы фабрики класса | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ce4021ee01052f1c830bba5ad1932898fd84b281
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="aggregation-and-class-factory-macros"></a>Агрегирование и макросы фабрики класса
Эти макросы обеспечивают способы управления статистической обработки и объявления фабрик классов.  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Объявляет, что объект может быть статистически (по умолчанию).|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Объявляет фабрики класса, чтобы быть [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), фабрика класса ATL по умолчанию.|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Объявляет объект фабрики вашего класса для фабрики класса.|  
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) быть фабрики класса.|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Объявляет [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) быть фабрики класса.|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Объявляет [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) быть фабрики класса.|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Объявляет виртуальный `GetControllingUnknown` функции.|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Объявляет, что невозможно выполнить статистическую обработку объекта.|  
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Объявляет, что ваш объект должен быть агрегатом.|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Проверяет значение внешняя Неизвестная строка и объявляет объект статистическую обработку или невозможна, соответствующим образом.|  
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Внешний объект защищает от удаления во время создания внутреннего объекта.|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|Указывает **Просмотр СОСТОЯНИЯ** флаги в контейнер.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
   
##  <a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE  
 Указывает, что объект может быть статистически вычислена.  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса, который был определен как статистическую обработку.  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит макрос, чтобы указать модель статистической обработки по умолчанию. Чтобы переопределить это поведение по умолчанию, укажите [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) или [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) макроса в определении класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_classfactory"></a>DECLARE_CLASSFACTORY  
 Объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) использует этот макрос для объявления фабрики класса по умолчанию для объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="ccomclassfactory_class"></a>Класс CComClassFactory  
 Этот класс реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейса.  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Примечания  
 `CComClassFactory`реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейс, который содержит методы для создания объекта конкретного CLSID, а также блокировки фабрики класса в памяти и позволяют быстрее создавать новые объекты. **IClassFactory** должен быть реализован для каждого класса, зарегистрированный в системном реестре и которые присваивают CLSID.  
  
 Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс содержит макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` как фабрика класса по умолчанию. Чтобы переопределить это поведение по умолчанию, укажите один из `DECLARE_CLASSFACTORY` *XXX* макросы в определении класса. Например [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) макрос использует указанный класс фабрики класса:  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 Указывает, что выше определения класса **CMyClassFactory** будет использоваться в качестве объекта фабрики класса по умолчанию. **CMyClassFactory** должен быть производным от `CComClassFactory` и Переопределите `CreateInstance`.  
  
 Библиотека ATL предоставляет три макроса, которые объявлять фабрики класса:  
  
- [DECLARE_CLASSFACTORY2](#declare_classfactory2) использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), какие элементы управления создавать с помощью лицензии.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) использует [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) использует [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), который создает один [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объекта.  
  
##  <a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX  
 Объявляет `cf` быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY_EX( cf )
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 [in] Имя класса, который реализует объект фабрики класса.  
  
### <a name="remarks"></a>Примечания  
 `cf` Параметр должен быть производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и Переопределите `CreateInstance` метод.  
  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) включает [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает `CComClassFactory` как фабрика класса по умолчанию. Тем не менее, включив `DECLARE_CLASSFACTORY_EX` макроса в определении класса объекта, можно переопределить поведение по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2  
 Объявляет [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>Параметры  
 *: лицензионное соглашение*  
 [in] Класс, реализующий `VerifyLicenseKey`, `GetLicenseKey`, и `IsLicenseValid`.  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) включает [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Тем не менее, включив `DECLARE_CLASSFACTORY2` макроса в определении класса объекта, можно переопределить поведение по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
##  <a name="ccomclassfactory2_class"></a>Класс CComClassFactory2  
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
  
- **статические VerifyLicenseKey BOOL (BSTR** `bstr` **);**  
  
- **GetLicenseKey статические BOOL (DWORD** `dwReserved` **, BSTR\***  `pBstr` **);**  
  
- **статические BOOL IsLicenseValid ();**  
  
### <a name="remarks"></a>Примечания  
 `CComClassFactory2`реализует [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) интерфейс, который представляет собой расширение для [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** создавать с помощью лицензии объекта элементов управления. Выполнения фабрики класса лицензированных компьютера можно ввести ключ лицензии во время выполнения. Это лицензионный ключ позволяет приложению для создания экземпляров объектов, при полной машины лицензии не существует.  
  
 Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс содержит макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Для использования `CComClassFactory2`, укажите [DECLARE_CLASSFACTORY2](#declare_classfactory2) макроса в определении класса объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 **CMyLicense**, параметр шаблона `CComClassFactory2`, необходимо реализовать статические функции `VerifyLicenseKey`, `GetLicenseKey`, и `IsLicenseValid`. Ниже приведен пример класса простого лицензии:  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2`наследует от **CComClassFactory2Base** и *лицензии*. **CComClassFactory2Base**, в свою очередь, является производным от **IClassFactory2** и **CComObjectRootEx\< CComGlobalsThreadModel >**.  
  
##  <a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD  
 Объявляет [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) включает [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Тем не менее, включив `DECLARE_CLASSFACTORY_AUTO_THREAD` макроса в определении класса объекта, можно переопределить поведение по умолчанию.  
  
 При создании объектов в нескольких подразделениях (в out процесса сервера), добавление `DECLARE_CLASSFACTORY_AUTO_THREAD` к классу.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="ccomclassfactoryautothread_class"></a>Класс CComClassFactoryAutoThread  
 Этот класс реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейса и позволяет создавать в нескольких подразделениях объекты.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Примечания  
 `CComClassFactoryAutoThread`Аналогично [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), но позволяет объектам должен быть создан в нескольких подразделениях. Чтобы воспользоваться преимуществами этой поддержки, являются производными модуля exe-ФАЙЛ из [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс содержит макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Для использования `CComClassFactoryAutoThread`, укажите [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) макроса в определении класса объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON  
 Объявляет [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) быть фабрики класса.  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>Параметры  
 `obj`  
 [in] Имя класса объекта.  
  
### <a name="remarks"></a>Примечания  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) включает [DECLARE_CLASSFACTORY](#declare_classfactory) макросом, который указывает [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Тем не менее, включив `DECLARE_CLASSFACTORY_SINGLETON` макроса в определении класса объекта, можно переопределить поведение по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="ccomclassfactorysingleton_class"></a>Класс CComClassFactorySingleton  
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
 Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс содержит макрос [DECLARE_CLASSFACTORY](#declare_classfactory), который объявляет `CComClassFactory` как фабрика класса по умолчанию. Для использования `CComClassFactorySingleton`, укажите [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) макроса в определении класса объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN  
 Объявляет виртуальную функцию `GetControllingUnknown`.  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>Примечания  
 Добавьте этот макрос в объект, если вы получаете сообщение об ошибке компилятора `GetControllingUnknown` не определен (например, в **CComAggregateCreator**).  
  
##  <a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE  
 Указывает, что невозможно выполнить статистическую обработку объекта.  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса объекта, который был определен как невозможна.  
  
### <a name="remarks"></a>Примечания  
 `DECLARE_NOT_AGGREGATABLE`вызывает `CreateInstance` будут возвращать ошибку ( **CLASS_E_NOAGGREGATION**) при попытке для статистической обработки на объект.  
  
 По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит [DECLARE_AGGREGATABLE](#declare_aggregatable) макросом, который указывает, что объект может быть статистически вычислена. Чтобы переопределить это поведение по умолчанию, включите `DECLARE_NOT_AGGREGATABLE` в определении класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE  
 Указывает, что ваш объект должен быть агрегатом.  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса объекта, который был определен как только статистическую обработку.  
  
### <a name="remarks"></a>Примечания  
 `DECLARE_ONLY_AGGREGATABLE`вызывает ошибку ( **E_FAIL**), если предпринята попытка **CoCreate** объект как неагрегированные объект.  
  
 По умолчанию [CComCoClass](../../atl/reference/ccomcoclass-class.md) содержит [DECLARE_AGGREGATABLE](#declare_aggregatable) макросом, который указывает, что объект может быть статистически вычислена. Чтобы переопределить это поведение по умолчанию, включите `DECLARE_ONLY_AGGREGATABLE` в определении класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE  
 Указывает, что экземпляр **CComPolyObject \<**  *x*  **>**  создается при создании объекта.  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса объекта, который был определен как статистическую обработку или невозможна.  
  
### <a name="remarks"></a>Примечания  
 Во время создания проверяется значение внешняя Неизвестная строка. Если это **NULL**, **IUnknown** реализуется для неагрегированные объекта. Если внешняя Неизвестная строка не **NULL**, **IUnknown** реализуется для вычисляемого объекта.  
  
 Преимущество использования `DECLARE_POLY_AGGREGATABLE` — избежать обладает и разрешением `CComAggObject` и `CComObject` в модуле для обработки случаев, статистические и нестатистические. Один `CComPolyObject` объект обрабатывает в обоих случаях. Это означает, что существуют только одна копия виртуальной таблице и одной копии функций в модуле. При большом вашей vtable это существенно уменьшить размер вашего модуля. Тем не менее, используемой при небольших вашей vtable `CComPolyObject` может привести к немного больший размер модуля, так как он не оптимизирован для суммирования или неагрегированные объекта, как `CComAggObject` и `CComObject`.  
  
 `DECLARE_POLY_AGGREGATABLE` Макрос автоматически объявляются в объекте при использовании мастер элементов управления ATL, чтобы создать полный доступ.  
  
##  <a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT  

 Защищает от удаления, если объект (во время [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) внутренний объект агрегированных увеличивает счетчик ссылок, а затем уменьшает число 0.  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="declare_view_status"></a>DECLARE_VIEW_STATUS  
 Поместите этот макрос в элемент управления ActiveX библиотеки ATL класс элемента управления, чтобы указать **Просмотр СОСТОЯНИЯ** флаги в контейнер.  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>Параметры  
 `statusFlags`  
 [in] **Просмотр СОСТОЯНИЯ** флаги. В разделе [Просмотр СОСТОЯНИЯ](http://msdn.microsoft.com/library/windows/desktop/ms687201) список флагов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
