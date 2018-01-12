---
title: "Класс CAxWindow2T | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12b7c8c66a092a92ef7fce25ce283f5145d9f910
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="caxwindow2t-class"></a>Класс CAxWindow2T
Этот класс предоставляет методы для работы с окном, размещает элемент ActiveX, а также поддержка размещения Лицензированные элементы управления ActiveX.  
  
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
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Создает объект `CAxWindow2T`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|Создает главное окно.|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его, размещает в указанном окне и возвращает указатель интерфейса (или указатели) из элемента управления.|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Статический метод, который получает имя класса окна.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|Назначает `HWND` к существующему `CAxWindow2T` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CAxWindow2T`Предоставляет методы для управления окна, на котором размещается элемент управления ActiveX. `CAxWindow2T`также включает поддержку для размещения Лицензированные элементы управления ActiveX. Обеспечивается размещения» **AtlAxWinLic80**«, который является оболочкой для `CAxWindow2T`.  
  
 Класс `CAxWindow2` реализуется в виде специализацией `CAxWindow2T` класса. Такая специализация объявляется как:  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT`члены описаны в разделе [CAxWindow](../../atl/reference/caxwindow-class.md).  
  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий члены этого класса.  
  
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
 Дескриптор существующему окну.  
  
##  <a name="create"></a>CAxWindow2T::Create  
 Создает главное окно.  
  
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
 `CAxWindow2T::Create`вызовы [CWindow::Create](../../atl/reference/cwindow-class.md#create) с `LPCTSTR lpstrWndClass` равным класс окна, который обеспечивает размещение элементов управления ( **AtlAxWinLic80**).  
  
 В разделе `CWindow::Create` описание параметров и возвращаемого значения.  
  
 **Примечание** при использовании 0 в качестве значения для `MenuOrID` параметра, он должен быть указан как 0U (значение по умолчанию) для предотвращения ошибок компилятора.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CAxWindow2T::Create`.  
  
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
 Лицензионный ключ для элемента управления. Значение NULL, если создание nonlicensed элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) описание оставшиеся параметры и возвращаемые значения.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CAxWindow2T::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx  
 Создает лицензированный элемент управления ActiveX, инициализирует его, размещает в указанном окне и возвращает указатель интерфейса (или указатели) из элемента управления.  
  
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
 Лицензионный ключ для элемента управления. Значение NULL, если создание nonlicensed элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) описание оставшиеся параметры и возвращаемые значения.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CAxWindow2T::CreateControlLicEx`.  
  
##  <a name="getwndclassname"></a>CAxWindow2T::GetWndClassName  
 Извлекает имя класса окна.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, содержащую имя класса окна ( **AtlAxWinLic80**), можно разместить лицензионную версию, nonlicensed элементы управления ActiveX.  
  
##  <a name="operator_eq"></a>CAxWindow2T::operator =  
 Назначает `HWND` к существующему `CAxWindow2T` объекта.  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 Дескриптор существующему окну.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)
