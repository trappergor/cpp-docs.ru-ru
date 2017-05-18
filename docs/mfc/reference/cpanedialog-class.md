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
- CPaneDialog::OnLButtonDblClk method
- CPaneDialog::OnLButtonDown method
- CPaneDialog::CreateObject method
- CPaneDialog::OnUpdateCmdUI method
- CPaneDialog constructor
- CPaneDialog::OnEraseBkgnd method
- CPaneDialog class
- CPaneDialog::OnWindowPosChanging method
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 27
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 85c7e338382758dd809fb770c5ab14860e362da8
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cpanedialog-class"></a>Класс CPaneDialog
`CPaneDialog` Класс поддерживает безрежимные Закрепляемое диалоговое окно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|Конструктор по умолчанию.|  
|`CPaneDialog::~CPaneDialog`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPaneDialog::Create](#create)|Закрепляемое окно создает и присоединяет его к `CPaneDialog` объекта.|  
|`CPaneDialog::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CPaneDialog::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Обрабатывает [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) сообщение. (Переопределяет `CBasePane::HandleInitDialog`.)|  
|`CPaneDialog::OnEraseBkgnd`|Обрабатывает [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) сообщение. (Переопределяет [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|  
|`CPaneDialog::OnLButtonDblClk`|Обрабатывает [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) сообщений. (Переопределяет [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|  
|`CPaneDialog::OnLButtonDown`|Обрабатывает [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) сообщений. (Переопределяет [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|  
|`CPaneDialog::OnUpdateCmdUI`|Вызывается платформой для обновления диалогового окна. (Переопределяет [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|`CPaneDialog::OnWindowPosChanging`|Обрабатывает [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) сообщений. (Переопределяет [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Указывает шаблон для диалогового окна, — это контейнер элемента управления OLE.|  
  
## <a name="remarks"></a>Примечания  
 Создать `CPaneDialog` объекта в два этапа. Во-первых можно создавайте объект в коде. Во-вторых, вызовите [CPaneDialog::Create](#create). Необходимо указать допустимый ресурс шаблона или шаблон, идентификатор и передать указатель на родительское окно. В противном случае — сбой в процессе создания. Диалоговое окно необходимо указать стиль WS_CHILD и WS_VISIBLE. Рекомендуется также указать стили WS_CLIPCHILDREN и WS_CLIPSIBLINGS. Дополнительные сведения см. в разделе [стили окна](window-styles.md).  
  
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
  
##  <a name="create"></a>CPaneDialog::Create  
 Диалоговое окно закрепления создает и присоединяет его к `CPaneDialog` объекта.  
  
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
 Указывает для родительского окна.  
  
 [in] `bHasGripper`  
 `TRUE`для создания закрепления диалоговое окно с заголовком (захвата); в противном случае — `FALSE`.  
  
 [in] `lpszTemplateName`  
 Имя ресурса шаблона диалогового окна.  
  
 [in] `nStyle`  
 В стиле Windows.  
  
 [in] `nID`  
 Идентификатор элемента управления.  
  
 [in] `nIDTemplate`  
 Идентификатор ресурса шаблона диалогового окна.  
  
 [in] `dwTabbedStyle`  
 Стиль окна с вкладками, когда пользователь перетаскивает другую панель управления в заголовок панели управления. Значение по умолчанию — `AFX_CBRS_REGULAR_TABS`. Дополнительные сведения см. в разделе «Примечания» [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) метод.  
  
 [in] `dwControlBarStyle`  
 Стиль дополнительные атрибуты. Значение по умолчанию — `AFX_DEFAULT_DOCKING_PANE_STYLE`. Дополнительные сведения см. в разделе «Примечания» [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Create` метод `CPaneDialog` класса. Этот пример является частью [задать размер области пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize&#2;](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize&#3;](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="handleinitdialog"></a>CPaneDialog::HandleInitDialog  
 Обрабатывает [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) сообщение.  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `wParam`  
 Дескриптор элемента управления, который должен получить фокус клавиатуры по умолчанию.  
  
 [in] `lParam`  
 Задает дополнительную инициализацию данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае — `FALSE`. Кроме того `TRUE` устанавливает фокус на элементе управления, определяемое `wParam` параметр; `FALSE` не позволяет установить фокус клавиатуры по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует этот метод для инициализации элементов управления и внешний вид диалогового окна. Платформа вызывает этот метод до отображения диалоговое окно.  
  
##  <a name="setoccdialoginfo"></a>CPaneDialog::SetOccDialogInfo  
 Указывает шаблон для диалогового окна, — это контейнер элемента управления OLE.  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pOccDialogInfo`  
 Указатель на шаблон диалогового окна, используемый для создания объект диалогового окна. Значение этого параметра впоследствии передается в [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод поддерживает [COccManager](../../mfc/reference/coccmanager-class.md) класс, который управляет узлов элемента управления OLE и элементы управления ActiveX. Структура _AFX_OCC_DIALOG_INFO определяется в файле заголовка afxocc.h.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)   
 [Стили окна](../../mfc/reference/window-styles.md)




