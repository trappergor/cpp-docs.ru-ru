---
title: "TN038. Реализация MFC/OLE IUnknown | Microsoft Docs"
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
  - "макросы агрегирования [C++]"
  - "BEGIN_INTERFACE_MAP - макрос"
  - "BEGIN_INTERFACE_PART - макрос"
  - "интерфейсы COM, базовый интерфейс"
  - "DECLARE_INTERFACE_MAP - макрос"
  - "END_INTERFACE_MAP - макрос"
  - "END_INTERFACE_PART - макрос"
  - "INTERFACE_PART - макрос"
  - "IUnknown - интерфейс"
  - "METHOD_PROLOGUE - макрос"
  - "OLE [C++], реализация интерфейса IUnknown"
  - "STDMETHOD - макрос"
  - "TN038"
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN038. Реализация MFC/OLE IUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию.  В результате некоторые процедуры и разделы могут быть устаревшими или неверными.  Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 В основе OLE 2 лежит модель COM OLE.  Модель COM определяет стандарт взаимодействия совместно действующих объектов.  Сюда входят сведения о самом «объекте», включая то, какие методы подготавливаются для отправки в объект.  Модель COM также определяет базовый класс, от которого наследуются все COM\-совместимые классы.  Этот базовый класс называется [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  Хотя интерфейс [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) называется классом C\+\+, модель COM не относится к какому\-либо определенному языку — она может быть реализована на C, PASCAL или любом другом языке, поддерживающем двоичное размещение COM\-объекта.  
  
 В рамках OLE все классы, производные от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), называются «интерфейсами». Это важное различие, поскольку «интерфейс», например [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), не несет с собой реализации.  Он просто определяет протокол, по которому взаимодействуют объекты, а не особенности этих реализаций.  Это оправдано для системы, которая нацелена на максимальную гибкость.  За реализацию поведения по умолчанию для программ MFC\/C\+\+ отвечает MFC.  
  
 Чтобы понять реализацию [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) MFC, необходимо сначала разобраться, что собой представляет этот интерфейс.  Ниже определена упрощенная версия [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
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
  
 Функции\-члены [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) управляют памятью объекта.  Модель COM использует схему подсчета ссылок для отслеживания объектов.  Ссылка на объект никогда не указывается напрямую, как это происходит в C\+\+.  Вместо этого ссылка на COM\-объекты всегда осуществляется через указатель.  Чтобы освободить объект после завершения его использования владельцем, вызывается член [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) объекта \(а не оператор delete, как это происходит в случае с обычным объектом C\+\+\).  Механизм подсчета ссылок позволяет управлять несколькими ссылками на один объект.  Реализация [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) ведет подсчет ссылок для объекта — объект не удаляется, пока число его ссылок не достигнет нуля.  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) довольно легко использовать с точки зрения реализации.  Вот пример простой реализации:  
  
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
  
 Функция\-член [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) немного интереснее.  Объект, функциями\-членами которого являются [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [функция\-член](http://msdn.microsoft.com/library/windows/desktop/ms682317) малоинтересен, было бы желательно заставить объект выполнять больше функций, чем определено [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  Именно для этого прекрасно подходит [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  Он позволяет получать разный «интерфейс» на базе одного и того же объекта.  Эти интерфейсы обычно являются производными от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) и добавляют дополнительную функциональность путем добавления новых функций\-членов.  COM\-интерфейсы никогда не имеют объявляемых в интерфейсе переменных\-членов, а все функции\-члены объявлены как чисто виртуальные.  Например:  
  
```  
class IPrintInterface : public IUnknown  
{  
public:  
    virtual void PrintObject() = 0;  
};  
```  
  
 Чтобы получить IPrintInterface при наличии только [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), вызовите [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) с помощью `IID` из **IPrintInterface**.  `IID` представляет собой 128\-разрядное число, которое однозначно определяет интерфейс.  `IID` присутствует для каждого интерфейса, определенного вами или OLE.  Если `pUnk` является указателем на объект [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), код для получения IPrintInterface из него может иметь следующий вид:  
  
```  
IPrintInterface* pPrint = NULL;  
if (pUnk->QueryInterface(IID_IPrintInterface,   
    (void**)&pPrint) == NOERROR)  
{  
    pPrint->PrintObject();  
    pPrint->Release();     
        // release pointer obtained via QueryInterface  
}  
```  
  
 Это кажется довольно простым, но как реализовать объект, поддерживающий как IPrintInterface, так и [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)?  В данном случае это несложно, поскольку IPrintInterface является производным непосредственно от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) — при реализации IPrintInterface поддержка [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) обеспечивается автоматически.  Пример:  
  
```  
class CPrintObj : public CPrintInterface  
{  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);  
    virtual ULONG AddRef();  
    virtual ULONG Release();  
    virtual void PrintObject();  
};  
```  
  
 Реализация [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) будет точно такой же, как описанная выше.  **CPrintObj::QueryInterface** будет выглядеть примерно следующим образом:  
  
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
  
 Как видите, если распознается идентификатор интерфейса \(IID\), в объект возвращается указатель, в противном случае возникает ошибка.  Обратите внимание и на то, что успешное выполнение [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) дает подразумеваемый [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379).  Конечно же, необходимо также реализовать CEditObj::Print.  Это просто, поскольку IPrintInterface является производным непосредственно от интерфейса [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  Однако, если требуется поддержка двух различных интерфейсов, которые являются производными от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), необходимо учитывать следующее:  
  
```  
class IEditInterface : public IUnkown  
{  
public:  
    virtual void EditObject() = 0;  
};  
```  
  
 Хотя существует несколько разных способов реализации класса, поддерживающего как IEditInterface, так и IPrintInterface, включая использование множественного наследования C\+\+, эта заметка будет посвящена использованию вложенных классов для реализации данной функциональности.  
  
```  
class CEditPrintObj  
{  
public:  
    CEditPrintObj();  
  
    HRESULT QueryInterface(REFIID iid, void**);  
    ULONG AddRef();  
    ULONG Release();  
    DWORD m_dwRef;  
  
    class CPrintObj : public IPrintInterface  
    {  
    public:  
        CEditPrintObj* m_pParent;  
        virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);  
        virtual ULONG AddRef();  
        virtual ULONG Release();  
    } m_printObj;  
  
    class CEditObj : public IEditInterface  
    {  
    public:  
        CEditPrintObj* m_pParent;  
        virtual ULONG QueryInterface(REFIID iid, void** ppvObj);  
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
  
HRESULT CEditPrintObj::QueryInterface(REFIID iid, void** ppvObj)  
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
    REFIID iid, void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid, ppvObj);   
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
    REFIID iid, void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid, ppvObj);   
}  
```  
  
 Обратите внимание, что основная часть реализации [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) помещается в класс CEditPrintObj вместо того, чтобы дублировать код в CEditPrintObj::CEditObj и CEditPrintObj::CPrintObj.  Это уменьшает объем кода и помогает избежать ошибок.  Самое главное здесь то, что из интерфейса IUnknown можно вызвать [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) для получения любого интерфейса который объект должен поддерживать, а из любого из этих интерфейсов можно сделать то же самое.  Это означает, что все функции [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), доступные из каждого интерфейса, должны вести себя точно так же.  Чтобы эти внедренные объекты вызвали реализацию во «внешнем объекте», используется обратный указатель \(m\_pParent\).  Указатель m\_pParent инициализируется во время выполнения конструктора CEditPrintObj.  Затем следует реализовать CEditPrintObj::CPrintObj::PrintObject, а также CEditPrintObj::CEditObj::EditObject.  Потребовалось написать довольно большой объем кода для реализации одной функции — возможности изменения объекта.  К счастью, интерфейсы крайне редко имеют только одну функцию\-член \(хотя такое и случается\), и в этом случае EditObject и PrintObject обычно объединяются в единый интерфейс.  
  
 Такой простой сценарий требует слишком долгих пояснений и слишком большого объема кода.  Классы MFC\/OLE предоставляют более простую альтернативу.  Реализация MFC использует методику, аналогичную использованию программы\-оболочки для сообщений Windows с помощью схем сообщений.  Этот компонент называется *схемы интерфейсов* и рассматривается в следующем разделе.  
  
## Схемы интерфейсов MFC  
 MFC\/OLE включает в себя реализацию «Схемы интерфейсов», аналогичную компонентам «Схемы сообщений» и «Схемы подготовки к отправке» MFC в рамках концепции и выполнения.  Схемы интерфейсов MFC имеют следующие основные возможности.  
  
-   Стандартная реализация [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), встроенная в класс `CCmdTarget`.  
  
-   Обслуживание счетчика ссылок, измененное [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)  
  
-   Управляемая данными реализация [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)  
  
 Кроме того, схемы интерфейсов поддерживают следующие дополнительные возможности.  
  
-   Поддержка создания COM\-объектов, допускающих статистическую обработку  
  
-   Поддержка использования агрегатных объектов в реализации COM\-объекта  
  
-   Реализация является обрабатываемой и расширяемой  
  
 Дополнительные сведения о статистической обработке см. в разделе [Статистическая обработка](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx).  
  
 Поддержка схем интерфейсов MFC заключена в класс `CCmdTarget`.  `CCmdTarget` *имеет* счетчик ссылок, а также все функции\-члены, связанные с реализацией [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) \(например, счетчик ссылок находится в `CCmdTarget`\).  Чтобы создать класс, поддерживающий модель COM OLE, создайте класс, производный от `CCmdTarget`, и используйте различные макросы и функции\-члены `CCmdTarget` для реализации требуемых интерфейсов.  Реализация MFC использует вложенные классы для определения каждой реализации интерфейса, что во многом похоже на приведенный выше пример.  Эта задача упрощается благодаря стандартной реализации IUnknown, а также набору макросов, позволяющих исключить некоторые из повторяющихся частей кода.  
  
## Основы использования схем интерфейсов  
  
#### Реализация класса с помощью схем интерфейсов MFC  
  
1.  Создайте класс, который явно или косвенно является от `CCmdTarget`.  
  
2.  Используйте функцию `DECLARE_INTERFACE_MAP` в определении производного класса.  
  
3.  Для каждого интерфейса, поддержку которого требуется обеспечить, используйте макросы `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART` в определении класса.  
  
4.  В файле реализации воспользуйтесь макросами `BEGIN_INTERFACE_MAP` и `END_INTERFACE_MAP` для определения схемы интерфейсов класса.  
  
5.  Для каждого поддерживаемого идентификатора интерфейса используйте макрос `INTERFACE_PART` между макросами `BEGIN_INTERFACE_MAP` и `END_INTERFACE_MAP`, чтобы сопоставить IID с конкретной частью класса.  
  
6.  Реализуйте каждый из вложенных классов, представляющих интерфейсы, которые вы поддерживаете.  
  
7.  Используйте макрос `METHOD_PROLOGUE` для доступа к родительскому объекту, производному от `CCmdTarget`.  
  
8.  [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317), и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) могут осуществлять делегирование реализации `CCmdTarget` этих функций \(`ExternalAddRef`, `ExternalRelease` и `ExternalQueryInterface`\).  
  
 Приведенный выше пример CPrintEditObj можно реализовать следующим образом:  
  
