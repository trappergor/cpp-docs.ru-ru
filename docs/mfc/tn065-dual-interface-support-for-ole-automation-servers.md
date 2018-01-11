---
title: "TN065: Поддержка сдвоенных интерфейсов для серверов автоматизации OLE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.ole
dev_langs: C++
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 959938be27e66a765ee0ae9e5aef9b3c1f1aed6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065. Поддержка сдвоенных интерфейсов для серверов автоматизации OLE
> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 Эта заметка рассматриваются как добавить поддержку сдвоенных интерфейсов для приложения сервера на базе MFC OLE-автоматизации. [ACDUAL](../visual-cpp-samples.md) примере описывается поддержка сдвоенных интерфейсов и пример кода в этой заметке берется из ACDUAL. Макросы, описанная в этой заметке, таких как `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, и `IMPLEMENT_DUAL_ERRORINFO`, входят в образце ACDUAL и можно найти в MFCDUAL. З.  
  
## <a name="dual-interfaces"></a>Сдвоенные интерфейсы  
 Несмотря на то, что OLE-автоматизации позволяет реализовать `IDispatch` интерфейс, интерфейс VTBL или сдвоенный интерфейс (который включает оба), корпорация Майкрософт настоятельно рекомендует реализовать сдвоенные интерфейсы для всех предоставленные объекты OLE-автоматизации. Сдвоенные интерфейсы имеют значительные преимущества над `IDispatch`-только или только для VTBL интерфейсов:  
  
-   Привязка может происходить во время компиляции через интерфейс VTBL или во время выполнения с помощью `IDispatch`.  
  
-   Контроллеры OLE-автоматизации, которые могут использовать интерфейс VTBL может дать преимущества повышения производительности.  
  
-   Существующие контроллеры OLE-автоматизации, использующих `IDispatch` интерфейс будет продолжать работать.  
  
-   Интерфейс VTBL проще вызвать из C++.  
  
-   Сдвоенные интерфейсы являются обязательными для совместимости с Visual Basic функции поддержки объекта.  
  
## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>Добавление поддержки сдвоенных интерфейсов для классов на основе CCmdTarget  
 Сдвоенный интерфейс-это просто это пользовательский интерфейс, производный от `IDispatch`. Самый простой способ реализации поддержка сдвоенных интерфейсов в `CCmdTarget`-на основе класса — для первой реализации диспетчеризации обычный интерфейс в классе с помощью MFC и ClassWizard, а затем добавьте пользовательский интерфейс более поздней версии. В большинстве случаев реализации пользовательского интерфейса просто передать обратно в MFC `IDispatch` реализации.  
  
 Во-первых измените ODL-файла для определения сдвоенных интерфейсов для объектов сервера. Чтобы определить сдвоенный интерфейс, необходимо использовать оператор interface вместо `DISPINTERFACE` инструкции, Создание мастеров Visual C++. Вместо удаления существующего `DISPINTERFACE` инструкции, добавить новый оператор interface. При этом `DISPINTERFACE` формы, можно продолжать использовать ClassWizard для добавления свойств и методов к объекту, но эквивалентные свойства и методы, необходимо добавить в инструкцию интерфейса.  
  
 Оператор interface для сдвоенный интерфейс должен иметь **OLEAUTOMATION** и **ДВОЙНОГО** атрибуты и интерфейс должен быть производным от `IDispatch`. Можно использовать [GUIDGEN](../visual-cpp-samples.md) образец для создания **IID** для сдвоенный интерфейс:  
  
```  
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick  
    oleautomation, 
    dual 
]  
interface IDualAClick : IDispatch  
 {  
 };  
```  
  
 После оператора interface на месте, приступите к добавлению записи для методов и свойств. Сдвоенные интерфейсы, необходимо изменить списки параметров таким образом, методы и функции метода доступа свойства в сдвоенный интерфейс возвращал `HRESULT` и передавать их возвращаемые значения в качестве параметров с атрибутами `[retval,out]`. Помните, что для свойств, будет необходимо добавить оба read (`propget`) и записи (`propput`) получить доступ к функции с тем же идентификатором. Пример:  
  
```  
[propput,
    id(1)] HRESULT text([in] BSTR newText);

