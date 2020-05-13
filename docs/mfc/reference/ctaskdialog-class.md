---
title: CTaskDialog Class
ms.date: 11/19/2018
f1_keywords:
- CTaskDialog
- AFXTASKDIALOG/CTaskDialog
- AFXTASKDIALOG/CTaskDialog::CTaskDialog
- AFXTASKDIALOG/CTaskDialog::AddCommandControl
- AFXTASKDIALOG/CTaskDialog::AddRadioButton
- AFXTASKDIALOG/CTaskDialog::ClickCommandControl
- AFXTASKDIALOG/CTaskDialog::ClickRadioButton
- AFXTASKDIALOG/CTaskDialog::DoModal
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonCount
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonFlag
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonId
- AFXTASKDIALOG/CTaskDialog::GetOptions
- AFXTASKDIALOG/CTaskDialog::GetSelectedCommandControlID
- AFXTASKDIALOG/CTaskDialog::GetSelectedRadioButtonID
- AFXTASKDIALOG/CTaskDialog::GetVerificationCheckboxState
- AFXTASKDIALOG/CTaskDialog::IsCommandControlEnabled
- AFXTASKDIALOG/CTaskDialog::IsRadioButtonEnabled
- AFXTASKDIALOG/CTaskDialog::IsSupported
- AFXTASKDIALOG/CTaskDialog::LoadCommandControls
- AFXTASKDIALOG/CTaskDialog::LoadRadioButtons
- AFXTASKDIALOG/CTaskDialog::NavigateTo
- AFXTASKDIALOG/CTaskDialog::OnCommandControlClick
- AFXTASKDIALOG/CTaskDialog::OnCreate
- AFXTASKDIALOG/CTaskDialog::OnDestroy
- AFXTASKDIALOG/CTaskDialog::OnExpandButtonClick
- AFXTASKDIALOG/CTaskDialog::OnHelp
- AFXTASKDIALOG/CTaskDialog::OnHyperlinkClick
- AFXTASKDIALOG/CTaskDialog::OnInit
- AFXTASKDIALOG/CTaskDialog::OnNavigatePage
- AFXTASKDIALOG/CTaskDialog::OnRadioButtonClick
- AFXTASKDIALOG/CTaskDialog::OnTimer
- AFXTASKDIALOG/CTaskDialog::OnVerificationCheckboxClick
- AFXTASKDIALOG/CTaskDialog::RemoveAllCommandControls
- AFXTASKDIALOG/CTaskDialog::RemoveAllRadioButtons
- AFXTASKDIALOG/CTaskDialog::SetCommandControlOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtons
- AFXTASKDIALOG/CTaskDialog::SetContent
- AFXTASKDIALOG/CTaskDialog::SetDefaultCommandControl
- AFXTASKDIALOG/CTaskDialog::SetDefaultRadioButton
- AFXTASKDIALOG/CTaskDialog::SetDialogWidth
- AFXTASKDIALOG/CTaskDialog::SetExpansionArea
- AFXTASKDIALOG/CTaskDialog::SetFooterIcon
- AFXTASKDIALOG/CTaskDialog::SetFooterText
- AFXTASKDIALOG/CTaskDialog::SetMainIcon
- AFXTASKDIALOG/CTaskDialog::SetMainInstruction
- AFXTASKDIALOG/CTaskDialog::SetOptions
- AFXTASKDIALOG/CTaskDialog::SetProgressBarMarquee
- AFXTASKDIALOG/CTaskDialog::SetProgressBarPosition
- AFXTASKDIALOG/CTaskDialog::SetProgressBarRange
- AFXTASKDIALOG/CTaskDialog::SetProgressBarState
- AFXTASKDIALOG/CTaskDialog::SetRadioButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckbox
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckboxText
- AFXTASKDIALOG/CTaskDialog::SetWindowTitle
- AFXTASKDIALOG/CTaskDialog::ShowDialog
- AFXTASKDIALOG/CTaskDialog::TaskDialogCallback
helpviewer_keywords:
- CTaskDialog [MFC], CTaskDialog
- CTaskDialog [MFC], AddCommandControl
- CTaskDialog [MFC], AddRadioButton
- CTaskDialog [MFC], ClickCommandControl
- CTaskDialog [MFC], ClickRadioButton
- CTaskDialog [MFC], DoModal
- CTaskDialog [MFC], GetCommonButtonCount
- CTaskDialog [MFC], GetCommonButtonFlag
- CTaskDialog [MFC], GetCommonButtonId
- CTaskDialog [MFC], GetOptions
- CTaskDialog [MFC], GetSelectedCommandControlID
- CTaskDialog [MFC], GetSelectedRadioButtonID
- CTaskDialog [MFC], GetVerificationCheckboxState
- CTaskDialog [MFC], IsCommandControlEnabled
- CTaskDialog [MFC], IsRadioButtonEnabled
- CTaskDialog [MFC], IsSupported
- CTaskDialog [MFC], LoadCommandControls
- CTaskDialog [MFC], LoadRadioButtons
- CTaskDialog [MFC], NavigateTo
- CTaskDialog [MFC], OnCommandControlClick
- CTaskDialog [MFC], OnCreate
- CTaskDialog [MFC], OnDestroy
- CTaskDialog [MFC], OnExpandButtonClick
- CTaskDialog [MFC], OnHelp
- CTaskDialog [MFC], OnHyperlinkClick
- CTaskDialog [MFC], OnInit
- CTaskDialog [MFC], OnNavigatePage
- CTaskDialog [MFC], OnRadioButtonClick
- CTaskDialog [MFC], OnTimer
- CTaskDialog [MFC], OnVerificationCheckboxClick
- CTaskDialog [MFC], RemoveAllCommandControls
- CTaskDialog [MFC], RemoveAllRadioButtons
- CTaskDialog [MFC], SetCommandControlOptions
- CTaskDialog [MFC], SetCommonButtonOptions
- CTaskDialog [MFC], SetCommonButtons
- CTaskDialog [MFC], SetContent
- CTaskDialog [MFC], SetDefaultCommandControl
- CTaskDialog [MFC], SetDefaultRadioButton
- CTaskDialog [MFC], SetDialogWidth
- CTaskDialog [MFC], SetExpansionArea
- CTaskDialog [MFC], SetFooterIcon
- CTaskDialog [MFC], SetFooterText
- CTaskDialog [MFC], SetMainIcon
- CTaskDialog [MFC], SetMainInstruction
- CTaskDialog [MFC], SetOptions
- CTaskDialog [MFC], SetProgressBarMarquee
- CTaskDialog [MFC], SetProgressBarPosition
- CTaskDialog [MFC], SetProgressBarRange
- CTaskDialog [MFC], SetProgressBarState
- CTaskDialog [MFC], SetRadioButtonOptions
- CTaskDialog [MFC], SetVerificationCheckbox
- CTaskDialog [MFC], SetVerificationCheckboxText
- CTaskDialog [MFC], SetWindowTitle
- CTaskDialog [MFC], ShowDialog
- CTaskDialog [MFC], TaskDialogCallback
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
ms.openlocfilehash: 79f52d275d360cf8447b8977b8196ea5f95eacd8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752282"
---
# <a name="ctaskdialog-class"></a>CTaskDialog Class

Всплывающее диалоговое окно, которое функционирует как окно сообщения, но может отображать дополнительные сведения для пользователя. `CTaskDialog` также включает функции для получения сведений от пользователя.

## <a name="syntax"></a>Синтаксис

