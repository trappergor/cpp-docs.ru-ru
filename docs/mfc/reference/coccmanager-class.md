---
title: "Класс COccManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COccManager
dev_langs:
- C++
helpviewer_keywords:
- custom controls [MFC], sites
- COccManager class
- CNoTrackObject class
- ActiveX control containers [C++], control site
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: 20
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
ms.openlocfilehash: 14a75c491a7061d921d6c0c250c6224f4e7d2f04
ms.lasthandoff: 02/24/2017

---
# <a name="coccmanager-class"></a>Класс COccManager
Управляет разными сайтами пользовательского элемента управления, реализованного объектами `COleControlContainer` и `COleControlSite` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COccManager::CreateContainer](#createcontainer)|Создает **COleContainer** объекта.|  
|[COccManager::CreateDlgControls](#createdlgcontrols)|Создает элементы управления ActiveX, размещенных в связанных `COleContainer` объекта.|  
|[COccManager::CreateSite](#createsite)|Создает объект `COleClientSite`.|  
|[COccManager::GetDefBtnCode](#getdefbtncode)|Извлекает код кнопки по умолчанию.|  
|[COccManager::IsDialogMessage](#isdialogmessage)|Определяет целевой объект диалогового окна сообщения.|  
|[COccManager::IsLabelControl](#islabelcontrol)|Определяет, является ли указанный элемент управления элемент управления label.|  
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|Определяет, соответствует ли текущий назначенный назначенный указанного элемента управления.|  
|[COccManager::OnEvent](#onevent)|Предпринимается попытка обработки указанного события.|  
|[COccManager::PostCreateDialog](#postcreatedialog)|Освобождает ресурсы, выделенные во время создания диалогового окна.|  
|[COccManager::PreCreateDialog](#precreatedialog)|Обрабатывает шаблона диалогового окна для элементов управления ActiveX.|  
|[COccManager::SetDefaultButton](#setdefaultbutton)|Переключает состояние указанного элемента управления по умолчанию.|  
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Все существующие элементы управления ActiveX отделяет от стандартных элементов управления в шаблоне указанное диалоговое окно.|  
  
## <a name="remarks"></a>Примечания  
 Базовый класс **CNoTrackObject**, недокументированные базовый класс (находится в AFXTLS. (H). Предназначены для использования платформой MFC, классы, производные от **CNoTrackObject** класса освобождаются от обнаружения утечек памяти. Не рекомендуется создавать производных непосредственно из **CNoTrackObject**.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CNoTrackObject`  
  
 `COccManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxocc.h  
  
##  <a name="a-namecreatecontainera--coccmanagercreatecontainer"></a><a name="createcontainer"></a>COccManager::CreateContainer  
 Вызывается платформой для создания контейнера элемента управления.  
  
```  
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на объект окна, связанный с контейнером пользовательского узла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный контейнер; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о создании пользовательских узлов см. в разделе [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).  
  
##  <a name="a-namecreatedlgcontrolsa--coccmanagercreatedlgcontrols"></a><a name="createdlgcontrols"></a>COccManager::CreateDlgControls  
 Эта функция вызывается для создания элементов управления ActiveX, определяемое `pOccDialogInfo` параметр.  
  
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
 Указатель на родительский объект диалогового окна.  
  
 `lpszResourceName`  
 Имя создаваемого ресурса.  
  
 `pOccDialogInfo`  
 Указатель шаблона диалогового окна, используемый для создания объекта диалогового окна.  
  
 `lpResource`  
 Указатель на ресурс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления был создан успешно. в противном случае — нуль.  
  
##  <a name="a-namecreatesitea--coccmanagercreatesite"></a><a name="createsite"></a>COccManager::CreateSite  
 Вызывается платформой для создания узла управления, размещенные в качестве контейнера, на который указывает `pCtrlCont`.  
  
```  
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Параметры  
 `pCtrlCont`  
 Указатель на размещение нового узла управления контейнера элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на узел вновь созданного элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию для создания пользовательского элемента управления сайта, используя вашей [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-производного класса.  
  
 Каждый контейнер элемента управления может размещаться несколько узлов. Создайте дополнительные сайты с несколькими вызовами в `CreateSite`.  
  
##  <a name="a-namegetdefbtncodea--coccmanagergetdefbtncode"></a><a name="getdefbtncode"></a>COccManager::GetDefBtnCode  
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
  
- **DLGC_UNDEFPUSHBUTTON** элемент управления не является кнопкой по умолчанию в диалоговом окне.  
  
- **0** элемент управления не является кнопкой.  
  
##  <a name="a-nameisdialogmessagea--coccmanagerisdialogmessage"></a><a name="isdialogmessage"></a>COccManager::IsDialogMessage  
 Вызывается платформой для определения ли сообщение предназначено для указанного диалогового и, если это так, обрабатывает сообщение.  
  
```  
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndDlg*  
 Указатель на окно намеченного сообщения.  
  
 `lpMsg`  
 Указатель на `MSG` структуру, содержащую сообщения для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение обработано; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `IsDialogMessage` — для проверки сообщений клавиатуры и преобразовывать их в выбранных элементов для соответствующего диалогового окна. Например при нажатии клавиши TAB выбирает следующий элемент управления или группы элементов управления.  
  
 Переопределите эту функцию, чтобы обеспечить пользовательское поведение для отправки сообщений на указанное диалоговое окно.  
  
##  <a name="a-nameislabelcontrola--coccmanagerislabelcontrol"></a><a name="islabelcontrol"></a>COccManager::IsLabelControl  
 Вызывайте эту функцию, чтобы определить, является ли указанный элемент управления элемент управления label.  
  
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
 Элемент управления label, которое действует как метка для любой элемент управления является следующим в порядок.  
  
##  <a name="a-nameismatchingmnemonica--coccmanagerismatchingmnemonic"></a><a name="ismatchingmnemonic"></a>COccManager::IsMatchingMnemonic  
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
 Указатель на сообщение, содержащее мнемонический символ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если назначенный соответствует элементу управления; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameoneventa--coccmanageronevent"></a><a name="onevent"></a>COccManager::OnEvent  
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
 Указатель на `CCmdTarget` объект попытка обработать событие  
  
 `idCtrl`  
 Идентификатор ресурса управления.  
  
 `pEvent`  
 Обрабатываемого события.  
  
 `pHandlerInfo`  
 Если не **NULL**, `OnEvent` заполняет **pTarget** и **pmf** члены **AFX_CMDHANDLERINFO** структуры вместо отправки команды. Как правило, этот параметр должен быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если событие было обработано, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки процесса обработки событий по умолчанию.  
  
##  <a name="a-nameprecreatedialoga--coccmanagerprecreatedialog"></a><a name="precreatedialog"></a>COccManager::PreCreateDialog  
 Вызывается платформой для обработки шаблона диалогового окна для элементов управления ActiveX перед созданием фактическое диалоговым окном.  
  
```  
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,  
    const DLGTEMPLATE* pOrigTemplate);
```  
  
### <a name="parameters"></a>Параметры  
 `pOccDialogInfo`  
 **_AFX_OCC_DIALOG_INFO** структура, содержащая сведения о шаблоне диалогового окна и элементы управления ActiveX, размещенных в диалоговом окне.  
  
 *pOrigTemplate*  
 Указатель для использования в диалоговом окне Создание шаблона диалогового окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на структуру шаблона диалоговое окно используется для создания диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию выполняется вызов `SplitDialogTemplate`, определение, если существуют элементы управления ActiveX определяет, присутствует, а затем возвращает результирующее диалоговое окно шаблона.  
  
 Переопределите эту функцию для настройки процесса создания диалогового окна, размещение элементов управления ActiveX.  
  
##  <a name="a-namepostcreatedialoga--coccmanagerpostcreatedialog"></a><a name="postcreatedialog"></a>COccManager::PostCreateDialog  
 Вызывается платформой для освобождения памяти, выделенной для шаблона диалогового окна.  
  
```  
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `pOccDialogInfo`  
 **_AFX_OCC_DIALOG_INFO** структура, содержащая сведения о шаблоне диалогового окна и элементы управления ActiveX, размещенных в диалоговом окне.  
  
### <a name="remarks"></a>Примечания  
 Эта память была выделена путем вызова `SplitDialogTemplate`и был использован для любой размещаемые элементы управления ActiveX в диалоговом окне.  
  
 Переопределите эту функцию для настройки процесса очистки все ресурсы, используемые объект диалогового окна.  
  
##  <a name="a-namesetdefaultbuttona--coccmanagersetdefaultbutton"></a><a name="setdefaultbutton"></a>COccManager::SetDefaultButton  
 Вызывайте эту функцию, чтобы задать элемент управления как кнопка по умолчанию.  
  
```  
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,  
    BOOL bDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащее элемент управления.  
  
 `bDefault`  
 Ненулевое значение, если элемент управления должен стать кнопка по умолчанию; в противном случае — нуль.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Элемент управления должен иметь **OLEMISC_ACTSLIKEBUTTON** бит состояния. Дополнительные сведения о **OLEMISC, ПОЗВОЛЯЯ** флаги, в разделе [OLEMISC, ПОЗВОЛЯЯ](http://msdn.microsoft.com/library/windows/desktop/ms678497) раздел в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesplitdialogtemplatea--coccmanagersplitdialogtemplate"></a><a name="splitdialogtemplate"></a>COccManager::SplitDialogTemplate  
 Вызывается платформой для разделения элементов управления ActiveX из общих элементов управления диалогового окна.  
  
```  
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,  
    DLGITEMTEMPLATE** ppOleDlgItems);
```  
  
### <a name="parameters"></a>Параметры  
 `pTemplate`  
 Указатель шаблона диалогового окна, которое необходимо проверить.  
  
 `ppOleDlgItems`  
 Список указателей на элементов диалоговых окон, являющихся элементами управления ActiveX.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на структуру шаблона диалогового окна, содержащую только те элементы не ActiveX. Если присутствуют элементы управления ActiveX не **NULL** возвращается.  
  
### <a name="remarks"></a>Примечания  
 Найденные элементы управления ActiveX, выполняется анализ шаблона, создается новый шаблон, содержащий только не-элементы управления ActiveX. Добавляются элементы управления ActiveX, обнаруженных в ходе этого процесса `ppOleDlgItems`.  
  
 Если в шаблоне нет элементы управления ActiveX **NULL** возвращается *.*  
  
> [!NOTE]
>  Память, выделенная для нового шаблона освобождается в `PostCreateDialog` функции.  
  
 Переопределите эту функцию для настройки этого процесса.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleControlSite](../../mfc/reference/colecontrolsite-class.md)   
 [Класс COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)

