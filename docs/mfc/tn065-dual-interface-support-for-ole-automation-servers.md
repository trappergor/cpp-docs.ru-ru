---
title: "TN065. Поддержка сдвоенных интерфейсов для серверов автоматизации OLE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ACDUAL - пример [MFC]"
  - "Серверы автоматизации, поддержка двойного интерфейса"
  - "сдвоенные интерфейсы, Автоматизация OLE"
  - "TN065"
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# TN065. Поддержка сдвоенных интерфейсов для серверов автоматизации OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию.  В результате некоторые процедуры и разделы могут быть устаревшими или неверными.  Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 Эта заметка в этом разделе описано, как добавить поддержку сдвоенных интерфейсов в приложение сервера OLE\-автоматизации на основе MFC.  Образец [В образце ACDUAL](../top/visual-cpp-samples.md) показывает поддержки сдвоенных интерфейсов и пример кода в этой заметке взят из ACDUAL.  Макросы, описанные в этой заметке, например `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART` и `IMPLEMENT_DUAL_ERRORINFO`, входит в пример ACDUAL и могут быть найдены в MFCDUAL.H.  
  
## Сдвоенные интерфейсы  
 Хотя ole\-автоматизации позволяет реализовать интерфейс `IDispatch`, интерфейс VTBL или сдвоенный интерфейс, включающий как \(Майкрософт\), настоятельно рекомендуется реализовать сдвоенные интерфейсы для всех доступных объектов ole\-автоматизации.  Сдвоенные интерфейсы есть существенные преимущества по сравнению с интерфейсами `IDispatch` только для или только для VTBL:  
  
-   Привязка может произойти во время компиляции через интерфейс VTBL или во время выполнения с помощью `IDispatch`.  
  
-   Контроллеры ole\-автоматизации, могут использовать интерфейс VTBL могут извлекать повышения производительности.  
  
-   Существующие контроллеры ole\-автоматизации, использующих интерфейс `IDispatch` продолжат работать.  
  
-   Интерфейс VTBL легче вызова из C C\+\+.  
  
-   Сдвоенные интерфейсы, необходимые для обеспечения совместимости с функциями поддержки объекта Visual Basic.  
  
## Добавление поддержки сдвоенных интерфейсов в класс CCmdTarget\-.  
 Сдвоенный интерфейс действительно только пользовательский интерфейс, производный от `IDispatch`.  Самый простой способ реализации поддержки сдвоенных интерфейсов в классе `CCmdTarget` на основе с первым обычно реализует интерфейс диспетчеризации в классе с помощью MFC и ClassWizard и добавляет пользовательский интерфейс позже.  В большинстве случаев пользовательскую реализацию интерфейса просто делегирует обратно в реализации MFC `IDispatch`.  
  
 Во\-первых, изменение odl\-файла сервера для определения сдвоенные интерфейсы для объектов.  Для определения сдвоенный интерфейс следует использовать вместо оператора интерфейса выписки `DISPINTERFACE`, мастера Visual C\+\+ создают C.  Вместо удаление существующей выписка `DISPINTERFACE` добавьте новую выписка интерфейса.  Сохранение, форма `DISPINTERFACE` можно продолжить использовать ClassWizard для добавления свойства и методы в объект, но необходимо добавить соответствующие свойства и методы в инструкцию интерфейса.  
  
 Выписка интерфейса для сдвоенного интерфейса должна иметь атрибуты **OLEAUTOMATION** и **DUAL**, интерфейс должен наследоваться от `IDispatch`.  Можно использовать пример [GUIDGEN](../top/visual-cpp-samples.md) для создания **IID** сдвоенных интерфейсов:  
  