```  
class CPrintEditObj : public CCmdTarget  
{  
public:  
    // member data and member functions for CPrintEditObj go here  
  
// Interface Maps  
protected:  
    DECLARE_INTERFACE_MAP()  
  
    BEGIN_INTERFACE_PART(EditObj, IEditInterface)  
        STDMETHOD_(void, EditObject)();  
    END_INTERFACE_PART(EditObj)  
  
    BEGIN_INTERFACE_PART(PrintObj, IPrintInterface)  
        STDMETHOD_(void, PrintObject)();  
    END_INTERFACE_PART(PrintObj)  
};  
```  
  
 Указанное выше объявление создает класс, производный от `CCmdTarget`.  Макрос `DECLARE_INTERFACE_MAP` указывает среде, что этот класс будет иметь настраиваемую схему интерфейсов.  Кроме того, макросы `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART` определяют вложенные классы, которые в данном случае имеют имена CEditObj и CPrintObj \(буква X используется только для обеспечения отличия вложенных классов от глобальных классов, которые начинаются с буквы C, и классов интерфейсов, которые начинаются с буквы I\).  Создаются два вложенных элемента этих классов — m\_CEditObj и m\_CPrintObj соответственно.  Макросы автоматически объявляют функции [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521); таким образом, можно объявить только функции, характерные для этого интерфейса: EditObject и PrintObject \(OLE\-макрос `STDMETHOD` используется, чтобы ключевые слова `_stdcall` и virtual предоставлялись корректно в соответствии с целевой платформой\).  
  
 Чтобы реализовать схему интерфейсов для этого класса, используйте следующий код:  
  
