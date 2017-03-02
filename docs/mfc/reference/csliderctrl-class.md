---
title: "CSliderCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSliderCtrl
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CSliderCtrl
- slider controls, CSliderCtrl class
- CSliderCtrl class, common controls
- CSliderCtrl class
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
caps.latest.revision: 22
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
ms.openlocfilehash: 0d024c7d6670ff3b7a94b9657151e7bf1958d5f1
ms.lasthandoff: 02/24/2017

---
# <a name="csliderctrl-class"></a>CSliderCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "ползунок" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Создает объект `CSliderCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|Отменяет текущее выделение в элементе управления "ползунок".|  
|[CSliderCtrl::ClearTics](#cleartics)|Удаляет текущий деления из элемента управления "ползунок".|  
|[CSliderCtrl::Create](#create)|Создает элемент управления slider и присоединяет его к `CSliderCtrl` объекта.|  
|[CSliderCtrl::CreateEx](#createex)|Создает элемент управления slider с указанным расширенные стили Windows и присоединяет его к `CSliderCtrl` объекта.|  
|[CSliderCtrl::GetBuddy](#getbuddy)|Получает дескриптор окна контактов управления slider в заданную позицию.|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Получает размер элемента управления "ползунок" канала.|  
|[CSliderCtrl::GetLineSize](#getlinesize)|Получает линейный размер ползунка.|  
|[CSliderCtrl::GetNumTics](#getnumtics)|Получает количество делений в элементе управления "ползунок".|  
|[CSliderCtrl::GetPageSize](#getpagesize)|Получает размер страницы элемента управления "ползунок".|  
|[CSliderCtrl::GetPos](#getpos)|Получает текущее положение ползунка.|  
|[CSliderCtrl::GetRange](#getrange)|Получает минимальное и максимальное позиций для ползунка.|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|Получает положение для ползунка.|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|Получает положение минимума для ползунка.|  
|[CSliderCtrl::GetSelection](#getselection)|Возвращает диапазон текущего выделенного фрагмента.|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|Получает длину ползунок в текущем элементе управления trackbar.|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Получает размер бегунка элемента управления "ползунок".|  
|[CSliderCtrl::GetTic](#gettic)|Возвращает позицию указанного делений.|  
|[CSliderCtrl::GetTicArray](#getticarray)|Извлекает массив позиций знак деления ползунка.|  
|[CSliderCtrl::GetTicPos](#getticpos)|Возвращает позицию указанного деления в клиентских координатах.|  
|[CSliderCtrl::GetToolTips](#gettooltips)|Извлекает дескриптора элемента управления всплывающей подсказки для элемента управления slider, если таковые имеются.|  
|[CSliderCtrl::SetBuddy](#setbuddy)|Назначает окно контактов окна для элемента управления "ползунок".|  
|[CSliderCtrl::SetLineSize](#setlinesize)|Задает линейный размер ползунка.|  
|[CSliderCtrl::SetPageSize](#setpagesize)|Задает размер страницы элемента управления "ползунок".|  
|[CSliderCtrl::SetPos](#setpos)|Задает текущее положение ползунка.|  
|[CSliderCtrl::SetRange](#setrange)|Задает минимальное и максимальное позицию для ползунка.|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|Задает положение для ползунка.|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|Задает минимальный позицию для ползунка.|  
|[CSliderCtrl::SetSelection](#setselection)|Задает диапазон текущего выделенного фрагмента.|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|Задает длину ползунка в текущем элементе управления trackbar.|  
|[CSliderCtrl::SetTic](#settic)|Задает позицию указанного делений.|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|Задает частоту делений на шаг управления ползунка.|  
|[CSliderCtrl::SetTipSide](#settipside)|Позиции элемента управления всплывающей подсказки используется элемент управления trackbar.|  
|[CSliderCtrl::SetToolTips](#settooltips)|Назначает ползунок элемента управления всплывающей подсказки.|  
  
## <a name="remarks"></a>Примечания  
 «Ползунок» (также называется trackbar) — это окно, содержащее ползунка и необязательный делениями. При перемещении ползунка, с помощью мыши или клавиш направления, элемент управления отправляет сообщения уведомления для отражения изменений.  
  
 Ползунки полезны в тех случаях, когда пользователю необходимо выбрать дискретное значение или набор последовательных значений в диапазоне. Например может использовать элемент управления slider позволяет пользователю задавать повторяющийся интервал клавиатуры с помощью ползунка заданного делений.  
  
 Этот элемент управления (и, следовательно, `CSliderCtrl` класса) доступны только для программы, запущенные в Windows 95/98 и Windows NT версии 3.51 и более поздних версий.  
  
 Перемещение ползунка на, указываемые при ее создании. Например, если указать что ползунок должен иметь диапазон из пяти ползунок можно только занимают шесть позиции: позиция с левой стороны элемента управления slider и на одну позицию для каждого фрагмента в диапазоне. Как правило каждый из этих позиций идентифицируется деления.  
  
 Создание ползунка с помощью конструктора и **создать** функции-члена `CSliderCtrl`. После создания элемента управления "ползунок", можно использовать функции-члены в `CSliderCtrl` для изменения многих из его свойств. Изменения, выполненные включают Задание минимального и максимального позиции ползунка, рисование делений, параметр диапазон выбора и положения ползунка.  
  
 Дополнительные сведения об использовании `CSliderCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CSliderCtrl с помощью](../../mfc/using-csliderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-nameclearsela--csliderctrlclearsel"></a><a name="clearsel"></a>CSliderCtrl::ClearSel  
 Отменяет текущее выделение в элементе управления "ползунок".  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bRedraw`  
 Перерисовывает флаг. Если этот параметр равен **TRUE**, ползунок перерисовке после очистки выделения; в противном случае не перерисовке ползунка.  
  
##  <a name="a-nameclearticsa--csliderctrlcleartics"></a><a name="cleartics"></a>CSliderCtrl::ClearTics  
 Удаляет текущий деления из элемента управления "ползунок".  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bRedraw`  
 Перерисовывает флаг. Если этот параметр равен **TRUE**, ползунок перерисовке после очистки делений; в противном случае не перерисовке ползунка.  
  
##  <a name="a-namecreatea--csliderctrlcreate"></a><a name="create"></a>CSliderCtrl::Create  
 Создает элемент управления slider и присоединяет его к `CSliderCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления "ползунок". Примените любое сочетание [стили элемента управления "ползунок"](http://msdn.microsoft.com/library/windows/desktop/bb760147), описанный в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], к элементу управления.  
  
 `rect`  
 Задает размер и положение элемента управления "ползунок". Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает родительского окна элемента управления slider обычно `CDialog`. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления "ползунок".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CSliderCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает элемент управления slider и присоединяет его к `CSliderCtrl` объекта.  
  
 В зависимости от значения для `dwStyle`, элемент управления slider может иметь вертикальной или горизонтальной ориентации. Он может иметь деления на обеих сторонах обоих сторон или ни одного. Он также может использоваться для указания диапазона последовательных значений.  
  
 Чтобы применить расширенные стили окна ползунком, вызовите [CreateEx](#createex) вместо **создать**.  
  
##  <a name="a-namecreateexa--csliderctrlcreateex"></a><a name="createex"></a>CSliderCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связывает его с `CSliderCtrl` объекта.  
  
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
 Задает стиль элемента управления "ползунок". Примените любое сочетание [стили элемента управления "ползунок"](http://msdn.microsoft.com/library/windows/desktop/bb760147), описанный в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], к элементу управления.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
##  <a name="a-namecsliderctrla--csliderctrlcsliderctrl"></a><a name="csliderctrl"></a>CSliderCtrl::CSliderCtrl  
 Создает объект `CSliderCtrl`.  
  
```  
CSliderCtrl();
```  
  
##  <a name="a-namegetbuddya--csliderctrlgetbuddy"></a><a name="getbuddy"></a>CSliderCtrl::GetBuddy  
 Получает дескриптор окна контактов управления slider в заданную позицию.  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `fLocation`  
 Логическое значение, указывающее, что два дескриптора окна контактов для получения. Может принимать одно из следующих значений:  
  
- **Значение TRUE,** Получает дескриптор контактов слева от ползунка. Если элемент управления "ползунок" использует `TBS_VERT` стиль, сообщение будет извлекать друг над ползунком.  
  
- **FALSE** Получает дескриптор контактов справа от ползунка. Если элемент управления "ползунок" использует `TBS_VERT` стиль, сообщение будет извлекать контактов ниже бегунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, являющийся приятель окна в расположении, заданном `fLocation`, или **NULL** Если окна контактов не существует в этом расположении.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TBM_GETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760178), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Описание стили элемента управления "ползунок" в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetchannelrecta--csliderctrlgetchannelrect"></a><a name="getchannelrect"></a>CSliderCtrl::GetChannelRect  
 Получает размер и положение ограничивающего прямоугольника для элемента управления "ползунок" канала.  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) когда функция возвращает объект, содержащий размер и положение канала ограничивающий прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 Канал представляет собой область ползунок и при выборе диапазона, который содержит выделения.  
  
##  <a name="a-namegetlinesizea--csliderctrlgetlinesize"></a><a name="getlinesize"></a>CSliderCtrl::GetLineSize  
 Возвращает размер строки для элемента управления "ползунок".  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер строки для элемента управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Размер строки влияет на объем ползунок для **TB_LINEUP** и **TB_LINEDOWN** уведомления. Размер строки по умолчанию — 1.  
  
##  <a name="a-namegetnumticsa--csliderctrlgetnumtics"></a><a name="getnumtics"></a>CSliderCtrl::GetNumTics  
 Получает количество делений в элементе управления "ползунок".  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество делений в элементе управления "ползунок".  
  
##  <a name="a-namegetpagesizea--csliderctrlgetpagesize"></a><a name="getpagesize"></a>CSliderCtrl::GetPageSize  
 Получает размер страницы для элемента управления "ползунок".  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер страницы для ползунка.  
  
### <a name="remarks"></a>Примечания  
 Размер страницы влияет на объем ползунок для **TB_PAGEUP** и **TB_PAGEDOWN** уведомления.  
  
##  <a name="a-namegetposa--csliderctrlgetpos"></a><a name="getpos"></a>CSliderCtrl::GetPos  
 Получает текущее положение ползунка в элементе управления "ползунок".  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая позиция.  
  
##  <a name="a-namegetrangea--csliderctrlgetrange"></a><a name="getrange"></a>CSliderCtrl::GetRange  
 Получает максимальное и минимальное позиции для ползунок в элементе управления "ползунок".  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nMin`  
 Ссылка на целое число, Получает положение минимума.  
  
 `nMax`  
 Ссылка на целое число, Получает положение.  
  
### <a name="remarks"></a>Примечания  
 Эта функция копирует значения в целые числа, ссылается `nMin` и `nMax`.  
  
##  <a name="a-namegetrangemaxa--csliderctrlgetrangemax"></a><a name="getrangemax"></a>CSliderCtrl::GetRangeMax  
 Получает положение ползунка в элементе управления "ползунок".  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение положения элемента управления.  
  
##  <a name="a-namegetrangemina--csliderctrlgetrangemin"></a><a name="getrangemin"></a>CSliderCtrl::GetRangeMin  
 Получает положение минимума ползунка в элементе управления "ползунок".  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальное положение элемента управления.  
  
##  <a name="a-namegetselectiona--csliderctrlgetselection"></a><a name="getselection"></a>CSliderCtrl::GetSelection  
 Получает начальное и конечное положения текущего выделенного фрагмента в элементе управления "ползунок".  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nMin`  
 Ссылка на целое число, Получает начальную позицию текущего выделенного фрагмента.  
  
 `nMax`  
 Ссылка на целое число, получающий конечную позицию текущего выделенного фрагмента.  
  
##  <a name="a-namegetthumblengtha--csliderctrlgetthumblength"></a><a name="getthumblength"></a>CSliderCtrl::GetThumbLength  
 Получает длину ползунок в текущем элементе управления trackbar.  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина ползунок в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TBM_GETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760201) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetthumbrecta--csliderctrlgetthumbrect"></a><a name="getthumbrect"></a>CSliderCtrl::GetThumbRect  
 Получает размер и положение ограничивающего прямоугольника для ползунка (бегунком) в элементе управления "ползунок".  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Указатель на `CRect` объект, содержащий прямоугольник, ограничивающий ползунок при возврате из функции.  
  
##  <a name="a-namegettica--csliderctrlgettic"></a><a name="gettic"></a>CSliderCtrl::GetTic  
 Получает позицию делений в элементе управления "ползунок".  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nTic`  
 Отсчитываемый от нуля индекс, ссылающийся на деления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положение указанного деления или – 1, если `nTic` не указан допустимый индекс.  
  
##  <a name="a-namegetticarraya--csliderctrlgetticarray"></a><a name="getticarray"></a>CSliderCtrl::GetTicArray  
 Извлекает адрес массива, содержащего позициях делений для элемента управления "ползунок".  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес массива, содержащего положения метки делений для элемента управления ползунка.  
  
##  <a name="a-namegetticposa--csliderctrlgetticpos"></a><a name="getticpos"></a>CSliderCtrl::GetTicPos  
 Получает текущий физическое положение делений в элементе управления "ползунок".  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nTic`  
 Отсчитываемый от нуля индекс, ссылающийся на деления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Физическое положение, в клиентских координатах, указанный деления или – 1, если `nTic` не указан допустимый индекс.  
  
##  <a name="a-namegettooltipsa--csliderctrlgettooltips"></a><a name="gettooltips"></a>CSliderCtrl::GetToolTips  
 Извлекает дескриптора элемента управления всплывающей подсказки для элемента управления slider, если таковые имеются.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта, или **NULL** если подсказки не используются. Если не использовать ползунок **TBS_TOOLTIPS** стиль, возвращаемым значением является **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TBM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760209), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Обратите внимание, что эта функция-член возвращает `CToolTipCtrl` объекта вместо дескриптора элемента управления.  
  
 Описание стили элемента управления "ползунок" в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbuddya--csliderctrlsetbuddy"></a><a name="setbuddy"></a>CSliderCtrl::SetBuddy  
 Назначает окно контактов окна для элемента управления "ползунок".  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndBuddy`  
 Указатель на `CWnd` объект, который будет установлен в качестве элемента управления slider контактов.  
  
 `fLocation`  
 Значение, указывающее место, в котором для отображения окна контактов. Это значение может быть одним из следующих:  
  
- **Значение TRUE,** контактов будут отображаться слева от trackbar, если используется элемент управления trackbar `TBS_HORZ` стиль. Если используется trackbar `TBS_VERT` стиля контактов отображается над элементом управления trackbar.  
  
- **FALSE** контактов будет отображаться справа от ползунка, если элемент управления trackbar использует `TBS_HORZ` стиль. Если используется trackbar `TBS_VERT` стиля контактов отображается под элементом управления trackbar.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, который ранее был назначен ползунок в этом расположении.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TBM_SETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760213), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Обратите внимание, что эта функция-член использует указатели на `CWnd` объектов вместо дескриптора окна для возвращаемого значения и параметры.  
  
 Описание стили элемента управления "ползунок" в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetlinesizea--csliderctrlsetlinesize"></a><a name="setlinesize"></a>CSliderCtrl::SetLineSize  
 Задает размер строки для элемента управления "ползунок".  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 `nSize`  
 Новый размер строки элемента управления ползунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий размер строки.  
  
### <a name="remarks"></a>Примечания  
 Размер строки влияет на объем ползунок для **TB_LINEUP** и **TB_LINEDOWN** уведомления.  
  
##  <a name="a-namesetpagesizea--csliderctrlsetpagesize"></a><a name="setpagesize"></a>CSliderCtrl::SetPageSize  
 Задает размер страницы для элемента управления "ползунок".  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 `nSize`  
 Новый размер страницы элемента управления ползунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий размер страницы.  
  
### <a name="remarks"></a>Примечания  
 Размер страницы влияет на объем ползунок для **TB_PAGEUP** и **TB_PAGEDOWN** уведомления.  
  
##  <a name="a-namesetposa--csliderctrlsetpos"></a><a name="setpos"></a>CSliderCtrl::SetPos  
 Задает текущее положение ползунка в элементе управления "ползунок".  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Указывает новое положение ползунка.  
  
##  <a name="a-namesetrangea--csliderctrlsetrange"></a><a name="setrange"></a>CSliderCtrl::SetRange  
 Задает диапазон (минимальные и максимальные позиций) для ползунок в элементе управления "ползунок".  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `nMin`  
 Положение минимума ползунка.  
  
 `nMax`  
 Значение положения ползунка.  
  
 `bRedraw`  
 Флаг перерисовки. Если этот параметр равен **TRUE**, ползунок перерисовке после значения диапазона; в противном случае не перерисовке ползунка.  
  
##  <a name="a-namesetrangemaxa--csliderctrlsetrangemax"></a><a name="setrangemax"></a>CSliderCtrl::SetRangeMax  
 Задает максимальный диапазон для ползунок в элементе управления "ползунок".  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `nMax`  
 Значение положения ползунка.  
  
 `bRedraw`  
 Флаг перерисовки. Если этот параметр равен **TRUE**, ползунок перерисовке после значения диапазона; в противном случае не перерисовке ползунка.  
  
##  <a name="a-namesetrangemina--csliderctrlsetrangemin"></a><a name="setrangemin"></a>CSliderCtrl::SetRangeMin  
 Задает минимальный диапазон для ползунок в элементе управления "ползунок".  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `nMin`  
 Положение минимума ползунка.  
  
 `bRedraw`  
 Флаг перерисовки. Если этот параметр равен **TRUE**, ползунок перерисовке после значения диапазона; в противном случае не перерисовке ползунка.  
  
##  <a name="a-namesetselectiona--csliderctrlsetselection"></a><a name="setselection"></a>CSliderCtrl::SetSelection  
 Задает начальные и конечные позиции для текущего выбора в элементе управления "ползунок".  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 `nMin`  
 Начальная позиция для ползунка.  
  
 `nMax`  
 Конечное положение ползунка.  
  
##  <a name="a-namesetthumblengtha--csliderctrlsetthumblength"></a><a name="setthumblength"></a>CSliderCtrl::SetThumbLength  
 Задает длину ползунка в текущем элементе управления trackbar.  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nLength`|Длина ползунок в пикселях.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод требует, чтобы элемент управления trackbar будет присвоено [TBS_FIXEDLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760147) стиль.  
  
 Этот метод отправляет [TBM_SETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760234) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_sliderCtrl`, который используется для доступа к текущей управления trackbar. В примере также определяется переменная, `thumbLength`, который используется для хранения длины по умолчанию компонента управления trackbar бегунка. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает компонент управления trackbar бегунка дважды длина по умолчанию.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="a-namesettica--csliderctrlsettic"></a><a name="settic"></a>CSliderCtrl::SetTic  
 Задает позицию делений в элементе управления "ползунок".  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>Параметры  
 `nTic`  
 Положение делений. Этот параметр необходимо указать положительное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если деления — значение NULL. в противном случае — 0.  
  
##  <a name="a-namesetticfreqa--csliderctrlsetticfreq"></a><a name="setticfreq"></a>CSliderCtrl::SetTicFreq  
 Задает частоту, с какой деления метки отображаются в ползунок.  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>Параметры  
 *nFreq*  
 Интервал меток делений.  
  
### <a name="remarks"></a>Примечания  
 Например если частота имеет значение 2, деление отображается для каждого приращения в диапазоне ползунка. Значение по умолчанию для частоты равно 1 (то есть каждый шаг в диапазоне связан с деления).  
  
 Необходимо создать элемент управления с `TBS_AUTOTICKS` стиль для использования этой функции. Дополнительные сведения см. в разделе [CSliderCtrl::Create](#create).  
  
##  <a name="a-namesettipsidea--csliderctrlsettipside"></a><a name="settipside"></a>CSliderCtrl::SetTipSide  
 Позиции элемента управления всплывающей подсказки используется элемент управления trackbar.  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>Параметры  
 `nLocation`  
 Значение, представляющее место, в котором для отображения элемента управления всплывающей подсказки. Список возможных значений см. в разделе сообщение Win32 [TBM_SETTIPSIDE](http://msdn.microsoft.com/library/windows/desktop/bb760240), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, представляющее предыдущее расположение элемента управления всплывающей подсказки. Возвращаемое значение равно одному из возможных значений для `nLocation`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 **TBM_SETTIPSIDE**, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Ползунок управления, использующих **TBS_TOOLTIPS** стиль отображения подсказки. Описание стили элемента управления "ползунок" в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
##  <a name="a-namesettooltipsa--csliderctrlsettooltips"></a><a name="settooltips"></a>CSliderCtrl::SetToolTips  
 Назначает ползунок элемента управления всплывающей подсказки.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndTip`  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объект, содержащий подсказок для использования с элементом управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TBM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760242), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. При создании элемента управления slider с **TBS_TOOLTIPS** стиль, он создает управления всплывающей подсказки по умолчанию, который отображается рядом с ползунком, отображение текущего положения ползунка. Описание стили элемента управления "ползунок" в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl-класс](../../mfc/reference/cprogressctrl-class.md)

