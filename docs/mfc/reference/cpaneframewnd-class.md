---
title: Класс CPaneFrameWnd | Документация Майкрософт
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
ms.openlocfilehash: 3e25fda2f6d30ea13882ae3b40875fb3d4ec61c7
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37854126"
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
  
|Имя|Описание:|  
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
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|Определяет, требуется ли свертывание или развертывание окна области.|  
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|Рисует границы окна области.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|Указывает, следует ли регистрация класса окна со стилем класса CS_SAVEBITS.|  
  
## <a name="remarks"></a>Примечания  
 Когда панель переходит из закрепленного состояния в плавающее, платформа автоматически создает объект `CPaneFrameWnd`.  
  
 Окно области можно перетащить вместе с его видимым содержимым (немедленное закрепление) или с помощью прямоугольника перетаскивания (стандартное закрепление). Режим закрепления панели контейнера окна области определяет поведение окна области при перетаскивании. Дополнительные сведения см. в разделе [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
 В заголовке окна области отображаются кнопки, зависящие от стиля включенной панели. Если область можно закрыть ( [CBasePane::CanBeClosed](../../mfc/reference/cbasepane-class.md#canbeclosed)), он отображает кнопку «Close». Если область имеет стиль AFX_CBRS_AUTO_ROLLUP, отображается ПИН-код.  
  
 Если вы получаете производный класс из класса `CPaneFrameWnd`, необходимо сообщить платформе способ его создания. Создайте класс, переопределив [CPane::CreateDefaultMiniframe](../../mfc/reference/cpane-class.md#createdefaultminiframe), или задать `CPane::m_pMiniFrameRTC` члену, так чтобы он указывал на сведения о классе среды выполнения для класса.  
  
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
 [in] *pWnd*  
 На панели, чтобы добавить.  
  
##  <a name="addremovepanefromgloballist"></a>  CPaneFrameWnd::AddRemovePaneFromGlobalList  
 Добавляет панель в глобальный список или удаляет из него.  
  
```  
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,  
    BOOL bAdd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pWnd*  
 Область для добавления или удаления.  
  
 [in] *bAdd*  
 Если ненулевое значение, добавьте области. Если значение равно 0, удаления области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод был выполнен успешно; в противном случае 0.  
  
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
 [out] *rectBorderSize*  
 Содержит размер в пикселях для границы плавающего окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для вычисления размера границу плавающего окна. Возвращаемый размер зависит от независимо от плавающего окна содержит панель инструментов или [CDockablePane](../../mfc/reference/cdockablepane-class.md).  
  
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
 [in] *pWndToDock*  
 Указатель на окно будет закреплено.  
  
 [in] *ptMouse*  
 Положение мыши.  
  
 [out] *rectResult*  
 Расчетный прямоугольник.  
  
 [out] *bDrawTab*  
 Если значение равно TRUE, рисования вкладки. Если значение равно FALSE, не рисования вкладки.  
  
 [out] *ppTargetBar*  
 Указатель на целевой области.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вычисляет прямоугольник, который должны занимать окна, если пользователь перетащил окна точку, указанную *ptMouse* и закрепленные он существует.  
  
##  <a name="canbeattached"></a>  CPaneFrameWnd::CanBeAttached  
 Определяет, может ли текущая панель быть закреплена на другой панели или окне фрейма.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если области можно прикреплять к другой панели или окне фрейма; в противном случае — значение FALSE.  
  
##  <a name="canbedockedtopane"></a>  CPaneFrameWnd::CanBeDockedToPane  
 Определяет, может ли окно области быть закреплено на панели.  
  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pDockingBar*  
 Область.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если мини-рамки можно прикреплять к *pDockingBar*; в противном случае — 0.  
  
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
 Создает плавающего окна и прикрепляет его к [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszWindowName*  
 Задает текст, отображаемый в окне области.  
  
 [in] *dwStyle*  
 Указывает стиль окна. Дополнительные сведения см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] *rect*  
 Задает первоначальный размер и положение окна области.  
  
 [in] [out] *pParentWnd*  
 Указывает родительского фрейма окна области. Это значение не должно быть значение NULL.  
  
 [in] [out] *pContext*  
 Указывает контекст, определяемый пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если окно был создан успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Плавающего окна создается в два этапа. Во-первых, платформа создает `CPaneFrameWnd` объекта. Во-вторых, он вызывает `Create` для создания плавающего окна Windows и присоединить его к `CPaneFrameWnd` объекта.  
  
##  <a name="createex"></a>  CPaneFrameWnd::CreateEx  
 Создает плавающего окна и прикрепляет его к [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) объекта.  
  
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
 [in] *dwStyleEx*  
 Указывает стиль окна расширенного. Дополнительные сведения см. в разделе [расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
 [in] *lpszWindowName*  
 Задает текст, отображаемый в окне области.  
  
 [in] *dwStyle*  
 Указывает стиль окна. Дополнительные сведения см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] *rect*  
 Задает первоначальный размер и положение окна области.  
  
 [in] [out] *pParentWnd*  
 Указывает родительского фрейма окна области. Это значение не должно быть значение NULL.  
  
 [in] [out] *pContext*  
 Указывает контекст, определяемый пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если окно был создан успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Плавающего окна создается в два этапа. Во-первых, платформа создает `CPaneFrameWnd` объекта. Во-вторых, он вызывает `Create` для создания плавающего окна Windows и присоединить его к `CPaneFrameWnd` объекта.  
  
##  <a name="dockpane"></a>  CPaneFrameWnd::DockPane  
 Закрепляет область.  
  
```  
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Параметры  
 [out] *bWasDocked*  
 Значение TRUE, если уже был закреплен области; в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если операция выполнена успешно, `CDockablePane` что было закреплено на; в противном случае — NULL.  
  
##  <a name="findfloatingpanebyid"></a>  CPaneFrameWnd::FindFloatingPaneByID  
 Находит в глобальном списке плавающих панелей панель с указанным идентификатором элемента управления.  
  
```  
static CBasePane* FindFloatingPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nID*  
 Представляет идентификатор элемента панели управления для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Области с указанным Идентификатором элемента управления; в противном случае — NULL, если нет области имеет идентификатор указанного элемента управления.  
  
##  <a name="framefrompoint"></a>  CPaneFrameWnd::FrameFromPoint  
 Находит окно области, содержащей заданную точку.  
  
```  
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,  
    int nSensitivity,  
    CPaneFrameWnd* pFrameToExclude = NULL,  
    BOOL bFloatMultiOnly = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pt*  
 Точку в экранных координатах.  
  
 [in] *nSensitivity*  
 Увеличьте этот размер области поиска окна области. Окна области удовлетворяет условиям поиска, если заданная точка находится в области повышения.  
  
 [in] *pFrameToExclude*  
 Указывает окна области, чтобы исключить из поиска.  
  
 [in] *bFloatMultiOnly*  
 Значение TRUE, если поиск только окна со стилем CBRS_FLOAT_MULTI. Если значение равно FALSE, найдите все окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно минифрейма, содержащее *pt*; в противном случае — NULL.  
  
##  <a name="getcaptionheight"></a>  CPaneFrameWnd::GetCaptionHeight  
 Возвращает высоту заголовка окна области.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях окна области.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для определения высоты окна области. По умолчанию высота присваивается SM_CYSMCAPTION. Дополнительные сведения см. в разделе [функцию GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385).  
  
##  <a name="getcaptionrect"></a>  CPaneFrameWnd::GetCaptionRect  
 Вычисляет ограничивающий прямоугольник заголовка окна области.  
  
```  
virtual void GetCaptionRect(CRect& rectCaption) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *rectCaption*  
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
 Этот метод вызывается платформой при его отображении текст заголовка.  
  
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
  
- DT_STANDARD  
  
- DT_IMMEDIATE  
  
- DT_SMART  
  
##  <a name="getfirstvisiblepane"></a>  CPaneFrameWnd::GetFirstVisiblePane  
 Возвращает первую видимую панель, содержащуюся в окне области.  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая область окна области, или значение NULL, если окно области содержит не панели.  
  
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
 Область, содержащаяся в области, или значение NULL, если окно области содержит не панели.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanecount"></a>  CPaneFrameWnd::GetPaneCount  
 Возвращает число панелей, содержащихся в окне области.  
  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество областей в окне области. Это значение может равняться нулю.  
  
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
 [in] *точки*  
 Точка для проверки.  
  
 [in] *bDetectCaption*  
 Если значение равно TRUE, проверьте точку с заголовком. Если значение равно FALSE, можно пропустите заголовок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|HTNOWHERE|Точка находится за пределами окна области.|  
|HTCLIENT|Точка находится в клиентской области.|  
|HTCAPTION|Она в заголовок.|  
|HTTOP|Точка находится в верхней.|  
|HTTOPLEFT|Точка находится в левом верхнем углу.|  
|HTTOPRIGHT|Точка находится в правом верхнем углу.|  
|HTLEFT|Точка находится слева.|  
|HTRIGHT|Точка находится в правом.|  
|HTBOTTOM|Точка находится в нижней.|  
|HTBOTTOMLEFT|Точка находится в нижнем левом углу.|  
|HTBOTTOMRIGHT|Точка находится в нижнем правом углу.|  
  
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
 Значение TRUE, если необходимо развертывание окна области; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для определения, следует ли развертывание окна области. Функция rollup/rolldown включена для окна области, если он содержит по крайней мере одну область, с флагом AFX_CBRS_AUTO_ROLLUP. Этот флаг установлен, при создании области. Дополнительные сведения см. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 По умолчанию платформа проверяет ли указатель мыши находится внутри ограничивающего прямоугольника окна минифрейма для определения, имеет ли окно быть откат вниз. Можно переопределить это поведение в производном классе.  
  
##  <a name="isrollup"></a>  CPaneFrameWnd::IsRollUp  
 Определяет, требуется ли свертывание окна области.  
  
```  
virtual BOOL IsRollUp() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если окно области, которые необходимо выполнить откат. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для определения ли окна области должны быть сведены. Функция rollup/rolldown включена для окна области, если он содержит по крайней мере одну область, с флагом AFX_CBRS_AUTO_ROLLUP. Этот флаг установлен, при создании области. Дополнительные сведения см. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 По умолчанию платформа проверяет ли указатель мыши находится внутри ограничивающего прямоугольника окна минифрейма для определения, имеет ли окно должны быть сведены. Можно переопределить это поведение в производном классе.  
  
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
 [in] *lpszProfileName*  
 Имя профиля.  
  
 [in] *uiID*  
 Идентификатор области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если состояние панели был загружен успешно; в противном случае — значение FALSE.  
  
##  <a name="m_busesavebits"></a>  CPaneFrameWnd::m_bUseSaveBits  
 Указывает, следует ли регистрация класса окна, имеющий стиль класса CS_SAVEBITS.  
  
```  
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте статический элемент на значение true, чтобы класс окна минифрейма, в которой CS_SAVEBITS стиль регистра. Это может помочь снизить мерцание, когда пользователь перетаскивает окна области.  
  
##  <a name="onbeforedock"></a>  CPaneFrameWnd::OnBeforeDock  
 Определяет возможность закрепления.  
  
```  
virtual BOOL OnBeforeDock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если возможно; закрепления в противном случае — значение FALSE.  
  
##  <a name="oncheckrollstate"></a>  CPaneFrameWnd::OnCheckRollState  
 Определяет, требуется ли свертывание или развертывание окна области.  
  
```  
virtual void OnCheckRollState();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для определения, следует ли выполнить откат окна области вверх или вниз.  
  
 По умолчанию платформа вызывает [CPaneFrameWnd::IsRollUp](#isrollup) и [CPaneFrameWnd::IsRollDown](#isrolldown) и просто растягивает или восстанавливает окна области. Можно переопределить этот метод в производном классе для использования различных визуальных эффектов.  
  
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
 [in] *основного контроллера домена*  
 Контекст устройства, используемый для рисования границы.  
  
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
 [in] *pBar*  
 Указатель на область (игнорируются).  
  
 [in] *ptOffset*  
 Смещение, на которую следует переместить на панели.  
  
##  <a name="onpanerecalclayout"></a>  CPaneFrameWnd::OnPaneRecalcLayout  
 Настраивает макет области внутри окна области.  
  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при необходимости настройки макета области внутри окна области.  
  
 По умолчанию области располагается для охвата всей клиентской области окна области.  
  
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
 [in] *pBar*  
 Области, для которого создается видима или скрыта.  
  
 [in] *bShow*  
 Значение TRUE, если отображается области; Значение FALSE, если область скрыта.  
  
### <a name="remarks"></a>Примечания  
 Вызывается платформой при видима или скрыта область в окне области. Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="pin"></a>  CPaneFrameWnd::Pin  

  
```  
void Pin(BOOL bPin = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bPin*  
  
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
 [in] *точки*  
 Точки, который был щелкнут пользователем, в экранных координатах.  
  
 [in] *nSensitivity*  
 Этот параметр не используется.  
  
 [in] *bCheckVisibility*  
 Значение TRUE, чтобы указать, что должно возвращаться только видимых панелей; в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Области, который был щелкнут пользователем, или значение NULL, если панель не существует в этом расположении.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для получения область, в которой содержится данная точка.  
  
##  <a name="redrawall"></a>  CPaneFrameWnd::RedrawAll  
 Перерисовывает все окна областей.  
  
```  
static void RedrawAll();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод обновляет все окна, вызвав [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) для каждого окна.  
  
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
 [in] *pWnd*  
 Указатель на область для удаления.  
  
 [in] *bDestroy*  
 Указывает, что происходит с окна области. Если *bDestroy* имеет значение TRUE, этот метод уничтожает окно минифрейма немедленно. Если он имеет значение FALSE, этот метод уничтожает окно минифрейма после определенных задержки.  
  
 [in] *bNoDelayedDestroy*  
 Значение TRUE, если отключена отложенного удаления. Если значение равно FALSE, включено отложенного удаления.  
  
### <a name="remarks"></a>Примечания  
 Платформа для уничтожения окна немедленно или после определенных задержки. Если требуется отложить уничтожения окна, передайте значение FALSE в *bNoDelayedDestroy* параметра. Отложенное удаление происходит, когда платформа обрабатывает сообщение AFX_WM_CHECKEMPTYMINIFRAME.  
  
##  <a name="replacepane"></a>  CPaneFrameWnd::ReplacePane  
 Заменяет одну панель другой.  
  
```  
virtual void ReplacePane(
    CBasePane* pBarOrg,  
    CBasePane* pBarReplaceWith);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBarOrg*  
 Указатель на исходной области.  
  
 [in] *pBarReplaceWith*  
 Указатель на область, которая заменяет исходной области.  
  
##  <a name="savestate"></a>  CPaneFrameWnd::SaveState  
 Сохраняет состояние панели в реестр.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszProfileName*  
 Имя профиля.  
  
 [in] *uiID*  
 Идентификатор области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если состояние панели было сохранено успешно. в противном случае — значение FALSE.  
  
##  <a name="setcaptionbuttons"></a>  CPaneFrameWnd::SetCaptionButtons  
 Задает кнопки заголовка.  
  
```  
virtual void SetCaptionButtons(DWORD dwButtons);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *dwButtons*  
 Побитовое или сочетания из следующих значений:  
  
- AFX_CAPTION_BTN_CLOSE  
  
- AFX_CAPTION_BTN_PIN  
  
- AFX_CAPTION_BTN_MENU  
  
- AFX_CAPTION_BTN_CUSTOMIZE  
  
##  <a name="setdelayshow"></a>  CPaneFrameWnd::SetDelayShow  

  
```  
void SetDelayShow(BOOL bDelayShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bDelayShow*  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdockingmanager"></a>  CPaneFrameWnd::SetDockingManager  

  
```  
void SetDockingManager(CDockingManager* pManager);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pManager*  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdockingtimer"></a>  CPaneFrameWnd::SetDockingTimer  
 Устанавливает таймер закрепления.  
  
```  
void SetDockingTimer(UINT nTimeOut);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nвремя ожидания*  
 Значение времени ожидания в миллисекундах.  
  
##  <a name="setdockstate"></a>  CPaneFrameWnd::SetDockState  
 Задает состояние закрепления.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pDockManager*  
 Указатель на диспетчере закрепления.  
  
##  <a name="sethotpoint"></a>  CPaneFrameWnd::SetHotPoint  

  
```  
void SetHotPoint(CPoint& ptNew);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *ptNew*  
  
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
 [in] *preDockState*  
 Возможные значения:  
  
- PDS_NOTHING,  
  
- PDS_DOCK_REGULAR,  
  
- PDS_DOCK_TO_TAB  
  
 [in] *pBarToDock*  
 Указатель на область для закрепления.  
  
 [in] *dockMethod*  
 Метод закрепления. (Этот параметр учитывается).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если окно области не закреплена; Значение FALSE, если она закреплена.  
  
##  <a name="sizetocontent"></a>  CPaneFrameWnd::SizeToContent  
 Изменяет размер окна области, так как это эквивалентно содержащейся панели.  
  
```  
virtual void SizeToContent();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод изменяет размер окна области размеру содержащейся панели.  
  
##  <a name="starttearoff"></a>  CPaneFrameWnd::StartTearOff  
 Делает меню перемещаемым.  
  
```  
BOOL StartTearOff(CMFCPopu* pMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pMenu*  
 Указатель на меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.  
  
##  <a name="storerecentdocksiteinfo"></a>  CPaneFrameWnd::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBar*  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="storerecenttabrelatedinfo"></a>  CPaneFrameWnd::StoreRecentTabRelatedInfo  

  
```  
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pDockingBar*  
 [in] *pTabbedBar*  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)
