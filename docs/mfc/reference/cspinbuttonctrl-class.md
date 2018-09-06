---
title: Класс CSpinButtonCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a12e5abcc02017acbd06c841cc9ab62a9d25bdf
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757105"
---
# <a name="cspinbuttonctrl-class"></a>Класс CSpinButtonCtrl
Предоставляет функциональные возможности стандартного элемента управления "счетчик" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Создает объект `CSpinButtonCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](#create)|Создает управления "Счетчик" и присоединяет его к `CSpinButtonCtrl` объекта.|  
|[CSpinButtonCtrl::CreateEx](#createex)|Создает управления "Счетчик" с указанным расширенные стили Windows и присоединяет его к `CSpinButtonCtrl` объекта.|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|Извлекает сведения о ускорение для управления "Счетчик".|  
|[CSpinButtonCtrl::GetBase](#getbase)|Извлекает текущий основание системы счисления для управления "Счетчик".|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Извлекает указатель на текущее окно контактов.|  
|[CSpinButtonCtrl::GetPos](#getpos)|Извлекает текущее положение элемента управления "Счетчик".|  
|[CSpinButtonCtrl::GetRange](#getrange)|Извлекает верхний и нижний пределы (диапазон) для управления "Счетчик".|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|Задает ускорение для управления "Счетчик".|  
|[CSpinButtonCtrl::SetBase](#setbase)|Задает основание системы счисления для управления "Счетчик".|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Задает в связанном окне для управления "Счетчик".|  
|[CSpinButtonCtrl::SetPos](#setpos)|Задает текущую позицию для элемента управления.|  
|[CSpinButtonCtrl::SetRange](#setrange)|Задает верхний и нижний пределы (диапазон) для управления "Счетчик".|  
  
## <a name="remarks"></a>Примечания  
 «Управления"Счетчик"» (также известный как элемент управления вверх вниз) представляет собой пару кнопок со стрелками, который пользователь может щелкнуть для увеличения или уменьшения значения, такие как позиция прокрутки или номер, показанный в сопутствующим элементом управления. Значение, связанное с элементом управления "Счетчик" называется ее текущей позиции. Управления "Счетчик" наиболее часто используется с сопутствующим элементом управления, называемым «связанным окном».  
  
 Этот элемент управления (и, следовательно `CSpinButtonCtrl` класс) доступны только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних версиях.  
  
 Для пользователя управления "Счетчик" и окна ее buddy часто вид одного элемента управления. Можно указать, что управления "Счетчик" автоматически располагаться рядом с окном buddy, и что он автоматически задайте в качестве заголовка в связанном окне в своем текущем положении. Управления "Счетчик" можно использовать с элементом управления ввода для запроса числового ввода данных пользователем.  
  
 Нажав кнопку со стрелкой вверх перемещает текущую позицию увеличивается до максимума, и щелкните стрелку вниз перемещает текущую позицию уменьшается до минимума. По умолчанию минимальное значение — 100, и максимальное значение — 0. Каждый раз, когда параметр минимального превышает максимальное значение параметра (например, если используются параметры по умолчанию), щелкнув вверх Стрелка уменьшается значение позиции и щелкните стрелку вниз увеличивает его.  
  
 Управления "Счетчик" без связанным окном функционирует как своего рода упрощенное ползунком. Например набор вкладок, иногда отображаются управления "Счетчик", чтобы пользователь мог прокрутки дополнительные вкладки в представлении.  
  
 Дополнительные сведения об использовании `CSpinButtonCtrl`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="create"></a>  CSpinButtonCtrl::Create  
 Создает управления "Счетчик" и присоединяет его к `CSpinButtonCtrl` объекта...  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *dwStyle*  
 Задает стиль элемента управления "Счетчик". Любое сочетание стили элемента управления "Счетчик" примените к элементу управления. Эти стили описаны в [стили элемента управления вверх-вниз](/windows/desktop/Controls/up-down-control-styles) в пакете Windows SDK.  
  
 *Rect*  
 Задает размер и положение элемента управления "Счетчик". Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры  
  
 *pParentWnd*  
 Указатель на управления "Счетчик" родительского окна, обычно `CDialog`. Он не должен иметь значение NULL.  
  
 *nID*  
 Указывает идентификатор элемента управления "Счетчик".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 При создании `CSpinButtonCtrl` объекта в два этапа, во-первых, вызовите конструктор, а затем вызовите `Create`, который создает управления "Счетчик" и присоединяет его к `CSpinButtonCtrl` объекта.  
  
 Чтобы создать управления "Счетчик" с расширенные стили окна, вызовите [CSpinButtonCtrl::CreateEx](#createex) вместо `Create`.  
  
##  <a name="createex"></a>  CSpinButtonCtrl::CreateEx  
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
 *dwExStyle*  
 Указывает расширенный стиль создаваемого элемента управления. Список стилей расширенных windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.  
  
 *dwStyle*  
 Задает стиль элемента управления "Счетчик". Любое сочетание стили элемента управления "Счетчик" примените к элементу управления. Эти стили описаны в [стили элемента управления вверх-вниз](/windows/desktop/Controls/up-down-control-styles) в пакете Windows SDK.  
  
 *Rect*  
 Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.  
  
 *pParentWnd*  
 Указатель на окно, которое является родительским для элемента управления.  
  
 *nID*  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) применение расширенных стилей Windows, определяемое WS_EX_ префикс расширенный стиль Windows.  
  
##  <a name="cspinbuttonctrl"></a>  CSpinButtonCtrl::CSpinButtonCtrl  
 Создает объект `CSpinButtonCtrl`.  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="getaccel"></a>  CSpinButtonCtrl::GetAccel  
 Извлекает сведения о ускорение для управления "Счетчик".  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nAccel*  
 Количество элементов массива, заданного параметром *pAccel*.  
  
 *pAccel*  
 Указатель на массив [UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel) структуры, получающий сведения ускорение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Получить число структур сочетаний клавиш.  
  
##  <a name="getbase"></a>  CSpinButtonCtrl::GetBase  
 Извлекает текущий основание системы счисления для управления "Счетчик".  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее базовое значение.  
  
##  <a name="getbuddy"></a>  CSpinButtonCtrl::GetBuddy  
 Извлекает указатель на текущее окно контактов.  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущее окно контактов.  
  
##  <a name="getpos"></a>  CSpinButtonCtrl::GetPos  
 Извлекает текущее положение элемента управления "Счетчик".  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpbError*  
 Указатель на логическое значение, которое имеет значение нуль, если значение успешно получены, или ненулевое значение, если произошла ошибка. Если этот параметр имеет значение NULL, то ошибки не выводятся.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая версия возвращает 16-разрядное текущую позицию в младшее слово. Старшее слово имеет ненулевое значение, если произошла ошибка.  
  
 Вторая версия возвращает позицию 32-разрядной.  
  
### <a name="remarks"></a>Примечания  
 Когда он обрабатывает значения, возвращаемого, элемент управления обновляет ее текущей позиции, в зависимости от заголовка элемента в связанном окне. Элемент управления возвращает ошибку, если нет buddy окна или если заголовок указывает недопустимое или диапазону значение.  
  
##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange  
 Извлекает верхний и нижний пределы (диапазон) для управления "Счетчик".  
  
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
 *нижний*  
 Ссылка на целое число, которое получает нижнюю границу для элемента управления.  
  
 *верхний*  
 Ссылка на целое число, Получает верхнюю границу для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая версия возвращает 32-разрядное значение, содержащее верхний и нижний пределы. Младшее слово — верхний предел для элемента управления, а старшее слово — нижняя граница.  
  
### <a name="remarks"></a>Примечания  
 Функция-член `GetRange32` извлекает диапазон управления "Счетчик" как 32-разрядное целое число.  
  
##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel  
 Задает ускорение для управления "Счетчик".  
  
```  
BOOL SetAccel(
    int nAccel,  
    UDACCEL* pAccel);
