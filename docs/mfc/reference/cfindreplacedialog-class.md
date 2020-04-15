---
title: Класс CFindReplaceDialog
ms.date: 11/04/2016
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
ms.openlocfilehash: 7a12d0520d070d74afd9fa91e828970d14c82700
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373862"
---
# <a name="cfindreplacedialog-class"></a>Класс CFindReplaceDialog

Позволяет реализовать в приложении стандартные диалоговые ящики строки Find/Replace.

## <a name="syntax"></a>Синтаксис

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFindReplaceДиалог::CFindReplaceDialog](#cfindreplacedialog)|Вызовите эту `CFindReplaceDialog` функцию для построения объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFindReplaceДиалог::Создание](#create)|Создает и отображает `CFindReplaceDialog` диалоговую коробку.|
|[CFindReplaceДиалог::FindNext](#findnext)|Позвоните в эту функцию, чтобы определить, хочет ли пользователь найти следующее появление строки поиска.|
|[CFindReplaceДиалог::GetFindString](#getfindstring)|Вызов эту функцию для извлечения текущей строки поиска.|
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Вызовите эту функцию, чтобы получить структуру `FINDREPLACE` в зарегистрированном обработчике сообщений.|
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Вызов ими функции для извлечения текущей строки замены.|
|[CFindReplaceДиалого::Исфинирование](#isterminating)|Вызовите эту функцию, чтобы определить, прекращается ли диалоговая будка.|
|[CFindReplaceДиалог::MatchCase](#matchcase)|Позвоните в эту функцию, чтобы определить, хочет ли пользователь точно соответствовать примеру строки поиска.|
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Позвоните в эту функцию, чтобы определить, хочет ли пользователь сопоставлять только все слова.|
|[CFindReplaceДиалог::ЗаменитьВсе](#replaceall)|Вызовите эту функцию, чтобы определить, хочет ли пользователь заменить все случаи строки.|
|[CFindReplaceДиалог::ReplaceCurrent](#replacecurrent)|Вызовите эту функцию, чтобы определить, хочет ли пользователь заменить текущее слово.|
|[CFindReplaceДиалог::Поиск](#searchdown)|Позвоните в эту функцию, чтобы определить, хочет ли пользователь продолжить поиск в нисходящем направлении.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFindReplaceДиалогог::m_fr](#m_fr)|Структура, используемая для `CFindReplaceDialog` настройки объекта.|

## <a name="remarks"></a>Remarks

В отличие от других общих диалогов ы Windows, `CFindReplaceDialog` объекты невозможны, что позволяет пользователям взаимодействовать с другими окнами, пока они находятся на экране. Существует два типа `CFindReplaceDialog` объектов: найти диалоговые ящики и найти/заменить диалоговые ящики. Хотя диалоговые данные позволяют пользователю вводить строки поиска и поиска/замены, они не выполняют ни одной из функций поиска или замены. Вы должны добавить их в приложение.

Чтобы построить `CFindReplaceDialog` объект, используйте предоставленный конструктор (который не имеет аргументов). Так как это бесрежимный диалоговый ящик, выделите объект на куче с помощью **нового** оператора, а не на стеке.

После `CFindReplaceDialog` того, как объект построен, необходимо вызвать функцию члена [Create](#create) для создания и отображения окна диалога.

Используйте [структуру m_fr](#m_fr) для инициализации диалогового окна перед вызовом. `Create` Структура `m_fr` типа [FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew). Для получения дополнительной информации об этой структуре см.

Для того, чтобы родительское окно было уведомлено о запросах на поиск/замену, [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) необходимо использовать функцию Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) и использовать ON_REGISTERED_MESSAGE макрос-карту сообщений в окне кадра, который обрабатывает это зарегистрированное сообщение.

Можно определить, решил ли пользователь прекратить диалоговое окно с функцией `IsTerminating` участника.

`CFindReplaceDialog`опирается на COMMDLG. DLL файл, который поставляется с версиями Windows 3.1 и позже.

Чтобы настроить диалоговое окно, вывежьте класс из, `CFindReplaceDialog`предоставьте пользовательский шаблон диалогов и добавьте карту сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любые необработанные сообщения должны передаваться базовому классу.

Настройка функции крючка не требуется.

Для получения дополнительной `CFindReplaceDialog`информации об использовании см. [Common Dialog Classes](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="cfindreplacedialogcfindreplacedialog"></a><a name="cfindreplacedialog"></a>CFindReplaceДиалог::CFindReplaceDialog

Формирует объект `CFindReplaceDialog`.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>Remarks

Поскольку `CFindReplaceDialog` объект является безмерным диалоговым окном, его необходимо построить на куче с помощью **нового** оператора.

Во время разрушения фреймворк пытается выполнить **удаление этого** на указателе в поле диалога. Если вы создали диалоговую коробку в стеке, **этот** указатель не существует, и неопределенное поведение может привести.

Для получения дополнительной информации о строительстве объектов, `CFindReplaceDialog` см. [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) Используйте [CFindReplaceDialog::Создание](#create) функции члена для отображения диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

## <a name="cfindreplacedialogcreate"></a><a name="create"></a>CFindReplaceДиалог::Создание

Создает и отображает либо Найти или найти / заменить диалог овой `bFindDialogOnly`объект, в зависимости от значения .

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*bFindDialogТолько*<br/>
Установите этот параметр **Find** для отображения окна поиска диалогов. Установите его на FALSE для отображения найти **/ заменить** диалоговую коробку.

*lpszFindЧто*<br/>
Указатель на строку поиска по умолчанию при появляются строки диалогового. Если NULL, диалоговый ящик не содержит строку поиска по умолчанию.

*lpszReplaceWith*<br/>
Указатель на строку замены по умолчанию при появляются строки диалогового. Если NULL, диалоговый ящик не содержит строки замены по умолчанию.

*dwFlags*<br/>
Один или несколько флагов можно использовать для настройки настроек диалогового окна, объединенных с помощью оператора bitwise OR. Значение по умолчанию является FR_DOWN, что указывает на то, что поиск должен идти в нисходящем направлении. Дополнительную информацию об этих флагах можно найти в структуре [FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew) в SDK Windows.

*pParentWnd*<br/>
Указатель на родительское или владельца окна диалогового окна. Это окно, которое получит специальное сообщение о том, что требуется действие поиска/замены. Если NULL, используется основное окно приложения.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект диалоговой коробки был успешно создан; в противном случае 0.

### <a name="remarks"></a>Remarks

Для того, чтобы родительское окно было уведомлено о запросах на поиск/замену, необходимо использовать функцию Windows [RegisterWindowMessage,](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) значение возврата которой является номером сообщения, уникальным для экземпляра приложения. Окно кадра должно иметь запись карты сообщений, `OnFindReplace` которая объявляет функцию обратного вызова (в следующем примере), которая обрабатывает это зарегистрированное сообщение. Следующий фрагмент кода является примером того, как это `CMyRichEditView`сделать для класса окна кадра под названием:

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

В `OnFindReplace` вашей функции вы интерпретируете намерения пользователя с помощью [CFindReplaceDialog::FindNext](#findnext) и [CFindReplaceDialog:::IsTerminating](#isterminating) методы и вы создаете код для поиска / замены операций.

### <a name="example"></a>Пример

  Смотрите пример [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).

## <a name="cfindreplacedialogfindnext"></a><a name="findnext"></a>CFindReplaceДиалог::FindNext

Вызов исчергните эту функцию из функции обратного вызова, чтобы определить, хочет ли пользователь найти следующее появление строки поиска.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь хочет найти следующее появление строки поиска; в противном случае 0.

## <a name="cfindreplacedialoggetfindstring"></a><a name="getfindstring"></a>CFindReplaceДиалог::GetFindString

Вызов эту функцию из функции обратного вызова, чтобы получить строку по умолчанию, чтобы найти.

```
CString GetFindString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка по умолчанию, чтобы найти.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetnotifier"></a><a name="getnotifier"></a>CFindReplaceDialog::GetNotifier

Вызов исправьте эту функцию, чтобы получить указатель в текущее поле диалога Find Replace.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*lParam*<br/>
Значение *lparam* передается функции `OnFindReplace` члена окна кадра.

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущее поле диалога.

### <a name="remarks"></a>Remarks

Он должен использоваться в функции обратного вызова для доступа к текущему `m_fr` диалоговому ящику, вызова его функций члена и доступа к структуре.

### <a name="example"></a>Пример

Смотрите [CFindReplaceDialog::Создайте](#create) пример того, как зарегистрировать обработчик OnFindReplace для получения уведомлений от диалогового окна Find Replace.

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetreplacestring"></a><a name="getreplacestring"></a>CFindReplaceDialog::GetReplaceString

Вызов ими функции для извлечения текущей строки замены.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка по умолчанию, с которой можно заменить найденные строки.

### <a name="example"></a>Пример

  Смотрите пример [CFindReplaceDialog::GetFindString](#getfindstring).

## <a name="cfindreplacedialogisterminating"></a><a name="isterminating"></a>CFindReplaceДиалого::Исфинирование

Вызовите эту функцию в функцию обратного вызова, чтобы определить, решил ли пользователь прекратить диалоговое окно.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь решил прекратить диалоговую будку; в противном случае 0.

### <a name="remarks"></a>Remarks

Если эта функция возвращается ненулевой, следует вызвать функцию `DestroyWindow` участника текущего окна диалогов и установить любую переменную указателя диалогового окна в NULL. Дополнительно, вы также можете хранить найти / заменить текст последний вошел и использовать его для инициализации следующей найти / заменить диалоговое окно.

### <a name="example"></a>Пример

  Смотрите пример [CFindReplaceDialog::GetFindString](#getfindstring).

## <a name="cfindreplacedialogm_fr"></a><a name="m_fr"></a>CFindReplaceДиалогог::m_fr

Используется для настройки `CFindReplaceDialog` объекта.

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>Remarks

`m_fr`представляет собой структуру типа [FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew). Его члены хранят характеристики объекта диалог-коробки. После построения `CFindReplaceDialog` объекта можно `m_fr` использовать для изменения различных значений в диалоговом поле.

Для получения дополнительной информации `FINDREPLACE` об этой структуре, см.

### <a name="example"></a>Пример

  Смотрите пример [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).

## <a name="cfindreplacedialogmatchcase"></a><a name="matchcase"></a>CFindReplaceДиалог::MatchCase

Позвоните в эту функцию, чтобы определить, хочет ли пользователь точно соответствовать примеру строки поиска.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь хочет найти случаи строки поиска, которые точно соответствуют случаю строки поиска; в противном случае 0.

## <a name="cfindreplacedialogmatchwholeword"></a><a name="matchwholeword"></a>CFindReplaceDialog::MatchWholeWord

Позвоните в эту функцию, чтобы определить, хочет ли пользователь сопоставлять только все слова.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь хочет сопоставить только все слова строки поиска; в противном случае 0.

## <a name="cfindreplacedialogreplaceall"></a><a name="replaceall"></a>CFindReplaceДиалог::ЗаменитьВсе

Вызовите эту функцию, чтобы определить, хочет ли пользователь заменить все случаи строки.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь просил заменить все строки, соответствующие строке замены; в противном случае 0.

## <a name="cfindreplacedialogreplacecurrent"></a><a name="replacecurrent"></a>CFindReplaceДиалог::ReplaceCurrent

Вызовите эту функцию, чтобы определить, хочет ли пользователь заменить текущее слово.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь просил заменить выбранную в настоящее время строку строкой замены; в противном случае 0.

## <a name="cfindreplacedialogsearchdown"></a><a name="searchdown"></a>CFindReplaceДиалог::Поиск

Позвоните в эту функцию, чтобы определить, хочет ли пользователь продолжить поиск в нисходящем направлении.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь хочет, чтобы поиск продолжался в нисходящем направлении; 0, если пользователь хочет, чтобы поиск продолжался в восходящем направлении.

## <a name="see-also"></a>См. также раздел

[Класс CCommonДиалог](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
