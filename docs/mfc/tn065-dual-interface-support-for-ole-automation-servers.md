---
title: TN065. Поддержка сдвоенных интерфейсов для серверов автоматизации OLE
ms.date: 06/28/2018
f1_keywords:
- vc.ole
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
ms.openlocfilehash: 5a04c2712182fe9c9ed3fd9e5fe4548404f96a5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575218"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065. Поддержка сдвоенных интерфейсов для серверов автоматизации OLE

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

Эта заметка описывает добавление поддержки сдвоенных интерфейсов в приложение сервера на базе MFC OLE-автоматизации. [ACDUAL](../visual-cpp-samples.md) примере описывается поддержка сдвоенных интерфейсов и пример кода в этой заметке берется из ACDUAL. Макросы, описанные в этой заметке, например DECLARE_DUAL_ERRORINFO, DUAL_ERRORINFO_PART и IMPLEMENT_DUAL_ERRORINFO, которые входят в образце ACDUAL и можно найти в MFCDUAL. З.

## <a name="dual-interfaces"></a>Сдвоенные интерфейсы

Несмотря на то, что OLE-автоматизации позволяет реализовать `IDispatch` интерфейс, интерфейс VTBL или сдвоенный интерфейс (который включает в себя оба), корпорация Майкрософт настоятельно рекомендует реализовать сдвоенные интерфейсы для всех, представленной в объекты OLE-автоматизации. Сдвоенные интерфейсы имеют значительные преимущества над `IDispatch`-только из цифр или только для VTBL интерфейсы:

- Привязки могут иметь место во время компиляции через интерфейс VTBL или во время выполнения с помощью `IDispatch`.

- Контроллеры OLE-автоматизации, которые могут использовать интерфейс VTBL может дать преимущества повышения производительности.

- Существующие контроллеры OLE-автоматизации, использующих `IDispatch` интерфейс будет продолжать работать.

- Интерфейс VTBL проще для вызова из C++.

- Сдвоенные интерфейсы являются обязательными для совместимости с функциями поддержки, объект Visual Basic.

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>Добавление поддержки сдвоенных интерфейсов для классов на основе CCmdTarget

Сдвоенный интерфейс это просто пользовательский интерфейс, производный от `IDispatch`. Самый простой способ реализации поддержки сдвоенных интерфейсов в `CCmdTarget`-класс на основе — Первая реализация диспетчеризации обычный интерфейс в классе с помощью MFC и ClassWizard, а затем добавьте пользовательский интерфейс более поздней версии. По большей части, просто делегируют реализации пользовательского интерфейса к MFC `IDispatch` реализации.

Во-первых измените ODL-файла для сервера, чтобы определить сдвоенные интерфейсы для объектов. Чтобы определить сдвоенный интерфейс, необходимо использовать оператор interface вместо `DISPINTERFACE` инструкции для создания мастера Visual C++. Вместо удаления существующего `DISPINTERFACE` инструкции, добавьте оператор новый интерфейс. За счет сохранения `DISPINTERFACE` форму, можно продолжать использовать ClassWizard для добавления свойств и методов для объекта, но необходимо добавить в инструкцию интерфейс эквивалентные свойства и методы.

Оператор interface для сдвоенный интерфейс должен иметь *OLEAUTOMATION* и *ДВОЙНОГО* атрибутов и интерфейс должен быть производным от `IDispatch`. Можно использовать [GUIDGEN](../visual-cpp-samples.md) образец для создания **IID** для сдвоенного интерфейса:

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

Получив interface-оператор в месте, начать добавление записей для методов и свойств. Сдвоенных интерфейсов, вам нужно изменить списки параметров таким образом, методы и функции метода доступа свойства в сдвоенный интерфейс возвращал **HRESULT** и передавать их возвращаемые значения в качестве параметров с атрибутами `[retval,out]`. Помните, что для свойств, будет необходимо добавить оба чтения (`propget`) и записи (`propput`) доступа к функции с одинаковым идентификатором. Пример:

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

Определив методы и свойства, необходимо добавить ссылку на интерфейс инструкции в инструкцию компонентного класса. Пример:

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