```  
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)  
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)  
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)  
END_INTERFACE_MAP()  
```  
  
 Он соединяет IID\_IPrintInterface IID с m\_CPrintObj, а IID\_IEditInterface — с m\_CEditObj.  Реализация `CCmdTarget` для [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) \(`CCmdTarget::ExternalQueryInterface`\) использует эту схему, чтобы возвратить указатели m\_CPrintObj и m\_CEditObj при получении соответствующего запроса.  Включать запись для `IID_IUnknown` не нужно, при запросе `IID_IUnknown` платформа будет использовать первый интерфейс в схеме \(в данном случае это m\_CPrintObj\).  
  
 Несмотря на то что макрос `BEGIN_INTERFACE_PART` автоматически объявил функции [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), их по\-прежнему необходимо реализовать:  
  
```  
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return pThis->ExternalAddRef();  
}  
  
ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return pThis->ExternalRelease();  
}  
  
HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(  
    REFIID iid, void FAR* FAR* ppvObj)  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return (HRESULT)pThis->ExternalQueryInterface(&iid, ppvObj);  
}  
  
void FAR EXPORT CEditPrintObj::XEditObj::EditObject()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    // code to "Edit" the object, whatever that means...  
}  
```  
  
 Реализация CEditPrintObj::CPrintObj будет похожа на приведенные выше определения CEditPrintObj::CEditObj.  Несмотря на то что возможно создать макрос, который может использоваться для автоматического создания таких функций \(а так было ранее при разработке MFC\/OLE\), становится трудно задавать точки останова, когда макрос создает более одной строки кода.  По этой причине этот код будет расширен вручную.  
  
 При использовании реализации платформы для схем сообщений существует несколько вещей, которые не нужно было выполнять.  
  
