---
title: 'TN038: Реализация MFC OLE IUnknown | Документы Microsoft'
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
- aggregation macros [MFC]
- COM interfaces, base interface
- IUnknown interface
- END_INTERFACE_MAP macro [MFC]
- TN038
- BEGIN_INTERFACE_PART macro [MFC]
- DECLARE_INTERFACE_MAP macro [MFC]
- BEGIN_INTERFACE_MAP macro [MFC]
- OLE [MFC], implementing IUnknown interface
- METHOD_PROLOGUE macro [MFC]
- STDMETHOD macro [MFC]
- END_INTERFACE_PART macro [MFC]
- INTERFACE_PART macro
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e93c4e9d8707d3960e768b6929bb2b1c16d60b42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385486"
---
# <a name="tn038-mfcole-iunknown-implementation"></a>TN038. Реализация MFC/OLE IUnknown
> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 В основе OLE 2 лежит модель COM OLE. Модель COM определяет стандарт взаимодействия совместно действующих объектов. Сюда входят сведения о самом «объекте», включая то, какие методы подготавливаются для отправки в объект. Модель COM также определяет базовый класс, от которого наследуются все COM-совместимые классы. Этот базовый класс является [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Несмотря на то что [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) интерфейс называется классом C++, модель COM не относится к любой определенному языку — она может быть реализована на C, PASCAL или любом другом языке, поддерживающем двоичное размещение COM-объекта.  
  
 OLE ссылается на все классы, производные от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) как «интерфейсами». Это важное различие, поскольку «интерфейс» например [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) несет с нет реализации. Он просто определяет протокол, по которому взаимодействуют объекты, а не особенности этих реализаций. Это оправдано для системы, которая нацелена на максимальную гибкость. За реализацию поведения по умолчанию для программ MFC/C++ отвечает MFC.  
  
 Чтобы понять реализацию MFC [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) необходимо сначала понять, этот интерфейс является. Упрощенная схема [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) определен ниже:  
  
```  
class IUnknown  
{  
public:  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;  
    virtual ULONG AddRef() = 0;  
    virtual ULONG Release() = 0;  
};  
```  
  
> [!NOTE]
>  Некоторые необходимые сведения по соглашениям о вызовах, такие как `__stdcall`, в данной иллюстрации опущены.  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) функции-члены управляют памятью объекта. Модель COM использует схему подсчета ссылок для отслеживания объектов. Ссылка на объект никогда не указывается напрямую, как это происходит в C++. Вместо этого ссылка на COM-объекты всегда осуществляется через указатель. Чтобы освободить объект после завершения владельца с помощью его, объект [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) вызывается элемент (а не оператор delete, как это происходит в случае обычным объектом C++). Механизм подсчета ссылок позволяет управлять несколькими ссылками на один объект. Реализация [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) поддерживает счетчик ссылок на объект — объект не удаляется, пока число ссылок достигает нуля.  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) довольно просты, с точки зрения реализации. Вот пример простой реализации:  
  
```  
ULONG CMyObj::AddRef()   
{   
    return ++m_dwRef;   
}  
 
ULONG CMyObj::Release()   
{   
    if (--m_dwRef == 0)   
 {  
    delete this;   
    return 0;  
 }  
    return m_dwRef;  
}  
```  
  
 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) функция-член является более интересным. Это не очень интересно объект только функции-члены которого являются [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) — бы желательно заставить объект выполнять больше задач, чем [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) предоставляет. Это место, куда [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) полезно. Он позволяет получать разный «интерфейс» на базе одного и того же объекта. Эти интерфейсы обычно являются производными от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) и добавить дополнительную функциональность путем добавления новых функций-членов. COM-интерфейсы никогда не имеют объявляемых в интерфейсе переменных-членов, а все функции-члены объявлены как чисто виртуальные. Например, примененная к объекту директива  
  
```  
class IPrintInterface : public IUnknown  
{  
public:  
    virtual void PrintObject() = 0;  
};  
```  
  
 Чтобы получить IPrintInterface при наличии только [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), вызовите [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) с помощью `IID` из **IPrintInterface**. `IID` представляет собой 128-разрядное число, которое однозначно определяет интерфейс. `IID` присутствует для каждого интерфейса, определенного вами или OLE. Если `pUnk` — это указатель на [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) объекта может быть указан код для получения IPrintInterface из него:  
  
