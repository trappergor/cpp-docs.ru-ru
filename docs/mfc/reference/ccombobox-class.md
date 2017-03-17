---
title: "CComboBox-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5328c245e0d662c4701042b37c16870d6b1e33c7
ms.lasthandoff: 02/24/2017

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
|[CComboBox::AddString](#addstring)|Добавляет строку в конец списка в поле со списком, списком или позиции отсортированных списков с **CBS_SORT** стиль.|  
|[CComboBox::Clear](#clear)|Удаляет (очистка) выделенной области, если в элементе управления.|  
|[CComboBox::CompareItem](#compareitem)|Вызывается платформой для определения относительной позиции элемента списка в отсортированном определяемые владельцем со списком.|  
|[CComboBox::Copy](#copy)|Копирует текущее выделение в том случае, если таковая имеется, в буфер обмена в **CF_TEXT** формат.|  
|[CComboBox::Create](#create)|Создает поле со списком и присоединяет его к `CComboBox` объекта.|  
|[CComboBox::Cut](#cut)|Удаляет (сокращает) выделенного элемента, если какие-либо, в меню Правка управления и копирует удаленный текст в буфер обмена в **CF_TEXT** формат.|  
|[CComboBox::DeleteItem](#deleteitem)|Вызывается инфраструктурой при удалении элемента списка из определяемого владельцем списком.|  
|[CComboBox::DeleteString](#deletestring)|Удаляет строку из списка поля со списком.|  
|[CComboBox::Dir](#dir)|Добавляет список имен файлов в списке поле со списком.|  
|[CComboBox::DrawItem](#drawitem)|Вызывается инфраструктурой при изменении внешнего вида, поле со списком, определяемые владельцем изменений.|  
|[CComboBox::FindString](#findstring)|Выполняет поиск первой строки, которая содержит указанный префикс в поле со списком списком.|  
|[CComboBox::FindStringExact](#findstringexact)|Находит первый списка строку (в поле со списком), совпадающий с указанной строкой.|  
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Получает сведения о `CComboBox` объекта.|  
|[CComboBox::GetCount](#getcount)|Получает число элементов в списке поля со списком.|  
|[CComboBox::GetCueBanner](#getcuebanner)|Возвращает текст подсказки, который отображается для элемента управления поля со списком.|  
|[CComboBox::GetCurSel](#getcursel)|Извлекает индекс текущего выделенного элемента, если в списке поля со списком.|  
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Возвращает координаты на экране отображается (отброшенных вниз) списка раскрывающемся поле со списком.|  
|[CComboBox::GetDroppedState](#getdroppedstate)|Определяет, является ли поле со списком раскрывающемся поле со списком отображается (выстроены).|  
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Получает минимальное ширины для части раскрывающегося списка в поле со списком.|  
|[CComboBox::GetEditSel](#geteditsel)|Возвращает начальное и конечное положения символа текущее выделение в элементе управления списком.|  
|[CComboBox::GetExtendedUI](#getextendedui)|Определяет, имеет ли поле со списком пользовательского интерфейса по умолчанию или расширенный пользовательский интерфейс.|  
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Возвращает ширину в пикселях, что части списка в поле со списком может прокручиваться по горизонтали.|  
|[CComboBox::GetItemData](#getitemdata)|Возвращает значение 32-разрядных предоставляемый приложением, связанное с указанным списком элементов.|  
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Получает 32-разрядного указателя предоставляемый приложением, который связан с указанным списком элементов.|  
|[CComboBox::GetItemHeight](#getitemheight)|Получает высоту элементов списка в поле со списком.|  
|[CComboBox::GetLBText](#getlbtext)|Возвращает строку, в раскрывающемся списке поля со списком.|  
|[CComboBox::GetLBTextLen](#getlbtextlen)|Возвращает длину строки в списке поля со списком.|  
|[CComboBox::GetLocale](#getlocale)|Извлекает идентификатор языкового стандарта для поля со списком.|  
|[CComboBox::GetMinVisible](#getminvisible)|Возвращает минимальное количество видимых элементов в раскрывающемся списке текущего поля со списком.|  
|[CComboBox::GetTopIndex](#gettopindex)|Возвращает индекс первой видимой позиции в части списка в поле со списком.|  
|[CComboBox::InitStorage](#initstorage)|Выделит место для блоков памяти для элементов и строк в части списка в поле со списком.|  
|[CComboBox::InsertString](#insertstring)|Вставляет строку в список поля со списком.|  
|[CComboBox::LimitText](#limittext)|Ограничивает длину текста, который пользователь может ввести в элемент управления списком.|  
|[CComboBox::MeasureItem](#measureitem)|Вызывается платформой для определения измерения поле со списком при создании определяемого владельцем списком.|  
|[CComboBox::Paste](#paste)|Вставляет данные из буфера обмена в элемент управления, расположенный в текущей позиции курсора. Данные вставляются только в том случае, если в буфере обмена содержатся данные в **CF_TEXT** формат.|  
|[CComboBox::ResetContent](#resetcontent)|Удаляет все элементы из списка и измените элемент управления списком.|  
|[CComboBox::SelectString](#selectstring)|Выполняет поиск строки в списке поля со списком и, если строка найдена, выбирает строки в поле со списком и копирует строки в элемент управления для редактирования.|  
|[CComboBox::SetCueBanner](#setcuebanner)|Задает текст подсказки, отображаемый для поля со списком.|  
|[CComboBox::SetCurSel](#setcursel)|Выбирает строки в списке поля со списком.|  
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Задает минимальное количество ширины для части раскрывающегося списка в поле со списком.|  
|[CComboBox::SetEditSel](#seteditsel)|Выбирает символы в элементе управления списком.|  
|[CComboBox::SetExtendedUI](#setextendedui)|Выбирает пользовательского интерфейса по умолчанию или расширенной пользовательский интерфейс для поля со списком, которое имеет **CBS_DROPDOWN** или **CBS_DROPDOWNLIST** стиль.|  
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Задает ширину в пикселях, что части списка в поле со списком может прокручиваться по горизонтали.|  
|[CComboBox::SetItemData](#setitemdata)|Задает 32-разрядное значение, связанное с указанного элемента в поле со списком.|  
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Задает 32-разрядный указатель, связанный с указанного элемента в поле со списком.|  
|[CComboBox::SetItemHeight](#setitemheight)|Задает высоту элементов списка в поле со списком или высоту управления редактированием (или статического текста) части поля со списком.|  
|[CComboBox::SetLocale](#setlocale)|Задает идентификатор языкового стандарта для поля со списком.|  
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Задает минимальное число видимых элементов в раскрывающемся списке текущего поля со списком.|  
|[CComboBox::SetTopIndex](#settopindex)|Указывает части списка в поле со списком для отображения элемента с указанным индексом в верхней.|  
|[CComboBox::ShowDropDown](#showdropdown)|Показывает или скрывает список со списком **CBS_DROPDOWN** или **CBS_DROPDOWNLIST** стиль.|  
  
## <a name="remarks"></a>Примечания  
 Поле со списком состоит из списка, в сочетании с статический элемент управления или элемент управления. Части списка элемента управления может отображаться все время, или может только раскрывающийся список, когда пользователь выбирает стрелку раскрывающегося списка рядом с элементом управления.  
  
 Текущего выделенного элемента (если таковые имеются) в поле со списком отображается в статическом или элемент управления. Кроме того Если поле со списком имеет стиль раскрывающегося списка, пользователь может ввести буквы одного из элементов в списке и списка, если она видна, выделит следующего элемента с этого начального знака.  
  
 В следующей таблице сравниваются три списком [стили](../../mfc/reference/combo-box-styles.md).  
  
|Стиль|Если отображается список|Статический метод или изменить элемент управления|  
|-----------|-------------------------------|-----------------------------|  
|Простая|Всегда|Правка|  
|Drop-down|При удалении|Правка|  
|Раскрывающийся список|При удалении|Static|  
  
 Можно создать `CComboBox` объекта из шаблона диалогового окна или непосредственно в коде. В обоих случаях сначала вызовите конструктор `CComboBox` для создания `CComboBox` объекта, затем вызовите [создать](#create) функции-члена для создания элемента управления и присоединить его к `CComboBox` объекта.  
  
 Если требуется обрабатывать сообщения уведомления Windows, отправляемые поле со списком с родительским (обычно класс, производный от `CDialog`), добавление карты сообщение входа и обработчик сообщений функции-члена родительский класс для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 **ON_**Notification **(**`id`**,**`memberFxn`**)**  
  
 где `id` указывает идентификатор дочернего окна элемента управления списком, отправку уведомления, и `memberFxn` имя родительской функции члена, написанный для обработки уведомления.  
  
 Прототип функции родительского выглядит следующим образом:  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 Невозможно предсказать порядок, в котором некоторые уведомления будут отправляться. В частности **CBN_SELCHANGE** уведомление может возникнуть до или после **CBN_CLOSEUP** уведомления.  
  
 Ниже перечислены схемы сообщений записей.  
  
- **ON_CBN_CLOSEUP** (Windows 3.1 или более поздней версии.) В списке поле со списком он закрыт. Это не отправляется уведомление для поля со списком, которое имеет [CBS_SIMPLE](../../mfc/reference/combo-box-styles.md) стиль.  
  
- **ON_CBN_DBLCLK** пользователь дважды щелкает строку в списке поля со списком. Это уведомление отправляется только в поле со списком **CBS_SIMPLE** стиль. Для поля со списком с [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиля, двойным щелчком не может произойти из-за одним щелчком скрывает поле списка.  
  
- **ON_CBN_DROPDOWN** списке списком — раскрывающийся список (виден). Это уведомление может возникать только в поле со списком **CBS_DROPDOWN** или **CBS_DROPDOWNLIST** стиль.  
  
- **ON_CBN_EDITCHANGE** пользователя вступила в действие, которое может изменить текст в части управления редактированием в поле со списком. В отличие от **CBN_EDITUPDATE** , это сообщение будет отправлено после обновления экрана в Windows. Она не отправляется, если поле со списком **CBS_DROPDOWNLIST** стиль.  
  
- **ON_CBN_EDITUPDATE** управления редактированием часть со списком собирается отобразить измененный текст. Это уведомление отправляется после форматирования текста элемента управления, но до отображения текста. Она не отправляется, если поле со списком **CBS_DROPDOWNLIST** стиль.  
  
- **ON_CBN_ERRSPACE** поле со списком не удается выделить достаточно памяти для выполнения конкретного запроса.  
  
- **ON_CBN_SELENDCANCEL** (Windows 3.1 или более поздней версии.) Указывает, что следует отменить выбор пользователя. Пользователь щелкает элемент и затем нажимает другого окна или элемента управления, чтобы скрыть список поле со списком. Это уведомление отправляется перед **CBN_CLOSEUP** сообщение уведомления, чтобы указать, игнорирование выбора пользователя. **CBN_SELENDCANCEL** или **CBN_SELENDOK** отправляется уведомление даже в том случае, если **CBN_CLOSEUP** не отправляется уведомление (как в случае в поле со списком **CBS_SIMPLE** стиль).  
  
- **ON_CBN_SELENDOK** пользователь выбирает элемент и затем нажимает клавишу ВВОД или нажимает КЛАВИШУ стрелка вниз для скрытия списка поля со списком. Это уведомление отправляется перед **CBN_CLOSEUP** сообщение, чтобы указать, что выбор пользователя должно считаться допустимым. **CBN_SELENDCANCEL** или **CBN_SELENDOK** отправляется уведомление даже в том случае, если **CBN_CLOSEUP** не отправляется уведомление (как в случае в поле со списком **CBS_SIMPLE** стиль).  
  
- **ON_CBN_KILLFOCUS** поле со списком теряет фокус ввода.  
  
- **ON_CBN_SELCHANGE** выбора в поле со списком списком — изменено в результате пользователь, щелкнув в поле со списком или изменение выделения с помощью клавиш со стрелками. При обработке этого сообщения, текст в элементе управления списком можно получить только через `GetLBText` или другой аналогичный функции. `GetWindowText`нельзя использовать.  
  
- **ON_CBN_SETFOCUS** поле со списком получает фокус ввода.  
  
 При создании `CComboBox` объекта в диалоговое окно (с помощью ресурса диалогового окна), `CComboBox` объект автоматически уничтожается, когда пользователь закрывает окно.  
  
 При внедрении `CComboBox` объект в другом окне объекта, необходимо уничтожить его. При создании `CComboBox` объекта в стеке удаляется автоматически. При создании `CComboBox` объектов в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы оно уничтожается при уничтожении поле со списком Windows.  
  
 **Примечание** Если вы хотите обрабатывать `WM_KEYDOWN` и `WM_CHAR` сообщений, необходимо подкласс списком изменять и список элементов управления, создавать производные классы от `CEdit` и `CListBox`, и добавьте обработчики для этих сообщений в производных классах. Дополнительные сведения см. в разделе [http://support.microsoft.com/default.aspxscid=kb;en-us; Q174667](http://support.microsoft.com/default.aspxscid=kb;en-us;q174667) и [CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="addstring"></a>CComboBox::AddString  
 Добавляет строку к окну списка поля со списком.  
  
```  
int AddString(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszString`  
 Указывает на строку символом null, должен быть добавлен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение больше или равно 0, это отсчитываемый от нуля индекс строки в списке. Возвращаемое значение является **CB_ERR** ; при возникновении ошибки возвращается **CB_ERRSPACE** Если недостаточно места для сохранения новой строки.  
  
### <a name="remarks"></a>Примечания  
 Если в списке не был создан с [CBS_SORT](../../mfc/reference/combo-box-styles.md) стиль, строка добавляется в конец списка. В противном случае — строка вставляется в списке, и список отсортирован.  
  
> [!NOTE]
>  Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения для этого элемента управления в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Чтобы вставить строку в определенное место в списке, используйте [InsertString](#insertstring) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#3;](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]  
  
##  <a name="ccombobox"></a>CComboBox::CComboBox  
 Создает объект `CComboBox`.  
  
```  
CComboBox();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#1;](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]  
  
##  <a name="clear"></a>CComboBox::Clear  
 Удаляет (очистка) выделенной области, если в элементе управления списком.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы удалить текущее выделение и поместите удаленные содержимое в буфер обмена, используйте [Вырезать](#cut) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#4;](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CComboBox::CompareItem  
 Вызывается средой, чтобы определить относительное положение элемента в списке части списком отсортированный рисование владельцем.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpCompareItemStruct`  
 Длинный указатель [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает относительную позицию двух элементов, описанных в `COMPAREITEMSTRUCT` структуру. Может принимать одно из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|– 1|Сортирует элемент 1 до 2 элемента.|  
|0|1 и 2 элемент сортировки же.|  
|1|Сортирует элемент 1 после элемента 2.|  
  
 В разделе [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) описание `COMPAREITEMSTRUCT`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. При создании поле со списком рисование владельцем **LBS_SORT** стиль, необходимо переопределить эту функцию-член для платформы сортировка новые элементы, добавленные в список.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#5;](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]  
  
##  <a name="copy"></a>CComboBox::Copy  
 Копирует текущее выделение в том случае, если в поле редактирования в буфер обмена в поле со списком **CF_TEXT** формат.  
  
```  
void Copy();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox №&6;](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]  
  
##  <a name="create"></a>CComboBox::Create  
 Создает поле со списком и присоединяет его к `CComboBox` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль поля со списком. Примените любое сочетание [поле со списком стили](../../mfc/reference/combo-box-styles.md) в поле.  
  
 `rect`  
 Указывает положение и размер поля со списком. Может быть [структура RECT](../../mfc/reference/rect-structure1.md) или `CRect` объекта.  
  
 `pParentWnd`  
 Указывает поле со списком родительского окна (обычно `CDialog`). Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CComboBox` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает поле со списком Windows и присоединяет его к `CComboBox` объекта.  
  
 Когда **создать** выполняет Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщений в поле со списком.  
  
 Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CComboBox`, Добавление нового класса схемы сообщений и переопределить выше функции-члены обработчик сообщений. Переопределение `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Примените следующий [стили окна](../../mfc/reference/window-styles.md) к элементу управления списком. :  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_VSCROLL** для добавления вертикальной прокрутки для списка в поле со списком  
  
- **WS_HSCROLL** для добавления горизонтальной прокрутки для списка в поле со списком  
  
- **WS_GROUP** для группирования элементов управления  
  
- **WS_TABSTOP** для включения в порядок следования поле со списком  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#2;](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]  
  
##  <a name="cut"></a>CComboBox::Cut  
 Удаляет (сокращает) выделенного элемента, если имеется, в поле со списком изменение управления и копирует удаленный текст в буфер обмена в **CF_TEXT** формат.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы удалить текущее выделение без помещения удаленный текст в буфер обмена, вызовите [снимите](#clear) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#7;](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]  
  
##  <a name="deleteitem"></a>CComboBox::DeleteItem  
 Вызывается платформой, когда пользователь удаляет элемент из рисование владельцем `CComboBox` объекта или удаляет поле со списком.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDeleteItemStruct`  
 Длинный указатель Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) структуру, содержащую сведения о удаляемого элемента. В разделе [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) описание этой структуры.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию, чтобы обновить поле со списком при необходимости.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox №&8;](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]  
  
##  <a name="deletestring"></a>CComboBox::DeleteString  
 Удаляет элемент в позиции `nIndex` поле со списком.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указывает индекс строки, который требуется удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение больше или равно 0, является число строк, оставшихся в списке. Возвращаемое значение является **CB_ERR** Если `nIndex` указывает индекс больше числа элементов в списке.  
  
### <a name="remarks"></a>Примечания  
 Все элементы `nIndex` теперь вниз на одну позицию. Например если поле со списком содержит два элемента, удаление первого элемента приведет оставшиеся элемента: теперь в первой позиции. `nIndex`=&0; в позиции первого элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox №&9;](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]  
  
##  <a name="dir"></a>CComboBox::Dir  
 Добавляет список имен файлов или дисков в списке поле со списком.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Параметры  
 `attr`  
 Может быть любым сочетанием `enum` значения описано в [CFile::GetStatus](../../mfc/reference/cfile-class.md#getstatus) или любое сочетание следующих значений:  
  
- **DDL_READWRITE** файл для чтения и записи.  
  
- **DDL_READONLY** файл можно считывать, но не записываются.  
  
- **DDL_HIDDEN** файл является скрытым и не отображается в каталоге.  
  
- **DDL_SYSTEM** файл является системным файлом.  
  
- **DDL_DIRECTORY** имя, указанное в `lpszWildCard` указывает каталог.  
  
- **DDL_ARCHIVE** файл заархивирован.  
  
- **DDL_DRIVES** относятся все диски, которые соответствуют имени, заданному в `lpszWildCard`.  
  
- **DDL_EXCLUSIVE** флаг Exclusive. Если флаг exclusive перечислены только файлы указанного типа. В противном случае — помимо файлов «normal» отображаются файлы указанного типа.  
  
 `lpszWildCard`  
 Указывает строку спецификация файла. Строка может содержать подстановочные знаки (например, *.\*).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение больше или равно 0, это отсчитываемый от нуля индекс последнего имени файла добавляется в список. Возвращаемое значение является **CB_ERR** ; при возникновении ошибки возвращается **CB_ERRSPACE** Если недостаточно места для хранения новых строк.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения для этого элемента управления в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#10;](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]  
  
##  <a name="drawitem"></a>CComboBox::DrawItem  
 Вызывается инфраструктурой при изменении поля со списком рисование владельцем внешнего вида.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено. В разделе [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) описание этой структуры.  
  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член для реализации отрисовки рисование владельцем `CComboBox` объекта. Прежде чем завершает эта функция-член, приложение следует восстановить всех графических устройств интерфейс (GDI) выбранных объектов в контексте отображения указано в `lpDrawItemStruct`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&11;](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]  
  
##  <a name="findstring"></a>CComboBox::FindString  
 Находит, но не выделяет первой строки, которая содержит указанный префикс в поле со списком списком.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszString) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nStartAfter`  
 Содержит отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает конца списка, он продолжает в верхней части списка обратно элемента, заданного параметром `nStartAfter`. Если значение –&1;, всего списка выполняется с самого начала.  
  
 `lpszString`  
 Указывает нулем строка, содержащая префикс для поиска. Поиск ситуация независимые, поэтому эта строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение больше или равно 0, это отсчитываемый от нуля индекс элемента сопоставления. Это **CB_ERR** , если не удалось выполнить поиск.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения для этого элемента управления в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#12;](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]  
  
##  <a name="findstringexact"></a>CComboBox::FindStringExact  
 Вызов `FindStringExact` для поиска первого списка строки (в поле со списком), соответствующая строка, указанная в функции-члена `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndexStart`  
 Задает отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает конца списка, он продолжает в верхней части списка обратно элемента, заданного параметром `nIndexStart`. Если `nIndexStart` –&1;, весь список просматривается с самого начала.  
  
 `lpszFind`  
 Указывает на строку, завершающуюся значением null для поиска. Эта строка может содержать полное имя файла, включая расширение. Поиск не чувствителен к регистру, поэтому эта строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента сопоставления или **CB_ERR** , если не удалось выполнить поиск.  
  
### <a name="remarks"></a>Примечания  
 Если поле со списком была создана с стиль рисования владельцем, но без [CBS_HASSTRINGS](../../mfc/reference/combo-box-styles.md) стиль, `FindStringExact` пытается сопоставить двойное значение со значением `lpszFind`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#13;](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]  
  
##  <a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo  
 Возвращает сведения о `CComboBox` объекта.  
  
```  
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pcbi*  
 Указатель на [COMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775798) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [CB_GETCOMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775839) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcount"></a>CComboBox::GetCount  
 Вызовите эту функцию-член для получения количества элементов в части списка в поле со списком.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов. Количество возвращаемых результатов, больше, чем значение индекса последнего элемента (индекс начинается с нуля). Это **CB_ERR** при возникновении ошибки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#14;](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]  
  
##  <a name="getcuebanner"></a>CComboBox::GetCueBanner  
 Возвращает текст подсказки, который отображается для элемента управления поля со списком.  
  
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
 В первой перегрузке [CString](../../atl-mfc-shared/using-cstring.md) , содержащий текст баннера подсказки, если он существует; в противном случае — `CString` объект, который имеет нулевую длину.  
  
 -или-  
  
 Во второй перегрузке `true` Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Текст подсказки — строки, который отображается в области ввода поля со списком. Текст подсказки отображается до ввода данных пользователем.  
  
 Этот метод отправляет [CB_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775843) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcursel"></a>CComboBox::GetCurSel  
 Вызовите эту функцию-член для определения выбранного элемента в поле со списком.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс текущего выделенного элемента в поле со списком, список или **CB_ERR** , если элемент не выбран.  
  
### <a name="remarks"></a>Примечания  
 `GetCurSel`Возвращает индекс в списке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#15;](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]  
  
##  <a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect  
 Вызов `GetDroppedControlRect` функции-члена для получения координаты на экране отображается (Удалить) списка раскрывающемся поле со списком.  
  
```  
void GetDroppedControlRect(LPRECT lprect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lprect*  
 Указывает [структура RECT](../../mfc/reference/rect-structure1.md) , предназначенный для получения координаты.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox №&16;](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]  
  
##  <a name="getdroppedstate"></a>CComboBox::GetDroppedState  
 Вызов `GetDroppedState` функцию-член, чтобы определить, является ли поле со списком раскрывающемся поле со списком отображается (выстроены).  
  
```  
BOOL GetDroppedState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если список является видимым. в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&17;](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]  
  
##  <a name="getdroppedwidth"></a>CComboBox::GetDroppedWidth  
 Эта функция вызывается для получения минимальную ширину допустимый, в пикселях, списка, поля со списком.  
  
```  
int GetDroppedWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха, Минимальная допустимая ширина в точках; в противном случае — **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция применяется только для полей со списком [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиль.  
  
 По умолчанию минимальная ширина допустимый раскрывающегося списка — 0. Минимальная допустимая ширина можно задать путем вызова [SetDroppedWidth](#setdroppedwidth). При отображении части списка в поле со списком его ширину больше Минимальная допустимая ширина или ширина поля со списком.  
  
### <a name="example"></a>Пример  
  В примере показано [SetDroppedWidth](#setdroppedwidth).  
  
##  <a name="geteditsel"></a>CComboBox::GetEditSel  
 Возвращает начальное и конечное положения символа текущее выделение в элементе управления списком.  
  
```  
DWORD GetEditSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 32-разрядное значение, содержащее начальную позицию в младшее слово и позиция первого знака невыбранные после конец выделения в старшее слово. Если эта функция используется в поле со списком без ввода, **CB_ERR** возвращается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&18;](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]  
  
##  <a name="getextendedui"></a>CComboBox::GetExtendedUI  
 Вызов `GetExtendedUI` функции-члена для определения, имеет ли поле со списком пользовательского интерфейса по умолчанию или расширенный пользовательский интерфейс.  
  
```  
BOOL GetExtendedUI() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поле со списком содержит расширенный пользовательский интерфейс; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Расширенный пользовательский интерфейс может быть идентифицирована одним из следующих способов.  
  
-   Щелкните статический элемент управления отображает список только для полей со списком [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиль.  
  
-   Нажмите клавишу Стрелка вниз отображает список (F4 отключена).  
  
 Если список элементов не является видимым (стрелка ключей отключены) прокрутки в элементе управления статический отключен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&19;](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]  
  
##  <a name="gethorizontalextent"></a>CComboBox::GetHorizontalExtent  
 Получает ширину в пикселях, на которое части списка в поле со списком может прокручиваться по горизонтали в поле со списком.  
  
```  
UINT GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина прокрутки части списка в поле со списком в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Это применимо только в том случае, если части списка в поле со списком горизонтальной полосы прокрутки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&20;](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]  
  
##  <a name="getitemdata"></a>CComboBox::GetItemData  
 Возвращает значение 32-разрядных предоставляемый приложением, связанное с указанным списком элементов.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс элемента в списке поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 32-разрядное значение, связанное с элементом, или **CB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 32-разрядное значение можно задать с помощью `dwItemData` параметр [SetItemData](#setitemdata) вызова функции-члена. Используйте `GetItemDataPtr` Если 32-разрядное значение, чтобы получить указатель функции-члена ( **void\***).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#21;](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]  
  
##  <a name="getitemdataptr"></a>CComboBox::GetItemDataPtr  
 Возвращает значение 32-разрядных предоставляемый приложением, связанное с указанным списком элемент как указатель ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс элемента в списке поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлекает указатель или значение -1, если произошла ошибка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#22;](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]  
  
##  <a name="getitemheight"></a>CComboBox::GetItemHeight  
 Вызов `GetItemHeight` функции-члена для получения высоты элементов списка в поле со списком.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указывает компонент поле со списком, высота которой требуется извлечь. Если `nIndex` параметр –&1;, получить высоту части управления редактированием (или статического текста) в поле со списком. Если поле со списком [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) стиль `nIndex` задает отсчитываемый от нуля индекс элемента списка, высота которой требуется извлечь. В противном случае — `nIndex` должно быть равным 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях указанного элемента в поле со списком. При возникновении ошибки возвращается значение **CB_ERR** .  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#23;](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]  
  
##  <a name="getlbtext"></a>CComboBox::GetLBText  
 Возвращает строку, в раскрывающемся списке поля со списком.  
  
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
 Содержит отсчитываемый от нуля индекс списка строки для копирования.  
  
 `lpszText`  
 Указывает на буфер, который должен получить строку. Буфер должен иметь достаточно места для и завершающий символ null.  
  
 `rString`  
 Ссылку на `CString`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки, исключая конечный символ null (в байтах). Если `nIndex` не указан допустимый индекс, возвращается значение **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Вторая форма этого члена функции заливки `CString` вместе с текстом элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#24;](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]  
  
##  <a name="getlbtextlen"></a>CComboBox::GetLBTextLen  
 Возвращает длину строки в списке поля со списком.  
  
```  
int GetLBTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс строки списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки в байтах, исключая конечный символ null. Если `nIndex` не указан допустимый индекс, возвращается значение **CB_ERR**.  
  
### <a name="example"></a>Пример  
  В примере показано [CComboBox::GetLBText](#getlbtext).  
  
##  <a name="getlocale"></a>CComboBox::GetLocale  
 Извлекает языковой стандарт, используемый в поле со списком.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение идентификатора (LCID) языка для строк в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Языковой стандарт используется, например, для определения порядка сортировки строк в отсортированном со списком.  
  
### <a name="example"></a>Пример  
  В примере показано [CComboBox::SetLocale](#setlocale).  
  
##  <a name="getminvisible"></a>CComboBox::GetMinVisible  
 Возвращает минимальное количество видимых элементов в раскрывающемся списке текущего элемента управления поля со списком.  
  
```  
int GetMinVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальное количество видимых элементов в текущем списке раскрывающегося списка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [CB_GETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettopindex"></a>CComboBox::GetTopIndex  
 Возвращает отсчитываемый от нуля индекс первой видимой позиции в части списка в поле со списком.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первой видимой позиции в части списка в поле со списком в случае успешного выполнения **CB_ERR** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Первоначально элемент 0 находится в верхней части списка, но если прокрутку списка, наверху может оказаться другой элемент.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#25;](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]  
  
##  <a name="initstorage"></a>CComboBox::InitStorage  
 Выделяет память для хранения элементы списка в части списка в поле со списком.  
  
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
 При успешном выполнении максимальное количество элементов, части списка в поле со списком может хранить до перераспределение памяти требуется **CB_ERRSPACE**, то есть не хватает памяти доступен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается перед добавлением большое число элементов в списке часть `CComboBox`.  
  
 Windows 95/98 только: `wParam` ограничен 16-разрядных значений. Это означает, что списки не может содержать более 32 767 элементов. Несмотря на то, что количество элементов является ограниченным, общий размер элементов в поле со списком ограничено только объемом доступной памяти.  
  
 Эта функция помогает ускорить инициализации список полей, имеющих большое число элементов (более 100). Он выделит место указанный объем памяти, поэтому последующие [AddString](#addstring), [InsertString](#insertstring), и [Dir](#dir) функции принимают кратчайший срок. Оценки можно использовать для параметров. Если вы пересмотреть некоторый дополнительный объем памяти выделяется; Если вы недооценивать обычного выделения используется для элементов, которые больше предварительно выделенной.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#26;](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]  
  
##  <a name="insertstring"></a>CComboBox::InsertString  
 Вставляет строку в список поля со списком.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс позиции в списке, в которую будет вставлена строка. Если этот параметр имеет значение –1, строка добавляется в конец списка.  
  
 `lpszString`  
 Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. При возникновении ошибки возвращается значение **CB_ERR** . Если для хранения новой строки недостаточно места, возвращается значение **CB_ERRSPACE** .  
  
### <a name="remarks"></a>Примечания  
 В отличие от [AddString](#addstring) функции-члена `InsertString` функции-члена не ведет список с [CBS_SORT](../../mfc/reference/combo-box-styles.md) стиль сортировки.  
  
> [!NOTE]
>  Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения для этого элемента управления в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#27;](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]  
  
##  <a name="limittext"></a>CComboBox::LimitText  
 Ограничивает длину в байтах текст, который пользователь может ввести в элемент управления списком.  
  
```  
BOOL LimitText(int nMaxChars);
```  
  
### <a name="parameters"></a>Параметры  
 `nMaxChars`  
 Указывает длину (в байтах), которые пользователь может вводить текст. Если этот параметр равен 0, длина текста устанавливается до 65 535 байт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успешного выполнения. При вызове раскрывающегося списка в стиле [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) или списком без элемента управления, возвращается значение **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Если поле со списком не имеет стиль [CBS_AUTOHSCROLL](../../mfc/reference/combo-box-styles.md), установленное которых превышает размер элемента управления редактирования текста не будет действовать.  
  
 `LimitText`ограничивает только текст, который может быть введено пользователем. Он не влияет на любой текст уже в элементе управления редактированием при отправки сообщения, а также влияет на длину текста, скопировать элемент управления поля ввода, при выборе строки в поле со списком.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#28;](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]  
  
##  <a name="measureitem"></a>CComboBox::MeasureItem  
 Вызывается инфраструктурой при создании поле со списком с стиль рисования владельцем.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMeasureItemStruct`  
 Длинный указатель [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования Windows измерений списка поле в поле со списком. Если поле со списком создается с [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) стиль, платформа вызывает эту функцию-член для каждого элемента в списке. В противном случае этот член вызывается только один раз.  
  
 С помощью **CBS_OWNERDRAWFIXED** стиля в поле со списком рисование владельцем, созданные с [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) функцию-член `CWnd` включает рекомендации по дальнейшей программирования. См. обсуждение в [14 технических Примечание](../../mfc/tn014-custom-controls.md).  
  
 В разделе [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) описание `MEASUREITEMSTRUCT` структуры.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#29;](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]  
  
##  <a name="paste"></a>CComboBox::Paste  
 Вставляет данные из буфера обмена в элемент управления поля со списком в текущей позиции курсора.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Примечания  
 Данные вставляются только в том случае, если в буфере обмена содержатся данные в **CF_TEXT** формат.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#30;](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]  
  
##  <a name="resetcontent"></a>CComboBox::ResetContent  
 Удаляет все элементы из списка и измените элемент управления списком.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#31;](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]  
  
##  <a name="selectstring"></a>CComboBox::SelectString  
 Выполняет поиск строки в списке поля со списком и если строка найдена, выбирает строки в поле со списком и копирует его в элемент управления для редактирования.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartAfter`  
 Содержит отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает конца списка, он продолжает в верхней части списка обратно элемента, заданного параметром `nStartAfter`. Если значение –&1;, всего списка выполняется с самого начала.  
  
 `lpszString`  
 Указывает нулем строка, содержащая префикс для поиска. Поиск ситуация независимые, поэтому эта строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс выбранного элемента, если строка была найдена. Если поиск завершилась ошибкой, возвращается **CB_ERR** и текущего выделения не изменяется.  
  
### <a name="remarks"></a>Примечания  
 Строка выбирается только в том случае, если его начальных символов (от начальной) соответствуют символы в строке префикс.  
  
 Обратите внимание, что `SelectString` и `FindString` функции-члены как найти строку, но `SelectString` функция-член также выбирает строки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#32;](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]  
  
##  <a name="setcuebanner"></a>CComboBox::SetCueBanner  
 Задает текст подсказки, отображаемый для поля со списком.  
  
```  
BOOL SetCueBanner(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] *lpszText*|Указатель на буфер нулем, содержащий текст подсказки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод выполнен успешно; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Текст подсказки — строки, который отображается в области ввода поля со списком. Текст подсказки отображается до ввода данных пользователем.  
  
 Этот метод отправляет [CB_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775897) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_combobox`, который используется для программного доступа к поле со списком. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается баннер подсказки для элемента управления полем со списком.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="setcursel"></a>CComboBox::SetCurSel  
 Выбирает строки в списке поля со списком.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Параметры  
 `nSelect`  
 Задает отсчитываемый от нуля индекс строки для выбора. Если значение –&1;, любое текущее выделение в поле со списком удаляется и очищается элемент управления для редактирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента, выбранного при успешном сообщения. Возвращаемое значение является **CB_ERR** Если `nSelect` больше, чем число элементов в списке или, если `nSelect` задано значение -1, который отменяет выделение.  
  
### <a name="remarks"></a>Примечания  
 При необходимости списке прокрутке строки (если в списке отображается). Текст в элементе управления списком изменяется для отражения нового выделения. Предыдущее выделение в поле со списком удаляется.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#33;](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]  
  
##  <a name="setdroppedwidth"></a>CComboBox::SetDroppedWidth  
 Вызывайте эту функцию, чтобы задать минимальную допустимую ширину в пикселях в списке поле со списком.  
  
```  
int SetDroppedWidth(UINT nWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `nWidth`  
 Минимальная допустимая ширина части списка в поле со списком в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, новая ширина списка поле, в противном случае **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция применяется только для полей со списком [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиль.  
  
 По умолчанию минимальная ширина допустимый раскрывающегося списка — 0. При отображении части списка в поле со списком его ширину больше Минимальная допустимая ширина или ширина поля со списком.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#34;](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]  
  
##  <a name="seteditsel"></a>CComboBox::SetEditSel  
 Выбирает символы в элементе управления списком.  
  
```  
BOOL SetEditSel(
    int nStartChar,  
    int nEndChar);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartChar`  
 Указывает начальную позицию. Если начальная позиция задано значение -1, будет удалена любого существующего выделения.  
  
 `nEndChar`  
 Указывает конечную позицию. Если конечная позиция задано значение -1, то весь текст из начальную позицию последнего символа в элементе управления выбирается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция-член прошла успешно; в противном случае — 0. Это **CB_ERR** Если `CComboBox` имеет [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиля или не имеет поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Позиции отсчитываются от нуля. Чтобы выбрать первый символ элемента управления поля ввода, указать начальную позицию 0. Конечная позиция — для символа сразу после последнего символа для выбора. Например чтобы выбрать первые четыре символа элемента управления поля ввода, используется начальной позиции 0 и конечную позицию 4.  
  
> [!NOTE]
>  Эта функция не поддерживается элементом управления Windows **ComboBoxEx** . Дополнительные сведения для этого элемента управления в разделе [управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CComboBox::GetEditSel](#geteditsel).  
  
##  <a name="setextendedui"></a>CComboBox::SetExtendedUI  
 Вызов `SetExtendedUI` функции-члена для выбора пользовательского интерфейса по умолчанию или расширенной пользовательский интерфейс для поля со списком, которое имеет [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиль.  
  
```  
int SetExtendedUI(BOOL bExtended = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bExtended*  
 Указывает, следует ли использовать поле со списком, расширенный пользовательский интерфейс или пользовательский интерфейс по умолчанию. Значение **TRUE** выбирает расширенного пользовательского интерфейса, а значение **FALSE** выбирает стандартный пользовательский интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CB_OKAY** , если операция выполнена успешно, или **CB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Расширенный пользовательский интерфейс может быть идентифицирована одним из следующих способов.  
  
-   Щелкните статический элемент управления отображает список только для полей со списком **CBS_DROPDOWNLIST** стиль.  
  
-   Нажмите клавишу Стрелка вниз отображает список (F4 отключена).  
  
 Прокрутка в статический элемент управления отключен, если не отображается список элементов (клавиши со стрелками отключены).  
  
### <a name="example"></a>Пример  
  В примере показано [CComboBox::GetExtendedUI](#getextendedui).  
  
##  <a name="sethorizontalextent"></a>CComboBox::SetHorizontalExtent  
 Задает ширину в пикселях, на которое части списка в поле со списком может прокручиваться по горизонтали.  
  
```  
void SetHorizontalExtent(UINT nExtent);
```  
  
### <a name="parameters"></a>Параметры  
 *nExtent*  
 Задает количество пикселей, на которое части списка в поле со списком может прокручиваться по горизонтали.  
  
### <a name="remarks"></a>Примечания  
 Если ширина поля меньше, чем это значение, горизонтальная полоса прокрутки по горизонтали прокручивает элементов в поле со списком. Если ширина поля списка равно или больше, чем это значение, горизонтальная полоса прокрутки является скрытым или, если поле со списком [CBS_DISABLENOSCROLL](../../mfc/reference/combo-box-styles.md) стиль, отключен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#35;](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]  
  
##  <a name="setitemdata"></a>CComboBox::SetItemData  
 Задает 32-разрядное значение, связанное с указанного элемента в поле со списком.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс элемента для задания.  
  
 `dwItemData`  
 Содержит новые значение, связанное с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте `SetItemDataPtr` Если 32-разрядных элемент должен быть указателем функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#36;](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]  
  
##  <a name="setitemdataptr"></a>CComboBox::SetItemDataPtr  
 Задает 32-разрядное значение, связанное с указанного элемента в поле со списком указанный указатель ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс элемента.  
  
 `pData`  
 Содержит указатель, чтобы связать с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель остается допустимым в течение жизненного цикла поле со списком, несмотря на то, что относительное положение элемента в поле со списком может измениться при добавлении и удалении элементов. Таким образом индекс элемента в поле можно изменить, но указатель остается надежным.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#37;](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]  
  
##  <a name="setitemheight"></a>CComboBox::SetItemHeight  
 Вызов `SetItemHeight` функция-член задайте высоту элементов списка в поле со списком или высоту управления редактированием (или статического текста) части поля со списком.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указывает, задан ли высота элементов списка или высоту части управления редактированием (или статического текста) в поле со списком.  
  
 Если поле со списком [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) стиль, `nIndex` задает отсчитываемый от нуля индекс элемента списка, высоту которого будет задано; в противном случае, `nIndex` должно быть 0 и высоту список всех элементов будет установлено.  
  
 Если `nIndex` является -1, высота элемента управления или статического текста поле со списком задать.  
  
 `cyItemHeight`  
 Указывает высоту в пикселях поле со списком компонентов, идентифицируемый `nIndex`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CB_ERR** Если индекс или высота недопустим; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Высота части управления редактированием (или статического текста) в поле со списком устанавливается независимо от высоты элементов списка. Приложение должно гарантировать, что высота этой части управления редактированием (или статический текст) не меньше высоты элемента определенного списка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#38;](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]  
  
##  <a name="setlocale"></a>CComboBox::SetLocale  
 Задает идентификатор языкового стандарта для этого поля со списком.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewLocale`  
 Новое значение идентификатор (LCID) языка для поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение идентификатора (LCID) языка списком.  
  
### <a name="remarks"></a>Примечания  
 Если **SetLocale** не вызывается, по умолчанию языкового стандарта, полученная от системы. Этот язык системы по умолчанию можно изменить с помощью панели управления Язык и International.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#39;](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]  
  
##  <a name="setminvisibleitems"></a>CComboBox::SetMinVisibleItems  
 Задает минимальное число видимых элементов в раскрывающемся списке текущего поля со списком.  
  
```  
BOOL SetMinVisibleItems(int iMinVisible);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iMinVisible`|Указывает минимальное количество видимых элементов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [CB_SETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_combobox`, который используется для программного доступа к поле со списком. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода вставляет 20 элементов в раскрывающемся списке элемента управления полем со списком. Затем он указывает, что менее 10 элементов будут отображаться при нажатии клавиши со стрелкой раскрывающегося списка.  
  
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
 Система выполняет прокрутку списка до элемента, заданного параметром `nIndex` отображается в верхней части списка достигнуто максимальное прокрутки диапазона или поля.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CComboBox&#40;](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]  
  
##  <a name="showdropdown"></a>CComboBox::ShowDropDown  
 Показывает или скрывает список со списком [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) или [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) стиль.  
  
```  
void ShowDropDown(BOOL bShowIt = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bShowIt*  
 Указывает, является ли поле раскрывающегося списка отображать и скрывать. Значение **TRUE** показано поле списка. Значение **FALSE** скрывает поле списка.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию поле со списком этого стиля будет отображать поле списка.  
  
 Эта функция-член не оказывает влияния на поле со списком, созданные с [CBS_SIMPLE](../../mfc/reference/combo-box-styles.md) стиль.  
  
### <a name="example"></a>Пример  
  В примере показано [CComboBox::GetDroppedState](#getdroppedstate).  
  
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
 [CDialog-класс](../../mfc/reference/cdialog-class.md)

