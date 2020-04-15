---
title: CMFCDesktopAlertWndButton класс
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
ms.openlocfilehash: 5b18a15f8bfd98396acae0558d121b32bc4127c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367629"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton класс

Позволяет добавлять кнопки в диалоговую будку оповещения на рабочем столе.

## <a name="syntax"></a>Синтаксис

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Конструктор по умолчанию.|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|Определяет, отображается ли кнопка в области заголовка диалогового окна оповещения.|
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|Определяет, закрывает ли кнопка диалоговую будку оповещения.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|Имя|Описание|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Значение Boolean, которое определяет, отображается ли кнопка в области заголовка диалогового окна.|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Значение Boolean, которое определяет, закрывает ли кнопка диалоговую окно оповещения.|

### <a name="remarks"></a>Remarks

По умолчанию конструктор устанавливает `m_bIsCaptionButton` `m_bIsCloseButton` и членов данных false. Родительский `CMFCDesktopAlertDialog` объект `m_bIsCaptionButton` устанавливается к TRUE, если кнопка расположена в области заголовка диалогового окна оповещения. Класс `CMFCDesktopAlertDialog` создает `CMFCDesktopAlertWndButton` объект, который служит в качестве кнопки, которая `m_bIsCloseButton` закрывает окно диалога оповещения и устанавливает на TRUE.

Добавляйте `CMFCDesktopAlertWndButton` объекты к объекту по мере добавления любой `CMFCDesktopAlertDialog` кнопки. Для получения `CMFCDesktopAlertDialog`дополнительной информации о , см. [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)

## <a name="example"></a>Пример

В следующем примере показано, `SetImage` как `CMFCDesktopAlertWndButton` использовать метод в классе. Этот фрагмент кода является частью [образца демо-версии оповещения рабочего стола.](../../overview/visual-cpp-samples.md)

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

## <a name="cmfcdesktopalertwndbuttoniscaptionbutton"></a><a name="iscaptionbutton"></a>CMFCDesktopAlertWndButton::IsCaptionButton

Определяет, отображается ли кнопка в области заголовка диалогового окна оповещения.

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка отображается в области заголовка диалогового окна; в противном случае, 0.

## <a name="cmfcdesktopalertwndbuttonisclosebutton"></a><a name="isclosebutton"></a>CMFCDesktopAlertWndButton::IsCloseButton

Определяет, закрывает ли кнопка диалоговую будку оповещения.

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка закрывает окно диалога оповещения; в противном случае, 0.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)
