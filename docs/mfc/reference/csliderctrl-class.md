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
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 745dc253ac0837ffc62f47db2038e6302b83b558
ms.lasthandoff: 04/01/2017

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
|[CSliderCtrl::Create](#create)|Создает элемент управления "ползунок" и прикрепляет его к `CSliderCtrl` объекта.|  
|[CSliderCtrl::CreateEx](#createex)|Создает элемент управления "ползунок" с указанным расширенные стили Windows и прикрепляет его к `CSliderCtrl` объекта.|  
|[CSliderCtrl::GetBuddy](#getbuddy)|Извлекает дескриптор окна элемента управления контактному лицу ползунок в заданную позицию.|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Получает размер элемента управления "ползунок" канала.|  
|[CSliderCtrl::GetLineSize](#getlinesize)|Получает размер элемента управления "ползунок" строки.|  
|[CSliderCtrl::GetNumTics](#getnumtics)|Извлекает количество делений в элементе управления "ползунок".|  
|[CSliderCtrl::GetPageSize](#getpagesize)|Получает размер страницы для элемента управления "ползунок".|  
|[CSliderCtrl::GetPos](#getpos)|Извлекает текущее положение ползунка.|  
|[CSliderCtrl::GetRange](#getrange)|Получает минимальное и максимальное позиции для ползунка.|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|Извлекает значение положения ползунка.|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|Возвращает позицию минимальное для ползунка.|  
|[CSliderCtrl::GetSelection](#getselection)|Извлекает диапазон текущего выделенного фрагмента.|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|Получает длину ползунок в текущем элементе управления trackbar.|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Получает размер элемента управления "ползунок" thumb.|  
|[CSliderCtrl::GetTic](#gettic)|Возвращает позицию указанного делений.|  
|[CSliderCtrl::GetTicArray](#getticarray)|Извлекает массив позиций знак деления для элемента управления "ползунок".|  
|[CSliderCtrl::GetTicPos](#getticpos)|Возвращает позицию указанного деления в клиентских координатах.|  
|[CSliderCtrl::GetToolTips](#gettooltips)|Извлекает дескриптор элемента управления всплывающей подсказки для элемента управления "ползунок", если таковые имеются.|  
|[CSliderCtrl::SetBuddy](#setbuddy)|Назначает окно в связанном окне для элемента управления "ползунок".|  
|[CSliderCtrl::SetLineSize](#setlinesize)|Задает линейный размер элемента управления "ползунок".|  
|[CSliderCtrl::SetPageSize](#setpagesize)|Задает размер страницы для элемента управления "ползунок".|  
|[CSliderCtrl::SetPos](#setpos)|Задает текущее положение ползунка.|  
|[CSliderCtrl::SetRange](#setrange)|Задает минимальную и максимальную позицию для ползунка.|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|Задает положение для ползунка.|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|Задает минимальный позицию для ползунка.|  
|[CSliderCtrl::SetSelection](#setselection)|Задает диапазон текущего выделенного фрагмента.|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|Задает длину ползунок в текущем элементе управления trackbar.|  
|[CSliderCtrl::SetTic](#settic)|Задает положение указанного делений.|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|Задает интервал делений на шаг элемента управления "ползунок".|  
|[CSliderCtrl::SetTipSide](#settipside)|Положения элемента управления всплывающей подсказки используется элемент управления trackbar.|  
|[CSliderCtrl::SetToolTips](#settooltips)|Присваивает элемент управления подсказки к элементу управления "ползунок".|  
  
## <a name="remarks"></a>Примечания  
 «Ползунок» (также называется trackbar) — это окно, содержащее ползунка и необязательный деления. При перемещении ползунка, с помощью мыши или клавиши направление, элемент управления отправляет сообщения уведомления для указания изменения.  
  
 Элементы управления "ползунок" полезны в тех случаях, когда пользователю необходимо выбрать дискретное значение или набор последовательных значений в диапазоне. Например может использовать элемент управления "ползунок" позволяет пользователю устанавливать частота возврата клавиатуры с помощью ползунка метки данной шкалы.  
  
 Этот элемент управления (и, следовательно, `CSliderCtrl` класс) доступен только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних.  
  
 Перемещение ползунка на, указываемые при ее создании. Например, при указании, ползунок должен иметь диапазон пяти ползунок можно только занимают шесть позиции: позиции с левой стороны элемента управления "ползунок" и на одну позицию для каждого фрагмента в диапазоне. Как правило каждый из этих позиций идентифицируется деления.  
  
 Создание ползунка с помощью конструктора и **создать** функции-члена `CSliderCtrl`. После создания управления "ползунок", можно использовать функции-члены в `CSliderCtrl` изменения многих из его свойств. Изменения, выполненные включают Задание минимального и максимального позиции для ползунок, рисование делений, задание диапазон выбора и положения ползунка.  
  
 Дополнительные сведения об использовании `CSliderCtrl`, в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="clearsel"></a>CSliderCtrl::ClearSel  
 Отменяет текущее выделение в элементе управления "ползунок".  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bRedraw`  
 Перерисовывает флаг. Если этот параметр имеет **TRUE**, ползунок перерисовке после очистки выделение; в противном случае не перерисовке ползунок.  
  
##  <a name="cleartics"></a>CSliderCtrl::ClearTics  
 Удаляет текущий деления из элемента управления "ползунок".  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bRedraw`  
 Перерисовывает флаг. Если этот параметр имеет **TRUE**, ползунок перерисовке после очистки делений; в противном случае не перерисовке ползунок.  
  
##  <a name="create"></a>CSliderCtrl::Create  
 Создает элемент управления "ползунок" и прикрепляет его к `CSliderCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления "ползунок". Примените любое сочетание [стили элемента управления "ползунок"](http://msdn.microsoft.com/library/windows/desktop/bb760147), описанном в статье [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], к элементу управления.  
  
 `rect`  
 Задает размер и положение элемента управления "ползунок". Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает родительскому окну элемента управления "ползунок", обычно `CDialog`. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления "ползунок".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CSliderCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает элемент управления "ползунок" и прикрепляет его к `CSliderCtrl` объекта.  
  
 В зависимости от значения, заданные для `dwStyle`, элемент управления "ползунок" может иметь вертикальной или горизонтальной ориентации. Он может иметь делений шкалы на обеих сторонах обоих сторон или ни одного. Он также может использоваться для указания диапазона последовательных значений.  
  
 Чтобы применить расширенные стили окна в элемент управления "ползунок", вызовите [CreateEx](#createex) вместо **создать**.  
  
##  <a name="createex"></a>CSliderCtrl::CreateEx  
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
 Задает стиль элемента управления "ползунок". Примените любое сочетание [стили элемента управления "ползунок"](http://msdn.microsoft.com/library/windows/desktop/bb760147), описанном в статье [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], к элементу управления.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна будет создан в клиентские координаты `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенные стили Windows, заданные вводной части расширенный стиль Windows **WS_EX_**.  
  
##  <a name="csliderctrl"></a>CSliderCtrl::CSliderCtrl  
 Создает объект `CSliderCtrl`.  
  
```  
CSliderCtrl();
```  
  
##  <a name="getbuddy"></a>CSliderCtrl::GetBuddy  
 Извлекает дескриптор окна элемента управления контактному лицу ползунок в заданную позицию.  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `fLocation`  
 Логическое значение, указывающее, какой из двух дескрипторов окна контактному лицу для извлечения. Может принимать одно из следующих значений:  
  
- **Значение TRUE,** извлекается дескриптор контакту слева от ползунка. Если элемент управления "ползунок" использует `TBS_VERT` стиля, сообщения будут получены друг над ползунком.  
  
- **FALSE** извлекается дескриптор контакту справа от ползунка. Если элемент управления "ползунок" использует `TBS_VERT` стиля, сообщения будут получены друг ниже бегунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) , являющийся в связанном окне в расположении, заданном `fLocation`, или **NULL** Если ни одного окна контактному лицу существует в этом расположении.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TBM_GETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760178), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Описание стили элемента управления "ползунок" см. в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getchannelrect"></a>CSliderCtrl::GetChannelRect  
 Извлекает размер и положение ограничивающего прямоугольника для элемента управления "ползунок" канала.  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) когда функция возвращает объект, содержащий размер и положение канала ограничивающий прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 Канал представляет собой область, на которое перемещается ползунок и при выборе диапазон, который содержит выделение.  
  
##  <a name="getlinesize"></a>CSliderCtrl::GetLineSize  
 Получает размер строки для элемента управления "ползунок".  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер строки для элемента управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Размер строки влияет на объем на которое перемещается ползунок для **TB_LINEUP** и **TB_LINEDOWN** уведомления. Размер строки по умолчанию — 1.  
  
##  <a name="getnumtics"></a>CSliderCtrl::GetNumTics  
 Извлекает количество делений в элементе управления "ползунок".  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество делений в элементе управления "ползунок".  
  
##  <a name="getpagesize"></a>CSliderCtrl::GetPageSize  
 Получает размер страницы для элемента управления "ползунок".  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер страницы для элемента управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Влияет на размер страницы, сколько на которое перемещается ползунок для **TB_PAGEUP** и **TB_PAGEDOWN** уведомления.  
  
##  <a name="getpos"></a>CSliderCtrl::GetPos  
 Извлекает текущее положение ползунка в элементе управления "ползунок".  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая позиция.  
  
##  <a name="getrange"></a>CSliderCtrl::GetRange  
 Извлекает максимальное и минимальное позиции для ползунок в элементе управления "ползунок".  
  
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
  
##  <a name="getrangemax"></a>CSliderCtrl::GetRangeMax  
 Получает положение ползунка в элементе управления "ползунок".  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение положения элемента управления.  
  
##  <a name="getrangemin"></a>CSliderCtrl::GetRangeMin  
 Извлекает минимальное положение ползунка в элементе управления "ползунок".  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальное положение элемента управления.  
  
##  <a name="getselection"></a>CSliderCtrl::GetSelection  
 Извлекает начальные и конечные позиции текущего выделенного фрагмента в элементе управления "ползунок".  
  
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
  
##  <a name="getthumblength"></a>CSliderCtrl::GetThumbLength  
 Получает длину ползунок в текущем элементе управления trackbar.  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина ползунок в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TBM_GETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760201) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getthumbrect"></a>CSliderCtrl::GetThumbRect  
 Извлекает размер и положение ограничивающего прямоугольника для ползунок (бегунок) в элементе управления "ползунок".  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Указатель на `CRect` объект, содержащий прямоугольник, ограничивающий ползунок при возврате из функции.  
  
##  <a name="gettic"></a>CSliderCtrl::GetTic  
 Возвращает позицию делений в элементе управления "ползунок".  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nTic`  
 Отсчитываемый от нуля индекс, определение деления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положение указанного деления или - 1, если `nTic` не указывает допустимый индекс.  
  
##  <a name="getticarray"></a>CSliderCtrl::GetTicArray  
 Извлекает адрес массив, содержащий позицию делений для элемента управления "ползунок".  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес массива, содержащего позиции метки делений для элемента управления "ползунок".  
  
##  <a name="getticpos"></a>CSliderCtrl::GetTicPos  
 Извлекает текущий физическое расположение делений в элементе управления "ползунок".  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nTic`  
 Отсчитываемый от нуля индекс, определение деления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Физическое расположение, в клиентских координатах, указанный деления или - 1, если `nTic` не указывает допустимый индекс.  
  
##  <a name="gettooltips"></a>CSliderCtrl::GetToolTips  
 Извлекает дескриптор элемента управления всплывающей подсказки для элемента управления "ползунок", если таковые имеются.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта, или **NULL** если подсказки не используются. Если не используется элемент управления "ползунок" **TBS_TOOLTIPS** стиля, возвращаемым значением является **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TBM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760209), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Обратите внимание, что эта функция-член возвращает `CToolTipCtrl` объект, а не дескриптор элемента управления.  
  
 Описание стили элемента управления "ползунок" см. в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setbuddy"></a>CSliderCtrl::SetBuddy  
 Назначает окно в связанном окне для элемента управления "ползунок".  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndBuddy`  
 Указатель на `CWnd` объект, который будет установлен в качестве элемента управления "ползунок" контактному лицу.  
  
 `fLocation`  
 Значение, указывающее расположение, в которой отображается в связанном окне. Это значение может быть одним из следующих:  
  
- **Значение TRUE,** контакта будет отображаться слева от trackbar, если элемент управления trackbar использует `TBS_HORZ` стиля. Если используется trackbar `TBS_VERT` стиля контакта отображается над элементом управления trackbar.  
  
- **FALSE** контактов будет отображаться справа от trackbar, если элемент управления trackbar использует `TBS_HORZ` стиля. Если используется trackbar `TBS_VERT` стиля контакта отображается под элементом управления trackbar.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, который ранее был назначен управления "ползунок" в этом расположении.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TBM_SETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760213), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Обратите внимание, что эта функция-член использует указатели на `CWnd` объекты, а не дескрипторами окон для возвращаемого значения и параметры.  
  
 Описание стили элемента управления "ползунок" см. в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setlinesize"></a>CSliderCtrl::SetLineSize  
 Задает размер строки для элемента управления "ползунок".  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 `nSize`  
 Новый размер строки элемента управления "ползунок".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий размер строки.  
  
### <a name="remarks"></a>Примечания  
 Размер строки влияет на объем на которое перемещается ползунок для **TB_LINEUP** и **TB_LINEDOWN** уведомления.  
  
##  <a name="setpagesize"></a>CSliderCtrl::SetPageSize  
 Задает размер страницы для элемента управления "ползунок".  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 `nSize`  
 Новый размер страницы элемента управления "ползунок".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий размер страницы.  
  
### <a name="remarks"></a>Примечания  
 Влияет на размер страницы, сколько на которое перемещается ползунок для **TB_PAGEUP** и **TB_PAGEDOWN** уведомления.  
  
##  <a name="setpos"></a>CSliderCtrl::SetPos  
 Задает текущее положение ползунка в элементе управления "ползунок".  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Указывает новое положение ползунка.  
  
##  <a name="setrange"></a>CSliderCtrl::SetRange  
 Задает для ползунок в элементе управления "ползунок" диапазон (должностей минимальное и максимальное).  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `nMin`  
 Минимальное положение ползунка.  
  
 `nMax`  
 Значение положения ползунка.  
  
 `bRedraw`  
 Флаг перерисовку. Если этот параметр имеет **TRUE**, ползунок перерисовке после значения диапазона; в противном случае не перерисовке ползунок.  
  
##  <a name="setrangemax"></a>CSliderCtrl::SetRangeMax  
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
 Флаг перерисовку. Если этот параметр имеет **TRUE**, ползунок перерисовке после значения диапазона; в противном случае не перерисовке ползунок.  
  
##  <a name="setrangemin"></a>CSliderCtrl::SetRangeMin  
 Задает минимальный диапазон для ползунок в элементе управления "ползунок".  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `nMin`  
 Минимальное положение ползунка.  
  
 `bRedraw`  
 Флаг перерисовку. Если этот параметр имеет **TRUE**, ползунок перерисовке после значения диапазона; в противном случае не перерисовке ползунок.  
  
##  <a name="setselection"></a>CSliderCtrl::SetSelection  
 Задает начальные и конечные позиции для текущего выделения в элементе управления "ползунок".  
  
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
  
##  <a name="setthumblength"></a>CSliderCtrl::SetThumbLength  
 Задает длину ползунок в текущем элементе управления trackbar.  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nLength`|Длина ползунок в пикселях.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод требует, что элемент управления trackbar было присвоено [TBS_FIXEDLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760147) стиля.  
  
 Этот метод отправляет [TBM_SETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760234) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_sliderCtrl`, который используется для доступа к текущей управления trackbar. В примере также определяется переменной, `thumbLength`, который используется для хранения длины по умолчанию компонента управления trackbar thumb. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает компонент управления trackbar thumb дважды длина по умолчанию.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="settic"></a>CSliderCtrl::SetTic  
 Задает позицию делений в элементе управления "ползунок".  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>Параметры  
 `nTic`  
 Положение деления. Этот параметр необходимо указать положительное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если деления — значение NULL. в противном случае — 0.  
  
##  <a name="setticfreq"></a>CSliderCtrl::SetTicFreq  
 Задает частоту, с какой деления метки отображаются в ползунка.  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>Параметры  
 *nFreq*  
 Частота делений.  
  
### <a name="remarks"></a>Примечания  
 Например если частота имеет значение 2, деление отображается для каждого приращения в диапазоне ползунка. Значение по умолчанию для частоты-1 (то есть каждый шаг в диапазоне связан с деление).  
  
 Необходимо создать элемент управления с `TBS_AUTOTICKS` стиль для использования этой функции. Дополнительные сведения см. в разделе [CSliderCtrl::Create](#create).  
  
##  <a name="settipside"></a>CSliderCtrl::SetTipSide  
 Положения элемента управления всплывающей подсказки используется элемент управления trackbar.  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>Параметры  
 `nLocation`  
 Значение, представляющее расположение, в которой отображается элемент управления tooltip. Список возможных значений см. в разделе сообщение Win32 [TBM_SETTIPSIDE](http://msdn.microsoft.com/library/windows/desktop/bb760240), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, представляющее предыдущее расположение элемента управления всплывающей подсказки. Возвращаемое значение равно одному из возможных значений для `nLocation`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 **TBM_SETTIPSIDE**, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Ползунок управления, использующих **TBS_TOOLTIPS** стиля отображения подсказки. Описание стили элемента управления "ползунок" см. в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
##  <a name="settooltips"></a>CSliderCtrl::SetToolTips  
 Присваивает элемент управления подсказки к элементу управления "ползунок".  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndTip`  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объект, содержащий всплывающих подсказок для использования с элементом управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TBM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760242), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. При создании ползунок с **TBS_TOOLTIPS** стиля, он создает элемент управления всплывающей подсказки по умолчанию, который отображается с помощью ползунка, отображается текущее положение ползунка. Описание стили элемента управления "ползунок" см. в разделе [стили элемента управления Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) в [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CProgressCtrl](../../mfc/reference/cprogressctrl-class.md)

