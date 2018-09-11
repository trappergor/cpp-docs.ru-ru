---
title: Класс CSliderCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6bd20852f1dfd278d4ae58cc6c67d6047579cd08
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693196"
---
# <a name="csliderctrl-class"></a>Класс CSliderCtrl
Предоставляет функциональные возможности стандартного элемента управления "ползунок" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Создает объект `CSliderCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|Очищает текущее выделение в элементе управления "ползунок".|  
|[CSliderCtrl::ClearTics](#cleartics)|Удаляет текущий делений из элемента управления "ползунок".|  
|[CSliderCtrl::Create](#create)|Создает элемент управления "ползунок" и присоединяет его к `CSliderCtrl` объекта.|  
|[CSliderCtrl::CreateEx](#createex)|Создает элемент управления "ползунок" с указанным расширенные стили Windows и присоединяет его к `CSliderCtrl` объекта.|  
|[CSliderCtrl::GetBuddy](#getbuddy)|Получает дескриптор элемента управления "ползунок" связанным окном в заданную позицию.|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Получает размер элемента управления "ползунок" канала.|  
|[CSliderCtrl::GetLineSize](#getlinesize)|Получает линейный размер ползунка.|  
|[CSliderCtrl::GetNumTics](#getnumtics)|Получает количество делений в элементе управления "ползунок".|  
|[CSliderCtrl::GetPageSize](#getpagesize)|Получает размер страницы элемента управления "ползунок".|  
|[CSliderCtrl::GetPos](#getpos)|Извлекает текущее положение ползунка.|  
|[CSliderCtrl::GetRange](#getrange)|Возвращает значение, минимальное и максимальное позиции ползунка.|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|Получает максимальное положение ползунка.|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|Получает минимальное положение ползунка.|  
|[CSliderCtrl::GetSelection](#getselection)|Извлекает диапазон текущего выделенного фрагмента.|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|Получает длину ползунок в текущий элемент управления trackbar.|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Извлекает размер бегунка элемента управления "ползунок".|  
|[CSliderCtrl::GetTic](#gettic)|Возвращает позицию указанного деления.|  
|[CSliderCtrl::GetTicArray](#getticarray)|Извлекает массив метки делений для элемента управления "ползунок".|  
|[CSliderCtrl::GetTicPos](#getticpos)|Возвращает позицию указанного деления, в координатах клиентской области окна.|  
|[CSliderCtrl::GetToolTips](#gettooltips)|Получает дескриптор элемента управления tooltip, назначенный элементу управления "ползунок", если таковые имеются.|  
|[CSliderCtrl::SetBuddy](#setbuddy)|Назначает окно в связанном окне для элемента управления "ползунок".|  
|[CSliderCtrl::SetLineSize](#setlinesize)|Задает линейный размер ползунка.|  
|[CSliderCtrl::SetPageSize](#setpagesize)|Задает размер страницы элемента управления "ползунок".|  
|[CSliderCtrl::SetPos](#setpos)|Задает текущее положение ползунка.|  
|[CSliderCtrl::SetRange](#setrange)|Задает минимальное и максимальное позиции ползунка.|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|Задает положение ползунка.|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|Задает минимальное положение ползунка.|  
|[CSliderCtrl::SetSelection](#setselection)|Задает диапазон текущего выделенного фрагмента.|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|Задает длину ползунок в элементе управления trackbar текущей.|  
|[CSliderCtrl::SetTic](#settic)|Задает положение указанного деления.|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|Задает частоту тактов для увеличения элемента управления "ползунок".|  
|[CSliderCtrl::SetTipSide](#settipside)|Позиции элемента управления всплывающей подсказки используется элемент управления trackbar.|  
|[CSliderCtrl::SetToolTips](#settooltips)|Назначает элемент управления всплывающей подсказки к элементу управления "ползунок".|  
  
## <a name="remarks"></a>Примечания  
 «Ползунок» (также называется trackbar) — это окно, содержащее ползунок и дополнительну метки. При перемещении ползунка, с помощью мыши или клавиш направление, элемент управления отправляет сообщения уведомления, указывающее на изменение.  
  
 Элементы управления "ползунок" полезны в тех случаях, когда требуется пользователю выбрать дискретное значение или набор последовательные значения в диапазоне. Например можно использовать элемент управления "ползунок" позволяет пользователю устанавливать скорость повтора клавиатуры, переместив ползунок для заданного деления.  
  
 Этот элемент управления (и, следовательно `CSliderCtrl` класс) доступны только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних версиях.  
  
 Ползунок перемещение на указанные вами при ее создании. Например, при указании у ползунка диапазона до пяти ползунка можно только занимают шесть позиции: позиция с левой стороны элемента управления "ползунок" и на одну позицию для каждого фрагмента в диапазоне. Как правило каждый из этих позиций определяется путем деления.  
  
 Создание ползунка с помощью конструктора и `Create` функцию-член `CSliderCtrl`. После создания элемента управления "ползунок", можно использовать функции-члены в `CSliderCtrl` изменения многих из его свойств. Изменения, которые планируется сделать включают Задание минимального и максимального позиции для ползунка, рисование делений, задание диапазон выделения и положения ползунка.  
  
 Дополнительные сведения об использовании `CSliderCtrl`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="clearsel"></a>  CSliderCtrl::ClearSel  
 Очищает текущее выделение в элементе управления "ползунок".  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *bRedraw*  
 Перерисовывает флаг. Если этот параметр имеет значение TRUE, ползунок перерисовке после выделения снят. в противном случае ползунка не переписывается.  
  
##  <a name="cleartics"></a>  CSliderCtrl::ClearTics  
 Удаляет текущий делений из элемента управления "ползунок".  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *bRedraw*  
 Перерисовывает флаг. Если этот параметр имеет значение TRUE, ползунок будет перерисован после очистки делений; в противном случае ползунка не переписывается.  
  
##  <a name="create"></a>  CSliderCtrl::Create  
 Создает элемент управления "ползунок" и присоединяет его к `CSliderCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *dwStyle*  
 Задает стиль элемента управления "ползунок". Применить любое сочетание [стили элемента управления "ползунок"](/windows/desktop/Controls/trackbar-control-styles), описанные в пакет SDK для Windows, к элементу управления.  
  
 *Rect*  
 Задает размер и положение элемента управления "ползунок". Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 *pParentWnd*  
 Указывает родительскому окну элемента управления "ползунок", обычно `CDialog`. Он не должен иметь значение NULL.  
  
 *nID*  
 Указывает идентификатор элемента управления "ползунок".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 При создании `CSliderCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает элемент управления "ползунок" и присоединяет его к `CSliderCtrl` объекта.  
  
 В зависимости от значения, заданные для *dwStyle*, элемент управления "ползунок" может иметь вертикальную или горизонтальную ориентацию. Он может иметь деления для обеих сторон, как стороны или ни одного. Он также может использоваться для указания диапазона последовательных значений.  
  
 Чтобы применить расширенные стили окна к элементу управления "ползунок", вызовите [CreateEx](#createex) вместо `Create`.  
  
##  <a name="createex"></a>  CSliderCtrl::CreateEx  
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
 *dwExStyle*  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.  
  
 *dwStyle*  
 Задает стиль элемента управления "ползунок". Применить любое сочетание [стили элемента управления "ползунок"](/windows/desktop/Controls/trackbar-control-styles), описанные в пакет SDK для Windows, к элементу управления.  
  
 *Rect*  
 Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.  
  
 *pParentWnd*  
 Указатель на окно, которое является родительским для элемента управления.  
  
 *nID*  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.  
  
##  <a name="csliderctrl"></a>  CSliderCtrl::CSliderCtrl  
 Создает объект `CSliderCtrl`.  
  
```  
CSliderCtrl();
```  
  
##  <a name="getbuddy"></a>  CSliderCtrl::GetBuddy  
 Получает дескриптор элемента управления "ползунок" связанным окном в заданную позицию.  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *fLocation*  
 Логическое значение, указывающее, какой из двух дескрипторов окон buddy для извлечения. Может принимать одно из следующих значений:  
  
- Значение TRUE Получает дескриптор buddy влево ползунка. Если элемент управления "ползунок" использует стиль TBS_VERT, сообщение будет извлекать buddy выше ползунка.  
  
- FALSE Получает дескриптор buddy справа от ползунка. Если элемент управления "ползунок" использует стиль TBS_VERT, сообщение будет извлекать buddy под ползунком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, являющийся в связанном окне в местоположении, указанном по *fLocation*, или значение NULL, если окно не buddy существует в этом расположении.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [TBM_GETBUDDY](/windows/desktop/Controls/tbm-getbuddy), как описано в пакете Windows SDK. Описание стили элемента управления "ползунок", см. в разделе [стили элемента управления Trackbar](/windows/desktop/Controls/trackbar-control-styles) в пакете Windows SDK.  
  
##  <a name="getchannelrect"></a>  CSliderCtrl::GetChannelRect  
 Извлекает размер и положение ограничивающего прямоугольника для элемента управления "ползунок" канала.  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lprc*  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) когда функция возвращает объект, содержащий размер и положение канала ограничивающего прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Канал — это область над ползунок также увеличивает и при выборе диапазона, который содержит выделение.  
  
##  <a name="getlinesize"></a>  CSliderCtrl::GetLineSize  
 Извлекает размер строки для элемента управления "ползунок".  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер строки для элемента управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Размер строки влияет на объем ползунок также увеличивает TB_LINEUP и TB_LINEDOWN уведомлений. Линейный размер по умолчанию равно 1.  
  
##  <a name="getnumtics"></a>  CSliderCtrl::GetNumTics  
 Получает количество делений в элементе управления "ползунок".  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество делений в элементе управления "ползунок".  
  
##  <a name="getpagesize"></a>  CSliderCtrl::GetPageSize  
 Получает размер страницы для элемента управления "ползунок".  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер страницы для элемента управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Размер страницы влияет на объем ползунок также увеличивает TB_PAGEUP и TB_PAGEDOWN уведомлений.  
  
##  <a name="getpos"></a>  CSliderCtrl::GetPos  
 Извлекает текущее положение ползунка в элементе управления "ползунок".  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая позиция.  
  
##  <a name="getrange"></a>  CSliderCtrl::GetRange  
 Извлекает максимальное и минимальное позиции для ползунок в элементе управления "ползунок".  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *Nмин.*  
 Ссылка на целое число, которое получает минимальное положение.  
  
 *Nмакс.*  
 Ссылка на целое число, которое получает максимальное положение.  
  
### <a name="remarks"></a>Примечания  
 Эта функция копирует значения в целые числа, ссылается *Nмин.* и *Nмакс*.  
  
##  <a name="getrangemax"></a>  CSliderCtrl::GetRangeMax  
 Получает максимальное положение ползунка в элементе управления "ползунок".  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Позиции максимума элемента управления.  
  
##  <a name="getrangemin"></a>  CSliderCtrl::GetRangeMin  
 Получает минимальное положение ползунка в элементе управления "ползунок".  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Позиции минимума элемента управления.  
  
##  <a name="getselection"></a>  CSliderCtrl::GetSelection  
 Получает начальное и конечное положение текущего выделения в элементе управления "ползунок".  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *Nмин.*  
 Ссылка на целое число, Получает позицию текущего выделенного фрагмента.  
  
 *Nмакс.*  
 Ссылка на целое число, Получает конечную позицию текущего выделенного фрагмента.  
  
##  <a name="getthumblength"></a>  CSliderCtrl::GetThumbLength  
 Получает длину ползунок в текущий элемент управления trackbar.  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина "ползунок", в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TBM_GETTHUMBLENGTH](/windows/desktop/Controls/tbm-getthumblength) сообщения, который описан в пакете Windows SDK.  
  
##  <a name="getthumbrect"></a>  CSliderCtrl::GetThumbRect  
 Извлекает размер и положение ограничивающего прямоугольника для ползунка (бегунка) в элементе управления "ползунок".  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lprc*  
 Указатель на `CRect` объект, содержащий ограничивающий прямоугольник для ползунка при возврате функции.  
  
##  <a name="gettic"></a>  CSliderCtrl::GetTic  
 Возвращает позицию делений в элементе управления "ползунок".  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nTic*  
 Отсчитываемый от нуля индекс, определяющий деления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положение указанного деления или - 1, если *nTic* не указывает допустимый индекс.  
  
##  <a name="getticarray"></a>  CSliderCtrl::GetTicArray  
 Извлекает адрес массив, содержащий положения делений для элемента управления "ползунок".  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес массив, содержащий метки делений для элемента управления "ползунок".  
  
##  <a name="getticpos"></a>  CSliderCtrl::GetTicPos  
 Извлекает текущий физическое расположение делений в элементе управления "ползунок".  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nTic*  
 Отсчитываемый от нуля индекс, определяющий деления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Физическое расположение, в координатах клиентской области окна, заданного деления или - 1, если *nTic* не указывает допустимый индекс.  
  
##  <a name="gettooltips"></a>  CSliderCtrl::GetToolTips  
 Получает дескриптор элемента управления tooltip, назначенный элементу управления "ползунок", если таковые имеются.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта, или значение NULL, если всплывающие подсказки не используются. Если элемент управления "ползунок", использует ли стиль TBS_TOOLTIPS, возвращается значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [TBM_GETTOOLTIPS](/windows/desktop/Controls/tbm-gettooltips), как описано в пакете Windows SDK. Обратите внимание, что эта функция-член возвращает `CToolTipCtrl` объекта вместо дескриптора элемента управления.  
  
 Описание стили элемента управления "ползунок", см. в разделе [стили элемента управления Trackbar](/windows/desktop/Controls/trackbar-control-styles) в пакете Windows SDK.  
  
##  <a name="setbuddy"></a>  CSliderCtrl::SetBuddy  
 Назначает окно в связанном окне для элемента управления "ползунок".  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndBuddy*  
 Указатель на `CWnd` объект, который будет установлен в качестве buddy управления "ползунок".  
  
 *fLocation*  
 Значение, указывающее расположение, в которой отображается в связанном окне. Это значение может быть одно из следующих значений:  
  
- Значение TRUE, контактов будет отображаться слева от trackbar Если элемент управления trackbar использует стиль TBS_HORZ. Если ползунок использует стиль TBS_VERT, buddy появляется над элементом управления trackbar.  
  
- FALSE контактов будет отображаться справа от trackbar Если элемент управления trackbar использует стиль TBS_HORZ. Если ползунок использует стиль TBS_VERT, buddy появляется элемент управления trackbar.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, который ранее был назначен управления "ползунок" в этом расположении.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [TBM_SETBUDDY](/windows/desktop/Controls/tbm-setbuddy), как описано в пакете Windows SDK. Обратите внимание, что эта функция-член использует указатели на `CWnd` объектов, а не дескрипторов окон для возвращаемого значения и параметров.  
  
 Описание стили элемента управления "ползунок", см. в разделе [стили элемента управления Trackbar](/windows/desktop/Controls/trackbar-control-styles) в пакете Windows SDK.  
  
##  <a name="setlinesize"></a>  CSliderCtrl::SetLineSize  
 Задает размер строки для элемента управления "ползунок".  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 *nSize*  
 Новый размер строки элемента управления "ползунок".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий размер строки.  
  
### <a name="remarks"></a>Примечания  
 Размер строки влияет на объем ползунок также увеличивает TB_LINEUP и TB_LINEDOWN уведомлений.  
  
##  <a name="setpagesize"></a>  CSliderCtrl::SetPageSize  
 Задает размер страницы для элемента управления "ползунок".  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 *nSize*  
 Новый размер страницы элемента управления "ползунок".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий размер страницы.  
  
### <a name="remarks"></a>Примечания  
 Размер страницы влияет на объем ползунок также увеличивает TB_PAGEUP и TB_PAGEDOWN уведомлений.  
  
##  <a name="setpos"></a>  CSliderCtrl::SetPos  
 Задает текущее положение ползунка в элементе управления "ползунок".  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>Параметры  
 *nPos*  
 Задает новое положение ползунка.  
  
##  <a name="setrange"></a>  CSliderCtrl::SetRange  
 Задает диапазон (минимальные и максимальные позиций) для ползунок в элементе управления "ползунок".  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *Nмин.*  
 Минимальное положение ползунка.  
  
 *Nмакс.*  
 Значение положения ползунка.  
  
 *bRedraw*  
 Флаг перерисовки. Если этот параметр имеет значение TRUE, ползунок будет перерисован после диапазона; в противном случае ползунка не переписывается.  
  
##  <a name="setrangemax"></a>  CSliderCtrl::SetRangeMax  
 Задает максимальный диапазон для ползунок в элементе управления "ползунок".  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *Nмакс.*  
 Значение положения ползунка.  
  
 *bRedraw*  
 Флаг перерисовки. Если этот параметр имеет значение TRUE, ползунок будет перерисован после диапазона; в противном случае ползунка не переписывается.  
  
##  <a name="setrangemin"></a>  CSliderCtrl::SetRangeMin  
 Задает минимальный диапазон для ползунок в элементе управления "ползунок".  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *Nмин.*  
 Минимальное положение ползунка.  
  
 *bRedraw*  
 Флаг перерисовки. Если этот параметр имеет значение TRUE, ползунок будет перерисован после диапазона; в противном случае ползунка не переписывается.  
  
##  <a name="setselection"></a>  CSliderCtrl::SetSelection  
 Задает начальное и конечное положения для текущего выделения в элементе управления "ползунок".  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 *Nмин.*  
 Начальная позиция для ползунка.  
  
 *Nмакс.*  
 Конечное положение ползунка.  
  
##  <a name="setthumblength"></a>  CSliderCtrl::SetThumbLength  
 Задает длину ползунок в элементе управления trackbar текущей.  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] *nLength*|Длина ползунка в пикселях.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод требует, что элемент управления trackbar было присвоено [TBS_FIXEDLENGTH](/windows/desktop/Controls/trackbar-control-styles) стиля.  
  
 Этот метод отправляет [TBM_SETTHUMBLENGTH](/windows/desktop/Controls/tbm-setthumblength) сообщения, который описан в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_sliderCtrl`, который используется для доступа к текущим элементом управления trackbar. В примере также определяется переменной, `thumbLength`, который используется для хранения длины по умолчанию элемент управления trackbar thumb компонента. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает компонент бегунка элемента управления trackbar дважды длина по умолчанию.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="settic"></a>  CSliderCtrl::SetTic  
 Задает позицию делений в элементе управления "ползунок".  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>Параметры  
 *nTic*  
 Положение деления. Этот параметр необходимо указать положительное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если деления — значение NULL. в противном случае 0.  
  
