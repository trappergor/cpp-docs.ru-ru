---
title: 'TN038: Реализация MFC-OLE IUnknown'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.ole
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
ms.openlocfilehash: 0722ce294e6a088446b8ba681810cf3f7885f122
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571435"
---
# <a name="tn038-mfcole-iunknown-implementation"></a>TN038. Реализация MFC/OLE IUnknown

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

В основе OLE 2 лежит модель COM OLE. Модель COM определяет стандарт взаимодействия совместно действующих объектов. Сюда входят сведения о самом «объекте», включая то, какие методы подготавливаются для отправки в объект. Модель COM также определяет базовый класс, от которого наследуются все COM-совместимые классы. Этот базовый класс является [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown). Несмотря на то что [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) интерфейс называется класса C++, COM не относится к любой один язык, его можно реализовать в C, PASCAL или любом другом языке, может поддерживать двоичное размещение COM-объекта.

OLE относится ко всем классам, производным от [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) называются «интерфейсами». Это важное различие, поскольку «интерфейс» например [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) несет с собой нет реализации. Он просто определяет протокол, по которому взаимодействуют объекты, а не особенности этих реализаций. Это оправдано для системы, которая нацелена на максимальную гибкость. За реализацию поведения по умолчанию для программ MFC/C++ отвечает MFC.

Чтобы понять реализацию MFC [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) необходимо сначала понять, что такое этот интерфейс. Упрощенная версия [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) определен ниже:

```cpp
class IUnknown
{
public:
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;
    virtual ULONG AddRef() = 0;
    virtual ULONG Release() = 0;
};
```

> [!NOTE]
> Некоторые необходимые сведения по соглашениям о вызовах, такие как `__stdcall`, в данной иллюстрации опущены.

[AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) функции-члены управляют памятью объекта. Модель COM использует схему подсчета ссылок для отслеживания объектов. Ссылка на объект никогда не указывается напрямую, как это происходит в C++. Вместо этого ссылка на COM-объекты всегда осуществляется через указатель. Чтобы освободить объект, когда владелец выполняется с помощью его, объект [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) элемент называется (а не оператор delete, как это происходит в обычным объектом C++). Механизм подсчета ссылок позволяет управлять несколькими ссылками на один объект. Реализация [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) поддерживает счетчик ссылок объекта — объект не удаляется, пока число ссылок достигает нуля.

[AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) довольно просты, с точки зрения реализации. Вот пример простой реализации:

```cpp
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

[QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) функция-член является более интересным. Это не очень интересно нет объекта только функции-члены которого являются [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) — было бы желательно заставить объект выполнять больше функций, чем [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) предоставляет. Именно здесь [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) полезно. Он позволяет получать разный «интерфейс» на базе одного и того же объекта. Эти интерфейсы обычно являются производными от [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) и добавить дополнительную функциональность путем добавления новых функций-членов. COM-интерфейсы никогда не имеют объявляемых в интерфейсе переменных-членов, а все функции-члены объявлены как чисто виртуальные. Например, примененная к объекту директива

```cpp
class IPrintInterface : public IUnknown
{
public:
    virtual void PrintObject() = 0;
};
```

Чтобы получить IPrintInterface при наличии только [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown), вызовите [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) с помощью `IID` из `IPrintInterface`. `IID` представляет собой 128-разрядное число, которое однозначно определяет интерфейс. `IID` присутствует для каждого интерфейса, определенного вами или OLE. Если *pUnk* — это указатель на [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) объекта, код для получения IPrintInterface из него могут входить:

```cpp
IPrintInterface* pPrint = NULL;
if (pUnk->QueryInterface(IID_IPrintInterface, (void**)&pPrint) == NOERROR)
{
    pPrint->PrintObject();
    pPrint->Release();
    // release pointer obtained via QueryInterface
}
```

Это кажется довольно простым, но как реализовать объект, поддерживающий как iprintinterface, так и [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) интерфейса в данном случае это просто, поскольку IPrintInterface является производным непосредственно от [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) — путем реализации IPrintInterface, [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) будет поддерживаться автоматически. Пример:

```cpp
class CPrintObj : public CPrintInterface
{
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);
    virtual ULONG AddRef();
    virtual ULONG Release();
    virtual void PrintObject();
};
```

Реализации [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) бы точно так же, как эти реализованных выше. `CPrintObj::QueryInterface` будет выглядеть следующим образом:

```cpp
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

