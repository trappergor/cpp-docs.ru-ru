---
title: Класс CFontDialog
ms.date: 11/04/2016
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
ms.openlocfilehash: 5c9e3a7de10b6ba0913b02c5f79dcc63c89adce5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525181"
---
# <a name="cfontdialog-class"></a>Класс CFontDialog

Позволяет включить диалоговое окно выбора шрифтов в приложение.

## <a name="syntax"></a>Синтаксис

```
class CFontDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFontDialog::CFontDialog](#cfontdialog)|Создает объект `CFontDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFontDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|
|[CFontDialog::GetCharFormat](#getcharformat)|Извлекает форматирования знаков в выбранном шрифте.|
|[CFontDialog::GetColor](#getcolor)|Возвращает цвет выбранного шрифта.|
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Назначает характеристики выбранный шрифт для `LOGFONT` структуры.|
|[CFontDialog::GetFaceName](#getfacename)|Возвращает имя начертания выбранного шрифта.|
|[CFontDialog::GetSize](#getsize)|Возвращает размер выбранного шрифта.|
|[CFontDialog::GetStyleName](#getstylename)|Возвращает имя стиля выбранного шрифта.|
|[CFontDialog::GetWeight](#getweight)|Возвращает вес подмножества выбранного шрифта.|
|[CFontDialog::IsBold](#isbold)|Определяет, является ли шрифт полужирным.|
|[CFontDialog::IsItalic](#isitalic)|Определяет, является ли шрифт курсивом.|
|[CFontDialog::IsStrikeOut](#isstrikeout)|Определяет, отображается ли с зачеркнутый шрифт.|
|[CFontDialog::IsUnderline](#isunderline)|Определяет, является ли шрифт подчеркнутым.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFontDialog::m_cf](#m_cf)|Структура, используемая для настройки `CFontDialog` объекта.|

## <a name="remarks"></a>Примечания

Объект `CFontDialog` объект представляет собой диалоговое окно со списком шрифтов, установленных в системе. Пользователь может выбрать определенный шрифт из списка, и этот выбор затем передаются обратно в приложение.

Для создания `CFontDialog` объекта, используйте предоставленный конструктор, или получение нового подкласса и использовать собственный пользовательский конструктор.

Один раз `CFontDialog` объект был создан, можно использовать `m_cf` структуры для инициализации значения или состояния элементов управления в диалоговом окне. [M_cf](#m_cf) структуры имеет тип [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta). Дополнительные сведения об этой структуре см. в разделе Windows SDK.

После инициализации объекта диалогового окна элементы управления, вызовите `DoModal` функция-член отображается диалоговое окно и позволяет пользователю выбрать шрифт. `DoModal` Возвращает, является ли пользователь выбрал кнопку ОК (IDOK) или Отмена (IDCANCEL).

Если `DoModal` возвращает IDOK, можно использовать один из `CFontDialog`в функции-члены для получения сведений, введенное пользователем.

Можно использовать Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) функция для определения, произошла ли ошибка во время инициализации диалогового окна и Дополнительные сведения об ошибке. Дополнительные сведения по этой функции см. в разделе Windows SDK.

`CFontDialog` использует COMMDLG. DLL-файл, который поставляется с Windows 3.1 и более поздних версиях.

Чтобы настроить в диалоговом окне, являются производными от класса `CFontDialog`, предоставляют шаблон настраиваемое диалоговое окно и добавить схему сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любые необработанные сообщения должны передаваться в базовый класс.

Настройка функция-обработчик не является обязательным.

Дополнительные сведения об использовании `CFontDialog`, см. в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

##  <a name="cfontdialog"></a>  CFontDialog::CFontDialog

Создает объект `CFontDialog`.

```
CFontDialog(
    LPLOGFONT lplfInitial = NULL,
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,
    DWORD dwFlags = CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*plfInitial*<br/>
Указатель на [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) структура данных, которая позволяет настроить некоторые характеристики шрифта.

*charFormat*<br/>
Указатель на [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) структура данных, которая позволяет настроить некоторые характеристики шрифта в форматированного текста элемента управления edit.

*dwFlags*<br/>
Указывает один или несколько флагов выбора шрифта. Одно или несколько предустановленных значений можно объединить с помощью побитового оператора OR. Если вы изменяете член структуры `m_cf.Flag`, используйте оператор OR в изменениях, чтобы сохранить поведение по умолчанию. Сведения о каждом из этих флагов см. в описании [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta) структуры в пакете Windows SDK.

*pdcPrinter*<br/>
Указатель на контекст принтера. Если этот параметр задан, он указывает на контекст принтера, для которого выбираются шрифты.

*pParentWnd*<br/>
Указатель на родительское окно или окно владельца диалогового окна шрифта.

### <a name="remarks"></a>Примечания

Обратите внимание, что конструктор автоматически заполняет члены структуры `CHOOSEFONT`. Их следует изменять, только если вам требуется диалоговое окно, отличное от стандартного.

> [!NOTE]
>  Первая версия этой функции существует, только если элементы управления форматированным редактированием не поддерживаются.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]

##  <a name="domodal"></a>  CFontDialog::DoModal

Вызывайте эту функцию для отображения диалоговое окно Windows распространенных шрифт и разрешает пользователю выбрать шрифт.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK и IDCANCEL. Если возвращается IDCANCEL, вызовите Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) функцию, чтобы определить, произошла ли ошибка.

IDOK и IDCANCEL являются константы, указывающие, является ли пользователь выбрал кнопку ОК или "Отмена".

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные элементы управления диалогового окна шрифта путем определения участников [m_cf](#m_cf) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.

Если `DoModal` возвращает IDOK, можно вызвать другой член функции, чтобы получить параметры или данные, введенные пользователем в диалоговом окне.

### <a name="example"></a>Пример

  См. в примерах [CFontDialog::CFontDialog](#cfontdialog) и [CFontDialog::GetColor](#getcolor).

##  <a name="getcharformat"></a>  CFontDialog::GetCharFormat

Извлекает форматирования знаков в выбранном шрифте.

```
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Объект [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) структуру, содержащую сведения о форматировании символов выбранного шрифта.

##  <a name="getcolor"></a>  CFontDialog::GetColor

Вызывайте эту функцию для получения цвет выбранного шрифта.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет выбранного шрифта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

##  <a name="getcurrentfont"></a>  CFontDialog::GetCurrentFont

Вызывайте эту функцию для назначения характеристики выбранный шрифт членами [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) структуры.

```
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>Параметры

*lplf*<br/>
Указатель на `LOGFONT` структуры.

### <a name="remarks"></a>Примечания

Другие `CFontDialog` функций-членов предоставляются для доступа к отдельным характеристик текущего шрифта.

Если эта функция вызывается во время вызова [DoModal](#domodal), он возвращает текущее выделение во время (что пользователь видит или имеет изменен в диалоговом окне). Если эта функция вызывается после вызова `DoModal` (только если `DoModal` возвращает IDOK), он возвращает какие фактически выбрал пользователь.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

##  <a name="getfacename"></a>  CFontDialog::GetFaceName

Вызывайте эту функцию для получения название шрифта выбранного шрифта.

```
CString GetFaceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя начертания шрифта, выбранного в `CFontDialog` диалоговое окно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

##  <a name="getsize"></a>  CFontDialog::GetSize

Вызывайте эту функцию для определения размера выбранного шрифта.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер шрифта в десятых долях точку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

##  <a name="getstylename"></a>  CFontDialog::GetStyleName

Вызывайте эту функцию для извлечения имени стиля выбранного шрифта.

```
CString GetStyleName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя стиля шрифта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

##  <a name="getweight"></a>  CFontDialog::GetWeight

Вызывайте эту функцию для получения вес подмножества выбранного шрифта.

```
int GetWeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Вес выбранного шрифта.

### <a name="remarks"></a>Примечания

Дополнительные сведения о Вес шрифта, см. в разделе [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

##  <a name="isbold"></a>  CFontDialog::IsBold

Вызывайте эту функцию, чтобы определить, является ли шрифт полужирным.

```
BOOL IsBold() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выбранный шрифт полужирным характеристика включена; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

##  <a name="isitalic"></a>  CFontDialog::IsItalic

Вызывайте эту функцию, чтобы определить, является ли шрифт курсивом.

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если шрифт имеет курсивное характеристика включена; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

##  <a name="isstrikeout"></a>  CFontDialog::IsStrikeOut

Вызывайте эту функцию, чтобы определить, если выбранный шрифт будет отображаться с зачеркнутый.

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если шрифт имеет зачеркнутый характеристика включена; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

##  <a name="isunderline"></a>  CFontDialog::IsUnderline

Вызывайте эту функцию, чтобы определить, если выбранный шрифт подчеркнутым.

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если шрифт имеет подчеркивание характеристика включена; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

##  <a name="m_cf"></a>  CFontDialog::m_cf

Структура, члены которой хранения характеристики объекта диалогового окна.

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>Примечания

После построения `CFontDialog` объекта, можно использовать `m_cf` для изменения различных аспектов диалоговом окне перед вызовом `DoModal` функция-член. Дополнительные сведения об этой структуре см. в разделе [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC HIERSVR](../../visual-cpp-samples.md)<br/>
[Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