После ODL-файла будет обновлен, использовать механизм схем интерфейсов MFC чтобы определить класс реализации для сдвоенный интерфейс класса объекта и соответствующие записи в MFC `QueryInterface` механизм. Вам потребуется одна запись в `INTERFACE_PART` блок для каждой записи в операторе интерфейс ODL, а также записи для интерфейса диспетчеризации. Каждый элемент ODL с *propput* атрибут имел функция с именем `put_propertyname`. Каждый элемент с *propget* атрибут имел функция с именем `get_propertyname`.

Чтобы определить класс реализации для вашего сдвоенный интерфейс, добавьте `DUAL_INTERFACE_PART` блока к определению класса объекта. Пример:

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

Для подключения к MFC сдвоенный интерфейс [QueryInterface](/windows/desktop/com/queryinterface--navigating-in-an-object) механизм, добавить `INTERFACE_PART` запись схему интерфейсов:

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

Далее необходимо для заполнения в реализации интерфейса. В большинстве случаев, можно делегировать существующие MFC `IDispatch` реализации. Пример:

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

Для методов и функций метода доступа свойства объекта ее потребуется указать в реализации. Функции методов и свойств, обычно можно делегировать обратно к методам, созданный с помощью классов. Тем не менее если вы настроили свойства прямой доступ к переменным, необходимо написать код для get или put значение в переменную. Пример:

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

## <a name="passing-dual-interface-pointers"></a>Передача указателей сдвоенных интерфейсов

Передавая указатель сдвоенных интерфейсов не является простым, особенно в том случае, если необходимо вызвать `CCmdTarget::FromIDispatch`. `FromIDispatch` работает только с MFC `IDispatch` указатели. Один из способов для решения этой проблемы — для исходного запроса `IDispatch` набора указатель вверх по MFC и передать этот указатель функции, которым она необходима. Пример:

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

Прежде чем передавать указатель обратно через метод сдвоенных интерфейсов, может потребоваться преобразовать его из MFC `IDispatch` указатель на указатель сдвоенных интерфейсов. Пример:

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

## <a name="registering-the-applications-type-library"></a>Регистрации библиотеки типа приложения

AppWizard не создает код для регистрации библиотеки типов приложения сервера OLE-автоматизации в системе. Хотя существуют другие способы регистрирует создаваемые библиотеки типов, удобно приложение регистрирует создаваемые библиотеки типов при обновлении сведений о ее OLE-типе, то есть при каждом запуске автономного приложения.

Чтобы зарегистрировать библиотеку типов приложения при каждом запуске приложения изолированно:

- Включить AFXCTL. H в вашем стандартном включает файл заголовка, STDAFX. H, чтобы получить доступ к определению `AfxOleRegisterTypeLib` функции.

- В вашем приложении `InitInstance` функцию, найдите вызов `COleObjectFactory::UpdateRegistryAll`. После этого вызова, добавьте вызов `AfxOleRegisterTypeLib`, указав **LIBID** соответствующий тип библиотеки, наряду с именем библиотеки типов:

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

Чтобы изменить параметры сборки проекта, чтобы файл заголовка, содержащий **UUID** определения формируется MkTypLib всякий раз, когда перестраивается библиотеки типов:

1. На **построения** меню, щелкните **параметры**, а затем выберите ODL-файла из списка файлов для каждой конфигурации.

2. Нажмите кнопку **OLE типы** и укажите имя файла в **выходного заголовка** поле имя файла. Используйте имя файла, которое уже не используется в проекте, так как MkTypLib перезапишет существующий файл. Нажмите кнопку **ОК** закрыть **параметры построения** диалоговое окно.

Чтобы добавить **UUID** определений из MkTypLib созданный заголовочный файл в проект:

1. Включать MkTypLib созданный файл заголовка в вашем стандартном включает файл заголовка, STDAFX. З.

2. Создайте новый файл INITIIDS. CPP и добавьте его в проект. В этом файле включают файл заголовков, сформированные MkTypLib после включения OLE2. H и INITGUID. H:

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. На **построения** меню, щелкните **параметры**, а затем выберите INITIIDS. CPP из списка файлов для каждой конфигурации.

