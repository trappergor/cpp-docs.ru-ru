---
title: "CProgressCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class
- progress controls [C++], CProgressCtrl class
- Internet Explorer 4.0 common controls
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
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
ms.openlocfilehash: 6c0e9bc16f88018c9f258504924670cc2be31d28
ms.lasthandoff: 02/24/2017

---
# <a name="cprogressctrl-class"></a>CProgressCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "индикатор выполнения" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Создает объект `CProgressCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CProgressCtrl::Create](#create)|Создает элемент управления progress bar и присоединяет его к `CProgressCtrl` объекта.|  
|[CProgressCtrl::CreateEx](#createex)|Создает элемент управления хода выполнения с указанным расширенные стили Windows и присоединяет его к `CProgressCtrl` объекта.|  
|[CProgressCtrl::GetBarColor](#getbarcolor)|Возвращает цвет полосы индикатора хода выполнения для текущего индикатора.|  
|[CProgressCtrl::GetBkColor](#getbkcolor)|Возвращает цвет фона индикатора хода выполнения.|  
|[CProgressCtrl::GetPos](#getpos)|Получает текущее положение индикатора хода выполнения.|  
|[CProgressCtrl::GetRange](#getrange)|Возвращает нижнюю и верхнюю границы диапазона индикатора.|  
|[CProgressCtrl::GetState](#getstate)|Возвращает состояние текущего индикатора.|  
|[CProgressCtrl::GetStep](#getstep)|Получает шаг приращения идентификатора в индикатора хода выполнения для текущего индикатора.|  
|[CProgressCtrl::OffsetPos](#offsetpos)|Увеличивает текущую позицию индикатора на заданное значение приращения и перерисовывает панели, чтобы отразить новое место.|  
|[CProgressCtrl::SetBarColor](#setbarcolor)|Задает цвет индикатора индикатор хода выполнения в текущем индикатора.|  
|[CProgressCtrl::SetBkColor](#setbkcolor)|Задает цвет фона для индикатора.|  
|[CProgressCtrl::SetMarquee](#setmarquee)|Отключает режим бегущей строки или отключить для текущего индикатора.|  
|[CProgressCtrl::SetPos](#setpos)|Задает текущую позицию для индикатора и перерисовывает панели, чтобы отразить новое место.|  
|[CProgressCtrl::SetRange](#setrange)|Задает минимальный и максимальный диапазоны для индикатора и перерисовывает панели, чтобы отразить новые диапазоны.|  
|[CProgressCtrl::SetState](#setstate)|Задает состояние текущего элемента управления "Индикатор выполнения".|  
|[CProgressCtrl::SetStep](#setstep)|Задает шаг прироста для индикатора.|  
|[CProgressCtrl::StepIt](#stepit)|Увеличивает текущую позицию для индикатора на шаг приращения (см. [SetStep](#setstep)) и перерисовывает панели, чтобы отразить новое место.|  
  
## <a name="remarks"></a>Примечания  
 Индикатор выполнения является окно, которое может использоваться приложением для отображения хода выполнения длительной операции. Он состоит из прямоугольника, который постепенно заполняется, слева, справа, с системой цвет подсветки мере выполнения операции.  
  
 Элемент управления progress bar имеет диапазон и текущую позицию. Диапазон представляет общее время выполнения, а текущая позиция ход сделанные приложения по выполнению операции. Процедура окна использует диапазон и текущее положение, чтобы определить процент индикатора хода выполнения для заполнения цвет выделения. Поскольку диапазон и текущее положение значения выражаются в виде целых чисел со знаком, возможный диапазон значений текущей позиции — из â €«2 147 483 648 для 2 147 483 647 включительно.  
  
 Дополнительные сведения об использовании `CProgressCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CProgressCtrl с помощью](../../mfc/using-cprogressctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="cprogressctrl"></a>CProgressCtrl::CProgressCtrl  
 Создает объект `CProgressCtrl`.  
  
```  
CProgressCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CProgressCtrl` , вызовите `CProgressCtrl::Create` для создания индикатора.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl&#1;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]  
  
##  <a name="create"></a>CProgressCtrl::Create  
 Создает элемент управления progress bar и присоединяет его к `CProgressCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль окна хода выполнения. Примените любое сочетание stylesdescribed окна в [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], кроме следующих индикатора стили элемента управления, к элементу управления:  
  
- `PBS_VERTICAL`Отображает ход выполнения сведения по вертикали, сверху вниз. Без указания этого флага индикатор выполнения отображается горизонтально, слева направо.  
  
- `PBS_SMOOTH`Отображает постепенно, плавное заполнение индикатора. Без указания этого флага элемент управления будет заполнить блоки.  
  
 `rect`  
 Задает размер и положение окна хода выполнения. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры. Поскольку элемент управления должен быть дочернего окна, указанный координаты указываются относительно клиентской области `pParentWnd`.  
  
 `pParentWnd`  
 Указывает индикатор родительского окна элемента управления, обычно `CDialog`. Оно не должно быть **значение NULL.**  
  
 `nID`  
 Указывает идентификатор элемента управления панели хода выполнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если `CProgressCtrl` объект успешно создан; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Создании `CProgressCtrl` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CProgressCtrl` , а затем вызвать **создать**, который создает элемент управления progress bar.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl&#2;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CProgressCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связывает его с `CProgressCtrl` объекта.  
  
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
 Задает стиль окна хода выполнения. Примените любое сочетание стилей окна, описанные в [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
##  <a name="getbarcolor"></a>CProgressCtrl::GetBarColor  
 Возвращает цвет полосы индикатора хода выполнения для текущего индикатора.  
  
```  
COLORREF GetBarColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет текущий индикатор в виде [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, или `CLR_DEFAULT` Если цвет по умолчанию цвет панели индикатор хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PBM_GETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760826) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getbkcolor"></a>CProgressCtrl::GetBkColor  
 Возвращает цвет фона индикатора хода выполнения.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет фона текущего индикатора в виде [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PBM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760828) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getpos"></a>CProgressCtrl::GetPos  
 Получает текущую позицию индикатора хода выполнения.  
  
```  
int GetPos();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положение индикатора.  
  
### <a name="remarks"></a>Примечания  
 Положение индикатора не физическое расположение на экране, но вместо между верхней и нижней диапазона указывается в [SetRange](#setrange).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl&#3;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]  
  
##  <a name="getrange"></a>CProgressCtrl::GetRange  
 Возвращает текущий нижний и верхний пределы или диапазона индикатора.  
  
```  
void GetRange(
    int& nLower,  
    int& nUpper);
```  
  
### <a name="parameters"></a>Параметры  
 `nLower`  
 Ссылка на целое число, получать нижней границы индикатора.  
  
 `nUpper`  
 Ссылка на целое число, получение верхнее предельное значение индикатора.  
  
### <a name="remarks"></a>Примечания  
 Эта функция копирует значения нижний и верхний пределы целых чисел, ссылается `nLower` и `nUpper`соответственно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl&#4;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]  
  
##  <a name="getstate"></a>CProgressCtrl::GetState  
 Возвращает состояние текущего индикатора.  
  
```  
int GetState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние текущего индикатора, которое является одним из следующих значений:  
  
|Значение|Состояние|  
|-----------|-----------|  
|`PBST_NORMAL`|Выполняется|  
|`PBST_ERROR`|Ошибка|  
|`PBST_PAUSED`|Paused|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PBM_GETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760834) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода извлекает состояние текущей индикатора.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]  
  
##  <a name="getstep"></a>CProgressCtrl::GetStep  
 Получает шаг приращения идентификатора в индикатора хода выполнения для текущего индикатора.  
  
```  
int GetStep() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Шаг приращения индикатора хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Шаг приращения является величина, на которую вызов [CProgressCtrl::StepIt](#stepit) увеличивает текущее положение индикатора хода выполнения.  
  
 Этот метод отправляет [PBM_GETSTEP](http://msdn.microsoft.com/library/windows/desktop/bb760836) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода извлекает шаг приращения из текущего индикатора.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]  
  
##  <a name="offsetpos"></a>CProgressCtrl::OffsetPos  
 Перемещает индикатор текущего положения элемента управления значение приращения, заданные `nPos` и перерисовывает панели, чтобы отразить новое место.  
  
```  
int OffsetPos(int nPos);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Сумма, чтобы переместить позицию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В предыдущее расположение поля индикатора.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl&#5;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]  
  
##  <a name="setbarcolor"></a>CProgressCtrl::SetBarColor  
 Задает цвет индикатора индикатор хода выполнения в текущем индикатора.  
  
```  
COLORREF SetBarColor(COLORREF clrBar);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `clrBar`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, которое указывает новый цвет индикатора индикатор хода выполнения. Укажите `CLR_DEFAULT` заставить индикатор использовать цвета по умолчанию.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий цвет индикатора индикатор хода выполнения в виде [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, или `CLR_DEFAULT` Если цвет по умолчанию цвет индикатора индикатор хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 `SetBarColor` Метод задает индикатор цвет только тогда, когда [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] [темы](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx) не действует.  
  
 Этот метод отправляет [PBM_SETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760838) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере изменяется цвет индикатора хода выполнения на красный, зеленый, синий или значение по умолчанию.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]  
  
##  <a name="setbkcolor"></a>CProgressCtrl::SetBkColor  
 Задает цвет фона для индикатора.  
  
```  
COLORREF SetBkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Параметры  
 `clrNew`  
 Объект **COLORREF** значение, которое указывает новый цвет фона. Укажите `CLR_DEFAULT` значение по умолчанию цвет фона для индикатора хода выполнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, указывающее, на предыдущий цвет фона или **CLR_DEFAULT** Если цвет по умолчанию цвет фона.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl №&6;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]  
  
##  <a name="setmarquee"></a>CProgressCtrl::SetMarquee  
 Отключает режим бегущей строки или отключить для текущего индикатора.  
  
```  
BOOL SetMarquee(
    BOOL fMarqueeMode,   
    int nInterval);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `fMarqueeMode`|`true`Чтобы включить режим бегущей строки, или `false` для отключения режима бегущей строки.|  
|[in] `nInterval`|Время в миллисекундах между обновлениями анимации бегущей строки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод всегда возвращает значение `true`.  
  
### <a name="remarks"></a>Примечания  
 Включен режим бегущей строки, анимированный индикатор хода выполнения и прокрутка, например вход на бегущую строку.  
  
 Этот метод отправляет [PBM_SETMARQUEE](http://msdn.microsoft.com/library/windows/desktop/bb760842) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода запускает и останавливает прокрутка анимации бегущей строки.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]  
  
##  <a name="setpos"></a>CProgressCtrl::SetPos  
 Задает сведения о ходе панели текущую позицию элемента управления в соответствии с `nPos` и перерисовывает панели, чтобы отразить новое место.  
  
```  
int SetPos(int nPos);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Новое положение индикатора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В предыдущее расположение поля индикатора.  
  
### <a name="remarks"></a>Примечания  
 Положение индикатора не физическое расположение на экране, но вместо между верхней и нижней диапазона указывается в [SetRange](#setrange).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl&#7;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]  
  
##  <a name="setrange"></a>CProgressCtrl::SetRange  
 Задает верхний и нижний пределы индикатора диапазон элемента управления и перерисовывает панели, чтобы отразить новые диапазоны.  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>Параметры  
 `nLower`  
 Задает нижнюю границу диапазона (по умолчанию равно нулю).  
  
 `nUpper`  
 Задает верхнюю границу диапазона (по умолчанию — 100).  
  
### <a name="remarks"></a>Примечания  
 Функция-член `SetRange32` задает 32-разрядным диапазоном для управления ходом выполнения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl №&8;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]  
  
##  <a name="setstate"></a>CProgressCtrl::SetState  
 Задает состояние текущего элемента управления "Индикатор выполнения".  
  
```  
int SetState(int iState);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iState`|Состояние, устанавливаемое для индикатора выполнения. Необходимо использовать одно из следующих значений.<br /><br /> - `PBST_NORMAL`-Идет<br />- `PBST_ERROR`-Ошибка<br />- `PBST_PAUSED`-Приостановлена|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее состояние текущего элемента управления "Индикатор выполнения".  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PBM_SETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760850) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Пример  
 Следующий пример кода позволяет задать состояние текущего индикатора выполнения: "Приостановлено" или "Выполняется".  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]  
  
##  <a name="setstep"></a>CProgressCtrl::SetStep  
 Задает шаг прироста для индикатора.  
  
```  
int SetStep(int nStep);
```  
  
### <a name="parameters"></a>Параметры  
 *nStep*  
 Новый шаг приращения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущего шага приращения.  
  
### <a name="remarks"></a>Примечания  
 Шаг приращения является величина, на которую вызов `CProgressCtrl::StepIt` хода выполнения увеличивается строки в текущей позиции.  
  
 Шаг приращения по умолчанию — 10.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl №&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]  
  
##  <a name="stepit"></a>CProgressCtrl::StepIt  
 Увеличивает текущую позицию для индикатора на шаг приращения и перерисовывает панели, чтобы отразить новое место.  
  
```  
int StepIt();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В предыдущее расположение поля индикатора.  
  
### <a name="remarks"></a>Примечания  
 Шаг приращения задается `CProgressCtrl::SetStep` функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CProgressCtrl&#10;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



