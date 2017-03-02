---
title: "Класс CTaskDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTaskDialog
dev_langs:
- C++
helpviewer_keywords:
- CTaskDialog class
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
caps.latest.revision: 29
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 46de64825de9f824ce3d0a5d0c74b7cdc2352774
ms.lasthandoff: 02/24/2017

---
# <a name="ctaskdialog-class"></a>CTaskDialog Class
Всплывающее диалоговое окно, которое функционирует как окно сообщения, но может отображать дополнительные сведения для пользователя. `CTaskDialog` также включает функции для получения сведений от пользователя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTaskDialog : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](#ctaskdialog)|Создает объект `CTaskDialog`.|  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|Добавляет элемент управления кнопки команд для `CTaskDialog`.|  
|[CTaskDialog::AddRadioButton](#addradiobutton)|Добавляет кнопку-переключатель `CTaskDialog`.|  
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Нажимает кнопку или кнопку общих программным способом.|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Кнопка переключателя программным способом.|  
|[CTaskDialog::DoModal](#domodal)|Отображает `CTaskDialog`.|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|Получает число доступных стандартные кнопки.|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Преобразует стандартной кнопки Windows в общий тип кнопки связанный с `CTaskDialog` класса.|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|Преобразует один из распространенных типов кнопки, связанные с `CTaskDialog` класса стандартной кнопки Windows.|  
|[CTaskDialog::GetOptions](#getoptions)|Возвращает флаги параметра `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|Возвращает выбранный элемент управления.|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Возвращает выбранного переключателя.|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|Получает состояние флажка проверки.|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Определяет, включен ли переключатель или общие кнопки.|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|Определяет, включен ли переключатель.|  
|[CTaskDialog::IsSupported](#issupported)|Определяет, поддерживает ли компьютер, на котором выполняется приложение `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Добавляет кнопку командные элементы управления, используя данные из строки таблицы.|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|Добавление переключателей с помощью данных из строки таблицы.|  
|[CTaskDialog::NavigateTo](#navigateto)|Переводит фокус на другой `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Платформа вызывает этот метод, когда пользователь нажимает кнопку.|  
|[CTaskDialog::OnCreate](#oncreate)|Платформа вызывает этот метод после создания `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](#ondestroy)|Платформа вызывает этот метод непосредственно перед уничтожает `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|Платформа вызывает этот метод, когда пользователь нажимает на кнопку расширения.|  
|[CTaskDialog::OnHelp](#onhelp)|Платформа вызывает этот метод при запросе справки.|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|Платформа вызывает этот метод, когда пользователь щелкает гиперссылку.|  
|[CTaskDialog::OnInit](#oninit)|Платформа вызывает этот метод при `CTaskDialog` инициализируется.|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Платформа вызывает этот метод при перемещении фокуса с точки зрения элементов управления `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|Платформа вызывает этот метод, когда пользователь выбирает элемент управления переключателя.|  
|[CTaskDialog::OnTimer](#ontimer)|Платформа вызывает этот метод после истечения срока действия таймера.|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|Платформа вызывает этот метод, когда пользователь выбирает флажок проверки.|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Удаляет все элементы из команды `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Удаляет все переключатели из `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Обновляет кнопку на `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|Обновляет подмножество стандартные кнопки, чтобы включить и требующие повышения прав UAC.|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|Добавляет стандартные кнопки для `CTaskDialog`.|  
|[CTaskDialog::SetContent](#setcontent)|Обновляет содержимое `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Указывает элемент управления по умолчанию.|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Задает переключатель по умолчанию.|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|Корректирует ширину `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|Обновляет область расширения `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|Значок нижнего колонтитула для обновлений `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](#setfootertext)|Обновляет текст в нижнем колонтитуле `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](#setmainicon)|Обновление главного значка `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Обновляет основные инструкции из `CTaskDialog`.|  
|[CTaskDialog::SetOptions](#setoptions)|Настраивает параметры для `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|Настраивает индикатора для `CTaskDialog` и добавляет его в диалоговое окно.|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|Регулирует положение индикатора хода выполнения.|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|Настройка диапазона индикатора хода выполнения.|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|Задает состояние индикатора хода выполнения и отображает его на `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Включает или отключает переключатель.|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|Задает состояние проверки элемента флажок проверки.|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Задает текст справа от флажка проверки.|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Задает заголовок `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](#showdialog)|Создает и отображает `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Платформа вызывает это в ответ на различные сообщения Windows.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|`m_aButtons`|Массив элементов управления кнопки команд для `CTaskDialog`.|  
|`m_aRadioButtons`|Массив элементов управления переключателями для `CTaskDialog`.|  
|`m_bVerified`|`TRUE`Указывает, что установлен флажок проверки; `FALSE` указывает, это не так.|  
|`m_footerIcon`|Значок в нижнем колонтитуле `CTaskDialog`.|  
|`m_hWnd`|Дескриптор окна для `CTaskDialog`.|  
|`m_mainIcon`|Значок главной `CTaskDialog`.|  
|`m_nButtonDisabled`|Маска, которая указывает, что стандартные кнопки будут отключены.|  
|`m_nButtonElevation`|Маска, которая указывает, что стандартные кнопки требуется повышение прав контроля учетных Записей.|  
|`m_nButtonId`|Идентификатор элемента управления button выбранной команды.|  
|`m_nCommonButton`|Маска, которая указывает, какие общие кнопки отображаются на `CTaskDialog`.|  
|`m_nDefaultCommandControl`|Идентификатор кнопки управления, при выборе `CTaskDialog` отображается.|  
|`m_nDefaultRadioButton`|Идентификатор переключатель управления, при выборе `CTaskDialog` отображается.|  
|`m_nFlags`|Маска, которая указывает параметры для `CTaskDialog`.|  
|`m_nProgressPos`|Текущее положение индикатора.  Это значение должно принадлежать диапазону от `m_nProgressRangeMin` до `m_nProgressRangeMax`.|  
|`m_nProgressRangeMax`|Максимальное значение для индикатора.|  
|`m_nProgressRangeMin`|Минимальное значение для индикатора.|  
|`m_nProgressState`|Состояние индикатора хода выполнения. Дополнительные сведения см. в разделе [CTaskDialog::SetProgressBarState](#setprogressbarstate).|  
|`m_nRadioId`|Идентификатор выбранного переключателя.|  
|`m_nWidth`|Ширина `CTaskDialog` в пикселях.|  
|`m_strCollapse`|Строка `CTaskDialog` отображается справа от поля расширения скрытого расширенные сведения.|  
|`m_strContent`|Строку содержимого объекта `CTaskDialog`.|  
|`m_strExpand`|Строка `CTaskDialog` отображается справа от поля расширения при отображении расширенные сведения.|  
|`m_strFooter`|В нижний колонтитул `CTaskDialog`.|  
|`m_strInformation`|Подробные сведения для `CTaskDialog`.|  
|`m_strMainInstruction`|Основные инструкции из `CTaskDialog`.|  
|`m_strTitle`|Название `CTaskDialog`.|  
|`m_strVerification`|Строка, `CTaskDialog` отображается справа от флажка проверки.|  
  
## <a name="remarks"></a>Примечания  
 `CTaskDialog` Класс заменяет со стандартным окном сообщений Windows и имеет дополнительные функциональные возможности, такие как новые элементы управления для сбора сведений от пользователя. Этот класс находится в библиотеке MFC в [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]. `CTaskDialog` Доступен, начиная с [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Более ранние версии Windows не удается отобразить `CTaskDialog` объекта. Использование `CTaskDialog::IsSupported` на этапе выполнения определить, может ли текущий пользователь отображать диалоговое окно задач. Со стандартным окном сообщений Windows по-прежнему поддерживается в [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  
  
 `CTaskDialog` Доступен только при построении приложения с использованием библиотеки Юникода.  
  
 `CTaskDialog` Имеет две различные конструкторы. Один конструктор позволяет указать две кнопки и максимум шесть элементов управления обычная кнопка. После создания можно добавить дополнительные кнопки `CTaskDialog`. Второй конструктор не поддерживает все кнопки, но можно добавить неограниченное число обычных кнопок. Дополнительные сведения о конструкторах см. в разделе [CTaskDialog::CTaskDialog](#ctaskdialog).  
  
 На следующем рисунке показано пример `CTaskDialog` Демонстрация расположение некоторых элементов управления.  
  
 ![Пример CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
Пример CTaskDialog  
  
## <a name="requirements"></a>Требования  
 **Минимальная требуемая операционная система:**[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
 **Заголовок:** afxtaskdialog.h  
  
##  <a name="a-nameaddcommandcontrola--ctaskdialogaddcommandcontrol"></a><a name="addcommandcontrol"></a>CTaskDialog::AddCommandControl  
 Добавляет новый элемент управления кнопки команд для `CTaskDialog`.  
  
```  
void AddCommandControl(
    int nCommandControlID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCommandControlID`  
 Идентификационный номер команды управления.  
  
 [in] `strCaption`  
 Строка, `CTaskDialog` отображает для пользователя. Используйте эту строку в качестве пояснения команды.  
  
 [in] `bEnabled`  
 Логический параметр, который указывает, включен ли новой кнопки.  
  
 [in] `bRequiresElevation`  
 Логический параметр, указывающий, требуется ли команда повышения прав.  
  
### <a name="remarks"></a>Примечания  
 `CTaskDialog Class` Может отображать неограниченное количество команды элемента управления button. Однако если `CTaskDialog` отобразится любой кнопки элементов управления, его можно отобразить до шести кнопок. Если `CTaskDialog` нет команды кнопки элементов управления, она может содержать неограниченное число кнопок.  
  
 Когда пользователь выбирает элемент управления кнопки команд, `CTaskDialog` закрывается. Если приложение отображает диалоговое окно с помощью [CTaskDialog::DoModal](#domodal), `DoModal` возвращает `nCommandControlID` элемента управления button выбранной команды.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-nameaddradiobuttona--ctaskdialogaddradiobutton"></a><a name="addradiobutton"></a>CTaskDialog::AddRadioButton  
 Добавляет кнопку-переключатель `CTaskDialog`.  
  
```  
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRadioButtonID`  
 Идентификационный номер переключатель.  
  
 [in] `strCaption`  
 Строка, `CTaskDialog` рядом переключатель отображается.  
  
 [in] `bEnabled`  
 Логический параметр, указывающий, включен ли переключатель.  
  
### <a name="remarks"></a>Примечания  
 Радио кнопок для [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) позволяют получать информацию от пользователя. Используйте функцию [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) для определения, какой переключатель установлен.  
  
 `CTaskDialog` Не требует `nRadioButtonID` параметры являются уникальными для каждого переключателя. Тем не менее могут испытать неожиданное поведение, если не используется distinct идентификатор для каждого переключателя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-nameclickcommandcontrola--ctaskdialogclickcommandcontrol"></a><a name="clickcommandcontrol"></a>CTaskDialog::ClickCommandControl  
 Нажимает кнопку или кнопку общих программным способом.  
  
```  
protected:  
void ClickCommandControl(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCommandControlID`  
 Идентификатор команды элемента управления, нажмите кнопку.  
  
### <a name="remarks"></a>Примечания  
 Этот метод формирует сообщение windows `TDM_CLICK_BUTTON`.  
  
##  <a name="a-nameclickradiobuttona--ctaskdialogclickradiobutton"></a><a name="clickradiobutton"></a>CTaskDialog::ClickRadioButton  
 Кнопка переключателя программным способом.  
  
```  
protected:  
void ClickRadioButton(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRadioButtonID`  
 Идентификатор щелкните кнопку-переключатель.  
  
### <a name="remarks"></a>Примечания  
 Этот метод формирует сообщение windows `TDM_CLICK_RADIO_BUTTON`.  
  
##  <a name="a-namectaskdialoga--ctaskdialogctaskdialog"></a><a name="ctaskdialog"></a>CTaskDialog::CTaskDialog  
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
 [in] `strContent`  
 Строка, используемая для создания содержимого `CTaskDialog`.  
  
 [in] `strMainInstruction`  
 Основные инструкции из `CTaskDialog`.  
  
 [in] `strTitle`  
 Название `CTaskDialog`.  
  
 [in] `nCommonButtons`  
 Маска стандартные кнопки, чтобы добавить `CTaskDialog`.  
  
 [in] `nTaskDialogOptions`  
 Набор параметров для `CTaskDialog`.  
  
 [in] `strFooter`  
 Строка для использования в качестве нижнего колонтитула.  
  
 [in] `nIDCommandControlsFirst`  
 Идентификатор строки первой команды.  
  
 [in] `nIDCommandControlsLast`  
 Идентификатор строки последней команды.  
  
### <a name="remarks"></a>Примечания  
 Существует два способа, которые можно добавить `CTaskDialog` в приложение. Первый способ — использовать один из конструкторов для создания `CTaskDialog` и отобразить ее с помощью [CTaskDialog::DoModal](#domodal). Вторым способом является использование статической функции [CTaskDialog::ShowDialog](#showdialog), который позволяет отображать `CTaskDialog` без явного создания `CTaskDialog` объекта.  
  
 Второй конструктор создает кнопку командные элементы управления с использованием данных из файла ресурсов приложения. В таблице строки в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Этот метод добавляет элемент управления кнопки команд для всех записей в таблице строк между `nIDCommandControlsFirst` и `nCommandControlsLast`включительно. Для этих элементов управления кнопки команды строка в таблице строк — заголовок элемента управления и идентификатор строки является идентификатором элемента управления.  
  
 В разделе [CTaskDialog::SetOptions](#setoptions) список допустимых параметров.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namedomodala--ctaskdialogdomodal"></a><a name="domodal"></a>CTaskDialog::DoModal  
 Показывает `CTaskDialog` и делает ее модальной.  
  
```  
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hParent`  
 Родительское окно для `CTaskDialog`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, соответствующее выбора, сделанного пользователем.  
  
### <a name="remarks"></a>Примечания  
 Отображает этот экземпляр [CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Затем приложение ожидает от пользователя закрыть диалоговое окно.  
  
 `CTaskDialog` Закрывается, когда пользователь выбирает общие кнопки, элемент управления command link, или закрывает `CTaskDialog`. Возвращает значение идентификатора, указывающее, как пользователь закрыл диалоговое окно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namegetcommonbuttoncounta--ctaskdialoggetcommonbuttoncount"></a><a name="getcommonbuttoncount"></a>CTaskDialog::GetCommonButtonCount  
 Получает число стандартные кнопки.  
  
```  
int GetCommonButtonCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество доступных стандартные кнопки.  
  
### <a name="remarks"></a>Примечания  
 Стандартные кнопки находятся кнопки по умолчанию, который предоставляется [CTaskDialog::CTaskDialog](#ctaskdialog). [Класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) отображает кнопки в нижней части диалоговое окно.  
  
 В файле CommCtrl.h предоставляется нумерованный список кнопок.  
  
##  <a name="a-namegetcommonbuttonflaga--ctaskdialoggetcommonbuttonflag"></a><a name="getcommonbuttonflag"></a>CTaskDialog::GetCommonButtonFlag  
 Преобразует стандартной кнопки Windows в общий тип кнопки связанных с [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md).  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nButtonId`  
 Значение стандартной кнопки Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение соответствующего `CTaskDialog` общие кнопки. Если отсутствует соответствующий кнопка "Общие", этот метод возвращает 0.  
  
##  <a name="a-namegetcommonbuttonida--ctaskdialoggetcommonbuttonid"></a><a name="getcommonbuttonid"></a>CTaskDialog::GetCommonButtonId  
 Преобразует один из распространенных типов кнопки, связанные с [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) для стандартной кнопки Windows.  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nFlag`  
 Общий тип кнопки, связанного с `CTaskDialog` класса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение соответствующего стандартной кнопки Windows. Если отсутствует соответствующий кнопка "Windows", метод возвращает 0.  
  
##  <a name="a-namegetoptionsa--ctaskdialoggetoptions"></a><a name="getoptions"></a>CTaskDialog::GetOptions  
 Возвращает флаги параметра `CTaskDialog`.  
  
```  
int GetOptions() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Флаги для `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о параметрах, доступных для [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md), в разделе [CTaskDialog::SetOptions](#setoptions).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namegetselectedcommandcontrolida--ctaskdialoggetselectedcommandcontrolid"></a><a name="getselectedcommandcontrolid"></a>CTaskDialog::GetSelectedCommandControlID  
 Возвращает выбранный элемент управления.  
  
```  
int GetSelectedCommandControlID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор элемента управления button текущей выбранной команды.  
  
### <a name="remarks"></a>Примечания  
 Необходимо использовать этот метод для получения идентификатора выбранный пользователем кнопки. Этот идентификатор возвращается либо [CTaskDialog::DoModal](#domodal) или [CTaskDialog::ShowDialog](#showdialog).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-namegetselectedradiobuttonida--ctaskdialoggetselectedradiobuttonid"></a><a name="getselectedradiobuttonid"></a>CTaskDialog::GetSelectedRadioButtonID  
 Возвращает выбранного переключателя.  
  
```  
int GetSelectedRadioButtonID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор выбранного переключателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать после пользователь закрывает диалоговое окно извлечения выбранного переключателя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namegetverificationcheckboxstatea--ctaskdialoggetverificationcheckboxstate"></a><a name="getverificationcheckboxstate"></a>CTaskDialog::GetVerificationCheckboxState  
 Получает состояние флажка проверки.  
  
```  
BOOL GetVerificationCheckboxState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если флажок установлен, `FALSE` Если это не так.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#5;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="a-nameiscommandcontrolenableda--ctaskdialogiscommandcontrolenabled"></a><a name="iscommandcontrolenabled"></a>CTaskDialog::IsCommandControlEnabled  
 Определяет, включен ли элемент управления кнопки команды или кнопки.  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCommandControlID`  
 Идентификатор элемента управления кнопки команды или кнопки для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включить элемент управления `FALSE` , если это не так.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать для определения доступности и кнопки команд и стандартные кнопки из `CTaskDialog Class`.  
  
 Если `nCommandControlID` является не является допустимым идентификатором для любого общего `CTaskDialog` кнопку или кнопку, этот метод создает исключение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-nameisradiobuttonenableda--ctaskdialogisradiobuttonenabled"></a><a name="isradiobuttonenabled"></a>CTaskDialog::IsRadioButtonEnabled  
 Определяет, включен ли переключатель.  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRadioButtonID`  
 Идентификатор переключатель для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если переключатель включен, `FALSE` Если это не так.  
  
### <a name="remarks"></a>Примечания  
 Если `nRadioButtonID` не является допустимым идентификатором для переключателя, этот метод создает исключение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-nameissupporteda--ctaskdialogissupported"></a><a name="issupported"></a>CTaskDialog::IsSupported  
 Определяет, поддерживает ли компьютер, на котором выполняется приложение `CTaskDialog`.  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если компьютер поддерживает `CTaskDialog`; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Эта функция позволяет определить во время выполнения, если компьютер, на котором выполняется приложение поддерживает `CTaskDialog Class`. Если компьютер не поддерживает `CTaskDialog`, следует предоставить другой способ обмена информацией для пользователя. Сбой при попытке использовать приложение `CTaskDialog` на компьютере, который не поддерживает `CTaskDialog` класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#1;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="a-nameloadcommandcontrolsa--ctaskdialogloadcommandcontrols"></a><a name="loadcommandcontrols"></a>CTaskDialog::LoadCommandControls  
 Добавляет кнопку командные элементы управления, используя данные из строки таблицы.  
  
```  
void LoadCommandControls(
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIDCommandControlsFirst`  
 Идентификатор строки первой команды.  
  
 [in] `nIDCommandControlsLast`  
 Идентификатор строки последней команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает кнопку командные элементы управления с использованием данных из файла ресурсов приложения. В таблице строки в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Команда кнопки добавлены новые элементы управления с помощью этого метода использовать строку заголовка элемента управления и идентификатор строки для идентификатора элемента управления. Диапазон строк, выбранных обеспечивается `nIDCommandControlsFirst` и `nCommandControlsLast`включительно. Если в диапазоне пустую запись, метод не добавляет командую кнопку для этой записи.  
  
 По умолчанию новые элементы управления кнопки команды включены и не требуют повышения прав.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-nameloadradiobuttonsa--ctaskdialogloadradiobuttons"></a><a name="loadradiobuttons"></a>CTaskDialog::LoadRadioButtons  
 Добавление переключателей с помощью данных из строки таблицы.  
  
```  
void LoadRadioButtons(
    int nIDRadioButtonsFirst,  
    int nIDRadioButtonsLast);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIDRadioButtonsFirst`  
 Идентификатор строки первый переключатель.  
  
 [in] `nIDRadioButtonsLast`  
 Идентификатор строки последнего переключателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает переключателей с помощью данных из файла ресурсов приложения. В таблице строки в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Новые переключатели, добавленные с помощью этого метода использовать строку заголовка переключатель и строковый идентификатор для идентификатора переключатель. Диапазон строк, выбранных обеспечивается `nIDRadioButtonsFirst` и `nRadioButtonsLast`включительно. Если в диапазоне пустую запись, метод не добавляет переключатель для этой записи.  
  
 По умолчанию включены новые переключатели.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namenavigatetoa--ctaskdialognavigateto"></a><a name="navigateto"></a>CTaskDialog::NavigateTo  
 Переводит фокус на другой `CTaskDialog`.  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `oTaskDialog`  
 `CTaskDialog` , Получающий фокус.  
  
### <a name="remarks"></a>Примечания  
 Этот метод скрывает текущий `CTaskDialog` при его отображении `oTaskDialog`. `oTaskDialog` Отображается в том же расположении, что и текущий `CTaskDialog`.  
  
##  <a name="a-nameoncommandcontrolclicka--ctaskdialogoncommandcontrolclick"></a><a name="oncommandcontrolclick"></a>CTaskDialog::OnCommandControlClick  
 Платформа вызывает этот метод, когда пользователь нажимает кнопку.  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCommandControlID`  
 Идентификатор элемент управления, выбранный пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameoncreatea--ctaskdialogoncreate"></a><a name="oncreate"></a>CTaskDialog::OnCreate  
 Платформа вызывает этот метод после создания `CTaskDialog`.  
  
```  
virtual HRESULT OnCreate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameondestroya--ctaskdialogondestroy"></a><a name="ondestroy"></a>CTaskDialog::OnDestroy  
 Платформа вызывает этот метод непосредственно перед уничтожает `CTaskDialog`.  
  
```  
virtual HRESULT OnDestroy();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameonexpandbuttonclicka--ctaskdialogonexpandbuttonclick"></a><a name="onexpandbuttonclick"></a>CTaskDialog::OnExpandButtonClick  
 Платформа вызывает этот метод, когда пользователь нажимает на кнопку расширения.  
  
```  
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bExpanded`  
 Ненулевое значение указывает, что отображается дополнительная информация; 0 указывает, что скрытые дополнительной информации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameonhelpa--ctaskdialogonhelp"></a><a name="onhelp"></a>CTaskDialog::OnHelp  
 Платформа вызывает этот метод при запросе справки.  
  
```  
virtual HRESULT OnHelp();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameonhyperlinkclicka--ctaskdialogonhyperlinkclick"></a><a name="onhyperlinkclick"></a>CTaskDialog::OnHyperlinkClick  
 Платформа вызывает этот метод, когда пользователь щелкает гиперссылку.  
  
```  
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strHref`  
 Строка, представляющая гиперссылки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) перед возвращением `S_OK`.  
  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameoninita--ctaskdialogoninit"></a><a name="oninit"></a>CTaskDialog::OnInit  
 Платформа вызывает этот метод при `CTaskDialog` инициализируется.  
  
```  
virtual HRESULT OnInit();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameonnavigatepagea--ctaskdialogonnavigatepage"></a><a name="onnavigatepage"></a>CTaskDialog::OnNavigatePage  
 Платформа вызывает этот метод в ответ на [CTaskDialog::NavigateTo](#navigateto) метод.  
  
```  
virtual HRESULT OnNavigatePage();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameonradiobuttonclicka--ctaskdialogonradiobuttonclick"></a><a name="onradiobuttonclick"></a>CTaskDialog::OnRadioButtonClick  
 Платформа вызывает этот метод, когда пользователь выбирает элемент управления переключателя.  
  
```  
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRadioButtonID`  
 Идентификатор переключателя, который выбрал пользователь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameontimera--ctaskdialogontimer"></a><a name="ontimer"></a>CTaskDialog::OnTimer  
 Платформа вызывает этот метод после истечения срока действия таймера.  
  
```  
virtual HRESULT OnTimer(long lTime);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lTime`  
 Время в миллисекундах с момента `CTaskDialog` был создан или сброса таймера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameonverificationcheckboxclicka--ctaskdialogonverificationcheckboxclick"></a><a name="onverificationcheckboxclick"></a>CTaskDialog::OnVerificationCheckboxClick  
 Платформа вызывает этот метод, когда пользователь выбирает флажок проверки.  
  
```  
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bChecked`  
 `TRUE`Указывает, что установлен флажок проверки; `FALSE` указывает, это не так.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское поведение.  
  
##  <a name="a-nameremoveallcommandcontrolsa--ctaskdialogremoveallcommandcontrols"></a><a name="removeallcommandcontrols"></a>CTaskDialog::RemoveAllCommandControls  
 Удаляет все элементы кнопки команд из `CTaskDialog`.  
  
```  
void RemoveAllCommandControls();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-nameremoveallradiobuttonsa--ctaskdialogremoveallradiobuttons"></a><a name="removeallradiobuttons"></a>CTaskDialog::RemoveAllRadioButtons  
 Удаляет все переключатели из `CTaskDialog`.  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namesetcommandcontroloptionsa--ctaskdialogsetcommandcontroloptions"></a><a name="setcommandcontroloptions"></a>CTaskDialog::SetCommandControlOptions  
 Обновляет кнопку на `CTaskDialog`.  
  
```  
void SetCommandControlOptions(
    int nCommandControlID,  
    BOOL bEnabled,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCommandControlID`  
 Идентификатор элемента управления команду для обновления.  
  
 [in] `bEnabled`  
 Логический параметр, который указывает, включен ли указанный элемент управления.  
  
 [in] `bRequiresElevation`  
 Логический параметр, указывающий, если указанный элемент управления требуется повышение прав.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы изменить кнопку включено, или требуется повышение прав, после добавления в `CTaskDialog Class`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-namesetcommonbuttonoptionsa--ctaskdialogsetcommonbuttonoptions"></a><a name="setcommonbuttonoptions"></a>CTaskDialog::SetCommonButtonOptions  
 Обновляет подмножество стандартные кнопки включения и требующие повышения прав UAC.  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nDisabledButtonMask`  
 Маска для стандартные кнопки для отключения.  
  
 [in] `nElevationButtonMask`  
 Маска для стандартные кнопки, требующие повышения прав.  
  
### <a name="remarks"></a>Примечания  
 Доступные стандартные кнопки можно присвоить экземпляр [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md) с помощью конструктора [CTaskDialog::CTaskDialog](#ctaskdialog) , а также метод [CTaskDialog::SetCommonButtons](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions`не поддерживает добавление новых общих кнопок.  
  
 При использовании этого метода для отключения или повысить общие кнопки, которая недоступна для данного `CTaskDialog`, этот метод создает исключение с помощью [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос.  
  
 Этот метод позволяет любую кнопку, которая доступна для `CTaskDialog` , но не находится в `nDisabledButtonMask`, даже если он был ранее отключен. Этот метод обрабатывает повышение аналогичным образом: она записывает стандартные кнопки как не требующие повышения прав, если кнопка «Общие» доступны, но не включается в `nElevationButtonMask`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog №&6;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="a-namesetcommonbuttonsa--ctaskdialogsetcommonbuttons"></a><a name="setcommonbuttons"></a>CTaskDialog::SetCommonButtons  
 Добавляет стандартные кнопки для `CTaskDialog`.  
  
```  
void SetCommonButtons(
    int nButtonMask,  
    int nDisabledButtonMask = 0,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nButtonMask`  
 Маска кнопок, чтобы добавить `CTaskDialog`.  
  
 [in] `nDisabledButtonMask`  
 Маска для отключения кнопки.  
  
 [in] `nElevationButtonMask`  
 Маска кнопок, которые требуют повышения прав.  
  
### <a name="remarks"></a>Примечания  
 Этот метод нельзя вызывать после окна отображения для этого экземпляра `CTaskDialog Class` создается. В противном случае этот метод создает исключение.  
  
 Указывает кнопки `nButtonMask` переопределить любые стандартные кнопки, ранее добавленный `CTaskDialog`. Указано только кнопки в `nButtonMask` доступны.  
  
 Если параметр `nDisabledButtonMask` или `nElevationButtonMask` содержит кнопку, которая не находится в `nButtonMask`, этот метод создает исключение с помощью [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос.  
  
 По умолчанию все стандартные кнопки включены и не требуют повышения прав.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog №&6;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="a-namesetcontenta--ctaskdialogsetcontent"></a><a name="setcontent"></a>CTaskDialog::SetContent  
 Обновляет содержимое `CTaskDialog`.  
  
```  
void SetContent(const CString& strContent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strContent`  
 Строка для отображения пользователю.  
  
### <a name="remarks"></a>Примечания  
 Содержимое `CTaskDialog Class` является текст, который отображается для пользователя в области основного окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetdefaultcommandcontrola--ctaskdialogsetdefaultcommandcontrol"></a><a name="setdefaultcommandcontrol"></a>CTaskDialog::SetDefaultCommandControl  
 Указывает элемент управления по умолчанию.  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCommandControlID`  
 Идентификатор элемент управления по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления по умолчанию является элемент управления, выбранный при `CTaskDialog` сначала отображается для пользователя.  
  
 Этот метод создает исключение, если не удается найти элемент управления, определяемое `nCommandControlID`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-namesetdefaultradiobuttona--ctaskdialogsetdefaultradiobutton"></a><a name="setdefaultradiobutton"></a>CTaskDialog::SetDefaultRadioButton  
 Задает переключатель по умолчанию.  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRadioButtonID`  
 Идентификатор переключатель по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Переключатель «по умолчанию», — это кнопка, выбранный при `CTaskDialog` сначала отображается для пользователя.  
  
 Этот метод создает исключение, если не удается найти переключатель, определяемое `nRadioButtonID`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namesetdialogwidtha--ctaskdialogsetdialogwidth"></a><a name="setdialogwidth"></a>CTaskDialog::SetDialogWidth  
 Корректирует ширину `CTaskDialog`.  
  
```  
void SetDialogWidth(int nWidth = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nWidth`  
 Ширина диалогового окна в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Параметр `nWidth` должен быть больше или равно 0. В противном случае этот метод создает исключение.  
  
 Если `nWidth` имеет значение 0, этот метод задает диалоговое окно размер по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetexpansionareaa--ctaskdialogsetexpansionarea"></a><a name="setexpansionarea"></a>CTaskDialog::SetExpansionArea  
 Обновляет область расширения `CTaskDialog`.  
  
```  
void SetExpansionArea(
    const CString& strExpandedInformation,  
    const CString& strCollapsedLabel = _T(""),  
    const CString& strExpandedLabel = _T(""));
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strExpandedInformation`  
 Строка, `CTaskDialog` отображает в основном тексте диалогового окна при нажатии пользователем кнопки расширения.  
  
 [in] `strCollapsedLabel`  
 Строка, `CTaskDialog` отображается рядом с кнопкой расширения свернутым Развернутая область.  
  
 [in] `strExpandedLabel`  
 Строка, `CTaskDialog` отображается рядом с кнопкой расширения при отображении Развернутая область.  
  
### <a name="remarks"></a>Примечания  
 Области расширения `CTaskDialog Class` позволяет предоставить пользователю Дополнительные сведения. Область расширения находится в основной части `CTaskDialog`, расположенного непосредственно под строку заголовка и содержимого.  
  
 Когда `CTaskDialog` является первым отображается, она не показывать подробные сведения и помещает `strCollapsedLabel` рядом с кнопкой расширение. Когда пользователь нажимает кнопку расширения, `CTaskDialog` отображает `strExpandedInformation` и изменяет метку `strExpandedLabel`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetfootericona--ctaskdialogsetfootericon"></a><a name="setfootericon"></a>CTaskDialog::SetFooterIcon  
 Обновляет значок нижнего колонтитула `CTaskDialog`.  
  
```  
void SetFooterIcon(HICON hFooterIcon);  
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hFooterIcon`  
 Новый значок `CTaskDialog`.  
  
 [in] `lpszFooterIcon`  
 Новый значок `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
 Значок нижнего колонтитула отображается в нижней части [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Его можно связать текст нижнего колонтитула. Можно изменить текст нижнего колонтитула с [CTaskDialog::SetFooterText](#setfootertext).  
  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос Если `CTaskDialog` отображается или входной параметр `NULL`.  
  
 Объект `CTaskDialog` может только принимать `HICON` или `LPCWSTR` как значок нижнего колонтитула. Это настраивается путем установки параметра `TDF_USE_HICON_FOOTER` в конструкторе или [CTaskDialog::SetOptions](#setoptions). По умолчанию `CTaskDialog` настроен для использования `LPCWSTR` как тип входных данных для значка нижний колонтитул. Этот метод создает исключение при попытке задать значок неподходящего типа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetfootertexta--ctaskdialogsetfootertext"></a><a name="setfootertext"></a>CTaskDialog::SetFooterText  
 Обновляет текст в нижнем колонтитуле `CTaskDialog`.  
  
```  
void SetFooterText(const CString& strFooterText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strFooterText`  
 Новый текст для нижнего колонтитула.  
  
### <a name="remarks"></a>Примечания  
 Нижний колонтитул значок отображается рядом с текстом нижнего колонтитула в нижней части `CTaskDialog`. Можно изменить значок нижнего колонтитула с [CTaskDialog::SetFooterIcon](#setfootericon).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetmainicona--ctaskdialogsetmainicon"></a><a name="setmainicon"></a>CTaskDialog::SetMainIcon  
 Обновление главного значка `CTaskDialog`.  
  
```  
void SetMainIcon(HICON hMainIcon);  
void SetMainIcon(LPCWSTR lpszMainIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMainIcon`  
 Новый значок.  
  
 [in] `lpszMainIcon`  
 Новый значок.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос Если `CTaskDialog` отображается или входной параметр `NULL`.  
  
 Объект `CTaskDialog` может только принимать `HICON` или `LPCWSTR` как основной значок. Это можно настроить, задав `TDF_USE_HICON_MAIN` параметр в конструкторе или в [CTaskDialog::SetOptions](#setoptions) метод. По умолчанию `CTaskDialog` настроен для использования `LPCWSTR` как тип входных данных для основной значок. Этот метод создает исключение при попытке задать значок неподходящего типа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetmaininstructiona--ctaskdialogsetmaininstruction"></a><a name="setmaininstruction"></a>CTaskDialog::SetMainInstruction  
 Обновляет основные инструкции из `CTaskDialog`.  
  
```  
void SetMainInstruction(const CString& strInstructions);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strInstructions`  
 Новые основные инструкции.  
  
### <a name="remarks"></a>Примечания  
 Основные инструкции из `CTaskDialog Class` является текст, отображаемый для пользователя крупным полужирным шрифтом. Он находится в диалоговом окне под заголовком окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetoptionsa--ctaskdialogsetoptions"></a><a name="setoptions"></a>CTaskDialog::SetOptions  
 Настраивает параметры для `CTaskDialog`.  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nOptionFlag`  
 Набор флагов, используемых для `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет все текущие параметры для `CTaskDialog`. Чтобы сохранить текущие параметры, сначала нужно получить их с [CTaskDialog::GetOptions](#getoptions) и объединить их с параметрами, которые требуется установить.  
  
 В следующей таблице перечислены все допустимые параметры.  
  
 `TDF_ENABLE_HYPERLINKS`  
 Позволяет гиперссылки в `CTaskDialog`.  
  
 `TDF_USE_HICON_MAIN`  
 Настраивает `CTaskDialog` использовать `HICON` для основной значок. Альтернативой является использование `LPCWSTR`.  
  
 `TDF_USE_HICON_FOOTER`  
 Настраивает `CTaskDialog` использование `HICON` значок нижнего колонтитула. Альтернативой является использование `LPCWSTR`.  
  
 `TDF_ALLOW_DIALOG_CANCELLATION`  
 Позволяет пользователю закрыть `CTaskDialog` с помощью клавиатуры или с помощью значка в правом верхнем углу диалогового окна, даже если **отменить** кнопка недоступна. Если этот флаг не установлен и **отменить** кнопка не включен, пользователь не может закрыть диалоговое окно с помощью клавиш Alt + F4, нажмите клавишу ESC, или кнопка закрытия в заголовке окна.  
  
 `TDF_USE_COMMAND_LINKS`  
 Настраивает `CTaskDialog` использование команды элемента управления button.  
  
 `TDF_USE_COMMAND_LINKS_NO_ICON`  
 Настраивает `CTaskDialog` использовать команду кнопки без отображения значка рядом с элементом управления. `TDF_USE_COMMAND_LINKS` переопределяет `TDF_USE_COMMAND_LINKS_NO_ICON`.  
  
 `TDF_EXPAND_FOOTER_AREA`  
 Указывает, что область расширения расширяется в данный момент.  
  
 `TDF_EXPANDED_BY_DEFAULT`  
 Определяет, развернут ли область расширения по умолчанию.  
  
 `TDF_VERIFICATION_FLAG_CHECKED`  
 Указывает, что в данный момент установлен флажок проверки.  
  
 `TDF_SHOW_PROGRESS_BAR`  
 Настраивает `CTaskDialog` для отображения индикатора.  
  
 `TDF_SHOW_MARQUEE_PROGRESS_BAR`  
 Настраивает индикатор быть индикатор выполнения. Если включить этот параметр, необходимо задать `TDF_SHOW_PROGRESS_BAR` ожидаемое поведение.  
  
 `TDF_CALLBACK_TIMER`  
 Указывает, что `CTaskDialog` обратного вызова интервал составляет приблизительно 200 миллисекунд.  
  
 `TDF_POSITION_RELATIVE_TO_WINDOW`  
 Настраивает `CTaskDialog` центрирование относительно родительского окна. Если этот флаг не включен, `CTaskDialog` центрируется относительно монитора.  
  
 `TDF_RTL_LAYOUT`  
 Настраивает `CTaskDialog` для чтения справа налево.  
  
 `TDF_NO_DEFAULT_RADIO_BUTTON`  
 Указывает, что нет переключателя при `CTaskDialog` отображается.  
  
 `TDF_CAN_BE_MINIMIZED`  
 Позволяет свести к минимуму `CTaskDialog`. Для поддержки этого параметра `CTaskDialog` не может быть модальным. MFC не поддерживают этот параметр, поскольку MFC не поддерживает немодальных `CTaskDialog`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetprogressbarmarqueea--ctaskdialogsetprogressbarmarquee"></a><a name="setprogressbarmarquee"></a>CTaskDialog::SetProgressBarMarquee  
 Настраивает индикатора для `CTaskDialog` и добавляет его в диалоговое окно.  
  
```  
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,  
    int nMarqueeSpeed = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnabled`  
 `TRUE`Чтобы включить индикатора; `FALSE` для отключения индикатора и удаляет его из `CTaskDialog`.  
  
 [in] `nMarqueeSpeed`  
 Целое число, указывающее скорость индикатора.  
  
### <a name="remarks"></a>Примечания  
 Под основной текст появится индикатора `CTaskDialog Class`.  
  
 Используйте `nMarqueeSpeed` скорости индикатора; большего значения указывают на более низкой скорости. Значение 0 для `nMarqueeSpeed` делает индикатора скорости по умолчанию для перемещения [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос Если `nMarqueeSpeed` меньше 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#4;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="a-namesetprogressbarpositiona--ctaskdialogsetprogressbarposition"></a><a name="setprogressbarposition"></a>CTaskDialog::SetProgressBarPosition  
 Регулирует положение индикатора хода выполнения.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nProgressPos`  
 Позиция для индикатора хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос Если `nProgressPos` не находится в диапазоне панель хода выполнения. Можно изменить диапазон панель хода выполнения с [CTaskDialog::SetProgressBarRange](#setprogressbarrange).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#4;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="a-namesetprogressbarrangea--ctaskdialogsetprogressbarrange"></a><a name="setprogressbarrange"></a>CTaskDialog::SetProgressBarRange  
 Настройка диапазона индикатора хода выполнения.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRangeMin`  
 Нижняя граница индикатора хода выполнения.  
  
 [in] `nRangeMax`  
 Верхняя граница индикатора хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Положение индикатора хода выполнения — относительно `nRangeMin` и `nRangeMax`. Например если `nRangeMin` — 50 и `nRangeMax` — 100, положение 75 находится на равном расстоянии вдоль индикатора. Используйте [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) Чтобы установить позицию индикатора хода выполнения.  
  
 Для отображения индикатора выполнения, параметр `TDF_SHOW_PROGRESS_BAR` должна быть включена и `TDF_SHOW_MARQUEE_PROGRESS_BAR` не должен быть включен. Этот метод автоматически устанавливает `TDF_SHOW_PROGRESS_BAR` и очищает `TDF_SHOW_MARQUEE_PROGRESS_BAR`. Используйте [CTaskDialog::SetOptions](#setoptions) вручную изменить параметры для этого экземпляра [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md).  
  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос Если `nRangeMin` — не менее `nRangeMax`. Этот метод вызывает исключение, если `CTaskDialog` уже отображается и имеет индикатор выполнения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#4;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="a-namesetprogressbarstatea--ctaskdialogsetprogressbarstate"></a><a name="setprogressbarstate"></a>CTaskDialog::SetProgressBarState  
 Задает состояние индикатора хода выполнения и отображает его на `CTaskDialog`.  
  
```  
void SetProgressBarState(int nState = PBST_NORMAL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nState`  
 Состояние индикатора хода выполнения. Возможные значения см.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос Если `CTaskDialog` уже отображается и имеет индикатор выполнения.  
  
 В следующей таблице перечислены возможные значения для `nState`. Во всех этих случаях индикатор будет заливка цветом регулярных до достижения позиции указанном табуляции. На этом этапе он изменится цвет на основе состояния.  
  
 PBST_NORMAL  
 После выполнения заполнится, `CTaskDialog` не изменяет цвет полосы. По умолчанию регулярные цвет имеет зеленый цвет.  
  
 PBST_ERROR  
 После выполнения заполнится, `CTaskDialog` изменяет цвет полосы цвет ошибок. По умолчанию это красным.  
  
 PBST_PAUSED  
 После выполнения заполнится, `CTaskDialog` изменяет цвет полосы приостановленных цвет. По умолчанию это желтый.  
  
 Можно задать, где прекращается индикатор [CTaskDialog::SetProgressBarPosition](#setprogressbarposition).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#4;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="a-namesetradiobuttonoptionsa--ctaskdialogsetradiobuttonoptions"></a><a name="setradiobuttonoptions"></a>CTaskDialog::SetRadioButtonOptions  
 Включает или отключает переключатель.  
  
```  
void SetRadioButtonOptions(
    int nRadioButtonID,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRadioButtonID`  
 Идентификатор переключателя.  
  
 [in] `bEnabled`  
 `TRUE`Чтобы включить переключатель; `FALSE` для отключения переключателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос Если `nRadioButtonID` не является допустимым Идентификатором для переключателя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namesetverificationcheckboxa--ctaskdialogsetverificationcheckbox"></a><a name="setverificationcheckbox"></a>CTaskDialog::SetVerificationCheckbox  
 Задает состояние проверки элемента флажок проверки.  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bChecked`  
 `TRUE`для проверки установлен флажок, когда `CTaskDialog` отображается; `FALSE` провести проверку флажок снят, когда `CTaskDialog` отображается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#5;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="a-namesetverificationcheckboxtexta--ctaskdialogsetverificationcheckboxtext"></a><a name="setverificationcheckboxtext"></a>CTaskDialog::SetVerificationCheckboxText  
 Задает текст, который отображается справа от флажка проверки.  
  
```  
void SetVerificationCheckboxText(CString& strVerificationText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strVerificationText`  
 Текст, этот метод отображает рядом с флажком проверки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает исключение с [УБЕДИТЕСЬ, что](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) макрос, если этот экземпляр `CTaskDialog Class` уже отображается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#5;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="a-namesetwindowtitlea--ctaskdialogsetwindowtitle"></a><a name="setwindowtitle"></a>CTaskDialog::SetWindowTitle  
 Задает заголовок `CTaskDialog`.  
  
```  
void SetWindowTitle(CString& strWindowTitle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strWindowTitle`  
 Новый заголовок для `CTaskDialog`.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-nameshowdialoga--ctaskdialogshowdialog"></a><a name="showdialog"></a>CTaskDialog::ShowDialog  
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
 [in] `strContent`  
 Строка, используемая для создания содержимого `CTaskDialog`.  
  
 [in] `strMainInstruction`  
 Основные инструкции из `CTaskDialog`.  
  
 [in] `strTitle`  
 Название `CTaskDialog`.  
  
 [in] `nIDCommandControlsFirst`  
 Идентификатор строки первой команды.  
  
 [in] `nIDCommandControlsLast`  
 Идентификатор строки последней команды.  
  
 [in] `nCommonButtons`  
 Маска кнопок, чтобы добавить `CTaskDialog`.  
  
 [in] `nTaskDialogOptions`  
 Набор параметров для `CTaskDialog`.  
  
 [in] `strFooter`  
 Строка для использования в качестве нижнего колонтитула.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, соответствующее выбора, сделанного пользователем.  
  
### <a name="remarks"></a>Примечания  
 Этот статический метод позволяет создавать экземпляр `CTaskDialog Class` без явного создания `CTaskDialog` объекта в коде. Из-за не `CTaskDialog` объекта, не может вызывать остальные методы из `CTaskDialog` при использовании этого метода для отображения `CTaskDialog` для пользователя.  
  
 Этот метод создает кнопку командные элементы управления с использованием данных из файла ресурсов приложения. В таблице строки в файле ресурсов имеет несколько строк с помощью связанных строковых идентификаторов. Этот метод добавляет элемент управления кнопки команд для всех записей в таблице строк между `nIDCommandControlsFirst` и `nCommandControlsLast`включительно. Для этих элементов управления кнопки команды строка в таблице строк — заголовок элемента управления и идентификатор строки является идентификатором элемента управления.  
  
 В разделе [CTaskDialog::SetOptions](#setoptions) список допустимых параметров.  
  
 `CTaskDialog` Закрывается, когда пользователь выбирает общие кнопки, элемент управления command link, или закрывает `CTaskDialog`. Возвращает значение идентификатора, указывающее, как пользователь закрыл диалоговое окно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTaskDialog&#1;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="a-nametaskdialogcallbacka--ctaskdialogtaskdialogcallback"></a><a name="taskdialogcallback"></a>CTaskDialog::TaskDialogCallback  
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
 [in] `hwnd`  
 Дескриптор `m_hWnd` структура для `CTaskDialog`.  
  
 [in] `uNotification`  
 Код уведомления, указывающее созданного сообщения.  
  
 [in] `wParam`  
 Дополнительные сведения о сообщении.  
  
 [in] `lParam`  
 Дополнительные сведения о сообщении.  
  
 [in] `dwRefData`  
 Указатель на `CTaskDialog` объект, к которому применяется сообщение обратного вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Зависит от кода уведомления. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию `TaskDialogCallback` обрабатывает конкретное сообщение и затем вызывает соответствующий метод [класс CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Например, в ответ на `TDN_BUTTON_CLICKED` сообщение, `TaskDialogCallback` вызовов [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick).  
  
 Значения для `wParam` и `lParam` зависят от конкретного создаваемого сообщения. Это возможно, одно или оба этих значения, быть пустым. В следующей таблице перечислены уведомлений по умолчанию, которые поддерживаются и какие значения `wParam` и `lParam` представления. При переопределении в производном классе этот метод следует реализовать код обратного вызова для каждого сообщения в следующей таблице.  
  
|Сообщение уведомления|Значение `wParam`|Значение `lParam`|  
|--------------------------|--------------------|--------------------|  
|`TDN_CREATED`|Не используется.|Не используется.|  
|`TDN_NAVIGATED`|Не используется.|Не используется.|  
|`TDN_BUTTON_CLICKED`|Кнопки управления идентификатором.|Не используется.|  
|`TDN_HYPERLINK_CLICKED`|Не используется.|Объект [— LPCWSTR](http://msdn.microsoft.com/library/windows/desktop/aa383751) структуру, содержащую ссылку.|  
|`TDN_TIMER`|Время в миллисекундах с момента `CTaskDialog` был создан или сброса таймера.|Не используется.|  
|`TDN_DESTROYED`|Не используется.|Не используется.|  
|`TDN_RADIO_BUTTON_CLICKED`|Идентификатор кнопки радио|Не используется.|  
|`TDN_DIALOG_CONSTRUCTED`|Не используется.|Не используется.|  
|`TDN_VERIFICATION_CLICKED`|1, если флажок установлен, значение 0, если это не так.|Не используется.|  
|`TDN_HELP`|Не используется.|Не используется.|  
|`TDN_EXPANDO_BUTTON_CLICKED`|0, если область расширения свернута; ненулевое значение, если отображается текст расширения.|Не используется.|  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Пошаговое руководство: Добавление CTaskDialog в приложение](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)




