---
title: Класс CPaneFrameWnd | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd::AddPane
- AFXPANEFRAMEWND/CPaneFrameWnd::AddRemovePaneFromGlobalList
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustPaneFrames
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcBorderSize
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcExpectedDockedRect
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeAttached
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeDockedToPane
- AFXPANEFRAMEWND/CPaneFrameWnd::CheckGripperVisibility
- AFXPANEFRAMEWND/CPaneFrameWnd::ConvertToTabbedDocument
- AFXPANEFRAMEWND/CPaneFrameWnd::Create
- AFXPANEFRAMEWND/CPaneFrameWnd::CreateEx
- AFXPANEFRAMEWND/CPaneFrameWnd::DockPane
- AFXPANEFRAMEWND/CPaneFrameWnd::FindFloatingPaneByID
- AFXPANEFRAMEWND/CPaneFrameWnd::FrameFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionHeight
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionText
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingMode
- AFXPANEFRAMEWND/CPaneFrameWnd::GetFirstVisiblePane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::GetParent
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPinState
- AFXPANEFRAMEWND/CPaneFrameWnd::GetRecentFloatingRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetVisiblePaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::HitTest
- AFXPANEFRAMEWND/CPaneFrameWnd::IsCaptured
- AFXPANEFRAMEWND/CPaneFrameWnd::IsDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollDown
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollUp
- AFXPANEFRAMEWND/CPaneFrameWnd::KillDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::LoadState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnBeforeDock
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDockToRecentPos
- AFXPANEFRAMEWND/CPaneFrameWnd::OnKillRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnMovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::OnPaneRecalcLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::OnSetRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnShowPane
- AFXPANEFRAMEWND/CPaneFrameWnd::PaneFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::Pin
- AFXPANEFRAMEWND/CPaneFrameWnd::RedrawAll
- AFXPANEFRAMEWND/CPaneFrameWnd::RemoveNonValidPanes
- AFXPANEFRAMEWND/CPaneFrameWnd::RemovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::ReplacePane
- AFXPANEFRAMEWND/CPaneFrameWnd::SaveState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetCaptionButtons
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::SetPreDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SizeToContent
- AFXPANEFRAMEWND/CPaneFrameWnd::StartTearOff
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentDockSiteInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentTabRelatedInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::OnCheckRollState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDrawBorder
- AFXPANEFRAMEWND/CPaneFrameWnd::m_bUseSaveBits
dev_langs:
- C++
helpviewer_keywords:
- CPaneFrameWnd [MFC], AddPane
- CPaneFrameWnd [MFC], AddRemovePaneFromGlobalList
- CPaneFrameWnd [MFC], AdjustLayout
- CPaneFrameWnd [MFC], AdjustPaneFrames
- CPaneFrameWnd [MFC], CalcBorderSize
- CPaneFrameWnd [MFC], CalcExpectedDockedRect
- CPaneFrameWnd [MFC], CanBeAttached
- CPaneFrameWnd [MFC], CanBeDockedToPane
- CPaneFrameWnd [MFC], CheckGripperVisibility
- CPaneFrameWnd [MFC], ConvertToTabbedDocument
- CPaneFrameWnd [MFC], Create
- CPaneFrameWnd [MFC], CreateEx
- CPaneFrameWnd [MFC], DockPane
- CPaneFrameWnd [MFC], FindFloatingPaneByID
- CPaneFrameWnd [MFC], FrameFromPoint
- CPaneFrameWnd [MFC], GetCaptionHeight
- CPaneFrameWnd [MFC], GetCaptionRect
- CPaneFrameWnd [MFC], GetCaptionText
- CPaneFrameWnd [MFC], GetDockingManager
- CPaneFrameWnd [MFC], GetDockingMode
- CPaneFrameWnd [MFC], GetFirstVisiblePane
- CPaneFrameWnd [MFC], GetHotPoint
- CPaneFrameWnd [MFC], GetPane
- CPaneFrameWnd [MFC], GetPaneCount
- CPaneFrameWnd [MFC], GetParent
- CPaneFrameWnd [MFC], GetPinState
- CPaneFrameWnd [MFC], GetRecentFloatingRect
- CPaneFrameWnd [MFC], GetVisiblePaneCount
- CPaneFrameWnd [MFC], HitTest
- CPaneFrameWnd [MFC], IsCaptured
- CPaneFrameWnd [MFC], IsDelayShow
- CPaneFrameWnd [MFC], IsRollDown
- CPaneFrameWnd [MFC], IsRollUp
- CPaneFrameWnd [MFC], KillDockingTimer
- CPaneFrameWnd [MFC], LoadState
- CPaneFrameWnd [MFC], OnBeforeDock
- CPaneFrameWnd [MFC], OnDockToRecentPos
- CPaneFrameWnd [MFC], OnKillRollUpTimer
- CPaneFrameWnd [MFC], OnMovePane
- CPaneFrameWnd [MFC], OnPaneRecalcLayout
- CPaneFrameWnd [MFC], OnSetRollUpTimer
- CPaneFrameWnd [MFC], OnShowPane
- CPaneFrameWnd [MFC], PaneFromPoint
- CPaneFrameWnd [MFC], Pin
- CPaneFrameWnd [MFC], RedrawAll
- CPaneFrameWnd [MFC], RemoveNonValidPanes
- CPaneFrameWnd [MFC], RemovePane
- CPaneFrameWnd [MFC], ReplacePane
- CPaneFrameWnd [MFC], SaveState
- CPaneFrameWnd [MFC], SetCaptionButtons
- CPaneFrameWnd [MFC], SetDelayShow
- CPaneFrameWnd [MFC], SetDockingManager
- CPaneFrameWnd [MFC], SetDockingTimer
- CPaneFrameWnd [MFC], SetDockState
- CPaneFrameWnd [MFC], SetHotPoint
- CPaneFrameWnd [MFC], SetPreDockState
- CPaneFrameWnd [MFC], SizeToContent
- CPaneFrameWnd [MFC], StartTearOff
- CPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
- CPaneFrameWnd [MFC], OnCheckRollState
- CPaneFrameWnd [MFC], OnDrawBorder
- CPaneFrameWnd [MFC], m_bUseSaveBits
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6846f50b0e89193992a42ea50e785009f31e6d19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378791"
---
# <a name="cpaneframewnd-class"></a>Класс CPaneFrameWnd
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Реализует окно минифрейма, которое содержит одну область. Область заполняет собой клиентскую область окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPaneFrameWnd::AddPane](#addpane)|Добавляет панель.|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|Добавляет панель в глобальный список или удаляет из него.|  
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|Настраивает макет окна области.|  
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||  
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|Вычисляет размер границ окна области.|  
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|Вычисляет ожидаемый прямоугольник закрепленного окна.|  
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|Определяет, может ли текущая панель быть закреплена на другой панели или окне фрейма.|  
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|Определяет, может ли окно области быть закреплено на панели.|  
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|Преобразует панель в документ с вкладками.|  
|[CPaneFrameWnd::Create](#create)|Создает окно области и прикрепляет его к объекту `CPaneFrameWnd`.|  
|[CPaneFrameWnd::CreateEx](#createex)|Создает окно области и прикрепляет его к объекту `CPaneFrameWnd`.|  
|[CPaneFrameWnd::DockPane](#dockpane)|Закрепляет область.|  
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|Находит в глобальном списке плавающих панелей панель с указанным идентификатором элемента управления.|  
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|Находит окно области, содержащее предоставленную пользователем точку.|  
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|Возвращает высоту заголовка окна области.|  
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|Вычисляет ограничивающий прямоугольник заголовка окна области.|  
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|Возвращает текст заголовка.|  
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||  
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|Возвращает режим закрепления.|  
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|Возвращает первую видимую панель, содержащуюся в окне области.|  
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||  
|[CPaneFrameWnd::GetPane](#getpane)|Возвращает панель, содержащуюся в окне области.|  
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|Возвращает число панелей, содержащихся в окне области.|  
|[CPaneFrameWnd::GetParent](#getparent)||  
|[CPaneFrameWnd::GetPinState](#getpinstate)||  
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||  
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|Возвращает число видимых панелей, содержащихся в окне области.|  
|[CPaneFrameWnd::HitTest](#hittest)|Определяет, какая часть окна области находится в заданной точке.|  
|[CPaneFrameWnd::IsCaptured](#iscaptured)||  
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||  
|[CPaneFrameWnd::IsRollDown](#isrolldown)|Определяет, требуется ли развертывание окна области.|  
|[CPaneFrameWnd::IsRollUp](#isrollup)|Определяет, требуется ли свертывание окна области.|  
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|Останавливает таймер закрепления.|  
|[CPaneFrameWnd::LoadState](#loadstate)|Загружает состояние панели из реестра.|  
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|Определяет возможность закрепления.|  
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|Закрепляет окно области в его последней позиции.|  
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|Останавливает таймер свертки.|  
|[CPaneFrameWnd::OnMovePane](#onmovepane)|Смещает окно области на указанное расстояние.|  
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|Настраивает макет содержащейся панели.|  
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|Устанавливает таймер свертки.|  
|[CPaneFrameWnd::OnShowPane](#onshowpane)|Вызывается платформой при скрытии или отображении панели в окне области.|  
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|Возвращает панель, если она содержит предоставленную пользователем точку в пределах окна области.|  
|[CPaneFrameWnd::Pin](#pin)||  
|`CPaneFrameWnd::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их передачей функциям Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .|  
|[CPaneFrameWnd::RedrawAll](#redrawall)|Перерисовывает все окна областей.|  
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|Вызывается платформой для удаления недопустимых панелей.|  
|[CPaneFrameWnd::RemovePane](#removepane)|Удаляет панель из окна области.|  
|[CPaneFrameWnd::ReplacePane](#replacepane)|Заменяет одну панель другой.|  
|[CPaneFrameWnd::SaveState](#savestate)|Сохраняет состояние панели в реестр.|  
|`CPaneFrameWnd::Serialize`|Считывает этот объект из архива или записывает в него.|  
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|Задает кнопки заголовка.|  
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||  
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||  
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|Устанавливает таймер закрепления.|  
|[CPaneFrameWnd::SetDockState](#setdockstate)|Задает состояние закрепления.|  
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||  
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|Вызывается платформой для задания предварительного состояния закрепления.|  
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|Делает размер окна области равным размеру содержащейся в нем панели.|  
|[CPaneFrameWnd::StartTearOff](#starttearoff)|Делает меню перемещаемым.|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|Определяет, требуется ли свертывание или развертывание окна области.|  
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|Рисует границы окна области.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание|  
|----------|-----------------|  
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|Указывает, требуется ли регистрация класса окна со стилем класса `CS_SAVEBITS`.|  
  
## <a name="remarks"></a>Примечания  
 Когда панель переходит из закрепленного состояния в плавающее, платформа автоматически создает объект `CPaneFrameWnd`.  
  
 Окно области можно перетащить вместе с его видимым содержимым (немедленное закрепление) или с помощью прямоугольника перетаскивания (стандартное закрепление). Режим закрепления панели контейнера окна области определяет поведение окна области при перетаскивании. Дополнительные сведения см. в разделе [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
 В заголовке окна области отображаются кнопки, зависящие от стиля включенной панели. Если область может быть закрыт ( [CBasePane::CanBeClosed](../../mfc/reference/cbasepane-class.md#canbeclosed)), он отображается кнопка закрытия. Если для панели используется стиль `AFX_CBRS_AUTO_ROLLUP`, отображается кнопка закрепления.  
  
 Если вы получаете производный класс из класса `CPaneFrameWnd`, необходимо сообщить платформе способ его создания. Создать класс, переопределив [CPane::CreateDefaultMiniframe](../../mfc/reference/cpane-class.md#createdefaultminiframe), или задать `CPane::m_pMiniFrameRTC` члену, так чтобы он указывал на сведения о классе среды выполнения для класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPaneFrameWnd`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxPaneFrameWnd.h  
  
##  <a name="addpane"></a>  CPaneFrameWnd::AddPane  
 Добавляет панель.  
  
```  
virtual void AddPane(CBasePane* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 На панели, чтобы добавить.  
  
##  <a name="addremovepanefromgloballist"></a>  CPaneFrameWnd::AddRemovePaneFromGlobalList  
 Добавляет панель в глобальный список или удаляет из него.  
  
```  
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,  
    BOOL bAdd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 На панели, чтобы добавить или удалить.  
  
 [in] `bAdd`  
 Если ненулевое значение, добавления области. Если значение равно 0, удалите область.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
##  <a name="adjustlayout"></a>  CPaneFrameWnd::AdjustLayout  
 Настраивает макет окна области.  
  
```  
virtual void AdjustLayout();
```  
  
##  <a name="adjustpaneframes"></a>  CPaneFrameWnd::AdjustPaneFrames  

  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="calcbordersize"></a>  CPaneFrameWnd::CalcBorderSize  
 Вычисляет размер границ для плавающего окна.  
  
```  
virtual void CalcBorderSize(CRect& rectBorderSize) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectBorderSize`  
 Содержит размер в пикселях границы плавающего окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, чтобы вычислить размер границы плавающего окна. Возвращаемый размер зависит от ли имеет плавающего окна инструментов или [CDockablePane](../../mfc/reference/cdockablepane-class.md).  
  
##  <a name="calcexpecteddockedrect"></a>  CPaneFrameWnd::CalcExpectedDockedRect  
 Вычисляет ожидаемый прямоугольник закрепленного окна.  
  
```  
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndToDock`  
 Указатель на окно будет закреплено.  
  
 [in] `ptMouse`  
 Положение мыши.  
  
 [выходной] `rectResult`  
 Расчетный прямоугольник.  
  
 [выходной] `bDrawTab`  
 Если `TRUE`, рисование вкладки. Если `FALSE`, не отображаются вкладки.  
  
 [выходной] `ppTargetBar`  
 Указатель на нужной панели.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вычисляет прямоугольник, должны занимать окна, если пользователь перетащить окна в точке, заданной `ptMouse` и закрепленные он существует.  
  
##  <a name="canbeattached"></a>  CPaneFrameWnd::CanBeAttached  
 Определяет, может ли текущая панель быть закреплена на другой панели или окне фрейма.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если области можно прикреплять к другой панели или окне фрейма; в противном случае `FALSE`.  
  
##  <a name="canbedockedtopane"></a>  CPaneFrameWnd::CanBeDockedToPane  
 Определяет, может ли окно области быть закреплено на панели.  
  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockingBar`  
 Область.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если мини-рамки можно прикреплять к `pDockingBar`; в противном случае — 0.  
  
##  <a name="checkgrippervisibility"></a>  CPaneFrameWnd::CheckGripperVisibility  

  
```  
virtual void CheckGripperVisibility();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="converttotabbeddocument"></a>  CPaneFrameWnd::ConvertToTabbedDocument  
 Преобразует панель в документ с вкладками.  
  
```  
virtual void ConvertToTabbedDocument();
```  
  
##  <a name="create"></a>  CPaneFrameWnd::Create  
 Создает окно области и прикрепляет его к [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszWindowName`  
 Задает текст, отображаемый на плавающего окна.  
  
 [in] `dwStyle`  
 Указывает стиль окна. Дополнительные сведения см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `rect`  
 Указывает исходный размер и положение плавающего окна.  
  
 [in] [out] `pParentWnd`  
 Указывает родительского фрейма для плавающего окна. Это значение не должно быть `NULL`.  
  
 [in] [out] `pContext`  
 Указывает контекст, определяемый пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если окно был создан успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Плавающего окна создаются в два этапа. Во-первых, платформа создает `CPaneFrameWnd` объекта. Во-вторых, он вызывает `Create` для создания плавающего окна Windows и присоединить его к `CPaneFrameWnd` объекта.  
  
##  <a name="createex"></a>  CPaneFrameWnd::CreateEx  
 Создает окно области и прикрепляет его к [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwStyleEx`  
 Указывает стиль окна расширенного. Дополнительные сведения см. в разделе [расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
 [in] `lpszWindowName`  
 Задает текст, отображаемый на плавающего окна.  
  
 [in] `dwStyle`  
 Указывает стиль окна. Дополнительные сведения см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `rect`  
 Указывает исходный размер и положение плавающего окна.  
  
 [in] [out] `pParentWnd`  
 Указывает родительского фрейма для плавающего окна. Это значение не должно быть `NULL`.  
  
 [in] [out] `pContext`  
 Указывает контекст, определяемый пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если окно был создан успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Плавающего окна создаются в два этапа. Во-первых, платформа создает `CPaneFrameWnd` объекта. Во-вторых, он вызывает `Create` для создания плавающего окна Windows и присоединить его к `CPaneFrameWnd` объекта.  
  
##  <a name="dockpane"></a>  CPaneFrameWnd::DockPane  
 Закрепляет область.  
  
```  
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `bWasDocked`  
 `TRUE` Если область уже была закреплена; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если операция выполнена успешно, `CDockablePane` , области были закреплены, в противном случае `NULL`.  
  
##  <a name="findfloatingpanebyid"></a>  CPaneFrameWnd::FindFloatingPaneByID  
 Находит в глобальном списке плавающих панелей панель с указанным идентификатором элемента управления.  
  
```  
static CBasePane* FindFloatingPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Представляет идентификатор элемента панели управления для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Области с указанным Идентификатором элемента управления; в противном случае `NULL`, если область не имеет идентификатор указанного элемента управления.  
  
##  <a name="framefrompoint"></a>  CPaneFrameWnd::FrameFromPoint  
 Находит окно области, содержащий указанную точку.  
  
```  
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,  
    int nSensitivity,  
    CPaneFrameWnd* pFrameToExclude = NULL,  
    BOOL bFloatMultiOnly = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pt`  
 Точка в экранных координатах.  
  
 [in] `nSensitivity`  
 Увеличьте область поиска из окна области, этот размер. Окна области удовлетворяет условиям поиска, если заданная точка находится в области увеличения.  
  
 [in] `pFrameToExclude`  
 Указывает окна области, чтобы исключить из поиска.  
  
 [in] `bFloatMultiOnly`  
 Если `TRUE`, поиск окна, имеющие только `CBRS_FLOAT_MULTI` стиля. Если `FALSE`, найти все окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно области, который содержит `pt`; в противном случае `NULL`.  
  
##  <a name="getcaptionheight"></a>  CPaneFrameWnd::GetCaptionHeight  
 Возвращает высоту заголовка окна области.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях окна области.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для определения высоты окна области. По умолчанию имеет значение высоты `SM_CYSMCAPTION`. Дополнительные сведения см. в разделе [GetSystemMetrics функция](http://msdn.microsoft.com/library/windows/desktop/ms724385).  
  
##  <a name="getcaptionrect"></a>  CPaneFrameWnd::GetCaptionRect  
 Вычисляет ограничивающий прямоугольник заголовка окна области.  
  
```  
virtual void GetCaptionRect(CRect& rectCaption) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectCaption`  
 Содержит размер и положение заголовка окна области, в экранных координатах.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для вычисления ограничивающий прямоугольник заголовка окна области.  
  
##  <a name="getcaptiontext"></a>  CPaneFrameWnd::GetCaptionText  
 Возвращает текст заголовка.  
  
```  
virtual CString GetCaptionText();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текст заголовка окна области.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при отображении текста заголовка.  
  
##  <a name="getdockingmanager"></a>  CPaneFrameWnd::GetDockingManager  

  
```  
CDockingManager* GetDockingManager() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdockingmode"></a>  CPaneFrameWnd::GetDockingMode  
 Возвращает режим закрепления.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Режим закрепления. Одно из следующих значений:  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
##  <a name="getfirstvisiblepane"></a>  CPaneFrameWnd::GetFirstVisiblePane  
 Возвращает первую видимую панель, содержащуюся в окне области.  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 На первой панели окна области или `NULL` Если области не содержит окна области.  
  
##  <a name="gethotpoint"></a>  CPaneFrameWnd::GetHotPoint  

  
```  
CPoint GetHotPoint() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpane"></a>  CPaneFrameWnd::GetPane  
 Возвращает панель, содержащуюся в окне области.  
  
```  
virtual CWnd* GetPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Области, в которой содержится в мини-рамки или `NULL` Если области не содержит окна области.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanecount"></a>  CPaneFrameWnd::GetPaneCount  
 Возвращает число панелей, содержащихся в окне области.  
  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество областей в окна области. Это значение может быть нулевой.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getparent"></a>  CPaneFrameWnd::GetParent  

  
```  
CWnd* GetParent();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpinstate"></a>  CPaneFrameWnd::GetPinState  

  
```  
BOOL GetPinState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getrecentfloatingrect"></a>  CPaneFrameWnd::GetRecentFloatingRect  

  
```  
CRect GetRecentFloatingRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getvisiblepanecount"></a>  CPaneFrameWnd::GetVisiblePaneCount  
 Возвращает число видимых панелей, содержащихся в окне области.  
  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число видимых панелей.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hittest"></a>  CPaneFrameWnd::HitTest  
 Определяет, какая часть окна области находится в заданной точке.  
  
```  
virtual LRESULT HitTest(
    CPoint point,  
    BOOL bDetectCaption);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Точки для проверки.  
  
 [in] `bDetectCaption`  
 Если `TRUE`, проверить точку с заголовком. Если `FALSE`, пропустить заголовок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|`HTNOWHERE`|Точка находится за пределами окна области.|  
|`HTCLIENT`|Точка находится в клиентской области.|  
|`HTCAPTION`|Точка находится в заголовке.|  
|`HTTOP`|Точка находится в начале.|  
|`HTTOPLEFT`|Точка находится в верхнем левом углу.|  
|`HTTOPRIGHT`|Точка находится в правом верхнем углу.|  
|`HTLEFT`|Точка находится слева.|  
|`HTRIGHT`|Точка находится справа.|  
|`HTBOTTOM`|Точка находится в нижней.|  
|`HTBOTTOMLEFT`|Точка находится в нижнем левом углу.|  
|`HTBOTTOMRIGHT`|Точка находится в нижнем правом углу.|  
  
##  <a name="iscaptured"></a>  CPaneFrameWnd::IsCaptured  

  
```  
BOOL IsCaptured() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isdelayshow"></a>  CPaneFrameWnd::IsDelayShow  

  
```  
BOOL IsDelayShow() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isrolldown"></a>  CPaneFrameWnd::IsRollDown  
 Определяет, требуется ли развертывание окна области.  
  
```  
virtual BOOL IsRollDown() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если необходимо развертывание окна области; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, чтобы определить, следует ли развертывание окна области. Для окна области включена функция свертки/rolldown, если он содержит по крайней мере одну область, которую имеет `AFX_CBRS_AUTO_ROLLUP` флаг. Этот флаг установлен, при создании области. Дополнительные сведения см. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 По умолчанию платформа проверяет, является ли указатель мыши внутри окна области ограничивающий прямоугольник для определения, имеет ли окно произвести накат вниз. Можно переопределить это поведение в производном классе.  
  
##  <a name="isrollup"></a>  CPaneFrameWnd::IsRollUp  
 Определяет, требуется ли свертывание окна области.  
  
```  
virtual BOOL IsRollUp() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если окно области должны быть сведены; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для определения, является ли окна области должны быть сведены. Для окна области включена функция свертки/rolldown, если он содержит по крайней мере одну область, которую имеет `AFX_CBRS_AUTO_ROLLUP` флаг. Этот флаг установлен, при создании области. Дополнительные сведения см. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 По умолчанию платформа проверяет, является ли указатель мыши внутри окна области ограничивающий прямоугольник для определения, имеет ли окно получить сводные данные. Можно переопределить это поведение в производном классе.  
  
##  <a name="killdockingtimer"></a>  CPaneFrameWnd::KillDockingTimer  
 Останавливает таймер закрепления.  
  
```  
void KillDockingTimer();
```  
  
##  <a name="loadstate"></a>  CPaneFrameWnd::LoadState  
 Загружает состояние панели из реестра.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Имя профиля.  
  
 [in] `uiID`  
 Идентификатор области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если состояние панели был загружен успешно. в противном случае `FALSE`.  
  
##  <a name="m_busesavebits"></a>  CPaneFrameWnd::m_bUseSaveBits  
 Указывает, следует ли регистрация класса окна, имеющий `CS_SAVEBITS` стиль класса.  
  
```  
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого статического члена `TRUE` зарегистрировать класс окна области с `CS_SAVEBITS` стиля. Это может помочь снизить мерцание, когда пользователь перетаскивает окна области.  
  
##  <a name="onbeforedock"></a>  CPaneFrameWnd::OnBeforeDock  
 Определяет возможность закрепления.  
  
```  
virtual BOOL OnBeforeDock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если возможно; закрепления в противном случае `FALSE`.  
  
##  <a name="oncheckrollstate"></a>  CPaneFrameWnd::OnCheckRollState  
 Определяет, требуется ли свертывание или развертывание окна области.  
  
```  
virtual void OnCheckRollState();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, чтобы определить, необходимо ли откатить вверх или вниз окна области.  
  
 По умолчанию платформа вызывает [CPaneFrameWnd::IsRollUp](#isrollup) и [CPaneFrameWnd::IsRollDown](#isrolldown) только растягивает или восстанавливает окна области. Можно переопределить этот метод в производном классе для использования различных визуальных эффектов.  
  
##  <a name="ondocktorecentpos"></a>  CPaneFrameWnd::OnDockToRecentPos  
 Закрепляет окно области в его последней позиции.  
  
```  
virtual void OnDockToRecentPos();
```  
  
##  <a name="ondrawborder"></a>  CPaneFrameWnd::OnDrawBorder  
 Рисует границы окна области.  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, используемого для рисования границ.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для отрисовки границ окна области.  
  
##  <a name="onkillrolluptimer"></a>  CPaneFrameWnd::OnKillRollUpTimer  
 Останавливает таймер свертки.  
  
```  
virtual void OnKillRollUpTimer();
```  
  
##  <a name="onmovepane"></a>  CPaneFrameWnd::OnMovePane  
 Смещает окно области на указанное расстояние.  
  
```  
virtual void OnMovePane(
    CPane* pBar,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на область (пропускается).  
  
 [in] `ptOffset`  
 Смещение, которое необходимо переместить область.  
  
##  <a name="onpanerecalclayout"></a>  CPaneFrameWnd::OnPaneRecalcLayout  
 Настраивает макет панели внутри окна области.  
  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при необходимости настройки макета области внутри окна области.  
  
 По умолчанию располагается область охватывают всей клиентской области окна области.  
  
##  <a name="onsetrolluptimer"></a>  CPaneFrameWnd::OnSetRollUpTimer  
 Устанавливает таймер свертки.  
  
```  
virtual void OnSetRollUpTimer();
```  
  
##  <a name="onshowpane"></a>  CPaneFrameWnd::OnShowPane  
 Вызывается платформой при скрытии или отображении панели в окне области.  
  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Области, которые отображены или скрыты.  
  
 [in] `bShow`  
 `TRUE` Если отображается области; `FALSE` Если область скрыта.  
  
### <a name="remarks"></a>Примечания  
 Вызывается платформой при отображении и скрытии панели в окне области. Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="pin"></a>  CPaneFrameWnd::Pin  

  
```  
void Pin(BOOL bPin = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bPin`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="panefrompoint"></a>  CPaneFrameWnd::PaneFromPoint  
 Возвращает панель, если она содержит предоставленную пользователем точку в пределах окна области.  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bCheckVisibility);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Точка, пользователь щелкнул в экранных координатах.  
  
 [in] `nSensitivity`  
 Этот параметр не используется.  
  
 [in] `bCheckVisibility`  
 `TRUE` Чтобы указать, что должно возвращаться только видимых панелей; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Области, в которой пользователь щелкнул, или `NULL` Если области не существует в этом расположении.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения область, в которой содержится заданная точка.  
  
##  <a name="redrawall"></a>  CPaneFrameWnd::RedrawAll  
 Перерисовывает все окна областей.  
  
```  
static void RedrawAll();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод обновляет все окна путем вызова [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) для каждого окна.  
  
##  <a name="removenonvalidpanes"></a>  CPaneFrameWnd::RemoveNonValidPanes  
 Вызывается платформой для удаления недопустимых панелей.  
  
```  
virtual void RemoveNonValidPanes();
```  
  
##  <a name="removepane"></a>  CPaneFrameWnd::RemovePane  
 Удаляет панель из окна области.  
  
```  
virtual void RemovePane(
    CBasePane* pWnd,  
    BOOL bDestroy = FALSE,  
    BOOL bNoDelayedDestroy = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель на область для удаления.  
  
 [in] `bDestroy`  
 Указывает, что происходит с окна области. Если `bDestroy` — `TRUE`, этот метод немедленно удаляет окна области. Если это `FALSE`, этот метод удаляет окна области после определенных задержки.  
  
 [in] `bNoDelayedDestroy`  
 Если `TRUE`, отложенной уничтожения отключена. Если `FALSE`, отложенной уничтожения включен.  
  
### <a name="remarks"></a>Примечания  
 Платформа для уничтожения окна сразу или после определенных задержки. Если нужно отложить уничтожение окна, передайте `FALSE` в `bNoDelayedDestroy` параметра. Отложенное удаление происходит во время обработки платформа `AFX_WM_CHECKEMPTYMINIFRAME` сообщения.  
  
##  <a name="replacepane"></a>  CPaneFrameWnd::ReplacePane  
 Заменяет одну панель другой.  
  
```  
virtual void ReplacePane(
    CBasePane* pBarOrg,  
    CBasePane* pBarReplaceWith);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBarOrg`  
 Указатель на исходной области.  
  
 [in] `pBarReplaceWith`  
 Указатель на область, которую заменяет исходной области.  
  
##  <a name="savestate"></a>  CPaneFrameWnd::SaveState  
 Сохраняет состояние панели в реестр.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Имя профиля.  
  
 [in] `uiID`  
 Идентификатор области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если состояние панели был сохранен успешно. в противном случае `FALSE`.  
  
##  <a name="setcaptionbuttons"></a>  CPaneFrameWnd::SetCaptionButtons  
 Задает кнопки заголовка.  
  
```  
virtual void SetCaptionButtons(DWORD dwButtons);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwButtons`  
 Побитовый оператор или сочетания из следующих значений:  
  
- `AFX_CAPTION_BTN_CLOSE`  
  
- `AFX_CAPTION_BTN_PIN`  
  
- `AFX_CAPTION_BTN_MENU`  
  
- `AFX_CAPTION_BTN_CUSTOMIZE`  
  
##  <a name="setdelayshow"></a>  CPaneFrameWnd::SetDelayShow  

  
```  
void SetDelayShow(BOOL bDelayShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDelayShow`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdockingmanager"></a>  CPaneFrameWnd::SetDockingManager  

  
```  
void SetDockingManager(CDockingManager* pManager);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pManager`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdockingtimer"></a>  CPaneFrameWnd::SetDockingTimer  
 Устанавливает таймер закрепления.  
  
```  
void SetDockingTimer(UINT nTimeOut);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTimeOut`  
 Значение времени ожидания в миллисекундах.  
  
##  <a name="setdockstate"></a>  CPaneFrameWnd::SetDockState  
 Задает состояние закрепления.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockManager`  
 Указатель на диспетчере закрепления.  
  
##  <a name="sethotpoint"></a>  CPaneFrameWnd::SetHotPoint  

  
```  
void SetHotPoint(CPoint& ptNew);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ptNew`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpredockstate"></a>  CPaneFrameWnd::SetPreDockState  
 Вызывается платформой для задания предварительного состояния закрепления.  
  
```  
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,  
    CBasePane* pBarToDock = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `preDockState`  
 Возможные значения:  
  
- `PDS_NOTHING`,  
  
- `PDS_DOCK_REGULAR`,  
  
- `PDS_DOCK_TO_TAB`  
  
 [in] `pBarToDock`  
 Указатель на панель, чтобы закрепить.  
  
 [in] `dockMethod`  
 Метод закрепления. (Этот параметр учитывается).  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если окно области не закреплена; `FALSE` , если она закреплена.  
  
##  <a name="sizetocontent"></a>  CPaneFrameWnd::SizeToContent  
 Изменяет размер окна области, чтобы он эквивалентен содержащейся панели.  
  
```  
virtual void SizeToContent();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для настройки размера окна области размеру содержащейся панели.  
  
##  <a name="starttearoff"></a>  CPaneFrameWnd::StartTearOff  
 Делает меню перемещаемым.  
  
```  
BOOL StartTearOff(CMFCPopu* pMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenu`  
 Указатель на меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE`, если метод выполнен успешно; в противном случае — значение `FALSE`.  
  
##  <a name="storerecentdocksiteinfo"></a>  CPaneFrameWnd::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="storerecenttabrelatedinfo"></a>  CPaneFrameWnd::StoreRecentTabRelatedInfo  

  
```  
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockingBar`  
 [in] `pTabbedBar`  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)