[propget,
    id(1)] HRESULT text([out,
    retval] BSTR* retval);
```  
  
 После определения методов и свойств, необходимо добавить ссылку на интерфейс инструкции в инструкции компонентного класса. Пример:  
  
```  
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]  
coclass Document  
{  
    dispinterface IAClick;  
 [default] interface IDualAClick;  
};  
```  
  
 После обновления ODL-файла используйте механизма схем интерфейсов MFC для определения класс реализации для сдвоенный интерфейс класса объекта и внести соответствующие записи в MFC `QueryInterface` механизм. Необходимо, чтобы с одной записью `INTERFACE_PART` блок для каждой записи в операторе интерфейс ODL, а также записи для интерфейса диспетчеризации. Каждый элемент ODL с **propput** атрибут имел функция с именем `put_propertyname`. Каждый элемент с **propget** атрибут имел функция с именем `get_propertyname`.  
  
 Чтобы определить класс реализации для вашего сдвоенный интерфейс, добавьте `DUAL_INTERFACE_PART` блок в определении класса объекта. Пример:  
  
```  
BEGIN_DUAL_INTERFACE_PART(DualAClick,
    IDualAClick)  
    STDMETHOD(put_text)(THIS_ BSTR newText);

    STDMETHOD(get_text)(THIS_ BSTR FAR* retval);

    STDMETHOD(put_x)(THIS_ short newX);

    STDMETHOD(get_x)(THIS_ short FAR* retval);

    STDMETHOD(put_y)(THIS_ short newY);

    STDMETHOD(get_y)(THIS_ short FAR* retval);

    STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);

    STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);

    STDMETHOD(RefreshWindow)(THIS);

 STDMETHOD(SetAllProps)(THIS_ short x,
    short y,
    BSTR text);

    STDMETHOD(ShowWindow)(THIS);

END_DUAL_INTERFACE_PART(DualAClick) 
```  
  
 Для подключения к MFC сдвоенный интерфейс [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) механизм, добавить `INTERFACE_PART` запись схему интерфейсов:  
  
```  
BEGIN_INTERFACE_MAP(CAutoClickDoc,
    CDocument)  
    INTERFACE_PART(CAutoClickDoc,
    DIID_IAClick,
    Dispatch)  
    INTERFACE_PART(CAutoClickDoc,
    IID_IDualAClick,
    DualAClick)  
END_INTERFACE_MAP()  
```  
  
 Далее необходимо заполнить реализацию интерфейса. В большинстве случаев можно делегировать с существующие MFC `IDispatch` реализации. Пример:  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalAddRef();

}  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalRelease();

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalQueryInterface(&iid,
    ppvObj);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(
    UINT FAR* pctinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfoCount(pctinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(
    UINT itinfo,
    LCID lcid,
    ITypeInfo FAR* FAR* pptinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfo(itinfo,
    lcid,
    pptinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(
    REFIID riid,
    OLECHAR FAR* FAR* rgszNames,
    UINT cNames,  
    LCID lcid,
    DISPID FAR* rgdispid)   
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetIDsOfNames(riid,
    rgszNames,
    cNames,   
    lcid,
    rgdispid);

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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->Invoke(dispidMember,
    riid,
    lcid,  
    wFlags,
    pdispparams,
    pvarResult,  
    pexcepinfo,
    puArgErr);

}  
```  
  
 Методы и функции метода доступа свойства объекта необходимо заполнить реализации. Метод и свойство функций обычно можно делегировать обратно в методы, созданные с помощью классов. Если настройка свойств напрямую обращаться к переменным, необходимо написать код для get и put значение в переменную. Пример:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Unicode BSTR to *// Ansi CString,
    if necessary...  
    pThis->m_str = newText;  
    return NOERROR;  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Ansi CString to *// Unicode BSTR,
    if necessary...  
    pThis->m_str.SetSysString(retval);

 return NOERROR;  
}  
```  
  
## <a name="passing-dual-interface-pointers"></a>Передача указателей на сдвоенные интерфейсы  
 Передача указатель сдвоенных интерфейсов не является простым, особенно в том случае, если необходимо вызвать `CCmdTarget::FromIDispatch`. `FromIDispatch`работает только с MFC `IDispatch` указатели. Является одним из способов обхода этого запроса для исходного `IDispatch` набор указатель вверх по MFC и передать данный указатель функции, которым она необходима. Пример:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_Position(
    IDualAutoClickPoint FAR* newPosition)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDisp;  
    lpDisp = pThis->GetPosition();
lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);

    return NOERROR;  
}  
```  
  
