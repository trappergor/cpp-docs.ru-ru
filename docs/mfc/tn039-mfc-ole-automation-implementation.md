---
title: 'TN039: Реализация автоматизации MFC OLE | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c6475e8c259026618192489ac2c67c20ed03d92
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039. Реализация автоматизации MFC/OLE
> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
## <a name="overview-of-ole-idispatch-interface"></a>Обзор интерфейса IDispatch OLE  
 `IDispatch` Интерфейса — средство, с помощью которого приложений предоставляют методы и свойства, например других приложений, таких как Visual BASIC и других языков могут сделать использование возможностей приложения. Самая важная часть этого интерфейса — **IDispatch::Invoke** функции. «Съемы» используется библиотекой MFC для реализации **IDispatch::Invoke**. Карта распределения предоставляет сведения о реализации MFC в макета или «формы» ваш `CCmdTarget`-производные классы, таким образом, что его можно непосредственно изменить свойства объекта, или вызвать член функций внутри объекта, чтобы удовлетворить  **IDispatch::Invoke** запросов.  
  
 В большинстве случаев мастер классов MFC взаимодействие и скрыть большую часть данных из приложения программиста OLE-автоматизации. Программист особое внимание уделяется полную функциональность для предоставления в приложении и не нужно беспокоиться о базовой коммуникации.  
  
 Существуют случаи, однако там, где это необходимо понимать, каким образом в фоновом MFC. Эта заметка поможет решить, каким образом платформа назначает **DISPID**функции-члены и свойства. Знание алгоритм, который используется библиотекой MFC для назначения **DISPID**s необходимо только в том случае, когда необходимо знать идентификаторы, например при создании «библиотеку типов» объектов приложения.  
  
## <a name="mfc-dispid-assignment"></a>Назначение MFC DISPID  
 Несмотря на то, что автоматизации (Visual Basic пользователя, например), конечный пользователь видит фактические имена автоматизации включены свойства и методы в коде (например, obj. ShowWindow), реализацию **IDispatch::Invoke** не получает фактические имена. В целях оптимизации получает **DISPID**, который является 32-разрядной magic куки-файл», описывающий метод или свойство, которое осуществляется. Эти **DISPID** значения возвращаются из `IDispatch` реализацию с использованием другой метод, называемый **:: GetIdsOfNames**. Вызывает приложение клиента автоматизации `GetIDsOfNames` после для каждого элемента или свойства он намеревается доступ и их кэширование для ее последующих вызовов **IDispatch::Invoke**. Таким образом, ресурсоемкие строки подстановки выполняется только один раз на каждое применение этого объекта, вместо один раз за **IDispatch::Invoke** вызова.  
  
 Определяет, MFC **DISPID**для каждого метода и свойства на основе две вещи:  
  
-   Расстояние от верхнего края карты распределения (относительно 1)  
  
-   Расстояние от карту диспетчеризации наиболее производного класса (0 относительный)  
  
 **DISPID** состоит из двух частей. **LOWORD** из **DISPID** содержит первый компонент, расстояние от верхнего края карту диспетчеризации. **HIWORD** содержит расстояние от наиболее производного класса. Пример:  
  
```  
class CDispPoint : public CCmdTarget  
{  
public:  
    short m_x,
    m_y;  
 ...  
    DECLARE_DISPATCH_MAP() 
 ...  
};  
 
class CDisp3DPoint : public CDispPoint  
{  
public:  
    short m_z;  
 ...  
    DECLARE_DISPATCH_MAP() 
 ...  
};  
 
BEGIN_DISPATCH_MAP(CDispPoint,
    CCmdTarget)  
    DISP_PROPERTY(CDispPoint, "x",
    m_x,
    VT_I2)  
    DISP_PROPERTY(CDispPoint, "y",
    m_y,
    VT_I2)  
END_DISPATCH_MAP()  
 
BEGIN_DISPATCH_MAP(CDisp3DPoint,
    CDispPoint)  
    DISP_PROPERTY(CDisp3DPoint, "z",
    m_z,
    VT_I2)  
END_DISPATCH_MAP()  
```  
  
 Как видите, существует два класса, которые предоставляют интерфейсы OLE-автоматизации. Одного из этих классов является производным от другого и таким образом использует функциональность базового класса, включая части автоматизации OLE («x» и «y» свойств в данном случае).  
  
 MFC создаст **DISPID**s для класса CDispPoint следующим образом:  
  