```  
IPrintInterface* pPrint = NULL;  
if (pUnk->QueryInterface(IID_IPrintInterface,   
 (void**)&pPrint) == NOERROR)  
{  
    pPrint->PrintObject();
pPrint->Release();
*// release pointer obtained via QueryInterface  
}  
```  
  
 Это кажется довольно простым, но как реализовать объект, поддерживающий как IPrintInterface, так и [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) интерфейса в данном случае это просто, поскольку IPrintInterface является производным непосредственно от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) — путем реализации IPrintInterface, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) будет поддерживаться автоматически. Пример:  
  
```  
class CPrintObj : public CPrintInterface  
{  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();
virtual void PrintObject();

};  
```  
  
 Реализации [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) будет точно таким же, как описанная выше. **CPrintObj::QueryInterface** будет выглядеть примерно следующим образом:  
  
```  
HRESULT CPrintObj::QueryInterface(REFIID iid, void FAR* FAR* ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
 {  
 *ppvObj = this;  
    AddRef();
return NOERROR;  
 }  
    return E_NOINTERFACE;  
}  
```  
  
 Как видите, если распознается идентификатор интерфейса (IID), в объект возвращается указатель, в противном случае возникает ошибка. Также Обратите внимание, что успешное выполнение [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) дает подразумеваемый [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379). Конечно же, необходимо также реализовать CEditObj::Print. Это просто, поскольку IPrintInterface является производным непосредственно от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) интерфейса. Тем не менее, если требуется поддержка двух различных интерфейсов, которые являются производными от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), необходимо учитывать следующее:  
  
```  
class IEditInterface : public IUnkown  
{  
public:  
    virtual void EditObject() = 0;  
};  
```  
  
 Хотя существует несколько разных способов реализации класса, поддерживающего как IEditInterface, так и IPrintInterface, включая использование множественного наследования C++, эта заметка будет посвящена использованию вложенных классов для реализации данной функциональности.  
  
```  
class CEditPrintObj  
{  
public:  
    CEditPrintObj();

 
    HRESULT QueryInterface(REFIID iid,
    void**);

    ULONG AddRef();
ULONG Release();
DWORD m_dwRef;  
 
    class CPrintObj : public IPrintInterface  
 {  
    public: 
    CEditPrintObj* m_pParent;  
    virtual HRESULT QueryInterface(REFIID iid,
    void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();

 } m_printObj;  
 
    class CEditObj : public IEditInterface  
 {  
    public: 
    CEditPrintObj* m_pParent;  
    virtual ULONG QueryInterface(REFIID iid,
    void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();

 } m_editObj;  
};  
```  
  
 Полная реализация приведена ниже.  
  
```  
CEditPrintObj::CEditPrintObj()  
{  
    m_editObj.m_pParent = this;  
    m_printObj.m_pParent = this;  
}  
 
ULONG CEditPrintObj::AddRef()   
{   
    return ++m_dwRef;  
}  
 
CEditPrintObj::Release()  
{  
    if (--m_dwRef == 0)  
 {  
    delete this;  
    return 0;  
 }  
    return m_dwRef;  
}  
 
HRESULT CEditPrintObj::QueryInterface(REFIID iid,
    void** ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
 {  
 *ppvObj = &m_printObj;  
    AddRef();
return NOERROR;  
 }  
    else if (iid == IID_IEditInterface)  
 {  
 *ppvObj = &m_editObj;  
    AddRef();
return NOERROR;  
 }  
    return E_NOINTERFACE;  
}  
 
ULONG CEditPrintObj::CEditObj::AddRef()   
{   
    return m_pParent->AddRef();

}  
 
ULONG CEditPrintObj::CEditObj::Release()   
{   
    return m_pParent->Release();

}  
 
HRESULT CEditPrintObj::CEditObj::QueryInterface(
    REFIID iid,
    void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid,
    ppvObj);

}  
 
ULONG CEditPrintObj::CPrintObj::AddRef()   
{   
    return m_pParent->AddRef();

}  
 
ULONG CEditPrintObj::CPrintObj::Release()   
{   
    return m_pParent->Release();

}  
 
HRESULT CEditPrintObj::CPrintObj::QueryInterface(
    REFIID iid,
    void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid,
    ppvObj);

}  
```  
  
 Обратите внимание, что большая часть [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) реализация помещается в класс CEditPrintObj вместо того чтобы дублировать код в CEditPrintObj::CEditObj и CEditPrintObj::CPrintObj. Это уменьшает объем кода и помогает избежать ошибок. Главное здесь то, что от интерфейса IUnknown можно вызвать [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) для получения любого интерфейса который объект должен поддерживать и из любого из этих интерфейсов можно сделать то же самое. Это означает, что все [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) функций, доступных из каждого интерфейса должны вести себя точно так же. Чтобы эти внедренные объекты вызвали реализацию во «внешнем объекте», используется обратный указатель (m_pParent). Указатель m_pParent инициализируется во время выполнения конструктора CEditPrintObj. Затем следует реализовать CEditPrintObj::CPrintObj::PrintObject, а также CEditPrintObj::CEditObj::EditObject. Потребовалось написать довольно большой объем кода для реализации одной возможности — возможности изменения объекта. К счастью, интерфейсы крайне редко имеют только одну функцию-член (хотя такое и случается), и в этом случае EditObject и PrintObject обычно объединяются в единый интерфейс.  
  
 Такой простой сценарий требует слишком долгих пояснений и слишком большого объема кода. Классы MFC/OLE предоставляют более простую альтернативу. Реализация MFC использует методику, аналогичную использованию программы-оболочки для сообщений Windows с помощью схем сообщений. Этот компонент называется *схемы интерфейсов* и рассматривается в следующем разделе.  
  
