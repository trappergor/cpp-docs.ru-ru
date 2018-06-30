---
title: 'TN065: Поддержка сдвоенных интерфейсов для серверов автоматизации OLE | Документы Microsoft'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.ole
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e30be46aeab92f63f1b4cba593cda52bf9aeef9a
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122187"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065. Поддержка сдвоенных интерфейсов для серверов автоматизации OLE

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

Эта заметка рассматриваются как добавить поддержку сдвоенных интерфейсов для приложения сервера на базе MFC OLE-автоматизации. [ACDUAL](../visual-cpp-samples.md) примере описывается поддержка сдвоенных интерфейсов и пример кода в этой заметке берется из ACDUAL. Макросы, описанная в этой заметке, например DECLARE_DUAL_ERRORINFO, DUAL_ERRORINFO_PART и IMPLEMENT_DUAL_ERRORINFO, входят в образце ACDUAL и можно найти в MFCDUAL. З.

## <a name="dual-interfaces"></a>Сдвоенные интерфейсы

Несмотря на то, что OLE-автоматизации позволяет реализовать `IDispatch` интерфейс, интерфейс VTBL или сдвоенный интерфейс (который включает оба), корпорация Майкрософт настоятельно рекомендует реализовать сдвоенные интерфейсы для всех предоставленные объекты OLE-автоматизации. Сдвоенные интерфейсы имеют значительные преимущества над `IDispatch`-только или только для VTBL интерфейсов:

- Привязка может происходить во время компиляции через интерфейс VTBL или во время выполнения с помощью `IDispatch`.

- Контроллеры OLE-автоматизации, которые могут использовать интерфейс VTBL может дать преимущества повышения производительности.

- Существующие контроллеры OLE-автоматизации, использующих `IDispatch` интерфейс будет продолжать работать.

- Интерфейс VTBL проще вызвать из C++.

- Сдвоенные интерфейсы являются обязательными для совместимости с Visual Basic функции поддержки объекта.

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>Добавление поддержки сдвоенных интерфейсов для классов на основе CCmdTarget

Сдвоенный интерфейс-это просто это пользовательский интерфейс, производный от `IDispatch`. Самый простой способ реализации поддержка сдвоенных интерфейсов в `CCmdTarget`-на основе класса — для первой реализации диспетчеризации обычный интерфейс в классе с помощью MFC и ClassWizard, а затем добавьте пользовательский интерфейс более поздней версии. В большинстве случаев реализации пользовательского интерфейса просто передать обратно в MFC `IDispatch` реализации.

Во-первых измените ODL-файла для определения сдвоенных интерфейсов для объектов сервера. Чтобы определить сдвоенный интерфейс, необходимо использовать оператор interface вместо `DISPINTERFACE` инструкции, Создание мастеров Visual C++. Вместо удаления существующего `DISPINTERFACE` инструкции, добавить новый оператор interface. При этом `DISPINTERFACE` формы, можно продолжать использовать ClassWizard для добавления свойств и методов к объекту, но эквивалентные свойства и методы, необходимо добавить в инструкцию интерфейса.

Оператор interface для сдвоенный интерфейс должен иметь *OLEAUTOMATION* и *ДВОЙНОГО* атрибуты и интерфейс должен быть производным от `IDispatch`. Можно использовать [GUIDGEN](../visual-cpp-samples.md) образец для создания **IID** для сдвоенный интерфейс:

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

После оператора interface на месте, приступите к добавлению записи для методов и свойств. Сдвоенные интерфейсы, необходимо изменить списки параметров таким образом, методы и функции метода доступа свойства в сдвоенный интерфейс возвращал **HRESULT** и передавать их возвращаемые значения в качестве параметров с атрибутами `[retval,out]`. Помните, что для свойств, будет необходимо добавить оба read (`propget`) и записи (`propput`) получить доступ к функции с тем же идентификатором. Пример:

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

После определения методов и свойств, необходимо добавить ссылку на интерфейс инструкции в инструкции компонентного класса. Пример:

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

