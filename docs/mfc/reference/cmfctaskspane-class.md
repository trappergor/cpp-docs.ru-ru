---
title: "Класс CMFCTasksPane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPane
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPane class
ms.assetid: b456328e-2525-4642-b78b-9edd1a1a7d3f
caps.latest.revision: 26
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
ms.openlocfilehash: 2eb41c24b60bcaea7eadc361c23d5c2273217919
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspane-class"></a>Класс CMFCTasksPane
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Класс `CMFCTasksPane` реализует список доступных для щелчка элементов (задач).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCTasksPane : public CDockablePane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPane::CMFCTasksPane](#cmfctaskspane)|Создает объект `CMFCTasksPane`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPane::AddGroup](#addgroup)|Добавляет новую группу задач для элемента управления области задач.|  
|[CMFCTasksPane::AddLabel](#addlabel)|Добавляет новую статическую подпись в указанную группу задач.|  
|[CMFCTasksPane::AddMRUFilesList](#addmrufileslist)|Добавляет в группу задачи, указанные в списке последних использовавшихся файлов (MRU).|  
|[CMFCTasksPane::AddPage](#addpage)|Добавляет новую страницу в область задач.|  
|[CMFCTasksPane::AddSeparator](#addseparator)||  
|[CMFCTasksPane::AddTask](#addtask)|Добавляет новую задачу в указанную группу задач.|  
|[CMFCTasksPane::AddWindow](#addwindow)|Добавляет дочернее окно в область задач.|  
|[CMFCTasksPane::CollapseAllGroups](#collapseallgroups)||  
|[CMFCTasksPane::CollapseGroup](#collapsegroup)|Программно сворачивает группу.|  
|[CMFCTasksPane::CreateDefaultMiniframe](#createdefaultminiframe)|(Переопределяет [CPane::CreateDefaultMiniframe](../../mfc/reference/cpane-class.md#createdefaultminiframe).)|  
|[CMFCTasksPane::CreateMenu](#createmenu)|Вызывается платформой для создания меню для **другие области задач** кнопки меню.|  
|[CMFCTasksPane::EnableAnimation](#enableanimation)|Включает или отключает анимацию свертывания и развертывания групп задач.|  
|[CMFCTasksPane::EnableGroupCollapse](#enablegroupcollapse)|Указывает, могут ли быть свернуты группы задач.|  
|[CMFCTasksPane::EnableHistoryMenuButtons](#enablehistorymenubuttons)|Включает или отключает раскрывающихся меню в **Далее** и **Назад** кнопок навигации.|  
|[CMFCTasksPane::EnableNavigationToolbar](#enablenavigationtoolbar)|Включает или отключает панель навигации.|  
|[CMFCTasksPane::EnableOffsetCustomControls](#enableoffsetcustomcontrols)||  
|[CMFCTasksPane::EnableScrollButtons](#enablescrollbuttons)|Заменяет полосу прокрутки на кнопки прокрутки.|  
|[CMFCTasksPane::EnableWrapLabels](#enablewraplabels)|Включает или отключает перенос слов для меток.|  
|[CMFCTasksPane::EnableWrapTasks](#enablewraptasks)|Включает или отключает перенос слов для задач.|  
|[CMFCTasksPane::GetActivePage](#getactivepage)|Возвращает для активной страницы отсчитываемый от нуля индекс.|  
|[CMFCTasksPane::GetGroupCaptionHeight](#getgroupcaptionheight)|Возвращает высоту заголовков групп.|  
|[CMFCTasksPane::GetGroupCaptionHorzOffset](#getgroupcaptionhorzoffset)|Возвращает текущее смещение заголовка группы относительно левого и правого края области задач.|  
|[CMFCTasksPane::GetGroupCaptionVertOffset](#getgroupcaptionvertoffset)|Возвращает текущее смещение заголовка группы относительно верхнего и нижнего края области задач.|  
|[CMFCTasksPane::GetGroupCount](#getgroupcount)|Возвращает общее количество групп.|  
|[CMFCTasksPane::GetGroupLocation](#getgrouplocation)|Возвращает внутренней индекс указанной группы.|  
|[CMFCTasksPane::GetGroupVertOffset](#getgroupvertoffset)|Возвращает смещение группы по вертикали.|  
|[CMFCTasksPane::GetHorzMargin](#gethorzmargin)|Возвращает горизонтальный интервал между областью задач и краями клиентской области.|  
|[CMFCTasksPane::GetNextPages](#getnextpages)||  
|[CMFCTasksPane::GetPageByGroup](#getpagebygroup)|Получает индекс страницы для указанной группы.|  
|[CMFCTasksPane::GetPagesCount](#getpagescount)|Возвращает количество страниц.|  
|[CMFCTasksPane::GetPreviousPages](#getpreviouspages)||  
|[CMFCTasksPane::GetScrollBarCtrl](#getscrollbarctrl)|(Переопределяет [CWnd::GetScrollBarCtrl](../../mfc/reference/cwnd-class.md#getscrollbarctrl).)|  
|[CMFCTasksPane::GetTask](#gettask)|Получает задачу.|  
|[CMFCTasksPane::GetTaskCount](#gettaskcount)|Возвращает количество элементов задач в указанной группе.|  
|[CMFCTasksPane::GetTaskGroup](#gettaskgroup)|Возвращает группу задач по указанному индексу группы.|  
|[CMFCTasksPane::GetTaskLocation](#gettasklocation)|Возвращает группу и индекс указанной задачи.|  
|[CMFCTasksPane::GetTasksHorzOffset](#gettaskshorzoffset)|Возвращает смещение задач по горизонтали относительно левого и правого края их родительских групп.|  
|[CMFCTasksPane::GetTasksIconHorzOffset](#gettasksiconhorzoffset)||  
|[CMFCTasksPane::GetTasksIconVertOffset](#gettasksiconvertoffset)||  
|[CMFCTasksPane::GetVertMargin](#getvertmargin)|Возвращает вертикальный интервал между областью задач и краями клиентской области.|  
|[CMFCTasksPane::IsAccessibilityCompatible](#isaccessibilitycompatible)|(Переопределяет `CDockablePane::IsAccessibilityCompatible`.)|  
|[CMFCTasksPane::IsAnimationEnabled](#isanimationenabled)|Указывает, включена ли анимация.|  
|[CMFCTasksPane::IsBackButtonEnabled](#isbackbuttonenabled)|Указывает, доступна ли кнопка перехода назад.|  
|[CMFCTasksPane::IsForwardButtonEnabled](#isforwardbuttonenabled)|Указывает, доступна ли кнопка перехода вперед.|  
|[CMFCTasksPane::IsGroupCollapseEnabled](#isgroupcollapseenabled)||  
|[CMFCTasksPane::IsHistoryMenuButtonsEnabled](#ishistorymenubuttonsenabled)|Указывает ли **Далее** и **Назад** кнопки навигации имеют раскрывающихся меню.|  
|[CMFCTasksPane::IsNavigationToolbarEnabled](#isnavigationtoolbarenabled)|Указывает, доступна ли панель навигации.|  
|[CMFCTasksPane::IsToolBox](#istoolbox)||  
|[CMFCTasksPane::IsWrapLabelsEnabled](#iswraplabelsenabled)|Указывает, переносятся ли слова в метках области задач.|  
|[CMFCTasksPane::IsWrapTasksEnabled](#iswraptasksenabled)|Указывает, переносятся ли слова в именах задач области задач.|  
|[CMFCTasksPane::LoadState](#loadstate)|(Переопределяет [CDockablePane::LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917).)|  
|[CMFCTasksPane::OnCancel](#oncancel)||  
|[CMFCTasksPane::OnClickTask](#onclicktask)|Вызывается платформой по щелчку элемента в области задач.|  
|[CMFCTasksPane::OnOK](#onok)||  
|[CMFCTasksPane::OnPressBackButton](#onpressbackbutton)|Вызывается платформой по нажатию кнопки перехода назад.|  
|[CMFCTasksPane::OnPressForwardButton](#onpressforwardbutton)|Вызывается платформой по нажатию кнопки перехода вперед.|  
|[CMFCTasksPane::OnPressHomeButton](#onpresshomebutton)|Вызывается платформой по нажатию кнопки перехода на домашнюю страницу.|  
|[CMFCTasksPane::OnPressOtherButton](#onpressotherbutton)||  
|[CMFCTasksPane::OnSetAccData](#onsetaccdata)|(Переопределяет [CBasePane::OnSetAccData](../../mfc/reference/cbasepane-class.md#onsetaccdata).)|  
|[CMFCTasksPane::OnUpdateCmdUI](#onupdatecmdui)|(Переопределяет [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|[CMFCTasksPane::PreTranslateMessage](#pretranslatemessage)|(Переопределяет [CDockablePane::PreTranslateMessage](http://msdn.microsoft.com/en-us/49a242cc-b158-400e-9e01-0345ec9c3ffd).)|  
|[CMFCTasksPane::RecalcLayout](#recalclayout)|(Переопределяет [CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CMFCTasksPane::RemoveAllGroups](#removeallgroups)|Удаляет все группы на указанной странице.|  
|[CMFCTasksPane::RemoveAllPages](#removeallpages)|Удаляет все страницы из области задач, за исключением страницы по умолчанию (первой страницы).|  
|[CMFCTasksPane::RemoveAllTasks](#removealltasks)|Удаляет все задачи из группы.|  
|[CMFCTasksPane::RemoveGroup](#removegroup)|Удаляет группу.|  
|[CMFCTasksPane::RemovePage](#removepage)|Удаляет указанную страницу из области задач.|  
|[CMFCTasksPane::RemoveTask](#removetask)|Удаляет задачу из группы задач.|  
|[CMFCTasksPane::SaveState](#savestate)|(Переопределяет [CDockablePane::SaveState](http://msdn.microsoft.com/en-us/c5c24249-8d0d-46cb-96d9-9f5c6dc191db).)|  
|[CMFCTasksPane::Serialize](#serialize)|(Переопределяет [CDockablePane::Serialize](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6).)|  
|[CMFCTasksPane::SetActivePage](#setactivepage)|Активирует указанную страницу в области задач.|  
|[CMFCTasksPane::SetCaption](#setcaption)|Задает заголовок области задач.|  
|[CMFCTasksPane::SetGroupCaptionHeight](#setgroupcaptionheight)|Задает высоту заголовка группы.|  
|[CMFCTasksPane::SetGroupCaptionHorzOffset](#setgroupcaptionhorzoffset)|Задает смещение заголовка группы по горизонтали.|  
|[CMFCTasksPane::SetGroupCaptionVertOffset](#setgroupcaptionvertoffset)|Задает смещение заголовка группы по вертикали.|  
|[CMFCTasksPane::SetGroupName](#setgroupname)|Задает имя группы.|  
|[CMFCTasksPane::SetGroupTextColor](#setgrouptextcolor)|Задает цвет текста для заголовка группы.|  
|[CMFCTasksPane::SetGroupVertOffset](#setgroupvertoffset)|Задает смещение группы по вертикали.|  
|[CMFCTasksPane::SetHorzMargin](#sethorzmargin)|Задает горизонтальный интервал между областью задач и краями клиентской области.|  
|[CMFCTasksPane::SetIconsList](#seticonslist)|Задает список изображений, связанных с задачами.|  
|[CMFCTasksPane::SetPageCaption](#setpagecaption)|Задает текст заголовка для страницы области задач.|  
|[CMFCTasksPane::SetTaskName](#settaskname)|Задает имя задачи.|  
|[CMFCTasksPane::SetTasksIconHorzOffset](#settasksiconhorzoffset)||  
|[CMFCTasksPane::SetTasksIconVertOffset](#settasksiconvertoffset)||  
|[CMFCTasksPane::SetTaskTextColor](#settasktextcolor)|Задает цвет текста для задачи.|  
|[CMFCTasksPane::SetTasksHorzOffset](#settaskshorzoffset)|Задает смещение задач по горизонтали относительно левого и правого краев их родительских групп.|  
|[CMFCTasksPane::SetVertMargin](#setvertmargin)|Задает вертикальный интервал между областью задач и краями клиентской области.|  
|[CMFCTasksPane::SetWindowHeight](#setwindowheight)|Задает высоту окна.|  
|[CMFCTasksPane::ShowCommandMessageString](#showcommandmessagestring)||  
|[CMFCTasksPane::ShowTask](#showtask)|Показывает или скрывает задачу.|  
|[CMFCTasksPane::ShowTaskByCmdId](#showtaskbycmdid)|Показывает или скрывает задачу по ее идентификатору команды.|  
|[CMFCTasksPane::Update](#update)|Обновляет элементы графического пользовательского интерфейса, принадлежащие области задач.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCTasksPane::OnActivateTasksPanePage](#onactivatetaskspanepage)|Вызывается платформой при активации новой страницы области задач.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CMFCTasksPane` реализует следующие возможности:  
  
-   Группировка элементов и назначение каждой группе заголовка.  
  
-   Свертывание и развертывание групп элементов.  
  
-   Назначение значков элементам области задач.  
  
-   Связь элементов с идентификаторами команд, выполняемых щелчком по этим элементам. Когда делается щелчок, владельцу элемента управления области задач отправляется сообщение `WM_COMMAND`.  
  
 Для использования элемента управления `CMFCTasksPane` в своем приложении выполните следующие действия:  
  
1.  Внедрите объект `CMFCTasksPane` в класс окна главного фрейма.  
  
2.  При обработке сообщения `WM_CREATE` вызовите метод `Create`. Можно использовать обычный [CControlBar](../../mfc/reference/ccontrolbar-class.md) стили. Для получения дополнительной информации см. `CControlBar::Create`.  
  
3.  Вызов [CMFCTasksPane::AddGroup](#addgroup) метод для добавления различных групп.  
  
4.  Вызов [CMFCTasksPane::AddTask](#addtask), [CMFCTasksPane::AddLabel](#addlabel) или [CMFCTasksPane::AddMRUFilesList](#addmrufileslist) функции-члены для добавления новых элементов (задач) в каждой группе.  
  
5.  Вызов [CMFCTasksPane::EnableGroupCollapse](#enablegroupcollapse) для указания, можно ли свернуть группы элементов.  
  
 На следующем рисунке показан стандартный элемент управления области задач. Первая группа — *специальных* группы и ее название является более темный цвет. Третья группа свернута. Последняя группа расположена в нижней части области задач и не имеет заголовка. Последняя задача в этой группе — простая метка:  
  
 ![Пример области задач](../../mfc/reference/media/nexttaskpane.png "nexttaskpane")  
  
 Внешний вид области задач можно настроить, перемещая различные поля и меняя смещения. На следующем рисунке разъясняется значение этих переменных:  
  
 ![Пользовательская группа задач](../../mfc/reference/media/nexttaskgrpcustom.png "nexttaskgrpcustom")  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется создание объекта `CMFCTasksPane` и использование различных методов класса `CMFCTasksPane`. В примере показано включение свертывание групп задач, включите раскрывающихся меню на **Далее** и **Назад** кнопки навигации включить кнопки прокрутки вместо полосу прокрутки, включите слово перенос текста метки, задайте имя заголовка области задач, задать цвет текста для заголовка группы и задайте горизонтальное и вертикальное.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#28;](../../mfc/reference/codesnippet/cpp/cmfctaskspane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 `CMFCTasksPane`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxTasksPane.h  
  
##  <a name="a-nameaddgroupa--cmfctaskspaneaddgroup"></a><a name="addgroup"></a>CMFCTasksPane::AddGroup  
 Добавляет новую группу задач для элемента управления области задач.  
  
```  
int AddGroup(
    int nPageIdx,  
    LPCTSTR lpszGroupName,  
    BOOL bBottomLocation = FALSE,  
    BOOL bSpecial = FALSE,  
    HICON hIcon = NULL);

 
int AddGroup(
    LPCTSTR lpszGroupName,  
    BOOL bBottomLocation = FALSE,  
    BOOL bSpecial = FALSE,  
    HICON hIcon = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPageIdx`  
 Определяет индекс (с нуля).  
  
 [in] `lpszGroupName`  
 Указывает имя группы.  
  
 [in] `bBottomLocation`  
 `TRUE`Чтобы создать группу в нижней части элемента управления области задач; в противном случае — `FALSE`.  
  
 [in] `bSpecial`  
 `TRUE`Чтобы пометить эту группу в качестве *специальных* группу, в противном случае — `FALSE`. Дополнительные сведения о специальных группах см. в разделе «Примечания» `CMFCTasksPane`.  
  
 [in] `hIcon`  
 Задает значок, отображаемый в заголовке группы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс группы в во внутренний список групп, которые поддерживает класс.  
  
### <a name="remarks"></a>Примечания  
 Этот метод для создания группы задач и добавить эту группу для управления области задач.  
  
 Платформа отображает группы задач, в верхней части элемента управления области задач или внизу. Платформа может отображать только одна группа внизу; последний необходимо добавить эту группу.  
  
##  <a name="a-nameaddlabela--cmfctaskspaneaddlabel"></a><a name="addlabel"></a>CMFCTasksPane::AddLabel  
 Добавляет метку группы указанной задачи.  
  
```  
int AddLabel(
    int nGroup,  
    LPCTSTR lpszLabelName,  
    int nTaskIcon = -1,  
    BOOL bIsBold = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Указывает индекс группы, куда добавляется метка.  
  
 [in] `lpszLabelName`  
 Задает имя метки.  
  
 [in] `nTaskIcon`  
 Задает значок, отображаемый рядом с меткой. Framework хранит значки в списке изображений. Этот параметр является индексом в списке.  
  
 [in] `bIsBold`  
 `TRUE`Чтобы отобразить метку полужирным шрифтом; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс, куда был добавлен метки группы или значение -1, если заданная группа `nGroup` не существует.  
  
### <a name="remarks"></a>Примечания  
 Платформа по-разному обрабатывает задачи и метки. Когда пользователь щелкает задачу, платформа выполняет команду. При щелчке метки не команда выполняется. Дополнительные сведения см. в разделе [CMFCTasksPane::AddTask](#addtask).  
  
##  <a name="a-nameaddmrufileslista--cmfctaskspaneaddmrufileslist"></a><a name="addmrufileslist"></a>CMFCTasksPane::AddMRUFilesList  
 Добавляет задачу для каждого файла, хранящийся в списке наиболее недавно Использованных файлов в группу.  
  
```  
int AddMRUFilesList(
    int nGroup,  
    int nMaxFiles = 4);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Указывает индекс в группе. Этот метод добавляет список файлов в группе, заданного этим параметром.  
  
 [in] `nMaxFiles`  
 Указывает число файлов, отображаемых в списке файлов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс группы, куда был добавлен в список наиболее часто Используемых файлов, или значение -1, если заданная группа `nGroup` не существует.  
  
##  <a name="a-nameaddpagea--cmfctaskspaneaddpage"></a><a name="addpage"></a>CMFCTasksPane::AddPage  
 Добавляет страницу в области задач.  
  
```  
int AddPage(LPCTSTR lpszPageLabel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPageLabel`  
 Задает метку для страницы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс новой страницы.  
  
##  <a name="a-nameaddseparatora--cmfctaskspaneaddseparator"></a><a name="addseparator"></a>CMFCTasksPane::AddSeparator  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int AddSeparator(int nGroup);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameaddtaska--cmfctaskspaneaddtask"></a><a name="addtask"></a>CMFCTasksPane::AddTask  
 Добавляет задачу в группу для указанной задачи.  
  
```  
int AddTask(
    int nGroup,  
    LPCTSTR lpszTaskName,  
    int nTaskIcon = -1,  
    UINT uiCommandID = 0,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Указывает индекс группы, куда добавляется задача.  
  
 [in] `lpszTaskName`  
 Задает имя задачи.  
  
 [in] `nTaskIcon`  
 Задает значок, отображаемый рядом с задачей. Framework хранит значки в списке изображений. Этот параметр является индексом в списке.  
  
 [in] `uiCommandID`  
 Указывает идентификатор команды команда выполняется, когда пользователь щелкает задачу. Задача обрабатывается как метки, если `uiCommandID` имеет значение 0.  
  
 [in] `dwUserData`  
 Задает определяемые пользователем данные, следует связать с задачей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс, куда был добавлен задачи группы или значение -1, если заданная группа `nGroup` не существует.  
  
##  <a name="a-nameaddwindowa--cmfctaskspaneaddwindow"></a><a name="addwindow"></a>CMFCTasksPane::AddWindow  
 Добавляет дочернее окно в область задач.  
  
```  
int AddWindow(
    int nGroup,  
    HWND hwndTask,  
    int nWndHeight,  
    BOOL bAutoDestroyWindow = FALSE,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Указывает индекс группы, куда добавляется окна.  
  
 [in] `hwndTask`  
 Указывает дескриптор окна для добавления.  
  
 [in] `nWndHeight`  
 Указывает высоту окна.  
  
 [in] `bAutoDestroyWindow`  
 `TRUE`уничтожить окно при удалении задачи; в противном случае — `FALSE`.  
  
 [in] `dwUserData`  
 Задает определяемые пользователем данные, связанные с задачей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс группы, куда был добавлен окна или -1, если заданная группа `nGroup` не существует.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы добавить элемент управления в область задач. Например можно добавить элемент управления редактирования, который работает как панель поиска.  
  
##  <a name="a-namecmfctaskspanea--cmfctaskspanecmfctaskspane"></a><a name="cmfctaskspane"></a>CMFCTasksPane::CMFCTasksPane  
 Создает [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) объекта.  
  
```  
CMFCTasksPane();
```  
  
##  <a name="a-namecollapseallgroupsa--cmfctaskspanecollapseallgroups"></a><a name="collapseallgroups"></a>CMFCTasksPane::CollapseAllGroups  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void CollapseAllGroups(BOOL bCollapse = TRUE);

 
void CollapseAllGroups(
    int nPageIdx,  
    BOOL bCollapse);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bCollapse`  
 [in] `nPageIdx`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecollapsegroupa--cmfctaskspanecollapsegroup"></a><a name="collapsegroup"></a>CMFCTasksPane::CollapseGroup  
 Сворачивает или разворачивает группы.  
  
```  
BOOL CollapseGroup(
    CMFCTasksPaneTaskGroup* pGroup,  
    BOOL bCollapse = TRUE);

 
BOOL CollapseGroup(
    int nGroup,  
    BOOL bCollapse = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pGroup`  
 Указывает группу, чтобы свернуть.  
  
 [in] `bCollapse`  
 `TRUE`Чтобы свернуть группу; `FALSE` чтобы развернуть группу.  
  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс в группу, чтобы свернуть во внутреннем списке групп.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если группа сворачивает или разворачивает успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Свернутой группы показывает только название группы; Список задач скрыта.  
  
##  <a name="a-namecreatedefaultminiframea--cmfctaskspanecreatedefaultminiframe"></a><a name="createdefaultminiframe"></a>CMFCTasksPane::CreateDefaultMiniframe  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectInitial`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecreatemenua--cmfctaskspanecreatemenu"></a><a name="createmenu"></a>CMFCTasksPane::CreateMenu  
 Создает меню, которое открывается при щелчке **другие области задач** кнопки меню.  
  
```  
HMENU CreateMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор новое меню.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить меню для панели задач.  
  
 Во всплывающем меню, этот метод создает список страниц в области задач. Меню отображается флажок рядом с активной страницы.  
  
##  <a name="a-nameenableanimationa--cmfctaskspaneenableanimation"></a><a name="enableanimation"></a>CMFCTasksPane::EnableAnimation  
 Включает или отключает анимацию, которая происходит, когда группа задач Разворачивание или сворачивание.  
  
```  
void EnableAnimation(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить анимацию, которая происходит, когда группа задач Разворачивание или сворачивание; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Анимация, которая происходит, когда группа задач Разворачивание или сворачивание включено по умолчанию.  
  
##  <a name="a-nameenablegroupcollapsea--cmfctaskspaneenablegroupcollapse"></a><a name="enablegroupcollapse"></a>CMFCTasksPane::EnableGroupCollapse  
 Указывает, может ли пользователь свернуть группы задач.  
  
```  
void EnableGroupCollapse(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Если пользователи можно свернуть группы задач; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Группы задач, свернута отображается только заголовок группы; Список задач скрыта.  
  
##  <a name="a-nameenablehistorymenubuttonsa--cmfctaskspaneenablehistorymenubuttons"></a><a name="enablehistorymenubuttons"></a>CMFCTasksPane::EnableHistoryMenuButtons  
 Включает раскрывающихся меню на **Далее** и **Назад** кнопок навигации.  
  
```  
void EnableHistoryMenuButtons(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить раскрывающихся меню на **Далее** и **Назад** кнопки навигации; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию в раскрывающемся меню **Далее** и **Назад** кнопки будут отключены.  
  
 Меню содержат историю страниц задач, которые пользователь использовал.  
  
##  <a name="a-nameenablenavigationtoolbara--cmfctaskspaneenablenavigationtoolbar"></a><a name="enablenavigationtoolbar"></a>CMFCTasksPane::EnableNavigationToolbar  
 Включает или отключает панель навигации.  
  
```  
void EnableNavigationToolbar(
    BOOL bEnable = TRUE,  
    UINT uiToolbarBmpRes = 0,  
    CSize sizeToolbarImage = CSize(0,
    0),  
    CSize sizeToolbarButton = CSize(0,
    0));
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить панели инструментов; в противном случае — `FALSE`.  
  
 [in] `uiToolbarBmpRes`  
 Указывает идентификатор ресурса растрового изображения, которое содержит изображения для отображения на панели инструментов.  
  
 [in] `sizeToolbarImage`  
 Указывает размер изображения панели инструментов.  
  
 [in] `sizeToolbarButton`  
 Задает размер кнопки панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Панели навигации — это панель, которая framework отображается в верхней части области задач. Панель навигации содержит **обратно**, **вперед**, и **Главная** кнопок навигации и кнопки меню, содержащее список доступных страниц.  
  
 По умолчанию платформа не отображается панель навигации. Если панель навигации не отображается, кнопки перехода расположены на заголовок панели закрепления.  
  
##  <a name="a-nameenableoffsetcustomcontrolsa--cmfctaskspaneenableoffsetcustomcontrols"></a><a name="enableoffsetcustomcontrols"></a>CMFCTasksPane::EnableOffsetCustomControls  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableOffsetCustomControls(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenablescrollbuttonsa--cmfctaskspaneenablescrollbuttons"></a><a name="enablescrollbuttons"></a>CMFCTasksPane::EnableScrollButtons  
 Включает прокрутки кнопки вместо полосы прокрутки.  
  
```  
void EnableScrollButtons(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`для отображения кнопки прокрутки в области задач вместо полосы прокрутки; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа отображаются кнопки прокрутки в области задач.  
  
##  <a name="a-nameenablewraplabelsa--cmfctaskspaneenablewraplabels"></a><a name="enablewraplabels"></a>CMFCTasksPane::EnableWrapLabels  
 Включение или отключение переноса слов в тексте метки.  
  
```  
void EnableWrapLabels(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы перенести текст метки, отображаемые на панели задач; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа не в вокруг текста метки. Если включен перенос слов, текст метки может располагаться в нескольких строках. Метка может включать строки, таких как критические маркеры `\n` и подчеркивание маркера `&`.  
  
##  <a name="a-nameenablewraptasksa--cmfctaskspaneenablewraptasks"></a><a name="enablewraptasks"></a>CMFCTasksPane::EnableWrapTasks  
 Включение или отключение переноса слов в тексте в задачах.  
  
```  
void EnableWrapTasks(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Перенос задач в области задач; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Перенос слов для задач отключена по умолчанию.  
  
##  <a name="a-namegetactivepagea--cmfctaskspanegetactivepage"></a><a name="getactivepage"></a>CMFCTasksPane::GetActivePage  
 Возвращает для активной страницы отсчитываемый от нуля индекс.  
  
```  
int GetActivePage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс текущей странице.  
  
##  <a name="a-namegetgroupcaptionheighta--cmfctaskspanegetgroupcaptionheight"></a><a name="getgroupcaptionheight"></a>CMFCTasksPane::GetGroupCaptionHeight  
 Возвращает высоту заголовка группы.  
  
```  
int GetGroupCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота заголовка группы, в пикселях.  
  
##  <a name="a-namegetgroupcaptionhorzoffseta--cmfctaskspanegetgroupcaptionhorzoffset"></a><a name="getgroupcaptionhorzoffset"></a>CMFCTasksPane::GetGroupCaptionHorzOffset  
 Возвращает горизонтальное смещение заголовка группы.  
  
```  
int GetGroupCaptionHorzOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Горизонтальное смещение заголовка группы. Смещение по горизонтали — это расстояние в точках от левого или правого края панели задач.  
  
##  <a name="a-namegetgroupcaptionvertoffseta--cmfctaskspanegetgroupcaptionvertoffset"></a><a name="getgroupcaptionvertoffset"></a>CMFCTasksPane::GetGroupCaptionVertOffset  
 Возвращает вертикальное смещение заголовка группы.  
  
```  
int GetGroupCaptionVertOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вертикальное смещение заголовок группы из верхней и нижней границ панели задач.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию для вертикальное смещение равно 7 пикселям.  
  
##  <a name="a-namegetgroupcounta--cmfctaskspanegetgroupcount"></a><a name="getgroupcount"></a>CMFCTasksPane::GetGroupCount  
 Возвращает общее количество групп.  
  
```  
int GetGroupCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Общее число групп в области задач.  
  
##  <a name="a-namegetgrouplocationa--cmfctaskspanegetgrouplocation"></a><a name="getgrouplocation"></a>CMFCTasksPane::GetGroupLocation  
 Возвращает индекс внутренней группы для указанной группы.  
  
```  
BOOL GetGroupLocation(
    CMFCTasksPaneTaskGroup* pGroup,  
    int& nGroup) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pGroup`  
 Группа задач, расположение которого извлекается.  
  
 [выходной] `nGroup`  
 Содержит отсчитываемый от нуля индекс группы задач.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если найдена группа задач; в противном случае — `FALSE`.  
  
##  <a name="a-namegetgroupvertoffseta--cmfctaskspanegetgroupvertoffset"></a><a name="getgroupvertoffset"></a>CMFCTasksPane::GetGroupVertOffset  
 Возвращает смещение группы по вертикали.  
  
```  
int GetGroupVertOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вертикальное смещение в группу, в пикселях.  
  
##  <a name="a-namegethorzmargina--cmfctaskspanegethorzmargin"></a><a name="gethorzmargin"></a>CMFCTasksPane::GetHorzMargin  
 Возвращает интервал по горизонтали между панели задач и границей клиентской области.  
  
```  
int GetHorzMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Интервал по горизонтали между панели задач и края клиентской области.  
  
### <a name="remarks"></a>Примечания  
 Интервал по умолчанию между панели задач и границей клиентской области — 12 пикселов.  
  
##  <a name="a-namegetnextpagesa--cmfctaskspanegetnextpages"></a><a name="getnextpages"></a>CMFCTasksPane::GetNextPages  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetNextPages(CStringList& lstNextPages) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lstNextPages`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetpagebygroupa--cmfctaskspanegetpagebygroup"></a><a name="getpagebygroup"></a>CMFCTasksPane::GetPageByGroup  
 Получает индекс страницы для указанной группы.  
  
```  
BOOL GetPageByGroup(
    int nGroup,  
    int& nPage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс группы задач.  
  
 [выходной] `nPage`  
 Содержит индекс страницы для указанной группы. Если группа задач содержит только страницы по умолчанию, возвращаемое значение равно 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если группе `nGroup` существует; в противном случае — `FALSE`.  
  
##  <a name="a-namegetpagescounta--cmfctaskspanegetpagescount"></a><a name="getpagescount"></a>CMFCTasksPane::GetPagesCount  
 Возвращает количество страниц.  
  
```  
int GetPagesCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество страниц в области задач.  
  
##  <a name="a-namegetpreviouspagesa--cmfctaskspanegetpreviouspages"></a><a name="getpreviouspages"></a>CMFCTasksPane::GetPreviousPages  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetPreviousPages(CStringList& lstPrevPages) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lstPrevPages`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetscrollbarctrla--cmfctaskspanegetscrollbarctrl"></a><a name="getscrollbarctrl"></a>CMFCTasksPane::GetScrollBarCtrl  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CScrollBar* GetScrollBarCtrl(int nBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nBar`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaska--cmfctaskspanegettask"></a><a name="gettask"></a>CMFCTasksPane::GetTask  
 Получает задачу.  
  
```  
CMFCTasksPaneTask* GetTask(
    int nGroup,  
    int nTask) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс, содержащий задачу.  
  
 [in] `nTask`  
 Задает отсчитываемый от нуля индекс задачи в список, указанный в `nGroup`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задача по указанному индексу.  
  
##  <a name="a-namegettaskcounta--cmfctaskspanegettaskcount"></a><a name="gettaskcount"></a>CMFCTasksPane::GetTaskCount  
 Возвращает число задач в указанной группе.  
  
```  
int GetTaskCount(int nGroup) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Указывает индекс группы задач.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число задач в указанную группу, или 0, если `nGroup` является недопустимым.  
  
##  <a name="a-namegettaskgroupa--cmfctaskspanegettaskgroup"></a><a name="gettaskgroup"></a>CMFCTasksPane::GetTaskGroup  
 Возвращает группу задач для индекса указанной группы.  
  
```  
CMFCTasksPaneTaskGroup* GetTaskGroup(int nGroup) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс извлекаемого группы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Группа задач по указанному индексу.  
  
##  <a name="a-namegettasklocationa--cmfctaskspanegettasklocation"></a><a name="gettasklocation"></a>CMFCTasksPane::GetTaskLocation  
 Возвращает группу и индекс для указанной задачи.  
  
```  
BOOL GetTaskLocation(
    UINT uiCommandID,  
    int& nGroup,  
    int& nTask) const;  
  
BOOL GetTaskLocation(
    HWND hwndTask,  
    int& nGroup,  
    int& nTask) const;  
  
BOOL GetTaskLocation(
    CMFCTasksPaneTask* pTask,  
    int& nGroup,  
    int& nTask) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCommandID`  
 Указывает идентификатор задачи для поиска.  
  
 [выходной] `nGroup`  
 Содержит индекс группы задачи.  
  
 [выходной] `nTask`  
 Содержит индекс задачи в группе задач.  
  
 [in] `hwndTask`  
 Определяет окно, связанное с задачей.  
  
 [in] `pTask`  
 Указывает задачу, чтобы найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если найдена расположение задач; `FALSE` Если указанное задание не существует.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает индекс группы и индекс задачи для указанной задачи. Если метод возвращает `FALSE`, `nGroup` и `nTask` задано значение -1.  
  
##  <a name="a-namegettaskshorzoffseta--cmfctaskspanegettaskshorzoffset"></a><a name="gettaskshorzoffset"></a>CMFCTasksPane::GetTasksHorzOffset  
 Возвращает горизонтальное смещение задачи.  
  
```  
int GetTasksHorzOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Горизонтальное смещение задач из левой и правой границ их родительские группы.  
  
### <a name="remarks"></a>Примечания  
 Горизонтальное смещение задачи по умолчанию — 12 пикселов.  
  
##  <a name="a-namegettasksiconhorzoffseta--cmfctaskspanegettasksiconhorzoffset"></a><a name="gettasksiconhorzoffset"></a>CMFCTasksPane::GetTasksIconHorzOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksIconHorzOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettasksiconvertoffseta--cmfctaskspanegettasksiconvertoffset"></a><a name="gettasksiconvertoffset"></a>CMFCTasksPane::GetTasksIconVertOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksIconVertOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetvertmargina--cmfctaskspanegetvertmargin"></a><a name="getvertmargin"></a>CMFCTasksPane::GetVertMargin  
 Возвращает вертикальное поле между панели задач и края клиентской области.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вертикальное поле между панели задач и края клиентской области.  
  
### <a name="remarks"></a>Примечания  
 Вертикальное поле представляет собой пространство между областью задач и края клиентской области. Значение по умолчанию вертикальный поля — 12 пикселов.  
  
##  <a name="a-nameisaccessibilitycompatiblea--cmfctaskspaneisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>CMFCTasksPane::IsAccessibilityCompatible  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisanimationenableda--cmfctaskspaneisanimationenabled"></a><a name="isanimationenabled"></a>CMFCTasksPane::IsAnimationEnabled  
 Указывает, включена ли анимация.  
  
```  
BOOL IsAnimationEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включена анимация, которая происходит, когда пользователь разворачивает или сворачивает группу. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Вызов [CMFCTasksPane::EnableAnimation](#enableanimation) для включения или отключения анимации.  
  
##  <a name="a-nameisbackbuttonenableda--cmfctaskspaneisbackbuttonenabled"></a><a name="isbackbuttonenabled"></a>CMFCTasksPane::IsBackButtonEnabled  
 Указывает, доступна ли кнопка перехода назад.  
  
```  
BOOL IsBackButtonEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включена кнопка «Назад». в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь нажимает кнопку "Назад", платформа Отображение предыдущей страницы задач.  
  
##  <a name="a-nameisforwardbuttonenableda--cmfctaskspaneisforwardbuttonenabled"></a><a name="isforwardbuttonenabled"></a>CMFCTasksPane::IsForwardButtonEnabled  
 Указывает, доступна ли кнопка перехода вперед.  
  
```  
BOOL IsForwardButtonEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включено кнопки «вперед»; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Кнопки «Вперед» позволяет переходов вперед в журнале страницы задач.  
  
##  <a name="a-nameisgroupcollapseenableda--cmfctaskspaneisgroupcollapseenabled"></a><a name="isgroupcollapseenabled"></a>CMFCTasksPane::IsGroupCollapseEnabled  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsGroupCollapseEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameishistorymenubuttonsenableda--cmfctaskspaneishistorymenubuttonsenabled"></a><a name="ishistorymenubuttonsenabled"></a>CMFCTasksPane::IsHistoryMenuButtonsEnabled  
 Указывает ли **Далее** и **Назад** кнопки навигации имеют раскрывающихся меню.  
  
```  
BOOL IsHistoryMenuButtonsEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если **Далее** и **Назад** кнопки навигации имеют раскрывающихся меню; в противном случае — `FALSE`.  
  
##  <a name="a-nameisnavigationtoolbarenableda--cmfctaskspaneisnavigationtoolbarenabled"></a><a name="isnavigationtoolbarenabled"></a>CMFCTasksPane::IsNavigationToolbarEnabled  
 Указывает, доступна ли панель навигации.  
  
```  
BOOL IsNavigationToolbarEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включена панели навигации. в противном случае — `FALSE`.  
  
##  <a name="a-nameistoolboxa--cmfctaskspaneistoolbox"></a><a name="istoolbox"></a>CMFCTasksPane::IsToolBox  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsToolBox() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameiswraplabelsenableda--cmfctaskspaneiswraplabelsenabled"></a><a name="iswraplabelsenabled"></a>CMFCTasksPane::IsWrapLabelsEnabled  
 Указывает, переносятся ли слова в метках области задач.  
  
```  
BOOL IsWrapLabelsEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если слова в метках, заключаются в оболочку; в противном случае — `FALSE`.  
  
##  <a name="a-nameiswraptasksenableda--cmfctaskspaneiswraptasksenabled"></a><a name="iswraptasksenabled"></a>CMFCTasksPane::IsWrapTasksEnabled  
 Перенос платформа строки задачи.  
  
```  
BOOL IsWrapTasksEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если строка задача заключается в оболочку; в противном случае — `FALSE`.  
  
##  <a name="a-nameloadstatea--cmfctaskspaneloadstate"></a><a name="loadstate"></a>CMFCTasksPane::LoadState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 [in] `nIndex`  
 [in] `uiID`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonactivatetaskspanepagea--cmfctaskspaneonactivatetaskspanepage"></a><a name="onactivatetaskspanepage"></a>CMFCTasksPane::OnActivateTasksPanePage  
 Вызывается платформой, когда он делает активным страницы области задач.  
  
```  
virtual void OnActivateTasksPanePage();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид страницы панели задач.  
  
##  <a name="a-nameoncancela--cmfctaskspaneoncancel"></a><a name="oncancel"></a>CMFCTasksPane::OnCancel  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonclicktaska--cmfctaskspaneonclicktask"></a><a name="onclicktask"></a>CMFCTasksPane::OnClickTask  
 Вызывается платформой по щелчку элемента в области задач.  
  
```  
virtual void OnClickTask(
    int nGroupNumber,  
    int nTaskNumber,  
    UINT uiCommandID,  
    DWORD dwUserData);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroupNumber`  
 Задает отсчитываемый от нуля индекс, содержащий выбранной задачи.  
  
 [in] `nTaskNumber`  
 Задает отсчитываемый от нуля индекс выбранной задачи.  
  
 [in] `uiCommandID`  
 Указывает идентификатор команды, связанные с задачей.  
  
 [in] `dwUserData`  
 Содержит определяемые пользователем данные, связанные с задачей, которую щелкнул пользователь.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда пользователь щелкает задачу. По умолчанию платформа проверяет идентификатор команды, связанные с выбранной задачей и, если он не равен нулю, отправляет `WM_COMMAND` сообщение с владельцем элемента управления области задач.  
  
 Переопределите этот метод в производном классе для выполнения пользовательского кода при щелчке задачи.  
  
##  <a name="a-nameonoka--cmfctaskspaneonok"></a><a name="onok"></a>CMFCTasksPane::OnOK  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonpressbackbuttona--cmfctaskspaneonpressbackbutton"></a><a name="onpressbackbutton"></a>CMFCTasksPane::OnPressBackButton  
 Вызывается платформой по нажатию кнопки перехода назад.  
  
```  
virtual void OnPressBackButton();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа отображает предыдущую страницу.  
  
 Переопределите этот метод в производном классе для выполнения пользовательского кода при нажатии кнопки "Назад".  
  
##  <a name="a-nameonpressforwardbuttona--cmfctaskspaneonpressforwardbutton"></a><a name="onpressforwardbutton"></a>CMFCTasksPane::OnPressForwardButton  
 Вызывается платформой по нажатию кнопки перехода вперед.  
  
```  
virtual void OnPressForwardButton();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа отобразит страницу, которую пользователь просматривать перед нажатием кнопки **обратно** кнопки.  
  
 Переопределите этот метод в производном классе для выполнения пользовательского кода при нажатии кнопки «вперед».  
  
##  <a name="a-nameonpresshomebuttona--cmfctaskspaneonpresshomebutton"></a><a name="onpresshomebutton"></a>CMFCTasksPane::OnPressHomeButton  
 Вызывается платформой, когда пользователь нажимает кнопку home навигации.  
  
```  
virtual void OnPressHomeButton();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа отобразит страницу по умолчанию для группы задач.  
  
 Переопределите этот метод в производном классе для выполнения пользовательского кода при нажатии кнопки home навигации.  
  
##  <a name="a-nameonpressotherbuttona--cmfctaskspaneonpressotherbutton"></a><a name="onpressotherbutton"></a>CMFCTasksPane::OnPressOtherButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnPressOtherButton(
    CMFCCaptionMenuButton* pbtn,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pbtn`  
 [in] `pWndOwner`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonsetaccdataa--cmfctaskspaneonsetaccdata"></a><a name="onsetaccdata"></a>CMFCTasksPane::OnSetAccData  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lVal`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonupdatecmduia--cmfctaskspaneonupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCTasksPane::OnUpdateCmdUI  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTarget`  
 [in] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namepretranslatemessagea--cmfctaskspanepretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCTasksPane::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMsg`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namerecalclayouta--cmfctaskspanerecalclayout"></a><a name="recalclayout"></a>CMFCTasksPane::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void RecalcLayout(BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bRedraw`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameremoveallgroupsa--cmfctaskspaneremoveallgroups"></a><a name="removeallgroups"></a>CMFCTasksPane::RemoveAllGroups  
 Удаляет все группы на указанной странице.  
  
```  
void RemoveAllGroups(int nPageIdx = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPageIdx`  
 Задает отсчитываемый от нуля индекс страницы.  
  
### <a name="remarks"></a>Примечания  
 Удаляет все группы на странице, указываемой `nPageIdx`, или для всех групп, если страница по умолчанию.  
  
##  <a name="a-nameremoveallpagesa--cmfctaskspaneremoveallpages"></a><a name="removeallpages"></a>CMFCTasksPane::RemoveAllPages  
 Удаляет все страницы из области задач, за исключением страницы по умолчанию (первой страницы).  
  
```  
void RemoveAllPages();
```  
  
##  <a name="a-nameremovealltasksa--cmfctaskspaneremovealltasks"></a><a name="removealltasks"></a>CMFCTasksPane::RemoveAllTasks  
 Удаляет все задания из указанной группы.  
  
```  
void RemoveAllTasks(int nGroup);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс группы.  
  
##  <a name="a-nameremovegroupa--cmfctaskspaneremovegroup"></a><a name="removegroup"></a>CMFCTasksPane::RemoveGroup  
 Удаляет группу.  
  
```  
void RemoveGroup(int nGroup);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс группы для удаления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет одну группу. Чтобы удалить все группы, вызвать [CMFCTasksPane::RemoveAllGroups](#removeallgroups) вместо.  
  
 Когда платформа удаляет группу, удаляются все задачи и связанные с ним пользователя windows.  
  
##  <a name="a-nameremovepagea--cmfctaskspaneremovepage"></a><a name="removepage"></a>CMFCTasksPane::RemovePage  
 Удаляет указанную страницу из области задач.  
  
```  
void RemovePage(int nPageIdx);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPageIdx`  
 Задает отсчитываемый от нуля индекс страницы для удаления.  
  
##  <a name="a-nameremovetaska--cmfctaskspaneremovetask"></a><a name="removetask"></a>CMFCTasksPane::RemoveTask  
 Удаляет задачу из группы задач.  
  
```  
BOOL RemoveTask(
    int nGroup,  
    int nTask,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс, содержащий задачу для удаления группы задач.  
  
 [in] `nTask`  
 Задает отсчитываемый от нуля индекс задачи для удаления.  
  
 [in] `bRedraw`  
 `TRUE`для повторной отрисовки панели задач; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если функция выполнена успешно; `FALSE` Если `nGroup` или `nTask` является недопустимым.  
  
##  <a name="a-namesavestatea--cmfctaskspanesavestate"></a><a name="savestate"></a>CMFCTasksPane::SaveState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 [in] `nIndex`  
 [in] `uiID`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameserializea--cmfctaskspaneserialize"></a><a name="serialize"></a>CMFCTasksPane::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetactivepagea--cmfctaskspanesetactivepage"></a><a name="setactivepage"></a>CMFCTasksPane::SetActivePage  
 Активизация указанную страницу в области задач.  
  
```  
void SetActivePage(int nPageIdx);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPageIdx`  
 Задает отсчитываемый от нуля индекс отображаемой страницы.  
  
### <a name="remarks"></a>Примечания  
 Этот метод утверждает, если `nPageIdx` является недопустимым.  
  
##  <a name="a-namesetcaptiona--cmfctaskspanesetcaption"></a><a name="setcaption"></a>CMFCTasksPane::SetCaption  
 Задает заголовок области задач.  
  
```  
void SetCaption(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Задает имя заголовка.  
  
### <a name="remarks"></a>Примечания  
 Если область задач состоит из нескольких страниц, страница по умолчанию имеет заголовок, который был задан с помощью этой функции.  
  
##  <a name="a-namesetgroupcaptionheighta--cmfctaskspanesetgroupcaptionheight"></a><a name="setgroupcaptionheight"></a>CMFCTasksPane::SetGroupCaptionHeight  
 Задает высоту заголовка группы.  
  
```  
void SetGroupCaptionHeight(int n = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
 Указывает высоту заголовка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для настройки полей элементов панели задач.  
  
 Если `n` равно -1, платформа определяет значение поля, используя диспетчер визуального представления ( `CMFCVisualManager::GetTasksPaneGroupCaptionHeight`). Высота заголовка по умолчанию — 25 пикселей.  
  
##  <a name="a-namesetgroupcaptionhorzoffseta--cmfctaskspanesetgroupcaptionhorzoffset"></a><a name="setgroupcaptionhorzoffset"></a>CMFCTasksPane::SetGroupCaptionHorzOffset  
 Задает смещение заголовка группы по горизонтали.  
  
```  
void SetGroupCaptionHorzOffset(int n = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
 Задает горизонтальное смещение заголовка группы.  
  
##  <a name="a-namesetgroupcaptionvertoffseta--cmfctaskspanesetgroupcaptionvertoffset"></a><a name="setgroupcaptionvertoffset"></a>CMFCTasksPane::SetGroupCaptionVertOffset  
 Задает смещение заголовка группы по вертикали.  
  
```  
void SetGroupCaptionVertOffset(int n = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
 Задает вертикальное смещение в пикселях, заголовка группы.  
  
##  <a name="a-namesetgroupnamea--cmfctaskspanesetgroupname"></a><a name="setgroupname"></a>CMFCTasksPane::SetGroupName  
 Задает имя группы.  
  
```  
BOOL SetGroupName(
    int nGroup,  
    LPCTSTR lpszGroupName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс группы.  
  
 [in] `lpszGroupName`  
 Задает имя группы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если имя группы была успешно задана; в противном случае — `FALSE`.  
  
##  <a name="a-namesetgrouptextcolora--cmfctaskspanesetgrouptextcolor"></a><a name="setgrouptextcolor"></a>CMFCTasksPane::SetGroupTextColor  
 Задает цвет текста для заголовка группы.  
  
```  
BOOL SetGroupTextColor(
    int nGroup,  
    COLORREF color,  
    COLORREF colorHot = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс группы.  
  
 [in] `color`  
 Определяет цвет текста.  
  
 [in] `colorHot`  
 Задает цвет текста для выделенной группы. Если значение-1, используется цвет выделения по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если цвет текста группа успешно изменена; в противном случае — `FALSE`.  
  
##  <a name="a-namesetgroupvertoffseta--cmfctaskspanesetgroupvertoffset"></a><a name="setgroupvertoffset"></a>CMFCTasksPane::SetGroupVertOffset  
 Задает смещение группы по вертикали.  
  
```  
void SetGroupVertOffset(int n = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
 Задает вертикальное смещение.  
  
### <a name="remarks"></a>Примечания  
 Смещение по вертикали — это расстояние между группой задач и границей панели задач.  
  
 Этот метод используется для настройки полей элементы в области задач. Если `n` равно -1, платформа определяет значение поля, используя диспетчер визуального представления ( `CMFCVisualManager::GetTasksPaneGroupVertOffset`). Смещение по умолчанию — 15 точек.  
  
##  <a name="a-namesethorzmargina--cmfctaskspanesethorzmargin"></a><a name="sethorzmargin"></a>CMFCTasksPane::SetHorzMargin  
 Задает поля по горизонтали.  
  
```  
void SetHorzMargin(int n = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
 Задает поле, в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Поля по горизонтали — это расстояние между панели задач и верхней или нижней границей клиентской области.  
  
 Если n-1, а платформа определяет значение поля, используя диспетчер визуального представления ( `CMFCVisualManager::GetTasksPaneHorzMargin`). Поля по горизонтали по умолчанию — 12 пикселов.  
  
##  <a name="a-nameseticonslista--cmfctaskspaneseticonslist"></a><a name="seticonslist"></a>CMFCTasksPane::SetIconsList  
 Задает список изображений.  
  
```  
BOOL SetIconsList(
    UINT uiImageListResID,  
    int cx,  
    COLORREF clrTransparent = RGB(255, 0, 255));  
  
void SetIconsList(HIMAGELIST hIcons);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiImageListResID`  
 Указывает идентификатор ресурса для списка изображений.  
  
 [in] `cx`  
 Указывает размер значков в списке изображений.  
  
 [in] `clrTransparent`  
 Указывает прозрачный цвет.  
  
 [in] `hIcons`  
 Задает список изображений, содержит значки для области задач.  
  
### <a name="remarks"></a>Примечания  
 Framework хранит значки в списке изображений. Задачи, связанные со значками, которые хранятся в этом списке.  
  
 Этот метод связывает списка изображений с элементом управления области задач. Чтобы задать значок для задачи, при вызове [CMFCTasksPane::AddTask](#addtask), задайте `nTaskIcon` для соответствующих отсчитываемый от нуля индекс в списке изображений.  
  
##  <a name="a-namesetpagecaptiona--cmfctaskspanesetpagecaption"></a><a name="setpagecaption"></a>CMFCTasksPane::SetPageCaption  
 Задает текст заголовка для страницы области задач.  
  
```  
void SetPageCaption(
    int nPageIdx,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPageIdx`  
 Задает отсчитываемый от нуля индекс страницы.  
  
 [in] `lpszName`  
 Задает текст заголовка для отображения на странице.  
  
### <a name="remarks"></a>Примечания  
 Если область задач состоит из нескольких страниц, страница по умолчанию имеет заголовок, который был задан с помощью этого метода.  
  
##  <a name="a-namesettasknamea--cmfctaskspanesettaskname"></a><a name="settaskname"></a>CMFCTasksPane::SetTaskName  
 Задает имя задачи.  
  
```  
BOOL SetTaskName(
    int nGroup,  
    int nTask,  
    LPCTSTR lpszTaskName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс группы задач.  
  
 [in] `nTask`  
 Задает отсчитываемый от нуля индекс задачи.  
  
 [in] `lpszTaskName`  
 Задает имя задачи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если имя задачи была успешно задана; в противном случае — `FALSE`.  
  
##  <a name="a-namesettaskshorzoffseta--cmfctaskspanesettaskshorzoffset"></a><a name="settaskshorzoffset"></a>CMFCTasksPane::SetTasksHorzOffset  
 Задает горизонтальное смещение для задач.  
  
```  
void SetTasksHorzOffset(int n = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
 Задает горизонтальное смещение.  
  
### <a name="remarks"></a>Примечания  
 Смещение по горизонтали — это расстояние в пикселях от левого и правого краев группы.  
  
 Если `n` равно -1, этот метод задает горизонтальное смещение значение, возвращаемое `CMFCVisualManager::GetTasksPaneTaskHorzOffset` метод.  
  
 Горизонтальное смещение по умолчанию — 12 пикселов.  
  
##  <a name="a-namesettasksiconhorzoffseta--cmfctaskspanesettasksiconhorzoffset"></a><a name="settasksiconhorzoffset"></a>CMFCTasksPane::SetTasksIconHorzOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetTasksIconHorzOffset(int n = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesettasksiconvertoffseta--cmfctaskspanesettasksiconvertoffset"></a><a name="settasksiconvertoffset"></a>CMFCTasksPane::SetTasksIconVertOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetTasksIconVertOffset(int n = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesettasktextcolora--cmfctaskspanesettasktextcolor"></a><a name="settasktextcolor"></a>CMFCTasksPane::SetTaskTextColor  
 Задает цвет текста для задачи.  
  
```  
BOOL SetTaskTextColor(
    int nGroup,  
    int nTask,  
    COLORREF color,  
    COLORREF colorHot = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс группы задач, содержащий задачу.  
  
 [in] `nTask`  
 Задает отсчитываемый от нуля индекс задачи.  
  
 [in] `color`  
 Указывает цвет текста для задачи.  
  
 [in] `colorHot`  
 Задает цвет текста для выделенной группы. Если значение-1, этот метод использует цвет выделения по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если цвет текста для задача была успешно задана; в противном случае — `FALSE`.  
  
##  <a name="a-namesetvertmargina--cmfctaskspanesetvertmargin"></a><a name="setvertmargin"></a>CMFCTasksPane::SetVertMargin  
 Задает вертикальное поле.  
  
```  
void SetVertMargin(int n = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
 Задает вертикальное поле для задания.  
  
### <a name="remarks"></a>Примечания  
 Вертикальное поле — это расстояние между панели задач и вертикальные края клиентской области.  
  
 Если `n` равно -1, платформа определяет значение поля, используя диспетчер визуального представления ( `CMFCVisualManager::GetTasksPaneVertMargin`). Поле по умолчанию — 12 пикселов.  
  
##  <a name="a-namesetwindowheighta--cmfctaskspanesetwindowheight"></a><a name="setwindowheight"></a>CMFCTasksPane::SetWindowHeight  
 Задает высоту элемента управления окна.  
  
```  
BOOL SetWindowHeight(
    int nGroup,  
    HWND hwndTask,  
    int nWndHeight);

 
BOOL SetWindowHeight(
    HWND hwndTask,  
    int nWndHeight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс, содержащий элементы управления окна.  
  
 [in] `hwndTask`  
 Указывает дескриптор окна элемента управления.  
  
 [in] `nWndHeight`  
 Указывает высоту для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если высота элемента управления окна была успешно задана; `FALSE` Если `nGroup` является недопустимым или если `hwndTask` не существует.  
  
### <a name="remarks"></a>Примечания  
 Вызов [CMFCTasksPane::AddWindow](#addwindow) для добавления задач с помощью элементов управления окнами.  
  
##  <a name="a-nameshowcommandmessagestringa--cmfctaskspaneshowcommandmessagestring"></a><a name="showcommandmessagestring"></a>CMFCTasksPane::ShowCommandMessageString  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameshowtaska--cmfctaskspaneshowtask"></a><a name="showtask"></a>CMFCTasksPane::ShowTask  
 Показывает или скрывает задачу.  
  
```  
BOOL ShowTask(
    int nGroup,  
    int nTask,  
    BOOL bShow = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroup`  
 Задает отсчитываемый от нуля индекс группы.  
  
 [in] `nTask`  
 Задает отсчитываемый от нуля индекс задачи, чтобы показать или скрыть.  
  
 [in] `bShow`  
 `TRUE`Чтобы отобразить задачи; `FALSE` для скрытия задачи.  
  
 [in] `bRedraw`  
 `TRUE`для повторной отрисовки панели задач; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если задача была успешно отображены или скрыты; `FALSE` Если указанная группа или задача не существует.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCTasksPane::ShowTaskByCmdId](#showtaskbycmdid) для отображения или скрытия задачи на основе его идентификатора команды.  
  
##  <a name="a-nameshowtaskbycmdida--cmfctaskspaneshowtaskbycmdid"></a><a name="showtaskbycmdid"></a>CMFCTasksPane::ShowTaskByCmdId  
 Показывает или скрывает задачу по ее идентификатору команды.  
  
```  
BOOL ShowTaskByCmdId(
    UINT uiCommandID,  
    BOOL bShow = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCommandID`  
 Указывает идентификатор команды задачи, чтобы показать или скрыть.  
  
 [in] `bShow`  
 `TRUE`Чтобы отобразить задачи; `FALSE` для скрытия задачи.  
  
 [in] `bRedraw`  
 `TRUE`для повторной отрисовки панели задач; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если задача была успешно отображены или скрыты; `FALSE` Если задача с заданным Идентификатором команды не существует.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCTasksPane::ShowTask](#showtask) для отображения или скрытия задачи на основе его идентификатора команды.  
  
##  <a name="a-nameupdatea--cmfctaskspaneupdate"></a><a name="update"></a>CMFCTasksPane::Update  
 Обновляет все элементы управления в области задач.  
  
```  
virtual void Update();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод обновляет заголовок панели задач, настраивает полосы прокрутки, перемещает все задачи и перерисовывает все элементы управления области задач.  
  
 Переопределите этот метод в производном классе для выполнения пользовательского кода, когда платформа обновляет панель задач.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)   
 [Класс CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [Класс CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