## <a name="mfc-interface-maps"></a>Схемы интерфейсов MFC  
 MFC/OLE включает в себя реализацию «Схемы интерфейсов», аналогичную компонентам «Схемы сообщений» и «Схемы подготовки к отправке» MFC в рамках концепции и выполнения. Схемы интерфейсов MFC имеют следующие основные возможности.  
  
-   Стандартная реализация [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), встроенная в `CCmdTarget` класса.  
  
-   Обслуживание счетчика ссылок, была изменена [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317)  
  
-   Управляемая данными реализация [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)  
  
 Кроме того, схемы интерфейсов поддерживают следующие дополнительные возможности.  
  
-   Поддержка создания COM-объектов, допускающих статистическую обработку  
  
-   Поддержка использования агрегатных объектов в реализации COM-объекта  
  
-   Реализация является обрабатываемой и расширяемой  
  
 Дополнительные сведения о статистической обработке см. в разделе [статистической обработки](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx) раздела.  
  
 Поддержка схем интерфейсов MFC заключена в класс `CCmdTarget`. `CCmdTarget` «*имеет*"ссылаются на число, а также все функции-члены, связанные с [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) реализацию (счетчик ссылок, например находится в `CCmdTarget`). Чтобы создать класс, поддерживающий модель COM OLE, создайте класс, производный от `CCmdTarget`, и используйте различные макросы и функции-члены `CCmdTarget` для реализации требуемых интерфейсов. Реализация MFC использует вложенные классы для определения каждой реализации интерфейса, что во многом похоже на приведенный выше пример. Эта задача упрощается благодаря стандартной реализации IUnknown, а также набору макросов, позволяющих исключить некоторые из повторяющихся частей кода.  
  
## <a name="interface-map-basics"></a>Основы использования схем интерфейсов  
  
#### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>Реализация класса с помощью схем интерфейсов MFC  
  
1.  Создайте класс, который явно или косвенно является от `CCmdTarget`.  
  
2.  Используйте функцию `DECLARE_INTERFACE_MAP` в определении производного класса.  
  
3.  Для каждого интерфейса, поддержку которого требуется обеспечить, используйте макросы `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART` в определении класса.  
  
4.  В файле реализации воспользуйтесь макросами `BEGIN_INTERFACE_MAP` и `END_INTERFACE_MAP` для определения схемы интерфейсов класса.  
  
5.  Для каждого поддерживаемого идентификатора интерфейса используйте макрос `INTERFACE_PART` между макросами `BEGIN_INTERFACE_MAP` и `END_INTERFACE_MAP`, чтобы сопоставить IID с конкретной частью класса.  
  
6.  Реализуйте каждый из вложенных классов, представляющих интерфейсы, которые вы поддерживаете.  
  
7.  Используйте макрос `METHOD_PROLOGUE` для доступа к родительскому объекту, производному от `CCmdTarget`.  
  
8. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317), и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) можно делегировать `CCmdTarget` реализации этих функций (`ExternalAddRef`, `ExternalRelease`, и `ExternalQueryInterface`).  
  
 Приведенный выше пример CPrintEditObj можно реализовать следующим образом:  
  
