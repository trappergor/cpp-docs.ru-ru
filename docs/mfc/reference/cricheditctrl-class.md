---
title: "CRichEditCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditCtrl
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class, common controls
- CRichEditCtrl class
- formatted text [C++]
ms.assetid: 2be52788-822c-4c27-aafd-2471231e74eb
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
ms.openlocfilehash: 77b8dfb6011831f4e4300096a127f70b26bcc603
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditctrl-class"></a>CRichEditCtrl-класс
Предоставляет функции элемента управления форматированным редактированием.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRichEditCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditCtrl::CRichEditCtrl](#cricheditctrl)|Создает объект `CRichEditCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditCtrl::CanPaste](#canpaste)|Определяет, если содержимое буфера обмена может быть вставлено в этом управления rich edit.|  
|[CRichEditCtrl::CanRedo](#canredo)|Определяет, существуют ли все действия в очереди повторного выполнения элемента управления.|  
|[CRichEditCtrl::CanUndo](#canundo)|Определяет, может ли отменить операцию редактирования.|  
|[CRichEditCtrl::CharFromPos](#charfrompos)|Извлекает сведения о символе, ближайший к заданной точке клиентской области элемента управления.|  
|[CRichEditCtrl::Clear](#clear)|Отменяет текущее выделение.|  
|[CRichEditCtrl::Copy](#copy)|Копирует текущее выделение в буфер обмена.|  
|[CRichEditCtrl::Create](#create)|В текстовом режиме Windows создает и связывает его с этим `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::CreateEx](#createex)|Создает управления rich edit Windows с указанным расширенные стили Windows и связывает его с этим `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::Cut](#cut)|Удаление выбранного в буфер обмена.|  
|[CRichEditCtrl::DisplayBand](#displayband)|Отображает часть содержимого данного `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::EmptyUndoBuffer](#emptyundobuffer)|Сбрасывает (очистка) флаг отмены этого `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::FindText](#findtext)|Поиск текста в рамках этого `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::FindWordBreak](#findwordbreak)|Поиск следующего слова разрыва до или после указанной позиции символа или извлекает сведения о знак в этой позиции.|  
|[CRichEditCtrl::FormatRange](#formatrange)|Форматирует диапазон текста для целевого устройства вывода.|  
|[CRichEditCtrl::GetCharPos](#getcharpos)|Определяет расположение определенный символ в рамках этого `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetDefaultCharFormat](#getdefaultcharformat)|Получает текущий символ по умолчанию форматирование атрибутов в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetEventMask](#geteventmask)|Извлекает маску события для данного `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetFirstVisibleLine](#getfirstvisibleline)|Определяет верхний видимой строки в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetIRichEditOle](#getiricheditole)|Извлекает указатель на `IRichEditOle` интерфейс для управления этот rich edit.|  
|[CRichEditCtrl::GetLimitText](#getlimittext)|Возвращает ограничение на объем текста, пользователь может ввести в это `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetLine](#getline)|Извлекает строки текста из этого `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetLineCount](#getlinecount)|Возвращает количество строк в данном `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetModify](#getmodify)|Определяет, если содержимое данного `CRichEditCtrl` объекта были изменены с момента последнего сохранения.|  
|[CRichEditCtrl::GetOptions](#getoptions)|Извлекает параметры управления форматированным редактированием.|  
|[CRichEditCtrl::GetParaFormat](#getparaformat)|Извлекает атрибуты в текущее выделение в этом форматирования абзаца `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetPunctuation](#getpunctuation)|Получает текущий знаки пунктуации для управления rich edit. Это сообщение является доступны только в азиатских языках версий операционной системы.|  
|[CRichEditCtrl::GetRect](#getrect)|Возвращает прямоугольник, форматирования для данного `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetRedoName](#getredoname)|Получает тип следующего действия, если есть, в элементе управления очередь повтора.|  
|[CRichEditCtrl::GetSel](#getsel)|Возвращает начальную и конечную позиции текущего выделенного фрагмента в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetSelectionCharFormat](#getselectioncharformat)|Возвращает символ форматирования атрибутов в текущее выделение в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetSelectionType](#getselectiontype)|Получает тип содержимого в текущее выделение в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::GetSelText](#getseltext)|Возвращает текст текущего выделенного фрагмента в этом `CRichEditCtrl` объекта|  
|[CRichEditCtrl::GetTextLength](#gettextlength)|Получает длину текста в знаках в этом `CRichEditCtrl` объекта. Отсутствует завершающий символ null.|  
|[CRichEditCtrl::GetTextLengthEx](#gettextlengthex)|Возвращает число символов или байтов в представлении форматируемого. Принимает список флаги, которые определяют способ определения длины текста в элементе управления rich edit|  
|[CRichEditCtrl::GetTextMode](#gettextmode)|Возвращает текущий текстовый режим и отмены уровень управления rich edit.|  
|[CRichEditCtrl::GetTextRange](#gettextrange)|Извлекает указанный фрагмент текста.|  
|[CRichEditCtrl::GetUndoName](#getundoname)|Получает тип Далее отменить действие, если таковые имеются.|  
|[CRichEditCtrl::GetWordWrapMode](#getwordwrapmode)|Получает текущий перенос слов и параметров разбиения на слова для управления rich edit. Это сообщение является доступны только в азиатских языках версий операционной системы.|  
|[CRichEditCtrl::HideSelection](#hideselection)|Показывает или скрывает текущее выделение.|  
|[CRichEditCtrl::LimitText](#limittext)|Ограничивает объем текста, пользователь может ввести в `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::LineFromChar](#linefromchar)|Определяет, какая строка содержит определенный символ.|  
|[CRichEditCtrl::LineIndex](#lineindex)|Получает индекс данной строки в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::LineLength](#linelength)|Получает длину заданной строки в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::LineScroll](#linescroll)|Прокрутка текста в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::Paste](#paste)|Вставляет содержимое буфера обмена в этом управления rich edit.|  
|[CRichEditCtrl::PasteSpecial](#pastespecial)|Вставляет содержимое буфера обмена в этом управления "rich edit" в указанном формате.|  
|[CRichEditCtrl::PosFromChar](#posfromchar)|Возвращает координаты области клиента указанного символа в элемент управления редактированием.|  
|[CRichEditCtrl::Redo](#redo)|Повтор следующего действия в очереди повторного выполнения элемента управления.|  
|[CRichEditCtrl::ReplaceSel](#replacesel)|Заменяет текущее выделение в этом `CRichEditCtrl` объекта с заданным текстом.|  
|[CRichEditCtrl::RequestResize](#requestresize)|Это заставляет `CRichEditCtrl` объекта для отправки уведомлений запроса изменения размера.|  
|[CRichEditCtrl::SetAutoURLDetect](#setautourldetect)|Указывает, активен ли автоматическое обнаружение URL-адреса в элементе управления rich edit.|  
|[CRichEditCtrl::SetBackgroundColor](#setbackgroundcolor)|Задает цвет фона в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetDefaultCharFormat](#setdefaultcharformat)|Задает текущий символ по умолчанию форматирование атрибутов в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetEventMask](#seteventmask)|Задает маску события для этого `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetModify](#setmodify)|Устанавливает или снимает флаг изменения для этого `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetOLECallback](#setolecallback)|Наборы `IRichEditOleCallback` COM-объект для этого элемента управления форматированным редактированием.|  
|[CRichEditCtrl::SetOptions](#setoptions)|Задает параметры для этого `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetParaFormat](#setparaformat)|Задает атрибуты в текущее выделение в этом форматирования абзаца `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetPunctuation](#setpunctuation)|Задает символы пунктуации для элемента управления rich edit. Это сообщение является доступны только в азиатских языках версий операционной системы.|  
|[CRichEditCtrl::SetReadOnly](#setreadonly)|Задает параметр только для чтения для этого `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetRect](#setrect)|Задает для этого прямоугольника форматирования `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetSel](#setsel)|Задает выбор в данном `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetSelectionCharFormat](#setselectioncharformat)|Задает символ, форматирование атрибутов в текущее выделение в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetTargetDevice](#settargetdevice)|Задает для данного целевого устройства вывода `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetTextMode](#settextmode)|Задает уровень режиме или отмены текстового элемента управления rich edit. Сообщение не проходит, если элемент управления содержит текст.|  
|[CRichEditCtrl::SetUndoLimit](#setundolimit)|Задает максимальное число действий, которые могут храниться в очереди отмены.|  
|[CRichEditCtrl::SetWordCharFormat](#setwordcharformat)|Задает символ, форматирование атрибуты текущего слова в этом `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::SetWordWrapMode](#setwordwrapmode)|Установка параметров переноса слов и разбиение по словам для сложных поля ввода. Это сообщение является доступны только в азиатских языках версий операционной системы.|  
|[CRichEditCtrl::StopGroupTyping](#stopgrouptyping)|Остановка управления сбор дополнительных ввода в действие отмены текущего действия. Элемент управления сохраняет следующего действия ввода, если таковая имеется, в новое действие в очереди отмены.|  
|[CRichEditCtrl::StreamIn](#streamin)|Вставляет текст из входного потока в эту `CRichEditCtrl` объекта.|  
|[CRichEditCtrl::StreamOut](#streamout)|Сохраняет текст из этого `CRichEditCtrl` объект в поток вывода.|  
|[CRichEditCtrl::Undo](#undo)|Отменяет последнюю операцию редактирования.|  
  
## <a name="remarks"></a>Примечания  
 «Управления rich edit» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматирование знаков и абзацев и может включать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.  
  
 Это Windows стандартного элемента управления (и, следовательно, `CRichEditCtrl` класса) доступны только для программы под управлением версий Windows 95/98 и Windows NT 3.51 и более поздних версий. `CRichEditCtrl` Класс поддерживает версии 2.0 и 3.0 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] элемент управления rich edit.  
  
> [!CAUTION]
>  При использовании элемента управления rich edit в диалоговом окне (независимо от того, является ли приложение SDI MDI, или на базе диалогового окна), необходимо вызвать [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit) после перед диалогового окна отображается окно. Типичный вызов этой функции находится в вашей программе `InitInstance` функции-члена. Необходимо вызывать при каждом диалоговом окне отображаются только в первый раз. Необходимо вызвать `AfxInitRichEdit` при работе с `CRichEditView`.  
  
 Дополнительные сведения об использовании `CRichEditCtrl`, см.:  
  
- [Элементы управления](../../mfc/controls-mfc.md)  
  
- [Использование CRichEditCtrl](../../mfc/using-cricheditctrl.md)  
  
-   Статья базы знаний Q259949: INFO: SetCaretPos() — не соответствующие CEdit или элементы управления CRichEditCtrl  
  
 Пример использования элемента управления rich edit в приложении MFC, в разделе [WORDPAD](../../visual-cpp-samples.md) образец приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CRichEditCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-namecanpastea--cricheditctrlcanpaste"></a><a name="canpaste"></a>CRichEditCtrl::CanPaste  
 Определяет, если элемент управления форматированием можно вставить указанный формат буфера обмена.  
  
```  
BOOL CanPaste(UINT nFormat = 0) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nFormat`  
 Формат данных буфера обмена для запроса. Этот параметр может принимать одно из предопределенных форматы буфера обмена, или значение, возвращаемое [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если формат буфера обмена, можно вставить; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `nFormat` равно 0, `CanPaste` попытается любого формата в данный момент в буфере обмена.  
  
 Дополнительные сведения см. в разделе [EM_CANPASTE](http://msdn.microsoft.com/library/windows/desktop/bb787993) сообщений и [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#1;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_1.cpp)]  
  
##  <a name="a-namecanredoa--cricheditctrlcanredo"></a><a name="canredo"></a>CRichEditCtrl::CanRedo  
 Определяет, содержит ли очереди повторного выполнения каких-либо действий.  
  
```  
BOOL CanRedo() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в очереди повторного выполнения имеются действия, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Чтобы получить имя операции в очереди повторов, вызовите [CRichEditCtrl::GetRedoName](#getredoname). Для повтора последней операции отмены, вызовите [вернуть](#redo).  
  
 Дополнительные сведения см. в разделе [EM_CANREDO](http://msdn.microsoft.com/library/windows/desktop/bb787995) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecanundoa--cricheditctrlcanundo"></a><a name="canundo"></a>CRichEditCtrl::CanUndo  
 Определяет, может ли отменить последнюю операцию редактирования.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если последнюю операцию редактирования могут быть отменены путем вызова [отменить](#undo) функция-член; 0, если он не может быть отменено.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#2;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_2.cpp)]  
  
##  <a name="a-namecharfromposa--cricheditctrlcharfrompos"></a><a name="charfrompos"></a>CRichEditCtrl::CharFromPos  
 Извлекает сведения о символа в позиции, заданным в параметре `pt`.  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объект, содержащий координаты указанной точки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс символа, ближайшего заданной точке. Если заданная точка за последним символом в элементе управления, возвращаемое значение указывает последний символ в элементе управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член работает с элемента управления rich edit. Чтобы получить сведения для элемента управления, вызовите [CEdit::CharFromPos](../../mfc/reference/cedit-class.md#charfrompos).  
  
 Дополнительные сведения см. в разделе [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecleara--cricheditctrlclear"></a><a name="clear"></a>CRichEditCtrl::Clear  
 (Очистка) удаляет текущее выделение (если таковые имеются) в богатую возможностями редактирования.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Удаления, выполняемые **снимите** можно отменить, вызвав [отменить](#undo) функции-члена.  
  
 Чтобы удалить текущий выделенный фрагмент и поместить удаленные содержимое в буфер обмена, вызовите [Вырезать](#cut) функции-члена.  
  
 Дополнительные сведения см. в разделе [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#3;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_3.cpp)]  
  
##  <a name="a-namecopya--cricheditctrlcopy"></a><a name="copy"></a>CRichEditCtrl::Copy  
 Копирует текущее выделение (если таковые имеются) в элементе управления форматированным редактированием в буфер обмена.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#4;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_4.cpp)]  
  
##  <a name="a-namecreatea--cricheditctrlcreate"></a><a name="create"></a>CRichEditCtrl::Create  
 В текстовом режиме Windows создает и связывает его с этим `CRichEditCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления поля ввода. Применить сочетание стилей окна, перечисленных в **примечания** ниже, и [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464), описанный в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Задает размер и положение элемента управления поля ввода. Может быть [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
 `pParentWnd`  
 Указывает родительского окна элемента управления поля ввода (часто [CDialog](../../mfc/reference/cdialog-class.md)). Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления поля ввода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CRichEditCtrl` объекта в два этапа. Во-первых, вызовите [CRichEditCtrl](#cricheditctrl) конструктора, затем вызовите **создать**, который создает управления редактированием Windows и присоединяет его к `CRichEditCtrl` объекта.  
  
 При создании элемента управления rich edit с этой функцией, сначала необходимо загрузить необходимые библиотеки общих элементов управления. Чтобы загрузить библиотеку, вызовите глобальную функцию [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit), который в свою очередь инициализирует библиотеки общих элементов управления. Необходимо вызвать `AfxInitRichEdit` только один раз в процессе.  
  
 Когда **создать** выполняет Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщений для элемента управления поля ввода.  
  
 Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CRichEditCtrl`, добавить схему сообщения в новый класс и переопределить выше функции-члены обработчик сообщений. Переопределение `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Примените следующий [стили окна](../../mfc/reference/window-styles.md) для элемента управления.  
  
- **WS_CHILD** всегда.  
  
- **WS_VISIBLE** обычно.  
  
- **WS_DISABLED** редко.  
  
- **WS_GROUP** для группирования элементов управления.  
  
- **WS_TABSTOP** для включения управления редактированием в порядок следования.  
  
 Дополнительные сведения о стилях окна в разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#5;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_5.cpp)]  
  
##  <a name="a-namecreateexa--cricheditctrlcreateex"></a><a name="createex"></a>CRichEditCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связывает его с `CRichEditCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Задает стиль элемента управления поля ввода. Применить сочетание стилей окна, перечисленных в **примечания** раздел [создать](#create) и [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464), описанный в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо **создать** для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
##  <a name="a-namecricheditctrla--cricheditctrlcricheditctrl"></a><a name="cricheditctrl"></a>CRichEditCtrl::CRichEditCtrl  
 Создает объект `CRichEditCtrl`.  
  
```  
CRichEditCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [создать](#create) для создания окна элемент управления rich edit.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl №&6;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_6.cpp)]  
  
##  <a name="a-namecuta--cricheditctrlcut"></a><a name="cut"></a>CRichEditCtrl::Cut  
 Удаление (сокращает) текущее выделение (если таковые имеются) в широкий набор функций управления edit и копирует удаленный текст в буфер обмена.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Примечания  
 Удаления, выполняемые **Вырезать** можно отменить, вызвав [отменить](#undo) функции-члена.  
  
 Чтобы удалить текущее выделение без помещения удаленный текст в буфер обмена, вызовите [снимите](#clear) функции-члена.  
  
 Дополнительные сведения см. в разделе [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#7;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_7.cpp)]  
  
##  <a name="a-namedisplaybanda--cricheditctrldisplayband"></a><a name="displayband"></a>CRichEditCtrl::DisplayBand  
 Отображает часть содержимого элемента управления "rich edit" (текст и элементы OLE), отформатированные в соответствии с ранее [FormatRange](#formatrange).  
  
```  
BOOL DisplayBand(LPRECT pDisplayRect);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisplayRect`  
 Указатель на [RECT](../../mfc/reference/rect-structure1.md) или [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, задающий область устройства для отображения текста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если отображение форматированного текста выполняется успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Текст и OLE-элементы будут обрезаны по области, определяемой заданным указателем `pDisplayRect`.  
  
 Дополнительные сведения см. в разделе [EM_DISPLAYBAND](http://msdn.microsoft.com/library/windows/desktop/bb787997) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditCtrl::FormatRange](#formatrange).  
  
##  <a name="a-nameemptyundobuffera--cricheditctrlemptyundobuffer"></a><a name="emptyundobuffer"></a>CRichEditCtrl::EmptyUndoBuffer  
 Сбрасывает флаг отмены этого управления rich edit (clear).  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Примечания  
 Элемент управления будет невозможно отменить последнюю операцию редактирования. Флаг отмены всякий раз, когда операции в рамках управления rich edit, можно отменить.  
  
 Флаг отмены автоматически очищается при каждом вызове [CWnd](../../mfc/reference/cwnd-class.md) функции-члена [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
 Дополнительные сведения см. в разделе [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl №&8;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_8.cpp)]  
  
##  <a name="a-namefindtexta--cricheditctrlfindtext"></a><a name="findtext"></a>CRichEditCtrl::FindText  
 Поиск текста в элементе управления форматированным редактированием.  
  
```  
long FindText(
    DWORD dwFlags,  
    FINDTEXTEX* pFindText) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Список возможных значений см. в разделе `wParam` в [EM_FINDTEXTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788011) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *pFindText*  
 Указатель на [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) структуры, что для поиска и возвращения диапазон, где было найдено соответствие.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля позиция следующее совпадение; – 1, если больше нет совпадений.  
  
### <a name="remarks"></a>Примечания  
 Можно выполнить поиск либо вверх или вниз, Настройка параметров необходимом диапазоне в [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) структуры в **FINDTEXTEX** структуры.  
  
 Дополнительные сведения см. в разделе [EM_FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb788011) сообщений и [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl №&9;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_9.cpp)]  
  
##  <a name="a-namefindwordbreaka--cricheditctrlfindwordbreak"></a><a name="findwordbreak"></a>CRichEditCtrl::FindWordBreak  
 Поиск следующего слова разрыва до или после позиции, указанной параметром `nStart`.  
  
```  
DWORD FindWordBreak(
    UINT nCode,  
    DWORD nStart) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nCode`  
 Указывает действие, предпринимаемое. Список возможных значений, см. в описании параметра `code` в **EM_FINDWORDBREAK** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nStart`  
 Отсчитываемый от нуля позиция, с которого следует начать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 На основе параметра `nCode`. Дополнительные сведения см. в разделе [EM_FINDWORDBREAK](http://msdn.microsoft.com/library/windows/desktop/bb788018) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член можно использовать для получения сведений о символа в заданной позиции.  
  
##  <a name="a-nameformatrangea--cricheditctrlformatrange"></a><a name="formatrange"></a>CRichEditCtrl::FormatRange  
 Форматирует диапазон текста в элементе управления "rich edit" для конкретного устройства.  
  
```  
long FormatRange(
    FORMATRANGE* pfr,  
    BOOL bDisplay = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *PFR*  
 Указатель на [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) структуры, который содержит информацию об устройстве вывода. **NULL** указывает, может быть освобожден кэшированные данные в элементе управления форматированным редактированием.  
  
 *bDisplay*  
 Указывает, если текст должен отображаться. Если **FALSE**, просто измеряется текст.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс последнего символа, который помещается в области, плюс один.  
  
### <a name="remarks"></a>Примечания  
 Как правило, этот вызов сопровождается вызов [DisplayBand](#displayband).  
  
 Дополнительные сведения см. в разделе [EM_FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb788020) сообщений и [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#10;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_10.cpp)]  
  
##  <a name="a-namegetcharposa--cricheditctrlgetcharpos"></a><a name="getcharpos"></a>CRichEditCtrl::GetCharPos  
 Возвращает позицию (верхний левый угол) определенный символ в рамках этого `CRichEditCtrl` объекта.  
  
```  
CPoint GetCharPos(long lChar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lChar`  
 Отсчитываемый от нуля индекс символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расположение верхнего левого угла символ `lChar`.  
  
### <a name="remarks"></a>Примечания  
 Символ, указанный, предоставив его с нуля значение. Если `lChar` больше индекса последнего символа в этом `CRichEditCtrl` объекта, возвращаемое значение указывает координаты позиции после последнего символа в этом `CRichEditCtrl` объекта.  
  
 Дополнительные сведения см. в разделе [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdefaultcharformata--cricheditctrlgetdefaultcharformat"></a><a name="getdefaultcharformat"></a>CRichEditCtrl::GetDefaultCharFormat  
 Возвращает символ по умолчанию форматирование атрибуты этого `CRichEditCtrl` объекта.  
  
```  
DWORD GetDefaultCharFormat(CHARFORMAT& cf) const;  DWORD GetDefaultCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a **CHARFORMAT** structure holding the default character formatting attributes.  
  
 In the second version, a pointer to a **CHARFORMAT2** structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure, holding the default character formatting attributes.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specified the default character formatting attributes.  
  
### Remarks  
 For more information, see the **EM_GETCHARFORMAT** message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetDefaultCharFormat](#setdefaultcharformat).  
  
##  <a name="geteventmask"></a>  CRichEditCtrl::GetEventMask  
 Gets the event mask for this `CRichEditCtrl` object.  
  
```  
длинное GetEventMask() константу;  
```  
  
### Return Value  
 The event mask for this `CRichEditCtrl` object.  
  
### Remarks  
 The event mask specifies which notification messages the `CRichEditCtrl` object sends to its parent window.  
  
 For more information, see [EM_GETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb788032) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [CRichEditCtrl::SetEventMask](#seteventmask).  
  
##  <a name="getfirstvisibleline"></a>  CRichEditCtrl::GetFirstVisibleLine  
 Determines the topmost visible line in this `CRichEditCtrl` object.  
  
```  
int GetFirstVisibleLine() константу;  
```  
  
### Return Value  
 Zero-based index of the uppermost visible line in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#11](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_11.cpp)]  
  
##  <a name="getiricheditole"></a>  CRichEditCtrl::GetIRichEditOle  
 Accesses the **IRichEditOle** interface for this `CRichEditCtrl` object.  
  
```  
GetIRichEditOle() IRichEditOle * const;  
```  
  
### Return Value  
 Pointer to the [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface that can be used to access this `CRichEditCtrl` object's OLE functionality; **NULL** if the interface is not accessible.  
  
### Remarks  
 Use this interface to access this `CRichEditCtrl` object's OLE functionality.  
  
 For more information, see [EM_GETOLEINTERFACE](http://msdn.microsoft.com/library/windows/desktop/bb788041) message and [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlimittext"></a>  CRichEditCtrl::GetLimitText  
 Gets the text limit for this `CRichEditCtrl` object.  
  
```  
длинное GetLimitText() константу;  
```  
  
### Return Value  
 The current text limit, in bytes, for this `CRichEditCtrl` object.  
  
### Remarks  
 The text limit is the maximum amount of text, in bytes, the rich edit control can accept.  
  
 For more information, see [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#12](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_12.cpp)]  
  
##  <a name="getline"></a>  CRichEditCtrl::GetLine  
 Retrieves a line of text from this `CRichEditCtrl` object.  
  
```  
GetLine (int nIndex, int  
    LPTSTR lpszBuffer) константу;  
  
GetLine (int nIndex, int  
    LPTSTR lpszBuffer  
    int nMaxLength) константу;  
```  
  
### Parameters  
 `nIndex`  
 Zero-based index of the line to retrieve.  
  
 `lpszBuffer`  
 Points to the buffer to receive the text. The first word of the buffer must specify the maximum number of bytes that can be copied into the buffer.  
  
 `nMaxLength`  
 Maximum number of characters that can be copied into `lpszBuffer`. The second form of `GetLine` places this value into the first word of the buffer specified by `lpszBuffer`.  
  
### Return Value  
 The number of characters copied into `lpszBuffer`.  
  
### Remarks  
 The copied line does not contain a terminating null character.  
  
> [!NOTE]
>  Because the first word of the buffer stores the number of characters to be copied, make sure that your buffer is at least 4 bytes long.  
  
 For more information, see [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>  CRichEditCtrl::GetLineCount  
 Retrieves the number of lines in the `CRichEditCtrl` object.  
  
```  
int GetLineCount() константу;  
```  
  
### Return Value  
 The number of lines in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#13](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_13.cpp)]  
  
##  <a name="getmodify"></a>  CRichEditCtrl::GetModify  
 Determines if the contents of this `CRichEditCtrl` object have been modified.  
  
```  
BOOL GetModify() константу;  
```  
  
### Return Value  
 Nonzero if the text in this `CRichEditCtrl` object has been modified; otherwise 0.  
  
### Remarks  
 Windows maintains an internal flag indicating whether the contents of the rich edit control have been changed. This flag is cleared when the edit control is first created and can also be cleared by calling the [SetModify](#setmodify) member function.  
  
 For more information, see [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#14](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_14.cpp)]  
  
##  <a name="getoptions"></a>  CRichEditCtrl::GetOptions  
 Retrieves the options currently set for the rich edit control.  
  
```  
UINT GetOptions() константу;  
```  
  
### Return Value  
 A combination of the current option flag values. For a list of these values, see the *fOptions* parameter in the [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getparaformat"></a>  CRichEditCtrl::GetParaFormat  
 Gets the paragraph formatting attributes of the current selection.  
  
```  
DWORD GetParaFormat(PARAFORMAT& pf) константу;  DWORD GetParaFormat(PARAFORMAT2& pf) константу;  ```  
  
### <a name="parameters"></a>Параметры  
 `pf`  
 В первой версии указатель [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) структура, содержащая атрибуты текущего выделения форматирования абзаца.  
  
 Во второй версии указатель [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) структуру, которая является расширением 2.0 изменить широкие возможности для **PARAFORMAT** структуры, удерживая атрибутов форматирования символов по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **DwMask** членом данных `pf`. Указывает атрибуты, которые согласованы во всей выделенной форматирования абзаца.  
  
### <a name="remarks"></a>Примечания  
 Если выбрано несколько абзацев, `pf` получает атрибуты первого абзаца. Возвращаемое значение указывает, какие атрибуты несогласованной в выделение.  
  
 Дополнительные сведения см. в разделе [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) сообщений и **PARAFORMAT** и **PARAFORMAT2** структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditCtrl::SetParaFormat](#setparaformat).  
  
##  <a name="a-namegetpunctuationa--cricheditctrlgetpunctuation"></a><a name="getpunctuation"></a>CRichEditCtrl::GetPunctuation  
 Возвращает текущий знаков препинания в элементе управления rich edit.  
  
```  
BOOL GetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `fType`  
 Флаг типа пунктуации, как описано в `fType` параметр [EM_GETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774184) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpPunc`  
 Указатель на [ПУНКТУАЦИИ](http://msdn.microsoft.com/library/windows/desktop/bb787944) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член доступен только в версиях азиатских языков операционной системы.  
  
##  <a name="a-namegetrecta--cricheditctrlgetrect"></a><a name="getrect"></a>CRichEditCtrl::GetRect  
 Возвращает прямоугольник, форматирования для данного `CRichEditCtrl` объекта.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md) или указатель [RECT](../../mfc/reference/rect-structure1.md) для получения прямоугольника форматирования этого `CRichEditCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольника форматирования представляет ограничивающий прямоугольник для текста. Это значение не зависит от размера `CRichEditCtrl` объекта.  
  
 Дополнительные сведения см. в разделе [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [LimitText](#limittext).  
  
##  <a name="a-namegetredonamea--cricheditctrlgetredoname"></a><a name="getredoname"></a>CRichEditCtrl::GetRedoName  
 Получает тип следующего доступного действия в очереди повторов, если таковые имеются.  
  
```  
UNDONAMEID GetRedoName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения `GetRedoName` возвращает [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) тип перечисления, указывающее тип следующего действия в очереди повторного выполнения элемента управления. Пуста ли очередь повтора или неизвестного типа, если действие повтора в очереди `GetRedoName` возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Типы действий, которые можно отменить или повторить включают ввода, удаления, перемещения, вырезания и вставки. Эта информация может быть полезна для приложений, которые предоставляют расширенный пользовательский интерфейс для отмены и повтора операций, таких как окно раскрывающегося списка redoable действий.  
  
##  <a name="a-namegetsela--cricheditctrlgetsel"></a><a name="getsel"></a>CRichEditCtrl::GetSel  
 Возвращает границы текущего выделенного фрагмента в этом `CRichEditCtrl` объекта.  
  
```  
void GetSel(CHARRANGE& cr) const;  
  
void GetSel(
    long& nStartChar,  
    long& nEndChar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `cr`  
 Ссылка на [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) структуру для получения границы текущего выделенного фрагмента.  
  
 `nStartChar`  
 Отсчитываемый от нуля индекс первого символа в выделенном фрагменте.  
  
 `nEndChar`  
 Отсчитываемый от нуля индекс последнего символа в выделенном фрагменте.  
  
### <a name="remarks"></a>Примечания  
 Две формы этой функции предоставляют альтернативные способы получения границы для выбора. Выполните краткое описание каждого из этих форм.  
  
- **GetSel (** `cr` **)** в этой форме используются **CHARRANGE** структура с его **cpMin** и **cpMax** границы возвращаемых элементов.  
  
- **GetSel (** `nStartChar` **,** `nEndChar` **)** Эта форма возвращает границы в параметрах `nStartChar` и `nEndChar`.  
  
 Выделение включает все, что, если начало ( **cpMin** или `nStartChar`) равно 0 и окончания ( **cpMax** или `nEndChar`) равняется – 1.  
  
 Дополнительные сведения см. в разделе [EM_EXGETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788001) сообщений и [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#15;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_15.cpp)]  
  
##  <a name="a-namegetselectioncharformata--cricheditctrlgetselectioncharformat"></a><a name="getselectioncharformat"></a>CRichEditCtrl::GetSelectionCharFormat  
 Возвращает символ форматирования атрибуты текущего выделенного фрагмента.  
  
```  
DWORD GetSelectionCharFormat(CHARFORMAT& cf) const;  DWORD GetSelectionCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) structure to receive the character formatting attributes of the current selection.  
  
 In the second version, a pointer to a [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure to receive the character formatting attributes of the current selection.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specifies the character formatting attributes that are consistent throughout the current selection.  
  
### Remarks  
 The `cf` parameter receives the attributes of the first character in the current selection. The return value specifies which attributes are consistent throughout the selection.  
  
 For more information, see the [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetSelectionCharFormat](#setselectioncharformat).  
  
##  <a name="getselectiontype"></a>  CRichEditCtrl::GetSelectionType  
 Determines the selection type in this `CRichEditCtrl` object.  
  
```  
GetSelectionType() слова const;  
```  
  
### Return Value  
 Flags indicating the contents of the current selection. A combination of the following flags:  
  
- `SEL_EMPTY` Indicates that there is no current selection.  
  
- `SEL_TEXT` Indicates that the current selection contains text.  
  
- `SEL_OBJECT` Indicates that the current selection contains at least one OLE item.  
  
- `SEL_MULTICHAR` Indicates that the current selection contains more than one character of text.  
  
- `SEL_MULTIOBJECT` Indicates that the current selection contains more than one OLE object.  
  
### Remarks  
 For more information, see [EM_SELECTIONTYPE](http://msdn.microsoft.com/library/windows/desktop/bb774223) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#16](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_16.cpp)]  
  
##  <a name="getseltext"></a>  CRichEditCtrl::GetSelText  
 Retrieves the text from the current selection in this `CRichEditCtrl` object.  
  
```  
длинное GetSelText(LPSTR lpBuf) константу;  CString GetSelText() константу;  ```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Указатель на буфер для получения текста в выделенном фрагменте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Зависит от формы:  
  
- **GetSelText (** `lpBuf` **)** число символов, копируются в `lpBuf`, не включая нулем.  
  
- **(GetSelText)** строка, содержащая текущее выделение.  
  
### <a name="remarks"></a>Примечания  
 Если использовать первую форму, **GetSelText (** `lpBuf` **)**, необходимо убедиться, что буфер достаточен для текста, он получит. Вызов [GetSel](#getsel) для определения количества символов в выделенном фрагменте.  
  
 Дополнительные сведения см. в разделе [EM_GETSELTEXT](http://msdn.microsoft.com/library/windows/desktop/bb774190) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditCtrl::GetSelectionType](#getselectiontype).  
  
##  <a name="a-namegettextlengtha--cricheditctrlgettextlength"></a><a name="gettextlength"></a>CRichEditCtrl::GetTextLength  
 Получает длину текста в знаках в этом `CRichEditCtrl` объекта, не включая завершающий символ null.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина текста в этом `CRichEditCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&17;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_17.cpp)]  
  
##  <a name="a-namegettextlengthexa--cricheditctrlgettextlengthex"></a><a name="gettextlengthex"></a>CRichEditCtrl::GetTextLengthEx  
 Вычисляет длину текста в элементе управления форматированным редактированием.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Значение, указывающее метод, используемый для определения длины текста. Этот член может быть один или несколько значений, перечисленных в член флаги [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `uCodePage`  
 Кодовая страница для перевода (CP_ACP для кодовой страницы ANSI, 1200 для Юникода).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов или байтов в элементе управления. Если были установлены несовместимые флаги `dwFlags`, эта функция-член возвращает `E_INVALIDARG`.  
  
### <a name="remarks"></a>Примечания  
 `GetTextLengthEx`предоставляет дополнительные способы определения длины текста. Он поддерживает 2.0 Изменить расширенные функциональные возможности. В разделе [о широкие возможности изменять элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb787873) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]для получения дополнительной информации.  
  
##  <a name="a-namegettextmodea--cricheditctrlgettextmode"></a><a name="gettextmode"></a>CRichEditCtrl::GetTextMode  
 Возвращает текущий текстовый режим и отмены уровень управления rich edit.  
  
```  
UINT GetTextMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Набор битовых флагов из [TEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774364) тип перечисления, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Флаги указывают текущий текстовый режим и отмены уровень элемента управления.  
  
##  <a name="a-namegettextrangea--cricheditctrlgettextrange"></a><a name="gettextrange"></a>CRichEditCtrl::GetTextRange  
 Возвращает указанный диапазон символов.  
  
```  
int GetTextRange(
    int nFirst,  
    int nLast,  
    CString& refString) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nFirst`  
 Индекс позиции символа, непосредственно перед первым символом в диапазоне.  
  
 `nLast`  
 Позиция символа сразу после последнего символа в диапазоне.  
  
 `refString`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта, который будет получать текст.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов копируются, не включая завершающий символ null.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_GETTEXTRANGE](http://msdn.microsoft.com/library/windows/desktop/bb774199) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `GetTextRange`поддерживает 2.0 Изменить расширенные функциональные возможности. В разделе [о широкие возможности изменять элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb787873) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]для получения дополнительной информации.  
  
##  <a name="a-namegetundonamea--cricheditctrlgetundoname"></a><a name="getundoname"></a>CRichEditCtrl::GetUndoName  
 Получает тип следующего доступного действия в очереди отмены при их наличии.  
  
```  
UNDONAMEID GetUndoName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если отмененное действие находится в очереди отмены элемента управления, `GetUndoName` возвращает [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) тип перечисления, указывающее тип следующего действия в очереди. Пуста ли очередь отмены или неизвестного типа, если действие отмены в очереди `GetUndoName` возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Типы действий, которые можно отменить или повторить включают ввода, удаления, перемещения, вырезания и вставки. Эта информация может быть полезна для приложений, которые предоставляют расширенный пользовательский интерфейс для отмены и повтора операций, таких как раскрывающийся список действий, которые могут быть отменены.  
  
##  <a name="a-namegetwordwrapmodea--cricheditctrlgetwordwrapmode"></a><a name="getwordwrapmode"></a>CRichEditCtrl::GetWordWrapMode  
 Получает текущий перенос слов и параметров разбиения на слова для управления rich edit.  
  
```  
UINT GetWordWrapMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий перенос слов и разбиение по словам параметры. Эти параметры описаны в [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член доступен только для азиатских языков версий операционной системы.  
  
##  <a name="a-namehideselectiona--cricheditctrlhideselection"></a><a name="hideselection"></a>CRichEditCtrl::HideSelection  
 Изменение видимости выделения.  
  
```  
void HideSelection(
    BOOL bHide,  
    BOOL bPerm);
```  
  
### <a name="parameters"></a>Параметры  
 `bHide`  
 Указывает, если выделение должно отображать и скрывать, **TRUE** скрыть выделение.  
  
 `bPerm`  
 Указывает, будет ли это изменение в видимость для выбора постоянной.  
  
### <a name="remarks"></a>Примечания  
 При `bPerm` — **TRUE**, он изменяет `ECO_NOHIDESEL` возможность `CRichEditCtrl` объекта. Краткое описание этого параметра см. в разделе [SetOptions](#setoptions). Эта функция используется для задания всех параметров для данного `CRichEditCtrl` объекта.  
  
 Дополнительные сведения см. в разделе [EM_HIDESELECTION](http://msdn.microsoft.com/library/windows/desktop/bb774210) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&18;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_18.cpp)]  
  
##  <a name="a-namelimittexta--cricheditctrllimittext"></a><a name="limittext"></a>CRichEditCtrl::LimitText  
 Ограничивает длину текста, который пользователь может ввести в элемент управления.  
  
```  
void LimitText(long nChars = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nChars`  
 Указывает длину (в байтах), которые пользователь может вводить текст. Если этот параметр равен 0 (значение по умолчанию), длина текста имеет значение 64 КБ.  
  
### <a name="remarks"></a>Примечания  
 Изменение текста ограничения ограничивает только текст, который может быть введено пользователем. Он не влияет на любой текст уже в элементе управления, а также влияет на длину текста, копируются в элемент управления поля ввода, [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) функции-члена `CWnd`. Если приложение использует `SetWindowText` поместить текст в элемент управления редактированием, чем указано в вызове функции `LimitText`, пользователь может удалять любой текст в поле редактирования. Однако ограничение текст не позволит пользователю заменять существующий текст новым текстом, если удаление выделенного вызывает текста нарушит ограничение текста.  
  
> [!NOTE]
>  Для ограничения текста каждого элемента OLE подсчитывает как один символ.  
  
 Дополнительные сведения см. в разделе [EM_EXLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788003) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&19;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_19.cpp)]  
  
##  <a name="a-namelinefromchara--cricheditctrllinefromchar"></a><a name="linefromchar"></a>CRichEditCtrl::LineFromChar  
 Получает номер строки, содержащей символ с указанным индексом.  
  
```  
long LineFromChar(long nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс значение требуемого символа в тексте элемента управления поля ввода, или значение -1. Если `nIndex` –&1;, он указывает текущей строки, то есть строка, содержащая курсор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля номер строки, содержащей указанный индекс символа `nIndex`. Если `nIndex` –&1;, возвращается номер строки, содержащей первого символа выделения. Если не выбрано, возвращается текущий номер строки.  
  
### <a name="remarks"></a>Примечания  
 Индекс символа — количество символов от начала управления rich edit. Подсчет знаков, элемент OLE учитывается как один символ.  
  
 Дополнительные сведения см. в разделе [EM_EXLINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb788005) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&20;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_20.cpp)]  
  
##  <a name="a-namelineindexa--cricheditctrllineindex"></a><a name="lineindex"></a>CRichEditCtrl::LineIndex  
 Получает индекс строки в рамках этого `CRichEditCtrl` объекта.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nLine`  
 Содержит значение индекса для нужной строке в тексте элемента управления поля ввода, или значение -1. Если `nLine` –&1;, он указывает текущей строки, то есть строка, содержащая курсор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс строки, указанной в `nLine` или -1, если номер строки больше, то количество строк в элементе управления.  
  
### <a name="remarks"></a>Примечания  
 Индекс знака является число символов от начала управления rich edit на указанную строку.  
  
 Дополнительные сведения см. в разделе [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#21;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_21.cpp)]  
  
##  <a name="a-namelinelengtha--cricheditctrllinelength"></a><a name="linelength"></a>CRichEditCtrl::LineLength  
 Получает длину строки в элементе управления rich edit.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nLine`  
 Указывает индекс символа в строке, длина которого требуется получить. Если этот параметр имеет значение -1, возвращается длина текущей строки (строки, содержащей курсор), не включая длину любой выделенный текст в строке. Когда `LineLength` вызывается для элемента управления редактирования одной строки, этот параметр учитывается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Когда `LineLength` вызывается для элемента управления редактирования несколько строк, возвращается длина (в байтах) строки, указанной в `nLine`. Когда `LineLength` вызывается для элемента управления редактирования одной строки, возвращается длина текста в элементе управления (в байтах).  
  
### <a name="remarks"></a>Примечания  
 Используйте [LineIndex](#lineindex) функции-члена для получения индекс символа для заданного номера строки в рамках этого `CRichEditCtrl` объекта.  
  
 Дополнительные сведения см. в разделе [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [LineIndex](#lineindex).  
  
##  <a name="a-namelinescrolla--cricheditctrllinescroll"></a><a name="linescroll"></a>CRichEditCtrl::LineScroll  
 Прокрутка текста элемента управления редактированием несколько строк.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nLines`  
 Указывает количество строк для прокрутки по вертикали.  
  
 `nChars`  
 Указывает количество позиций знаков для прокрутки по горизонтали. Это значение игнорируется, если у элемента управления форматированным редактированием либо **ES_RIGHT** или **ES_CENTER** стиль. [Изменение стилей](../../mfc/reference/edit-styles.md) указываются в [создать](#create).  
  
### <a name="remarks"></a>Примечания  
 Элемент управления поля ввода не вертикальную прокрутку, после последней строки текста в элементе управления. Если текущей строки и количество строк, определяемое `nLines` превышает общее число строк в элементе управления, значение корректируется, чтобы последняя строка элемента управления может прокручиваться в верхней части окна управления редактированием.  
  
 `LineScroll`можно использовать для прокрутки по горизонтали после последнего символа все строки.  
  
 Дополнительные сведения см. в разделе [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="a-namepastea--cricheditctrlpaste"></a><a name="paste"></a>CRichEditCtrl::Paste  
 Вставляет данные из буфера обмена в `CRichEditCtrl` в точку вставки положением курсора в редакторе.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Примечания  
 Данные вставляются только в том случае, если в буфере обмена содержатся данные в формате.  
  
 Дополнительные сведения см. в разделе [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#22;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_22.cpp)]  
  
##  <a name="a-namepastespeciala--cricheditctrlpastespecial"></a><a name="pastespecial"></a>CRichEditCtrl::PasteSpecial  
 Вставка данных в определенном формате буфера обмена в это `CRichEditCtrl` объекта.  
  
```  
void PasteSpecial(
    UINT nClipFormat,  
    DWORD dvAspect = 0,  
    HMETAFILE hMF = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *nClipFormat*  
 Формат буфера обмена для вставки в это `CRichEditCtrl` объекта.  
  
 *dvAspect*  
 Аспект устройства, для данных, извлекаемых из буфера обмена.  
  
 *hMF*  
 Дескриптор метафайла, содержащей символическое представление объекта, чтобы вставить.  
  
### <a name="remarks"></a>Примечания  
 Новые материалы вставляется в позицию курсора, положением курсора в редакторе.  
  
 Дополнительные сведения см. в разделе [EM_PASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/bb774214) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#23;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_23.cpp)]  
  
##  <a name="a-nameposfromchara--cricheditctrlposfromchar"></a><a name="posfromchar"></a>CRichEditCtrl::PosFromChar  
 Возвращает координаты области клиента указанного символа в элемент управления редактированием.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nChar`  
 Отсчитываемый от нуля индекс символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Позиция символа, (x, y). Элемент управления редактирование однострочный координату по оси y всегда равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameredoa--cricheditctrlredo"></a><a name="redo"></a>CRichEditCtrl::Redo  
 Повтор следующего действия в очереди повторного выполнения элемента управления.  
  
```  
BOOL Redo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_REDO](http://msdn.microsoft.com/library/windows/desktop/bb774218) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namereplacesela--cricheditctrlreplacesel"></a><a name="replacesel"></a>CRichEditCtrl::ReplaceSel  
 Заменяет текущее выделение в этом `CRichEditCtrl` объект с указанным текстом.  
  
```  
void ReplaceSel(
    LPCTSTR lpszNewText,  
    BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszNewText`  
 Указатель нулем строка, содержащая текст для замены.  
  
 `bCanUndo`  
 Чтобы указать, что эта функция может быть отменено, значение этого параметра для **TRUE**. Значение по умолчанию — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Чтобы заменить весь текст в этом `CRichEditCtrl` , используйте [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
 Если выделенный фрагмент отсутствует, текст замены вставляется в позицию курсора, то есть текущей позиции курсора.  
  
 Эта функция будет отформатировано вставленный текст с существующей форматирование знаков. При замене весь диапазон текста (путем вызова `SetSel`(0, -1) до вызова метода `ReplaceSel`), существует в конце символ абзаца, который сохраняет форматирование предыдущего абзаца, которой в наследуемых вставленный текст.  
  
 Дополнительные сведения см. в разделе [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [LineIndex](#lineindex).  
  
##  <a name="a-namerequestresizea--cricheditctrlrequestresize"></a><a name="requestresize"></a>CRichEditCtrl::RequestResize  
 Это заставляет `CRichEditCtrl` объект для отправки **EN_REQUESTRESIZE** уведомления для родительского окна.  
  
```  
void RequestResize();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна при [CWnd::OnSize](../../mfc/reference/cwnd-class.md#onsize) обработку без дна `CRichEditCtrl` объекта.  
  
 Дополнительные сведения см. в разделе [EM_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb774220) сообщений и **элементов управления без дна широкие возможности изменить** раздел [о широкие возможности изменять элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb787873) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetautourldetecta--cricheditctrlsetautourldetect"></a><a name="setautourldetect"></a>CRichEditCtrl::SetAutoURLDetect  
 Задает элемент управления форматированием автоматически определить URL-адрес.  
  
```  
BOOL SetAutoURLDetect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Указывает, установлен ли элемент управления автоматически обнаруживать URL-адрес. Если **TRUE**, он включен. Если **FALSE**, он будет отключен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если успешно; в противном случае ненулевое значение. Например сообщение может завершиться ошибкой из-за нехватки памяти.  
  
### <a name="remarks"></a>Примечания  
 Если параметр включен, управления rich edit поиск текста, чтобы определить, соответствует стандартному формату URL-адрес. Список из следующих форматов URL-адрес, в разделе [EM_AUTOURLDETECT](http://msdn.microsoft.com/library/windows/desktop/bb787991) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Не устанавливайте `SetAutoURLDetect` для **TRUE** Если используется элемент управления редактирование **CFE_LINK** эффект для текста, отличный от URL-адреса. `SetAutoURLDetect`включает этот эффект для URL-адресов и отключает его для всего текста. В разделе [EN_LINK](http://msdn.microsoft.com/library/windows/desktop/bb787970) Дополнительные сведения о **CFE_LINK** эффект.  
  
##  <a name="a-namesetbackgroundcolora--cricheditctrlsetbackgroundcolor"></a><a name="setbackgroundcolor"></a>CRichEditCtrl::SetBackgroundColor  
 Задает цвет фона для этого `CRichEditCtrl` объекта.  
  
```  
COLORREF SetBackgroundColor(
    BOOL bSysColor,  
    COLORREF cr);
```  
  
### <a name="parameters"></a>Параметры  
 `bSysColor`  
 Указывает, если цвет фона должно быть присвоено значение system. Если это значение равно **TRUE**, `cr` игнорируется.  
  
 `cr`  
 Запрошенный фоновый цвет. Используется, только если `bSysColor` — **FALSE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 На предыдущий цвет фона для этого `CRichEditCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Можно задать цвет фона, или на заданное значение системы [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение.  
  
 Дополнительные сведения см. в разделе [EM_SETBKGNDCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774228) сообщений и [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#24;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_24.cpp)]  
  
##  <a name="a-namesetdefaultcharformata--cricheditctrlsetdefaultcharformat"></a><a name="setdefaultcharformat"></a>CRichEditCtrl::SetDefaultCharFormat  
 Задает символ, форматирование атрибуты для нового текста в этом `CRichEditCtrl` объекта.  
  
```  
BOOL SetDefaultCharFormat(CHARFORMAT& cf);  
BOOL SetDefaultCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 В первой версии указатель [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) структуру, содержащую новых атрибутов форматирования символов по умолчанию.  
  
 Во второй версии указатель [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) структуру, которая является расширением 2.0 изменить широкие возможности для **CHARFORMAT** структура, содержащая атрибутов форматирования символов по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Только атрибуты, указанные в **dwMask** членом `cf` были изменены с помощью этой функции.  
  
 Дополнительные сведения см. в разделе [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) сообщений и **CHARFORMAT** и **CHARFORMAT2** структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#25;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_25.cpp)]  
  
##  <a name="a-nameseteventmaska--cricheditctrlseteventmask"></a><a name="seteventmask"></a>CRichEditCtrl::SetEventMask  
 Задает маску события для этого `CRichEditCtrl` объекта.  
  
```  
DWORD SetEventMask(DWORD dwEventMask);
```  
  
### <a name="parameters"></a>Параметры  
 *dwEventMask*  
 Новая маска события для этого `CRichEditCtrl` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Маску предыдущие события.  
  
### <a name="remarks"></a>Примечания  
 Маска событие указывает, какие сообщения уведомления `CRichEditCtrl` отправляет его родительского окна объекта.  
  
 Дополнительные сведения см. в разделе [EM_SETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb774238) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#26;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_26.cpp)]  
  
##  <a name="a-namesetmodifya--cricheditctrlsetmodify"></a><a name="setmodify"></a>CRichEditCtrl::SetModify  
 Устанавливает или снимает измененного флага для элемента управления.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bModified`  
 Значение **TRUE** указывает, что текст был изменен, а значение **FALSE** указывает, он не меняется. По умолчанию значение измененного флага.  
  
### <a name="remarks"></a>Примечания  
 Измененный флаг указывает, был изменен ли текст в элементе управления редактирования. Автоматически устанавливается каждый раз, когда пользователь изменяет текст. Его значение можно получить с помощью [GetModify](#getmodify) функции-члена.  
  
 Дополнительные сведения см. в разделе [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [GetModify](#getmodify).  
  
##  <a name="a-namesetolecallbacka--cricheditctrlsetolecallback"></a><a name="setolecallback"></a>CRichEditCtrl::SetOLECallback  
 Это дает `CRichEditCtrl` объект **IRichEditOleCallback** объект, используемый для доступа к ресурсам, связанным с OLE и сведения.  
  
```  
BOOL SetOLECallback(IRichEditOleCallback* pCallback);
```  
  
### <a name="parameters"></a>Параметры  
 `pCallback`  
 Указатель на [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) объекта, `CRichEditCtrl` объекта будет использовать для получения ресурсов, связанные с OLE и сведений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это `CRichEditCtrl` объекта будет вызывать [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) увеличивается счетчик использования COM-объекта, заданного параметром `pCallback`.  
  
 Дополнительные сведения см. в разделе [EM_SETOLECALLBACK](http://msdn.microsoft.com/library/windows/desktop/bb774252) сообщений и [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) интерфейс [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetoptionsa--cricheditctrlsetoptions"></a><a name="setoptions"></a>CRichEditCtrl::SetOptions  
 Задает параметры для этого `CRichEditCtrl` объекта.  
  
```  
void SetOptions(
    WORD wOp,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *wOp*  
 Указывает тип операции. Одно из следующих значений:  
  
- `ECOOP_SET`Задайте параметры, указанные по `dwFlags`.  
  
- `ECOOP_OR`Объединить текущие параметры с разрешениями, заданными в `dwFlags`.  
  
- `ECOOP_AND`Сохранить только для текущих параметров, которые также указаны `dwFlags`.  
  
- `ECOOP_XOR`Сохранить только для текущих параметров, которые являются *не* определяется `dwFlags`.  
  
 `dwFlags`  
 Широкие возможности редактирования. Значения флагов, перечислены в разделе «Примечания».  
  
### <a name="remarks"></a>Примечания  
 Параметры может быть сочетанием следующих значений:  
  
- `ECO_AUTOWORDSELECTION`Дважды щелкните автоматический выбор слов на.  
  
- `ECO_AUTOVSCROLL`Автоматическая прокрутка текста справа по 10 символов при вводе символа в конце строки. Когда пользователь нажимает клавишу ВВОД, элемент управления прокручивается весь текст в нулевой позиции.  
  
- `ECO_AUTOHSCROLL`Автоматическая прокрутка текста вверх на одну страницу, при нажатии клавиши ВВОД в последней строке.  
  
- `ECO_NOHIDESEL`Отключает поведение по умолчанию для элемента управления. Поведение по умолчанию скрывает выбор, когда элемент управления теряет фокус ввода и показан выбор, когда элемент управления получает фокус ввода. При указании `ECO_NOHIDESEL`, инвертируется выделенный текст, даже если элемент управления имеет фокус.  
  
- `ECO_READONLY`Пользователю запрещено изменение текста в элементе управления.  
  
- `ECO_WANTRETURN`Указывает вставить символ возврата каретки, когда пользователь нажимает клавишу ВВОД при вводе текста в элементе управления rich edit несколько строк в диалоговом окне. Если не указать этот стиль, нажатие клавиши ВВОД отправляет команду управления rich edit родительского окна, который имитирует нажатие кнопки по умолчанию родительского окна (например, кнопка ОК в диалоговое окно). Этот стиль не оказывает влияния на однострочный элемент управления.  
  
- `ECO_SAVESEL`Сохраняет выбор, если элемент управления теряет фокус. По умолчанию когда он получает фокус выбираются все содержимое элемента управления.  
  
- `ECO_VERTICAL`Рисует текст и объекты в вертикальном направлении. Доступно только для азиатских языков.  
  
 Дополнительные сведения см. в разделе [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#27;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_27.cpp)]  
  
##  <a name="a-namesetparaformata--cricheditctrlsetparaformat"></a><a name="setparaformat"></a>CRichEditCtrl::SetParaFormat  
 Задает атрибуты для текущего выбора в этом форматирования абзаца `CRichEditCtrl` объекта.  
  
```  
BOOL SetParaFormat(PARAFORMAT& pf);  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Параметры  
 `pf`  
 В первой версии указатель [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) атрибуты форматирования абзаца структура, содержащая новое значение по умолчанию.  
  
 Во второй версии указатель [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) структуру, которая является расширением 2.0 изменить широкие возможности для **PARAFORMAT** структуры, удерживая атрибутов форматирования символов по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Только атрибуты, указанные в **dwMask** членом `pf` были изменены с помощью этой функции.  
  
 Дополнительные сведения см. в разделе [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) сообщений и **PARAFORMAT** и **PARAFORMAT2** структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#28;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_28.cpp)]  
  
##  <a name="a-namesetpunctuationa--cricheditctrlsetpunctuation"></a><a name="setpunctuation"></a>CRichEditCtrl::SetPunctuation  
 Задает знаки препинания в элементе управления rich edit.  
  
```  
BOOL SetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc);
```  
  
### <a name="parameters"></a>Параметры  
 `fType`  
 Флаг, знаки препинания. Список возможных значений см. в разделе `fType` параметр [EM_SETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774278) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpPunc`  
 Указатель на [ПУНКТУАЦИИ](http://msdn.microsoft.com/library/windows/desktop/bb787944) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член доступен для азиатских языков только версии операционной системы.  
  
##  <a name="a-namesetreadonlya--cricheditctrlsetreadonly"></a><a name="setreadonly"></a>CRichEditCtrl::SetReadOnly  
 Изменения `ECO_READONLY` возможность `CRichEditCtrl` объекта.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bReadOnly`  
 Указывает, если `CRichEditCtrl` объект должен быть только для чтения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Краткое описание этого параметра см. в разделе [SetOptions](#setoptions). Эта функция используется для задания всех параметров для данного `CRichEditCtrl` объекта.  
  
 Дополнительные сведения см. в разделе [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#29;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_29.cpp)]  
  
##  <a name="a-namesetrecta--cricheditctrlsetrect"></a><a name="setrect"></a>CRichEditCtrl::SetRect  
 Задает для этого прямоугольника форматирования `CRichEditCtrl` объекта.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md) или указатель [RECT](../../mfc/reference/rect-structure1.md) указывает новые границы прямоугольника форматирования.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольника форматирования является ограничивающим прямоугольником для текста. Ограничивающим прямоугольником не зависит от размера окна элемента управления форматированным редактированием. При этом `CRichEditCtrl` сначала создается объект, форматирования прямоугольника равна размеру клиентской области окна. Используйте `SetRect` для увеличения или меньше, чем окно форматируемого прямоугольника форматирования.  
  
 Дополнительные сведения см. в разделе [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#30;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_30.cpp)]  
  
##  <a name="a-namesetsela--cricheditctrlsetsel"></a><a name="setsel"></a>CRichEditCtrl::SetSel  
 Задает выбранный в рамках этого `CRichEditCtrl` объекта.  
  
```  
void SetSel(
    long nStartChar,  
    long nEndChar);  
  
void SetSel(CHARRANGE& cr);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartChar`  
 Отсчитываемый от нуля индекс первого символа для выбора.  
  
 `nEndChar`  
 Отсчитываемый от нуля индекс последнего символа для выбора.  
  
 `cr`  
 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) структуру, которая содержит границы текущего выделенного фрагмента.  
  
### <a name="remarks"></a>Примечания  
 Две формы этой функции предоставляют альтернативные способы задать границы для выбора. Выполните краткое описание каждого из этих форм.  
  
- **SetSel (** `cr` **)** в этой форме используются **CHARRANGE** структура с его **cpMin** и **cpMax** членов границы.  
  
- **SetSel (** `nStartChar` **,** `nEndChar` **)** параметры использовать эту форму `nStartChar` и `nEndChar` Чтобы задать границы.  
  
 Курсор помещается в конце соответствующий больше начала ( **cpMin** или `nStartChar`) и окончания ( **cpMax** или `nEndChar`) индексов. Эта функция прокручивает содержимое элемента `CRichEditCtrl` , чтобы курсор был виден.  
  
 Чтобы выбрать весь текст в этом `CRichEditCtrl` , вызовите `SetSel` с начального индекса 0 и конечный индекс – 1.  
  
 Дополнительные сведения см. в разделе [EM_EXSETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788007) сообщений и [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [GetSel](#getsel).  
  
##  <a name="a-namesetselectioncharformata--cricheditctrlsetselectioncharformat"></a><a name="setselectioncharformat"></a>CRichEditCtrl::SetSelectionCharFormat  
 Задает символ, форматирование атрибуты для текста в выделенном фрагменте в этом `CRichEditCtrl` объекта.  
  
```  
BOOL SetSelectionCharFormat(CHARFORMAT& cf);  
BOOL SetSelectionCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 В первой версии указатель [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) структуру, содержащую форматирование знаков атрибуты для текущего выделения.  
  
 Во второй версии указатель [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) структуру, которая является расширением 2.0 изменение форматированного для **CHARFORMAT** структуры, содержащий символ новой форматирование атрибуты для текущего выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Только атрибуты, указанные в **dwMask** членом `cf` были изменены с помощью этой функции.  
  
 Дополнительные сведения см. в разделе [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) и **CHARFORMAT** и **CHARFORMAT2** структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#31;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_31.cpp)]  
  
##  <a name="a-namesettargetdevicea--cricheditctrlsettargetdevice"></a><a name="settargetdevice"></a>CRichEditCtrl::SetTargetDevice  
 Задает ширину целевого устройства и строки для WYSIWYG (отображаемые получается) форматирования в этом `CRichEditCtrl` объекта.  
  
```  
BOOL SetTargetDevice(
    HDC hDC,  
    long lLineWidth);

 
BOOL SetTargetDevice(
    CDC& dc,  
    long lLineWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `hDC`  
 Дескриптор контекста устройства для нового целевого устройства.  
  
 *lLineWidth*  
 Толщина линии, используемый для форматирования.  
  
 `dc`  
 [CDC](../../mfc/reference/cdc-class.md) для нового целевого устройства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 При успешном выполнении эта функция управления rich edit, которому принадлежит устройство контекста, переданного в качестве параметра. В этом случае вызываемая функция не должен уничтожить контекст устройства.  
  
 Дополнительные сведения см. в разделе [EM_SETTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/bb774282) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#32;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_32.cpp)]  
  
##  <a name="a-namesettextmodea--cricheditctrlsettextmode"></a><a name="settextmode"></a>CRichEditCtrl::SetTextMode  
 Задает уровень текстовый режим или отмены и повтора для элемента управления rich edit.  
  
```  
BOOL SetTextMode(UINT fMode);
```  
  
### <a name="parameters"></a>Параметры  
 *fMode*  
 Задает новые параметры для элемента управления текстового режима и отмены уровня параметров. Список возможных значений см. в разделе параметра режима для [EM_SETTEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774286) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если успешно; в противном случае ненулевое значение.  
  
### <a name="remarks"></a>Примечания  
 Описание режимов текста в разделе **EM_SETTEXTMODE** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Эта функция-член не выполняется, если элемент управления содержит текст. Убедитесь, что элемент управления является пустым, отправлять [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) сообщений с пустой строкой.  
  
##  <a name="a-namesetundolimita--cricheditctrlsetundolimit"></a><a name="setundolimit"></a>CRichEditCtrl::SetUndoLimit  
 Задает максимальное число действий, которые могут храниться в очереди отмены.  
  
```  
UINT SetUndoLimit(UINT nLimit);
```  
  
### <a name="parameters"></a>Параметры  
 *nLimit*  
 Указывает максимальное число действий, которые могут храниться в очереди отмены. Установлено в ноль для отключения отката.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное количество новых отмененные действия для сложных поля ввода.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию максимальное количество действий в очереди отмены — 100. Если увеличить это число должно существовать недостаточно памяти для размещения новой. Для повышения производительности ограничить до минимально допустимое значение.  
  
##  <a name="a-namesetwordcharformata--cricheditctrlsetwordcharformat"></a><a name="setwordcharformat"></a>CRichEditCtrl::SetWordCharFormat  
 Задает символ, форматирование атрибуты для выбранного слова в этом `CRichEditCtrl` объекта.  
  
```  
BOOL SetWordCharFormat(CHARFORMAT& cf);  
BOOL SetWordCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 В первой версии указатель [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) атрибуты структуру, содержащую форматирование знаков для выделенного слова.  
  
 Во второй версии указатель [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) структуру, которая является расширением 2.0 изменить широкие возможности для **CHARFORMAT** структуру, содержащую атрибуты для выбранного слова форматирования символ новой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Только атрибуты, указанные в **dwMask** членом `cf` были изменены с помощью этой функции.  
  
 Дополнительные сведения см. в разделе [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) сообщений и **CHARFORMAT** и **CHARFORMAT2** структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#33;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_33.cpp)]  
  
##  <a name="a-namesetwordwrapmodea--cricheditctrlsetwordwrapmode"></a><a name="setwordwrapmode"></a>CRichEditCtrl::SetWordWrapMode  
 Установка параметров переноса слов и разбиение по словам для сложных поля ввода.  
  
```  
UINT SetWordWrapMode(UINT uFlags) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `uFlags`  
 Параметры, устанавливаемые для переноса и разбиение по словам. Список возможных параметров в разделе [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий перенос слов и разбиение по словам параметры.  
  
### <a name="remarks"></a>Примечания  
 Это сообщение является доступны только в азиатских языках версий операционной системы.  
  
##  <a name="a-namestopgrouptypinga--cricheditctrlstopgrouptyping"></a><a name="stopgrouptyping"></a>CRichEditCtrl::StopGroupTyping  
 Остановка управления сбор дополнительных ввода в действие отмены текущего действия.  
  
```  
void StopGroupTyping();
```  
  
### <a name="remarks"></a>Примечания  
 Элемент управления сохраняет следующего действия ввода, если таковая имеется, в новое действие в очереди отмены.  
  
 Дополнительные сведения см. в разделе [EM_STOPGROUPTYPING](http://msdn.microsoft.com/library/windows/desktop/bb774300) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namestreamina--cricheditctrlstreamin"></a><a name="streamin"></a>CRichEditCtrl::StreamIn  
 Заменяет текст в этой `CRichEditCtrl` вместе с текстом из указанного входного потока.  
  
```  
long StreamIn(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>Параметры  
 `nFormat`  
 Флаги, определяющие форматы входных данных. Дополнительные сведения см. в разделе "Примечания".  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) структура входного потока. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число считанных символов из входного потока.  
  
### <a name="remarks"></a>Примечания  
 Значение `nFormat` должно быть одним из следующих:  
  
- `SF_TEXT`Указывает только для чтения текста.  
  
- `SF_RTF`Указывает чтения текста и форматирование.  
  
 Одно из этих значений может сочетаться с `SFF_SELECTION`. Если `SFF_SELECTION` указан, `StreamIn` заменяет текущее выделение содержимое входного потока. Если не указан, `StreamIn` заменяет все содержимое `CRichEditCtrl` объекта.  
  
 В **EDITSTREAM** параметр `es`, можно указать функции обратного вызова, который заполняет буфер текста. Эта функция обратного вызова вызывается повторно, пока не будет исчерпан входного потока.  
  
 Дополнительные сведения см. в разделе [EM_STREAMIN](http://msdn.microsoft.com/library/windows/desktop/bb774302) сообщений и [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#34;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_34.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#35;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_35.cpp)]  
  
##  <a name="a-namestreamouta--cricheditctrlstreamout"></a><a name="streamout"></a>CRichEditCtrl::StreamOut  
 Записывает содержимое данного `CRichEditCtrl` объект в указанный выходной поток.  
  
```  
long StreamOut(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>Параметры  
 `nFormat`  
 Флаги, определяющие форматы вывода данных. Дополнительные сведения см. в разделе "Примечания".  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) структуры, указав в выходной поток. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, записанных в выходной поток.  
  
### <a name="remarks"></a>Примечания  
 Значение `nFormat` должно быть одним из следующих:  
  
- `SF_TEXT`Указывает только текст письма.  
  
- `SF_RTF`Указывает, написание текста и форматирования.  
  
- `SF_RTFNOOBJS`Указывает, написание текста и форматирования, заменив пробелы OLE-элементы.  
  
- `SF_TEXTIZED`Указывает, написание текста и форматирования, с помощью текстового представления элементов OLE.  
  
 Эти значения могут объединяться с `SFF_SELECTION`. Если `SFF_SELECTION` указан, `StreamOut` записывает текущее выделение в выходной поток. Если не указан, `StreamOut` записывает все содержимое данного объекта `CRichEditCtrl` объекта.  
  
 В **EDITSTREAM** параметр `es`, можно указать функции обратного вызова, который заполняет буфер текста. Эта функция обратного вызова вызывается повторно, пока не будет исчерпан в выходной поток.  
  
 Дополнительные сведения см. в разделе [EM_STREAMOUT](http://msdn.microsoft.com/library/windows/desktop/bb774304) сообщений и [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#36;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_36.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#37;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_37.cpp)]  
  
##  <a name="a-nameundoa--cricheditctrlundo"></a><a name="undo"></a>CRichEditCtrl::Undo  
 Отменяет последнюю операцию в управления rich edit.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция отмены выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Операции отмены также могут быть отменены. Например, можно восстановить удаленный текст с первого вызова **отменить**. При условии, что нет промежуточные операции редактирования, можно удалить текст снова с помощью второго вызова **отменить**.  
  
 Дополнительные сведения см. в разделе [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CanUndo](#canundo).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CRichEditView-класс](../../mfc/reference/cricheditview-class.md)

