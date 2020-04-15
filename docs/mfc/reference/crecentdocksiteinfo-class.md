---
title: Класс CRecentDockSiteInfo
ms.date: 11/04/2016
f1_keywords:
- CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::CleanUp
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDefaultPaneDivider
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedPercent
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedRect
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentListOfPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentPaneContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentTabContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::Init
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::IsRecentLeftPane
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SaveListOfRecentPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SetInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::StoreDockInfo
helpviewer_keywords:
- CRecentDockSiteInfo [MFC], CleanUp
- CRecentDockSiteInfo [MFC], GetRecentDefaultPaneDivider
- CRecentDockSiteInfo [MFC], GetRecentDockedPercent
- CRecentDockSiteInfo [MFC], GetRecentDockedRect
- CRecentDockSiteInfo [MFC], GetRecentListOfPanes
- CRecentDockSiteInfo [MFC], GetRecentPaneContainer
- CRecentDockSiteInfo [MFC], GetRecentTabContainer
- CRecentDockSiteInfo [MFC], Init
- CRecentDockSiteInfo [MFC], IsRecentLeftPane
- CRecentDockSiteInfo [MFC], SaveListOfRecentPanes
- CRecentDockSiteInfo [MFC], SetInfo
- CRecentDockSiteInfo [MFC], StoreDockInfo
ms.assetid: 2dd14f95-d5a2-4461-a7a5-2c6c36a3a165
ms.openlocfilehash: d2178881ea18f9dc5300bde838b01a516e6bb395
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370926"
---
# <a name="crecentdocksiteinfo-class"></a>Класс CRecentDockSiteInfo

Класс `CRecentDockSiteInfo` является классом помощника, который хранит последние сведения о состоянии для [класса CPane.](../../mfc/reference/cpane-class.md)

## <a name="syntax"></a>Синтаксис