Как видите, если распознается идентификатор интерфейса (IID), в объект возвращается указатель, в противном случае возникает ошибка. Также Обратите внимание, что успешное выполнение [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) дает подразумеваемый [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref). Конечно же, необходимо также реализовать CEditObj::Print. Это простой, поскольку iprintinterface является производным непосредственно от [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) интерфейс. Тем не менее, если требуется поддержка двух различных интерфейсов, производными от [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown), необходимо учитывать следующее:

```cpp
class IEditInterface : public IUnkown
{
public:
    virtual void EditObject() = 0;
};
```

Хотя существует несколько разных способов реализации класса, поддерживающего как IEditInterface, так и IPrintInterface, включая использование множественного наследования C++, эта заметка будет посвящена использованию вложенных классов для реализации данной функциональности.

```cpp
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

```cpp
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

HRESULT CEditPrintObj::CEditObj::QueryInterface(REFIID iid, void** ppvObj)
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

HRESULT CEditPrintObj::CPrintObj::QueryInterface(REFIID iid, void** ppvObj)
{
    return m_pParent->QueryInterface(iid, ppvObj);
}
```

Обратите внимание, что большая часть [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) реализация помещается в класс CEditPrintObj вместо того чтобы дублировать код в CEditPrintObj::CEditObj и CEditPrintObj::CPrintObj. Это уменьшает объем кода и помогает избежать ошибок. Главное здесь то, что от интерфейса IUnknown можно вызвать [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) для получения любого интерфейса который объект должен поддерживать, и из любого из этих интерфейсов можно сделать то же самое. Это означает, что все [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) функции, доступные из каждого интерфейса должны вести себя точно так же. Чтобы эти внедренные объекты вызвали реализацию во «внешнем объекте», используется обратный указатель (m_pParent). Указатель m_pParent инициализируется во время выполнения конструктора CEditPrintObj. Затем следует реализовать CEditPrintObj::CPrintObj::PrintObject, а также CEditPrintObj::CEditObj::EditObject. Потребовалось написать довольно большой объем кода для реализации одной возможности — возможности изменения объекта. К счастью, интерфейсы крайне редко имеют только одну функцию-член (хотя такое и случается), и в этом случае EditObject и PrintObject обычно объединяются в единый интерфейс.

Такой простой сценарий требует слишком долгих пояснений и слишком большого объема кода. Классы MFC/OLE предоставляют более простую альтернативу. Реализация MFC использует методику, аналогичную использованию программы-оболочки для сообщений Windows с помощью схем сообщений. Этот компонент называется *схемы интерфейсов* и рассматривается в следующем разделе.

## <a name="mfc-interface-maps"></a>Схемы интерфейсов MFC

MFC/OLE включает в себя реализацию «Схемы интерфейсов», аналогичную компонентам «Схемы сообщений» и «Схемы подготовки к отправке» MFC в рамках концепции и выполнения. Схемы интерфейсов MFC имеют следующие основные возможности.

- Стандартная реализация [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown), встроенная в `CCmdTarget` класса.

- Обслуживание счетчика ссылок, изменяемом [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)

- Данными реализация [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))

Кроме того, схемы интерфейсов поддерживают следующие дополнительные возможности.

- Поддержка создания COM-объектов, допускающих статистическую обработку

- Поддержка использования агрегатных объектов в реализации COM-объекта

- Реализация является обрабатываемой и расширяемой

Дополнительные сведения об агрегировании см. в разделе [статистической обработки](/windows/desktop/com/aggregation) раздела.

Поддержка схем интерфейсов MFC заключена в класс `CCmdTarget`. `CCmdTarget` "*имеет*" ссылаются на число, а также все функции-члены, связанные с [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) реализации (число ссылок, например находится в `CCmdTarget`). Чтобы создать класс, поддерживающий модель COM OLE, создайте класс, производный от `CCmdTarget`, и используйте различные макросы и функции-члены `CCmdTarget` для реализации требуемых интерфейсов. Реализация MFC использует вложенные классы для определения каждой реализации интерфейса, что во многом похоже на приведенный выше пример. Эта задача упрощается благодаря стандартной реализации IUnknown, а также набору макросов, позволяющих исключить некоторые из повторяющихся частей кода.

## <a name="interface-map-basics"></a>Основы использования схем интерфейсов

### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>Реализация класса с помощью схем интерфейсов MFC

1. Создайте класс, который явно или косвенно является от `CCmdTarget`.

2. Используйте функцию `DECLARE_INTERFACE_MAP` в определении производного класса.

3. Для каждого интерфейса, которая должна поддерживаться используйте макрос BEGIN_INTERFACE_PART и END_INTERFACE_PART в определении класса.

4. В файле реализации используйте макрос BEGIN_INTERFACE_MAP и END_INTERFACE_MAP для определения схемы интерфейсов класса.

5. Для каждого поддерживаемого идентификатора интерфейса используйте макрос INTERFACE_PART между макросами BEGIN_INTERFACE_MAP и END_INTERFACE_MAP, чтобы сопоставить IID с конкретной «часть» вашего класса.

6. Реализуйте каждый из вложенных классов, представляющих интерфейсы, которые вы поддерживаете.

7. Использовать method_prologue-макрос для доступа к родительскому элементу, `CCmdTarget`-объект, производный от.

8. [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), и [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) можно делегировать `CCmdTarget` реализации этих функций (`ExternalAddRef`, `ExternalRelease`, и `ExternalQueryInterface`).

Приведенный выше пример CPrintEditObj можно реализовать следующим образом:

```cpp
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

