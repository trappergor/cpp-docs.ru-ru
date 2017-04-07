---
title: "Классе CFileDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileDialog
- AFXDLGS/CFileDialog
- AFXDLGS/CFileDialog::CFileDialog
- AFXDLGS/CFileDialog::AddCheckButton
- AFXDLGS/CFileDialog::AddComboBox
- AFXDLGS/CFileDialog::AddControlItem
- AFXDLGS/CFileDialog::AddEditBox
- AFXDLGS/CFileDialog::AddMenu
- AFXDLGS/CFileDialog::AddPlace
- AFXDLGS/CFileDialog::AddPushButton
- AFXDLGS/CFileDialog::AddRadioButtonList
- AFXDLGS/CFileDialog::AddSeparator
- AFXDLGS/CFileDialog::AddText
- AFXDLGS/CFileDialog::ApplyOFNToShellDialog
- AFXDLGS/CFileDialog::DoModal
- AFXDLGS/CFileDialog::EnableOpenDropDown
- AFXDLGS/CFileDialog::EndVisualGroup
- AFXDLGS/CFileDialog::GetCheckButtonState
- AFXDLGS/CFileDialog::GetControlItemState
- AFXDLGS/CFileDialog::GetControlState
- AFXDLGS/CFileDialog::GetEditBoxText
- AFXDLGS/CFileDialog::GetFileExt
- AFXDLGS/CFileDialog::GetFileName
- AFXDLGS/CFileDialog::GetFileTitle
- AFXDLGS/CFileDialog::GetFolderPath
- AFXDLGS/CFileDialog::GetIFileDialogCustomize
- AFXDLGS/CFileDialog::GetIFileOpenDialog
- AFXDLGS/CFileDialog::GetIFileSaveDialog
- AFXDLGS/CFileDialog::GetNextPathName
- AFXDLGS/CFileDialog::GetOFN
- AFXDLGS/CFileDialog::GetPathName
- AFXDLGS/CFileDialog::GetReadOnlyPref
- AFXDLGS/CFileDialog::GetResult
- AFXDLGS/CFileDialog::GetResults
- AFXDLGS/CFileDialog::GetSelectedControlItem
- AFXDLGS/CFileDialog::GetStartPosition
- AFXDLGS/CFileDialog::HideControl
- AFXDLGS/CFileDialog::IsPickFoldersMode
- AFXDLGS/CFileDialog::MakeProminent
- AFXDLGS/CFileDialog::RemoveControlItem
- AFXDLGS/CFileDialog::SetCheckButtonState
- AFXDLGS/CFileDialog::SetControlItemState
- AFXDLGS/CFileDialog::SetControlItemText
- AFXDLGS/CFileDialog::SetControlLabel
- AFXDLGS/CFileDialog::SetControlState
- AFXDLGS/CFileDialog::SetControlText
- AFXDLGS/CFileDialog::SetDefExt
- AFXDLGS/CFileDialog::SetEditBoxText
- AFXDLGS/CFileDialog::SetProperties
- AFXDLGS/CFileDialog::SetSelectedControlItem
- AFXDLGS/CFileDialog::SetTemplate
- AFXDLGS/CFileDialog::StartVisualGroup
- AFXDLGS/CFileDialog::UpdateOFNFromShellDialog
- AFXDLGS/CFileDialog::OnButtonClicked
- AFXDLGS/CFileDialog::OnCheckButtonToggled
- AFXDLGS/CFileDialog::OnControlActivating
- AFXDLGS/CFileDialog::OnFileNameChange
- AFXDLGS/CFileDialog::OnFileNameOK
- AFXDLGS/CFileDialog::OnFolderChange
- AFXDLGS/CFileDialog::OnInitDone
- AFXDLGS/CFileDialog::OnItemSelected
- AFXDLGS/CFileDialog::OnLBSelChangedNotify
- AFXDLGS/CFileDialog::OnShareViolation
- AFXDLGS/CFileDialog::OnTypeChange
- AFXDLGS/CFileDialog::m_ofn
dev_langs:
- C++
helpviewer_keywords:
- CFileDialog class
- common file dialog boxes
- dialog boxes, common
ms.assetid: fda4fd3c-08b8-4ce0-8e9d-7bab23f8c6c0
caps.latest.revision: 47
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
ms.openlocfilehash: 7cde10ee445a719bce6be4167698bd86c46a18c0
ms.lasthandoff: 02/24/2017

