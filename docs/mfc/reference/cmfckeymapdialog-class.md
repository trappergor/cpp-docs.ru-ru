---
title: Класс CMFCKeyMapDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25d86a4797479fe3ee95dde162e22cde63aaa71e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfckeymapdialog-class"></a>Класс CMFCKeyMapDialog
`CMFCKeyMapDialog` Класс поддерживает элемент управления, который сопоставляет команды клавишам на клавиатуре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|Создает объект `CMFCKeyMapDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCKeyMapDialog::DoModal](#domodal)|Отображает диалоговое окно сопоставления клавиатуры.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Вызывается платформой для создания строку, описывающую сопоставления ключей. По умолчанию строка содержит имя команды, сочетания клавиш, используемые и описание ключа сочетания клавиш.|  
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Возвращает строку, содержащую список сочетаний клавиш, связанных с указанной командой.|  
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Вызывается платформой перед вставкой элемента в внутренний список управления, который поддерживает элемент управления сопоставления клавиатуры.|  
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Вызывается платформой, чтобы напечатать заголовок карты клавиатуры на новую страницу.|  
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Вызывается платформой для вывода элемента сопоставления клавиатуры.|  
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Вызывается платформой, чтобы задать заголовки для столбцов в элементе управления внутренний список, который поддерживает сопоставление клавиатуры элемент управления.|  
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Вызывается платформой, когда пользователь щелкает **печати** кнопки.|  
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Вызывается платформой для задания ширины столбцов в элементе управления внутренний список, который поддерживает сопоставление клавиатуры элемент управления.|  
  
## <a name="remarks"></a>Примечания  
 Используйте `CMFCKeyMapDialog` класса для реализации диалогового окна сопоставление с раскрывающимися списками клавиатуры. Диалоговое окно использует элементе представления списка для отображения сочетания клавиш и соответствующих команд.  
  
 Для использования `CMFCKeyMapDialog` класса в приложении, передайте в указатель фрейма главного окна в качестве параметра для `CMFCKeyMapDialog` конструктор. Затем вызовите `DoModal` метода для запуска модального диалогового окна.  
  
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
 [in] `pWndParentFrame`  
 Указатель на родительское окно `CMFCKeyMapDialog` объекта.  
  
 [in] `bEnablePrint`  
 `TRUE` Если можно распечатать список сочетаний клавиш; в противном случае `FALSE`. Значение по умолчанию — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCKeyMapDialog` класса. Данный пример является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CMFCKeyMapDialog::DoModal  
 Отображает диалоговое окно сопоставления клавиатуры.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число со знаком, таких как `IDOK` или `IDCANCEL`, который передается [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) метод. Метод, в свою очередь, закрытие диалогового окна. Дополнительные сведения см. в разделе [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal).  
  
### <a name="remarks"></a>Примечания  
 Диалоговое окно сопоставления клавиатуры можно выбрать и назначить сочетания клавиш для разных категорий команд. Кроме того можно скопировать выбранный сочетания клавиш и их описание в буфер обмена.  
  
##  <a name="formatitem"></a>  CMFCKeyMapDialog::FormatItem  
 Вызывается платформой для создания строку, описывающую сопоставления ключей. По умолчанию строка содержит имя команды, сочетания клавиш, используемые и описание ключа сочетания клавиш.  
  
```  
virtual CString FormatItem(int nItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nItem`  
 Отсчитываемый от нуля индекс элемента в во внутренний список сопоставлений ключей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий форматированный текст.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcommandkeys"></a>  CMFCKeyMapDialog::GetCommandKeys  
 Получает строковое значение. Строка содержит перечень сочетаний клавиш, связанных с указанной команды.  
  
