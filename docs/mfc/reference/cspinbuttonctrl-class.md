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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 91be67ccbf1fb7fb863aa4072d55bb3f330aa44f
ms.lasthandoff: 04/04/2017

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
|[CSpinButtonCtrl::Create](#create)|Создает счетчик-элемент управления и прикрепляет его к `CSpinButtonCtrl` объекта.|  
|[CSpinButtonCtrl::CreateEx](#createex)|Создает счетчик-элемент управления с указанным расширенные стили Windows и прикрепляет его к `CSpinButtonCtrl` объекта.|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|Извлекает сведения о ускорение для счетчик-элемент управления.|  
|[CSpinButtonCtrl::GetBase](#getbase)|Извлекает базе текущий счетчик-элемент управления.|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Извлекает указатель на текущее окно контактному лицу.|  
|[CSpinButtonCtrl::GetPos](#getpos)|Получает текущее положение счетчик-элемент управления.|  
|[CSpinButtonCtrl::GetRange](#getrange)|Возвращает верхний и нижний пределы (диапазон) для элемента управления button "Счетчик".|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|Задает ускорение для счетчик-элемент управления.|  
|[CSpinButtonCtrl::SetBase](#setbase)|Задает основание счетчик-элемент управления.|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Задает в связанном окне для счетчик-элемент управления.|  
|[CSpinButtonCtrl::SetPos](#setpos)|Задает текущую позицию элемента управления.|  
|[CSpinButtonCtrl::SetRange](#setrange)|Задает верхний и нижний пределы (диапазон) для элемента управления button "Счетчик".|  
  
## <a name="remarks"></a>Примечания  
 «Регулятор» (также известная как элемент управления вверх / вниз) — это пара кнопок со стрелками, пользователь может щелкнуть для увеличения или уменьшения значения, например позиции прокрутки или номер, отображаемые в элементе управления дополнительное. Значение, связанное с элементом управления "Счетчик", называется текущей позиции. Регулятор наиболее часто используется с дополнительное элемент управления с именем «окно контактному лицу».  
  
 Этот элемент управления (и, следовательно, `CSpinButtonCtrl` класс) доступен только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних.  
  
 Для пользователя, а регулятор и окна ее контактному лицу часто выглядеть одного элемента управления. Можно указать, что регулятор автоматически поместить себя рядом с его окна контактному лицу и, он автоматически присваивается заголовок окна контактному лицу по текущей позиции. Регулятор с помощью элемента управления можно использовать для запроса у пользователя для ввода чисел.  
  
 Нажмите кнопку со стрелкой вверх перемещает текущую позицию увеличивается до максимума, и щелкните стрелку вниз перемещает текущую позицию уменьшается до минимума. По умолчанию минимальное значение — 100, а максимальное значение — 0. Каждый раз, когда минимальное значение превышает максимальное значение параметра (например, если используются параметры по умолчанию), по нажатию кнопки вверх Стрелка уменьшается значение позиции и щелкните стрелку вниз увеличивает его.  
  
 Счетчик-элемент управления без окна контактному лицу функции сортировки полосы прокрутки упрощенный. Например набор вкладок иногда отображаются регулятор, чтобы пользователь мог прокрутку и отобразить дополнительные вкладки.  
  
 Дополнительные сведения об использовании `CSpinButtonCtrl`, в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="create"></a>CSpinButtonCtrl::Create  
 Создает счетчик-элемент управления и прикрепляет его к `CSpinButtonCtrl` объекта...  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль кнопки элемента управления "Счетчик". Любое сочетание стилей элемента управления "Счетчик" кнопку примените к элементу управления. Эти стили описаны в [стили элемента управления вверх / вниз](http://msdn.microsoft.com/library/windows/desktop/bb759885) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Задает размер и положение элемента управления "Счетчик" кнопки. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры  
  
 `pParentWnd`  
 Указатель на кнопку элемента управления "Счетчик" родительского окна, обычно `CDialog`. Он не должен быть **значение NULL.**  
  
 `nID`  
 Указывает идентификатор элемента управления "Счетчик" кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CSpinButtonCtrl` объекта сначала в два этапа, вызовите конструктор, а затем вызвать **создать**, который создает счетчик-элемент управления и прикрепляет его к `CSpinButtonCtrl` объекта.  
  
 Чтобы создать счетчик-элемент управления с расширенные стили окна, вызовите [CSpinButtonCtrl::CreateEx](#createex) вместо **создать**.  
  
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
 Указывает расширенный стиль создаваемого элемента управления. Список windows расширенных стилей см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Задает стиль кнопки элемента управления "Счетчик". Любое сочетание стилей элемента управления "Счетчик" кнопку примените к элементу управления. Эти стили описаны в [стили элемента управления вверх / вниз](http://msdn.microsoft.com/library/windows/desktop/bb759885) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
##  <a name="cspinbuttonctrl"></a>CSpinButtonCtrl::CSpinButtonCtrl  
 Создает объект `CSpinButtonCtrl`.  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="getaccel"></a>CSpinButtonCtrl::GetAccel  
 Извлекает сведения о ускорение для счетчик-элемент управления.  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nAccel`  
 Количество элементов массива, заданного параметром `pAccel`.  
  
 `pAccel`  
 Указатель на массив [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) структуры, которые получает данные для ускорения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Получить число структур сочетаний клавиш.  
  
##  <a name="getbase"></a>CSpinButtonCtrl::GetBase  
 Извлекает базе текущий счетчик-элемент управления.  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее базовое значение.  
  
##  <a name="getbuddy"></a>CSpinButtonCtrl::GetBuddy  
 Извлекает указатель на текущее окно контактному лицу.  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущее окно контактному лицу.  
  
##  <a name="getpos"></a>CSpinButtonCtrl::GetPos  
 Получает текущее положение счетчик-элемент управления.  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpbError*  
 Указатель на значение типа boolean, значение равно нулю, если значение успешно получены, или ненулевое значение, если произошла ошибка. Если этот параметр имеет значение **NULL**, ошибки не отображаются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая версия возвращает 16-разрядное текущую позицию в младшее слово. Старшее слово ненулевое значение, если произошла ошибка.  
  
 Вторая версия возвращает позицию 32-разрядной.  
  
### <a name="remarks"></a>Примечания  
 При обработке возвращаемое значение, элемент управления обновляет ее текущей позиции, основанной на заголовок окна контактному лицу. Элемент управления возвращает ошибку, если нет окна контактному лицу или заголовок указывает недопустимое или вне диапазона значение.  
  
##  <a name="getrange"></a>CSpinButtonCtrl::GetRange  
 Возвращает верхний и нижний пределы (диапазон) для элемента управления button "Счетчик".  
  
```  
DWORD GetRange() const;  
  
void GetRange(
    int& lower,  
    int& upper) const;  
  
void GetRange32(
    int& lower,  
    int &upper) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *Ниже*  
 Ссылка на целое число, Получает нижний предел для элемента управления.  
  
 *верхний*  
 Ссылка на целое число, Получает верхний предел для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая версия возвращает 32-разрядное значение, содержащее верхний и нижний пределы. Младшее слово верхний предел для элемента управления, который старшее слово нижнего предела.  
  
### <a name="remarks"></a>Примечания  
 Функция-член `GetRange32` извлекает диапазон кнопки элемента управления "Счетчик" как 32-разрядное целое число.  
  
##  <a name="setaccel"></a>CSpinButtonCtrl::SetAccel  
 Задает ускорение для счетчик-элемент управления.  
  
```  
BOOL SetAccel(
    int nAccel,  
    UDACCEL* pAccel);
```  
  
### <a name="parameters"></a>Параметры  
 `nAccel`  
 Число [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) структур, указанных `pAccel`.  
  
 `pAccel`  
 Указатель на массив `UDACCEL` структуры, которые содержат сведения для ускорения. Элементы должны быть отсортированы по возрастанию на основе **nSec** член.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="setbase"></a>CSpinButtonCtrl::SetBase  
 Задает основание счетчик-элемент управления.  
  
```  
int SetBase(int nBase);
```  
  
### <a name="parameters"></a>Параметры  
 `nBase`  
 Новый базовое значение для элемента управления. Он может быть 10 в качестве десятичного или 16 для шестнадцатеричной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие базовое значение в случае успешного выполнения, или нуль, если указано недопустимое основание.  
  
### <a name="remarks"></a>Примечания  
 Базовое значение определяет, отображаются ли в связанном окне в десятичное или шестнадцатеричное цифр номера. Шестнадцатеричные числа всегда не имеют знака; десятичные числа подписываются.  
  
##  <a name="setbuddy"></a>CSpinButtonCtrl::SetBuddy  
 Задает в связанном окне для счетчик-элемент управления.  
  
```  
CWnd* SetBuddy(CWnd* pWndBuddy);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndBuddy`  
 Указатель на окно нового контакта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на предыдущее окно контактному лицу.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления "Счетчик" почти всегда связан с другое окно, такие как элемент управления, отображающий некоторое содержимое. Это другое окно называется «контакт» элемента управления "Счетчик".  
  
##  <a name="setpos"></a>CSpinButtonCtrl::SetPos  
 Задает текущую позицию для счетчик-элемент управления.  
  
```  
int SetPos(int nPos);  
int SetPos32(int nPos);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Новое положение элемента управления. Это значение должно быть в диапазоне, определяемом верхняя и нижняя границы для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущей позиции (16-разрядной точности для `SetPos`32- разрядная точность для `SetPos32`).  
  
### <a name="remarks"></a>Примечания  
 `SetPos32`Задает положение 32-разрядной.  
  
##  <a name="setrange"></a>CSpinButtonCtrl::SetRange  
 Задает верхний и нижний пределы (диапазон) для элемента управления button "Счетчик".  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>Параметры  
 `nLower` и `nUpper`.  
 Верхняя и нижняя границы для элемента управления. Для `SetRange`, ни ограничение может быть больше, чем **UD_MAXVAL** или меньше, чем **UD_MINVAL**; Кроме того, не может превышать разницу между двумя ограничениями **UD_MAXVAL**. `SetRange32`не накладывает ограничений на ограничения; Используйте любой целых чисел.  
  
### <a name="remarks"></a>Примечания  
 Функция-член `SetRange32` задает 32-разрядным диапазоном для кнопки элемента управления "Счетчик".  
  
> [!NOTE]
>  Диапазон по умолчанию для кнопки "Счетчик" имеет значение ноль (0) максимальное и минимальное значение 100. Так как максимальное значение меньше минимального значения, нажав кнопку со стрелкой вверх приведет к уменьшению позицию, щелкнув стрелку вниз увеличивается его. Используйте `CSpinButtonCtrl::SetRange` для настройки этих значений.  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CSliderCtrl](../../mfc/reference/csliderctrl-class.md)