---
# <a name="cfiledialog-class"></a>Классе CFileDialog
Инкапсулирует обычное диалоговое окно, используемое для открытия файла или файла операции сохранения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFileDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileDialog::CFileDialog](#cfiledialog)|Создает объект `CFileDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileDialog::AddCheckButton](#addcheckbutton)|Добавляет кнопку возврата в диалоговое окно.|  
|[CFileDialog::AddComboBox](#addcombobox)|Добавляет поле со списком в диалоговом окне.|  
|[CFileDialog::AddControlItem](#addcontrolitem)|Добавляет элемент в контейнерный элемент управления в диалоговом окне.|  
|[CFileDialog::AddEditBox](#addeditbox)|Добавляет текстовое поле диалогового окна.|  
|[CFileDialog::AddMenu](#addmenu)|Добавляет меню диалогового окна.|  
|[CFileDialog::AddPlace](#addplace)|Перегружен. Добавляет папку в список помещает доступных пользователю для открытия или сохранения элементов.|  
|[CFileDialog::AddPushButton](#addpushbutton)|Добавляет кнопки диалогового окна.|  
|[CFileDialog::AddRadioButtonList](#addradiobuttonlist)|Добавляет группе (также известный как переключатель) диалогового окна.|  
|[CFileDialog::AddSeparator](#addseparator)|Добавляет разделитель в диалоговое окно.|  
|[CFileDialog::AddText](#addtext)|Добавляет текст в диалоговое окно.|  
|[CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog)|Обновляет состояние `CFileDialog` в соответствии с параметрами и флаги, хранящиеся в `m_ofn` переменной-члена.|  
|[CFileDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|  
|[CFileDialog::EnableOpenDropDown](#enableopendropdown)|Включает раскрывающегося списка на **откройте** или **Сохранить** кнопка в диалоговом окне.|  
|[CFileDialog::EndVisualGroup](#endvisualgroup)|Останавливает Добавление элементов в группу visual в диалоговом окне.|  
|[CFileDialog::GetCheckButtonState](#getcheckbuttonstate)|Возвращает текущее состояние проверки кнопки (флажок) в диалоговом окне.|  
|[CFileDialog::GetControlItemState](#getcontrolitemstate)|Возвращает текущее состояние элемента в элементе управления контейнера, в диалоговом окне.|  
|[CFileDialog::GetControlState](#getcontrolstate)|Возвращает текущую видимость и состояниях данного элемента управления.|  
|[CFileDialog::GetEditBoxText](#geteditboxtext)|Получает текущий текст в поле ввода.|  
|[CFileDialog::GetFileExt](#getfileext)|Возвращает расширение выбранного файла.|  
|[CFileDialog::GetFileName](#getfilename)|Возвращает имя файла, выбранного файла.|  
|[CFileDialog::GetFileTitle](#getfiletitle)|Возвращает название выбранного файла.|  
|[CFileDialog::GetFolderPath](#getfolderpath)|Возвращает путь в настоящее время открыть папку или каталог для стиле проводника **откройте** или **Сохранить как** общее диалоговое окно.|  
|[CFileDialog::GetIFileDialogCustomize](#getifiledialogcustomize)|Возвращает внутренний объект COM для настраиваемый `CFileDialog` объекта.|  
|[CFileDialog::GetIFileOpenDialog](#getifileopendialog)|Возвращает внутренний объект COM для `CFileDialog` , используемая в качестве **откройте** диалоговое окно файла.|  
|[CFileDialog::GetIFileSaveDialog](#getifilesavedialog)|Возвращает внутренний объект COM для `CFileDialog` , используемая в качестве **Сохранить** диалоговое окно файла.|  
|[CFileDialog::GetNextPathName](#getnextpathname)|Возвращает полный путь Далее выбранного файла.|  
|[CFileDialog::GetOFN](#getofn)|Извлекает `OPENFILENAME` структуры `CFileDialog` объекта.|  
|[CFileDialog::GetPathName](#getpathname)|Возвращает полный путь выбранного файла.|  
|[CFileDialog::GetReadOnlyPref](#getreadonlypref)|Возвращает состояние только для чтения из выбранного файла.|  
|[CFileDialog::GetResult](#getresult)|Возвращает выбор, внесенные пользователем в диалоговом окне.|  
|[CFileDialog::GetResults](#getresults)|Получает варианты пользователя в диалоговое окно Выбор нескольких элементов.|  
|[CFileDialog::GetSelectedControlItem](#getselectedcontrolitem)|Возвращает определенный элемент из указанного контейнера элементов управления в диалоговом окне.|  
|[CFileDialog::GetStartPosition](#getstartposition)|Возвращает позицию первого элемента списка имен файлов.|  
|[CFileDialog::HideControl](#hidecontrol)|Скрывает элемент управления, указанный в стиле обозревателя **откройте** или **Сохранить как** общее диалоговое окно.|  
|[CFileDialog::IsPickFoldersMode](#ispickfoldersmode)|Определяет, если текущее диалоговое окно в режиме выбора папки.|  
|[CFileDialog::MakeProminent](#makeprominent)|Местах элемента управления в диалоговом окне, чтобы лучше выделялся по сравнению с другими элементами управления, добавленными.|  
|[CFileDialog::RemoveControlItem](#removecontrolitem)|Удаляет элемент из контейнерного элемента управления в диалоговом окне.|  
|[CFileDialog::SetCheckButtonState](#setcheckbuttonstate)|Задает текущее состояние кнопки «Проверка» (флажок) в диалоговом окне.|  
|[CFileDialog::SetControlItemState](#setcontrolitemstate)|Задает текущее состояние элемента в элементе управления контейнера, в диалоговом окне.|  
|[CFileDialog::SetControlItemText](#setcontrolitemtext)|Задает текст элемента управления. Например текст, сопровождающий переключатель или элемента меню.|  
|[CFileDialog::SetControlLabel](#setcontrollabel)|Задает текст, связанный с элементом управления, например текст кнопки или метку поля редактирования.|  
|[CFileDialog::SetControlState](#setcontrolstate)|Задает видимость текущего и состояниях данного элемента управления.|  
|[CFileDialog::SetControlText](#setcontroltext)|Задает текст для указанного элемента управления в стиле обозревателя **откройте** или **Сохранить как** общее диалоговое окно.|  
|[CFileDialog::SetDefExt](#setdefext)|Задает расширение имени файла по умолчанию для обозревателя стиле **откройте** или **Сохранить как** общее диалоговое окно.|  
|[CFileDialog::SetEditBoxText](#seteditboxtext)|Задает текущий текст в поле ввода.|  
|[CFileDialog::SetProperties](#setproperties)|Предоставляет хранилище свойств, которое определяет значения по умолчанию для сохраняемого элемента.|  
|[CFileDialog::SetSelectedControlItem](#setselectedcontrolitem)|Задает состояние выбранного какой-либо элемент в группе или в поле со списком, в диалоговом окне.|  
|[CFileDialog::SetTemplate](#settemplate)|Задает поле шаблона диалогового окна для `CFileDialog` объекта.|  
|[CFileDialog::StartVisualGroup](#startvisualgroup)|Объявляет visual группы в диалоговом окне. Последующие вызовы к любому методу «добавить» добавить эти элементы в эту группу.|  
|[CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog)|Обновляет данные, хранящиеся в `m_ofn` переменную-член для соответствия текущему состоянию диалоговым окном файла.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileDialog::OnButtonClicked](#onbuttonclicked)|Вызывается при нажатии кнопки.|  
|[CFileDialog::OnCheckButtonToggled](#oncheckbuttontoggled)|Вызывается, когда флажок или снятии флажка.|  
|[CFileDialog::OnControlActivating](#oncontrolactivating)|Вызывается при активной элемента управления.|  
|[CFileDialog::OnFileNameChange](#onfilenamechange)|Обрабатывает `WM_NOTIFY CDN_SELCHANGE` сообщение.|  
|[CFileDialog::OnFileNameOK](#onfilenameok)|Проверяет, введенное в диалоговом окне имя файла.|  
|[CFileDialog::OnFolderChange](#onfolderchange)|Обрабатывает `WM_NOTIFY CDN_FOLDERCHANGE` сообщение.|  
|[CFileDialog::OnInitDone](#oninitdone)|Обрабатывает `WM_NOTIFY CDN_INITDONE` сообщение.|  
|[CFileDialog::OnItemSelected](#onitemselected)|Вызывается, когда выбран элемент контейнера.|  
|[CFileDialog::OnLBSelChangedNotify](#onlbselchangednotify)|Позволяет выполнять пользовательские действия при изменении выбора файла.|  
|[CFileDialog::OnShareViolation](#onshareviolation)|Маркеры имеют нарушений.|  
|[CFileDialog::OnTypeChange](#ontypechange)|Обрабатывает `WM_NOTIFY CDN_TYPECHANGE` сообщение.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileDialog::m_ofn](#m_ofn)|Windows `OPENFILENAME` структуры. Предоставляет доступ к параметрам поле диалогового окна основной файл.|  
  
## <a name="remarks"></a>Примечания  
 Общие диалоговые окна файлов позволяют реализовать Выбор файла диалоговые окна, например, **открыть файл** и **Сохранить как**, способом, совместимым со стандартами Windows.  
  
 Можно использовать `CFileDialog` как есть, без конструктора, предоставленного также можно вывести собственный класс диалогового окна из `CFileDialog` и создание конструктора в соответствии с потребностями. В любом случае эти диалоговые будет работать как стандартные диалоговые окна MFC, поскольку они являются производными от [CCommonDialog класса](../../mfc/reference/ccommondialog-class.md). `CFileDialog`зависит от COMMDLG. DLL-файл, включенный в Windows.  
  
 Внешний вид и функциональные возможности `CFileDialog` с [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] отличаются от более ранних версий Windows. Значение по умолчанию `CFileDialog` автоматически использует новый [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] стиля без изменения кода при компиляции программы и выполнения в разделе [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Используйте `bVistaStyle` параметр в конструкторе, чтобы переопределить это автоматическое обновление вручную. Исключение для автоматического обновления — настраиваемые диалоговые окна. Они не преобразуются в новый стиль. Дополнительные сведения о конструкторе см. в разделе [CFileDialog::CFileDialog](#cfiledialog).  
  
> [!NOTE]
>  Идентификатор системы управления отличается в [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] из более ранних версий Windows, при использовании `CFileDialog`. Необходимо обновить все ссылки на `CFileDialog` элементов управления в коде, прежде чем можно будет перенести проекта из более ранней версии Windows.  
  
 Некоторые `CFileDialog` методы не поддерживаются в разделе [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Проверьте раздел отдельный метод для получения сведений о том, поддерживается ли метод. Кроме того, следующие унаследованные функции не поддерживаются в разделе [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)  
  
- [CDialog::OnSetFont](../../mfc/reference/cdialog-class.md#onsetfont)  
  
 Сообщения windows для `CFileDialog` класс зависит от операционной системы вы используете. Например, Windows XP не поддерживает [CDialog::OnCancel](../../mfc/reference/cdialog-class.md#oncancel) и [CDialog::OnOK](../../mfc/reference/cdialog-class.md#onok) для `CFileDialog` класса. Тем не менее [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] их поддерживает. Дополнительные сведения о различных сообщений, которые создаются и порядок, в котором они поступают в разделе [CFileDialog образец: порядок ведения журнала событий](../../visual-cpp-samples.md).  
  
 Для использования `CFileDialog` объекта, сначала создайте объект с помощью `CFileDialog` конструктор. После отправки диалоговом окне можно задать или изменить какое-либо значение [CFileDialog::m_ofn](#m_ofn) структуры для инициализации значения или состояния элементов управления диалогового окна. `m_ofn` Структуры имеет тип `OPENFILENAME`. Дополнительные сведения см. в разделе [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 После инициализации диалоговыми окнами, вызовите [CFileDialog::DoModal](#domodal) поле метод для отображения диалогового окна, чтобы пользователь может ввести путь и имя файла. `DoModal`Возвращает ли пользователь нажал кнопку Cancel (IDCANCEL) или ОК (IDOK). Если `DoModal` возвращает IDOK, можно использовать один из `CFileDialog` поместить открытый член функции для извлечения информации в пользователем.  
  
> [!NOTE]
>  В разделе [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], несколько вызовов [IFileDialog::SetFileTypes](http://msdn.microsoft.com/library/windows/desktop/bb775980) приводит к ошибке. Второй вызов `SetFileTypes` для всех экземпляров `CFileDialog` вернет `E_UNEXPECTED` в [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Некоторые `CFileDialog` вызов функции, метод `SetFileTypes`. Например, два вызова к `CFileDialog::DoModal` для одного экземпляра `CFileDialog` создает [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c).  
  
 `CFileDialog`включает несколько защищенных членов, которые позволяют выполнять пользовательскую обработку нарушений общего ресурса, проверка правильности имени файла и уведомления об изменении списков. Эти защищенные члены — функции обратного вызова, большинство приложений, у которых нет в использовании, поскольку по умолчанию обработка выполняется автоматически. Записи схемы сообщений для этих функций не требуются, поскольку они являются стандартных виртуальных функций.  
  
 Можно использовать окна [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функции, чтобы определить, произошла ли ошибка во время инициализации диалогового окна и для получения дополнительных сведений об ошибке.  
  
 Уничтожение `CFileDialog` объектов обрабатывается автоматически. Необходимо вызвать [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog).  
  
 Чтобы пользователь мог выбрать несколько файлов, установите `OFN_ALLOWMULTISELECT` флаг перед вызовом метода `DoModal`. Необходимо предоставить свои собственные буфера имя файла для размещения возвращаемый список несколько имен файлов. Это можно сделать путем замены `m_ofn.lpstrFile` указатель на буфер, выделено, после создания `CFileDialog`, но перед вызовом метода `DoModal`.  
  
 Кроме того, необходимо установить `m_ofn.nMaxFile` с помощью число символов в буфере, на который указывает `m_ofn.lpstrFile`. Если задать максимальное количество файлов для `n`, необходимый размер буфера — `n * (_MAX_PATH + 1) + 1`. Первый элемент, возвращается в буфер — путь к папке, где были выбраны файлы. Для [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]-строк имен каталогов и файлов диалоговых окнах стиль, завершающуюся значением null, дополнительный символ null после последнего имени файла. Этот формат позволяет диалоговых окнах стиль проводника для возврата длинные имена файлов, содержащие пробелы. Для старого стиля диалоговых окон строк имен каталогов и файлов разделенных пробелами и функция использует короткие имена файлов пробелами.  
  
 Ниже приведен пример, как использовать буфер для получения и списка несколько имен файлов.  
  
 [!code-cpp[NVC_MFCFiles&#23;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 Чтобы изменить размер буфера в ответ на выбор несколько имен файлов, необходимо создать новый класс из `CFileDialog` и Переопределите [CFileDialog::OnFileNameChange](#onfilenamechange) метод.  
  
 Если необходимо наследовать новый класс из `CFileDialog`, можно использовать схемы сообщений для обработки сообщения. Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CFileDialog`, Добавление нового класса схемы сообщений и предоставляют функции-члены для новых сообщений. Необходимо предоставить функция-ловушка для настройки диалогового окна.  
  
 Чтобы настроить диалоговое окно, создайте класс, производный от `CFileDialog`, предоставить шаблон пользовательского диалогового окна и добавить схемы сообщений для обработки сообщений уведомления из расширенных элементов управления. Передайте все необработанные сообщения базового класса. Необходимо настроить функцию-обработчик.  
  
 При использовании [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] стиль `CFileDialog`, нельзя использовать схемы сообщений и шаблонов диалоговых окон. Вместо этого необходимо использовать COM-интерфейсы для сходных функциональных возможностей.  
  
 Дополнительные сведения об использовании `CFileDialog`, в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFileDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="addcheckbutton"></a>CFileDialog::AddCheckButton  
 Добавляет кнопку возврата в диалоговое окно.  
  
```  
HRESULT AddCheckButton(
    DWORD dwIDCtl,  
    const CString& strLabel,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор "Проверить" для добавления.  
  
 `strLabel`  
 Имя кнопки проверки.  
  
 `bChecked`  
 Логическое значение, указывающее текущее состояние "Проверить". `TRUE`Если флажок установлен; `FALSE` в противном случае  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addcombobox"></a>CFileDialog::AddComboBox  
 Добавляет поле со списком в диалоговом окне.  
  
```  
HRESULT AddComboBox(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор поле со списком для добавления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addcontrolitem"></a>CFileDialog::AddControlItem  
 Добавляет элемент в контейнерный элемент управления в диалоговом окне.  
  
```  
HRESULT AddControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор контейнерного элемента управления для добавления элемента.  
  
 `dwIDItem`  
 Идентификатор элемента.  
  
 `strLabel`  
 Текст элемента.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addeditbox"></a>CFileDialog::AddEditBox  
 Добавляет текстовое поле диалогового окна.  
  
```  
HRESULT AddEditBox(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор поля для добавления.  
  
 `strText`  
 Имя поля редактирования.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addmenu"></a>CFileDialog::AddMenu  
 Добавляет меню диалогового окна.  
  
```  
HRESULT AddMenu(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор меню для добавления.  
  
 `strLabel`  
 Имя меню.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addplace"></a>CFileDialog::AddPlace  
 Добавляет папку в список помещает доступных пользователю для открытия или сохранения элементов.  
  
```  
void AddPlace(
    LPCWSTR lpszFolder,  
    FDAP fdap = FDAP_TOP) throw();

 
void AddPlace(
    IShellItem* psi,  
    FDAP fdap = FDAP_TOP) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFolder`  
 Путь к папке должен быть доступным для пользователя. Это может быть только папки.  
  
 `fdap`  
 Указывает, где папка размещается в пределах списка.  
  
 `psi`  
 Указатель на экземпляр интерфейса IShellItem, представляющий папки должны быть доступны пользователю. Это может быть только папки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addpushbutton"></a>CFileDialog::AddPushButton  
 Добавляет кнопки диалогового окна.  
  
```  
HRESULT AddPushButton(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор кнопки для добавления.  
  
 `strLabel`  
 Имя кнопки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addradiobuttonlist"></a>CFileDialog::AddRadioButtonList  
 Добавляет группе (также известный как переключатель) диалогового окна.  
  
```  
HRESULT AddRadioButtonList(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор группы переключателей для добавления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addseparator"></a>CFileDialog::AddSeparator  
 Добавляет разделитель в диалоговое окно.  
  
```  
HRESULT AddSeparator(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Добавьте идентификатор разделителя.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addtext"></a>CFileDialog::AddText  
 Добавляет текст в диалоговое окно.  
  
```  
HRESULT AddText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор для добавления текста.  
  
 `strText`  
 Имя текста.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="applyofntoshelldialog"></a>CFileDialog::ApplyOFNToShellDialog  
 Обновляет текущее состояние [CFileDialog](../../mfc/reference/cfiledialog-class.md) на основе значений, хранящихся в `m_ofn` структуру данных.  
  
```  
void ApplyOFNToShellDialog();
```  
  
### <a name="remarks"></a>Примечания  
 В версиях Windows до [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], член [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx) структуру данных постоянно был синхронизирован с состоянием `CFileDialog`. Любые изменения в [m_ofn](#m_ofn) переменной-члена были немедленно отражаются в состоянии диалогового окна. Кроме того, любые изменения состояния диалогового окна немедленно обновить `m_ofn` переменной-члена.  
  
 В [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], значения в `m_ofn` переменной-члена и состояние `CFileDialog` , не обязательно быть синхронизирована. Эта функция принудительно состояние `CFileDialog` обновляться в соответствии `m_ofn` структуры. Эта функция автоматически во время вызовов Windows [CFileDialog::DoModal](#domodal).  
  
 Дополнительные сведения об использовании `CFileDialog` класса под [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], в разделе [класса CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Пример  
  В примере показано [CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog).  
  
##  <a name="cfiledialog"></a>CFileDialog::CFileDialog  
 Эта функция вызывается для создания стандартного диалогового окна файла Windows.  
  
```  
explicit CFileDialog(
    BOOL bOpenFileDialog,  
    LPCTSTR lpszDefExt = NULL,  
    LPCTSTR lpszFileName = NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter = NULL,  
    CWnd* pParentWnd = NULL,  
    DWORD dwSize = 0,  
    BOOL bVistaStyle = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bOpenFileDialog`  
 Параметр, указывающий тип диалогового окна для создания. Задайте для него значение `TRUE` для создания **Открытие файла** диалоговое окно. Задайте для него значение `FALSE` для создания **сохранить файл как** диалоговое окно.  
  
 [in] `lpszDefExt`  
 Суффикс для имени файла по умолчанию. Если пользователь не содержит известного расширения (у которого есть связь на компьютере пользователя) в поле имя файла, заданный модуль `lpszDefExt` , автоматически добавляется к имени файла. Если этот параметр равен `NULL`, расширение не добавляется.  
  
 [in] `lpszFileName`  
 Имя исходного файла, которое отображается в поле имя файла. Если `NULL`, имя исходного файла не отображается.  
  
 [in] `dwFlags`  
 Сочетание одного или нескольких флагов, которые можно использовать для настройки диалогового окна. Описание этих флагов см. в разделе [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Если изменить `m_ofn.Flags` структуры элементов, используйте оператор побитового или изменений, чтобы сохранить поведение по умолчанию.  
  
 [in] `lpszFilter`  
 Ряд пары строк, которые задают фильтры можно применять к файлу. При указании фильтров файлов только те файлы, которые соответствуют условиям фильтра будут отображаться в списке файлов. Дополнительные сведения о работе с фильтрами файлов см.  
  
 [in] `pParentWnd`  
 Указатель на родительский окно или окно владельца диалогового окна файла.  
  
 [in] `dwSize`  
 Размер `OPENFILENAME` структуры. Это значение зависит от версии операционной системы. MFC позволяет определить соответствующий вид диалогового окна для создания этого параметра (например, новые [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] диалоговых окон вместо NT4 диалоговые окна). Размер по умолчанию 0 означает, что код MFC определит размер поле правильные диалогового окна для использования в зависимости от версии операционной системы, на котором выполняется программа.  
  
 [in] `bVistaStyle`  
 **Примечание** этот параметр доступен в Visual Studio 2008 и более поздних и оно будет вызывать диалоговое окно Новый стиль, чтобы использовать только в том случае, если вы используете [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] или более поздней версии.  
  
 Параметр, который задает стиль в диалоговом окне файла. Задайте для него значение `TRUE` для использования новых диалоговых стиль Vista. В противном случае будет использоваться старый стиль диалоговых окон. В разделе Примечания для получения дополнительной информации выполнении Vista.  
  
### <a name="remarks"></a>Примечания  
 Либо **Открытие файла** или **сохранить файл как** создается диалоговое окно, в зависимости от значения `bOpenFileDialog`.  
  
 Указание расширения по умолчанию с помощью `lpszDefExt` может не дать поведение, которое предполагается, что, поскольку редко является предсказуемым, какие расширения имеют сопоставления файлов на компьютере пользователя. Если необходим больший контроль над добавления расширения по умолчанию, можно наследовать класс от `CFileDialog`и Переопределите `CFileDialog::OnFileNameOK` метод, чтобы выполнить собственную обработку расширения.  
  
 Чтобы разрешить пользователю выбирать несколько файлов, установите `OFN_ALLOWMULTISELECT` флаг перед вызовом метода [DoModal](#domodal). Необходимо предоставить свои собственные буфера имя файла для хранения возвращаемый список несколько имен файлов. Это можно сделать путем замены `m_ofn.lpstrFile` указатель на буфер, выделено, после создания [CFileDialog](../../mfc/reference/cfiledialog-class.md), но перед вызовом метода `DoModal`. Кроме того, необходимо установить `m_ofn.nMaxFile` число символов в буфере, на который указывает `m_ofn.lpstrFile`. Если задать максимальное количество файлов для `n`, необходимый размер буфера — `n`*(_MAX_PATH + 1) + 1. Пример:  
  
 [!code-cpp[NVC_MFCFiles&#23;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 Чтобы разрешить пользователю изменять размер диалоговое окно с стиле проводника с помощью мыши или клавиатуры, установите `OFN_ENABLESIZING` флаг. Этот флаг установлен необходим только в том случае, если указать процедуру обработки или пользовательский шаблон. Флаг работает только с диалоговым окном в стиле проводника; Невозможно изменить размеры диалоговые окна старого стиля.  
  
 `lpszFilter` Параметр используется для определения типа имени файла, файл должен иметь для отображения в списке файлов. Первая строка в паре строка описывает фильтр; Вторая строка указывает расширение имени файла для использования. Можно указать несколько расширений, используя в качестве разделителя точку с запятой (символ «;»). Строка заканчивается с двумя "|" символов, за которыми следует `NULL` символов. Можно также использовать [CString](../../atl-mfc-shared/using-cstring.md) объект для этого параметра.  
  
 Например [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] позволяет пользователям открывать файлы с расширениями .xlc (диаграмма) или xls (лист), среди прочих. Фильтр для Excel может быть записан следующим образом:  
  
 [!code-cpp[NVC_MFCFiles&#24;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_2.cpp)]  
  
 Тем не менее, если вы планируете использовать эту строку, чтобы напрямую обновлять `OPENFILENAME` структуры, следует заканчивать строки символом null '\0' вместо вертикальные полосы ("|").  
  
 `bVistaStyle` Параметр применим только при выполнении [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. В более ранних версиях Windows этот параметр учитывается. Если `bVistaStyle` равен `TRUE`, при компиляции программы с [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] или более поздней версии, по-новому Vista **диалоговое окно файла** будет использоваться. В противном случае — предыдущим стилем MFC **диалоговое окно файла** будет использоваться.  
  
 Шаблоны диалоговых окон не поддерживаются на основе диалоговых окон`bVistaStyle`  
  
### <a name="example"></a>Пример  
  В примере показано [CFileDialog::DoModal](#domodal).  
  
##  <a name="domodal"></a>CFileDialog::DoModal  
 Эта функция вызывается для отображения Windows общего файлового диалогового и разрешить пользователю просматривать файлы и каталоги и введите имя файла.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **IDOK** или **IDCANCEL**. Если **IDCANCEL** будет возвращен, вызовите Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функцию, чтобы определить, произошла ли ошибка.  
  
 **IDOK** и **IDCANCEL** константы, которые указывают, выбрал ли пользователь кнопку OK или "Отмена".  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные параметры диалогового окна файла, задав члены **m_ofn** структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Например, если вы хотите разрешить пользователю выбирать несколько файлов, установите `OFN_ALLOWMULTISELECT` флаг перед вызовом метода `DoModal`, как показано в примере кода в этом разделе.  
  
 Когда пользователь нажимает кнопку OK или "Отмена" диалогового окна или выбирает закрытия параметр в диалоговом элемент управления меню, управление возвращается в приложение. Затем можно вызвать другие функции-члены для получения параметров или сведения о входных данных пользователя в диалоговом окне.  
  
 `DoModal`является виртуальной функцией переопределения из класса `CDialog`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles&#25;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_3.cpp)]  
  
##  <a name="enableopendropdown"></a>CFileDialog::EnableOpenDropDown  
 Позволяет раскрывающегося списка при открытии или «сохранить» в диалоговом окне.  
  
```  
HRESULT EnableOpenDropDown(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор из раскрывающегося списка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="endvisualgroup"></a>CFileDialog::EndVisualGroup  
 Останавливает Добавление элементов в группу visual в диалоговом окне.  
  
```  
HRESULT EndVisualGroup();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если выполнено успешно; в противном случае — значение ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcheckbuttonstate"></a>CFileDialog::GetCheckButtonState  
 Получает текущее состояние проверки кнопки (флажок) в диалоговом окне.  
  
```  
HRESULT GetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL& bChecked);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор флажок.  
  
 `bChecked`  
 Состояние флажка. `TRUE`Указывает, отмеченный; `FALSE` указывает флажок снят.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcontrolitemstate"></a>CFileDialog::GetControlItemState  
 Получает текущее состояние элемента в элементе управления контейнера, в диалоговом окне.  
  
```  
HRESULT GetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор контейнерного элемента управления.  
  
 `dwIDItem`  
 Идентификатор элемента.  
  
 `dwState`  
 Ссылка на переменную, которая получает одно из нескольких значений из перечисления CDCONTROLSTATE, который указывает текущее состояние элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcontrolstate"></a>CFileDialog::GetControlState  
 Получает текущую видимость и состояниях данного элемента управления.  
  
```  
HRESULT GetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор элемента управления.  
  
 `dwState`  
 Ссылка на переменную, которая получает одно или несколько значений из перечисления CDCONTROLSTATE, который указывает текущее состояние элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="geteditboxtext"></a>CFileDialog::GetEditBoxText  
 Извлекает текущий текст в поле ввода.  
  
```  
HRESULT GetEditBoxText(
    DWORD dwIDCtl,  
    CString& strText);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор поля ввода.  
  
 `strText`  
 Текстовое значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getfileext"></a>CFileDialog::GetFileExt  
 Эта функция вызывается для получения расширения имени файла, введенного в диалоговом окне.  
  
```  
CString GetFileExt() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расширение имени файла.  
  
### <a name="remarks"></a>Примечания  
 Например если указанное имя файла является данных. TXT, `GetFileExt` возвращает «TXT».  
  
 Если `m_ofn.Flags` имеет `OFN_ALLOWMULTISELECT` флаг установлен, эта строка содержит последовательность нулем строк с первой строки, являющейся путь к каталогу файловой группы выбранного, за которым следуют имена всех файлов, выбранных пользователем. Для получения пути файла, используйте [GetStartPosition](#getstartposition) и [GetNextPathName](#getnextpathname) функции-члены.  
  
##  <a name="getfilename"></a>CFileDialog::GetFileName  
 Эта функция вызывается для получения имени файла, введенного в поле имя.  
  
```  
CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя файла  
  
### <a name="remarks"></a>Примечания  
 Имя файла содержит префикс и расширение. Например `GetFileName` возвращает «текст. DAT» для файла C:\FILES\TEXT.DAT.  
  
 Если `m_ofn.Flags` имеет `OFN_ALLOWMULTISELECT` набор флагов, следует вызвать [GetStartPosition](#getstartposition) и [GetNextPathName](#getnextpathname) для получения пути файла.  
  
##  <a name="getfiletitle"></a>CFileDialog::GetFileTitle  
 Эта функция вызывается для получения заголовка файла, введенных в диалоговом окне.  
  
```  
CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Заголовок файла.  
  
### <a name="remarks"></a>Примечания  
 Заголовок файла содержит только его префикса, без пути или расширения. Например `GetFileTitle` для файла C:\FILES\TEXT.DAT возвратит «TEXT».  
  
 Если `m_ofn.Flags` имеет `OFN_ALLOWMULTISELECT` флаг установлен, эта строка содержит последовательность нулем строк с первой строки, являющейся путь к каталогу файловой группы выбранного, за которым следуют имена всех файлов, выбранных пользователем. По этой причине использовать [GetStartPosition](#getstartposition) и [GetNextPathName](#getnextpathname) функции-члены для получения следующего имени файла в списке.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileDialog::DoModal](#domodal).  
  
##  <a name="getfolderpath"></a>CFileDialog::GetFolderPath  
 Вызовите эту функцию-член для получения пути, открытые в настоящий момент папки или каталога для стиле проводника открыть или сохранить как стандартным диалоговым окном.  
  
```  
CString GetFolderPath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий открытые папки или каталога.  
  
### <a name="remarks"></a>Примечания  
 Диалоговое окно должен быть создан с помощью **OFN_EXPLORER** стиль; в противном случае, метод завершится с утверждение.  
  
 Этот метод можно вызывать только в том случае, пока откроется диалоговое окно. После закрытия диалогового эта функция не будет работать, и метод завершится с утверждение.  
  
##  <a name="getifiledialogcustomize"></a>CFileDialog::GetIFileDialogCustomize  
 Извлекает указатель на внутренний COM-объект для данного [CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
```  
IFileDialogCustomize* GetIFileDialogCustomize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на внутренний объект COM для `CFileDialog`. Это необходимо освободить этот указатель соответствующим образом.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию следует использовать только при выполнении [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] с объекта, имеющего `bVistaStyle` значение `true`. Если эта функция используется при `bVistaStyle` — `false`, будет возвращено `NULL` в режиме выпуска и throw утверждение в режиме отладки.  
  
 Дополнительные сведения о `IFileDialogCustomize` интерфейса см. в разделе [IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912).  
  
### <a name="example"></a>Пример  
 В этом примере извлекается внутренний COM-объект. Чтобы запустить этот пример кода, необходимо скомпилировать его в папке [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!code-cpp[NVC_MFC_CFileDialog&#4;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_4.cpp)]  
  
##  <a name="getifileopendialog"></a>CFileDialog::GetIFileOpenDialog  
 Извлекает указатель на внутренний COM-объект для данного `CFileDialog`.  
  
```  
IFileOpenDialog* GetIFileOpenDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на внутренний объект COM для `CFileDialog`. Это необходимо освободить этот указатель соответствующим образом.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию следует использовать только при выполнении [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] с объекта, имеющего `bVistaStyle` значение `true`. Эта функция возвращает `NULL` Если `CFileDialog` не **откройте** диалоговое окно или если `bVistaStyle` равен `false`. В данном случае последний, функция возвращает только `NULL` в режиме выпуска — в режиме отладки исключений утверждения.  
  
 Дополнительные сведения о `IFileOpenDialog` интерфейса см. в разделе [IFileOpenDialog](http://msdn.microsoft.com/library/windows/desktop/bb775834).  
  
### <a name="example"></a>Пример  
 В этом примере извлекается внутренний COM-объект. Для выполнения этого кода необходимо скомпилировать его в папке [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!code-cpp[NVC_MFC_CFileDialog&#2;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_5.cpp)]  
  
##  <a name="getifilesavedialog"></a>CFileDialog::GetIFileSaveDialog  
 Извлекает указатель на внутренний COM-объект для данного `CFileDialog`.  
  
```  
IFileSaveDialog* GetIFileSaveDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на внутренний объект COM для `CFileDialog`. Это необходимо освободить этот указатель соответствующим образом.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию следует использовать только при выполнении [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] с объекта, имеющего `bVistaStyle` значение `true`. Эта функция возвращает `NULL` Если `CFileDialog` не **Сохранить** диалоговое окно или если `bVistaStyle` равен `false`. В данном случае последний, функция возвращает только `NULL` в режиме выпуска — в режиме отладки исключений утверждения.  
  
 Дополнительные сведения о `IFileSaveDialog` интерфейса см. в разделе [IFileSaveDialog](http://msdn.microsoft.com/library/windows/desktop/bb775688).  
  
### <a name="example"></a>Пример  
 В этом примере извлекается внутренний COM-объект. Чтобы запустить этот пример кода, необходимо скомпилировать его в папке [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!code-cpp[NVC_MFC_CFileDialog&#3;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_6.cpp)]  
  
##  <a name="getnextpathname"></a>CFileDialog::GetNextPathName  
 Эта функция вызывается для получения следующего файла из группы, выбранной в диалоговом окне.  
  
```  
CString GetNextPathName(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetNextPathName` или `GetStartPosition` вызов функции. **NULL** Если был достигнут конец списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный путь к файлу.  
  
### <a name="remarks"></a>Примечания  
 Путь к имени файла содержит заголовок файла, а также весь каталог. Например `GetNextPathName` возвратит «C:\FILES\TEXT. DAT» для файла C:\FILES\TEXT.DAT. Можно использовать `GetNextPathName` в прямой итерации цикла, если установить начальное положение, с помощью вызова `GetStartPosition`.  
  
 Если выделение содержит только один файл, будет возвращаться имя этого файла.  
  
##  <a name="getofn"></a>CFileDialog::GetOFN  
 Получает связанный **OPENFILENAME** структуры.  
  
```  
const OPENFILENAME& GetOFN() const;  
  
OPENFILENAME& GetOFN();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) структуры.  
  
### <a name="remarks"></a>Примечания  
 Использовать второй версии этой функции для инициализации вида **Открытие файла** или **сохранить файл как** диалоговое окно после его создания, но перед отображением с `DoModal` функции-члена. Например, можно установить **lpstrTitle** членом **m_ofn** в заголовок необходимо иметь диалоговое окно.  
  
##  <a name="getpathname"></a>CFileDialog::GetPathName  
 Эта функция вызывается для получения полного пути файла, введенных в диалоговом окне.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный путь к файлу.  
  
### <a name="remarks"></a>Примечания  
 Путь к имени файла содержит заголовок файла, а также весь каталог. Например `GetPathName` возвратит «C:\FILES\TEXT. DAT» для файла C:\FILES\TEXT.DAT.  
  
 Если `m_ofn.Flags` имеет `OFN_ALLOWMULTISELECT` флаг установлен, эта строка содержит последовательность из null teminated строк с первой строки, являющейся путь к каталогу файловой группы выбранного, следуют имена всех файлов, выбранных пользователем. По этой причине использовать [GetStartPosition](#getstartposition) и [GetNextPathName](#getnextpathname) функции-члены для получения следующего имени файла в списке.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileDialog::DoModal](#domodal).  
  
##  <a name="getreadonlypref"></a>CFileDialog::GetReadOnlyPref  
 Вызывайте эту функцию, чтобы определить, выделен ли флажок только для чтения в стандартный файл открыть и сохранить файл как диалоговые окна Windows.  
  
```  
BOOL GetReadOnlyPref() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если установлен флажок только для чтения, в диалоговом окне; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно скрыть, установив флажок «только чтение» `OFN_HIDEREADONLY` стиля в `CFileDialog` конструктора.  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]стиль `CFileDialog` объекты не поддерживают эту функцию. Попытка использовать эту функцию в [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] стиль `CFileDialog` вызовет [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).   
  
##  <a name="getresult"></a>CFileDialog::GetResult  
 Получает выбор, внесенные пользователем в диалоговом окне.  
  
```  
IShellItem* GetResult() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на экземпляр интерфейса IShellItem, представляющий выбора пользователя.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getresults"></a>CFileDialog::GetResults  
 Получает параметры пользователя в диалоговое окно Выбор нескольких элементов.  
  
```  
IShellItemArray* GetResults() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на IShellItemArray, через который может осуществляться элементов, выбранных в диалоговом окне.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getselectedcontrolitem"></a>CFileDialog::GetSelectedControlItem  
 Возвращает определенный элемент из указанного контейнера элемента управления в диалоговом окне.  
  
```  
HRESULT GetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD& dwIDItem);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор контейнерного элемента управления.  
  
 `dwIDItem`  
 Идентификатор элемента, который пользователь выбрал в элементе управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getstartposition"></a>CFileDialog::GetStartPosition  
 Вызовите эту функцию-член для получения позиции первого пути файла в списке, если `m_ofn.Flags` имеет `OFN_ALLOWMULTISELECT` значение флага.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации; **NULL** Если список пуст.  
  
##  <a name="hidecontrol"></a>CFileDialog::HideControl  
 Вызовите эту функцию-член для скрытия указанного элемента управления в стиле проводника открыть или сохранить как стандартным диалоговым окном.  
  
```  
void HideControl(int nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления, чтобы скрыть.  
  
### <a name="remarks"></a>Примечания  
 Диалоговое окно должен быть создан с помощью **OFN_EXPLORER** стиль; в противном случае, функция завершится сбоем с утверждением.  
  
##  <a name="ispickfoldersmode"></a>CFileDialog::IsPickFoldersMode  
 Определяет, является ли текущее диалоговое окно в режиме выбора папки.  
  
```  
BOOL IsPickFoldersMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если диалоговое окно находится в режиме выбора папки; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_ofn"></a>CFileDialog::m_ofn  
 `m_ofn`Структура типа `OPENFILENAME`. Данные в этой структуре представляет текущее состояние `CFileDialog`.  
  
### <a name="remarks"></a>Примечания  
 Использовать эту структуру для инициализации вида **Открытие файла** или **сохранить файл как** после его создания, но перед его отображением диалогового [DoModal](#domodal) метод. Например, можно установить `lpstrTitle` членом `m_ofn` к заголовку необходимо иметь диалоговое окно.  
  
 С [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] стиль [CFileDialog](../../mfc/reference/cfiledialog-class.md), `m_ofn` , не обязательно всегда соответствует состоянию диалогового окна. Она синхронизируется с диалоговым окном в более ранних версиях Windows. В разделе [CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog) и [CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog) Дополнительные сведения о синхронизации `m_ofn` структуры и `CFileDialog` состояния в разделе [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]диалоговых окон стиля не поддерживают определенные элементы и флаги `CFileDialog`. В результате это не повлияет.  
  
 Ниже приведен список членов, не поддерживаемых [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- `lpstrCustomFilter`  
  
- `lpstrInitialDir`  
  
- `lCustData`  
  
- `lpfnHook`  
  
- `lpTemplateName`  
  
 Не поддерживаются следующие флаги и поэтому не действовать при использовании [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] стиль `CFileDialog`:  
  
-   OFN_ENABLEHOOK  
  
-   OFN_ENABLEINCLUDENOTIFY  
  
-   OFN_ENABLETEMPLATE  
  
-   OFN_ENABLETEMPLATEHANDLE  
  
-   OFN_EXPLORER  
  
-   OFN_EXTENSIONDIFFERENT  
  
-   OFN_HIDEREADONLY  
  
-   OFN_LONGNAMES - всегда эффективно на в[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NOLONGNAMES - всегда эффективно off в[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NONETWORKBUTTON - эффективно всегда на в[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_READONLY  
  
-   OFN_SHOWHELP  
  
 Дополнительные сведения об этой структуры см. в разделе [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="makeprominent"></a>CFileDialog::MakeProminent  
 Окружение элемента управления в диалоговом окне таким образом, чтобы он выделялся по сравнению с другими элементами управления.  
  
```  
HRESULT MakeProminent(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onbuttonclicked"></a>CFileDialog::OnButtonClicked  
 Вызывается при нажатии кнопки.  
  
```  
virtual void OnButtonClicked(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор кнопки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="oncheckbuttontoggled"></a>CFileDialog::OnCheckButtonToggled  
 Вызывается, когда этот флажок не установлен или снят флажок.  
  
```  
virtual void OnCheckButtonToggled(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор флажок.  
  
 `bChecked`  
 Помечены или нет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="oncontrolactivating"></a>CFileDialog::OnControlActivating  
 Вызывается при активации элемента управления.  
  
```  
virtual void OnControlActivating(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onfilenamechange"></a>CFileDialog::OnFileNameChange  
 Переопределите этот метод, если требуется обрабатывать `WM_NOTIFY``CDN_SELCHANGE` сообщение.  
  
```  
virtual void OnFileNameChange();
```  
  
### <a name="remarks"></a>Примечания  
 Система отправляет `CDN_SELCHANGE` сообщений, если пользователь выбирает новый файл или папку в списке файлов **откройте** или **Сохранить как** диалоговое окно. Переопределите этот метод, если вы хотите выполнять любые действия в ответ на данное сообщение.  
  
 Система отправляет данное сообщение только в том случае, если диалоговое окно содержит OFN_EXPLORER включен. Дополнительные сведения об уведомлениях в разделе [CDN_SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646865). Сведения о флаге OFN_EXPLORER см. в разделе [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) структуры и [открыть и сохранить как диалоговые окна](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
##  <a name="onfilenameok"></a>CFileDialog::OnFileNameOK  
 Эту функцию можно переопределите только в том случае, если вы хотите предоставить пользовательскую проверку имен файлов, которые вводятся в общее диалоговое окно файла.  
  
```  
virtual BOOL OnFileNameOK();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 1, если имя файла не является допустимым именем файла; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция позволяет отклонить filename для какой-либо причине конкретного приложения. Как правило не нужно использовать эту функцию, так как платформа обеспечивает проверку по умолчанию имена файлов и отображает окно сообщения, если введено недопустимое имя файла.  
  
 Если возвращается 1, диалоговое окно будет отображаться для пользователя ввести другое имя файла. Процедуру диалогового окна закрывает диалоговое окно, если возвращаемое значение 0. Другие ненулевое значение, возвращают значения в данный момент зарезервированы и не должны использоваться.  
  
##  <a name="onfolderchange"></a>CFileDialog::OnFolderChange  
 Переопределить эту функцию для обработки **WM_NOTIFYCDN_FOLDERCHANGE** сообщений.  
  
```  
virtual void OnFolderChange();
```  
  
### <a name="remarks"></a>Примечания  
 Уведомление отправляется при открытии в диалоговом окне Открыть или сохранить как новую папку.  
  
 Уведомление отправляется только в том случае, если диалоговое окно был создан с использованием стиля OFN_EXPLORER. Дополнительные сведения об уведомлениях в разделе [CDN_FOLDERCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646859). В разделе сведения о стиле OFN_EXPLORER [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) структуры и [открыть и сохранить как диалоговые окна](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
##  <a name="oninitdone"></a>CFileDialog::OnInitDone  
 Переопределить эту функцию для обработки `WM_NOTIFY``CDN_INITDONE` сообщение.  
  
```  
virtual void OnInitDone();
```  
  
### <a name="remarks"></a>Примечания  
 Система отправляет это сообщение уведомления о завершении упорядочение элементов управления в системе **откройте** или **Сохранить как** диалогового окна для освобождения места для диалогового окна дочерних элементов управления.  
  
 Система отправляет это только в том случае, если диалоговое окно был создан с использованием стиля OFN_EXPLORER. Дополнительные сведения об уведомлениях в разделе [CDN_INITDONE](http://msdn.microsoft.com/library/windows/desktop/ms646863). В разделе сведения о стиле OFN_EXPLORER [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) структуры и [открыть и сохранить как диалоговые окна](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]диалоговых окон стиля не поддерживают эту функцию. Попытка использовать эту функцию в [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] вызовет диалоговое окно файла стиля [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md). 
  
##  <a name="onitemselected"></a>CFileDialog::OnItemSelected  
 Вызывается при выборе элемента контейнера.  
  
```  
virtual void OnItemSelected(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор контейнерного элемента управления.  
  
 `dwIDItem`  
 Идентификатор элемента.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onlbselchangednotify"></a>CFileDialog::OnLBSelChangedNotify  
 Эта функция вызывается всякий раз, когда текущее выделение в поле со списком будет изменена.  
  
```  
virtual void OnLBSelChangedNotify(
    UINT nIDBox,  
    UINT iCurSel,  
    UINT nCode);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDBox*  
 Идентификатор списка или поля со списком, в котором произошло выделения.  
  
 `iCurSel`  
 Индекс текущего выделенного фрагмента.  
  
 `nCode`  
 Код уведомлений элемента управления. Этот параметр должен иметь одно из следующих значений:  
  
- **CD_LBSELCHANGE** указывает `iCurSel` выделенный элемент в поле со списком одиночным выбором.  
  
- **CD_LBSELSUB** указывает, что `iCurSel` больше не выбран в поле со списком множественного выбора.  
  
- **CD_LBSELADD** указывает, что `iCurSel` выбран в поле со списком множественного выбора.  
  
- **CD_LBSELNOITEMS** указывает, что выбор не существует в поле со списком множественного выбора.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для обеспечения настраиваемой обработки изменения выбора в поле со списком. Например эту функцию можно использовать для отображения прав доступа или пользователь выбирает дату последнего изменения каждого файла.  
  
##  <a name="onshareviolation"></a>CFileDialog::OnShareViolation  
 Переопределите эту функцию для обеспечения настраиваемой обработки нарушений общего ресурса.  
  
```  
virtual UINT OnShareViolation(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPathName`  
 Путь к файлу, в котором произошло нарушение общего ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений:  
  
- **OFN_SHAREFALLTHROUGH** имя файла возвращается из диалогового окна.  
  
- **OFN_SHARENOWARN** необходимо принимать никаких дополнительных действий.  
  
- **OFN_SHAREWARN** пользователь получает стандартный предупреждение для этой ошибки.  
  
### <a name="remarks"></a>Примечания  
 Обычно не нужно использовать эту функцию, так как платформа обеспечивает проверку нарушения общего ресурса по умолчанию и отображает окно сообщения, если происходит нарушение общего ресурса.  
  
 Если вы хотите отключить проверку нарушение общей папки, используйте оператор побитового или для объединения флаг **OFN_SHAREAWARE** с `m_ofn.Flags`.  
  
##  <a name="ontypechange"></a>CFileDialog::OnTypeChange  
 Переопределить эту функцию для обработки **WM_NOTIFYCDN_TYPECHANGE** сообщений.  
  
```  
virtual void OnTypeChange();
```  
  
### <a name="remarks"></a>Примечания  
 Сообщение уведомления отправляется в том случае, когда пользователь выбирает новый тип файла в списке типов файлов в окне Открыть или сохранить как диалоговое окно.  
  
 Уведомление отправляется только в том случае, если диалоговое окно был создан с использованием стиля OFN_EXPLORER. Дополнительные сведения об уведомлениях в разделе [CDN_TYPECHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646868). В разделе сведения о стиле OFN_EXPLORER [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) структуры и [открыть и сохранить как диалоговые окна](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
##  <a name="removecontrolitem"></a>CFileDialog::RemoveControlItem  
 Удаляет элемент из контейнерного элемента управления в диалоговом окне.  
  
```  
HRESULT RemoveControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор для удаления элемента из контейнерного элемента управления.  
  
 `dwIDItem`  
 Идентификатор элемента.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcheckbuttonstate"></a>CFileDialog::SetCheckButtonState  
 Задает текущее состояние кнопки «Проверка» (флажок) в диалоговом окне.  
  
```  
HRESULT SetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор флажок.  
  
 `bChecked`  
 Состояние флажка. `TRUE`Указывает, отмеченный; `FALSE` указывает флажок снят.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcontrolitemstate"></a>CFileDialog::SetControlItemState  
 Задает текущее состояние элемента в элементе управления контейнера, в диалоговом окне.  
  
```  
HRESULT SetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор контейнерного элемента управления.  
  
 `dwIDItem`  
 Идентификатор элемента.  
  
 `dwState`  
 Одно или несколько значений из перечисления CDCONTROLSTATE, указывающие новое состояние элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcontrolitemtext"></a>CFileDialog::SetControlItemText  
 Задает текст элемента управления. Например текст, сопровождающий переключатель или элемента меню.  
  
```  
HRESULT SetControlItemText(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор контейнерного элемента управления.  
  
 `dwIDItem`  
 Идентификатор элемента.  
  
 `strLabel`  
 Текст элемента.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcontrollabel"></a>CFileDialog::SetControlLabel  
 Задает текст, связанный с элементом управления, например текст кнопки или метку поля редактирования.  
  
```  
HRESULT SetControlLabel(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор элемента управления.  
  
 `strLabel`  
 Имя элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcontrolstate"></a>CFileDialog::SetControlState  
 Задает видимость текущего и состояниях данного элемента управления.  
  
```  
HRESULT SetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор элемента управления.  
  
 `dwState`  
 Одно или несколько значений из перечисления CDCONTROLSTATE, указывающие текущее состояние элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcontroltext"></a>CFileDialog::SetControlText  
 Вызовите этот метод, чтобы задать текст для указанного элемента управления в стиле обозревателя **откройте** или **Сохранить как** диалоговое окно.  
  
```  
void SetControlText(
    int nID,  
    LPCSTR lpsz);

 
void SetControlText(
    int nID,  
    const wchar_t *lpsz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор элемента управления, для которого требуется задать текст.  
  
 [in] `lpsz`  
 Указатель на строку, содержащую текст, чтобы задать для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Обе версии этой функции могут использоваться для приложений, использующих Юникод. Тем не менее, является допустимым для приложений, использующих только версия с типом LPCSTR [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)].  
  
 Чтобы использовать этот метод, необходимо создать диалоговое окно со стилем OFN_EXPLORER. В противном случае функция завершится с утверждение.  
  
##  <a name="setdefext"></a>CFileDialog::SetDefExt  
 Эта функция вызывается для задать расширение имени файла по умолчанию для обозревателя стиле открытым или сохранить как стандартным диалоговым окном.  
  
```  
void SetDefExt(LPCSTR lpsz);
```  
  
### <a name="parameters"></a>Параметры  
 `lpsz`  
 Указатель на строку, содержащую расширение по умолчанию для использования объект диалогового окна. Эта строка не должны содержать точку (.).  
  
### <a name="remarks"></a>Примечания  
 Диалоговое окно должен быть создан с помощью **OFN_EXPLORER** стиль; в противном случае, функция завершится сбоем с утверждением.  
  
##  <a name="seteditboxtext"></a>CFileDialog::SetEditBoxText  
 Задает текущий текст в поле ввода.  
  
```  
HRESULT SetEditBoxText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор поля ввода.  
  
 `strText`  
 Текстовое значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setproperties"></a>CFileDialog::SetProperties  
 Предоставляет хранилище свойств, которое определяет значения по умолчанию для сохраняемого элемента.  
  
```  
BOOL SetProperties(LPCWSTR lpszPropList);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPropList`  
 Список предварительно заданных свойств, разделенных точкой с запятой (";"). Список флагов см. в разделе `Flags` раздел [OPENFILENAME](http://msdn.microsoft.com/en-us/8cecfd45-f7c1-4f8d-81a0-4e7fecc3b104).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setselectedcontrolitem"></a>CFileDialog::SetSelectedControlItem  
 Задает состояние выбранного какой-либо элемент в группе или в поле со списком, в диалоговом окне.  
  
```  
HRESULT SetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор контейнерного элемента управления.  
  
 `dwIDItem`  
 Идентификатор элемента, который пользователь выбрал в элементе управления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settemplate"></a>CFileDialog::SetTemplate  
 Задает поле шаблона диалогового окна для [CFileDialog](../../mfc/reference/cfiledialog-class.md) объекта.  
  
```  
void SetTemplate(
    UINT nWin3ID,  
    UINT nWin4ID);

 
void SetTemplate(
    LPCTSTR lpWin3ID,  
    LPCTSTR lpWin4ID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nWin3ID`  
 Содержит идентификатор ресурса шаблона для отличных от обозревателя `CFileDialog` объекта. Этот шаблон используется только на Windows NT 3.51 или если стиль OFN_EXPLORER не присутствует.  
  
 [in] `nWin4ID`  
 Содержит идентификатор ресурса шаблона для проводника `CFileDialog` объекта. Этот шаблон используется только в [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] и более поздних версий, Windows 95 и более поздних версий, или если присутствует OFN_EXPLORER стиль.  
  
 [in] `lpWin3ID`  
 Содержит имя ресурса шаблона не Explorer- `CFileDialog` объекта. Этот шаблон используется только на Windows NT 3.51 или если стиль OFN_EXPLORER не присутствует.  
  
 [in] `lpWin4ID`  
 Содержит имя ресурса шаблона обозревателя `CFileDialog` объекта. Этот шаблон используется только в [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] и более поздних версий, Windows 95 и более поздних версий, или если присутствует OFN_EXPLORER стиль.  
  
### <a name="remarks"></a>Примечания  
 Система будет использовать только один из указанного шаблонов. Система определяет, какой шаблон нужно использовать на основе наличия стиль OFN_EXPLORER и операционной системы, приложение выполняется на. Указывая шаблон в стиле проводника и не Explorer, очень легко поддержки Windows NT 3.51 [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] и более поздние версии и Windows 95 и более поздних версиях.  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]Стиль файловых диалоговых окон не поддерживают эту функцию. Попытка использовать эту функцию в [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] вызовет диалоговое окно файла стиля [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md). Альтернативой является использование настраиваемого диалогового окна. Дополнительные сведения об использовании пользовательского `CFileDialog`, в разделе [IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912).  
  
##  <a name="startvisualgroup"></a>CFileDialog::StartVisualGroup  
 Объявляет visual группы в диалоговом окне. Последующие вызовы к любому методу «добавить» добавить эти элементы в эту группу.  
  
```  
HRESULT StartVisualGroup(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Параметры  
 `dwIDCtl`  
 Идентификатор группы visual.  
  
 `strLabel`  
 Имя группы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="updateofnfromshelldialog"></a>CFileDialog::UpdateOFNFromShellDialog  
 Обновления `m_ofn` структура данных [CFileDialog](../../mfc/reference/cfiledialog-class.md) на основе текущего состояния внутреннего объекта.  
  
```  
void UpdateOFNFromShellDialog();
```  
  
### <a name="remarks"></a>Примечания  
 В версиях Windows до [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], член [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx) структуру данных постоянно был синхронизирован с состоянием `CFileDialog`. Любые изменения в [m_ofn](#m_ofn) переменной-члена непосредственно влияют состояния диалогового окна. Кроме того любые изменения состояния в диалоговом окне немедленно обновить m_ofn переменной-члена.  
  
 В [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], `m_ofn` структура данных не обновляется автоматически. Чтобы гарантировать точность данных в `m_ofn` переменную-член, необходимо вызвать `UpdateOFNFromShellDialog` перед доступом к данным. Windows вызывает эту функцию автоматически во время обработки [IFileDialog::OnFileOK](http://msdn.microsoft.com/library/windows/desktop/bb775879).  
  
 Дополнительные сведения об использовании `CFileDialog` класса под [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], в разделе [класса CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Пример  
 В этом примере обновляется `CFileDialog` перед его отображением. Перед обновлением `m_ofn` переменной-члена, нам нужно синхронизировать ее текущее состояние диалогового окна.  
  
 [!code-cpp[NVC_MFC_CFileDialog&#1;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


