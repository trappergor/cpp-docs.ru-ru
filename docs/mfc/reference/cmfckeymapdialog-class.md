---
title: "Класс CMFCKeyMapDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCKeyMapDialog class
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6599f5c3cda6eb407f4545d42528c1c68950b94c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Вызывается платформой для создания строку, описывающую сопоставления ключей. По умолчанию строка содержит имя команды, сочетания клавиш, используемые и Описание ключевых ярлык.|  
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Получает строку, содержащую список сочетаний клавиш, связанных с указанной командой.|  
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Вызывается средой перед вставкой нового элемента в внутренний список управления, который поддерживает управление сопоставления с помощью клавиатуры.|  
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Вызывается средой, чтобы напечатать заголовок для карты клавиатуры на новой странице.|  
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Вызывается платформой для печати элемент сопоставления клавиатуры.|  
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Вызывается платформой для задания заголовки для столбцов в элементе управления внутренний список, который поддерживает управление сопоставления с помощью клавиатуры.|  
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Вызывается платформой, когда пользователь щелкает **печати** кнопки.|  
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Вызывается платформой для задания ширины столбцов в элементе управления внутренний список, который поддерживает управление сопоставления с помощью клавиатуры.|  
  
## <a name="remarks"></a>Примечания  
 Используйте `CMFCKeyMapDialog` класса, чтобы реализовать диалоговое окно сопоставления изменяемые клавиатуры. Диалоговое окно использует элемент представления списка для отображения сочетания клавиш и соответствующих команд.  
  
 Для использования `CMFCKeyMapDialog` класса в приложении, передать указатель фрейма главного окна в качестве параметра `CMFCKeyMapDialog` конструктор. Затем вызовите `DoModal` метод для запуска модального диалогового окна.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxkeymapdialog.h  
  
##  <a name="cmfckeymapdialog"></a>CMFCKeyMapDialog::CMFCKeyMapDialog  
 Создает объект `CMFCKeyMapDialog`.  
  
```  
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bEnablePrint=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParentFrame`  
 Указатель на родительское окно элемента `CMFCKeyMapDialog` объекта.  
  
 [in] `bEnablePrint`  
 `TRUE`Если можно распечатать список сочетаний клавиш; в противном случае — `FALSE`. Значение по умолчанию — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCKeyMapDialog` класса. Этот пример является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#21;](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CMFCKeyMapDialog::DoModal  
 Отображает диалоговое окно сопоставления клавиатуры.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Знаковое целое число, например `IDOK` или `IDCANCEL`, который передается [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) метод. Метод, в свою очередь, закрытие диалогового окна. Дополнительные сведения см. в разделе [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal).  
  
### <a name="remarks"></a>Примечания  
 Диалоговое окно сопоставления клавиатуры позволяет выбрать и назначить сочетания клавиш для различных категорий команд. Кроме того можно скопировать выбранный сочетания клавиш и их описание в буфер обмена.  
  
##  <a name="formatitem"></a>CMFCKeyMapDialog::FormatItem  
 Вызывается платформой для создания строку, описывающую сопоставления ключей. По умолчанию строка содержит имя команды, сочетания клавиш, используемые и Описание ключевых ярлык.  
  
```  
virtual CString FormatItem(int nItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nItem`  
 Отсчитываемый от нуля индекс элемента в списке внутреннего ключа сопоставлений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий форматированный текст.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcommandkeys"></a>CMFCKeyMapDialog::GetCommandKeys  
 Получает строковое значение. Строка содержит список сочетаний клавиш, которые связаны с определенной команды.  
  
```  
virtual CString GetCommandKeys(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Разделенных точкой с запятой (;) список сочетаний клавиш, связанный с заданной команды.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="oninsertitem"></a>CMFCKeyMapDialog::OnInsertItem  
 Вызывается средой перед вставкой нового элемента в элементе управления внутренний список, который поддерживает управление сопоставления с помощью клавиатуры.  
  
```  
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,  
    int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку панели инструментов, который используется для сопоставления сочетания клавиш клавиатуры имя команды и описание. Элемент карты ключей хранится в элементе управления внутренний список.  
  
 [in] `nItem`  
 Отсчитываемый от нуля индекс, указывающий место вставки нового элемента карты ключей в элементе управления внутренний список.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onprintheader"></a>CMFCKeyMapDialog::OnPrintHeader  
 Вызывается средой, чтобы напечатать заголовок для карты клавиатуры на новой странице.  
  
```  
virtual int OnPrintHeader(
    CDC& dc,  
    int nPage,  
    int cx) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dc`  
 Контекст устройства для принтера.  
  
 [in] `nPage`  
 Номер страницы для печати.  
  
 [in] `cx`  
 Горизонтальное смещение заголовка в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха высоту печатного текста. Для получения дополнительной информации ознакомьтесь с разделом возвращают значение [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext).  
  
### <a name="remarks"></a>Примечания  
 Платформа использует этот метод для печати с раскладкой. По умолчанию этот метод выводит номер страницы, имя приложения и заголовок диалогового окна.  
  
##  <a name="onprintitem"></a>CMFCKeyMapDialog::OnPrintItem  
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
 [in] `dc`  
 Контекст устройства принтера.  
  
 [in] `nItem`  
 Отсчитываемый от нуля индекс элемента для печати.  
  
 [in] `y`  
 Смещение по вертикали между верхней части страницы и положение элемента управления.  
  
 [in] `cx`  
 Смещение по горизонтали между левой части страницы и положение элемента.  
  
 [in] `bCalcHeight`  
 `TRUE`Чтобы рассчитать высоту лучшим для печати элемента; `FALSE` усечение печати элемента, чтобы он соответствовал пространства по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота элемента в печати.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для печати карты ключей элемента диалогового окна. По умолчанию этот метод выводит имя команды, сочетания клавиш и команды описание элемента.  
  
##  <a name="onsetcolumns"></a>CMFCKeyMapDialog::OnSetColumns  
 Вызывается платформой для задания заголовки для столбцов в элементе управления внутренний список, который поддерживает управление сопоставления с помощью клавиатуры.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод получает заголовки столбцов из трех ресурсов. Заголовок столбца команда является из IDS_AFXBARRES_COMMAND, является заголовком столбца ключа из IDS_AFXBARRES_KEYS, и заголовок столбца описания является IDS_AFXBARRES_DESCRIPTION.  
  
##  <a name="printkeymap"></a>CMFCKeyMapDialog::PrintKeyMap  
 Вызывается платформой, когда пользователь щелкает **печати** кнопки.  
  
```  
virtual void PrintKeyMap();
```  
  
### <a name="remarks"></a>Примечания  
 `PrintKeyMap` Метод выводит карты ключей. Он запускает новое задание печати, а затем многократно вызывает [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) и [CMFCKeyMapDialog::OnPrintItem](#onprintitem) методы, пока не выводятся все сопоставления ключей.  
  
##  <a name="setcolumnswidth"></a>CMFCKeyMapDialog::SetColumnsWidth  
 Вызывается платформой для задания ширины столбцов в элементе управления внутренний список, который поддерживает управление сопоставления с помощью клавиатуры.  
  
```  
virtual void SetColumnsWidth();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает внутренний список столбцов элемента управления по умолчанию ширина. Во-первых вычисляется ширину столбца ключей ярлык. Затем размещенных трети оставшуюся ширину столбца command и оставшиеся две трети выделяется в столбце «Описание».  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

