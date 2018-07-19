---
title: Класс CTaskDialog | Документы Microsoft
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
ms.openlocfilehash: 2971293a61a662b789506bbc32923089097f962d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123218"
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
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|Добавляет элемент управления button команды для `CTaskDialog`.|  
|[CTaskDialog::AddRadioButton](#addradiobutton)|Добавляет переключатель, чтобы `CTaskDialog`.|  
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Нажимает кнопку или общие кнопку программными средствами.|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Щелкает переключатель программными средствами.|  
|[CTaskDialog::DoModal](#domodal)|Отображает `CTaskDialog`.|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|Возвращает число доступных общих кнопок.|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Преобразует стандартной кнопки Windows в общий тип кнопки связанные с `CTaskDialog` класса.|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|Преобразует один из распространенных типов кнопки, связанные с `CTaskDialog` класса для стандартной кнопки Windows.|  
|[CTaskDialog::GetOptions](#getoptions)|Возвращает флаги параметров для этого `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|Возвращает выбранный элемент управления.|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Возвращает выбранного переключателя.|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|Получает состояние флажка проверки.|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Определяет, включен ли переключатель или общие кнопки.|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|Определяет, включен ли переключатель.|  
|[CTaskDialog::IsSupported](#issupported)|Определяет, поддерживает ли компьютер, на котором выполняется приложение `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Добавляет команды управления "Кнопка", используя данные из таблицы строки.|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|Добавление переключателей, используя данные из строки таблицы.|  
|[CTaskDialog::NavigateTo](#navigateto)|Для перемещения фокуса в другую `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Этот метод вызывается платформой, когда пользователь нажимает кнопку.|  
|[CTaskDialog::OnCreate](#oncreate)|Платформа вызывает этот метод после создания `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](#ondestroy)|Этот метод вызывается платформой непосредственно перед уничтожает `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|Этот метод вызывается платформой при нажатии на кнопку расширения.|  
|[CTaskDialog::OnHelp](#onhelp)|Этот метод вызывается платформой при запросе справки.|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|Этот метод вызывается платформой, когда пользователь щелкает гиперссылку.|  
|[CTaskDialog::OnInit](#oninit)|Этот метод вызывается платформой при `CTaskDialog` инициализируется.|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Платформа вызывает этот метод, когда пользователь перемещает фокус по отношению к элементам управления `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|Этот метод вызывается платформой, когда пользователь выбирает элемент управления переключателя.|  
|[CTaskDialog::OnTimer](#ontimer)|Платформа вызывает этот метод после истечения срока действия таймера.|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|Этот метод вызывается платформой, когда пользователь щелкает флажок проверки.|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Удаляет все элементы из команды `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Удаляет все переключатели из `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Обновляет кнопку на `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|Обновляет подмножество общих кнопки, чтобы включить и требуется повышение уровня контроля учетных Записей.|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|Добавляет общие кнопки `CTaskDialog`.|  
|[CTaskDialog::SetContent](#setcontent)|Обновляет содержимое `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Указывает элемент управления по умолчанию.|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Указывает переключателя по умолчанию.|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|Корректирует ширину `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|Обновляет область расширения `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|Значок нижнего колонтитула для обновлений `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](#setfootertext)|Обновляет текст в нижнем колонтитуле `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](#setmainicon)|Обновление главного значка `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Обновляет главной инструкции `CTaskDialog`.|  
|[CTaskDialog::SetOptions](#setoptions)|Настраивает параметры для `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|Настраивает индикатора для `CTaskDialog` и добавляет его в диалоговое окно.|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|Изменяет положение индикатора выполнения.|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|Настройка диапазона индикатора хода выполнения.|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|Задает состояние индикатора хода выполнения и отображает его на `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Включает или отключает переключатель.|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|Задает состояние флажка проверки.|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Задает текст справа от флажка проверки.|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Задает заголовок `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](#showdialog)|Создает и отображает `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Платформа вызывает это в ответ на различные сообщения Windows.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|`m_aButtons`|Массив элементов управления кнопок команд для `CTaskDialog`.|  
|`m_aRadioButtons`|Массив переключателей для `CTaskDialog`.|  
|`m_bVerified`|`TRUE` Указывает, что установлен флажок проверки; `FALSE` указывает, это не так.|  
|`m_footerIcon`|Значок в нижнем колонтитуле `CTaskDialog`.|  
|`m_hWnd`|Дескриптор окна для `CTaskDialog`.|  
|`m_mainIcon`|Значок главной `CTaskDialog`.|  
|`m_nButtonDisabled`|Маска, которая указывает, какая из кнопок общих отключены.|  
|`m_nButtonElevation`|Маска, которая указывает, какая из кнопок общих требуется повышение прав контроля учетных Записей.|  
|`m_nButtonId`|Идентификатор элемента управления button выбранную команду.|  
|`m_nCommonButton`|Маска, которая указывает, какие общие кнопки отображаются на `CTaskDialog`.|  
|`m_nDefaultCommandControl`|Идентификатор кнопки элемента управления, при выборе `CTaskDialog` отображается.|  
|`m_nDefaultRadioButton`|Идентификатор переключателя элемента управления, при выборе `CTaskDialog` отображается.|  
|`m_nFlags`|Маска, которая указывает параметры для `CTaskDialog`.|  
|`m_nProgressPos`|Текущее положение индикатора.  Это значение должно принадлежать диапазону от `m_nProgressRangeMin` до `m_nProgressRangeMax`.|  
|`m_nProgressRangeMax`|Максимальное значение для индикатора.|  
|`m_nProgressRangeMin`|Минимальное значение для индикатора.|  
|`m_nProgressState`|Состояние индикатора хода выполнения. Дополнительные сведения см. в разделе [CTaskDialog::SetProgressBarState](#setprogressbarstate).|  
|`m_nRadioId`|Идентификатор выбранного переключателя.|  
|`m_nWidth`|Ширина `CTaskDialog` в пикселях.|  
|`m_strCollapse`|Строка `CTaskDialog` отображается справа от поля расширения скрытого расширенные сведения.|  
|`m_strContent`|Строка содержимого из `CTaskDialog`.|  
|`m_strExpand`|Строка `CTaskDialog` отображается справа от поля расширения при отображении расширенные сведения.|  
|`m_strFooter`|Нижний колонтитул `CTaskDialog`.|  
|`m_strInformation`|Подробные сведения для `CTaskDialog`.|  
|`m_strMainInstruction`|Основные инструкции из `CTaskDialog`.|  
|`m_strTitle`|Заголовок `CTaskDialog`.|  
|`m_strVerification`|Строка, `CTaskDialog` отображается справа от флажка проверки.|  
  
## <a name="remarks"></a>Примечания  
 `CTaskDialog` Класс заменяет стандартные окна сообщения и имеет дополнительные функциональные возможности, такие как новые элементы управления для сбора информации от пользователя. Этот класс находится в библиотеке MFC в [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]. `CTaskDialog` Доступен, начиная с Windows Vista. Более ранние версии Windows не удается отобразить `CTaskDialog` объекта. Используйте `CTaskDialog::IsSupported` во время выполнения определить, может ли текущий пользователь отображать диалоговое окно задачи. Стандартные окна сообщения по-прежнему поддерживается в [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  
  
 `CTaskDialog` Доступен только при создании приложения с помощью библиотеки Юникода.  
  
 `CTaskDialog` Имеет два различных конструкторов. Один конструктор позволяет указать две командные кнопки и максимум шесть элементов управления обычная кнопка. После создания можно добавить дополнительные кнопки `CTaskDialog`. Второй конструктор не поддерживает все кнопки команд, но можно добавлять неограниченное число элементов управления обычная кнопка. Дополнительные сведения о конструкторах см. в разделе [CTaskDialog::CTaskDialog](#ctaskdialog).  
  
 На следующем рисунке показана образец `CTaskDialog` для иллюстрации расположение некоторых элементов управления.  
  
 ![Пример CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
Пример CTaskDialog  
  
## <a name="requirements"></a>Требования  
 **Минимальная требуемая ОС:** Windows Vista  
  
 **Заголовок:** afxtaskdialog.h  
  
##  <a name="addcommandcontrol"></a>  CTaskDialog::AddCommandControl  
 Добавляет новые кнопки команды для `CTaskDialog`.  
  
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
 Логический параметр, указывающее, включено ли «создать».  
  
 [in] *bRequiresElevation*  
 Логический параметр, указывает, требуется ли команда повышения прав.  
  
### <a name="remarks"></a>Примечания  
 `CTaskDialog Class` Может отображать неограниченное число элементов управления кнопки команд. Однако если `CTaskDialog` отобразится любой кнопки элементов управления, он может отображать до шести кнопок. Если `CTaskDialog` нет элементов управления кнопку команды, она может содержать неограниченное количество кнопок.  
  
 Когда пользователь выбирает команду кнопки, `CTaskDialog` закрывается. Если приложение отображает диалоговое окно с помощью [CTaskDialog::DoModal](#domodal), `DoModal` возвращает *nCommandControlID* элемента управления button выбранную команду.  
  
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
 Идентификационный номер переключатель.  
  
 [in] *strCaption*  
 Строка, `CTaskDialog` отображается рядом с "переключатель".  
  
 [in] *bEnabled*  
 Логический параметр, указывает, включен ли переключатель.  
  
### <a name="remarks"></a>Примечания  
 Кнопки переключателя для [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) позволяют собирать сведения от пользователя. Используйте функцию [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) для определения, какой переключатель установлен.  
  
 `CTaskDialog` Не требует *nRadioButtonID* параметры являются уникальными для каждого переключателя. Тем не менее могут испытать неожиданное поведение, если не выполнить уникальные идентификатор для каждого переключателя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="clickcommandcontrol"></a>  CTaskDialog::ClickCommandControl  
 Нажимает кнопку или общие кнопку программными средствами.  
  
```  
protected:  
void ClickCommandControl(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор команды элемента управления, нажмите кнопку.  
  
### <a name="remarks"></a>Примечания  
 Этот метод формирует сообщение windows TDM_CLICK_BUTTON.  
  
##  <a name="clickradiobutton"></a>  CTaskDialog::ClickRadioButton  
 Щелкает переключатель программными средствами.  
  
```  
protected:  
void ClickRadioButton(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRadioButtonID*  
 Идентификатор нажмите кнопку переключателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод формирует сообщение windows TDM_CLICK_RADIO_BUTTON.  
  
##  <a name="ctaskdialog"></a>  CTaskDialog::CTaskDialog  
 Создает экземпляр [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md).  
  
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
 Заголовок `CTaskDialog`.  
  
 [in] *nCommonButtons*  
 Маска общих кнопок, чтобы добавить `CTaskDialog`.  
  
 [in] *nTaskDialogOptions*  
 Набор параметров для `CTaskDialog`.  
  
 [in] *strFooter*  
 Строка для использования в качестве нижнего колонтитула.  
  
 [in] *nIDCommandControlsFirst*  
 Идентификатор первой команды строки.  
  
 [in] *nIDCommandControlsLast*  
 Идентификатор строки последней команды.  
  
### <a name="remarks"></a>Примечания  
 Существует два способа, которые можно добавить `CTaskDialog` в приложение. Первый способ — использовать один из конструкторов для создания `CTaskDialog` и отобразить ее с помощью [CTaskDialog::DoModal](#domodal). Вторым способом является использование статической функции [CTaskDialog::ShowDialog](#showdialog), которая позволяет отображать `CTaskDialog` без явного создания `CTaskDialog` объекта.  
  
 Второй конструктор создает команды управления "Кнопка" с использованием данных из файла ресурсов приложения. Таблица строк в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Этот метод добавляет элемент управления button команды для всех записей в таблице строк между *nIDCommandControlsFirst* и *nCommandControlsLast*включительно. Для этих элементов управления кнопок командной строки в таблице строк является заголовка элемента управления и идентификатор строки является идентификатором элемента управления.  
  
 В разделе [CTaskDialog::SetOptions](#setoptions) список допустимых параметров.  
  
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
 Отображает этот экземпляр [CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Затем приложение ожидает от пользователя закрыть диалоговое окно.  
  
 `CTaskDialog` Закрывается, если пользователь общих нажатие кнопки командую ссылку или закрывает `CTaskDialog`. Возвращаемое значение — идентификатор, который указывает, как пользователь закрыл диалоговое окно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getcommonbuttoncount"></a>  CTaskDialog::GetCommonButtonCount  
 Возвращает число общих кнопок.  
  
```  
int GetCommonButtonCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число доступных общих кнопок.  
  
### <a name="remarks"></a>Примечания  
 Содержит общие кнопки, кнопки по умолчанию, который предоставляется [CTaskDialog::CTaskDialog](#ctaskdialog). [Класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) Перечень кнопок в нижней части окна.  
  
 Нумерованный список кнопок предоставляется в CommCtrl.h.  
  
##  <a name="getcommonbuttonflag"></a>  CTaskDialog::GetCommonButtonFlag  
 Преобразует стандартной кнопки Windows в общий тип кнопки связанные с [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md).  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nButtonId*  
 Значение стандартной кнопки Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение соответствующего `CTaskDialog` общие кнопки. Если отсутствует соответствующий кнопка "Общие", этот метод возвращает 0.  
  
##  <a name="getcommonbuttonid"></a>  CTaskDialog::GetCommonButtonId  
 Преобразует один из распространенных типов кнопки, связанные с [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) для стандартной кнопки Windows.  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nFlag*  
 Общий тип кнопки, связанной с `CTaskDialog` класса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, соответствующие стандартной кнопки Windows. Если отсутствует соответствующий кнопка "Windows", метод возвращает 0.  
  
##  <a name="getoptions"></a>  CTaskDialog::GetOptions  
 Возвращает флаги параметров для этого `CTaskDialog`.  
  
```  
int GetOptions() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Флаги для `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о параметрах, доступных для [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md), в разделе [CTaskDialog::SetOptions](#setoptions).  
  
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
 Необходимо использовать этот метод для получения идентификатора, выбранное пользователем кнопки. Этот идентификатор возвращается либо [CTaskDialog::DoModal](#domodal) или [CTaskDialog::ShowDialog](#showdialog).  
  
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
 Этот метод можно использовать после пользователь закрывает диалоговое окно для извлечения выбранного переключателя.  
  
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
 Определяет, включен ли элемент управления кнопки команды или кнопки.  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор элемента управления кнопки команды или кнопки для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если элемент управления включен, FALSE, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать для определения доступности и кнопки команд и общие кнопок `CTaskDialog` класс *.  
  
 Если *nCommandControlID* , не является допустимым идентификатором либо общий `CTaskDialog` кнопку или кнопку, этот метод создает исключение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="isradiobuttonenabled"></a>  CTaskDialog::IsRadioButtonEnabled  
 Определяет, включен ли переключатель.  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRadioButtonID*  
 Идентификатор "переключатель" для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переключатель включен, FALSE, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Если *nRadioButtonID* не является допустимым идентификатором для типа "переключатель", этот метод создает исключение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="issupported"></a>  CTaskDialog::IsSupported  
 Определяет, поддерживает ли компьютер, на котором выполняется приложение `CTaskDialog`.  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если компьютер поддерживает `CTaskDialog`; Значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для определения во время выполнения, если компьютер, на котором выполняется приложение поддерживает `CTaskDialog` класса. Если компьютер не поддерживает `CTaskDialog`, необходимо предоставить другой метод передачи информации для пользователя. Приложение произойдет сбой при попытке использовать `CTaskDialog` на компьютере, который не поддерживает `CTaskDialog` класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="loadcommandcontrols"></a>  CTaskDialog::LoadCommandControls  
 Добавляет команды управления "Кнопка", используя данные из таблицы строки.  
  
```  
void LoadCommandControls(
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nIDCommandControlsFirst*  
 Идентификатор первой команды строки.  
  
 [in] *nIDCommandControlsLast*  
 Идентификатор строки последней команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает команды управления "Кнопка" с использованием данных из файла ресурсов приложения. Таблица строк в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Команда кнопки добавлены новые элементы управления с помощью этого метода использовать строку для заголовка элемента управления и идентификатор строки для идентификатора элемента управления. Диапазон строк, выбранных обеспечивается *nIDCommandControlsFirst* и *nCommandControlsLast*включительно. Если в диапазоне пустую запись, метод не добавляет командую кнопку для этой записи.  
  
 По умолчанию новые элементы управления кнопки команды включены и не требуется повышение прав.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="loadradiobuttons"></a>  CTaskDialog::LoadRadioButtons  
 Добавление переключателей, используя данные из строки таблицы.  
  
```  
void LoadRadioButtons(
    int nIDRadioButtonsFirst,  
    int nIDRadioButtonsLast);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nIDRadioButtonsFirst*  
 Идентификатор строки для первого переключателя.  
  
 [in] *nIDRadioButtonsLast*  
 Идентификатор строки последнего переключателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает переключателей, используя данные из файла ресурсов приложения. Таблица строк в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Новый переключателей, добавленные с помощью этого метода использовать строку для заголовка "переключатель" и идентификатор строки для идентификатора "переключатель". Диапазон строк, выбранных обеспечивается *nIDRadioButtonsFirst* и *nRadioButtonsLast*включительно. Если в диапазоне пустую запись, метод не добавляет типа "переключатель" для этой записи.  
  
 По умолчанию включены новые переключателей.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="navigateto"></a>  CTaskDialog::NavigateTo  
 Для перемещения фокуса в другую `CTaskDialog`.  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *oTaskDialog*  
 `CTaskDialog` , Получающий фокус.  
  
### <a name="remarks"></a>Примечания  
 Этот метод скрывает текущего `CTaskDialog` при его отображении *oTaskDialog*. *OTaskDialog* отображается в том же расположении, что и текущий `CTaskDialog`.  
  
##  <a name="oncommandcontrolclick"></a>  CTaskDialog::OnCommandControlClick  
 Этот метод вызывается платформой, когда пользователь нажимает кнопку.  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор элемента управления кнопки команд, выбранное пользователем.  
  
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
 Этот метод вызывается платформой при нажатии на кнопку расширения.  
  
```  
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bExpanded*  
 Ненулевое значение указывает, что отображается дополнительный сведения; 0 указывает, что скрытые дополнительных сведений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="onhelp"></a>  CTaskDialog::OnHelp  
 Этот метод вызывается платформой при запросе справки.  
  
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
 Этот метод вызывает метод [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) перед возвращает значение S_OK.  
  
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
 Платформа вызывает этот метод после истечения срока действия таймера.  
  
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
 Удаляет все переключатели из `CTaskDialog`.  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setcommandcontroloptions"></a>  CTaskDialog::SetCommandControlOptions  
 Обновляет кнопку на `CTaskDialog`.  
  
```  
void SetCommandControlOptions(
    int nCommandControlID,  
    BOOL bEnabled,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор команды управления, который требуется обновить.  
  
 [in] *bEnabled*  
 Логический параметр, указывает, включен ли указанный элемент управления.  
  
 [in] *bRequiresElevation*  
 Логический параметр, указывающее, если указанный элемент управления требует повышения прав.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы изменить кнопку включен, или требуется повышение прав, после добавления в `CTaskDialog` класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setcommonbuttonoptions"></a>  CTaskDialog::SetCommonButtonOptions  
 Обновляет подмножество общих кнопки должно быть включено, а также требуется повышение уровня контроля учетных Записей.  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nDisabledButtonMask*  
 Маска для распространенных кнопок, чтобы отключить.  
  
 [in] *nElevationButtonMask*  
 Маска для распространенных кнопок, требующие повышения прав.  
  
### <a name="remarks"></a>Примечания  
 Можно задать общие кнопок, доступных в экземпляр [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) с помощью конструктора [CTaskDialog::CTaskDialog](#ctaskdialog) , а также метод [CTaskDialog::SetCommonButtons ](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` не поддерживает добавление новых общих кнопок.  
  
 При использовании этого метода для отключения или повысить общий кнопки, которая недоступна для данного `CTaskDialog`, этот метод создает исключение с помощью [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос.  
  
 Этот метод позволяет любой кнопки, которая доступна для `CTaskDialog` , но не находится в *nDisabledButtonMask*, даже если оно было отключено. Этот метод обрабатывает повышение аналогичным образом: она записывает общих кнопок как не требующие повышения прав, если кнопка «Общие» доступны, но не включается в *nElevationButtonMask*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcommonbuttons"></a>  CTaskDialog::SetCommonButtons  
 Добавляет общие кнопки `CTaskDialog`.  
  
```  
void SetCommonButtons(
    int nButtonMask,  
    int nDisabledButtonMask = 0,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nButtonMask*  
 Маска кнопок, чтобы добавить `CTaskDialog`.  
  
 [in] *nDisabledButtonMask*  
 Маска для отключения кнопки.  
  
 [in] *nElevationButtonMask*  
 Маска кнопок, требующие повышения прав.  
  
### <a name="remarks"></a>Примечания  
 Этот метод нельзя вызвать после окно отображения для этого экземпляра `CTaskDialog` создается класс. В противном случае этот метод создает исключение.  
  
 Указывает кнопки *nButtonMask* переопределить любые общие кнопок, ранее добавленный `CTaskDialog`. Указано только кнопки в *nButtonMask* доступны.  
  
 Если параметр *nDisabledButtonMask* или *nElevationButtonMask* содержат кнопки, которая не находится в *nButtonMask*, этот метод создает исключение с помощью [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос.  
  
 По умолчанию все общие кнопки включены и не требуется повышение прав.  
  
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
 Содержимое `CTaskDialog` класс — это текст, который отображается для пользователя в основном разделе диалогового окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setdefaultcommandcontrol"></a>  CTaskDialog::SetDefaultCommandControl  
 Указывает элемент управления по умолчанию.  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nCommandControlID*  
 Идентификатор элемента управления кнопки команды по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления по умолчанию — элемент управления, выбранный при `CTaskDialog` сначала отображается для пользователя.  
  
 Этот метод вызывает исключение, если его не удается найти элемент управления, определяемое *nCommandControlID*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setdefaultradiobutton"></a>  CTaskDialog::SetDefaultRadioButton  
 Указывает переключателя по умолчанию.  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRadioButtonID*  
 Идентификатор переключателя по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Переключатель по умолчанию — это кнопка, выбранный при `CTaskDialog` сначала отображается для пользователя.  
  
 Этот метод вызывает исключение, если его не удается найти переключатель, определяемое *nRadioButtonID*.  
  
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
  
 Если *nWidth* имеет значение 0 задает метод диалогового размер по умолчанию.  
  
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
 Строка, `CTaskDialog` отображаются в основном тексте диалогового окна при нажатии пользователем кнопки расширения.  
  
 [in] *strCollapsedLabel*  
 Строка, `CTaskDialog` отображается рядом с кнопкой расширения при расширенном область свернута.  
  
 [in] *strExpandedLabel*  
 Строка, `CTaskDialog` отображается рядом с кнопкой расширения при отображении развернутой области.  
  
### <a name="remarks"></a>Примечания  
 Области расширения `CTaskDialog` позволяет предоставить дополнительные сведения для пользователя. Область расширения отображается в основной части `CTaskDialog`, расположенного непосредственно под заголовком и содержимым строки.  
  
 Когда `CTaskDialog` сначала отображается, он не содержит расширенные сведения и помещает `strCollapsedLabel` рядом с кнопкой расширения. Когда пользователь нажимает кнопку расширения, `CTaskDialog` отображает *strExpandedInformation* и изменяет метку, которая *strExpandedLabel*.  
  
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
 Нижний колонтитул значок отображается в нижней части [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Оно может связано текст нижнего колонтитула. Можно изменять текст нижнего колонтитула с [CTaskDialog::SetFooterText](#setfootertext).  
  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос Если `CTaskDialog` отображается или входной параметр имеет значение NULL.  
  
 Объект `CTaskDialog` может принимать только `HICON` или `LPCWSTR` как значок нижнего колонтитула. Это настраивается путем установки параметра TDF_USE_HICON_FOOTER в конструкторе или [CTaskDialog::SetOptions](#setoptions). По умолчанию `CTaskDialog` настроен на использование `LPCWSTR` качестве типа ввода для значка нижний колонтитул. Этот метод создает исключение при попытке задания с помощью неуместные типа значка.  
  
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
 Нижний колонтитул значок рядом с текстом нижнего колонтитула в нижней части `CTaskDialog`. Можно изменить значок нижнего колонтитула с [CTaskDialog::SetFooterIcon](#setfootericon).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmainicon"></a>  CTaskDialog::SetMainIcon  
 Обновление главного значка `CTaskDialog`.  
  
```  
void SetMainIcon(HICON hMainIcon);  
void SetMainIcon(LPCWSTR lpszMainIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *hMainIcon*  
 Значок «Создать».  
  
 [in] *lpszMainIcon*  
 Значок «Создать».  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос Если `CTaskDialog` отображается или входной параметр имеет значение NULL.  
  
 Объект `CTaskDialog` может принимать только `HICON` или `LPCWSTR` как главный значок. Это можно настроить путем установки параметра TDF_USE_HICON_MAIN в конструкторе или в [CTaskDialog::SetOptions](#setoptions) метод. По умолчанию `CTaskDialog` настроен на использование `LPCWSTR` как тип входных данных для главного значка. Этот метод создает исключение при попытке задания с помощью неуместные типа значка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmaininstruction"></a>  CTaskDialog::SetMainInstruction  
 Обновляет главной инструкции `CTaskDialog`.  
  
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
 Настраивает параметры для `CTaskDialog`.  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nOptionFlag*  
 Набор флагов, используемых для `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет все текущие параметры для `CTaskDialog`. Чтобы сохранить текущие параметры, необходимо получить их сначала с [CTaskDialog::GetOptions](#getoptions) и объединять их с параметрами, которые требуется установить.  
  
 В следующей таблице перечислены все допустимые параметры.  
  
 TDF_ENABLE_HYPERLINKS  
 Включает гиперссылки в `CTaskDialog`.  
  
 TDF_USE_HICON_MAIN  
 Настраивает `CTaskDialog` использовать `HICON` для основного значка. Альтернативой является использование `LPCWSTR`.  
  
 TDF_USE_HICON_FOOTER  
 Настраивает `CTaskDialog` использовать `HICON` для значка нижний колонтитул. Альтернативой является использование `LPCWSTR`.  
  
 TDF_ALLOW_DIALOG_CANCELLATION  
 Дает пользователю возможность закрыть `CTaskDialog` с помощью клавиатуры или с помощью значка в правом верхнем углу диалогового окна, даже если **отменить** кнопка недоступна. Если этот флаг не установлен и **отменить** кнопка недоступна, пользователь не может закрыть диалоговое окно с помощью клавиш Alt + F4, нажмите клавишу ESC, или строке заголовка кнопку Закрыть.  
  
 TDF_USE_COMMAND_LINKS  
 Настраивает `CTaskDialog` для использования команды элемента управления button.  
  
 TDF_USE_COMMAND_LINKS_NO_ICON  
 Настраивает `CTaskDialog` для использования элементов управления кнопки команд без отображения значка рядом с элементом управления. TDF_USE_COMMAND_LINKS переопределяет TDF_USE_COMMAND_LINKS_NO_ICON.  
  
 TDF_EXPAND_FOOTER_AREA  
 Указывает, что в данный момент развернут области расширения.  
  
 TDF_EXPANDED_BY_DEFAULT  
 Определяет, развернута ли области расширения по умолчанию.  
  
 TDF_VERIFICATION_FLAG_CHECKED  
 Указывает, что в настоящее время выбран флажок проверки.  
  
 TDF_SHOW_PROGRESS_BAR  
 Настраивает `CTaskDialog` для отображения индикатора хода выполнения.  
  
 TDF_SHOW_MARQUEE_PROGRESS_BAR  
 Настраивает индикатор для индикатора хода выполнения. Если этот параметр включен, необходимо задать TDF_SHOW_PROGRESS_BAR иметь ожидаемое поведение.  
  
 TDF_CALLBACK_TIMER  
 Указывает, что `CTaskDialog` обратного вызова интервал равен примерно 200 миллисекунд.  
  
 TDF_POSITION_RELATIVE_TO_WINDOW  
 Настраивает `CTaskDialog` центрирование относительно родительского окна. Если этот флаг не включена, `CTaskDialog` выравнивается по центру относительно монитор.  
  
 TDF_RTL_LAYOUT  
 Настраивает `CTaskDialog` для чтения справа налево.  
  
 TDF_NO_DEFAULT_RADIO_BUTTON  
 Указывает, что нет переключателя при `CTaskDialog` отображается.  
  
 TDF_CAN_BE_MINIMIZED  
 Позволяет свести к минимуму `CTaskDialog`. Для поддержки этого параметра `CTaskDialog` не может быть модальным. MFC поддерживает этот параметр, поскольку MFC не поддерживает немодальный `CTaskDialog`.  
  
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
 Значение TRUE, чтобы включить индикатора; Значение FALSE, если отключение индикатора и удалите его из `CTaskDialog`.  
  
 [in] *nMarqueeSpeed*  
 Целое число, указывающее скорость индикатора.  
  
### <a name="remarks"></a>Примечания  
 Индикатора отображается под основной текст `CTaskDialog` класса.  
  
 Используйте *nMarqueeSpeed* скорости индикатора; большего значения указывают на более низкой скорости. Значение 0 для *nMarqueeSpeed* делает индикатора перемещения со скоростью по умолчанию для Windows.  
  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос Если *nMarqueeSpeed* меньше 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarposition"></a>  CTaskDialog::SetProgressBarPosition  
 Изменяет положение индикатора выполнения.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nProgressPos*  
 Позиция в строке состояния.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос Если *nProgressPos* не находится в диапазоне панели хода выполнения. Можно изменить диапазон панель хода выполнения с [CTaskDialog::SetProgressBarRange](#setprogressbarrange).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarrange"></a>  CTaskDialog::SetProgressBarRange  
 Настройка диапазона индикатора хода выполнения.  
  
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
 Положение индикатора — относительно *nRangeMin* и *nRangeMax*. Например если *nRangeMin* равно 50 и *nRangeMax* — 100, положение 75 находится на равном расстоянии вдоль индикатора. Используйте [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) Чтобы установить позицию индикатора выполнения.  
  
 Чтобы отобразить индикатор выполнения, параметр TDF_SHOW_PROGRESS_BAR должна быть включена и TDF_SHOW_MARQUEE_PROGRESS_BAR не включается. Этот метод автоматически задает TDF_SHOW_PROGRESS_BAR и очищает TDF_SHOW_MARQUEE_PROGRESS_BAR. Используйте [CTaskDialog::SetOptions](#setoptions) и вручную изменить параметры для этого экземпляра [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md).  
  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос Если *nRangeMin* — не менее *nRangeMax*. Этот метод вызывает исключение, если `CTaskDialog` уже отображается и имеет индикатора хода выполнения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarstate"></a>  CTaskDialog::SetProgressBarState  
 Задает состояние индикатора хода выполнения и отображает его на `CTaskDialog`.  
  
```  
void SetProgressBarState(int nState = PBST_NORMAL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nState*  
 Состояние индикатора хода выполнения. Возможные значения см.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос Если `CTaskDialog` уже отображается и имеет индикатора хода выполнения.  
  
 В следующей таблице перечислены возможные значения для *nState*. Во всех этих случаях индикатор выполнения будет заливка цветом регулярного до достижения позиции указанного табуляции. На этом этапе это приведет к изменению цвета на основе состояния.  
  
 PBST_NORMAL  
 После выполнения заполняет панель, `CTaskDialog` не изменяет цвет полосы. По умолчанию цвет регулярного имеет зеленый цвет.  
  
 PBST_ERROR  
 После выполнения заполняет панель, `CTaskDialog` изменяется цвет строки к ошибке. По умолчанию это — красным.  
  
 PBST_PAUSED  
 После выполнения заполняет панель, `CTaskDialog` изменяется цвет строки к приостановлена. По умолчанию это желтый.  
  
 Можно задать останавливается индикатор выполнения, где [CTaskDialog::SetProgressBarPosition](#setprogressbarposition).  
  
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
 Идентификатор элемента управления "переключатель".  
  
 [in] *bEnabled*  
 Значение TRUE, чтобы включить переключатель; Значение FALSE, чтобы отключить кнопку-переключатель.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос Если *nRadioButtonID* не является допустимым Идентификатором для типа "переключатель".  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setverificationcheckbox"></a>  CTaskDialog::SetVerificationCheckbox  
 Задает состояние флажка проверки.  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bChecked*  
 Значение true для флажок проверки выбранных при `CTaskDialog` отображается; Значение FALSE, чтобы иметь флажок проверки не выбрано, когда `CTaskDialog` отображается.  
  
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
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](diagnostic-services.md#ensure) макрос, если этот экземпляр `CTaskDialog` класс уже отображается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setwindowtitle"></a>  CTaskDialog::SetWindowTitle  
 Задает заголовок `CTaskDialog`.  
  
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
 Заголовок `CTaskDialog`.  
  
 [in] *nIDCommandControlsFirst*  
 Идентификатор первой команды строки.  
  
 [in] *nIDCommandControlsLast*  
 Идентификатор строки последней команды.  
  
 [in] *nCommonButtons*  
 Маска кнопок, чтобы добавить `CTaskDialog`.  
  
 [in] *nTaskDialogOptions*  
 Набор параметров для `CTaskDialog`.  
  
 [in] *strFooter*  
 Строка для использования в качестве нижнего колонтитула.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, соответствующее выбора, сделанного пользователем.  
  
### <a name="remarks"></a>Примечания  
 Этот статический метод дает возможность создать экземпляр `CTaskDialog` класса без явного создания `CTaskDialog` объекта в коде. Так как не `CTaskDialog` объекта, не может вызывать остальные методы из `CTaskDialog` при использовании этого метода для отображения `CTaskDialog` для пользователя.  
  
 Этот метод создает команды управления "Кнопка" с использованием данных из файла ресурсов приложения. Таблица строк в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Этот метод добавляет элемент управления button команды для всех записей в таблице строк между *nIDCommandControlsFirst* и *nCommandControlsLast*включительно. Для этих элементов управления кнопок командной строки в таблице строк является заголовка элемента управления и идентификатор строки является идентификатором элемента управления.  
  
 В разделе [CTaskDialog::SetOptions](#setoptions) список допустимых параметров.  
  
 `CTaskDialog` Закрывается, если пользователь общих нажатие кнопки командую ссылку или закрывает `CTaskDialog`. Возвращаемое значение — идентификатор, который указывает, как пользователь закрыл диалоговое окно.  
  
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
 Дескриптор `m_hWnd` структуру `CTaskDialog`.  
  
 [in] *uNotification*  
 Код уведомления, указывающий созданного сообщения.  
  
 [in] *wParam*  
 Дополнительные сведения о сообщении.  
  
 [in] *lParam*  
 Дополнительные сведения о сообщении.  
  
 [in] *dwRefData*  
 Указатель на `CTaskDialog` объект, к которому применяется сообщение обратного вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Зависит от конкретного уведомления кода. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию `TaskDialogCallback` обрабатывает конкретное сообщение и затем вызывает соответствующий метод [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Например, в ответ на сообщение TDN_BUTTON_CLICKED `TaskDialogCallback` вызовы [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick).  
  
 Значения для *wParam* и *lParam* зависят от конкретного создаваемого сообщения. Это возможно, один или оба эти значения, быть пустым. В следующей таблице перечислены уведомлений по умолчанию, которые поддерживаются и какие значения *wParam* и *lParam* представления. При переопределении в производном классе этот метод необходимо реализовать код обратного вызова для каждого сообщения в следующей таблице.  
  
|Сообщение уведомления|*wParam* значение|*lParam* значение|  
|--------------------------|--------------------|--------------------|  
|TDN_CREATED|Не используется.|Не используется.|  
|TDN_NAVIGATED|Не используется.|Не используется.|  
|TDN_BUTTON_CLICKED|Кнопка идентификатора элемента управления.|Не используется.|  
|TDN_HYPERLINK_CLICKED|Не используется.|Объект [— LPCWSTR](http://msdn.microsoft.com/library/windows/desktop/aa383751) структуру, содержащую ссылку.|  
|TDN_TIMER|Время в миллисекундах с момента `CTaskDialog` был создан или сброса таймера.|Не используется.|  
|TDN_DESTROYED|Не используется.|Не используется.|  
|TDN_RADIO_BUTTON_CLICKED|Идентификатор radio кнопки|Не используется.|  
|TDN_DIALOG_CONSTRUCTED|Не используется.|Не используется.|  
|TDN_VERIFICATION_CLICKED|1, если флажок установлен, значение 0, если это не так.|Не используется.|  
|TDN_HELP|Не используется.|Не используется.|  
|TDN_EXPANDO_BUTTON_CLICKED|0, если свернута область расширения; ненулевое значение, если отображается текст расширения.|Не используется.|  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Пошаговое руководство. Добавление CTaskDialog в приложение](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)