```  
  
### <a name="parameters"></a>Параметры  
 *nAccel*  
 Число [UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel) структур, указанных *pAccel*.  
  
 *pAccel*  
 Указатель на массив структур UDACCEL, которые содержат информацию ускорение. Элементы должны быть отсортированы по возрастанию на основе `nSec` член.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase  
 Задает основание системы счисления для управления "Счетчик".  
  
```  
int SetBase(int nBase);
```  
  
### <a name="parameters"></a>Параметры  
 *nBase*  
 Новый базовое значение для элемента управления. Он может быть 10 в качестве десятичного разделителя или 16 для шестнадцатеричной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение базового при успешном выполнении, или нуль, если указано недопустимое основание.  
  
### <a name="remarks"></a>Примечания  
 Базовое значение определяет, отображает ли в связанном окне номера в десятичных или шестнадцатеричных цифр. Шестнадцатеричные числа всегда не имеют знака; десятичные числа должны быть подписаны.  
  
##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy  
 Задает в связанном окне для управления "Счетчик".  
  
```  
CWnd* SetBuddy(CWnd* pWndBuddy);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndBuddy*  
 Указатель на новое окно контактов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на предыдущее окно контактов.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления "Счетчик" почти всегда связан с другого окна, такие как элемент управления редактирования, который отображает часть содержимого. Это другое окно называется «контакт» элемента управления "Счетчик".  
  
##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos  
 Задает текущую позицию для управления "Счетчик".  
  
```  
int SetPos(int nPos);  
int SetPos32(int nPos);
```  
  
### <a name="parameters"></a>Параметры  
 *nPos*  
 Новая позиция для элемента управления. Это значение должно быть в диапазоне, определяемом верхний и нижний пределы для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущей позиции (16-битной точности для `SetPos`32- разрядное точности для `SetPos32`).  
  
### <a name="remarks"></a>Примечания  
 `SetPos32` Задает положение 32-разрядной.  
  
##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange  
 Задает верхний и нижний пределы (диапазон) для управления "Счетчик".  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>Параметры  
 *nLower* и *nUpper*  
 Верхний и нижний пределы для элемента управления. Для `SetRange`, ни ограничение может быть больше, чем UD_MAXVAL или меньше, чем UD_MINVAL; Кроме того, разница между двумя ограничениями не может превышать UD_MAXVAL. `SetRange32` не накладывает ограничений на ограничения; Используйте любой целых чисел.  
  
### <a name="remarks"></a>Примечания  
 Функция-член `SetRange32` задает 32-разрядным диапазоном, для управления "Счетчик".  
  
> [!NOTE]
>  По умолчанию кнопка "Счетчик" имеет максимальное значение ноль (0), а также минимальное, равным 100. Так как максимальное значение меньше минимального значения, нажав кнопку со стрелкой вверх приведет к уменьшению положение и щелкните стрелку вниз будет увеличить его. Используйте `CSpinButtonCtrl::SetRange` для настройки этих значений.  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CSliderCtrl](../../mfc/reference/csliderctrl-class.md)