## <a name="registering-the-applications-type-library"></a>Регистрация приложения библиотеки типов  
 Мастер приложений не создает код, чтобы зарегистрировать библиотеку типов для приложения сервера OLE-автоматизации в системе. Хотя есть и другие способы регистрации библиотеки типов, удобно приложением зарегистрировать библиотеку типов, при обновлении сведения об этом типе OLE, то есть, при каждом запуске изолированного приложения.  
  
 Для регистрации библиотеки типов приложения при каждом запуске приложения независимо от них:  
  
-   Включить AFXCTL. H в вашей стандартной включает файл заголовка, STDAFX. H, чтобы получить доступ к определению `AfxOleRegisterTypeLib` функции.  
  
-   В вашем приложении `InitInstance` функцию, найдите вызов `COleObjectFactory::UpdateRegistryAll`. После этого вызова, добавьте вызов `AfxOleRegisterTypeLib`, указав **LIBID** соответствующий свою библиотеку типов, вместе с именем библиотеки типов:  
  
 '' "* / / При запуске серверного приложения автономного рекомендуется * / / чтобы обновить реестр в случае, если он поврежден.  
    m_server. UpdateRegistry(OAT_DISPATCH_OBJECT);

 COleObjectFactory::UpdateRegistryAll(); * / / DUAL_SUPPORT_START * / и убедитесь, что библиотека типов зарегистрирована или сдвоенный интерфейс не будет работать.  
AfxOleRegisterTypeLib(AfxGetInstanceHandle() LIBID_ACDual, _T("AutoClik.TLB")); * / / DUAL_SUPPORT_END  
 ```  
  
## Modifying Project Build Settings to Accommodate Type Library Changes  
 To modify a project's build settings so that a header file containing **UUID** definitions is generated by MkTypLib whenever the type library is rebuilt:  
  
1.  On the **Build** menu, click **Settings**, and then select the ODL file from the file list for each configuration.  
  
2.  Click the **OLE Types** tab and specify a filename in the **Output header** filename field. Use a filename that is not already used by your project, because MkTypLib will overwrite any existing file. Click **OK** to close the **Build Settings** dialog box.  
  
 To add the **UUID** definitions from the MkTypLib-generated header file to your project:  
  
1.  Include the MkTypLib-generated header file in your standard includes header file, STDAFX.H.  
  
2.  Create a new file, INITIIDS.CPP, and add it to your project. In this file, include your MkTypLib-generated header file after including OLE2.H and INITGUID.H:  
  
 ```  
    initIIDs.c: Определяет IID для сдвоенные интерфейсы  
    Это не должны быть построены с предкомпилированным заголовком.  
      #<a name="include-ole2h"></a>включить < ole2.h >  
      #<a name="include-initguidh"></a>Включите < initguid.h >  
      #<a name="include-acdualh"></a>включить «acdual.h»  
 ```  
  
3.  On the **Build** menu, click **Settings**, and then select INITIIDS.CPP from the file list for each configuration.  
  
4.  Click the **C++** tab, click category **Precompiled Headers**, and select the **Not using precompiled headers** radio button. Click OK to close the **Build Settings** dialog box.  
  
## Specifying the Correct Object Class Name in the Type Library  
 The wizards shipped with Visual C++ incorrectly use the implementation class name to specify the coclass in the server's ODL file for OLE-creatable classes. While this will work, the implementation class name is probably not the class name you want users of your object to use. To specify the correct name, open the ODL file, locate each coclass statement, and replace the implementation class name with the correct external name.  
  
 Note that when the coclass statement is changed, the variable names of **CLSID**s in the MkTypLib-generated header file will change accordingly. You will need to update your code to use the new variable names.  
  
## Handling Exceptions and the Automation Error Interfaces  
 Your automation object's methods and property accessor functions may throw exceptions. If so, you should handle them in your dual-interface implementation and pass information about the exception back to the controller through the OLE Automation error-handling interface, **IErrorInfo**. This interface provides for detailed, contextual error information through both `IDispatch` and VTBL interfaces. To indicate that an error handler is available, you should implement the **ISupportErrorInfo** interface.  
  
 To illustrate the error-handling mechanism, assume that the ClassWizard-generated functions used to implement the standard dispatch support throw exceptions. MFC's implementation of **IDispatch::Invoke** typically catches these exceptions and converts them into an EXCEPTINFO structure that is returned through the `Invoke` call. However, when VTBL interface is used, you are responsible for catching the exceptions yourself. As an example of protecting your dual-interface methods:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE (CAutoClickDoc, DualAClick)  
    TRY_DUAL(IID_IDualAClick) {* / / MFC автоматически преобразует из BSTR Юникода для * / / Ansi CString, при необходимости...  
    pThis -> m_str = newText;  
    Возвращает значение NOERROR;  
 }  
    CATCH_ALL_DUAL}  
```  
  
 `CATCH_ALL_DUAL` takes care of returning the correct error code when an exception occurs. `CATCH_ALL_DUAL` converts an MFC exception into OLE Automation error-handling information using the **ICreateErrorInfo** interface. (An example `CATCH_ALL_DUAL` macro is in the file MFCDUAL.H in the [ACDUAL](../visual-cpp-samples.md) sample. The function it calls to handle exceptions, `DualHandleException`, is in the file MFCDUAL.CPP.) `CATCH_ALL_DUAL` determines the error code to return based on the type of exception that occurred:  
  
- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) - In this case, `HRESULT` is constructed using the following code:  
  
 ```  
    hr = MAKE_HRESULT(SEVERITY_ERROR,
    FACILITY_ITF,   
 (e -> m_wCode + 0x200));

 ```  
  
     This creates an `HRESULT` specific to the interface that caused the exception. The error code is offset by 0x200 to avoid any conflicts with system-defined `HRESULT`s for standard OLE interfaces.  
  
- [CMemoryException](../mfc/reference/cmemoryexception-class.md) - In this case, `E_OUTOFMEMORY` is returned.  
  
-   Any other exception - In this case, `E_UNEXPECTED` is returned.  
  
 To indicate that the OLE Automation error handler is used, you should also implement the **ISupportErrorInfo** interface.  
  
 First, add code to your automation class definition to show it supports **ISupportErrorInfo**.  
  
 Second, add code to your automation class's interface map to associate the **ISupportErrorInfo** implementation class with MFC's `QueryInterface` mechanism. The `INTERFACE_PART` statement matches the class defined for **ISupportErrorInfo**.  
  
 Finally, implement the class defined to support **ISupportErrorInfo**.  
  
 (The [ACDUAL](../visual-cpp-samples.md) sample contains three macros to help do these three steps, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, and `IMPLEMENT_DUAL_ERRORINFO`, all contained in MFCDUAL.H.)  
  
 The following example implements a class defined to support **ISupportErrorInfo**. `CAutoClickDoc` is the name of your automation class and `IID_IDualAClick` is the **IID** for the interface that is the source of errors reported through the OLE Automation error object:  
  
```  
STDMETHODIMP_(ulong) CAutoClickDoc::XSupportErrorInfo::AddRef()   
{  
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    Возврат pThis -> ExternalAddRef();

}   
STDMETHODIMP_(ulong) CAutoClickDoc::XSupportErrorInfo::Release()   
{   
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    Возврат pThis -> ExternalRelease();

}   
CAutoClickDoc::XSupportErrorInfo::QueryInterface STDMETHODIMP (REFIID iid, LPVOID * ppvObj)   
{   
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    Возврат pThis -> ExternalQueryInterface (& iid, ppvObj);

}   
CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo STDMETHODIMP (REFIID iid)   
{   
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    Возвращает (iid == IID_IDualAClick) S_OK: S_FALSE;   
}  
```  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)

