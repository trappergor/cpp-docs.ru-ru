---
title: "CSpinButtonCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CSpinButtonCtrl
- CSpinButtonCtrl class
- CSpinButtonCtrl class, common controls
- up-down controls, spin button control
- spin button control
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
caps.latest.revision: 23
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
ms.openlocfilehash: 486a0842ed04f0e760bbb332986a97a35ce9851f
ms.lasthandoff: 02/24/2017

---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "счетчик" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Создает объект `CSpinButtonCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](#create)|Регулятор создает и присоединяет его к `CSpinButtonCtrl` объекта.|  
|[CSpinButtonCtrl::CreateEx](#createex)|Создает регулятор с указанным расширенные стили Windows и присоединяет его к `CSpinButtonCtrl` объекта.|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|Извлекает сведения о ускорение для регулятор.|  
|[CSpinButtonCtrl::GetBase](#getbase)|Извлекает текущей базы для регулятор.|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Извлекает указатель на текущее окно контактов.|  
|[CSpinButtonCtrl::GetPos](#getpos)|Получает текущее положение регулятор.|  
|[CSpinButtonCtrl::GetRange](#getrange)|Извлекает верхнее и нижнее ограничение (диапазон) для управления "Счетчик".|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|Задает ускорение для регулятор.|  
|[CSpinButtonCtrl::SetBase](#setbase)|Задает основание регулятор.|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Задает окно регулятор контактов.|  
|[CSpinButtonCtrl::SetPos](#setpos)|Задает текущую позицию элемента управления.|  
|[CSpinButtonCtrl::SetRange](#setrange)|Задает верхний и нижний пределы (диапазон) для управления "Счетчик".|  
  
## <a name="remarks"></a>Примечания  
 «Регулятор» (также известный как элемент управления вверх / вниз) представляет собой пару кнопок со стрелками, пользователь может щелкнуть для увеличения или уменьшения значения, такие как позиция прокрутки или числа, отображаемые в элементе управления помощник по поиску. Значение, связанное с элементом управления "Счетчик" вызывается ее текущей позиции. Регулятор чаще всего используется с сопутствующим элементом управления, называемая «окном контактов».  
  
 Этот элемент управления (и, следовательно, `CSpinButtonCtrl` класса) доступны только для программы, запущенные в Windows 95/98 и Windows NT версии 3.51 и более поздних версий.  
  
 Пользователю регулятор и окна ее контактов часто выглядеть одного элемента управления. Можно указать, что регулятор автоматически располагаться рядом с его окна контактов и что он автоматически присваивается заголовок окна контактов ее текущей позиции. Регулятор с ввода позволяет запрашивать у пользователя входных числовых данных.  
  
 Нажмите кнопку со стрелкой вверх перемещает текущую позицию увеличивается до максимума, и нажмите кнопку со стрелкой вниз текущей позиции уменьшается до минимума. По умолчанию минимальное значение — 100, а максимальное значение — 0. Каждый раз, когда минимального значения превышает максимальное значение параметра (например, если используются параметры по умолчанию), нажав кнопку вверх Стрелка уменьшается значение позиции и щелкнув стрелку вниз повышает его.  
  
 Регулятор без окна контактов функции сортировки упрощенный прокрутки. Например набор вкладок иногда отображается регулятор пользователь, который прокручивается в представлении дополнительные вкладки.  
  
 Дополнительные сведения об использовании `CSpinButtonCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CSpinButtonCtrl с помощью](../../mfc/using-cspinbuttonctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="create"></a>CSpinButtonCtrl::Create  
 Регулятор создает и присоединяет его к `CSpinButtonCtrl` объекта...  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль кнопки элемента управления "Счетчик". Любое сочетание стили кнопок элемента управления "Счетчик" примените к элементу управления. Эти стили, описаны в [стили элемента управления вверх / вниз](http://msdn.microsoft.com/library/windows/desktop/bb759885) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Задает размер и положение элемента управления "Счетчик" кнопки. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры  
  
 `pParentWnd`  
 Указатель на кнопке счетчик родительского окна, обычно `CDialog`. Оно не должно быть **значение NULL.**  
  
 `nID`  
 Указывает идентификатор кнопки элемента управления "Счетчик".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создания `CSpinButtonCtrl` объект в два этапа, вызовите конструктор и затем вызвать **создать**, который создает счетчик-элемент управления и присоединяет его к `CSpinButtonCtrl` объекта.  
  
 Чтобы создать регулятор с расширенные стили окна, вызовите [CSpinButtonCtrl::CreateEx](#createex) вместо **создать**.  
  
##  <a name="createex"></a>CSpinButtonCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связывает его с `CSpinButtonCtrl` объекта.  
  
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
 Указывает расширенный стиль создаваемого элемента управления. Список стилей расширенной windows, см. `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Задает стиль кнопки элемента управления "Счетчик". Любое сочетание стили кнопок элемента управления "Счетчик" примените к элементу управления. Эти стили, описаны в [стили элемента управления вверх / вниз](http://msdn.microsoft.com/library/windows/desktop/bb759885) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
##  <a name="cspinbuttonctrl"></a>CSpinButtonCtrl::CSpinButtonCtrl  
 Создает объект `CSpinButtonCtrl`.  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="getaccel"></a>CSpinButtonCtrl::GetAccel  
 Извлекает сведения о ускорение для регулятор.  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nAccel`  
 Количество элементов массива, заданного параметром `pAccel`.  
  
 `pAccel`  
 Указатель на массив [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) структуры, которые получает сведения о ускорение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Получить число структур сочетаний клавиш.  
  
##  <a name="getbase"></a>CSpinButtonCtrl::GetBase  
 Извлекает текущей базы для регулятор.  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее базовое значение.  
  
##  <a name="getbuddy"></a>CSpinButtonCtrl::GetBuddy  
 Извлекает указатель на текущее окно контактов.  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель текущего окна контактов.  
  
##  <a name="getpos"></a>CSpinButtonCtrl::GetPos  
 Получает текущее положение регулятор.  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  ```  
  
### Parameters  
 *lpbError*  
 A pointer to a boolean value that is set to zero if the value is successfully retrieved or non-zero if an error occurs. If this parameter is set to **NULL**, errors are not reported.  
  
### Return Value  
 The first version returns the 16-bit current position in the low-order word. The high-order word is nonzero if an error occurred.  
  
 The second version returns the 32-bit position.  
  
### Remarks  
 When it processes the value returned, the control updates its current position based on the caption of the buddy window. The control returns an error if there is no buddy window or if the caption specifies an invalid or out-of-range value.  
  
##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange  
 Retrieves the upper and lower limits (range) for a spin button control.  
  
```  
DWORD GetRange() константу;  
  
void GetRange (int & ниже,  
    int & верхней) константу;  
  
void GetRange32 (int & ниже,  
    int & верхней) константу;  
```  
  
### Parameters  
 *lower*  
 Reference to an integer that receives the lower limit for the control.  
  
 *upper*  
 Reference to an integer that receives the upper limit for the control.  
  
### Return Value  
 The first version returns a 32-bit value containing the upper and lower limits. The low-order word is the upper limit for the control, and the high-order word is the lower limit.  
  
### Remarks  
 The member function `GetRange32` retrieves the spin button control's range as a 32-bit integer.  
  
##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel  
 Sets the acceleration for a spin button control.  
  
```  
SetAccel BOOL (int nAccel,  
    UDACCEL* pAccel);
```  
  
### Parameters  
 `nAccel`  
 Number of [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) structures specified by `pAccel`.  
  
 `pAccel`  
 Pointer to an array of `UDACCEL` structures, which contain acceleration information. Elements should be sorted in ascending order based on the **nSec** member.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase  
 Sets the base for a spin button control.  
  
```  
int SetBase (int nBase);
```  
  
### Parameters  
 `nBase`  
 New base value for the control. It can be 10 for decimal or 16 for hexadecimal.  
  
### Return Value  
 The previous base value if successful, or zero if an invalid base is given.  
  
### Remarks  
 The base value determines whether the buddy window displays numbers in decimal or hexadecimal digits. Hexadecimal numbers are always unsigned; decimal numbers are signed.  
  
##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy  
 Sets the buddy window for a spin button control.  
  
```  
CWnd* SetBuddy (CWnd* pWndBuddy);
```  
  
### Parameters  
 `pWndBuddy`  
 Pointer to the new buddy window.  
  
### Return Value  
 A pointer to the previous buddy window.  
  
### Remarks  
 A spin control is almost always associated with another window, such as an edit control, that displays some content. This other window is called the "buddy" of the spin control.  
  
##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos  
 Sets the current position for a spin button control.  
  
```  
int SetPos (int nPos);  
int SetPos32(int nPos);
```  
  
### Parameters  
 `nPos`  
 New position for the control. This value must be in the range specified by the upper and lower limits for the control.  
  
### Return Value  
 The previous position (16-bit precision for `SetPos`, 32-bit precision for `SetPos32`).  
  
### Remarks  
 `SetPos32` sets the 32-bit position.  
  
##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange  
 Sets the upper and lower limits (range) for a spin button control.  
  
```  
void SetRange (короткий nLower,  
    Краткое nUpper);

 
void SetRange32 (int nLower,  
    int nUpper);
```  
  
### Parameters  
 `nLower`and `nUpper`  
 Upper and lower limits for the control. For `SetRange`, neither limit can be greater than **UD_MAXVAL** or less than **UD_MINVAL**; in addition, the difference between the two limits cannot exceed **UD_MAXVAL**. `SetRange32` places no restrictions on the limits; use any integers.  
  
### Remarks  
 The member function `SetRange32` sets the 32-bit range for the spin button control.  
  
> [!NOTE]
>  The default range for the spin button has the maximum set to zero (0) and the minimum set to 100. Because the maximum value is less than the minimum value, clicking the up arrow will decrease the position and clicking the down arrow will increase it. Use `CSpinButtonCtrl::SetRange` to adjust these values.  
  
## See Also  
 [MFC Sample CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd Class](../../mfc/reference/cwnd-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Class](../../mfc/reference/csliderctrl-class.md)

