---
title: Класс CKeyboardManager
ms.date: 11/04/2016
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
helpviewer_keywords:
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
ms.openlocfilehash: d144731d05e861f4b462c4d58022b5155fdeb79b
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694274"
---
# <a name="ckeyboardmanager-class"></a>Класс CKeyboardManager

Управляет таблицами клавиш быстрого доступа для окна главного и дочерних фреймов.

## <a name="syntax"></a>Синтаксис

```
class CKeyboardManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание:|
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Создает объект `CKeyboardManager`.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание:|
|[CKeyboardManager::CleanUp](#cleanup)|Очистка таблиц ключа ярлыка.|
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Получает сочетание клавиш по умолчанию для указанной команды и окна.|
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Определяет, обрабатывается ли ключ в таблице сочетаний клавиш.|
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Указывает, является ли символ печати.|
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Указывает, является ли меню отображаются все сочетания клавиш для команды или сочетание клавиш по умолчанию.|
|[CKeyboardManager::LoadState](#loadstate)|Загружает таблицы сочетания ключа из реестра Windows.|
|[CKeyboardManager::ResetAll](#resetall)|Перезагружает ярлык ключей таблиц из ресурсов приложения.|
|[CKeyboardManager::SaveState](#savestate)|Сохраняет сочетание таблиц ключа реестра Windows.|
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Указывает, отображаются ли платформа все сочетания клавиш для всех команд, или одному сочетанию клавиш для каждой команды. Этот метод не влияет на команды, которые имеют только одно сочетанием клавиш.|
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Преобразует символ в его верхний регистр.|
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Заносит в таблицу ключа ярлык таблицу ключа ярлыка.|

## <a name="remarks"></a>Примечания

Члены этого класса позволяют сохранить и загрузить ярлык таблиц ключа в реестре Windows, использовать шаблон для обновления таблиц ключа ярлык и найти сочетание клавиш по умолчанию для команды в окне фрейма. Кроме того `CKeyboardManager` объекта позволяет управлять способом отображения сочетания клавиш для пользователя.

Не следует создавать `CKeyboardManager` объект вручную. Он будет создаваться автоматически платформой приложения. Тем не менее, следует вызывать [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) во время инициализации приложения. Чтобы получить указатель на диспетчер клавиатуры для вашего приложения, вызовите [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).

## <a name="example"></a>Пример

Следующий пример демонстрирует, как получить указатель на `CKeyboardManager` объекта из `CWinAppEx` , а также показать сочетания клавиш, связанные с командами меню. Этот фрагмент кода является частью [пример пользовательские страницы](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxkeyboardmanager.h

##  <a name="ckeyboardmanager"></a>  CKeyboardManager::CKeyboardManager

Создает объект `CKeyboardManager`.

```
CKeyboardManager();
```

### <a name="remarks"></a>Примечания

В большинстве случаев не нужно создавать `CKeyboardManager` напрямую. По умолчанию платформа создает ее автоматически. Чтобы получить указатель на `CKeyboardManager`, вызовите [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Если можно создать вручную, необходимо инициализировать его с помощью метода [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).

##  <a name="cleanup"></a>  CKeyboardManager::CleanUp

Освобождает `CKeyboardManager` ресурсы и очищает все сопоставлений сочетаний клавиш.

```
static void CleanUp();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения о сочетаниях клавиш см. в разделе [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md).

У вас нет для вызова этой функции в том случае, когда приложение завершает работу, так как вызывается платформой его автоматически во время выхода приложения.

##  <a name="finddefaultaccelerator"></a>  CKeyboardManager::FindDefaultAccelerator

Получает сочетание клавиш по умолчанию для указанной команды и окна.

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
[in] Идентификатор команды.

*str*<br/>
[out] Ссылку на `CString` объекта.

*pWndFrame*<br/>
[in] Указатель на фрейм окна.

*bIsDefaultFrame*<br/>
[in] Указывает, является ли окно фрейма окна по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если найден ярлык; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод ищет команда, заданная *uiCmd* и получает сочетание клавиш по умолчанию. Затем этот метод принимает строку, связанную с этого сочетания клавиш и записывает значение *str* параметра.

##  <a name="iskeyhandled"></a>  CKeyboardManager::IsKeyHandled

Определяет, обрабатывается ли указанный ключ [класс CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md).

