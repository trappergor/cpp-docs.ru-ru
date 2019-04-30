---
title: Класс CMFCDesktopAlertWndButton
ms.date: 11/04/2016
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
ms.openlocfilehash: 639342e0a09a6e970478fce1b5aac629f03c2015
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403663"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>Класс CMFCDesktopAlertWndButton

Позволяет кнопки для добавления в классических оповещений диалоговое окно.

## <a name="syntax"></a>Синтаксис

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|name|Описание|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Конструктор по умолчанию.|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|name|Описание|
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|Определяет, отображается ли кнопка в области заголовка диалогового окна предупреждения.|
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|Определяет, ли кнопки закрывает диалоговое окно предупреждения.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|name|Описание|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Логическое значение, указывающее, отображается ли кнопка в области заголовка диалогового окна предупреждения.|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Логическое значение, указывающее, закрывает ли кнопки диалогового окна предупреждения.|

### <a name="remarks"></a>Примечания

По умолчанию, конструктор задает `m_bIsCaptionButton` и `m_bIsCloseButton` данные-члены в значение FALSE. Родительский `CMFCDesktopAlertDialog` набора объектов `m_bIsCaptionButton` значение true, если кнопка находится в области заголовка диалогового окна предупреждения. `CMFCDesktopAlertDialog` Класс создает `CMFCDesktopAlertWndButton` объект, который служит в качестве кнопки, которая закрывает диалоговое окно предупреждения, поле и задает `m_bIsCloseButton` значение true.

Добавить `CMFCDesktopAlertWndButton` объектов `CMFCDesktopAlertDialog` как вы добавляете любой кнопки. Дополнительные сведения о `CMFCDesktopAlertDialog`, см. в разделе [класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md).

## <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `SetImage` метод в `CMFCDesktopAlertWndButton` класса. Этот фрагмент кода является частью [Desktop оповещения демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdesktopalertwnd.h

##  <a name="iscaptionbutton"></a>  CMFCDesktopAlertWndButton::IsCaptionButton

Определяет, отображается ли кнопка в области заголовка диалогового окна предупреждения.

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка отображается в области заголовка диалогового окна предупреждения; в противном случае — 0.

##  <a name="isclosebutton"></a>  CMFCDesktopAlertWndButton::IsCloseButton

Определяет, ли кнопки закрывает диалоговое окно предупреждения.

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопки закрывает окно диалоговое окно предупреждения; в противном случае — 0.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)