```  
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick  
   oleautomation,  
   dual  
]  
interface IDualAClick : IDispatch  
  {  
  };  
```  
  
 Как только получен оператора интерфейса на месте, начните добавление записи для методов и свойств.  Для сдвоенных интерфейсов необходимо самостоятельно упорядочится списки параметров, чтобы собственные методы и функции метод доступа к свойству в интерфейсе сдвоенном возвращают `HRESULT` и передают их возвращаемые значения в качестве параметров с атрибутами `[retval,out]`.  Помните, что для свойств, или потребуется добавить и \(`propget`\) и создать функцию доступа \(`propput`\) с таким же идентификатором.  Примеры.  
  
```  
[propput, id(1)] HRESULT text([in] BSTR newText);  
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);  
```  
  
 После методов и свойств укажите необходимо добавить ссылку на инструкцию интерфейса в инструкцию компонентного класса.  Примеры.  
  
```  
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]  
coclass Document  
{  
   dispinterface IAClick;  
   [default] interface IDualAClick;  
};  
```  
  
 После создания odl\-файла был обновлен, используйте механизм сопоставления интерфейсов MFC для определения класса реализации сдвоенного интерфейса в классе объекта и выполнить соответствующие записи в механизме `QueryInterface` MFC.  Требуется одна запись в блоке `INTERFACE_PART` для каждой записи в инструкцию интерфейса ODL, плюс записи для интерфейса диспетчеризации.  Каждой записи ODL атрибутом **propput** требуется функцию с именем `put_propertyname`.  Каждой записи с атрибутом **propget** требуется функцию с именем `get_propertyname`.  
  
 Для определения класса для реализации сдвоенного интерфейса добавьте блок `DUAL_INTERFACE_PART` в определение класса объекта.  Примеры.  
  
```  
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
  
 Для подключения к механизму сдвоенный интерфейс [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) MFC добавьте запись `INTERFACE_PART` к сопоставлению интерфейса:  
  
```  
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)  
  INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)  
  INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)  
END_INTERFACE_MAP()  
```  
  
 Далее необходимо заполнить реализацию интерфейса.  В большинстве случаев будет делегировать к существующей реализации MFC `IDispatch`.  Примеры.  
  
```  
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
             REFIID iid, LPVOID* ppvObj)  
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
          UINT itinfo, LCID lcid, ITypeInfo FAR* FAR* pptinfo)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetTypeInfo(itinfo, lcid, pptinfo);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(  
       REFIID riid, OLECHAR FAR* FAR* rgszNames, UINT cNames,  
       LCID lcid, DISPID FAR* rgdispid)   
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetIDsOfNames(riid, rgszNames, cNames,   
                                    lcid, rgdispid);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::Invoke(  
    DISPID dispidMember, REFIID riid, LCID lcid, WORD wFlags,  
    DISPPARAMS FAR* pdispparams, VARIANT FAR* pvarResult,  
    EXCEPINFO FAR* pexcepinfo, UINT FAR* puArgErr)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->Invoke(dispidMember, riid, lcid,  
                             wFlags, pdispparams, pvarResult,  
                             pexcepinfo, puArgErr);  
}  
```  
  
 Для методов объекта класса и функций метод доступа к свойству необходимо заполнить реализацию.  В метод и функции свойств могут обычно делегировать обратно к методам, используя ClassWizard.  Однако при необходимости настройки свойств для получения переменные непосредственно, требуется написать, код, который необходимо получить\/положил значение в переменную.  Примеры.  
  
```  
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
  
## Передача указателей на сдвоенные интерфейсы  
 Передача указатель на сдвоенные интерфейсы не простой, особенно если необходимо вызвать `CCmdTarget::FromIDispatch`.  `FromIDispatch` только работает над указателями `IDispatch` MFC.  Один из способов обхода этого ограничения на запрос для исходной настройки указателя `IDispatch` MFC и пропуском этот указатель на функции, нужно.  Примеры.  
  
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
  
 Перед передачей указатель назад по метод сдвоенных интерфейсов, можно преобразовать его из указателя MFC `IDispatch` в указатель сдвоенных интерфейсов.  Примеры.  
  
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
  
