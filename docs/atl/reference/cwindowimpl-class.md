---
title: "Класс CWindowImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3aa14c3ae6c083cbf440d8b5b94fcb3754bd6fff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cwindowimpl-class"></a>Класс CWindowImpl
Предоставляет методы для создания или создание подкласса для окна.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```    
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Новый класс, производный от `CWindowImpl`.  
  
 *TBase*  
 Базовый класс для класса. По умолчанию является базовым классом [CWindow](../../atl/reference/cwindow-class.md).  
  
 `TWinTraits`  
 Объект [класс характеристик](../../atl/understanding-window-traits.md) , определяющий стили для окна. Значение по умолчанию — `CControlWinTraits`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
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
|[GetWndClassInfo](#getwndclassinfo)|Возвращает статический экземпляр [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md), который управляет сведениями о классе окна.|  
|[WindowProc](#windowproc)|Обрабатывает сообщения, отправленные в окно.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Указывает класс окна исходной процедуры окна.|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `CWindowImpl` для создания окна или подкласс существующему окну. `CWindowImpl` процедуру окна использует схемы сообщений для направления сообщений для соответствующих обработчиков.  
  
 `CWindowImpl::Create`Создает окно на основе сведений класса окна, под управлением [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl`содержит [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) макросом, который означает `CWndClassInfo` регистрирует новый класс окна. Если вы хотите суперкласса существующего класса окна, получении класса из `CWindowImpl` и включать [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос. В этом случае `CWndClassInfo` регистрирует класс окна, который основан на существующем классе, но использует `CWindowImpl::WindowProc`. Пример:  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  Поскольку `CWndClassInfo` управляет данными только один класс окна каждого окна, созданные с помощью экземпляра `CWindowImpl` основан на один класс.  
  
 `CWindowImpl`также поддерживает создания подкласса окна. `SubclassWindow` Метод прикрепляет к существующему окну `CWindowImpl` объекта и изменяет процедура окна для `CWindowImpl::WindowProc`. Каждый экземпляр `CWindowImpl` можно подкласс другого окна.  
  
> [!NOTE]
>  Для любой заданной `CWindowImpl` , либо вызовите **создать** или `SubclassWindow`. Не вызывать оба метода того же объекта.  
  
 В дополнение к `CWindowImpl`, библиотека ATL предоставляет [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) для создания окна, содержащийся в другом объекте.  
  
 Деструктор базового класса (~ **CWindowImplRoot**) гарантирует, что окно удалены до уничтожения объекта.  
  
 `CWindowImpl`является производным от **CWindowImplBaseT**, который является производным от **CWindowImplRoot**, который является производным от **TBase** и [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
|Дополнительные сведения о|См.|  
|--------------------------------|---------|  
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|  
|Использование окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|  
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="create"></a>CWindowImpl::Create  
 Создает окно на основе нового класса окна.  
  
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
 [in] Объект [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, которые задают позицию окна. `RECT` Можно передать указатель или по ссылке.  
  
 `szWindowName`  
 [in] Задает имя окна. Значение по умолчанию — **NULL**.  
  
 `dwStyle`  
 [in] Стиль окна. Это значение объединяется с использованием стиля, предоставляемый классом признаки для окна. Значение по умолчанию предоставляет признаки класса полный контроль над стиль. Список возможных значений см. в разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в Windows SDK.  
  
 `dwExStyle`  
 [in] Стиль окна расширенного. Это значение объединяется с использованием стиля, предоставляемый классом признаки для окна. Значение по умолчанию предоставляет признаки класса полный контроль над стиль. Список возможных значений см. в разделе [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в Windows SDK.  
  
 `MenuOrID`  
 [in] Для дочернего окна идентификатор окна. Для окна верхнего уровня, дескриптор меню для окна. Значение по умолчанию — **0U**.  
  
 `lpCreateParam`  
 [in] Указатель на окно создания данных. Полное описание см. в описании последний параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения дескриптор для созданного окна. В противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 **Создание** сначала регистрирует класс окна, если он не был зарегистрирован. Вновь созданный окно автоматически присоединяется к `CWindowImpl` объекта.  
  
> [!NOTE]
>  Не вызывайте **создать** Если уже был вызван [SubclassWindow](#subclasswindow).  
  
 Чтобы использовать класс окна, который основан на существующий класс окна, получении класса из `CWindowImpl` и включать [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос. Оконная функция существующий класс окна сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc). Дополнительные сведения см. в разделе [CWindowImpl](../../atl/reference/cwindowimpl-class.md) Обзор.  
  
> [!NOTE]
>  Если используется значение 0 как значение для `MenuOrID` параметра, он должен быть указан как 0U (значение по умолчанию) для предотвращения ошибок компилятора.  
  
##  <a name="defwindowproc"></a>CWindowImpl::DefWindowProc  
 Вызывается методом [WindowProc](#windowproc) для обработки сообщений, не обработанные в схеме сообщений.  
  
```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```  
  
### <a name="parameters"></a>Параметры  
 `uMsg`  
 [in] Сообщение, отправленное окну.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `DefWindowProc` вызовы [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) функцию Win32 для отправки сведений сообщение процедуре окна, указанный в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
 Функция без параметров автоматически извлекает необходимые параметры из текущего сообщения.  
  
##  <a name="getcurrentmessage"></a>CWindowImpl::GetCurrentMessage  
 Возвращает текущее сообщение, упакованные в `MSG` структуры.  
  
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
 Переопределите этот метод для замены вашу процедуру окна.  
  
##  <a name="getwndclassinfo"></a>CWindowImpl::GetWndClassInfo  
 Вызывается методом [создать](#create) доступ к сведениям класс окна.  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Статический экземпляр [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CWindowImpl` через этот метод получает [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) макросом, который указывает новый класс окна.  
  
 Чтобы суперкласса существующего класса окна, получении класса из `CWindowImpl` и включать [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос для переопределения `GetWndClassInfo`. Дополнительные сведения см. в разделе [CWindowImpl](../../atl/reference/cwindowimpl-class.md) Обзор.  
  
 Помимо использования `DECLARE_WND_CLASS` и `DECLARE_WND_SUPERCLASS` макросов, можно переопределить `GetWndClassInfo` собственной реализацией.  
  
##  <a name="m_pfnsuperwindowproc"></a>CWindowImpl::m_pfnSuperWindowProc  
 В зависимости от окна указывает на одну из следующих процедур окна.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Примечания  
  
|Тип окна|Процедуры окна|  
|--------------------|----------------------|  
|Окна на основании нового класса окна, указанное с помощью [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) макрос.|[DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) функции Win32.|  
|Окна, основанного на классе окна, изменяющего существующего класса, указанное с помощью [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос.|Процедуру окна существующий класс окна.|  
|Окно подклассов.|Окно подклассов исходной процедуры окна.|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc) отправляет сообщение сведения, сохраненные в процедуре окна `m_pfnSuperWindowProc`.  
  
##  <a name="onfinalmessage"></a>CWindowImpl::OnFinalMessage  
 Вызывается после получения последнего сообщения (обычно `WM_NCDESTROY`).  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор окна уничтожении.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию `OnFinalMessage` не выполняет никаких действий, однако его можно переопределить эту функцию для обработки очистки, перед удалением окна. Если вы хотите автоматически удалить объект после уничтожения окна, можно вызвать `delete this;` в этой функции.  
  
##  <a name="subclasswindow"></a>CWindowImpl::SubclassWindow  
 Подклассы окна, обозначенную `hWnd` и прикрепляет его к `CWindowImpl` объекта.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор окна подкласса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** является ли окно подклассов успешно, в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Окно подклассов теперь использует [CWindowImpl::WindowProc](#windowproc). Исходной процедуры окна сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Не вызывайте `SubclassWindow` Если уже был вызван [создать](#create).  
  
##  <a name="unsubclasswindow"></a>CWindowImpl::UnsubclassWindow  
 Отсоединяет окно подклассов `CWindowImpl` объекта и восстанавливает исходную процедуру окна, сохраненные в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
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
 [in] Сообщение, отправленное окну.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения.  
  
### <a name="remarks"></a>Примечания  
 `WindowProc`использует схему сообщений по умолчанию (объявлено с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)) для направления сообщений для соответствующих обработчиков. При необходимости `WindowProc` вызовы [DefWindowProc](#defwindowproc) для обработки дополнительных сообщений. Если сообщение последним не обрабатывается, `WindowProc` делает следующее:  
  
-   Выполняет unsubclassing, если окно было unsubclassed.  
  
-   Очищает `m_hWnd`.  
  
-   Вызовы [OnFinalMessage](#onfinalmessage) до уничтожения окна.  
  
 Можно переопределить `WindowProc` для предоставления разных механизма для обработки сообщений.  
  
## <a name="see-also"></a>См. также  
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
