---
title: Класс CMFCStatusBar | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
dev_langs:
- C++
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b622ca84ca73090d609cbb557096fb75802a023
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcstatusbar-class"></a>Класс CMFCStatusBar
`CMFCStatusBar` Класс реализует строку состояния, аналогичную `CStatusBar` класса. Однако класс `CMFCStatusBar` не содержит функции, предоставляемые классом `CStatusBar` , такие как возможность отображать изображения, анимации и индикаторы выполнения, а также возможность реагировать на двойные нажатия мыши. 

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]   
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(Переопределяет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||  
|[CMFCStatusBar::Create](#create)|Создает панель элементов управления и прикрепляет его к [CPane](../../mfc/reference/cpane-class.md) объекта. (Переопределяет [CPane::Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCStatusBar::CreateEx](#createex)|Создает панель элементов управления и прикрепляет его к [CPane](../../mfc/reference/cpane-class.md) объекта. (Переопределяет [CPane::CreateEx](../../mfc/reference/cpane-class.md#createex).)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, может ли другой области динамической вставки между этой панели и родительского фрейма. (Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Включает или отключает обработку мыши дважды щелкает в строке состояния.|  
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Отображает индикатор выполнения в указанной области.|  
|[CMFCStatusBar::GetCount](#getcount)|Возвращает количество областей в строке состояния.|  
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||  
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCStatusBar::GetItemID](#getitemid)||  
|[CMFCStatusBar::GetItemRect](#getitemrect)||  
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||  
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||  
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Возвращает стиль панели. (Переопределяет [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|  
|[CMFCStatusBar::GetPaneText](#getpanetext)||  
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Возвращает ширину в пикселях указанной области строки состояния.|  
|[CMFCStatusBar::GetTipText](#gettiptext)|Возвращает текст подсказки для указанной области строки состояния.|  
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|Делает недействительной указанной области и перерисовывает его содержимого.|  
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Вызывается платформой до создания окна Windows, присоединенного к данному `CWnd` объекта. (Переопределяет [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|  
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||  
|[CMFCStatusBar::SetIndicators](#setindicators)||  
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Назначает анимации для указанной области.|  
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Задает цвет фона для указанной области строки состояния.|  
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Задает значок для указанной области строки состояния.|  
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||  
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|Задает текущее положение индикатора хода выполнения для указанной области строки состояния.|  
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Задает стиль окна. (Переопределяет [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|  
|[CMFCStatusBar::SetPaneText](#setpanetext)||  
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Задает цвет текста для указанной области строки состояния.|  
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Задает ширину в пикселях указанной области строки состояния.|  
|[CMFCStatusBar::SetTipText](#settiptext)|Задает текст подсказки для указанной области строки состояния.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Вызывается платформой, когда он перерисовывает области строки состояния.|  
  
## <a name="remarks"></a>Примечания  
 На следующей диаграмме показан на рисунке строки состояния из [состояние панели демонстрационный пример](../../visual-cpp-samples.md) приложения.  
  
 ![Пример CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "cmfcstatusbar")  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется локальные переменные, которые приложение использует для вызова методов в `CMFCStatusBar` класса. Эти переменные объявляются в StatusBarDemoView.h. Объявлено главного фрейма в MainFrm.h, документ объявляется в StatusBarDemoDoc.h и представление объявляется в StatusBarDemoView.h. Этот фрагмент кода является частью [состояние панели демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить ссылку на `CMFCStatusBar` объекта путем введения `GetStatusBar` метод в MainFrm.h и затем вызвать этот метод из `GetStatusBar` метода в StatusBarDemoView.h. Этот фрагмент кода является частью [состояние панели демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует вызов методов `CMFCStatusBar` класса в StatusBarDemoView.cpp. Константы объявляются в MainFrm.h. В примере показано, как задать значок, задания текста всплывающей панели строки состояния, будет отображаться индикатор хода выполнения в указанной области, назначить анимации для указанной области, текст и ширину панели строки состояния и текущий индикатор хода выполнения progr панель ESS для панели строки состояния. Этот фрагмент кода является частью [состояние панели демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxstatusbar.h  
  
##  <a name="calcfixedlayout"></a>  CMFCStatusBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="commandtoindex"></a>  CMFCStatusBar::CommandToIndex  

  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIDFind`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="create"></a>  CMFCStatusBar::Create  

  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 [in] `dwStyle`  
 [in] `nID`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="createex"></a>  CMFCStatusBar::CreateEx  

  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 [in] `dwCtrlStyle`  
 [in] `dwStyle`  
 [in] `nID`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="doesallowdyninsertbefore"></a>  CMFCStatusBar::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enablepanedoubleclick"></a>  CMFCStatusBar::EnablePaneDoubleClick  
 Включает или отключает обработку мыши дважды щелкает в строке состояния.  
  
```  
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Если `TRUE`, включите обработку мыши дважды щелкните. В противном случае отключите обработку двойной щелчок мышью.  
  
### <a name="remarks"></a>Примечания  
 При включении в строке состояния для обработки двойных щелчков Windows отправляет `WM_COMMAND` уведомления вместе с идентификатора ресурса владелец строки каждый раз при двойном щелчке на панели строки состояния состояния.  
  
##  <a name="enablepaneprogressbar"></a>  CMFCStatusBar::EnablePaneProgressBar  
 В указанной области будет отображаться индикатор хода выполнения.  
  
```  
void EnablePaneProgressBar(
    int nIndex,  
    long nTotal=100,  
    BOOL bDisplayText=FALSE,  
    COLORREF clrBar=-1,  
    COLORREF clrBarDest=-1,  
    COLORREF clrProgressText=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает, индикатор выполнения, чтобы включить индекс области.  
  
 [in] `nTotal`  
 Указывает максимальное значение для индикатора хода выполнения.  
  
 [in] `bDisplayText`  
 Отображение индикатора текущего значения хода выполнения.  
  
 [in] `clrBar`  
 Задает цвет фона индикатора хода выполнения.  
  
 [in] `clrBarDest`  
 Задает вторичный цвет фона панели хода выполнения. Использовать другое значение, чем `clrBar` для заливки цветом, объединяются в градиенте.  
  
 [in] `clrProgressText`  
 Указывает цвет текста индикатора хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите отключить панель вызов выполняется `EnablePaneProgressBar` с `nTotal` задано значение -1. По умолчанию `nTotal` установлено значение 100. Таким образом не все дополнительные вычисления для отображения хода выполнения в процентах.  
  
 Следует передавать разные значения `clrBar` и `clrBarDest` , чтобы цвет фона индикатора хода выполнения отображает цвет, объединяются в градиенте. .  
  
 Чтобы задать текущий ход выполнения, вызовите [CMFCStatusBar::SetPaneProgress](#setpaneprogress) метод.  
  
##  <a name="getcount"></a>  CMFCStatusBar::GetCount  
 Возвращает число панелей в строке состояния.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество областей в строке состояния.  
  
##  <a name="getdrawextendedarea"></a>  CMFCStatusBar::GetDrawExtendedArea  

  
```  
BOOL GetDrawExtendedArea() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getextendedarea"></a>  CMFCStatusBar::GetExtendedArea  

  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getitemid"></a>  CMFCStatusBar::GetItemID  

  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getitemrect"></a>  CMFCStatusBar::GetItemRect  

  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 [in] `lpRect`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpaneinfo"></a>  CMFCStatusBar::GetPaneInfo  

  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 [in] `nID`  
 [in] `nStyle`  
 [in] `cxWidth`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpaneprogress"></a>  CMFCStatusBar::GetPaneProgress  

  
```  
long GetPaneProgress(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanestyle"></a>  CMFCStatusBar::GetPaneStyle  

  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanetext"></a>  CMFCStatusBar::GetPaneText  

  
```  
void GetPaneText(
    int nIndex,  
    CString& s) const;  
  
CString GetPaneText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 [in] `s`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanewidth"></a>  CMFCStatusBar::GetPaneWidth  
 Получает ширину панели строки состояния.  
  
```  
int GetPaneWidth(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс панели строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина панели строки состояния, `nIndex` указывает; в противном случае — нуль, если в строке состояния области не существует.  
  
##  <a name="gettiptext"></a>  CMFCStatusBar::GetTipText  
 Получить текст подсказки для панели строки состояния.  
  
```  
CString GetTipText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс области, для которого требуется извлечь текст подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текст подсказки для панели строки состояния, `nIndex` указывает. В противном случае — пустой строке, если панель строки состояния не существует для указанного `nIndex` или его текст всплывающей подсказки, пустое.  
  
##  <a name="invalidatepanecontent"></a>  CMFCStatusBar::InvalidatePaneContent  
 Делает недоступной панели строки состояния и перерисовывает его содержимого.  
  
```  
void InvalidatePaneContent(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс область, содержимое которого является недействительным и перерисовать.  
  
### <a name="remarks"></a>Примечания  
 Если строка состояния становится недействительным, оно помечено для перерисовки. Windows перерисовывает его при `UpdateWindow` метод отправляет `WM_PAINT` сообщения к `OnPaint` метод.  
  
##  <a name="ondrawpane"></a>  CMFCStatusBar::OnDrawPane  
 Перерисовывает области строки состояния.  
  
```  
virtual void OnDrawPane(
    CDC* pDC,  
    CMFCStatusBarPaneInfo* pPane);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для рисования.  
  
 [in] `pPane`  
 Указатель на `CMFCStatusBarPaneInfo` структуру, содержащую сведения об области перерисовку.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `OnDrawPane` перерисовывает области с помощью контекста устройства `pDC` согласно стиля на панели и его содержимое.  
  
 Переопределите этот метод в `CMFCStatusBar`-производного класса, чтобы настроить внешний вид области.  
  
##  <a name="precreatewindow"></a>  CMFCStatusBar::PreCreateWindow  

  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `cs`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdrawextendedarea"></a>  CMFCStatusBar::SetDrawExtendedArea  

  
```  
void SetDrawExtendedArea(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setindicators"></a>  CMFCStatusBar::SetIndicators  

  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpIDArray`  
 [in] `nIDCount`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpaneanimation"></a>  CMFCStatusBar::SetPaneAnimation  
 Назначает анимации для указанной области.  
  
```  
void SetPaneAnimation(
    int nIndex,  
    HIMAGELIST hImageList,  
    UINT nFrameRate=500,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс панели, к которому вы хотите назначить в него анимации.  
  
 [in] `hImageList`  
 Задает дескриптор для списка изображений, который содержит кадров анимации.  
  
 [in] `nFrameRate`  
 Указывает частоту кадров, в миллисекундах для анимации.  
  
 [in] `bUpdate`  
 Если `TRUE`, немедленно обновлять содержимое области. В противном случае содержимое панели обновляется, когда он становится недействительным.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите отключить текущий анимации, вызовите `SetPaneAnimation` с `hImageList` значение `NULL`.  
  
##  <a name="setpanebackgroundcolor"></a>  CMFCStatusBar::SetPaneBackgroundColor  
 Задает цвет фона панели строки состояния.  
  
```  
void SetPaneBackgroundColor(
    int nIndex,  
    COLORREF clrBackground=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс области, для которого требуется задать новый цвет фона.  
  
 [in] `clrBackground`  
 Указывает новый цвет фона.  
  
 [in] `bUpdate`  
 Если `TRUE`, немедленно обновлять содержимое области. В противном случае не обновить содержимое области до области становится недействительным другим методом.  
  
##  <a name="setpaneicon"></a>  CMFCStatusBar::SetPaneIcon  
 Задает значок панели строки состояния.  
  
```  
void SetPaneIcon(
    int nIndex,  
    HICON hIcon,  
    BOOL bUpdate=TRUE);

 
void SetPaneIcon(
    int nIndex,  
    HBITMAP hBmp,  
    COLORREF clrTransparent=RGB(255, 0, 255),  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс области, для которого требуется задать изображение.  
  
 [in] `hIcon`  
 Указывает дескриптор значка в качестве области изображения.  
  
 [in] `bUpdate`  
 Указывает, следует немедленно обновить содержимое области.  
  
 [in] `hBmp`  
 Указывает дескриптор растрового изображения в качестве области изображения.  
  
 [in] `clrTransparent`  
 Определяет прозрачный цвет изображения, `hBmp` указывает.  
  
### <a name="remarks"></a>Примечания  
 Можно передать либо `HICON` или `HBITMAP` вместе с прозрачный цвет, чтобы задать область изображения. Если вы не хотите больше отображения изображения, передайте `NULL` значение в качестве маркера изображения.  
  
 Если любой запущенная анимация, [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) имеет задано, анимация будет остановлена.  
  
##  <a name="setpaneinfo"></a>  CMFCStatusBar::SetPaneInfo  

  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 [in] `nID`  
 [in] `nStyle`  
 [in] `cxWidth`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpaneprogress"></a>  CMFCStatusBar::SetPaneProgress  
 Задайте текущий индикатор хода выполнения индикатора хода выполнения для указанной области.  
  
```  
void SetPaneProgress(
    int nIndex,  
    long nCurr,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс области, для которого требуется обновить индикатор хода выполнения.  
  
 [in] `nCurr`  
 Указывает текущее значение индикатора хода выполнения.  
  
 [in] `bUpdate`  
 Указывает, является ли области должны быть обновлены сразу же.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается в том случае, если вы хотите обновить индикатор хода выполнения для индикатора в указанной области.  
  
 Чтобы использовать эту функцию для данной области, необходимо вызвать [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) первой.  
  
##  <a name="setpanestyle"></a>  CMFCStatusBar::SetPaneStyle  

  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 [in] `nStyle`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpanetext"></a>  CMFCStatusBar::SetPaneText  

  
```  
virtual BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 [in] `lpszNewText`  
 [in] `bUpdate`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpanetextcolor"></a>  CMFCStatusBar::SetPaneTextColor  
 Задает цвет текста указанной области.  
  
```  
void SetPaneTextColor(
    int nIndex,  
    COLORREF clrText=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс панели, к которому вы хотите назначить новый цвет текста.  
  
 [in] `clrText`  
 Указывает цвет текста.  
  
 [in] `bUpdate`  
 Если `TRUE`, немедленно обновлять содержимое области. В противном случае не обновить содержимое области до области становится недействительным другим методом.  
  
##  <a name="setpanewidth"></a>  CMFCStatusBar::SetPaneWidth  
 Задайте ширину панели строки состояния.  
  
```  
void SetPaneWidth(
    int nIndex,  
    int cx);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Индекс панели строки состояния, для которого требуется задать новую ширину.  
  
 [in] `cx`  
 Новая ширина панели строки состояния, в пикселях.  
  
##  <a name="settiptext"></a>  CMFCStatusBar::SetTipText  
 Задания текста всплывающей панели строки состояния.  
  
```  
void SetTipText(
    int nIndex,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Индекс области, к которому вы хотите назначить текст всплывающей подсказки.  
  
 [in] `pszTipText`  
 Новый текст всплывающей подсказки.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CPane](../../mfc/reference/cpane-class.md)   
 [Класс CStatusBar](../../mfc/reference/cstatusbar-class.md)
