---
title: Класс CCheckListBox | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
dev_langs:
- C++
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4129da35eca5aecfb1e976361d1716d1cd78e906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|[CCheckListBox::Create](#create)|Создает поля со списком Windows и прикрепляет его к `CCheckListBox` объекта.|  
|[CCheckListBox::DrawItem](#drawitem)|Вызывается платформой при изменении вида изменяется рисуемый владельцем списка.|  
|[CCheckListBox::Enable](#enable)|Включает или отключает элемент поле контрольного списка.|  
|[CCheckListBox::GetCheck](#getcheck)|Получает состояние флажка элемента.|  
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Получает стиль элемента управления флажки.|  
|[CCheckListBox::IsEnabled](#isenabled)|Определяет, включен ли элемент.|  
|[CCheckListBox::MeasureItem](#measureitem)|Вызывается платформой при создании списка стиль рисования владельцем.|  
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|Вызывается платформой для получения позиции флажка элемента.|  
|[CCheckListBox::SetCheck](#setcheck)|Задает состояние флажка элемента.|  
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Задает стиль элемента управления флажков.|  
  
## <a name="remarks"></a>Примечания  
 «Контрольный список для поля» отображает список элементов, таких как имена файлов. Каждый элемент в списке имеет флажок рядом с ним, пользователь может установите или снимите флажок.  
  
 `CCheckListBox` используется только для определяемых владельцем элементов управления, поскольку этот список содержит несколько текстовых строк. В самом простом случае поля со списком содержит флажки и текстовые строки, но не обязательно должны иметь текст во всех. Например имеется список маленькие точечные рисунки с флажком рядом с каждым элементом.  
  
 Чтобы создать собственные поля со списком, должен быть производным класса из `CCheckListBox`. Для создания собственного производного класса, создание конструктора для производного класса, затем вызовите **создать**.  
  
 Если вы хотите обработки сообщений Windows уведомления, отправленные в поле со списком с родительским (обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)), добавить схему сообщений входа и обработчик сообщений функции-члена родительского класса для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 **ON_** уведомления **(**`id`, `memberFxn` **)**  
  
 где `id` указывает идентификатор дочернего окна элемента управления, отправляющего уведомление и `memberFxn` имя функции-члена родительского вы написали для обработки уведомления.  
  
 Прототип функции родительского элемента выглядит следующим образом:  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 Только одна операция схему сообщений, которая относится конкретно к **CCheckListBox** (но см. также записи схемы сообщений для [CListBox](../../mfc/reference/clistbox-class.md)):  
  
- **ON_CLBN_CHKCHANGE** пользователь изменил состояние флажка элемента.  
  
 Если ваш поля со списком окно контрольного списка по умолчанию (список строк с размерами по умолчанию флажки слева от каждого), можно использовать значение по умолчанию [CCheckListBox::DrawItem](#drawitem) для отрисовки поля со списком. В противном случае необходимо переопределить [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) функции и [CCheckListBox::DrawItem](#drawitem) и [CCheckListBox::MeasureItem](#measureitem) функции.  
  
 Поле контрольного списка можно создать на основе шаблона диалогового окна или непосредственно в коде.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cchecklistbox"></a>  CCheckListBox::CCheckListBox  
 Создает объект `CCheckListBox`.  
  
```  
CCheckListBox();
```  
  
### <a name="remarks"></a>Примечания  
 Создании `CCheckListBox` объекта в два этапа. Сначала определите класс, производный от `CCheckListBox`, затем вызовите **создать**, который инициализирует поля со списком Windows и прикрепляет его к `CCheckListBox` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]  
  
##  <a name="create"></a>  CCheckListBox::Create  
 Создает поля со списком Windows и прикрепляет его к `CCheckListBox` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль поля со списком. Необходимо выбрать **LBS_HASSTRINGS** и либо **LBS_OWNERDRAWFIXED** (все элементы в списке имеют одинаковую высоту) или **LBS_OWNERDRAWVARIABLE** (элементы в списке — Изменение высоты). Этот стиль можно объединять с другими [стили списков](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) за исключением **LBS_USETABSTOPS**.  
  
 `rect`  
 Указывает поле контрольного списка размер и положение. Может быть как [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
 `pParentWnd`  
 Указывает поле контрольного списка родительскому окну (обычно `CDialog` объекта). Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления поле контрольного списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CCheckListBox` объекта в два этапа. Во-первых, определите класс, производный от **CcheckListBox** и затем вызвать **создать**, который инициализирует поля со списком Windows и прикрепляет его к `CCheckListBox`. В разделе [CCheckListBox::CCheckListBox](#cchecklistbox) образец.  
  
 Когда **создать** выполняет Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщений для управления поле контрольного списка.  
  
 Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить возможности обработки сообщений по умолчанию, добавить схему сообщений для производного класса и функции-члены переопределение предыдущий обработчик сообщений. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Применить следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления полем контрольный список:  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_VSCROLL** для добавления вертикальной полосы прокрутки  
  
- **WS_HSCROLL** для добавления горизонтальной полосы прокрутки  
  
- **WS_GROUP** для группировки элементов управления  
  
- **WS_TABSTOP** чтобы разрешить переход на данный элемент управления  
  
##  <a name="drawitem"></a>  CCheckListBox::DrawItem  
 Вызывается платформой при изменении вида поля изменится, определяемые владельцем контрольный список.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Длинный указатель [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** и **itemState** члены `DRAWITEMSTRUCT` структура определять рисования действие, которое должно быть выполнено.  
  
 По умолчанию эта функция выводит список флажок по умолчанию, состоящий из список строк, каждый с размерами по умолчанию флажок рядом с. Размер списка флажок не указанным в [создать](#create).  
  
 Переопределите эту функцию-член для реализации Рисование рисуемый владельцем контрольный список полей, которые не используются по умолчанию, таких как контрольный список поля со списками, которые не являются строками, элементы переменной высоты или флажки, которые не входят в левой части экрана. Приложения следует восстановить всех графических устройств (интерфейс) выбранных объектов контекст отображения указано в `lpDrawItemStruct` перед прекращением работы этой функции-члена.  
  
 Поле контрольного списка элементов, не ту же высоту, контрольный список стилей (указанного в **создать**) должен быть **LBS_OWNERVARIABLE**, и необходимо переопределить [MeasureItem](#measureitem) функция.  
  
##  <a name="enable"></a>  CCheckListBox::Enable  
 Эта функция вызывается для включения или отключения элемента контрольный список.  
  
```  
void Enable(
    int nIndex,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс элемента поле контрольного списка включения.  
  
 `bEnabled`  
 Указывает, включен ли элемент.  
  
##  <a name="getcheck"></a>  CCheckListBox::GetCheck  
 Получает состояние указанного флажок.  
  
```  
int GetCheck(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс флажок, который содержится в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние указанного флажок. В следующей таблице перечислены возможные значения.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`BST_CHECKED`|Флажок установлен.|  
|`BST_UNCHECKED`|Флажок не установлен.|  
|`BST_INDETERMINATE`|Состояние флажка не определено.|  
  
##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle  
 Вызовите эту функцию для получения стиля поле контрольного списка.  
  
```  
UINT GetCheckStyle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стиль элемента управления флажки.  
  
### <a name="remarks"></a>Примечания  
 Сведения о возможных стилей см. в разделе [SetCheckStyle](#setcheckstyle).  
  
##  <a name="isenabled"></a>  CCheckListBox::IsEnabled  
 Вызывайте эту функцию, чтобы определить, включен ли элемент.  
  
```  
BOOL IsEnabled(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент включен; в противном случае — 0.  
  
##  <a name="measureitem"></a>  CCheckListBox::MeasureItem  
 Вызывается платформой при создании поля со списком с стиль не по умолчанию.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMeasureItemStruct`  
 Длинный указатель [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования Windows размеры элементов поле контрольного списка. Если поле контрольного списка создается с [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля, платформа вызывает эту функцию-член для каждого элемента в поле со списком. В противном случае этот член вызывается только один раз.  
  
##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition  
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
 По умолчанию положения и размера флажка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положение и размер флажка элемента.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию возвращает только по умолчанию положения и размера флажка ( `rectCheckBox`). По умолчанию флажок выравнивается в левом верхнем углу элемента и размер стандартный флажок. Возможны случаи, когда требуется флажки справа или хотите флажок больше или меньше. В таких случаях можно переопределить `OnGetCheckPosition` изменение флажок положение и размер внутри элемента.  
  
##  <a name="setcheck"></a>  CCheckListBox::SetCheck  
 Задает состояние указанного флажок.  
  
```  
void SetCheck(
    int nIndex,  
    int nCheck);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс флажок, который содержится в поле со списком.  
  
 `nCheck`  
 Состояние кнопки для указанного флажка. Возможные значения см.  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице перечислены возможные значения для `nCheck` параметра.  
  
|Значение|Описание|  
|-----------|-----------------|  
|**BST_CHECKED**|Установите указанный флажок.|  
|**BST_UNCHECKED**|Снимите флажок указанного.|  
|**BST_INDETERMINATE**|Задайте состояние указанного флажок в неопределенном состоянии.<br /><br /> Это состояние доступен, только если флажок стиль `BS_AUTO3STATE` или `BS_3STATE`. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
  
##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle  
 Эта функция вызывается для задания стиля флажков в окне контрольного списка.  
  
```  
void SetCheckStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `nStyle`  
 Определяет стиль флажки в поле контрольного списка.  
  
### <a name="remarks"></a>Примечания  
 Существуют следующие допустимые стили:  
  
- **BS_CHECKBOX**  
  
- **BS_AUTOCHECKBOX**  
  
- **BS_AUTO3STATE**  
  
- **BS_3STATE**  
  
 Сведения об этих стилей см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC TSTCON](../../visual-cpp-samples.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CListBox](../../mfc/reference/clistbox-class.md)
