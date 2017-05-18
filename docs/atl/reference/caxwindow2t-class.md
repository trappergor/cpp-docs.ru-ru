---
title: "Класс CAxWindow2T | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: a0724b0ea8922d1f39d8cf7ccd630068c32ea3ac
ms.contentlocale: ru-ru
ms.lasthandoff: 02/28/2017

---
# <a name="caxwindow2t-class"></a>Класс CAxWindow2T
Этот класс предоставляет методы для управления окно, которое размещает элемент управления ActiveX, а также включает поддержку для размещения Лицензированные элементы управления ActiveX.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```  
  
#### <a name="parameters"></a>Параметры  
 *TBase*  
 Класс, от которого `CAxWindowT` является производным.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Создает объект `CAxWindow2T`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|Создание главного окна.|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его, размещает в указанном окне и получает указатель на интерфейс (или указатели) с элементом управления.|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Статический метод, который получает имя класса окна.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|Назначает `HWND` к существующему `CAxWindow2T` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CAxWindow2T`Предоставляет методы для управления окна, содержащего элемент управления ActiveX. `CAxWindow2T`также включает поддержку для размещения Лицензированные элементы управления ActiveX. Размещение обеспечивается» **AtlAxWinLic80**», который является оболочкой для `CAxWindow2T`.  
  
 Класс `CAxWindow2` реализуется как специализацию `CAxWindow2T` класса. Данная специализация объявляется как:  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT`элементы описаны в разделе [CAxWindow](../../atl/reference/caxwindow-class.md).  
  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, использующего члены этого класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T  
 Создает объект `CAxWindow2T`.  
  
```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 Дескриптор существующего окна.  
  
##  <a name="create"></a>CAxWindow2T::Create  
 Создание главного окна.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="remarks"></a>Примечания  
 `CAxWindow2T::Create`вызовы [CWindow::Create](../../atl/reference/cwindow-class.md#create) с `LPCTSTR lpstrWndClass` параметру в класс окна, который обеспечивает размещение элементов управления ( **AtlAxWinLic80**).  
  
 В разделе `CWindow::Create` описание параметров и возвращаемого значения.  
  
 **Примечание** Если 0 служит значением для `MenuOrID` параметр, он должен быть указан как 0U (значение по умолчанию), чтобы избежать ошибки компилятора.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CAxWindow2T::Create`.  
  
##  <a name="createcontrollic"></a>CAxWindow2T::CreateControlLic  
 Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.  
  
```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bstrLicKey`  
 Лицензионный ключ для элемента управления; Значение NULL, если создание nonlicensed элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) описание оставшиеся параметры и возвращаемые значения.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CAxWindow2T::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx  
 Создает лицензированный элемент управления ActiveX, инициализирует его, размещает в указанном окне и получает указатель на интерфейс (или указатели) с элементом управления.  
  
```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bstrLicKey`  
 Лицензионный ключ для элемента управления; Значение NULL, если создание nonlicensed элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) описание оставшиеся параметры и возвращаемые значения.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CAxWindow2T::CreateControlLicEx`.  
  
##  <a name="getwndclassname"></a>CAxWindow2T::GetWndClassName  
 Получает имя класса окна.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, содержащую имя класса окна ( **AtlAxWinLic80**), можно разместить лицензированное и nonlicensed элементы управления ActiveX.  
  
##  <a name="operator_eq"></a>CAxWindow2T::operator =  
 Назначает `HWND` к существующему `CAxWindow2T` объекта.  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 Дескриптор существующего окна.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)

