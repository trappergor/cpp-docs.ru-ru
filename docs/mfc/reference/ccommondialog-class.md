---
title: Класс CCommonDialog
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 4fa7aa51d1ce482e00f68365045cd35c3fb7939b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264876"
---
# <a name="ccommondialog-class"></a>Класс CCommonDialog

Базовый класс для классов, которые инкапсулируют функцию общих диалоговых окон Windows.

## <a name="syntax"></a>Синтаксис

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CCommonDialog::CCommonDialog](#ccommondialog)|Создает объект `CCommonDialog`.|

## <a name="remarks"></a>Примечания

Следующие классы инкапсулируют функцию общих диалоговых окон Windows:

- [CFileDialog](../../mfc/reference/cfiledialog-class.md)

- [CFontDialog](../../mfc/reference/cfontdialog-class.md)

- [CColorDialog](../../mfc/reference/ccolordialog-class.md)

- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)

- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)

- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)

- [Диалоговое окно CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)

- [COleDialog](../../mfc/reference/coledialog-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CCommonDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

##  <a name="ccommondialog"></a>  CCommonDialog::CCommonDialog

Создает объект `CCommonDialog`.

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указывает на объект окна родительский объект или владельца (типа [CWnd](../../mfc/reference/cwnd-class.md)), которому принадлежит объект диалогового окна. Если это значение NULL, родительское окно объекта диалогового окна будет присвоено главного окна приложения.

### <a name="remarks"></a>Примечания

См. в разделе [CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog) полные сведения.

## <a name="see-also"></a>См. также

[Класс CDialog](../../mfc/reference/cdialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFileDialog](../../mfc/reference/cfiledialog-class.md)<br/>
[Класс CFontDialog](../../mfc/reference/cfontdialog-class.md)<br/>
[Класс CColorDialog](../../mfc/reference/ccolordialog-class.md)<br/>
[Класс CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)<br/>
[Класс CPrintDialog](../../mfc/reference/cprintdialog-class.md)<br/>
[Класс CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