```
static BOOL __stdcall IsKeyHandled(
    WORD nKey,
    BYTE fVirt,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание:|
|*nKey*|[in] Проверяемая клавиша.|
|*fVirt*|[in] Задает поведение сочетания клавиш. Список возможных значений см. в разделе [УСКОРЕНИЕ структуры](/windows/desktop/api/winuser/ns-winuser-tagaccel).|
|*pWndFrame*|[in] Окно фрейма. Этот метод определяет, обрабатывается ли сочетания клавиш в данном фрейме.|
|*bIsDefaultFrame*|[in] Логический параметр, указывает ли *pWndFrame* – окно рамки по умолчанию.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если клавиша обрабатывается. Значение FALSE, если ключ не обрабатывается или *pWndFrame* имеет значение NULL.

### <a name="remarks"></a>Примечания

Входные параметры должна совпадать с записью в таблице сочетаний клавиш как для *nKey* и *fVirt* для определения того, обрабатывается ли сочетания клавиш в *pWndFrame*.

##  <a name="iskeyprintable"></a>  CKeyboardManager::IsKeyPrintable

Указывает, является ли символ печати.

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание:|
|*NChar*|[in] Символ, этот метод проверяет.|

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение Если печатный символ, нуль, если это не так.

### <a name="remarks"></a>Примечания

Этот метод завершается ошибкой, если в вызове [GetKeyboardState](/windows/desktop/api/winuser/nf-winuser-getkeyboardstate) завершается ошибкой.

##  <a name="isshowallaccelerators"></a>  CKeyboardManager::IsShowAllAccelerators

Указывает, является ли меню отображаются все сочетания клавиш, связанные с помощью команд меню или сочетания клавиш по умолчанию.

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если приложение перечисляет все сочетания клавиш для команд меню; 0, если приложение отображает только сочетания клавиш по умолчанию.

### <a name="remarks"></a>Примечания

Приложение перечислены сочетания клавиш для команды меню в строке меню. Используйте функцию [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) для управления того, приложение перечисляет все сочетания клавиш или просто сочетания клавиш по умолчанию.

##  <a name="loadstate"></a>  CKeyboardManager::LoadState

Загружает таблицы сочетания ключа из реестра Windows.

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Путь в реестре где `CKeyboardManager` данные сохраняются.

*pDefaultFrame*<br/>
[in] Указатель на фрейм окна для использования в качестве окна по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если состояние успешно загружен или 0 в противном случае.

### <a name="remarks"></a>Примечания

Если *lpszProfileName* параметра равно NULL, этот метод проверяет расположение реестра по умолчанию для `CKeyboardManager` данных. Расположение реестра по умолчанию задается [класс CWinAppEx](../../mfc/reference/cwinappex-class.md). Данные должны записываться ранее с помощью метода [CKeyboardManager::SaveState](#savestate).

Если вы не укажете окна по умолчанию, будет использоваться фрейма главного окна приложения.

##  <a name="resetall"></a>  CKeyboardManager::ResetAll

Перезагружает ярлык ключей таблиц из ресурсов приложения.

```
void ResetAll();
```

### <a name="remarks"></a>Примечания

Эта функция удаляет ярлыки, хранящиеся в `CKeyboardManager` экземпляра. Состояние диспетчера клавиатуры из ресурсов приложения затем перезагружается.

##  <a name="savestate"></a>  CKeyboardManager::SaveState

Сохраняет сочетание таблиц ключа реестра Windows.

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Путь в реестре для сохранения `CKeyboardManager` состояния.

*pDefaultFrame*<br/>
[in] Указатель на фрейм окна, который становится окна по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если состояние клавиатуры manager сохранен успешно, или 0 в противном случае.

### <a name="remarks"></a>Примечания

Если *lpszProfileName* параметр равен NULL, этот метод запишет `CKeyboardManager` состояния в расположение по умолчанию, определяемое [класс CWinAppEx](../../mfc/reference/cwinappex-class.md). Если указано расположение, можно загрузить данные, более поздней версии с помощью метода [CKeyboardManager::LoadState](#loadstate).

Если вы не укажете окна по умолчанию, как окна по умолчанию будет использоваться фрейма главного окна.

##  <a name="showallaccelerators"></a>  CKeyboardManager::ShowAllAccelerators

Показывает все сочетания клавиш, связанные с командами меню.

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>Параметры

*bShowAll*<br/>
[in] Если значение равно TRUE, будет отображаться все сочетания клавиш. Если значение равно FALSE, отображается только первый сочетание клавиш.

*lpszDelimiter*<br/>
[in] Строка для вставки между сочетания клавиш. Этот разделитель не оказывает влияния если только одно сочетание клавиш или клавиша отображается.

### <a name="remarks"></a>Примечания

По умолчанию Если команда имеет более одного сочетание клавиш, связанное с ним, только первый сочетание клавиш отображается. Эта функция позволяет перечислять все сочетания клавиш, связанные с всех команд.

Сочетания клавиш отображается рядом с командой в строке меню. Если отображаются все сочетания клавиш, строки, предоставляемые *lpszDelimiter* разделит отдельных сочетания клавиш.

##  <a name="translatechartoupper"></a>  CKeyboardManager::TranslateCharToUpper

Преобразует символ в его верхний регистр.

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>Параметры

*NChar*<br/>
[in] Знак для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Символ, — верхний регистр во входном параметре.

##  <a name="updateacceltable"></a>  CKeyboardManager::UpdateAccelTable

Заносит в таблицу ключа ярлык таблицу ключа ярлыка.

```
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    LPACCEL lpAccel,
    int nSize,
    CFrameWnd* pDefaultFrame = NULL);

BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    HACCEL hAccelNew,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Параметры

*pTemplate*<br/>
[in] Указатель на шаблон документа.

*lpAccel*<br/>
[in] Указатель на новое сочетание клавиш.

*nSize*<br/>
[in] Размер новой таблицы ярлыка.

*pDefaultFrame*<br/>
[in] Указатель на рамку окна по умолчанию.

*hAccelNew*<br/>
[in] Дескриптор в новую таблицу ярлыка.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Эту функцию можно используйте для замены существующей таблицы ярлык новых сочетаний клавиш для нескольких объектов окна фрейма. Функция получает шаблон документа в качестве параметра для получения доступа ко всем объектам окна фрейма, подключенных к данному документу шаблона.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)

