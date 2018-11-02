---
title: Класс COleDialog
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: c798c1ad81395465e7aa5405ab786ddfb67b71d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494709"
---
# <a name="coledialog-class"></a>Класс COleDialog

Предоставляет стандартные функции для диалоговых окон OLE.

## <a name="syntax"></a>Синтаксис

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDialog::GetLastError](#getlasterror)|Получает код ошибки, возвращаемый диалоговым окном.|

## <a name="remarks"></a>Примечания

Библиотеки Microsoft Foundation Class предоставляет несколько классов, производных от `COleDialog`:

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

##  <a name="getlasterror"></a>  COleDialog::GetLastError

Вызовите `GetLastError` функция-член для получения дополнительных сведений об ошибке при `DoModal` возвращает IDABORT.

```
UINT GetLastError() const;
```

### <a name="return-value"></a>Возвращаемое значение

Коды ошибок, возвращенные `GetLastError` зависят от конкретного диалогового окна.

### <a name="remarks"></a>Примечания

См. в разделе `DoModal` функция-член в производных классах, сведения о специальных сообщений об ошибках.

## <a name="see-also"></a>См. также

[Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