Указанное выше объявление создает класс, производный от `CCmdTarget`. Declare_interface_map-макрос указывает платформе, что этот класс будет иметь настраиваемую схему интерфейсов. Кроме того макросы BEGIN_INTERFACE_PART и END_INTERFACE_PART в данном случае определяют вложенные классы, имена CEditObj и CPrintObj (X используется только для отличия вложенных классов от глобальных классов, в которых начинаются с «C» и классы, которые начинается с «I»). Создаются два вложенных элемента этих классов — m_CEditObj и m_CPrintObj соответственно. Макросы автоматически объявляют [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), и [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) функции; таким образом можно объявить только функции, характерные для этого интерфейса: EditObject и PrintObject (OLE-макрос STDMETHOD используется, чтобы **_stdcall** и ключевых слов virtual предоставляются в соответствии с целевой платформы).

Чтобы реализовать схему интерфейсов для этого класса, используйте следующий код:

```cpp
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)
END_INTERFACE_MAP()
```

Он соединяет IID_IPrintInterface IID с m_CPrintObj, а IID_IEditInterface — с m_CEditObj. `CCmdTarget` Реализация [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) (`CCmdTarget::ExternalQueryInterface`) использует эту схему, чтобы возвратить указатели m_CPrintObj и m_CEditObj при запросе. Включать запись для `IID_IUnknown` не нужно, при запросе `IID_IUnknown` платформа будет использовать первый интерфейс в схеме (в данном случае это m_CPrintObj).

Несмотря на то, что автоматически объявляются в begin_interface_part-макрос [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) и [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) функции для вас по-прежнему необходимо реализовать их:

```cpp
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
    REFIID iid,
    void FAR* FAR* ppvObj)
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

Реализация CEditPrintObj::CPrintObj будет похожа на приведенные выше определения CEditPrintObj::CEditObj. Несмотря на то что возможно создать макрос, который может использоваться для автоматического создания таких функций (а так было ранее при разработке MFC/OLE), становится трудно задавать точки останова, когда макрос создает более одной строки кода. По этой причине этот код будет расширен вручную.

При использовании реализации платформы для схем сообщений существует несколько вещей, которые не нужно было выполнять.

- Реализация QueryInterface

- Реализация AddRef и Release

- Объявление любого из этих встроенных методов для обоих интерфейсов

Кроме того, платформа использует схемы сообщений для внутренних целей. Это позволяет создавать производные объекты от класса платформы, например `COleServerDoc`, который уже поддерживает определенные интерфейсы и предоставляет замены или дополнения для интерфейсов, предоставляемых платформой. Это можно сделать, так как платформа полностью поддерживает наследование схемы интерфейсов от базового класса. Это причина, почему BEGIN_INTERFACE_MAP принимает в качестве второго параметра имя базового класса.

> [!NOTE]
> В общем случае нельзя повторно использовать реализацию встроенных реализаций интерфейсов OLE MFC путем простого наследования внедренных специализаций этого интерфейса от версии MFC. Это невозможно из-за применения method_prologue-макрос для получения доступа к содержащему `CCmdTarget`-подразумевает производного объекта *фиксированном смещении* внедренного объекта из `CCmdTarget`-объект, производный от. Это означает, например, что нельзя наследовать внедренный XMyAdviseSink от реализации MFC в `COleClientItem::XAdviseSink`, так как XAdviseSink ожидает наличия определенного смещения относительно верхнего края объект `COleClientItem`.

> [!NOTE]
> Однако можно делегировать реализацию MFC для всех функций, для которых требуется поведение по умолчанию MFC. Это делается в реализации MFC `IOleInPlaceFrame` (XOleInPlaceFrame) в классе `COleFrameHook` (он делегирует в m_xOleInPlaceUIWindow для многих функций). Такой подход был выбран для уменьшения размера среды выполнения объектов, реализующих несколько интерфейсов. Он устраняет необходимость в обратном указателе (например, в m_pParent из примера в предыдущем разделе).

### <a name="aggregation-and-interface-maps"></a>Статистическая обработка и схемы интерфейсов

В дополнение к поддержке изолированных COM-объектов MFC также поддерживает статистическую обработку. Агрегирование само по себе является слишком сложной темой, чтобы рассматривать ее здесь; ссылаться на [статистической обработки](/windows/desktop/com/aggregation) Дополнительные сведения об агрегировании. Эта заметка просто описывает поддержку статистической обработки, встроенную в платформу и схемы интерфейсов.

Существует два способа использования статистической обработки: (1) использование COM-объекта, поддерживающего статистическую обработку, и (2) реализация объекта, который может быть статистически вычислен другим объектом. Эти возможности можно называть «использование агрегатного объекта» и «превращение объекта в допускающий статистическую обработку». MFC поддерживает оба этих варианта.

### <a name="using-an-aggregate-object"></a>Использование агрегатного объекта

Для использования агрегатного объекта требуется какой-либо способ связать статистическое выражение с механизмом QueryInterface. Другими словами, агрегатный объект должен работать так, как будто это собственная часть объекта. Так как этот объект привязан в механизм схем интерфейсов MFC в дополнение к interface_part-макрос, где вложенный объект сопоставляется с IID, можно также объявить Агрегатный объект как часть вашего `CCmdTarget` производного класса. Для этого используется макроса INTERFACE_AGGREGATE. Это позволяет указать переменную-член (который должен быть указателем на [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) или производного класса), это был интегрирован в механизм схем интерфейсов. Если указатель не равен NULL при `CCmdTarget::ExternalQueryInterface` является именем, платформа автоматически вызывает агрегатного объекта [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) функция-член, если `IID` запроса не является одним из собственных `IID`s поддерживаемые `CCmdTarget` сам объект.

#### <a name="to-use-the-interfaceaggregate-macro"></a>Использование макроса INTERFACE_AGGREGATE

1. Объявите переменную-член (`IUnknown*`) которая будет содержать указатель на агрегатный объект.

2. Включите макроса INTERFACE_AGGREGATE в схему интерфейсов, который ссылается на переменную-член по имени.

3. В определенный момент (обычно во время `CCmdTarget::OnCreateAggregates`) инициализируйте переменную-член со значением, отличным от NULL.

Пример:

```cpp
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

Переменная m_lpAggrInner инициализируется в конструкторе со значением NULL. Платформа игнорирует переменную-член NULL в реализации по умолчанию [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)). `OnCreateAggregates` удобно использовать для создания агрегатных объектов. Его потребуется вызвать явным образом при создании объекта за пределами реализации `COleObjectFactory` MFC. Причина создания статистических выражений в `CCmdTarget::OnCreateAggregates` и использование `CCmdTarget::GetControllingUnknown` станут очевидными при рассмотрении создания агрегатных объектов.