```
class CRecentDockSiteInfo : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CRecentDockSiteInfo::CRecentDockSiteInfo`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRecentDockSiteInfo::CleanUp](#cleanup)||
|[CRecentDockSiteInfo::GetRecentDefaultPaneDivider](#getrecentdefaultpanedivider)||
|[CRecentDockSiteInfo::GetRecentDockedPercent](#getrecentdockedpercent)||
|[CRecentDockSiteInfo::GetRecentDockedRect](#getrecentdockedrect)||
|[CRecentDockSiteInfo::GetRecentListOfPanes](#getrecentlistofpanes)||
|[CRecentDockSiteInfo::GetRecentPaneContainer](#getrecentpanecontainer)||
|[CRecentDockSiteInfo::GetRecentTabContainer](#getrecenttabcontainer)||
|[CRecentDockSiteInfo::Init](#init)||
|[CRecentDockSiteInfo::IsRecentLeftPane](#isrecentleftpane)||
|[CRecentDockSiteInfo::оператор](#operator_eq)||
|[CRecentDockSiteInfo::SaveListOfRecentPanes](#savelistofrecentpanes)||
|[CRecentDockSiteInfo::SetInfo](#setinfo)||
|[CRecentDockSiteInfo::StoreDockInfo](#storedockinfo)||

## <a name="remarks"></a>Remarks

Класс `CRecentDockSiteInfo` предназначен для управления данными. Он отслеживает последнее состояние объекта `CPane` при переходе от закрепленного режима к плавающему. Когда пользователь дважды щелкает плавающую закрепляемую панель, она становится закрепленной. Дважды щелкнув закрепленную панель, можно вернуть ее на прежнее место, с прежним размером и состоянием. Аналогичным образом повторное закрепление возвращает панель на предыдущее место закрепления. Именно этот класс данных открывает эту возможность. Поскольку члены этого класса хранят сведения о состоянии закрепленной панели, они не должны напрямую изменяться вашим приложением.

Объект `CRecentDockSiteInfo` создается при каждом создании панели. Каждый `CPane` объект имеет переменную члена, [CPane::m_recentDockInfo,](../../mfc/reference/cpane-class.md#m_recentdockinfo)для хранения этой информации.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrecentDockSiteInfo.h

## <a name="crecentdocksiteinfocleanup"></a><a name="cleanup"></a>CRecentdockSiteInfo::Очистка

```
void CleanUp();
```

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfocrecentdocksiteinfo"></a><a name="crecentdocksiteinfo"></a>CRecentDockSiteInfo::CRecentDockSiteInfo

```
CRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfogetrecentdefaultpanedivider"></a><a name="getrecentdefaultpanedivider"></a>CRecentDockSiteInfo::GetRecentDefaultPaneDivider

```
CPaneDivider* GetRecentDefaultPaneDivider();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfogetrecentdockedpercent"></a><a name="getrecentdockedpercent"></a>CRecentDockSiteInfo:GetRecentDockedPercent

```
int GetRecentDockedPercent(BOOL bForSlider);
```

### <a name="parameters"></a>Параметры

(в) *bForSlider*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfogetrecentdockedrect"></a><a name="getrecentdockedrect"></a>CRecentDockSiteInfo:GetRecentDockedRect

```
CRect& GetRecentDockedRect(BOOL bForSlider);
```

### <a name="parameters"></a>Параметры

(в) *bForSlider*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfogetrecentlistofpanes"></a><a name="getrecentlistofpanes"></a>CRecentdockSiteinfo:GetRecentListOfPanes

```
CList<HWND, HWND>& GetRecentListOfPanes(BOOL bForSlider);
```

### <a name="parameters"></a>Параметры

(в) *bForSlider*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfogetrecentpanecontainer"></a><a name="getrecentpanecontainer"></a>CRecentDockSiteInfo:GetRecentPaneContainer

```
CPaneContainer* GetRecentPaneContainer(BOOL bForSlider);
```

### <a name="parameters"></a>Параметры

(в) *bForSlider*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfogetrecenttabcontainer"></a><a name="getrecenttabcontainer"></a>CRecentDockSiteInfo::GetRecentTabContainer

```
CPaneContainer* GetRecentTabContainer(BOOL bForSlider);
```

### <a name="parameters"></a>Параметры

(в) *bForSlider*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfoinit"></a><a name="init"></a>CRecentdockSiteinfo::Init

```
void Init();
```

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfoisrecentleftpane"></a><a name="isrecentleftpane"></a>CRecentDockSiteInfo::IsrecentLeftPane

```
BOOL IsRecentLeftPane(BOOL bForSlider);
```

### <a name="parameters"></a>Параметры

(в) *bForSlider*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfooperator-"></a><a name="operator_eq"></a>CRecentDockSiteInfo::оператор

```
CRecentDockSiteInfo& operator=(CRecentDockSiteInfo& src);
```

### <a name="parameters"></a>Параметры

(в) *src*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfosavelistofrecentpanes"></a><a name="savelistofrecentpanes"></a>CRecentdockSiteinfo:SaveListOfRecentPanes

```
void SaveListOfRecentPanes(CList<HWND,
    HWND>& lstOrg,
    BOOL bForSlider);
```

### <a name="parameters"></a>Параметры

(в) *CList<HWND*<br/>
(в) *lstOrg*<br/>
(в) *bForSlider*<br/>

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfosetinfo"></a><a name="setinfo"></a>CRecentDockSiteInfo::SetInfo

```
virtual void SetInfo(
    BOOL bForSlider,
    CRecentDockSiteInfo& srcInfo);
```

### <a name="parameters"></a>Параметры

(в) *bForSlider*<br/>
(в) *srcInfo*<br/>

### <a name="remarks"></a>Remarks

## <a name="crecentdocksiteinfostoredockinfo"></a><a name="storedockinfo"></a>CRecentDockSiteInfo::StoreDockInfo

```
virtual void StoreDockInfo(
    CPaneContainer* pRecentContainer,
    CDockablePane* pTabbedBar = NULL);
```

### <a name="parameters"></a>Параметры

(в) *pRecentContainer*<br/>
(в) *pTabbedBar*<br/>

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite Class](../../mfc/reference/cdocksite-class.md)
