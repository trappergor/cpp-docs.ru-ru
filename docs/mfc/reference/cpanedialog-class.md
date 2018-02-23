---
title: "Класс CPaneDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
dev_langs:
- C++
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e247d1d824d710cfa9588a01d73e1ca611d77ed
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2018
---
# <a name="cpanedialog-class"></a>Класс CPaneDialog
`CPaneDialog` Класс поддерживает безрежимные, Закрепляемое окно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|Конструктор по умолчанию.|  
|`CPaneDialog::~CPaneDialog`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPaneDialog::Create](#create)|Создает закрепляемую диалоговое окно и прикрепляет его к `CPaneDialog` объекта.|  
|`CPaneDialog::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CPaneDialog::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Обрабатывает [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) сообщения. (Переопределяет `CBasePane::HandleInitDialog`.)|  
|`CPaneDialog::OnEraseBkgnd`|Обрабатывает [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) сообщения. (Переопределяет [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|  
|`CPaneDialog::OnLButtonDblClk`|Обрабатывает [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) сообщения. (Переопределяет [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|  
|`CPaneDialog::OnLButtonDown`|Обрабатывает [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) сообщения. (Переопределяет [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|  
|`CPaneDialog::OnUpdateCmdUI`|Вызывается платформой для обновления диалогового окна. (Переопределяет [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|`CPaneDialog::OnWindowPosChanging`|Обрабатывает [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) сообщения. (Переопределяет [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Задает шаблон для диалогового окна, представляет собой контейнер элемента управления OLE.|  
  
## <a name="remarks"></a>Примечания  
 Создать `CPaneDialog` объекта в два этапа. Во-первых можно создавайте объект в коде. Во-вторых, вызовите [CPaneDialog::Create](#create). Необходимо указать действительный ресурс шаблона или шаблон, идентификатор и передать указатель на родительское окно. В противном случае происходит сбой в процессе создания. Диалоговое окно необходимо указать стиль WS_CHILD и WS_VISIBLE. Рекомендуется также указать стили WS_CLIPCHILDREN и WS_CLIPSIBLINGS. Дополнительные сведения см. в разделе [стили окна](styles-used-by-mfc.md#window-styles).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpanedialog.h  
  
##  <a name="create"></a>  CPaneDialog::Create  
 Создает закрепления диалоговое окно и прикрепляет его к `CPaneDialog` объекта.  
  
```  
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID,  
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

 
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszWindowName`  
 Имя диалогового окна закрепления.  
  
 [in] `pParentWnd`  
 Указатель на родительское окно.  
  
 [in] `bHasGripper`  
 `TRUE` для создания закрепления диалогового окна с заголовком (захвата); в противном случае `FALSE`.  
  
 [in] `lpszTemplateName`  
 Имя ресурса шаблона диалогового окна.  
  
 [in] `nStyle`  
 В стиле Windows.  
  
 [in] `nID`  
 Идентификатор элемента управления.  
  
 [in] `nIDTemplate`  
 Идентификатор ресурса шаблона диалогового окна.  
  
 [in] `dwTabbedStyle`  
 Стиль окна с вкладками, происходящий, когда пользователь перетаскивает другую панель управления в заголовок данной панели управления. Значение по умолчанию — `AFX_CBRS_REGULAR_TABS`. Дополнительные сведения см. в разделе «Примечания» [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) метод.  
  
 [in] `dwControlBarStyle`  
 Стиль дополнительные атрибуты. Значение по умолчанию — `AFX_DEFAULT_DOCKING_PANE_STYLE`. Дополнительные сведения см. в разделе «Примечания» [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Create` метод `CPaneDialog` класса. Данный пример является частью [задать размер области пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog  
 Обрабатывает [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) сообщения.  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `wParam`  
 Дескриптор элемента управления, получающего фокус клавиатуры по умолчанию.  
  
 [in] `lParam`  
 Задает дополнительную инициализацию данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае `FALSE`. Кроме того `TRUE` устанавливает фокус на элементе управления, определяемое `wParam` параметра; `FALSE` не позволяет установить фокус клавиатуры по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует этот метод для инициализации элементов управления и внешний вид диалогового окна. Этот метод вызывается платформой перед отображается диалоговое окно.  
  
##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo  
 Задает шаблон для диалогового окна, представляет собой контейнер элемента управления OLE.  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pOccDialogInfo`  
 Указатель на шаблон диалогового окна, используемый для создания объекта поле диалогового окна. Значение этого параметра впоследствии передается в [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод поддерживает [COccManager](../../mfc/reference/coccmanager-class.md) класс, который управляет узлов элемента управления OLE и элементы управления ActiveX. Структура _AFX_OCC_DIALOG_INFO определяется в файле заголовка afxocc.h.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)   
 [Стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles)