```
class CTaskDialog : public CObject
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|||
|-|-|
|[CTaskDialog::CTaskDialog](#ctaskdialog)|Формирует объект `CTaskDialog`.|

### <a name="methods"></a>Методы

|||
|-|-|
|[CTaskDialog:AddCommandControl](#addcommandcontrol)|Добавляет управление кнопкой `CTaskDialog`команды в управление .|
|[CTaskDialog::AddRadioButton](#addradiobutton)|Добавляет кнопку радио `CTaskDialog`в .|
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Нажимает кнопку управления командой или общую кнопку программно.|
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Нажимает кнопку радио программно.|
|[CTaskDialog::DoModal](#domodal)|Отображает `CTaskDialog`.|
|[CTaskDialog::GetCommonButton](#getcommonbuttoncount)|Извлекает количество доступных кнопок.|
|[CTaskDialog:GetCommonButtonFlag](#getcommonbuttonflag)|Преобразует стандартную кнопку Windows в общий `CTaskDialog` тип кнопки, связанный с классом.|
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|Преобразует один из распространенных типов `CTaskDialog` кнопок, связанных с классом, в стандартную кнопку Windows.|
|[CTaskDialog::GetOptions](#getoptions)|Возвращает флаги опции для этого. `CTaskDialog`|
|[CTaskDialog:GetSelectedCommandControlID](#getselectedcommandcontrolid)|Возвращает выбранное управление кнопкой команды.|
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Возвращает выбранную кнопку радио.|
|[CTaskDialog:GetVerificationCheckboxState](#getverificationcheckboxstate)|Извлекает состояние контрольного ящика проверки.|
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Определяет, включено ли управление кнопкой команды или общая кнопка.|
|[CTaskDialog::IsRadioButton](#isradiobuttonenabled)|Определяет, включена ли радиокнопка.|
|[CTaskDialog::Поддерживается](#issupported)|Определяет, поддерживает ли компьютер, работающий `CTaskDialog`под управлением приложения, .|
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Добавляет элементы управления кнопками команд, используя данные из строки таблицы.|
|[CTaskDialog:LoadRadioButtons](#loadradiobuttons)|Добавляет радиокнопки с помощью данных из строки таблицы.|
|[CTaskDialog::NavigateTo](#navigateto)|Переносит фокус `CTaskDialog`на другой .|
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Рамочная система вызывает этот метод, когда пользователь нажимает на управление кнопкой команды.|
|[CTaskDialog::OnCreate](#oncreate)|Платформа вызывает этот метод после `CTaskDialog`того, как он создает .|
|[CTaskDialog::Уничтожение](#ondestroy)|Рамки вызывает этот метод непосредственно перед `CTaskDialog`тем, как он уничтожает .|
|[CTaskDialog::OnExpandbutton](#onexpandbuttonclick)|Рамочная система вызывает этот метод, когда пользователь нажимает на кнопку расширения.|
|[CTaskDialog::OnHelp](#onhelp)|Платформа вызывает этот метод, когда пользователь запрашивает помощь.|
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|Рамочная система вызывает этот метод, когда пользователь нажимает на гиперссылку.|
|[CTaskDialog:It](#oninit)|Фрейм вызывает этот `CTaskDialog` метод, когда инициализирован.|
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Рамочная система вызывает этот метод, когда пользователь `CTaskDialog`перемещает фокус в отношении элементов управления на .|
|[CTaskDialog::OnRadioButton](#onradiobuttonclick)|Рамочная система вызывает этот метод, когда пользователь выбирает управление радиокнопкой.|
|[CTaskDialog:OnTimer](#ontimer)|Фрейм вызывает этот метод по истечении срока действия таймера.|
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|Рамочная система вызывает этот метод, когда пользователь нажимает на флажок проверки.|
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Удаляет все элементы управления `CTaskDialog`командой из .|
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Удаляет все радиокнопки с `CTaskDialog`.|
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Обновляет управление кнопкой `CTaskDialog`команды на .|
|[CTaskDialog::SetCommonButton](#setcommonbuttonoptions)|Обновляет подмножество общих кнопок, которые должны быть включены и требуют высоты UAC.|
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|Добавляет общие кнопки `CTaskDialog`в .|
|[CTaskDialog::SetContent](#setcontent)|Обновляет содержание `CTaskDialog`.|
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Определяет управление кнопкой команды по умолчанию.|
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Определяет кнопку радио по умолчанию.|
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|Регулирует ширину `CTaskDialog`.|
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|Обновляет область расширения `CTaskDialog`.|
|[CTaskDialog::SetFooterIcon](#setfootericon)|Обновления значок колонтитулдлядля. `CTaskDialog`|
|[CTaskDialog::SetFooterText](#setfootertext)|Обновления текста на колонтитул `CTaskDialog`.|
|[CTaskDialog::SetMainIcon](#setmainicon)|Обновления главной иконы `CTaskDialog`.|
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Обновления основной инструкции `CTaskDialog`.|
|[CTaskDialog::SetOptions](#setoptions)|Настраивает варианты `CTaskDialog`для .|
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|Настраивает шатер-бар `CTaskDialog` для и добавляет его в диалоговую будку.|
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|Регулирует положение панели прогресса.|
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|Регулирует диапазон панели прогресса.|
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|Устанавливает состояние панели прогресса и отображает ее `CTaskDialog`на .|
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Включает или отсваивает кнопку радио.|
|[CTaskDialog:SetVerificationCheckbox](#setverificationcheckbox)|Устанавливает проверенное состояние контрольного ящика проверки.|
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Устанавливает текст на правой стороне контрольного ящика проверки.|
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Устанавливает название `CTaskDialog`.|
|[CTaskDialog:ShowDialog](#showdialog)|Создает и отображает `CTaskDialog`.|
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Платформа называет это в ответ на различные сообщения Windows.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|`m_aButtons`|Массив управления кнопкой команды `CTaskDialog`для .|
|`m_aRadioButtons`|Массив управления радиокнопкой `CTaskDialog`для .|
|`m_bVerified`|`TRUE`указывает на проверку флажка проверки; `FALSE` указывает, что это не так.|
|`m_footerIcon`|Икона в колонтитуле `CTaskDialog`.|
|`m_hWnd`|Ручка к окну `CTaskDialog`для .|
|`m_mainIcon`|Главная икона `CTaskDialog`.|
|`m_nButtonDisabled`|Маска, которая указывает, какие из общих кнопок отключены.|
|`m_nButtonElevation`|Маска, которая указывает, какие из общих кнопок требуют высоты UAC.|
|`m_nButtonId`|Идентификатор выбранного управления кнопкой команды.|
|`m_nCommonButton`|Маска, которая указывает, какие общие кнопки отображаются на `CTaskDialog`.|
|`m_nDefaultCommandControl`|Идентификатор управления кнопкой команды, `CTaskDialog` выбранный при отображении.|
|`m_nDefaultRadioButton`|Идентификатор управления радиокнопкой, `CTaskDialog` выбранный при отображении кнопки.|
|`m_nFlags`|Маска, отопомдавшая `CTaskDialog`параметры.|
|`m_nProgressPos`|Текущая позиция панели прогресса.  Это значение должно принадлежать диапазону от `m_nProgressRangeMin` до `m_nProgressRangeMax`.|
|`m_nProgressRangeMax`|Максимальное значение для бара прогресса.|
|`m_nProgressRangeMin`|Минимальное значение для бара прогресса.|
|`m_nProgressState`|Состояние бара прогресса. Для получения дополнительной информации [см. CTaskDialog::SetProgressBarState](#setprogressbarstate).|
|`m_nRadioId`|Идентификатор выбранного управления радиокнопкой.|
|`m_nWidth`|Ширина `CTaskDialog` (в пикселях).|
|`m_strCollapse`|Строка `CTaskDialog` отображается справа от окна расширения, когда расширенная информация скрыта.|
|`m_strContent`|Содержание строки `CTaskDialog`.|
|`m_strExpand`|Строка `CTaskDialog` отображается справа от окна расширения при отображении расширенной информации.|
|`m_strFooter`|Колонтитул `CTaskDialog`.|
|`m_strInformation`|Расширенная информация `CTaskDialog`для .|
|`m_strMainInstruction`|Основная инструкция `CTaskDialog`.|
|`m_strTitle`|Заголовок `CTaskDialog`.|
|`m_strVerification`|Строка, `CTaskDialog` которая отображается справа от флажка проверки.|

## <a name="remarks"></a>Remarks

Класс `CTaskDialog` заменяет стандартное окно сообщений Windows и имеет дополнительные функциональные возможности, такие как новые элементы управления для сбора информации от пользователя. Этот класс находится в библиотеке МФЦ в Visual Studio 2010 и позже. Доступно, `CTaskDialog` начиная с Windows Vista. Более ранние версии `CTaskDialog` Windows не могут отображать объект. Используйте `CTaskDialog::IsSupported` для определения времени выполнения, может ли текущий пользователь отображать поле диалога задач. Стандартная коробка сообщений Windows по-прежнему поддерживается.

Это `CTaskDialog` доступно только при создании приложения с помощью библиотеки Unicode.

Имеет `CTaskDialog` два разных конструктора. Один конструктор позволяет указать две кнопки команды и максимум шесть регулярных элементов управления кнопками. Вы можете добавить больше кнопок команды после создания `CTaskDialog`. Второй конструктор не поддерживает никаких командных кнопок, но вы можете добавить неограниченное количество регулярных элементов управления кнопками. Для получения дополнительной информации о конструкторах, [см. CTaskDialog::CTaskDialog](#ctaskdialog).

На следующем изображении `CTaskDialog` показан пример, иллюстрирующий расположение некоторых элементов управления.

![Пример CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "Пример CTaskDialog") <br/>
Образец CTaskDialog

## <a name="requirements"></a>Требования

**Минимально необходимая операционная система:** Windows Vista

**Заголовок:** afxtaskdialog.h

## <a name="ctaskdialogaddcommandcontrol"></a><a name="addcommandcontrol"></a>CTaskDialog:AddCommandControl

Добавляет новое управление кнопкой `CTaskDialog`команды в .

```cpp
void AddCommandControl(
    int nCommandControlID,
    const CString& strCaption,
    BOOL bEnabled = TRUE,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Параметры

*nCommandControlID*<br/>
(в) Идентификационный номер командного управления.

*strCaption caption*<br/>
(в) Строка, `CTaskDialog` которую отображает пользователь. Используйте эту строку, чтобы объяснить назначение команды.

*bВСтои*<br/>
(в) Параметр Boolean, указывающий, включена ли новая кнопка или отключена.

*bRequiresВысота*<br/>
(в) Параметр Boolean, указывающий, требует ли команда высоты.

### <a name="remarks"></a>Remarks

Можно `CTaskDialog Class` отображать неограниченное количество элементов управления кнопкой команды. Однако, `CTaskDialog` если отображается любое управление кнопкой команды, он может отображать не более шести кнопок. Если `CTaskDialog` у него нет управления кнопкой команды, он может отображать неограниченное количество кнопок.

Когда пользователь выбирает управление кнопкой `CTaskDialog` команды, он закрывается. Если приложение отображает диалоговую коробку с помощью [CTaskDialog::DoModal,](#domodal) `DoModal` возвращает *nCommandControlID* выбранного управления кнопкой команды.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogaddradiobutton"></a><a name="addradiobutton"></a>CTaskDialog::AddRadioButton

Добавляет кнопку радио `CTaskDialog`в .

```cpp
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Параметры

*nРадиоБаттонID*<br/>
(в) Идентификационный номер радиокнопки.

*strCaption caption*<br/>
(в) Строка, `CTaskDialog` которую отображает рядом с кнопкой радио.

*bВСтои*<br/>
(в) Параметр Boolean, указывающий, включена ли радиокнопка.

### <a name="remarks"></a>Remarks

Кнопки радиоприемника для [класса CTaskDialog](../../mfc/reference/ctaskdialog-class.md) позволяют собирать информацию от пользователя. Используйте функцию [CTaskDialog::GetSelectedRadioButtonID,](#getselectedradiobuttonid) чтобы определить, какая радиокнопка выбрана.

Параметры `CTaskDialog` *nRadioButtonID* не требуют уникальности для каждой кнопки радио. Однако, если вы не используете отдельный идентификатор для каждой кнопки радио, вы можете столкнуться с неожиданным поведением.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogclickcommandcontrol"></a><a name="clickcommandcontrol"></a>CTaskDialog::ClickCommandControl

Нажимает кнопку управления командой или общую кнопку программно.

```
protected:
void ClickCommandControl(int nCommandControlID) const;
```

### <a name="parameters"></a>Параметры

*nCommandControlID*<br/>
(в) Идентификатор команды управления для нажатия кнопки.

### <a name="remarks"></a>Remarks

Этот метод генерирует сообщение windows TDM_CLICK_BUTTON.

## <a name="ctaskdialogclickradiobutton"></a><a name="clickradiobutton"></a>CTaskDialog::ClickRadioButton

Нажимает кнопку радио программно.

```
protected:
void ClickRadioButton(int nRadioButtonID) const;
```

### <a name="parameters"></a>Параметры

*nРадиоБаттонID*<br/>
(в) Идентификатор кнопки радио для нажатия.

### <a name="remarks"></a>Remarks

Этот метод генерирует сообщение windows TDM_CLICK_RADIO_BUTTON.

## <a name="ctaskdialogctaskdialog"></a><a name="ctaskdialog"></a>CTaskDialog::CTaskDialog

Создает экземпляр [класса CTaskDialog.](../../mfc/reference/ctaskdialog-class.md)

```
CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nCommonButtons = TDCBF_OK_BUTTON | TDCBF_CANCEL_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));

CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>Параметры

*strContent*<br/>
(в) Строка для использования для `CTaskDialog`содержания .

*strMainInstruction*<br/>
(в) Основная инструкция `CTaskDialog`.

*strTitle*<br/>
(в) Название `CTaskDialog`.

*nCommonButtons*<br/>
(в) Маска общих кнопок, `CTaskDialog`чтобы добавить в .

*nTaskDialogOptions*<br/>
(в) Набор опций для использования `CTaskDialog`для .

*strFooter*<br/>
(в) Строка для использования в качестве колонтитула.

*nIDCommandControlsFirst*<br/>
(в) Идентификатор строки первой команды.

*nIDCommandControlsLast*<br/>
(в) Идентификатор строки последней команды.

### <a name="remarks"></a>Remarks

Есть два способа, которые `CTaskDialog` можно добавить в приложение. Первый способ заключается в использовании одного `CTaskDialog` из конструкторов для создания и отображения его с помощью [CTaskDialog::DoModal](#domodal). Второй способ заключается в использовании статической функции [CTaskDialog::ShowDialog](#showdialog), которая позволяет отображать `CTaskDialog` без явного создания `CTaskDialog` объекта.

Второй конструктор создает элементы управления кнопками команд, используя данные из файла ресурсов приложения. Таблица строк в файле ресурса имеет несколько строк с соответствующими имии строки. Этот метод добавляет управление кнопкой команды для каждого действительного входа в строку таблицы между *nIDCommandControlsFirst* и *nCommandControlsLast*, включительно. Для этих элементов управления кнопкой команды строка в таблице строки является подписью управления, а идентификатор строки — идентификатором управления.

Смотрите [CTaskDialog::SetOptions](#setoptions) для списка действительных вариантов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogdomodal"></a><a name="domodal"></a>CTaskDialog::DoModal

Показывает `CTaskDialog` и делает его модальным.

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Параметры

*hРодитель*<br/>
(в) Родительское окно `CTaskDialog`для .

### <a name="return-value"></a>Возвращаемое значение

Цель, которая соответствует выбору, сделанному пользователем.

### <a name="remarks"></a>Remarks

Отображает этот экземпляр [CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Затем приложение ждет, пока пользователь закроет диалоговое окно.

Закрывается, `CTaskDialog` когда пользователь выбирает общую кнопку, управление командой `CTaskDialog`или закрывает. Значение возврата — это идентификатор, указывающий, как пользователь закрыл диалоговое окно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetcommonbuttoncount"></a><a name="getcommonbuttoncount"></a>CTaskDialog::GetCommonButton

Извлекает количество общих кнопок.

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество доступных кнопок.

### <a name="remarks"></a>Remarks

Общие кнопки по умолчанию, которые вы предоставляете [CTaskDialog::CTaskDialog](#ctaskdialog). [Класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) отображает кнопки в нижней части диалогового окна.

Перечисленный список кнопок приведен в CommCtrl.h.

## <a name="ctaskdialoggetcommonbuttonflag"></a><a name="getcommonbuttonflag"></a>CTaskDialog:GetCommonButtonFlag

Преобразует стандартную кнопку Windows в общий тип кнопки, связанный с [классом CTaskDialog.](../../mfc/reference/ctaskdialog-class.md)

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>Параметры

*nButtonId*<br/>
(в) Стандартное значение кнопки Windows.

### <a name="return-value"></a>Возвращаемое значение

Значение соответствующей `CTaskDialog` общей кнопки. Если нет соответствующей общей кнопки, этот метод возвращает 0.

## <a name="ctaskdialoggetcommonbuttonid"></a><a name="getcommonbuttonid"></a>CTaskDialog::GetCommonButtonId

Преобразует один из распространенных типов кнопок, связанных с [классом CTaskDialog,](../../mfc/reference/ctaskdialog-class.md) в стандартную кнопку Windows.

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>Параметры

*nФлаг*<br/>
(в) Общий тип кнопки, связанный с классом. `CTaskDialog`

### <a name="return-value"></a>Возвращаемое значение

Значение соответствующей стандартной кнопки Windows. Если нет соответствующей кнопки Windows, метод возвращает 0.

## <a name="ctaskdialoggetoptions"></a><a name="getoptions"></a>CTaskDialog::GetOptions

Возвращает флаги опции для этого. `CTaskDialog`

```
int GetOptions() const;
```

### <a name="return-value"></a>Возвращаемое значение

Флаги для `CTaskDialog`.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о вариантах, доступных [для класса CTaskDialog,](../../mfc/reference/ctaskdialog-class.md)см. [CTaskDialog::SetOptions](#setoptions).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetselectedcommandcontrolid"></a><a name="getselectedcommandcontrolid"></a>CTaskDialog:GetSelectedCommandControlID

Возвращает выбранное управление кнопкой команды.

```
int GetSelectedCommandControlID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор выбранного в настоящее время управления кнопкой команды.

### <a name="remarks"></a>Remarks

Вам не нужно использовать этот метод для получения идентификатора кнопки команды, выбранной пользователем. Этот идентификатор возвращается либо [CTaskDialog::DoModal](#domodal) или [CTaskDialog::ShowDialog](#showdialog).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialoggetselectedradiobuttonid"></a><a name="getselectedradiobuttonid"></a>CTaskDialog::GetSelectedRadioButtonID

Возвращает выбранную кнопку радио.

```
int GetSelectedRadioButtonID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор выбранной кнопки радио.

### <a name="remarks"></a>Remarks

Этот метод можно использовать после того, как пользователь закроет диалоговую будку для получения выбранной кнопки радио.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialoggetverificationcheckboxstate"></a><a name="getverificationcheckboxstate"></a>CTaskDialog:GetVerificationCheckboxState

Извлекает состояние контрольного ящика проверки.

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если флажок проверяется, FALSE, если это не так.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogiscommandcontrolenabled"></a><a name="iscommandcontrolenabled"></a>CTaskDialog::IsCommandControlEnabled

Определяет, включено ли управление кнопкой команды или кнопка.

```
BOOL IsCommandControlEnabled(int nCommandControlID) const;
```

### <a name="parameters"></a>Параметры

*nCommandControlID*<br/>
(в) Идентификатор управления кнопкой команды или кнопки для тестирования.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если элемент управления включен, FALSE, если это не так.

### <a name="remarks"></a>Remarks

Этот метод можно использовать для определения наличия как элементов управления `CTaskDialog` кнопками команды, так и общих кнопок класса.

Если *nCommandControlID* не является действительным идентификатором для общей `CTaskDialog` кнопки или управления кнопкой команды, этот метод бросает исключение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogisradiobuttonenabled"></a><a name="isradiobuttonenabled"></a>CTaskDialog::IsRadioButton

Определяет, включена ли радиокнопка.

```
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;
```

### <a name="parameters"></a>Параметры

*nРадиоБаттонID*<br/>
(в) Идентификатор радиокнопки для тестирования.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если радио кнопка включена, FALSE, если это не так.

### <a name="remarks"></a>Remarks

Если *nRadioButtonID* не является действительным идентификатором для радиокнопки, этот метод выбрасывает исключение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogissupported"></a><a name="issupported"></a>CTaskDialog::Поддерживается

Определяет, поддерживает ли компьютер, работающий `CTaskDialog`под управлением приложения, .

```
static BOOL IsSupported();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если компьютер `CTaskDialog`поддерживает ; FALSE в противном случае.

### <a name="remarks"></a>Remarks

Используйте эту функцию, чтобы определить время выполнения, `CTaskDialog` поддерживает ли этот класс компьютер, работающий с приложением. Если компьютер не `CTaskDialog`поддерживает, вы должны предоставить другой способ передачи информации пользователю. Ваше приложение выйдет из строя, `CTaskDialog` если оно попытается `CTaskDialog` использовать компьютер, который не поддерживает класс.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogloadcommandcontrols"></a><a name="loadcommandcontrols"></a>CTaskDialog::LoadCommandControls

Добавляет элементы управления кнопками команд, используя данные из строки таблицы.

```cpp
void LoadCommandControls(
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast);
```

### <a name="parameters"></a>Параметры

*nIDCommandControlsFirst*<br/>
(в) Идентификатор строки первой команды.

*nIDCommandControlsLast*<br/>
(в) Идентификатор строки последней команды.

### <a name="remarks"></a>Remarks

Этот метод создает элементы управления кнопками команд, используя данные из файла ресурсов приложения. Таблица строк в файле ресурса имеет несколько строк с соответствующими имии строки. Новые элементы управления кнопкой команды, добавленные с помощью этого метода, используют строку для заголовка элемента управления и идентификатор строки для идентификатора элемента управления. Диапазон выбранных строк обеспечивается *nIDCommandControlsFirst* и *nCommandControlsLast*, включительно. Если в диапазоне есть пустая запись, метод не добавляет управление кнопкой команды для этой записи.

По умолчанию новые элементы управления кнопками команд включены и не требуют высоты.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogloadradiobuttons"></a><a name="loadradiobuttons"></a>CTaskDialog:LoadRadioButtons

Добавляет элементы управления радиокнопками с помощью данных из строки таблицы.

```cpp
void LoadRadioButtons(
    int nIDRadioButtonsFirst,
    int nIDRadioButtonsLast);
```

### <a name="parameters"></a>Параметры

*nIDRadioButtonsПервый*<br/>
(в) Идентификатор строки первой кнопки радио.

*nIDRadioButtonsПоследний*<br/>
(в) Идентификатор строки последней кнопки радио.

### <a name="remarks"></a>Remarks

Этот метод создает радиокнопки, используя данные из файла ресурса вашего приложения. Таблица строк в файле ресурса имеет несколько строк с соответствующими имии строки. Новые радиокнопки, добавленные с помощью этого метода, используют строку для заголовка радиокнопки и идентификатор строки для идентификатора радиокнопки. Диапазон выбранных строк обеспечивается *nIDRadioButtonsFirst* и *nRadioButtonsLast*, включительно. Если в диапазоне есть пустая запись, метод не добавляет кнопку радио для этой записи.

По умолчанию включены новые радиокнопки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialognavigateto"></a><a name="navigateto"></a>CTaskDialog::NavigateTo

Переносит фокус `CTaskDialog`на другой .

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>Параметры

*oTaskДиалог*<br/>
(в) Тот, `CTaskDialog` кто получает фокус.

### <a name="remarks"></a>Remarks

Этот метод скрывает `CTaskDialog` ток, когда он отображает *oTaskDialog.* *OTaskDialog* отображается в том же месте, что и текущий `CTaskDialog`.

## <a name="ctaskdialogoncommandcontrolclick"></a><a name="oncommandcontrolclick"></a>CTaskDialog::OnCommandControlClick

Рамочная система вызывает этот метод, когда пользователь нажимает на управление кнопкой команды.

```
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```

### <a name="parameters"></a>Параметры

*nCommandControlID*<br/>
(в) Идентификатор выбранного пользователем идентификатора кнопки команды.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogoncreate"></a><a name="oncreate"></a>CTaskDialog::OnCreate

Платформа вызывает этот метод после `CTaskDialog`того, как он создает .

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogondestroy"></a><a name="ondestroy"></a>CTaskDialog::Уничтожение

Рамки вызывает этот метод непосредственно перед `CTaskDialog`тем, как он уничтожает .

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogonexpandbuttonclick"></a><a name="onexpandbuttonclick"></a>CTaskDialog::OnExpandbutton

Рамочная система вызывает этот метод, когда пользователь нажимает на кнопку расширения.

```
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```

### <a name="parameters"></a>Параметры

*bРасширенный*<br/>
(в) Значение ненулевого указывает на отображение дополнительной информации; 0 указывает на то, что дополнительная информация скрыта.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogonhelp"></a><a name="onhelp"></a>CTaskDialog::OnHelp

Платформа вызывает этот метод, когда пользователь запрашивает помощь.

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogonhyperlinkclick"></a><a name="onhyperlinkclick"></a>CTaskDialog::OnHyperlinkClick

Рамочная система вызывает этот метод, когда пользователь нажимает на гиперссылку.

```
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```

### <a name="parameters"></a>Параметры

*strHref*<br/>
(в) Строка, представляющая гиперссылку.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Этот метод вызывает [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) перед тем, как он возвращается S_OK.

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogoninit"></a><a name="oninit"></a>CTaskDialog:It

Фрейм вызывает этот `CTaskDialog` метод, когда инициализирован.

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogonnavigatepage"></a><a name="onnavigatepage"></a>CTaskDialog::OnNavigatePage

Платформа называет этот метод в ответ на [метод CTaskDialog::NavigateTo.](#navigateto)

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogonradiobuttonclick"></a><a name="onradiobuttonclick"></a>CTaskDialog::OnRadioButton

Рамочная система вызывает этот метод, когда пользователь выбирает управление радиокнопкой.

```
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```

### <a name="parameters"></a>Параметры

*nРадиоБаттонID*<br/>
(в) Идентификатор управления радиокнопкой, на который нажал пользователь.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogontimer"></a><a name="ontimer"></a>CTaskDialog:OnTimer

Фрейм вызывает этот метод по истечении срока действия таймера.

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>Параметры

*lTime*<br/>
(в) Время в миллисекундах с момента `CTaskDialog` создания или сбросить таймер.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogonverificationcheckboxclick"></a><a name="onverificationcheckboxclick"></a>CTaskDialog::OnVerificationCheckboxClick

Рамочная система вызывает этот метод, когда пользователь нажимает на флажок проверки.

```
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```

### <a name="parameters"></a>Параметры

*bChecked*<br/>
(в) TRUE указывает на то, что выбрана проверка флажка; FALSE указывает, что это не так.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращается S_OK.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для реализации пользовательского поведения.

## <a name="ctaskdialogremoveallcommandcontrols"></a><a name="removeallcommandcontrols"></a>CTaskDialog::RemoveAllCommandControls

Удаляет все элементы управления `CTaskDialog`кнопкой команды из .

```cpp
void RemoveAllCommandControls();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogremoveallradiobuttons"></a><a name="removeallradiobuttons"></a>CTaskDialog::RemoveAllRadioButtons

Удаляет все радиокнопки с `CTaskDialog`.

```cpp
void RemoveAllRadioButtons();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetcommandcontroloptions"></a><a name="setcommandcontroloptions"></a>CTaskDialog::SetCommandControlOptions

Обновляет управление кнопкой `CTaskDialog`команды на .

```cpp
void SetCommandControlOptions(
    int nCommandControlID,
    BOOL bEnabled,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Параметры

*nCommandControlID*<br/>
(в) Идентификатор командного управления для обновления.

*bВСтои*<br/>
(в) Параметр Boolean, указывающий, включен или отключен указанный элемент управления кнопкой команды.

*bRequiresВысота*<br/>
(в) Параметр Boolean, указывающий, требует ли указанное управление кнопкой командования высотой.

### <a name="remarks"></a>Remarks

Используйте этот метод, чтобы изменить, включен ли элемент управления кнопкой командования или требует высоты после его добавления в `CTaskDialog` класс.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetcommonbuttonoptions"></a><a name="setcommonbuttonoptions"></a>CTaskDialog::SetCommonButton

Обновляет подмножество общих кнопок, которые должны быть включены и требуют высоты UAC.

```cpp
void SetCommonButtonOptions(
    int nDisabledButtonMask,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Параметры

*nDisabledButtonMask*<br/>
(в) Маска для обычных кнопок, чтобы отключить.

*nElevationButtonMask*<br/>
(в) Маска для общих кнопок, требующих высоты.

### <a name="remarks"></a>Remarks

Вы можете настроить общие кнопки, доступные для экземпляра [класса CTaskDialog,](../../mfc/reference/ctaskdialog-class.md) используя конструктор [CTaskDialog::CTaskDialog](#ctaskdialog) и метод [CTaskDialog::SetCommonButtons](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions`не поддерживает добавление новых общих кнопок.

Если вы используете этот метод, чтобы отключить или поднять общую кнопку, которая не доступна для этого, `CTaskDialog`этот метод бросает исключение с помощью макроса [ENSURE.](diagnostic-services.md#ensure)

Этот метод позволяет любую кнопку, которая доступна, `CTaskDialog` но не в *nDisabledButtonMask*, даже если он был ранее отключен. Этот метод рассматривает высоту аналогичным образом: он записывает общие кнопки как не требующие высоты, если общая кнопка доступна, но не включена в *nElevationButtonMask*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcommonbuttons"></a><a name="setcommonbuttons"></a>CTaskDialog::SetCommonButtons

Добавляет общие кнопки `CTaskDialog`в .

```cpp
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Параметры

*nButtonMask*<br/>
(в) Маска кнопок, чтобы `CTaskDialog`добавить в .

*nDisabledButtonMask*<br/>
(в) Маска кнопок, чтобы отключить.

*nElevationButtonMask*<br/>
(в) Маска кнопок, требующих высоты.

### <a name="remarks"></a>Remarks

Вы не можете вызвать этот метод после `CTaskDialog` создания окна дисплея для данного экземпляра класса. Если вы делаете, этот метод бросает исключение.

Кнопки, указанные *nButtonMask* переопределить любые общие `CTaskDialog`кнопки, ранее добавленные в . Доступны только кнопки, указанные в *nButtonMask.*

Если либо *nDisabledButtonMask* или *nElevationButtonMask* содержат кнопку, которая не находится в *nButtonMask*, этот метод бросает исключение с помощью макроса [ENSURE.](diagnostic-services.md#ensure)

По умолчанию все общие кнопки включены и не требуют высоты.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcontent"></a><a name="setcontent"></a>CTaskDialog::SetContent

Обновляет содержание `CTaskDialog`.

```cpp
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>Параметры

*strContent*<br/>
(в) Строка для отображения пользователю.

### <a name="remarks"></a>Remarks

Содержимое `CTaskDialog` класса — это текст, отображаемый пользователю в основной части диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetdefaultcommandcontrol"></a><a name="setdefaultcommandcontrol"></a>CTaskDialog::SetDefaultCommandControl

Определяет управление кнопкой команды по умолчанию.

```cpp
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>Параметры

*nCommandControlID*<br/>
(в) Идентификатор управления кнопкой команды будет по умолчанию.

### <a name="remarks"></a>Remarks

Управление кнопкой команды по умолчанию — `CTaskDialog` это элемент управления, который выбирается при первом отображении пользователю.

Этот метод бросает исключение, если он не может найти управление кнопкой команды, указанное *nCommandControlID.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetdefaultradiobutton"></a><a name="setdefaultradiobutton"></a>CTaskDialog::SetDefaultRadioButton

Определяет кнопку радио по умолчанию.

```cpp
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>Параметры

*nРадиоБаттонID*<br/>
(в) Идентификатор кнопки радио будет по умолчанию.

### <a name="remarks"></a>Remarks

Радиокнопка по умолчанию — это `CTaskDialog` кнопка, выбранная при первом отображении пользователю.

Этот метод бросает исключение, если он не может найти кнопку радио, указанную *nRadioButtonID.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetdialogwidth"></a><a name="setdialogwidth"></a>CTaskDialog::SetDialogWidth

Регулирует ширину `CTaskDialog`.

```cpp
void SetDialogWidth(int nWidth = 0);
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
(в) Ширина диалогового окна, в пикселях.

### <a name="remarks"></a>Remarks

Параметр *nWidth* должен быть больше или равен 0. В противном случае этот метод выбрасывает исключение.

Если *nWidth* установлен до 0, этот метод устанавливает поле диалога к размеру по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetexpansionarea"></a><a name="setexpansionarea"></a>CTaskDialog::SetExpansionArea

Обновляет область расширения `CTaskDialog`.

```cpp
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>Параметры

*strExpandedInformation*<br/>
(в) Строка, `CTaskDialog` которую отображается в основном корпусе диалогового окна, когда пользователь нажимает кнопку расширения.

*strCollapsedLabel*<br/>
(в) Строка, `CTaskDialog` которая отображается рядом с кнопкой расширения при обрушении расширенной области.

*strExpandedLabel*<br/>
(в) Строка, `CTaskDialog` которая отображается рядом с кнопкой расширения при отображении расширенной области.

### <a name="remarks"></a>Remarks

Область расширения `CTaskDialog` класса позволяет предоставлять пользователю дополнительную информацию. Область расширения находится в основной `CTaskDialog`части , расположенных непосредственно под названием и содержание строки.

При `CTaskDialog` первом отображении он не отображает `strCollapsedLabel` расширенную информацию и помещается рядом с кнопкой расширения. Когда пользователь нажимает кнопку расширения, `CTaskDialog` отображает *strExpandedInformation* и изменяет метку на *strExpandedLabel.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootericon"></a><a name="setfootericon"></a>CTaskDialog::SetFooterIcon

Обновления колонтитул значок `CTaskDialog`.

```cpp
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>Параметры

*hFooterIcon*<br/>
(в) Новая иконка `CTaskDialog`для .

*lpszFooterIcon*<br/>
(в) Новая иконка `CTaskDialog`для .

### <a name="remarks"></a>Remarks

Значок колонтитула отображается в нижней части [класса CTaskDialog.](../../mfc/reference/ctaskdialog-class.md) Он может иметь связанный текст колонтитула. Вы можете изменить текст колонтитула с [помощью CTaskDialog::SetFooterText](#setfootertext).

Этот метод выбрасывает исключение с макросом [ENSURE,](diagnostic-services.md#ensure) если `CTaskDialog` отображается или параметр ввода NULL.

A `CTaskDialog` может принимать `HICON` `LPCWSTR` только или в качестве значка колонтитула. Это настроено путем установки опции TDF_USE_HICON_FOOTER в конструкторе или [CTaskDialog::SetOptions](#setoptions). По умолчанию `CTaskDialog` настроен для `LPCWSTR` использования в качестве ввода для значка колонтитула. Этот метод генерирует исключение, если вы попытаетесь установить значок с помощью неподходящего типа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootertext"></a><a name="setfootertext"></a>CTaskDialog::SetFooterText

Обновления текста на колонтитул `CTaskDialog`.

```cpp
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>Параметры

*strFooterText*<br/>
(в) Новый текст для колонтитула.

### <a name="remarks"></a>Remarks

Значок колонтитула появляется рядом с текстом колонтитула на дне `CTaskDialog`. Вы можете изменить значок колонтитула с [CTaskDialog::SetFooterIcon](#setfootericon).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmainicon"></a><a name="setmainicon"></a>CTaskDialog::SetMainIcon

Обновления главной иконы `CTaskDialog`.

```cpp
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>Параметры

*hMainIcon*<br/>
(в) Новая икона.

*lpszMainIcon*<br/>
(в) Новая икона.

### <a name="remarks"></a>Remarks

Этот метод выбрасывает исключение с макросом [ENSURE,](diagnostic-services.md#ensure) если `CTaskDialog` отображается или параметр ввода NULL.

A `CTaskDialog` может принимать `HICON` `LPCWSTR` только или в качестве основного значка. Вы можете настроить это, установив TDF_USE_HICON_MAIN опцию в конструкторе или в методе [CTaskDialog::SetOptions.](#setoptions) По умолчанию `CTaskDialog` настроен для `LPCWSTR` использования в качестве ввода для основного значка. Этот метод генерирует исключение, если вы попытаетесь установить значок с помощью неподходящего типа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmaininstruction"></a><a name="setmaininstruction"></a>CTaskDialog::SetMainInstruction

Обновления основной инструкции `CTaskDialog`.

```cpp
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>Параметры

*strИнструкции*<br/>
(в) Новая основная инструкция.

### <a name="remarks"></a>Remarks

Основной инструкцией `CTaskDialog` класса является текст, отображаемый пользователю большим жирным шрифтом. Он расположен в диалоговом поле под заголовком бара.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetoptions"></a><a name="setoptions"></a>CTaskDialog::SetOptions

Настраивает варианты `CTaskDialog`для .

```cpp
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>Параметры

*nOptionFlag*<br/>
(в) Набор флагов для использования `CTaskDialog`для .

### <a name="remarks"></a>Remarks

Этот метод очищает все текущие `CTaskDialog`параметры для . Чтобы сохранить текущие параметры, вы должны получить их сначала с [CTaskDialog::GetOptions](#getoptions) и объединить их с вариантами, которые вы хотите установить.

В следующей таблице перечислены все допустимые варианты.

|||
|-|-|
|TDF_ENABLE_HYPERLINKS|Позволяет гиперссылки `CTaskDialog`в .|
|TDF_USE_HICON_MAIN|Настраивает `CTaskDialog` использовать `HICON` для основного значка. Альтернативой является использование `LPCWSTR`.|
|TDF_USE_HICON_FOOTER|Настраивает `CTaskDialog` использовать `HICON` для колонтитулзначк. Альтернативой является использование `LPCWSTR`.|
|TDF_ALLOW_DIALOG_CANCELLATION|Позволяет пользователю закрыть `CTaskDialog` его с помощью клавиатуры или с помощью значка в правом верхнем углу диалогового окна, даже если кнопка **Отмена** не включена. Если этот флаг не установлен и кнопка **«Отмена»** не включена, пользователь не может закрыть поле диалога, используя alt-F4, ключ Escape или кнопку закрытия заголовка.|
|TDF_USE_COMMAND_LINKS|Настраивает `CTaskDialog` на использование управления кнопками команд.|
|TDF_USE_COMMAND_LINKS_NO_ICON|Настраивает `CTaskDialog` элементы управления кнопками команд без отображения значка рядом с управлением. TDF_USE_COMMAND_LINKS переопределяет TDF_USE_COMMAND_LINKS_NO_ICON.|
|TDF_EXPAND_FOOTER_AREA|Указывает на расширение области в настоящее время расширяется.|
|TDF_EXPANDED_BY_DEFAULT|Определяет, расширяется ли область расширения по умолчанию.|
|TDF_VERIFICATION_FLAG_CHECKED|Указывает на то, что в настоящее время выбрана флажок проверки.|
|TDF_SHOW_PROGRESS_BAR|Настраивает `CTaskDialog` панель прогресса.|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|Настраивает панель прогресса, чтобы быть баром прогресса шатер. Если вы включите эту опцию, необходимо установить TDF_SHOW_PROGRESS_BAR, чтобы иметь ожидаемое поведение.|
|TDF_CALLBACK_TIMER|Означает, `CTaskDialog` что интервал обратного вызова установлен примерно до 200 миллисекунд.|
|TDF_POSITION_RELATIVE_TO_WINDOW|Настраивает `CTaskDialog` центровое окно по отношению к родительскому окну. Если этот флаг не `CTaskDialog` включен, центрировка по центру по отношению к монитору.|
|TDF_RTL_LAYOUT|Настраивает `CTaskDialog` макет чтения справа налево.|
|TDF_NO_DEFAULT_RADIO_BUTTON|Означает, что при отобрасвении `CTaskDialog` кнопки радио не выбирается.|
|TDF_CAN_BE_MINIMIZED|Позволяет пользователю свести к минимуму `CTaskDialog`. Для поддержки этого `CTaskDialog` параметра, не может быть модальным. МФЦ не поддерживает эту опцию, потому `CTaskDialog`что МФЦ не поддерживает безрежимный.|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetprogressbarmarquee"></a><a name="setprogressbarmarquee"></a>CTaskDialog::SetProgressBarMarquee

Настраивает шатер-бар `CTaskDialog` для и добавляет его в диалоговую будку.

```cpp
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>Параметры

*bВСтои*<br/>
(в) TRUE для включения шатер бар; FALSE отключить шатер бар и удалить его `CTaskDialog`из .

*nMarqueeSpeed*<br/>
(в) Цель, которая указывает скорость шатер бар.

### <a name="remarks"></a>Remarks

Под основным текстом `CTaskDialog` класса отображается шатер-бар.

Используйте *nMarqueeSpeed,* чтобы установить скорость шатер бар; большие значения указывают на более низкую скорость. Значение 0 для *nMarqueeSpeed* делает шатер бар двигаться со скоростью по умолчанию для Windows.

Этот метод бросает исключение с macro [ENSURE,](diagnostic-services.md#ensure) если *nMarqueeSpeed* меньше 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarposition"></a><a name="setprogressbarposition"></a>CTaskDialog::SetProgressBarPosition

Регулирует положение панели прогресса.

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Параметры

*nProgressPos*<br/>
(в) Позиция для бара прогресса.

### <a name="remarks"></a>Remarks

Этот метод выбрасывает исключение с макросом [ENSURE,](diagnostic-services.md#ensure) если *nProgressPos* не находится в диапазоне диапазона панели прогресса. Вы можете изменить диапазон панели прогресса с [помощью CTaskDialog::SetProgressBarRange](#setprogressbarrange).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarrange"></a><a name="setprogressbarrange"></a>CTaskDialog::SetProgressBarRange

Регулирует диапазон панели прогресса.

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Параметры

*nRangeMin*<br/>
(в) Нижняя граница бара прогресса.

*nRangeMax*<br/>
(в) Верхняя граница бара прогресса.

### <a name="remarks"></a>Remarks

Положение панели прогресса относительно *nRangeMin* и *nRangeMax.* Например, если *nRangeMin* 50, *а nRangeMax* - 100, то положение 75 находится на полпути к планке прогресса. Используйте [CTaskDialog::SetProgressBarPosition,](#setprogressbarposition) чтобы установить положение панели прогресса.

Для отображения панели прогресса необходимо TDF_SHOW_PROGRESS_BAR опции и TDF_SHOW_MARQUEE_PROGRESS_BAR не должны быть включены. Этот метод автоматически устанавливает TDF_SHOW_PROGRESS_BAR и очищает TDF_SHOW_MARQUEE_PROGRESS_BAR. Используйте [CTaskDialog::SetOptions,](#setoptions) чтобы вручную изменить параметры для данного экземпляра [класса CTaskDialog.](../../mfc/reference/ctaskdialog-class.md)

Этот метод бросает исключение с macro [ENSURE,](diagnostic-services.md#ensure) если *nRangeMin* не меньше *nRangeMax.* Этот метод также бросает исключение, если уже `CTaskDialog` отображается и имеет шатер прогресса бар.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarstate"></a><a name="setprogressbarstate"></a>CTaskDialog::SetProgressBarState

Устанавливает состояние панели прогресса и отображает ее `CTaskDialog`на .

```cpp
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>Параметры

*nState*<br/>
(в) Состояние бара прогресса. Овозможных значениях читайте в разделе Замечания.

### <a name="remarks"></a>Remarks

Этот метод бросает исключение с macro `CTaskDialog` [ENSURE,](diagnostic-services.md#ensure) если уже отображается и имеет бар прогресса шатер.

В следующей таблице перечислены возможные значения для *nState.* Во всех этих случаях панель прогресса заполняется обычным цветом до тех пор, пока не достигнет назначенной стоп-позиции. В этот момент он будет менять цвет в зависимости от состояния.

|||
|-|-|
|PBST_NORMAL|После заполнения `CTaskDialog` панели прогресса цвет бара не меняется. По умолчанию обычный цвет зеленый.|
|PBST_ERROR|После заполнения панели прогресса `CTaskDialog` цвет бара меняется на цвет ошибки. По умолчанию это красный цвет.|
|PBST_PAUSED|После заполнения панели прогресса `CTaskDialog` цвет бара меняется на приостановленный цвет. По умолчанию это желтый цвет.|

Вы можете установить, где панель прогресса останавливается с [CTaskDialog::SetProgressBarPosition](#setprogressbarposition).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetradiobuttonoptions"></a><a name="setradiobuttonoptions"></a>CTaskDialog::SetRadioButtonOptions

Включает или отсваивает кнопку радио.

```cpp
void SetRadioButtonOptions(
    int nRadioButtonID,
    BOOL bEnabled);
```

### <a name="parameters"></a>Параметры

*nРадиоБаттонID*<br/>
(в) Идентификатор управления радиокнопкой.

*bВСтои*<br/>
(в) TRUE для включения кнопки радио; FALSE отключить кнопку радио.

### <a name="remarks"></a>Remarks

Этот метод бросает исключение с макросом [ENSURE,](diagnostic-services.md#ensure) если *nRadioButtonID* не является действительным идентификатором для радиокнопки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetverificationcheckbox"></a><a name="setverificationcheckbox"></a>CTaskDialog:SetVerificationCheckbox

Устанавливает проверенное состояние контрольного ящика проверки.

```cpp
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>Параметры

*bChecked*<br/>
(в) TRUE для выбора флажка проверки при отображении; `CTaskDialog` FALSE, чтобы проверить флажок невыбранный при отображении. `CTaskDialog`

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetverificationcheckboxtext"></a><a name="setverificationcheckboxtext"></a>CTaskDialog::SetVerificationCheckboxText

Устанавливает текст, отображаемый справа от флажка проверки.

```cpp
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>Параметры

*strVerificationText*<br/>
(в) Текст, который этот метод отображает рядом с флажкой проверки.

### <a name="remarks"></a>Remarks

Этот метод выбрасывает исключение с макросом `CTaskDialog` [ENSURE,](diagnostic-services.md#ensure) если этот экземпляр класса уже отображается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetwindowtitle"></a><a name="setwindowtitle"></a>CTaskDialog::SetWindowTitle

Устанавливает название `CTaskDialog`.

```cpp
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>Параметры

*strWindowTitle*<br/>
(в) Новое название для `CTaskDialog`.

### <a name="remarks"></a>Remarks

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogshowdialog"></a><a name="showdialog"></a>CTaskDialog:ShowDialog

Создает и отображает `CTaskDialog`.

```
static INT_PTR ShowDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons = TDCBF_YES_BUTTON | TDCBF_NO_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>Параметры

*strContent*<br/>
(в) Строка для использования для `CTaskDialog`содержания .

*strMainInstruction*<br/>
(в) Основная инструкция `CTaskDialog`.

*strTitle*<br/>
(в) Название `CTaskDialog`.

*nIDCommandControlsFirst*<br/>
(в) Идентификатор строки первой команды.

*nIDCommandControlsLast*<br/>
(в) Идентификатор строки последней команды.

*nCommonButtons*<br/>
(в) Маска кнопок, чтобы `CTaskDialog`добавить в .

*nTaskDialogOptions*<br/>
(в) Набор опций для использования `CTaskDialog`для .

*strFooter*<br/>
(в) Строка для использования в качестве колонтитула.

### <a name="return-value"></a>Возвращаемое значение

Цель, которая соответствует выбору, сделанному пользователем.

### <a name="remarks"></a>Remarks

Этот статический метод позволяет создать `CTaskDialog` экземпляр класса без `CTaskDialog` явного создания объекта в коде. Поскольку объекта `CTaskDialog` нет, нельзя вызывать другие `CTaskDialog` методы, если вы `CTaskDialog` используете этот метод для отображения пользователя.

Этот метод создает элементы управления кнопками команд, используя данные из файла ресурсов приложения. Таблица строк в файле ресурса имеет несколько строк с соответствующими имии строки. Этот метод добавляет управление кнопкой команды для каждого действительного входа в строку таблицы между *nIDCommandControlsFirst* и *nCommandControlsLast*, включительно. Для этих элементов управления кнопкой команды строка в таблице строки является подписью управления, а идентификатор строки — идентификатором управления.

Смотрите [CTaskDialog::SetOptions](#setoptions) для списка действительных вариантов.

Закрывается, `CTaskDialog` когда пользователь выбирает общую кнопку, управление командой `CTaskDialog`или закрывает. Значение возврата — это идентификатор, указывающий, как пользователь закрыл диалоговое окно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogtaskdialogcallback"></a><a name="taskdialogcallback"></a>CTaskDialog::TaskDialogCallback

Платформа вызывает этот метод в ответ на различные сообщения Windows.

```
friend:
HRESULT TaskDialogCallback(
    HWND hWnd,
    UINT uNotification,
    WPARAM wParam,
    LPARAM lParam,
    LONG_PTR dwRefData);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к `m_hWnd` структуре `CTaskDialog`для .

*uУведомление*<br/>
(в) Код уведомления, опозначающие генерируемое сообщение.

*wParam*<br/>
(в) Более подробная информация о сообщении.

*lParam*<br/>
(в) Более подробная информация о сообщении.

*dwRefData*<br/>
(в) Указатель на `CTaskDialog` объект, к сообщению обратного вызова.

### <a name="return-value"></a>Возвращаемое значение

Зависит от конкретного кода уведомлений. Дополнительные сведения см. в разделе «Примечания».

### <a name="remarks"></a>Remarks

Реализация по `TaskDialogCallback` умолчанию обрабатывает конкретное сообщение, а затем вызывает соответствующий метод На методе [класса CTaskDialog.](../../mfc/reference/ctaskdialog-class.md) Например, в ответ на `TaskDialogCallback` сообщение TDN_BUTTON_CLICKED [звоните CTaskDialog::OnCommandControlClick](#oncommandcontrolclick).

Значения для *wParam* и *lParam* зависят от конкретного генерируемого сообщения. Любое или оба этих значения могут быть пустыми. В следующей таблице перечислены уведомления по умолчанию, которые поддерживаются, и то, что значения *wParam* и *lParam* представляют. Если вы переопределяете этот метод в производном классе, следует реализовать код обратного вызова для каждого сообщения в следующей таблице.

|Сообщение об уведомлении|*wParam* Значение|*lПарам* Значение|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|Не используется.|Не используется.|
|TDN_NAVIGATED|Не используется.|Не используется.|
|TDN_BUTTON_CLICKED|Идентификатор управления кнопкой команды.|Не используется.|
|TDN_HYPERLINK_CLICKED|Не используется.|Структура [LPCWSTR,](/windows/win32/WinProg/windows-data-types) содержащая ссылку.|
|TDN_TIMER|Время в миллисекундах с момента `CTaskDialog` создания или сбросить таймер.|Не используется.|
|TDN_DESTROYED|Не используется.|Не используется.|
|TDN_RADIO_BUTTON_CLICKED|Идентификатор радиокнопки.|Не используется.|
|TDN_DIALOG_CONSTRUCTED|Не используется.|Не используется.|
|TDN_VERIFICATION_CLICKED|1, если флажок проверен, 0, если это не так.|Не используется.|
|TDN_HELP|Не используется.|Не используется.|
|TDN_EXPANDO_BUTTON_CLICKED|0, если область расширения разрушена; ненулевой, если отображается текст расширения.|Не используется.|

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Пошаговое руководство. Добавление CTaskDialog в приложение](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)
