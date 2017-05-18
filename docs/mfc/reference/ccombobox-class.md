---
title: "CComboBox-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
dev_langs:
- C++
helpviewer_keywords:
- combo boxes, CComboBox objects
- CComboBox class
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
caps.latest.revision: 25
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 6cd8407f3c70469afa256d8fb7608b7de43b6c72
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="ccombobox-class"></a>CComboBox-класс
Предоставляет функции поля со списком Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CComboBox : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComboBox::CComboBox](#ccombobox)|Создает объект `CComboBox`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComboBox::AddString](#addstring)|Добавляет строку в конец списка в поле со списком списком или позиции отсортированных списков с **CBS_SORT** стиля.|  
|[CComboBox::Clear](#clear)|Удаляет (очищает) текущее выделение, если таковая имеется, в поле редактирования.|  
|[CComboBox::CompareItem](#compareitem)|Вызывается платформой для определения относительной позиции элемента списка в отсортированном определяемые владельцем поле со списком.|  
|[CComboBox::Copy](#copy)|Копирует текущее выделение в том случае, если таковая имеется, в буфер обмена в **CF_TEXT** формат.|  
|[CComboBox::Create](#create)|Создает поле со списком и прикрепляет его к `CComboBox` объекта.|  
|[CComboBox::Cut](#cut)|Удаляет (порезов) выделенного элемента, если имеется, в режиме изменения управления и копирует удаленный текст в буфер обмена в **CF_TEXT** формат.|  
|[CComboBox::DeleteItem](#deleteitem)|Вызывается платформой при удалении элемента списка из определяемых владельцем списком.|  
|[CComboBox::DeleteString](#deletestring)|Удаляет строку из списка поля со списком.|  
|[CComboBox::Dir](#dir)|Добавляет список имен файлов в список поля со списком.|  
|[CComboBox::DrawItem](#drawitem)|Вызывается платформой при изменении внешнего вида пользовательского со списком, изменится.|  
|[CComboBox::FindString](#findstring)|Находит первая строка, содержащая префикс, указанный в списке поля со списком.|  
|[CComboBox::FindStringExact](#findstringexact)|Находит первый списков строки (в поле со списком), совпадающий с указанной строкой.|  
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Извлекает сведения о `CComboBox` объекта.|  
|[CComboBox::GetCount](#getcount)|Возвращает число элементов в списке поля со списком.|  
|[CComboBox::GetCueBanner](#getcuebanner)|Возвращает текст подсказки, отображаемый для элемента управления поля со списком.|  
|[CComboBox::GetCurSel](#getcursel)|Извлекает индекс текущего выделенного элемента, если таковая имеется, в списке поля со списком.|  
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Извлекает координаты на экране отображается (удаленные вниз) списка раскрывающемся поле со списком.|  
|[CComboBox::GetDroppedState](#getdroppedstate)|Определяет, является ли поле со списком в поле с раскрывающимся списком отображается (раскрыл).|  
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Возвращает минимально допустимого ширину части раскрывающегося списка в поле со списком.|  
|[CComboBox::GetEditSel](#geteditsel)|Возвращает позиции символов начала и конца текущего выделенного фрагмента в элементе управления списком.|  
|[CComboBox::GetExtendedUI](#getextendedui)|Определяет, имеет ли поле со списком пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс.|  
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Возвращает ширину в пикселях горизонтальной прокруткой списков часть поле со списком.|  
|[CComboBox::GetItemData](#getitemdata)|Извлекает значение предоставленного приложением 32-разрядной, связанное с указанным списком элементов.|  
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Возвращает 32-разрядного указателя предоставленную приложением, который связан с указанным списком элементов.|  
|[CComboBox::GetItemHeight](#getitemheight)|Получает высоту элементов списка в поле со списком.|  
|[CComboBox::GetLBText](#getlbtext)|Получает строку из списка поля со списком.|  
|[CComboBox::GetLBTextLen](#getlbtextlen)|Возвращает длину строки в списке поля со списком.|  
|[CComboBox::GetLocale](#getlocale)|Возвращает идентификатор языкового стандарта для поля со списком.|  
|[CComboBox::GetMinVisible](#getminvisible)|Получает минимальное количество видимых элементов в раскрывающемся списке текущего поля со списком.|  
|[CComboBox::GetTopIndex](#gettopindex)|Возвращает индекс первой видимой позиции в списке части поле со списком.|  
|[CComboBox::InitStorage](#initstorage)|Предварительно размещает блоки памяти для элементов и строк в списке части поле со списком.|  
|[CComboBox::InsertString](#insertstring)|Вставляет строку в список поля со списком.|  
|[CComboBox::LimitText](#limittext)|Ограничивает длину текста, который пользователь может ввести в элемент управления списком.|  
|[CComboBox::MeasureItem](#measureitem)|Вызывается платформой для определения измерений поле со списком при создании определяемых владельцем списком.|  
|[CComboBox::Paste](#paste)|Вставляет данные из буфера обмена в элемент управления, расположенный в текущей позиции курсора. Вставляются данные только в том случае, если в буфере обмена содержатся данные в **CF_TEXT** формат.|  
|[CComboBox::ResetContent](#resetcontent)|Удаляет все элементы из списка и измените элемент управления списком.|  
|[CComboBox::SelectString](#selectstring)|Выполняет поиск строки в списке поля со списком и, если строка найдена, выбирает строки в поле со списком и копирует строки в элемент управления для редактирования.|  
|[CComboBox::SetCueBanner](#setcuebanner)|Задает текст подсказки, отображаемый для элемента управления поля со списком.|  
|[CComboBox::SetCurSel](#setcursel)|Выбирает строку в списке поля со списком.|  
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Задает минимально допустимого ширину части раскрывающегося списка в поле со списком.|  
|[CComboBox::SetEditSel](#seteditsel)|Выбирает символов в элементе управления списком.|  
|[CComboBox::SetExtendedUI](#setextendedui)|Выбирает пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс поле со списком, который имеет **CBS_DROPDOWN** или **CBS_DROPDOWNLIST** стиля.|  
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Задает ширину в пикселях горизонтальной прокруткой списков часть поле со списком.|  
|[CComboBox::SetItemData](#setitemdata)|Задает 32-разрядное значение, связанное с указанным элементом в поле со списком.|  
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Задает 32-разрядный указатель, связанный с указанного элемента в поле со списком.|  
|[CComboBox::SetItemHeight](#setitemheight)|Задает высоту элементов списка в поле со списком или высота элемента управления редактирования (или статического текста) часть со списком.|  
|[CComboBox::SetLocale](#setlocale)|Задает идентификатор языкового стандарта для поля со списком.|  
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Задает минимальное число видимых элементов в раскрывающемся списке текущего поля со списком.|  
|[CComboBox::SetTopIndex](#settopindex)|Сообщает списков часть поле со списком для отображения элемента с указанным индексом в верхней.|  
|[CComboBox::ShowDropDown](#showdropdown)|Показывает или скрывает поле со списком поле со списком, который имеет **CBS_DROPDOWN** или **CBS_DROPDOWNLIST** стиля.|  
  
## <a name="remarks"></a>Примечания  
 Поле со списком содержит поле со списком, в сочетании с статический элемент управления или элемент управления. Списков части элемента управления могут отображаться все время или только может раскрывающийся список, когда пользователь выбирает стрелку раскрывающегося списка рядом с элементом управления.  
  
 Текущего выделенного элемента (если таковые имеются) в поле со списком отображается в статическом или элемента управления edit. Кроме того Если поле со списком имеет стиль раскрывающегося списка, пользователь может ввести начальный символ для одного из элементов в списке и списке, если она видна, будут выделены следующего элемента с этого начального знака.  
  
 В следующей таблице сравниваются три списком [стили](../../mfc/reference/combo-box-styles.md).  
  
|Стиль|Если отображается список|Статический метод или редактирования элемента управления|  
|-----------|-------------------------------|-----------------------------|  
|Простая|Всегда|Правка|  
|Drop-down|При удалении|Правка|  
|Раскрывающийся список|При удалении|Static|  
  
 Можно создать `CComboBox` объекта на основе шаблона диалогового окна или непосредственно в коде. В обоих случаях сначала вызовите конструктор `CComboBox` для создания `CComboBox` объекта; затем вызвать [создать](#create) функции-члена для создания элемента управления и присоединить его к `CComboBox` объекта.  
  
 Если вы хотите обработки сообщений Windows уведомлений, отправленных в поле со списком с родительским (обычно класс, производный от `CDialog`), добавить схему сообщений входа и обработчик сообщений функции-члена родительского класса для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 **ON_**Notification **(**`id`**,**`memberFxn`**)**  
  
 где `id` указывает идентификатор дочернего окна элемента управления списком, отправляющего уведомление и `memberFxn` имя функции-члена родительского вы написали для обработки уведомления.  
  
 Прототип функции родительского элемента выглядит следующим образом:  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 Невозможно предсказать порядок, в котором некоторые уведомления будут отправляться. В частности **CBN_SELCHANGE** уведомление может возникнуть до или после **CBN_CLOSEUP** уведомления.  
  
 Ниже перечислены возможные записи схемы сообщений.  
  
- **ON_CBN_CLOSEUP** (Windows 3.1 или более поздней версии.) Поле со списком списком закрыл. Это сообщение уведомления не отправляются для поля со списком, которое имеет [CBS_SIMPLE](../../mfc/reference/combo-box-styles.md) стиля.  
  
- **ON_CBN_DBLCLK** пользователь дважды щелкает строку в списке поля со списком. Это уведомление отправляется только в поле со списком **CBS_SIMPLE** стиля. Для поля со списком с [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиля, двойным щелчком невозможен из-за одним щелчком скрывает поле списка.  
  
- **ON_CBN_DROPDOWN** поле со списком списком — раскрывающийся список (виден). Это сообщение уведомления возможна только в поле со списком **CBS_DROPDOWN** или **CBS_DROPDOWNLIST** стиля.  
  
- **ON_CBN_EDITCHANGE** смены действие, которое может изменен текст в элемент управления Правка часть со списком. В отличие от **CBN_EDITUPDATE** , это сообщение будет отправлено после обновления экрана в Windows. Не отправляются, если поле со списком имеет **CBS_DROPDOWNLIST** стиля.  
  
- **ON_CBN_EDITUPDATE** управления редактирования часть со списком собирается отобразить измененный текст. Это уведомление отправляется после форматирования текста элемента управления, но до отображения текста. Не отправляются, если поле со списком имеет **CBS_DROPDOWNLIST** стиля.  
  
- **ON_CBN_ERRSPACE** поле со списком не удается выделить достаточно памяти для выполнения конкретного запроса.  
  
- **ON_CBN_SELENDCANCEL** (Windows 3.1 или более поздней версии.) Указывает, что следует отменить выбор пользователя. Пользователь щелкает элемент и затем нажимает другого окна или элемента управления, чтобы скрыть поле со списком в поле со списком. Это уведомление отправляется перед **CBN_CLOSEUP** сообщение уведомления, чтобы указать игнорирования выбранных пользователем. **CBN_SELENDCANCEL** или **CBN_SELENDOK** отправляется уведомление даже в том случае, если **CBN_CLOSEUP** не отправляется уведомление (как в случае в поле со списком **CBS_SIMPLE** стиль).  
  
- **ON_CBN_SELENDOK** пользователь выбирает элемент и затем нажимает клавишу ВВОД или нажимает клавиши Стрелка вниз, чтобы скрыть поле со списком в поле со списком. Это уведомление отправляется перед **CBN_CLOSEUP** сообщение, чтобы указать, что выбор пользователем должно считаться допустимым. **CBN_SELENDCANCEL** или **CBN_SELENDOK** отправляется уведомление даже в том случае, если **CBN_CLOSEUP** не отправляется уведомление (как в случае в поле со списком **CBS_SIMPLE** стиль).  
  
- **ON_CBN_KILLFOCUS** поле со списком теряет фокус ввода.  
  
- **ON_CBN_SELCHANGE** элемент, выбранный в списке поля со списком собирается измениться в результате пользователь, щелкнув в поле со списком или изменение выделения с помощью клавиш со стрелками. При обработке этого сообщения, текст в поле редактирования комбинированного окна можно получить только через `GetLBText` или другой аналогичные функции. `GetWindowText`не может использоваться.  
  
- **ON_CBN_SETFOCUS** поле со списком получает фокус ввода.  
  
 Если вы создаете `CComboBox` объектов в диалоговом окне (с помощью ресурса диалогового окна) `CComboBox` объект автоматически освобождается, когда пользователь закрывает диалоговое окно.  
  
 При внедрении `CComboBox` объекта объект внутри другого окна необходимо уничтожить его. Если вы создаете `CComboBox` объекта в стеке, удаляется автоматически. При создании `CComboBox` объекта в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы оно уничтожается при уничтожении поле со списком Windows.  
  
 **Примечание** Если необходимо обработать `WM_KEYDOWN` и `WM_CHAR` сообщений, необходимо подкласс поле со списком редактировать и список элементов управления, создавать производные классы от `CEdit` и `CListBox`, и добавьте обработчики для этих сообщений для производных классов. Дополнительные сведения см. в разделе [http://support.microsoft.com/default.aspxscid=kb;en-us; Q174667](http://support.microsoft.com/default.aspxscid=kb;en-us;q174667) и [CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="addstring"></a>CComboBox::AddString  
 Добавляет строку в списке поля со списком.  
  
```  
int AddString(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszString`  
 Указывает на строку, завершающуюся значением null, который должен быть добавлен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение больше или равно 0, это начинающийся с нуля индекс строки в окне списка. Возвращает значение **CB_ERR** ; при возникновении ошибки возвращается **CB_ERRSPACE** Если недостаточно места для хранения новой строки.  
  
### <a name="remarks"></a>Примечания  
 Если в списке не был создан с [CBS_SORT](../../mfc/reference/combo-box-styles.md) стиля, строка добавляется в конец списка. В противном случае строка вставляется в списке, и список сортируется.  
  
> [!NOTE]
>  Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения в этом элементе управления см. в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Чтобы вставить строку в определенное место в списке, используйте [InsertString](#insertstring) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]  
  
##  <a name="ccombobox"></a>CComboBox::CComboBox  
 Создает объект `CComboBox`.  
  
```  
CComboBox();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]  
  
##  <a name="clear"></a>CComboBox::Clear  
 Удаляет (очищает) текущее выделение, если таковая имеется, в поле редактирования комбинированного окна.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы удалить текущий выделенный фрагмент и поместить удаленные содержимое в буфер обмена, используйте [Вырезать](#cut) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CComboBox::CompareItem  
 Вызывается платформой для определения относительной позиции нового элемента в списке части отсортированный рисования владельцем поле со списком.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpCompareItemStruct`  
 Длинный указатель [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает относительную позицию двух элементов, описанных в `COMPAREITEMSTRUCT` структуры. Он может иметь любое из следующих значений.  
  
|Значение|Значение|  
|-----------|-------------|  
|- 1|Элемент 1 предшествует элемент 2.|  
|0|1 и 2 элемент сортировки одинаковыми.|  
|1|Элемент 1 сортирует после элемента 2.|  
  
 В разделе [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) описание `COMPAREITEMSTRUCT`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. При создании поле со списком рисуемый владельцем **LBS_SORT** стилей, необходимо переопределить эту функцию-член для помощи в новые элементы, добавленные в список сортировки платформу.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]  
  
##  <a name="copy"></a>CComboBox::Copy  
 Копирует текущее выделение в том случае, если таковая имеется, в поле редактирования комбинированного окна в буфер обмена в **CF_TEXT** формат.  
  
```  
void Copy();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]  
  
##  <a name="create"></a>CComboBox::Create  
 Создает поле со списком и прикрепляет его к `CComboBox` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль поля со списком. Примените любое сочетание [стили полей со списками](../../mfc/reference/combo-box-styles.md) в поле.  
  
 `rect`  
 Указывает положение и размер комбинированного окна. Может быть [структура RECT](../../mfc/reference/rect-structure1.md) или `CRect` объекта.  
  
 `pParentWnd`  
 Указывает поле со списком родительскому окну (обычно `CDialog`). Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CComboBox` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает поле со списком Windows и прикрепляет его к `CComboBox` объекта.  
  
 Когда **создать** выполняет Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщений в поле со списком.  
  
 Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CComboBox`, добавить схему сообщений к новому классу и переопределить предыдущей функции-члены обработчика сообщений. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Применить следующие [стили окна](../../mfc/reference/window-styles.md) к элементу управления полем со списком. :  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_VSCROLL** Добавление вертикальную прокрутку, для поля со списком в поле со списком  
  
- **WS_HSCROLL** для добавления горизонтальной прокрутки для поля со списком в поле со списком  
  
- **WS_GROUP** для группировки элементов управления  
  
- **WS_TABSTOP** включать поле со списком в порядок перехода по табуляции  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]  
  
##  <a name="cut"></a>CComboBox::Cut  
 Удалений (порезов) текущее выделение, если таковой имеется, в поле со списком ввода, управления и копирует удаленный текст в буфер обмена в **CF_TEXT** формат.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы удалить выбранные элементы без помещения удаленный текст в буфер обмена, вызовите [снимите](#clear) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]  
  
##  <a name="deleteitem"></a>CComboBox::DeleteItem  
 Вызывается платформой, когда пользователь удаляет элемент из рисуемый владельцем `CComboBox` объекта или уничтожает поле со списком.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDeleteItemStruct`  
 Длинный указатель на Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) структуру, содержащую сведения о удаляемого элемента. В разделе [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) описание этой структуры.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для перерисовки поле со списком, при необходимости.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]  
  
##  <a name="deletestring"></a>CComboBox::DeleteString  
 Удаляет элемент в позиции `nIndex` из поля со списком.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает индекс строки, который требуется удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение больше или равно 0, представляет число строк, оставшихся в списке. Возвращает значение **CB_ERR** Если `nIndex` указывает индекс больше числа элементов в списке.  
  
### <a name="remarks"></a>Примечания  
 Все элементы, следующие `nIndex` теперь перемещаются на одну позицию вниз. Например если поле со списком содержит два элемента, удаление первого элемента приведет оставшиеся элемента: теперь в первую позицию. `nIndex`= 0 в первую позицию элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]  
  
##  <a name="dir"></a>CComboBox::Dir  
 Список имен файлов или накопителей добавляет в список поля со списком.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Параметры  
 `attr`  
 Может быть любым сочетанием `enum` значений описано в [CFile::GetStatus](../../mfc/reference/cfile-class.md#getstatus) или любое сочетание следующих значений:  
  
- **DDL_READWRITE** файл для чтения и записи.  
  
- **DDL_READONLY** файл можно считывать, но не записываются.  
  
- **DDL_HIDDEN** файл является скрытым и не отображается в списках каталогов.  
  
- **DDL_SYSTEM** файл является системным файлом.  
  
- **DDL_DIRECTORY** имя, заданное `lpszWildCard` указывает каталог.  
  
- **DDL_ARCHIVE** файл помещен в архив.  
  
- **DDL_DRIVES** относятся все диски, которые соответствуют имени, указанного параметром `lpszWildCard`.  
  
- **DDL_EXCLUSIVE** флаг Exclusive. Если установить флаг exclusive, включаются только файлы указанного типа. В противном случае файлы указанного типа, перечислены помимо файлов «normal».  
  
 `lpszWildCard`  
 Указывает строку спецификация файла. Строка может содержать подстановочные знаки (например, *.\*).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение больше или равно 0, это начинающийся с нуля индекс последнего имени файла добавляется в список. Возвращает значение **CB_ERR** ; при возникновении ошибки возвращается **CB_ERRSPACE** Если недостаточно места для хранения новых строк.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения в этом элементе управления см. в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]  
  
##  <a name="drawitem"></a>CComboBox::DrawItem  
 Вызывается платформой при изменении внешнего вида рисуемый владельцем со списком, изменится.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено. В разделе [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) описание этой структуры.  
  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член для реализации отрисовки рисуемый владельцем `CComboBox` объекта. Перед завершением работы этой функции-члена, приложение следует восстановить всех графических устройств (интерфейс) выбранных объектов контекст отображения указано в `lpDrawItemStruct`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox № 11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]  
  
##  <a name="findstring"></a>CComboBox::FindString  
 Находит, но не приводит к выделению, первая строка, содержащая префикс, указанный в списке поля со списком.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszString) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nStartAfter`  
 Содержит отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает нижней части списка, он по-прежнему в верхней части списка обратно элемент с указанным `nStartAfter`. Если значение-1, весь список выполняется поиск с начала.  
  
 `lpszString`  
 Указывает на строку, завершающуюся значением null, содержащая префикс для поиска. Поиск ситуация независимые, поэтому эта строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение больше или равно 0, это начинающийся с нуля индекс элемента сопоставления. Это **CB_ERR** , если не удалось выполнить поиск.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения в этом элементе управления см. в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]  
  
##  <a name="findstringexact"></a>CComboBox::FindStringExact  
 Вызовите `FindStringExact` для поиска первого списков строки (в поле со списком), соответствующая строка, указанная в функции-члена `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndexStart`  
 Задает отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает нижней части списка, он по-прежнему в верхней части списка обратно элемент с указанным `nIndexStart`. Если `nIndexStart` равно -1, весь список просматривается с самого начала.  
  
 `lpszFind`  
 Указывает на строку, завершающуюся значением null, для поиска. Эта строка может содержать полное имя файла, включая расширение. Поиск не учитывается регистр, поэтому эта строка может содержать любое сочетание букв верхнего и нижнего регистра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента сопоставления или **CB_ERR** , если не удалось выполнить поиск.  
  
### <a name="remarks"></a>Примечания  
 Если поле со списком был создан в стиле рисуемый владельцем, но без [CBS_HASSTRINGS](../../mfc/reference/combo-box-styles.md) стиля, `FindStringExact` пытается сопоставить двойное значение для значения `lpszFind`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]  
  
##  <a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo  
 Возвращает сведения о `CComboBox` объекта.  
  
```  
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pcbi*  
 Указатель на [COMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775798) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [CB_GETCOMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775839) сообщения, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcount"></a>CComboBox::GetCount  
 Вызовите эту функцию-член для получения количества элементов в списке часть со списком.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов. Количество возвращаемых результатов — единицу больше, чем значение индекса последнего элемента (индекс начинается с нуля). Это **CB_ERR** при возникновении ошибки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]  
  
##  <a name="getcuebanner"></a>CComboBox::GetCueBanner  
 Возвращает текст подсказки, отображаемый для элемента управления поля со списком.  
  
```  
CString GetCueBanner() const;  
  
BOOL GetCueBanner(
    LPTSTR lpszText,   
    int cchText) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `lpszText`|Указатель на буфер, получающий текст баннера подсказки.|  
|[in] `cchText`|Размер буфера, `lpszText` указывает параметр.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой перегрузке [CString](../../atl-mfc-shared/using-cstring.md) , содержащий текст баннера подсказки, если он существует; в противном случае `CString` объект, который имеет нулевую длину.  
  
 -или-  
  
 Во второй перегрузке `true` Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Текст подсказки является приглашение, которое отображается в области ввода поля со списком. Текст подсказки отображается до ввода данных пользователем.  
  
 Этот метод отправляет [CB_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775843) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcursel"></a>CComboBox::GetCurSel  
 Вызовите эту функцию-член для определения выбранного элемента в поле со списком.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс текущего выделенного элемента в поле со списком, списка или **CB_ERR** , если элемент не выбран.  
  
### <a name="remarks"></a>Примечания  
 `GetCurSel`Возвращает индекс в списке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]  
  
##  <a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect  
 Вызовите `GetDroppedControlRect` функция-член для извлечения координаты на экране отображается (удалены) списка раскрывающемся поле со списком.  
  
```  
void GetDroppedControlRect(LPRECT lprect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lprect*  
 Указывает на [структура RECT](../../mfc/reference/rect-structure1.md) , предназначенный для получения координат.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox № 16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]  
  
##  <a name="getdroppedstate"></a>CComboBox::GetDroppedState  
 Вызовите `GetDroppedState` функцию-член, чтобы определить, является ли поле со списком в поле с раскрывающимся списком отображается (раскрыл).  
  
```  
BOOL GetDroppedState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если список является видимым. в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox 17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]  
  
##  <a name="getdroppedwidth"></a>CComboBox::GetDroppedWidth  
 Эта функция вызывается для получения минимального допустимого ширину в пикселях списка поля со списком.  
  
```  
int GetDroppedWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения Минимальная допустимая ширина в пикселях; в противном случае **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция применяется только для полей со списком [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиля.  
  
 По умолчанию минимальная ширина, допустимая раскрывающегося списка — 0. Минимальная допустимая ширина можно задать путем вызова [SetDroppedWidth](#setdroppedwidth). При отображении списков часть поле со списком его ширину больше Минимальная допустимая ширина или ширина поля со списком.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [SetDroppedWidth](#setdroppedwidth).  
  
##  <a name="geteditsel"></a>CComboBox::GetEditSel  
 Возвращает позиции символов начала и конца текущего выделенного фрагмента в элементе управления списком.  
  
```  
DWORD GetEditSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 32-разрядное значение, содержащий начальную позицию в младшее слово и позицию первого символа невыбранные после окончания выделенного текста в word высокого порядка. Если эта функция используется в поле со списком без элемент управления редактированием **CB_ERR** возвращается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox 18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]  
  
##  <a name="getextendedui"></a>CComboBox::GetExtendedUI  
 Вызовите `GetExtendedUI` функции-члена для определения, имеет ли поле со списком пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс.  
  
```  
BOOL GetExtendedUI() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поле со списком содержит расширенный пользовательский интерфейс; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Расширенный пользовательский интерфейс может быть идентифицирована одним из следующих способов.  
  
-   Щелкните статический элемент управления отображает список только для полей со списком [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиля.  
  
-   Нажмите клавишу Стрелка вниз отображает список (F4 отключен).  
  
 Если в списке элементов не является видимым (стрелка ключи отключены) прокрутки в статический элемент управления отключен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox 19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]  
  
##  <a name="gethorizontalextent"></a>CComboBox::GetHorizontalExtent  
 Извлекает поле со списком ширину в пикселях, по которым списков часть поле со списком может прокручиваться по горизонтали.  
  
```  
UINT GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прокручиваемые ширина списков части поле со списком в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Это применимо только в том случае, если часть со списком списков горизонтальной полосы прокрутки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox № 20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]  
  
##  <a name="getitemdata"></a>CComboBox::GetItemData  
 Извлекает значение предоставленного приложением 32-разрядной, связанное с указанным списком элементов.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс элемента в списке поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 32-разрядное значение, связанное с элементом, или **CB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 32-разрядное значение можно задать с помощью `dwItemData` параметр [SetItemData](#setitemdata) вызова функции-члена. Используйте `GetItemDataPtr` Если 32-разрядное значение, чтобы получить указатель функции-члена ( **void\***).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]  
  
##  <a name="getitemdataptr"></a>CComboBox::GetItemDataPtr  
 Возвращает значение 32-разрядных предоставляемую приложением, связанное с указанным списком элемент как указатель ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс элемента в списке поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлекает указатель или значение -1, если произошла ошибка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]  
  
##  <a name="getitemheight"></a>CComboBox::GetItemHeight  
 Вызовите `GetItemHeight` функция-член для извлечения высота элементов списка в поле со списком.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указывает компонент поле со списком имеет высоту которого требуется получить. Если `nIndex` параметр имеет значение -1, извлекается высоты элемента управления редактирования (или статического текста) часть поле со списком. Если поле со списком имеет [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) стиль `nIndex` указывает отсчитываемый от нуля индекс элемента списка, который имеет высоту которого требуется получить. В противном случае `nIndex` должно быть равно 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях указанного элемента в поле со списком. При возникновении ошибки возвращается значение **CB_ERR** .  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]  
  
##  <a name="getlbtext"></a>CComboBox::GetLBText  
 Получает строку из списка поля со списком.  
  
```  
int GetLBText(
    int nIndex,  
    LPTSTR lpszText) const;  
  
void GetLBText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс строки для копирования списков.  
  
 `lpszText`  
 Указывает на буфер, который принимает строку. Буфер должен иметь достаточно места для строки и знак завершения null.  
  
 `rString`  
 Ссылку на `CString`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки, за исключением завершающего символа null (в байтах). Если `nIndex` не указывает допустимый индекс, возвращаемым значением является **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Вторая форма этого элемента функция заливки `CString` вместе с текстом элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]  
  
##  <a name="getlbtextlen"></a>CComboBox::GetLBTextLen  
 Возвращает длину строки в списке поля со списком.  
  
```  
int GetLBTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс строки списков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки в байтах, за исключением завершающего символа null. Если `nIndex` не указывает допустимый индекс, возвращаемым значением является **CB_ERR**.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CComboBox::GetLBText](#getlbtext).  
  
##  <a name="getlocale"></a>CComboBox::GetLocale  
 Возвращает языковой стандарт, используемый в поле со списком.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение код (LCID) языка для строк, указанных в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Локаль используется, например, для определения порядка сортировки строк в отсортированном со списком.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CComboBox::SetLocale](#setlocale).  
  
##  <a name="getminvisible"></a>CComboBox::GetMinVisible  
 Получает минимальное количество видимых элементов в раскрывающемся списке текущего элемента управления поля со списком.  
  
```  
int GetMinVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальное число видимых элементов в текущем списке раскрывающегося списка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [CB_GETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettopindex"></a>CComboBox::GetTopIndex  
 Возвращает отсчитываемый от нуля индекс первой видимой позиции в списке части поле со списком.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первой видимой позиции в списке части поле со списком в случае успешного выполнения **CB_ERR** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Изначально элемент 0 находится в верхней части списка, но если прокрутить список, сверху может оказаться другой элемент.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]  
  
##  <a name="initstorage"></a>CComboBox::InitStorage  
 Выделяет память для хранения элементов списка в списке части поле со списком.  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `nItems`  
 Указывает количество элементов для добавления.  
  
 `nBytes`  
 Указывает объем памяти в байтах для выделения для элемента строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении максимальное количество элементов, списке часть поле со списком может хранить до перераспределение памяти требуется **CB_ERRSPACE**, доступен, то есть не хватает памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию перед добавлением большое количество элементов в списке часть `CComboBox`.  
  
 Windows 95/98 только: `wParam` ограничен 16-разрядных значений. Это означает, что списки не может содержать более 32 767 элементов. Несмотря на то, что количество элементов является ограниченным, общий размер элементов в поле со списком ограничен только объемом доступной памяти.  
  
 Эта функция помогает ускорить инициализации списка полей, имеющих большое количество элементов (более 100). Он предварительно размещает указанный объем памяти, поэтому последующие [AddString](#addstring), [InsertString](#insertstring), и [Dir](#dir) функции принимают кратчайшие сроки. Оценки можно использовать для параметров. Если вы пересмотреть, некоторые дополнительная память выделяется; Если стоит недооценивать, обычный распределение используется для элементов, которые превышают предварительно выделенной сумму.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]  
  
##  <a name="insertstring"></a>CComboBox::InsertString  
 Вставляет строку в список поля со списком.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс позиции в списке, в которую будет вставлена строка. Если этот параметр имеет значение -1, строка добавляется в конец списка.  
  
 `lpszString`  
 Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. При возникновении ошибки возвращается значение **CB_ERR** . Если для хранения новой строки недостаточно места, возвращается значение **CB_ERRSPACE** .  
  
### <a name="remarks"></a>Примечания  
 В отличие от [AddString](#addstring) функции-члена `InsertString` функции-члена не ведет список с [CBS_SORT](../../mfc/reference/combo-box-styles.md) стиль сортировки.  
  
> [!NOTE]
>  Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения в этом элементе управления см. в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]  
  
##  <a name="limittext"></a>CComboBox::LimitText  
 Ограничивает длину в байтах текст, который пользователь может ввести в элемент управления списком.  
  
```  
BOOL LimitText(int nMaxChars);
```  
  
### <a name="parameters"></a>Параметры  
 `nMaxChars`  
 Указывает длину (в байтах), пользователь может ввести текст. Если этот параметр равен 0, длина текста имеет значение 65 535 байт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успешного выполнения. При вызове для поля со списком в стиле [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) или списком без элемента управления, возвращается значение **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Если поле со списком имеет стиль [CBS_AUTOHSCROLL](../../mfc/reference/combo-box-styles.md), установленное которых превышает размер элемента управления редактирования текста не будет действовать.  
  
 `LimitText`ограничивает только текст, который пользователь может ввести. Он уже не влияет на любой текст в элементе управления при отправке сообщения, а также влияет на длину текста, скопировать элемент управления для редактирования при выборе строки в поле со списком.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]  
  
##  <a name="measureitem"></a>CComboBox::MeasureItem  
 Вызывается платформой при создании стиля рисования владельцем поле со списком.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMeasureItemStruct`  
 Длинный указатель [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования поле Windows размеры этого списка в поле со списком. Если поле со списком создается с [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) стиля, платформа вызывает эту функцию-член для каждого элемента в поле со списком. В противном случае этот член вызывается только один раз.  
  
 С помощью **CBS_OWNERDRAWFIXED** стиля в поле со списком рисуемый владельцем, созданных с помощью [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) функцию-член `CWnd` включает рекомендации по дальнейшей программирования. См. обсуждение в [Технические заметки 14](../../mfc/tn014-custom-controls.md).  
  
 В разделе [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) описание `MEASUREITEMSTRUCT` структуры.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]  
  
##  <a name="paste"></a>CComboBox::Paste  
 Вставляет данные из буфера обмена в поле редактирования комбинированного окна в текущей позиции курсора.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Примечания  
 Вставляются данные только в том случае, если в буфере обмена содержатся данные в **CF_TEXT** формат.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]  
  
##  <a name="resetcontent"></a>CComboBox::ResetContent  
 Удаляет все элементы из списка и измените элемент управления списком.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]  
  
##  <a name="selectstring"></a>CComboBox::SelectString  
 Выполняет поиск строки в списке поля со списком и если строка найдена, выбирает строки в окне списка и копирует его в поле редактирования.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartAfter`  
 Содержит отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает нижней части списка, он по-прежнему в верхней части списка обратно элемент с указанным `nStartAfter`. Если значение-1, весь список выполняется поиск с начала.  
  
 `lpszString`  
 Указывает на строку, завершающуюся значением null, содержащая префикс для поиска. Поиск ситуация независимые, поэтому эта строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс выбранного элемента, если строка была найдена. Если поиск завершилась неудачно, возвращается **CB_ERR** и текущего выделения не изменяется.  
  
### <a name="remarks"></a>Примечания  
 Строка выбирается только в том случае, если его начальные символы (от начальной) совпадать с символами в строке префикса.  
  
 Обратите внимание, что `SelectString` и `FindString` функции-члены обоих поиска строки, но `SelectString` функция-член также выделяет строку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]  
  
##  <a name="setcuebanner"></a>CComboBox::SetCueBanner  
 Задает текст подсказки, отображаемый для элемента управления поля со списком.  
  
```  
BOOL SetCueBanner(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] *lpszText*|Указатель на буфер, содержащий текст подсказки завершающуюся значением null.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод выполнен успешно; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Текст подсказки является приглашение, которое отображается в области ввода поля со списком. Текст подсказки отображается до ввода данных пользователем.  
  
 Этот метод отправляет [CB_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775897) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_combobox`, который используется для программного доступа к поле со списком. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается баннер подсказки для элемента управления полем со списком.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="setcursel"></a>CComboBox::SetCurSel  
 Выбирает строку в списке поля со списком.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Параметры  
 `nSelect`  
 Задает отсчитываемый от нуля индекс строки для выбора. Если значение-1, любое текущее выделение в поле со списком удаляется и очищается поле редактирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента, выбранного при успешном выполнении сообщения. Возвращает значение **CB_ERR** Если `nSelect` больше, чем число элементов в списке или, если `nSelect` имеет значение -1, который отменяет выделение.  
  
### <a name="remarks"></a>Примечания  
 При необходимости списке прокрутке строке (если в списке отображается). Текст в поле редактирования комбинированного окна изменяется, чтобы отразить новое выделение. Предыдущее выделение в поле со списком удаляется.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]  
  
##  <a name="setdroppedwidth"></a>CComboBox::SetDroppedWidth  
 Вызывайте эту функцию, чтобы задать минимальную допустимую ширину в пикселях списка поля со списком.  
  
```  
int SetDroppedWidth(UINT nWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `nWidth`  
 Минимальная ширина допустимый списков части поле со списком в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, новая ширина списка поле, в противном случае **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция применяется только для полей со списком [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиля.  
  
 По умолчанию минимальная ширина, допустимая раскрывающегося списка — 0. При отображении списков часть поле со списком его ширину больше Минимальная допустимая ширина или ширина поля со списком.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]  
  
##  <a name="seteditsel"></a>CComboBox::SetEditSel  
 Выбирает символов в элементе управления списком.  
  
```  
BOOL SetEditSel(
    int nStartChar,  
    int nEndChar);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartChar`  
 Указывает начальную позицию. Если начальная позиция имеет значение -1, удаляется любого существующего выделения.  
  
 `nEndChar`  
 Указывает конечную позицию. Если конечная позиция имеет значение -1, затем весь текст от начальной позиции до конца выбирается символ в поле редактирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция-член прошла успешно; в противном случае — 0. Это **CB_ERR** Если `CComboBox` имеет [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиля или не имеет поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Позиции отсчитываются от нуля. Чтобы выбрать первый символ элемента управления, указать начальную позицию 0. Конечная позиция — для символа сразу после последнего символа для выбора. Например чтобы выбрать первые четыре символа элемента управления, используется начальная позиция 0 и конечного 4.  
  
> [!NOTE]
>  Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения в этом элементе управления см. в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CComboBox::GetEditSel](#geteditsel).  
  
##  <a name="setextendedui"></a>CComboBox::SetExtendedUI  
 Вызовите `SetExtendedUI` функции-члена для выбора по умолчанию пользовательский интерфейс или расширенный пользовательский интерфейс поле со списком, который имеет [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиля.  
  
```  
int SetExtendedUI(BOOL bExtended = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bExtended*  
 Указывает, следует ли использовать поле со списком, расширенный пользовательский интерфейс или пользовательского интерфейса по умолчанию. Значение **TRUE** выбирает расширенного пользовательского интерфейса; значение **FALSE** выбирает стандартный пользовательский интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CB_OKAY** , если операция выполнена успешно, или **CB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Расширенный пользовательский интерфейс может быть идентифицирована одним из следующих способов.  
  
-   Щелкните статический элемент управления отображает список только для полей со списком **CBS_DROPDOWNLIST** стиля.  
  
-   Нажмите клавишу Стрелка вниз отображает список (F4 отключен).  
  
 Прокрутка в статический элемент управления остается недоступной, если не отображается в списке элементов (отключены клавиши со стрелками).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CComboBox::GetExtendedUI](#getextendedui).  
  
##  <a name="sethorizontalextent"></a>CComboBox::SetHorizontalExtent  
 Задает ширину в пикселях, на которое списков часть поле со списком может прокручиваться по горизонтали.  
  
```  
void SetHorizontalExtent(UINT nExtent);
```  
  
### <a name="parameters"></a>Параметры  
 *nExtent*  
 Задает количество пикселей, на которое списков часть поле со списком может прокручиваться по горизонтали.  
  
### <a name="remarks"></a>Примечания  
 Если ширина поля меньше, чем это значение, горизонтальная полоса прокрутки по горизонтали прокручивает элементы в поле со списком. Если ширина списка равно или больше, чем это значение, горизонтальная полоса прокрутки будет скрыта или, если поле со списком имеет [CBS_DISABLENOSCROLL](../../mfc/reference/combo-box-styles.md) стиля, отключен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]  
  
##  <a name="setitemdata"></a>CComboBox::SetItemData  
 Задает 32-разрядное значение, связанное с указанным элементом в поле со списком.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс задаваемого элемента.  
  
 `dwItemData`  
 Содержит новое значение, связанное с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте `SetItemDataPtr` Если 32-разрядных элемент должен быть указателем функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]  
  
##  <a name="setitemdataptr"></a>CComboBox::SetItemDataPtr  
 Задает 32-разрядное значение, связанное с указанным элементом в поле со списком указанный указатель ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс изменяемого элемента.  
  
 `pData`  
 Содержит указатель, связываемый с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель остается допустимым в течение жизненного цикла поле со списком, несмотря на то, что относительное положение данного элемента в поле со списком может измениться при добавлении и удалении элементов. Таким образом индекс элемента в поле можно изменить, но указатель остается надежным.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]  
  
##  <a name="setitemheight"></a>CComboBox::SetItemHeight  
 Вызовите `SetItemHeight` функции-члена для задайте высоту элементов списка в поле со списком или высота элемента управления редактирования (или статического текста) часть со списком.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указывает, задан ли высота элементов списка или высоту элемента управления редактирования (или статического текста) части поле со списком.  
  
 Если поле со списком имеет [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) стиля, `nIndex` указывает отсчитываемый от нуля индекс, высоту которого будет задано; в противном случае — элемент списка `nIndex` должно быть 0 и высоту список всех элементов будет значение.  
  
 Если `nIndex` является -1, высота элемента управления редактирования или часть статического текста в поле со списком задать.  
  
 `cyItemHeight`  
 Указывает высоту в пикселях компонент списком `nIndex`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CB_ERR** Если индекс или высоту недопустим; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Высота элемента управления редактирования (или статического текста) часть поле со списком устанавливается независимо от высоты элементов списка. Приложения необходимо убедиться, что высота этой части элемента управления редактирования (или статического текста) не меньше, чем высота элемента определенного списка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]  
  
##  <a name="setlocale"></a>CComboBox::SetLocale  
 Задает идентификатор языкового стандарта для этого поля со списком.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewLocale`  
 Новое значение код (LCID) языка должно быть задано для поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение языкового стандарта код (LCID) для этого поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Если **SetLocale** не вызывается, значение по умолчанию языковой стандарт, полученной из системы. Этот язык системы по умолчанию можно изменить с помощью панели управления язык (или международной) приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]  
  
##  <a name="setminvisibleitems"></a>CComboBox::SetMinVisibleItems  
 Задает минимальное число видимых элементов в раскрывающемся списке текущего поля со списком.  
  
```  
BOOL SetMinVisibleItems(int iMinVisible);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iMinVisible`|Указывает минимальное число видимых элементов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [CB_SETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_combobox`, который используется для программного доступа к поле со списком. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода вставляет 20 элементов в раскрывающемся списке элемента управления полем со списком. Затем он задает отображение менее 10 элементов при нажатии клавиши со стрелкой раскрывающегося списка.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="settopindex"></a>CComboBox::SetTopIndex  
 Гарантирует, что какой-либо элемент отображается в списке части поле со списком.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ноль при успешном завершении, или **CB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Система выполняет прокрутку списка до элемента, заданного параметром `nIndex` отображается в верхней части списка достигнут диапазона максимальную прокрутку или поля.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox #40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]  
  
##  <a name="showdropdown"></a>CComboBox::ShowDropDown  
 Показывает или скрывает поле со списком поле со списком, который имеет [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиля.  
  
```  
void ShowDropDown(BOOL bShowIt = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bShowIt*  
 Указывает, является ли поле раскрывающегося списка отображаться или скрываться. Значение **TRUE** показывает поле списка. Значение **FALSE** скрывает поле списка.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию поле со списком этого стиля будет показывать окно списка.  
  
 Эта функция-член не оказывает влияния на поле со списком, созданных с помощью [CBS_SIMPLE](../../mfc/reference/combo-box-styles.md) стиля.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CComboBox::GetDroppedState](#getdroppedstate).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)   
 [Класс CStatic](../../mfc/reference/cstatic-class.md)   
 [Класс CDialog](../../mfc/reference/cdialog-class.md)