```  
class CPrintEditObj : public CCmdTarget  
{  
public: *// member data and member functions for CPrintEditObj go here  
 
// Interface Maps  
protected:  
    DECLARE_INTERFACE_MAP() 
 
    BEGIN_INTERFACE_PART(EditObj,
    IEditInterface)  
    STDMETHOD_(void,
    EditObject)();
END_INTERFACE_PART(EditObj) 
 
    BEGIN_INTERFACE_PART(PrintObj,
    IPrintInterface)  
    STDMETHOD_(void,
    PrintObject)();
END_INTERFACE_PART(PrintObj) 
};  
```  
  
 Указанное выше объявление создает класс, производный от `CCmdTarget`. Макрос `DECLARE_INTERFACE_MAP` указывает среде, что этот класс будет иметь настраиваемую схему интерфейсов. Кроме того, макросы `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART` определяют вложенные классы, которые в данном случае имеют имена CEditObj и CPrintObj (буква X используется только для обеспечения отличия вложенных классов от глобальных классов, которые начинаются с буквы C, и классов интерфейсов, которые начинаются с буквы I). Создаются два вложенных элемента этих классов — m_CEditObj и m_CPrintObj соответственно. Макросы автоматически объявляют [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317), и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) функции; таким образом можно объявить только функции, характерные для этого интерфейса: EditObject и PrintObject (OLE-макрос `STDMETHOD` используется, чтобы `_stdcall` и виртуальный ключевые слова, которые предоставляются соответствующим образом для целевой платформы).  
  
 Чтобы реализовать схему интерфейсов для этого класса, используйте следующий код:  
  
```  
BEGIN_INTERFACE_MAP(CPrintEditObj,
    CCmdTarget)  
    INTERFACE_PART(CPrintEditObj,
    IID_IPrintInterface,
    PrintObj)  
    INTERFACE_PART(CPrintEditObj,
    IID_IEditInterface,
    EditObj)  
END_INTERFACE_MAP()  
```  
  
 Он соединяет IID_IPrintInterface IID с m_CPrintObj, а IID_IEditInterface — с m_CEditObj. `CCmdTarget` Реализация [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) (`CCmdTarget::ExternalQueryInterface`) использует эту схему, чтобы возвратить указатели m_CPrintObj и m_CEditObj при запросе. Включать запись для `IID_IUnknown` не нужно, при запросе `IID_IUnknown` платформа будет использовать первый интерфейс в схеме (в данном случае это m_CPrintObj).  
  
 Несмотря на то что `BEGIN_INTERFACE_PART` макрос автоматически объявляются [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317) и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) функции для вас по-прежнему необходимо реализовать их:  
  
```  
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return pThis->ExternalAddRef();

}  
 
ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return pThis->ExternalRelease();

}  
 
HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(
    REFIID iid,
    void FAR* FAR* ppvObj)  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return (HRESULT)pThis->ExternalQueryInterface(&iid,
    ppvObj);

}  
 
void FAR EXPORT CEditPrintObj::XEditObj::EditObject()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj) *// code to "Edit" the object,
    whatever that means...  
}  
```  
  
 Реализация CEditPrintObj::CPrintObj будет похожа на приведенные выше определения CEditPrintObj::CEditObj. Несмотря на то что возможно создать макрос, который может использоваться для автоматического создания таких функций (а так было ранее при разработке MFC/OLE), становится трудно задавать точки останова, когда макрос создает более одной строки кода. По этой причине этот код будет расширен вручную.  
  
 При использовании реализации платформы для схем сообщений существует несколько вещей, которые не нужно было выполнять.  
  
-   Реализация QueryInterface  
  
-   Реализация AddRef и Release  
  
-   Объявление любого из этих встроенных методов для обоих интерфейсов  
  
 Кроме того, платформа использует схемы сообщений для внутренних целей. Это позволяет создавать производные объекты от класса платформы, например `COleServerDoc`, который уже поддерживает определенные интерфейсы и предоставляет замены или дополнения для интерфейсов, предоставляемых платформой. Это можно сделать, так как платформа полностью поддерживает наследование схемы интерфейсов от базового класса. Именно поэтому `BEGIN_INTERFACE_MAP` принимает имя базового класса в качестве второго параметра.  
  
> [!NOTE]
>  В общем случае нельзя повторно использовать реализацию встроенных реализаций интерфейсов OLE MFC путем простого наследования внедренных специализаций этого интерфейса от версии MFC. Это невозможно из-за использования `METHOD_PROLOGUE` макрос для получения доступа к содержащему `CCmdTarget`-подразумевает производного объекта *фиксированному смещению* внедренного объекта из `CCmdTarget`-производного объекта. Это означает, например, что нельзя наследовать внедренный XMyAdviseSink от реализации MFC в `COleClientItem::XAdviseSink`, так как XAdviseSink ожидает наличия определенного смещения относительно верхнего края объект `COleClientItem`.  
  