```  
property X    (DISPID)0x00000001  
property Y    (DISPID)0x00000002  
```  
  
 Поскольку свойства не входят в базовом классе, **HIWORD** из **DISPID** всегда равно нулю (расстояние от наиболее производный класс для CDispPoint равно нулю).  
  
 MFC создаст **DISPID**s для класса CDisp3DPoint следующим образом:  
  
```  
property Z    (DISPID)0x00000001  
property X    (DISPID)0x00010001  
property Y    (DISPID)0x00010002  
```  
  
 Получает свойства Z **DISPID** с нулем в **HIWORD** , так как он определен в классе, который Предоставление свойств, а CDisp3DPoint. Поскольку свойства X и Y определяются в базовом классе, **HIWORD** из **DISPID** имеет значение 1, так как класс, в котором определены эти свойства находится на расстоянии одного наследования от наиболее производного класса.  
  
> [!NOTE]
>  **LOWORD** всегда определяется положение на карте, даже если существуют записи в схеме с явной **DISPID** (см. в следующем разделе сведения **_ID** версии `DISP_PROPERTY` и `DISP_FUNCTION` макросы).  
  
## <a name="advanced-mfc-dispatch-map-features"></a>Дополнительные возможности сопоставления диспетчеризации MFC  
 Существует несколько дополнительных функций, которые ClassWizard не поддерживаются в этом выпуске Visual C++. Поддерживает ClassWizard `DISP_FUNCTION`, `DISP_PROPERTY`, и `DISP_PROPERTY_EX` которого определить метод, свойство переменной члена и функции get и set свойства, соответственно. Обычно эти возможности являются все, что требуется для создания большинства серверы автоматизации.  
  
 Следующие дополнительные макросы можно использовать при ClassWizard поддерживается макросы не подходят: `DISP_PROPERTY_NOTIFY`, и `DISP_PROPERTY_PARAM`.  
  
## <a name="disppropertynotify--macro-description"></a>DISP_PROPERTY_NOTIFY — Описание макроса  
  
```  
 
    DISP_PROPERTY_NOTIFY(
 theClass,   
    pszName, 
    memberName, 
    pfnAfterSet, 
    vtPropType) 
```  
  
## <a name="remarks"></a>Примечания  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойства.  
  
 `memberName`  
 Имя переменной-члена, в котором хранится свойство.  
  
 `pfnAfterSet`  
 Имя функции-члена для вызова при изменении свойства.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос имеет очень похоже на `DISP_PROPERTY`, за исключением того, что он принимает дополнительный аргумент. Дополнительный аргумент *pfnAfterSet,* должно быть функцией-членом, не возвращает ничего и не принимает никаких параметров «void OnPropertyNotify()». Он будет вызван **после** переменной-члену был изменен.  
  
## <a name="disppropertyparam--macro-description"></a>DISP_PROPERTY_PARAM — Описание макроса  
  
```  
 
    DISP_PROPERTY_PARAM(
 theClass,   
    pszName, 
    pfnGet, 
    pfnSet, 
    vtPropType, 
    vtsParams) 
```  
  
## <a name="remarks"></a>Примечания  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойства.  
  
 `memberGet`  
 Имя функции-члена, используемый для получения свойства.  
  
 `memberSet`  
 Имя функции-члена, используемый для задания свойства.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
 `vtsParams`  
 Строка пространства запятыми VTS_ для каждого параметра.  
  
## <a name="remarks"></a>Примечания  
 Как `DISP_PROPERTY_EX` макрос, этот макрос определяет свойства доступа к отдельной функции-члены Get и Set. Этот макрос, тем не менее, можно указать список параметров для свойства. Это полезно для реализации свойства, параметризованные или индексированные иным способом. Параметры, всегда помещаются во-первых, за которым следует новое значение для свойства. Пример:  
  
```  
DISP_PROPERTY_PARAM(CMyObject, "item",
    GetItem,
    SetItem,
    VT_DISPATCH,
    VTS_I2 VTS_I2)  
```  
  
 будет соответствовать для получения и задания функций-членов:  
  
```  
LPDISPATCH CMyObject::GetItem(short row,
    short col)  
void CMyObject::SetItem(short row,
    short col,
    LPDISPATCH newValue)  
```  
  
## <a name="dispxxxxid--macro-descriptions"></a>DISP_XXXX_ID — Описания макросов  
  
