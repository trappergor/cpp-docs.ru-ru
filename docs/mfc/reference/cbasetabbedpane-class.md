---
title: Класс CBaseTabbedPane | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::AddTab
- AFXBASETABBEDPANE/CBaseTabbedPane::AllowDestroyEmptyTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::ApplyRestoredTabInfo
- AFXBASETABBEDPANE/CBaseTabbedPane::CanFloat
- AFXBASETABBEDPANE/CBaseTabbedPane::CanSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::ConvertToTabbedDocument
- AFXBASETABBEDPANE/CBaseTabbedPane::DetachPane
- AFXBASETABBEDPANE/CBaseTabbedPane::EnableSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::FillDefaultTabsOrderArray
- AFXBASETABBEDPANE/CBaseTabbedPane::FindBarByTabNumber
- AFXBASETABBEDPANE/CBaseTabbedPane::FindPaneByID
- AFXBASETABBEDPANE/CBaseTabbedPane::FloatTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetDefaultTabsOrder
- AFXBASETABBEDPANE/CBaseTabbedPane::GetFirstVisibleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetMinSize
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneIcon
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneList
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabArea
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::GetUnderlyingWindow
- AFXBASETABBEDPANE/CBaseTabbedPane::GetVisibleTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::HasAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::IsHideSingleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::RecalcLayout
- AFXBASETABBEDPANE/CBaseTabbedPane::RemovePane
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoDestroy
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::ShowTab
dev_langs:
- C++
helpviewer_keywords:
- CBaseTabbedPane [MFC], AddTab
- CBaseTabbedPane [MFC], AllowDestroyEmptyTabbedPane
- CBaseTabbedPane [MFC], ApplyRestoredTabInfo
- CBaseTabbedPane [MFC], CanFloat
- CBaseTabbedPane [MFC], CanSetCaptionTextToTabName
- CBaseTabbedPane [MFC], ConvertToTabbedDocument
- CBaseTabbedPane [MFC], DetachPane
- CBaseTabbedPane [MFC], EnableSetCaptionTextToTabName
- CBaseTabbedPane [MFC], FillDefaultTabsOrderArray
- CBaseTabbedPane [MFC], FindBarByTabNumber
- CBaseTabbedPane [MFC], FindPaneByID
- CBaseTabbedPane [MFC], FloatTab
- CBaseTabbedPane [MFC], GetDefaultTabsOrder
- CBaseTabbedPane [MFC], GetFirstVisibleTab
- CBaseTabbedPane [MFC], GetMinSize
- CBaseTabbedPane [MFC], GetPaneIcon
- CBaseTabbedPane [MFC], GetPaneList
- CBaseTabbedPane [MFC], GetTabArea
- CBaseTabbedPane [MFC], GetTabsNum
- CBaseTabbedPane [MFC], GetUnderlyingWindow
- CBaseTabbedPane [MFC], GetVisibleTabsNum
- CBaseTabbedPane [MFC], HasAutoHideMode
- CBaseTabbedPane [MFC], IsHideSingleTab
- CBaseTabbedPane [MFC], RecalcLayout
- CBaseTabbedPane [MFC], RemovePane
- CBaseTabbedPane [MFC], SetAutoDestroy
- CBaseTabbedPane [MFC], SetAutoHideMode
- CBaseTabbedPane [MFC], ShowTab
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 412010f7e8599ab9a97ea5a4e5cab55fca6051a0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213860"
---
# <a name="cbasetabbedpane-class"></a>Класс CBaseTabbedPane
Расширяет функциональность [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) для поддержки создания окон с вкладками.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBaseTabbedPane::AddTab](#addtab)|Добавляет новую вкладку области с вкладками.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Указывает, можно ли уничтожить пустой области с вкладками.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Применяет параметры вкладки, которые загружаются из реестра, для области с вкладками.|  
|[CBaseTabbedPane::CanFloat](#canfloat)|Определяет, может ли перемещаться области. (Переопределяет [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Определяет, должен ли заголовок для области с вкладками отображать тот же текст в качестве активной вкладки.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(Переопределяет [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|  
|[CBaseTabbedPane::DetachPane](#detachpane)|Преобразует один или несколько закрепляемых областей для документов с вкладками MDI.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Включает или отключает возможность синхронизировать текст заголовка с текстом метки на активной вкладке области с вкладками.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|Восстанавливает состояние по умолчанию внутренней последовательности.|  
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Возвращает область, в которой находится на вкладке при вкладке идентифицируется по клавише tab (с нуля).|  
|||  
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|Возвращает область, в которой определяется идентификатором области.|  
|[CBaseTabbedPane::FloatTab](#floattab)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Возвращает значение по умолчанию порядок вкладок на панели.|  
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|Извлекает указатель на первой вкладке отображается.|  
|[CBaseTabbedPane::GetMinSize](#getminsize)|Получает минимальный поддерживаемый размер для области. (Переопределяет [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Возвращает дескриптор для значка панели. (Переопределяет [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|  
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Возвращает список панелей, содержащихся в области с вкладками.|  
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Возвращает ограничивающих прямоугольников для верхней и нижней области вкладки.|  
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Возвращает количество вкладок в окне вкладку.|  
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Получает нижележащего окна (оболочку) вкладки.|  
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Возвращает количество отображаемых вкладок.|  
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|Определяет, можно ли переключить в режим автоматического скрытия панели с вкладками.|  
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|Определяет, скрыт ли панель с вкладками, если только одна вкладка отображается.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Используется внутренним образом во время сериализации.|  
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Повторно вычисляет сведения о структуре для области. (Переопределяет [CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CBaseTabbedPane::RemovePane](#removepane)|Удаляет панель из панели с вкладками.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Используется внутренним образом во время сериализации.|  
|`CBaseTabbedPane::Serialize`|(Переопределяет [CDockablePane::Serialize](https://msdn.microsoft.com/09787e59-e446-4e76-894b-206d303dcfd6).)|  
|`CBaseTabbedPane::SerializeTabWindow`|Используется внутренним образом во время сериализации.|  
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Определяет, автоматическое удаление панели элементов управления с вкладками.|  
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Переключает область закрепления между отображается и режим автоматического скрытия. (Переопределяет [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|  
|[CBaseTabbedPane::ShowTab](#showtab)|Показывает или скрывает вкладки.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является абстрактным классом и не может быть создан. Она реализует службы, которые являются общими для всех видов панели с вкладками.  
  
 В настоящее время библиотека включает два класса производный области с вкладками: [класс CTabbedPane](../../mfc/reference/ctabbedpane-class.md) и [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Объект `CBaseTabbedPane` объект оболочкой для указателя на [класс CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) объекта. [Класс CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) становится дочернее окно области с вкладками.  
  
 Дополнительные сведения о создании панели с вкладками, см. в разделе [класс CDockablePane](../../mfc/reference/cdockablepane-class.md), [класс CTabbedPane](../../mfc/reference/ctabbedpane-class.md), и [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 `CBaseTabbedPane`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxBaseTabbedPane.h  
  
##  <a name="addtab"></a>  CBaseTabbedPane::AddTab  
 Добавляет новую вкладку области с вкладками.  
  
```  
virtual BOOL AddTab(
    CWnd* pNewBar,  
    BOOL bVisible = TRUE,  
    BOOL bSetActive = TRUE,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out] *pNewBar*  
 Указатель на область для добавления. Этот указатель может перестать работать после вызова этого метода. Дополнительные сведения см. в разделе "Примечания".  
  
 [in] *bVisible*  
 Значение TRUE, чтобы сделать видимым. в противном случае — значение FALSE.  
  
 [in] *bSetActive*  
 Значение TRUE, чтобы отобразить вкладку активной вкладкой; в противном случае — значение FALSE.  
  
 [in] *bDetachable*  
 Значение TRUE, чтобы отобразить вкладку отделяемые; в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если область был успешно добавлен в виде вкладки и не был удален в процессе. Значение FALSE, если панель добавляемый объект типа `CBaseTabbedPane`. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы добавить область в виде новой вкладки в области с вкладками. Если *pNewBar* указывает на объект типа `CBaseTabbedPane`, все ее вкладки, копируются на панель с вкладками и затем *pNewBar* уничтожается. Таким образом *pNewBar* становится недопустимый указатель и не должны использоваться.  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CBaseTabbedPane::AllowDestroyEmptyTabbedPane  
 Указывает, можно ли уничтожить пустой области с вкладками.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если пустой области с вкладками можно уничтожить; в противном случае — значение FALSE. Реализация по умолчанию всегда возвращает значение TRUE.  
  
### <a name="remarks"></a>Примечания  
 Если пустой области с вкладками не может быть уничтожены, вместо этого framework скрывает область.  
  
##  <a name="applyrestoredtabinfo"></a>  CBaseTabbedPane::ApplyRestoredTabInfo  
 Загружает параметры табуляции из реестра и применяет их к области с вкладками.  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bUseTabIndexes*  
 Этот параметр используется внутренне платформой.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при его перезагрузке закрепления сведения о состоянии из реестра. Метод получает сведения о последовательности табуляции и имена вкладок для области с вкладками.  
  
##  <a name="canfloat"></a>  CBaseTabbedPane::CanFloat  
 Указывает, может перемещаться ли панель с вкладками.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если область может перемещаться; в противном случае — значение FALSE.  
  
##  <a name="cansetcaptiontexttotabname"></a>  CBaseTabbedPane::CanSetCaptionTextToTabName  
 Определяет, должен ли заголовок для области с вкладками отображать тот же текст в качестве активной вкладки.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если текст заголовка панели с вкладками имеет значение text активной вкладки; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Метод используется для определения ли текст отображаться дубликатов заголовок области с вкладками метка активной вкладки. Можно включить или отключить эту функцию, вызвав [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname).  
  
##  <a name="converttotabbeddocument"></a>  CBaseTabbedPane::ConvertToTabbedDocument  
 Преобразует один или несколько закрепляемых областей для документов с вкладками MDI.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bActiveTabOnly*  
 При преобразовании области с вкладками, укажите значение TRUE, чтобы преобразовать только к активной вкладке. Укажите значение FALSE, чтобы преобразовать все вкладки в области.  
  
##  <a name="detachpane"></a>  CBaseTabbedPane::DetachPane  
 Отсоединяет область от области с вкладками.  
  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBar*  
 Указатель на область для отсоединения.  
  
 [in] *bHide*  
 Логический параметр, указывает ли framework скрывает область, после ее отключении.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если платформа успешно отсоединяет область; Значение FALSE, если *pBar* имеет значение NULL или ссылается на область, в которой находится не на области с вкладками.  
  
### <a name="remarks"></a>Примечания  
 Платформы смещает области отсоединенного, если это возможно. Дополнительные сведения см. в разделе [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).  
  
##  <a name="enablesetcaptiontexttotabname"></a>  CBaseTabbedPane::EnableSetCaptionTextToTabName  
 Включает или отключает возможность синхронизировать текст заголовка с текстом метки на активной вкладке области с вкладками.  
  
```  
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 Значение TRUE, чтобы синхронизировать заголовок области с вкладками с активной вкладкой заголовок; в противном случае — значение FALSE.  
  
##  <a name="filldefaulttabsorderarray"></a>  CBaseTabbedPane::FillDefaultTabsOrderArray  
 Восстанавливает состояние по умолчанию внутренней последовательности.  
  
```  
void FillDefaultTabsOrderArray();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, когда платформа восстанавливает панель Outlook в исходное состояние.  
  
##  <a name="findpanebyid"></a>  CBaseTabbedPane::FindPaneByID  
 Возвращает панель, определенный с помощью идентификатора области.  
  
```  
virtual CWnd* FindPaneByID(UINT uBarID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uBarID*  
 Указывает идентификатор области для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на область, если он найден; в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Этот метод сравнивает все вкладки в области и возвращает запись с Идентификатором, указанным параметром *uBarID* параметра.  
  
##  <a name="findbarbytabnumber"></a>  CBaseTabbedPane::FindBarByTabNumber  
 Возвращает область, в которой находится на вкладке.  
  
```  
virtual CWnd* FindBarByTabNumber(
    int nTabNum,  
    BOOL bGetWrappedBar = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nTabNum*  
 Указывает отсчитываемый от нуля индекс вкладки для извлечения.  
  
 [in] *bGetWrappedBar*  
 TRUE, чтобы вернуть окна (оболочку) области вместо области в противном случае — значение FALSE. Это относится только к области, производный от [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если обнаруживается области, то возвращается допустимый указатель на панель, поиск которого выполняется; в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для извлечения области, находящиеся в вкладку, указанную в *nTabNum* параметра.  
  
##  <a name="floattab"></a>  CBaseTabbedPane::FloatTab  
 Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out] *pBar*  
 Указатель на панель, число с плавающей запятой.  
  
 [in] *nTabID*  
 Указывает отсчитываемый от нуля индекс вкладки, число с плавающей запятой.  
  
 [in] *dockMethod*  
 Задает метод, с помощью панели float. Дополнительные сведения см. в разделе "Примечания".  
  
 [in] *bHide*  
 Значение TRUE, чтобы скрыть область перед с плавающей запятой; в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если оставить плавающим области; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для перемещения область, в которой в данный момент расположен на отделяемой вкладке.  
  
 Если необходимо отключить панель программными средствами, укажите DM_SHOW для *dockMethod* параметра. Число с плавающей запятой на панели в той же позиции, где ранее находился следует указать DM_DBL_CLICK как *dockMethod* параметра.  
  
##  <a name="getdefaulttabsorder"></a>  CBaseTabbedPane::GetDefaultTabsOrder  
 Возвращает значение по умолчанию порядок вкладок на панели.  
  
```  
const CArray<int,int>& GetDefaultTabsOrder();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CArray` , указывающий значение по умолчанию порядок вкладок на панели.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при сбросе панель Outlook в исходное состояние.  
  
##  <a name="getfirstvisibletab"></a>  CBaseTabbedPane::GetFirstVisibleTab  
 Извлекает указатель на первой вкладке отображается.  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iTabNum*  
 Ссылка на целое число. Этот метод записывает отсчитываемый от нуля индекс первого отображаемого вкладки этот параметр, или значение -1, если не отображается, найти вкладку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении указатель на первой вкладке отображается; в противном случае — значение NULL.  
  
##  <a name="getminsize"></a>  CBaseTabbedPane::GetMinSize  
 Получает минимальный поддерживаемый размер для области.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *размер*  
 Объект `CSize` объект, который заполняется минимально допустимого размера.  
  
### <a name="remarks"></a>Примечания  
 Если согласованная обработка размеров Минимальная область активна ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *размер* заполняется минимальный поддерживаемый размер для активной вкладки. В противном случае *размер* заполняется возвращаемое значение [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpaneicon"></a>  CBaseTabbedPane::GetPaneIcon  
 Получает минимальный поддерживаемый размер для области.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *размер*  
 Объект `CSize` объект, который заполняется минимально допустимого размера.  
  
### <a name="remarks"></a>Примечания  
 Если согласованная обработка размеров Минимальная область активна ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *размер* заполняется минимальный поддерживаемый размер для активной вкладки. В противном случае *размер* заполняется возвращаемое значение [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpanelist"></a>  CBaseTabbedPane::GetPaneList  
 Возвращает список панелей, содержащихся в области с вкладками.  
  
```  
virtual void GetPaneList(
    CObList& lst,  
    CRuntimeClass* pRTCFilter = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [out] *lst*  
 Объект `CObList` , заполняемый панелей, содержащихся в области с вкладками.  
  
 [in] *pRTCFilter*  
 Если он не равен NULL, возвращаемый список содержит только те области, которые входят в класс указанной среды выполнения.  
  
##  <a name="gettabarea"></a>  CBaseTabbedPane::GetTabArea  
 Возвращает ограничивающих прямоугольников для верхней и нижней области вкладки.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *rectTabAreaTop*  
 Получает экранные координаты области верхняя вкладка.  
  
 [out] *rectTabAreaBottom*  
 Получает экранные координаты в нижней области вкладки.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы определить, ограничивающие прямоугольники, в экранных координатах, для области верхнего и нижнего вкладки.  
  
##  <a name="gettabsnum"></a>  CBaseTabbedPane::GetTabsNum  
 Возвращает количество вкладок в окне вкладку.  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество вкладок в области с вкладками.  
  
##  <a name="getunderlyingwindow"></a>  CBaseTabbedPane::GetUnderlyingWindow  
 Получает нижележащего окна (оболочку) вкладки.  
  
```  
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на вкладке окна.  
  
##  <a name="getvisibletabsnum"></a>  CBaseTabbedPane::GetVisibleTabsNum  
 Возвращает количество видимых вкладок.  
  
```  
virtual int GetVisibleTabsNum() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество видимых вкладок, которые будут больше или равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы определить количество видимых вкладок на панели с вкладками.  
  
##  <a name="hasautohidemode"></a>  CBaseTabbedPane::HasAutoHideMode  
 Определяет возможность переключения панели с вкладками в режим автоматического скрытия.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если области можно переключить в режим автоматического скрытия. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Если отключен режим автоматического скрытия, отсутствует кнопка "закрепить" отображается в заголовке области с вкладками.  
  
##  <a name="ishidesingletab"></a>  CBaseTabbedPane::IsHideSingleTab  
 Определяет, скрыт ли панель с вкладками, если только одна вкладка отображается.  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если окно вкладка не отображается, если имеется только одна видимая вкладка; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Если панель не отображается, так как только одна вкладка открыт, можно вызвать этот метод, чтобы определить, правильно ли работает области с вкладками.  
  
##  <a name="removepane"></a>  CBaseTabbedPane::RemovePane  
 Удаляет панель из панели с вкладками.  
  
```  
virtual BOOL RemovePane(CWnd* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out] *pBar*  
 Указатель на панели, чтобы удалить из области с вкладками.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если области успешно удален из области с вкладками и панели с вкладками по-прежнему действителен. Значение FALSE, если последнее был удален из области с вкладками и панели с вкладками уничтожить. Если возвращаемое значение равно FALSE, не используйте панель с вкладками больше.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для удаления области, определяемой *pBar* параметра из области с вкладками.  
  
##  <a name="setautodestroy"></a>  CBaseTabbedPane::SetAutoDestroy  
 Определяет, автоматическое удаление панели элементов управления с вкладками.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bAutoDestroy*  
 Значение TRUE, если панель с вкладками была создана динамически, и вы не управляете существования; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Задайте автоматическое уничтожить режиме значение TRUE при создании области с вкладками динамически, и если вы не управляете времени его существования. Если уничтожить автоматического режима — TRUE, в области с вкладками будет быть автоматически уничтожена платформой.  
  
##  <a name="showtab"></a>  CBaseTabbedPane::ShowTab  
 Показывает или скрывает вкладки.  
  
```  
virtual BOOL ShowTab(
    CWnd* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBar*  
 Указатель на панель, чтобы показать или скрыть.  
  
 [in] *bShow*  
 Значение TRUE для отображения области; Значение FALSE, чтобы скрыть области.  
  
 [in] *bDelay*  
 Значение TRUE, чтобы отложить корректировка вкладок; в противном случае — значение FALSE.  
  
 [in] *bActivate*  
 Значение TRUE, чтобы отобразить вкладку активной вкладкой; в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если вкладке показано или скрыто успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 При вызове этого метода, либо показано или скрыта область, в зависимости от значения *bShow* параметра. Если скрыть вкладку, она является последней видимой в окна вкладка скрыта области с вкладками. Если при наличии ранее не вкладки видимыми Показать вкладку, отображается панель с вкладками.  
  
##  <a name="recalclayout"></a>  CBaseTabbedPane::RecalcLayout  
 Повторно вычисляет сведения о структуре для области.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Если область является перемещаемой, этот метод уведомляет framework для изменения размера панели, чтобы текущий размер мини-рамки.  
  
 Если панель закреплена, этот метод не выполняет никаких действий.  
  
##  <a name="setautohidemode"></a>  CBaseTabbedPane::SetAutoHideMode  
 Задает режим автоматического скрытия для отделяемые панелей в области с вкладками.  
  
```  
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bMode*  
 Значение TRUE, чтобы включить режим автоматического скрытия; Значение FALSE, чтобы включить обычный режим закрепления.  
  
 [in] *dwAlignment*  
 Задает выравнивание автоматического скрытия области, в которой должен быть создан. Список возможных значений см. в разделе [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).  
  
 [in] [out] *pCurrAutoHideBar*  
 Указатель на текущей панели инструментов автоматического скрытия. Может иметь значение NULL.  
  
 [in] *bUseTimer*  
 Указывает, следует ли использовать автоматическое скрытие эффекта, когда пользователь переключает область в режим автоматического скрытия или скрыть область немедленно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панели инструментов автоматического скрытия, которая создается при переключении в режим автоматического скрытия, или значение NULL, если создается не панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда пользователь нажимает кнопку закрепления для переключения панели с вкладками в режим автоматического скрытия или в обычный режим закрепления.  
  
 Для каждой отделяемые панели в области с вкладками, используется режим автоматического скрытия. Области, которые являются неотделяемые игнорируются. Дополнительные сведения см. в разделе [CMFCBaseTabCtrl::EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).  
  
 Этот метод используется для переключения области с вкладками в режим автоматического скрытия программным способом. Области должно быть закреплено окно главного фрейма ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) должен возвращать допустимый указатель на [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)