> [!NOTE]
>  Однако можно делегировать реализацию MFC для всех функций, для которых требуется поведение по умолчанию MFC. Это делается в реализации MFC `IOleInPlaceFrame` (XOleInPlaceFrame) в классе `COleFrameHook` (он делегирует в m_xOleInPlaceUIWindow для многих функций). Такой подход был выбран для уменьшения размера среды выполнения объектов, реализующих несколько интерфейсов. Он устраняет необходимость в обратном указателе (например, в m_pParent из примера в предыдущем разделе).  
  
### <a name="aggregation-and-interface-maps"></a>Статистическая обработка и схемы интерфейсов  
 В дополнение к поддержке изолированных COM-объектов MFC также поддерживает статистическую обработку. Статистическая обработка является довольно сложной темой, чтобы обсудить ссылаться на [статистической обработки](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx) Дополнительные сведения о статистической обработке. Эта заметка просто описывает поддержку статистической обработки, встроенную в платформу и схемы интерфейсов.  
  
 Существует два способа использования статистической обработки: (1) использование COM-объекта, поддерживающего статистическую обработку, и (2) реализация объекта, который может быть статистически вычислен другим объектом. Эти возможности можно называть «использование агрегатного объекта» и «превращение объекта в допускающий статистическую обработку». MFC поддерживает оба этих варианта.  
  
### <a name="using-an-aggregate-object"></a>Использование агрегатного объекта  
 Для использования агрегатного объекта требуется какой-либо способ связать статистическое выражение с механизмом QueryInterface. Другими словами, агрегатный объект должен работать так, как будто это собственная часть объекта. Так как этот объект привязан интерфейсов MFC выполняет сопоставление механизм в дополнение к `INTERFACE_PART` макрос, где вложенный объект сопоставляется с IID, можно также объявить Агрегатный объект как часть вашего `CCmdTarget` производного класса. Чтобы сделать это, используется макрос `INTERFACE_AGGREGATE`. Это позволяет указать переменную-член (который должен быть указателем на [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) или производного класса), являющийся для интеграции в механизм схем интерфейсов. Если указатель не имеет значение NULL, если `CCmdTarget::ExternalQueryInterface` является именем, платформа автоматически вызывает Агрегатный объект [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) функция-член, если `IID` запрошенный не является одним из собственных `IID`s поддерживаемые `CCmdTarget` сам объект.  
  
##### <a name="to-use-the-interfaceaggregate-macro"></a>Использование макроса INTERFACE_AGGREGATE  
  
1.  Объявите переменную-член (`IUnknown*`) которая будет содержать указатель на агрегатный объект.  
  
2.  Включите в схему интерфейсов макрос `INTERFACE_AGGREGATE`, который ссылается на переменную-член по имени.  
  
3.  В определенный момент (обычно во время `CCmdTarget::OnCreateAggregates`) инициализируйте переменную-член со значением, отличным от NULL.  
  
 Пример:  
  
```  
class CAggrExample : public CCmdTarget  
{  
public:  
    CAggrExample();

 
protected:  
    LPUNKNOWN m_lpAggrInner;  
    virtual BOOL OnCreateAggregates();

 
    DECLARE_INTERFACE_MAP() *// "native" interface part macros may be used here  
};  
 
CAggrExample::CAggrExample()  
{  
    m_lpAggrInner = NULL;  
}  
 
BOOL CAggrExample::OnCreateAggregates()  
{ *// wire up aggregate with correct controlling unknown  
    m_lpAggrInner = CoCreateInstance(CLSID_Example,  
    GetControllingUnknown(),
    CLSCTX_INPROC_SERVER,  
    IID_IUnknown, (LPVOID*)&m_lpAggrInner);

    if (m_lpAggrInner == NULL)  
    return FALSE; *// optionally,
    create other aggregate objects here  
    return TRUE;  
}  
 
BEGIN_INTERFACE_MAP(CAggrExample,
    CCmdTarget) *// native "INTERFACE_PART" entries go here  
    INTERFACE_AGGREGATE(CAggrExample,
    m_lpAggrInner)  
END_INTERFACE_MAP()  
```  
  
 Переменная m_lpAggrInner инициализируется в конструкторе со значением NULL. Платформа игнорирует переменную-член NULL в реализации по умолчанию [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521). `OnCreateAggregates` удобно использовать для создания агрегатных объектов. Его потребуется вызвать явным образом при создании объекта за пределами реализации `COleObjectFactory` MFC. Причина создания статистических выражений в `CCmdTarget::OnCreateAggregates` и использование `CCmdTarget::GetControllingUnknown` станут очевидными при рассмотрении создания агрегатных объектов.  
  
 Эта методика дает объекту все интерфейсы, поддерживаемые агрегатным объектом, а также все его собственные интерфейсы. Если требуется только подмножество интерфейсов, поддерживаемых статистическим выражением, можно переопределить `CCmdTarget::GetInterfaceHook`. Это позволяет очень низкого уровня по аналогии с [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521). В общем случае требуются все интерфейсы, которые поддерживает статистическое выражение.  
  