Эта методика дает объекту все интерфейсы, поддерживаемые агрегатным объектом, а также все его собственные интерфейсы. Если требуется только подмножество интерфейсов, поддерживаемых статистическим выражением, можно переопределить `CCmdTarget::GetInterfaceHook`. Это позволяет очень низкого уровня по аналогии с [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)). В общем случае требуются все интерфейсы, которые поддерживает статистическое выражение.

### <a name="making-an-object-implementation-aggregatable"></a>Превращение реализации объекта в допускающую статистическую обработку

Объект допускающим статистическую обработку, реализация [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), и [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) должны делегировать «управляющему unknown». Другими словами, он был частью объекта, она должна делегировать [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), и [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) другому объекту, также является производным от [ IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown). Этот «управляющий unknown» предоставляется для объекта при его создании, то есть предоставляется реализации `COleObjectFactory`. Такая реализация имеет небольшое количество издержек и в некоторых случаях является нежелательной, поэтому MFC делает ее необязательной. Чтобы сделать объект допускающим статистическую обработку, вызовите `CCmdTarget::EnableAggregation` из конструктора объекта.

Если этот объект также использует статистические выражения, необходимо обязательно передать в агрегатные объекты правильный «управляющий unknown». Обычно это [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) передается указатель на объект при создании статистического выражения. Например, параметр pUnkOuter является «управляющим unknown» для объектов, созданных с использованием `CoCreateInstance`. Можно получить правильный указатель «управляющий unknown» путем вызова `CCmdTarget::GetControllingUnknown`. Однако значение, возвращаемое из этой функции, является недопустимым во время конструктора. Поэтому рекомендуется создавать ваши статистические выражения только в переопределении `CCmdTarget::OnCreateAggregates`, где возвращаемое значение из `GetControllingUnknown` является надежным, даже если оно создано на базе реализации `COleObjectFactory`.

Не менее важно, чтобы объект изменял правильный счетчик ссылок во время добавления или освобождения искусственных счетчиков ссылок. Чтобы обеспечить это, следует всегда вызывать `ExternalAddRef` и `ExternalRelease` вместо `InternalRelease` и `InternalAddRef`. `InternalRelease` или `InternalAddRef` редко вызываются для класса, поддерживающего статистическую обработку.

## <a name="reference-material"></a>Справочные материалы

Расширенное использование OLE, например при определении собственных интерфейсов или переопределении реализации интерфейсов OLE платформы, требует использования базового механизма схем интерфейсов.

В этом разделе рассматриваются все макросы и интерфейсы API, которые используются для реализации этих дополнительных функций.

### <a name="ccmdtargetenableaggregation--function-description"></a>CCmdTarget::EnableAggregation — описание функции

```cpp
void EnableAggregation();
```

#### <a name="remarks"></a>Примечания

Вызовите эту функцию в конструкторе производного класса, если хотите обеспечить поддержку статистической обработки OLE для объектов этого типа. При этом подготавливается специальная реализация IUnknown, которая необходима для агрегатных объектов.

### <a name="ccmdtargetexternalqueryinterface--function-description"></a>CCmdTarget::ExternalQueryInterface — описание функции

```cpp
DWORD ExternalQueryInterface(
    const void FAR* lpIID,
    LPVOIDFAR* ppvObj
);
```

#### <a name="parameters"></a>Параметры

*lpIID*<br/>
Дальний указатель на IID (первый аргумент QueryInterface)

*ppvObj*<br/>
Указатель на IUnknown * (второй аргумент QueryInterface)

#### <a name="remarks"></a>Примечания

Вызовите эту функцию в реализации IUnknown для каждого интерфейса, который реализуется вашим классом. Эта функция предоставляет стандартную управляемую данными реализацию QueryInterface, основанную на схеме интерфейсов объекта. Это необходимо, чтобы привести возвращаемое значение к HRESULT. Если объект является статистическим выражением, вместо использования локальной схемы интерфейсов эта функция вызывает «управляющий IUnknown».

