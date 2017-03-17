---
title: "Класс CBaseTabbedPane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CBaseTabbedPane class
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b72804dd8b2ca2253caff4cebf5b0631ae6040c6
ms.lasthandoff: 02/24/2017

---
# <a name="cbasetabbedpane-class"></a>Класс CBaseTabbedPane
Расширяет функциональность [CDockablePane класса](../../mfc/reference/cdockablepane-class.md) для поддержки создания окон с вкладками.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBaseTabbedPane::AddTab](#addtab)|Добавляет новую вкладку область с вкладками.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Указывает, можно ли удалить пустая область с вкладками.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Применяет параметры табуляции, которые загружаются из реестра, чтобы область с вкладками.|  
|[CBaseTabbedPane::CanFloat](#canfloat)|Определяет, может перемещаться ли области. (Переопределяет [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Определяет, должен ли заголовок для области с вкладками отображать тот же текст в активную вкладку.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(Переопределяет [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|  
|[CBaseTabbedPane::DetachPane](#detachpane)|Преобразует один или несколько закрепляемых областей документы с вкладками MDI.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Включает или отключает возможность синхронизации текст заголовка с текстом метки на активной вкладке области с вкладками.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|Восстанавливает состояние по умолчанию внутренней последовательности.|  
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Возвращает область, в которой находится на вкладке при вкладке определяется по клавише tab (с нуля).|  
|||  
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|Возвращает область, в которой определяется по идентификатору области.|  
|[CBaseTabbedPane::FloatTab](#floattab)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Возвращает порядок вкладок на панели.|  
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|Извлекает указатель на первой вкладке отображается.|  
|[CBaseTabbedPane::GetMinSize](#getminsize)|Получает минимальный поддерживаемый размер для области. (Переопределяет [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Возвращает дескриптор для значка панели. (Переопределяет [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|  
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Возвращает список областей, содержащихся в области с вкладками.|  
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Возвращает прямоугольников вкладки в верхней и нижней областях.|  
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Возвращает число вкладок в окне вкладку.|  
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Возвращает базовый (оболочку) вкладки окна.|  
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Возвращает число отображаемых вкладок.|  
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|Определяет, можно ли переключить режим автоматического скрытия области с вкладками.|  
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|Определяет, скрыт ли области с вкладками, если только одна вкладка отображается.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Используется во время сериализации.|  
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Обновление сведений о макете для области. (Переопределяет [CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CBaseTabbedPane::RemovePane](#removepane)|Удаляет область панели с вкладками.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Используется во время сериализации.|  
|`CBaseTabbedPane::Serialize`|(Переопределяет [CDockablePane::Serialize](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6).)|  
|`CBaseTabbedPane::SerializeTabWindow`|Используется во время сериализации.|  
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Определяет, автоматическое удаление панели управления с вкладками.|  
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Переключение между закрепляемой области отображения и режим автоматического скрытия. (Переопределяет [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|  
|[CBaseTabbedPane::ShowTab](#showtab)|Показывает или скрывает вкладку.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является абстрактным классом и не может быть создан. Он реализует службы, которые являются общими для всех видов вкладки.  
  
 В настоящее время библиотека включает два класса производного панели с вкладками: [класса CTabbedPane](../../mfc/reference/ctabbedpane-class.md) и [CMFCOutlookBar класса](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Объект `CBaseTabbedPane` объект охватывает указатель [CMFCBaseTabCtrl класс](../../mfc/reference/cmfcbasetabctrl-class.md) объекта. [Класс CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) становится дочернее окно области с вкладками.  
  
 Дополнительные сведения о создании вкладки см. в разделе [класса CDockablePane](../../mfc/reference/cdockablepane-class.md), [класса CTabbedPane](../../mfc/reference/ctabbedpane-class.md), и [CMFCOutlookBar класса](../../mfc/reference/cmfcoutlookbar-class.md).  
  
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
  
##  <a name="addtab"></a>CBaseTabbedPane::AddTab  
 Добавляет новую вкладку область с вкладками.  
  
```  
virtual BOOL AddTab(
    CWnd* pNewBar,  
    BOOL bVisible = TRUE,  
    BOOL bSetActive = TRUE,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pNewBar`  
 Указатель на область для добавления. Этот указатель могут стать недопустимыми после вызова этого метода. Дополнительные сведения см. в разделе "Примечания".  
  
 [in] `bVisible`  
 `TRUE`Чтобы отобразить вкладку; в противном случае — `FALSE`.  
  
 [in] `bSetActive`  
 `TRUE`отобразить вкладку активной вкладке; в противном случае — `FALSE`.  
  
 [in] `bDetachable`  
 `TRUE`Чтобы отобразить вкладку отключаемых; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если был успешно добавлен в виде вкладки области и не удаляется в процессе. `FALSE`Если панель добавляемый объект типа `CBaseTabbedPane`. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы добавить область в виде новой вкладки на область с вкладками. Если `pNewBar` указывает на объект типа `CBaseTabbedPane`, копируется все вкладки на панели с вкладками и затем `pNewBar` уничтожается. Таким образом `pNewBar` становится недопустимый указатель и не должны использоваться.  
  
##  <a name="allowdestroyemptytabbedpane"></a>CBaseTabbedPane::AllowDestroyEmptyTabbedPane  
 Указывает, можно ли удалить пустая область с вкладками.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если пустая область с вкладками можно быть уничтожено; в противном случае — `FALSE`. Реализация по умолчанию всегда возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Если пустая область с вкладками запрещено будут уничтожены, платформа вместо скрывает панель.  
  
##  <a name="applyrestoredtabinfo"></a>CBaseTabbedPane::ApplyRestoredTabInfo  
 Загружает вкладку Параметры из реестра и применяет их к область с вкладками.  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bUseTabIndexes`  
 Этот параметр используется внутри платформой.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при его перезагрузке закрепления сведения о состоянии из реестра. Метод получает сведения о последовательности табуляции и названия вкладок для область с вкладками.  
  
##  <a name="canfloat"></a>CBaseTabbedPane::CanFloat  
 Указывает, можно ли float панели с вкладками.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель может перемещаться; в противном случае — `FALSE`.  
  
##  <a name="cansetcaptiontexttotabname"></a>CBaseTabbedPane::CanSetCaptionTextToTabName  
 Определяет, должен ли заголовок для области с вкладками отображать тот же текст в активную вкладку.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если текст заголовка панели с вкладками текст активной вкладке; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Метод используется для определения ли текст отображаться на дубликаты заголовок панели с вкладками метка активной вкладки. Можно включить или отключить эту функцию, вызвав [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname).  
  
##  <a name="converttotabbeddocument"></a>CBaseTabbedPane::ConvertToTabbedDocument  
 Преобразует один или несколько закрепляемых областей документы с вкладками MDI.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bActiveTabOnly`  
 При преобразовании область с вкладками, укажите `TRUE` для преобразования только на активную вкладку. Укажите `FALSE` для преобразования всех вкладок на панели.  
  
##  <a name="detachpane"></a>CBaseTabbedPane::DetachPane  
 Отсоединяет панель из панели с вкладками.  
  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на область для отсоединения.  
  
 [in] `bHide`  
 Логический параметр, указывает ли платформа framework скрывает панель после ее отключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если платформа успешно отсоединяет области; `FALSE` Если `pBar` — `NULL` или ссылается на область, которая не находится в области с вкладками.  
  
### <a name="remarks"></a>Примечания  
 Платформа смещает отсоединенных области, если это возможно. Дополнительные сведения см. в разделе [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).  
  
##  <a name="enablesetcaptiontexttotabname"></a>CBaseTabbedPane::EnableSetCaptionTextToTabName  
 Включает или отключает возможность синхронизации текст заголовка с текстом метки на активной вкладке области с вкладками.  
  
```  
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`для синхронизации с вкладками панели заголовка с активной вкладке заголовок; в противном случае — `FALSE`.  
  
##  <a name="filldefaulttabsorderarray"></a>CBaseTabbedPane::FillDefaultTabsOrderArray  
 Восстанавливает состояние по умолчанию внутренней последовательности.  
  
```  
void FillDefaultTabsOrderArray();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, когда платформа восстанавливает панель Outlook в исходное состояние.  
  
##  <a name="findpanebyid"></a>CBaseTabbedPane::FindPaneByID  
 Возвращает область, определяемый идентификатор области.  
  
```  
virtual CWnd* FindPaneByID(UINT uBarID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uBarID`  
 Указывает идентификатор области для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на область, если он найден; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод сравнивает все вкладки в области и возвращает запись с Идентификатором, указанным параметром `uBarID` параметр.  
  
##  <a name="findbarbytabnumber"></a>CBaseTabbedPane::FindBarByTabNumber  
 Возвращает область, в которой находится на вкладке.  
  
```  
virtual CWnd* FindBarByTabNumber(
    int nTabNum,  
    BOOL bGetWrappedBar = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTabNum`  
 Задает отсчитываемый от нуля индекс вкладки для извлечения.  
  
 [in] `bGetWrappedBar`  
 `TRUE`Чтобы вернуть окна (оболочку) области вместо области в противном случае `FALSE`. Это относится только к области, производный от [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если найден области, то возвращается допустимый указатель на панель, поиск которого выполняется; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения области, находящиеся в вкладку, указанную в `nTabNum` параметр.  
  
##  <a name="floattab"></a>CBaseTabbedPane::FloatTab  
 Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pBar`  
 Указатель на область с плавающей запятой.  
  
 [in] `nTabID`  
 Задает отсчитываемый от нуля индекс вкладки с плавающей запятой.  
  
 [in] `dockMethod`  
 Указывает метод, с помощью панели с плавающей запятой. Дополнительные сведения см. в разделе "Примечания".  
  
 [in] `bHide`  
 `TRUE`Чтобы скрыть область перед с плавающей запятой; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если оставить плавающим области; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для область, в которой в данный момент находится на вкладке отключаемых float.  
  
 Отключение панели программными средствами, укажите `DM_SHOW` для `dockMethod` параметр. Если вы хотите float области в том же месте, где ранее находился, укажите `DM_DBL_CLICK` как `dockMethod` параметр.  
  
##  <a name="getdefaulttabsorder"></a>CBaseTabbedPane::GetDefaultTabsOrder  
 Возвращает порядок вкладок на панели.  
  
```  
const CArray<int,int>& GetDefaultTabsOrder();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CArray` , определяющий порядок вкладок на панели.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда панель Outlook сбрасывается в исходное состояние.  
  
##  <a name="getfirstvisibletab"></a>CBaseTabbedPane::GetFirstVisibleTab  
 Извлекает указатель на первой вкладке отображается.  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTabNum`  
 Ссылка на целое число. Этот метод записывает отсчитываемый от нуля индекс первой отображаемой вкладке этот параметр или значение -1, если не отображается, находится вкладке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха, указатель на первой вкладке отображается; в противном случае — `NULL`.  
  
##  <a name="getminsize"></a>CBaseTabbedPane::GetMinSize  
 Получает минимальный поддерживаемый размер для области.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `size`  
 Объект `CSize` объект, который заполняется минимально допустимого размера.  
  
### <a name="remarks"></a>Примечания  
 Если согласованная обработка размеров Минимальная область активна ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), `size` заполняется минимально допустимого размера для активной вкладки. В противном случае — `size` заполняется возвращаемое значение [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpaneicon"></a>CBaseTabbedPane::GetPaneIcon  
 Получает минимальный поддерживаемый размер для области.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `size`  
 Объект `CSize` объект, который заполняется минимально допустимого размера.  
  
### <a name="remarks"></a>Примечания  
 Если согласованная обработка размеров Минимальная область активна ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), `size` заполняется минимально допустимого размера для активной вкладки. В противном случае — `size` заполняется возвращаемое значение [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpanelist"></a>CBaseTabbedPane::GetPaneList  
 Возвращает список областей, содержащихся в области с вкладками.  
  
```  
virtual void GetPaneList(
    CObList& lst,  
    CRuntimeClass* pRTCFilter = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `lst`  
 A `CObList` заполняется панелей, которые находятся в области с вкладками.  
  
 [in] `pRTCFilter`  
 Если это не `NULL`, возвращаемый список содержит только те области, которые имеют указанного класса среды выполнения.  
  
##  <a name="gettabarea"></a>CBaseTabbedPane::GetTabArea  
 Возвращает прямоугольников вкладки в верхней и нижней областях.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectTabAreaTop`  
 Получает экранные координаты верхней вкладки области.  
  
 [выходной] `rectTabAreaBottom`  
 Получает экранные координаты в нижней области вкладки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для определения прямоугольников, в экранных координатах для вкладку верхней и нижней области.  
  
##  <a name="gettabsnum"></a>CBaseTabbedPane::GetTabsNum  
 Возвращает число вкладок в окне вкладку.  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число вкладок на панели с вкладками.  
  
##  <a name="getunderlyingwindow"></a>CBaseTabbedPane::GetUnderlyingWindow  
 Возвращает базовый (оболочку) вкладки окна.  
  
```  
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на вкладку окна.  
  
##  <a name="getvisibletabsnum"></a>CBaseTabbedPane::GetVisibleTabsNum  
 Возвращает число вкладок видимым.  
  
```  
virtual int GetVisibleTabsNum() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число отображается вкладок, которые будет больше или равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Этот метод служит для определения числа видимым вкладки в области с вкладками.  
  
##  <a name="hasautohidemode"></a>CBaseTabbedPane::HasAutoHideMode  
 Определяет возможность переключения панели с вкладками в режим автоматического скрытия.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области можно переключить в режим автоскрытия. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 При отключении режима Автоскрытие не кнопка ПИН-код отображается в заголовке панели с вкладками.  
  
##  <a name="ishidesingletab"></a>CBaseTabbedPane::IsHideSingleTab  
 Определяет, скрыт ли области с вкладками, если только одна вкладка отображается.  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если окно вкладка не отображается, если имеется только одна вкладка отображается; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если область не отображается, поскольку открыта только одна вкладка, можно вызвать этот метод, чтобы определить, правильно ли работает области с вкладками.  
  
##  <a name="removepane"></a>CBaseTabbedPane::RemovePane  
 Удаляет область панели с вкладками.  
  
```  
virtual BOOL RemovePane(CWnd* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pBar`  
 Указатель на панели, чтобы удалить из области с вкладками.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области был успешно удален из области с вкладками и панели с вкладками по-прежнему действительна. `FALSE`Если последнее был удален из области с вкладками и панели с вкладками будут уничтожены. Если возвращаемое значение является `FALSE`, больше не используйте панели с вкладками.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для удаления области, определяемой `pBar` параметра из области с вкладками.  
  
##  <a name="setautodestroy"></a>CBaseTabbedPane::SetAutoDestroy  
 Определяет, автоматическое удаление панели управления с вкладками.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAutoDestroy`  
 `TRUE`Если область с вкладками создан динамически, и вы не управляете существования; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Задать режим автоматического уничтожения `TRUE` Если динамически создать область с вкладками, и если вы не управляете времени его существования. Если автоматического удаления режим `TRUE`, области с вкладками, уничтожается автоматически платформой.  
  
##  <a name="showtab"></a>CBaseTabbedPane::ShowTab  
 Показывает или скрывает вкладку.  
  
```  
virtual BOOL ShowTab(
    CWnd* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на панели, чтобы показать или скрыть.  
  
 [in] `bShow`  
 `TRUE`для отображения области; `FALSE` скрыть области.  
  
 [in] `bDelay`  
 `TRUE`Чтобы отложить корректировка структуру вкладки; в противном случае — `FALSE`.  
  
 [in] `bActivate`  
 `TRUE`отобразить вкладку активной вкладке; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если на вкладке была показаны или скрыты успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 При вызове этого метода области показаны или скрыты, в зависимости от значения `bShow` параметр. Если скрыть вкладку, это последняя отображается вкладка окна вкладку панели с вкладками скрыт. Если показать вкладку при наличии ранее вкладки не видны, отображается область с вкладками.  
  
##  <a name="recalclayout"></a>CBaseTabbedPane::RecalcLayout  
 Обновление сведений о макете для области.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Если панель закреплена, этот метод уведомляет платформу для изменения размера области, чтобы текущий размер области.  
  
 Если панель закреплена, этот метод не выполняет никаких действий.  
  
##  <a name="setautohidemode"></a>CBaseTabbedPane::SetAutoHideMode  
 Задает режим автоматического скрытия отключаемых панелей в области с вкладками.  
  
```  
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMode`  
 `TRUE`Чтобы включить режим автоматического скрытия; `FALSE` Включение обычный режим закрепления.  
  
 [in] `dwAlignment`  
 Задает выравнивание автоматического скрытия области, в которой должен быть создан. Список возможных значений см. в разделе [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).  
  
 [in] [out]`pCurrAutoHideBar`  
 Указатель на текущий инструментов автоматического скрытия. Может быть `NULL`.  
  
 [in] `bUseTimer`  
 Указывает, следует ли использовать эффект автоматического скрытия при переключении панели в режиме автоматического скрытия или скрыть область немедленно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель инструментов автоматического скрытия, которая создается при переключении в режим автоматического скрытия или `NULL` Если создается нет панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда пользователь нажимает кнопку закрепления в области с вкладками для переключения в режим автоматического скрытия или обычный режим закрепления.  
  
 Для каждой отключаемых панели в области с вкладками задан режим автоматического скрытия. Области, которые не отключаемых игнорируются. Дополнительные сведения см. в разделе [CMFCBaseTabCtrl::EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).  
  
 Этот метод используется для переключения область с вкладками в режиме автоматического скрытия программным способом. Необходимо закрепить области фрейма главного окна ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) должен возвращать допустимый указатель на [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)