##  <a name="setticfreq"></a>  CSliderCtrl::SetTicFreq  
 Задает частоту, с какой делений метки отображаются ползунка.  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>Параметры  
 *nFreq*  
 Частота делений.  
  
### <a name="remarks"></a>Примечания  
 Например если частота имеет значение 2, деление отображается для каждого приращения, в диапазоне ползунка. Значение по умолчанию для частоты-1 (то есть каждый шаг в диапазоне связан с деления).  
  
 Необходимо создать элемент управления с TBS_AUTOTICKS стиль для использования этой функции. Дополнительные сведения см. в разделе [CSliderCtrl::Create](#create).  
  
##  <a name="settipside"></a>  CSliderCtrl::SetTipSide  
 Позиции элемента управления всплывающей подсказки используется элемент управления trackbar.  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>Параметры  
 *nLocation*  
 Значение, представляющее место, в котором для отображения элемента управления tooltip. Список возможных значений см. в разделе сообщение Win32 [TBM_SETTIPSIDE](/windows/desktop/Controls/tbm-settipside), как описано в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, представляющее предыдущее расположение элемента управления всплывающей подсказки. Возвращаемое значение равно одно из возможных значений для *nLocation*.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 TBM_SETTIPSIDE, как описано в пакете Windows SDK. Элементы управления "ползунок", использующие TBS_TOOLTIPS стиль отображения подсказки. Описание стили элемента управления "ползунок", см. в разделе [стили элемента управления Trackbar](/windows/desktop/Controls/trackbar-control-styles) в пакете Windows SDK.  
  
##  <a name="settooltips"></a>  CSliderCtrl::SetToolTips  
 Назначает элемент управления всплывающей подсказки к элементу управления "ползунок".  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndTip*  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объект, содержащий всплывающие подсказки для использования с элементом управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [TBM_SETTOOLTIPS](/windows/desktop/Controls/tbm-settooltips), как описано в пакете Windows SDK. Когда элемент управления "ползунок" создается со стилем TBS_TOOLTIPS, он создает элемент управления подсказки по умолчанию, которое отображается рядом с ползунком, отображение текущей позиции ползунка. Описание стили элемента управления "ползунок", см. в разделе [стили элемента управления Trackbar](/windows/desktop/Controls/trackbar-control-styles) в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CProgressCtrl](../../mfc/reference/cprogressctrl-class.md)
