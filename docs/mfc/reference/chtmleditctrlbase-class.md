---
title: "Класс CHtmlEditCtrlBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditCtrlBase
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrlBase class
ms.assetid: e0cc74b4-8320-4570-b673-16c03d2ae266
caps.latest.revision: 21
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
ms.openlocfilehash: e5541025653cca908d5d0c7666a434aa3f81ab5b
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditctrlbase-class"></a>Класс CHtmlEditCtrlBase
Представляет компонент редактирования HTML.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class T> class CHtmlEditCtrlBase  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHtmlEditCtrlBase::AddToGlyphTable](#addtoglyphtable)|Добавляет запись в таблицу глиф указывает, изображения, отображаемые для определенных тегов в режиме конструктора.|  
|[CHtmlEditCtrlBase::Bold](#bold)|Переключает состояние полужирным шрифтом выбранного текста.|  
|[CHtmlEditCtrlBase::Button](#button)|Заменяет элемент управления button для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::CheckBox](#checkbox)|Перезаписывает управления "флажок" для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::ClearSelection](#clearselection)|Отменяет текущее выделение.|  
|[CHtmlEditCtrlBase::Copy](#copy)|Копирует текущее выделение в буфер обмена.|  
|[CHtmlEditCtrlBase::Cut](#cut)|Копирует текущее выделение в буфер обмена, а затем удаляет его.|  
|[CHtmlEditCtrlBase::Delete](#delete)|Удаление выбранного объекта.|  
|[CHtmlEditCtrlBase::DropDownBox](#dropdownbox)|Заменяет элемент управления выбора раскрывающегося списка для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::EmptyGlyphTable](#emptyglyphtable)|Удаляет все записи из таблицы глиф скрывает все изображения, отображаемые для тегов в режиме конструктора.|  
|[CHtmlEditCtrlBase::ExecCommand](#execcommand)|Выполняет команду.|  
|[CHtmlEditCtrlBase::Font](#font)|Откроется диалоговое окно шрифта, чтобы позволить пользователю изменять цвет, шрифт и размер шрифта для текущего выделения.|  
|[CHtmlEditCtrlBase::GetAbsolutePosition](#getabsoluteposition)|Указывает, является ли свойство положение элемента «абсолютный».|  
|[CHtmlEditCtrlBase::GetBackColor](#getbackcolor)|Получает цвет фона текущего выделенного фрагмента.|  
|[CHtmlEditCtrlBase::GetBlockFormat](#getblockformat)|Получает текущий тег формат блока.|  
|[CHtmlEditCtrlBase::GetBlockFormatNames](#getblockformatnames)|Извлекает строки, соответствующие теги форматирования доступного блока.|  
|[CHtmlEditCtrlBase::GetBookMark](#getbookmark)|Возвращает имя привязки закладки.|  
|[CHtmlEditCtrlBase::GetDocument](#getdocument)|Получает объект документа.|  
|[CHtmlEditCtrlBase::GetDocumentHTML](#getdocumenthtml)|Получает HTML-код текущего документа.|  
|[CHtmlEditCtrlBase::GetDocumentTitle](#getdocumenttitle)|Получает название документа.|  
|[CHtmlEditCtrlBase::GetEvent](#getevent)|Получает указатель интерфейса на объект события, содержащий сведения, относящиеся к самых последних событий.|  
|[CHtmlEditCtrlBase::GetEventSrcElement](#geteventsrcelement)|Извлекает объект, создавший событие.|  
|[CHtmlEditCtrlBase::GetFontFace](#getfontface)|Получает имя шрифта для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::GetFontSize](#getfontsize)|Получает размер шрифта для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::GetForeColor](#getforecolor)|Получает цвет переднего плана (текст) текущего выделенного фрагмента.|  
|[CHtmlEditCtrlBase::GetFrameZone](#getframezone)|Возвращает зоны безопасности текущей страницы в веб-браузере.|  
|[CHtmlEditCtrlBase::GetIsDirty](#getisdirty)|Указывает, было ли изменено HTML-документа.|  
|[CHtmlEditCtrlBase::GetShowAlignedSiteTags](#getshowalignedsitetags)|Возвращает, будет ли отображаться глиф для всех элементов, имеющих **styleFloat** свойство.|  
|[CHtmlEditCtrlBase::GetShowAllTags](#getshowalltags)|Возвращает ли браузер отображает глифы для отображения положения всех тегов в документе.|  
|[CHtmlEditCtrlBase::GetShowAreaTags](#getshowareatags)|Сообщает, является ли браузер отображает глиф для области тегов.|  
|[CHtmlEditCtrlBase::GetShowBRTags](#getshowbrtags)|Сообщает, является ли браузер отображает глиф для br тегов.|  
|[CHtmlEditCtrlBase::GetShowCommentTags](#getshowcommenttags)|Сообщает, является ли браузер отображает глиф для тегами комментария.|  
|[CHtmlEditCtrlBase::GetShowMiscTags](#getshowmisctags)|Сообщает, является ли браузер отображает все теги, которые показаны в Microsoft Internet Explorer 4.0.|  
|[CHtmlEditCtrlBase::GetShowScriptTags](#getshowscripttags)|Сообщает, является ли браузер отображает глиф для всех тегов сценария.|  
|[CHtmlEditCtrlBase::GetShowStyleTags](#getshowstyletags)|Сообщает, является ли браузер отображает глиф для всех тегов стиля.|  
|[CHtmlEditCtrlBase::GetShowUnknownTags](#getshowunknowntags)|Сообщает, является ли браузер отображает глиф для всех неизвестных тегов.|  
|[CHtmlEditCtrlBase::HorizontalLine](#horizontalline)|Перезаписывает горизонтальной линии для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::HyperLink](#hyperlink)|Вставка гиперссылки на текущее выделение.|  
|[CHtmlEditCtrlBase::IE50Paste](#ie50paste)|Выполняет операцию вставки, совместимые с Microsoft Internet Explorer 5.|  
|[CHtmlEditCtrlBase::Iframe](#iframe)|Перезаписывает встроенную рамку для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::Image](#image)|Перезаписывает изображения для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::Indent](#indent)|Увеличение отступа выделенного текста на один отступ приращения.|  
|[CHtmlEditCtrlBase::InsFieldSet](#insfieldset)|Перезаписывает поле для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::InsInputButton](#insinputbutton)|Заменяет элемент управления button для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::InsInputHidden](#insinputhidden)|Вставка скрытого элемента управления для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::InsInputImage](#insinputimage)|Перезаписывает рисунка для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::InsInputPassword](#insinputpassword)|Заменяет элемент управления пароль для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::InsInputReset](#insinputreset)|Заменяет элемент управления сброса для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::InsInputSubmit](#insinputsubmit)|Перезаписывает кнопка отправки для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::InsInputUpload](#insinputupload)|Заменяет элемент управления отправкой файлов для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::Is1DElement](#is1delement)|Определяет, если элемент располагается статически.|  
|[CHtmlEditCtrlBase::Is2DElement](#is2delement)|Определяет, если элемент (абсолютное) положение.|  
|[CHtmlEditCtrlBase::Italic](#italic)|Переключает текущий Выбор курсивного и nonitalic.|  
|[CHtmlEditCtrlBase::JustifyCenter](#justifycenter)|Центрирует форматирование блока, в которой находится текущее выделение.|  
|[CHtmlEditCtrlBase::JustifyLeft](#justifyleft)|Выравнивает по левому краю блока format, в которой находится текущее выделение.|  
|[CHtmlEditCtrlBase::JustifyRight](#justifyright)|Выравнивает по правому краю блока format, в которой находится текущее выделение.|  
|[CHtmlEditCtrlBase::ListBox](#listbox)|Перезаписывает окно выбора списка для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::Marquee](#marquee)|Перезаписывает пустая область для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::NewDocument](#newdocument)|Создает новый документ.|  
|[CHtmlEditCtrlBase::OrderList](#orderlist)|Переключает текущий выбор между упорядоченный список и обычное форматирование блока.|  
|[CHtmlEditCtrlBase::Outdent](#outdent)|Уменьшается на один шаг отступ блока format, в которой находится текущее выделение.|  
|[CHtmlEditCtrlBase::Paragraph](#paragraph)|Перезаписывает разрыва строки для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::Paste](#paste)|Перезаписывает содержимое буфера обмена в текущее выделение.|  
|[CHtmlEditCtrlBase::PrintDocument](#printdocument)|Печать текущего документа.|  
|[CHtmlEditCtrlBase::PrintPreview](#printpreview)|Открывается окно предварительного просмотра печати для текущего документа с помощью шаблона предварительного просмотра по умолчанию или пользовательский шаблон.|  
|[CHtmlEditCtrlBase::QueryStatus](#querystatus)|Вызовите этот метод, чтобы запросить состояние команды.|  
|[CHtmlEditCtrlBase::RadioButton](#radiobutton)|Заменяет элемент управления "переключатель" для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::RefreshDocument](#refreshdocument)|Обновление текущего документа.|  
|[CHtmlEditCtrlBase::RemoveFormat](#removeformat)|Удаляет теги форматирования из текущего выделенного фрагмента.|  
|[CHtmlEditCtrlBase::SaveAs](#saveas)|Сохранение текущей веб-страницы в файле.|  
|[CHtmlEditCtrlBase::SelectAll](#selectall)|Выделяет весь документ.|  
|[CHtmlEditCtrlBase::Set2DPosition](#set2dposition)|Позволяет переместить, перетаскивая элементы с абсолютным позиционированием.|  
|[CHtmlEditCtrlBase::SetAbsolutePosition](#setabsoluteposition)|Задает значение свойства position элемента на «абсолютный» или «static».|  
|[CHtmlEditCtrlBase::SetAtomicSelection](#setatomicselection)|Режим выбора atomic.|  
|[CHtmlEditCtrlBase::SetAutoURLDetectMode](#setautourldetectmode)|Включение автоматического обнаружения URL-адрес и отключение.|  
|[CHtmlEditCtrlBase::SetBackColor](#setbackcolor)|Задает цвет фона текущего выделенного фрагмента.|  
|[CHtmlEditCtrlBase::SetBlockFormat](#setblockformat)|Задает текущий тег формат блока.|  
|[CHtmlEditCtrlBase::SetBookMark](#setbookmark)|Создает привязку закладки для текущего выделения или места вставки.|  
|[CHtmlEditCtrlBase::SetCSSEditingLevel](#setcsseditinglevel)|Выбирает уровень CSS (CSS1 или CSS2) Редактор будет поддерживать, если таковые имеются.|  
|[CHtmlEditCtrlBase::SetDefaultComposeSettings](#setdefaultcomposesettings)|Вызов этого метода по умолчанию параметров создания.|  
|[CHtmlEditCtrlBase::SetDesignMode](#setdesignmode)|Режим конструктора.|  
|[CHtmlEditCtrlBase::SetDisableEditFocusUI](#setdisableeditfocusui)|Отключает штриховой границей и обрабатывает вокруг элемента с фокусом редактирования.|  
|[CHtmlEditCtrlBase::SetDocumentHTML](#setdocumenthtml)|Задает HTML-код текущего документа.|  
|[CHtmlEditCtrlBase::SetFontFace](#setfontface)|Задает шрифт для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::SetFontSize](#setfontsize)|Задает размер шрифта для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::SetForeColor](#setforecolor)|Задает цвет переднего плана (текст) текущего выделенного фрагмента.|  
|[CHtmlEditCtrlBase::SetIE5PasteMode](#setie5pastemode)|Задает операции вставки для совместимости с Microsoft Internet Explorer 5.|  
|[CHtmlEditCtrlBase::SetLiveResize](#setliveresize)|В результате WebBrowser обновить вид элемента постоянно во время операции изменения размера или перемещения.|  
|[CHtmlEditCtrlBase::SetMultiSelect](#setmultiselect)|Обеспечивает выбор нескольких элементов.|  
|[CHtmlEditCtrlBase::SetOverrideCursor](#setoverridecursor)|Команды WebBrowser никогда не следует изменять указатель мыши.|  
|[CHtmlEditCtrlBase::SetOverwriteMode](#setoverwritemode)|Режим ввода текста между переключатели вставки и перезаписать.|  
|[CHtmlEditCtrlBase::SetRespectVisInDesign](#setrespectvisindesign)|Скрывает невидимых элементов в режиме конструктора.|  
|[CHtmlEditCtrlBase::SetShowAlignedSiteTags](#setshowalignedsitetags)|Отображает глиф для всех элементов, имеющих **styleFloat** свойство.|  
|[CHtmlEditCtrlBase::SetShowAllTags](#setshowalltags)|Отображает глифы для отображения положения всех тегов в документе.|  
|[CHtmlEditCtrlBase::SetShowAreaTags](#setshowareatags)|Отображает глиф для всех тегов области.|  
|[CHtmlEditCtrlBase::SetShowBRTags](#setshowbrtags)|Отображает глиф для всех тегов br.|  
|[CHtmlEditCtrlBase::SetShowCommentTags](#setshowcommenttags)|Отображает глиф для всех тегов комментария.|  
|[CHtmlEditCtrlBase::SetShowMiscTags](#setshowmisctags)|Отображает все теги, которые показаны в Microsoft Internet Explorer 4.0.|  
|[CHtmlEditCtrlBase::SetShowScriptTags](#setshowscripttags)|Отображает глиф для всех тегов сценария.|  
|[CHtmlEditCtrlBase::SetShowStyleTags](#setshowstyletags)|Отображает глиф для всех тегов стиля.|  
|[CHtmlEditCtrlBase::SetShowUnknownTags](#setshowunknowntags)|Отображает глиф для всех неизвестных тегов.|  
|[CHtmlEditCtrlBase::TextArea](#textarea)|Перезаписывает многострочный управления для ввода текста для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::TextBox](#textbox)|Перезаписывает текстового элемента управления для выделенного фрагмента.|  
|[CHtmlEditCtrlBase::UnBookmark](#unbookmark)|Удаляет все закладки из текущего выделенного фрагмента.|  
|[CHtmlEditCtrlBase::Underline](#underline)|Переключение между подчеркнут и не подчеркнуто текущее выделение.|  
|[CHtmlEditCtrlBase::Unlink](#unlink)|Удаляет все гиперссылки из текущего выделенного фрагмента.|  
|[CHtmlEditCtrlBase::UnorderList](#unorderlist)|Переключает текущий выбор между упорядоченный список и обычное форматирование блока.|  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Имя производного класса.  
  
## <a name="remarks"></a>Примечания  
 **CHtmlEditCtrlBase** предоставляет функции-члены для команд редактирования, такие как HTML WebBrowser [Полужирный](#bold). (Кроме того, можно вызвать [ExecCommand](#execcommand) для выполнения **IDM_BOLD** команды.)  
  
 **CHtmlEditCtrlBase** не является автономной свой собственный. Он разработан как базовый класс для производных классов, которые предоставляют функциональные возможности элемента управления WebBrowser редактирования HTML (см. [CHtmlEditCtrl](../../mfc/reference/chtmleditctrl-class.md) и [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CHtmlEditCtrlBase`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxhtml.h  
  
##  <a name="a-nameaddtoglyphtablea--chtmleditctrlbaseaddtoglyphtable"></a><a name="addtoglyphtable"></a>CHtmlEditCtrlBase::AddToGlyphTable  
 Добавляет запись в таблицу глиф указывает, изображения, отображаемые для определенных тегов в режиме конструктора.  
  
```  
HRESULT AddToGlyphTable(
    LPCTSTR szTag,  
    LPCTSTR szImgUrl,  
    unsigned short nTagType,  
    unsigned short nAlignment,  
    unsigned short nPosInfo,  
    unsigned short nDirection,  
    unsigned int nImgWidth,  
    unsigned int nImgHeight) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szTag`  
 Имя тега (например, «P» или «таблица»).  
  
 *szImgUrl*  
 URL-адрес изображения.  
  
 *nTagType*  
 Типа тега: 0 означает образ предназначен для только открывающий тег. 1 означает, что образ предназначен для только закрывающий тег. 2 означает, что образ предназначен для открывающим и закрывающим тегами. Один теги, такие как комментарий и br должно быть добавлено с типом тега, равным 0.  
  
 *nAlignment*  
 Выравнивание (только для прямоугольный элементы): этот параметр определяет изображения для элемента с атрибут выравнивания. Щелчок = 0, центр = 1, прямо = 2, а не определено = 3. Слева, справа или атрибутами center должны задаваться явным образом в элементе.  
  
 *nPosInfo*  
 Данные размещения. Определяет, какие каскадные таблицы стилей (CSS) позиционирования значение относится глифа, где статический позиционирования = 0, абсолютное позиционирование = 1, относительное расположение = 2, а также все = 3. Это поле позволяет указать один глиф для тега, если он не размещается и другой глиф для отображения опорную точку при позиционировании тег.  
  
 *nDirection*  
 Направление. Этот параметр задает изображение, чтобы тег, основанный на порядок чтения для текущего языка. значение 0 указывает, слева направо, 1 указывает справа налево, 2 означает сверху вниз, 3 указывает снизу вверх и 4 указывает все. Обычно это поле равным 4.  
  
 *nImgWidth*  
 Ширина изображения в точках.  
  
 *nImgHeight*  
 Высота изображения в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о параметрах см. в разделе «Формат строки таблицы глиф» в [с помощью редактирования глифы](https://msdn.microsoft.com/library/aa969614.aspx).  
  
 Этот метод отправляет [идентификатор команды IDM_ADDTOGLYPHTABLE](https://msdn.microsoft.com/library/aa769891.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namebolda--chtmleditctrlbasebold"></a><a name="bold"></a>CHtmlEditCtrlBase::Bold  
 Переключает состояние полужирным шрифтом выбранного текста.  
  
```  
HRESULT Bold() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_BOLD](https://msdn.microsoft.com/library/aa769861.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namebuttona--chtmleditctrlbasebutton"></a><a name="button"></a>CHtmlEditCtrlBase::Button  
 Заменяет элемент управления button для выделенного фрагмента.  
  
```  
HRESULT Button(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор элемента управления button.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_BUTTON](https://msdn.microsoft.com/library/aa769966.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namecheckboxa--chtmleditctrlbasecheckbox"></a><a name="checkbox"></a>CHtmlEditCtrlBase::CheckBox  
 Перезаписывает управления "флажок" для выделенного фрагмента.  
  
```  
HRESULT CheckBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор элемента управления флажком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_CHECKBOX](https://msdn.microsoft.com/library/aa769972.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameclearselectiona--chtmleditctrlbaseclearselection"></a><a name="clearselection"></a>CHtmlEditCtrlBase::ClearSelection  
 Отменяет текущее выделение.  
  
```  
HRESULT ClearSelection() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_CLEARSELECTION](https://msdn.microsoft.com/library/aa770038.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namecopya--chtmleditctrlbasecopy"></a><a name="copy"></a>CHtmlEditCtrlBase::Copy  
 Копирует текущее выделение в буфер обмена.  
  
```  
HRESULT Copy() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_COPY](https://msdn.microsoft.com/library/aa769872.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namecuta--chtmleditctrlbasecut"></a><a name="cut"></a>CHtmlEditCtrlBase::Cut  
 Копирует текущее выделение в буфер обмена, а затем удаляет его.  
  
```  
HRESULT Cut() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_CUT](https://msdn.microsoft.com/library/aa769875.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namedeletea--chtmleditctrlbasedelete"></a><a name="delete"></a>CHtmlEditCtrlBase::Delete  
 Удаление выбранного объекта.  
  
```  
HRESULT Delete() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_DELETE](https://msdn.microsoft.com/library/aa769876.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namedropdownboxa--chtmleditctrlbasedropdownbox"></a><a name="dropdownbox"></a>CHtmlEditCtrlBase::DropDownBox  
 Заменяет элемент управления выбора раскрывающегося списка для выделенного фрагмента.  
  
```  
HRESULT DropDownBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор элемента управления выбора раскрывающегося списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_DROPDOWNBOX](https://msdn.microsoft.com/library/aa769984.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameemptyglyphtablea--chtmleditctrlbaseemptyglyphtable"></a><a name="emptyglyphtable"></a>CHtmlEditCtrlBase::EmptyGlyphTable  
 Удаляет все записи из таблицы глиф скрывает все изображения, отображаемые для тегов в режиме конструктора.  
  
```  
HRESULT EmptyGlyphTable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_EMPTYGLYPHTABLE](https://msdn.microsoft.com/library/aa769907.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameexeccommanda--chtmleditctrlbaseexeccommand"></a><a name="execcommand"></a>CHtmlEditCtrlBase::ExecCommand  
 Выполняет команду.  
  
```  
HRESULT ExecCommand(
    long cmdID,  
    long cmdExecOpt,  
    VARIANT* pInVar = NULL,  
    VARIANT* pOutVar = NULL) const;  
  
HRESULT ExecCommand(
    const GUID* pGuid,  
    long cmdID,  
    long cmdExecOpt,  
    VARIANT* pInVar = NULL,  
    VARIANT* pOutVar = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды для выполнения. Список см. в разделе [идентификаторы команд MSHTML](https://msdn.microsoft.com/library/aa741315.aspx).  
  
 `cmdExecOpt`  
 Значения, взятые из [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) перечисления, описывают, как объект выполнения команды.  
  
 *pInVar*  
 Входные аргументы.  
  
 *pOutVar*  
 Выходные данные команды.  
  
 *pGuid*  
 Идентификатор GUID группы команд.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод предоставляет функциональные возможности [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300).  
  
##  <a name="a-namefonta--chtmleditctrlbasefont"></a><a name="font"></a>CHtmlEditCtrlBase::Font  
 Откроется диалоговое окно шрифта, чтобы позволить пользователю изменять цвет, шрифт и размер шрифта для текущего выделения.  
  
```  
HRESULT Font() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_FONT](https://msdn.microsoft.com/library/aa769913.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namegetabsolutepositiona--chtmleditctrlbasegetabsoluteposition"></a><a name="getabsoluteposition"></a>CHtmlEditCtrlBase::GetAbsolutePosition  
 Указывает, является ли свойство положение элемента «абсолютный».  
  
```  
HRESULT GetAbsolutePosition(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если свойство положение элемента на «абсолютный.»  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_ABSOLUTE_POSITION](https://msdn.microsoft.com/library/aa769889.aspx).  
  
##  <a name="a-namegetbackcolora--chtmleditctrlbasegetbackcolor"></a><a name="getbackcolor"></a>CHtmlEditCtrlBase::GetBackColor  
 Получает цвет фона текущего выделенного фрагмента.  
  
```  
HRESULT GetBackColor(int& nColor) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nColor`  
 Цвет фона.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_BACKCOLOR](https://msdn.microsoft.com/library/aa769858.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namegetblockformata--chtmleditctrlbasegetblockformat"></a><a name="getblockformat"></a>CHtmlEditCtrlBase::GetBlockFormat  
 Получает текущий тег формат блока.  
  
```  
HRESULT GetBlockFormat(CString& strFormat) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *strFormat*  
 Текущий тег формат блока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_BLOCKFMT](https://msdn.microsoft.com/library/aa769883.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namegetblockformatnamesa--chtmleditctrlbasegetblockformatnames"></a><a name="getblockformatnames"></a>CHtmlEditCtrlBase::GetBlockFormatNames  
 Извлекает строки, соответствующие теги форматирования доступного блока.  
  
```  
HRESULT GetBlockFormatNames(CStringArray& sa) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *SA*  
 Формат доступный блок теги как массив строк.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM_GETBLOCKFMTS ИД команды](https://msdn.microsoft.com/library/aa769884.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namegetbookmarka--chtmleditctrlbasegetbookmark"></a><a name="getbookmark"></a>CHtmlEditCtrlBase::GetBookMark  
 Возвращает имя привязки закладки.  
  
```  
HRESULT GetBookMark(CString& strAnchor) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *strAnchor*  
 Имя привязки закладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_BOOKMARK](https://msdn.microsoft.com/library/aa769873.aspx).  
  
##  <a name="a-namegetdocumenta--chtmleditctrlbasegetdocument"></a><a name="getdocument"></a>CHtmlEditCtrlBase::GetDocument  
 Получает объект документа.  
  
```  
HRESULT GetDocument(IHTMLDocument2** ppDoc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppDoc`  
 Объект документа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namegetdocumenthtmla--chtmleditctrlbasegetdocumenthtml"></a><a name="getdocumenthtml"></a>CHtmlEditCtrlBase::GetDocumentHTML  
 Получает HTML-код текущего документа.  
  
```  
HRESULT GetDocumentHTML(CString& szHTML) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szHTML`  
 HTML-код.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namegetdocumenttitlea--chtmleditctrlbasegetdocumenttitle"></a><a name="getdocumenttitle"></a>CHtmlEditCtrlBase::GetDocumentTitle  
 Получает название документа.  
  
```  
HRESULT GetDocumentTitle(CString& szTitle) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *szTitle*  
 Название документа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namegeteventa--chtmleditctrlbasegetevent"></a><a name="getevent"></a>CHtmlEditCtrlBase::GetEvent  
 Получает указатель интерфейса на объект события, содержащий сведения, относящиеся к самых последних событий.  
  
```  
HRESULT GetEvent(IHTMLEventObj** ppEventObj) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppEventObj`  
 Объект события.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namegeteventsrcelementa--chtmleditctrlbasegeteventsrcelement"></a><a name="geteventsrcelement"></a>CHtmlEditCtrlBase::GetEventSrcElement  
 Извлекает объект, создавший событие.  
  
```  
HRESULT GetEventSrcElement(IHTMLElement** ppSrcElement) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ppSrcElement*  
 Элемент, инициировавший событие.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namegetfontfacea--chtmleditctrlbasegetfontface"></a><a name="getfontface"></a>CHtmlEditCtrlBase::GetFontFace  
 Получает имя шрифта для выделенного фрагмента.  
  
```  
HRESULT GetFontFace(CString& strFace) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `strFace`  
 Имя шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Если текущее выделение использует несколько шрифтов `strFace` будет пустая строка.  
  
 Этот метод отправляет [идентификатор команды IDM_FONTNAME](https://msdn.microsoft.com/library/aa769880.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namegetfontsizea--chtmleditctrlbasegetfontsize"></a><a name="getfontsize"></a>CHtmlEditCtrlBase::GetFontSize  
 Получает размер шрифта для выделенного фрагмента.  
  
```  
HRESULT GetFontSize(short& nSize) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nSize`  
 Размер шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер шрифта HTML (1-7). Возвращает 0, если выделение содержит несколько размеров шрифта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_FONTSIZE](https://msdn.microsoft.com/library/aa769881.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namegetforecolora--chtmleditctrlbasegetforecolor"></a><a name="getforecolor"></a>CHtmlEditCtrlBase::GetForeColor  
 Получает цвет переднего плана (текст) текущего выделенного фрагмента.  
  
```  
HRESULT GetForeColor(int& nColor);
```  
  
### <a name="parameters"></a>Параметры  
 `nColor`  
 Цвет переднего плана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_FORECOLOR](https://msdn.microsoft.com/library/aa769882.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namegetframezonea--chtmleditctrlbasegetframezone"></a><a name="getframezone"></a>CHtmlEditCtrlBase::GetFrameZone  
 Возвращает зоны безопасности текущей страницы в веб-браузере.  
  
```  
HRESULT GetFrameZone(short& nZone) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nZone*  
 Зоны безопасности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_GETFRAMEZONE](https://msdn.microsoft.com/library/aa769916.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namegetisdirtya--chtmleditctrlbasegetisdirty"></a><a name="getisdirty"></a>CHtmlEditCtrlBase::GetIsDirty  
 Указывает, было ли изменено HTML-документа.  
  
```  
HRESULT GetIsDirty() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Указывает, является ли документ был изменен. `GetIsDirty`Возвращает `HRESULT` из [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910).  
  
##  <a name="a-namegetshowalignedsitetagsa--chtmleditctrlbasegetshowalignedsitetags"></a><a name="getshowalignedsitetags"></a>CHtmlEditCtrlBase::GetShowAlignedSiteTags  
 Возвращает, будет ли отображаться глиф для всех элементов, имеющих **styleFloat** свойство.  
  
```  
HRESULT GetShowAlignedSiteTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если глиф отображается для всех элементов, имеющих **styleFloat** свойства; значение false, если не отображается ни одного глифа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_SHOWALIGNEDSITETAGS](https://msdn.microsoft.com/library/aa769947.aspx).  
  
##  <a name="a-namegetshowalltagsa--chtmleditctrlbasegetshowalltags"></a><a name="getshowalltags"></a>CHtmlEditCtrlBase::GetShowAllTags  
 Возвращает ли браузер отображает глифы для отображения положения всех тегов в документе.  
  
```  
HRESULT GetShowAllTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если браузер отображает глифы для отображения положения всех тегов в документе; значение false, если это не так.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_SHOWALLTAGS](https://msdn.microsoft.com/library/aa769948.aspx).  
  
##  <a name="a-namegetshowareatagsa--chtmleditctrlbasegetshowareatags"></a><a name="getshowareatags"></a>CHtmlEditCtrlBase::GetShowAreaTags  
 Сообщает, является ли браузер отображает глиф для области тегов.  
  
```  
HRESULT GetShowAreaTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если браузер отображает глиф тегов области false, если это не так.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_SHOWAREATAGS](https://msdn.microsoft.com/library/aa769949.aspx).  
  
##  <a name="a-namegetshowbrtagsa--chtmleditctrlbasegetshowbrtags"></a><a name="getshowbrtags"></a>CHtmlEditCtrlBase::GetShowBRTags  
 Сообщает, является ли браузер отображает глиф для br тегов.  
  
```  
HRESULT GetShowBRTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если браузер отображает глиф для тегов br false если это не так.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_SHOWWBRTAGS](https://msdn.microsoft.com/library/aa769956.aspx).  
  
##  <a name="a-namegetshowcommenttagsa--chtmleditctrlbasegetshowcommenttags"></a><a name="getshowcommenttags"></a>CHtmlEditCtrlBase::GetShowCommentTags  
 Сообщает, является ли браузер отображает глиф для тегами комментария.  
  
```  
HRESULT GetShowCommentTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если WebBrowser false отображает глиф для комментариев, если это не так.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_SHOWCOMMENTTAGS](https://msdn.microsoft.com/library/aa769950.aspx).  
  
##  <a name="a-namegetshowmisctagsa--chtmleditctrlbasegetshowmisctags"></a><a name="getshowmisctags"></a>CHtmlEditCtrlBase::GetShowMiscTags  
 Сообщает, является ли браузер отображает все теги, которые показаны в Microsoft Internet Explorer 4.0.  
  
```  
HRESULT GetShowMiscTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если браузер отображает все теги, показанный в Microsoft Internet Explorer 4.0, false, если это не так.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_SHOWMISCTAGS](https://msdn.microsoft.com/library/aa769952.aspx).  
  
##  <a name="a-namegetshowscripttagsa--chtmleditctrlbasegetshowscripttags"></a><a name="getshowscripttags"></a>CHtmlEditCtrlBase::GetShowScriptTags  
 Сообщает, является ли браузер отображает глиф для всех тегов сценария.  
  
```  
HRESULT GetShowScriptTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если браузер отображает глиф для всех тегов скрипта, значение false, если это не так.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_SHOWSCRIPTTAGS](https://msdn.microsoft.com/library/aa769953.aspx).  
  
##  <a name="a-namegetshowstyletagsa--chtmleditctrlbasegetshowstyletags"></a><a name="getshowstyletags"></a>CHtmlEditCtrlBase::GetShowStyleTags  
 Сообщает, является ли браузер отображает глиф для всех тегов стиля.  
  
```  
HRESULT GetShowStyleTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если браузер отображает глиф для всех тегов стиля, значение false, если это не так  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_SHOWSTYLETAGS](https://msdn.microsoft.com/library/aa769954.aspx).  
  
##  <a name="a-namegetshowunknowntagsa--chtmleditctrlbasegetshowunknowntags"></a><a name="getshowunknowntags"></a>CHtmlEditCtrlBase::GetShowUnknownTags  
 Сообщает, является ли браузер отображает глиф для всех неизвестных тегов.  
  
```  
HRESULT GetShowUnknownTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bCurValue`  
 Значение true, если браузер отображает глиф для всех неизвестных тегов, значение false, если это не так.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [идентификатор команды IDM_SHOWUNKNOWNTAGS](https://msdn.microsoft.com/library/aa769955.aspx).  
  
##  <a name="a-namehorizontallinea--chtmleditctrlbasehorizontalline"></a><a name="horizontalline"></a>CHtmlEditCtrlBase::HorizontalLine  
 Перезаписывает горизонтальной линии для выделенного фрагмента.  
  
```  
HRESULT HorizontalLine(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *szID*  
 Идентификатор для горизонтальной линии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_HORIZONTALLINE](https://msdn.microsoft.com/library/aa769968.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namehyperlinka--chtmleditctrlbasehyperlink"></a><a name="hyperlink"></a>CHtmlEditCtrlBase::HyperLink  
 Вставка гиперссылки на текущее выделение.  
  
```  
HRESULT HyperLink(LPCTSTR szUrl = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szUrl`  
 URL-адрес гиперссылки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_HYPERLINK](https://msdn.microsoft.com/library/aa769874.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameie50pastea--chtmleditctrlbaseie50paste"></a><a name="ie50paste"></a>CHtmlEditCtrlBase::IE50Paste  
 Выполняет операцию вставки, которая совместима с Internet Explorer 5.  
  
```  
HRESULT IE50Paste(LPCTSTR szData) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szData`  
 Строка для вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_IE50_PASTE](https://msdn.microsoft.com/library/aa769922.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameiframea--chtmleditctrlbaseiframe"></a><a name="iframe"></a>CHtmlEditCtrlBase::Iframe  
 Перезаписывает встроенную рамку для выделенного фрагмента.  
  
```  
HRESULT Iframe(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для рамки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_IFRAME](https://msdn.microsoft.com/library/aa769969.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameimagea--chtmleditctrlbaseimage"></a><a name="image"></a>CHtmlEditCtrlBase::Image  
 Перезаписывает изображения для выделенного фрагмента.  
  
```  
HRESULT Image(LPCTSTR szUrl = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szUrl`  
 Путь и имя изображения для вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_IMAGE](https://msdn.microsoft.com/library/aa769970.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameindenta--chtmleditctrlbaseindent"></a><a name="indent"></a>CHtmlEditCtrlBase::Indent  
 Увеличение отступа выделенного текста на один отступ приращения.  
  
```  
HRESULT Indent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_INDENT](https://msdn.microsoft.com/library/aa769963.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameinsfieldseta--chtmleditctrlbaseinsfieldset"></a><a name="insfieldset"></a>CHtmlEditCtrlBase::InsFieldSet  
 Перезаписывает поле для выделенного фрагмента.  
  
```  
HRESULT InsFieldSet(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для поля.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_INSFIELDSET](https://msdn.microsoft.com/library/aa769967.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameinsinputbuttona--chtmleditctrlbaseinsinputbutton"></a><a name="insinputbutton"></a>CHtmlEditCtrlBase::InsInputButton  
 Заменяет элемент управления button для выделенного фрагмента.  
  
```  
HRESULT InsInputButton(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для элемента управления button.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_INSINPUTBUTTON](https://msdn.microsoft.com/library/aa769971.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameinsinputhiddena--chtmleditctrlbaseinsinputhidden"></a><a name="insinputhidden"></a>CHtmlEditCtrlBase::InsInputHidden  
 Вставка скрытого элемента управления для выделенного фрагмента.  
  
```  
HRESULT InsInputHidden(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для скрытого элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_INSINPUTHIDDEN](https://msdn.microsoft.com/library/aa769974.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameinsinputimagea--chtmleditctrlbaseinsinputimage"></a><a name="insinputimage"></a>CHtmlEditCtrlBase::InsInputImage  
 Перезаписывает рисунка для выделенного фрагмента.  
  
```  
HRESULT InsInputImage(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для элемента управления image.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_INSINPUTIMAGE](https://msdn.microsoft.com/library/aa769975.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameinsinputpassworda--chtmleditctrlbaseinsinputpassword"></a><a name="insinputpassword"></a>CHtmlEditCtrlBase::InsInputPassword  
 Заменяет элемент управления пароль для выделенного фрагмента.  
  
```  
HRESULT InsInputPassword(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для элемента управления пароль.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_INSINPUTPASSWORD](https://msdn.microsoft.com/library/aa769976.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameinsinputreseta--chtmleditctrlbaseinsinputreset"></a><a name="insinputreset"></a>CHtmlEditCtrlBase::InsInputReset  
 Заменяет элемент управления сброса для выделенного фрагмента.  
  
```  
HRESULT InsInputReset(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для соответствующего элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_INSINPUTRESET](https://msdn.microsoft.com/library/aa769978.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameinsinputsubmita--chtmleditctrlbaseinsinputsubmit"></a><a name="insinputsubmit"></a>CHtmlEditCtrlBase::InsInputSubmit  
 Перезаписывает кнопка отправки для выделенного фрагмента.  
  
```  
HRESULT InsInputSubmit(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для элемента управления отправки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_INSINPUTSUBMIT](https://msdn.microsoft.com/library/aa769979.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameinsinputuploada--chtmleditctrlbaseinsinputupload"></a><a name="insinputupload"></a>CHtmlEditCtrlBase::InsInputUpload  
 Заменяет элемент управления отправкой файлов для выделенного фрагмента.  
  
```  
HRESULT InsInputUpload(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор элемента управления отправкой файлов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_INSINPUTUPLOAD](https://msdn.microsoft.com/library/aa769973.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameis1delementa--chtmleditctrlbaseis1delement"></a><a name="is1delement"></a>CHtmlEditCtrlBase::Is1DElement  
 Определяет, если элемент располагается статически.  
  
```  
HRESULT Is1DElement(bool& bValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bValue`  
 Значение true, если элемент является статически позиционированные, и false в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_1D_ELEMENT](https://msdn.microsoft.com/library/aa769885.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameis2delementa--chtmleditctrlbaseis2delement"></a><a name="is2delement"></a>CHtmlEditCtrlBase::Is2DElement  
 Определяет, если элемент (абсолютное) положение.  
  
```  
HRESULT Is2DElement(bool& bValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bValue`  
 Значение true, если элемент является абсолютным позиционированием, и false в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_2D_ELEMENT](https://msdn.microsoft.com/library/aa769886.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameitalica--chtmleditctrlbaseitalic"></a><a name="italic"></a>CHtmlEditCtrlBase::Italic  
 Переключает текущий Выбор курсивного и nonitalic.  
  
```  
HRESULT Italic() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_ITALIC](https://msdn.microsoft.com/library/aa769988.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namejustifycentera--chtmleditctrlbasejustifycenter"></a><a name="justifycenter"></a>CHtmlEditCtrlBase::JustifyCenter  
 Центрирует форматирование блока, в которой находится текущее выделение.  
  
```  
HRESULT JustifyCenter() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_JUSTIFYCENTER](https://msdn.microsoft.com/library/aa769989.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namejustifylefta--chtmleditctrlbasejustifyleft"></a><a name="justifyleft"></a>CHtmlEditCtrlBase::JustifyLeft  
 Выравнивает по левому краю блока format, в которой находится текущее выделение.  
  
```  
HRESULT JustifyLeft() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_JUSTIFYLEFT](https://msdn.microsoft.com/library/aa770011.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namejustifyrighta--chtmleditctrlbasejustifyright"></a><a name="justifyright"></a>CHtmlEditCtrlBase::JustifyRight  
 Выравнивает по правому краю блока format, в которой находится текущее выделение.  
  
```  
HRESULT JustifyRight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_JUSTIFYRIGHT](https://msdn.microsoft.com/library/aa770013.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namelistboxa--chtmleditctrlbaselistbox"></a><a name="listbox"></a>CHtmlEditCtrlBase::ListBox  
 Перезаписывает окно выбора списка для выделенного фрагмента.  
  
```  
HRESULT ListBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для управления "список".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_LISTBOX](https://msdn.microsoft.com/library/aa769985.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namemarqueea--chtmleditctrlbasemarquee"></a><a name="marquee"></a>CHtmlEditCtrlBase::Marquee  
 Перезаписывает пустая область для выделенного фрагмента.  
  
```  
HRESULT Marquee(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для бегущей строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_MARQUEE](https://msdn.microsoft.com/library/aa769981.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namenewdocumenta--chtmleditctrlbasenewdocument"></a><a name="newdocument"></a>CHtmlEditCtrlBase::NewDocument  
 Создает новый документ.  
  
```  
HRESULT NewDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-nameorderlista--chtmleditctrlbaseorderlist"></a><a name="orderlist"></a>CHtmlEditCtrlBase::OrderList  
 Переключает текущий выбор между упорядоченный список и обычное форматирование блока.  
  
```  
HRESULT OrderList(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор упорядоченный список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_ORDERLIST](https://msdn.microsoft.com/library/aa769982.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameoutdenta--chtmleditctrlbaseoutdent"></a><a name="outdent"></a>CHtmlEditCtrlBase::Outdent  
 Уменьшается на один шаг отступ блока format, в которой находится текущее выделение.  
  
```  
HRESULT Outdent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_OUTDENT](https://msdn.microsoft.com/library/aa770015.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameparagrapha--chtmleditctrlbaseparagraph"></a><a name="paragraph"></a>CHtmlEditCtrlBase::Paragraph  
 Перезаписывает разрыва строки для выделенного фрагмента.  
  
```  
HRESULT Paragraph(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор для абзаца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_PARAGRAPH](https://msdn.microsoft.com/library/aa769983.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namepastea--chtmleditctrlbasepaste"></a><a name="paste"></a>CHtmlEditCtrlBase::Paste  
 Перезаписывает содержимое буфера обмена в текущее выделение.  
  
```  
HRESULT Paste() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_PASTE](https://msdn.microsoft.com/library/aa770017.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameprintdocumenta--chtmleditctrlbaseprintdocument"></a><a name="printdocument"></a>CHtmlEditCtrlBase::PrintDocument  
 Печать текущего документа.  
  
```  
HRESULT PrintDocument() const;  
HRESULT PrintDocument(LPCTSTR szPrintTemplate) const;  
HRESULT PrintDocument(bool bShowPrintDialog) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szPrintTemplate`  
 Путь к шаблону печати; Если ничего не указано, используется шаблон печати по умолчанию.  
  
 *bShowPrintDialog*  
 Если значение равно true, отображает диалоговое окно печати.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_PRINT](https://msdn.microsoft.com/library/aa769937.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameprintpreviewa--chtmleditctrlbaseprintpreview"></a><a name="printpreview"></a>CHtmlEditCtrlBase::PrintPreview  
 Открывается окно предварительного просмотра печати для текущего документа с помощью шаблона предварительного просмотра по умолчанию или пользовательский шаблон.  
  
```  
HRESULT PrintPreview() const;  
HRESULT PrintPreview(LPCTSTR szPrintTemplate) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szPrintTemplate`  
 Путь к шаблону печати.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_PRINTPREVIEW](https://msdn.microsoft.com/library/aa769938.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namequerystatusa--chtmleditctrlbasequerystatus"></a><a name="querystatus"></a>CHtmlEditCtrlBase::QueryStatus  
 Вызовите этот метод, чтобы запросить состояние команды.  
  
```  
long QueryStatus(long cmdID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды. Идентификаторы команд, взяты из `CGID_MSHTML`группы команд. Эти команды определены в Mshtmcid.h. Также можно найти в списке сети [идентификаторы команд MSHTML](http://go.microsoft.com/fwlink/linkid=149220).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237) , показывающая состояние `cmdID`, или 0 в случае сбоя.  
  
##  <a name="a-nameradiobuttona--chtmleditctrlbaseradiobutton"></a><a name="radiobutton"></a>CHtmlEditCtrlBase::RadioButton  
 Заменяет элемент управления "переключатель" для выделенного фрагмента.  
  
```  
HRESULT RadioButton(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор переключателя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_RADIOBUTTON](https://msdn.microsoft.com/library/aa769977.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namerefreshdocumenta--chtmleditctrlbaserefreshdocument"></a><a name="refreshdocument"></a>CHtmlEditCtrlBase::RefreshDocument  
 Обновление текущего документа.  
  
```  
HRESULT RefreshDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_REFRESH](https://msdn.microsoft.com/library/aa770020.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameremoveformata--chtmleditctrlbaseremoveformat"></a><a name="removeformat"></a>CHtmlEditCtrlBase::RemoveFormat  
 Удаляет теги форматирования из текущего выделенного фрагмента.  
  
```  
HRESULT RemoveFormat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_REMOVEFORMAT](https://msdn.microsoft.com/library/aa770021.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesaveasa--chtmleditctrlbasesaveas"></a><a name="saveas"></a>CHtmlEditCtrlBase::SaveAs  
 Сохранение текущей веб-страницы в файле.  
  
```  
HRESULT SaveAs(LPCTSTR szPath = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szPath`  
 Путь и имя файла для сохранения веб-страницы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM_SAVEAS ИД команды](https://msdn.microsoft.com/library/aa770024.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameselectalla--chtmleditctrlbaseselectall"></a><a name="selectall"></a>CHtmlEditCtrlBase::SelectAll  
 Выделяет весь документ.  
  
```  
HRESULT SelectAll() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_SELECTALL](https://msdn.microsoft.com/library/aa770025.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameset2dpositiona--chtmleditctrlbaseset2dposition"></a><a name="set2dposition"></a>CHtmlEditCtrlBase::Set2DPosition  
 Позволяет переместить, перетаскивая элементы с абсолютным позиционированием.  
  
```  
HRESULT Set2DPosition(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Значение true, если элементы с абсолютным позиционированием можно перемещать путем перетаскивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_2D_POSITION](https://msdn.microsoft.com/library/aa769887.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetabsolutepositiona--chtmleditctrlbasesetabsoluteposition"></a><a name="setabsoluteposition"></a>CHtmlEditCtrlBase::SetAbsolutePosition  
 Задает значение свойства position элемента на «абсолютный» или «static».  
  
```  
HRESULT SetAbsolutePosition(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Значение true, если свойство положение элемента «абсолютный»; Если значение равно false, это «static».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_ABSOLUTE_POSITION](https://msdn.microsoft.com/library/aa769889.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetatomicselectiona--chtmleditctrlbasesetatomicselection"></a><a name="setatomicselection"></a>CHtmlEditCtrlBase::SetAtomicSelection  
 Режим выбора atomic.  
  
```  
HRESULT SetAtomicSelection(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Значение true, если любой элемент, имеющий атрибут ATOMICSELECTION задано значение TRUE, могут быть выделены только как единое целое.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_ATOMICSELECTION](https://msdn.microsoft.com/library/aa769892.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetautourldetectmodea--chtmleditctrlbasesetautourldetectmode"></a><a name="setautourldetectmode"></a>CHtmlEditCtrlBase::SetAutoURLDetectMode  
 Включение автоматического обнаружения URL-адрес и отключение.  
  
```  
HRESULT SetAutoURLDetectMode(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Значение true, если включено автоматическое обнаружение URL-адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_AUTOURLDETECT_MODE](https://msdn.microsoft.com/library/aa769893.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetbackcolora--chtmleditctrlbasesetbackcolor"></a><a name="setbackcolor"></a>CHtmlEditCtrlBase::SetBackColor  
 Задает цвет фона текущего выделенного фрагмента.  
  
```  
HRESULT SetBackColor(int nColor) const;  
HRESULT SetBackColor(LPCTSTR szColor) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nColor`  
 Цвет. В разделе `pvaIn` в [идентификатор команды IDM_BACKCOLOR](https://msdn.microsoft.com/library/aa769858.aspx).  
  
 `szColor`  
 Цвет. В разделе `pvaIn` в [идентификатор команды IDM_BACKCOLOR](https://msdn.microsoft.com/library/aa769858.aspx).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_BACKCOLOR_](https://msdn.microsoft.com/library/aa769858.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetblockformata--chtmleditctrlbasesetblockformat"></a><a name="setblockformat"></a>CHtmlEditCtrlBase::SetBlockFormat  
 Задает текущий тег формат блока.  
  
```  
HRESULT SetBlockFormat(LPCTSTR szFormat) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szFormat`  
 Тег форматирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM_BLOCKFMT_command идентификатор](https://msdn.microsoft.com/library/aa769883.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetbookmarka--chtmleditctrlbasesetbookmark"></a><a name="setbookmark"></a>CHtmlEditCtrlBase::SetBookMark  
 Создает привязку закладки для текущего выделения или места вставки.  
  
```  
HRESULT SetBookMark(LPCTSTR szAnchorName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *szAnchorName*  
 Имя привязки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_BOOKMARK](https://msdn.microsoft.com/library/aa769873.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetcsseditinglevela--chtmleditctrlbasesetcsseditinglevel"></a><a name="setcsseditinglevel"></a>CHtmlEditCtrlBase::SetCSSEditingLevel  
 Выбирает уровень CSS (CSS1 или CSS2) Редактор будет поддерживать, если таковые имеются.  
  
```  
HRESULT SetCSSEditingLevel(short nLevel) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nLevel`  
 Уровень CSS. Передайте 0, если не требуется поддержка CSS.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_CSSEDITING_LEVEL](https://msdn.microsoft.com/library/aa769903.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetdefaultcomposesettingsa--chtmleditctrlbasesetdefaultcomposesettings"></a><a name="setdefaultcomposesettings"></a>CHtmlEditCtrlBase::SetDefaultComposeSettings  
 Вызов этого метода по умолчанию параметров создания.  
  
```  
HRESULT SetDefaultComposeSettings(
    LPCSTR szFontName = NULL,  
    unsigned short nFontSize = 3,  
    COLORREF crFontColor = 0xFF000000,  
    COLORREF crFontBgColor = 0xFF000000,  
    bool bBold = false,  
    bool bItalic = false,  
    bool bUnderline = false) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *szFontName*  
 Имя шрифта.  
  
 *nFontSize*  
 Размер шрифта.  
  
 *crFontColor*  
 Цвет шрифта.  
  
 *crFontBgColor*  
 Фоновый цвет шрифта.  
  
 *bBold*  
 Передайте значение true для полужирным шрифтом.  
  
 `bItalic`  
 Передайте значение true для курсивом.  
  
 `bUnderline`  
 Передайте значение true для подчеркнутый текст.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM_COMPOSESETTINGS ИД команды](https://msdn.microsoft.com/library/aa769901.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetdesignmodea--chtmleditctrlbasesetdesignmode"></a><a name="setdesignmode"></a>CHtmlEditCtrlBase::SetDesignMode  
 Режим конструктора.  
  
```  
BOOL SetDesignMode(BOOL bMode) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bMode`  
 Если значение равно true, включает режим конструктора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
##  <a name="a-namesetdisableeditfocusuia--chtmleditctrlbasesetdisableeditfocusui"></a><a name="setdisableeditfocusui"></a>CHtmlEditCtrlBase::SetDisableEditFocusUI  
 Отключает штриховой границей и обрабатывает вокруг элемента с фокусом редактирования.  
  
```  
HRESULT SetDisableEditFocusUI(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Значение true, если отключить штриховой границей и дескрипторы для выбора элемента узла после элемента «изменить фокус» в режиме конструктора. то есть, когда текст или содержимое элемента можно изменить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM_DISABLE_EDITFOCUS_UI](https://msdn.microsoft.com/library/aa769905.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetdocumenthtmla--chtmleditctrlbasesetdocumenthtml"></a><a name="setdocumenthtml"></a>CHtmlEditCtrlBase::SetDocumentHTML  
 Задает HTML-код текущего документа.  
  
```  
HRESULT SetDocumentHTML(LPCTSTR szHTML) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szHTML`  
 HTML-код.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namesetfontfacea--chtmleditctrlbasesetfontface"></a><a name="setfontface"></a>CHtmlEditCtrlBase::SetFontFace  
 Задает шрифт для выделенного фрагмента.  
  
```  
HRESULT SetFontFace(LPCTSTR szFace) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szFace`  
 Имя шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды FONTNAME IDM](https://msdn.microsoft.com/library/aa769880.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetfontsizea--chtmleditctrlbasesetfontsize"></a><a name="setfontsize"></a>CHtmlEditCtrlBase::SetFontSize  
 Задает размер шрифта для выделенного фрагмента.  
  
```  
HRESULT SetFontSize(unsigned short size) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Размер шрифта HTML (1-7). Значение 0 устанавливает размер шрифта значение 1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM FONTSIZE](https://msdn.microsoft.com/library/aa769881.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetforecolora--chtmleditctrlbasesetforecolor"></a><a name="setforecolor"></a>CHtmlEditCtrlBase::SetForeColor  
 Задает цвет переднего плана (текст) текущего выделенного фрагмента.  
  
```  
HRESULT SetForeColor(LPCTSTR szColor) const;  
HRESULT SetForeColor(int nColor) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szColor`  
 Цвет.  
  
 `nColor`  
 Цвет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM FORECOLOR](https://msdn.microsoft.com/library/aa769882.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetie5pastemodea--chtmleditctrlbasesetie5pastemode"></a><a name="setie5pastemode"></a>CHtmlEditCtrlBase::SetIE5PasteMode  
 Задает операции вставки для совместимости с Microsoft Internet Explorer 5.  
  
```  
HRESULT SetIE5PasteMode(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Значение true, если все операции вставки совместимы с Internet Explorer 5; Если значение равно false, операции вставки, совместимы с Internet Explorer 5.5.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM IE50_PASTE_MODE идентификатор команды](https://msdn.microsoft.com/library/aa769923.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetliveresizea--chtmleditctrlbasesetliveresize"></a><a name="setliveresize"></a>CHtmlEditCtrlBase::SetLiveResize  
 В результате WebBrowser для обновления внешнего вида элемента постоянно во время операции изменения размера или перемещения, а не обновление только по завершении перемещения или изменения размера.  
  
```  
HRESULT SetLiveResize(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, приводит к WebBrowser обновить вид элемента постоянно во время операции изменения размера или перемещения; Если значение равно false, он обновляет только по завершении перемещения или изменения размера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM LIVERESIZE идентификатор команды](https://msdn.microsoft.com/library/aa769928.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetmultiselecta--chtmleditctrlbasesetmultiselect"></a><a name="setmultiselect"></a>CHtmlEditCtrlBase::SetMultiSelect  
 Обеспечивает выбор нескольких элементов.  
  
```  
HRESULT SetMultiSelect(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, позволяет выбирать более одного элемента для выбора узла во время, когда пользователь удерживает нажатую клавишу SHIFT или CTRL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM MULTIPLESELECTION идентификатор команды](https://msdn.microsoft.com/library/aa769929.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetoverridecursora--chtmleditctrlbasesetoverridecursor"></a><a name="setoverridecursor"></a>CHtmlEditCtrlBase::SetOverrideCursor  
 Команды WebBrowser никогда не следует изменять указатель мыши.  
  
```  
HRESULT SetOverrideCursor(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Значение true, если браузер не изменит указатель мыши.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM OVERRIDE_CURSOR идентификатор команды](https://msdn.microsoft.com/library/aa769932.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetoverwritemodea--chtmleditctrlbasesetoverwritemode"></a><a name="setoverwritemode"></a>CHtmlEditCtrlBase::SetOverwriteMode  
 Режим ввода текста между переключатели вставки и перезаписать.  
  
```  
HRESULT SetOverwriteMode(bool bMode) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bMode`  
 Если значение равно true, режим ввода текста перезаписать; Если значение равно false, режим ввода текста — insert.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [ПЕРЕЗАПИСАТЬ IDM идентификатор команды](https://msdn.microsoft.com/library/aa770016.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetrespectvisindesigna--chtmleditctrlbasesetrespectvisindesign"></a><a name="setrespectvisindesign"></a>CHtmlEditCtrlBase::SetRespectVisInDesign  
 Скрывает невидимых элементов в режиме конструктора.  
  
```  
HRESULT SetRespectVisInDesign(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Значение true, если все элементы, которые содержат значение «скрытый» или отобразить свойство имеет значение «none» не будет отображаться в режим конструктора и режим просмотра. Если значение равно false, эти элементы должны отображаться только в режиме просмотра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM RESPECTVISIBILITY_INDESIGN идентификатор команды](https://msdn.microsoft.com/library/aa770023.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetshowalignedsitetagsa--chtmleditctrlbasesetshowalignedsitetags"></a><a name="setshowalignedsitetags"></a>CHtmlEditCtrlBase::SetShowAlignedSiteTags  
 Отображает глиф для всех элементов, имеющих **styleFloat** свойство.  
  
```  
HRESULT SetShowAlignedSiteTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, отображает глиф для всех элементов, имеющих **styleFloat** свойство.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM SHOWALIGNEDSITETAGS идентификатор команды](https://msdn.microsoft.com/library/aa769947.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetshowalltagsa--chtmleditctrlbasesetshowalltags"></a><a name="setshowalltags"></a>CHtmlEditCtrlBase::SetShowAllTags  
 Отображает глифы для отображения положения всех тегов в документе.  
  
```  
HRESULT SetShowAllTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, отображает глифы для отображения положения всех тегов в документе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM SHOWALLTAGS идентификатор команды](https://msdn.microsoft.com/library/aa769948.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetshowareatagsa--chtmleditctrlbasesetshowareatags"></a><a name="setshowareatags"></a>CHtmlEditCtrlBase::SetShowAreaTags  
 Отображает глиф для всех тегов области.  
  
```  
HRESULT SetShowAreaTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, отображает глиф для всех тегов области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM SHOWAREATAGS идентификатор команды](https://msdn.microsoft.com/library/aa769949.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetshowbrtagsa--chtmleditctrlbasesetshowbrtags"></a><a name="setshowbrtags"></a>CHtmlEditCtrlBase::SetShowBRTags  
 Отображает глиф для всех тегов br.  
  
```  
HRESULT SetShowBRTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, отображает глиф для всех тегов br.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM SHOWWBRTAGS идентификатор команды](https://msdn.microsoft.com/library/aa769956.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetshowcommenttagsa--chtmleditctrlbasesetshowcommenttags"></a><a name="setshowcommenttags"></a>CHtmlEditCtrlBase::SetShowCommentTags  
 Отображает глиф для всех тегов комментария.  
  
```  
HRESULT SetShowCommentTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, отображает глиф для всех тегов комментария.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM SHOWCOMMENTTAGS идентификатор команды](https://msdn.microsoft.com/library/aa769950.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetshowmisctagsa--chtmleditctrlbasesetshowmisctags"></a><a name="setshowmisctags"></a>CHtmlEditCtrlBase::SetShowMiscTags  
 Отображает все теги, которые показаны в Microsoft Internet Explorer 4.0.  
  
```  
HRESULT SetShowMiscTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, отображаются все теги, показано в Microsoft Internet Explorer 4.0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM SHOWMISCTAGS идентификатор команды](https://msdn.microsoft.com/library/aa769952.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetshowscripttagsa--chtmleditctrlbasesetshowscripttags"></a><a name="setshowscripttags"></a>CHtmlEditCtrlBase::SetShowScriptTags  
 Отображает глиф для всех тегов сценария.  
  
```  
HRESULT SetShowScriptTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, отображает глиф для всех тегов сценария.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM SHOWSCRIPTTAGS идентификатор команды](https://msdn.microsoft.com/library/aa769953.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetshowstyletagsa--chtmleditctrlbasesetshowstyletags"></a><a name="setshowstyletags"></a>CHtmlEditCtrlBase::SetShowStyleTags  
 Отображает глиф для всех тегов стиля.  
  
```  
HRESULT SetShowStyleTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, отображает глиф для всех тегов стиля.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM SHOWSTYLETAGS идентификатор команды](https://msdn.microsoft.com/library/aa769954.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-namesetshowunknowntagsa--chtmleditctrlbasesetshowunknowntags"></a><a name="setshowunknowntags"></a>CHtmlEditCtrlBase::SetShowUnknownTags  
 Отображает глиф для всех неизвестных тегов.  
  
```  
HRESULT SetShowUnknownTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение равно true, отображает глиф для всех неизвестных тегов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM SHOWUNKNOWNTAGS идентификатор команды](https://msdn.microsoft.com/library/aa769955.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nametextareaa--chtmleditctrlbasetextarea"></a><a name="textarea"></a>CHtmlEditCtrlBase::TextArea  
 Перезаписывает многострочный управления для ввода текста для выделенного фрагмента.  
  
```  
HRESULT TextArea(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор элемента управления вводом многострочный текст.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM TEXTAREA](https://msdn.microsoft.com/library/aa769986.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nametextboxa--chtmleditctrlbasetextbox"></a><a name="textbox"></a>CHtmlEditCtrlBase::TextBox  
 Перезаписывает текстового элемента управления для выделенного фрагмента.  
  
```  
HRESULT TextBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор текстового элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [идентификатор команды IDM TEXTBOX](https://msdn.microsoft.com/library/aa769980.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameunbookmarka--chtmleditctrlbaseunbookmark"></a><a name="unbookmark"></a>CHtmlEditCtrlBase::UnBookmark  
 Удаляет все закладки из текущего выделенного фрагмента.  
  
```  
HRESULT UnBookmark() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM UNBOOKMARK идентификатор команды](https://msdn.microsoft.com/library/aa770034.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameunderlinea--chtmleditctrlbaseunderline"></a><a name="underline"></a>CHtmlEditCtrlBase::Underline  
 Переключение между подчеркнут и не подчеркнуто текущее выделение.  
  
```  
HRESULT Underline() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [ПОДЧЕРКИВАНИЕ IDM идентификатор команды](https://msdn.microsoft.com/library/aa770035.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameunlinka--chtmleditctrlbaseunlink"></a><a name="unlink"></a>CHtmlEditCtrlBase::Unlink  
 Удаляет все гиперссылки из текущего выделенного фрагмента.  
  
```  
HRESULT Unlink() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [удалить связь группы IDM идентификатор команды](https://msdn.microsoft.com/library/aa770037.aspx) для элемента управления WebBrowser.  
  
##  <a name="a-nameunorderlista--chtmleditctrlbaseunorderlist"></a><a name="unorderlist"></a>CHtmlEditCtrlBase::UnorderList  
 Переключает текущий выбор между упорядоченный список и обычное форматирование блока.  
  
```  
HRESULT UnorderList(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 Идентификатор неупорядоченного списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [IDM UNORDERLIST идентификатор команды](https://msdn.microsoft.com/library/aa769987.aspx) для элемента управления WebBrowser.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Образец HTMLEdit](../../visual-cpp-samples.md)


