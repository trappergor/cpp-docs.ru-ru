---
title: "Класс CMFCStatusBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCStatusBar class
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
caps.latest.revision: 36
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 20881637d74bafffbcf2e0c3dcd1cc98e173aa07
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcstatusbar-class"></a>Класс CMFCStatusBar
`CMFCStatusBar` Класс реализует строку состояния, аналогично `CStatusBar` класса. Однако класс `CMFCStatusBar` не содержит функции, предоставляемые классом `CStatusBar` , такие как возможность отображать изображения, анимации и индикаторы выполнения, а также возможность реагировать на двойные нажатия мыши.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(Переопределяет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||  
|[CMFCStatusBar::Create](#create)|Создает панель элементов управления и присоединяет его к [CPane](../../mfc/reference/cpane-class.md) объекта. (Переопределяет [CPane::Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCStatusBar::CreateEx](#createex)|Создает панель элементов управления и присоединяет его к [CPane](../../mfc/reference/cpane-class.md) объекта. (Переопределяет [CPane::CreateEx](../../mfc/reference/cpane-class.md#createex).)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, может ли другой области динамически вставляются между этой панели и родительского фрейма. (Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
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
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Возвращает ширину в пикселях, указанной области строки состояния.|  
|[CMFCStatusBar::GetTipText](#gettiptext)|Возвращает текст подсказки для указанной области строки состояния.|  
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|Делает недействительной указанной области и перерисовывает его содержимого.|  
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Вызывается платформой до создания окна Windows, присоединенные к этому `CWnd` объекта. (Переопределяет [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|  
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||  
|[CMFCStatusBar::SetIndicators](#setindicators)||  
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Назначает анимации для указанной области.|  
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Задает цвет фона для области, указанной строки состояния.|  
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Задает значок для указанной области строки состояния.|  
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||  
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|Задает текущее положение индикатора хода выполнения для указанной области строки состояния.|  
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Задает стиль панели. (Переопределяет [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|  
|[CMFCStatusBar::SetPaneText](#setpanetext)||  
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Задает цвет текста для указанной области строки состояния.|  
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Задает ширину в пикселях указанной области строки состояния.|  
|[CMFCStatusBar::SetTipText](#settiptext)|Задает текст подсказки для указанной области строки состояния.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Вызывается инфраструктурой при его перерисовывает панели строки состояния.|  
  
## <a name="remarks"></a>Примечания  
 На следующей схеме показано рис строки состояния из [состояние панели демонстрационного](../../visual-cpp-samples.md) приложения.  
  
 ![Пример CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "cmfcstatusbar")  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется локальные переменные, которые приложение использует для вызова методов в `CMFCStatusBar` класса. Эти переменные объявляются в StatusBarDemoView.h. Главного фрейма объявляется в MainFrm.h и документа, объявленной в StatusBarDemoDoc.h представлении объявляется в StatusBarDemoView.h. Этот фрагмент кода является частью [демонстрационного панель состояния](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo №&9;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует получение ссылки на `CMFCStatusBar` объекта путем введения `GetStatusBar` метод MainFrm.h и вызов этого метода из `GetStatusBar` метода в StatusBarDemoView.h. Этот фрагмент кода является частью [демонстрационного панель состояния](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#7;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo №&8;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует вызов методов `CMFCStatusBar` класса StatusBarDemoView.cpp. Константы объявляются в MainFrm.h. В примере показано, как задать значок, задайте текст подсказки панели строки состояния, отображать индикатор в указанной области, назначить анимации к указанной области, задать текст и ширину панели строки состояния, а текущий индикатор выполнения для панели строки состояния индикатора хода выполнения. Этот фрагмент кода является частью [демонстрационного панель состояния](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo №&6;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#3;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#4;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#5;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxstatusbar.h  
  
##  <a name="calcfixedlayout"></a>CMFCStatusBar::CalcFixedLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="commandtoindex"></a>CMFCStatusBar::CommandToIndex  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIDFind`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="create"></a>CMFCStatusBar::Create  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="createex"></a>CMFCStatusBar::CreateEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="doesallowdyninsertbefore"></a>CMFCStatusBar::DoesAllowDynInsertBefore  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enablepanedoubleclick"></a>CMFCStatusBar::EnablePaneDoubleClick  
 Включает или отключает обработку мыши дважды щелкает в строке состояния.  
  
```  
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Если `TRUE`, обработку мыши дважды щелкните включить. В противном случае отключите обработку двойной щелчок мышью.  
  
### <a name="remarks"></a>Примечания  
 Если строка состояния включена для обработки двойные щелчки, Windows отправляет `WM_COMMAND` уведомления вместе с Идентификатором ресурса владелец строки каждый раз при двойном щелчке на панели строки состояния состояния.  
  
##  <a name="enablepaneprogressbar"></a>CMFCStatusBar::EnablePaneProgressBar  
 Отобразить индикатор выполнения в указанной области.  
  
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
 Указывает, индикатор, чтобы включить индекс области.  
  
 [in] `nTotal`  
 Указывает максимальное значение для индикатора хода выполнения.  
  
 [in] `bDisplayText`  
 Отображение индикатора текущего значения хода работы.  
  
 [in] `clrBar`  
 Задает цвет фона индикатора хода выполнения.  
  
 [in] `clrBarDest`  
 Задает вторичный цвет фона строки хода выполнения. Используйте другое значение, чем `clrBar` для заполнения с переходом в градиент цвета.  
  
 [in] `clrProgressText`  
 Задает цвет текста индикатора хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите отключить панель вызов выполняется `EnablePaneProgressBar` с `nTotal` задано значение -1. По умолчанию `nTotal` установлено значение 100. Таким образом любые дополнительные вычисления для отображения хода выполнения в процентах необязательно.  
  
 Необходимо передать различные значения `clrBar` и `clrBarDest` , чтобы цвет фона индикатора хода выполнения отображает цвет, объединяются в градиенте. .  
  
 Чтобы задать текущий ход выполнения, вызовите [CMFCStatusBar::SetPaneProgress](#setpaneprogress) метод.  
  
##  <a name="getcount"></a>CMFCStatusBar::GetCount  
 Возвращает количество областей в строке состояния.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество областей в строке состояния.  
  
##  <a name="getdrawextendedarea"></a>CMFCStatusBar::GetDrawExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetDrawExtendedArea() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getextendedarea"></a>CMFCStatusBar::GetExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getitemid"></a>CMFCStatusBar::GetItemID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getitemrect"></a>CMFCStatusBar::GetItemRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 [in] `lpRect`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpaneinfo"></a>CMFCStatusBar::GetPaneInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="getpaneprogress"></a>CMFCStatusBar::GetPaneProgress  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
long GetPaneProgress(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanestyle"></a>CMFCStatusBar::GetPaneStyle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanetext"></a>CMFCStatusBar::GetPaneText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="getpanewidth"></a>CMFCStatusBar::GetPaneWidth  
 Получает ширину области строки состояния.  
  
```  
int GetPaneWidth(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс панели строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина панели строки состояния, `nIndex` указывает; в противном случае — нуль, если в строке состояния области не существует.  
  
##  <a name="gettiptext"></a>CMFCStatusBar::GetTipText  
 Получить текст подсказки панели строки состояния.  
  
```  
CString GetTipText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс области, для которого нужно извлечь текст подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текст подсказки на панели строки состояния, `nIndex` указывает. В противном случае — пустая строка, если панель строки состояния не существует для указанного `nIndex` или если его текст подсказки пуста.  
  
##  <a name="invalidatepanecontent"></a>CMFCStatusBar::InvalidatePaneContent  
 Сделать недействительным панели строки состояния и перерисовывает его содержимого.  
  
```  
void InvalidatePaneContent(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс панели, содержимым которого является недействительным и перерисовать.  
  
### <a name="remarks"></a>Примечания  
 Если строка состояния становится недействительным, она помечена для перерисовки. Windows перерисовывает его при `UpdateWindow` метод отправляет `WM_PAINT` сообщение `OnPaint` метод.  
  
##  <a name="ondrawpane"></a>CMFCStatusBar::OnDrawPane  
 Перерисовывает панели строки состояния.  
  
```  
virtual void OnDrawPane(
    CDC* pDC,  
    CMFCStatusBarPaneInfo* pPane);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для рисования.  
  
 [in] `pPane`  
 Указатель на `CMFCStatusBarPaneInfo` структуру, содержащую сведения о панели перерисовку.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `OnDrawPane` перерисовывает области с помощью контекста устройства `pDC` согласно стиля и содержимого панели.  
  
 Переопределите этот метод в `CMFCStatusBar`-производного класса, чтобы настроить внешний вид области.  
  
##  <a name="precreatewindow"></a>CMFCStatusBar::PreCreateWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `cs`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdrawextendedarea"></a>CMFCStatusBar::SetDrawExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetDrawExtendedArea(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setindicators"></a>CMFCStatusBar::SetIndicators  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="setpaneanimation"></a>CMFCStatusBar::SetPaneAnimation  
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
 Указывает индекс области, к которому вы хотите назначить анимации.  
  
 [in] `hImageList`  
 Указывает дескриптор списка изображений, который содержит кадров анимации.  
  
 [in] `nFrameRate`  
 Указывает частоту кадров в миллисекундах для анимации.  
  
 [in] `bUpdate`  
 Если `TRUE`, немедленного обновления содержимого панели. В противном случае — содержимое панели обновляется при их недействительными.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите отключить текущий анимации, вызвать `SetPaneAnimation` с `hImageList` значение `NULL`.  
  
##  <a name="setpanebackgroundcolor"></a>CMFCStatusBar::SetPaneBackgroundColor  
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
 Если `TRUE`, немедленного обновления содержимого панели. В противном случае — не обновить содержимое области, пока не становится недействительным области с помощью другого метода.  
  
##  <a name="setpaneicon"></a>CMFCStatusBar::SetPaneIcon  
 Установите значок на панели строки состояния.  
  
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
 Указывает дескриптор значок, чтобы задать в качестве области изображения.  
  
 [in] `bUpdate`  
 Признак немедленного обновления содержимого панели.  
  
 [in] `hBmp`  
 Указывает дескриптор точечного рисунка в качестве области изображения.  
  
 [in] `clrTransparent`  
 Задает прозрачный цвет изображения, `hBmp` указывает.  
  
### <a name="remarks"></a>Примечания  
 Можно передать либо `HICON` или `HBITMAP` вместе с прозрачный цвет для области изображения. Если вы не хотите больше изображение, передайте `NULL` значение как дескриптор изображения.  
  
 Если любой запущенная анимация, [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) имеет значение, анимация будет остановлена.  
  
##  <a name="setpaneinfo"></a>CMFCStatusBar::SetPaneInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="setpaneprogress"></a>CMFCStatusBar::SetPaneProgress  
 Задайте текущий индикатор выполнения индикатора хода выполнения для указанной области.  
  
```  
void SetPaneProgress(
    int nIndex,  
    long nCurr,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс области, для которого требуется обновить индикатор выполнения.  
  
 [in] `nCurr`  
 Указывает текущее значение индикатора хода выполнения.  
  
 [in] `bUpdate`  
 Указывает, следует ли немедленно обновлять области.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, когда требуется обновить индикатор выполнения для индикатора в указанной области.  
  
 Чтобы использовать эту функцию для данной области, необходимо вызвать [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) первой.  
  
##  <a name="setpanestyle"></a>CMFCStatusBar::SetPaneStyle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 [in] `nStyle`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpanetext"></a>CMFCStatusBar::SetPaneText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="setpanetextcolor"></a>CMFCStatusBar::SetPaneTextColor  
 Задает цвет текста в указанной области.  
  
```  
void SetPaneTextColor(
    int nIndex,  
    COLORREF clrText=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс области, к которому вы хотите назначить новый цвет текста.  
  
 [in] `clrText`  
 Определяет цвет текста.  
  
 [in] `bUpdate`  
 Если `TRUE`, немедленного обновления содержимого панели. В противном случае — не обновить содержимое области, пока не становится недействительным области с помощью другого метода.  
  
##  <a name="setpanewidth"></a>CMFCStatusBar::SetPaneWidth  
 Задайте ширину панели строки состояния.  
  
```  
void SetPaneWidth(
    int nIndex,  
    int cx);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Индекс панели строки состояния, для которого задается новое значение ширины.  
  
 [in] `cx`  
 Новая ширина панели строки состояния, в пикселях.  
  
##  <a name="settiptext"></a>CMFCStatusBar::SetTipText  
 Задайте текст подсказки панели строки состояния.  
  
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
 [CStatusBar-класс](../../mfc/reference/cstatusbar-class.md)

