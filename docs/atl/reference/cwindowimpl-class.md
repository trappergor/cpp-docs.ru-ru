---
title: "Класс CWindowImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::DefWindowProc
- ATLWIN/ATL::GetCurrentMessage
- ATLWIN/ATL::GetWindowProc
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::SubclassWindow
- ATLWIN/ATL::UnsubclassWindow
- ATLWIN/ATL::GetWndClassInfo
- ATLWIN/ATL::WindowProc
- ATLWIN/ATL::m_pfnSuperWindowProc
dev_langs:
- C++
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 76827682e96d2aea80880fa7d70c267abe02ee1c
ms.lasthandoff: 02/24/2017

---
# <a name="cwindowimpl-class"></a>Класс CWindowImpl
Предоставляет методы для создания или создание подкласса для окна.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```    
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Новый класс, производный от `CWindowImpl`.  
  
 *TBase*  
 Базовый класс для класса. По умолчанию базовым классом является [CWindow](../../atl/reference/cwindow-class.md).  
  
 `TWinTraits`  
 Объект [класс характеристик](../../atl/understanding-window-traits.md) , определяющий стили для окна. Значение по умолчанию — `CControlWinTraits`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWindowImpl::Create](#create)|Создает окно.|  
  
### <a name="cwindowimplbaset-methods"></a>Методы CWindowImplBaseT  
  
|||  
|-|-|  
|[DefWindowProc](#defwindowproc)|Обеспечивает обработку сообщений по умолчанию.|  
|[GetCurrentMessage](#getcurrentmessage)|Возвращает текущее сообщение.|  
|[GetWindowProc](#getwindowproc)|Возвращает текущую процедуру окна.|  
|[OnFinalMessage](#onfinalmessage)|Вызывается после получения последнего сообщения (обычно `WM_NCDESTROY`).|  
|[SubclassWindow](#subclasswindow)|Подклассы окно.|  
|[UnsubclassWindow](#unsubclasswindow)|Восстановление ранее подклассов окна.|  
  
### <a name="static-methods"></a>Статические методы  
  
|||  
|-|-|  
|[GetWndClassInfo](#getwndclassinfo)|Возвращает статический экземпляр [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md), который управляет информация о классе окна.|  
|[WindowProc](#windowproc)|Обрабатывает сообщения, отправленные в окно.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Указывает исходную процедуру окна класс окна.|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `CWindowImpl` для создания окна или подкласс существующее окно. `CWindowImpl` процедура окна использует схему сообщений для направления сообщений для соответствующих обработчиков.  
  
 `CWindowImpl::Create`Создает окно на основе данных класса окна под управлением [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl`содержит [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) макросом, который означает `CWndClassInfo` регистрирует новый класс окна. Если вы хотите суперкласса существующий класс окон, необходимо создать собственный класс из `CWindowImpl` и включить [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) макрос. В этом случае `CWndClassInfo` регистрирует класс окна, который основан на существующем классе, но использует `CWindowImpl::WindowProc`. Пример:  
  
 [!code-cpp[NVC_ATL_Windowing&#43;](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  Поскольку `CWndClassInfo` управляет сведениями для лишь один класс окна каждого окна, созданные с помощью экземпляра `CWindowImpl` основана на один класс.  
  
 `CWindowImpl`также поддерживает создать подкласс окна. `SubclassWindow` Метод присоединяет к существующему окну `CWindowImpl` объекта и изменяет процедура окна для `CWindowImpl::WindowProc`. Каждый экземпляр `CWindowImpl` можно создать подкласс другое окно.  
  
> [!NOTE]
>  Для любой заданной `CWindowImpl` , либо вызовите **создать** или `SubclassWindow`. Не вызвать оба метода в том же объекте.  
  
 В дополнение к `CWindowImpl`, библиотека ATL предоставляет [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) для создания окна, которое содержится в другом объекте.  
  
 Деструктор базового класса (~ **CWindowImplRoot**) гарантирует, что окно будет удален перед уничтожением объекта.  
  
 `CWindowImpl`является производным от **CWindowImplBaseT**, который является производным от **CWindowImplRoot**, который является производным от **TBase** и [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
|Дополнительные сведения о|См.|  
|--------------------------------|---------|  
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|  
|Использование окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|  
|Мастер проектов ATL|[Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="create"></a>CWindowImpl::Create  
 Создает окно, в зависимости от нового класса окна.  
  
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
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 [in] Дескриптор окна родительского или владельца.  
  
 `rect`  
 [in] Объект [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, задающая положение окна. `RECT` Можно передать указатель или ссылка.  
  
 `szWindowName`  
 [in] Задает имя окна. Значение по умолчанию — **NULL**.  
  
 `dwStyle`  
 [in] Стиль окна. Это значение объединяется с использованием стиля, предоставляемый класс характеристик для окна. Значение по умолчанию предоставляет класс полный контроль над стиль характеристиками. Список возможных значений см. в разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwExStyle`  
 [in] Стиль окна расширенного. Это значение объединяется с использованием стиля, предоставляемый класс характеристик для окна. Значение по умолчанию предоставляет класс полный контроль над стиль характеристиками. Список возможных значений см. в разделе [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `MenuOrID`  
 [in] Для дочернего окна код окна. Для окна верхнего уровня, дескриптор меню для окна. Значение по умолчанию — **0U**.  
  
 `lpCreateParam`  
 [in] Указатель на создание окна данных. Полное описание см. в описании для последнего параметра для [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха дескриптор для созданного окна. В противном случае — **NULL**.  
  
### <a name="remarks"></a>Примечания  
 **Создание** сначала регистрирует класс окна, если он не был зарегистрирован. Вновь созданное окно, автоматически присоединяется к `CWindowImpl` объекта.  
  
> [!NOTE]
>  Не следует вызывать **создать** Если уже был вызван [SubclassWindow](#subclasswindow).  
  
 Чтобы использовать класс окна, который основан на существующий класс окон, сформируйте класс из `CWindowImpl` и включить [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) макрос. Процедура окна существующий класс окон сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc). Дополнительные сведения см. в разделе [CWindowImpl](../../atl/reference/cwindowimpl-class.md) Обзор.  
  
> [!NOTE]
>  Если 0 служит значением для `MenuOrID` параметр, он должен быть указан как 0U (значение по умолчанию), чтобы избежать ошибки компилятора.  
  
##  <a name="defwindowproc"></a>CWindowImpl::DefWindowProc  
 Вызывается методом [WindowProc](#windowproc) для обработки сообщений, не обрабатываются в схеме сообщений.  
  
```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```  
  
### <a name="parameters"></a>Параметры  
 `uMsg`  
 [in] Сообщение отправлено в окно.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `DefWindowProc` вызовов [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) функцию Win32 для отправки сведений сообщение процедуре окна, указанный в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
 Функция без параметров автоматически извлекает необходимые параметры из текущего сообщения.  
  
##  <a name="getcurrentmessage"></a>CWindowImpl::GetCurrentMessage  
 Возвращает текущее сообщение, упакованные в `MSG` структуру.  
  
```
const MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее сообщение.  
  
##  <a name="getwindowproc"></a>CWindowImpl::GetWindowProc  
 Возвращает `WindowProc`, текущую процедуру окна.  
  
```
virtual WNDPROC GetWindowProc();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущую процедуру окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для замены процедуры окна на свои собственные.  
  
##  <a name="getwndclassinfo"></a>CWindowImpl::GetWndClassInfo  
 Вызывается методом [создать](#create) для доступа к данным класса окна.  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Статический экземпляр [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CWindowImpl` получает этот метод через [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) макросом, который указывает новый класс окна.  
  
 Чтобы суперкласса существующий класс окон являются производными класса из `CWindowImpl` и включить [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) макрос для переопределения `GetWndClassInfo`. Дополнительные сведения см. в разделе [CWindowImpl](../../atl/reference/cwindowimpl-class.md) Обзор.  
  
 Помимо использования `DECLARE_WND_CLASS` и `DECLARE_WND_SUPERCLASS` макросы, можно переопределить `GetWndClassInfo` с собственной реализации.  
  
##  <a name="m_pfnsuperwindowproc"></a>CWindowImpl::m_pfnSuperWindowProc  
 В зависимости от окна указывает на одну из следующих процедур окна.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Примечания  
  
|Тип окна|Процедуры окна|  
|--------------------|----------------------|  
|Окно на основании нового класса окна, указанное с помощью [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) макрос.|[DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) функции Win32.|  
|Окно на основании класс окна, который изменяет существующий класс, указанное с помощью [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) макрос.|Процедура окна существующий класс окон.|  
|Окно подклассов.|Окно подклассов исходную процедуру окна.|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc) отправляет сообщение сведения, сохраненные в процедуре окна `m_pfnSuperWindowProc`.  
  
##  <a name="onfinalmessage"></a>CWindowImpl::OnFinalMessage  
 Вызывается после получения последнего сообщения (обычно `WM_NCDESTROY`).  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор окна удаляется.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию `OnFinalMessage` не выполняет никаких действий, но можно переопределить эту функцию для обработки очистки перед удалением окна. Если вы хотите автоматически удалить объект после уничтожение окна, можно вызвать `delete this;` в этой функции.  
  
##  <a name="subclasswindow"></a>CWindowImpl::SubclassWindow  
 Подклассы окна определяется `hWnd` и присоединяет его к `CWindowImpl` объекта.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор окна подклассом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если окно подклассов успешно, в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Окно подклассов теперь использует [CWindowImpl::WindowProc](#windowproc). В исходную процедуру окна сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Не следует вызывать `SubclassWindow` Если уже был вызван [создать](#create).  
  
##  <a name="unsubclasswindow"></a>CWindowImpl::UnsubclassWindow  
 Отсоединяет подклассов в окне `CWindowImpl` объекта и восстанавливает исходную процедуру окна, сохраненные в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна ранее подкласса.  
  
##  <a name="windowproc"></a>CWindowImpl::WindowProc  
 Эта статическая функция реализует процедуру окна.  
  
```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор окна.  
  
 `uMsg`  
 [in] Сообщение отправлено в окно.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения.  
  
### <a name="remarks"></a>Примечания  
 `WindowProc`использует схему сообщений по умолчанию (объявленные с [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)) для направления сообщений для соответствующих обработчиков. При необходимости `WindowProc` вызовов [DefWindowProc](#defwindowproc) для обработки дополнительных сообщений. Если последнее сообщение не обработано, `WindowProc` делает следующее:  
  
-   Выполняет unsubclassing, если окно было unsubclassed.  
  
-   Очищает `m_hWnd`.  
  
-   Вызовы [OnFinalMessage](#onfinalmessage) перед уничтожением окна.  
  
 Можно переопределить `WindowProc` для предоставления другой механизм для обработки сообщений.  
  
## <a name="see-also"></a>См. также  
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

