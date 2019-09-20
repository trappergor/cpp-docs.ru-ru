---
title: Класс Колелинксдиалог
ms.date: 11/04/2016
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
ms.openlocfilehash: 911108f9a231b752790abfdf86d1b4042d30b149
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504112"
---
# <a name="colelinksdialog-class"></a>Класс Колелинксдиалог

Используется для диалогового окна OLE "Изменить ссылки".

## <a name="syntax"></a>Синтаксис

```
class COleLinksDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Колелинксдиалог:: Колелинксдиалог](#colelinksdialog)|Создает объект `COleLinksDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Колелинксдиалог::D Омодал](#domodal)|Отображает диалоговое окно «Редактирование ссылок OLE».|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[COleLinksDialog::m_el](#m_el)|Структура типа ОЛЕУИЕДИТЛИНКС, которая управляет поведением диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект класса `COleLinksDialog` , если нужно вызвать это диалоговое окно. После создания объекта `COleLinksDialog` можно использовать структуру [m_el](#m_el) для инициализации значений или состояний элементов управления в диалоговом окне. `m_el` Структура имеет тип олеуиедитлинкс. Дополнительные сведения об использовании этого класса диалогового окна см. в описании функции члена [DoModal](#domodal) .

> [!NOTE]
>  Созданный мастером приложений код контейнера использует этот класс.

Дополнительные сведения см. в описании структуры [олеуиедитлинкс](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) в Windows SDK.

Дополнительные сведения о диалоговых окнах, связанных с OLE, см. в разделе [диалоговые окна статьи в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

[коледиалог](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксодлгс. h

##  <a name="domodal"></a>Колелинксдиалог::D Омодал

Отображает диалоговое окно «Редактирование ссылок OLE».

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- ИДОК, если диалоговое окно было успешно отображено.

- ИДКАНЦЕЛ, если пользователь отменил диалоговое окно.

- ИДАБОРТ, если произошла ошибка. Если возвращается идаборт, вызовите `COleDialog::GetLastError` функцию-член, чтобы получить дополнительные сведения о типе произошедшей ошибки. Список возможных ошибок см. в описании функции [олеуиедитлинкс](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) в Windows SDK.

### <a name="remarks"></a>Примечания

Если требуется инициализировать различные элементы управления диалогового окна путем установки элементов структуры [m_el](#m_el) , следует выполнить их перед вызовом метода `DoModal`, но после создания объекта диалогового окна.

##  <a name="colelinksdialog"></a>Колелинксдиалог:: Колелинксдиалог

Создает объект `COleLinksDialog`.

```
COleLinksDialog (
    COleDocument* pDoc,
    CView* pView,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указывает на документ OLE, содержащий ссылки для изменения.

*pView*<br/>
Указывает на текущее представление в *pDoc*.

*dwFlags*<br/>
Флаг создания, который содержит 0 или ELF_SHOWHELP, чтобы указать, будет ли отображаться кнопка "Справка" при отображении диалогового окна.

*ппарентвнд*<br/>
Указывает на родительский элемент или объект окна-владельца ( `CWnd`типа), которому принадлежит объект диалогового окна. Если это значение равно NULL, родительскому окну диалогового окна присваивается основное окно приложения.

### <a name="remarks"></a>Примечания

Эта функция конструирует только `COleLinksDialog` объект. Чтобы открыть диалоговое окно, вызовите функцию [DoModal](#domodal) .

##  <a name="m_el"></a>Колелинксдиалог:: m_el

Структура типа ОЛЕУИЕДИТЛИНКС, используемая для управления поведением диалогового окна "изменение ссылок".

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>Примечания

Члены этой структуры можно изменять напрямую или с помощью функций-членов.

Дополнительные сведения см. в описании структуры [олеуиедитлинкс](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