4. Нажмите кнопку **C++** вкладке, выберите категорию **предкомпилированные заголовки**и выберите **не использовать предварительно скомпилированные заголовки** "переключатель". Нажмите кнопку ОК, чтобы закрыть **параметры построения** диалоговое окно.

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>Указание правильного имени класса объекта в библиотеке типов

Мастеры, неправильно в состав Visual C++ позволяет указать компонентного класса в файле ODL сервера для OLE-создаваемых классов имя класса реализации. Хотя это будет работать, имя класса реализации, скорее всего, не является имя класса, который требуется пользователям объекта для использования. Чтобы указать правильное имя, откройте ODL-файла, найдите каждой инструкции компонентного класса и замените имя класса реализации с правильным именем внешних.

Обратите внимание, что при изменении инструкции компонентного класса, имена переменных из **CLSID**s в файле заголовка, сформированные MkTypLib изменится соответствующим образом. Будет необходимо обновить код, чтобы использовать новые имена переменных.

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>Обработка исключений и интерфейсах ошибок автоматизации

Методы и функции метода доступа свойства объект автоматизации может вызывать исключения. Если таким образом, необходимо их обработать в реализации сдвоенных интерфейсов и передать сведения об исключении обратно в контроллер в интерфейсе OLE-автоматизации обработки ошибок, `IErrorInfo`. Этот интерфейс предоставляет подробные, контекстные сведения об ошибке через оба `IDispatch` и интерфейсы VTBL. Чтобы указать, что доступен обработчик ошибок, следует реализовать `ISupportErrorInfo` интерфейс.

Чтобы проиллюстрировать механизма обработки ошибок, считать, что создаваемые ClassWizard функции, используемые для реализации поддержки standard диспетчеризации выдают исключения. Реализация MFC `IDispatch::Invoke` обычно перехватывает эти исключения и преобразует их в структуру EXCEPTINFO, который возвращается через `Invoke` вызова. Тем не менее если используется интерфейс VTBL, вы несете ответственность для перехвата исключений, самостоятельно. В качестве примера защиты методов сдвоенных интерфейсов:

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

`CATCH_ALL_DUAL` отвечает за возвращение правильный код ошибки, при возникновении исключения. `CATCH_ALL_DUAL` Преобразует исключения MFC в OLE-автоматизации обработки ошибок с помощью `ICreateErrorInfo` интерфейс. (Пример `CATCH_ALL_DUAL` макрос находится в файле MFCDUAL. H в [ACDUAL](../visual-cpp-samples.md) образца. Функция вызывается для обработки исключений, `DualHandleException`, находится в файле MFCDUAL. CPP.) `CATCH_ALL_DUAL` определяет код ошибки для возврата в зависимости от типа созданного исключения:

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) — в этом случае `HRESULT` создается с помощью следующий код:

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

   При этом создается `HRESULT` для интерфейса, вызвавшего исключение. Код ошибки компенсируется 0x200, чтобы предотвратить конфликты с помощью определяемого системой `HRESULT`s для стандартных интерфейсов OLE.

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) — в этом случае `E_OUTOFMEMORY` возвращается.

- Любое другое исключение — в данном случае `E_UNEXPECTED` возвращается.

Чтобы указать, что используется обработчик ошибок OLE-автоматизации, следует реализовать `ISupportErrorInfo` интерфейс.

Во-первых, добавьте код к определению класса автоматизации для отображения, он поддерживает `ISupportErrorInfo`.

Во-вторых, добавьте код в схему интерфейсов класса автоматизации, чтобы связать `ISupportErrorInfo` класс реализации с помощью MFC `QueryInterface` механизм. `INTERFACE_PART` Инструкции соответствует класс, определенный для `ISupportErrorInfo`.

Наконец, реализовать класс, определенный для поддержки `ISupportErrorInfo`.

( [ACDUAL](../visual-cpp-samples.md) образец содержит три макросы, чтобы помочь сделать эти три шага, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, и `IMPLEMENT_DUAL_ERRORINFO`, все содержащиеся в MFCDUAL. З.)

В следующем примере реализуется класс, определенный для поддержки `ISupportErrorInfo`. `CAutoClickDoc` Имя класса службы автоматизации и `IID_IDualAClick` — **IID** для интерфейса, который является источником ошибки, сообщенные через объект error OLE-автоматизации:

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

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
