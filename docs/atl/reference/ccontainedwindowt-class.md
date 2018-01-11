---
title: "Класс CContainedWindowT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
dev_langs: C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cf792fed2f7a5cac45826649224a565228f9d73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccontainedwindowt-class"></a>Класс CContainedWindowT
Этот класс реализует окно, содержатся внутри другого объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>Параметры  
 *TBase*  
 Базовый класс к новому классу. Базовый класс по умолчанию — `CWindow`.  
  
 `TWinTraits`  
 Класс характеристик, определяющий стили для окна. Значение по умолчанию — `CControlWinTraits`.  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) является специализацией `CContainedWindowT`. Если вы хотите изменить базовый класс или признаки, используйте `CContainedWindowT` напрямую.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Конструктор. Инициализирует элементы данных, чтобы указать, какой карты сообщение будет обрабатывать содержащееся окно сообщения.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CContainedWindowT::Create](#create)|Создает окно.|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Обеспечивает обработку сообщений по умолчанию.|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Возвращает текущее сообщение.|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Регистрирует класс окна содержащееся окно.|  
|[CContainedWindowT::SubclassWindow](#subclasswindow)|Подклассы окно.|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Изменения, какие схемы сообщений используется для обработки сообщений автономной окна.|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Восстановление ранее подклассов окна.|  
|[CContainedWindowT::WindowProc](#windowproc)|(Статический) Обрабатывает сообщения, отправленные в окно автономной.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Определяет, какие схемы сообщений будет обрабатывать содержащееся окно сообщения.|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Указывает имя существующего класса окна, на котором будет основан новый класс окна.|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Указывает класс окна исходной процедуры окна.|  
|[CContainedWindowT::m_pObject](#m_pobject)|Указывает для вмещающего объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CContainedWindowT`реализует окно, содержатся внутри другого объекта. `CContainedWindowT`в окне процедуры используется сопоставляют сообщения для вмещающего объекта для прямого соответствующих обработчиков сообщений. При создании `CContainedWindowT` объекта, укажите, какие схему сообщений следует использовать.  
  
 `CContainedWindowT`можно создать новое окно, создание суперклассов существующего класса окна. **Создать** метод сначала регистрирует класс окна, который основан на существующем классе, но использует `CContainedWindowT::WindowProc`. **Создание** создает окно с учетом этого нового класса. Каждый экземпляр `CContainedWindowT` можно суперкласса класс другое окно.  
  
 `CContainedWindowT`также поддерживает создания подкласса окна. `SubclassWindow` Метод прикрепляет к существующему окну `CContainedWindowT` объекта и изменяет процедура окна для `CContainedWindowT::WindowProc`. Каждый экземпляр `CContainedWindowT` можно подкласс другого окна.  
  
> [!NOTE]
>  Для любой заданной `CContainedWindowT` , либо вызовите **создать** или `SubclassWindow`. Не должен вызывать оба метода того же объекта.  
  
 При использовании **добавить элемент управления на основе** параметр в мастер проектов ATL, мастер автоматически добавит `CContainedWindowT` данные-члены класса, который реализует элемент управления. В следующем примере показано, как окно автономной объявлен:  
  
 [!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|Дополнительные сведения о|См.|  
|--------------------------------|---------|  
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|  
|Использование окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|  
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) и последующие разделы в Windows SDK|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="ccontainedwindowt"></a>CContainedWindowT::CContainedWindowT  
 Конструктор инициализирует члены данных.  
  
```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```     
  
### <a name="parameters"></a>Параметры  
 `lpszClassName`  
 [in] Имя существующего класса окна, на котором будет основываться содержащееся окно.  
  
 `pObject`  
 [in] Указатель вмещающего объекта, который объявляет сопоставление сообщений. Этот объект класса должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Определяет схему сообщений, которая будет обрабатывать содержащееся окно сообщения. Значение по умолчанию — 0, указывает сопоставление сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Чтобы использовать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), передайте `msgMapID`.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите создать новое окно через [создать](#create), необходимо передать имя существующего класса окна для `lpszClassName` параметра. Пример см. в разделе [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) Обзор.  
  
 Существует три конструктора:  
  
-   Конструктор с тремя аргументами не тем, который обычно называется.  
  
-   Конструктор с двумя аргументами использует имя класса из **TBase::GetWndClassName**.  
  
-   Конструктор без аргументов используется в том случае, если требуется передать аргументы в более поздней версии. Необходимо указать имя класса окна, объект карты сообщений и карты идентификатор сообщения, при последующем вызове **создать**.  
  
 Если подкласс существующему окну через [SubclassWindow](#subclasswindow), `lpszClassName` значение не используется; таким образом, можно передать **NULL** для этого параметра.  
  
##  <a name="create"></a>CContainedWindowT::Create  
 Вызовы [RegisterWndSuperclass](#registerwndsuperclass) зарегистрировать класс окна, который основан на существующем классе, но использует [CContainedWindowT::WindowProc](#windowproc).  
  
```
HWND Create(  
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszClassName`  
 [in] Имя существующего класса окна, на котором будет основываться содержащееся окно.  
  
 `pObject`  
 [in] Указатель вмещающего объекта, который объявляет сопоставление сообщений. Этот объект класса должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Определяет схему сообщений, которая будет обрабатывать содержащееся окно сообщения. Значение по умолчанию — 0, указывает сопоставление сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Чтобы использовать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), передайте `msgMapID`.  
  
 `hWndParent`  
 [in] Дескриптор окна родительского или владельца.  
  
 `rect`  
 [in] Объект [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, которые задают позицию окна. `RECT` Можно передать указатель или по ссылке.  
  
 `szWindowName`  
 [in] Задает имя окна. Значение по умолчанию — **NULL**.  
  
 `dwStyle`  
 [in] Стиль окна. Значение по умолчанию — **WS_CHILD &#124; WS_VISIBLE**. Список возможных значений см. в разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в Windows SDK.  
  
 `dwExStyle`  
 [in] Стиль окна расширенного. Значение по умолчанию — 0, то есть не расширенный стиль. Список возможных значений см. в разделе [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в Windows SDK.  
  
 `MenuOrID`  
 [in] Для дочернего окна идентификатор окна. Для окна верхнего уровня, дескриптор меню для окна. Значение по умолчанию — **0U**.  
  
 `lpCreateParam`  
 [in] Указатель на окно создания данных. Полное описание см. в описании последний параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения дескриптор для созданного окна. в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Имя существующего класса окна сохраняется в [m_lpszClassName](#m_lpszclassname). **Создание** создает окно на основе этого нового класса. Вновь созданный окно автоматически присоединяется к `CContainedWindowT` объекта.  
  
> [!NOTE]
>  Не вызывайте **создать** Если уже был вызван [SubclassWindow](#subclasswindow).  
  
> [!NOTE]
>  Если используется значение 0 как значение для `MenuOrID` параметра, он должен быть указан как 0U (значение по умолчанию) для предотвращения ошибок компилятора.  
  
##  <a name="defwindowproc"></a>CContainedWindowT::DefWindowProc  
 Вызывается методом [WindowProc](#windowproc) для обработки сообщений, не обработанные в схеме сообщений.  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
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
  
##  <a name="getcurrentmessage"></a>CContainedWindowT::GetCurrentMessage  
 Возвращает текущее сообщение ( **m_pCurrentMsg**).  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее сообщение, упакованные в `MSG` структуры.  
  
##  <a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID  
 Содержит идентификатор схемы сообщений, используемые для автономной окна.  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>Примечания  
 На этой карте сообщения должен быть объявлен в вмещающего объекта.  
  
 Сопоставление сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), всегда определяется на ноль. Альтернативную схему сообщений, объявленных с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), определяется `msgMapID`.  
  
 `m_dwMsgMapID`Сначала инициализирован конструктором и может быть изменено путем вызова [SwitchMessageMap](#switchmessagemap). Пример см. в разделе [CContainedWindowT Обзор](../../atl/reference/ccontainedwindowt-class.md).  
  
##  <a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName  
 Указывает имя существующего класса окна.  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>Примечания  
 При создании окна [создать](#create) регистрирует класс окна, основан на существующий класс, но использует [CContainedWindowT::WindowProc](#windowproc).  
  
 `m_lpszClassName`инициализируется в конструкторе. Пример см. в разделе [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) Обзор.  
  
##  <a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc  
 Если содержащееся окно является подклассом, `m_pfnSuperWindowProc` указывает на исходную процедуру окна класса окна.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Примечания  
 Если содержащееся окно суперкласса, что означает, что создается на основе класса окна, изменяющего существующий класс, `m_pfnSuperWindowProc` указывает на существующий класс окна процедуру окна.  
  
 [DefWindowProc](#defwindowproc) метод отправляет сведения сообщение процедуре окна, сохраненные в `m_pfnSuperWindowProc`.  
  
##  <a name="m_pobject"></a>CContainedWindowT::m_pObject  
 Указывает на объект, содержащий `CContainedWindowT` объекта.  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>Примечания  
 Этот контейнер, класс которого должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md), объявляет схему сообщений, используемые в окне автономной.  
  
 `m_pObject`инициализируется в конструкторе. Пример см. в разделе [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) Обзор.  
  
##  <a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass  
 Вызывается методом [создать](#create) зарегистрировать класс окна содержащееся окно.  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения atom, однозначно идентифицирующий класс окна регистрации; в противном случае возвращается ноль.  
  
### <a name="remarks"></a>Примечания  
 Этот класс окна основана на существующий класс, но использует [CContainedWindowT::WindowProc](#windowproc). Имя и окно процедуры существующий класс окна сохраняются в [m_lpszClassName](#m_lpszclassname) и [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)соответственно.  
  
##  <a name="subclasswindow"></a>CContainedWindowT::SubclassWindow  
 Подклассы окна, обозначенную `hWnd` и прикрепляет его к `CContainedWindowT` объекта.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор окна подкласса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** является ли окно подклассов успешно, в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Окно подклассов теперь использует [CContainedWindowT::WindowProc](#windowproc). Исходной процедуры окна сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Не вызывайте `SubclassWindow` Если уже был вызван [создать](#create).  
  
##  <a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap  
 Изменения, какие схемы сообщений будет использоваться для обработки сообщений содержащееся окно.  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwMsgMapID`  
 [in] Идентификатор сопоставления сообщения. Для использования в схеме сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), передать нулевое значение. Чтобы использовать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), передайте `msgMapID`.  
  
### <a name="remarks"></a>Примечания  
 Сопоставление сообщений должны быть определены в вмещающего объекта.  
  
 Сначала укажите идентификатор сообщения карты в конструкторе.  
  
##  <a name="unsubclasswindow"></a>CContainedWindowT::UnsubclassWindow  
 Отсоединяет окно подклассов `CContainedWindowT` объекта и восстанавливает исходную процедуру окна, сохраненные в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bForce`  
 [in] Значение **TRUE** для принудительного исходной процедуры окна для восстановления даже в том случае, если эта процедура окна `CContainedWindowT` объект не является активным. Если `bForce` равно **FALSE** и эта процедура окна `CContainedWindowT` объект не является активным, исходной процедуры окна не будут восстановлены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна ранее подкласса. Если `bForce` равно **FALSE** и эта процедура окна `CContainedWindowT` объект не является активным, возвращается **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только в том случае, если вы хотите восстановить исходную процедуру окна до уничтожения окна. В противном случае [WindowProc](#windowproc) автоматически происходит при уничтожении окна.  
  
##  <a name="windowproc"></a>CContainedWindowT::WindowProc  
 Этот статический метод реализует процедуру окна.  
  
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
 `WindowProc`направляет сообщения в схему сообщений, определяется [m_dwMsgMapID](#m_dwmsgmapid). При необходимости `WindowProc` вызовы [DefWindowProc](#defwindowproc) для обработки дополнительных сообщений.  
  
## <a name="see-also"></a>См. также  
 [Класс CWindow](../../atl/reference/cwindow-class.md)   
 [Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)   
 [Класс CMessageMap](../../atl/reference/cmessagemap-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
