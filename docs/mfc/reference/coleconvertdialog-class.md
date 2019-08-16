---
title: Класс Колеконвертдиалог
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
ms.openlocfilehash: ba57e756457fcffca806eeba7454ddf7bcf99d34
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504298"
---
# <a name="coleconvertdialog-class"></a>Класс Колеконвертдиалог

Дополнительные сведения см. в описании структуры [олеуиконверт](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) в Windows SDK.

## <a name="syntax"></a>Синтаксис

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Колеконвертдиалог:: Колеконвертдиалог](#coleconvertdialog)|Создает объект `COleConvertDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Колеконвертдиалог::D Оконверт](#doconvert)|Выполняет преобразование, указанное в диалоговом окне.|
|[Колеконвертдиалог::D Омодал](#domodal)|Отображает диалоговое окно «изменение элемента OLE».|
|[Колеконвертдиалог::, ClassID](#getclassid)|Возвращает CLSID, связанный с выбранным элементом.|
|[Колеконвертдиалог:: Жетдраваспект](#getdrawaspect)|Указывает, следует ли рисовать элемент как значок.|
|[Колеконвертдиалог:: Жетиконикметафиле](#geticonicmetafile)|Возвращает маркер для метафайла, связанного со значком этого элемента.|
|[Колеконвертдиалог:: Жетселектионтипе](#getselectiontype)|Возвращает выбранный тип выбора.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Колеконвертдиалог:: m_cv](#m_cv)|Структура, которая управляет поведением диалогового окна.|

## <a name="remarks"></a>Примечания

> [!NOTE]
>  Созданный мастером приложений код контейнера использует этот класс.

Дополнительные сведения о диалоговых окнах, связанных с OLE, см. в разделе [диалоговые окна статьи в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

[коледиалог](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксодлгс. h

##  <a name="coleconvertdialog"></a>Колеконвертдиалог:: Колеконвертдиалог

Конструирует только `COleConvertDialog` объект.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*питем*<br/>
Указывает на элемент, который необходимо преобразовать или активировать.

*dwFlags*<br/>
Флаг создания, который содержит любое число следующих значений, Объединенных с помощью оператора побитового или:

- CF_SELECTCONVERTTO указывает, что при вызове диалогового окна сначала будет выбран переключатель преобразовать в. Это значение по умолчанию.

- CF_SELECTACTIVATEAS Указывает, что при вызове диалогового окна изначально будет выбран переключатель активировать как.

- CF_SETCONVERTDEFAULT указывает, что класс, CLSID которого задан `clsidConvertDefault` членом `m_cv` структуры, будет использоваться в качестве выбора по умолчанию в списке классов при выборе переключателя преобразовать в переключатель.

- CF_SETACTIVATEDEFAULT указывает, что класс с идентификатором CLSID, заданный `clsidActivateDefault` членом `m_cv` структуры, будет использоваться в качестве выбора по умолчанию в списке классов при выборе переключателя «активировать как».

- CF_SHOWHELPBUTTON указывает, что при вызове диалогового окна появится кнопка Справка.

*pClassId равен*<br/>
Указывает на идентификатор CLSID элемента, который необходимо преобразовать или активировать. Если значение равно NULL, будет использоваться CLSID, связанный с *питем* .

*ппарентвнд*<br/>
Указывает на родительский элемент или объект окна-владельца ( `CWnd`типа), которому принадлежит объект диалогового окна. Если это значение равно NULL, родительскому окну диалогового окна присваивается основное окно приложения.

### <a name="remarks"></a>Примечания

Чтобы открыть диалоговое окно, вызовите функцию [DoModal](#domodal) .

Дополнительные сведения см. в разделе [ключ CLSID](/windows/win32/com/clsid-key-hklm) и структура [олеуиконверт](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) .

##  <a name="doconvert"></a>Колеконвертдиалог::D Оконверт

Вызовите эту функцию после успешного возврата из [DoModal](#domodal)для преобразования или для активации объекта типа [COleClientItem](../../mfc/reference/coleclientitem-class.md).

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>Параметры

*питем*<br/>
Указывает на элемент, который необходимо преобразовать или активировать. Не может принимать значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Элемент преобразуется или активируется в соответствии со сведениями, выбранными пользователем в диалоговом окне Преобразование.

##  <a name="domodal"></a>Колеконвертдиалог::D Омодал

Эта функция вызывается для вывода диалогового окна OLE Convert.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- ИДОК, если диалоговое окно было успешно отображено.

- ИДКАНЦЕЛ, если пользователь отменил диалоговое окно.

- ИДАБОРТ, если произошла ошибка. Если возвращается ИДАБОРТ, вызовите функцию-член [коледиалог:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) , чтобы получить дополнительные сведения о типе произошедшей ошибки. Список возможных ошибок см. в описании функции [олеуиконверт](/windows/win32/api/oledlg/nf-oledlg-oleuiconvertw) в Windows SDK.

### <a name="remarks"></a>Примечания

Если требуется инициализировать различные элементы управления диалогового окна путем установки элементов структуры [m_cv](#m_cv) , следует выполнить это действие перед вызовом метода `DoModal`, но после создания объекта диалогового окна.

Если `DoModal` возвращает идок, можно вызвать другие функции, чтобы получить параметры или сведения, введенные пользователем в диалоговое окно.

##  <a name="getclassid"></a>Колеконвертдиалог::, ClassID

Вызовите эту функцию, чтобы получить идентификатор CLSID, связанный с элементом, выбранным пользователем в диалоговом окне Преобразование.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор CLSID, связанный с элементом, выбранным в диалоговом окне Преобразование.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию только после того, как [DoModal](#domodal) возвращает идок.

Дополнительные сведения см. в разделе [ключ CLSID](/windows/win32/com/clsid-key-hklm) в Windows SDK.

##  <a name="getdrawaspect"></a>Колеконвертдиалог:: Жетдраваспект

Вызовите эту функцию, чтобы определить, выбрал ли пользователь Отображение выбранного элемента в виде значка.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод, необходимый для отрисовки объекта.

- DVASPECT_CONTENT возвращается, если флажок "отображать как значок" не установлен.

- DVASPECT_ICON возвращается, если установлен флажок "отображать как значок".

### <a name="remarks"></a>Примечания

Вызывайте эту функцию только после того, как [DoModal](#domodal) возвращает идок.

Дополнительные сведения о аспекте рисования см. в разделе Структура данных [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

##  <a name="geticonicmetafile"></a>Колеконвертдиалог:: Жетиконикметафиле

Вызовите эту функцию, чтобы получить маркер для метафайла, содержащего значок выбранного элемента.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маркер для метафайла, содержащего значок выбранного элемента, если флажок Отображать как значок был установлен при отклонении диалогового окна нажатием кнопки ОК. в противном случае — NULL.

##  <a name="getselectiontype"></a>Колеконвертдиалог:: Жетселектионтипе

Вызовите эту функцию, чтобы определить тип преобразования, выбранного в диалоговом окне Преобразование.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип сделанного выбора.

### <a name="remarks"></a>Примечания

Значения возвращаемого типа задаются `Selection` типом перечисления, объявленным `COleConvertDialog` в классе.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

Ниже приведены краткие описания этих значений.

- `COleConvertDialog::noConversion`Возвращается, если диалоговое окно было отменено или пользователь не выбрал преобразование. Если `COleConvertDialog::DoModal` возвращено значение идок, пользователь может выбрать другой значок, отличный от того, который был выбран ранее.

- `COleConvertDialog::convertItem`Возвращается, если был установлен переключатель преобразовать в переключатель, пользователь выбрал другой элемент для преобразования в и `DoModal` вернул идок.

- `COleConvertDialog::activateAs`Возвращается, если был установлен переключатель "активировать как", пользователь выбрал другой элемент для активации и `DoModal` вернул идок.

##  <a name="m_cv"></a>Колеконвертдиалог:: m_cv

Структура типа ОЛЕУИКОНВЕРТ, используемая для управления поведением диалогового окна «Преобразование».

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>Примечания

Члены этой структуры можно изменять напрямую или с помощью функций-членов.

Дополнительные сведения см. в описании структуры [олеуиконверт](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
