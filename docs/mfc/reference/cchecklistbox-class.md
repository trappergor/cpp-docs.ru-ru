---
title: "Класс CCheckListBox | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCheckListBox
dev_langs:
- C++
helpviewer_keywords:
- CCheckListBox class
- checklist boxes
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2cce91e3b6cb6cdf6ec2f4564fcf5090a54c917f
ms.lasthandoff: 02/24/2017

---
# <a name="cchecklistbox-class"></a>Класс CCheckListBox
Предоставляет функции поля со списком Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCheckListBox : public CListBox  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCheckListBox::CCheckListBox](#cchecklistbox)|Создает объект `CCheckListBox`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCheckListBox::Create](#create)|Поле контрольного списка Windows создает и присоединяет его к `CCheckListBox` объекта.|  
|[CCheckListBox::DrawItem](#drawitem)|Вызывается инфраструктурой при изменении внешнего вида изменяется список рисование владельцем.|  
|[CCheckListBox::Enable](#enable)|Включает или отключает элемент поля контрольный список.|  
|[CCheckListBox::GetCheck](#getcheck)|Получает состояние флажка элемента.|  
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Получает стиль элемента управления флажков.|  
|[CCheckListBox::IsEnabled](#isenabled)|Определяет, включен ли элемент.|  
|[CCheckListBox::MeasureItem](#measureitem)|Вызывается инфраструктурой при создании списка стилей рисования владельцем.|  
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|Вызывается платформой для получения позиции элемента флажок.|  
|[CCheckListBox::SetCheck](#setcheck)|Задает состояние флажка элемента.|  
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Задает стиль элемента управления флажков.|  
  
## <a name="remarks"></a>Примечания  
 «Контрольный список для поля» отображает список элементов, таких как имена файлов. Каждый элемент в списке имеет флажок рядом с ним, пользователь может установите или снимите флажок.  
  
 `CCheckListBox`используется только для определяемых владельцем элементов управления, поскольку список содержит несколько текстовых строк. В простейшем случае поле контрольного списка содержит флажки и текстовые строки, но необходимо иметь текст вообще. Например может иметь маленькие точечные рисунки, снимите флажок рядом с каждым элементом списка.  
  
 Для создания собственного контрольного списка, необходимо создать производный класс из `CCheckListBox`. Для создания собственного производного класса, создание конструктора для производного класса, затем вызовите **создать**.  
  
 Если требуется обрабатывать сообщения уведомления Windows, отправляемые поле со списком с родительским (обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)), добавление карты сообщение входа и обработчик сообщений функции-члена родительский класс для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 **ON_**Notification **(**`id`, `memberFxn`**)**  
  
 где `id` указывает идентификатор дочернего окна элемента управления отправки уведомлений и `memberFxn` имя родительской функции члена, написанный для обработки уведомления.  
  
 Прототип функции родительского выглядит следующим образом:  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 Существует только одна запись сопоставления сообщений, относящиеся конкретно к **CCheckListBox** (но см. также записи карт сообщений для [CListBox](../../mfc/reference/clistbox-class.md)):  
  
- **ON_CLBN_CHKCHANGE** пользователь изменил состояние флажка элемента.  
  
 Если ваш контрольный список является окном контрольный список по умолчанию (список строк с размерами по умолчанию флажки слева от каждого), можно использовать значение по умолчанию [CCheckListBox::DrawItem](#drawitem) для отрисовки поля со списком. В противном случае, необходимо переопределить [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) функции и [CCheckListBox::DrawItem](#drawitem) и [CCheckListBox::MeasureItem](#measureitem) функции.  
  
 Поле контрольного списка можно создать из шаблона диалогового окна или непосредственно в коде.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namecchecklistboxa--cchecklistboxcchecklistbox"></a><a name="cchecklistbox"></a>CCheckListBox::CCheckListBox  
 Создает объект `CCheckListBox`.  
  
```  
CCheckListBox();
```  
  
### <a name="remarks"></a>Примечания  
 Создании `CCheckListBox` объекта в два этапа. Сначала определите класс, производный от `CCheckListBox`, затем вызовите **создать**, который инициализирует поля со списком Windows и присоединяет его к `CCheckListBox` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog&#60;](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]  
  
##  <a name="a-namecreatea--cchecklistboxcreate"></a><a name="create"></a>CCheckListBox::Create  
 Поле контрольного списка Windows создает и присоединяет его к `CCheckListBox` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль поля со списком. Необходимо выбрать **LBS_HASSTRINGS** и **LBS_OWNERDRAWFIXED** (все элементы в списке имеют одинаковую высоту) или **LBS_OWNERDRAWVARIABLE** (элементов в списке — различной высоты). Этот стиль можно объединять с другими [стили списков](../../mfc/reference/list-box-styles.md) за исключением **LBS_USETABSTOPS**.  
  
 `rect`  
 Указывает поле контрольного списка размеров и положения. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
 `pParentWnd`  
 Указывает поле контрольного списка родительского окна (обычно `CDialog` объекта). Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления поле контрольного списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CCheckListBox` объекта в два этапа. Во-первых, определите класс, производный от **CcheckListBox** , а затем вызвать **создать**, который инициализирует поля со списком Windows и присоединяет его к `CCheckListBox`. В разделе [CCheckListBox::CCheckListBox](#cchecklistbox) образец.  
  
 При **создать** выполняет Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщений для элемента управления полем контрольный список.  
  
 Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Для расширения обработки сообщений по умолчанию, добавить схему сообщений для производного класса и функции-члены переопределение предыдущий обработчик сообщений. Переопределение `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Примените следующий [стили окна](../../mfc/reference/window-styles.md) к элементу управления поле контрольного списка:  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_VSCROLL** для добавления вертикальной полосы прокрутки  
  
- **WS_HSCROLL** для добавления горизонтальной полосы прокрутки  
  
- **WS_GROUP** для группирования элементов управления  
  
- **WS_TABSTOP** чтобы разрешить переход к этому элементу управления  
  
##  <a name="a-namedrawitema--cchecklistboxdrawitem"></a><a name="drawitem"></a>CCheckListBox::DrawItem  
 Вызывается инфраструктурой при изменении внешнего вида изменяется определяемые владельцем контрольный список.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Длинный указатель [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** и **itemState** члены `DRAWITEMSTRUCT` структуры определяют рисования действие, которое должно быть выполнено.  
  
 По умолчанию эта функция выводит список флажок по умолчанию, содержащая список строк, каждый с размерами по умолчанию флажок рядом с. Размер списка флажок не указано в [создать](#create).  
  
 Переопределите эту функцию-член для реализации Рисование рисование владельцем контрольный список полей, которые не используются по умолчанию, такие как контрольный список полей со списками, которые не являются строками, элементы переменной высоты или флажки, которые не входят в левом. Приложение должно восстановить всех графических устройств интерфейс (GDI) выбранных объектов в контексте отображения указано в `lpDrawItemStruct` до завершения работы этой функции-члена.  
  
 Если контрольный список элементов не ту же высоту, контрольный список поле стиль (указанного в **создать**) должны быть **LBS_OWNERVARIABLE**, и необходимо переопределить [MeasureItem](#measureitem) функции.  
  
##  <a name="a-nameenablea--cchecklistboxenable"></a><a name="enable"></a>CCheckListBox::Enable  
 Эта функция вызывается для включения или отключения элемент поля контрольный список.  
  
```  
void Enable(
    int nIndex,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс элемента поле контрольного списка для включения.  
  
 `bEnabled`  
 Указывает, включен ли элемент.  
  
##  <a name="a-namegetchecka--cchecklistboxgetcheck"></a><a name="getcheck"></a>CCheckListBox::GetCheck  
 Получает состояние указанного флажок.  
  
```  
int GetCheck(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс флажок, который содержится в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние указанный флажок. В следующей таблице перечислены возможные значения.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`BST_CHECKED`|Флажок установлен.|  
|`BST_UNCHECKED`|Флажок не установлен.|  
|`BST_INDETERMINATE`|Состояние флажка не определено.|  
  
##  <a name="a-namegetcheckstylea--cchecklistboxgetcheckstyle"></a><a name="getcheckstyle"></a>CCheckListBox::GetCheckStyle  
 Эта функция вызывается для получения стиля поле контрольного списка.  
  
```  
UINT GetCheckStyle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стиль элемента управления флажки.  
  
### <a name="remarks"></a>Примечания  
 Сведения о возможных стилей см. в разделе [SetCheckStyle](#setcheckstyle).  
  
##  <a name="a-nameisenableda--cchecklistboxisenabled"></a><a name="isenabled"></a>CCheckListBox::IsEnabled  
 Эта функция вызывается для определения, включен ли элемент.  
  
```  
BOOL IsEnabled(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент включен; в противном случае — 0.  
  
##  <a name="a-namemeasureitema--cchecklistboxmeasureitem"></a><a name="measureitem"></a>CCheckListBox::MeasureItem  
 Вызывается инфраструктурой при создании нестандартных стиль поля со списком.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMeasureItemStruct`  
 Длинный указатель [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования Windows измерений поле контрольного списка элементов. Если поле контрольного списка создается с [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) стиль, платформа вызывает эту функцию-член для каждого элемента в списке. В противном случае этот член вызывается только один раз.  
  
##  <a name="a-nameongetcheckpositiona--cchecklistboxongetcheckposition"></a><a name="ongetcheckposition"></a>CCheckListBox::OnGetCheckPosition  
 Платформа вызывает эту функцию для получения позиции и размера флажка в элементе.  
  
```  
virtual CRect OnGetCheckPosition(
    CRect rectItem,  
    CRect rectCheckBox);
```  
  
### <a name="parameters"></a>Параметры  
 *rectItem*  
 Положение и размер элемента списка.  
  
 `rectCheckBox`  
 По умолчанию положение и размер флажка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положение и размер флажка элемента.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию возвращает только по умолчанию положение и размер флажка ( `rectCheckBox`). По умолчанию флажок выравнивается в левом верхнем углу элемента и размер стандартный флажок. Возможны случаи, когда требуется флажки справа или хотите флажок больше или меньше. В этих случаях переопределить `OnGetCheckPosition` изменение флажок положение и размер в элементе.  
  
##  <a name="a-namesetchecka--cchecklistboxsetcheck"></a><a name="setcheck"></a>CCheckListBox::SetCheck  
 Задает состояние указанного флажок.  
  
```  
void SetCheck(
    int nIndex,  
    int nCheck);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс флажок, который содержится в списке.  
  
 `nCheck`  
 Состояние кнопки для указанного поля с флажком. Возможные значения см.  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице перечислены возможные значения для `nCheck` параметр.  
  
|Значение|Описание|  
|-----------|-----------------|  
|**BST_CHECKED**|Установите указанный флажок.|  
|**BST_UNCHECKED**|Снимите указанный флажок.|  
|**BST_INDETERMINATE**|Установите неопределенное состояние указанный флажок.<br /><br /> Это состояние доступна, только если флажок стиль `BS_AUTO3STATE` или `BS_3STATE`. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/button-styles.md).|  
  
##  <a name="a-namesetcheckstylea--cchecklistboxsetcheckstyle"></a><a name="setcheckstyle"></a>CCheckListBox::SetCheckStyle  
 Эта функция вызывается для задания стиля флажков в окне контрольного списка.  
  
```  
void SetCheckStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `nStyle`  
 Определяет стиль флажки в поле контрольного списка.  
  
### <a name="remarks"></a>Примечания  
 Допустимы стили являются:  
  
- **BS_CHECKBOX**  
  
- **BS_AUTOCHECKBOX**  
  
- **BS_AUTO3STATE**  
  
- **BS_3STATE**  
  
 Сведения об этих стилей см. в разделе [стили кнопок](../../mfc/reference/button-styles.md).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC TSTCON](../../visual-cpp-samples.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)