## Регистрация библиотеки типов приложения  
 AppWizard не создает код для регистрации библиотеки типов приложения сервера OLE\-автоматизации в системе.  В то время как другие способы зарегистрировать библиотеку типов, удобно иметь регистр приложения библиотеки типов, когда он обновляет его OLE сведения о типе, то есть когда приложение, выполняемое изолированное.  
  
 Регистрация библиотеки типов приложения, когда приложение, выполняемое изолированного:  
  
-   Включите AFXCTL.H в стандарте включает файл заголовка, STDAFX.H, чтобы получить определение функции `AfxOleRegisterTypeLib`.  
  
-   В функции `InitInstance` приложения найдите вызов `COleObjectFactory::UpdateRegistryAll`.  После этого вызова добавьте вызов `AfxOleRegisterTypeLib`, указав **LIBID** соответствует библиотеке типов вместе с именем вашей библиотеки типов:  
  
    ```  
    // When a server application is launched stand-alone, it is a good idea  
    // to update the system registry in case it has been damaged.  
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);  
    COleObjectFactory::UpdateRegistryAll();  
    // DUAL_SUPPORT_START  
    // Make sure the type library is registered or dual interface won't work.  
    AfxOleRegisterTypeLib(AfxGetInstanceHandle(), LIBID_ACDual, _T("AutoClik.TLB"));  
    // DUAL_SUPPORT_END  
    ```  
  
## Изменение параметров построения проекта в соответствии с изменениями библиотеки типов  
 Изменение параметров построения проекта, чтобы файл заголовка, содержащих определения **UUID** создается MkTypLib, когда библиотека типов перестроена.  
  
1.  В меню **Сборка** выберите пункт **Параметры**, а затем выбирает odl\-файла из списка файлов для каждой конфигурации.  
  
2.  Щелкните вкладку **Типы OLE** и укажите имя файла в поле имени файла **Заголовок.** Имена файлов, которые еще не используется проектом, поскольку MkTypLib перезаписать существующий файл.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно **Параметры сборки**.  
  
 Добавление определения **UUID** из MkTypLib\- создаваемого файла заголовка в проект.  
  
1.  Включите MkTypLib\- созданный файл заголовка в стандарте включает файл заголовка, STDAFX.H.  
  
2.  Создайте новый файл, INITIIDS.CPP и добавьте его к проекту.  В этом файле, включите в MkTypLib\- созданный файл заголовка позже, включая OLE2.H и INITGUID.H:  
  
    ```  
    // initIIDs.c: defines IIDs for dual interfaces  
    // This must not be built with precompiled header.  
      #include <ole2.h>  
      #include <initguid.h>  
      #include "acdual.h"  
    ```  
  
3.  В меню **Сборка** выберите пункт **Параметры**, а затем выбирает INITIIDS.CPP из списка файлов для каждой конфигурации.  
  
4.  Щелкните вкладку **C\+\+**, щелкните категорию **Предварительно откомпилированные заголовки** и выделите переключатель **Не использовать предварительно скомпилированные заголовки**.  Нажмите кнопку " ОК ", чтобы закрыть диалоговое окно **Параметры сборки**.  
  
## Указание правильного имени класса объекта в библиотеке типов.  
 Мастера поставлявшиеся с Visual C\+\+ неправильно используют имя класса реализации, чтобы определить компонентный класс в файле ODL сервера для классов OLE — могут быть созданы.  Поскольку это будет работать, имя класса реализации не может имени класса требуется пользователям объекта, который необходимо использовать.  Для определения правильного имени откройте odl\-файла найдите каждую выписка компонентного класса и замените имя класса реализации с правильным внешним именем.  
  
 Обратите внимание, что если выписка компонентного класса будет изменена, имена переменных **CLSID** MkTypLib\- s в созданном файле заголовка изменяются соответствующим образом.  Потребуется обновить код для использования новых имен переменных.  
  
