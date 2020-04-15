---
title: Класс CBaseTabbedPane
ms.date: 11/04/2016
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
ms.openlocfilehash: ce7c48263ed511545757c94d61552e6206e74a00
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352858"
---
# <a name="cbasetabbedpane-class"></a>Класс CBaseTabbedPane

Расширяет функциональность [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) для поддержки создания окон с вкладками.

## <a name="syntax"></a>Синтаксис

```
class CBaseTabbedPane : public CDockablePane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CBaseTabbedPane::CBaseTabbedPane`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBaseTabbedPane::AddTab](#addtab)|Добавляет новую вкладку в панель ный вкладок.|
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Определяет, можно ли уничтожить пустое табло.|
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Применяет настройки вкладок, которые загружаются из реестра, к панели вкладок.|
|[CBaseTabbedPane::CanFloat](#canfloat)|Определяет, может ли панель плавать. (Переопределяет [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Определяет, должна ли подпись для панели вкладок отображать тот же текст, что и активная вкладка.|
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(Перекрывает [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|
|[CBaseTabbedPane::DetachPane](#detachpane)|Преобразует одну или несколько доковых стекол в документы MDI.|
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Позволяет или отсутствует способность панели вкладок синхронизировать текст подписи с текстом этикетки на активной вкладке.|
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|Восстанавливает внутренний порядок вкладки в состояние по умолчанию.|
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Возвращает панель, которая находится во вкладке, когда вкладка идентифицирована индексом вкладок с нулевым уровнем.|
|||
|[CBaseTabbedPane:FindPaneByID](#findpanebyid)|Возвращает панель, идентифицированную идентификатором панели.|
|[CBaseTabbedPane::FloatTab](#floattab)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.|
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Возвращает порядок вкладок по умолчанию в панели.|
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|Извлекает указатель на первую отображаемую вкладку.|
|[CBaseTabbedPane::GetMinSize](#getminsize)|Получает минимальный допустимый размер для панели. (Переопределяет [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Возвращает ручку значку панели. (Оверлет [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Возвращает список стекол, которые содержатся в панели вкладок.|
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Возвращает прямоугольники для верхних и нижних областей вкладки.|
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Возвращает количество вкладок в окне вкладок.|
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Получает базовое (обертое) окно вкладок.|
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Возвращает количество отображаемых вкладок.|
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|Определяет, можно ли переключить панель вкладок в режим автоматической скрытности.|
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|Определяет, скрыто ли табло, если отображается только одна вкладка.|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Используется внутренне во время сериализации.|
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Пересчитывает информацию о макете для панели. (Перекрывает [CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|
|[CBaseTabbedPane::RemovePane](#removepane)|Удаляет панель из панели вкладок.|
|`CBaseTabbedPane::SaveSiblingBarIDs`|Используется внутренне во время сериализации.|
|`CBaseTabbedPane::Serialize`|(Перекрывает [CDockablePane::Serialize](cdockablepane-class.md).)|
|`CBaseTabbedPane::SerializeTabWindow`|Используется внутренне во время сериализации.|
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Определяет, будет ли панель управления вкладками уничтожена автоматически.|
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Переключает стыковочные панели между отображаемым и автоматически скрыть режим. (Перекрывает [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|
|[CBaseTabbedPane::ShowTab](#showtab)|Показывает или скрывает вкладку.|

## <a name="remarks"></a>Remarks

Этот класс является абстрактным классом и не может быть мгновенно. Он реализует службы, которые являются общими для всех видов табло стекол.

В настоящее время библиотека включает в себя два производных классы табло- панель: [класс CTabbedPane](../../mfc/reference/ctabbedpane-class.md) и [CMFCOutlookBar.](../../mfc/reference/cmfcoutlookbar-class.md)

Объект `CBaseTabbedPane` обертывает указатель на объект [класса CMFCBaseTabCtrl.](../../mfc/reference/cmfcbasetabctrl-class.md) [CmFCBaseTabCtrl Класс](../../mfc/reference/cmfcbasetabctrl-class.md) затем становится окном ребенка панели вкладок.

Для получения дополнительной информации о том, как создать панели вкладок, [см. CDockablePane класса](../../mfc/reference/cdockablepane-class.md), [CTabbedPane класса](../../mfc/reference/ctabbedpane-class.md), и [CMFCOutlookBar класса](../../mfc/reference/cmfcoutlookbar-class.md).

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

## <a name="cbasetabbedpaneaddtab"></a><a name="addtab"></a>CBaseTabbedPane::AddTab

Добавляет новую вкладку в панель ный вкладок.

```
virtual BOOL AddTab(
    CWnd* pNewBar,
    BOOL bVisible = TRUE,
    BOOL bSetActive = TRUE,
    BOOL bDetachable = TRUE);
```

### <a name="parameters"></a>Параметры

*pNewBar*<br/>
(в, вне) Указатель на панель, чтобы добавить. Этот указатель может стать недействительным после вызова этого метода. Дополнительные сведения см. в разделе «Примечания».

*bVisible*<br/>
(в) TRUE, чтобы сделать вкладку видимой; в противном случае, FALSE.

*bSetActive*<br/>
(в) TRUE, чтобы сделать вкладку активной вкладкой; в противном случае, FALSE.

*bDetachable*<br/>
(в) TRUE, чтобы сделать вкладку съемной; в противном случае, FALSE.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель была успешно добавлена в качестве вкладки и не был уничтожен в процессе. FALSE, если добавленное стежок является объектом типа. `CBaseTabbedPane` Дополнительные сведения см. в разделе «Примечания».

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы добавить панель в качестве новой вкладки на панели вкладок. Если *pNewBar* указывает на `CBaseTabbedPane`объект типа, все его вкладки копируются на панель вкладок, а затем *pNewBar* разрушается. Таким образом, *pNewBar* становится недействительным указателем и не должен использоваться.

## <a name="cbasetabbedpaneallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>CBaseTabbedPane::AllowDestroyEmptyTabbedPane

Определяет, можно ли уничтожить пустое табло.

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если пустое табло панели могут быть уничтожены; в противном случае, FALSE. Реализация по умолчанию всегда возвращает TRUE.

### <a name="remarks"></a>Remarks

Если пустое табло не может быть уничтожено, фреймворк вместо этого скрывает панель.

## <a name="cbasetabbedpaneapplyrestoredtabinfo"></a><a name="applyrestoredtabinfo"></a>CBaseTabbedPane::ApplyRestoredTabInfo

Загружает настройки вкладок из реестра и применяет их к панели вкладок.

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>Параметры

*bUseTabИндексы*<br/>
(в) Этот параметр используется внутри фреймворка.

### <a name="remarks"></a>Remarks

Этот метод вызывается инфраструктурой при перезагрузке стыковки государственной информации из реестра. Метод получает информацию о порядке вкладок и именах вкладок для панели вкладок.

## <a name="cbasetabbedpanecanfloat"></a><a name="canfloat"></a>CBaseTabbedPane::CanFloat

Определяет, может ли табло плавать.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель может плавать; в противном случае, FALSE.

## <a name="cbasetabbedpanecansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>CBaseTabbedPane::CanSetCaptionTextToTabName

Определяет, должна ли подпись для панели вкладок отображать тот же текст, что и активная вкладка.

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если текст заголовка табло установлен на текст активной вкладки; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Метод используется для определения того, дублирует ли текст подпись вкладке подпись к метке активной вкладки. Вы можете включить или отключить эту функциональность, позвонив [по телефону CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname).

## <a name="cbasetabbedpaneconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CBaseTabbedPane::ConvertToTabbedDocument

Преобразует одну или несколько доковых стекол в документы MDI.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>Параметры

*bActiveTabТолько*<br/>
(в) При преобразовании панели вкладок укажите TRUE, чтобы преобразовать только активную вкладку.

## <a name="cbasetabbedpanedetachpane"></a><a name="detachpane"></a>CBaseTabbedPane::DetachPane

Отсоединяет панель от панели с вкладками.

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Указатель на панель, чтобы отсоединить.

*bHide*<br/>
(в) Параметр Boolean, который определяет, скрывает ли фреймворк стекло после того, как оно отсоединяется.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если фреймворк успешно отсоединяет панель; FALSE, если *pBar* является NULL или относится к панели, которая не находится в панели вкладок.

### <a name="remarks"></a>Remarks

Рамки плавает отдельной панели, если это возможно. Для получения дополнительной информации [см. CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).

## <a name="cbasetabbedpaneenablesetcaptiontexttotabname"></a><a name="enablesetcaptiontexttotabname"></a>CBaseTabbedPane::EnableSetCaptionTextToTabName

Позволяет или отсутствует способность панели вкладок синхронизировать текст подписи с текстом этикетки на активной вкладке.

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для синхронизации подписи к панели вкладок с подписью активной вкладки; в противном случае, FALSE.

## <a name="cbasetabbedpanefilldefaulttabsorderarray"></a><a name="filldefaulttabsorderarray"></a>CBaseTabbedPane::FillDefaultTabsOrderArray

Восстанавливает внутренний порядок вкладки в состояние по умолчанию.

```
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>Remarks

Этот метод вызывается, когда фреймворк восстанавливает панель Outlook в исходное состояние.

## <a name="cbasetabbedpanefindpanebyid"></a><a name="findpanebyid"></a>CBaseTabbedPane:FindPaneByID

Возвращает панель, идентифицированную идентификатором панели.

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>Параметры

*uBarID*<br/>
(в) Упоняет идентификатор панели для поиска.

### <a name="return-value"></a>Возвращаемое значение

Указатель на панель, если она была найдена; в противном случае, NULL.

### <a name="remarks"></a>Remarks

Этот метод сравнивает все вкладки в панели и возвращает один с идентификатором, указанным параметром *uBarID.*

## <a name="cbasetabbedpanefindbarbytabnumber"></a><a name="findbarbytabnumber"></a>CBaseTabbedPane::FindBarByTabNumber

Возвращает панель, которая находится во вкладке.

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>Параметры

*nTabNum*<br/>
(в) Упогоняет нулевой индекс вкладки для извлечения.

*bGetWrappedBar*<br/>
(в) TRUE, чтобы вернуть основное (обернутое) окно стекла вместо самого стекла; в противном случае FALSE. Это относится только к стеклам, полученным из [CDockablePaneAdapter.](../../mfc/reference/cdockablepaneadapter-class.md)

### <a name="return-value"></a>Возвращаемое значение

Если панель найдена, возвращается действительный указатель на исцеляемый стекол; в противном случае, NULL.

### <a name="remarks"></a>Remarks

Вызовите этот метод для извлечения панели, проживающей в вкладке, указанной параметром *nTabNum.*

## <a name="cbasetabbedpanefloattab"></a><a name="floattab"></a>CBaseTabbedPane::FloatTab

Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в, вне) Указатель на панель, чтобы плавать.

*nTabID*<br/>
(в) Упогоняет нулевой индекс вкладки для плавания.

*dockMethod*<br/>
(в) Определяет метод использования для сделать панель поплавок. Дополнительные сведения см. в разделе «Примечания».

*bHide*<br/>
(в) ПРАВДА, чтобы скрыть стекло перед плавающей; в противном случае, FALSE.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель плавали; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы плавать панели, которая в настоящее время находится в съемной вкладке.

Если вы хотите, чтобы отделить панель программно, укажите DM_SHOW для *dockMethod* параметра. Если вы хотите, чтобы плавать панели в том же положении, где он плавал ранее, укажите DM_DBL_CLICK в качестве параметра *dockMethod.*

## <a name="cbasetabbedpanegetdefaulttabsorder"></a><a name="getdefaulttabsorder"></a>CBaseTabbedPane::GetDefaultTabsOrder

Возвращает порядок вкладок по умолчанию в панели.

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CArray` описывающий порядок вкладок по умолчанию в панели.

### <a name="remarks"></a>Remarks

Платформа вызывает этот метод при сбросить панель Outlook в исходное состояние.

## <a name="cbasetabbedpanegetfirstvisibletab"></a><a name="getfirstvisibletab"></a>CBaseTabbedPane::GetFirstVisibleTab

Извлекает указатель на первую отображаемую вкладку.

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>Параметры

*iTabNum*<br/>
(в) Ссылка на ряд. Этот метод записывает нулевой индекс первой отображаемых вкладок к этому параметру, или -1, если отображаемые вкладки не найдены.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха указатель на первую отображаемую вкладку; в противном случае, NULL.

## <a name="cbasetabbedpanegetminsize"></a><a name="getminsize"></a>CBaseTabbedPane::GetMinSize

Получает минимальный допустимый размер для панели.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Параметры

*Размер*<br/>
(ваут) Объект, `CSize` наполненный минимально допустимым размером.

### <a name="remarks"></a>Remarks

Если последовательная обработка минимальных размеров панели активна [(CPane::m_bHandleMinSize),](../../mfc/reference/cpane-class.md#m_bhandleminsize) *размер* заполняется минимальным допустимым размером для активной вкладки. В противном случае *размер* заполняется возвратным значением [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).

## <a name="cbasetabbedpanegetpaneicon"></a><a name="getpaneicon"></a>CBaseTabbedPane::GetPaneIcon

Получает минимальный допустимый размер для панели.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Параметры

*Размер*<br/>
(ваут) Объект, `CSize` наполненный минимально допустимым размером.

### <a name="remarks"></a>Remarks

Если последовательная обработка минимальных размеров панели активна [(CPane::m_bHandleMinSize),](../../mfc/reference/cpane-class.md#m_bhandleminsize) *размер* заполняется минимальным допустимым размером для активной вкладки. В противном случае *размер* заполняется возвратным значением [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).

## <a name="cbasetabbedpanegetpanelist"></a><a name="getpanelist"></a>CBaseTabbedPane::GetPaneList

Возвращает список стекол, которые содержатся в панели вкладок.

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>Параметры

*Lst*<br/>
(ваут) А, `CObList` который заполнен стекла, которые содержатся в вкладке панели.

*pRTCFilter*<br/>
(в) Если он не NULL, то в списке возвращается только стекла, относящиеся к указанному классу времени выполнения.

## <a name="cbasetabbedpanegettabarea"></a><a name="gettabarea"></a>CBaseTabbedPane::GetTabArea

Возвращает прямоугольники для верхних и нижних областей вкладки.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>Параметры

*rectTabAreaTop*<br/>
(ваут) Получает координаты экрана верхней области вкладки.

*rectTabAreaBottom*<br/>
(ваут) Получает координаты экрана нижней области вкладки.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы определить прямоугольники, в координатах экрана, для верхних и нижних областей вкладки.

## <a name="cbasetabbedpanegettabsnum"></a><a name="gettabsnum"></a>CBaseTabbedPane::GetTabsNum

Возвращает количество вкладок в окне вкладок.

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество вкладок в панели вкладок.

## <a name="cbasetabbedpanegetunderlyingwindow"></a><a name="getunderlyingwindow"></a>CBaseTabbedPane::GetUnderlyingWindow

Получает базовое (обертое) окно вкладок.

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовое окно вкладки.

## <a name="cbasetabbedpanegetvisibletabsnum"></a><a name="getvisibletabsnum"></a>CBaseTabbedPane::GetVisibleTabsNum

Возвращает количество видимых вкладок.

```
virtual int GetVisibleTabsNum() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество видимых вкладок, которые будут больше или равны нулю.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы определить количество видимых вкладок в панели вкладок.

## <a name="cbasetabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>CBaseTabbedPane::HasAutoHideMode

Определяет возможность переключения панели с вкладками в режим автоматического скрытия.

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель можно переключить в режим автохидирования; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Если режим автоматической hide отключен, ни одна кнопка контакта не отображается на заголовок панели вкладок.

## <a name="cbasetabbedpaneishidesingletab"></a><a name="ishidesingletab"></a>CBaseTabbedPane::IsHideSingleTab

Определяет, скрыто ли табло, если отображается только одна вкладка.

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если окно вкладки не отображается, когда есть только одна видимая вкладка; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Если панель не отображается из-за открытия только одной вкладки, можно вызвать этот метод, чтобы определить, правильно ли работает панель вкладок.

## <a name="cbasetabbedpaneremovepane"></a><a name="removepane"></a>CBaseTabbedPane::RemovePane

Удаляет панель из панели вкладок.

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в, вне) Указатель на панель, чтобы удалить из вкладки панели.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель была успешно удалена из панели вкладок, и если вкладки панели по-прежнему действительна. FALSE, если последнее стекло было удалено из панели вкладок и табло панель вот-вот будет уничтожена. Если значение возврата FALSE, не используйте панель вкладок больше.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы удалить панель, указанную параметром *pBar,* из панели вкладок.

## <a name="cbasetabbedpanesetautodestroy"></a><a name="setautodestroy"></a>CBaseTabbedPane::SetAutoDestroy

Определяет, будет ли панель управления вкладками уничтожена автоматически.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*bAutoDestroy*<br/>
(в) ПРАВДА, если вкладки панели был создан динамически, и вы не контролируете его жизни; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Установите режим автоматического уничтожения, чтобы true, если вы создаете вкладку панели динамически, и если вы не контролируете его срок службы. Если режим автоматического уничтожения является правдой, табло будет автоматически уничтожено рамкой.

## <a name="cbasetabbedpaneshowtab"></a><a name="showtab"></a>CBaseTabbedPane::ShowTab

Показывает или скрывает вкладку.

```
virtual BOOL ShowTab(
    CWnd* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Указатель на панель, чтобы показать или скрыть.

*bShow*<br/>
(в) TRUE, чтобы показать панель; FALSE, чтобы скрыть панель.

*bDelay*<br/>
(в) TRUE для задержки регулировки макета вкладки; в противном случае, FALSE.

*bActivate*<br/>
(в) TRUE, чтобы сделать вкладку активной вкладкой; в противном случае, FALSE.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если вкладка была либо показана или скрыта успешно; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

При вызове этого метода панель отображается или скрыта, в зависимости от значения параметра *bShow.* Если вы скрываете вкладку, и это последняя видимая вкладка в базовом окне вкладки, панель вкладок скрыта. Если вы показываете вкладку, когда ранее не было видимых вкладок, отображается панель вкладок.

## <a name="cbasetabbedpanerecalclayout"></a><a name="recalclayout"></a>CBaseTabbedPane::RecalcLayout

Пересчитывает информацию о макете для панели.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Remarks

Если панель плавает, этот метод уведомляет фреймворк для перебазирования панели до текущего размера мини-кадра.

Если панель пристыкована, этот метод ничего не делает.

## <a name="cbasetabbedpanesetautohidemode"></a><a name="setautohidemode"></a>CBaseTabbedPane::SetAutoHideMode

Устанавливает режим автоматической скрытности для съемных стекол в панели вкладок.

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>Параметры

*bMode*<br/>
(в) TRUE для включения режима автоматической скрытности; FALSE для включения регулярного режима стыковки.

*dwAlignment*<br/>
(в) Определяет выравнивание автоматического стекла, которое должно быть создано. Список возможных значений можно узнать на примере [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).

*pCurrAutoHideBar*<br/>
(в, вне) Указатель на текущую панель инструментов автоматического сокрытия. Может иметь значение NULL.

*bUseTimer*<br/>
(в) Уточняется, следует ли использовать эффект автоматической скрытности при переключении панели в режим автоматической скрытности или немедленно скрыть панель.

### <a name="return-value"></a>Возвращаемое значение

Указатель на панель инструментов автоматического сокрытия, которая создается при переходе в режим автоматической скрытности, или NULL, если панель инструментов не создана.

### <a name="remarks"></a>Remarks

Рамка вызывает этот метод, когда пользователь выбирает кнопку контакта для переключения табло в режим автоматической скрытности или в обычный режим стыковки.

Режим автоматической скрытности установлен для каждого съемного стекла в панели вкладок. Панели, которые не являются съежеными, игнорируются. Для получения дополнительной информации [см. CMFCBaseTabCtrl::EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).

Вызовите этот метод, чтобы переключить панель вкладок в режим автоматического сокрытия программно. Панель должна быть пристыкована к окну основной рамы [(CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) должен вернуть действительный указатель на [CPaneDivider).](../../mfc/reference/cpanedivider-class.md)

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
