---
title: Класс COleInsertDialog | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
dev_langs:
- C++
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f279472e0783498b3d175ab55c605fa7c7e7286b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416919"
---
# <a name="coleinsertdialog-class"></a>Класс COleInsertDialog

Используется для диалогового окна OLE "Вставить объект".

## <a name="syntax"></a>Синтаксис

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Создает объект `COleInsertDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleInsertDialog::CreateItem](#createitem)|Создает элемента, выбранного в диалоговом окне.|
|[COleInsertDialog::DoModal](#domodal)|Отображает диалоговое окно вставки объекта OLE.|
|[COleInsertDialog::GetClassID](#getclassid)|Возвращает идентификатор CLSID, связанный с выбранным элементом.|
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Указывает, следует ли рисовать элемента в виде значка.|
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Получает дескриптор метафайла, связанных с формой, преобразованного в значок этого элемента.|
|[COleInsertDialog::GetPathName](#getpathname)|Получает полный путь к файлу, выбранному в диалоговом окне.|
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Получает тип выбранного объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleInsertDialog::m_io](#m_io)|Структура типа OLEUIINSERTOBJECT, которое управляет поведением окна.|

## <a name="remarks"></a>Примечания

Создайте объект класса `COleInsertDialog` при необходимости вызвать это диалоговое окно. После `COleInsertDialog` объект был создан, можно использовать [m_io](#m_io) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_io` Структуры имеет тип OLEUIINSERTOBJECT. Дополнительные сведения об использовании этого класса диалогового окна см. в разделе [DoModal](#domodal) функция-член.

> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.

Дополнительные сведения см. в разделе [OLEUIINSERTOBJECT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta) структуры в пакете Windows SDK.

Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

##  <a name="coleinsertdialog"></a>  COleInsertDialog::COleInsertDialog

Эта функция создает только `COleInsertDialog` объекта.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Создание флаг, который содержит любое количество следующих значений, чтобы объединить с помощью битового оператора или:

- IOF_SHOWHELP указывает, что при вызове диалоговом окне будет отображаться кнопку "Справка".

- IOF_SELECTCREATENEW указывает, что будет создать новый переключатель выбран при вызове диалоговое окно. Это значение по умолчанию и не может использоваться с IOF_SELECTCREATEFROMFILE.

- IOF_SELECTCREATEFROMFILE указывает, что переключатель Создать из файла будет выбран при вызове диалоговое окно. Не может использоваться с IOF_SELECTCREATENEW.

- IOF_CHECKLINK указывает, что флажок связь будет проверен изначально из при вызове диалоговое окно.

- При вызове диалоговом окне будут отключены IOF_DISABLELINK указывает, что ее флажок.

- IOF_CHECKDISPLAYASICON указывает, что флажок виде значка будет проверяться изначально, текущий значок будет отображаться и изменить значок кнопки будет включена, когда вызывается диалоговое окно.

- IOF_VERIFYSERVERSEXIST указывает, что в диалоговом окне следует проверять классы, которые он добавляет поле со списком, гарантируя, что серверы, указанные в базе данных регистрации существовать до откроется диалоговое окно. Этот параметр может существенно снизить общую производительность.

*pParentWnd*<br/>
Указывает на объект окна родительский объект или владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если это значение NULL, родительское окно объекта диалогового окна будет присвоено главного окна приложения.

### <a name="remarks"></a>Примечания

Чтобы отобразить диалоговое окно, вызовите [DoModal](#domodal) функции.

##  <a name="createitem"></a>  COleInsertDialog::CreateItem

Вызывайте эту функцию для создания объекта типа [COleClientItem](../../mfc/reference/coleclientitem-class.md) только если [DoModal](#domodal) возвращает IDOK.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указывает элемент должен быть создан.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент был создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Необходимо выделить `COleClientItem` объект перед вызовом этой функции.

##  <a name="domodal"></a>  COleInsertDialog::DoModal

Вызывайте эту функцию, чтобы отобразить диалоговое окно вставки объекта OLE.

```
virtual INT_PTR
    DoModal();


INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Одно из следующих значений:

`COleInsertDialog::DocObjectsOnly` вставляет только DocObjects.

`COleInsertDialog::ControlsOnly` Вставляет элементы управления ActiveX.

Ноль вставляет DocObject ни элемент управления ActiveX. Это значение результаты в той же реализации, как первый прототип перечисленных выше.

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если было успешно отображено диалоговое окно.

- IDCANCEL, если пользователь отменил диалоговое окно.

- IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функция-член для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок, см. в разделе [OleUIInsertObject](/windows/desktop/api/oledlg/nf-oledlg-oleuiinsertobjecta) функции в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различных диалоговых путем определения участников [m_io](#m_io) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.

Если `DoModal` возвращает IDOK, можно вызвать другой член функции, чтобы получить параметры или данные, введенные в диалоговом окне пользователь.

##  <a name="getclassid"></a>  COleInsertDialog::GetClassID

Вызывайте эту функцию, чтобы получить идентификатор CLSID, связанный с выбранного элемента, только если [DoModal](#domodal) возвращает IDOK и тип выбора `COleInsertDialog::createNewItem`.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает идентификатор CLSID, связанный с выбранным элементом.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [раздел CLSID](/windows/desktop/com/clsid-key-hklm) в пакете Windows SDK.

##  <a name="getdrawaspect"></a>  COleInsertDialog::GetDrawAspect

Вызывайте эту функцию, чтобы определить, если пользователь решает отображения выбранного элемента в виде значка.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод, необходимых для отображения объекта.

- DVASPECT_CONTENT возвращается, если не был установлен флажок виде значка.

- DVASPECT_ICON возвращается, если был установлен флажок виде значка.

### <a name="remarks"></a>Примечания

Вызовите этот, только если функция [DoModal](#domodal) возвращает IDOK.

Дополнительные сведения о рисовании аспект, см. в разделе [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуры данных в пакете Windows SDK.

##  <a name="geticonicmetafile"></a>  COleInsertDialog::GetIconicMetafile

Вызывайте эту функцию для получения дескриптора метафайл, содержащий аспект, преобразованного в значок выбранного элемента.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор метафайла, содержащий символическое аспектом выбранного элемента, в том случае, если флажок виде значка был установлен после закрытия диалогового окна, выбрав **ОК**; в противном случае — NULL.

##  <a name="getpathname"></a>  COleInsertDialog::GetPathName

Вызывайте эту функцию, чтобы получить полный путь, только если выбранный файл [DoModal](#domodal) возвращает IDOK и тип выбора не `COleInsertDialog::createNewItem`.

```
CString GetPathName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный путь к файлу, выбранному в диалоговом окне. Если тип выбора `createNewItem`, эта функция возвращает смысла `CString` в режиме выпуска или вызывает проверочное утверждение в режиме отладки.

##  <a name="getselectiontype"></a>  COleInsertDialog::GetSelectionType

Вызовите эту функцию для получения выбранного, когда в диалоговом окне Вставка объекта было отклонено, выбрав выбора типа **ОК**.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип выбора, сделанного.

### <a name="remarks"></a>Примечания

Тип возвращаемого значения задаются `Selection` тип перечисления, объявленный в `COleInsertDialog` класса.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

Выполните краткое описание каждого из этих значений.

- `COleInsertDialog::createNewItem` Создать новый переключатель выбран.

- `COleInsertDialog::insertFromFile` Был выбран переключатель Создать из файла и не был установлен флажок ссылку.

- `COleInsertDialog::linkToFile` Был выбран переключатель Создать из файла и был установлен флажок «ссылку».

##  <a name="m_io"></a>  COleInsertDialog::m_io

Структура типа OLEUIINSERTOBJECT используется для управления поведением в диалоговом окне Вставка объекта.

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>Примечания

Члены этой структуры можно изменить напрямую или с помощью функций-членов.

Дополнительные сведения см. в разделе [OLEUIINSERTOBJECT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta) структуры в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Пример MFC OCLIENT](../../visual-cpp-samples.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