-   Реализация QueryInterface  
  
-   Реализация AddRef и Release  
  
-   Объявление любого из этих встроенных методов для обоих интерфейсов  
  
 Кроме того, платформа использует схемы сообщений для внутренних целей.  Это позволяет создавать производные объекты от класса платформы, например `COleServerDoc`, который уже поддерживает определенные интерфейсы и предоставляет замены или дополнения для интерфейсов, предоставляемых платформой.  Это можно сделать, так как платформа полностью поддерживает наследование схемы интерфейсов от базового класса.  Именно поэтому `BEGIN_INTERFACE_MAP` принимает имя базового класса в качестве второго параметра.  
  
> [!NOTE]
>  В общем случае нельзя повторно использовать реализацию встроенных реализаций интерфейсов OLE MFC путем простого наследования внедренных специализаций этого интерфейса от версии MFC.  Это невозможно, поскольку использование макроса `METHOD_PROLOGUE` для получения доступа к содержащему производному от `CCmdTarget` объекту подразумевает *фиксированное смещение* внедренного объекта относительно объекта, производного от `CCmdTarget`.  Это означает, например, что нельзя наследовать внедренный XMyAdviseSink от реализации MFC в `COleClientItem::XAdviseSink`, так как XAdviseSink ожидает наличия определенного смещения относительно верхнего края объект `COleClientItem`.  
  
> [!NOTE]
>  Однако можно делегировать реализацию MFC для всех функций, для которых требуется поведение по умолчанию MFC.  Это делается в реализации MFC `IOleInPlaceFrame` \(XOleInPlaceFrame\) в классе `COleFrameHook` \(он делегирует в m\_xOleInPlaceUIWindow для многих функций\).  Такой подход был выбран для уменьшения размера среды выполнения объектов, реализующих несколько интерфейсов. Он устраняет необходимость в обратном указателе \(например, в m\_pParent из примера в предыдущем разделе\).  
  