После обновления ODL-файла используйте механизма схем интерфейсов MFC для определения класс реализации для сдвоенный интерфейс класса объекта и внести соответствующие записи в MFC `QueryInterface` механизм. Необходимо, чтобы с одной записью `INTERFACE_PART` блок для каждой записи в операторе интерфейс ODL, а также записи для интерфейса диспетчеризации. Каждый элемент ODL с *propput* атрибут имел функция с именем `put_propertyname`. Каждый элемент с *propget* атрибут имел функция с именем `get_propertyname`.

Чтобы определить класс реализации для вашего сдвоенный интерфейс, добавьте `DUAL_INTERFACE_PART` блок в определении класса объекта. Пример:

```cpp
BEGIN_DUAL_INTERFACE_PART(DualAClick, IDualAClick)
    STDMETHOD(put_text)(THIS_ BSTR newText);
    STDMETHOD(get_text)(THIS_ BSTR FAR* retval);
    STDMETHOD(put_x)(THIS_ short newX);
    STDMETHOD(get_x)(THIS_ short FAR* retval);
    STDMETHOD(put_y)(THIS_ short newY);
    STDMETHOD(get_y)(THIS_ short FAR* retval);
    STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);
    STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);
    STDMETHOD(RefreshWindow)(THIS);
    STDMETHOD(SetAllProps)(THIS_ short x, short y, BSTR text);
    STDMETHOD(ShowWindow)(THIS);
END_DUAL_INTERFACE_PART(DualAClick)
```

Для подключения к MFC сдвоенный интерфейс [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) механизм, добавить `INTERFACE_PART` запись схему интерфейсов:

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

Далее необходимо заполнить реализацию интерфейса. В большинстве случаев можно делегировать с существующие MFC `IDispatch` реализации. Пример:

```cpp
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalAddRef();
}

STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalRelease();
}

STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalQueryInterface(&iid, ppvObj);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(
    UINT FAR* pctinfo)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);
    return lpDispatch->GetTypeInfoCount(pctinfo);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(
    UINT itinfo,
    LCID lcid,
    ITypeInfo FAR* FAR* pptinfo)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfo(itinfo, lcid, pptinfo);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(
    REFIID riid,
    OLECHAR FAR* FAR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID FAR* rgdispid)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetIDsOfNames(riid, rgszNames, cNames, lcid, rgdispid);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::Invoke(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS FAR* pdispparams,
    VARIANT FAR* pvarResult,
    EXCEPINFO FAR* pexcepinfo,
    UINT FAR* puArgErr)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->Invoke(dispidMember, riid, lcid,
        wFlags, pdispparams, pvarResult, pexcepinfo, puArgErr);
}
```

Методы и функции метода доступа свойства объекта необходимо заполнить реализации. Метод и свойство функций обычно можно делегировать обратно в методы, созданные с помощью классов. Если настройка свойств напрямую обращаться к переменным, необходимо написать код для get и put значение в переменную. Пример:

```cpp
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    // MFC automatically converts from Unicode BSTR to
    // Ansi CString, if necessary...
    pThis->m_str = newText;
    return NOERROR;
}

STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    // MFC automatically converts from Ansi CString to
    // Unicode BSTR, if necessary...
    pThis->m_str.SetSysString(retval);
    return NOERROR;
}
```

## <a name="passing-dual-interface-pointers"></a>Передача указателей на сдвоенные интерфейсы

Передача указатель сдвоенных интерфейсов не является простым, особенно в том случае, если необходимо вызвать `CCmdTarget::FromIDispatch`. `FromIDispatch` работает только с MFC `IDispatch` указатели. Является одним из способов обхода этого запроса для исходного `IDispatch` набор указатель вверх по MFC и передать данный указатель функции, которым она необходима. Пример:

```
STDMETHODIMP CAutoClickDoc::XDualAClick::put_Position(
    IDualAutoClickPoint FAR* newPosition)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDisp = NULL;
    newPosition->QueryInterface(IID_IDispatch, (LPVOID*)&lpDisp);
    pThis->SetPosition(lpDisp);
    lpDisp->Release();
    return NOERROR;
}
```

