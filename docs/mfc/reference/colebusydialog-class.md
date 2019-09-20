---
title: Класс Колебусидиалог
ms.date: 11/04/2016
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
ms.openlocfilehash: aa3f0d85bcbf34d325125187b22b38c4da01fb43
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504402"
---
# <a name="colebusydialog-class"></a>Класс Колебусидиалог

Используется для диалоговых окон OLE "Сервер не отвечает" или "Сервер занят".

## <a name="syntax"></a>Синтаксис

```
class COleBusyDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Колебусидиалог:: Колебусидиалог](#colebusydialog)|Создает объект `COleBusyDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Колебусидиалог::D Омодал](#domodal)|Отображает диалоговое окно «занято OLE Server».|
|[Колебусидиалог:: Жетселектионтипе](#getselectiontype)|Определяет выбор, сделанный в диалоговом окне.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Колебусидиалог:: m_bz](#m_bz)|Структура типа ОЛЕУИБУСИ, которая управляет поведением диалогового окна.|

## <a name="remarks"></a>Примечания

При необходимости вызова этих диалоговых окон создайте объект класса `COleBusyDialog` . После создания объекта `COleBusyDialog` можно использовать структуру [m_bz](#m_bz) для инициализации значений или состояний элементов управления в диалоговом окне. `m_bz` Структура имеет тип олеуибуси. Дополнительные сведения об использовании этого класса диалогового окна см. в описании функции члена [DoModal](#domodal) .

> [!NOTE]
>  Созданный мастером приложений код контейнера использует этот класс.

Дополнительные сведения см. в описании структуры [олеуибуси](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) в Windows SDK.

Дополнительные сведения о диалоговых окнах, связанных с OLE, см. в разделе [диалоговые окна статьи в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

[коледиалог](../../mfc/reference/coledialog-class.md)

`COleBusyDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксодлгс. h

##  <a name="colebusydialog"></a>Колебусидиалог:: Колебусидиалог

Эта функция конструирует `COleBusyDialog` только объект.

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*хтаскбуси*<br/>
Работающая задача сервера, которая занята.

*бнотреспондинг*<br/>
Если значение — TRUE, вместо диалогового окна «сервер занят» следует вызвать диалоговое окно «не отвечает». Слово в диалоговом окне не отвечает немного отличается от слова в диалоговом окне «сервер занят», а кнопка «отмена» отключена.

*dwFlags*<br/>
Флаг создания. Может содержать ноль или более следующих значений, Объединенных с помощью оператора побитового или:

- BZ_DISABLECANCELBUTTON Отключение кнопки отмены при вызове диалогового окна.

- BZ_DISABLESWITCHTOBUTTON отключает кнопку переключения на при вызове диалогового окна.

- BZ_DISABLERETRYBUTTON отключить кнопку "повторить" при вызове диалогового окна.

*ппарентвнд*<br/>
Указывает на родительский элемент или объект окна-владельца ( `CWnd`типа), которому принадлежит объект диалогового окна. Если это значение равно NULL, родительскому окну объекта диалогового окна присваивается основное окно приложения.

### <a name="remarks"></a>Примечания

Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal).

Дополнительные сведения см. в описании структуры [олеуибуси](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) в Windows SDK.

##  <a name="domodal"></a>Колебусидиалог::D Омодал

Вызовите эту функцию, чтобы отобразить диалоговое окно OLE Server busy или сервер не отвечает.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- ИДОК, если диалоговое окно было успешно отображено.

- ИДКАНЦЕЛ, если пользователь отменил диалоговое окно.

- ИДАБОРТ, если произошла ошибка. Если возвращается идаборт, вызовите `COleDialog::GetLastError` функцию-член, чтобы получить дополнительные сведения о типе произошедшей ошибки. Список возможных ошибок см. в описании функции [олеуибуси](/windows/win32/api/oledlg/nf-oledlg-oleuibusyw) в Windows SDK.

### <a name="remarks"></a>Примечания

Если требуется инициализировать различные элементы управления диалогового окна путем установки элементов структуры [m_bz](#m_bz) , следует выполнить это действие перед вызовом метода `DoModal`, но после создания объекта диалогового окна.

Если `DoModal` возвращает идок, можно вызвать другие функции, чтобы получить параметры или сведения, введенные пользователем в диалоговое окно.

##  <a name="getselectiontype"></a>Колебусидиалог:: Жетселектионтипе

Вызовите эту функцию, чтобы получить тип выбора, выбранный пользователем в диалоговом окне "сервер занят".

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип сделанного выбора.

### <a name="remarks"></a>Примечания

Значения возвращаемого типа задаются `Selection` типом перечисления, объявленным `COleBusyDialog` в классе.

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

Ниже приведены краткие описания этих значений.

- `COleBusyDialog::switchTo`Была нажата кнопка переключиться на.

- `COleBusyDialog::retry`Была нажата кнопка "повторить".

- `COleBusyDialog::callUnblocked`Вызов для активации сервера теперь разблокирован.

##  <a name="m_bz"></a>Колебусидиалог:: m_bz

Структура типа ОЛЕУИБУСИ, используемая для управления поведением диалогового окна «занято сервером».

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>Примечания

Члены этой структуры могут быть изменены напрямую или через функции-члены.

Дополнительные сведения см. в описании структуры [олеуибуси](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
