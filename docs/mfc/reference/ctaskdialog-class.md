---
title: Класс CTaskDialog | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8d3f081cc74c6e4288bc2e0e8d3b15af8dba325
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42538356"
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
|[CTaskDialog::CTaskDialog](#ctaskdialog)|Создает объект `CTaskDialog`.|  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|Добавляет элемент управления кнопки команд для `CTaskDialog`.|  
|[CTaskDialog::AddRadioButton](#addradiobutton)|Добавляет переключатель, чтобы `CTaskDialog`.|  
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Нажимает кнопку или общие кнопки программным способом.|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Нажимает типа "переключатель" программным способом.|  
|[CTaskDialog::DoModal](#domodal)|Отображает `CTaskDialog`.|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|Возвращает число доступных общих кнопок.|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Преобразует стандартной кнопки Windows в общий тип кнопки связан `CTaskDialog` класса.|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|Преобразует один из распространенных типов кнопки, связанных с `CTaskDialog` класс стандартной кнопки Windows.|  
|[CTaskDialog::GetOptions](#getoptions)|Возвращает флаги параметров для этого `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|Возвращает выбранный элемент управления.|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Возвращает выбранного переключателя.|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|Получает состояние флажка проверки.|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Определяет, включена ли команда управления "Кнопка" или общие кнопки.|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|Определяет, включен ли параметр типа "переключатель".|  
|[CTaskDialog::IsSupported](#issupported)|Определяет, поддерживает ли компьютер, на котором выполняется приложение `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Добавляет кнопку командные элементы управления, используя данные из таблицы строки.|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|Добавляет переключателей, используя данные из таблицы строки.|  
|[CTaskDialog::NavigateTo](#navigateto)|Передает фокус на другой `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Этот метод вызывается платформой, когда пользователь нажимает кнопку.|  
|[CTaskDialog::OnCreate](#oncreate)|Платформа вызывает этот метод после создания `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](#ondestroy)|Этот метод вызывается платформой непосредственно перед уничтожает `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|Этот метод вызывается платформой, когда пользователь нажимает кнопку «расширения».|  
|[CTaskDialog::OnHelp](#onhelp)|Этот метод вызывается платформой, когда пользователь запросит справку.|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|Этот метод вызывается платформой, когда пользователь щелкает гиперссылку.|  
|[CTaskDialog::OnInit](#oninit)|Этот метод вызывается платформой при `CTaskDialog` инициализируется.|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Этот метод вызывается платформой, когда пользователь перемещает фокус по отношению к элементам управления `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|Этот метод вызывается платформой, когда пользователь выбирает элемент управления переключателя.|  
|[CTaskDialog::OnTimer](#ontimer)|Этот метод вызывается платформой, по истечении срока действия таймера.|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|Этот метод вызывается платформой, когда пользователь щелкает флажок проверки.|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Удаляет все командные элементы управления из `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Удаляет всех переключателей из `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Обновляет элемент управления кнопки команд на `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|Обновляет подмножество общих кнопок включена и требуется повышение Полномочий.|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|Добавляет стандартные кнопки для `CTaskDialog`.|  
|[CTaskDialog::SetContent](#setcontent)|Обновляет содержимое `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Указывает элемент управления по умолчанию.|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Указывает значение по умолчанию переключателя.|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|Корректирует ширину `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|Обновляет область расширения `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|Обновляет значок нижнего колонтитула `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](#setfootertext)|Обновляет текст в нижнем колонтитуле `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](#setmainicon)|Обновляет главного значка `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Обновляет основные инструкция `CTaskDialog`.|  
|[CTaskDialog::SetOptions](#setoptions)|Служит для настройки параметров для `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|Настраивает индикатора для `CTaskDialog` и добавляет его в диалоговое окно.|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|Регулирует положение индикатора выполнения.|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|Настройка диапазона индикатора.|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|Задает состояние индикатора хода выполнения и отображает его на `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Включает или отключает переключатель.|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|Задает состояние флажка проверки.|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Задает текст справа от флажка проверки.|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Задает название `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](#showdialog)|Создает и отображает `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Это вызывается платформой в ответ на различные сообщения Windows.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|`m_aButtons`|Массив элементов управления кнопки команд для `CTaskDialog`.|  
|`m_aRadioButtons`|Массив элементов управления переключателями для `CTaskDialog`.|  
|`m_bVerified`|`TRUE` Указывает, что установлен флажок проверки; `FALSE` указывает, это не так.|  
|`m_footerIcon`|Значок в нижнем колонтитуле `CTaskDialog`.|  
|`m_hWnd`|Дескриптор окна для `CTaskDialog`.|  
|`m_mainIcon`|Главного значка `CTaskDialog`.|  
|`m_nButtonDisabled`|Маска, которая указывает, какие из стандартные кнопки будут отключены.|  
|`m_nButtonElevation`|Маска, которая указывает, какой из общих кнопок требуется повышение прав контроля учетных Записей.|  
|`m_nButtonId`|Идентификатор элемента управления button выбранной команды.|  
|`m_nCommonButton`|Маска, которая указывает, какие общие кнопки отображаются на `CTaskDialog`.|  
|`m_nDefaultCommandControl`|Идентификатор кнопки элемента управления, при выборе `CTaskDialog` отображается.|  
|`m_nDefaultRadioButton`|Идентификатор переключателя элемента управления, при выборе `CTaskDialog` отображается.|  
|`m_nFlags`|Маска, которая указывает параметры, `CTaskDialog`.|  
|`m_nProgressPos`|Текущая позиция индикатор хода выполнения.  Это значение должно принадлежать диапазону от `m_nProgressRangeMin` до `m_nProgressRangeMax`.|  
|`m_nProgressRangeMax`|Максимальное значение для индикатора выполнения.|  
|`m_nProgressRangeMin`|Минимальное значение для индикатора выполнения.|  
|`m_nProgressState`|Состояние индикатора хода выполнения. Дополнительные сведения см. в разделе [CTaskDialog::SetProgressBarState](#setprogressbarstate).|  
|`m_nRadioId`|Идентификатор выбранного переключателя.|  
|`m_nWidth`|Ширина `CTaskDialog` в пикселях.|  
|`m_strCollapse`|Строка `CTaskDialog` отображается справа от поля расширения при Расширенная информация является скрытым.|  
|`m_strContent`|Строку содержимого объекта `CTaskDialog`.|  
|`m_strExpand`|Строка `CTaskDialog` отображается справа от поля расширения при отображении расширенные сведения.|  
|`m_strFooter`|Нижний колонтитул `CTaskDialog`.|  
|`m_strInformation`|Подробные сведения для `CTaskDialog`.|  
|`m_strMainInstruction`|Основные инструкции из `CTaskDialog`.|  
|`m_strTitle`|Название `CTaskDialog`.|  
|`m_strVerification`|Строка, `CTaskDialog` отображается справа от флажка проверки.|  
  
## <a name="remarks"></a>Примечания  
 `CTaskDialog` Класс заменяет стандартным окном сообщений Windows и имеет дополнительные функциональные возможности, такие как новые элементы управления для сбора информации от пользователя. Этот класс находится в библиотеке MFC в Visual Studio 2010 и более поздних версий. `CTaskDialog` Доступен, начиная с Windows Vista. Более ранние версии Windows не удается отобразить `CTaskDialog` объекта. Используйте `CTaskDialog::IsSupported` на этапе выполнения определить, может ли текущий пользователь отображать диалоговое окно задачи. Стандартным окном сообщений Windows по-прежнему поддерживается.  
  
 `CTaskDialog` Доступен только при построении приложения с помощью библиотеки Юникода.  
  
 `CTaskDialog` Имеет двух различных конструкторов. Один конструктор позволяет указать две кнопки и не более шести элементов управления обычная кнопка. После создания можно добавить дополнительные кнопки `CTaskDialog`. Второй конструктор не поддерживает все кнопки, но можно добавить неограниченное число регулярных кнопок. Дополнительные сведения о конструкторах см. в разделе [CTaskDialog::CTaskDialog](#ctaskdialog).  
  
 На следующем рисунке показано пример `CTaskDialog` для иллюстрации расположение некоторых элементов управления.  
  
 ![Пример CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
Образец CTaskDialog  
  
## <a name="requirements"></a>Требования  
 **Минимальная требуемая ОС:** Windows Vista  
  
 **Заголовок:** afxtaskdialog.h  
  
##  <a name="addcommandcontrol"></a>  CTaskDialog::AddCommandControl  
 Добавляет новый элемент управления кнопки команд для `CTaskDialog`.  
  
```  
void AddCommandControl(
    int nCommandControlID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификационный номер команды управления.  
  
 [in] *strCaption*  
 Строка, `CTaskDialog` отображает для пользователя. Используйте эту строку в качестве пояснения команды.  
  
 [in] *bEnabled*  
 Логический параметр, который указывает, включен ли новая кнопка.  
  
 [in] *bRequiresElevation*  
 Логический параметр, который указывает, требуется ли команда повышения прав.  
  
### <a name="remarks"></a>Примечания  
 `CTaskDialog Class` Можно отобразить неограниченное число элементов управления кнопки команд. Тем не менее если `CTaskDialog` отобразится любой кнопки команды элементов управления, его можно отобразить до шести кнопок. Если `CTaskDialog` не содержит команду кнопки элементов управления, его можно отобразить неограниченное количество кнопок.  
  
 Когда пользователь выбирает команду кнопки, `CTaskDialog` закрывается. Если приложение отображает диалоговое окно с помощью [CTaskDialog::DoModal](#domodal), `DoModal` возвращает *nCommandControlID* элемента управления button выбранной команды.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="addradiobutton"></a>  CTaskDialog::AddRadioButton  
 Добавляет переключатель, чтобы `CTaskDialog`.  
  
```  
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRadioButtonID*  
 Идентификационный номер переключателя.  
  
 [in] *strCaption*  
 Строка, `CTaskDialog` рядом переключатель отображается.  
  
 [in] *bEnabled*  
 Логический параметр, который указывает, включен ли переключатель.  
  
### <a name="remarks"></a>Примечания  
 Радио кнопки для [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) позволяют собирать информацию от пользователя. Используйте функцию [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) для определения, какой переключатель выбран.  
  
 `CTaskDialog` Не требует *nRadioButtonID* параметры являются уникальными для каждого переключателя. Тем не менее могут возникнуть непредвиденное поведение, если вы не используете distinct идентификатор для каждого переключателя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="clickcommandcontrol"></a>  CTaskDialog::ClickCommandControl  
 Нажимает кнопку или общие кнопки программным способом.  
  
```  
protected:  
void ClickCommandControl(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор команды элемента управления, нажмите кнопку.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает TDM_CLICK_BUTTON сообщение windows.  
  
##  <a name="clickradiobutton"></a>  CTaskDialog::ClickRadioButton  
 Нажимает типа "переключатель" программным способом.  
  
```  
protected:  
void ClickRadioButton(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRadioButtonID*  
 Идентификатор нажмите кнопку переключателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает TDM_CLICK_RADIO_BUTTON сообщение windows.  
  
##  <a name="ctaskdialog"></a>  CTaskDialog::CTaskDialog  
 Создает экземпляр класса [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md).  
  
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
 [in] *strContent*  
 Строка, используемая для содержимого `CTaskDialog`.  
  
 [in] *strMainInstruction*  
 Основные инструкции из `CTaskDialog`.  
  
 [in] *strTitle*  
 Название `CTaskDialog`.  
  
 [in] *nCommonButtons*  
 Стандартные кнопки, чтобы добавить маску `CTaskDialog`.  
  
 [in] *nTaskDialogOptions*  
 Набор параметров для `CTaskDialog`.  
  
 [in] *strFooter*  
 Строка для использования в качестве нижнего колонтитула.  
  
 [in] *nIDCommandControlsFirst*  
 Идентификатор строки первой команды.  
  
 [in] *nIDCommandControlsLast*  
 Идентификатор строки последней команды.  
  
### <a name="remarks"></a>Примечания  
 Существует два способа, которые можно добавить `CTaskDialog` в приложение. Первый способ — использовать один из конструкторов для создания `CTaskDialog` и отобразить ее с помощью [CTaskDialog::DoModal](#domodal). Второй способ — использовать статическую функцию [CTaskDialog::ShowDialog](#showdialog), которая позволяет отображать `CTaskDialog` без явного создания `CTaskDialog` объекта.  
  
 Второй конструктор создает кнопку командные элементы управления, используя данные из файла ресурсов приложения. Таблица строк в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Этот метод добавляет элемент управления кнопки команд для всех действительных записей в таблице строк между *nIDCommandControlsFirst* и *nCommandControlsLast*включительно. Для этих элементов управления кнопки команд строка в таблице строк имеет заголовок элемента управления и идентификатор строки является идентификатором элемента управления.  
  
 См. в разделе [CTaskDialog::SetOptions](#setoptions) список допустимых параметров.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="domodal"></a>  CTaskDialog::DoModal  
 Показывает `CTaskDialog` и делает его модальным.  
  
```  
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Параметры  
 [in] *hParent*  
 Родительское окно для `CTaskDialog`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, соответствующее выбора, сделанного пользователем.  
  
### <a name="remarks"></a>Примечания  
 Отображает данный экземпляр [CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Затем приложение ожидает от пользователя закрыть диалоговое окно.  
  
 `CTaskDialog` Закрывается, когда пользователь выбирает общие кнопки, элемент управления command link, или закрывает `CTaskDialog`. Возвращает значение идентификатора, указывающее, каким образом пользователь закрыл диалоговое окно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getcommonbuttoncount"></a>  CTaskDialog::GetCommonButtonCount  
 Извлекает число общих кнопок.  
  
```  
int GetCommonButtonCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число доступных общих кнопок.  
  
### <a name="remarks"></a>Примечания  
 Стандартные кнопки находятся кнопки по умолчанию, который предоставляется [CTaskDialog::CTaskDialog](#ctaskdialog). [Класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) отображает кнопки внизу диалогового окна.  
  
 Нумерованный список кнопок предоставляется в файле CommCtrl.h.  
  
##  <a name="getcommonbuttonflag"></a>  CTaskDialog::GetCommonButtonFlag  
 Преобразует стандартной кнопки Windows в общий тип кнопки связан [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md).  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nButtonId*  
 Стандартное значение кнопки Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение соответствующего `CTaskDialog` общие кнопки. Если отсутствует соответствующий кнопка "Общие", этот метод возвращает 0.  
  
##  <a name="getcommonbuttonid"></a>  CTaskDialog::GetCommonButtonId  
 Преобразует один из распространенных типов кнопки, связанных с [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) к стандартной кнопки Windows.  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *снять пометку со*  
 Общий тип кнопки связан `CTaskDialog` класса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение соответствующего стандартной кнопки Windows. Если нет соответствующей кнопки Windows, метод возвращает 0.  
  
##  <a name="getoptions"></a>  CTaskDialog::GetOptions  
 Возвращает флаги параметров для этого `CTaskDialog`.  
  
```  
int GetOptions() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Флаги для `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о параметрах, доступных для [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md), см. в разделе [CTaskDialog::SetOptions](#setoptions).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getselectedcommandcontrolid"></a>  CTaskDialog::GetSelectedCommandControlID  
 Возвращает выбранный элемент управления.  
  
```  
int GetSelectedCommandControlID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор элемента управления button текущей выбранной команды.  
  
### <a name="remarks"></a>Примечания  
 У вас нет для использования этого метода для получения идентификатора кнопки, выбранного пользователем. Этот идентификатор, возвращаемый методом [CTaskDialog::DoModal](#domodal) или [CTaskDialog::ShowDialog](#showdialog).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="getselectedradiobuttonid"></a>  CTaskDialog::GetSelectedRadioButtonID  
 Возвращает выбранного переключателя.  
  
```  
int GetSelectedRadioButtonID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор выбранного переключателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать после пользователь закрывает диалоговое окно для получения выбранного переключателя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="getverificationcheckboxstate"></a>  CTaskDialog::GetVerificationCheckboxState  
 Получает состояние флажка проверки.  
  
```  
BOOL GetVerificationCheckboxState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если флажок установлен, FALSE, если это не так.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="iscommandcontrolenabled"></a>  CTaskDialog::IsCommandControlEnabled  
 Определяет, включен ли элемент управления кнопки команд или кнопки.  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор команды управления "Кнопка" или кнопку для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если элемент управления включен; FALSE, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать для определения доступности как кнопка командные элементы управления и общих кнопок `CTaskDialog` класс *.  
  
 Если *nCommandControlID* , не является допустимым идентификатором для либо общий `CTaskDialog` кнопку или кнопку, этот метод создает исключение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="isradiobuttonenabled"></a>  CTaskDialog::IsRadioButtonEnabled  
 Определяет, включен ли параметр типа "переключатель".  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRadioButtonID*  
 Идентификатор переключателя для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переключатель включен, FALSE, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Если *nRadioButtonID* не является допустимым идентификатором для типа "переключатель" Этот метод создает исключение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="issupported"></a>  CTaskDialog::IsSupported  
 Определяет, поддерживает ли компьютер, на котором выполняется приложение `CTaskDialog`.  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если компьютеры поддерживают `CTaskDialog`; Значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для определения во время выполнения, если компьютер, на котором выполняется приложение поддерживает `CTaskDialog` класса. Если компьютер не поддерживает `CTaskDialog`, следует предоставить другой способ передачи информации пользователю. Приложение аварийно, если предпринимается попытка использовать `CTaskDialog` на компьютере, который не поддерживает `CTaskDialog` класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="loadcommandcontrols"></a>  CTaskDialog::LoadCommandControls  
 Добавляет кнопку командные элементы управления, используя данные из таблицы строки.  
  
```  
void LoadCommandControls(
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nIDCommandControlsFirst*  
 Идентификатор строки первой команды.  
  
 [in] *nIDCommandControlsLast*  
 Идентификатор строки последней команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает кнопку командные элементы управления, используя данные из файла ресурсов приложения. Таблица строк в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Команда кнопки добавлены новые элементы управления с помощью этого метода использовать строку для заголовка элемента управления и идентификатор строки для идентификатора элемента управления. Диапазон строк, выбранных обеспечивается *nIDCommandControlsFirst* и *nCommandControlsLast*включительно. Если в диапазоне пустую запись, метод не добавляет элемент управления кнопки команд для этой записи.  
  
 По умолчанию новые элементы управления кнопки команды включены и не требуется повышение прав.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="loadradiobuttons"></a>  CTaskDialog::LoadRadioButtons  
 Добавляет переключателей, используя данные из таблицы строки.  
  
```  
void LoadRadioButtons(
    int nIDRadioButtonsFirst,  
    int nIDRadioButtonsLast);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nIDRadioButtonsFirst*  
 Идентификатор строки для первого переключателя.  
  
 [in] *nIDRadioButtonsLast*  
 Идентификатор строки от последнее переключателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает переключателей, используя данные из файла ресурсов приложения. Таблица строк в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Новый переключателей, добавленных с помощью этого метода использовать строку для заголовка переключателя и идентификатор строки для идентификатора переключателя. Диапазон строк, выбранных обеспечивается *nIDRadioButtonsFirst* и *nRadioButtonsLast*включительно. Если в диапазоне пустую запись, метод не добавляет типа "переключатель" для этой записи.  
  
 По умолчанию включены новые переключатели.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="navigateto"></a>  CTaskDialog::NavigateTo  
 Передает фокус на другой `CTaskDialog`.  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *oTaskDialog*  
 `CTaskDialog` , Получает фокус.  
  
### <a name="remarks"></a>Примечания  
 Этот метод скрывает текущего `CTaskDialog` при его отображении *oTaskDialog*. *OTaskDialog* отображается в том же расположении, что и текущий `CTaskDialog`.  
  
##  <a name="oncommandcontrolclick"></a>  CTaskDialog::OnCommandControlClick  
 Этот метод вызывается платформой, когда пользователь нажимает кнопку.  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор элемент управления, выбранного пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="oncreate"></a>  CTaskDialog::OnCreate  
 Платформа вызывает этот метод после создания `CTaskDialog`.  
  
```  
virtual HRESULT OnCreate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="ondestroy"></a>  CTaskDialog::OnDestroy  
 Этот метод вызывается платформой непосредственно перед уничтожает `CTaskDialog`.  
  
```  
virtual HRESULT OnDestroy();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="onexpandbuttonclick"></a>  CTaskDialog::OnExpandButtonClick  
 Этот метод вызывается платформой, когда пользователь нажимает кнопку «расширения».  
  
```  
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bExpanded*  
 Ненулевое значение указывает, что отображается нужные дополнительные данные; 0 указывает, что эти дополнительные данные скрыты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="onhelp"></a>  CTaskDialog::OnHelp  
 Этот метод вызывается платформой, когда пользователь запросит справку.  
  
```  
virtual HRESULT OnHelp();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="onhyperlinkclick"></a>  CTaskDialog::OnHyperlinkClick  
 Этот метод вызывается платформой, когда пользователь щелкает гиперссылку.  
  
```  
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *strHref*  
 Строка, представляющая гиперссылки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) прежде, чем возвращает значение S_OK.  
  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="oninit"></a>  CTaskDialog::OnInit  
 Этот метод вызывается платформой при `CTaskDialog` инициализируется.  
  
```  
virtual HRESULT OnInit();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="onnavigatepage"></a>  CTaskDialog::OnNavigatePage  
 Этот метод вызывается платформой в ответ на [CTaskDialog::NavigateTo](#navigateto) метод.  
  
```  
virtual HRESULT OnNavigatePage();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="onradiobuttonclick"></a>  CTaskDialog::OnRadioButtonClick  
 Этот метод вызывается платформой, когда пользователь выбирает элемент управления переключателя.  
  
```  
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRadioButtonID*  
 Идентификатор переключателя, который был щелкнут пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="ontimer"></a>  CTaskDialog::OnTimer  
 Этот метод вызывается платформой, по истечении срока действия таймера.  
  
```  
virtual HRESULT OnTimer(long lTime);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lTime*  
 Время в миллисекундах с момента `CTaskDialog` был создан или сброса таймера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="onverificationcheckboxclick"></a>  CTaskDialog::OnVerificationCheckboxClick  
 Этот метод вызывается платформой, когда пользователь щелкает флажок проверки.  
  
```  
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bChecked*  
 Значение TRUE указывает, что установлен флажок проверки; Значение FALSE указывает, что это не так.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="removeallcommandcontrols"></a>  CTaskDialog::RemoveAllCommandControls  
 Удаляет все элементы кнопки команды из `CTaskDialog`.  
  
```  
void RemoveAllCommandControls();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="removeallradiobuttons"></a>  CTaskDialog::RemoveAllRadioButtons  
 Удаляет всех переключателей из `CTaskDialog`.  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setcommandcontroloptions"></a>  CTaskDialog::SetCommandControlOptions  
 Обновляет элемент управления кнопки команд на `CTaskDialog`.  
  
```  
void SetCommandControlOptions(
    int nCommandControlID,  
    BOOL bEnabled,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор элемента управления команду для обновления.  
  
 [in] *bEnabled*  
 Логический параметр, который указывает, включен ли указанный элемент управления.  
  
 [in] *bRequiresElevation*  
 Логический параметр, который указывает, если указанный элемент управления требуется повышение прав.  
  
### <a name="remarks"></a>Примечания  
 Этот метод позволяет изменить кнопку включен, или требуется повышение прав, после его добавления к `CTaskDialog` класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setcommonbuttonoptions"></a>  CTaskDialog::SetCommonButtonOptions  
 Обновляет подмножество стандартные кнопки включения и требуется повышение Полномочий.  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nDisabledButtonMask*  
 Маска для стандартные кнопки для отключения.  
  
 [in] *nElevationButtonMask*  
 Маска для общих кнопок, которые требуют повышения прав.  
  
### <a name="remarks"></a>Примечания  
 Можно задать общие кнопки, доступные для экземпляра [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) с помощью конструктора [CTaskDialog::CTaskDialog](#ctaskdialog) и метод [CTaskDialog::SetCommonButtons ](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` не поддерживает добавление новых общих кнопок.  
  
 При использовании этого метода для отключения или повысить распространенных кнопку, которая не поддерживается для этого `CTaskDialog`, этот метод создает исключение с помощью [убедитесь, ЧТО](diagnostic-services.md#ensure) макрос.  
  
 Этот метод позволяет любая кнопка, которая доступна для `CTaskDialog` , но не находится в *nDisabledButtonMask*, даже если оно было отключено. Этот метод обрабатывает повышения прав, так же, как: она записывает стандартные кнопки, как не требующие повышения прав, если кнопка «Общие» доступны, но не включен в *nElevationButtonMask*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcommonbuttons"></a>  CTaskDialog::SetCommonButtons  
 Добавляет стандартные кнопки для `CTaskDialog`.  
  
```  
void SetCommonButtons(
    int nButtonMask,  
    int nDisabledButtonMask = 0,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nButtonMask*  
 Маска из кнопок, чтобы добавить `CTaskDialog`.  
  
 [in] *nDisabledButtonMask*  
 Маска из кнопок, чтобы отключить.  
  
 [in] *nElevationButtonMask*  
 Маска кнопок, которые требуют повышения прав.  
  
### <a name="remarks"></a>Примечания  
 Этот метод нельзя вызывать после отображения окна для данного экземпляра `CTaskDialog` создается класс. В противном случае этот метод вызывает исключение.  
  
 Указывает кнопки *nButtonMask* переопределить любые стандартные кнопки, ранее добавленных `CTaskDialog`. Указано только кнопки в *nButtonMask* доступны.  
  
 Если параметр *nDisabledButtonMask* или *nElevationButtonMask* содержат кнопку, которая не находится в *nButtonMask*, этот метод создает исключение с помощью [Убедитесь, ЧТО](diagnostic-services.md#ensure) макрос.  
  
 По умолчанию все стандартные кнопки включены и не требуется повышение прав.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcontent"></a>  CTaskDialog::SetContent  
 Обновляет содержимое `CTaskDialog`.  
  
```  
void SetContent(const CString& strContent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *strContent*  
 Строка для отображения пользователю.  
  
### <a name="remarks"></a>Примечания  
 Содержание `CTaskDialog` класс — это текст, отображаемый пользователю в области основного окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setdefaultcommandcontrol"></a>  CTaskDialog::SetDefaultCommandControl  
 Указывает элемент управления по умолчанию.  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор элемент управления по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления по умолчанию является элемент управления, который является выбираемый, когда `CTaskDialog` сначала отображаются пользователю.  
  
 Этот метод создает исключение, если не удается найти элемент управления, определяемое *nCommandControlID*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setdefaultradiobutton"></a>  CTaskDialog::SetDefaultRadioButton  
 Указывает значение по умолчанию переключателя.  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRadioButtonID*  
 Идентификатор переключателя по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию переключатель является кнопкой, выбираемый, когда `CTaskDialog` сначала отображаются пользователю.  
  
 Этот метод создает исключение, если не удается найти переключатель, определяемое *nRadioButtonID*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setdialogwidth"></a>  CTaskDialog::SetDialogWidth  
 Корректирует ширину `CTaskDialog`.  
  
```  
void SetDialogWidth(int nWidth = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nWidth*  
 Ширина диалогового окна в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Параметр *nWidth* должно быть больше или равно 0. В противном случае этот метод создает исключение.  
  
 Если *nWidth* имеет значение 0, этот метод наборов, диалоговое окно, показанное размер по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setexpansionarea"></a>  CTaskDialog::SetExpansionArea  
 Обновляет область расширения `CTaskDialog`.  
  
```  
void SetExpansionArea(
    const CString& strExpandedInformation,  
    const CString& strCollapsedLabel = _T(""),  
    const CString& strExpandedLabel = _T(""));
```  
  
### <a name="parameters"></a>Параметры  
 [in] *strExpandedInformation*  
 Строка, `CTaskDialog` отображает в основном тексте диалогового окна, когда пользователь нажимает кнопку расширения.  
  
 [in] *strCollapsedLabel*  
 Строка, `CTaskDialog` отображается рядом с кнопкой расширения, когда Развернутая область свернута.  
  
 [in] *strExpandedLabel*  
 Строка, `CTaskDialog` отображается рядом с кнопкой расширения при отображении Развернутая область.  
  
### <a name="remarks"></a>Примечания  
 Область расширения `CTaskDialog` класс позволяет предоставить пользователю Дополнительные сведения. Область расширения находится в основной части `CTaskDialog`, находящийся непосредственно под заголовок и содержимое строки.  
  
 Когда `CTaskDialog` является первым отображается, он не содержит расширенные сведения и помещает `strCollapsedLabel` рядом с кнопкой расширения. Когда пользователь нажимает кнопку расширения, `CTaskDialog` отображает *strExpandedInformation* и изменяет метку для *strExpandedLabel*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootericon"></a>  CTaskDialog::SetFooterIcon  
 Обновляет значок нижнего колонтитула `CTaskDialog`.  
  
```  
void SetFooterIcon(HICON hFooterIcon);  
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *hFooterIcon*  
 Значок "Создать" для `CTaskDialog`.  
  
 [in] *lpszFooterIcon*  
 Значок "Создать" для `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
 Значок нижнего колонтитула отображается в нижней части [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Он может быть связано текст нижнего колонтитула. Можно изменить текст нижнего колонтитула с [CTaskDialog::SetFooterText](#setfootertext).  
  
 Этот метод создает исключение с [убедитесь, ЧТО](diagnostic-services.md#ensure) макрос Если `CTaskDialog` отображается или входной параметр имеет значение NULL.  
  
 Объект `CTaskDialog` могут принимать только `HICON` или `LPCWSTR` как значок нижнего колонтитула. Этот номер настраивается при установке TDF_USE_HICON_FOOTER в конструктор или [CTaskDialog::SetOptions](#setoptions). По умолчанию `CTaskDialog` настроен для использования `LPCWSTR` как тип входных данных для нижнего колонтитула значка. Этот метод создает исключение при попытке задать значок, с помощью неподходящего типа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootertext"></a>  CTaskDialog::SetFooterText  
 Обновляет текст в нижнем колонтитуле `CTaskDialog`.  
  
```  
void SetFooterText(const CString& strFooterText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *strFooterText*  
 Новый текст для нижнего колонтитула.  
  
### <a name="remarks"></a>Примечания  
 Значок нижнего колонтитула отображается рядом с текстом нижнего колонтитула в нижней части `CTaskDialog`. Можно изменить значок нижнего колонтитула с [CTaskDialog::SetFooterIcon](#setfootericon).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmainicon"></a>  CTaskDialog::SetMainIcon  
 Обновляет главного значка `CTaskDialog`.  
  
```  
void SetMainIcon(HICON hMainIcon);  
void SetMainIcon(LPCWSTR lpszMainIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *hMainIcon*  
 Значок "Создать".  
  
 [in] *lpszMainIcon*  
 Значок "Создать".  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [убедитесь, ЧТО](diagnostic-services.md#ensure) макрос Если `CTaskDialog` отображается или входной параметр имеет значение NULL.  
  
 Объект `CTaskDialog` могут принимать только `HICON` или `LPCWSTR` как главный значок. Это можно настроить, задав параметр TDF_USE_HICON_MAIN в конструкторе или в [CTaskDialog::SetOptions](#setoptions) метод. По умолчанию `CTaskDialog` настроен для использования `LPCWSTR` как тип входных данных для главного значка. Этот метод создает исключение при попытке задать значок, с помощью неподходящего типа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmaininstruction"></a>  CTaskDialog::SetMainInstruction  
 Обновляет основные инструкция `CTaskDialog`.  
  
```  
void SetMainInstruction(const CString& strInstructions);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *strInstructions*  
 Новые основные инструкции.  
  
### <a name="remarks"></a>Примечания  
 Основные инструкции из `CTaskDialog` класс является текст, отображаемый для пользователя крупным полужирным шрифтом. Он находится в диалоговом окне под заголовком окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setoptions"></a>  CTaskDialog::SetOptions  
 Служит для настройки параметров для `CTaskDialog`.  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nOptionFlag*  
 Набор флагов, используемых для `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод очищает все текущие параметры для `CTaskDialog`. Чтобы сохранить текущие параметры, сначала нужно получить их с [CTaskDialog::GetOptions](#getoptions) и объединить их с параметрами, которые вы хотите установить.  
  
 В следующей таблице перечислены все допустимые значения.  
  
 TDF_ENABLE_HYPERLINKS  
 Позволяет гиперссылок в `CTaskDialog`.  
  
 TDF_USE_HICON_MAIN  
 Настраивает `CTaskDialog` использовать `HICON` для главного значка. Альтернативой является использование `LPCWSTR`.  
  
 TDF_USE_HICON_FOOTER  
 Настраивает `CTaskDialog` использовать `HICON` значок нижнего колонтитула. Альтернативой является использование `LPCWSTR`.  
  
 TDF_ALLOW_DIALOG_CANCELLATION  
 Позволяет пользователю закрыть `CTaskDialog` с помощью клавиатуры или с помощью значка в правом верхнем углу диалогового окна, даже если **отменить** кнопка неактивна. Если этот флаг не установлен и **отменить** кнопка неактивна, пользователь не может закрыть диалоговое окно с помощью клавиши Alt + F4, нажмите клавишу ESC, или строке заголовка кнопку Закрыть.  
  
 TDF_USE_COMMAND_LINKS  
 Настраивает `CTaskDialog` использовать командные элементы управления кнопки.  
  
 TDF_USE_COMMAND_LINKS_NO_ICON  
 Настраивает `CTaskDialog` использовать элементы управления кнопки команды без отображения значка рядом с элементом управления. TDF_USE_COMMAND_LINKS переопределяет TDF_USE_COMMAND_LINKS_NO_ICON.  
  
 TDF_EXPAND_FOOTER_AREA  
 Указывает, что в настоящее время развернута область расширения.  
  
 TDF_EXPANDED_BY_DEFAULT  
 Определяет, развернута ли область расширения по умолчанию.  
  
 TDF_VERIFICATION_FLAG_CHECKED  
 Указывает, что в настоящее время установлен флажок проверки.  
  
 TDF_SHOW_PROGRESS_BAR  
 Настраивает `CTaskDialog` для отображения индикатор хода выполнения.  
  
 TDF_SHOW_MARQUEE_PROGRESS_BAR  
 Настраивает индикатор хода выполнения, чтобы быть индикатор выполнения. Если включить этот параметр, необходимо задать TDF_SHOW_PROGRESS_BAR иметь ожидаемое поведение.  
  
 TDF_CALLBACK_TIMER  
 Указывает, что `CTaskDialog` интервал обратного вызова имеет значение приблизительно 200 миллисекунд.  
  
 TDF_POSITION_RELATIVE_TO_WINDOW  
 Настраивает `CTaskDialog` должен быть отцентрован относительно родительского окна. Если этот флаг не включена, `CTaskDialog` центрируется относительно монитор.  
  
 TDF_RTL_LAYOUT  
 Настраивает `CTaskDialog` для чтения справа налево.  
  
 TDF_NO_DEFAULT_RADIO_BUTTON  
 Указывает, что нет переключателя при `CTaskDialog` отображается.  
  
 TDF_CAN_BE_MINIMIZED  
 Позволяет свести к минимуму `CTaskDialog`. Для поддержки этого параметра `CTaskDialog` не может быть модальным. MFC не поддерживают этот параметр, так как MFC поддерживает немодальный `CTaskDialog`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setprogressbarmarquee"></a>  CTaskDialog::SetProgressBarMarquee  
 Настраивает индикатора для `CTaskDialog` и добавляет его в диалоговое окно.  
  
```  
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,  
    int nMarqueeSpeed = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnabled*  
 Значение TRUE, чтобы включить в виде бегущей строки; Значение FALSE, чтобы отключить в виде бегущей строки и удалите его из `CTaskDialog`.  
  
 [in] *nMarqueeSpeed*  
 Целое число, указывающее скорость в виде бегущей строки.  
  
### <a name="remarks"></a>Примечания  
 Отображается в виде бегущей строки под основной текст `CTaskDialog` класса.  
  
 Используйте *nMarqueeSpeed* скорости в виде бегущей строки; большие значения указывают более низкой скорости. Значение 0 для *nMarqueeSpeed* делает перемещения со скоростью по умолчанию для Windows в виде бегущей строки.  
  
 Этот метод создает исключение с [убедитесь, ЧТО](diagnostic-services.md#ensure) макрос Если *nMarqueeSpeed* меньше 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarposition"></a>  CTaskDialog::SetProgressBarPosition  
 Регулирует положение индикатора выполнения.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nProgressPos*  
 Положение индикатора выполнения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [убедитесь, ЧТО](diagnostic-services.md#ensure) макрос Если *nProgressPos* не находится в диапазоне панели хода выполнения. Вы можете изменить диапазон панель хода выполнения с [CTaskDialog::SetProgressBarRange](#setprogressbarrange).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarrange"></a>  CTaskDialog::SetProgressBarRange  
 Настройка диапазона индикатора.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRangeMin*  
 Нижняя граница индикатора хода выполнения.  
  
 [in] *nRangeMax*  
 Верхняя граница индикатора хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Положение индикатора выполнения определяется относительно *nRangeMin* и *nRangeMax*. Например если *nRangeMin* равно 50 и *nRangeMax* — 100, позиция 75 находится на равном расстоянии вдоль индикатора. Используйте [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) Чтобы установить позицию индикатора хода выполнения.  
  
 Чтобы отобразить индикатор выполнения, параметр TDF_SHOW_PROGRESS_BAR должна быть включена и TDF_SHOW_MARQUEE_PROGRESS_BAR не включается. Этот метод автоматически задает TDF_SHOW_PROGRESS_BAR и очищает TDF_SHOW_MARQUEE_PROGRESS_BAR. Используйте [CTaskDialog::SetOptions](#setoptions) Чтобы вручную изменить параметры для данного экземпляра [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md).  
  
 Этот метод создает исключение с [убедитесь, ЧТО](diagnostic-services.md#ensure) макрос Если *nRangeMin* — не меньше *nRangeMax*. Этот метод также создает исключение, если `CTaskDialog` уже отображается и имеет индикатор выполнения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarstate"></a>  CTaskDialog::SetProgressBarState  
 Задает состояние индикатора хода выполнения и отображает его на `CTaskDialog`.  
  
```  
void SetProgressBarState(int nState = PBST_NORMAL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nState*  
 Состояние индикатора хода выполнения. Возможные значения в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [убедитесь, ЧТО](diagnostic-services.md#ensure) макрос Если `CTaskDialog` уже отображается и имеет индикатор выполнения.  
  
 В следующей таблице перечислены возможные значения для *nState*. Во всех этих случаях индикатор хода выполнения будет заливка цветом регулярных пока не достигнет позиции указанного табуляции. После этого он будет меняться на основе состояния.  
  
 PBST_NORMAL  
 После ход выполнения заполнится, `CTaskDialog` не изменяет цвет строки. По умолчанию регулярные цвет имеет зеленый цвет.  
  
 PBST_ERROR  
 После ход выполнения заполнится, `CTaskDialog` изменяется цвет полосы к ошибке. По умолчанию это красный.  
  
 PBST_PAUSED  
 После ход выполнения заполнится, `CTaskDialog` изменяется цвет панели к приостановлена. По умолчанию это желтый.  
  
 Можно задать место прекращения индикатор хода выполнения с [CTaskDialog::SetProgressBarPosition](#setprogressbarposition).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setradiobuttonoptions"></a>  CTaskDialog::SetRadioButtonOptions  
 Включает или отключает переключатель.  
  
```  
void SetRadioButtonOptions(
    int nRadioButtonID,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRadioButtonID*  
 Идентификатор переключателя.  
  
 [in] *bEnabled*  
 Значение TRUE, чтобы включить переключатель; Значение FALSE, чтобы отключить кнопку-переключатель.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [убедитесь, ЧТО](diagnostic-services.md#ensure) макрос Если *nRadioButtonID* не является допустимым Идентификатором для типа "переключатель".  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setverificationcheckbox"></a>  CTaskDialog::SetVerificationCheckbox  
 Задает состояние флажка проверки.  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bChecked*  
 Значение true для проверки флажок выбора при `CTaskDialog` отображается; Значение FALSE, чтобы иметь верификации флажок снят, когда `CTaskDialog` отображается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setverificationcheckboxtext"></a>  CTaskDialog::SetVerificationCheckboxText  
 Задает текст, который отображается справа от флажка проверки.  
  
```  
void SetVerificationCheckboxText(CString& strVerificationText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *strVerificationText*  
 Текст, этот метод отображает рядом с флажком проверки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [убедитесь, ЧТО](diagnostic-services.md#ensure) макрос, если данный экземпляр `CTaskDialog` класс уже отображается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setwindowtitle"></a>  CTaskDialog::SetWindowTitle  
 Задает название `CTaskDialog`.  
  
```  
void SetWindowTitle(CString& strWindowTitle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *strWindowTitle*  
 Новый заголовок для `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="showdialog"></a>  CTaskDialog::ShowDialog  
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
 [in] *strContent*  
 Строка, используемая для содержимого `CTaskDialog`.  
  
 [in] *strMainInstruction*  
 Основные инструкции из `CTaskDialog`.  
  
 [in] *strTitle*  
 Название `CTaskDialog`.  
  
 [in] *nIDCommandControlsFirst*  
 Идентификатор строки первой команды.  
  
 [in] *nIDCommandControlsLast*  
 Идентификатор строки последней команды.  
  
 [in] *nCommonButtons*  
 Маска из кнопок, чтобы добавить `CTaskDialog`.  
  
 [in] *nTaskDialogOptions*  
 Набор параметров для `CTaskDialog`.  
  
 [in] *strFooter*  
 Строка для использования в качестве нижнего колонтитула.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, соответствующее выбора, сделанного пользователем.  
  
### <a name="remarks"></a>Примечания  
 Этот статический метод позволяет создавать экземпляр `CTaskDialog` класса без явного создания `CTaskDialog` объекта в коде. Так как не `CTaskDialog` объекта, не может вызывать остальные методы из `CTaskDialog` при использовании этого метода для отображения `CTaskDialog` для пользователя.  
  
 Этот метод создает кнопку командные элементы управления, используя данные из файла ресурсов приложения. Таблица строк в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Этот метод добавляет элемент управления кнопки команд для всех действительных записей в таблице строк между *nIDCommandControlsFirst* и *nCommandControlsLast*включительно. Для этих элементов управления кнопки команд строка в таблице строк имеет заголовок элемента управления и идентификатор строки является идентификатором элемента управления.  
  
 См. в разделе [CTaskDialog::SetOptions](#setoptions) список допустимых параметров.  
  
 `CTaskDialog` Закрывается, когда пользователь выбирает общие кнопки, элемент управления command link, или закрывает `CTaskDialog`. Возвращает значение идентификатора, указывающее, каким образом пользователь закрыл диалоговое окно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="taskdialogcallback"></a>  CTaskDialog::TaskDialogCallback  
 Этот метод вызывается платформой в ответ на различные сообщения Windows.  
  
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
 [in] *hwnd*  
 Дескриптор `m_hWnd` структуры для `CTaskDialog`.  
  
 [in] *uNotification*  
 Код уведомления, которое указывает сообщение, созданный.  
  
 [in] *wParam*  
 Дополнительные сведения о сообщении.  
  
 [in] *lParam*  
 Дополнительные сведения о сообщении.  
  
 [in] *dwRefData*  
 Указатель на `CTaskDialog` объект, к которому применяется сообщения обратного вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Зависит от кода уведомления. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию `TaskDialogCallback` обрабатывает конкретное сообщение и затем вызывает соответствующий метод [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Например, в ответ на сообщение TDN_BUTTON_CLICKED `TaskDialogCallback` вызовы [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick).  
  
 Значения для *wParam* и *lParam* зависят от конкретного формируемое сообщение. Вполне возможно, для одного или обоих этих значений в быть пустым. В следующей таблице перечислены уведомлений по умолчанию, которые поддерживаются и какие значения *wParam* и *lParam* представления. Если вы Переопределите этот метод в производном классе, необходимо реализовать код обратного вызова для каждого сообщения в следующей таблице.  
  
|Сообщение уведомления|*wParam* значение|*lParam* значение|  
|--------------------------|--------------------|--------------------|  
|TDN_CREATED|Не используется.|Не используется.|  
|TDN_NAVIGATED|Не используется.|Не используется.|  
|TDN_BUTTON_CLICKED|Кнопки идентификатора элемента управления.|Не используется.|  
|TDN_HYPERLINK_CLICKED|Не используется.|Объект [LPCWSTR](http://msdn.microsoft.com/library/windows/desktop/aa383751) структуру, содержащую ссылку.|  
|TDN_TIMER|Время в миллисекундах с момента `CTaskDialog` был создан или сброса таймера.|Не используется.|  
|TDN_DESTROYED|Не используется.|Не используется.|  
|TDN_RADIO_BUTTON_CLICKED|Идентификатор кнопки радио|Не используется.|  
|TDN_DIALOG_CONSTRUCTED|Не используется.|Не используется.|  
|TDN_VERIFICATION_CLICKED|1, если флажок установлен, 0, если это не так.|Не используется.|  
|TDN_HELP|Не используется.|Не используется.|  
|TDN_EXPANDO_BUTTON_CLICKED|0, если область расширения свернута; ненулевое значение, если отображается текст расширения.|Не используется.|  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CObject](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Пошаговое руководство. Добавление CTaskDialog в приложение](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)



