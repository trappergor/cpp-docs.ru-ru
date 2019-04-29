---
title: Класс CMFCKeyMapDialog
ms.date: 11/04/2016
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
ms.openlocfilehash: 65aa5ab0f24999ee23a97f383577b69584825502
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388505"
---
# <a name="cmfckeymapdialog-class"></a>Класс CMFCKeyMapDialog

`CMFCKeyMapDialog` Класс поддерживает элемент управления, который сопоставляет команды клавишам на клавиатуре.

## <a name="syntax"></a>Синтаксис

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|Создает объект `CMFCKeyMapDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCKeyMapDialog::DoModal](#domodal)|Отображает диалоговое окно сопоставления клавиатуры.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Вызывается платформой для создания строку, описывающую сопоставления ключей. По умолчанию строка содержит имя команды, сочетаний клавиш, используемых и описание ключа ярлыка.|
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Извлекает строку, которая содержит список сочетаний клавиш, связанных с заданной команды.|
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Вызвано структурой перед вставкой нового элемента в элемент управления внутреннего списка, который поддерживает элемент управления сопоставления клавиатуры.|
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Вызывается платформой, чтобы напечатать заголовок для карты клавиатуры на новую страницу.|
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Вызывается платформой для печати элемент сопоставления клавиатуры.|
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Вызывается платформой для задания заголовков столбцов в элементе управления внутреннего списка, который поддерживает элемент управления сопоставления клавиатуры.|
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Вызывается платформой, когда пользователь щелкает **печати** кнопки.|
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Вызывается платформой для задания ширины столбцов в элементе управления внутреннего списка, который поддерживает элемент управления сопоставления клавиатуры.|

## <a name="remarks"></a>Примечания

Используйте `CMFCKeyMapDialog` класс для реализации диалоговое окно сопоставления можно изменять клавиатуры. Диалоговое окно используется элемент управления списка для отображения сочетаний клавиш и соответствующих команд.

Чтобы использовать `CMFCKeyMapDialog` класса в приложении, передать указатель фрейма главного окна в качестве параметра `CMFCKeyMapDialog` конструктор. Затем вызовите `DoModal` метод, чтобы запустить модальное диалоговое окно.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxkeymapdialog.h

##  <a name="cmfckeymapdialog"></a>  CMFCKeyMapDialog::CMFCKeyMapDialog

Создает объект `CMFCKeyMapDialog`.

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>Параметры

*pWndParentFrame*<br/>
[in] Указатель на родительское окно `CMFCKeyMapDialog` объекта.

*bEnablePrint*<br/>
[in] Значение TRUE, если можно напечатать список сочетаний клавиш; в противном случае — значение FALSE. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCKeyMapDialog` класса. Этот пример является частью [Visual Studio демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

##  <a name="domodal"></a>  CMFCKeyMapDialog::DoModal

Отображает диалоговое окно сопоставления клавиатуры.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Целое число со знаком, например IDOK и IDCANCEL, который передается [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) метод. Метод, в свою очередь, закрытие диалогового окна. Дополнительные сведения см. в разделе [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal).

### <a name="remarks"></a>Примечания

Диалоговое окно клавиатуры сопоставления позволяет выбрать и назначить сочетания клавиш для различных категорий команд. Кроме того выбранный сочетания клавиш и их описание можно скопировать в буфер обмена.

##  <a name="formatitem"></a>  CMFCKeyMapDialog::FormatItem

Вызывается платформой для создания строку, описывающую сопоставления ключей. По умолчанию строка содержит имя команды, сочетаний клавиш, используемых и описание ключа ярлыка.

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
[in] Отсчитываемый от нуля индекс элемента в во внутренний список сопоставлений ключей.

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащий форматированный текст.

### <a name="remarks"></a>Примечания

##  <a name="getcommandkeys"></a>  CMFCKeyMapDialog::GetCommandKeys

Получает строковое значение. Строка содержит список сочетаний клавиш, которые связаны с определенной команды.

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
[in] Идентификатор команды.

### <a name="return-value"></a>Возвращаемое значение

Разделенный точками с запятой (;) список сочетаний клавиш, который связан с указанной команды.

### <a name="remarks"></a>Примечания

##  <a name="oninsertitem"></a>  CMFCKeyMapDialog::OnInsertItem

Вызвано структурой перед вставкой нового элемента в элементе управления внутреннего списка, который поддерживает элемент управления сопоставления клавиатуры.

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
[in] Указатель на кнопку панели инструментов, которая используется для сопоставления ключа сочетание клавиш для команды имя и описание. Элемент карты ключей хранится в элементе управления внутренний список.

*nItem*<br/>
[in] Отсчитываемый от нуля индекс, указывающий место вставки нового элемента карты ключей в элементе управления внутренний список.

### <a name="remarks"></a>Примечания

##  <a name="onprintheader"></a>  CMFCKeyMapDialog::OnPrintHeader

Вызывается платформой, чтобы напечатать заголовок для карты клавиатуры на новую страницу.

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>Параметры

*dc*<br/>
[in] Контекст устройства принтера.

*nPage*<br/>
[in] Номер страницы для печати.

*cx*<br/>
[in] Горизонтальное смещение заголовка в пикселях.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения высоту печатном тексте. Дополнительные сведения см. в разделе возвращают значение [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext).

### <a name="remarks"></a>Примечания

Инфраструктура использует этот метод для печати раскладкой. По умолчанию этот метод выводит номер страницы, имя приложения и заголовок диалогового окна.

##  <a name="onprintitem"></a>  CMFCKeyMapDialog::OnPrintItem

Вызывается платформой для печати элемент сопоставления клавиатуры.

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>Параметры

*dc*<br/>
[in] Контекст устройства принтера.

*nItem*<br/>
[in] Отсчитываемый от нуля индекс элемента для печати.

*y*<br/>
[in] Вертикальное смещение между верхней частью страницы и положение элемента.

*cx*<br/>
[in] Горизонтальное смещение между левой части страницы и положение элемента.

*bCalcHeight*<br/>
[in] Значение TRUE, чтобы рассчитать высоту рекомендации для печати элемента; Значение FALSE, чтобы усечь элемент печати, так, чтобы по умолчанию пустое пространство.

### <a name="return-value"></a>Возвращаемое значение

Высота элемента в печати.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод для элемента карты ключей диалогового окна печати. По умолчанию этот метод выводит имя команды, сочетания клавиш и команда описание элемента.

##  <a name="onsetcolumns"></a>  CMFCKeyMapDialog::OnSetColumns

Вызывается платформой для задания заголовков столбцов в элементе управления внутреннего списка, который поддерживает элемент управления сопоставления клавиатуры.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод получает заголовки для столбцов из трех ресурсов. Заголовок столбца команда является из IDS_AFXBARRES_COMMAND, заголовок столбца ключа из IDS_AFXBARRES_KEYS и заголовок столбца описания — от IDS_AFXBARRES_DESCRIPTION.

##  <a name="printkeymap"></a>  CMFCKeyMapDialog::PrintKeyMap

Вызывается платформой, когда пользователь щелкает **печати** кнопки.

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>Примечания

`PrintKeyMap` Метод выводит карты ключей. Он запускает новое задание печати, а затем многократно вызывает [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) и [CMFCKeyMapDialog::OnPrintItem](#onprintitem) методы, пока не выводятся все сопоставления ключей.

##  <a name="setcolumnswidth"></a>  CMFCKeyMapDialog::SetColumnsWidth

Вызывается платформой для задания ширины столбцов в элементе управления внутреннего списка, который поддерживает элемент управления сопоставления клавиатуры.

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>Примечания

Этот метод устанавливает во внутренний список столбцов элемента управления для ширины по умолчанию. Во-первых вычисляются ширину столбца сочетания клавиш. Затем размещенных одну треть от оставшуюся ширину столбца command и оставшиеся две трети выделяется в столбце «Описание».

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)
