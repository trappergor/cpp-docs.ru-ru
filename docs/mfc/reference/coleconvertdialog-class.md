---
title: Класс COleConvertDialog
ms.date: 11/04/2016
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
ms.openlocfilehash: d0d2f83a6340224cf0fd6318e470fcfae103d72b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267736"
---
# <a name="coleconvertdialog-class"></a>Класс COleConvertDialog

Дополнительные сведения см. в разделе [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) структуры в пакете Windows SDK.

## <a name="syntax"></a>Синтаксис

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Создает объект `COleConvertDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[COleConvertDialog::DoConvert](#doconvert)|Выполняет преобразование, указанных в диалоговом окне.|
|[COleConvertDialog::DoModal](#domodal)|Отображает диалоговое окно элементов OLE изменений.|
|[COleConvertDialog::GetClassID](#getclassid)|Возвращает идентификатор CLSID, связанный с выбранным элементом.|
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Указывает, следует ли рисовать элемент как значок.|
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Получает дескриптор метафайла, связанных с формой, преобразованного в значок этого элемента.|
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Получает тип выделения выбранного.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[COleConvertDialog::m_cv](#m_cv)|Структура, которая управляет поведением окна.|

## <a name="remarks"></a>Примечания

> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.

Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

##  <a name="coleconvertdialog"></a>  COleConvertDialog::COleConvertDialog

Создает только `COleConvertDialog` объекта.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указывает элемент, чтобы преобразовывать или активации.

*dwFlags*<br/>
Создание флаг, который содержит любое количество следующих значений в сочетании с помощью побитовой операции- или оператор:

- CF_SELECTCONVERTTO указывает, что будет преобразовать в переключатель выбран при вызове диалоговое окно. Это значение по умолчанию.

- CF_SELECTACTIVATEAS указывает, что переключатель «активировать» будет выбран при вызове диалоговое окно.

- CF_SETCONVERTDEFAULT указывает, что класс, указанный которого CLSID `clsidConvertDefault` членом `m_cv` структура будет использоваться как значение по умолчанию в поле со списком классов, при выборе переключателя преобразовать в.

- CF_SETACTIVATEDEFAULT указывает, что класс, указанный которого CLSID `clsidActivateDefault` членом `m_cv` структуры будет использоваться как значение по умолчанию в поле со списком классов, если выбран переключатель «активировать».

- CF_SHOWHELPBUTTON указывает, что при вызове диалоговом окне будет отображаться кнопку "Справка".

*pClassID*<br/>
Указывает идентификатор CLSID элемента необходимо преобразовывать или активации. Если значение равно NULL, CLSID, связанная с *pItem* будет использоваться.

*pParentWnd*<br/>
Указывает на объект окна родительский объект или владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если он имеет значение NULL, родительского окна окно присваивается главного окна приложения.

### <a name="remarks"></a>Примечания

Чтобы отобразить диалоговое окно, вызовите [DoModal](#domodal) функции.

Дополнительные сведения см. в разделе [раздел CLSID](/windows/desktop/com/clsid-key-hklm) и [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) структуры.

##  <a name="doconvert"></a>  COleConvertDialog::DoConvert

Вызывайте эту функцию после успешного возврата из [DoModal](#domodal), либо для преобразования или активировать объект типа [COleClientItem](../../mfc/reference/coleclientitem-class.md).

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указывает элемент, чтобы преобразовывать или активации. Не может принимать значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Преобразовать или активированное в соответствии с выбранные пользователем в диалоговом окне Convert сведения элемента.

##  <a name="domodal"></a>  COleConvertDialog::DoModal

Вызывайте эту функцию, чтобы отобразить диалоговое окно преобразования OLE.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если было успешно отображено диалоговое окно.

- IDCANCEL, если пользователь отменил диалоговое окно.

- IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функция-член для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок, см. в разделе [OleUIConvert](/windows/desktop/api/oledlg/nf-oledlg-oleuiconverta) функции в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различных диалоговых путем определения участников [m_cv](#m_cv) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.

Если `DoModal` возвращает IDOK, можно вызывать другой член функции для получения параметров или данных, введенных пользователем в диалоговом окне.

##  <a name="getclassid"></a>  COleConvertDialog::GetClassID

Вызовите эту функцию для получения CLSID связанный с элементом, который пользователь выбрал в диалоговом окне Convert.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор CLSID, связанный с элементом, который был выбран в диалоговом окне Convert.

### <a name="remarks"></a>Примечания

Эта функция только после вызова [DoModal](#domodal) возвращает IDOK.

Дополнительные сведения см. в разделе [раздел CLSID](/windows/desktop/com/clsid-key-hklm) в пакете Windows SDK.

##  <a name="getdrawaspect"></a>  COleConvertDialog::GetDrawAspect

Вызывайте эту функцию, чтобы определить, что выбрал пользователь для отображения выбранного элемента в виде значка.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод, необходимых для отображения объекта.

- DVASPECT_CONTENT возвращается, если не был установлен флажок виде значка.

- DVASPECT_ICON возвращается, если был установлен флажок виде значка.

### <a name="remarks"></a>Примечания

Эта функция только после вызова [DoModal](#domodal) возвращает IDOK.

Дополнительные сведения о рисовании аспект, см. в разделе [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуры данных в пакете Windows SDK.

##  <a name="geticonicmetafile"></a>  COleConvertDialog::GetIconicMetafile

Вызывайте эту функцию для получения дескриптора метафайл, содержащий аспект, преобразованного в значок выбранного элемента.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор метафайла, содержащий символическое аспектом выбранного элемента, в том случае, если флажок виде значка был установлен, при отклонении диалоговое окно, нажав кнопку OK; в противном случае имеет значение NULL.

##  <a name="getselectiontype"></a>  COleConvertDialog::GetSelectionType

Вызывайте эту функцию, чтобы определить тип выполняемого преобразования, выбранного в диалоговом окне Convert.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип выбора, сделанного.

### <a name="remarks"></a>Примечания

Тип возвращаемого значения задаются `Selection` тип перечисления, объявленный в `COleConvertDialog` класса.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

Выполните краткое описание каждого из этих значений.

- `COleConvertDialog::noConversion` Возвращается, если диалоговое окно было отменено или преобразование выбранного пользователем. Если `COleConvertDialog::DoModal` возвращено IDOK, это возможно, что пользователь выбрал отличающегося был выбран другой значок.

- `COleConvertDialog::convertItem` Возвращается, если установлен переключатель, чтобы преобразовать, пользователь выбирает другой элемент для преобразования, и `DoModal` возвращается IDOK.

- `COleConvertDialog::activateAs` Возвращается, если был установлен переключатель «активировать», пользователь выбирает другой элемент для активации, и `DoModal` возвращается IDOK.

##  <a name="m_cv"></a>  COleConvertDialog::m_cv

Структура типа OLEUICONVERT, используемый для управления поведением диалоговое окно "преобразование".

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>Примечания

Члены этой структуры можно изменить напрямую или с помощью функций-членов.

Дополнительные сведения см. в разделе [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) структуры в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
