---
title: Класс CMFCWindowsManagerDialog | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7889d5bb2d94d7501f20578efb984fe75908f2a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374700"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>Класс CMFCWindowsManagerDialog

`CMFCWindowsManagerDialog` Объекта позволяет пользователю управлять дочерними окнами MDI в приложении MDI.

## <a name="syntax"></a>Синтаксис

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Создает объект `CMFCWindowsManagerDialog`.|

## <a name="remarks"></a>Примечания

`CMFCWindowsManagerDialog` Содержит список дочерних MDI-окон, открытых в настоящий момент в приложении. Пользователь вручную можно контролировать состояние дочерних окон интерфейса MDI с помощью это диалоговое окно.

`CMFCWindowsManagerDialog` встроенный [класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md). `CMFCWindowsManagerDialog` Не является классом, который необходимо создать вручную. Вместо этого вызовите функцию [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog), и он будет создать и отобразить `CMFCWindowsManagerDialog` объекта.

## <a name="example"></a>Пример

В следующем примере демонстрируется создание `CMFCWindowsManagerDialog` путем вызова метода `CMDIFrameWndEx::ShowWindowsDialog`. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxWindowsManagerDialog.h

##  <a name="cmfcwindowsmanagerdialog"></a>  CMFCWindowsManagerDialog::CMFCWindowsManagerDialog

Создает [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) объекта.

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>Параметры

*pMDIFrame*<br/>
[in] Указатель на родительский объект или владельца окна.

*bHelpButton*<br/>
[in] Логический параметр, который указывает, отображает ли платформа **помочь** кнопки.

### <a name="remarks"></a>Примечания

Дополнительные сведения о диспетчеров визуального представления, см. в разделе [диспетчер визуализации](../../mfc/visualization-manager.md).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)
