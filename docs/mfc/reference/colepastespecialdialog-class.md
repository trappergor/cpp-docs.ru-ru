---
title: Класс КолепастеспеЦиалдиалог
ms.date: 11/04/2016
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
ms.openlocfilehash: f4174369620f14f2d1ac410aa5d756c75097ad0f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426621"
---
# <a name="colepastespecialdialog-class"></a>Класс КолепастеспеЦиалдиалог

Используется для диалогового окна OLE "Вставить специальный объект".

## <a name="syntax"></a>Синтаксис

```
class COlePasteSpecialDialog : public COleDialog
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[КолепастеспеЦиалдиалог:: КолепастеспеЦиалдиалог](#colepastespecialdialog)|Формирует объект `COlePasteSpecialDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[КолепастеспеЦиалдиалог:: Аддформат](#addformat)|Добавляет пользовательские форматы в список форматов, которые может вставлять приложение.|
|[КолепастеспеЦиалдиалог:: Аддлинкентри](#addlinkentry)|Добавляет новую запись в список поддерживаемых форматов буфера обмена.|
|[КолепастеспеЦиалдиалог:: Аддстандардформатс](#addstandardformats)|Добавляет CF_BITMAP, CF_DIB, CF_METAFILEPICT и при необходимости CF_LINKSOURCE в список форматов, которые приложение может вставить.|
|[КолепастеспеЦиалдиалог:: CreateItem](#createitem)|Создает элемент в документе контейнера, используя указанный формат.|
|[КолепастеспеЦиалдиалог::D Омодал](#domodal)|Отображает диалоговое окно «Специальная вставка» OLE.|
|[КолепастеспеЦиалдиалог:: Жетдраваспект](#getdrawaspect)|Указывает, следует ли рисовать элемент как значок.|
|[КолепастеспеЦиалдиалог:: Жетиконикметафиле](#geticonicmetafile)|Возвращает маркер для метафайла, связанного со значком этого элемента.|
|[КолепастеспеЦиалдиалог:: Жетпастеиндекс](#getpasteindex)|Возвращает индекс доступных параметров вставки, выбранных пользователем.|
|[КолепастеспеЦиалдиалог:: Жетселектионтипе](#getselectiontype)|Возвращает выбранный тип выбора.|

### <a name="public-data-members"></a>Открытые элементы данных

|Имя|Description|
|----------|-----------------|
|[КолепастеспеЦиалдиалог:: m_ps](#m_ps)|Структура типа ОЛЕУИПАСТЕСПЕЦИАЛ, которая управляет функцией диалогового окна.|

## <a name="remarks"></a>Remarks

Создайте объект класса `COlePasteSpecialDialog`, если требуется вызвать это диалоговое окно. После создания объекта `COlePasteSpecialDialog` можно использовать функции-члены [аддформат](#addformat) и [аддстандардформатс](#addstandardformats) для добавления форматов буфера обмена в диалоговое окно. Можно также использовать структуру [m_ps](#m_ps) для инициализации значений или состояний элементов управления в диалоговом окне. Структура `m_ps` имеет тип ОЛЕУИПАСТЕСПЕЦИАЛ.

Дополнительные сведения см. в описании структуры [олеуипастеспеЦиал](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) в Windows SDK.

Дополнительные сведения о диалоговых окнах, связанных с OLE, см. в разделе [диалоговые окна статьи в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

[коледиалог](../../mfc/reference/coledialog-class.md)

`COlePasteSpecialDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксодлгс. h

##  <a name="addformat"></a>КолепастеспеЦиалдиалог:: Аддформат

Вызовите эту функцию, чтобы добавить новые форматы в список форматов, которые приложение может поддерживать в специальной операции вставки.

```
void AddFormat(
    const FORMATETC& formatEtc,
    LPTSTR lpszFormat,
    LPTSTR lpszResult,
    DWORD flags);

void AddFormat(
    UINT cf,
    DWORD tymed,
    UINT nFormatID,
    BOOL bEnableIcon,
    BOOL bLink);
```

### <a name="parameters"></a>Параметры

*FMT*<br/>
Ссылка на добавляемый тип данных.

*лпсзформат*<br/>
Строка, описывающая формат для пользователя.

*лпсзресулт*<br/>
Строка, описывающая результат, если этот формат выбран в диалоговом окне.

*flags*<br/>
Различные параметры связывания и встраивания, доступные для этого формата. Этот флаг является побитовым сочетанием одного или нескольких различных значений в перечислимом типе ОЛЕУИПАСТЕФЛАГ.

*CF*<br/>
Добавляемый формат буфера обмена.

*тимед*<br/>
Типы носителей, доступные в этом формате. Это побитовое сочетание одного или нескольких значений в перечислимом типе ТИМЕД.

*нформатид*<br/>
Идентификатор строки, определяющей этот формат. Формат этой строки состоит из двух отдельных строк, разделенных символом "\n". Первая строка совпадает с передачей в параметр *лпстрформат* , а вторая — с параметром *лпстрресулт* .

*бенаблеикон*<br/>
Флаг, определяющий, включен ли флажок "отображать как значок", если этот формат выбран в списке.

*Частоты*<br/>
Флаг, определяющий, включен ли переключатель «Вставить ссылку», если этот формат выбран в списке.

### <a name="remarks"></a>Remarks

Эта функция может быть вызвана для добавления стандартных форматов, таких как CF_TEXT или CF_TIFF или пользовательских форматов, зарегистрированных приложением в системе. Дополнительные сведения о вставлении объектов данных в приложение см. в статье [объекты данных и источники данных: Управление](../../mfc/data-objects-and-data-sources-manipulation.md).

Дополнительные сведения см. в описании типа перечисления [тимед](/windows/win32/api/objidl/ne-objidl-tymed) и структуры [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в описании типа перечисления [олеуипастефлаг](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) в Windows SDK.

##  <a name="addlinkentry"></a>КолепастеспеЦиалдиалог:: Аддлинкентри

Добавляет новую запись в список поддерживаемых форматов буфера обмена.

```
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Добавляемый формат буфера обмена.

### <a name="return-value"></a>Возвращаемое значение

Структура [олеуипастефлаг](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) , содержащая сведения о новой записи ссылки.

##  <a name="addstandardformats"></a>КолепастеспеЦиалдиалог:: Аддстандардформатс

Вызовите эту функцию, чтобы добавить следующие форматы буфера обмена в список форматов, которые приложение может поддерживать в специальной операции вставки:

```
void AddStandardFormats(BOOL bEnableLink = TRUE);
```

### <a name="parameters"></a>Параметры

*бенаблелинк*<br/>
Флаг, определяющий, следует ли добавлять CF_LINKSOURCE в список форматов, которые приложение может вставить.

### <a name="remarks"></a>Remarks

- CF_BITMAP

- CF_DIB

- CF_METAFILEPICT

- **"Внедренный объект"**

- При необходимости **"Источник связи"**

Эти форматы используются для поддержки внедрения и компоновки.

##  <a name="colepastespecialdialog"></a>КолепастеспеЦиалдиалог:: КолепастеспеЦиалдиалог

Формирует объект `COlePasteSpecialDialog`.

```
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,
    COleDataObject* pDataObject = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаг создания содержит любое число следующих флагов, Объединенных с помощью оператора побитового или:

- PSF_SELECTPASTE указывает, что переключатель Вставить будет проверяться изначально при вызове этого диалогового окна. Нельзя использовать в сочетании с PSF_SELECTPASTELINK. Это значение по умолчанию.

- PSF_SELECTPASTELINK указывает, что переключатель Вставить ссылку будет проверяться изначально при вызове этого диалогового окна. Нельзя использовать в сочетании с PSF_SELECTPASTE.

- PSF_CHECKDISPLAYASICON указывает, что флажок Отображать как значок будет проверяться изначально при вызове этого диалогового окна.

- PSF_SHOWHELP указывает, что при вызове диалогового окна появится кнопка Справка.

*pDataObject*<br/>
Указывает на [коледатаобжект](../../mfc/reference/coledataobject-class.md) для вставления. Если это значение равно NULL, оно получает `COleDataObject` из буфера обмена.

*ппарентвнд*<br/>
Указывает на родительский элемент или объект окна-владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если это значение равно NULL, родительскому окну диалогового окна присваивается основное окно приложения.

### <a name="remarks"></a>Remarks

Эта функция конструирует только объект `COlePasteSpecialDialog`. Чтобы открыть диалоговое окно, вызовите функцию [DoModal](#domodal) .

Дополнительные сведения см. в описании типа перечисления [олеуипастефлаг](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) в Windows SDK.

##  <a name="createitem"></a>КолепастеспеЦиалдиалог:: CreateItem

Создает новый элемент, который был выбран в диалоговом окне Специальная вставка.

```
BOOL CreateItem(COleClientItem* pNewItem);
```

### <a name="parameters"></a>Параметры

*пневитем*<br/>
Указывает на экземпляр `COleClientItem`. Не может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент был успешно создан; в противном случае — 0.

### <a name="remarks"></a>Remarks

Эту функцию следует вызывать только после того, как [DoModal](#domodal) возвращает идок.

##  <a name="domodal"></a>КолепастеспеЦиалдиалог::D Омодал

Отображает диалоговое окно «Специальная вставка» OLE.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- ИДОК, если диалоговое окно было успешно отображено.

- ИДКАНЦЕЛ, если пользователь отменил диалоговое окно.

- ИДАБОРТ, если произошла ошибка. Если возвращается ИДАБОРТ, вызовите функцию-член `COleDialog::GetLastError`, чтобы получить дополнительные сведения о типе произошедшей ошибки. Список возможных ошибок см. в описании функции [олеуипастеспеЦиал](/windows/win32/api/oledlg/nf-oledlg-oleuipastespecialw) в Windows SDK.

### <a name="remarks"></a>Remarks

Если требуется инициализировать различные элементы управления диалогового окна путем установки элементов структуры [m_ps](#m_ps) , следует сделать это перед вызовом `DoModal`, но после создания объекта диалогового окна.

Если `DoModal` возвращает ИДОК, можно вызвать другие функции члена для получения параметров или данных, вводимых пользователем, в диалоговое окно.

##  <a name="getdrawaspect"></a>КолепастеспеЦиалдиалог:: Жетдраваспект

Определяет, выбран ли пользователь для показа выбранного элемента в виде значка.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод, необходимый для отрисовки объекта.

- DVASPECT_CONTENT возвращается, если флажок Отображать как значок не был установлен при отклонении этого диалогового окна.

- DVASPECT_ICON возвращается, если флажок Отображать как значок был установлен при отклонении этого диалогового окна.

### <a name="remarks"></a>Remarks

Вызывайте эту функцию только после того, как [DoModal](#domodal) возвращает идок.

Дополнительные сведения о аспекте рисования см. в описании структуры [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

##  <a name="geticonicmetafile"></a>КолепастеспеЦиалдиалог:: Жетиконикметафиле

Возвращает метафайл, связанный с элементом, выбранным пользователем.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маркер для метафайла, содержащего значок выбранного элемента, если флажок Отображать как значок был установлен при отклонении диалогового окна нажатием кнопки **ОК**. в противном случае — NULL.

##  <a name="getpasteindex"></a>КолепастеспеЦиалдиалог:: Жетпастеиндекс

Возвращает значение индекса, связанное с записью, выбранной пользователем.

```
int GetPasteIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс в массиве `OLEUIPASTEENTRY` структур, выбранных пользователем. При выполнении операции вставки следует использовать формат, соответствующий выбранному индексу.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в описании структуры [олеуипастинтри](/windows/win32/api/oledlg/ns-oledlg-oleuipasteentryw) в Windows SDK.

##  <a name="getselectiontype"></a>КолепастеспеЦиалдиалог:: Жетселектионтипе

Определяет тип выбора, сделанный пользователем.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает тип сделанного выбора.

### <a name="remarks"></a>Remarks

Значения возвращаемого типа задаются типом перечисления `Selection`, объявленным в классе `COlePasteSpecialDialog`.

```
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };
```

Ниже приведен краткий десккриптионс этих значений.

- `COlePasteSpecialDialog::pasteLink` был установлен переключатель Вставить ссылку, и выбранный формат был стандартным форматом OLE.

- `COlePasteSpecialDialog::pasteNormal` был установлен переключатель Вставить, а выбранный формат был стандартным форматом OLE.

- `COlePasteSpecialDialog::pasteOther` выбранный формат не является стандартным форматом OLE.

- `COlePasteSpecialDialog::pasteStatic` выбранный формат был метафайлом.

##  <a name="m_ps"></a>КолепастеспеЦиалдиалог:: m_ps

Структура типа ОЛЕУИПАСТЕСПЕЦИАЛ, используемая для управления поведением диалогового окна «Специальная вставка».

```
OLEUIPASTESPECIAL m_ps;
```

### <a name="remarks"></a>Remarks

Члены этой структуры могут быть изменены напрямую или через функции-члены.

Дополнительные сведения см. в описании структуры [олеуипастеспеЦиал](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Пример OCLIENT MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
