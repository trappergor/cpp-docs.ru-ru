---
title: Класс CBaseTabbedPane | Документы Microsoft
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
ms.openlocfilehash: edb9fe1942f9fe8b462ce9fc6a56e37538866174
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954992"
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
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Указывает, можно ли удалить пустой области с вкладками.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Применяет параметры вкладки, которые загружаются из реестра, в области с вкладками.|  
|[CBaseTabbedPane::CanFloat](#canfloat)|Определяет, можно ли float области. (Переопределяет [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Определяет, должен ли заголовок для области с вкладками отображать тот же текст в качестве активной вкладки.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(Переопределяет [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|  
|[CBaseTabbedPane::DetachPane](#detachpane)|Преобразует одного или нескольких закрепляемых областей в документы с вкладками MDI.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Включает или отключает возможность синхронизации текст заголовка текстом метки на активной вкладке области с вкладками.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|Восстанавливает состояние по умолчанию внутренней последовательности.|  
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Возвращает область, в которой находится на вкладке при вкладке идентифицируется по клавише tab (с нуля).|  
|||  
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|Возвращает область, в которой определяется по идентификатору области.|  
|[CBaseTabbedPane::FloatTab](#floattab)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Возвращает по умолчанию порядок вкладок на панели.|  
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|Извлекает указатель на первую вкладку отображается.|  
|[CBaseTabbedPane::GetMinSize](#getminsize)|Возвращает минимально допустимого размера области. (Переопределяет [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Возвращает дескриптор значка области. (Переопределяет [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|  
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Возвращает список панелей, содержащихся в области с вкладками.|  
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Возвращает прямоугольников вкладки в верхней и нижней областях.|  
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Возвращает количество вкладок в окно вкладки.|  
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Возвращает базовый (оболочку) вкладки окна.|  
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Возвращает количество отображаемых вкладок.|  
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|Определяет, является ли панель с вкладками можно переключить в режим автоматического скрытия.|  
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|Определяет, скрыт ли панель с вкладками, если только одна вкладка отображается.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Используется внутренним образом во время сериализации.|  
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Обновление сведений о макете для области. (Переопределяет [CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CBaseTabbedPane::RemovePane](#removepane)|Удаляет панель из области с вкладками.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Используется внутренним образом во время сериализации.|  
|`CBaseTabbedPane::Serialize`|(Переопределяет [CDockablePane::Serialize](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6).)|  
|`CBaseTabbedPane::SerializeTabWindow`|Используется внутренним образом во время сериализации.|  
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Определяет, автоматически уничтожаться панели элементов управления с вкладками.|  
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Переключает область закрепления между отображается и режима автоматического скрытия. (Переопределяет [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|  
|[CBaseTabbedPane::ShowTab](#showtab)|Показывает или скрывает вкладки.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является абстрактным классом и не может быть создан. Он реализует службы, которые являются общими для всех видов панели с вкладками.  
  
 В настоящее время в библиотеку входят два класса производного области с вкладками: [класса CTabbedPane](../../mfc/reference/ctabbedpane-class.md) и [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Объект `CBaseTabbedPane` объект охватывает указатель [CMFCBaseTabCtrl класс](../../mfc/reference/cmfcbasetabctrl-class.md) объекта. [Класс CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) становится дочерним окном области с вкладками.  
  
 Дополнительные сведения о создании панели с вкладками см. в разделе [класс CDockablePane](../../mfc/reference/cdockablepane-class.md), [класса CTabbedPane](../../mfc/reference/ctabbedpane-class.md), и [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
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
 Указатель на область для добавления. Этот указатель могут стать недопустимыми после вызова этого метода. Дополнительные сведения см. в разделе "Примечания".  
  
 [in] *bVisible*  
 `TRUE` Чтобы сделать вкладку видимым. в противном случае `FALSE`.  
  
 [in] *bSetActive*  
 `TRUE` Чтобы сделать вкладку активной вкладки; в противном случае `FALSE`.  
  
 [in] *bDetachable*  
 `TRUE` Чтобы сделать вкладку отделяемые; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если область был успешно добавлен в виде вкладки и не был удален в процессе. `FALSE` Если панель добавляется объект типа `CBaseTabbedPane`. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для добавления в область в виде новой вкладки в области с вкладками. Если *pNewBar* указывает на объект типа `CBaseTabbedPane`, копируется на панель с вкладками все вкладки и затем *pNewBar* уничтожается. Таким образом *pNewBar* становится недопустимый указатель и не должны использоваться.  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CBaseTabbedPane::AllowDestroyEmptyTabbedPane  
 Указывает, можно ли удалить пустой области с вкладками.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если пустая область с вкладками может быть уничтожено; в противном случае `FALSE`. Реализация по умолчанию всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Если не может быть пустой области с вкладками будут уничтожены, вместо этого платформа скрывает область.  
  
##  <a name="applyrestoredtabinfo"></a>  CBaseTabbedPane::ApplyRestoredTabInfo  
 Загружает параметры табуляции из реестра и применяет их к области с вкладками.  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bUseTabIndexes*  
 Этот параметр используется внутренне платформой.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при его перезагрузке закрепления сведения о состоянии из реестра. Метод получает сведения о последовательности табуляции и названия вкладок для области с вкладками.  
  
##  <a name="canfloat"></a>  CBaseTabbedPane::CanFloat  
 Указывает, можно ли float области с вкладками.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если область может число с плавающей запятой; в противном случае `FALSE`.  
  
##  <a name="cansetcaptiontexttotabname"></a>  CBaseTabbedPane::CanSetCaptionTextToTabName  
 Определяет, должен ли заголовок для области с вкладками отображать тот же текст в качестве активной вкладки.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если текст заголовка области с вкладками текста активной вкладки; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Метод используется для определения ли текст отображаться на повторяющиеся значения заголовка области с вкладками метка активной вкладки. Можно включить или отключить эту возможность, вызвав [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname).  
  
##  <a name="converttotabbeddocument"></a>  CBaseTabbedPane::ConvertToTabbedDocument  
 Преобразует одного или нескольких закрепляемых областей в документы с вкладками MDI.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bActiveTabOnly*  
 При преобразовании области с вкладками, укажите `TRUE` для преобразования только активной вкладки. Укажите `FALSE` для преобразования всех вкладок на панели.  
  
##  <a name="detachpane"></a>  CBaseTabbedPane::DetachPane  
 Отсоединяет область из области с вкладками.  
  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBar*  
 Указатель на область для отсоединения.  
  
 [in] *bHide*  
 Логический параметр, указывает ли платформа скрывает область после ее отсоединения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если платформа успешно отсоединяет области; `FALSE` Если *pBar* — `NULL` или ссылается на область, которая не находится в области с вкладками.  
  
### <a name="remarks"></a>Примечания  
 Платформа смещает области отсоединенных Если это возможно. Дополнительные сведения см. в разделе [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).  
  
##  <a name="enablesetcaptiontexttotabname"></a>  CBaseTabbedPane::EnableSetCaptionTextToTabName  
 Включает или отключает возможность синхронизации текст заголовка текстом метки на активной вкладке области с вкладками.  
  
```  
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 `TRUE` для синхронизации с заголовком активной вкладке; заголовок области с вкладками в противном случае `FALSE`.  
  
##  <a name="filldefaulttabsorderarray"></a>  CBaseTabbedPane::FillDefaultTabsOrderArray  
 Восстанавливает состояние по умолчанию внутренней последовательности.  
  
```  
void FillDefaultTabsOrderArray();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, когда платформа панель Outlook восстанавливает в исходное состояние.  
  
##  <a name="findpanebyid"></a>  CBaseTabbedPane::FindPaneByID  
 Возвращает область, определяемый по идентификатору области.  
  
```  
virtual CWnd* FindPaneByID(UINT uBarID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uBarID*  
 Указывает идентификатор области для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на область, если он найден; в противном случае `NULL`.  
  
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
 Задает отсчитываемый от нуля индекс вкладки для извлечения.  
  
 [in] *bGetWrappedBar*  
 `TRUE` для возврата базового (оболочку) окна области вместо области в противном случае `FALSE`. Это относится только к области, производный от [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если обнаруживается области, то возвращается допустимый указатель в область, поиск которого выполняется; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения панели, находящейся в вкладку, указанную в *nTabNum* параметра.  
  
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
 Указатель на панели, чтобы число с плавающей запятой.  
  
 [in] *nTabID*  
 Задает отсчитываемый от нуля индекс вкладки в тип float.  
  
 [in] *dockMethod*  
 Указывает метод, чтобы делать на панели с плавающей запятой. Дополнительные сведения см. в разделе "Примечания".  
  
 [in] *bHide*  
 `TRUE` Чтобы скрыть область перед с плавающей запятой; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если перемещается области; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для число с плавающей запятой в область, расположенную в настоящее время на отделяемой вкладке.  
  
 Для отсоединения панель программными средствами, укажите `DM_SHOW` для *dockMethod* параметра. Если вы хотите float области в той же позиции, где ранее перемещается, укажите `DM_DBL_CLICK` как *dockMethod* параметра.  
  
##  <a name="getdefaulttabsorder"></a>  CBaseTabbedPane::GetDefaultTabsOrder  
 Возвращает по умолчанию порядок вкладок на панели.  
  
```  
const CArray<int,int>& GetDefaultTabsOrder();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CArray` , указывающий порядок вкладок на панели.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при сбросе панель Outlook в исходное состояние.  
  
##  <a name="getfirstvisibletab"></a>  CBaseTabbedPane::GetFirstVisibleTab  
 Извлекает указатель на первую вкладку отображается.  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iTabNum*  
 Ссылка на целое число. Этот метод записывает отсчитываемый от нуля индекс первой отображаемой вкладке этот параметр или значение -1, если не отображается, найти вкладку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения указатель на первую вкладку отображаемых; в противном случае `NULL`.  
  
##  <a name="getminsize"></a>  CBaseTabbedPane::GetMinSize  
 Возвращает минимально допустимого размера области.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *размер*  
 Объект `CSize` объект, который заполняется минимально допустимого размера.  
  
### <a name="remarks"></a>Примечания  
 Если активен согласованно обрабатывать размеры области в минимальное ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *размер* заполняется минимально допустимого размера для активной вкладки. В противном случае *размер* заполняется возвращаемое значение [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpaneicon"></a>  CBaseTabbedPane::GetPaneIcon  
 Возвращает минимально допустимого размера области.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *размер*  
 Объект `CSize` объект, который заполняется минимально допустимого размера.  
  
### <a name="remarks"></a>Примечания  
 Если активен согласованно обрабатывать размеры области в минимальное ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *размер* заполняется минимально допустимого размера для активной вкладки. В противном случае *размер* заполняется возвращаемое значение [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpanelist"></a>  CBaseTabbedPane::GetPaneList  
 Возвращает список панелей, содержащихся в области с вкладками.  
  
```  
virtual void GetPaneList(
    CObList& lst,  
    CRuntimeClass* pRTCFilter = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [out] *lst*  
 Объект `CObList` , заполняемый панелей, которые находятся в области с вкладками.  
  
 [in] *pRTCFilter*  
 Если это не `NULL`, возвращаемый список содержит только те области, которые имеют указанного класса среды выполнения.  
  
##  <a name="gettabarea"></a>  CBaseTabbedPane::GetTabArea  
 Возвращает прямоугольников вкладки в верхней и нижней областях.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *rectTabAreaTop*  
 Получает экранные координаты вкладки в верхней области.  
  
 [out] *rectTabAreaBottom*  
 Получает экранные координаты в нижней области вкладки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для определения прямоугольников, в экранных координатах для области верхнего и нижнего вкладки.  
  
##  <a name="gettabsnum"></a>  CBaseTabbedPane::GetTabsNum  
 Возвращает количество вкладок в окно вкладки.  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число вкладок на панели с вкладками.  
  
##  <a name="getunderlyingwindow"></a>  CBaseTabbedPane::GetUnderlyingWindow  
 Возвращает базовый (оболочку) вкладки окна.  
  
```  
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на базовый окно вкладки.  
  
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
 `TRUE` Если области можно переключить режим автоматического скрытия; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Режим автоматического скрытия при отключении кнопка не ПИН-код отображается в заголовке области с вкладками.  
  
##  <a name="ishidesingletab"></a>  CBaseTabbedPane::IsHideSingleTab  
 Определяет, скрыт ли панель с вкладками, если только одна вкладка отображается.  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если окно вкладки не отображается, если имеется только одна видимая вкладка; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если область не отображается, поскольку открыта только одна вкладка, можно вызвать этот метод, чтобы определить, правильно ли работает области с вкладками.  
  
##  <a name="removepane"></a>  CBaseTabbedPane::RemovePane  
 Удаляет панель из области с вкладками.  
  
```  
virtual BOOL RemovePane(CWnd* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out] *pBar*  
 Указатель на панели, чтобы удалить из области с вкладками.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если области был успешно удален из области с вкладками и области с вкладками по-прежнему действителен. `FALSE` Если последнее был удален из области с вкладками и области с вкладками будут уничтожены. Если возвращается значение `FALSE`, больше не используйте панель с вкладками.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для удаления области, определяемой *pBar* параметра из области с вкладками.  
  
##  <a name="setautodestroy"></a>  CBaseTabbedPane::SetAutoDestroy  
 Определяет, автоматически уничтожаться панели элементов управления с вкладками.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bAutoDestroy*  
 `TRUE` Если панель с вкладками создан динамически, и вы не управляете существования; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Задайте режим auto уничтожить `TRUE` при создании области с вкладками динамически и если вы не управляете времени его существования. Если автоматически уничтожить режим — `TRUE`, панель с вкладками будет удален автоматически платформой.  
  
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
 Указатель на панели, чтобы показать или скрыть.  
  
 [in] *bShow*  
 `TRUE` Чтобы отобразить область; `FALSE` скрыть область.  
  
 [in] *bDelay*  
 `TRUE` для задержки корректировки вкладка макета; в противном случае `FALSE`.  
  
 [in] *bActivate*  
 `TRUE` Чтобы сделать вкладку активной вкладки; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если вкладке было показано или скрыто успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 При вызове этого метода областью показано или скрыто, в зависимости от значения *bShow* параметра. Если это последний отображается вкладка в окне базовой tab скрыта метка вкладки, скрыто области с вкладками. Если при наличии ранее не вкладки видимыми Показать вкладку, отображается панель с вкладками.  
  
##  <a name="recalclayout"></a>  CBaseTabbedPane::RecalcLayout  
 Обновление сведений о макете для области.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Если панель открывается как плавающее окно, этот метод сообщает платформе, чтобы изменить размер области, чтобы текущий размер мини-рамки.  
  
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
 `TRUE` Чтобы включить режим автоматического скрытия; `FALSE` Включение обычный режим закрепления.  
  
 [in] *dwAlignment*  
 Задает выравнивание автоматического скрытия области, в которой должен быть создан. Список возможных значений см. в разделе [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).  
  
 [in] [out] *pCurrAutoHideBar*  
 Указатель на панель инструментов текущего автоматического скрытия. Может быть `NULL`.  
  
 [in] *bUseTimer*  
 Указывает, следует ли использовать эффект автоматического скрытия при переключении области в режим автоматического скрытия, или скрыть область немедленно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панели инструментов автоматического скрытия, которая создается при переключении в режим автоматического скрытия или `NULL` , созданный без панелей инструментов.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда пользователь нажимает кнопку закрепления для области с вкладками для переключения в режим автоматического скрытия или обычный режим закрепления.  
  
 Для каждой отделяемые панели в области с вкладками задан режим автоматического скрытия. Области, которые являются неотделяемые игнорируются. Дополнительные сведения см. в разделе [CMFCBaseTabCtrl::EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).  
  
 Этот метод используется для переключения области с вкладками в режим автоматического скрытия программными средствами. Области должно быть закреплено основную область окна ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) должен возвращать допустимый указатель на [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)