### <a name="ccmdtargetexternaladdref--function-description"></a>CCmdTarget::ExternalAddRef — описание функции

```cpp
DWORD ExternalAddRef();
```

#### <a name="remarks"></a>Примечания

Вызовите эту функцию в реализации IUnknown::AddRef для каждого интерфейса, который реализуется вашим классом. Возвращаемое значение является новым счетчиком ссылок для объекта CCmdTarget. Если объект является статистическим выражением, вместо изменения локального счетчика ссылок эта функция вызывает «управляющий IUnknown».

### <a name="ccmdtargetexternalrelease--function-description"></a>CCmdTarget::ExternalRelease — описание функции

```cpp
DWORD ExternalRelease();
```

#### <a name="remarks"></a>Примечания

Вызовите эту функцию в реализации IUnknown::Release для каждого интерфейса, который реализуется вашим классом. Возвращаемое значение указывает новый счетчик для объекта. Если объект является статистическим выражением, вместо изменения локального счетчика ссылок эта функция вызывает «управляющий IUnknown».

### <a name="declareinterfacemap--macro-description"></a>DECLARE_INTERFACE_MAP — описание макроса

```cpp
DECLARE_INTERFACE_MAP
```

#### <a name="remarks"></a>Примечания

Используйте этот макрос в любом классе, производном от `CCmdTarget`, который будет иметь схему интерфейсов. Используется во многом так же, как DECLARE_MESSAGE_MAP. Вызов этого макроса следует поместить в определение класса, обычно для этого используется файл заголовка (. (H). Класс с DECLARE_INTERFACE_MAP необходимо определить схему интерфейсов в файле реализации (. CPP) с макросами BEGIN_INTERFACE_MAP и END_INTERFACE_MAP.

### <a name="begininterfacepart-and-endinterfacepart--macro-descriptions"></a>BEGIN_INTERFACE_PART и END_INTERFACE_PART — описания макросов

```cpp
BEGIN_INTERFACE_PART(localClass, iface);
END_INTERFACE_PART(localClass)
```

#### <a name="parameters"></a>Параметры

*localClass*<br/>
Имя класса, реализующего интерфейс.

*iface*<br/>
Имя интерфейса, реализуемого с помощью данного класса.

#### <a name="remarks"></a>Примечания

Для каждого интерфейса, реализуемого вашим классом необходимо иметь пару BEGIN_INTERFACE_PART и END_INTERFACE_PART. Эти макросы определяют локальный класс, производный от определенного вами интерфейса OLE, а также внедренную переменную-член этого класса. [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), и [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) элементы объявлены автоматически. Необходимо включить объявления для других функций-членов, которые являются частью реализуемого интерфейса (эти объявления размещаются между макросами BEGIN_INTERFACE_PART и END_INTERFACE_PART).

*Iface* аргумент является интерфейсом OLE, который вы хотите реализовать, например `IAdviseSink`, или `IPersistStorage` (или собственный пользовательский интерфейс).

*LocalClass* аргумента — имя локального класса, который будет определен. К имени будет автоматически добавляться буква X. Это соглашение об именовании используется для предотвращения конфликтов с глобальными классами, имеющими такое же имя. Кроме того, имя внедренного члена совпадает *localClass* имя, за исключением того, оно будет начинаться префикса «m_x».

Пример:

```cpp
BEGIN_INTERFACE_PART(MyAdviseSink, IAdviseSink)
    STDMETHOD_(void, OnDataChange)(LPFORMATETC, LPSTGMEDIUM);
    STDMETHOD_(void, OnViewChange)(DWORD, LONG);
    STDMETHOD_(void, OnRename)(LPMONIKER);
    STDMETHOD_(void, OnSave)();
    STDMETHOD_(void, OnClose)();
END_INTERFACE_PART(MyAdviseSink)
```

Этот код определяет локальный класс с именем XMyAdviseSink, являющийся производным от IAdviseSink, и член класса, в котором он определен, с именем m_xMyAdviseSink.Note:

> [!NOTE]
> Строки, начинающиеся с `STDMETHOD`_ фактически копируются из OLE2. H и слегка изменена. Их копирование из OLE2.H позволяет уменьшить число трудноразрешимых ошибок.

### <a name="begininterfacemap-and-endinterfacemap--macro-descriptions"></a>BEGIN_INTERFACE_MAP и END_INTERFACE_MAP — описания макросов

```cpp
BEGIN_INTERFACE_MAP(theClass, baseClass)
END_INTERFACE_MAP
```

#### <a name="parameters"></a>Параметры

*theClass*<br/>
Класс, в котором определяется схема интерфейсов.

*baseClass*<br/>
Класс, от которого *theClass* является производным от.

#### <a name="remarks"></a>Примечания

BEGIN_INTERFACE_MAP и END_INTERFACE_MAP макросы используются в файле реализации для фактического определения схемы интерфейсов. Для каждого интерфейса, реализуемого имеется один или несколько вызовов макросов INTERFACE_PART. Для каждого агрегата, используемого классом имеется один вызов макроса INTERFACE_AGGREGATE.

### <a name="interfacepart--macro-description"></a>INTERFACE_PART — описание макроса

```cpp
INTERFACE_PART(theClass, iid, localClass)
```

#### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса, содержащего схему интерфейсов.

*IID*<br/>
`IID`, который будет сопоставляться с внедренным классом.

*localClass*<br/>
Имя локального класса (без буквы X).

#### <a name="remarks"></a>Примечания

Этот макрос используется между макрос BEGIN_INTERFACE_MAP и end_interface_map-макрос для каждого интерфейса, который будет поддерживать этот объект. Он позволяет сопоставить IID с членом класса, обозначенного *theClass* и *localClass*. «m_x» будут добавлены к *localClass* автоматически. Обратите внимание, что с одним членом можно сопоставить больше одного `IID`. Это очень удобно, если вы реализуете только «самый производный» интерфейс и хотите также предоставить все промежуточные интерфейсы. Хорошим примером этого является интерфейс `IOleInPlaceFrameWindow`. Иерархия выглядит следующим образом.

```Hierarchy
IUnknown
    IOleWindow
        IOleUIWindow
            IOleInPlaceFrameWindow
```

Если объект реализует интерфейс `IOleInPlaceFrameWindow`, клиент может `QueryInterface` на любой из этих интерфейсов: `IOleUIWindow`, `IOleWindow`, или [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown), кроме «самого производного» интерфейса `IOleInPlaceFrameWindow` (тот, фактически являются реализации). Для обработки этого можно использовать более одного interface_part-макрос для сопоставления каждый базовый интерфейс для `IOleInPlaceFrameWindow` интерфейса:

В файле определения класса:

```cpp
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)
```

В файле реализации класса:

```cpp
BEGIN_INTERFACE_MAP(CMyWnd, CFrameWnd)
    INTERFACE_PART(CMyWnd, IID_IOleWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleUIWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleInPlaceFrameWindow, MyFrameWindow)
END_INTERFACE_MAP
```

Платформа самостоятельно обрабатывает IUnknown, так как он всегда является обязательным.

### <a name="interfacepart--macro-description"></a>INTERFACE_PART — описание макроса

```cpp
INTERFACE_AGGREGATE(theClass, theAggr)
```

#### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса, содержащего схему интерфейсов.

*theAggr*<br/>
Имя переменной-члена, подлежащей статистической обработке.

#### <a name="remarks"></a>Примечания

Этот макрос применяется, чтобы сообщить платформе о том, что класс использует агрегатный объект. Его следует разместить между макросами BEGIN_INTERFACE_PART и END_INTERFACE_PART. Агрегатный объект представляет собой отдельный объект, производный от [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown). С помощью статистического выражения и макроса INTERFACE_AGGREGATE, можно сделать все интерфейсы, которые поддерживает статистическое выражение, по-видимому, бы поддерживались непосредственно объектом. *TheAggr* аргумент — это просто имя переменной-члена класса, который является производным от [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) (прямо или косвенно). Все макросы INTERFACE_AGGREGATE важно следовать макросы INTERFACE_PART при помещении в схему интерфейсов.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