Перед передачей указатель обратно через метод сдвоенных интерфейсов, может потребоваться преобразовать его из MFC `IDispatch` указатель на указатель сдвоенных интерфейсов. Пример:

```
STDMETHODIMP CAutoClickDoc::XDualAClick::get_Position(
    IDualAutoClickPoint FAR* FAR* retval)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDisp;
    lpDisp = pThis->GetPosition();
    lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);
    return NOERROR;
}
```

## <a name="registering-the-applications-type-library"></a>Регистрация приложения библиотеки типов

Мастер приложений не создает код, чтобы зарегистрировать библиотеку типов для приложения сервера OLE-автоматизации в системе. Хотя есть и другие способы регистрации библиотеки типов, удобно приложением зарегистрировать библиотеку типов, при обновлении сведения об этом типе OLE, то есть, при каждом запуске изолированного приложения.

Для регистрации библиотеки типов приложения при каждом запуске приложения независимо от них:

- Включить AFXCTL. H в вашей стандартной включает файл заголовка, STDAFX. H, чтобы получить доступ к определению `AfxOleRegisterTypeLib` функции.

- В вашем приложении `InitInstance` функцию, найдите вызов `COleObjectFactory::UpdateRegistryAll`. После этого вызова, добавьте вызов `AfxOleRegisterTypeLib`, указав **LIBID** соответствующий свою библиотеку типов, вместе с именем библиотеки типов:

    ```cpp
    // When a server application is launched stand-alone, it is a good idea
    // to update the system registry in case it has been damaged.
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);

    COleObjectFactory::UpdateRegistryAll();

    // DUAL_SUPPORT_START
        // Make sure the type library is registered or dual interface won't work.
        AfxOleRegisterTypeLib(AfxGetInstanceHandle(),
            LIBID_ACDual,
            _T("AutoClik.TLB"));
    // DUAL_SUPPORT_END
    ```

## <a name="modifying-project-build-settings-to-accommodate-type-library-changes"></a>Изменение параметров построения проекта в соответствии с изменениями библиотеки типов

Чтобы изменить параметры сборки проекта, чтобы заголовок файла, содержащего **UUID** определения формируется MkTypLib всякий раз, когда перестраивается библиотеки типов:

1. На **построения** меню, нажмите кнопку **параметры**, а затем выберите ODL-файла из списка файлов для каждой конфигурации.

2. Нажмите кнопку **OLE типы** вкладку и укажите имя файла в **выходные данные заголовка** поле имя файла. Используйте имя файла, который уже не используется в проекте, поскольку MkTypLib приведет к перезаписи существующего файла. Нажмите кнопку **ОК** закрыть **параметры построения** диалоговое окно.

Чтобы добавить **UUID** определений из создаваемого MkTypLib заголовка файла в проект:

1. Включить MkTypLib созданный файл заголовка в вашей стандартной включает файл заголовка, STDAFX. З.

2. Создайте новый файл INITIIDS. CPP и добавить его в проект. В этом файле включают созданные MkTypLib заголовка файла после включения OLE2. H и INITGUID. H:

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. На **построения** меню, нажмите кнопку **параметры**, а затем выберите INITIIDS. CPP из списка файлов для каждой конфигурации.

4. Нажмите кнопку **C++** щелкните категорию **предварительно скомпилированные заголовки**и выберите **не использовать предварительно скомпилированные заголовки** переключатель. Нажмите кнопку ОК, чтобы закрыть **параметры построения** диалоговое окно.

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>Указание правильного имени класса объекта в библиотеке типов

Мастеры, неправильно, поставляемых с Visual C++ позволяет указать компонентный класс в файле ODL сервера для классов, создаваемыми OLE имя класса реализации. Хотя это будет работать нормально, имя класса реализации не, возможно, имя класса, который требуется пользователям для использования объекта. Чтобы указать правильное имя, откройте ODL-файла, найдите каждой инструкции компонентного класса и замените имя класса реализации внешнего правильное имя.

