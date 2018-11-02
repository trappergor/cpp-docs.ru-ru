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
ms.openlocfilehash: e891a6694f0a85715a7d76d196865e3238695753
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571188"
---
# <a name="cfindreplacedialog-class"></a>Класс CFindReplaceDialog

Позволяет реализовать стандартную строку поиска и замены диалоговым окнам в приложении.

## <a name="syntax"></a>Синтаксис

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Вызывайте эту функцию для создания `CFindReplaceDialog` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFindReplaceDialog::Create](#create)|Создает и отображает `CFindReplaceDialog` диалоговое окно.|
|[CFindReplaceDialog::FindNext](#findnext)|Вызывайте эту функцию, чтобы определить, является ли пользователь хочет найти следующее вхождение строки поиска.|
|[CFindReplaceDialog::GetFindString](#getfindstring)|Вызывайте эту функцию для получения текущей строки поиска.|
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Вызывайте эту функцию для получения `FINDREPLACE` структуры в обработчике зарегистрированных сообщений.|
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Вызывайте эту функцию для получения текущей строки замены.|
|[CFindReplaceDialog::IsTerminating](#isterminating)|Вызывайте эту функцию, чтобы определить, завершается ли диалоговое окно.|
|[CFindReplaceDialog::MatchCase](#matchcase)|Вызывайте эту функцию, чтобы определить, требуется ли пользователю должны точности совпадать регистр в строке поиска.|
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Вызывайте эту функцию, чтобы определить, требуется ли пользователю поиск только целых слов.|
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Вызывайте эту функцию, чтобы определить, требуется ли пользователю все вхождения строки замены.|
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Вызывайте эту функцию, чтобы определить, требуется ли пользователю текущего слова, заменяемого.|
|[CFindReplaceDialog::SearchDown](#searchdown)|Вызывайте эту функцию, чтобы определить, требуется ли пользователю поиска, чтобы перейти вниз.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFindReplaceDialog::m_fr](#m_fr)|Структура, используемая для настройки `CFindReplaceDialog` объекта.|

## <a name="remarks"></a>Примечания

В отличие от других Windows окон `CFindReplaceDialog` объекты являются немодальным, что позволяет пользователям взаимодействовать с другими окнами, находящихся на экране. Существует два типа из `CFindReplaceDialog` объектов: поиск диалоговые окна и диалоговые окна поиска и замены. Несмотря на то, что диалоговые окна разрешить пользователю ввода поиска и поиска и замены строк, они не выполняют поиск и замена функции. Необходимо добавить их в приложение.

Для создания `CFindReplaceDialog` объекта, использование предоставленного конструктора (который не содержит аргументов). Так как это немодального диалогового окна, выделить объект в куче с использованием **новый** оператор, а не в стеке.

Один раз `CFindReplaceDialog` объект был создан, необходимо вызвать [создать](#create) функция-член для создания и отображения в диалоговом окне.

Используйте [m_fr](#m_fr) структуры для инициализации диалогового перед вызовом `Create`. `m_fr` Структуры имеет тип [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea). Дополнительные сведения об этой структуре см. в разделе Windows SDK.

Чтобы родительского окна получать уведомления о запросах поиска и замены, необходимо использовать Windows [RegisterWindowMessage](https://msdn.microsoft.com/library/windows/desktop/ms644947) работать и использовать [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) макрос схемы сообщений в кадре окно, которое обрабатывает это зарегистрированных сообщение.

Можно определить, приняла ли пользователь для завершения диалоговое окно с `IsTerminating` функция-член.

`CFindReplaceDialog` использует COMMDLG. DLL-файл, который поставляется с Windows 3.1 и более поздних версиях.

Чтобы настроить в диалоговом окне, являются производными от класса `CFindReplaceDialog`, предоставляют шаблон настраиваемое диалоговое окно и добавить схему сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любые необработанные сообщения должны передаваться в базовый класс.

Настройка функция-обработчик не является обязательным.

Дополнительные сведения об использовании `CFindReplaceDialog`, см. в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

##  <a name="cfindreplacedialog"></a>  CFindReplaceDialog::CFindReplaceDialog

Создает объект `CFindReplaceDialog`.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>Примечания

Так как `CFindReplaceDialog` объект немодального диалогового окна, то необходимо создать в куче с помощью **новый** оператор.

Во время уничтожения, платформа пытается выполнить **удалить этот** на указатель на окно. Если вы создали диалоговое окно в стеке, **это** указателя не существует и может привести к неопределенному поведению.

Дополнительные сведения о построении `CFindReplaceDialog` объектов, см. в разделе [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) Обзор. Используйте [CFindReplaceDialog::Create](#create) функция-член для отображения в диалоговом окне.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

##  <a name="create"></a>  CFindReplaceDialog::Create

Создает и отображает поиска или поиска и замены объект диалогового окна, в зависимости от значения `bFindDialogOnly`.

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*bFindDialogOnly*<br/>
Установите этот параметр в значение TRUE, чтобы отобразить **найти** диалоговое окно. Задайте для него значение FALSE для отображения **поиска и замены** диалоговое окно.

*lpszFindWhat*<br/>
Указатель на строку поиска по умолчанию, когда появится диалоговое окно. Если значение равно NULL, диалоговое окно не содержит строку поиска по умолчанию.

*lpszReplaceWith*<br/>
Указатель на строку замены по умолчанию, когда появится диалоговое окно. Если значение равно NULL, диалоговое окно не содержит строку замены по умолчанию.

*dwFlags*<br/>
Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна, объединенные с помощью битового оператора или. Значение по умолчанию — FR_DOWN, который указывает, что поиск, чтобы перейти вниз. См. в разделе [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea) структуры в пакете SDK для Windows, Дополнительные сведения о эти флаги.

*pParentWnd*<br/>
Указатель на окно родительский объект или владельца диалогового окна. Это окно, в который будет получать специальное сообщение, указывающее, запрашивается действие поиска и замены. Если значение равно NULL, используется главное окно приложения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект диалогового окна был успешно создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Чтобы родительского окна получать уведомления о запросах поиска и замены, необходимо использовать Windows [RegisterWindowMessage](https://msdn.microsoft.com/library/windows/desktop/ms644947) функции, возвращаемое значение которой является номер сообщения, уникальный для экземпляра приложения. Фрейма окна должны иметь запись сопоставления сообщений, в которой объявляется функция обратного вызова ( `OnFindReplace` в следующем примере), обрабатывает это зарегистрированных сообщение. В следующем фрагменте кода приведен пример того, как это сделать для окна фрейма класс с именем `CMyRichEditView`:

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

В рамках вашей `OnFindReplace` функции, интерпретировать намерения пользователя с помощью [CFindReplaceDialog::FindNext](#findnext) и [CFindReplaceDialog::IsTerminating](#isterminating) методов и вы создаете код для операций поиска и замены.

### <a name="example"></a>Пример

  См. в примере [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).

##  <a name="findnext"></a>  CFindReplaceDialog::FindNext

Эта функция вызывается из функции обратного вызова для определения, является ли пользователь хочет найти следующее вхождение строки поиска.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь хочет найти следующее вхождение строки поиска; в противном случае 0.

##  <a name="getfindstring"></a>  CFindReplaceDialog::GetFindString

Эта функция вызывается из функции обратного вызова для получения строки по умолчанию для поиска.

```
CString GetFindString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Искомая строка по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getnotifier"></a>  CFindReplaceDialog::GetNotifier

Вызывайте эту функцию для получения указателя на текущий поиск и замена диалоговом окне.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*lParam*<br/>
*Lparam* значение, передаваемое в фрейме окна `OnFindReplace` функция-член.

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущее окно.

### <a name="remarks"></a>Примечания

Он должен использоваться внутри функции обратного вызова для доступа к текущей диалоговое окно, вызовите ее члена функции и доступа `m_fr` структуры.

### <a name="example"></a>Пример

См. в разделе [CFindReplaceDialog::Create](#create) пример того, как зарегистрировать обработчик OnFindReplace для получения уведомлений в диалоговом окне «Поиск и замена».

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getreplacestring"></a>  CFindReplaceDialog::GetReplaceString

Вызывайте эту функцию для получения текущей строки замены.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка по умолчанию, которой заменяется найденный строк.

### <a name="example"></a>Пример

  См. в примере [CFindReplaceDialog::GetFindString](#getfindstring).

##  <a name="isterminating"></a>  CFindReplaceDialog::IsTerminating

Вызывайте эту функцию в функции обратного вызова для определения, решила ли пользователь завершить диалоговое окно.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь решил завершить диалоговое окно. в противном случае 0.

### <a name="remarks"></a>Примечания

Если эта функция возвращает ненулевое значение, необходимо вызвать `DestroyWindow` функцию-член текущего диалогового окна и задать любой переменной указателя поле диалоговое окно значение NULL. При необходимости можно также хранить последний введенный текст поиска и замены и использовать его для инициализации Далее диалогового окно поиска и замены.

### <a name="example"></a>Пример

  См. в примере [CFindReplaceDialog::GetFindString](#getfindstring).

##  <a name="m_fr"></a>  CFindReplaceDialog::m_fr

Используется для настройки `CFindReplaceDialog` объекта.

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>Примечания

`m_fr` — это структура типа [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea). Его члены хранить характеристики объекта диалогового окна. После построения `CFindReplaceDialog` объекта, можно использовать `m_fr` для изменения различных значений в диалоговом окне.

Дополнительные сведения об этой структуре см. в разделе `FINDREPLACE` структуры в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).

##  <a name="matchcase"></a>  CFindReplaceDialog::MatchCase

Вызывайте эту функцию, чтобы определить, требуется ли пользователю должны точности совпадать регистр в строке поиска.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь хочет найти вхождения строки поиска, которые точно соответствовать регистру строка поиска; в противном случае 0.

##  <a name="matchwholeword"></a>  CFindReplaceDialog::MatchWholeWord

Вызывайте эту функцию, чтобы определить, требуется ли пользователю поиск только целых слов.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь хочет сопоставление только целых слов в строке поиска; в противном случае 0.

##  <a name="replaceall"></a>  CFindReplaceDialog::ReplaceAll

Вызывайте эту функцию, чтобы определить, требуется ли пользователю все вхождения строки замены.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь запросил что заменить все строки, соответствующие замены строки; в противном случае 0.

##  <a name="replacecurrent"></a>  CFindReplaceDialog::ReplaceCurrent

Вызывайте эту функцию, чтобы определить, требуется ли пользователю текущего слова, заменяемого.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь запросил, что в настоящее время выбранной строки заменяется замены строки; в противном случае 0.

##  <a name="searchdown"></a>  CFindReplaceDialog::SearchDown

Вызывайте эту функцию, чтобы определить, требуется ли пользователю поиска, чтобы перейти вниз.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь хочет условия поиска для продолжения работы с направлением вниз; 0, если пользователь хочет поиска, чтобы перейти вверх.

## <a name="see-also"></a>См. также

[Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
