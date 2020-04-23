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
ms.openlocfilehash: a8053ab33a2b49eb2c447cdaa1cb2b9e356bc696
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754924"
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
|Имя|Описание|
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Формирует объект `CKeyboardManager`.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CKeyboardManager::CleanUp](#cleanup)|Очищает ключевые таблицы ярлыка.|
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Извлекает ключ ярлыка по умолчанию для указанной команды и окна.|
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Определяет, обрабатывается ли ключ таблицей акселератора.|
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Указывает, можно ли распечатать символ.|
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Указывает, отображаются ли меню все клавиши ярлыка для команды или только ключ ярлыка по умолчанию.|
|[CKeyboardManager::LoadState](#loadstate)|Загружает ключевые таблицы ярлыка из реестра Windows.|
|[CKeyboardManager::ResetAll](#resetall)|Перезагружает ключевые таблицы ярлыка из ресурса приложения.|
|[CKeyboardManager::SaveState](#savestate)|Сохраняет ключевые таблицы ярлыка в реестре Windows.|
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Определяет, отображает ли фреймворк все клавиши ярлыка для всех команд, или один ключ ярлыка для каждой команды. Этот метод не влияет на команды, которые имеют только один связанный ключ ярлыка.|
|[Ckeyboardmanager::Translatechartoupper](#translatechartoupper)|Преобразует символ в его верхний регистр.|
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Обновления таблицы ключей ярлыка с новой таблицей ключей ярлыка.|

## <a name="remarks"></a>Remarks

Члены этого класса позволяют сохранить и загрузить ключевые таблицы для поиска ключей в реестр Windows, использовать шаблон для обновления ключевых таблиц короткого среза и найти ключ ярлыка по умолчанию для команды в окне рамы. Кроме того, `CKeyboardManager` объект позволяет управлять тем, как клавиши ярлыка отображаются пользователю.

Объект не должен `CKeyboardManager` создаваться вручную. Он будет создан автоматически в рамках вашего приложения. Тем не менее, вы должны позвонить [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) во время процесса инициализации приложения. Чтобы получить указатель на клавиатуру менеджера для вашего приложения, позвоните [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).

## <a name="example"></a>Пример

В следующем примере показано, как получить `CKeyboardManager` указатель `CWinAppEx` объекта из класса и как отобрачь все клавиши ярлыка, связанные с командами меню. Этот фрагмент кода является частью [образца пользовательских страниц.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxkeyboardmanager.h

## <a name="ckeyboardmanagerckeyboardmanager"></a><a name="ckeyboardmanager"></a>CKeyboardManager::CKeyboardManager

Формирует объект `CKeyboardManager`.

```
CKeyboardManager();
```

### <a name="remarks"></a>Remarks

В большинстве случаев, вам `CKeyboardManager` не придется создавать непосредственно. По умолчанию фреймворк создает один для вас. Чтобы получить указатель `CKeyboardManager`на, позвоните [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Если вы создаете его вручную, вы должны инициализировать его с методом [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).

## <a name="ckeyboardmanagercleanup"></a><a name="cleanup"></a>CKeyboardManager::CleanUp

Освобождает ресурсы `CKeyboardManager` и очищает все ключевые отображения ярлыка.

```
static void CleanUp();
```

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о клавишах ярлыка, см [Клавиатура и мышь настройки](../../mfc/keyboard-and-mouse-customization.md).

Вам не нужно вызывать эту функцию, когда приложение выходит из-за того, что платформа автоматически вызывает ее во время выхода приложения.

## <a name="ckeyboardmanagerfinddefaultaccelerator"></a><a name="finddefaultaccelerator"></a>CKeyboardManager::FindDefaultAccelerator

Извлекает ключ ярлыка по умолчанию для указанной команды и окна.

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды.

*Ул*<br/>
[out] Ссылка на объект `CString`.

*pWndFrame*<br/>
(в) Указатель на окно рамы.

*bIsDefaultFrame*<br/>
(в) Определяет, является ли окно кадра окном кадра по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если ярлык найден; в противном случае 0.

### <a name="remarks"></a>Remarks

Этот метод просматривает команду, указанную *uiCmd,* и получает ключ ярлыка по умолчанию. Затем метод берет строку, связанную с этим ключом ярлыка, и записывает значение параметра *str.*

## <a name="ckeyboardmanageriskeyhandled"></a><a name="iskeyhandled"></a>CKeyboardManager::IsKeyHandled

Определяет, обрабатывается ли указанный ключ [классом CKeyboardManager.](../../mfc/reference/ckeyboardmanager-class.md)

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
|Параметр|Описание|
|*nKey*|(в) Ключ для проверки.|
|*fВирт*|(в) Определяет поведение ключа ярлыка. Список возможных значений [можно](/windows/win32/api/winuser/ns-winuser-accel)узнать.|
|*pWndFrame*|(в) Окно рамы. Этот метод определяет, обрабатывается ли ключ ярлыка в этом кадре.|
|*bIsDefaultFrame*|(в) Параметр Boolean, указывающий, является ли *pWndFrame* окном кадра по умолчанию.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ключ ярлык обрабатывается. FALSE, если ключ не обработан или если *pWndFrame* является NULL.

### <a name="remarks"></a>Remarks

Параметры ввода должны соответствовать записи в таблице ускорителя как для *nKey,* так и *для fVirt,* чтобы определить, обрабатывается ли ключ кратки в *pWndFrame.*

## <a name="ckeyboardmanageriskeyprintable"></a><a name="iskeyprintable"></a>CKeyboardManager::IsKeyPrintable

Указывает, можно ли распечатать символ.

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*Nchar*|(в) Символ, который проверяет этот метод.|

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если символ печатается, ноль, если это не так.

### <a name="remarks"></a>Remarks

Этот метод не удается, если вызов [GetKeyboardState](/windows/win32/api/winuser/nf-winuser-getkeyboardstate) не удается.

## <a name="ckeyboardmanagerisshowallaccelerators"></a><a name="isshowallaccelerators"></a>CKeyboardManager::IsShowAllAccelerators

Указывает, отображаются ли меню все клавиши ярлыка, связанные с командами меню, или только клавиши ярлыка по умолчанию.

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если приложение перечисляет все клавиши ярлыка для команд меню; 0, если приложение отображает только клавиши ярлыка по умолчанию.

### <a name="remarks"></a>Remarks

Приложение перечисляет клавиши ярлыка для команд меню в панели меню. Используйте функцию [CKeyboardManager::ShowAllAccelerators,](#showallaccelerators) чтобы контролировать, перечисляет ли приложение все клавиши ярлыка или просто клавиши ярлыка по умолчанию.

## <a name="ckeyboardmanagerloadstate"></a><a name="loadstate"></a>CKeyboardManager::LoadState

Загружает ключевые таблицы ярлыка из реестра Windows.

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Путь реестра, `CKeyboardManager` по которому сохраняются данные.

*pDefaultFrame*<br/>
(в) Указатель на окно кадра для использования в качестве окна по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если состояние было загружено успешно или 0 в противном случае.

### <a name="remarks"></a>Remarks

Если параметр *lpszProfileName* является NULL, этот метод `CKeyboardManager` проверяет местоположение реестра по умолчанию для данных. Местоположение реестра по умолчанию определяется [классом CWinAppEx.](../../mfc/reference/cwinappex-class.md) Данные должны быть ранее написаны методом [CKeyboardManager::SaveState](#savestate).

Если вы не укажете окно по умолчанию, будет использовано окно основной кадра приложения.

## <a name="ckeyboardmanagerresetall"></a><a name="resetall"></a>CKeyboardManager::ResetAll

Перезагружает ключевые таблицы ярлыка из ресурса приложения.

```cpp
void ResetAll();
```

### <a name="remarks"></a>Remarks

Эта функция очищает ярлыки, `CKeyboardManager` хранящиеся в экземпляре. Затем он перезагрузит состояние диспетчера клавиатуры с ресурса приложения.

## <a name="ckeyboardmanagersavestate"></a><a name="savestate"></a>CKeyboardManager::SaveState

Сохраняет ключевые таблицы ярлыка в реестре Windows.

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Путь реестра для `CKeyboardManager` спасения государства.

*pDefaultFrame*<br/>
(в) Указатель на окно кадра, которое становится окном по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если состояние менеджера клавиатуры было сохранено успешно, или 0 в противном случае.

### <a name="remarks"></a>Remarks

Если параметр *lpszProfileName* является NULL, `CKeyboardManager` этот метод записывает состояние в место по умолчанию, указанное [классом CWinAppEx.](../../mfc/reference/cwinappex-class.md) Если вы укажете местоположение, вы можете загрузить данные позже с помощью метода [CKeyboardManager:LoadState.](#loadstate)

Если вы не указали окно по умолчанию, окно основной кадра будет использоваться в качестве окна по умолчанию.

## <a name="ckeyboardmanagershowallaccelerators"></a><a name="showallaccelerators"></a>CKeyboardManager::ShowAllAccelerators

Отображается все клавиши ярлыка, связанные с командами меню.

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>Параметры

*bShowAll*<br/>
(в) Если true, все клавиши ярлыка будут отображаться. Если FALSE, будет отображаться только первый ключ ярлыка.

*lpszDelimiter*<br/>
(в) Строка для вставки между клавишами ярлыка. Этот делимитер не имеет никакого эффекта, если отображается только один ключ ярлыка.

### <a name="remarks"></a>Remarks

По умолчанию, если у команды есть более одного ключа быстрого ключа, связанного с ней, будет отображаться только первый ключ ярлыка. Эта функция позволяет перечислить все клавиши ярлыка, связанные со всеми командами.

Ключи ярлыка будут перечислены рядом с командой в панели меню. Если все клавиши ярлыка отображаются, строка, предоставляемая *lpszDelimiter,* будет отделять отдельные клавиши ярлыка.

## <a name="ckeyboardmanagertranslatechartoupper"></a><a name="translatechartoupper"></a>Ckeyboardmanager::Translatechartoupper

Преобразует символ в его верхний регистр.

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>Параметры

*Nchar*<br/>
(в) Персонаж для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Символ, который является верхним регистром параметра ввода.

## <a name="ckeyboardmanagerupdateacceltable"></a><a name="updateacceltable"></a>CKeyboardManager::UpdateAccelTable

Обновления таблицы ключей ярлыка с новой таблицей ключей ярлыка.

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
(в) Указатель на шаблон документа.

*lpAccel*<br/>
(в) Указатель на новый ключ ярлыка.

*Nsize*<br/>
(в) Размер новой таблицы ярлыков.

*pDefaultFrame*<br/>
(в) Указатель на окно кадра по умолчанию.

*hAccelNew*<br/>
(в) Ручка к новой таблице ярлыка.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод успешен; в противном случае 0.

### <a name="remarks"></a>Remarks

Используйте эту функцию, чтобы заменить существующую таблицу ярлыков новыми ключами ярлыка для нескольких объектов окна кадра. Функция получает шаблон документа в качестве параметра для получения доступа ко всем объектам окна кадра, подключенным к заданного шаблону документа.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)
