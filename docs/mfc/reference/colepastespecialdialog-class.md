---
title: Класс COlePasteSpecialDialog | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aad3a019b3c81b4edc890daafdff232a522ed4e2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074349"
---
# <a name="colepastespecialdialog-class"></a>Класс COlePasteSpecialDialog

Используется для диалогового окна OLE "Вставить специальный объект".

## <a name="syntax"></a>Синтаксис

```
class COlePasteSpecialDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Создает объект `COlePasteSpecialDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COlePasteSpecialDialog::AddFormat](#addformat)|Добавляет в список форматов, которые можно вставить в приложение пользовательские форматы.|
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Добавляет новую запись в список поддерживаемых форматов буфера обмена.|
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|Добавляет CF_METAFILEPICT CF_BITMAP CF_DIB, и при необходимости CF_LINKSOURCE в список форматов приложения можно вставить.|
|[COlePasteSpecialDialog::CreateItem](#createitem)|Создает элемент в документе-контейнере, используя указанный формат.|
|[COlePasteSpecialDialog::DoModal](#domodal)|Отображает диалоговое окно OLE Специальная вставка.|
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Сообщает ли нарисовать элемент как значок или нет.|
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Получает дескриптор метафайла, связанных с формой, преобразованного в значок этого элемента.|
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Возвращает индекс параметры доступных вставки, которая была выбрана пользователем.|
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Получает тип выделения выбранного.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COlePasteSpecialDialog::m_ps](#m_ps)|Структура типа OLEUIPASTESPECIAL, который управляет функция диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект класса `COlePasteSpecialDialog` при необходимости вызвать это диалоговое окно. После `COlePasteSpecialDialog` объект был создан, можно использовать [AddFormat](#addformat) и [AddStandardFormats](#addstandardformats) функции-члены для добавления форматы буфера обмена в диалоговое окно. Можно также использовать [m_ps](#m_ps) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_ps` Структуры имеет тип OLEUIPASTESPECIAL.

Дополнительные сведения см. в разделе [OLEUIPASTESPECIAL](/windows/desktop/api/oledlg/ns-oledlg-tagoleuipastespeciala) структуры в пакете Windows SDK.

Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePasteSpecialDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

##  <a name="addformat"></a>  COlePasteSpecialDialog::AddFormat

Вызывайте эту функцию, чтобы добавить новые форматы список форматов, которые приложение может поддерживать в Специальная вставка операции.

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
Ссылка на тип данных для добавления.

*lpszFormat*<br/>
Строка, описывающая формат для пользователя.

*lpszResult*<br/>
Строка, описывающая результат, если выбран этот формат, в диалоговом окне.

*flags*<br/>
Различные связь и внедрение параметры, доступные для данного формата. Этот флаг представляет собой битовую комбинацию одного или нескольких разных значений в OLEUIPASTEFLAG перечисляемый тип.

*CF*<br/>
Формат буфера обмена для добавления.

*Тип*<br/>
Типы мультимедиа, доступные в этом формате. Это представляет собой битовую комбинацию одного или нескольких значений в TYMED перечисляемый тип.

*nFormatID*<br/>
Идентификатор строки, который определяет этот формат. Эта строка имеет две отдельных строки, разделенные символом «\n». Первая строка имеет те же данные, будут передаваться в *lpstrFormat* параметра, а второе — совпадает со значением *lpstrResult* параметра.

*bEnableIcon*<br/>
Флаг, который определяет, включен ли флажок виде значка, когда этот формат выбирается в поле со списком.

*включения индикатора*<br/>
Флаг, который определяет, включен ли переключатель связать, когда этот формат выбирается в поле со списком.

### <a name="remarks"></a>Примечания

Эта функция может вызываться для добавления стандартных форматах, например CF_TEXT или CF_TIFF либо пользовательских форматов, зарегистрированных в системе приложения. Дополнительные сведения о вставке данных объектов в приложении см. в статье [объекты и источники данных: манипуляции](../../mfc/data-objects-and-data-sources-manipulation.md).

Дополнительные сведения см. в разделе [TYMED](/windows/desktop/api/objidl/ne-objidl-tagtymed) тип перечисления и [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуры в пакете Windows SDK.

Дополнительные сведения см. в разделе [OLEUIPASTEFLAG](/windows/desktop/api/oledlg/ne-oledlg-tagoleuipasteflag) перечислимый тип в пакете Windows SDK.

##  <a name="addlinkentry"></a>  COlePasteSpecialDialog::AddLinkEntry

Добавляет новую запись в список поддерживаемых форматов буфера обмена.

```
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Формат буфера обмена для добавления.

### <a name="return-value"></a>Возвращаемое значение

[OLEUIPASTEFLAG](/windows/desktop/api/oledlg/ne-oledlg-tagoleuipasteflag) структуру, содержащую сведения для новой записи связи.

##  <a name="addstandardformats"></a>  COlePasteSpecialDialog::AddStandardFormats

Вызывайте эту функцию, чтобы добавить следующие форматы буфера обмена в список форматов, которые приложение может поддерживать в Специальная вставка операции:

```
void AddStandardFormats(BOOL bEnableLink = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnableLink*<br/>
Флаг, определяющий, следует ли добавить в список форматов CF_LINKSOURCE приложения можно вставить.

### <a name="remarks"></a>Примечания

- CF_BITMAP

- CF_DIB

- CF_METAFILEPICT

- **«Внедренный объект»**

- (необязательно) **«Связать источник»**

Эти форматы используются для поддержки внедрения и связывания.

##  <a name="colepastespecialdialog"></a>  COlePasteSpecialDialog::COlePasteSpecialDialog

Создает объект `COlePasteSpecialDialog`.

```
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,
    COleDataObject* pDataObject = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаг создания содержит любое количество следующих флагов, объединенные с помощью битового оператора или:

- PSF_SELECTPASTE указывает, что переключатель «вставить» будет проверен изначально из при вызове диалоговое окно. Не может использоваться в сочетании с PSF_SELECTPASTELINK. Это значение по умолчанию.

- PSF_SELECTPASTELINK указывает, что будет связать переключатель флажок установлен изначально при вызове диалоговое окно. Не может использоваться в сочетании с PSF_SELECTPASTE.

- PSF_CHECKDISPLAYASICON указывает, что флажок виде значка будет проверен изначально из при вызове диалоговое окно.

- PSF_SHOWHELP указывает, что при вызове диалоговом окне будет отображаться кнопку "Справка".

*pDataObject*<br/>
Указывает на [COleDataObject](../../mfc/reference/coledataobject-class.md) для вставки. Если это значение равно NULL, он получает `COleDataObject` из буфера обмена.

*pParentWnd*<br/>
Указывает на объект окна родительский объект или владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если он имеет значение NULL, родительского окна окно присваивается главного окна приложения.

### <a name="remarks"></a>Примечания

Эта функция только создает `COlePasteSpecialDialog` объекта. Чтобы отобразить диалоговое окно, вызовите [DoModal](#domodal) функции.

Дополнительные сведения см. в разделе [OLEUIPASTEFLAG](/windows/desktop/api/oledlg/ne-oledlg-tagoleuipasteflag) перечислимый тип в пакете Windows SDK.

##  <a name="createitem"></a>  COlePasteSpecialDialog::CreateItem

Создает новый элемент, которая была выбрана в диалоговом окне Специальная вставка.

```
BOOL CreateItem(COleClientItem* pNewItem);
```

### <a name="parameters"></a>Параметры

*pNewItem*<br/>
Указывает на `COleClientItem` экземпляра. Не может принимать значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент был создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Эту функцию следует вызывать только после [DoModal](#domodal) возвращает IDOK.

##  <a name="domodal"></a>  COlePasteSpecialDialog::DoModal

Отображает диалоговое окно OLE Специальная вставка.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если было успешно отображено диалоговое окно.

- IDCANCEL, если пользователь отменил диалоговое окно.

- IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите `COleDialog::GetLastError` функция-член для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок, см. в разделе [OleUIPasteSpecial](/windows/desktop/api/oledlg/nf-oledlg-oleuipastespeciala) функции в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различных диалоговых путем определения участников [m_ps](#m_ps) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.

Если `DoModal` возвращает IDOK, можно вызвать другой член функции, чтобы получить параметры или данные, введенные пользователем в диалоговом окне.

##  <a name="getdrawaspect"></a>  COlePasteSpecialDialog::GetDrawAspect

Определяет, если пользователь решает отображения выбранного элемента в виде значка.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод, необходимых для отображения объекта.

- DVASPECT_CONTENT возвращается, если флажок виде значка не проверяются, когда диалоговое окно было закрыть.

- DVASPECT_ICON возвращается, если был установлен флажок виде значка, когда диалоговое окно было отклонено.

### <a name="remarks"></a>Примечания

Только вызывайте эту функцию после [DoModal](#domodal) возвращает IDOK.

Дополнительные сведения о рисовании аспект, см. в разделе [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуры в пакете Windows SDK.

##  <a name="geticonicmetafile"></a>  COlePasteSpecialDialog::GetIconicMetafile

Получает метафайл, связанный с элементом, выбранного пользователем.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор метафайла, содержащий аспект, преобразованного в значок выбранного элемента, в том случае, если был установлен флажок виде значка, когда диалоговое окно было отклонено, выбрав **ОК**; в противном случае — NULL.

##  <a name="getpasteindex"></a>  COlePasteSpecialDialog::GetPasteIndex

Получает индекс значение, связанное с записью выбрал пользователь.

```
int GetPasteIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс в массиве `OLEUIPASTEENTRY` структур, выбранные пользователем. Формат, который соответствует выбранного индекса следует использовать при выполнении операции вставки.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [OLEUIPASTEENTRY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuipasteentrya) структуры в пакете Windows SDK.

##  <a name="getselectiontype"></a>  COlePasteSpecialDialog::GetSelectionType

Определяет тип выбора, сделанного пользователем.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает тип Выбор, сделанный.

### <a name="remarks"></a>Примечания

Тип возвращаемого значения задаются `Selection` тип перечисления, объявленный в `COlePasteSpecialDialog` класса.

```
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };
```

Выполните краткие desccriptions из следующих значений.

- `COlePasteSpecialDialog::pasteLink` Установлен переключатель, связать и выбранного формата был стандартный формат OLE.

- `COlePasteSpecialDialog::pasteNormal` Переключатель «вставить» был извлечен и выбранного формата был стандартный формат OLE.

- `COlePasteSpecialDialog::pasteOther` Выбранный формат не стандартный формат OLE.

- `COlePasteSpecialDialog::pasteStatic` Выбранный формат был метафайл.

##  <a name="m_ps"></a>  COlePasteSpecialDialog::m_ps

Структура типа OLEUIPASTESPECIAL используется для управления поведением диалогового окна "Специальная вставка".

```
OLEUIPASTESPECIAL m_ps;
```

### <a name="remarks"></a>Примечания

Члены этой структуры можно изменить непосредственно или с помощью функций-членов.

Дополнительные сведения см. в разделе [OLEUIPASTESPECIAL](/windows/desktop/api/oledlg/ns-oledlg-tagoleuipastespeciala) структуры в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Пример MFC OCLIENT](../../visual-cpp-samples.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
