---
title: Класс Колеинсертдиалог
ms.date: 11/04/2016
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
ms.openlocfilehash: a884f946b60be0567f39477f434db8efe041e393
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503932"
---
# <a name="coleinsertdialog-class"></a>Класс Колеинсертдиалог

Используется для диалогового окна OLE "Вставить объект".

## <a name="syntax"></a>Синтаксис

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Колеинсертдиалог:: Колеинсертдиалог](#coleinsertdialog)|Создает объект `COleInsertDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Колеинсертдиалог:: CreateItem](#createitem)|Создает элемент, выбранный в диалоговом окне.|
|[Колеинсертдиалог::D Омодал](#domodal)|Отображает диалоговое окно OLE: Вставка объекта.|
|[Колеинсертдиалог::, ClassID](#getclassid)|Возвращает CLSID, связанный с выбранным элементом.|
|[Колеинсертдиалог:: Жетдраваспект](#getdrawaspect)|Указывает, следует ли нарисовать элемент в виде значка.|
|[Колеинсертдиалог:: Жетиконикметафиле](#geticonicmetafile)|Возвращает маркер для метафайла, связанного со значком этого элемента.|
|[Колеинсертдиалог:: путь к файлу](#getpathname)|Возвращает полный путь к файлу, выбранному в диалоговом окне.|
|[Колеинсертдиалог:: Жетселектионтипе](#getselectiontype)|Возвращает тип выбранного объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Колеинсертдиалог:: m_io](#m_io)|Структура типа ОЛЕУИИНСЕРТОБЖЕКТ, которая управляет поведением диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект класса `COleInsertDialog` , если нужно вызвать это диалоговое окно. После создания объекта `COleInsertDialog` можно использовать структуру [m_io](#m_io) для инициализации значений или состояний элементов управления в диалоговом окне. `m_io` Структура имеет тип олеуиинсертобжект. Дополнительные сведения об использовании этого класса диалогового окна см. в описании функции члена [DoModal](#domodal) .

> [!NOTE]
>  Созданный мастером приложений код контейнера использует этот класс.

Дополнительные сведения см. в описании структуры [олеуиинсертобжект](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) в Windows SDK.

Дополнительные сведения о диалоговых окнах, связанных с OLE, см. в разделе [диалоговые окна статьи в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

[коледиалог](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксодлгс. h

##  <a name="coleinsertdialog"></a>Колеинсертдиалог:: Колеинсертдиалог

Эта функция конструирует только `COleInsertDialog` объект.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаг создания, который содержит любое число следующих значений, объединяемых с помощью оператора побитового или:

- IOF_SHOWHELP Указывает, что при вызове диалогового окна появится кнопка Справка.

- IOF_SELECTCREATENEW указывает, что при вызове диалогового окна сначала будет выбран переключатель Создать новый. Этот параметр используется по умолчанию и не может использоваться с IOF_SELECTCREATEFROMFILE.

- IOF_SELECTCREATEFROMFILE Указывает, что при вызове диалогового окна будет выбран переключатель Создать из файла. Не может использоваться с IOF_SELECTCREATENEW.

- IOF_CHECKLINK указывает, что флажок проверки связи будет проверяться изначально при вызове диалогового окна.

- IOF_DISABLELINK Указывает, что при вызове диалогового окна флажок связь будет отключен.

- IOF_CHECKDISPLAYASICON указывает, что флажок Отображать как значок будет проверяться изначально, отображается текущий значок, а при вызове этого диалогового окна будет включена кнопка Изменить значок.

- IOF_VERIFYSERVERSEXIST Указывает, что диалоговое окно должно проверить классы, добавляемые в список, убедившись, что серверы, указанные в базе данных регистрации, существуют до отображения диалогового окна. Установка этого флага может значительно повредить производительность.

*ппарентвнд*<br/>
Указывает на родительский элемент или объект окна-владельца ( `CWnd`типа), которому принадлежит объект диалогового окна. Если это значение равно NULL, родительскому окну объекта диалогового окна присваивается основное окно приложения.

### <a name="remarks"></a>Примечания

Чтобы открыть диалоговое окно, вызовите функцию [DoModal](#domodal) .

##  <a name="createitem"></a>Колеинсертдиалог:: CreateItem

Вызывайте эту функцию для создания объекта типа [COleClientItem](../../mfc/reference/coleclientitem-class.md) только в том случае, если [DoModal](#domodal) возвращает идок.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>Параметры

*питем*<br/>
Указывает на создаваемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент был создан; в противном случае — 0.

### <a name="remarks"></a>Примечания

Перед вызовом этой `COleClientItem` функции необходимо выделить объект.

##  <a name="domodal"></a>Колеинсертдиалог::D Омодал

Вызовите эту функцию, чтобы отобразить диалоговое окно OLE: Вставка объекта.

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Одно из следующих значений:

`COleInsertDialog::DocObjectsOnly`вставляет только Докобжектс.

`COleInsertDialog::ControlsOnly`вставляет только элементы управления ActiveX.

Ноль не вставляет ни DocObject, ни элемент управления ActiveX. Это значение приводит к той же реализации, что и первый приведенный выше прототип.

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- ИДОК, если диалоговое окно было успешно отображено.

- ИДКАНЦЕЛ, если пользователь отменил диалоговое окно.

- ИДАБОРТ, если произошла ошибка. Если возвращается ИДАБОРТ, вызовите функцию-член [коледиалог:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) , чтобы получить дополнительные сведения о типе произошедшей ошибки. Список возможных ошибок см. в описании функции [олеуиинсертобжект](/windows/win32/api/oledlg/nf-oledlg-oleuiinsertobjectw) в Windows SDK.

### <a name="remarks"></a>Примечания

Если требуется инициализировать различные элементы управления диалогового окна путем установки элементов структуры [m_io](#m_io) , следует выполнить это действие перед вызовом метода `DoModal`, но после создания объекта диалогового окна.

Если `DoModal` возвращает идок, можно вызвать другие функции члена для получения параметров или данных, вводимых в диалоговое окно пользователем.

##  <a name="getclassid"></a>Колеинсертдиалог::, ClassID

Вызывайте эту функцию, чтобы получить CLSID, связанный с выбранным элементом, только если [DoModal](#domodal) возвращает идок, а `COleInsertDialog::createNewItem`тип выбора —.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает CLSID, связанный с выбранным элементом.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ключ CLSID](/windows/win32/com/clsid-key-hklm) в Windows SDK.

##  <a name="getdrawaspect"></a>Колеинсертдиалог:: Жетдраваспект

Вызовите эту функцию, чтобы определить, выбрал ли пользователь Отображение выбранного элемента в виде значка.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод, необходимый для отрисовки объекта.

- DVASPECT_CONTENT возвращается, если флажок "отображать как значок" не установлен.

- DVASPECT_ICON возвращается, если установлен флажок "отображать как значок".

### <a name="remarks"></a>Примечания

Вызывайте эту функцию только в том случае, если [DoModal](#domodal) возвращает идок.

Дополнительные сведения о аспекте рисования см. в разделе Структура данных [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

##  <a name="geticonicmetafile"></a>Колеинсертдиалог:: Жетиконикметафиле

Вызовите эту функцию, чтобы получить маркер для метафайла, содержащего значок выбранного элемента.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маркер для метафайла, содержащего значок выбранного элемента, если флажок Отображать как значок был установлен при отклонении диалогового окна нажатием кнопки **ОК**. в противном случае — NULL.

##  <a name="getpathname"></a>Колеинсертдиалог:: путь к файлу

Вызывайте эту функцию, чтобы получить полный путь к выбранному файлу, только если [DoModal](#domodal) возвращает идок, а тип выбора `COleInsertDialog::createNewItem`— нет.

```
CString GetPathName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный путь к файлу, выбранному в диалоговом окне. Если тип выделения — `createNewItem`, эта функция возвращает бессмысленное `CString` значение в режиме выпуска или вызывает утверждение в режиме отладки.

##  <a name="getselectiontype"></a>Колеинсертдиалог:: Жетселектионтипе

Вызывайте эту функцию для получения выбранного типа выбора при отклонении диалогового окна Вставка объекта нажатием кнопки **ОК**.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип сделанного выбора.

### <a name="remarks"></a>Примечания

Значения возвращаемого типа задаются `Selection` типом перечисления, объявленным `COleInsertDialog` в классе.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

Ниже приведены краткие описания этих значений.

- `COleInsertDialog::createNewItem`Выбран переключатель Создать новый.

- `COleInsertDialog::insertFromFile`Выбран переключатель "создать из файла", а флажок "ссылка" не установлен.

- `COleInsertDialog::linkToFile`Выбран переключатель Создать из файла и установлен флажок связь.

##  <a name="m_io"></a>Колеинсертдиалог:: m_io

Структура типа ОЛЕУИИНСЕРТОБЖЕКТ, используемая для управления поведением диалогового окна «Вставка объекта».

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>Примечания

Члены этой структуры можно изменять напрямую или с помощью функций-членов.

Дополнительные сведения см. в описании структуры [олеуиинсертобжект](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) в Windows SDK.

## <a name="see-also"></a>См. также

[Пример OCLIENT MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
