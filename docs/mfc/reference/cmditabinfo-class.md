---
title: Класс CMDITabInfo
ms.date: 11/04/2016
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
ms.openlocfilehash: 30bf7726b35d762be2bbbd119e0303894879cd3d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752651"
---
# <a name="cmditabinfo-class"></a>Класс CMDITabInfo

Класс `CMDITabInfo` используется для передачи параметров методу [CMDIFrameWndEx::EnableMDITabbedGroups.](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) Задайте элементы этого класса, чтобы контролировать поведение групп вкладок MDI.

## <a name="syntax"></a>Синтаксис

```
class CMDITabInfo
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMDITabInfo::CMDITabInfo`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMDITabInfo::Serialize](#serialize)|Считывает этот объект из архива или записывает в него.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Определяет, отображается ли кнопка **«Закрыть»** на этикетке активной вкладки.|
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|Уточняется, следует ли окрасить вкладки MDI.|
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Определяет, отображает ли группа вкладок всплывающее меню, в которое отображается список открытых документов или отображает кнопки прокрутки.|
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Определяет, может ли пользователь поменять позиции вкладок путем перетаскивания.|
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Определяет, есть ли вкладки с плоской рамой.|
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Определяет, отображает ли каждая метка вкладок кнопку **«Закрыть».**|
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Уточняется, включены ли пользовательские наборы инструментов.|
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|Определяет, следует ли отображать значки на вкладках MDI.|
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Определяет размер границы каждого окна вкладки.|
|[CMDITabInfo::m_style](#m_style)|Определяет стиль меток вкладок.|
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Определяет, расположены ли метки вкладок в верхней или нижней части страницы.|

## <a name="remarks"></a>Remarks

Этот класс определяет параметры групп вкладок MDI, которые создает платформа.

## <a name="example"></a>Пример

В следующем примере показано, как установить значения различных переменных членов в `CMDITabInfo` классе.

[!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxmdiclientareawnd.h

## <a name="cmditabinfom_bactivetabclosebutton"></a><a name="m_bactivetabclosebutton_"></a>CMDITabInfo::m_bActiveTabCloseButton;

Определяет, отображается ли кнопка **«Закрыть»** на этикетке активной вкладки.

```
BOOL m_bActiveTabCloseButton;
```

### <a name="remarks"></a>Remarks

Если TRUE, метка активной вкладке будет отображать кнопку **"Закрыть".** Кнопка **«Закрыть»** будет удалена из правого верхнего угла области вкладки. В противном случае на метке активной вкладки не отображается кнопка **«Закрыть».** Кнопка **«Закрыть»** появится в правом верхнем углу области вкладки.

## <a name="cmditabinfom_bautocolor"></a><a name="m_bautocolor"></a>CMDITabInfo::m_bAutoColor

Определяет, имеет ли каждая вкладка MDI свой собственный цвет.

```
BOOL m_bAutoColor;
```

### <a name="remarks"></a>Remarks

Если правда, каждая вкладка будет иметь свой собственный цвет. Набор цветов управляется библиотекой MFC. В противном случае вкладки отображаются белым цветом. Значение по умолчанию — FALSE.

## <a name="cmditabinfom_bdocumentmenu"></a><a name="m_bdocumentmenu"></a>CMDITabInfo::m_bDocumentMenu

Определяет, отображает ли каждая вкладка всплывающее меню, показующее список открытых документов на правом краю области вкладки.

```
BOOL m_bDocumentMenu;
```

### <a name="remarks"></a>Remarks

Если true, каждое окно вкладки отображает всплывающее меню, которое показывает список открытых документов на правом краю области вкладки; В противном случае окно вкладки отображает кнопки прокрутки на правом краю области вкладки. Значение по умолчанию — FALSE.

## <a name="cmditabinfom_benabletabswap"></a><a name="m_benabletabswap"></a>CMDITabInfo::m_bEnableTabSwap

Определяет, может ли пользователь поменять позиции вкладок путем перетаскивания.

```
BOOL m_bEnableTabSwap;
```

### <a name="remarks"></a>Remarks

Если это правда, пользователь может изменить позиции вкладок, перетащив вкладки. В противном случае пользователь не может изменить позиции вкладок. Значение по умолчанию — TRUE.

## <a name="cmditabinfom_bflatframe"></a><a name="m_bflatframe"></a>CMDITabInfo::m_bFlatFrame

Определяет, имеет ли каждое окно вкладки плоскую рамку.

```
BOOL m_bFlatFrame;
```

## <a name="cmditabinfom_btabclosebutton"></a><a name="m_btabclosebutton"></a>CMDITabInfo::m_bTabCloseButton

Определяет, отображает ли каждое окно вкладки кнопку **«Закрыть».**

```
BOOL m_bTabCloseButton;
```

### <a name="remarks"></a>Remarks

Если правда, каждое окно вкладки отображает кнопку **"Закрыть"** на правом краю вкладки. В противном случае кнопка **"Закрыть"** не отображается. Значение по умолчанию — TRUE.

## <a name="cmditabinfom_btabcustomtooltips"></a><a name="m_btabcustomtooltips"></a>CMDITabInfo::m_bTabCustomTooltips

Определяет, отображаются ли вкладки на панели инструментов.

```
BOOL m_bTabCustomTooltips;
```

### <a name="remarks"></a>Remarks

Если это правда, приложение отправляет AFX_WM_ON_GET_TAB_TOOLTIP сообщение в основной кадр. Вы можете обрабатывать это сообщение с помощью ON_REGISTERED_MESSAGE макроса.

## <a name="cmditabinfom_btabicons"></a><a name="m_btabicons"></a>CMDITabInfo::m_bTabIcons

Определяет, следует ли отображать значки на вкладках MDI.

```
BOOL m_bTabIcons;
```

### <a name="remarks"></a>Remarks

Если true, значки отображаются на каждой вкладке MDI. В противном случае, значки не отображаются на вкладках. Значение по умолчанию — FALSE.

## <a name="cmditabinfom_ntabbordersize"></a><a name="m_ntabbordersize"></a>CMDITabInfo::m_nTabBorderSize

Определяет размер границы в пикселях каждого окна вкладки.

```
int m_nTabBorderSize;
```

### <a name="remarks"></a>Remarks

[CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) возвращает значение по умолчанию.

## <a name="cmditabinfom_style"></a><a name="m_style"></a>CMDITabInfo::m_style

Определяет стиль меток вкладок.

```
CMFCTabCtrl::Style m_style
```

### <a name="remarks"></a>Remarks

Укажите один из следующих стилей для меток вкладок:

|||
|-|-|
|STYLE_3D|3D-стиль.  |
|STYLE_3D_ONENOTE|Стиль Microsoft OneNote.  |
|STYLE_3D_VS2005|Microsoft Visual Studio 2005 стиль.  |
|STYLE_3D_SCROLLED|3D-стиль с этикетками прямоугольников.  |
|STYLE_FLAT_SHARED_HORZ_SCROLL|Плоский стиль с общим горизонтальным баром прокрутки.  |
|STYLE_3D_ROUNDED_SCROLL|3D-стиль с круглыми метками вкладок.  |

## <a name="cmditabinfom_tablocation"></a><a name="m_tablocation"></a>CMDITabInfo::m_tabLocation

Определяет, расположены ли метки вкладок в верхней или нижней части страницы.

```
CMFCTabCtrl::Location m_tabLocation;
```

### <a name="remarks"></a>Remarks

Нанесите на вкладки один из следующих флагов местоположения:

- LOCATION_BOTTOM: метки вкладок расположены в нижней части страницы.

- LOCATION_TOP: метки вкладок расположены в верхней части страницы

## <a name="cmditabinfoserialize"></a><a name="serialize"></a>CMDITabInfo::Serialize

Читает или пишет этот объект из архива или в архив.

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
(в) Объект [класса CArchive](../../mfc/reference/carchive-class.md) для сериализации.

## <a name="see-also"></a>См. также раздел

[Класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)<br/>
[MDI Tabbed групп](../../mfc/mdi-tabbed-groups.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