### Статистическая обработка и схемы интерфейсов  
 В дополнение к поддержке изолированных COM\-объектов MFC также поддерживает статистическую обработку.  Статистическая обработка является довольно сложной темой, чтобы ее можно было рассмотреть здесь, для получения сведений по данному вопросу см. радел [Статистическая обработка](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx).  Эта заметка просто описывает поддержку статистической обработки, встроенную в платформу и схемы интерфейсов.  
  
 Существует два способа использования статистической обработки: \(1\) использование COM\-объекта, поддерживающего статистическую обработку, и \(2\) реализация объекта, который может быть статистически вычислен другим объектом.  Эти возможности можно называть «использование агрегатного объекта» и «превращение объекта в допускающий статистическую обработку».  MFC поддерживает оба этих варианта.  
  
### Использование агрегатного объекта  
 Для использования агрегатного объекта требуется какой\-либо способ связать статистическое выражение с механизмом QueryInterface.  Другими словами, агрегатный объект должен работать так, как будто это собственная часть объекта.  Так как же этот объект привязан к механизму схем интерфейсов MFC?  В дополнение к макросу `INTERFACE_PART`, где вложенный объект сопоставляется с IID, можно также объявить агрегатный объект как часть вашего производного класса `CCmdTarget`.  Чтобы сделать это, используется макрос `INTERFACE_AGGREGATE`.  Это позволяет указать переменную\-член \(которая должна быть указателем на [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) или производный класс\), предназначенную для интеграции в механизм схем интерфейсов.  Если при вызове `CCmdTarget::ExternalQueryInterface` указатель имеет значение, отличное от NULL, платформа автоматически вызывает функцию\-член [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) агрегатного объекта, если запрошенный `IID` не является одним из собственных `IID`, поддерживаемых самим объектом `CCmdTarget`.  
  
##### Использование макроса INTERFACE\_AGGREGATE  
  
1.  Объявите переменную\-член \(`IUnknown*`\) которая будет содержать указатель на агрегатный объект.  
  
2.  Включите в схему интерфейсов макрос `INTERFACE_AGGREGATE`, который ссылается на переменную\-член по имени.  
  
3.  В определенный момент \(обычно во время `CCmdTarget::OnCreateAggregates`\) инициализируйте переменную\-член со значением, отличным от NULL.  
  
 Пример:  
  
