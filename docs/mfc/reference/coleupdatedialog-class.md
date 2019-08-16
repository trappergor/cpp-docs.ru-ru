---
title: Класс Колеупдатедиалог
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
ms.openlocfilehash: 150e78b7880a61343db21c3c787ffdd1f0b734a5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503173"
---
# <a name="coleupdatedialog-class"></a>Класс Колеупдатедиалог

Используется в особых случаях в диалоговом окне OLE "Изменить ссылки", которое используется при необходимости обновления только существующих связанных или внедренных объектов в документе.

## <a name="syntax"></a>Синтаксис

```
class COleUpdateDialog : public COleLinksDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Колеупдатедиалог:: Колеупдатедиалог](#coleupdatedialog)|Создает объект `COleUpdateDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Колеупдатедиалог::D Омодал](#domodal)|Отображает диалоговое окно **изменение ссылок** в режиме обновления.|

## <a name="remarks"></a>Примечания

Дополнительные сведения о диалоговых окнах, связанных с OLE, см. в разделе [диалоговые окна статьи в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

[коледиалог](../../mfc/reference/coledialog-class.md)

[колелинксдиалог](../../mfc/reference/colelinksdialog-class.md)

`COleUpdateDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксодлгс. h

##  <a name="coleupdatedialog"></a>Колеупдатедиалог:: Колеупдатедиалог

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
Указывает документ, содержащий ссылки, которые могут потребоваться для обновления.

*бупдателинкс*<br/>
Флаг, который определяет, следует ли обновлять связанные объекты.

*бупдатимбеддингс*<br/>
Флаг, определяющий, следует ли обновлять внедренные объекты.

*ппарентвнд*<br/>
Указывает на родительский элемент или объект окна-владельца ( `CWnd`типа), которому принадлежит объект диалогового окна. Если значение равно NULL, то родительское окно диалогового окна будет установлено в главное окно приложения.

### <a name="remarks"></a>Примечания

Эта функция конструирует только `COleUpdateDialog` объект. Чтобы открыть диалоговое окно, вызовите [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Этот класс следует использовать вместо `COleLinksDialog` , если требуется обновить только существующие связанные или внедренные элементы.

##  <a name="domodal"></a>Колеупдатедиалог::D Омодал

Отображает диалоговое окно изменение ссылок в режиме обновления.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- ИДОК, если диалоговое окно успешно возвращено.

- ИДКАНЦЕЛ, если ни один из связанных или внедренных элементов в текущем документе не нуждается в обновлении.

- ИДАБОРТ, если произошла ошибка. Если возвращается ИДАБОРТ, вызовите функцию-член [коледиалог:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) , чтобы получить дополнительные сведения о типе произошедшей ошибки. Список возможных ошибок см. в описании функции [олеуиедитлинкс](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) в Windows SDK.

### <a name="remarks"></a>Примечания

Все ссылки и (или) внедрения обновляются, пока пользователь не нажмет кнопку Отмена.

## <a name="see-also"></a>См. также

[Пример OCLIENT MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)