```  
 
    DISP_FUNCTION_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnMember, 
    vtRetVal, 
    vtsParams)DISP_PROPERTY_ID(
 theClass,   
    pszName, 
    dispid, 
    memberName, 
    vtPropType)DISP_PROPERTY_NOTIFY_ID(
 theClass,   
    pszName, 
    dispid, 
    memberName, 
    pfnAfterSet, 
    vtPropType)DISP_PROPERTY_EX_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnGet, 
    pfnSet, 
    vtPropType)DISP_PROPERTY_PARAM_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnGet, 
    pfnSet, 
    vtPropType, 
    vtsParams) 
```  
  
## <a name="remarks"></a>Примечания  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойства.  
  
 `dispid`  
 Фиксированный DISPID для свойства или метода.  
  
 `pfnGet`  
 Имя функции-члена, используемый для получения свойства.  
  
 `pfnSet`  
 Имя функции-члена, используемый для задания свойства.  
  
 `memberName`  
 Имя переменной-члена для сопоставления свойства  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
 `vtsParams`  
 Строка пространства запятыми VTS_ для каждого параметра.  
  
## <a name="remarks"></a>Примечания  
 Эти макросы позволяют указывать **DISPID** фиксированного MFC автоматически назначить один. Эти дополнительные макросы имеют те же имена, за исключением того, что идентификатор добавляется к имени макроса (например **DISP_PROPERTY_ID**) и идентификатор определяется сразу после указанного параметра `pszName` параметр. В разделе AFXDISP. H Дополнительные сведения об этих макросов. **_ID** записи должны располагаться в конце карту диспетчеризации. Они будут применяться автоматическое **DISPID** поколения в так же, как значение, отличное от **_ID** бы версии макроса ( **DISPID**s определяются по положению). Пример:  
  
```  
BEGIN_DISPATCH_MAP(CDisp3DPoint,
    CCmdTarget)  
    DISP_PROPERTY(CDisp3DPoint, "y",
    m_y,
    VT_I2)  
    DISP_PROPERTY(CDisp3DPoint, "z",
    m_z,
    VT_I2)  
    DISP_PROPERTY_ID(CDisp3DPoint, "x",
    0x00020003,
    m_x,
    VT_I2)  
END_DISPATCH_MAP()  
```  
  
 MFC создаст DISPID для класса CDisp3DPoint следующим образом:  
  
```  
property X    (DISPID)0x00020003  
property Y    (DISPID)0x00000002  
property Z     (DISPID)0x00000001  
```  
  
 Указав фиксированный **DISPID** полезно, чтобы обеспечить обратную совместимость для существующих интерфейс диспетчеризации или для реализации определенных системы и определены методы или свойства (обычно определяется отрицательное  **DISPID**, такие как **DISPID_NEWENUM** коллекции).  
  
#### <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>Извлечение интерфейса IDispatch для COleClientItem  
 Многие серверы будут поддерживать автоматизации в свои объекты документа, а возможности сервера OLE. Чтобы получить доступ к интерфейсу автоматизации, требуется доступ непосредственно **COleClientItem::m_lpObject** переменной-члена. В приведенном ниже коде извлечет `IDispatch` интерфейс для объекта, производного от `COleClientItem`. Приведенный ниже код можно включить в приложение, если эта функциональность найти необходимые:  
  
```  
LPDISPATCH CMyClientItem::GetIDispatch()  
{  
    ASSERT_VALID(this);

 ASSERT(m_lpObject != NULL);

 
    LPUNKNOWN lpUnk = m_lpObject;  
 
    Run();
*// must be running  
 
    LPOLELINK lpOleLink = NULL;  
    if (m_lpObject->QueryInterface(IID_IOleLink,   
 (LPVOID FAR*)&lpOleLink) == NOERROR)  
 {  
    ASSERT(lpOleLink != NULL);

    lpUnk = NULL;  
    if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)  
 {  
    TRACE0("Warning: Link is not connected!\n");

    lpOleLink->Release();
return NULL;  
 }  
    ASSERT(lpUnk != NULL);

 }  
 
    LPDISPATCH lpDispatch = NULL;  
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch)   
 != NOERROR)  
 {  
    TRACE0("Warning: does not support IDispatch!\n");

    return NULL;  
 }  
 
    ASSERT(lpDispatch != NULL);

    return lpDispatch;  
}  
```  
  
 Возвращенный интерфейс диспетчеризации затем можно использовать непосредственно или подключен к эта функция `COleDispatchDriver` для доступа к строго типизированным. Если использовать непосредственно, убедитесь, что вызвать его **выпуска** член при через указатель ( `COleDispatchDriver` деструктор делается по умолчанию).  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

