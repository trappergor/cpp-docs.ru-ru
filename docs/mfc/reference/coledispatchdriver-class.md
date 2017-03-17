---
title: "Класс COleDispatchDriver | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchDriver class
- Automation clients, implementing Automation
- OLE dispatch interface
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 51fc2064e2f4b51b4f4328afb03920dab27ef74b
ms.lasthandoff: 02/24/2017

---
# <a name="coledispatchdriver-class"></a>Класс COleDispatchDriver
Реализует автоматизацию OLE на стороне клиента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDispatchDriver  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|Создает объект `COleDispatchDriver`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|Присоединяет `IDispatch` соединение `COleDispatchDriver` объекта.|  
|[COleDispatchDriver::CreateDispatch](#createdispatch)|Создает `IDispatch` соединений и присоединяет его к `COleDispatchDriver` объекта.|  
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|Отсоединяет `IDispatch` соединения, не освобождая его.|  
|[COleDispatchDriver::GetProperty](#getproperty)|Получает свойство автоматизации.|  
|[COleDispatchDriver::InvokeHelper](#invokehelper)|Вспомогательный класс для вызова методов автоматизации.|  
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|Выпуски `IDispatch` соединения.|  
|[COleDispatchDriver::SetProperty](#setproperty)|Задает свойство автоматизации.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDispatchDriver::operator =](#operator_eq)|Копирует значение источника в `COleDispatchDriver` объекта.|  
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|Обращается к основной `IDispatch` указателя.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|Указывает, следует ли освободить `IDispatch` во время `ReleaseDispatch` или уничтожение объектов.|  
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|Указывает указатель `IDispatch` интерфейс, подключенный к этому `COleDispatchDriver`.|  
  
## <a name="remarks"></a>Примечания  
 `COleDispatchDriver`не имеет базового класса.  
  
 Диспетчерские интерфейсы OLE предоставляют доступ к методам и свойствам объекта. Функции-члены `COleDispatchDriver` подключать, отключать, создание и выпуск для диспетчера подключения типа `IDispatch`. Переменные списки аргументов использовать другие функции-члены для упрощения вызова **IDispatch::Invoke**.  
  
 Этот класс может использоваться непосредственно, но он обычно используется только классы, созданные с помощью мастера добавления классов. При импорте библиотеки типов, при создании новых классов C++, новые классы являются производными от `COleDispatchDriver`.  
  
 Дополнительные сведения об использовании `COleDispatchDriver`, ознакомьтесь со следующими статьями:  
  
- [Клиенты автоматизации](../../mfc/automation-clients.md)  
  
- [Серверы автоматизации](../../mfc/automation-servers.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `COleDispatchDriver`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="attachdispatch"></a>COleDispatchDriver::AttachDispatch  
 Функция-член `AttachDispatch` вызывается для того, чтобы присоединить указатель `IDispatch` к объекту `COleDispatchDriver` . Дополнительные сведения см. в разделе [реализации интерфейса IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
```  
void AttachDispatch(
        LPDISPATCH lpDispatch,  
        BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDispatch`  
 Указатель на объект OLE `IDispatch` , который необходимо присоединить к объекту `COleDispatchDriver` .  
  
 `bAutoRelease`  
 Определяет, следует ли освободить диспетчер, когда этот объект выходит из области действия.  
  
### <a name="remarks"></a>Примечания  
 Эта функция освобождает все указатели `IDispatch` , которые уже присоединены к объекту `COleDispatchDriver` .  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#3;](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]  
  
##  <a name="coledispatchdriver"></a>COleDispatchDriver::COleDispatchDriver  
 Создает объект `COleDispatchDriver`.  
  
```  
COleDispatchDriver();  
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);  
  COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDispatch`  
 Указатель на объект OLE `IDispatch` , который необходимо присоединить к объекту `COleDispatchDriver` .  
  
 `bAutoRelease`  
 Определяет, следует ли освободить диспетчер, когда этот объект выходит из области действия.  
  
 `dispatchSrc`  
 Ссылка на существующую `COleDispatchDriver` объекта.  
  
### <a name="remarks"></a>Примечания  
 Формы `COleDispatchDriver`( `LPDISPATCH``lpDispatch`, **BOOL**`bAutoRelease` = **TRUE**) подключается [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) интерфейса.  
  
 Формы `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) копирует существующую `COleDispatchDriver` объекта и увеличивает счетчик ссылок.  
  
 Формы `COleDispatchDriver`() создает `COleDispatchDriver` объекта, но не выполняет соединение `IDispatch` интерфейса. Перед использованием `COleDispatchDriver`() без аргументов, необходимо подключить `IDispatch` к нему с помощью [COleDispatchDriver::CreateDispatch](#createdispatch) или [COleDispatchDriver::AttachDispatch](#attachdispatch). Дополнительные сведения см. в разделе [реализации интерфейса IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
### <a name="example"></a>Пример  
  В примере показано [COleDispatchDriver::CreateDispatch](#createdispatch).  
  
##  <a name="createdispatch"></a>COleDispatchDriver::CreateDispatch  
 Создает [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) объект интерфейса и присоединяет его к `COleDispatchDriver` объекта.  
  
```  
BOOL CreateDispatch(
        REFCLSID clsid,  
        COleException* pError = NULL);

 
BOOL CreateDispatch(
    LPCTSTR lpszProgID,  
    COleException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 Идентификатор класса создаваемого объекта подключения `IDispatch` .  
  
 `pError`  
 Указатель на объект исключения OLE, который будет содержать код состояния, полученный в результате создания.  
  
 `lpszProgID`  
 Указатель на программный идентификатор, например Excel.Document.5, объекта автоматизации, для которого будет создаваться объект обработки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#4;](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]  
  
##  <a name="detachdispatch"></a>COleDispatchDriver::DetachDispatch  
 Отсоединяет текущий `IDispatch` подключения от этого объекта.  
  
```  
LPDISPATCH DetachDispatch();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на ранее присоединенные OLE `IDispatch` объекта.  
  
### <a name="remarks"></a>Примечания  
 `IDispatch` Не освобождается.  
  
 Дополнительные сведения о `LPDISPATCH` см. в разделе [реализации интерфейса IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#5;](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]  
  
##  <a name="getproperty"></a>COleDispatchDriver::GetProperty  
 Возвращает свойства объекта, указанного параметром `dwDispID`.  
  
```  
void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwDispID`  
 Определяет свойство, которое требуется получить.  
  
 `vtProp`  
 Задает свойство для извлечения. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](#invokehelper).  
  
 `pvProp`  
 Адрес переменной, которая будет получать значение свойства. Он должен соответствовать типа, заданного параметром `vtProp`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer №&6;](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]  
  
##  <a name="invokehelper"></a>COleDispatchDriver::InvokeHelper  
 Вызывает метод или свойство объекта, заданное `dwDispID`, в контексте, определяемом `wFlags`.  
  
```  
void AFX_CDECL InvokeHelper(
        DISPID dwDispID,  
        WORD wFlags,  
        VARTYPE vtRet,  
        void* pvRet,  
        const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDispID`  
 Задает вызываемый метод или свойство.  
  
 `wFlags`  
 Флаги, описывающие контекст вызова **IDispatch::Invoke**. . Список возможных значений см. в разделе `wFlags` параметр в [IDispatch::Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `vtRet`  
 Указывает тип возвращаемого значения. Возможные значения см. в разделе "Примечания".  
  
 `pvRet`  
 Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Переменная должна иметь тип, заданный в параметре `vtRet`.  
  
 `pbParamInfo`  
 Указатель на завершающуюся символом null строку байтов, определяющую типы параметров после `pbParamInfo`.  
  
 *...*  
 Переменный список параметров типов, указанных в `pbParamInfo`.  
  
### <a name="remarks"></a>Примечания  
 Параметр `pbParamInfo` определяет типы параметров, передаваемых в метод или свойство. Переменный список аргументов представлен в объявлении синтаксиса как **...** .  
  
 Возможные значения аргумента `vtRet` берутся из перечисления `VARENUM` . Ниже приведены возможные значения.  
  
|Символ|Тип возвращаемого значения|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**ПОЛУГОДИЕ**|  
|`VT_DATE`|**ДАТА**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 Аргумент `pbParamInfo` содержит разделенный пробелами список констант **VTS_** . Одно или несколько из этих значений, разделенных пробелами (не запятыми), составляют список параметров функции. Возможные значения перечислены в [EVENT_CUSTOM](event-maps.md#event_custom) макрос.  
  
 Эта функция преобразует параметры в значения **VARIANTARG** , а затем вызывает метод [IDispatch::Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) . Если вызов `Invoke` завершается сбоем, эта функция создает исключение. Если `SCODE` (код состояния), возвращенный **IDispatch::Invoke** — `DISP_E_EXCEPTION`, эта функция вызывает [COleException](../../mfc/reference/coleexception-class.md) объекта; в противном случае он вызывает [COleDispatchException](../../mfc/reference/coledispatchexception-class.md).  
  
 Дополнительные сведения см. в разделе [VARIANTARG](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [реализации интерфейса IDispatch](http://msdn.microsoft.com/library/windows/desktop/ms221037\(v=vs.85\).aspx), [IDispatch::Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx), и [структура кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [COleDispatchDriver::CreateDispatch](#createdispatch).  
  
##  <a name="m_bautorelease"></a>COleDispatchDriver::m_bAutoRelease  
 Если **TRUE**, COM-объект, доступ к [m_lpDispatch](#m_lpdispatch) автоматически освобождается при [ReleaseDispatch](#releasedispatch) вызывается или если это `COleDispatchDriver` объект уничтожается.  
  
```  
BOOL m_bAutoRelease;  
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `m_bAutoRelease` равен **TRUE** в конструкторе.  
  
 Дополнительные сведения о освобождения COM-объектов в разделе [подсчет ссылок на реализации](http://msdn.microsoft.com/library/windows/desktop/ms693431) и [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer №&9;](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]  
  
##  <a name="m_lpdispatch"></a>COleDispatchDriver::m_lpDispatch  
 Указатель на `IDispatch` интерфейс, подключенный к этому `COleDispatchDriver`.  
  
```  
LPDISPATCH m_lpDispatch;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_lpDispatch` Член данных — это открытая переменная типа `LPDISPATCH`.  
  
 Дополнительные сведения см. в разделе [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [COleDispatchDriver::AttachDispatch](#attachdispatch).  
  
##  <a name="operator_eq"></a>COleDispatchDriver::operator =  
 Копирует значение источника в `COleDispatchDriver` объекта.  
  
```  
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `dispatchSrc`  
 Указатель на существующую `COleDispatchDriver` объекта.  
  
##  <a name="operator_lpdispatch"></a>COleDispatchDriver::operator LPDISPATCH  
 Обращается к основной `IDispatch` указатель `COleDispatchDriver` объекта.  
  
```  
operator LPDISPATCH();
```   
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer №&8;](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]  
  
##  <a name="releasedispatch"></a>COleDispatchDriver::ReleaseDispatch  
 Выпуски `IDispatch` соединения. Дополнительные сведения см. в разделе [реализации интерфейса IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)  
  
```  
void ReleaseDispatch();
```  
  
### <a name="remarks"></a>Примечания  
 Если автоматического освобождения имеет для этого подключения, эта функция вызывает функцию **IDispatch::Release** перед освобождением интерфейса.  
  
### <a name="example"></a>Пример  
  В примере показано [COleDispatchDriver::AttachDispatch](#attachdispatch).  
  
##  <a name="setproperty"></a>COleDispatchDriver::SetProperty  
 Задает свойство объекта OLE, указанное с помощью параметра `dwDispID`.  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDispID`  
 Определяет свойство, которое необходимо задать.  
  
 `vtProp`  
 Определяет тип свойства, которое необходимо задать. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](#invokehelper).  
  
 *...*  
 Один параметр типа, указанного в параметре `vtProp`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#7;](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CALCDRIV](../../visual-cpp-samples.md)   
 [Пример MFC ACDUAL](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)

