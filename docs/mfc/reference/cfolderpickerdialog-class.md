---
title: Класс CFolderPickerDialog
ms.date: 11/04/2016
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: ba189badaa9b1605e3467526e7b92a18a1bb5a73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561308"
---
# <a name="cfolderpickerdialog-class"></a>Класс CFolderPickerDialog

Класс CFolderPickerDialog реализует CFileDialog в режиме выбора папки.

## <a name="syntax"></a>Синтаксис

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#cfolderpickerdialog__~cfolderpickerdialog)|Деструктор.|
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|Конструктор.|

## <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

##  <a name="cfolderpickerdialog"></a>  CFolderPickerDialog::CFolderPickerDialog

Конструктор.

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>Параметры

*lpszFolder*<br/>
Исходная папка.

*dwFlags*<br/>
Сочетание одного или нескольких флагов, которые дают возможность настройки диалогового окна.

*pParentWnd*<br/>
Указатель на окно родительский объект или владельца объекта поле диалогового окна.

*dwSize*<br/>
Размер структуры OPENFILENAME.

### <a name="remarks"></a>Примечания

##  <a name="_dtorcfolderpickerdialog"></a>  CFolderPickerDialog:: ~ CFolderPickerDialog

Деструктор.

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
