---
title: Класс COleUpdateDialog
ms.date: 11/04/2016
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
ms.openlocfilehash: 74607a2a145025533c660ae68f20ffb8e59d3fad
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281737"
---
# <a name="coleupdatedialog-class"></a>Класс COleUpdateDialog

Используется в особых случаях в диалоговом окне OLE "Изменить ссылки", которое используется при необходимости обновления только существующих связанных или внедренных объектов в документе.

## <a name="syntax"></a>Синтаксис

```
class COleUpdateDialog : public COleLinksDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|Создает объект `COleUpdateDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleUpdateDialog::DoModal](#domodal)|Отображает **изменить ссылки** диалоговое окно в режиме обновления.|

## <a name="remarks"></a>Примечания

Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

[COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

`COleUpdateDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

##  <a name="coleupdatedialog"></a>  COleUpdateDialog::COleUpdateDialog

Создает объект `COleUpdateDialog`.

```
explicit COleUpdateDialog(
    COleDocument* pDoc,
    BOOL bUpdateLinks = TRUE,
    BOOL bUpdateEmbeddings = FALSE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указывает на документ, содержащий ссылки, может потребоваться обновление.

*bUpdateLinks*<br/>
Флаг, который определяет, является ли связанные объекты должны быть обновлены.

*bUpdateEmbeddings*<br/>
Флаг, который определяет, является ли внедренные объекты должны быть обновлены.

*pParentWnd*<br/>
Указывает на объект окна родительский объект или владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если это значение NULL, родительского окна окно будет присвоено главного окна приложения.

### <a name="remarks"></a>Примечания

Эта функция создает только `COleUpdateDialog` объекта. Чтобы отобразить диалоговое окно, вызовите [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Этот класс следует использовать вместо `COleLinksDialog` при необходимости обновления только существующих связанных или внедренных элементов.

##  <a name="domodal"></a>  COleUpdateDialog::DoModal

Появляется диалоговое окно Изменение связей в режим обновления.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если диалоговое окно успешно возвращен.

- IDCANCEL, если ни один из связанных или внедренных элементов в текущем документе необходимо обновить.

- IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функция-член для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок, см. в разделе [OleUIEditLinks](/windows/desktop/api/oledlg/nf-oledlg-oleuieditlinksa) функции в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Все ссылки и (или) векторные представления обновляются, если пользователь выбирает кнопки "Отмена".

## <a name="see-also"></a>См. также

[Пример MFC OCLIENT](../../visual-cpp-samples.md)<br/>
[Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)