### <a name="making-an-object-implementation-aggregatable"></a>Превращение реализации объекта в допускающую статистическую обработку  
 Чтобы объект допускающим статистическую обработку, реализация [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317), и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) должны делегировать «управляющий unknown». Другими словами, для того, чтобы быть частью объекта, она должна делегировать [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317), и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) другому объекту, который также является производным от [ IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Этот «управляющий unknown» предоставляется для объекта при его создании, то есть предоставляется реализации `COleObjectFactory`. Такая реализация имеет небольшое количество издержек и в некоторых случаях является нежелательной, поэтому MFC делает ее необязательной. Чтобы сделать объект допускающим статистическую обработку, вызовите `CCmdTarget::EnableAggregation` из конструктора объекта.  
  
 Если этот объект также использует статистические выражения, необходимо обязательно передать в агрегатные объекты правильный «управляющий unknown». Обычно это [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) передается указатель на объект при создании статистического выражения. Например, параметр pUnkOuter является «управляющим unknown» для объектов, созданных с использованием `CoCreateInstance`. Можно получить правильный указатель «управляющий unknown» путем вызова `CCmdTarget::GetControllingUnknown`. Однако значение, возвращаемое из этой функции, является недопустимым во время конструктора. Поэтому рекомендуется создавать ваши статистические выражения только в переопределении `CCmdTarget::OnCreateAggregates`, где возвращаемое значение из `GetControllingUnknown` является надежным, даже если оно создано на базе реализации `COleObjectFactory`.  
  
 Не менее важно, чтобы объект изменял правильный счетчик ссылок во время добавления или освобождения искусственных счетчиков ссылок. Чтобы обеспечить это, следует всегда вызывать `ExternalAddRef` и `ExternalRelease` вместо `InternalRelease` и `InternalAddRef`. `InternalRelease` или `InternalAddRef` редко вызываются для класса, поддерживающего статистическую обработку.  
  
### <a name="reference-material"></a>Справочные материалы  
 Расширенное использование OLE, например при определении собственных интерфейсов или переопределении реализации интерфейсов OLE платформы, требует использования базового механизма схем интерфейсов.  
  
 В этом разделе рассматриваются все макросы и интерфейсы API, которые используются для реализации этих дополнительных функций.  
  
### <a name="ccmdtargetenableaggregation--function-description"></a>CCmdTarget::EnableAggregation — описание функции  
  
```  
 
void EnableAggregation();

 
```  
  
## <a name="remarks"></a>Примечания  
 Вызовите эту функцию в конструкторе производного класса, если хотите обеспечить поддержку статистической обработки OLE для объектов этого типа. При этом подготавливается специальная реализация IUnknown, которая необходима для агрегатных объектов.  
  
### <a name="ccmdtargetexternalqueryinterface--function-description"></a>CCmdTarget::ExternalQueryInterface — описание функции  
  
```  
 
    DWORD ExternalQueryInterface(constvoidFAR* lpIID, LPVOIDFAR* ppvObj);
```  
  
## <a name="remarks"></a>Примечания  
  
#### <a name="parameters"></a>Параметры  
 `lpIID`  
 Дальний указатель на IID (первый аргумент QueryInterface)  
  
 `ppvObj`  
 Указатель на IUnknown * (второй аргумент QueryInterface)  
  
## <a name="remarks"></a>Примечания  
 Вызовите эту функцию в реализации IUnknown для каждого интерфейса, который реализуется вашим классом. Эта функция предоставляет стандартную управляемую данными реализацию QueryInterface, основанную на схеме интерфейсов объекта. Это необходимо, чтобы привести возвращаемое значение к HRESULT. Если объект является статистическим выражением, вместо использования локальной схемы интерфейсов эта функция вызывает «управляющий IUnknown».  
  
### <a name="ccmdtargetexternaladdref--function-description"></a>CCmdTarget::ExternalAddRef — описание функции  
  
```  
 
DWORD ExternalAddRef();

 
```  
  
## <a name="remarks"></a>Примечания  
 Вызовите эту функцию в реализации IUnknown::AddRef для каждого интерфейса, который реализуется вашим классом. Возвращаемое значение является новым счетчиком ссылок для объекта CCmdTarget. Если объект является статистическим выражением, вместо изменения локального счетчика ссылок эта функция вызывает «управляющий IUnknown».  
  
### <a name="ccmdtargetexternalrelease--function-description"></a>CCmdTarget::ExternalRelease — описание функции  
  
```  
 
DWORD ExternalRelease();

 
```  
  
## <a name="remarks"></a>Примечания  
 Вызовите эту функцию в реализации IUnknown::Release для каждого интерфейса, который реализуется вашим классом. Возвращаемое значение указывает новый счетчик для объекта. Если объект является статистическим выражением, вместо изменения локального счетчика ссылок эта функция вызывает «управляющий IUnknown».  
  
### <a name="declareinterfacemap--macro-description"></a>DECLARE_INTERFACE_MAP — описание макроса  
  
```  
 
DECLARE_INTERFACE_MAP  
 
```  
  
## <a name="remarks"></a>Примечания  
 Используйте этот макрос в любом классе, производном от `CCmdTarget`, который будет иметь схему интерфейсов. Его использование во многом идентично использованию `DECLARE_MESSAGE_MAP`. Вызов этого макроса следует поместить в определение класса, обычно для этого используется файл заголовка (. (H). Класс с `DECLARE_INTERFACE_MAP` должен определять схему интерфейсов в файле реализации (CPP) с использованием макросов `BEGIN_INTERFACE_MAP` и `END_INTERFACE_MAP`.  
  
### <a name="begininterfacepart-and-endinterfacepart--macro-descriptions"></a>BEGIN_INTERFACE_PART и END_INTERFACE_PART — описания макросов  
  
```  
 
    BEGIN_INTERFACE_PART(
 localClass,   
    iface);

END_INTERFACE_PART(
 localClass)  
```  
  
## <a name="remarks"></a>Примечания  
  
#### <a name="parameters"></a>Параметры  
 `localClass`  
 Имя класса, реализующего интерфейс.  
  
 `iface`  
 Имя интерфейса, реализуемого с помощью данного класса.  
  
## <a name="remarks"></a>Примечания  
 Для каждого интерфейса, реализуемого вашим классом, необходимо иметь пару из `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART`. Эти макросы определяют локальный класс, производный от определенного вами интерфейса OLE, а также внедренную переменную-член этого класса. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317), и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) элементы объявлены автоматически. Необходимо включить объявления для других функций-членов, являющихся частью реализуемого интерфейса (эти объявления размещаются между макросами `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART`).  
  
 Аргумент `iface` является интерфейсом OLE, который вы хотите реализовать, например `IAdviseSink` или `IPersistStorage` (или собственный пользовательский интерфейс).  
  
 Аргумент `localClass` является именем локального класса, который будет определен. К имени будет автоматически добавляться буква X. Это соглашение об именовании используется для предотвращения конфликтов с глобальными классами, имеющими такое же имя. Кроме того, имя внедренного члена совпадает с именем `localClass`, за исключением наличия у него префикса «m_x».  
  
 Пример:  
  