## Обработка исключений и интерфейсы ошибок автоматизации  
 Методы объекта класса автоматизации и функции метод доступа к свойству могут создавать исключения.  В этом случае необходимо обработать их реализации сдвоенного интерфейса и передавать сведения об исключении назад к контроллеру ole\-автоматизации через интерфейс обработки ошибок, **IErrorInfo**.  Этот интерфейс предоставляет более подробные сведения об ошибке, контекстно\-зависимого как через `IDispatch`, так и через интерфейсы VTBL.  Чтобы указать, что обработчик ошибок доступен, необходимо реализовать интерфейс **Интерфейс ISupportErrorInfo**.  
  
 Для демонстрации механизм обработки ошибок высказывать ClassWizard\- созданные функции, используемые для реализации поддержки стандартные исключения выполнения диспетчеризации.  Реализация MFC **IDispatch::Invoke** обычно перехватывает эти исключения и преобразует их в структуру EXCEPTINFO, возвращается посредством вызова `Invoke`.  Однако если интерфейс VTBL используется, самостоятельно ответственность за определение исключения.  В качестве примера защитить методы сдвоенных интерфейсов:  
  
```  
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
  
 `CATCH_ALL_DUAL` следит за возврата кода исправления ошибок при возникновении исключения.  `CATCH_ALL_DUAL` преобразования исключение MFC данные по ole\-автоматизации обработки ошибок с помощью интерфейса **ICreateErrorInfo**. \(Макрос `CATCH_ALL_DUAL` примера в файле MFCDUAL.H в примере [В образце ACDUAL](../top/visual-cpp-samples.md).  Функция она вызывает для обработки исключений, `DualHandleException`, в файле MFCDUAL.CPP.\) `CATCH_ALL_DUAL` указывается код ошибки для возврата на основе типа исключения, начавший:  
  
-   [COleDispatchException](../Topic/COleDispatchException%20Class.md) \(В данном случае `HRESULT` построен с помощью следующего кода:  
  
    ```  
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF,   
                               (e->m_wCode + 0x200));  
    ```  
  
     При этом создается с `HRESULT` на интерфейс, который вызвал исключение.  Код ошибки смещаться 0x200 во избежание всех конфликтов с системой указанным `HRESULT` для стандартных интерфейсов OLE.  
  
-   [CMemoryException](../mfc/reference/cmemoryexception-class.md) \(В данном случае `E_OUTOFMEMORY` возвращается.  
  
-   Любое другое исключение \(в данном случае `E_UNEXPECTED` возвращается.  
  
 Чтобы указать, что обработчик ошибок ole\-автоматизации используется, необходимо также реализовать интерфейс **Интерфейс ISupportErrorInfo**.  
  
 Сначала добавьте код в определение класса автоматизации для отображения поддерживает **Интерфейс ISupportErrorInfo**.  
  
 Во\-вторых, добавьте код в сопоставление интерфейса класса автоматизации, чтобы связать класс реализации **Интерфейс ISupportErrorInfo** с механизмом `QueryInterface` MFC.  Выписка `INTERFACE_PART` соответствует класс, определенный для **Интерфейс ISupportErrorInfo**.  
  
 Наконец, реализуйте класс, определенный для поддержки **Интерфейс ISupportErrorInfo**.  
  
 \(В примере [В образце ACDUAL](../top/visual-cpp-samples.md) содержит 3 макроса, помогающие делать шага 3, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART` и `IMPLEMENT_DUAL_ERRORINFO`; все, содержащиеся в MFCDUAL.H\).  
  
 В следующем примере реализуется класс, определенный для поддержки **Интерфейс ISupportErrorInfo**.  `CAutoClickDoc` имя класса автоматизации и `IID_IDualAClick`**IID** для интерфейса, источник ошибок сообщенных через объект ошибки ole\-автоматизации.  
  
```  
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
   REFIID iid, LPVOID* ppvObj)   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return pThis->ExternalQueryInterface(&iid, ppvObj);   
}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo(   
   REFIID iid)   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return (iid == IID_IDualAClick) ? S_OK : S_FALSE;   
}  
```  
  
## См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)