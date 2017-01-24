---
title: "TN039. Реализация автоматизации MFC/OLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "автоматизация, точки входа в интерфейс COM-модели MFC"
  - "IDispatch - интерфейс"
  - "MFC - библиотека, поддержка COM"
  - "MFC - библиотека, OLE DB и"
  - "TN039"
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN039. Реализация автоматизации MFC/OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию.  В результате некоторые процедуры и разделы могут быть устаревшими или неверными.  Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
## Обзор интерфейса OLE IDispatch  
 Интерфейс `IDispatch` означает, приложения предоставляют методы и свойства так, что другие приложения, например Visual Basic, или на других языках, могут использовать функции приложения.  Наиболее важной частью этого интерфейса функцию **IDispatch::Invoke**.  MFC использует «схемы подготовки к отправке» для реализации **IDispatch::Invoke**.  Схема подготовки к отправке предоставляет сведения о реализации MFC в макете фигуре» или «. `CCmdTarget`\- производных классов, таких, что она может непосредственного управления свойства объекта или вызывает функции\-члены в этот объект, чтобы удовлетворять запросы **IDispatch::Invoke**.  
  
 В большинстве случаев ClassWizard и MFC сотрудничают скрывать большинство сведения ole\-автоматизации от программиста приложения.  Программист сосредоточено на фактическую функции для предоставления в приложении, а не нужно беспокоиться о базовом трубопроводе.  
  
 Случаи, когда необходимо понять MFC выполняет в фоновом режиме.  Эта заметка рассматривается как платформа присвоить **DISPID** к функциям элемента и свойства.  Знание алгоритма MFC использует для присвоения s **DISPID** требуется только при необходимости знать идентификаторы, например при создании «библиотека типов» для объектов приложения.  
  
## Назначение MFC DISPID  
 Хотя пользователь автоматизации пользователя \(Visual Basic\), например, просмотреть фактические имена свойств которых автоматизации и методы их в коде \(например, obj.ShowWindow\), реализация метода **IDispatch::Invoke** не возвращает фактические имена.  Для повышения оптимизации оно получает **DISPID**, 32 бит волшебное файл «cookie», которое описывает метод или свойство, доступу.  Эти значения **DISPID** возвращаются из реализации `IDispatch` через другой метод с именем **IDispatch::GetIDsOfNames**.  Приложение клиента автоматизации вызовет `GetIDsOfNames` один раз для каждого члена или свойства оно планирует доступ, и они кэширования для последующих вызовов **IDispatch::Invoke**.  Таким образом, требует поиск строки выполняется только один раз для каждого объекта, а не использовать один раз для каждого вызова **IDispatch::Invoke**.  
  
 MFC определяет **DISPID**, для всех методов и свойств, основанных на 2 действиях.  
  
-   Расстояние — от верха схемы подготовки к отправке relative \(1\)  
  
-   Расстояние схемы подготовки к сообщению с большинства производного класса родственников \(0\)  
  
 **DISPID** Состоит из 2 частей.  **LOWORDDISPID** Содержит первый компонент, расстояние — от верха схемы подготовки к сообщению.  **HIWORD** Содержит расстояние от наиболее производного класса.  Примеры.  
  
```  
class CDispPoint : public CCmdTarget  
{  
public:  
    short m_x, m_y;  
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
  
BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)  
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)  
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)  
END_DISPATCH_MAP()  
  
BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)  
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)  
END_DISPATCH_MAP()  
```  
  
 Как видно, существует 2 классов, которые предоставляют интерфейсы ole\-автоматизации.  Один из этих классов является производным от другого и таким образом используется функция базового класса, в том числе часть ole\-автоматизации \(свойства «x» и «y» в данном случае\).  
  
 MFC создает s **DISPID** для класса CDispPoint следующим образом:  
  
```  
property X    (DISPID)0x00000001  
property Y    (DISPID)0x00000002  
```  
  
 Поскольку свойства нет в базовом классе, **HIWORDDISPID** всегда равно нулю \(расстояние от наиболее производного класса для CDispPoint ноль\).  
  
 MFC создает s **DISPID** для класса CDisp3DPoint следующим образом:  
  
```  
property Z    (DISPID)0x00000001  
property X    (DISPID)0x00010001  
property Y    (DISPID)0x00010002  
```  
  
 Z назначается свойству **DISPID** с **HIWORD**, поскольку определена в классе, который предоставляет свойства, CDisp3DPoint.  Поскольку свойства x и Y определить в базовом классе, **HIWORDDISPID** 1, поскольку класс, в котором эти свойства определяются на расстоянии от наследования от наиболее производного класса.  
  
> [!NOTE]
>  **LOWORD** Всегда определяется позицией в сопоставлении, даже при наличии существующих записей в сопоставлении с явной **DISPID** \(см. следующий раздел сведения о версиях **\_ID** макросов `DISP_PROPERTY` и `DISP_FUNCTION` \).  
  
## Дополнительные функции схемы подготовки к отправке MFC  
 Ряд дополнительных функций, ClassWizard не поддерживается в этом выпуске Visual C\+\+.  ClassWizard поддерживает `DISP_FUNCTION`, `DISP_PROPERTY` и `DISP_PROPERTY_EX`, определяет метод, свойство переменной\-члена и получает или задает свойство функции\-члена соответственно.  Обычно все эти возможности, необходимые для создания большинства серверы автоматизации.  
  
 Следующие дополнительные макросы могут использоваться, если макросы поддерживаемые ClassWizard не адекватни: `DISP_PROPERTY_NOTIFY` и `DISP_PROPERTY_PARAM`.  
  
## DISP\_PROPERTY\_NOTIFY — Описание макроса  
  