```  
BEGIN_INTERFACE_PART(MyAdviseSink,
    IAdviseSink)  
    STDMETHOD_(void,
    OnDataChange)(LPFORMATETC,
    LPSTGMEDIUM);

    STDMETHOD_(void,
    OnViewChange)(DWORD,
    LONG);

    STDMETHOD_(void,
    OnRename)(LPMONIKER);

 STDMETHOD_(void,
    OnSave)();
STDMETHOD_(void,
    OnClose)();

END_INTERFACE_PART(MyAdviseSink) 
```  
  
 Этот код определяет локальный класс с именем XMyAdviseSink, являющийся производным от IAdviseSink, и член класса, в котором он определен, с именем m_xMyAdviseSink.Note:  
  
> [!NOTE]
>  Строки, начинающиеся с `STDMETHOD`_ фактически копируются из OLE2. H и немного изменены. Их копирование из OLE2.H позволяет уменьшить число трудноразрешимых ошибок.  
  
### <a name="begininterfacemap-and-endinterfacemap--macro-descriptions"></a>BEGIN_INTERFACE_MAP и END_INTERFACE_MAP — описания макросов  
  
```  
 
    BEGIN_INTERFACE_MAP(
 theClass,   
    baseClass)END_INTERFACE_MAP 
```  
  