```  
class CAggrExample : public CCmdTarget  
{  
public:  
    CAggrExample();  
  
protected:  
    LPUNKNOWN m_lpAggrInner;  
    virtual BOOL OnCreateAggregates();  
  
    DECLARE_INTERFACE_MAP()  
    // "native" interface part macros may be used here  
};  
  
CAggrExample::CAggrExample()  
{  
    m_lpAggrInner = NULL;  
}  
  
BOOL CAggrExample::OnCreateAggregates()  
{  
    // wire up aggregate with correct controlling unknown  
    m_lpAggrInner = CoCreateInstance(CLSID_Example,  
        GetControllingUnknown(), CLSCTX_INPROC_SERVER,  
        IID_IUnknown, (LPVOID*)&m_lpAggrInner);  
    if (m_lpAggrInner == NULL)  
        return FALSE;  
    // optionally, create other aggregate objects here  
    return TRUE;  
}  
  
BEGIN_INTERFACE_MAP(CAggrExample, CCmdTarget)  
    // native "INTERFACE_PART" entries go here  
    INTERFACE_AGGREGATE(CAggrExample, m_lpAggrInner)  
END_INTERFACE_MAP()  
```  
  
 Переменная m\_lpAggrInner инициализируется в конструкторе со значением NULL.  Платформа игнорирует переменную\-член NULL в реализации по умолчанию [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  `OnCreateAggregates` удобно использовать для создания агрегатных объектов.  Его потребуется вызвать явным образом при создании объекта за пределами реализации `COleObjectFactory` MFC.  Причина создания статистических выражений в `CCmdTarget::OnCreateAggregates` и использование `CCmdTarget::GetControllingUnknown` станут очевидными при рассмотрении создания агрегатных объектов.  
  
 Эта методика дает объекту все интерфейсы, поддерживаемые агрегатным объектом, а также все его собственные интерфейсы.  Если требуется только подмножество интерфейсов, поддерживаемых статистическим выражением, можно переопределить `CCmdTarget::GetInterfaceHook`.  Это позволяет получить возможность обработки на очень низком уровне по аналогии с [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  В общем случае требуются все интерфейсы, которые поддерживает статистическое выражение.  
  
### Превращение реализации объекта в допускающую статистическую обработку  
 Чтобы сделать объект допускающим статистическую обработку, реализация [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) должна делегировать «управляющему unknown». Другими словами, чтобы быть частью объекта, она должна делегировать [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) другому объекту, который также является производным от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  Этот «управляющий unknown» предоставляется для объекта при его создании, то есть предоставляется реализации `COleObjectFactory`.  Такая реализация имеет небольшое количество издержек и в некоторых случаях является нежелательной, поэтому MFC делает ее необязательной.  Чтобы сделать объект допускающим статистическую обработку, вызовите `CCmdTarget::EnableAggregation` из конструктора объекта.  
  
 Если этот объект также использует статистические выражения, необходимо обязательно передать в агрегатные объекты правильный «управляющий unknown».  Обычно этот указатель [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) передается объекту при создании статистического выражения.  Например, параметр pUnkOuter является «управляющим unknown» для объектов, созданных с использованием `CoCreateInstance`.  Можно получить правильный указатель «управляющий unknown» путем вызова `CCmdTarget::GetControllingUnknown`.  Однако значение, возвращаемое из этой функции, является недопустимым во время конструктора.  Поэтому рекомендуется создавать ваши статистические выражения только в переопределении `CCmdTarget::OnCreateAggregates`, где возвращаемое значение из `GetControllingUnknown` является надежным, даже если оно создано на базе реализации `COleObjectFactory`.  
  
 Не менее важно, чтобы объект изменял правильный счетчик ссылок во время добавления или освобождения искусственных счетчиков ссылок.  Чтобы обеспечить это, следует всегда вызывать `ExternalAddRef` и `ExternalRelease` вместо `InternalRelease` и `InternalAddRef`.  `InternalRelease` или `InternalAddRef` редко вызываются для класса, поддерживающего статистическую обработку.  
  
### Справочные материалы  
 Расширенное использование OLE, например при определении собственных интерфейсов или переопределении реализации интерфейсов OLE платформы, требует использования базового механизма схем интерфейсов.  
  
 В этом разделе рассматриваются все макросы и интерфейсы API, которые используются для реализации этих дополнительных функций.  
  
### CCmdTarget::EnableAggregation — описание функции  
  
```  
  
void EnableAggregation();  
```  
  
## Примечания  
 Вызовите эту функцию в конструкторе производного класса, если хотите обеспечить поддержку статистической обработки OLE для объектов этого типа.  При этом подготавливается специальная реализация IUnknown, которая необходима для агрегатных объектов.  
  
### CCmdTarget::ExternalQueryInterface — описание функции  
  
```  
  
              DWORD ExternalQueryInterface(    const void FAR* lpIID,    LPVOID FAR* ppvObj   
);  
```  
  
## Примечания  
  
#### Параметры  
 `lpIID`  
 Дальний указатель на IID \(первый аргумент QueryInterface\)  
  
 `ppvObj`  
 Указатель на IUnknown \* \(второй аргумент QueryInterface\)  
  
## Примечания  
 Вызовите эту функцию в реализации IUnknown для каждого интерфейса, который реализуется вашим классом.  Эта функция предоставляет стандартную управляемую данными реализацию QueryInterface, основанную на схеме интерфейсов объекта.  Это необходимо, чтобы привести возвращаемое значение к HRESULT.  Если объект является статистическим выражением, вместо использования локальной схемы интерфейсов эта функция вызывает «управляющий IUnknown».  
  
### CCmdTarget::ExternalAddRef — описание функции  
  
```  
  
DWORD ExternalAddRef();  
```  
  
## Примечания  
 Вызовите эту функцию в реализации IUnknown::AddRef для каждого интерфейса, который реализуется вашим классом.  Возвращаемое значение является новым счетчиком ссылок для объекта CCmdTarget.  Если объект является статистическим выражением, вместо изменения локального счетчика ссылок эта функция вызывает «управляющий IUnknown».  
  
### CCmdTarget::ExternalRelease — описание функции  
  
```  
  
DWORD ExternalRelease();  
  
```  
  
## Примечания  
 Вызовите эту функцию в реализации IUnknown::Release для каждого интерфейса, который реализуется вашим классом.  Возвращаемое значение указывает новый счетчик для объекта.  Если объект является статистическим выражением, вместо изменения локального счетчика ссылок эта функция вызывает «управляющий IUnknown».  
  
### DECLARE\_INTERFACE\_MAP — описание макроса  
  
```  
  
DECLARE_INTERFACE_MAP  
  
```  
  
## Примечания  
 Используйте этот макрос в любом классе, производном от `CCmdTarget`, который будет иметь схему интерфейсов.  Его использование во многом идентично использованию `DECLARE_MESSAGE_MAP`.  Вызов этого макроса следует поместить в определение класса, обычно для этого используется файл заголовка \(. \(H\).  Класс с `DECLARE_INTERFACE_MAP` должен определять схему интерфейсов в файле реализации \(CPP\) с использованием макросов `BEGIN_INTERFACE_MAP` и `END_INTERFACE_MAP`.  
  
### BEGIN\_INTERFACE\_PART и END\_INTERFACE\_PART — описания макросов  
  
```  
  
              BEGIN_INTERFACE_PART(   
   localClass,  
   iface   
);  
END_INTERFACE_PART(   
   localClass   
)  
```  
  
## Примечания  
  
#### Параметры  
 l`ocalClass`  
 Имя класса, реализующего интерфейс.  
  
 `iface`  
 Имя интерфейса, реализуемого с помощью данного класса.  
  
## Примечания  
 Для каждого интерфейса, реализуемого вашим классом, необходимо иметь пару из `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART`.  Эти макросы определяют локальный класс, производный от определенного вами интерфейса OLE, а также внедренную переменную\-член этого класса.  Члены [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) и [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) объявляются автоматически.  Необходимо включить объявления для других функций\-членов, являющихся частью реализуемого интерфейса \(эти объявления размещаются между макросами `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART`\).  
  
 Аргумент `iface` является интерфейсом OLE, который вы хотите реализовать, например `IAdviseSink` или `IPersistStorage` \(или собственный пользовательский интерфейс\).  
  
 Аргумент `localClass` является именем локального класса, который будет определен.  К имени будет автоматически добавляться буква X.  Это соглашение об именовании используется для предотвращения конфликтов с глобальными классами, имеющими такое же имя.  Кроме того, имя внедренного члена совпадает с именем `localClass`, за исключением наличия у него префикса «m\_x».  
  
 Пример:  
  
```  
BEGIN_INTERFACE_PART(MyAdviseSink, IAdviseSink)  
   STDMETHOD_(void,OnDataChange)(LPFORMATETC, LPSTGMEDIUM);  
   STDMETHOD_(void,OnViewChange)(DWORD, LONG);  
   STDMETHOD_(void,OnRename)(LPMONIKER);  
   STDMETHOD_(void,OnSave)();  
   STDMETHOD_(void,OnClose)();  
END_INTERFACE_PART(MyAdviseSink)  
```  
  
 Этот код определяет локальный класс с именем XMyAdviseSink, являющийся производным от IAdviseSink, и член класса, в котором он определен, с именем m\_xMyAdviseSink.Note:  
  
> [!NOTE]
>  Строки, начинающиеся с `STDMETHOD`\_, фактически скопированы из OLE2.H с небольшими изменениями.  Их копирование из OLE2.H позволяет уменьшить число трудноразрешимых ошибок.  
  
### BEGIN\_INTERFACE\_MAP и END\_INTERFACE\_MAP — описания макросов  
  
```  
  
              BEGIN_INTERFACE_MAP(   
   theClass,  
   baseClass   
) END_INTERFACE_MAP  
```  
  
## Примечания  
  
#### Параметры  
 `theClass`  
 Класс, в котором определяется схема интерфейсов.  
  
 `baseClass`  
 Класс, от которого `theClass` является производным.  
  
## Примечания  
 Макросы `BEGIN_INTERFACE_MAP` и `END_INTERFACE_MAP` используются в файле реализации для фактического определения схемы интерфейсов.  Для каждого реализованного там интерфейса имеется один или несколько вызовов макросов `INTERFACE_PART`.  Для каждого статистического выражения, используемого классом, имеется один вызов макроса `INTERFACE_AGGREGATE`.  
  
### INTERFACE\_PART — описание макроса  
  
```  
  
              INTERFACE_PART(   
   theClass,  
   iid,   
   localClass   
)  
```  
  
## Примечания  
  
#### Параметры  
 `theClass`  
 Имя класса, содержащего схему интерфейсов.  
  
 `iid`  
 `IID`, который будет сопоставляться с внедренным классом.  
  
 `localClass`  
 Имя локального класса \(без буквы X\).  
  
## Примечания  
 Этот макрос используется между макросом `BEGIN_INTERFACE_MAP` и макросом `END_INTERFACE_MAP` для каждого интерфейса, поддерживаемого объектом.  Он позволяет сопоставить IID с членом класса, обозначенного `theClass` и `localClass`.  К `localClass` будет автоматически добавлено «m\_x».  Обратите внимание, что с одним членом можно сопоставить больше одного `IID`.  Это очень удобно, если вы реализуете только «самый производный» интерфейс и хотите также предоставить все промежуточные интерфейсы.  Хорошим примером этого является интерфейс `IOleInPlaceFrameWindow`.  Иерархия выглядит следующим образом.  
  
```  
IUnknown  
    IOleWindow  
        IOleUIWindow  
            IOleInPlaceFrameWindow  
```  
  
 Если объект реализует `IOleInPlaceFrameWindow`, клиент может выполнить `QueryInterface` для любого из этих интерфейсов: `IOleUIWindow`, `IOleWindow` или [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), кроме «самого производного» интерфейса `IOleInPlaceFrameWindow` \(именно того, который вы реализуете\).  Для обработки в данном случае может потребоваться более одного макроса `INTERFACE_PART`, чтобы сопоставить каждый базовый интерфейс с интерфейсом `IOleInPlaceFrameWindow`:  
  
 В файле определения класса:  
  
```  
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)  
```  
  
 В файле реализации класса:  
  
```  
BEGIN_INTERFACE_MAP(CMyWnd, CFrameWnd)  
    INTERFACE_PART(CMyWnd, IID_IOleWindow, MyFrameWindow)  
    INTERFACE_PART(CMyWnd, IID_IOleUIWindow, MyFrameWindow)  
    INTERFACE_PART(CMyWnd, IID_IOleInPlaceFrameWindow, MyFrameWindow)  
END_INTERFACE_MAP  
```  
  
 Платформа самостоятельно обрабатывает IUnknown, так как он всегда является обязательным.  
  
### INTERFACE\_PART — описание макроса  
  
```  
  
              INTERFACE_AGGREGATE(   
   theClass,  
   theAggr   
)  
```  
  
## Примечания  
  
#### Параметры  
 `theClass`  
 Имя класса, содержащего схему интерфейсов.  
  
 `theAggr`  
 Имя переменной\-члена, подлежащей статистической обработке.  
  
## Примечания  
 Этот макрос применяется, чтобы сообщить платформе о том, что класс использует агрегатный объект.  Его следует разместить между макросами `BEGIN_INTERFACE_PART` и `END_INTERFACE_PART`.  Агрегатный объект представляет собой отдельный объект, производный от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  С помощью статистического выражения и макроса `INTERFACE_AGGREGATE` можно сделать так, чтобы все интерфейсы, которые поддерживает статистическое выражение, выглядели так, как если бы поддерживались непосредственно объектом.  Аргумент `theAggr` — это просто имя переменной — члена класса, который является производным от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) \(напрямую или косвенно\).  При помещении в схему интерфейсов все макросы `INTERFACE_AGGREGATE` должны следовать за макросами `INTERFACE_PART`.  
  
## См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)