Обратите внимание, что при изменении инструкции компонентного класса, имена переменных из **CLSID**s в файле заголовка, созданный MkTypLib изменится соответствующим образом. Будет необходимо обновить код для использования новых имен переменной.

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>Обработка исключений и интерфейсах ошибок автоматизации

Методы и функции метода доступа свойства объект автоматизации могут вызывать исключения. Если таким образом, следует их обработки в реализации сдвоенных интерфейсов и передать сведения об исключении контроллера через интерфейс OLE-автоматизации обработки ошибок, `IErrorInfo`. Этот интерфейс предоставляет подробные, контекстные сведения об ошибке через `IDispatch` и интерфейсы VTBL. Чтобы указать, что обработчик ошибок доступен, необходимо реализовать `ISupportErrorInfo` интерфейса.

Чтобы продемонстрировать механизма обработки ошибок, предположим, созданных классов функции, используемые для реализации поддержки стандартной диспетчеризации исключений. Реализация MFC `IDispatch::Invoke` обычно перехватывает эти исключения и преобразует их в структуру EXCEPTINFO, возвращается через `Invoke` вызова. Тем не менее если используется интерфейс VTBL, вы несете ответственность для перехвата исключения самостоятельно. В качестве примера защиты методов сдвоенных интерфейсов:

```cpp
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    TRY_DUAL(IID_IDualAClick)
    {
        // MFC automatically converts from Unicode BSTR to
        // Ansi CString, if necessary...
        pThis->m_str = newText;
        return NOERROR;
    }
    CATCH_ALL_DUAL
}
```

`CATCH_ALL_DUAL` отвечает за возвращение правильный код ошибки при возникновении исключения. `CATCH_ALL_DUAL` Преобразует исключения MFC в сведения о обработка ошибок OLE-автоматизации с помощью `ICreateErrorInfo` интерфейса. (Пример `CATCH_ALL_DUAL` макрос находится в файле MFCDUAL. H в [ACDUAL](../visual-cpp-samples.md) образца. Функция вызывается для обработки исключений, `DualHandleException`, находится в файле MFCDUAL. CPP). `CATCH_ALL_DUAL` определяет код ошибки для возврата в зависимости от типа возникшего исключения:

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) — в этом случае `HRESULT` создается с помощью следующий код:

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

     При этом создается `HRESULT` для интерфейса, вызвавшего исключение. Код ошибки смещением 0x200 во избежание конфликтов с системные `HRESULT`s для стандартных интерфейсов OLE.

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) — в этом случае `E_OUTOFMEMORY` возвращается.

- Любые другие исключения - в этом случае `E_UNEXPECTED` возвращается.

Чтобы указать, что используется обработчик ошибок OLE-автоматизации, также требуется реализовать `ISupportErrorInfo` интерфейса.

Во-первых, добавьте код в определении класса автоматизации, чтобы показать его поддерживает `ISupportErrorInfo`.

Во-вторых, добавьте код в схему интерфейсов класса автоматизации связываемый `ISupportErrorInfo` реализацию класса MFC `QueryInterface` механизм. `INTERFACE_PART` Инструкции соответствующий класс, определенный для `ISupportErrorInfo`.

Наконец, реализовать класс, определенный для поддержки `ISupportErrorInfo`.

( [ACDUAL](../visual-cpp-samples.md) пример содержит три макросы, чтобы помочь сделать эти три шага `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, и `IMPLEMENT_DUAL_ERRORINFO`, все содержащиеся в MFCDUAL. З.)

В следующем примере реализуется класс, определенный для поддержки `ISupportErrorInfo`. `CAutoClickDoc` Имя класса автоматизации и `IID_IDualAClick` — **IID** для интерфейса, который является источником ошибок, через объект OLE-автоматизации ошибка:

```cpp
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::AddRef()
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalAddRef();
}

STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::Release()
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalRelease();
}

STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalQueryInterface(&iid, ppvObj);
}

STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo(
    REFIID iid)
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return (iid == IID_IDualAClick) S_OK : S_FALSE;
}
```

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)  
[Технические примечания по категории](../mfc/technical-notes-by-category.md)  
