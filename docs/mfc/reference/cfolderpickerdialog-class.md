---
title: Класс CFolderPickerDialog | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
dev_langs:
- C++
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d80839fca18d62c5fa9a9432296777c546268c5b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411435"
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
