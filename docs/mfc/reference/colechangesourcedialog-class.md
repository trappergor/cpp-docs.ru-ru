---
title: Класс Колечанжесаурцедиалог
ms.date: 11/04/2016
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
ms.openlocfilehash: 239d7eed89796f414a7665b203ca50fafec51277
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504389"
---
# <a name="colechangesourcedialog-class"></a>Класс Колечанжесаурцедиалог

Используется для диалогового окна OLE "Изменить источник".

## <a name="syntax"></a>Синтаксис

```
class COleChangeSourceDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Колечанжесаурцедиалог:: Колечанжесаурцедиалог](#colechangesourcedialog)|Создает объект `COleChangeSourceDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Колечанжесаурцедиалог::D Омодал](#domodal)|Отображает диалоговое окно «источник изменения OLE».|
|[Колечанжесаурцедиалог::/DisplayName](#getdisplayname)|Возвращает полное отображаемое имя источника.|
|[Колечанжесаурцедиалог:: имя_файла](#getfilename)|Возвращает имя файла из имени источника.|
|[Колечанжесаурцедиалог:: Жетфромпрефикс](#getfromprefix)|Возвращает префикс предыдущего источника.|
|[Колечанжесаурцедиалог:: Жетитемнаме](#getitemname)|Возвращает имя элемента из имени источника.|
|[Колечанжесаурцедиалог:: Жеттопрефикс](#gettoprefix)|Возвращает префикс нового источника|
|[Колечанжесаурцедиалог:: Исвалидсаурце](#isvalidsource)|Указывает, является ли источник допустимым.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Колечанжесаурцедиалог:: m_cs](#m_cs)|Структура, которая управляет поведением диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект класса `COleChangeSourceDialog` , если нужно вызвать это диалоговое окно. После создания объекта `COleChangeSourceDialog` можно использовать структуру [m_cs](#m_cs) для инициализации значений или состояний элементов управления в диалоговом окне. Структура `m_cs` имеет тип [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew). Дополнительные сведения об использовании этого класса диалогового окна см. в описании функции члена [DoModal](#domodal) .

Дополнительные сведения см. в описании структуры [олеуичанжесаурце](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) в Windows SDK.

Дополнительные сведения о диалоговых окнах, связанных с OLE, см. в разделе [диалоговые окна статьи в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

[коледиалог](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксодлгс. h

##  <a name="colechangesourcedialog"></a>Колечанжесаурцедиалог:: Колечанжесаурцедиалог

Эта функция конструирует `COleChangeSourceDialog` объект.

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*питем*<br/>
Указатель на связанный [COleClientItem](../../mfc/reference/coleclientitem-class.md) , источник которого должен быть обновлен.

*ппарентвнд*<br/>
Указывает на родительский элемент или объект окна-владельца ( `CWnd`типа), которому принадлежит объект диалогового окна. Если значение равно NULL, то родительское окно диалогового окна будет установлено в главное окно приложения.

### <a name="remarks"></a>Примечания

Чтобы открыть диалоговое окно, вызовите функцию [DoModal](#domodal) .

Дополнительные сведения см. в разделе Структура [олеуичанжесаурце](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) и функция [олеуичанжесаурце](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) в Windows SDK.

##  <a name="domodal"></a>Колечанжесаурцедиалог::D Омодал

Вызовите эту функцию, чтобы отобразить диалоговое окно источник изменения OLE.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- ИДОК, если диалоговое окно было успешно отображено.

- ИДКАНЦЕЛ, если пользователь отменил диалоговое окно.

- ИДАБОРТ, если произошла ошибка. Если возвращается ИДАБОРТ, вызовите функцию-член [коледиалог:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) , чтобы получить дополнительные сведения о типе произошедшей ошибки. Список возможных ошибок см. в разделе Функция [олеуичанжесаурце](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) в Windows SDK.

### <a name="remarks"></a>Примечания

Если требуется инициализировать различные элементы управления диалогового окна путем установки элементов структуры [m_cs](#m_cs) , следует выполнить это действие перед вызовом метода `DoModal`, но после создания объекта диалогового окна.

Если `DoModal` возвращает идок, можно вызывать функции-члены для получения параметров или сведений, введенных пользователем, из диалогового окна. В следующем списке перечислены типичные функции запросов:

- [GetFileName](#getfilename)

- [Переdisplayname](#getdisplayname)

- [жетитемнаме](#getitemname)

##  <a name="getdisplayname"></a>Колечанжесаурцедиалог::/DisplayName

Вызовите эту функцию, чтобы получить полное отображаемое имя для связанного элемента клиента.

```
CString GetDisplayName();
```

### <a name="return-value"></a>Возвращаемое значение

Полное отображаемое имя источника (моникер) для [COleClientItem](../../mfc/reference/coleclientitem-class.md) , указанное в конструкторе.

##  <a name="getfilename"></a>Колечанжесаурцедиалог:: имя_файла

Вызовите эту функцию, чтобы извлечь часть отображаемого имени файла для связанного клиентского элемента.

```
CString GetFileName();
```

### <a name="return-value"></a>Возвращаемое значение

Часть моникера файла отображаемого имени источника для [COleClientItem](../../mfc/reference/coleclientitem-class.md) , указанного в конструкторе.

### <a name="remarks"></a>Примечания

Моникер файла вместе с моникером элемента предоставляет полное отображаемое имя.

##  <a name="getfromprefix"></a>Колечанжесаурцедиалог:: Жетфромпрефикс

Вызовите эту функцию, чтобы получить предыдущую строку префикса для источника.

```
CString GetFromPrefix();
```

### <a name="return-value"></a>Возвращаемое значение

Предыдущая строка префикса источника.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию только после того, как [DoModal](#domodal) возвращает идок.

Это значение происходит непосредственно из `lpszFrom` элемента структуры [олеуичанжесаурце](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) .

Дополнительные сведения см. в описании структуры [олеуичанжесаурце](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) в Windows SDK.

##  <a name="getitemname"></a>Колечанжесаурцедиалог:: Жетитемнаме

Вызовите эту функцию, чтобы получить часть моникера элемента для отображаемого имени связанного элемента клиента.

```
CString GetItemName();
```

### <a name="return-value"></a>Возвращаемое значение

Часть моникера элемента в отображаемом имени источника для [COleClientItem](../../mfc/reference/coleclientitem-class.md) , указанного в конструкторе.

### <a name="remarks"></a>Примечания

Моникер файла вместе с моникером элемента предоставляет полное отображаемое имя.

##  <a name="gettoprefix"></a>Колечанжесаурцедиалог:: Жеттопрефикс

Вызовите эту функцию, чтобы получить новую строку префикса для источника.

```
CString GetToPrefix();
```

### <a name="return-value"></a>Возвращаемое значение

Новая строка префикса источника.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию только после того, как [DoModal](#domodal) возвращает идок.

Это значение происходит непосредственно из `lpszTo` элемента структуры [олеуичанжесаурце](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) .

Дополнительные сведения см. в описании структуры [олеуичанжесаурце](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) в Windows SDK.

##  <a name="m_cs"></a>Колечанжесаурцедиалог:: m_cs

Этот элемент данных является структурой типа [олеуичанжесаурце](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew).

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>Примечания

`OLEUICHANGESOURCE`используется для управления поведением диалогового окна «источник изменения OLE». Члены этой структуры можно изменять напрямую.

Дополнительные сведения см. в описании структуры [олеуичанжесаурце](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) в Windows SDK.

##  <a name="isvalidsource"></a>Колечанжесаурцедиалог:: Исвалидсаурце

Вызовите эту функцию, чтобы определить, является ли новый источник допустимым.

```
BOOL IsValidSource();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если новый источник допустим; в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию только после того, как [DoModal](#domodal) возвращает идок.

Дополнительные сведения см. в описании структуры [олеуичанжесаурце](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