## <a name="remarks"></a>Примечания  
  
#### <a name="parameters"></a>Параметры  
 `theClass`  
 Класс, в котором определяется схема интерфейсов.  
  
 `baseClass`  
 Класс, от которого `theClass` является производным.  
  
## <a name="remarks"></a>Примечания  
 Макросы `BEGIN_INTERFACE_MAP` и `END_INTERFACE_MAP` используются в файле реализации для фактического определения схемы интерфейсов. Для каждого реализованного там интерфейса имеется один или несколько вызовов макросов `INTERFACE_PART`. Для каждого статистического выражения, используемого классом, имеется один вызов макроса `INTERFACE_AGGREGATE`.  
  
### <a name="interfacepart--macro-description"></a>INTERFACE_PART — описание макроса  
  
```  
 
    INTERFACE_PART(
 theClass,   
    iid, 
    localClass) 
```  
  
## <a name="remarks"></a>Примечания  
  
#### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса, содержащего схему интерфейсов.  
  
 `iid`  
 `IID`, который будет сопоставляться с внедренным классом.  
  
 `localClass`  
 Имя локального класса (без буквы X).  
  
## <a name="remarks"></a>Примечания  
 Этот макрос используется между макросом `BEGIN_INTERFACE_MAP` и макросом `END_INTERFACE_MAP` для каждого интерфейса, поддерживаемого объектом. Он позволяет сопоставить IID с членом класса, обозначенного `theClass` и `localClass`. К `localClass` будет автоматически добавлено «m_x». Обратите внимание, что с одним членом можно сопоставить больше одного `IID`. Это очень удобно, если вы реализуете только «самый производный» интерфейс и хотите также предоставить все промежуточные интерфейсы. Хорошим примером этого является интерфейс `IOleInPlaceFrameWindow`. Иерархия выглядит следующим образом.  
  
```  
IUnknown  
    IOleWindow 
    IOleUIWindow 
    IOleInPlaceFrameWindow 
```  
  
 Если объект реализует интерфейс `IOleInPlaceFrameWindow`, клиент может `QueryInterface` на любой из этих интерфейсов: `IOleUIWindow`, `IOleWindow`, или [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), кроме «самого производного» интерфейса `IOleInPlaceFrameWindow` (той фактически являются Реализация). Для обработки в данном случае может потребоваться более одного макроса `INTERFACE_PART`, чтобы сопоставить каждый базовый интерфейс с интерфейсом `IOleInPlaceFrameWindow`:  
  
 В файле определения класса:  
  
```  
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)  
```  
  
 В файле реализации класса:  
  
```  
BEGIN_INTERFACE_MAP(CMyWnd,
    CFrameWnd)  
    INTERFACE_PART(CMyWnd,
    IID_IOleWindow,
    MyFrameWindow)  
    INTERFACE_PART(CMyWnd,
    IID_IOleUIWindow,
    MyFrameWindow)  
    INTERFACE_PART(CMyWnd,
    IID_IOleInPlaceFrameWindow,
    MyFrameWindow)  
END_INTERFACE_MAP  
```  
  
 Платформа самостоятельно обрабатывает IUnknown, так как он всегда является обязательным.  
  
### <a name="interfacepart--macro-description"></a>INTERFACE_PART — описание макроса  
  
```  
 
    INTERFACE_AGGREGATE(
 theClass,   
    theAggr) 
```  
  
## <a name="remarks"></a>Примечания  
  
#### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса, содержащего схему интерфейсов.  
  
 `theAggr`  
 Имя переменной-члена, подлежащей статистической обработке.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос применяется, чтобы сообщить платформе о том, что класс использует агрегатный объект. Его следует разместить между макросами `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART`. Агрегатный объект представляет собой отдельный объект, производный от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). С помощью статистического выражения и макроса `INTERFACE_AGGREGATE` можно сделать так, чтобы все интерфейсы, которые поддерживает статистическое выражение, выглядели так, как если бы поддерживались непосредственно объектом. `theAggr` Аргумент — это просто имя переменной — члена класса, который является производным от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) (прямо или косвенно). При помещении в схему интерфейсов все макросы `INTERFACE_AGGREGATE` должны следовать за макросами `INTERFACE_PART`.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

