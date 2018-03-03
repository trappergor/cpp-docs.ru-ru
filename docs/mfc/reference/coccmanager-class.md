---
title: "Класс COccManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
dev_langs:
- C++
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ffa16b7a210bc53f178e3ec437aefb6cede766a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coccmanager-class"></a>Класс COccManager
Управляет разными сайтами пользовательского элемента управления, реализованного объектами `COleControlContainer` и `COleControlSite` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COccManager::CreateContainer](#createcontainer)|Создает **COleContainer** объекта.|  
|[COccManager::CreateDlgControls](#createdlgcontrols)|Создает элементы управления ActiveX, размещенных в связанных `COleContainer` объекта.|  
|[COccManager::CreateSite](#createsite)|Создает объект `COleClientSite`.|  
|[COccManager::GetDefBtnCode](#getdefbtncode)|Извлекает код кнопкой по умолчанию.|  
|[COccManager::IsDialogMessage](#isdialogmessage)|Определяет целевой объект диалогового окна сообщения.|  
|[COccManager::IsLabelControl](#islabelcontrol)|Определяет, является ли указанный элемент управления, элемент управления label.|  
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|Определяет, соответствует ли текущий назначенный назначенный указанного элемента управления.|  
|[COccManager::OnEvent](#onevent)|Предпринимается попытка обработки указанного события.|  
|[COccManager::PostCreateDialog](#postcreatedialog)|Освобождает ресурсы, выделенные во время создания диалогового окна.|  
|[COccManager::PreCreateDialog](#precreatedialog)|Обрабатывает шаблона диалогового окна для элементов управления ActiveX.|  
|[COccManager::SetDefaultButton](#setdefaultbutton)|Переключает состояние указанного элемента управления по умолчанию.|  
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Разделяет все существующие элементы управления ActiveX из стандартных элементов управления в шаблоне указанное диалоговое окно.|  
  
## <a name="remarks"></a>Примечания  
 Базовый класс **CNoTrackObject**, недокументированные базовый класс (находится в AFXTLS. (H). Предназначен для использования платформой MFC, классы, производные от **CNoTrackObject** класса будут исключены из обнаружения утечек памяти. Не рекомендуется является производным непосредственно от **CNoTrackObject**.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CNoTrackObject`  
  
 `COccManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxocc.h  
  
##  <a name="createcontainer"></a>COccManager::CreateContainer  
 Вызывается платформой для создания контейнера элемента управления.  
  
```  
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на объект window, связанные с контейнером пользовательский узел.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданном контейнере; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о создании настраиваемых сайтов см. в разделе [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).  
  
##  <a name="createdlgcontrols"></a>COccManager::CreateDlgControls  
 Вызывайте эту функцию для создания элементов управления ActiveX, определяемое `pOccDialogInfo` параметра.  
  
```  
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    LPCTSTR lpszResourceName,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

 
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    void* lpResource,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndParent*  
 Указатель на родительский объект объекта диалогового окна.  
  
 `lpszResourceName`  
 Имя создаваемого ресурса.  
  
 `pOccDialogInfo`  
 Указатель шаблона диалогового окна, используемый для создания объекта диалогового окна.  
  
 `lpResource`  
 Указатель на ресурс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления был создан успешно. в противном случае значение равно нулю.  
  
##  <a name="createsite"></a>COccManager::CreateSite  
 Вызывается платформой для создания сайта элемента управления, размещенного в качестве контейнера, на который указывает `pCtrlCont`.  
  
```  
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Параметры  
 `pCtrlCont`  
 Указатель на размещение на новом сайте управления контейнера элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный элемент управления узла.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию для создания пользовательского элемента управления сайта, с помощью вашей [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-производного класса.  
  
 Каждый контейнер элемента управления может размещаться несколько узлов. Создайте дополнительные сайты с несколькими вызовами в `CreateSite`.  
  
##  <a name="getdefbtncode"></a>COccManager::GetDefBtnCode  
 Эта функция вызывается для определения, является ли элемент управления является кнопкой по умолчанию.  
  
```  
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Объект window, содержащий элемент управления button.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений:  
  
- **DLGC_DEFPUSHBUTTON** элемент управления является кнопкой по умолчанию в диалоговом окне.  
  
- **DLGC_UNDEFPUSHBUTTON** управления не является кнопкой по умолчанию в диалоговом окне.  
  
- **0** элемент управления не кнопки.  
  
##  <a name="isdialogmessage"></a>COccManager::IsDialogMessage  
 Вызывается платформой для определения сообщение предназначено для указанного диалогового и, если это так, обрабатывает сообщение.  
  
```  
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndDlg*  
 Указатель на целевом диалогового окна сообщения.  
  
 `lpMsg`  
 Указатель на `MSG` структуру, содержащую сообщение для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение обработано; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Поведение по умолчанию `IsDialogMessage` — для проверки сообщений клавиатуры и преобразовывать их в выбранных элементов для соответствующего диалогового окна. Например при нажатии клавиши TAB выбирает следующий элемент управления или группы элементов управления.  
  
 Переопределите эту функцию, чтобы обеспечить пользовательское поведение для отправки сообщений на указанное диалоговое окно.  
  
##  <a name="islabelcontrol"></a>COccManager::IsLabelControl  
 Вызывайте эту функцию, чтобы определить, является ли указанный элемент управления, элемент управления label.  
  
```  
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);  
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащее элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления label; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления label — который действует как метка для любой элемент управления далее в этом упорядочении.  
  
##  <a name="ismatchingmnemonic"></a>COccManager::IsMatchingMnemonic  
 Эта функция вызывается для определения текущего назначенный соответствия, представленного элементом управления.  
  
```  
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,  
    LPMSG lpMsg);

 
static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащее элемент управления.  
  
 `lpMsg`  
 Указатель на сообщение, содержащее мнемоническую.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если назначенный совпадает с элементом управления; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onevent"></a>COccManager::OnEvent  
 Вызывается платформой для обработки указанного события.  
  
```  
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,  
    UINT idCtrl,  
    AFX_EVENT* pEvent,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Параметры  
 *pCmdTarget*  
 Указатель на `CCmdTarget` объекта при попытке обработать событие  
  
 `idCtrl`  
 Идентификатор ресурса управления.  
  
 `pEvent`  
 Обрабатываемого события.  
  
 `pHandlerInfo`  
 В противном случае **NULL**, `OnEvent` заполняет **pTarget** и **pmf** члены **AFX_CMDHANDLERINFO** структуры вместо Отправка команды. Как правило, этот параметр должен быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если событие было обработано, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки процесса обработки событий по умолчанию.  
  
##  <a name="precreatedialog"></a>COccManager::PreCreateDialog  
 Вызывается платформой для обработки шаблона диалогового окна для элементов управления ActiveX, перед созданием фактическое диалоговым окном.  
  
```  
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,  
    const DLGTEMPLATE* pOrigTemplate);
```  
  
### <a name="parameters"></a>Параметры  
 `pOccDialogInfo`  
 **_AFX_OCC_DIALOG_INFO** структуру, содержащую сведения о шаблоне диалогового окна и элементы управления ActiveX, который размещен в диалоговом окне.  
  
 *pOrigTemplate*  
 Указатель шаблона диалогового окна для использования при создании диалоговым окном.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на структуру шаблона диалогового окна, используемую для создания диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Поведение по умолчанию вызывает метод `SplitDialogTemplate`, определение того, если существуют элементы управления ActiveX для управления присутствует, а затем возвращает шаблона итоговые диалогового окна.  
  
 Переопределите эту функцию для настройки процесса создания диалоговое окно, размещение элементов управления ActiveX.  
  
##  <a name="postcreatedialog"></a>COccManager::PostCreateDialog  
 Вызывается платформой для освобождения памяти, выделенной для шаблона диалогового окна.  
  
```  
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `pOccDialogInfo`  
 **_AFX_OCC_DIALOG_INFO** структуру, содержащую сведения о шаблоне диалогового окна и элементы управления ActiveX, который размещен в диалоговом окне.  
  
### <a name="remarks"></a>Примечания  
 Эта память была выделена с помощью вызова `SplitDialogTemplate`и был использован для любой размещенные элементы управления ActiveX в диалоговом окне.  
  
 Переопределите эту функцию для настройки процесса очистки все ресурсы, используемые объект диалогового окна.  
  
##  <a name="setdefaultbutton"></a>COccManager::SetDefaultButton  
 Вызывайте эту функцию, чтобы задать элемент управления кнопкой по умолчанию.  
  
```  
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,  
    BOOL bDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащее элемент управления.  
  
 `bDefault`  
 Ненулевое значение, если элемент управления должен стать кнопки по умолчанию. в противном случае значение равно нулю.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Элемент управления должен иметь **OLEMISC_ACTSLIKEBUTTON** состояние бит. Дополнительные сведения о **OLEMISC, ПОЗВОЛЯЯ** флаги, в разделе [OLEMISC, ПОЗВОЛЯЯ](http://msdn.microsoft.com/library/windows/desktop/ms678497) раздел в Windows SDK.  
  
##  <a name="splitdialogtemplate"></a>COccManager::SplitDialogTemplate  
 Вызывается платформой для разделения элементов управления ActiveX из стандартных элементов управления диалогового окна.  
  
```  
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,  
    DLGITEMTEMPLATE** ppOleDlgItems);
```  
  
### <a name="parameters"></a>Параметры  
 `pTemplate`  
 Указатель шаблона диалогового окна, которое необходимо проверить.  
  
 `ppOleDlgItems`  
 Список указателей на элементов диалоговых окон, элементов управления ActiveX.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на структуру шаблона диалогового окна, содержащий только элементы управления, не являющееся. Если нет элементов управления ActiveX, **NULL** возвращается.  
  
### <a name="remarks"></a>Примечания  
 Найденные элементы управления ActiveX, выполняется анализ шаблона, и создается новый шаблон, содержащий только не-элементы управления ActiveX. Элементы управления ActiveX, найденные во время этого процесса добавляются `ppOleDlgItems`.  
  
 Если в шаблоне, элементы управления ActiveX не **NULL** возвращается *.*  
  
> [!NOTE]
>  Память, выделенная для нового шаблона освобождается в `PostCreateDialog` функции.  
  
 Переопределите эту функцию для настройки этого процесса.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleControlSite](../../mfc/reference/colecontrolsite-class.md)   
 [Класс COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)
