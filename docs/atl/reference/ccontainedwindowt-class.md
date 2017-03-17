---
title: "Класс CContainedWindowT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e10aa4b455696fd217f88b6eb1de2421fccda6de
ms.lasthandoff: 02/24/2017

---
# <a name="ccontainedwindowt-class"></a>Класс CContainedWindowT
Этот класс реализует окно содержатся внутри другого объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>Параметры  
 *TBase*  
 Базовый класс для нового класса. По умолчанию используется базовый класс `CWindow`.  
  
 `TWinTraits`  
 Класс характеристик, определяет стили для окна. Значение по умолчанию — `CControlWinTraits`.  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) представляет собой специализацию службы `CContainedWindowT`. Если вы хотите изменить базовый класс или характеристик, используйте `CContainedWindowT` напрямую.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Конструктор. Инициализирует элементы данных, чтобы указать, какая схема сообщений будет обрабатывать содержащееся окно сообщения.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CContainedWindowT::Create](#create)|Создает окно.|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Обеспечивает обработку сообщений по умолчанию.|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Возвращает текущее сообщение.|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Регистрирует класс окна содержащееся окно.|  
|[CContainedWindowT::SubclassWindow](#subclasswindow)|Подклассы окно.|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Изменения, какая схема сообщений используется для обработки содержащееся окно сообщения.|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Восстановление ранее подклассов окна.|  
|[CContainedWindowT::WindowProc](#windowproc)|(Статический) Обрабатывает сообщения, отправляемые содержащееся окно.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Определяет, какая схема сообщений будет обрабатывать содержащееся окно сообщения.|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Задает имя существующий класс окон, на котором будет основан новый класс окна.|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Указывает исходную процедуру окна класс окна.|  
|[CContainedWindowT::m_pObject](#m_pobject)|Указывает для вмещающего объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CContainedWindowT`реализует окно, содержатся внутри другого объекта. `CContainedWindowT`в процедуры используется окно сообщения сопоставления в вмещающего прямой сообщения для соответствующих обработчиков. При создании `CContainedWindowT` объекта, укажите, какие схемы сообщений следует использовать.  
  
 `CContainedWindowT`позволяет создать новое окно существующий класс окон Создание суперклассов. **Создать** метод сначала регистрирует класс окна, который основан на существующем классе, но использует `CContainedWindowT::WindowProc`. **Создание** создает окно, в зависимости от этого нового класса. Каждый экземпляр `CContainedWindowT` можно суперкласс класса другое окно.  
  
 `CContainedWindowT`также поддерживает создать подкласс окна. `SubclassWindow` Метод присоединяет к существующему окну `CContainedWindowT` объекта и изменяет процедура окна для `CContainedWindowT::WindowProc`. Каждый экземпляр `CContainedWindowT` можно создать подкласс другое окно.  
  
> [!NOTE]
>  Для любой заданной `CContainedWindowT` , либо вызовите **создать** или `SubclassWindow`. Не следует вызвать оба метода в том же объекте.  
  
 При использовании **добавить элемент управления на основе** параметр в мастере проекта ATL, мастер автоматически добавит `CContainedWindowT` данные-член к классу, реализующему элемент управления. В следующем примере показано, как объявляется содержащееся окно:  
  
 [!code-cpp[NVC_ATL_Windowing&#38;](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing&#39;](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing&#40;](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|Дополнительные сведения о|См.|  
|--------------------------------|---------|  
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|  
|Использование окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|  
|Мастер проектов ATL|[Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) и последующих разделах[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="ccontainedwindowt"></a>CContainedWindowT::CContainedWindowT  
 Конструктор инициализирует элементы данных.  
  
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
 [in] Имя существующий класс окон, на котором будет основываться содержащееся окно.  
  
 `pObject`  
 [in] Указатель содержит объект, который объявляет схемы сообщений. Класс этого объекта должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Определяет сопоставление сообщений, которая будет обрабатывать сообщения содержащееся окно. Значение по умолчанию — 0, указывает в схеме сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554). Чтобы использовать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), передайте `msgMapID`.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите создать новое окно через [создать](#create), необходимо передать имя существующего класса окна для `lpszClassName` параметр. Например, в разделе [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) Обзор.  
  
 Существует три конструктора:  
  
-   Конструктор с тремя аргументами является обычно называется.  
  
-   Конструктор с двумя аргументами использует имя класса из **TBase::GetWndClassName**.  
  
-   Конструктор без аргументов используется в том случае, если требуется передать аргументы в более поздней версии. Необходимо указать имя класса окна, объект сообщения карты и карты идентификатор сообщения при последующем вызове **создать**.  
  
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
 [in] Имя существующий класс окон, на котором будет основываться содержащееся окно.  
  
 `pObject`  
 [in] Указатель содержит объект, который объявляет схемы сообщений. Класс этого объекта должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Определяет сопоставление сообщений, которая будет обрабатывать сообщения содержащееся окно. Значение по умолчанию — 0, указывает в схеме сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554). Чтобы использовать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), передайте `msgMapID`.  
  
 `hWndParent`  
 [in] Дескриптор окна родительского или владельца.  
  
 `rect`  
 [in] Объект [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, задающая положение окна. `RECT` Можно передать указатель или ссылка.  
  
 `szWindowName`  
 [in] Задает имя окна. Значение по умолчанию — **NULL**.  
  
 `dwStyle`  
 [in] Стиль окна. Значение по умолчанию — **WS_CHILD | WS_VISIBLE**. Список возможных значений см. в разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwExStyle`  
 [in] Стиль окна расширенного. Значение по умолчанию — 0, то есть не расширенный стиль. Список возможных значений см. в разделе [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `MenuOrID`  
 [in] Для дочернего окна код окна. Для окна верхнего уровня, дескриптор меню для окна. Значение по умолчанию — **0U**.  
  
 `lpCreateParam`  
 [in] Указатель на создание окна данных. Полное описание см. в описании для последнего параметра для [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха дескриптор вновь созданного окна. в противном случае — **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Имя существующего класса окна сохраняется в [m_lpszClassName](#m_lpszclassname). **Создание** создает окно на основе этого нового класса. Вновь созданное окно, автоматически присоединяется к `CContainedWindowT` объекта.  
  
> [!NOTE]
>  Не следует вызывать **создать** Если уже был вызван [SubclassWindow](#subclasswindow).  
  
> [!NOTE]
>  Если 0 служит значением для `MenuOrID` параметр, он должен быть указан как 0U (значение по умолчанию), чтобы избежать ошибки компилятора.  
  
##  <a name="defwindowproc"></a>CContainedWindowT::DefWindowProc  
 Вызывается методом [WindowProc](#windowproc) для обработки сообщений, не обрабатываются в схеме сообщений.  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
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
  
##  <a name="getcurrentmessage"></a>CContainedWindowT::GetCurrentMessage  
 Возвращает текущее сообщение ( **m_pCurrentMsg**).  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее сообщение, упакованные в `MSG` структуру.  
  
##  <a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID  
 Содержит идентификатор схемы сообщений, используемые для автономной окна.  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>Примечания  
 На этой карте сообщения должен быть объявлен в вмещающего объекта.  
  
 Схемы сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554), всегда определяется на ноль. Альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), определяется `msgMapID`.  
  
 `m_dwMsgMapID`сначала инициализируются конструктором и может быть изменено путем вызова [SwitchMessageMap](#switchmessagemap). Например, в разделе [CContainedWindowT Обзор](../../atl/reference/ccontainedwindowt-class.md).  
  
##  <a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName  
 Указывает имя существующего класса окна.  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>Примечания  
 При создании окна [создать](#create) регистрирует класс окна, основан на существующий класс, но использует [CContainedWindowT::WindowProc](#windowproc).  
  
 `m_lpszClassName`инициализируется в конструкторе. Например, в разделе [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) Обзор.  
  
##  <a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc  
 Если содержащееся окно является подклассом, `m_pfnSuperWindowProc` Указывает исходную процедуру окна класса окна.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Примечания  
 Если окно автономной суперкласса, то есть он основан на класс окна, который изменяет существующий класс, `m_pfnSuperWindowProc` указывает на существующий класс окон процедуру окна.  
  
 [DefWindowProc](#defwindowproc) метод отправляет сведения сообщение процедуре окна, сохраненные в `m_pfnSuperWindowProc`.  
  
##  <a name="m_pobject"></a>CContainedWindowT::m_pObject  
 Указывает объект, содержащий `CContainedWindowT` объекта.  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>Примечания  
 Этот контейнер, класс которого должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md), объявляет схемы сообщений, используемые в окне автономной.  
  
 `m_pObject`инициализируется в конструкторе. Например, в разделе [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) Обзор.  
  
##  <a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass  
 Вызывается методом [создать](#create) зарегистрировать класс окна содержащееся окно.  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха atom, однозначно идентифицирующий класс окна регистрируется; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Этот класс окна основан на существующем классе, но использует [CContainedWindowT::WindowProc](#windowproc). Существующий класс окон имя и процедуры окна сохраняются в [m_lpszClassName](#m_lpszclassname) и [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)соответственно.  
  
##  <a name="subclasswindow"></a>CContainedWindowT::SubclassWindow  
 Подклассы окна определяется `hWnd` и присоединяет его к `CContainedWindowT` объекта.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор окна подклассом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если окно подклассов успешно, в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Окно подклассов теперь использует [CContainedWindowT::WindowProc](#windowproc). В исходную процедуру окна сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Не следует вызывать `SubclassWindow` Если уже был вызван [создать](#create).  
  
##  <a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap  
 Изменения, какая схема сообщений будет использоваться для обработки содержащееся окно сообщений.  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwMsgMapID`  
 [in] Идентификатор сопоставления сообщений. Для использования в схеме сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554), передать нулевое значение. Чтобы использовать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), передайте `msgMapID`.  
  
### <a name="remarks"></a>Примечания  
 Сопоставление сообщений должен быть определен в вмещающего объекта.  
  
 Идентификатор сообщения карта изначально задать в конструкторе.  
  
##  <a name="unsubclasswindow"></a>CContainedWindowT::UnsubclassWindow  
 Отсоединяет подклассов в окне `CContainedWindowT` объекта и восстанавливает исходную процедуру окна, сохраненные в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bForce`  
 [in] Значение **TRUE** для принудительного исходную процедуру окна для восстановления даже в том случае, если эта процедура окна `CContainedWindowT` объект не является активным в данный момент. Если `bForce` равен **FALSE** и эта процедура окна `CContainedWindowT` объект не является активным в данный момент, не будут восстановлены в исходную процедуру окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна ранее подкласса. Если `bForce` равен **FALSE** и эта процедура окна `CContainedWindowT` объект не является активной, возвращает **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только в том случае, если вы хотите восстановить исходную процедуру окна до уничтожения окна. В противном случае — [WindowProc](#windowproc) автоматически происходит при уничтожении окна.  
  
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
 [in] Сообщение отправлено в окно.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения.  
  
### <a name="remarks"></a>Примечания  
 `WindowProc`направляет сообщения к схеме сообщений, идентифицируемый [m_dwMsgMapID](#m_dwmsgmapid). При необходимости `WindowProc` вызовов [DefWindowProc](#defwindowproc) для обработки дополнительных сообщений.  
  
## <a name="see-also"></a>См. также  
 [Класс CWindow](../../atl/reference/cwindow-class.md)   
 [Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)   
 [Класс CMessageMap](../../atl/reference/cmessagemap-class.md)   
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [ALT_MSG_MAP](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