```  
virtual CString GetCommandKeys(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Разделенный точками с запятой (;) список сочетаний клавиш, связанный с указанной команды.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="oninsertitem"></a>  CMFCKeyMapDialog::OnInsertItem  
 Вызывается платформой перед вставкой элемента в элементе управления внутренний список, который поддерживает элемент управления сопоставления клавиатуры.  
  
```  
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,  
    int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку панели инструментов, используемый для сопоставления сочетания клавиш клавиатуры для команды имя и описание. Элемент карты ключей хранится в элементе управления внутренний список.  
  
 [in] `nItem`  
 Отсчитываемый от нуля индекс, указывающий место вставки нового элемента карты ключей в элементе управления внутренний список.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onprintheader"></a>  CMFCKeyMapDialog::OnPrintHeader  
 Вызывается платформой, чтобы напечатать заголовок карты клавиатуры на новую страницу.  
  
```  
virtual int OnPrintHeader(
    CDC& dc,  
    int nPage,  
    int cx) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dc`  
 Контекст устройства принтера.  
  
 [in] `nPage`  
 Номер страницы для печати.  
  
 [in] `cx`  
 Горизонтальное смещение заголовка в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения высоту печати текста. Дополнительные сведения см. в разделе разделе возвращают значение [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext).  
  
### <a name="remarks"></a>Примечания  
 Платформа использует этот метод для печати с раскладкой. По умолчанию этот метод выводит номер страницы, имя приложения и заголовок диалогового окна.  
  
##  <a name="onprintitem"></a>  CMFCKeyMapDialog::OnPrintItem  
 Вызывается платформой для вывода элемента сопоставления клавиатуры.  
  
```  
virtual int OnPrintItem(
    CDC& dc,  
    int nItem,  
    int y,  
    int cx,  
    BOOL bCalcHeight) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dc`  
 Контекст устройства принтера.  
  
 [in] `nItem`  
 Отсчитываемый от нуля индекс элемента для печати.  
  
 [in] `y`  
 Смещение по вертикали между верхним краем страницы и положение элемента.  
  
 [in] `cx`  
 Смещение по горизонтали между левой части страницы и положение элемента.  
  
 [in] `bCalcHeight`  
 `TRUE` для вычисления наиболее высоту для элемента печати; `FALSE` усечение печати элемента так, чтобы по умолчанию пустое пространство.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота элемента в печати.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для элемента карты ключей диалогового окна печати. По умолчанию этот метод выводит имя команды, сочетания клавиш и команда описание элемента.  
  
##  <a name="onsetcolumns"></a>  CMFCKeyMapDialog::OnSetColumns  
 Вызывается платформой, чтобы задать заголовки для столбцов в элементе управления внутренний список, который поддерживает сопоставление клавиатуры элемент управления.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод получает заголовки для столбцов с тремя ресурсами. Заголовок столбца команды должно из IDS_AFXBARRES_COMMAND, заголовок столбца ключа является из IDS_AFXBARRES_KEYS, и заголовок столбца описания из IDS_AFXBARRES_DESCRIPTION.  
  
##  <a name="printkeymap"></a>  CMFCKeyMapDialog::PrintKeyMap  
 Вызывается платформой, когда пользователь щелкает **печати** кнопки.  
  
```  
virtual void PrintKeyMap();
```  
  
### <a name="remarks"></a>Примечания  
 `PrintKeyMap` Метод выводит карты ключей. Он запускает новое задание печати, а затем повторно вызывает [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) и [CMFCKeyMapDialog::OnPrintItem](#onprintitem) методы, пока не выводятся все сопоставления ключей.  
  
##  <a name="setcolumnswidth"></a>  CMFCKeyMapDialog::SetColumnsWidth  
 Вызывается платформой для задания ширины столбцов в элементе управления внутренний список, который поддерживает сопоставление клавиатуры элемент управления.  
  
```  
virtual void SetColumnsWidth();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает внутренний список столбцов элемента управления по умолчанию ширина. Во-первых вычисляется ширину столбца ключи ярлык. Затем размещенных трети оставшуюся ширину столбца команды и оставшиеся две трети выделяется в столбце «Описание».  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)