```  
  
        DISP_PROPERTY_NOTIFY(   
   theClass,   
   pszName,   
   memberName,   
   pfnAfterSet,   
   vtPropType   
)  
```  
  
## Примечания  
  
### Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойства.  
  
 `memberName`  
 Имя переменной, в котором хранится свойство.  
  
 `pfnAfterSet`  
 Имя функции\-члена, который вызывается при изменении свойства.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
## Примечания  
 Этот макрос подобно `DISP_PROPERTY`, за исключением того, что он принимает дополнительный аргумент.  Дополнительный аргумент, *pfnAfterSet,* должен быть функцией\-членом, который не возвращает никаких действий и не принимает параметры, «void OnPropertyNotify \(\)».  Он вызывается **после** переменную\-член будет изменен.  
  
## DISP\_PROPERTY\_PARAM — Описание макроса  
  
```  
  
        DISP_PROPERTY_PARAM(   
   theClass,  
   pszName,  
   pfnGet,  
   pfnSet,  
   vtPropType,  
   vtsParams   
)  
```  
  
## Примечания  
  
### Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойства.  
  
 `memberGet`  
 Имя функции\-члена, используемого для доступа к свойству.  
  
 `memberSet`  
 Имя функции\-члена используется для задания свойства.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
 `vtsParams`  
 Строка отделила VTS\_ пространства для каждого параметра.  
  
## Примечания  
 Подобно макрос `DISP_PROPERTY_EX`, этот макрос указывает свойство с отдельной последнего доступа get и set функции\-члены.  Этот макрос, однако позволяет определить список параметров для свойства.  Это полезно для реализации свойств индексируются, или параметризованный каким\-либо другим способом.  Параметры всегда помещаются сначала выполнены новое значение свойства.  Примеры.  
  
```  
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH,    VTS_I2 VTS_I2)  
```  
  
 совпадают, чтобы получать и задавать функции\-члены.  
  
```  
LPDISPATCH CMyObject::GetItem(short row, short col)  
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)  
```  
  
## DISP\_XXXX\_ID — описания макроса  
  
```  
  
        DISP_FUNCTION_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnMember,  
   vtRetVal,  
   vtsParams   
) DISP_PROPERTY_ID(   
   theClass,  
   pszName,  
   dispid,  
   memberName,  
   vtPropType   
) DISP_PROPERTY_NOTIFY_ID(   
   theClass,  
   pszName,  
   dispid,  
   memberName,  
   pfnAfterSet,  
   vtPropType   
) DISP_PROPERTY_EX_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnGet,  
   pfnSet,  
   vtPropType   
) DISP_PROPERTY_PARAM_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnGet,  
   pfnSet,  
   vtPropType,  
   vtsParams   
)  
```  
  
## Примечания  
  
### Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойства.  
  
 `dispid`  
 Фиксированное DISPID для свойства или метода.  
  
 `pfnGet`  
 Имя функции\-члена, используемого для доступа к свойству.  
  
 `pfnSet`  
 Имя функции\-члена используется для задания свойства.  
  
 `memberName`  
 Имя переменной, с которым выполняется сопоставление для свойства  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
 `vtsParams`  
 Строка отделила VTS\_ пространства для каждого параметра.  
  
## Примечания  
 Эти макросы позволяют указывать **DISPID** вместо предоставление MFC автоматически присвоено одно.  Эти дополнительные макросы имеют те же имена, за исключением того, что идентификатор добавляется к имени макроса \(например.  **DISP\_PROPERTY\_ID**\) и идентификатор определены указанным параметром сразу после параметра `pszName`.  В разделе AFXDISP.H дополнительные сведения об этих макросах.  Записи **\_ID** должен быть помещен в конце схемы подготовки к сообщению.  Изменения действовали для автоматического создания **DISPID** точно так же, как и для версии **\_ID** макроса **DISPID** определяется позицией \(s\).  Примеры.  
  
```  
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)  
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)  
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)  
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)  
END_DISPATCH_MAP()  
```  
  
 MFC создает Dispid для класса CDisp3DPoint следующим образом:  
  
```  
property X    (DISPID)0x00020003  
property Y    (DISPID)0x00000002  
property Z     (DISPID)0x00000001  
```  
  
 Определение фиксированное **DISPID** полезен для обеспечения обратной совместимости с ранее существующим интерфейсом диспетчеризации, или реализовать некоторую систему, методов или свойств \(обычно показываемые отрицательным **DISPID**, например коллекция **DISPID\_NEWENUM** \).  
  
#### Извлечь интерфейс IDispatch для COleClientItem  
 Многим серверам поддерживали автоматизации в их объекты документа, вместе с функцией OLE\-сервера.  Чтобы получить доступ к этому интерфейсу автоматизации, необходимо напрямую обращается к переменной\-члену **COleClientItem::m\_lpObject**.  Приведенный ниже код получает интерфейс `IDispatch` для объекта производного от `COleClientItem`.  Можно включать приведенный ниже код в приложении при обнаружении этой функции является обязательной, выполните следующие действия.  
  
```  
LPDISPATCH CMyClientItem::GetIDispatch()  
{  
    ASSERT_VALID(this);  
    ASSERT(m_lpObject != NULL);  
  
    LPUNKNOWN lpUnk = m_lpObject;  
  
    Run();    // must be running  
  
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
  
 Интерфейс диспетчеризации, возвращенный из этой функции может затем использоваться непосредственно или вложен в `COleDispatchDriver` для типобезопасного доступа.  При использовании этой напрямую, убедитесь, что элемент **Выпуск** при вызове его через указатель с `COleDispatchDriver` делает это деструктор \(по умолчанию\).  
  
## См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)